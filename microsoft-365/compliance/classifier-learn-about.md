---
title: Weitere Informationen zu trainierbaren Klassifizierern (Vorschau)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Eine Microsoft 365-schulungsable-Klassifizierung ist ein Tool, mit dem Sie verschiedene Arten von Inhalten erkennen können, indem Sie positive und negative Beispiele für Ihre Untersuchung geben. Nach der Schulung der Klassifizierung bestätigen Sie, dass die Ergebnisse korrekt sind. Anschließend können Sie die Inhalte Ihrer Organisation durchsuchen und klassifizieren, um Aufbewahrungs-oder Vertraulichkeits Bezeichnungen anzuwenden oder Sie in Datenverlust Verhinderung (DLP) oder in Aufbewahrungsrichtlinien einzubeziehen.
ms.openlocfilehash: 8b086690faba23e1331e02d8844503c44e7617c0
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2020
ms.locfileid: "48322188"
---
# <a name="learn-about-classifiers-preview"></a>Informationen zu Klassifizierungen (Vorschau)

Das klassifizieren und kennzeichnen von Inhalten, damit es geschützt und ordnungsgemäß behandelt werden kann, ist der Ausgangspunkt für die Informationsschutz Disziplin. Microsoft 365 verfügt über drei Möglichkeiten zum Klassifizieren von Inhalten.

## <a name="manually"></a>Manuell

Für diese Methode ist menschliches Urteilen und Handeln erforderlich. Ein Administrator kann entweder die bereits vorhandenen Bezeichnungen und Typen vertraulicher Informationen verwenden oder eigene erstellen und diese dann veröffentlichen. Benutzer und Administratoren wenden diese auf Inhalte an, wenn Sie darauf stoßen. Anschließend können Sie den Inhalt schützen und seine Disposition verwalten.

## <a name="automated-pattern-matching"></a>Automatischer Musterabgleich

Diese Kategorie von Klassifizierungsmechanismen umfasst die Suche nach Inhalten nach folgenden Themen:

- Schlüsselwörter oder Metadatenwerte (Stichwortabfrage Sprache).
- Verwenden zuvor identifizierter Muster vertraulicher Informationen wie soziale Sicherheit, Kreditkarten-oder Bank Kontonummern [(vertrauliche Informationstypen – Entitätsdefinitionen)](sensitive-information-type-entity-definitions.md).
- Erkennen eines Elements, da es sich um eine Variation einer Vorlage handelt [(Dokumentieren des Finger Drucks)](document-fingerprinting.md).
- Verwenden des Vorhandenseins exakter Zeichenfolgen [(exakte Datenübereinstimmung)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).

Sensitivitäts-und Aufbewahrungs Bezeichnungen können dann automatisch angewendet werden, um die Inhalte für die Verwendung in [Datenverlust Verhinderung (DLP)](data-loss-prevention-policies.md) und [automatisch anwenden von Policen für Aufbewahrungs Bezeichnungen](apply-retention-labels-automatically.md)verfügbar zu machen.

## <a name="classifiers"></a>Klassifizierungen

Diese Klassifizierungsmethode eignet sich besonders gut für Inhalte, die nicht einfach durch die manuellen oder automatisierten Mustervergleichsmethoden identifiziert werden können. Bei dieser Klassifizierungsmethode geht es eher darum, einen Klassifizierer so zu trainieren, dass er ein Element anhand dessen identifiziert, was das Element ist, und nicht anhand von Elementen, die sich im Element befinden (Musterabgleich). Eine Klassifizierung zeigt, wie Sie einen Inhaltstyp identifizieren, indem Sie sich Hunderte Beispiele für die Inhalte ansehen, die Sie bei der Klassifizierung interessieren. Sie beginnen mit dem Füttern von IT-Beispielen, die definitiv in der Kategorie sind. Nachdem diese verarbeitet wurden, testen Sie Sie, indem Sie eine Kombination aus sowohl passenden als auch nicht passenden Beispielen zuweisen. Die Klassifizierung legt dann Vorhersagen fest, ob ein bestimmtes Element in die Kategorie fällt, die Sie erstellen. Anschließend bestätigen Sie die Ergebnisse, sortieren die wahren positiven Werte, true negative, falsch positive Ergebnisse und falsche Negative, um die Genauigkeit der Vorhersagen zu verbessern. 

