---
title: Behandeln von Problemen mit Microsoft Threat Protection-Diensten
description: Suchen nach Lösungen und Umgehen bekannter Probleme mit Microsoft Threat Protection
keywords: Problembehandlung beim Microsoft-Bedrohungsschutz, Problembehandlung, Azure ATP, Probleme, Add-on, Seite "Einstellungen"
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: bbc7d5d434765b94b0b2707605be2edfbbc8e423
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2020
ms.locfileid: "41661981"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a><span data-ttu-id="d35c1-104">Behandeln von Problemen mit Microsoft Threat Protection-Diensten</span><span class="sxs-lookup"><span data-stu-id="d35c1-104">Troubleshoot Microsoft Threat Protection service issues</span></span>

<span data-ttu-id="d35c1-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="d35c1-105">**Applies to:**</span></span>
- <span data-ttu-id="d35c1-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d35c1-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="d35c1-107">Dieser Abschnitt bezieht sich auf Probleme, die bei Verwendung des Microsoft Threat Protection-Diensts auftreten können.</span><span class="sxs-lookup"><span data-stu-id="d35c1-107">This section addresses issues that might arise as you use the Microsoft Threat Protection service.</span></span>


## <a name="i-dont-see-microsoft-threat-protection-content"></a><span data-ttu-id="d35c1-108">Microsoft Threat Protection-Inhalt wird nicht angezeigt</span><span class="sxs-lookup"><span data-stu-id="d35c1-108">I don't see Microsoft Threat Protection content</span></span>
<span data-ttu-id="d35c1-109">Wenn im Navigationsbereich keine Funktionen wie die Vorfälle, das Wartungs Center oder die Suche in Ihrem Portal angezeigt werden, müssen Sie sicherstellen, dass Ihr Mandant über die entsprechenden Lizenzen verfügt.</span><span class="sxs-lookup"><span data-stu-id="d35c1-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span> 

<span data-ttu-id="d35c1-110">Weitere Informationen finden Sie unter [Voraussetzungen](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="d35c1-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a><span data-ttu-id="d35c1-111">Azure ATP-Warnungen werden in den Microsoft Threat Protection-Vorfällen nicht angezeigt</span><span class="sxs-lookup"><span data-stu-id="d35c1-111">Azure ATP alerts are not showing up in the Microsoft Threat Protection incidents</span></span>
<span data-ttu-id="d35c1-112">Wenn Sie Azure ATP in Ihrer Umgebung bereitgestellt haben, in Microsoft Threat Protection-Vorfällen aber keine Azure ATP-Warnungen angezeigt werden, müssen Sie sicherstellen, dass Microsoft Cloud App Security und Azure ATP-Integration aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="d35c1-112">If you have Azure ATP deployed in your environment but you're not seeing Azure ATP alerts as part of Microsoft Threat Protection incidents, you'll need to ensure that the Microsoft Cloud App Security and Azure ATP integration is enabled.</span></span> 

<span data-ttu-id="d35c1-113">Weitere Informationen finden Sie unter [Azure ATP-Integration](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span><span class="sxs-lookup"><span data-stu-id="d35c1-113">For more information, see [Azure ATP integration](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span></span>

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a><span data-ttu-id="d35c1-114">Ist Microsoft Threat Protection für US Government Community Cloud (GCC) oder GCC High verfügbar?</span><span class="sxs-lookup"><span data-stu-id="d35c1-114">Is Microsoft Threat Protection available for US Government Community Cloud (GCC) or GCC High?</span></span>
<span data-ttu-id="d35c1-115">Zurzeit ist Microsoft Threat Protection dafür nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d35c1-115">At the moment, it is not available.</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="d35c1-116">Wo befindet sich die Seite "Einstellungen" für die Aktivierung des Diensts?</span><span class="sxs-lookup"><span data-stu-id="d35c1-116">Where is the settings page for turning the service on?</span></span>
<span data-ttu-id="d35c1-117">Um Microsoft Threat Protection zu aktivieren, greifen Sie auf **Einstellungen** im Navigationsbereich im Microsoft 365 Security Center zu.</span><span class="sxs-lookup"><span data-stu-id="d35c1-117">To turn on Microsoft Threat Protection, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="d35c1-118">Dieses Navigationselement ist nur sichtbar, wenn Sie über die [erforderlichen Berechtigungen und Lizenzen](mtp-enable.md#check-license-eligibility-and-required-permissions)verfügen.</span><span class="sxs-lookup"><span data-stu-id="d35c1-118">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>

## <a name="can-i-use-an-add-on-instead-of-the-required-e5-licenses"></a><span data-ttu-id="d35c1-119">Kann ich anstelle der erforderlichen E5-Lizenzen ein Add-on verwenden?</span><span class="sxs-lookup"><span data-stu-id="d35c1-119">Can I use an add-on instead of the required E5 licenses?</span></span>
<span data-ttu-id="d35c1-120">Derzeit gibt es keine Add-ons für Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="d35c1-120">There are currently no add-ons for Microsoft Threat Protection.</span></span> [<span data-ttu-id="d35c1-121">Siehe Lizenzierungsanforderungen</span><span class="sxs-lookup"><span data-stu-id="d35c1-121">See licensing requirements</span></span>](prerequisites.md) 

