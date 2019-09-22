---
title: Suchen und Freigeben von isolierten Nachrichten als Benutzer in Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 05/19/2018
audience: Consumer/IW
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
description: 'Als Office 365-Benutzer können Sie Ihre eigenen in Spamquarantäne befindlichen Nachrichten auf eine von zwei Arten verwalten: Sie können entweder auf direkt an Sie gesendete Spambenachrichtigungen reagieren (sofern Ihr Administrator dieses Feature eingerichtet hat) oder im Security &amp; Compliance Center das Spamquarantänefeature verwenden.'
ms.openlocfilehash: 341e56049926851c4a84989c5a437e5d994aff5f
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081287"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-office-365"></a>Suchen und Freigeben von isolierten Nachrichten als Benutzer in Office 365

Als Office 365-Benutzer können Sie Nachrichten, die unter Quarantäne gestellt anstatt ihnen zugesendet wurden, mit einer von zwei Methoden verwalten: Sie können entweder [auf direkt an Sie gesendete Spambenachrichtigungen reagieren](use-spam-notifications-to-release-and-report-quarantined-messages.md) (sofern Ihr Administrator dieses Feature eingerichtet hat), oder das Security &amp; Compliance Center verwenden. 
  
> [!NOTE]
> Wenn Sie ein Administrator sind, können Sie [in Quarantäne befindliche Nachrichten für andere Personen in Ihrer Organisation verwalten](manage-quarantined-messages-and-files.md). 
  
## <a name="view-messages-that-were-sent-to-quarantine-instead-of-to-you"></a>Anzeigen von Nachrichten, die unter Quarantäne gestellt anstatt ihnen zugesendet wurden

1. Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto bei Office 365 an, und [wechseln Sie zum Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md). 
    
2. Erweitern Sie auf der linken Seite **Bedrohungsverwaltung**, wählen Sie **Überprüfen** und dann **Quarantäne** aus.
    
    > [!TIP]
    > Um direkt zur **Quarantäne**-Seite im Security &amp; Compliance Center zu wechseln, verwenden Sie diese URL:> [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)
  
Standardmäßig werden im Security &amp; Compliance Center alle E-Mail-Nachrichten, die isoliert wurden, als Spam angezeigt. Die Nachrichten werden von der neuesten zur ältesten sortiert, basierend auf dem **Datum**, an dem die Nachricht empfangen wurde. Für jede Nachricht werden außerdem der **Absender**, das **Betreff** und das Ablaufdatum (unter **Läuft ab**) angezeigt. Sie können schnell nach einem Feld sortieren, indem Sie auf die entsprechende Spaltenüberschrift klicken; klicken Sie erneut auf eine Spaltenüberschrift, um die Sortierreihenfolge umzukehren. 
  
Sie können eine Liste aller in Quarantäne befindlichen Nachrichten anzeigen, oder Sie können per Filter nach bestimmten Nachrichten suchen. Massenvorgänge können nur für bis zu 100 Elemente durchgeführt werden, d. h. mit Filtern können Sie das Resultset reduzieren, wenn mehr als 500 Elemente vorhanden sind. Sie können Nachrichten schnell nach einem einzelnen Quarantänegrund filtern, indem Sie eine Option in der Dropdownliste auswählen. Die folgenden Optionen stehen zur Verfügung:
  
- E-Mail, die als Spam erkannt wurde. Diese in Quarantäne befindlichen Nachrichten werden standardmäßig angezeigt.
    
- E-Mail, die als Massensendungen erkannt wurde.
    
Nachdem Sie eine bestimmte, in Quarantäne befindliche Nachricht gefunden haben, klicken Sie darauf, um Details hierzu anzuzeigen und Aktionen durchzuführen. Sie können die Nachricht in Ihr Postfach freigeben, die Nachricht in der Vorschau anzeigen, die Nachricht herunterladen oder die Nachricht sofort aus der Quarantäne löschen.
  
> [!NOTE]
> Sie müssen Administratorberechtigungen in Office 365 haben, um mit in Quarantäne befindlichen Nachrichten zu arbeiten, die an andere Benutzer gesendet wurden. 
  
