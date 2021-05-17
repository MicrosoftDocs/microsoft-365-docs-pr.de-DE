---
title: Nachrichtenflussregeln in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 9c2cf227-eff7-48ef-87fb-487186e47363
description: Sie können Nachrichtenflussregeln (Transportregeln) verwenden, um Nachrichten zu identifizieren und Maßnahmen zu ergreifen, die durch Ihre Organisation fließen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 06ff4c723d0c7d8bba2e24ece1b62007f14198e2
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206271"
---
# <a name="mail-flow-rules-transport-rules-in-standalone-eop"></a>Nachrichtenflussregeln (Transportregeln) in EOP als eigenständige Lösung

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online Postfächer können Sie Nachrichtenflussregeln (auch als Transportregeln bezeichnet) verwenden, um Nachrichten zu identifizieren und Maßnahmen zu ergreifen, die durch Ihre Organisation fließen.

In diesem Thema werden die Komponenten von Nachrichtenflussregeln und deren Funktionsweise erläutert.

Schritte zum Erstellen, Kopieren und Verwalten von Nachrichtenflussregeln finden Sie unter [Verwalten von Nachrichtenflussregeln in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules). Bei jeder Regel haben Sie die Möglichkeit, sie zu erzwingen, sie zu testen oder sie zu testen und den Absender zu benachrichtigen. Weitere Informationen zu den Testoptionen finden Sie unter [Test mail flow rules](/exchange/security-and-compliance/mail-flow-rules/test-mail-flow-rules) and Policy Tipps in [Exchange Online](/exchange/security-and-compliance/data-loss-prevention/policy-tips).

Zusammenfassungs- und Detailberichte zu Nachrichten, die mit Nachrichtenflussregeln übereinstimmen, finden Sie unter Verwenden von E-Mail-Schutzberichten zum Anzeigen von Daten zu Schadsoftware, Spam und [Regelerkennungen.](/exchange/monitoring/use-mail-protection-reports)

Informationen zur Implementierung bestimmter Nachrichtenrichtlinien mithilfe von Nachrichtenflussregeln finden Sie in den folgenden Themen:

