---
title: Überprüfen Ihrer Suchabfrage auf Fehler
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
search.appverid:
- MOE150
- MET150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
ms.custom: seo-marvel-apr2020
description: Erfahren Sie, wie Sie Fehler und Tippfehler in Ihrer Schlüsselwortabfrage für eDiscovery-Suchen erkennen, bevor Sie die Suche ausführen.
ms.openlocfilehash: 9c041ca690df3306347cbca77df3ba9639801245
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311688"
---
# <a name="check-your-search-query-for-errors"></a><span data-ttu-id="b1add-103">Überprüfen Ihrer Suchabfrage auf Fehler</span><span class="sxs-lookup"><span data-stu-id="b1add-103">Check your search query for errors</span></span>
  
<span data-ttu-id="b1add-104">Hier ist eine Liste der nicht unterstützten Zeichen, die wir in Suchabfragen für die Inhaltssuche und Core eDiscovery suchen.</span><span class="sxs-lookup"><span data-stu-id="b1add-104">Here's a list of the unsupported characters that we check for in search queries for Content search and Core eDiscovery.</span></span> <span data-ttu-id="b1add-105">Nicht unterstützte Zeichen werden häufig ausgeblendet und verursachen in der Regel einen Suchfehler oder geben unbeabsichtigte Ergebnisse zurück.</span><span class="sxs-lookup"><span data-stu-id="b1add-105">Unsupported characters are often hidden, and they typically cause a search error or return unintended results.</span></span>
  
- <span data-ttu-id="b1add-106">**Intelligente Anführungszeichen** – Intelligente einfache und doppelte Anführungszeichen (auch als geschweifte Anführungszeichen bezeichnet) werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b1add-106">**Smart quotation marks** - Smart single and double quotation marks (also called curly quotes) aren't supported.</span></span> <span data-ttu-id="b1add-107">Nur gerade Anführungszeichen können in einer Suchabfrage verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b1add-107">Only straight quotation marks can be used in a search query.</span></span> 

- <span data-ttu-id="b1add-108">**Nicht druckbare Zeichen und Steuerelementzeichen** : Nicht druckbare Zeichen und Steuerelementzeichen stellen kein geschriebenes Symbol dar, z. B. ein alphanumerisches Zeichen.</span><span class="sxs-lookup"><span data-stu-id="b1add-108">**Non-printable and control characters** - Non-printable and control characters don't represent a written symbol, such as an alpha-numeric character.</span></span> <span data-ttu-id="b1add-109">Beispiele für nicht druckbare Zeichen und Steuerzeichen sind Zeichen, die Text formatieren oder Textzeilen trennen.</span><span class="sxs-lookup"><span data-stu-id="b1add-109">Examples of non-printable and control characters include characters that format text or separate lines of text.</span></span> 

- <span data-ttu-id="b1add-110">Markierungen von links nach rechts und von rechts nach links **:** Diese Markierungen sind Steuerzeichen, die zum Angeben der Textrichtung für Sprachen von links nach rechts (z. B. Englisch und Spanisch) und von rechts nach links (z. B. Arabisch und Hebräisch) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b1add-110">**Left-to-right and right-to-left marks** - These marks are control characters used to indicate text direction for left-to-right languages (such as English and Spanish) and right-to-left languages (such as Arabic and Hebrew).</span></span>

- <span data-ttu-id="b1add-111">**Boolesche Kleinbuchstabenoperatoren** : Wenn Sie einen booleschen Operator wie **AND**, **OR** und **NOT** in einer Suchabfrage verwenden, muss er Großbuchstaben sein.</span><span class="sxs-lookup"><span data-stu-id="b1add-111">**Lowercase Boolean operators** - If you use a Boolean operator, such as **AND**, **OR**, and **NOT** in a search query, it must be uppercase.</span></span> <span data-ttu-id="b1add-112">Wenn wir eine Abfrage auf Tippfehler überprüfen, weist die Abfragesyntax häufig darauf hin, dass ein boolescher Operator verwendet wird, auch wenn Kleinbuchstabenoperatoren verwendet werden können. Beispiel:  `(WordA or WordB) and (WordC or WordD)` .</span><span class="sxs-lookup"><span data-stu-id="b1add-112">When we check a query for typos, the query syntax will often indicate that a Boolean operator is being used even though lowercase operators might be used; for example,  `(WordA or WordB) and (WordC or WordD)`.</span></span>

