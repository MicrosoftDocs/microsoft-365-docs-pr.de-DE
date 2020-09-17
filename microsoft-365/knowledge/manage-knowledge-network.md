---
title: 'Verwalten Ihres Wissens Verwaltungsnetzwerks (Vorschau) '
description: Einrichten der Wissensverwaltung
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 3ca180dba82e677dbc0d9f112b713df14820ce61
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950772"
---
# <a name="manage-your-knowledge-management-network-preview"></a>Verwalten Ihres Wissens Verwaltungsnetzwerks (Vorschau)

> [!Note] 
> Der Inhalt dieses Artikels ist für Project Cortex private Preview. [Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).


Nachdem Sie das [Knowledge Management eingerichtet](set-up-knowledge-network.md)haben, kann ein Administrator zu jeder Zeit Anpassungen an Ihren Konfigurationseinstellungen über das Microsoft 365 Admin Center vornehmen.

Beispielsweise müssen Sie die Einstellungen für Folgendes anpassen:
- Hinzufügen von neuen SharePoint-Quellen zu Minen Themen.
- Ändern der Benutzer, die auf Themen zugreifen können
- Ändern Sie, welche Benutzerberechtigungen für Aufgaben im Themen Center haben.
- Ändern des Namens Ihres Themen Centers


## <a name="requirements"></a>Anforderungen 
Sie müssen über globale Administrator-oder SharePoint-Administratorberechtigungen verfügen, um auf das Microsoft 365 Admin Center zugreifen und organisatorische Wissens Aufgaben verwalten zu können.


## <a name="to-access-knowledge-management-settings"></a>So greifen Sie auf Wissens Verwaltungseinstellungen zu:

