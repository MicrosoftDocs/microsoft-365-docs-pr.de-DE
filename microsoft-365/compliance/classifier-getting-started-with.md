---
title: Erste Schritte mit trainierbaren Klassifizierern (Vorschau)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Eine Microsoft 365-schulungsable-Klassifizierung ist ein Tool, mit dem Sie verschiedene Arten von Inhalten erkennen können, indem Sie positive und negative Beispiele für Ihre Untersuchung geben. Nach der Schulung der Klassifizierung bestätigen Sie, dass die Ergebnisse korrekt sind. Anschließend können Sie die Inhalte Ihrer Organisation durchsuchen und klassifizieren, um Aufbewahrungs-oder Vertraulichkeits Bezeichnungen anzuwenden oder Sie in Datenverlust Verhinderung (DLP) oder in Aufbewahrungsrichtlinien einzubeziehen.
ms.openlocfilehash: 7cad27112597bcdbdce6aeb33fef66f24bdd8819
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "46502972"
---
# <a name="getting-started-with-trainable-classifiers-preview"></a>Erste Schritte mit trainierbaren Klassifizierern (Vorschau)

Das klassifizieren und kennzeichnen von Inhalten, damit es geschützt und ordnungsgemäß behandelt werden kann, ist der Ausgangspunkt für die Informationsschutz Disziplin. Microsoft 365 verfügt über drei Möglichkeiten zum Klassifizieren von Inhalten.

## <a name="manually"></a>Manuell

Für diese Methode ist menschliches Urteilen und Handeln erforderlich. Ein Administrator kann entweder die bereits vorhandenen Bezeichnungen und Typen vertraulicher Informationen verwenden oder eigene erstellen und diese dann veröffentlichen. Benutzer und Administratoren wenden diese auf Inhalte an, wenn Sie darauf stoßen. Anschließend können Sie den Inhalt schützen und seine Disposition verwalten.

## <a name="automated-pattern-matching"></a>Automatischer Musterabgleich

Diese Kategorie von Klassifizierungsmechanismen umfasst das Auffinden von Inhalten nach folgenden Themen:

- Schlüsselwörter oder Metadatenwerte (Stichwortabfrage Sprache).
- Verwenden zuvor identifizierter Muster vertraulicher Informationen wie soziale Sicherheit, Kreditkarten-oder Bank Kontonummern [(vertrauliche Informationstypen – Entitätsdefinitionen)](sensitive-information-type-entity-definitions.md).
- Erkennen eines Elements, da es sich um eine Variation einer Vorlage handelt [(Dokumentieren des Finger Drucks)](document-fingerprinting.md).
- Verwenden des Vorhandenseins exakter Zeichenfolgen [(exakte Datenübereinstimmung)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).

Sensitivitäts-und Aufbewahrungs Bezeichnungen können dann automatisch angewendet werden, um die Inhalte für die Verwendung in [Datenverlust Verhinderung (DLP)](data-loss-prevention-policies.md) und [automatisch anwenden von Policen für Aufbewahrungs Bezeichnungen](apply-retention-labels-automatically.md)verfügbar zu machen.

## <a name="trainable-classifiers"></a>Trainierbare Klassifizierungsmerkmale

Diese Klassifizierungsmethode eignet sich besonders gut für Inhalte, die nicht einfach durch die manuellen oder automatisierten Mustervergleichsmethoden identifiziert werden können. Bei dieser Klassifizierungsmethode geht es eher darum, einen Klassifizierer so zu trainieren, dass er ein Element anhand dessen identifiziert, was das Element ist, und nicht anhand von Elementen, die sich im Element befinden (Musterabgleich). Eine Klassifizierung zeigt, wie Sie einen Inhaltstyp identifizieren, indem Sie sich Hunderte Beispiele für die Inhalte ansehen, die Sie bei der Klassifizierung interessieren. Sie beginnen mit dem Füttern von IT-Beispielen, die definitiv in der Kategorie sind. Nachdem diese verarbeitet wurden, testen Sie Sie, indem Sie eine Kombination aus sowohl passenden als auch nicht passenden Beispielen zuweisen. Die Klassifizierung legt dann Vorhersagen fest, ob ein bestimmtes Element in die Kategorie fällt, die Sie erstellen. Anschließend bestätigen Sie die Ergebnisse, sortieren die positiven, negativen, falsch positiven und falschen negative, um die Genauigkeit der Vorhersagen zu verbessern. Wenn Sie die geschulte Klassifizierung veröffentlichen, werden Elemente an Speicherorten wie SharePoint Online, Exchange und OneDrive sortiert, und der Inhalt wird klassifiziert.

