---
title: Erste Schritte mit trainierbaren Klassifizierern (Vorschau)
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
description: Eine Microsoft 365-Klassifizierung ist ein Tool, mit dem Sie verschiedene Arten von Inhalten erkennen können, indem Sie sich Beispiele ansehen. In diesem Artikel erfahren Sie, wie Sie eine benutzerdefinierte Klassifizierung erstellen und trainieren und Sie neu trainieren, um die Genauigkeit zu verbessern.
ms.openlocfilehash: 9fe50f7faada77492fd93a86d0c3549cc8e1d361
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2020
ms.locfileid: "49072964"
---
# <a name="get-started-with-trainable-classifiers-preview"></a>Erste Schritte mit trainierbaren Klassifizierern (Vorschau)

Eine Microsoft 365-schulungsable-Klassifizierung ist ein Tool, mit dem Sie verschiedene Arten von Inhalten erkennen können, indem Sie Beispiele für die Untersuchung geben. Sobald Sie geschult wurden, können Sie es verwenden, um das Element für die Anwendung von Office-Vertraulichkeits Bezeichnungen, Kommunikationsrichtlinien und Aufbewahrungs Bezeichnungsrichtlinien zu identifizieren.

Das Erstellen einer benutzerdefinierten Klassifizierer-Klassifizierung umfasst zunächst das Erteilen von Stichproben, die von Menschen ausgewählt werden und der Kategorie positiv entsprechen. Nachdem Sie diese verarbeitet haben, testen Sie dann die Fähigkeit der Klassifizierungen, vorherzusagen, indem Sie eine Mischung aus positiven und negativen Beispielen geben. In diesem Artikel erfahren Sie, wie Sie eine benutzerdefinierte Klassifizierung erstellen und trainieren und wie Sie die Leistung von benutzerdefinierten Schulungs fähigen Klassifizierungen und vorab ausgebildeten Klassifizierungen über ihre Lebensdauer durch Umschulung verbessern können.

Weitere Informationen zu den verschiedenen Klassifizierungstypen finden Sie unter [Learn about trainable Klassifizierers (Preview)](classifier-learn-about.md).

## <a name="prerequisites"></a>Voraussetzungen

### <a name="licensing-requirements"></a>Lizenzierungsanforderungen

Klassifizierungen sind ein Microsoft 365 E5-oder E5-Konformitäts Feature. Sie müssen über eines dieser Abonnements verfügen, damit Sie Sie nutzen können.

### <a name="permissions"></a>Berechtigungen

So greifen Sie auf die Klassifizierung in der Benutzeroberfläche zu: 

- der globale Administrator muss sich für den Mandanten anmelden, um benutzerdefinierte Klassifizierungen zu erstellen.
- Compliance-Administrator oder Daten Ermittlungs Rolle ist erforderlich, um eine Klassifizierung zu trainieren.

Sie benötigen Konten mit diesen Berechtigungen für die Verwendung von Klassifizierungen in den folgenden Szenarien:

- Richtlinien Szenario für Aufbewahrungs Bezeichnungen: Rollen für die Datensatzverwaltung und Aufbewahrungsverwaltung 
- Richtlinien Szenario für die Sensitivitäts Bezeichnung: Sicherheitsadministrator, Kompatibilitäts Administrator, Kompatibilitätsdaten Administrator
- Kommunikations Konformitätsrichtlinien Szenario: Administrator für Insider Risiko Management, Aufsichts Überprüfungs Administrator 

> [!IMPORTANT]
> Standardmäßig kann nur der Benutzer, der eine benutzerdefinierte Klassifizierung erstellt, die von dieser Klassifizierung vorgenommenen Vorhersagen trainieren und überprüfen.

## <a name="prepare-for-a-custom-trainable-classifier"></a>Vorbereiten auf eine benutzerdefinierte Schulungs Klassifizierung 

Es ist hilfreich zu verstehen, was am Erstellen einer benutzerdefinierten Klassifizierer-Klassifizierung beteiligt ist, bevor Sie eintauchen. 

### <a name="timeline"></a>Zeitachse

Diese Zeitachse reflektiert eine Beispielbereitstellung von Schulungs Klassifizierern.

