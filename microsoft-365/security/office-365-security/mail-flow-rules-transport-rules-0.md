---
title: Nachrichtenflussregeln (Transportregeln) in Exchange Online Protection
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9c2cf227-eff7-48ef-87fb-487186e47363
description: Sie können Nachrichtenfluss Regeln (Transportregeln) verwenden, um Nachrichten zu identifizieren und zu ergreifen, die in Ihrer Office 365 Organisation fließen.
ms.openlocfilehash: 42b55893a9884b547a0d2d36e901169153d290d7
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599022"
---
# <a name="mail-flow-rules-transport-rules-in-exchange-online-protection"></a>Nachrichtenflussregeln (Transportregeln) in Exchange Online Protection

Mithilfe von Nachrichtenflussregeln (auch bekannt als Transportregeln) können Sie Nachrichten, die über Ihre Office 365-Organisation fließen, identifizieren und Maßnahmen dafür ergreifen. Nachrichtenflussregeln sind mit den Posteingangsregeln vergleichbar, die in Outlook und Outlook im Web zur Verfügung stehen. Der Hauptunterschied besteht darin, dass Nachrichtenflussregeln Nachrichten während der Übertragung behandeln und nicht nach der Übermittlung der Nachricht an das Postfach. Nachrichtenflussregeln enthalten einen reichhaltigeren Satz an Bedingungen, Ausnahmen und Aktionen, sodass Sie über die Flexibilität verfügen, viele Arten von Nachrichtenrichtlinien zu implementieren.

In diesem Artikel werden die Komponenten von Nachrichtenflussregeln und deren Funktionsweise erläutert.

Schritte zum Erstellen, kopieren und Verwalten von Nachrichtenfluss Regeln finden Sie unter [Manage Mail Flow Rules in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules). Bei jeder Regel haben Sie die Möglichkeit, sie zu erzwingen, sie zu testen oder sie zu testen und den Absender zu benachrichtigen. Weitere Informationen zu den Testoptionen finden Sie unter [Test Mail Flow Rules](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/test-mail-flow-rules) and [Policy Tips in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/policy-tips).

