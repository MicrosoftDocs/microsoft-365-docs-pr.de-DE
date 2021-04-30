---
title: 'In Kürze: Konfigurieren SharePoint als Lerninhaltsquelle für Microsoft Viva Learning (Vorschau)'
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 04/30/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: Erfahren Sie, wie Sie SharePoint als Lerninhaltsquelle für Microsoft Viva Learning (Vorschau) konfigurieren.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: da75ec0573519ed73507994afeac995c0461de0c
ms.sourcegitcommit: d3f8c69519c593b1580cfa7187ce085a99b8a846
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52100962"
---
# <a name="coming-soon-configure-sharepoint-as-a-learning-content-source-for-microsoft-viva-learning-preview"></a>In Kürze: Konfigurieren SharePoint als Lerninhaltsquelle für Microsoft Viva Learning (Vorschau)

> [!NOTE]
> Die Informationen in diesem Artikel beziehen sich auf ein Vorschauprodukt, das möglicherweise erheblich geändert wird, bevor es kommerziell veröffentlicht wird. 

Sie können SharePoint als Lerninhaltsquelle konfigurieren, um die eigenen Inhalte Ihrer Organisation in Viva Learning (Vorschau) verfügbar zu machen.

## <a name="overview"></a>Übersicht

Der Wissensadministrator (oder globaler Administrator) stellt eine Website-URL zur Verfügung, zu der der Lerndienst einen leeren zentralen Speicherort – das Lern-App-Inhaltsrepository – in Form einer strukturierten SharePoint erstellen kann. Diese Liste kann von Ihrer Organisation verwendet werden, um Links zu unternehmensübergreifenden SharePoint, die Lerninhalte enthalten, zu speichern. Administratoren sind für das Sammeln und Krümmen einer Liste von URLs für Ordner verantwortlich. Diese Ordner sollten nur Inhalte enthalten, die in Viva Learning (Vorschau) verfügbar gemacht werden können.

Viva Learning (Preview) unterstützt die folgenden Dokumenttypen:

- Word, PowerPoint, Excel, PDF
- Audio (.m4a)
- Video (.mov, .mp4, .avi)

Weitere Informationen finden Sie in der [SharePoint Onlinedokumentation](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits?redirectSourcePath=%252farticle%252fSharePoint-Online-limits-8f34ff47-b749-408b-abc0-b605e1f6d498). 

## <a name="permissions"></a>Berechtigungen

URLs für Dokumentbibliotheksordner können von allen SharePoint in der Organisation gesammelt werden. Viva Learning (Preview) folgt allen vorhandenen Inhaltsberechtigungen. Daher sind nur Inhalte, für die ein Benutzer Zugriffsrechte hat, in Viva Learning (Vorschau) durchsuchbar und sichtbar. Alle Inhalte in diesen Ordnern sind durchsuchbar, aber nur Inhalte, für die der einzelne Mitarbeiter Berechtigungen besitzt, können verwendet werden.

Das Löschen von Inhalten aus dem Repository Ihrer Organisation wird derzeit nicht unterstützt.

Führen Sie die folgenden Schritte aus, um unbeabsichtigt angezeigte Inhalte zu entfernen:

1.  Um den Zugriff auf die Dokumentbibliothek einzuschränken, wählen Sie **die** Option Aktionen anzeigen aus, und wählen Sie dann Zugriff **verwalten aus.**
     
     ![Dokumentbibliotheksseite in SharePoint zeigt die Option Aktionen anzeigen mit Zugriff verwalten highligted.](../media/learning/learning-sharepoint-permissions2.png)

2.  Löschen Sie das ursprüngliche Dokument in der Dokumentbibliothek.

Weitere Informationen finden Sie unter [Freigabe und Berechtigungen in der modernen SharePoint.](/sharepoint/modern-experience-sharing-permissions) 

## <a name="learning-service"></a>Lerndienst

Der Lerndienst verwendet die bereitgestellten Ordner-URLs, um Metadaten aus allen Inhalten zu erhalten, die in diesen Ordnern gespeichert sind. Innerhalb von 24 Stunden nach der Bereitstellung der Ordner-URL im zentralen Repository können Mitarbeiter innerhalb von Viva Learning (Vorschau) nach den Inhalten Ihrer Organisation suchen und diese verwenden. Alle Änderungen an Inhalten, einschließlich aktualisierter Metadaten und Berechtigungen, werden auch innerhalb von 24 Stunden im Lerndienst angewendet.

## <a name="configure-sharepoint-as-a-source"></a>Konfigurieren SharePoint als Quelle

Sie müssen ein globaler administrator Microsoft 365 oder SharePoint oder Wissensadministrator sein, um diese Aufgaben ausführen zu können.

Führen Sie die folgenden SharePoint aus, um die Inhalte als Lerninhaltsquellen in für Viva Learning (Preview) zu konfigurieren:

1.  Wechseln Sie in der linken Navigation des Microsoft 365 Admin Center zu **Einstellungen**  >  **Organisationseinstellungen**.
 
2.  Wählen Sie **auf der** Seite Organisationseinstellungen auf der Registerkarte **Dienste** die Option **Lern-App (Vorschau)** aus.

     ![Einstellungen seite im Microsoft 365 Admin Center, in dem Das Viva Learning aufgeführt ist.](../media/learning/learning-sharepoint-configure1.png)

3.  Stellt im Bereich Lern-App **(Vorschau)** unter SharePoint die Website-URL für die SharePoint-Website zur Verfügung, auf der Sie ein zentrales Repository von Viva Learning erstellen möchten.

     ![Lernbereich im Microsoft 365 Admin Center, in dem SharePoint angezeigt wird.](../media/learning/learning-sharepoint-configure2.png)

