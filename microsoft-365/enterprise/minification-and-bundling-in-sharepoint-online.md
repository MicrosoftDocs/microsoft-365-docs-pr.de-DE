---
title: Minimierung und Bündelung in SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 3/1/2017
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- SPO160
- MET150
ms.assetid: 87a52468-994e-43a2-b155-7229ed659291
description: In diesem Artikel erfahren Sie, wie Sie Minimierungs und Kopplungstechniken mit WebEssentials verwenden, um HTTP-Anforderungen zu reduzieren, und wie lange es dauert, Seiten in SharePoint Online zu laden.
ms.openlocfilehash: 2e2ff7b9d36a6c28ca3840304d896782e1096e85
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690323"
---
# <a name="minification-and-bundling-in-sharepoint-online"></a>Minimierung und Bündelung in SharePoint Online

In diesem Artikel wird beschrieben, wie Sie Minimierungs-und Kopplungstechniken mit WebEssentials verwenden, um die Anzahl der HTTP-Anforderungen zu reduzieren und die Zeit zu reduzieren, die zum Laden von Seiten in SharePoint Online benötigt wird.
  
Wenn Sie Ihre Website anpassen, können Sie am Ende eine große Anzahl zusätzlicher Dateien auf dem Server hinzufügen, um die Anpassung zu unterstützen. Durch Hinzufügen von zusätzlichen JavaScript-, CSS-und Bilddateien wird die Anzahl der HTTP-Anforderungen an den Server erhöht, was wiederum die Zeit für die Anzeige einer Webseite erhöht. Wenn Sie mehrere Dateien desselben Typs haben, können Sie diese Dateien bündeln, damit diese Dateien schneller heruntergeladen werden.
  
Bei JavaScript-und CSS-Dateien können Sie auch einen Ansatz namens "Minimierungs" verwenden, bei dem Sie die Gesamtgröße von Dateien verringern, indem Sie Leerzeichen und andere nicht benötigte Zeichen entfernen.
  
## <a name="minification-and-bundling-javascript-and-css-files-with-web-essentials"></a>Minimierungs und Bündelung von JavaScript-und CSS-Dateien mit WebEssentials

Sie können Drittanbietersoftware wie WebEssentials verwenden, um CSS-und JavaScript-Dateien zu bündeln.
  
> [!IMPORTANT]
> WebEssentials ist ein Open-Source-Projekt von Drittanbietern, das auf communitybasis basiert. Die Software ist eine Erweiterung für Visual Studio 2012 und Visual Studio 2013 und wird von Microsoft nicht unterstützt. Um Web Essentials herunterzuladen, besuchen Sie die Website unter [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629) . 
  
WebEssentials bietet zwei Formen der Bündelung:
  
- . Bundle: für CSS-und JavaScript-Dateien
    
- . Sprite: für Bilder (nur in Visual Studio 2013 verfügbar)
    
Sie können WebEssentials verwenden, wenn Sie ein vorhandenes Feature mit einigen Branding-Elementen haben, auf die in einer benutzerdefinierten Gestaltungsvorlage verwiesen wird, beispielsweise:
  
![Screenshot des Marken Elements in der benutzerdefinierten Gestaltungsvorlage](../media/3a6eba36-973d-482b-8556-a9394b8ba19f.png)
  
 **So erstellen Sie ein TE000127218-und CSS-Bundle in WebEssentials**
  
1. Wählen Sie in Visual Studio im Projektmappen-Explorer die Dateien aus, die Sie in das Bundle einschließen möchten.
    
2. Klicken Sie mit der rechten Maustaste auf die ausgewählten Dateien, und wählen Sie dann im Kontextmenü die Option **WebEssentials** \> **Create JavaScript Bundle File** aus. Beispiel: 
    
    ![Screenshot mit WebEssentials-Menü Optionen](../media/41aac84c-4538-4f78-b454-46e651f868a3.png)
  
## <a name="viewing-the-results-of-bundling-javascript-and-css-files"></a>Anzeigen der Ergebnisse der Bündelung von JavaScript-und CSS-Dateien

