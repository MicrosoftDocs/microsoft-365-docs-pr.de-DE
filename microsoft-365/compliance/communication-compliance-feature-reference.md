---
title: Referenz zur Kommunikation Compliance-Feature
description: Funktionsreferenz für die Kommunikations Kompatibilität in Microsoft 365. Hier finden Sie Details und Spezifikationen für die einzelnen Feature-Komponenten.
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
ms.openlocfilehash: 25f69491156d7862d9dc145123ec158a3ff40556
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634187"
---
# <a name="communication-compliance-feature-reference"></a>Referenz zur Kommunikation Compliance-Feature

## <a name="policies"></a>Richtlinien

>[!Important]
>Die Verwendung von PowerShell zum Erstellen und Verwalten von Kommunikations Konformitätsrichtlinien wird nicht unterstützt. Zum Erstellen und Verwalten dieser Richtlinien müssen Sie die Steuerelemente für die Richtlinienverwaltung in der [Microsoft 365 Communication Compliance-Lösung](https://compliance.microsoft.com/supervisoryreview)verwenden.

Sie erstellen Kommunikationsrichtlinien für Microsoft 365-Organisationen im Microsoft 365 Compliance Center. Wenn Sie über eine Microsoft 365-Organisation verfügen, [Konfigurieren Sie Aufsichtsrichtlinien](configure-supervision-policies.md) im Security & Compliance Center. Compliance-Richtlinien für Kommunikation definieren, welche Kommunikation und welche Benutzer in Ihrer Organisation überprüft werden sollen, definieren, welche benutzerdefinierten Bedingungen die Kommunikation erfüllen muss, und angeben, wer Überprüfungen durchführen soll. Benutzer, die in der Rollengruppe **aufsichtsüberprüfung-Administrator** enthalten sind, können Richtlinien einrichten, und jeder, dem diese Rolle zugewiesen ist, kann auf die Seite **Kommunikations Kompatibilität** im Microsoft 365 Compliance Center zugreifen. Bei Bedarf können Sie den Verlauf von Änderungen an einer Richtlinie in eine CSV-Datei exportieren, die auch den Status der ausstehenden Warnungen, eskalierter Elemente und aufgelöster Elemente enthält. Richtlinien können nicht umbenannt werden und können gelöscht werden, wenn Sie nicht mehr benötigt werden.

>[!NOTE]
>Aufsichtsrichtlinien, die im Security & Compliance Center für Office 365-Abonnements erstellt wurden, können nicht zu Microsoft 365 migriert werden. Wenn Sie von einem Office 365-Abonnement zu einem Microsoft 365-Abonnement migrieren, müssen Sie neue Richtlinien für die Kommunikationsrichtlinien Erstellung erstellen, um vorhandene Aufsichtsrichtlinien zu ersetzen.

## <a name="policy-templates"></a>Richtlinienvorlagen

Richtlinienvorlagen sind vordefinierte Richtlinieneinstellungen, mit denen Sie schnell Richtlinien erstellen können, um allgemeine Kompatibilitätsszenarien zu behandeln. Jede dieser Vorlagen weist Unterschiede bei Bedingungen und Umfang auf, und alle Vorlagen verwenden dieselben Arten von Scan Signalen. Sie können aus den folgenden Richtlinienvorlagen auswählen:

|**Bereich**|**Richtlinienvorlage**|**Details**|
|:-----|:-----|:-----|
| **Anstößige Sprache und Anti-Belästigung** | Überwachen der Kommunikation für anstößige Sprache | -Standorte: Exchange, Teams, Skype for Business <br> -Direction: eingehend, ausgehende, intern <br> -Review-Prozentsatz: 100% <br> -Bedingungen: anstößige sprach Klassifizierung |
| **Vertrauliche Informationen** | Überwachen der Kommunikation für vertrauliche Informationen | -Standorte: Exchange, Teams, Skype for Business <br> -Direction: eingehend, ausgehende, intern <br> -Review-Prozentsatz: 10% <br> -Bedingungen: vertrauliche Informationen, vordefinierte Inhalts Muster und-Typen, benutzerdefinierte wörterbuchoption, Anlagen größer als 1 MB |
| **Einhaltung von Vorschriften** | Überwachen der Kommunikation für Informationen im Zusammenhang mit der finanzbehördlichen Compliance | -Standorte: Exchange, Teams, Skype for Business <br> -Direction: eingehend, Outbound <br> -Review-Prozentsatz: 10% <br> -Bedingungen: Benutzerwörterbuch-Option, Anlagen größer als 1 MB |

## <a name="supervised-users"></a>Beaufsichtigte Benutzer

Bevor Sie mit der Verwendung der Kommunikations Konformität beginnen, müssen Sie ermitteln, wer Ihre Kommunikationen überprüfen muss. In der Richtlinie identifizieren Benutzer-e-Mail-Adressen einzelne Personen oder Gruppen von Personen, die überwacht werden sollen. Einige Beispiele für diese Gruppen sind Microsoft 365-Gruppen, Exchange-basierte Verteilerlisten und Microsoft Teams-Kanäle. Sie können auch bestimmte Benutzer oder Gruppen von der Überprüfung mit einer bestimmten Ausschlussgruppe oder einer Liste von Gruppen ausschließen.

>[!IMPORTANT]
>Für Benutzer, die von Kommunikationsrichtlinien Richtlinien abgedeckt werden, muss entweder eine Microsoft 365 E5-Konformitäts Lizenz, eine Office 365 Enterprise E3-Lizenz mit dem Add-on für die erweiterte Kompatibilität oder ein Office 365 Enterprise E5-Abonnement enthalten sein. Wenn Sie über keinen vorhandenen Enterprise E5-Plan verfügen und die Kommunikations Kompatibilität testen möchten, können Sie [sich für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279).

## <a name="reviewers"></a>Prüfer

Wenn Sie eine Kommunikations Konformitätsrichtlinie erstellen, müssen Sie ermitteln, wer die Nachrichten der überwachten Benutzer überprüft. In der Richtlinie identifizieren Benutzer e-Mail-Adressen einzelne Personen oder Gruppen von Personen, um die beaufsichtigte Kommunikation zu überprüfen. Alle Bearbeiter müssen über Postfächer verfügen, die auf Exchange Online gehostet werden und der **Fall Verwaltungs** -und **Überprüfungs** Rolle zugewiesen werden müssen.

## <a name="groups-for-supervised-users-and-reviewers"></a>Gruppen für beaufsichtigte Benutzer und Bearbeiter

Um Ihr Setup zu vereinfachen, erstellen Sie Gruppen für Personen, die Ihre Kommunikation überprüfen müssen, sowie Gruppen für Personen, die diese Kommunikationen überprüfen. Wenn Sie Gruppen verwenden, benötigen Sie möglicherweise mehrere. Wenn Sie beispielsweise die Kommunikation zwischen zwei unterschiedlichen Personengruppen überprüfen möchten oder wenn Sie eine Gruppe angeben möchten, die nicht überwacht wird.

Wenn Sie eine Microsoft 365-Gruppe für beaufsichtigte Benutzer auswählen, überprüft die Richtlinie den Inhalt des freigegebenen Postfachs und der Microsoft Teams-Kanäle, die der Gruppe zugeordnet sind. Wenn Sie eine Verteilerliste auswählen, scannt die Richtlinie einzelne Benutzerpostfächer.

## <a name="supported-communication-types"></a>Unterstützte Kommunikationstypen

Mit Richtlinien für die Kommunikations Konformität können Sie auswählen, ob Nachrichten in einer oder mehreren der folgenden Kommunikationsplattformen als Gruppe oder als eigenständige Quellen überprüft werden sollen. Auf diesen Plattformen erfasste Kommunikationen werden für jede Richtlinie standardmäßig sieben Jahre lang aufbewahrt, selbst wenn Benutzer Ihre Organisation verlassen und ihre Postfächer gelöscht werden.

- **Microsoft Teams**: Chat Kommunikation und zugehörige Anlagen in öffentlichen und privaten Microsoft Teams-Kanälen und einzelne Chats können gescannt werden. Microsoft Teams-Chats und-Anlagen, die Richtlinienbedingungen für die Kommunikation erfüllen, können bis zu 24 Stunden verarbeiten. Verwenden Sie die folgenden Gruppen Verwaltungs Konfigurationen, um einzelne Benutzer Chats und Kanal Kommunikationen in Microsoft Teams zu überwachen:

    - **Für Chatnachrichten in Microsoft Teams:** Zuweisen einzelner Benutzer oder Zuweisen einer [Verteilergruppe](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) zur Kommunikations Konformitätsrichtlinie. Diese Einstellung gilt für 1:1-oder 1: n-Benutzer-/-Chat-Beziehungen.
    - **Für Teams-Kanal Kommunikation:** Weisen Sie alle Microsoft Team Channel-oder Microsoft 365-Gruppen zu, die Sie überprüfen möchten, die einen bestimmten Benutzer für die Kommunikations Konformitätsrichtlinie enthalten. Wenn Sie denselben Benutzer zu anderen Microsoft Teams-Kanälen oder Microsoft 365-Gruppen hinzufügen, müssen Sie diese neuen Kanäle und Gruppen der Kommunikations Konformitätsrichtlinie hinzufügen.

- **Exchange-e-Mail**: Postfächer, die auf Exchange Online als Teil Ihres Microsoft 365-oder Office 365-Abonnements gehostet werden, sind alle für die Nachrichtenüberprüfung berechtigt. Exchange-e-Mail-Nachrichten und Anlagen, die Richtlinienbedingungen für die Kommunikation erfüllen, können bis zu 24 Stunden verarbeiten. Unterstützte Anlagentypen für die Kommunikations Kompatibilität sind identisch mit den [für Exchange-Nachrichtenfluss Regel-Inhalts Prüfungen unterstützten Dateitypen](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection).

- **Skype for Business Online**: Chat Kommunikation und zugehörige Anlagen in Skype for Business Online können überwacht werden. Skype for Business Online Chats, die Richtlinienbedingungen für die Kommunikation erfüllen, können bis zu 24 Stunden verarbeiten. Überwachte Chat Unterhaltungen werden aus [früheren Unterhaltungen, die in Skype for Business Online gespeichert](https://support.office.com/article/Find-a-previous-Skype-for-Business-conversation-18892eba-5f18-4281-8c87-fd48bd72e6a2)wurden, bezogen.  Verwenden Sie die folgende Gruppen Verwaltungskonfiguration, um die Benutzer Chat Kommunikation in Skype for Business Online zu überwachen:

    - **Für Skype for Business Online Chat Kommunikation**: zuweisen einzelner Benutzer oder Zuweisen einer [Verteilergruppe](https://support.office.com/article/Distribution-groups-E8BA58A8-FAB2-4AAF-8AA1-2A304052D2DE) zur Kommunikations Konformitätsrichtlinie. Diese Einstellung gilt für 1:1-oder 1: n-Benutzer-/-Chat-Beziehungen.

- **Drittanbieterquellen**: Sie können die Kommunikation von Drittanbieterquellen für Daten, die in Postfächer in Ihrer Microsoft 365-Organisation importiert werden, überprüfen. Connectors unterstützen die folgenden Drittanbieterressourcen:

    - [Instant Bloomberg](archive-instant-bloomberg-data.md)
    - [Facebook](archive-facebook-data-with-sample-connector.md)
    - [LinkedIn](archive-linkedin-data.md)
    - SAP-SuccessFactors
    - [Twitter](archive-twitter-data-with-sample-connector.md)
    - [Benutzerdefinierter Daten-Konnektor](archiving-third-party-data.md)

Sie müssen einen Drittanbieter-Connector für Ihre Microsoft 365-Organisation konfigurieren, bevor Sie den Connector einer Kommunikations Konformitätsrichtlinie zuweisen können. Im Abschnitt " **Drittanbieterquellen** " des Assistenten für die Kommunikation mit Kompatibilitätsrichtlinien werden derzeit konfigurierte Connectors von Drittanbietern angezeigt.

## <a name="transitioning-from-supervision-in-office-365"></a>Übergang von der Aufsicht in Office 365

Organisationen, die Aufsichtsrichtlinien in Office 365 verwenden und den Übergang zu Kommunikationsrichtlinien in Microsoft 365 planen, müssen diese wichtigen Punkte verstehen:

- Beide Lösungen können nebeneinander in Ihrer Organisation verwendet werden, aber Richtlinien, die in jeder Lösung verwendet werden, müssen eindeutige Richtliniennamen aufweisen. Gruppen und benutzerdefinierte Schlüsselwörter Wörterbücher können während eines Übergangszeitraums Zwischenlösungen freigegeben werden.
- Nachrichten, die in Office 365 Richtlinien Übereinstimmungen gespeichert wurden, können nicht in der Kommunikations Kompatibilität in Microsoft 365 verschoben oder freigegeben werden.
- Die Überwachungslösung in Office 365 wird vollständig durch die Kommunikations kompatibilitätslösung in Microsoft 365 ersetzt. Es wird empfohlen, neue Richtlinien in der Kommunikations Kompatibilität zu erstellen, die die gleichen Einstellungen wie die vorhandenen Aufsichtsrichtlinien aufweisen, um die neuen Untersuchungen und Korrektur Verbesserungen zu verwenden. Beim Übergang zur Kommunikations Kompatibilität in Microsoft 365 sollten Sie planen, Berichtsdaten aus der Beaufsichtigung in Office 365 zu exportieren, wenn Sie über interne Compliance-Aufbewahrungsrichtlinien Anforderungen verfügen.

Informationen zur Beaufsichtigung in Office 365 finden Sie im [Microsoft 365-Fahrplan](https://www.microsoft.com/microsoft-365/roadmap) für Vorsorge Informationen.

## <a name="policy-settings"></a>Richtlinieneinstellungen

### <a name="users"></a>Benutzer

Sie haben die Möglichkeit, **alle Benutzer** auszuwählen oder bestimmte Benutzer in einer Kommunikations Konformitätsrichtlinie zu definieren. Wenn Sie **alle Benutzer** auswählen, wird die Richtlinie auf alle Benutzer und alle Gruppen angewendet, in denen ein beliebiger Benutzer als Mitglied enthalten ist. Durch das Definieren bestimmter Benutzer wird die Richtlinie auf die definierten Benutzer und alle Gruppen angewendet, in denen die definierten Benutzer als Mitglied enthalten sind.

### <a name="direction"></a>Direction

Standardmäßig wird die Bedingung " **Direction** " angezeigt und kann nicht entfernt werden. Die Einstellungen für die Kommunikationsrichtung in einer Richtlinie werden einzeln oder gemeinsam ausgewählt:

- **Eingehend**: Sie können " **eingehend** " auswählen, um die Kommunikation zu überprüfen **, die an** die Personen gesendet wird, die Sie überwachen möchten.
- Ausgehend **: Sie**können ausgehend **wählen,** Wenn Sie die Kommunikationen überprüfen möchten, die **von** den Personen gesendet wurden, die Sie überwachen wollten.
- **Intern**: Sie können **interne** auswählen, um die Kommunikation zu überprüfen, die **zwischen** den Personen gesendet wird, die Sie in der Richtlinie angegeben haben.

### <a name="sensitive-information-types"></a>Typen vertraulicher Informationen

Sie haben die Möglichkeit, vertrauliche Informationstypen als Teil ihrer Kommunikations Konformitätsrichtlinie einzubinden. Vertrauliche Informationstypen sind entweder vordefinierte oder benutzerdefinierte Datentypen, die helfen, Kreditkartennummern, Bank Kontonummern, Passport-Nummern und vieles mehr zu identifizieren und zu schützen. Im Rahmen der [Verhinderung von Datenverlust (Data Loss Prevention, DLP)](data-loss-prevention-policies.md)können mit der Konfiguration vertraulicher Informationen Muster, Zeichen Nähe, Konfidenz Stufen und sogar benutzerdefinierte Datentypen verwendet werden, um Inhalte zu identifizieren und zu kennzeichnen, die möglicherweise vertraulich sind. Die Standardtypen für vertrauliche Informationen sind:

- Finanzwesen
- Medizin und Gesundheit
- Datenschutz
- Benutzerdefinierter Informationstyp

Weitere Informationen zu Details zu vertraulichen Informationen und zu den Mustern, die in den Standardtypen enthalten sind, finden Sie unter [welche Typen von vertraulichen Informationen suchen](what-the-sensitive-information-types-look-for.md).

### <a name="custom-keyword-dictionaries"></a>Benutzerdefinierte Schlüsselwörter Wörterbücher

Konfigurieren Sie benutzerdefinierte Keyword-Wörterbücher (oder Lexika), um eine einfache Verwaltung von Schlüsselwörtern für Ihre Organisation oder Industrie bereitzustellen. Stichwort Wörterbücher unterstützen bis zu 100.000 Begriffe pro Wörterbuch und unterstützen jede Sprache. Bei Bedarf können Sie mehrere benutzerdefinierte Schlüsselwörter Wörterbücher auf eine einzelne Richtlinie anwenden oder über ein einzelnes Schlüssel Wörterbuch pro Richtlinie verfügen. Diese Wörterbücher werden in einer Kommunikations Konformitätsrichtlinie zugewiesen und können aus einer Datei (wie einer CSV-oder txt-Liste) oder aus einer Liste stammen, [die Sie im Compliance Center importieren](create-a-keyword-dictionary.md)können. Verwenden Sie Benutzerwörterbücher, wenn Sie Ausdrücke oder Sprachen speziell für Ihre Organisation und ihre Richtlinien unterstützen müssen.

### <a name="classifiers"></a>Klassifizierungen

Integrierte Klassifizierungen überprüfen gesendete oder empfangene Nachrichten über alle Kommunikationskanäle in Ihrer Organisation für unterschiedliche Arten von Kompatibilitätsproblemen. Für Klassifizierungen wird eine Kombination aus künstlicher Intelligenz und Stichwörtern verwendet, um die Sprache in Nachrichten zu identifizieren, die gegen Belästigungs Richtlinien verstoßen könnten. Integrierte Klassifizierungen unterstützen derzeit nur englische Stichwörter in Nachrichten.

Kommunikation Compliance integrierte Klassifizierungen überprüfen die Kommunikation nach Ausdrücken und Gefühlen für die folgenden Sprachtypen:

- **Bedrohung**: scannt nach Bedrohungen, um Gewalt oder körperlichen Schaden für eine Person oder Eigenschaft zu begehen.
- **Belästigung**: Scans für anstößige Verhaltensweisen, die sich an Personen in Bezug auf Rasse, Farbe, Religion und nationale Herkunft ausrichten.
- **Profanität**: scannt nach profanen Ausdrücken, die die meisten Menschen in Verlegenheit bringen.

Die integrierten Klassifizierungen bieten keine erschöpfende Liste von Begriffen in diesen Bereichen. Außerdem ändern sich die Sprach-und Kulturstandards ständig, und in Anbetracht dieser Gegebenheiten behält sich Microsoft das Recht vor, die Klassifizierungen nach eigenem Ermessen zu aktualisieren. Während Klassifizierungen Ihre Organisation bei der Überwachung dieser Bereiche unterstützen können, sind Klassifizierungen nicht dazu gedacht, die einzige Möglichkeit zur Überwachung oder Adressierung dieser Sprache für Ihre Organisation bereitzustellen. Ihre Organisation, nicht Microsoft, bleibt für alle Entscheidungen im Zusammenhang mit dem Scannen und Blockieren von Sprache in diesen Bereichen verantwortlich.

Informationen zu Klassifizierungen in Microsoft 365 finden Sie unter [Klassifizierer](classifier-getting-started-with.md).

### <a name="conditional-settings"></a>Bedingte Einstellungen
<a name="ConditionalSettings"> </a>

Die Bedingungen, die Sie für die Richtlinie wählen, gelten für die Kommunikation sowohl von e-Mails als auch von Drittanbieterquellen in Ihrer Organisation (wie Facebook oder Dropbox).

In der folgenden Tabelle werden die einzelnen Bedingungen näher erläutert.
  
|**Bedingung**|**Verwendung**|
|:-----|:-----|
| **Inhalt entspricht einer dieser Klassifizierungen** | Auf die Richtlinie anwenden, wenn Klassifizierer in einer Nachricht eingeschlossen oder ausgeschlossen werden. Einige Klassifizierungen sind in Ihrem Mandanten vordefiniert, und benutzerdefinierte Klassifizierungen müssen separat konfiguriert werden, bevor Sie für diese Bedingung verfügbar sind. Nur eine Klassifizierung kann als Bedingung in einer Richtlinie definiert werden. Weitere Informationen zum Konfigurieren von Klassifizierungen finden Sie unter [Klassifizierer](classifier-getting-started-with.md). |
| **Inhalt enthält alle diese vertraulichen Info Typen** | Auf die Richtlinie anwenden, wenn vertrauliche Informationstypen in einer Nachricht enthalten oder ausgeschlossen werden. Einige Klassifizierungen sind in Ihrem Mandanten vordefiniert, und benutzerdefinierte Klassifizierungen können separat oder als Teil des Bedingungs Zuordnungsprozesses konfiguriert werden. Jeder vertrauliche Informationstyp, den Sie auswählen, wird separat angewendet, und nur einer dieser Typen für vertrauliche Informationen muss für die Richtlinie gelten, die auf die Nachricht angewendet werden soll. Weitere Informationen zu benutzerdefinierten vertraulichen Informationstypen finden Sie unter [benutzerdefinierte vertrauliche Informationstypen](custom-sensitive-info-types.md). |
| **Nachricht wird von einer dieser Domänen empfangen**  <br><br> **Nachricht wird von keiner dieser Domänen empfangen** | Wenden Sie die Richtlinie an, um bestimmte Domänen oder e-Mail-Adressen in empfangene Nachrichten einzubeziehen oder auszuschließen. Geben Sie jede Domäne oder e-Mail-Adresse ein, und trennen Sie mehrere Domänen oder e-Mail-Adressen durch ein Komma. Jede eingegebene Domäne oder e-Mail-Adresse wird separat angewendet, nur eine Domäne oder e-Mail-Adresse muss für die Richtlinie gelten, die auf die Nachricht angewendet werden soll. <br><br> Wenn Sie alle e-Mails von einer bestimmten Domäne überprüfen möchten, aber Nachrichten ausschließen möchten, die keine Überprüfung (Newsletter, Ankündigungen usw.) benötigen, müssen Sie konfigurieren, dass eine **Nachricht nicht von einer dieser Domänen Bedingungen empfangen wird** , die die e-Mail-Adresse ausschließt (Beispiel "Newsletter@contoso.com"). |
| **Nachricht wird an eine dieser Domänen gesendet.**  <br><br> **Nachricht wird nicht an eine dieser Domänen gesendet** | Wenden Sie die Richtlinie an, um bestimmte Domänen oder e-Mail-Adressen in gesendete Nachrichten einzuschließen oder auszuschließen. Geben Sie jede Domäne oder e-Mail-Adresse ein, und trennen Sie mehrere Domänen oder e-Mail-Adressen durch ein Komma. Jede Domäne oder e-Mail-Adresse wird separat angewendet, nur eine Domäne oder e-Mail-Adresse muss für die Richtlinie gelten, die auf die Nachricht angewendet werden soll. <br><br> Wenn Sie alle an eine bestimmte Domäne gesendeten e-Mails überprüfen möchten, jedoch gesendete Nachrichten ausschließen möchten, die keine Überprüfung benötigen, müssen Sie zwei Bedingungen konfigurieren: <br> -Eine **Nachricht wird an eine dieser Domänen Bedingungen gesendet** , die die Domäne definiert ("contoso.com") und <br> -Eine **Nachricht wird nicht an eine dieser Domänen Bedingungen gesendet** , die die e-Mail-Adresse ("Subscriptions@contoso.com") ausschließen. |
| **Nachricht wird mit einer dieser Bezeichnungen klassifiziert.**  <br><br> **Nachricht ist nicht mit einer dieser Bezeichnungen klassifiziert** | So wenden Sie die Richtlinie an, wenn bestimmte Aufbewahrungs Bezeichnungen in einer Nachricht enthalten oder ausgeschlossen werden. Aufbewahrungs Bezeichnungen müssen separat konfiguriert werden, und die konfigurierten Beschriftungen werden als Teil dieser Bedingung ausgewählt. Jede ausgewählte Bezeichnung wird separat angewendet (nur eine dieser Bezeichnungen muss für die Richtlinie gelten, die auf die Nachricht angewendet wird). Weitere Informationen zum Konfigurieren von Aufbewahrungs Bezeichnungen finden Sie unter [Overview of Retention Labels](labels.md).|
| **Nachricht enthält eines dieser Wörter**  <br><br> **Nachricht enthält keines dieser Wörter** | Wenn Sie die Richtlinie anwenden möchten, wenn bestimmte Wörter oder Ausdrücke in einer Nachricht enthalten oder ausgeschlossen werden, geben Sie jedes Wort ein, das durch ein Komma getrennt ist. Verwenden Sie für Ausdrücke mit zwei oder mehr Wörtern Anführungszeichen um den Ausdruck. Jedes Wort oder jede Phrase, die Sie eingeben, wird separat angewendet (es muss nur ein Wort für die Richtlinie gelten, die auf die Nachricht angewendet wird). Weitere Informationen zum Eingeben von Wörtern oder Ausdrücken finden Sie im nächsten Abschnitt [Matching words and phrases to emails or attachments](communication-compliance-feature-reference.md#Matchwords).|
| **Attachment enthält eines dieser Wörter**  <br><br> **Attachment enthält keines dieser Wörter** | Wenn Sie die Richtlinie anwenden möchten, wenn bestimmte Wörter oder Ausdrücke in einer Nachrichtenanlage eingeschlossen oder ausgeschlossen werden (beispielsweise in einem Word-Dokument), geben Sie jedes Wort durch ein Komma getrennt ein. Verwenden Sie für Ausdrücke mit zwei oder mehr Wörtern Anführungszeichen um den Ausdruck. Jedes Wort oder jede Phrase, die Sie eingeben, wird separat angewendet (nur ein Wort muss gelten, damit die Richtlinie auf die Anlage angewendet wird). Weitere Informationen zum Eingeben von Wörtern oder Ausdrücken finden Sie im nächsten Abschnitt [Matching words and phrases to emails or attachments](communication-compliance-feature-reference.md#Matchwords).|
| **Attachment ist einer der folgenden Dateitypen**  <br><br> **Attachment ist keiner dieser Dateitypen** | Geben Sie die Dateierweiterungen ein (beispielsweise. exe oder. pdf), um die Kommunikation zu überwachen, die bestimmte Anlagentypen einschließen oder ausschließen. Wenn Sie mehrere Dateierweiterungen einschließen oder ausschließen möchten, geben Sie diese in separaten Zeilen ein. Nur eine Anlagenerweiterung muss übereinstimmen, damit die Richtlinie angewendet wird.|
| **Nachricht ist größer als**  <br><br> **Die Nachrichtengröße ist nicht größer als** | Zum Überprüfen von Nachrichten, die auf einer bestimmten Größe basieren, verwenden Sie diese Bedingungen, um die maximale oder minimale Größe einer Nachricht anzugeben, bevor Sie überprüft werden kann. Wenn Sie beispielsweise angeben, dass die **Nachrichtengröße größer als** \> **1,0 MB**ist, werden alle Nachrichten mit einer Größe von 1,01 MB überprüft. Sie können Byte, Kilobyte, Megabyte oder Gigabyte für diese Bedingung auswählen.|
| **Anlage ist größer als**  <br><br> **Die Anlage ist nicht größer als** | Um Nachrichten anhand der Größe Ihrer Anlagen zu überprüfen, geben Sie die maximale oder minimale Größe an, die eine Anlage sein kann, bevor die Nachricht und ihre Anlagen überprüft werden können. Wenn Sie beispielsweise **Attachment größer als** \> **2,0 MB**angeben, werden alle Nachrichten mit Anlagen von 2,01 MB und mehr überprüft. Sie können Byte, Kilobyte, Megabyte oder Gigabyte für diese Bedingung auswählen.|
   
#### <a name="matching-words-and-phrases-to-emails-or-attachments"></a>Übereinstimmende Wörter und Ausdrücke in E-Mails oder Anlagen
<a name="Matchwords"> </a>

Jedes Wort, das Sie eingeben und mit einem Komma trennen, wird separat angewendet (nur ein Wort muss gelten, damit die Richtlinienbedingung auf die e-Mail oder Anlage angewendet wird). Verwenden wir beispielsweise die Bedingung, **Nachricht enthält eines dieser Wörter**, wobei die Schlüsselwörter "Banker", "vertraulich" und "Insiderhandel" durch ein Komma getrennt sind (Banker, Confidential, "Insiderhandel"). Die Richtlinie gilt für alle Nachrichten, die das Wort "Banker", "vertraulich" oder den Ausdruck "Insiderhandel" enthalten. Nur eins der Wörter oder einer der Ausdrücke muss vorkommen, damit die Richtlinienbedingung zutrifft. Wörter in der Nachricht oder Anlage müssen genau übereinstimmen, die Sie eingeben.

>[!IMPORTANT]
>Wenn Sie eine benutzerdefinierte Wörterbuchdatei importieren, muss jedes Wort oder jeder Ausdruck mit einem Wagenrücklauf und in einer separaten Zeilen getrennt werden. <br> Beispiel: <br><br>
>*Banker* <br>
>*vertraulich* <br>
>*Insiderhandel*

Zum Überprüfen von e-Mail-Nachrichten und Anlagen für dieselben Stichwörter erstellen Sie eine [Richtlinie zur Verhinderung von Datenverlust](create-test-tune-dlp-policy.md) mit einem [benutzerdefinierten Stichwort Wörterbuch](create-a-keyword-dictionary.md) für die Begriffe, die Sie in Nachrichten überprüfen möchten. Diese Richtlinienkonfiguration identifiziert definierte Schlüsselwörter, die entweder in der e-Mail-Nachricht **oder** in der e-Mail-Anlage angezeigt werden. Verwenden der standardmäßigen bedingten Richtlinieneinstellungen (*Nachricht enthält* eines dieser Wörter, und *Attachment enthält*eines dieser Wörter) um Begriffe in Nachrichten und Anlagen zu identifizieren, müssen die Begriffe **sowohl** in der Nachricht als auch in der Anlage vorhanden sein.
  
#### <a name="enter-multiple-conditions"></a>Eingeben mehrerer Bedingungen

Wenn Sie mehrere Bedingungen eingeben, verwendet Microsoft 365 alle Bedingungen zusammen, um zu bestimmen, wann die Aufsichtsrichtlinie auf Kommunikationselemente angewendet werden soll. Wenn Sie mehrere Bedingungen einrichten, müssen alle Bedingungen erfüllt sein, damit die Richtlinie angewendet werden kann, es sei denn, Sie geben eine Ausnahme ein. Sie benötigen beispielsweise eine Richtlinie, die gilt, wenn eine Nachricht das Wort "Trade" enthält und größer als 2 MB ist. Wenn die Nachricht jedoch auch die Wörter "von Contoso Financial genehmigt" enthält, sollte die Richtlinie nicht angewendet werden. In diesem Beispiel wären die drei Bedingungen wie folgt definiert:
  
- **Nachricht enthält eines dieser Wörter**mit den Schlüsselwörtern "Trade"
- Die **Nachrichtengröße ist größer als**, mit dem Wert 2 MB
- **Nachricht enthält keines dieser Wörter**, mit den Schlüsselwörtern "genehmigt von Contoso Financial Team"

### <a name="review-percentage"></a>Überprüfen des Prozentsatzes

Wenn Sie die zu überprüfende Menge an Inhalten reduzieren möchten, können Sie einen Prozentsatz der gesamten Kommunikation angeben, die einer Aufsichtsrichtlinie unterliegt. Aus dem Gesamtprozentsatz des Inhalts, der den ausgewählten Richtlinienbedingungen entspricht, wird ein Zufalls Beispiel für eine echt Zeitauswahl ausgewählt. Wenn Bearbeiter alle Elemente überprüfen möchten, können Sie **100%** in einer Kommunikations Konformitätsrichtlinie konfigurieren.

## <a name="notices"></a>Hinweise

Sie können Benachrichtigungsvorlagen erstellen, wenn Sie Benutzern eine e-Mail-Erinnerungs Benachrichtigung für Richtlinien Übereinstimmungen als Teil des Problem Lösungsprozesses senden möchten. Benachrichtigungen können nur an die e-Mail-Adresse des Mitarbeiters gesendet werden, die der Richtlinienübereinstimmung zugeordnet ist, die die spezifische Warnung zur Korrektur generiert hat. Wenn Sie eine Benachrichtigungsvorlage auswählen, die auf eine Richtlinienverletzung als Teil des Korrektur Workflows angewendet werden soll, können Sie die in der Vorlage definierten Feldwerte akzeptieren oder die Felder bei Bedarf überschreiben.

Notices-Vorlagen sind benutzerdefinierte e-Mail-Vorlagen, in denen Sie die folgenden Nachrichtenfelder definieren können:

|**Feld**|**Required**| **Details** |
|:-----|:-----|:-----|
|**Vorlagenname** | Ja | Anzeigename für die Notizvorlage, die Sie im Benachrichtigungs Workflow während der Wiederherstellung auswählen, unterstützt Textzeichen. |
| **Absenderadresse** | Ja | Die Adresse von einem oder mehreren Benutzern oder Gruppen, die die Nachricht an den Mitarbeiter mit einer Richtlinienübereinstimmung senden, die aus dem Active Directory für Ihr Abonnement ausgewählt wird. |
| **CC-und Bcc-Adressen** | Nein | Optionale Benutzer oder Gruppen, die über die Richtlinienübereinstimmung benachrichtigt werden sollen, ausgewählt aus dem Active Directory für Ihr Abonnement. |
| **Betreff** | Ja | Informationen, die in der Betreffzeile der Nachricht angezeigt werden, unterstützen Textzeichen. |
| **Nachrichtentext** | Ja | Informationen, die im Nachrichtentext angezeigt werden, unterstützen Text-oder HTML-Werte. |

### <a name="html-for-notices"></a>HTML für Benachrichtigungen

Wenn Sie mehr als eine einfache textbasierte e-Mail-Nachricht für Benachrichtigungen erstellen möchten, können Sie eine ausführlichere Meldung mithilfe von HTML im Feld Nachrichtentext einer Notizvorlage erstellen. Im folgenden Beispiel wird das Nachrichtentextformat für eine grundlegende HTML-basierte e-Mail-Benachrichtigungsvorlage bereitgestellt:

```HTML
<!DOCTYPE html>
<html>
<body>
<h2>Action Required: Contoso Employee Code of Conduct Policy Training</h2>
<p>A recent message you've sent has generated a policy alert for the Contoso Employee <a href='https://www.contoso.com'>Code of Conduct Policy</a>.</p>
<p>You are required to attend the Contoso Employee Code of Conduct <a href='https://www.contoso.com'>training</a> within the next 14 days. Please contact <a href='mailto:hr@contoso.com'>Human Resources</a> with any questions about this training request.</p>
<p>Thank you,</p>
<p><em>Human Resources</em></p>
</body>
</html>
```

>[!NOTE]
>Die HTML-href-Attribut Implementierung in den Benachrichtigungsvorlagen für die Kommunikations Konformität unterstützt derzeit nur einfache Anführungszeichen anstelle von doppelten Anführungszeichen für URL-Verweise.

## <a name="filters"></a>Filter

Mit den Kommunikations Kompatibilitäts filtern können Sie Warnmeldungen für schnellere Untersuchungen und Korrekturaktionen Filtern und sortieren. Die Filterung steht auf den Registerkarten **Ausstehend** und **aufgelöst** für jede Richtlinie zur Verfügung. Zum Speichern eines Filters oder Filtersatzes als gespeicherte Filterabfrage müssen mindestens ein Wert als Filterauswahl konfiguriert werden. In der folgenden Tabelle sind die Filterdetails aufgeführt:

|**Filter**|**Details**|
|:-----|:-----|
| **Date** | Das Datum, an dem die Nachricht von einem Benutzer in Ihrer Organisation gesendet oder empfangen wurde. |
| **File-Klasse** | Die Klasse der Nachricht auf der Grundlage des Nachrichtentyps, entweder *Nachricht* oder *Anlage*. |
| **Weist eine Anlage auf** | Das Attachment-vorhanden sein in der Nachricht. |
| **Elementklasse** | Die Quelle der Nachricht basierend auf dem Nachrichtentyp, e-Mail, Microsoft Team Chat, Bloonmberg usw. |
| **Empfängerdomänen** | Die Domäne, an die die Nachricht gesendet wurde. Diese Domäne ist normalerweise Ihre Microsoft 365-Abonnement Domäne standardmäßig. |
| **Empfänger** | Der Benutzer, an den die Nachricht gesendet wurde. |
| **Sender** | Die Person, die die Nachricht gesendet hat. |
| **Absenderdomäne** | Die Domäne, die die Nachricht gesendet hat. |
| **Size** | Die Größe der Nachricht in KB. |
| **Betreff/Titel** | Der Nachrichtenbetreff oder der Chat Titel. |
| **Tags** | Die einer Nachricht zugewiesenen Tags, entweder *fragwürdig*, *kompatibel*oder *nicht kompatibel*. |
| **Eskaliert an** | Der Benutzername der Person, die im Rahmen einer Nachrichten Eskalations Aktion enthalten ist. |
| **Klassifizierungen** | Der Name der integrierten und benutzerdefinierten Klassifizierungen, die auf die Nachricht angewendet werden. Einige Beispiele sind *beleidigende Sprache*, *gezielte Belästigung*, *Profanität*, *Bedrohung*und vieles mehr.

## <a name="alert-policies"></a>Warnungsrichtlinien

Nachdem Sie eine Richtlinie konfiguriert haben, wird automatisch eine entsprechende Warnungs Richtlinie erstellt, und Warnungen werden für Nachrichten generiert, die die in der Richtlinie definierten Bedingungen erfüllen. Standardmäßig wird für alle Richtlinien Übereinstimmungen Warnungsauslöser ein Schweregrad von Medium in der zugeordneten Warnungs Richtlinie zugewiesen. Warnungen werden für eine Kommunikations Konformitätsrichtlinie generiert, nachdem die Schwellenwertstufe Aggregations Auslöser in der zugeordneten Warnungs Richtlinie erfüllt ist.

Für Kommunikations Konformitätsrichtlinien sind die folgenden Warnungsrichtlinien Werte standardmäßig konfiguriert:

|**Warnungsrichtlinien Auslöser**|**Standardwert**|
|:-----|:-----|
| Aggregation | Einfache Aggregation |
| Schwellenwert | 4 Aktivitäten |
| Fenster | 60 Minuten |

>[!Note]
>Die Einstellungen für den Warnungsrichtlinien Schwellenwert für Aktivitäten unterstützen einen Mindestwert von 3 oder höher für Kommunikationsrichtlinien.

Sie können die Standardeinstellungen für Auslöser für die Anzahl der Aktivitäten, den Zeitraum für die Aktivitäten und für bestimmte Benutzer in Warnungsrichtlinien auf der Seite **Warnungsrichtlinien** im Security & Compliance Center ändern.

### <a name="change-the-severity-level-for-an-alert-policy"></a>Ändern des Schweregrads für eine Warnungs Richtlinie

Wenn Sie den in einer Warnungs Richtlinie für eine bestimmte Kommunikations Konformitätsrichtlinie zugewiesenen Schweregrad ändern möchten, führen Sie die folgenden Schritte aus:

1. Melden Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) sich mit Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365-Organisation an.

2. Wechseln Sie im Microsoft 365 Compliance Center zu **Richtlinien**.

3. Wählen Sie auf der Seite **Richtlinien** **Office 365 Benachrichtigung** aus, um die Seite **Warnungsrichtlinien** im **Office 365 Security & Compliance Center**zu öffnen.

4. Aktivieren Sie das Kontrollkästchen für die Kommunikations Konformitätsrichtlinie, die Sie aktualisieren möchten, und wählen Sie dann **Richtlinie bearbeiten**aus.

5. Wählen Sie auf der Registerkarte **Beschreibung** das Dropdownfeld **Schweregrad** aus, um die Richtlinien Warnstufe zu konfigurieren.

6. Wählen Sie **Speichern** aus, um den neuen Schweregrad auf die Richtlinie anzuwenden.

7. Wählen Sie **Schließen** aus, um die Seite Warnungsrichtlinien Details zu beenden.

## <a name="audit"></a>Überwachung

In einigen Fällen müssen Sie Aufsichtsbehörden oder Compliance-Prüfern Informationen bereitstellen, um die Überwachung der Aktivitäten und der Kommunikation von Mitarbeitern nachzuweisen. Bei diesen Informationen kann es sich um eine Zusammenfassung aller Aktivitäten handeln, die mit einer definierten Organisationsrichtlinie verknüpft sind, oder wenn sich eine Kommunikations Konformitätsrichtlinie ändert. Kommunikations Konformitätsrichtlinien verfügen über integrierte Überwachungspfade für die vollständige Bereitstellung interner oder externer Überprüfungen. Detaillierte Überwachungs Verläufe jeder Aktion zum Erstellen, bearbeiten und löschen werden von ihren Kommunikationsrichtlinien erfasst, um einen Nachweis der Aufsichtsverfahren zu ermöglichen.

>[!Important]
>Die Überwachung muss für Ihre Organisation aktiviert werden, bevor Kommunikations kompatibilitätsereignisse aufgezeichnet werden. Informationen zum Aktivieren der Überwachung finden Sie unter [Aktivieren des Überwachungsprotokolls](communication-compliance-configure.md#step-2-required-enable-the-audit-log).

Um Kommunikationsrichtlinien Aktivitäten anzuzeigen, wählen Sie das Steuerelement zum **Überprüfen von Aktivitäten** auf der Hauptseite für eine beliebige Richtlinie exportieren aus. Mit dieser Aktion wird eine Überwachungsdatei im CSV-Format generiert, die die folgenden Informationen enthält:

|**Feld**|**Details**|
|:-----|:-----|
| **CreationDate** | Das Datum, an dem die Aktivität in einer Richtlinie ausgeführt wurde. |
| **UserIds** | Der Benutzer, der die Aktivität in einer Richtlinie ausgeführt hat. |
| **Operations** | Die für die Richtlinie ausgeführten Vorgänge. |
| **Auditdata** | Dieses Feld ist die Hauptdatenquelle für alle Richtlinien Aktivitäten. Alle Aktivitäten werden durch Kommata-Trennzeichen aufgezeichnet und getrennt. |

Sie können auch Überwachungsaktivitäten im einheitlichen Überwachungsprotokoll oder mit dem PowerShell [-Cmdlet Search-UnifiedAuditLog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) anzeigen.

Im folgenden Beispiel werden die Aktivitäten für alle Aufsichts Überprüfungsaktivitäten (Richtlinien und Regeln) zurückgegeben:

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType AeD -Operations SupervisoryReviewTag
```

In diesem Beispiel werden die Updateaktivitäten für Ihre Richtlinien für die Kommunikations Konformität zurückgegeben:

```PowerShell
Search-UnifiedAuditLog -StartDate $startDate -EndDate $endDate -RecordType Discovery -Operations SupervisionPolicyCreated,SupervisionPolicyUpdated,SupervisionPolicyDeleted
```

## <a name="ready-to-get-started"></a>Sind Sie bereit zu beginnen?

Informationen zum Konfigurieren der Kommunikations Kompatibilität für Ihre Microsoft 365-Organisation finden Sie unter [configure Communication Compliance for your Microsoft 365 Organization](communication-compliance-configure.md).
