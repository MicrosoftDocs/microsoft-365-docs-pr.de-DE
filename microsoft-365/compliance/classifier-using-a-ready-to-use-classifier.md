---
title: Testen integrierter Klassifizierungen mithilfe von Aufbewahrungs Bezeichnungen (Vorschau)
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
ms.openlocfilehash: 2652df8d79b06d6614e2478843195e67de0a8ebb
ms.sourcegitcommit: 87eff6e8a08cec3cb0464a3b765434717584a4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/26/2020
ms.locfileid: "44371407"
---
# <a name="testing-built-in-classifiers-using-retention-labels-preview"></a>Testen integrierter Klassifizierungen mithilfe von Aufbewahrungs Bezeichnungen (Vorschau)

Microsoft hat fünf Klassifizierungen geschult und getestet, die bei der Identifizierung bestimmter Inhaltskategorien helfen können. Diese Klassifizierungen werden `Ready to use` standardmäßig in der Gruppe angezeigt und wurden mit sehr umfangreichen Beispieldatensätzen geschult.

> [!IMPORTANT]
> Bevor Sie integrierte Klassifizierungen in Ihrem Klassifikations-und Bezeichnungs Workflow verwenden, sollten Sie Sie anhand eines Beispiels für die Inhalte Ihrer Organisation testen, das Ihrer Meinung nach der Kategorie entspricht, um sicherzustellen, dass Ihre Klassifizierungs Vorhersagen Ihren Erwartungen entsprechen.

Weitere Informationen zu Schulungs Klassifizierern finden Sie unter [Erste Schritte mit Schulungs Klassifizierern (Preview)](classifier-getting-started-with.md).

Microsoft 365 verfügt über fünf Empfohlene integrierte Klassifizierungen:

> [!CAUTION]
> Die integrierte Klassifizierung **Anstößige Sprache** wird eingestellt, da sie eine große Anzahl falsch positiver Ergebnisse erzeugt hat. Verwenden Sie es nicht, und wenn Sie es derzeit verwenden, sollten Sie Ihre Geschäftsprozesse aus dieser entfernen. Es wird empfohlen, stattdessen die integrierten Klassifizierungen " **Bedrohung**", " **Profanität**" und " **Belästigung** " zu verwenden.

- **Lebensläufe**: erkennt Elemente, bei denen es sich um Text Konten für persönliche, pädagogische, berufliche Qualifikationen, Berufserfahrung und andere personenbezogene Informationen handelt.
- **Quellcode**: erkennt Elemente, die eine Reihe von Anweisungen und Anweisungen enthalten, die in den Top 25 verwendeten Computer Programmiersprachen auf GitHub geschrieben wurden.

  |Name der Sprache|||||
  |---------|---------|---------|---------|---------|
  |ActionScript|C        |C #       |C++     |Clojure  |
  |CoffeeScript|CSS     |OK       |Haskell |HTML     |
  |Java     |JavaScript|Lua      |MATLAB   |Objective-C|
  |Perl     |PHP      |Python   |R        |Ruby     |
  |Scala    |Shell    |SWIFT    |Tex      |Vim-Skript|

> [!NOTE]
> Der Quellcode wird geschult, um zu erkennen, wann der Hauptteil des Texts Quellcode ist. Es wird kein quellcodetext erkannt, der mit nur-Text vermischt wird.

- **Belästigung**: erkennt eine bestimmte Kategorie von Textelementen anstößiger Sprache im Zusammenhang mit anstößigem Verhalten, das auf eine oder mehrere Personen basierend auf den folgenden Merkmalen ausgerichtet ist: Rasse, Ethnizität, Religion, nationale Herkunft, Geschlecht, sexuelle Orientierung, Alter, Behinderung
- **Profanität**: erkennt eine bestimmte Kategorie von Textelementen anstößiger Sprache, die Ausdrücke enthalten, die die meisten Personen in Verlegenheit bringen
- **Threat**: erkennt eine bestimmte Kategorie von Textelementen anstößiger Sprache im Zusammenhang mit Bedrohungen, um Gewalt zu begehen oder physischen Schaden oder einer Person oder einer Eigenschaft zu Schaden

> [!IMPORTANT]
> Bitte beachten Sie, dass die beleidigende Sprache, Belästigung, Profanität und Bedrohungs Klassifizierungen nur mit durchsuchbarem Text funktionieren, die nicht erschöpfend oder vollständig sind. Außerdem ändern sich die Sprach-und Kulturstandards ständig, und in Anbetracht dieser Gegebenheiten behält sich Microsoft das Recht vor, diese Klassifizierungen nach eigenem Ermessen zu aktualisieren. Während die Klassifizierungen Ihre Organisation bei der Überwachung von anstößigen und anderen Sprachen unterstützen können, befassen sich die Klassifizierungsverfahren nicht mit den Konsequenzen dieser Sprache und dienen nicht dazu, die Verwendung dieser Sprache allein zu überwachen oder zu beantworten. Ihre Organisation und nicht Microsoft oder ihre Niederlassungen bleiben für alle Entscheidungen im Zusammenhang mit der Überwachung, Durchsetzung, Sperrung, Entfernung und Aufbewahrung von Inhalten, die von einer vorab ausgebildeten Klassifizierung identifiziert werden, verantwortlich.

