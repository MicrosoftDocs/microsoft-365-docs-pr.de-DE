---
title: 'Schritt 2: Bereitstellung des Remotezugriffs auf lokale Apps und Dienste'
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom:
- M365solutions
description: Stellen Sie sicher, dass Ihre Remotemitarbeiter auf lokale Ressourcen zugreifen können, während Sie den Zugriff auf die Microsoft 365-Clouddienste optimieren.
ms.openlocfilehash: daa1a04912dd83c7a53769299b3870b90dbfd33a
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049558"
---
# <a name="step-2-provide-remote-access-to-on-premises-apps-and-services"></a><span data-ttu-id="73642-104">Schritt 2:</span><span class="sxs-lookup"><span data-stu-id="73642-104">Step 2.</span></span> <span data-ttu-id="73642-105">Bereitstellung des Remotezugriffs auf lokale Apps und Dienste</span><span class="sxs-lookup"><span data-stu-id="73642-105">Provide remote access to on-premises apps and services</span></span>

<span data-ttu-id="73642-106">Wenn Ihre Organisation eine VPN-Lösung für den Remotezugriff verwendet, die in der Regel VPN-Servern am Rande des Netzwerks und VPN-Clients umfasst, die auf den Geräten Ihrer Benutzer installiert sind, können Ihre Benutzer VPN-Verbindungen für den Remotezugriff auf lokale Apps und Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="73642-106">If your organization uses a remote access VPN solution, typically with VPN servers on the edge of your network and VPN clients installed on your users' devices, your users can use remote access VPN connections to access on-premises apps and servers.</span></span> <span data-ttu-id="73642-107">Möglicherweise müssen Sie jedoch den Datenverkehr zu den cloudbasierten Diensten von Microsoft 365 optimieren.</span><span class="sxs-lookup"><span data-stu-id="73642-107">But you may need to optimize traffic to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="73642-108">Wenn Ihre Benutzer keine VPN-Lösung verwenden, können Sie Azure Active Directory (Azure AD)-Anwendungs-Proxy und Azure-Punkt-zu-Standort-VPN (P2S) verwenden, um den Zugriff bereitzustellen, je nachdem, ob alle Ihre Apps webbasiert sind.</span><span class="sxs-lookup"><span data-stu-id="73642-108">If your users do not use a VPN solution, you can use Azure Active Directory (Azure AD) Application Proxy and Azure Point-to-Site (P2S) VPN to provide access, depending on whether all your apps are web-based.</span></span>

<span data-ttu-id="73642-109">Es gibt drei primäre Konfigurationen:</span><span class="sxs-lookup"><span data-stu-id="73642-109">There are three primary configurations:</span></span>

1. <span data-ttu-id="73642-110">Sie verwenden bereits eine VPN-Lösung für den Remotezugriff.</span><span class="sxs-lookup"><span data-stu-id="73642-110">You are already using a remote access VPN solution.</span></span>
2. <span data-ttu-id="73642-111">Sie verwenden keine VPN-Lösung für den Remotezugriff, Sie verfügen über eine hybride Identität und Sie benötigen Remotezugriff nur für lokale webbasierte Apps.</span><span class="sxs-lookup"><span data-stu-id="73642-111">You are not using a remote access VPN solution, you have hybrid identity, and you need remote access only to on-premises web-based apps.</span></span>
3. <span data-ttu-id="73642-112">Sie verwenden keine VPN-Lösung für den Remotezugriff und Sie benötigen Zugriff auf lokale Apps, von denen einige nicht webbasiert sind.</span><span class="sxs-lookup"><span data-stu-id="73642-112">You are not using a remote access VPN solution and you need access to on-premises apps, some of which are not web-based.</span></span>

<span data-ttu-id="73642-113">In diesem Flussdiagramm sehen Sie die Konfigurationsoptionen des Remotezugriffs, die in diesem Artikel erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="73642-113">See this flowchart for the remote access configuration options discussed in this article.</span></span>

![Flussdiagramm der Konfiguration des Remotezugriffs](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-flowchart.png)

<span data-ttu-id="73642-115">Bei Remotezugriffsverbindungen können Sie auch [Remotedesktop](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) verwenden, um Ihre Benutzer mit einem lokalen PC zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="73642-115">With remote access connections, you can also use [Remote Desktop](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) to connect your users to an on-premises PC.</span></span> <span data-ttu-id="73642-116">So können beispielsweise Remotemitarbeiter Remotedesktop verwenden, um eine Verbindung mit PC in ihrem Büro über ihre Windows-, IOS-oder Android-Gerät herstellen.</span><span class="sxs-lookup"><span data-stu-id="73642-116">For example, a remote worker can use Remote Desktop to connect to the PC in their office from their Windows, iOS or Android device.</span></span> <span data-ttu-id="73642-117">Sobald sie per Fernzugriff verbunden sind, können sie diese verwenden, als säßen sie davor.</span><span class="sxs-lookup"><span data-stu-id="73642-117">Once they are remotely connected, they can use it as if they were sitting in front of it.</span></span>

