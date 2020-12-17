---
title: Verwalten der Themen Ermittlung in Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Erfahren Sie, wie Sie die Themen Ermittlung in Microsoft 365 verwalten.
ms.openlocfilehash: dec8aeef9dda390fb19f5067638c2ebea6b6a2fe
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698543"
---
# <a name="manage-topic-discovery-in-microsoft-365"></a>Verwalten der Themen Ermittlung in Microsoft 365

Sie können Themen Ermittlungs Einstellungen im [Microsoft 365 Admin Center](https://admin.microsoft.com)verwalten. Sie müssen ein globaler Administrator oder SharePoint-Administrator sein, um diese Aufgaben ausführen zu können.

## <a name="to-access-topics-management-settings"></a>So greifen Sie auf Themen Verwaltungseinstellungen zu:

1. Klicken Sie im Microsoft 365 Admin Center auf **Einstellungen** und dann auf **org-Einstellungen**.
2. Klicken Sie auf der Registerkarte **Dienste** auf **Wissensnetzwerk**.

    ![Verbinden von Personen mit wissen](../media/admin-org-knowledge-options-completed.png) 

3. Wählen Sie die Registerkarte **Thema Discovery** aus. In den folgenden Abschnitten finden Sie Informationen zu den einzelnen Einstellungen.

    ![Wissen-Netzwerk-Einstellungen](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a>Auswählen von SharePoint-Themen Quellen

Sie können die SharePoint-Websites in Ihrer Organisation ändern, die nach Themen durchforstet werden.

Wenn Sie eine bestimmte Liste von Websites einschließen oder ausschließen möchten, können Sie die folgende CSV-Vorlage verwenden:

``` csv
Site name,URL
```

Wenn Sie Websites mithilfe der Websiteauswahl hinzufügen, werden Sie der vorhandenen Liste der einzuschließenden oder auszuschließenden Websites hinzugefügt. Wenn Sie eine CSV-Datei hochladen, werden alle vorhandenen Listen überschrieben. Wenn Sie zuvor bestimmte Websites einbezogen oder ausgeschlossen haben, können Sie die Liste als CSV-Datei herunterladen, Änderungen vornehmen und die neue Liste hochladen.

So wählen Sie Websites für die Themen Ermittlung aus

1. Wählen Sie auf der Registerkarte **Thema Discovery** unter **SharePoint-Themen Quellen auswählen** die Option **Bearbeiten** aus.
2. Wählen Sie auf der Seite **SharePoint-Themen Quellen auswählen** aus, welche SharePoint-Websites während der Ermittlung als Quellen für Ihre Themen gecrawlt werden sollen. Hierzu zählen Folgende:
    - **Alle Websites**: alle SharePoint-Websites in Ihrem Mandanten. Dadurch werden aktuelle und zukünftige Websites erfasst.
    - **Alle, außer ausgewählte Websites**: Geben Sie die Namen der Websites ein, die Sie ausschließen möchten.  Sie können auch eine Liste der Websites hochladen, für die Sie die Ermittlung deaktivieren möchten. In der Zukunft erstellte Websites werden als Quellen für die Themen Ermittlung hinzugefügt. 
    - **Nur ausgewählte Websites**: Geben Sie die Namen der Websites ein, die Sie einschließen möchten. Sie können auch eine Liste der Websites hochladen. In der Zukunft erstellte Websites werden nicht als Quellen für die Themen Ermittlung einbezogen.
    - **Keine Websites**: Themen werden nicht automatisch generiert oder mit SharePoint-Inhalten aktualisiert. Vorhandene Themen verbleiben im Themen Center.

    ![Screenshot der SharePoint-Themen Quellen-Benutzeroberfläche](../media/k-manage-select-topic-source.png)
   
3. Klicken Sie auf **Speichern**.

## <a name="exclude-topics-by-name"></a>Themen nach Namen ausschließen

Sie können Themen aus der Ermittlung ausschließen, indem Sie eine Liste mithilfe einer CSV-Datei hochladen. Wenn Sie Themen zuvor ausgeschlossen haben, können Sie die CSV-Datei herunterladen, Änderungen vornehmen und erneut hochladen.

1. Wählen Sie auf der Registerkarte **Thema Discovery** unter **Themen ausschließen** die Option **Bearbeiten** aus.
2. Klicken Sie auf **Themen nach Namen ausschließen**.
3. Wenn Sie eine Liste erstellen möchten, laden Sie die CSV-Vorlage herunter, und fügen Sie die auszuschließenden Themen hinzu (siehe *Arbeiten mit der CSV-Vorlage* unten). Wenn die Datei verfügbar ist, klicken Sie auf **Durchsuchen** , und laden Sie die Datei hoch. Wenn eine Liste vorhanden ist, können Sie die CSV-Datei herunterladen, die die Liste enthält.
4. Klicken Sie auf **Speichern**.

    ![Screenshot der Benutzeroberfläche zum Ausschließen von Themen](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a>Arbeiten mit der CSV-Vorlage

Sie können die CSV-Vorlage unten kopieren:

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

Geben Sie in der CSV-Vorlage die folgenden Informationen zu den Themen ein, die Sie ausschließen möchten:

- **Name**: Geben Sie den Namen des Themas ein, das Sie ausschließen möchten. Sie können auf zwei Arten vorgehen:
    - Exakte Übereinstimmung: Sie können den genauen Namen oder das Akronym angeben (beispielsweise *contoso* oder *ATL*).
    - Partielle Übereinstimmung: Sie können alle Themen ausschließen, die ein bestimmtes Wort enthalten.  Beispielsweise schließt *Bogen* alle Themen mit dem Wort *Bogen* in ihm aus, wie *Bogen Kreis*, *Plasma Schweißen* oder *Schulungs Bogen*. Beachten Sie, dass die Themen, in denen der Text als Teil eines Wortes eingeschlossen ist, wie etwa die *Architektur*, nicht ausgeschlossen werden.
- **Steht für (optional)**: Wenn Sie ein Akronym ausschließen möchten, geben Sie die Wörter ein, für die die Abkürzung steht.
- **MatchType-Exact/Partial**: Geben Sie an, ob es sich bei dem von Ihnen eingegebenen Namen um einen *genauen* oder *partiellen* Übereinstimmungs handelt.

    ![Themen in CSV-Vorlage ausschließen](../media/exclude-topics-csv.png) 

## <a name="see-also"></a>Siehe auch

[Verwalten der Themen Sichtbarkeit in Microsoft 365](topic-experiences-knowledge-rules.md)

[Verwalten von Themen Berechtigungen in Microsoft 365](topic-experiences-user-permissions.md)

[Ändern des Namens des Themen Centers in Microsoft 365](topic-experiences-administration.md)
