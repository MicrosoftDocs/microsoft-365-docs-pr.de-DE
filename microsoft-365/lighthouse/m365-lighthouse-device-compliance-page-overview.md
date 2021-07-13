---
title: Microsoft 365 Lighthouse Übersicht über die Gerätekompatibilitätsseite
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Informationen zu verwalteten Dienstanbietern (Managed Service Providers, MSPs), die Microsoft 365 Lighthouse verwenden, finden Sie auf der Seite "Gerätekompatibilität".
ms.openlocfilehash: 3568f5b362df86955a1ea6ce15928658c854a584
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395099"
---
# <a name="microsoft-365-lighthouse-device-compliance-page-overview"></a><span data-ttu-id="6cb10-103">Microsoft 365 Lighthouse Übersicht über die Gerätekompatibilitätsseite</span><span class="sxs-lookup"><span data-stu-id="6cb10-103">Microsoft 365 Lighthouse Device compliance page overview</span></span>

> [!NOTE]
> <span data-ttu-id="6cb10-104">Die in diesem Artikel beschriebenen Features befinden sich in der Vorschau, können geändert werden und sind nur für Partner verfügbar, die die [Anforderungen](m365-lighthouse-requirements.md)erfüllen.</span><span class="sxs-lookup"><span data-stu-id="6cb10-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="6cb10-105">Wenn Ihre Organisation nicht über Microsoft 365 Lighthouse verfügt, lesen Sie ["Registrieren für Microsoft 365 Lighthouse".](m365-lighthouse-sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="6cb10-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="6cb10-106">Microsoft 365 Lighthouse können Sie Einblicke und Informationen zur Intune-Gerätekompatibilität für alle Mandanten anzeigen, indem Sie im linken Navigationsbereich **"Geräte"** auswählen, um die Seite "Gerätekompatibilität" zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="6cb10-106">Microsoft 365 Lighthouse lets you view insights and information related to Intune device compliance for all your tenants by selecting **Devices** in the left navigation pane to open the Device compliance page.</span></span> <span data-ttu-id="6cb10-107">Auf dieser Seite können Sie einen Überblick über den Compliancestatus mandantenübergreifend erhalten, eine Liste der Geräte für jeden Mandanten anzeigen und Statusberichte zu Compliancerichtlinien und -einstellungen abrufen.</span><span class="sxs-lookup"><span data-stu-id="6cb10-107">From this page, you can get an overview of compliance status across tenants, view a list of devices for each tenant, and get status reports on compliance policies and settings.</span></span>

## <a name="overview-tab"></a><span data-ttu-id="6cb10-108">Registerkarte „Übersicht“</span><span class="sxs-lookup"><span data-stu-id="6cb10-108">Overview tab</span></span>  
  
<span data-ttu-id="6cb10-109">Auf der Registerkarte "Übersicht" können Sie den Gerätekompatibilitätsstatus für alle Mandanten anzeigen, monatliche Trends zur Gerätecompliance anzeigen und nachverfolgen, ob Geräten Compliancerichtlinien zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="6cb10-109">On the Overview tab, you can view device compliance status across your tenants, see monthly device compliance trends, and track whether devices have compliance policies assigned to them.</span></span> <span data-ttu-id="6cb10-110">Sie können auch Informationen zu Complianceaktionen und Anforderungen für Mandantengeräte basierend auf Richtlinien für bedingten Zugriff anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6cb10-110">You can also view information on tenant device compliance actions and requirements based on Conditional Access policies.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/device-overview-tab.png" alt-text="Screenshot der Registerkarte &quot;Übersicht&quot;.":::

## <a name="devices-tab"></a><span data-ttu-id="6cb10-112">Registerkarte "Geräte"</span><span class="sxs-lookup"><span data-stu-id="6cb10-112">Devices tab</span></span>

