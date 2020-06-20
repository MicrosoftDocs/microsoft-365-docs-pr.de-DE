---
title: Erstellen einer CSV-Datei für eine Inhaltssuche anhand der ID-Liste
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
ms.assetid: 82c97bb4-2b64-4edc-804d-cedbda525d22
ms.custom:
- seo-marvel-apr2020
description: Verwenden Sie CSV-Dateien aus einer vorhandenen Inhaltssuche, um eine ID-Listensuche zu erstellen, die bestimmte e-Mail-Nachrichten zurückgibt.
ms.openlocfilehash: 7b63a78d34306cf3afcef49276e584bc816c107f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817974"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search"></a>Erstellen einer CSV-Datei für eine Inhaltssuche anhand der ID-Liste

Sie können mithilfe einer Liste von Exchange-IDs nach bestimmten Post Fachnachrichten und anderen Postfachelementen suchen. Um eine ID-Listensuche (formell als gezielte Suche bezeichnet) zu erstellen, senden Sie eine CSV-Datei (Comma Separated Value), die die zu suchenden Postfachelemente identifiziert. Für diese CSV-Datei verwenden Sie die **Results.csv** Datei oder die nicht **Indexierte Items.csv** Datei, die beim Exportieren der Inhalts Suchergebnisse oder beim Exportieren eines Inhalts Suchberichts aus einer vorhandenen Inhaltssuche enthalten ist. Bearbeiten Sie dann eine dieser Dateien, um anzugeben, nach welchen Elementen gesucht werden soll, und erstellen Sie dann eine neue ID-Listensuche, und senden Sie die CSV-Datei.

Im folgenden finden Sie eine kurze Übersicht über den Prozess zum Erstellen einer ID-Listensuche.

1. Erstellen Sie eine neue oder geführte Inhaltssuche im Security & Compliance Center, und führen Sie Sie aus.

2. Exportieren Sie die Inhalts Suchergebnisse, oder exportieren Sie den Bericht zur Inhaltssuche. Weitere Informationen finden Sie unter:

    - [Exportieren von Inhaltssuchergebnissen ](export-search-results.md)

    - [Exportieren eines Inhaltssuchberichts](export-a-content-search-report.md)