## <a name="what-happens-if-a-query-has-an-unsupported-character"></a><span data-ttu-id="b1add-113">Was geschieht, wenn eine Abfrage ein nicht unterstütztes Zeichen hat?</span><span class="sxs-lookup"><span data-stu-id="b1add-113">What happens if a query has an unsupported character?</span></span>

<span data-ttu-id="b1add-114">Wenn in Ihrer Abfrage nicht unterstützte Zeichen gefunden werden, wird eine Warnmeldung angezeigt, dass nicht unterstützte Zeichen gefunden wurden, und es wird eine Alternative vorgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="b1add-114">If unsupported characters are found in your query, a warning message is displayed that says unsupported characters were found and suggests an alternative.</span></span> <span data-ttu-id="b1add-115">Anschließend können Sie die ursprüngliche Abfrage behalten oder durch die vorgeschlagene überarbeitete Abfrage ersetzen.</span><span class="sxs-lookup"><span data-stu-id="b1add-115">You then have the option keep the original query or replace it with the suggested revised query.</span></span>

<span data-ttu-id="b1add-116">Hier sehen Sie ein Beispiel für die Warnmeldung,  die angezeigt wird, nachdem Sie im vorherigen Screenshot auf Abfrage auf Tippfehler für die Suchabfrage überprüfen geklickt haben.</span><span class="sxs-lookup"><span data-stu-id="b1add-116">Here's an example of the warning message that's displayed after you click **Check query for typos** for the search query in the previous screenshot.</span></span> <span data-ttu-id="b1add-117">Beachten Sie, dass die ursprüngliche Abfrage intelligente Anführungszeichen und boolesche Kleinbuchstabenoperatoren verwendet.</span><span class="sxs-lookup"><span data-stu-id="b1add-117">Note the original query used smart quotes and lowercase Boolean operators.</span></span>
  
![Eine Warnmeldung wird mit einer vorgeschlagenen Überarbeitung für Ihre Abfrage angezeigt.](../media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a><span data-ttu-id="b1add-119">Verhindern nicht unterstützter Zeichen in Suchabfragen</span><span class="sxs-lookup"><span data-stu-id="b1add-119">How to prevent unsupported characters in your search queries</span></span>

<span data-ttu-id="b1add-120">Nicht unterstützte Zeichen werden in der Regel einer Abfrage hinzugefügt, wenn Sie die Abfrage oder Teile der Abfrage aus anderen Anwendungen (z. B. Microsoft Word oder Microsoft Excel) kopieren und in das Schlüsselwortfeld auf der Abfrageseite einer Inhaltssuche einfügen.</span><span class="sxs-lookup"><span data-stu-id="b1add-120">Unsupported characters are typically added to a query when you copy the query or parts of the query from other applications (such as Microsoft Word or Microsoft Excel) and paste them in the keyword box on the query page of a Content Search.</span></span> <span data-ttu-id="b1add-121">Die beste Möglichkeit zur Verhinderung nicht unterstützter Zeichen besteht darin, die Abfrage direkt in das Schlüsselwortfeld einzugeben.</span><span class="sxs-lookup"><span data-stu-id="b1add-121">The best way to prevent unsupported characters is to just type the query in the keyword box.</span></span> <span data-ttu-id="b1add-122">Sie können auch eine Abfrage aus Word oder Excel kopieren und dann in einen Nur-Text-Editor einfügen, z. B. Microsoft Editor.</span><span class="sxs-lookup"><span data-stu-id="b1add-122">Or you can copy a query from Word or Excel, and then paste it in a plain text editor, such as Microsoft Notepad.</span></span> <span data-ttu-id="b1add-123">Speichern Sie die Textdatei, und wählen **Sie INSI** in der **Dropdownliste Codierung** aus.</span><span class="sxs-lookup"><span data-stu-id="b1add-123">Save the text file and select **ANSI** in the **Encoding** drop-down list.</span></span> <span data-ttu-id="b1add-124">Dadurch werden alle Formatierungen und nicht unterstützten Zeichen entfernt.</span><span class="sxs-lookup"><span data-stu-id="b1add-124">This will remove any formatting and unsupported characters.</span></span> <span data-ttu-id="b1add-125">Anschließend können Sie die Abfrage aus der Textdatei kopieren und im Schlüsselwort-Abfragefeld einfügen.</span><span class="sxs-lookup"><span data-stu-id="b1add-125">Then you can copy and paste the query from the text file to the keyword query box.</span></span>
