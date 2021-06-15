---
title: Bildoptimierung für SharePoint klassische Online-Veröffentlichungswebsites
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
description: Erfahren Sie, wie Sie Darstellungen und Sprites verwenden, um die Imageleistung auf Ihren klassischen SharePoint Online-Veröffentlichungswebsites zu verbessern.
ms.openlocfilehash: 15885f1d8803332e24e2656a48b796dab28c665f
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924575"
---
# <a name="image-optimization-for-sharepoint-online-classic-publishing-sites"></a>Bildoptimierung für SharePoint klassische Online-Veröffentlichungswebsites

Die Ladegeschwindigkeit einer Webseite hängt von der kombinierten Größe aller Komponenten ab, die zum Rendern der Seite erforderlich sind, einschließlich Bilder, HTML, JavaScript und CSS. Bilder sind eine hervorragende Möglichkeit, Ihre Website ansprechender zu gestalten, aber ihre Größe kann sich auf die Leistung auswirken. Indem Sie Ihre Bilder mit Komprimierung und Größenänderung optimieren und Sprites verwenden, können Sie die Effekte sehr großer Bilder verdrücken. Mit SharePoint Bilddarstellungen können Sie ein einzelnes großes Bild hochladen und Abschnitte des Bilds anzeigen, sodass es wiederverwendet und nicht neu geladen werden kann.

>[!NOTE]
>Dieses Thema bezieht sich auf SharePoint klassische Online-Veröffentlichungswebsites, nicht auf moderne Portalwebsites. Informationen zur Bildoptimierung in SharePoint Modern Portal Online-Websites finden Sie unter [Optimieren von Bildern auf SharePoint modernen Onlineportalseiten.](modern-image-optimization.md)
  
## <a name="using-sprites-to-speed-up-image-loading"></a>Verwenden von Sprites zum Beschleunigen des Ladens von Bildern

![Screenshot von spcommon](../media/cc5cdee1-8e54-4537-9a8a-8854f4ee849f.png)

Ein Bild-Sprite enthält viele kleinere Bilder. MitHILFE von CSS wählen Sie einen Teil des zusammengesetzten Bilds aus, der auf einem bestimmten Teil der Seite mit absoluter Positionierung angezeigt werden soll. Im Wesentlichen verschieben Sie ein einzelnes Bild um die Seite, anstatt mehrere Bilder zu laden, und machen einen kleinen Teil dieses Bilds durch ein kleines Fenster sichtbar, in dem dem Endbenutzer der erforderliche Teil des Sprite-Bilds angezeigt wird. SharePoint Online verwendet Sprites, um die verschiedenen Symbole in der Sprite-spcommon.png-Datei anzuzeigen.

Hier wird Folgendes behandelt:
- Bildkomprimierung
- Bildoptimierung
- SharePoint Bilddarstellungen
   
