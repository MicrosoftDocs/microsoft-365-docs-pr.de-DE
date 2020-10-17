---
title: Simuliertes standortübergreifendes virtuelles Netzwerk in einer Microsoft 365-Testumgebung
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
search.appverid:
- MET150
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: seo-marvel-apr2020
description: 'Zusammenfassung: Erstellen Sie ein simuliertes standortübergreifendes virtuelles Netzwerk in Microsoft Azure als Microsoft 365-Testumgebung.'
ms.openlocfilehash: ce8b1963e97decc58820bff7b563bb835a843772
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487648"
---
# <a name="simulated-cross-premises-virtual-network-in-a-microsoft-365-test-environment"></a>Simuliertes standortübergreifendes virtuelles Netzwerk in einer Microsoft 365-Testumgebung

*Diese Test Umgebungs Anleitung kann sowohl für Microsoft 365 für Unternehmen als auch für Office 365 Enterprise Testumgebungen verwendet werden.*

Dieser Artikel führt Sie schrittweise durch das Erstellen einer simulierten Hybrid-Cloudumgebung mit Microsoft Azure unter Verwendung von zwei virtuellen Azure-Netzwerken. Nachfolgend sehen Sie die daraus resultierende Konfiguration. 
  
![Phase 3 des simulierten standortübergreifenden virtuellen Netzwerks in der Testumgebung mit dem virtuellen DC2-Computer im XPrem VNet](../media/simulated-cross-premises-microsoft-365-enterprise/df458c56-022b-4688-ab18-056c3fd776b4.png)
  
Dies simuliert eine Hybrid Cloud-Produktionsumgebung in Azure IaaS und besteht aus Folgendem:
  
- Einem simulierten und vereinfachten lokalen Netzwerk, das in einem virtuellen Azure-Netzwerk (dem virtuellen TestLab-Netzwerk) gehostet wird.
    
- Einem simuliertem standortübergreifenden virtuellen Netzwerk, das in Azure gehostet wird (XPrem).
    
- Einer VNet-Peeringbeziehung zwischen den beiden virtuellen Netzwerken.
    
- Einem sekundären Domänencontroller im virtuellen XPrem-Netzwerk.
    
Dies liefert eine Grundlage und einen Einstiegspunkt für Folgendes: 
  
- Entwickeln und Testen von Anwendungen in einer simulierten Hybrid Cloud-Umgebung in Azure IaaS.
    
- Erstellen von Testkonfigurationen von Computer, einige innerhalb des virtuellen TestLab-Netzwerks und einige innerhalb des virtuellen XPrem-Netzwerks, um Hybrid Cloud-basierte IT-Arbeitslasten zu simulieren.
    
Es gibt drei Hauptphasen bei der Einrichtung dieser Testumgebung:
  
1. Konfigurieren des virtuellen TestLab-Netzwerks
    
2. Erstellen des standortübergreifenden virtuellen Netzwerks
    
3. Konfigurieren von DC2
    
> [!NOTE]
> Diese Konfiguration erfordert ein kostenpflichtiges Abonnement für Azure. 

