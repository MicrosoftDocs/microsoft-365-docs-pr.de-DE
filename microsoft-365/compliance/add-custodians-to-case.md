---
title: Hinzufügen von Verwaltern zu einem erweiterten eDiscovery-Fall
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
description: Erfahren Sie, wie Sie das integrierte Depot Verwaltungstool in Advanced eDiscovery verwenden, um Ihre Workflows zu koordinieren und relevante Datenquellen in einem Fall zu identifizieren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9468fb889e9115b3652d1dba8a6c6632bb367fe3
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740342"
---
# <a name="add-custodians-to-an-advanced-ediscovery-case"></a>Hinzufügen von Verwaltern zu einem erweiterten eDiscovery-Fall

Verwenden Sie das integrierte Depot Verwaltungstool in Advanced eDiscovery, um Ihre Workflows rund um das Verwalten von Depotbanken zu koordinieren und relevante, Freiheits geschützte Datenquellen zu identifizieren, die einem Fall zugeordnet sind. Wenn Sie eine Depotbank hinzufügen, kann das System das Exchange-Postfach und das OneDrive für Unternehmen Konto automatisch identifizieren und aufbewahren. Während des Ermittlungsprozesses ihrer Untersuchung können Sie auch andere Datenquellen (wie Postfächer, Websites oder Teams) identifizieren, auf die eine Depotbank zugegriffen oder dazu beigetragen hat. In diesem Fall können Sie das Depot Verwaltungstool verwenden, um diese Datenquellen einer bestimmten Depotbank zuzuordnen. Nachdem Sie einem Fall Verwalter hinzugefügt und ihm eine andere Datenquelle zugeordnet haben, können Sie schnell Daten aufbewahren und die Freiheits Schutz-Daten durchsuchen.

Sie können Verwalter in erweiterten eDiscovery-Fällen in vier Schritten hinzufügen und verwalten:

1. Identifizieren Sie die depotverwalter.

2. Wählen Sie Depotdaten Speicherorte aus.

3. Konfigurieren von halte Einstellungen.

4. Überprüfen Sie die depotverwalter, und führen Sie den Vorgang aus.

   [![Registerkarte "Quellen" im erweiterten eDiscovery-Fall ](../media/AeD-Sources-Tab.png)](../media/AeD-Sources-Tab.png#lightbox)

## <a name="make-sure-you-have-the-necessary-permissions"></a>Stellen Sie sicher, dass Sie über die erforderlichen Berechtigungen verfügen

Um einem Fall Verwalter hinzuzufügen, müssen Sie Mitglied der Rollengruppe "eDiscovery-Manager" sein. Auf diese Weise erhalten Sie die erforderlichen Berechtigungen, um einem Fall Verwalter hinzuzufügen und die Datenquellen für den Freiheitsentzug aufzubewahren. Weitere Informationen finden Sie unter [Zuweisen von eDiscovery-Berechtigungen](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions).

## <a name="step-1-identify-custodians"></a>Schritt 1: Identifizieren der depotverwalter

1. Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com) und melden Sie sich mit einem Benutzerkonto an, dem die entsprechenden eDiscovery-Berechtigungen zugewiesen wurden.

2. Klicken Sie im linken Navigationsbereich des Microsoft 365 Compliance Centers auf **Ale anzeigen**, und klicken Sie dann auf **eDiscovery > Advanced**.

3. Klicken Sie auf der Seite **Erweiterte eDiscovery** auf die Registerkarte **Fälle** , und wählen Sie dann den Fall aus, dem Sie Verwalter hinzufügen möchten.

4. Klicken Sie auf die Registerkarte **Datenquellen** , und klicken Sie dann auf **Datenquelle hinzu** fügen  >  **neuer depotverwalter**.

5. Fügen Sie einen oder mehrere Benutzer in Ihrer Organisation als Verwalter für den Fall hinzu, indem Sie den ersten Teil des Namens oder Alias einer Person eingeben. Nachdem Sie die richtige Person gefunden haben, wählen Sie Ihren Namen aus, um Sie der Liste hinzuzufügen.

