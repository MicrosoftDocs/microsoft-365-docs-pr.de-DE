---
title: 'Schritt 2: Bereitstellung des Remotezugriffs auf lokale Apps und Dienste'
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: Stellen Sie sicher, dass Ihre Remotemitarbeiter auf lokale Ressourcen zugreifen können, während Sie den Zugriff auf die Microsoft 365-Clouddienste optimieren.
ms.openlocfilehash: bc446cf26ec99d3e9f81564b5474777c674603bc
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229431"
---
# <a name="step-2-provide-remote-access-to-on-premises-apps-and-services"></a><span data-ttu-id="8acda-p102">Schritt 2: Bereitstellung des Remotezugriffs auf lokale Apps und Dienste</span><span class="sxs-lookup"><span data-stu-id="8acda-p102">Step 2. Provide remote access to on-premises apps and services</span></span>

<span data-ttu-id="8acda-p103">Wenn Ihre Organisation eine VPN-Lösung für den Remotezugriff verwendet, die in der Regel VPN-Server am Rande des Netzwerks und VPN-Clients umfasst, die auf den Geräten Ihrer Benutzer installiert sind, können Ihre Benutzer VPN-Verbindungen für den Remotezugriff auf lokale Apps und Server verwenden. Möglicherweise müssen Sie jedoch den Datenverkehr zu Microsoft 365 cloudbasierten Diensten optimieren.</span><span class="sxs-lookup"><span data-stu-id="8acda-p103">If your organization uses a remote access VPN solution, typically with VPN servers on the edge of your network and VPN clients installed on your users' devices, your users can use remote access VPN connections to access on-premises apps and servers. But you may need to optimize traffic to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="8acda-108">Wenn Ihre Benutzer keine VPN-Lösung verwenden, können Sie Azure Active Directory (Azure AD)-Anwendungs-Proxy und Azure-Punkt-zu-Standort-VPN (P2S) verwenden, um den Zugriff bereitzustellen, je nachdem, ob alle Ihre Apps webbasiert sind.</span><span class="sxs-lookup"><span data-stu-id="8acda-108">If your users do not use a VPN solution, you can use Azure Active Directory (Azure AD) Application Proxy and Azure Point-to-Site (P2S) VPN to provide access, depending on whether all your apps are web-based.</span></span>

<span data-ttu-id="8acda-109">Das sind die primären Konfigurationen für den Remotezugriff:</span><span class="sxs-lookup"><span data-stu-id="8acda-109">Here are the primary configurations for remote access:</span></span>

- <span data-ttu-id="8acda-110">Sie verwenden bereits eine VPN-Lösung für den Remotezugriff.</span><span class="sxs-lookup"><span data-stu-id="8acda-110">You are already using a remote access VPN solution.</span></span>
- <span data-ttu-id="8acda-111">Sie verwenden keine RAS-VPN-Lösung und Sie möchten, dass Ihre Remotemitarbeiter Ihre eigenen Computer verwenden.</span><span class="sxs-lookup"><span data-stu-id="8acda-111">You are not using a remote access VPN solution and you want your remote workers to use their personal computers.</span></span>
- <span data-ttu-id="8acda-112">Sie verwenden keine VPN-Lösung für den Remotezugriff, Sie verfügen über eine hybride Identität und Sie benötigen Remotezugriff nur für lokale webbasierte Apps.</span><span class="sxs-lookup"><span data-stu-id="8acda-112">You are not using a remote access VPN solution, you have hybrid identity, and you need remote access only to on-premises web-based apps.</span></span>
- <span data-ttu-id="8acda-113">Sie verwenden keine VPN-Lösung für den Remotezugriff und Sie benötigen Zugriff auf lokale Apps, von denen einige nicht webbasiert sind.</span><span class="sxs-lookup"><span data-stu-id="8acda-113">You are not using a remote access VPN solution and you need access to on-premises apps, some of which are not web-based.</span></span>

<span data-ttu-id="8acda-114">In diesem Flussdiagramm sehen Sie die Konfigurationsoptionen des Remotezugriffs, die in diesem Artikel erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="8acda-114">See this flowchart for the remote access configuration options discussed in this article.</span></span>

