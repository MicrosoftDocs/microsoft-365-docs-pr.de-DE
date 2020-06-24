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
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: seo-marvel-apr2020
description: 'Zusammenfassung: Erstellen Sie ein simuliertes standortübergreifendes virtuelles Netzwerk in Microsoft Azure als Microsoft 365-Testumgebung.'
ms.openlocfilehash: 6a9eb7377ff7ce3aa5b251d345e57ae2a25ba926
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817071"
---
# <a name="simulated-cross-premises-virtual-network-in-a-microsoft-365-test-environment"></a><span data-ttu-id="03718-103">Simuliertes standortübergreifendes virtuelles Netzwerk in einer Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="03718-103">Simulated cross-premises virtual network in a Microsoft 365 test environment</span></span>

<span data-ttu-id="03718-104">*Diese Testumgebungsanleitung kann für Microsoft 365 Enterprise- und Office 365 Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="03718-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="03718-105">This article steps you through creating a simulated hybrid cloud environment with Microsoft Azure using two Azure virtual networks.</span><span class="sxs-lookup"><span data-stu-id="03718-105">This article steps you through creating a simulated hybrid cloud environment with Microsoft Azure using two Azure virtual networks.</span></span> <span data-ttu-id="03718-106">Here is the resulting configuration.</span><span class="sxs-lookup"><span data-stu-id="03718-106">Here is the resulting configuration.</span></span> 
  
![Phase 3 des simulierten standortübergreifenden virtuellen Netzwerks in der Testumgebung mit dem virtuellen DC2-Computer im XPrem VNet](../media/simulated-cross-premises-microsoft-365-enterprise/df458c56-022b-4688-ab18-056c3fd776b4.png)
  
<span data-ttu-id="03718-108">Dies simuliert eine Hybrid Cloud-Produktionsumgebung in Azure IaaS und besteht aus Folgendem:</span><span class="sxs-lookup"><span data-stu-id="03718-108">This simulates an Azure IaaS hybrid cloud production environment and consists of:</span></span>
  
- <span data-ttu-id="03718-109">Einem simulierten und vereinfachten lokalen Netzwerk, das in einem virtuellen Azure-Netzwerk (dem virtuellen TestLab-Netzwerk) gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="03718-109">A simulated and simplified on-premises network hosted in an Azure virtual network (the TestLab virtual network).</span></span>
    
- <span data-ttu-id="03718-110">Einem simuliertem standortübergreifenden virtuellen Netzwerk, das in Azure gehostet wird (XPrem).</span><span class="sxs-lookup"><span data-stu-id="03718-110">A simulated cross-premises virtual network hosted in Azure (XPrem).</span></span>
    
- <span data-ttu-id="03718-111">Einer VNet-Peeringbeziehung zwischen den beiden virtuellen Netzwerken.</span><span class="sxs-lookup"><span data-stu-id="03718-111">A VNet peering relationship between the two virtual networks.</span></span>
    
- <span data-ttu-id="03718-112">Einem sekundären Domänencontroller im virtuellen XPrem-Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="03718-112">A secondary domain controller in the XPrem virtual network.</span></span>
    
<span data-ttu-id="03718-113">Dies liefert eine Grundlage und einen Einstiegspunkt für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="03718-113">This provides a basis and common starting point from which you can:</span></span> 
  
- <span data-ttu-id="03718-114">Entwickeln und Testen von Anwendungen in einer simulierten Hybrid Cloud-Umgebung in Azure IaaS.</span><span class="sxs-lookup"><span data-stu-id="03718-114">Develop and test applications in a simulated Azure IaaS hybrid cloud environment.</span></span>
    
- <span data-ttu-id="03718-115">Erstellen von Testkonfigurationen von Computer, einige innerhalb des virtuellen TestLab-Netzwerks und einige innerhalb des virtuellen XPrem-Netzwerks, um Hybrid Cloud-basierte IT-Arbeitslasten zu simulieren.</span><span class="sxs-lookup"><span data-stu-id="03718-115">Create test configurations of computers, some within the TestLab virtual network and some within the XPrem virtual network, to simulate hybrid cloud-based IT workloads.</span></span>
    
<span data-ttu-id="03718-116">Es gibt drei Hauptphasen bei der Einrichtung dieser Testumgebung:</span><span class="sxs-lookup"><span data-stu-id="03718-116">There are three major phases to setting up this test environment:</span></span>
  
1. <span data-ttu-id="03718-117">Konfigurieren des virtuellen TestLab-Netzwerks</span><span class="sxs-lookup"><span data-stu-id="03718-117">Configure the TestLab virtual network.</span></span>
    
