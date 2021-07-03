---
title: Erste Schritte mit trainierbaren Klassifizierern
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
description: Ein Microsoft 365 Klassifizierer ist ein Tool, das Sie trainieren können, um verschiedene Arten von Inhalten zu erkennen, indem Sie ihm Beispiele geben, die Sie sich ansehen können. In diesem Artikel erfahren Sie, wie Sie einen benutzerdefinierten Klassifizierer erstellen und trainieren und sie neu trainieren, um die Genauigkeit zu erhöhen.
ms.openlocfilehash: 3053e5154fb4e1ff39ce7db366ce4679bbb8911d
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286633"
---
# <a name="get-started-with-trainable-classifiers"></a>Erste Schritte mit trainierbaren Klassifizierern

Ein Microsoft 365 trainierbarer Klassifizierer ist ein Tool, das Sie trainieren können, um verschiedene Arten von Inhalten zu erkennen, indem Sie ihm Beispiele zum Betrachten geben. Sobald Sie geschult sind, können Sie damit Elemente für die Anwendung von Office Vertraulichkeitsbezeichnungen, Kommunikationscompliancerichtlinien und Aufbewahrungsbezeichnungsrichtlinien identifizieren.

Zum Erstellen eines benutzerdefinierten trainierbaren Klassifizierers müssen Sie zunächst Beispiele bereitstellen, die vom Menschen ausgewählt und positiv mit der Kategorie übereinstimmen. Nachdem diese verarbeitet wurden, testen Sie die Fähigkeit der Klassifizierer, vorherzusagen, indem Sie eine Mischung aus positiven und negativen Stichproben erhalten. In diesem Artikel erfahren Sie, wie Sie einen benutzerdefinierten Klassifizierer erstellen und trainieren und die Leistung von benutzerdefinierten trainierbaren Klassifizierern und vorab trainierten Klassifizierern während ihrer Lebensdauer durch Umschulung verbessern.

Weitere Informationen zu den verschiedenen Typen von Klassifizierern finden Sie unter [Informationen zu trainierbaren Klassifizierern.](classifier-learn-about.md)

Sehen Sie sich dieses Video an, um eine kurze Zusammenfassung der Erstellung eines trainierbaren Klassifizierers zu sehen. Sie müssen immer noch diesen vollständigen Artikel lesen, um die Details zu erhalten.

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGL7]


## <a name="prerequisites"></a>Voraussetzungen

### <a name="licensing-requirements"></a>Lizenzierungsanforderungen

Klassifizierungen sind ein Microsoft 365 E5- oder E5-Compliance-Feature. Sie müssen über eines dieser Abonnements verfügen, um sie nutzen zu können.

### <a name="permissions"></a>Berechtigungen

So greifen Sie auf Klassifizierer in der Benutzeroberfläche zu: 

- Der globale Administrator muss sich dafür entscheiden, dass der Mandant benutzerdefinierte Klassifizierer erstellt.
- Die Rolle "Complianceadministrator" ist erforderlich, um einen Klassifizierer zu trainieren.

Sie benötigen Konten mit diesen Berechtigungen, um Klassifizierer in diesen Szenarien zu verwenden:

- Szenario mit Aufbewahrungsbezeichnungsrichtlinien: Rollen "Datensatzverwaltung" und "Aufbewahrungsverwaltung" 
- Richtlinienszenario für Vertraulichkeitsbezeichnungen: Sicherheitsadministrator, Complianceadministrator, Compliancedatenadministrator
- Szenario der Kommunikationscompliance-Richtlinie: Administrator des Insider-Risikomanagements, Administrator für aufsichtsrechtliche Überprüfung 

> [!IMPORTANT]
> Standardmäßig kann nur der Benutzer, der einen benutzerdefinierten Klassifizierer erstellt, die von diesem Klassifizierer erstellten Vorhersagen trainieren und überprüfen.

## <a name="prepare-for-a-custom-trainable-classifier"></a>Vorbereiten eines benutzerdefinierten trainierbaren Klassifizierers 

Es ist hilfreich zu verstehen, was bei der Erstellung eines benutzerdefinierten trainierbaren Klassifizierers vor dem Einlassen erforderlich ist. 

### <a name="timeline"></a>Zeitachse

Diese Zeitachse spiegelt eine Beispielbereitstellung trainierbarer Klassifizierer wider.