## <a name="step-2-choose-custodian-data-locations"></a>Schritt 2: Auswählen von Depotdaten Speicherorten

Nachdem Sie Verwalter ausgewählt haben, versucht das System automatisch, diese Benutzer und Ihre Datenquellen zu identifizieren und zu überprüfen. Nachdem Sie der Liste Verwalter hinzugefügt haben, enthält das Tool automatisch das primäre Postfach und das OneDrive-Konto für jede Depotbank. Sie können festlegen, dass diese Datenquellen beim Hinzufügen von Bewahrern in den Fall nicht eingeschlossen werden sollen.

Neben dem Postfach und OneDrive-Konto eines Depotinhabers können Sie auch andere Datenspeicherorte einer Depotbank zuordnen, beispielsweise SharePoint-Website oder ein Microsoft-Team, bei dem die Depotbank Mitglied ist. Auf diese Weise können Sie Inhalte in anderen Datenquellen beibehalten, sammeln, analysieren und überprüfen, die mit den Verwalter der Anfrage verknüpft sind.

So deaktivieren Sie das primäre Postfach und das OneDrive-Konto für eine Depotstelle:

1. Erweitern Sie die Depotbank, um die primären Datenspeicherorte anzuzeigen, die den einzelnen depotern automatisch zugeordnet wurden.

2. Wählen Sie neben **Postfach** oder **OneDrive** **Löschen** aus, um das Postfach oder das OneDrive-Konto eines Depot Besitzers als Datenspeicherort für diese Depotstelle zu verknüpfen.

   ![Konfigurieren von Speicherorten für die Zuordnung zu einer Depotbank](../media/ConfigureCustodianLocations.png)

So ordnen Sie einer bestimmten Depotbank andere Postfächer, Websites, Teams oder Jammer Gruppen zu:

1. Erweitern Sie eine Depotbank, um die folgenden Dienste anzuzeigen, um Datenspeicherorte der Depotbank zuzuordnen. Klicken Sie neben einem Dienst auf **Bearbeiten** , um einen Datenspeicherort hinzuzufügen.

   - **Exchange**: Verwenden Sie, um andere Postfächer der Depotbank zuzuordnen. Geben Sie den Namen oder den Alias (mindestens drei Zeichen) von Benutzerpostfächern oder Verteilergruppen in das Suchfeld ein. Wählen Sie die Postfächer aus, die Sie der Depotbank zuweisen möchten, und klicken Sie dann auf **Hinzufügen**.

   - **SharePoint**: Verwenden Sie, um SharePoint-Websites der Depotbank zuzuordnen. Wählen Sie eine Website in der Liste aus, oder suchen Sie nach einer Website, indem Sie eine URL in das Suchfeld eingeben. Wählen Sie die Websites aus, die Sie der Depotbank zuweisen möchten, und klicken Sie dann auf **Hinzufügen**.

   - **Teams**: Verwenden Sie, um Microsoft Teams zuzuweisen, zu denen die Depotbank derzeit gehört. Wählen Sie die Teams aus, die Sie der Depotbank zuweisen möchten, und klicken Sie dann auf **Hinzufügen**. Nachdem Sie ein Team hinzugefügt haben, identifiziert und sucht das System automatisch die SharePoint-Website und das Gruppenpostfach, die diesem Team zugeordnet sind, und ordnet Sie der Depotbank zu.

   - **Jammern**: Verwenden Sie, um die Jammer Gruppen zuzuweisen, denen die Depotbank derzeit angehört. Wählen Sie die Gruppen aus, die Sie der Depotbank zuweisen möchten, und klicken Sie dann auf **Hinzufügen**. Nachdem Sie ein Team hinzugefügt haben, identifiziert und sucht das System automatisch die SharePoint-Website und das Gruppenpostfach, die dieser Gruppe zugeordnet sind, und weist Sie der Depotbank zu.

   > [!NOTE]
   > Sie können die **Exchange** -und **SharePoint** -Standortauswahl verwenden, um andere Teams oder Jammer Gruppen (die ein Depot Mitglied nicht ist) einer Depotbank zuzuordnen. Dazu müssen Sie sowohl das Postfach als auch die Website hinzufügen, die den einzelnen Teams oder der Gruppe "jammern" zugeordnet ist.

