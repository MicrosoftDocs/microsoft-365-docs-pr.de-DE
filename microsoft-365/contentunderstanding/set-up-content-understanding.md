---
title: 'Einrichten des Inhalts Verständnisses (Vorschau) '
description: So richten Sie Project Cortex ein.
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 5fcc7f78bfc12faae19ce2a3fbc77c4348da01de
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612702"
---
# <a name="set-up-content-understanding-preview"></a>Einrichten des Inhalts Verständnisses (Vorschau)

> [!Note] 
> Der Inhalt dieses Artikels ist für Project Cortex private Preview. [Erfahren Sie mehr über Project Cortex](https://aka.ms/projectcortex).

Administratoren können das Microsoft 365 Admin Center verwenden, um das Verständnis von Inhalten einzurichten und zu konfigurieren. 

Stellen Sie vor dem einrichten sicher, dass Sie die beste Möglichkeit zum Einrichten und Konfigurieren des Inhalts Verständnisses in Ihrer Umgebung planen. Beispielsweise müssen Sie Überlegungen zu den folgenden Aspekten treffen:
- Auf welchen SharePoint-Websites wird die Formularverarbeitung aktiviert? Alle, einige, oder wählen Sie Websites aus?
- Name Ihres inhaltscenters und wer ist der primäre Websiteadministrator?

Ein Administrator kann Änderungen an den ausgewählten Einstellungen auch jederzeit nach dem Setup über die Verwaltungseinstellungen für Inhalte im Microsoft 365 Admin Center vornehmen.


## <a name="requirements"></a>Anforderungen 
Sie müssen über globale Administrator-oder SharePoint-Administratorberechtigungen verfügen, um auf das Microsoft 365 Admin Center zugreifen und das Verständnis für Inhalte einrichten zu können.


## <a name="to-set-up-content-understanding"></a>So richten Sie das Verständnis von Inhalten ein

1. Wählen Sie im Microsoft 365 Admin Center die Option **Setup**aus, und zeigen Sie dann den Abschnitt **organisatorisches Wissen** an.
2. Wählen Sie im Abschnitt **organisatorisches Wissen** die Option **Inhalts Verständnis automatisieren**aus.<br/>

    ![Setup Seite für organisatorisches Wissen](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. Klicken Sie auf der Seite zum **Automatisieren des Inhalts Verständnisses** auf **Erste Schritte** , um Sie durch den Setupprozess zu führen.<br/>

    ![Setup starten](../media/content-understanding/admin-content-understanding-get-started.png)</br>


4. Auf der Seite **Formularverarbeitung konfigurieren** können Sie auswählen, ob Benutzer in der Lage sein sollen, Ai Builder zum Erstellen von Formular Verarbeitungs Modellen in bestimmten SharePoint-Dokumentbibliotheken zu verwenden. Im Menüband der Dokumentbibliothek wird eine Menüoption zur Verfügung stehen, um **ein Formular Verarbeitungsmodell** in SharePoint-Dokumentbibliotheken zu erstellen, in denen es aktiviert ist.
 
     Für **welche SharePoint-Bibliotheken die Option zum Erstellen eines Formular Verarbeitungsmodells anzeigen soll**, können Sie Folgendes auswählen:</br>
    - **Alle SharePoint-Bibliotheken** , um Sie allen SharePoint-Bibliotheken in Ihrem Mandanten zur Verfügung zu stellen.</br>
    - **Nur Bibliotheken an ausgewählten Websites**, und wählen Sie dann die Websites aus, in denen Sie verfügbar sein sollen.</br>
    - **Keine SharePoint-Bibliotheken** , wenn Sie Sie derzeit nicht für Websites verfügbar machen möchten (Dies können Sie nach dem Setup ändern).
</br>

   ![Konfigurieren der Formularverarbeitung](../media/content-understanding/admin-configforms.png)
</br>

   > [!Note]
   > Das Aktivieren dieser Einstellung für eine SharePoint-Dokumentbibliothek wirkt sich nicht auf vorhandene Modelle aus, die auf die Bibliothek angewendet werden, oder auf die Möglichkeit, Dokument Verständnis Modelle auf eine Bibliothek anzuwenden. 

    
5. Auf der Seite **inhaltscenter erstellen** können Sie eine SharePoint-inhaltscenter-Website erstellen, auf der Ihre Benutzerdokument Verständnis Modelle erstellen und verwalten können. </br>
    a. Geben Sie unter **Websitename**den Namen ein, den Sie Ihrer inhaltscenter-Website zuweisen möchten.</br>
    b. Die **Websiteadresse** zeigt basierend auf dem, was Sie für den Websitenamen ausgewählt haben, die URL für Ihre Website an.</br>

    > [!Note] 
    > Sie können zwar eine beliebige unterstützte Sprache auswählen, beachten Sie jedoch, dass Inhalte, die Modelle verstehen, nur für Englisch erstellt werden können.</br>

      ![Inhaltscenter erstellen](../media/content-understanding/admin-cu-create-cc.png)</br>


    Wählen Sie **Weiter** aus.
6. Auf der Seite **Fertig stellen und überprüfen** können Sie sich Ihre ausgewählte Einstellung ansehen und auswählen, dass Sie Änderungen vornehmen möchten. Wenn Sie mit Ihrer Auswahl zufrieden sind, wählen Sie **aktivieren**aus.



7. Die Seite zur **Aktivierung des Inhalts Verständnisses** wird angezeigt und bestätigt, dass das System Ihre Formular Verarbeitungseinstellungen hinzugefügt und die Inhalts Center-Website erstellt hat. Wählen Sie **Fertig** aus.

8. Sie kehren zu Ihrer Seite zum **Automatisieren von Inhalten** zurück. Auf dieser Seite können Sie **Verwalten** auswählen, um Änderungen an Ihren Konfigurationseinstellungen vorzunehmen. 

## <a name="see-also"></a>Siehe auch



  






