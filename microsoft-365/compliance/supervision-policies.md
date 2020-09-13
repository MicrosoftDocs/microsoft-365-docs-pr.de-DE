---
title: Aufsichtsrichtlinien
description: In diesem Artikel erfahren Sie mehr über die Verwendung von Aufsichtsrichtlinien in Microsoft 365 zum Erfassen von Mitarbeiterkommunikation zur Untersuchung durch designierte Bearbeiter.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.custom: seo-marvel-apr2020
titleSuffix: Microsoft 365 Compliance
ms.openlocfilehash: 27c4d4603396089cb58cfed192f09d0db70cac5a
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547585"
---
# <a name="supervision-policies"></a>Aufsichtsrichtlinien

>[!IMPORTANT]
>Nach dem Release of Communication Compliance in Microsoft 365 Compliance im Februar 2020 wird die Überwachung in Office 365 zurückgezogen. Aufsichtsrichtlinien stehen nicht mehr zur Erstellung zur Verfügung, und die Richtlinien werden nach einer längeren Lesezugriff-Zeit endgültig entfernt.
>
>Wenn Sie die Überwachung verwenden, beachten Sie Folgendes:
>
>- Ab dem 15. Juni 2020 werden Mandanten nicht in der Lage sein, neue Aufsichtsrichtlinien zu erstellen.
>- Ab dem 31. August 2020 werden durch vorhandene Richtlinien keine neuen Nachrichten mehr erfasst.
>- Ab dem 26. Oktober 2020 werden vorhandene Richtlinien gelöscht.
>
>Wir ermutigen Kunden, die derzeit die Überwachung in Office 365 untersuchen oder verwenden, aktiv dazu, die neue [Kommunikations Compliance](communication-compliance.md) -Lösung zu verwenden, um ihre Kommunikations Überwachungs-oder behördlichen Anforderungen mit einer wesentlich umfangreicheren Palette intelligenter Funktionen zu erfüllen.

Mit Aufsichtsrichtlinien in Microsoft 365 können Sie Mitarbeiter Kommunikationen zur Untersuchung durch designierte Bearbeiter erfassen. Sie können bestimmte Richtlinien definieren, die interne und externe e-Mails, Microsoft Teams oder Drittanbieter Kommunikationen in Ihrer Organisation erfassen. Bearbeiter können dann die Nachrichten überprüfen, um sicherzustellen, dass Sie mit den Nachrichtenstandards Ihrer Organisation übereinstimmen und diese mit dem Klassifizierungs lösen.

Mithilfe dieser Richtlinien können Sie auch viele moderne Anforderungen an die Compliance bewältigen, darunter:

- Überwachen der zunehmenden Typen von Kommunikationskanälen
- Die zunehmende Menge an Nachrichtendaten
- Regulatorische Durchsetzung & das Risiko von Geldbußen

In einigen Organisationen besteht möglicherweise eine Trennung der Aufgaben zwischen der IT-Unterstützung und der Compliance-Verwaltungsgruppe. Microsoft 365 unterstützt die Trennung zwischen der Konfiguration von Aufsichtsrichtlinien Features und der Konfiguration von Richtlinien für aufgezeichnete Kommunikationen. Beispielsweise kann die IT-Gruppe für eine Organisation für die Einrichtung von Rollen Berechtigungen und-Gruppen zuständig sein, um Aufsichtsrichtlinien zu unterstützen, die vom Compliance-Team der Organisation konfiguriert und verwaltet werden.

