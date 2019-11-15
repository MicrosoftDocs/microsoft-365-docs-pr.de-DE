---
title: Simulierte Unternehmensstandardkonfiguration für Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Verwenden Sie diese Testumgebungsanleitung, um eine Testumgebung mit einem simulierten Unternehmen für Microsoft 365 Enterprise zu erstellen.
ms.openlocfilehash: 5faa6857de42049cbcfc237e3e617de294794530
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2019
ms.locfileid: "38640387"
---
# <a name="the-simulated-enterprise-base-configuration"></a><span data-ttu-id="3ac63-103">Die simulierte Unternehmensstandardkonfiguration</span><span class="sxs-lookup"><span data-stu-id="3ac63-103">The simulated enterprise base configuration</span></span>

<span data-ttu-id="3ac63-104">Dieser Artikel bietet Schrittanleitungen zum Erstellen einer vereinfachten Umgebung für Microsoft 365 Enterprise, die Folgendes umfasst:</span><span class="sxs-lookup"><span data-stu-id="3ac63-104">This article provides you with step-by-step instructions to create a simplified environment for Microsoft 365 Enterprise that includes:</span></span>

- <span data-ttu-id="3ac63-105">Eine Testversion oder ein kostenpflichtiges Abonnement für Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="3ac63-105">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="3ac63-106">Ein vereinfachtes Unternehmensintranet mit Internetzugriff, das aus drei virtuellen Computern in einem virtuellen Azure-Netzwerk (DC1, APP1 und CLIENT1) besteht.</span><span class="sxs-lookup"><span data-stu-id="3ac63-106">A simplified organization intranet connected to the Internet, consisting of three virtual machines on an Azure virtual network (DC1, APP1, and CLIENT1).</span></span>
 
![Die simulierte Unternehmensstandardkonfiguration](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="3ac63-108">Sie können die resultierende Umgebung verwenden, um die Features und Funktionen von [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) zu testen, mit zusätzlichen [Testumgebungsanleitungen](m365-enterprise-test-lab-guides.md) oder selbst.</span><span class="sxs-lookup"><span data-stu-id="3ac63-108">You can use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) with additional [Test Lab Guides](m365-enterprise-test-lab-guides.md) or on your own.</span></span>

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="3ac63-110">Klicken Sie [hier](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3ac63-110">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-create-a-simulated-intranet"></a><span data-ttu-id="3ac63-111">Phase 1: Erstellen eines simulierten Intranets</span><span class="sxs-lookup"><span data-stu-id="3ac63-111">Phase 1: Create a simulated intranet</span></span>

<span data-ttu-id="3ac63-112">In dieser Phase erstellen Sie ein simuliertes Intranet in den Azure-Infrastrukturdiensten, das einen Active Directory Domain Services(AD DS)-Domänencontroller, einen Anwendungsserver und einen Clientcomputer umfasst.</span><span class="sxs-lookup"><span data-stu-id="3ac63-112">In this phase, you build a simulated intranet in Azure infrastructure services that includes an Active Directory Domain Services (AD DS) domain controller, an application server, and a client computer.</span></span> 

<span data-ttu-id="3ac63-113">Sie verwenden diese Computer in zusätzlichen [Microsoft 365 Enterprise-Testumgebungsanleitungen](m365-enterprise-test-lab-guides.md), um Hybrid-Identitäten und andere Funktionen zu konfigurieren und zu demonstrieren.</span><span class="sxs-lookup"><span data-stu-id="3ac63-113">You'll use these computers in additional [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) to configure and demonstrate hybrid identity and other capabilities.</span></span>

### <a name="method-1-build-your-simulated-intranet-with-an-azure-resource-manager-template"></a><span data-ttu-id="3ac63-114">Methode 1: Erstellen eines simulierten Intranets mit einer Azure Ressourcenmanager-Vorlage</span><span class="sxs-lookup"><span data-stu-id="3ac63-114">Method 1: Build your simulated intranet with an Azure Resource Manager template</span></span>

<span data-ttu-id="3ac63-p101">Bei dieser Methode verwenden Sie eine Azure Resource Manager-Vorlage (ARM), um das simulierte Intranet auszubauen. ARM-Vorlagen enthalten alle Anweisungen zum Erstellen der Azure-Netzwerkinfrastruktur, die virtuellen Computer und die dazugehörige Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="3ac63-p101">In this method, you use an Azure Resource Manager (ARM) template to build out the simulated intranet. ARM templates contain all of the instructions to create the Azure networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="3ac63-117">Lesen Sie vor der Bereitstellung der Vorlage die [Infodatei auf der Vorlagenseite](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) und halten Sie folgende Informationen bereit:</span><span class="sxs-lookup"><span data-stu-id="3ac63-117">Prior to deploying the template, read through the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) and have the following information ready:</span></span>

- <span data-ttu-id="3ac63-p102">Der öffentliche DNS-Domänenname Ihrer Testumgebung (Testlabor.\<Ihre öffentlichen Domäne>). Sie müssen diesen Namen in das Feld **Domänenname** der Seite **Benutzerdefinierte Bereitstellung** einegben.</span><span class="sxs-lookup"><span data-stu-id="3ac63-p102">The public DNS domain name of your test environment (testlab.\<your public domain>). You’ll need to enter this name in the **Domain Name field** of the **Custom deployment** page.</span></span>
- <span data-ttu-id="3ac63-p103">Ein DNS-Präfix für die URLs der öffentlichen IP-Adressen Ihrer virtueller Computer. Sie müssen diese Bezeichnung in das Feld **DNS-Präfix** der Seite **Benutzerdefinierte Bereitstellung** eingeben.</span><span class="sxs-lookup"><span data-stu-id="3ac63-p103">A DNS label prefix for the URLs of the public IP addresses of your virtual machines. You’ll need to enter this label in the **Dns Label Prefix** field of the **Custom deployment** page.</span></span>

