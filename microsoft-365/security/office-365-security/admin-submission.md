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
description: Administratoren können erfahren, wie Sie das Übermittlungsportal im Security & Compliance Center verwenden, um verdächtige E-Mails, verdächtige Phishing-E-Mails, Spam und andere potenziell schädliche Nachrichten, URLs und Dateien zur Überprüfung an Microsoft zu übermitteln.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d0b91808aa9008f467f66b8200f2c05a120fbcd9
ms.sourcegitcommit: 794f9767aaebe13ab1aead830b214ea674289d19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52107230"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>Verwenden von Administrator-Übermittlung, um verdächtige Spam- oder Phishing-Nachrichten, URLs und Dateien an Microsoft zu übermitteln

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)


In Microsoft 365 Organisationen mit Postfächern in Exchange Online können Administratoren das Übermittlungsportal im Security & Compliance Center verwenden, um E-Mail-Nachrichten, URLs und Anlagen zur Überprüfung an Microsoft zu übermitteln.

Wenn Sie eine E-Mail-Nachricht übermitteln, erhalten Sie:

1. **E-Mail-Authentifizierungsprüfung:** Details dazu, ob die E-Mail-Authentifizierung bei der Zugestellten bestanden oder fehlgeschlagen ist.
2. **Richtlinientreffer**: Informationen zu allen Richtlinien, die die eingehenden E-Mails möglicherweise in Ihrem Mandanten zugelassen oder blockiert haben, und überschreiben unsere Dienstfilter-Urteile.
3. **Nutzlast reputation/detonation**: Prüfung aller URLs und Anlagen in der Nachricht.
4. **Analyse der** Benotung: Überprüfen Sie, ob Nachrichten bösartig sind oder nicht.

> [!IMPORTANT]
> Die Nutzlastre reputation/detonation und grader analysis werden nicht in allen Mandanten durchgeführt. Es wird verhindert, dass Informationen außerhalb der Organisation bleiben, wenn Daten die Mandantengrenze nicht aus Compliancegründen verlassen sollen.

