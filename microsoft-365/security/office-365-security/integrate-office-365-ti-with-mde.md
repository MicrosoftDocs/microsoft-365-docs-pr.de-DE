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
ms.openlocfilehash: fed3a04a7a699b4689cd9d6d9d335a8ba51d2fd8
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083380"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="9a32a-104">Verwenden von Microsoft Defender für Office 365 zusammen mit Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="9a32a-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="9a32a-105">[Microsoft Defender für Office 365](defender-for-office-365.md) kann für die Verwendung mit [Microsoft Defender für Endpunkt](/windows/security/threat-protection)konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="9a32a-105">[Microsoft Defender for Office 365](defender-for-office-365.md) can be configured to work with [Microsoft Defender for Endpoint](/windows/security/threat-protection).</span></span>

<span data-ttu-id="9a32a-106">Die Integration von Microsoft Defender für Office 365 in Microsoft Defender für Endpunkt kann Ihrem Sicherheitsteam helfen, die Überwachung und schnelle Maßnahmen zu ergreifen, wenn die Geräte der Benutzer gefährdet sind.</span><span class="sxs-lookup"><span data-stu-id="9a32a-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="9a32a-107">Sobald die Integration beispielsweise aktiviert ist, kann Ihr Sicherheitsteam die Geräte sehen, die möglicherweise von einer erkannten E-Mail-Nachricht betroffen sind, sowie wie viele aktuelle Warnungen für diese Geräte in Microsoft Defender für Endpunkt generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="9a32a-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="9a32a-108">Die folgende Abbildung zeigt, wie die Registerkarte **"Geräte"** aussieht, wenn Die Integration von Microsoft Defender für Endpunkt aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="9a32a-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![Wenn Microsoft Defender für Endpunkt aktiviert ist, sehen Sie eine Liste der Geräte mit Warnungen.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="9a32a-110">In diesem Beispiel können Sie sehen, dass die Empfänger der erkannten E-Mail-Nachricht über vier Geräte verfügen und eines über eine Warnung verfügt.</span><span class="sxs-lookup"><span data-stu-id="9a32a-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="9a32a-111">Durch Klicken auf den Link für ein Gerät wird die Seite [im Microsoft 365 Defender-Portal](../defender-endpoint/microsoft-defender-security-center.md) (früher Microsoft Defender Security Center) geöffnet.</span><span class="sxs-lookup"><span data-stu-id="9a32a-111">Clicking the link for a device opens its page in [the Microsoft 365 Defender portal](../defender-endpoint/microsoft-defender-security-center.md) (formerly the Microsoft Defender security center).</span></span>

