---
title: Abrufen von Vorfallbenachrichtigungen in Microsoft 365 Defender
description: Informationen zum Erstellen von Regeln zum Abrufen von e-Mail-Benachrichtigungen für Vorfälle in Microsoft 365 Defender
keywords: Vorfall, e-Mail, e-Mail-notfications, konfigurieren, Benutzer, Postfach, e-Mail, Vorfälle
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 3af1dcfec165c88a18cbc0d8cbf6866bb6398adc
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668322"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="ef0dd-104">Abrufen von Vorfallbenachrichtigungen per e-Mail</span><span class="sxs-lookup"><span data-stu-id="ef0dd-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!IMPORTANT]
> <span data-ttu-id="ef0dd-105">Das Feature e-Mail-Benachrichtigungen für Vorfälle befindet sich derzeit in der öffentlichen Vorschau.</span><span class="sxs-lookup"><span data-stu-id="ef0dd-105">The email notifications for incidents feature is currently in public preview.</span></span> <span data-ttu-id="ef0dd-106">Einige Informationen zu dieser Funktion können sich vor der kommerziellen Verfügbarkeit ändern.</span><span class="sxs-lookup"><span data-stu-id="ef0dd-106">Some information about this feature may change before commercial availability.</span></span> <span data-ttu-id="ef0dd-107">Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.</span><span class="sxs-lookup"><span data-stu-id="ef0dd-107">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="ef0dd-108">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="ef0dd-108">**Applies to:**</span></span>
- <span data-ttu-id="ef0dd-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ef0dd-109">Microsoft 365 Defender</span></span>

<span data-ttu-id="ef0dd-110">Sie können Microsoft 365 Defender so einrichten, dass Sie jedes Mal, wenn neue Vorfälle oder neue Updates für vorhandene Vorfälle vorliegen, per e-Mail benachrichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="ef0dd-110">You can set up Microsoft 365 Defender to notify you by email every time there are new incidents or new updates to existing incidents.</span></span> 

<span data-ttu-id="ef0dd-111">Sie können auswählen, ob Benachrichtigungen basierend auf dem Schweregrad des Vorfalls oder nach Gerätegruppen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ef0dd-111">You can choose to get notifications based on incident severity or by device group.</span></span> <span data-ttu-id="ef0dd-112">Sie können auch festlegen, dass eine Benachrichtigung nur beim ersten Update pro Vorfall abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ef0dd-112">You can also choose to get a notification only on the first update per incident.</span></span>

<span data-ttu-id="ef0dd-113">Sie können Empfänger in e-Mail-Benachrichtigungen hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="ef0dd-113">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="ef0dd-114">Neu hinzugefügte Empfänger werden über Vorfälle benachrichtigt, nachdem Sie hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="ef0dd-114">Newly added recipients get notified about incidents after they're added.</span></span> 

<span data-ttu-id="ef0dd-115">Die e-Mail-Benachrichtigung enthält wichtige Details zu dem Vorfall, beispielsweise den Vorfall Namen, den Schweregrad und die Kategorien, unter anderem.</span><span class="sxs-lookup"><span data-stu-id="ef0dd-115">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="ef0dd-116">Sie können auch direkt zu Vorfälle wechseln, damit Sie sofort mit der Untersuchung beginnen können.</span><span class="sxs-lookup"><span data-stu-id="ef0dd-116">You can also directly go to incidents so you can start your investigation right away.</span></span> <span data-ttu-id="ef0dd-117">Weitere Informationen zur Untersuchung von Vorfällen finden Sie unter [untersuchen von Vorfällen in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents).</span><span class="sxs-lookup"><span data-stu-id="ef0dd-117">For more on investigating incidents, see [Investigate incidents in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents).</span></span>

>[!NOTE]
><span data-ttu-id="ef0dd-118">Sie benötigen die Berechtigungen "Sicherheitseinstellungen verwalten" zum Konfigurieren von Einstellungen für e-Mail-Benachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="ef0dd-118">You need 'Manage security settings' permissions to configure email notification settings.</span></span> <span data-ttu-id="ef0dd-119">Wenn Sie sich für die Verwendung der grundlegenden Berechtigungsverwaltung entschieden haben, können Benutzer mit Sicherheitsadministrator-oder globalen Administrator Rollen e-Mail-Benachrichtigungen für Sie konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ef0dd-119">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="ef0dd-120">Wenn Ihre Organisation rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) verwendet, können Sie Benachrichtigungen nur basierend auf Gerätegruppen erstellen, bearbeiten, löschen und empfangen, die Sie verwalten dürfen.</span><span class="sxs-lookup"><span data-stu-id="ef0dd-120">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-rules-for-incident-notifications"></a><span data-ttu-id="ef0dd-121">Erstellen von Regeln für Vorfallbenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="ef0dd-121">Create rules for incident notifications</span></span>

<span data-ttu-id="ef0dd-122">Um Ihre erste e-Mail-Benachrichtigung für Vorfälle einzurichten, erstellen Sie eine neue Regel und passen die Einstellungen für e-Mail-Benachrichtigungen an.</span><span class="sxs-lookup"><span data-stu-id="ef0dd-122">To set up your first email notification for incidents, create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="ef0dd-123">Wählen Sie im Navigationsbereich die Option **Einstellungen** für  >  **Vorfall-e-Mail-Benachrichtigungen** aus.</span><span class="sxs-lookup"><span data-stu-id="ef0dd-123">In the navigation pane, select **Settings** > **Incident email notifications**.</span></span>
2. <span data-ttu-id="ef0dd-124">Wählen Sie **Element hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="ef0dd-124">Select **Add item**.</span></span>
3. <span data-ttu-id="ef0dd-125">Geben Sie der Regel einen Namen in **Name** , und geben Sie eine **Beschreibung** an.</span><span class="sxs-lookup"><span data-stu-id="ef0dd-125">Give the rule a name in **Name** and supply a **Description**.</span></span>

    ![Fenster "Regel erstellen" für Vorfall-e-Mail notifs](../../media/incidentemailnotif1.png) 