![Flussdiagramm der Konfiguration des Remotezugriffs](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-flowchart.png)

<span data-ttu-id="8acda-116">Bei Remotezugriffsverbindungen können Sie auch [Remotedesktop](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) verwenden, um Ihre Benutzer mit einem lokalen PC zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="8acda-116">With remote access connections, you can also use [Remote Desktop](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) to connect your users to an on-premises PC.</span></span> <span data-ttu-id="8acda-117">So können beispielsweise Remotemitarbeiter Remotedesktop verwenden, um eine Verbindung mit dem PC in ihrem Büro über ihre Windows-, IOS- oder Android-Gerät herzustellen.</span><span class="sxs-lookup"><span data-stu-id="8acda-117">For example, a remote worker can use Remote Desktop to connect to the PC in their office from their Windows, iOS, or Android device.</span></span> <span data-ttu-id="8acda-118">Sobald sie per Fernzugriff verbunden sind, können sie diese verwenden, als säßen sie davor.</span><span class="sxs-lookup"><span data-stu-id="8acda-118">Once they are remotely connected, they can use it as if they were sitting in front of it.</span></span>

## <a name="optimize-performance-for-remote-access-vpn-clients-to-microsoft-365-cloud-services"></a><span data-ttu-id="8acda-119">Optimieren der Leistung von VPN-Clients für den Remotezugriff auf Microsoft 365-Clouddienste</span><span class="sxs-lookup"><span data-stu-id="8acda-119">Optimize performance for remote access VPN clients to Microsoft 365 cloud services</span></span>

<span data-ttu-id="8acda-120">Wenn Ihre Remotemitarbeiter einen herkömmlichen VPN-Client für den Remotezugriff auf Ihr Organisationsnetzwerk verwenden, überprüfen Sie, ob der VPN-Client geteilte Tunnel unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8acda-120">If your remote workers are using a traditional VPN client to obtain remote access to your organization network, verify that the VPN client has split tunneling support.</span></span>

<span data-ttu-id="8acda-121">Ohne geteilte Tunnel wird der gesamte Datenverkehr im Rahmend er Remotearbeit über die VPN-Verbindung gesendet, wo er an die Geräte am Rande Ihrer Organisation weitergeleitet, verarbeitet und dann im Internet gesendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="8acda-121">Without split tunneling, all of your remote work traffic gets sent across the VPN connection, where it must be forwarded to your organization’s edge devices, get processed, and then sent on the Internet.</span></span>

