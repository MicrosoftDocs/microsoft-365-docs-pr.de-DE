---
title: Einrichten von Microsoft Viva Topics
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Erfahren Sie, wie Sie Microsoft Viva Topics einrichten
ms.openlocfilehash: 42f84b9b792907d7fe118e0b15c3767674ddf19b
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229587"
---
# <a name="set-up-microsoft-viva-topics"></a>Einrichten von Microsoft Viva Topics

Sie können die Microsoft 365 Admin Center verwenden, um [Topics](topic-experiences-overview.md)einzurichten und zu konfigurieren. 

Es ist wichtig, die beste Methode zum Einrichten und Konfigurieren von Themen in Ihrer Umgebung zu planen. Lesen Sie unbedingt ["Plan für Microsoft Viva Topics",](plan-topic-experiences.md) bevor Sie mit den Verfahren in diesem Artikel beginnen.

Sie müssen [Viva Topics abonniert](https://www.microsoft.com/microsoft-viva/topics) haben und ein globaler Administrator oder SharePoint Administrator sein, um auf die Microsoft 365 Admin Center zugreifen und Topics einrichten zu können.

Wenn Sie SharePoint so konfiguriert haben, dass [verwaltete Geräte erforderlich](/sharepoint/control-access-from-unmanaged-devices)sind, müssen Sie Themen von einem verwalteten Gerät einrichten.

## <a name="video-demonstration"></a>Videodemonstration

Dieses Video zeigt den Prozess zum Einrichten von Themen in Microsoft 365.

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="assign-licenses"></a>Zuweisen von Lizenzen

Sie müssen Lizenzen für die Benutzer zuweisen, die Topics verwenden. Nur Benutzer mit einer Lizenz können Informationen zu Themen wie Highlights, Themenkarten, Themenseiten und dem Themencenter sehen. 

So weisen Sie Lizenzen zu

1. Klicken Sie im Microsoft 365 Admin Center auf **Benutzer** > **Aktive Benutzer**.

2. Wählen Sie die Benutzer aus, die Sie lizenzen möchten, und klicken Sie auf **"Lizenzen und Apps".**

3. Wählen Sie unter **Lizenzen** **Viva Topics** aus.

4. Stellen Sie unter **"Apps"** sicher, dass **Graph Connectors-Suche mit Index (Viva Topics)** und **Viva Topics** ausgewählt sind.

   > [!div class="mx-imgBorder"]
   > ![Microsoft Viva Topics-Lizenzen im Microsoft 365 Admin Center](../media/topic-experiences-licenses.png)

5. Klicken Sie auf **Änderungen speichern**.

Es kann bis zu einer Stunde dauern, bis Benutzer zugriff auf Topics erhalten, nachdem die Lizenzen zugewiesen wurden.

## <a name="set-up-topics"></a>Einrichten von Themen

> [!Note]
> Wenn die Themensuche zum ersten Mal aktiviert ist, kann es bis zu zwei Wochen dauern, bis alle vorgeschlagenen Themen in der Ansicht "Themen verwalten" angezeigt werden. Die Themensuche wird fortgesetzt, wenn neue Inhalte oder Aktualisierungen an Inhalten vorgenommen werden. Es ist normal, dass die Anzahl der vorgeschlagenen Themen in Ihrer Organisation Schwankungen aufweist, wenn Viva Topics neue Informationen auswertet.

So richten Sie Themen ein
1. Wählen Sie im [Microsoft 365 Admin Center](https://admin.microsoft.com) **setup** aus, und zeigen Sie dann den Abschnitt **"Dateien und Inhalt"** an.
2. Klicken Sie im Abschnitt **"Dateien und Inhalt"** auf **Verbinden Personen wissen.**

    ![Verbinden Von Personen zu Wissen](../media/admin-org-knowledge-options.png) 

3. Klicken Sie auf der **Seite Verbinden Personen zu Wissen** auf **"Erste Schritte",** um Sie durch den Einrichtungsprozess zu führen.

    ![Erste Schritte](../media/k-get-started.png) 

4. Auf der Seite **"Auswählen, wie Viva Topics Themen finden kann"** konfigurieren Sie die Themensuche. Wählen Sie im Abschnitt **"SharePoint Themenquellen auswählen"** aus, welche SharePoint Websites während der Suche als Quellen für Ihre Themen durchforstet werden. Wählen Sie zwischen:
    - **Alle Websites**: Alle SharePoint-Websites in Ihrer Organisation. Dies schließt aktuelle und zukünftige Websites ein.
    - **Alle, außer ausgewählten Websites:** Geben Sie die Namen der Websites ein, die Sie ausschließen möchten.  Sie können auch eine Liste der Websites hochladen, die Sie von der Ermittlung abmelden möchten. Websites, die in Zukunft erstellt werden, werden als Quellen für die Themensuche einbezogen. 
    - **Nur ausgewählte Websites:** Geben Sie die Namen der Websites ein, die Sie einschließen möchten. Sie können auch eine Liste von Websites hochladen. Zukünftig erstellte Websites werden nicht als Quellen für die Themensuche einbezogen.
    - **Keine Websites**: Schließen Sie keine SharePoint-Websites ein.

    ![Auswählen, wie Themen gesucht werden sollen](../media/ksetup1.png) 
   
5. Im Abschnitt **"Themen nach Namen ausschließen"** können Sie Namen von Themen hinzufügen, die Sie von der Themensuche ausschließen möchten. Verwenden Sie diese Einstellung, um zu verhindern, dass vertrauliche Informationen als Themen eingeschlossen werden. Mögliche Optionen:
    - **Themen nicht ausschließen** 
    - **Ausschließen von Themen nach Name**

    ![Themen ausschließen](../media/topics-excluded-by-name.png) 

    (Wissensmanager können auch Themen im Themencenter nach der Ermittlung ausschließen.)

    #### <a name="how-to-exclude-topics-by-name"></a>Ausschließen von Themen nach Namen    

    Wenn Sie Themen ausschließen müssen, laden Sie nach dem Auswählen **von "Themen ausschließen" anhand des Namens** die vorlage .csv herunter, und aktualisieren Sie sie mit der Liste der Themen, die Sie aus Ihren Ermittlungsergebnissen ausschließen möchten.

    ![Ausschließen von Themen in csv-Vorlage](../media/exclude-topics-csv.png) 

    Geben Sie in der CSV-Vorlage die folgenden Informationen zu den Themen ein, die Sie ausschließen möchten:

    - **Name**: Geben Sie den Namen des Themas ein, das ausgeschlossen werden soll. Sie können auf zwei Arten vorgehen:
        - Genaue Übereinstimmung: Sie können den genauen Namen oder das Akronym angeben (z. B. *Contoso* oder *ATL).*
        - Partielle Übereinstimmung: Sie können alle Themen ausschließen, die ein bestimmtes Wort enthalten.  Beispielsweise schließt *Arc* alle Themen mit dem Wort *Bogen* aus, z. B. *Arc Circle,* *Arc Arc-* oder *Training Arc.* Beachten Sie, dass Themen, in denen der Text als Teil eines Worts enthalten ist, wie z. B. *Architektur,* nicht ausgeschlossen werden.
    - **Steht für (optional):** Wenn Sie ein Akronym ausschließen möchten, geben Sie die Wörter ein, für die das Akronym steht.
    - **MatchType-Exact/Partial:** Geben Sie an, ob der eingegebene Name ein *exakter* oder *teilweiser* Übereinstimmungstyp war.

    Nachdem Sie Die .csv-Datei abgeschlossen und gespeichert haben, wählen Sie **"Durchsuchen"** aus, um sie zu suchen und auszuwählen.
    
    Wählen Sie **Weiter** aus.

6. Auf der **Wer Themen anzeigen können und wo diese angezeigt** werden, konfigurieren Sie die Themensichtbarkeit. In der Wer die **Themeneinstellung anzeigen können,** wählen Sie aus, wer Zugriff auf Themendetails hat, z. B. hervorgehobene Themen, Themenkarten, Themenantworten in der Suche und Themenseiten. Sie können Folgendes auswählen:
    - **Jeder in meiner Organisation**
    - **Nur ausgewählte Personen oder Sicherheitsgruppen**
    - **Niemand**

    ![Wer können Themen anzeigen](../media/ksetup2.png)  

    > [!Note] 
    > Mit dieser Einstellung können Sie zwar einen beliebigen Benutzer in Ihrer Organisation auswählen, aber nur Benutzer, denen Themenerfahrungslizenzen zugewiesen sind, können Themen anzeigen.

7. Auf der Seite **"Berechtigungen für die Themenverwaltung"** wählen Sie aus, wer Themen erstellen, bearbeiten oder verwalten kann. In the **Wer can create and edit topics** section, you can select:
    - **Jeder in meiner Organisation**
    - **Nur ausgewählte Personen oder Sicherheitsgruppen**
    - **Niemand**

    ![Berechtigungen für die Themenverwaltung, die Themen erstellen und bearbeiten können](../media/ksetup3.png) 

8. In the **Wer can manage topics** section, you can select:
    - **Jeder in meiner Organisation**
    - **Nur ausgewählte Personen oder Sicherheitsgruppen**

    ![Berechtigungen für die Themenverwaltung](../media/km-setup-create-edit-topics.png) 

    Wählen Sie **Weiter** aus.

9. Auf der Seite **"Themencenter** erstellen" können Sie Ihre Themencenterwebsite erstellen, auf der Themenseiten angezeigt und Themen verwaltet werden können. Geben Sie im **Feld "Websitename"** einen Namen für Ihr Themencenter ein. Sie können auf das Stiftsymbol klicken, wenn Sie die URL ändern möchten. Geben Sie optional eine kurze Beschreibung in das **Feld Beschreibung** ein. 

   > [!Important]
   > Sie können den Websitenamen später ändern, aber sie können die URL nach Abschluss des Assistenten nicht mehr ändern.

   Wählen Sie **Weiter** aus.

   ![Erstellen des Wissenscenters](../media/ksetup4.png)  

10. Auf der Seite **Überprüfen und beenden** können Sie sich die ausgewählte Einstellung ansehen und Änderungen vornehmen. Wenn Sie mit Ihrer Auswahl zufrieden sind, wählen Sie **Aktivieren** aus.

11. Die **aktivierte** Viva Topics-Seite wird angezeigt und bestätigt, dass das System nun mit der Analyse Ihrer ausgewählten Websites für Themen und dem Erstellen der Themencenterwebsite beginnt. Wählen Sie **Fertig** aus.

12. Sie werden zu Ihrer **Verbinden Seite "Personen zu Wissen"** zurückgegeben. Auf dieser Seite können Sie **Verwalten** auswählen, um Änderungen an Ihren Konfigurationseinstellungen vorzunehmen. 

    ![angewendete Einstellungen](../media/ksetup7.png)    

## <a name="manage-topic-experiences"></a>Verwalten von Themenerfahrungen

Nachdem Sie Topics eingerichtet haben, können Sie die Einstellungen ändern, die Sie während der Einrichtung im [Microsoft 365 Admin Center](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)ausgewählt haben. Sehen Sie sich die folgenden Verweise an:

- [Verwalten der Themensuche in Microsoft Viva Topics](topic-experiences-discovery.md)
- [Verwalten der Sichtbarkeit von Themen in Microsoft Viva Topics](topic-experiences-knowledge-rules.md)
- [Verwalten von Themenberechtigungen in Microsoft Viva Topics](topic-experiences-user-permissions.md)
- [Ändern des Namens des Themencenters in Microsoft Viva Topics](topic-experiences-administration.md)

## <a name="see-also"></a>Siehe auch

[Übersicht über Themenerfahrungen](topic-experiences-overview.md)
