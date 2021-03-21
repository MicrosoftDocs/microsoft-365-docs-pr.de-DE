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
description: Informationen zum Einrichten von Microsoft Viva Topics
ms.openlocfilehash: 629008e083d71e09632b05e21eaefb011d7d9ce2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929444"
---
# <a name="set-up-microsoft-viva-topics"></a>Einrichten von Microsoft Viva Topics

Sie können das Microsoft 365 Admin Center zum Einrichten und Konfigurieren von [Themen verwenden.](topic-experiences-overview.md) 

Es ist wichtig, die beste Methode zum Einrichten und Konfigurieren von Themen in Ihrer Umgebung zu planen. Lesen Sie unbedingt [Plan for Microsoft Viva Topics,](plan-topic-experiences.md) bevor Sie mit den Verfahren in diesem Artikel beginnen.

Sie müssen ["Viva Topics"](https://www.microsoft.com/microsoft-viva/topics) abonniert haben und ein globaler Administrator oder SharePoint-Administrator sein, um auf das Microsoft 365 Admin Center zu zugreifen und Themen einrichten zu können.

Wenn Sie SharePoint so konfiguriert haben, [dass verwaltete](/sharepoint/control-access-from-unmanaged-devices)Geräte erforderlich sind, müssen Sie Themen auf einem verwalteten Gerät einrichten.

## <a name="video-demonstration"></a>Videodemonstration

Dieses Video zeigt den Prozess zum Einrichten von Themen in Microsoft 365.

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="set-up-topics"></a>Einrichten von Themen

So richten Sie Themen ein

1. Wählen Sie [im Microsoft 365 Admin Center](https://admin.microsoft.com) **Setup** aus, und zeigen Sie dann den Abschnitt Dateien **und Inhalte** an.
2. Klicken Sie **im Abschnitt** Dateien und Inhalte auf Personen mit Wissen **verbinden.**

    ![Verbinden von Personen mit Wissen](../media/admin-org-knowledge-options.png) 

3. Klicken Sie **auf der Seite Personen mit Wissen verbinden** auf Erste **Schritte,** um Sie durch den Einrichtungsprozess zu gehen.

    ![Erste Schritte](../media/k-get-started.png) 

4. Auf der **Seite Auswählen, wie Themen von "Themen" zu** finden sind, konfigurieren Sie die Themenermittlung. Wählen Sie **im Abschnitt SharePoint-Themenquellen** auswählen aus, welche SharePoint-Websites während der Suche als Quellen für Ihre Themen durchforstet werden sollen. Wählen Sie zwischen:
    - **Alle Websites**: Alle SharePoint-Websites in Ihrer Organisation. Dies umfasst aktuelle und zukünftige Websites.
    - **Alle, mit Ausnahme ausgewählter Websites:** Geben Sie die Namen der Websites ein, die Sie ausschließen möchten.  Sie können auch eine Liste der Websites hochladen, die Sie von der Ermittlung abmelden möchten. Websites, die in Zukunft erstellt werden, werden als Quellen für die Themenerkennung einbezogen. 
    - **Nur ausgewählte Websites:** Geben Sie die Namen der Websites ein, die Sie enthalten möchten. Sie können auch eine Liste von Websites hochladen. Websites, die in Zukunft erstellt werden, werden nicht als Quellen für die Themenerkennung einbezogen.
    - **Keine Websites**: Keine SharePoint-Websites enthalten.

    ![Auswählen des Suchens von Themen](../media/ksetup1.png) 
   
5. Im Abschnitt **Themen nach Name** ausschließen können Sie Namen von Themen hinzufügen, die Sie von der Themenermittlung ausschließen möchten. Verwenden Sie diese Einstellung, um zu verhindern, dass vertrauliche Informationen als Themen einbezogen werden. Mögliche Optionen:
    - **Keine Themen ausschließen** 
    - **Ausschließen von Themen nach Namen**

    ![Ausschließen von Themen](../media/topics-excluded-by-name.png) 

    (Wissensmanager können auch Themen im Themencenter nach der Ermittlung ausschließen.)

    #### <a name="how-to-exclude-topics-by-name"></a>So schließen Sie Themen nach Namen aus    

    Wenn Sie Themen ausschließen müssen, laden Sie nach auswahl von Themen nach Name ausschließen die CSV-Vorlage herunter, und aktualisieren Sie sie mit der Liste der Themen, die Sie aus Ihren Ermittlungsergebnissen ausschließen möchten. 

    ![Ausschließen von Themen in der CSV-Vorlage](../media/exclude-topics-csv.png) 

    Geben Sie in der CSV-Vorlage die folgenden Informationen zu den Themen ein, die Sie ausschließen möchten:

    - **Name**: Geben Sie den Namen des Themas ein, das Sie ausschließen möchten. Sie können auf zwei Arten vorgehen:
        - Genaue Übereinstimmung: Sie können den genauen Namen oder das Akronym (z. B. *Contoso* oder *ATL) eingeben.*
        - Teilweise Übereinstimmung: Sie können alle Themen ausschließen, in denen ein bestimmtes Wort enthalten ist.  Der Bogen schließt *beispielsweise* alle Themen  aus, in denen der Wortbogen enthalten ist, z. B. Bogenkreis, Lichtbogenverschwesung oder *Schulungsbogen.*  Beachten Sie, dass Themen, in denen der Text als Teil eines Worts enthalten ist, wie z. B. Architektur, nicht *ausgeschlossen werden.*
    - **Steht für (optional)**: Wenn Sie ein Akronym ausschließen möchten, geben Sie die Wörter ein, für die das Akronym steht.
    - **MatchType-Exact/Partial**: Geben Sie ein, ob der eingegebene Name ein exakter oder *teilweiser* *Übereinstimmungstyp* war.

    Nachdem Sie die CSV-Datei abgeschlossen und gespeichert haben, wählen Sie **Durchsuchen** aus, um sie zu suchen und auszuwählen.
    
    Wählen Sie **Weiter** aus.

6. Auf der **Seite Wer kann Themen sehen und wo kann** sie angezeigt werden, konfigurieren Sie die Sichtbarkeit des Themas. In der **Einstellung Themen** anzeigen können wählen Sie aus, wer Zugriff auf Themendetails hat, z. B. hervorgehobene Themen, Themenkarten, Themenantworten in der Suche und Themenseiten. Sie können wählen:
    - **Jeder in meiner Organisation**
    - **Nur ausgewählte Personen oder Sicherheitsgruppen**
    - **Niemand**

    ![Wer Kann Themen sehen](../media/ksetup2.png)  

    > [!Note] 
    > Mit dieser Einstellung können Sie zwar beliebige Benutzer in Ihrer Organisation auswählen, aber nur Benutzer, denen Themenerfahrungslizenzen zugewiesen sind, können Themen anzeigen.

7. Auf der **Seite Berechtigungen für die Themenverwaltung** wählen Sie aus, wer Themen erstellen, bearbeiten oder verwalten kann. Im Abschnitt **Wer kann Themen erstellen und** bearbeiten, können Sie folgende Auswahl auswählen:
    - **Jeder in meiner Organisation**
    - **Nur ausgewählte Personen oder Sicherheitsgruppen**
    - **Niemand**

    ![Berechtigungen für die Themenverwaltung, die Themen erstellen und bearbeiten können](../media/ksetup3.png) 

8. Im Abschnitt **Wer kann Themen verwalten,** können Sie folgende Option auswählen:
    - **Jeder in meiner Organisation**
    - **Nur ausgewählte Personen oder Sicherheitsgruppen**

    ![Berechtigungen für die Themenverwaltung](../media/km-setup-create-edit-topics.png) 

    Wählen Sie **Weiter** aus.

9. Auf der **Seite Themencenter erstellen** können Sie Ihre Themencenterwebsite erstellen, auf der Themenseiten angezeigt und Themen verwaltet werden können. Geben Sie **im Feld** Websitename einen Namen für Ihr Themencenter ein. Optional können Sie eine kurze Beschreibung in das Feld **Beschreibung** eingeben. 

   Wählen Sie **Weiter** aus.

   ![Erstellen von Knowledge Center](../media/ksetup4.png)  

10. Auf der Seite **Überprüfen und beenden** können Sie sich die ausgewählte Einstellung ansehen und Änderungen vornehmen. Wenn Sie mit Ihrer Auswahl zufrieden sind, wählen Sie **Aktivieren** aus.

11. Die **aktivierte Seite "Viva Topics"** wird angezeigt, um zu bestätigen, dass das System nun mit der Analyse der ausgewählten Websites für Themen beginnt und die Themencenterwebsite erstellt. Wählen Sie **Fertig** aus.

12. Sie werden an Ihre Seite Personen mit Wissen verbinden **zurückgegeben.** Auf dieser Seite können Sie **Verwalten** auswählen, um Änderungen an Ihren Konfigurationseinstellungen vorzunehmen. 

    ![Angewendete Einstellungen](../media/ksetup7.png)    

Beachten Sie, dass es bei der ersten Aktivierung der Themenermittlung bis zu zwei Wochen dauern kann, bis alle vorgeschlagenen Themen in der Ansicht Themen verwalten angezeigt werden. Die Themenermittlung wird fortgesetzt, wenn neue Inhalte oder Aktualisierungen von Inhalten vorgenommen werden. Es ist normal, dass es Schwankungen bei der Anzahl vorgeschlagener Themen in Ihrer Organisation gibt, wenn Neue Informationen von Viva Topics ausgewertet werden.

## <a name="assign-licenses"></a>Zuweisen von Lizenzen

Nachdem Sie die Themenerfahrung konfiguriert haben, müssen Sie den Benutzern, die Themen verwenden, Lizenzen zuweisen. Nur Benutzer mit einer Lizenz können Informationen zu Themen wie Highlights, Themenkarten, Themenseiten und dem Themencenter anzeigen. 

So weisen Sie Lizenzen zu

1. Klicken Sie im Microsoft 365 Admin Center auf **Benutzer** > **Aktive Benutzer**.

2. Wählen Sie die Benutzer aus, die Sie lizenzen möchten, und klicken Sie auf **Lizenzen und Apps**.

3. Wählen **Sie unter Lizenzen** die Option Viva Topics **aus.**

4. Stellen **Sie unter Apps** sicher, dass Graph Connectors Search with Index **(Viva Topics)** und Viva **Topics** beide ausgewählt sind.

   > [!div class="mx-imgBorder"]
   > ![Microsoft Viva Topics-Lizenzen im Microsoft 365 Admin Center](../media/topic-experiences-licenses.png)

5. Klicken Sie auf **Änderungen speichern**.

## <a name="manage-topic-experiences"></a>Verwalten von Themenerfahrungen

Nachdem Sie Themen eingerichtet haben, können Sie die Einstellungen ändern, die Sie beim Setup im [Microsoft 365 Admin Center ausgewählt haben.](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement) Sehen Sie sich die folgenden Verweise an:

- [Verwalten der Themensuche in Microsoft Viva Topics](topic-experiences-discovery.md)
- [Verwalten der Sichtbarkeit von Themen in Microsoft Viva Topics](topic-experiences-knowledge-rules.md)
- [Verwalten von Themenberechtigungen in Microsoft Viva Topics](topic-experiences-user-permissions.md)
- [Ändern des Namens des Themencenters in Microsoft Viva Topics](topic-experiences-administration.md)

## <a name="see-also"></a>Siehe auch

[Übersicht über Die Themenerfahrungen](topic-experiences-overview.md)
