---
title: Bildoptimierung für SharePoint Online klassischen Veröffentlichungswebsites
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 9/18/2019
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: c7edb02a-fdab-4f91-9a20-cba01dad28ef
description: In diesem Artikel erfahren Sie, wie Sie mithilfe von Formatvarianten und Sprites die Bildleistung auf Ihren SharePoint Online klassischen Veröffentlichungswebsites verbessern.
ms.openlocfilehash: 47d0f085c13c192417842fcef88c695fe875124c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690525"
---
# <a name="image-optimization-for-sharepoint-online-classic-publishing-sites"></a>Bildoptimierung für SharePoint Online klassischen Veröffentlichungswebsites

Die Ladegeschwindigkeit einer Webseite hängt von der kombinierten Größe aller Komponenten ab, die zum Rendern der Seite erforderlich sind, einschließlich Bildern, HTML, JavaScript und CSS. Bilder sind eine großartige Möglichkeit, um Ihre Website attraktiver zu machen, aber ihre Größe kann die Leistung beeinträchtigen. Durch Optimieren der Bilder mit Komprimierung und Größenanpassung und Verwenden von Sprites können Sie die Effekte sehr großer Bilder kompensieren. Mithilfe von SharePoint-Bildwiedergaben können Sie ein einzelnes großes Bild hochladen und Abschnitte des Bilds anzeigen, die das wieder verwenden und nicht das erneute Laden ermöglichen.

>[!NOTE]
>Dieses Thema bezieht sich auf SharePoint Online klassischen Veröffentlichungswebsites und nicht auf moderne Portalwebsites. Informationen zur Bildoptimierung in SharePoint Online modernen Portalwebsites finden Sie unter [Optimieren von Bildern auf SharePoint Online modernen Portalseiten](modern-image-optimization.md).
  
## <a name="using-sprites-to-speed-up-image-loading"></a>Verwenden von Sprites zum Beschleunigen des Ladens von Bildern

|||
|:-----|:-----|
| Ein Bild-Sprite enthält viele kleinere Bilder. Mit CSS wählen Sie einen Teil des zusammengesetzten Bilds aus, der auf einem bestimmten Teil der Seite mit absoluter Positionierung angezeigt werden soll. Im Grunde bewegen Sie ein einzelnes Bild um die Seite, anstatt mehrere Bilder zu laden, und machen einen kleinen Teil dieses Bilds durch ein kleines Fenster sichtbar, in dem der erforderliche Teil des Sprite-Bilds dem Endbenutzer angezeigt wird. SharePoint Online verwendet Sprites, um die verschiedenen Symbole im Sprite-spcommon.png anzuzeigen.  <br/>  Was ist hier behandelt:  <br/>  Bildkomprimierung  <br/>  Bildoptimierung  <br/>  SharePoint-Bildwiedergaben  <br/> |![Screenshot von "Common"](../media/cc5cdee1-8e54-4537-9a8a-8854f4ee849f.png)|
   
