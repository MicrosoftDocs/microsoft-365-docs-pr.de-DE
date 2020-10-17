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

*Diese Test Umgebungs Anleitung kann sowohl für Microsoft 365 für Unternehmen als auch für Office 365 Enterprise Testumgebungen verwendet werden.*

Microsoft 365 unterstützt Verbundidentität. Dies bedeutet, dass Microsoft 365, anstatt die Prüfung von Anmeldeinformationen selbst durchzuführen, den Benutzer, der eine Verbindung herstellt, auf einen Verbundauthentifizierungsserver verweist, der für Microsoft 365 vertrauenswürdig ist. Wenn die Anmeldeinformationen des Benutzers korrekt sind, gibt der Verbundauthentifizierungsserver ein Sicherheitstoken aus, das der Client als Nachweis der Authentifizierung an Microsoft 365 sendet. Verbundidentität ermöglicht das Abladen und zentrale Skalieren der Authentifizierung für ein Microsoft 365-Abonnement sowie erweiterte Authentifizierungs- und Sicherheitsszenarien.
  
In diesem Artikel wird beschrieben, wie Sie die Verbundauthentifizierung für Ihre Microsoft 365-Testumgebung konfigurieren, was Folgendes ergibt:

![Die Verbundauthentifizierung für die Microsoft 365-Testumgebung](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
Diese Konfiguration besteht aus:
  
- Ein Microsoft 365 E5-Test-oder Produktions Abonnement.
    
- Ein vereinfachtes Organisationsintranet, das mit dem Internet verbunden ist und das aus fünf virtuellen Computern in einem Subnetz eines virtuellen Azure-Netzwerks besteht (DC1, App1, CLIENT1, ADFS1 und PROXY1). Azure AD Connect wird auf App1 ausgeführt, um die Liste der Konten in der Active Directory-Domänendienste Domäne mit Microsoft 365 zu synchronisieren. PROXY1 erhält die eingehenden Authentifizierungsanfragen. ADFS1 überprüft Anmeldeinformationen mit DC1 und gibt Sicherheitstoken aus.
    
Das Einrichten dieser Testumgebung umfasst fünf Phasen:
- [Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Phase 2: Erstellen des AD FS-Servers](#phase-2-create-the-ad-fs-server)
- [Phase 3: Erstellen des Webproxyservers](#phase-3-create-the-web-proxy-server)
- [Phase 4: Erstellen eines selbstsignierten Zertifikats und Konfigurieren von ADFS1 und PROXY1](#phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1)
- [Phase 5: Konfigurieren von Microsoft 365 für Verbundidentität](#phase-5-configure-microsoft-365-for-federated-identity)
    
> [!NOTE]
> Sie können diese Testumgebung nicht mit einem Azure-Testabonnement konfigurieren.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung

Befolgen Sie die Anweisungen unter [Kennworthash Synchronisierung für Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Die resultierende Konfiguration sieht wie folgt aus:
  
![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase1.png)
  
Diese Konfiguration besteht aus: 
  
- Eine Microsoft 365 E5-Testversion oder kostenpflichtige Abonnements.
- Ein vereinfachtes Organisationsintranet, das mit dem Internet verbunden ist, das aus den virtuellen Computern DC1, App1 und CLIENT1 in einem Subnetz eines virtuellen Azure-Netzwerks besteht. Azure AD Connect wird auf App1 ausgeführt, um die TESTLAB Active Directory-Domänendienste (AD DS) Domäne regelmäßig mit dem Azure AD Mandanten Ihrer Microsoft 365-Abonnements zu synchronisieren.

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

Die resultierende Konfiguration sieht wie folgt aus:
  
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
  
Fügen Sie als nächstes eine Regel zur Netzwerksicherheitsgruppe für das Corpnet-Subnetz hinzu, um unerwünschten eingehenden Datenverkehr aus dem Internet an PROXY1's private IP-Adresse und TCP-Port 443 zu ermöglichen. Führen Sie diese Befehle an der Azure PowerShell-Eingabeaufforderung auf dem lokalen Computer aus.
  
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

Zeigen Sie die öffentliche IP-Adresse von PROXY1 mit diesen Azure PowerShell-Befehlen auf dem lokalen Computer an.
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "PROXY1-PIP" -ResourceGroup $rgName).IPAddress
```

Im nächsten Schritt arbeiten Sie mit Ihrem öffentlichen DNS-Anbieter und erstellen einen neuen öffentlichen DNS A-Eintrag für **fs.testlab.**\<*your DNS domain name*>, der in die IP-Adresse aufgelöst wird, die vom Befehl **Write-Host** angezeigt wird. Auf **fs.testlab.**\<*your DNS domain name*> wird nachfolgend als *FQDN des Verbunddiensts verwiesen*.
  
Im nächsten Schritt stellen Sie über das [Azure-Portal](https://portal.azure.com) eine Verbindung mit dem virtuellen Computer DC1 unter Verwendung der Anmeldeinformationen „CORP\\User1“ her und führen dann die folgenden Befehle an einer Windows PowerShell-Eingabeaufforderung auf Administratorebene aus:
  
```powershell
Add-DnsServerPrimaryZone -Name corp.contoso.com -ZoneFile corp.contoso.com.dns
Add-DnsServerResourceRecordA -Name "fs" -ZoneName corp.contoso.com -AllowUpdateAny -IPv4Address "10.0.0.100" -TimeToLive 01:00:00
```
Mit diesen Befehlen wird ein interner DNS-A-Eintrag erstellt, sodass virtuelle Computer im virtuellen Azure-Netzwerk den internen Verbunddienst-FQDN in ADFS1's private IP-Adresse auflösen können.
  
Die resultierende Konfiguration sieht wie folgt aus:
  
![Der Webanwendungs-Proxyserver, der der DirSync für die Microsoft 365-Testumgebung hinzugefügt wurde](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
## <a name="phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1"></a>Phase 4: Erstellen eines selbstsignierten Zertifikats und Konfigurieren von ADFS1 und PROXY1

In dieser Phase erstellen Sie ein selbstsigniertes digitales Zertifikat für den FQDN des Verbunddiensts und konfigurieren ADFS1 und PROXY1 als AD FS-Farm.
  
Im nächsten Schritt stellen Sie über das [Azure-Portal](https://portal.azure.com) eine Verbindung mit dem virtuellen Computer DC1 unter Verwendung der Anmeldeinformationen „CORP\\User1“ her und öffnen dann eine Windows PowerShell-Eingabeaufforderung auf Administratorebene.
  
Erstellen Sie als nächstes ein AD FS-Dienstkonto mit diesem Befehl an der Windows PowerShell Eingabeaufforderung auf DC1:
  
```powershell
New-ADUser -SamAccountName ADFS-Service -AccountPassword (read-host "Set user password" -assecurestring) -name "ADFS-Service" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```
Beachten Sie, dass Sie von dem Befehl aufgefordert werden, das Kontokennwort anzugeben. Verwenden Sie ein sicheres Kennwort, und notieren Sie es an einem sicheren Ort. Sie benötigen Sie für diese Phase und für Phase 5.
  
Verwenden Sie das [Azure-Portal](https://portal.azure.com), um eine Verbindung zu dem virtuellen Computer ADFS1 unter Verwendung der Anmeldeinformationen „CORP\\User1“ herzustellen. Öffnen Sie eine Windows PowerShell-Eingabeaufforderung auf Administratorebene auf ADFS1, geben Sie den FQDN des Verbunddiensts ein, und führen Sie dann die folgenden Befehle aus, um ein selbstsigniertes Zertifikat zu erstellen:
  
```powershell
$fedServiceFQDN="<federation service FQDN>"
New-SelfSignedCertificate -DnsName $fedServiceFQDN -CertStoreLocation "cert:\LocalMachine\My"
New-Item -path c:\Certs -type directory
New-SmbShare -name Certs -path c:\Certs -changeaccess CORP\User1
```

Gehen Sie dann folgendermaßen vor, um das neue selbstsignierte Zertifikat als Datei zu speichern.
  
1. Klicken Sie auf **Start**, geben Sie **mmc.exe**ein, und drücken Sie dann die **Eingabe**Taste.
    
2. Wählen **File**Sie  >  **Snap-in "Datei hinzufügen/entfernen**" aus.
    
3. Doppelklicken Sie in **Snap-Ins hinzufügen oder entfernen**in der Liste der verfügbaren Snap-Ins auf **Zertifikate** , wählen Sie **Computer Konto**aus, und wählen Sie dann **weiter**aus.
    
4. Wählen Sie unter **Computer auswählen**die Option **Fertig stellen**aus, und wählen Sie dann **OK**aus.
    
5. Öffnen Sie im Strukturbereich **Zertifikate (Lokaler Computer) > Persönlich > Zertifikate**.
    
6. Wählen Sie das Zertifikat mit dem FQDN des Verbunddiensts aus, halten Sie es gedrückt (oder klicken Sie mit der rechten Maustaste), wählen Sie **alle Aufgaben**aus, und wählen Sie dann **exportieren**aus.
    
7. Klicken Sie auf der **Willkommens** Seite auf **weiter**.
    
8. Wählen Sie auf der Seite **privaten Schlüssel exportieren** die Option **Ja**aus, und wählen Sie dann **weiter**aus.
    
9. Wählen Sie auf der Seite **Datei Format exportieren** die Option **alle erweiterten Eigenschaften exportieren**aus, und wählen Sie dann **weiter**aus.
    
10. Wählen Sie auf der Seite **Sicherheit** die Option **Kennwort** aus, und geben Sie ein Kennwort in **Kennwort** und **Kennwort bestätigen ein.**
    
11. Wählen Sie auf der Seite **zu exportierende Datei** die Option **Durchsuchen**aus.
    
12. Wechseln Sie zum **Ordner C \\ : certs** , geben Sie **SSL** unter **Dateiname**ein, und wählen Sie dann **Speichern aus.**
    
13. Wählen Sie auf der Seite **zu exportierende Datei** die Option **weiter**aus.
    
14. Wählen Sie auf der Seite fertig stellen **des Zertifikat Exports den Assistenten** **Fertig stellen**aus. Wenn Sie dazu aufgefordert werden, wählen Sie **OK**aus.
    
Im nächsten Schritt erstellen Sie den AD FS-Dienst mit dem folgenden Befehl an der Windows PowerShell-Eingabeaufforderung auf ADFS1:
  
```powershell
Install-WindowsFeature ADFS-Federation -IncludeManagementTools
```

Warten Sie, bis die Installation abgeschlossen ist.
  
Konfigurieren Sie als Nächstes den AD FS-Dienst mit den folgenden Schritten:
  
1. Wählen Sie **Start**aus, und wählen Sie dann das Symbol **Server-Manager** aus.
    
2. Wählen Sie im Strukturbereich des Server-Managers **AD FS**aus.
    
3. Wählen Sie oben in der Symbolleiste das orangefarbene Warnsymbol aus, und wählen Sie dann **den Verbunddienst auf diesem Server konfigurieren**aus.
    
4. Wählen Sie auf der **Willkommens** Seite des Assistenten zum Konfigurieren von Active Directory Verbunddienste die Option **weiter**aus.
    
5. Wählen Sie auf der Seite mit **AD DS verbinden** die Option **weiter**aus.
    
6. Auf der Seite **Diensteigenschaften angeben**:
    
  - Wählen Sie für **SSL-Zertifikat**den Pfeil nach unten aus, und wählen Sie dann das Zertifikat mit dem Namen des FQDN des Verbunddiensts aus.
    
  - Geben Sie unter **Anzeigename des Verbunddiensts**den Namen ihrer fiktiven Organisation ein.
    
  - Wählen Sie **Weiter** aus.
    
7. Wählen Sie auf der Seite **Dienstkonto angeben** die Option für **Kontonamen** **auswählen** aus.
    
8. Geben Sie unter **Benutzer oder Dienstkonto auswählen**den Namen **ADFS-Service**ein, wählen Sie **Namen überprüfen**aus, und wählen Sie dann **OK**aus.
    
9. Geben Sie unter **Kontokennwort**das Kennwort für das ADFS-Service Konto ein, und wählen Sie dann **weiter**aus.
    
10. Wählen Sie auf der Seite **Konfigurationsdatenbank angeben** die Option **weiter**aus.
    
11. Wählen Sie auf der Seite **Überprüfungsoptionen** die Option **weiter**aus.
    
12. Wählen Sie auf der Seite **Voraussetzungen überprüfen** die Option **configure**aus.

13. Klicken Sie auf der Seite **Ergebnisse** auf **Schließen**.
    
14. Wählen Sie **Start**, wählen Sie das Symbol Power aus, wählen Sie **neu starten**aus, und wählen Sie dann **weiter**aus.
    
Melden Sie sich über das [Azure-Portal](https://portal.azure.com) mit dem CORP\\User1-Konto bei PROXY1 an.
  
Gehen Sie dann folgendermaßen vor, um das selbstsignierte Zertifikat auf ** PROXY1 und APP1** zu installieren.
  
1. Klicken Sie auf **Start**, geben Sie **mmc.exe**ein, und drücken Sie dann die **Eingabe**Taste.
    
2. Wählen Sie **Datei > Snap-in hinzufügen/entfernen**aus.
    
3. Doppelklicken Sie in **Snap-Ins hinzufügen oder entfernen**in der Liste der verfügbaren Snap-Ins auf **Zertifikate** , wählen Sie **Computer Konto**aus, und wählen Sie dann **weiter**aus.
    
4. Wählen Sie unter **Computer auswählen**die Option **Fertig stellen**aus, und wählen Sie dann **OK**aus.
    
5. Öffnen Sie im Strukturbereich **Zertifikate (lokaler Computer)**  >  **persönliche**  >  **Zertifikate**.
    
6. Wählen Sie aus, und halten Sie (oder klicken Sie mit der rechten Maustaste auf) **persönlich**, wählen Sie **alle Aufgaben**aus, und wählen Sie dann **importieren**aus.
    
7. Klicken Sie auf der **Willkommens** Seite auf **weiter**.
    
8. Geben Sie auf der Seite **zu importierende Datei** ** \\ \\ adfs1 \\ certs \\ SSL. pfx**ein, und wählen Sie dann **weiter**aus.
    
9. Geben Sie auf der Seite **privater Schlüsselschutz** das Zertifikat Kennwort in **Kennwort ein**, und wählen Sie dann **weiter aus.**
    
10. Wählen Sie auf der Seite **Zertifikatspeicher** die Option **weiter aus.**
    
11. Klicken Sie auf **der Seite fertig** Stellung auf **Fertig stellen**.
    
12. Wählen Sie auf der Seite **Zertifikatspeicher** die Option **weiter**aus.
    
13. Wenn Sie dazu aufgefordert werden, wählen Sie **OK**aus.
    
14. Wählen Sie im Strukturbereich **Zertifikate**aus.
    
15. Wählen Sie das Zertifikat aus, halten Sie es gedrückt (oder klicken Sie mit der rechten Maustaste darauf), und wählen Sie dann **Kopieren**aus.
    
16. Öffnen Sie im Strukturbereich **Vertrauenswürdige Stammzertifizierungsstellen**  >  **Zertifikate**.
    
17. Bewegen Sie den Mauszeiger unter die Liste der installierten Zertifikate, wählen Sie und halten Sie (oder klicken Sie mit der rechten Maustaste), und wählen Sie dann **Einfügen**aus.
    
Öffnen Sie eine PowerShell-Eingabeaufforderung auf Administratorebene, und führen Sie den folgenden Befehl aus:
  
```powershell
Install-WindowsFeature Web-Application-Proxy -IncludeManagementTools
```

Warten Sie, bis die Installation abgeschlossen ist.
  
Verwenden Sie die folgenden Schritte, um den Webanwendungs-Proxydienst so zu konfigurieren, dass ADFS1 als Verbundserver verwendet wird:
  
1. Wählen Sie **Start**aus, und wählen Sie dann **Server-Manager**aus.
    
2. Wählen Sie im Strukturbereich **Remote Zugriff**aus.
    
3. Wählen Sie oben in der Symbolleiste das orangefarbene Warnsymbol aus, und wählen Sie dann **den Assistenten zum Öffnen des Webanwendungs-Proxys**aus.
    
4. Wählen Sie auf der **Willkommens** Seite des Assistenten für die Webanwendungs Proxy Konfiguration die Option **weiter**aus.
    
5. Auf der Seite **Verbundserver**:
    
  - Geben Sie im Feld **verbunddienstname** den FQDN des Verbunddiensts ein.
    
  - Geben Sie in das Feld **Benutzername den Namen** **Corp \\ User1**ein.
    
  - Geben Sie im Feld **Kennwort** das Kennwort für das user1-Konto ein.
    
  - Wählen Sie **Weiter** aus.
    
6. Wählen Sie auf der Seite **AD FS-Proxy Zertifikat** den Pfeil nach unten aus, wählen Sie das Zertifikat mit dem FQDN des Verbunddiensts aus, und wählen Sie dann **weiter**aus.
    
7. Wählen Sie auf der Seite **Bestätigung** die Option **configure**aus.
    
8. Klicken Sie auf der Seite **Ergebnisse** auf **Schließen**.
    
## <a name="phase-5-configure-microsoft-365-for-federated-identity"></a>Phase 5: Konfigurieren von Microsoft 365 für Verbundidentität

Verwenden Sie das [Azure-Portal](https://portal.azure.com), um eine Verbindung zu dem virtuellen Computer APP1 unter Verwendung der Kontoanmeldeinformationen „CORP\\User1“ herzustellen.
  
Verwenden Sie diese Schritte, um Azure AD Connect und Ihr Microsoft 365-Abonnement für die Verbundauthentifizierung zu konfigurieren:
  
1. Doppelklicken Sie auf dem Desktop auf **Azure AD Connect**.
    
2. Wählen Sie auf der Seite **Willkommen bei Azure AD Connect** die Option **configure**aus.
    
3. Wählen Sie auf der Seite **Weitere Aufgaben** die Option **Benutzeranmeldung ändern**aus, und wählen Sie dann **weiter**aus.
    
4. Geben Sie auf der Seite mit **Azure AD verbinden** den Namen des globalen Administratorkontos und das Kennwort ein, und wählen Sie dann **weiter**aus.
    
5. Wählen Sie auf der Seite **Benutzeranmeldung** die Option Partner **Verbund mit AD FS**aus, und wählen Sie dann **weiter**aus.
    
6. Wählen Sie auf der Seite **AD FS-Farm** die Option **vorhandene AD FS-Farm verwenden**aus, geben Sie **ADFS1** in das Feld **Server Name** ein, und wählen Sie dann **weiter**aus.
    
7. Wenn Sie zur Eingabe von Serveranmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen des \\ Kontos Corp user1 ein, und wählen Sie dann **OK**aus.
    
8. Geben Sie auf der Seite Anmeldeinformationen für den **Domänen Administrator** in das Feld **Benutzername den Namen** **Corp \\ User1** ein, geben Sie das Kontokennwort in das Feld **Kennwort** ein, und klicken Sie dann auf **weiter**.
    
9. Geben Sie auf der Seite **AD FS-Dienstkonto** im Feld **Domänenname den Namen** **Corp \\ ADFS-Service** ein, geben Sie das Kontokennwort in das Feld **Domänenbenutzer Kennwort** ein, und wählen Sie dann **weiter**aus.
    
10. Wählen Sie auf der Seite **Azure AD Domäne** unter **Domäne**den Namen der Domäne aus, die Sie zuvor erstellt und Ihrem Abonnement in Phase 1 hinzugefügt haben, und wählen Sie dann **weiter**aus.
    
11. Wählen Sie auf der Seite " **vorbereiten zur Konfiguration** " die Option **configure**aus.
    
12. Wählen Sie auf der Seite **Installation abgeschlossen** die Option **Verify**aus.
    
    Es sollten Meldungen angezeigt werden, die darauf hindeuten, dass sowohl die Intranet-als auch die Internetkonfiguration überprüft wurden.
    
13. Klicken Sie auf der Seite **Installation abgeschlossen** auf **Beenden**.
    
Gehen Sie folgendermaßen vor, um zu zeigen, dass die Verbundauthentifizierung funktioniert:
  
1. Öffnen Sie eine neue private Instanz Ihres Browsers auf Ihrem lokalen Computer, und wechseln Sie zu [https://admin.microsoft.com](https://admin.microsoft.com).
    
2. Geben Sie für die Anmeldeinformationen user1@ ein **user1@** \<*the domain created in Phase 1*> .
    
    Wenn Ihre Testdomäne beispielsweise **testlab.contoso.com**lautet, geben Sie "user1@testlab.contoso.com" ein. Drücken Sie die **Tab** -Taste, oder lassen Sie Microsoft 365 automatisch umleiten.
    
    Jetzt sollten Sie die Seite **Die Verbindung ist nicht privat** sehen. Sie sehen dies, weil Sie ein selbstsigniertes Zertifikat auf ADFS1 installiert haben, das Ihr Desktopcomputer nicht validieren kann. In einer Produktionsbereitstellung der Verbundauthentifizierung würden Sie ein Zertifikat von einer vertrauenswürdigen Zertifizierungsstelle verwenden, und Ihre Benutzer würden diese Seite nicht sehen.
    
3. Wählen Sie auf der Seite **Ihre Verbindung ist nicht privat** die Option **erweitert**aus, und wählen Sie dann **weiter zu \<*your federation service FQDN*> **aus. 
    
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

Wenn Sie bereit sind, produktionsfähige Verbundauthentifizierung für hohe Verfügbarkeit für Microsoft 365 in Azure bereitzustellen, lesen Sie [Bereitstellen der Verbundauthentifizierung mit hoher Verfügbarkeit für Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md).
  
