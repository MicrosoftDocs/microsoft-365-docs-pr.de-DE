---
title: Advanced eDiscovery Dashboard für Überprüfungssätze
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
description: Verwenden Sie Advanced eDiscovery Dashboard für Überprüfungssätze, um Ihren Korpus schnell zu analysieren, um Trends oder wichtige Statistiken zu identifizieren, die Ihnen bei der Entwicklung Ihrer Überprüfungsstrategie helfen.
ms.openlocfilehash: 36f30689047eec7ff2c2c49c6b0d54f1a60470e4
ms.sourcegitcommit: 956dd3f87adb4e6173517550a662c3bacc2d2d79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44741700"
---
# <a name="advanced-ediscovery-dashboard-for-review-sets"></a>Advanced eDiscovery Dashboard für Überprüfungssätze

In einigen Fällen Advanced eDiscovery sie eine große Menge von Dokumenten und E-Mail-Nachrichten, die überprüft werden müssen. Bevor Sie mit dem Überprüfungsprozess beginnen, sollten Sie Ihren Korpus schnell analysieren, um Trends oder wichtige Statistiken zu identifizieren, mit deren Hilfe Sie Ihre Überprüfungsstrategie entwickeln können. Dazu können Sie das Advanced eDiscovery für Überprüfungssätze verwenden, um Ihren Korpus schnell zu analysieren.

## <a name="step-1-create-a-widget-on-the-review-set-dashboard"></a>Schritt 1: Erstellen eines Widgets im Dashboard des Überprüfungssatzs

1. Wechseln Sie im Security & Compliance Center zu **eDiscovery > Advanced eDiscovery,** um die Liste der Fälle in Ihrer Organisation anzeigen.
  
2. Wählen Sie einen vorhandenen Fall aus.
  
3. Klicken Sie **auf die Registerkarte Set** überprüfen, und wählen Sie dann einen Überprüfungssatz aus.
  
4. Klicken Sie in der Dropdownliste **Einzelne Ergebnisse** auf die **Suchprofilansicht**. 

   ![DashbordPivot](../media/dashboardpivot.png)

   Die **Seite Suchprofilansicht** wird angezeigt. Wenn Sie diese Seite zum ersten Mal anzeigen, werden drei Standard-Widgets angezeigt.

   ![Dashboard](../media/dashboardonly.png)
  
5. Klicken Sie **auf das Neue Widget,** und wählen Sie dann eines der folgenden Elemente aus:

   ![Neue Dropdownliste für Widget](../media/NewWidgetDropdownBox.png)

   - **Wählen Sie aus bibliothek:** Zeigt eine Standardbibliothek mit Widgets an. Sie klicken auf ein Widget und dann auf **Hinzufügen,** um es den Widgets auf der Seite Profilansicht **suchen hinzuzufügen.**
  
   - **Erstellen eines benutzerdefinierten Widgets:** Zeigt eine Flyoutseite an, mit der Sie ein benutzerdefiniertes Widget einrichten können. 

6. Gehen Sie zum Erstellen eines benutzerdefinierten Widgets auf der Flyoutseite **Widget** hinzufügen wie folgt vor:

   ![Widget erstellen](../media/addwidget.png)

    a. Geben Sie einen Namen für das Widget ein, das in der Titelleiste des Widgets angezeigt wird. Die Benennung eines Widgets ist erforderlich, es ist jedoch hilfreich, die Widgetdaten zu identifizieren.

    b. Wählen Sie in der **Dropdownliste Pivot** auswählen eine Eigenschaft aus, die für die Widgetdaten verwendet wird. Die Elemente in dieser Liste sind die durchsuchbaren Eigenschaften für die Elemente im Überprüfungssatz. Eine Beschreibung dieser Eigenschaften finden Sie unter [Dokumentmetadatenfelder in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md). Die Pivotoptionen für das Widget sind in diesem Thema in der Spalte **Durchsuchbarer Feldname** aufgeführt.

    c. Wählen Sie einen Diagrammtyp aus, um die Daten aus der ausgewählten Pivot-Eigenschaft anzeigen zu können.

  6. Klicken **Sie auf Hinzufügen,** um das benutzerdefinierte Widget zu erstellen und es auf der Seite **Suchprofilansicht anzuzeigen.**

## <a name="step-2-create-a-review-set-search-query"></a>Schritt 2: Erstellen einer Suchabfrage für den Überprüfungssatz

1. Klicken **Sie in** der Titelleiste des Widgets auf ... und dann auf Bedingung **anwenden.**

   ![Dashboard](../media/searchprofilehome.png)

2. Klicken Sie auf der Flyoutseite auf ein Element in der Widgettaste oder im Widgetdiagramm, um einen Filter zu erstellen.

   ![CreateFilter](../media/applyconditionfilter.png)

3. Wiederholen Sie die Schritte 1 bis 2 für andere Widgets mit mehreren Widgets. 

4. Klicken Sie anschließend auf **Als** Abfrage speichern, um Ihre Bedingungen als neue Suchabfrage für den Überprüfungssatz zu speichern.

   ![Abfrage](../media/savequery.png)

5. Schließen Sie die **Suchprofilansicht,** um zur Suchergebnisseinsicht zurückzukehren.

   Wenn Sie visuelle Filter erstellt haben, wird die resultierende Abfrage auf die angezeigten Suchergebnisse angewendet, und die suchabfrage, die Sie in Schritt 4 gespeichert haben, wird unter Gespeicherte Abfragen **angezeigt.** Weitere Informationen zu Überprüfungssatzabfragen finden Sie unter [Query the data in a review set](review-set-search.md).
