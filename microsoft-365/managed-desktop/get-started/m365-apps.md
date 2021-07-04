---
title: Microsoft 365 Apps for Enterprise
description: Bereitstellen Microsoft 365 Apps, Aktualisieren und Verwalten von Einstellungen
keywords: Änderungsverlauf
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 7b1178312178865face58748a37228f60643d5fc
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287975"
---
# <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="03e9d-104">Microsoft 365 Apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="03e9d-104">Microsoft 365 Apps for enterprise</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="03e9d-105">Erstbereitstellung</span><span class="sxs-lookup"><span data-stu-id="03e9d-105">Initial deployment</span></span>

<span data-ttu-id="03e9d-106">Microsoft Managed Desktop stellt sicher, dass Microsoft 365 Apps for Enterprise (64-Bit) als Teil des Images auf allen [Programmgeräten](../service-description/device-list.md)installiert werden.</span><span class="sxs-lookup"><span data-stu-id="03e9d-106">Microsoft Managed Desktop ensures that Microsoft 365 Apps for enterprise (64-bit) are installed as a part of the image on all [program devices](../service-description/device-list.md).</span></span> <span data-ttu-id="03e9d-107">Alle folgenden Anwendungen sollten auf dem Gerät vorhanden sein, wenn es bereitgestellt wird:</span><span class="sxs-lookup"><span data-stu-id="03e9d-107">All of the following applications should be present on the device when it's delivered:</span></span>

- <span data-ttu-id="03e9d-108">Word</span><span class="sxs-lookup"><span data-stu-id="03e9d-108">Word</span></span>
- <span data-ttu-id="03e9d-109">Excel</span><span class="sxs-lookup"><span data-stu-id="03e9d-109">Excel</span></span>
- <span data-ttu-id="03e9d-110">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="03e9d-110">PowerPoint</span></span>
- <span data-ttu-id="03e9d-111">Outlook</span><span class="sxs-lookup"><span data-stu-id="03e9d-111">Outlook</span></span>
- <span data-ttu-id="03e9d-112">Publisher</span><span class="sxs-lookup"><span data-stu-id="03e9d-112">Publisher</span></span>
- <span data-ttu-id="03e9d-113">Zugriff</span><span class="sxs-lookup"><span data-stu-id="03e9d-113">Access</span></span>
- <span data-ttu-id="03e9d-114">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="03e9d-114">Skype for Business</span></span>
- <span data-ttu-id="03e9d-115">OneNote</span><span class="sxs-lookup"><span data-stu-id="03e9d-115">OneNote</span></span>

<span data-ttu-id="03e9d-116">Dieser Ansatz minimiert die Auswirkungen auf das Netzwerk und stellt sicher, dass Benutzer produktiv sein können, sobald sie ihr Gerät erhalten.</span><span class="sxs-lookup"><span data-stu-id="03e9d-116">This approach minimizes network impact and ensures that users can be productive as soon as they receive their device.</span></span> <span data-ttu-id="03e9d-117">Anschließend stellen wir weitere Richtlinien auf verwalteten Geräten bereit, um die Anwendungen für die Verwendung einzurichten.</span><span class="sxs-lookup"><span data-stu-id="03e9d-117">We then deploy more policies to managed devices to set up the applications for use.</span></span>

> [!NOTE]
> <span data-ttu-id="03e9d-118">Microsoft Teams wird separat von Microsoft 365 Apps for Enterprise bereitgestellt und ist nicht im Basisimage enthalten.</span><span class="sxs-lookup"><span data-stu-id="03e9d-118">Microsoft Teams is deployed separately from Microsoft 365 Apps for enterprise and is not included in the base image.</span></span> 

### <a name="available-deployment-to-users"></a><span data-ttu-id="03e9d-119">Verfügbare Bereitstellung für Benutzer</span><span class="sxs-lookup"><span data-stu-id="03e9d-119">Available deployment to users</span></span>