Wenn Sie ein JavaScript-und CSS-Bundle erstellen, erstellt WebEssentials eine XML-Datei namens "Rezept Datei", in der die JavaScript-und CSS-Dateien sowie einige andere Konfigurationsinformationen identifiziert werden: 
  
![Screenshot der JavaScript-und CSS-Rezept Datei](../media/7ba891f8-52d8-467b-a0f6-b062dd1137a4.png)
  
Wenn das minimieren-Flag in der Kopplungs Rezeptur auf true festgelegt ist, werden die Dateien zudem sowohl in der Größe als auch in der zusammengefassten Form reduziert. Dies bedeutet, dass neue, minimierte Versionen der JavaScript-Dateien erstellt wurden, auf die Sie in ihrer Gestaltungsvorlage verweisen können.
  
![Screenshot des minimieren-Flags auf true festgelegt](../media/50523af2-6412-4117-ac3d-5bd26f6d562e.png)
  
Wenn Sie eine Seite von Ihrer Website laden, können Sie die Entwicklertools aus Ihrem Webbrowser wie Internet Explorer 11 verwenden, um zu sehen, wie viele Anforderungen an den Server gesendet wurden und wie lange die einzelnen Dateien zum Laden benötigt wurden.
  
Die folgende Abbildung ist das Ergebnis des Ladens der JavaScript-und CSS-Dateien vor Minimierungs.
  
![Screenshot mit 80 Elementen, die heruntergeladen werden](../media/e2df3912-1923-46e6-8cf2-3015a31554e1.png)
  
Nachdem die CSS-und JavaScript-Dateien zusammen gebündelt wurden, wurde die Anzahl der Anforderungen auf 74 und jede Datei dauerte nur geringfügig länger als die ursprünglichen Dateien einzeln heruntergeladen werden:
  
![Screenshot mit 74 Elementen, die heruntergeladen werden](../media/686c4387-70e8-4a74-9d45-059f33a91184.png)
  
Nach dem bündeln wird die JavaScript-Bundle-Datei erheblich von 815KB auf 365KB reduziert:
  
![Screenshot mit reduzierter Downloadgröße](../media/5e7dbd98-faff-4f68-b320-108fb252e395.png)
  
## <a name="bundling-images-by-creating-an-image-sprite"></a>Bilder bündeln, indem Sie ein Bild Sprite erstellen

Ähnlich wie Sie JavaScript-und CSS-Dateien bündeln, können Sie viele kleine Symbole und andere allgemeine Bilder in ein größeres Sprite-Blatt kombinieren und dann mit CSS die einzelnen Bilder aufdecken. Anstatt jedes einzelne Bild herunterzuladen, downloadet der Webbrowser des Benutzers das Sprite-Blatt einmal und speichert es dann auf dem lokalen Computer zwischen. Dadurch wird die Seiten Ladeleistung verbessert, indem die Anzahl der Downloads und Roundtrips auf dem Webserver reduziert werden.
  
 **So erstellen Sie ein Image-Sprite in WebEssentials**
  
1. Wählen Sie in Visual Studio im Projektmappen-Explorer die Dateien aus, die Sie in das Bundle einschließen möchten.
    
2. Klicken Sie mit der rechten Maustaste auf die ausgewählten Dateien, und wählen Sie dann im Kontextmenü die Option **WebEssentials** \> **Create Image Sprite** aus. Beispiel: 
    
    ![Screenshot, der zeigt, wie ein Bild Sprite erstellt wird](../media/de0fe741-4ef7-4e3b-bafa-ef9f4822dac6.png)
  
3. Wählen Sie einen Speicherort aus, um die Sprite-Datei zu speichern. Die Sprite-Datei ist eine XML-Datei, in der die Einstellungen und Dateien im Sprite beschrieben werden. Die folgenden Abbildungen zeigen ein Beispiel für eine Sprite-PNG-Datei und die zugehörige Sprite-XML-Datei.
    
    ![Screenshot einer Sprite-Datei](../media/0876bb2a-d1b9-4169-8e95-9c290d628d90.png)
  
    ![Screenshot der Sprite-XML-Datei](../media/d1f94776-280d-4d56-abb5-384f145d9989.png)
  

