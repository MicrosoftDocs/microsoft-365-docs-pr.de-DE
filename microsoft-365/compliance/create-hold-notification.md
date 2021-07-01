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
# <a name="create-a-legal-hold-notice"></a>Erstellen eines Rechtlichen Aufbewahrungshinweiss

Mithilfe Advanced eDiscovery Kommunikation mit Verwahrern können Organisationen ihren Workflow für die Kommunikation mit Verwahrern verwalten. Mithilfe des Kommunikationstools können Rechtsteams Benachrichtigungen über gesetzliche Aufbewahrungspflicht systematisch senden, sammeln und nachverfolgen. Der flexible Erstellungsprozess ermöglicht es Teams auch, den Aufbewahrungsbenachrichtigungsworkflow und die Inhalte in den an Verwahrer gesendeten Benachrichtigungen anzupassen.

![Kommunikationsseite](../media/CommunicationPage.PNG)

In diesem Artikel werden die Schritte im Aufbewahrungsbenachrichtigungsworkflow beschrieben.

## <a name="step-1-specify-communication-details"></a>Schritt 1: Angeben von Kommunikationsdetails

Der erste Schritt besteht darin, die entsprechenden Details für Benachrichtigungen über gesetzliche Aufbewahrung oder andere Mitteilungen von Verwahrern anzugeben.

![Kommunikationsseite "Name"](../media/NameCommunication.PNG)

1. Wechseln Sie im Security & Compliance Center zu **eDiscovery > Advanced eDiscovery,** um die Liste der Fälle in Ihrer Organisation anzuzeigen.

2. Wählen Sie einen Fall aus, klicken Sie auf die Registerkarte **"Kommunikation"** und dann auf **"Neue Kommunikation".**