Weitere Möglichkeiten zum Übermitteln von E-Mail-Nachrichten, URLs und Anlagen an Microsoft finden Sie unter Melden von Nachrichten [und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Um direkt zur Übermittlungsseite **zu** wechseln, verwenden Sie <https://protection.office.com/reportsubmission> .

- Zum Übermitteln von Nachrichten und Dateien an Microsoft müssen Sie Mitglied einer der folgenden Rollengruppen sein:

  - **Organisationsverwaltung** oder **Security Reader** im Security & [Compliance Center](permissions-in-the-security-and-compliance-center.md).

  - **Organisationsverwaltung** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).

    Beachten Sie, dass die Mitgliedschaft in dieser Rollengruppe erforderlich ist, um Benutzerübermittlungen an [das](#view-user-submissions-to-the-custom-mailbox) benutzerdefinierte Postfach wie weiter unten in diesem Artikel beschrieben anzeigen.

- Weitere Informationen dazu, wie Benutzer Nachrichten und Dateien an Microsoft übermitteln können, finden Sie unter Melden von Nachrichten und Dateien [an Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="report-suspicious-content-to-microsoft"></a>Melden verdächtiger Inhalte an Microsoft

1. Wechseln Sie & Security & Compliance  Center zu Übermittlungen der \> **Bedrohungsverwaltung,** überprüfen Sie, ob Sie sich auf der Registerkarte **Administratorübermittlungen** befindet, und klicken Sie dann auf **Neue Übermittlung**.

2. Verwenden **Sie Neues Übermittlungsf** flyout, das die Nachricht, URL oder Anlage wie in den folgenden Abschnitten beschrieben zu übermitteln scheint.

### <a name="submit-a-questionable-email-to-microsoft"></a>Senden einer fragwürdigen E-Mail an Microsoft

1. Wählen Sie **im Abschnitt Objekttyp** die Option **E-Mail aus.** Verwenden Sie **im** Abschnitt Übermittlungsformat eine der folgenden Optionen:

   - **Netzwerknachrichten-ID:** Dies ist ein GUID-Wert, der im **X-MS-Exchange-Organization-Network-Message-Id-Header** in der Nachricht oder im **X-MS-Office365-Filtering-Correlation-Id-Header** in isolierten Nachrichten verfügbar ist.

   - **Datei**: Klicken Sie **auf Datei auswählen**. Suchen Und wählen Sie im geöffneten Dialogfeld die Datei EML oder MSG aus, und klicken Sie dann auf **Öffnen**.

   > [!NOTE]
   > Die Möglichkeit, Nachrichten ab einem Alter von 30 Tagen zu übermitteln, wurde für Defender für Office 365 ausgesetzt. Administratoren können nur 7 Tage zurück.

2. Geben Sie **im Abschnitt Empfänger** einen oder mehrere Empfänger an, für die Sie eine Richtlinienüberprüfung ausführen möchten. Die Richtlinienüberprüfung bestimmt, ob die E-Mail-Überprüfung aufgrund von Benutzer- oder Organisationsrichtlinien umgangen wurde.

3. Wählen Sie **im Abschnitt** Gründe für die Übermittlung eine der folgenden Optionen aus:

   - **Sollte nicht blockiert worden sein**

   - **Sollte blockiert sein:** Wählen **Sie Spam,** **Phishing** oder **Malware aus.** Wenn Sie nicht sicher sind, verwenden Sie Ihr bestes Urteil.

4. Wenn Sie fertig sind, klicken Sie auf **die** Schaltfläche Absenden.

   ![Neues URL-Übermittlungsbeispiel](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>Senden einer verdächtigen URL an Microsoft

1. Wählen Sie **im Abschnitt Objekttyp** die **Option URL aus.** Geben Sie in das angezeigte Feld die vollständige URL ein (z. B. `https://www.fabrikam.com/marketing.html` ).

2. Wählen Sie **im Abschnitt** Gründe für die Übermittlung eine der folgenden Optionen aus:

   - **Sollte nicht blockiert worden sein**

   - **Sollte blockiert sein:** Wählen Sie **Phishing oder** **Schadsoftware aus.**

3. Wenn Sie fertig sind, klicken Sie auf **die** Schaltfläche Absenden.

   ![Beispiel für neue E-Mail-Übermittlung](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a>Übermitteln einer verdächtigen Datei an Microsoft

1. Wählen Sie **im Abschnitt Objekttyp** die Option **Anlage aus.**

2. Klicken **Sie auf Datei auswählen.** Suchen Und wählen Sie im geöffneten Dialogfeld die Datei aus, und klicken Sie dann auf **Öffnen**.

3. Wählen Sie **im Abschnitt** Gründe für die Übermittlung eine der folgenden Optionen aus:

   - **Sollte nicht blockiert worden sein**

   - **Sollte blockiert worden sein:** **Schadsoftware** ist die einzige Wahl und wird automatisch ausgewählt.

4. Wenn Sie fertig sind, klicken Sie auf **die** Schaltfläche Absenden.

   ![Beispiel für die Übermittlung neuer Anlagen](../../media/submission-file-flyout.PNG)

## <a name="view-items-submitted-for-analysis"></a>Zur Analyse übermittelte Elemente anzeigen

Wechseln Sie & Security & Compliance  Center zu Übermittlungen zur \> **Bedrohungsverwaltung,** überprüfen Sie, ob Sie auf der Registerkarte Übermittelt für **die Analyse** sind.

Am oberen Rand der Seite können Sie ein Startdatum, ein Enddatum und  (standardmäßig) nach Übermittlungs-ID filtern (ein GUID-Wert, der jeder Übermittlung zugewiesen ist), indem Sie einen Wert in das Feld eingeben und auf Aktualisieren ![ ](../../media/scc-quarantine-refresh.png) klicken. Mehrere Werte können durch Kommata getrennt eingegeben werden.

Klicken Sie zum Ändern der Filterkriterien auf die Schaltfläche **Übermittlungs-ID,** und wählen Sie einen der folgenden Werte aus:

- **Sender**
- **Betreff/URL/Dateiname**
- **Übermittelt von**
- **Übermittlungstyp**
- **Status**

![Neue Filteroptionen für Administratorübermittlungen](../../media/admin-submission-email-filter-options.png)

Klicken Sie zum Exportieren der Ergebnisse **am** oberen Rand der Seite auf Exportieren, und wählen Sie **Diagrammdaten** oder **Tabelle aus.** Speichern Sie im angezeigten Dialogfeld die .csv Datei.

Unterhalb des Diagramms befinden sich drei Registerkarten: **E-Mail** (Standard), **URL** und **Anlage**.

### <a name="view-admin-email-submissions"></a>Anzeigen von Administrator-E-Mail-Übermittlungen

Klicken Sie auf **die Registerkarte E-Mail.**

Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:

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

#### <a name="admin-submission-rescan-details"></a>Details zum erneuten Scannen der Administratorübermittlung

Nachrichten, die in Administratorübermittlungen übermittelt werden, werden erneut überprüft, und die Ergebnisse werden im Detailf flyout angezeigt:

- Mögliche Fehler in der E-Mail-Authentifizierung des Absenders zum Zeitpunkt der Auslieferung.
- Informationen zu Richtlinientreffern, welche die Bewertung über einer Nachricht beeinflusst oder überschrieben haben könnten.
- Aktuelle Detonationsergebnisse, um festzustellen, ob die in der Nachricht enthaltenen URLs oder Dateien böswillig waren oder nicht.
- Feedback von Gradern.

Wenn eine Überschreibung gefunden wurde, sollte der erneute Scan in einigen Minuten abgeschlossen sein. Wenn kein Problem bei der E-Mail-Authentifizierung oder -Zustellung durch eine Außerkraftsetzung verursacht wurde, kann das Feedback von Gradern bis zu einem Tag dauern.

### <a name="view-admin-url-submissions"></a>Anzeigen von Administrator-URL-Übermittlungen

Klicken Sie auf **die Registerkarte URL.**

Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:

- **Date**
- **Übermittlungs-ID**
- **Übermittelt von**<sup>\*</sup>
- **URL**<sup>\*</sup>
- **Übermittlungstyp**
- **Status**<sup>\*</sup>

  <sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden detaillierte Informationen in einem Flyout angezeigt.

### <a name="view-admin-attachment-submissions"></a>Anzeigen von Administratoranhangsübermittlungen

Klicken Sie auf **die Registerkarte Anlagen.**

Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:

- **Date**
- **Übermittlungs-ID**
- **Übermittelt von**<sup>\*</sup>
- **Dateiname**<sup>\*</sup>
- **Übermittlungstyp**
- **Status**<sup>\*</sup>

  <sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden detaillierte Informationen in einem Flyout angezeigt.

## <a name="view-user-submissions-to-microsoft"></a>Anzeigen von Benutzerübermittlungen an Microsoft

Wenn Sie das Berichtsnachrichten-Add-In , das  Phishing-Add-In Melden oder Personen, die die integrierte Berichterstellung in Outlook im Web verwenden, bereitgestellt haben, können Sie auf der Registerkarte Benutzerübermittlungen [anzeigen, welche](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)Benutzer melden. [](enable-the-report-message-add-in.md) [](enable-the-report-phish-add-in.md)

1. Wechseln Sie im Security & Compliance Center zu Übermittlungen **der** \> **Bedrohungsverwaltung.**

2. Wählen Sie **die Registerkarte Benutzerübermittlungen** aus, und klicken Sie dann auf **Neue Übermittlung**.

Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:

- **Gesendet am**
- **Übermittelt von**<sup>\*</sup>
- **Betreff**<sup>\*</sup>
- **Sender**
- **Sender-IP**<sup>\*</sup>
- **Übermittlungstyp**

<sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden detaillierte Informationen in einem Flyout angezeigt.

Am oberen Rand der Seite können Sie ein Startdatum, ein Enddatum und (standardmäßig) nach **Sender** filtern, indem Sie einen Wert in das Feld eingeben und auf Aktualisieren ![ ](../../media/scc-quarantine-refresh.png) klicken. Mehrere Werte können durch Kommata getrennt eingegeben werden.

Klicken Sie zum Ändern der Filterkriterien auf die Schaltfläche **Absender,** und wählen Sie einen der folgenden Werte aus:

- **Absenderdomäne**
- **Betreff**
- **Übermittelt von**
- **Übermittlungstyp**
- **Sender-IP**

![Neue Filteroptionen für Benutzerübermittlungen](../../media/user-submissions-filter-options.png)

Klicken Sie zum Exportieren der Ergebnisse **am** oberen Rand der Seite auf Exportieren, und wählen Sie **Diagrammdaten** oder **Tabelle aus.** Speichern Sie im angezeigten Dialogfeld die .csv Datei.

## <a name="view-user-submissions-to-the-custom-mailbox"></a>Anzeigen von Benutzerübermittlungen an das benutzerdefinierte Postfach

**Wenn** Sie ein [benutzerdefiniertes](user-submission.md) Postfach für den Empfang von vom Benutzer gemeldeten Nachrichten konfiguriert haben, können Sie Nachrichten anzeigen und auch übermitteln, die an das Berichtspostfach übermittelt wurden.

1. Wechseln Sie im Security & Compliance Center zu Übermittlungen **der** \> **Bedrohungsverwaltung.**

2. Wählen Sie die **Registerkarte Benutzerdefiniertes Postfach** aus.

Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:

- **Gesendet am**
- **Übermittelt von**<sup>\*</sup>
- **Betreff**<sup>\*</sup>
- **Sender**
- **Sender-IP**<sup>\*</sup>
- **Übermittlungstyp**

Am oberen Rand der Seite können Sie ein Startdatum, ein Enddatum eingeben und nach **Übermittelt** filtern, indem Sie in das Feld einen Wert eingeben und auf Aktualisieren ![ ](../../media/scc-quarantine-refresh.png) klicken. Mehrere Werte können durch Kommata getrennt eingegeben werden.

Klicken Sie zum Exportieren der Ergebnisse **am** oberen Rand der Seite auf Exportieren, und wählen Sie **Diagrammdaten** oder **Tabelle aus.** Speichern Sie im angezeigten Dialogfeld die .csv Datei.

> [!NOTE]
> Wenn Organisationen nur für das Senden an benutzerdefinierte Postfächer konfiguriert sind, werden die gemeldeten Nachrichten nicht zum erneuten Scannen gesendet, und die Ergebnisse im Portal für vom Benutzer gemeldete Nachrichten sind immer leer.

## <a name="undo-user-submissions"></a>Rückgängig machen von Benutzerübermittlungen

Sobald ein Benutzer eine verdächtige E-Mail an das benutzerdefinierte Postfach übermittelt hat, haben der Benutzer und der Administrator keine Möglichkeit, die Übermittlung rückgängig zu machen. Wenn der Benutzer die E-Mail wiederherstellen möchte, steht sie für die Wiederherstellung in den Ordnern Gelöschte Elemente oder Junk-E-Mail zur Verfügung.

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>Senden von Nachrichten an Microsoft aus dem benutzerdefinierten Postfach

Wenn Sie das benutzerdefinierte Postfach so konfiguriert haben, dass von Benutzern gemeldete Nachrichten abgefangen werden, ohne die Nachrichten an Microsoft zu senden, können Sie bestimmte Nachrichten zur Analyse finden und an Microsoft senden. Dadurch wird eine Benutzerübermittlung effektiv in eine Administratorübermittlung verlagert.

Wählen Sie **auf** der Registerkarte Benutzer gemeldete Nachrichten  eine Nachricht in der Liste aus, klicken Sie auf die Schaltfläche Aktion, und treffen Sie eine der folgenden Auswahlen:

- **Bericht bereinigen**
- **Melden von Phishing**
- **Melden von Schadsoftware**
- **Melden von Spam**

![Neue Optionen auf der Schaltfläche Aktion](../../media/user-submission-custom-mailbox-action-button.png)
