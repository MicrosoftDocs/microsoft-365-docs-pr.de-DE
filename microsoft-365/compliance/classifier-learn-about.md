---
title: Weitere Informationen zu trainierbaren Klassifizierern
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
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Ein Microsoft 365 trainierbarer Klassifikator ist ein Tool, das Sie trainieren können, um verschiedene Arten von Inhalten zu erkennen, indem Sie ihm positive und negative Beispiele zum Betrachten geben. Sobald der Klassifizierer geschult wurde, bestätigen Sie, dass die Ergebnisse korrekt sind. Anschließend verwenden Sie es, um die Inhalte Ihrer Organisation zu durchsuchen und zu klassifizieren, um Aufbewahrungs- oder Vertraulichkeitsbezeichnungen anzuwenden oder sie in Die Verhinderung von Datenverlust (Data Loss Prevention, DLP) oder Aufbewahrungsrichtlinien einzubehalten.
ms.openlocfilehash: 1881e4de87fd41f21bb1f2236d46391b3a1ed785
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114051"
---
# <a name="learn-about-trainable-classifiers"></a>Weitere Informationen zu trainierbaren Klassifizierern

Die Klassifizierung und Bezeichnung von Inhalten, damit sie geschützt und ordnungsgemäß behandelt werden können, ist der Ausgangspunkt für die Informationsschutz-Disziplin. Microsoft 365 bietet drei Möglichkeiten zum Klassifizieren von Inhalten.

## <a name="manually"></a>Manuell

Diese Methode erfordert menschliches Urteilsvermögen und Handeln. Ein Administrator kann entweder die bereits vorhandenen Bezeichnungen und Typen vertraulicher Informationen verwenden oder eigene erstellen und diese dann veröffentlichen. Benutzer und Administratoren wenden sie auf Inhalte an, wenn sie auf sie stoßen. Anschließend können Sie den Inhalt schützen und dessen Disposition verwalten.

## <a name="automated-pattern-matching"></a>Automatisierte Musterabgleich

Diese Kategorie von Klassifizierungsmechanismen umfasst die Suche nach Inhalten nach:

- Schlüsselwörter oder Metadatenwerte (Stichwortabfragesprache).
- Verwenden zuvor identifizierter Muster vertraulicher Informationen wie z. B. Sozialversicherung, Kreditkarten- oder Bankkontonummern (Entitätsdefinitionen vom Typ ["Vertrauliche Informationen")](sensitive-information-type-entity-definitions.md).
- Erkennen eines Elements, da es sich um eine Variation auf einer Vorlage [(Dokumentfingerdruck) ist.](document-fingerprinting.md)
- Verwenden von exakten Zeichenfolgen [(genaue Daten übereinstimmend)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).

Vertraulichkeits- und Aufbewahrungsbezeichnungen können dann automatisch angewendet werden, um die Inhalte für die Verwendung in [Informationen](dlp-learn-about-dlp.md)zur Verhinderung von Datenverlust zur Verfügung zu stellen und die Polizei für [Aufbewahrungsbezeichnungen](apply-retention-labels-automatically.md)automatisch anzuwenden.

## <a name="classifiers"></a>Klassifizierungen

Diese Klassifizierungsmethode eignet sich besonders gut für Inhalte, die weder von den manuellen noch von automatisierten Mustervergleichsmethoden leicht identifiziert werden können. Bei dieser Klassifizierungsmethode geht es eher darum, einen Klassifizierer so zu trainieren, dass er ein Element anhand dessen identifiziert, was das Element ist, und nicht anhand von Elementen, die sich im Element befinden (Musterabgleich). Ein Klassifikator lernt, wie sie einen Inhaltstyp identifizieren, indem er sich Hunderte von Beispielen der Inhalte anschaut, die Sie für die Klassifizierung interessieren. Sie beginnen mit dem Einfüttern von Beispielen, die definitiv in der Kategorie sind. Nachdem sie diese verarbeitet haben, testen Sie sie, indem Sie ihm eine Mischung aus übereinstimmenden und nicht übereinstimmenden Beispielen geben. Der Klassifikator gibt dann Vorhersagen darüber ab, ob ein bestimmtes Element in die Kategorie fällt, die Sie erstellen. Anschließend bestätigen Sie die Ergebnisse und sortieren die wahren Positiven, echten Negativen, falsch positiven und falsch negativen Ergebnisse aus, um die Genauigkeit der Vorhersagen zu erhöhen. 

