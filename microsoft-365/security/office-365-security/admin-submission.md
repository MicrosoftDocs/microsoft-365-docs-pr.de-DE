---
title: Administratorübermittlungen
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie das Übermittlungsportal im Security & Compliance Center verwenden, um verdächtige E-Mails, verdächtige Phishing-E-Mails, Spam und andere potenziell schädliche Nachrichten, URLs und Dateien zur Überprüfung an Microsoft zu übermitteln.
ms.openlocfilehash: 432a245530d7906ae8babbc54176480d36315351
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "49864948"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>Verwenden von Administrator-Übermittlung, um verdächtige Spam- oder Phishing-Nachrichten, URLs und Dateien an Microsoft zu übermitteln

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-Organisationen mit Postfächern in Exchange Online können Administratoren das Übermittlungsportal im Security & Compliance Center verwenden, um E-Mail-Nachrichten, URLs und Anlagen zur Überprüfung an Microsoft zu übermitteln.

Wenn Sie eine E-Mail übermitteln, erhalten Sie Informationen zu allen Richtlinien, die die eingehende E-Mail möglicherweise in Ihren Mandanten zugelassen haben, sowie zur Untersuchung aller URLs und Anlagen in der E-Mail. Zu den Richtlinien, die eine E-Mail möglicherweise zugelassen haben, gehören die Liste sicherer Absender eines einzelnen Benutzers sowie Richtlinien auf Mandantenebene wie Exchange-Nachrichtenflussregeln (auch als Transportregeln bekannt).