<span data-ttu-id="6cb10-113">Auf der Registerkarte "Geräte" können Sie eine Liste aller Mandantengeräte anzeigen und die Liste basierend auf den folgenden Konformitätsstatus filtern: Kompatibel, nicht konform, In Karenzzeit und nicht ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="6cb10-113">On the Devices tab, you can view a list of all tenant devices and filter the list based on the following compliance statuses: Compliant, Non-compliant, In Grace period, and Not evaluated.</span></span> <span data-ttu-id="6cb10-114">Weitere Informationen zu den verschiedenen Compliancestatus finden Sie unter Überwachen von [Intune-Gerätekompatibilitätsrichtlinien.](/mem/intune/protect/compliance-policy-monitor)</span><span class="sxs-lookup"><span data-stu-id="6cb10-114">For more information about the different compliance statuses, see [Monitor Intune Device compliance policies](/mem/intune/protect/compliance-policy-monitor).</span></span>

<span data-ttu-id="6cb10-115">Wählen Sie ein beliebiges Gerät aus, um weitere Informationen darüber anzuzeigen, warum sich das Gerät im aktuellen Kompatibilitätsstatus befindet.</span><span class="sxs-lookup"><span data-stu-id="6cb10-115">Select any device to view more information on why the device is in its current compliance state.</span></span> <span data-ttu-id="6cb10-116">Wenn Sie Maßnahmen auf dem Gerät ergreifen müssen, gibt es eine Option zum Anzeigen des Geräts in Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="6cb10-116">If you need to take action on the device, there's an option to view the device in Microsoft Endpoint Manager.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/devices-device-tab.png" alt-text="Screenshot der Registerkarte &quot;Geräte&quot;.":::

## <a name="policies-tab"></a><span data-ttu-id="6cb10-118">Registerkarte "Richtlinien"</span><span class="sxs-lookup"><span data-stu-id="6cb10-118">Policies tab</span></span>

<span data-ttu-id="6cb10-119">Auf der Registerkarte "Richtlinien" können Sie Compliancerichtlinien mandantenübergreifend anzeigen und zwei oder drei Richtlinien desselben Plattformtyps mithilfe der Vergleichsfunktion auf der Symbolleiste vergleichen.</span><span class="sxs-lookup"><span data-stu-id="6cb10-119">On the Policies tab, you can view compliance policies across your tenants and compare two or three policies of the same platform type by using the Compare feature on the toolbar.</span></span> <span data-ttu-id="6cb10-120">Sie können auch eine beliebige Richtlinie auswählen, um weitere Informationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6cb10-120">You can also select any policy to view more information.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/devices-policies-tab.png" alt-text="Screenshot der Registerkarte &quot;Richtlinien&quot;.":::

## <a name="settings-tab"></a><span data-ttu-id="6cb10-122">Registerkarte "Einstellungen"</span><span class="sxs-lookup"><span data-stu-id="6cb10-122">Settings tab</span></span>

<span data-ttu-id="6cb10-123">Die Registerkarte "Einstellungen" enthält einen aggregierten Bericht über nicht konforme Einstellungen auf mandantenübergreifenden Geräten.</span><span class="sxs-lookup"><span data-stu-id="6cb10-123">The settings tab provides an aggregated report of non-compliant settings across tenant devices.</span></span> <span data-ttu-id="6cb10-124">Wählen Sie eine der Berichtszeilen aus, um weitere Informationen anzuzeigen, einschließlich der Mandanten, zu denen die nicht kompatiblen Geräte gehören.</span><span class="sxs-lookup"><span data-stu-id="6cb10-124">Select any of the report rows to view more information, including which tenants the non-compliant devices belong to.</span></span>

:::image type="content" source="../media/m365-lighthouse-device-compliance-page-overview/device-settings-tab.png" alt-text="Screenshot der Registerkarte Einstellungen.":::

## <a name="related-content"></a><span data-ttu-id="6cb10-126">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="6cb10-126">Related content</span></span>

<span data-ttu-id="6cb10-127">[Übersicht über die Seite "Microsoft 365 Lighthouse Benutzer"](m365-lighthouse-users-page-overview.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="6cb10-127">[Microsoft 365 Lighthouse Users page overview](m365-lighthouse-users-page-overview.md) (article)</span></span>\
<span data-ttu-id="6cb10-128">[faq zu Microsoft 365 Lighthouse](m365-lighthouse-faq.yml) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="6cb10-128">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>
