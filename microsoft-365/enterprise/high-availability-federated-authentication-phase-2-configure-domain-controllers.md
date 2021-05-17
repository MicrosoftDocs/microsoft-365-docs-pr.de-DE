---
title: Hochverfügbarkeit der Verbundauthentifizierung Phase 2 Konfigurieren von Domänencontrollern
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Ent_Solutions
ms.assetid: 6b0eff4c-2c5e-4581-8393-a36f7b36a72f
description: 'Zusammenfassung: Konfigurieren Sie die Domänencontroller und den Verzeichnissynchronisierungsserver für Ihre Hochverfügbarkeits-Verbundauthentifizierung für Microsoft 365 in Microsoft Azure.'
ms.openlocfilehash: 751d332ce5f5606fe5f833182f002a1f4b6f29ad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909810"
---
# <a name="high-availability-federated-authentication-phase-2-configure-domain-controllers"></a><span data-ttu-id="805c3-103">Hochverfügbarkeit der Verbundauthentifizierung, Phase 2: Konfigurieren von Domänencontrollern</span><span class="sxs-lookup"><span data-stu-id="805c3-103">High availability federated authentication Phase 2: Configure domain controllers</span></span>

<span data-ttu-id="805c3-104">In dieser Phase der Bereitstellung hoher Verfügbarkeit für die Microsoft 365-Verbundauthentifizierung in Azure-Infrastrukturdiensten konfigurieren Sie zwei Domänencontroller und den Verzeichnissynchronisierungsserver im virtuellen Azure-Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="805c3-104">In this phase of deploying high availability for Microsoft 365 federated authentication in Azure infrastructure services, you configure two domain controllers and the directory synchronization server in the Azure virtual network.</span></span> <span data-ttu-id="805c3-105">Clientwebanforderungen für die Authentifizierung können dann im virtuellen Azure-Netzwerk authentifiziert werden, anstatt diesen Authentifizierungsverkehr über das VPN zwischen Standorten an Ihr lokales Netzwerk zu senden.</span><span class="sxs-lookup"><span data-stu-id="805c3-105">Client web requests for authentication can then be authenticated in the Azure virtual network, rather than sending that authentication traffic across the site-to-site VPN connection to your on-premises network.</span></span>
  
> [!NOTE]
> <span data-ttu-id="805c3-106">Active Directory Federation Services (AD FS) kann Azure Active Directory (Azure AD) nicht als Ersatz für Active Directory Domain Services (AD DS)-Domänencontroller verwenden.</span><span class="sxs-lookup"><span data-stu-id="805c3-106">Active Directory Federation Services (AD FS) cannot use Azure Active Directory (Azure AD) as a substitute for Active Directory Domain Services (AD DS) domain controllers.</span></span> 
  
<span data-ttu-id="805c3-107">Sie müssen diese Phase abschließen, bevor Sie mit [Phase 3: Konfigurieren von AD FS-Servern weiter.](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md)</span><span class="sxs-lookup"><span data-stu-id="805c3-107">You must complete this phase before moving on to [Phase 3: Configure AD FS servers](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md).</span></span> <span data-ttu-id="805c3-108">Alle Phasen finden Sie unter [Deploy high availability federated authentication for Microsoft 365 in Azure.](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)</span><span class="sxs-lookup"><span data-stu-id="805c3-108">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="create-the-domain-controller-virtual-machines-in-azure"></a><span data-ttu-id="805c3-109">Erstellen der Domänencontroller der virtuellen Computer in Azure</span><span class="sxs-lookup"><span data-stu-id="805c3-109">Create the domain controller virtual machines in Azure</span></span>

<span data-ttu-id="805c3-110">Zunächst müssen Sie die Spalte **Name des virtuellen Computers** in Tabelle M ausfüllen und in der Spalte **Mindestgröße** die Größe der einzelnen virtuellen Computer nach Bedarf anpassen.</span><span class="sxs-lookup"><span data-stu-id="805c3-110">First, you need to fill out the **Virtual machine name** column of Table M and modify virtual machine sizes as needed in the **Minimum size** column.</span></span>
  
