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
# <a name="federated-identity-for-your-microsoft-365-test-environment"></a><span data-ttu-id="50e14-103">Verbundidentität für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="50e14-103">Federated identity for your Microsoft 365 test environment</span></span>

<span data-ttu-id="50e14-104">*Diese Test Umgebungs Anleitung kann sowohl für Microsoft 365 für Unternehmen als auch für Office 365 Enterprise Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="50e14-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="50e14-p101">Microsoft 365 unterstützt Verbundidentität. Dies bedeutet, dass Microsoft 365, anstatt die Prüfung von Anmeldeinformationen selbst durchzuführen, den Benutzer, der eine Verbindung herstellt, auf einen Verbundauthentifizierungsserver verweist, der für Microsoft 365 vertrauenswürdig ist. Wenn die Anmeldeinformationen des Benutzers korrekt sind, gibt der Verbundauthentifizierungsserver ein Sicherheitstoken aus, das der Client als Nachweis der Authentifizierung an Microsoft 365 sendet. Verbundidentität ermöglicht das Abladen und zentrale Skalieren der Authentifizierung für ein Microsoft 365-Abonnement sowie erweiterte Authentifizierungs- und Sicherheitsszenarien.</span><span class="sxs-lookup"><span data-stu-id="50e14-p101">Microsoft 365 supports federated identity. This means that instead of performing the validation of credentials itself, Microsoft 365 refers the connecting user to a federated authentication server that Microsoft 365 trusts. If the user's credentials are correct, the federated authentication server issues a security token that the client then sends to Microsoft 365 as proof of authentication. Federated identity allows for the offloading and scaling up of authentication for a Microsoft 365 subscription and advanced authentication and security scenarios.</span></span>
  
<span data-ttu-id="50e14-109">In diesem Artikel wird beschrieben, wie Sie die Verbundauthentifizierung für Ihre Microsoft 365-Testumgebung konfigurieren, was Folgendes ergibt:</span><span class="sxs-lookup"><span data-stu-id="50e14-109">This article describes how to configure federated authentication for your Microsoft 365 test environment, resulting in the following:</span></span>