Wenn Sie die Klassifizierung veröffentlichen, werden Elemente an Speicherorten wie SharePoint Online, Exchange und OneDrive sortiert, und der Inhalt wird klassifiziert. Nachdem Sie die Klassifizierung veröffentlicht haben, können Sie Sie mit einem Feedbackprozess weiterbilden, der dem anfänglichen Schulungsprozess ähnelt.

### <a name="where-you-can-use-trainable-classifiers"></a>Wo Sie Schulungs Klassifizierer verwenden können
Sowohl integrierte Klassifizierungen als auch eingestufte Klassifizierungen stehen als Bedingung für die automatische [Kennzeichnung von Office mit Vertraulichkeits Bezeichnungen](apply-sensitivity-label-automatically.md), [automatisch angewendete Aufbewahrungs Bezeichnungsrichtlinie basierend auf einer Bedingung](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) und in der [Kommunikations Konformität](communication-compliance.md)zur Verfügung. 

Vertraulichkeits Bezeichnungen können Klassifizierungen als Bedingungen verwenden, siehe [Anwenden einer Vertraulichkeits Bezeichnung auf Inhalte automatisch](apply-sensitivity-label-automatically.md).

> [!IMPORTANT]
> Klassifizierungen funktionieren nur mit Elementen, die nicht verschlüsselt sind und sich in Englisch befinden.

## <a name="types-of-classifiers"></a>Typen von Klassifizierungen

- **vorab ausgebildete Klassifizierungen** – Microsoft hat eine Reihe von Klassifizierungen erstellt und vorab geschult, die Sie verwenden können, ohne Sie zu Schulen. Diese Klassifizierungen werden mit dem Status von angezeigt `Ready to use` .
- **benutzerdefinierte** Klassifizierungen – wenn Klassifizierungsanforderungen über das hinausgehen, was die vorgeschulten Klassifizierungen umfassen, können Sie eigene Klassifizierungen erstellen und Schulen.

### <a name="pre-trained-classifiers"></a>Vorab ausgebildete Klassifizierungen

Microsoft 365 verfügt über fünf vorab ausgebildete Klassifizierungen:

> [!CAUTION]
> Wir verwerfen die vorab ausgebildete Klassifizierung der **offensiven Sprache** , da Sie eine hohe Anzahl falsch positiver Ergebnisse erzeugt. Verwenden Sie es nicht, und wenn Sie es derzeit verwenden, sollten Sie Ihre Geschäftsprozesse aus dieser entfernen. Es wird empfohlen, stattdessen die vorab ausgebildeten Klassifizierungen " **Bedrohung**", " **Profanität**" und " **Belästigung** " zu verwenden.

- **Lebensläufe**: erkennt Elemente, bei denen es sich um Text Konten für persönliche, pädagogische, berufliche Qualifikationen, Berufserfahrung und andere personenbezogene Informationen handelt.
- **Quellcode**: erkennt Elemente, die eine Reihe von Anweisungen und Anweisungen enthalten, die in den Top 25 verwendeten Computer Programmiersprachen auf GitHub geschrieben wurden.
    - ActionScript
    - C
    - C#
    - C++
    - Clojure
    - CoffeeScript
    - OK
    - Haskell
    - Java
    - JavaScript
    - Lua
    - MATLAB
    - Objective-C
    - Perl
    - PHP
    - Python
    - R
    - Ruby
    - Scala
    - Shell
    - SWIFT
    - Tex
    - Vim-Skript

> [!NOTE]
> Der Quellcode wird geschult, um zu erkennen, wann der Hauptteil des Texts Quellcode ist. Es wird kein quellcodetext erkannt, der mit nur-Text vermischt wird.

- **Belästigung**: erkennt eine bestimmte Kategorie von Textelementen anstößiger Sprache im Zusammenhang mit anstößigem Verhalten, das auf eine oder mehrere Personen basierend auf den folgenden Merkmalen ausgerichtet ist: Rasse, Ethnizität, Religion, nationale Herkunft, Geschlecht, sexuelle Orientierung, Alter, Behinderung
- **Profanität**: erkennt eine bestimmte Kategorie von Textelementen anstößiger Sprache, die Ausdrücke enthalten, die die meisten Personen in Verlegenheit bringen
- **Threat**: erkennt eine bestimmte Kategorie von Textelementen anstößiger Sprache im Zusammenhang mit Bedrohungen, um Gewalt zu begehen oder physischen Schaden oder einer Person oder einer Eigenschaft zu Schaden