|<span data-ttu-id="805c3-111">**Element**</span><span class="sxs-lookup"><span data-stu-id="805c3-111">**Item**</span></span>|<span data-ttu-id="805c3-112">**Name des virtuellen Computers**</span><span class="sxs-lookup"><span data-stu-id="805c3-112">**Virtual machine name**</span></span>|<span data-ttu-id="805c3-113">**Katalogbild**</span><span class="sxs-lookup"><span data-stu-id="805c3-113">**Gallery image**</span></span>|<span data-ttu-id="805c3-114">**Speichertyp**</span><span class="sxs-lookup"><span data-stu-id="805c3-114">**Storage type**</span></span>|<span data-ttu-id="805c3-115">**Mindestgröße**</span><span class="sxs-lookup"><span data-stu-id="805c3-115">**Minimum size**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="805c3-116">1.</span><span class="sxs-lookup"><span data-stu-id="805c3-116">1.</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png) <span data-ttu-id="805c3-118"> (erster Domänencontroller, Beispiel DC1)</span><span class="sxs-lookup"><span data-stu-id="805c3-118">(first domain controller, example DC1)</span></span>  <br/> |<span data-ttu-id="805c3-119">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="805c3-119">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="805c3-120">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="805c3-120">Standard_LRS</span></span>  <br/> |<span data-ttu-id="805c3-121">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="805c3-121">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="805c3-122">2.</span><span class="sxs-lookup"><span data-stu-id="805c3-122">2.</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png) <span data-ttu-id="805c3-124"> (zweiter Domänencontroller, Beispiel DC2)</span><span class="sxs-lookup"><span data-stu-id="805c3-124">(second domain controller, example DC2)</span></span>  <br/> |<span data-ttu-id="805c3-125">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="805c3-125">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="805c3-126">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="805c3-126">Standard_LRS</span></span>  <br/> |<span data-ttu-id="805c3-127">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="805c3-127">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="805c3-128">3.</span><span class="sxs-lookup"><span data-stu-id="805c3-128">3.</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png) <span data-ttu-id="805c3-130">(Verzeichnissynchronisierungsserver, Beispiel DS1)</span><span class="sxs-lookup"><span data-stu-id="805c3-130">(directory synchronization server, example DS1)</span></span>  <br/> |<span data-ttu-id="805c3-131">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="805c3-131">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="805c3-132">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="805c3-132">Standard_LRS</span></span>  <br/> |<span data-ttu-id="805c3-133">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="805c3-133">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="805c3-134">4.</span><span class="sxs-lookup"><span data-stu-id="805c3-134">4.</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png) <span data-ttu-id="805c3-136">(erster AD FS-Server, Beispiel ADFS1)</span><span class="sxs-lookup"><span data-stu-id="805c3-136">(first AD FS server, example ADFS1)</span></span>  <br/> |<span data-ttu-id="805c3-137">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="805c3-137">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="805c3-138">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="805c3-138">Standard_LRS</span></span>  <br/> |<span data-ttu-id="805c3-139">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="805c3-139">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="805c3-140">5.</span><span class="sxs-lookup"><span data-stu-id="805c3-140">5.</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png) <span data-ttu-id="805c3-142">(zweiter AD FS-Server, Beispiel ADFS2)</span><span class="sxs-lookup"><span data-stu-id="805c3-142">(second AD FS server, example ADFS2)</span></span>  <br/> |<span data-ttu-id="805c3-143">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="805c3-143">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="805c3-144">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="805c3-144">Standard_LRS</span></span>  <br/> |<span data-ttu-id="805c3-145">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="805c3-145">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="805c3-146">6.</span><span class="sxs-lookup"><span data-stu-id="805c3-146">6.</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png) <span data-ttu-id="805c3-148">(erster Webanwendungsproxyserver, Beispiel WEB1)</span><span class="sxs-lookup"><span data-stu-id="805c3-148">(first web application proxy server, example WEB1)</span></span>  <br/> |<span data-ttu-id="805c3-149">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="805c3-149">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="805c3-150">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="805c3-150">Standard_LRS</span></span>  <br/> |<span data-ttu-id="805c3-151">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="805c3-151">Standard_D2</span></span>  <br/> |
|<span data-ttu-id="805c3-152">7.</span><span class="sxs-lookup"><span data-stu-id="805c3-152">7.</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png) <span data-ttu-id="805c3-154">(zweiter Webanwendungsproxyserver, Beispiel WEB2)</span><span class="sxs-lookup"><span data-stu-id="805c3-154">(second web application proxy server, example WEB2)</span></span>  <br/> |<span data-ttu-id="805c3-155">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="805c3-155">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="805c3-156">Standard_LRS</span><span class="sxs-lookup"><span data-stu-id="805c3-156">Standard_LRS</span></span>  <br/> |<span data-ttu-id="805c3-157">Standard_D2</span><span class="sxs-lookup"><span data-stu-id="805c3-157">Standard_D2</span></span>  <br/> |
   
 <span data-ttu-id="805c3-158">**Tabelle M – Virtuelle Computer für die Hochverfügbarkeits-Verbundauthentifizierung für Microsoft 365 in Azure**</span><span class="sxs-lookup"><span data-stu-id="805c3-158">**Table M - Virtual machines for the high availability federated authentication for Microsoft 365 in Azure**</span></span>
  
