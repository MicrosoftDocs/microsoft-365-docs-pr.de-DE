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
ms.openlocfilehash: bcf5b79fcd2fdf0a5af5648e6f6b7ea65d69594c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201291"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a><span data-ttu-id="f02a5-104">Behandeln von Problemen mit Microsoft Threat Protection-Diensten</span><span class="sxs-lookup"><span data-stu-id="f02a5-104">Troubleshoot Microsoft Threat Protection service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f02a5-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f02a5-105">**Applies to:**</span></span>
- <span data-ttu-id="f02a5-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f02a5-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="f02a5-107">Dieser Abschnitt bezieht sich auf Probleme, die bei Verwendung des Microsoft Threat Protection-Diensts auftreten können.</span><span class="sxs-lookup"><span data-stu-id="f02a5-107">This section addresses issues that might arise as you use the Microsoft Threat Protection service.</span></span>


## <a name="i-dont-see-microsoft-threat-protection-content"></a><span data-ttu-id="f02a5-108">Microsoft Threat Protection-Inhalt wird nicht angezeigt</span><span class="sxs-lookup"><span data-stu-id="f02a5-108">I don't see Microsoft Threat Protection content</span></span>
<span data-ttu-id="f02a5-109">Wenn im Navigationsbereich keine Funktionen wie die Vorfälle, das Wartungs Center oder die Suche in Ihrem Portal angezeigt werden, müssen Sie sicherstellen, dass Ihr Mandant über die entsprechenden Lizenzen verfügt.</span><span class="sxs-lookup"><span data-stu-id="f02a5-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span> 

<span data-ttu-id="f02a5-110">Weitere Informationen finden Sie unter [Voraussetzungen](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="f02a5-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a><span data-ttu-id="f02a5-111">Azure ATP-Warnungen werden in den Microsoft Threat Protection-Vorfällen nicht angezeigt</span><span class="sxs-lookup"><span data-stu-id="f02a5-111">Azure ATP alerts are not showing up in the Microsoft Threat Protection incidents</span></span>
<span data-ttu-id="f02a5-112">Wenn Sie Azure ATP in Ihrer Umgebung bereitgestellt haben, in Microsoft Threat Protection-Vorfällen aber keine Azure ATP-Warnungen angezeigt werden, müssen Sie sicherstellen, dass Microsoft Cloud App Security und Azure ATP-Integration aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="f02a5-112">If you have Azure ATP deployed in your environment but you're not seeing Azure ATP alerts as part of Microsoft Threat Protection incidents, you'll need to ensure that the Microsoft Cloud App Security and Azure ATP integration is enabled.</span></span> 

<span data-ttu-id="f02a5-113">Weitere Informationen finden Sie unter [Azure ATP-Integration](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span><span class="sxs-lookup"><span data-stu-id="f02a5-113">For more information, see [Azure ATP integration](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="f02a5-114">Wo befindet sich die Seite "Einstellungen" für die Aktivierung des Diensts?</span><span class="sxs-lookup"><span data-stu-id="f02a5-114">Where is the settings page for turning the service on?</span></span>
<span data-ttu-id="f02a5-115">Um Microsoft Threat Protection zu aktivieren, greifen Sie auf **Einstellungen** im Navigationsbereich im Microsoft 365 Security Center zu.</span><span class="sxs-lookup"><span data-stu-id="f02a5-115">To turn on Microsoft Threat Protection, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="f02a5-116">Dieses Navigationselement ist nur sichtbar, wenn Sie über die [erforderlichen Berechtigungen und Lizenzen](mtp-enable.md#check-license-eligibility-and-required-permissions)verfügen.</span><span class="sxs-lookup"><span data-stu-id="f02a5-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>
 

