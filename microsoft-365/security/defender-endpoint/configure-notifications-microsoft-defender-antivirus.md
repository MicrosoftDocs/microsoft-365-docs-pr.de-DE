---
title: Konfigurieren von Microsoft Defender Antivirus-Benachrichtigungen
description: Erfahren Sie, wie Sie standard- und zusätzliche Microsoft Defender Antivirus-Benachrichtigungen auf Endpunkten konfigurieren und anpassen.
keywords: Benachrichtigungen, Defender, Antivirus, Endpunkt, Verwaltung, Administrator
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 82ca54e383943f4994f9647ce1e110a6621b1327
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690685"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a><span data-ttu-id="56807-104">Konfigurieren der Benachrichtigungen, die auf Endpunkten angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="56807-104">Configure the notifications that appear on endpoints</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="56807-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="56807-105">**Applies to:**</span></span>

- [<span data-ttu-id="56807-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="56807-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="56807-107">In Windows 10 sind Anwendungsbenachrichtigungen zur Erkennung und Behebung von Schadsoftware robuster, konsistenter und präziser.</span><span class="sxs-lookup"><span data-stu-id="56807-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span>

<span data-ttu-id="56807-108">Benachrichtigungen werden auf Endpunkten angezeigt, wenn manuell ausgelöste und geplante Scans abgeschlossen werden und Bedrohungen erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="56807-108">Notifications appear on endpoints when manually triggered and scheduled scans are completed and threats are detected.</span></span> <span data-ttu-id="56807-109">Diese Benachrichtigungen werden auch im **Notification Center** angezeigt, und eine Zusammenfassung der Scans und Bedrohungserkennungen wird in regelmäßigen Zeitintervallen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="56807-109">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="56807-110">Sie können auch konfigurieren, wie Standardbenachrichtigungen auf Endpunkten angezeigt werden, z. B. Benachrichtigungen für einen Neustart oder wenn eine Bedrohung erkannt und behoben wurde.</span><span class="sxs-lookup"><span data-stu-id="56807-110">You can also configure how standard notifications appear on endpoints, such as notifications for reboot or when a threat has been detected and remediated.</span></span>

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a><span data-ttu-id="56807-111">Konfigurieren der zusätzlichen Benachrichtigungen, die auf Endpunkten angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="56807-111">Configure the additional notifications that appear on endpoints</span></span>

<span data-ttu-id="56807-112">Sie können die Anzeige zusätzlicher Benachrichtigungen, z. B. zusammenfassungen zur Erkennung neuer Bedrohungen, in der [Windows Security-App](microsoft-defender-security-center-antivirus.md) und mit Gruppenrichtlinien konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="56807-112">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="56807-113">In Windows 10, Version 1607, hieß das Feature erweiterte Benachrichtigungen und konnte unter **Windows Settings** Update &   >  **security**  >  **Windows Defender.**</span><span class="sxs-lookup"><span data-stu-id="56807-113">In Windows 10, version 1607 the feature was called **Enhanced notifications** and could be configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="56807-114">Unter Gruppenrichtlinieneinstellungen in allen Versionen von Windows 10 wird dies als Erweiterte **Benachrichtigungen bezeichnet.**</span><span class="sxs-lookup"><span data-stu-id="56807-114">In Group Policy settings in all versions of Windows 10, it is called **Enhanced notifications**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="56807-115">Das Deaktivieren zusätzlicher Benachrichtigungen deaktiviert keine kritischen Benachrichtigungen, z. B. Bedrohungserkennungs- und Behebungswarnungen.</span><span class="sxs-lookup"><span data-stu-id="56807-115">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

<span data-ttu-id="56807-116">**Verwenden Sie die Windows Security-App, um zusätzliche Benachrichtigungen zu deaktivieren:**</span><span class="sxs-lookup"><span data-stu-id="56807-116">**Use the Windows Security app to disable additional notifications:**</span></span>

1. <span data-ttu-id="56807-117">Öffnen Sie die Windows Security-App, indem Sie auf das Schildsymbol in der Aufgabenleiste klicken oder im Startmenü nach **Defender suchen.**</span><span class="sxs-lookup"><span data-stu-id="56807-117">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="56807-118">Klicken Sie **auf &** Kachel "Virenschutz" (oder auf das Schildsymbol auf der linken Menüleiste) und dann auf die Bezeichnung **& Bedrohungsschutzeinstellungen:**</span><span class="sxs-lookup"><span data-stu-id="56807-118">Click the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![Screenshot der Bezeichnung & Virenschutzeinstellungen in der Windows Security App](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="56807-120">Scrollen Sie zum Abschnitt **Benachrichtigungen,** und klicken Sie **auf Benachrichtigungseinstellungen ändern.**</span><span class="sxs-lookup"><span data-stu-id="56807-120">Scroll to the **Notifications** section and click **Change notification settings**.</span></span>

4. <span data-ttu-id="56807-121">Wechseln Sie zu **Aus** oder **Ein,** um zusätzliche Benachrichtigungen zu deaktivieren oder zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="56807-121">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

<span data-ttu-id="56807-122">**Verwenden von Gruppenrichtlinien zum Deaktivieren zusätzlicher Benachrichtigungen:**</span><span class="sxs-lookup"><span data-stu-id="56807-122">**Use Group Policy to disable additional notifications:**</span></span>

1. <span data-ttu-id="56807-123">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="56807-123">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="56807-124">Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="56807-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="56807-125">Klicken Sie **auf Administrative Vorlagen**.</span><span class="sxs-lookup"><span data-stu-id="56807-125">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="56807-126">Erweitern Sie die Struktur auf **Windows-Komponenten > Microsoft Defender Antivirus > Reporting**.</span><span class="sxs-lookup"><span data-stu-id="56807-126">Expand the tree to **Windows components > Microsoft Defender Antivirus > Reporting**.</span></span>

5. <span data-ttu-id="56807-127">Doppelklicken Sie **auf Erweiterte Benachrichtigungen deaktivieren,** und legen Sie die Option auf **Aktiviert .**</span><span class="sxs-lookup"><span data-stu-id="56807-127">Double-click **Turn off enhanced notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="56807-128">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="56807-128">Click **OK**.</span></span> <span data-ttu-id="56807-129">Dadurch wird verhindert, dass zusätzliche Benachrichtigungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="56807-129">This will prevent additional notifications from appearing.</span></span>

## <a name="configure-standard-notifications-on-endpoints"></a><span data-ttu-id="56807-130">Konfigurieren von Standardbenachrichtigungen auf Endpunkten</span><span class="sxs-lookup"><span data-stu-id="56807-130">Configure standard notifications on endpoints</span></span>

<span data-ttu-id="56807-131">Sie können Gruppenrichtlinien verwenden, um:</span><span class="sxs-lookup"><span data-stu-id="56807-131">You can use Group Policy to:</span></span>

- <span data-ttu-id="56807-132">Anzeigen von zusätzlichem, angepassten Text auf Endpunkten, wenn der Benutzer eine Aktion ausführen muss</span><span class="sxs-lookup"><span data-stu-id="56807-132">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="56807-133">Ausblenden aller Benachrichtigungen auf Endpunkten</span><span class="sxs-lookup"><span data-stu-id="56807-133">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="56807-134">Ausblenden von Neustartbenachrichtigungen auf Endpunkten</span><span class="sxs-lookup"><span data-stu-id="56807-134">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="56807-135">Das Ausblenden von Benachrichtigungen kann in Situationen hilfreich sein, in denen Sie nicht die gesamte Microsoft Defender Antivirus-Schnittstelle ausblenden können.</span><span class="sxs-lookup"><span data-stu-id="56807-135">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="56807-136">Weitere Informationen finden Sie unter Prevent users from seeing or [interacting with the Microsoft Defender Antivirus user interface.](prevent-end-user-interaction-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="56807-136">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> 

> [!NOTE]
> <span data-ttu-id="56807-137">Ausblenden von Benachrichtigungen tritt nur auf Endpunkten auf, für die die Richtlinie bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="56807-137">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="56807-138">Benachrichtigungen im Zusammenhang mit Aktionen, die ausgeführt werden müssen (z. B. ein Neustart), werden weiterhin im Microsoft Endpoint Manager Endpoint Protection-Überwachungsdashboard und [berichten angezeigt.](/configmgr/protect/deploy-use/monitor-endpoint-protection)</span><span class="sxs-lookup"><span data-stu-id="56807-138">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="56807-139">Anweisungen [zum Hinzufügen benutzerdefinierter](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) Kontaktinformationen zu den Benachrichtigungen, die Benutzern auf ihren Computern angezeigt werden, finden Sie unter Customize the Windows Security app for your organization.</span><span class="sxs-lookup"><span data-stu-id="56807-139">See [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) for instructions to add custom contact information to the notifications that users see on their machines.</span></span>

<span data-ttu-id="56807-140">**Verwenden von Gruppenrichtlinien zum Ausblenden von Benachrichtigungen:**</span><span class="sxs-lookup"><span data-stu-id="56807-140">**Use Group Policy to hide notifications:**</span></span>

1. <span data-ttu-id="56807-141">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="56807-141">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and click **Edit**.</span></span>

2. <span data-ttu-id="56807-142">Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** und klicken Sie auf **Administrative Vorlagen**.</span><span class="sxs-lookup"><span data-stu-id="56807-142">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="56807-143">Erweitern Sie die Struktur auf **Windows-Komponenten > Microsoft Defender Antivirus > Clientschnittstelle**.</span><span class="sxs-lookup"><span data-stu-id="56807-143">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span> 

4. <span data-ttu-id="56807-144">Doppelklicken Sie **auf Alle Benachrichtigungen unterdrücken,** und legen Sie die Option auf **Aktiviert .**</span><span class="sxs-lookup"><span data-stu-id="56807-144">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="56807-145">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="56807-145">Click **OK**.</span></span> <span data-ttu-id="56807-146">Dadurch wird verhindert, dass zusätzliche Benachrichtigungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="56807-146">This will prevent additional notifications from appearing.</span></span>

<span data-ttu-id="56807-147">**Verwenden von Gruppenrichtlinien zum Ausblenden von Neustartbenachrichtigungen:**</span><span class="sxs-lookup"><span data-stu-id="56807-147">**Use Group Policy to hide reboot notifications:**</span></span>

1. <span data-ttu-id="56807-148">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="56807-148">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="56807-149">Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="56807-149">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="56807-150">Klicken Sie **auf Administrative Vorlagen**.</span><span class="sxs-lookup"><span data-stu-id="56807-150">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="56807-151">Erweitern Sie die Struktur auf **Windows-Komponenten > Microsoft Defender Antivirus > Clientschnittstelle**.</span><span class="sxs-lookup"><span data-stu-id="56807-151">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="56807-152">Doppelklicken Sie **auf Neustartbenachrichtigungen unterdrücken,** und legen Sie die Option auf **Aktiviert .**</span><span class="sxs-lookup"><span data-stu-id="56807-152">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="56807-153">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="56807-153">Click **OK**.</span></span> <span data-ttu-id="56807-154">Dadurch wird verhindert, dass zusätzliche Benachrichtigungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="56807-154">This will prevent additional notifications from appearing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="56807-155">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="56807-155">Related topics</span></span>

- [<span data-ttu-id="56807-156">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="56807-156">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="56807-157">Konfigurieren der Endbenutzerinteraktion mit Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="56807-157">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)