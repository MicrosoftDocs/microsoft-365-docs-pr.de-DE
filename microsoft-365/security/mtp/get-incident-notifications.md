---
title: Vorfallbenachrichtigungen in Microsoft 365 Defender erhalten
description: Erfahren Sie, wie Sie Regeln erstellen, um E-Mail-Benachrichtigungen für Vorfälle in Microsoft 365 Defender zu erhalten.
keywords: Vorfall, E-Mail, E-Mail-Notationen, konfigurieren, Benutzer, Postfach, E-Mail, Vorfälle
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
ms.openlocfilehash: f25be4de3f25db869957474c3cb32b20e9f7aa53
ms.sourcegitcommit: 88d358d778804b26d5e41c53b4f725d01a78112b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49848891"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="fe50f-104">Vorfallbenachrichtigungen per E-Mail erhalten</span><span class="sxs-lookup"><span data-stu-id="fe50f-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="fe50f-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="fe50f-105">**Applies to:**</span></span>
- <span data-ttu-id="fe50f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fe50f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="fe50f-107">Sie können Microsoft 365 Defender so einrichten, dass Sie jedes Mal per E-Mail benachrichtigt werden, wenn es neue Vorfälle oder neue Updates für vorhandene Vorfälle gibt.</span><span class="sxs-lookup"><span data-stu-id="fe50f-107">You can set up Microsoft 365 Defender to notify you by email every time there are new incidents or new updates to existing incidents.</span></span> 

<span data-ttu-id="fe50f-108">Sie können Benachrichtigungen basierend auf dem Schweregrad des Vorfalls oder nach Gerätegruppe erhalten.</span><span class="sxs-lookup"><span data-stu-id="fe50f-108">You can choose to get notifications based on incident severity or by device group.</span></span> <span data-ttu-id="fe50f-109">Sie können auch festlegen, dass eine Benachrichtigung nur beim ersten Update pro Vorfall angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="fe50f-109">You can also choose to get a notification only on the first update per incident.</span></span>

<span data-ttu-id="fe50f-110">Sie können Empfänger in den E-Mail-Benachrichtigungen hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="fe50f-110">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="fe50f-111">Neu hinzugefügte Empfänger werden über Vorfälle benachrichtigt, nachdem sie hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="fe50f-111">Newly added recipients get notified about incidents after they're added.</span></span> 

<span data-ttu-id="fe50f-112">Die E-Mail-Benachrichtigung enthält wichtige Details zu dem Vorfall, z. B. den Vorfallnamen, schweregrad und Kategorien.</span><span class="sxs-lookup"><span data-stu-id="fe50f-112">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="fe50f-113">Sie können auch direkt zu Vorfällen wechseln, damit Sie ihre Untersuchung sofort starten können.</span><span class="sxs-lookup"><span data-stu-id="fe50f-113">You can also directly go to incidents so you can start your investigation right away.</span></span> <span data-ttu-id="fe50f-114">Weitere Informationen zur Untersuchung von Vorfällen finden Sie unter ["Untersuchen von Vorfällen in Microsoft 365 Defender".](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)</span><span class="sxs-lookup"><span data-stu-id="fe50f-114">For more on investigating incidents, see [Investigate incidents in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents).</span></span>

>[!NOTE]
><span data-ttu-id="fe50f-115">Sie benötigen die Berechtigungen "Sicherheitseinstellungen verwalten", um E-Mail-Benachrichtigungseinstellungen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="fe50f-115">You need 'Manage security settings' permissions to configure email notification settings.</span></span> <span data-ttu-id="fe50f-116">Wenn Sie sich für die Verwendung der grundlegenden Berechtigungsverwaltung entschieden haben, können Benutzer mit Sicherheitsadministrator- oder globalen Administratorrollen E-Mail-Benachrichtigungen für Sie konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="fe50f-116">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="fe50f-117">Ebenso können Sie, wenn Ihre Organisation die rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) verwendet, Benachrichtigungen nur basierend auf Gerätegruppen erstellen, bearbeiten, löschen und empfangen, die Sie verwalten dürfen.</span><span class="sxs-lookup"><span data-stu-id="fe50f-117">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-rules-for-incident-notifications"></a><span data-ttu-id="fe50f-118">Erstellen von Regeln für Vorfallbenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="fe50f-118">Create rules for incident notifications</span></span>

<span data-ttu-id="fe50f-119">Erstellen Sie zum Einrichten Ihrer ersten E-Mail-Benachrichtigung für Vorfälle eine neue Regel, und passen Sie die Einstellungen für E-Mail-Benachrichtigungen an.</span><span class="sxs-lookup"><span data-stu-id="fe50f-119">To set up your first email notification for incidents, create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="fe50f-120">Wählen Sie im Navigationsbereich E-Mail-Benachrichtigungen  >  **zu Einstellungen für Vorfälle aus.**</span><span class="sxs-lookup"><span data-stu-id="fe50f-120">In the navigation pane, select **Settings** > **Incident email notifications**.</span></span>
2. <span data-ttu-id="fe50f-121">Wählen Sie **"Element hinzufügen" aus.**</span><span class="sxs-lookup"><span data-stu-id="fe50f-121">Select **Add item**.</span></span>
3. <span data-ttu-id="fe50f-122">Geben Sie der Regel einen Namen im **Namen und** geben Sie eine **Beschreibung an.**</span><span class="sxs-lookup"><span data-stu-id="fe50f-122">Give the rule a name in **Name** and supply a **Description**.</span></span>

    ![Erstellen eines Regelfensters für Vorfall-E-Mail-Notififen](../../media/incidentemailnotif1.png) 
