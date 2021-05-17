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
description: Erfahren Sie, wie Sie die Ladezeit für SharePoint Onlineseiten verringern, indem Sie JavaScript verwenden, um das Laden von Bildern und nicht unbedingtes JavaScript zu verzögern.
ms.openlocfilehash: 86b93c4e1e102132bb0c1bfb9a413233529adecb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919164"
---
# <a name="delay-loading-images-and-javascript-in-sharepoint-online"></a><span data-ttu-id="9325b-103">Verzögerung beim Laden von Bildern und JavaScript in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9325b-103">Delay loading images and JavaScript in SharePoint Online</span></span>

<span data-ttu-id="9325b-104">In diesem Artikel wird beschrieben, wie Sie die Ladezeit für SharePoint Onlineseiten verringern können, indem Sie JavaScript verwenden, um das Laden von Bildern zu verzögern und auch darauf zu warten, dass nicht essentielles JavaScript bis nach dem Laden der Seite geladen wird.</span><span class="sxs-lookup"><span data-stu-id="9325b-104">This article describes how you can decrease the load time for SharePoint Online pages by using JavaScript to delay loading images and also by waiting to load non-essential JavaScript until after the page loads.</span></span>
  
<span data-ttu-id="9325b-105">Bilder können sich negativ auf die Seitenladegeschwindigkeit in SharePoint Online auswirken.</span><span class="sxs-lookup"><span data-stu-id="9325b-105">Images can negatively affect page load speeds on SharePoint Online.</span></span> <span data-ttu-id="9325b-106">Standardmäßig rufen die meisten modernen Internetbrowser Bilder beim Laden einer HTML-Seite vorab ab.</span><span class="sxs-lookup"><span data-stu-id="9325b-106">By default, most modern Internet browsers pre-fetch images when loading an HTML page.</span></span> <span data-ttu-id="9325b-107">Dies kann dazu führen, dass die Seite unnötig langsam geladen wird, wenn die Bilder nicht auf dem Bildschirm angezeigt werden, bis der Benutzer einen Bildlauf nach unten durchführen kann.</span><span class="sxs-lookup"><span data-stu-id="9325b-107">This can cause the page to be unnecessarily slow to load if the images are not visible on the screen until the user scrolls down.</span></span> <span data-ttu-id="9325b-108">Die Bilder können verhindern, dass der Browser den sichtbaren Teil der Seite lädt.</span><span class="sxs-lookup"><span data-stu-id="9325b-108">The images can block the browser from loading the visible part of the page.</span></span> <span data-ttu-id="9325b-109">Um dieses Problem zu beheben, können Sie javaScript verwenden, um das Laden der Bilder zuerst zu überspringen.</span><span class="sxs-lookup"><span data-stu-id="9325b-109">To work around this problem, you can use JavaScript to skip loading the images first.</span></span> <span data-ttu-id="9325b-110">Darüber hinaus kann das Laden nicht wesentlicher JavaScript-Dateien die Downloadzeiten auf Ihren SharePoint verlangsamen.</span><span class="sxs-lookup"><span data-stu-id="9325b-110">Also, loading non-essential JavaScript can slow download times on your SharePoint pages too.</span></span> <span data-ttu-id="9325b-111">In diesem Thema werden einige Methoden beschrieben, mit deren Hilfe Sie die Ladezeiten von Seiten mit JavaScript in SharePoint Online verbessern können.</span><span class="sxs-lookup"><span data-stu-id="9325b-111">This topic describes some methods you can use to improve page load times with JavaScript in SharePoint Online.</span></span>
  
## <a name="improve-page-load-times-by-delaying-image-loading-in-sharepoint-online-pages-by-using-javascript"></a><span data-ttu-id="9325b-112">Verbessern sie die Ladezeiten von Seiten, indem Sie das Laden von Bildern in SharePoint Onlineseiten mithilfe von JavaScript verzögern</span><span class="sxs-lookup"><span data-stu-id="9325b-112">Improve page load times by delaying image loading in SharePoint Online pages by using JavaScript</span></span>

