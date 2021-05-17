---
title: Verbundidentität für Ihre Microsoft 365-Testumgebung
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: 65a6d687-a16a-4415-9fd5-011ba9c5fd80
description: 'Zusammenfassung: Konfigurieren der Verbundauthentifizierung für Ihre Microsoft 365-Testumgebung.'
ms.openlocfilehash: 0fb8c55f5b7291cdc6bcec636981a9d31015e723
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487684"
---
# <a name="federated-identity-for-your-microsoft-365-test-environment"></a>Verbundidentität für Ihre Microsoft 365-Testumgebung

*Diese Testumgebungsanleitung kann sowohl für Microsoft 365 als auch für Office 365 Enterprise verwendet werden.*

Microsoft 365 unterstützt Verbundidentität. Dies bedeutet, dass Microsoft 365, anstatt die Prüfung von Anmeldeinformationen selbst durchzuführen, den Benutzer, der eine Verbindung herstellt, auf einen Verbundauthentifizierungsserver verweist, der für Microsoft 365 vertrauenswürdig ist. Wenn die Anmeldeinformationen des Benutzers korrekt sind, gibt der Verbundauthentifizierungsserver ein Sicherheitstoken aus, das der Client als Nachweis der Authentifizierung an Microsoft 365 sendet. Verbundidentität ermöglicht das Abladen und zentrale Skalieren der Authentifizierung für ein Microsoft 365-Abonnement sowie erweiterte Authentifizierungs- und Sicherheitsszenarien.
  
In diesem Artikel wird beschrieben, wie Sie die Verbundauthentifizierung Microsoft 365 Testumgebung konfigurieren, was zu folgenden Folgen führt:

