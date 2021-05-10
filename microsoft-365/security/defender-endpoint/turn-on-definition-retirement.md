---
title: Aktivieren der Definitionsentgrenzung für Microsoft Defender Antivirus
description: Aktivieren sie die Definitionsentgrenzung für Microsoft Defender Antivirus.
keywords: Microsoft Defender Antivirus, Antischalware, Sicherheit, Verteidiger, Definitionsentgrenzung
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
ms.openlocfilehash: 66b2e882a0f6de21e27dabb3a4bfe2fe113bcb32
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296482"
---
# <a name="turn-on-definition-retirement"></a><span data-ttu-id="8f140-104">Aktivieren der Definitionentgrenzung</span><span class="sxs-lookup"><span data-stu-id="8f140-104">Turn on definition retirement</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8f140-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="8f140-105">**Applies to:**</span></span>

- [<span data-ttu-id="8f140-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="8f140-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="8f140-107">Sie können die Definitionentgrenzung mithilfe von Gruppenrichtlinien konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8f140-107">You can configure definition retirement using Group Policy.</span></span> <span data-ttu-id="8f140-108">Definitionsentgrenzung überprüft, ob ein Computer über die erforderlichen Sicherheitsupdates verfügt, um ihn vor einer bestimmten Sicherheitslücke zu schützen.</span><span class="sxs-lookup"><span data-stu-id="8f140-108">Definition retirement checks to see if a computer has the required security updates necessary to protect it against a particular vulnerability.</span></span> <span data-ttu-id="8f140-109">Wenn das System nicht anfällig für den von einer Definition erkannten Exploit ist, ist diese Definition "eingestellt".</span><span class="sxs-lookup"><span data-stu-id="8f140-109">If the system is not vulnerable to the exploit detected by a definition, then that definition is "retired".</span></span> <span data-ttu-id="8f140-110">Wenn alle Sicherheitsintelligenz für ein bestimmtes Protokoll eingestellt wird, wird dieses Protokoll nicht mehr analysiert.</span><span class="sxs-lookup"><span data-stu-id="8f140-110">If all security intelligence for a given protocol are retired then that protocol is no longer parsed.</span></span> <span data-ttu-id="8f140-111">Wenn Sie dieses Feature aktivieren, können Sie die Leistung verbessern.</span><span class="sxs-lookup"><span data-stu-id="8f140-111">Enabling this feature helps to improve performance.</span></span> <span data-ttu-id="8f140-112">Auf einem Computer, der mit allen neuesten Sicherheitsupdates auf dem neuesten Stand ist, hat der Netzwerkschutz keine Auswirkungen auf die Netzwerkleistung.</span><span class="sxs-lookup"><span data-stu-id="8f140-112">On a computer that is up-to-date with all the latest security updates, network protection will have no impact on network performance.</span></span>

## <a name="use-group-policy-to-configure-definition-retirement"></a><span data-ttu-id="8f140-113">Konfigurieren der Definitionsentgrenzung mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="8f140-113">Use Group Policy to configure definition retirement</span></span>

1. <span data-ttu-id="8f140-114">Öffnen Sie auf dem Endpunkt für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="8f140-114">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="8f140-115">Wechseln Sie **zu Computerkonfiguration**  >  **Administrative Vorlagen** Windows  >  **Komponenten**  >  **Microsoft Defender Antivirus**  >  **Netzwerkinspektionssystem**.</span><span class="sxs-lookup"><span data-stu-id="8f140-115">Go to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="8f140-116">Wählen **Sie Definitionsentgrenzung aktivieren aus.**</span><span class="sxs-lookup"><span data-stu-id="8f140-116">Select **Turn on definition retirement**.</span></span> <span data-ttu-id="8f140-117">Diese Richtlinie ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8f140-117">By default, this policy is enabled.</span></span> <span data-ttu-id="8f140-118">Wenn **"Nicht konfiguriert" festgelegt ist,** ist die Definitionsentgrenzung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8f140-118">If set **Not configured**, definition retirement is enabled.</span></span> 

4. <span data-ttu-id="8f140-119">Wählen Sie zum Bearbeiten der Richtlinie den **Link Richtlinieneinstellung** bearbeiten aus.</span><span class="sxs-lookup"><span data-stu-id="8f140-119">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="8f140-120">Wählen **Sie Aktiviert** aus, und wählen Sie dann OK **aus.**</span><span class="sxs-lookup"><span data-stu-id="8f140-120">Select **Enabled**, and then select **OK**.</span></span>

6. <span data-ttu-id="8f140-121">Stellen Sie ihr aktualisiertes Gruppenrichtlinienobjekt zur Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="8f140-121">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="8f140-122">Weitere [Informationen finden Sie unter Gruppenrichtlinienverwaltungskonsole](/windows/win32/srvnodes/group-policy).</span><span class="sxs-lookup"><span data-stu-id="8f140-122">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="8f140-123">Verwenden Sie Gruppenrichtlinienobjekte lokal?</span><span class="sxs-lookup"><span data-stu-id="8f140-123">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="8f140-124">Sehen Sie, wie sie in der Cloud übersetzen.</span><span class="sxs-lookup"><span data-stu-id="8f140-124">See how they translate in the cloud.</span></span> <span data-ttu-id="8f140-125">[Analysieren Sie Ihre lokalen Gruppenrichtlinienobjekte mithilfe der Gruppenrichtlinienanalyse in Microsoft Endpoint Manager – Vorschau](/mem/intune/configuration/group-policy-analytics).</span><span class="sxs-lookup"><span data-stu-id="8f140-125">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="8f140-126">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="8f140-126">Related articles</span></span>

- [<span data-ttu-id="8f140-127">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="8f140-127">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
 
- [<span data-ttu-id="8f140-128">Aus der Cloud bereitgestellten Schutz aktivieren</span><span class="sxs-lookup"><span data-stu-id="8f140-128">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="8f140-129">Erstellen und Bereitstellen von Antischalwarerichtlinien: Cloudschutzdienst</span><span class="sxs-lookup"><span data-stu-id="8f140-129">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)