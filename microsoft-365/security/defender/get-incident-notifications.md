---
title: Vorfallbenachrichtigungen per E-Mail in Microsoft 365 Defender erhalten
description: Informationen zum Erstellen von Regeln zum Erhalten von E-Mail-Benachrichtigungen für Vorfälle in Microsoft 365 Defender
keywords: Incident, email, email notfications, configure, users, mailbox, email, incidents, analyze, response
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 8d29291c63bdc437163feecce8164089d958d71d
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52299964"
---
# <a name="get-incident-notifications-by-email"></a><span data-ttu-id="bd75b-104">Vorfallbenachrichtigungen per E-Mail erhalten</span><span class="sxs-lookup"><span data-stu-id="bd75b-104">Get incident notifications by email</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bd75b-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="bd75b-105">**Applies to:**</span></span>
- <span data-ttu-id="bd75b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bd75b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="bd75b-107">Sie können Microsoft 365 Defender einrichten, um Ihre Mitarbeiter per E-Mail über neue Vorfälle oder Updates zu vorhandenen Vorfällen zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="bd75b-107">You can set up Microsoft 365 Defender to notify your staff with an email about new incidents or updates to existing incidents.</span></span> <span data-ttu-id="bd75b-108">Sie können Benachrichtigungen basierend auf:</span><span class="sxs-lookup"><span data-stu-id="bd75b-108">You can choose to get notifications based on:</span></span>

- <span data-ttu-id="bd75b-109">Schweregrad des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="bd75b-109">Incident severity.</span></span>
- <span data-ttu-id="bd75b-110">Gerätegruppe.</span><span class="sxs-lookup"><span data-stu-id="bd75b-110">Device group.</span></span>
- <span data-ttu-id="bd75b-111">Nur beim ersten Update pro Vorfall.</span><span class="sxs-lookup"><span data-stu-id="bd75b-111">Only on the first update per incident.</span></span>

<span data-ttu-id="bd75b-112">Die E-Mail-Benachrichtigung enthält wichtige Details zu dem Vorfall, z. B. den Vorfallnamen, schweregrad und Kategorien.</span><span class="sxs-lookup"><span data-stu-id="bd75b-112">The email notification contains important details about the incident like the incident name, severity, and categories, among others.</span></span> <span data-ttu-id="bd75b-113">Sie können auch direkt zu dem Vorfall wechseln und ihre Analyse sofort starten.</span><span class="sxs-lookup"><span data-stu-id="bd75b-113">You can also go directly to the incident and start your analysis right away.</span></span> <span data-ttu-id="bd75b-114">Weitere Informationen finden Sie unter [Investigate incidents](investigate-incidents.md).</span><span class="sxs-lookup"><span data-stu-id="bd75b-114">For more information, see [Investigate incidents](investigate-incidents.md).</span></span>

<span data-ttu-id="bd75b-115">Sie können Empfänger in den E-Mail-Benachrichtigungen hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="bd75b-115">You can add or remove recipients in the email notifications.</span></span> <span data-ttu-id="bd75b-116">Neue Empfänger werden über Vorfälle benachrichtigt, nachdem sie hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="bd75b-116">New recipients get notified about incidents after they're added.</span></span> 

>[!NOTE]
><span data-ttu-id="bd75b-117">Sie benötigen die Berechtigung "Sicherheitseinstellungen verwalten", um E-Mail-Benachrichtigungseinstellungen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="bd75b-117">You need the 'Manage security settings' permission to configure email notification settings.</span></span> <span data-ttu-id="bd75b-118">Wenn Sie sich für die Verwendung der grundlegenden Berechtigungsverwaltung entschieden haben, können Benutzer mit Sicherheitsadministrator- oder globalen Administratorrollen E-Mail-Benachrichtigungen für Sie konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="bd75b-118">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications for you.</span></span> <br> <br>
<span data-ttu-id="bd75b-119">Wenn Ihre Organisation rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) verwendet, können Sie nur Benachrichtigungen basierend auf Gerätegruppen erstellen, bearbeiten, löschen und empfangen, die Sie verwalten dürfen.</span><span class="sxs-lookup"><span data-stu-id="bd75b-119">Likewise, if your organization is using role-based access control (RBAC), you can only create, edit, delete, and receive notifications based on device groups that you are allowed to manage.</span></span>

