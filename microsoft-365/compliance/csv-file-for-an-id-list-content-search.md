---
title: Vorbereiten einer CSV-Datei für eine ID-Liste Inhaltssuche
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
description: Verwenden Sie eine CSV-Datei aus einer vorhandenen Inhaltssuche, um eine ID-Listensuche zu erstellen, die bestimmte E-Mail-Elemente zurückgibt.
ms.openlocfilehash: 37a398d0896fcfd7b7282bda1f6a549ed9f53601
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311538"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search"></a>Vorbereiten einer CSV-Datei für eine ID-Liste Inhaltssuche

Sie können nach bestimmten Postfach-E-Mail-Nachrichten und anderen Postfachelementen mithilfe einer Liste von Exchange suchen. Um eine ID-Listensuche zu erstellen, übermitteln Sie eine durch Kommata getrennte Wertedatei (CSV), in der Sie die spezifischen Postfachelemente angeben, nach denen Sie suchen. Für diese CSV-Datei verwenden Sie die **Results.csv-Datei** oder die **Nicht indizierte** Items.csv-Datei, die enthalten sind, wenn Sie die Inhaltssuchergebnisse exportieren oder einen Inhaltssuchbericht aus einer vorhandenen Inhaltssuche exportieren. Anschließend bearbeiten Sie eine dieser Dateien, um die zu suchende bestimmten Elemente anzugeben, eine neue ID-Listensuche zu erstellen und die CSV-Datei zu übermitteln.

**Warum eine ID-Listensuche erstellen?** Wenn Sie nicht ermitteln können, ob ein Element auf eine eDiscovery-Anforderung basierend auf den Metadaten in den **Results.csv-** oder **Nicht indizierten Items.csv-Dateien** reagiert, können Sie eine ID-Listensuche verwenden, um dieses Element zu suchen, in der Vorschau anzuzeigen und dann zu exportieren, um festzustellen, ob es auf den untersuchten Fall reagiert. Id-Listensuchen werden in der Regel verwendet, um nach einer bestimmten Gruppe nicht indizierter Elemente zu suchen und diese zurückzukehren.

Hier finden Sie eine kurze Übersicht über den Prozess zum Erstellen einer ID-Listensuche.

1. Erstellen und ausführen Sie eine neue Suche im Microsoft 365 Compliance Center.

2. Exportieren Sie die Inhaltssuchergebnisse oder den Inhaltssuchbericht. Weitere Informationen finden Sie unter:

    - [Ergebnisse der Inhaltssuche exportieren ](export-search-results.md)

    - [Bericht zur Inhaltssuche exportieren](export-a-content-search-report.md)

