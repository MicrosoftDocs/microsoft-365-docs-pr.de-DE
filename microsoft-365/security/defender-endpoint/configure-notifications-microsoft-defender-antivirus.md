---
title: Konfigurieren Microsoft Defender Antivirus Benachrichtigungen
description: Erfahren Sie, wie Sie standard- und andere Microsoft Defender Antivirus-Benachrichtigungen auf Endpunkten konfigurieren und anpassen.
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
ms.date: 06/16/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: a7a838bb15cd011b750fbfa3d6df100ddf9f713c
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985408"
---
# <a name="configure-microsoft-defender-antivirus-notifications-that-appear-on-endpoints"></a><span data-ttu-id="78043-104">Konfigurieren Microsoft Defender Antivirus Benachrichtigungen, die auf Endpunkten angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="78043-104">Configure Microsoft Defender Antivirus notifications that appear on endpoints</span></span>

<span data-ttu-id="78043-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="78043-105">**Applies to:**</span></span>

- [<span data-ttu-id="78043-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="78043-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="78043-107">In Windows 10 sind Anwendungsbenachrichtigungen zur Erkennung und Behebung von Schadsoftware robuster, konsistenter und präziser.</span><span class="sxs-lookup"><span data-stu-id="78043-107">In Windows 10, application notifications about malware detection and remediation are more robust, consistent, and concise.</span></span> <span data-ttu-id="78043-108">Microsoft Defender Antivirus Benachrichtigungen werden auf Endpunkten angezeigt, wenn Scans abgeschlossen sind und Bedrohungen erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="78043-108">Microsoft Defender Antivirus notifications appear on endpoints when scans are completed and threats are detected.</span></span> <span data-ttu-id="78043-109">Benachrichtigungen folgen sowohl geplanten als auch manuell ausgelösten Scans.</span><span class="sxs-lookup"><span data-stu-id="78043-109">Notifications follow both scheduled and manually triggered scans.</span></span> <span data-ttu-id="78043-110">Diese Benachrichtigungen werden auch im **Info-Center** angezeigt, und eine Zusammenfassung der Scans und Bedrohungserkennungen wird in regelmäßigen Zeitabständen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="78043-110">These notifications also appear in the **Notification Center**, and a summary of scans and threat detections appear at regular time intervals.</span></span>

<span data-ttu-id="78043-111">Wenn Sie Teil des Sicherheitsteams Ihrer Organisation sind, können Sie konfigurieren, wie Benachrichtigungen auf Endpunkten angezeigt werden, z. B. Benachrichtigungen, die zu einem Systemneustart auffordern oder darauf hinweisen, dass eine Bedrohung erkannt und behoben wurde.</span><span class="sxs-lookup"><span data-stu-id="78043-111">If you're part of your organization's security team, you can configure how notifications appear on endpoints, such as notifications that prompt for a system reboot or that indicate a threat has been detected and remediated.</span></span>

## <a name="configure-antivirus-notifications-using-group-policy-or-the-windows-security-app"></a><span data-ttu-id="78043-112">Konfigurieren von Antivirusbenachrichtigungen mithilfe von Gruppenrichtlinien oder der Windows-Sicherheit-App</span><span class="sxs-lookup"><span data-stu-id="78043-112">Configure antivirus notifications using Group Policy or the Windows Security app</span></span>

<span data-ttu-id="78043-113">Sie können die Anzeige zusätzlicher Benachrichtigungen, z. B. aktuelle Zusammenfassungen zur Bedrohungserkennung, in der [Windows-Sicherheit-App](microsoft-defender-security-center-antivirus.md) und mithilfe von Gruppenrichtlinien konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="78043-113">You can configure the display of additional notifications, such as recent threat detection summaries, in the [Windows Security app](microsoft-defender-security-center-antivirus.md) and with Group Policy.</span></span>

> [!NOTE]
> <span data-ttu-id="78043-114">In Windows 10 Version 1607 wurde das Feature als **erweiterte Benachrichtigungen** bezeichnet und unter **Windows Einstellungen**  >  **Update & Security**  >  **Windows Defender** konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="78043-114">In Windows 10, version 1607 the feature was called **Enhanced notifications** and was configured under **Windows Settings** > **Update & security** > **Windows Defender**.</span></span> <span data-ttu-id="78043-115">In den Gruppenrichtlinieneinstellungen für alle Versionen von Windows 10 wird das Benachrichtigungsfeature als **erweiterte Benachrichtigungen** bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="78043-115">In Group Policy settings for all versions of Windows 10, the notification feature is called **Enhanced notifications**.</span></span>

### <a name="use-group-policy-to-disable-additional-notifications"></a><span data-ttu-id="78043-116">Verwenden von Gruppenrichtlinien zum Deaktivieren zusätzlicher Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="78043-116">Use Group Policy to disable additional notifications</span></span>

1. <span data-ttu-id="78043-117">Öffnen Sie auf dem Computer, der Ihre Gruppenrichtlinie verwaltet, die [Gruppenrichtlinien-Verwaltungskonsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="78043-117">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="78043-118">Klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie dann **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="78043-118">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="78043-119">Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration.**</span><span class="sxs-lookup"><span data-stu-id="78043-119">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4. <span data-ttu-id="78043-120">Wählen Sie **Administrative Vorlagen** aus.</span><span class="sxs-lookup"><span data-stu-id="78043-120">Select **Administrative templates**.</span></span>

5. <span data-ttu-id="78043-121">Erweitern Sie die Struktur bis Windows **Komponenten**  >  **Microsoft Defender Antivirus** > Reporting\*\*.</span><span class="sxs-lookup"><span data-stu-id="78043-121">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > Reporting\*\*.</span></span>

6. <span data-ttu-id="78043-122">Doppelklicken Sie auf **"Erweiterte Benachrichtigungen deaktivieren",** und legen Sie die Option auf **"Aktiviert"** fest.</span><span class="sxs-lookup"><span data-stu-id="78043-122">Double-click **Turn off enhanced notifications**, and set the option to **Enabled**.</span></span> <span data-ttu-id="78043-123">Wählen Sie dann **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="78043-123">Then select **OK**.</span></span> <span data-ttu-id="78043-124">Dadurch wird verhindert, dass zusätzliche Benachrichtigungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="78043-124">This will prevent additional notifications from appearing.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="78043-125">Durch das Deaktivieren zusätzlicher Benachrichtigungen werden kritische Benachrichtigungen, z. B. Warnungen zur Bedrohungserkennung und -behebung, nicht deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="78043-125">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

### <a name="use-the-windows-security-app-to-disable-additional-notifications"></a><span data-ttu-id="78043-126">Verwenden der Windows-Sicherheit-App zum Deaktivieren zusätzlicher Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="78043-126">Use the Windows Security app to disable additional notifications</span></span>

1. <span data-ttu-id="78043-127">Öffnen Sie die Windows-Sicherheit App, indem Sie auf das Schildsymbol in der Taskleiste klicken oder im Startmenü nach **Sicherheit** suchen.</span><span class="sxs-lookup"><span data-stu-id="78043-127">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="78043-128">Wählen Sie die Kachel **"Viren- & Bedrohungsschutz"** (oder das Schildsymbol auf der linken Menüleiste) aus, und wählen Sie dann **"Virus & Bedrohungsschutzeinstellungen"** aus.</span><span class="sxs-lookup"><span data-stu-id="78043-128">Select **Virus & threat protection** tile (or the shield icon on the left menu bar) and, then select **Virus & threat protection settings**</span></span>

3. <span data-ttu-id="78043-129">Scrollen Sie zum Abschnitt **"Benachrichtigungen",** und wählen Sie **"Benachrichtigungseinstellungen ändern" aus.**</span><span class="sxs-lookup"><span data-stu-id="78043-129">Scroll to the **Notifications** section and select **Change notification settings**.</span></span>

4. <span data-ttu-id="78043-130">Ziehen Sie den Schalter auf **"Aus"** oder **"Ein",** um zusätzliche Benachrichtigungen zu deaktivieren oder zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="78043-130">Slide the switch to **Off** or **On** to disable or enable additional notifications.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="78043-131">Durch das Deaktivieren zusätzlicher Benachrichtigungen werden kritische Benachrichtigungen, z. B. Warnungen zur Bedrohungserkennung und -behebung, nicht deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="78043-131">Disabling additional notifications will not disable critical notifications, such as threat detection and remediation alerts.</span></span>

## <a name="configure-standard-notifications-on-endpoints-using-group-policy"></a><span data-ttu-id="78043-132">Konfigurieren von Standardbenachrichtigungen auf Endpunkten mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="78043-132">Configure standard notifications on endpoints using Group Policy</span></span>

<span data-ttu-id="78043-133">Mithilfe von Gruppenrichtlinien können Sie:</span><span class="sxs-lookup"><span data-stu-id="78043-133">You can use Group Policy to:</span></span>

- <span data-ttu-id="78043-134">Anzeigen von zusätzlichem, angepassten Text auf Endpunkten, wenn der Benutzer eine Aktion ausführen muss</span><span class="sxs-lookup"><span data-stu-id="78043-134">Display additional, customized text on endpoints when the user needs to perform an action</span></span>
- <span data-ttu-id="78043-135">Ausblenden aller Benachrichtigungen auf Endpunkten</span><span class="sxs-lookup"><span data-stu-id="78043-135">Hide all notifications on endpoints</span></span>
- <span data-ttu-id="78043-136">Ausblenden von Neustartbenachrichtigungen auf Endpunkten</span><span class="sxs-lookup"><span data-stu-id="78043-136">Hide reboot notifications on endpoints</span></span>

<span data-ttu-id="78043-137">Das Ausblenden von Benachrichtigungen kann in Situationen nützlich sein, in denen Sie nicht die gesamte Microsoft Defender Antivirus Schnittstelle ausblenden können.</span><span class="sxs-lookup"><span data-stu-id="78043-137">Hiding notifications can be useful in situations where you can't hide the entire Microsoft Defender Antivirus interface.</span></span> <span data-ttu-id="78043-138">Weitere Informationen finden Sie unter ["Verhindern, dass Benutzer die Microsoft Defender Antivirus-Benutzeroberfläche sehen oder damit interagieren."](prevent-end-user-interaction-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="78043-138">See [Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface](prevent-end-user-interaction-microsoft-defender-antivirus.md) for more information.</span></span> <span data-ttu-id="78043-139">Das Ausblenden von Benachrichtigungen erfolgt nur auf Endpunkten, auf denen die Richtlinie bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="78043-139">Hiding notifications will only occur on endpoints to which the policy has been deployed.</span></span> <span data-ttu-id="78043-140">Benachrichtigungen im Zusammenhang mit Aktionen, die ausgeführt werden müssen (z. B. ein Neustart), werden weiterhin im [Microsoft Endpoint Manager Endpoint Protection Überwachungsdashboard und den Berichten](/configmgr/protect/deploy-use/monitor-endpoint-protection)angezeigt.</span><span class="sxs-lookup"><span data-stu-id="78043-140">Notifications related to actions that must be taken (such as a reboot) will still appear on the [Microsoft Endpoint Manager Endpoint Protection monitoring dashboard and reports](/configmgr/protect/deploy-use/monitor-endpoint-protection).</span></span> 

<span data-ttu-id="78043-141">Informationen zum Hinzufügen von benutzerdefinierten Kontaktinformationen zu Endpunktbenachrichtigungen finden Sie unter [Anpassen der Windows-Sicherheit-App für Ihre Organisation.](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)</span><span class="sxs-lookup"><span data-stu-id="78043-141">To add custom contact information to endpoint notifications, see [Customize the Windows Security app for your organization](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center).</span></span>

### <a name="use-group-policy-to-hide-notifications"></a><span data-ttu-id="78043-142">Verwenden von Gruppenrichtlinien zum Ausblenden von Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="78043-142">Use Group Policy to hide notifications</span></span>

1. <span data-ttu-id="78043-143">Öffnen Sie auf dem Computer, der Ihre Gruppenrichtlinie verwaltet, die [Gruppenrichtlinien-Verwaltungskonsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="78043-143">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="78043-144">Klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie dann **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="78043-144">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="78043-145">Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration,** und wählen Sie dann **administrative Vorlagen** aus.</span><span class="sxs-lookup"><span data-stu-id="78043-145">In the **Group Policy Management Editor** go to **Computer configuration** and then select **Administrative templates**.</span></span>

4. <span data-ttu-id="78043-146">Erweitern Sie die Struktur bis Windows **Komponenten**  >  **Microsoft Defender Antivirus**  >  **Clientschnittstelle.**</span><span class="sxs-lookup"><span data-stu-id="78043-146">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Client interface**.</span></span> 

5. <span data-ttu-id="78043-147">Doppelklicken Sie auf **"Alle Benachrichtigungen unterdrücken",** und legen Sie die Option auf **"Aktiviert"** fest.</span><span class="sxs-lookup"><span data-stu-id="78043-147">Double-click **Suppress all notifications** and set the option to **Enabled**.</span></span> 

6. <span data-ttu-id="78043-148">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="78043-148">Select **OK**.</span></span> <span data-ttu-id="78043-149">Dadurch wird verhindert, dass zusätzliche Benachrichtigungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="78043-149">This will prevent additional notifications from appearing.</span></span>

### <a name="use-group-policy-to-hide-reboot-notifications"></a><span data-ttu-id="78043-150">Verwenden von Gruppenrichtlinien zum Ausblenden von Neustartbenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="78043-150">Use Group Policy to hide reboot notifications</span></span>

1. <span data-ttu-id="78043-151">Öffnen Sie auf dem Computer, der Ihre Gruppenrichtlinie verwaltet, die [Gruppenrichtlinien-Verwaltungskonsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="78043-151">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="78043-152">Klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie dann **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="78043-152">Right-click the Group Policy Object you want to configure and then select **Edit**.</span></span>

2. <span data-ttu-id="78043-153">Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration.**</span><span class="sxs-lookup"><span data-stu-id="78043-153">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="78043-154">Klicken Sie auf **"Administrative Vorlagen".**</span><span class="sxs-lookup"><span data-stu-id="78043-154">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="78043-155">Erweitern Sie die Struktur bis Windows **Komponenten**  >  **Microsoft Defender Antivirus**  >  **Clientschnittstelle.**</span><span class="sxs-lookup"><span data-stu-id="78043-155">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Client interface**.</span></span>

5. <span data-ttu-id="78043-156">Doppelklicken Sie auf **"Neustartbenachrichtigungen unterdrücken",** und legen Sie die Option auf **"Aktiviert"** fest.</span><span class="sxs-lookup"><span data-stu-id="78043-156">Double-click **Suppresses reboot notifications** and set the option to **Enabled**.</span></span> 

5. <span data-ttu-id="78043-157">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="78043-157">Select **OK**.</span></span> <span data-ttu-id="78043-158">Dadurch wird verhindert, dass zusätzliche Benachrichtigungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="78043-158">This will prevent additional notifications from appearing.</span></span>

