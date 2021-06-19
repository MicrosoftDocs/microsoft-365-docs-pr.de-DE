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
ms.openlocfilehash: e59f608a6f732f58002dfd2ff34666865ab23f3d
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028875"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="344b5-104">Verwenden von Microsoft Defender für Office 365 zusammen mit Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="344b5-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="344b5-105">[Microsoft Defender für Office 365](defender-for-office-365.md) kann für die Verwendung mit [Microsoft Defender für Endpunkt](/windows/security/threat-protection)konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="344b5-105">[Microsoft Defender for Office 365](defender-for-office-365.md) can be configured to work with [Microsoft Defender for Endpoint](/windows/security/threat-protection).</span></span>

<span data-ttu-id="344b5-106">Die Integration von Microsoft Defender für Office 365 in Microsoft Defender für Endpunkt kann Ihrem Sicherheitsteam helfen, die Überwachung und schnelle Maßnahmen zu ergreifen, wenn die Geräte der Benutzer gefährdet sind.</span><span class="sxs-lookup"><span data-stu-id="344b5-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="344b5-107">Sobald die Integration beispielsweise aktiviert ist, kann Ihr Sicherheitsteam die Geräte sehen, die möglicherweise von einer erkannten E-Mail-Nachricht betroffen sind, sowie wie viele aktuelle Warnungen für diese Geräte in Microsoft Defender für Endpunkt generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="344b5-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="344b5-108">Die folgende Abbildung zeigt, wie die Registerkarte **"Geräte"** aussieht, wenn Die Integration von Microsoft Defender für Endpunkt aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="344b5-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![Wenn Microsoft Defender für Endpunkt aktiviert ist, sehen Sie eine Liste der Geräte mit Warnungen.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="344b5-110">In diesem Beispiel können Sie sehen, dass die Empfänger der erkannten E-Mail-Nachricht über vier Geräte verfügen und eines über eine Warnung verfügt.</span><span class="sxs-lookup"><span data-stu-id="344b5-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="344b5-111">Durch Klicken auf den Link für ein Gerät wird die Seite in [Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (früher Microsoft Defender Security Center) geöffnet.</span><span class="sxs-lookup"><span data-stu-id="344b5-111">Clicking the link for a device opens its page in [Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (formerly the Microsoft Defender Security Center).</span></span>

> [!TIP]
> <span data-ttu-id="344b5-112">Das Microsoft 365 Defender-Portal ersetzt die Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="344b5-112">The Microsoft 365 Defender portal replaces the Microsoft Defender Security Center.</span></span> <span data-ttu-id="344b5-113">Siehe [Microsoft Defender für Endpunkt in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).</span><span class="sxs-lookup"><span data-stu-id="344b5-113">See [Microsoft Defender for Endpoint in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="344b5-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="344b5-114">Requirements</span></span>

- <span data-ttu-id="344b5-115">Ihre Organisation benötigt Microsoft Defender für Office 365 (oder Office 365 E5) und Microsoft Defender für Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="344b5-115">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="344b5-116">Sie müssen ein globaler Administrator sein oder eine Sicherheitsadministratorrolle (z. B. Sicherheitsadministrator) in Microsoft 365 zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="344b5-116">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in Microsoft 365.</span></span> <span data-ttu-id="344b5-117">(Siehe [Berechtigungen im Microsoft 365 Defender](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="344b5-117">(See [Permissions in the Microsoft 365 Defender](permissions-in-the-security-and-compliance-center.md))</span></span>

- <span data-ttu-id="344b5-118">Sie müssen Zugriff auf [Explorer (oder Echtzeiterkennungen)](threat-explorer.md)haben.</span><span class="sxs-lookup"><span data-stu-id="344b5-118">You must have access to [Explorer (or real-time detections)](threat-explorer.md).</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="344b5-119">So integrieren Sie Microsoft Defender für Office 365 in Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="344b5-119">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="344b5-120">Die Integration von Microsoft Defender für Office 365 in Microsoft Defender für Endpunkt ist sowohl in Defender für Endpunkt als auch in Defender für Office 365 eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="344b5-120">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up in both Defender for Endpoint and Defender for Office 365.</span></span>

1. <span data-ttu-id="344b5-121">Wechseln Sie als globaler Administrator oder Sicherheitsadministrator zu [https://security.microsoft.com](https://security.microsoft.com) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="344b5-121">As a global administrator or a security administrator, go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> <span data-ttu-id="344b5-122">(Dadurch gelangen Sie zum Microsoft 365 Defender-Portal.)</span><span class="sxs-lookup"><span data-stu-id="344b5-122">(This takes you to the Microsoft 365 Defender portal.)</span></span>

2. <span data-ttu-id="344b5-123">Wählen Sie im Navigationsbereich **E-Mail &** Zusammenarbeits-Explorer \> aus.</span><span class="sxs-lookup"><span data-stu-id="344b5-123">In the navigation pane, choose **Email & collaboration** \> **Explorer**.</span></span>

3. <span data-ttu-id="344b5-124">Klicken Sie in der oberen rechten Ecke des Bildschirms auf **MDE Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="344b5-124">In the upper right corner of the screen, click **MDE Settings**.</span></span>

4. <span data-ttu-id="344b5-125">Aktivieren Sie im Microsoft Defender für Endpunkt-Verbindungsdialogfeld **Verbinden zu Microsoft Defender für Endpunkt.**</span><span class="sxs-lookup"><span data-stu-id="344b5-125">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    :::image type="content" source="../../media/explorer-mdeconnection-dialognew.png" alt-text="MDE-Verbindung":::

5. <span data-ttu-id="344b5-127">Wechseln Sie zum Microsoft 365 Defender-Portal ( [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="344b5-127">Go to the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com).</span></span>

6. <span data-ttu-id="344b5-128">Wählen Sie in der Navigationsleiste **Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="344b5-128">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="344b5-129">Wählen Sie dann unter **"Allgemein"** die Option **"Erweiterte Features" aus.**</span><span class="sxs-lookup"><span data-stu-id="344b5-129">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="344b5-130">Scrollen Sie nach unten zu **Office 365 Threat Intelligence-Verbindung,** und aktivieren Sie die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="344b5-130">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span>

   ![Office 365 Verbindung zur Bedrohungserkennung](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a><span data-ttu-id="344b5-132">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="344b5-132">Related articles</span></span>

[<span data-ttu-id="344b5-133">Funktionen zur Untersuchung und Reaktion auf Bedrohungen in Office 365</span><span class="sxs-lookup"><span data-stu-id="344b5-133">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="344b5-134">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="344b5-134">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)

[<span data-ttu-id="344b5-135">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="344b5-135">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)