2. Sie können die Gesamtanzahl der Postfächer, Websites, Teams und Jammer Gruppen anzeigen, die jeder Depotbank zugewiesen sind, indem Sie jede Depotbank in der Tabelle erweitern. Wenn Sie die zugewiesenen Datenspeicherorte für jede Depotbank abgeschlossen haben, werden diese Zuordnungen während der Sammlungs-, Verarbeitungs-und Überprüfungsphase im erweiterten eDiscovery-Workflow beibehalten und verwendet.

3. Nachdem Sie Verwalter hinzugefügt und ihre Datenspeicherorte konfiguriert haben, klicken Sie auf **weiter** , um zur Seite **Aufbewahrungseinstellungen** zu wechseln.  

## <a name="step-3-configure-hold-settings"></a>Schritt 3: Konfigurieren der Aufbewahrungseinstellungen

 Nachdem Sie die Verwalter und ihre Datenspeicherorte abgeschlossen haben, können Sie einige oder alle depotverwalter in der Warteschleife platzieren. Wenn Sie eine Depotstelle aufbewahren, werden alle Inhalte in allen Inhaltsspeicherorten, die dem depotverwalter zugeordnet sind, beibehalten, bis Sie den Haltebereich entfernen oder die Depotbank aus dem Archiv freigeben. In einigen Fällen möchten Sie möglicherweise Verwalter einem Fall hinzufügen, ohne diese in den Wartebereich zu versetzen.

So platzieren Sie die Depotstellen und Datenquellen in der Warteschleife:

1. Auf der Seite **Aufbewahrungseinstellungen** können Sie einzelnen Depotbanken einen Haltestatus zuweisen, indem Sie das Kontrollkästchen unter der Spalte **halten** aktivieren.

   Alternativ können Sie alle Verwalter in der Warteschleife platzieren, indem Sie das Kontrollkästchen **halten** am oberen Rand der Spalte aktivieren.

2. Überprüfen Sie die Aufbewahrungsoptionen, und klicken Sie dann auf **weiter**.

   > [!NOTE]
   > Wenn Sie keine Aufbewahrungspflicht für einen depotverwalter festlegen, werden die Depotbank und die ihr zugeordneten Datenquellen dem Fall hinzugefügt, der Inhalt dieser Datenquellen wird jedoch nicht durch den mit der Anfrage verknüpften Aufbewahrungsplatz beibehalten.

## <a name="step-4-review-the-custodians-and-complete-the-process"></a>Schritt 4: Überprüfen der depotverwalter und Abschließen des Prozesses

Bevor Sie die Verwalter dem Fall hinzufügen, können Sie die Liste der depotverwalter, die Ihnen zugewiesenen Datenspeicherorte und die Aufbewahrungseinstellungen überprüfen.

1. Überprüfen und überprüfen Sie alle Datenquellen Zählung und die Aufbewahrungseinstellung, die mit den einzelnen Depotbanken in der Tabelle verknüpft ist. Wenn erforderlich, kehren Sie zur Seite " **Verwalter identifizieren** " oder " **Einstellungen speichern** " zurück, um Änderungen vorzunehmen.

2. Klicken Sie auf **Submit** , um dem Fall depotverwalter und deren Datenspeicherorte hinzuzufügen und alle Einstellungen für den Freiheitsentzug anzuwenden.

   Die neuen depotverwalter werden dem Fall hinzugefügt und auf der Registerkarte **Datenquellen** angezeigt.

   [![Auf der Registerkarte "Datenquellen" ](../media/DataSourcesTab.png) aufgelistete depotverwalter](../media/DataSourcesTab.png#lightbox)
