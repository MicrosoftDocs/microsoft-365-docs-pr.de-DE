---
title: Behandeln von Problemen mit dem Microsoft 365 Defender-Dienst
description: Suchen von Lösungen und Problemumgehungen für bekannte Microsoft 365 Defender-Probleme
keywords: Problembehandlung für Microsoft 365 Defender, Problembehandlung, Microsoft Defender for Identity, Probleme, Add-On, Einstellungsseite
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 0c933edfe80275dbfa60464ff862a7609b269332
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933397"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="5db29-104">Behandeln von Problemen mit dem Microsoft 365 Defender-Dienst</span><span class="sxs-lookup"><span data-stu-id="5db29-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="5db29-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="5db29-105">**Applies to:**</span></span>
- <span data-ttu-id="5db29-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5db29-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="5db29-107">In diesem Abschnitt werden Probleme behandelt, die bei der Verwendung des Microsoft 365 Defender-Diensts auftreten können.</span><span class="sxs-lookup"><span data-stu-id="5db29-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="5db29-108">Microsoft 365 Defender-Inhalte werden nicht angezeigt</span><span class="sxs-lookup"><span data-stu-id="5db29-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="5db29-109">Wenn im Navigationsbereich keine Funktionen wie Vorfälle, Aktionscenter oder Suche in Ihrem Portal angezeigt werden, müssen Sie überprüfen, ob Ihr Mandant über die entsprechenden Lizenzen verfügt.</span><span class="sxs-lookup"><span data-stu-id="5db29-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="5db29-110">Weitere Informationen finden Sie unter [Voraussetzungen](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="5db29-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="5db29-111">Microsoft Defender for Identity-Warnungen werden in den Microsoft 365 Defender-Vorfällen nicht angezeigt</span><span class="sxs-lookup"><span data-stu-id="5db29-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="5db29-112">Wenn Sie Microsoft Defender for Identity in Ihrer Umgebung bereitgestellt haben, aber im Rahmen von Microsoft 365 Defender-Vorfällen keine Defender for Identity-Warnungen angezeigt werden, müssen Sie sicherstellen, dass die Integration von Microsoft Cloud App Security und Defender for Identity aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="5db29-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="5db29-113">Weitere Informationen finden Sie unter [Microsoft Defender for Identity integration](/cloud-app-security/mdi-integration).</span><span class="sxs-lookup"><span data-stu-id="5db29-113">For more information, see [Microsoft Defender for Identity integration](/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a><span data-ttu-id="5db29-114">Wo befindet sich die Einstellungsseite zum Aktivieren des Diensts?</span><span class="sxs-lookup"><span data-stu-id="5db29-114">Where is the settings page for turning on the service?</span></span>

<span data-ttu-id="5db29-115">Um Microsoft 365 Defender  zu aktivieren, greifen Sie über den Navigationsbereich im Microsoft 365 Security Center auf Einstellungen zu.</span><span class="sxs-lookup"><span data-stu-id="5db29-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="5db29-116">Dieses Navigationselement ist nur sichtbar, wenn Sie über die erforderlichen [Berechtigungen und Lizenzen verfügen.](m365d-enable.md#check-license-eligibility-and-required-permissions)</span><span class="sxs-lookup"><span data-stu-id="5db29-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](m365d-enable.md#check-license-eligibility-and-required-permissions).</span></span>

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a><span data-ttu-id="5db29-117">Wie erstelle ich eine Ausnahme für meine Datei/URL?</span><span class="sxs-lookup"><span data-stu-id="5db29-117">How do I create an exception for my file/URL?</span></span>

<span data-ttu-id="5db29-118">Ein falsch positives Ergebnis ist eine Datei oder URL, die als schädlich erkannt wird, aber keine Bedrohung darstellt.</span><span class="sxs-lookup"><span data-stu-id="5db29-118">A false positive is a file or URL that is detected as malicious but is not a threat.</span></span> <span data-ttu-id="5db29-119">Sie können Indikatoren erstellen und Ausschlüsse definieren, um die Blockierung zu aufheben und bestimmte Dateien/URLs zu erlauben.</span><span class="sxs-lookup"><span data-stu-id="5db29-119">You can create indicators and define exclusions to unblock and allow certain files/URLs.</span></span> <span data-ttu-id="5db29-120">Weitere [Informationen finden Sie unter Address false positives/negatives in Defender for Endpoint](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives).</span><span class="sxs-lookup"><span data-stu-id="5db29-120">See [Address false positives/negatives in Defender for Endpoint](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives).</span></span>


