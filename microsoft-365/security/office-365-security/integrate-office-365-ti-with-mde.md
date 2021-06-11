---
title: Verwenden von Microsoft Defender für Office 365 zusammen mit Microsoft Defender für Endpunkt
f1.keywords:
- NOCSH
keywords: Integration, Microsoft Defender, Microsoft Defender für Endpunkt
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 06/10/2021
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
ms.openlocfilehash: 63ae9f8c1136a973e4fccb63ecfbaee2639c3f6f
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904080"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="3a0d8-104">Verwenden von Microsoft Defender für Office 365 zusammen mit Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="3a0d8-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="3a0d8-105">[Microsoft Defender für Office 365](defender-for-office-365.md) kann für die Verwendung mit [Microsoft Defender für Endpunkt](/windows/security/threat-protection)konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="3a0d8-105">[Microsoft Defender for Office 365](defender-for-office-365.md) can be configured to work with [Microsoft Defender for Endpoint](/windows/security/threat-protection).</span></span>

<span data-ttu-id="3a0d8-106">Die Integration von Microsoft Defender für Office 365 in Microsoft Defender für Endpunkt kann Ihrem Sicherheitsteam dabei helfen, schnell zu überwachen und Maßnahmen zu ergreifen, wenn die Geräte der Benutzer gefährdet sind.</span><span class="sxs-lookup"><span data-stu-id="3a0d8-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="3a0d8-107">Sobald die Integration beispielsweise aktiviert ist, kann Ihr Sicherheitsteam die Geräte sehen, die möglicherweise von einer erkannten E-Mail-Nachricht betroffen sind, sowie wie viele aktuelle Warnungen für diese Geräte in Microsoft Defender für Endpunkt generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="3a0d8-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="3a0d8-108">Die folgende Abbildung zeigt, wie die Registerkarte **"Geräte"** aussieht, wenn Die Integration von Microsoft Defender für Endpunkt aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="3a0d8-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![Wenn Microsoft Defender für Endpunkt aktiviert ist, sehen Sie eine Liste der Geräte mit Warnungen.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="3a0d8-110">In diesem Beispiel können Sie sehen, dass die Empfänger der erkannten E-Mail-Nachricht über vier Geräte verfügen und eines über eine Warnung verfügt.</span><span class="sxs-lookup"><span data-stu-id="3a0d8-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="3a0d8-111">Wenn Sie auf den Link für ein Gerät klicken, wird seine Seite in [Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (früher Microsoft Defender Security Center) geöffnet.</span><span class="sxs-lookup"><span data-stu-id="3a0d8-111">Clicking the link for a device opens its page in [Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (formerly the Microsoft Defender Security Center).</span></span>

> [!TIP]
> <span data-ttu-id="3a0d8-112">Das Microsoft 365 Defender-Portal ersetzt die Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="3a0d8-112">The Microsoft 365 Defender portal replaces the Microsoft Defender Security Center.</span></span> <span data-ttu-id="3a0d8-113">Siehe [Microsoft Defender für Endpunkt in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).</span><span class="sxs-lookup"><span data-stu-id="3a0d8-113">See [Microsoft Defender for Endpoint in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="3a0d8-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3a0d8-114">Requirements</span></span>

- <span data-ttu-id="3a0d8-115">Ihre Organisation muss Über Microsoft Defender für Office 365 (oder Office 365 E5) und Microsoft Defender für Endpunkt verfügen.</span><span class="sxs-lookup"><span data-stu-id="3a0d8-115">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="3a0d8-116">Sie müssen ein globaler Administrator sein oder eine Sicherheitsadministratorrolle (z. B. Sicherheitsadministrator) in Microsoft 365 zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="3a0d8-116">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in Microsoft 365.</span></span> <span data-ttu-id="3a0d8-117">(Siehe [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="3a0d8-117">(See [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>

- <span data-ttu-id="3a0d8-118">Sie müssen Zugriff auf [Explorer (oder Echtzeiterkennungen)](threat-explorer.md)haben.</span><span class="sxs-lookup"><span data-stu-id="3a0d8-118">You must have access to [Explorer (or real-time detections)](threat-explorer.md).</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="3a0d8-119">So integrieren Sie Microsoft Defender für Office 365 in Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="3a0d8-119">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="3a0d8-120">Die Integration von Microsoft Defender für Office 365 in Microsoft Defender für Endpunkt ist sowohl in Defender für Endpunkt als auch in Defender für Office 365 eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="3a0d8-120">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up in both Defender for Endpoint and Defender for Office 365.</span></span>

1. <span data-ttu-id="3a0d8-121">Wechseln Sie als globaler Administrator oder Sicherheitsadministrator zu [https://protection.office.com](https://protection.office.com) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="3a0d8-121">As a global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="3a0d8-122">(Dadurch gelangen Sie zum Office 365 Security & Compliance Center.)</span><span class="sxs-lookup"><span data-stu-id="3a0d8-122">(This takes you to the Office 365 Security & Compliance Center.)</span></span>

2. <span data-ttu-id="3a0d8-123">Wählen Sie im Navigationsbereich **den Explorer für die Bedrohungsverwaltung** \> aus.</span><span class="sxs-lookup"><span data-stu-id="3a0d8-123">In the navigation pane, choose **Threat management** \> **Explorer**.</span></span>

   ![Explorer im Menü "Bedrohungsverwaltung"](../../media/ThreatMgmt-Explorer-nav.png)

3. <span data-ttu-id="3a0d8-125">Wählen Sie in der oberen rechten Ecke des Bildschirms **Defender für Endpunkt Einstellungen (MDE Einstellungen)** aus.</span><span class="sxs-lookup"><span data-stu-id="3a0d8-125">In the upper right corner of the screen, choose **Defender for Endpoint Settings (MDE Settings)**.</span></span>

4. <span data-ttu-id="3a0d8-126">Aktivieren Sie im Dialogfeld "Verbindung mit Microsoft Defender für Endpunkt" **Verbinden zu Microsoft Defender für Endpunkt.**</span><span class="sxs-lookup"><span data-stu-id="3a0d8-126">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

   ![Microsoft Defender für Endpunkt-Verbindung](../../media/Explorer-WDATPConnection-dialog.png)

5. <span data-ttu-id="3a0d8-128">Wechseln Sie zum Microsoft 365 Defender-Portal ( [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="3a0d8-128">Go to the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com).</span></span>

6. <span data-ttu-id="3a0d8-129">Wählen Sie in der Navigationsleiste **Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="3a0d8-129">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="3a0d8-130">Wählen Sie dann unter **"Allgemein"** die Option **"Erweiterte Features" aus.**</span><span class="sxs-lookup"><span data-stu-id="3a0d8-130">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="3a0d8-131">Scrollen Sie nach unten zu **Office 365 Threat Intelligence-Verbindung,** und aktivieren Sie die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="3a0d8-131">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span>

   ![Office 365 Verbindung zur Bedrohungserkennung](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a><span data-ttu-id="3a0d8-133">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="3a0d8-133">Related articles</span></span>

[<span data-ttu-id="3a0d8-134">Funktionen für die Untersuchung und Reaktion auf Bedrohungen in Office 365</span><span class="sxs-lookup"><span data-stu-id="3a0d8-134">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="3a0d8-135">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="3a0d8-135">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)

[<span data-ttu-id="3a0d8-136">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="3a0d8-136">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)
