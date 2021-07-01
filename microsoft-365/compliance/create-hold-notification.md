---
title: Erstellen eines Rechtlichen Aufbewahrungshinweiss
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Verwenden Sie das Kommunikationstool in einem Advanced eDiscovery Fall, um Benachrichtigungen über gesetzliche Aufbewahrungspflicht zu senden, zu sammeln und nachzuverfolgen.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 026670b9ed45f366ff3d711d8f2b2d0274be5a19
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227103"
---
# <a name="create-a-legal-hold-notice"></a><span data-ttu-id="00809-103">Erstellen eines Rechtlichen Aufbewahrungshinweiss</span><span class="sxs-lookup"><span data-stu-id="00809-103">Create a legal hold notice</span></span>

<span data-ttu-id="00809-104">Mithilfe Advanced eDiscovery Kommunikation mit Verwahrern können Organisationen ihren Workflow für die Kommunikation mit Verwahrern verwalten.</span><span class="sxs-lookup"><span data-stu-id="00809-104">Using Advanced eDiscovery custodian communications, organizations can manage their workflow around communicating with custodians.</span></span> <span data-ttu-id="00809-105">Mithilfe des Kommunikationstools können Rechtsteams Benachrichtigungen über gesetzliche Aufbewahrungspflicht systematisch senden, sammeln und nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="00809-105">Through the Communications tool, legal teams can systematically send, collect, and track legal hold notifications.</span></span> <span data-ttu-id="00809-106">Der flexible Erstellungsprozess ermöglicht es Teams auch, den Aufbewahrungsbenachrichtigungsworkflow und die Inhalte in den an Verwahrer gesendeten Benachrichtigungen anzupassen.</span><span class="sxs-lookup"><span data-stu-id="00809-106">The flexible creation process also allows teams to customize the hold notification workflow and the content in the notices sent to custodians.</span></span>

![Kommunikationsseite](../media/CommunicationPage.PNG)

<span data-ttu-id="00809-108">In diesem Artikel werden die Schritte im Aufbewahrungsbenachrichtigungsworkflow beschrieben.</span><span class="sxs-lookup"><span data-stu-id="00809-108">The article outlines the steps in the hold notification workflow.</span></span>

## <a name="step-1-specify-communication-details"></a><span data-ttu-id="00809-109">Schritt 1: Angeben von Kommunikationsdetails</span><span class="sxs-lookup"><span data-stu-id="00809-109">Step 1: Specify communication details</span></span>

<span data-ttu-id="00809-110">Der erste Schritt besteht darin, die entsprechenden Details für Benachrichtigungen über gesetzliche Aufbewahrung oder andere Mitteilungen von Verwahrern anzugeben.</span><span class="sxs-lookup"><span data-stu-id="00809-110">The first step is to specify the appropriate details for legal hold notices or other custodian communications.</span></span>

![Kommunikationsseite "Name"](../media/NameCommunication.PNG)

1. <span data-ttu-id="00809-112">Wechseln Sie im Security & Compliance Center zu **eDiscovery > Advanced eDiscovery,** um die Liste der Fälle in Ihrer Organisation anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="00809-112">In the Security & Compliance Center, go to **eDiscovery > Advanced eDiscovery** to display the list of cases in your organization.</span></span>

2. <span data-ttu-id="00809-113">Wählen Sie einen Fall aus, klicken Sie auf die Registerkarte **"Kommunikation"** und dann auf **"Neue Kommunikation".**</span><span class="sxs-lookup"><span data-stu-id="00809-113">Select a case, click the **Communications** tab, and then click **New communication**.</span></span>