3. Bearbeiten Sie **Results.csv** oder **Nicht indizierte Items.csv,** und identifizieren Sie die bestimmten Postfachelemente, die in die ID-Listensuche aufgenommen werden sollen. Weitere Informationen [finden Sie in](#prepare-the-csv-file-for-an-id-list-search) den Anweisungen zum Vorbereiten einer CSV-Datei für eine ID-Listensuche.

4. Erstellen Sie eine neue ID-Listensuche (siehe [Anweisungen),](#create-an-id-list-search)und übermitteln Sie die vorbereitete CSV-Datei. Die erstellte Suchabfrage sucht nur nach den in der CSV-Datei ausgewählten Elementen.

> [!NOTE]
> Id-Listensuchen werden nur für Postfachelemente unterstützt. Sie können nicht nach Dokumenten SharePoint und OneDrive in einer ID-Listensuche suchen.

## <a name="prepare-the-csv-file-for-an-id-list-search"></a>Vorbereiten der CSV-Datei für eine ID-Listensuche

Nachdem Sie die Suchergebnisse oder den Bericht für eine Suche exportiert haben, führen Sie die folgenden Schritte aus, um die CSV-Datei für eine ID-Listensuche vorzubereiten. Diese CSV-Datei identifiziert jedes Element in der ID-Listensuche.

Sie können eine CSV-Datei aus einer Suche verwenden, die SharePoint websites und OneDrive-Konten enthielt, Aber Sie können nur Postfachelemente für eine ID-Listensuche auswählen. Wenn Sie ein Dokument in SharePoint oder OneDrive auswählen, kann die CSV-Datei beim Erstellen einer ID-Listensuche nicht validiert werden.

1. Öffnen Sie **Results.csv** **oder Nicht indizierte Items.csv** in Excel.

2. Geben Sie in der **Spalte** Ausgewählt in der Zelle **Ja** ein, die dem Element entspricht, nach dem Sie suchen möchten. Wiederholen Sie diesen Schritt für jedes Element, nach dem Sie suchen möchten.

    > [!IMPORTANT]
    > Wenn Sie die CSV-Datei in Excel öffnen, wurde das Datenformat für die Spalte **Dokument-ID** möglicherweise in **Allgemein geändert.** Dies führt dazu, dass die Dokument-ID für ein Element in der wissenschaftlichen Notation angezeigt wird. Beispielsweise wird die Dokument-ID "481037338205" als "4.81037E+11" angezeigt. In diesem Fall müssen Sie die nächsten Schritte ausführen, um das Datenformat der Spalte **Dokument-ID** in **Zahl** zu ändern, um das richtige Format für die Dokument-ID wiederherzustellen. Wenn Sie dies nicht tun, wird bei der ID-Listensuche, die die CSV-Datei verwendet, ein Fehler angezeigt.

3. Klicken Sie mit der rechten Maustaste auf die gesamte **Spalte Dokument-ID,** und wählen Sie **Zellen formatieren aus.**

4. Klicken Sie **im Feld Kategorie** auf **Nummer**.

5. Ändern Sie die Anzahl der Dezimalstellen in **0**, und klicken Sie dann auf **OK,** um Die Änderungen zu speichern. Beachten Sie, dass die Werte in der Spalte Dokument-ID in Zahlen geändert werden.

    Im Folgenden finden Sie ein Beispiel für eine CSV-Datei, die für eine ID-Listeninhaltssuche übermittelt werden kann.

    ![Beispiel für eine CSV-Datei für eine gezielte Inhaltssuche](../media/SearchIDListCSVFile.png)

6. Speichern Sie die CSV-Datei, oder verwenden **Sie Speichern unter,** um die Datei mit einem anderen Dateinamen zu speichern. Achten Sie in beiden Fällen darauf, die Datei im CSV-Format zu speichern.

## <a name="create-an-id-list-search"></a>Erstellen einer ID-Listensuche

Im nächsten Schritt erstellen Sie eine neue ID-Listensuche und übermitteln die CSV-Datei, die Sie im vorherigen Schritt vorbereitet haben.

> [!IMPORTANT]
> Sie sollten eine ID-Listensuche nicht mehr als 2 Tage nach dem Exportieren der Suchergebnisse oder Berichte erstellen. Wenn die Suchergebnisse oder berichte, in denen vor mehr als 2 Tagen exportiert wurden, sollten Sie die Suchergebnisse oder den Bericht erneut exportieren, um aktualisierte CSV-Dateien zu generieren. Anschließend können Sie eine der aktualisierten CSV-Dateien vorbereiten und verwenden, um eine ID-Listensuche zu erstellen.

1. Gehen Sie auf <https://compliance.microsoft.com>, und melden Sie sich an.

2. Klicken Sie im linken Navigationsbereich des Microsoft 365 Compliance Centers auf **Alle anzeigen** und dann auf **Inhaltssuche**.

3. Klicken Sie **auf der Seite** Inhaltssuche auf Suche nach **ID-Liste**.

4. Nennen Sie **im Flyout** Suche nach ID-Liste die Suche (und beschreiben Sie sie optional), und klicken Sie dann auf **Durchsuchen,** und wählen Sie die CSV-Datei aus, die Sie im vorherigen Schritt vorbereitet haben.

    Microsoft 365 versucht, die CSV-Datei zu überprüfen. Wenn die Überprüfung nicht erfolgreich war, wird eine Fehlermeldung angezeigt, die Ihnen bei der Problembehandlung der Überprüfungsfehler helfen kann. Die CSV-Datei muss erfolgreich überprüft werden, um eine ID-Listensuche zu erstellen.

5. Nachdem die CSV-Datei erfolgreich überprüft wurde, klicken Sie auf **Suchen,** um die ID-Listensuche zu erstellen.

    Hier ist ein Beispiel für die Flyoutseite aus einer ID-Listensuche, die die generierte Abfrage und die geschätzte Anzahl von Suchergebnissen zeigt.

    ![Suchabfrage für id list search](../media/SearchIDListFlyout.png)

    Die Anzahl der geschätzten Elemente, die in Statistiken für die ID-Suche angezeigt werden, sollte mit der Anzahl der Elemente übereinstimmen, die Sie in der CSV-Datei ausgewählt haben.

6. Anzeigen oder Exportieren der von der ID-Listensuche zurückgegebenen Elemente.

## <a name="more-information"></a>Weitere Informationen

Wenn Sie ein Postfach nach dem Erstellen einer ID-Listensuche verschieben, gibt die Abfrage für die Suche die angegebenen Elemente nicht zurück. Das liegt daran, dass die **DocumentId-Eigenschaft** für Postfachelemente geändert wird, wenn ein Postfach verschoben wird. In der seltenen Instanz, in der ein Postfach nach dem Erstellen einer ID-Listensuche verschoben wird, sollten Sie eine neue Inhaltssuche erstellen (oder die Suchergebnisse für eine vorhandene Suche aktualisieren) und dann die Suchergebnisse oder den Bericht exportieren, um aktualisierte CSV-Dateien zu generieren, die zum Erstellen einer neuen ID-Listensuche verwendet werden können.
