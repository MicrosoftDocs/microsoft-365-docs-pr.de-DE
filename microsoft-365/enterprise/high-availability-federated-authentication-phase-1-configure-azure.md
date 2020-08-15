---
title: Hoch Verfügbarkeits Verbund Authentifizierungs Phase 1 Konfigurieren von Azure
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
ms.assetid: 91266aac-4d00-4b5f-b424-86a1a837792c
description: 'Zusammenfassung: Konfigurieren der Microsoft Azure Infrastruktur zum Hosten der Verbundauthentifizierung mit hoher Verfügbarkeit für Microsoft 365.'
ms.openlocfilehash: a99259e8c60346665f76aeba3a8a440e0f9061f0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690798"
---
# <a name="high-availability-federated-authentication-phase-1-configure-azure"></a><span data-ttu-id="2bc96-103">Hochverfügbarkeit der Verbundauthentifizierung, Phase 1: Konfigurieren von Azure</span><span class="sxs-lookup"><span data-stu-id="2bc96-103">High availability federated authentication Phase 1: Configure Azure</span></span>

<span data-ttu-id="2bc96-104">In dieser Phase erstellen Sie die Ressourcengruppen, das virtuelle Netzwerk (VNet) und die Verfügbarkeits Sätze in Azure, die die virtuellen Computer in den Phasen 2, 3 und 4 hosten werden.</span><span class="sxs-lookup"><span data-stu-id="2bc96-104">In this phase, you create the resource groups, virtual network (VNet), and availability sets in Azure that will host the virtual machines in phases 2, 3, and 4.</span></span> <span data-ttu-id="2bc96-105">Sie müssen diese Phase abschließen, bevor Sie mit [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) fortfahren können.</span><span class="sxs-lookup"><span data-stu-id="2bc96-105">You must complete this phase before moving on to [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md).</span></span> <span data-ttu-id="2bc96-106">Unter [Bereitstellen der Verbundauthentifizierung mit hoher Verfügbarkeit für Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) für alle Phasen.</span><span class="sxs-lookup"><span data-stu-id="2bc96-106">See [Deploy high availability federated authentication for Microsoft 365 in Azure](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md) for all of the phases.</span></span>
  
<span data-ttu-id="2bc96-107">Azure muss mit diesen grundlegenden Komponenten ausgestattet werden:</span><span class="sxs-lookup"><span data-stu-id="2bc96-107">Azure must be provisioned with these basic components:</span></span>
  
- <span data-ttu-id="2bc96-108">Ressourcengruppen</span><span class="sxs-lookup"><span data-stu-id="2bc96-108">Resource groups</span></span>
    
- <span data-ttu-id="2bc96-109">Ein standortübergreifendes virtuelles Azure-Netzwerk (VNet) mit Subnetzen für das Hosting der virtuellen Computer in Azure</span><span class="sxs-lookup"><span data-stu-id="2bc96-109">A cross-premises Azure virtual network (VNet) with subnets for hosting the Azure virtual machines</span></span>
    
- <span data-ttu-id="2bc96-110">Netzwerksicherheitsgruppen zur Isolierung der Subnetze</span><span class="sxs-lookup"><span data-stu-id="2bc96-110">Network security groups for performing subnet isolation</span></span>
    
- <span data-ttu-id="2bc96-111">Verfügbarkeitsgruppen</span><span class="sxs-lookup"><span data-stu-id="2bc96-111">Availability sets</span></span>
    
## <a name="configure-azure-components"></a><span data-ttu-id="2bc96-112">Konfigurieren der Azure-Komponenten</span><span class="sxs-lookup"><span data-stu-id="2bc96-112">Configure Azure components</span></span>

<span data-ttu-id="2bc96-113">Füllen Sie die folgenden Tabellen aus, bevor Sie mit dem Konfigurieren von Azure-Komponenten beginnen.</span><span class="sxs-lookup"><span data-stu-id="2bc96-113">Before you begin configuring Azure components, fill in the following tables.</span></span> <span data-ttu-id="2bc96-114">Um Sie bei den Verfahren für die Konfiguration von Azure zu unterstützen, Drucken Sie diesen Abschnitt aus, notieren Sie die erforderlichen Informationen, oder kopieren Sie diesen Abschnitt in ein Dokument, und füllen Sie ihn aus.</span><span class="sxs-lookup"><span data-stu-id="2bc96-114">To assist you in the procedures for configuring Azure, print this section and write down the needed information or copy this section to a document and fill it in.</span></span> <span data-ttu-id="2bc96-115">Geben Sie in Tabelle V die Einstellungen für das VNet ein.</span><span class="sxs-lookup"><span data-stu-id="2bc96-115">For the settings of the VNet, fill in Table V.</span></span>
  