<span data-ttu-id="03e9d-120">Wenn ein Benutzer aus irgendeinem Grund keine Microsoft 365 Apps auf seinem Gerät hat, können Sie ein Paket verwenden, um das Gerät in den erwarteten Zustand zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="03e9d-120">If a user does not have Microsoft 365 Apps on their device for any reason, you can use a package to return the device to its expected state.</span></span> <span data-ttu-id="03e9d-121">Fügen Sie den Benutzer der Gruppe **"Modern Workplace-Office-Office365_Install"** hinzu, und die Apps stehen ihnen im Unternehmensportal zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="03e9d-121">Add the user to the **Modern Workplace-Office-Office365_Install** group and the apps will become available to them in the Company Portal.</span></span>

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a><span data-ttu-id="03e9d-122">Microsoft 365 Apps for Enterprise (32-Bit)</span><span class="sxs-lookup"><span data-stu-id="03e9d-122">Microsoft 365 Apps for enterprise (32-bit)</span></span>

<span data-ttu-id="03e9d-123">Microsoft Managed Desktop unterstützt die Bereitstellung der 32-Bit-Version von M365 Apps for Enterprise nicht.</span><span class="sxs-lookup"><span data-stu-id="03e9d-123">Microsoft Managed Desktop doesn't support the deployment of the 32-bit version of M365 Apps for enterprise.</span></span>

## <a name="updates-to-microsoft-365-apps"></a><span data-ttu-id="03e9d-124">Updates für Microsoft 365 Apps</span><span class="sxs-lookup"><span data-stu-id="03e9d-124">Updates to Microsoft 365 Apps</span></span>