## <a name="optimize-performance-for-remote-access-vpn-clients-to-microsoft-365-cloud-services"></a><span data-ttu-id="73642-118">Optimieren der Leistung von VPN-Clients für den Remotezugriff auf Microsoft 365-Clouddienste</span><span class="sxs-lookup"><span data-stu-id="73642-118">Optimize performance for remote access VPN clients to Microsoft 365 cloud services</span></span>

<span data-ttu-id="73642-119">Wenn Ihre Remotemitarbeiter einen herkömmlichen VPN-Client für den Remotezugriff auf Ihr Organisationsnetzwerk verwenden, überprüfen Sie, ob der VPN-Client geteilte Tunnel unterstützt.</span><span class="sxs-lookup"><span data-stu-id="73642-119">If your remote workers are using a traditional VPN client to obtain remote access to your organization network, verify that the VPN client has split tunneling support.</span></span>

<span data-ttu-id="73642-120">Ohne geteilte Tunnel wird der gesamte Datenverkehr im Rahmend er Remotearbeit über die VPN-Verbindung gesendet, wo er an die Geräte am Rande Ihrer Organisation weitergeleitet, verarbeitet und dann im Internet gesendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="73642-120">Without split tunneling, all of your remote work traffic gets sent across the VPN connection, where it must be forwarded to your organization’s edge devices, get processed, and then sent on the Internet.</span></span>