Dies kann die Leistung erhöhen, da Sie nur ein Bild anstelle mehrerer herunterladen und dieses Dann zwischenspeichern und wiederverwenden. Selbst wenn das Image nicht zwischengespeichert bleibt, reduziert diese Methode durch die Verwendung eines einzelnen Bilds anstelle mehrerer Bilder die Gesamtzahl der HTTP-Anforderungen an den Server, wodurch die Seitenladezeiten reduziert werden. Dies ist wirklich eine Form der Bildbündelung. Dies ist eine sehr nützliche Technik, wenn die Bilder nicht sehr oft geändert werden, z. B. Symbole, wie im oben gezeigten SharePoint Beispiel gezeigt. Sie können [Web Essentials](https://vswebessentials.com/)verwenden, ein Open-Source-Community-basiertes Drittanbieterprojekt, um dies in Microsoft Visual Studio zu erreichen. Weitere Informationen finden Sie unter [Minification und Bündelung in SharePoint Online](./minification-and-bundling-in-sharepoint-online.md).
  
## <a name="using-image-compression-and-optimization-to-speed-up-page-loading"></a>Verwenden der Bildkomprimierung und -optimierung zum beschleunigen des Ladens von Seiten

Bei der Bildkomprimierung und -optimierung geht es um die Reduzierung der Dateigröße der Bilder, die Sie auf Ihrer Website verwenden. Häufig besteht die beste Technik zum Reduzieren der Größe eines Bilds darin, die Größe des Bilds auf die maximalen Abmessungen zu ändern, die auf der Website angezeigt werden. Es hat keinen Sinn, ein Bild zu haben, das größer ist, als es jemals angezeigt wird. Stellen Sie sicher, dass Bilder die richtigen Abmessungen aufweisen, indem Sie einen Bild-Editor verwenden, um die Größe Ihrer Seite schnell und einfach zu reduzieren.
  
Sobald Bilder die richtige Größe haben, besteht der nächste Schritt darin, die Komprimierung dieser Bilder zu optimieren. Für die Komprimierung und Optimierung stehen verschiedene Tools zur Verfügung, einschließlich Fotogalerie- und Drittanbietertools. Der Schlüssel für die Komprimierung besteht darin, die Dateigröße so weit wie möglich zu reduzieren, ohne die Qualität für Endbenutzer zu verlieren. Stellen Sie sicher, dass Sie Ihre komprimierten Dateien auf einer Hd-Anzeige testen, um sicherzustellen, dass sie weiterhin gut aussehen.
  
## <a name="speed-up-page-downloads-by-using-sharepoint-image-renditions"></a>Beschleunigen von Seitendownloads mithilfe SharePoint Bilddarstellungen

Bilddarstellungen sind ein Feature in SharePoint Online, mit dem Sie verschiedene Versionen von Bildern basierend auf vordefinierten Bildabmessungen bereitstellen können. Dies ist besonders wichtig, wenn vom Benutzer generierte Bildinhalte vorhanden sind oder die Bildabmessungen wie Breite und Höhe vom CSS auf der Website festgelegt werden. Selbst wenn ein Bild durch CSS behoben wird, wird das Bild mit voller Auflösung immer noch geladen. In diesem Fall kann die Dateigröße mithilfe von Bilddarstellungen reduziert werden.
  
> [!NOTE]
> Formatvarianten sind nur für SharePoint verfügbar, wenn die Veröffentlichung aktiviert ist. Sie können die Veröffentlichung unter Einstellungen \> Website Einstellungen \> Websitefeatures SharePoint Serververöffentlichung verwalten \> aktivieren. Andernfalls wird die Option nicht angezeigt.
  
Die Größenänderung der Bilddarstellung funktioniert, indem sie die kleinste Dimension verwendet, die Sie definieren, entweder Breite oder Höhe, und dann die Größe des Bilds ändern, sodass die Größe der anderen Dimension basierend auf dem gesperrten Seitenverhältnis automatisch geändert wird. Standardmäßig wird das Bild von der Mitte um die verbleibenden Dimensionen zugeschnitten. Wenn Sie z. B. eine Formatvariante mit einer Breite von 100 px und einer Höhe von 50 Pixeln definieren und das Originalbild 1000 Pixel breit und 800 Pixel hoch ist, wird die Größe geändert, sodass die 800px-Dimension jetzt 50px und die 1000px-Dimension (jetzt 62,5px) von der Mitte des Bilds zugeschnitten wird.
  
Die Schritte sind relativ einfach, aber damit Bilder die Formatvarianten verwenden können, müssen sich die Formatvarianten auf der SharePoint Website befinden, bevor Sie die Bilder hinzufügen. Darüber hinaus müssen Sie die Features SharePoint Server Publishing Infrastructure (Site Collection Level) und SharePoint Server Publishing (Site Level) aktiviert haben.
  
### <a name="add-an-image-rendition-to-speed-up-page-loading"></a>Hinzufügen einer Bilddarstellung, um das Laden der Seite zu beschleunigen
  
1. Stellen Sie sicher, dass das Benutzerkonto, das dieses Verfahren ausführt, mindestens über Entwurfsberechtigungen für die Website auf oberster Ebene der Websitesammlung verfügt und dass die Website auf einer Webseite veröffentlicht wird.

2. Wechseln Sie in einem Webbrowser zur Website auf oberster Ebene der Veröffentlichungswebsitesammlung.

3. Klicken Sie auf das Symbol **Einstellungen**.

4. Auf der Seite **"Website Einstellungen"** im Abschnitt **"Aussehen und Verhalten"** werden die integrierten Bilddarstellungen angezeigt.

    Sie können die vordefinierten Formatvarianten verwenden oder **Bilddarstellungen** auswählen, um eine neue zu erstellen.

    ![Screenshot der Bilddarstellung](../media/eaae0d53-657d-47ef-b687-65c5167eae4d.PNG)
  
5. Wählen Sie auf der Seite **Bildwiedergaben** die Option **Neues Element hinzufügen**.

    ![Screenshot von "Neues Element hinzufügen"](../media/8cede22e-52bf-4d9d-99cb-162f2f6ce92b.PNG)
  
6. Geben Sie auf der Seite **Neue Bildwiedergabe** in das Feld **Name** einen Namen für die Darstellung ein, z.

7. Geben Sie in die Textfelder **Breite** und **Höhe** die Breite und Höhe der Darstellung in Pixel ein, und klicken Sie dann auf **Speichern**.

    ![Screenshot des Bilddarstellungsnamens](../media/5a6119ed-c163-40df-a4db-ec629d15607d.PNG)
  
## <a name="custom-cropping-with-image-renditions"></a>Benutzerdefiniertes Zuschneiden mit Bilddarstellungen

Standardmäßig wird eine Bilddarstellung aus der Mitte des Bilds generiert. Sie können die Bilddarstellung für einzelne Bilder anpassen, indem Sie den Teil des Bilds zuschneiden, den Sie verwenden möchten. Sie können die Bilder pro Formatition einzeln zuschneiden. Das Zuschneiden der Bilder beschleunigt das Laden der Seite, indem der Blobcache SharePoint verwendet wird, um eine Version des Bilds für jede Darstellung zu erstellen. Auf diese Weise wird die Serverlast reduziert, da die Größe des Images nur einmal geändert wird und dann mehrere Male für Endbenutzer bereitgestellt werden kann. Weitere Informationen zum Zuschneiden einer Bilddarstellung finden Sie unter [Zuschneiden einer Bilddarstellung.](/sharepoint/dev/general-development/sharepoint-design-manager-device-channels)
