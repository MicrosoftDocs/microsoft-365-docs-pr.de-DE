---
title: Suchen und Freigeben von Nachrichten in Quarantäne als Benutzer
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Benutzer können erfahren, wie sie in Exchange Online Protection (EOP) isolierte (unter Quarantäne gestellte) Nachrichten anzeigen und verwalten, die sie hätten empfangen sollen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c0f95561977c453d7040d84ba0c779c3d33e07f0
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029825"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-eop"></a>Suchen und Freigeben von isolierten Nachrichten als Benutzer in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder in eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer, enthält die Quarantäne potenziell gefährliche oder unerwünschte Nachrichten. Weitere Informationen finden Sie unter [Quarantäne in EOP](quarantine-email-messages.md).

Als Empfänger einer unter Quarantäne gestellten Nachricht wird in der folgenden Tabelle beschrieben, was Sie als Benutzer ohne Administratorrechte mit der Nachricht tun können:

<br>

****

|Quarantänegrund|Anzeigen|Freigabe|Löschen|
|---|:---:|:---:|:---:|
|Masse|![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)|
|Spam|![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)|![Häkchen](../../media/checkmark.png)|
|Phishing (keine hohe Phishingwahrscheinlichkeit)|![Häkchen](../../media/checkmark.png)||![Häkchen](../../media/checkmark.png)|
|

Sie sehen und verwalten Ihre unter Quarantäne gestellten Nachrichten im Microsoft 365 Defender-Portal oder (wenn ein Administrator dies eingerichtet hat) in den [Spam-Benachrichtigungen für Endbenutzer](use-spam-notifications-to-release-and-report-quarantined-messages.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wissenswertes, bevor Sie anfangen

- Um das Microsoft 365 Defender-Portal zu öffnen, gehen Sie zu <https://security.microsoft.com>. Um die Quarantäne-Seite direkt zu öffnen, wechseln Sie zu <https://security.microsoft.com/quarantine>.

- Administratoren können konfigurieren, wie lange Nachrichten isoliert werden, bevor sie endgültig in Anti-Spam-Richtlinien gelöscht werden. Nachrichten, die aus der Quarantäne abgelaufen sind, können nicht wiederhergestellt werden. Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).