![Netzwerkdatenverkehr von VPN-Clients ohne Tunneling](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

<span data-ttu-id="73642-122">Der Microsoft 365-Datenverkehr muss eine indirekte Route durch Ihre Organisation nehmen, die zu einem Microsoft-Netzwerkeintrittspunkt weit entfernt vom physischen Standort des VPN-Clients weitergeleitet werden könnte.</span><span class="sxs-lookup"><span data-stu-id="73642-122">Microsoft 365 traffic must take an indirect route through your organization, which could be the forwarded to a Microsoft network entry point far away from the VPN client’s physical location.</span></span> <span data-ttu-id="73642-123">Dieser indirekte Pfad erhöht die Latenz des Netzwerkverkehrs und verringert die Gesamtleistung.</span><span class="sxs-lookup"><span data-stu-id="73642-123">This indirect path adds latency to the network traffic and decreases overall performance.</span></span> 

<span data-ttu-id="73642-124">Mit geteilten Tunneln können Sie Ihren VPN-Client so konfigurieren, dass bestimmte Typen von Datenverkehr von der Übertragung über die VPN-Verbindung zum Unternehmensnetzwerk ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="73642-124">With split tunneling, you can configure your VPN client to exclude specific types of traffic from being sent over the VPN connection to the organization network.</span></span>

<span data-ttu-id="73642-125">Um den Zugriff auf Microsoft 365-Cloudressourcen zu optimieren, konfigurieren Sie die VPN-Clients für geteilte Tunneln so, dass der Datenverkehr an die Endpunkte der **Optimieren**-Kategorie von Microsoft 365 über die VPN-Verbindung ausgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="73642-125">To optimize access to Microsoft 365 cloud resources, configure your split tunneling VPN clients to exclude traffic to the **Optimize** category Microsoft 365 endpoints over the VPN connection.</span></span> <span data-ttu-id="73642-126">Weitere Informationen finden Sie unter [Office 365 Endpunkt-Kategorien](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories).</span><span class="sxs-lookup"><span data-stu-id="73642-126">For more information, see [Office 365 endpoint categories](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories).</span></span> <span data-ttu-id="73642-127">Sehen Sie sich die Liste der Endpunkte der Kategorie „Optimieren“ [hier](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="73642-127">See the list of Optimize category endpoints [here](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

![Netzwerkdatenverkehr von VPN-Clients mit Tunneling](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

<span data-ttu-id="73642-129">Auf diese Weise kann der VPN-Client wichtigen Datenverkehr innerhalb des Microsoft 365-Clouddienstes direkt über das Internet und zum nächstgelegenen Einstiegspunkt ins Microsoft-Netzwerk senden und empfangen.</span><span class="sxs-lookup"><span data-stu-id="73642-129">This allows the VPN client to send and receive crucial Microsoft 365 cloud service traffic directly over the Internet and to the nearest entry point into the Microsoft network.</span></span>

<span data-ttu-id="73642-130">Weitere Informationen und eine Anleitung finden Sie unter[Optimieren der Office 365-Konnektivität für Remotebenutzer mithilfe von geteilten VPN-Tunneln](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel).</span><span class="sxs-lookup"><span data-stu-id="73642-130">For more information and guidance, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel).</span></span>

## <a name="deploy-remote-access-when-all-your-apps-are-web-apps-and-you-have-hybrid-identity"></a><span data-ttu-id="73642-131">Remotezugriff bereitstellen, wenn alle Ihre Apps Web-Apps sind und Sie über eine hybride Identität verfügen</span><span class="sxs-lookup"><span data-stu-id="73642-131">Deploy remote access when all your apps are web apps and you have hybrid identity</span></span>

<span data-ttu-id="73642-132">Wenn Ihre Remotemitarbeiter keinen herkömmlichen VPN-Client verwenden und ihre lokalen Benutzerkonten und -gruppen mit Azure AD synchronisiert werden, können Sie Azure AD-Anwendungsproxy verwenden, um einen sicheren Remotezugriff für webbasierte Anwendungen zu gewährleisten, die auf Intranet-Servern gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="73642-132">If your remote workers are not using a traditional VPN client and your on-premises user accounts and groups are synchronized with Azure AD, you can use Azure AD Application Proxy to provide secure remote access for web-based applications hosted on intranet servers.</span></span> <span data-ttu-id="73642-133">Webbasierte Anwendungen umfassen Microsoft Office SharePoint Online-Websites, Outlook Web Access-Server oder beliebige andere webbasierte Branchenanwendungen.</span><span class="sxs-lookup"><span data-stu-id="73642-133">Web-based applications include SharePoint sites, Outlook Web Access servers, or any other web-based line of business applications.</span></span> 

<span data-ttu-id="73642-134">Hier sind die Komponenten des Azure AD-Anwendungsproxys.</span><span class="sxs-lookup"><span data-stu-id="73642-134">Here are the components of Azure AD Application Proxy.</span></span>

![Komponenten des Azure AD-Anwendungsproxys](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-application-proxy.png)

<span data-ttu-id="73642-136">Weitere Informationen finden Sie in dieser [Übersicht über den Azure AD-Anwendungsproxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).</span><span class="sxs-lookup"><span data-stu-id="73642-136">For more information, see this [overview of Azure AD Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).</span></span>

## <a name="deploy-remote-access-when-not-all-your-apps-are-web-apps"></a><span data-ttu-id="73642-137">Remotezugriff bereitstellen, wenn nicht alle Ihre Apps Web-Apps sind</span><span class="sxs-lookup"><span data-stu-id="73642-137">Deploy remote access when not all your apps are web apps</span></span>

<span data-ttu-id="73642-138">Wenn Ihre Remotemitarbeiter keinen herkömmlichen VPN-Client verwenden und keine Ihrer Apps webbasiert ist, können Sie ein Azure-Punkt-zu-Standort-VPN (P2S) verwenden.</span><span class="sxs-lookup"><span data-stu-id="73642-138">If your remote workers are not using a traditional VPN client and any of your apps are not web-based, you can use an Azure Point-to-Site (P2S) VPN.</span></span>

<span data-ttu-id="73642-139">Eine P2S-VPN-Verbindung erstellt eine sichere Verbindung vom Gerät eines Remotemitarbeiters zu Ihrem Organisationsnetzwerk über ein virtuelles Azure-Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="73642-139">A P2S VPN connection creates a secure connection from a remote worker’s device to your organization network through an Azure virtual network.</span></span> 

![Komponenten von Azure P2S-VPN](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-p2s-vpn.png)

<span data-ttu-id="73642-141">Weitere Informationen finden Sie in dieser [Übersicht über P2S-VPN](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about).</span><span class="sxs-lookup"><span data-stu-id="73642-141">For more information, see this [overview of P2S VPN](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about).</span></span>

## <a name="deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices"></a><span data-ttu-id="73642-142">Bereitstellen von Windows Virtual Desktop zur Gewährleistung des Remotezugriffs für Mitarbeiter auf persönlichen Geräten</span><span class="sxs-lookup"><span data-stu-id="73642-142">Deploy Windows Virtual Desktop to provide remote access for remote workers using personal devices</span></span> 

<span data-ttu-id="73642-143">Nutzen Sie zur Unterstützung von Remotemitarbeitern, die nur Ihre persönlichen und nicht verwalteten Geräte verwenden können, Windows Virtual Desktop in Azure, um virtuelle Desktops für Ihre Benutzer zu erstellen und zuzuweisen, die sie von zu Hause aus nutzen können.</span><span class="sxs-lookup"><span data-stu-id="73642-143">To support remote workers who can only use their personal and unmanaged devices, use Windows Virtual Desktop in Azure to create and allocate virtual desktops for your users to use from home.</span></span>

<span data-ttu-id="73642-144">Virtualisierte PCs können sich genauso wie PCs verhalten, die mit Ihrem Unternehmensnetzwerk verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="73642-144">Virtualized PCs can act just like PCs connected to your organization network.</span></span>

<span data-ttu-id="73642-145">Weitere Informationen finden Sie in dieser [Übersicht über Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/overview).</span><span class="sxs-lookup"><span data-stu-id="73642-145">For more information, see [this overview of Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/overview).</span></span>

## <a name="admin-technical-resources-for-remote-access"></a><span data-ttu-id="73642-146">Verwaltung technischer Ressourcen für den Remotezugriff</span><span class="sxs-lookup"><span data-stu-id="73642-146">Admin technical resources for remote access</span></span>

- [<span data-ttu-id="73642-147">Den Office 365-Datenverkehr für Remotemitarbeiter schnell optimieren & die Auslastung Ihrer Infrastruktur verringern</span><span class="sxs-lookup"><span data-stu-id="73642-147">How to quickly optimize Office 365 traffic for remote staff & reduce the load on your infrastructure</span></span>](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571)
- [<span data-ttu-id="73642-148">Optimieren der Office 365-Konnektivität für Remotebenutzer mithilfe eines geteilten VPN-Tunnels</span><span class="sxs-lookup"><span data-stu-id="73642-148">Optimize Office 365 connectivity for remote users using VPN split tunneling</span></span>](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel)

## <a name="results-of-step-2"></a><span data-ttu-id="73642-149">Ergebnisse von Schritt 2</span><span class="sxs-lookup"><span data-stu-id="73642-149">Results of Step 2</span></span>

<span data-ttu-id="73642-150">Nach der Bereitstellung einer Remotezugriffslösung für Ihre Remotemitarbeiter:</span><span class="sxs-lookup"><span data-stu-id="73642-150">After deployment of a remote access solution for your remote workers:</span></span>

| <span data-ttu-id="73642-151">Konfiguration des Remotezugriffs</span><span class="sxs-lookup"><span data-stu-id="73642-151">Remote access configuration</span></span> | <span data-ttu-id="73642-152">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="73642-152">Results</span></span> |
|:-------|:-----|
| <span data-ttu-id="73642-153">Eine VPN-Lösung für den Remotezugriff ist eingerichtet</span><span class="sxs-lookup"><span data-stu-id="73642-153">A remote access VPN solution is in place</span></span> | <span data-ttu-id="73642-154">Sie haben den VPN-Client für den Remotezugriff für geteilten Tunnel und für die Kategorie „Optimieren“ von Microsoft 365-Endpunkten konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="73642-154">You have configured your remote access VPN client for split tunneling and for the Optimize category of Microsoft 365 endpoints.</span></span> |
| <span data-ttu-id="73642-155">Keine VPN-Lösung für den Remotezugriff und Sie benötigen Remotezugriff nur für lokale webbasierte Apps</span><span class="sxs-lookup"><span data-stu-id="73642-155">No remote access VPN solution and you need remote access only to on-premises web-based apps</span></span> | <span data-ttu-id="73642-156">Sie haben Azure-Anwendungsproxy konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="73642-156">You have configured Azure Application Proxy.</span></span> |
| <span data-ttu-id="73642-157">Keine VPN-Lösung für den Remotezugriff und Sie benötigen Zugriff auf lokale Apps, von denen einige nicht webbasiert sind</span><span class="sxs-lookup"><span data-stu-id="73642-157">No remote access VPN solution and you need access to on-premises apps, some of which are not web-based</span></span> | <span data-ttu-id="73642-158">Sie haben Azure P2S-VPN konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="73642-158">You have configured Azure P2S VPN.</span></span> |
| <span data-ttu-id="73642-159">Remotemitarbeiter verwenden Ihre privaten Geräte von zu Hause aus</span><span class="sxs-lookup"><span data-stu-id="73642-159">Remote workers are using their personal devices from home</span></span> | <span data-ttu-id="73642-160">Sie haben Windows Virtual Desktop konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="73642-160">You have configured Windows Virtual Desktop.</span></span> |
|||

## <a name="next-step"></a><span data-ttu-id="73642-161">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="73642-161">Next step</span></span>

<span data-ttu-id="73642-162">Fahren Sie fort mit [Schritt 3](empower-people-to-work-remotely-manage-endpoints.md), um Ihre Geräte, PCs und anderen Endpunkte zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="73642-162">Continue with [Step 3](empower-people-to-work-remotely-manage-endpoints.md) to manage your devices, PCs, and other endpoints.</span></span>
