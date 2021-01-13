---
title: Erstellen eines Hinweises zur gesetzlichen Benachrichtigung
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
description: Verwenden Sie das Kommunikationstool in einem Advanced eDiscovery-Fall, um Benachrichtigungen über die gesetzliche Gesetzliche Benachrichtigungen zu senden, zu sammeln und nachverfolgt zu werden.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: df1b2d962e83110c62ccac871f669bbc0d3bfe02
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840560"
---
# <a name="create-a-legal-hold-notice"></a>Erstellen eines Hinweises zur gesetzlichen Benachrichtigung

Mithilfe der Advanced eDiscovery-Verwaltung können Organisationen ihren Workflow um die Kommunikation mit Verwahrern verwalten. Mithilfe des Kommunikationstools können Rechtsteams Benachrichtigungen über die gesetzliche Benachrichtigungen systematisch senden, sammeln und nachverfolgen. Mit dem flexiblen Erstellungsprozess können Teams außerdem den Workflow für haltebenachrichtigungen und die Inhalte in den Benachrichtigungen anpassen, die an Verwahrer gesendet werden.

![Seite "Kommunikation"](../media/CommunicationPage.PNG)

In diesem Artikel werden die Schritte im Workflow für haltebenachrichtigungen beschrieben.

## <a name="step-1-specify-communication-details"></a>Schritt 1: Angeben von Kommunikationsdetails

Der erste Schritt besteht in der Angabe der entsprechenden Details für Hinweise zur gesetzlichen Haltebewahrung oder andere Mitteilungen von Verwahrern.

![Seite "Name Communication"](../media/NameCommunication.PNG)

1. Wechseln Sie im Security & Compliance Center zu **eDiscovery > Advanced eDiscovery,** um die Liste der Fälle in Ihrer Organisation anzeigen.

2. Wählen Sie einen Fall aus, **klicken** Sie auf die Registerkarte "Kommunikation", und klicken Sie dann auf **"Neue Kommunikation".**