> [!TIP]
> <span data-ttu-id="9a32a-112">Das Microsoft 365 Defender-Portal ersetzt die Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="9a32a-112">The Microsoft 365 Defender portal replaces the Microsoft Defender Security Center.</span></span> <span data-ttu-id="9a32a-113">Siehe [Microsoft Defender für Endpunkt in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).</span><span class="sxs-lookup"><span data-stu-id="9a32a-113">See [Microsoft Defender for Endpoint in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="9a32a-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9a32a-114">Requirements</span></span>

- <span data-ttu-id="9a32a-115">Ihre Organisation benötigt Microsoft Defender für Office 365 (oder Office 365 E5) und Microsoft Defender für Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="9a32a-115">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="9a32a-116">Sie müssen ein globaler Administrator sein oder eine Sicherheitsadministratorrolle (z. B. Sicherheitsadministrator) in Microsoft 365 zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="9a32a-116">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in Microsoft 365.</span></span> <span data-ttu-id="9a32a-117">Weitere Informationen finden Sie unter [Berechtigungen im Microsoft 365 Defender-Portal](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="9a32a-117">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

- <span data-ttu-id="9a32a-118">Sie müssen Zugriff auf [Explorer (oder Echtzeiterkennungen)](threat-explorer.md)haben.</span><span class="sxs-lookup"><span data-stu-id="9a32a-118">You must have access to [Explorer (or real-time detections)](threat-explorer.md).</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="9a32a-119">So integrieren Sie Microsoft Defender für Office 365 in Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="9a32a-119">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="9a32a-120">Die Integration von Microsoft Defender für Office 365 in Microsoft Defender für Endpunkt ist sowohl in Defender für Endpunkt als auch in Defender für Office 365 eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="9a32a-120">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up in both Defender for Endpoint and Defender for Office 365.</span></span>

1. <span data-ttu-id="9a32a-121">Öffnen Sie als globaler Administrator oder Sicherheitsadministrator das Microsoft 365 Defender-Portal ( <https://security.microsoft.com> ), und wechseln Sie zu **E-Mail & Zusammenarbeits-Explorer.** \> </span><span class="sxs-lookup"><span data-stu-id="9a32a-121">As a global administrator or a security administrator, open the Microsoft 365 Defender portal (<https://security.microsoft.com>) and go to **Email & collaboration** \> **Explorer**.</span></span> <span data-ttu-id="9a32a-122">Um direkt zur **Explorer-Seite** zu wechseln, verwenden Sie <https://security.microsoft.com/threatexplorer> .</span><span class="sxs-lookup"><span data-stu-id="9a32a-122">To go directly to the **Explorer** page, use <https://security.microsoft.com/threatexplorer>.</span></span>

2. <span data-ttu-id="9a32a-123">Klicken Sie auf der **Explorer-Seite** in der oberen rechten Ecke des Bildschirms auf **MDE Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="9a32a-123">On the **Explorer** page, in the upper right corner of the screen, click **MDE Settings**.</span></span>

3. <span data-ttu-id="9a32a-124">Aktivieren Sie im angezeigten **Microsoft Defender für Endpunkt-Verbindungs-Flyout** **Verbinden zu Microsoft Defender für Endpunkt** ( ![ Umschalten ](../../media/scc-toggle-on.png) ) und klicken Sie dann auf schließen ![ ](../../media/m365-cc-sc-close-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="9a32a-124">In the **Microsoft Defender for Endpoint connection** flyout that appears, turn on **Connect to Microsoft Defender for Endpoint** (![Toggle on](../../media/scc-toggle-on.png)) and then click ![Close icon](../../media/m365-cc-sc-close-icon.png) **Close**.</span></span>

    :::image type="content" source="../../media/explorer-mdeconnection-dialognew.png" alt-text="MDE-Verbindung":::

4. <span data-ttu-id="9a32a-126">Wählen Sie im Navigationsbereich **Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="9a32a-126">Back in the navigation pane, choose **Settings**.</span></span> <span data-ttu-id="9a32a-127">Wählen Sie auf der **Seite Einstellungen** **Endpunkte aus.**</span><span class="sxs-lookup"><span data-stu-id="9a32a-127">On the **Settings** page, choose **Endpoints**</span></span>

5. <span data-ttu-id="9a32a-128">Wählen Sie auf der seite **"Endpunkte",** die geöffnet wird, die Option **"Erweiterte Features" aus.**</span><span class="sxs-lookup"><span data-stu-id="9a32a-128">On the **Endpoints** page that opens, choose **Advanced features**.</span></span>

6. <span data-ttu-id="9a32a-129">Scrollen Sie nach unten zu **Office 365 Threat Intelligence-Verbindung,** und aktivieren Sie sie ( ![ Umschalten ](../../media/scc-toggle-on.png) ).</span><span class="sxs-lookup"><span data-stu-id="9a32a-129">Scroll down to **Office 365 Threat Intelligence connection**, and turn it on (![Toggle on](../../media/scc-toggle-on.png)).</span></span>

   <span data-ttu-id="9a32a-130">Wenn Sie fertig sind, klicken Sie auf **"Einstellungen speichern".**</span><span class="sxs-lookup"><span data-stu-id="9a32a-130">When you're finished, click **Save preferences**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="9a32a-131">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="9a32a-131">Related articles</span></span>

[<span data-ttu-id="9a32a-132">Funktionen zur Untersuchung und Reaktion auf Bedrohungen in Office 365</span><span class="sxs-lookup"><span data-stu-id="9a32a-132">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="9a32a-133">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="9a32a-133">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)

[<span data-ttu-id="9a32a-134">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="9a32a-134">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)
