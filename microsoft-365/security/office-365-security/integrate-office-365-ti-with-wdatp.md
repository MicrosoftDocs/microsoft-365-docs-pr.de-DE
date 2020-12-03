---
title: Verwenden von Microsoft Defender für Office 365 zusammen mit Microsoft Defender für Endpoint
f1.keywords:
- NOCSH
keywords: Integration, Microsoft Defender, ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 09/29/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Verwenden Sie Microsoft Defender für Office 365 zusammen mit Microsoft Defender für Endpoint, um ausführlichere Informationen zu Bedrohungen für Ihre Geräte und e-Mail-Inhalte zu erhalten.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8a598dce3a8049d97d43b742477ca8f7a2bfeadb
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561219"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="0a7d5-104">Verwenden von Microsoft Defender für Office 365 zusammen mit Microsoft Defender für Endpoint</span><span class="sxs-lookup"><span data-stu-id="0a7d5-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="0a7d5-105">[Microsoft Defender für Office 365](office-365-atp.md) kann für die Zusammenarbeit mit [Microsoft Defender für Endpoint](https://docs.microsoft.com/windows/security/threat-protection)konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="0a7d5-105">[Microsoft Defender for Office 365](office-365-atp.md) can be configured to work with [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection).</span></span>

<span data-ttu-id="0a7d5-106">Die Integration von Microsoft Defender für Office 365 mit Microsoft Defender für Endpoint kann Ihren sicherheitsvorgängen helfen, das Team zu überwachen und schnell Maßnahmen zu ergreifen, wenn die Geräte der Benutzer gefährdet sind.</span><span class="sxs-lookup"><span data-stu-id="0a7d5-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="0a7d5-107">Wenn beispielsweise die Integration aktiviert ist, kann Ihr Sicherheits Betriebsteam die Geräte anzeigen, die von einer erkannten e-Mail-Nachricht potenziell betroffen sind, sowie die Anzahl der letzten Warnungen, die für diese Geräte in Microsoft Defender für Endpoint generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="0a7d5-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span> 

<span data-ttu-id="0a7d5-108">In der folgenden Abbildung wird dargestellt, wie die Registerkarte **Geräte** aussieht, wenn Microsoft Defender für die Endpunkt Integration aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="0a7d5-108">The following image depicts what the **Devices** tab looks like have Microsoft Defender for Endpoint integration enabled:</span></span>
  
![Wenn Microsoft Defender für Endpoint aktiviert ist, können Sie eine Liste der Geräte mit Warnungen anzeigen.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="0a7d5-110">In diesem Beispiel können Sie sehen, dass die Empfänger der erkannten e-Mail-Nachricht vier Geräte und eine Warnung besitzen.</span><span class="sxs-lookup"><span data-stu-id="0a7d5-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="0a7d5-111">Wenn Sie auf den Link für ein Gerät klicken, wird seine Seite im Sicherheits Center von Microsoft Defender geöffnet ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="0a7d5-111">Clicking the link for a device opens its page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

> [!TIP]
> <span data-ttu-id="0a7d5-112">**[Erfahren Sie mehr über das Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (auch als Microsoft Defender für Endpoint-Portal bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="0a7d5-112">**[Learn more about the Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender for Endpoint portal.)</span></span>
  
## <a name="requirements"></a><span data-ttu-id="0a7d5-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0a7d5-113">Requirements</span></span>

- <span data-ttu-id="0a7d5-114">Ihre Organisation muss Microsoft Defender für Office 365 (oder Office 365 E5) und Microsoft Defender für Endpoint haben.</span><span class="sxs-lookup"><span data-stu-id="0a7d5-114">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>
    
- <span data-ttu-id="0a7d5-115">Sie müssen ein globaler Administrator sein oder über eine Sicherheitsadministrator Rolle (beispielsweise Sicherheitsadministrator) verfügen, die im [Security & Compliance Center](https://protection.office.com)zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="0a7d5-115">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="0a7d5-116">(Siehe [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="0a7d5-116">(See [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="0a7d5-117">Sie müssen sowohl im Sicherheits & Compliance Center als auch im Sicherheitscenter von Microsoft Defender Zugriff auf beide [Explorer-(oder Echt Zeit Erkennungen)](threat-explorer.md) haben.</span><span class="sxs-lookup"><span data-stu-id="0a7d5-117">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="0a7d5-118">So integrieren Sie Microsoft Defender für Office 365 mit Microsoft Defender für Endpoint</span><span class="sxs-lookup"><span data-stu-id="0a7d5-118">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="0a7d5-119">Die Integration von Microsoft Defender für Office 365 mit Microsoft Defender für Endpoint wird mithilfe des Security & Compliance Centers und des Sicherheitscenters von Microsoft Defender eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="0a7d5-119">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="0a7d5-120">Wechseln Sie als globaler Administrator oder Sicherheitsadministrator zu und melden Sie sich an [https://protection.office.com](https://protection.office.com) .</span><span class="sxs-lookup"><span data-stu-id="0a7d5-120">As a global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="0a7d5-121">(Hiermit gelangen Sie zum Office 365 Security & Compliance Center.)</span><span class="sxs-lookup"><span data-stu-id="0a7d5-121">(This takes you to the Office 365 Security & Compliance Center.)</span></span>
    
2. <span data-ttu-id="0a7d5-122">Wählen Sie im Navigationsbereich **Threat Management**  >  **Explorer** aus.</span><span class="sxs-lookup"><span data-stu-id="0a7d5-122">In the navigation pane, choose **Threat management** > **Explorer**.</span></span><br><span data-ttu-id="0a7d5-123">![Explorer im Menü "Threat Management"](../../media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="0a7d5-123">![Explorer in Threat Management menu](../../media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="0a7d5-124">Wählen Sie in der oberen rechten Ecke des Bildschirms **Defender for Endpoint Settings** aus.</span><span class="sxs-lookup"><span data-stu-id="0a7d5-124">In the upper right corner of the screen, choose **Defender for Endpoint Settings**.</span></span>
    
4. <span data-ttu-id="0a7d5-125">Aktivieren Sie im Dialogfeld Microsoft Defender für Endpunkt Verbindung die Option **Verbindung mit Microsoft Defender für Endpunkt herstellen**.</span><span class="sxs-lookup"><span data-stu-id="0a7d5-125">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span><br><span data-ttu-id="0a7d5-126">![Microsoft Defender für Endpunkt Verbindung](../../media/Explorer-WDATPConnection-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="0a7d5-126">![Microsoft Defender for Endpoint connection](../../media/Explorer-WDATPConnection-dialog.png)</span></span><br>
    
5. <span data-ttu-id="0a7d5-127">Wechseln Sie zum Microsoft Defender-Sicherheits Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="0a7d5-127">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

6. <span data-ttu-id="0a7d5-128">Klicken Sie in der Navigationsleiste auf **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="0a7d5-128">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="0a7d5-129">Wählen Sie dann unter **Allgemein** die Option **Erweiterte Funktionen** aus.</span><span class="sxs-lookup"><span data-stu-id="0a7d5-129">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="0a7d5-130">Scrollen Sie nach unten zu **Office 365 Threat Intelligence-Verbindung**, und schalten Sie die Verbindung ein.</span><span class="sxs-lookup"><span data-stu-id="0a7d5-130">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span><br/><span data-ttu-id="0a7d5-131">![Office 365 Threat Intelligence-Verbindung](../../media/mdatp-oatptoggle.png)</span><span class="sxs-lookup"><span data-stu-id="0a7d5-131">![Office 365 threat intelligence connection](../../media/mdatp-oatptoggle.png)</span></span><br>

## <a name="related-articles"></a><span data-ttu-id="0a7d5-132">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="0a7d5-132">Related articles</span></span>

[<span data-ttu-id="0a7d5-133">Funktionen für die Untersuchung und Reaktion auf Bedrohungen in Office 365</span><span class="sxs-lookup"><span data-stu-id="0a7d5-133">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)
  
[<span data-ttu-id="0a7d5-134">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="0a7d5-134">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
  
[<span data-ttu-id="0a7d5-135">Microsoft Defender für Endpoint</span><span class="sxs-lookup"><span data-stu-id="0a7d5-135">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)
