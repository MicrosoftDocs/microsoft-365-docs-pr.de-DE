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
# <a name="minification-and-bundling-in-sharepoint-online"></a><span data-ttu-id="95be9-103">Minimierung und Bündelung in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="95be9-103">Minification and bundling in SharePoint Online</span></span>

<span data-ttu-id="95be9-104">In diesem Artikel wird beschrieben, wie Sie Verminungs- und Bündelungstechniken mit Web Essentials verwenden, um die Anzahl der HTTP-Anforderungen zu reduzieren und den Zeitaufwand für das Laden von Seiten in SharePoint Online zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="95be9-104">This article describes how to use minification and bundling techniques with Web Essentials to reduce the number of HTTP requests and to reduce the time it takes to load pages in SharePoint Online.</span></span>
  
<span data-ttu-id="95be9-105">Wenn Sie Ihre Website anpassen, können Sie dem Server eine große Anzahl zusätzlicher Dateien hinzufügen, um die Anpassung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="95be9-105">When you customize your website you can end up adding a large number of extra files to the server to support the customization.</span></span> <span data-ttu-id="95be9-106">Durch hinzufügen zusätzlicher JavaScript-, CSS- und Bilder wird die Anzahl der HTTP-Anforderungen an den Server erhöht, was wiederum die Zeit erhöht, die zum Anzeigen einer Webseite benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="95be9-106">Adding extra JavaScript, CSS, and images increases the number of HTTP requests to the server which in turn increases the time it takes to display a web page.</span></span> <span data-ttu-id="95be9-107">Wenn Sie über mehrere Dateien desselben Typs verfügen, können Sie diese Dateien bündeln, um das Herunterladen dieser Dateien zu beschleunigen.</span><span class="sxs-lookup"><span data-stu-id="95be9-107">If you have multiple files of the same type, you can bundle these files to make downloading these files faster.</span></span>
  
<span data-ttu-id="95be9-108">Für JavaScript- und CSS-Dateien können Sie auch einen Ansatz namens Minification verwenden, bei dem Sie die Gesamtgröße von Dateien reduzieren, indem Sie Leerzeichen und andere Zeichen entfernen, die nicht erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="95be9-108">For JavaScript and CSS files, you can also use an approach called minification, where you reduce the total size of files by removing whitespace and other characters that aren't necessary.</span></span>
  
## <a name="minification-and-bundling-javascript-and-css-files-with-web-essentials"></a><span data-ttu-id="95be9-109">Verminen und Bündeln von JavaScript- und CSS-Dateien mit Web Essentials</span><span class="sxs-lookup"><span data-stu-id="95be9-109">Minification and bundling JavaScript and CSS files with Web Essentials</span></span>

<span data-ttu-id="95be9-110">Sie können Software von Drittanbietern wie Web Essentials verwenden, um CSS- und JavaScript-Dateien zu bündeln.</span><span class="sxs-lookup"><span data-stu-id="95be9-110">You can use third-party software such as Web Essentials to bundle CSS and JavaScript files.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="95be9-111">Web Essentials ist ein Open-Source-Projekt auf Communitybasis von Drittanbietern.</span><span class="sxs-lookup"><span data-stu-id="95be9-111">Web Essentials is a third-party, open-source, community-based project.</span></span> <span data-ttu-id="95be9-112">Die Software ist eine Erweiterung von Visual Studio 2012 und Visual Studio 2013 und wird von Microsoft nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="95be9-112">The software is an extension to Visual Studio 2012 and Visual Studio 2013 and is not supported by Microsoft.</span></span> <span data-ttu-id="95be9-113">Um Web Essentials herunterzuladen, besuchen Sie die Website unter [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629) .</span><span class="sxs-lookup"><span data-stu-id="95be9-113">To download Web Essentials, visit the website at [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629).</span></span> 
  
<span data-ttu-id="95be9-114">Web Essentials bietet zwei Arten von Bündelung:</span><span class="sxs-lookup"><span data-stu-id="95be9-114">Web Essentials offers two forms of bundling:</span></span>
  
- <span data-ttu-id="95be9-115">.bundle: für CSS- und JavaScript-Dateien</span><span class="sxs-lookup"><span data-stu-id="95be9-115">.bundle: for CSS and JavaScript files</span></span>
    
- <span data-ttu-id="95be9-116">.sprite: für Bilder (nur in Visual Studio 2013)</span><span class="sxs-lookup"><span data-stu-id="95be9-116">.sprite: for images (only available in Visual Studio 2013)</span></span>
    
