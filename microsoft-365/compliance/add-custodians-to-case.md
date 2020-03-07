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
description: ''
ms.openlocfilehash: f77a2967c6b789d28a95516594b1bdd5d8b9f3c6
ms.sourcegitcommit: 6c8edbc54b193e964cf93aec48c51cb79231f1d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2020
ms.locfileid: "42543604"
---
# <a name="add-custodians-to-an-advanced-ediscovery-case"></a>Hinzufügen von Verwaltern zu einem erweiterten eDiscovery-Fall

Verwenden Sie das integrierte Depot Verwaltungstool in Advanced eDiscovery, um Ihre Workflows rund um das Verwalten von Depotbanken zu koordinieren und relevante, Freiheits geschützte Datenquellen zu identifizieren, die einem Fall zugeordnet sind. Wenn Sie eine Depotbank hinzufügen, kann das System das Exchange-Postfach und das OneDrive für Unternehmen Konto automatisch identifizieren und aufbewahren. Während des Ermittlungsprozesses ihrer Untersuchung können Sie auch zusätzliche Datenquellen (wie Postfächer, Websites oder Teams) identifizieren, auf die eine Depotbank zugegriffen oder dazu beigetragen hat. In diesem Fall können Sie das Depot Verwaltungstool verwenden, um diese Datenquellen einer bestimmten Depotbank zuzuordnen. Nachdem Sie einem Fall Verwalter hinzugefügt und ihm eine andere Datenquelle zugeordnet haben, können Sie schnell Daten aufbewahren und die Freiheits Schutz-Daten durchsuchen.

Verwenden Sie den folgenden Workflow, um Verwalter in erweiterten eDiscovery-Fällen hinzuzufügen und zu verwalten. 

![Registerkarte "Depotverwaltung"](../media/CustodianMgtPage.png)

## <a name="before-you-begin"></a>Bevor Sie beginnen

Um einem Fall Verwalter hinzuzufügen, müssen Sie Mitglied der Rollengruppe "eDiscovery-Manager" sein. Auf diese Weise erhalten Sie die erforderlichen Berechtigungen zum Hinzufügen von Bewahrern zu einem Fall und zum Aufbewahren der Datenquellen für den Freiheitsentzug.


## <a name="step-1-add-potential-custodians"></a>Schritt 1: Hinzufügen potenzieller depotverwalter

Der erste Schritt besteht darin, die Verwalter für den Fall zu identifizieren und hinzuzufügen.

1. Klicken Sie auf der Seite für die **Erweiterte eDiscovery** -Homepage auf den Fall, dem Sie Verwalter hinzufügen möchten. 
 
2. Klicken Sie auf die Registerkarte **depotverwalter** , und klicken Sie dann auf **depotverwalter hinzufügen**.

3. Hier finden Sie die Verwalter, die dem Fall hinzugefügt werden sollen. Geben Sie den ersten Teil des Namens einer Person ein, um Benutzer aus der Azure-Active Directory Ihrer Organisation anzuzeigen. Wenn Sie die richtige Person gefunden haben, klicken Sie auf Ihren Namen, um Sie der Liste hinzuzufügen.

   ![Ermitteln potenzieller depotverwalter](../media/AddCustodianStep1.png)
 
4. Nachdem Sie alle relevanten Verwalter hinzugefügt haben, klicken Sie auf **weiter** , um die primären Datenquellen der Depotbank auszuwählen.
  
## <a name="step-2-select-custodian-data-sources"></a>Schritt 2: Auswählen von Depotdaten Quellen

Nach dem Hinzufügen von Depotbanken hilft Ihnen das depotverwalter-Tool dabei, die primären Datenquellen zu identifizieren, die im Besitz jeder Depotbank sind. Diese Datenspeicherorte sind das Exchange-Postfach des Depotbank und das OneDrive-Konto. 

So identifizieren Sie Depotbank-Datenquellen: 

