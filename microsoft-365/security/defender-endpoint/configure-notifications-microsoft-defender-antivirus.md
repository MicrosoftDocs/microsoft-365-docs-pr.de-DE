---
title: Konfigurieren Microsoft Defender Antivirus Benachrichtigungen
description: Erfahren Sie, wie Sie standard- und Microsoft Defender Antivirus Benachrichtigungen auf Endpunkten konfigurieren und anpassen.
keywords: Benachrichtigungen, Defender, Antivirus, Endpunkt, Verwaltung, Administrator
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f885b6d7991e4175cd14be5bbe9e0a7c96b1580f
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572345"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a><span data-ttu-id="c4186-104">Konfigurieren der Benachrichtigungen, die auf Endpunkten angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="c4186-104">Configure the notifications that appear on endpoints</span></span>

<span data-ttu-id="c4186-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c4186-105">**Applies to:**</span></span>

- [<span data-ttu-id="c4186-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="c4186-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="c4186-107">In Windows 10 sind Anwendungsbenachrichtigungen zur Erkennung und Behebung von Schadsoftware robuster, konsistenter und präziser.</span><span class="sxs-lookup"><span data-stu-id="c4186-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span>

<span data-ttu-id="c4186-108">Benachrichtigungen werden auf Endpunkten angezeigt, wenn manuell ausgelöste und geplante Scans abgeschlossen werden und Bedrohungen erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="c4186-108">Notifications appear on endpoints when manually triggered and scheduled scans are completed and threats are detected.</span></span> <span data-ttu-id="c4186-109">Diese Benachrichtigungen werden auch im **Notification Center** angezeigt, und eine Zusammenfassung der Scans und Bedrohungserkennungen wird in regelmäßigen Zeitintervallen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c4186-109">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="c4186-110">Sie können auch konfigurieren, wie Standardbenachrichtigungen auf Endpunkten angezeigt werden, z. B. Benachrichtigungen für einen Neustart oder wenn eine Bedrohung erkannt und behoben wurde.</span><span class="sxs-lookup"><span data-stu-id="c4186-110">You can also configure how standard notifications appear on endpoints, such as notifications for reboot or when a threat has been detected and remediated.</span></span>

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a><span data-ttu-id="c4186-111">Konfigurieren der zusätzlichen Benachrichtigungen, die auf Endpunkten angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="c4186-111">Configure the additional notifications that appear on endpoints</span></span>

<span data-ttu-id="c4186-112">Sie können die Anzeige zusätzlicher Benachrichtigungen, z. B. Zusammenfassungen zur Erkennung neuer Bedrohungen, in der [Windows-Sicherheit-App](microsoft-defender-security-center-antivirus.md) und mit Gruppenrichtlinien konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c4186-112">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="c4186-113">In Windows 10 Version 1607 hieß das  Feature erweiterte Benachrichtigungen und konnte unter **Windows Einstellungen**  >  **Update & Security** Windows Defender konfiguriert  >  **werden.**</span><span class="sxs-lookup"><span data-stu-id="c4186-113">In Windows 10, version 1607 the feature was called **Enhanced notifications** and could be configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="c4186-114">Unter Gruppenrichtlinieneinstellungen in allen Versionen von Windows 10 wird dies als Erweiterte **Benachrichtigungen bezeichnet.**</span><span class="sxs-lookup"><span data-stu-id="c4186-114">In Group Policy settings in all versions of Windows 10, it is called **Enhanced notifications**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c4186-115">Das Deaktivieren zusätzlicher Benachrichtigungen deaktiviert keine kritischen Benachrichtigungen, z. B. Bedrohungserkennungs- und Behebungswarnungen.</span><span class="sxs-lookup"><span data-stu-id="c4186-115">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

<span data-ttu-id="c4186-116">**Verwenden sie Windows-Sicherheit App, um zusätzliche Benachrichtigungen zu deaktivieren:**</span><span class="sxs-lookup"><span data-stu-id="c4186-116">**Use the Windows Security app to disable additional notifications:**</span></span>

1. <span data-ttu-id="c4186-117">Öffnen Sie Windows-Sicherheit App, indem Sie auf das Schildsymbol in der Taskleiste klicken oder im Startmenü nach **Sicherheit suchen.**</span><span class="sxs-lookup"><span data-stu-id="c4186-117">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="c4186-118">Wählen **Sie &** Kachel für den Bedrohungsschutz (oder das Schildsymbol auf der linken Menüleiste) aus, und wählen Sie dann **Virenschutzeinstellungen & Bedrohungsschutz aus.**</span><span class="sxs-lookup"><span data-stu-id="c4186-118">Select **Virus & threat protection** tile (or the shield icon on the left menu bar) and, then select **Virus & threat protection settings**</span></span>

3. <span data-ttu-id="c4186-119">Scrollen Sie zum Abschnitt **Benachrichtigungen,** und klicken Sie **auf Benachrichtigungseinstellungen ändern.**</span><span class="sxs-lookup"><span data-stu-id="c4186-119">Scroll to the **Notifications** section and click **Change notification settings**.</span></span>

4. <span data-ttu-id="c4186-120">Wechseln Sie zu **Aus** oder **Ein,** um zusätzliche Benachrichtigungen zu deaktivieren oder zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c4186-120">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

<span data-ttu-id="c4186-121">**Verwenden von Gruppenrichtlinien zum Deaktivieren zusätzlicher Benachrichtigungen:**</span><span class="sxs-lookup"><span data-stu-id="c4186-121">**Use Group Policy to disable additional notifications:**</span></span>

1. <span data-ttu-id="c4186-122">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="c4186-122">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="c4186-123">Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="c4186-123">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="c4186-124">Klicken Sie **auf Administrative Vorlagen**.</span><span class="sxs-lookup"><span data-stu-id="c4186-124">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="c4186-125">Erweitern Sie die **Struktur, um Windows komponenten > Microsoft Defender Antivirus > zu erweitern.**</span><span class="sxs-lookup"><span data-stu-id="c4186-125">Expand the tree to **Windows components > Microsoft Defender Antivirus > Reporting**.</span></span>

5. <span data-ttu-id="c4186-126">Doppelklicken Sie **auf Erweiterte Benachrichtigungen deaktivieren,** und legen Sie die Option auf **Aktiviert .**</span><span class="sxs-lookup"><span data-stu-id="c4186-126">Double-click **Turn off enhanced notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="c4186-127">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4186-127">Click **OK**.</span></span> <span data-ttu-id="c4186-128">Dadurch wird verhindert, dass zusätzliche Benachrichtigungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c4186-128">This will prevent additional notifications from appearing.</span></span>

## <a name="configure-standard-notifications-on-endpoints"></a><span data-ttu-id="c4186-129">Konfigurieren von Standardbenachrichtigungen auf Endpunkten</span><span class="sxs-lookup"><span data-stu-id="c4186-129">Configure standard notifications on endpoints</span></span>

<span data-ttu-id="c4186-130">Sie können Gruppenrichtlinien verwenden, um:</span><span class="sxs-lookup"><span data-stu-id="c4186-130">You can use Group Policy to:</span></span>

- <span data-ttu-id="c4186-131">Anzeigen von zusätzlichem, angepassten Text auf Endpunkten, wenn der Benutzer eine Aktion ausführen muss</span><span class="sxs-lookup"><span data-stu-id="c4186-131">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="c4186-132">Ausblenden aller Benachrichtigungen auf Endpunkten</span><span class="sxs-lookup"><span data-stu-id="c4186-132">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="c4186-133">Ausblenden von Neustartbenachrichtigungen auf Endpunkten</span><span class="sxs-lookup"><span data-stu-id="c4186-133">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="c4186-134">Das Ausblenden von Benachrichtigungen kann in Situationen hilfreich sein, in denen Sie nicht die gesamte Microsoft Defender Antivirus können.</span><span class="sxs-lookup"><span data-stu-id="c4186-134">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="c4186-135">Weitere Informationen finden Sie unter Prevent users from seeing or [interacting with the Microsoft Defender Antivirus user interface.](prevent-end-user-interaction-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="c4186-135">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> 

> [!NOTE]
> <span data-ttu-id="c4186-136">Ausblenden von Benachrichtigungen tritt nur auf Endpunkten auf, für die die Richtlinie bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c4186-136">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="c4186-137">Benachrichtigungen im Zusammenhang mit Aktionen, die ausgeführt werden müssen (z. B. ein Neustart), werden weiterhin im Microsoft Endpoint Manager Endpoint Protection [und Berichten angezeigt.](/configmgr/protect/deploy-use/monitor-endpoint-protection)</span><span class="sxs-lookup"><span data-stu-id="c4186-137">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="c4186-138">Anweisungen zum Hinzufügen benutzerdefinierter Kontaktinformationen zu den Benachrichtigungen, die Benutzern auf ihren Computern angezeigt werden, finden Sie unter Customize [the Windows-Sicherheit app for](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) your organization.</span><span class="sxs-lookup"><span data-stu-id="c4186-138">See [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) for instructions to add custom contact information to the notifications that users see on their machines.</span></span>

<span data-ttu-id="c4186-139">**Verwenden von Gruppenrichtlinien zum Ausblenden von Benachrichtigungen:**</span><span class="sxs-lookup"><span data-stu-id="c4186-139">**Use Group Policy to hide notifications:**</span></span>

1. <span data-ttu-id="c4186-140">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="c4186-140">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and click **Edit**.</span></span>

2. <span data-ttu-id="c4186-141">Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** und klicken Sie auf **Administrative Vorlagen**.</span><span class="sxs-lookup"><span data-stu-id="c4186-141">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="c4186-142">Erweitern Sie die **Struktur, Windows komponenten > Microsoft Defender Antivirus > Clientschnittstelle .**</span><span class="sxs-lookup"><span data-stu-id="c4186-142">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span> 

4. <span data-ttu-id="c4186-143">Doppelklicken Sie **auf Alle Benachrichtigungen unterdrücken,** und legen Sie die Option auf **Aktiviert .**</span><span class="sxs-lookup"><span data-stu-id="c4186-143">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="c4186-144">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4186-144">Click **OK**.</span></span> <span data-ttu-id="c4186-145">Dadurch wird verhindert, dass zusätzliche Benachrichtigungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c4186-145">This will prevent additional notifications from appearing.</span></span>

<span data-ttu-id="c4186-146">**Verwenden von Gruppenrichtlinien zum Ausblenden von Neustartbenachrichtigungen:**</span><span class="sxs-lookup"><span data-stu-id="c4186-146">**Use Group Policy to hide reboot notifications:**</span></span>

1. <span data-ttu-id="c4186-147">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="c4186-147">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="c4186-148">Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="c4186-148">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="c4186-149">Klicken Sie **auf Administrative Vorlagen**.</span><span class="sxs-lookup"><span data-stu-id="c4186-149">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="c4186-150">Erweitern Sie die **Struktur, Windows komponenten > Microsoft Defender Antivirus > Clientschnittstelle .**</span><span class="sxs-lookup"><span data-stu-id="c4186-150">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="c4186-151">Doppelklicken Sie **auf Neustartbenachrichtigungen unterdrücken,** und legen Sie die Option auf **Aktiviert .**</span><span class="sxs-lookup"><span data-stu-id="c4186-151">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="c4186-152">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4186-152">Click **OK**.</span></span> <span data-ttu-id="c4186-153">Dadurch wird verhindert, dass zusätzliche Benachrichtigungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c4186-153">This will prevent additional notifications from appearing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c4186-154">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="c4186-154">Related topics</span></span>

- [<span data-ttu-id="c4186-155">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="c4186-155">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="c4186-156">Konfigurieren der Endbenutzerinteraktion mit Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="c4186-156">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)