3. <span data-ttu-id="00809-114">Geben Sie auf der Kommunikationsseite **"Name"** die folgenden (erforderlichen) Kommunikationsdetails an.</span><span class="sxs-lookup"><span data-stu-id="00809-114">On the **Name communication** page, specify the following (required) communication details.</span></span>

    - <span data-ttu-id="00809-115">**Name:** Dies ist der Name für die Kommunikation.</span><span class="sxs-lookup"><span data-stu-id="00809-115">**Name**: This is the name for the communication.</span></span>

    - <span data-ttu-id="00809-116">**Ausstellende Beauftragte:** In der Dropdownliste wird eine Liste der Fallmitglieder angezeigt.</span><span class="sxs-lookup"><span data-stu-id="00809-116">**Issuing officer**: The dropdown list displays a list of case members.</span></span> <span data-ttu-id="00809-117">Weitere Informationen zum Hinzufügen neuer Mitglieder zu einem Fall finden Sie unter [Erstellen eines Advanced eDiscovery Falls.](create-and-manage-advanced-ediscoveryv2-case.md#create-a-case)</span><span class="sxs-lookup"><span data-stu-id="00809-117">For more information on how to add new members to a case, see [Create an Advanced eDiscovery case](create-and-manage-advanced-ediscoveryv2-case.md#create-a-case).</span></span> <span data-ttu-id="00809-118">Jede Benachrichtigung, die an Verwahrer gesendet wird, wird im Namen des angegebenen Ausstellenden Beauftragten gesendet.</span><span class="sxs-lookup"><span data-stu-id="00809-118">Each notice sent to custodians will be sent on behalf of the specified issuing officer.</span></span>

> [!NOTE]
> <span data-ttu-id="00809-119">Der ausstellende Beauftragte muss über ein **aktives Postfach** verfügen, um in der Dropdownliste des Ausstellenden Beauftragten angezeigt zu werden.</span><span class="sxs-lookup"><span data-stu-id="00809-119">The issuing officer must have an **active mailbox** to show up in the Issuing Officer dropdown</span></span>


4. <span data-ttu-id="00809-120">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="00809-120">Click **Next**.</span></span>

## <a name="step-2-define-the-portal-content"></a><span data-ttu-id="00809-121">Schritt 2: Definieren des Portalinhalts</span><span class="sxs-lookup"><span data-stu-id="00809-121">Step 2: Define the portal content</span></span>

<span data-ttu-id="00809-122">Als Nächstes können Sie den Inhalt der Aufbewahrungsbenachrichtigung erstellen und hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="00809-122">Next, you can create and add the content of the hold notice.</span></span> <span data-ttu-id="00809-123">Geben Sie auf der Seite **"Portalinhalt definieren"** im Assistenten zum Erstellen von **Kommunikationen** den Inhalt des Aufbewahrungshinweiss an.</span><span class="sxs-lookup"><span data-stu-id="00809-123">On the **Define portal content** page in the **Create communication** wizard, specify the contents of the hold notice.</span></span> <span data-ttu-id="00809-124">Dieser Inhalt wird automatisch an die Benachrichtigungen "Veröffentlichung", "Erneut ausgeben", "Erinnerung" und "Eskalation" angefügt.</span><span class="sxs-lookup"><span data-stu-id="00809-124">This content will be automatically appended to the Issuance, Re-Issue, Reminder, and Escalation notices.</span></span> <span data-ttu-id="00809-125">Darüber hinaus werden diese Inhalte im Compliance-Portal des Verwalters angezeigt.</span><span class="sxs-lookup"><span data-stu-id="00809-125">Additionally, this content will appear in the custodian's Compliance Portal.</span></span>

![Portalinhaltsseite](../media/PortalContent.PNG)

<span data-ttu-id="00809-127">So erstellen Sie den Portalinhalt:</span><span class="sxs-lookup"><span data-stu-id="00809-127">To create the portal content:</span></span>

1. <span data-ttu-id="00809-128">Geben Sie Ihren Haltebereichshinweis in das Textfeld für den Portalinhalt ein (oder schneiden und aus einem anderen Dokument einfügen).</span><span class="sxs-lookup"><span data-stu-id="00809-128">Type (or cut and paste from another document) your hold notice in the textbox for the portal content.</span></span>

2. <span data-ttu-id="00809-129">Fügen Sie Zusammenführungsvariablen in Ihren Hinweis ein, um den Hinweis anzupassen und das Custodian Compliance Portal freizugeben.</span><span class="sxs-lookup"><span data-stu-id="00809-129">Insert merge variables into your notice to customize the notice and share the Custodian Compliance Portal.</span></span>

3. <span data-ttu-id="00809-130">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="00809-130">Click **Next**.</span></span>

  > [!TIP]
  > <span data-ttu-id="00809-131">Weitere Informationen dazu, wie Sie den Inhalt und das Format der Portalinhalte anpassen können, finden Sie unter [Verwenden des Kommunikations-Editors.](using-communications-editor.md)</span><span class="sxs-lookup"><span data-stu-id="00809-131">To learn more about how to can customize the content and format of the portal content, see [Use the Communications Editor](using-communications-editor.md).</span></span>

## <a name="step-3-set-the-required-notifications"></a><span data-ttu-id="00809-132">Schritt 3: Festlegen der erforderlichen Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="00809-132">Step 3: Set the required notifications</span></span>

<span data-ttu-id="00809-133">Nachdem Sie den Inhalt der Aufbewahrungsbenachrichtigung definiert haben, können Sie die Workflows zum Senden und Verwalten des Benachrichtigungsprozesses einrichten.</span><span class="sxs-lookup"><span data-stu-id="00809-133">After you've defined the contents of the hold notice, you can set up the workflows around sending and managing the notification process.</span></span> <span data-ttu-id="00809-134">Benachrichtigungen sind E-Mail-Nachrichten, die gesendet werden, um Verwalter zu benachrichtigen und zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="00809-134">Notifications are email messages that are sent to notify and follow up with custodians.</span></span> <span data-ttu-id="00809-135">Jeder zur Kommunikation hinzugefügte Verwalter erhält dieselbe Benachrichtigung.</span><span class="sxs-lookup"><span data-stu-id="00809-135">Every custodian added to the communication will receive the same notification.</span></span>

<span data-ttu-id="00809-136">Um eine Aufbewahrungsbenachrichtigung einzurichten und zu senden, müssen Sie Benachrichtigungen zu Ausstellung, Erneuter Veröffentlichung und Veröffentlichung einschließen.</span><span class="sxs-lookup"><span data-stu-id="00809-136">To set up and send a hold notice, you must include Issuance, Re-Issuance, and Release notifications.</span></span>

### <a name="issuance-notification"></a><span data-ttu-id="00809-137">Benachrichtigung über die Ausstellung</span><span class="sxs-lookup"><span data-stu-id="00809-137">Issuance notification</span></span>

<span data-ttu-id="00809-138">Nachdem die Kommunikation erstellt wurde, wird die **Benachrichtigung über** die Veröffentlichung durch den angegebenen Ausstellenden Beauftragten initiiert.</span><span class="sxs-lookup"><span data-stu-id="00809-138">After the communication is created, the **Issuance Notification** is initiated by the specified Issuing Officer.</span></span> <span data-ttu-id="00809-139">Die Benachrichtigung über die Ausstellung ist die erste an den Verwahrer gesendete Kommunikation, um ihn über seine Aufbewahrungspflichten zu informieren.</span><span class="sxs-lookup"><span data-stu-id="00809-139">The Issuance notification is the first communication sent to the custodian to inform them about their preservation obligations.</span></span>

<span data-ttu-id="00809-140">So erstellen Sie eine Veröffentlichungsbenachrichtigung:</span><span class="sxs-lookup"><span data-stu-id="00809-140">To create an issuance notification:</span></span>

1. <span data-ttu-id="00809-141">Klicken Sie in der Kachel **"Ausstellung"** auf **"Bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="00809-141">In the **Issuance** tile, click **Edit**.</span></span>

2. <span data-ttu-id="00809-142">Fügen Sie ggf. zusätzliche Fallmitglieder oder Mitarbeiter zu den Feldern **"Cc"** und **"Bcc"** hinzu.</span><span class="sxs-lookup"><span data-stu-id="00809-142">If necessary, add additional case members or staff to the **Cc** and **Bcc** fields.</span></span> <span data-ttu-id="00809-143">Um diesen Feldern mehrere Benutzer hinzuzufügen, trennen Sie E-Mail-Adressen mit einem Semikolon.</span><span class="sxs-lookup"><span data-stu-id="00809-143">To add multiple users to these fields, separate email addresses with a semi-colon.</span></span>

3. <span data-ttu-id="00809-144">Geben Sie den **Betreff** für den Hinweis an (erforderlich).</span><span class="sxs-lookup"><span data-stu-id="00809-144">Specify the **Subject** for the notice (required).</span></span>

4. <span data-ttu-id="00809-145">Geben Sie die Inhalte oder zusätzlichen Anweisungen an, die Sie dem Verwahrer bereitstellen möchten (erforderlich).</span><span class="sxs-lookup"><span data-stu-id="00809-145">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="00809-146">Der in Schritt 2 definierte Portalinhalt wird am Ende der Veröffentlichungsbenachrichtigung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="00809-146">The portal content you defined in Step 2 is added to the end of the issuance notice.</span></span>

5. <span data-ttu-id="00809-147">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="00809-147">Click **Save**.</span></span>

### <a name="re-issuance-notification"></a><span data-ttu-id="00809-148">Re-Issuance Benachrichtigung</span><span class="sxs-lookup"><span data-stu-id="00809-148">Re-Issuance notification</span></span>

<span data-ttu-id="00809-149">Im Weiteren Verlauf des Falls müssen Verwahrer möglicherweise zusätzliche oder weniger Daten beibehalten, als zuvor angewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="00809-149">As the case progresses, custodians may be required to preserve additional or less data than was previously instructed.</span></span> <span data-ttu-id="00809-150">Nachdem Sie den Portalinhalt aktualisiert haben, wird die Benachrichtigung zur erneuten Veröffentlichung gesendet, und die Verwahrer werden über Änderungen an ihren Aufbewahrungspflichten benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="00809-150">After you update the portal content, the re-issuance notification is sent and alerts custodians about any changes to their preservation obligations.</span></span>

<span data-ttu-id="00809-151">So erstellen Sie eine Benachrichtigung zur erneuten Veröffentlichung:</span><span class="sxs-lookup"><span data-stu-id="00809-151">To create a re-issuance notification:</span></span>

1. <span data-ttu-id="00809-152">Klicken Sie in der Kachel **"Neuauflage"** auf **"Bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="00809-152">In the **Reissue** tile, click **Edit**.</span></span>

2. <span data-ttu-id="00809-153">Fügen Sie ggf. zusätzliche Fallmitglieder oder Mitarbeiter zu den Feldern **"Cc"** und **"Bcc"** hinzu.</span><span class="sxs-lookup"><span data-stu-id="00809-153">If necessary, add additional case members or staff to the **Cc** and **Bcc** fields.</span></span> <span data-ttu-id="00809-154">Um diesen Feldern mehrere Benutzer hinzuzufügen, trennen Sie E-Mail-Adressen mit einem Semikolon.</span><span class="sxs-lookup"><span data-stu-id="00809-154">To add multiple users to these fields, separate email addresses with a semi-colon.</span></span>

3. <span data-ttu-id="00809-155">Geben Sie den **Betreff** für den Hinweis an (erforderlich).</span><span class="sxs-lookup"><span data-stu-id="00809-155">Specify the **Subject** for the notice (required).</span></span>

4. <span data-ttu-id="00809-156">Geben Sie die Inhalte oder zusätzlichen Anweisungen an, die Sie dem Verwahrer bereitstellen möchten (erforderlich).</span><span class="sxs-lookup"><span data-stu-id="00809-156">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="00809-157">Der portalinhalt, den Sie in Schritt 2 definiert haben, wird am Ende der Benachrichtigung zur erneuten Veröffentlichung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="00809-157">The portal content you defined in Step 2 is added to the end of the re-issuance notice.</span></span>

5. <span data-ttu-id="00809-158">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="00809-158">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="00809-159">Wenn der Portalinhalt geändert wird (auf der Seite **"Portalinhalt definieren"** im **Kommunikationsassistenten),** wird die Benachrichtigung über die erneute Ausstellung automatisch an alle Verwahrer gesendet, die der Benachrichtigung zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="00809-159">If the portal content is modified (on the **Define Portal Content** page in the **Edit communication** wizard), the re-issuance notification will be automatically sent to all custodians assigned to the notice.</span></span> <span data-ttu-id="00809-160">Nachdem die Benachrichtigung gesendet wurde, werden die Verwahrer aufgefordert, ihre Aufbewahrungsbenachrichtigung erneut zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="00809-160">After the notification is sent, custodians will be asked to re-acknowledge their hold notice.</span></span> <span data-ttu-id="00809-161">Wenn Sie Erinnerungs- oder Eskalationsworkflows eingerichtet haben, werden diese ebenfalls neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="00809-161">If you have set up any reminder or escalation workflows, these will also re-start.</span></span> <span data-ttu-id="00809-162">Weitere Informationen dazu, welche anderen Fallverwaltungsereignisse die Kommunikation auslösen, finden Sie unter [Ereignisse, die Benachrichtigungen auslösen.](#events-that-trigger-notifications)</span><span class="sxs-lookup"><span data-stu-id="00809-162">For more information about what other case management events trigger communications, see [Events that trigger notifications](#events-that-trigger-notifications).</span></span>

### <a name="release-notification"></a><span data-ttu-id="00809-163">Benachrichtigung zur Veröffentlichung</span><span class="sxs-lookup"><span data-stu-id="00809-163">Release notification</span></span>

<span data-ttu-id="00809-164">Nachdem eine Frage gelöst wurde oder wenn ein Verwalter nicht mehr der Aufbewahrung von Inhalten unterliegt, können Sie den Verwalter aus einem Fall freigeben.</span><span class="sxs-lookup"><span data-stu-id="00809-164">After a matter is resolved or if a custodian is no longer subject to preserve content, you can release the custodian from a case.</span></span> <span data-ttu-id="00809-165">Wenn dem Verwahrer zuvor eine Aufbewahrungsbenachrichtigung ausgestellt wurde, kann die Benachrichtigung über die Veröffentlichung verwendet werden, um Verwalter darauf hinzuweisen, dass sie von ihrer Verpflichtung freigelassen wurden.</span><span class="sxs-lookup"><span data-stu-id="00809-165">If the custodian was previously issued a hold notice, the release notification can be used to alert custodians that they have been released from their obligation.</span></span>

<span data-ttu-id="00809-166">So erstellen Sie eine Benachrichtigung über die Veröffentlichung:</span><span class="sxs-lookup"><span data-stu-id="00809-166">To create a release notification:</span></span>

1. <span data-ttu-id="00809-167">Klicken Sie in der **Kachel "Freigeben"** auf **"Bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="00809-167">In the **Release** tile, click **Edit**.</span></span>

2. <span data-ttu-id="00809-168">Fügen Sie ggf. zusätzliche Fallmitglieder oder Mitarbeiter zu den Feldern **"Cc"** und **"Bcc"** hinzu.</span><span class="sxs-lookup"><span data-stu-id="00809-168">If necessary, add additional case members or staff to the **Cc** and **Bcc** fields.</span></span> <span data-ttu-id="00809-169">Um diesen Feldern mehrere Benutzer hinzuzufügen, trennen Sie E-Mail-Adressen mit einem Semikolon.</span><span class="sxs-lookup"><span data-stu-id="00809-169">To add multiple users to these fields, separate email addresses with a semi-colon.</span></span>

3. <span data-ttu-id="00809-170">Geben Sie den **Betreff** für den Hinweis an (erforderlich).</span><span class="sxs-lookup"><span data-stu-id="00809-170">Specify the **Subject** for the notice (required).</span></span>

4. <span data-ttu-id="00809-171">Geben Sie die Inhalte oder zusätzlichen Anweisungen an, die Sie dem Verwahrer bereitstellen möchten (erforderlich).</span><span class="sxs-lookup"><span data-stu-id="00809-171">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span>

5. <span data-ttu-id="00809-172">Klicken Sie auf **"Speichern",** und fahren Sie mit dem nächsten Schritt fort.</span><span class="sxs-lookup"><span data-stu-id="00809-172">Click **Save** and go to the next step.</span></span>

## <a name="optional-step-4-set-the-optional-notifications"></a><span data-ttu-id="00809-173">(Optional) Schritt 4: Festlegen der optionalen Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="00809-173">(Optional) Step 4: Set the optional notifications</span></span>

<span data-ttu-id="00809-174">Optional können Sie den Workflow für die Nachverfolgung nicht reagierender Verwalter vereinfachen, indem Sie automatisierte Erinnerungs- und Eskalationsbenachrichtigungen erstellen und planen.</span><span class="sxs-lookup"><span data-stu-id="00809-174">Optionally, you can simplify the workflow for following up with unresponsive custodians by creating and scheduling automated reminder and escalation notifications.</span></span>

![Erinnerung/Eskalationsseite](../media/ReminderEscalations.PNG)

### <a name="reminders"></a><span data-ttu-id="00809-176">Erinnerungen</span><span class="sxs-lookup"><span data-stu-id="00809-176">Reminders</span></span>

<span data-ttu-id="00809-177">Nachdem Sie eine Aufbewahrungsbenachrichtigung gesendet haben, können Sie nicht reagierende Verwahrer durch Definieren eines Erinnerungsworkflows weiterverarbeiten.</span><span class="sxs-lookup"><span data-stu-id="00809-177">After you have sent a hold notification, you can follow up with unresponsive custodians by defining a reminder workflow.</span></span>

<span data-ttu-id="00809-178">So planen Sie Erinnerungen:</span><span class="sxs-lookup"><span data-stu-id="00809-178">To schedule reminders:</span></span>

1. <span data-ttu-id="00809-179">Klicken Sie in der **Kachel "Erinnerung"** auf **"Bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="00809-179">In the **Reminder** tile, click **Edit**.</span></span>

2. <span data-ttu-id="00809-180">Aktivieren  Sie den Erinnerungsworkflow, indem Sie die Status-Umschaltfläche aktivieren (erforderlich). </span><span class="sxs-lookup"><span data-stu-id="00809-180">Enable the **Reminder** workflow by turning on the **Status** toggle (required).</span></span>

3. <span data-ttu-id="00809-181">Geben Sie das **Erinnerungsintervall (in Tagen)** an (erforderlich).</span><span class="sxs-lookup"><span data-stu-id="00809-181">Specify the **Reminder interval (in days)** (required).</span></span> <span data-ttu-id="00809-182">Dies ist die Anzahl der Tage, die vor dem Senden der ersten und nachbereitenden Erinnerungsbenachrichtigungen gewartet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="00809-182">This is the number of days to wait before sending the first and follow-up reminder notifications.</span></span> <span data-ttu-id="00809-183">Wenn Sie beispielsweise das Erinnerungsintervall auf sieben Tage festlegen, wird die erste Erinnerung sieben Tage nach der anfänglichen Ausgabe der Aufbewahrungsbenachrichtigung gesendet.</span><span class="sxs-lookup"><span data-stu-id="00809-183">For example, if you set the reminder interval to seven days, then the first reminder would be sent seven days after the hold notification was initially issued.</span></span> <span data-ttu-id="00809-184">Alle nachfolgenden Erinnerungen würden auch alle sieben Tage gesendet.</span><span class="sxs-lookup"><span data-stu-id="00809-184">All subsequent reminders would also be sent every seven days.</span></span>

4. <span data-ttu-id="00809-185">Geben Sie die **Anzahl der Erinnerungen** an (erforderlich).</span><span class="sxs-lookup"><span data-stu-id="00809-185">Specify the **Number of reminders** (required).</span></span> <span data-ttu-id="00809-186">Dieses Feld gibt an, wie viele Erinnerungen an nicht reagierende Verwalter gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="00809-186">This field specifies how many reminders to send to unresponsive custodians.</span></span> <span data-ttu-id="00809-187">Wenn Sie beispielsweise die Anzahl der Erinnerungen auf 3 festlegen, erhält ein Verwahrer maximal drei Erinnerungen.</span><span class="sxs-lookup"><span data-stu-id="00809-187">For example, if you set the number of reminders to 3, then a custodian would receive a maximum of three reminders.</span></span> <span data-ttu-id="00809-188">Nachdem ein Verwahrer die Aufbewahrungsbenachrichtigung bestätigt hat, werden keine Erinnerungen mehr an diesen Benutzer gesendet.</span><span class="sxs-lookup"><span data-stu-id="00809-188">After a custodian acknowledges the hold notification, reminders will no longer be sent to that user.</span></span>

5. <span data-ttu-id="00809-189">Geben Sie den **Betreff** für den Hinweis an (erforderlich).</span><span class="sxs-lookup"><span data-stu-id="00809-189">Specify the **Subject** for the notice (required).</span></span>

6. <span data-ttu-id="00809-190">Geben Sie die Inhalte oder zusätzlichen Anweisungen an, die Sie dem Verwahrer bereitstellen möchten (erforderlich).</span><span class="sxs-lookup"><span data-stu-id="00809-190">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="00809-191">Der in Schritt 2 definierte Portalinhalt wird am Ende des Erinnerungshinweiss hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="00809-191">The portal content you defined in Step 2 is added to the end of the reminder notice.</span></span>

7. <span data-ttu-id="00809-192">Klicken Sie auf **"Speichern",** und fahren Sie mit dem nächsten Schritt fort.</span><span class="sxs-lookup"><span data-stu-id="00809-192">Click **Save** and go the next step.</span></span>

### <a name="escalations"></a><span data-ttu-id="00809-193">Eskalationen</span><span class="sxs-lookup"><span data-stu-id="00809-193">Escalations</span></span>

<span data-ttu-id="00809-194">In einigen Situationen benötigen Sie möglicherweise zusätzliche Möglichkeiten, um nicht reagierende Verwahrer zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="00809-194">In some situations, you may need additional ways to follow up with unresponsive custodians.</span></span> <span data-ttu-id="00809-195">Wenn ein Verwalter eine Aufbewahrungsbenachrichtigung nach Erhalt der angegebenen Anzahl von Erinnerungen nicht bestätigt, kann das Rechtsteam einen Workflow angeben, um automatisch eine Eskalationsbenachrichtigung an den Verwalter und dessen Vorgesetzten zu senden.</span><span class="sxs-lookup"><span data-stu-id="00809-195">If a custodian doesn't acknowledge a hold notification after receiving the specified number of reminders, the legal team can specify a workflow to automatically send an escalation notice to the custodian and their manager.</span></span>

<span data-ttu-id="00809-196">So planen Sie Eskalationen:</span><span class="sxs-lookup"><span data-stu-id="00809-196">To schedule escalations:</span></span>

1. <span data-ttu-id="00809-197">Klicken Sie in der **Kachel "Eskalation"** auf **"Bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="00809-197">In the **Escalation** tile, click **Edit**.</span></span>

2. <span data-ttu-id="00809-198">Aktivieren Sie den **Eskalationsworkflow,** indem Sie die Status-Umschaltfläche aktivieren. </span><span class="sxs-lookup"><span data-stu-id="00809-198">Enable the **Escalation** workflow by turning on the **Status** toggle.</span></span>

3. <span data-ttu-id="00809-199">Geben Sie das **Eskalationsintervall (in Tagen)** an (erforderlich).</span><span class="sxs-lookup"><span data-stu-id="00809-199">Specify the **Escalation interval (in days)** (required).</span></span>

4. <span data-ttu-id="00809-200">Geben Sie die **Anzahl der Eskalationen** an (erforderlich).</span><span class="sxs-lookup"><span data-stu-id="00809-200">Specify the **Number of escalations** (required).</span></span> <span data-ttu-id="00809-201">Dieses Feld gibt an, wie viele Eskalationen an nicht reagierende Verwalter gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="00809-201">This field specifies how many escalations to send to unresponsive custodians.</span></span> <span data-ttu-id="00809-202">Wenn Sie beispielsweise die Anzahl der Eskalationen auf 3 festlegen, wird eine Eskalationsbenachrichtigung maximal dreimal an den Verwalter und dessen Vorgesetzten gesendet.</span><span class="sxs-lookup"><span data-stu-id="00809-202">For example, if you set the number of escalations to 3, then an escalation notice would be sent to the custodian and their manager a maximum of three times.</span></span> <span data-ttu-id="00809-203">Nachdem ein Verwalter die Aufbewahrungsbenachrichtigung bestätigt hat, werden keine Eskalationen mehr gesendet.</span><span class="sxs-lookup"><span data-stu-id="00809-203">After a custodian acknowledges the hold notification, escalations will no longer be sent.</span></span>

5. <span data-ttu-id="00809-204">Geben Sie den **Betreff** für den Hinweis an (erforderlich).</span><span class="sxs-lookup"><span data-stu-id="00809-204">Specify the **Subject** for the notice (required).</span></span>

6. <span data-ttu-id="00809-205">Geben Sie die Inhalte oder zusätzlichen Anweisungen an, die Sie dem Verwahrer bereitstellen möchten (erforderlich).</span><span class="sxs-lookup"><span data-stu-id="00809-205">Specify the contents or additional instructions that you would like to provide to the custodian (required).</span></span> <span data-ttu-id="00809-206">Die in Schritt 2 definierten Portalinhalte werden am Ende der Eskalationsbenachrichtigung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="00809-206">The portal content you defined in Step 2 is added to the end of the escalation notice.</span></span>

7. <span data-ttu-id="00809-207">Klicken Sie auf **"Speichern",** und fahren Sie mit dem nächsten Schritt fort.</span><span class="sxs-lookup"><span data-stu-id="00809-207">Click **Save** and go the next step.</span></span>

## <a name="step-5-assign-custodians-to-receive-notifications"></a><span data-ttu-id="00809-208">Schritt 5: Zuweisen von Verwahrern zum Empfangen von Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="00809-208">Step 5: Assign custodians to receive notifications</span></span>

<span data-ttu-id="00809-209">Nachdem Sie den Inhalt für Benachrichtigungen abgeschlossen haben, wählen Sie die Verwahrer aus, an die Sie Benachrichtigungen senden möchten.</span><span class="sxs-lookup"><span data-stu-id="00809-209">After you have finalized the content for notifications, select the custodians that you would like to send notifications to.</span></span>

![Seite "Verwahrer auswählen"](../media/SelectCustodians.PNG)

<span data-ttu-id="00809-211">So fügen Sie Verwahrer hinzu:</span><span class="sxs-lookup"><span data-stu-id="00809-211">To add custodians:</span></span>

1. <span data-ttu-id="00809-212">Weisen Sie der Kommunikation Verwahrer zu, indem Sie auf das Kontrollkästchen neben ihrem Namen klicken.</span><span class="sxs-lookup"><span data-stu-id="00809-212">Assign custodians to the communication by clicking the checkbox next to their name.</span></span>

    <span data-ttu-id="00809-213">Nachdem die Kommunikation erstellt wurde, gilt der Benachrichtigungsworkflow automatisch für die ausgewählten Verwahrer.</span><span class="sxs-lookup"><span data-stu-id="00809-213">After the communication is created, the notification workflow will automatically apply to the selected custodians.</span></span>

2. <span data-ttu-id="00809-214">Klicken Sie auf **"Weiter",** um die Kommunikationseinstellungen und -details zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="00809-214">Click **Next** to review the communication settings and details.</span></span>

> [!NOTE]
> <span data-ttu-id="00809-215">Sie können nur Verwahrer hinzufügen, die dem Fall hinzugefügt wurden und keine weitere Benachrichtigung innerhalb des Falls erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="00809-215">You can only add custodians who have been added to the case and haven't been sent another notification within the case.</span></span>

## <a name="step-6-review-settings"></a><span data-ttu-id="00809-216">Schritt 6: Überprüfen der Einstellungen</span><span class="sxs-lookup"><span data-stu-id="00809-216">Step 6: Review settings</span></span>

<span data-ttu-id="00809-217">Nachdem Sie die Einstellungen überprüft und auf **"Senden"** klicken, um die Kommunikation abzuschließen, startet das System den Kommunikationsworkflow automatisch, indem die Veröffentlichungsbenachrichtigung gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="00809-217">After you review the settings and click **Send** to complete the communication, the system will automatically start the communication workflow by sending the issuance notice.</span></span>

## <a name="events-that-trigger-notifications"></a><span data-ttu-id="00809-218">Ereignisse, die Benachrichtigungen auslösen</span><span class="sxs-lookup"><span data-stu-id="00809-218">Events that trigger notifications</span></span>

<span data-ttu-id="00809-219">In der folgenden Tabelle werden Ereignisse im Fallverwaltungsprozess beschrieben, die ausgelöst werden, wenn die verschiedenen Arten von Benachrichtigungen an Verwahrer gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="00809-219">The following table describes events in the case management process that trigger when the different types of notifications are sent to custodians.</span></span>

|<span data-ttu-id="00809-220">Art der Kommunikation</span><span class="sxs-lookup"><span data-stu-id="00809-220">Type of communication</span></span>|<span data-ttu-id="00809-221">Auslöser</span><span class="sxs-lookup"><span data-stu-id="00809-221">Trigger</span></span> |
|:---------|:---------|
|<span data-ttu-id="00809-222">Veröffentlichungshinweise</span><span class="sxs-lookup"><span data-stu-id="00809-222">Issuance notices</span></span>|<span data-ttu-id="00809-223">Die anfängliche Erstellung der Benachrichtigung.</span><span class="sxs-lookup"><span data-stu-id="00809-223">The initial creation of the notification.</span></span> <span data-ttu-id="00809-224">Sie können eine Aufbewahrungsbenachrichtigung auch manuell erneut senden.</span><span class="sxs-lookup"><span data-stu-id="00809-224">You can also manually resend a hold notification.</span></span> |
|<span data-ttu-id="00809-225">Benachrichtigungen zur erneuten Veröffentlichung</span><span class="sxs-lookup"><span data-stu-id="00809-225">Re-issuance notices</span></span>|<span data-ttu-id="00809-226">Aktualisieren des Portalinhalts auf der Seite **"Portalinhalt definieren"** im Assistenten zum Bearbeiten der **Kommunikation.**</span><span class="sxs-lookup"><span data-stu-id="00809-226">Updating the portal content on the **Define Portal Content** page in the **Edit communication** wizard.</span></span>|
|<span data-ttu-id="00809-227">Benachrichtigungen zur Veröffentlichung</span><span class="sxs-lookup"><span data-stu-id="00809-227">Release notices</span></span>|<span data-ttu-id="00809-228">Der Verwahrer wird aus dem Fall freigelassen.</span><span class="sxs-lookup"><span data-stu-id="00809-228">The custodian is released from the case.</span></span>|
|<span data-ttu-id="00809-229">Erinnerungen</span><span class="sxs-lookup"><span data-stu-id="00809-229">Reminders</span></span>|<span data-ttu-id="00809-230">Das Intervall und die Anzahl der Erinnerungen, die für die Erinnerung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="00809-230">The interval and number of reminders configured for the reminder.</span></span>|
|<span data-ttu-id="00809-231">Eskalationen</span><span class="sxs-lookup"><span data-stu-id="00809-231">Escalations</span></span>|<span data-ttu-id="00809-232">Das Intervall und die Anzahl der Erinnerungen, die für die Eskalation konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="00809-232">The interval and number of reminders configured for the escalation.</span></span>|
|||