<span data-ttu-id="95be9-117">Sie können Web Essentials verwenden, wenn Sie über ein vorhandenes Feature mit einigen Brandingelementen verfügen, auf die in einer benutzerdefinierten Masterseite verwiesen wird, z. B.:</span><span class="sxs-lookup"><span data-stu-id="95be9-117">You can use Web Essentials if you have an existing feature with some branding elements that are referenced inside a custom master page, such as:</span></span>
  
![Screenshot des Markenelements auf der benutzerdefinierten Masterseite](../media/3a6eba36-973d-482b-8556-a9394b8ba19f.png)
  
 <span data-ttu-id="95be9-119">**So erstellen Sie ein TE000127218- und CSS-Bundle in Web Essentials**</span><span class="sxs-lookup"><span data-stu-id="95be9-119">**To create a TE000127218 and CSS bundle in Web Essentials**</span></span>
  
1. <span data-ttu-id="95be9-120">Wählen Visual Studio im Projektmappen-Explorer die Dateien aus, die Sie in das Bundle hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="95be9-120">In Visual Studio, in Solution Explorer, select the files that you want to include in the bundle.</span></span>
    
2. <span data-ttu-id="95be9-121">Klicken Sie mit der rechten Maustaste auf die ausgewählten Dateien, und wählen Sie dann im Kontextmenü **Web Essentials** \> **Create JavaScript bundle file** aus.</span><span class="sxs-lookup"><span data-stu-id="95be9-121">Right-click the selected files and then select **Web Essentials** \> **Create JavaScript bundle file** from the context menu.</span></span> <span data-ttu-id="95be9-122">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="95be9-122">For example:</span></span> 
    
    ![Screenshot mit Web Essentials-Menüoptionen](../media/41aac84c-4538-4f78-b454-46e651f868a3.png)
  
## <a name="viewing-the-results-of-bundling-javascript-and-css-files"></a><span data-ttu-id="95be9-124">Anzeigen der Ergebnisse der Bündelung von JavaScript- und CSS-Dateien</span><span class="sxs-lookup"><span data-stu-id="95be9-124">Viewing the results of bundling JavaScript and CSS files</span></span>

<span data-ttu-id="95be9-125">Wenn Sie ein JavaScript- und CSS-Bündel erstellen, erstellt Web Essentials eine XML-Datei namens Rezeptdatei, die die JavaScript- und CSS-Dateien sowie einige andere Konfigurationsinformationen identifiziert:</span><span class="sxs-lookup"><span data-stu-id="95be9-125">When you create a JavaScript and CSS bundle, Web Essentials creates an XML file called a recipe file that identifies the JavaScript and CSS files as well as some other configuration information:</span></span> 
  
![Screenshot der JavaScript- und CSS-Rezeptdatei](../media/7ba891f8-52d8-467b-a0f6-b062dd1137a4.png)
  
<span data-ttu-id="95be9-127">Wenn das Minify-Flag im Bündelungsrezept auf true festgelegt ist, werden die Dateien außerdem in der Größe reduziert und zusammengebündelt.</span><span class="sxs-lookup"><span data-stu-id="95be9-127">In addition, if the minify flag is set to true in the bundling recipe the files are reduced in size as well as bundled together.</span></span> <span data-ttu-id="95be9-128">Dies bedeutet, dass neue, verminte Versionen der JavaScript-Dateien erstellt wurden, auf die Sie in Ihrer Masterseite verweisen können.</span><span class="sxs-lookup"><span data-stu-id="95be9-128">This means that new, minified versions of the JavaScript files were created that you can reference in your master page.</span></span>
  
![Screenshot des auf true festgelegten Minify-Flags](../media/50523af2-6412-4117-ac3d-5bd26f6d562e.png)
  
<span data-ttu-id="95be9-130">Wenn Sie eine Seite von Ihrer Website laden, können Sie die Entwicklertools aus Ihrem Webbrowser verwenden, z. B. Internet Explorer 11, um die Anzahl der anforderungen anzuzeigen, die an den Server gesendet wurden und wie lange die Einzelnen Dateien geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="95be9-130">When you load a page from your web site, you can use the developer tools from your web browser, such as Internet Explorer 11, to see the number of requests sent to the server and how long each file took to load.</span></span>
  
<span data-ttu-id="95be9-131">Die folgende Abbildung ist das Ergebnis des Ladens der JavaScript- und CSS-Dateien vor der Minifizierung.</span><span class="sxs-lookup"><span data-stu-id="95be9-131">The following figure is the result of loading the JavaScript and CSS files before minification.</span></span>
  
![Screenshot mit 80 heruntergeladenen Elementen](../media/e2df3912-1923-46e6-8cf2-3015a31554e1.png)
  