3. Geben Sie **auf der Seite "Namenskommunikation"** die folgenden (erforderlichen) Kommunikationsdetails an.

    - **Name**: Dies ist der Name für die Kommunikation.

    - **Ausstellende Mitarbeiter:** In der Dropdownliste wird eine Liste der Fallmitglieder angezeigt. Weitere Informationen zum Hinzufügen neuer Mitglieder zu einem Fall finden Sie unter [Erstellen eines Advanced eDiscovery-Falls.](create-and-manage-advanced-ediscoveryv2-case.md#create-a-case) Jede Benachrichtigung, die an Verwahrer gesendet wird, wird im Namen des angegebenen ausstellenden Mitarbeiters gesendet.

> [!NOTE]
> Der ausstellende Mitarbeiter muss über ein **aktives Postfach verfügen,** um in der Dropdownliste des ausstellenden Mitarbeiters angezeigt zu werden.


4. Klicken Sie auf **Weiter**.

## <a name="step-2-define-the-portal-content"></a>Schritt 2: Definieren des Portalinhalts

Als Nächstes können Sie den Inhalt des Haltehinweises erstellen und hinzufügen. Geben Sie **auf der Seite "Portalinhalt definieren"** **im** Assistenten zum Erstellen einer Kommunikation den Inhalt des Haltehinweises an. Dieser Inhalt wird automatisch an die Benachrichtigungen "Ausstellungs", "Erneut ausschreiben", "Erinnerung" und "Eskalation" angefügt. Darüber hinaus werden diese Inhalte im Complianceportal des Wahrers angezeigt. 

![Portalinhaltsseite](../media/PortalContent.PNG)

So erstellen Sie den Portalinhalt:

1. Geben Sie Ihren Haltebemerkung aus einem anderen Dokument in das Textfeld für den Portalinhalt ein (oder schneiden sie aus und fügen Sie ihn ein). 

2. Fügen Sie Zusammenführungsvariablen in Ihren Hinweis ein, um den Hinweis anzupassen und das Custodian Compliance Portal frei zu geben.

3. Klicken Sie auf **Weiter**.

  >[!Tip]
  >Weitere Informationen zum Anpassen des Inhalts und Formats des Portalinhalts finden Sie unter [Verwenden des Communications Editors.](using-communications-editor.md)

## <a name="step-3-set-the-required-notifications"></a>Schritt 3: Festlegen der erforderlichen Benachrichtigungen

Nachdem Sie den Inhalt des Haltebereichs definiert haben, können Sie die Workflows zum Senden und Verwalten des Benachrichtigungsprozesses einrichten. Benachrichtigungen sind E-Mail-Nachrichten, die gesendet werden, um Verwahrer zu benachrichtigen und sie weiter zu verfolgen. Jeder zur Kommunikation hinzugefügte Verwahrer erhält dieselbe Benachrichtigung. 

Zum Einrichten und Senden eines Haltehinweises müssen Sie Veröffentlichungs-, Veröffentlichungs- und Veröffentlichungsbenachrichtigungen enthalten.

### <a name="issuance-notification"></a>Ausstellungsbenachrichtigung 

Nachdem die Kommunikation erstellt wurde, wird die **Benachrichtigung** über die Ausstellung vom angegebenen ausstellenden Mitarbeiter initiiert. Die Benachrichtigung über die Ausstellung ist die erste Mitteilung, die an den Wahrer gesendet wird, um ihn über seine Aufbewahrungspflichten zu informieren. 

So erstellen Sie eine Ausstellungsbenachrichtigung:

1. Klicken Sie **in der Kachel "Ausstellungs"** auf **"Bearbeiten".**

2. Fügen Sie gegebenenfalls weitere Fallmitglieder oder Mitarbeiter zu den Feldern **"Cc"** und **"Bcc"** hinzu. Wenn Sie diesen Feldern mehrere Benutzer hinzufügen möchten, trennen Sie E-Mail-Adressen durch einen Semikolon.

3. Geben Sie **den Betreff** für den Hinweis an (erforderlich).

4. Geben Sie den Inhalt oder zusätzliche Anweisungen an, die Sie dem Verwahrer bereitstellen möchten (erforderlich). Der in Schritt 2 definierte Portalinhalt wird am Ende der Benachrichtigung hinzugefügt. 

5. Klicken Sie auf **Speichern**.

### <a name="re-issuance-notification"></a>Re-Issuance Benachrichtigung

Im weiteren Verlauf des Falls müssen Verwahrer möglicherweise zusätzliche oder weniger Daten beibehalten, als zuvor angewiesen wurden. Nachdem Sie den Portalinhalt aktualisiert haben, wird die Benachrichtigung über die erneute Benachrichtigung gesendet und Benachrichtigungen an Wahrer über Änderungen an ihren Aufbewahrungspflichten gesendet.

So erstellen Sie eine Benachrichtigung über die erneute Benachrichtigung:

1. Klicken Sie **in der Kachel "Erneuter Text"** auf **"Bearbeiten".**

2. Fügen Sie gegebenenfalls weitere Fallmitglieder oder Mitarbeiter zu den Feldern **"Cc"** und **"Bcc"** hinzu. Wenn Sie diesen Feldern mehrere Benutzer hinzufügen möchten, trennen Sie E-Mail-Adressen durch einen Semikolon.

3. Geben Sie **den Betreff** für den Hinweis an (erforderlich).

4. Geben Sie den Inhalt oder zusätzliche Anweisungen an, die Sie dem Verwahrer bereitstellen möchten (erforderlich). Die in Schritt 2 definierten Portalinhalte werden am Ende des Benachrichtigungs zur erneuten Ausstellung hinzugefügt.

5. Klicken Sie auf **Speichern**.

> [!NOTE]
> Wenn der Portalinhalt geändert  wird (auf der  Seite "Portalinhalt definieren" im Assistenten zum Bearbeiten der Kommunikation), wird die Erneute Benachrichtigung automatisch an alle Verwahrer gesendet, die dem Hinweis zugewiesen sind. Nachdem die Benachrichtigung gesendet wurde, werden verwahrer aufgefordert, ihre Haltebenachrichtigung erneut zu bestätigen. Wenn Sie Erinnerungs- oder Eskalationsworkflows eingerichtet haben, werden diese ebenfalls neu gestartet. Weitere Informationen dazu, welche anderen Fallverwaltungsereignisse die Kommunikation auslösen, finden Sie unter [Ereignisse, die Benachrichtigungen auslösen.](#events-that-trigger-notifications)

### <a name="release-notification"></a>Benachrichtigung zur Veröffentlichung

Nachdem eine Frage gelöst wurde oder ein Verwahrer nicht mehr der Erhaltung von Inhalten unterliegt, können Sie den Verwahrer aus einem Fall frei lassen. Wenn der Verwahrer zuvor eine Haltebenachrichtigung ausgegeben hat, kann die Freigabebenachrichtigung verwendet werden, um verwahrer zu warnen, dass sie von ihrer Verpflichtung losgelassen wurden.

So erstellen Sie eine Veröffentlichungsbenachrichtigung: 

1. Klicken Sie **auf der Kachel** "Release" auf **"Bearbeiten".**

2. Fügen Sie gegebenenfalls weitere Fallmitglieder oder Mitarbeiter zu den Feldern **"Cc"** und **"Bcc"** hinzu. Wenn Sie diesen Feldern mehrere Benutzer hinzufügen möchten, trennen Sie E-Mail-Adressen durch einen Semikolon.

3. Geben Sie **den Betreff** für den Hinweis an (erforderlich).

4. Geben Sie den Inhalt oder zusätzliche Anweisungen an, die Sie dem Verwahrer bereitstellen möchten (erforderlich).

5. Klicken Sie **auf "Speichern",** und fahren Sie mit dem nächsten Schritt fort.

## <a name="optional-step-4-set-the-optional-notifications"></a>(Optional) Schritt 4: Festlegen der optionalen Benachrichtigungen

Optional können Sie den Workflow für die Nachbesprechung mit nicht reagierenden Verwahrern vereinfachen, indem Sie automatisierte Erinnerungs- und Eskalationsbenachrichtigungen erstellen und planen.

![Erinnerungs-/Eskalationsseite](../media/ReminderEscalations.PNG)

### <a name="reminders"></a>Erinnerungen

Nachdem Sie eine Haltebereichsbenachrichtigung gesendet haben, können Sie sich an nicht reagierende Verwahrer halten, indem Sie einen Erinnerungsworkflow definieren.

So planen Sie Erinnerungen:

1. Klicken Sie **auf der Kachel "Erinnerung"** auf **"Bearbeiten".**

2. Aktivieren Sie den **Erinnerungsworkflow,** indem Sie die **Statusschaltleiste** (erforderlich) aktivieren.

3. Angeben des **Erinnerungsintervalls (in Tagen)** (erforderlich). Dies ist die Anzahl der Tage, die gewartet werden muss, bevor die ersten und nach dem Senden von Erinnerungsbenachrichtigungen gesendet werden. Wenn Sie z. B. das Erinnerungsintervall auf sieben Tage festlegen, wird die erste Erinnerung sieben Tage nach der ursprünglichen Benachrichtigung gesendet. Alle nachfolgenden Erinnerungen werden ebenfalls alle sieben Tage gesendet.

4. Geben Sie **die Anzahl der Erinnerungen an** (erforderlich). Dieses Feld gibt an, wie viele Erinnerungen an nicht reagierende Verwahrer gesendet werden. Wenn Sie beispielsweise die Anzahl der Erinnerungen auf 3 festlegen, erhält ein Verwahrer maximal drei Erinnerungen. Nachdem ein Wahrer die Haltebereichsbenachrichtigung bestätigt hat, werden keine Erinnerungen mehr an den Benutzer gesendet.

5. Geben Sie **den Betreff** für den Hinweis an (erforderlich). 

6. Geben Sie den Inhalt oder zusätzliche Anweisungen an, die Sie dem Verwahrer bereitstellen möchten (erforderlich). Der in Schritt 2 definierte Portalinhalt wird am Ende des Erinnerungshinweises hinzugefügt.

7. Klicken Sie **auf "Speichern",** und fahren Sie mit dem nächsten Schritt fort.

### <a name="escalations"></a>Eskalationen

In einigen Situationen benötigen Sie möglicherweise zusätzliche Möglichkeiten, um mit nicht reagierenden Verwahrern nachzuverschieben. Wenn ein Verwalter eine Haltebenachrichtigung nach Erhalt der angegebenen Anzahl von Erinnerungen nicht bestätigt, kann das Rechtsteam einen Workflow angeben, um automatisch eine Eskalationsbenachrichtigung an den Verwahrer und seinen Vorgesetzten zu senden.

So planen Sie Eskalationen:

1. Klicken Sie **in der Kachel "Eskalation"** auf **"Bearbeiten".**

2. Aktivieren Sie den **Eskalationsworkflow,** indem Sie die **Statusschaltleiste** aktivieren.

3. Geben Sie das **Eskalationsintervall (in Tagen)** an (erforderlich).

4. Geben Sie **die Anzahl der Eskalationen** an (erforderlich). Dieses Feld gibt an, wie viele Eskalationen an nicht reagierende Verwahrer gesendet werden. Wenn Sie beispielsweise die Anzahl der Eskalationen auf 3 festlegen, wird maximal dreimal eine Eskalationsbenachrichtigung an den Verwalter und seinen Vorgesetzten gesendet. Nachdem ein Wahrer die Haltebereichsbenachrichtigung bestätigt hat, werden keine Eskalationen mehr gesendet.

5. Geben Sie **den Betreff** für den Hinweis an (erforderlich). 

6. Geben Sie den Inhalt oder zusätzliche Anweisungen an, die Sie dem Verwahrer bereitstellen möchten (erforderlich). Die in Schritt 2 definierten Portalinhalte werden am Ende der Eskalationsbenachrichtigung hinzugefügt.

7. Klicken Sie **auf "Speichern",** und fahren Sie mit dem nächsten Schritt fort.

## <a name="step-5-assign-custodians-to-receive-notifications"></a>Schritt 5: Zuweisen von Verwahrern zum Empfangen von Benachrichtigungen

Wählen Sie nach Abschluss des Inhalts für Benachrichtigungen die Verwahrer aus, an die Sie Benachrichtigungen senden möchten. 

![Seite "Wahrer auswählen"](../media/SelectCustodians.PNG)

So fügen Sie Verwahrer hinzu:

1. Weisen Sie der Kommunikation Verwahrer zu, indem Sie auf das Kontrollkästchen neben ihrem Namen klicken.

    Nachdem die Kommunikation erstellt wurde, gilt der Benachrichtigungsworkflow automatisch für die ausgewählten Verwahrer.

2. Klicken **Sie auf "Weiter",** um die Kommunikationseinstellungen und -details zu überprüfen.

>[!NOTE]
>Sie können nur Verwahrer hinzufügen, die dem Fall hinzugefügt wurden und in dem Fall keine weitere Benachrichtigung erhalten haben.

## <a name="step-6-review-settings"></a>Schritt 6: Überprüfen der Einstellungen

Nachdem Sie die Einstellungen  überprüft und auf "Senden" geklickt haben, um die Kommunikation zu vervollständigen, startet das System automatisch den Kommunikationsworkflow, indem der Benachrichtigungsmitteilung gesendet wird.

## <a name="events-that-trigger-notifications"></a>Ereignisse, die Benachrichtigungen auslösen

In der folgenden Tabelle werden Ereignisse im Fallverwaltungsprozess beschrieben, die ausgelöst werden, wenn die verschiedenen Arten von Benachrichtigungen an Verwahrer gesendet werden.

|Art der Kommunikation|Auslöser |
|:---------|:---------|
|Benachrichtigungen zur Ausstellung|Die anfängliche Erstellung der Benachrichtigung. Sie können eine Haltebereichsbenachrichtigung auch manuell erneut senden. |
|Erneutes Aufkündigen von Benachrichtigungen|Aktualisieren des Portalinhalts auf der Seite **"Portalinhalt** definieren" im Assistenten zum Bearbeiten **der** Kommunikation.|
|Veröffentlichungshinweise|Der Verwahrer wird aus dem Fall freigelassen.|
|Erinnerungen|Das Intervall und die Anzahl der Erinnerungen, die für die Erinnerung konfiguriert sind.|
|Eskalationen|Das Intervall und die Anzahl der Erinnerungen, die für die Eskalation konfiguriert sind.|
|||
