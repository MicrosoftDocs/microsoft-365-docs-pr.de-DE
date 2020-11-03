---
title: Beheben von Problemen mit Microsoft 365 Defender-Diensten
description: Suchen von Lösungen und umgehen mit bekannten Problemen mit Microsoft 365 Defender
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
ms.openlocfilehash: 16cb1116f400c8d0a83ccc4cac23da06cd1be2a4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844668"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="b74e8-104">Beheben von Problemen mit Microsoft 365 Defender-Diensten</span><span class="sxs-lookup"><span data-stu-id="b74e8-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b74e8-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b74e8-105">**Applies to:**</span></span>
- <span data-ttu-id="b74e8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b74e8-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="b74e8-107">In diesem Abschnitt werden Probleme behandelt, die bei der Verwendung des Microsoft 365 Defender-Diensts auftreten können.</span><span class="sxs-lookup"><span data-stu-id="b74e8-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>


## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="b74e8-108">Microsoft 365 Defender-Inhalt wird nicht angezeigt</span><span class="sxs-lookup"><span data-stu-id="b74e8-108">I don't see Microsoft 365 Defender content</span></span>
<span data-ttu-id="b74e8-109">Wenn im Navigationsbereich keine Funktionen wie die Vorfälle, das Wartungs Center oder die Suche in Ihrem Portal angezeigt werden, müssen Sie sicherstellen, dass Ihr Mandant über die entsprechenden Lizenzen verfügt.</span><span class="sxs-lookup"><span data-stu-id="b74e8-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span> 

<span data-ttu-id="b74e8-110">Weitere Informationen finden Sie unter [Voraussetzungen](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="b74e8-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="b74e8-111">Microsoft Defender für Identitäts Warnungen wird nicht in den Microsoft 365 Defender-Vorfällen angezeigt</span><span class="sxs-lookup"><span data-stu-id="b74e8-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>
<span data-ttu-id="b74e8-112">Wenn Sie Microsoft Defender for Identity in Ihrer Umgebung bereitgestellt haben, aber Defender für Identitäts Warnungen als Teil von Microsoft 365 Defender-Vorfällen nicht angezeigt wird, müssen Sie sicherstellen, dass die Microsoft Cloud App Security and Defender for Identity Integration aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b74e8-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span> 

<span data-ttu-id="b74e8-113">Weitere Informationen finden Sie unter [Microsoft Defender for Identity Integration](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span><span class="sxs-lookup"><span data-stu-id="b74e8-113">For more information, see [Microsoft Defender for Identity integration](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="b74e8-114">Wo befindet sich die Seite "Einstellungen" für die Aktivierung des Diensts?</span><span class="sxs-lookup"><span data-stu-id="b74e8-114">Where is the settings page for turning the service on?</span></span>
<span data-ttu-id="b74e8-115">Um Microsoft 365 Defender zu aktivieren, greifen Sie auf **Einstellungen** im Navigationsbereich im Microsoft 365 Security Center zu.</span><span class="sxs-lookup"><span data-stu-id="b74e8-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="b74e8-116">Dieses Navigationselement ist nur sichtbar, wenn Sie über die [erforderlichen Berechtigungen und Lizenzen](mtp-enable.md#check-license-eligibility-and-required-permissions)verfügen.</span><span class="sxs-lookup"><span data-stu-id="b74e8-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>
 

