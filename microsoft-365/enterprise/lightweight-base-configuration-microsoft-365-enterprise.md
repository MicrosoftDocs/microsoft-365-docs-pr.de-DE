---
title: Einfache Standardkonfiguration
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/18/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Verwenden Sie diese Tetstumgebungsanleitung zum Erstellen einer einfachen Testumgebung für das Testen von Microsoft 365 Enterprise.
ms.openlocfilehash: e162f1dbdb79b17c5ba6fa4fd88f4b2be3c53863
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868131"
---
# <a name="the-lightweight-base-configuration"></a>Die einfache Standardkonfiguration

In diesem Artikel erhalten Sie schrittweise Anweisungen zum Erstellen einer vereinfachten Umgebung, die Office 365 E5, Enterprise Mobility + Security (EMS) E5 und einen Computer mit Windows 10 Enterprise umfasst. 

![Die Microsoft 365 Enterprise-Testumgebung (Lightweight)](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

Verwenden die resultierende Umgebung zum Testen der Features und Funktionen von [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).

![Testumgebungsanleitungen für die Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.

## <a name="phase-1-create-your-office-365-e5-subscription"></a>Phase 1: Erstellen des Office 365 E5-Abonnements

Folgen Sie den Schritten für Phase 2 und 3 unter [Office 365-Entwicklungs-/Testumgebung](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment), um eine einfache Entwicklungs-/Testumgebung für Office 365 zu erstellen, wie in Abbildung 1 gezeigt.
  
**Abbildung 1: Ihr Office 365 E5-Abonnement mit dem Azure Active Directory (AD)-Mandanten und Benutzerkonten**

![Phase 1 der Microsoft 365 Enterprise-Testumgebung](media/lightweight-base-configuration-microsoft-365-enterprise/Phase1.png)

> [!NOTE]
> Das Testabonnement für Office 365 E5 ist 30 Tage gültig und kann problemlos auf 60 Tage verlängert werden. Erstellen Sie für eine dauerhafte Testumgebung ein neues kostenpflichtiges Abonnement mit einer kleinen Anzahl von Lizenzen. 
  
## <a name="phase-2-add-ems"></a>Phase 2: Hinzufügen von EMS

In dieser Phase registrieren Sie sich für das EMS E5-Testabonnement und fügen es derselben Organisation wie Ihr Office 365 E5-Testabonnement hinzu.
  
Fügen Sie zunächst das Testabonnement für EMS E5 hinzu, und weisen Sie ihrem globalen Administratorkonto eine EMS-Lizenz zu.
  
1. Melden Sie sich mit einer privaten Instanz eines Internetbrowsers beim Office 365-Portal an, indem Sie die Anmeldeinformationen für Ihr globales Administratorkonto verwenden. Hilfe dazu finden Sie unter [Wo kann ich mich bei Office 365 anmelden?](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. Klicken Sie auf die Kachel **Admin**.
    
3. Klicken Sie auf der Registerkarte **Office Admin Center** in Ihrem Browser im linken Navigationsbereich auf **Abrechnung > Dienste kaufen**.
    
4. Suchen Sie auf der Seite **Dienste kaufen** den Artikel **Enterprise Mobility + Security E5**. Platzieren Sie den Mauszeiger auf dem Artikelnamen, und klicken Sie auf **Start free trial**.
    
5. Klicken Sie auf der Seite für die **Bestätigung Ihrer Bestellung** auf **Jetzt versuchen**.
    
6. Klicken Sie auf der Seite **Bestellbestätigung** auf **Weiter**.
    
7. Klicken Sie auf der Registerkarte **Office 365 Admin Center** in Ihrem Browser im linken Navigationsbereich auf **Benutzer > Aktive Benutzer**.
    
8. Klicken Sie auf Ihr globales Administratorkonto und dann auf **Bearbeiten**, um die **Produktlizenzen** anzuzeigen.
    
9. Setzen Sie im Bereich **Product licenses** die Produktlizenz für **Enterprise Mobility + Security E5** auf **On**. Klicken Sie auf **Speichern** und dann auf **Schließen**.
    
> [!NOTE]
> Das Testabonnement für Enterprise Mobility + Security E5 ist 90 Tage gültig. Für eine dauerhafteTestumgebung erstellen Sie ein neues bezahltes Abonnement mit einer kleinen Anzahl von Lizenzen. 
  
 ***Wenn Sie die Schritte in Phase 3 des Artikels*** [Office 365-Entwicklungs-/Testumgebung](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment) abgeschlossen haben, wiederholen Sie die Schritte 8 und 9 des vorherigen Verfahrens für alle anderen Konten (Benutzer 2, Benutzer 3, Benutzer 4 und Benutzer 5).
  
Ihre Testumgebung verfügt nun über Folgendes:
  
- Office 365 E5 Enterprise- und EMS E5-Testabonnements mit demselben Azure AD-Mandanten mit Ihrer Liste von Benutzerkonten.
- Alle entsprechenden Benutzerkonten (entweder nur der globale Administrator oder alle fünf Benutzerkonten) können Office 365 E5 und EMS E5 verwenden.
    
Abbildung 2 zeigt die Konfiguration nach dem Hinzufügen von EMS.
  
**Abbildung 2: Hinzufügen des EMS-Testabonnements**

![Phase 2 der Microsoft 365 Enterprise-Testumgebung](media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-3-create-a-windows-10-enterprise-computer"></a>Phase 3: Erstellen eines Computers mit Windows 10 Enterprise

In dieser Phase erstellen Sie einen eigenständigen Computer unter Windows 10 Enterprise entweder als physischen Computer, als virtuellen Computer oder als virtuellen Azure-Computer.
  
### <a name="physical-computer"></a>Physischer Computer

Installieren Sie Windows 10 Enterprise auf einem PC. Sie können die Testversion von Windows 10 Enterprise [hier](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise) herunterladen.
  
### <a name="virtual-machine"></a>Virtueller Computer

Erstellen Sie mit dem Hypervisor Ihrer Wahl einen virtuellen Computer, und installieren Sie Windows 10 Enterprise darauf. Sie können die Testversion von Windows 10 Enterprise [hier](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise) herunterladen.
  
### <a name="virtual-machine-in-azure"></a>Virtueller Computer in Azure

Zum Erstellen eines virtuellen Computers mit Windows 10 in Microsoft Azure ***benötigen Sie ein Visual Studio-basiertes Abonnement***, das Zugriff auf das Image für Windows 10 Enterprise hat. Andere Arten von Azure-Abonnements, wie z. B. Testabonnements und kostenpflichtige Abonnements, haben keinen Zugriff auf dieses Image. Die neuesten Informationen finden Sie unter [Verwenden des Windows-Clients in Azure für Entwicklungs-/Testszenarien](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).
  
> [!NOTE]
> Die folgenden Befehlssätze verwenden die aktuelle Version von Azure PowerShell. Informationen dazu finden Sie unter [Erste Schritte mit Azure PowerShell-Cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). Mit diesen Befehlssätzen werden ein virtueller Windows 10 Enterprise-Computer mit dem Namen „WIN10“ sowie die gesamte erforderliche Infrastruktur, einschließlich einer Ressourcengruppe, eines Speicherkontos und eines virtuellen Netzwerks erstellt. Wenn Sie bereits mit den Azure-Infrastrukturdiensten vertraut sind, passen Sie diese Anweisungen entsprechend Ihrer aktuell bereitgestellten Infrastruktur an. 
  
Starten Sie zuerst eine Microsoft PowerShell-Eingabeaufforderung.
  
Melden Sie sich mit dem folgenden Befehl bei Ihrem Azure-Konto an.
  
```
Login-AzureRMAccount
```

Rufen Sie den Namen Ihres Abonnements mithilfe des folgenden Befehls ab.
  
```
Get-AzureRMSubscription | Sort Name | Select Name
```

Tragen Sie Ihr Azure-Abonnement ein. Ersetzen Sie alles innerhalb der Anführungszeichen, einschließlich der Zeichen „\<“ und „>“, durch den entsprechenden Namen.
  
```
$subscr="<subscription name>"
Get-AzureRmSubscription -SubscriptionName $subscr | Select-AzureRmSubscription
```

Im nächsten Schritt wird eine neue Ressourcengruppe erstellt. Verwenden Sie zum Ermitteln eines eindeutigen Ressourcengruppennamens diesen Befehl, mit dem die vorhandenen Ressourcengruppen aufgeführt werden.
  
```
Get-AzureRMResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

Erstellen Sie die neue Ressourcengruppe mit diesen Befehlen. Ersetzen Sie alles innerhalb der Anführungszeichen, einschließlich der Zeichen „\<“ und „>“, durch die entsprechenden Namen.
  
```
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzureRMResourceGroup -Name $rgName -Location $locName
```

Im nächsten Schritt erstellen Sie ein neues virtuelles Netzwerk und den virtuellen WIN10-Computer mit den folgenden Befehlen. Wenn Sie dazu aufgefordert werden, geben Sie den Namen und das Kennwort des lokalen Administratorkontos für WIN10 an, und bewahren Sie dieses an einem sicheren Ort auf.
  
```
$corpnetSubnet=New-AzureRMVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzureRMVirtualNetwork -Name "M365Ent-TestLab" -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet
$rule1=New-AzureRMNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzureRMNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzureRMVirtualNetwork -ResourceGroupName $rgName -Name "M365Ent-TestLab"
$nsg=Get-AzureRMNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzureRMVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$pip=New-AzureRMPublicIpAddress -Name WIN10-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzureRMNetworkInterface -Name WIN10-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzureRMVMConfig -VMName WIN10 -VMSize Standard_D1_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for WIN10."
$vm=Set-AzureRMVMOperatingSystem -VM $vm -Windows -ComputerName WIN10 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzureRMVMSourceImage -VM $vm -PublisherName MicrosoftWindowsDesktop -Offer Windows-10 -Skus RS3-Pro -Version "latest"
$vm=Add-AzureRMVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzureRmVMOSDisk -VM $vm -Name WIN10-TestLab-OSDisk -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzureRMVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

## <a name="phase-4-join-your-windows-10-computer-to-azure-ad"></a>Phase 4: Einbinden des Windows 10-Computers in Azure AD

Nachdem Sie den physischen oder virtuellen Computer mit Windows 10 Enterprise erstellt haben, melden Sie sich mit einem lokalen Administratorkonto an.
  
> [!NOTE]
> Für einen virtuellen Computer in Azure verbinden Sie diesen mithilfe der [folgenden Anweisungen](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).
  
Als Nächstes fügen Sie den WIN10-Computer dem Azure AD-Mandanten Ihrer Office 365- und EMS-Abonnements hinzu.
  
1. Klicken Sie auf dem Desktop des WIN10-Computers auf **Start > Einstellungen > Konten > Auf Arbeits- oder Schulkonto zugreifen > Verbinden**.
    
2. Klicken Sie im Dialogfeld **Geschäfts-, Schul- oder Unikonto einrichten** auf **Dieses Gerät in Azure Active Directory einbinden**.
    
3. Geben Sie unter **Geschäfts-, Schul- oder Unikonto** den Namen des globalen Administratorkontos Ihres Office 365-Abonnements ein, und klicken Sie dann auf **Weiter**.
    
4. Geben Sie unter **Kennwort eingeben** das Kennwort für das globale Administratorkonto ein, und klicken Sie dann auf **Anmelden**.
    
5. Wenn Sie dazu aufgefordert werden, sicherzustellen, dass es sich hierbei um Ihre Organisation handelt, klicken Sie auf **Teilnehmen**, und klicken Sie dann auf **Fertig**.
    
6. Schließen Sie das Fenster mit den Einstellungen.
    
Installieren Sie im nächsten Schritt Office 365 ProPlus auf dem WIN10-Computer.
  
1. Öffnen Sie den Microsoft Edge-Browser, und melden Sie sich mit den Anmeldeinformationen Ihres globalen Administratorkontos beim Office 365-Portal an. Hilfe dazu finden Sie unter [Wo kann ich mich bei Office 365 anmelden?](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. Klicken Sie auf der Registerkarte der **Microsoft Office-Startseite** auf **Office 2016 installieren**.
    
3. Wenn Sie dazu aufgefordert werden, klicken Sie auf **Ausführen**, und klicken Sie dann auf **Ja** für **Benutzerkontensteuerung**.
    
4. Warten Sie, bis Office die Installation beendet hat. Wenn **Alles bereit** angezeigt wird, klicken Sie zweimal auf **Schließen**.
    
Abbildung 3 zeigt die resultierende Umgebung, die den WIN10-Computer enthält, für den Folgendes gilt:

- Er wurde dem Azure AD-Mandanten Ihrer Office 365- und EMS-Abonnements hinzugefügt.
- Er wurde als Azure AD-Gerät in Intune (EMS) registriert.
- Auf ihm ist Office 365 ProPlus installiert.
  
**Abbildung 3: Die endgültige Konfiguration der Microsoft 365-Testumgebung**


![Phase 4 der Microsoft 365 Enterprise-Testumgebung](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
  
Sie können nun die zusätzlichen Funktionen von [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) ausprobieren.
  
## <a name="next-steps"></a>Nächste Schritte

Sehen Sie sich diese zusätzlichen Testumgebungsanleitungen an:
  
- [Identität](m365-enterprise-test-lab-guides.md#identity)
- [Verwaltung mobiler Geräte](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [Schutz von Daten](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Bereitstellen von Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Dokumentation zu Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
