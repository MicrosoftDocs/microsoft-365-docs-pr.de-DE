---
title: Verbundidentität für Ihre Microsoft 365-Testumgebung
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
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
ms.openlocfilehash: 0fb8c55f5b7291cdc6bcec636981a9d31015e723
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487684"
---
# <a name="federated-identity-for-your-microsoft-365-test-environment"></a><span data-ttu-id="7d85f-103">Verbundidentität für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="7d85f-103">Federated identity for your Microsoft 365 test environment</span></span>

<span data-ttu-id="7d85f-104">*Diese Testumgebungsanleitung kann sowohl für Microsoft 365 als auch für Office 365 Enterprise verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="7d85f-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="7d85f-p101">Microsoft 365 unterstützt Verbundidentität. Dies bedeutet, dass Microsoft 365, anstatt die Prüfung von Anmeldeinformationen selbst durchzuführen, den Benutzer, der eine Verbindung herstellt, auf einen Verbundauthentifizierungsserver verweist, der für Microsoft 365 vertrauenswürdig ist. Wenn die Anmeldeinformationen des Benutzers korrekt sind, gibt der Verbundauthentifizierungsserver ein Sicherheitstoken aus, das der Client als Nachweis der Authentifizierung an Microsoft 365 sendet. Verbundidentität ermöglicht das Abladen und zentrale Skalieren der Authentifizierung für ein Microsoft 365-Abonnement sowie erweiterte Authentifizierungs- und Sicherheitsszenarien.</span><span class="sxs-lookup"><span data-stu-id="7d85f-p101">Microsoft 365 supports federated identity. This means that instead of performing the validation of credentials itself, Microsoft 365 refers the connecting user to a federated authentication server that Microsoft 365 trusts. If the user's credentials are correct, the federated authentication server issues a security token that the client then sends to Microsoft 365 as proof of authentication. Federated identity allows for the offloading and scaling up of authentication for a Microsoft 365 subscription and advanced authentication and security scenarios.</span></span>
  
<span data-ttu-id="7d85f-109">In diesem Artikel wird beschrieben, wie Sie die Verbundauthentifizierung Microsoft 365 Testumgebung konfigurieren, was zu folgenden Folgen führt:</span><span class="sxs-lookup"><span data-stu-id="7d85f-109">This article describes how to configure federated authentication for your Microsoft 365 test environment, resulting in the following:</span></span>