Dies kann die Leistung verbessern, da Sie nur ein Bild anstelle von mehreren herunterladen und dieses Bild dann Zwischenspeichern und wieder verwenden. Selbst wenn das Bild nicht zwischengespeichert bleibt, indem es ein einzelnes Bild anstelle von mehreren Bildern aufweist, reduziert diese Methode die Gesamtzahl der HTTP-Anforderungen an den Server, wodurch die Seitenladezeiten reduziert werden. Dies ist wirklich eine Form der Bild Bündelung. Dies ist eine sehr nützliche Technik, wenn sich die Bilder nicht sehr häufig ändern, beispielsweise Symbole, wie im obigen SharePoint-Beispiel dargestellt. Sie können die Verwendung von [WebEssentials](https://vswebessentials.com/), ein Community-basiertes Open-Source-Projekt eines Drittanbieters, verwenden, um dies problemlos in Microsoft Visual Studio zu erreichen. Weitere Informationen finden Sie unter [Minimierungs und Bündelung in SharePoint Online](https://go.microsoft.com/fwlink/?LinkId=708698).
  
## <a name="using-image-compression-and-optimization-to-speed-up-page-loading"></a>Verwenden von Bildkomprimierung und Optimierung zum Beschleunigen des Seitenladevorgangs

Bei der Bildkomprimierung und-Optimierung geht es um die Verringerung der Dateigröße der Bilder, die Sie auf Ihrer Website verwenden. Die beste Methode zum Verringern der Größe eines Bilds ist häufig die Größe des Bilds auf die maximalen Abmessungen, die auf der Website angezeigt werden. Es hat keinen Sinn, ein Bild zu haben, das größer ist, als es jemals angezeigt wird. Wenn Sie sicherstellen möchten, dass die Bilder mit einem Bild-Editor korrekt dimensioniert sind, können Sie die Größe Ihrer Seite schnell und einfach reduzieren.
  
Sobald Bilder die richtige Größe haben, besteht der nächste Schritt darin, die Komprimierung dieser Bilder zu optimieren. Für die Komprimierung und Optimierung stehen verschiedene Tools zur Verfügung, einschließlich Fotogalerie und Tools von Drittanbietern. Der Schlüssel zur Komprimierung besteht darin, die Dateigröße so weit wie möglich zu reduzieren, ohne dass die Qualität der Endbenutzer erkennbar ist. Stellen Sie sicher, dass Sie Ihre komprimierten Dateien in einer hochauflösenden Anzeige testen, um sicherzustellen, dass Sie weiterhin gut aussehen.
  
## <a name="speed-up-page-downloads-by-using-sharepoint-image-renditions"></a>Beschleunigen der Seitendownloads mithilfe von SharePoint-Bildwiedergaben

Bildwiedergaben sind ein Feature in SharePoint Online, mit dem Sie verschiedene Versionen von Bildern basierend auf vordefinierten Bildabmessungen servieren können. Dies ist besonders wichtig, wenn es Benutzer generierte Bildinhalte gibt oder die Bildabmessungen wie Breite und Höhe durch das CSS auf der Website festgelegt werden. Selbst wenn ein Bild durch CSS fixiert ist, wird das Bild in voller Auflösung immer noch geladen. In diesem Fall kann die Dateigröße mithilfe von Bildwiedergaben reduziert werden.
  
> [!NOTE]
> Formatvarianten sind nur für SharePoint verfügbar, wenn die Veröffentlichung aktiviert ist. Sie können die Veröffentlichung unter Einstellungen \> Websiteeinstellungen \> Verwalten von Websitefeatures \> SharePoint Server veröffentlichen aktivieren. Die Option wird andernfalls nicht angezeigt.
  
Die Größenänderung der Bildwiedergabe funktioniert, indem Sie die kleinste von Ihnen definierte Dimension, entweder Breite oder Höhe, und dann die Größe des Bilds so ändern, dass die andere Bemaßung automatisch basierend auf dem gesperrten Seitenverhältnis geändert wird. Standardmäßig wird das Bild von der Mitte durch die restlichen Dimensionen zuschneiden. Wenn Sie beispielsweise eine Formatvariante von 100px Wide und 50px High definieren und Ihr Originalbild 1000px breit und 800px hoch ist, wird die Größe so geändert, dass die 800px-Dimension jetzt 50px und die 1000px-Dimension (jetzt 62,5 px) von der Mitte des Bilds abgeschnitten wird.
  
Die Schritte sind relativ einfach, aber für Bilder, um die Darstellungen zu verwenden, müssen sich die Wiedergaben auf der SharePoint-Website befinden, bevor Sie die Bilder hinzufügen. Darüber hinaus müssen Sie auch die SharePoint Server Veröffentlichungs Infrastruktur (Websitesammlungsebene) und die Features für die SharePoint Server Veröffentlichung (Websiteebene) aktiviert haben.
  
### <a name="add-an-image-rendition-to-speed-up-page-loading"></a>Hinzufügen einer Bildwiedergabe zur Beschleunigung des Seitenladevorgangs
  
1. Stellen Sie sicher, dass das Benutzerkonto, unter dem dieses Verfahren ausgeführt wird, mindestens über Entwurfsberechtigungen für die Website auf oberster Ebene der Websitesammlung verfügt und dass die Website auf einer Webseite veröffentlicht wird.

2. Wechseln Sie in einem Webbrowser zur Website auf oberster Ebene der Veröffentlichungswebsite Sammlung.

3. Klicken Sie auf das Symbol **Einstellungen**.

4. Auf der Seite **Websiteeinstellungen** im Abschnitt **Aussehen und Verhalten** werden die integrierten Bildwiedergaben angezeigt.

    Sie können die Out-of-the-Box-Wiedergabe verwenden oder **Bildwiedergaben** auswählen, um eine neue zu erstellen.

    ![Screenshot der Bildwiedergabe](../media/eaae0d53-657d-47ef-b687-65c5167eae4d.PNG)
  
5. Wählen Sie auf der Seite **Bildwiedergaben** die Option **Neues Element hinzufügen**.

    ![Screenshot des neuen Elements hinzufügen](../media/8cede22e-52bf-4d9d-99cb-162f2f6ce92b.PNG)
  
6. Geben Sie auf der Seite **Neue Bildwiedergabe** in das Feld **Name** einen Namen für die Darstellung ein, z.

7. Geben Sie in die Textfelder **Breite** und **Höhe** die Breite und Höhe der Darstellung in Pixel ein, und klicken Sie dann auf **Speichern**.

    ![Screenshot des Bildwiedergabe namens](../media/5a6119ed-c163-40df-a4db-ec629d15607d.PNG)
  
## <a name="custom-cropping-with-image-renditions"></a>Benutzerdefiniertes Zuschneiden mit Bildwiedergaben

Standardmäßig wird eine Bilddarstellung aus der Mitte des Bilds generiert. Sie können die Bilddarstellung für einzelne Bilder anpassen, indem Sie den Teil des Bilds zuschneiden, den Sie verwenden möchten. Sie können die Bilder pro Wiedergabe auf individueller Basis zuschneiden. Durch das Zuschneiden der Bilder wird das Laden von Seiten beschleunigt, indem der BLOB-Cache von SharePoint verwendet wird, um eine Version des Bilds für jede Formatvariante zu erstellen. Auf diese Weise wird die Serverlast reduziert, da das Bild nur einmal geändert wird und dann für Endbenutzer mehrmals bereitgestellt werden kann. Weitere Informationen zum Zuschneiden einer Bilddarstellung finden Sie unter [Zuschneiden einer Bildwiedergabe](https://go.microsoft.com/fwlink/p/?LinkId=525626).
  

