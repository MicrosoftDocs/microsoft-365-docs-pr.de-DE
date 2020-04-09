---
title: Verwenden einer integrierten Klassifizierung (Vorschau)
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
description: Microsoft 365 enthält eine Reihe integrierter Klassifizierungen, die Sie zum Identifizieren und Beschriften von Inhalten in Ihrer Organisation verwenden können. In diesem Thema wird gezeigt, wie Sie die Verwendung dieser Klassifizierungen vorbereiten.
ms.openlocfilehash: 2bd36ac42278cfe7b015d03caf2d9e1958908f8f
ms.sourcegitcommit: 13f28aa762e467bab8ab1e95e1917b3ac28931da
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2020
ms.locfileid: "43193503"
---
# <a name="using-a-built-in-classifier-preview"></a>Verwenden einer integrierten Klassifizierung (Vorschau)

Microsoft hat fünf Klassifizierungen mit sehr großen Beispieldatensätzen ausgebildet und getestet, um bestimmte Inhaltskategorien identifizieren zu können. Weitere Informationen finden Sie unter [Erste Schritte mit Schulungs Klassifizierern (Vorschau)](classifier-getting-started-with.md). Diese Klassifizierungen werden standardmäßig in `Ready to use` der Gruppe angezeigt.

Microsoft 365 verfügt über fünf Empfohlene integrierte Klassifizierungen:

> [!CAUTION]
> Wir veraltern die integrierte Klassifizierung der **offensiven Sprache** , da Sie eine hohe Anzahl falsch positiver Ergebnisse erzeugt. Verwenden Sie es nicht, und wenn Sie es derzeit verwenden, sollten Sie Ihre Geschäftsprozesse aus dieser entfernen. Es wird empfohlen, stattdessen die integrierten Klassifizierungen " **Bedrohung**", " **Profanität**" und " **Belästigung** " zu verwenden.

- **Lebensläufe**: erkennt Elemente, bei denen es sich um Text Konten für persönliche, pädagogische, berufliche Qualifikationen, Berufserfahrung und andere personenbezogene Informationen handelt.
- **Quellcode**: erkennt Elemente, die eine Reihe von Anweisungen und Anweisungen enthalten, die in den Top 25 verwendeten Computer Programmiersprachen auf GitHub geschrieben wurden.

|Name der Sprache|||||
|---------|---------|---------|---------|---------|
|ActionScript|C        |C #       |C++     |Clojure  |
|CoffeeScript|CSS     |OK       |Haskell |HTML     |
|Java     |JavaScript|Lua      |MATLAB   |Objective-C|
|Perl     |PHP      |Python   |R        |Ruby     |
|Scala    |Shell    |SWIFT    |Tex      |Vim-Skript|

- **Belästigung**: erkennt eine bestimmte Kategorie von Textelementen anstößiger Sprache im Zusammenhang mit anstößigem Verhalten, das auf eine oder mehrere Personen basierend auf den folgenden Merkmalen ausgerichtet ist: Rasse, Ethnizität, Religion, nationale Herkunft, Geschlecht, sexuelle Orientierung, Alter, Behinderung.
- **Profanity**: erkennt eine bestimmte Kategorie von Textelementen anstößiger Sprache, die Ausdrücke enthalten, die die meisten Personen in Verlegenheit bringen.
- **Threat**: erkennt eine bestimmte Kategorie von Textelementen anstößiger Sprache im Zusammenhang mit Bedrohungen, um Gewalt zu begehen oder physischen Schaden oder einer Person oder einer Eigenschaft zu Schaden;

> [!NOTE]
> Bevor Sie integrierte Klassifizierungen in Ihrem Klassifikations-und Bezeichnungs Workflow verwenden, sollten Sie Sie anhand eines Beispiels für die Inhalte Ihrer Organisation testen, das Ihrer Meinung nach der Kategorie entspricht, um sicherzustellen, dass Ihre Klassifizierungs Vorhersagen Ihren Erwartungen entsprechen.

> [!IMPORTANT]
> Bitte beachten Sie, dass die beleidigende Sprache, Belästigung, Profanität und Bedrohungs Klassifizierungen nur mit durchsuchbarem Text funktionieren, die nicht erschöpfend oder vollständig sind. Außerdem ändern sich die Sprach-und Kulturstandards ständig, und in Anbetracht dieser Gegebenheiten behält sich Microsoft das Recht vor, diese Klassifizierungen nach eigenem Ermessen zu aktualisieren. Während die Klassifizierungen Ihre Organisation bei der Überwachung von anstößigen und anderen Sprachen unterstützen können, befassen sich die Klassifizierungsverfahren nicht mit den Konsequenzen dieser Sprache und dienen nicht dazu, die Verwendung dieser Sprache allein zu überwachen oder zu beantworten. Ihre Organisation und nicht Microsoft oder ihre Niederlassungen bleiben für alle Entscheidungen im Zusammenhang mit der Überwachung, Durchsetzung, Sperrung, Entfernung und Aufbewahrung von Inhalten, die von einer vorab ausgebildeten Klassifizierung identifiziert werden, verantwortlich.