|<span data-ttu-id="2bc96-116">**Element**</span><span class="sxs-lookup"><span data-stu-id="2bc96-116">**Item**</span></span>|<span data-ttu-id="2bc96-117">**Konfigurationseinstellung**</span><span class="sxs-lookup"><span data-stu-id="2bc96-117">**Configuration setting**</span></span>|<span data-ttu-id="2bc96-118">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="2bc96-118">**Description**</span></span>|<span data-ttu-id="2bc96-119">**Wert**</span><span class="sxs-lookup"><span data-stu-id="2bc96-119">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2bc96-120">1.</span><span class="sxs-lookup"><span data-stu-id="2bc96-120">1.</span></span>  <br/> |<span data-ttu-id="2bc96-121">VNet-Name</span><span class="sxs-lookup"><span data-stu-id="2bc96-121">VNet name</span></span>  <br/> |<span data-ttu-id="2bc96-122">Ein Name, der dem VNet zugewiesen wird (z. B. FedAuthNet).</span><span class="sxs-lookup"><span data-stu-id="2bc96-122">A name to assign to the VNet (example FedAuthNet).</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="2bc96-124">2.</span><span class="sxs-lookup"><span data-stu-id="2bc96-124">2.</span></span>  <br/> |<span data-ttu-id="2bc96-125">VNet-Standort</span><span class="sxs-lookup"><span data-stu-id="2bc96-125">VNet location</span></span>  <br/> |<span data-ttu-id="2bc96-126">Das regionale Azure-Rechenzentrum, in dem sich das virtuelle Netzwerk befinden soll</span><span class="sxs-lookup"><span data-stu-id="2bc96-126">The regional Azure datacenter that will contain the virtual network.</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="2bc96-128">3.</span><span class="sxs-lookup"><span data-stu-id="2bc96-128">3.</span></span>  <br/> |<span data-ttu-id="2bc96-129">IP-Adresse des VPN-Geräts</span><span class="sxs-lookup"><span data-stu-id="2bc96-129">VPN device IP address</span></span>  <br/> |<span data-ttu-id="2bc96-130">Die öffentliche IPv4-Adresse der Schnittstelle des VPN-Geräts im Internet</span><span class="sxs-lookup"><span data-stu-id="2bc96-130">The public IPv4 address of your VPN device's interface on the Internet.</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="2bc96-132">4.</span><span class="sxs-lookup"><span data-stu-id="2bc96-132">4.</span></span>  <br/> |<span data-ttu-id="2bc96-133">VNet-Adressraum</span><span class="sxs-lookup"><span data-stu-id="2bc96-133">VNet address space</span></span>  <br/> |<span data-ttu-id="2bc96-p103">Der Adressraum für das virtuelle Netzwerk (Fragen Sie Ihre IT-Abteilung nach diesem Adressraum.)</span><span class="sxs-lookup"><span data-stu-id="2bc96-p103">The address space for the virtual network. Work with your IT department to determine this address space.</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="2bc96-137">5.</span><span class="sxs-lookup"><span data-stu-id="2bc96-137">5.</span></span>  <br/> |<span data-ttu-id="2bc96-138">Gemeinsam verwendeter IPsec-Schlüssel</span><span class="sxs-lookup"><span data-stu-id="2bc96-138">IPsec shared key</span></span>  <br/> |<span data-ttu-id="2bc96-p104">Eine aus 32 zufällig ausgewählten alphanumerischen Zeichen bestehende Zeichenfolge, die zur Authentifizierung beider Seiten der Standort-zu-Standort-VPN-Verbindung verwendet wird (Fragen Sie Ihre IT- oder Sicherheitsabteilung nach diesem Schlüsselwert. Alternativ finden Sie weitere Informationen unter [Create a random string for an IPsec preshared key](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx).)  </span><span class="sxs-lookup"><span data-stu-id="2bc96-p104">A 32-character random, alphanumeric string that will be used to authenticate both sides of the site-to-site VPN connection. Work with your IT or security department to determine this key value. Alternately, see [Create a random string for an IPsec preshared key](https://social.technet.microsoft.com/wiki/contents/articles/32330.create-a-random-string-for-an-ipsec-preshared-key.aspx).  </span></span><br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="2bc96-143">**Tabelle V: Konfiguration eines standortübergreifenden virtuellen Netzwerks**</span><span class="sxs-lookup"><span data-stu-id="2bc96-143">**Table V: Cross-premises virtual network configuration**</span></span>
  
<span data-ttu-id="2bc96-p105">Füllen Sie nun Tabelle S für die Subnetze dieser Lösung aus. Alle Adressräume sollten im CIDR (Classless Inter-Domain Routing)-Format angegeben werden, auch Netzwerkpräfixformat genannt. Beispiel: 10.24.64.0/20.</span><span class="sxs-lookup"><span data-stu-id="2bc96-p105">Next, fill in Table S for the subnets of this solution. All address spaces should be in Classless Interdomain Routing (CIDR) format, also known as network prefix format. An example is 10.24.64.0/20.</span></span>
  
<span data-ttu-id="2bc96-p106">Geben Sie für die ersten drei Subnetze einen Namen und einen einzigen IP-Adressraum aus dem Adressraum des virtuellen Netzwerks an. Gehen Sie wie folgt vor, um den 27-Bit-Adressraum (mit Präfixlänge „/27“) für das Azure-Gatewaysubnetz zu ermitteln:</span><span class="sxs-lookup"><span data-stu-id="2bc96-p106">For the first three subnets, specify a name and a single IP address space based on the virtual network address space. For the gateway subnet, determine the 27-bit address space (with a /27 prefix length) for the Azure gateway subnet with the following:</span></span>
  
1. <span data-ttu-id="2bc96-149">Setzen Sie die variablen Bits im Adressraum des VNet auf 1, bis zu den für das Gatewaysubnetz verwendeten Bits. Setzen Sie die verbleibenden Bits auf 0.</span><span class="sxs-lookup"><span data-stu-id="2bc96-149">Set the variable bits in the address space of the VNet to 1, up to the bits being used by the gateway subnet, then set the remaining bits to 0.</span></span>
    
2. <span data-ttu-id="2bc96-150">Übertragen Sie den resultierenden Bitblock ins Dezimalsystem, und drücken Sie ihn als Adressraum aus, wobei Sie als Präfixlänge die Größe des Gatewaysubnetzes festlegen.</span><span class="sxs-lookup"><span data-stu-id="2bc96-150">Convert the resulting bits to decimal and express it as an address space with the prefix length set to the size of the gateway subnet.</span></span>
    
