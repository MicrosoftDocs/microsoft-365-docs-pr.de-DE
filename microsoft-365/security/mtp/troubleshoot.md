---
title: Behandeln von Problemen mit dem Microsoft 365 Defender-Dienst
description: Suchen von Lösungen und Arbeiten mit bekannten Microsoft 365 Defender-Problemen
keywords: Problembehandlung bei Microsoft Threat Protection, Problembehandlung, Azure ATP, Probleme, Add-On, Einstellungsseite
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 414743fa5ba25b9d2714c1dd08dd38e34ec94372
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925718"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="b2222-104">Behandeln von Problemen mit dem Microsoft 365 Defender-Dienst</span><span class="sxs-lookup"><span data-stu-id="b2222-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b2222-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b2222-105">**Applies to:**</span></span>
- <span data-ttu-id="b2222-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b2222-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="b2222-107">In diesem Abschnitt werden Probleme behandelt, die auftreten können, wenn Sie den Microsoft 365 Defender-Dienst verwenden.</span><span class="sxs-lookup"><span data-stu-id="b2222-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="b2222-108">Microsoft 365 -Defender-Inhalte werden nicht angezeigt</span><span class="sxs-lookup"><span data-stu-id="b2222-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="b2222-109">Wenn im Navigationsbereich keine Funktionen wie Vorfälle, Das Aktionscenter oder die Suche in Ihrem Portal angezeigt werden, müssen Sie überprüfen, ob Ihr Mandant über die entsprechenden Lizenzen verfügt.</span><span class="sxs-lookup"><span data-stu-id="b2222-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="b2222-110">Weitere Informationen finden Sie unter [Voraussetzungen](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="b2222-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="b2222-111">Microsoft Defender for Identity-Warnungen werden in den Microsoft 365 Defender-Vorfällen nicht angezeigt</span><span class="sxs-lookup"><span data-stu-id="b2222-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="b2222-112">Wenn Sie Microsoft Defender for Identity in Ihrer Umgebung bereitgestellt haben, aber im Rahmen von Microsoft 365 Defender-Vorfällen keine Defender for Identity-Warnungen angezeigt werden, müssen Sie sicherstellen, dass die Integration von Microsoft Cloud App Security und Defender for Identity aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b2222-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="b2222-113">Weitere Informationen finden Sie unter [Microsoft Defender for Identity Integration](https://docs.microsoft.com/cloud-app-security/mdi-integration).</span><span class="sxs-lookup"><span data-stu-id="b2222-113">For more information, see [Microsoft Defender for Identity integration](https://docs.microsoft.com/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="b2222-114">Wo befindet sich die Einstellungsseite zum Aktivieren des Diensts?</span><span class="sxs-lookup"><span data-stu-id="b2222-114">Where is the settings page for turning the service on?</span></span>

<span data-ttu-id="b2222-115">Um Microsoft 365 Defender  zu aktivieren, greifen Sie über den Navigationsbereich im Microsoft 365 Security Center auf die Einstellungen zu.</span><span class="sxs-lookup"><span data-stu-id="b2222-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="b2222-116">Dieses Navigationselement ist nur sichtbar, wenn Sie über die erforderlichen [Berechtigungen und Lizenzen verfügen.](mtp-enable.md#check-license-eligibility-and-required-permissions)</span><span class="sxs-lookup"><span data-stu-id="b2222-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>
