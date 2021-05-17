---
title: Hinzufügen von Custodians zu Advanced eDiscovery Fall
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
description: Erfahren Sie, wie Sie das integrierte Verwaltungstool für Custodian in Advanced eDiscovery, um Ihre Workflows zu koordinieren und relevante Datenquellen in einem Fall zu identifizieren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9468fb889e9115b3652d1dba8a6c6632bb367fe3
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740342"
---
# <a name="add-custodians-to-an-advanced-ediscovery-case"></a>Hinzufügen von Custodians zu Advanced eDiscovery Fall

Verwenden Sie das integrierte Verwaltungstool für verwahrer in Advanced eDiscovery, um Ihre Workflows rund um die Verwaltung von Verwahrern und die Identifizierung relevanter, einem Fall zugeordneter verwahrter Datenquellen zu koordinieren. Wenn Sie einen Verwahrer hinzufügen, kann das System automatisch sein Postfach und sein Exchange und OneDrive for Business halten. Während des Ermittlungsprozesses Ihrer Untersuchung können Sie auch andere Datenquellen (z. B. Postfächer, Websites oder Teams) identifizieren, auf die ein Verwahrer zugegriffen hat oder zu der er beigetragen hat. In dieser Situation können Sie das Verwaltungstool des Verwahrers verwenden, um diesen Datenquellen einen bestimmten Verwahrer zuzuordnen. Nachdem Sie einem Fall Custodians hinzugefügt und anderen Datenquellen zugeordnet haben, können Sie Daten schnell beibehalten und die Verwahrdaten durchsuchen.

Sie können Custodians in Advanced eDiscovery in vier Schritten hinzufügen und verwalten:

1. Identifizieren Sie die Verwahrer.

2. Wählen Sie Speicherorte für Custodian-Daten aus.

3. Konfigurieren von Halteeinstellungen.

