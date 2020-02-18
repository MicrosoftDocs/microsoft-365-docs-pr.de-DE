---
title: Verbundidentität für Ihre Microsoft 365-Testumgebung
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: 65a6d687-a16a-4415-9fd5-011ba9c5fd80
description: 'Zusammenfassung: Konfigurieren der Verbundauthentifizierung für Ihre Microsoft 365-Testumgebung.'
ms.openlocfilehash: 4796f8f2a7dc6757ccbcb3d608d72ad789d34e40
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067624"
---
# <a name="federated-identity-for-your-microsoft-365-test-environment"></a><span data-ttu-id="8fb5d-103">Verbundidentität für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="8fb5d-103">Federated identity for your Microsoft 365 test environment</span></span>

<span data-ttu-id="8fb5d-104">*Diese Testumgebungsanleitung kann für Microsoft 365 Enterprise- und Office 365 Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="8fb5d-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="8fb5d-p101">Office 365 unterstützt Verbundidentität. Dies bedeutet, dass Office 365, anstatt die Prüfung von Anmeldeinformationen selbst durchzuführen, den Benutzer, der eine Verbindung herstellt, auf einen Verbundauthentifizierungsserver verweist, der für Office 365 vertrauenswürdig ist. Wenn die Anmeldeinformationen des Benutzers korrekt sind, gibt der Verbundauthentifizierungsserver ein Sicherheitstoken aus, das der Client als Nachweis der Authentifizierung an Office 365 sendet. Verbundidentität ermöglicht das Abladen und zentrale Skalieren der Authentifizierung für ein Office 365-Abonnement sowie erweiterte Authentifizierungs- und Sicherheitsszenarien.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-p101">Office 365 supports federated identity. This means that instead of performing the validation of credentials itself, Office 365 refers the connecting user to a federated authentication server that Office 365 trusts. If the user's credentials are correct, the federated authentication server issues a security token that the client then sends to Office 365 as proof of authentication. Federated identity allows for the offloading and scaling up of authentication for an Office 365 subscription and advanced authentication and security scenarios.</span></span>
  
<span data-ttu-id="8fb5d-109">In diesem Artikel wird beschrieben, wie Sie die Verbundauthentifizierung für Ihre Microsoft 365- oder Office 365-Testumgebung konfigurieren können, die zu Folgendem führt:</span><span class="sxs-lookup"><span data-stu-id="8fb5d-109">This article describes how you can configure federated authentication for your Microsoft 365 or Office 365 test environment, resulting in the following:</span></span>

![Die Verbundauthentifizierung für die Microsoft 365-Testumgebung](../media/federated-identity-for-your-office-365-dev-test-environment/federated-tlg-phase3.png)
  
<span data-ttu-id="8fb5d-111">Diese Konfiguration besteht aus:</span><span class="sxs-lookup"><span data-stu-id="8fb5d-111">This configuration consists of:</span></span> 
  
- <span data-ttu-id="8fb5d-112">Eine Testversion oder ein Produktionsabonnement für Microsoft 365 E5 oder Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-112">A Microsoft 365 E5 or Office 365 E5 trial or production subscription.</span></span>
    
- <span data-ttu-id="8fb5d-p102">Einem vereinfachten Unternehmensintranet, das mit dem Internet verbunden ist, bestehend aus fünf virtuellen Computern in einem Subnetz eines virtuellen Azure-Netzwerks (DC1, APP1, CLIENT1, ADFS1 und PROXY1). Azure AD Connect wird auf APP1 ausgeführt, um die Liste von Konten in der Active Directory Domain Services-Domäne mit Office 365 zu synchronisieren. PROXY1 erhält die eingehenden Authentifizierungsanfragen. ADFS1 überprüft Anmeldeinformationen mit DC1 und gibt Sicherheitstoken aus.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-p102">A simplified organization intranet connected to the Internet, consisting of five virtual machines on a subnet of an Azure virtual network (DC1, APP1, CLIENT1, ADFS1, and PROXY1). Azure AD Connect runs on APP1 to synchronize the list of accounts in the Active Directory Domain Services domain to Office 365. PROXY1 receives the incoming authentication requests. ADFS1 validates credentials with DC1 and issues security tokens.</span></span>
    
<span data-ttu-id="8fb5d-117">Das Einrichten dieser Testumgebung besteht aus fünf Phasen:</span><span class="sxs-lookup"><span data-stu-id="8fb5d-117">There are five phases to setting up this test environment:</span></span>
  
1. <span data-ttu-id="8fb5d-118">Erstellen Sie die simulierte Testunternehmensumgebung mit Kennworthashsynchronisierung.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-118">Create the simulated enterprise test environment with password hash synchronization.</span></span>
    
2. <span data-ttu-id="8fb5d-119">Erstellen des AD FS-Servers (ADFS1).</span><span class="sxs-lookup"><span data-stu-id="8fb5d-119">Create the AD FS server (ADFS1).</span></span>
    
3. <span data-ttu-id="8fb5d-120">Erstellen des Webproxyservers (PROXY1).</span><span class="sxs-lookup"><span data-stu-id="8fb5d-120">Create the web proxy server (PROXY1).</span></span>
    
4. <span data-ttu-id="8fb5d-121">Erstellen eines selbstsignierten Zertifikats und Konfigurieren von ADFS1 und PROXY1.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-121">Create a self-signed certificate and configure ADFS1 and PROXY1.</span></span>
    