## <a name="create-a-rule-for-email-notifications"></a><span data-ttu-id="bd75b-120">Erstellen einer Regel für E-Mail-Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="bd75b-120">Create a rule for email notifications</span></span>

<span data-ttu-id="bd75b-121">Führen Sie die folgenden Schritte aus, um eine neue Regel zu erstellen und E-Mail-Benachrichtigungseinstellungen anzupassen.</span><span class="sxs-lookup"><span data-stu-id="bd75b-121">Follow these steps to create a new rule and customize email notification settings.</span></span>

1. <span data-ttu-id="bd75b-122">Wählen Sie im Navigationsbereich Einstellungen **> Microsoft 365 Defender > Vorfall-E-Mail-Benachrichtigungen aus.**</span><span class="sxs-lookup"><span data-stu-id="bd75b-122">In the navigation pane, select **Settings > Microsoft 365 Defender > Incident email notifications**.</span></span>
2. <span data-ttu-id="bd75b-123">Wählen **Sie Element hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="bd75b-123">Select **Add item**.</span></span>
3. <span data-ttu-id="bd75b-124">Geben Sie **auf der** Seite Grundlagen den Regelnamen und eine Beschreibung ein, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="bd75b-124">On the **Basics** page, type the rule name and a description, and then select **Next**.</span></span>
4. <span data-ttu-id="bd75b-125">Konfigurieren Sie **auf der** Seite Benachrichtigungseinstellungen:</span><span class="sxs-lookup"><span data-stu-id="bd75b-125">On the **Notification settings** page, configure:</span></span>
    - <span data-ttu-id="bd75b-126">**Warnungsschweregrad:** Wählen Sie den Warnungsschweregrad aus, der eine Vorfallbenachrichtigung auslöst.</span><span class="sxs-lookup"><span data-stu-id="bd75b-126">**Alert severity** - Choose the alert severities that will trigger an incident notification.</span></span> <span data-ttu-id="bd75b-127">Wenn Sie beispielsweise nur über Vorfälle mit hohem Schweregrad informiert werden möchten, wählen Sie **Hoch aus.**</span><span class="sxs-lookup"><span data-stu-id="bd75b-127">For example, if you only want to be informed about high-severity incidents, select **High**.</span></span>
    - <span data-ttu-id="bd75b-128">**Gerätegruppenbereich** : Sie können alle Gerätegruppen angeben oder aus der Liste der Gerätegruppen in Ihrem Mandanten auswählen.</span><span class="sxs-lookup"><span data-stu-id="bd75b-128">**Device group scope** - You can specify all device groups or select from the list of device groups in your tenant.</span></span>
    - <span data-ttu-id="bd75b-129">**Nur beim ersten Auftreten pro Vorfall** benachrichtigen – Wählen Sie aus, wenn Sie eine Benachrichtigung nur für die erste Warnung wünschen, die Mit Ihrer anderen Auswahl entspricht.</span><span class="sxs-lookup"><span data-stu-id="bd75b-129">**Only notify on first occurrence per incident** - Select if you want a notification only on the first alert that matches your other selections.</span></span> <span data-ttu-id="bd75b-130">Spätere Updates oder Warnungen im Zusammenhang mit dem Vorfall senden keine zusätzlichen Benachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="bd75b-130">Later updates or alerts related to the incident won't send additional notifications.</span></span>
    - <span data-ttu-id="bd75b-131">**Organisationsname in die E-Mail eingeben** – Wählen Sie aus, ob Ihr Organisationsname in der E-Mail-Benachrichtigung angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="bd75b-131">**Include organization name in the email** - Select if you want your organization name to appear in the email notification.</span></span>
    - <span data-ttu-id="bd75b-132">**Mandantenspezifischer Portallink hinzufügen** – Wählen Sie aus, ob Sie einen Link mit der Mandanten-ID in der E-Mail-Benachrichtigung für den Zugriff auf einen bestimmten Microsoft 365-Mandanten hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="bd75b-132">**Include tenant-specific portal link** - Select if you want to add a link with the tenant ID in the email notification for access to a specific Microsoft 365 tenant.</span></span>

    :::image type="content" source="../../media/get-incident-notifications/incidents-ss-email-notification-settings.png" alt-text="Benachrichtigungseinstellungen für Vorfall-E-Mail-Benachrichtigungen":::

