---
title: Verwalten von Personen mit Interesse an Daten Ermittlungen (Vorschau)
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
description: Hier erfahren Sie, wie Sie interessante Personen für den Bereich Ihrer Suche verwalten oder Informationen wie Kontakt, Standort und Aktivitätsprotokolle anzeigen können.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 85f6bdbe7a0602f8ce0038a4aca912896d5c2079
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46528171"
---
# <a name="manage-people-of-interest-in-data-investigations-preview"></a>Verwalten von Personen mit Interesse an Daten Ermittlungen (Vorschau)

Daten Untersuchungen beziehen häufig Interessen Personen mit ein. Normalerweise handelt es sich um Personen, die die verfallenen, vertraulichen oder bösartigen Daten besitzen, die Sie untersuchen oder zu beheben versuchen. In **Data Investigations (Preview)** können Sie diese hinzufügen, um die Datenquellen zu ermitteln, die Sie beim Festlegen Ihrer Suche oder beim Anzeigen zusätzlicher Informationen wie Kontakt-, Standort-und Aktivitätsprotokolle verwenden müssen. 


## <a name="add-people-of-interest"></a>Hinzufügen von interessanten Personen

Auf der Registerkarte " **interessante Personen** " können Sie interessante Personen hinzufügen und deren Datenquellen wie Exchange-Postfächer oder OneDrive für Unternehmen Website ermitteln, die Sie zum Umfang Ihrer Suche verwenden können. Wenn die Suche nach Personen mit Interesse erfolgt, sind die Suchvorgänge leistungsfähiger und genauer, da das Tool alle nicht indizierten Daten wie Bilder oder nicht unterstützte Dateitypen neu verarbeitet. Sie können auch Ihre Kontaktinformationen, Standortinformationen und Aktivitätsprotokolle anzeigen, mit denen Sie die Kommunikation initiieren oder ihre Aktivitäten weiter untersuchen können. 

So fügen Sie einer Untersuchung interessante Personen hinzu:

1. Wechseln Sie auf der Seite **Daten Ermittlungen (Vorschau)** zu ihrer Untersuchung.
 
2. Nachdem Sie eine Untersuchung ausgewählt haben, wechseln Sie zur Registerkarte **Personen von Interesse** , und klicken Sie auf **+ Personen von Interesse hinzufügen**. 
 
3. Wählen Sie Personen aus, die Sie der Untersuchung hinzufügen möchten. Sie können mit der Eingabe beginnen, um die Benutzer aus der Azure-Active Directory Ihrer Organisation zu suchen und auszuwählen.
 
4. Nachdem Sie die Liste der Personen mit Interesse abgeschlossen haben, klicken Sie auf **weiter** , um Ihre Datenquellen zuzuordnen. 

5. Optional Wählen Sie für jede Person **Exchange** aus, um das primäre Exchange-Postfach der Person hinzuzufügen, und **OneDrive** , um die primäre OneDrive für Unternehmen Website der Person hinzuzufügen.

6. Optional Klicken Sie auf **weiter** , um zusätzliche Datenquellen hinzuzufügen, die Sie Ihren Interessen Personen zuordnen möchten.

7. Optional Wählen Sie **Aktualisieren** aus, um inhaltsspeicherorte wie Postfächer, Websites und Teams einer Person zuzuweisen. 