4. Überprüfen Sie die Verwahrer, und führen Sie den Vorgang aus.

   [![Registerkarte Quellen in Advanced eDiscovery Fall ](../media/AeD-Sources-Tab.png)](../media/AeD-Sources-Tab.png#lightbox)

## <a name="make-sure-you-have-the-necessary-permissions"></a>Stellen Sie sicher, dass Sie über die erforderlichen Berechtigungen verfügen

Um einem Fall Verwalter hinzuzufügen, müssen Sie Mitglied der Rollengruppe eDiscovery-Manager sein. Dadurch erhalten Sie die erforderlichen Berechtigungen, um einem Fall Verwahrer hinzuzufügen und die Verwahrerdatenquellen zu speichern. Weitere Informationen finden Sie unter [Zuweisen von eDiscovery-Berechtigungen](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions).

## <a name="step-1-identify-custodians"></a>Schritt 1: Identifizieren von Verwahrern

1. Wechseln Sie zu und melden Sie sich mit einem Benutzerkonto an, dem die entsprechenden [https://compliance.microsoft.com](https://compliance.microsoft.com) eDiscovery-Berechtigungen zugewiesen wurden.

2. Klicken Sie im linken Navigationsbereich des Microsoft 365 Compliance Centers auf **Ale anzeigen**, und klicken Sie dann auf **eDiscovery > Advanced**.

3. Klicken Sie **Advanced eDiscovery** seite auf **die** Registerkarte Fälle, und wählen Sie dann den Fall aus, dem Sie Custodians hinzufügen möchten.

4. Klicken Sie **auf die** Registerkarte Datenquellen, und klicken Sie dann auf Datenquelle **hinzufügen**  >  **Neue Verwahrer hinzufügen.**

5. Fügen Sie dem Fall einen oder mehrere Benutzer in Ihrer Organisation als Verwahrer hinzu, indem Sie den ersten Teil des Namens oder Alias einer Person eingeben. Nachdem Sie die richtige Person finden, wählen Sie ihren Namen aus, um sie der Liste hinzuzufügen.

## <a name="step-2-choose-custodian-data-locations"></a>Schritt 2: Auswählen von Speicherorten für Custodian-Daten

Nachdem Sie Custodians ausgewählt haben, versucht das System automatisch, diese Benutzer und ihre Datenquellen zu identifizieren und zu überprüfen. Nach dem Hinzufügen von Verwahrern zur Liste enthält das Tool automatisch das primäre Postfach und OneDrive für jeden Custodian. Sie können diese Datenquellen beim Hinzufügen von Verwahrern zum Fall nicht hinzufügen.

Neben dem Postfach und dem OneDrive eines Verwahrers können Sie auch andere Datenspeicherorte einem Verwahrer zuordnen, z. B. SharePoint-Website oder einem Microsoft-Team, in dem der Custodian Mitglied ist. Auf diese Weise können Sie Inhalte in anderen Datenquellen beibehalten, sammeln, analysieren und überprüfen, die den Verwahrern des Falls zugeordnet sind.

So deaktivieren Sie das primäre Postfach und OneDrive konto für einen Verwahrer:

1. Erweitern Sie den Verwahrer, um die primären Datenspeicherorte zu sehen, die jedem Custodian automatisch zugeordnet wurden.

2. Wählen **Sie Neben** **Postfach** oder **OneDrive** löschen aus, um das Postfach oder das OneDrive eines Custodians als Datenspeicherort für diesen Custodian zu entfernen.

   ![Konfigurieren von Speicherorten, die einem Verwahrer zugeordnet werden](../media/ConfigureCustodianLocations.png)

So ordnen Sie anderen Postfächern, Websites, Teams oder Yammer einem bestimmten Verwahrer zu:

1. Erweitern Sie einen Verwahrer, um die folgenden Dienste zum Zuordnen von Datenspeicherorten zum Verwahrer anzeigen. Klicken **Sie neben** einem Dienst auf Bearbeiten, um einen Datenspeicherort hinzuzufügen.

   - **Exchange**: Wird verwendet, um andere Postfächer dem Verwahrer zuzuordnen. Geben Sie in das Suchfeld den Namen oder Alias (mindestens drei Zeichen) von Benutzerpostfächern oder Verteilergruppen ein. Wählen Sie die Postfächer aus, die dem Custodian zugewiesen werden, und klicken Sie dann auf **Hinzufügen**.

   - **SharePoint**: Verwenden Sie zum Zuordnen SharePoint Websites zum Verwahrer. Wählen Sie eine Website in der Liste aus, oder suchen Sie nach einer Website, indem Sie eine URL in das Suchfeld eingeben. Wählen Sie die Websites aus, die dem Custodian zugewiesen werden soll, und klicken Sie dann auf **Hinzufügen**.

   - **Teams**: Verwenden Sie zum Zuweisen Microsoft Teams, bei dem der Verwahrer derzeit Mitglied ist. Wählen Sie die Teams aus, die dem Verwahrer zugewiesen werden, und klicken Sie dann auf **Hinzufügen**. Nachdem Sie ein Team hinzugefügt haben, identifiziert und sucht das System automatisch die SharePoint- und Gruppenpostfach, die diesem Team zugeordnet sind, und weist sie dem Verwahrer zu.

   - **Yammer**: Verwenden Sie zum Zuweisen Yammer Gruppen, in der der Custodian derzeit Mitglied ist. Wählen Sie die Gruppen aus, die dem Custodian zugewiesen werden, und klicken Sie dann auf **Hinzufügen**. Nachdem Sie ein Team hinzugefügt haben, identifiziert und sucht das System automatisch die SharePoint- und Gruppenpostfach, die dieser Gruppe zugeordnet sind, und weist sie dem Verwahrer zu.

   > [!NOTE]
   > Sie können die **Exchange-** und **SharePoint-Standortauswahl** verwenden, um andere Teams oder Yammer-Gruppen (bei der ein Verwahrer kein Mitglied ist) einem Verwahrer zuzuordnen. Dazu müssen Sie sowohl das Postfach als auch die Website hinzufügen, die jedem Team oder jeder Gruppe Yammer werden.

2. Sie können die Gesamtanzahl der Postfächer, Websites, Teams und Yammer, die jedem Custodian zugewiesen sind, anzeigen, indem Sie die einzelnen Custodian in der Tabelle erweitern. Wenn Sie die zugewiesenen Datenspeicherorte für jeden Verwahrer endgültig erstellt haben, werden diese Zuordnungen während der Erfassungs-, Verarbeitungs- und Überprüfungsphasen im Workflow Advanced eDiscovery verwendet.

3. Nachdem Sie Custodians hinzugefügt und ihre Datenspeicherorte konfiguriert haben, klicken Sie auf **Weiter,** um zur Seite **Halteeinstellungen zu** wechseln.  

## <a name="step-3-configure-hold-settings"></a>Schritt 3: Konfigurieren von Halteeinstellungen

 Nachdem Sie die Verwahrer und deren Datenspeicherorte finalisiert haben, können Sie einige oder alle Verwahrer in der Warteschleife platzieren. Wenn Sie einen Custodian in den Halteraum setzen, werden alle Inhalte an allen Inhaltsstandorten, die dem Custodian zugeordnet sind, aufbewahrt, bis Sie den Halteraum entfernen oder den Custodian aus dem Halteraum entfernen. In einigen Fällen können Sie einem Fall Custodians hinzufügen, ohne sie in der Warteschleife zu platzieren.

So platzieren Sie die Verwahrer und Datenquellen in der Warteschleife:

1. Auf der **Seite Halteeinstellungen** können Sie ein Halterecht auf einzelne Verwahrer anwenden, indem Sie das Kontrollkästchen unter der Spalte **Halterecht** aktivieren.

   Alternativ können Sie alle Verwahrer  in der Warteschleife platzieren, indem Sie das Kontrollkästchen Halterecht am oberen Rand der Spalte aktivieren.

2. Überprüfen Sie die Auswahl der Custodian-Halte, und klicken Sie dann auf **Weiter**.

   > [!NOTE]
   > Wenn Sie einen Verwahrer nicht in den Halteraum setzen, werden der Custodian und die zugehörigen Datenquellen dem Fall hinzugefügt, aber der Inhalt in diesen Datenquellen wird nicht durch den Dem Fall zugeordneten Halteraum beibehalten.

## <a name="step-4-review-the-custodians-and-complete-the-process"></a>Schritt 4: Überprüfen der Verwahrer und Abschließen des Prozesses

Bevor Sie dem Fall die Verwahrer hinzufügen, können Sie die Liste der Verwahrer, die ihnen zugewiesenen Datenspeicherorte und die Halteeinstellungen überprüfen.

1. Überprüfen und überprüfen Sie alle Datenquellenanzahl und die Halteeinstellung, die jedem Verwahrer in der Tabelle zugeordnet ist. Wechseln Sie bei Bedarf zurück zu den Seiten Einstellungen für **Custodian identifizieren** oder **speichern,** um Änderungen vorzunehmen.

2. Klicken **Sie auf Übermitteln,** um dem Fall Custodians und deren Datenspeicherorte hinzuzufügen und alle Einstellungen für den Verwahrer anzuwenden.

   Die neuen Custodians werden dem Fall hinzugefügt und auf der Registerkarte **Datenquellen** angezeigt.

   [![Auf der Registerkarte Datenquellen aufgeführte Verwahrer ](../media/DataSourcesTab.png)](../media/DataSourcesTab.png#lightbox)