5. <span data-ttu-id="bd75b-134">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="bd75b-134">Select **Next**.</span></span> <span data-ttu-id="bd75b-135">Fügen Sie **auf der** Seite Empfänger die E-Mail-Adressen hinzu, die die Vorfallbenachrichtigungen erhalten.</span><span class="sxs-lookup"><span data-stu-id="bd75b-135">On the **Recipients** page, add the email addresses that will receive the incident notifications.</span></span> <span data-ttu-id="bd75b-136">Wählen **Sie Nach** eingabe jeder neuen E-Mail-Adresse hinzufügen aus.</span><span class="sxs-lookup"><span data-stu-id="bd75b-136">Select **Add** after typing each new email address.</span></span> <span data-ttu-id="bd75b-137">Um Benachrichtigungen zu testen und sicherzustellen, dass die Empfänger sie in den Posteingangen empfangen, wählen Sie **Test-E-Mail senden aus.**</span><span class="sxs-lookup"><span data-stu-id="bd75b-137">To test notifications and ensure that the recipients receive them in the inboxes, select **Send test email**.</span></span> 
6. <span data-ttu-id="bd75b-138">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="bd75b-138">Select **Next**.</span></span> <span data-ttu-id="bd75b-139">Überprüfen Sie **auf der Seite** Regel überprüfen die Einstellungen der Regel, und wählen Sie dann Regel erstellen **aus.**</span><span class="sxs-lookup"><span data-stu-id="bd75b-139">On the **Review rule** page, review the settings of the rule, and then select **Create rule**.</span></span> <span data-ttu-id="bd75b-140">Empfänger erhalten Benachrichtigungen über Vorfälle über E-Mail basierend auf den Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="bd75b-140">Recipients will start receiving incident notifications through email based on the settings.</span></span>

<span data-ttu-id="bd75b-141">Um eine vorhandene Regel zu bearbeiten, wählen Sie sie aus der Liste der Regeln aus.</span><span class="sxs-lookup"><span data-stu-id="bd75b-141">To edit an existing rule, select it from the list of rules.</span></span> <span data-ttu-id="bd75b-142">Wählen Sie im Bereich mit  dem Regelnamen Regel bearbeiten aus, und nehmen Sie ihre Änderungen auf den Seiten **Grundlagen, Benachrichtigungseinstellungen** **und** **Empfänger** vor.</span><span class="sxs-lookup"><span data-stu-id="bd75b-142">On the pane with the rule name, select **Edit rule** and make your changes on the **Basics**, **Notification settings**, and **Recipients** pages.</span></span>

<span data-ttu-id="bd75b-143">Um eine vorhandene Regel zu bearbeiten, wählen Sie sie aus der Liste der Regeln aus.</span><span class="sxs-lookup"><span data-stu-id="bd75b-143">To edit an existing rule, select it from the list of rules.</span></span> <span data-ttu-id="bd75b-144">Wählen Sie im Bereich mit dem Regelnamen Löschen **aus.**</span><span class="sxs-lookup"><span data-stu-id="bd75b-144">On the pane with the rule name, select **Delete**.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd75b-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd75b-145">See also</span></span>
- [<span data-ttu-id="bd75b-146">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="bd75b-146">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="bd75b-147">Priorisieren von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="bd75b-147">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="bd75b-148">Untersuchen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="bd75b-148">Investigate incidents</span></span>](investigate-incidents.md)