<span data-ttu-id="95be9-133">Nach dem Bündeln der CSS- und JavaScript-Dateien ist die Anzahl der Anforderungen auf 74 gesunken, und jede Datei hat nur geringfügig länger ge dauert als die ursprünglichen Dateien, um sie einzeln herunterzuladen:</span><span class="sxs-lookup"><span data-stu-id="95be9-133">After bundling the CSS and JavaScript files together, the number of requests dropped to 74 and each file took only slightly longer than the original files to download individually:</span></span>
  
![Screenshot mit 74 heruntergeladenen Elementen](../media/686c4387-70e8-4a74-9d45-059f33a91184.png)
  
<span data-ttu-id="95be9-135">Nach der Bündelung wird die JavaScript-Bundledatei erheblich von 815 KB auf 365 KB reduziert:</span><span class="sxs-lookup"><span data-stu-id="95be9-135">After bundling, the JavaScript bundle file is reduced significantly from 815KB to 365KB:</span></span>
  
![Screenshot mit reduzierter Downloadgröße](../media/5e7dbd98-faff-4f68-b320-108fb252e395.png)
  
## <a name="bundling-images-by-creating-an-image-sprite"></a><span data-ttu-id="95be9-137">Bündeln von Bildern durch Erstellen eines Bildsprites</span><span class="sxs-lookup"><span data-stu-id="95be9-137">Bundling images by creating an image sprite</span></span>

<span data-ttu-id="95be9-138">Ähnlich wie Sie JavaScript- und CSS-Dateien bündeln, können Sie viele kleine Symbole und andere allgemeine Bilder in einem größeren Spritesheet kombinieren und dann CSS verwenden, um die einzelnen Bilder zu zeigen.</span><span class="sxs-lookup"><span data-stu-id="95be9-138">Similar to how you bundle JavaScript and CSS files, you can combine many small icons and other common images into a larger sprite sheet and then use CSS to reveal the individual images.</span></span> <span data-ttu-id="95be9-139">Anstatt jedes einzelne Bild herunterzuladen, lädt der Webbrowser des Benutzers das Spritesheet einmal herunter und speichert es dann auf dem lokalen Computer zwischen.</span><span class="sxs-lookup"><span data-stu-id="95be9-139">Instead of downloading each individual image, the user's web browser downloads the sprite sheet once and then caches it on the local computer.</span></span> <span data-ttu-id="95be9-140">Dadurch wird die Seitenlastleistung verbessert, indem die Anzahl der Downloads und Roundtrips zum Webserver herabgefahren wird.</span><span class="sxs-lookup"><span data-stu-id="95be9-140">This improves page load performance by cutting down on the number of downloads and round trips to the web server.</span></span>
  
 <span data-ttu-id="95be9-141">**So erstellen Sie ein Bild-Sprite in Web Essentials**</span><span class="sxs-lookup"><span data-stu-id="95be9-141">**To create an image sprite in Web Essentials**</span></span>
  
1. <span data-ttu-id="95be9-142">Wählen Visual Studio im Projektmappen-Explorer die Dateien aus, die Sie in das Bundle hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="95be9-142">In Visual Studio, in Solution Explorer, select the files that you want to include in the bundle.</span></span>
    
2. <span data-ttu-id="95be9-143">Klicken Sie mit der rechten Maustaste auf die ausgewählten Dateien, und wählen Sie dann im Kontextmenü **Web Essentials** \> **Image sprite** erstellen aus.</span><span class="sxs-lookup"><span data-stu-id="95be9-143">Right-click the selected files and then select **Web Essentials** \> **Create image sprite** from the context menu.</span></span> <span data-ttu-id="95be9-144">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="95be9-144">For example:</span></span> 
    
    ![Screenshot, der zeigt, wie Sie ein Bild-Sprite erstellen](../media/de0fe741-4ef7-4e3b-bafa-ef9f4822dac6.png)
  
3. <span data-ttu-id="95be9-146">Wählen Sie einen Speicherort aus, um die sprite-Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="95be9-146">Choose a location to save the sprite file.</span></span> <span data-ttu-id="95be9-147">Die SPRITE-Datei ist eine XML-Datei, die die Einstellungen und Dateien im sprite beschreibt.</span><span class="sxs-lookup"><span data-stu-id="95be9-147">The .sprite file is an XML file that describes the settings and files in the sprite.</span></span> <span data-ttu-id="95be9-148">Die folgenden Abbildungen zeigen ein Beispiel für eine sprite-PNG-Datei und die entsprechende SPRITE-XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="95be9-148">The following figures show an example of a sprite PNG file and its corresponding .sprite XML file.</span></span>
    
    ![Screenshot einer sprite-Datei](../media/0876bb2a-d1b9-4169-8e95-9c290d628d90.png)
  
    ![Screenshot der sprite-XML-Datei](../media/d1f94776-280d-4d56-abb5-384f145d9989.png)
  