![Die Verbundauthentifizierung für die Microsoft 365-Testumgebung](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
<span data-ttu-id="7d85f-111">Diese Konfiguration besteht aus:</span><span class="sxs-lookup"><span data-stu-id="7d85f-111">This configuration consists of:</span></span>
  
- <span data-ttu-id="7d85f-112">Ein Microsoft 365 E5 oder Produktionsabonnement.</span><span class="sxs-lookup"><span data-stu-id="7d85f-112">A Microsoft 365 E5 trial or production subscription.</span></span>
    
- <span data-ttu-id="7d85f-113">Ein vereinfachtes Unternehmensintranet, das mit dem Internet verbunden ist und aus fünf virtuellen Computern in einem Subnetz eines virtuellen Azure-Netzwerks (DC1, APP1, CLIENT1, ADFS1 und PROXY1) besteht.</span><span class="sxs-lookup"><span data-stu-id="7d85f-113">A simplified organization intranet connected to the internet, consisting of five virtual machines on a subnet of an Azure virtual network (DC1, APP1, CLIENT1, ADFS1, and PROXY1).</span></span> <span data-ttu-id="7d85f-114">Azure AD Verbinden wird auf APP1 ausgeführt, um die Liste der Konten in der Domäne Active Directory Domain Services mit Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7d85f-114">Azure AD Connect runs on APP1 to synchronize the list of accounts in the Active Directory Domain Services domain to Microsoft 365.</span></span> <span data-ttu-id="7d85f-115">PROXY1 erhält die eingehenden Authentifizierungsanfragen.</span><span class="sxs-lookup"><span data-stu-id="7d85f-115">PROXY1 receives the incoming authentication requests.</span></span> <span data-ttu-id="7d85f-116">ADFS1 überprüft Anmeldeinformationen mit DC1 und gibt Sicherheitstoken aus.</span><span class="sxs-lookup"><span data-stu-id="7d85f-116">ADFS1 validates credentials with DC1 and issues security tokens.</span></span>
    
<span data-ttu-id="7d85f-117">Das Einrichten dieser Testumgebung umfasst fünf Phasen:</span><span class="sxs-lookup"><span data-stu-id="7d85f-117">Setting up this test environment involves five phases:</span></span>
- [<span data-ttu-id="7d85f-118">Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="7d85f-118">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="7d85f-119">Phase 2: Erstellen des AD FS-Servers</span><span class="sxs-lookup"><span data-stu-id="7d85f-119">Phase 2: Create the AD FS server</span></span>](#phase-2-create-the-ad-fs-server)
- [<span data-ttu-id="7d85f-120">Phase 3: Erstellen des Webproxyservers</span><span class="sxs-lookup"><span data-stu-id="7d85f-120">Phase 3: Create the web proxy server</span></span>](#phase-3-create-the-web-proxy-server)
- [<span data-ttu-id="7d85f-121">Phase 4: Erstellen eines selbstsignierten Zertifikats und Konfigurieren von ADFS1 und PROXY1</span><span class="sxs-lookup"><span data-stu-id="7d85f-121">Phase 4: Create a self-signed certificate and configure ADFS1 and PROXY1</span></span>](#phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1)
- [<span data-ttu-id="7d85f-122">Phase 5: Konfigurieren von Microsoft 365 für Verbundidentität</span><span class="sxs-lookup"><span data-stu-id="7d85f-122">Phase 5: Configure Microsoft 365 for federated identity</span></span>](#phase-5-configure-microsoft-365-for-federated-identity)
    
> [!NOTE]
> <span data-ttu-id="7d85f-123">Sie können diese Testumgebung nicht mit einem Azure-Testabonnement konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7d85f-123">You can't configure this test environment with an Azure Trial subscription.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="7d85f-124">Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="7d85f-124">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="7d85f-125">Befolgen Sie die Anweisungen unter [Kennworthashsynchronisierung für Microsoft 365.](password-hash-sync-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="7d85f-125">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="7d85f-126">Die resultierende Konfiguration sieht wie die folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="7d85f-126">Your resulting configuration looks like this:</span></span>
  
![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase1.png)
  
<span data-ttu-id="7d85f-128">Diese Konfiguration besteht aus: </span><span class="sxs-lookup"><span data-stu-id="7d85f-128">This configuration consists of:</span></span>
  
- <span data-ttu-id="7d85f-129">Eine Microsoft 365 E5 oder kostenpflichtige Abonnements.</span><span class="sxs-lookup"><span data-stu-id="7d85f-129">A Microsoft 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="7d85f-130">Ein vereinfachtes Unternehmensintranet, das mit dem Internet verbunden ist und aus den virtuellen Computern DC1, APP1 und CLIENT1 in einem Subnetz eines virtuellen Azure-Netzwerks besteht.</span><span class="sxs-lookup"><span data-stu-id="7d85f-130">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="7d85f-131">Azure AD Verbinden wird auf APP1 ausgeführt, um die Active Directory Domain Services (AD DS)-Domäne testlab regelmäßig mit dem Azure AD-Mandanten Ihrer Microsoft 365 zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="7d85f-131">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscriptions periodically.</span></span>

## <a name="phase-2-create-the-ad-fs-server"></a><span data-ttu-id="7d85f-132">Phase 2: Erstellen des AD FS-Servers</span><span class="sxs-lookup"><span data-stu-id="7d85f-132">Phase 2: Create the AD FS server</span></span>

<span data-ttu-id="7d85f-133">Ein AD FS-Server bietet Verbundauthentifizierung zwischen Microsoft 365 und den Konten in der Domäne „corp.contoso.com“, die auf DC1 gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="7d85f-133">An AD FS server provides federated authentication between Microsoft 365 and the accounts in the corp.contoso.com domain hosted on DC1.</span></span>
  
<span data-ttu-id="7d85f-134">Um einen virtuellen Azure-Computer für ADFS1 zu erstellen, geben Sie den Namen Ihres Abonnements und der Ressourcengruppe sowie den Azure-Speicherort für Ihre Basiskonfiguration ein, und führen Sie diese Befehle in der Azure PowerShell-Befehlszeile auf Ihrem lokalen Computer aus.</span><span class="sxs-lookup"><span data-stu-id="7d85f-134">To create an Azure virtual machine for ADFS1, fill in the name of your subscription and the resource group and Azure location for your Base Configuration, and then run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
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

<span data-ttu-id="7d85f-135">Im nächsten Schritt stellen Sie über das [Azure-Portal](https://portal.azure.com) eine Verbindung mit dem virtuellen Computer ADFS1 mit dem Namen und Kennwort des lokalen Administratorkontos von ADFS1 her und öffnen dann eine Windows PowerShell-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="7d85f-135">Next, use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the ADFS1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="7d85f-136">Führen Sie zum Überprüfen der Namensauflösung und der Netzwerkkommunikation zwischen ADFS1 und DC1 den Befehl **ping dc1.corp.contoso.com** aus, und vergewissern Sie sich, dass vier Antworten vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="7d85f-136">To check name resolution and network communication between ADFS1 and DC1, run the **ping dc1.corp.contoso.com** command and check that there are four replies.</span></span>
  
<span data-ttu-id="7d85f-137">Verknüpfen Sie als Nächstes unter Verwendung der folgenden Befehle an der Windows PowerShell-Eingabeaufforderung auf ADFS1 den virtuellen Computer ADFS1 mit der Domäne CORP.</span><span class="sxs-lookup"><span data-stu-id="7d85f-137">Next, join the ADFS1 virtual machine to the CORP domain with these commands at the Windows PowerShell prompt on ADFS1.</span></span>
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

<span data-ttu-id="7d85f-138">Die resultierende Konfiguration sieht wie die folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="7d85f-138">Your resulting configuration looks like this:</span></span>
  
![Der AD FS-Server, der der DirSync für die Microsoft 365-Testumgebung hinzugefügt wurde](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase2.png)
  
## <a name="phase-3-create-the-web-proxy-server"></a><span data-ttu-id="7d85f-140">Phase 3: Erstellen des Webproxyservers</span><span class="sxs-lookup"><span data-stu-id="7d85f-140">Phase 3: Create the web proxy server</span></span>

<span data-ttu-id="7d85f-141">PROXY1 stellt die Proxyfunktion für Authentifizierungsnachrichten zwischen Benutzern, die versuchen, sich zu authentifizieren, und ADFS1 bereit.</span><span class="sxs-lookup"><span data-stu-id="7d85f-141">PROXY1 provides proxying of authentication messages between users trying to authenticate and ADFS1.</span></span>
  
<span data-ttu-id="7d85f-142">Um einen virtuellen Azure-Computer für PROXY1 zu erstellen, geben Sie den Namen Ihrer Ressourcengruppe und den Azure-Speicherort ein und führen diese Befehle in der Azure PowerShell-Befehlszeile auf Ihrem lokalen Computer aus.</span><span class="sxs-lookup"><span data-stu-id="7d85f-142">To create an Azure virtual machine for PROXY1, fill in the name of your resource group and Azure location, and then run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
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
> <span data-ttu-id="7d85f-143">PROXY1 wird einer statischen öffentlichen IP-Adresse zugewiesen, da Sie einen öffentlichen DNS-Eintrag erstellen, der darauf verweist, und der nicht geändert werden muss, wenn Sie den virtuellen PROXY1-Computer neu starten.</span><span class="sxs-lookup"><span data-stu-id="7d85f-143">PROXY1 is assigned a static public IP address because you will create a public DNS record that points to it and it must not change when you restart the PROXY1 virtual machine.</span></span>
  
<span data-ttu-id="7d85f-144">Fügen Sie als Nächstes der Netzwerksicherheitsgruppe für das CorpNet-Subnetz eine Regel hinzu, um unerwünschten eingehenden Datenverkehr aus dem Internet an die private IP-Adresse von PROXY1 und den TCP-Port 443 zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="7d85f-144">Next, add a rule to the network security group for the CorpNet subnet to allow unsolicited inbound traffic from the internet to PROXY1's private IP address and TCP port 443.</span></span> <span data-ttu-id="7d85f-145">Führen Sie diese Befehle an der Azure PowerShell-Eingabeaufforderung auf dem lokalen Computer aus.</span><span class="sxs-lookup"><span data-stu-id="7d85f-145">Run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
Get-AzNetworkSecurityGroup -Name CorpNet -ResourceGroupName $rgName | Add-AzNetworkSecurityRuleConfig -Name "HTTPS-to-PROXY1" -Description "Allow TCP 443 to PROXY1" -Access "Allow" -Protocol "Tcp" -Direction "Inbound" -Priority 101 -SourceAddressPrefix "Internet" -SourcePortRange "*" -DestinationAddressPrefix "10.0.0.101" -DestinationPortRange "443" | Set-AzNetworkSecurityGroup
```

<span data-ttu-id="7d85f-146">Im nächsten Schritt stellen Sie über das [Azure-Portal](https://portal.azure.com) eine Verbindung mit dem virtuellen Computer PROXY1 mit dem Kontonamen und Kennwort des lokalen Administratorkontos von PROXY1 her und öffnen dann eine Windows PowerShell-Eingabeaufforderung auf PROXY1.</span><span class="sxs-lookup"><span data-stu-id="7d85f-146">Next, use the [Azure portal](https://portal.azure.com) to connect to the PROXY1 virtual machine using the PROXY1 local administrator account name and password, and then open a Windows PowerShell command prompt on PROXY1.</span></span>
  
<span data-ttu-id="7d85f-147">Führen Sie zum Überprüfen der Namensauflösung und der Netzwerkkommunikation zwischen PROXY1 und DC1 den Befehl **ping dc1.corp.contoso.com** aus, und vergewissern Sie sich, dass vier Antworten vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="7d85f-147">To check name resolution and network communication between PROXY1 and DC1, run the **ping dc1.corp.contoso.com** command and check that there are four replies.</span></span>
  
<span data-ttu-id="7d85f-148">Verknüpfen Sie als Nächstes unter Verwendung der folgenden Befehle an der Windows PowerShell-Eingabeaufforderung auf PROXY1 den virtuellen Computer PROXY1 mit der Domäne CORP.</span><span class="sxs-lookup"><span data-stu-id="7d85f-148">Next, join the PROXY1 virtual machine to the CORP domain with these commands at the Windows PowerShell prompt on PROXY1.</span></span>
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

<span data-ttu-id="7d85f-149">Zeigen Sie die öffentliche IP-Adresse von PROXY1 mit Azure PowerShell befehlen auf Dem lokalen Computer an.</span><span class="sxs-lookup"><span data-stu-id="7d85f-149">Display the public IP address of PROXY1 with these Azure PowerShell commands on your local computer.</span></span>
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "PROXY1-PIP" -ResourceGroup $rgName).IPAddress
```

<span data-ttu-id="7d85f-p106">Im nächsten Schritt arbeiten Sie mit Ihrem öffentlichen DNS-Anbieter und erstellen einen neuen öffentlichen DNS A-Eintrag für **fs.testlab.**\<*your DNS domain name*>, der in die IP-Adresse aufgelöst wird, die vom Befehl **Write-Host** angezeigt wird. Auf **fs.testlab.**\<*your DNS domain name*> wird nachfolgend als *FQDN des Verbunddiensts verwiesen*.</span><span class="sxs-lookup"><span data-stu-id="7d85f-p106">Next, work with your public DNS provider and create a new public DNS A record for **fs.testlab.**\<*your DNS domain name*> that resolves to the IP address displayed by the **Write-Host** command. The **fs.testlab.**\<*your DNS domain name*> is hereafter referred to as the  *federation service FQDN*.</span></span>
  
<span data-ttu-id="7d85f-154">Im nächsten Schritt stellen Sie über das [Azure-Portal](https://portal.azure.com) eine Verbindung mit dem virtuellen Computer DC1 unter Verwendung der Anmeldeinformationen „CORP\\User1“ her und führen dann die folgenden Befehle an einer Windows PowerShell-Eingabeaufforderung auf Administratorebene aus:</span><span class="sxs-lookup"><span data-stu-id="7d85f-154">Next, use the [Azure portal](https://portal.azure.com) to connect to the DC1 virtual machine using the CORP\\User1 credentials, and then run the following commands at an administrator-level Windows PowerShell command prompt:</span></span>
  
```powershell
Add-DnsServerPrimaryZone -Name corp.contoso.com -ZoneFile corp.contoso.com.dns
Add-DnsServerResourceRecordA -Name "fs" -ZoneName corp.contoso.com -AllowUpdateAny -IPv4Address "10.0.0.100" -TimeToLive 01:00:00
```
<span data-ttu-id="7d85f-155">Diese Befehle erstellen einen internen DNS A-Eintrag, damit virtuelle Computer im virtuellen Azure-Netzwerk den FQDN des internen Verbunddiensts in die private IP-Adresse von ADFS1 auflösen können.</span><span class="sxs-lookup"><span data-stu-id="7d85f-155">These commands create an internal DNS A record so that virtual machines on the Azure virtual network can resolve the internal federation service FQDN to ADFS1's private IP address.</span></span>
  
<span data-ttu-id="7d85f-156">Die resultierende Konfiguration sieht wie die folgenden aus:</span><span class="sxs-lookup"><span data-stu-id="7d85f-156">Your resulting configuration looks like this:</span></span>
  
![Der Webanwendungs-Proxyserver, der der DirSync für die Microsoft 365-Testumgebung hinzugefügt wurde](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
## <a name="phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1"></a><span data-ttu-id="7d85f-158">Phase 4: Erstellen eines selbstsignierten Zertifikats und Konfigurieren von ADFS1 und PROXY1</span><span class="sxs-lookup"><span data-stu-id="7d85f-158">Phase 4: Create a self-signed certificate and configure ADFS1 and PROXY1</span></span>

<span data-ttu-id="7d85f-159">In dieser Phase erstellen Sie ein selbstsigniertes digitales Zertifikat für den FQDN des Verbunddiensts und konfigurieren ADFS1 und PROXY1 als AD FS-Farm.</span><span class="sxs-lookup"><span data-stu-id="7d85f-159">In this phase, you create a self-signed digital certificate for your federation service FQDN and configure ADFS1 and PROXY1 as an AD FS farm.</span></span>
  
<span data-ttu-id="7d85f-160">Im nächsten Schritt stellen Sie über das [Azure-Portal](https://portal.azure.com) eine Verbindung mit dem virtuellen Computer DC1 unter Verwendung der Anmeldeinformationen „CORP\\User1“ her und öffnen dann eine Windows PowerShell-Eingabeaufforderung auf Administratorebene.</span><span class="sxs-lookup"><span data-stu-id="7d85f-160">First, use the [Azure portal](https://portal.azure.com) to connect to the DC1 virtual machine using the CORP\\User1 credentials, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="7d85f-161">Erstellen Sie als Nächstes ein AD FS-Dienstkonto mit diesem Befehl an der eingabeaufforderung Windows PowerShell DC1:</span><span class="sxs-lookup"><span data-stu-id="7d85f-161">Next, create an AD FS service account with this command at the Windows PowerShell command prompt on DC1:</span></span>
  
```powershell
New-ADUser -SamAccountName ADFS-Service -AccountPassword (read-host "Set user password" -assecurestring) -name "ADFS-Service" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```
<span data-ttu-id="7d85f-162">Beachten Sie, dass Sie von dem Befehl aufgefordert werden, das Kontokennwort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7d85f-162">Note that this command prompts you to supply the account password.</span></span> <span data-ttu-id="7d85f-163">Verwenden Sie ein sicheres Kennwort, und notieren Sie es an einem sicheren Ort.</span><span class="sxs-lookup"><span data-stu-id="7d85f-163">Choose a strong password and record it in a secured location.</span></span> <span data-ttu-id="7d85f-164">Sie benötigen sie für diese Phase und für Phase 5.</span><span class="sxs-lookup"><span data-stu-id="7d85f-164">You will need it for this phase and for Phase 5.</span></span>
  
<span data-ttu-id="7d85f-p108">Verwenden Sie das [Azure-Portal](https://portal.azure.com), um eine Verbindung zu dem virtuellen Computer ADFS1 unter Verwendung der Anmeldeinformationen „CORP\\User1“ herzustellen. Öffnen Sie eine Windows PowerShell-Eingabeaufforderung auf Administratorebene auf ADFS1, geben Sie den FQDN des Verbunddiensts ein, und führen Sie dann die folgenden Befehle aus, um ein selbstsigniertes Zertifikat zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="7d85f-p108">Use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the CORP\\User1 credentials. Open an administrator-level Windows PowerShell command prompt on ADFS1, fill in your federation service FQDN, and then run these commands to create a self-signed certificate:</span></span>
  
```powershell
$fedServiceFQDN="<federation service FQDN>"
New-SelfSignedCertificate -DnsName $fedServiceFQDN -CertStoreLocation "cert:\LocalMachine\My"
New-Item -path c:\Certs -type directory
New-SmbShare -name Certs -path c:\Certs -changeaccess CORP\User1
```

<span data-ttu-id="7d85f-167">Gehen Sie dann folgendermaßen vor, um das neue selbstsignierte Zertifikat als Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="7d85f-167">Next, use these steps to save the new self-signed certificate as a file.</span></span>
  
1. <span data-ttu-id="7d85f-168">Wählen **Sie Start** aus, geben **mmc.exe** ein, und drücken Sie dann die **EINGABETASTE.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-168">Select **Start**, enter **mmc.exe**, and then press **Enter**.</span></span>
    
2. <span data-ttu-id="7d85f-169">Wählen **Sie Datei**  >  **hinzufügen/entfernen Andocken-In aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-169">Select **File** > **Add/Remove Snap-in**.</span></span>
    
3. <span data-ttu-id="7d85f-170">Doppelklicken Sie **unter Andocken-Ins** hinzufügen oder entfernen **in** der Liste der verfügbaren Snap-Ins auf Zertifikate, wählen Sie **Computerkonto** aus, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-170">In **Add or Remove Snap-ins**, double-click **Certificates** in the list of available snap-ins, select **Computer account**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="7d85f-171">Wählen **Sie unter Computer** auswählen die Option **Fertig** stellen aus, und wählen Sie dann **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-171">In **Select Computer**, select **Finish**, and then select **OK**.</span></span>
    
5. <span data-ttu-id="7d85f-172">Öffnen Sie im Strukturbereich **Zertifikate (Lokaler Computer) > Persönlich > Zertifikate**.</span><span class="sxs-lookup"><span data-stu-id="7d85f-172">In the tree pane, open **Certificates (Local Computer) > Personal > Certificates**.</span></span>
    
6. <span data-ttu-id="7d85f-173">Wählen Sie das Zertifikat mit dem FQDN des Verbunddiensts aus, und halten Sie es fest (oder klicken Sie mit der rechten Maustaste), wählen Sie **Alle Aufgaben** aus, und wählen Sie **dann Exportieren aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-173">Select and hold (or right-click) the certificate with your federation service FQDN, select **All tasks**, and then select **Export**.</span></span>
    
7. <span data-ttu-id="7d85f-174">Wählen Sie **auf der Seite** Willkommen die Option Weiter **aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-174">On the **Welcome** page, select **Next**.</span></span>
    
8. <span data-ttu-id="7d85f-175">Wählen Sie **auf der** Seite Privater Schlüssel exportieren die Option **Ja** aus, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-175">On the **Export Private Key** page, select **Yes**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="7d85f-176">Wählen Sie **auf der Seite** Dateiformat exportieren die Option Alle **erweiterten** Eigenschaften exportieren aus, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-176">On the **Export File Format** page, select **Export all extended properties**, and then select **Next**.</span></span>
    
10. <span data-ttu-id="7d85f-177">Wählen Sie **auf der Seite** Sicherheit die Option **Kennwort** aus, und geben Sie ein Kennwort in **Kennwort und** Kennwort **bestätigen ein.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-177">On the **Security** page, select **Password** and enter a password in **Password** and **Confirm password.**</span></span>
    
11. <span data-ttu-id="7d85f-178">Wählen Sie **auf der Seite Zu exportierende** Datei die Option Durchsuchen **aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-178">On the **File to Export** page, select **Browse**.</span></span>
    
12. <span data-ttu-id="7d85f-179">Navigieren Sie zum **Ordner C: \\ Certs,** geben Sie **SSL** unter **Dateiname** ein, und wählen Sie dann **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-179">Browse to the **C:\\Certs** folder, enter **SSL** in **File name**, and then select **Save.**</span></span>
    
13. <span data-ttu-id="7d85f-180">Wählen Sie **auf der Seite Zu exportierende** Datei die Option Weiter **aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-180">On the **File to Export** page, select **Next**.</span></span>
    
14. <span data-ttu-id="7d85f-181">Wählen Sie **auf der Seite Zertifikatexport-Assistent abschließen** die Option Fertig stellen **aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-181">On the **Completing the Certificate Export Wizard** page, select **Finish**.</span></span> <span data-ttu-id="7d85f-182">Wenn Sie dazu aufgefordert werden, wählen Sie **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-182">When prompted, select **OK**.</span></span>
    
<span data-ttu-id="7d85f-183">Im nächsten Schritt erstellen Sie den AD FS-Dienst mit dem folgenden Befehl an der Windows PowerShell-Eingabeaufforderung auf ADFS1:</span><span class="sxs-lookup"><span data-stu-id="7d85f-183">Next, install the AD FS service with this command at the Windows PowerShell command prompt on ADFS1:</span></span>
  
```powershell
Install-WindowsFeature ADFS-Federation -IncludeManagementTools
```

<span data-ttu-id="7d85f-184">Warten Sie, bis die Installation abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="7d85f-184">Wait for the installation to complete.</span></span>
  
<span data-ttu-id="7d85f-185">Konfigurieren Sie als Nächstes den AD FS-Dienst mit den folgenden Schritten:</span><span class="sxs-lookup"><span data-stu-id="7d85f-185">Next, configure the AD FS service with these steps:</span></span>
  
1. <span data-ttu-id="7d85f-186">Wählen **Sie Start** aus, und wählen Sie dann das Symbol **Server-Manager** aus.</span><span class="sxs-lookup"><span data-stu-id="7d85f-186">Select **Start**, and then select the **Server Manager** icon.</span></span>
    
2. <span data-ttu-id="7d85f-187">Wählen Sie im Strukturbereich von Server Manager AD **FS aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-187">In the tree pane of Server Manager, select **AD FS**.</span></span>
    
3. <span data-ttu-id="7d85f-188">Wählen Sie oben in der Toolleiste das orangefarbene Warnsymbol aus, und wählen Sie dann Konfigurieren des Verbunddiensts **auf diesem Server aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-188">In the tool bar at the top, select the orange caution symbol, and then select **Configure the federation service on this server**.</span></span>
    
4. <span data-ttu-id="7d85f-189">Wählen Sie **auf der Willkommensseite** des Active Directory Federation Services Configuration Wizard die Option **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-189">On the **Welcome** page of the Active Directory Federation Services Configuration Wizard, select **Next**.</span></span>
    
5. <span data-ttu-id="7d85f-190">Wählen Sie **auf Verbinden zu AD DS** die Option Weiter **aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-190">On the **Connect to AD DS** page, select **Next**.</span></span>
    
6. <span data-ttu-id="7d85f-191">Auf der Seite **Diensteigenschaften angeben**:</span><span class="sxs-lookup"><span data-stu-id="7d85f-191">On the **Specify Service Properties** page:</span></span>
    
  - <span data-ttu-id="7d85f-192">Wählen **Sie für SSL-Zertifikat** den Pfeil nach unten aus, und wählen Sie dann das Zertifikat mit dem Namen Des Verbunddienst-FQDN aus.</span><span class="sxs-lookup"><span data-stu-id="7d85f-192">For **SSL Certificate**, select the down arrow, and then select the certificate with the name of your federation service FQDN.</span></span>
    
  - <span data-ttu-id="7d85f-193">Geben **Sie unter Anzeigename** des Verbunddiensts den Namen Ihrer fiktiven Organisation ein.</span><span class="sxs-lookup"><span data-stu-id="7d85f-193">In **Federation Service Display Name**, enter the name of your fictional organization.</span></span>
    
  - <span data-ttu-id="7d85f-194">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="7d85f-194">Select **Next**.</span></span>
    
7. <span data-ttu-id="7d85f-195">Wählen Sie **auf der Seite Dienstkonto angeben** die Option **Für** **Kontonamen auswählen aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-195">On the **Specify Service Account** page, select **Select** for **Account name**.</span></span>
    
8. <span data-ttu-id="7d85f-196">Geben **Sie unter Benutzer- oder Dienstkonto auswählen** **ADFS-Service ein,** wählen Sie Namen **überprüfen** aus, und wählen Sie dann **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-196">In **Select User or Service Account**, enter **ADFS-Service**, select **Check Names**, and then select **OK**.</span></span>
    
9. <span data-ttu-id="7d85f-197">Geben **Sie unter** Kontokennwort das Kennwort für das ADFS-Service ein, und wählen Sie dann Weiter **aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-197">In **Account Password**, enter the password for the ADFS-Service account, and then select **Next**.</span></span>
    
10. <span data-ttu-id="7d85f-198">Wählen Sie auf der Seite **Konfigurationsdatenbank angeben** die Option **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-198">On the **Specify Configuration Database** page, select **Next**.</span></span>
    
11. <span data-ttu-id="7d85f-199">Wählen Sie **auf der** Seite Überprüfungsoptionen die Option **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-199">On the **Review Options** page, select **Next**.</span></span>
    
12. <span data-ttu-id="7d85f-200">Wählen Sie **auf der Seite Erforderliche Prüfungen** die Option Konfigurieren **aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-200">On the **Pre-requisite Checks** page, select **Configure**.</span></span>

13. <span data-ttu-id="7d85f-201">Wählen Sie **auf der** Seite Ergebnisse die Option **Schließen aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-201">On the **Results** page, select **Close**.</span></span>
    
14. <span data-ttu-id="7d85f-202">Wählen **Sie Start** aus, wählen Sie das Netzsymbol aus, wählen Sie **Neustart** aus, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-202">Select **Start**, select the power icon, select **Restart**, and then select **Continue**.</span></span>
    
<span data-ttu-id="7d85f-203">Melden Sie sich über das [Azure-Portal](https://portal.azure.com) mit dem CORP\\User1-Konto bei PROXY1 an.</span><span class="sxs-lookup"><span data-stu-id="7d85f-203">From the [Azure portal](https://portal.azure.com), connect to PROXY1 with the CORP\\User1 account credentials.</span></span>
  
<span data-ttu-id="7d85f-204">Gehen Sie dann folgendermaßen vor, um das selbstsignierte Zertifikat auf **PROXY1 und APP1** zu installieren.</span><span class="sxs-lookup"><span data-stu-id="7d85f-204">Next, use these steps to install the self-signed certificate on **both PROXY1 and APP1**.</span></span>
  
1. <span data-ttu-id="7d85f-205">Wählen **Sie Start** aus, geben **mmc.exe** ein, und drücken Sie dann die **EINGABETASTE.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-205">Select **Start**, enter **mmc.exe**, and then press **Enter**.</span></span>
    
2. <span data-ttu-id="7d85f-206">Wählen **Sie Datei > Hinzufügen/Entfernen Andocken-In aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-206">Select **File > Add/Remove Snap-in**.</span></span>
    
3. <span data-ttu-id="7d85f-207">Doppelklicken Sie **unter Andocken-Ins** hinzufügen oder entfernen **in** der Liste der verfügbaren Snap-Ins auf Zertifikate, wählen Sie **Computerkonto** aus, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-207">In **Add or Remove Snap-ins**, double-click **Certificates** in the list of available snap-ins, select **Computer account**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="7d85f-208">Wählen **Sie unter Computer** auswählen die Option **Fertig** stellen aus, und wählen Sie dann **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-208">In **Select Computer**, select **Finish**, and then select **OK**.</span></span>
    
5. <span data-ttu-id="7d85f-209">Öffnen Sie im Strukturbereich **Zertifikate (Lokaler Computer)**  >  **Persönliche**  >  **Zertifikate**.</span><span class="sxs-lookup"><span data-stu-id="7d85f-209">In the tree pane, open **Certificates (Local Computer)** > **Personal** > **Certificates**.</span></span>
    
6. <span data-ttu-id="7d85f-210">Wählen Und halten (oder klicken Sie mit der rechten Maustaste) **Personal**, wählen **Sie Alle Aufgaben** aus, und wählen Sie dann Importieren **aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-210">Select and hold (or right-click) **Personal**, select **All tasks**, and then select **Import**.</span></span>
    
7. <span data-ttu-id="7d85f-211">Wählen Sie **auf der Seite** Willkommen die Option Weiter **aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-211">On the **Welcome** page, select **Next**.</span></span>
    
8. <span data-ttu-id="7d85f-212">Geben Sie **auf der Seite Zu importierende** Datei **\\ \\ adfs1 \\ certs \\ ssl.pfx** ein, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-212">On the **File to Import** page, enter **\\\\adfs1\\certs\\ssl.pfx**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="7d85f-213">Geben Sie **auf der Seite** Schutz privater Schlüssel das Zertifikatkennwort in **Kennwort** ein, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-213">On the **Private key protection** page, enter the certificate password in **Password**, and then select **Next.**</span></span>
    
10. <span data-ttu-id="7d85f-214">Wählen Sie **auf der Seite Zertifikatspeicher** die Option **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-214">On the **Certificate store** page, select **Next.**</span></span>
    
11. <span data-ttu-id="7d85f-215">Wählen Sie **auf der Seite** Fertigstellung die Option Fertig stellen **aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-215">On the **Completing** page, select **Finish**.</span></span>
    
12. <span data-ttu-id="7d85f-216">Wählen Sie **auf** Store Seite Zertifikat die Option **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-216">On the **Certificate Store** page, select **Next**.</span></span>
    
13. <span data-ttu-id="7d85f-217">Wenn Sie dazu aufgefordert werden, wählen Sie **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-217">When prompted, select **OK**.</span></span>
    
14. <span data-ttu-id="7d85f-218">Wählen Sie im Strukturbereich Zertifikate **aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-218">In the tree pane, select **Certificates**.</span></span>
    
15. <span data-ttu-id="7d85f-219">Wählen Sie das Zertifikat aus, und halten Sie es fest (oder klicken Sie mit der rechten Maustaste), und wählen Sie dann **Kopieren aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-219">Select and hold (or right-click) the certificate, and then select **Copy**.</span></span>
    
16. <span data-ttu-id="7d85f-220">Öffnen Sie im Strukturbereich Zertifikate für **vertrauenswürdige Stammzertifizierungsstellen**  >  .</span><span class="sxs-lookup"><span data-stu-id="7d85f-220">In the tree pane, open **Trusted Root Certification Authorities** > **Certificates**.</span></span>
    
17. <span data-ttu-id="7d85f-221">Bewegen Sie den Mauszeiger unter die Liste der installierten Zertifikate, wählen Sie und halten Sie (oder klicken Sie mit der rechten Maustaste), und wählen Sie dann **Einfügen aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-221">Move your mouse pointer below the list of installed certificates, select and hold (or right-click), and then select **Paste**.</span></span>
    
<span data-ttu-id="7d85f-222">Öffnen Sie eine PowerShell-Eingabeaufforderung auf Administratorebene, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="7d85f-222">Open an administrator-level PowerShell command prompt and run the following command:</span></span>
  
```powershell
Install-WindowsFeature Web-Application-Proxy -IncludeManagementTools
```

<span data-ttu-id="7d85f-223">Warten Sie, bis die Installation abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="7d85f-223">Wait for the installation to complete.</span></span>
  
<span data-ttu-id="7d85f-224">Verwenden Sie die folgenden Schritte, um den Webanwendungs-Proxydienst so zu konfigurieren, dass ADFS1 als Verbundserver verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="7d85f-224">Use these steps to configure the web application proxy service to use ADFS1 as its federation server:</span></span>
  
1. <span data-ttu-id="7d85f-225">Wählen **Sie Start** aus, und wählen Sie dann **Server-Manager aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-225">Select **Start**, and then select **Server Manager**.</span></span>
    
2. <span data-ttu-id="7d85f-226">Wählen Sie im Strukturbereich **Remotezugriff aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-226">In the tree pane, select **Remote Access**.</span></span>
    
3. <span data-ttu-id="7d85f-227">Wählen Sie oben in der Toolleiste das orangefarbene Warnsymbol aus, und wählen Sie dann **Den Webanwendungsproxy-Assistenten öffnen aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-227">In the tool bar at the top, select the orange caution symbol, and then select **Open the Web Application Proxy Wizard**.</span></span>
    
4. <span data-ttu-id="7d85f-228">Wählen Sie **auf der** Seite Willkommen des Assistenten für die Webanwendungsproxykonfiguration die Option **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-228">On the **Welcome** page of the Web Application Proxy Configuration Wizard, select **Next**.</span></span>
    
5. <span data-ttu-id="7d85f-229">Auf der Seite **Verbundserver**:</span><span class="sxs-lookup"><span data-stu-id="7d85f-229">On the **Federation Server** page:</span></span>
    
  - <span data-ttu-id="7d85f-230">Geben Sie **im Feld Verbunddienstname** den FQDN des Verbunddiensts ein.</span><span class="sxs-lookup"><span data-stu-id="7d85f-230">In the **Federation service name** box, enter your federation service FQDN.</span></span>
    
  - <span data-ttu-id="7d85f-231">Geben Sie **im Feld Benutzername** corp **\\ User1 ein.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-231">In the **User name** box, enter **CORP\\User1**.</span></span>
    
  - <span data-ttu-id="7d85f-232">Geben Sie **im Feld** Kennwort das Kennwort für das Benutzerkonto "User1" ein.</span><span class="sxs-lookup"><span data-stu-id="7d85f-232">In the **Password** box, enter the password for the User1 account.</span></span>
    
  - <span data-ttu-id="7d85f-233">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="7d85f-233">Select **Next**.</span></span>
    
6. <span data-ttu-id="7d85f-234">Wählen Sie auf der **Seite AD FS-Proxyzertifikat** den Pfeil nach unten aus, wählen Sie das Zertifikat mit dem FQDN des Verbunddiensts aus, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-234">On the **AD FS Proxy Certificate** page, select the down arrow, select the certificate with your federation service FQDN, and then select **Next**.</span></span>
    
7. <span data-ttu-id="7d85f-235">Wählen Sie **auf der Seite** Bestätigung die Option Konfigurieren **aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-235">On the **Confirmation** page, select **Configure**.</span></span>
    
8. <span data-ttu-id="7d85f-236">Wählen Sie **auf der** Seite Ergebnisse die Option **Schließen aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-236">On the **Results** page, select **Close**.</span></span>
    
## <a name="phase-5-configure-microsoft-365-for-federated-identity"></a><span data-ttu-id="7d85f-237">Phase 5: Konfigurieren von Microsoft 365 für Verbundidentität</span><span class="sxs-lookup"><span data-stu-id="7d85f-237">Phase 5: Configure Microsoft 365 for federated identity</span></span>

<span data-ttu-id="7d85f-238">Verwenden Sie das [Azure-Portal](https://portal.azure.com), um eine Verbindung zu dem virtuellen Computer APP1 unter Verwendung der Kontoanmeldeinformationen „CORP\\User1“ herzustellen.</span><span class="sxs-lookup"><span data-stu-id="7d85f-238">Use the [Azure portal](https://portal.azure.com) to connect to the APP1 virtual machine with the CORP\\User1 account credentials.</span></span>
  
<span data-ttu-id="7d85f-239">Verwenden Sie diese Schritte, um Azure AD Connect und Ihr Microsoft 365-Abonnement für die Verbundauthentifizierung zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="7d85f-239">Use these steps to configure Azure AD Connect and your Microsoft 365 subscription for federated authentication:</span></span>
  
1. <span data-ttu-id="7d85f-240">Doppelklicken Sie auf dem Desktop auf **Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="7d85f-240">From the desktop, double-click **Azure AD Connect**.</span></span>
    
2. <span data-ttu-id="7d85f-241">Wählen Sie auf der Seite Willkommen bei **Azure AD Verbinden** Konfigurieren **aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-241">On the **Welcome to Azure AD Connect** page, select **Configure**.</span></span>
    
3. <span data-ttu-id="7d85f-242">Wählen Sie **auf der** Seite Zusätzliche Aufgaben die Option **Benutzeranmelden ändern** aus, und wählen Sie dann Weiter **aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-242">On the **Additional tasks** page, select **Change user sign-in**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="7d85f-243">Geben Sie **auf Verbinden Azure AD** den Namen und das Kennwort Ihres globalen Administratorkontos ein, und wählen Sie dann Weiter **aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-243">On the **Connect to Azure AD** page, enter your global administrator account name and password, and then select **Next**.</span></span>
    
5. <span data-ttu-id="7d85f-244">Wählen Sie **auf der Seite Benutzeranmelden** die Option **Verbund mit AD FS** aus, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-244">On the **User sign-in** page, select **Federation with AD FS**, and then select **Next**.</span></span>
    
6. <span data-ttu-id="7d85f-245">Wählen Sie auf der **Seite AD FS-Farm** die Option Vorhandene **AD FS-Farm** verwenden aus, geben Sie **ADFS1** in das Feld **Servername** ein, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-245">On the **AD FS farm** page, select **Use an existing AD FS farm**, enter **ADFS1** in the **Server Name** box, and then select **Next**.</span></span>
    
7. <span data-ttu-id="7d85f-246">Wenn Sie zur Eingabe von Serveranmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen des CORP User1-Kontos ein, und wählen \\ Sie dann **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-246">When prompted for server credentials, enter the credentials of the CORP\\User1 account, and then select **OK**.</span></span>
    
8. <span data-ttu-id="7d85f-247">Geben Sie **auf der Seite Anmeldeinformationen** des Domänenadministrators corp **\\ User1** in das Feld **Benutzername** ein, geben Sie das Kontokennwort in das Feld **Kennwort** ein, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-247">On the **Domain Administrator** credentials page, enter **CORP\\User1** in the **Username** box, enter the account password in the **Password** box, and then select **Next**.</span></span>
    
9. <span data-ttu-id="7d85f-248">Geben Sie auf der **Seite AD FS-Dienstkonto** corp  **\\ ADFS-Service** in das Feld Domänenbenutzername ein, geben Sie das Kontokennwort in das Feld **Domänenbenutzerkennwort** ein, und wählen Sie dann Weiter **aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-248">On the **AD FS service account** page, enter **CORP\\ADFS-Service** in the **Domain Username** box, enter the account password in the **Domain User Password** box, and then select **Next**.</span></span>
    
10. <span data-ttu-id="7d85f-249">Wählen Sie auf der **Seite Azure AD-Domäne** unter **Domäne** den Namen der Domäne aus, die Sie zuvor in Phase 1 erstellt und Ihrem Abonnement hinzugefügt haben, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-249">On the **Azure AD Domain** page, in **Domain**, select the name of the domain that you previously created and added to your subscription in Phase 1, and then select **Next**.</span></span>
    
11. <span data-ttu-id="7d85f-250">Wählen Sie **auf der Seite** Bereit zum Konfigurieren die Option Konfigurieren **aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-250">On the **Ready to configure** page, select **Configure**.</span></span>
    
12. <span data-ttu-id="7d85f-251">Wählen Sie **auf der Seite Installation abgeschlossen** die Option Überprüfen **aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-251">On the **Installation complete** page, select **Verify**.</span></span>
    
    <span data-ttu-id="7d85f-252">Es sollten Nachrichten angezeigt werden, die angeben, dass sowohl die Intranet- als auch die Internetkonfiguration überprüft wurde.</span><span class="sxs-lookup"><span data-stu-id="7d85f-252">You should see messages indicating that both the intranet and internet configuration was verified.</span></span>
    
13. <span data-ttu-id="7d85f-253">Wählen Sie **auf der Seite Installation abgeschlossen** die Option Beenden **aus.**</span><span class="sxs-lookup"><span data-stu-id="7d85f-253">On the **Installation complete** page, select **Exit**.</span></span>
    
<span data-ttu-id="7d85f-254">Gehen Sie folgendermaßen vor, um zu zeigen, dass die Verbundauthentifizierung funktioniert:</span><span class="sxs-lookup"><span data-stu-id="7d85f-254">To demonstrate that federated authentication is working:</span></span>
  
1. <span data-ttu-id="7d85f-255">Öffnen Sie eine neue private Instanz Ihres Browsers auf Ihrem lokalen Computer, und wechseln Sie zu [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="7d85f-255">Open a new private instance of your browser on your local computer and go to [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
    
2. <span data-ttu-id="7d85f-256">Geben Sie für die Anmeldeinformationen user1@  \<*the domain created in Phase 1*> ein.</span><span class="sxs-lookup"><span data-stu-id="7d85f-256">For the sign-in credentials, enter **user1@**\<*the domain created in Phase 1*>.</span></span>
    
    <span data-ttu-id="7d85f-257">Wenn Ihre Testdomäne z. **B.** testlab.contoso.com ist, geben Sie "user1@testlab.contoso.com" ein.</span><span class="sxs-lookup"><span data-stu-id="7d85f-257">For example, if your test domain is **testlab.contoso.com**, you would enter "user1@testlab.contoso.com".</span></span> <span data-ttu-id="7d85f-258">Drücken Sie **die TAB-TASTE,** Microsoft 365 Sie automatisch umleiten können.</span><span class="sxs-lookup"><span data-stu-id="7d85f-258">Press the **Tab** key or allow Microsoft 365 to automatically redirect you.</span></span>
    
    <span data-ttu-id="7d85f-259">Jetzt sollten Sie die Seite **Die Verbindung ist nicht privat** sehen.</span><span class="sxs-lookup"><span data-stu-id="7d85f-259">You should now see a **Your connection is not private** page.</span></span> <span data-ttu-id="7d85f-260">Dies liegt daran, dass Sie ein selbst signiertes Zertifikat auf ADFS1 installiert haben, das ihr Desktopcomputer nicht überprüfen kann.</span><span class="sxs-lookup"><span data-stu-id="7d85f-260">You are seeing this because you installed a self-signed certificate on ADFS1 that your desktop computer can't validate.</span></span> <span data-ttu-id="7d85f-261">In einer Produktionsbereitstellung der Verbundauthentifizierung würden Sie ein Zertifikat von einer vertrauenswürdigen Zertifizierungsstelle verwenden, und Ihre Benutzer würden diese Seite nicht sehen.</span><span class="sxs-lookup"><span data-stu-id="7d85f-261">In a production deployment of federated authentication, you would use a certificate from a trusted certification authority and your users would not see this page.</span></span>
    
3. <span data-ttu-id="7d85f-262">Wählen Sie auf der Seite Ihre **Verbindung ist nicht privat** die Option **Erweitert** aus, und wählen Sie dann Weiter **zu aus. \<*your federation service FQDN*>**</span><span class="sxs-lookup"><span data-stu-id="7d85f-262">On the **Your connection is not private** page, select **Advanced**, and then select **Proceed to \<*your federation service FQDN*>**.</span></span> 
    
4. <span data-ttu-id="7d85f-263">Melden Sie sich auf der Seite mit dem Namen Ihrer fiktiven Organisation mit den folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="7d85f-263">On the page with the name of your fictional organization, sign in with the following:</span></span>
    
  - <span data-ttu-id="7d85f-264">**CORP\\User1** als Name</span><span class="sxs-lookup"><span data-stu-id="7d85f-264">**CORP\\User1** for the name</span></span>
    
  - <span data-ttu-id="7d85f-265">Das Kennwort für das Konto „User1“</span><span class="sxs-lookup"><span data-stu-id="7d85f-265">The password for the User1 account</span></span>
    
    <span data-ttu-id="7d85f-266">Die **Microsoft Office-Startseite** sollte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7d85f-266">You should see the **Microsoft Office Home** page.</span></span>
    
<span data-ttu-id="7d85f-p112">In diesem Verfahren wird veranschaulicht, dass Ihr Testabonnement im Verbund mit der AD DS-Domäne „corp.contoso.com“ steht, die auf DC1 gehostet wird. Nachfolgend finden Sie die Grundlagen des Authentifizierungsprozesses:</span><span class="sxs-lookup"><span data-stu-id="7d85f-p112">This procedure demonstrates that your trial subscription is federated with the AD DS corp.contoso.com domain hosted on DC1. Here are the basics of the authentication process:</span></span>
  
1. <span data-ttu-id="7d85f-269">Wenn Sie die Verbunddomäne verwenden, die Sie in Phase 1 mit dem Anmeldekontonamen erstellt haben, wird Ihr Browser von Microsoft 365 an den FQDN des Verbunddiensts und PROXY1 umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="7d85f-269">When you use the federated domain that you created in Phase 1 within the sign-in account name, Microsoft 365 redirects your browser to your federation service FQDN and PROXY1.</span></span>
    
2. <span data-ttu-id="7d85f-270">PROXY1 sendet dem lokalen Computer die Anmeldeseite des fiktiven Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="7d85f-270">PROXY1 sends your local computer the fictional company sign-in page.</span></span>
    
3. <span data-ttu-id="7d85f-271">Wenn Sie „CORP\\User1“ und das Kennwort an PROXY1 senden, werden diese Informationen an ADFS1 weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="7d85f-271">When you send CORP\\User1 and the password to PROXY1, it forwards them to ADFS1.</span></span>
    
4. <span data-ttu-id="7d85f-272">ADFS1 überprüft CORP\\User1 und das Kennwort mit DC1 und sendet dem lokalen Computer ein Sicherheitstoken.</span><span class="sxs-lookup"><span data-stu-id="7d85f-272">ADFS1 validates CORP\\User1 and the password with DC1 and sends your local computer a security token.</span></span>
    
5. <span data-ttu-id="7d85f-273">Der lokale Computer sendet das Sicherheitstoken an Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7d85f-273">Your local computer sends the security token to Microsoft 365.</span></span>
    
6. <span data-ttu-id="7d85f-274">Microsoft 365 überprüft, dass das Sicherheitstoken von ADFS1 erstellt wurde und erlaubt den Zugriff.</span><span class="sxs-lookup"><span data-stu-id="7d85f-274">Microsoft 365 validates that the security token was created by ADFS1 and allows access.</span></span>
    
<span data-ttu-id="7d85f-p113">Ihr Testabonnement ist jetzt mit Verbundauthentifizierung konfiguriert. Sie können diese Entwicklungs-/Testumgebung für erweiterte Authentifizierungsszenarien verwenden.</span><span class="sxs-lookup"><span data-stu-id="7d85f-p113">Your trial subscription is now configured with federated authentication. You can use this dev/test environment for advanced authentication scenarios.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="7d85f-277">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="7d85f-277">Next step</span></span>

<span data-ttu-id="7d85f-278">Wenn Sie bereit sind, die produktionsbereite Hochverfügbarkeits-Verbundauthentifizierung für Microsoft 365 in Azure zu bereitstellen, finden Sie weitere Informationen unter [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md).</span><span class="sxs-lookup"><span data-stu-id="7d85f-278">When you are ready to deploy production-ready, high availability federated authentication for Microsoft 365 in Azure, see [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md).</span></span>
  