Sie können die resultierende Umgebung verwenden, um die Features und Funktionen von [Microsoft 365 for Enterprise](https://www.microsoft.com/microsoft-365/enterprise) mit zusätzlichen [testumgebungsanleitungen](m365-enterprise-test-lab-guides.md) oder eigenständig zu testen.

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Wechseln Sie zu [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf) für eine visuelle Zuordnung zu allen Artikeln im Stapel Microsoft 365 for Enterprise Test Lab Guide.

## <a name="phase-1-configure-the-testlab-virtual-network"></a>Phase 1: Konfigurieren des virtuellen TestLab-Netzwerks

Verwenden Sie die Anweisungen in **Phase 1** der [simulierten Unternehmensstandardkonfiguration](simulated-ent-base-configuration-microsoft-365-enterprise.md), um die Computer DC1, APP1 und CLIENT1 im virtuellen Azure-Netzwerk mit dem Namen "TestLab" zu konfigurieren.
  
Dies ist Ihre aktuelle Konfiguration. 
  
![Die simulierte Unternehmensstandardkonfiguration in Azure](../media/simulated-cross-premises-microsoft-365-enterprise/25a010a6-c870-4690-b8f3-84421f8bc5c7.png)
  
## <a name="phase-2-create-the-xprem-virtual-network"></a>Phase 2: Erstellen des virtuellen XPrem-Netzwerks

In dieser Phase erstellen und konfigurieren Sie das neue virtuelle XPrem-Netzwerk und verbinden es dann über VNet-Peering mit dem virtuellen TestLab-Netzwerk.
  
Starten Sie zunächst eine Azure PowerShell-Eingabeaufforderung auf dem lokalen Computer.
  
> [!NOTE]
> In den folgenden Befehlssätzen wird die aktuelle Version von Azure PowerShell verwendet. Informationen dazu finden Sie unter [Erste Schritte mit Azure PowerShell-Cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). 
  
Melden Sie sich bei Ihrem Azure-Konto mit diesem Befehl an.
  
```powershell
Connect-AzAccount
```

Rufen Sie den Namen Ihres Abonnements mithilfe des folgenden Befehls ab.
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

Tragen Sie Ihr Azure-Abonnement ein. Ersetzen Sie alles innerhalb der Anführungszeichen, einschließlich der Zeichen „\< and >“ durch den entsprechenden Namen.
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

Erstellen Sie als Nächstes das virtuelle XPrem-Netzwerk, und schützen Sie es mithilfe dieser Befehle mit einer Netzwerksicherheitsgruppe.
  
```powershell
$rgName="<name of the resource group that you used for your TestLab virtual network>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$Testnet=New-AzVirtualNetworkSubnetConfig -Name "Testnet" -AddressPrefix 192.168.0.0/24
New-AzVirtualNetwork -Name "XPrem" -ResourceGroupName $rgName -Location $locName -AddressPrefix 192.168.0.0/16 -Subnet $Testnet -DNSServer 10.0.0.4
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name "Testnet" -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name XPrem
$nsg=Get-AzNetworkSecurityGroup -Name "Testnet" -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name "Testnet" -AddressPrefix 192.168.0.0/24 -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

Anschließend erstellen Sie mit diesen Befehlen die VNet-Peeringbeziehung zwischen dem virtuellen TestLab- und XPrem-Netzwerk.
  
```powershell
$rgName="<name of the resource group that you used for your TestLab virtual network>"
$vnet1=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name TestLab
$vnet2=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name XPrem
Add-AzVirtualNetworkPeering -Name TestLab2XPrem -VirtualNetwork $vnet1 -RemoteVirtualNetworkId $vnet2.Id
Add-AzVirtualNetworkPeering -Name XPrem2TestLab -VirtualNetwork $vnet2 -RemoteVirtualNetworkId $vnet1.Id
```

Dies ist Ihre aktuelle Konfiguration. 
  
![Phase 2 des simulierten standortübergreifenden virtuellen Netzwerks in der Testumgebung mit der XPrem VNet- und der VNet-Peeringbeziehung.](../media/simulated-cross-premises-microsoft-365-enterprise/cac5e999-69c7-4f4c-bfce-a7f4006115ef.png)
  
## <a name="phase-3-configure-dc2"></a>Phase 3: Konfigurieren von DC2

In dieser Phase erstellen Sie den virtuellen Computer DC2 im virtuellen XPrem-Netzwerk und konfigurieren ihn dann als Replikatdomänencontroller.
  
Erstellen Sie zunächst einen virtuellen Computer für DC2. Führen Sie diese Befehle an der Azure PowerShell-Eingabeaufforderung auf dem lokalen Computer aus.
  
```powershell
$rgName="<your resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name XPrem -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name DC2-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name DC2-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress 192.168.0.4
$vm=New-AzVMConfig -VMName DC2 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for DC2."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName DC2 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "DC2-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
$diskConfig=New-AzDiskConfig -AccountType "Standard_LRS" -Location $locName -CreateOption Empty -DiskSizeGB 20
$dataDisk1=New-AzDisk -DiskName "DC2-DataDisk1" -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name "DC2-DataDisk1" -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

Stellen Sie dann über das [Azure-Portal](https://portal.azure.com) unter Verwendung des lokalen Administratorkontonamens und Kennworts eine Verbindung zu dem neuen virtuellen Compter DC2 her. 
  
Konfigurieren Sie als Nächstes eine Window-Firewallregel, um Verkehr für grundlegende Konnektivitätstests zuzulassen. Führen Sie diese Befehle an einer Windows PowerShell-Eingabeaufforderung auf Administratorebene für DC2 aus. 
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
ping dc1.corp.contoso.com
```

Der Ping-Befehl sollte zu vier erfolgreichen Antworten von IP-Adresse 10.0.0.4 führen. Dies ist ein Test für Datenverkehr über die VNet-Peeringbeziehung. 
  
Im nächsten Schritt führen Sie diesen Befehl über die Windows PowerShell-Eingabeaufforderung auf DC2 aus, um das zusätzliche Datenlaufwerk als neues Volume mit dem Laufwerkbuchstaben „F:“ hinzuzufügen.
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

Konfigurieren Sie als Nächstes DC2 als Replikatdomänencontroller für die Domäne „corp.contoso.com“. Führen Sie diese Befehle an der Windows PowerShell-Eingabeaufforderung auf Administratorebene für DC2 aus.
  
```powershell
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -Credential (Get-Credential CORP\User1) -DomainName "corp.contoso.com" -InstallDns:$true -DatabasePath "F:\NTDS" -LogPath "F:\Logs" -SysvolPath "F:\SYSVOL"
```

Beachten Sie, dass Sie aufgefordert werden, sowohl das Kennwort für CORP\\CORPUser1 als auch ein DSRM-Kennwort (Directory Services Restore Mode) anzugeben und DC2 neu zu starten.  
  
Da das virtuelle XPrem-Netzwerk nun über seinen eigenen DNS-Server (DC2) verfügt, müssen Sie das virtuelle XPrem-Netzwerk so konfigurieren, dass dieser DNS-Server verwendet wird. Führen Sie diese Befehle an der Azure PowerShell-Eingabeaufforderung auf dem lokalen Computer aus.
  
```powershell
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -name "XPrem"
$vnet.DhcpOptions.DnsServers="192.168.0.4" 
Set-AzVirtualNetwork -VirtualNetwork $vnet
Restart-AzVM -ResourceGroupName $rgName -Name "DC2"
```

Stellen Sie über das Azure-Portal auf dem lokalen Computer eine Verbindung mit DC1 mit den Anmeldeinformationen für CORP\\CORPUser1 her. Um die Domäne CORP so zu konfigurieren, dass Computer und Benutzer ihre lokalen Domänencontroller für die Authentifizierung verwenden, führen Sie diese Befehle an einer Windows PowerShell-Befehlszeile auf Administratorebene für DC1 aus.
  
```powershell
New-ADReplicationSite -Name "TestLab" 
New-ADReplicationSite -Name "XPrem"
New-ADReplicationSubnet -Name "10.0.0.0/8" -Site "TestLab"
New-ADReplicationSubnet -Name "192.168.0.0/16" -Site "XPrem"
```

Dies ist Ihre aktuelle Konfiguration. 
  
![Phase 3 des simulierten standortübergreifenden virtuellen Netzwerks in der Testumgebung mit dem virtuellen DC2-Computer im XPrem VNet](../media/simulated-cross-premises-microsoft-365-enterprise/df458c56-022b-4688-ab18-056c3fd776b4.png)
  
Ihre simulierte Hybrid Cloud-Umgebung für Azure kann nun getestet werden.
  
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
