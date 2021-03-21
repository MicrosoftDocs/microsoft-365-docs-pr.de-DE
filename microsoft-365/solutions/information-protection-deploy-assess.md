---
title: Bewerten von Datenschutzrisiken und Identifizieren vertraulicher Elemente mit Microsoft 365
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 07/13/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Bestimmen Sie die Datenschutzbestimmungen, die relevanten Szenarien, Ihre Bereitschaft und die Typen vertraulicher Informationen, die sich in Ihrer Microsoft 365-Umgebung befinden.
ms.openlocfilehash: 6801f0af70e08d2b4efdc9e27f1cb1f1d636b821
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929168"
---
# <a name="assess-data-privacy-risks-and-identify-sensitive-items-with-microsoft-365"></a>Bewerten von Datenschutzrisiken und Identifizieren vertraulicher Elemente mit Microsoft 365

Die Bewertung der Datenschutzbestimmungen und Risiken, denen Ihre Organisation unterliegt, ist ein wichtiger erster Schritt vor der Implementierung verwandter Verbesserungsmaßnahmen, einschließlich derer, die mit Microsoft 365-Features und -Diensten erreichbar sind. 

## <a name="potentially-applicable-data-privacy-regulations"></a>Potenziell anwendbare Datenschutzbestimmungen