Wenn Sie den Klassifizierer veröffentlichen, sortiert er Elemente an Speicherorten wie SharePoint Online, Exchange und OneDrive und ordnet den Inhalt ein. Nachdem Sie den Klassifizierer veröffentlicht haben, können Sie ihn mithilfe eines Feedbackprozesses weiter schulen, der dem anfänglichen Schulungsvorgang ähnelt.

### <a name="where-you-can-use-trainable-classifiers"></a>Wo Sie trainierbare Klassifikatoren verwenden können
Sowohl integrierte Klassifikatoren als auch trainierbare Klassifikatoren sind als Bedingung für Office [autolabeling mit](apply-sensitivity-label-automatically.md)Vertraulichkeitsbezeichnungen, [](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) automatisch angewendete Aufbewahrungsbezeichnungsrichtlinie basierend auf einer Bedingung und in der Kommunikationskonformität [verfügbar.](communication-compliance.md) 

Vertraulichkeitsbezeichnungen können Klassifizierungen als Bedingungen verwenden. Weitere Informationen finden Sie unter [Apply a sensitivity label to content automatically](apply-sensitivity-label-automatically.md).

> [!IMPORTANT]
> Klassifizierungen funktionieren nur mit Elementen, die nicht verschlüsselt sind und auf Englisch sind.

## <a name="types-of-classifiers"></a>Typen von Klassifizierungen

- **vorab geschulte Klassifikatoren** – Microsoft hat eine Reihe von Klassifizierungen erstellt und vortrainiert, die Sie verwenden können, ohne sie zu trainieren. Diese Klassifizierungen werden mit dem Status `Ready to use` angezeigt.
- **Benutzerdefinierte Klassifikatoren** – Wenn Sie Klassifizierungsanforderungen haben, die über das hinausgehen, was die vordefinierten Klassifizierungen abdecken, können Sie Eigene Klassifikatoren erstellen und schulen.

### <a name="pre-trained-classifiers"></a>Vortrainierte Klassifikatoren

Microsoft 365 verfügt über fünf vordefinierte Klassifikatoren:

> [!CAUTION]
> Der vortrainierte Klassifikator Anstößige Sprache wird veraltet, da er eine hohe Anzahl falsch positiver Ergebnisse erzeugt hat.  Verwenden Sie es nicht, und wenn Sie es derzeit verwenden, sollten Sie Ihre Geschäftsprozesse davon abziehen. Es wird empfohlen, stattdessen die Klassifikatoren **Threat,** **Profanity** und **Harassment** zu verwenden.

- **Resumes**: erkennt Elemente, bei denen es sich um Textkonten der persönlichen, bildungsbezogenen, beruflichen Qualifikationen, Arbeitserfahrungen und anderer persönlich identifizierenden Informationen eines Antragstellers handelt.
- **Quellcode**: erkennt Elemente, die eine Reihe von Anweisungen und Anweisungen enthalten, die in den 25 am meisten verwendeten Computerprogrammiersprachen auf GitHub
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
    - Swift
    - Tex
    - Vim-Skript

> [!NOTE]
> Der Quellcode wird geschult, um zu erkennen, ob der Großteil des Texts Quellcode ist. Es erkennt keinen Quellcodetext, der mit Nur-Text durchsperrt ist.

- **Belästigung**: Erkennt eine bestimmte Kategorie von anstößigen Sprachtextelementen im Zusammenhang mit anstößigem Verhalten, das auf eine oder mehrere Personen ausgerichtet ist, basierend auf den folgenden Merkmalen: Rasse, Ethnischer Zugehörigkeit, Religiöser, nationaler Ursprung, Geschlecht, sexuelle Ausrichtung, Alter, Behinderung
- **Profanity**: Erkennt eine bestimmte Kategorie von anstößigen Sprachtextelementen, die Ausdrücke enthalten, die die meisten Personen in Verlegenheit setzen
- **Bedrohung**: erkennt eine bestimmte Kategorie anstößiger Sprachtextelemente im Zusammenhang mit Bedrohungen, um Gewalt zu begehen oder physischen Schaden an einer Person oder Eigenschaft zu verursachen.