## <a name="to-filter-and-find-quarantined-messages"></a>So filtern und suchen Sie in Quarantäne befindliche Nachrichten

Wenn Sie über viele in Quarantäne befindliche Elemente verfügen, können Sie die Anzahl auf einen verwaltbaren Satz reduzieren, indem Sie sie filtern.
  
1. Wählen Sie auf der Seite **Quarantäne** aus, ob Sie in Quarantäne befindliche **Spamnachrichten**- oder **Massensendungen** anzeigen möchten. 
    
2. Wählen Sie unter **Ergebnisse sortieren nach** eine beliebige Kombination aus Bedingungen aus, indem Sie den oder die entsprechenden Filter festlegen (Sie können zurzeit keine Platzhalter verwenden). Es gibt verschiedene Kriterien, unter denen Sie wählen können, wie die folgenden:
    
  - **Nachrichten-ID** Verwenden Sie dieses Kriterium zur Auswahl einer bestimmten Nachricht, wenn Sie die Nachrichten-ID kennen. 
    
    Wenn eine bestimmte Nachricht von einem Benutzer in Ihrer Organisation gesendet wurde oder an diesen gerichtet war, den Zielort aber nie erreicht hat, können Sie mithilfe der Nachrichtenablaufverfolgung nach der Nachricht suchen. (Lesen Sie [Ausführen einer Nachrichtenablaufverfolgung und Anzeigen der Ergebnisse](https://go.microsoft.com/fwlink/?LinkId=799737).) Wenn Sie feststellen, dass die Nachricht an die Quarantäne gesendet wurde, möglicherweise aufgrund der Übereinstimmung mit einer Nachrichtenflussregel oder ihrer Identifizierung als Spam, können Sie diese Nachricht anhand ihrer Nachrichten-ID einfach in der Quarantäne finden. Stellen Sie sicher, dass die vollständige Zeichenfolge der Nachrichten-ID enthalten ist. Hierzu können auch spitze Klammern (\<\>) gehören. Beispiel:
    
    \<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com\>
    
  - **E-Mail-Adresse des Absenders** Wählen Sie diese Option aus, wenn Sie nach einer einzelnen Absender-E-Mail-Adresse filtern möchten. 
    
  - **E-Mail-Adresse des Empfängers** Wählen Sie diese Option aus, wenn Sie nach einer einzelnen Empfänger-E-Mail-Adresse filtern möchten. 
    
  - **Betreff** Geben Sie den Betreff für eine E-Mail ein, die Sie finden möchten. 
    
  - **Datumsbereich** Sie können Sie nach dem Datum filtern, an dem die Nachricht in die Quarantäne verschoben wurde. Sie können das Datum oder einen Datumsbereich einschließlich der Uhrzeit angeben. 
    
  - **Ablaufdatum** Um nach dem Ablaufdatum zu filtern, wählen Sie **Erweiterter Filter** aus. Sie können Nachrichten auswählen, die innerhalb der nächsten 24 Stunden (**Heute**), innerhalb der nächsten 48 Stunden (**Nächsten 2 Tage**) oder innerhalb der nächsten Woche (**Nächsten 7 Tage**) aus der Quarantäne gelöscht werden, oder Sie können ein benutzerdefiniertes Zeitintervall auswählen.
    
    > [!IMPORTANT]
    > Standardmäßig werden Spam- und Massenmails für 30 Tage in Quarantäne gehalten. Dieser Zeitraum kann jedoch konfiguriert werden, und Ihr Administrator hat möglicherweise einen anderen Aufbewahrungszeitraum für die Quarantäne festgelegt. Wenn Office 365 eine Nachricht aus der Quarantäne löscht, kann die Nachricht nicht wiederhergestellt werden. 
  
## <a name="view-details-for-a-specific-message"></a>Anzeigen von Details zu einer bestimmten Nachricht

Nachdem Sie eine Nachricht ausgewählt haben, wird in einem Bereich rechts auf der Seite eine Zusammenfassung der Nachrichteneigenschaften angezeigt.
  
- **Nachrichten-ID**: Der eindeutige Bezeichner der Nachricht. 
    
- **Absenderadresse**: Die Person, die die Nachricht gesendet hat. 
    
- **Empfangen**: Das Datum, an dem die Nachricht empfangen wurde. 
    
- **Betreff**: Der Text der Betreffzeile der Nachricht. 
    
- **Quarantänegrund**: Zeigt an, ob eine Nachricht als **Spam** oder **Massensendung** erkannt wurde.
    
- **Läuft ab**: Das Datum, zu dem die Nachricht aus der Quarantäne gelöscht wird. 
    
- **Freigegeben für**: Alle E-Mail-Adressen (sofern vorhanden), für die die Nachricht freigegeben wurde. 
    
- **Noch nicht freigegeben für**: Alle E-Mail-Adressen (sofern vorhanden), für die die Nachricht nicht freigegeben wurde. Sie können **Freigeben für** auswählen, wenn Sie die Nachricht an Ihr Postfach freigeben möchten (näheres zum Freigeben von Nachrichten im nächsten Abschnitt). 
    
Sie können noch mehr Details zu der Nachricht anzeigen, indem Sie eine der folgenden Optionen auswählen:
  
- **Nachrichtenkopf anzeigen**: Wählen Sie diese Option aus, um den Nachrichtenkopftext anzuzeigen. Um den Nachrichtenkopf im Detail zu analysieren, kopieren Sie den Nachrichtenkopftext in die Zwischenablage, und wählen Sie dann **Microsoft-Nachrichtenkopfanalyse** aus, um zur Remoteverbindungsuntersuchung zu wechseln (klicken Sie mit der rechten Maustaste, und wählen Sie "In neuer Registerkarte öffnen" aus, wenn Sie Office 365 nicht verlassen möchten, um die Aufgabe auszuführen). Fügen Sie den Nachrichtenkopf auf der Seite in den Abschnitt "Nachrichtenkopfanalyse" ein, und wählen Sie dann "Kopfzeilen analysieren" aus. 
    
- **Nachrichtenvorschau** Hier können Sie die Roh- oder HTML-Version des Nachrichtentexts anzeigen. In der HTML-Ansicht sind Links deaktiviert. 
    
## <a name="manage-your-quarantined-messages"></a>Verwalten Ihrer Nachrichten in Quarantäne

Nachdem Sie eine Nachricht oder eine Gruppe von Nachrichten ausgewählt haben, haben Sie mehrere Optionen zum Verwalten von Nachrichten in Quarantäne.
  
- Keine Aktion ausführen. Wenn Sie sich entschließen, keine Aktion auszuführen, wird die Nachricht von Office 365 automatisch nach Ablauf gelöscht. Bedenken Sie, dass von Office 365 aus der Quarantäne gelöschte Nachrichten nicht wiederhergestellt werden können.
    
- **Nachricht freigeben**: Sie können eine in Quarantäne befindliche Nachricht (oder eine Gruppe von Nachrichten) freigeben und an Ihr Postfach senden. Wenn Sie eine Nachricht freigeben, haben Sie die Möglichkeit, die Nachricht zur Analyse an Microsoft zu melden. 
    
    Wenn Sie sich entscheiden, eine Nachricht zu melden (auch "Nachricht als falsch positiv melden"), wird die Nachricht dem Microsoft-Spamanalyseteam gemeldet. Das Team wertet die Nachricht aus und analysiert falsch positive Nachrichten. Je nach dem Ergebnis der Analyse werden die dienstinternen Spaminhaltsfilterregeln möglicherweise angepasst, damit diese Nachrichten durchgelassen werden können.
    
- **Nachricht herunterladen**: Ermöglicht es Ihnen, die Nachricht als EML-Datei herunterzuladen. Sobald Sie eine Nachricht heruntergeladen haben, können Sie die EML-Datei mit Ihrem E-Mail-Client überprüfen, bevor Sie sie freigeben. 
    
- **Aus Quarantäne entfernen**: Löscht die Nachricht sofort aus der Quarantäne, ohne sie in Ihr Postfach freizugeben. 
    