<span data-ttu-id="03e9d-125">Microsoft 365 Apps werden im [monatlichen Enterprise Kanal](/deployoffice/overview-update-channels#monthly-enterprise-channel-overview)aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="03e9d-125">Microsoft 365 Apps are set to update on the [Monthly Enterprise Channel](/deployoffice/overview-update-channels#monthly-enterprise-channel-overview).</span></span> <span data-ttu-id="03e9d-126">Diese Vorgehensweise bietet Ihren Benutzern jeden Monat neue Office Features, aber sie erhalten nur ein Update pro Monat nach einem vorhersagbaren Veröffentlichungszeitplan.</span><span class="sxs-lookup"><span data-stu-id="03e9d-126">This practice provides your users with new Office features each month, but they'll receive just one update per month on a predictable release schedule.</span></span> <span data-ttu-id="03e9d-127">Updates werden am zweiten Dienstag des Monats veröffentlicht. Diese Updates können Funktions-, Sicherheits- und Qualitätsupdates enthalten.</span><span class="sxs-lookup"><span data-stu-id="03e9d-127">Updates are released on the second Tuesday of the month; these updates can include feature, security, and quality updates.</span></span> <span data-ttu-id="03e9d-128">Diese Updates erfolgen automatisch und werden direkt aus dem Office CDN für diesen spezifischen Kanal abgerufen.</span><span class="sxs-lookup"><span data-stu-id="03e9d-128">These updates occur automatically and are pulled directly from the Office CDN for that specific channel.</span></span>

<span data-ttu-id="03e9d-129">Microsoft Managed Desktop staturiert jede Version, um potenzielle Probleme in Ihrer Umgebung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="03e9d-129">Microsoft Managed Desktop staggers each release to identify any potential issues in your environment.</span></span> <span data-ttu-id="03e9d-130">Wir führen das Rollout 28 Tage nach der Veröffentlichung der Microsoft 365 App-Produktgruppe durch.</span><span class="sxs-lookup"><span data-stu-id="03e9d-130">We complete the rollout 28 days after the release from the Microsoft 365 App product group.</span></span> <span data-ttu-id="03e9d-131">Microsoft Managed Desktop plant Updateversionen für verschiedene Gruppen, um Zeit für Überprüfungen und Tests wie folgt zu lassen:</span><span class="sxs-lookup"><span data-stu-id="03e9d-131">Microsoft Managed Desktop schedules update releases to different groups to allow time for validation and testing as follows:</span></span> 

- <span data-ttu-id="03e9d-132">Test: null Tage</span><span class="sxs-lookup"><span data-stu-id="03e9d-132">Test: zero days</span></span>
- <span data-ttu-id="03e9d-133">First: zero days</span><span class="sxs-lookup"><span data-stu-id="03e9d-133">First: zero days</span></span>
- <span data-ttu-id="03e9d-134">Schnell: 3 Tage</span><span class="sxs-lookup"><span data-stu-id="03e9d-134">Fast: 3 days</span></span>
- <span data-ttu-id="03e9d-135">Allgemein: 7 Tage</span><span class="sxs-lookup"><span data-stu-id="03e9d-135">Broad: 7 days</span></span>

<span data-ttu-id="03e9d-136">Microsoft Managed Desktop legt einen [Stichtag](/deployoffice/configure-update-settings-microsoft-365-apps) für sieben Tage für Updates für Geräte fest.</span><span class="sxs-lookup"><span data-stu-id="03e9d-136">Microsoft Managed Desktop sets a seven-day [update deadline](/deployoffice/configure-update-settings-microsoft-365-apps) for devices.</span></span> <span data-ttu-id="03e9d-137">Sobald das Update verfügbar ist, muss es innerhalb von sieben Tagen installiert werden.</span><span class="sxs-lookup"><span data-stu-id="03e9d-137">Once the update is available, it must be installed within seven days.</span></span> <span data-ttu-id="03e9d-138">Benutzer werden [benachrichtigt,](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) dass Updates an verschiedenen Stellen erforderlich sind: die Anwendung, 12 Stunden vor dem Stichtag in der Taskleiste des Systems, und sie erhalten eine 15-minütige Warnung vor dem Stichtag.</span><span class="sxs-lookup"><span data-stu-id="03e9d-138">Users are [notified](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) that updates are required in several locations: the application, in the system tray 12 hours prior to the deadline, and they receive a 15-minute warning prior to the deadline.</span></span> <span data-ttu-id="03e9d-139">Alle Microsoft 365 Apps müssen geschlossen werden, damit das Update abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="03e9d-139">All Microsoft 365 Apps must be closed for the update to complete.</span></span>

### <a name="pausing-or-rolling-back-an-update"></a><span data-ttu-id="03e9d-140">Anhalten oder Zurücksetzen eines Updates</span><span class="sxs-lookup"><span data-stu-id="03e9d-140">Pausing or rolling back an update</span></span>

<span data-ttu-id="03e9d-141">Wenn Sie Microsoft 365 App-Update aus irgendeinem Grund anhalten oder zurücksetzen müssen, stellen Sie eine [Administrator-Supportanfrage](../working-with-managed-desktop/admin-support.md) über das Microsoft Managed Desktop Portal.</span><span class="sxs-lookup"><span data-stu-id="03e9d-141">If you need to pause or roll back Microsoft 365 App update for any reason, file an [admin support request](../working-with-managed-desktop/admin-support.md) through the Microsoft Managed Desktop portal.</span></span>

<span data-ttu-id="03e9d-142">Während einer Veröffentlichung überwacht Microsoft Managed Desktop die Fehlerraten aller Microsoft 365 Apps.</span><span class="sxs-lookup"><span data-stu-id="03e9d-142">During a release, Microsoft Managed Desktop monitors the error rates of all Microsoft 365 Apps.</span></span> <span data-ttu-id="03e9d-143">Wenn wir einen erheblichen Qualitätsunterschied zwischen der neuen Version und dem Vorgänger feststellen, können wir Sie über das Microsoft Managed Desktop Admin-Portal kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="03e9d-143">If we note a significant difference in quality between the new release and its predecessor, we might contact you through the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="03e9d-144">Je nach Schweregrad werden wir entweder fragen, ob Sie die Version anhalten möchten, oder Sie darüber informieren, dass wir Maßnahmen zur Behebung eines Problems ergriffen haben.</span><span class="sxs-lookup"><span data-stu-id="03e9d-144">Depending on the severity, we will either ask if you want to pause the release or inform you that we have taken action to mitigate an issue.</span></span> 

### <a name="delivery-optimization"></a><span data-ttu-id="03e9d-145">Übermittlungsoptimierung</span><span class="sxs-lookup"><span data-stu-id="03e9d-145">Delivery optimization</span></span>

<span data-ttu-id="03e9d-146">Die Übermittlungsoptimierung ist eine Peer-to-Peer-Verteilungstechnologie, die in Windows 10 verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="03e9d-146">Delivery Optimization is a peer-to-peer distribution technology available in Windows 10.</span></span> <span data-ttu-id="03e9d-147">Damit können Geräte Inhalte, z. B. Updates, freigeben, die die Geräte über das Internet von Microsoft heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="03e9d-147">It allows devices to share content, such as updates, that the devices have downloaded from Microsoft over the internet.</span></span> <span data-ttu-id="03e9d-148">Die Verwendung kann dazu beitragen, die Netzwerkbandbreite zu reduzieren, da ein Gerät Teile des Updates von einem anderen Gerät im lokalen Netzwerk abrufen kann, anstatt das Update vollständig von Microsoft herunterladen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="03e9d-148">Using it can help reduce network bandwidth because a device can get portions of the update from another device on its local network instead of having to download the update completely from Microsoft.</span></span>

<span data-ttu-id="03e9d-149">[Die Übermittlungsoptimierung](/deployoffice/delivery-optimization) ist auf Geräten mit der Windows 10 Enterprise oder Windows 10 Education Editionen standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="03e9d-149">[Delivery Optimization](/deployoffice/delivery-optimization) is enabled by default on devices running the Windows 10 Enterprise or Windows 10 Education editions.</span></span> 

## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="03e9d-150">von Microsoft Managed Desktop verwaltete Einstellungen</span><span class="sxs-lookup"><span data-stu-id="03e9d-150">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="03e9d-151">Microsoft verwaltet einige Einstellungen als Teil des Diensts.</span><span class="sxs-lookup"><span data-stu-id="03e9d-151">Microsoft manages some settings as a part of the service.</span></span> <span data-ttu-id="03e9d-152">Microsoft Managed Desktop verwaltet keine Office Sicherheitsgrundwerte, aber Sie können einen selbst festlegen, indem Sie die Anweisungen im [Abschnitt Einstellungen Verwalten](#settings-you-manage) befolgen.</span><span class="sxs-lookup"><span data-stu-id="03e9d-152">Microsoft Managed Desktop doesn't manage an Office Security baseline but you can set one yourself by following the guidance in the [Settings you manage](#settings-you-manage) section.</span></span>

### <a name="update-settings"></a><span data-ttu-id="03e9d-153">Einstellungen aktualisieren</span><span class="sxs-lookup"><span data-stu-id="03e9d-153">Update settings</span></span>

<span data-ttu-id="03e9d-154">Microsoft Managed Desktop verwaltet alle [Updateeinstellungen](/deployoffice/configure-update-settings-microsoft-365-apps) für verwaltete Geräte, und Sie sollten diese Einstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="03e9d-154">Microsoft Managed Desktop maintains all [update settings](/deployoffice/configure-update-settings-microsoft-365-apps) for managed devices and you should modify these settings.</span></span>

### <a name="set-updates-to-occur-automatically"></a><span data-ttu-id="03e9d-155">Festlegen der automatischen Durchführung von Updates</span><span class="sxs-lookup"><span data-stu-id="03e9d-155">Set updates to occur automatically</span></span>

<span data-ttu-id="03e9d-156">**Standardwert:** Aktiviert</span><span class="sxs-lookup"><span data-stu-id="03e9d-156">**Default value**: Enabled</span></span>

<span data-ttu-id="03e9d-157">Diese Richtlinie wird konfiguriert, um sicherzustellen, dass alle Office Geräte aus der Cloud auf dem neuesten Stand gehalten werden können.</span><span class="sxs-lookup"><span data-stu-id="03e9d-157">This policy is configured in order to ensure that all Office devices can be kept up to date from the cloud.</span></span> 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a><span data-ttu-id="03e9d-158">Festlegen eines Stichtags für die Anwendung von Updates</span><span class="sxs-lookup"><span data-stu-id="03e9d-158">Set a deadline when updates have to be applied</span></span>

<span data-ttu-id="03e9d-159">**Standardwert:** 7 Tage</span><span class="sxs-lookup"><span data-stu-id="03e9d-159">**Default value**: 7 days</span></span>

<span data-ttu-id="03e9d-160">Die **UpdateDeadline-Richtlinie** wird verwendet, um die Karenzzeit zu konfigurieren, über die Benutzer verfügen, bevor ein Update auf dem Gerät erzwungen wird.</span><span class="sxs-lookup"><span data-stu-id="03e9d-160">The **UpdateDeadline** policy is used to configure the grace period which users have before an update is enforced on the device.</span></span> <span data-ttu-id="03e9d-161">Diese Stichtagsrichtlinie löst auch [Benachrichtigungen](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) an den Benutzer aus, um sie über die auf dem Gerät erforderlichen Änderungen zu informieren.</span><span class="sxs-lookup"><span data-stu-id="03e9d-161">This deadline policy also triggers [notifications](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) to the user to inform them of the changes required on their device.</span></span>  

### <a name="defer-updates-on-a-device-for-a-period"></a><span data-ttu-id="03e9d-162">Zurückstellen von Updates auf einem Gerät für einen Bestimmten Zeitraum</span><span class="sxs-lookup"><span data-stu-id="03e9d-162">Defer updates on a device for a period</span></span>

<span data-ttu-id="03e9d-163">Diese Richtlinie ist für jede Updateverwaltungsgerätegruppe unterschiedlich konfiguriert und für Microsoft Managed Desktop erforderlich, um ihre Updateziele zu erreichen:</span><span class="sxs-lookup"><span data-stu-id="03e9d-163">This policy is configured differently for each update management device group and is required for Microsoft Managed Desktop to meet its update targets:</span></span>  

- <span data-ttu-id="03e9d-164">Test: null Tage</span><span class="sxs-lookup"><span data-stu-id="03e9d-164">Test: zero days</span></span>
- <span data-ttu-id="03e9d-165">First: zero days</span><span class="sxs-lookup"><span data-stu-id="03e9d-165">First: zero days</span></span>
- <span data-ttu-id="03e9d-166">Schnell 7 Tage</span><span class="sxs-lookup"><span data-stu-id="03e9d-166">Fast 7 days</span></span>
- <span data-ttu-id="03e9d-167">Allgemein: 21 Tage</span><span class="sxs-lookup"><span data-stu-id="03e9d-167">Broad: 21 days</span></span>

### <a name="update-notifications-settings"></a><span data-ttu-id="03e9d-168">Aktualisieren von Benachrichtigungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="03e9d-168">Update notifications settings</span></span>

<span data-ttu-id="03e9d-169">**Standardwert:** False</span><span class="sxs-lookup"><span data-stu-id="03e9d-169">**Default value**: False</span></span>

<span data-ttu-id="03e9d-170">Die Einstellung "Updatebenachrichtigungen ausblenden" ist auf Microsoft Managed Desktop Geräten auf **"False"** festgelegt, um benutzern die bestmögliche Updateerfahrung zu bieten, indem sie [benachrichtigt](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) werden, wenn Updates erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="03e9d-170">The "hide update notifications" setting is set to **False** on Microsoft Managed Desktop devices to provide the best update experience for users by [notifying](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) them when updates are required.</span></span>

### <a name="specify-a-location-to-look-for-updates"></a><span data-ttu-id="03e9d-171">Angeben eines Orts für die Suche nach Updates</span><span class="sxs-lookup"><span data-stu-id="03e9d-171">Specify a location to look for updates</span></span>

<span data-ttu-id="03e9d-172">**Standardwert:** Monatlicher Enterprise Channel</span><span class="sxs-lookup"><span data-stu-id="03e9d-172">**Default value**: Monthly Enterprise Channel</span></span>

<span data-ttu-id="03e9d-173">Eine Kombination der **UpdatePath-** und **UpdateChannel-Richtlinien** wird nach Bedarf verwendet, um den Updatezeitplan zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="03e9d-173">A combination of the **UpdatePath** and **UpdateChannel** policies is used as needed to achieve the update schedule.</span></span> <span data-ttu-id="03e9d-174">Diese Richtlinien werden festgelegt, um sicherzustellen, dass alle Office Geräte Updates direkt vom CDN für den monatlichen Enterprise-Kanal erhalten.</span><span class="sxs-lookup"><span data-stu-id="03e9d-174">These policies are set to ensure that all Office devices receive updates directly from the CDN for the Monthly Enterprise Channel.</span></span>

### <a name="specify-the-target-version-of-microsoft-365-apps"></a><span data-ttu-id="03e9d-175">Angeben der Zielversion von Microsoft 365 Apps</span><span class="sxs-lookup"><span data-stu-id="03e9d-175">Specify the Target Version of Microsoft 365 Apps</span></span>

<span data-ttu-id="03e9d-176">Die Zielversionsrichtlinie wird manchmal von Microsoft Managed Desktop zum Zurücksetzen oder Anheften einer bestimmten Version von Office verwendet.</span><span class="sxs-lookup"><span data-stu-id="03e9d-176">The Target Version policy is sometimes used by Microsoft Managed Desktop in order to roll back or pin a specific version of Office.</span></span> 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a><span data-ttu-id="03e9d-177">Ausblenden der Option zum Aktivieren oder Deaktivieren Office automatischen Updates</span><span class="sxs-lookup"><span data-stu-id="03e9d-177">Hide the option to enable or disable Office automatic updates</span></span>

<span data-ttu-id="03e9d-178">**Standardwert:** Aktiviert</span><span class="sxs-lookup"><span data-stu-id="03e9d-178">**Default value**: Enabled</span></span>

<span data-ttu-id="03e9d-179">Diese Einstellung ist erforderlich, damit Microsoft Managed Desktop ihre Updateziele für Microsoft 365-Anwendungen erfüllen können.</span><span class="sxs-lookup"><span data-stu-id="03e9d-179">This setting is required for Microsoft Managed Desktop to meet its update targets for Microsoft 365 Applications.</span></span> 

### <a name="first-run-settings"></a><span data-ttu-id="03e9d-180">Einstellungen für die erstausführung</span><span class="sxs-lookup"><span data-stu-id="03e9d-180">First run settings</span></span> 

<span data-ttu-id="03e9d-181">Es gibt mehrere Einstellungen, die sich auf das Verhalten auswirken, wenn Office zum ersten Mal ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="03e9d-181">There are several settings that affect the behavior the first time Office is run.</span></span>

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a><span data-ttu-id="03e9d-182">Akzeptieren der Lizenzbedingungen im Namen des Endbenutzers</span><span class="sxs-lookup"><span data-stu-id="03e9d-182">Accept the license terms on behalf of the end user</span></span>

<span data-ttu-id="03e9d-183">**Standardwert:** Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="03e9d-183">**Default value**: Disabled</span></span>

<span data-ttu-id="03e9d-184">Wenn ein Benutzer ein Microsoft 365 App zum ersten Mal öffnet, wird er aufgefordert, die Lizenzbedingungen zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="03e9d-184">The first time a user opens a Microsoft 365 App, they are prompted to accept the license terms.</span></span> <span data-ttu-id="03e9d-185">Wenn Sie die Lizenzbedingungen im Namen Ihrer Benutzer akzeptieren möchten, stellen Sie eine Serviceanfrage beim Microsoft Managed Desktop Operations-Team, in dem Sie die Aktivierung dieser Einstellung anfordern.</span><span class="sxs-lookup"><span data-stu-id="03e9d-185">If you want to accept the license terms on behalf of your users, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

### <a name="suppress-outlook-mobile-check-box"></a><span data-ttu-id="03e9d-186">Kontrollkästchen "Outlook Mobile unterdrücken"</span><span class="sxs-lookup"><span data-stu-id="03e9d-186">Suppress Outlook mobile check box</span></span>

<span data-ttu-id="03e9d-187">**Standardwert:** Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="03e9d-187">**Default value**: Disabled</span></span>

<span data-ttu-id="03e9d-188">Wenn ein Benutzer Outlook zum ersten Mal öffnet, wird er aufgefordert, Outlook Mobile zu installieren.</span><span class="sxs-lookup"><span data-stu-id="03e9d-188">The first time a user opens Outlook they are prompted to install Outlook Mobile.</span></span> <span data-ttu-id="03e9d-189">Wenn Sie nicht möchten, dass Ihren Benutzern dieses Kontrollkästchen angezeigt wird, senden Sie eine Serviceanfrage beim Microsoft Managed Desktop Operations-Team, in dem sie aufgefordert werden, diese Einstellung für Ihre Geräte zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="03e9d-189">If you don’t want your users to see that check box, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled for your devices.</span></span> 

## <a name="other-settings"></a><span data-ttu-id="03e9d-190">Weitere Einstellungen</span><span class="sxs-lookup"><span data-stu-id="03e9d-190">Other settings</span></span>

<span data-ttu-id="03e9d-191">Es gibt weitere Microsoft 365 App-Einstellungen, die Microsoft Managed Desktop optional in Ihrem Auftrag konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="03e9d-191">There are other Microsoft 365 App settings which Microsoft Managed Desktop can optionally configure on your behalf.</span></span> 

### <a name="disable-personal-onedrive"></a><span data-ttu-id="03e9d-192">Persönliche OneDrive deaktivieren</span><span class="sxs-lookup"><span data-stu-id="03e9d-192">Disable Personal OneDrive</span></span>

<span data-ttu-id="03e9d-193">**Standardwert:** Deaktiviert</span><span class="sxs-lookup"><span data-stu-id="03e9d-193">**Default value**: Disabled</span></span>

<span data-ttu-id="03e9d-194">Einige Organisationen sind darüber besorgt, dass Benutzer zugriff auf unternehmenseigene und persönliche Dateien auf ihren Geräten haben.</span><span class="sxs-lookup"><span data-stu-id="03e9d-194">Some organizations are concerned about users having access to both corporate and personal files on their devices.</span></span> <span data-ttu-id="03e9d-195">Sie können eine Serviceanfrage beim Microsoft Managed Desktop Operations-Team einreichen und diese Einstellung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="03e9d-195">You can file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

## <a name="settings-you-manage"></a><span data-ttu-id="03e9d-196">Einstellungen, die Sie verwalten</span><span class="sxs-lookup"><span data-stu-id="03e9d-196">Settings you manage</span></span>

<span data-ttu-id="03e9d-197">Es gibt viele andere Richtlinien, die Microsoft Managed Desktop noch nicht als Teil unseres Diensts festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="03e9d-197">There are many other policies which Microsoft Managed Desktop does not yet set as a part of our service.</span></span> <span data-ttu-id="03e9d-198">Sie können diese Richtlinien mithilfe von Microsoft Intune konfigurieren, die den [Office Cloudrichtliniendienst](/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) verwendet.</span><span class="sxs-lookup"><span data-stu-id="03e9d-198">You can configure these policies by using Microsoft Intune, which uses the [Office Cloud Policy](/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) service.</span></span> <span data-ttu-id="03e9d-199">Führen Sie die folgenden Schritte aus, um diese Richtlinien festzulegen:</span><span class="sxs-lookup"><span data-stu-id="03e9d-199">To set these policies, follow these steps:</span></span>

1. <span data-ttu-id="03e9d-200">Melden Sie sich beim Microsoft Endpoint Manager Admin Center an.</span><span class="sxs-lookup"><span data-stu-id="03e9d-200">Sign in to the Microsoft Endpoint Manager admin center.</span></span>
2. <span data-ttu-id="03e9d-201">Auswählen **von Apps > Richtlinien für Office Apps > Erstellen**</span><span class="sxs-lookup"><span data-stu-id="03e9d-201">Select **Apps > Policies for Office apps > Create**</span></span>
3. <span data-ttu-id="03e9d-202">Führen Sie auf der Seite **"Richtlinienkonfiguration erstellen"** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="03e9d-202">On the **Create policy** configuration page, do the following:</span></span>
    - <span data-ttu-id="03e9d-203">Geben Sie einen Namen ein.</span><span class="sxs-lookup"><span data-stu-id="03e9d-203">Enter a name.</span></span>
    - <span data-ttu-id="03e9d-204">Geben Sie eine Beschreibung an (optional).</span><span class="sxs-lookup"><span data-stu-id="03e9d-204">Provide a description (optional).</span></span>
    - <span data-ttu-id="03e9d-205">Wählen Sie in **Aufgaben** aus, ob diese Richtlinie für alle Benutzer von Microsoft 365 Apps for Enterprise oder nur für Benutzer gilt, die anonym über Office für das Web auf Dokumente zugreifen.</span><span class="sxs-lookup"><span data-stu-id="03e9d-205">In **assignments**, choose whether this policy applies to all users of Microsoft 365 Apps for enterprise, or just to users who anonymously access documents using Office for the web.</span></span>
    - <span data-ttu-id="03e9d-206">Wählen Sie die AAD-basierte Sicherheitsgruppe aus, die der Richtlinienkonfiguration zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="03e9d-206">Select the AAD-based security group that is assigned to the policy configuration.</span></span> <span data-ttu-id="03e9d-207">Jede Richtlinienkonfiguration kann nur einer Gruppe zugewiesen werden, und jeder Gruppe kann nur eine Richtlinienkonfiguration zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="03e9d-207">Each policy configuration can only be assigned to one group, and each group can only be assigned one policy configuration.</span></span>
    - <span data-ttu-id="03e9d-208">Konfigurieren Sie die Richtlinieneinstellungen, die in der Richtlinienkonfiguration enthalten sein sollen.</span><span class="sxs-lookup"><span data-stu-id="03e9d-208">Configure the policy settings to be included in the policy configuration.</span></span> <span data-ttu-id="03e9d-209">Sie können nach dem Namen der Richtlinieneinstellung suchen, um die Richtlinieneinstellung zu finden, die Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="03e9d-209">You can search on the policy setting name to find the policy setting that you want to configure.</span></span> <span data-ttu-id="03e9d-210">Sie können auch nach der Anwendung filtern, ob es sich bei der Richtlinie um eine empfohlene Sicherheitsbaseline handelt und ob die Richtlinie konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="03e9d-210">You can also filter on the application, on whether the policy is a recommended security baseline, and on whether the policy has been configured.</span></span> <span data-ttu-id="03e9d-211">Die Plattformspalte gibt an, ob die Richtlinie auf Microsoft 365 Apps for Enterprise für Windows Geräte, Office für das Web oder alle angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="03e9d-211">The platform column indicates whether the policy is applied to Microsoft 365 Apps for enterprise for Windows devices, Office for the web, or all.</span></span>
4. <span data-ttu-id="03e9d-212">Nachdem Sie Ihre Auswahl getroffen haben, wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="03e9d-212">After you have made your selections, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="03e9d-213">Office Konfigurationsrichtlinien unterstützen nur die benutzerbasierte Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="03e9d-213">Office Configuration Policies only support user-based deployment</span></span>