Eine Zusammenfassung und ausführliche Berichte zu Nachrichten, die Nachrichtenflussregeln entsprechen, finden Sie unter [Verwenden von Berichten zum E-Mail-Schutz in Office 365, um Daten über Schadsoftware, Spam und Regelerkennung anzuzeigen](https://docs.microsoft.com/exchange/monitoring/use-mail-protection-reports).

Informationen zur Implementierung bestimmter Nachrichtenrichtlinien mithilfe von Nachrichtenflussregeln finden Sie in den folgenden Themen:

- [Verwenden von Nachrichtenfluss Regeln zum Überprüfen von Nachrichtenanlagen in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

- [Einrichten der Verschlüsselung in Office 365 Enterprise](../../compliance/set-up-encryption.md)

- [Organisationsweite Nachrichten Haftungsausschlüsse, Signaturen, Fußzeilen oder Kopfzeilen in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers)

- [Verwenden von Nachrichtenflussregeln zum Festlegen der SCL-Bewertung (Spam Confidence Level) in Nachrichten ](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

- [Erstellen von Block Absenderlisten in Office 365](create-block-sender-lists-in-office-365.md)

- [Reduzieren von Schadsoftwarebedrohungen durch das Blockieren von Dateianlagen in Exchange Online Protection](reducing-malware-threats-through-file-attachment-blocking-in-exchange-online-pro.md)

- [Definieren von Regeln zum Verschlüsseln oder Entschlüsseln von e-Mails in Office 365](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)

Das folgende Video bietet eine Demonstration zum Einrichten von Nachrichtenfluss Regeln in Exchange Online Schutz.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/7cdcd2cb-9382-4065-98e1-81257b32a189?autoplay=false]

## <a name="mail-flow-rule-components"></a>Komponenten von Nachrichtenflussregeln

Eine Nachrichtenflussregel besteht aus Bedingungen, Ausnahmen, Aktionen und Eigenschaften:

- **Bedingungen**: identifizieren Sie die Nachrichten, auf die Sie die Aktionen anwenden möchten. Einige Bedingungen untersuchen Nachrichtenkopffelder (beispielsweise die Felder "an", "von" oder "CC"). Andere Bedingungen untersuchen Nachrichteneigenschaften (beispielsweise Nachrichtenbetreff, Text, Anlagen, Nachrichtengröße oder Nachrichtenklassifikation). Bei den meisten Bedingungen müssen Sie einen Vergleichsoperator angeben (beispielsweise Equals, doesn 't EQUAL oder Contains) und einen Wert, der übereinstimmen soll. Wenn keine Bedingungen oder Ausnahmen vorhanden sind, wird die Regel auf alle Nachrichten angewendet.

Weitere Informationen zu Bedingungen für Nachrichtenfluss Regeln in Exchange Online Protection finden Sie unter [Nachrichtenfluss Regelbedingungen und Ausnahmen (Prädikate) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

- **Ausnahmen**: identifizieren Sie optional die Nachrichten, auf die die Aktionen nicht angewendet werden sollten. In Ausnahmen sind die gleichen Nachrichten-IDs verfügbar wie in Bedingungen. Mit Ausnahmen werden Bedingungen außer Kraft gesetzt, und es wird verhindert, dass die Regelaktionen auf eine Nachricht angewendet werden, und zwar auch dann, wenn die Nachricht allen konfigurierten Bedingungen entspricht.

- **Actions**: Geben Sie an, was mit Nachrichten ausgeführt werden soll, die den Bedingungen in der Regel entsprechen, und stimmen Sie keiner der Ausnahmen überein. Es stehen zahlreiche Aktionen zur Verfügung, wie Ablehnen, Löschen oder Umleiten von Nachrichten, Hinzufügen weiterer Empfänger, Hinzufügen von Präfixen zum Nachrichtenbetreff oder Einfügen von Haftungsausschlüssen in den Nachrichtentext.

Weitere Informationen zu Aktionen für Nachrichtenfluss Regeln, die in Exchange Online Protection verfügbar sind, finden Sie unter [Aktionen für Nachrichtenfluss Regeln in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).

- **Eigenschaften**: Geben Sie andere Regeleinstellungen an, die keine Bedingungen, Ausnahmen oder Aktionen sind. Zum Beispiel, wann die Regel angewendet werden soll, ob die Regel erzwungen oder getestet werden soll und in welchem Zeitraum die Regel aktiv ist.

  Weitere Informationen finden Sie im Abschnitt [Eigenschaften von Nachrichtenflussregeln](#mail-flow-rule-properties) in diesem Thema.

### <a name="multiple-conditions-exceptions-and-actions"></a>Mehrere Bedingungen, Ausnahmen und Aktionen

Die folgende Tabelle zeigt, wie mehrere Bedingungen, Bedingungswerte, Ausnahmen und Aktionen in einer Regel verarbeitet werden.

|**Komponente**|**Logik**|**Kommentare**|
|:-----|:-----|:-----|
|Kommentare|UND|Eine Nachricht muss allen Bedingungen in der Regel entsprechen. Wenn eine von zwei Bedingungen erfüllt werden muss, verwenden Sie für die Bedingungen separate Regeln. Wenn Sie z. B. Nachrichten mit Anlagen und Nachrichten, die einen bestimmten Text enthalten, die gleiche Haftungsausschlusserklärung hinzufügen möchten, erstellen Sie für jede Bedingung eine Regel. In der Exchange-Verwaltungskonsole können Sie eine Regel ganz einfach kopieren.|
|Eine Nachricht muss allen Bedingungen in der Regel entsprechen. Wenn eine bestimmte Bedingung erfüllt werden muss, verwenden Sie für jede Bedingung separate Regeln. Wenn Sie Nachrichten mit Anlagen und Nachrichten mit Inhalt, der einem Muster entspricht, z. B. die gleichen Haftungsausschlusserklärung hinzufügen möchten, erstellen Sie für jede Bedingung eine Regel. Sie können eine Regel problemlos kopieren.|ODER|Bei einigen Bedingungen können Sie mehr als einen Wert angeben. Die Nachricht muss einem der angegebenen Werte (nicht allen) entsprechen. Beispiel: Wenn eine E-Mail den Betreff Informationen zum Börsenkurs hat und die Bedingung **Betreff enthält eines der folgenden Wörter** für die Übereinstimmung mit den Wörtern Contoso oder Börsenkurs konfiguriert ist, gilt die Bedingung als erfüllt, da der Betreff mindestens einen der angegebenen Werte enthält.  |
|Bei einigen Bedingungen können Sie mehr als einen Wert angeben. Wenn eine Bedingung die Eingabe mehrerer Werte zulässt, muss die Nachricht einem der Werte entsprechen, der für diese Bedingung angegeben wurde. Beispiel: Wenn eine E-Mail den Betreff Informationen zum Börsenkurs hat und die Bedingung Betreff enthält eines der folgenden Wörter für die Übereinstimmung mit den Wörtern Contoso oder Börsenkurs konfiguriert ist, gilt die Bedingung als erfüllt, da der Betreff mindestens einen der Bedingungswerte enthält.|ODER|Wenn eine Nachricht einer der Ausnahmen entspricht, werden die Aktionen nicht angewendet. Die Nachricht muss nicht allen Ausnahmen entsprechen.|
|Wenn eine Nachricht einer der Ausnahmen entspricht, werden die Aktionen nicht durchgeführt. Die Nachricht muss nicht allen Ausnahmen entsprechen.|UND|Für Nachrichten, die die Bedingungen einer Regel erfüllen, werden alle in der Regel angegebenen Aktionen ausgeführt. Wenn beispielsweise die Aktionen **Dem Betreff der Nachricht Folgendes voranstellen** und **Empfänger zum Feld "Bcc" hinzufügen** ausgewählt wurden, werden beide Aktionen auf die Nachricht angewendet.  <br/><br/> Bei Nachrichten, die den Bedingungen einer Regel entsprechen, werden alle in der Regel angegebenen Aktionen durchgeführt. Wenn beispielsweise die Aktionen "Dem Betreff der Nachricht Folgendes voranstellen" und "Empfänger zum Feld "Bcc" hinzufügen" ausgewählt wurden, werden beide Aktionen auf die Nachricht angewendet. In der Nachricht wird die angegebene Zeichenfolge dem Nachrichtenbetreff vorangestellt, und die angegebenen Empfänger werden als Bcc-Empfänger hinzugefügt.<br/><br/> Sie können für eine Regel auch eine Aktion festlegen, sodass bei Anwendung dieser Regel nachfolgende Regeln nicht auf die Nachricht angewendet werden.|

### <a name="mail-flow-rule-properties"></a>Eigenschaften von Nachrichtenflussregeln

Die folgende Tabelle beschreibt die Regeleigenschaften, die in Nachrichtenflussregeln zur Verfügung stehen.

|**Eigenschaftenname in der Exchange-Verwaltungskonsole**|**Parametername in PowerShell**|**Beschreibung**|
|:-----|:-----|:-----|
|**Priority**|_Priority_|Gibt die Reihenfolge an, in der die Regeln auf Nachrichten angewendet werden. Die Standardpriorität basiert auf dem Erstellungsdatum der Regel (ältere Regeln haben eine höhere Priorität als neuere Regeln, und Regeln mit höherer Priorität werden vor Regeln mit niedrigerer Priorität verarbeitet).   <br/><br/> Sie ändern die Regelpriorität in der Exchange-Verwaltungskonsole, indem Sie die Regel in der Liste der Regeln nach oben oder unten verschieben. In der PowerShell legen Sie die Prioritätsnummer fest (0 ist die höchste Priorität).   <br/><br/> Wenn Sie z. B. eine Regel verwenden, um Nachrichten abzulehnen, die eine Kreditkartennummer enthalten, und eine andere Regel, die eine Genehmigung erfordert, sollte die Ablehnungsregel zuerst angewendet werden, und es sollten keine anderen Regeln mehr angewendet werden.      |
|**Mode**|_Mode_|Sie können angeben, ob die Regel sofort mit der Verarbeitung von Nachrichten beginnen soll oder ob Sie Regeln ohne Auswirkungen auf die Übermittlung der Nachricht (mit oder ohne Verhinderung von Datenverlust oder DLP-Richtlinientipps) testen möchten. <br/><br/> Richtlinientipps zeigen dem Ersteller einer Nachricht in Outlook oder Outlook im Web einen Hinweis mit Informationen über mögliche Richtlinienverletzungen an. Weitere Informationen finden Sie unter **Policy Tips**.  <br/><br/> Weitere Informationen zu den Modi finden Sie unter **Test a mail flow rule**.|
|**Diese Regel an folgendem Datum aktivieren** <br/><br/> **Diese Regel an folgendem Datum deaktivieren**|_ActivationDate_ <br/> _Ablaufdatum_|Gibt den Datumsbereich an, in dem die Regel aktiv ist.|
|Kontrollkästchen **Ein** aktiviert oder nicht aktiviert|Neue Regeln: Parameter _Enabled_ im Cmdlet **New-TransportRule** . <br/><br/> Vorhandene Regeln: Verwenden Sie die Cmdlets **Enable-TransportRule** oder **Disable-TransportRule**. <br/><br/> Der Wert wird in der **State** -Eigenschaft der Regel angezeigt.|Sie können eine deaktivierte Regel erstellen und diese aktivieren, wenn Sie sie testen möchten. Alternativ können Sie eine Regel deaktivieren, ohne sie zu löschen, um die Einstellungen beizubehalten.|
|**Nachricht zurückstellen, wenn die Regelverarbeitung nicht abgeschlossen wird**|_RuleErrorAction_|Sie können angeben, wie die Nachricht behandelt werden soll, wenn die Regelverarbeitung nicht abgeschlossen werden kann. Standardmäßig wird die Regel ignoriert, aber Sie können angeben, dass die Nachricht erneut zur Verarbeitung übermittelt werden soll.|
|**Absenderadresse in Nachricht vergleichen**|_SenderAddressLocation_|Wenn die Regel Bedingungen oder Ausnahmen verwendet, die die E-Mail-Adresse des Absenders überprüfen, finden Sie den Wert in der Nachrichtenkopfzeile und/oder im Nachrichtenumschlag.|
|**Verarbeiten weiterer Regeln beenden**|_SenderAddressLocation_|Dies ist eine Aktion für die Regel, aber sie sieht in der Exchange-Verwaltungskonsole wie eine Eigenschaft aus. Sie können auswählen, dass keine weiteren Regeln auf eine Nachricht angewendet werden, nachdem eine Nachricht durch eine Regel verarbeitet wurde.|
|**Comments**|_Comments_|Sie können beschreibende Kommentare zur Regel eingeben.|

## <a name="how-mail-flow-rules-are-applied-to-messages"></a>Wie Nachrichtenflussregeln auf Nachrichten angewendet werden

Alle Nachrichten, die Ihre Organisation durchlaufen, werden anhand der aktivierten Nachrichtenflussregeln in Ihrer Organisation ausgewertet. Regeln werden in der Reihenfolge verarbeitet, die auf der Seite **Nachrichtenfluss** \> **Regeln** in der Exchange-Verwaltungskonsole aufgeführt ist, oder basierend auf dem entsprechenden _Priority_ -Parameterwert in der PowerShell.

Jede Regel bietet außerdem die Möglichkeit, die Verarbeitung weiterer Regeln anzuhalten, wenn die Regel erfüllt wird. Diese Einstellung ist für Nachrichten wichtig, die die Bedingungen in mehreren E-Mail-Flussregeln erfüllen. (Welche Regel soll auf die die Nachricht angewendet werden? Alle? Nur eine?)

### <a name="differences-in-processing-based-on-message-type"></a>Unterschiede in der Verarbeitung basierend auf dem Nachrichtentyp

Es gibt verschiedene Nachrichtentypen, die eine Organisation durchlaufen. Die folgende Tabelle zeigt, welche Nachrichtentypen von Nachrichtenflussregeln verarbeitet werden können.

****

|**Nachrichtentyp**|**Kann eine Regel angewendet werden?**|
|:-----|:-----|
|**Reguläre Nachrichten**: Nachrichten, die ein einzelnes Rich-Text-Format (RTF), HTML oder nur-Text-Nachrichtentext oder eine mehrteilige oder alternative Gruppe von Nachrichtentexten enthalten.|Ja|
|**Office 365 Nachrichtenverschlüsselung**: Nachrichten, die von Office 365 Nachrichtenverschlüsselung in Office 365 verschlüsselt wurden. Weitere Informationen finden Sie unter [Verschlüsselung in Office 365](https://docs.microsoft.com/microsoft-365/compliance/encryption).|Regeln können immer auf Umschlagkopfzeilen zugreifen und Nachrichten auf Grundlage von Bedingungen verarbeiten, mit denen diese Kopfzeilen untersucht werden. <br/><br/> Damit eine Regel den Inhalt einer verschlüsselten Nachricht überprüft oder ändert, müssen Sie überprüfen, ob die Transportentschlüsselung aktiviert ist („Obligatorisch" oder „Optional"; der Standardwert ist „Optional"). Weitere Informationen finden Sie unter [Definieren von Regeln zum Verschlüsseln oder Entschlüsseln von e-Mail-Nachrichten in Office 365](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).|
|**S/MIME-Verschlüsselte Nachrichten**|Regeln können nur auf Umschlagkopfzeilen zugreifen und Nachrichten auf Grundlage von Bedingungen verarbeiten, mit denen diese Kopfzeilen untersucht werden. <br/><br/> Regeln mit Bedingungen, die eine Untersuchung des Nachrichteninhalts erfordern, oder Aktionen, die den Inhalt der Nachricht ändern, können nicht verarbeitet werden.|
|**RMS-geschützte nach**richten: Nachrichten, für die eine Active Directory Rights Management Services (AD RMS) oder eine Azure Rights Management (RMS)-Richtlinie angewendet wurde.|Regeln können immer auf Umschlagkopfzeilen zugreifen und Nachrichten auf Grundlage von Bedingungen verarbeiten, mit denen diese Kopfzeilen untersucht werden. <br/><br/> Damit eine Regel den Inhalt einer RMS-geschützten Nachricht überprüft oder ändert, müssen Sie überprüfen, ob die Transportentschlüsselung aktiviert ist („Obligatorisch" oder „Optional"; der Standardwert ist „Optional").|
|**Clear-signed Messages**: signierte, aber nicht verschlüsselte Nachrichten.|Ja|
|**Um-Nachrichten**: Nachrichten, die vom Unified Messaging-Dienst erstellt oder verarbeitet werden, wie Voicemail, Fax, Benachrichtigungen über verpasste Anrufe und Nachrichten, die mit Microsoft Outlook Voice Access erstellt oder weitergeleitet wurden.|Ja|
|**Anonyme nach**richten: von anonymen Absendern gesendete Nachrichten.|Ja|
|**Lesen von Berichten**: Berichte, die als Reaktion auf Lese Bestätigungsanforderungen von Absendern generiert werden. Lese Berichte haben eine Nachrichtenklasse von `IPM.Note*.MdnRead` oder `IPM.Note*.MdnNotRead`.|Ja|

## <a name="what-else-should-i-know"></a>Was muss ich sonst noch wissen?

- Der Wert der **Version** oder der **RuleVersion** -Eigenschaft für eine Regel ist in Exchange Online Schutz nicht wichtig.

- Nach dem Erstellen oder Ändern einer E-Mail-Flussregel kann es bis zu 30 Minuten dauern, bis die neue oder aktualisierte Regel auf Nachrichten angewendet wird.

## <a name="for-more-information"></a>Weitere Informationen

[Verwenden von Nachrichtenfluss Regeln zum Überprüfen von Nachrichtenanlagen in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

[E-Mail-Verschlüsselung in Office 365](https://docs.microsoft.com/office365/securitycompliance/email-encryption)

[Journal-, Transport- und Posteingangsregelgrenzen](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#journal-transport-and-inbox-rule-limits)