![Die Verbundauthentifizierung für die Microsoft 365-Testumgebung](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
Diese Konfiguration besteht aus:
  
- Ein Microsoft 365 E5 oder Produktionsabonnement.
    
- Ein vereinfachtes Unternehmensintranet, das mit dem Internet verbunden ist und aus fünf virtuellen Computern in einem Subnetz eines virtuellen Azure-Netzwerks (DC1, APP1, CLIENT1, ADFS1 und PROXY1) besteht. Azure AD Verbinden wird auf APP1 ausgeführt, um die Liste der Konten in der Domäne Active Directory Domain Services mit Microsoft 365. PROXY1 erhält die eingehenden Authentifizierungsanfragen. ADFS1 überprüft Anmeldeinformationen mit DC1 und gibt Sicherheitstoken aus.
    
Das Einrichten dieser Testumgebung umfasst fünf Phasen:
- [Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Phase 2: Erstellen des AD FS-Servers](#phase-2-create-the-ad-fs-server)
- [Phase 3: Erstellen des Webproxyservers](#phase-3-create-the-web-proxy-server)
- [Phase 4: Erstellen eines selbstsignierten Zertifikats und Konfigurieren von ADFS1 und PROXY1](#phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1)
- [Phase 5: Konfigurieren von Microsoft 365 für Verbundidentität](#phase-5-configure-microsoft-365-for-federated-identity)
    
> [!NOTE]
> Sie können diese Testumgebung nicht mit einem Azure-Testabonnement konfigurieren.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung

Befolgen Sie die Anweisungen unter [Kennworthashsynchronisierung für Microsoft 365.](password-hash-sync-m365-ent-test-environment.md) Die resultierende Konfiguration sieht wie die folgenden aus:
  
![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase1.png)
  
Diese Konfiguration besteht aus: 
  
- Eine Microsoft 365 E5 oder kostenpflichtige Abonnements.
- Ein vereinfachtes Unternehmensintranet, das mit dem Internet verbunden ist und aus den virtuellen Computern DC1, APP1 und CLIENT1 in einem Subnetz eines virtuellen Azure-Netzwerks besteht. Azure AD Verbinden wird auf APP1 ausgeführt, um die Active Directory Domain Services (AD DS)-Domäne testlab regelmäßig mit dem Azure AD-Mandanten Ihrer Microsoft 365 zu synchronisieren.

## <a name="phase-2-create-the-ad-fs-server"></a>Phase 2: Erstellen des AD FS-Servers

Ein AD FS-Server bietet Verbundauthentifizierung zwischen Microsoft 365 und den Konten in der Domäne „corp.contoso.com“, die auf DC1 gehostet wird.
  
Um einen virtuellen Azure-Computer für ADFS1 zu erstellen, geben Sie den Namen Ihres Abonnements und der Ressourcengruppe sowie den Azure-Speicherort für Ihre Basiskonfiguration ein, und führen Sie diese Befehle in der Azure PowerShell-Befehlszeile auf Ihrem lokalen Computer aus.
  
```powershell
$subscrName="<your Azure subscription name>"
$rgName="<the resource group name of your Base Configuration>"
$vnetName="TlgBaseConfig-01-VNET"
# NOTE: If you built your simulated intranet with Azure PowerShell, comment the previous line with a "#" and remove the "#" from the next line.
#$vnetName="TestLab"
Connect-AzAccount
Select-AzSubscription -SubscriptionName $subscrName
$staticIP="10.0.0.100"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$pip = New-AzPublicIpAddress -Name ADFS1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic = New-AzNetworkInterface -Name ADFS1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName ADFS1 -VMSize Standard_D2_v2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for ADFS1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName ADFS1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "ADFS-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

Im nächsten Schritt stellen Sie über das [Azure-Portal](https://portal.azure.com) eine Verbindung mit dem virtuellen Computer ADFS1 mit dem Namen und Kennwort des lokalen Administratorkontos von ADFS1 her und öffnen dann eine Windows PowerShell-Eingabeaufforderung.
  
Führen Sie zum Überprüfen der Namensauflösung und der Netzwerkkommunikation zwischen ADFS1 und DC1 den Befehl **ping dc1.corp.contoso.com** aus, und vergewissern Sie sich, dass vier Antworten vorhanden sind.
  
Verknüpfen Sie als Nächstes unter Verwendung der folgenden Befehle an der Windows PowerShell-Eingabeaufforderung auf ADFS1 den virtuellen Computer ADFS1 mit der Domäne CORP.
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

Die resultierende Konfiguration sieht wie die folgenden aus:
  
![Der AD FS-Server, der der DirSync für die Microsoft 365-Testumgebung hinzugefügt wurde](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase2.png)
  
## <a name="phase-3-create-the-web-proxy-server"></a>Phase 3: Erstellen des Webproxyservers

PROXY1 stellt die Proxyfunktion für Authentifizierungsnachrichten zwischen Benutzern, die versuchen, sich zu authentifizieren, und ADFS1 bereit.
  
Um einen virtuellen Azure-Computer für PROXY1 zu erstellen, geben Sie den Namen Ihrer Ressourcengruppe und den Azure-Speicherort ein und führen diese Befehle in der Azure PowerShell-Befehlszeile auf Ihrem lokalen Computer aus.
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
$vnetName="TlgBaseConfig-01-VNET"
# NOTE: If you built your simulated intranet with Azure PowerShell, comment the previous line with a "#" and remove the "#" from the next line.
#$vnetName="TestLab"
$staticIP="10.0.0.101"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$pip = New-AzPublicIpAddress -Name PROXY1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Static
$nic = New-AzNetworkInterface -Name PROXY1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName PROXY1 -VMSize Standard_D2_v2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for PROXY1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName PROXY1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "PROXY1-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> PROXY1 wird einer statischen öffentlichen IP-Adresse zugewiesen, da Sie einen öffentlichen DNS-Eintrag erstellen, der darauf verweist, und der nicht geändert werden muss, wenn Sie den virtuellen PROXY1-Computer neu starten.
  
Fügen Sie als Nächstes der Netzwerksicherheitsgruppe für das CorpNet-Subnetz eine Regel hinzu, um unerwünschten eingehenden Datenverkehr aus dem Internet an die private IP-Adresse von PROXY1 und den TCP-Port 443 zu ermöglichen. Führen Sie diese Befehle an der Azure PowerShell-Eingabeaufforderung auf dem lokalen Computer aus.
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
Get-AzNetworkSecurityGroup -Name CorpNet -ResourceGroupName $rgName | Add-AzNetworkSecurityRuleConfig -Name "HTTPS-to-PROXY1" -Description "Allow TCP 443 to PROXY1" -Access "Allow" -Protocol "Tcp" -Direction "Inbound" -Priority 101 -SourceAddressPrefix "Internet" -SourcePortRange "*" -DestinationAddressPrefix "10.0.0.101" -DestinationPortRange "443" | Set-AzNetworkSecurityGroup
```

Im nächsten Schritt stellen Sie über das [Azure-Portal](https://portal.azure.com) eine Verbindung mit dem virtuellen Computer PROXY1 mit dem Kontonamen und Kennwort des lokalen Administratorkontos von PROXY1 her und öffnen dann eine Windows PowerShell-Eingabeaufforderung auf PROXY1.
  
Führen Sie zum Überprüfen der Namensauflösung und der Netzwerkkommunikation zwischen PROXY1 und DC1 den Befehl **ping dc1.corp.contoso.com** aus, und vergewissern Sie sich, dass vier Antworten vorhanden sind.
  
Verknüpfen Sie als Nächstes unter Verwendung der folgenden Befehle an der Windows PowerShell-Eingabeaufforderung auf PROXY1 den virtuellen Computer PROXY1 mit der Domäne CORP.
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

Zeigen Sie die öffentliche IP-Adresse von PROXY1 mit Azure PowerShell befehlen auf Dem lokalen Computer an.
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "PROXY1-PIP" -ResourceGroup $rgName).IPAddress
```

Im nächsten Schritt arbeiten Sie mit Ihrem öffentlichen DNS-Anbieter und erstellen einen neuen öffentlichen DNS A-Eintrag für **fs.testlab.**\<*your DNS domain name*>, der in die IP-Adresse aufgelöst wird, die vom Befehl **Write-Host** angezeigt wird. Auf **fs.testlab.**\<*your DNS domain name*> wird nachfolgend als *FQDN des Verbunddiensts verwiesen*.
  
Im nächsten Schritt stellen Sie über das [Azure-Portal](https://portal.azure.com) eine Verbindung mit dem virtuellen Computer DC1 unter Verwendung der Anmeldeinformationen „CORP\\User1“ her und führen dann die folgenden Befehle an einer Windows PowerShell-Eingabeaufforderung auf Administratorebene aus:
  
```powershell
Add-DnsServerPrimaryZone -Name corp.contoso.com -ZoneFile corp.contoso.com.dns
Add-DnsServerResourceRecordA -Name "fs" -ZoneName corp.contoso.com -AllowUpdateAny -IPv4Address "10.0.0.100" -TimeToLive 01:00:00
```
Diese Befehle erstellen einen internen DNS A-Eintrag, damit virtuelle Computer im virtuellen Azure-Netzwerk den FQDN des internen Verbunddiensts in die private IP-Adresse von ADFS1 auflösen können.
  
Die resultierende Konfiguration sieht wie die folgenden aus:
  
![Der Webanwendungs-Proxyserver, der der DirSync für die Microsoft 365-Testumgebung hinzugefügt wurde](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
## <a name="phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1"></a>Phase 4: Erstellen eines selbstsignierten Zertifikats und Konfigurieren von ADFS1 und PROXY1

In dieser Phase erstellen Sie ein selbstsigniertes digitales Zertifikat für den FQDN des Verbunddiensts und konfigurieren ADFS1 und PROXY1 als AD FS-Farm.
  
Im nächsten Schritt stellen Sie über das [Azure-Portal](https://portal.azure.com) eine Verbindung mit dem virtuellen Computer DC1 unter Verwendung der Anmeldeinformationen „CORP\\User1“ her und öffnen dann eine Windows PowerShell-Eingabeaufforderung auf Administratorebene.
  
Erstellen Sie als Nächstes ein AD FS-Dienstkonto mit diesem Befehl an der eingabeaufforderung Windows PowerShell DC1:
  
```powershell
New-ADUser -SamAccountName ADFS-Service -AccountPassword (read-host "Set user password" -assecurestring) -name "ADFS-Service" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```
Beachten Sie, dass Sie von dem Befehl aufgefordert werden, das Kontokennwort anzugeben. Verwenden Sie ein sicheres Kennwort, und notieren Sie es an einem sicheren Ort. Sie benötigen sie für diese Phase und für Phase 5.
  
Verwenden Sie das [Azure-Portal](https://portal.azure.com), um eine Verbindung zu dem virtuellen Computer ADFS1 unter Verwendung der Anmeldeinformationen „CORP\\User1“ herzustellen. Öffnen Sie eine Windows PowerShell-Eingabeaufforderung auf Administratorebene auf ADFS1, geben Sie den FQDN des Verbunddiensts ein, und führen Sie dann die folgenden Befehle aus, um ein selbstsigniertes Zertifikat zu erstellen:
  
```powershell
$fedServiceFQDN="<federation service FQDN>"
New-SelfSignedCertificate -DnsName $fedServiceFQDN -CertStoreLocation "cert:\LocalMachine\My"
New-Item -path c:\Certs -type directory
New-SmbShare -name Certs -path c:\Certs -changeaccess CORP\User1
```

Gehen Sie dann folgendermaßen vor, um das neue selbstsignierte Zertifikat als Datei zu speichern.
  
1. Wählen **Sie Start** aus, geben **mmc.exe** ein, und drücken Sie dann die **EINGABETASTE.**
    
2. Wählen **Sie Datei**  >  **hinzufügen/entfernen Andocken-In aus.**
    
3. Doppelklicken Sie **unter Andocken-Ins** hinzufügen oder entfernen **in** der Liste der verfügbaren Snap-Ins auf Zertifikate, wählen Sie **Computerkonto** aus, und wählen Sie dann **Weiter aus.**
    
4. Wählen **Sie unter Computer** auswählen die Option **Fertig** stellen aus, und wählen Sie dann **OK aus.**
    
5. Öffnen Sie im Strukturbereich **Zertifikate (Lokaler Computer) > Persönlich > Zertifikate**.
    
6. Wählen Sie das Zertifikat mit dem FQDN des Verbunddiensts aus, und halten Sie es fest (oder klicken Sie mit der rechten Maustaste), wählen Sie **Alle Aufgaben** aus, und wählen Sie **dann Exportieren aus.**
    
7. Wählen Sie **auf der Seite** Willkommen die Option Weiter **aus.**
    
8. Wählen Sie **auf der** Seite Privater Schlüssel exportieren die Option **Ja** aus, und wählen Sie dann **Weiter aus.**
    
9. Wählen Sie **auf der Seite** Dateiformat exportieren die Option Alle **erweiterten** Eigenschaften exportieren aus, und wählen Sie dann **Weiter aus.**
    
10. Wählen Sie **auf der Seite** Sicherheit die Option **Kennwort** aus, und geben Sie ein Kennwort in **Kennwort und** Kennwort **bestätigen ein.**
    
11. Wählen Sie **auf der Seite Zu exportierende** Datei die Option Durchsuchen **aus.**
    
12. Navigieren Sie zum **Ordner C: \\ Certs,** geben Sie **SSL** unter **Dateiname** ein, und wählen Sie dann **Speichern aus.**
    
13. Wählen Sie **auf der Seite Zu exportierende** Datei die Option Weiter **aus.**
    
14. Wählen Sie **auf der Seite Zertifikatexport-Assistent abschließen** die Option Fertig stellen **aus.** Wenn Sie dazu aufgefordert werden, wählen Sie **OK aus.**
    
Im nächsten Schritt erstellen Sie den AD FS-Dienst mit dem folgenden Befehl an der Windows PowerShell-Eingabeaufforderung auf ADFS1:
  
```powershell
Install-WindowsFeature ADFS-Federation -IncludeManagementTools
```

Warten Sie, bis die Installation abgeschlossen ist.
  
Konfigurieren Sie als Nächstes den AD FS-Dienst mit den folgenden Schritten:
  
1. Wählen **Sie Start** aus, und wählen Sie dann das Symbol **Server-Manager** aus.
    
2. Wählen Sie im Strukturbereich von Server Manager AD **FS aus.**
    
3. Wählen Sie oben in der Toolleiste das orangefarbene Warnsymbol aus, und wählen Sie dann Konfigurieren des Verbunddiensts **auf diesem Server aus.**
    
4. Wählen Sie **auf der Willkommensseite** des Active Directory Federation Services Configuration Wizard die Option **Weiter aus.**
    
5. Wählen Sie **auf Verbinden zu AD DS** die Option Weiter **aus.**
    
6. Auf der Seite **Diensteigenschaften angeben**:
    
  - Wählen **Sie für SSL-Zertifikat** den Pfeil nach unten aus, und wählen Sie dann das Zertifikat mit dem Namen Des Verbunddienst-FQDN aus.
    
  - Geben **Sie unter Anzeigename** des Verbunddiensts den Namen Ihrer fiktiven Organisation ein.
    
  - Wählen Sie **Weiter** aus.
    
7. Wählen Sie **auf der Seite Dienstkonto angeben** die Option **Für** **Kontonamen auswählen aus.**
    
8. Geben **Sie unter Benutzer- oder Dienstkonto auswählen** **ADFS-Service ein,** wählen Sie Namen **überprüfen** aus, und wählen Sie dann **OK aus.**
    
9. Geben **Sie unter** Kontokennwort das Kennwort für das ADFS-Service ein, und wählen Sie dann Weiter **aus.**
    
10. Wählen Sie auf der Seite **Konfigurationsdatenbank angeben** die Option **Weiter aus.**
    
11. Wählen Sie **auf der** Seite Überprüfungsoptionen die Option **Weiter aus.**
    
12. Wählen Sie **auf der Seite Erforderliche Prüfungen** die Option Konfigurieren **aus.**

13. Wählen Sie **auf der** Seite Ergebnisse die Option **Schließen aus.**
    
14. Wählen **Sie Start** aus, wählen Sie das Netzsymbol aus, wählen Sie **Neustart** aus, und wählen Sie dann **Weiter aus.**
    
Melden Sie sich über das [Azure-Portal](https://portal.azure.com) mit dem CORP\\User1-Konto bei PROXY1 an.
  
Gehen Sie dann folgendermaßen vor, um das selbstsignierte Zertifikat auf **PROXY1 und APP1** zu installieren.
  
1. Wählen **Sie Start** aus, geben **mmc.exe** ein, und drücken Sie dann die **EINGABETASTE.**
    
2. Wählen **Sie Datei > Hinzufügen/Entfernen Andocken-In aus.**
    
3. Doppelklicken Sie **unter Andocken-Ins** hinzufügen oder entfernen **in** der Liste der verfügbaren Snap-Ins auf Zertifikate, wählen Sie **Computerkonto** aus, und wählen Sie dann **Weiter aus.**
    
4. Wählen **Sie unter Computer** auswählen die Option **Fertig** stellen aus, und wählen Sie dann **OK aus.**
    
5. Öffnen Sie im Strukturbereich **Zertifikate (Lokaler Computer)**  >  **Persönliche**  >  **Zertifikate**.
    
6. Wählen Und halten (oder klicken Sie mit der rechten Maustaste) **Personal**, wählen **Sie Alle Aufgaben** aus, und wählen Sie dann Importieren **aus.**
    
7. Wählen Sie **auf der Seite** Willkommen die Option Weiter **aus.**
    
8. Geben Sie **auf der Seite Zu importierende** Datei **\\ \\ adfs1 \\ certs \\ ssl.pfx** ein, und wählen Sie dann **Weiter aus.**
    
9. Geben Sie **auf der Seite** Schutz privater Schlüssel das Zertifikatkennwort in **Kennwort** ein, und wählen Sie dann **Weiter aus.**
    
10. Wählen Sie **auf der Seite Zertifikatspeicher** die Option **Weiter aus.**
    
11. Wählen Sie **auf der Seite** Fertigstellung die Option Fertig stellen **aus.**
    
12. Wählen Sie **auf** Store Seite Zertifikat die Option **Weiter aus.**
    
13. Wenn Sie dazu aufgefordert werden, wählen Sie **OK aus.**
    
14. Wählen Sie im Strukturbereich Zertifikate **aus.**
    
15. Wählen Sie das Zertifikat aus, und halten Sie es fest (oder klicken Sie mit der rechten Maustaste), und wählen Sie dann **Kopieren aus.**
    
16. Öffnen Sie im Strukturbereich Zertifikate für **vertrauenswürdige Stammzertifizierungsstellen**  >  .
    
17. Bewegen Sie den Mauszeiger unter die Liste der installierten Zertifikate, wählen Sie und halten Sie (oder klicken Sie mit der rechten Maustaste), und wählen Sie dann **Einfügen aus.**
    
Öffnen Sie eine PowerShell-Eingabeaufforderung auf Administratorebene, und führen Sie den folgenden Befehl aus:
  
```powershell
Install-WindowsFeature Web-Application-Proxy -IncludeManagementTools
```

Warten Sie, bis die Installation abgeschlossen ist.
  
Verwenden Sie die folgenden Schritte, um den Webanwendungs-Proxydienst so zu konfigurieren, dass ADFS1 als Verbundserver verwendet wird:
  
1. Wählen **Sie Start** aus, und wählen Sie dann **Server-Manager aus.**
    
2. Wählen Sie im Strukturbereich **Remotezugriff aus.**
    
3. Wählen Sie oben in der Toolleiste das orangefarbene Warnsymbol aus, und wählen Sie dann **Den Webanwendungsproxy-Assistenten öffnen aus.**
    
4. Wählen Sie **auf der** Seite Willkommen des Assistenten für die Webanwendungsproxykonfiguration die Option **Weiter aus.**
    
5. Auf der Seite **Verbundserver**:
    
  - Geben Sie **im Feld Verbunddienstname** den FQDN des Verbunddiensts ein.
    
  - Geben Sie **im Feld Benutzername** corp **\\ User1 ein.**
    
  - Geben Sie **im Feld** Kennwort das Kennwort für das Benutzerkonto "User1" ein.
    
  - Wählen Sie **Weiter** aus.
    
6. Wählen Sie auf der **Seite AD FS-Proxyzertifikat** den Pfeil nach unten aus, wählen Sie das Zertifikat mit dem FQDN des Verbunddiensts aus, und wählen Sie dann **Weiter aus.**
    
7. Wählen Sie **auf der Seite** Bestätigung die Option Konfigurieren **aus.**
    
8. Wählen Sie **auf der** Seite Ergebnisse die Option **Schließen aus.**
    
## <a name="phase-5-configure-microsoft-365-for-federated-identity"></a>Phase 5: Konfigurieren von Microsoft 365 für Verbundidentität

Verwenden Sie das [Azure-Portal](https://portal.azure.com), um eine Verbindung zu dem virtuellen Computer APP1 unter Verwendung der Kontoanmeldeinformationen „CORP\\User1“ herzustellen.
  
Verwenden Sie diese Schritte, um Azure AD Connect und Ihr Microsoft 365-Abonnement für die Verbundauthentifizierung zu konfigurieren:
  
1. Doppelklicken Sie auf dem Desktop auf **Azure AD Connect**.
    
2. Wählen Sie auf der Seite Willkommen bei **Azure AD Verbinden** Konfigurieren **aus.**
    
3. Wählen Sie **auf der** Seite Zusätzliche Aufgaben die Option **Benutzeranmelden ändern** aus, und wählen Sie dann Weiter **aus.**
    
4. Geben Sie **auf Verbinden Azure AD** den Namen und das Kennwort Ihres globalen Administratorkontos ein, und wählen Sie dann Weiter **aus.**
    
5. Wählen Sie **auf der Seite Benutzeranmelden** die Option **Verbund mit AD FS** aus, und wählen Sie dann **Weiter aus.**
    
6. Wählen Sie auf der **Seite AD FS-Farm** die Option Vorhandene **AD FS-Farm** verwenden aus, geben Sie **ADFS1** in das Feld **Servername** ein, und wählen Sie dann **Weiter aus.**
    
7. Wenn Sie zur Eingabe von Serveranmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen des CORP User1-Kontos ein, und wählen \\ Sie dann **OK aus.**
    
8. Geben Sie **auf der Seite Anmeldeinformationen** des Domänenadministrators corp **\\ User1** in das Feld **Benutzername** ein, geben Sie das Kontokennwort in das Feld **Kennwort** ein, und wählen Sie dann **Weiter aus.**
    
9. Geben Sie auf der **Seite AD FS-Dienstkonto** corp  **\\ ADFS-Service** in das Feld Domänenbenutzername ein, geben Sie das Kontokennwort in das Feld **Domänenbenutzerkennwort** ein, und wählen Sie dann Weiter **aus.**
    
10. Wählen Sie auf der **Seite Azure AD-Domäne** unter **Domäne** den Namen der Domäne aus, die Sie zuvor in Phase 1 erstellt und Ihrem Abonnement hinzugefügt haben, und wählen Sie dann **Weiter aus.**
    
11. Wählen Sie **auf der Seite** Bereit zum Konfigurieren die Option Konfigurieren **aus.**
    
12. Wählen Sie **auf der Seite Installation abgeschlossen** die Option Überprüfen **aus.**
    
    Es sollten Nachrichten angezeigt werden, die angeben, dass sowohl die Intranet- als auch die Internetkonfiguration überprüft wurde.
    
13. Wählen Sie **auf der Seite Installation abgeschlossen** die Option Beenden **aus.**
    
Gehen Sie folgendermaßen vor, um zu zeigen, dass die Verbundauthentifizierung funktioniert:
  
1. Öffnen Sie eine neue private Instanz Ihres Browsers auf Ihrem lokalen Computer, und wechseln Sie zu [https://admin.microsoft.com](https://admin.microsoft.com).
    
2. Geben Sie für die Anmeldeinformationen user1@  \<*the domain created in Phase 1*> ein.
    
    Wenn Ihre Testdomäne z. **B.** testlab.contoso.com ist, geben Sie "user1@testlab.contoso.com" ein. Drücken Sie **die TAB-TASTE,** Microsoft 365 Sie automatisch umleiten können.
    
    Jetzt sollten Sie die Seite **Die Verbindung ist nicht privat** sehen. Dies liegt daran, dass Sie ein selbst signiertes Zertifikat auf ADFS1 installiert haben, das ihr Desktopcomputer nicht überprüfen kann. In einer Produktionsbereitstellung der Verbundauthentifizierung würden Sie ein Zertifikat von einer vertrauenswürdigen Zertifizierungsstelle verwenden, und Ihre Benutzer würden diese Seite nicht sehen.
    
3. Wählen Sie auf der Seite Ihre **Verbindung ist nicht privat** die Option **Erweitert** aus, und wählen Sie dann Weiter **zu aus. \<*your federation service FQDN*>** 
    
4. Melden Sie sich auf der Seite mit dem Namen Ihrer fiktiven Organisation mit den folgenden Informationen an:
    
  - **CORP\\User1** als Name
    
  - Das Kennwort für das Konto „User1“
    
    Die **Microsoft Office-Startseite** sollte angezeigt werden.
    
In diesem Verfahren wird veranschaulicht, dass Ihr Testabonnement im Verbund mit der AD DS-Domäne „corp.contoso.com“ steht, die auf DC1 gehostet wird. Nachfolgend finden Sie die Grundlagen des Authentifizierungsprozesses:
  
1. Wenn Sie die Verbunddomäne verwenden, die Sie in Phase 1 mit dem Anmeldekontonamen erstellt haben, wird Ihr Browser von Microsoft 365 an den FQDN des Verbunddiensts und PROXY1 umgeleitet.
    
2. PROXY1 sendet dem lokalen Computer die Anmeldeseite des fiktiven Unternehmens.
    
3. Wenn Sie „CORP\\User1“ und das Kennwort an PROXY1 senden, werden diese Informationen an ADFS1 weitergeleitet.
    
4. ADFS1 überprüft CORP\\User1 und das Kennwort mit DC1 und sendet dem lokalen Computer ein Sicherheitstoken.
    
5. Der lokale Computer sendet das Sicherheitstoken an Microsoft 365.
    
6. Microsoft 365 überprüft, dass das Sicherheitstoken von ADFS1 erstellt wurde und erlaubt den Zugriff.
    
Ihr Testabonnement ist jetzt mit Verbundauthentifizierung konfiguriert. Sie können diese Entwicklungs-/Testumgebung für erweiterte Authentifizierungsszenarien verwenden.
  
## <a name="next-step"></a>Nächster Schritt

Wenn Sie bereit sind, die produktionsbereite Hochverfügbarkeits-Verbundauthentifizierung für Microsoft 365 in Azure zu bereitstellen, finden Sie weitere Informationen unter [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md).
  
