---
title: Einfache Standardkonfiguration
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Verwenden Sie diese Test Umgebungs Anleitung zum Erstellen einer einfachen Testumgebung zum Testen von Microsoft 365 für Unternehmen.
ms.openlocfilehash: 2b8505e142c3c1b87578db7342ed299b95d8c049
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487388"
---
# <a name="the-lightweight-base-configuration"></a>Die einfache Standardkonfiguration

*Diese Test Umgebungs Anleitung kann sowohl für Microsoft 365 für Unternehmen als auch für Office 365 Enterprise Testumgebungen verwendet werden.*

In diesem Artikel wird beschrieben, wie eine vereinfachte Umgebung mit einem Microsoft 365 E5-Abonnement und einem Computer mit Windows 10 Enterprise erstellt wird.

![Einfache Microsoft 365 Enterprise-Testumgebung](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

Das Erstellen einer einfachen Testumgebung umfasst fünf Phasen:
- [Phase 1: Erstellen Ihres Microsoft 365 E5-Abonnements](#phase-1-create-your-microsoft-365-e5-subscription)
- [Phase 2: Konfigurieren des Office 365-Testabonnements](#phase-2-configure-your-office-365-trial-subscription)
- [Phase 3: Hinzufügen eines Testabonnements für Microsoft 365 E5](#phase-3-add-a-microsoft-365-e5-trial-subscription)
- [Phase 4: Erstellen eines Computers mit Windows 10 Enterprise](#phase-4-create-a-windows-10-enterprise-computer)
- [Phase 5: Einbinden des Windows 10-Computers in Azure AD](#phase-5-join-your-windows-10-computer-to-azure-ad)

Verwenden Sie die resultierende Umgebung, um die Features und Funktionen von [Microsoft 365 for Enterprise](https://www.microsoft.com/microsoft-365/enterprise)zu testen.

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Eine visuelle Zuordnung zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide-Stack finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).

>[!NOTE]
>Sie können diesen Artikel auch ausdrucken, um die speziellen Informationen zu notieren, die Sie für diese Umgebung in den kommenden 30 Tage des Office 365-Testabonnements benötigen. Sie können das Testabonnement einfach um weitere 30 Tage verlängern. Für eine dauerhafte Testumgebung erstellen Sie ein neues bezahltes Abonnement mit einem separaten Azure AD-Mandanten und einer kleinen Anzahl von Lizenzen.

## <a name="phase-1-create-your-microsoft-365-e5-subscription"></a>Phase 1: Erstellen Ihres Microsoft 365 E5-Abonnements

Wir beginnen mit einem Microsoft 365 E5-Testabonnement und fügen dann das Microsoft 365 E5-Abonnement hinzu.

>[!NOTE]
>Es wird empfohlen, ein Testabonnement für Office 365 zu erstellen, damit Ihre Testumgebung über einen separaten Azure AD Mandanten von beliebigen bezahlten Abonnements verfügt, die Sie derzeit haben. Diese Trennung bedeutet, dass Sie Benutzer und Gruppen im Testmandanten hinzufügen und entfernen können, ohne dass sich dies auf Ihre Produktions Abonnements auswirkt.

Für das Microsoft 365 E5-Testabonnement benötigen Sie zunächst einen fiktiven Unternehmensnamen und ein neues Microsoft-Konto.
  
1. Es wird empfohlen, eine Variante von „Contoso“ als Unternehmensnamen zu verwenden. Dies ist ein fiktives Unternehmen, das von Microsoft in Beispielen verwendet wird. Notieren Sie hier Ihren fiktiven Unternehmensnamen: . ![Zeile](../media/Common-Images/TableLine.png)
    
2. Wenn Sie sich für ein neues Microsoft-Konto registrieren möchten, wechseln Sie zu [https://outlook.com](https://outlook.com), und erstellen Sie ein Konto mit neuem E-Mail-Konto und neuer E-Mail-Adresse. Dieses Konto wird für die Registrierung für Office 365 verwendet.
    
    - Notieren Sie hier den Vor- und Nachnamen des Kontos:  ![Zeile](../media/Common-Images/TableLine.png)
    
    - Notieren Sie hier die neue E-Mail-Kontoadresse: ![Zeile](../media/Common-Images/TableLine.png)@outlook.com
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a>Registrieren für ein Office 365 E5-Testabonnement

1. Wechseln Sie in Ihrem Browser zu [https://aka.ms/e5trial](https://aka.ms/e5trial) .
    
2. Geben Sie in Schritt 1 der Seite **Danke für die Auswahl Office 365 E5** Ihre neue e-Mail-Kontoadresse ein.
3. Geben Sie in Schritt 2 des Trail-Abonnementprozesses die angeforderten Informationen ein, und führen Sie dann die Überprüfung durch.
4. Geben Sie in Schritt 3 einen Organisationsnamen und dann einen Kontonamen ein, der als globaler Administrator für das Abonnement verwendet werden soll.
5. Notieren Sie hier für Schritt 4 die Anmeldeseite (auswählen und kopieren): ![Zeile](../media/Common-Images/TableLine.png)
6. Notieren Sie hier die Benutzer-ID: ![Line](../media/Common-Images/TableLine.png).onmicrosoft.com  
   Notieren Sie sich das Kennwort, das Sie an einem sicheren Ort eingegeben haben.
   Dieser Wert wird **Name des globalen Administrators** genannt.
7. Wählen Sie **Gehe zu Setup**aus.
8. Wählen Sie in Office 365 E5 **-Setup *die Option Organization*. onmicrosoft.com für e-Mail und Anmeldung weiter verwenden**aus, und wählen Sie dann **beenden und später fortfahren**aus.

Das Microsoft 365 Admin Center sollte angezeigt werden.
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a>Phase 2: Konfigurieren des Office 365-Testabonnements

In dieser Phase konfigurieren Sie Ihr Abonnement mit weiteren Benutzern und weisen diesen Office 365 E5-Lizenzen zu.
  
Verwenden Sie die Anweisungen unter [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module), um eine Verbindung zu Ihrem Abonnement mit dem Azure Active Directory PowerShell for Graph-Modul von Ihrem Computer herzustellen.
    
Geben Sie im Dialogfeld **Windows PowerShell Anmeldeinformationen** den globalen Administratornamen ein (beispielsweise *jdoe@contosotoycompany.onmicrosoft.com*) und das Kennwort.
  
Geben Sie den Namen Ihrer Organisation ein (beispielsweise *contosotoycompany*), den zweistelligen Ländercode für Ihren Standort, ein gemeinsames Kontokennwort, und führen Sie dann die folgenden Befehle an der PowerShell-Eingabeaufforderung aus:

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$commonPW="<common user account password>"
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPW

$userUPN= "user2@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 2" -GivenName User -SurName 2 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user2"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user3@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 3" -GivenName User -SurName 3 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user3"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user4@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 4" -GivenName User -SurName 4 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user4"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```
> [!NOTE]
> Für die Automatisierung und Vereinfachung der Konfiguration einer Testumgebung wird hier ein gemeinsames Kennwort verwendet. Natürlich ist davon bei Produktionsabonnements dringend abzuraten. 

### <a name="record-key-information-for-future-reference"></a>Aufzeichnen von Schlüsselinformationen für spätere Verweise

Wenn Sie diese Werte noch nicht aufgezeichnet haben, notieren Sie Sie jetzt:
  
- Globaler Administratorname: ![Zeile](../media/Common-Images/TableLine.png).onmicrosoft.com (aus Schritt 6 von Phase 1)
    
    Notieren Sie auch das Kennwort für dieses Konto, und bewahren Sie es an einem sicheren Ort auf.
    
- Organisationsname für das Testabonnement: ![Zeile](../media/Common-Images/TableLine.png) (aus Schritt 4 von Phase 1)
    
- Führen Sie über die „Windows Azure Active Directory-Modul für Windows PowerShell“-Eingabeaufforderung den folgenden Befehl aus, um die Konten für Benutzer 2, Benutzer 3, Benutzer 4 und Benutzer 5 anzuzeigen:
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    Notieren Sie hier die Kontonamen:
    
  - Benutzer 2 Kontoname: user2@![Zeile](../media/Common-Images/TableLine.png).onmicrosoft.com
    
  - Benutzer 3 Kontoname: user3@![Zeile](../media/Common-Images/TableLine.png).onmicrosoft.com
    
  - Benutzer 4 Kontoname: user4@![Zeile](../media/Common-Images/TableLine.png).onmicrosoft.com
    
  - Benutzer 5 Kontoname: user5@![Zeile](../media/Common-Images/TableLine.png).onmicrosoft.com
    
    Notieren Sie auch das gemeinsame Kennwort für diese Konten, und bewahren Sie es an einem sicheren Ort auf.
   
### <a name="using-an-office-365-test-environment"></a>Verwenden einer Office 365-Testumgebung

Wenn Sie nur eine Office 365 Testumgebung benötigen, müssen Sie den Rest dieses Artikels nicht lesen.

Weitere testumgebungsanleitungen, die sowohl für Office 365 als auch für Microsoft 365 gelten, finden Sie unter [Microsoft 365 for Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a>Phase 3: Hinzufügen eines Testabonnements für Microsoft 365 E5

In dieser Phase registrieren Sie sich für das Microsoft 365 E5-Testabonnement und fügen es derselben Organisation wie Ihr Office 365 E5-Testabonnement hinzu.
  
Fügen Sie zuerst das Testabonnement für Microsoft 365 E5 hinzu, und weisen Sie ihrem globalen Administratorkonto die neue Microsoft 365-Lizenz zu.
  
1. Verwenden Sie in einem privaten Internet Browser-Fenster Ihre Anmeldeinformationen für das globale Administratorkonto, um sich beim Microsoft 365 Admin Center unter anzumelden [https://admin.microsoft.com](https://admin.microsoft.com) .
    
2. Wählen Sie auf der Seite **Microsoft 365 Admin Center** im linken Navigations **Bereich Abrechnungs > Dienste kaufen**aus.
    
3. Wählen Sie auf der Seite " **Dienste kaufen** " **Microsoft 365 E5**aus, und wählen Sie dann **﻿Kostenlose Testversion abrufen**aus.

4. Entscheiden Sie auf der **Microsoft 365 E5-Testseite** , eine Textnachricht oder einen Anruf zu erhalten, geben Sie Ihre Telefonnummer ein, und wählen Sie dann **Text mich** oder **rufen Sie mich**an. Führen Sie eine Überprüfung durch.

5. Wählen Sie auf der Seite **Bestätigung Ihrer Bestellung** die Option **jetzt testen**aus.

6. Wählen Sie auf der Seite **Bestellbestätigung** die Option **Continue**aus.

7. Wählen Sie im Microsoft 365 Admin Center die Option **Benutzer > aktive Benutzer**aus.

8. Wählen Sie unter **aktive Benutzer**Ihr Administratorkonto aus.

9. Wählen Sie **Lizenzen und apps**aus.

10. Deaktivieren Sie die Lizenz für Office 365 Enterprise E5 und aktivieren Sie die Lizenz für Microsoft 365 E5.

11. Wählen Sie **Änderungen speichern**aus, und schließen Sie dann den Bereich Benutzerkontoinformationen.

Wiederholen Sie dann die Schritte 8 bis 11 des vorherigen Verfahrens für alle anderen Konten (Benutzer 2, Benutzer 3, Benutzer 4 und Benutzer 5).
  
> [!NOTE]
> Die Länge des Microsoft 365 E5-Testabonnements beträgt 30 Tage. Ändern Sie für eine dauerhafte Testumgebung dieses Testabonnement in ein kostenpflichtiges Abonnement mit einer kleinen Anzahl von Lizenzen.
  
Ihre Testumgebung verfügt nun über Folgendes:
  
- Ein Testabonnement für Microsoft 365 E5.
- Alle Ihre entsprechenden Benutzerkonten (entweder nur der globale Administrator oder alle fünf Benutzerkonten) können Microsoft 365 E5 verwenden.
    
Die resultierende Konfiguration, die Microsoft 365 E5 hinzufügt, sieht wie folgt aus:
  
![Phase 3 der Microsoft 365 Enterprise-Testumgebung](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a>Phase 4: Erstellen eines Computers mit Windows 10 Enterprise

In dieser Phase erstellen Sie einen eigenständigen Computer unter Windows 10 Enterprise entweder als physischen Computer, als virtuellen Computer oder als virtuellen Azure-Computer.
  
### <a name="physical-computer"></a>Physischer Computer

Installieren Sie auf einem PC Windows 10 Enterprise. Sie können die Windows 10 Enterprise-Testversion [hier](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)herunterladen.
  
### <a name="virtual-machine"></a>Virtueller Computer

Verwenden Sie zum Erstellen eines virtuellen Computers den Hypervisor Ihrer Wahl, und installieren Sie dann Windows 10 Enterprise. Sie können die Windows 10 Enterprise-Testversion [hier](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)herunterladen.
  
### <a name="virtual-machine-in-azure"></a>Virtueller Computer in Azure

Zum Erstellen eines virtuellen Computers mit Windows 10 in Microsoft Azure ***benötigen Sie ein Visual Studio-basiertes Abonnement***, das Zugriff auf das Image für Windows 10 Enterprise hat. Andere Arten von Azure-Abonnements, wie z. B. Testabonnements und kostenpflichtige Abonnements, haben keinen Zugriff auf dieses Image. Die neuesten Informationen finden Sie unter [Verwenden des Windows-Clients in Azure für Entwicklungs-/Testszenarien](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).
  
> [!NOTE]
> [!HINWEIS] In den folgenden Befehlssätzen wird die aktuelle Version von Azure PowerShell verwendet. Informationen dazu finden Sie unter [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). Mit diesen Befehlssätzen werden ein virtueller Windows 10 Enterprise-Computer mit dem Namen „WIN10“ hat sowie die gesamte erforderliche Infrastruktur, einschließlich einer Ressourcengruppe, eines Speicherkontos und eines virtuellen Netzwerks erstellt. Wenn Sie bereits mit Azure-Infrastrukturdiensten vertraut sind, passen Sie diese Anweisungen entsprechend ihrer derzeit bereitgestellten Infrastruktur an.
  
Starten Sie zuerst eine Microsoft PowerShell-Eingabeaufforderung.
  
Melden Sie sich bei Ihrem Azure-Konto mit diesem Befehl an.
  
```powershell
Connect-AzAccount
```

Rufen Sie Ihren Abonnement Namen mit diesem Befehl ab.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Tragen Sie Ihr Azure-Abonnement ein. Ersetzen Sie alles innerhalb der Anführungszeichen, einschließlich der \< and > Zeichen, durch den korrekten Namen.
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

Im nächsten Schritt wird eine neue Ressourcengruppe erstellt. Verwenden Sie zum Ermitteln eines eindeutigen Ressourcengruppennamens diesen Befehl, mit dem die vorhandenen Ressourcengruppen aufgeführt werden.
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Erstellen Sie die neue Ressourcengruppe mit diesen Befehlen. Ersetzen Sie alles innerhalb der Anführungszeichen, einschließlich der \< and > Zeichen, durch die richtigen Namen.
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

Erstellen Sie als nächstes ein neues virtuelles Netzwerk und den virtuellen WIN10-Computer mit diesen Befehlen. Wenn Sie dazu aufgefordert werden, geben Sie den Namen und das Kennwort des lokalen Administratorkontos für WIN10 an, und bewahren Sie dieses an einem sicheren Ort auf.
  
```powershell
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name "M365Ent-TestLab" -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name "M365Ent-TestLab"
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
$pip=New-AzPublicIpAddress -Name WIN10-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name WIN10-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName WIN10 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for WIN10."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName WIN10 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsDesktop -Offer Windows-10 -Skus RS3-Pro -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name WIN10-TestLab-OSDisk -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a>Phase 5: Einbinden des Windows 10-Computers in Azure AD

Nachdem Sie den physischen oder virtuellen Computer mit Windows 10 Enterprise erstellt haben, melden Sie sich mit einem lokalen Administratorkonto an.
  
> [!NOTE]
> Verwenden Sie für einen virtuellen Computer in Azure  [diese Anweisungen](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon) , um eine Verbindung mit diesem herzustellen.
  
Als Nächstes fügen Sie den WIN10-Computer dem Azure AD-Mandanten Ihres Microsoft 365 E5-Abonnements hinzu.
  
1. Wählen Sie auf dem Desktop des WIN10-Computers **> Einstellungen > Konten > Access work oder School > Connect**aus.
    
2. Wählen Sie im Dialogfeld **Arbeits-oder Schulkonto einrichten** die Option **diesem Gerät mit Azure Active Directory beitreten**aus.
    
3. Geben Sie im **Arbeits-oder Schulkonto**den Namen des globalen Administratorkontos Ihres Microsoft 365 E5-Abonnements ein, und wählen Sie dann **weiter**aus.
    
4. Geben Sie unter **Kennwort eingeben**das Kennwort für Ihr globales Administratorkonto ein, und wählen Sie dann **Anmelden**aus.
    
5. Wenn Sie aufgefordert werden, sicherzustellen, dass es sich um Ihre Organisation handelt, wählen Sie **beitreten**aus, und klicken Sie dann auf **Fertig**.
    
6. Schließen Sie das Fenster mit den Einstellungen.
    
Installieren Sie als nächstes Microsoft 365-Apps für Enterprise auf dem WIN10-Computer:
  
1. Öffnen Sie den Microsoft-Edge-Browser, und melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit Ihren Anmeldeinformationen für das globale Administratorkonto an.
    
2. Wählen Sie auf der Registerkarte **Microsoft Office Startseite** die Option **Office installieren**aus.
    
3. Wenn Sie dazu aufgefordert werden, wählen Sie **Ausführen**aus, und wählen Sie dann **Ja** für die **Benutzerkontensteuerung**aus.
    
4. Warten Sie, bis Office die Installation beendet hat. Wenn Sie sehen, dass **Sie alle festgelegt haben**, wählen Sie **Schließen** zweimal aus.
    
Die resultierende Umgebung sieht wie folgt aus:

![Phase 5 der Microsoft 365 Enterprise-Testumgebung](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

Dies schließt den WIN10-Computer mit ein:

- Er wurde dem Azure AD-Mandanten Ihres Microsoft 365 E5-Abonnements hinzugefügt.
- Er wurde als Azure AD-Gerät in Microsoft Intune (EMS) registriert.
- Microsoft 365-Apps für Enterprise installiert.
  
Sie können nun mit weiteren Features von [Microsoft 365 for Enterprise](https://www.microsoft.com/microsoft-365/enterprise)experimentieren.
  
## <a name="next-steps"></a>Nächste Schritte

Sehen Sie sich diese zusätzlichen Testumgebungsanleitungen an:
  
- [Identität](m365-enterprise-test-lab-guides.md#identity)
- [Verwaltung mobiler Geräte](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [Schutz von Daten](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Dokumentation zu Microsoft 365 für Unternehmen](https://docs.microsoft.com/microsoft-365-enterprise/)