4. <span data-ttu-id="fe50f-124">Wählen **Sie "Weiter"** aus, um zu den **Benachrichtigungseinstellungen zu wechseln.**</span><span class="sxs-lookup"><span data-stu-id="fe50f-124">Select **Next** to go to **Notification settings**.</span></span> <span data-ttu-id="fe50f-125">Hier können Sie angeben:</span><span class="sxs-lookup"><span data-stu-id="fe50f-125">Here you can specify:</span></span>
    - <span data-ttu-id="fe50f-126">**Warnungsschweregrad** : Wählen Sie den Warnungsschweregrad aus, der eine Vorfallbenachrichtigung auslöst.</span><span class="sxs-lookup"><span data-stu-id="fe50f-126">**Alert severity** - Choose the alert severity that will trigger an incident notification.</span></span> <span data-ttu-id="fe50f-127">Wenn Sie beispielsweise nur über Vorfälle mit hohem Schweregrad informiert werden möchten, wählen Sie "Hoch" aus.</span><span class="sxs-lookup"><span data-stu-id="fe50f-127">For example, if you only want to be informed about High severity incidents, select High.</span></span>
    - <span data-ttu-id="fe50f-128">**Gerätegruppenbereich** – In dieser Dropdownliste werden alle Gerätegruppen angezeigt, auf die der Benutzer zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="fe50f-128">**Device group scope** - This dropdown displays all the device groups the user can access.</span></span> <span data-ttu-id="fe50f-129">Wählen Sie aus, für welche Gerätegruppen Sie die Regeln für die Vorfallbenachrichtigung erstellen.</span><span class="sxs-lookup"><span data-stu-id="fe50f-129">Select which device groups you're creating the incident notification rules for.</span></span>
    - <span data-ttu-id="fe50f-130">**Nur beim ersten Auftreten pro** Vorfall benachrichtigen – Wenn Sie diese Option auswählen, wird nur bei der ersten Warnung eine E-Mail-Benachrichtigung gesendet, die Ihrer anderen Auswahl entspricht.</span><span class="sxs-lookup"><span data-stu-id="fe50f-130">**Only notify on first occurrence per incident** - Selecting this option will send an email notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="fe50f-131">Spätere Updates oder Warnungen im Zusammenhang mit dem Vorfall lösen keine Benachrichtigung aus.</span><span class="sxs-lookup"><span data-stu-id="fe50f-131">Later updates or alerts related to the incident won't trigger a notification.</span></span>
    - <span data-ttu-id="fe50f-132">**Name der Organisation angeben** – Gibt an, ob der Name des Kunden in der E-Mail-Benachrichtigung angezeigt wird oder nicht.</span><span class="sxs-lookup"><span data-stu-id="fe50f-132">**Include organization name** - Indicates whether the customer name appears on the email notification or not.</span></span>
    - <span data-ttu-id="fe50f-133">**Mandantenspezifische Portallink hinzufügen** – Fügt einen Link mit der Mandanten-ID hinzu, um den Zugriff auf einen bestimmten Mandanten zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="fe50f-133">**Include tenant-specific portal link** -  Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    
    ![Fenster "Notif settings" für Vorfall-E-Mail-Notifen](../../media/incidentemailnotif2.png)
5. <span data-ttu-id="fe50f-135">Wählen **Sie "Weiter"** aus, um zum Abschnitt **"Empfänger" zu** wechseln.</span><span class="sxs-lookup"><span data-stu-id="fe50f-135">Select **Next** to go the **Recipients** section.</span></span> <span data-ttu-id="fe50f-136">Hier können Sie E-Mail-Adressen angeben, die die Vorfall-E-Mail-Benachrichtigungen erhalten.</span><span class="sxs-lookup"><span data-stu-id="fe50f-136">Here you can specify email addresses that will receive the incident email notifications.</span></span> <span data-ttu-id="fe50f-137">Wählen **Sie nach der Eingabe jeder** E-Mail-Adresse die Option "Empfänger hinzufügen" aus.</span><span class="sxs-lookup"><span data-stu-id="fe50f-137">Select **Add a recipient** after typing every email address.</span></span>

    ![Fenster "Empfänger hinzufügen" für Vorfall-E-Mail-Notifen](../../media/incidentemailnotif3.png) 

6. <span data-ttu-id="fe50f-139">Wählen Sie schließlich **"Weiter"** aus, **um** zur Regel "Überprüfen" zu wechseln, damit Sie alle Einstellungen sehen können, die der neuen Regel zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="fe50f-139">Finally, select **Next** to go to **Review rule** so you can see all the settings associated with your new rule.</span></span> <span data-ttu-id="fe50f-140">Empfänger erhalten Benachrichtigungen über Vorfälle per E-Mail basierend auf den Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="fe50f-140">Recipients will start receiving incident notifications through email based on the settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe50f-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe50f-141">See also</span></span>
- [<span data-ttu-id="fe50f-142">Übersicht über Vorfälle in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fe50f-142">Incidents overview in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incidents-overview)
- [<span data-ttu-id="fe50f-143">Priorisieren von Vorfällen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fe50f-143">Prioritize incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/incident-queue)
- [<span data-ttu-id="fe50f-144">Untersuchen von Vorfällen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fe50f-144">Investigate incidents in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/investigate-incidents)