![trainable-classifier-timeline](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> Die Erstmalige Anmeldung für trainierbare Klassifizierer ist erforderlich. Es dauert zwölf Tage, bis Microsoft 365 eine Grundlegende Auswertung der Inhalte Ihrer Organisation durchführen. Wenden Sie sich an Ihren globalen Administrator, um den Anmeldevorgang zu starten.

### <a name="overall-workflow"></a>Gesamter Workflow

Weitere Informationen zum Gesamtworkflow der Erstellung benutzerdefinierter trainierbarer Klassifizierer finden Sie unter [Prozessablauf zum Erstellen von trainierbaren Klassifizierern für Kunden.](classifier-learn-about.md#process-flow-for-creating-custom-classifiers)

### <a name="seed-content"></a>Ausgangsinhalt

Wenn ein trainierbarer Klassifizierer ein Element unabhängig und genau als eine bestimmte Kategorie von Inhalten identifizieren soll, müssen Sie es zunächst mit vielen Beispielen des Inhaltstyps in der Kategorie präsentieren. Diese Zufuhr von Beispielen an den trainierbaren Klassifizierer wird als *Seeding* bezeichnet. Ausgangsinhalte werden von einem Menschen ausgewählt und stehen für die Kategorie der Inhalte.

> [!TIP]
> Sie benötigen mindestens 50 positive Beispiele und bis zu 500. Der trainierbare Klassifizierer verarbeitet bis zu den 500 zuletzt erstellten Beispielen (nach Datums-/Zeitstempel der Datei). Je mehr Beispiele Sie bereitstellen, desto genauer sind die Vorhersagen, die der Klassifizierer macht.

### <a name="testing-content"></a>Testen von Inhalten

Nachdem der trainierbare Klassifizierer genügend positive Beispiele verarbeitet hat, um ein Vorhersagemodell zu erstellen, müssen Sie die getroffenen Vorhersagen testen, um festzustellen, ob der Klassifizierer zwischen Elementen, die der Kategorie entsprechen, und Elementen, die nicht übereinstimmen, ordnungsgemäß unterscheiden kann. Dazu wählen Sie einen weiteren, hoffentlich größeren Satz von vom Menschen ausgewählten Inhalten aus, die aus Beispielen bestehen, die in die Kategorie fallen sollten, und Beispielen, die nicht in die Kategorie fallen. Sie sollten mit anderen Daten als die anfänglichen Startdaten testen, die Sie zuerst angegeben haben. Nachdem diese verarbeitet wurden, durchlaufen Sie die Ergebnisse manuell und überprüfen, ob jede Vorhersage korrekt, falsch oder nicht sicher ist. Der trainierbare Klassifizierer verwendet dieses Feedback, um sein Vorhersagemodell zu verbessern.

> [!TIP]
> Um optimale Ergebnisse zu erzielen, müssen Sie mindestens 200 Elemente in Ihrem Testbeispiel mit einer gleichmäßigen Verteilung positiver und negativer Übereinstimmungen festlegen.

## <a name="how-to-create-a-trainable-classifier"></a>So erstellen Sie einen trainierbaren Klassifizierer

1. Sammeln sie zwischen 50 und 500 Startinhaltselementen. Hierbei darf es sich nur um Beispiele handeln, die den Inhaltstyp stark darstellen, den der trainierbare Klassifizierer positiv als in der Klassifizierungskategorie identifizieren soll. Die unterstützten Dateitypen finden Sie [unter "Standardmäßig durchforstete Dateinamenerweiterungen und analysierte Dateitypen in SharePoint Server".](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

   > [!IMPORTANT]
   > Die Ausgangs- und Testbeispielelemente dürfen nicht verschlüsselt werden, und sie müssen englisch sein.

   > [!IMPORTANT]
   > Stellen Sie sicher, dass die Elemente in Ihrem Startset **starke** Beispiele für die Kategorie sind. Der trainierbare Klassifizierer erstellt zunächst sein Modell basierend auf dem Ausgangswert. Der Klassifizierer geht davon aus, dass alle Ausgangsbeispiele starke positive Ergebnisse sind und keine Möglichkeit hat zu wissen, ob es sich bei einer Stichprobe um eine schwache oder negative Übereinstimmung mit der Kategorie handelt.

2. Platzieren Sie den Startinhalt in einem SharePoint Online-Ordner, *der nur den Startinhalt* enthalten soll. Notieren Sie sich die Website, Bibliothek und Ordner-URL.

   > [!TIP]
   > Wenn Sie eine neue Website und einen neuen Ordner für Ihre Startdaten erstellen, lassen Sie die Indizierung dieses Speicherorts mindestens eine Stunde zu, bevor Sie den trainierbaren Klassifizierer erstellen, der diese Startdaten verwendet.

3. Melden Sie sich bei Microsoft 365 Compliance Center mit Complianceadministrator- oder Sicherheitsadministratorrollenzugriff an, und öffnen **Sie Microsoft 365 Compliance Center** oder **Microsoft 365** Sicherheitscenter-Datenklassifizierung.  >  

4. Wählen Sie die Registerkarte **"Trainierbare Klassifizierer" aus.**

5. Wählen Sie **trainierbaren Klassifizierer erstellen** aus.

6. Geben Sie die entsprechenden Werte für die und die Felder der Kategorie der Elemente ein, die `Name` dieser `Description` trainierbare Klassifizierer identifizieren soll.

7. Wählen Sie die SharePoint Onlinewebsite, Bibliothek und Ordner-URL für die Ausgangsinhaltswebsite aus Schritt 2 aus. Wählen Sie `Add` .

8. Überprüfen Sie die Einstellungen, und wählen Sie `Create trainable classifier` aus.

9. Innerhalb von 24 Stunden verarbeitet der trainierbare Klassifizierer die Startdaten und erstellt ein Vorhersagemodell. Der Klassifizierungsstatus `In progress` ist, während die Startdaten verarbeitet werden. Wenn der Klassifizierer die Verarbeitung der Startdaten abgeschlossen hat, ändert sich der Status in `Need test items` .

10. Sie können jetzt die Detailseite anzeigen, indem Sie den Klassifizierer auswählen.

    > [!div class="mx-imgBorder"]
    > ![Trainierbarer Klassifizierer, der für Tests bereit ist](../media/classifier-trainable-ready-to-test-detail.png)

11. Sammeln Sie mindestens 200 Testinhaltselemente (maximal 10.000), um optimale Ergebnisse zu erzielen. Hierbei sollte es sich um eine Mischung aus Elementen mit starken positiven, starken negativen und einigen Elementen handelt, die ihrer Natur nach etwas weniger offensichtlich sind. Die unterstützten Dateitypen finden Sie [unter "Standardmäßig durchforstete Dateinamenerweiterungen und analysierte Dateitypen in SharePoint Server".](/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

    > [!IMPORTANT]
    > Die Beispielelemente dürfen nicht verschlüsselt werden und müssen in Englisch sein.

12. Platzieren Sie den Testinhalt in einem SharePoint Online-Ordner, *der nur den Testinhalt* enthalten soll. Notieren Sie sich die SharePoint Onlinewebsite, Bibliothek und Ordner-URL.

    > [!TIP]
    > Wenn Sie eine neue Website und einen neuen Ordner für Ihre Testdaten erstellen, lassen Sie die Indizierung dieses Speicherorts mindestens eine Stunde zu, bevor Sie den trainierbaren Klassifizierer erstellen, der diese Startdaten verwendet.

13. Wählen Sie `Add items to test` .

14. Wählen Sie die SharePoint Onlinewebsite, Bibliothek und Ordner-URL für die Testinhaltswebsite aus Schritt 12 aus. Wählen Sie `Add` .

15. Schließen Sie den Assistenten ab, indem Sie . `Done` auswählen. Die Verarbeitung der Testdateien durch den trainierbaren Klassifizierer dauert bis zu einer Stunde.

16. Wenn der trainierbare Klassifizierer die Verarbeitung Ihrer Testdateien abgeschlossen hat, ändert sich der Status auf der Detailseite in `Ready to review` . Wenn Sie die Testbeispielgröße erhöhen müssen, wählen `Add items to test` Sie den trainierbaren Klassifizierer aus, und lassen Sie es zu, um die zusätzlichen Elemente zu verarbeiten.

    > [!div class="mx-imgBorder"]
    > ![bereit zum Überprüfen des Screenshots](../media/classifier-trainable-ready-to-review-detail.png)

17. Wählen Sie `Tested items to review` die Registerkarte aus, um Elemente zu überprüfen.

18. Microsoft 365 werden jeweils 30 Elemente präsentieren. Überprüfen Sie sie, und wählen Sie im `We predict this item is "Relevant". Do you agree?` Feld entweder `Yes` oder `No` `Not sure, skip to next item` aus. Die Modellgenauigkeit wird nach 30 Elementen automatisch aktualisiert.

    > [!div class="mx-imgBorder"]
    > ![Feld "Elemente überprüfen"](../media/classifier-trainable-review-detail.png)

19. Überprüfen Sie *mindestens* 200 Elemente. Sobald sich die Genauigkeitsbewertung stabilisiert hat, wird die **Veröffentlichungsoption** verfügbar sein, und der Klassifizierungsstatus wird `Ready to use` sagen.

    > [!div class="mx-imgBorder"]
    > ![Genauigkeitsbewertung und Veröffentlichungsbereitschaft](../media/classifier-trainable-review-ready-to-publish.png)

20. Veröffentlichen Sie den Klassifizierer.

21. Nach der Veröffentlichung steht Der Klassifizierer als Bedingung in [Office automatischen Bezeichnung mit Vertraulichkeitsbezeichnungen,](apply-sensitivity-label-automatically.md) [automatisch angewendeter Aufbewahrungsbezeichnungsrichtlinie basierend auf einer Bedingung](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) und in der [Kommunikationscompliance](communication-compliance.md)zur Verfügung.
