---
title: Simulierte Unternehmensstandardkonfiguration für Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Verwenden Sie diese Testumgebungsanleitung, um eine Testumgebung mit einem simulierten Unternehmen für Microsoft 365 Enterprise zu erstellen.
ms.openlocfilehash: 486429bf9e1c0a88c9beb01a092f968256c1fa77
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818495"
---
# <a name="the-simulated-enterprise-base-configuration"></a><span data-ttu-id="eaaad-103">Die simulierte Unternehmensstandardkonfiguration</span><span class="sxs-lookup"><span data-stu-id="eaaad-103">The simulated enterprise base configuration</span></span>

<span data-ttu-id="eaaad-104">*Diese Testumgebungsanleitung kann für Microsoft 365 Enterprise- und Office 365 Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="eaaad-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="eaaad-105">Dieser Artikel bietet Schrittanleitungen zum Erstellen einer vereinfachten Umgebung für Microsoft 365 Enterprise, die Folgendes umfasst:</span><span class="sxs-lookup"><span data-stu-id="eaaad-105">This article provides you with step-by-step instructions to create a simplified environment for Microsoft 365 Enterprise that includes:</span></span>

- <span data-ttu-id="eaaad-106">Eine Testversion oder ein kostenpflichtiges Abonnement für Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="eaaad-106">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="eaaad-107">Ein vereinfachtes Unternehmensintranet mit Internetzugriff, das aus drei virtuellen Computern in einem virtuellen Azure-Netzwerk (DC1, APP1 und CLIENT1) besteht.</span><span class="sxs-lookup"><span data-stu-id="eaaad-107">A simplified organization intranet connected to the Internet, consisting of three virtual machines on an Azure virtual network (DC1, APP1, and CLIENT1).</span></span>
 
![Die simulierte Unternehmensstandardkonfiguration](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="eaaad-109">Sie können die resultierende Umgebung verwenden, um die Features und Funktionen von [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) zu testen, mit zusätzlichen [Testumgebungsanleitungen](m365-enterprise-test-lab-guides.md) oder selbst.</span><span class="sxs-lookup"><span data-stu-id="eaaad-109">You can use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) with additional [Test Lab Guides](m365-enterprise-test-lab-guides.md) or on your own.</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="eaaad-111">Wechseln Sie zu [Microsoft 365 Enterprise Test Lab Ratgeberstapel](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="eaaad-111">Go to [Microsoft 365 Enterprise Test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-create-a-simulated-intranet"></a><span data-ttu-id="eaaad-112">Phase 1: Erstellen eines simulierten Intranets</span><span class="sxs-lookup"><span data-stu-id="eaaad-112">Phase 1: Create a simulated intranet</span></span>

<span data-ttu-id="eaaad-113">In dieser Phase erstellen Sie ein simuliertes Intranet in den Azure-Infrastrukturdiensten, das einen Active Directory Domain Services(AD DS)-Domänencontroller, einen Anwendungsserver und einen Clientcomputer umfasst.</span><span class="sxs-lookup"><span data-stu-id="eaaad-113">In this phase, you build a simulated intranet in Azure infrastructure services that includes an Active Directory Domain Services (AD DS) domain controller, an application server, and a client computer.</span></span> 

<span data-ttu-id="eaaad-114">Sie verwenden diese Computer in zusätzlichen [Microsoft 365 Enterprise-Testumgebungsanleitungen](m365-enterprise-test-lab-guides.md), um Hybrid-Identitäten und andere Funktionen zu konfigurieren und zu demonstrieren.</span><span class="sxs-lookup"><span data-stu-id="eaaad-114">You'll use these computers in additional [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) to configure and demonstrate hybrid identity and other capabilities.</span></span>

### <a name="method-1-build-your-simulated-intranet-with-an-azure-resource-manager-template"></a><span data-ttu-id="eaaad-115">Methode 1: Erstellen eines simulierten Intranets mit einer Azure Ressourcenmanager-Vorlage</span><span class="sxs-lookup"><span data-stu-id="eaaad-115">Method 1: Build your simulated intranet with an Azure Resource Manager template</span></span>

<span data-ttu-id="eaaad-116">In this method, you use an Azure Resource Manager (ARM) template to build out the simulated intranet.</span><span class="sxs-lookup"><span data-stu-id="eaaad-116">In this method, you use an Azure Resource Manager (ARM) template to build out the simulated intranet.</span></span> <span data-ttu-id="eaaad-117">ARM templates contain all of the instructions to create the Azure networking infrastructure, the virtual machines, and their configuration.</span><span class="sxs-lookup"><span data-stu-id="eaaad-117">ARM templates contain all of the instructions to create the Azure networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="eaaad-118">Lesen Sie vor der Bereitstellung der Vorlage die [Infodatei auf der Vorlagenseite](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) und halten Sie folgende Informationen bereit:</span><span class="sxs-lookup"><span data-stu-id="eaaad-118">Prior to deploying the template, read through the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) and have the following information ready:</span></span>

- <span data-ttu-id="eaaad-119">The public DNS domain name of your test environment (testlab.\<your public domain>).</span><span class="sxs-lookup"><span data-stu-id="eaaad-119">The public DNS domain name of your test environment (testlab.\<your public domain>).</span></span> <span data-ttu-id="eaaad-120">You'll need to enter this name in the **Domain Name field** of the **Custom deployment** page.</span><span class="sxs-lookup"><span data-stu-id="eaaad-120">You'll need to enter this name in the **Domain Name field** of the **Custom deployment** page.</span></span>
- <span data-ttu-id="eaaad-121">A DNS label prefix for the URLs of the public IP addresses of your virtual machines.</span><span class="sxs-lookup"><span data-stu-id="eaaad-121">A DNS label prefix for the URLs of the public IP addresses of your virtual machines.</span></span> <span data-ttu-id="eaaad-122">You'll need to enter this label in the **Dns Label Prefix** field of the **Custom deployment** page.</span><span class="sxs-lookup"><span data-stu-id="eaaad-122">You'll need to enter this label in the **Dns Label Prefix** field of the **Custom deployment** page.</span></span>

<span data-ttu-id="eaaad-123">Klicken Sie nach dem Lesen der Anweisungen auf **In Azure bereitstellen** in der [Infodatei auf der Vorlagenseite](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems), um loszulegen.</span><span class="sxs-lookup"><span data-stu-id="eaaad-123">After reading through the instructions, click **Deploy to Azure** on the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) to get started.</span></span>