2. <span data-ttu-id="03718-118">Erstellen des standortübergreifenden virtuellen Netzwerks</span><span class="sxs-lookup"><span data-stu-id="03718-118">Create the cross-premises virtual network.</span></span>
    
3. <span data-ttu-id="03718-119">Konfigurieren von DC2</span><span class="sxs-lookup"><span data-stu-id="03718-119">Configure DC2.</span></span>
    
> [!NOTE]
> <span data-ttu-id="03718-120">Diese Konfiguration erfordert ein kostenpflichtiges Abonnement für Azure.</span><span class="sxs-lookup"><span data-stu-id="03718-120">This configuration requires a paid Azure subscription.</span></span> 

<span data-ttu-id="03718-121">Sie können die resultierende Umgebung verwenden, um die Features und Funktionen von [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) zu testen, mit zusätzlichen [Testumgebungsanleitungen](m365-enterprise-test-lab-guides.md) oder selbst.</span><span class="sxs-lookup"><span data-stu-id="03718-121">You can use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) with additional [Test Lab Guides](m365-enterprise-test-lab-guides.md) or on your own.</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="03718-123">Wechseln Sie zu [Microsoft 365 Enterprise Test Lab Ratgeberstapel](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="03718-123">Go to [Microsoft 365 Enterprise Test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-configure-the-testlab-virtual-network"></a><span data-ttu-id="03718-124">Phase 1: Konfigurieren des virtuellen TestLab-Netzwerks</span><span class="sxs-lookup"><span data-stu-id="03718-124">Phase 1: Configure the TestLab virtual network</span></span>

<span data-ttu-id="03718-125">Verwenden Sie die Anweisungen in **Phase 1** der [simulierten Unternehmensstandardkonfiguration](simulated-ent-base-configuration-microsoft-365-enterprise.md), um die Computer DC1, APP1 und CLIENT1 im virtuellen Azure-Netzwerk mit dem Namen "TestLab" zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="03718-125">Use the instructions in **Phase 1** of the [simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) to configure the DC1, APP1, and CLIENT1 computers in the Azure virtual network named TestLab.</span></span>
  
<span data-ttu-id="03718-126">Dies ist Ihre aktuelle Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="03718-126">This is your current configuration.</span></span> 
  
![Die simulierte Unternehmensstandardkonfiguration in Azure](../media/simulated-cross-premises-microsoft-365-enterprise/25a010a6-c870-4690-b8f3-84421f8bc5c7.png)
  
## <a name="phase-2-create-the-xprem-virtual-network"></a><span data-ttu-id="03718-128">Phase 2: Erstellen des virtuellen XPrem-Netzwerks</span><span class="sxs-lookup"><span data-stu-id="03718-128">Phase 2: Create the XPrem virtual network</span></span>

<span data-ttu-id="03718-129">In dieser Phase erstellen und konfigurieren Sie das neue virtuelle XPrem-Netzwerk und verbinden es dann über VNet-Peering mit dem virtuellen TestLab-Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="03718-129">In this phase, you create and configure the new XPrem virtual network and then connect it to the TestLab virtual network with VNet peering.</span></span>
  
<span data-ttu-id="03718-130">Starten Sie zunächst eine Azure PowerShell-Eingabeaufforderung auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="03718-130">First, start an Azure PowerShell prompt on your local computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="03718-131">The following command sets use the latest version of Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="03718-131">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="03718-132">See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span><span class="sxs-lookup"><span data-stu-id="03718-132">See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> 
  
<span data-ttu-id="03718-133">Melden Sie sich bei Ihrem Azure-Konto mit diesem Befehl an.</span><span class="sxs-lookup"><span data-stu-id="03718-133">Sign in to your Azure account with this command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="03718-134">Rufen Sie den Namen Ihres Abonnements mithilfe des folgenden Befehls ab.</span><span class="sxs-lookup"><span data-stu-id="03718-134">Get your subscription name using this command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="03718-135">Set your Azure subscription.</span><span class="sxs-lookup"><span data-stu-id="03718-135">Set your Azure subscription.</span></span> <span data-ttu-id="03718-136">Replace everything within the quotes, including the \< and > characters, with the correct names.</span><span class="sxs-lookup"><span data-stu-id="03718-136">Replace everything within the quotes, including the \< and > characters, with the correct names.</span></span>
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

<span data-ttu-id="03718-137">Erstellen Sie als Nächstes das virtuelle XPrem-Netzwerk, und schützen Sie es mithilfe dieser Befehle mit einer Netzwerksicherheitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="03718-137">Next, create the XPrem virtual network and protect it with a network security group with these commands.</span></span>
  
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

<span data-ttu-id="03718-138">Anschließend erstellen Sie mit diesen Befehlen die VNet-Peeringbeziehung zwischen dem virtuellen TestLab- und XPrem-Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="03718-138">Next, you create the VNet peering relationship between the TestLab and XPrem VNets with these commands.</span></span>
  
```powershell
$rgName="<name of the resource group that you used for your TestLab virtual network>"
$vnet1=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name TestLab
$vnet2=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name XPrem
Add-AzVirtualNetworkPeering -Name TestLab2XPrem -VirtualNetwork $vnet1 -RemoteVirtualNetworkId $vnet2.Id
Add-AzVirtualNetworkPeering -Name XPrem2TestLab -VirtualNetwork $vnet2 -RemoteVirtualNetworkId $vnet1.Id
```

<span data-ttu-id="03718-139">Dies ist Ihre aktuelle Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="03718-139">This is your current configuration.</span></span> 
  
![Phase 2 des simulierten standortübergreifenden virtuellen Netzwerks in der Testumgebung mit der XPrem VNet- und der VNet-Peeringbeziehung.](../media/simulated-cross-premises-microsoft-365-enterprise/cac5e999-69c7-4f4c-bfce-a7f4006115ef.png)
  
## <a name="phase-3-configure-dc2"></a><span data-ttu-id="03718-141">Phase 3: Konfigurieren von DC2</span><span class="sxs-lookup"><span data-stu-id="03718-141">Phase 3: Configure DC2</span></span>

<span data-ttu-id="03718-142">In dieser Phase erstellen Sie den virtuellen Computer DC2 im virtuellen XPrem-Netzwerk und konfigurieren ihn dann als Replikatdomänencontroller.</span><span class="sxs-lookup"><span data-stu-id="03718-142">In this phase, you create the DC2 virtual machine in the XPrem virtual network and then configure it as a replica domain controller.</span></span>
  
<span data-ttu-id="03718-143">First, create a virtual machine for DC2.</span><span class="sxs-lookup"><span data-stu-id="03718-143">First, create a virtual machine for DC2.</span></span> <span data-ttu-id="03718-144">Run these commands at the Azure PowerShell command prompt on your local computer.</span><span class="sxs-lookup"><span data-stu-id="03718-144">Run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
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

<span data-ttu-id="03718-145">Stellen Sie dann über das [Azure-Portal](https://portal.azure.com) unter Verwendung des lokalen Administratorkontonamens und Kennworts eine Verbindung zu dem neuen virtuellen Compter DC2 her. </span><span class="sxs-lookup"><span data-stu-id="03718-145">Next, connect to the new DC2 virtual machine from the [Azure portal](https://portal.azure.com) using its local administrator account name and password.</span></span>
  
<span data-ttu-id="03718-146">Next, configure a Windows Firewall rule to allow traffic for basic connectivity testing.</span><span class="sxs-lookup"><span data-stu-id="03718-146">Next, configure a Windows Firewall rule to allow traffic for basic connectivity testing.</span></span> <span data-ttu-id="03718-147">From an administrator-level Windows PowerShell command prompt on DC2, run these commands.</span><span class="sxs-lookup"><span data-stu-id="03718-147">From an administrator-level Windows PowerShell command prompt on DC2, run these commands.</span></span> 
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
ping dc1.corp.contoso.com
```

<span data-ttu-id="03718-148">The ping command should result in four successful replies from IP address 10.0.0.4.</span><span class="sxs-lookup"><span data-stu-id="03718-148">The ping command should result in four successful replies from IP address 10.0.0.4.</span></span> <span data-ttu-id="03718-149">This is a test of traffic across the VNet peering relationship.</span><span class="sxs-lookup"><span data-stu-id="03718-149">This is a test of traffic across the VNet peering relationship.</span></span> 
  
<span data-ttu-id="03718-150">Im nächsten Schritt führen Sie diesen Befehl über die Windows PowerShell-Eingabeaufforderung auf DC2 aus, um das zusätzliche Datenlaufwerk als neues Volume mit dem Laufwerkbuchstaben „F:“ hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="03718-150">Next, add the extra data disk as a new volume with the drive letter F: with this command from the Windows PowerShell command prompt on DC2.</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="03718-151">Next, configure DC2 as a replica domain controller for the corp.contoso.com domain.</span><span class="sxs-lookup"><span data-stu-id="03718-151">Next, configure DC2 as a replica domain controller for the corp.contoso.com domain.</span></span> <span data-ttu-id="03718-152">Run these commands from the Windows PowerShell command prompt on DC2.</span><span class="sxs-lookup"><span data-stu-id="03718-152">Run these commands from the Windows PowerShell command prompt on DC2.</span></span>
  
```powershell
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -Credential (Get-Credential CORP\User1) -DomainName "corp.contoso.com" -InstallDns:$true -DatabasePath "F:\NTDS" -LogPath "F:\Logs" -SysvolPath "F:\SYSVOL"
```

<span data-ttu-id="03718-153">Beachten Sie, dass Sie aufgefordert werden, sowohl das Kennwort für CORP\\CORPUser1 als auch ein DSRM-Kennwort (Directory Services Restore Mode) anzugeben und DC2 neu zu starten. </span><span class="sxs-lookup"><span data-stu-id="03718-153">Note that you are prompted to supply both the CORP\\User1 password and a Directory Services Restore Mode (DSRM) password, and to restart DC2.</span></span> 
  
<span data-ttu-id="03718-154">Now that the XPrem virtual network has its own DNS server (DC2), you must configure the XPrem virtual network to use this DNS server.</span><span class="sxs-lookup"><span data-stu-id="03718-154">Now that the XPrem virtual network has its own DNS server (DC2), you must configure the XPrem virtual network to use this DNS server.</span></span> <span data-ttu-id="03718-155">Run these commands from the Azure PowerShell command prompt on your local computer.</span><span class="sxs-lookup"><span data-stu-id="03718-155">Run these commands from the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -name "XPrem"
$vnet.DhcpOptions.DnsServers="192.168.0.4" 
Set-AzVirtualNetwork -VirtualNetwork $vnet
Restart-AzVM -ResourceGroupName $rgName -Name "DC2"
```

<span data-ttu-id="03718-156">From the Azure portal on your local computer, connect to DC1 with the CORP\\User1 credentials.</span><span class="sxs-lookup"><span data-stu-id="03718-156">From the Azure portal on your local computer, connect to DC1 with the CORP\\User1 credentials.</span></span> <span data-ttu-id="03718-157">To configure the CORP domain so that computers and users use their local domain controller for authentication, run these commands from an administrator-level Windows PowerShell command prompt on DC1.</span><span class="sxs-lookup"><span data-stu-id="03718-157">To configure the CORP domain so that computers and users use their local domain controller for authentication, run these commands from an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
New-ADReplicationSite -Name "TestLab" 
New-ADReplicationSite -Name "XPrem"
New-ADReplicationSubnet -Name "10.0.0.0/8" -Site "TestLab"
New-ADReplicationSubnet -Name "192.168.0.0/16" -Site "XPrem"
```

<span data-ttu-id="03718-158">Dies ist Ihre aktuelle Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="03718-158">This is your current configuration.</span></span> 
  
![Phase 3 des simulierten standortübergreifenden virtuellen Netzwerks in der Testumgebung mit dem virtuellen DC2-Computer im XPrem VNet](../media/simulated-cross-premises-microsoft-365-enterprise/df458c56-022b-4688-ab18-056c3fd776b4.png)
  
<span data-ttu-id="03718-160">Ihre simulierte Hybrid Cloud-Umgebung für Azure kann nun getestet werden.</span><span class="sxs-lookup"><span data-stu-id="03718-160">Your simulated Azure hybrid cloud environment is now ready for testing.</span></span>
  
<span data-ttu-id="03718-161">Sie können nun die zusätzlichen Funktionen von [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) ausprobieren.</span><span class="sxs-lookup"><span data-stu-id="03718-161">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="03718-162">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="03718-162">Next steps</span></span>

<span data-ttu-id="03718-163">Sehen Sie sich diese zusätzlichen Testumgebungsanleitungen an:</span><span class="sxs-lookup"><span data-stu-id="03718-163">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="03718-164">Identität</span><span class="sxs-lookup"><span data-stu-id="03718-164">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="03718-165">Verwaltung mobiler Geräte</span><span class="sxs-lookup"><span data-stu-id="03718-165">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="03718-166">Schutz von Daten</span><span class="sxs-lookup"><span data-stu-id="03718-166">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a><span data-ttu-id="03718-167">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03718-167">See also</span></span>

[<span data-ttu-id="03718-168">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="03718-168">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="03718-169">Bereitstellen von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="03718-169">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="03718-170">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="03718-170">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
