---
title: Überprüfen der Inhaltssuchabfrage auf Fehler
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie Ihre Stichwortabfrage für die Inhaltssuche nach Fehlern und Tippfehlern überprüfen, beispielsweise nicht unterstützte Zeichen und boolesche Kleinbuchstaben Operatoren.
ms.openlocfilehash: 489afd8b2fe19742b63232d323197afecc257ccc
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035627"
---
# <a name="check-your-content-search-query-for-errors"></a><span data-ttu-id="5acfd-103">Überprüfen der Inhaltssuchabfrage auf Fehler</span><span class="sxs-lookup"><span data-stu-id="5acfd-103">Check your Content Search query for errors</span></span>

<span data-ttu-id="5acfd-104">Wenn Sie eine Inhaltssuche erstellen oder bearbeiten, kann Microsoft 365 die Abfrage auf nicht unterstützte Zeichen und boolesche Operatoren in Kleinbuchstaben überprüfen lassen.</span><span class="sxs-lookup"><span data-stu-id="5acfd-104">When you create or edit a Content Search, you can have Microsoft 365 check your query for unsupported characters and lowercase Boolean operators.</span></span> <span data-ttu-id="5acfd-105">Wie?</span><span class="sxs-lookup"><span data-stu-id="5acfd-105">How?</span></span> <span data-ttu-id="5acfd-106">Klicken Sie auf der Seite Abfrage einer Inhaltssuche einfach auf **Abfrage für Tippfehler überprüfen** .</span><span class="sxs-lookup"><span data-stu-id="5acfd-106">Just click **Check query for typos** on the query page of a Content Search.</span></span> 
  
![Klicken Sie auf "Abfrage für Tippfehler überprüfen", um Ihre Suchabfrage auf nicht unterstützte Zeichen zu überprüfen.](../media/e5314306-cfb2-481d-9b5c-13ce658156e7.png)
  
<span data-ttu-id="5acfd-108">Im folgenden finden Sie eine Liste der nicht unterstützten Zeichen, die wir überprüfen.</span><span class="sxs-lookup"><span data-stu-id="5acfd-108">Here's a list of the unsupported characters that we check for.</span></span> <span data-ttu-id="5acfd-109">Nicht unterstützte Zeichen werden häufig ausgeblendet, und Sie verursachen in der Regel einen Suchfehler oder geben unbeabsichtigte Ergebnisse zurück.</span><span class="sxs-lookup"><span data-stu-id="5acfd-109">Unsupported characters are often hidden, and they typically cause a search error or return unintended results.</span></span>
  
- <span data-ttu-id="5acfd-110">**Typografische Anführungs** Zeichen – intelligente einfache und doppelte Anführungszeichen (auch als Curly Anführungszeichen bezeichnet) werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5acfd-110">**Smart quotation marks** - Smart single and double quotation marks (also called curly quotes) aren't supported.</span></span> <span data-ttu-id="5acfd-111">Nur gerade Anführungszeichen können in einer Suchabfrage verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5acfd-111">Only straight quotation marks can be used in a search query.</span></span> 
    
- <span data-ttu-id="5acfd-112">Nicht **druckbare und Steuerzeichen** -nicht druckbare und Steuerzeichen stellen kein schriftliches Symbol dar, beispielsweise ein alphanumerisches Zeichen.</span><span class="sxs-lookup"><span data-stu-id="5acfd-112">**Non-printable and control characters** - Non-printable and control characters don't represent a written symbol, such as an alpha-numeric character.</span></span> <span data-ttu-id="5acfd-113">Beispiele für nicht druckbare Zeichen und Steuerzeichen sind Zeichen, die Text formatieren oder Textzeilen trennen.</span><span class="sxs-lookup"><span data-stu-id="5acfd-113">Examples of non-printable and control characters include characters that format text or separate lines of text.</span></span> 
    
- <span data-ttu-id="5acfd-114">**Links-nach-rechts-und rechts-nach-links-Markierungen** -diese Zeichen sind Steuerzeichen, die zum Anzeigen der Textrichtung für Links-nach-rechts-Sprachen (wie Englisch und Spanisch) und Sprachen mit Schreibrichtung von rechts nach Links verwendet werden (beispielsweise Arabisch und Hebräisch).</span><span class="sxs-lookup"><span data-stu-id="5acfd-114">**Left-to-right and right-to-left marks** - These marks are control characters used to indicate text direction for left-to-right languages (such as English and Spanish) and right-to-left languages (such as Arabic and Hebrew).</span></span>
    
- <span data-ttu-id="5acfd-115">**Kleinbuchstaben-boolesche Operatoren** – Wenn Sie einen booleschen Operator wie **and**, **or**und **Not** in einer Suchabfrage verwenden, muss er in Großbuchstaben eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5acfd-115">**Lowercase Boolean operators** - If you use a Boolean operator, such as **AND**, **OR**, and **NOT** in a search query, it must be uppercase.</span></span> <span data-ttu-id="5acfd-116">Wenn eine Abfrage auf Tippfehler überprüft wird, gibt die Abfragesyntax häufig an, dass ein boolescher Operator verwendet wird, obwohl klein-Operatoren verwendet werden können; andernfalls false. Beispiel: `(WordA or WordB) and (WordC or WordD)`.</span><span class="sxs-lookup"><span data-stu-id="5acfd-116">When we check a query for typos, the query syntax will often indicate that a Boolean operator is being used even though lowercase operators might be used; for example,  `(WordA or WordB) and (WordC or WordD)`.</span></span>
    