4.  Eine SharePoint wird automatisch innerhalb der bereitgestellten SharePoint erstellt.

     ![Neu erstellte SharePoint innerhalb der SharePoint Website.](../media/learning/learning-sharepoint-configure3.png)

     Wählen Sie in der linken Navigationsleiste SharePoint Website **Websiteinhalte**  >  **Lern-App-Inhaltsrepository aus.** 

     ![SharePoint liste mit der Navigation der Websiteinhalte und dem Abschnitt Lern-App-Inhaltsrepository.](../media/learning/learning-sharepoint-configure4.png) 

5. Füllen Sie **auf** der Seite Lern-App-Inhaltsrepository die Liste SharePoint den Lerninhaltsordnern mit URLs auf.

   1. Wählen **Sie Neu** aus, um den Bereich Neues Element **anzeigen** zu können. 

       ![Seite "Lerninhaltsrepository" in SharePoint die Option Neu.](../media/learning/learning-sharepoint-configure5.png)
 
   2. Fügen Sie **im Bereich** Neues Element im Feld **Titel** einen Verzeichnisnamen Ihrer Wahl hinzu. Fügen Sie **im Feld Ordner-URL** die URL dem Lerninhaltsordner hinzu. Klicken Sie auf **Speichern**.

       ![Neuer Elementbereich in SharePoint die Felder Titel und Ordner-URL.](../media/learning/learning-sharepoint-configure6.png)

   3. Die **Seite Lern-App-Inhaltsrepository** wird mit den neuen Lerninhalten aktualisiert.

       ![Seite "Lerninhaltsrepository" in SharePoint, auf der die aktualisierten Informationen angezeigt werden.](../media/learning/learning-sharepoint-configure7.png)

> [!NOTE]
> Um einen umfassenderen Zugriff auf das Inhaltsrepository der Lern-App zu ermöglichen, wird in Kürze ein Link zur Liste in der Benutzeroberfläche von Viva Learning (Vorschau) verfügbar sein, auf der Benutzer Zugriff anfordern und letztendlich dazu beitragen können, die Liste auffüllen zu können. Websitebesitzer und globale Administratoren müssen Zugriff auf die Liste gewähren. Der Zugriff ist nur für die Liste spezifisch und gilt nicht für die Website, auf der die Liste gespeichert ist. Weitere Informationen finden Sie weiter unten in diesem Artikel unter [Bereitstellen](#provide-your-own-organizations-content) der Inhalte Ihrer eigenen Organisation.

### <a name="folder-url-document-library-curation"></a>Krümmung der Ordner-URL-Dokumentbibliothek

Standardmetadaten (z. B. geändertes Datum, erstellt durch Dokumentname, Inhaltstyp und Organisationsname) werden von der Microsoft Graph-API automatisch in Das Lernen von Viva Learning (Vorschau) gezogen.
 
Um die allgemeine Such- und Suchrelevanz des Inhalts zu verbessern, empfehlen wir das Hinzufügen einer **Beschreibungsspalte.**

Führen Sie **die** folgenden Schritte aus, um der Dokumentbibliotheksseite eine Beschreibungsspalte hinzuzufügen:

1.  Wählen Sie **auf der** Seite Dokumente die Option Spalte **hinzufügen aus.**

2. Wählen Sie **die Option Aktionen** anzeigen aus, und wählen Sie dann Einzelne **Textzeile aus.**

     ![Seite "Dokumente" in SharePoint zeigt die Optionen Aktionen anzeigen mit hervorgehobener Textzeile.](../media/learning/learning-sharepoint-curation1.png)

3. Fügen Sie **im Bereich** Spalte erstellen im **Feld Name** einen beschreibenden Namen für die Spalte hinzu. Klicken Sie auf **Speichern**.

     ![Erstellen Sie einen Spaltenbereich in SharePoint, in dem der Name und andere Felder angezeigt werden.](../media/learning/learning-sharepoint-curation2.png)
 
4. Fügen Sie **auf** der Seite Dokumente in der **Spalte Beschreibung** benutzerdefinierte Beschreibungen für jedes Element hinzu. Wenn keine Beschreibung angegeben wird, stellt Viva Learning (Vorschau) eine Standardnachricht zur Verfügung, die den Inhalt als aus Ihrer eigenen Bibliothek SharePoint hervorhebt. 

     ![Die Seite Dokumente in SharePoint die Beschreibungen in der Spalte Beschreibung.](../media/learning/learning-sharepoint-curation3.png)
 
### <a name="provide-your-own-organizations-content"></a>Bereitstellen der Inhalte Ihrer eigenen Organisation

Wissensadministratoren können auf das Lern-App-Inhaltsrepository ihrer Organisation in SharePoint zugreifen, wo sie Verweise auf organisationsübergreifende Dokumentbibliotheken bereitstellen können. Inhalte in diesen Bibliotheken werden dann in "Viva Learning" (Vorschau) als Lerninhalte angezeigt.

1. Wählen Sie in Viva Learning (Vorschau) **weitere Optionen** (**...**) aus, und wählen Sie **dann Einstellungen**.

     ![SharePoint Bibliotheksseite, auf der die Option Weitere Optionen und Einstellungen angezeigt wird.](../media/learning/learning-sharepoint-library-1.png)
     
2. Wählen **Einstellungen** unter Berechtigungen **aus.**

     ![Einstellungen option page in SharePoint zeigt die Berechtigungen und Zugriffsoptionen überprüfen.](../media/learning/learning-sharepoint-library-2.png)

3. Wählen **Sie Zugriff überprüfen** aus, um eine Verbindung mit der zentralen Bibliothek Ihrer Organisation herzustellen.
     