1. Wählen Sie im Microsoft 365 Admin Center die Option **Setup**aus, und zeigen Sie dann den Abschnitt **organisatorisches Wissen** an.
2. Klicken Sie im Abschnitt **organisatorisches Wissen** auf **Personen mit Wissen verbinden**.<br/>

    ![Verbinden von Personen mit wissen](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. Wählen Sie auf der Seite mit den **Informationen zum Benutzer verbinden** die Option **Manage** aus, um den Bereich **Wissensnetzwerk Einstellungen** zu öffnen.<br/>

    ![Wissen-Netzwerk-Einstellungen](../media/content-understanding/knowledge-network-settings.png) </br>

## <a name="change-how-the-knowledge-network-can-find-topics"></a>Ändern, wie das Wissensnetzwerk Themen finden kann

Wählen Sie die Registerkarte **Thema Ermittlung** aus, wenn Sie Ihre Auswahlmöglichkeiten für SharePoint-Themen Quellen aktualisieren möchten. Mit dieser Einstellung können Sie die SharePoint-Websites in Ihrem Mandanten auswählen, die durchforstet und für Themen abgebaut werden.

1. Wählen Sie auf der Registerkarte **Thema Discovery** unter **SharePoint-Themen Quellen auswählen**die Option **Bearbeiten**aus.
2. Wählen Sie auf der Seite **SharePoint-Themen Quellen auswählen** aus, welche SharePoint-Websites während der Ermittlung als Quellen für Ihre Themen gecrawlt werden sollen. Dies umfasst Folgendes:</br>
    a. **Alle Websites**: alle SharePoint-Websites in Ihrem Mandanten. Dadurch werden aktuelle und zukünftige Websites erfasst.</br>
    b. **Alle, außer ausgewählte Websites**: Geben Sie die Namen der Websites ein, die Sie ausschließen möchten.  Sie können auch eine Liste der Websites hochladen, für die Sie die Ermittlung deaktivieren möchten. In der Zukunft erstellte Websites werden als Quellen für die Themen Ermittlung hinzugefügt. </br>
    c. **Nur ausgewählte Websites**: Geben Sie die Namen der Websites ein, die Sie einschließen möchten. Sie können auch eine Liste der Websites hochladen. In der Zukunft erstellte Websites werden nicht als Quellen für die Themen Ermittlung einbezogen. </br>

    ![Auswählen der Suche nach Themen](../media/content-understanding/k-manage-select-topic-source.png) </br>
   
    Wenn Sie über eine Reihe von Websites verfügen, die Sie ausschließen möchten (wenn Sie **Alle auswählen, außer ausgewählte Websites**) oder einbeziehen (wenn Sie **nur ausgewählte Websites**ausgewählt haben), können Sie eine CSV-Datei mit den Websitenamen und-URLs hochladen. Sie können die Option **Download Site Template. CSV** auswählen, wenn Sie die CSV-Vorlagendatei verwenden möchten.

3. Wählen Sie **Speichern** aus.

##  <a name="change-who-can-see-topics-in-your-organization"></a>Ändern der Personen, die Themen in Ihrer Organisation anzeigen können

Wählen Sie die Registerkarte **Thema Ermittlung** aus, wenn Sie aktualisieren möchten, wer in Ihrer Organisation entdeckte Themen in Suchergebnissen sehen kann und wann Themen in Inhalten wie SharePoint-Seiten hervorgehoben werden.

1. Wählen Sie auf der Registerkarte **Thema Discovery** unter **wer Themen im Wissensnetzwerk anzeigen kann die**Option **Bearbeiten**aus.
2. Auf der Seite " **Wer kann Themen auf der Wissensnetzwerk Seite sehen** " wählen Sie aus, wer Zugriff auf Themen Details haben soll, wie beispielsweise hervorgehobene Themen, Themenkarten, Themen Antworten auf der Suche und Themenseiten. Sie können Folgendes auswählen:</br>
    a. **Jeder in Ihrer Organisation**</br>
    b. **Nur ausgewählte Personen oder Sicherheitsgruppen**</br>
    c. **Niemand**</br>

    ![Wer Themen sehen kann](../media/content-understanding/k-manage-who-can-see-topics.png) </br> 
3. Wählen Sie **Speichern** aus.  
 
> [!Note] 
> Während Sie mit dieser Einstellung einen beliebigen Benutzer in Ihrer Organisation auswählen können, können nur Benutzer, denen Lizenzen für Wissensmanagement zugewiesen sind, Themen anzeigen.

## <a name="change-who-has-permissions-to-do-tasks-on-the-topic-center"></a>Ändern der Berechtigungen für Aufgaben im Themen Center

Wählen Sie die Registerkarte **Thema Berechtigungen** aus, wenn Sie aktualisieren möchten, wer über Berechtigungen für Folgendes auf der Seite "Themen Center" verfügt:

- Die Benutzer können Themen erstellen und bearbeiten: Erstellen Sie neue Themen, die während der Suche nicht gefunden wurden, oder bearbeiten Sie vorhandene Themenseiten Details.
- Welche Benutzer Themen verwalten können: bestätigen oder ablehnen erkannter Themen.

So aktualisieren Sie die Benutzer, die Berechtigungen zum Erstellen und Bearbeiten von Themen haben:

1. Wählen Sie auf der Registerkarte **Thema Berechtigungen** unter **Wer kann Themen erstellen und bearbeiten**aus die Option **Bearbeiten**aus.</br>
2. Auf der Seite für die **Erstellung und Bearbeitung von Themen** können Sie Folgendes auswählen:</br>
    a. **Jeder in Ihrer Organisation**</br>
    b. **Nur ausgewählte Personen oder Sicherheitsgruppen**</br>

    ![Erstellen und Bearbeiten von Themen](../media/content-understanding/k-manage-who-can-create-and-edit.png) </br> 

3. Wählen Sie **Speichern** aus.</br>

So aktualisieren Sie, wer über Berechtigungen zum Verwalten von Themen verfügt:

1. Wählen Sie auf der Registerkarte **Thema Berechtigungen** unter **Benutzer können Themen verwalten die**Option **Bearbeiten**aus.</br>
2. Auf der Seite **Themen, die Themen verwalten können** , können Sie Folgendes auswählen:</br>
    a. **Jeder in Ihrer Organisation**</br>
    b. **Ausgewählte Personen oder Sicherheitsgruppen**</br>

    ![Verwalten von Themen](../media/content-understanding/k-manage-who-can-manage-topics.png) </br> 

3. Wählen Sie **Speichern** aus.</br>


##  <a name="update-your-topic-center-name"></a>Aktualisieren des Namens des Themen Centers

Wählen Sie die Registerkarte **Topic Center** aus, wenn Sie den Namen Ihres Themen Centers aktualisieren möchten. 

1. Wählen Sie auf der Registerkarte **Themen Center** unter **Name des Themas**" **Bearbeiten**" aus.
2. Geben Sie auf der Seite **Themen Center Namen bearbeiten** im Feld **Themen Center Name** den neuen Namen für Ihr Themen Center ein.
3. Wählen Sie **Speichern** aus.

    ![Bearbeiten des Themen Center namens](../media/content-understanding/manage-topic-center-name.png) </br> 











## <a name="see-also"></a>Siehe auch



  






