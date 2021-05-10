---
title: Aktivieren der Protokollerkennung für Microsoft Defender Antivirus
description: Aktivieren Sie die Protokollerkennung für Microsoft Defender Antivirus.
keywords: Microsoft Defender Antivirus, Antischalware, Sicherheit, Defender, Protokollerkennung
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/07/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 890303a15618a0318db0421c9c80f270583e19bf
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296477"
---
# <a name="turn-on-protocol-recognition"></a><span data-ttu-id="673c4-104">Aktivieren der Protokollerkennung</span><span class="sxs-lookup"><span data-stu-id="673c4-104">Turn on protocol recognition</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="673c4-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="673c4-105">**Applies to:**</span></span>

- [<span data-ttu-id="673c4-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="673c4-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="673c4-107">Mit dieser Richtlinieneinstellung können Sie die Protokollerkennung für den Netzwerkschutz vor Exploits bekannter Sicherheitsrisiken konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="673c4-107">This policy setting allows you to configure protocol recognition for network protection against exploits of known vulnerabilities.</span></span> <span data-ttu-id="673c4-108">Wenn Sie diese Einstellung aktivieren oder nicht konfigurieren, wird die Protokollerkennung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="673c4-108">If you enable or do not configure this setting, protocol recognition will be enabled.</span></span> <span data-ttu-id="673c4-109">Wenn Sie diese Einstellung deaktivieren, wird die Protokollerkennung deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="673c4-109">If you disable this setting, protocol recognition will be disabled.</span></span>

## <a name="use-group-policy-to-configure-protocol-recognition"></a><span data-ttu-id="673c4-110">Konfigurieren der Protokollerkennung mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="673c4-110">Use Group Policy to configure protocol recognition</span></span>

1. <span data-ttu-id="673c4-111">Öffnen Sie auf dem Endpunkt für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="673c4-111">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="673c4-112">Wechseln Sie **zu Computerkonfiguration**  >  **Administrative Vorlagen** Windows  >  **Komponenten**  >  **Microsoft Defender Antivirus**  >  **Netzwerkinspektionssystem**.</span><span class="sxs-lookup"><span data-stu-id="673c4-112">Go to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="673c4-113">Wählen Sie **Protokollerkennung aus.**</span><span class="sxs-lookup"><span data-stu-id="673c4-113">Select **protocol recognition**.</span></span> <span data-ttu-id="673c4-114">Diese Richtlinie ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="673c4-114">By default, this policy is enabled.</span></span> <span data-ttu-id="673c4-115">Wenn **"Nicht konfiguriert" festgelegt ist,** ist die Definitionsentgrenzung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="673c4-115">If set **Not configured**, definition retirement is enabled.</span></span> 

4. <span data-ttu-id="673c4-116">Wählen Sie zum Bearbeiten der Richtlinie den **Link Richtlinieneinstellung** bearbeiten aus.</span><span class="sxs-lookup"><span data-stu-id="673c4-116">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="673c4-117">Wählen **Sie Aktiviert** aus, und wählen Sie dann OK **aus.**</span><span class="sxs-lookup"><span data-stu-id="673c4-117">Select **Enabled**, and then select **OK**.</span></span>

6. <span data-ttu-id="673c4-118">Stellen Sie ihr aktualisiertes Gruppenrichtlinienobjekt zur Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="673c4-118">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="673c4-119">Weitere [Informationen finden Sie unter Gruppenrichtlinienverwaltungskonsole](/windows/win32/srvnodes/group-policy).</span><span class="sxs-lookup"><span data-stu-id="673c4-119">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="673c4-120">Verwenden Sie Gruppenrichtlinienobjekte lokal?</span><span class="sxs-lookup"><span data-stu-id="673c4-120">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="673c4-121">Sehen Sie, wie sie in der Cloud übersetzen.</span><span class="sxs-lookup"><span data-stu-id="673c4-121">See how they translate in the cloud.</span></span> <span data-ttu-id="673c4-122">[Analysieren Sie Ihre lokalen Gruppenrichtlinienobjekte mithilfe der Gruppenrichtlinienanalyse in Microsoft Endpoint Manager – Vorschau](/mem/intune/configuration/group-policy-analytics).</span><span class="sxs-lookup"><span data-stu-id="673c4-122">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="673c4-123">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="673c4-123">Related articles</span></span>

- [<span data-ttu-id="673c4-124">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="673c4-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
 
- [<span data-ttu-id="673c4-125">Aus der Cloud bereitgestellten Schutz aktivieren</span><span class="sxs-lookup"><span data-stu-id="673c4-125">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="673c4-126">Erstellen und Bereitstellen von Antischalwarerichtlinien: Cloudschutzdienst</span><span class="sxs-lookup"><span data-stu-id="673c4-126">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)