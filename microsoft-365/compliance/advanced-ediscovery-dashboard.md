---
title: Erweitertes eDiscovery-Dashboard für Überprüfungs Sätze
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Verwenden Sie das erweiterte eDiscovery-Dashboard für Überprüfungs Sätze, um Ihren Korpus schnell zu analysieren, um Trends oder wichtige Statistiken zu identifizieren, mit denen Sie Ihre Überprüfungsstrategie entwickeln können.
ms.openlocfilehash: 36f30689047eec7ff2c2c49c6b0d54f1a60470e4
ms.sourcegitcommit: 956dd3f87adb4e6173517550a662c3bacc2d2d79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44741700"
---
# <a name="advanced-ediscovery-dashboard-for-review-sets"></a>Erweitertes eDiscovery-Dashboard für Überprüfungs Sätze

In einigen Fällen in Advanced eDiscovery ist möglicherweise eine große Menge an Dokumenten und e-Mail-Nachrichten vorhanden, die überprüft werden müssen. Bevor Sie mit dem Überprüfungsprozess beginnen, können Sie Ihren Korpus schnell analysieren, um Trends oder wichtige Statistiken zu identifizieren, die Sie bei der Entwicklung ihrer Überprüfungsstrategie unterstützen sollen. Zu diesem Zweck können Sie das erweiterte eDiscovery-Dashboard für Überprüfungs Sätze verwenden, um Ihren Korpus schnell zu analysieren.

## <a name="step-1-create-a-widget-on-the-review-set-dashboard"></a>Schritt 1: Erstellen eines Widgets im Dashboard für Überprüfungs Sätze

1. Wechseln Sie im Security & Compliance Center zu **eDiscovery > Advanced eDiscovery** , um die Liste der Fälle in Ihrer Organisation anzuzeigen.
  
2. Wählen Sie einen vorhandenen Fall aus.
  
3. Klicken Sie auf die Registerkarte **Überarbeitungs Gruppe** , und wählen Sie dann einen Überprüfungs Sätze aus.
  
4. Klicken Sie in der Dropdownliste **einzelne Ergebnisse** auf **Suchprofil Ansicht**. 

   ![DashbordPivot](../media/dashboardpivot.png)

   Die Seite **Suchprofil Ansicht** wird angezeigt; Wenn Sie diese Seite zum ersten Mal anzeigen, werden drei Standard-Widgets angezeigt.

   ![Dashboard](../media/dashboardonly.png)
  
5. Klicken Sie auf das **neue Widget** , und wählen Sie dann eines der folgenden Elemente aus:

   ![Neue Widget-Dropdownliste](../media/NewWidgetDropdownBox.png)

   - **Wählen Sie aus Bibliothek:** Zeigt eine Standardbibliothek von Widgets an. Klicken Sie auf ein Widget, und klicken Sie dann auf **Hinzufügen** , um es zu den Widgets auf der Seite **Suchprofil Ansicht** hinzuzufügen.
  
   - **Benutzerdefiniertes Widget erstellen:** Zeigt eine Flyout-Seite an, mit der Sie ein benutzerdefiniertes Widget einrichten können. 

6. Um ein benutzerdefiniertes Widget zu erstellen, gehen Sie auf der Seite Widget-Flyout **Hinzufügen** wie folgt vor:

   ![Widget erstellen](../media/addwidget.png)

    a. Geben Sie einen Namen für das Widget ein, der in der Titelleiste des Widgets angezeigt wird. Das Benennen eines Widgets ist erforderlich, es ist jedoch hilfreich, die widgetdaten zu identifizieren.

    b. Wählen Sie in der Dropdownliste **Pivot auswählen** eine Eigenschaft aus, die für die Widget-Daten verwendet wird. Die Elemente in dieser Liste sind die durchsuchbaren Eigenschaften für die Elemente in der Überprüfungsgruppe. Eine Beschreibung dieser Eigenschaften finden Sie unter [Document Metadata fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md). Die Pivot-Optionen für das Widget werden in der Spalte **durchsuchbarer Feldname** in diesem Thema aufgeführt.

    c. Auswählen eines Diagrammtyps zum Anzeigen der Daten aus der ausgewählten Pivot-Eigenschaft.

  6. Klicken Sie auf **Hinzufügen** , um das benutzerdefinierte Widget zu erstellen und es auf der Seite **Suchprofil Ansicht** anzuzeigen.

## <a name="step-2-create-a-review-set-search-query"></a>Schritt 2: Erstellen einer Suchabfrage für Überprüfungs Sätze

1. Klicken Sie auf der Titelleiste des Widgets auf **...** , und klicken Sie dann auf **Bedingung anwenden**.

   ![Dashboard](../media/searchprofilehome.png)

2. Klicken Sie auf der Flyout-Seite auf ein Element in der Widget-Taste oder im Widget-Diagramm, um einen Filter zu erstellen.

   ![Createfilter](../media/applyconditionfilter.png)

3. Wiederholen Sie die Schritte 1-2 für andere Widgets mehrere Widgets. 

4. Wenn Sie fertig sind, klicken Sie auf **als Abfrage speichern** , um Ihre Bedingungen als neue Suchabfrage für die Überprüfungsgruppe zu speichern.

   ![Abfrage](../media/savequery.png)

5. Schließen Sie die **Suchprofil Ansicht** , um zur Suchergebnis Ansicht zurückzukehren.

   Wenn Sie visuelle Filter erstellt haben, wird die resultierende Abfrage auf die angezeigten Suchergebnisse angewendet, und die in Schritt 4 gespeicherte Suchabfrage wird unter **gespeicherte Abfragen**angezeigt. Weitere Informationen zum Überprüfen von Mengen Abfragen finden Sie unter [Abfragen der Daten in einem Überprüfungs Satzes](review-set-search.md).