![Netzwerkdatenverkehr von VPN-Clients ohne Tunneling](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

<span data-ttu-id="8acda-p105">Microsoft 365-Datenverkehr muss eine indirekte Route durch Ihre Organisation nehmen, die an einen Microsoft-Netzwerkeinstiegspunkt weit vom physischen Standort des VPN-Clients weitergeleitet werden kann. Dieser indirekte Pfad erhöht die Latenz des Netzwerkdatenverkehrs und verringert die Gesamtleistung.</span><span class="sxs-lookup"><span data-stu-id="8acda-p105">Microsoft 365 traffic must take an indirect route through your organization, which could be forwarded to a Microsoft network entry point far away from the VPN client’s physical location. This indirect path adds latency to the network traffic and decreases overall performance.</span></span>

<span data-ttu-id="8acda-125">Mit geteilten Tunneln können Sie Ihren VPN-Client so konfigurieren, dass bestimmte Typen von Datenverkehr von der Übertragung über die VPN-Verbindung zum Unternehmensnetzwerk ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="8acda-125">With split tunneling, you can configure your VPN client to exclude specific types of traffic from being sent over the VPN connection to the organization network.</span></span>

<span data-ttu-id="8acda-126">Um den Zugriff auf Microsoft 365-Cloudressourcen zu optimieren, konfigurieren Sie die VPN-Clients für geteilte Tunneln so, dass der Datenverkehr an die Endpunkte der **Optimieren**-Kategorie von Microsoft 365 über die VPN-Verbindung ausgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="8acda-126">To optimize access to Microsoft 365 cloud resources, configure your split tunneling VPN clients to exclude traffic to the **Optimize** category Microsoft 365 endpoints over the VPN connection.</span></span> <span data-ttu-id="8acda-127">Weitere Informationen finden Sie unter [Office 365 Endpunkt-Kategorien](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories).</span><span class="sxs-lookup"><span data-stu-id="8acda-127">For more information, see [Office 365 endpoint categories](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories).</span></span> <span data-ttu-id="8acda-128">Sehen Sie sich [diese Liste](../enterprise/urls-and-ip-address-ranges.md) der Endpunkte der Kategorie „Optimieren“ an.</span><span class="sxs-lookup"><span data-stu-id="8acda-128">See [this list](../enterprise/urls-and-ip-address-ranges.md) of Optimize category endpoints.</span></span>

<span data-ttu-id="8acda-129">Hier sehen Sie den resultierenden Datenverkehrsfluss, bei dem der größte Teil des Datenverkehrs an Microsoft 365-Cloud-Apps die VPN-Verbindung umgehen kann.</span><span class="sxs-lookup"><span data-stu-id="8acda-129">Here is the resulting traffic flow, in which most of the traffic to Microsoft 365 cloud apps bypass the VPN connection.</span></span>

![Netzwerkdatenverkehr von VPN-Clients mit Tunneling](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

<span data-ttu-id="8acda-131">Auf diese Weise kann der VPN-Client wichtigen Datenverkehr innerhalb des Microsoft 365-Clouddienstes direkt über das Internet und zum nächstgelegenen Einstiegspunkt ins Microsoft-Netzwerk senden und empfangen.</span><span class="sxs-lookup"><span data-stu-id="8acda-131">This allows the VPN client to send and receive crucial Microsoft 365 cloud service traffic directly over the Internet and to the nearest entry point into the Microsoft network.</span></span>

<span data-ttu-id="8acda-132">Weitere Informationen und eine Anleitung finden Sie unter[Optimieren der Office 365-Konnektivität für Remotebenutzer mithilfe von geteilten VPN-Tunneln](../enterprise/microsoft-365-vpn-split-tunnel.md).</span><span class="sxs-lookup"><span data-stu-id="8acda-132">For more information and guidance, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](../enterprise/microsoft-365-vpn-split-tunnel.md).</span></span>

## <a name="deploy-remote-access-when-all-your-apps-are-web-apps-and-you-have-hybrid-identity"></a><span data-ttu-id="8acda-133">Remotezugriff bereitstellen, wenn alle Ihre Apps Web-Apps sind und Sie über eine hybride Identität verfügen</span><span class="sxs-lookup"><span data-stu-id="8acda-133">Deploy remote access when all your apps are web apps and you have hybrid identity</span></span>

<span data-ttu-id="8acda-p107">Wenn Ihre Remotemitarbeiter keinen herkömmlichen VPN-Client verwenden und Ihre lokalen Benutzerkonten und Gruppen mit Azure AD synchronisiert werden, können Sie Azure AD-Anwendungsproxy verwenden, um sicheren Remotezugriff für webbasierte Anwendungen bereitzustellen, die auf lokalen Servern gehostet werden. Zu webbasierten Anwendungen gehören SharePoint Server-Websites, Outlook Webzugriff-Server oder andere webbasierte Geschäftsanwendungen.</span><span class="sxs-lookup"><span data-stu-id="8acda-p107">If your remote workers are not using a traditional VPN client and your on-premises user accounts and groups are synchronized with Azure AD, you can use Azure AD Application Proxy to provide secure remote access for web-based applications hosted on on-premises servers. Web-based applications include SharePoint Server sites, Outlook Web Access servers, or any other web-based line of business applications.</span></span>

<span data-ttu-id="8acda-136">Hier sind die Komponenten des Azure AD-Anwendungsproxys.</span><span class="sxs-lookup"><span data-stu-id="8acda-136">Here are the components of Azure AD Application Proxy.</span></span>

![Komponenten des Azure AD-Anwendungsproxys](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-application-proxy.png)

<span data-ttu-id="8acda-138">Weitere Informationen finden Sie in dieser [Übersicht über den Azure AD-Anwendungsproxy](/azure/active-directory/manage-apps/application-proxy).</span><span class="sxs-lookup"><span data-stu-id="8acda-138">For more information, see this [overview of Azure AD Application Proxy](/azure/active-directory/manage-apps/application-proxy).</span></span>

> [!NOTE]
> <span data-ttu-id="8acda-139">Der Azure AD-Anwendungsproxy ist in einem Microsoft 365-Abonnement nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="8acda-139">Azure AD Application Proxy is not included with a Microsoft 365 subscription.</span></span> <span data-ttu-id="8acda-140">Sie müssen die Nutzung mit einem separaten Azure-Abonnement bezahlen.</span><span class="sxs-lookup"><span data-stu-id="8acda-140">You must pay for usage with a separate Azure subscription.</span></span>

## <a name="deploy-remote-access-when-not-all-your-apps-are-web-apps"></a><span data-ttu-id="8acda-141">Remotezugriff bereitstellen, wenn nicht alle Ihre Apps Web-Apps sind</span><span class="sxs-lookup"><span data-stu-id="8acda-141">Deploy remote access when not all your apps are web apps</span></span>

<span data-ttu-id="8acda-142">Wenn Ihre Remotemitarbeiter keinen herkömmlichen VPN-Client verwenden und Sie über Apps verfügen, die nicht webbasiert ist, können Sie ein Azure-Punkt-zu-Standort-VPN (P2S) verwenden.</span><span class="sxs-lookup"><span data-stu-id="8acda-142">If your remote workers are not using a traditional VPN client and you have apps that are not web-based, you can use an Azure Point-to-Site (P2S) VPN.</span></span>

<span data-ttu-id="8acda-143">Eine P2S-VPN-Verbindung erstellt eine sichere Verbindung vom Gerät eines Remotemitarbeiters zu Ihrem Organisationsnetzwerk über ein virtuelles Azure-Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="8acda-143">A P2S VPN connection creates a secure connection from a remote worker’s device to your organization network through an Azure virtual network.</span></span>

![Komponenten von Azure P2S-VPN](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-p2s-vpn.png)

<span data-ttu-id="8acda-145">Weitere Informationen finden Sie in dieser [Übersicht über P2S-VPN](/azure/vpn-gateway/point-to-site-about).</span><span class="sxs-lookup"><span data-stu-id="8acda-145">For more information, see this [overview of P2S VPN](/azure/vpn-gateway/point-to-site-about).</span></span>

> [!NOTE]
> <span data-ttu-id="8acda-146">Der Azure P2S VPN ist in einem Microsoft 365-Abonnement nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="8acda-146">Azure P2S VPN is not included with a Microsoft 365 subscription.</span></span> <span data-ttu-id="8acda-147">Sie müssen die Nutzung mit einem separaten Azure-Abonnement bezahlen.</span><span class="sxs-lookup"><span data-stu-id="8acda-147">You must pay for usage with a separate Azure subscription.</span></span>

## <a name="deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices"></a><span data-ttu-id="8acda-148">Bereitstellen von Windows Virtual Desktop zur Gewährleistung des Remotezugriffs für Mitarbeiter auf persönlichen Geräten</span><span class="sxs-lookup"><span data-stu-id="8acda-148">Deploy Windows Virtual Desktop to provide remote access for remote workers using personal devices</span></span>

<span data-ttu-id="8acda-p110">Um Remotemitarbeiter zu unterstützen, die nur ihre persönlichen und nicht verwalteten Geräte verwenden können, verwenden Sie Windows Virtual Desktop in Azure, um virtuelle Desktops zu erstellen und zuzuordnen, die Ihre Benutzer von zu Hause aus verwenden können. Virtualisierte PCs können wie PCs fungieren, die mit Ihrem Organisationsnetzwerk verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="8acda-p110">To support remote workers who can only use their personal and unmanaged devices, use Windows Virtual Desktop in Azure to create and allocate virtual desktops for your users to use from home. Virtualized PCs can act just like PCs connected to your organization network.</span></span>

![Komponenten von Azure Windows Virtual Desktop](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-windows-virtual-desktop.png)

<span data-ttu-id="8acda-152">Weitere Informationen finden Sie in dieser [Übersicht über Windows Virtual Desktop](/azure/virtual-desktop/overview).</span><span class="sxs-lookup"><span data-stu-id="8acda-152">For more information, see this [overview of Windows Virtual Desktop](/azure/virtual-desktop/overview).</span></span>

> [!NOTE]
><span data-ttu-id="8acda-153">Windows Virtual Desktop ist in einem Microsoft 365-Abonnement nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="8acda-153">Windows Virtual Desktop is not included with a Microsoft 365 subscription.</span></span> <span data-ttu-id="8acda-154">Sie müssen die Nutzung mit einem separaten Azure-Abonnement bezahlen.</span><span class="sxs-lookup"><span data-stu-id="8acda-154">You must pay for usage with a separate Azure subscription.</span></span>

## <a name="protect-your-remote-desktop-services-connections-with-the-remote-desktop-services-gateway"></a><span data-ttu-id="8acda-155">Schützen der Remotedesktopdienste-Verbindungen mit dem Remotedesktopdienste-Gateway</span><span class="sxs-lookup"><span data-stu-id="8acda-155">Protect your Remote Desktop Services connections with the Remote Desktop Services Gateway</span></span>

<span data-ttu-id="8acda-156">Wenn Sie Remotedesktopdienste (Remote Desktop Services, RDS) verwenden, um Mitarbeitern das Herstellen einer Verbindung mit Windows-basierten Computern in Ihrem lokalen Netzwerk zu ermöglichen, sollten Sie ein Microsoft Remotedesktopdienste-Gateway in Ihrem Microsoft Edge-Netzwerk verwenden.</span><span class="sxs-lookup"><span data-stu-id="8acda-156">If you are using Remote Desktop Services (RDS) to allow employees to connect into Windows-based computers on your on-premises network, you should use a Microsoft Remote Desktop Services gateway in your edge network.</span></span> <span data-ttu-id="8acda-157">Das Gateway verwendet Transport Layer Security (TLS) zum Verschlüsseln des Datenverkehrs, und es wird verhindert, dass der lokale Computer, auf dem RDS gehostet wird, direkt über das Internet verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="8acda-157">The gateway uses Transport Layer Security (TLS) to encrypt traffic and prevents the on-premises computer hosting RDS from being directly exposed to the Internet.</span></span>

![Remotedesktopdienste-Verbindungen mit dem Remotedesktopdienste-Gateway](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-remote-desktop.png)

<span data-ttu-id="8acda-159">Weitere Informationen finden Sie in [diesem](https://www.microsoft.com/security/blog/2020/04/16/security-guidance-remote-desktop-adoption/) Artikel.</span><span class="sxs-lookup"><span data-stu-id="8acda-159">See [this article](https://www.microsoft.com/security/blog/2020/04/16/security-guidance-remote-desktop-adoption/) for more information.</span></span>

## <a name="admin-technical-resources-for-remote-access"></a><span data-ttu-id="8acda-160">Verwaltung technischer Ressourcen für den Remotezugriff</span><span class="sxs-lookup"><span data-stu-id="8acda-160">Admin technical resources for remote access</span></span>

- [<span data-ttu-id="8acda-161">Den Office 365-Datenverkehr für Remotemitarbeiter schnell optimieren & die Auslastung Ihrer Infrastruktur verringern</span><span class="sxs-lookup"><span data-stu-id="8acda-161">How to quickly optimize Office 365 traffic for remote staff & reduce the load on your infrastructure</span></span>](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571)
- [<span data-ttu-id="8acda-162">Optimieren der Office 365-Konnektivität für Remotebenutzer mithilfe eines geteilten VPN-Tunnels</span><span class="sxs-lookup"><span data-stu-id="8acda-162">Optimize Office 365 connectivity for remote users using VPN split tunneling</span></span>](../enterprise/microsoft-365-vpn-split-tunnel.md)

## <a name="results-of-step-2"></a><span data-ttu-id="8acda-163">Ergebnisse von Schritt 2</span><span class="sxs-lookup"><span data-stu-id="8acda-163">Results of Step 2</span></span>

<span data-ttu-id="8acda-164">Nach der Bereitstellung einer Remotezugriffslösung für Ihre Remotemitarbeiter:</span><span class="sxs-lookup"><span data-stu-id="8acda-164">After deployment of a remote access solution for your remote workers:</span></span>

| <span data-ttu-id="8acda-165">Konfiguration des Remotezugriffs</span><span class="sxs-lookup"><span data-stu-id="8acda-165">Remote access configuration</span></span> | <span data-ttu-id="8acda-166">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="8acda-166">Results</span></span> |
|:-------|:-----|
| <span data-ttu-id="8acda-167">Eine VPN-Lösung für den Remotezugriff ist eingerichtet</span><span class="sxs-lookup"><span data-stu-id="8acda-167">A remote access VPN solution is in place</span></span> | <span data-ttu-id="8acda-168">Sie haben den VPN-Client für den Remotezugriff für geteilten Tunnel und für die Kategorie „Optimieren“ von Microsoft 365-Endpunkten konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="8acda-168">You have configured your remote access VPN client for split tunneling and for the Optimize category of Microsoft 365 endpoints.</span></span> |
| <span data-ttu-id="8acda-169">Keine VPN-Lösung für den Remotezugriff und Sie benötigen Remotezugriff nur für lokale webbasierte Apps</span><span class="sxs-lookup"><span data-stu-id="8acda-169">No remote access VPN solution and you need remote access only to on-premises web-based apps</span></span> | <span data-ttu-id="8acda-170">Sie haben Azure-Anwendungsproxy konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="8acda-170">You have configured Azure Application Proxy.</span></span> |
| <span data-ttu-id="8acda-171">Keine VPN-Lösung für den Remotezugriff und Sie benötigen Zugriff auf lokale Apps, von denen einige nicht webbasiert sind</span><span class="sxs-lookup"><span data-stu-id="8acda-171">No remote access VPN solution and you need access to on-premises apps, some of which are not web-based</span></span> | <span data-ttu-id="8acda-172">Sie haben Azure P2S-VPN konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="8acda-172">You have configured Azure P2S VPN.</span></span> |
| <span data-ttu-id="8acda-173">Remotemitarbeiter verwenden Ihre privaten Geräte von zu Hause aus</span><span class="sxs-lookup"><span data-stu-id="8acda-173">Remote workers are using their personal devices from home</span></span> | <span data-ttu-id="8acda-174">Sie haben Windows Virtual Desktop konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="8acda-174">You have configured Windows Virtual Desktop.</span></span> |
| <span data-ttu-id="8acda-175">Remotemitarbeiter verwenden RDS-Verbindungen zu lokalen Systemen.</span><span class="sxs-lookup"><span data-stu-id="8acda-175">Remote workers are using RDS connections to on-premises systems</span></span> | <span data-ttu-id="8acda-176">Sie haben in Ihrem Microsoft Edge-Netzwerk ein Remotedesktopdienste-Gateway bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="8acda-176">You have deployed a Remote Desktop Services gateway in your edge network.</span></span> |
|||

## <a name="next-step"></a><span data-ttu-id="8acda-177">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="8acda-177">Next step</span></span>

<span data-ttu-id="8acda-178">[![Schritt 3: Bereitstellen von Sicherheits- und Compliancediensten von Microsoft 365](../media/empower-people-to-work-remotely/remote-workers-step-grid-3.png)](empower-people-to-work-remotely-security-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="8acda-178">[![Step 3: Deploy Microsoft 365 security and compliance services](../media/empower-people-to-work-remotely/remote-workers-step-grid-3.png)](empower-people-to-work-remotely-security-compliance.md)</span></span>

<span data-ttu-id="8acda-179">Fahren Sie mit [Schritt 3](empower-people-to-work-remotely-security-compliance.md) fort, um die Sicherheits- und Compliance-Dienste von Microsoft 365 zum Schutz Ihrer Apps, Daten und Geräte für Remotemitarbeiter bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="8acda-179">Continue with [Step 3](empower-people-to-work-remotely-security-compliance.md) to deploy Microsoft 365 security and compliance services to protect your apps, data, and devices.</span></span>