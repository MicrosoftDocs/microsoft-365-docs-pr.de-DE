---
title: Hohe Verfügbarkeit Verbund Authentifizierungs Phase 3 Konfigurieren von AD FS-Servern
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
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 202b76ff-74a6-4486-ada1-a9bf099dab8f
description: Erfahren Sie, wie Sie die AD FS-Server für die Verbundauthentifizierung mit hoher Verfügbarkeit für Microsoft 365 in Microsoft Azure erstellen und konfigurieren.
ms.openlocfilehash: bf8b52f4cd0dead0c264b71363fd5248397ae88d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690900"
---
# <a name="high-availability-federated-authentication-phase-3-configure-ad-fs-servers"></a><span data-ttu-id="f2c08-103">Hochverfügbarkeit der Verbundauthentifizierung, Phase 3: Konfigurieren von AD FS-Servern</span><span class="sxs-lookup"><span data-stu-id="f2c08-103">High availability federated authentication Phase 3: Configure AD FS servers</span></span>

<span data-ttu-id="f2c08-104">In dieser Phase der Bereitstellung von hoher Verfügbarkeit für die Verbundauthentifizierung von Microsoft 365 in Azure-Infrastrukturdiensten erstellen Sie einen internen Lastenausgleich und zwei AD FS-Server.</span><span class="sxs-lookup"><span data-stu-id="f2c08-104">In this phase of deploying high availability for Microsoft 365 federated authentication in Azure infrastructure services, you create an internal load balancer and two AD FS servers.</span></span>
  
<span data-ttu-id="f2c08-105">Sie müssen diese Phase abschließen, bevor Sie mit [Phase 4: Konfigurieren von Webanwendungs Proxys](high-availability-federated-authentication-phase-4-configure-web-application-pro.md)fortfahren.</span><span class="sxs-lookup"><span data-stu-id="f2c08-105">You must complete this phase before moving on to [Phase 4: Configure web application proxies](high-availability-federated-authentication-phase-4-configure-web-application-pro.md).</span></span> <span data-ttu-id="f2c08-106">Unter [Bereitstellen der Verbundauthentifizierung mit hoher Verfügbarkeit für Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) für alle Phasen.</span><span class="sxs-lookup"><span data-stu-id="f2c08-106">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
## <a name="create-the-ad-fs-server-virtual-machines-in-azure"></a><span data-ttu-id="f2c08-107">Erstellen der virtuellen Computer des AD FS-Servers in Azure</span><span class="sxs-lookup"><span data-stu-id="f2c08-107">Create the AD FS server virtual machines in Azure</span></span>

<span data-ttu-id="f2c08-p102">Verwenden Sie den folgenden PowerShell-Befehlsblock, um die virtuellen Computer für die beiden AD FS-Server zu erstellen. Dieser PowerShell-Befehlssatz verwendet Werte aus den folgenden Tabellen:</span><span class="sxs-lookup"><span data-stu-id="f2c08-p102">Use the following block of PowerShell commands to create the virtual machines for the two AD FS servers. This PowerShell command set uses values from the following tables:</span></span>
  
- <span data-ttu-id="f2c08-110">Tabelle M (für die virtuellen Computer)</span><span class="sxs-lookup"><span data-stu-id="f2c08-110">Table M, for your virtual machines</span></span>
    
- <span data-ttu-id="f2c08-111">Tabelle R (für die Ressourcengruppen)</span><span class="sxs-lookup"><span data-stu-id="f2c08-111">Table R, for your resource groups</span></span>
    
- <span data-ttu-id="f2c08-112">Tabelle V (für die Einstellungen des virtuellen Netzwerks)</span><span class="sxs-lookup"><span data-stu-id="f2c08-112">Table V, for your virtual network settings</span></span>
    
- <span data-ttu-id="f2c08-113">Tabelle S (für das Subnetz)</span><span class="sxs-lookup"><span data-stu-id="f2c08-113">Table S, for your subnets</span></span>
    
- <span data-ttu-id="f2c08-114">Tabelle I (für die statischen IP-Adressen)</span><span class="sxs-lookup"><span data-stu-id="f2c08-114">Table I, for your static IP addresses</span></span>
    
- <span data-ttu-id="f2c08-115">Tabelle A (für die Verfügbarkeitsgruppen)</span><span class="sxs-lookup"><span data-stu-id="f2c08-115">Table A, for your availability sets</span></span>
    