1. Wenn Sie das Exchange-Postfach für alle Verwalter auswählen möchten, aktivieren Sie das Kontrollkästchen **Exchange** oben in der Spalte. Sie können dann das Kontrollkästchen für eine bestimmte Depotbank deaktivieren, um ein Postfach als Speicherort für die Freiheitsentzug zu entfernen. Alternativ können Sie das Kontrollkästchen **Exchange** oben in der Spalte deaktivieren und dann das Kontrollkästchen für einzelne depotverwalter aktivieren. 
 
   ![Auswählen von Datenquellen für sorgeberechtigte](../media/AddCustodianStep2.png)
 
2. Wiederholen Sie die gleiche Sache für die OneDrive-Konten der Verwalter. 

    Nachdem Sie die Depotbank-Datenquellen ausgewählt haben, versucht das System automatisch, diese Datenquellen zu identifizieren und zu überprüfen, und fügt Sie dann dem Fall als Datenquellen hinzu, die den Depotbanken zugeordnet sind.
 
4. Klicken Sie auf **weiter** , um mit dem Zuordnen zusätzlicher Datenquellen zu den Depotstellen in dem Fall zu beginnen.

## <a name="step-3-associate-additional-data-sources-to-a-custodian"></a>Schritt 3: Zuordnen zusätzlicher Datenquellen zu einer Depotstelle

Je nachdem, welchen Fall Sie untersuchen, müssen Sie möglicherweise auch Postfächer suchen (und beibehalten), auf die eine bestimmte Depotbank zugegriffen haben kann, Office 365 Gruppen, auf die eine Depotbank derzeit gehört, oder auf Websites, auf die auch eine Depotbank zugegriffen hat. Zusätzlich zu den primären Depotdaten Quellen, die Sie im vorherigen Schritt angegeben haben, können Sie auch zusätzliche Office 365 Datenquellen mit einer Depotbank in dem Fall verknüpfen. 

So ordnen Sie Postfächern, Websites oder Teams einer bestimmten Depotbank zu:

1. Klicken Sie auf der Seite **Weitere Datenquellen auswählen** in der Zeile für die jeweilige Depotbank auf **Hinzufügen** . 
  
   ![Zuordnen zusätzlicher Datenquellen](../media/AddCustodianStep3.PNG)

2. Auf der Flyout-Seite können Sie eine Datenquelle aus einem der folgenden Office 365 Dienste angeben:
  
   -  **Exchange-e-Mail** -klicken Sie auf **Benutzer, Gruppen oder Teams auswählen** , und klicken Sie dann erneut auf **Benutzer, Gruppen oder Teams auswählen** . Verwenden Sie das Suchfeld, um nach Postfächern zu suchen, die der Depotbank zugeordnet werden sollen. Zum Angeben von Postfächern, die der ausgewählten Depotbank zugewiesen werden sollen, suchen Sie im Suchfeld nach Benutzerpostfächern und Verteilergruppen. Sie können auch das zugeordnete Postfach für eine Office 365 Gruppe oder ein Microsoft-Team zuweisen. Aktivieren Sie das Kontrollkästchen Benutzer, Gruppe, Team, klicken Sie auf **auswählen**, und klicken Sie dann auf **Fertig**.

        > [!NOTE]
        > Wenn Sie auf Benutzer, Gruppen oder Teams auswählen, um Postfächer anzugeben, ist die angezeigte Post Fachauswahl leer. Dies ist beabsichtigt, um die Leistung zu verbessern. Geben Sie einen Namen oder Alias (mindestens 3 Zeichen) in das Suchfeld ein, um dieser Liste ein Postfach hinzuzufügen.
     
     - **SharePoint-Websites** – klicken Sie auf **Websites auswählen** , und klicken Sie dann erneut auf **Websites auswählen** , um eine Liste der SharePoint-Websites in Ihrer Organisation anzuzeigen. Zum Zuordnen einer Website zur Depotbank können Sie eine Website in der Liste auswählen oder die URL einer anderen Website oder Website eingeben, die einer Office 365 Gruppe, einem Microsoft Team oder einem OneDrive-Konto zugeordnet ist.
     
     - **Teams** – klicken Sie auf **Teams auswählen** , und klicken Sie dann erneut auf **Teams auswählen** , um eine Liste der Microsoft Teams anzuzeigen, bei denen die Depotbank derzeit Mitglied ist. Wählen Sie die Teams aus, die Sie Ihrer Depotbank hinzufügen möchten. Nach der Auswahl identifiziert das System automatisch & wählen Sie die zugeordnete SharePoint-Website und das Gruppenpostfach, das diesem Microsoft-Team zugeordnet ist. Klicken Sie auf **auswählen**, und klicken Sie dann auf **Fertig**.

       ![Zuordnen von Datenquellen](../media/AddCustodianStep4.PNG)
        
      > [!NOTE]
      > Wenn Sie ein zusätzliches Team einer Depotbank zuordnen möchten, müssen Sie das Postfach und den Standort, der dem Team zugeordnet ist, separat mithilfe der Speicherorte von **Exchange-e-Mail** und **SharePoint-Websites** hinzufügen.