>[!Note]
><span data-ttu-id="eaaad-124">Das anhand der ARM-Vorlage erstellte simulierte Intranet erfordert ein kostenpflichtiges Azure-Abonnement.</span><span class="sxs-lookup"><span data-stu-id="eaaad-124">The simulated intranet built by the ARM template requires a paid Azure subscription.</span></span>
>

<span data-ttu-id="eaaad-125">Hier finden Sie Ihre Konfiguration nach Abschluss der Vorlage.</span><span class="sxs-lookup"><span data-stu-id="eaaad-125">Here is your configuration after the template is complete.</span></span>

![Das simulierte Intranet in den Azure-Infrastrukturdiensten](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

### <a name="method-2-build-your-simulated-intranet-with-azure-powershell"></a><span data-ttu-id="eaaad-127">Methode 2: Erstellen Ihres simulierten Intranets mit Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="eaaad-127">Method 2: Build your simulated intranet with Azure PowerShell</span></span>

<span data-ttu-id="eaaad-128">Bei dieser Methode verwenden Sie Windows PowerShell und das Azure PowerShell-Modul zum Erstellen der Netzwerkinfrastruktur, der virtuellen Computer und ihrer Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="eaaad-128">In this method, you use Windows PowerShell and the Azure PowerShell module to build out the networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="eaaad-129">Use this method if you want to get experience creating elements of Azure infrastructure one step at a time with PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eaaad-129">Use this method if you want to get experience creating elements of Azure infrastructure one step at a time with PowerShell.</span></span> <span data-ttu-id="eaaad-130">You can then customize the PowerShell command blocks for your own deployment of other virtual machines in Azure.</span><span class="sxs-lookup"><span data-stu-id="eaaad-130">You can then customize the PowerShell command blocks for your own deployment of other virtual machines in Azure.</span></span>

#### <a name="step-1-create-dc1"></a><span data-ttu-id="eaaad-131">Phase 1: Erstellen von DC1</span><span class="sxs-lookup"><span data-stu-id="eaaad-131">Step 1: Create DC1</span></span>

<span data-ttu-id="eaaad-132">In dieser Phase erstellen wir ein virtuelles Azure-Netzwerk und fügen DC1 hinzu, einen virtuellen Computer, der ein Domänencontroller für eine AD DS-Domäne ist.</span><span class="sxs-lookup"><span data-stu-id="eaaad-132">In this step, we create an Azure virtual network and add DC1, a virtual machine that is a domain controller for an AD DS domain.</span></span>

<span data-ttu-id="eaaad-133">Starten Sie zunächst eine Windows PowerShell-Eingabeaufforderung auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="eaaad-133">First, start a Windows PowerShell command prompt on your local computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="eaaad-134">The following command sets use the latest version of Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eaaad-134">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="eaaad-135">See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span><span class="sxs-lookup"><span data-stu-id="eaaad-135">See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> 
  
<span data-ttu-id="eaaad-136">Melden Sie sich mit dem folgenden Befehl bei Ihrem Azure-Konto an.</span><span class="sxs-lookup"><span data-stu-id="eaaad-136">Sign in to your Azure account with the following command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="eaaad-137">Rufen Sie den Namen Ihres Abonnements mithilfe des folgenden Befehls ab.</span><span class="sxs-lookup"><span data-stu-id="eaaad-137">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="eaaad-138">Set your Azure subscription.</span><span class="sxs-lookup"><span data-stu-id="eaaad-138">Set your Azure subscription.</span></span> <span data-ttu-id="eaaad-139">Replace everything within the quotes, including the < and > characters, with the correct name.</span><span class="sxs-lookup"><span data-stu-id="eaaad-139">Replace everything within the quotes, including the < and > characters, with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="eaaad-140">Next, create a new resource group for your simulated enterprise test lab.</span><span class="sxs-lookup"><span data-stu-id="eaaad-140">Next, create a new resource group for your simulated enterprise test lab.</span></span> <span data-ttu-id="eaaad-141">To determine a unique resource group name, use this command to list your existing resource groups.</span><span class="sxs-lookup"><span data-stu-id="eaaad-141">To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="eaaad-142">Create your new resource group with these commands.</span><span class="sxs-lookup"><span data-stu-id="eaaad-142">Create your new resource group with these commands.</span></span> <span data-ttu-id="eaaad-143">Replace everything within the quotes, including the < and > characters, with the correct names.</span><span class="sxs-lookup"><span data-stu-id="eaaad-143">Replace everything within the quotes, including the < and > characters, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="eaaad-144">Next, you create the TestLab virtual network that will host the Corpnet subnet of the simulated enterprise environment and protect it with a network security group.</span><span class="sxs-lookup"><span data-stu-id="eaaad-144">Next, you create the TestLab virtual network that will host the Corpnet subnet of the simulated enterprise environment and protect it with a network security group.</span></span> <span data-ttu-id="eaaad-145">Fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span><span class="sxs-lookup"><span data-stu-id="eaaad-145">Fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<name of your new resource group>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet -DNSServer 10.0.0.4
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name TestLab
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

<span data-ttu-id="eaaad-146">Als Nächstes erstellen Sie den virtuellen Computer DC1 und konfigurieren ihn als Domänencontroller für **testlab.**\<your public domain></span><span class="sxs-lookup"><span data-stu-id="eaaad-146">Next, you create the DC1 virtual machine and configure it as a domain controller for the **testlab.**\<your public domain></span></span> <span data-ttu-id="eaaad-147">AD DS-Domäne und ein DNS-Server für die virtuellen Computer des virtuellen Netzwerks TestLab.</span><span class="sxs-lookup"><span data-stu-id="eaaad-147">AD DS domain and a DNS server for the virtual machines of the TestLab virtual network.</span></span> <span data-ttu-id="eaaad-148">Wenn der Name der öffentlichen Domäne **<span>contoso</span>.com** ist, ist die virtuelle Maschine DC1 ein Domänencontroller für die Domäne **<span>testlab</span>.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="eaaad-148">For example, if your public domain name is **<span>contoso</span>.com**, the DC1 virtual machine will be a domain controller for the **<span>testlab</span>.contoso.com** domain.</span></span>
  
<span data-ttu-id="eaaad-149">Geben Sie zum Erstellen eines virtuellen Azure-Computers für DC1 den Namen Ihrer Ressourcengruppe ein, und führen Sie über die PowerShell-Eingabeaufforderung auf Ihrem lokalen Computer die nachfolgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="eaaad-149">To create an Azure virtual machine for DC1, fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name DC1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name DC1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress 10.0.0.4
$vm=New-AzVMConfig -VMName DC1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for DC1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName DC1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "DC1-OS" -DiskSizeInGB 128 -CreateOption FromImage
$diskConfig=New-AzDiskConfig -AccountType "Standard_LRS" -Location $locName -CreateOption Empty -DiskSizeGB 20
$dataDisk1=New-AzDisk -DiskName "DC1-DataDisk1" -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name "DC1-DataDisk1" -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="eaaad-150">You will be prompted for a user name and password for the local administrator account on DC1.</span><span class="sxs-lookup"><span data-stu-id="eaaad-150">You will be prompted for a user name and password for the local administrator account on DC1.</span></span> <span data-ttu-id="eaaad-151">Use a strong password and record both the name and password in a secure location.</span><span class="sxs-lookup"><span data-stu-id="eaaad-151">Use a strong password and record both the name and password in a secure location.</span></span>
  
<span data-ttu-id="eaaad-152">Stellen Sie dann eine Verbindung mit dem virtuellen Computer DC1 her.</span><span class="sxs-lookup"><span data-stu-id="eaaad-152">Next, connect to the DC1 virtual machine.</span></span>
  
1. <span data-ttu-id="eaaad-153">Klicken Sie im [Azure-Portal](https://portal.azure.com) auf **Ressourcengruppen >** [Name der neuen Ressourcengruppe] **> DC1 > Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="eaaad-153">In the [Azure portal](https://portal.azure.com), click **Resource Groups >** [the name of your new resource group] **> DC1 > Connect**.</span></span>
    
2. <span data-ttu-id="eaaad-154">In the open pane, click **Download RDP file**.</span><span class="sxs-lookup"><span data-stu-id="eaaad-154">In the open pane, click **Download RDP file**.</span></span> <span data-ttu-id="eaaad-155">Open the DC1.rdp file that is downloaded, and then click **Connect**.</span><span class="sxs-lookup"><span data-stu-id="eaaad-155">Open the DC1.rdp file that is downloaded, and then click **Connect**.</span></span>
    
3. <span data-ttu-id="eaaad-156">Geben Sie den Namen des lokalen DC1-Administratorkontos an:</span><span class="sxs-lookup"><span data-stu-id="eaaad-156">Specify the DC1 local administrator account name:</span></span>
    
   - <span data-ttu-id="eaaad-157">Für Windows 7:</span><span class="sxs-lookup"><span data-stu-id="eaaad-157">For Windows 7:</span></span>
    
     <span data-ttu-id="eaaad-158">In the **Windows Security** dialog box, click **Use another account**.</span><span class="sxs-lookup"><span data-stu-id="eaaad-158">In the **Windows Security** dialog box, click **Use another account**.</span></span> <span data-ttu-id="eaaad-159">In **User name**, type **DC1\\**[Local administrator account name].</span><span class="sxs-lookup"><span data-stu-id="eaaad-159">In **User name**, type **DC1\\**[Local administrator account name].</span></span>
    
   - <span data-ttu-id="eaaad-160">Für Windows 8 oder Windows 10:</span><span class="sxs-lookup"><span data-stu-id="eaaad-160">For Windows 8 or Windows 10:</span></span>
    
     <span data-ttu-id="eaaad-161">In the **Windows Security** dialog box, click **More choices**, and then click **Use a different account**.</span><span class="sxs-lookup"><span data-stu-id="eaaad-161">In the **Windows Security** dialog box, click **More choices**, and then click **Use a different account**.</span></span> <span data-ttu-id="eaaad-162">In **User name**, type **DC1\\**[Local administrator account name].</span><span class="sxs-lookup"><span data-stu-id="eaaad-162">In **User name**, type **DC1\\**[Local administrator account name].</span></span>
    
4. <span data-ttu-id="eaaad-163">Geben Sie unter **Kennwort** das Kennwort des lokalen Administratorkontos ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="eaaad-163">In **Password**, type the password of the local administrator account, and then click **OK**.</span></span>
    
5. <span data-ttu-id="eaaad-164">Klicken Sie auf **Ja**, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="eaaad-164">When prompted, click **Yes**.</span></span>
    
<span data-ttu-id="eaaad-165">Im nächsten Schritt führen Sie diesen Befehl über eine Windows PowerShell-Eingabeaufforderung mit Administratorrechten auf DC1 aus, um ein zusätzliches Datenlaufwerk als neues Volume mit dem Laufwerkbuchstaben „F:" hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="eaaad-165">Next, add an extra data disk as a new volume with the drive letter F: with this command at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="eaaad-166">Konfigurieren Sie als Nächstes DC1 als Domänencontroller und DNS-Server für **testlab.**\<your public domain></span><span class="sxs-lookup"><span data-stu-id="eaaad-166">Next, configure DC1 as a domain controller and DNS server for the **testlab.**\<your public domain></span></span> <span data-ttu-id="eaaad-167">Domain vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="eaaad-167">domain.</span></span> <span data-ttu-id="eaaad-168">Geben Sie den Namen Ihrer öffentlichen Domäne an, entfernen Sie die \< and > Zeichen, und führen Sie dann die folgenden Befehle auf einer Administratorebene aus: Windows PowerShell-Eingabeaufforderung auf DC1.</span><span class="sxs-lookup"><span data-stu-id="eaaad-168">Specify your public domain name, remove the \< and > characters, and then run these commands at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
$yourDomain="<your public domain>"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSForest -DomainName testlab.$yourDomain -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs"
```
<span data-ttu-id="eaaad-169">You will need to specify a safe mode administrator password.</span><span class="sxs-lookup"><span data-stu-id="eaaad-169">You will need to specify a safe mode administrator password.</span></span> <span data-ttu-id="eaaad-170">Store this password in a secure location.</span><span class="sxs-lookup"><span data-stu-id="eaaad-170">Store this password in a secure location.</span></span>
  
<span data-ttu-id="eaaad-171">Beachten Sie, dass der Abschluss dieser Befehle ein paar Minuten in Anspruch nehmen kann.</span><span class="sxs-lookup"><span data-stu-id="eaaad-171">Note that these commands can take a few minutes to complete.</span></span>
  
<span data-ttu-id="eaaad-172">Stellen Sie nach dem Neustart von DC1 wieder eine Verbindung zum virtuellen DC1-Computer her.</span><span class="sxs-lookup"><span data-stu-id="eaaad-172">After DC1 restarts, reconnect to the DC1 virtual machine.</span></span>
  
1. <span data-ttu-id="eaaad-173">Klicken Sie im [Azure-Portal](https://portal.azure.com) auf **Ressourcengruppen >** [Ihre Ressourcengruppe] **> DC1 > Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="eaaad-173">In the [Azure portal](https://portal.azure.com), click **Resource Groups >** [your resource group name] **> DC1 > Connect**.</span></span>
    
2. <span data-ttu-id="eaaad-174">Führen Sie die Datei „DC1.rdp“ aus, die heruntergeladen wurde, und klicken Sie dann auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="eaaad-174">Run the DC1.rdp file that is downloaded, and then click **Connect**.</span></span>
    
3. <span data-ttu-id="eaaad-175">In **Windows Security**, click **Use another account**.</span><span class="sxs-lookup"><span data-stu-id="eaaad-175">In **Windows Security**, click **Use another account**.</span></span> <span data-ttu-id="eaaad-176">In **User name**, type **TESTLAB\\**[Local administrator account name].</span><span class="sxs-lookup"><span data-stu-id="eaaad-176">In **User name**, type **TESTLAB\\**[Local administrator account name].</span></span>
    
4. <span data-ttu-id="eaaad-177">Geben Sie unter **Kennwort** das Kennwort des lokalen Administratorkontos ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="eaaad-177">In **Password**, type the password of the local administrator account, and then click **OK**.</span></span>
    
5. <span data-ttu-id="eaaad-178">Klicken Sie auf **Ja**, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="eaaad-178">When prompted, click **Yes**.</span></span>
    
<span data-ttu-id="eaaad-179">Next, create a user account in Active Directory that will be used when logging in to TESTLAB domain member computers.</span><span class="sxs-lookup"><span data-stu-id="eaaad-179">Next, create a user account in Active Directory that will be used when logging in to TESTLAB domain member computers.</span></span> <span data-ttu-id="eaaad-180">Run this command at an administrator-level Windows PowerShell command prompt.</span><span class="sxs-lookup"><span data-stu-id="eaaad-180">Run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
New-ADUser -SamAccountName User1 -AccountPassword (read-host "Set user password" -assecurestring) -name "User1" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```

<span data-ttu-id="eaaad-181">Note that this command prompts you to supply the User1 account password.</span><span class="sxs-lookup"><span data-stu-id="eaaad-181">Note that this command prompts you to supply the User1 account password.</span></span> <span data-ttu-id="eaaad-182">Because this account will be used for remote desktop connections for all TESTLAB domain member computers, choose a strong password.</span><span class="sxs-lookup"><span data-stu-id="eaaad-182">Because this account will be used for remote desktop connections for all TESTLAB domain member computers, choose a strong password.</span></span> <span data-ttu-id="eaaad-183">Record the User1 account password and store it in a secured location.</span><span class="sxs-lookup"><span data-stu-id="eaaad-183">Record the User1 account password and store it in a secured location.</span></span>
  
<span data-ttu-id="eaaad-184">Next, configure the new User1 account as a domain, enterprise, and schema administrator.</span><span class="sxs-lookup"><span data-stu-id="eaaad-184">Next, configure the new User1 account as a domain, enterprise, and schema administrator.</span></span> <span data-ttu-id="eaaad-185">Run this command at the administrator-level Windows PowerShell command prompt.</span><span class="sxs-lookup"><span data-stu-id="eaaad-185">Run this command at the administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
$yourDomain="<your public domain>"
$domainName = "testlab."+$yourDomain
$userName="user1@" + $domainName
$userSID=(New-Object System.Security.Principal.NTAccount($userName)).Translate([System.Security.Principal.SecurityIdentifier]).Value
$groupNames=@("Domain Admins","Enterprise Admins","Schema Admins")
ForEach ($name in $groupNames) {Add-ADPrincipalGroupMembership -Identity $userSID -MemberOf (Get-ADGroup -Identity $name).SID.Value}
```

<span data-ttu-id="eaaad-186">Schließen Sie die Remotedesktopsitzung mit DC1, und stellen Sie dann mit dem Konto „TESTLAB\\Benutzer1“ wieder eine Verbindung her.</span><span class="sxs-lookup"><span data-stu-id="eaaad-186">Close the Remote Desktop session with DC1 and then reconnect using the TESTLAB\\User1 account.</span></span>
  
<span data-ttu-id="eaaad-187">Führen Sie als Nächstes den folgenden Befehl an einer Windows PowerShell-Eingabeaufforderung auf Administratorebene aus, um Datenverkehr für das Tool Ping zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="eaaad-187">Next, to allow traffic for the Ping tool, run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
```

<span data-ttu-id="eaaad-188">Dies ist Ihre aktuelle Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="eaaad-188">This is your current configuration.</span></span>
  
![Schritt 1 der simulierten Unternehmensstandardkonfiguration](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase1.png)
  
#### <a name="step-2-configure-app1"></a><span data-ttu-id="eaaad-190">Schritt 2: Konfigurieren von APP1</span><span class="sxs-lookup"><span data-stu-id="eaaad-190">Step 2: Configure APP1</span></span>

<span data-ttu-id="eaaad-191">In diesem Schritt erstellen und konfigurieren Sie APP1, ein Anwendungsserver, der zunächst Web- und Dateifreigabedienste bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="eaaad-191">In this step, you create and configure APP1, which is an application server that initially provides web and file sharing services.</span></span>

<span data-ttu-id="eaaad-192">Geben Sie zum Erstellen eines virtuellen Azure-Computers für APP1 den Namen Ihrer Ressourcengruppe ein, und führen Sie über die Eingabeaufforderung auf Ihrem lokalen Computer die nachfolgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="eaaad-192">To create an Azure Virtual Machine for APP1, fill in the name of your resource group and run these commands at the  command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name APP1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name APP1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName APP1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for APP1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName APP1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "APP1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="eaaad-193">Im nächsten Schritt stellen Sie eine Verbindung mit dem virtuellen Computer APP1 mit dem Kontonamen und Kennwort des lokalen Administratorkontos von APP1 her und öffnen dann eine Windows PowerShell-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="eaaad-193">Next, connect to the APP1 virtual machine using the APP1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="eaaad-194">Wenn Sie die Namensauflösung und Netzwerkkommunikation zwischen APP1 und DC1 überprüfen möchten, führen Sie **ping dc1.testlab.**\<your public domain name> aus</span><span class="sxs-lookup"><span data-stu-id="eaaad-194">To check name resolution and network communication between APP1 and DC1, run the **ping dc1.testlab.**\<your public domain name></span></span> <span data-ttu-id="eaaad-195">und überprüfen Sie, ob vier Antworten vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="eaaad-195">command and verify that there are four replies.</span></span>
  
<span data-ttu-id="eaaad-196">Verknüpfen Sie als Nächstes unter Verwendung der folgenden Befehle an der Windows PowerShell-Eingabeaufforderung den virtuellen Computer APP1 mit der Domäne TESTLAB.</span><span class="sxs-lookup"><span data-stu-id="eaaad-196">Next, join the APP1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

<span data-ttu-id="eaaad-197">Beachten Sie, dass Sie nach der Ausführung des Befehls **Add-Computer** die Anmeldeinformationen für das Domänenkonto „TESTLAB\\Benutzer1“ eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="eaaad-197">Note that you must supply the TESTLAB\\User1 domain account credentials after running the **Add-Computer** command.</span></span>
  
<span data-ttu-id="eaaad-198">Stellen Sie nach dem Neustart von APP1 eine Verbindung über das Konto „TESLAB\\Benutzer1“ damit her, und öffnen Sie dann eine Windows PowerShell-Eingabeaufforderung auf Administratorebene.</span><span class="sxs-lookup"><span data-stu-id="eaaad-198">After APP1 restarts, connect to it using the TESTLAB\\User1 account, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="eaaad-199">Im nächsten Schritt richten Sie APP1 mit dem folgenden Befehl in der Windows PowerShell-Eingabeaufforderung auf Administratorebene auf APP1 als Webserver ein.</span><span class="sxs-lookup"><span data-stu-id="eaaad-199">Next, make APP1 a web server with this command at an administrator-level Windows PowerShell command prompt on APP1.</span></span>
  
```powershell
Install-WindowsFeature Web-WebServer -IncludeManagementTools
```

<span data-ttu-id="eaaad-200">Erstellen Sie als Nächstes einen freigegebenen Ordner und eine Textdatei innerhalb des Ordners auf APP1 mit diesen PowerShell-Befehlen.</span><span class="sxs-lookup"><span data-stu-id="eaaad-200">Next, create a shared folder and a text file within the folder on APP1 with these PowerShell commands.</span></span>
  
```powershell
New-Item -path c:\files -type directory
Write-Output "This is a shared file." | out-file c:\files\example.txt
New-SmbShare -name files -path c:\files -changeaccess TESTLAB\User1
```

<span data-ttu-id="eaaad-201">Dies ist Ihre aktuelle Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="eaaad-201">This is your current configuration.</span></span>
  
![Schritt 2 der simulierten Unternehmensstandardkonfiguration](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase2.png)
  
#### <a name="step-3-configure-client1"></a><span data-ttu-id="eaaad-203">Schritt 3: Konfigurieren von CLIENT1</span><span class="sxs-lookup"><span data-stu-id="eaaad-203">Step 3: Configure CLIENT1</span></span>

<span data-ttu-id="eaaad-204">In diesem Schritt wird CLIENT1 erstellt und konfiguriert, der als typischer Laptop, als Tablet oder als Desktopcomputer im Intranet fungiert.</span><span class="sxs-lookup"><span data-stu-id="eaaad-204">In this step, you create and configure CLIENT1, which acts as a typical laptop, tablet, or desktop computer on the intranet.</span></span>

> [!NOTE]  
> <span data-ttu-id="eaaad-205">The following command set creates CLIENT1 running Windows Server 2016 Datacenter, which can be done for all types of Azure subscriptions.</span><span class="sxs-lookup"><span data-stu-id="eaaad-205">The following command set creates CLIENT1 running Windows Server 2016 Datacenter, which can be done for all types of Azure subscriptions.</span></span> <span data-ttu-id="eaaad-206">If you have a Visual Studio-based Azure subscription, you can create CLIENT1 running Windows 10 with the [Azure portal](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="eaaad-206">If you have a Visual Studio-based Azure subscription, you can create CLIENT1 running Windows 10 with the [Azure portal](https://portal.azure.com).</span></span> 
  
<span data-ttu-id="eaaad-207">Geben Sie zum Erstellen eines virtuellen Azure-Computers für CLIENT1 den Namen Ihrer Ressourcengruppe ein, und führen Sie über die Eingabeaufforderung auf Ihrem lokalen Computer die nachfolgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="eaaad-207">To create an Azure Virtual Machine for CLIENT1, fill in the name of your resource group and run these commands at the  command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name CLIENT1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name CLIENT1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName CLIENT1 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for CLIENT1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName CLIENT1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "CLIENT1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="eaaad-208">Im nächsten Schritt stellen Sie eine Verbindung mit dem virtuellen Computer CLIENT1 mit dem Kontonamen und Kennwort des lokalen Administratorkontos von CLIENT1 her und öffnen dann eine Windows PowerShell-Eingabeaufforderung auf Administratorebene.</span><span class="sxs-lookup"><span data-stu-id="eaaad-208">Next, connect to the CLIENT1 virtual machine using the CLIENT1 local administrator account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="eaaad-209">Wenn Sie die Namensauflösung und Netzwerkkommunikation zwischen CLIENT1 und DC1 überprüfen möchten, führen Sie **ping dc1.testlab.**\<your public domain name></span><span class="sxs-lookup"><span data-stu-id="eaaad-209">To check name resolution and network communication between CLIENT1 and DC1, run the **ping dc1.testlab.**\<your public domain name></span></span> <span data-ttu-id="eaaad-210">an einer Windows PowerShell Kommandozeile aus und stellen Sie sicher, dass vier Antworten vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="eaaad-210">command at a Windows PowerShell command prompt and verify that there are four replies.</span></span>
  
<span data-ttu-id="eaaad-211">Verknüpfen Sie als Nächstes unter Verwendung der folgenden Befehle an der Windows PowerShell-Eingabeaufforderung den virtuellen Computer CLIENT1 mit der Domäne TESTLAB.</span><span class="sxs-lookup"><span data-stu-id="eaaad-211">Next, join the CLIENT1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

<span data-ttu-id="eaaad-212">Beachten Sie, dass Sie nach der Ausführung des Befehls **Add-Computer** die Anmeldeinformationen für das Domänenkonto „TESTLAB\\Benutzer1“ eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="eaaad-212">Note that you must supply your TESTLAB\\User1 domain account credentials after running the **Add-Computer** command.</span></span>
  
<span data-ttu-id="eaaad-213">Stellen Sie nach dem Neustart von CLIENT1 eine Verbindung über den Kontonamen und das Kennwort von „TESTLAB\\Benutzer1“ damit her, und öffnen Sie dann eine Windows PowerShell-Eingabeaufforderung auf Administratorebene.</span><span class="sxs-lookup"><span data-stu-id="eaaad-213">After CLIENT1 restarts, connect to it using the TESTLAB\\User1 account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="eaaad-214">Überprüfen Sie im nächsten Schritt, ob Sie von CLIENT1 aus auf Web- und Dateifreigaberessourcen auf APP1 zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="eaaad-214">Next, verify that you can access web and file share resources on APP1 from CLIENT1.</span></span>
  
1. <span data-ttu-id="eaaad-215">Klicken Sie im Server-Manager im Strukturbereich auf **Lokaler Server**.</span><span class="sxs-lookup"><span data-stu-id="eaaad-215">In Server Manager, in the tree pane, click **Local Server**.</span></span>
    
2. <span data-ttu-id="eaaad-216">Klicken Sie in **Eigenschaften für CLIENT1** neben **Verstärkte Sicherheitskonfiguration für IE** auf **Ein**.</span><span class="sxs-lookup"><span data-stu-id="eaaad-216">In **Properties for CLIENT1**, click **On** next to **IE Enhanced Security Configuration**.</span></span>
    
3. <span data-ttu-id="eaaad-217">Klicken Sie unter **Verstärkte Sicherheitskonfiguration für Internet Explorer** für **Administratoren** und für **Benutzer** auf **Aus**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="eaaad-217">In **Internet Explorer Enhanced Security Configuration**, click **Off** for **Administrators** and **Users**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="eaaad-218">Klicken Sie auf dem Startbildschirm auf **Internet Explorer** und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="eaaad-218">From the Start screen, click **Internet Explorer**, and then click **OK**.</span></span>
    
5. <span data-ttu-id="eaaad-219">Geben Sie in der Adressleiste **http<span>://</span>app1.testab.**\<your public domain name>**/** ein und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="eaaad-219">In the Address bar, type **http<span>://</span>app1.testab.**\<your public domain name>**/**, and then press ENTER.</span></span> <span data-ttu-id="eaaad-220">Nun sollte die standardmäßige Internetinformationsdienste-Webseite für APP1 angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="eaaad-220">You should see the default Internet Information Services web page for APP1.</span></span>
    
6. <span data-ttu-id="eaaad-221">Klicken Sie auf der Desktop-Taskleiste auf das Symbol für den Datei-Explorer.</span><span class="sxs-lookup"><span data-stu-id="eaaad-221">From the desktop taskbar, click the File Explorer icon.</span></span>
    
7. <span data-ttu-id="eaaad-222">In the address bar, type **\\\\app1\\Files**, and then press ENTER.</span><span class="sxs-lookup"><span data-stu-id="eaaad-222">In the address bar, type **\\\\app1\\Files**, and then press ENTER.</span></span> <span data-ttu-id="eaaad-223">You should see a folder window with the contents of the Files shared folder.</span><span class="sxs-lookup"><span data-stu-id="eaaad-223">You should see a folder window with the contents of the Files shared folder.</span></span>
    
8. <span data-ttu-id="eaaad-224">In the **Files** shared folder window, double-click the **Example.txt** file.</span><span class="sxs-lookup"><span data-stu-id="eaaad-224">In the **Files** shared folder window, double-click the **Example.txt** file.</span></span> <span data-ttu-id="eaaad-225">You should see the contents of the Example.txt file.</span><span class="sxs-lookup"><span data-stu-id="eaaad-225">You should see the contents of the Example.txt file.</span></span>
    
9. <span data-ttu-id="eaaad-226">Schließen Sie das Fenster **example.txt - Editor** und das Fenster des freigegebenen Ordners **Files**.</span><span class="sxs-lookup"><span data-stu-id="eaaad-226">Close the **example.txt - Notepad** and the **Files** shared folder windows.</span></span>
    
<span data-ttu-id="eaaad-227">Dies ist Ihre aktuelle Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="eaaad-227">This is your current configuration.</span></span>
  
![Schritt 3 der simulierten Unternehmensstandardkonfiguration](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)


## <a name="phase-2-create-your-microsoft-365-e5-subscription"></a><span data-ttu-id="eaaad-229">Phase 2: Erstellen Ihres Abonnements für Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="eaaad-229">Phase 2: Create your Microsoft 365 E5 subscription</span></span>

<span data-ttu-id="eaaad-230">In this phase, you create a new Microsoft 365 E5 subscription that uses a new Azure AD tenant, one that is separate from your production subscription.</span><span class="sxs-lookup"><span data-stu-id="eaaad-230">In this phase, you create a new Microsoft 365 E5 subscription that uses a new Azure AD tenant, one that is separate from your production subscription.</span></span> <span data-ttu-id="eaaad-231">You can do this in two ways:</span><span class="sxs-lookup"><span data-stu-id="eaaad-231">You can do this in two ways:</span></span>

- <span data-ttu-id="eaaad-232">Verwenden Sie ein Testabonnement von Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="eaaad-232">Use a trial subscription of Microsoft 365 E5.</span></span> 

  <span data-ttu-id="eaaad-233">The Microsoft 365 E5 trial subscription is 30 days, which can be easily extended to 60 days.</span><span class="sxs-lookup"><span data-stu-id="eaaad-233">The Microsoft 365 E5 trial subscription is 30 days, which can be easily extended to 60 days.</span></span> <span data-ttu-id="eaaad-234">When the trial subscription expires, you must either convert it to a paid subscription or create a new trial subscription.</span><span class="sxs-lookup"><span data-stu-id="eaaad-234">When the trial subscription expires, you must either convert it to a paid subscription or create a new trial subscription.</span></span> <span data-ttu-id="eaaad-235">Creating new trial subscriptions means you will leave your configuration, which could include complex scenarios, behind.</span><span class="sxs-lookup"><span data-stu-id="eaaad-235">Creating new trial subscriptions means you will leave your configuration, which could include complex scenarios, behind.</span></span>  

- <span data-ttu-id="eaaad-236">Verwenden Sie ein separates Produktionsabonnement von Microsoft 365 E5 mit einer kleinen Anzahl von Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="eaaad-236">Use a separate production subscription of Microsoft 365 E5 with a small number of licenses.</span></span>

  <span data-ttu-id="eaaad-237">This is an additional cost, but ensures that you have a working test environment to try features, configurations, and scenarios that does not expire.</span><span class="sxs-lookup"><span data-stu-id="eaaad-237">This is an additional cost, but ensures that you have a working test environment to try features, configurations, and scenarios that does not expire.</span></span> <span data-ttu-id="eaaad-238">You can use the same test environment over the long term for proofs of concept, demonstration to peers and management, and application development and testing.</span><span class="sxs-lookup"><span data-stu-id="eaaad-238">You can use the same test environment over the long term for proofs of concept, demonstration to peers and management, and application development and testing.</span></span> <span data-ttu-id="eaaad-239">This is the recommended method.</span><span class="sxs-lookup"><span data-stu-id="eaaad-239">This is the recommended method.</span></span>

### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="eaaad-240">Registrieren für ein Office 365 E5-Testabonnement</span><span class="sxs-lookup"><span data-stu-id="eaaad-240">Sign up for an Office 365 E5 trial subscription</span></span>

<span data-ttu-id="eaaad-241">Melden Sie sich über das Azure-Portal mit dem CORP\User1-Konto bei CLIENT1 an.</span><span class="sxs-lookup"><span data-stu-id="eaaad-241">Connect to CLIENT1 with the CORP\User1 account from the Azure portal.</span></span>

<span data-ttu-id="eaaad-242">Wenn Sie ein neues Office 365 E5-Testabonnement erstellen möchten, führen Sie die Anweisungen in [Phase 1](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-office-365-e5-subscription) der Testumgebungsanleitung zur einfachen Standardkonfiguration aus.</span><span class="sxs-lookup"><span data-stu-id="eaaad-242">To create a new Office 365 E5 trial subscription, perform the instructions in [Phase 1](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-office-365-e5-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

<span data-ttu-id="eaaad-243">Wenn Sie Ihr neues Office 365 E5-Testabonnement konfigurieren möchten, führen Sie die Anweisungen in [Phase 2](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription) der Testumgebungsanleitung zur einfachen Standardkonfiguration aus.</span><span class="sxs-lookup"><span data-stu-id="eaaad-243">To configure your new Office 365 E5 trial subscription, perform the instructions in [Phase 2](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

#### <a name="using-an-office-365-e5-test-environment"></a><span data-ttu-id="eaaad-244">Verwenden einer Office 365 E5-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="eaaad-244">Using an Office 365 E5 test environment</span></span>

<span data-ttu-id="eaaad-245">Wenn Sie nur eine Office 365-Testumgebung benötigen, sind Sie hier fertig.</span><span class="sxs-lookup"><span data-stu-id="eaaad-245">If all you need is an Office 365 test environment, you can stop here.</span></span> 

<span data-ttu-id="eaaad-246">Weitere Testumgebungsanleitungen, die sowohl für Office 365 als auch für Microsoft 365 gelten, finden Sie unter [Microsoft 365 Enterprise-Testumgebungsanleitungen](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="eaaad-246">See [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) for additional Test Lab Guides that apply to both Office 365 and Microsoft 365.</span></span>

### <a name="add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="eaaad-247">Hinzufügen eines Testabonnements für Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="eaaad-247">Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="eaaad-248">Um ein Microsoft 365 E5-Testabonnement zu testen und Ihre Benutzerkonten mit Lizenzen zu konfigurieren, führen Sie die Anweisungen in [Phase 3](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) der Testumgebungsanleitung zur einfachen Standardkonfiguration aus.</span><span class="sxs-lookup"><span data-stu-id="eaaad-248">To a Microsoft 365 E5 trial subscription and configure your users accounts with licenses, perform the instructions in [Phase 3](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

  
## <a name="results"></a><span data-ttu-id="eaaad-249">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="eaaad-249">Results</span></span>

<span data-ttu-id="eaaad-250">Ihre Testumgebung verfügt nun über Folgendes:</span><span class="sxs-lookup"><span data-stu-id="eaaad-250">Your test environment now has:</span></span>
  
- <span data-ttu-id="eaaad-251">Ein Testabonnement für Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="eaaad-251">Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="eaaad-252">Alle entsprechenden Benutzerkonten sind für die Verwendung von Microsoft 365 E5 aktiviert.</span><span class="sxs-lookup"><span data-stu-id="eaaad-252">All your appropriate user accounts are enabled to use Microsoft 365 E5.</span></span>
- <span data-ttu-id="eaaad-253">Ein simuliertes und vereinfachtes Intranet.</span><span class="sxs-lookup"><span data-stu-id="eaaad-253">A simulated and simplified intranet.</span></span>
    
<span data-ttu-id="eaaad-254">Dies ist Ihre endgültige Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="eaaad-254">This is your final configuration.</span></span>
  
![Phase 2 der simulierten Unternehmensstandardkonfiguration](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)
  
<span data-ttu-id="eaaad-256">Sie können nun die zusätzlichen Funktionen von [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) ausprobieren.</span><span class="sxs-lookup"><span data-stu-id="eaaad-256">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="eaaad-257">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="eaaad-257">Next steps</span></span>

<span data-ttu-id="eaaad-258">Sehen Sie sich diese zusätzlichen Testumgebungsanleitungen an:</span><span class="sxs-lookup"><span data-stu-id="eaaad-258">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="eaaad-259">Identität</span><span class="sxs-lookup"><span data-stu-id="eaaad-259">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="eaaad-260">Verwaltung mobiler Geräte</span><span class="sxs-lookup"><span data-stu-id="eaaad-260">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="eaaad-261">Schutz von Daten</span><span class="sxs-lookup"><span data-stu-id="eaaad-261">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a><span data-ttu-id="eaaad-262">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eaaad-262">See also</span></span>

[<span data-ttu-id="eaaad-263">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="eaaad-263">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="eaaad-264">Bereitstellen von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="eaaad-264">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="eaaad-265">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="eaaad-265">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