<span data-ttu-id="f2c08-116">Erinnern Sie sich, dass Sie Tabelle M in Phase [2: Configure Domain Controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) and Tables R, V, S, I und A in [Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md)definiert haben.</span><span class="sxs-lookup"><span data-stu-id="f2c08-116">Recall that you defined Table M in [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) and Tables R, V, S, I, and A in [Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f2c08-117">[!HINWEIS] In den folgenden Befehlssätzen wird die aktuelle Version von Azure PowerShell verwendet.</span><span class="sxs-lookup"><span data-stu-id="f2c08-117">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="f2c08-118">Weitere Informationen finden Sie unter [Erste Schritte mit Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="f2c08-118">See [Get started with Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span></span> 
  
<span data-ttu-id="f2c08-119">Zuerst erstellen Sie in Azure einen internen Lastenausgleich für die beiden AD FS-Server.</span><span class="sxs-lookup"><span data-stu-id="f2c08-119">First, you create an Azure internal load balancer for the two AD FS servers.</span></span> <span data-ttu-id="f2c08-120">Geben Sie die Werte für die Variablen an, und entfernen Sie die \< and > Zeichen.</span><span class="sxs-lookup"><span data-stu-id="f2c08-120">Specify the values for the variables, removing the \< and > characters.</span></span> <span data-ttu-id="f2c08-121">Sobald Sie alle Werte korrekt festgelegt haben, führen Sie den resultierenden Block über die Azure PowerShell-Eingabeaufforderung oder in PowerShell ISE aus.</span><span class="sxs-lookup"><span data-stu-id="f2c08-121">When you have supplied all the proper values, run the resulting block at the Azure PowerShell command prompt or in the PowerShell ISE.</span></span>
  
> [!TIP]
> <span data-ttu-id="f2c08-122">Verwenden Sie diese [Microsoft Excel Konfigurations Arbeitsmappe](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx), um Ready-to-Run PowerShell-Befehlsblöcke basierend auf Ihren benutzerdefinierten Einstellungen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="f2c08-122">To generate ready-to-run PowerShell command blocks based on your custom settings, use this [Microsoft Excel configuration workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span></span> 

```powershell
# Set up key variables
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table R - Item 2 - Subnet name column>"
$privIP="<Table I - Item 4 - Value column>"
$rgName=<Table R - Item 4 - Resource group name column>"

$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName

$frontendIP=New-AzLoadBalancerFrontendIpConfig -Name "ADFSServers-LBFE" -PrivateIPAddress $privIP -Subnet $subnet
$beAddressPool=New-AzLoadBalancerBackendAddressPoolConfig -Name "ADFSServers-LBBE"

$healthProbe=New-AzLoadBalancerProbeConfig -Name WebServersProbe -Protocol "TCP" -Port 443 -IntervalInSeconds 15 -ProbeCount 2
$lbrule=New-AzLoadBalancerRuleConfig -Name "HTTPSTraffic" -FrontendIpConfiguration $frontendIP -BackendAddressPool $beAddressPool -Probe $healthProbe -Protocol "TCP" -FrontendPort 443 -BackendPort 443
New-AzLoadBalancer -ResourceGroupName $rgName -Name "ADFSServers" -Location $locName -LoadBalancingRule $lbrule -BackendAddressPool $beAddressPool -Probe $healthProbe -FrontendIpConfiguration $frontendIP
```

<span data-ttu-id="f2c08-123">Erstellen Sie als Nächstes die virtuellen Computer des AD FS-Servers.</span><span class="sxs-lookup"><span data-stu-id="f2c08-123">Next, create the AD FS server virtual machines.</span></span>
  
<span data-ttu-id="f2c08-124">Sobald Sie alle Werte korrekt festgelegt haben, führen Sie den resultierenden Block über die Azure PowerShell-Eingabeaufforderung oder in PowerShell ISE aus.</span><span class="sxs-lookup"><span data-stu-id="f2c08-124">When you have supplied all the proper values, run the resulting block at the Azure PowerShell command prompt or in the PowerShell ISE.</span></span>
  
```powershell
# Set up variables common to both virtual machines
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$subnetName="<Table R - Item 2 - Subnet name column>"
$avName="<Table A - Item 2 - Availability set name column>"
$rgNameTier="<Table R - Item 2 - Resource group name column>"
$rgNameInfra="<Table R - Item 4 - Resource group name column>"

$rgName=$rgNameInfra
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnetName
$backendSubnet=Get-AzVirtualNetworkSubnetConfig -Name $subnetName -VirtualNetwork $vnet
$webLB=Get-AzLoadBalancer -ResourceGroupName $rgName -Name "ADFSServers"

$rgName=$rgNameTier
$avSet=Get-AzAvailabilitySet -Name $avName -ResourceGroupName $rgName

# Create the first ADFS server virtual machine
$vmName="<Table M - Item 4 - Virtual machine name column>"
$vmSize="<Table M - Item 4 - Minimum size column>"
$staticIP="<Table I - Item 5 - Value column>"
$diskStorageType="<Table M - Item 4 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName -Subnet $backendSubnet -LoadBalancerBackendAddressPool $webLB.BackendAddressPools[0] -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the first AD FS server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

# Create the second AD FS virtual machine
$vmName="<Table M - Item 5 - Virtual machine name column>"
$vmSize="<Table M - Item 5 - Minimum size column>"
$staticIP="<Table I - Item 6 - Value column>"
$diskStorageType="<Table M - Item 5 - Storage type column>"

$nic=New-AzNetworkInterface -Name ($vmName +"-NIC") -ResourceGroupName $rgName -Location $locName  -Subnet $backendSubnet -LoadBalancerBackendAddressPool $webLB.BackendAddressPools[0] -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName $vmName -VMSize $vmSize -AvailabilitySetId $avset.Id

$cred=Get-Credential -Message "Type the name and password of the local administrator account for the second AD FS server." 
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName $vmName -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name ($vmName +"-OS") -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType $diskStorageType
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm

```

> [!NOTE]
> <span data-ttu-id="f2c08-p105">Da diese virtuellen Computer für eine Intranetanwendung gedacht sind, wird ihnen weder eine öffentliche IP-Adresse noch eine DNS-Domänennamenbezeichnung zugewiesen. Sie sind also nicht über das Internet erreichbar. Das bedeutet allerdings, dass Sie auch nicht über das Azure-Portal auf sie zugreifen können. Wenn Sie die Eigenschaften eines der virtuellen Computer aufrufen, ist die Option zum **Verbinden**nicht verfügbar. Verwenden Sie eine Remotedesktopverbindung oder ein anderes Remotedesktoptool, um eine Verbindung über die private IP-Adresse des betreffenden virtuellen Computers oder seinen Intranet-DNS-Namen herzustellen.</span><span class="sxs-lookup"><span data-stu-id="f2c08-p105">Because these virtual machines are for an intranet application, they are not assigned a public IP address or a DNS domain name label and exposed to the Internet. However, this also means that you cannot connect to them from the Azure portal. The **Connect** option is unavailable when you view the properties of the virtual machine. Use the Remote Desktop Connection accessory or another Remote Desktop tool to connect to the virtual machine using its private IP address or intranet DNS name.</span></span>
  
<span data-ttu-id="f2c08-p106">Erstellen Sie mithilfe eines Remotedesktopclients Ihrer Wahl eine Remotedesktopverbindung für jeden virtuellen Computer. Verwenden Sie den Intranet-DNS-Namen oder den Computernamen des jeweiligen Servers und die Anmeldeinformationen des lokalen Administratorkontos.</span><span class="sxs-lookup"><span data-stu-id="f2c08-p106">For each virtual machine, use the remote desktop client of your choice and create a remote desktop connection. Use its intranet DNS or computer name and the credentials of the local administrator account.</span></span>
  
<span data-ttu-id="f2c08-131">Fügen Sie für jeden virtuellen Computer die entsprechenden Active Directory-Domänendienste (AD DS) Domäne mit den folgenden Befehlen an der Windows PowerShell-Eingabeaufforderung ein.</span><span class="sxs-lookup"><span data-stu-id="f2c08-131">For each virtual machine, join them to the appropriate Active Directory Domain Services (AD DS) domain with these commands at the Windows PowerShell prompt.</span></span>
  
```powershell
$domName="<AD DS domain name to join, such as corp.contoso.com>"
$cred=Get-Credential -Message "Type the name and password of a domain acccount."
Add-Computer -DomainName $domName -Credential $cred
Restart-Computer
```

<span data-ttu-id="f2c08-132">Wenn Sie diese Phase erfolgreich abgeschlossen haben, sieht Ihre Konfiguration wie folgt aus. Für die Computernamen werden hier Platzhalter verwendet.</span><span class="sxs-lookup"><span data-stu-id="f2c08-132">Here is the configuration resulting from the successful completion of this phase, with placeholder computer names.</span></span>
  
<span data-ttu-id="f2c08-133">**Phase 3: Die AD FS-Server und der interne Lastenausgleich für die hohe Verfügbarkeit der Verbundauthentifizierungsinfrastruktur in Azure**</span><span class="sxs-lookup"><span data-stu-id="f2c08-133">**Phase 3: The AD FS servers and internal load balancer for your high availability federated authentication infrastructure in Azure**</span></span>

![Phase 3 der hoch verfügbaren Microsoft 365-Verbund Authentifizierungsinfrastruktur in Azure mit den AD FS-Servern](../media/f39b2d2f-8a5b-44da-b763-e1f943fcdbc4.png)
  
## <a name="next-step"></a><span data-ttu-id="f2c08-135">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="f2c08-135">Next step</span></span>

<span data-ttu-id="f2c08-136">Verwenden Sie [Phase 4: Konfigurieren von Webanwendungs Proxys](high-availability-federated-authentication-phase-4-configure-web-application-pro.md) , um mit der Konfiguration dieser Arbeitsauslastung fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="f2c08-136">Use [Phase 4: Configure web application proxies](high-availability-federated-authentication-phase-4-configure-web-application-pro.md) to continue configuring this workload.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f2c08-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2c08-137">See Also</span></span>

[<span data-ttu-id="f2c08-138">Bereitstellen der Verbundauthentifizierung mit Hochverfügbarkeit für Microsoft 365 in Azure</span><span class="sxs-lookup"><span data-stu-id="f2c08-138">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="f2c08-139">Verbundidentität für Ihre Microsoft 365-Entwicklungs-/Testumgebung</span><span class="sxs-lookup"><span data-stu-id="f2c08-139">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)