- Administratoren können auch [Spam-Benachrichtigungen für Endbenutzer](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in Anti-Spam-Richtlinien aktivieren. Benutzende können in Quarantäne befindliche Spamnachrichten direkt über diese Benachrichtigungen freigeben. Benutzende können die in Quarantäne befindlichen Phishing-Nachrichten (keine Phishing-Nachrichten mit hohem Sicherheitsrisiko) direkt aus diesen Benachrichtigungen überprüfen. Weitere Informationen finden Sie unter [Spam-Benachrichtigungen für Endbenutzer in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).

- Nachrichten, die wegen Phishing mit hohem Sicherheitsrisiko, Malware oder durch Mail-Flow-Regeln (auch als Transportregeln bekannt) unter Quarantäne gestellt wurden, sind nur für Admins verfügbar und für Benutzende nicht sichtbar. Weitere Informationen finden Sie unter [Verwalten von isolierten Nachrichten und Dateien als Administrator in EOP](manage-quarantined-messages-and-files.md).

- Sie können eine Nachricht nur einmal freigeben und als falsch positiv markiert (keine Junk-E-Mail) melden.

## <a name="view-your-quarantined-messages"></a>Anzeigen Ihrer isolierten Nachrichten

1. Gehen Sie im Microsoft 365 Defender-Portal zu **E-Mail & Zusammenarbeit** \> **Überprüfung** \> **Quarantäne**.

2. Sie können die Ergebnisse sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken. Klicken Sie auf **Spalten ändern**, um höchstens sieben Spalten anzuzeigen. Die Standardwerte sind mit einem Sternchen (<sup>\*</sup>) gekennzeichnet:

   - **Empfangen**<sup>\*</sup>
   - **Absender**<sup>\*</sup>
   - **Betreff**<sup>\*</sup>
   - **Quarantänegrund**<sup>\*</sup>
   - **Veröffentlicht?**<sup>\*</sup>
   - **Richtlinientyp**<sup>\*</sup>
   - **Läuft ab**<sup>\*</sup>
   - **Empfänger**
   - **Nachrichten-ID**
   - **Name der Richtlinie**
   - **Größe**
   - **Richtung**

   Klicken Sie nach Abschluss des Vorgangs auf **Speichern**, oder klicken Sie auf **Als Standard festlegen**.

3. Klicken Sie auf **Filter**, um die Ergebnisse zu filtern. Die verfügbaren Filter sind:

   - **Ablaufzeit**: Filtern von Nachrichten nach ihrem Ablauf aus der Quarantäne:
     - **Heute**
     - **Nächste 2 Tage**
     - **Nächste 7 Tage**
     - **Benutzerdefiniert**: Geben Sie ein **Anfangsdatum** und **Enddatum** ein.

   - **Empfangszeit**: Geben Sie ein **Anfangsdatum** und **Enddatum** ein.

   - **Quarantänegrund**:
     - **Massensendung**
     - **Spam**
     - **Phishing**

   - **Richtlinientyp**: Filtern von Nachrichten nach Richtlinientyp:
     - **Anti-Schadsoftware-Richtlinie**
     - **Richtlinie für sichere Anlagen** (Defender für Office 365)
     - **Antiphishing-Richtlinie**
     - **Richtlinie für gehostete Inhaltsfilter** (Antispamrichtlinie)
     - **Transportregel**

     <sup>\*</sup>

   Klicken Sie auf **Löschen**, um den Filter zu löschen. Um das Filter-Flyout auszublenden, klicken Sie erneut auf **Filter**.

4. Verwenden Sie **Ergebnisse sortieren nach** (standardmäßig die Schaltfläche **Nachrichten-ID**) und einen entsprechenden Wert, um bestimmte Nachrichten zu finden. Platzhalter werden nicht unterstützt. Sie können nach den folgenden Werten suchen:

   - **Nachrichten-ID**: Die globale eindeutige ID der Nachricht. Wenn Sie eine Nachricht in der Liste auswählen, wird der Wert **Nachrichten-ID** im Flyout-Fenster **Details** angezeigt, der angezeigt wird. Administratoren können [Nachrichtenverfolgung](message-trace-scc.md) verwenden, um Nachrichten und die entsprechenden Nachrichten-ID-Werte zu suchen.
   - **E-Mail-Adresse des Absenders**: Die E-Mail-Adresse eines einzelnen Absenders.
   - **Richtlinienname**: Verwenden Sie den vollständigen Namen der Nachricht. Bei der Suche wird nicht zwischen Groß- und Kleinschreibung unterschieden.
   - **E-Mail-Adresse des Empfängers**: Die E-Mail-Adresse eines einzelnen Empfängers.
   - **Betreff**: Verwenden Sie den gesamten Betreff der Nachricht. Bei der Suche wird nicht zwischen Groß- und Kleinschreibung unterschieden.

   Nachdem Sie die Suchkriterien eingegeben haben, klicken Sie auf die ![Schaltfläche Aktualisieren](../../media/scc-quarantine-refresh.png) **Aktualisieren**, um die Ergebnisse zu filtern.

Nachdem Sie eine bestimmte isolierte Nachricht gefunden haben, wählen Sie die Nachricht aus, um Details dazu anzuzeigen und Maßnahmen zu ergreifen (z. B. die Nachricht anzeigen, freigeben, herunterladen oder löschen).

### <a name="export-message-results"></a>Nachrichtenergebnisse exportieren

1. Wählen Sie die gewünschten Nachrichten aus, und klicken Sie auf **Ergebnisse exportieren**.

2. Klicken Sie auf **Ja** in der Bestätigungsnachricht, die Sie warnt, das Browserfenster geöffnet zu lassen.

3. Wenn Ihr Export fertig ist, können Sie den Speicherort für die .csv-Datei benennen und auswählen.

### <a name="view-quarantined-message-details"></a>Anzeigen von Details der isolierten Nachricht

Wenn Sie eine E-Mail-Nachricht in der Liste auswählen, werden die folgenden Nachrichtendetails im Flyout-Fenster **Details** angezeigt:

- **Nachrichten-ID**: Die globale eindeutige ID für die Nachricht.
- **Absenderadresse**
- **Empfangen**: Das Datum/die Uhrzeit des Nachrichtenempfangs.
- **Betreff**
- **Quarantänegrund**: Zeigt an, ob eine Nachricht als **Spam**, **Massensendung** oder **Phishing** erkannt wurde.
- **Empfänger**: Wenn die Nachricht mehrere Empfänger enthält, müssen Sie auf **Vorschau der Nachricht anzeigen** oder **Nachrichten** Kopfzeile anzeigen klicken, um die gesamte Liste der Empfänger anzuzeigen.
- **Läuft ab**. Das Datum/die Uhrzeit, zu der die Nachricht automatisch und dauerhaft aus der Quarantäne gelöscht wird.
- **Freigegeben für**: Alle E-Mail-Adressen (sofern vorhanden), für die die Nachricht freigegeben wurde.
- **Noch nicht freigegeben für**: Alle E-Mail-Adressen (sofern vorhanden), für die die Nachricht noch nicht freigegeben wurde.

### <a name="take-action-on-quarantined-email"></a>Maßnahmen für isolierte E-Mails ergreifen

Nachdem Sie eine Nachricht ausgewählt haben, haben Sie Optionen, was mit den Nachrichten im Flyout-Fenster **Details** geschehen soll:

- **Nachricht freigeben**: Wählen Sie im angezeigten Flyout-Fenster, ob Sie **Meldungen zur Analyse an Microsoft melden** möchten. Diese ist standardmäßig ausgewählt und meldet die irrtümlich isolierte Nachricht an Microsoft als falsches positives Ergebnis.

  Klicken Sie nach Abschluss des Vorgangs auf **Nachrichten freigeben**.

- **Nachrichtenkopf anzeigen**: Wählen Sie diesen Link aus, um den Nachrichtenkopftext anzuzeigen. Um den Nachrichtenkopf im Detail zu analysieren, kopieren Sie den Nachrichtenkopftext in die Zwischenablage, und wählen Sie dann **Microsoft-Nachrichtenkopfanalyse** aus, um zur Remoteverbindungsuntersuchung zu wechseln (klicken Sie mit der rechten Maustaste, und wählen Sie **In neuer Registerkarte öffnen** aus, wenn Sie Microsoft 365 nicht verlassen möchten, um die Aufgabe auszuführen). Fügen Sie den Nachrichtenkopf auf der Seite in den Abschnitt "Nachrichtenkopfanalyse" ein, und wählen Sie dann **Kopfzeilen analysieren** aus:

- **Vorschau der Nachricht anzeigen**: Wählen Sie im angezeigten Flyout-Fenster eine der folgenden Optionen:
  - **Quellansicht**: Zeigt die HTML-Version des Nachrichtentextes an, wobei alle Links deaktiviert sind.
  - **Textansicht**: Zeigt den Nachrichtentext im Klartext an.

- **Aus Quarantäne entfernen**: Nachdem Sie in der angezeigten Warnung auf **Ja** geklickt haben, wird die Nachricht sofort gelöscht.

- **Absender blockieren**: Fügen Sie den Absender zur Liste blockierter Absender für Ihr Postfach hinzu. Weitere Informationen finden Sie unter [E-Mail-Absender blockieren](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).

Fügen Sie den Absender zur Liste blockierter Absender für Ihr Postfach hinzu. Weitere Informationen finden Sie unter [E-Mail-Absender blockieren](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).

Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.

Wenn Sie die Nachricht nicht freigeben oder entfernen, wird sie nach Ablauf der Standard-Quarantäneaufbewahrungszeit gelöscht.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>Maßnahmen für mehrere isolierte E-Mail-Nachrichten ergreifen

Wenn Sie mehrere isolierte Nachrichten in der Liste auswählen (bis zu 100), erscheint das Flyout-Fenster **Massenaktionen**, in dem Sie die folgenden Aktionen durchführen können:

- **Nachrichten freigeben**: Die Optionen sind die gleichen wie bei der Freigabe einer einzelnen Nachricht, außer dass Sie nicht **Nachrichten an bestimmte Empfänger freigeben** auswählen können; Sie können nur **Nachricht an alle Empfänger freigeben** oder **Nachrichten an andere Personen freigeben** auswählen.
- **Nachrichten löschen**: Nachdem Sie in der angezeigten Warnung auf **Ja** klicken, wird die Nachricht sofort gelöscht, ohne an die ursprünglichen Empfänger gesendet zu werden.

Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.