### <a name="where-you-can-use-trainable-classifiers"></a>Wo Sie Schulungs Klassifizierer verwenden können
Sowohl integrierte Klassifizierungen als auch eingestufte Klassifizierungen stehen als Bedingung für die automatische [Kennzeichnung von Office mit Vertraulichkeits Bezeichnungen](apply-sensitivity-label-automatically.md), [automatisch angewendete Aufbewahrungs Bezeichnungsrichtlinie basierend auf einer Bedingung](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) und in der [Kommunikations Konformität](communication-compliance.md)zur Verfügung. 

Für Sensitivitäts Bezeichnungen können integrierte und eigene Klassifizierungen als Bedingungen verwendet werden, siehe [Anwenden einer Vertraulichkeits Bezeichnung auf Inhalte automatisch](apply-sensitivity-label-automatically.md).

> [!IMPORTANT]
> Schulungs fähige Klassifizierungen funktionieren nur mit Elementen, die nicht verschlüsselt sind und sich in Englisch befinden.

### <a name="licensing-requirements"></a>Lizenzierungsanforderungen

Auszubildende Klassifizierer sind ein Microsoft 365 E5-oder E5-Compliance-Feature. Sie müssen über eines dieser Abonnements verfügen, damit Sie Sie nutzen können.

### <a name="pre-requisites"></a>Voraussetzungen

So greifen Sie in der Benutzeroberfläche auf schulungsbezogene Klassifizierungen zu: 
- der globale Administrator muss sich für den Mandanten anmelden.
- Compliance-Administratorrolle oder Kompatibilitätsdaten Administrator ist erforderlich, um eine Klassifizierung zu trainieren.

In diesen Szenarien benötigen Sie Konten mit diesen Berechtigungen zur Verwendung von Schulungs Klassifizierern:

- Richtlinien Szenario für Aufbewahrungs Bezeichnungen: RecordManagement-und Aufbewahrungs Verwaltungsrollen 
- Richtlinien Szenario für die Sensitivitäts Bezeichnung: Sicherheitsadministrator, Kompatibilitäts Administrator, Kompatibilitätsdaten Administrator
- Kommunikations Konformitätsrichtlinien Szenario: Administrator für Insider Risiko Management, Aufsichts Überprüfungs Administrator 

## <a name="types-of-classifiers"></a>Typen von Klassifizierungen

Es gibt integrierte Klassifizierungen und Klassifizierer für Auszubildende. Das Einholen einer lernbaren Klassifizierung in einen Veröffentlichungszustand erfordert eine Zeitinvestition für die Schulung. Für die ersten Schritte bei der Verwendung von Klassifizierungen enthält Microsoft 365 einige integrierte Klassifizierungen.

> [!NOTE]
> Bevor Sie eine integrierte Klassifizierung in Ihrem Klassifikations-und Beschriftungs Workflow verwenden, sollten Sie Sie anhand eines Beispiels ihrer organisationsinhalte testen, das Ihrer Meinung nach der Kategorie entspricht, um zu überprüfen, ob Ihre Klassifizierungs Vorhersagen Ihren Erwartungen entsprechen.

### <a name="understanding-built-in-classifiers"></a>Grundlegendes zu integrierten Klassifizierungen

Microsoft 365 verfügt über fünf Empfohlene integrierte Klassifizierungen:

> [!CAUTION]
> Die integrierte Klassifizierung **Anstößige Sprache** wird eingestellt, da sie eine große Anzahl falsch positiver Ergebnisse erzeugt hat. Verwenden Sie es nicht, und wenn Sie es derzeit verwenden, sollten Sie Ihre Geschäftsprozesse aus dieser entfernen. Es wird empfohlen, stattdessen die integrierten Klassifizierungen " **Bedrohung**", " **Profanität**" und " **Belästigung** " zu verwenden.

- **Lebensläufe**: erkennt Elemente, bei denen es sich um Text Konten für persönliche, pädagogische, berufliche Qualifikationen, Berufserfahrung und andere personenbezogene Informationen handelt.
- **Quellcode**: erkennt Elemente, die eine Reihe von Anweisungen und Anweisungen enthalten, die in den Top 25 verwendeten Computer Programmiersprachen auf GitHub geschrieben wurden.

  |Name der Sprache|||||
  |---------|---------|---------|---------|---------|
  |ActionScript|C        |C#       |C++     |Clojure  |
  |CoffeeScript|CSS     |OK       |Haskell |HTML     |
  |Java     |JavaScript|Lua      |MATLAB   |Objective-C|
  |Perl     |PHP      |Python   |R        |Ruby     |
  |Scala    |Shell    |SWIFT    |Tex      |Vim-Skript|

> [!NOTE]
> Der Quellcode wird geschult, um zu erkennen, wann der Hauptteil des Texts Quellcode ist. Es wird kein quellcodetext erkannt, der mit nur-Text vermischt wird.

