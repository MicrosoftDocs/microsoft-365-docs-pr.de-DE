---
title: Verwenden von Microsoft Defender für Office 365 zusammen mit Microsoft Defender für Endpunkt
f1.keywords:
- NOCSH
keywords: Integration, Microsoft Defender, Microsoft Defender für Endpunkt
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
description: Verwenden Sie Microsoft Defender für Office 365 zusammen mit Microsoft Defender für Endpunkt, um detailliertere Informationen zu Bedrohungen für Ihre Geräte und E-Mail-Inhalte zu erhalten.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3f1d92d2433267b89398c7f7f582a8d1ee8cdba5
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878604"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="684ef-104">Verwenden von Microsoft Defender für Office 365 zusammen mit Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="684ef-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="684ef-105">[Microsoft Defender für Office 365](defender-for-office-365.md) kann für die Verwendung mit [Microsoft Defender für Endpunkt](/windows/security/threat-protection)konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="684ef-105">[Microsoft Defender for Office 365](defender-for-office-365.md) can be configured to work with [Microsoft Defender for Endpoint](/windows/security/threat-protection).</span></span>

<span data-ttu-id="684ef-106">Die Integration von Microsoft Defender für Office 365 in Microsoft Defender für Endpunkt kann Ihrem Sicherheitsteam dabei helfen, schnell zu überwachen und Maßnahmen zu ergreifen, wenn die Geräte der Benutzer gefährdet sind.</span><span class="sxs-lookup"><span data-stu-id="684ef-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="684ef-107">Sobald die Integration beispielsweise aktiviert ist, kann Ihr Sicherheitsteam die Geräte sehen, die möglicherweise von einer erkannten E-Mail-Nachricht betroffen sind, sowie wie viele aktuelle Warnungen für diese Geräte in Microsoft Defender für Endpunkt generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="684ef-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="684ef-108">Die folgende Abbildung zeigt, wie die Registerkarte **"Geräte"** aussieht, wenn Die Integration von Microsoft Defender für Endpunkt aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="684ef-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![Wenn Microsoft Defender für Endpunkt aktiviert ist, sehen Sie eine Liste der Geräte mit Warnungen.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="684ef-110">In diesem Beispiel können Sie sehen, dass die Empfänger der erkannten E-Mail-Nachricht über vier Geräte verfügen und eines über eine Warnung verfügt.</span><span class="sxs-lookup"><span data-stu-id="684ef-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="684ef-111">Durch Klicken auf den Link für ein Gerät wird die Seite im Microsoft Defender Security Center ( <https://securitycenter.windows.com> ) geöffnet.</span><span class="sxs-lookup"><span data-stu-id="684ef-111">Clicking the link for a device opens its page in the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

> [!TIP]
> <span data-ttu-id="684ef-112">**[Erfahren Sie mehr über die Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/use)** (auch als Microsoft Defender für Endpunkt-Portal bezeichnet).)</span><span class="sxs-lookup"><span data-stu-id="684ef-112">**[Learn more about the Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender for Endpoint portal.)</span></span>

## <a name="requirements"></a><span data-ttu-id="684ef-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="684ef-113">Requirements</span></span>

- <span data-ttu-id="684ef-114">Ihre Organisation benötigt Microsoft Defender für Office 365 (oder Office 365 E5) und Microsoft Defender für Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="684ef-114">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="684ef-115">Sie müssen ein globaler Administrator sein oder eine Sicherheitsadministratorrolle (z. B. Sicherheitsadministrator) im [Security & Compliance Center](https://protection.office.com)zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="684ef-115">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="684ef-116">(Siehe [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="684ef-116">(See [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>

- <span data-ttu-id="684ef-117">Sie müssen zugriff auf [Explorer (oder Echtzeiterkennungen)](threat-explorer.md) im Security & Compliance Center und im Microsoft Defender Security Center haben.</span><span class="sxs-lookup"><span data-stu-id="684ef-117">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="684ef-118">So integrieren Sie Microsoft Defender für Office 365 in Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="684ef-118">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="684ef-119">Die Integration von Microsoft Defender für Office 365 in Microsoft Defender für Endpunkt wird mithilfe des Security & Compliance Centers und des Microsoft Defender Security Center eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="684ef-119">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>

1. <span data-ttu-id="684ef-120">Wechseln Sie als globaler Administrator oder Sicherheitsadministrator zu <https://protection.office.com> und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="684ef-120">As a global administrator or a security administrator, go to <https://protection.office.com> and sign in.</span></span> <span data-ttu-id="684ef-121">(Dadurch gelangen Sie zum Office 365 Security & Compliance Center.)</span><span class="sxs-lookup"><span data-stu-id="684ef-121">(This takes you to the Office 365 Security & Compliance Center.)</span></span>

2. <span data-ttu-id="684ef-122">Wählen Sie im Navigationsbereich **den Explorer für die Bedrohungsverwaltung** \> aus.</span><span class="sxs-lookup"><span data-stu-id="684ef-122">In the navigation pane, choose **Threat management** \> **Explorer**.</span></span>

   ![Explorer im Menü "Bedrohungsverwaltung"](../../media/ThreatMgmt-Explorer-nav.png)

3. <span data-ttu-id="684ef-124">Wählen Sie in der oberen rechten Ecke des Bildschirms **Defender für Endpunkt Einstellungen (MDE Einstellungen)** aus.</span><span class="sxs-lookup"><span data-stu-id="684ef-124">In the upper right corner of the screen, choose **Defender for Endpoint Settings (MDE Settings)**.</span></span>

4. <span data-ttu-id="684ef-125">Aktivieren Sie im Microsoft Defender für Endpunkt-Verbindungsdialogfeld **Verbinden zu Microsoft Defender für Endpunkt.**</span><span class="sxs-lookup"><span data-stu-id="684ef-125">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

   ![Microsoft Defender für Endpunkt-Verbindung](../../media/Explorer-WDATPConnection-dialog.png)

5. <span data-ttu-id="684ef-127">Wechseln Sie zum Microsoft Defender Security Center ( <https://securitycenter.windows.com> ).</span><span class="sxs-lookup"><span data-stu-id="684ef-127">Go to the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

6. <span data-ttu-id="684ef-128">Wählen Sie in der Navigationsleiste **Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="684ef-128">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="684ef-129">Wählen Sie dann unter **"Allgemein"** die Option **"Erweiterte Features" aus.**</span><span class="sxs-lookup"><span data-stu-id="684ef-129">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="684ef-130">Scrollen Sie nach unten zu **Office 365 Threat Intelligence-Verbindung,** und aktivieren Sie die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="684ef-130">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span>

   ![Office 365 Verbindung zur Bedrohungserkennung](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a><span data-ttu-id="684ef-132">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="684ef-132">Related articles</span></span>

[<span data-ttu-id="684ef-133">Funktionen für die Untersuchung und Reaktion auf Bedrohungen in Office 365</span><span class="sxs-lookup"><span data-stu-id="684ef-133">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="684ef-134">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="684ef-134">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)

[<span data-ttu-id="684ef-135">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="684ef-135">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)