<span data-ttu-id="2bc96-151">Weitere Informationen finden Sie unter [Adressraum Rechner für Azure-Gateway-Subnetze](https://gallery.technet.microsoft.com/scriptcenter/Address-prefix-calculator-a94b6eed) für einen PowerShell-Befehlsblock und eine C#-oder python-Konsolenanwendung, die diese Berechnung ausführt.</span><span class="sxs-lookup"><span data-stu-id="2bc96-151">See [Address space calculator for Azure gateway subnets](https://gallery.technet.microsoft.com/scriptcenter/Address-prefix-calculator-a94b6eed) for a PowerShell command block and C# or Python console application that performs this calculation for you.</span></span>
  
<span data-ttu-id="2bc96-152">Fragen Sie Ihre IT-Abteilung nach diesen Adressräumen aus dem Adressraum des virtuellen Netzwerks.</span><span class="sxs-lookup"><span data-stu-id="2bc96-152">Work with your IT department to determine these address spaces from the virtual network address space.</span></span>
  
|<span data-ttu-id="2bc96-153">**Element**</span><span class="sxs-lookup"><span data-stu-id="2bc96-153">**Item**</span></span>|<span data-ttu-id="2bc96-154">**Subnetzname**</span><span class="sxs-lookup"><span data-stu-id="2bc96-154">**Subnet name**</span></span>|<span data-ttu-id="2bc96-155">**Subnetzadressraum**</span><span class="sxs-lookup"><span data-stu-id="2bc96-155">**Subnet address space**</span></span>|<span data-ttu-id="2bc96-156">**Zweck**</span><span class="sxs-lookup"><span data-stu-id="2bc96-156">**Purpose**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2bc96-157">1.</span><span class="sxs-lookup"><span data-stu-id="2bc96-157">1.</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="2bc96-160">Das Subnetz, das von den virtuellen Computern (VMS) Active Directory-Domänendienste (AD DS) Domänencontroller und Verzeichnissynchronisierungsserver verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2bc96-160">The subnet used by the Active Directory Domain Services (AD DS) domain controller and directory synchronization server virtual machines (VMs).</span></span>  <br/> |
|<span data-ttu-id="2bc96-161">2.</span><span class="sxs-lookup"><span data-stu-id="2bc96-161">2.</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="2bc96-164">Das von den virtuellen Computern von AD FS verwendete Subnetz.</span><span class="sxs-lookup"><span data-stu-id="2bc96-164">The subnet used by the AD FS VMs.</span></span>  <br/> |
|<span data-ttu-id="2bc96-165">3.</span><span class="sxs-lookup"><span data-stu-id="2bc96-165">3.</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="2bc96-168">Das von den virtuellen Computern des Webanwendungsproxys verwendete Subnetz.</span><span class="sxs-lookup"><span data-stu-id="2bc96-168">The subnet used by the web application proxy VMs.</span></span>  <br/> |
|<span data-ttu-id="2bc96-169">4.</span><span class="sxs-lookup"><span data-stu-id="2bc96-169">4.</span></span>  <br/> |<span data-ttu-id="2bc96-170">GatewaySubnet</span><span class="sxs-lookup"><span data-stu-id="2bc96-170">GatewaySubnet</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="2bc96-172">Das von den virtuellen Computern des Azure-Gateways verwendete Subnetz.</span><span class="sxs-lookup"><span data-stu-id="2bc96-172">The subnet used by the Azure gateway VMs.</span></span>  <br/> |
   
 <span data-ttu-id="2bc96-173">**Tabelle S: Subnetze im virtuellen Netzwerk**</span><span class="sxs-lookup"><span data-stu-id="2bc96-173">**Table S: Subnets in the virtual network**</span></span>
  
<span data-ttu-id="2bc96-174">Tragen Sie in Tabelle I nun die statischen IP-Adressen ein, die den virtuellen Computern und den Load Balancer-Instanzen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="2bc96-174">Next, fill in Table I for the static IP addresses assigned to virtual machines and load balancer instances.</span></span>
  
|<span data-ttu-id="2bc96-175">**Element**</span><span class="sxs-lookup"><span data-stu-id="2bc96-175">**Item**</span></span>|<span data-ttu-id="2bc96-176">**Zweck**</span><span class="sxs-lookup"><span data-stu-id="2bc96-176">**Purpose**</span></span>|<span data-ttu-id="2bc96-177">**IP-Adresse im Subnetz**</span><span class="sxs-lookup"><span data-stu-id="2bc96-177">**IP address on the subnet**</span></span>|<span data-ttu-id="2bc96-178">**Wert**</span><span class="sxs-lookup"><span data-stu-id="2bc96-178">**Value**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2bc96-179">1.</span><span class="sxs-lookup"><span data-stu-id="2bc96-179">1.</span></span>  <br/> |<span data-ttu-id="2bc96-180">Statische IP-Adresse des ersten Domänencontrollers</span><span class="sxs-lookup"><span data-stu-id="2bc96-180">Static IP address of the first domain controller</span></span>  <br/> |<span data-ttu-id="2bc96-181">Die vierte mögliche IP-Adresse für den Adressraum des in Tabelle S, Element 1 definierten Subnetzes</span><span class="sxs-lookup"><span data-stu-id="2bc96-181">The fourth possible IP address for the address space of the subnet defined in Item 1 of Table S.</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="2bc96-183">2.</span><span class="sxs-lookup"><span data-stu-id="2bc96-183">2.</span></span>  <br/> |<span data-ttu-id="2bc96-184">Statische IP-Adresse des zweiten Domänencontrollers</span><span class="sxs-lookup"><span data-stu-id="2bc96-184">Static IP address of the second domain controller</span></span>  <br/> |<span data-ttu-id="2bc96-185">Die fünfte mögliche IP-Adresse für den Adressraum des in Tabelle S, Element 1 definierten Subnetzes</span><span class="sxs-lookup"><span data-stu-id="2bc96-185">The fifth possible IP address for the address space of the subnet defined in Item 1 of Table S.</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="2bc96-187">3.</span><span class="sxs-lookup"><span data-stu-id="2bc96-187">3.</span></span>  <br/> |<span data-ttu-id="2bc96-188">Statische IP-Adresse des Verzeichnissynchronisierungsservers</span><span class="sxs-lookup"><span data-stu-id="2bc96-188">Static IP address of the directory synchronization server</span></span>  <br/> |<span data-ttu-id="2bc96-189">Die sechste mögliche IP-Adresse für den Adressraum des in Tabelle S, Element 1 definierten Subnetzes</span><span class="sxs-lookup"><span data-stu-id="2bc96-189">The sixth possible IP address for the address space of the subnet defined in Item 1 of Table S.</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="2bc96-191">4.</span><span class="sxs-lookup"><span data-stu-id="2bc96-191">4.</span></span>  <br/> |<span data-ttu-id="2bc96-192">Statische IP-Adresse des internen Lastenausgleichs für die AD FS-Server</span><span class="sxs-lookup"><span data-stu-id="2bc96-192">Static IP address of the internal load balancer for the AD FS servers</span></span>  <br/> |<span data-ttu-id="2bc96-193">Die vierte mögliche IP-Adresse für den Adressraum des in Tabelle S, Element 2 definierten Subnetzes</span><span class="sxs-lookup"><span data-stu-id="2bc96-193">The fourth possible IP address for the address space of the subnet defined in Item 2 of Table S.</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="2bc96-195">5.</span><span class="sxs-lookup"><span data-stu-id="2bc96-195">5.</span></span>  <br/> |<span data-ttu-id="2bc96-196">Statische IP-Adresse des ersten AD FS-Servers</span><span class="sxs-lookup"><span data-stu-id="2bc96-196">Static IP address of the first AD FS server</span></span>  <br/> |<span data-ttu-id="2bc96-197">Die fünfte mögliche IP-Adresse für den Adressraum des in Tabelle S, Element 2 definierten Subnetzes</span><span class="sxs-lookup"><span data-stu-id="2bc96-197">The fifth possible IP address for the address space of the subnet defined in Item 2 of Table S.</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="2bc96-199">6.</span><span class="sxs-lookup"><span data-stu-id="2bc96-199">6.</span></span>  <br/> |<span data-ttu-id="2bc96-200">Statische IP-Adresse des zweiten AD FS-Servers</span><span class="sxs-lookup"><span data-stu-id="2bc96-200">Static IP address of the second AD FS server</span></span>  <br/> |<span data-ttu-id="2bc96-201">Die sechste mögliche IP-Adresse für den Adressraum des in Tabelle S, Element 2 definierten Subnetzes</span><span class="sxs-lookup"><span data-stu-id="2bc96-201">The sixth possible IP address for the address space of the subnet defined in Item 2 of Table S.</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="2bc96-203">7.</span><span class="sxs-lookup"><span data-stu-id="2bc96-203">7.</span></span>  <br/> |<span data-ttu-id="2bc96-204">Statische IP-Adresse des ersten Webanwendungsproxy-Servers
</span><span class="sxs-lookup"><span data-stu-id="2bc96-204">Static IP address of the first web application proxy server</span></span>  <br/> |<span data-ttu-id="2bc96-205">Die vierte mögliche IP-Adresse für den Adressraum des in Tabelle S, Element 3 definierten Subnetzes</span><span class="sxs-lookup"><span data-stu-id="2bc96-205">The fourth possible IP address for the address space of the subnet defined in Item 3 of Table S.</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="2bc96-207">8.</span><span class="sxs-lookup"><span data-stu-id="2bc96-207">8.</span></span>  <br/> |<span data-ttu-id="2bc96-208">Statische IP-Adresse des zweiten Webanwendungsproxy-Servers
</span><span class="sxs-lookup"><span data-stu-id="2bc96-208">Static IP address of the second web application proxy server</span></span>  <br/> |<span data-ttu-id="2bc96-209">Die fünfte mögliche IP-Adresse für den Adressraum des in Tabelle S, Element 3 definierten Subnetzes</span><span class="sxs-lookup"><span data-stu-id="2bc96-209">The fifth possible IP address for the address space of the subnet defined in Item 3 of Table S.</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="2bc96-211">**Tabelle I: Statische IP-Adressen im virtuellen Netzwerk**</span><span class="sxs-lookup"><span data-stu-id="2bc96-211">**Table I: Static IP addresses in the virtual network**</span></span>
  
<span data-ttu-id="2bc96-212">Füllen Sie Tabelle D für die beiden DNS-Server in Ihrem lokalen Netzwerk aus, die Sie bei der Ersteinrichtung der Domänencontroller in Ihrem virtuellen Netzwerk verwenden möchten. Stellen Sie diese Liste gemeinsam mit Ihrer IT-Abteilung zusammen.</span><span class="sxs-lookup"><span data-stu-id="2bc96-212">For two Domain Name System (DNS) servers in your on-premises network that you want to use when initially setting up the domain controllers in your virtual network, fill in Table D. Work with your IT department to determine this list.</span></span>
  
|<span data-ttu-id="2bc96-213">**Element**</span><span class="sxs-lookup"><span data-stu-id="2bc96-213">**Item**</span></span>|<span data-ttu-id="2bc96-214">**Anzeigename des DNS-Servers**</span><span class="sxs-lookup"><span data-stu-id="2bc96-214">**DNS server friendly name**</span></span>|<span data-ttu-id="2bc96-215">**IP-Adresse des DNS-Servers**</span><span class="sxs-lookup"><span data-stu-id="2bc96-215">**DNS server IP address**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2bc96-216">1.</span><span class="sxs-lookup"><span data-stu-id="2bc96-216">1.</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="2bc96-219">2.</span><span class="sxs-lookup"><span data-stu-id="2bc96-219">2.</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="2bc96-222">**Tabelle D: Lokale DNS-Server**</span><span class="sxs-lookup"><span data-stu-id="2bc96-222">**Table D: On-premises DNS servers**</span></span>
  
<span data-ttu-id="2bc96-223">Um Pakete aus dem standortübergreifenden Netzwerk an Ihr Organisationsnetzwerk über die Standort-zu-Standort-VPN-Verbindung weiterzuleiten, müssen Sie das virtuelle Netzwerk mit einem lokalen Netzwerk konfigurieren, das über eine Liste der Adressräume (in der CIDR-Notation) für alle erreichbaren Standorte im lokalen Netzwerk Ihrer Organisation verfügt.</span><span class="sxs-lookup"><span data-stu-id="2bc96-223">To route packets from the cross-premises network to your organization network across the site-to-site VPN connection, you must configure the virtual network with a local network that has a list of the address spaces (in CIDR notation) for all of the reachable locations on your organization's on-premises network.</span></span> <span data-ttu-id="2bc96-224">Die Liste der Adressräume, die Ihr lokales Netzwerk definieren, muss eindeutig sein und darf sich nicht mit dem Adressraum überschneiden, der für andere virtuelle Netzwerke oder andere lokale Netzwerke verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2bc96-224">The list of address spaces that define your local network must be unique and must not overlap with the address space used for other virtual networks or other local networks.</span></span>
  
<span data-ttu-id="2bc96-p108">Für die Teilmenge der Adressräume für das lokale Netzwerk füllen Sie Tabelle L aus. Auch wenn hierfür nur drei Einträge vorgesehen sind, können Sie noch weitere hinzufügen. Erarbeiten Sie diese Liste der Adressräume gemeinsam mit Ihrer IT-Abteilung.</span><span class="sxs-lookup"><span data-stu-id="2bc96-p108">For the set of local network address spaces, fill in Table L. Note that three blank entries are listed but you will typically need more. Work with your IT department to determine this list of address spaces.</span></span>
  
|<span data-ttu-id="2bc96-227">**Element**</span><span class="sxs-lookup"><span data-stu-id="2bc96-227">**Item**</span></span>|<span data-ttu-id="2bc96-228">**Adressraum des lokalen Netzwerks**</span><span class="sxs-lookup"><span data-stu-id="2bc96-228">**Local network address space**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2bc96-229">1.</span><span class="sxs-lookup"><span data-stu-id="2bc96-229">1.</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="2bc96-231">2.</span><span class="sxs-lookup"><span data-stu-id="2bc96-231">2.</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="2bc96-233">3.</span><span class="sxs-lookup"><span data-stu-id="2bc96-233">3.</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="2bc96-235">**Tabelle L: Adresspräfixe für das lokale Netzwerk**</span><span class="sxs-lookup"><span data-stu-id="2bc96-235">**Table L: Address prefixes for the local network**</span></span>
  
<span data-ttu-id="2bc96-236">Lassen Sie uns nun mit dem Erstellen der Azure-Infrastruktur beginnen, um Ihre Verbundauthentifizierung für Microsoft 365 zu hosten.</span><span class="sxs-lookup"><span data-stu-id="2bc96-236">Now let's begin building the Azure infrastructure to host your federated authentication for Microsoft 365.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2bc96-237">[!HINWEIS] In den folgenden Befehlssätzen wird die aktuelle Version von Azure PowerShell verwendet.</span><span class="sxs-lookup"><span data-stu-id="2bc96-237">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="2bc96-238">Weitere Informationen finden Sie unter [Erste Schritte mit Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="2bc96-238">See [Get started with Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span></span> 
  
<span data-ttu-id="2bc96-239">Starten Sie zunächst eine Azure PowerShell-Eingabeaufforderung, und melden Sie sich bei Ihrem Konto an.</span><span class="sxs-lookup"><span data-stu-id="2bc96-239">First, start an Azure PowerShell prompt and login to your account.</span></span>
  
```powershell
Connect-AzAccount
```

> [!TIP]
> <span data-ttu-id="2bc96-240">Verwenden Sie diese [Microsoft Excel Konfigurations Arbeitsmappe](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx), um Ready-to-Run PowerShell-Befehlsblöcke basierend auf Ihren benutzerdefinierten Einstellungen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="2bc96-240">To generate ready-to-run PowerShell command blocks based on your custom settings, use this [Microsoft Excel configuration workbook](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/O365FedAuthInAzure_Config.xlsx).</span></span> 

<span data-ttu-id="2bc96-241">Rufen Sie den Namen Ihres Abonnements mithilfe des folgenden Befehls ab.</span><span class="sxs-lookup"><span data-stu-id="2bc96-241">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="2bc96-242">Verwenden Sie für ältere Versionen von Azure PowerShell stattdessen diesen Befehl.</span><span class="sxs-lookup"><span data-stu-id="2bc96-242">For older versions of Azure PowerShell, use this command instead.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select SubscriptionName
```

<span data-ttu-id="2bc96-243">Tragen Sie Ihr Azure-Abonnement ein.</span><span class="sxs-lookup"><span data-stu-id="2bc96-243">Set your Azure subscription.</span></span> <span data-ttu-id="2bc96-244">Ersetzen Sie alles innerhalb der Anführungszeichen, einschließlich der \< and > Zeichen, durch den korrekten Namen.</span><span class="sxs-lookup"><span data-stu-id="2bc96-244">Replace everything within the quotes, including the \< and > characters, with the correct name.</span></span>
  
```powershell
$subscrName="<subscription name>"
Select-AzSubscription -SubscriptionName $subscrName
```

<span data-ttu-id="2bc96-p111">Erstellen Sie im nächsten Schritt die neuen Ressourcengruppen. Listen Sie mit dem folgenden Befehl alle bereits vorhandenen Ressourcengruppen auf, um eine eindeutige Gruppe von Ressourcengruppennamen zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="2bc96-p111">Next, create the new resource groups. To determine a unique set of resource group names, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="2bc96-247">Tragen Sie die eindeutigen Ressourcengruppennamen in die folgende Tabelle ein.</span><span class="sxs-lookup"><span data-stu-id="2bc96-247">Fill in the following table for the set of unique resource group names.</span></span>
  
|<span data-ttu-id="2bc96-248">**Element**</span><span class="sxs-lookup"><span data-stu-id="2bc96-248">**Item**</span></span>|<span data-ttu-id="2bc96-249">**Ressourcengruppenname**</span><span class="sxs-lookup"><span data-stu-id="2bc96-249">**Resource group name**</span></span>|<span data-ttu-id="2bc96-250">**Zweck**</span><span class="sxs-lookup"><span data-stu-id="2bc96-250">**Purpose**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2bc96-251">1.</span><span class="sxs-lookup"><span data-stu-id="2bc96-251">1.</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="2bc96-253">Domänencontroller</span><span class="sxs-lookup"><span data-stu-id="2bc96-253">Domain controllers</span></span>  <br/> |
|<span data-ttu-id="2bc96-254">2.</span><span class="sxs-lookup"><span data-stu-id="2bc96-254">2.</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="2bc96-256">AD FS-Server</span><span class="sxs-lookup"><span data-stu-id="2bc96-256">AD FS servers</span></span>  <br/> |
|<span data-ttu-id="2bc96-257">3.</span><span class="sxs-lookup"><span data-stu-id="2bc96-257">3.</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="2bc96-259">Webanwendungsproxy-Server</span><span class="sxs-lookup"><span data-stu-id="2bc96-259">Web application proxy servers</span></span>  <br/> |
|<span data-ttu-id="2bc96-260">4.</span><span class="sxs-lookup"><span data-stu-id="2bc96-260">4.</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |<span data-ttu-id="2bc96-262">Infrastrukturelemente</span><span class="sxs-lookup"><span data-stu-id="2bc96-262">Infrastructure elements</span></span>  <br/> |
   
 <span data-ttu-id="2bc96-263">**Tabelle R: Ressourcengruppen**</span><span class="sxs-lookup"><span data-stu-id="2bc96-263">**Table R: Resource groups**</span></span>
  
<span data-ttu-id="2bc96-264">Erstellen Sie die neuen Ressourcengruppen mit den folgenden Befehlen.</span><span class="sxs-lookup"><span data-stu-id="2bc96-264">Create your new resource groups with these commands.</span></span>
  
```powershell
$locName="<an Azure location, such as West US>"
$rgName="<Table R - Item 1 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
$rgName="<Table R - Item 2 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
$rgName="<Table R - Item 3 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
$rgName="<Table R - Item 4 - Name column>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="2bc96-265">Erstellen Sie als Nächstes das virtuelle Azure-Netzwerk und seine Subnetze.</span><span class="sxs-lookup"><span data-stu-id="2bc96-265">Next, you create the Azure virtual network and its subnets.</span></span>
  
```powershell
$rgName="<Table R - Item 4 - Resource group name column>"
$locName="<your Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$vnetAddrPrefix="<Table V - Item 4 - Value column>"
$dnsServers=@( "<Table D - Item 1 - DNS server IP address column>", "<Table D - Item 2 - DNS server IP address column>" )
# Get the shortened version of the location
$locShortName=(Get-AzResourceGroup -Name $rgName).Location

# Create the subnets
$subnet1Name="<Table S - Item 1 - Subnet name column>"
$subnet1Prefix="<Table S - Item 1 - Subnet address space column>"
$subnet1=New-AzVirtualNetworkSubnetConfig -Name $subnet1Name -AddressPrefix $subnet1Prefix
$subnet2Name="<Table S - Item 2 - Subnet name column>"
$subnet2Prefix="<Table S - Item 2 - Subnet address space column>"
$subnet2=New-AzVirtualNetworkSubnetConfig -Name $subnet2Name -AddressPrefix $subnet2Prefix
$subnet3Name="<Table S - Item 3 - Subnet name column>"
$subnet3Prefix="<Table S - Item 3 - Subnet address space column>"
$subnet3=New-AzVirtualNetworkSubnetConfig -Name $subnet3Name -AddressPrefix $subnet3Prefix
$gwSubnet4Prefix="<Table S - Item 4 - Subnet address space column>"
$gwSubnet=New-AzVirtualNetworkSubnetConfig -Name "GatewaySubnet" -AddressPrefix $gwSubnet4Prefix

# Create the virtual network
New-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName -Location $locName -AddressPrefix $vnetAddrPrefix -Subnet $gwSubnet,$subnet1,$subnet2,$subnet3 -DNSServer $dnsServers

```

<span data-ttu-id="2bc96-266">Als Nächstes erstellen Sie Netzwerk Sicherheitsgruppen für jedes Subnetz mit virtuellen Computern.</span><span class="sxs-lookup"><span data-stu-id="2bc96-266">Next, you create network security groups for each subnet that has virtual machines.</span></span> <span data-ttu-id="2bc96-267">Um die Isolierung der Subnetze durchzuführen, können Sie Regeln für den jeweiligen Typ von Datenverkehr hinzufügen, der für die Netzwerksicherheitsgruppe eines Subnetzes erlaubt oder zurückgewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="2bc96-267">To perform subnet isolation, you can add rules for the specific types of traffic allowed or denied to the network security group of a subnet.</span></span>
  
```powershell
# Create network security groups
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name $vnetName

New-AzNetworkSecurityGroup -Name $subnet1Name -ResourceGroupName $rgName -Location $locShortName
$nsg=Get-AzNetworkSecurityGroup -Name $subnet1Name -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnet1Name -AddressPrefix $subnet1Prefix -NetworkSecurityGroup $nsg

New-AzNetworkSecurityGroup -Name $subnet2Name -ResourceGroupName $rgName -Location $locShortName
$nsg=Get-AzNetworkSecurityGroup -Name $subnet2Name -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnet2Name -AddressPrefix $subnet2Prefix -NetworkSecurityGroup $nsg

New-AzNetworkSecurityGroup -Name $subnet3Name -ResourceGroupName $rgName -Location $locShortName
$nsg=Get-AzNetworkSecurityGroup -Name $subnet3Name -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name $subnet3Name -AddressPrefix $subnet3Prefix -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
```

<span data-ttu-id="2bc96-268">Verwenden Sie anschließend diese Befehle zum Erstellen der Gateways für die Standort-zu-Standort-VPN-Verbindung.</span><span class="sxs-lookup"><span data-stu-id="2bc96-268">Next, use these commands to create the gateways for the site-to-site VPN connection.</span></span>
  
```powershell
$rgName="<Table R - Item 4 - Resource group name column>"
$locName="<Azure location>"
$vnetName="<Table V - Item 1 - Value column>"
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$subnet=Get-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name "GatewaySubnet"

# Attach a virtual network gateway to a public IP address and the gateway subnet
$publicGatewayVipName="PublicIPAddress"
$vnetGatewayIpConfigName="PublicIPConfig"
New-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$publicGatewayVip=Get-AzPublicIpAddress -Name $vnetGatewayIpConfigName -ResourceGroupName $rgName
$vnetGatewayIpConfig=New-AzVirtualNetworkGatewayIpConfig -Name $vnetGatewayIpConfigName -PublicIpAddressId $publicGatewayVip.Id -Subnet $subnet

# Create the Azure gateway
$vnetGatewayName="AzureGateway"
$vnetGateway=New-AzVirtualNetworkGateway -Name $vnetGatewayName -ResourceGroupName $rgName -Location $locName -GatewayType Vpn -VpnType RouteBased -IpConfigurations $vnetGatewayIpConfig

# Create the gateway for the local network
$localGatewayName="LocalNetGateway"
$localGatewayIP="<Table V - Item 3 - Value column>"
$localNetworkPrefix=@( <comma-separated, double-quote enclosed list of the local network address prefixes from Table L, example: "10.1.0.0/24", "10.2.0.0/24"> )
$localGateway=New-AzLocalNetworkGateway -Name $localGatewayName -ResourceGroupName $rgName -Location $locName -GatewayIpAddress $localGatewayIP -AddressPrefix $localNetworkPrefix

# Define the Azure virtual network VPN connection
$vnetConnectionName="S2SConnection"
$vnetConnectionKey="<Table V - Item 5 - Value column>"
$vnetConnection=New-AzVirtualNetworkGatewayConnection -Name $vnetConnectionName -ResourceGroupName $rgName -Location $locName -ConnectionType IPsec -SharedKey $vnetConnectionKey -VirtualNetworkGateway1 $vnetGateway -LocalNetworkGateway2 $localGateway

```

> [!NOTE]
> <span data-ttu-id="2bc96-269">Für die Verbundauthentifizierung einzelner Benutzer ist kein Rückgriff auf lokale Ressourcen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2bc96-269">Federated authentication of individual users does not rely on any on-premises resources.</span></span> <span data-ttu-id="2bc96-270">Wenn diese Standort-zu-Standort-VPN-Verbindung jedoch nicht mehr verfügbar ist, erhalten die Domänencontroller im VNet keine Updates für Benutzerkonten und Gruppen, die im lokalen Active Directory-Domänendienste ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2bc96-270">However, if this site-to-site VPN connection becomes unavailable, the domain controllers in the VNet will not receive updates to user accounts and groups made in the on-premises Active Directory Domain Services.</span></span> <span data-ttu-id="2bc96-271">Um dies zu verhindern, können Sie die hohe Verfügbarkeit für Ihre Standort-zu-Standort-VPN-Verbindung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2bc96-271">To ensure this does not happen, you can configure high availability for your site-to-site VPN connection.</span></span> <span data-ttu-id="2bc96-272">Weitere Informationen finden Sie unter [highly available Cross-premises and VNet-to-VNet Connectivity](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-highlyavailable) .</span><span class="sxs-lookup"><span data-stu-id="2bc96-272">For more information, see [Highly Available Cross-Premises and VNet-to-VNet Connectivity](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-highlyavailable)</span></span>
  
<span data-ttu-id="2bc96-273">Notieren Sie sich jetzt die öffentliche IPv4-Adresse des Azure-VPN-Gateways für Ihr virtuelles Netzwerk aus der Ausgabe des folgenden Befehls:</span><span class="sxs-lookup"><span data-stu-id="2bc96-273">Next, record the public IPv4 address of the Azure VPN gateway for your virtual network from the display of this command:</span></span>
  
```powershell
Get-AzPublicIpAddress -Name $publicGatewayVipName -ResourceGroupName $rgName
```

<span data-ttu-id="2bc96-p114">Konfigurieren Sie im nächsten Schritt die Verbindung zwischen dem lokalen VPN-Gerät und dem Azure-VPN-Gateway. Weitere Informationen finden Sie im Artikel zum Thema [Konfigurieren von VPN-Geräten](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpn-devices).</span><span class="sxs-lookup"><span data-stu-id="2bc96-p114">Next, configure your on-premises VPN device to connect to the Azure VPN gateway. For more information, see [Configure your VPN device](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpn-devices).</span></span>
  
<span data-ttu-id="2bc96-276">Sie benötigen folgende Informationen zum Konfigurieren Ihres lokalen VPN-Geräts:</span><span class="sxs-lookup"><span data-stu-id="2bc96-276">To configure your on-premises VPN device, you will need the following:</span></span>
  
- <span data-ttu-id="2bc96-277">Die öffentliche IPv4-Adresse des Azure-VPN-Gateways</span><span class="sxs-lookup"><span data-stu-id="2bc96-277">The public IPv4 address of the Azure VPN gateway.</span></span>
    
- <span data-ttu-id="2bc96-278">Den vorinstallierten IPsec-Schlüssel für die Standort-zu-Standort-VPN-Verbindung (Tabelle V, Element 5, Spalte „Wert")</span><span class="sxs-lookup"><span data-stu-id="2bc96-278">The IPsec pre-shared key for the site-to-site VPN connection (Table V - Item 5 - Value column).</span></span>
    
<span data-ttu-id="2bc96-p115">Vergewissern Sie sich im nächsten Schritt, dass der Adressraum des virtuellen Netzwerks aus Ihrem lokalen Netzwerk erreichbar ist. In der Regel fügen Sie dazu Ihrem VPN-Gerät eine dem Adressraum des virtuellen Netzwerks entsprechende Route hinzu und senden diese Route anschließend an die restliche Weiterleitungsinfrastruktur Ihres Organisationsnetzwerks. Erkundigen Sie sich bei Ihrer IT-Abteilung, wie Sie vorgehen sollen.</span><span class="sxs-lookup"><span data-stu-id="2bc96-p115">Next, ensure that the address space of the virtual network is reachable from your on-premises network. This is usually done by adding a route corresponding to the virtual network address space to your VPN device and then advertising that route to the rest of the routing infrastructure of your organization network. Work with your IT department to determine how to do this.</span></span>
  
<span data-ttu-id="2bc96-p116">Definieren Sie nun die Namen von drei Verfügbarkeitsgruppen. Füllen Sie Tabelle A aus. </span><span class="sxs-lookup"><span data-stu-id="2bc96-p116">Next, define the names of three availability sets. Fill out Table A.</span></span> 
  
|<span data-ttu-id="2bc96-284">**Element**</span><span class="sxs-lookup"><span data-stu-id="2bc96-284">**Item**</span></span>|<span data-ttu-id="2bc96-285">**Zweck**</span><span class="sxs-lookup"><span data-stu-id="2bc96-285">**Purpose**</span></span>|<span data-ttu-id="2bc96-286">**Name der Verfügbarkeitsgruppe**</span><span class="sxs-lookup"><span data-stu-id="2bc96-286">**Availability set name**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2bc96-287">1.</span><span class="sxs-lookup"><span data-stu-id="2bc96-287">1.</span></span>  <br/> |<span data-ttu-id="2bc96-288">Domänencontroller</span><span class="sxs-lookup"><span data-stu-id="2bc96-288">Domain controllers</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="2bc96-290">2.</span><span class="sxs-lookup"><span data-stu-id="2bc96-290">2.</span></span>  <br/> |<span data-ttu-id="2bc96-291">AD FS-Server</span><span class="sxs-lookup"><span data-stu-id="2bc96-291">AD FS servers</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |
|<span data-ttu-id="2bc96-293">3.</span><span class="sxs-lookup"><span data-stu-id="2bc96-293">3.</span></span>  <br/> |<span data-ttu-id="2bc96-294">Webanwendungsproxy-Server</span><span class="sxs-lookup"><span data-stu-id="2bc96-294">Web application proxy servers</span></span>  <br/> |![Zeile](../media/Common-Images/TableLine.png)  <br/> |
   
 <span data-ttu-id="2bc96-296">**Tabelle A: Verfügbarkeitsgruppen**</span><span class="sxs-lookup"><span data-stu-id="2bc96-296">**Table A: Availability sets**</span></span>
  
<span data-ttu-id="2bc96-297">Sie benötigen diese Namen bei der Erstellung der virtuellen Computer in den Phasen 2, 3 und 4.</span><span class="sxs-lookup"><span data-stu-id="2bc96-297">You will need these names when you create the virtual machines in phases 2, 3, and 4.</span></span>
  
<span data-ttu-id="2bc96-298">Erstellen Sie die neuen Verfügbarkeitsgruppen mithilfe der folgenden Azure PowerShell-Befehle.</span><span class="sxs-lookup"><span data-stu-id="2bc96-298">Create the new availability sets with these Azure PowerShell commands.</span></span>
  
```powershell
$locName="<the Azure location for your new resource group>"
$rgName="<Table R - Item 1 - Resource group name column>"
$avName="<Table A - Item 1 - Availability set name column>"
New-AzAvailabilitySet -ResourceGroupName $rgName -Name $avName -Location $locName -Sku Aligned  -PlatformUpdateDomainCount 5 -PlatformFaultDomainCount 2
$rgName="<Table R - Item 2 - Resource group name column>"
$avName="<Table A - Item 2 - Availability set name column>"
New-AzAvailabilitySet -ResourceGroupName $rgName -Name $avName -Location $locName -Sku Aligned  -PlatformUpdateDomainCount 5 -PlatformFaultDomainCount 2
$rgName="<Table R - Item 3 - Resource group name column>"
$avName="<Table A - Item 3 - Availability set name column>"
New-AzAvailabilitySet -ResourceGroupName $rgName -Name $avName -Location $locName -Sku Aligned  -PlatformUpdateDomainCount 5 -PlatformFaultDomainCount 2
```

<span data-ttu-id="2bc96-299">Haben Sie diese Phase erfolgreich abgeschlossen, sieht Ihre Konfiguration wie folgt aus.</span><span class="sxs-lookup"><span data-stu-id="2bc96-299">This is the configuration resulting from the successful completion of this phase.</span></span>
  
<span data-ttu-id="2bc96-300">**Phase 1: die Azure-Infrastruktur für die Verbundauthentifizierung mit hoher Verfügbarkeit für Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="2bc96-300">**Phase 1: The Azure infrastructure for high availability federated authentication for Microsoft 365**</span></span>

![Phase 1 der Microsoft 365-Verbundauthentifizierung mit hoher Verfügbarkeit in Azure mit der Azure-Infrastruktur](../media/4e7ba678-07df-40ce-b372-021bf7fc91fa.png)
  
## <a name="next-step"></a><span data-ttu-id="2bc96-302">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="2bc96-302">Next step</span></span>

<span data-ttu-id="2bc96-303">Verwenden Sie [Phase 2: Konfigurieren von Domänencontrollern](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) , um mit der Konfiguration dieser Arbeitsauslastung fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="2bc96-303">Use [Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md) to continue with the configuration of this workload.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2bc96-304">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2bc96-304">See Also</span></span>

[<span data-ttu-id="2bc96-305">Bereitstellen der Verbundauthentifizierung mit Hochverfügbarkeit für Microsoft 365 in Azure</span><span class="sxs-lookup"><span data-stu-id="2bc96-305">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>](deploy-high-availability-federated-authentication-for-microsoft-365-in-azure.md)
  
[<span data-ttu-id="2bc96-306">Verbundidentität für Ihre Microsoft 365-Entwicklungs-/Testumgebung</span><span class="sxs-lookup"><span data-stu-id="2bc96-306">Federated identity for your Microsoft 365 dev/test environment</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
[<span data-ttu-id="2bc96-307">Microsoft 365 Lösungs- und Architektur-Center</span><span class="sxs-lookup"><span data-stu-id="2bc96-307">Microsoft 365 solution and architecture center</span></span>](../solutions/solution-architecture-center.md)

[<span data-ttu-id="2bc96-308">Grundlegendes zu Microsoft 365 Identity und Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="2bc96-308">Understanding Microsoft 365 identity and Azure Active Directory</span></span>](about-microsoft-365-identity.md)


