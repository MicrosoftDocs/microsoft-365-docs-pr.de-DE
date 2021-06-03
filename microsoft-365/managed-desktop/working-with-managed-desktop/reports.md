---
title: Mit Berichten arbeiten
description: Die verschiedenen Berichte, die in Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 28035a9f0a669c1daa7526d0b1fefac52a77c81a
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52729968"
---
# <a name="work-with-reports"></a><span data-ttu-id="6f63f-104">Mit Berichten arbeiten</span><span class="sxs-lookup"><span data-stu-id="6f63f-104">Work with reports</span></span>

<span data-ttu-id="6f63f-105">Microsoft Managed Desktop bietet mehrere Berichte und Dashboards, die IT-Administratoren in Ihrer Organisation verwenden können, um verschiedene Aspekte der Gerätegesamtheit zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="6f63f-105">Microsoft Managed Desktop provides several reports and dashboards that IT admins in your organization can use to understand various aspects of the population of devices.</span></span><span data-ttu-id="6f63f-106">Berichte finden Sie an zwei Speicherorten: in [Microsoft Endpoint Manager](https://endpoint.microsoft.com) und im [Microsoft 365 Admin Center](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop).</span><span class="sxs-lookup"><span data-stu-id="6f63f-106"> You'll find reports in two locations: in [Microsoft Endpoint Manager](https://endpoint.microsoft.com) and in the [Microsoft 365 Admin Center](https://admin.microsoft.com/adminportal/home?previewoff=false#/microsoftmanageddesktop).</span></span> 

## <a name="reports-in-microsoft-endpoint-manager"></a><span data-ttu-id="6f63f-107">Berichte in Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="6f63f-107">Reports in Microsoft Endpoint Manager</span></span>

<span data-ttu-id="6f63f-108">Die Microsoft Endpoint Manager führt Berichte aus mehreren Produkten an einem einzigen Ort zusammen, um Probleme mit ihrer Azure AD-Organisation ("Mandant")-Konfiguration und -Geräten zu überwachen und zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="6f63f-108">The Microsoft Endpoint Manager console brings together reporting from several products into a single location to help you monitor and investigate issues with your Azure AD organization ("tenant") configuration and devices.</span></span> <span data-ttu-id="6f63f-109">Microsoft Managed desktop has a section under **Reports** in the main menu where you can find reports specific to Microsoft Managed Desktop's management of the devices you've registered.</span><span class="sxs-lookup"><span data-stu-id="6f63f-109">Microsoft Managed desktop has a section under **Reports** in the main menu where you can find reports specific to Microsoft Managed Desktop's management of the devices you’ve registered.</span></span>

<span data-ttu-id="6f63f-110">Zu diesen Berichten gehören:</span><span class="sxs-lookup"><span data-stu-id="6f63f-110">These reports include:</span></span>
- <span data-ttu-id="6f63f-111">**Verwaltete Geräte**  >  **Featureupdates:** Diese Ansicht zeigt den Gesamtstatus von Featureupdates auf Ihren Microsoft Managed Desktop an.</span><span class="sxs-lookup"><span data-stu-id="6f63f-111">**Managed devices** > **Feature updates**: This view shows the overall status of feature updates across your Microsoft Managed Desktop devices.</span></span>
- <span data-ttu-id="6f63f-112">**Verwaltete Geräte**  >  **Office Updates:** Diese Ansicht zeigt den Gesamtstatus der Office Updates auf Ihren Microsoft Managed Desktop an.</span><span class="sxs-lookup"><span data-stu-id="6f63f-112">**Managed devices** > **Office updates**: This view shows the overall status of Office updates across your Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="6f63f-113">Darüber hinaus können Sie berichte Microsoft Endpoint Manager anderen Produktgruppen filtern, um Ihre Geräte, die von anderen Produktgruppen verwaltet werden, explizit ein- oder auszuschließen, Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="6f63f-113">Additionally, in several locations throughout Microsoft Endpoint Manager you can filter reports from other product groups to specifically include or exclude your devices that are managed by Microsoft Managed Desktop.</span></span> <span data-ttu-id="6f63f-114">Diese Berichte haben diese Filterfunktion integriert:</span><span class="sxs-lookup"><span data-stu-id="6f63f-114">These reports have integrated this filtering capability:</span></span>

- [<span data-ttu-id="6f63f-115">Alle Geräte</span><span class="sxs-lookup"><span data-stu-id="6f63f-115">All devices</span></span>](/mem/intune/remote-actions/device-management#get-to-your-devices)
- [<span data-ttu-id="6f63f-116">Gerätekompatibilität</span><span class="sxs-lookup"><span data-stu-id="6f63f-116">Device compliance</span></span>](/mem/intune/fundamentals/reports#device-compliance-report-organizational)
- [<span data-ttu-id="6f63f-117">Nicht kompatible Geräte</span><span class="sxs-lookup"><span data-stu-id="6f63f-117">Noncompliant devices</span></span>](/mem/intune/fundamentals/reports#noncompliant-devices-report-operational)

> [!NOTE]
> <span data-ttu-id="6f63f-118">Benutzerdefinierte Microsoft Managed Desktop garantieren nur zugriff auf die Microsoft Managed Desktop Berichte.</span><span class="sxs-lookup"><span data-stu-id="6f63f-118">Custom Microsoft Managed Desktop roles guarantee access only to the Microsoft Managed Desktop reports.</span></span> <span data-ttu-id="6f63f-119">Informationen zum Zugriff auf andere Microsoft Endpoint Manager, z. B. **Alle** Geräte, finden Sie unter [Rollenbasierte](/mem/intune/fundamentals/role-based-access-control)Zugriffssteuerung mit Microsoft Intune .</span><span class="sxs-lookup"><span data-stu-id="6f63f-119">To access other parts of Microsoft Endpoint Manager, such as **All devices**, see [Role-based access control with Microsoft Intune](/mem/intune/fundamentals/role-based-access-control).</span></span> 


 ## <a name="inventory-data"></a><span data-ttu-id="6f63f-120">Bestandsdaten</span><span class="sxs-lookup"><span data-stu-id="6f63f-120">Inventory data</span></span>

<span data-ttu-id="6f63f-121">Zusätzlich zu den anderen Berichten können Sie Informationen zu den geräten exportieren, die von Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="6f63f-121">In addition to the other reports, you can export information about the devices managed by Microsoft Managed Desktop.</span></span> <span data-ttu-id="6f63f-122">Verwenden Sie **in** der Geräteansicht **des** Bereichs Geräte von Microsoft Endpoint Manager die Registerkarte **Alle** exportieren, um [einen detaillierten Inventarbericht herunterzuladen.](device-inventory-report.md)</span><span class="sxs-lookup"><span data-stu-id="6f63f-122">In the **Devices** view of the **Devices** area of Microsoft Endpoint Manager, use the **Export all** tab to [download a detailed inventory report](device-inventory-report.md).</span></span>