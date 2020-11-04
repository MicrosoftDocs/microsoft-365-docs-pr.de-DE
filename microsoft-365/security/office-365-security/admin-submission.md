---
title: Übermittlungen von Administratoren
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
description: Administratoren können erfahren, wie Sie das Übermittlungen-Portal im Security & Compliance Center verwenden, um verdächtige e-Mails, verdächtige Phishing-Mails, Spam und andere potenziell schädliche Nachrichten, URLs und Dateien für die Überprüfung an Microsoft zu übermitteln.
ms.openlocfilehash: be2fc8e41e3b53923b0297f30dfb102bbabd7489
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877267"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>Verwenden von Administrator-Übermittlung, um verdächtige Spam- oder Phishing-Nachrichten, URLs und Dateien an Microsoft zu übermitteln

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-Organisationen mit Postfächern in Exchange Online können Administratoren das Übermittlungen-Portal im Security & Compliance Center verwenden, um e-Mail-Nachrichten, URLs und Anlagen für die Überprüfung an Microsoft zu übermitteln.

Wenn Sie eine e-Mail übermitteln, erhalten Sie Informationen zu allen Richtlinien, die möglicherweise die eingehenden e-Mails in ihren Mandanten zugelassen haben, sowie über die Untersuchung von URLs und Anlagen in der e-Mail. Richtlinien, die möglicherweise eine e-Mail erlaubt haben, enthalten die Liste sicherer Absender eines einzelnen Benutzers sowie Richtlinien auf Mandantenebene wie Exchange-Nachrichtenfluss Regeln (auch bekannt als Transportregeln).

