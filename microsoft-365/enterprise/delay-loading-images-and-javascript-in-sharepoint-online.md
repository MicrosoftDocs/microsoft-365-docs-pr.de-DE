---
title: Verzögerung beim Laden von Bildern und JavaScript in SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
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
ms.assetid: 74d327e5-755f-4135-b9a5-7b79578c1bf9
description: In diesem Artikel erfahren Sie, wie Sie die Ladezeit für SharePoint Online Seiten reduzieren können, indem Sie JavaScript zum verzögern des Ladens von Bildern und nicht-essentiellen JavaScript verwenden.
ms.openlocfilehash: ee86ae0813c11fbfd836d7d38ea124c1e3f277d0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690655"
---
# <a name="delay-loading-images-and-javascript-in-sharepoint-online"></a>Verzögerung beim Laden von Bildern und JavaScript in SharePoint Online

In diesem Artikel wird beschrieben, wie Sie die Ladezeit für SharePoint Online Seiten reduzieren können, indem Sie JavaScript verwenden, um das Laden von Bildern zu verzögern und außerdem darauf zu warten, dass unwesentliches JavaScript geladen wird, bevor die Seite geladen wird.
  
Bilder können sich negativ auf die Seitenlast Geschwindigkeiten auf SharePoint Online auswirken. Standardmäßig werden von den meisten modernen Internet Browsern vor dem Laden einer HTML-Seite Bilder abgerufen. Dies kann dazu führen, dass die Seite unnötig langsam belastet wird, wenn die Bilder auf dem Bildschirm nicht sichtbar sind, bis der Benutzer einen Bildlauf nach unten durchführt. Die Bilder können verhindern, dass der Browser den sichtbaren Teil der Seite lädt. Um dieses Problem zu umgehen, können Sie JavaScript verwenden, um das Laden der Bilder zuerst zu überspringen. Außerdem kann das Laden nicht wesentlicher JavaScript-Downloadzeiten auch auf Ihren SharePoint-Seiten verlangsamen. In diesem Thema werden einige Methoden beschrieben, die Sie zum Verbessern der Seitenladezeiten mit JavaScript in SharePoint Online verwenden können.
  
## <a name="improve-page-load-times-by-delaying-image-loading-in-sharepoint-online-pages-by-using-javascript"></a>Verbessern der Seitenladezeiten durch verzögertes Laden von Bildern in SharePoint Online Seiten mithilfe von JavaScript

Sie können JavaScript verwenden, um zu verhindern, dass ein Webbrowser Vorabbilder abruft. Dadurch wird das gesamte Dokument Rendering beschleunigt. Dazu entfernen Sie den Wert des src-Attributs aus dem \<img\> -Tag und ersetzen ihn durch den Pfad zu einer Datei in einem Data-Attribut wie: Data-src. Beispiel:
  
```html
<img src="" data-src="/sites/NavigationBySearch/_catalogs/masterpage/media/microsoft-white-8.jpg" />
```

Mithilfe dieser Methode lädt der Browser die Bilder nicht sofort herunter. Wenn sich das Bild bereits im Viewport befindet, teilt JavaScript dem Browser mit, dass die URL aus dem Data-Attribut abgerufen und als Wert für das src-Attribut eingefügt wird. Das Bild wird nur geladen, wenn der Benutzer einen Bildlauf durchführt und in der Ansicht angezeigt wird.
  
Damit dies geschieht, müssen Sie JavaScript verwenden.
  
Definieren Sie in einer Textdatei die **isElementInViewport ()** -Funktion, um zu überprüfen, ob sich ein Element in dem Teil des Browsers befindet, der für den Benutzer sichtbar ist.
  
```javascript
function isElementInViewport(el) {
  if (!el)
    return false;
  var rect = el.getBoundingClientRect();
  return (
    rect.top >= 0 &amp;&amp;
    rect.left >= 0 &amp;&amp;
    rect.bottom <= (window.innerHeight || document.documentElement.clientHeight) &amp;&amp;
    rect.right <= (window.innerWidth || document.documentElement.clientWidth)
  );
}
```

Verwenden Sie als nächstes **isElementInViewport ()** in der **loadItemsInView ()** -Funktion. Die **loadItemsInView ()-** Funktion lädt alle Bilder mit einem Wert für das Data-src-Attribut, wenn Sie sich in dem Teil des Browsers befinden, der für den Benutzer sichtbar ist. Fügen Sie die folgende Funktion zur Textdatei hinzu:
  
```javascript
function loadItemsInView() {
  //Select elements by the row id.
  $("#row [data-src]").each(function () {
      var isVisible = isElementInViewport(this);
      if (isVisible) {
          if ($(this).attr("src") == undefined) {
              $(this).attr("src", $(this).data("src"));
          }
      }
  });
}
```