5. <span data-ttu-id="8fb5d-122">Konfigurieren von Office 365 für Verbundidentität.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-122">Configure Office 365 for federated identity.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8fb5d-123">Sie können diese Testumgebung nicht mit einem Azure-Testabonnement konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-123">You cannot configure this test environment with an Azure Trial subscription.</span></span> 
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="8fb5d-124">Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="8fb5d-124">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="8fb5d-p103">Befolgen Sie die Anweisungen unter [Kennworthashsynchronisierung für Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Hier ist die resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-p103">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](../media/federated-identity-for-your-office-365-dev-test-environment/federated-tlg-phase1.png)
  
<span data-ttu-id="8fb5d-128">Diese Konfiguration besteht aus: </span><span class="sxs-lookup"><span data-stu-id="8fb5d-128">This configuration consists of:</span></span> 
  
- <span data-ttu-id="8fb5d-129">Eine Testversion oder ein kostenpflichtiges Abonnement für Microsoft 365 E5 oder Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-129">A Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="8fb5d-130">Einem vereinfachtem Unternehmensintranet mit Internetzugriff, das aus virtuellen DC1-, APP1- und CLIENT1-Computern in einem Subnetz eines virtuellen Azure-Netzwerks besteht.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-130">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="8fb5d-131">Azure AD Connect wird auf APP1 ausgeführt, um die AD DS-Domäne "TESTLAB" mit dem Azure AD-Mandanten Ihrer Microsoft 365- oder Office 365 E5-Abonnements regelmäßig zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-131">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 or Office 365 subscriptions periodically.</span></span>

## <a name="phase-2-create-the-ad-fs-server"></a><span data-ttu-id="8fb5d-132">Phase 2: Erstellen des AD FS-Servers</span><span class="sxs-lookup"><span data-stu-id="8fb5d-132">Phase 2: Create the AD FS server</span></span>

<span data-ttu-id="8fb5d-133">Ein AD FS-Server bietet Verbundauthentifizierung zwischen Office 365 und den Konten in der Domäne „corp.contoso.com“, die auf DC1 gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-133">An AD FS server provides federated authentication between Office 365 and the accounts in the corp.contoso.com domain hosted on DC1.</span></span>
  
<span data-ttu-id="8fb5d-134">Um einen virtuellen Azure-Computer für ADFS1 zu erstellen, geben Sie den Namen Ihres Abonnements und der Ressourcengruppe sowie den Azure-Speicherort für Ihre Basiskonfiguration ein, und führen Sie diese Befehle in der Azure PowerShell-Befehlszeile auf Ihrem lokalen Computer aus.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-134">To create an Azure virtual machine for ADFS1, fill in the name of your subscription and the resource group and Azure location for your Base Configuration, and then run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$subscrName="<your Azure subscription name>"
$rgName="<the resource group name of your Base Configuration>"
$vnetName="TlgBaseConfig-01-VNET"
# NOTE: If you built your simulated intranet with Azure PowerShell, comment the previous line with a "#" and remove the "#" from the next line.
#$vnetName="TestLab"
Connect-AzAccount
Select-AzSubscription -SubscriptionName $subscrName
$staticIP="10.0.0.100"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$pip = New-AzPublicIpAddress -Name ADFS1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic = New-AzNetworkInterface -Name ADFS1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName ADFS1 -VMSize Standard_D2_v2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for ADFS1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName ADFS1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "ADFS-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

<span data-ttu-id="8fb5d-135">Im nächsten Schritt stellen Sie über das [Azure-Portal](https://portal.azure.com) eine Verbindung mit dem virtuellen Computer ADFS1 mit dem Namen und Kennwort des lokalen Administratorkontos von ADFS1 her und öffnen dann eine Windows PowerShell-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-135">Next, use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the ADFS1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="8fb5d-136">Führen Sie zum Überprüfen der Namensauflösung und der Netzwerkkommunikation zwischen ADFS1 und DC1 den Befehl **ping dc1.corp.contoso.com** aus, und vergewissern Sie sich, dass vier Antworten vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-136">To check name resolution and network communication between ADFS1 and DC1, run the **ping dc1.corp.contoso.com** command and check that there are four replies.</span></span>
  
<span data-ttu-id="8fb5d-137">Verknüpfen Sie als Nächstes unter Verwendung der folgenden Befehle an der Windows PowerShell-Eingabeaufforderung auf ADFS1 den virtuellen Computer ADFS1 mit der Domäne CORP.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-137">Next, join the ADFS1 virtual machine to the CORP domain with these commands at the Windows PowerShell prompt on ADFS1.</span></span>
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

<span data-ttu-id="8fb5d-138">Nachfolgend sehen Sie die daraus resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-138">Here is your resulting configuration.</span></span>
  
![Der AD FS-Server, der der DirSync für die Microsoft 365-Testumgebung hinzugefügt wurde](../media/federated-identity-for-your-office-365-dev-test-environment/federated-tlg-phase2.png)
  
## <a name="phase-3-create-the-web-proxy-server"></a><span data-ttu-id="8fb5d-140">Phase 3: Erstellen des Webproxyservers</span><span class="sxs-lookup"><span data-stu-id="8fb5d-140">Phase 3: Create the web proxy server</span></span>

<span data-ttu-id="8fb5d-141">PROXY1 stellt die Proxyfunktion für Authentifizierungsnachrichten zwischen Benutzern, die versuchen, sich zu authentifizieren, und ADFS1 bereit.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-141">PROXY1 provides proxying of authentication messages between users trying to authenticate and ADFS1.</span></span>
  
<span data-ttu-id="8fb5d-142">Um einen virtuellen Azure-Computer für PROXY1 zu erstellen, geben Sie den Namen Ihrer Ressourcengruppe und den Azure-Speicherort ein und führen diese Befehle in der Azure PowerShell-Befehlszeile auf Ihrem lokalen Computer aus.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-142">To create an Azure virtual machine for PROXY1, fill in the name of your resource group and Azure location, and then run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
$vnetName="TlgBaseConfig-01-VNET"
# NOTE: If you built your simulated intranet with Azure PowerShell, comment the previous line with a "#" and remove the "#" from the next line.
#$vnetName="TestLab"
$staticIP="10.0.0.101"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$pip = New-AzPublicIpAddress -Name PROXY1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Static
$nic = New-AzNetworkInterface -Name PROXY1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName PROXY1 -VMSize Standard_D2_v2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for PROXY1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName PROXY1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "PROXY1-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> <span data-ttu-id="8fb5d-143">PROXY1 wird einer statischen öffentlichen IP-Adresse zugewiesen, da Sie einen öffentlichen DNS-Eintrag erstellen, der darauf verweist, und der nicht geändert werden muss, wenn Sie den virtuellen PROXY1-Computer neu starten.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-143">PROXY1 is assigned a static public IP address because you will create a public DNS record that points to it and it must not change when you restart the PROXY1 virtual machine.</span></span> 
  
<span data-ttu-id="8fb5d-p105">Fügen Sie als Nächstes eine Regel zu der Netzwerksicherheitsgruppe für das CorpNet-Subnetz hinzu, um unerwünschten eingehenden Verkehr aus dem Internet an die private IP-Adresse von PROXY1 und den TCP-Port 443 zuzulassen. Führen Sie diese Befehle an der Azure PowerShell-Eingabeaufforderung auf dem lokalen Computer aus.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-p105">Next, add a rule to the network security group for the CorpNet subnet to allow unsolicited inbound traffic from the Internet to PROXY1's private IP address and TCP port 443. Run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
Get-AzNetworkSecurityGroup -Name CorpNet -ResourceGroupName $rgName | Add-AzNetworkSecurityRuleConfig -Name "HTTPS-to-PROXY1" -Description "Allow TCP 443 to PROXY1" -Access "Allow" -Protocol "Tcp" -Direction "Inbound" -Priority 101 -SourceAddressPrefix "Internet" -SourcePortRange "*" -DestinationAddressPrefix "10.0.0.101" -DestinationPortRange "443" | Set-AzNetworkSecurityGroup
```

<span data-ttu-id="8fb5d-146">Im nächsten Schritt stellen Sie über das [Azure-Portal](https://portal.azure.com) eine Verbindung mit dem virtuellen Computer PROXY1 mit dem Kontonamen und Kennwort des lokalen Administratorkontos von PROXY1 her und öffnen dann eine Windows PowerShell-Eingabeaufforderung auf PROXY1.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-146">Next, use the [Azure portal](https://portal.azure.com) to connect to the PROXY1 virtual machine using the PROXY1 local administrator account name and password, and then open a Windows PowerShell command prompt on PROXY1.</span></span>
  
<span data-ttu-id="8fb5d-147">Führen Sie zum Überprüfen der Namensauflösung und der Netzwerkkommunikation zwischen PROXY1 und DC1 den Befehl **ping dc1.corp.contoso.com** aus, und vergewissern Sie sich, dass vier Antworten vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-147">To check name resolution and network communication between PROXY1 and DC1, run the **ping dc1.corp.contoso.com** command and check that there are four replies.</span></span>
  
<span data-ttu-id="8fb5d-148">Verknüpfen Sie als Nächstes unter Verwendung der folgenden Befehle an der Windows PowerShell-Eingabeaufforderung auf PROXY1 den virtuellen Computer PROXY1 mit der Domäne CORP.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-148">Next, join the PROXY1 virtual machine to the CORP domain with these commands at the Windows PowerShell prompt on PROXY1.</span></span>
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

<span data-ttu-id="8fb5d-149">Zeigen Sie die öffentliche IP-Adresse von PROXY1 mit den folgenden Azure PowerShell-Befehlen auf dem lokalen Computer an:</span><span class="sxs-lookup"><span data-stu-id="8fb5d-149">Display the public IP address of PROXY1 with these Azure PowerShell commands on your local computer:</span></span>
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "PROXY1-PIP" -ResourceGroup $rgName).IPAddress
```

<span data-ttu-id="8fb5d-p106">Im nächsten Schritt arbeiten Sie mit Ihrem öffentlichen DNS-Anbieter und erstellen einen neuen öffentlichen DNS A-Eintrag für **fs.testlab.**\<Ihr DNS-Domänenname>, der in die IP-Adresse aufgelöst wird, die vom Befehl **Write-Host** angezeigt wird. Auf **fs.testlab.**\<Ihr DNS-Domänenname> wird nachfolgend als *FQDN des Verbunddiensts* verwiesen.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-p106">Next, work with your public DNS provider and create a new public DNS A record for **fs.testlab.**\<your DNS domain name> that resolves to the IP address displayed by the **Write-Host** command. The **fs.testlab.**\<your DNS domain name> is hereafter referred to as the  *federation service FQDN*.</span></span>
  
<span data-ttu-id="8fb5d-152">Im nächsten Schritt stellen Sie über das [Azure-Portal](https://portal.azure.com) eine Verbindung mit dem virtuellen Computer DC1 unter Verwendung der Anmeldeinformationen „CORP\\User1“ her und führen dann die folgenden Befehle an einer Windows PowerShell-Eingabeaufforderung auf Administratorebene aus:</span><span class="sxs-lookup"><span data-stu-id="8fb5d-152">Next, use the [Azure portal](https://portal.azure.com) to connect to the DC1 virtual machine using the CORP\\User1 credentials, and then run the following commands at an administrator-level Windows PowerShell command prompt:</span></span>
  
```powershell
Add-DnsServerPrimaryZone -Name corp.contoso.com -ZoneFile corp.contoso.com.dns
Add-DnsServerResourceRecordA -Name "fs" -ZoneName corp.contoso.com -AllowUpdateAny -IPv4Address "10.0.0.100" -TimeToLive 01:00:00
```
<span data-ttu-id="8fb5d-153">Diese Befehle erstellen einen internen DNS-A-Eintrag, sodass virtuelle Computer im virtuellen Azure-Netzwerk den internen FQDN des Verbunddiensts in die private IP-Adresse von ADFS1 auflösen können.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-153">These commands create an internal DNS A record so that virtual machines on the Azure virtual network can resolve the internal federation FQDN to ADFS1's private IP address.</span></span>
  
<span data-ttu-id="8fb5d-154">Nachfolgend sehen Sie die daraus resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-154">Here is your resulting configuration.</span></span>
  
![Der Webanwendungs-Proxyserver, der der DirSync für die Microsoft 365-Testumgebung hinzugefügt wurde](../media/federated-identity-for-your-office-365-dev-test-environment/federated-tlg-phase3.png)
  
## <a name="phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1"></a><span data-ttu-id="8fb5d-156">Phase 4: Erstellen eines selbstsignierten Zertifikats und Konfigurieren von ADFS1 und PROXY1</span><span class="sxs-lookup"><span data-stu-id="8fb5d-156">Phase 4: Create a self-signed certificate and configure ADFS1 and PROXY1</span></span>

<span data-ttu-id="8fb5d-157">In dieser Phase erstellen Sie ein selbstsigniertes digitales Zertifikat für den FQDN des Verbunddiensts und konfigurieren ADFS1 und PROXY1 als AD FS-Farm.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-157">In this phase, you create a self-signed digital certificate for your federation service FQDN and configure ADFS1 and PROXY1 as an AD FS farm.</span></span>
  
<span data-ttu-id="8fb5d-158">Im nächsten Schritt stellen Sie über das [Azure-Portal](https://portal.azure.com) eine Verbindung mit dem virtuellen Computer DC1 unter Verwendung der Anmeldeinformationen „CORP\\User1“ her und öffnen dann eine Windows PowerShell-Eingabeaufforderung auf Administratorebene.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-158">First, use the [Azure portal](https://portal.azure.com) to connect to the DC1 virtual machine using the CORP\\User1 credentials, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="8fb5d-159">Im nächsten Schritt erstellen Sie das AD FS-Dienstkonto mit dem folgenden Befehl an der Windows PowerShell-Eingabeaufforderung auf DC1:</span><span class="sxs-lookup"><span data-stu-id="8fb5d-159">Next, create AD FS service account with this command at the Windows PowerShell command prompt on DC1:</span></span>
  
```powershell
New-ADUser -SamAccountName ADFS-Service -AccountPassword (read-host "Set user password" -assecurestring) -name "ADFS-Service" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```
<span data-ttu-id="8fb5d-p107">Beachten Sie, dass Sie von dem Befehl aufgefordert werden, das Kontokennwort anzugeben. Verwenden Sie ein sicheres Kennwort, und notieren Sie es an einem sicheren Ort. Sie benötigen es für diese Phase und für Phase 5.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-p107">Note that this command prompts you to supply the account password. Choose a strong password and record it in a secured location. You will need it for this phase and Phase 5.</span></span>
  
<span data-ttu-id="8fb5d-p108">Verwenden Sie das [Azure-Portal](https://portal.azure.com), um eine Verbindung zu dem virtuellen Computer ADFS1 unter Verwendung der Anmeldeinformationen „CORP\\User1“ herzustellen. Öffnen Sie eine Windows PowerShell-Eingabeaufforderung auf Administratorebene auf ADFS1, geben Sie den FQDN des Verbunddiensts ein, und führen Sie dann die folgenden Befehle aus, um ein selbstsigniertes Zertifikat zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="8fb5d-p108">Use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the CORP\\User1 credentials. Open an administrator-level Windows PowerShell command prompt on ADFS1, fill in your federation service FQDN, and then run these commands to create a self-signed certificate:</span></span>
  
```powershell
$fedServiceFQDN="<federation service FQDN>"
New-SelfSignedCertificate -DnsName $fedServiceFQDN -CertStoreLocation "cert:\LocalMachine\My"
New-Item -path c:\Certs -type directory
New-SmbShare -name Certs -path c:\Certs -changeaccess CORP\User1
```

<span data-ttu-id="8fb5d-165">Gehen Sie dann folgendermaßen vor, um das neue selbstsignierte Zertifikat als Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-165">Next, use these steps to save the new self-signed certificate as a file.</span></span>
  
1. <span data-ttu-id="8fb5d-166">Klicken Sie auf **Start**, geben Sie **mmc.exe** ein, und drücken Sie dann die  **EINGABETASTE**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-166">Click **Start**, type **mmc.exe**, and then press **Enter**.</span></span>
    
2. <span data-ttu-id="8fb5d-167">Klicken Sie auf **Datei > Snap-In hinzufügen/entfernen**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-167">Click **File > Add/Remove Snap-in**.</span></span>
    
3. <span data-ttu-id="8fb5d-168">Doppelklicken Sie unter **Snap-In hinzufügen/entfernen** in der Liste verfügbarer Snap-Ins auf **Zertifikate**, klicken Sie auf **Computerkonto**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-168">In **Add or Remove Snap-ins**, double-click **Certificates** in the list of available snap-ins, click **Computer account**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="8fb5d-169">Klicken Sie unter **Computer auswählen** auf **Fertig stellen**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-169">In **Select Computer**, click **Finish**, and then click **OK**.</span></span>
    
5. <span data-ttu-id="8fb5d-170">Öffnen Sie im Strukturbereich **Zertifikate (Lokaler Computer) > Persönlich > Zertifikate**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-170">In the tree pane, open **Certificates (Local Computer) > Personal > Certificates**.</span></span>
    
6. <span data-ttu-id="8fb5d-171">Klicken Sie mit der rechten Maustaste auf das Zertifikat mit dem FQDN des Verbunddiensts, klicken Sie auf **Alle Vorgänge**, und klicken Sie dann auf **Exportieren**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-171">Right-click the certificate with your federation service FQDN, click **All tasks**, and then click **Export**.</span></span>
    
7. <span data-ttu-id="8fb5d-172">Klicken Sie auf der Seite **Willkommen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-172">On the **Welcome** page, click **Next**.</span></span>
    
8. <span data-ttu-id="8fb5d-173">Klicken Sie auf der Seite **Privaten Schlüssel exportieren** auf **Ja** und dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-173">On the **Export Private Key** page, click **Yes**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="8fb5d-174">Klicken Sie auf der Seite **Dateiformat exportieren** auf **Alle erweiterten Eigenschaften exportieren**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-174">On the **Export File Format** page, click **Export all extended properties**, and then click **Next**.</span></span>
    
10. <span data-ttu-id="8fb5d-175">Klicken Sie auf der Seite **Sicherheit** auf **Kennwort**, und geben Sie unter **Kennwort** und **Kennwort bestätigen** ein Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-175">On the **Security** page, click **Password** and type a password in **Password** and **Confirm password.**</span></span>
    
11. <span data-ttu-id="8fb5d-176">Klicken Sie auf der Seite **Zu exportierende Datei** auf **Durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-176">On the **File to Export** page, click **Browse**.</span></span>
    
12. <span data-ttu-id="8fb5d-177">Navigieren Sie zum Ordner **C:\\Certs**, geben Sie **SSL** unter **Dateiname** ein, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-177">Browse to the **C:\\Certs** folder, type **SSL** in **File name**, and then click **Save.**</span></span>
    
13. <span data-ttu-id="8fb5d-178">Klicken Sie auf der Seite **Zu exportierende Datei** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-178">On the **File to Export** page, click **Next**.</span></span>
    
14. <span data-ttu-id="8fb5d-p109">Klicken Sie auf der Seite **Fertigstellen des Assistenten** auf **Fertig stellen**. Wenn Sie dazu aufgefordert werden, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-p109">On the **Completing the Certificate Export Wizard** page, click **Finish**. When prompted, click **OK**.</span></span>
    
<span data-ttu-id="8fb5d-181">Im nächsten Schritt erstellen Sie den AD FS-Dienst mit dem folgenden Befehl an der Windows PowerShell-Eingabeaufforderung auf ADFS1:</span><span class="sxs-lookup"><span data-stu-id="8fb5d-181">Next, install the AD FS service with this command at the Windows PowerShell command prompt on ADFS1:</span></span>
  
```powershell
Install-WindowsFeature ADFS-Federation -IncludeManagementTools
```

<span data-ttu-id="8fb5d-182">Warten Sie, bis die Installation abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-182">Wait for the installation to complete.</span></span>
  
<span data-ttu-id="8fb5d-183">Konfigurieren Sie als Nächstes den AD FS-Dienst mit den folgenden Schritten:</span><span class="sxs-lookup"><span data-stu-id="8fb5d-183">Next, configure the AD FS service with these steps:</span></span>
  
1. <span data-ttu-id="8fb5d-184">Klicken Sie auf **Start** und dann auf das Symbol **Server-Manager**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-184">Click **Start**, and then click the **Server Manager** icon.</span></span>
    
2. <span data-ttu-id="8fb5d-185">Klicken Sie im Strukturbereich des Server-Managers auf **Features**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-185">In the tree pane of Server Manager, click **AD FS**.</span></span>
    
3. <span data-ttu-id="8fb5d-186">Klicken Sie in der Symbolleiste oben auf das orange Warnsymbol, und klicken Sie dann auf **Verbunddienst auf diesem Server konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-186">In the tool bar at the top, click the orange caution symbol, and then click **Configure the federation service on this server**.</span></span>
    
4. <span data-ttu-id="8fb5d-187">Klicken Sie auf der **Willkommensseite** des Assistenten zum Konfigurieren von Active Directory-Verbunddiensten auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-187">On the **Welcome** page of the Active Directory Federation Services Configuration Wizard, click **Next**.</span></span>
    
5. <span data-ttu-id="8fb5d-188">Klicken Sie auf der Seite **Mit AD DS verbinden** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-188">On the **Connect to AD DS** page, click **Next**.</span></span>
    
6. <span data-ttu-id="8fb5d-189">Auf der Seite **Diensteigenschaften angeben**:</span><span class="sxs-lookup"><span data-stu-id="8fb5d-189">On the **Specify Service Properties** page:</span></span>
    
  - <span data-ttu-id="8fb5d-190">Klicken Sie für **SSL-Zertifikat** auf den Pfeil nach unten, und klicken Sie dann auf das Zertifikat mit dem Namen des FQDN des Verbunddiensts.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-190">For **SSL Certificate**, click the down arrow, and then click the certificate with the name of your federation service FQDN.</span></span>
    
  - <span data-ttu-id="8fb5d-191">Geben Sie unter **Anzeigename des Verbunddiensts** den Namen Ihrer fiktiven Organisation ein.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-191">In **Federation Service Display Name**, type the name of your fictional organization.</span></span>
    
  - <span data-ttu-id="8fb5d-192">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-192">Click **Next**.</span></span>
    
7. <span data-ttu-id="8fb5d-193">Klicken Sie auf der Seite **Dienstkonto angeben** auf **Auswählen** für **Kontoname**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-193">On the **Specify Service Account** page, click **Select** for **Account name**.</span></span>
    
8. <span data-ttu-id="8fb5d-194">Geben Sie unter **Benutzer oder Dienstkonto auswählen** den Text **ADFS-Service** ein, klicken Sie auf **Namen überprüfen**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-194">In **Select User or Service Account**, type **ADFS-Service**, click **Check Names**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="8fb5d-195">Geben Sie unter **Kontokennwort** das Kennwort für das ADFS-Dienstkonto ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-195">In **Account Password**, type the password for the ADFS-Service account, and then click **Next**.</span></span>
    
10. <span data-ttu-id="8fb5d-196">Klicken Sie auf der Seite **Konfigurationsdatenbank angeben** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-196">On the **Specify Configuration Database** page, click **Next**.</span></span>
    
11. <span data-ttu-id="8fb5d-197">Klicken Sie auf der Seite **Optionen prüfen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-197">On the **Review Options** page, click **Next**.</span></span>
    
12. <span data-ttu-id="8fb5d-198">Klicken Sie auf der Seite **Voraussetzungsprüfungen** auf **Konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-198">On the **Pre-requisite Checks** page, click **Configure**.</span></span>
    
13. <span data-ttu-id="8fb5d-199">Klicken Sie auf der Seite **Ergebnisse** auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-199">On the **Results** page, click **Close**.</span></span>
    
14. <span data-ttu-id="8fb5d-200">Klicken Sie auf **Start**, klicken Sie auf das Ein-/Ausschaltsymbol, klicken Sie auf **Neu starten**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-200">Click **Start**, click the power icon, click **Restart**, and then click **Continue**.</span></span>
    
<span data-ttu-id="8fb5d-201">Melden Sie sich über das [Azure-Portal](https://portal.azure.com) mit dem CORP\\User1-Konto bei PROXY1 an.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-201">From the [Azure portal](https://portal.azure.com), connect to PROXY1 with the CORP\\User1 account credentials.</span></span>
  
<span data-ttu-id="8fb5d-202">Gehen Sie dann folgendermaßen vor, um das selbstsignierte Zertifikat zu installieren und PROXY1 zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-202">Next, use these steps to install the self-signed certificate and configure PROXY1.</span></span>
  
1. <span data-ttu-id="8fb5d-203">Klicken Sie auf **Start**, geben Sie **mmc.exe** ein, und drücken Sie dann die  **EINGABETASTE**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-203">Click **Start**, type **mmc.exe**, and then press **Enter**.</span></span>
    
2. <span data-ttu-id="8fb5d-204">Klicken Sie auf **Datei > Snap-In hinzufügen/entfernen**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-204">Click **File > Add/Remove Snap-in**.</span></span>
    
3. <span data-ttu-id="8fb5d-205">Doppelklicken Sie unter **Snap-In hinzufügen/entfernen** in der Liste verfügbarer Snap-Ins auf **Zertifikate**, klicken Sie auf **Computerkonto**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-205">In **Add or Remove Snap-ins**, double-click **Certificates** in the list of available snap-ins, click **Computer account**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="8fb5d-206">Klicken Sie unter **Computer auswählen** auf **Fertig stellen**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-206">In **Select Computer**, click **Finish**, and then click **OK**.</span></span>
    
5. <span data-ttu-id="8fb5d-207">Öffnen Sie im Strukturbereich **Zertifikate (Lokaler Computer) > Persönlich > Zertifikate**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-207">In the tree pane, open **Certificates (Local Computer) > Personal > Certificates**.</span></span>
    
6. <span data-ttu-id="8fb5d-208">Klicken Sie mit der rechten Maustaste auf **Persönlich**, wählen Sie **Alle Tasks** aus, und klicken Sie dann auf **Importieren**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-208">Right-click **Personal**, click **All tasks**, and then click **Import**.</span></span>
    
7. <span data-ttu-id="8fb5d-209">Klicken Sie auf der Seite **Willkommen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-209">On the **Welcome** page, click **Next**.</span></span>
    
8. <span data-ttu-id="8fb5d-210">Geben Sie auf der Seite **Zu importierende Datei** den Namen **\\\\adfs1\\certs\\ssl.pfx** ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-210">On the **File to Import** page, type **\\\\adfs1\\certs\\ssl.pfx**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="8fb5d-211">Geben Sie auf der Seite **Schutz durch privaten Schlüssel** das Kennwort des Zertifikats unter **Kennwort** ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-211">On the **Private key protection** page, type the certificate password in **Password**, and then click **Next.**</span></span>
    
10. <span data-ttu-id="8fb5d-212">Klicken Sie auf der Seite **Zertifikatspeicher** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-212">On the **Certificate store** page, click **Next.**</span></span>
    
11. <span data-ttu-id="8fb5d-213">Klicken Sie auf der Seite **Fertigstellung** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-213">On the **Completing** page, click **Finish**.</span></span>
    
12. <span data-ttu-id="8fb5d-214">Klicken Sie auf der Seite **Zertifikatspeicher** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-214">On the **Certificate Store** page, click **Next**.</span></span>
    
13. <span data-ttu-id="8fb5d-215">Klicken Sie auf **OK**, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-215">When prompted, click **OK**.</span></span>
    
14. <span data-ttu-id="8fb5d-216">Klicken Sie in der Strukturansicht auf **Zertifikate**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-216">Click **Certificates** in the tree pane.</span></span>
    
15. <span data-ttu-id="8fb5d-217">Klicken Sie mit der rechten Maustaste auf das Zertifikat, und klicken Sie dann auf **Kopieren**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-217">Right-click the certificate, and then click **Copy**.</span></span>
    
16. <span data-ttu-id="8fb5d-218">Öffnen Sie im Strukturbereich **Vertrauenswürdige Stammzertifizierungsstellen > Zertifizierungsstellen**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-218">In the tree pane, open **Trusted Root Certification Authorities > Certificates**.</span></span>
    
17. <span data-ttu-id="8fb5d-219">Verschieben Sie den Mauszeiger unter die Liste der installierten Zertifikate, klicken Sie mit der rechten Maustaste, und klicken Sie dann auf **Einfügen**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-219">Move your mouse pointer below the list of installed certificates, right-click, and then click **Paste**.</span></span>
    
<span data-ttu-id="8fb5d-220">Öffnen Sie eine PowerShell-Eingabeaufforderung auf Administratorebene, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="8fb5d-220">Open an administrator-level PowerShell command prompt and run the following command:</span></span>
  
```powershell
Install-WindowsFeature Web-Application-Proxy -IncludeManagementTools
```

<span data-ttu-id="8fb5d-221">Warten Sie, bis die Installation abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-221">Wait for the installation to complete.</span></span>
  
<span data-ttu-id="8fb5d-222">Verwenden Sie die folgenden Schritte, um den Webanwendungs-Proxydienst so zu konfigurieren, dass ADFS1 als Verbundserver verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="8fb5d-222">Use these steps to configure the web application proxy service to use ADFS1 as its federation server:</span></span>
  
1. <span data-ttu-id="8fb5d-223">Klicken Sie auf **Start** und dann auf **Server-Manager**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-223">Click **Start**, and then click **Server Manager**.</span></span>
    
2. <span data-ttu-id="8fb5d-224">Klicken Sie in der Strukturansicht auf **Remotezugriff**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-224">In the tree pane, click **Remote Access**.</span></span>
    
3. <span data-ttu-id="8fb5d-225">Klicken Sie in der Symbolleiste oben auf das orange Warnsymbol, und klicken Sie dann auf **Assistent für Webanwendungsproxy öffnen**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-225">In the tool bar at the top, click the orange caution symbol, and then click **Open the Web Application Proxy Wizard**.</span></span>
    
4. <span data-ttu-id="8fb5d-226">Klicken Sie auf der **Willkommensseite** des Assistenten zum Konfigurieren des Webanwendungsproxys auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-226">On the **Welcome** page of the Web Application Proxy Configuration Wizard, click **Next**.</span></span>
    
5. <span data-ttu-id="8fb5d-227">Auf der Seite **Verbundserver**:</span><span class="sxs-lookup"><span data-stu-id="8fb5d-227">On the **Federation Server** page:</span></span>
    
  - <span data-ttu-id="8fb5d-228">Geben Sie unter **Verbunddienstname** den FQDN des Verbunddiensts ein.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-228">Type your federation service FQDN in **Federation service name**.</span></span>
    
  - <span data-ttu-id="8fb5d-229">Geben Sie **CORP\\User1** unter **Benutzername** ein.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-229">Type **CORP\\User1** in **User name**.</span></span>
    
  - <span data-ttu-id="8fb5d-230">Geben Sie das Kennwort des User1-Kontos unter **Kennwort** ein.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-230">Type the password for the User1 account in **Password**.</span></span>
    
  - <span data-ttu-id="8fb5d-231">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-231">Click **Next**.</span></span>
    
6. <span data-ttu-id="8fb5d-232">Klicken Sie auf der Seite **AD FS-Proxyzertifikat** auf den Pfeil nach unten, klicken Sie dann auf das Zertifikat mit dem FQDN des Verbunddiensts, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-232">On the **AD FS Proxy Certificate** page, click the down arrow, click the certificate with your federation service FQDN, and then click **Next**.</span></span>
    
7. <span data-ttu-id="8fb5d-233">Klicken Sie auf der Seite **Bestätigung** auf **Konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-233">On the **Confirmation** page, click **Configure**.</span></span>
    
8. <span data-ttu-id="8fb5d-234">Klicken Sie auf der Seite **Ergebnisse** auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-234">On the **Results** page, click **Close**.</span></span>

    
## <a name="phase-5-configure-office-365-for-federated-identity"></a><span data-ttu-id="8fb5d-235">Phase 5: Konfigurieren von Office 365 für Verbundidentität</span><span class="sxs-lookup"><span data-stu-id="8fb5d-235">Phase 5: Configure Office 365 for federated identity</span></span>

<span data-ttu-id="8fb5d-236">Verwenden Sie das [Azure-Portal](https://portal.azure.com), um eine Verbindung zu dem virtuellen Computer APP1 unter Verwendung der Kontoanmeldeinformationen „CORP\\User1“ herzustellen.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-236">Use the [Azure portal](https://portal.azure.com) to connect to the APP1 virtual machine with the CORP\\User1 account credentials.</span></span>
  
<span data-ttu-id="8fb5d-237">Verwenden Sie diese Schritte, um Azure AD Connect und Ihr Office 365-Abonnement für die Verbundauthentifizierung zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="8fb5d-237">Use these steps to configure Azure AD Connect and your Office 365 subscription for federated authentication:</span></span>
  
1. <span data-ttu-id="8fb5d-238">Doppelklicken Sie auf dem Desktop auf **Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-238">From the desktop, double-click **Azure AD Connect**.</span></span>
    
2. <span data-ttu-id="8fb5d-239">Klicken Sie auf der Seite **Willkommen bei Azure AD Connect** auf **Konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-239">On the **Welcome to Azure AD Connect** page, click **Configure**.</span></span>
    
3. <span data-ttu-id="8fb5d-240">Klicken Sie auf der Seite **Weitere Aufgaben** auf **Benutzeranmeldung ändern**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-240">On the **Additional tasks** page, click **Change user sign-in**, and then click **Next**.</span></span>
    
4. <span data-ttu-id="8fb5d-241">Geben Sie auf der Seite **Mit Azure AD verbinden** den Namen und das Kennwort für das globale Office 365-Administratorkonto ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-241">On the **Connect to Azure AD** page, type your Office 365 global administrator account name and password, and then click **Next**.</span></span>
    
5. <span data-ttu-id="8fb5d-242">Klicken Sie auf der Seite **Benutzeranmeldung** auf **Verbund mit AD FS**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-242">On the **User sign-in** page, click **Federation with AD FS**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="8fb5d-243">Klicken Sie auf der Seite **AD FS-Farm** auf **Vorhandene AD FS-Farm verwenden**, geben Sie **ADFS1** unter **Servername** ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-243">On the **AD FS farm** page, click **Use an existing AD FS farm**, type **ADFS1** in **Server Name**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="8fb5d-244">Wenn Sie aufgefordert werden, Serveranmeldeinformationen einzugeben, geben Sie die Anmeldeinformationen des Kontos „CORP\\User1“ ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-244">When prompted for server credentials, enter the credentials of the CORP\\User1 account, and then click **OK**.</span></span>
    
8. <span data-ttu-id="8fb5d-245">Geben Sie auf der Seite mit den Anmeldeinformationen für den **Domänenadministrator** unter **Benutzername** den Namen **CORP\\User1** und unter **Kennwort** das Kontokennwort ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-245">On the **Domain Administrator** credentials page, type **CORP\\User1** in **Username** and the account password in **Password**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="8fb5d-246">Geben Sie auf der Seite **AD FS-Dienstkonto** den Namen **CORP\\ADFS-Service** unter **Domänenbenutzername** und das Kontokennwort unter **Domänenbenutzerkennwort** ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-246">On the **AD FS service account** page, type **CORP\\ADFS-Service** in **Domain Username** and the account password in **Domain User Password**, and then click **Next**.</span></span>
    
10. <span data-ttu-id="8fb5d-247">Wählen Sie auf der Seite **Azure AD-Domäne** unter **Domäne** den Namen der Domäne aus, die Sie zuvor in Phase 1 erstellt und zu Ihrem Office 365-Abonnement hinzugefügt haben, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-247">On the **Azure AD Domain** page, in **Domain**, select the name of the domain you previously created and added to your Office 365 subscription in Phase 1, and then click **Next**.</span></span>
    
11. <span data-ttu-id="8fb5d-248">Klicken Sie auf der Seite **Bereit zur Konfiguration** auf **Konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-248">On the **Ready to configure** page, click **Configure**.</span></span>
    
12. <span data-ttu-id="8fb5d-249">Klicken Sie auf der Seite **Installation ist abgeschlossen** auf **Überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-249">On the **Installation complete** page, click **Verify**.</span></span>
    
    <span data-ttu-id="8fb5d-250">Nun sollten Meldungen angezeigt werden, aus denen hervorgeht, dass sowohl die Intranet- als auch die Internetkonfiguration überprüft wurde.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-250">You should see messages indicating that both the intranet and Internet configuration was verified.</span></span>
    
13. <span data-ttu-id="8fb5d-251">Klicken Sie auf der Seite **Installation ist abgeschlossen** auf **Beenden**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-251">On the **Installation complete** page, click **Exit**.</span></span>
    
<span data-ttu-id="8fb5d-252">Gehen Sie folgendermaßen vor, um zu zeigen, dass die Verbundauthentifizierung funktioniert:</span><span class="sxs-lookup"><span data-stu-id="8fb5d-252">To demonstrate that federated authentication is working:</span></span>
  
1. <span data-ttu-id="8fb5d-253">Öffnen Sie eine neue private Instanz Ihres Browsers auf Ihrem lokalen Computer, und wechseln Sie zu [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="8fb5d-253">Open a new private instance of your browser on your local computer and go to [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
    
2. <span data-ttu-id="8fb5d-254">Geben Sie als Anmeldeinformationen **user1@**\<die in Phase 1 erstellte Domäne> ein. </span><span class="sxs-lookup"><span data-stu-id="8fb5d-254">For the sign-in credentials, type **user1@**\<the domain created in Phase 1>.</span></span> 
    
    <span data-ttu-id="8fb5d-p110">Wenn Ihre Testdomäne beispielsweise **testlab.contoso.com** ist, geben Sie "user1@testlab.contoso.com" ein. Drücken Sie die TAB-TASTE, oder lassen Sie sich von Office 365 automatisch weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-p110">For example, if your test domain is **testlab.contoso.com**, you would type "user1@testlab.contoso.com". Press TAB or allow Office 365 to automatically redirect you.</span></span>
    
    <span data-ttu-id="8fb5d-p111">Jetzt sollten Sie die Seite **Die Verbindung ist nicht privat** sehen. Dies wird angezeigt, weil Sie ein selbstsigniertes Zertifikat auf ADFS1 installiert haben, das der Desktopcomputer nicht überprüfen kann. In einer Produktionsbereitstellung der Verbundauthentifizierung würden Sie ein Zertifikat von einer vertrauenswürdigen Zertifizierungsstelle verwenden, und Ihre Benutzer würden diese Seite nicht sehen.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-p111">You should now see a **Your connection is not private** page. You are seeing this because you installed a self-signed certificate on ADFS1 that your desktop computer cannot validate. In a production deployment of federated authentication, you would use a certificate from a trusted certification authority and your users would not see this page.</span></span>
    
3. <span data-ttu-id="8fb5d-260">Klicken Sie auf der Seite **Die Verbindung ist nicht privat** auf **Erweitert**, und klicken Sie dann auf **Fortfahren mit \<FQDN des Verbunddiensts>**.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-260">On the **Your connection is not private** page, click **Advanced**, and then click **Proceed to \<your federation service FQDN>**.</span></span> 
    
4. <span data-ttu-id="8fb5d-261">Melden Sie sich auf der Seite mit dem Namen Ihrer fiktiven Organisation mit den folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="8fb5d-261">On the page with the name of your fictional organization, sign in with the following:</span></span>
    
  - <span data-ttu-id="8fb5d-262">**CORP\\User1** als Name</span><span class="sxs-lookup"><span data-stu-id="8fb5d-262">**CORP\\User1** for the name</span></span>
    
  - <span data-ttu-id="8fb5d-263">Das Kennwort für das Konto „User1“</span><span class="sxs-lookup"><span data-stu-id="8fb5d-263">The password for the User1 account</span></span>
    
    <span data-ttu-id="8fb5d-264">Die **Microsoft Office-Homepage** sollte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-264">You should see the **Microsoft Office Home** page.</span></span>
    
<span data-ttu-id="8fb5d-p112">In diesem Verfahren wird veranschaulicht, dass Ihr Office 365-Testabonnement im Verbund mit der AD DS-Domäne „corp.contoso.com“ steht, die auf DC1 gehostet wird. Nachfolgend finden Sie die Grundlagen des Authentifizierungsprozesses:</span><span class="sxs-lookup"><span data-stu-id="8fb5d-p112">This procedure demonstrates that your Office 365 trial subscription is federated with the AD DS corp.contoso.com domain hosted on DC1. Here are the basics of the authentication process:</span></span>
  
1. <span data-ttu-id="8fb5d-267">Wenn Sie die Verbunddomäne verwenden, die Sie in Phase 1 mit dem Anmeldekontonamen erstellt haben, wird Ihr Browser von Office 365 an den FQDN des Verbunddiensts und PROXY1 umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-267">When you use the federated domain that you created in Phase 1 within the sign-in account name, Office 365 redirects your browser to your federation service FQDN and PROXY1.</span></span>
    
2. <span data-ttu-id="8fb5d-268">PROXY1 sendet dem lokalen Computer die Anmeldeseite des fiktiven Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-268">PROXY1 sends your local computer the fictional company sign-in page.</span></span>
    
3. <span data-ttu-id="8fb5d-269">Wenn Sie „CORP\\User1“ und das Kennwort an PROXY1 senden, werden diese Informationen an ADFS1 weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-269">When you send CORP\\User1 and the password to PROXY1, it forwards them to ADFS1.</span></span>
    
4. <span data-ttu-id="8fb5d-270">ADFS1 überprüft CORP\\User1 und das Kennwort mit DC1 und sendet dem lokalen Computer ein Sicherheitstoken.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-270">ADFS1 validates CORP\\User1 and the password with DC1 and sends your local computer a security token.</span></span>
    
5. <span data-ttu-id="8fb5d-271">Der lokale Computer sendet das Sicherheitstoken an Office 365.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-271">Your local computer sends the security token to Office 365.</span></span>
    
6. <span data-ttu-id="8fb5d-272">Office 365 überprüft, dass das Sicherheitstoken von ADFS1 erstellt wurde und erlaubt den Zugriff.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-272">Office 365 validates that the security token was created by ADFS1 and allows access.</span></span>
    
<span data-ttu-id="8fb5d-p113">Ihr Office 365-Testabonnement ist jetzt mit Verbundauthentifizierung konfiguriert. Sie können diese Entwicklungs-/Testumgebung für erweiterte Authentifizierungsszenarien verwenden.</span><span class="sxs-lookup"><span data-stu-id="8fb5d-p113">Your Office 365 trial subscription is now configured with federated authentication. You can use this dev/test environment for advanced authentication scenarios.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="8fb5d-275">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="8fb5d-275">Next step</span></span>

<span data-ttu-id="8fb5d-276">Wenn Sie bereit sind, die produktionsbereite, hochverfügbare Verbundauthentifizierung für Microsoft 365 oder Office 365 in Azure bereitzustellen, finden Sie weitere Informationen unter [Bereitstellen der Verbundauthentifizierung mit Hochverfügbarkeit für Office 365 in Azure](https://docs.microsoft.com/office365/enterprise/deploy-high-availability-federated-authentication-for-office-365-in-azure).</span><span class="sxs-lookup"><span data-stu-id="8fb5d-276">When you are ready to deploy production-ready, high availability federated authentication for Microsoft 365 or Office 365 in Azure, see [Deploy high availability federated authentication for Office 365 in Azure](https://docs.microsoft.com/office365/enterprise/deploy-high-availability-federated-authentication-for-office-365-in-azure).</span></span>
  