<span data-ttu-id="9325b-113">Sie können JavaScript verwenden, um zu verhindern, dass ein Webbrowser Bilder vorab abruft.</span><span class="sxs-lookup"><span data-stu-id="9325b-113">You can use JavaScript to prevent a web browser from pre-fetching images.</span></span> <span data-ttu-id="9325b-114">Dadurch wird das gesamte Dokumentrendering beschleunigt.</span><span class="sxs-lookup"><span data-stu-id="9325b-114">This speeds up overall document rendering.</span></span> <span data-ttu-id="9325b-115">Dazu entfernen Sie den Wert des src-Attributs aus dem Tag und ersetzen ihn durch den Pfad zu einer Datei in einem \<img\> Datenattribut wie: data-src.</span><span class="sxs-lookup"><span data-stu-id="9325b-115">To do this you remove the value of the src attribute from the \<img\> tag and replace it with the path to a file in a data attribute such as: data-src.</span></span> <span data-ttu-id="9325b-116">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9325b-116">For example:</span></span>
  
```html
<img src="" data-src="/sites/NavigationBySearch/_catalogs/masterpage/media/microsoft-white-8.jpg" />
```

<span data-ttu-id="9325b-117">Mithilfe dieser Methode wird der Browser die Bilder nicht sofort herunterladen.</span><span class="sxs-lookup"><span data-stu-id="9325b-117">By using this method, the browser doesn't download the images immediately.</span></span> <span data-ttu-id="9325b-118">Wenn sich das Bild bereits im Viewport befindet, weist JavaScript den Browser an, die URL aus dem Data-Attribut abzurufen und als Wert für das src-Attribut einfüge.</span><span class="sxs-lookup"><span data-stu-id="9325b-118">If the image is already in the viewport, JavaScript tells the browser to retrieve the URL from the data attribute and insert it as the value for the src attribute.</span></span> <span data-ttu-id="9325b-119">Das Bild wird nur geladen, wenn der Benutzer einen Bildlauf durchblättert, und es wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9325b-119">The image only loads as the user scrolls and it comes into view.</span></span>
  
<span data-ttu-id="9325b-120">Um all dies zu geschehen, müssen Sie JavaScript verwenden.</span><span class="sxs-lookup"><span data-stu-id="9325b-120">To make all of this happen, you'll need to use JavaScript.</span></span>
  
<span data-ttu-id="9325b-121">Definieren Sie in einer Textdatei die **isElementInViewport()-Funktion,** um zu überprüfen, ob sich ein Element im Browserteil befindet, der für den Benutzer sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="9325b-121">In a text file, define the **isElementInViewport()** function to check whether or not an element is in the part of the browser that is visible to the user.</span></span>
  
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

<span data-ttu-id="9325b-122">Verwenden Sie als Nächstes **isElementInViewport()** in der **loadItemsInView()-Funktion.**</span><span class="sxs-lookup"><span data-stu-id="9325b-122">Next, use **isElementInViewport()** in the **loadItemsInView()** function.</span></span> <span data-ttu-id="9325b-123">Die **loadItemsInView()-Funktion** laden alle Bilder, die einen Wert für das data-src-Attribut haben, wenn sie sich im Für den Benutzer sichtbaren Teil des Browsers befinden.</span><span class="sxs-lookup"><span data-stu-id="9325b-123">The **loadItemsInView()** function will load all images that have a value for the data-src attribute if they are in the part of the browser that is visible to the user.</span></span> <span data-ttu-id="9325b-124">Fügen Sie der Textdatei die folgende Funktion hinzu:</span><span class="sxs-lookup"><span data-stu-id="9325b-124">Add the following function to the text file:</span></span>
  
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

<span data-ttu-id="9325b-125">Rufen Sie **schließlich loadItemsInView()** aus **dem Fenster window.onscroll()** auf, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="9325b-125">Finally, call **loadItemsInView()** from within **window.onscroll()** as shown in the following example.</span></span> <span data-ttu-id="9325b-126">Dadurch wird sichergestellt, dass alle Bilder, die sich im Viewport befinden, nach Bedarf des Benutzers geladen werden, aber nicht zuvor.</span><span class="sxs-lookup"><span data-stu-id="9325b-126">This ensures that any images that are in the viewport are loaded as the user needs them, but not before.</span></span> <span data-ttu-id="9325b-127">Fügen Sie der Textdatei Folgendes hinzu:</span><span class="sxs-lookup"><span data-stu-id="9325b-127">Add the following to the text file:</span></span>
  
