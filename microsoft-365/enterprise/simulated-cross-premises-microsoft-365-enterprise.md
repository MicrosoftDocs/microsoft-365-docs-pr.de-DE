---
title: Simuliertes standortübergreifendes virtuelles Netzwerk in einer Microsoft 365-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
description: 'Zusammenfassung: Erstellen Sie ein simuliertes standortübergreifendes virtuelles Netzwerk in Microsoft Azure als Microsoft 365-Testumgebung.'
ms.openlocfilehash: 7fc3035db5e0b6e924d8b55e81cbee5eca38bfbf
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2019
ms.locfileid: "38640714"
---
# <a name="simulated-cross-premises-virtual-network-in-a-microsoft-365-test-environment"></a><span data-ttu-id="d3522-103">Simuliertes standortübergreifendes virtuelles Netzwerk in einer Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="d3522-103">Simulated cross-premises virtual network in a Microsoft 365 test environment</span></span>

 <span data-ttu-id="d3522-104">**Zusammenfassung:** Erstellen Sie ein simuliertes standortübergreifendes virtuelles Netzwerk in Microsoft Azure als Entwicklungs-/Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="d3522-104">**Summary:** Create a simulated cross-premises virtual network in Microsoft Azure as a dev/test environment.</span></span>
  
<span data-ttu-id="d3522-p101">Dieser Artikel führt Sie schrittweise durch das Erstellen einer simulierten Hybrid-Cloudumgebung mit Microsoft Azure unter Verwendung von zwei virtuellen Azure-Netzwerken. Nachfolgend sehen Sie die daraus resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="d3522-p101">This article steps you through creating a simulated hybrid cloud environment with Microsoft Azure using two Azure virtual networks. Here is the resulting configuration.</span></span> 
  
![Phase 3 des simulierten standortübergreifenden virtuellen Netzwerks in der Entwicklungs-/Testumgebung mit dem virtuellen DC2-Computer im XPrem VNet](media/simulated-cross-premises-microsoft-365-enterprise/df458c56-022b-4688-ab18-056c3fd776b4.png)
  
<span data-ttu-id="d3522-108">Dies simuliert eine Hybrid Cloud-Produktionsumgebung in Azure IaaS und besteht aus Folgendem:</span><span class="sxs-lookup"><span data-stu-id="d3522-108">This simulates an Azure IaaS hybrid cloud production environment and consists of:</span></span>
  
- <span data-ttu-id="d3522-109">Einem simulierten und vereinfachten lokalen Netzwerk, das in einem virtuellen Azure-Netzwerk (dem virtuellen TestLab-Netzwerk) gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="d3522-109">A simulated and simplified on-premises network hosted in an Azure virtual network (the TestLab virtual network).</span></span>
    
- <span data-ttu-id="d3522-110">Einem simuliertem standortübergreifenden virtuellen Netzwerk, das in Azure gehostet wird (XPrem).</span><span class="sxs-lookup"><span data-stu-id="d3522-110">A simulated cross-premises virtual network hosted in Azure (XPrem).</span></span>
    
- <span data-ttu-id="d3522-111">Einer VNet-Peeringbeziehung zwischen den beiden virtuellen Netzwerken.</span><span class="sxs-lookup"><span data-stu-id="d3522-111">A VNet peering relationship between the two virtual networks.</span></span>
    
- <span data-ttu-id="d3522-112">Einem sekundären Domänencontroller im virtuellen XPrem-Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="d3522-112">A secondary domain controller in the XPrem virtual network.</span></span>
    
<span data-ttu-id="d3522-113">Dies liefert eine Grundlage und einen Einstiegspunkt für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d3522-113">This provides a basis and common starting point from which you can:</span></span> 
  
- <span data-ttu-id="d3522-114">Entwickeln und Testen von Anwendungen in einer simulierten Hybrid Cloud-Umgebung in Azure IaaS.</span><span class="sxs-lookup"><span data-stu-id="d3522-114">Develop and test applications in a simulated Azure IaaS hybrid cloud environment.</span></span>
    
- <span data-ttu-id="d3522-115">Erstellen von Testkonfigurationen von Computer, einige innerhalb des virtuellen TestLab-Netzwerks und einige innerhalb des virtuellen XPrem-Netzwerks, um Hybrid Cloud-basierte IT-Arbeitslasten zu simulieren.</span><span class="sxs-lookup"><span data-stu-id="d3522-115">Create test configurations of computers, some within the TestLab virtual network and some within the XPrem virtual network, to simulate hybrid cloud-based IT workloads.</span></span>
    
<span data-ttu-id="d3522-116">Es gibt drei Hauptphasen bei der Einrichtung dieser Entwicklungs-/Testumgebung:</span><span class="sxs-lookup"><span data-stu-id="d3522-116">There are three major phases to setting up this dev/test environment:</span></span>
  
