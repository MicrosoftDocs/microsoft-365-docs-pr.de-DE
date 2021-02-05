---
title: Verwalten der Themenermittlung in Microsoft -Themen
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Erfahren Sie, wie Sie die Themenermittlung in Microsoft Topics verwalten.
ms.openlocfilehash: 36b64433726479dc2a46c809ae9504c6f12f4ab8
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107759"
---
# <a name="manage-topic-discovery-in-microsoft-viva-topics"></a>Verwalten der Themenermittlung in Microsoft -Themen

Sie können Die Themenermittlungseinstellungen im [Microsoft 365 Admin Center verwalten.](https://admin.microsoft.com) Sie müssen ein globaler Administrator oder ein SharePoint-Administrator sein, um diese Aufgaben ausführen zu können.

## <a name="to-access-topics-management-settings"></a>So greifen Sie auf Die Themenverwaltungseinstellungen zu:

1. Klicken Sie im Microsoft 365 Admin Center auf **"Einstellungen"** und dann auf **"Organisationseinstellungen".**
2. Klicken Sie **auf der** Registerkarte "Dienste" auf **"Themenerfahrungen".**

    ![Verbinden von Personen mit Wissen](../media/admin-org-knowledge-options-completed.png) 

3. Wählen Sie die **Registerkarte "Themenermittlung"** aus. Informationen zu den einzelnen Einstellungen finden Sie in den folgenden Abschnitten.

    ![knowledge-network-settings](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a>Auswählen von SharePoint-Themenquellen

Sie können die SharePoint-Websites in Ihrer Organisation ändern, die nach Themen gecrawlt werden.

Wenn Sie eine bestimmte Liste von Websites ein- oder ausschließen möchten, können Sie die folgende .csv-Vorlage verwenden:

``` csv
Site name,URL
```

Wenn Sie Websites mithilfe der Websiteauswahl hinzufügen, werden sie der vorhandenen Liste der Websites hinzugefügt, die ein- oder ausgeschlossen werden sollen. Wenn Sie eine CSV-Datei hochladen, werden alle vorhandenen Listen überschrieben. Wenn Sie zuvor bestimmte Websites eingeschlossen oder ausgeschlossen haben, laden Sie die Liste als CSV-Datei herunter, nehmen Sie Änderungen vor, und laden Sie die neue Liste hoch.

So wählen Sie Websites für die Themenermittlung aus

1. Wählen Sie **auf der Registerkarte "Themenermittlung"** unter **"SharePoint-Themenquellen auswählen"** die Option **"Bearbeiten" aus.**
2. Wählen Sie **auf der Seite "SharePoint-Themenquellen** auswählen" aus, welche SharePoint-Websites während der Suche als Quellen für Ihre Themen durchforstet werden. Dies umfasst Folgendes:
    - **Alle Websites:** Alle SharePoint-Websites in Ihrem Mandanten. Dadurch werden aktuelle und zukünftige Websites erfasst.
    - **Alle, mit Ausnahme ausgewählter Websites:** Geben Sie die Namen der Websites ein, die Sie ausschließen möchten.  Sie können auch eine Liste der Websites hochladen, für die Sie die Suche abmelden möchten. Websites, die in Zukunft erstellt werden, werden als Quellen für die Themenermittlung einbezogen. 
    - **Nur ausgewählte Websites:** Geben Sie die Namen der Websites ein, die Sie enthalten möchten. Sie können auch eine Liste von Websites hochladen. Websites, die in Zukunft erstellt werden, werden nicht als Quellen für die Themenermittlung einbezogen.
    - **Keine Websites:** Themen werden nicht automatisch generiert oder mit SharePoint-Inhalten aktualisiert. Vorhandene Themen verbleiben im Themencenter.

    ![Screenshot der Benutzeroberfläche für SharePoint-Themenquellen](../media/k-manage-select-topic-source.png)
   
3. Klicken Sie auf **Speichern**.

## <a name="exclude-topics-by-name"></a>Ausschließen von Themen nach Namen

Sie können Themen von der Suche ausschließen, indem Sie eine Liste mithilfe einer CSV-Datei hochladen. Wenn Sie zuvor Themen ausgeschlossen haben, können Sie die CSV herunterladen, Änderungen vornehmen und sie erneut hochladen.

1. Wählen Sie **auf der Registerkarte "Themenermittlung"** unter **"Themen ausschließen"** die Option **"Bearbeiten" aus.**
2. Klicken **Sie auf "Themen nach Namen ausschließen".**
3. Wenn Sie eine Liste erstellen müssen, laden Sie die .csv-Vorlage herunter, und fügen Sie die Themen hinzu, die Sie ausschließen möchten (siehe "Arbeiten mit der *CSV-Vorlage"* weiter unten). Wenn die Datei bereit ist, klicken Sie auf **"Durchsuchen",** und laden Sie die Datei hoch. Wenn eine Liste vorhanden ist, können Sie die CSV herunterladen, die die Liste enthält.
4. Klicken Sie auf **Speichern**.

    ![Screenshot der Benutzeroberfläche "Themen ausschließen"](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a>Arbeiten mit der .csv-Vorlage

Sie können die folgende CSV-Vorlage kopieren:

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

Geben Sie in der Csv-Vorlage die folgenden Informationen zu den Themen ein, die Sie ausschließen möchten:

- **Name**: Geben Sie den Namen des Themas ein, das Sie ausschließen möchten. Sie können auf zwei Arten vorgehen:
    - Genaue Übereinstimmung: Sie können den genauen Namen oder das Akronym (z. B. *Contoso* oder *ATL) verwenden.*
    - Teilweise Übereinstimmung: Sie können alle Themen ausschließen, in denen ein bestimmtes Wort enthalten ist.  Der Bogen *schließt* z. B. alle Themen aus, *in* denen der Wortbogen enthalten ist, z. B. Bogenkreis,  *Arkusbogen* oder *Schulungsbogen.* Beachten Sie, dass Themen, in denen der Text als Teil eines Worts enthalten ist, wie z. B. Architektur, nicht *ausgeschlossen werden.*
- **Steht für (optional):** Wenn Sie ein Akronym ausschließen möchten, geben Sie die Wörter ein, für die das Akronym steht.
- **MatchType-Exact/Partial**: Geben Sie ein, ob der eingegebene Name ein *exakter* oder teilweiser *Übereinstimmungstyp* war.

    ![Ausschließen von Themen in der CSV-Vorlage](../media/exclude-topics-csv.png) 

## <a name="see-also"></a>Siehe auch

[Verwalten der Sichtbarkeit von Themen in Microsoft 365](topic-experiences-knowledge-rules.md)

[Verwalten von Themenberechtigungen in Microsoft 365](topic-experiences-user-permissions.md)

[Ändern des Namens des Themencenters in Microsoft 365](topic-experiences-administration.md)