8. Optional Im Flyout:
   
    -  **Exchange-Postfächer** – klicken Sie auf **Benutzer, Gruppen oder Teams auswählen** , und klicken Sie dann erneut auf **Benutzer, Gruppen oder Teams auswählen** . Verwenden Sie zum Hinzufügen weiterer Postfächer das Suchfeld, um nach Benutzerpostfächern und Verteilergruppen zu suchen. Sie können auch Postfächer hinzufügen, die zum Speichern einer Microsoft 365-Gruppe oder von Microsoft-Team Informationen verwendet werden. Aktivieren Sie das Kontrollkästchen Benutzer, Gruppe, Team, klicken Sie auf **auswählen**, und klicken Sie dann auf **Fertig**.

        > [!NOTE]
        > Wenn Sie auf Benutzer, Gruppen oder Teams auswählen, um Postfächer anzugeben, ist die angezeigte Post Fachauswahl leer. Dies ist beabsichtigt, um die Leistung zu verbessern. Geben Sie einen Namen (mindestens 3 Zeichen) in das Suchfeld ein, um Personen zu dieser Liste hinzuzufügen.
     
     - **SharePoint-Websites** – klicken Sie auf **Websites auswählen** , und klicken Sie dann auf **Websites erneut auswählen** , um zusätzliche SharePoint-und OneDrive für Unternehmen-Websites anzugeben, die Sie einer Person hinzufügen möchten. Sie können auch die URL für die SharePoint-Website für eine Microsoft 365-Gruppe oder ein Microsoft-Team hinzufügen. Geben Sie die URL für jede Website ein, die Sie zuweisen möchten. Klicken Sie auf **auswählen**, und klicken Sie dann auf **Fertig**.
     - **Microsoft Teams** – klicken Sie auf **Teams auswählen** , und klicken Sie dann auf **Teams erneut auswählen** , um eine Liste der Microsoft-Team Gruppen anzuzeigen, in denen die Person heute Mitglied ist. Wählen Sie die Teams aus, die Sie der Person hinzufügen möchten. Nach der Auswahl identifiziert das System automatisch & wählen Sie die zugeordnete SharePoint-Website und das Gruppenpostfach, das diesem Microsoft-Team zugeordnet ist. Klicken Sie auf **auswählen**, und klicken Sie dann auf **Fertig**.
        
      > [!NOTE]
      > Wenn Sie weitere Microsoft Teams hinzufügen möchten, müssen Sie das Postfach und die SharePoint-Website wie oben gezeigt separat hinzufügen.

Nachdem Sie die Zuordnung von Datenquellen zu interessanten Personen abgeschlossen haben, können Sie die Zusammenfassung der Gesamtzahl der Postfächer, Websites und Teams anzeigen, die Sie soeben hinzugefügt haben. Wenn Sie zusätzliche Datenquellen den Interessen Personen zuordnen und Ihre Suche nach Interessenbereichen durchführen, wird die Zuordnung von Dokumenten zu Interessen Personen während der gesamten Untersuchung fortbestehen, wodurch es einfacher wird, Nachweise zu organisieren oder einen Bericht von interessanten Personen zu generieren. 

## <a name="view-additional-people-of-interest-information"></a>Anzeigen zusätzlicher Informationen zu interessanten Personen

Klicken Sie auf der Registerkarte **interessante Personen** auf eine Person, die Sie hinzugefügt haben. In einem Flyout sehen Sie Folgendes:

- Kontaktinformationen

  - **Anzeigename**: der Name der Person, die im Adressbuch angezeigt wird. Dies ist normalerweise die Kombination aus Vorname, mittlerer Initiale und Nachname.
  - **Mail/SMTP**: die SMTP-Adresse der Person, beispielsweise Jeff@contoso.onmicrosoft.com.  
  - **Title**: Position Title.
  - **Department**: der Name der Abteilung, in der die Person arbeitet.
  - **Manager**: der Vorgesetzte der Person. Manager erhält eine Eskalations Kommunikation für diese Person.
  
- Standortinformationen

  - **Stadt**: der Ort, an dem sich die Person befindet.
  - **State**: der Staat oder die Provinz, in dem sich die Person befindet.
  - **Land/Region**: das Land/die Region, in dem sich die Person befindet; Beispiel: "US" oder "UK".
  - **Office**: der Office-Standort der Person.

- Verarbeitungsstatus

  - **Indizierungsstatus**: Status der Deep-Indizierung der Datenquellen
  - **Indizierungs Zeitpunkt der letzten Aktualisierung: Zeit**Stempel für den Zeitpunkt des letzten Triggers des tiefen Indizierungs Auftrags.
  - **Datenquellen**: zeigt die Anzahl von Postfächern, Websites und Teams an, die der Person zugeordnet sind.

- Index aktualisieren
    - Sie können die Datenquellen dieser Person neu indizieren. 

- Aktivität anzeigen 

    - Sie können die Aktivitätsprotokolle des Benutzers anzeigen und durchsuchen. Weitere Informationen finden Sie unter [Anzeigen von Aktivitäten für Personen mit Interesse](view-people-of-interest-activity.md) . 