## <a name="what-happens-if-a-query-has-an-unsupported-character"></a><span data-ttu-id="5acfd-117">Was passiert, wenn eine Abfrage ein nicht unterstütztes Zeichen hat?</span><span class="sxs-lookup"><span data-stu-id="5acfd-117">What happens if a query has an unsupported character?</span></span>

<span data-ttu-id="5acfd-118">Wenn in Ihrer Abfrage nicht unterstützte Zeichen gefunden werden, wird eine Warnmeldung angezeigt, die besagt, dass nicht unterstützte Zeichen gefunden wurden, und schlägt eine Alternative vor.</span><span class="sxs-lookup"><span data-stu-id="5acfd-118">If unsupported characters are found in your query, a warning message is displayed that says unsupported characters were found and suggests an alternative.</span></span> <span data-ttu-id="5acfd-119">Anschließend können Sie die ursprüngliche Abfrage beibehalten oder durch die vorgeschlagene geänderte Abfrage ersetzen.</span><span class="sxs-lookup"><span data-stu-id="5acfd-119">You then have the option keep the original query or replace it with the suggested revised query.</span></span> <span data-ttu-id="5acfd-120">Hier ist ein Beispiel für die Warnmeldung, die angezeigt wird, nachdem Sie im vorherigen Screenshot auf **Abfrage für Tippfehler** für die Suchabfrage prüfen klicken.</span><span class="sxs-lookup"><span data-stu-id="5acfd-120">Here's an example of the warning message that's displayed after you click **Check query for typos** for the search query in the previous screenshot.</span></span> <span data-ttu-id="5acfd-121">Beachten Sie, dass die ursprüngliche Abfrage intelligente Anführungszeichen und Kleinbuchstaben-boolesche Operatoren enthält.</span><span class="sxs-lookup"><span data-stu-id="5acfd-121">Notice that the original query contains smart quotes and lowercase Boolean operators.</span></span> 
  
![Eine Warnmeldung mit einer vorgeschlagenen Überarbeitung für Ihre Abfrage wird angezeigt.](../media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a><span data-ttu-id="5acfd-123">Vorgehensweise verhindern, dass nicht unterstützte Zeichen in Ihren Suchabfragen</span><span class="sxs-lookup"><span data-stu-id="5acfd-123">How to prevent unsupported characters in your search queries</span></span>

<span data-ttu-id="5acfd-124">Nicht unterstützte Zeichen werden normalerweise einer Abfrage hinzugefügt, wenn Sie die Abfrage oder Teile der Abfrage aus anderen Anwendungen (wie Microsoft Word oder Microsoft Excel) kopieren und in das Feld Schlüsselwort auf der Seite Abfrage einer Inhaltssuche einfügen.</span><span class="sxs-lookup"><span data-stu-id="5acfd-124">Unsupported characters are typically added to a query when you copy the query or parts of the query from other applications (such as Microsoft Word or Microsoft Excel) and paste them in the keyword box on the query page of a Content Search.</span></span> <span data-ttu-id="5acfd-125">Die beste Möglichkeit zur Verhinderung nicht unterstützter Zeichen besteht darin, die Abfrage direkt in das Schlüsselwortfeld einzugeben.</span><span class="sxs-lookup"><span data-stu-id="5acfd-125">The best way to prevent unsupported characters is to just type the query in the keyword box.</span></span> <span data-ttu-id="5acfd-126">Sie können auch eine Abfrage aus Word oder Excel kopieren und dann in einem nur-Text-Editor wie Microsoft Notepad einfügen.</span><span class="sxs-lookup"><span data-stu-id="5acfd-126">Or you can copy a query from Word or Excel, and then paste it in a plain text editor, such as Microsoft Notepad.</span></span> <span data-ttu-id="5acfd-127">Speichern Sie die Textdatei, und wählen Sie in der Dropdownliste **Codierung** den Wert **ANSI** aus.</span><span class="sxs-lookup"><span data-stu-id="5acfd-127">Save the text file and select **ANSI** in the **Encoding** drop-down list.</span></span> <span data-ttu-id="5acfd-128">Dadurch werden alle Formatierungen und nicht unterstützten Zeichen entfernt.</span><span class="sxs-lookup"><span data-stu-id="5acfd-128">This will remove any formatting and unsupported characters.</span></span> <span data-ttu-id="5acfd-129">Anschließend können Sie die Abfrage aus der Textdatei kopieren und im Schlüsselwort-Abfragefeld einfügen.</span><span class="sxs-lookup"><span data-stu-id="5acfd-129">Then you can copy and paste the query from the text file to the keyword query box.</span></span> 
