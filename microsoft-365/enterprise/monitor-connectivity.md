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
description: In diesem Artikel erfahren Sie mehr über die Tools und Techniken, die Sie zum Überwachen und Warten der Microsoft 365-Konnektivität verwenden können.
ms.openlocfilehash: db3811b70f91efb9fd1e9f023df12d0852ce0189
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920776"
---
# <a name="monitor-microsoft-365-connectivity"></a><span data-ttu-id="7e977-103">Überwachen der Microsoft 365-Konnektivität</span><span class="sxs-lookup"><span data-stu-id="7e977-103">Monitor Microsoft 365 connectivity</span></span>

<span data-ttu-id="7e977-104">Nachdem Sie Microsoft 365 bereitgestellt haben, können Sie die Microsoft 365-Konnektivität mithilfe einiger der unten aufgeführten Tools und Techniken verwalten.</span><span class="sxs-lookup"><span data-stu-id="7e977-104">Once you've deployed Microsoft 365, you can maintain Microsoft 365 connectivity using some of the tools and techniques below.</span></span> <span data-ttu-id="7e977-105">Sie möchten die offiziellen Richtlinien für [Dienstintegheit](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) und Kontinuität sowie unsere bewährten Methoden für die Verwendung von [Microsoft 365 in](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)einem langsamen Netzwerk verstehen.</span><span class="sxs-lookup"><span data-stu-id="7e977-105">You'll want to understand the official [Service Health and Continuity](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) guidelines as well as our [Best practices for using Microsoft 365 on a slow network](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166).</span></span> <span data-ttu-id="7e977-106">Sie möchten auch die [Microsoft 365-Administrator-App](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) nutzen und unsere [Microsoft 365 For Business - Administratorhilfe](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791)als Lesezeichen markieren.</span><span class="sxs-lookup"><span data-stu-id="7e977-106">You'll also want to grab the [Microsoft 365 admin app](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) and bookmark our [Microsoft 365 for business - Admin Help](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791).</span></span>
  
