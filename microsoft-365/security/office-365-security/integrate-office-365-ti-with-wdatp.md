---
title: Integration von Office 365 ATP in Microsoft Defender ATP
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 07/08/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: Integrieren Sie Office 365 Advanced Threat Protection mit Microsoft Defender Advanced Threat Protection, um detaillierte Informationen zur Bedrohungs Verwaltung zu erhalten.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bfb87edd24a22033b3771ba0fd3c4f1afbbc988e
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086708"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="a923f-103">Integration Office 365 Advanced Threat Protection mit Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a923f-103">Integrate Office 365 Advanced Threat Protection with Microsoft Defender Advanced Threat Protection</span></span>

<span data-ttu-id="a923f-104">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Office 365 ATP) kann für die Zusammenarbeit mit [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender ATP) konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="a923f-104">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Office 365 ATP) can be configured to work with [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender ATP).</span></span>

<span data-ttu-id="a923f-105">Die Integration von Office 365 ATP mit Microsoft Defender ATP kann Ihren sicherheitsvorgängen helfen, das Team zu überwachen und schnell Maßnahmen zu ergreifen, wenn die Geräte der Benutzer gefährdet sind.</span><span class="sxs-lookup"><span data-stu-id="a923f-105">Integrating Office 365 ATP with Microsoft Defender ATP can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="a923f-106">Wenn die Integration beispielsweise aktiviert ist, kann Ihr Sicherheits Betriebsteam die Geräte anzeigen, die von einer erkannten e-Mail-Nachricht potenziell betroffen sind, sowie die Anzahl der letzten Warnungen, die diese Geräte in Microsoft Defender ATP haben.</span><span class="sxs-lookup"><span data-stu-id="a923f-106">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts those devices have in Microsoft Defender ATP.</span></span> 

<span data-ttu-id="a923f-107">In der folgenden Abbildung wird dargestellt, wie die Registerkarte **Geräte** aussieht, wenn die ATP-Integration von Microsoft Defender aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="a923f-107">The following image depicts what the **Devices** tab looks like have Microsoft Defender ATP integration enabled:</span></span>
  
![Wenn Microsoft Defender ATP aktiviert ist, können Sie eine Liste der Geräte mit Warnungen anzeigen.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="a923f-109">In diesem Beispiel können Sie sehen, dass die Empfänger der erkannten e-Mail-Nachricht vier Geräte und eine Warnung besitzen.</span><span class="sxs-lookup"><span data-stu-id="a923f-109">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="a923f-110">Wenn Sie auf den Link für ein Gerät klicken, wird seine Seite im Sicherheits Center von Microsoft Defender geöffnet ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="a923f-110">Clicking the link for a device opens its page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

> [!TIP]
> <span data-ttu-id="a923f-111">**[Erfahren Sie mehr über das Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (auch als Microsoft Defender ATP-Portal bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="a923f-111">**[Learn more about the Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender ATP portal.)</span></span>
  
## <a name="requirements"></a><span data-ttu-id="a923f-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a923f-112">Requirements</span></span>

- <span data-ttu-id="a923f-113">Ihre Organisation muss Office 365 ATP-Plan 2 (oder Office 365 E5) und Microsoft Defender ATP haben.</span><span class="sxs-lookup"><span data-stu-id="a923f-113">Your organization must have Office 365 ATP Plan 2 (or Office 365 E5) and Microsoft Defender ATP.</span></span>
    
- <span data-ttu-id="a923f-114">Sie müssen ein globaler Administrator sein oder über eine Sicherheitsadministrator Rolle (wie etwa Sicherheitsadministrator) verfügen, die im [Security &amp; Compliance Center](https://protection.office.com)zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="a923f-114">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="a923f-115">(Siehe [Berechtigungen im Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="a923f-115">(See [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="a923f-116">Sie müssen sowohl im Sicherheits & Compliance Center als auch im Sicherheitscenter von Microsoft Defender Zugriff auf beide [Explorer-(oder Echt Zeit Erkennungen)](threat-explorer.md) haben.</span><span class="sxs-lookup"><span data-stu-id="a923f-116">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a><span data-ttu-id="a923f-117">So integrieren Sie Office 365 ATP mit Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="a923f-117">To integrate Office 365 ATP with Microsoft Defender ATP</span></span>

<span data-ttu-id="a923f-118">Die Integration von Office 365 ATP mit Microsoft Defender ATP wird mithilfe des Security & Compliance Centers und des Sicherheitscenters von Microsoft Defender eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="a923f-118">Integrating Office 365 ATP with Microsoft Defender ATP is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="a923f-119">Wechseln Sie als globaler Administrator oder Sicherheitsadministrator zu und melden Sie sich an [https://protection.office.com](https://protection.office.com) .</span><span class="sxs-lookup"><span data-stu-id="a923f-119">As a global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="a923f-120">(Hiermit gelangen Sie zum Office 365 Security & Compliance Center.)</span><span class="sxs-lookup"><span data-stu-id="a923f-120">(This takes you to the Office 365 Security & Compliance Center.)</span></span>
    
2. <span data-ttu-id="a923f-121">Wählen Sie im Navigationsbereich **Threat Management**  >  **Explorer**aus.</span><span class="sxs-lookup"><span data-stu-id="a923f-121">In the navigation pane, choose **Threat management** > **Explorer**.</span></span><br><span data-ttu-id="a923f-122">![Explorer im Menü "Threat Management"](../../media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="a923f-122">![Explorer in Threat Management menu](../../media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="a923f-123">Wählen Sie in der oberen rechten Ecke des Bildschirms **Einstellungen für WDATP**aus.</span><span class="sxs-lookup"><span data-stu-id="a923f-123">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="a923f-124">Aktivieren Sie im Dialogfeld Microsoft Defender ATP Connection die Option **Connect to Windows ATP**.</span><span class="sxs-lookup"><span data-stu-id="a923f-124">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span><br><span data-ttu-id="a923f-125">![Microsoft Defender ATP-Verbindung](../../media/Explorer-WDATPConnection-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="a923f-125">![Microsoft Defender ATP connection](../../media/Explorer-WDATPConnection-dialog.png)</span></span><br>
    
5. <span data-ttu-id="a923f-126">Wechseln Sie zum Microsoft Defender-Sicherheits Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="a923f-126">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

6. <span data-ttu-id="a923f-127">Klicken Sie in der Navigationsleiste auf **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="a923f-127">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="a923f-128">Wählen Sie dann unter **Allgemein**die Option **Erweiterte Funktionen**aus.</span><span class="sxs-lookup"><span data-stu-id="a923f-128">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="a923f-129">Scrollen Sie nach unten zu **Office 365 Threat Intelligence-Verbindung**, und schalten Sie die Verbindung ein.</span><span class="sxs-lookup"><span data-stu-id="a923f-129">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span><br/><span data-ttu-id="a923f-130">![Office 365 Threat Intelligence-Verbindung](../../media/mdatp-oatptoggle.png)</span><span class="sxs-lookup"><span data-stu-id="a923f-130">![Office 365 threat intelligence connection](../../media/mdatp-oatptoggle.png)</span></span><br>

## <a name="related-articles"></a><span data-ttu-id="a923f-131">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="a923f-131">Related articles</span></span>

[<span data-ttu-id="a923f-132">Funktionen für die Untersuchung und Reaktion auf Bedrohungen in Office 365</span><span class="sxs-lookup"><span data-stu-id="a923f-132">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)
  
[<span data-ttu-id="a923f-133">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a923f-133">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="a923f-134">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="a923f-134">Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection)
