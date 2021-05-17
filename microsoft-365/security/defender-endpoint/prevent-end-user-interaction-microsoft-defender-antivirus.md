---
title: Ausblenden der Microsoft Defender Antivirus Schnittstelle
description: Sie können die Kachel "Viren- und Bedrohungsschutz" in der Windows-Sicherheit ausblenden.
keywords: ui lockdown, headless mode, hide app, hide settings, hide interface
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
ms.openlocfilehash: 06ee2f1cb68df0a957818e1fccb45628487c39fd
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274916"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a><span data-ttu-id="8ad3a-104">Verhindern, dass Benutzer die Benutzeroberfläche Microsoft Defender Antivirus sehen oder interagieren</span><span class="sxs-lookup"><span data-stu-id="8ad3a-104">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8ad3a-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="8ad3a-105">**Applies to:**</span></span>

- [<span data-ttu-id="8ad3a-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="8ad3a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="8ad3a-107">Sie können gruppenrichtlinien verwenden, um zu verhindern, dass Benutzer auf Endpunkten die Microsoft Defender Antivirus sehen.</span><span class="sxs-lookup"><span data-stu-id="8ad3a-107">You can use Group Policy to prevent users on endpoints from seeing the Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="8ad3a-108">Sie können auch verhindern, dass Scans angehalten werden.</span><span class="sxs-lookup"><span data-stu-id="8ad3a-108">You can also prevent them from pausing scans.</span></span>

## <a name="hide-the-microsoft-defender-antivirus-interface"></a><span data-ttu-id="8ad3a-109">Ausblenden der Microsoft Defender Antivirus Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8ad3a-109">Hide the Microsoft Defender Antivirus interface</span></span>

<span data-ttu-id="8ad3a-110">In Windows 10 Version 1703 blendet das Ausblenden der Schnittstelle Microsoft Defender Antivirus Benachrichtigungen aus und verhindert, dass die Kachel "Viren & Bedrohungsschutz" in der Windows-Sicherheit angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="8ad3a-110">In Windows 10, versions 1703, hiding the interface will hide Microsoft Defender Antivirus notifications and prevent the Virus & threat protection tile from appearing in the Windows Security app.</span></span>

<span data-ttu-id="8ad3a-111">Mit der Einstellung auf **Enabled festgelegt:**</span><span class="sxs-lookup"><span data-stu-id="8ad3a-111">With the setting set to **Enabled**:</span></span>

![Screenshot der Windows-Sicherheit ohne den Abschnitt "Schildsymbol" und "Viren- und Bedrohungsschutz"](images/defender/wdav-headless-mode-1703.png)

<span data-ttu-id="8ad3a-113">Mit der Einstellung **deaktiviert** oder nicht konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="8ad3a-113">With the setting set to **Disabled** or not configured:</span></span>

![Screenshot der Windows-Sicherheit mit dem Schutzsymbol und dem Abschnitt "Viren- und Bedrohungsschutz"](images/defender/wdav-headless-mode-off-1703.png)

>[!NOTE]
><span data-ttu-id="8ad3a-115">Das Ausblenden der Schnittstelle verhindert auch, Microsoft Defender Antivirus Benachrichtigungen auf dem Endpunkt angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8ad3a-115">Hiding the interface will also prevent Microsoft Defender Antivirus notifications from appearing on the endpoint.</span></span> <span data-ttu-id="8ad3a-116">Microsoft Defender for Endpoint-Benachrichtigungen werden weiterhin angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8ad3a-116">Microsoft Defender for Endpoint notifications will still appear.</span></span> <span data-ttu-id="8ad3a-117">Sie können auch die auf [Endpunkten angezeigten Benachrichtigungen einzeln konfigurieren.](configure-notifications-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="8ad3a-117">You can also individually [configure the notifications that appear on endpoints](configure-notifications-microsoft-defender-antivirus.md)</span></span>

<span data-ttu-id="8ad3a-118">In früheren Versionen von Windows 10 blendet die Einstellung die Windows Defender aus.</span><span class="sxs-lookup"><span data-stu-id="8ad3a-118">In earlier versions of Windows 10, the setting will hide the Windows Defender client interface.</span></span> <span data-ttu-id="8ad3a-119">Wenn der Benutzer versucht, die App zu öffnen, wird eine Warnung mit dem Hinweis "Ihr Systemadministrator hat eingeschränkten Zugriff auf diese App" erhalten.</span><span class="sxs-lookup"><span data-stu-id="8ad3a-119">If the user attempts to open it, they will receive a warning that says, "Your system administrator has restricted access to this app."</span></span>

![Warnmeldung, wenn der Kopflosenmodus in Windows 10 Versionen vor 1703 aktiviert ist](images/defender/wdav-headless-mode-1607.png)

## <a name="use-group-policy-to-hide-the-microsoft-defender-av-interface-from-users"></a><span data-ttu-id="8ad3a-121">Verwenden von Gruppenrichtlinien zum Ausblenden der Microsoft Defender AV-Schnittstelle vor Benutzern</span><span class="sxs-lookup"><span data-stu-id="8ad3a-121">Use Group Policy to hide the Microsoft Defender AV interface from users</span></span>

1. <span data-ttu-id="8ad3a-122">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="8ad3a-122">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="8ad3a-123">Wechseln Sie **mit dem Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="8ad3a-123">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="8ad3a-124">Klicken Sie **auf Administrative Vorlagen**.</span><span class="sxs-lookup"><span data-stu-id="8ad3a-124">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="8ad3a-125">Erweitern Sie die **Struktur, Windows komponenten > Microsoft Defender Antivirus > Clientschnittstelle .**</span><span class="sxs-lookup"><span data-stu-id="8ad3a-125">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="8ad3a-126">Doppelklicken Sie auf die Einstellung **Kopflose Benutzeroberflächenmodus** aktivieren, und legen Sie die Option auf **Aktiviert .**</span><span class="sxs-lookup"><span data-stu-id="8ad3a-126">Double-click the **Enable headless UI mode** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="8ad3a-127">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8ad3a-127">Click **OK**.</span></span> 

<span data-ttu-id="8ad3a-128">Weitere [Optionen zum Verhindern,](configure-local-policy-overrides-microsoft-defender-antivirus.md) dass Benutzer den Schutz auf ihren PCs ändern, finden Sie unter Verhindern, dass Benutzer Richtlinieneinstellungen lokal ändern.</span><span class="sxs-lookup"><span data-stu-id="8ad3a-128">See [Prevent users from locally modifying policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) for more options on preventing users form modifying protection on their PCs.</span></span>

## <a name="prevent-users-from-pausing-a-scan"></a><span data-ttu-id="8ad3a-129">Verhindern, dass Benutzer eine Überprüfung anhalten</span><span class="sxs-lookup"><span data-stu-id="8ad3a-129">Prevent users from pausing a scan</span></span>

<span data-ttu-id="8ad3a-130">Sie können verhindern, dass Benutzer Scans anhalten, was hilfreich sein kann, um sicherzustellen, dass geplante oder bedarfsmäßige Scans nicht von Benutzern unterbrochen werden.</span><span class="sxs-lookup"><span data-stu-id="8ad3a-130">You can prevent users from pausing scans, which can be helpful to ensure scheduled or on-demand scans are not interrupted by users.</span></span>

> [!NOTE]
> <span data-ttu-id="8ad3a-131">Diese Einstellung wird bei der Windows 10.</span><span class="sxs-lookup"><span data-stu-id="8ad3a-131">This setting is not supported on Windows 10.</span></span>

### <a name="use-group-policy-to-prevent-users-from-pausing-a-scan"></a><span data-ttu-id="8ad3a-132">Verwenden von Gruppenrichtlinien, um zu verhindern, dass Benutzer eine Überprüfung anhalten</span><span class="sxs-lookup"><span data-stu-id="8ad3a-132">Use Group Policy to prevent users from pausing a scan</span></span>

1. <span data-ttu-id="8ad3a-133">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="8ad3a-133">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="8ad3a-134">Wechseln Sie **mit dem Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="8ad3a-134">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="8ad3a-135">Klicken Sie **auf Administrative Vorlagen**.</span><span class="sxs-lookup"><span data-stu-id="8ad3a-135">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="8ad3a-136">Erweitern Sie die Struktur, **Windows komponenten Microsoft Defender Antivirus**  >    >  **scannen**.</span><span class="sxs-lookup"><span data-stu-id="8ad3a-136">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

5. <span data-ttu-id="8ad3a-137">Doppelklicken Sie auf die Einstellung **Benutzern das Anhalten der** Überprüfung erlauben, und legen Sie die Option auf Deaktiviert **.**</span><span class="sxs-lookup"><span data-stu-id="8ad3a-137">Double-click the **Allow users to pause scan** setting and set the option to **Disabled**.</span></span> <span data-ttu-id="8ad3a-138">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8ad3a-138">Click **OK**.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="8ad3a-139">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="8ad3a-139">Related articles</span></span>

- [<span data-ttu-id="8ad3a-140">Konfigurieren der Benachrichtigungen, die auf Endpunkten angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="8ad3a-140">Configure the notifications that appear on endpoints</span></span>](configure-notifications-microsoft-defender-antivirus.md)

- [<span data-ttu-id="8ad3a-141">Konfigurieren der Endbenutzerinteraktion mit Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="8ad3a-141">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)

- [<span data-ttu-id="8ad3a-142">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="8ad3a-142">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)