![Die Verbundauthentifizierung für die Microsoft 365-Testumgebung](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
<span data-ttu-id="50e14-111">Diese Konfiguration besteht aus:</span><span class="sxs-lookup"><span data-stu-id="50e14-111">This configuration consists of:</span></span>
  
- <span data-ttu-id="50e14-112">Ein Microsoft 365 E5-Test-oder Produktions Abonnement.</span><span class="sxs-lookup"><span data-stu-id="50e14-112">A Microsoft 365 E5 trial or production subscription.</span></span>
    
- <span data-ttu-id="50e14-113">Ein vereinfachtes Organisationsintranet, das mit dem Internet verbunden ist und das aus fünf virtuellen Computern in einem Subnetz eines virtuellen Azure-Netzwerks besteht (DC1, App1, CLIENT1, ADFS1 und PROXY1).</span><span class="sxs-lookup"><span data-stu-id="50e14-113">A simplified organization intranet connected to the internet, consisting of five virtual machines on a subnet of an Azure virtual network (DC1, APP1, CLIENT1, ADFS1, and PROXY1).</span></span> <span data-ttu-id="50e14-114">Azure AD Connect wird auf App1 ausgeführt, um die Liste der Konten in der Active Directory-Domänendienste Domäne mit Microsoft 365 zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="50e14-114">Azure AD Connect runs on APP1 to synchronize the list of accounts in the Active Directory Domain Services domain to Microsoft 365.</span></span> <span data-ttu-id="50e14-115">PROXY1 erhält die eingehenden Authentifizierungsanfragen.</span><span class="sxs-lookup"><span data-stu-id="50e14-115">PROXY1 receives the incoming authentication requests.</span></span> <span data-ttu-id="50e14-116">ADFS1 überprüft Anmeldeinformationen mit DC1 und gibt Sicherheitstoken aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-116">ADFS1 validates credentials with DC1 and issues security tokens.</span></span>
    
<span data-ttu-id="50e14-117">Das Einrichten dieser Testumgebung umfasst fünf Phasen:</span><span class="sxs-lookup"><span data-stu-id="50e14-117">Setting up this test environment involves five phases:</span></span>
- [<span data-ttu-id="50e14-118">Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="50e14-118">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="50e14-119">Phase 2: Erstellen des AD FS-Servers</span><span class="sxs-lookup"><span data-stu-id="50e14-119">Phase 2: Create the AD FS server</span></span>](#phase-2-create-the-ad-fs-server)
- [<span data-ttu-id="50e14-120">Phase 3: Erstellen des Webproxyservers</span><span class="sxs-lookup"><span data-stu-id="50e14-120">Phase 3: Create the web proxy server</span></span>](#phase-3-create-the-web-proxy-server)
- [<span data-ttu-id="50e14-121">Phase 4: Erstellen eines selbstsignierten Zertifikats und Konfigurieren von ADFS1 und PROXY1</span><span class="sxs-lookup"><span data-stu-id="50e14-121">Phase 4: Create a self-signed certificate and configure ADFS1 and PROXY1</span></span>](#phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1)
- [<span data-ttu-id="50e14-122">Phase 5: Konfigurieren von Microsoft 365 für Verbundidentität</span><span class="sxs-lookup"><span data-stu-id="50e14-122">Phase 5: Configure Microsoft 365 for federated identity</span></span>](#phase-5-configure-microsoft-365-for-federated-identity)
    
> [!NOTE]
> <span data-ttu-id="50e14-123">Sie können diese Testumgebung nicht mit einem Azure-Testabonnement konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="50e14-123">You can't configure this test environment with an Azure Trial subscription.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="50e14-124">Phase 1: Konfigurieren Sie Kennworthashsynchronisierung für Ihre Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="50e14-124">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="50e14-125">Befolgen Sie die Anweisungen unter [Kennworthash Synchronisierung für Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="50e14-125">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="50e14-126">Die resultierende Konfiguration sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="50e14-126">Your resulting configuration looks like this:</span></span>
  
![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase1.png)
  
<span data-ttu-id="50e14-128">Diese Konfiguration besteht aus: </span><span class="sxs-lookup"><span data-stu-id="50e14-128">This configuration consists of:</span></span>
  
- <span data-ttu-id="50e14-129">Eine Microsoft 365 E5-Testversion oder kostenpflichtige Abonnements.</span><span class="sxs-lookup"><span data-stu-id="50e14-129">A Microsoft 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="50e14-130">Ein vereinfachtes Organisationsintranet, das mit dem Internet verbunden ist, das aus den virtuellen Computern DC1, App1 und CLIENT1 in einem Subnetz eines virtuellen Azure-Netzwerks besteht.</span><span class="sxs-lookup"><span data-stu-id="50e14-130">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="50e14-131">Azure AD Connect wird auf App1 ausgeführt, um die TESTLAB Active Directory-Domänendienste (AD DS) Domäne regelmäßig mit dem Azure AD Mandanten Ihrer Microsoft 365-Abonnements zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="50e14-131">Azure AD Connect runs on APP1 to synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscriptions periodically.</span></span>

## <a name="phase-2-create-the-ad-fs-server"></a><span data-ttu-id="50e14-132">Phase 2: Erstellen des AD FS-Servers</span><span class="sxs-lookup"><span data-stu-id="50e14-132">Phase 2: Create the AD FS server</span></span>

<span data-ttu-id="50e14-133">Ein AD FS-Server bietet Verbundauthentifizierung zwischen Microsoft 365 und den Konten in der Domäne „corp.contoso.com“, die auf DC1 gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="50e14-133">An AD FS server provides federated authentication between Microsoft 365 and the accounts in the corp.contoso.com domain hosted on DC1.</span></span>
  
<span data-ttu-id="50e14-134">Um einen virtuellen Azure-Computer für ADFS1 zu erstellen, geben Sie den Namen Ihres Abonnements und der Ressourcengruppe sowie den Azure-Speicherort für Ihre Basiskonfiguration ein, und führen Sie diese Befehle in der Azure PowerShell-Befehlszeile auf Ihrem lokalen Computer aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-134">To create an Azure virtual machine for ADFS1, fill in the name of your subscription and the resource group and Azure location for your Base Configuration, and then run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
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

<span data-ttu-id="50e14-135">Im nächsten Schritt stellen Sie über das [Azure-Portal](https://portal.azure.com) eine Verbindung mit dem virtuellen Computer ADFS1 mit dem Namen und Kennwort des lokalen Administratorkontos von ADFS1 her und öffnen dann eine Windows PowerShell-Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="50e14-135">Next, use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the ADFS1 local administrator account name and password, and then open a Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="50e14-136">Führen Sie zum Überprüfen der Namensauflösung und der Netzwerkkommunikation zwischen ADFS1 und DC1 den Befehl **ping dc1.corp.contoso.com** aus, und vergewissern Sie sich, dass vier Antworten vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="50e14-136">To check name resolution and network communication between ADFS1 and DC1, run the **ping dc1.corp.contoso.com** command and check that there are four replies.</span></span>
  
<span data-ttu-id="50e14-137">Verknüpfen Sie als Nächstes unter Verwendung der folgenden Befehle an der Windows PowerShell-Eingabeaufforderung auf ADFS1 den virtuellen Computer ADFS1 mit der Domäne CORP.</span><span class="sxs-lookup"><span data-stu-id="50e14-137">Next, join the ADFS1 virtual machine to the CORP domain with these commands at the Windows PowerShell prompt on ADFS1.</span></span>
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

<span data-ttu-id="50e14-138">Die resultierende Konfiguration sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="50e14-138">Your resulting configuration looks like this:</span></span>
  
![Der AD FS-Server, der der DirSync für die Microsoft 365-Testumgebung hinzugefügt wurde](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase2.png)
  
## <a name="phase-3-create-the-web-proxy-server"></a><span data-ttu-id="50e14-140">Phase 3: Erstellen des Webproxyservers</span><span class="sxs-lookup"><span data-stu-id="50e14-140">Phase 3: Create the web proxy server</span></span>

<span data-ttu-id="50e14-141">PROXY1 stellt die Proxyfunktion für Authentifizierungsnachrichten zwischen Benutzern, die versuchen, sich zu authentifizieren, und ADFS1 bereit.</span><span class="sxs-lookup"><span data-stu-id="50e14-141">PROXY1 provides proxying of authentication messages between users trying to authenticate and ADFS1.</span></span>
  
<span data-ttu-id="50e14-142">Um einen virtuellen Azure-Computer für PROXY1 zu erstellen, geben Sie den Namen Ihrer Ressourcengruppe und den Azure-Speicherort ein und führen diese Befehle in der Azure PowerShell-Befehlszeile auf Ihrem lokalen Computer aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-142">To create an Azure virtual machine for PROXY1, fill in the name of your resource group and Azure location, and then run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
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
> <span data-ttu-id="50e14-143">PROXY1 wird einer statischen öffentlichen IP-Adresse zugewiesen, da Sie einen öffentlichen DNS-Eintrag erstellen, der darauf verweist, und der nicht geändert werden muss, wenn Sie den virtuellen PROXY1-Computer neu starten.</span><span class="sxs-lookup"><span data-stu-id="50e14-143">PROXY1 is assigned a static public IP address because you will create a public DNS record that points to it and it must not change when you restart the PROXY1 virtual machine.</span></span>
  
<span data-ttu-id="50e14-144">Fügen Sie als nächstes eine Regel zur Netzwerksicherheitsgruppe für das Corpnet-Subnetz hinzu, um unerwünschten eingehenden Datenverkehr aus dem Internet an PROXY1's private IP-Adresse und TCP-Port 443 zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="50e14-144">Next, add a rule to the network security group for the CorpNet subnet to allow unsolicited inbound traffic from the internet to PROXY1's private IP address and TCP port 443.</span></span> <span data-ttu-id="50e14-145">Führen Sie diese Befehle an der Azure PowerShell-Eingabeaufforderung auf dem lokalen Computer aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-145">Run these commands at the Azure PowerShell command prompt on your local computer.</span></span>
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
Get-AzNetworkSecurityGroup -Name CorpNet -ResourceGroupName $rgName | Add-AzNetworkSecurityRuleConfig -Name "HTTPS-to-PROXY1" -Description "Allow TCP 443 to PROXY1" -Access "Allow" -Protocol "Tcp" -Direction "Inbound" -Priority 101 -SourceAddressPrefix "Internet" -SourcePortRange "*" -DestinationAddressPrefix "10.0.0.101" -DestinationPortRange "443" | Set-AzNetworkSecurityGroup
```

<span data-ttu-id="50e14-146">Im nächsten Schritt stellen Sie über das [Azure-Portal](https://portal.azure.com) eine Verbindung mit dem virtuellen Computer PROXY1 mit dem Kontonamen und Kennwort des lokalen Administratorkontos von PROXY1 her und öffnen dann eine Windows PowerShell-Eingabeaufforderung auf PROXY1.</span><span class="sxs-lookup"><span data-stu-id="50e14-146">Next, use the [Azure portal](https://portal.azure.com) to connect to the PROXY1 virtual machine using the PROXY1 local administrator account name and password, and then open a Windows PowerShell command prompt on PROXY1.</span></span>
  
<span data-ttu-id="50e14-147">Führen Sie zum Überprüfen der Namensauflösung und der Netzwerkkommunikation zwischen PROXY1 und DC1 den Befehl **ping dc1.corp.contoso.com** aus, und vergewissern Sie sich, dass vier Antworten vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="50e14-147">To check name resolution and network communication between PROXY1 and DC1, run the **ping dc1.corp.contoso.com** command and check that there are four replies.</span></span>
  
<span data-ttu-id="50e14-148">Verknüpfen Sie als Nächstes unter Verwendung der folgenden Befehle an der Windows PowerShell-Eingabeaufforderung auf PROXY1 den virtuellen Computer PROXY1 mit der Domäne CORP.</span><span class="sxs-lookup"><span data-stu-id="50e14-148">Next, join the PROXY1 virtual machine to the CORP domain with these commands at the Windows PowerShell prompt on PROXY1.</span></span>
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

<span data-ttu-id="50e14-149">Zeigen Sie die öffentliche IP-Adresse von PROXY1 mit diesen Azure PowerShell-Befehlen auf dem lokalen Computer an.</span><span class="sxs-lookup"><span data-stu-id="50e14-149">Display the public IP address of PROXY1 with these Azure PowerShell commands on your local computer.</span></span>
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "PROXY1-PIP" -ResourceGroup $rgName).IPAddress
```

<span data-ttu-id="50e14-p106">Im nächsten Schritt arbeiten Sie mit Ihrem öffentlichen DNS-Anbieter und erstellen einen neuen öffentlichen DNS A-Eintrag für **fs.testlab.**\<*your DNS domain name*>, der in die IP-Adresse aufgelöst wird, die vom Befehl **Write-Host** angezeigt wird. Auf **fs.testlab.**\<*your DNS domain name*> wird nachfolgend als *FQDN des Verbunddiensts verwiesen*.</span><span class="sxs-lookup"><span data-stu-id="50e14-p106">Next, work with your public DNS provider and create a new public DNS A record for **fs.testlab.**\<*your DNS domain name*> that resolves to the IP address displayed by the **Write-Host** command. The **fs.testlab.**\<*your DNS domain name*> is hereafter referred to as the  *federation service FQDN*.</span></span>
  
<span data-ttu-id="50e14-154">Im nächsten Schritt stellen Sie über das [Azure-Portal](https://portal.azure.com) eine Verbindung mit dem virtuellen Computer DC1 unter Verwendung der Anmeldeinformationen „CORP\\User1“ her und führen dann die folgenden Befehle an einer Windows PowerShell-Eingabeaufforderung auf Administratorebene aus:</span><span class="sxs-lookup"><span data-stu-id="50e14-154">Next, use the [Azure portal](https://portal.azure.com) to connect to the DC1 virtual machine using the CORP\\User1 credentials, and then run the following commands at an administrator-level Windows PowerShell command prompt:</span></span>
  
```powershell
Add-DnsServerPrimaryZone -Name corp.contoso.com -ZoneFile corp.contoso.com.dns
Add-DnsServerResourceRecordA -Name "fs" -ZoneName corp.contoso.com -AllowUpdateAny -IPv4Address "10.0.0.100" -TimeToLive 01:00:00
```
<span data-ttu-id="50e14-155">Mit diesen Befehlen wird ein interner DNS-A-Eintrag erstellt, sodass virtuelle Computer im virtuellen Azure-Netzwerk den internen Verbunddienst-FQDN in ADFS1's private IP-Adresse auflösen können.</span><span class="sxs-lookup"><span data-stu-id="50e14-155">These commands create an internal DNS A record so that virtual machines on the Azure virtual network can resolve the internal federation service FQDN to ADFS1's private IP address.</span></span>
  
<span data-ttu-id="50e14-156">Die resultierende Konfiguration sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="50e14-156">Your resulting configuration looks like this:</span></span>
  
![Der Webanwendungs-Proxyserver, der der DirSync für die Microsoft 365-Testumgebung hinzugefügt wurde](../media/federated-identity-for-your-microsoft-365-dev-test-environment/federated-tlg-phase3.png)
  
## <a name="phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1"></a><span data-ttu-id="50e14-158">Phase 4: Erstellen eines selbstsignierten Zertifikats und Konfigurieren von ADFS1 und PROXY1</span><span class="sxs-lookup"><span data-stu-id="50e14-158">Phase 4: Create a self-signed certificate and configure ADFS1 and PROXY1</span></span>

<span data-ttu-id="50e14-159">In dieser Phase erstellen Sie ein selbstsigniertes digitales Zertifikat für den FQDN des Verbunddiensts und konfigurieren ADFS1 und PROXY1 als AD FS-Farm.</span><span class="sxs-lookup"><span data-stu-id="50e14-159">In this phase, you create a self-signed digital certificate for your federation service FQDN and configure ADFS1 and PROXY1 as an AD FS farm.</span></span>
  
<span data-ttu-id="50e14-160">Im nächsten Schritt stellen Sie über das [Azure-Portal](https://portal.azure.com) eine Verbindung mit dem virtuellen Computer DC1 unter Verwendung der Anmeldeinformationen „CORP\\User1“ her und öffnen dann eine Windows PowerShell-Eingabeaufforderung auf Administratorebene.</span><span class="sxs-lookup"><span data-stu-id="50e14-160">First, use the [Azure portal](https://portal.azure.com) to connect to the DC1 virtual machine using the CORP\\User1 credentials, and then open an administrator-level Windows PowerShell command prompt.</span></span>
  
<span data-ttu-id="50e14-161">Erstellen Sie als nächstes ein AD FS-Dienstkonto mit diesem Befehl an der Windows PowerShell Eingabeaufforderung auf DC1:</span><span class="sxs-lookup"><span data-stu-id="50e14-161">Next, create an AD FS service account with this command at the Windows PowerShell command prompt on DC1:</span></span>
  
```powershell
New-ADUser -SamAccountName ADFS-Service -AccountPassword (read-host "Set user password" -assecurestring) -name "ADFS-Service" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```
<span data-ttu-id="50e14-162">Beachten Sie, dass Sie von dem Befehl aufgefordert werden, das Kontokennwort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="50e14-162">Note that this command prompts you to supply the account password.</span></span> <span data-ttu-id="50e14-163">Verwenden Sie ein sicheres Kennwort, und notieren Sie es an einem sicheren Ort.</span><span class="sxs-lookup"><span data-stu-id="50e14-163">Choose a strong password and record it in a secured location.</span></span> <span data-ttu-id="50e14-164">Sie benötigen Sie für diese Phase und für Phase 5.</span><span class="sxs-lookup"><span data-stu-id="50e14-164">You will need it for this phase and for Phase 5.</span></span>
  
<span data-ttu-id="50e14-p108">Verwenden Sie das [Azure-Portal](https://portal.azure.com), um eine Verbindung zu dem virtuellen Computer ADFS1 unter Verwendung der Anmeldeinformationen „CORP\\User1“ herzustellen. Öffnen Sie eine Windows PowerShell-Eingabeaufforderung auf Administratorebene auf ADFS1, geben Sie den FQDN des Verbunddiensts ein, und führen Sie dann die folgenden Befehle aus, um ein selbstsigniertes Zertifikat zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="50e14-p108">Use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the CORP\\User1 credentials. Open an administrator-level Windows PowerShell command prompt on ADFS1, fill in your federation service FQDN, and then run these commands to create a self-signed certificate:</span></span>
  
```powershell
$fedServiceFQDN="<federation service FQDN>"
New-SelfSignedCertificate -DnsName $fedServiceFQDN -CertStoreLocation "cert:\LocalMachine\My"
New-Item -path c:\Certs -type directory
New-SmbShare -name Certs -path c:\Certs -changeaccess CORP\User1
```

<span data-ttu-id="50e14-167">Gehen Sie dann folgendermaßen vor, um das neue selbstsignierte Zertifikat als Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="50e14-167">Next, use these steps to save the new self-signed certificate as a file.</span></span>
  
1. <span data-ttu-id="50e14-168">Klicken Sie auf **Start**, geben Sie **mmc.exe**ein, und drücken Sie dann die **Eingabe**Taste.</span><span class="sxs-lookup"><span data-stu-id="50e14-168">Select **Start**, enter **mmc.exe**, and then press **Enter**.</span></span>
    
2. <span data-ttu-id="50e14-169">Wählen **File**Sie  >  **Snap-in "Datei hinzufügen/entfernen**" aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-169">Select **File** > **Add/Remove Snap-in**.</span></span>
    
3. <span data-ttu-id="50e14-170">Doppelklicken Sie in **Snap-Ins hinzufügen oder entfernen**in der Liste der verfügbaren Snap-Ins auf **Zertifikate** , wählen Sie **Computer Konto**aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-170">In **Add or Remove Snap-ins**, double-click **Certificates** in the list of available snap-ins, select **Computer account**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="50e14-171">Wählen Sie unter **Computer auswählen**die Option **Fertig stellen**aus, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-171">In **Select Computer**, select **Finish**, and then select **OK**.</span></span>
    
5. <span data-ttu-id="50e14-172">Öffnen Sie im Strukturbereich **Zertifikate (Lokaler Computer) > Persönlich > Zertifikate**.</span><span class="sxs-lookup"><span data-stu-id="50e14-172">In the tree pane, open **Certificates (Local Computer) > Personal > Certificates**.</span></span>
    
6. <span data-ttu-id="50e14-173">Wählen Sie das Zertifikat mit dem FQDN des Verbunddiensts aus, halten Sie es gedrückt (oder klicken Sie mit der rechten Maustaste), wählen Sie **alle Aufgaben**aus, und wählen Sie dann **exportieren**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-173">Select and hold (or right-click) the certificate with your federation service FQDN, select **All tasks**, and then select **Export**.</span></span>
    
7. <span data-ttu-id="50e14-174">Klicken Sie auf der **Willkommens** Seite auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="50e14-174">On the **Welcome** page, select **Next**.</span></span>
    
8. <span data-ttu-id="50e14-175">Wählen Sie auf der Seite **privaten Schlüssel exportieren** die Option **Ja**aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-175">On the **Export Private Key** page, select **Yes**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="50e14-176">Wählen Sie auf der Seite **Datei Format exportieren** die Option **alle erweiterten Eigenschaften exportieren**aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-176">On the **Export File Format** page, select **Export all extended properties**, and then select **Next**.</span></span>
    
10. <span data-ttu-id="50e14-177">Wählen Sie auf der Seite **Sicherheit** die Option **Kennwort** aus, und geben Sie ein Kennwort in **Kennwort** und **Kennwort bestätigen ein.**</span><span class="sxs-lookup"><span data-stu-id="50e14-177">On the **Security** page, select **Password** and enter a password in **Password** and **Confirm password.**</span></span>
    
11. <span data-ttu-id="50e14-178">Wählen Sie auf der Seite **zu exportierende Datei** die Option **Durchsuchen**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-178">On the **File to Export** page, select **Browse**.</span></span>
    
12. <span data-ttu-id="50e14-179">Wechseln Sie zum **Ordner C \\ : certs** , geben Sie **SSL** unter **Dateiname**ein, und wählen Sie dann **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="50e14-179">Browse to the **C:\\Certs** folder, enter **SSL** in **File name**, and then select **Save.**</span></span>
    
13. <span data-ttu-id="50e14-180">Wählen Sie auf der Seite **zu exportierende Datei** die Option **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-180">On the **File to Export** page, select **Next**.</span></span>
    
14. <span data-ttu-id="50e14-181">Wählen Sie auf der Seite fertig stellen **des Zertifikat Exports den Assistenten** **Fertig stellen**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-181">On the **Completing the Certificate Export Wizard** page, select **Finish**.</span></span> <span data-ttu-id="50e14-182">Wenn Sie dazu aufgefordert werden, wählen Sie **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-182">When prompted, select **OK**.</span></span>
    
<span data-ttu-id="50e14-183">Im nächsten Schritt erstellen Sie den AD FS-Dienst mit dem folgenden Befehl an der Windows PowerShell-Eingabeaufforderung auf ADFS1:</span><span class="sxs-lookup"><span data-stu-id="50e14-183">Next, install the AD FS service with this command at the Windows PowerShell command prompt on ADFS1:</span></span>
  
```powershell
Install-WindowsFeature ADFS-Federation -IncludeManagementTools
```

<span data-ttu-id="50e14-184">Warten Sie, bis die Installation abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="50e14-184">Wait for the installation to complete.</span></span>
  
<span data-ttu-id="50e14-185">Konfigurieren Sie als Nächstes den AD FS-Dienst mit den folgenden Schritten:</span><span class="sxs-lookup"><span data-stu-id="50e14-185">Next, configure the AD FS service with these steps:</span></span>
  
1. <span data-ttu-id="50e14-186">Wählen Sie **Start**aus, und wählen Sie dann das Symbol **Server-Manager** aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-186">Select **Start**, and then select the **Server Manager** icon.</span></span>
    
2. <span data-ttu-id="50e14-187">Wählen Sie im Strukturbereich des Server-Managers **AD FS**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-187">In the tree pane of Server Manager, select **AD FS**.</span></span>
    
3. <span data-ttu-id="50e14-188">Wählen Sie oben in der Symbolleiste das orangefarbene Warnsymbol aus, und wählen Sie dann **den Verbunddienst auf diesem Server konfigurieren**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-188">In the tool bar at the top, select the orange caution symbol, and then select **Configure the federation service on this server**.</span></span>
    
4. <span data-ttu-id="50e14-189">Wählen Sie auf der **Willkommens** Seite des Assistenten zum Konfigurieren von Active Directory Verbunddienste die Option **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-189">On the **Welcome** page of the Active Directory Federation Services Configuration Wizard, select **Next**.</span></span>
    
5. <span data-ttu-id="50e14-190">Wählen Sie auf der Seite mit **AD DS verbinden** die Option **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-190">On the **Connect to AD DS** page, select **Next**.</span></span>
    
6. <span data-ttu-id="50e14-191">Auf der Seite **Diensteigenschaften angeben**:</span><span class="sxs-lookup"><span data-stu-id="50e14-191">On the **Specify Service Properties** page:</span></span>
    
  - <span data-ttu-id="50e14-192">Wählen Sie für **SSL-Zertifikat**den Pfeil nach unten aus, und wählen Sie dann das Zertifikat mit dem Namen des FQDN des Verbunddiensts aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-192">For **SSL Certificate**, select the down arrow, and then select the certificate with the name of your federation service FQDN.</span></span>
    
  - <span data-ttu-id="50e14-193">Geben Sie unter **Anzeigename des Verbunddiensts**den Namen ihrer fiktiven Organisation ein.</span><span class="sxs-lookup"><span data-stu-id="50e14-193">In **Federation Service Display Name**, enter the name of your fictional organization.</span></span>
    
  - <span data-ttu-id="50e14-194">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-194">Select **Next**.</span></span>
    
7. <span data-ttu-id="50e14-195">Wählen Sie auf der Seite **Dienstkonto angeben** die Option für **Kontonamen** **auswählen** aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-195">On the **Specify Service Account** page, select **Select** for **Account name**.</span></span>
    
8. <span data-ttu-id="50e14-196">Geben Sie unter **Benutzer oder Dienstkonto auswählen**den Namen **ADFS-Service**ein, wählen Sie **Namen überprüfen**aus, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-196">In **Select User or Service Account**, enter **ADFS-Service**, select **Check Names**, and then select **OK**.</span></span>
    
9. <span data-ttu-id="50e14-197">Geben Sie unter **Kontokennwort**das Kennwort für das ADFS-Service Konto ein, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-197">In **Account Password**, enter the password for the ADFS-Service account, and then select **Next**.</span></span>
    
10. <span data-ttu-id="50e14-198">Wählen Sie auf der Seite **Konfigurationsdatenbank angeben** die Option **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-198">On the **Specify Configuration Database** page, select **Next**.</span></span>
    
11. <span data-ttu-id="50e14-199">Wählen Sie auf der Seite **Überprüfungsoptionen** die Option **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-199">On the **Review Options** page, select **Next**.</span></span>
    
12. <span data-ttu-id="50e14-200">Wählen Sie auf der Seite **Voraussetzungen überprüfen** die Option **configure**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-200">On the **Pre-requisite Checks** page, select **Configure**.</span></span>

13. <span data-ttu-id="50e14-201">Klicken Sie auf der Seite **Ergebnisse** auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="50e14-201">On the **Results** page, select **Close**.</span></span>
    
14. <span data-ttu-id="50e14-202">Wählen Sie **Start**, wählen Sie das Symbol Power aus, wählen Sie **neu starten**aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-202">Select **Start**, select the power icon, select **Restart**, and then select **Continue**.</span></span>
    
<span data-ttu-id="50e14-203">Melden Sie sich über das [Azure-Portal](https://portal.azure.com) mit dem CORP\\User1-Konto bei PROXY1 an.</span><span class="sxs-lookup"><span data-stu-id="50e14-203">From the [Azure portal](https://portal.azure.com), connect to PROXY1 with the CORP\\User1 account credentials.</span></span>
  
<span data-ttu-id="50e14-204">Gehen Sie dann folgendermaßen vor, um das selbstsignierte Zertifikat auf \*\* PROXY1 und APP1\*\* zu installieren.</span><span class="sxs-lookup"><span data-stu-id="50e14-204">Next, use these steps to install the self-signed certificate on **both PROXY1 and APP1**.</span></span>
  
1. <span data-ttu-id="50e14-205">Klicken Sie auf **Start**, geben Sie **mmc.exe**ein, und drücken Sie dann die **Eingabe**Taste.</span><span class="sxs-lookup"><span data-stu-id="50e14-205">Select **Start**, enter **mmc.exe**, and then press **Enter**.</span></span>
    
2. <span data-ttu-id="50e14-206">Wählen Sie **Datei > Snap-in hinzufügen/entfernen**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-206">Select **File > Add/Remove Snap-in**.</span></span>
    
3. <span data-ttu-id="50e14-207">Doppelklicken Sie in **Snap-Ins hinzufügen oder entfernen**in der Liste der verfügbaren Snap-Ins auf **Zertifikate** , wählen Sie **Computer Konto**aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-207">In **Add or Remove Snap-ins**, double-click **Certificates** in the list of available snap-ins, select **Computer account**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="50e14-208">Wählen Sie unter **Computer auswählen**die Option **Fertig stellen**aus, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-208">In **Select Computer**, select **Finish**, and then select **OK**.</span></span>
    
5. <span data-ttu-id="50e14-209">Öffnen Sie im Strukturbereich **Zertifikate (lokaler Computer)**  >  **persönliche**  >  **Zertifikate**.</span><span class="sxs-lookup"><span data-stu-id="50e14-209">In the tree pane, open **Certificates (Local Computer)** > **Personal** > **Certificates**.</span></span>
    
6. <span data-ttu-id="50e14-210">Wählen Sie aus, und halten Sie (oder klicken Sie mit der rechten Maustaste auf) **persönlich**, wählen Sie **alle Aufgaben**aus, und wählen Sie dann **importieren**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-210">Select and hold (or right-click) **Personal**, select **All tasks**, and then select **Import**.</span></span>
    
7. <span data-ttu-id="50e14-211">Klicken Sie auf der **Willkommens** Seite auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="50e14-211">On the **Welcome** page, select **Next**.</span></span>
    
8. <span data-ttu-id="50e14-212">Geben Sie auf der Seite **zu importierende Datei** \*\* \\ \\ adfs1 \\ certs \\ SSL. pfx\*\*ein, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-212">On the **File to Import** page, enter **\\\\adfs1\\certs\\ssl.pfx**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="50e14-213">Geben Sie auf der Seite **privater Schlüsselschutz** das Zertifikat Kennwort in **Kennwort ein**, und wählen Sie dann **weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="50e14-213">On the **Private key protection** page, enter the certificate password in **Password**, and then select **Next.**</span></span>
    
10. <span data-ttu-id="50e14-214">Wählen Sie auf der Seite **Zertifikatspeicher** die Option **weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="50e14-214">On the **Certificate store** page, select **Next.**</span></span>
    
11. <span data-ttu-id="50e14-215">Klicken Sie auf **der Seite fertig** Stellung auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="50e14-215">On the **Completing** page, select **Finish**.</span></span>
    
12. <span data-ttu-id="50e14-216">Wählen Sie auf der Seite **Zertifikatspeicher** die Option **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-216">On the **Certificate Store** page, select **Next**.</span></span>
    
13. <span data-ttu-id="50e14-217">Wenn Sie dazu aufgefordert werden, wählen Sie **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-217">When prompted, select **OK**.</span></span>
    
14. <span data-ttu-id="50e14-218">Wählen Sie im Strukturbereich **Zertifikate**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-218">In the tree pane, select **Certificates**.</span></span>
    
15. <span data-ttu-id="50e14-219">Wählen Sie das Zertifikat aus, halten Sie es gedrückt (oder klicken Sie mit der rechten Maustaste darauf), und wählen Sie dann **Kopieren**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-219">Select and hold (or right-click) the certificate, and then select **Copy**.</span></span>
    
16. <span data-ttu-id="50e14-220">Öffnen Sie im Strukturbereich **Vertrauenswürdige Stammzertifizierungsstellen**  >  **Zertifikate**.</span><span class="sxs-lookup"><span data-stu-id="50e14-220">In the tree pane, open **Trusted Root Certification Authorities** > **Certificates**.</span></span>
    
17. <span data-ttu-id="50e14-221">Bewegen Sie den Mauszeiger unter die Liste der installierten Zertifikate, wählen Sie und halten Sie (oder klicken Sie mit der rechten Maustaste), und wählen Sie dann **Einfügen**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-221">Move your mouse pointer below the list of installed certificates, select and hold (or right-click), and then select **Paste**.</span></span>
    
<span data-ttu-id="50e14-222">Öffnen Sie eine PowerShell-Eingabeaufforderung auf Administratorebene, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="50e14-222">Open an administrator-level PowerShell command prompt and run the following command:</span></span>
  
```powershell
Install-WindowsFeature Web-Application-Proxy -IncludeManagementTools
```

<span data-ttu-id="50e14-223">Warten Sie, bis die Installation abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="50e14-223">Wait for the installation to complete.</span></span>
  
<span data-ttu-id="50e14-224">Verwenden Sie die folgenden Schritte, um den Webanwendungs-Proxydienst so zu konfigurieren, dass ADFS1 als Verbundserver verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="50e14-224">Use these steps to configure the web application proxy service to use ADFS1 as its federation server:</span></span>
  
1. <span data-ttu-id="50e14-225">Wählen Sie **Start**aus, und wählen Sie dann **Server-Manager**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-225">Select **Start**, and then select **Server Manager**.</span></span>
    
2. <span data-ttu-id="50e14-226">Wählen Sie im Strukturbereich **Remote Zugriff**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-226">In the tree pane, select **Remote Access**.</span></span>
    
3. <span data-ttu-id="50e14-227">Wählen Sie oben in der Symbolleiste das orangefarbene Warnsymbol aus, und wählen Sie dann **den Assistenten zum Öffnen des Webanwendungs-Proxys**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-227">In the tool bar at the top, select the orange caution symbol, and then select **Open the Web Application Proxy Wizard**.</span></span>
    
4. <span data-ttu-id="50e14-228">Wählen Sie auf der **Willkommens** Seite des Assistenten für die Webanwendungs Proxy Konfiguration die Option **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-228">On the **Welcome** page of the Web Application Proxy Configuration Wizard, select **Next**.</span></span>
    
5. <span data-ttu-id="50e14-229">Auf der Seite **Verbundserver**:</span><span class="sxs-lookup"><span data-stu-id="50e14-229">On the **Federation Server** page:</span></span>
    
  - <span data-ttu-id="50e14-230">Geben Sie im Feld **verbunddienstname** den FQDN des Verbunddiensts ein.</span><span class="sxs-lookup"><span data-stu-id="50e14-230">In the **Federation service name** box, enter your federation service FQDN.</span></span>
    
  - <span data-ttu-id="50e14-231">Geben Sie in das Feld **Benutzername den Namen** **Corp \\ User1**ein.</span><span class="sxs-lookup"><span data-stu-id="50e14-231">In the **User name** box, enter **CORP\\User1**.</span></span>
    
  - <span data-ttu-id="50e14-232">Geben Sie im Feld **Kennwort** das Kennwort für das user1-Konto ein.</span><span class="sxs-lookup"><span data-stu-id="50e14-232">In the **Password** box, enter the password for the User1 account.</span></span>
    
  - <span data-ttu-id="50e14-233">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-233">Select **Next**.</span></span>
    
6. <span data-ttu-id="50e14-234">Wählen Sie auf der Seite **AD FS-Proxy Zertifikat** den Pfeil nach unten aus, wählen Sie das Zertifikat mit dem FQDN des Verbunddiensts aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-234">On the **AD FS Proxy Certificate** page, select the down arrow, select the certificate with your federation service FQDN, and then select **Next**.</span></span>
    
7. <span data-ttu-id="50e14-235">Wählen Sie auf der Seite **Bestätigung** die Option **configure**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-235">On the **Confirmation** page, select **Configure**.</span></span>
    
8. <span data-ttu-id="50e14-236">Klicken Sie auf der Seite **Ergebnisse** auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="50e14-236">On the **Results** page, select **Close**.</span></span>
    
## <a name="phase-5-configure-microsoft-365-for-federated-identity"></a><span data-ttu-id="50e14-237">Phase 5: Konfigurieren von Microsoft 365 für Verbundidentität</span><span class="sxs-lookup"><span data-stu-id="50e14-237">Phase 5: Configure Microsoft 365 for federated identity</span></span>

<span data-ttu-id="50e14-238">Verwenden Sie das [Azure-Portal](https://portal.azure.com), um eine Verbindung zu dem virtuellen Computer APP1 unter Verwendung der Kontoanmeldeinformationen „CORP\\User1“ herzustellen.</span><span class="sxs-lookup"><span data-stu-id="50e14-238">Use the [Azure portal](https://portal.azure.com) to connect to the APP1 virtual machine with the CORP\\User1 account credentials.</span></span>
  
<span data-ttu-id="50e14-239">Verwenden Sie diese Schritte, um Azure AD Connect und Ihr Microsoft 365-Abonnement für die Verbundauthentifizierung zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="50e14-239">Use these steps to configure Azure AD Connect and your Microsoft 365 subscription for federated authentication:</span></span>
  
1. <span data-ttu-id="50e14-240">Doppelklicken Sie auf dem Desktop auf **Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="50e14-240">From the desktop, double-click **Azure AD Connect**.</span></span>
    
2. <span data-ttu-id="50e14-241">Wählen Sie auf der Seite **Willkommen bei Azure AD Connect** die Option **configure**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-241">On the **Welcome to Azure AD Connect** page, select **Configure**.</span></span>
    
3. <span data-ttu-id="50e14-242">Wählen Sie auf der Seite **Weitere Aufgaben** die Option **Benutzeranmeldung ändern**aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-242">On the **Additional tasks** page, select **Change user sign-in**, and then select **Next**.</span></span>
    
4. <span data-ttu-id="50e14-243">Geben Sie auf der Seite mit **Azure AD verbinden** den Namen des globalen Administratorkontos und das Kennwort ein, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-243">On the **Connect to Azure AD** page, enter your global administrator account name and password, and then select **Next**.</span></span>
    
5. <span data-ttu-id="50e14-244">Wählen Sie auf der Seite **Benutzeranmeldung** die Option Partner **Verbund mit AD FS**aus, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-244">On the **User sign-in** page, select **Federation with AD FS**, and then select **Next**.</span></span>
    
6. <span data-ttu-id="50e14-245">Wählen Sie auf der Seite **AD FS-Farm** die Option **vorhandene AD FS-Farm verwenden**aus, geben Sie **ADFS1** in das Feld **Server Name** ein, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-245">On the **AD FS farm** page, select **Use an existing AD FS farm**, enter **ADFS1** in the **Server Name** box, and then select **Next**.</span></span>
    
7. <span data-ttu-id="50e14-246">Wenn Sie zur Eingabe von Serveranmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen des \\ Kontos Corp user1 ein, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-246">When prompted for server credentials, enter the credentials of the CORP\\User1 account, and then select **OK**.</span></span>
    
8. <span data-ttu-id="50e14-247">Geben Sie auf der Seite Anmeldeinformationen für den **Domänen Administrator** in das Feld **Benutzername den Namen** **Corp \\ User1** ein, geben Sie das Kontokennwort in das Feld **Kennwort** ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="50e14-247">On the **Domain Administrator** credentials page, enter **CORP\\User1** in the **Username** box, enter the account password in the **Password** box, and then select **Next**.</span></span>
    
9. <span data-ttu-id="50e14-248">Geben Sie auf der Seite **AD FS-Dienstkonto** im Feld **Domänenname den Namen** **Corp \\ ADFS-Service** ein, geben Sie das Kontokennwort in das Feld **Domänenbenutzer Kennwort** ein, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-248">On the **AD FS service account** page, enter **CORP\\ADFS-Service** in the **Domain Username** box, enter the account password in the **Domain User Password** box, and then select **Next**.</span></span>
    
10. <span data-ttu-id="50e14-249">Wählen Sie auf der Seite **Azure AD Domäne** unter **Domäne**den Namen der Domäne aus, die Sie zuvor erstellt und Ihrem Abonnement in Phase 1 hinzugefügt haben, und wählen Sie dann **weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-249">On the **Azure AD Domain** page, in **Domain**, select the name of the domain that you previously created and added to your subscription in Phase 1, and then select **Next**.</span></span>
    
11. <span data-ttu-id="50e14-250">Wählen Sie auf der Seite " **vorbereiten zur Konfiguration** " die Option **configure**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-250">On the **Ready to configure** page, select **Configure**.</span></span>
    
12. <span data-ttu-id="50e14-251">Wählen Sie auf der Seite **Installation abgeschlossen** die Option **Verify**aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-251">On the **Installation complete** page, select **Verify**.</span></span>
    
    <span data-ttu-id="50e14-252">Es sollten Meldungen angezeigt werden, die darauf hindeuten, dass sowohl die Intranet-als auch die Internetkonfiguration überprüft wurden.</span><span class="sxs-lookup"><span data-stu-id="50e14-252">You should see messages indicating that both the intranet and internet configuration was verified.</span></span>
    
13. <span data-ttu-id="50e14-253">Klicken Sie auf der Seite **Installation abgeschlossen** auf **Beenden**.</span><span class="sxs-lookup"><span data-stu-id="50e14-253">On the **Installation complete** page, select **Exit**.</span></span>
    
<span data-ttu-id="50e14-254">Gehen Sie folgendermaßen vor, um zu zeigen, dass die Verbundauthentifizierung funktioniert:</span><span class="sxs-lookup"><span data-stu-id="50e14-254">To demonstrate that federated authentication is working:</span></span>
  
1. <span data-ttu-id="50e14-255">Öffnen Sie eine neue private Instanz Ihres Browsers auf Ihrem lokalen Computer, und wechseln Sie zu [https://admin.microsoft.com](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="50e14-255">Open a new private instance of your browser on your local computer and go to [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
    
2. <span data-ttu-id="50e14-256">Geben Sie für die Anmeldeinformationen user1@ ein **user1@** \<*the domain created in Phase 1*> .</span><span class="sxs-lookup"><span data-stu-id="50e14-256">For the sign-in credentials, enter **user1@**\<*the domain created in Phase 1*>.</span></span>
    
    <span data-ttu-id="50e14-257">Wenn Ihre Testdomäne beispielsweise **testlab.contoso.com**lautet, geben Sie "user1@testlab.contoso.com" ein.</span><span class="sxs-lookup"><span data-stu-id="50e14-257">For example, if your test domain is **testlab.contoso.com**, you would enter "user1@testlab.contoso.com".</span></span> <span data-ttu-id="50e14-258">Drücken Sie die **Tab** -Taste, oder lassen Sie Microsoft 365 automatisch umleiten.</span><span class="sxs-lookup"><span data-stu-id="50e14-258">Press the **Tab** key or allow Microsoft 365 to automatically redirect you.</span></span>
    
    <span data-ttu-id="50e14-259">Jetzt sollten Sie die Seite **Die Verbindung ist nicht privat** sehen.</span><span class="sxs-lookup"><span data-stu-id="50e14-259">You should now see a **Your connection is not private** page.</span></span> <span data-ttu-id="50e14-260">Sie sehen dies, weil Sie ein selbstsigniertes Zertifikat auf ADFS1 installiert haben, das Ihr Desktopcomputer nicht validieren kann.</span><span class="sxs-lookup"><span data-stu-id="50e14-260">You are seeing this because you installed a self-signed certificate on ADFS1 that your desktop computer can't validate.</span></span> <span data-ttu-id="50e14-261">In einer Produktionsbereitstellung der Verbundauthentifizierung würden Sie ein Zertifikat von einer vertrauenswürdigen Zertifizierungsstelle verwenden, und Ihre Benutzer würden diese Seite nicht sehen.</span><span class="sxs-lookup"><span data-stu-id="50e14-261">In a production deployment of federated authentication, you would use a certificate from a trusted certification authority and your users would not see this page.</span></span>
    
3. <span data-ttu-id="50e14-262">Wählen Sie auf der Seite **Ihre Verbindung ist nicht privat** die Option **erweitert**aus, und wählen Sie dann \*\*weiter zu \<*your federation service FQDN*> \*\*aus.</span><span class="sxs-lookup"><span data-stu-id="50e14-262">On the **Your connection is not private** page, select **Advanced**, and then select **Proceed to \<*your federation service FQDN*>**.</span></span> 
    
4. <span data-ttu-id="50e14-263">Melden Sie sich auf der Seite mit dem Namen Ihrer fiktiven Organisation mit den folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="50e14-263">On the page with the name of your fictional organization, sign in with the following:</span></span>
    
  - <span data-ttu-id="50e14-264">**CORP\\User1** als Name</span><span class="sxs-lookup"><span data-stu-id="50e14-264">**CORP\\User1** for the name</span></span>
    
  - <span data-ttu-id="50e14-265">Das Kennwort für das Konto „User1“</span><span class="sxs-lookup"><span data-stu-id="50e14-265">The password for the User1 account</span></span>
    
    <span data-ttu-id="50e14-266">Die **Microsoft Office-Startseite** sollte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="50e14-266">You should see the **Microsoft Office Home** page.</span></span>
    
<span data-ttu-id="50e14-p112">In diesem Verfahren wird veranschaulicht, dass Ihr Testabonnement im Verbund mit der AD DS-Domäne „corp.contoso.com“ steht, die auf DC1 gehostet wird. Nachfolgend finden Sie die Grundlagen des Authentifizierungsprozesses:</span><span class="sxs-lookup"><span data-stu-id="50e14-p112">This procedure demonstrates that your trial subscription is federated with the AD DS corp.contoso.com domain hosted on DC1. Here are the basics of the authentication process:</span></span>
  
1. <span data-ttu-id="50e14-269">Wenn Sie die Verbunddomäne verwenden, die Sie in Phase 1 mit dem Anmeldekontonamen erstellt haben, wird Ihr Browser von Microsoft 365 an den FQDN des Verbunddiensts und PROXY1 umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="50e14-269">When you use the federated domain that you created in Phase 1 within the sign-in account name, Microsoft 365 redirects your browser to your federation service FQDN and PROXY1.</span></span>
    
2. <span data-ttu-id="50e14-270">PROXY1 sendet dem lokalen Computer die Anmeldeseite des fiktiven Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="50e14-270">PROXY1 sends your local computer the fictional company sign-in page.</span></span>
    
3. <span data-ttu-id="50e14-271">Wenn Sie „CORP\\User1“ und das Kennwort an PROXY1 senden, werden diese Informationen an ADFS1 weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="50e14-271">When you send CORP\\User1 and the password to PROXY1, it forwards them to ADFS1.</span></span>
    
4. <span data-ttu-id="50e14-272">ADFS1 überprüft CORP\\User1 und das Kennwort mit DC1 und sendet dem lokalen Computer ein Sicherheitstoken.</span><span class="sxs-lookup"><span data-stu-id="50e14-272">ADFS1 validates CORP\\User1 and the password with DC1 and sends your local computer a security token.</span></span>
    
5. <span data-ttu-id="50e14-273">Der lokale Computer sendet das Sicherheitstoken an Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="50e14-273">Your local computer sends the security token to Microsoft 365.</span></span>
    
6. <span data-ttu-id="50e14-274">Microsoft 365 überprüft, dass das Sicherheitstoken von ADFS1 erstellt wurde und erlaubt den Zugriff.</span><span class="sxs-lookup"><span data-stu-id="50e14-274">Microsoft 365 validates that the security token was created by ADFS1 and allows access.</span></span>
    
<span data-ttu-id="50e14-p113">Ihr Testabonnement ist jetzt mit Verbundauthentifizierung konfiguriert. Sie können diese Entwicklungs-/Testumgebung für erweiterte Authentifizierungsszenarien verwenden.</span><span class="sxs-lookup"><span data-stu-id="50e14-p113">Your trial subscription is now configured with federated authentication. You can use this dev/test environment for advanced authentication scenarios.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="50e14-277">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="50e14-277">Next step</span></span>

<span data-ttu-id="50e14-278">Wenn Sie bereit sind, produktionsfähige Verbundauthentifizierung für hohe Verfügbarkeit für Microsoft 365 in Azure bereitzustellen, lesen Sie [Bereitstellen der Verbundauthentifizierung mit hoher Verfügbarkeit für Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md).</span><span class="sxs-lookup"><span data-stu-id="50e14-278">When you are ready to deploy production-ready, high availability federated authentication for Microsoft 365 in Azure, see [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md).</span></span>
  