```javascript
//Example of calling loadItemsInView() from within window.onscroll()
$(window).on("scroll", function () {
    loadItemsInView();
});

```

<span data-ttu-id="9325b-128">For SharePoint Online, you need to attach the following function to the scroll event on the #s4-workspace \<div\> tag.</span><span class="sxs-lookup"><span data-stu-id="9325b-128">For SharePoint Online, you need to attach the following function to the scroll event on the #s4-workspace \<div\> tag.</span></span> <span data-ttu-id="9325b-129">Dies liegt daran, dass die Fensterereignisse überschrieben werden, um sicherzustellen, dass das Menüband am oberen Rand der Seite angefügt bleibt.</span><span class="sxs-lookup"><span data-stu-id="9325b-129">This is because the window events are overridden in order to ensure the ribbon remains attached to the top of the page.</span></span>
  
```javascript
//Keep the ribbon at the top of the page
$('#s4-workspace').on("scroll", function () {
    loadItemsInView();
});
```

<span data-ttu-id="9325b-130">Speichern Sie die Textdatei als JavaScript-Datei mit der .js, z. B. delayLoadImages.js.</span><span class="sxs-lookup"><span data-stu-id="9325b-130">Save the text file as a JavaScript file with the extension .js, for example delayLoadImages.js.</span></span>
  
<span data-ttu-id="9325b-131">Nachdem Sie das Schreiben der delayLoadImages.js abgeschlossen haben, können Sie den Inhalt der Datei einer Masterseite in SharePoint Online hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9325b-131">Once you've finished writing delayLoadImages.js, you can add the contents of the file to a master page in SharePoint Online.</span></span> <span data-ttu-id="9325b-132">Dazu fügen Sie der Kopfzeile auf der Masterseite einen Skriptlink hinzu.</span><span class="sxs-lookup"><span data-stu-id="9325b-132">You do this by adding a script link to the header in the master page.</span></span> <span data-ttu-id="9325b-133">Sobald es sich in einer Gestaltungsgestaltungsseite ist, wird das JavaScript auf alle Seiten in Ihrer SharePoint Online-Website angewendet, die dieses Gestaltungsgestaltungslayout verwenden.</span><span class="sxs-lookup"><span data-stu-id="9325b-133">Once it's in a master page, the JavaScript will be applied to all pages in your SharePoint Online site that use that master page layout.</span></span> <span data-ttu-id="9325b-134">Wenn Sie dies nur auf einer Seite Ihrer Website verwenden möchten, verwenden Sie alternativ das Skript-Editor-Web part, um javaScript in die Seite einzubetten.</span><span class="sxs-lookup"><span data-stu-id="9325b-134">Alternatively, if you intend to only use this on one page of your site, use the script editor Web Part to embed the JavaScript into the page.</span></span> <span data-ttu-id="9325b-135">Weitere Informationen finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="9325b-135">See these topics for more information:</span></span>
  
- [<span data-ttu-id="9325b-136">Vorgehensweise: Anwenden einer Gestaltungsvorlage auf eine Website in SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="9325b-136">How to: Apply a master page to a site in SharePoint 2013</span></span>](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)

- [<span data-ttu-id="9325b-137">Vorgehensweise: Erstellen eines Seitenlayouts in SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="9325b-137">How to: Create a page layout in SharePoint 2013</span></span>](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)

### <a name="example-referencing-the-javascript-delayloadimagesjs-file-from-a-master-page-in-sharepoint-online"></a><span data-ttu-id="9325b-138">Beispiel: Verweisen auf die JavaScript-delayLoadImages.js von einer Masterseite in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9325b-138">Example: Referencing the JavaScript delayLoadImages.js file from a master page in SharePoint Online</span></span>
  
<span data-ttu-id="9325b-139">Damit dies funktioniert, müssen Sie auf der Masterseite auch auf jQuery verweisen.</span><span class="sxs-lookup"><span data-stu-id="9325b-139">In order for this to work, you also need to reference jQuery in the master page.</span></span> <span data-ttu-id="9325b-140">Im folgenden Beispiel sehen Sie in der ersten Seitenlade, dass nur ein Bild geladen ist, aber es sind mehrere weitere auf der Seite.</span><span class="sxs-lookup"><span data-stu-id="9325b-140">In the following example, you can see in the initial page load that there is only one image loaded but there are several more on the page.</span></span>
  