Einen guten Bezug zum umfassenderen regulatorischen Rahmen für Datenschutzbestimmungen finden Sie im [Microsoft Services Trust Portal](https://servicetrust.microsoft.com/) und in der Artikelreihe zur DSGVO-Verordnung [(DSGVO)](/compliance/regulatory/gdpr)sowie in anderen Materialien zu den Bestimmungen, die In Ihrer Branche oder Region möglicherweise unterliegen.

### <a name="gdpr"></a>DSGVO

Die DSGVO, die bekannteste und zitierte der Datenschutzbestimmungen, regelt die Sammlung, Speicherung, Verarbeitung und Freigabe von personenbezogenen Daten, die sich auf eine identifizierte oder identifizierbare natürliche Person beziehen, die in der Europäischen Union (EU) ansässig ist. 

Gemäß Artikel 4 der DSGVO: 

- "personenbezogene Daten" alle Informationen, die sich auf eine identifizierte oder identifizierbare natürliche Person ("betroffene Person") bezogen; Eine identifizierbare natürliche Person ist eine Person, die direkt oder indirekt identifiziert werden kann, insbesondere durch Verweis auf einen Bezeichner wie einen Namen, eine Identifikationsnummer, Standortdaten, eine Online-ID oder auf einen oder mehrere Faktoren, die für die physische, physiologische, genetische, geistige, wirtschaftliche, kulturelle oder soziale Identität dieser natürlichen Person spezifisch sind.

### <a name="iso-27001"></a>ISO 27001

Die Einhaltung anderer Standards wie ISO 27001 wurde auch von mehreren europäischen Aufsichtsbehörden als gültiger Absichtsproxy im gesamten Personen-, Prozess- und Technologiespektrum anerkannt. Die standards it specifies overlap and compliance to ISO-27001-driven protection mechanisms may be considered a proxy fulfilling some privacy obligations in certain circumstances.

### <a name="other-data-privacy-regulations"></a>Andere Datenschutzbestimmungen

Andere wichtige Datenschutzbestimmungen geben auch Anforderungen für die Verarbeitung personenbezogener Daten an.

In den USA sind dies der California Consumer Protection Act ([CCPA](/compliance/regulatory/ccpa-faq)), HIPAA-HITECH (United States Health Care Privacy Act) und der "Graham Leach Bliley Act" (GLBA). Zusätzliche statusspezifische Vorschriften sind auch in der Entwicklung oder in der Entwicklung. 

Weltweit gibt es weitere Beispiele, z. B. das Nationale DSGVO-Implementierungsgesetz (BDSG), das Brasilianische Datenschutzgesetz (LGPD) und viele andere.

## <a name="regulation-mapping-to-microsoft-365-technical-control-categories"></a>Zuordnung von Vorschriften zu technischen Steuerelementkategorien von Microsoft 365

Viele der datenschutzbezogenen Vorschriften haben überlappende Anforderungen, daher sollten Sie wissen, welchen Vorschriften sie unterliegen, bevor Sie ein technisches Kontrollsystem entwickeln. 

Für einen späteren Verweis in den Artikeln dieser Gesamtlösung enthält diese Tabelle Auszüge aus einer Auswahl von Datenschutzbestimmungen. 

| Verordnung | Artikel/Abschnitt | Auszug | Anwendbare kategorien für technische Steuerungen |
|:-------|:-----|:-------|:-------|
| DSGVO | Artikel 5(1)(f) | Personenbezogene Daten werden auf eine Weise verarbeitet, die eine angemessene Sicherheit der personenbezogenen Daten gewährleistet, einschließlich des Schutzes vor unbefugter oder unrechtmäßiger Verarbeitung und vor versehentlichem Verlust, Zerstörung oder Beschädigung, unter Verwendung geeigneter technischer oder organisatorischer Maßnahmen ("Integrität und Vertraulichkeit".  |  (Alle) <br> Identität <br> Gerät <br> Bedrohungsschutz <br> Schützen von Informationen <br> Steuern von Informationen <br> Entdecken und Reagieren |
|  | Artikel (32)(1)(a) | Unter Berücksichtigung des Standes der Technik, der Kosten der Implementierung und der Art, des Umfangs, des Kontexts und der Zwecke der Verarbeitung sowie des Risikos unterschiedlicher Wahrscheinlichkeit und Schwere für die Rechte und Freiheiten natürlicher Personen führen der Verantwortliche und der Auftragsverarbeiter geeignete technische und organisatorische Maßnahmen durch, um ein risikogerechtes Sicherheitsniveau sicherzustellen. , einschließlich gegebenenfalls: (a) Pseudonymisierung und Verschlüsselung personenbezogener Daten. | Schützen von Informationen |
|  | Artikel (13)(2)(a) | "... Der Verantwortliche stellt der Person zum Zeitpunkt der Personenbezogene Daten die folgenden weiteren Informationen zur Verfügung, die erforderlich sind, um eine gerechte und transparente Verarbeitung sicherzustellen: (a) den Zeitraum, für den die personenbezogenen Daten gespeichert werden, oder, falls dies nicht möglich ist, die Kriterien, die für die Bestimmung dieses Zeitraums verwendet werden. | Steuern von Informationen |
|  | Artikel (15)(1)(e) | Die person person hat das Recht, von der Verantwortlichen bestätigung zu erhalten, ob personenbezogene Daten, die sie betrifft, verarbeitet werden, und, falls dies der Fall ist, Zugriff auf die personenbezogenen Daten und die folgenden Informationen: (e) das Vorhandensein des Rechts auf Berichtigung oder Löschung personenbezogener Daten durch den Verantwortlichen oder einschränkung der Verarbeitung personenbezogener Daten bezüglich der person oder zum Widerspruch gegen diese Verarbeitung | Entdecken und Reagieren |
| LGPD | Artikel 46 | Verarbeitungsagenten treffen Sicherheits-, technische und administrative Maßnahmen, die personenbezogene Daten vor unbefugten Zugriffen und zufälligen oder unrechtmäßigen Situationen der Zerstörung, des Verlusts, der Änderung, der Kommunikation oder jeder Art von unsachgemäßer oder unrechtmäßiger Verarbeitung schützen können. | Schützen von Informationen <br> Steuern von Informationen <br> Entdecken und Reagieren|
|  | Artikel 48 | Der Prüfer muss der nationalen Behörde und den betroffenen Personen mitteilen, wenn ein Sicherheitsereignis eintritt, durch das Risiken oder relevante Schäden für die betroffenen Personen entstehen können. | Entdecken und Reagieren |
| HIPPA-HITECH | 45 CFR 164.312(e)(1) | Implementieren von technischen Sicherheitsmaßnahmen, um geschützte elektronische Gesundheitsdaten, die über ein elektronisches Kommunikationsnetzwerk übertragen werden, gegen nicht autorisierte Zugriffe zu schützen. | Schützen von Informationen |
|  | 45 C.F.R. 164.312(e)(2)(ii) | Implementieren eines Mechanismus zum Verschlüsseln und Entschlüsseln geschützter elektronischer Gesundheitsdaten, wann immer dies als angemessen erachtet wird. | Schützen von Informationen |
|  | 45 CFR 164.312(c)(2) | Implementieren elektronischer Mechanismen zur Bestätigung, dass geschützte elektronische Gesundheitsdaten nicht auf unbefugte Weise verändert oder vernichtet wurden. | Steuern von Informationen |
|  | 45 CFR 164.316(b)(1)(i) | Wenn für diesen Unterpart eine Aktion, Aktivität oder Bewertung dokumentiert werden muss, bewahren Sie einen schriftlichen (möglicherweise elektronischen) Datensatz der Aktion, Aktivität oder Bewertung auf. | Steuern von Informationen |
|  | 45 CFR 164.316(b)(1)(ii) | Die gemäß Paragraf (b)(1) dieses Abschnitts vorgeschriebene Dokumentation ist für einen Zeitraum von sechs Jahren ab dem Datum ihrer Erstellung oder ab dem Datum, zu welchem diese zuletzt in Kraft war, je nachdem, welcher Zeitpunkt später eintritt, aufzubewahren. | Steuern von Informationen |
|  | 45 C.F.R. 164.308(a)(1)(ii)(D) | Implementieren von Verfahren zum regelmäßigen Überprüfen von Datensätzen der Aktivitäten des Informationssystems, z. B. Überwachungsprotokolle, Zugriffsberichte und Berichte zur Nachverfolgung von Sicherheitsvorfällen | Entdecken und Reagieren |
|  | 45 C.F.R. 164.308(a)(6)(ii) | Identifikation und Reaktion auf mutmaßliche oder bekannte Sicherheitsvorfälle; Minimieren von schädlichen Auswirkungen von Sicherheitsvorfällen, die der betroffenen Entität oder betroffenen Geschäftspartnern bekannt sind, im größtmöglichen Ausmaß; Dokumentieren von Sicherheitsvorfällen und deren Ergebnissen. | Entdecken und Reagieren |
|  | 45 C.F.R. 164.312(b) | Implementieren Sie Hardware-, Software- und Verfahrensmechanismen, die Aktivitäten in Informationssystemen aufzeichnen und untersuchen, die elektronische geschützte Integritätsinformationen enthalten oder verwenden. | Entdecken und Reagieren |
| CCPA | 1798.105(c) | Ein Unternehmen, das eine überprüfbare Anforderung eines Verbrauchers erhält, die personenbezogenen Informationen des Verbrauchers gemäß Unterteilung (a) dieses Abschnitts zu löschen, löscht die personenbezogenen Daten des Verbrauchers aus seinen Datensätzen und leitet alle Dienstanbieter an, die personenbezogenen Informationen des Verbrauchers aus ihren Datensätzen zu löschen. | Entdecken und Reagieren |
|  | 1798.105(d) | (Ausnahmen von 1798.105(c) <br> Ein Unternehmen oder ein Dienstanbieter muss dem Antrag eines Verbrauchers, die personenbezogenen Informationen des Verbrauchers zu löschen, nicht nach entsprechen, wenn es erforderlich ist, dass das Unternehmen oder der Dienstanbieter die personenbezogenen Informationen des Verbrauchers in folgender Reihenfolge aufbehaltt: (Weitere Informationen finden Sie in der aktuellen Verordnung). | Entdecken und Reagieren |
|||||

>[!Important]
>Dies ist nicht als vollständige Liste vorgesehen. Weitere Informationen zur Anwendbarkeit der genannten Abschnitte finden Sie unter [Compliance Manager](../compliance/compliance-manager.md) oder Ihrem Rechts- oder Complianceberater zu den aufgeführten technischen Kontrollkategorien.
>

## <a name="knowing-your-data"></a>Wissen über Ihre Daten

Unabhängig von den Bestimmungen, denen Sie unterliegen, sind unterschiedliche Benutzerdatentypen innerhalb und außerhalb Ihrer Organisation, die mit Ihren Systemen interagieren, wichtige Faktoren, die sich auf Ihre allgemeine Strategie zum Schutz personenbezogener Daten auswirken können, vorbehaltlich der Branchen- und Behördenbestimmungen, die für Ihre Organisation gelten. Dazu gehört, wo personenbezogene Daten gespeichert werden, welcher Typ sie sind und wie viel davon es gibt und unter welchen Umständen sie erfasst wurden.
 
![Wissen ihrer Daten: Welcher Typ sie ist und wie viel davon es gibt und unter welchen Umständen sie gesammelt wurden](../media/information-protection-deploy-assess/information-protection-deploy-assess-knowing-data.png)

### <a name="data-portability"></a>Datenportabilität 

Daten werden auch im Laufe der Zeit bewegt, während sie verarbeitet, verfeinert und andere Versionen daraus abgeleitet werden. Eine anfängliche Momentaufnahme reicht nie aus. Es muss einen fortlaufenden Prozess zum Kennen Ihrer Daten gibt. Dies stellt eine der größten Herausforderungen für große Organisationen dar, die erhebliche Mengen an personenbezogenen Daten verarbeiten. Organisationen, die das Problem "Ihre Daten kennen" nicht beheben, können potenziell mit einem sehr hohen Risiko und möglichen Bußgeldern von Aufsichtsbehörden rechnen.

![Der Datenlebenszyklus](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-lifecycle.png)
 
### <a name="where-the-personal-data-is"></a>Wo die personenbezogenen Daten gespeichert sind

Um Datenschutzbestimmungen zu erfüllen, können Sie sich nicht auf allgemeine Vorstellungen verlassen, wo personenbezogene Daten vorhanden sein könnten, entweder jetzt oder in Der Zukunft. Datenschutzbestimmungen erfordern, dass Organisationen nachweisen, dass sie ständig wissen, wo personenbezogene Daten gespeichert sind. Dies macht es wichtig, eine erste Momentaufnahme aller Datenquellen für eine mögliche Speicherung personenbezogener Informationen, einschließlich Ihrer Microsoft 365-Umgebung, zu erstellen und Mechanismen für die laufende Überwachung und Erkennung zu erstellen.

Wenn Sie Ihre allgemeine Bereitschaft und Das risiko im Zusammenhang mit Datenschutzbestimmungen noch nicht bewertet haben, verwenden Sie das folgende 3-Schritt-Framework, um zu beginnen. 

![Schritte zur Bewertung der allgemeinen Bereitschaft und des Risikos im Zusammenhang mit Datenschutzbestimmungen](../media/information-protection-deploy-assess/information-protection-deploy-assess-grid.png)

>[!Note]
>Dieser Artikel und seine Inhalte sollen nicht an die Stelle von Rechtsberatungsdiensten stehen. Es enthält einfach einige grundlegende Anleitungen und Links zu Tools, die in den frühen Phasen Ihrer Bewertung unterstützungshilfen.
>
 
## <a name="step-1-develop-a-foundational-understanding-of-your-organizations-personal-data-scenarios"></a>Schritt 1: Entwickeln eines grundlegenden Verständnisses der Szenarien für personenbezogene Daten In Ihrer Organisation 

Sie müssen die Gefährdung durch datenschutzbezogene Risiken basierend auf der Art der derzeit verwalteten personenbezogenen Daten, dem Ort, an dem sie gespeichert sind, den Schutzkontrollen, derEn Lebenszyklus und dem Zugriff darauf messen. 

Als Ausgangspunkt ist es wichtig, inventar zu machen, welche Arten von personenbezogenen Daten in Ihrer Microsoft 365-Umgebung vorhanden sind. Verwenden Sie die folgenden Kategorien:

- Mitarbeiterdaten, die für die Durchführung von täglichen Geschäftsfunktionen erforderlich sind
- Daten, die die Organisation zu ihren Geschäftskunden, Partnern und anderen Beziehungen im Business-to-Business(B2B)-Szenario hat
- Daten, die die Organisation über Verbraucher verfügt, die Informationen für Onlinedienste bereitstellen, die die Organisation im Business-to-Customer (B2C)-Szenario verwaltet

Im Folgenden finden Sie ein Beispiel für die verschiedenen Datentypen für typische Abteilungen einer Organisation.

![Arten von personenbezogenen Daten](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-types.png)

Ein Teil der personenbezogenen Daten, für die Datenschutzbestimmungen gelten, werden in der Regel außerhalb von Microsoft 365 gesammelt und gespeichert. Alle personenbezogenen Daten aus verbraucherorientierten Web- oder mobilen Anwendungen müssten aus diesen Anwendungen nach Microsoft 365 exportiert worden sein, um in Microsoft 365 einer Datenschutzprüfung unterliegen zu können. 

Ihre Datenschutzrisiken in Microsoft 365 sind möglicherweise im Verhältnis zu Ihren Webanwendungen und CRM-Systemen eingeschränkt, die diese Lösung nicht adressiert.

Es ist auch wichtig, bei der Bewertung Ihres Risikoprofils die folgenden häufigen Herausforderungen bei der Einhaltung von Datenschutzbestimmungen zu prüfen:

 - **Verteilung personenbezogener Daten.** Wie gestreut sind Informationen zu einem bestimmten Thema? Ist es bekannt genug, die Aufsichtsbehörden davon zu überzeugen, dass geeignete Kontrollen zur Anwendung kommen? Kann sie bei Bedarf untersucht und behoben werden?
- **Schutz vor Exfiltration.** Wie schützen Sie personenbezogene Daten eines bestimmten Typs oder einer bestimmten Quelle vor Einerkompromittiert und wie reagieren Sie, wenn dies der Gegebene war?
- **Schutz vs. Risiko.** Welche Information protection-Mechanismen sind im Verhältnis zum Risiko geeignet, und wie kann die Geschäftskontinuität und Produktivität erhalten und die Auswirkungen der Endbenutzer minimiert werden, wenn ein Eingreifen des Endbenutzers erforderlich ist? Soll beispielsweise die manuelle Klassifizierung oder Verschlüsselung verwendet werden?
- **Aufbewahrung personenbezogener Daten.** Wie lange müssen Informationen, die personenbezogene Daten enthalten, aus gültigen geschäftlichen Gründen aufbewahrt werden, und wie können Sie frühere Keep-it-forever-Praktiken vermeiden, die mit den Aufbewahrungsanforderungen für die Geschäftskontinuität abgewogen werden?
- **Behandeln von Anfragen von Datensubjekten.** Welche Mechanismen sind erforderlich, um Anträge von Datensubjekten (Data Subject Requests, DSRs) und Abhilfemaßnahmen wie Anonymisierung, Redaktion und Löschung zu behandeln?
- **Fortlaufende Überwachung und Berichterstellung.** Welche Art von Täglichen Überwachungs-, Untersuchungs- und Berichtstechniken stehen für die verschiedenen Datentypen und Quellen zur Verfügung?
- **Einschränkungen bei der Datenverarbeitung.** Gibt es Einschränkungen bei der Datennutzung für Informationen, die über diese Methoden gesammelt oder gespeichert werden, die die Organisation in Datenschutzkontrollen widerspiegeln muss? Beispielsweise können Verpflichtungen, dass personenbezogene Daten nicht von Vertriebsmitarbeitern verwendet werden, ihre Organisation dazu verpflichtet, Mechanismen zu schaffen, um die Übertragung oder Speicherung dieser Informationen in Systemen zu verhindern, die der Vertriebsorganisation zugeordnet sind.

### <a name="employee-data-required-to-carry-out-day-to-day-business-functions"></a>Mitarbeiterdaten, die für die Durchführung von täglichen Geschäftsfunktionen erforderlich sind

Organisationen müssen von Natur aus Daten zu Mitarbeitern zu elektronischen Identitäts- und Personalzwecken sammeln, vorbehaltlich der Vereinbarungen, denen sie in ihren Mitarbeiterverträgen zustimmen. Solange eine Person für ein Unternehmen arbeitet, ist dies in der Regel kein Problem. Die Organisation möchte möglicherweise Mechanismen schaffen, um zu verhindern, dass böswillige Akteure personenbezogene Daten von Mitarbeitern aussiczen oder insIcieren kommen. 

Wenn eine Person ein Unternehmen verlässt, verfügen Organisationen in der Regel über Prozesse, Verfahren und Aufbewahrungs- und Löschzeitpläne zum Entfernen von Benutzerkonten, zum Außerbetriebsetzen von Postfächern und persönlichen Laufwerken und zum Ändern des Mitarbeiterstatus in z. B. Personalsystemen. In Fällen, in denen ein Rechtsstreit besteht, kann ein Mitarbeiter oder ein anderer Beteiligter einer juristischen Untersuchung berechtigte Gründe für das Abrufen von Informationen zu personenbezogenen Daten haben, die in den Systemen der Organisation gespeichert sind. In einigen Fällen kann diese Partei anfordern, dass diese Daten entfernt oder anonymisiert werden. 

Um diese Anforderungen zu erfüllen, sollten Organisationen über Prozesse und Verfahren verfügen, die vorbeugende, detektive und Abhilfemaßnahmen erfüllen, um solche Anforderungen zu erleichtern, und beachten Sie, dass einige Informationen über einen Mitarbeiter für die Geschäftskontinuität als sinnvoll betrachtet werden können. Beispielsweise Informationen, die eine Person eine Datei erstellt oder eine Funktion ausgeführt hat. 

>[!Note]
>Untersuchungs- und Korrekturmethoden für personenbezogene Daten in Microsoft 365 finden Sie im [Artikel monitor and respond](information-protection-deploy-monitor-respond.md). Sie können auch automatisierte Klassifizierungs- und Schutzsysteme verwenden, um sicherzustellen, dass personenbezogene Daten innerhalb der Organisation gesteuert werden, und sie daran hindern, die Organisation in Situationen mit böswilligen Akteurs zu verlassen. Weitere Informationen [finden Sie im](information-protection-deploy-protect-information.md) Artikel zum Schützen von Informationen.
>
 
### <a name="data-the-organization-has-about-its-business-customers-in-the-b2b-scenario"></a>Daten, die die Organisation zu ihren Geschäftskunden im B2B-Szenario hat

Die Sammlung von B2B-Informationen stellt auch eine Herausforderung dar, da Ihre Organisation möglicherweise Aufzeichnungen von Kundennamen und Transaktionen in den verschiedenen Systemen für Geschäftskontinuitätszwecke vor versehentlicher oder böswilliger Exfiltration bewahren muss. Wie Mitarbeiterdaten müssen Organisationen über Richtlinien, Verfahren und technische Kontrollen verfügen, um diese Daten zu schützen und sie gemäß definierten Aufbewahrungs- und Löschungszeitplänen zu altern. 

In der Regel verfügen Verträge mit externen Kunden, Partnern und den anderen Entitäten, mit denen die Organisation Geschäfte macht, über Eine Sprache zur Behandlung solcher Daten, einschließlich Schutz, Aufbewahrung und Löschung während und nach der Beziehung der Entität mit der Organisation. 

### <a name="data-the-organization-has-about-consumers-who-provide-information-to-online-services-that-the-organization-manages-in-the-b2c-scenario"></a>Daten, die die Organisation über Verbraucher hat, die Informationen für Onlinedienste bereitstellen, die die Organisation im B2C-Szenario verwaltet

Diese Kategorie ist aufgrund vieler öffentlicher Fälle von Kundendatenlecks die kategorie, die die meisten Personen für den Datenschutz halten. Dies kann beabsichtigt sein, z. B. wenn ein Drittanbieter einen Vertrag mit dem Anbieter hat, oder unbeabsichtigt, z. B. exfiltration durch einen böswilligen Akteur. Der Schutz von Verbraucherdaten ist einer der Hauptgründe, warum die EU und andere diese Vorschriften erlassen haben. Datenschutzbestimmungen wie DSGVO und CCPA erfordern, dass Sie die Planung für:

- [Prüflisten für](/compliance/regulatory/gdpr-action-plan) Die [Aktionsplane und die Bereitschaft zur Rechenschaftspflicht](/compliance/regulatory/gdpr-arc-Office365)
- [Datenschutz-Folgenabschätzungen](/compliance/regulatory/gdpr-data-protection-impact-assessments)
- [Benachrichtigungen über Sicherheitsverletzungen](/compliance/regulatory/gdpr-breach-Office365)
- [Anfragen von Datensubjekten](/compliance/regulatory/gdpr-dsr-Office365)

Wenn Ihre Organisation nicht viele Direkte-von-Verbraucher-Datensammlungen macht, ist diese Kategorie möglicherweise weniger ein Problem. Möglicherweise müssen Sie jedoch weiterhin die in diesen Artikeln beschriebenen Prozesse durchgehen, um eine Compliance zu erreichen.

### <a name="step-1-summary"></a>Zusammenfassung von Schritt 1

Das Verständnis Ihrer Risiko- und Datenschutzbestimmungen ist ein wichtiger erster Schritt, der auf einem grundlegenden Verständnis der Szenarien für personenbezogene Daten In Ihrer Organisation basiert.

Wenn Sie nicht über personenbezogene Daten von Verbrauchern in Ihrer Microsoft 365-Umgebung verfügen oder sie auf bestimmte Teile der Umgebung beschränkt sind und die Notwendigkeit einer technischen Kontrolle auf eine Verbraucherdatenexposition setzt, muss diese technische Kontrolle möglicherweise nur in Teilen der Umgebung mit hohem Risiko eingesetzt werden, nicht überall.

Eine empfehlung einer externen Organisation oder eines Standardsteuerelements, z. B. vom Compliance Manager in Microsoft 365, kann zwar dazu beitragen, Ihre Steuerungsstrategie zu informieren, ihre Wahl der Implementierung sollte jedoch durch das Bewusstsein für das Datenbestandsbewusstsein gesteuert werden, um Ihr tatsächliches Risikorisiko zu quantifizieren.

Die meisten Organisationen haben ein gewisses Risiko für eines der oben genannten Szenarien. Es ist wichtig, einen ganzheitlichen Ansatz für die Bewertung zu nehmen.

## <a name="step-2-assess-your-readiness-for-complying-with-data-privacy-regulations"></a>Schritt 2: Bewerten Ihrer Bereitschaft zur Einhaltung von Datenschutzbestimmungen

Obwohl sie spezifisch für die DSGVO sind, bieten die Im kostenlosen Microsoft-DSGVO-Bewertungstool gestellten Fragen einen guten Einstieg in das Verständnis Ihrer allgemeinen Datenschutzbereitschaft. [](https://www.microsoft.com/cyberassessment/en/gdpr/uso365) 

Organisationen, die anderen Datenschutzbestimmungen unterliegen, wie z. B. CCPA in den USA oder Brasiliens LGPD, können auch von der Bestandsaufnahme der Bereitschaft dieses Tools profitieren, die sich auf überlappende Bestimmungen mit der DSGVO überschneiden.

Die DSGVO-Bewertung besteht aus den folgenden Abschnitten:

| Abschnitt | Beschreibung |
|:-------|:-----|
| Governance | <ol><li>Gibt Ihre Datenschutzrichtlinie explizit an, welche Dateninformationen verarbeitet werden? </li><li>Führen Sie regelmäßig Datenschutz-Folgenabschätzungen (Privacy Impact Assessments, PIAs) aus? </li><li> Verwenden Sie ein Tool zum Verwalten personenbezogener Informationen (PI)? </li><li> Verfügen Sie über eine gesetzliche Autorität für die Durchführung von Geschäftsgeschäften mit PI-Daten für eine bestimmte Person? Verfolgen Sie die Zustimmung für Daten? </li><li> Verfolgen, implementieren und verwalten Sie Überwachungssteuerelemente? Überwachen Sie datenlecks? </li></ol>|
| Löschen und Benachrichtigung | <ol><li>Geben Sie explizite Anweisungen dazu, wie auf benutzerdaten zugegriffen werden kann? </li><li> Verfügen Sie über dokumentierte Prozesse für die Verarbeitung der Zustimmung zum Opt-Out? </li><li> Verfügen Sie über einen automatisierten Löschvorgang für Daten? </li><li>   Haben Sie einen Prozess zum Überprüfen der Identität bei der Interaktion mit einem Kunden? </li></ol>|
| Risikominderung und Informationssicherheit | <ol><li>Verwenden Sie Tools zum Überprüfen unstrukturierter Daten? </li><li>Sind alle Server auf dem neuesten Stand, und nutzen Sie Firewalls, um sie zu schützen? </li><li>Führen Sie regelmäßige Sicherungen Ihrer Server aus? </li><li>Überwachen Sie aktiv auf Datenlecks? </li><li>Verschlüsseln Sie Ihre Ruhe- und Übertragungsdaten? </li></ol>|
| Richtlinienverwaltung | <ol><li>Wie verwalten Sie Ihre verbindlichen Unternehmensregeln (Binding Corporate Rules, BCRs)? </li><li>Verfolgen Sie die Zustimmung für Daten? </li><li> In einer Skala von 1 bis 5, die vollständig abgedeckt ist, umfassen Ihre Verträge Datenklassifizierungen und Handhabungsanforderungen? </li><li>Haben Sie einen Plan zur Reaktion auf Vorfälle und testen sie regelmäßig? </li><li>Welche Richtlinie verwenden Sie zum Verwalten des Zugriffs? </li></ol>|
|||
 
## <a name="step-3-identify-sensitive-information-types-that-occur-in-your-microsoft-365-environment"></a>Schritt 3: Identifizieren von Typen vertraulicher Informationen, die in Ihrer Microsoft 365-Umgebung auftreten. 

Dieser Schritt umfasst die Identifizierung bestimmter vertraulicher Informationstypen, die bestimmten behördlichen Kontrollen unterliegen, sowie das Auftreten dieser Typen in Ihrer Microsoft 365-Umgebung. 

Das Suchen von Inhalten in Ihrer Umgebung, die persönliche Inhalte enthalten, kann eine enorme Aufgabe sein, die früher eine Kombination aus Compliancesuche, eDiscovery, Advanced eDiscovery, DLP und Überwachung enthält. 

Mit der  neuen Datenklassifizierungslösung im Microsoft Compliance Admin Center ist dies mit der [Content Explorer-Funktion,](../compliance/data-classification-content-explorer.md) die entweder mit integrierten oder benutzerdefinierten vertraulichen Informationstypen funktioniert, einschließlich derjenigen im Zusammenhang mit personenbezogenen Daten, wesentlich einfacher geworden.
 
### <a name="sensitive-information-types"></a>Typen vertraulicher Informationen

Das Microsoft Compliance Admin Center wird mit über 100 vertraulichen Informationstypen vorab geladen, die meisten davon im Zusammenhang mit der Identifizierung und Suche nach personenbezogenen Daten. Diese integrierten Typen vertraulicher Informationen können dazu beitragen, Kreditkartennummern, Bankkontonummern, Reisepassnummern und vieles mehr basierend auf Mustern zu identifizieren und zu schützen, die durch einen regulären Ausdruck (regex) oder eine Funktion definiert sind. Weitere Informationen finden Sie unter [Wonach die Typen vertraulicher Informationen suchen](../compliance/sensitive-information-type-entity-definitions.md).

Wenn Sie einen organisationsspezifischen oder regionalen Typ vertraulicher Elemente identifizieren und schützen müssen, z. B. ein benutzerdefiniertes Format für Mitarbeiter-IDs oder andere persönliche Informationen, die noch nicht von einem integrierten vertraulichen Informationstyp abgedeckt sind, können Sie mit den folgenden Methoden einen benutzerdefinierten vertraulichen Informationstyp erstellen: 

- PowerShell
- Benutzerdefinierte Regeln mit exakter Daten übereinstimmung (EDM)
- Über die Benutzeroberfläche des Compliance Center-Admins, wie im [Artikel Use Compliance Score and Compliance Manager hervorgehoben](information-protection-deploy-compliance.md)

Sie können auch einen vorhandenen, integrierten vertraulichen Informationstyp anpassen.

Weitere Informationen finden Sie in den folgenden Artikeln:

- [Anpassen eines integrierten, vertraulichen Informationstyps](../compliance/customize-a-built-in-sensitive-information-type.md)
- [Informationen zu Typen vertraulicher Informationen](../compliance/sensitive-information-type-learn-about.md)
- [Erstellen eines benutzerdefinierten vertraulichen Informationstyps im Security & Compliance Center](../compliance/create-a-custom-sensitive-information-type.md)
- [Erstellen eines benutzerdefinierten Typs für vertrauliche Informationen in Security & Compliance Center PowerShell](../compliance/create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [Erstellen von benutzerdefinierten vertraulichen Informationstypen mit genauer Datenübereinstimmungsklassifizierung](../compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

### <a name="content-explorer"></a>Inhalts-Explorer

Ein wichtiges Tool zum Bestimmen des Vorkommens vertraulicher Elemente in Ihrer Umgebung ist der neue [Inhalts-Explorer](../compliance/data-classification-content-explorer.md) im Microsoft 365 Compliance Admin Center. Es ist ein automatisiertes Tool für die anfängliche und fortlaufende Überprüfung Ihres gesamten Microsoft 365-Abonnements auf das Auftreten vertraulicher Informationstypen und die Anzeige der Ergebnisse.
 
Mit dem neuen Tool für den Inhalts-Explorer können Sie die Speicherorte vertraulicher Elemente in Ihrer Umgebung schnell identifizieren, indem Sie entweder integrierte typen für vertrauliche Informationen oder benutzerdefinierte Typen verwenden. Dies kann die Einrichtung eines Prozesses und die zugewiesene Verantwortung für die regelmäßige Untersuchung der Anwesenheit und des Speicherorts vertraulicher Elemente umfassen.

Zusammen mit den anderen in diesem Artikel hervorgehobenen Schritten bietet dies einen Ausgangspunkt für die Identifizierung Ihrer allgemeinen Risikoexposition, Bereitschaft und des Standorts vertraulicher Elemente, die durch die geplante Microsoft 365-Konfiguration und -Überwachung geschützt werden sollen. 

### <a name="other-methods-to-identify-personal-data-in-your-environment"></a>Andere Methoden zum Identifizieren personenbezogener Daten in Ihrer Umgebung

Zusätzlich zum Inhalts-Explorer haben Organisationen Zugriff auf die Inhaltssuche-Funktion, um benutzerdefinierte Suchfunktionen zu erstellen, um personenbezogene Daten in ihrer Umgebung mithilfe erweiterter Suchkriterien und benutzerdefinierter Filter zu finden.

Ausführliche Anleitungen zur Verwendung der Inhaltssuche für die Ermittlung personenbezogener Daten finden Sie in [diesem Artikel](/compliance/regulatory/gdpr). Die Inhaltssuche und andere Ermittlungstechniken werden auch in DSRs für die [DSGVO und das CCPA untersucht.](/compliance/regulatory/gdpr-dsr-Office365#introduction-to-dsrs)

Weitere Einblicke in Untersuchungs- und Abhilfemaßnahmen für personenbezogene Daten in Microsoft 365 finden Sie im [Monitor- und Reaktionsartikel](information-protection-deploy-monitor-respond.md).

> [!NOTE]
> Informationen zu vertraulichen Informationen in lokalen Dateien finden Sie unter [Azure Information Protection](/azure/information-protection/quickstart-findsensitiveinfo).