<span data-ttu-id="805c3-159">Eine vollständige Liste der Größen der virtuellen Computer finden Sie unter [Größen für virtuelle Computer](/azure/virtual-machines/virtual-machines-windows-sizes).</span><span class="sxs-lookup"><span data-stu-id="805c3-159">For the complete list of virtual machine sizes, see [Sizes for virtual machines](/azure/virtual-machines/virtual-machines-windows-sizes).</span></span>
  
<span data-ttu-id="805c3-160">Verwenden Sie den folgenden Azure PowerShell-Befehlsblock, um die virtuellen Computer für die beiden Domänencontroller zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="805c3-160">The following Azure PowerShell command block creates the virtual machines for the two domain controllers.</span></span> <span data-ttu-id="805c3-161">Geben Sie die Werte für die Variablen an, und entfernen Sie die \< and > Zeichen.</span><span class="sxs-lookup"><span data-stu-id="805c3-161">Specify the values for the variables, removing the \< and > characters.</span></span> <span data-ttu-id="805c3-162">Beachten Sie, dass dieser Azure PowerShell-Befehlsblock Werte aus den folgenden Tabellen verwendet:</span><span class="sxs-lookup"><span data-stu-id="805c3-162">Note that this Azure PowerShell command block uses values from the following tables:</span></span>
  
- <span data-ttu-id="805c3-163">Tabelle M (für die virtuellen Computer)</span><span class="sxs-lookup"><span data-stu-id="805c3-163">Table M, for your virtual machines</span></span>
    
- <span data-ttu-id="805c3-164">Tabelle R (für die Ressourcengruppen)</span><span class="sxs-lookup"><span data-stu-id="805c3-164">Table R, for your resource groups</span></span>
    
- <span data-ttu-id="805c3-165">Tabelle V (für die Einstellungen des virtuellen Netzwerks)</span><span class="sxs-lookup"><span data-stu-id="805c3-165">Table V, for your virtual network settings</span></span>
    
- <span data-ttu-id="805c3-166">Tabelle S (für das Subnetz)</span><span class="sxs-lookup"><span data-stu-id="805c3-166">Table S, for your subnets</span></span>
    
- <span data-ttu-id="805c3-167">Tabelle I (für die statischen IP-Adressen)</span><span class="sxs-lookup"><span data-stu-id="805c3-167">Table I, for your static IP addresses</span></span>
    
- <span data-ttu-id="805c3-168">Tabelle A (für die Verfügbarkeitsgruppen)</span><span class="sxs-lookup"><span data-stu-id="805c3-168">Table A, for your availability sets</span></span>
    