3. Bearbeiten Sie die **Results.csv** Datei oder den nicht **indizierten Items.csv** , und identifizieren Sie die spezifischen Postfachelemente, die in die ID-Listensuche einbezogen werden sollen. Lesen Sie die [Anweisungen](#prepare-the-csv-file-for-an-id-list-search) zum Vorbereiten einer CSV-Datei für eine ID-Listensuche.

4. Erstellen Sie eine neue ID-Listensuche (Lesen Sie die [Anweisungen](#create-an-id-list-search)), und übermitteln Sie die vorbereitete CSV-Datei. Die erstellte Suchabfrage sucht nur nach den Elementen, die in der CSV-Datei ausgewählt sind.

> [!NOTE]
> Die Suche von ID-Listen wird nur für Postfachelemente unterstützt. Sie können nicht nach SharePoint-und OneDrive-Dokumenten in einer ID-Listensuche suchen.

 **Gründe für die Erstellung einer ID-Listensuche** Wenn Sie nicht ermitteln können, ob ein Element auf einer eDiscovery-Anforderung basierend auf den Metadaten in den **Results.csv** -oder nicht **indizierten Items.csv** -Dateien reagiert, können Sie eine ID-Listensuche verwenden, um das Element zu suchen, in der Vorschau anzuzeigen und dann zu exportieren, um zu ermitteln, ob es auf den Fall reagiert, den Sie untersuchen. ID-Listensuche wird in der Regel zum Suchen und Zurückgeben einer bestimmten Gruppe von nicht indizierten Elementen verwendet.

## <a name="prepare-the-csv-file-for-an-id-list-search"></a>Vorbereiten der CSV-Datei für eine ID-Listensuche

Nachdem Sie die Suchergebnisse oder den Bericht für eine Inhaltssuche exportiert haben, können Sie die folgenden Schritte ausführen, um die CSV-Datei für eine ID-Listensuche vorzubereiten. In dieser CSV-Datei werden alle Elemente in der ID-Listensuche identifiziert.

Beachten Sie, dass Sie eine CSV-Datei aus einer Suche verwenden können, die SharePoint-Websites und OneDrive-Konten enthielt, aber Sie können *nur* Postfachelemente für eine ID-Listensuche auswählen. Wenn Sie ein Dokument in SharePoint oder OneDrive auswählen, wird die Überprüfung der CSV-Datei beim Erstellen einer ID-Listensuche nicht ausgeführt.

1. Öffnen Sie die Items.csvDatei **Results.csv** oder nicht **indiziert** in Excel.

2. Geben Sie in der **ausgewählten** Spalte **Ja** in die Zelle ein, die dem Element entspricht, nach dem Sie suchen möchten. Wiederholen Sie diesen Schritt für jedes Element, nach dem Sie suchen möchten.

    > [!IMPORTANT]
    > Wenn Sie die CSV-Datei in Excel öffnen, wird das Datenformat für die **Dokument-ID-** Spalte in " **Allgemein**" geändert. Dies führt dazu, dass die Dokument-ID für ein Element in der wissenschaftlichen Notation angezeigt wird. Beispielsweise wird die Dokument-ID "481037338205" als "4.81037 e + 11" angezeigt. Sie müssen die nächsten Schritte durchführen, um das Datenformat der Spalte " **Dokument-ID** " in " **Number** " zu ändern, um das richtige Format für die Dokument-ID wiederherzustellen. Wenn Sie dies nicht tun, schlägt die ID-Listensuche, in der die CSV-Datei verwendet wird, fehl.

3. Klicken Sie mit der rechten Maustaste auf die gesamte Spalte **Dokument-ID** , und wählen Sie **Zellen formatieren**aus.

4. Klicken Sie im Feld **Kategorie** auf **Zahl**.

5. Ändern Sie die Anzahl der Dezimalstellen in **0**, und klicken Sie dann auf **OK** , um die Änderungen zu speichern. Beachten Sie, dass die Werte in der Spalte "Dokument-ID" in Zahlen geändert wurden.

    Im folgenden finden Sie ein Beispiel für eine CSV-Datei, die für eine ID-Listeninhalts Suche gesendet werden kann.

    ![Beispiel für eine CSV-Datei für eine gezielte Inhaltssuche](../media/8371b8cb-1638-496e-9be1-fe1565757d67.png)

6. Speichern Sie die CSV-Datei, oder **Speichern Sie die** Datei unter anderem Dateinamen speichern. In beiden Fällen müssen Sie die Datei im CSV-Format speichern.

## <a name="create-an-id-list-search"></a>Erstellen einer ID-Listensuche

Im nächsten Schritt erstellen Sie eine neue ID-Listeninhalts Suche und übermitteln die CSV-Datei, die Sie im vorherigen Schritt vorbereitet haben.

> [!IMPORTANT]
> Sie sollten eine ID-Listensuche nicht länger als 2 Tage nach dem Exportieren der Ergebnisse oder des Berichts aus einer Inhaltssuche erstellen. Wenn die Suchergebnisse oder der Bericht vor mehr als 2 Tagen exportiert wurden, sollten Sie die Suchergebnisse oder den Bericht erneut exportieren, um aktualisierte CSV-Dateien zu generieren. Anschließend können Sie eine der aktualisierten CSV-Dateien vorbereiten und Sie zum Erstellen einer ID-Listensuche verwenden.

1. Wechseln Sie im Security & Compliance Center zu **Such** \> **Inhaltssuche**.

2. Klicken Sie auf der Seite **Suchen** auf den Pfeil neben ![ Symbol ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **neue Suche**hinzufügen, und klicken Sie dann auf **nach ID-Liste suchen**.

    ![Klicken Sie in der Dropdownliste neue Suche auf nach ID-Liste suchen.](../media/e65f9942-09b2-4127-865e-e64029a590df.png)

3. Geben Sie im Flyout **Suche nach ID-Liste** den Namen der Suche ein (und beschreiben Sie Sie optional), und klicken Sie dann auf **Durchsuchen** , und wählen Sie dann die CSV-Datei aus, die Sie im vorherigen Schritt vorbereitet haben.

    Microsoft 365 versucht, die CSV-Datei zu überprüfen. Wenn die Überprüfung nicht erfolgreich ist, wird eine Fehlermeldung angezeigt, die Ihnen helfen kann, die Validierungsfehler zu beheben. Die CSV-Datei muss erfolgreich überprüft werden, um eine ID-Listensuche zu erstellen.

4. Nachdem die CSV-Datei erfolgreich überprüft wurde, klicken Sie auf **Suchen** , um die ID-Listensuche zu erstellen.

    Im folgenden finden Sie ein Beispiel für die geschätzten Suchergebnisse und die Abfrage, die für eine ID-Listensuche generiert wurde.

    ![Suchabfrage für eine gezielte Inhaltssuche im Detailbereich](../media/dbd9e570-c04b-4056-a8a7-37e9916ec683.png)

    Beachten Sie, dass die Anzahl der geschätzten Elemente, die in Statistik für die ID-Suche angezeigt werden, mit der Anzahl der Elemente übereinstimmen sollte, die Sie in der CSV-Datei ausgewählt haben.

5. Vorschau oder Exportieren der Elemente, die von der ID-Listensuche zurückgegeben werden.

> [!NOTE]
> Wenn Sie ein Postfach nach dem Erstellen einer ID-Listensuche migrieren, gibt die Abfrage für die Suche nicht die angegebenen Elemente zurück. Das liegt daran, dass die **Document** -Eigenschaft für Postfachelemente geändert wird, wenn ein Postfach verschoben wird. In der seltenen Instanz, in der ein Postfach verschoben wird, nachdem Sie eine ID-Listensuche erstellt haben, sollten Sie eine neue Inhaltssuche erstellen (oder die Suchergebnisse für die vorhandene Inhaltssuche aktualisieren) und dann die Suchergebnisse oder den Bericht exportieren, um aktualisierte CSV-Dateien zu generieren, mit denen eine neue ID-Listensuche erstellt werden kann.