<span data-ttu-id="3ac63-122">Klicken Sie nach dem Lesen der Anweisungen auf **In Azure bereitstellen** in der [Infodatei auf der Vorlagenseite](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems), um loszulegen.</span><span class="sxs-lookup"><span data-stu-id="3ac63-122">After reading through the instructions, click **Deploy to Azure** on the [template README page](https://github.com/maxskunkworks/TLG/tree/master/tlg-base-config_3-vm.m365-ems) to get started.</span></span>

>[!Note]
><span data-ttu-id="3ac63-123">Das anhand der ARM-Vorlage erstellte simulierte Intranet erfordert ein kostenpflichtiges Azure-Abonnement.</span><span class="sxs-lookup"><span data-stu-id="3ac63-123">The simulated intranet built by the ARM template requires a paid Azure subscription.</span></span>
>

<span data-ttu-id="3ac63-124">Hier finden Sie Ihre Konfiguration nach Abschluss der Vorlage.</span><span class="sxs-lookup"><span data-stu-id="3ac63-124">Here is your configuration after the template is complete.</span></span>

![Das simulierte Intranet in den Azure-Infrastrukturdiensten](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)

### <a name="method-2-build-your-simulated-intranet-with-azure-powershell"></a><span data-ttu-id="3ac63-126">Methode 2: Erstellen Ihres simulierten Intranets mit Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ac63-126">Method 2: Build your simulated intranet with Azure PowerShell</span></span>

<span data-ttu-id="3ac63-127">Bei dieser Methode verwenden Sie Windows PowerShell und das Azure PowerShell-Modul zum Erstellen der Netzwerkinfrastruktur, der virtuellen Computer und ihrer Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="3ac63-127">In this method, you use Windows PowerShell and the Azure PowerShell module to build out the networking infrastructure, the virtual machines, and their configuration.</span></span>

<span data-ttu-id="3ac63-p104">Verwenden Sie diese Methode, wenn Sie Erfahrungen mit dem Erstellen von Elementen der Azure-Infrastruktur für jeden einzelnen Schritt mit PowerShell sammeln möchten. Sie können dann die PowerShell-Befehlsblöcke für eine eigene Bereitstellung von anderen virtuellen Computern in Azure anpassen.</span><span class="sxs-lookup"><span data-stu-id="3ac63-p104">Use this method if you want to get experience creating elements of Azure infrastructure one step at a time with PowerShell. You can then customize the PowerShell command blocks for your own deployment of other virtual machines in Azure.</span></span>

#### <a name="step-1-create-dc1"></a><span data-ttu-id="3ac63-130">Phase 1: Erstellen von DC1</span><span class="sxs-lookup"><span data-stu-id="3ac63-130">Step 1: Create DC1</span></span>

<span data-ttu-id="3ac63-131">In dieser Phase erstellen wir ein virtuelles Azure-Netzwerk und fügen DC1 hinzu, einen virtuellen Computer, der ein Domänencontroller für eine AD DS-Domäne ist.</span><span class="sxs-lookup"><span data-stu-id="3ac63-131">In this step, we create an Azure virtual network and add DC1, a virtual machine that is a domain controller for an AD DS domain.</span></span>

<span data-ttu-id="3ac63-132">Starten Sie zunächst eine Windows PowerShell-Eingabeaufforderung auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="3ac63-132">First, start a Windows PowerShell command prompt on your local computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3ac63-p105">In den folgenden Befehlssätzen wird die aktuelle Version von Azure PowerShell verwendet. Informationen dazu finden Sie unter [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span><span class="sxs-lookup"><span data-stu-id="3ac63-p105">The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> 
  
<span data-ttu-id="3ac63-135">Melden Sie sich mit dem folgenden Befehl bei Ihrem Azure-Konto an.</span><span class="sxs-lookup"><span data-stu-id="3ac63-135">Sign in to your Azure account with the following command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="3ac63-136">Rufen Sie den Namen Ihres Abonnements mithilfe des folgenden Befehls ab.</span><span class="sxs-lookup"><span data-stu-id="3ac63-136">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="3ac63-p106">Legen Sie Ihr Azure-Abonnement fest. Ersetzen Sie alles innerhalb der Anführungszeichen, einschließlich der Zeichen „<“ und „>“, durch den entsprechenden Namen.</span><span class="sxs-lookup"><span data-stu-id="3ac63-p106">Set your Azure subscription. Replace everything within the quotes, including the < and > characters, with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="3ac63-p107">Im nächsten Schritt wird eine neue Ressourcengruppe für Ihr simuliertes Unternehmenstestlabor erstellt. Verwenden Sie zum Ermitteln eines eindeutigen Ressourcengruppennamens diesen Befehl, mit dem die vorhandenen Ressourcengruppen aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3ac63-p107">Next, create a new resource group for your simulated enterprise test lab. To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="3ac63-p108">Erstellen Sie die neue Ressourcengruppe mit diesen Befehlen. Ersetzen Sie alles innerhalb der Anführungszeichen, einschließlich der Zeichen „<“ und „>“, durch die entsprechenden Namen.</span><span class="sxs-lookup"><span data-stu-id="3ac63-p108">Create your new resource group with these commands. Replace everything within the quotes, including the < and > characters, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="3ac63-p109">Als Nächstes erstellen Sie das virtuelle Netzwerk „TestLab“, in dem das Corpnet-Subnetz der simulierten Unternehmensumgebung gehostet und mit einer Netzwerksicherheitsgruppe geschützt wird. Tragen Sie den Namen Ihrer Ressourcengruppe ein, und führen Sie diese Befehle an der PowerShell-Eingabeaufforderung auf dem lokalen Computer aus.</span><span class="sxs-lookup"><span data-stu-id="3ac63-p109">Next, you create the TestLab virtual network that will host the Corpnet subnet of the simulated enterprise environment and protect it with a network security group. Fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
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

<span data-ttu-id="3ac63-145">Als Nächstes erstellen Sie den virtuellen DC1-Computer und konfigurieren ihn als einen Domänencontroller für **testlab.**\<Ihre öffentliche Domäne> AD DS-Domäne und einen DNS-Server für die virtuellen Computer des virtuellen Netzwerks TestLab.</span><span class="sxs-lookup"><span data-stu-id="3ac63-145">Next, you create the DC1 virtual machine and configure it as a domain controller for the **testlab.**\<your public domain> AD DS domain and a DNS server for the virtual machines of the TestLab virtual network.</span></span> <span data-ttu-id="3ac63-146">Wenn der Name der öffentlichen Domäne **<span>contoso</span>.com** ist, ist die virtuelle Maschine DC1 ein Domänencontroller für die Domäne **<span>testlab</span>.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="3ac63-146">For example, if your public domain name is **<span>contoso</span>.com**, the DC1 virtual machine will be a domain controller for the **<span>testlab</span>.contoso.com** domain.</span></span>
  
<span data-ttu-id="3ac63-147">Geben Sie zum Erstellen eines virtuellen Azure-Computers für DC1 den Namen Ihrer Ressourcengruppe ein, und führen Sie über die PowerShell-Eingabeaufforderung auf Ihrem lokalen Computer die nachfolgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="3ac63-147">To create an Azure virtual machine for DC1, fill in the name of your resource group and run these commands at the PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name DC1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name DC1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress 10.0.0.4
$vm=New-AzVMConfig -VMName DC1 -VMSize Standard_A1
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

<span data-ttu-id="3ac63-p111">Sie werden nach einem Benutzernamen und Kennwort für das lokale Administratorkonto auf DC1 gefragt. Verwenden Sie ein sicheres Kennwort, und notieren Sie den Namen und das Kennwort an einem sicheren Ort.</span><span class="sxs-lookup"><span data-stu-id="3ac63-p111">You will be prompted for a user name and password for the local administrator account on DC1. Use a strong password and record both the name and password in a secure location.</span></span>
  
<span data-ttu-id="3ac63-150">Stellen Sie dann eine Verbindung mit dem virtuellen Computer DC1 her.</span><span class="sxs-lookup"><span data-stu-id="3ac63-150">Next, connect to the DC1 virtual machine.</span></span>
  
1. <span data-ttu-id="3ac63-151">Klicken Sie im [Azure-Portal](https://portal.azure.com) auf **Ressourcengruppen >** [Name der neuen Ressourcengruppe] **> DC1 > Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="3ac63-151">In the [Azure portal](https://portal.azure.com), click **Resource Groups >** [the name of your new resource group] **> DC1 > Connect**.</span></span>
    
2. <span data-ttu-id="3ac63-p112">Klicken Sie im Bereich „Öffnen“ auf  **RDP-Datei herunterladen**. Öffnen Sie die Datei „DC1.rdp“, die heruntergeladen wird, und klicken Sie dann auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="3ac63-p112">In the open pane, click **Download RDP file**. Open the DC1.rdp file that is downloaded, and then click **Connect**.</span></span>
    
3. <span data-ttu-id="3ac63-154">Geben Sie den Namen des lokalen DC1-Administratorkontos an:</span><span class="sxs-lookup"><span data-stu-id="3ac63-154">Specify the DC1 local administrator account name:</span></span>
    
   - <span data-ttu-id="3ac63-155">Für Windows 7:</span><span class="sxs-lookup"><span data-stu-id="3ac63-155">For Windows 7:</span></span>
    
     <span data-ttu-id="3ac63-p113">Klicken Sie im Dialogfeld **Windows-Sicherheit** auf **Anderes Konto verwenden**. Geben Sie unter **Benutzername** den Namen **DC1\\**[Kontoname des lokalen Administrators] ein.</span><span class="sxs-lookup"><span data-stu-id="3ac63-p113">In the **Windows Security** dialog box, click **Use another account**. In **User name**, type **DC1\\**[Local administrator account name].</span></span>
    
   - <span data-ttu-id="3ac63-158">Für Windows 8 oder Windows 10:</span><span class="sxs-lookup"><span data-stu-id="3ac63-158">For Windows 8 or Windows 10:</span></span>
    
     <span data-ttu-id="3ac63-p114">Klicken Sie im Dialogfeld **Windows-Sicherheit** auf **Weitere Optionen**, und klicken Sie dann auf **Anderes Konto verwenden**. Geben Sie unter **Benutzername** den Namen **DC1\\**[Kontoname des lokalen Administrators] ein.</span><span class="sxs-lookup"><span data-stu-id="3ac63-p114">In the **Windows Security** dialog box, click **More choices**, and then click **Use a different account**. In **User name**, type **DC1\\**[Local administrator account name].</span></span>
    
4. <span data-ttu-id="3ac63-161">Geben Sie unter **Kennwort** das Kennwort des lokalen Administratorkontos ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3ac63-161">In **Password**, type the password of the local administrator account, and then click **OK**.</span></span>
    
5. <span data-ttu-id="3ac63-162">Klicken Sie auf **Ja**, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="3ac63-162">When prompted, click **Yes**.</span></span>
    
<span data-ttu-id="3ac63-163">Im nächsten Schritt führen Sie diesen Befehl über eine Windows PowerShell-Eingabeaufforderung mit Administratorrechten auf DC1 aus, um ein zusätzliches Datenlaufwerk als neues Volume mit dem Laufwerkbuchstaben „F:" hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="3ac63-163">Next, add an extra data disk as a new volume with the drive letter F: with this command at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="3ac63-p115">Konfigurieren Sie als Nächstes DC1 als Domänencontroller und DNS-Server für die Domäne **testlab.**\<Ihr öffentlicher Domänenname>. Geben Sie Ihren öffentlichen Domänennamen an, entfernen Sie die Zeichen \< und „>“, und führen Sie die folgenden Befehle an einer Windows PowerShell-Eingabeaufforderung auf Administratorebene auf DC1 aus.</span><span class="sxs-lookup"><span data-stu-id="3ac63-p115">Next, configure DC1 as a domain controller and DNS server for the **testlab.**\<your public domain> domain. Specify your public domain name, remove the \< and > characters, and then run these commands at an administrator-level Windows PowerShell command prompt on DC1.</span></span>
  
```powershell
$yourDomain="<your public domain>"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSForest -DomainName testlab.$yourDomain -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs"
```
<span data-ttu-id="3ac63-p116">Sie müssen ein Administratorkennwort für den abgesicherten Modus angeben. Bewahren Sie das Kennwort an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="3ac63-p116">You will need to specify a safe mode administrator password. Store this password in a secure location.</span></span>
  
<span data-ttu-id="3ac63-168">Beachten Sie, dass der Abschluss dieser Befehle ein paar Minuten in Anspruch nehmen kann.</span><span class="sxs-lookup"><span data-stu-id="3ac63-168">Note that these commands can take a few minutes to complete.</span></span>
  
<span data-ttu-id="3ac63-169">Stellen Sie nach dem Neustart von DC1 wieder eine Verbindung zum virtuellen DC1-Computer her.</span><span class="sxs-lookup"><span data-stu-id="3ac63-169">After DC1 restarts, reconnect to the DC1 virtual machine.</span></span>
  
1. <span data-ttu-id="3ac63-170">Klicken Sie im [Azure-Portal](https://portal.azure.com) auf **Ressourcengruppen >** [Ihre Ressourcengruppe] **> DC1 > Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="3ac63-170">In the [Azure portal](https://portal.azure.com), click **Resource Groups >** [your resource group name] **> DC1 > Connect**.</span></span>
    
2. <span data-ttu-id="3ac63-171">Führen Sie die Datei „DC1.rdp“ aus, die heruntergeladen wurde, und klicken Sie dann auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="3ac63-171">Run the DC1.rdp file that is downloaded, and then click **Connect**.</span></span>
    
3. <span data-ttu-id="3ac63-p117">Klicken Sie unter **Windows-Sicherheit** auf **Anderes Konto verwenden**. Geben Sie unter **Benutzername** den Namen **TESTLAB\\**[Kontoname des lokalen Administrators] ein.</span><span class="sxs-lookup"><span data-stu-id="3ac63-p117">In **Windows Security**, click **Use another account**. In **User name**, type **TESTLAB\\**[Local administrator account name].</span></span>
    
4. <span data-ttu-id="3ac63-174">Geben Sie unter **Kennwort** das Kennwort des lokalen Administratorkontos ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3ac63-174">In **Password**, type the password of the local administrator account, and then click **OK**.</span></span>
    
5. <span data-ttu-id="3ac63-175">Klicken Sie auf **Ja**, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="3ac63-175">When prompted, click **Yes**.</span></span>
    
<span data-ttu-id="3ac63-p118">Im nächsten Schritt erstellen Sie ein Benutzerkonto in Active Directory, das bei der Anmeldung an Mitgliedscomputern der Domäne TESTLAB verwendet wird. Führen Sie diesen Befehl an einer Windows PowerShell-Eingabeaufforderung auf Administratorebene aus.</span><span class="sxs-lookup"><span data-stu-id="3ac63-p118">Next, create a user account in Active Directory that will be used when logging in to TESTLAB domain member computers. Run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
New-ADUser -SamAccountName User1 -AccountPassword (read-host "Set user password" -assecurestring) -name "User1" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```

<span data-ttu-id="3ac63-p119">Beachten Sie, dass Sie von dem Befehl aufgefordert werden, das Kennwort des Kontos „Benutzer1“ anzugeben. Da dieses Konto für Remotedesktopverbindungen für alle Mitgliedscomputer der Domäne TESTLAB verwendet wird, sollten Sie ein sicheres Kennwort wählen. Notieren Sie das Kennwort des Kontos „Benutzer1“, und bewahren Sie es an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="3ac63-p119">Note that this command prompts you to supply the User1 account password. Because this account will be used for remote desktop connections for all TESTLAB domain member computers, choose a strong password. Record the User1 account password and store it in a secured location.</span></span>
  
<span data-ttu-id="3ac63-p120">Konfigurieren Sie als Nächstes das neue Konto „Benutzer1“ als Domänen-, Unternehmens- und Schemaadministrator aus. Führen Sie diesen Befehl an der Windows PowerShell-Eingabeaufforderung auf Administratorebene aus.</span><span class="sxs-lookup"><span data-stu-id="3ac63-p120">Next, configure the new User1 account as a domain, enterprise, and schema administrator. Run this command at the administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
$yourDomain="<your public domain>"
$domainName = "testlab"+$yourDomain
$userName="user1@" + $domainName
$userSID=(New-Object System.Security.Principal.NTAccount($userName)).Translate([System.Security.Principal.SecurityIdentifier]).Value
$groupNames=@("Domain Admins","Enterprise Admins","Schema Admins")
ForEach ($name in $groupNames) {Add-ADPrincipalGroupMembership -Identity $userSID -MemberOf (Get-ADGroup -Identity $name).SID.Value}
```

<span data-ttu-id="3ac63-183">Schließen Sie die Remotedesktopsitzung mit DC1, und stellen Sie dann mit dem Konto „TESTLAB\\Benutzer1“ wieder eine Verbindung her.</span><span class="sxs-lookup"><span data-stu-id="3ac63-183">Close the Remote Desktop session with DC1 and then reconnect using the TESTLAB\\User1 account.</span></span>
  
<span data-ttu-id="3ac63-184">Führen Sie als Nächstes den folgenden Befehl an einer Windows PowerShell-Eingabeaufforderung auf Administratorebene aus, um Datenverkehr für das Tool Ping zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="3ac63-184">Next, to allow traffic for the Ping tool, run this command at an administrator-level Windows PowerShell command prompt.</span></span>
  
```powershell
Set-NetFirewallRule -DisplayName "File and Printer Sharing (Echo Request - ICMPv4-In)" -enabled True
```

<span data-ttu-id="3ac63-185">Dies ist Ihre aktuelle Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="3ac63-185">This is your current configuration.</span></span>
  
![Schritt 1 der simulierten Unternehmensstandardkonfiguration](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase1.png)
  
#### <a name="step-2-configure-app1"></a><span data-ttu-id="3ac63-187">Schritt 2: Konfigurieren von APP1</span><span class="sxs-lookup"><span data-stu-id="3ac63-187">Step 2: Configure APP1</span></span>

<span data-ttu-id="3ac63-188">In diesem Schritt erstellen und konfigurieren Sie APP1, ein Anwendungsserver, der zunächst Web- und Dateifreigabedienste bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="3ac63-188">In this step, you create and configure APP1, which is an application server that initially provides web and file sharing services.</span></span>

<span data-ttu-id="3ac63-189">Geben Sie zum Erstellen eines virtuellen Azure-Computers für APP1 den Namen Ihrer Ressourcengruppe ein, und führen Sie über die Eingabeaufforderung auf Ihrem lokalen Computer die nachfolgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="3ac63-189">To create an Azure Virtual Machine for APP1, fill in the name of your resource group and run these commands at the  command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name APP1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name APP1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName APP1 -VMSize Standard_A1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for APP1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName APP1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "APP1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="3ac63-190">Im nächsten Schritt stellen Sie eine Verbindung mit dem virtuellen Computer APP1 mit dem Kontonamen und Kennwort des lokalen Administratorkontos von APP1 her und öffnen dann eine Windows PowerShell-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="3ac63-190">Next, connect to the APP1 virtual machine using the APP1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="3ac63-191">Führen Sie zum Überprüfen der Namensauflösung und der Netzwerkkommunikation zwischen APP1 und DC1 den Befehl **ping dc1.testlab.**\<Ihr öffentlicher Domänenname> aus, und vergewissern Sie sich, dass vier Antworten vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="3ac63-191">To check name resolution and network communication between APP1 and DC1, run the **ping dc1.testlab.**\<your public domain name> command and verify that there are four replies.</span></span>
  
<span data-ttu-id="3ac63-192">Verknüpfen Sie als Nächstes unter Verwendung der folgenden Befehle an der Windows PowerShell-Eingabeaufforderung den virtuellen Computer APP1 mit der Domäne TESTLAB.</span><span class="sxs-lookup"><span data-stu-id="3ac63-192">Next, join the APP1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab" + $yourDomain)
Restart-Computer
```

<span data-ttu-id="3ac63-193">Beachten Sie, dass Sie nach der Ausführung des Befehls **Add-Computer** die Anmeldeinformationen für das Domänenkonto „TESTLAB\\Benutzer1“ eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="3ac63-193">Note that you must supply the TESTLAB\\User1 domain account credentials after running the **Add-Computer** command.</span></span>
  
<span data-ttu-id="3ac63-194">Stellen Sie nach dem Neustart von APP1 eine Verbindung über das Konto „TESLAB\\Benutzer1“ damit her, und öffnen Sie dann eine Windows PowerShell-Eingabeaufforderung auf Administratorebene.</span><span class="sxs-lookup"><span data-stu-id="3ac63-194">After APP1 restarts, connect to it using the TESTLAB\\User1 account, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="3ac63-195">Im nächsten Schritt richten Sie APP1 mit dem folgenden Befehl in der Windows PowerShell-Eingabeaufforderung auf Administratorebene auf APP1 als Webserver ein.</span><span class="sxs-lookup"><span data-stu-id="3ac63-195">Next, make APP1 a web server with this command at an administrator-level Windows PowerShell command prompt on APP1.</span></span>
  
```powershell
Install-WindowsFeature Web-WebServer -IncludeManagementTools
```

<span data-ttu-id="3ac63-196">Erstellen Sie als Nächstes einen freigegebenen Ordner und eine Textdatei innerhalb des Ordners auf APP1 mit diesen PowerShell-Befehlen.</span><span class="sxs-lookup"><span data-stu-id="3ac63-196">Next, create a shared folder and a text file within the folder on APP1 with these PowerShell commands.</span></span>
  
```powershell
New-Item -path c:\files -type directory
Write-Output "This is a shared file." | out-file c:\files\example.txt
New-SmbShare -name files -path c:\files -changeaccess TESTLAB\User1
```

<span data-ttu-id="3ac63-197">Dies ist Ihre aktuelle Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="3ac63-197">This is your current configuration.</span></span>
  
![Schritt 2 der simulierten Unternehmensstandardkonfiguration](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase2.png)
  
#### <a name="step-3-configure-client1"></a><span data-ttu-id="3ac63-199">Schritt 3: Konfigurieren von CLIENT1</span><span class="sxs-lookup"><span data-stu-id="3ac63-199">Step 3: Configure CLIENT1</span></span>

<span data-ttu-id="3ac63-200">In diesem Schritt wird CLIENT1 erstellt und konfiguriert, der als typischer Laptop, als Tablet oder als Desktopcomputer im Intranet fungiert.</span><span class="sxs-lookup"><span data-stu-id="3ac63-200">In this step, you create and configure CLIENT1, which acts as a typical laptop, tablet, or desktop computer on the intranet.</span></span>

> [!NOTE]  
> <span data-ttu-id="3ac63-p121">Der folgende Befehlssatz erstellt CLIENT1 unter Windows Server 2016 Datacenter. Er gilt für alle Arten von Azure-Abonnements. Wenn Sie über ein Visual Studio-basiertes Azure-Abonnement verfügen, können Sie CLIENT1 unter Windows 10 mit dem [Azure-Portal](https://portal.azure.com) erstellen.</span><span class="sxs-lookup"><span data-stu-id="3ac63-p121">The following command set creates CLIENT1 running Windows Server 2016 Datacenter, which can be done for all types of Azure subscriptions. If you have an Visual Studio-based Azure subscription, you can create CLIENT1 running Windows 10 with the [Azure portal](https://portal.azure.com).</span></span> 
  
<span data-ttu-id="3ac63-203">Geben Sie zum Erstellen eines virtuellen Azure-Computers für CLIENT1 den Namen Ihrer Ressourcengruppe ein, und führen Sie über die Eingabeaufforderung auf Ihrem lokalen Computer die nachfolgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="3ac63-203">To create an Azure Virtual Machine for CLIENT1, fill in the name of your resource group and run these commands at the  command prompt on your local computer.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name TestLab -ResourceGroupName $rgName
$pip=New-AzPublicIpAddress -Name CLIENT1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name CLIENT1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName CLIENT1 -VMSize Standard_A1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for CLIENT1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName CLIENT1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "CLIENT1-OS" -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="3ac63-204">Im nächsten Schritt stellen Sie eine Verbindung mit dem virtuellen Computer CLIENT1 mit dem Kontonamen und Kennwort des lokalen Administratorkontos von CLIENT1 her und öffnen dann eine Windows PowerShell-Eingabeaufforderung auf Administratorebene.</span><span class="sxs-lookup"><span data-stu-id="3ac63-204">Next, connect to the CLIENT1 virtual machine using the CLIENT1 local administrator account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="3ac63-205">Führen Sie zum Überprüfen der Namensauflösung und der Netzwerkkommunikation zwischen CLIENT1 und DC1 den Befehl **ping dc1.testlab.**\<Ihr öffentlicher Domänenname> an einer Windows PowerShell-Eingabeaufforderung aus, und vergewissern Sie sich, dass vier Antworten vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="3ac63-205">To check name resolution and network communication between CLIENT1 and DC1, run the **ping dc1.testlab.**\<your public domain name> command at a Windows PowerShell command prompt and verify that there are four replies.</span></span>
  
<span data-ttu-id="3ac63-206">Verknüpfen Sie als Nächstes unter Verwendung der folgenden Befehle an der Windows PowerShell-Eingabeaufforderung den virtuellen Computer CLIENT1 mit der Domäne TESTLAB.</span><span class="sxs-lookup"><span data-stu-id="3ac63-206">Next, join the CLIENT1 virtual machine to the TESTLAB domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$yourDomain="<your public domain name>"
Add-Computer -DomainName ("testlab" + $yourDomain)
Restart-Computer
```

<span data-ttu-id="3ac63-207">Beachten Sie, dass Sie nach der Ausführung des Befehls **Add-Computer** die Anmeldeinformationen für das Domänenkonto „TESTLAB\\Benutzer1“ eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="3ac63-207">Note that you must supply your TESTLAB\\User1 domain account credentials after running the **Add-Computer** command.</span></span>
  
<span data-ttu-id="3ac63-208">Stellen Sie nach dem Neustart von CLIENT1 eine Verbindung über den Kontonamen und das Kennwort von „TESTLAB\\Benutzer1“ damit her, und öffnen Sie dann eine Windows PowerShell-Eingabeaufforderung auf Administratorebene.</span><span class="sxs-lookup"><span data-stu-id="3ac63-208">After CLIENT1 restarts, connect to it using the TESTLAB\\User1 account name and password, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="3ac63-209">Überprüfen Sie im nächsten Schritt, ob Sie von CLIENT1 aus auf Web- und Dateifreigaberessourcen auf APP1 zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="3ac63-209">Next, verify that you can access web and file share resources on APP1 from CLIENT1.</span></span>
  
1. <span data-ttu-id="3ac63-210">Klicken Sie im Server-Manager im Strukturbereich auf **Lokaler Server**.</span><span class="sxs-lookup"><span data-stu-id="3ac63-210">In Server Manager, in the tree pane, click **Local Server**.</span></span>
    
2. <span data-ttu-id="3ac63-211">Klicken Sie in **Eigenschaften für CLIENT1** neben **Verstärkte Sicherheitskonfiguration für IE** auf **Ein**.</span><span class="sxs-lookup"><span data-stu-id="3ac63-211">In **Properties for CLIENT1**, click **On** next to **IE Enhanced Security Configuration**.</span></span>
    
3. <span data-ttu-id="3ac63-212">Klicken Sie unter **Verstärkte Sicherheitskonfiguration für Internet Explorer** für **Administratoren** und für **Benutzer** auf **Aus**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3ac63-212">In **Internet Explorer Enhanced Security Configuration**, click **Off** for **Administrators** and **Users**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="3ac63-213">Klicken Sie auf dem Startbildschirm auf **Internet Explorer** und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3ac63-213">From the Start screen, click **Internet Explorer**, and then click **OK**.</span></span>
    
5. <span data-ttu-id="3ac63-p122">Geben Sie in der Adressleiste **http<span>://</span>app1.testab.**\<Ihr öffentlicher Domänenname>**/** ein, und drücken Sie dann die EINGABETASTE. Nun sollte die standardmäßige Internetinformationsdienste-Webseite für APP1 angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3ac63-p122">In the Address bar, type **http<span>://</span>app1.testab.**\<your public domain name>**/**, and then press ENTER. You should see the default Internet Information Services web page for APP1.</span></span>
    
6. <span data-ttu-id="3ac63-216">Klicken Sie auf der Desktop-Taskleiste auf das Symbol für den Datei-Explorer.</span><span class="sxs-lookup"><span data-stu-id="3ac63-216">From the desktop taskbar, click the File Explorer icon.</span></span>
    
7. <span data-ttu-id="3ac63-p123">Geben Sie in der Adressleiste **\\\\app1\\Files** ein, und drücken Sie dann die EINGABETASTE. Nun sollte ein Ordnerfenster mit dem Inhalt des freigegebenen Ordners „Files“ angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3ac63-p123">In the address bar, type **\\\\app1\\Files**, and then press ENTER. You should see a folder window with the contents of the Files shared folder.</span></span>
    
8. <span data-ttu-id="3ac63-p124">Doppelklicken Sie im Fenster des freigegebenen Ordners **Files** auf die Datei **Example.txt**. Nun sollte der Inhalt der Datei „Example.txt“ angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3ac63-p124">In the **Files** shared folder window, double-click the **Example.txt** file. You should see the contents of the Example.txt file.</span></span>
    
9. <span data-ttu-id="3ac63-221">Schließen Sie das Fenster **example.txt - Editor** und das Fenster des freigegebenen Ordners **Files**.</span><span class="sxs-lookup"><span data-stu-id="3ac63-221">Close the **example.txt - Notepad** and the **Files** shared folder windows.</span></span>
    
<span data-ttu-id="3ac63-222">Dies ist Ihre aktuelle Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="3ac63-222">This is your current configuration.</span></span>
  
![Schritt 3 der simulierten Unternehmensstandardkonfiguration](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase3.png)


## <a name="phase-2-create-your-microsoft-365-e5-subscription"></a><span data-ttu-id="3ac63-224">Phase 2: Erstellen Ihres Abonnements für Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="3ac63-224">Phase 2: Create your Microsoft 365 E5 subscriptions</span></span>

<span data-ttu-id="3ac63-p125">In dieser Phase erstellen Sie ein neues Abonnement für Microsoft 365 E5, das einen neuen Azure AD-Mandanten verwendet, der von Ihrem Produktionsabonnement getrennt ist. Dies können Sie auf zwei Arten tun:</span><span class="sxs-lookup"><span data-stu-id="3ac63-p125">In this phase, you create a new Microsoft 365 E5 subscription that use a new Azure AD tenant, one that is separate from your production subscription. You can do this in two ways:</span></span>

- <span data-ttu-id="3ac63-227">Verwenden Sie ein Testabonnement von Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="3ac63-227">Use a trial subscription of Microsoft 365 E5.</span></span> 

  <span data-ttu-id="3ac63-p126">Das Testabonnement von Microsoft 365 E5 gilt für 30 Tage, die problemlos auf 60 Tage verlängert werden können. Wenn das Testabonnement abläuft, müssen Sie entweder zu einem kostenpflichtigen Abonnement wechseln oder eine neue Testversion erstellen. Durch Erstellen neuer Testabonnements müssen Sie Ihre Konfiguration verlassen, was im Hintergrund zu komplexen Szenarien führen kann.</span><span class="sxs-lookup"><span data-stu-id="3ac63-p126">The Microsoft 365 E5 trial subscription is 30 days, which can be easily extended to 60 days. When the trial subscription expires, you must either convert it to a paid subscriptions or create a new trial subscription. Creating new trial subscriptions means you will leave your configuration, which could include complex scenarios, behind.</span></span>  

- <span data-ttu-id="3ac63-231">Verwenden Sie ein separates Produktionsabonnement von Microsoft 365 E5 mit einer kleinen Anzahl von Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="3ac63-231">Use a separate production subscription of Microsoft 365 E5 with a small number of licenses.</span></span>

  <span data-ttu-id="3ac63-p127">Dabei entstehen zusätzliche Kosten, aber es wird sichergestellt, dass Sie über eine funktionierende Testumgebung zum Testen von Features, Konfigurationen und Szenarien verfüge, die nicht abläuft. Sie können dieselbe Testumgebung über die gesamten Zeiträume für Machbarkeitsstudien, Demos für Mitarbeiter und Führungskräfte sowie für Anwendungsentwicklung und Tests verwenden. Dies ist die empfohlene Methode.</span><span class="sxs-lookup"><span data-stu-id="3ac63-p127">This is an additional cost, but ensures that you have a working test environment to try features, configurations, and scenarios that does not expire. You can use the same test environment over the long term for proofs of concept, demonstration to peers and management, and application development and testing. This is the recommended method.</span></span>

<span data-ttu-id="3ac63-235">Für das Microsoft 365 E5-Testabonnement benötigen Sie zunächst einen fiktiven Unternehmensnamen und ein neues Microsoft-Konto.</span><span class="sxs-lookup"><span data-stu-id="3ac63-235">To start your Office 365 E5 trial subscription, you first need a fictitious company name and a new Microsoft account.</span></span>
  
1. <span data-ttu-id="3ac63-p128">Es wird empfohlen, eine Variante von „Contoso“ als Unternehmensnamen zu verwenden. Dies ist ein fiktives Unternehmen, das von Microsoft in Beispielen verwendet wird. Notieren Sie hier Ihren fiktiven Unternehmensnamen: ![](./media/Common-Images/TableLine.png).</span><span class="sxs-lookup"><span data-stu-id="3ac63-p128">We recommend that you use a variant of the company name Contoso for your company name, which is a fictitious company used in Microsoft sample content, but it isn't required. Record your fictitious company name here: ![](./media/Common-Images/TableLine.png)</span></span>
    
2. <span data-ttu-id="3ac63-p129">Wenn Sie sich für ein neues Microsoft-Konto registrieren möchten, wechseln Sie zu [https://outlook.com](https://outlook.com), und erstellen Sie ein Konto mit neuem E-Mail-Konto und neuer E-Mail-Adresse. Dieses Konto wird für die Registrierung für Office 365 verwendet.</span><span class="sxs-lookup"><span data-stu-id="3ac63-p129">To sign up for a new Microsoft account, go to [https://outlook.com](https://outlook.com) and create an account with a new email account and address. You will use this account to sign up for Office 365.</span></span>
    
  - <span data-ttu-id="3ac63-240">Notieren Sie hier den Vor- und Nachnamen des Kontos: ![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="3ac63-240">Record the first and last name of your new account here: ![](./media/Common-Images/TableLine.png)</span></span>
    
  - <span data-ttu-id="3ac63-241">Notieren Sie hier die neue E-Mail-Kontoadresse: ![](./media/Common-Images/TableLine.png)@outlook.com</span><span class="sxs-lookup"><span data-stu-id="3ac63-241">Record the new email account address here: ![](./media/Common-Images/TableLine.png)@outlook.com</span></span>
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="3ac63-242">Registrieren für ein Office 365 E5-Testabonnement</span><span class="sxs-lookup"><span data-stu-id="3ac63-242">Sign up for an Office 365 E5 trial subscription</span></span>

<span data-ttu-id="3ac63-243">Wir beginnen mit einem Office 365 E5-Testabonnement und fügen dann das Microsoft 365 E5-Abonnement hinzu.</span><span class="sxs-lookup"><span data-stu-id="3ac63-243">We start with an Office 365 E5 trial subscription and then add the Microsoft 365 E5 subscription to it.</span></span>

1. <span data-ttu-id="3ac63-244">Stellen Sie für die simulierte Office 365-Entwicklungs-/Testumgebung über das Azure-Portal eine Verbindung mit CLIENT1 mit dem CORP\User1-Konto her.</span><span class="sxs-lookup"><span data-stu-id="3ac63-244">For the simulated enterprise Office 365 dev/test environment, connect to CLIENT1 with the CORP\User1 account from the Azure portal.</span></span>  <span data-ttu-id="3ac63-245">Führen Sie vom Startbildschirm Microsoft Edge aus, und wechseln Sie zu [https://aka.ms/e5trial](https://aka.ms/e5trial).</span><span class="sxs-lookup"><span data-stu-id="3ac63-245">From the Start screen, run Microsoft Edge and go to [https://aka.ms/e5trial](https://aka.ms/e5trial).</span></span>
    
2. <span data-ttu-id="3ac63-246">Geben Sie auf der Seite **Willkommen, Grundlegendes zu Ihrer Person** die folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="3ac63-246">On the **Welcome, let's get to know you** page, specify:</span></span>
    
  - <span data-ttu-id="3ac63-247">Tatsächlicher Standort</span><span class="sxs-lookup"><span data-stu-id="3ac63-247">Your physical location</span></span>
    
  - <span data-ttu-id="3ac63-248">Vor- und Nachname des neuen Microsoft-Kontos</span><span class="sxs-lookup"><span data-stu-id="3ac63-248">The first and last name of your new Microsoft account</span></span>
    
  - <span data-ttu-id="3ac63-249">Die neue E-Mail-Kontoadresse</span><span class="sxs-lookup"><span data-stu-id="3ac63-249">Your new email account address</span></span>
    
  - <span data-ttu-id="3ac63-250">Telefonnummer geschäftlich</span><span class="sxs-lookup"><span data-stu-id="3ac63-250">A business phone number</span></span>
    
  - <span data-ttu-id="3ac63-251">Fiktiver Unternehmensname</span><span class="sxs-lookup"><span data-stu-id="3ac63-251">Your fictional company name</span></span>
    
  - <span data-ttu-id="3ac63-252">Unternehmensgröße zwischen 250-999 Mitarbeitern</span><span class="sxs-lookup"><span data-stu-id="3ac63-252">An organization size of 250-999 people</span></span>
    
3. <span data-ttu-id="3ac63-253">Klicken Sie auf **Nur noch ein Schritt**.</span><span class="sxs-lookup"><span data-stu-id="3ac63-253">Click **Just one more step**.</span></span>
    
4. <span data-ttu-id="3ac63-254">Geben Sie auf der Seite **Benutzer-ID erstellen** einen Benutzernamen auf Grundlage der neuen E-Mail-Adresse, den fiktiven Unternehmensnamen nach dem @-Zeichen (entfernen Sie alle Leerzeichen im Namen) und dann (zweimal) ein Kennwort für dieses neue Office 365-Konto ein. </span><span class="sxs-lookup"><span data-stu-id="3ac63-254">On the **Create your user ID** page, type a user name based on your new email address, your fictional company after the @ sign (remove all spaces in the name), then a password (twice) for this new Office 365 account.</span></span>
    
    <span data-ttu-id="3ac63-255">Notieren Sie das verwendete Kennwort, und bewahren Sie es an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="3ac63-255">Record the password that you typed in a secure location.</span></span>
    
    <span data-ttu-id="3ac63-256">Notieren Sie hier den fiktiven Unternehmensnamen, der im Folgenden **Organisationsname** genannt wird: ![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="3ac63-256">Record your fictional company name, to be referred to as the **organization name**, here: ![](./media/Common-Images/TableLine.png)</span></span>
    
5. <span data-ttu-id="3ac63-257">Klicken Sie auf **Mein Konto erstellen**.</span><span class="sxs-lookup"><span data-stu-id="3ac63-257">Click **Create my account**.</span></span>
    
6. <span data-ttu-id="3ac63-p131">Geben Sie auf der Seite **Ich bin kein Roboter** die Rufnummer eines SMS-fähigen Mobiltelefons, und klicken Sie dann auf **SMS an mich**.</span><span class="sxs-lookup"><span data-stu-id="3ac63-p131">On the **Prove. You're. Not. A. Robot.** page, type the phone number of your text-capable phone, and then click **Text me**.</span></span>
    
7. <span data-ttu-id="3ac63-260">Geben Sie den Verifizierungscode ein, den Sie per SMS erhalten haben, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3ac63-260">Type the verification code from the received text message, and then click **Next**.</span></span>
    
8. <span data-ttu-id="3ac63-261">Notieren Sie hier die URL der Anmeldeseite (auswählen und kopieren): ![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="3ac63-261">Record the sign-in page URL here (select and copy): ![](./media/Common-Images/TableLine.png)</span></span>
    
9. <span data-ttu-id="3ac63-262">Notieren Sie hier die Benutzer-ID (auswählen und kopieren): ![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="3ac63-262">Record the user ID here (select and copy): ![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
    <span data-ttu-id="3ac63-263">Dieser Wert wird **Name des globalen Office 365-Administrators** genannt.</span><span class="sxs-lookup"><span data-stu-id="3ac63-263">This value will be referred to as the **Office 365 global administrator name**.</span></span>
    
10. <span data-ttu-id="3ac63-264">Wenn **Alle Schritte wurden abgeschlossen.** angezeigt wird, klicken Sie darauf.</span><span class="sxs-lookup"><span data-stu-id="3ac63-264">When you see **You're ready to go**, click it.</span></span>
    
11. <span data-ttu-id="3ac63-265">Warten Sie auf der nächsten Seite, bis die Einrichtung von Office 365 abgeschlossen ist und alle Kacheln verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="3ac63-265">On the next page, wait until Office 365 completes setting up and all the tiles are available.</span></span>
    
<span data-ttu-id="3ac63-266">Nun sollte die Hauptseite des Office 365-Portals angezeigt werden, über die Sie auf Office-Dienste und das Microsoft 365 Admin Center zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="3ac63-266">You should see main Office 365 portal page from which you can access Office services and the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="3ac63-267">Dann fordern wir Sie dazu auf, ein Office 365-Testabonnement zu erstellen, damit Ihre Dev/Test-Umgebung über einen separaten Azure AD-Mandanten verfügt, der getrennt ist von allen kostenpflichtigen Abonnements, die Sie aktuell haben.</span><span class="sxs-lookup"><span data-stu-id="3ac63-267">We have you create a trial subscription of Office 365 so that your dev/test environment has a separate Azure AD tenant from any paid subscriptions you currently have.</span></span> <span data-ttu-id="3ac63-268">Diese Trennung bedeutet, dass Sie Benutzer zum Testmandanten hinzufügen und entfernen können, ohne dass dies Auswirkungen auf Ihre Produktionsabonnements hat.</span><span class="sxs-lookup"><span data-stu-id="3ac63-268">This separation means you can add and remove users and groups in the test tenant without affecting your production subscriptions.</span></span>
    
### <a name="configure-your-office-365-e5-trial-subscription"></a><span data-ttu-id="3ac63-269">Konfigurieren des Office 365 E5-Testabonnements</span><span class="sxs-lookup"><span data-stu-id="3ac63-269">Phase 3: Configure your Office 365 trial subscription</span></span>

<span data-ttu-id="3ac63-270">Als Nächstes konfigurieren Sie Ihr Office 365 E5-Abonnement mit weiteren Benutzern und weisen diesen Office 365 E5-Lizenzen zu.</span><span class="sxs-lookup"><span data-stu-id="3ac63-270">In this phase, you configure your Office 365 subscription with additional users and assign them Office 365 E5 licenses.</span></span>
  
<span data-ttu-id="3ac63-271">Befolgen Sie die Anweisungen unter [Verbinden mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module), um Ihr Office 365-Abonnement mit dem Azure Active Directory PowerShell-Modul für Graph und dem virtuellen Computer CLIENT1 zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="3ac63-271">Use the instructions in [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) to connect to your Office 365 subscription with the Azure Active Directory PowerShell for Graph module from:</span></span>
    
<span data-ttu-id="3ac63-272">Geben Sie in das Dialogfeld „Windows PowerShell Credential Request“ den Namen des globalen Office 365-Administrators (z. B. „jdoe@contosotoycompany.onmicrosoft.com“) und sein Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="3ac63-272">In the Windows PowerShell Credential Request dialog box, type the Office 365 global administrator name (example: jdoe@contosotoycompany.onmicrosoft.com) and password.</span></span>
  
<span data-ttu-id="3ac63-273">Geben Sie den Namen Ihrer Organisation (z. B. „contosotoycompany“), den zweistelligen Ländercode für Ihren Standort und ein gemeinsames Kontokennwort ein, und führen Sie dann die folgenden Befehle von der PowerShell-Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="3ac63-273">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, a common account password, and then run the following commands from the PowerShell prompt:</span></span>

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
> <span data-ttu-id="3ac63-274">Für die Automatisierung und Vereinfachung der Konfiguration einer Dev/Test-Umgebung wird hier ein gemeinsames Kennwort verwendet.</span><span class="sxs-lookup"><span data-stu-id="3ac63-274">The use of a common password here is for automation and ease of configuration for a dev/test environment.</span></span> <span data-ttu-id="3ac63-275">Natürlich ist davon bei Produktionsabonnements dringend abzuraten.</span><span class="sxs-lookup"><span data-stu-id="3ac63-275">Obviously, this is highly discouraged for production subscriptions.</span></span> 

#### <a name="record-key-information-for-future-reference"></a><span data-ttu-id="3ac63-276">Aufzeichnen von Schlüsselinformationen für spätere Verweise</span><span class="sxs-lookup"><span data-stu-id="3ac63-276">Record key information for future reference</span></span>

<span data-ttu-id="3ac63-277">Sie können diesen Artikel auch ausdrucken, um die speziellen Informationen zu notieren, die Sie für diese Umgebung in den kommenden 30 Tage des Office 365-Testabonnements benötigen.</span><span class="sxs-lookup"><span data-stu-id="3ac63-277">You might want to print this article to record the specific values that you will need for this environment over the 30 days of the Office 365 trial subscription.</span></span> <span data-ttu-id="3ac63-278">Sie können das Testabonnement einfach um weitere 30 Tage verlängern.</span><span class="sxs-lookup"><span data-stu-id="3ac63-278">You can easily extend the trail subscription for another 30 days.</span></span> <span data-ttu-id="3ac63-279">Für eine dauerhafte Entwicklungs-/Testumgebung erstellen Sie ein neues bezahltes Abonnement mit einem separaten Azure AD-Mandanten und einer kleinen Anzahl von Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="3ac63-279">For a permanent dev/test environment, create a new paid subscription with a small number of licenses.</span></span>

<span data-ttu-id="3ac63-280">Notieren Sie diese Werte:</span><span class="sxs-lookup"><span data-stu-id="3ac63-280">Record these values:</span></span>
  
- <span data-ttu-id="3ac63-281">Name des globalen Office 365-Administrators: ![](./media/Common-Images/TableLine.png).onmicrosoft.com (aus Schritt 9 von Phase 2)</span><span class="sxs-lookup"><span data-stu-id="3ac63-281">Office 365 global administrator name: ![](./media/Common-Images/TableLine.png).onmicrosoft.com (from step 9 of Phase 2)</span></span>
    
    <span data-ttu-id="3ac63-282">Notieren Sie auch das Kennwort für dieses Konto, und bewahren Sie es an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="3ac63-282">Also record the password for this account in a secure location.</span></span>
    
- <span data-ttu-id="3ac63-283">Organisationsname für das Testabonnement: ![](./media/Common-Images/TableLine.png) (aus Schritt 4 von Phase 2)</span><span class="sxs-lookup"><span data-stu-id="3ac63-283">Your trial subscription organization name: ![](./media/Common-Images/TableLine.png) (from step 4 of Phase 2)</span></span>
    
- <span data-ttu-id="3ac63-284">Führen Sie über die „Windows Azure Active Directory-Modul für Windows PowerShell“-Eingabeaufforderung den folgenden Befehl aus, um die Konten für Benutzer 2, Benutzer 3, Benutzer 4 und Benutzer 5 anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="3ac63-284">To list the accounts for User 2, User 3, User 4, and User 5, run the following command from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    <span data-ttu-id="3ac63-285">Notieren Sie hier die Kontonamen:</span><span class="sxs-lookup"><span data-stu-id="3ac63-285">Record the account names here:</span></span>
    
  - <span data-ttu-id="3ac63-286">Kontoname für Benutzer 2: benutzer2@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="3ac63-286">User 2 account name: user2@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
  - <span data-ttu-id="3ac63-287">Kontoname für Benutzer 3: benutzer3@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="3ac63-287">User 3 account name: user3@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
  - <span data-ttu-id="3ac63-288">Kontoname für Benutzer 4: benutzer4@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="3ac63-288">User 4 account name: user4@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
  - <span data-ttu-id="3ac63-289">Kontoname für Benutzer 5: benutzer5@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="3ac63-289">User 5 account name: user5@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
    <span data-ttu-id="3ac63-290">Notieren Sie auch das gemeinsame Kennwort für diese Konten, und bewahren Sie es an einem sicheren Ort auf.</span><span class="sxs-lookup"><span data-stu-id="3ac63-290">Also record the passwords for these accounts in a secure location.</span></span>
   

#### <a name="using-an-office-365-e5-devtest-environment"></a><span data-ttu-id="3ac63-291">Verwenden einer Office 365 E5-Entwicklungs-/Testumgebung</span><span class="sxs-lookup"><span data-stu-id="3ac63-291">Using an Office 365 E5 dev/test environment</span></span>

<span data-ttu-id="3ac63-292">Wenn Sie nur eine Office 365-Entwicklungs-/Testumgebung benötigen, sind Sie hier fertig.</span><span class="sxs-lookup"><span data-stu-id="3ac63-292">If all you need is an Office 365 dev/test environment, you can stop here.</span></span> 

<span data-ttu-id="3ac63-293">Weitere Testumgebungsanleitungen, die sowohl für Office 365 als auch für Microsoft 365 gelten, finden Sie unter [Microsoft 365 Enterprise-Testumgebungsanleitungen](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="3ac63-293">See [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) for additional Test Lab Guides that apply to both Office 365 and Microsoft 365.</span></span>
  
### <a name="add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="3ac63-294">Hinzufügen eines Testabonnements für Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="3ac63-294">Phase 2: Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="3ac63-295">Als Nächstes registrieren Sie sich für das Microsoft 365 E5-Testabonnement und fügen es derselben Organisation wie Ihr Office 365 E5-Testabonnement hinzu.</span><span class="sxs-lookup"><span data-stu-id="3ac63-295">In this phase, you sign up for the Microsoft 365 E5 trial subscription and add it to the same organization as your Office 365 E5 trial subscription.</span></span>
  
<span data-ttu-id="3ac63-296">Fügen Sie zuerst das Testabonnement für Microsoft 365 E5 hinzu, und weisen Sie ihrem globalen Administratorkonto eine Microsoft 365-Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="3ac63-296">First, add the Microsoft 365 E5 trial subscription and assign a Microsoft 365 license to your global administrator account.</span></span>
  
1. <span data-ttu-id="3ac63-297">Melden Sie sich mit einer privaten Instanz eines Internetbrowsers mit den Anmeldeinformationen Ihres globalen Administratorkontos beim Microsoft 365 Admin Center unter [https://admin.microsoft.com](https://admin.microsoft.com) an. </span><span class="sxs-lookup"><span data-stu-id="3ac63-297">With a private instance of an Internet browser, sign in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com) with your global administrator account credentials.</span></span>
    
2. <span data-ttu-id="3ac63-298">Klicken Sie auf der Registerkarte **Microsoft 365 Admin Center** im linken Navigationsbereich auf **Abrechnung > Dienste kaufen**.</span><span class="sxs-lookup"><span data-stu-id="3ac63-298">On the **Microsoft 365 admin center** page, in the left navigation, click **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="3ac63-299">Finden Sie auf der Seite**Dienste kaufen** das Element **Microsoft 365 E5**.</span><span class="sxs-lookup"><span data-stu-id="3ac63-299">On the **Purchase services** page, find the **Microsoft 365 E5** item.</span></span> <span data-ttu-id="3ac63-300">Zeigen Sie mit Ihrem Mauszeiger darauf und klicken Sie **Kostenlose Testversion starten**.</span><span class="sxs-lookup"><span data-stu-id="3ac63-300">Hover your mouse pointer over it and click **Start free trial**.</span></span>

4. <span data-ttu-id="3ac63-301">Wählen Sie auf der Seite **Microsoft 365 E5 Testversion** aus, ob Sie eine SMS oder einen Anruf erhalten möchten, geben Sie Ihre Telefonnummer ein und klicken Sie dann **SMS an mich senden** oder **Mich anrufen**.</span><span class="sxs-lookup"><span data-stu-id="3ac63-301">On the **Microsoft 365 E5 Trial** page, choose to receive a text or a call, enter your phone number, then click **Text me** or **Call me**.</span></span>

5. <span data-ttu-id="3ac63-302">Klicken Sie auf der Seite für die **Bestätigung Ihrer Bestellung** auf **Jetzt versuchen**.</span><span class="sxs-lookup"><span data-stu-id="3ac63-302">On the **Confirm your order** page, click **Try now**.</span></span>

6. <span data-ttu-id="3ac63-303">Klicken Sie auf der Seite **Bestellbestätigung** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3ac63-303">On the **Order receipt** page, click **Continue**.</span></span>

7. <span data-ttu-id="3ac63-304">Klicken Sie im Microsoft 365 Admin Center **Aktiver Benutzer** und klicken Sie dann auf Ihr Administratorkonto.</span><span class="sxs-lookup"><span data-stu-id="3ac63-304">In the Microsoft 365 admin center, click **Active users**, and then your administrator account.</span></span>

8. <span data-ttu-id="3ac63-305">Klicken Sie **Bearbeiten** für **Produktlizenzen**.</span><span class="sxs-lookup"><span data-stu-id="3ac63-305">Click **Edit** for **Product licenses**.</span></span>

9. <span data-ttu-id="3ac63-306">Deaktivieren Sie die Lizenz für Office 365 Enterprise E5 und aktivieren Sie die Lizenz für Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="3ac63-306">Turn off the license for Office 365 Enterprise E5 and turn on the license for Microsoft 365 E5.</span></span>

10. <span data-ttu-id="3ac63-307">Klicken Sie auf **Speichern > Schließen > Schließen**.</span><span class="sxs-lookup"><span data-stu-id="3ac63-307">Click **Save > Close > Close**.</span></span>

<span data-ttu-id="3ac63-308">Wiederholen Sie dann die Schritte 8 bis 11 des vorherigen Verfahrens für alle anderen Konten (Benutzer 2, Benutzer 3, Benutzer 4 und Benutzer 5).</span><span class="sxs-lookup"><span data-stu-id="3ac63-308">Next, repeat steps 8 and 9 of the previous procedure for all of your other accounts (User 2, User 3, User 4, and User 5).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3ac63-309">Das Testabonnement für Microsoft 365 E5 ist 30 Tage gültig.</span><span class="sxs-lookup"><span data-stu-id="3ac63-309">The Microsoft 365 E5 trial subscription is 30 days.</span></span> <span data-ttu-id="3ac63-310">Ändern Sie für eine dauerhafte Testumgebung dieses Testabonnement in ein kostenpflichtiges Abonnement mit einer kleinen Anzahl von Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="3ac63-310">For a permanent test environment, convert this trial subscription to a paid subscription with a small number of licenses.</span></span> 
  
### <a name="results"></a><span data-ttu-id="3ac63-311">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="3ac63-311">Results</span></span>

<span data-ttu-id="3ac63-312">Ihre Testumgebung verfügt nun über Folgendes:</span><span class="sxs-lookup"><span data-stu-id="3ac63-312">Your test environment now has:</span></span>
  
- <span data-ttu-id="3ac63-313">Ein Testabonnement für Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="3ac63-313">Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="3ac63-314">Alle entsprechenden Benutzerkonten sind für die Verwendung von Microsoft 365 E5 aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3ac63-314">All your appropriate user accounts (either just the global administrator or all five user accounts) are enabled to use Microsoft 365 E5.</span></span>
- <span data-ttu-id="3ac63-315">Ein simuliertes und vereinfachtes Intranet.</span><span class="sxs-lookup"><span data-stu-id="3ac63-315">A simulated and simplified intranet.</span></span>
    
<span data-ttu-id="3ac63-316">Dies ist Ihre endgültige Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="3ac63-316">This is your final configuration.</span></span>
  
![Phase 2 der simulierten Unternehmensstandardkonfiguration](media/simulated-ent-base-configuration-microsoft-365-enterprise/Phase4.png)
  
<span data-ttu-id="3ac63-318">Sie können nun die zusätzlichen Funktionen von [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise) ausprobieren.</span><span class="sxs-lookup"><span data-stu-id="3ac63-318">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="3ac63-319">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="3ac63-319">Next steps</span></span>

<span data-ttu-id="3ac63-320">Sehen Sie sich diese zusätzlichen Testumgebungsanleitungen an:</span><span class="sxs-lookup"><span data-stu-id="3ac63-320">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="3ac63-321">Identität</span><span class="sxs-lookup"><span data-stu-id="3ac63-321">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="3ac63-322">Verwaltung mobiler Geräte</span><span class="sxs-lookup"><span data-stu-id="3ac63-322">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="3ac63-323">Schutz von Daten</span><span class="sxs-lookup"><span data-stu-id="3ac63-323">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)

## <a name="see-also"></a><span data-ttu-id="3ac63-324">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ac63-324">See also</span></span>

[<span data-ttu-id="3ac63-325">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3ac63-325">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="3ac63-326">Bereitstellen von Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3ac63-326">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="3ac63-327">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="3ac63-327">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