![Screenshot mit einem auf der Seite geladenen Bild](../media/3d177ddb-67e5-43a7-b327-c9f9566ca937.png)
  
<span data-ttu-id="9325b-142">Der folgende Screenshot zeigt die restlichen Bilder, die nach dem Bildlauf in die Ansicht heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="9325b-142">The following screenshot shows the rest of the images that are downloaded after they scroll into view.</span></span>
  
![Screenshot mit mehreren auf der Seite geladenen Bildern](../media/95eb2b14-f6a1-4eac-a5cb-96097e49514c.png)
  
<span data-ttu-id="9325b-144">Das Verzögern des Ladens von Bildern mithilfe von JavaScript kann eine effektive Technik zur Leistungssteigerung sein. Wenn die Technik jedoch auf einer öffentlichen Website angewendet wird, können Suchmaschinen die Bilder nicht auf die gleiche Weise durchforsten, wie sie ein regelmäßig gebildetes Bild durchforsten würden.</span><span class="sxs-lookup"><span data-stu-id="9325b-144">Delaying image loading by using JavaScript can be an effective technique in increasing performance; however, if the technique is applied on a public website then search engines are not able to crawl the images in the same way they would crawl a regularly formed image.</span></span> <span data-ttu-id="9325b-145">Dies kann sich auf die Rangfolge von Suchmaschinen auswirken, da Metadaten auf dem Bild selbst erst wirklich verfügbar sind, wenn die Seite geladen wird.</span><span class="sxs-lookup"><span data-stu-id="9325b-145">This can affect rankings on search engines because metadata on the image itself is not really there until the page loads.</span></span> <span data-ttu-id="9325b-146">Suchmaschinencrawler lesen nur den HTML-Code und sehen daher die Bilder nicht als Inhalt auf der Seite.</span><span class="sxs-lookup"><span data-stu-id="9325b-146">Search engine crawlers only read the HTML and therefore will not see the images as content on the page.</span></span> <span data-ttu-id="9325b-147">Bilder sind einer der Faktoren, die zum Rangieren von Seiten in Suchergebnissen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9325b-147">Images are one of the factors used to rank pages in search results.</span></span> <span data-ttu-id="9325b-148">Eine Möglichkeit, dies zu umarbeiten, ist die Verwendung von Einführungstext für Ihre Bilder.</span><span class="sxs-lookup"><span data-stu-id="9325b-148">One way to work around this is to use introductory text for your images.</span></span>
  
## <a name="github-code-sample-injecting-javascript-to-improve-performance"></a><span data-ttu-id="9325b-149">GitHub code sample: Injecting JavaScript to improve performance</span><span class="sxs-lookup"><span data-stu-id="9325b-149">GitHub code sample: Injecting JavaScript to improve performance</span></span>

<span data-ttu-id="9325b-150">Verpassen Sie nicht den Artikel und das Codebeispiel für [die JavaScript-Injection,](https://go.microsoft.com/fwlink/p/?LinkId=524759) die auf der GitHub.</span><span class="sxs-lookup"><span data-stu-id="9325b-150">Don't miss the article and code sample on [JavaScript injection](https://go.microsoft.com/fwlink/p/?LinkId=524759) provided on GitHub.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9325b-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9325b-151">See also</span></span>

[<span data-ttu-id="9325b-152">Unterstützte Browser in Office 2013 und Microsoft 365 Apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="9325b-152">Supported browsers in Office 2013 and Microsoft 365 Apps for enterprise</span></span>](https://support.office.com/article/57342811-0dc4-4316-b773-20082ced8a82)
  
[<span data-ttu-id="9325b-153">Vorgehensweise: Anwenden einer Gestaltungsvorlage auf eine Website in SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="9325b-153">How to: Apply a master page to a site in SharePoint 2013</span></span>](/sharepoint/dev/general-development/how-to-apply-a-master-page-to-a-site-in-sharepoint)
  
[<span data-ttu-id="9325b-154">Vorgehensweise: Erstellen eines Seitenlayouts in SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="9325b-154">How to: Create a page layout in SharePoint 2013</span></span>](/sharepoint/dev/general-development/how-to-create-a-page-layout-in-sharepoint)