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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Verwenden Sie diese Test Umgebungs Anleitung, um eine simulierte Enterprise-Testumgebung für Microsoft 365 for Enterprise zu erstellen.
ms.openlocfilehash: e66ec8c48e309daeb15aad5fcc475edcb2b8bb35
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487660"
---
# <a name="the-simulated-enterprise-base-configuration"></a><span data-ttu-id="e6fe3-103">Die simulierte Unternehmensstandardkonfiguration</span><span class="sxs-lookup"><span data-stu-id="e6fe3-103">The simulated enterprise base configuration</span></span>

<span data-ttu-id="e6fe3-104">*Diese Test Umgebungs Anleitung kann sowohl für Microsoft 365 für Unternehmen als auch für Office 365 Enterprise Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="e6fe3-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="e6fe3-105">In diesem Artikel wird beschrieben, wie Sie eine vereinfachte Umgebung für Microsoft 365 für Unternehmen erstellen, die Folgendes umfasst:</span><span class="sxs-lookup"><span data-stu-id="e6fe3-105">This article describes how to create a simplified environment for Microsoft 365 for enterprise that includes:</span></span>

- <span data-ttu-id="e6fe3-106">Eine Testversion oder ein kostenpflichtiges Abonnement für Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-106">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="e6fe3-107">Ein vereinfachtes Organisationsintranet, das mit dem Internet verbunden ist und das aus drei virtuellen Computern in einem virtuellen Azure-Netzwerk (DC1, App1 und CLIENT1) besteht.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-107">A simplified organization intranet connected to the internet, consisting of three virtual machines on an Azure virtual network (DC1, APP1, and CLIENT1).</span></span>
 
