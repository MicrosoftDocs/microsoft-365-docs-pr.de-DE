---
title: 'Arbeiten mit Themen im Themen Center (Vorschau) '
description: Vorgehensweise zum Arbeiten mit Themen im Thema Center.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: e4a9917464e22c6220d26619e7b5ca60f090abb7
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612490"
---
# <a name="work-with-topics-in-the-topic-center-preview"></a>Arbeiten mit Themen im Themen Center (Vorschau)

> [!Note] 
> Der Inhalt dieses Artikels ist für Project Cortex private Preview. [Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).


Im Themen Center kann ein Wissensmanager Themen überprüfen, die in den von Ihnen angegebenen SharePoint-Quell Standorten abgebaut und erkannt wurden, und Sie können Sie entweder bestätigen oder ablehnen. Ein Knowledge Manager kann auch neue Themenseiten erstellen und veröffentlichen, wenn diese nicht in der Themen Erkennung gefunden wurden, oder vorhandene bearbeiten, wenn Sie aktualisiert werden müssen.

## <a name="requirements"></a>Anforderungen

Um im Themen Center arbeiten zu können, müssen Sie über die erforderlichen Berechtigungen verfügen. Ihr Administrator kann Sie während des [Knowledge Management-Setups](set-up-knowledge-network.md)hinzufügen, oder anschließend können neue Benutzer [hinzugefügt](give-user-permissions-to-the-topic-center.md)werden.

Topic Center Benutzer können zwei Berechtigungssätze erhalten:

- Themen erstellen und bearbeiten: neue Themen erstellen oder Themen Inhalte wie Beschreibung, Dokumente und zugehörige Personen aktualisieren
- Themen verwalten: Verwenden Sie das Themen Verwaltungs Dashboard, um Themen in der gesamten Organisation zu überprüfen. Benutzer können Aktionen wie das bestätigen und ablehnen von Themen ausführen


## <a name="review-unconfirmed-topics"></a>Überprüfen unbestätigter Themen

Auf der Startseite des Themen Centers werden Themen, die in den angegebenen SharePoint-Quell Standorten ermittelt wurden, auf der Registerkarte nicht **bestätigt** angezeigt. Ein Benutzer mit Berechtigungen zum Verwalten von Themen kann unbestätigte Themen überprüfen und auswählen, ob diese bestätigt oder abgelehnt werden sollen.


So überprüfen Sie ein unbestätigtes Thema:

1. Wählen Sie auf der Registerkarte nicht **bestätigt** das Thema aus, um die Themen Seite zu öffnen.</br>

2. Lesen Sie auf der Seite Thema die Seite Thema, und wählen Sie **Bearbeiten** aus, wenn Sie Änderungen an der Seite vornehmen müssen.
3. Auf der Knowledge Center-Startseite für das ausgewählte Thema können Sie Folgendes tun:</br>
    a. Aktivieren Sie das Kontrollkästchen, um zu bestätigen, dass Sie das Thema beibehalten möchten.</br>
    b. Wählen Sie das **x** aus, wenn Sie das Thema ablehnen möchten.</br>

    Bestätigte Themen werden aus der **unbestätigten** Liste entfernt und werden jetzt auf der Registerkarte **bestätigt** angezeigt.</br>

    Abgelehnte Themen werden aus der **unbestätigten** Liste entfernt und werden nun auf der Registerkarte **abgelehnt oder ausgeschlossen** angezeigt.</br>
    
   
## <a name="create-a-new-topic"></a>Erstellen eines neuen Themas

Ein Benutzer mit Berechtigungen zum Erstellen oder Bearbeiten von Themen kann bei Bedarf ein neues Thema erstellen. Dies ist möglicherweise erforderlich, wenn das Thema nicht durch Discovery erkannt wurde oder wenn die AI-Technologie nicht genügend Beweise gefunden hat, um Sie als Thema zu etablieren.

So erstellen Sie ein neues Thema:
1. Wählen Sie auf der Seite Topic Center die Option **neu**und dann **Themen Seite**aus.</br>

    ![Neues Thema](../media/content-understanding/k-new-topic.png) </br>

2. Auf der Seite Neues Thema können Sie die Informationen zur neuen Thema Vorlage eingeben:</br>
    a. Geben Sie im Abschnitt **Name dieses Themas** den Namen des neuen Themas ein.</br>
    b. Geben Sie im Abschnitt **Alternative Namen** Namen oder Akronyme ein, die auch zum besprechen des Themas verwendet werden.</br>
    c. Geben Sie im Abschnitt **kurze Beschreibung** eine Beschreibung des Themas ein oder zwei Sätze ein. Dieser Text wird für die zugeordnete Themenkarte verwendet.</br>
    d. Geben Sie im Abschnitt **Personen** die Namen der Experten für Sachverständige für das Thema ein.</br>
    e. Wählen Sie im Abschnitt **Dateien und Seiten** die Option **Hinzufügen** aus, und wählen Sie dann auf der nächsten Seite zugeordnete OneDrive-Dateien oder SharePoint Online Seiten aus.</br>
    f. Wählen Sie im Abschnitt **Websites** die Option **Hinzufügen**aus. Wählen Sie im Bereich **Websites** , der angezeigt wird, die Websites aus, die dem Thema zugeordnet sind.</br>

    ![Neue Themen Seite](../media/content-understanding/k-new-topic-page.png) </br>
3. Wenn Sie der Seite weitere Komponenten hinzufügen müssen, wie Text, Bilder, Webparts, Links usw., wählen Sie das Canvas-Symbol in der Mitte der Seite aus, um Sie zu suchen und hinzuzufügen.
    ![Hinzufügen von Elementen zur Seite](../media/content-understanding/static-icon.png) </br> 

4. Wenn Sie fertig sind, wählen Sie **veröffentlichen** aus, um die Seite Thema zu veröffentlichen. Veröffentlichte Themenseiten werden auf der Registerkarte **Seiten** angezeigt.

> [!Note] 
> Die neue Themen Seite besteht aus Webparts, die *Knowledge Network-fähig*sind. Dies bedeutet, dass, wenn AI mehr Informationen zum Thema sammelt, die Informationen in diesen Webparts mit Vorschlägen aktualisiert werden, um die Seite für Benutzer nützlicher zu machen.


## <a name="edit-an-existing-topic-page"></a>Bearbeiten einer vorhandenen Themen Seite

Vorhandene Themenseiten befinden sich auf der Seite **Seiten** . 

1. Wählen Sie auf der Seite Themen Center die Option **Seiten**aus.</br>
2. Auf der Seite **Seiten** wird eine Liste der Themenseiten angezeigt. Verwenden Sie das Suchfeld, um die Themen Seite zu finden, die Sie aktualisieren möchten. Klicken Sie auf den Namen der Themen Seite, die Sie bearbeiten möchten.</br>
3. Wählen Sie auf der Seite Thema die Option **Bearbeiten**aus. </br>
4. Nehmen Sie die erforderlichen Änderungen an der Seite vor. Dies umfasst Aktualisierungen für die folgenden Felder:</br>
    a. Alternative Namen</br>
    b. Beschreibung</br>
    c. Personen</br>
    d. Dateien und Seiten</br>
    e. Websites</br>
    f. Sie können der Seite auch statische Elemente hinzufügen, beispielsweise Text, Bilder oder Links, indem Sie das Canvas-Symbol auswählen.</br>

5. Wählen Sie **erneut veröffentlichen** aus, um die Änderungen zu speichern.

## <a name="see-also"></a>Siehe auch



  






