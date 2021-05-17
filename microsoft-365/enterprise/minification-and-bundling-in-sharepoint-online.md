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
description: Erfahren Sie, wie Sie Verminungs- und Bündelungstechniken mit Web Essentials verwenden, um HTTP-Anforderungen und den Zeitaufwand für das Laden von Seiten in SharePoint Online zu reduzieren.
ms.openlocfilehash: 2e2ff7b9d36a6c28ca3840304d896782e1096e85
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690323"
---
# <a name="minification-and-bundling-in-sharepoint-online"></a>Minimierung und Bündelung in SharePoint Online

In diesem Artikel wird beschrieben, wie Sie Verminungs- und Bündelungstechniken mit Web Essentials verwenden, um die Anzahl der HTTP-Anforderungen zu reduzieren und den Zeitaufwand für das Laden von Seiten in SharePoint Online zu reduzieren.
  
Wenn Sie Ihre Website anpassen, können Sie dem Server eine große Anzahl zusätzlicher Dateien hinzufügen, um die Anpassung zu unterstützen. Durch hinzufügen zusätzlicher JavaScript-, CSS- und Bilder wird die Anzahl der HTTP-Anforderungen an den Server erhöht, was wiederum die Zeit erhöht, die zum Anzeigen einer Webseite benötigt wird. Wenn Sie über mehrere Dateien desselben Typs verfügen, können Sie diese Dateien bündeln, um das Herunterladen dieser Dateien zu beschleunigen.
  
Für JavaScript- und CSS-Dateien können Sie auch einen Ansatz namens Minification verwenden, bei dem Sie die Gesamtgröße von Dateien reduzieren, indem Sie Leerzeichen und andere Zeichen entfernen, die nicht erforderlich sind.
  
## <a name="minification-and-bundling-javascript-and-css-files-with-web-essentials"></a>Verminen und Bündeln von JavaScript- und CSS-Dateien mit Web Essentials

Sie können Software von Drittanbietern wie Web Essentials verwenden, um CSS- und JavaScript-Dateien zu bündeln.
  
> [!IMPORTANT]
> Web Essentials ist ein Open-Source-Projekt auf Communitybasis von Drittanbietern. Die Software ist eine Erweiterung von Visual Studio 2012 und Visual Studio 2013 und wird von Microsoft nicht unterstützt. Um Web Essentials herunterzuladen, besuchen Sie die Website unter [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629) . 
  
Web Essentials bietet zwei Arten von Bündelung:
  
- .bundle: für CSS- und JavaScript-Dateien
    
- .sprite: für Bilder (nur in Visual Studio 2013)
    
Sie können Web Essentials verwenden, wenn Sie über ein vorhandenes Feature mit einigen Brandingelementen verfügen, auf die in einer benutzerdefinierten Masterseite verwiesen wird, z. B.:
  
![Screenshot des Markenelements auf der benutzerdefinierten Masterseite](../media/3a6eba36-973d-482b-8556-a9394b8ba19f.png)
  
 **So erstellen Sie ein TE000127218- und CSS-Bundle in Web Essentials**
  
1. Wählen Visual Studio im Projektmappen-Explorer die Dateien aus, die Sie in das Bundle hinzufügen möchten.
    
2. Klicken Sie mit der rechten Maustaste auf die ausgewählten Dateien, und wählen Sie dann im Kontextmenü **Web Essentials** \> **Create JavaScript bundle file** aus. Beispiel: 
    
    ![Screenshot mit Web Essentials-Menüoptionen](../media/41aac84c-4538-4f78-b454-46e651f868a3.png)
  
## <a name="viewing-the-results-of-bundling-javascript-and-css-files"></a>Anzeigen der Ergebnisse der Bündelung von JavaScript- und CSS-Dateien

Wenn Sie ein JavaScript- und CSS-Bündel erstellen, erstellt Web Essentials eine XML-Datei namens Rezeptdatei, die die JavaScript- und CSS-Dateien sowie einige andere Konfigurationsinformationen identifiziert: 
  
