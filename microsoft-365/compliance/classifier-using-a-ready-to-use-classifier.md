---
title: Verwenden einer gebrauchsfertigen Klassifizierung (Vorschau)
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
description: Microsoft 365 verfügt über eine Reihe von einsatzfähigen Computer Lern-Klassifizierungen, mit denen Sie Inhalte in Ihrer Organisation identifizieren und bezeichnen können. In diesem Thema wird erläutert, wie Sie diese bereit für die Verwendung von Klassifizierungen vorbereiten.
ms.openlocfilehash: 8f3df8e7851bf453add162df4088e11dc7745cee
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42078792"
---
# <a name="using-a-ready-to-use-classifier-preview"></a>Verwenden einer gebrauchsfertigen Klassifizierung (Vorschau)

Microsoft hat eine Reihe von Klassifizierungen mit sehr umfangreichen Beispieldatensätzen geschult und getestet, mit denen bestimmte Inhaltskategorien identifiziert werden können. Weitere Informationen finden Sie unter [Erste Schritte mit Schulungs Klassifizierern (Vorschau)](classifier-getting-started-with.md). Diese Klassifizierungen werden standardmäßig in `Ready to use` der Gruppe angezeigt.

- **Anstößige Sprache**: erkennt Textelemente, die Profanität, Beleidigungen, verspottungen und verschleierte Ausdrücke enthalten (bei denen es sich um Ausdrücke handelt, die die gleiche Bedeutung wie ein beleidigender Ausdruck haben).
- **Lebensläufe**: erkennt Elemente, bei denen es sich um Text Konten für persönliche, pädagogische, berufliche Qualifikationen, Berufserfahrung und andere personenbezogene Informationen handelt.
- **Sourcecode**: erkennt Elemente, die eine Reihe von Anweisungen und Anweisungen enthalten, die in weit verbreiteten Programmiersprachen für Computer geschrieben wurden.
- **Belästigung**: erkennt eine bestimmte Kategorie von Textelementen anstößiger Sprache im Zusammenhang mit anstößigem Verhalten, das auf eine oder mehrere Personen basierend auf den folgenden Merkmalen ausgerichtet ist: Rasse, Ethnizität, Religion, nationale Herkunft, Geschlecht, sexuelle Orientierung, Alter, Behinderung.
- **Profanity**: erkennt eine bestimmte Kategorie von Textelementen anstößiger Sprache, die Ausdrücke enthalten, die die meisten Personen in Verlegenheit bringen.
- **Threat**: erkennt eine bestimmte Kategorie von Textelementen anstößiger Sprache im Zusammenhang mit Bedrohungen, um Gewalt zu begehen oder physischen Schaden oder einer Person oder einer Eigenschaft zu Schaden;

> [!NOTE]
> Bevor Sie die Klassifizierungstools in Ihrem Klassifikations-und Beschriftungs Workflow verwenden, sollten Sie Sie anhand eines Beispiels für die Inhalte Ihrer Organisation testen, das Ihrer Meinung nach der Kategorie entspricht, um zu überprüfen, ob Ihre Klassifizierungs Vorhersagen Ihren Erwartungen entsprechen.

> [!IMPORTANT]
> Bitte beachten Sie, dass die beleidigende Sprache, Belästigung, Profanität und Bedrohungs Klassifizierungen nur mit durchsuchbarem Text funktionieren, die nicht erschöpfend oder vollständig sind. Außerdem ändern sich die Sprach-und Kulturstandards ständig, und in Anbetracht dieser Gegebenheiten behält sich Microsoft das Recht vor, diese Klassifizierungen nach eigenem Ermessen zu aktualisieren. Während die Klassifizierungen Ihre Organisation bei der Überwachung von anstößigen und anderen Sprachen unterstützen können, befassen sich die Klassifizierungsverfahren nicht mit den Folgen dieser Sprache und dienen nicht dazu, die alleinigen Möglichkeiten Ihrer Organisation zur Überwachung oder Reaktion auf die Verwendung von zu bieten. solche Sprache. Ihre Organisation und nicht Microsoft oder ihre Niederlassungen bleiben für alle Entscheidungen im Zusammenhang mit der Überwachung, Durchsetzung, Sperrung, Entfernung und Aufbewahrung von Inhalten, die von einer vorab ausgebildeten Klassifizierung identifiziert werden, verantwortlich.

## <a name="how-to-prepare-for-and-use-a-ready-to-use-classifier"></a>Vorgehensweise vorbereiten und Verwenden einer bereit zu verwendenden Klassifizierung

1. Sammeln Sie Inhaltselemente für den verfügbaren Test, die ihrer Meinung nach zur Kategorie der betriebsbereiten Klassifizierung gehören (positive Übereinstimmungen) und diejenigen, die nicht einbezogen werden sollten (negative Übereinstimmungen) in der Kategorie, die Sie testen.

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

11. Nennen Sie die Richtlinie, beispielsweise "Quellcode-fähig für den Klassifizierungs Test".

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