1. <span data-ttu-id="d3522-117">Konfigurieren des virtuellen TestLab-Netzwerks</span><span class="sxs-lookup"><span data-stu-id="d3522-117">Configure the TestLab virtual network.</span></span>
    
2. <span data-ttu-id="d3522-118">Erstellen des standortübergreifenden virtuellen Netzwerks</span><span class="sxs-lookup"><span data-stu-id="d3522-118">Create the cross-premises virtual network.</span></span>
    
3. <span data-ttu-id="d3522-119">Konfigurieren von DC2</span><span class="sxs-lookup"><span data-stu-id="d3522-119">Configure DC2.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d3522-120">Diese Konfiguration erfordert ein kostenpflichtiges Abonnement für Azure.</span><span class="sxs-lookup"><span data-stu-id="d3522-120">This configuration requires a paid Azure subscription.</span></span> 

<span data-ttu-id="d3522-121">Sie können die resultierende Umgebung verwenden, um die Features und Funktionen von [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) zu testen, mit zusätzlichen [Testumgebungsanleitungen](m365-enterprise-test-lab-guides.md) oder selbst.</span><span class="sxs-lookup"><span data-stu-id="d3522-121">You can use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) with additional [Test Lab Guides](m365-enterprise-test-lab-guides.md) or on your own.</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="d3522-123">Klicken Sie [hier](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d3522-123">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-configure-the-testlab-virtual-network"></a><span data-ttu-id="d3522-124">Phase 1: Konfigurieren des virtuellen TestLab-Netzwerks</span><span class="sxs-lookup"><span data-stu-id="d3522-124">Phase 1: Configure the TestLab virtual network</span></span>

<span data-ttu-id="d3522-125">Verwenden Sie die Anweisungen in **Phase 1** der [simulierten Unternehmensstandardkonfiguration](simulated-ent-base-configuration-microsoft-365-enterprise.md), um die Computer DC1, APP1 und CLIENT1 im virtuellen Azure-Netzwerk mit dem Namen "TestLab" zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d3522-125">Use the instructions in **Phase 1** of the [simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) to configure the DC1, APP1, and CLIENT1 computers in the Azure virtual network named TestLab.</span></span>
  
<span data-ttu-id="d3522-126">Dies ist Ihre aktuelle Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="d3522-126">This is your current configuration.</span></span> 
  
![Die simulierte Unternehmensstandardkonfiguration in Azure](media/simulated-cross-premises-microsoft-365-enterprise/25a010a6-c870-4690-b8f3-84421f8bc5c7.png)
  
## <a name="phase-2-create-the-xprem-virtual-network"></a><span data-ttu-id="d3522-128">Phase 2: Erstellen des virtuellen XPrem-Netzwerks</span><span class="sxs-lookup"><span data-stu-id="d3522-128">Phase 2: Create the XPrem virtual network</span></span>

<span data-ttu-id="d3522-129">In dieser Phase erstellen und konfigurieren Sie das neue virtuelle XPrem-Netzwerk und verbinden es dann über VNet-Peering mit dem virtuellen TestLab-Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="d3522-129">In this phase, you create and configure the new XPrem virtual network and then connect it to the TestLab virtual network with VNet peering.</span></span>
  
<span data-ttu-id="d3522-130">Starten Sie zunächst eine Azure PowerShell-Eingabeaufforderung auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="d3522-130">First, start an Azure PowerShell prompt on your local computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d3522-p102">In den folgenden Befehlssätzen wird die aktuelle Version von Azure PowerShell verwendet. Informationen dazu finden Sie unter [Erste Schritte mit Azure PowerShell-Cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span><span class="sxs-lookup"><span data-stu-id="d3522-p102">The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> 
  
<span data-ttu-id="d3522-133">Melden Sie sich bei Ihrem Azure-Konto mit diesem Befehl an.</span><span class="sxs-lookup"><span data-stu-id="d3522-133">Sign in to your Azure account with this command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="d3522-134">Rufen Sie den Namen Ihres Abonnements mithilfe des folgenden Befehls ab.</span><span class="sxs-lookup"><span data-stu-id="d3522-134">Get your subscription name using this command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="d3522-p103">Tragen Sie Ihr Azure-Abonnement ein. Ersetzen Sie alles innerhalb der Anführungszeichen, einschließlich der Zeichen „\<“ und „>“, durch den entsprechenden Namen.</span><span class="sxs-lookup"><span data-stu-id="d3522-p103">Set your Azure subscription. Replace everything within the quotes, including the \< and > characters, with the correct names.</span></span>
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

<span data-ttu-id="d3522-137">Erstellen Sie als Nächstes das virtuelle XPrem-Netzwerk, und schützen Sie es mithilfe dieser Befehle mit einer Netzwerksicherheitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="d3522-137">Next, create the XPrem virtual network and protect it with a network security group with these commands.</span></span>
  
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

<span data-ttu-id="d3522-138">Anschließend erstellen Sie mit diesen Befehlen die VNet-Peeringbeziehung zwischen dem virtuellen TestLab- und XPrem-Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="d3522-138">Next, you create the VNet peering relationship between the TestLab and XPrem VNets with these commands.</span></span>
  
```powershell
$rgName="<name of the resource group that you used for your TestLab virtual network>"
$vnet1=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name TestLab
$vnet2=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name XPrem
Add-AzVirtualNetworkPeering -Name TestLab2XPrem -VirtualNetwork $vnet1 -RemoteVirtualNetworkId $vnet2.Id
Add-AzVirtualNetworkPeering -Name XPrem2TestLab -VirtualNetwork $vnet2 -RemoteVirtualNetworkId $vnet1.Id
```

<span data-ttu-id="d3522-139">Dies ist Ihre aktuelle Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="d3522-139">This is your current configuration.</span></span> 
  
![Phase 2 des simulierten standortübergreifenden virtuellen Netzwerks in der Entwicklungs-/Testumgebung mit der XPrem VNet- und der VNet-Peeringbeziehung.](media/simulated-cross-premises-microsoft-365-enterprise/cac5e999-69c7-4f4c-bfce-a7f4006115ef.png)
  
## <a name="phase-3-configure-dc2"></a><span data-ttu-id="d3522-141">Phase 3: Konfigurieren von DC2</span><span class="sxs-lookup"><span data-stu-id="d3522-141">Phase 3: Configure DC2</span></span>

<span data-ttu-id="d3522-142">In dieser Phase erstellen Sie den virtuellen Computer DC2 im virtuellen XPrem-Netzwerk und konfigurieren ihn dann als Replikatdomänencontroller.</span><span class="sxs-lookup"><span data-stu-id="d3522-142">In this phase, you create the DC2 virtual machine in the XPrem virtual network and then configure it as a replica domain controller.</span></span>
  
<span data-ttu-id="d3522-p104">Erstellen Sie zunächst einen virtuellen Computer für DC2. Führen Sie diese Befehle an der Azure PowerShell-Eingabeaufforderung auf dem lokalen Computer aus.</span><span class="sxs-lookup"><span data-stu-id="d3522-p104">First, create a virtual machine for DC2. Run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<your resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name XPrem -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name DC2-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name DC2-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress 192.168.0.4
$vm=New-AzVMConfig -VMName DC2 -VMSize Standard_A1
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

<span data-ttu-id="d3522-145">Stellen Sie dann über das [Azure-Portal](https://portal.azure.com) unter Verwendung des lokalen Administratorkontonamens und Kennworts eine Verbindung zu dem neuen virtuellen Compter DC2 her. </span><span class="sxs-lookup"><span data-stu-id="d3522-145">Next, connect to the new DC2 virtual machine from the [Azure portal](https://portal.azure.com) using its local administrator account name and password.</span></span>
  
<span data-ttu-id="d3522-p105">Konfigurieren Sie als Nächstes eine Window-Firewallregel, um Verkehr für grundlegende Konnektivitätstests zuzulassen. Führen Sie diese Befehle an einer Windows PowerShell-Eingabeaufforderung auf Administratorebene für DC2 aus.</span><span class="sxs-lookup"><span data-stu-id="d3522-p105">Next, configure a Windows Firewall rule to allow traffic for basic connectivity testing. From an administrator-level Windows PowerShell command prompt on DC2, run these commands.</span></span> 
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
ping dc1.corp.contoso.com
```

<span data-ttu-id="d3522-p106">Der Ping-Befehl sollte zu vier erfolgreichen Antworten von IP-Adresse 10.0.0.4 führen. Dies ist ein Test für Datenverkehr über die VNet-Peeringbeziehung.</span><span class="sxs-lookup"><span data-stu-id="d3522-p106">The ping command should result in four successful replies from IP address 10.0.0.4. This is a test of traffic across the VNet peering relationship.</span></span> 
  
<span data-ttu-id="d3522-150">Im nächsten Schritt führen Sie diesen Befehl über die Windows PowerShell-Eingabeaufforderung auf DC2 aus, um das zusätzliche Datenlaufwerk als neues Volume mit dem Laufwerkbuchstaben „F:“ hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d3522-150">Next, add the extra data disk as a new volume with the drive letter F: with this command from the Windows PowerShell command prompt on DC2.</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="d3522-p107">Konfigurieren Sie als Nächstes DC2 als Replikatdomänencontroller für die Domäne „corp.contoso.com“. Führen Sie diese Befehle an der Windows PowerShell-Eingabeaufforderung auf Administratorebene für DC2 aus.</span><span class="sxs-lookup"><span data-stu-id="d3522-p107">Next, configure DC2 as a replica domain controller for the corp.contoso.com domain. Run these commands from the Windows PowerShell command prompt on DC2.</span></span>
  
```powershell
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -Credential (Get-Credential CORP\User1) -DomainName "corp.contoso.com" -InstallDns:$true -DatabasePath "F:\NTDS" -LogPath "F:\Logs" -SysvolPath "F:\SYSVOL"
```

<span data-ttu-id="d3522-153">Beachten Sie, dass Sie aufgefordert werden, sowohl das Kennwort für CORP\\CORPUser1 als auch ein DSRM-Kennwort (Directory Services Restore Mode) anzugeben und DC2 neu zu starten. </span><span class="sxs-lookup"><span data-stu-id="d3522-153">Note that you are prompted to supply both the CORP\\User1 password and a Directory Services Restore Mode (DSRM) password, and to restart DC2.</span></span> 
  
<span data-ttu-id="d3522-p108">Da das virtuelle XPrem-Netzwerk nun über seinen eigenen DNS-Server (DC2) verfügt, müssen Sie das virtuelle XPrem-Netzwerk so konfigurieren, dass dieser DNS-Server verwendet wird. Führen Sie diese Befehle an der Azure PowerShell-Eingabeaufforderung auf dem lokalen Computer aus.</span><span class="sxs-lookup"><span data-stu-id="d3522-p108">Now that the XPrem virtual network has its own DNS server (DC2), you must configure the XPrem virtual network to use this DNS server. Run these commands from the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -name "XPrem"
$vnet.DhcpOptions.DnsServers="192.168.0.4" 
Set-AzVirtualNetwork -VirtualNetwork $vnet
Restart-AzVM -ResourceGroupName $rgName -Name "DC2"
```

<span data-ttu-id="d3522-p109">Stellen Sie über das Azure-Portal auf dem lokalen Computer eine Verbindung mit DC1 mit den Anmeldeinformationen für CORP\\CORPUser1 her. Um die Domäne CORP so zu konfigurieren, dass Computer und Benutzer ihre lokalen Domänencontroller für die Authentifizierung verwenden, führen Sie diese Befehle an einer Windows PowerShell-Befehlszeile auf Administratorebene für DC1 aus.</span><span class="sxs-lookup"><span data-stu-id="d3522-p109">From the Azure portal on your local computer, connect to DC1 with the CORP\\User1 credentials. To configure the CORP domain so that computers and users use their local domain controller for authentication, run these commands from an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
New-ADReplicationSite -Name "TestLab" 
New-ADReplicationSite -Name "XPrem"
New-ADReplicationSubnet -Name "10.0.0.0/8" -Site "TestLab"
New-ADReplicationSubnet -Name "192.168.0.0/16" -Site "XPrem"
```

<span data-ttu-id="d3522-158">Dies ist Ihre aktuelle Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="d3522-158">This is your current configuration.</span></span> 
  
![Phase 3 des simulierten standortübergreifenden virtuellen Netzwerks in der Entwicklungs-/Testumgebung mit dem virtuellen DC2-Computer im XPrem VNet](media/simulated-cross-premises-microsoft-365-enterprise/df458c56-022b-4688-ab18-056c3fd776b4.png)
  
<span data-ttu-id="d3522-160">Ihre simulierte Hybrid Cloud-Umgebung für Azure kann nun getestet werden.</span><span class="sxs-lookup"><span data-stu-id="d3522-160">Your simulated Azure hybrid cloud environment is now ready for testing.</span></span>
  
<span data-ttu-id="d3522-161">Sie können nun die zusätzlichen Funktionen von [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) ausprobieren.</span><span class="sxs-lookup"><span data-stu-id="d3522-161">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="d3522-162">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="d3522-162">Next steps</span></span>

<span data-ttu-id="d3522-163">Sehen Sie sich diese zusätzlichen Testumgebungsanleitungen an:</span><span class="sxs-lookup"><span data-stu-id="d3522-163">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="d3522-164">Identität</span><span class="sxs-lookup"><span data-stu-id="d3522-164">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="d3522-165">Verwaltung mobiler Geräte</span><span class="sxs-lookup"><span data-stu-id="d3522-165">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="d3522-166">Schutz von Daten</span><span class="sxs-lookup"><span data-stu-id="d3522-166">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a><span data-ttu-id="d3522-167">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3522-167">See also</span></span>

[<span data-ttu-id="d3522-168">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d3522-168">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="d3522-169">Bereitstellen von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d3522-169">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="d3522-170">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d3522-170">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