- **Belästigung**: erkennt eine bestimmte Kategorie von Textelementen anstößiger Sprache im Zusammenhang mit anstößigem Verhalten, das auf eine oder mehrere Personen basierend auf den folgenden Merkmalen ausgerichtet ist: Rasse, Ethnizität, Religion, nationale Herkunft, Geschlecht, sexuelle Orientierung, Alter, Behinderung
- **Profanität**: erkennt eine bestimmte Kategorie von Textelementen anstößiger Sprache, die Ausdrücke enthalten, die die meisten Personen in Verlegenheit bringen
- **Threat**: erkennt eine bestimmte Kategorie von Textelementen anstößiger Sprache im Zusammenhang mit Bedrohungen, um Gewalt zu begehen oder physischen Schaden oder einer Person oder einer Eigenschaft zu Schaden

Diese werden in der Ansicht " **Microsoft 365 Compliance Center**  >  **-Datenklassifizierung (Preview)**"  >  **trainable Klassifizierers** "mit dem Status" angezeigt `Ready to use` .

![Klassifizierungen – einsatzfertige Klassifizierungen](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> Bitte beachten Sie, dass die beleidigende Sprache, Belästigung, Profanität und Bedrohungs Klassifizierungen nur mit durchsuchbarem Text funktionieren, die nicht erschöpfend oder vollständig sind.  Außerdem ändern sich die Sprach-und Kulturstandards ständig, und in Anbetracht dieser Gegebenheiten behält sich Microsoft das Recht vor, diese Klassifizierungen nach eigenem Ermessen zu aktualisieren. Während die Klassifizierungen Ihre Organisation bei der Überwachung von anstößigen und anderen Sprachen unterstützen können, befassen sich die Klassifizierungsverfahren nicht mit den Konsequenzen dieser Sprache und dienen nicht dazu, die Verwendung dieser Sprache allein zu überwachen oder zu beantworten. Ihre Organisation und nicht Microsoft oder ihre Niederlassungen bleiben für alle Entscheidungen im Zusammenhang mit der Überwachung, Durchsetzung, Sperrung, Entfernung und Aufbewahrung von Inhalten, die von einer vorab ausgebildeten Klassifizierung identifiziert werden, verantwortlich.

#### <a name="process-flow-for-using-built-in-classifiers"></a>Prozessablauf für die Verwendung integrierter Klassifizierungen

Integrierte Klassifizierungen müssen nicht geschult werden, Sie müssen jedoch sicherstellen, dass Sie die Inhaltstypen identifizieren, die Sie benötigen, bevor Sie Sie in Compliance-Lösungen verwenden können. Das Testen einer vorab ausgebildeten Klassifizierung folgt diesem Fluss.

![Prozessfluss Test einer vorab ausgebildeten Klassifizierung](../media/classifier-pre-trained-classifier-flow.png)

### <a name="understanding-trainable-classifiers"></a>Grundlegendes zu Schulungs Klassifizierern

Wenn die integrierten Klassifizierungen nicht Ihren Anforderungen entsprechen, können Sie eigene Klassifizierungen erstellen und Schulen. Es gibt wesentlich mehr Arbeit bei der Erstellung Ihrer eigenen, aber Sie werden viel besser auf ihre Organisationen zugeschnitten werden muss. Weitere Informationen zur Verwendung einer vorgeschulten Klassifizierung finden Sie unter [using a built-in Klassifizierer](classifier-using-a-ready-to-use-classifier.md)

> [!IMPORTANT]
> Nur der Benutzer, der eine schulungsable-Klassifizierung erstellt, kann vorhersagen, die von dieser Klassifizierung vorgenommen werden, trainieren und überprüfen.

#### <a name="process-flow-for-creating-trainable-classifiers"></a>Prozessablauf zum Erstellen von Schulungs Klassifizierern

Das Erstellen und Veröffentlichen einer Schulungs Klassifizierer zur Verwendung in Compliance-Lösungen wie Aufbewahrungsrichtlinien und Kommunikationsüberwachung folgt diesem Fluss. Weitere Informationen zum Erstellen einer lernbaren Klassifizierung finden Sie unter [Creating a trainable Klassifizierer](classifier-creating-a-trainable-classifier.md).

![Prozessablauf-schulungsable-Klassifizierung](../media/classifier-trainable-classifier-flow.png)

## <a name="see-also"></a>Siehe auch


- [Aufbewahrungsbezeichnungen](retention.md)
- [Verhinderung von Datenverlust (DLP)](data-loss-prevention-policies.md)
- [Vertraulichkeitsbezeichnungen](sensitivity-labels.md)
- [Entitätsdefinitionen für Typen vertraulicher Informationen](sensitive-information-type-entity-definitions.md)
- [Dokumentieren des Finger Drucks](document-fingerprinting.md)
- [Exakte Datenübereinstimmung](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
