---
title: Konfigurieren Microsoft Defender Antivirus Benachrichtigungen
description: Erfahren Sie, wie Sie standard- und zusätzliche Microsoft Defender Antivirus-Benachrichtigungen auf Endpunkten konfigurieren und anpassen.
keywords: Benachrichtigungen, Defender, Antivirus, Endpunkt, Verwaltung, Administrator
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.topic: article
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 1e9f733b20b62af7e73a923932057920ff1dc155
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926238"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a><span data-ttu-id="cc65a-104">Konfigurieren der Benachrichtigungen, die auf Endpunkten angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="cc65a-104">Configure the notifications that appear on endpoints</span></span>

<span data-ttu-id="cc65a-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="cc65a-105">**Applies to:**</span></span>

- [<span data-ttu-id="cc65a-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="cc65a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="cc65a-107">In Windows 10 sind Anwendungsbenachrichtigungen zur Erkennung und Behebung von Schadsoftware robuster, konsistenter und präziser.</span><span class="sxs-lookup"><span data-stu-id="cc65a-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span>

<span data-ttu-id="cc65a-108">Benachrichtigungen werden auf Endpunkten angezeigt, wenn manuell ausgelöste und geplante Scans abgeschlossen und Bedrohungen erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="cc65a-108">Notifications appear on endpoints when manually triggered and scheduled scans are completed and threats are detected.</span></span> <span data-ttu-id="cc65a-109">Diese Benachrichtigungen werden auch im **Info-Center** angezeigt, und eine Zusammenfassung der Scans und Bedrohungserkennungen wird in regelmäßigen Zeitabständen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc65a-109">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="cc65a-110">Sie können auch konfigurieren, wie Standardbenachrichtigungen auf Endpunkten angezeigt werden, z. B. Benachrichtigungen zum Neustart oder wenn eine Bedrohung erkannt und behoben wurde.</span><span class="sxs-lookup"><span data-stu-id="cc65a-110">You can also configure how standard notifications appear on endpoints, such as notifications for reboot or when a threat has been detected and remediated.</span></span>

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a><span data-ttu-id="cc65a-111">Konfigurieren der zusätzlichen Benachrichtigungen, die auf Endpunkten angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="cc65a-111">Configure the additional notifications that appear on endpoints</span></span>

<span data-ttu-id="cc65a-112">Sie können die Anzeige zusätzlicher Benachrichtigungen, z. B. aktuelle Zusammenfassungen zur Bedrohungserkennung, in der [Windows-Sicherheit-App](microsoft-defender-security-center-antivirus.md) und mithilfe von Gruppenrichtlinien konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="cc65a-112">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="cc65a-113">In Windows 10 Version 1607 wurde das Feature als **erweiterte Benachrichtigungen** bezeichnet und konnte unter **Windows Einstellungen** Update & Security Windows Defender konfiguriert  >    >  werden.</span><span class="sxs-lookup"><span data-stu-id="cc65a-113">In Windows 10, version 1607 the feature was called **Enhanced notifications** and could be configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="cc65a-114">In den Gruppenrichtlinieneinstellungen in allen Versionen von Windows 10 wird sie als **erweiterte Benachrichtigungen** bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="cc65a-114">In Group Policy settings in all versions of Windows 10, it is called **Enhanced notifications**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc65a-115">Durch das Deaktivieren zusätzlicher Benachrichtigungen werden kritische Benachrichtigungen, z. B. Warnungen zur Bedrohungserkennung und -behebung, nicht deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="cc65a-115">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

<span data-ttu-id="cc65a-116">**Verwenden Sie die Windows-Sicherheit-App, um zusätzliche Benachrichtigungen zu deaktivieren:**</span><span class="sxs-lookup"><span data-stu-id="cc65a-116">**Use the Windows Security app to disable additional notifications:**</span></span>

1. <span data-ttu-id="cc65a-117">Öffnen Sie die Windows-Sicherheit App, indem Sie auf das Schildsymbol in der Taskleiste klicken oder im Startmenü nach **Sicherheit** suchen.</span><span class="sxs-lookup"><span data-stu-id="cc65a-117">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="cc65a-118">Wählen Sie die Kachel **"Viren- & Bedrohungsschutz"** (oder das Schildsymbol auf der linken Menüleiste) aus, und wählen Sie dann **"Virus & Bedrohungsschutzeinstellungen"** aus.</span><span class="sxs-lookup"><span data-stu-id="cc65a-118">Select **Virus & threat protection** tile (or the shield icon on the left menu bar) and, then select **Virus & threat protection settings**</span></span>

3. <span data-ttu-id="cc65a-119">Scrollen Sie zum Abschnitt **"Benachrichtigungen",** und klicken Sie auf **"Benachrichtigungseinstellungen ändern".**</span><span class="sxs-lookup"><span data-stu-id="cc65a-119">Scroll to the **Notifications** section and click **Change notification settings**.</span></span>

4. <span data-ttu-id="cc65a-120">Ziehen Sie den Schalter auf **"Aus"** oder **"Ein",** um zusätzliche Benachrichtigungen zu deaktivieren oder zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cc65a-120">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

<span data-ttu-id="cc65a-121">**Verwenden Von Gruppenrichtlinien zum Deaktivieren zusätzlicher Benachrichtigungen:**</span><span class="sxs-lookup"><span data-stu-id="cc65a-121">**Use Group Policy to disable additional notifications:**</span></span>

1. <span data-ttu-id="cc65a-122">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="cc65a-122">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="cc65a-123">Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration.**</span><span class="sxs-lookup"><span data-stu-id="cc65a-123">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="cc65a-124">Klicken Sie auf **"Administrative Vorlagen".**</span><span class="sxs-lookup"><span data-stu-id="cc65a-124">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="cc65a-125">Erweitern Sie die Struktur bis Windows **Komponenten > Microsoft Defender Antivirus > Berichterstellung.**</span><span class="sxs-lookup"><span data-stu-id="cc65a-125">Expand the tree to **Windows components > Microsoft Defender Antivirus > Reporting**.</span></span>

5. <span data-ttu-id="cc65a-126">Doppelklicken Sie auf **"Erweiterte Benachrichtigungen deaktivieren",** und legen Sie die Option auf **"Aktiviert"** fest.</span><span class="sxs-lookup"><span data-stu-id="cc65a-126">Double-click **Turn off enhanced notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="cc65a-127">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="cc65a-127">Click **OK**.</span></span> <span data-ttu-id="cc65a-128">Dadurch wird verhindert, dass zusätzliche Benachrichtigungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="cc65a-128">This will prevent additional notifications from appearing.</span></span>

## <a name="configure-standard-notifications-on-endpoints"></a><span data-ttu-id="cc65a-129">Konfigurieren von Standardbenachrichtigungen auf Endpunkten</span><span class="sxs-lookup"><span data-stu-id="cc65a-129">Configure standard notifications on endpoints</span></span>

<span data-ttu-id="cc65a-130">Mithilfe von Gruppenrichtlinien können Sie:</span><span class="sxs-lookup"><span data-stu-id="cc65a-130">You can use Group Policy to:</span></span>

- <span data-ttu-id="cc65a-131">Anzeigen von zusätzlichem, angepassten Text auf Endpunkten, wenn der Benutzer eine Aktion ausführen muss</span><span class="sxs-lookup"><span data-stu-id="cc65a-131">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="cc65a-132">Ausblenden aller Benachrichtigungen auf Endpunkten</span><span class="sxs-lookup"><span data-stu-id="cc65a-132">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="cc65a-133">Ausblenden von Neustartbenachrichtigungen auf Endpunkten</span><span class="sxs-lookup"><span data-stu-id="cc65a-133">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="cc65a-134">Das Ausblenden von Benachrichtigungen kann in Situationen nützlich sein, in denen Sie nicht die gesamte Microsoft Defender Antivirus Schnittstelle ausblenden können.</span><span class="sxs-lookup"><span data-stu-id="cc65a-134">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="cc65a-135">Weitere Informationen finden Sie unter ["Verhindern, dass Benutzer die Microsoft Defender Antivirus-Benutzeroberfläche sehen oder damit interagieren."](prevent-end-user-interaction-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="cc65a-135">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> 

> [!NOTE]
> <span data-ttu-id="cc65a-136">Das Ausblenden von Benachrichtigungen erfolgt nur auf Endpunkten, auf denen die Richtlinie bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="cc65a-136">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="cc65a-137">Benachrichtigungen im Zusammenhang mit Aktionen, die ausgeführt werden müssen (z. B. ein Neustart), werden weiterhin im [Microsoft Endpoint Manager Endpoint Protection Überwachungsdashboard und den Berichten](/configmgr/protect/deploy-use/monitor-endpoint-protection)angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc65a-137">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="cc65a-138">Anweisungen zum Hinzufügen von benutzerdefinierten Kontaktinformationen zu den Benachrichtigungen, die Benutzern auf ihren Computern angezeigt werden, finden Sie unter Anpassen der [Windows-Sicherheit-App für Ihre Organisation.](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)</span><span class="sxs-lookup"><span data-stu-id="cc65a-138">See [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) for instructions to add custom contact information to the notifications that users see on their machines.</span></span>

<span data-ttu-id="cc65a-139">**Verwenden von Gruppenrichtlinien zum Ausblenden von Benachrichtigungen:**</span><span class="sxs-lookup"><span data-stu-id="cc65a-139">**Use Group Policy to hide notifications:**</span></span>

1. <span data-ttu-id="cc65a-140">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **Bearbeiten.**</span><span class="sxs-lookup"><span data-stu-id="cc65a-140">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and click **Edit**.</span></span>

2. <span data-ttu-id="cc65a-141">Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration,** und klicken Sie auf **"Administrative Vorlagen".**</span><span class="sxs-lookup"><span data-stu-id="cc65a-141">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="cc65a-142">Erweitern Sie die Struktur bis Windows **Komponenten > Microsoft Defender Antivirus > Clientschnittstelle.**</span><span class="sxs-lookup"><span data-stu-id="cc65a-142">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span> 

4. <span data-ttu-id="cc65a-143">Doppelklicken Sie auf **"Alle Benachrichtigungen unterdrücken",** und legen Sie die Option auf **"Aktiviert"** fest.</span><span class="sxs-lookup"><span data-stu-id="cc65a-143">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="cc65a-144">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="cc65a-144">Click **OK**.</span></span> <span data-ttu-id="cc65a-145">Dadurch wird verhindert, dass zusätzliche Benachrichtigungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="cc65a-145">This will prevent additional notifications from appearing.</span></span>

<span data-ttu-id="cc65a-146">**Verwenden von Gruppenrichtlinien zum Ausblenden von Neustartbenachrichtigungen:**</span><span class="sxs-lookup"><span data-stu-id="cc65a-146">**Use Group Policy to hide reboot notifications:**</span></span>

1. <span data-ttu-id="cc65a-147">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und klicken Sie auf **"Bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="cc65a-147">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="cc65a-148">Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration.**</span><span class="sxs-lookup"><span data-stu-id="cc65a-148">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="cc65a-149">Klicken Sie auf **"Administrative Vorlagen".**</span><span class="sxs-lookup"><span data-stu-id="cc65a-149">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="cc65a-150">Erweitern Sie die Struktur bis Windows **Komponenten > Microsoft Defender Antivirus > Clientschnittstelle.**</span><span class="sxs-lookup"><span data-stu-id="cc65a-150">Expand the tree to **Windows components > Microsoft Defender Antivirus > Client interface**.</span></span>

5. <span data-ttu-id="cc65a-151">Doppelklicken Sie auf **"Neustartbenachrichtigungen unterdrücken",** und legen Sie die Option auf **"Aktiviert"** fest.</span><span class="sxs-lookup"><span data-stu-id="cc65a-151">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> <span data-ttu-id="cc65a-152">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="cc65a-152">Click **OK**.</span></span> <span data-ttu-id="cc65a-153">Dadurch wird verhindert, dass zusätzliche Benachrichtigungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="cc65a-153">This will prevent additional notifications from appearing.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cc65a-154">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="cc65a-154">Related topics</span></span>

- [<span data-ttu-id="cc65a-155">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="cc65a-155">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="cc65a-156">Konfigurieren der Endbenutzerinteraktion mit Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="cc65a-156">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)