Diese werden in der Ansicht " **Microsoft 365 Compliance Center**  >  **-Datenklassifizierung (Preview)**"  >  **trainable Klassifizierers** "mit dem Status" angezeigt `Ready to use` .

![Klassifizierungen – vorab geschulte-Klassifizierungen](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> Bitte beachten Sie, dass die beleidigende Sprache, Belästigung, Profanität und Bedrohungs Klassifizierungen nur mit durchsuchbarem Text funktionieren, die nicht erschöpfend oder vollständig sind.  Außerdem ändern sich die Sprach-und Kulturstandards ständig, und in Anbetracht dieser Gegebenheiten behält sich Microsoft das Recht vor, diese Klassifizierungen nach eigenem Ermessen zu aktualisieren. Während die Klassifizierungen Ihre Organisation bei der Überwachung von anstößigen und anderen Sprachen unterstützen können, befassen sich die Klassifizierungsverfahren nicht mit den Konsequenzen dieser Sprache und dienen nicht dazu, die Verwendung dieser Sprache allein zu überwachen oder zu beantworten. Ihre Organisation und nicht Microsoft oder ihre Niederlassungen bleiben für alle Entscheidungen im Zusammenhang mit der Überwachung, Durchsetzung, Sperrung, Entfernung und Aufbewahrung von Inhalten, die von einer vorab ausgebildeten Klassifizierung identifiziert werden, verantwortlich.

### <a name="custom-classifiers"></a>Benutzerdefinierte Klassifizierungen

Wenn die vorab ausgebildeten Klassifizierungen nicht Ihren Anforderungen entsprechen, können Sie eigene Klassifizierungen erstellen und Schulen. Es gibt wesentlich mehr Arbeit bei der Erstellung Ihrer eigenen, aber Sie werden viel besser auf ihre Organisationen zugeschnitten werden muss.

> [!IMPORTANT]
> Standardmäßig kann nur der Benutzer, der eine benutzerdefinierte Klassifizierung erstellt, die von dieser Klassifizierung vorgenommenen Vorhersagen trainieren und überprüfen. Wenn andere Benutzer in der Lage sein sollen, Klassifizierungs Vorhersagen auszubilden und zu überprüfen, finden Sie weitere Informationen unter [Erteilen von Schulungs-und Überprüfungs rechten](classifier-get-started-with.md#give-others-train-and-review-rights).

#### <a name="process-flow-for-creating-custom-classifiers"></a>Prozessablauf zum Erstellen benutzerdefinierter Klassifizierungen

Das Erstellen und Veröffentlichen einer Klassifizierung für die Verwendung in Compliance-Lösungen wie Aufbewahrungsrichtlinien und Kommunikationsüberwachung folgt diesem Fluss. Weitere Informationen zum Erstellen einer benutzerdefinierten Klassifizierer-Klassifizierung finden Sie unter [Erstellen einer benutzerdefinierten Klassifizierung](classifier-get-started-with.md).

![benutzerdefinierte Prozessablauf Klassifizierung](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a>Umschulungs Klassifizierungen

Sie können die Genauigkeit aller benutzerdefinierten Klassifizierungen und einiger vorab ausgebildeter Klassifizierungen verbessern, indem Sie Ihnen Feedback zur Genauigkeit der von Ihnen durchgeführten Klassifizierung liefern. Dies wird als Umschulung bezeichnet und folgt diesem Workflow.

![Klassifizierungs Umschulungs Workflow](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a>Siehe auch

- [Aufbewahrungsbezeichnungen](retention.md)
- [Verhinderung von Datenverlust (DLP)](data-loss-prevention-policies.md)
- [Vertraulichkeitsbezeichnungen](sensitivity-labels.md)
- [Entitätsdefinitionen für Typen vertraulicher Informationen](sensitive-information-type-entity-definitions.md)
- [Dokumentieren des Finger Drucks](document-fingerprinting.md)
- [Exakte Datenübereinstimmung](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