![Schulungs-und Klassifizierungs Zeitplan](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> Das Anmelden ist zum ersten Mal für Schulungs orientierte Klassifizierungen erforderlich. Es dauert zwölf Tage, bis Microsoft 365 eine Basisbewertung ihrer organisationsinhalte abgeschlossen hat. Wenden Sie sich an ihren globalen Administrator, um den Opt-in-Prozess zu starten.

### <a name="overall-workflow"></a>Allgemeiner Workflow

Weitere Informationen zum Gesamtworkflow beim Erstellen von benutzerdefinierten Schulungs Klassifizierern finden Sie unter [Prozessablauf zum Erstellen von Schulungs Klassifizierern für Kunden](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).

### <a name="seed-content"></a>Seed-Inhalt

Wenn Sie möchten, dass eine Lernende Klassifizierung ein Element in einer bestimmten Inhaltskategorie unabhängig und genau identifiziert, müssen Sie es zunächst mit vielen Beispielen des Inhaltstyps in der Kategorie präsentieren. Diese Fütterung von Proben zur Klassifizierer-Schulung wird als *Seeding* bezeichnet. Seed-Inhalt wird von einem Menschen ausgewählt und wird bewertet, um die Kategorie des Inhalts darzustellen.

> [!TIP]
> Sie benötigen mindestens 50 positive Beispiele und bis zu 500. Die eingestufte Klassifizierung wird bis zu den 500 zuletzt erstellten Beispielen verarbeitet (nach Dateierstellungsdatum/Zeitstempel). Je mehr Beispiele Sie bereitstellen, desto genauer sind die Vorhersagen, die von der Klassifizierung vorgenommen werden.

### <a name="testing-content"></a>Testen von Inhalten

Nachdem die Schulungs fähigen Klassifizierung genügend positive Beispiele zum Erstellen eines Vorhersagemodells verarbeitet hat, müssen Sie die vorher gestellten Voraussagen testen, um zu ermitteln, ob die Klassifizierung ordnungsgemäß zwischen Elementen unterscheiden kann, die der Kategorie und den Elementen entsprechen, die nicht übereinstimmen. Sie tun dies, indem Sie eine andere, hoffentlich größere Gruppe von Personen übergreifenden Inhalten auswählen, die aus Beispielen besteht, die in die Kategorie fallen sollten, und Beispiele, die dies nicht tun. Sie sollten mit unterschiedlichen Daten als die anfänglichen Ausgangsdaten testen, die Sie zuerst angegeben haben. Nachdem Sie diese verarbeitet haben, gehen Sie die Ergebnisse manuell durch und überprüfen, ob jede Vorhersage korrekt, falsch oder nicht sicher ist. Die Schulungs-Klassifizierung verwendet dieses Feedback, um das Vorhersagemodell zu verbessern.

> [!TIP]
> Die besten Ergebnisse erzielen Sie, wenn Ihr Test Beispiel mindestens 200 Elemente mit einer gleichmäßigen Verteilung positiver und negativer Übereinstimmungen auflistet.

## <a name="how-to-create-a-trainable-classifier"></a>Vorgehensweise Erstellen einer Schulungs Klassifizierer

1. Sammeln zwischen 50-500-Seed-Inhaltselementen. Hierbei muss es sich nur um Beispiele handeln, die den Typ des Inhalts, den die Lernenden Klassifizierung positiv als in der Kategorie Klassifizierung identifiziert werden soll, stark darstellen. Weitere Informationen finden Sie unter [standardmäßig durchforstete Dateinamenerweiterungen und analysierte Dateitypen in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) für die unterstützten Dateitypen.

   > [!IMPORTANT]
   > Die Ausgangs-und Test Beispielelemente dürfen nicht verschlüsselt sein und müssen in Englisch sein.

   > [!IMPORTANT]
   > Stellen Sie sicher, dass die Elemente im seedsatz **starke** Beispiele für die Kategorie sind. Die eingestufte Klassifizierung erstellt zunächst Ihr Modell basierend auf dem, was Sie mit dem Seeding beginnen. Bei der Klassifizierung wird davon ausgegangen, dass alle Seed-Beispiele starke positive Ergebnisse aufweisen und keine Möglichkeit haben zu wissen, ob ein Beispiel einer schwachen oder negativen Übereinstimmung mit der Kategorie entspricht.

2. Platzieren Sie den Ausgangs Inhalt in einem SharePoint Online Ordner, *der ausschließlich für den Inhalt des Seeds* reserviert ist. Notieren Sie sich die Website-, Bibliotheks-und Ordner-URL.

   > [!TIP]
   > Wenn Sie eine neue Website und einen neuen Ordner für Ihre Seed-Daten erstellen, lassen Sie mindestens eine Stunde für diesen Standort indiziert werden, bevor Sie die Schulungs Klassifizierung erstellen, die diese Startdaten verwendet.

3. Melden Sie sich bei Microsoft 365 Compliance Center mit dem Compliance-Administrator oder der Rolle "Sicherheitsadministrator" an, und öffnen Sie **Microsoft 365 Compliance Center** oder die Datenklassifizierung für das **Microsoft 365 Security Center**  >  **Data classification**.

4. Klicken Sie auf die Registerkarte **Schulungs Klassifizierung** .

5. Wählen Sie **Create trainable Klassifizierer** aus.

6. Geben Sie die entsprechenden Werte für `Name` die `Description` Felder und der Kategorie der Elemente ein, die diese Lernbare Klassifizierung identifizieren soll.

7. Wählen Sie in Schritt 2 die SharePoint Online Website, Bibliothek und Ordner-URL für die Seed-Inhaltswebsite aus. Wählen Sie aus `Add` .

8. Überprüfen Sie die Einstellungen, und wählen Sie `Create trainable classifier` .

9. Innerhalb von 24 Stunden verarbeitet die Schulungs-und Klassifizierungs Stelle die seeddaten und erstellt ein Vorhersagemodell. Der Klassifizierungsstatus ist `In progress` , während er die seeddaten verarbeitet. Wenn die Klassifizierung die Verarbeitung der seeddaten abgeschlossen hat, wird der Status in geändert `Need test items` .

10. Sie können die Seite Details jetzt anzeigen, indem Sie die Klassifizierung auswählen.

    > [!div class="mx-imgBorder"]
    > ![Schulungs fähige Klassifizierung zum Testen verfügbar](../media/classifier-trainable-ready-to-test-detail.png)

11. Sammeln Sie mindestens 200 Testinhalts Elemente (10.000 max), um optimale Ergebnisse zu erzielen. Dabei muss es sich um eine Mischung von Elementen handeln, die starke positive Ergebnisse aufweisen, starke negative und einige, die in ihrer Natur etwas weniger offensichtlich sind. Weitere Informationen finden Sie unter [standardmäßig durchforstete Dateinamenerweiterungen und analysierte Dateitypen in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) für die unterstützten Dateitypen.

    > [!IMPORTANT]
    > Die Beispielelemente dürfen nicht verschlüsselt werden und müssen in Englisch sein.

12. Platzieren Sie den Testinhalt in einem SharePoint Online Ordner, *der ausschließlich für den Testinhalt* reserviert ist. Notieren Sie sich die SharePoint Online Website, Bibliothek und Ordner-URL.

    > [!TIP]
    > Wenn Sie eine neue Website und einen neuen Ordner für Ihre Testdaten erstellen, lassen Sie mindestens eine Stunde für diesen Ort indiziert werden, bevor Sie die Schulungs Klassifizierung erstellen, die diese Startdaten verwendet.

13. Wählen Sie aus `Add items to test` .

14. Wählen Sie die SharePoint Online Website, Bibliothek und Ordner-URL für die Testinhalts Website aus Schritt 12 aus. Wählen Sie aus `Add` .

15. Beenden Sie den Assistenten, indem Sie auswählen `Done` . Ihre Schulungs-Klassifizierung dauert bis zu einer Stunde, um die Testdateien zu verarbeiten.

16. Wenn die ausbildende Klassifizierung die Verarbeitung Ihrer Testdateien abgeschlossen hat, wird der Status auf der Seite Details in geändert `Ready to review` . Wenn Sie die Größe des testsamples vergrößern möchten, wählen Sie aus, `Add items to test` und lassen Sie die Schulungs-Klassifizierung die zusätzlichen Elemente verarbeiten.

    > [!div class="mx-imgBorder"]
    > ![zur Überprüfung des Screenshot verfügbar](../media/classifier-trainable-ready-to-review-detail.png)

17. Klicken Sie `Tested items to review` auf die Registerkarte, um Elemente zu überprüfen.

18. Microsoft 365 wird 30 Elemente gleichzeitig darstellen. Überprüfen Sie diese, und `We predict this item is "Relevant". Do you agree?` Wählen Sie im Feld entweder `Yes` oder `No` oder aus `Not sure, skip to next item` . Die Modellgenauigkeit wird nach jeweils 30 Elementen automatisch aktualisiert.

    > [!div class="mx-imgBorder"]
    > ![Feld "Elemente überprüfen"](../media/classifier-trainable-review-detail.png)

19. Über *prüfen Sie mindestens 200* Elemente. Nachdem das Genauigkeits Ergebnis stabilisiert wurde, wird die Option **veröffentlichen** verfügbar sein, und der Status der Klassifizierung wird sagen `Ready to use` .

    > [!div class="mx-imgBorder"]
    > ![Genauigkeits Bewertung und Veröffentlichungs bereit](../media/classifier-trainable-review-ready-to-publish.png)

20. Veröffentlichen Sie die Klassifizierung.

21. Nachdem Ihre Klassifizierung veröffentlicht wurde, wird Sie als Bedingung in der [automatischen Office-Bezeichnungsrichtlinie mit Vertraulichkeits Bezeichnungen](apply-sensitivity-label-automatically.md), [automatisch angewendeten Aufbewahrungs Bezeichnungsrichtlinien basierend auf einer Bedingung](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) und in der [Kommunikations Konformität](communication-compliance.md)verfügbar sein.