## <a name="monitoring-microsoft-365-connectivity"></a><span data-ttu-id="7e977-107">Überwachen der Microsoft 365-Konnektivität</span><span class="sxs-lookup"><span data-stu-id="7e977-107">Monitoring Microsoft 365 Connectivity</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="7e977-108">**Benachrichtigung über neue Microsoft 365-Endpunkte**</span><span class="sxs-lookup"><span data-stu-id="7e977-108">**Getting notified of new Microsoft 365 endpoints**</span></span> <br/> |<span data-ttu-id="7e977-109">Wenn Sie [Microsoft 365-Endpunkte](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)verwalten, möchten Sie Benachrichtigungen erhalten, wenn wir neue Endpunkte veröffentlichen, können Sie unseren RSS-Feed mit Ihrem bevorzugten RSS-Reader abonnieren.</span><span class="sxs-lookup"><span data-stu-id="7e977-109">If you're [Managing Microsoft 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), you'll want to receive notifications when we publish new endpoints, you can subscribe to our RSS feed using your favorite RSS reader.</span></span> <span data-ttu-id="7e977-110">Hier erfahren Sie, wie [Sie über Outlook abonnieren,](https://go.microsoft.com/fwlink/p/?LinkId=532416) oder Sie können die [RSS-Feedupdates per E-Mail an Sie senden lassen.](https://go.microsoft.com/fwlink/p/?LinkId=532417)</span><span class="sxs-lookup"><span data-stu-id="7e977-110">Here is how to [subscribe via Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) or you can [have the RSS feed updates emailed to you](https://go.microsoft.com/fwlink/p/?LinkId=532417).</span></span>  <br/> |
|<span data-ttu-id="7e977-111">**Überwachen von Microsoft 365 mithilfe von System Center**</span><span class="sxs-lookup"><span data-stu-id="7e977-111">**Use System Center to Monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="7e977-112">Wenn Sie Microsoft System Center verwenden, können Sie das [System Center Management Pack für Office 365](https://www.microsoft.com/download/details.aspx?id=43708) herunterladen, um mit der Überwachung von Microsoft 365 zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="7e977-112">If you're using Microsoft System Center, you can download the [System Center Management Pack for Office 365](https://www.microsoft.com/download/details.aspx?id=43708) to begin monitoring Microsoft 365 today.</span></span> <span data-ttu-id="7e977-113">Ausführlichere Anleitungen finden Sie im Management Pack Operations Guide oder in diesem Blogbeitrag [Office365 Monitoring using System Center Operations Manager](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx)</span><span class="sxs-lookup"><span data-stu-id="7e977-113">For more detailed guidance, please see the management pack operations guide or this blog post [Office365 Monitoring using System Centre Operations Manager](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx)</span></span> <br/> |
|<span data-ttu-id="7e977-114">**Überwachen des Zustands von Azure ExpressRoute**</span><span class="sxs-lookup"><span data-stu-id="7e977-114">**Monitoring the health of Azure ExpressRoute**</span></span> <br/> |<span data-ttu-id="7e977-115">Wenn Sie eine Verbindung mit Microsoft 365 mithilfe von Azure ExpressRoute für Microsoft 365 herstellen, sollten Sie sicherstellen, dass Sie sowohl das Microsoft 365 Service Health Dashboard als auch das Azure [Reducing troubleshooting time with Azure Resource health](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/) verwenden.</span><span class="sxs-lookup"><span data-stu-id="7e977-115">If you are connecting to Microsoft 365 using Azure ExpressRoute for Microsoft 365, you'll want to ensure that you're using both the Microsoft 365 Service Health Dashboard as well as the Azure [Reducing troubleshooting time with Azure Resource health](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)</span></span> <br/> |
|<span data-ttu-id="7e977-116">**Verwenden von Azure AD Connect Health mit AD FS**</span><span class="sxs-lookup"><span data-stu-id="7e977-116">**Using Azure AD Connect Health with AD FS**</span></span> <br/> |<span data-ttu-id="7e977-117">Wenn Sie AD FS für single Sign-On mit Microsoft 365 verwenden, sollten Sie mit der Verwendung von Azure AD Connect Health beginnen, um Ihre [AD FS-Infrastruktur zu überwachen.](/azure/active-directory/hybrid/how-to-connect-health-adfs)</span><span class="sxs-lookup"><span data-stu-id="7e977-117">If you're using AD FS for Single Sign-On with Microsoft 365, you'll want to begin [using Azure AD Connect Health to monitor your AD FS infrastructure](/azure/active-directory/hybrid/how-to-connect-health-adfs).</span></span>  <br/> |
|<span data-ttu-id="7e977-118">**Programmgesteuerte Überwachung von Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="7e977-118">**Programmatically monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="7e977-119">Lesen Sie unsere Anleitungen zur [Microsoft 365-Verwaltungs-API](/office/office-365-management-api/office-365-management-apis-overview).</span><span class="sxs-lookup"><span data-stu-id="7e977-119">Refer to our guidance on the [Microsoft 365 Management API](/office/office-365-management-api/office-365-management-apis-overview).</span></span>  <br/> |

<span data-ttu-id="7e977-120">Mit diesem kurzen Link gelangen Sie wieder hierher zurück: [https://aka.ms/monitorconnectivity365]()</span><span class="sxs-lookup"><span data-stu-id="7e977-120">Here's a short link you can use to come back: [https://aka.ms/monitorconnectivity365]()</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="7e977-121">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="7e977-121">Related topics</span></span>

[<span data-ttu-id="7e977-122">Konfigurieren von Microsoft 365 Enterprise-Diensten und -Anwendungen</span><span class="sxs-lookup"><span data-stu-id="7e977-122">Configure Microsoft 365 Enterprise services and applications</span></span>](configure-services-and-applications.md)
  
[<span data-ttu-id="7e977-123">Bereiten Sie Ihre Organisation für Microsoft 365 Enterprise vor</span><span class="sxs-lookup"><span data-stu-id="7e977-123">Get your organization ready for Microsoft 365 Enterprise</span></span>](get-your-organization-ready-for-office-365.md)
  
[<span data-ttu-id="7e977-124">Netzwerkplanung und Leistungsoptimierung für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7e977-124">Network planning and performance tuning for Microsoft 365</span></span>](network-planning-and-performance.md)
  
[<span data-ttu-id="7e977-125">Microsoft 365-Integration in lokale Umgebungen</span><span class="sxs-lookup"><span data-stu-id="7e977-125">Microsoft 365 integration with on-premises environments</span></span>](microsoft-365-integration.md)
  
[<span data-ttu-id="7e977-126">Verwalten von Microsoft 365-Endpunkten</span><span class="sxs-lookup"><span data-stu-id="7e977-126">Managing Microsoft 365 endpoints</span></span>](managing-office-365-endpoints.md)