---
title: Administratorübermittlungen
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie das Übermittlungsportal im Microsoft 365 Security Center verwenden, um verdächtige E-Mails, verdächtige Phishing-E-Mails, Spam und andere potenziell schädliche Nachrichten, URLs und E-Mail-Anlagen zur erneuten Überprüfung an Microsoft zu senden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6de6a018a96407a5690249bea15e90c2f5a0d1ed
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878688"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>Verwenden von Administrator-Übermittlung, um verdächtige Spam- oder Phishing-Nachrichten, URLs und Dateien an Microsoft zu übermitteln

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)


In Microsoft 365 Organisationen mit Postfächern in Exchange Online können Administratoren das Übermittlungsportal im Security & Compliance Center verwenden, um E-Mail-Nachrichten, URLs und Anlagen zur Überprüfung an Microsoft zu senden.

Wenn Sie eine E-Mail-Nachricht übermitteln, erhalten Sie Folgendes:

1. **E-Mail-Authentifizierungsprüfung:** Details dazu, ob die E-Mail-Authentifizierung bei der Zustellung erfolgreich war oder fehlgeschlagen ist.
2. **Richtlinientreffer:** Informationen zu allen Richtlinien, die eingehende E-Mails in Ihrem Mandanten möglicherweise zugelassen oder blockiert haben, und überschreiben unsere Dienstfilterbewertungen.
3. **Nutzlastreputation/-detonation:** Untersuchung aller URLs und Anlagen in der Nachricht.
4. **Benotungsanalyse:** Überprüfung durch Benotungsprüfer, um zu überprüfen, ob Nachrichten bösartig sind oder nicht.

> [!IMPORTANT]
> Nutzlastreputation/-detonation und Bewertungsanalyse werden nicht in allen Mandanten durchgeführt. Informationen werden daran gehindert, sich außerhalb der Organisation zu befinden, wenn Daten die Mandantengrenze nicht zu Compliancezwecken verlassen sollen.