## <a name="how-to-verify-that-a-built-in-classifier-will-meet-your-needs"></a>Überprüfen, ob eine integrierte Klassifizierung Ihren Anforderungen entspricht

1. Sammeln Sie Inhaltselemente für den verfügbaren Test, die Sie in die Kategorie der integrierten Klassifizierung (positive Übereinstimmungen) und diejenigen, die nicht berücksichtigt werden sollten (negative Übereinstimmungen) in der Kategorie, die Sie testen, gehören.

   > [!IMPORTANT]
   > Die Beispielelemente dürfen nicht verschlüsselt werden und müssen in Englisch sein.

2. Erstellen eines dedizierten SharePoint Online Ordners; warten Sie mindestens eine Stunde, bis der Ordner dem Suchindex hinzugefügt wurde. Notieren Sie sich die Ordner-URL.

3. Melden Sie sich bei Microsoft 365 Compliance Center mit Compliance Admin oder Security Admin Role Access an, und öffnen Sie **Microsoft 365 Compliance Center**  >  **Records Management (Preview)**  >  **Label Policies** Tab.

4. Wählen Sie aus `Auto-apply a label` .

5. Wählen Sie aus `Choose a label to auto-apply` .

6. Wählen Sie `Create new labels` und erstellen Sie eine Bezeichnung für die Verwendung nur mit diesem Test. Wenn Sie dies tun, lassen Sie `Retention` die Einstellung auf `off` . Sie möchten keine Aufbewahrung oder andere Aktionen aktivieren. In diesem Fall verwenden Sie die Aufbewahrungs Bezeichnung einfach als Textbeschriftung, ohne dass Aktionen erzwungen werden. Sie können beispielsweise eine Aufbewahrungs Bezeichnung mit dem Namen "Sourcecode-Klassifizierungs Test" ohne Aktionen erstellen und diese Aufbewahrungs Bezeichnung automatisch auf Inhalte anwenden, für die die Quell Code Klassifizierung als Bedingung verwendet wird. Weitere Informationen zum Erstellen von Aufbewahrungs Bezeichnungen finden Sie unter [Overview of Retention Labels](labels.md).
  
7. Wählen Sie `Auto-apply a label` und dann aus `Choose a label to auto-apply` . Weitere Informationen zur Verwendung von Condition Based Auto-Apply a Label finden Sie unter [Automatisches Anwenden von Aufbewahrungs Bezeichnungsrichtlinien basierend auf einer Bedingung](labels.md#applying-a-retention-label-automatically-based-on-conditions).

8. Wählen Sie Ihre Test Bezeichnung in der Liste aus, und wählen Sie aus `Next` .

9. Wählen Sie aus `Apply label to content that matches a trainable classifier` .

   ![Auswählen der Klassifizierung als Bedingung](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

10. Wählen Sie Ihre Klassifizierung aus der Liste aus, in diesem Fall`Source Code`

11. Nennen Sie die Richtlinie, beispielsweise "Quellcode-integrierter Klassifizierungs Test".

12. Wählen Sie aus `Let me choose specific locations` .

13. Deaktivieren Sie alle Speicherorte `SharePoint sites` , außer und wählen Sie `Choose sites` .

14. Geben Sie in Schritt 2 die URL für die Website ein.

15. Beenden Sie den Assistenten, und wählen Sie`Auto-apply`

16. Platzieren Sie die Testelemente in den Ordner dedizierter SharePoint Online.

17. Lassen Sie eine Stunde für die Anwendung der Bezeichnung zu.

18. Überprüfen Sie die Eigenschaften der Dokumente für die Bezeichnung, um festzustellen, ob die Klassifizierung den Testinhalt wie erwartet enthielt und ausschloß.

19. Überprüfen Sie die Elemente, die beschriftet wurden.

20. Löschen Sie den Inhalt und die Bezeichnungsrichtlinie, wenn Sie mit Ihren Tests fertig sind.

Siehe auch:

- [Erste Schritte mit trainierbaren Klassifizierern (Vorschau)](classifier-getting-started-with.md)
- [Übersicht über Aufbewahrungsbezeichnungen](labels.md)
- [Automatisches Anwenden von Aufbewahrungs Bezeichnungsrichtlinien basierend auf einer Bedingung](labels.md#applying-a-retention-label-automatically-based-on-conditions)
