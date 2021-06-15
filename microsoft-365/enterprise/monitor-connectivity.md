---
title: Überwachen der Microsoft 365-Konnektivität
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/4/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 53cdb60c-a6b2-4848-b3ff-e7b75dc3fd1f
description: In diesem Artikel erfahren Sie mehr über die Tools und Techniken, die Sie verwenden können, um Microsoft 365 Konnektivität zu überwachen und aufrechtzuerhalten.
ms.openlocfilehash: 8fa0820cf9b7778001be5184041e5c96930a29dd
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924199"
---
# <a name="monitor-microsoft-365-connectivity"></a><span data-ttu-id="05cc4-103">Überwachen der Microsoft 365-Konnektivität</span><span class="sxs-lookup"><span data-stu-id="05cc4-103">Monitor Microsoft 365 connectivity</span></span>

<span data-ttu-id="05cc4-104">Nachdem Sie Microsoft 365 bereitgestellt haben, können Sie Microsoft 365 Konnektivität mithilfe einiger der unten aufgeführten Tools und Techniken aufrechterhalten.</span><span class="sxs-lookup"><span data-stu-id="05cc4-104">Once you've deployed Microsoft 365, you can maintain Microsoft 365 connectivity using some of the tools and techniques below.</span></span> <span data-ttu-id="05cc4-105">Sie sollten die offiziellen Richtlinien für [Dienstintegrität und -kontinuität](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) sowie unsere [bewährten Methoden für die Verwendung von Microsoft 365 in einem langsamen Netzwerk](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)verstehen.</span><span class="sxs-lookup"><span data-stu-id="05cc4-105">You'll want to understand the official [Service Health and Continuity](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) guidelines as well as our [Best practices for using Microsoft 365 on a slow network](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166).</span></span> <span data-ttu-id="05cc4-106">Sie sollten auch die [Microsoft 365 Administrator-App](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) abrufen und unser Microsoft 365 für Unternehmen mit einem Lesezeichen versehen [– Administratorhilfe.](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791)</span><span class="sxs-lookup"><span data-stu-id="05cc4-106">You'll also want to grab the [Microsoft 365 admin app](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) and bookmark our [Microsoft 365 for business - Admin Help](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791).</span></span>
  
## <a name="monitoring-microsoft-365-connectivity"></a><span data-ttu-id="05cc4-107">Überwachen Microsoft 365 Konnektivität</span><span class="sxs-lookup"><span data-stu-id="05cc4-107">Monitoring Microsoft 365 Connectivity</span></span>

