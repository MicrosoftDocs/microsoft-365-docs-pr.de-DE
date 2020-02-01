---
title: Erste Schritte mit lernbaren Klassifizierungen (Vorschau)
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
ms.openlocfilehash: 4b4bfa996b1f68f9db8c206aaaec43878abf3f42
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595902"
---
# <a name="getting-started-with-trainable-classifiers-preview"></a>Erste Schritte mit lernbaren Klassifizierungen (Vorschau)

Das klassifizieren und kennzeichnen von Inhalten, damit es geschützt und ordnungsgemäß behandelt werden kann, ist der Ausgangspunkt für die Informationsschutz Disziplin. Microsoft 365 verfügt über drei Möglichkeiten zum Klassifizieren von Inhalten.

## <a name="manually"></a>Manuell

Für diese Methode ist menschliches Urteilen und Handeln erforderlich. Ein Administrator kann entweder die bereits vorhandenen Bezeichnungen und Typen vertraulicher Informationen verwenden oder eigene erstellen und diese dann veröffentlichen. Benutzer und Administratoren wenden diese auf Inhalte an, wenn Sie darauf stoßen. Anschließend können Sie den Inhalt schützen und seine Disposition verwalten.

## <a name="automated-pattern-matching"></a>Automatischer Musterabgleich

Diese Kategorie von Klassifizierungsmechanismen umfasst das Auffinden von Inhalten nach folgenden Themen:

- Schlüsselwörter oder Metadatenwerte (Stichwortabfrage Sprache)
- verwenden zuvor identifizierter Muster vertraulicher Informationen wie soziale Sicherheit, Kreditkarten-oder Bank Kontonummern [(vertrauliche Informationstypen)](what-the-sensitive-information-types-look-for.md)
- Erkennen eines Elements, da es sich um eine Variation einer Vorlage handelt [(Dokumentieren des Finger Drucks)](document-fingerprinting.md)
- Verwenden des Vorhandenseins exakter Zeichenfolgen [(exakte Datenübereinstimmung)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).

Vertraulichkeits-und Aufbewahrungs Bezeichnungen können dann automatisch angewendet werden, um die Inhalte für die Verwendung in [DLP (Data Loss Prevention)](data-loss-prevention-policies.md) und [Aufbewahrungsrichtlinien](retention-policies.md)zur Verfügung zu stellen.

## <a name="trainable-classifiers"></a>Schulungs Klassifizierer

Diese Klassifizierungsmethode eignet sich besonders gut für Inhalte, die nicht einfach durch die manuellen oder automatisierten Mustervergleichsmethoden identifiziert werden können. Bei dieser Klassifizierungsmethode geht es um die Schulung einer Klassifizierung, um ein Element basierend auf dem Element zu identifizieren, nicht durch Elemente, die sich im Element befinden (Mustervergleich). Eine Klassifizierung zeigt, wie Sie einen Inhaltstyp identifizieren, indem Sie sich Hunderte Beispiele für die Inhalte ansehen, die Sie bei der Klassifizierung interessieren. Sie beginnen mit dem Füttern von IT-Beispielen, die definitiv in der Kategorie sind. Nachdem diese verarbeitet wurden, testen Sie Sie, indem Sie eine Kombination aus sowohl passenden als auch nicht passenden Beispielen zuweisen. Die Klassifizierung legt dann Vorhersagen fest, ob ein bestimmtes Element in die Kategorie fällt, die Sie erstellen. Anschließend bestätigen Sie die Ergebnisse, sortieren die positiven, negativen, falsch positiven und falschen negative, um die Genauigkeit der Vorhersagen zu verbessern. Wenn Sie die geschulte Klassifizierung veröffentlichen, werden Elemente an Speicherorten wie SharePoint Online, Exchange und OneDrive sortiert, und der Inhalt wird klassifiziert.