Weitere Möglichkeiten zum Übermitteln von E-Mail-Nachrichten, URLs und Anlagen an Microsoft finden Sie unter "Melden von [Nachrichten und Dateien an Microsoft".](report-junk-email-messages-to-microsoft.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Microsoft 365 Security Center unter <https://security.microsoft.com/> . Um direkt zur Seite **"Übermittlungen"** zu wechseln, verwenden Sie <https://security.microsoft.com/reportsubmission> .

- Um Nachrichten und Dateien an Microsoft zu übermitteln, müssen Sie Mitglied einer der folgenden Rollengruppen sein:

  - **Organisationsverwaltung** oder **Sicherheitsleseberechtigter** im [Microsoft 365 Security Center.](permissions-microsoft-365-security-center.md)

  - **Organisationsverwaltung** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).

    Beachten Sie, dass die Mitgliedschaft in dieser Rollengruppe erforderlich ist, um [Benutzerübermittlungen an das benutzerdefinierte Postfach anzuzeigen,](#view-user-submissions-to-the-custom-mailbox) wie weiter unten in diesem Artikel beschrieben.

- Weitere Informationen dazu, wie Benutzer Nachrichten und Dateien an Microsoft übermitteln können, finden Sie unter ["Melden von Nachrichten und Dateien an Microsoft".](report-junk-email-messages-to-microsoft.md)

## <a name="report-suspicious-content-to-microsoft"></a>Melden verdächtiger Inhalte an Microsoft

1. Wechseln Sie im [Microsoft 365 Security Center](../defender/overview-security-center.md)zu **"Übermittlungen",** und überprüfen Sie, ob Sie sich auf der Registerkarte **"Zur Analyse übermittelt"** befinden, und klicken Sie dann zur Überprüfung auf **"An Microsoft übermitteln".**

2. Verwenden Sie das Flyout **"An Microsoft übermitteln" zum Überprüfen** des Flyouts, das die Nachricht, URL oder E-Mail-Anlage wie in den folgenden Abschnitten beschrieben zu übermitteln scheint.

### <a name="submit-a-questionable-email-to-microsoft"></a>Senden einer fragebaren E-Mail an Microsoft

1. Wählen Sie im Abschnitt **"Übermittlungstyp auswählen" die** Option **"E-Mail**" aus. Verwenden Sie im Abschnitt **"Netzwerknachrichten-ID hinzufügen" oder "E-Mail-Datei hochladen"** eine der folgenden Optionen:

   - **Fügen Sie die E-Mail-Netzwerknachrichten-ID** hinzu: Dies ist ein GUID-Wert, der im **X-MS-Exchange-Organization-Network-Message-Id-Header** in der Nachricht oder im **X-MS-Office365-Filtering-Correlation-Id-Header** in isolierten Nachrichten verfügbar ist.

   - **Hochladen die E-Mail-Datei:** Klicken Sie auf **"Dateien durchsuchen".** Suchen Sie im daraufhin geöffneten Dialogfeld die EML- oder MSG-Datei, und wählen Sie sie aus, und klicken Sie dann auf **"Öffnen".**

   > [!NOTE]
   > Die Möglichkeit, Nachrichten ab 30 Tagen zu übermitteln, wurde für Defender für Office 365 Kunden vorübergehend ausgesetzt. Administratoren können nur 7 Tage zurückkehren.

2. Geben Sie im Abschnitt **"Empfänger auswählen, der ein Problem hatte"** den Empfänger an, für den Sie eine Richtlinienüberprüfung ausführen möchten. Die Richtlinienüberprüfung bestimmt, ob die Überprüfung durch die E-Mail aufgrund von Benutzer- oder Organisationsrichtlinien umgangen wurde.

3. Wählen Sie im Abschnitt **"Auswählen eines Grunds für die Übermittlung an Microsoft"** eine der folgenden Optionen aus:

   - **Sollte nicht blockiert worden sein**

   - **Sollte blockiert worden sein:** Wählen Sie **Spam,** **Phishing** oder **Schadsoftware** aus. Wenn Sie nicht sicher sind, verwenden Sie Ihr bestes Ermessen.

4. Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **"Absenden".**

   ![Beispiel für neue URL-Übermittlung](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>Senden einer verdächtigen URL an Microsoft

1. Wählen Sie im Abschnitt **"Übermittlungstyp auswählen" die** **URL** aus. Geben Sie in das angezeigte Feld die vollständige URL ein (z. B. `https://www.fabrikam.com/marketing.html` ).

2. Wählen Sie im Abschnitt **"Grund für Übermittlung"** eine der folgenden Optionen aus:

   - **Sollte nicht blockiert worden sein**

   - Sollte blockiert worden sein: **Phishing** oder **Schadsoftware** auswählen. 

3. Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **"Absenden".**

   ![Beispiel für neue E-Mail-Übermittlung](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a>Übermitteln einer verdächtigen E-Mail-Anlage an Microsoft

1. Wählen Sie im Abschnitt **"Übermittlungstyp auswählen" die** Option **E-Mail-Anlage** aus.

2. Klicken Sie auf **"Datei auswählen".** Suchen Sie im daraufhin geöffneten Dialogfeld die Datei, wählen Sie sie aus, und klicken Sie dann auf **"Öffnen".**

3. Wählen Sie im Abschnitt **"Grund für Übermittlung"** eine der folgenden Optionen aus:

   - **Sollte nicht blockiert worden sein**

   - **Sollte blockiert worden sein:** **Schadsoftware** ist die einzige Wahl und wird automatisch ausgewählt.

4. Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **"Absenden".**

   ![Beispiel für die Übermittlung neuer Anlagen](../../media/submission-file-flyout.PNG)

## <a name="view-items-submitted-for-analysis"></a>Anzeigen von Elementen, die für die Analyse übermittelt wurden

Wechseln Sie im Microsoft 365 Security Center zu **Übermittlungen,** und vergewissern Sie sich, dass Sie sich auf der Registerkarte **"Zur Analyse übermittelt"** befinden.

In der Befehlsleiste in der Mitte der Seite können Sie ein Startdatum, ein Enddatum eingeben und (standardmäßig) sie können nach **Übermittlungs-ID** (einem GUID-Wert, der jeder Übermittlung zugewiesen ist) filtern, indem Sie einen Wert in das Feld eingeben und auf ![ die Schaltfläche "Aktualisieren" ](../../media/scc-quarantine-refresh.png) klicken. Mehrere Werte können durch Kommata getrennt eingegeben werden.

Um die Filterkriterien zu ändern, klicken Sie auf die Schaltfläche **"Filter",** und wählen Sie einen der folgenden Werte aus:

- **Sender**
- **Betreff/URL/Dateiname**
- **Übermittelt von**
- **Übermittlungstyp**
- **Status**

![Neue Filteroptionen für Administratorübermittlungen](../../media/admin-submission-email-filter-options.png)

Um die Ergebnisse zu exportieren, klicken Sie oben auf der Seite auf **"Exportieren",** und wählen Sie **Diagrammdaten** oder **Tabelle** aus. Speichern Sie im daraufhin angezeigten Dialogfeld die .csv Datei.

Unterhalb des Diagramms befinden sich drei Registerkarten: **E-Mail** (Standard), **URL** und **E-Mail-Anlage.**

### <a name="view-admin-email-submissions"></a>Anzeigen von Administrator-E-Mail-Übermittlungen

Sie können auf die Schaltfläche **"Spalten anpassen"** am unteren Rand der Seite klicken, um Der Ansicht Spalten hinzuzufügen oder daraus zu entfernen:

- **Date**
- **Übermittlungs-ID:** Ein GUID-Wert, der jeder Übermittlung zugewiesen wird.
- **Übermittelt von**<sup>\*</sup>
- **Betreff**<sup>\*</sup>
- **Sender**
- **Sender-IP**<sup>\*</sup>
- **Übermittlungstyp**
- **Übermittlungsgrund**
- **Status**<sup>\*</sup>

  <sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden detaillierte Informationen in einem Flyout angezeigt.

#### <a name="admin-submission-rescan-details"></a>Details zur erneuten Überprüfung der Administratorübermittlung

Nachrichten, die in Administratorübermittlungen übermittelt werden, werden erneut überprüft, und die Ergebnisse werden im Flyout "Übermittlungsdetails" angezeigt:

- Mögliche Fehler in der E-Mail-Authentifizierung des Absenders zum Zeitpunkt der Auslieferung.
- Informationen zu Richtlinientreffern, welche die Bewertung über einer Nachricht beeinflusst oder überschrieben haben könnten.
- Aktuelle Detonationsergebnisse, um festzustellen, ob die in der Nachricht enthaltenen URLs oder Dateien böswillig waren oder nicht.
- Feedback von Benotungsprüfern.

Wenn eine Überschreibung gefunden wurde, sollte der erneute Scan in einigen Minuten abgeschlossen sein. Wenn es kein Problem bei der E-Mail-Authentifizierung gab oder die Zustellung nicht von einer Außerkraftsetzung betroffen war, kann das Feedback von Bewertern bis zu einem Tag dauern.

### <a name="view-admin-url-submissions"></a>Anzeigen von Administrator-URL-Übermittlungen

Klicken Sie auf die **Registerkarte "URL".**

Sie können auf die Schaltfläche **"Spaltenoptionen"** am unteren Rand der Seite klicken, um Der Ansicht Spalten hinzuzufügen oder daraus zu entfernen:

- **Date**
- **Übermittlungs-ID**
- **Übermittelt von**<sup>\*</sup>
- **URL**<sup>\*</sup>
- **Übermittlungstyp**
- **Status**<sup>\*</sup>

  <sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden detaillierte Informationen in einem Flyout angezeigt.

### <a name="view-email-attachment-submissions"></a>Anzeigen von Übermittlungen von E-Mail-Anlagen

Klicken Sie auf die Registerkarte **"Anlagen".**

Sie können auf die Schaltfläche **"Spaltenoptionen"** am unteren Rand der Seite klicken, um Der Ansicht Spalten hinzuzufügen oder daraus zu entfernen:

- **Date**
- **Übermittlungs-ID**
- **Übermittelt von**<sup>\*</sup>
- **Dateiname**<sup>\*</sup>
- **Übermittlungstyp**
- **Status**<sup>\*</sup>

  <sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden detaillierte Informationen in einem Flyout angezeigt.

## <a name="view-user-submissions-to-microsoft"></a>Anzeigen von Benutzerübermittlungen an Microsoft

Wenn Sie das [Add-In "Nachricht melden",](enable-the-report-message-add-in.md)das [Add-In "Phishing melden"](enable-the-report-phish-add-in.md)bereitgestellt haben oder Personen die [integrierte Berichterstellung in Outlook im Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)verwenden, können Sie sehen, welche Benutzer auf der Registerkarte **"Benutzerübermittlungen"** Berichte erstellen.

1. Wechseln Sie im Security & Compliance  Center zu \> **Übermittlungen zur Bedrohungsverwaltung.**

2. Wählen Sie die Registerkarte **"Benutzerübermittlungen" aus,** und klicken Sie dann auf **"Neue Übermittlung".**

Sie können auf die Schaltfläche **"Spaltenoptionen"** am unteren Rand der Seite klicken, um Der Ansicht Spalten hinzuzufügen oder daraus zu entfernen:

- **Übermittelt am**
- **Übermittelt von**<sup>\*</sup>
- **Betreff**<sup>\*</sup>
- **Sender**
- **Sender-IP**<sup>\*</sup>
- **Übermittlungstyp**

<sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden detaillierte Informationen in einem Flyout angezeigt.

Im oberen Bereich der Seite können Sie ein Startdatum, ein Enddatum eingeben und (standardmäßig) nach **Absender** filtern, indem Sie einen Wert in das Feld eingeben und auf die ![ Schaltfläche "Aktualisieren" ](../../media/scc-quarantine-refresh.png) klicken. Mehrere Werte können durch Kommata getrennt eingegeben werden.

Klicken Sie zum Ändern der Filterkriterien auf die Schaltfläche **"Absender",** und wählen Sie einen der folgenden Werte aus:

- **Absenderdomäne**
- **Betreff**
- **Übermittelt von**
- **Übermittlungstyp**
- **Sender-IP**

![Neue Filteroptionen für Benutzerübermittlungen](../../media/user-submissions-filter-options.png)

Um die Ergebnisse zu exportieren, klicken Sie oben auf der Seite auf **"Exportieren",** und wählen Sie **Diagrammdaten** oder **Tabelle** aus. Speichern Sie im daraufhin angezeigten Dialogfeld die .csv Datei.

## <a name="view-user-submissions-to-the-custom-mailbox"></a>Anzeigen von Benutzerübermittlungen an das benutzerdefinierte Postfach

**Wenn** Sie [ein benutzerdefiniertes Postfach für](user-submission.md) den Empfang von vom Benutzer gemeldeten Nachrichten konfiguriert haben, können Sie Nachrichten anzeigen und auch senden, die an das Berichtspostfach übermittelt wurden.

1. Wechseln Sie im Security & Compliance  Center zu \> **Übermittlungen zur Bedrohungsverwaltung.**

2. Wählen Sie die Registerkarte **"Benutzerdefiniertes Postfach"** aus.

Sie können auf die Schaltfläche **"Spaltenoptionen"** am unteren Rand der Seite klicken, um Der Ansicht Spalten hinzuzufügen oder daraus zu entfernen:

- **Übermittelt am**
- **Übermittelt von**<sup>\*</sup>
- **Betreff**<sup>\*</sup>
- **Sender**
- **Sender-IP**<sup>\*</sup>
- **Übermittlungstyp**

Am oberen Rand der Seite können Sie ein Startdatum, ein Enddatum eingeben und nach **"Übermittelt"** filtern, indem Sie einen Wert in das Feld eingeben und auf die ![ Schaltfläche "Aktualisieren" ](../../media/scc-quarantine-refresh.png) klicken. Mehrere Werte können durch Kommata getrennt eingegeben werden.

Um die Ergebnisse zu exportieren, klicken Sie oben auf der Seite auf **"Exportieren",** und wählen Sie **Diagrammdaten** oder **Tabelle** aus. Speichern Sie im daraufhin angezeigten Dialogfeld die .csv Datei.

> [!NOTE]
> Wenn Organisationen so konfiguriert sind, dass sie nur an ein benutzerdefiniertes Postfach senden, werden gemeldete Nachrichten nicht zur erneuten Überprüfung gesendet, und die Ergebnisse im Portal für vom Benutzer gemeldete Nachrichten sind immer leer.

## <a name="undo-user-submissions"></a>Rückgängigmachen von Benutzerübermittlungen

Sobald ein Benutzer eine verdächtige E-Mail an das benutzerdefinierte Postfach sendet, haben der Benutzer und der Administrator keine Möglichkeit, die Übermittlung rückgängig zu machen. Wenn der Benutzer die E-Mail wiederherstellen möchte, steht sie für die Wiederherstellung in den Ordnern "Gelöschte Elemente" oder "Junk-E-Mail" zur Verfügung.

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>Senden von Nachrichten aus dem benutzerdefinierten Postfach an Microsoft

Wenn Sie das benutzerdefinierte Postfach so konfiguriert haben, dass von Benutzern gemeldete Nachrichten abgefangen werden, ohne die Nachrichten an Microsoft zu senden, können Sie bestimmte Nachrichten suchen und zur Analyse an Microsoft senden. Dadurch wird eine Benutzerübermittlung effektiv an eine Administratorübermittlung verschoben.

Wählen Sie auf der Registerkarte **"Vom Benutzer gemeldete Nachrichten"** eine Nachricht in der Liste aus, klicken Sie auf die Schaltfläche **"Aktion",** und wählen Sie eine der folgenden Optionen aus:

- **Bericht sauber**
- **Melden von Phishing**
- **Melden von Schadsoftware**
- **Melden von Spam**

![Neue Optionen auf der Schaltfläche "Aktion"](../../media/user-submission-custom-mailbox-action-button.png)