![Die simulierte Unternehmensstandardkonfiguration](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="e6fe3-109">Das Erstellen einer vereinfachten Testumgebung umfasst zwei Phasen:</span><span class="sxs-lookup"><span data-stu-id="e6fe3-109">Creating a simplified test environment involves two phases:</span></span>
- [<span data-ttu-id="e6fe3-110">Phase 1: Erstellen eines simulierten Intranets</span><span class="sxs-lookup"><span data-stu-id="e6fe3-110">Phase 1: Create a simulated intranet</span></span>](#phase-1-create-a-simulated-intranet)
- [<span data-ttu-id="e6fe3-111">Phase 2: Erstellen Ihres Abonnements für Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="e6fe3-111">Phase 2: Create your Microsoft 365 E5 subscription</span></span>](#phase-2-create-your-microsoft-365-e5-subscription)

<span data-ttu-id="e6fe3-112">Sie können die resultierende Umgebung verwenden, um die Features und Funktionen von [Microsoft 365 for Enterprise](https://www.microsoft.com/microsoft-365/enterprise) mit zusätzlichen [testumgebungsanleitungen](m365-enterprise-test-lab-guides.md) oder eigenständig zu testen.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-112">You can use the resulting environment to test the features and functionality of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise) with additional [Test Lab Guides](m365-enterprise-test-lab-guides.md) or on your own.</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="e6fe3-114">Eine visuelle Zuordnung zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide Stack finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="e6fe3-114">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-create-a-simulated-intranet"></a><span data-ttu-id="e6fe3-115">Phase 1: Erstellen eines simulierten Intranets</span><span class="sxs-lookup"><span data-stu-id="e6fe3-115">Phase 1: Create a simulated intranet</span></span>

<span data-ttu-id="e6fe3-116">Erstellen Sie in dieser Phase ein simuliertes Intranet in Azure-Infrastrukturdiensten, das einen Active Directory-Domänendienste (AD DS) Domänencontroller, einen Anwendungsserver und einen Clientcomputer enthält.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-116">In this phase, build a simulated intranet in Azure infrastructure services that includes an Active Directory Domain Services (AD DS) domain controller, an application server, and a client computer.</span></span>

<span data-ttu-id="e6fe3-117">Sie verwenden diese Computer in weiteren [Microsoft 365 for Enterprise-Test Umgebungs Anleitungen](m365-enterprise-test-lab-guides.md) , um Hybrid Identitäten und andere Funktionen zu konfigurieren und zu demonstrieren.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-117">You'll use these computers in additional [Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) to configure and demonstrate hybrid identity and other capabilities.</span></span>

### <a name="method-1-build-your-simulated-intranet-with-an-azure-resource-manager-template"></a><span data-ttu-id="e6fe3-118">Methode 1: Erstellen eines simulierten Intranets mit einer Azure Ressourcenmanager-Vorlage</span><span class="sxs-lookup"><span data-stu-id="e6fe3-118">Method 1: Build your simulated intranet with an Azure Resource Manager template</span></span>

<span data-ttu-id="e6fe3-119">In dieser Methode verwenden Sie eine Azure Resource Manager-Vorlage, um das simulierte Intranet zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-119">In this method, you use an Azure Resource Manager template to build out the simulated intranet.</span></span> <span data-ttu-id="e6fe3-120">Azure Resource Manager-Vorlagen enthalten alle Anweisungen zum Erstellen der Azure-Netzwerkinfrastruktur, der virtuellen Computer und ihrer Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-120">Azure Resource Manager templates contain all of the instructions to create the Azure networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="e6fe3-121">Lesen Sie vor dem Bereitstellen der Vorlage die [Seite Readme-Vorlage](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) , und halten Sie die folgenden Informationen bereit:</span><span class="sxs-lookup"><span data-stu-id="e6fe3-121">Before deploying the template, read through the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) and have the following information ready:</span></span>

- <span data-ttu-id="e6fe3-122">Der öffentliche DNS-Domänenname der Testumgebung (testlab. \<*your public domain*> ).</span><span class="sxs-lookup"><span data-stu-id="e6fe3-122">The public DNS domain name of your test environment (testlab.\<*your public domain*>).</span></span> <span data-ttu-id="e6fe3-123">Sie geben diesen Namen in das Feld **Domänenname** der Seite **benutzerdefinierte Bereitstellung** ein.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-123">You'll enter this name in the **Domain Name** field of the **Custom deployment** page.</span></span>
- <span data-ttu-id="e6fe3-p103">Ein DNS-Präfix für die URLs der öffentlichen IP-Adressen Ihrer virtueller Computer. Sie müssen diese Bezeichnung in das Feld **DNS-Präfix** der Seite **Benutzerdefinierte Bereitstellung** eingeben.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-p103">A DNS label prefix for the URLs of the public IP addresses of your virtual machines. You'll need to enter this label in the **Dns Label Prefix** field of the **Custom deployment** page.</span></span>

<span data-ttu-id="e6fe3-126">Nachdem Sie die Anweisungen gelesen haben, wählen Sie die Option **in Azure bereitstellen** auf der [Seite Readme-Vorlage](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) aus, um die ersten Schritte zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-126">After you read through the instructions, select **Deploy to Azure** on the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) to get started.</span></span>

>[!Note]
><span data-ttu-id="e6fe3-127">Das simulierte Intranet, das von der Azure Resource Manager-Vorlage erstellt wurde, erfordert ein kostenpflichtiges Azure-Abonnement.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-127">The simulated intranet built by the Azure Resource Manager template requires a paid Azure subscription.</span></span>

<span data-ttu-id="e6fe3-128">Nachdem die Vorlage abgeschlossen ist, sieht Ihre Konfiguration wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="e6fe3-128">After the template is complete, your configuration looks like this:</span></span>

![Das simulierte Intranet in den Azure-Infrastrukturdiensten](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

### <a name="method-2-build-your-simulated-intranet-with-azure-powershell"></a><span data-ttu-id="e6fe3-130">Methode 2: Erstellen Ihres simulierten Intranets mit Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="e6fe3-130">Method 2: Build your simulated intranet with Azure PowerShell</span></span>

<span data-ttu-id="e6fe3-131">Bei dieser Methode verwenden Sie Windows PowerShell und das Azure PowerShell-Modul zum Erstellen der Netzwerkinfrastruktur, der virtuellen Computer und ihrer Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-131">In this method, you use Windows PowerShell and the Azure PowerShell module to build out the networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="e6fe3-p104">Verwenden Sie diese Methode, wenn Sie Erfahrungen mit dem Erstellen von Elementen der Azure-Infrastruktur für jeden einzelnen Schritt mit PowerShell sammeln möchten. Sie können dann die PowerShell-Befehlsblöcke für eine eigene Bereitstellung von anderen virtuellen Computern in Azure anpassen.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-p104">Use this method if you want to get experience creating elements of Azure infrastructure one step at a time with PowerShell. You can then customize the PowerShell command blocks for your own deployment of other virtual machines in Azure.</span></span>

#### <a name="step-1-create-dc1"></a><span data-ttu-id="e6fe3-134">Phase 1: Erstellen von DC1</span><span class="sxs-lookup"><span data-stu-id="e6fe3-134">Step 1: Create DC1</span></span>

<span data-ttu-id="e6fe3-135">In diesem Schritt erstellen Sie ein virtuelles Azure-Netzwerk und fügen DC1 hinzu, ein virtueller Computer, der ein Domänencontroller für eine AD DS Domäne ist.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-135">In this step, you create an Azure virtual network and add DC1, a virtual machine that is a domain controller for an AD DS domain.</span></span>

<span data-ttu-id="e6fe3-136">Starten Sie zunächst eine Windows PowerShell-Eingabeaufforderung auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-136">First, start a Windows PowerShell command prompt on your local computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e6fe3-p105">In den folgenden Befehlssätzen wird die aktuelle Version von Azure PowerShell verwendet. Informationen dazu finden Sie unter [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span><span class="sxs-lookup"><span data-stu-id="e6fe3-p105">The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> 
  
<span data-ttu-id="e6fe3-139">Melden Sie sich mit dem folgenden Befehl bei Ihrem Azure-Konto an.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-139">Sign in to your Azure account with the following command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="e6fe3-140">Rufen Sie den Namen Ihres Abonnements mithilfe des folgenden Befehls ab.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-140">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="e6fe3-141">Tragen Sie Ihr Azure-Abonnement ein.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-141">Set your Azure subscription.</span></span> <span data-ttu-id="e6fe3-142">Ersetzen Sie alles innerhalb der Anführungszeichen, einschließlich der spitzen Klammern ("<" und ">") mit dem korrekten Namen.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-142">Replace everything within the quotation marks, including the angle brackets ("<" and ">"), with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="e6fe3-p107">Im nächsten Schritt wird eine neue Ressourcengruppe für Ihr simuliertes Unternehmenstestlabor erstellt. Verwenden Sie zum Ermitteln eines eindeutigen Ressourcengruppennamens diesen Befehl, mit dem die vorhandenen Ressourcengruppen aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-p107">Next, create a new resource group for your simulated enterprise test lab. To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="e6fe3-145">Erstellen Sie die neue Ressourcengruppe mit diesen Befehlen.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-145">Create your new resource group with these commands.</span></span> <span data-ttu-id="e6fe3-146">Ersetzen Sie alles innerhalb der Anführungszeichen, einschließlich der spitzen Klammern, durch die korrekten Namen.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-146">Replace everything within the quotation marks, including the angle brackets, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="e6fe3-147">Erstellen Sie als nächstes das virtuelle testlab-Netzwerk, in dem das Subnetz des Unternehmensnetzwerks der simulierten Unternehmensumgebung gehostet wird, und schützen Sie es mit einer Netzwerksicherheitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-147">Next, create the TestLab virtual network that will host the corporate network subnet of the simulated enterprise environment and protect it with a network security group.</span></span> <span data-ttu-id="e6fe3-148">Geben Sie den Namen Ihrer Ressourcengruppe ein, und führen Sie diese Befehle an der PowerShell-Eingabeaufforderung auf dem lokalen Computer aus.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-148">Fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
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

<span data-ttu-id="e6fe3-149">Als Nächstes erstellen Sie den virtuellen Computer DC1 und konfigurieren ihn als Domänencontroller für **testlab.**\<your public domain></span><span class="sxs-lookup"><span data-stu-id="e6fe3-149">Next, you create the DC1 virtual machine and configure it as a domain controller for the **testlab.**\<your public domain></span></span> <span data-ttu-id="e6fe3-150">AD DS-Domäne und ein DNS-Server für die virtuellen Computer des virtuellen Netzwerks TestLab.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-150">AD DS domain and a DNS server for the virtual machines of the TestLab virtual network.</span></span> <span data-ttu-id="e6fe3-151">Wenn der Name der öffentlichen Domäne **<span>contoso</span>.com** ist, ist die virtuelle Maschine DC1 ein Domänencontroller für die Domäne **<span>testlab</span>.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-151">For example, if your public domain name is **<span>contoso</span>.com**, the DC1 virtual machine will be a domain controller for the **<span>testlab</span>.contoso.com** domain.</span></span>
  
<span data-ttu-id="e6fe3-152">Geben Sie zum Erstellen eines virtuellen Azure-Computers für DC1 den Namen Ihrer Ressourcengruppe ein, und führen Sie über die PowerShell-Eingabeaufforderung auf Ihrem lokalen Computer die nachfolgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-152">To create an Azure virtual machine for DC1, fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
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

<span data-ttu-id="e6fe3-p111">Sie werden nach einem Benutzernamen und Kennwort für das lokale Administratorkonto auf DC1 gefragt. Verwenden Sie ein sicheres Kennwort, und notieren Sie den Namen und das Kennwort an einem sicheren Ort.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-p111">You will be prompted for a user name and password for the local administrator account on DC1. Use a strong password and record both the name and password in a secure location.</span></span>
  
<span data-ttu-id="e6fe3-155">Stellen Sie als nächstes eine Verbindung mit dem virtuellen DC1-Computer her:</span><span class="sxs-lookup"><span data-stu-id="e6fe3-155">Next, connect to the DC1 virtual machine:</span></span>
  
1. <span data-ttu-id="e6fe3-156">Wählen Sie [im Azure](https://portal.azure.com)-Portal **Ressourcengruppen** > <***den Namen der neuen Ressourcengruppe***> > **DC1**  >  **Connect**aus.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-156">In the [Azure portal](https://portal.azure.com), select **Resource Groups** > <***the name of your new resource group***> > **DC1** > **Connect**.</span></span>
    
2. <span data-ttu-id="e6fe3-157">Wählen Sie im geöffneten Bereich **RDP-Datei herunterladen**aus.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-157">In the open pane, select **Download RDP file**.</span></span> <span data-ttu-id="e6fe3-158">Öffnen Sie die Datei DC1. RDP, die heruntergeladen wird, und wählen Sie dann **verbinden**aus.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-158">Open the DC1.rdp file that is downloaded, and then select **Connect**.</span></span>
    
3. <span data-ttu-id="e6fe3-159">Geben Sie den Namen des lokalen DC1-Administratorkontos an:</span><span class="sxs-lookup"><span data-stu-id="e6fe3-159">Specify the DC1 local administrator account name:</span></span>
    
   - <span data-ttu-id="e6fe3-160">Für Windows 7:</span><span class="sxs-lookup"><span data-stu-id="e6fe3-160">For Windows 7:</span></span>
    
     <span data-ttu-id="e6fe3-161">Wählen Sie im Dialogfeld **Windows-Sicherheit** die Option **anderes Konto verwenden**aus.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-161">In the **Windows Security** dialog box, select **Use another account**.</span></span> <span data-ttu-id="e6fe3-162">Geben Sie unter **Benutzername**den Namen des lokalen \*\*DC1 \\ \*\*- < *Administratorkontos*> ein.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-162">In **User name**, enter **DC1\\**<*local administrator account name*>.</span></span>
    
   - <span data-ttu-id="e6fe3-163">Für Windows 8 oder Windows 10:</span><span class="sxs-lookup"><span data-stu-id="e6fe3-163">For Windows 8 or Windows 10:</span></span>
    
     <span data-ttu-id="e6fe3-164">Wählen Sie im Dialogfeld **Windows-Sicherheit** die Option **Weitere Optionen**aus, und wählen Sie dann **anderes Konto verwenden**aus.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-164">In the **Windows Security** dialog box, select **More choices**, and then select **Use a different account**.</span></span> <span data-ttu-id="e6fe3-165">Geben Sie unter **Benutzername**den Namen des lokalen \*\*DC1 \\ \*\*- < *Administratorkontos*> ein.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-165">In **User name**, enter **DC1\\**<*local administrator account name*>.</span></span>
    
4. <span data-ttu-id="e6fe3-166">Geben Sie unter **Kennwort**das Kennwort des lokalen Administratorkontos ein, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-166">In **Password**, enter the password of the local administrator account, and then select **OK**.</span></span>
    
5. <span data-ttu-id="e6fe3-167">Wenn Sie dazu aufgefordert werden, wählen Sie **Ja**aus.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-167">When prompted, select **Yes**.</span></span>
    
<span data-ttu-id="e6fe3-168">Im nächsten Schritt führen Sie diesen Befehl über eine Windows PowerShell-Eingabeaufforderung mit Administratorrechten auf DC1 aus, um ein zusätzliches Datenlaufwerk als neues Volume mit dem Laufwerkbuchstaben „F:" hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-168">Next, add an extra data disk as a new volume with the drive letter F: with this command at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="e6fe3-169">Konfigurieren Sie als Nächstes DC1 als Domänencontroller und DNS-Server für **testlab.**\<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="e6fe3-169">Next, configure DC1 as a domain controller and DNS server for the **testlab.**\<*your public domain*></span></span> <span data-ttu-id="e6fe3-170">Domain vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-170">domain.</span></span> <span data-ttu-id="e6fe3-171">Geben Sie Ihren öffentlichen Domänennamen an, entfernen Sie die spitzen Klammern, und führen Sie diese Befehle auf einer Windows PowerShell Eingabeaufforderung auf der Administratorebene auf DC1 aus.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-171">Specify your public domain name, remove the angle brackets, and then run these commands at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
$yourDomain="<your public domain>"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSForest -DomainName testlab.$yourDomain -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs"
```
<span data-ttu-id="e6fe3-p116">Sie müssen ein Administratorkennwort für den abgesicherten Modus angeben. Bewahren Sie das Kennwort an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-p116">You will need to specify a safe mode administrator password. Store this password in a secure location.</span></span>
  
<span data-ttu-id="e6fe3-174">Beachten Sie, dass der Abschluss dieser Befehle ein paar Minuten in Anspruch nehmen kann.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-174">Note that these commands can take a few minutes to complete.</span></span>
  
<span data-ttu-id="e6fe3-175">Stellen Sie nach dem Neustart von DC1 wieder eine Verbindung zum virtuellen DC1-Computer her.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-175">After DC1 restarts, reconnect to the DC1 virtual machine.</span></span>
  
1. <span data-ttu-id="e6fe3-176">Wählen Sie im [Azure](https://portal.azure.com)-Portal **Ressourcengruppen** > <*den Namen Ihrer Ressourcengruppe*> > **DC1**  >  **Connect**aus.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-176">In the [Azure portal](https://portal.azure.com), select **Resource Groups** > <*your resource group name*> > **DC1** > **Connect**.</span></span>
    
2. <span data-ttu-id="e6fe3-177">Führen Sie die heruntergeladene Datei DC1. RDP aus, und wählen Sie dann **verbinden**aus.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-177">Run the DC1.rdp file that is downloaded, and then select **Connect**.</span></span>
    
3. <span data-ttu-id="e6fe3-178">Wählen Sie unter **Windows-Sicherheit**die Option **anderes Konto verwenden**aus.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-178">In **Windows Security**, select **Use another account**.</span></span> <span data-ttu-id="e6fe3-179">Geben Sie unter **Benutzername**den Namen \*\*TESTLAB \\ \*\*des < *lokalen Administratorkontos*> ein.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-179">In **User name**, enter **TESTLAB\\**<*local administrator account name*>.</span></span>
    
4. <span data-ttu-id="e6fe3-180">Geben Sie im Feld **Kennwort** das Kennwort des lokalen Administratorkontos ein, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-180">In the **Password** box, enter the password of the local administrator account, and then select **OK**.</span></span>
    
5. <span data-ttu-id="e6fe3-181">Wenn Sie dazu aufgefordert werden, wählen Sie **Ja**aus.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-181">When prompted, select **Yes**.</span></span>
    
<span data-ttu-id="e6fe3-182">Erstellen Sie als nächstes ein Benutzerkonto in Active Directory, das beim Anmelden bei TESTLAB-Domänenmitgliedscomputern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-182">Next, create a user account in Active Directory that will be used when signing in to TESTLAB domain member computers.</span></span> <span data-ttu-id="e6fe3-183">Führen Sie diesen Befehl an einer Windows PowerShell Eingabeaufforderung auf Administratorebene aus.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-183">Run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
New-ADUser -SamAccountName User1 -AccountPassword (read-host "Set user password" -assecurestring) -name "User1" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```

<span data-ttu-id="e6fe3-184">Beachten Sie, dass Sie mit diesem Befehl aufgefordert werden, das Kennwort des Kontos "user1" anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-184">Note that this command prompts you to supply the User1 account password.</span></span> <span data-ttu-id="e6fe3-185">Dieses Konto wird für Remotedesktopverbindungen für alle TESTLAB-Domänenmitgliedscomputer verwendet, daher wählen Sie ein sicheres Kennwort aus.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-185">This account will be used for remote desktop connections for all TESTLAB domain member computers, so choose a strong password.</span></span> <span data-ttu-id="e6fe3-186">Zeichnen Sie das Kennwort des user1-Kontos auf, und speichern Sie es an einem sicheren Ort.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-186">Record the User1 account password and store it in a secured location.</span></span>
  
<span data-ttu-id="e6fe3-p120">Konfigurieren Sie als Nächstes das neue Konto „Benutzer1“ als Domänen-, Unternehmens- und Schemaadministrator aus. Führen Sie diesen Befehl an der Windows PowerShell-Eingabeaufforderung auf Administratorebene aus.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-p120">Next, configure the new User1 account as a domain, enterprise, and schema administrator. Run this command at the administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
$yourDomain="<your public domain>"
$domainName = "testlab."+$yourDomain
$userName="user1@" + $domainName
$userSID=(New-Object System.Security.Principal.NTAccount($userName)).Translate([System.Security.Principal.SecurityIdentifier]).Value
$groupNames=@("Domain Admins","Enterprise Admins","Schema Admins")
ForEach ($name in $groupNames) {Add-ADPrincipalGroupMembership -Identity $userSID -MemberOf (Get-ADGroup -Identity $name).SID.Value}
```

<span data-ttu-id="e6fe3-189">Schließen Sie die Remotedesktopsitzung mit DC1, und stellen Sie dann mit dem Konto „TESTLAB\\Benutzer1“ wieder eine Verbindung her.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-189">Close the Remote Desktop session with DC1 and then reconnect using the TESTLAB\\User1 account.</span></span>
  
<span data-ttu-id="e6fe3-190">Führen Sie als Nächstes den folgenden Befehl an einer Windows PowerShell-Eingabeaufforderung auf Administratorebene aus, um Datenverkehr für das Tool Ping zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-190">Next, to allow traffic for the Ping tool, run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
```

<span data-ttu-id="e6fe3-191">Die aktuelle Konfiguration sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="e6fe3-191">Your current configuration looks like this:</span></span>
  
![Schritt 1 der simulierten Unternehmensstandardkonfiguration](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase1.png)
  
#### <a name="step-2-configure-app1"></a><span data-ttu-id="e6fe3-193">Schritt 2: Konfigurieren von APP1</span><span class="sxs-lookup"><span data-stu-id="e6fe3-193">Step 2: Configure APP1</span></span>

<span data-ttu-id="e6fe3-194">In diesem Schritt erstellen und konfigurieren Sie APP1, ein Anwendungsserver, der zunächst Web- und Dateifreigabedienste bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-194">In this step, you create and configure APP1, which is an application server that initially provides web and file sharing services.</span></span>

<span data-ttu-id="e6fe3-195">Geben Sie zum Erstellen eines virtuellen Azure-Computers für APP1 den Namen Ihrer Ressourcengruppe ein, und führen Sie über die Eingabeaufforderung auf Ihrem lokalen Computer die nachfolgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-195">To create an Azure Virtual Machine for APP1, fill in the name of your resource group and run these commands at the  command prompt on your local computer.</span></span>
  
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

<span data-ttu-id="e6fe3-196">Im nächsten Schritt stellen Sie eine Verbindung mit dem virtuellen Computer APP1 mit dem Kontonamen und Kennwort des lokalen Administratorkontos von APP1 her und öffnen dann eine Windows PowerShell-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-196">Next, connect to the APP1 virtual machine using the APP1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="e6fe3-197">Wenn Sie die Namensauflösung und Netzwerkkommunikation zwischen APP1 und DC1 überprüfen möchten, führen Sie **ping dc1.testlab.**\<*your public domain name*> aus</span><span class="sxs-lookup"><span data-stu-id="e6fe3-197">To check name resolution and network communication between APP1 and DC1, run the **ping dc1.testlab.**\<*your public domain name*></span></span> <span data-ttu-id="e6fe3-198">und überprüfen Sie, ob vier Antworten vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-198">command and verify that there are four replies.</span></span>
  
<span data-ttu-id="e6fe3-199">Verknüpfen Sie als Nächstes unter Verwendung der folgenden Befehle an der Windows PowerShell-Eingabeaufforderung den virtuellen Computer APP1 mit der Domäne TESTLAB.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-199">Next, join the APP1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

<span data-ttu-id="e6fe3-200">Beachten Sie, dass Sie nach dem Ausführen des Befehls **Add-Computer** die \\ Anmeldeinformationen des TESTLAB user1-Domänenkontos angeben müssen.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-200">Note that you after you run the **Add-Computer** command, you must supply the TESTLAB\\User1 domain account credentials.</span></span>
  
<span data-ttu-id="e6fe3-201">Stellen Sie nach dem Neustart von APP1 eine Verbindung über das Konto „TESLAB\\Benutzer1“ damit her, und öffnen Sie dann eine Windows PowerShell-Eingabeaufforderung auf Administratorebene.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-201">After APP1 restarts, connect to it using the TESTLAB\\User1 account, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="e6fe3-202">Im nächsten Schritt richten Sie APP1 mit dem folgenden Befehl in der Windows PowerShell-Eingabeaufforderung auf Administratorebene auf APP1 als Webserver ein.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-202">Next, make APP1 a web server with this command at an administrator-level Windows PowerShell command prompt on APP1.</span></span>
  
```powershell
Install-WindowsFeature Web-WebServer -IncludeManagementTools
```

<span data-ttu-id="e6fe3-203">Erstellen Sie als Nächstes einen freigegebenen Ordner und eine Textdatei innerhalb des Ordners auf APP1 mit diesen PowerShell-Befehlen.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-203">Next, create a shared folder and a text file within the folder on APP1 with these PowerShell commands.</span></span>
  
```powershell
New-Item -path c:\files -type directory
Write-Output "This is a shared file." | out-file c:\files\example.txt
New-SmbShare -name files -path c:\files -changeaccess TESTLAB\User1
```

<span data-ttu-id="e6fe3-204">Die aktuelle Konfiguration sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="e6fe3-204">Your current configuration looks like this:</span></span>
  
![Schritt 2 der simulierten Unternehmensstandardkonfiguration](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase2.png)
  
#### <a name="step-3-configure-client1"></a><span data-ttu-id="e6fe3-206">Schritt 3: Konfigurieren von CLIENT1</span><span class="sxs-lookup"><span data-stu-id="e6fe3-206">Step 3: Configure CLIENT1</span></span>

<span data-ttu-id="e6fe3-207">In diesem Schritt wird CLIENT1 erstellt und konfiguriert, der als typischer Laptop, als Tablet oder als Desktopcomputer im Intranet fungiert.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-207">In this step, you create and configure CLIENT1, which acts as a typical laptop, tablet, or desktop computer on the intranet.</span></span>

> [!NOTE]  
> <span data-ttu-id="e6fe3-p122">Der folgende Befehlssatz erstellt CLIENT1 unter Windows Server 2016 Datacenter. Er gilt für alle Arten von Azure-Abonnements. Wenn Sie über ein Visual Studio-basiertes Azure-Abonnement verfügen, können Sie CLIENT1 unter Windows 10 mit dem [Azure-Portal](https://portal.azure.com) erstellen.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-p122">The following command set creates CLIENT1 running Windows Server 2016 Datacenter, which can be done for all types of Azure subscriptions. If you have a Visual Studio-based Azure subscription, you can create CLIENT1 running Windows 10 with the [Azure portal](https://portal.azure.com).</span></span>
  
<span data-ttu-id="e6fe3-210">Geben Sie zum Erstellen eines virtuellen Azure-Computers für CLIENT1 den Namen Ihrer Ressourcengruppe ein, und führen Sie diese Befehle an der Eingabeaufforderung auf dem lokalen Computer aus.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-210">To create an Azure Virtual Machine for CLIENT1, fill in the name of your resource group and run these commands at the command prompt on your local computer.</span></span>
  
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

<span data-ttu-id="e6fe3-211">Im nächsten Schritt stellen Sie eine Verbindung mit dem virtuellen Computer CLIENT1 mit dem Kontonamen und Kennwort des lokalen Administratorkontos von CLIENT1 her und öffnen dann eine Windows PowerShell-Eingabeaufforderung auf Administratorebene.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-211">Next, connect to the CLIENT1 virtual machine using the CLIENT1 local administrator account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="e6fe3-212">Wenn Sie die Namensauflösung und Netzwerkkommunikation zwischen CLIENT1 und DC1 überprüfen möchten, führen Sie **ping dc1.testlab.**\<*your public domain name*></span><span class="sxs-lookup"><span data-stu-id="e6fe3-212">To check name resolution and network communication between CLIENT1 and DC1, run the **ping dc1.testlab.**\<*your public domain name*></span></span> <span data-ttu-id="e6fe3-213">an einer Windows PowerShell Kommandozeile aus und stellen Sie sicher, dass vier Antworten vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-213">command at a Windows PowerShell command prompt and verify that there are four replies.</span></span>
  
<span data-ttu-id="e6fe3-214">Verknüpfen Sie als Nächstes unter Verwendung der folgenden Befehle an der Windows PowerShell-Eingabeaufforderung den virtuellen Computer CLIENT1 mit der Domäne TESTLAB.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-214">Next, join the CLIENT1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab." + $yourDomain)
Restart-Computer
```

<span data-ttu-id="e6fe3-215">Beachten Sie, dass Sie nach der Ausführung des Befehls **Add-Computer** die Anmeldeinformationen für das Domänenkonto „TESTLAB\\Benutzer1“ eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-215">Note that you must supply your TESTLAB\\User1 domain account credentials after running the **Add-Computer** command.</span></span>
  
<span data-ttu-id="e6fe3-216">Stellen Sie nach dem Neustart von CLIENT1 eine Verbindung über den Kontonamen und das Kennwort von „TESTLAB\\Benutzer1“ damit her, und öffnen Sie dann eine Windows PowerShell-Eingabeaufforderung auf Administratorebene.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-216">After CLIENT1 restarts, connect to it using the TESTLAB\\User1 account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="e6fe3-217">Überprüfen Sie im nächsten Schritt, ob Sie von CLIENT1 aus auf Web- und Dateifreigaberessourcen auf APP1 zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-217">Next, verify that you can access web and file share resources on APP1 from CLIENT1.</span></span>
  
1. <span data-ttu-id="e6fe3-218">Klicken Sie im Server-Manager im Strukturbereich auf **lokaler Server**.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-218">In Server Manager, in the tree pane, select **Local Server**.</span></span>
    
2. <span data-ttu-id="e6fe3-219">Wählen Sie in **Eigenschaften für CLIENT1**neben **IE Enhanced Security Configuration**die Option **on** aus.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-219">In **Properties for CLIENT1**, select **On** next to **IE Enhanced Security Configuration**.</span></span>
    
3. <span data-ttu-id="e6fe3-220">Wählen Sie unter **Internet Explorer Verstärkte Sicherheitskonfiguration**für **Administratoren** und **Benutzer**die Option **aus** , und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-220">In **Internet Explorer Enhanced Security Configuration**, select **Off** for **Administrators** and **Users**, and then select **OK**.</span></span>
    
4. <span data-ttu-id="e6fe3-221">Wählen Sie auf dem Start Bildschirm **Internet Explorer**aus, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-221">From the Start screen, select **Internet Explorer**, and then select **OK**.</span></span>
    
5. <span data-ttu-id="e6fe3-222">Geben Sie in der Adressleiste **http<span>://</span>App1. testab.** ein \<*your public domain name*> **/** , und drücken Sie dann die **Eingabe**Taste.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-222">In the address bar, enter **http<span>://</span>app1.testab.**\<*your public domain name*>**/**, and then press **Enter**.</span></span> <span data-ttu-id="e6fe3-223">Nun sollte die standardmäßige Internetinformationsdienste-Webseite für APP1 angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-223">You should see the default Internet Information Services web page for APP1.</span></span>
    
6. <span data-ttu-id="e6fe3-224">Wählen Sie auf der Desktop-Taskleiste das Symboldatei-Explorer aus.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-224">On the desktop taskbar, select the File Explorer icon.</span></span>
    
7. <span data-ttu-id="e6fe3-225">Geben Sie in der Adressleiste \*\* \\ \\ App1- \\ Dateien\*\*ein, und drücken Sie dann die **Eingabe**Taste.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-225">In the address bar, enter **\\\\app1\\Files**, and then press **Enter**.</span></span> <span data-ttu-id="e6fe3-226">Es sollte ein Ordnerfenster mit dem Inhalt des freigegebenen Ordners Dateien angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-226">You should see a folder window with the contents of the Files shared folder.</span></span>
    
8. <span data-ttu-id="e6fe3-p126">Doppelklicken Sie im Fenster des freigegebenen Ordners **Files** auf die Datei **Example.txt**. Nun sollte der Inhalt der Datei „Example.txt“ angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-p126">In the **Files** shared folder window, double-click the **Example.txt** file. You should see the contents of the Example.txt file.</span></span>
    
9. <span data-ttu-id="e6fe3-229">Schließen Sie das Fenster **example.txt - Editor** und das Fenster des freigegebenen Ordners **Files**.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-229">Close the **example.txt - Notepad** and the **Files** shared folder windows.</span></span>
    
<span data-ttu-id="e6fe3-230">Die aktuelle Konfiguration sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="e6fe3-230">Your current configuration looks like this:</span></span>
  
![Schritt 3 der simulierten Unternehmensstandardkonfiguration](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

## <a name="phase-2-create-your-microsoft-365-e5-subscription"></a><span data-ttu-id="e6fe3-232">Phase 2: Erstellen Ihres Abonnements für Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="e6fe3-232">Phase 2: Create your Microsoft 365 E5 subscription</span></span>

<span data-ttu-id="e6fe3-p127">In dieser Phase erstellen Sie ein neues Abonnement für Microsoft 365 E5, das einen neuen Azure AD-Mandanten verwendet, der von Ihrem Produktionsabonnement getrennt ist. Dies können Sie auf zwei Arten tun:</span><span class="sxs-lookup"><span data-stu-id="e6fe3-p127">In this phase, you create a new Microsoft 365 E5 subscription that uses a new Azure AD tenant, one that is separate from your production subscription. You can do this in two ways:</span></span>

- <span data-ttu-id="e6fe3-235">Verwenden Sie ein Testabonnement von Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-235">Use a trial subscription of Microsoft 365 E5.</span></span>

  <span data-ttu-id="e6fe3-p128">Das Testabonnement von Microsoft 365 E5 gilt für 30 Tage, die problemlos auf 60 Tage verlängert werden können. Wenn das Testabonnement abläuft, müssen Sie entweder zu einem kostenpflichtigen Abonnement wechseln oder eine neue Testversion erstellen. Durch Erstellen neuer Testabonnements müssen Sie Ihre Konfiguration verlassen, was im Hintergrund zu komplexen Szenarien führen kann.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-p128">The Microsoft 365 E5 trial subscription is 30 days, which can be easily extended to 60 days. When the trial subscription expires, you must either convert it to a paid subscription or create a new trial subscription. Creating new trial subscriptions means you will leave your configuration, which could include complex scenarios, behind.</span></span>  

- <span data-ttu-id="e6fe3-239">Verwenden Sie ein separates Produktionsabonnement von Microsoft 365 E5 mit einer kleinen Anzahl von Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-239">Use a separate production subscription of Microsoft 365 E5 with a small number of licenses.</span></span>

  <span data-ttu-id="e6fe3-240">Dies ist ein zusätzlicher Aufwand, stellt jedoch sicher, dass Sie über eine funktionierende Testumgebung verfügen, die nicht abläuft. darin können Sie Features, Konfigurationen und Szenarien testen.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-240">This is an additional cost, but ensures that you have a working test environment that doesn't expire; in it, you can try features, configurations, and scenarios.</span></span> <span data-ttu-id="e6fe3-241">Sie können die gleiche Testumgebung langfristig für Machbarkeitsstudien, Demonstrationen an Peers und für die Verwaltung sowie für die Entwicklung und das Testen von Anwendungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-241">You can use the same test environment over the long term for proofs of concept, demonstration to peers and management, and application development and testing.</span></span> <span data-ttu-id="e6fe3-242">Dies ist die empfohlene Methode.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-242">This is the recommended method.</span></span>

### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="e6fe3-243">Registrieren für ein Office 365 E5-Testabonnement</span><span class="sxs-lookup"><span data-stu-id="e6fe3-243">Sign up for an Office 365 E5 trial subscription</span></span>

<span data-ttu-id="e6fe3-244">Stellen Sie über das Azure-Portal mit dem corp\user1 an-Konto eine Verbindung mit CLIENT1 her.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-244">From the Azure portal, connect to CLIENT1 with the CORP\User1 account.</span></span>

<span data-ttu-id="e6fe3-245">Wenn Sie ein neues Office 365 E5-Testabonnement erstellen möchten, führen Sie die Anweisungen in [Phase 1](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-microsoft-365-e5-subscription) der Testumgebungsanleitung zur einfachen Standardkonfiguration aus.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-245">To create a new Office 365 E5 trial subscription, perform the instructions in [Phase 1](lightweight-base-configuration-microsoft-365-enterprise.md#phase-1-create-your-microsoft-365-e5-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

<span data-ttu-id="e6fe3-246">Wenn Sie Ihr neues Office 365 E5-Testabonnement konfigurieren möchten, führen Sie die Anweisungen in [Phase 2](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription) der Testumgebungsanleitung zur einfachen Standardkonfiguration aus.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-246">To configure your new Office 365 E5 trial subscription, perform the instructions in [Phase 2](lightweight-base-configuration-microsoft-365-enterprise.md#phase-2-configure-your-office-365-trial-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

#### <a name="using-an-office-365-e5-test-environment"></a><span data-ttu-id="e6fe3-247">Verwenden einer Office 365 E5-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="e6fe3-247">Using an Office 365 E5 test environment</span></span>

<span data-ttu-id="e6fe3-248">Wenn Sie nur eine Office 365 Testumgebung benötigen, müssen Sie den Rest dieses Artikels nicht lesen.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-248">If you need only an Office 365 test environment, you do not need to read the rest of this article.</span></span>

<span data-ttu-id="e6fe3-249">Weitere testumgebungsanleitungen, die sowohl für Microsoft 365 als auch für Office 365 gelten, finden Sie unter [Microsoft 365 for Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="e6fe3-249">For additional Test Lab Guides that apply to both Microsoft 365 and Office 365, see [Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>

### <a name="add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="e6fe3-250">Hinzufügen eines Testabonnements für Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="e6fe3-250">Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="e6fe3-251">Wenn Sie ein Microsoft 365 E5-Testabonnement hinzufügen und ihre Benutzerkonten mit Lizenzen konfigurieren möchten, führen Sie die Anweisungen in [Phase 3](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) des Test Umgebungs Handbuchs für die Lightweight Base Configuration aus.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-251">To add a Microsoft 365 E5 trial subscription and configure your users accounts with licenses, perform the instructions in [Phase 3](lightweight-base-configuration-microsoft-365-enterprise.md#phase-3-add-a-microsoft-365-e5-trial-subscription) of the lightweight base configuration Test Lab Guide.</span></span>

  
## <a name="results"></a><span data-ttu-id="e6fe3-252">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="e6fe3-252">Results</span></span>

<span data-ttu-id="e6fe3-253">Ihre Testumgebung verfügt nun über Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e6fe3-253">Your test environment now has:</span></span>
  
- <span data-ttu-id="e6fe3-254">Ein Testabonnement für Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-254">Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="e6fe3-255">Alle entsprechenden Benutzerkonten sind für die Verwendung von Microsoft 365 E5 aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-255">All your appropriate user accounts are enabled to use Microsoft 365 E5.</span></span>
- <span data-ttu-id="e6fe3-256">Ein simuliertes und vereinfachtes Intranet.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-256">A simulated and simplified intranet.</span></span>
    
<span data-ttu-id="e6fe3-257">Die endgültige Konfiguration sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="e6fe3-257">Your final configuration looks like this:</span></span>
  
![Phase 2 der simulierten Unternehmensstandardkonfiguration](../media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)
  
<span data-ttu-id="e6fe3-259">Sie können nun mit weiteren Features von [Microsoft 365 for Enterprise](https://www.microsoft.com/microsoft-365/enterprise)experimentieren.</span><span class="sxs-lookup"><span data-stu-id="e6fe3-259">You are now ready to experiment with additional features of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="e6fe3-260">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="e6fe3-260">Next steps</span></span>

<span data-ttu-id="e6fe3-261">Sehen Sie sich diese zusätzlichen Testumgebungsanleitungen an:</span><span class="sxs-lookup"><span data-stu-id="e6fe3-261">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="e6fe3-262">Identität</span><span class="sxs-lookup"><span data-stu-id="e6fe3-262">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="e6fe3-263">Verwaltung mobiler Geräte</span><span class="sxs-lookup"><span data-stu-id="e6fe3-263">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="e6fe3-264">Schutz von Daten</span><span class="sxs-lookup"><span data-stu-id="e6fe3-264">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a><span data-ttu-id="e6fe3-265">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6fe3-265">See also</span></span>

[<span data-ttu-id="e6fe3-266">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e6fe3-266">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="e6fe3-267">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e6fe3-267">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="e6fe3-268">Dokumentation zu Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="e6fe3-268">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