> [!IMPORTANT]
> Beide Typen von Klassifizierungen stehen als Bedingung für die [automatische Anwendung von Aufbewahrungs Bezeichnungsrichtlinien basierend auf einer Bedingungs-](labels.md#applying-a-retention-label-automatically-based-on-conditions) und [Kommunikations Konformität](communication-compliance.md)zur Verfügung.

> [!IMPORTANT]
> Schulungs fähige Klassifizierungen funktionieren nur mit Elementen, die nicht verschlüsselt sind und sich in Englisch befinden.

## <a name="types-of-classifiers"></a>Typen von Klassifizierungen

Sie können Klassifizierungen und Schulungs fähige Klassifizierungen verwenden. Das Einholen einer lernbaren Klassifizierung in einen Veröffentlichungszustand erfordert eine Zeitinvestition für die Schulung. Für die ersten Schritte bei der Verwendung von Klassifizierungen ist Microsoft 365 mit einigen einsatzfähigen Klassifizierungen ausgestattet.

> [!NOTE]
> Bevor Sie die Klassifizierung in Ihrem Klassifikations-und Beschriftungs Workflow verwenden, sollten Sie Sie anhand eines Beispiels ihrer organisationsinhalte testen, das Ihrer Meinung nach der Kategorie entspricht, um zu überprüfen, ob Ihre Klassifizierungs Vorhersagen Ihren Erwartungen entsprechen.

### <a name="understanding-ready-to-use-classifiers"></a>Grundlegendes zu verwendungsfähigen Klassifizierungen

Microsoft 365 ist mit sechs einsatzfähigen Klassifizierungen ausgestattet:

- **Anstößige Sprache**: erkennt Textelemente, die Profanität, Beleidigungen, verspottungen und verschleierte Ausdrücke enthalten (bei denen es sich um Ausdrücke handelt, die die gleiche Bedeutung wie ein beleidigender Ausdruck haben).
- **Lebensläufe**: erkennt Elemente, bei denen es sich um Text Konten für persönliche, pädagogische, berufliche Qualifikationen, Berufserfahrung und andere personenbezogene Informationen handelt.
- **Sourcecode**: erkennt Elemente, die eine Reihe von Anweisungen und Anweisungen enthalten, die in weit verbreiteten Programmiersprachen für Computer geschrieben wurden.
- **Belästigung**: erkennt eine bestimmte Kategorie von Textelementen anstößiger Sprache im Zusammenhang mit anstößigem Verhalten, das auf eine oder mehrere Personen basierend auf den folgenden Merkmalen ausgerichtet ist: Rasse, Ethnizität, Religion, nationale Herkunft, Geschlecht, sexuelle Orientierung, Alter, Behinderung.
- **Profanity**: erkennt eine bestimmte Kategorie von Textelementen anstößiger Sprache, die Ausdrücke enthalten, die die meisten Personen in Verlegenheit bringen.
- **Threat**: erkennt eine bestimmte Kategorie von Textelementen anstößiger Sprache im Zusammenhang mit Bedrohungen, um Gewalt zu begehen oder physischen Schaden oder einer Person oder einer Eigenschaft zu Schaden.

Diese werden in der Ansicht " **Microsoft 365 Compliance Center** > **-Datenklassifizierung (Preview)** > "**trainable Klassifizierers** " `Ready to use`mit dem Status" angezeigt.

![Klassifizierungen – einsatzfertige Klassifizierungen](media/classifiers-ready-to-use-classifiers.png)

> [!IMPORTANT]
> Bitte beachten Sie, dass die beleidigende Sprache, Belästigung, Profanität und Bedrohungs Klassifizierungen nur mit durchsuchbarem Text funktionieren, die nicht erschöpfend oder vollständig sind.  Außerdem ändern sich die Sprach-und Kulturstandards ständig, und in Anbetracht dieser Gegebenheiten behält sich Microsoft das Recht vor, diese Klassifizierungen nach eigenem Ermessen zu aktualisieren. Während die Klassifizierungen Ihre Organisation bei der Überwachung von anstößigen und anderen Sprachen unterstützen können, befassen sich die Klassifizierungsverfahren nicht mit den Folgen dieser Sprache und dienen nicht dazu, die alleinigen Möglichkeiten Ihrer Organisation zur Überwachung oder Reaktion auf die Verwendung von zu bieten. solche Sprache. Ihre Organisation und nicht Microsoft oder ihre Niederlassungen bleiben für alle Entscheidungen im Zusammenhang mit der Überwachung, Durchsetzung, Sperrung, Entfernung und Aufbewahrung von Inhalten, die von einer vorab ausgebildeten Klassifizierung identifiziert werden, verantwortlich.

#### <a name="process-flow-for-using-ready-to-use-classifiers"></a>Prozessablauf für die Verwendung von Klassifizierungen bereit

Bereit für die Verwendung von Klassifizierungen müssen Sie nicht geschult werden, Sie müssen jedoch sicherstellen, dass Sie die Inhaltstypen identifizieren, die Sie benötigen, bevor Sie Sie in Compliance-Lösungen verwenden können. Das Testen einer vorab ausgebildeten Klassifizierung folgt diesem Fluss.

![Prozessfluss Test einer vorab ausgebildeten Klassifizierung](media/classifier-pre-trained-classifier-flow.png)

### <a name="understanding-trainable-classifiers"></a>Grundlegendes zu Schulungs Klassifizierern

Wenn die verwendungsfähigen Klassifizierungen nicht Ihren Anforderungen entsprechen, können Sie eigene Klassifizierungen erstellen und Schulen. Es gibt wesentlich mehr Arbeit bei der Erstellung Ihrer eigenen, aber Sie werden viel besser auf ihre Organisationen zugeschnitten werden muss. Weitere Informationen zur Verwendung einer vorgeschulten Klassifizierung finden Sie unter [using a ready to use Klassifizierer](classifier-using-a-ready-to-use-classifier.md)

> [!IMPORTANT]
> Nur der Benutzer, der eine schulungsable-Klassifizierung erstellt, kann vorhersagen, die von dieser Klassifizierung vorgenommen werden, trainieren und überprüfen.

#### <a name="process-flow-for-creating-trainable-classifiers"></a>Prozessablauf zum Erstellen von Schulungs Klassifizierern

Das Erstellen und Veröffentlichen einer Schulungs Klassifizierer zur Verwendung in Compliance-Lösungen wie Aufbewahrungsrichtlinien und Kommunikationsüberwachung folgt diesem Fluss. Weitere Informationen zum Erstellen einer lernbaren Klassifizierung finden Sie unter [Creating a trainable Klassifizierer](classifier-creating-a-trainable-classifier.md).

![Prozessablauf-schulungsable-Klassifizierung](media/classifier-trainable-classifier-flow.png)

## <a name="see-also"></a>Siehe auch

- [Aufbewahrungs Bezeichnungen](labels.md)
- [Aufbewahrungsrichtlinien](retention-policies.md)
- [Verhinderung von Datenverlust (DLP)](data-loss-prevention-policies.md)
- [Vertraulichkeits Bezeichnungen](sensitivity-labels.md)
- [Typen vertraulicher Informationen](what-the-sensitive-information-types-look-for.md)
- [Dokumentieren des Finger Drucks](document-fingerprinting.md)
- [exakte Datenübereinstimmung](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)
