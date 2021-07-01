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
ms.openlocfilehash: 8e41dccea3569573d45b2e07e8ab7f122c44b311
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229311"
---
# <a name="assess-data-privacy-risks-and-identify-sensitive-items-with-microsoft-365"></a>Bewerten von Datenschutzrisiken und Identifizieren vertraulicher Elemente mit Microsoft 365

Die Bewertung der Datenschutzbestimmungen und Risiken, denen Ihre Organisation unterliegt, ist ein wichtiger erster Schritt vor der Implementierung verwandter Verbesserungsmaßnahmen, einschließlich derjenigen, die mit Microsoft 365 Features und Diensten erreichbar sind.

## <a name="potentially-applicable-data-privacy-regulations"></a>Potenziell geltende Datenschutzbestimmungen

Einen guten Verweis auf den umfassenderen rechtlichen Rahmen für Datenschutzbestimmungen finden Sie im [Microsoft Services Trust Portal](https://servicetrust.microsoft.com/) und in der Reihe von Artikeln zur [Datenschutz-Grundverordnung (DSGVO)](/compliance/regulatory/gdpr)sowie in anderen Materialien zu den Bestimmungen, denen Sie in Ihrer Branche oder Region unterliegen können.

### <a name="gdpr"></a>DSGVO

Die DSGVO, die am häufigsten bekannte und zitate der Datenschutzbestimmungen, regelt die Erfassung, Speicherung, Verarbeitung und Freigabe von personenbezogenen Daten, die sich auf eine identifizierte oder identifizierbare natürliche Person beziehen, die in der Europäischen Union (EU) ansässig ist.

Gemäß Artikel 4 der DSGVO:

- "personenbezogene Daten" sind alle Informationen, die sich auf eine identifizierte oder identifizierbare natürliche Person ("betroffene Person") beziehen; Eine identifizierbare natürliche Person ist eine Person, die direkt oder indirekt identifiziert werden kann, insbesondere durch Verweis auf einen Bezeichner wie einen Namen, eine Identifikationsnummer, Standortdaten, eine Online-ID oder einen oder mehrere Faktoren, die spezifisch für die physische, physikalische, genetischen, mentalen, kulturellen, kulturellen oder sozialen Identität dieser natürlichen Person sind.

### <a name="iso-27001"></a>ISO 27001

Die Einhaltung anderer Standards wie ISO 27001 wurde auch von mehreren europäischen Aufsichtsbehörden als gültiger Absichtsproxy im gesamten Spektrum von Personen, Prozessen und Technologien erkannt. Die darin angegebenen Standards für die Überlappung und Einhaltung iso-27001-gesteuerter Schutzmechanismen können unter bestimmten Umständen als Proxy betrachtet werden, der einige Datenschutzverpflichtungen erfüllt.

### <a name="other-data-privacy-regulations"></a>Weitere Datenschutzbestimmungen

Andere wichtige Datenschutzbestimmungen legen auch Anforderungen für den Umgang mit personenbezogenen Daten fest.

In den Vereinigten Staaten sind dies der California Consumer Protection Act ([CCPA](/compliance/regulatory/ccpa-faq)), HIPAA-HITECH (United States Health Care Privacy Act) und der The California Leach Bliley Act (GLBA). Zusätzliche zustandsspezifische Vorschriften sind auch in der Anwendung oder in der Entwicklung.

In der ganzen Welt sind weitere Beispiele das nationale DSGVO-Implementierungs-Gesetz (BWP) Deutschland, das Brazil Data Protection Act (LGPD) und viele andere.

## <a name="regulation-mapping-to-microsoft-365-technical-control-categories"></a>Verordnungszuordnung zu Microsoft 365 Technischen Kontrollkategorien

Viele der Datenschutzbestimmungen haben sich überschneidende Anforderungen, daher sollten Sie verstehen, welchen Vorschriften sie unterliegen, bevor Sie ein technisches Kontrollschema entwickeln.

Für einen späteren Verweis in den Artikeln dieser Gesamtlösung enthält diese Tabelle Auszüge aus einer Stichprobe von Datenschutzbestimmungen.

| Verordnung | Artikel/Abschnitt | Auszug | Anwendbare Technische Kontrollkategorien |
|:-------|:-----|:-------|:-------|
| DSGVO | Artikel 5 Absatz 1 Buchstabe f | Personenbezogene Daten werden auf eine Weise verarbeitet, die eine angemessene Sicherheit der personenbezogenen Daten gewährleistet, einschließlich des Schutzes vor unbefugter oder unrechtmäßiger Verarbeitung und vor versehentlichem Verlust, Vernichtung oder Beschädigung unter Verwendung geeigneter technischer oder organisatorischer Maßnahmen ("Integrität und Vertraulichkeit".  |  (Alle) <br> Identität <br> Gerät <br> Bedrohungsschutz <br> Schützen von Informationen <br> Verwalten von Informationen <br> Entdecken und Reagieren |
|  | Artikel (32) (1) (a) | Unter Berücksichtigung des Standes der Technik, der Implementierungskosten und der Art, des Umfangs, des Kontexts und der Zwecke der Verarbeitung sowie des Risikos unterschiedlicher Wahrscheinlichkeit und Dringlichkeit für die Rechte und Freiheiten natürlicher Personen treffen der Verantwortliche und der Auftragsverarbeiter geeignete technische und organisatorische Maßnahmen, um ein dem Risiko angemessenes Sicherheitsniveau zu gewährleisten. , einschließlich gegebenenfalls zwischen den Folgenden: (a) Pseudonymisierung und Verschlüsselung personenbezogener Daten. | Schützen von Informationen |
|  | Artikel (13) (2) (a) | "... Der Verantwortliche stellt der betroffenen Person zum Zeitpunkt der Erfassung personenbezogener Daten die folgenden weiteren Informationen zur Verfügung, die erforderlich sind, um eine ordnungsgemäße und transparente Verarbeitung sicherzustellen: (a) den Zeitraum, für den die personenbezogenen Daten gespeichert werden, oder, falls dies nicht möglich ist, die Kriterien, die zur Festlegung dieses Zeitraums verwendet werden. | Verwalten von Informationen |
|  | Artikel (15) (1) (e) | Die betroffene Person hat das Recht, von dem Verantwortlichen eine Bestätigung darüber zu erhalten, ob sie betreffende personenbezogene Daten verarbeitet werden, und in diesem Fall Zugriff auf die personenbezogenen Daten und die folgenden Informationen: (e) das Vorhandensein des Rechts, von dem Verantwortlichen eine Berichtigung oder Löschung personenbezogener Daten oder eine Einschränkung der Verarbeitung personenbezogener Daten, die die betroffene Person betreffen, anzufordern oder gegen diese zu verfügen Verarbeitung | Entdecken und Reagieren |
| LGPD | Artikel 46 | Verarbeitungsagenten treffen Sicherheitsmaßnahmen, technische und administrative Maßnahmen, die in der Lage sind, personenbezogene Daten vor unbefugtem Zugriff und unbeabsichtigten oder unrechtmäßigen Situationen der Zerstörung, des Verlusts, der Änderung, der Kommunikation oder jeder Art von unsachgemäßer oder unrechtmäßiger Verarbeitung zu schützen. | Schützen von Informationen <br> Verwalten von Informationen <br> Entdecken und Reagieren|
|  | Artikel 48 | Der Prüfer muss der nationalen Behörde und den betroffenen Personen mitteilen, wenn ein Sicherheitsereignis eintritt, durch das Risiken oder relevante Schäden für die betroffenen Personen entstehen können. | Entdecken und Reagieren |
| MAUSTASTEA-HITECH | 45 CFR 164.312(e)(1) | Implementieren von technischen Sicherheitsmaßnahmen, um geschützte elektronische Gesundheitsdaten, die über ein elektronisches Kommunikationsnetzwerk übertragen werden, gegen nicht autorisierte Zugriffe zu schützen. | Schützen von Informationen |
|  | 45 C.F.R. 164.312(e)(2)(ii) | Implementieren eines Mechanismus zum Verschlüsseln und Entschlüsseln geschützter elektronischer Gesundheitsdaten, wann immer dies als angemessen erachtet wird. | Schützen von Informationen |
|  | 45 CFR 164.312(c)(2) | Implementieren elektronischer Mechanismen zur Bestätigung, dass geschützte elektronische Gesundheitsdaten nicht auf unbefugte Weise verändert oder vernichtet wurden. | Verwalten von Informationen |
|  | 45 CFR 164.316(b)(1)(i) | Wenn eine Aktion, Aktivität oder Bewertung von diesem Unterabschnitt dokumentiert werden muss, führen Sie ein schriftliches (möglicherweise elektronisches) Verzeichnis der Aktion, Aktivität oder Bewertung. | Verwalten von Informationen |
|  | 45 CFR 164.316(b)(1)(ii) | Die gemäß Paragraf (b)(1) dieses Abschnitts vorgeschriebene Dokumentation ist für einen Zeitraum von sechs Jahren ab dem Datum ihrer Erstellung oder ab dem Datum, zu welchem diese zuletzt in Kraft war, je nachdem, welcher Zeitpunkt später eintritt, aufzubewahren. | Verwalten von Informationen |
|  | 45 C.F.R. 164.308(a)(1)(ii)(D) | Implementieren von Verfahren zur regelmäßigen Überprüfung von Datensätzen über Informationssystem-Aktivitäten, z. B. Überwachungsprotokolle, Zugriffsberichte und Berichte zur Nachverfolgung von Sicherheitsvorfällen | Entdecken und Reagieren |
|  | 45 C.F.R. 164.308(a)(6)(ii) | Identifikation und Reaktion auf mutmaßliche oder bekannte Sicherheitsvorfälle; Minimieren von schädlichen Auswirkungen von Sicherheitsvorfällen, die der betroffenen Entität oder betroffenen Geschäftspartnern bekannt sind, im größtmöglichen Ausmaß; Dokumentieren von Sicherheitsvorfällen und deren Ergebnissen. | Entdecken und Reagieren |
|  | 45 C.F.R. 164.312(b) | Implementieren Sie Hardware-, Software- und Verfahrensmechanismen, die Aktivitäten in Informationssystemen aufzeichnen und untersuchen, die geschützte elektronische Gesundheitsdaten enthalten oder verwenden. | Entdecken und Reagieren |
| CCPA | 1798.105(c) | Ein Unternehmen, das einen nachweisbaren Antrag von einem Verbraucher erhält, die persönlichen Informationen des Verbrauchers gemäß Unterabschnitt (a) dieses Abschnitts zu löschen, löscht die persönlichen Informationen des Verbrauchers aus seinen Aufzeichnungen und weist alle Dienstanbieter an, die persönlichen Informationen des Verbrauchers aus seinen Aufzeichnungen zu löschen. | Entdecken und Reagieren |
|  | 1798.105(d) | (Ausnahmen von 1798.105(c) <br> Ein Unternehmen oder ein Dienstanbieter ist nicht verpflichtet, dem Antrag eines Verbrauchers auf Löschung der persönlichen Informationen des Verbrauchers nachzukommen, wenn es für das Unternehmen oder den Dienstanbieter erforderlich ist, die persönlichen Informationen des Verbrauchers zu verwalten, um: (Weitere Informationen finden Sie in der aktuellen Verordnung). | Entdecken und Reagieren |
|||||

> [!IMPORTANT]
> Dies ist nicht als vollständige Liste gedacht. Weitere Informationen zur Anwendbarkeit der aufgeführten Abschnitte auf die aufgeführten technischen Kontrollkategorien finden Sie im [Compliance-Manager](../compliance/compliance-manager.md) oder Ihrem Rechts- oder Compliance-Ratgeber.

## <a name="knowing-your-data"></a>Ihre Daten kennen

Unabhängig von den Bestimmungen, denen Sie unterliegen, sind unterschiedliche Benutzerdatentypen innerhalb und außerhalb Ihrer Organisation mit Ihren Systemen wichtige Faktoren, die sich auf Ihre allgemeine Strategie zum Schutz personenbezogener Daten auswirken können, vorbehaltlich der Branchen- und Regierungsvorschriften, die für Ihre Organisation gelten. Dazu gehört, wo personenbezogene Daten gespeichert werden, um welchen Typ es sich handelt und wie viel davon vorhanden ist und unter welchen Umständen sie gesammelt wurden.

![Wissen über Ihre Daten: Um welchen Typ es sich handelt und wie viel davon vorhanden ist und unter welchen Umständen sie erfasst wurden](../media/information-protection-deploy-assess/information-protection-deploy-assess-knowing-data.png)

### <a name="data-portability"></a>Datenportabilität

Daten werden auch im Laufe der Zeit verschoben, während sie verarbeitet, optimiert und andere Versionen davon abgeleitet werden. Eine erste Momentaufnahme reicht nie aus. Es muss ein fortlaufender Prozess vorhanden sein, um Ihre Daten zu kennen. Dies stellt eine der größten Herausforderungen für große Organisationen dar, die große Mengen an personenbezogenen Daten verarbeiten. Organisationen, die sich nicht mit dem Problem "Ihre Daten kennen" befassen, könnten potenziell ein sehr hohes Risiko und mögliche Strafzahlungen von Aufsichtsbehörden nach sich ziehen.

![Der Datenlebenszyklus](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-lifecycle.png)

### <a name="where-the-personal-data-is"></a>Wo sich die personenbezogenen Daten befinden

Um die Datenschutzbestimmungen zu erfüllen, können Sie sich weder jetzt noch in Zukunft auf allgemeine Begriffe verlassen, in denen Ihrer Meinung nach personenbezogene Daten vorhanden sein könnten. Datenschutzbestimmungen erfordern, dass Organisationen nachweisen, dass sie wissen, wo sich personenbezogene Daten kontinuierlich befinden. Dies macht es wichtig, eine erste Momentaufnahme aller Datenquellen für die mögliche Speicherung von persönlichen Informationen, einschließlich Ihrer Microsoft 365 Umgebung, zu erstellen und Mechanismen für die fortlaufende Überwachung und Erkennung einzurichten.

Wenn Sie Ihre allgemeine Bereitschaft und Ihr Risiko im Zusammenhang mit Datenschutzbestimmungen noch nicht bewertet haben, verwenden Sie das folgende 3-Schritt-Framework, um zu beginnen.

![Schritte zur Bewertung Ihrer allgemeinen Bereitschaft und Ihres Risikos im Zusammenhang mit Datenschutzbestimmungen](../media/information-protection-deploy-assess/information-protection-deploy-assess-grid.png)

> [!NOTE]
> Dieser Artikel und sein Inhalt sind nicht als Rechtsbeistand gedacht. Es enthält nur einige grundlegende Anleitungen und Links zu Tools, die in den frühen Phasen Ihrer Bewertung möglicherweise von Unterstützung sind.

## <a name="step-1-develop-a-foundational-understanding-of-your-organizations-personal-data-scenarios"></a>Schritt 1: Entwickeln eines grundlegenden Verständnisses der Szenarien für personenbezogene Daten Ihrer Organisation

Sie müssen die Gefährdung des Datenschutzrisikos anhand der Art der derzeit verwalteten personenbezogenen Daten messen, wo sie gespeichert werden, welche Schutzkontrollen darauf platziert werden, wie der Lebenszyklus verwaltet wird und wer Zugriff darauf hat.

Als Ausgangspunkt ist es wichtig, zu erfassen, welche Arten von personenbezogenen Daten in Ihrer Microsoft 365 Umgebung vorhanden sind. Verwenden Sie die folgenden Kategorien:

- Mitarbeiterdaten, die für die Ausführung von täglichen Geschäftsfunktionen erforderlich sind
- Daten, die die Organisation über ihre Geschäftskunden, Partner und andere Beziehungen im Business-to-Business (B2B)-Szenario hat
- Daten, die die Organisation über Verbraucher verfügt, die Informationen zu Onlinediensten bereitstellen, die die Organisation im B2C-Szenario (Business-to-Customer) verwaltet

Nachfolgend sehen Sie ein Beispiel für die verschiedenen Datentypen für typische Abteilungen einer Organisation.

![Arten von personenbezogenen Daten](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-types.png)

Ein Großteil der personenbezogenen Daten, die der Datenschutzbestimmungen unterliegen, werden in der Regel außerhalb Microsoft 365 gesammelt und gespeichert. Alle personenbezogenen Daten aus verbraucherorientierten Web- oder mobilen Anwendungen müssten aus diesen Anwendungen in Microsoft 365 exportiert worden sein, um innerhalb Microsoft 365 der Datenschutzprüfung unterzogen zu werden.

Ihre Datenschutzrisiken in Microsoft 365 können im Verhältnis zu Ihren Webanwendungen und CRM-Systemen, die von dieser Lösung nicht behandelt werden, eingeschränkt sein.

Es ist auch wichtig, bei der Bewertung Ihres Risikoprofils die folgenden allgemeinen Herausforderungen bei der Datenschutzcompliance zu berücksichtigen:

 - **Verteilung personenbezogener Daten.** Wie weit sind Informationen zu einem bestimmten Thema verteilt? Ist es bekannt genug, um Aufsichtsbehörden davon zu überzeugen, dass geeignete Kontrollen vorhanden sind? Kann es untersucht und bei Bedarf behoben werden?
- **Schutz vor Exfiltration.** Wie schützen Sie personenbezogene Daten eines bestimmten Typs oder einer bestimmten Quelle davor, kompromittiert zu werden, und wie reagieren Sie, wenn dies der Fall war?
- **Schutz im Vergleich zu Risiko.** Welche Informationsschutzmechanismen sind relativ zum Risiko geeignet, und wie können Sie die Geschäftskontinuität und Produktivität aufrechterhalten und die Auswirkungen der Endbenutzer minimieren, wenn ein Eingreifen des Endbenutzers erforderlich ist? Soll z. B. eine manuelle Klassifizierung oder Verschlüsselung verwendet werden?
- **Aufbewahrung personenbezogener Daten.** Wie lange müssen Informationen, die personenbezogene Daten enthalten, aus gültigen geschäftlichen Gründen aufbewahrt werden, und wie können Sie vergangene Keep-it-Forever-Praktiken vermeiden, die mit den Aufbewahrungsanforderungen für die Geschäftskontinuität in Zusammenhang stehen?
- **Verarbeitung von Anträgen betroffener Personen.** Welche Mechanismen sind für die Behandlung von Anträgen betroffener Personen (Data Subject Requests, DSRs) und Abhilfemaßnahmen wie Anonymisierung, Redaction und Löschung erforderlich?
- **Fortlaufende Überwachung und Berichterstellung.** Welche Arten von täglichen Überwachungs-, Untersuchungs- und Berichterstellungstechniken stehen für die verschiedenen Datentypen und Quellen zur Verfügung?
- **Einschränkungen bei der Datenverarbeitung.** Gibt es Einschränkungen bei der Verwendung von Daten für Informationen, die über diese Methoden gesammelt oder gespeichert werden, die die Organisation in Datenschutzkontrollen berücksichtigen muss? Beispielsweise kann es aufgrund von Verpflichtungen, dass personenbezogene Daten nicht von Vertriebsmitarbeitern verwendet werden, erforderlich sein, dass Ihre Organisation Mechanismen einleiten muss, um die Übertragung oder Speicherung dieser Informationen in Systemen zu verhindern, die mit der Vertriebsorganisation verbunden sind.

### <a name="employee-data-required-to-carry-out-day-to-day-business-functions"></a>Mitarbeiterdaten, die für die Ausführung von täglichen Geschäftsfunktionen erforderlich sind

Organisationen müssen von Natur aus Daten über Mitarbeiter für elektronische Identität und Personalwesen sammeln, abhängig von dem, was sie in ihren Mitarbeiterverträgen vereinbaren. Solange eine Person für ein Unternehmen arbeitet, ist dies in der Regel kein Problem. Die Organisation möchte möglicherweise Mechanismen einsetzen, um zu verhindern, dass böswillige Akteure personenbezogene Daten von Mitarbeitern ausfiltern oder offengelegt werden.

Wenn eine Person ein Unternehmen verlässt, verfügen Organisationen in der Regel über Prozesse, Verfahren sowie Aufbewahrungs- und Löschzeitpläne zum Entfernen von Benutzerkonten, Außerbetriebsetzen von Postfächern und persönlichen Laufwerken und Ändern des Mitarbeiterstatus in Personalsystemen. In Situationen, in denen ein Rechtsstreitigkeiten beteiligt ist, kann ein Mitarbeiter oder eine andere Partei einer rechtlichen Untersuchung gültige Gründe für die Beschaffung von Informationen über personenbezogene Daten haben, die in den Systemen der Organisation gespeichert sind. In einigen Fällen kann diese Partei verlangen, dass solche Daten entfernt oder anonymisiert werden.

Um diesen Anforderungen gerecht zu werden, sollten Organisationen über Prozesse und Verfahren verfügen, die den Präventiv-, Erkennungs- und Abhilfemaßnahmen dienen, um solche Anforderungen zu erleichtern. Dabei wird darauf hingewiesen, dass einige Informationen über einen Mitarbeiter für die Geschäftskontinuität unter Umständen als wesentlich betrachtet werden. Beispielsweise Informationen, dass eine Einzelperson eine Datei erstellt oder eine Funktion ausgeführt hat.

> [!NOTE]
> Untersuchungs- und Korrekturtechniken für personenbezogene Daten in Microsoft 365 finden Sie im [Artikel "Überwachen und Reagieren".](information-protection-deploy-monitor-respond.md) Sie können auch automatisierte Klassifizierungs- und Schutzschemas verwenden, um sicherzustellen, dass personenbezogene Daten innerhalb der Organisation kontrolliert werden, und um zu verhindern, dass sie die Organisation in Situationen mit böswilligen Angreifern verlassen. Weitere Informationen finden Sie im [Artikel "Informationen zum Schutz".](information-protection-deploy-protect-information.md)

### <a name="data-the-organization-has-about-its-business-customers-in-the-b2b-scenario"></a>Daten, die die Organisation über ihre Geschäftskunden im B2B-Szenario hat

Das Sammeln von B2B-Informationen ist auch eine Herausforderung, da Ihre Organisation möglicherweise Aufzeichnungen von Kundennamen und Transaktionen in ihren verschiedenen Systemen für Geschäftskontinuitätszwecke aufbewahren muss, diese Informationen jedoch vor versehentlicher oder böswilliger Exfiltration schützen muss. Wie Mitarbeiterdaten müssen Organisationen über Richtlinien, Verfahren und technische Kontrollen verfügen, um diese Daten zu schützen und entsprechend den definierten Aufbewahrungs- und Löschzeitplänen zu altern.

In der Regel werden Verträge mit externen Kunden, Partnern und den anderen Entitäten, mit denen die Organisation geschäftlich arbeitet, über eine Sprache für die Verarbeitung dieser Daten verfügen, einschließlich Schutz, Aufbewahrung und Löschung sowohl während als auch nach der Beziehung zwischen der Entität und der Organisation.

### <a name="data-the-organization-has-about-consumers-who-provide-information-to-online-services-that-the-organization-manages-in-the-b2c-scenario"></a>Daten, die die Organisation über Verbraucher verfügt, die Informationen zu Onlinediensten bereitstellen, die die Organisation im B2C-Szenario verwaltet

Diese Kategorie ist die Kategorie, die aufgrund vieler öffentlicher Instanzen von Kundendatenlecks am meisten in Bezug auf den Datenschutz nachdenkt. Dies kann beabsichtigt sein, z. B. ein Drittanbieter, der mit dem Anbieter in Vertrag ist, oder unbeabsichtigt, z. B. exfiltration durch einen böswilligen Akteur. Der Schutz von Verbraucherdaten ist einer der Hauptgründe, warum die EU und andere Diese Bestimmungen umgesetzt haben. Datenschutzbestimmungen wie DSGVO und CCPA erfordern, dass Sie Folgendes planen:

- [Aktionsplane](/compliance/regulatory/gdpr-action-plan) und [Prüflisten zu den Verantwortlichkeiten](/compliance/regulatory/gdpr-arc-Office365)
- [Datenschutz-Folgenabschätzung](/compliance/regulatory/gdpr-data-protection-impact-assessments)
- [Benachrichtigungen über Sicherheitsverletzungen](/compliance/regulatory/gdpr-breach-Office365)
- [Anfragen von Datensubjekten](/compliance/regulatory/gdpr-dsr-Office365)

Wenn Ihre Organisation nicht viele Direkte-von-Verbraucher-Datensammlungen durchführt, ist diese Kategorie möglicherweise weniger ein Problem. Möglicherweise müssen Sie jedoch noch die in diesen Artikeln beschriebenen Prozesse durchlaufen, um die Compliance zu erreichen.

### <a name="step-1-summary"></a>Zusammenfassung zu Schritt 1

Das Verständnis Ihrer Risiko- und Datenschutzbestimmungen ist ein wichtiger erster Schritt, der auf einem grundlegenden Verständnis der Szenarien für personenbezogene Daten Ihrer Organisation basiert.

Wenn Sie keine personenbezogenen Daten von Verbrauchern in Ihrer Microsoft 365-Umgebung haben oder auf bestimmte Teile der Umgebung beschränkt sind und die Notwendigkeit einer technischen Kontrolle darauf basiert, dass Verbraucherdaten ausgesetzt sind, muss diese technische Kontrolle möglicherweise nur in Bereichen mit hohem Risiko in der Umgebung eingesetzt werden, nicht überall.

Während eine empfehlung einer externen Organisation oder eines Standardsteuerelementsatzes, z. B. vom Compliance-Manager in Microsoft 365, ihre Steuerungsstrategie informieren kann, sollte Ihre Wahl der Implementierung durch das Datenbestandsbewusstsein gesteuert werden, um Ihre tatsächliche Risikobelichtung zu quantifizieren.

Die meisten Organisationen sind einem der oben genannten Szenarien ausgesetzt. Es ist wichtig, einen ganzheitlichen Ansatz für die Bewertung zu verfolgen.

## <a name="step-2-assess-your-readiness-for-complying-with-data-privacy-regulations"></a>Schritt 2: Bewerten Ihrer Bereitschaft zur Einhaltung von Datenschutzbestimmungen

Obwohl die Fragen im kostenlosen [Dsgvo-Bewertungstool](https://www.microsoft.com/cyberassessment/en/gdpr/uso365) von Microsoft spezifisch für die DSGVO sind, bieten sie einen guten Einstieg in das Verständnis Ihrer allgemeinen Datenschutzbereitschaft.

Organisationen, die anderen Datenschutzbestimmungen unterliegen, z. B. CCPA in den VEREINIGTEn Staaten oder die LGPD brasiliens, können auch von der Bestandsaufnahme der Bereitschaft dieses Tools aufgrund überlappender Bestimmungen mit der DSGVO profitieren.

Die DSGVO-Bewertung besteht aus folgenden Abschnitten:

| Abschnitt | Beschreibung |
|:-------|:-----|
| Governance | <ol><li>Gibt Ihre Datenschutzrichtlinie explizit an, welche Dateninformationen verarbeitet werden? </li><li>Führen Sie regelmäßig Datenschutz-Folgenabschätzungen durch? </li><li> Verwenden Sie ein Tool zum Verwalten persönlicher Informationen (PI)? </li><li> Verfügen Sie über eine rechtliche Autorität für die Geschäftstätigkeit mit PI-Daten für eine bestimmte Person? Verfolgen Sie die Zustimmung für Daten nach? </li><li> Verfolgen, implementieren und verwalten Sie Überwachungssteuerelemente? Überwachen Sie Datenlecks? </li></ol>|
| Löschen und Benachrichtigen | <ol><li>Geben Sie explizite Anweisungen dazu, wie auf die Daten von Benutzern zugegriffen werden kann? </li><li> Verfügen Sie über dokumentierte Prozesse für die Verarbeitung der Opt-Out-Zustimmung? </li><li> Verfügen Sie über einen automatisierten Löschvorgang für Daten? </li><li>   Haben Sie einen Prozess zum Überprüfen der Identität, wenn Sie mit einem Kunden in Kontakt treten? </li></ol>|
| Risikominderung und Informationssicherheit | <ol><li>Verwenden Sie Tools zum Scannen unstrukturierter Daten? </li><li>Sind alle Server auf dem neuesten Stand, und nutzen Sie Firewalls, um sie zu schützen? </li><li>Führen Sie regelmäßige Sicherungen Ihrer Server aus? </li><li>Überwachen Sie datenlecks aktiv? </li><li>Verschlüsseln Sie Ihre ruhenden daten und während der Übertragung? </li></ol>|
| Richtlinienverwaltung | <ol><li>Wie verwalten Sie Ihre Binding Corporate Rules (BCRs)? </li><li>Verfolgen Sie die Zustimmung für Daten nach? </li><li> Umfassen Ihre Verträge auf einer Skala von 1 bis 5, die vollständig abgedeckt wird, Datenklassifizierungen und Verarbeitungsanforderungen? </li><li>Haben Sie einen Plan zur Reaktion auf Vorfälle und testen Sie diesen regelmäßig? </li><li>Welche Richtlinie verwenden Sie zum Verwalten des Zugriffs? </li></ol>|
|||

## <a name="step-3-identify-sensitive-information-types-that-occur-in-your-microsoft-365-environment"></a>Schritt 3: Identifizieren Sie Typen vertraulicher Informationen, die in Ihrer Microsoft 365 Umgebung auftreten.

Dieser Schritt umfasst die Identifizierung bestimmter vertraulicher Informationstypen, die bestimmten behördlichen Kontrollen unterliegen, sowie deren Vorkommen in Ihrer Microsoft 365 Umgebung.

Das Suchen von Inhalten in Ihrer Umgebung, die persönliche Inhalte enthalten, kann eine beeindruckende Aufgabe sein, die früher eine Kombination aus Compliancesuche, eDiscovery, Advanced eDiscovery, DLP und Überwachung umfasste.

Mit der neuen **Datenklassifizierungslösung** im Microsoft Compliance Admin Center ist dies mit der [Inhalts-Explorer-Funktion,](../compliance/data-classification-content-explorer.md) die entweder mit integrierten oder benutzerdefinierten Typen vertraulicher Informationen funktioniert, einschließlich derjenigen im Zusammenhang mit personenbezogenen Daten, viel einfacher geworden.

### <a name="sensitive-information-types"></a>Typen vertraulicher Informationen

Das Microsoft Compliance Admin Center ist mit mehr als 100 Typen vertraulicher Informationen vorinstalliert, die meisten davon im Zusammenhang mit der Identifizierung und Suche nach personenbezogenen Daten. Diese integrierten Typen vertraulicher Informationen können dazu beitragen, Kreditkartennummern, Bankkontonummern, Reisepassnummern und vieles mehr basierend auf Mustern zu identifizieren und zu schützen, die durch einen regulären Ausdruck (regex) oder eine Funktion definiert sind. Weitere Informationen finden Sie unter [Wonach die Typen vertraulicher Informationen suchen](../compliance/sensitive-information-type-entity-definitions.md).

Wenn Sie einen organisationsspezifischen oder regionalen Typ vertraulicher Elemente identifizieren und schützen müssen, z. B. ein benutzerdefiniertes Format für Mitarbeiter-IDs oder andere persönliche Informationen, die nicht bereits von einem integrierten vertraulichen Informationstyp abgedeckt sind, können Sie mit diesen Methoden einen benutzerdefinierten Typ vertraulicher Informationen erstellen:

- PowerShell
- Benutzerdefinierte Regeln mit genauer Datenübereinstimmung (EDM)
- Über die Compliance Center-Administrator-Benutzeroberfläche, wie im [Artikel "Compliancebewertung und Compliance-Manager verwenden"](information-protection-deploy-compliance.md) hervorgehoben

Sie können auch einen vorhandenen integrierten vertraulichen Informationstyp anpassen.

Weitere Informationen finden Sie in den folgenden Artikeln:

- [Anpassen eines integrierten, vertraulichen Informationstyps](../compliance/customize-a-built-in-sensitive-information-type.md)
- [Informationen zu Typen vertraulicher Informationen](../compliance/sensitive-information-type-learn-about.md)
- [Erstellen eines benutzerdefinierten vertraulichen Informationstyps im Security & Compliance Center](../compliance/create-a-custom-sensitive-information-type.md)
- [Erstellen eines benutzerdefinierten Typs für vertrauliche Informationen in Security & Compliance Center PowerShell](../compliance/create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [Erstellen von benutzerdefinierten vertraulichen Informationstypen mit genauer Datenübereinstimmungsklassifizierung](../compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

### <a name="content-explorer"></a>Inhalts-Explorer

Ein wichtiges Tool, mit dem Das Auftreten vertraulicher Elemente in Ihrer Umgebung bestimmt werden kann, ist der neue [Inhalts-Explorer](../compliance/data-classification-content-explorer.md) im Microsoft 365 Compliance Admin Center. Es ist ein automatisiertes Tool für die anfängliche und fortlaufende Überprüfung Ihres gesamten Microsoft 365 Abonnements auf das Auftreten vertraulicher Informationstypen und die Anzeige der Ergebnisse.

Mit dem neuen Inhalts-Explorer-Tool können Sie schnell die Speicherorte vertraulicher Elemente in Ihrer Umgebung identifizieren, indem Sie entweder integrierte oder benutzerdefinierte Typen vertraulicher Informationen verwenden. Dies kann die Einrichtung eines Prozesses und die zugewiesene Verantwortung umfassen, das Vorhandensein und den Speicherort vertraulicher Elemente regelmäßig zu untersuchen.

Zusammen mit den anderen in diesem Artikel hervorgehobenen Schritten bietet dies einen Ausgangspunkt für die Identifizierung der Gesamtrisikoposition, Bereitschaft und Desorts vertraulicher Elemente, die durch geplante Microsoft 365 Konfiguration und Überwachung geschützt werden sollen.

### <a name="other-methods-to-identify-personal-data-in-your-environment"></a>Andere Methoden zum Identifizieren personenbezogener Daten in Ihrer Umgebung

Zusätzlich zum Inhalts-Explorer haben Organisationen Zugriff auf die Inhaltssuche-Funktion, um benutzerdefinierte Suchvorgänge zu erstellen, um personenbezogene Daten in ihrer Umgebung mithilfe erweiterter Suchkriterien und benutzerdefinierter Filter zu finden.

Ausführliche Anleitungen zur Verwendung der Inhaltssuche zur Ermittlung personenbezogener Daten finden Sie in [diesem Artikel.](/compliance/regulatory/gdpr) Die Inhaltssuche und andere Ermittlungstechniken werden auch in [Anträgen betroffener Personen für die DSGVO und das CCPA](/compliance/regulatory/gdpr-dsr-Office365#introduction-to-dsrs)untersucht.

Weitere Einblicke in Untersuchungs- und Korrekturtechniken für personenbezogene Daten in Microsoft 365 finden Sie im [Monitor- und Reaktionsartikel.](information-protection-deploy-monitor-respond.md)

> [!NOTE]
> Informationen dazu, welche vertraulichen Informationen Sie in lokalen Dateien gespeichert haben, finden Sie unter [Azure Information Protection.](/azure/information-protection/quickstart-findsensitiveinfo)