3. Geben Sie auf der Kommunikationsseite **"Name"** die folgenden (erforderlichen) Kommunikationsdetails an.

    - **Name:** Dies ist der Name für die Kommunikation.

    - **Ausstellende Beauftragte:** In der Dropdownliste wird eine Liste der Fallmitglieder angezeigt. Weitere Informationen zum Hinzufügen neuer Mitglieder zu einem Fall finden Sie unter [Erstellen eines Advanced eDiscovery Falls.](create-and-manage-advanced-ediscoveryv2-case.md#create-a-case) Jede Benachrichtigung, die an Verwahrer gesendet wird, wird im Namen des angegebenen Ausstellenden Beauftragten gesendet.

> [!NOTE]
> Der ausstellende Beauftragte muss über ein **aktives Postfach** verfügen, um in der Dropdownliste des Ausstellenden Beauftragten angezeigt zu werden.


4. Klicken Sie auf **Weiter**.

## <a name="step-2-define-the-portal-content"></a>Schritt 2: Definieren des Portalinhalts

Als Nächstes können Sie den Inhalt der Aufbewahrungsbenachrichtigung erstellen und hinzufügen. Geben Sie auf der Seite **"Portalinhalt definieren"** im Assistenten zum Erstellen von **Kommunikationen** den Inhalt des Aufbewahrungshinweiss an. Dieser Inhalt wird automatisch an die Benachrichtigungen "Veröffentlichung", "Erneut ausgeben", "Erinnerung" und "Eskalation" angefügt. Darüber hinaus werden diese Inhalte im Compliance-Portal des Verwalters angezeigt.

![Portalinhaltsseite](../media/PortalContent.PNG)

So erstellen Sie den Portalinhalt:

1. Geben Sie Ihren Haltebereichshinweis in das Textfeld für den Portalinhalt ein (oder schneiden und aus einem anderen Dokument einfügen).

2. Fügen Sie Zusammenführungsvariablen in Ihren Hinweis ein, um den Hinweis anzupassen und das Custodian Compliance Portal freizugeben.

3. Klicken Sie auf **Weiter**.

  > [!TIP]
  > Weitere Informationen dazu, wie Sie den Inhalt und das Format der Portalinhalte anpassen können, finden Sie unter [Verwenden des Kommunikations-Editors.](using-communications-editor.md)

## <a name="step-3-set-the-required-notifications"></a>Schritt 3: Festlegen der erforderlichen Benachrichtigungen

Nachdem Sie den Inhalt der Aufbewahrungsbenachrichtigung definiert haben, können Sie die Workflows zum Senden und Verwalten des Benachrichtigungsprozesses einrichten. Benachrichtigungen sind E-Mail-Nachrichten, die gesendet werden, um Verwalter zu benachrichtigen und zu verfolgen. Jeder zur Kommunikation hinzugefügte Verwalter erhält dieselbe Benachrichtigung.

Um eine Aufbewahrungsbenachrichtigung einzurichten und zu senden, müssen Sie Benachrichtigungen zu Ausstellung, Erneuter Veröffentlichung und Veröffentlichung einschließen.

### <a name="issuance-notification"></a>Benachrichtigung über die Ausstellung

Nachdem die Kommunikation erstellt wurde, wird die **Benachrichtigung über** die Veröffentlichung durch den angegebenen Ausstellenden Beauftragten initiiert. Die Benachrichtigung über die Ausstellung ist die erste an den Verwahrer gesendete Kommunikation, um ihn über seine Aufbewahrungspflichten zu informieren.

So erstellen Sie eine Veröffentlichungsbenachrichtigung:

1. Klicken Sie in der Kachel **"Ausstellung"** auf **"Bearbeiten".**

2. Fügen Sie ggf. zusätzliche Fallmitglieder oder Mitarbeiter zu den Feldern **"Cc"** und **"Bcc"** hinzu. Um diesen Feldern mehrere Benutzer hinzuzufügen, trennen Sie E-Mail-Adressen mit einem Semikolon.

3. Geben Sie den **Betreff** für den Hinweis an (erforderlich).

4. Geben Sie die Inhalte oder zusätzlichen Anweisungen an, die Sie dem Verwahrer bereitstellen möchten (erforderlich). Der in Schritt 2 definierte Portalinhalt wird am Ende der Veröffentlichungsbenachrichtigung hinzugefügt.

5. Klicken Sie auf **Speichern**.

### <a name="re-issuance-notification"></a>Re-Issuance Benachrichtigung

Im Weiteren Verlauf des Falls müssen Verwahrer möglicherweise zusätzliche oder weniger Daten beibehalten, als zuvor angewiesen wurden. Nachdem Sie den Portalinhalt aktualisiert haben, wird die Benachrichtigung zur erneuten Veröffentlichung gesendet, und die Verwahrer werden über Änderungen an ihren Aufbewahrungspflichten benachrichtigt.

So erstellen Sie eine Benachrichtigung zur erneuten Veröffentlichung:

1. Klicken Sie in der Kachel **"Neuauflage"** auf **"Bearbeiten".**

2. Fügen Sie ggf. zusätzliche Fallmitglieder oder Mitarbeiter zu den Feldern **"Cc"** und **"Bcc"** hinzu. Um diesen Feldern mehrere Benutzer hinzuzufügen, trennen Sie E-Mail-Adressen mit einem Semikolon.

3. Geben Sie den **Betreff** für den Hinweis an (erforderlich).

4. Geben Sie die Inhalte oder zusätzlichen Anweisungen an, die Sie dem Verwahrer bereitstellen möchten (erforderlich). Der portalinhalt, den Sie in Schritt 2 definiert haben, wird am Ende der Benachrichtigung zur erneuten Veröffentlichung hinzugefügt.

5. Klicken Sie auf **Speichern**.

> [!NOTE]
> Wenn der Portalinhalt geändert wird (auf der Seite **"Portalinhalt definieren"** im **Kommunikationsassistenten),** wird die Benachrichtigung über die erneute Ausstellung automatisch an alle Verwahrer gesendet, die der Benachrichtigung zugewiesen sind. Nachdem die Benachrichtigung gesendet wurde, werden die Verwahrer aufgefordert, ihre Aufbewahrungsbenachrichtigung erneut zu bestätigen. Wenn Sie Erinnerungs- oder Eskalationsworkflows eingerichtet haben, werden diese ebenfalls neu gestartet. Weitere Informationen dazu, welche anderen Fallverwaltungsereignisse die Kommunikation auslösen, finden Sie unter [Ereignisse, die Benachrichtigungen auslösen.](#events-that-trigger-notifications)

### <a name="release-notification"></a>Benachrichtigung zur Veröffentlichung

Nachdem eine Frage gelöst wurde oder wenn ein Verwalter nicht mehr der Aufbewahrung von Inhalten unterliegt, können Sie den Verwalter aus einem Fall freigeben. Wenn dem Verwahrer zuvor eine Aufbewahrungsbenachrichtigung ausgestellt wurde, kann die Benachrichtigung über die Veröffentlichung verwendet werden, um Verwalter darauf hinzuweisen, dass sie von ihrer Verpflichtung freigelassen wurden.

So erstellen Sie eine Benachrichtigung über die Veröffentlichung:

1. Klicken Sie in der **Kachel "Freigeben"** auf **"Bearbeiten".**

2. Fügen Sie ggf. zusätzliche Fallmitglieder oder Mitarbeiter zu den Feldern **"Cc"** und **"Bcc"** hinzu. Um diesen Feldern mehrere Benutzer hinzuzufügen, trennen Sie E-Mail-Adressen mit einem Semikolon.

3. Geben Sie den **Betreff** für den Hinweis an (erforderlich).

4. Geben Sie die Inhalte oder zusätzlichen Anweisungen an, die Sie dem Verwahrer bereitstellen möchten (erforderlich).

5. Klicken Sie auf **"Speichern",** und fahren Sie mit dem nächsten Schritt fort.

## <a name="optional-step-4-set-the-optional-notifications"></a>(Optional) Schritt 4: Festlegen der optionalen Benachrichtigungen

Optional können Sie den Workflow für die Nachverfolgung nicht reagierender Verwalter vereinfachen, indem Sie automatisierte Erinnerungs- und Eskalationsbenachrichtigungen erstellen und planen.

![Erinnerung/Eskalationsseite](../media/ReminderEscalations.PNG)

### <a name="reminders"></a>Erinnerungen

Nachdem Sie eine Aufbewahrungsbenachrichtigung gesendet haben, können Sie nicht reagierende Verwahrer durch Definieren eines Erinnerungsworkflows weiterverarbeiten.

So planen Sie Erinnerungen:

1. Klicken Sie in der **Kachel "Erinnerung"** auf **"Bearbeiten".**

2. Aktivieren  Sie den Erinnerungsworkflow, indem Sie die Status-Umschaltfläche aktivieren (erforderlich). 

3. Geben Sie das **Erinnerungsintervall (in Tagen)** an (erforderlich). Dies ist die Anzahl der Tage, die vor dem Senden der ersten und nachbereitenden Erinnerungsbenachrichtigungen gewartet werden müssen. Wenn Sie beispielsweise das Erinnerungsintervall auf sieben Tage festlegen, wird die erste Erinnerung sieben Tage nach der anfänglichen Ausgabe der Aufbewahrungsbenachrichtigung gesendet. Alle nachfolgenden Erinnerungen würden auch alle sieben Tage gesendet.

4. Geben Sie die **Anzahl der Erinnerungen** an (erforderlich). Dieses Feld gibt an, wie viele Erinnerungen an nicht reagierende Verwalter gesendet werden sollen. Wenn Sie beispielsweise die Anzahl der Erinnerungen auf 3 festlegen, erhält ein Verwahrer maximal drei Erinnerungen. Nachdem ein Verwahrer die Aufbewahrungsbenachrichtigung bestätigt hat, werden keine Erinnerungen mehr an diesen Benutzer gesendet.

5. Geben Sie den **Betreff** für den Hinweis an (erforderlich).

6. Geben Sie die Inhalte oder zusätzlichen Anweisungen an, die Sie dem Verwahrer bereitstellen möchten (erforderlich). Der in Schritt 2 definierte Portalinhalt wird am Ende des Erinnerungshinweiss hinzugefügt.

7. Klicken Sie auf **"Speichern",** und fahren Sie mit dem nächsten Schritt fort.

### <a name="escalations"></a>Eskalationen

In einigen Situationen benötigen Sie möglicherweise zusätzliche Möglichkeiten, um nicht reagierende Verwahrer zu verfolgen. Wenn ein Verwalter eine Aufbewahrungsbenachrichtigung nach Erhalt der angegebenen Anzahl von Erinnerungen nicht bestätigt, kann das Rechtsteam einen Workflow angeben, um automatisch eine Eskalationsbenachrichtigung an den Verwalter und dessen Vorgesetzten zu senden.

So planen Sie Eskalationen:

1. Klicken Sie in der **Kachel "Eskalation"** auf **"Bearbeiten".**

2. Aktivieren Sie den **Eskalationsworkflow,** indem Sie die Status-Umschaltfläche aktivieren. 

3. Geben Sie das **Eskalationsintervall (in Tagen)** an (erforderlich).

4. Geben Sie die **Anzahl der Eskalationen** an (erforderlich). Dieses Feld gibt an, wie viele Eskalationen an nicht reagierende Verwalter gesendet werden sollen. Wenn Sie beispielsweise die Anzahl der Eskalationen auf 3 festlegen, wird eine Eskalationsbenachrichtigung maximal dreimal an den Verwalter und dessen Vorgesetzten gesendet. Nachdem ein Verwalter die Aufbewahrungsbenachrichtigung bestätigt hat, werden keine Eskalationen mehr gesendet.

5. Geben Sie den **Betreff** für den Hinweis an (erforderlich).

6. Geben Sie die Inhalte oder zusätzlichen Anweisungen an, die Sie dem Verwahrer bereitstellen möchten (erforderlich). Die in Schritt 2 definierten Portalinhalte werden am Ende der Eskalationsbenachrichtigung hinzugefügt.

7. Klicken Sie auf **"Speichern",** und fahren Sie mit dem nächsten Schritt fort.

## <a name="step-5-assign-custodians-to-receive-notifications"></a>Schritt 5: Zuweisen von Verwahrern zum Empfangen von Benachrichtigungen

Nachdem Sie den Inhalt für Benachrichtigungen abgeschlossen haben, wählen Sie die Verwahrer aus, an die Sie Benachrichtigungen senden möchten.

![Seite "Verwahrer auswählen"](../media/SelectCustodians.PNG)

So fügen Sie Verwahrer hinzu:

1. Weisen Sie der Kommunikation Verwahrer zu, indem Sie auf das Kontrollkästchen neben ihrem Namen klicken.

    Nachdem die Kommunikation erstellt wurde, gilt der Benachrichtigungsworkflow automatisch für die ausgewählten Verwahrer.

2. Klicken Sie auf **"Weiter",** um die Kommunikationseinstellungen und -details zu überprüfen.

> [!NOTE]
> Sie können nur Verwahrer hinzufügen, die dem Fall hinzugefügt wurden und keine weitere Benachrichtigung innerhalb des Falls erhalten haben.

## <a name="step-6-review-settings"></a>Schritt 6: Überprüfen der Einstellungen

Nachdem Sie die Einstellungen überprüft und auf **"Senden"** klicken, um die Kommunikation abzuschließen, startet das System den Kommunikationsworkflow automatisch, indem die Veröffentlichungsbenachrichtigung gesendet wird.

## <a name="events-that-trigger-notifications"></a>Ereignisse, die Benachrichtigungen auslösen

In der folgenden Tabelle werden Ereignisse im Fallverwaltungsprozess beschrieben, die ausgelöst werden, wenn die verschiedenen Arten von Benachrichtigungen an Verwahrer gesendet werden.

|Art der Kommunikation|Auslöser |
|:---------|:---------|
|Veröffentlichungshinweise|Die anfängliche Erstellung der Benachrichtigung. Sie können eine Aufbewahrungsbenachrichtigung auch manuell erneut senden. |
|Benachrichtigungen zur erneuten Veröffentlichung|Aktualisieren des Portalinhalts auf der Seite **"Portalinhalt definieren"** im Assistenten zum Bearbeiten der **Kommunikation.**|
|Benachrichtigungen zur Veröffentlichung|Der Verwahrer wird aus dem Fall freigelassen.|
|Erinnerungen|Das Intervall und die Anzahl der Erinnerungen, die für die Erinnerung konfiguriert sind.|
|Eskalationen|Das Intervall und die Anzahl der Erinnerungen, die für die Eskalation konfiguriert sind.|
|||