Eine kurze Übersicht über Aufsichtsrichtlinien finden Sie im [Video zur Aufsichtsrichtlinie](https://youtu.be/C3Y8WZ7o_dI) im [Microsoft Mechanics-Kanal](https://www.youtube.com/user/OfficeGarageSeries).

## <a name="transitioning-from-supervision"></a>Übergang von der Überwachung

Organisationen, die Aufsichtsrichtlinien und die Planung für den Übergang zu [Kommunikationsrichtlinien in Microsoft 365](communication-compliance.md) verwenden, müssen diese wichtigen Punkte verstehen:

- Die Überwachungslösung in Microsoft 365 wird vollständig durch die Kommunikations kompatibilitätslösung in Microsoft 365 ersetzt. Für Organisationen, die von Aufsichtsrichtlinien auf die Konformität mit der Kommunikation umstellen, wird empfohlen, neue Richtlinien in der Kommunikations Kompatibilität zu erstellen, die dieselben *Bedingungen* wie die vorhandenen Aufsichtsrichtlinien haben, um neue Untersuchungen und Korrektur Verbesserungen zu ermöglichen. Beim Übergang zur Kommunikations Kompatibilität in Microsoft 365 sollten Sie planen, Berichtsdaten aus der Beaufsichtigung zu exportieren, wenn Sie über interne Compliance-Aufbewahrungsrichtlinien Anforderungen verfügen.
- In der Zwischenzeit können Organisationen beide Lösungen nebeneinander verwenden, bis Sie vollständig migriert wurden, aber Richtlinien, die in jeder Lösung verwendet werden, müssen *eindeutige Richtliniennamen*aufweisen. Gruppen und benutzerdefinierte Schlüsselwörter Wörterbücher können während der Übergangsphase Zwischenlösungen freigegeben werden.
- Nachrichten, die in der Überwachung in Microsoft 365-Richtlinien Übereinstimmungen gespeichert wurden, können in Microsoft 365 nicht in die Kommunikations Kompatibilität verschoben oder weitergegeben werden.

Informationen zur Beaufsichtigung in Office 365 finden Sie im [Microsoft 365-Fahrplan](https://www.microsoft.com/microsoft-365/roadmap) für Vorsorge Informationen.

## <a name="scenarios-for-supervision-policies"></a>Szenarien für Aufsichtsrichtlinien

Aufsichtsrichtlinien können die Überwachung der Kommunikation in Ihrer Organisation in mehreren Bereichen unterstützen:

- **Unternehmensrichtlinien**

    Mitarbeiter müssen in ihrer geschäftsbezogenen Kommunikation angemessene Verwendung, ethische Standards und andere Unternehmensrichtlinien einhalten. Aufsichtsrichtlinien können Richtlinienverstöße erkennen und Sie bei der Durchführung von Korrekturmaßnahmen unterstützen, um diese Art von Vorfällen zu verringern. Sie können beispielsweise potenzielle Verletzungen von Humanressourcen wie Belästigung oder die Verwendung ungeeigneter oder anstößiger Sprachen in der Mitarbeiterkommunikation überwachen.

- **Risikomanagement**

    Organisationen sind für die gesamte Kommunikation verantwortlich, die über Ihre Infrastruktur und Unternehmensnetzwerk Systeme verteilt ist. Durch die Verwendung von Aufsichtsrichtlinien zur Ermittlung und Verwaltung potenzieller rechtlicher Risiken und Risiken können Risiken minimiert werden, bevor Sie Unternehmensvorgänge beschädigen können. Beispielsweise können Sie Ihre Organisation auf unbefugte Kommunikation für vertrauliche Projekte wie bevorstehende Akquisitionen, Fusionen, Gewinn Offenlegungen, Neuorganisationen oder Änderungen des Führungsteams überwachen.

- **Einhaltung gesetzlicher Bestimmungen**

    Die meisten Organisationen müssen im Rahmen ihrer normalen Betriebsverfahren einige Arten von Standards für die Einhaltung gesetzlicher Vorschriften einhalten. In diesen Vorschriften wird häufig gefordert, dass Organisationen einen Aufsichts-oder Überwachungsprozess für Messaging implementieren, der für Ihre Branche geeignet ist. Die Regel 3110 der Financial Industry Regulatory Authority (FINRA) ist ein gutes Beispiel für eine Anforderung an Organisationen, Aufsichtsverfahren für die Überwachung der Aktivitäten Ihrer Mitarbeiter und der Unternehmenstypen, in denen Sie tätig ist, zu überwachen. Ein weiteres Beispiel ist möglicherweise die Notwendigkeit, Broker Händler in Ihrer Organisation zu überwachen, um gegen potenzielle Geldwäsche, Insidergeschäfte, Absprachen oder Bestechungsaktivitäten zu schützen. Aufsichtsrichtlinien können Ihre Organisation bei der Erfüllung dieser Anforderungen unterstützen, indem Sie einen Prozess für die Überwachung und den Bericht über die Unternehmenskommunikation bereitstellen.

## <a name="components"></a>Komponenten

### <a name="supervision-policy"></a>Aufsichtsrichtlinie

Sie erstellen Aufsichtsrichtlinien im Compliance Center. Diese Richtlinien definieren, welche Kommunikation und welche Benutzer in Ihrer Organisation überprüft werden sollen, definieren benutzerdefinierte Bedingungen, denen die Kommunikation entsprechen muss, und geben an, wer Überprüfungen durchführen soll. Benutzer, die in der Rollengruppe "aufsichtsüberprüfung" enthalten sind, können Richtlinien einrichten, und jeder, dem diese Rolle zugewiesen ist, kann im Compliance Center auf die Seite "Beaufsichtigung" zugreifen.

### <a name="supervised-users"></a>Beaufsichtigte Benutzer

Bevor Sie mit der Überwachung beginnen, müssen Sie ermitteln, wer Ihre Kommunikationen überprüfen muss. In der Richtlinie identifizieren die E-Mail-Adressen der Benutzer Einzelpersonen oder Personengruppen, die überwacht werden sollen. Einige Beispiele für diese Gruppen sind Microsoft 365 Groups, Exchange-basierte Verteilerlisten und Microsoft Teams-Kanäle. Sie können auch bestimmte Benutzer oder Gruppen von der Beaufsichtigung mit einer beaufsichtigten Gruppe oder einer Liste von Gruppen ausschließen.

>[!IMPORTANT]
>Benutzer, die von Aufsichtsrichtlinien überwacht werden, müssen über eine Microsoft 365 E5-Konformitäts Lizenz, eine Office 365 Enterprise E3-Lizenz mit dem Add-on für die erweiterte Kompatibilität oder ein Office 365 Enterprise E5-Abonnement verfügen oder in einem Microsoft 365 E5-Abonnement enthalten sein. Wenn Sie über keinen vorhandenen Enterprise E5-Plan verfügen und die Überwachung testen möchten, können Sie [sich für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279).

### <a name="reviewers"></a>Prüfer

Wenn Sie eine Aufsichtsrichtlinie erstellen, müssen Sie festlegen, wer die Überprüfungen der Nachrichten der überwachten Benutzer durchführen soll. In der Richtlinie identifizieren die E-Mail-Adressen der Benutzer Einzelpersonen oder Personengruppen, welche die überwachte Kommunikation überprüfen sollen. Alle Bearbeiter müssen über Postfächer verfügen, die auf Exchange Online gehostet werden.

### <a name="groups-for-supervised-users-and-reviewers"></a>Gruppen für beaufsichtigte Benutzer und Bearbeiter

Um Ihr Setup zu vereinfachen, erstellen Sie Gruppen für Personen, die Ihre Kommunikation überprüfen müssen, sowie Gruppen für Personen, die diese Kommunikationen überprüfen. Wenn Sie Gruppen verwenden, benötigen Sie möglicherweise mehrere. Wenn Sie beispielsweise die Kommunikation zwischen zwei unterschiedlichen Personengruppen überwachen möchten oder wenn Sie eine Gruppe angeben möchten, die nicht überwacht wird.

Wenn Sie eine Microsoft 365-Gruppe für beaufsichtigte Benutzer auswählen, überwacht die Richtlinie den Inhalt des freigegebenen Postfachs und der Microsoft Teams-Kanäle, die der Gruppe zugeordnet sind. Wenn Sie eine Verteilerliste auswählen, überwacht die Richtlinie einzelne Benutzerpostfächer.

### <a name="supported-communication-types"></a>Unterstützte Kommunikationstypen

Mit Aufsichtsrichtlinien können Sie festlegen, dass Nachrichten in einer oder mehreren der folgenden Kommunikationsplattformen überwacht werden:

- **Exchange-e-Mail:** Postfächer, die auf Exchange Online als Teil Ihres Microsoft 365-Abonnements gehostet werden, sind alle für die Nachrichtenüberwachung berechtigt. E-Mails und Anhänge, die Aufsichtsrichtlinien Bedingungen entsprechen, stehen sofort für die Überwachung und in Aufsichtsberichten zur Verfügung. Unterstützte Anlagentypen für die Überwachung sind identisch mit den [Dateitypen, die für Exchange-Nachrichtenfluss Regelinhalts Inspektionen unterstützt](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)werden.

- **Microsoft Teams:** Chatnachrichten und zugehörige Anlagen sowohl in öffentlichen als auch privaten Microsoft Teams-Kanälen und einzelnen Chats können überwacht werden. Microsoft Teams-Chats entsprechende Aufsichtsrichtlinien Bedingungen werden einmal alle 24 Stunden verarbeitet und stehen dann für die Überwachung und in Aufsichtsberichten zur Verfügung. Verwenden Sie die folgenden Gruppen Verwaltungs Konfigurationen, um einzelne Benutzer Chats und Kanal Kommunikationen in Microsoft Teams zu überwachen:

    - **Für Teams-Chat Überwachung:** Zuweisen einzelner Benutzer oder Zuweisen einer [Verteilergruppe](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) zur Aufsichtsrichtlinie Diese Konfiguration ist für 1-zu-1-oder 1: n-Benutzer-/-Chat-Beziehungen.
    - **Für Teams-Kanal Kommunikation:** Weisen Sie jede Microsoft Team Channel-oder Microsoft 365-Gruppe zu, die Sie überwachen möchten, die einen bestimmten Benutzer für die Aufsichtsrichtlinie enthält. Wenn Sie denselben Benutzer anderen Microsoft Teams-Kanälen oder Microsoft 365-Gruppen hinzufügen, müssen Sie diese neuen Kanäle und Gruppen der Aufsichtsrichtlinie hinzufügen.

- **Skype for Business Online:** Chat Nachrichten und zugehörige Anlagen in Skype for Business Online können überwacht werden. Skype for Business Online Chats, die Aufsichtsrichtlinien Bedingungen entsprechen, werden einmal alle 24 Stunden verarbeitet und stehen dann für die Überwachung und in Aufsichtsberichten zur Verfügung. Überwachte Chat Unterhaltungen werden aus [früheren Unterhaltungen, die in Skype for Business Online gespeichert](https://support.office.com/article/Find-a-previous-Skype-for-Business-conversation-18892eba-5f18-4281-8c87-fd48bd72e6a2)wurden, bezogen.  Verwenden Sie die folgende Gruppen Verwaltungskonfiguration, um die Benutzer Chat Kommunikation in Skype for Business Online zu überwachen:

    - **Für Skype for Business Online Chat Überwachung:** Zuweisen einzelner Benutzer oder Zuweisen einer [Verteilergruppe](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) zur Aufsichtsrichtlinie Diese Konfiguration ist für 1-zu-1-oder 1: n-Benutzer-/-Chat-Beziehungen.

- **Drittanbieterquellen:** Sie können die Kommunikation von Drittanbieter-Quellen (wie Facebook oder Dropbox) für Daten überwachen, die in Postfächer in Ihrer Organisation importiert werden. [Hier erfahren Sie, wie Sie drittanbieterdaten importieren](archiving-third-party-data.md).

Auf diesen Plattformen erfasste Kommunikationen werden für jede Richtlinie standardmäßig sieben Jahre lang aufbewahrt, selbst wenn Benutzer Ihre Organisation verlassen und Ihr Postfach gelöscht wird.

### <a name="policy-settings"></a>Richtlinieneinstellungen

#### <a name="direction"></a>Direction

Standardmäßig wird die Bedingung " **Direction** " angezeigt und kann nicht entfernt werden. Die Einstellungen für die Kommunikationsrichtung in einer Richtlinie werden einzeln oder gemeinsam ausgewählt:

- **Eingehend**: Sie können " **eingehend** " auswählen, um die Kommunikation zu überprüfen, die **an** die Personen gesendet wird, die Sie überwachen möchten, **von** Personen, die nicht in die Richtlinie
- Ausgehend **: Sie**können ausgehend **wählen,** Wenn Sie die Kommunikation überprüfen **möchten, die** **von** den Personen gesendet wurde, die Sie für die Überwachung ausgewählt haben, die nicht in der Richtlinie enthalten sind.
- **Intern**: Sie können **interne** auswählen, um die Kommunikation zu überprüfen, die **zwischen** den Personen gesendet wird, die Sie in der Richtlinie angegeben haben.

#### <a name="sensitive-information-types"></a>Typen vertraulicher Informationen

Sie haben die Möglichkeit, vertrauliche Informationstypen als Teil ihrer Aufsichtsrichtlinie einzubinden. Vertrauliche Informationstypen sind entweder vordefinierte oder benutzerdefinierte Datentypen, die helfen, Kreditkartennummern, Bank Kontonummern, Passport-Nummern und vieles mehr zu identifizieren und zu schützen. Im Rahmen der [Verhinderung von Datenverlust (DLP)](data-loss-prevention-policies.md)können mit der Konfiguration vertraulicher Informationen Muster, Zeichen Nähe, Konfidenz Stufen und sogar benutzerdefinierte Datentypen verwendet werden, um Inhalte zu identifizieren und zu kennzeichnen, die möglicherweise vertraulich sind. Die Standardtypen für vertrauliche Informationen sind:

- Finanzwesen
- Medizin und Gesundheit
- Datenschutz
- Benutzerdefinierter Informationstyp

Weitere Informationen zu vertraulichen Informationsdetails und den Mustern, die in den Standardtypen enthalten sind, finden Sie unter [sensitive Information Type Entity Definitions](sensitive-information-type-entity-definitions.md).

#### <a name="custom-keyword-dictionaries"></a>Benutzerdefinierte Schlüsselwörter Wörterbücher

Konfigurieren Sie benutzerdefinierte Keyword-Wörterbücher (oder Lexika), um eine einfache Verwaltung von Schlüsselwörtern für Ihre Organisation oder Industrie bereitzustellen. Stichwort Wörterbücher unterstützen bis zu 100KB Begriffe (nach Komprimierung) im Wörterbuch und unterstützen jede Sprache. Die Mandantengrenze liegt nach der Komprimierung ebenfalls bei 100 KB. Bei Bedarf können Sie mehrere benutzerdefinierte Schlüsselwörter Wörterbücher auf eine einzelne Richtlinie anwenden oder über ein einzelnes Schlüssel Wörterbuch pro Richtlinie verfügen. Diese Wörterbücher werden in einer Aufsichtsrichtlinie zugewiesen und können aus einer Datei (wie einer CSV-oder txt-Liste) oder aus einer Liste, [die Sie im Compliance Center importieren](create-a-keyword-dictionary.md)können, bezogen werden.

#### <a name="offensive-language"></a>Anstößige Sprache

Überwachen von gesendeten oder empfangenen e-Mail-Nachrichten in Ihrer Organisation für anstößige Sprachen Das Modell verwendet eine Kombination aus maschinellem lernen, künstlicher Intelligenz und Stichwörtern, um die Sprache in e-Mail-Nachrichten zu identifizieren, die gegen Belästigung und Mobbing-Richtlinien verstoßen. Das Offensive Sprachmodell unterstützt derzeit englische Stichwörter und überwacht den Textkörper von e-Mail-Nachrichten.

>[!NOTE]
>Erstellen Sie eine [Richtlinie zur Verhinderung von Datenverlust](create-test-tune-dlp-policy.md) mit einem [benutzerdefinierten Stichwort Wörterbuch](create-a-keyword-dictionary.md) blockierter Ausdrücke, wenn Sie Folgendes benötigen:
>
>- Überwachen der Kommunikation von Microsoft Teams in Ihrer Organisation für anstößige Sprachen
>- verhindern oder blockieren anstößiger Sprachen in der Kommunikation in Ihrer Organisation

Das Modell bietet keine erschöpfende Liste der beleidigenden Sprache. Außerdem ändern sich die Sprach-und Kulturstandards ständig, und in Anbetracht dieser Gegebenheiten behält sich Microsoft das Recht vor, das Modell nach eigenem Ermessen zu aktualisieren. Das Modell unterstützt Ihre Organisation möglicherweise bei der Überwachung anstößiger Sprache, aber das Modell ist nicht dazu gedacht, die einzige Möglichkeit zu bieten, diese Sprache zu überwachen oder zu adressieren. Ihre Organisation, nicht Microsoft, bleibt für alle Entscheidungen im Zusammenhang mit der Überwachung und Sperrung anstößiger Sprachen verantwortlich.

Das Offensive Sprachmodell überwacht e-Mails nach dem Sentiment, das den folgenden Sprachtypen zugeordnet ist:

|**Type**|**Beschreibung**|
|:-----|:-----|
| **Weltlichkeiten** | Ausdrücke, die die meisten Menschen in Verlegenheit bringen. |
| **Bögen** | Ausdrücke, die Vorurteile gegenüber bestimmten Gruppen (beispielsweise Rasse, ethnische Zugehörigkeit, sexuelle Orientierung, Behinderung) Ausdrücken. |
| **Sticheleien** | Ausdrücke, die verspotten, verurteilen, lächerlich machen oder potenziell Wut oder Gewalt verursachen könnten. |
| **Getarnte Ausdrücke** | Ausdrücke, für die die Bedeutung oder Aussprache identisch mit einem anderen beleidigenden Begriff ist. |

#### <a name="conditional-settings"></a>Bedingte Einstellungen
<a name="ConditionalSettings"> </a>

Die Bedingungen, die Sie für die Richtlinie wählen, gelten für die Kommunikation sowohl von e-Mails als auch von Drittanbieterquellen in Ihrer Organisation (wie Facebook oder Dropbox).

In der folgenden Tabelle werden die einzelnen Bedingungen näher erläutert.
  
|**Bedingung**|**Verwendung**|
|:-----|:-----|
| **Nachricht wird von einer dieser Domänen empfangen** <br><br> **Nachricht wird von keiner dieser Domänen empfangen** | Wenden Sie die Richtlinie an, um bestimmte Domänen oder e-Mail-Adressen in empfangene Nachrichten einzubeziehen oder auszuschließen. Geben Sie jede Domäne oder e-Mail-Adresse ein, und trennen Sie mehrere Domänen oder e-Mail-Adressen durch ein Komma. Jede eingegebene Domäne oder e-Mail-Adresse wird separat angewendet, nur eine Domäne oder e-Mail-Adresse muss für die Richtlinie gelten, die auf die Nachricht angewendet werden soll. <br><br> Wenn Sie alle e-Mails von einer bestimmten Domäne überwachen, aber Nachrichten ausschließen möchten, die keine Überprüfung (Newsletter, Ankündigungen usw.) benötigen, müssen Sie die Bedingung konfigurieren, dass eine **Nachricht nicht von einer dieser Domänen Bedingungen empfangen wird** , die die e-Mail-Adresse ausschließt (Beispiel "Newsletter@contoso.com"). |
| **Nachricht wird an eine dieser Domänen gesendet.** <br><br> **Nachricht wird nicht an eine dieser Domänen gesendet** | Wenden Sie die Richtlinie an, um bestimmte Domänen oder e-Mail-Adressen in gesendete Nachrichten einzuschließen oder auszuschließen. Geben Sie jede Domäne oder e-Mail-Adresse ein, und trennen Sie mehrere Domänen oder e-Mail-Adressen durch ein Komma. Jede Domäne oder e-Mail-Adresse wird separat angewendet, nur eine Domäne oder e-Mail-Adresse muss für die Richtlinie gelten, die auf die Nachricht angewendet werden soll. <br><br> Wenn Sie alle an eine bestimmte Domäne gesendeten e-Mails überwachen möchten, jedoch gesendete Nachrichten ausschließen möchten, die nicht überprüft werden müssen, müssen Sie zwei Bedingungen konfigurieren: <br> -Eine **Nachricht wird an eine dieser Domänen Bedingungen gesendet** , die die Domäne definiert ("contoso.com") und <br> -Eine **Nachricht wird nicht an eine dieser Domänen Bedingungen gesendet** , die die e-Mail-Adresse ("Subscriptions@contoso.com") ausschließen. |
| **Nachricht wird mit einer dieser Bezeichnungen klassifiziert.** <br><br> **Nachricht ist nicht mit einer dieser Bezeichnungen klassifiziert** | So wenden Sie die Richtlinie an, wenn bestimmte Aufbewahrungs Bezeichnungen in einer Nachricht enthalten oder ausgeschlossen werden. Aufbewahrungs Bezeichnungen müssen separat konfiguriert werden, und die konfigurierten Beschriftungen werden als Teil dieser Bedingung ausgewählt. Jede ausgewählte Bezeichnung wird separat angewendet (nur eine dieser Bezeichnungen muss für die Richtlinie gelten, die auf die Nachricht angewendet wird). Weitere Informationen zu Aufbewahrungs Bezeichnungen finden Sie unter Informationen [zu Aufbewahrungsrichtlinien und Aufbewahrungs Bezeichnungen](retention.md).|
| **Nachricht enthält eines dieser Wörter** <br><br> **Nachricht enthält keines dieser Wörter** | Um die Richtlinie anzuwenden, wenn bestimmte Wörter oder Ausdrücke in einer Nachricht enthalten oder ausgeschlossen werden, geben Sie jedes Wort oder jede Phrase ein, und trennen Sie Sie durch ein Komma. Jedes Wort, das Sie eingeben, wird separat angewendet (es muss nur ein Wort für die Richtlinie gelten, die auf die Nachricht angewendet wird). Weitere Informationen zum Eingeben von Wörtern oder Ausdrücken finden Sie im nächsten Abschnitt [Matching words and phrases to emails or attachments](supervision-policies.md#Matchwords).|
| **Attachment enthält eines dieser Wörter** <br><br> **Attachment enthält keines dieser Wörter** | Wenn Sie die Richtlinie anwenden möchten, wenn bestimmte Wörter oder Ausdrücke in einer Nachrichtenanlage eingeschlossen oder ausgeschlossen werden (beispielsweise in einem Word-Dokument), geben Sie jedes Wort oder jede Phrase ein, und trennen Sie Sie durch ein Komma. Jedes Wort, das Sie eingeben, wird separat angewendet (nur ein Wort muss gelten, damit die Richtlinie auf die Anlage angewendet wird). Weitere Informationen zum Eingeben von Wörtern oder Ausdrücken finden Sie im nächsten Abschnitt [Matching words and phrases to emails or attachments](supervision-policies.md#Matchwords).|
| **Attachment ist einer der folgenden Dateitypen** <br><br> **Attachment ist keiner dieser Dateitypen** | Geben Sie die Dateierweiterungen ein (beispielsweise. exe oder. pdf), um die Kommunikation zu überwachen, die bestimmte Anlagentypen einschließen oder ausschließen. Wenn Sie mehrere Dateierweiterungen einschließen oder ausschließen möchten, geben Sie diese in separaten Zeilen ein. Nur eine Anlagenerweiterung muss übereinstimmen, damit die Richtlinie angewendet wird.|
| **Nachricht ist größer als** <br><br> **Die Nachrichtengröße ist nicht größer als** | Zum Überprüfen von Nachrichten, die auf einer bestimmten Größe basieren, verwenden Sie diese Bedingungen, um die maximale oder minimale Größe einer Nachricht anzugeben, bevor Sie überprüft werden kann. Wenn Sie beispielsweise angeben, dass die **Nachrichtengröße größer als** \> **1,0 MB**ist, werden alle Nachrichten mit einer Größe von 1,01 MB überprüft. Sie können Byte, Kilobyte, Megabyte oder Gigabyte für diese Bedingung auswählen.|
| **Anlage ist größer als** <br><br> **Die Anlage ist nicht größer als** | Um Nachrichten anhand der Größe Ihrer Anlagen zu überprüfen, geben Sie die maximale oder minimale Größe an, die eine Anlage sein kann, bevor die Nachricht und ihre Anlagen überprüft werden können. Wenn Sie beispielsweise **Attachment größer als** \> **2,0 MB**angeben, werden alle Nachrichten mit Anlagen von 2,01 MB und mehr überprüft. Sie können Byte, Kilobyte, Megabyte oder Gigabyte für diese Bedingung auswählen.|
   
##### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>Übereinstimmende Wörter und Ausdrücke in E-Mails oder Anlagen
<a name="Matchwords"> </a> Jedes Wort, das Sie eingeben und mit einem Komma trennen, wird separat angewendet (nur ein Wort muss gelten, damit die Richtlinienbedingung auf die e-Mail oder Anlage angewendet wird). Verwenden wir beispielsweise die Bedingung, **Nachricht enthält eines dieser Wörter**, wobei die Schlüsselwörter "Banker" und "Insiderhandel" durch ein Komma getrennt sind (Banker, Insiderhandel). Die Richtlinie gilt für alle Nachrichten, die das Wort "Banker" oder den Ausdruck "Insiderhandel" enthalten. Nur eins der Wörter oder einer der Ausdrücke muss vorkommen, damit die Richtlinienbedingung zutrifft. Wörter in der Nachricht oder Anlage müssen genau übereinstimmen, die Sie eingeben.

Um sowohl e-Mail-Nachrichten als auch Anlagen für dieselben Stichwörter zu überprüfen, erstellen Sie eine [Richtlinie zur Verhinderung von Datenverlust](create-test-tune-dlp-policy.md) mit einem [benutzerdefinierten Stichwort Wörterbuch](create-a-keyword-dictionary.md) für die zu überwachenden Ausdrücke. Diese Richtlinienkonfiguration identifiziert definierte Schlüsselwörter, die entweder in der e-Mail-Nachricht **oder** in der e-Mail-Anlage angezeigt werden. Unter Verwendung der standardmäßigen bedingten Richtlinieneinstellungen (*Nachricht enthält* eines dieser Wörter und *Anlage enthält*eines dieser Wörter) zum Identifizieren von Ausdrücken in Nachrichten und in Anlagen erfordert die Begriffe sind **sowohl** in der Nachricht als auch in der Anlage vorhanden.
  
##### <a name="enter-multiple-conditions"></a>Eingeben mehrerer Bedingungen

Wenn Sie mehrere Bedingungen eingeben, verwendet Microsoft 365 alle Bedingungen zusammen, um zu bestimmen, wann die Richtlinie auf Kommunikationselemente angewendet werden soll. Wenn Sie mehrere Bedingungen einrichten, müssen alle Bedingungen erfüllt sein, damit die Richtlinie angewendet werden kann, es sei denn, Sie geben eine Ausnahme ein. Sie benötigen beispielsweise eine Richtlinie, die gilt, wenn eine Nachricht das Wort "Trade" enthält und größer als 2 MB ist. Wenn die Nachricht jedoch auch die Wörter "von Contoso Financial genehmigt" enthält, sollte die Richtlinie nicht angewendet werden. In diesem Fall wären also die folgenden drei Bedingungen erfüllt:
  
- **Nachricht enthält eines dieser Wörter**mit dem Stichwort "Trade"

- Die **Nachrichtengröße ist größer als**, mit dem Wert 2 MB

- **Nachricht enthält keines dieser Wörter**, mit den Schlüsselwörtern "genehmigt von Contoso Financial Team"

#### <a name="review-percentage"></a>Überprüfen des Prozentsatzes

Wenn Sie den Umfang der zu überprüfenden Inhalte reduzieren möchten, können Sie einen Prozentsatz aller Kommunikationen angeben, die unter eine Überwachungsrichtlinie fallen. Eine zufällige Stichprobe von Inhalten wird in Echtzeit aus dem Gesamtprozentsatz der Inhalte ausgewählt, die den gewählten Richtlinienbedingungen entsprechen. Wenn Bearbeiter alle Elemente überprüfen möchten, können Sie in einer Aufsichtsrichtlinie **100%** eingeben.

## <a name="monitor--manage"></a>Überwachen der & verwalten

Es ist einfach, die Ergebnisse ihrer Aufsichtsrichtlinien zu überwachen und ein Auflösungs-Tag anzuwenden. Sie können schnell sehen:

- Der Status der überprüften Elemente
- Benutzer und Gruppen unter Aufsicht
- Als Bearbeiter bezeichnete Benutzer und Gruppen

### <a name="supervision-policy-dashboard"></a>Aufsichtsrichtlinien-Dashboard

Verwenden Sie das Dashboard für Aufsichtsrichtlinien, um Aufsichtsrichtlinien Ergebnisse zu verwalten und ausstehende Elemente aufzulösen. In diesem Dashboard können Bearbeiter Elemente anzeigen, die überprüft werden müssen, auf ein Element reagieren und die Ergebnisse der zuvor geprüften und aufgelösten Elemente für jede Aufsichtsrichtlinie überprüfen. Sie können auf das Dashboard für Aufsichtsrichtlinien im Compliance Center unter **beaufsichtigen**der  >  *benutzerdefinierten Richt*Linie  >  **Öffnen**zugreifen.

#### <a name="dashboard-home"></a>Dashboard-Startseite

Die Dashboard- **Start** Seite verfügt über mehrere Abschnitte, die Ihnen helfen, ihre Aufsichtsrichtlinien schnell zu bearbeiten. Hier haben Sie folgende Möglichkeiten:

- Schnelles Überprüfen der ausstehenden und aufgelösten Highlights für die Woche
- Anzeigen einer Liste der überwachten Benutzer und der überwachten Gruppen für die ausgewählte Richtlinie
- Anzeigen einer Liste der Bearbeiter und Überprüfungsteams für die ausgewählte Richtlinie
- Anzeigen der Kommunikationsplattformen für die Richtlinie unter Aufsicht über Inhalte

#### <a name="review-tab"></a>Registerkarte "überprüfen"

Auf der Registerkarte " **überprüfen** " werden die von der ausgewählten Richtlinie identifizierten Elemente klassifiziert und aufgelöst. Hier haben Sie folgende Möglichkeiten:

- Filtern nach ausstehenden, kompatiblen, nicht kompatiblen und fragwürdigen Elementen.
- Kennzeichnen eines einzelnen Elements als konform, nicht kompatibel oder fragwürdig. Sie können auch einen Kommentar mit dem Element aufzeichnen, um die getroffene Markierungs Aktion zu verdeutlichen.
- Massen Markierung mehrerer Elemente als konform, nicht kompatibel oder fragwürdig. Sie können auch einen Kommentar mit mehreren Elementen aufzeichnen, um eine Erläuterung der ausgeführten Markierungs Aktion zu ermöglichen.
- Zeigt den Verlauf der Kennzeichnung für ein einzelnes Element an. Enthält, wer das Element aufgelöst hat, das Datum und die Uhrzeit der Aktion, das Auflösungs und alle eingeschlossenen Kommentare.
- Erneutes Klassifizieren zuvor geprüfter Elemente als konform, nicht kompatibel oder fragwürdig. Sie können auch einen Kommentar mit einem oder mehreren Elementen aufzeichnen, um die vorgenommene umklassifizierungs Aktion zu verdeutlichen.

#### <a name="resolved-items-tab"></a>Registerkarte "aufgelöste Elemente"

Auf der Registerkarte **aufgelöste Elemente** können Bearbeiter alle zuvor aufgelösten Elemente für die ausgewählte Richtlinie anzeigen. Hier haben Sie folgende Möglichkeiten:

- Schnelles anzeigen und Sortieren des Betreffs, des Absenders und des Datums von aufgelösten Elementen
- Anzeigen der Klassifizierung und des Kommentar Verlaufs eines beliebigen ausgewählten Elements

## <a name="reports"></a>Berichte

Verwenden Sie die Überwachungsberichte, um die Überprüfungsaktivität auf der Ebene Richtlinie und Prüfer anzuzeigen. Für jede Richtlinie können Sie auch Live Statistiken zum aktuellen Status der Überprüfungsaktivität anzeigen. Sie können die Überwachungsberichte für folgende Zwecke verwenden:
  
- Stellen Sie sicher, dass Ihre Richtlinien ordnungsgemäß funktionieren.
- Erfahren Sie, wie viele Kommunikationsanforderungen überprüft werden müssen.
- Finden Sie heraus, wie viele Kommunikationen nicht konform sind und welche die Überprüfung übergeben. Anhand dieser Informationen können Sie entscheiden, ob Sie Ihre Richtlinien optimieren oder die Anzahl der Bearbeiter ändern möchten.

### <a name="view-the-supervision-report"></a>Anzeigen des Aufsichts Berichts

1. Melden Sie sich beim [Compliance Center](https://compliance.microsoft.com) mit Anmeldeinformationen für ein Administratorkonto mit Berechtigungen zum Anzeigen von Aufsichtsberichten an.
2. Wechseln Sie zu **Berichts** \> **Dashboard** oder **Überwachung** , um das Widget für die Beaufsichtigung von Berichten für eine Zusammenfassung der aktuellen Aufsichtsrichtlinien Aktivitäten anzuzeigen.
3. Wählen Sie das **Aufsichts** widget aus, um die Seite detaillierter Bericht zu öffnen.

>[!NOTE]
>Wenn Sie nicht auf die Seite **Berichte** zugreifen können, überprüfen Sie, dass Sie ein Mitglied der Rollengruppe aufsichtsüberprüfung sind, wie unter [machen Sie die Überwachung in Ihrer Organisation verfügbar](configure-supervision-policies.md)beschrieben. Mit der Aufnahme in diese Rollengruppe können Sie Aufsichtsrichtlinien erstellen und verwalten und den Bericht ausführen.
  
### <a name="how-to-use-the-report"></a>Verwenden des Berichts

In diesem Bericht werden die einzelnen Richtlinien und die Anzahl der Kommunikationen in jeder Phase des Überprüfungsprozesses aufgelistet. Verwenden Sie den Bericht, um Folgendes zu tun:
  
- Anzeigen von Daten für alle oder bestimmte Richtlinien.
- Anzeigen von Daten, die nach Tag-Typ, Prüfer oder Nachrichtentyp gruppiert sind.
- Exportieren Sie Daten basierend auf dem Aktivitätsdatum, der Richtlinie und den Prüfer Aktivitäten in eine CSV-Datei.
- Filtern von Daten basierend auf dem Aktivitätsdatum, dem Tag-Typ, dem Prüfer und dem Nachrichtentyp.

Im folgenden finden Sie eine Aufschlüsselung der Werte, die in der Spalte **Tag Type** angezeigt werden.
  
|**Tagtyp**|**Bedeutung**|
|:-----|:-----|
| **Nicht überprüft** | Die Anzahl der e-Mails, die noch nicht überprüft wurden. Diese e-Mails warten auf die Überprüfung im Microsoft 365-Aufsichts Dashboard.
| **Compliant** | Die Anzahl der überprüften und als konform gekennzeichneten e-Mails. Diese Nachrichten benötigen noch eine Lösung. |
| **Fragwürdig** | Die Anzahl der überprüften und fragwürdig markierten e-Mails. Dient als Kennzeichnung anderer Bearbeiter, um zu überprüfen, ob eine e-Mail-Konformität untersucht werden muss. Diese Nachrichten benötigen noch eine Lösung. |
| **Nicht kompatibel (aktiv)** | Die Anzahl der nicht kompatiblen e-Mails, die von den Prüfern derzeit untersucht werden. |
| **Nicht kompatibel (aufgelöst)** | Die Anzahl der nicht kompatiblen e-Mails, die von den Prüfern untersucht und aufgelöst wurden. |
| **Treffer Richtlinie** | Die Gesamtzahl (täglich) von Nachrichten von Exchange, Microsoft Teams und Drittanbieter-Datenquellen, die einer oder mehreren in einer Aufsichtsrichtlinie definierten Bedingungen entsprechen. |
| **In Zuständigkeitsbereich** | Die Gesamtzahl (täglich) von Nachrichten von Exchange, von Teams und von Drittanbieter-Datenquellen, die von einer Aufsichtsrichtlinie überprüft wurden. |
| **Resolved** | Die Gesamtzahl der Nachrichten von Exchange, Microsoft Teams und Drittanbieter-Datenquellen, die als **aufgelöst** klassifiziert wurden.|

>[!NOTE]
>Aufsichtsrichtlinien müssen vor der Anzeige in Berichten eingerichtet werden. Wenn Richtlinien gelöscht werden, werden Verlaufsdaten weiterhin angezeigt. Sie werden jedoch als "nicht vorhandene Richtlinie" angezeigt, und die **Export** Funktion ist nicht verfügbar.

## <a name="audit"></a>Überwachung

In einigen Fällen müssen Sie Aufsichtsbehörden oder Compliance-Prüfern Informationen bereitstellen, um die Überwachung der Aktivitäten und der Kommunikation von Mitarbeitern nachzuweisen. Diese Informationen können eine Zusammenfassung aller Aufsichtsaktivitäten sein, die einer definierten Richtlinie zugeordnet sind, oder wenn sich eine Aufsichtsrichtlinie ändert. Aufsichtsrichtlinien verfügen über integrierte Überwachungspfade für die vollständige Bereitstellung interner oder externer Überprüfungen. Detaillierte Überwachungs Verläufe jeder durch ihre Aufsichtsrichtlinien überwachten Aktion bieten einen Nachweis über Aufsichtsverfahren.

Zeigen Sie Überwachungsaktivitäten im einheitlichen Überwachungsprotokoll oder mit dem PowerShell [-Cmdlet Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) an.

Im folgenden Beispiel werden die Aktivitäten für alle Aufsichts Überprüfungsaktivitäten (Richtlinien und Regeln) zurückgegeben, und es werden detaillierte Informationen zu den einzelnen Vorgängen aufgelistet:

```PowerShell
Search-UnifiedAuditLog -StartDate 3/1/2019 -EndDate ([System.DateTime]::Now) -RecordType DataGovernance -ResultSize 5000 | Where-Object {$_.Operations -like "*SupervisoryReview*"}  | fl CreationDate,Operations,UserIds,AuditData
```

In diesem Beispiel werden die Updateaktivitäten für Ihre Richtlinien für die Kommunikations Konformität zurückgegeben:

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -Operations SupervisionPolicyCreated,SupervisionPolicyUpdated,SupervisionPolicyDeletedAuditData
```

Zusätzlich zu den in den Überwachungsberichten und-Protokollen bereitgestellten Informationen können Sie auch das Cmdlet [Get-SupervisoryReviewActivity](https://docs.microsoft.com/powershell/module/exchange/get-supervisoryreviewactivity) PowerShell verwenden, um eine vollständige detaillierte Auflistung aller Aufsichtsrichtlinien Aktivitäten zurückzugeben.

## <a name="ready-to-get-started"></a>Sind Sie bereit loszulegen?

Informationen zum Konfigurieren von Aufsichtsrichtlinien für Ihre Organisation finden Sie unter [configure Supervision Policies](configure-supervision-policies.md).
