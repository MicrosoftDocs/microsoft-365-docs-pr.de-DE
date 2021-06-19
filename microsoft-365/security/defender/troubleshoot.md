---
title: Problembehandlung bei Microsoft 365 Defender Dienstproblemen
description: Suchen nach Lösungen und Problemumgehungen für bekannte Microsoft 365 Defender Probleme
keywords: Problembehandlung Microsoft 365 Defender, Problembehandlung, Microsoft Defender for Identity, Probleme, Add-On, Einstellungsseite
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
ms.openlocfilehash: 7891d61de7581a896a6599004eae91a4e47e1581
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029945"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="6915e-104">Problembehandlung bei Microsoft 365 Defender Dienstproblemen</span><span class="sxs-lookup"><span data-stu-id="6915e-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6915e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="6915e-105">**Applies to:**</span></span>
- <span data-ttu-id="6915e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6915e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6915e-107">In diesem Abschnitt werden Probleme behandelt, die bei der Verwendung des Microsoft 365 Defender Diensts auftreten können.</span><span class="sxs-lookup"><span data-stu-id="6915e-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="6915e-108">Ich sehe keine Microsoft 365 Defender Inhalte</span><span class="sxs-lookup"><span data-stu-id="6915e-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="6915e-109">Wenn im Navigationsbereich keine Funktionen wie Vorfälle, Info-Center oder Suche in Ihrem Portal angezeigt werden, müssen Sie überprüfen, ob Ihr Mandant über die entsprechenden Lizenzen verfügt.</span><span class="sxs-lookup"><span data-stu-id="6915e-109">If you don't see capabilities on the navigation pane such as the Incidents, Action center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="6915e-110">Weitere Informationen finden Sie unter [Voraussetzungen](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="6915e-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="6915e-111">Microsoft Defender for Identity-Warnungen werden in den Microsoft 365 Defender-Vorfällen nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6915e-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="6915e-112">Wenn Sie Microsoft Defender for Identity in Ihrer Umgebung bereitgestellt haben, ihnen aber im Rahmen Microsoft 365 Defender Vorfällen keine Defender for Identity-Warnungen angezeigt werden, müssen Sie sicherstellen, dass die integration von Microsoft Cloud App Security und Defender for Identity aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="6915e-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="6915e-113">Weitere Informationen finden Sie unter [Microsoft Defender for Identity-Integration.](/cloud-app-security/mdi-integration)</span><span class="sxs-lookup"><span data-stu-id="6915e-113">For more information, see [Microsoft Defender for Identity integration](/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a><span data-ttu-id="6915e-114">Wo befindet sich die Einstellungsseite zum Aktivieren des Diensts?</span><span class="sxs-lookup"><span data-stu-id="6915e-114">Where is the settings page for turning on the service?</span></span>

<span data-ttu-id="6915e-115">Um Microsoft 365 Defender zu aktivieren, greifen **Sie** über den Navigationsbereich im Microsoft 365 Security Center auf Einstellungen zu.</span><span class="sxs-lookup"><span data-stu-id="6915e-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="6915e-116">Dieses Navigationselement ist nur sichtbar, wenn Sie über die [erforderlichen Berechtigungen und Lizenzen verfügen.](m365d-enable.md#check-license-eligibility-and-required-permissions)</span><span class="sxs-lookup"><span data-stu-id="6915e-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](m365d-enable.md#check-license-eligibility-and-required-permissions).</span></span>

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a><span data-ttu-id="6915e-117">Wie erstelle ich eine Ausnahme für meine Datei/URL?</span><span class="sxs-lookup"><span data-stu-id="6915e-117">How do I create an exception for my file/URL?</span></span>

<span data-ttu-id="6915e-118">Ein falsch positives Ergebnis ist eine Datei oder URL, die als bösartig erkannt wird, aber keine Bedrohung darstellt.</span><span class="sxs-lookup"><span data-stu-id="6915e-118">A false positive is a file or URL that is detected as malicious but is not a threat.</span></span> <span data-ttu-id="6915e-119">Sie können Indikatoren erstellen und Ausschlüsse definieren, um bestimmte Dateien/URLs zu entsperren und zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="6915e-119">You can create indicators and define exclusions to unblock and allow certain files/URLs.</span></span> <span data-ttu-id="6915e-120">Siehe ["Adresse falsch positive/negative Ergebnisse" in Defender für Endpunkt.](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives)</span><span class="sxs-lookup"><span data-stu-id="6915e-120">See [Address false positives/negatives in Defender for Endpoint](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives).</span></span>
