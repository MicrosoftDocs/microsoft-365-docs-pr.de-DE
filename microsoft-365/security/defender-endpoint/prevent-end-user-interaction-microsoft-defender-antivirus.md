---
title: Ausblenden der Microsoft Defender Antivirus-Schnittstelle
description: Sie können die Kachel für Viren- und Bedrohungsschutz in der Windows-Sicherheit-App ausblenden.
keywords: Ui-Sperrmodus, Headless-Modus, App ausblenden, Einstellungen ausblenden, Benutzeroberfläche ausblenden
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ff0e134d38288b12cbc46dc3ca5f103fbf8c7ad9
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007668"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a><span data-ttu-id="e51b3-104">Benutzer am Anzeigen oder Interagieren mit der Microsoft Defender Antivirus Benutzeroberfläche hindern</span><span class="sxs-lookup"><span data-stu-id="e51b3-104">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e51b3-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="e51b3-105">**Applies to:**</span></span>

- [<span data-ttu-id="e51b3-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="e51b3-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="e51b3-107">Mithilfe von Gruppenrichtlinien können Sie verhindern, dass Benutzern auf Endpunkten die Microsoft Defender Antivirus-Schnittstelle angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e51b3-107">You can use Group Policy to prevent users on endpoints from seeing the Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="e51b3-108">Sie können auch verhindern, dass sie Scans anhalten.</span><span class="sxs-lookup"><span data-stu-id="e51b3-108">You can also prevent them from pausing scans.</span></span>

## <a name="hide-the-microsoft-defender-antivirus-interface"></a><span data-ttu-id="e51b3-109">Ausblenden der Microsoft Defender Antivirus-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e51b3-109">Hide the Microsoft Defender Antivirus interface</span></span>

<span data-ttu-id="e51b3-110">In Windows 10, Version 1703, blendet das Ausblenden der Schnittstelle Microsoft Defender Antivirus Benachrichtigungen aus und verhindert, dass die Kachel zum Viren- & Bedrohungsschutz in der Windows-Sicherheit App angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e51b3-110">In Windows 10, versions 1703, hiding the interface will hide Microsoft Defender Antivirus notifications and prevent the Virus & threat protection tile from appearing in the Windows Security app.</span></span>

<span data-ttu-id="e51b3-111">Mit aktivierter **Einstellung:**</span><span class="sxs-lookup"><span data-stu-id="e51b3-111">With the setting set to **Enabled**:</span></span>

:::image type="content" source="../../media/wdav-headless-mode-1703.png" alt-text="Windows-Sicherheit ohne das Schildsymbol und den Abschnitt &quot;Viren- und Bedrohungsschutz&quot;":::

<span data-ttu-id="e51b3-113">Wenn die Einstellung auf **"Deaktiviert"** festgelegt oder nicht konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="e51b3-113">With the setting set to **Disabled** or not configured:</span></span>

:::image type="content" source="../../media/wdav-headless-mode-1703.png" alt-text="Screenshot der Windows-Sicherheit mit Schutzsymbolen und Bedrohungsschutzabschnitten":::

>[!NOTE]
><span data-ttu-id="e51b3-115">Durch das Ausblenden der Schnittstelle wird auch verhindert, dass Microsoft Defender Antivirus Benachrichtigungen auf dem Endpunkt angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e51b3-115">Hiding the interface will also prevent Microsoft Defender Antivirus notifications from appearing on the endpoint.</span></span> <span data-ttu-id="e51b3-116">Microsoft Defender für Endpunkt-Benachrichtigungen werden weiterhin angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e51b3-116">Microsoft Defender for Endpoint notifications will still appear.</span></span> <span data-ttu-id="e51b3-117">Sie können auch [die Benachrichtigungen, die auf Endpunkten angezeigt werden,](configure-notifications-microsoft-defender-antivirus.md) einzeln konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e51b3-117">You can also individually [configure the notifications that appear on endpoints](configure-notifications-microsoft-defender-antivirus.md)</span></span>

<span data-ttu-id="e51b3-118">In früheren Versionen von Windows 10 blendet die Einstellung die Windows Defender Clientschnittstelle aus.</span><span class="sxs-lookup"><span data-stu-id="e51b3-118">In earlier versions of Windows 10, the setting will hide the Windows Defender client interface.</span></span> <span data-ttu-id="e51b3-119">Wenn der Benutzer versucht, sie zu öffnen, wird eine Warnung mit der Meldung "Ihr Systemadministrator hat den Zugriff auf diese App eingeschränkt" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e51b3-119">If the user attempts to open it, they will receive a warning that says, "Your system administrator has restricted access to this app."</span></span>

:::image type="content" source="../../media/wdav-headless-mode-1607.png" alt-text="Warnmeldung, wenn der Headless-Modus in früheren Versionen als 1703 in Windows 10 aktiviert ist":::

## <a name="use-group-policy-to-hide-the-microsoft-defender-av-interface-from-users"></a><span data-ttu-id="e51b3-121">Verwenden von Gruppenrichtlinien zum Ausblenden der Microsoft Defender AV-Benutzeroberfläche vor Benutzern</span><span class="sxs-lookup"><span data-stu-id="e51b3-121">Use Group Policy to hide the Microsoft Defender AV interface from users</span></span>

1. <span data-ttu-id="e51b3-122">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="e51b3-122">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="e51b3-123">Navigieren Sie mithilfe des **Gruppenrichtlinienverwaltungs-Editors** zur **Computerkonfiguration.**</span><span class="sxs-lookup"><span data-stu-id="e51b3-123">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="e51b3-124">Klicken Sie auf **"Administrative Vorlagen".**</span><span class="sxs-lookup"><span data-stu-id="e51b3-124">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="e51b3-125">Erweitern Sie die Struktur bis Windows **Komponenten > Microsoft Defender Antivirus > Clientschnittstelle.**</span><span class="sxs-lookup"><span data-stu-id="e51b3-125">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="e51b3-126">Doppelklicken Sie auf die Einstellung **"Headless UI-Modus aktivieren",** und legen Sie die Option auf **"Aktiviert"** fest.</span><span class="sxs-lookup"><span data-stu-id="e51b3-126">Double-click the **Enable headless UI mode** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="e51b3-127">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e51b3-127">Click **OK**.</span></span> 

<span data-ttu-id="e51b3-128">Weitere Optionen zum Verhindern, dass Benutzer den Schutz auf ihren PCs ändern, finden Sie unter ["Verhindern,](configure-local-policy-overrides-microsoft-defender-antivirus.md) dass Benutzer richtlinieneinstellungen lokal ändern".</span><span class="sxs-lookup"><span data-stu-id="e51b3-128">See [Prevent users from locally modifying policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) for more options on preventing users form modifying protection on their PCs.</span></span>

## <a name="prevent-users-from-pausing-a-scan"></a><span data-ttu-id="e51b3-129">Verhindern, dass Benutzer eine Überprüfung anhalten</span><span class="sxs-lookup"><span data-stu-id="e51b3-129">Prevent users from pausing a scan</span></span>

<span data-ttu-id="e51b3-130">Sie können verhindern, dass Benutzer Scans anhalten. Dies kann hilfreich sein, um sicherzustellen, dass geplante oder bedarfsgesteuerte Scans nicht von Benutzern unterbrochen werden.</span><span class="sxs-lookup"><span data-stu-id="e51b3-130">You can prevent users from pausing scans, which can be helpful to ensure scheduled or on-demand scans are not interrupted by users.</span></span>

> [!NOTE]
> <span data-ttu-id="e51b3-131">Diese Einstellung wird für Windows 10 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e51b3-131">This setting is not supported on Windows 10.</span></span>

### <a name="use-group-policy-to-prevent-users-from-pausing-a-scan"></a><span data-ttu-id="e51b3-132">Verwenden von Gruppenrichtlinien, um zu verhindern, dass Benutzer einen Scan anhalten</span><span class="sxs-lookup"><span data-stu-id="e51b3-132">Use Group Policy to prevent users from pausing a scan</span></span>

1. <span data-ttu-id="e51b3-133">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="e51b3-133">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="e51b3-134">Navigieren Sie mithilfe des **Gruppenrichtlinienverwaltungs-Editors** zur **Computerkonfiguration.**</span><span class="sxs-lookup"><span data-stu-id="e51b3-134">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="e51b3-135">Klicken Sie auf **"Administrative Vorlagen".**</span><span class="sxs-lookup"><span data-stu-id="e51b3-135">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="e51b3-136">Erweitern Sie die Struktur, um **komponenten Microsoft Defender Antivirus**  >  Scan **Windows.**  >  </span><span class="sxs-lookup"><span data-stu-id="e51b3-136">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

5. <span data-ttu-id="e51b3-137">Doppelklicken Sie auf die Einstellung "Benutzern das Anhalten der **Scaneinstellung erlauben",** und legen Sie die Option auf **"Deaktiviert"** fest.</span><span class="sxs-lookup"><span data-stu-id="e51b3-137">Double-click the **Allow users to pause scan** setting and set the option to **Disabled**.</span></span> <span data-ttu-id="e51b3-138">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e51b3-138">Click **OK**.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="e51b3-139">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="e51b3-139">Related articles</span></span>

- [<span data-ttu-id="e51b3-140">Konfigurieren der Benachrichtigungen, die auf Endpunkten angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="e51b3-140">Configure the notifications that appear on endpoints</span></span>](configure-notifications-microsoft-defender-antivirus.md)

- [<span data-ttu-id="e51b3-141">Konfigurieren der Endbenutzerinteraktion mit Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="e51b3-141">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)

- [<span data-ttu-id="e51b3-142">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="e51b3-142">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)