- [Verwenden von Nachrichtenflussregeln zum Überprüfen von Nachrichtenanlagen in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

- [Einrichten der Verschlüsselung in Office 365 Enterprise](../../compliance/set-up-encryption.md)

- [Organisationsweite Haftungsausschlüsse, Signaturen, Fußzeilen oder Kopfzeilen in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers)

- [Verwenden von Nachrichtenflussregeln zum Festlegen der SCL-Bewertung (Spam Confidence Level) in Nachrichten ](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

- [Erstellen von Listen mit blockierten Absendern in EOP](create-block-sender-lists-in-office-365.md)

- [Reduzieren von Schadsoftwarebedrohungen durch das Blockieren von Dateianlagen in Exchange Online Protection](reducing-malware-threats-through-file-attachment-blocking-in-exchange-online-pro.md)

- [Definieren von Regeln zum Verschlüsseln oder Entschlüsseln von E-Mail-Nachrichten in Office 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md)

Im folgenden Video wird das Einrichten von Nachrichtenflussregeln in eigenständigem EOP demonstriert.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/7cdcd2cb-9382-4065-98e1-81257b32a189?autoplay=false]

## <a name="mail-flow-rule-components"></a>Komponenten von Nachrichtenflussregeln

Eine Nachrichtenflussregel besteht aus Bedingungen, Ausnahmen, Aktionen und Eigenschaften:

- **Bedingungen**: Identifizieren Sie die Nachrichten, auf die Sie die Aktionen anwenden möchten. Einige Bedingungen untersuchen Nachrichtenkopffelder (z. B. die Felder An, From oder Cc). Andere Bedingungen untersuchen Nachrichteneigenschaften (z. B. Nachrichtensubjekt, Textkörper, Anlagen, Nachrichtengröße oder Nachrichtenklassifikation). Für die meisten Bedingungen müssen Sie einen Vergleichsoperator (z. B. gleich, nicht gleich oder enthält) und einen wert angeben, der übereinstimmen soll. Wenn keine Bedingungen oder Ausnahmen gelten, wird die Regel auf alle Nachrichten angewendet.

Weitere Informationen zu Nachrichtenflussregelbedingungen in eigenständigem EOP finden Sie unter Nachrichtenflussregelbedingungen und Ausnahmen [(Prädikate) in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

- **Ausnahmen:** Identifizieren Sie optional die Nachrichten, auf die die Aktionen nicht angewendet werden sollen. In Ausnahmen sind die gleichen Nachrichten-IDs verfügbar wie in Bedingungen. Mit Ausnahmen werden Bedingungen außer Kraft gesetzt, und es wird verhindert, dass die Regelaktionen auf eine Nachricht angewendet werden, und zwar auch dann, wenn die Nachricht allen konfigurierten Bedingungen entspricht.

- **Aktionen**: Geben Sie an, was mit Nachrichten zu tun ist, die den Bedingungen in der Regel entsprechen, und keines der Ausnahmen. Es stehen zahlreiche Aktionen zur Verfügung, wie Ablehnen, Löschen oder Umleiten von Nachrichten, Hinzufügen weiterer Empfänger, Hinzufügen von Präfixen zum Nachrichtenbetreff oder Einfügen von Haftungsausschlüssen in den Nachrichtentext.

Weitere Informationen zu Nachrichtenflussregelaktionen, die in eigenständigen EOP verfügbar sind, finden Sie unter [Nachrichtenflussregelaktionen in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).

- **Eigenschaften**: Geben Sie andere Regeleinstellungen an, die keine Bedingungen, Ausnahmen oder Aktionen sind. Zum Beispiel, wann die Regel angewendet werden soll, ob die Regel erzwungen oder getestet werden soll und in welchem Zeitraum die Regel aktiv ist.

  Weitere Informationen finden Sie im Abschnitt [Nachrichtenflussregeleigenschaften](#mail-flow-rule-properties) in diesem Artikel.

### <a name="multiple-conditions-exceptions-and-actions"></a>Mehrere Bedingungen, Ausnahmen und Aktionen

Use a transport rule so messages can bypass Clutter

****

|Komponente|Logik|Kommentare|
|---|---|---|
|Kommentare|UND|Eine Nachricht muss allen Bedingungen in der Regel entsprechen. Wenn eine von zwei Bedingungen erfüllt werden muss, verwenden Sie für die Bedingungen separate Regeln. Wenn Sie z. B. Nachrichten mit Anlagen und Nachrichten, die einen bestimmten Text enthalten, die gleiche Haftungsausschlusserklärung hinzufügen möchten, erstellen Sie für jede Bedingung eine Regel. In der Exchange-Verwaltungskonsole können Sie eine Regel ganz einfach kopieren.|
|Eine Nachricht muss allen Bedingungen in der Regel entsprechen. Wenn eine bestimmte Bedingung erfüllt werden muss, verwenden Sie für jede Bedingung separate Regeln. Wenn Sie Nachrichten mit Anlagen und Nachrichten mit Inhalt, der einem Muster entspricht, z. B. die gleichen Haftungsausschlusserklärung hinzufügen möchten, erstellen Sie für jede Bedingung eine Regel. Sie können eine Regel problemlos kopieren.|ODER|Bei einigen Bedingungen können Sie mehr als einen Wert angeben. Die Nachricht muss einem der angegebenen Werte (nicht allen) entsprechen. Beispiel: Wenn eine E-Mail den Betreff Informationen zum Börsenkurs hat und die Bedingung **Betreff enthält eines der folgenden Wörter** für die Übereinstimmung mit den Wörtern Contoso oder Börsenkurs konfiguriert ist, gilt die Bedingung als erfüllt, da der Betreff mindestens einen der angegebenen Werte enthält.  |
|Bei einigen Bedingungen können Sie mehr als einen Wert angeben. Wenn eine Bedingung die Eingabe mehrerer Werte zulässt, muss die Nachricht einem der Werte entsprechen, der für diese Bedingung angegeben wurde. Beispiel: Wenn eine E-Mail den Betreff Informationen zum Börsenkurs hat und die Bedingung Betreff enthält eines der folgenden Wörter für die Übereinstimmung mit den Wörtern Contoso oder Börsenkurs konfiguriert ist, gilt die Bedingung als erfüllt, da der Betreff mindestens einen der Bedingungswerte enthält.|ODER|Wenn eine Nachricht einer der Ausnahmen entspricht, werden die Aktionen nicht angewendet. Die Nachricht muss nicht allen Ausnahmen entsprechen.|
|Wenn eine Nachricht einer der Ausnahmen entspricht, werden die Aktionen nicht durchgeführt. Die Nachricht muss nicht allen Ausnahmen entsprechen.|UND|Für Nachrichten, die die Bedingungen einer Regel erfüllen, werden alle in der Regel angegebenen Aktionen ausgeführt. Wenn beispielsweise die Aktionen **Dem Betreff der Nachricht Folgendes voranstellen** und **Empfänger zum Feld "Bcc" hinzufügen** ausgewählt wurden, werden beide Aktionen auf die Nachricht angewendet.  <p> Bei Nachrichten, die den Bedingungen einer Regel entsprechen, werden alle in der Regel angegebenen Aktionen durchgeführt. Wenn beispielsweise die Aktionen "Dem Betreff der Nachricht Folgendes voranstellen" und "Empfänger zum Feld "Bcc" hinzufügen" ausgewählt wurden, werden beide Aktionen auf die Nachricht angewendet. In der Nachricht wird die angegebene Zeichenfolge dem Nachrichtenbetreff vorangestellt, und die angegebenen Empfänger werden als Bcc-Empfänger hinzugefügt.<p> Sie können für eine Regel auch eine Aktion festlegen, sodass bei Anwendung dieser Regel nachfolgende Regeln nicht auf die Nachricht angewendet werden.|
|

### <a name="mail-flow-rule-properties"></a>Eigenschaften von Nachrichtenflussregeln

Die folgende Tabelle beschreibt die Regeleigenschaften, die in Nachrichtenflussregeln zur Verfügung stehen.

****

|Eigenschaftenname in der Exchange-Verwaltungskonsole|Parametername in PowerShell|Beschreibung|
|---|---|---|
|**Priority**|_Priority_|Gibt die Reihenfolge an, in der die Regeln auf Nachrichten angewendet werden. Die Standardpriorität basiert auf dem Erstellungsdatum der Regel (ältere Regeln haben eine höhere Priorität als neuere Regeln, und Regeln mit höherer Priorität werden vor Regeln mit niedrigerer Priorität verarbeitet).   <p> Sie ändern die Regelpriorität in der Exchange-Verwaltungskonsole, indem Sie die Regel in der Liste der Regeln nach oben oder unten verschieben. In PowerShell legen Sie die Prioritätsnummer (0 ist die höchste Priorität) festgelegt. <p> Wenn Sie z. B. eine Regel verwenden, um Nachrichten abzulehnen, die eine Kreditkartennummer enthalten, und eine andere Regel, die eine Genehmigung erfordert, sollte die Ablehnungsregel zuerst angewendet werden, und es sollten keine anderen Regeln mehr angewendet werden.      |
|**Mode**|_Mode_|Sie können angeben, ob die Regel sofort mit der Verarbeitung von Nachrichten beginnen soll oder ob Sie Regeln ohne Auswirkungen auf die Übermittlung der Nachricht (mit oder ohne Verhinderung von Datenverlust oder DLP-Richtlinientipps) testen möchten. <p> Richtlinientipps zeigen dem Ersteller einer Nachricht in Outlook oder Outlook im Web einen Hinweis mit Informationen über mögliche Richtlinienverletzungen an. Weitere Informationen finden Sie unter **Policy Tips**.  <p> Weitere Informationen zu den Modi finden Sie unter **Test a mail flow rule**.|
|**Diese Regel an folgendem Datum aktivieren** <p> **Diese Regel an folgendem Datum deaktivieren**|_ActivationDate_ <p> _ExpiryDate_|Gibt den Datumsbereich an, in dem die Regel aktiv ist.|
|Kontrollkästchen **Ein** aktiviert oder nicht aktiviert|Neue Regeln: _Enabled-Parameter_ im **Cmdlet New-TransportRule.** <p> Vorhandene Regeln: Verwenden Sie die Cmdlets **Enable-TransportRule** oder **Disable-TransportRule**. <p> Der Wert wird in der **State** -Eigenschaft der Regel angezeigt.|Sie können eine deaktivierte Regel erstellen und diese aktivieren, wenn Sie sie testen möchten. Alternativ können Sie eine Regel deaktivieren, ohne sie zu löschen, um die Einstellungen beizubehalten.|
|**Nachricht zurückstellen, wenn die Regelverarbeitung nicht abgeschlossen wird**|_RuleErrorAction_|Sie können angeben, wie die Nachricht behandelt werden soll, wenn die Regelverarbeitung nicht abgeschlossen werden kann. Standardmäßig wird die Regel ignoriert, aber Sie können angeben, dass die Nachricht erneut zur Verarbeitung übermittelt werden soll.|
|**Absenderadresse in Nachricht vergleichen**|_SenderAddressLocation_|Wenn die Regel Bedingungen oder Ausnahmen verwendet, die die E-Mail-Adresse des Absenders überprüfen, finden Sie den Wert in der Nachrichtenkopfzeile und/oder im Nachrichtenumschlag.|
|**Verarbeiten weiterer Regeln beenden**|_SenderAddressLocation_|Dies ist eine Aktion für die Regel, aber sie sieht in der Exchange-Verwaltungskonsole wie eine Eigenschaft aus. Sie können auswählen, dass keine weiteren Regeln auf eine Nachricht angewendet werden, nachdem eine Nachricht durch eine Regel verarbeitet wurde.|
|**Comments**|_Comments_|Sie können beschreibende Kommentare zur Regel eingeben.|
|

## <a name="how-mail-flow-rules-are-applied-to-messages"></a>Wie Nachrichtenflussregeln auf Nachrichten angewendet werden

Alle Nachrichten, die Ihre Organisation durchlaufen, werden anhand der aktivierten Nachrichtenflussregeln in Ihrer Organisation ausgewertet. Regeln werden in der auf der Seite **Nachrichtenflussregeln** in EAC aufgeführten Reihenfolge oder basierend auf dem entsprechenden \>  _Priority-Parameterwert_ in PowerShell verarbeitet.

Jede Regel bietet außerdem die Möglichkeit, die Verarbeitung weiterer Regeln anzuhalten, wenn die Regel erfüllt wird. Diese Einstellung ist für Nachrichten wichtig, die die Bedingungen in mehreren E-Mail-Flussregeln erfüllen. (Welche Regel soll auf die die Nachricht angewendet werden? Alle? Nur eine?)

### <a name="differences-in-processing-based-on-message-type"></a>Unterschiede in der Verarbeitung basierend auf dem Nachrichtentyp

Es gibt verschiedene Nachrichtentypen, die eine Organisation durchlaufen. Die folgende Tabelle zeigt, welche Nachrichtentypen von Nachrichtenflussregeln verarbeitet werden können.

****

|Es gibt verschiedene Nachrichtentypen, die eine Organisation durchlaufen. Die folgende Tabelle zeigt, welche Nachrichtentypen von Transportregeln verarbeitet werden können.|Nachrichtentyp|
|---|---|
|**Reguläre Nachrichten:** Nachrichten, die ein einzelnes Rich-Text-Format (RTF), HTML- oder Nur-Text-Nachrichtentext oder einen mehrteiligen oder alternativen Satz von Nachrichtentexten enthalten.|Ja|
|**Office 365-Nachrichtenverschlüsselung**: Nachrichten, die von Office 365-Nachrichtenverschlüsselung in Office 365. Weitere Informationen finden Sie unter [Verschlüsselung in Office 365](../../compliance/encryption.md).|Regeln können immer auf Umschlagkopfzeilen zugreifen und Nachrichten auf Grundlage von Bedingungen verarbeiten, mit denen diese Kopfzeilen untersucht werden. <p> Damit eine Regel den Inhalt einer verschlüsselten Nachricht überprüft oder ändert, müssen Sie überprüfen, ob die Transportentschlüsselung aktiviert ist („Obligatorisch" oder „Optional"; der Standardwert ist „Optional"). Weitere Informationen finden Sie unter Definieren von Regeln zum Verschlüsseln oder Entschlüsseln von [E-Mail-Nachrichten in Office 365.](../../compliance/define-mail-flow-rules-to-encrypt-email.md)|
|**S/MIME-Verschlüsselte Nachrichten**|Regeln können nur auf Umschlagkopfzeilen zugreifen und Nachrichten auf Grundlage von Bedingungen verarbeiten, mit denen diese Kopfzeilen untersucht werden. <p> Regeln mit Bedingungen, die eine Untersuchung des Nachrichteninhalts erfordern, oder Aktionen, die den Inhalt der Nachricht ändern, können nicht verarbeitet werden.|
|**RMS-geschützte Nachrichten:** Nachrichten, auf die Active Directory Rights Management Services (AD RMS) oder die Azure Rights Management (RMS)-Richtlinie angewendet wurde.|Regeln können immer auf Umschlagkopfzeilen zugreifen und Nachrichten auf Grundlage von Bedingungen verarbeiten, mit denen diese Kopfzeilen untersucht werden. <p> Damit eine Regel den Inhalt einer RMS-geschützten Nachricht überprüft oder ändert, müssen Sie überprüfen, ob die Transportentschlüsselung aktiviert ist („Obligatorisch" oder „Optional"; der Standardwert ist „Optional").|
|**Klar signierte Nachrichten:** Nachrichten, die signiert, aber nicht verschlüsselt wurden.|Ja|
|**UM-Nachrichten:** Nachrichten, die vom Unified Messaging-Dienst erstellt oder verarbeitet werden, z. B. Voicemail, Fax, Benachrichtigungen über verpasste Anrufe und Nachrichten, die mithilfe von Microsoft Outlook Voice Access.|Ja|
|**Anonyme Nachrichten:** Nachrichten, die von anonymen Absendern gesendet werden.|Ja|
|**Berichte lesen:** Berichte, die als Antwort auf Lesebestätigungsanforderungen von Absendern generiert werden. Leseberichte haben eine Nachrichtenklasse von `IPM.Note*.MdnRead` oder `IPM.Note*.MdnNotRead` .|Ja|
|

## <a name="what-else-should-i-know"></a>Was muss ich sonst noch wissen?

- Der Wert der **Version-** oder **RuleVersion-Eigenschaft** für eine Regel ist in der Regel Exchange Online Protection.

- Nach dem Erstellen oder Ändern einer E-Mail-Flussregel kann es bis zu 30 Minuten dauern, bis die neue oder aktualisierte Regel auf Nachrichten angewendet wird.

## <a name="for-more-information"></a>Weitere Informationen

[Verwenden von Nachrichtenflussregeln zum Überprüfen von Nachrichtenanlagen in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

[E-Mail-Verschlüsselung in Office 365](../../compliance/email-encryption.md)

[Journal-, Transport- und Posteingangsregelgrenzen](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#journal-transport-and-inbox-rule-limits)