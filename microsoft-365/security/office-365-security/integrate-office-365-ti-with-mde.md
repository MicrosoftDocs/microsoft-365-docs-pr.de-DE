---
title: Verwenden von Microsoft Defender for Office 365 zusammen mit Microsoft Defender for Endpoint
f1.keywords:
- NOCSH
keywords: integration, Microsoft Defender, Microsoft Defender for Endpoint
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Verwenden Sie Microsoft Defender for Office 365 zusammen mit Microsoft Defender for Endpoint, um detailliertere Informationen zu Bedrohungen gegen Ihre Geräte und E-Mail-Inhalte zu erhalten.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e6ad81102a9702a725f40fcdb5421a2b19b0086d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934033"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="bbacb-104">Verwenden von Microsoft Defender for Office 365 zusammen mit Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bbacb-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="bbacb-105">[Microsoft Defender für Office 365](defender-for-office-365.md) kann für die Zusammenarbeit mit [Microsoft Defender for Endpoint konfiguriert werden.](/windows/security/threat-protection)</span><span class="sxs-lookup"><span data-stu-id="bbacb-105">[Microsoft Defender for Office 365](defender-for-office-365.md) can be configured to work with [Microsoft Defender for Endpoint](/windows/security/threat-protection).</span></span>

<span data-ttu-id="bbacb-106">Die Integration von Microsoft Defender for Office 365 in Microsoft Defender for Endpoint kann Ihrem Sicherheitsbetriebsteam bei der Überwachung und schnellen Umsetzung von Maßnahmen helfen, wenn die Geräte der Benutzer gefährdet sind.</span><span class="sxs-lookup"><span data-stu-id="bbacb-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="bbacb-107">Wenn beispielsweise die Integration aktiviert ist, kann Ihr Sicherheitsteam die Geräte anzeigen, die potenziell von einer erkannten E-Mail-Nachricht betroffen sind, sowie die Vielen kürzlich generierten Warnungen für diese Geräte in Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="bbacb-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="bbacb-108">Die folgende Abbildung zeigt, wie die Registerkarte **Geräte** aussieht, wenn Die Integration von Microsoft Defender for Endpoint aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="bbacb-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![Wenn Microsoft Defender for Endpoint aktiviert ist, wird eine Liste der Geräte mit Warnungen angezeigt.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="bbacb-110">In diesem Beispiel sehen Sie, dass die Empfänger der erkannten E-Mail-Nachricht vier Geräte und eines über eine Warnung verfügen.</span><span class="sxs-lookup"><span data-stu-id="bbacb-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="bbacb-111">Wenn Sie auf den Link für ein Gerät klicken, wird die Seite im Microsoft Defender Security Center ( <https://securitycenter.windows.com> ) geöffnet.</span><span class="sxs-lookup"><span data-stu-id="bbacb-111">Clicking the link for a device opens its page in the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

> [!TIP]
> <span data-ttu-id="bbacb-112">**[Erfahren Sie mehr über Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/use)** (auch als Microsoft Defender for Endpoint-Portal bezeichnet).)</span><span class="sxs-lookup"><span data-stu-id="bbacb-112">**[Learn more about the Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender for Endpoint portal.)</span></span>

## <a name="requirements"></a><span data-ttu-id="bbacb-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bbacb-113">Requirements</span></span>

- <span data-ttu-id="bbacb-114">Ihre Organisation muss über Microsoft Defender für Office 365 (oder Office 365 E5) und Microsoft Defender for Endpoint verfügen.</span><span class="sxs-lookup"><span data-stu-id="bbacb-114">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="bbacb-115">Sie müssen ein globaler Administrator sein oder eine Sicherheitsadministratorrolle (z. B. Sicherheitsadministrator) im [Security & Compliance Center zugewiesen haben.](https://protection.office.com)</span><span class="sxs-lookup"><span data-stu-id="bbacb-115">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="bbacb-116">(Siehe [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="bbacb-116">(See [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>

- <span data-ttu-id="bbacb-117">Sie müssen sowohl auf [Explorer (oder Echtzeiterkennungen)](threat-explorer.md) im Security & Compliance Center als auch auf die Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="bbacb-117">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="bbacb-118">So integrieren Sie Microsoft Defender for Office 365 in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="bbacb-118">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="bbacb-119">Die Integration von Microsoft Defender for Office 365 in Microsoft Defender for Endpoint wird mithilfe des Security & Compliance Center und der Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="bbacb-119">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>

1. <span data-ttu-id="bbacb-120">Wechseln Sie als globaler Administrator oder Sicherheitsadministrator zu und <https://protection.office.com> melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="bbacb-120">As a global administrator or a security administrator, go to <https://protection.office.com> and sign in.</span></span> <span data-ttu-id="bbacb-121">(Dies führt Sie zum Office 365 Security & Compliance Center.)</span><span class="sxs-lookup"><span data-stu-id="bbacb-121">(This takes you to the Office 365 Security & Compliance Center.)</span></span>

2. <span data-ttu-id="bbacb-122">Wählen Sie im Navigationsbereich Den **Bedrohungsverwaltungs-Explorer** \> **aus.**</span><span class="sxs-lookup"><span data-stu-id="bbacb-122">In the navigation pane, choose **Threat management** \> **Explorer**.</span></span>

   ![Explorer im Menü Bedrohungsverwaltung](../../media/ThreatMgmt-Explorer-nav.png)

3. <span data-ttu-id="bbacb-124">Wählen Sie in der oberen rechten Ecke des Bildschirms **Defender for Endpoint Einstellungen (MDE Einstellungen) aus.**</span><span class="sxs-lookup"><span data-stu-id="bbacb-124">In the upper right corner of the screen, choose **Defender for Endpoint Settings (MDE Settings)**.</span></span>

4. <span data-ttu-id="bbacb-125">Aktivieren Sie im Dialogfeld Microsoft Defender for Endpoint-Verbindung die **Verbinden Microsoft Defender for Endpoint**.</span><span class="sxs-lookup"><span data-stu-id="bbacb-125">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

   ![Microsoft Defender for Endpoint-Verbindung](../../media/Explorer-WDATPConnection-dialog.png)

5. <span data-ttu-id="bbacb-127">Wechseln Sie zum Microsoft Defender Security Center ( <https://securitycenter.windows.com> ).</span><span class="sxs-lookup"><span data-stu-id="bbacb-127">Go to the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

6. <span data-ttu-id="bbacb-128">Wählen Sie in der Navigationsleiste **Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="bbacb-128">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="bbacb-129">Wählen Sie dann unter **Allgemein** die Option **Erweiterte Features aus.**</span><span class="sxs-lookup"><span data-stu-id="bbacb-129">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="bbacb-130">Scrollen Sie nach **unten Office 365 Threat Intelligence-Verbindung,** und schalten Sie die Verbindung ein.</span><span class="sxs-lookup"><span data-stu-id="bbacb-130">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span>

   ![Office 365 Threat Intelligence-Verbindung](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a><span data-ttu-id="bbacb-132">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="bbacb-132">Related articles</span></span>

[<span data-ttu-id="bbacb-133">Bedrohungsuntersuchungs- und Reaktionsfunktionen in Office 365</span><span class="sxs-lookup"><span data-stu-id="bbacb-133">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="bbacb-134">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="bbacb-134">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)

[<span data-ttu-id="bbacb-135">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="bbacb-135">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)