<span data-ttu-id="805c3-169">Beachten Sie, dass Sie die Tabellen R, V, S, I und A in [Phase 1: Konfigurieren von Azure definiert haben.](high-availability-federated-authentication-phase-1-configure-azure.md)</span><span class="sxs-lookup"><span data-stu-id="805c3-169">Recall that you defined Tables R, V, S, I, and A in [Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="805c3-170">[!HINWEIS] In den folgenden Befehlssätzen wird die aktuelle Version von Azure PowerShell verwendet.</span><span class="sxs-lookup"><span data-stu-id="805c3-170">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="805c3-171">Weitere [Informationen finden Sie unter Erste Schritte mit Azure PowerShell](/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="805c3-171">See [Get started with Azure PowerShell](/powershell/azure/get-started-azureps).</span></span> 
  
<span data-ttu-id="805c3-172">Sobald Sie alle Werte korrekt festgelegt haben, führen Sie den resultierenden Block über die Azure PowerShell-Eingabeaufforderung oder in PowerShell ISE (Integrated Script Environment) auf Ihrem lokalen Computer aus.</span><span class="sxs-lookup"><span data-stu-id="805c3-172">When you have supplied all the correct values, run the resulting block at the Azure PowerShell prompt or in the PowerShell Integrated Script Environment (ISE) on your local computer.</span></span>
  
> [!TIP]
> <span data-ttu-id="805c3-173">Verwenden Sie diese [Microsoft Excel-Konfigurationsarbeitsmappe,](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx)um einsatzbereite PowerShell-Befehlsblöcke basierend auf Ihren benutzerdefinierten Einstellungen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="805c3-173">To generate ready-to-run PowerShell command blocks based on your custom settings, use this [Microsoft Excel configuration workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span></span> 

```powershell
# Set up variables common to both virtual machines
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table S - Item 1 - Value column>"
$avName="<Table A - Item 1 - Availability set name column>"
$rgNameTier="<Table R - Item 1 - Resource group name column>"
$rgNameInfra="<Table R - Item 4 - Resource group name column>"

$rgName=$rgNameInfra
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName

$rgName=$rgNameTier
$avSet=Get-AzAvailabilitySet -Name $avName -ResourceGroupName $rgName 

# Create the first domain controller
$vmName="<Table M - Item 1 - Virtual machine name column>"
$vmSize="<Table M - Item 1 - Minimum size column>"
$staticIP="<Table I - Item 1 - Value column>"
$diskStorageType="<Table M - Item 1 - Storage type column>"
$diskSize=<size of the extra disk for Active Directory Domain Services (AD DS) data in GB>

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
$diskConfig=New-AzDiskConfig -AccountType $diskStorageType -Location $locName -CreateOption Empty -DiskSizeGB $diskSize
$dataDisk1=New-AzDisk -DiskName ($vmName + "-DataDisk1") -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name ($vmName + "-DataDisk1") -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for the first domain controller." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the second domain controller
$vmName="<Table M - Item 2 - Virtual machine name column>"
$vmSize="<Table M - Item 2 - Minimum size column>"
$staticIP="<Table I - Item 2 - Value column>"
$diskStorageType="<Table M - Item 2 - Storage type column>"
$diskSize=<size of the extra disk for AD DS data in GB>

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
$diskConfig=New-AzDiskConfig -AccountType $diskStorageType -Location $locName -CreateOption Empty -DiskSizeGB $diskSize
$dataDisk1=New-AzDisk -DiskName ($vmName + "-DataDisk1") -Disk $diskConfig -ResourceGroupName $rgName
$vm=Add-AzVMDataDisk -VM $vm -Name ($vmName + "-DataDisk1") -CreateOption Attach -ManagedDiskId $dataDisk1.Id -Lun 1
$cred=Get-Credential -Message "Type the name and password of the local administrator account for the second domain controller." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the directory synchronization server
$vmName="<Table M - Item 3 - Virtual machine name column>"
$vmSize="<Table M - Item 3 - Minimum size column>"
$staticIP="<Table I - Item 3 - Value column>"
$diskStorageType="<Table M - Item 3 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $subnet -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the directory synchronization server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> <span data-ttu-id="805c3-p105">Da diese virtuellen Computer für eine Intranetanwendung gedacht sind, wird ihnen weder eine öffentliche IP-Adresse noch eine DNS-Domänennamenbezeichnung zugewiesen. Sie sind also nicht über das Internet erreichbar. Das bedeutet allerdings, dass Sie auch nicht über das Azure-Portal auf sie zugreifen können. Wenn Sie die Eigenschaften eines der virtuellen Computer aufrufen, ist die Option zum **Verbinden** nicht verfügbar. Verwenden Sie eine Remotedesktopverbindung oder ein anderes Remotedesktoptool, um eine Verbindung über die private IP-Adresse des betreffenden virtuellen Computers oder seinen Intranet-DNS-Namen herzustellen.</span><span class="sxs-lookup"><span data-stu-id="805c3-p105">Because these virtual machines are for an intranet application, they are not assigned a public IP address or a DNS domain name label and exposed to the Internet. However, this also means that you cannot connect to them from the Azure portal. The **Connect** option is unavailable when you view the properties of the virtual machine. Use the Remote Desktop Connection accessory or another Remote Desktop tool to connect to the virtual machine using its private IP address or intranet DNS name.</span></span>
  
## <a name="configure-the-first-domain-controller"></a><span data-ttu-id="805c3-178">Konfigurieren des ersten Domänencontrollers</span><span class="sxs-lookup"><span data-stu-id="805c3-178">Configure the first domain controller</span></span>

<span data-ttu-id="805c3-p106">Erstellen Sie mithilfe eines Remotedesktopclients Ihrer Wahl eine Remotedesktopverbindung zum virtuellen Computer mit dem ersten Domänencontroller. Verwenden Sie den Intranet-DNS-Namen oder den Computernamen des Servers und die Anmeldeinformationen des lokalen Administratorkontos.</span><span class="sxs-lookup"><span data-stu-id="805c3-p106">Use the remote desktop client of your choice and create a remote desktop connection to the first domain controller virtual machine. Use its intranet DNS or computer name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="805c3-181">Fügen Sie als Nächstes den zusätzlichen Datenträger dem ersten Domänencontroller mit diesem Befehl über eine Windows PowerShell-Eingabeaufforderung auf dem ersten virtuellen **Domänencontrollercomputer hinzu:**</span><span class="sxs-lookup"><span data-stu-id="805c3-181">Next, add the extra data disk to the first domain controller with this command from a Windows PowerShell command prompt **on the first domain controller virtual machine**:</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="805c3-182">Im nächsten Schritt testen Sie die Verbindung des ersten Domänencontrollers mit Standorten im Netzwerk Ihrer Organisation mithilfe des Befehls **ping** aus, um einen Ping an die Namen und IP-Adressen von Ressourcen innerhalb des Netzwerks Ihrer Organisation zu senden.</span><span class="sxs-lookup"><span data-stu-id="805c3-182">Next, test the first domain controller's connectivity to locations on your organization network by using the **ping** command to ping names and IP addresses of resources on your organization network.</span></span>
  
<span data-ttu-id="805c3-p107">Gleichzeitig stellen Sie damit sicher, dass die DNS-Namensauflösung korrekt funktioniert (d. h., dass der virtuelle Computer korrekt mit denlokalen DNS-Servern konfiguriert ist) und dass Pakete sowohl an das standortübergreifende Netzwerk als auch aus ihm gesendet werden können. Wenn bei diesem grundlegenden Test ein Fehler auftritt, wenden Sie sich an Ihre IT-Abteilung, um die Probleme mit der DNS-Namensauflösung und der Paketzustellung zu lösen.</span><span class="sxs-lookup"><span data-stu-id="805c3-p107">This procedure ensures that DNS name resolution is working correctly (that the virtual machine is correctly configured with on-premises DNS servers) and that packets can be sent to and from the cross-premises virtual network. If this basic test fails, contact your IT department to troubleshoot the DNS name resolution and packet delivery issues.</span></span>
  
<span data-ttu-id="805c3-185">Führen Sie im nächsten Schritt an der Windows PowerShell-Eingabeaufforderung auf dem ersten Domänencontroller die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="805c3-185">Next, from the Windows PowerShell command prompt on the first domain controller, run the following commands:</span></span>
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred
```

<span data-ttu-id="805c3-p108">Sie werden aufgefordert, die Anmeldeinformationen für ein Domänenadministratorkonto einzugeben. Der Computer wird neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="805c3-p108">You will be prompted to supply the credentials of a domain administrator account. The computer will restart.</span></span>
  
## <a name="configure-the-second-domain-controller"></a><span data-ttu-id="805c3-188">Konfigurieren des zweiten Domänencontrollers</span><span class="sxs-lookup"><span data-stu-id="805c3-188">Configure the second domain controller</span></span>

<span data-ttu-id="805c3-p109">Erstellen Sie mithilfe eines Remotedesktopclients Ihrer Wahl eine Remotedesktopverbindung zum virtuellen Computer mit dem zweiten Domänencontroller. Verwenden Sie den Intranet-DNS-Namen oder den Computernamen des Servers und die Anmeldeinformationen des lokalen Administratorkontos.</span><span class="sxs-lookup"><span data-stu-id="805c3-p109">Use the remote desktop client of your choice and create a remote desktop connection to the second domain controller virtual machine. Use its intranet DNS or computer name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="805c3-191">Als Nächstes müssen Sie dem zweiten Domänencontroller den zusätzlichen Datenträger mit diesem Befehl über eine eingabeaufforderung Windows PowerShell des zweiten virtuellen Domänencontrollercomputers **hinzufügen:**</span><span class="sxs-lookup"><span data-stu-id="805c3-191">Next, you need to add the extra data disk to the second domain controller with this command from a Windows PowerShell command prompt **on the second domain controller virtual machine**:</span></span>
  
```powershell
Get-Disk | Where PartitionStyle -eq "RAW" | Initialize-Disk -PartitionStyle MBR -PassThru | New-Partition -AssignDriveLetter -UseMaximumSize | Format-Volume -FileSystem NTFS -NewFileSystemLabel "WSAD Data"
```

<span data-ttu-id="805c3-192">Führen Sie als nächsten Schritt die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="805c3-192">Next, run the following commands:</span></span>
  
```powershell
$domname="<DNS domain name of the domain for which this computer will be a domain controller, such as corp.contoso.com>"
$cred = Get-Credential -Message "Enter credentials of an account with permission to join a new domain controller to the domain"
Install-WindowsFeature AD-Domain-Services -IncludeManagementTools
Install-ADDSDomainController -InstallDns -DomainName $domname  -DatabasePath "F:\NTDS" -SysvolPath "F:\SYSVOL" -LogPath "F:\Logs" -Credential $cred

```

<span data-ttu-id="805c3-p110">Sie werden aufgefordert, die Anmeldeinformationen für ein Domänenadministratorkonto einzugeben. Der Computer wird neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="805c3-p110">You will be prompted to supply the credentials of a domain administrator account. The computer will restart.</span></span>
  
<span data-ttu-id="805c3-195">Als Nächstes müssen Sie die DNS-Server für Ihr virtuelles Netzwerk so aktualisieren, dass Azure den virtuellen Computern die IP-Adressen der beiden neuen Domänencontroller zur Verwendungals DNS-Server zuweist.</span><span class="sxs-lookup"><span data-stu-id="805c3-195">Next, you need to update the DNS servers for your virtual network so that Azure assigns virtual machines the IP addresses of the two new domain controllers to use as their DNS servers.</span></span> <span data-ttu-id="805c3-196">Füllen Sie die Variablen aus, und führen Sie dann diese Befehle an Windows PowerShell Eingabeaufforderung auf Dem lokalen Computer aus:</span><span class="sxs-lookup"><span data-stu-id="805c3-196">Fill in the variables and then run these commands from a Windows PowerShell command prompt on your local computer:</span></span>
  
```powershell
$rgName="<Table R - Item 4 - Resource group name column>"
$adrgName="<Table R - Item 1 - Resource group name column>"
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$onpremDNSIP1="<Table D - Item 1 - DNS server IP address column>"
$onpremDNSIP2="<Table D - Item 2 - DNS server IP address column>"
$staticIP1="<Table I - Item 1 - Value column>"
$staticIP2="<Table I - Item 2 - Value column>"
$firstDCName="<Table M - Item 1 - Virtual machine name column>"
$secondDCName="<Table M - Item 2 - Virtual machine name column>"

$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name $vnetName
$vnet.DhcpOptions.DnsServers.Add($staticIP1)
$vnet.DhcpOptions.DnsServers.Add($staticIP2) 
$vnet.DhcpOptions.DnsServers.Remove($onpremDNSIP1)
$vnet.DhcpOptions.DnsServers.Remove($onpremDNSIP2) 
Set-AzVirtualNetwork -VirtualNetwork $vnet
Restart-AzVM -ResourceGroupName $adrgName -Name $firstDCName
Restart-AzVM -ResourceGroupName $adrgName -Name $secondDCName
```

<span data-ttu-id="805c3-p112">Beachten Sie, dass die beiden Domänencontroller neu gestartet werden, damit sie nicht mit den lokalen DNS-Server als DNS-Server konfiguriert werden. Da beide selbst DNS-Server sind, wurden sie bei der Höherstufung zu Domänencontrollern automatisch mit den lokalen DNS-Servern als DNS-Weiterleitungen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="805c3-p112">Note that we restart the two domain controllers so that they are not configured with the on-premises DNS servers as DNS servers. Because they are both DNS servers themselves, they were automatically configured with the on-premises DNS servers as DNS forwarders when they were promoted to domain controllers.</span></span>
  
<span data-ttu-id="805c3-p113">Als Nächstes müssen wir eine Active Directory-Replikationswebsite erstellen, um sicherzustellen, dass Server im virtuellen Azure-Netzwerk die lokalen Domänencontroller verwenden. Stellen Sie mit einem Domänenadministratorkonto eine Verbindung zu einem der Domänencontroller her, und führen Sie folgende Befehle an einer Windows PowerShell-Eingabeaufforderung auf Administratorebene aus:</span><span class="sxs-lookup"><span data-stu-id="805c3-p113">Next, we need to create an Active Directory replication site to ensure that servers in the Azure virtual network use the local domain controllers. Connect to either domain controller with a domain administrator account and run the following commands from an administrator-level Windows PowerShell prompt:</span></span>
  
```powershell
$vnet="<Table V - Item 1 - Value column>"
$vnetSpace="<Table V - Item 4 - Value column>"
New-ADReplicationSite -Name $vnet 
New-ADReplicationSubnet -Name $vnetSpace -Site $vnet
```

## <a name="configure-the-directory-synchronization-server"></a><span data-ttu-id="805c3-201">Konfigurieren des Verzeichnissynchronisierungsservers</span><span class="sxs-lookup"><span data-stu-id="805c3-201">Configure the directory synchronization server</span></span>

<span data-ttu-id="805c3-202">Verwenden Sie den Remotedesktopclient Ihrer Wahl, und erstellen Sie eine Remotedesktopverbindung mit dem virtuellen Computer des Verzeichnissynchronisierungsservers.</span><span class="sxs-lookup"><span data-stu-id="805c3-202">Use the remote desktop client of your choice and create a remote desktop connection to the directory synchronization server virtual machine.</span></span> <span data-ttu-id="805c3-203">Verwenden Sie den Intranet-DNS-Namen oder den Computernamen des Servers und die Anmeldeinformationen des lokalen Administratorkontos.</span><span class="sxs-lookup"><span data-stu-id="805c3-203">Use its intranet DNS or computer name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="805c3-204">Als Nächstes verbinden Sie es mit der entsprechenden AD DS-Domäne mit diesen Befehlen an Windows PowerShell Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="805c3-204">Next, join it to the appropriate AD DS domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$domName="<AD DS domain name to join, such as corp.contoso.com>"
$cred=Get-Credential -Message "Type the name and password of a domain acccount."
Add-Computer -DomainName $domName -Credential $cred
Restart-Computer
```

<span data-ttu-id="805c3-205">Wenn Sie diese Phase erfolgreich abgeschlossen haben, sieht Ihre Konfiguration wie folgt aus. Für die Computernamen werden hier Platzhalter verwendet.</span><span class="sxs-lookup"><span data-stu-id="805c3-205">Here is the configuration resulting from the successful completion of this phase, with placeholder computer names.</span></span>
  
<span data-ttu-id="805c3-206">**Phase 2: Domänencontroller und Verzeichnissynchronisierungsserver für Ihre Hochverfügbarkeits-Verbundauthentifizierungsinfrastruktur in Azure**</span><span class="sxs-lookup"><span data-stu-id="805c3-206">**Phase 2: The domain controllers and directory synchronization server for your high availability federated authentication infrastructure in Azure**</span></span>

![Phase 2 der Hochverfügbarkeit der Microsoft 365-Verbundauthentifizierungsinfrastruktur in Azure mit Domänencontrollern](../media/b0c1013b-3fb4-499e-93c1-bf310d8f4c32.png)
  
## <a name="next-step"></a><span data-ttu-id="805c3-208">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="805c3-208">Next step</span></span>

<span data-ttu-id="805c3-209">Verwenden [Sie Phase 3: Konfigurieren von AD FS-Servern,](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md) um die Konfiguration dieser Arbeitsauslastung fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="805c3-209">Use [Phase 3: Configure AD FS servers](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md) to continue configuring this workload.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="805c3-210">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="805c3-210">See Also</span></span>

[<span data-ttu-id="805c3-211">Bereitstellen der Verbundauthentifizierung mit Hochverfügbarkeit für Microsoft 365 in Azure</span><span class="sxs-lookup"><span data-stu-id="805c3-211">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="805c3-212">Verbundidentität für Ihre Microsoft 365-Entwicklungs-/Testumgebung</span><span class="sxs-lookup"><span data-stu-id="805c3-212">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="805c3-213">Microsoft 365-Lösungs- und Architekturcenter</span><span class="sxs-lookup"><span data-stu-id="805c3-213">Microsoft 365 solution and architecture center</span></span>](../solutions/index.yml)