Weitere Möglichkeiten zum Senden von E-Mail-Nachrichten, URLs und Anlagen an Microsoft finden Sie unter "Nachrichten und Dateien an [Microsoft melden".](report-junk-email-messages-to-microsoft.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Um direkt zur **Übermittlungsseite zu** wechseln, verwenden Sie <https://protection.office.com/reportsubmission> .

- Um Nachrichten und Dateien an Microsoft zu übermitteln, müssen Sie Mitglied einer der folgenden Rollengruppen sein:

  - **Organisationsverwaltung** oder **Sicherheitsadministrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

  - **Organisationsverwaltung** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

    Beachten Sie, dass die Mitgliedschaft [](#view-user-submissions-to-the-custom-mailbox) in dieser Rollengruppe erforderlich ist, um Benutzerübermittlungen an das benutzerdefinierte Postfach wie weiter unten in diesem Artikel beschrieben anzeigen zu können.

- Weitere Informationen dazu, wie Benutzer Nachrichten und Dateien an Microsoft übermitteln können, finden Sie unter "Nachrichten und Dateien an [Microsoft melden".](report-junk-email-messages-to-microsoft.md)

## <a name="report-suspicious-content-to-microsoft"></a>Verdächtige Inhalte an Microsoft melden

1. Wechseln Sie im Security & Compliance  Center zu "Übermittlungen zur \> **Bedrohungsverwaltung",** vergewissern Sie sich, dass Sie auf der Registerkarte **"Administratorübermittlungen"** sind, und klicken Sie dann auf **"Neue Übermittlung".**

2. Verwenden **Sie das Flyout "Neue** Übermittlung", das wie in den folgenden Abschnitten beschrieben angezeigt wird, um die Nachricht, URL oder Anlage zu übermitteln.

### <a name="submit-a-questionable-email-to-microsoft"></a>Senden einer fragwürdigen E-Mail an Microsoft

1. Wählen Sie **im Abschnitt "Objekttyp"** die Option **"E-Mail" aus.** Verwenden Sie **im Abschnitt** "Übermittlungsformat" eine der folgenden Optionen:

   - **Netzwerknachrichten-ID:** Dies ist ein GUID-Wert, der im **X-MS-Exchange-Organization-Network-Message-Id-Header** in der Nachricht oder im **X-MS-Office365-Filtering-Correlation-Id-Header** in isolierten Nachrichten verfügbar ist.

   - **Datei**: Klicken Sie **auf Datei auswählen**. Suchen Sie im dialogfeld, das geöffnet wird, die EML- oder MSG-Datei, und wählen Sie sie aus, und klicken Sie dann auf **Öffnen**.

   > [!NOTE]
   > Administratoren mit Defender für Office 365 Plan 1 oder Plan 2 können Nachrichten übermitteln, die 30 Tage alt sind. Andere Administratoren können nur 7 Tage zurück gehen.

2. Geben Sie **im** Abschnitt "Empfänger" einen oder mehrere Empfänger an, für die Sie eine Richtlinienüberprüfung ausführen möchten. Die Richtlinienüberprüfung bestimmt, ob die Überprüfung per E-Mail aufgrund von Benutzer- oder Organisationsrichtlinien umgangen wurde.

3. Wählen Sie **im Abschnitt "Gründe für die** Übermittlung" eine der folgenden Optionen aus:

   - **Sollte nicht blockiert worden sein**

   - **Sollte blockiert worden sein:** Wählen **Sie Spam,** **Phishing** oder **Schadsoftware aus.** Wenn Sie nicht sicher sind, verwenden Sie Ihre beste Einschätzung.

4. Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **"Absenden".**

![Beispiel für die URL-Übermittlung](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>Senden einer verdächtigen URL an Microsoft

1. Wählen Sie **im Abschnitt "Objekttyp"** **die URL aus.** Geben Sie in das angezeigte Feld die vollständige URL ein (z. B. `https://www.fabrikam.com/marketing.html` ).

2. Wählen Sie **im Abschnitt "Gründe für die** Übermittlung" eine der folgenden Optionen aus:

   - **Sollte nicht blockiert worden sein**

   - **Sollte blockiert worden sein:** Wählen Sie **Phishing oder** **Schadsoftware aus.**

3. Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **"Absenden".**

![Beispiel für die E-Mail-Übermittlung](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a>Übermitteln einer verdächtigen Datei an Microsoft

1. Wählen Sie **im Abschnitt "Objekttyp"** die Option **"Anlage" aus.**

2. Klicken Sie **auf Datei auswählen**. Suchen Sie im dialogfeld, das geöffnet wird, die Datei, und wählen Sie sie aus, und klicken Sie dann auf **Öffnen**.

3. Wählen Sie **im Abschnitt "Gründe für die** Übermittlung" eine der folgenden Optionen aus:

   - **Sollte nicht blockiert worden sein**

   - **Sollte blockiert worden sein:** **Schadsoftware** ist die einzige Wahl und wird automatisch ausgewählt.

4. Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **"Absenden".**

![Beispiel für Anlagenübermittlung](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a>Anzeigen von Administratorübermittlungen

Wechseln Sie im Security & Compliance  Center zu "Übermittlungen zur \> **Bedrohungsverwaltung",** vergewissern Sie sich, dass Sie auf der Registerkarte **"Administratorübermittlungen"** sind, und klicken Sie dann auf **"Neue Übermittlung".**

Im oberen Seitenanfang können Sie ein Startdatum, ein Enddatum und (standardmäßig)  einen Filter nach Übermittlungs-ID (einem GUID-Wert, der jeder Übermittlung zugewiesen ist) eingeben, indem Sie einen Wert in das Feld eingeben und auf die Schaltfläche "Aktualisieren" ![ ](../../media/scc-quarantine-refresh.png) klicken. Update

Um die Filterkriterien zu ändern, klicken Sie auf die Schaltfläche **"Übermittlungs-ID",** und wählen Sie einen der folgenden Werte aus:

- **Sender**
- **Betreff/URL/Dateiname**
- **Übermittelt von**
- **Übermittlungstyp**
- **Status**

![Filteroptionen für Administratorübermittlungen](../../media/admin-submission-email-filter-options.png)

Zum Exportieren der Ergebnisse klicken **Sie** oben auf der Seite auf "Exportieren", und wählen Sie **Diagrammdaten** oder **Tabelle aus.** Speichern Sie im angezeigten Dialogfeld die CSV-Datei.

Unterhalb des Diagramms gibt es drei Registerkarten: **E-Mail** (Standard), **URL** und **Anlage**.

### <a name="view-admin-email-submissions"></a>Anzeigen von Administrator-E-Mail-Übermittlungen

Klicken Sie auf die **Registerkarte "E-Mail".**

Sie können auf die Schaltfläche **"Spaltenoptionen"** am unteren Rand der Seite klicken, um Spalten in der Ansicht hinzuzufügen oder zu entfernen:

- **Date**
- **Übermittlungs-ID:** Ein GUID-Wert, der jeder Übermittlung zugewiesen ist.
- **Übermittelt von**<sup>\*</sup>
- **Betreff**<sup>\*</sup>
- **Sender**
- **Sender-IP**<sup>\*</sup>
- **Übermittlungstyp**
- **Zustellungsgrund**
- **Status**<sup>\*</sup>

  <sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden detaillierte Informationen in einem Flyout angezeigt.

#### <a name="admin-submission-rescan-details"></a>Details zur erneuten Eingabe der Administratorübermittlung

Nachrichten, die in Administratorübermittlungen übermittelt werden, werden erneut überprüft, und die Ergebnisse werden im Detailf flyout angezeigt:

- Wenn bei der E-Mail-Authentifizierung des Absenders zum Zeitpunkt der Zustellung ein Fehler aufting.
- Informationen zu allen Richtlinientreffern, die die Entscheidung einer Nachricht beeinflusst oder außer Kraft gesetzt haben könnten.
- Aktuelle Ergebnisse der Detonation, um zu sehen, ob die URLs oder Dateien in der Nachricht bösartig waren oder nicht.
- Feedback von Benotungsgebern.

Wenn eine Außerkraftsetzung gefunden wurde, sollte die Erneutes Scannen in einigen Minuten abgeschlossen sein. Wenn kein Problem bei der E-Mail-Authentifizierung oder Zustellung von einer Außerkraftsetzung betroffen war, kann das Feedback der Benotungsbesteller bis zu einem Tag dauern.

### <a name="view-admin-url-submissions"></a>Anzeigen von Admin-URL-Übermittlungen

Klicken Sie auf **die Registerkarte "URL".**

Sie können auf die Schaltfläche **"Spaltenoptionen"** am unteren Rand der Seite klicken, um Spalten in der Ansicht hinzuzufügen oder zu entfernen:

- **Date**
- **Übermittlungs-ID**
- **Übermittelt von**<sup>\*</sup>
- **URL**<sup>\*</sup>
- **Übermittlungstyp**
- **Status**<sup>\*</sup>

  <sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden detaillierte Informationen in einem Flyout angezeigt.

### <a name="view-admin-attachment-submissions"></a>Anzeigen von Administrator-Anlagenübermittlungen

Klicken Sie auf die **Registerkarte "Anlagen".**

Sie können auf die Schaltfläche **"Spaltenoptionen"** am unteren Rand der Seite klicken, um Spalten in der Ansicht hinzuzufügen oder zu entfernen:

- **Date**
- **Übermittlungs-ID**
- **Übermittelt von**<sup>\*</sup>
- **Dateiname**<sup>\*</sup>
- **Übermittlungstyp**
- **Status**<sup>\*</sup>

  <sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden detaillierte Informationen in einem Flyout angezeigt.

## <a name="view-user-submissions-to-microsoft"></a>Anzeigen von Benutzerübermittlungen an Microsoft

Wenn Sie das Report [Message-Add-In,](enable-the-report-message-add-in.md)das [Phishing-Add-In](enable-the-report-phish-add-in.md)"Melden" oder Personen, die die integrierte Berichterstellung in  [Outlook im Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)verwenden, bereitgestellt haben, können Sie auf der Registerkarte "Benutzerübermittlungen" anzeigen, welche Benutzer berichte.

1. Wechseln Sie im Security & Compliance Center zu **"Übermittlungen zur** \> **Bedrohungsverwaltung".**

2. Wählen Sie **die Registerkarte "Benutzerübermittlungen"** aus, und klicken Sie dann auf **"Neue Übermittlung".**

Sie können auf die Schaltfläche **"Spaltenoptionen"** am unteren Rand der Seite klicken, um Spalten in der Ansicht hinzuzufügen oder zu entfernen:

- **Übermittelt am**
- **Übermittelt von**<sup>\*</sup>
- **Betreff**<sup>\*</sup>
- **Sender**
- **Sender-IP**<sup>\*</sup>
- **Übermittlungstyp**

<sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden detaillierte Informationen in einem Flyout angezeigt.

Im oberen Seitenanfang können Sie ein Startdatum, ein Enddatum und (standardmäßig) einen Filter nach **Absender** eingeben, indem Sie einen Wert in das Feld eingeben und auf die Schaltfläche Aktualisieren ![ ](../../media/scc-quarantine-refresh.png) klicken. Update

Um die Filterkriterien zu ändern, klicken Sie auf die Schaltfläche **"Absender",** und wählen Sie einen der folgenden Werte aus:

- **Absenderdomäne**
- **Betreff**
- **Übermittelt von**
- **Übermittlungstyp**
- **Sender-IP**

![Filteroptionen für Benutzerübermittlungen](../../media/user-submissions-filter-options.png)

Zum Exportieren der Ergebnisse klicken **Sie** oben auf der Seite auf "Exportieren", und wählen Sie **Diagrammdaten** oder **Tabelle aus.** Speichern Sie im angezeigten Dialogfeld die CSV-Datei.

## <a name="view-user-submissions-to-the-custom-mailbox"></a>Anzeigen von Benutzerübermittlungen an das benutzerdefinierte Postfach

**Wenn** Sie ein [benutzerdefiniertes](user-submission.md) Postfach für den Empfang von vom Benutzer gemeldeten Nachrichten konfiguriert haben, können Sie auch Nachrichten anzeigen und übermitteln, die an das Berichtspostfach zugestellt wurden.

1. Wechseln Sie im Security & Compliance Center zu **"Übermittlungen zur** \> **Bedrohungsverwaltung".**

2. Wählen Sie die **Registerkarte "Benutzerdefiniertes Postfach"** aus.

Sie können auf die Schaltfläche **"Spaltenoptionen"** am unteren Rand der Seite klicken, um Spalten in der Ansicht hinzuzufügen oder zu entfernen:

- **Übermittelt am**
- **Übermittelt von**<sup>\*</sup>
- **Betreff**<sup>\*</sup>
- **Sender**
- **Sender-IP**<sup>\*</sup>
- **Übermittlungstyp**

Im oberen Seitenanfang können Sie ein Startdatum, ein Enddatum eingeben  und nach "Übermittelt" filtern, indem Sie einen Wert in das Feld eingeben und auf die Schaltfläche ![ "Aktualisieren" ](../../media/scc-quarantine-refresh.png) klicken. Update

Zum Exportieren der Ergebnisse klicken **Sie** oben auf der Seite auf "Exportieren", und wählen Sie **Diagrammdaten** oder **Tabelle aus.** Speichern Sie im angezeigten Dialogfeld die CSV-Datei.

## <a name="undo-user-submissions"></a>Rückgängig machen von Benutzerübermittlungen

Sobald ein Benutzer eine verdächtige E-Mail an das benutzerdefinierte Postfach übermittelt hat, haben der Benutzer und der Administrator keine Möglichkeit, die Übermittlung rückgängig zu machen. Wenn der Benutzer die E-Mail wiederherstellen möchte, steht sie für die Wiederherstellung in den Ordnern "Gelöschte Elemente" oder "Junk-E-Mail" zur Verfügung.

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>Senden von Nachrichten aus dem benutzerdefinierten Postfach an Microsoft

Wenn Sie das benutzerdefinierte Postfach so konfiguriert haben, dass von Benutzern gemeldete Nachrichten abgefangen werden, ohne die Nachrichten an Microsoft zu senden, können Sie bestimmte Nachrichten zur Analyse finden und an Microsoft senden. Dadurch wird eine Benutzerübermittlung effektiv in eine Administratorübermittlung verlagert.

Wählen Sie auf der Registerkarte **"Benutzerdefiniertes**  Postfach" eine Nachricht in der Liste aus, klicken Sie auf die Schaltfläche "Aktion", und treffen Sie eine der folgenden Optionen:

- **Bereinigen des Berichts**
- **Melden von Phishing**
- **Melden von Schadsoftware**
- **Melden von Spam**

![Optionen auf der Schaltfläche "Aktion"](../../media/user-submission-custom-mailbox-action-button.png)