Diese werden in der Ansicht **Microsoft 365 Compliance Center**  >  **Datenklassifizierung**  >  **Trainierbare Klassifizierungen** mit dem Status `Ready to use` angezeigt.

![classifiers-pre-trained-classifiers](../media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> Bitte beachten Sie, dass die anstößigen Sprach-, Schikanen-, Profanitäts- und Bedrohungsklassifikatoren nur mit durchsuchbarem Text funktionieren, nicht vollständig oder vollständig sind.  Darüber hinaus ändern sich die Sprach- und Kulturstandards ständig, und angesichts dieser Realität behält sich Microsoft das Recht vor, diese Klassifizierungen nach eigenem Ermessen zu aktualisieren. Während die Klassifizierungen Ihre Organisation bei der Überwachung von Anstößigen und anderen verwendeten Sprachen unterstützen können, gehen die Klassifikatoren nicht auf die Folgen einer solchen Sprache ein und sind nicht dafür vorgesehen, die alleinigen Mittel ihrer Organisation zur Überwachung oder Reaktion auf die Verwendung dieser Sprache zur Verfügung zu stellen. Ihre Organisation und nicht Microsoft oder seine Tochtergesellschaften sind weiterhin für alle Entscheidungen im Zusammenhang mit der Überwachung, Durchsetzung, Blockierung, Entfernung und Aufbewahrung von Inhalten verantwortlich, die von einem vortrainierten Klassifikator identifiziert werden.

### <a name="custom-classifiers"></a>Benutzerdefinierte Klassifizierungen

Wenn die vordefinierten Klassifikatoren Ihre Anforderungen nicht erfüllen, können Sie Ihre eigenen Klassifizierungen erstellen und schulen. Es ist wesentlich mehr Arbeit an der Erstellung Eigener beteiligt, aber sie sind viel besser auf Die Anforderungen Ihrer Organisation zugeschnitten. 

Sie können z. B. trainierbare Klassifikatoren für folgende Informationen erstellen:
 
- Rechtliche Dokumente – z. B. Anwalts-Clientrechte, Schließende Sätze, Arbeitsanweisung
- Strategische Geschäftsdokumente – wie Pressemitteilungen, Fusionen und Übernahmen, Deals, Geschäfts- oder Marketingpläne, geistiges Eigentum, Patente, Entwurfsdokumente
- Preisinformationen – wie Rechnungen, Preisangebote, Arbeitsaufträge, Bietdokumente 
- Finanzinformationen – z. B. Unternehmensinvestitionen, Quartals- oder Jahresergebnisse    

#### <a name="process-flow-for-creating-custom-classifiers"></a>Prozessablauf zum Erstellen benutzerdefinierter Klassifikatoren

Das Erstellen und Veröffentlichen eines Klassifizierer für die Verwendung in Compliancelösungen, z. B. Aufbewahrungsrichtlinien und Kommunikationsüberwachung, folgt diesem Fluss. Weitere Informationen zum Erstellen eines benutzerdefinierten trainierbaren Klassifikierers finden Sie unter [Creating a custom classifier](classifier-get-started-with.md).

![benutzerdefinierter Klassifikator für Prozessfluss](../media/classifier-trainable-classifier-flow.png)

### <a name="retraining-classifiers"></a>Umschulung von Klassifizierungen

Sie können dazu beitragen, die Genauigkeit aller benutzerdefinierten Klassifikatoren und einiger vordefinierter Klassifizierungen zu verbessern, indem Sie ihnen Feedback zur Genauigkeit der von ihnen durchzuführenden Klassifizierung geben. Dies wird als Umschulung bezeichnet und folgt diesem Workflow.

![Klassifizierer-Umschulungsworkflow](../media/classifier-retraining-workflow.png)

## <a name="see-also"></a>Siehe auch

- [Aufbewahrungsbezeichnungen](retention.md)
- [Informationen zur Verhinderung von Datenverlust](dlp-learn-about-dlp.md)
- [Vertraulichkeitsbezeichnungen](sensitivity-labels.md)
- [Entitätsdefinitionen für Typen vertraulicher Informationen](sensitive-information-type-entity-definitions.md)
- [Drucken von Dokumentenfingern](document-fingerprinting.md)
- [Genaue Übereinstimmung der Daten](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