|<span data-ttu-id="05cc4-108">Art der Überwachung</span><span class="sxs-lookup"><span data-stu-id="05cc4-108">Type of monitoring</span></span> |<span data-ttu-id="05cc4-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="05cc4-109">Description</span></span> |
|:-----|:-----|
|<span data-ttu-id="05cc4-110">**Benachrichtigung über neue Microsoft 365 Endpunkte**</span><span class="sxs-lookup"><span data-stu-id="05cc4-110">**Getting notified of new Microsoft 365 endpoints**</span></span> <br/> |<span data-ttu-id="05cc4-111">Wenn Sie [Microsoft 365 Endpunkte verwalten,](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)sollten Sie Benachrichtigungen erhalten, wenn wir neue Endpunkte veröffentlichen. Sie können unseren RSS-Feed mit Ihrem bevorzugten RSS-Reader abonnieren.</span><span class="sxs-lookup"><span data-stu-id="05cc4-111">If you're [Managing Microsoft 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), you'll want to receive notifications when we publish new endpoints, you can subscribe to our RSS feed using your favorite RSS reader.</span></span> <span data-ttu-id="05cc4-112">Hier erfahren Sie, wie Sie [über Outlook abonnieren,](https://go.microsoft.com/fwlink/p/?LinkId=532416) oder Sie können [die RSS-Feedupdates per E-Mail an Sie senden](https://go.microsoft.com/fwlink/p/?LinkId=532417)lassen.</span><span class="sxs-lookup"><span data-stu-id="05cc4-112">Here is how to [subscribe via Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) or you can [have the RSS feed updates emailed to you](https://go.microsoft.com/fwlink/p/?LinkId=532417).</span></span>  <br/> |
|<span data-ttu-id="05cc4-113">**Verwenden von System Center zum Überwachen von Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="05cc4-113">**Use System Center to Monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="05cc4-114">Wenn Sie Microsoft System Center verwenden, können Sie das [System Center Management Pack für Office 365](https://www.microsoft.com/download/details.aspx?id=43708) herunterladen, um noch heute mit der Überwachung Microsoft 365 zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="05cc4-114">If you're using Microsoft System Center, you can download the [System Center Management Pack for Office 365](https://www.microsoft.com/download/details.aspx?id=43708) to begin monitoring Microsoft 365 today.</span></span> <span data-ttu-id="05cc4-115">Ausführlichere Anleitungen finden Sie im Management Pack-Betriebshandbuch.</span><span class="sxs-lookup"><span data-stu-id="05cc4-115">For more detailed guidance, please see the management pack operations guide.</span></span> <br/> |
|<span data-ttu-id="05cc4-116">**Überwachen des Zustands von Azure ExpressRoute**</span><span class="sxs-lookup"><span data-stu-id="05cc4-116">**Monitoring the health of Azure ExpressRoute**</span></span> <br/> |<span data-ttu-id="05cc4-117">Wenn Sie mit Azure ExpressRoute für Microsoft 365 eine Verbindung mit Microsoft 365 herstellen, sollten Sie sicherstellen, dass Sie sowohl das Microsoft 365 Service Health Dashboard als auch die Azure [Reducing-Problembehandlungszeit mit Azure Resource Health](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/) verwenden.</span><span class="sxs-lookup"><span data-stu-id="05cc4-117">If you are connecting to Microsoft 365 using Azure ExpressRoute for Microsoft 365, you'll want to ensure that you're using both the Microsoft 365 Service Health Dashboard as well as the Azure [Reducing troubleshooting time with Azure Resource health](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)</span></span> <br/> |
|<span data-ttu-id="05cc4-118">**Verwenden von Azure AD Connect Health mit AD FS**</span><span class="sxs-lookup"><span data-stu-id="05cc4-118">**Using Azure AD Connect Health with AD FS**</span></span> <br/> |<span data-ttu-id="05cc4-119">Wenn Sie AD FS für einzelne Sign-On mit Microsoft 365 verwenden, sollten Sie azure [AD Verbinden Health verwenden, um Ihre AD FS-Infrastruktur zu überwachen.](/azure/active-directory/hybrid/how-to-connect-health-adfs)</span><span class="sxs-lookup"><span data-stu-id="05cc4-119">If you're using AD FS for Single Sign-On with Microsoft 365, you'll want to begin [using Azure AD Connect Health to monitor your AD FS infrastructure](/azure/active-directory/hybrid/how-to-connect-health-adfs).</span></span>  <br/> |
|<span data-ttu-id="05cc4-120">**Programmgesteuerte Überwachung Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="05cc4-120">**Programmatically monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="05cc4-121">Lesen Sie unsere Anleitung zur [Microsoft 365-Verwaltungs-API.](/office/office-365-management-api/office-365-management-apis-overview)</span><span class="sxs-lookup"><span data-stu-id="05cc4-121">Refer to our guidance on the [Microsoft 365 Management API](/office/office-365-management-api/office-365-management-apis-overview).</span></span>  <br/> |

<span data-ttu-id="05cc4-122">Mit diesem kurzen Link gelangen Sie wieder hierher zurück: [https://aka.ms/monitorconnectivity365]()</span><span class="sxs-lookup"><span data-stu-id="05cc4-122">Here's a short link you can use to come back: [https://aka.ms/monitorconnectivity365]()</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="05cc4-123">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="05cc4-123">Related topics</span></span>

[<span data-ttu-id="05cc4-124">Konfigurieren Microsoft 365 Enterprise Dienste und Anwendungen</span><span class="sxs-lookup"><span data-stu-id="05cc4-124">Configure Microsoft 365 Enterprise services and applications</span></span>](configure-services-and-applications.md)
  
[<span data-ttu-id="05cc4-125">Vorbereiten Ihrer Organisation auf Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="05cc4-125">Get your organization ready for Microsoft 365 Enterprise</span></span>](get-your-organization-ready-for-office-365.md)
  
[<span data-ttu-id="05cc4-126">Netzwerkplanung und Leistungsoptimierung für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="05cc4-126">Network planning and performance tuning for Microsoft 365</span></span>](network-planning-and-performance.md)
  
[<span data-ttu-id="05cc4-127">Microsoft 365 Integration in lokale Umgebungen</span><span class="sxs-lookup"><span data-stu-id="05cc4-127">Microsoft 365 integration with on-premises environments</span></span>](microsoft-365-integration.md)
  
[<span data-ttu-id="05cc4-128">Verwalten Microsoft 365 Endpunkte</span><span class="sxs-lookup"><span data-stu-id="05cc4-128">Managing Microsoft 365 endpoints</span></span>](managing-office-365-endpoints.md)