## <a name="how-to-prepare-for-and-use-a-built-in-classifier"></a>Vorgehensweise vorbereiten und Verwenden einer integrierten Klassifizierung

1. Sammeln Sie Inhaltselemente für den verfügbaren Test, die Sie in die Kategorie der integrierten Klassifizierung (positive Übereinstimmungen) und diejenigen, die nicht berücksichtigt werden sollten (negative Übereinstimmungen) in der Kategorie, die Sie testen, gehören.

> [!IMPORTANT]
> Die Beispielelemente dürfen nicht verschlüsselt werden und müssen in Englisch sein.

2. Erstellen eines dedizierten SharePoint Online Ordners; warten Sie mindestens eine Stunde, bis der Ordner dem Suchindex hinzugefügt wurde. Notieren Sie sich die Ordner-URL.

3. Melden Sie sich bei Microsoft 365 Compliance Center mit Compliance Admin oder Security Admin Role Access an, und öffnen Sie **Microsoft 365 Compliance Center** > **Records Management (Preview)** > **Label Policies** Tab.

4. Wählen `Auto-apply a label`Sie aus.

5. Wählen `Choose a label to auto-apply`Sie aus.

6. Wählen `Create new labels` Sie und erstellen Sie eine Bezeichnung für die Verwendung nur mit diesem Test. Wenn Sie dies tun, lassen `Retention` Sie die Einstellung aus. Sie möchten keine Aufbewahrung oder andere Aktionen aktivieren. In diesem Fall verwenden Sie die Aufbewahrungs Bezeichnung einfach als Textbeschriftung, ohne dass Aktionen erzwungen werden. Sie können beispielsweise eine Aufbewahrungs Bezeichnung mit dem Namen "Sourcecode-Klassifizierungs Test" ohne Aktionen erstellen und diese Aufbewahrungs Bezeichnung automatisch auf Inhalte anwenden, für die die Quell Code Klassifizierung als Bedingung verwendet wird. Weitere Informationen zum Erstellen von Aufbewahrungs Bezeichnungen finden Sie unter [Overview of Retention Labels](labels.md).
  
7. Wählen `Auto-apply a label` Sie und `Choose a label to auto-apply`dann aus. Weitere Informationen zur Verwendung von Condition Based Auto-Apply a Label finden Sie unter [Automatisches Anwenden von Aufbewahrungs Bezeichnungsrichtlinien basierend auf einer Bedingung](labels.md#applying-a-retention-label-automatically-based-on-conditions).

8. Wählen Sie Ihre Test Bezeichnung in der Liste aus `Next`, und wählen Sie aus.

9. Wählen `Apply label to content that matches a trainable classifier`Sie aus.

![Auswählen der Klassifizierung als Bedingung](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png).

10. Wählen Sie Ihre Klassifizierung aus der Liste aus, in diesem Fall`Source Code`

11. Nennen Sie die Richtlinie, beispielsweise "Quellcode-integrierter Klassifizierungs Test".

12. Wählen `Let me choose specific locations`Sie aus.

13. Deaktivieren Sie alle Speicherorte `SharePoint sites` , außer `Choose sites`und wählen Sie.

14. Geben Sie in Schritt 2 die URL für die Website ein.

15. Beenden Sie den Assistenten, und wählen Sie`Auto-apply`

16. Platzieren Sie die Testelemente in den Ordner dedizierter SharePoint Online.

17. Lassen Sie eine Stunde für die Anwendung der Bezeichnung zu.

18. Überprüfen Sie die Eigenschaften der Dokumente für die Bezeichnung, um festzustellen, ob die Klassifizierung den Testinhalt wie erwartet enthielt und ausschloß.

19. Überprüfen Sie die Elemente, die beschriftet wurden.

20. Löschen Sie den Inhalt und die Bezeichnungsrichtlinie, wenn Sie mit Ihren Tests fertig sind.

Siehe auch:

- [Erste Schritte mit lernbaren Klassifizierungen (Vorschau)](classifier-getting-started-with.md)
- [Übersicht über Aufbewahrungsbezeichnungen](labels.md)
- [Automatisches Anwenden von Aufbewahrungs Bezeichnungsrichtlinien basierend auf einer Bedingung](labels.md#applying-a-retention-label-automatically-based-on-conditions)