Weitere Möglichkeiten zum Übermitteln von e-Mail-Nachrichten, URLs und Anlagen an Microsoft finden Sie unter [Report Messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Wenn Sie direkt zur **Übermittlungs** Seite wechseln möchten, verwenden Sie <https://protection.office.com/reportsubmission> .

- Um Nachrichten und Dateien an Microsoft zu übermitteln, müssen Sie Mitglied einer der folgenden Rollengruppen sein:

  - **Organisationsverwaltung** oder **Sicherheitsadministrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

  - **Organisationsverwaltung** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

    Beachten Sie, dass die Mitgliedschaft in dieser Rollengruppe erforderlich ist, um [Benutzer Übermittlungen an das benutzerdefinierte Postfach anzuzeigen](#view-user-submissions-to-the-custom-mailbox) , wie weiter unten in diesem Thema beschrieben.

- Weitere Informationen darüber, wie Benutzer Nachrichten und Dateien an Microsoft übermitteln können, finden Sie unter [Report Messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="report-suspicious-content-to-microsoft"></a>Verdächtigen Inhalt an Microsoft melden

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> -über **mittlungen** , stellen Sie sicher, dass Sie sich auf der Registerkarte Admin-über **mittlungen** befinden, und klicken Sie dann auf **neue Übermittlung**.

2. Verwenden Sie das **neue Übermittlungs** Flyout, das angezeigt wird, um die Nachricht, die URL oder Anlage zu übermitteln, wie in den folgenden Abschnitten beschrieben.

### <a name="submit-a-questionable-email-to-microsoft"></a>Senden einer fragwürdigen e-Mail an Microsoft

1. Wählen Sie im Abschnitt **Objekttyp** die Option **e-Mail** aus. Verwenden Sie im Abschnitt **Übermittlungs Format** eine der folgenden Optionen:

   - **Netzwerknachrichten-ID** : Dies ist ein GUID-Wert, der im **X-MS-Exchange-Organization-Network-Message-ID** -Header in der Nachricht zur Verfügung steht.

   - **Datei** : Klicken Sie auf **Datei auswählen**. Suchen Sie in dem Dialogfeld, das geöffnet wird, nach der EML-oder msg-Datei, und wählen Sie Sie aus, und klicken Sie dann auf **Öffnen**.

2. Geben Sie im Abschnitt **Empfänger** einen oder mehrere Empfänger an, für die Sie eine Richtlinienüberprüfung ausführen möchten. Durch die Richtlinienüberprüfung wird ermittelt, ob die e-Mail-Überprüfung aufgrund von Benutzer-oder Organisationsrichtlinien umgangen wurde.

3. Wählen Sie im Abschnitt **Grund für die Übermittlung** eine der folgenden Optionen aus:

   - **Sollte nicht blockiert worden sein**

   - **Sollte blockiert worden sein** : Wählen Sie **Spam** , **Phishing** oder **Schadsoftware** aus. Wenn Sie nicht sicher sind, verwenden Sie Ihr Bestes Urteil.

4. Wenn der Filter aufgrund von Richtlinien bei der Übermittlung umgangen wurde, werden Informationen zu dieser Richtlinie angezeigt.

   Wenn der Filter aufgrund einer oder mehrerer Richtlinien nicht umgangen wurde, wird die Überprüfung in einigen Minuten abgeschlossen. Sie erhalten zusätzliche Informationen über die Übermittlung, indem Sie auf den Link Status klicken. Dies beinhaltet die Ergebnisse der Richtlinienüberprüfung und das Ergebnis der erneuten Überprüfung. Hinweis Dadurch wird die e-Mail-Nachricht nicht über den Microsoft Defender für Office 365 vollständigen Filter Stapel ausgeführt, es wird jedoch ein partieller erneuter Scan auf der Grundlage bestimmter Attribute der e-Mail, der URL oder der Datei ausgeführt.

5. Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **Absenden** .

![URL-Übermittlungs Beispiel](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>Senden einer verdächtigen URL an Microsoft

1. Wählen Sie im Abschnitt **Objekttyp** die Option **URL** aus. Geben Sie in das Feld, das angezeigt wird, die vollständige URL ein (beispielsweise `https://www.fabrikam.com/marketing.html` ).

2. Wählen Sie im Abschnitt **Grund für die Übermittlung** eine der folgenden Optionen aus:

   - **Sollte nicht blockiert worden sein**

   - **Sollte blockiert worden sein** : Wählen Sie **Phishing** oder **Schadsoftware** aus.

3. Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **Absenden** .

![Beispiel für eine e-Mail-Übermittlung](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a>Übermitteln einer vermuteten Datei an Microsoft

1. Wählen Sie im Abschnitt **Objekttyp** die Option **Anlage** aus.

2. Klicken Sie auf **Datei auswählen**. Suchen und wählen Sie im daraufhin geöffneten Dialogfeld die Datei aus, und klicken Sie dann auf **Öffnen**.

3. Wählen Sie im Abschnitt **Grund für die Übermittlung** eine der folgenden Optionen aus:

   - **Sollte nicht blockiert worden sein**

   - **Sollte blockiert worden sein** : **Schadsoftware** ist die einzige Wahl und wird automatisch ausgewählt..

4. Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **Absenden** .

![Beispiel für Anlagen Übermittlung](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a>Anzeigen von Übermittlungen von Administratoren

Wechseln Sie im Security & Compliance Center zu **Threat Management** \> -über **mittlungen** , stellen Sie sicher, dass Sie sich auf der Registerkarte Admin-über **mittlungen** befinden, und klicken Sie dann auf **neue Übermittlung**.

Oben auf der Seite können Sie ein Startdatum, ein Enddatum und (standardmäßig) nach **Übermittlungs-ID** (ein GUID-Wert, der jeder Übermittlung zugewiesen ist) filtern, indem Sie einen Wert in das Feld eingeben und auf Aktualisieren klicken ![ ](../../media/scc-quarantine-refresh.png) . Update

Klicken Sie zum Ändern der Filterkriterien auf die Schaltfläche **Übermittlungs-ID** , und wählen Sie einen der folgenden Werte aus:

- **Sender**
- **Betreff/URL/Dateiname**
- **Eingereicht von**
- **Übermittlungs**
- **Status**

![Filter Optionen für Übermittlungen von Administratoren](../../media/admin-submission-email-filter-options.png)

Klicken Sie zum Exportieren der Ergebnisse im oberen Bereich der Seite auf **exportieren** , und wählen Sie **Diagrammdaten** oder **Tabelle** aus. Speichern Sie im angezeigten Dialogfeld die CSV-Datei.

Unter dem Diagramm befinden sich drei Registerkarten: **e-Mail** (Standard), **URL** und **Anlage**.

### <a name="view-admin-email-submissions"></a>Anzeigen von Administrator-e-Mail-Übermittlungen

Klicken Sie auf die Registerkarte **e-Mail** .

Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:

- **Date**
- **Übermittlungs-ID** : ein GUID-Wert, der jeder Übermittlung zugewiesen ist.
- **Eingereicht von**<sup>\*</sup>
- **Betreff**<sup>\*</sup>
- **Sender**
- **Sender-IP**<sup>\*</sup>
- **Übermittlungs**
- **Zustellungs Grund**
- **Status**<sup>\*</sup>
- **Steuerelementtyp**
- **Steuerelementquelle**

  <sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden ausführliche Informationen in einem Flyout angezeigt.

### <a name="view-admin-url-submissions"></a>Anzeigen von Administratoren-URL-Übermittlungen

Klicken Sie auf die Registerkarte **URL** .

Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:

- **Date**
- **Übermittlungs-ID**
- **Eingereicht von**<sup>\*</sup>
- **URL**<sup>\*</sup>
- **Übermittlungs**
- **Status**<sup>\*</sup>

  <sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden ausführliche Informationen in einem Flyout angezeigt.

### <a name="view-admin-attachment-submissions"></a>Anzeigen der Übermittlungen von Administrator Anlagen

Klicken Sie auf die Registerkarte **Anlagen** .

Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:

- **Date**
- **Übermittlungs-ID**
- **Eingereicht von**<sup>\*</sup>
- **Dateiname**<sup>\*</sup>
- **Übermittlungs**
- **Status**<sup>\*</sup>

  <sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden ausführliche Informationen in einem Flyout angezeigt.

## <a name="view-user-submissions-to-microsoft"></a>Anzeigen von Benutzern Übermittlungen an Microsoft

Wenn Sie das [Add-in "Berichtsnachricht](enable-the-report-message-add-in.md)" bereitgestellt haben oder die [integrierten Berichte in Outlook im Internet](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)verwendet werden, können Sie sehen, welche Benutzer auf der Registerkarte " **Benutzereingaben** " berichten.

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** -über \> **mittlungen**.

2. Wählen Sie die Registerkarte **Benutzer Übermittlungen** aus, und klicken Sie dann auf **neue Übermittlung**.

Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:

- **Übermittelt am**
- **Eingereicht von**<sup>\*</sup>
- **Betreff**<sup>\*</sup>
- **Sender**
- **Sender-IP**<sup>\*</sup>
- **Übermittlungs**

<sup>\*</sup> Wenn Sie auf diesen Wert klicken, werden ausführliche Informationen in einem Flyout angezeigt.

Am oberen Rand der Seite können Sie ein Startdatum, ein Enddatum und (standardmäßig) nach **Absender** filtern, indem Sie einen Wert in das Feld eingeben und auf ![ Aktualisieren klicken ](../../media/scc-quarantine-refresh.png) . Update

Klicken Sie zum Ändern der Filterkriterien auf die Schaltfläche **Absender** , und wählen Sie einen der folgenden Werte aus:

- **Absenderdomäne**
- **Betreff**
- **Eingereicht von**
- **Übermittlungs**
- **Sender-IP**

![Filter Optionen für Benutzer Übermittlungen](../../media/user-submissions-filter-options.png)

Klicken Sie zum Exportieren der Ergebnisse im oberen Bereich der Seite auf **exportieren** , und wählen Sie **Diagrammdaten** oder **Tabelle** aus. Speichern Sie im angezeigten Dialogfeld die CSV-Datei.

## <a name="view-user-submissions-to-the-custom-mailbox"></a>Anzeigen von Benutzereingaben zum benutzerdefinierten Postfach

**Wenn** Sie [ein benutzerdefiniertes Postfach](user-submission.md) für den Empfang von gemeldeten Benutzern konfiguriert haben, können Sie Nachrichten anzeigen und auch senden, die an das Berichts Postfach übermittelt wurden.

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** -über \> **mittlungen**.

2. Wählen Sie die Registerkarte **benutzerdefiniertes Postfach** aus.

Sie können auf die Schaltfläche **Spaltenoptionen** am unteren Rand der Seite klicken, um Spalten aus der Ansicht hinzuzufügen oder zu entfernen:

- **Übermittelt am**
- **Eingereicht von**<sup>\*</sup>
- **Betreff**<sup>\*</sup>
- **Sender**
- **Sender-IP**<sup>\*</sup>
- **Übermittlungs**

Am oberen Rand der Seite können Sie ein Startdatum, ein Enddatum eingeben und nach **abgesendet** filtern, indem Sie einen Wert in das Feld eingeben und auf ![ Aktualisieren klicken ](../../media/scc-quarantine-refresh.png) . Update

Klicken Sie zum Exportieren der Ergebnisse im oberen Bereich der Seite auf **exportieren** , und wählen Sie **Diagrammdaten** oder **Tabelle** aus. Speichern Sie im angezeigten Dialogfeld die CSV-Datei.

## <a name="undo-user-submissions"></a>Benutzereingaben rückgängig machen

Sobald ein Benutzer eine verdächtige e-Mail an das benutzerdefinierte Postfach übermittelt hat, haben der Benutzer und der Administrator keine Option zum Rückgängigmachen der Übermittlung. Wenn der Benutzer die e-Mail wiederherstellen möchte, steht er für die Wiederherstellung in den Ordner "Gelöschte Elemente" oder "Junk-e-Mail" zur Verfügung. 

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>Übermitteln von Nachrichten an Microsoft aus dem benutzerdefinierten Postfach

Wenn Sie das benutzerdefinierte Postfach so konfiguriert haben, dass vom Benutzer gemeldete Nachrichten abgefangen werden, ohne dass die Nachrichten an Microsoft gesendet werden, können Sie bestimmte Nachrichten zur Analyse an Microsoft senden. Dadurch wird eine Benutzer Übermittlung effektiv in eine Administrator Übermittlung verschoben.

Wählen Sie auf der Registerkarte **benutzerdefiniertes Postfach** eine Nachricht in der Liste aus, klicken Sie auf die Schaltfläche **Aktion** , und führen Sie eine der folgenden Optionen aus:

- **Bericht säubern**
- **Phishing melden**
- **Melden von Schadsoftware**
- **Spam melden**

![Optionen für die Schaltfläche "Aktion"](../../media/user-submission-custom-mailbox-action-button.png)