![Screenshot der JavaScript- und CSS-Rezeptdatei](../media/7ba891f8-52d8-467b-a0f6-b062dd1137a4.png)
  
Wenn das Minify-Flag im Bündelungsrezept auf true festgelegt ist, werden die Dateien außerdem in der Größe reduziert und zusammengebündelt. Dies bedeutet, dass neue, verminte Versionen der JavaScript-Dateien erstellt wurden, auf die Sie in Ihrer Masterseite verweisen können.
  
![Screenshot des auf true festgelegten Minify-Flags](../media/50523af2-6412-4117-ac3d-5bd26f6d562e.png)
  
Wenn Sie eine Seite von Ihrer Website laden, können Sie die Entwicklertools aus Ihrem Webbrowser verwenden, z. B. Internet Explorer 11, um die Anzahl der anforderungen anzuzeigen, die an den Server gesendet wurden und wie lange die Einzelnen Dateien geladen wurden.
  
Die folgende Abbildung ist das Ergebnis des Ladens der JavaScript- und CSS-Dateien vor der Minifizierung.
  
![Screenshot mit 80 heruntergeladenen Elementen](../media/e2df3912-1923-46e6-8cf2-3015a31554e1.png)
  
Nach dem Bündeln der CSS- und JavaScript-Dateien ist die Anzahl der Anforderungen auf 74 gesunken, und jede Datei hat nur geringfügig länger ge dauert als die ursprünglichen Dateien, um sie einzeln herunterzuladen:
  
![Screenshot mit 74 heruntergeladenen Elementen](../media/686c4387-70e8-4a74-9d45-059f33a91184.png)
  
Nach der Bündelung wird die JavaScript-Bundledatei erheblich von 815 KB auf 365 KB reduziert:
  
![Screenshot mit reduzierter Downloadgröße](../media/5e7dbd98-faff-4f68-b320-108fb252e395.png)
  
## <a name="bundling-images-by-creating-an-image-sprite"></a>Bündeln von Bildern durch Erstellen eines Bildsprites

Ähnlich wie Sie JavaScript- und CSS-Dateien bündeln, können Sie viele kleine Symbole und andere allgemeine Bilder in einem größeren Spritesheet kombinieren und dann CSS verwenden, um die einzelnen Bilder zu zeigen. Anstatt jedes einzelne Bild herunterzuladen, lädt der Webbrowser des Benutzers das Spritesheet einmal herunter und speichert es dann auf dem lokalen Computer zwischen. Dadurch wird die Seitenlastleistung verbessert, indem die Anzahl der Downloads und Roundtrips zum Webserver herabgefahren wird.
  
 **So erstellen Sie ein Bild-Sprite in Web Essentials**
  
1. Wählen Visual Studio im Projektmappen-Explorer die Dateien aus, die Sie in das Bundle hinzufügen möchten.
    
2. Klicken Sie mit der rechten Maustaste auf die ausgewählten Dateien, und wählen Sie dann im Kontextmenü **Web Essentials** \> **Image sprite** erstellen aus. Beispiel: 
    
    ![Screenshot, der zeigt, wie Sie ein Bild-Sprite erstellen](../media/de0fe741-4ef7-4e3b-bafa-ef9f4822dac6.png)
  
3. Wählen Sie einen Speicherort aus, um die sprite-Datei zu speichern. Die SPRITE-Datei ist eine XML-Datei, die die Einstellungen und Dateien im sprite beschreibt. Die folgenden Abbildungen zeigen ein Beispiel für eine sprite-PNG-Datei und die entsprechende SPRITE-XML-Datei.
    
    ![Screenshot einer sprite-Datei](../media/0876bb2a-d1b9-4169-8e95-9c290d628d90.png)
  
    ![Screenshot der sprite-XML-Datei](../media/d1f94776-280d-4d56-abb5-384f145d9989.png)
  