Schließlich rufen Sie **loadItemsInView ()** in **Window. OnScroll ()** auf, wie im folgenden Beispiel gezeigt. Dadurch wird sichergestellt, dass alle im Viewport enthaltenen Bilder geladen werden, wenn der Benutzer Sie benötigt, jedoch nicht zuvor. Fügen Sie Folgendes zur Textdatei hinzu:
  
```javascript
//Example of calling loadItemsInView() from within window.onscroll()
$(window).on("scroll", function () {
    loadItemsInView();
});

```

Für SharePoint Online müssen Sie die folgende Funktion an das Scroll-Ereignis im #S4-Workspace-Tag anfügen \<div\> . Dies liegt daran, dass die Fenster Ereignisse außer Kraft gesetzt werden, um sicherzustellen, dass das Menüband am oberen Rand der Seite angefügt bleibt.
  
```javascript
//Keep the ribbon at the top of the page
$('#s4-workspace').on("scroll", function () {
    loadItemsInView();
});
```

Speichern Sie die Textdatei als JavaScript-Datei mit der Erweiterung. js, beispielsweise delayLoadImages.js.
  
Nachdem Sie das Schreiben von delayLoadImages.js abgeschlossen haben, können Sie den Inhalt der Datei einer Gestaltungsvorlage in SharePoint Online hinzufügen. Hierzu fügen Sie der Kopfzeile auf der Gestaltungsvorlage einen Skript Link hinzu. Sobald er auf einer Gestaltungsvorlage liegt, wird das JavaScript auf alle Seiten auf der SharePoint Online Website angewendet, die dieses Gestaltungsvorlagen Layout verwenden. Wenn Sie diese nur auf einer Seite Ihrer Website verwenden möchten, verwenden Sie alternativ das Skript-Editor-Webpart, um das JavaScript in die Seite einzubetten. Weitere Informationen finden Sie in den folgenden Themen:
  
- [Vorgehensweise: Anwenden einer Gestaltungsvorlage auf eine Website in SharePoint 2013](https://go.microsoft.com/fwlink/p/?LinkId=525627)

- [Vorgehensweise: Erstellen eines Seitenlayouts in SharePoint 2013](https://go.microsoft.com/fwlink/p/?LinkId=525628)

### <a name="example-referencing-the-javascript-delayloadimagesjs-file-from-a-master-page-in-sharepoint-online"></a>Beispiel: verweisen auf die JavaScript-delayLoadImages.js Datei von einer Gestaltungsvorlage in SharePoint Online
  
Damit dies funktioniert, müssen Sie auch auf der Gestaltungsvorlage auf jQuery verweisen. Im folgenden Beispiel sehen Sie auf der anfänglichen Seite laden, dass nur ein Bild geladen ist, aber es gibt mehrere weitere auf der Seite.
  
![Screenshot mit einem auf der Seite geladenen Bild](../media/3d177ddb-67e5-43a7-b327-c9f9566ca937.png)
  
Der folgende Screenshot zeigt die restlichen Bilder, die heruntergeladen werden, nachdem Sie in die Ansicht verschoben wurden.
  
![Screenshot mit mehreren auf der Seite geladenen Bildern](../media/95eb2b14-f6a1-4eac-a5cb-96097e49514c.png)
  
Das verzögerte Laden von Bildern mithilfe von JavaScript kann ein effektives Verfahren zur Leistungssteigerung sein; Wenn die Technik jedoch auf einer öffentlichen Website angewendet wird, können Suchmodule die Bilder nicht auf die gleiche Weise durchforsten wie ein regelmäßig geformtes Bild. Dies kann sich auf Rankings in Suchmodulen auswirken, da Metadaten auf dem Bild selbst nicht wirklich vorhanden sind, bis die Seite geladen wird. Suchmaschinen-Crawler lesen nur den HTML-Code und sehen daher die Bilder nicht als Inhalt auf der Seite. Bilder sind einer der Faktoren, die für die Rangfolge von Seiten in Suchergebnissen verwendet werden. Eine Möglichkeit, dies zu umgehen, ist die Verwendung von Einführungstext für Ihre Bilder.
  
## <a name="github-code-sample-injecting-javascript-to-improve-performance"></a>GitHub-Codebeispiel: Einfügen von JavaScript zur Verbesserung der Leistung

Verpassen Sie nicht den Artikel und das Codebeispiel auf der auf GitHub bereitgestellten [JavaScript-Injektion](https://go.microsoft.com/fwlink/p/?LinkId=524759) .
  
## <a name="see-also"></a>Siehe auch

[Unterstützte Browser in Office 2013 und Microsoft 365-Apps für Unternehmen](https://support.office.com/article/57342811-0dc4-4316-b773-20082ced8a82)
  
[Vorgehensweise: Anwenden einer Gestaltungsvorlage auf eine Website in SharePoint 2013](https://go.microsoft.com/fwlink/p/?LinkId=525627)
  
[Vorgehensweise: Erstellen eines Seitenlayouts in SharePoint 2013](https://go.microsoft.com/fwlink/p/?LinkId=525628)
