---
title: Deaktivieren der Definition für Microsoft Defender Antivirus
description: Aktivieren Sie die Einstellung der Definition für Microsoft Defender Antivirus.
keywords: Microsoft Defender Antivirus, Antischadsoftware, Sicherheit, Defender, Einstellung der Definition
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 505270d319a78de20bf6fed01b7ca79c9fc2b400
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903804"
---
# <a name="turn-on-definition-retirement"></a><span data-ttu-id="a0002-104">Deaktivieren der Definition</span><span class="sxs-lookup"><span data-stu-id="a0002-104">Turn on definition retirement</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a0002-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="a0002-105">**Applies to:**</span></span>

- [<span data-ttu-id="a0002-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="a0002-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="a0002-107">Sie können die Einstellung der Definition mithilfe von Gruppenrichtlinien konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a0002-107">You can configure definition retirement using Group Policy.</span></span> <span data-ttu-id="a0002-108">Die Einstellung der Definition überprüft, ob ein Computer über die erforderlichen Sicherheitsupdates verfügt, um ihn vor einer bestimmten Sicherheitslücke zu schützen.</span><span class="sxs-lookup"><span data-stu-id="a0002-108">Definition retirement checks to see if a computer has the required security updates necessary to protect it against a particular vulnerability.</span></span> <span data-ttu-id="a0002-109">Wenn das System nicht anfällig für den durch eine Definition erkannten Exploit ist, wird diese Definition "eingestellt".</span><span class="sxs-lookup"><span data-stu-id="a0002-109">If the system is not vulnerable to the exploit detected by a definition, then that definition is "retired".</span></span> <span data-ttu-id="a0002-110">Wenn alle Sicherheitsinformationen für ein bestimmtes Protokoll eingestellt werden, wird dieses Protokoll nicht mehr analysiert.</span><span class="sxs-lookup"><span data-stu-id="a0002-110">If all security intelligence for a given protocol are retired then that protocol is no longer parsed.</span></span> <span data-ttu-id="a0002-111">Die Aktivierung dieses Features trägt zur Verbesserung der Leistung bei.</span><span class="sxs-lookup"><span data-stu-id="a0002-111">Enabling this feature helps to improve performance.</span></span> <span data-ttu-id="a0002-112">Auf einem Computer, der mit den neuesten Sicherheitsupdates auf dem neuesten Stand ist, hat der Netzwerkschutz keine Auswirkungen auf die Netzwerkleistung.</span><span class="sxs-lookup"><span data-stu-id="a0002-112">On a computer that is up-to-date with all the latest security updates, network protection will have no impact on network performance.</span></span>

## <a name="use-group-policy-to-configure-definition-retirement"></a><span data-ttu-id="a0002-113">Konfigurieren der Einstellung von Definitionen mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="a0002-113">Use Group Policy to configure definition retirement</span></span>

1. <span data-ttu-id="a0002-114">Öffnen Sie auf Ihrem Gruppenrichtlinienverwaltungsendpunkt die [Gruppenrichtlinien-Verwaltungskonsole.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="a0002-114">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="a0002-115">Wechseln Sie zu Administrative Vorlagen für die **Computerkonfiguration**  >    >  **Windows Komponenten**  >  **Microsoft Defender Antivirus**  >  **Netzwerküberprüfungssystem.**</span><span class="sxs-lookup"><span data-stu-id="a0002-115">Go to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="a0002-116">Wählen Sie "Deaktivieren der **Definition aktivieren" aus.**</span><span class="sxs-lookup"><span data-stu-id="a0002-116">Select **Turn on definition retirement**.</span></span> <span data-ttu-id="a0002-117">Diese Richtlinie ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a0002-117">By default, this policy is enabled.</span></span> <span data-ttu-id="a0002-118">Wenn **"Nicht konfiguriert" festgelegt** ist, ist die Einstellung der Definition aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a0002-118">If set **Not configured**, definition retirement is enabled.</span></span> 

4. <span data-ttu-id="a0002-119">Um die Richtlinie zu bearbeiten, wählen Sie den Link **"Richtlinieneinstellung bearbeiten"** aus.</span><span class="sxs-lookup"><span data-stu-id="a0002-119">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="a0002-120">Wählen Sie **"Aktiviert"** und dann **"OK"** aus.</span><span class="sxs-lookup"><span data-stu-id="a0002-120">Select **Enabled**, and then select **OK**.</span></span>

6. <span data-ttu-id="a0002-121">Stellen Sie das aktualisierte Gruppenrichtlinienobjekt bereit.</span><span class="sxs-lookup"><span data-stu-id="a0002-121">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="a0002-122">Siehe [Gruppenrichtlinien-Verwaltungskonsole.](/windows/win32/srvnodes/group-policy)</span><span class="sxs-lookup"><span data-stu-id="a0002-122">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="a0002-123">Verwenden Sie gruppenrichtlinienobjekte lokal?</span><span class="sxs-lookup"><span data-stu-id="a0002-123">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="a0002-124">Erfahren Sie, wie sie in der Cloud übersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="a0002-124">See how they translate in the cloud.</span></span> <span data-ttu-id="a0002-125">[Analysieren Sie Ihre lokalen Gruppenrichtlinienobjekte mithilfe von Gruppenrichtlinienanalysen in Microsoft Endpoint Manager – Vorschau](/mem/intune/configuration/group-policy-analytics).</span><span class="sxs-lookup"><span data-stu-id="a0002-125">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