Nachdem Sie die Zuordnung zusätzlicher Datenquellen zu den Depotstellen abgeschlossen haben, können Sie die Gesamtzahl der Postfächer, Websites und Teams anzeigen, die jeder Depotbank auf der **Seite Weitere Datenquellen auswählen**zugeordnet sind. Wenn Sie die relevanten Datenquellen für eine bestimmte Depotbank abgeschlossen haben, wird diese Zuordnung während der Sammlungs-, Verarbeitungs-und Überprüfungsphase im eDiscovery-Workflow beibehalten und verwendet.

## <a name="step-4-place-custodians-on-hold"></a>Schritt 4: Platzieren von Depot Haltern

Nachdem Sie die Verwalter und Datenquellen abgeschlossen haben, die dem Fall hinzugefügt werden sollen, können Sie optional einige oder alle depotverwalter in der Warteschleife platzieren. Wenn Sie eine Depotstelle aufbewahren, werden alle Inhalte in allen Inhaltsspeicherorten, die dem depotverwalter zugeordnet sind, beibehalten, bis Sie den Haltebereich entfernen oder die Depotbank aus dem Archiv freigeben. In einigen Fällen möchten Sie möglicherweise Verwalter einem Fall hinzufügen, ohne diese in den Wartebereich zu versetzen.

So platzieren Sie die Depotstellen und Datenquellen in der Warteschleife:

1. Aktivieren Sie auf der Seite **Aufbewahrungsplatz auf der ausgewählten Depotstelle** das Kontrollkästchen **halten** am oberen Rand der Spalte, um alle depotverwalter in den Haltebereich zu versetzen. Sie können dann das Kontrollkästchen für eine bestimmte Depotbank deaktivieren, die aus dem Haltestatus entfernt werden soll. Alternativ können Sie das Kontrollkästchen **halten** am oberen Rand der Spalte deaktiviert lassen und dann das Kontrollkästchen für einzelne depotverwalter aktivieren. 
 
   ![Platz hält](../media/AddCustodianStep5.PNG)

2. Überprüfen Sie die Aufbewahrungsoptionen, und klicken Sie dann auf **Fertig**stellen.

Wenn Sie keine Aufbewahrungspflicht für einen depotverwalter festlegen, werden der Verwalter und die ihm zugeordneten Datenquellen dem Fall hinzugefügt, der Inhalt dieser Datenquellen wird jedoch nicht in die Warteschleife gesetzt.

Nachdem eine Depotbank in den Wartebereich versetzt wurde, wird automatisch eine Depotbank-Aufbewahrungsrichtlinie erstellt, die alle Freiheitsentzug-Quellen enthält. So zeigen Sie diese Richtlinie an:

1. Klicken Sie auf der **Start** Seite der Anfrage auf die Registerkarte halte **Status** , und klicken Sie dann auf **CustodianHold-GUID**,  

2. Klicken Sie auf der Flyout-Seite auf **Speichern Bearbeiten** , um alle Depotdaten Quellen anzuzeigen, die in der Warteschleife gespeichert werden.