4. <span data-ttu-id="ef0dd-127">Wählen Sie **weiter** aus, um zu **Benachrichtigungseinstellungen** zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="ef0dd-127">Select **Next** to go to **Notification settings**.</span></span> <span data-ttu-id="ef0dd-128">Hier können Sie Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="ef0dd-128">Here you can specify:</span></span>
    - <span data-ttu-id="ef0dd-129">**Warnungsschweregrad** – wählen Sie den Warnungsschweregrad aus, der eine Vorfall Benachrichtigung auslösen wird.</span><span class="sxs-lookup"><span data-stu-id="ef0dd-129">**Alert severity** - Choose the alert severity that will trigger an incident notification.</span></span> <span data-ttu-id="ef0dd-130">Wenn Sie beispielsweise nur über Vorfälle mit hohem Schweregrad informiert werden möchten, wählen Sie hoch.</span><span class="sxs-lookup"><span data-stu-id="ef0dd-130">For example, if you only want to be informed about High severity incidents, select High.</span></span>
    - <span data-ttu-id="ef0dd-131">**Gerätegruppen Bereich** : in diesem Dropdown werden alle Gerätegruppen angezeigt, auf die der Benutzer zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="ef0dd-131">**Device group scope** - This dropdown displays all the device groups the user can access.</span></span> <span data-ttu-id="ef0dd-132">Wählen Sie aus, für welche Gerätegruppen die Vorfall Benachrichtigungsregeln erstellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ef0dd-132">Select which device groups you're creating the incident notification rules for.</span></span>
    - <span data-ttu-id="ef0dd-133">**Nur beim ersten Auftreten pro Vorfall Benachrichtigen** – Wenn Sie diese Option auswählen, wird eine e-Mail-Benachrichtigung nur bei der ersten Benachrichtigung gesendet, die ihren anderen Auswahlen entspricht.</span><span class="sxs-lookup"><span data-stu-id="ef0dd-133">**Only notify on first occurrence per incident** - Selecting this option will send an email notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="ef0dd-134">Spätere Aktualisierungen oder Warnungen im Zusammenhang mit dem Vorfall lösen keine Benachrichtigung aus.</span><span class="sxs-lookup"><span data-stu-id="ef0dd-134">Later updates or alerts related to the incident won't trigger a notification.</span></span>
    - <span data-ttu-id="ef0dd-135">**Organisationsname einbeziehen** : gibt an, ob der Name des Kunden in der e-Mail-Benachrichtigung angezeigt wird oder nicht.</span><span class="sxs-lookup"><span data-stu-id="ef0dd-135">**Include organization name** - Indicates whether the customer name appears on the email notification or not.</span></span>
    - <span data-ttu-id="ef0dd-136">**Mandanten spezifischer Portal Link einbeziehen** – fügt einen Link mit der Mandanten-ID hinzu, um den Zugriff auf einen bestimmten Mandanten zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="ef0dd-136">**Include tenant-specific portal link** -  Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    
    ![Benach-Einstellungsfenster für Vorfall-e-Mail-notifs](../../media/incidentemailnotif2.png)
5. <span data-ttu-id="ef0dd-138">Wählen Sie **weiter** aus, um den Abschnitt **Empfänger** zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="ef0dd-138">Select **Next** to go the **Recipients** section.</span></span> <span data-ttu-id="ef0dd-139">Hier können Sie e-Mail-Adressen angeben, die die Vorfall-e-Mail-Benachrichtigungen erhalten sollen.</span><span class="sxs-lookup"><span data-stu-id="ef0dd-139">Here you can specify email addresses that will receive the incident email notifications.</span></span> <span data-ttu-id="ef0dd-140">Wählen Sie **Empfänger hinzufügen** aus, nachdem Sie jede e-Mail-Adresse eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="ef0dd-140">Select **Add a recipient** after typing every email address.</span></span>

    ![Fenster "Empfänger hinzufügen" für Vorfall-e-Mail notifs](../../media/incidentemailnotif3.png) 

6. <span data-ttu-id="ef0dd-142">Wählen Sie schließlich **weiter** , um zur **Überprüfungsregel** zu wechseln, damit Sie alle mit der neuen Regel verknüpften Einstellungen sehen können.</span><span class="sxs-lookup"><span data-stu-id="ef0dd-142">Finally, select **Next** to go to **Review rule** so you can see all the settings associated with your new rule.</span></span> <span data-ttu-id="ef0dd-143">Empfänger erhalten Benachrichtigungen über e-Mails basierend auf den Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="ef0dd-143">Recipients will start receiving incident notifications through email based on the settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="ef0dd-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef0dd-144">See also</span></span>
- [<span data-ttu-id="ef0dd-145">Übersicht über Vorfälle in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ef0dd-145">Incidents overview in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)
- [<span data-ttu-id="ef0dd-146">Priorisieren von Vorfällen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ef0dd-146">Prioritize incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- [<span data-ttu-id="ef0dd-147">Untersuchen von Vorfällen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ef0dd-147">Investigate incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

