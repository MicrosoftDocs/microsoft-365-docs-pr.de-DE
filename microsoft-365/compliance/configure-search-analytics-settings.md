---
title: Konfigurieren der Such- und Analyseeinstellungen
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
ms.assetid: ''
description: ''
ms.openlocfilehash: 0456ee21087c7fe05c3ef96d517feb468c7cfe5e
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081023"
---
# <a name="configure-search-and-analytics-settings"></a><span data-ttu-id="1143e-102">Konfigurieren der Such- und Analyseeinstellungen</span><span class="sxs-lookup"><span data-stu-id="1143e-102">Configure search and analytics settings</span></span>

## <a name="near-duplicates-and-email-threading"></a><span data-ttu-id="1143e-103">Nahe Duplikate und e-Mail-Threading</span><span class="sxs-lookup"><span data-stu-id="1143e-103">Near duplicates and email threading</span></span>

<span data-ttu-id="1143e-104">In diesem Abschnitt können Sie Parameter für die doppelte Erkennung, in der Nähe der doppelten Erkennung und beim e-Mail-Threading festlegen.</span><span class="sxs-lookup"><span data-stu-id="1143e-104">In this section, you can set parameters for duplicate detection, near duplicate detection, and email threading.</span></span>

- <span data-ttu-id="1143e-105">Aktivieren/deaktivieren: doppelte Erkennung, nahezu doppelte Erkennung und e-Mail-Threading als Teil des Analyse Flusses einschließen, falls aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1143e-105">Enable/disable: include duplicate detection, near duplicate detection, and email threading as part of analytics flow if enabled.</span></span> <span data-ttu-id="1143e-106">Da Sie sich übereinander aufbauen, müssen Sie alle aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="1143e-106">Because they build on top of each other, you must enable all of them or disable all of them.</span></span>

- <span data-ttu-id="1143e-107">Schwellenwert: Wenn sich die Ähnlichkeits Ebene zweier Dokumente über dem Schwellenwert befindet, werden Sie in derselben nahe doppelten Gruppe platziert.</span><span class="sxs-lookup"><span data-stu-id="1143e-107">Threshold: if the similarity level of two documents are above the threshold, they will be put in the same near duplicate set.</span></span>

- <span data-ttu-id="1143e-108">Duplikate standardmäßig ausblenden: Wenn diese Einstellung aktiviert ist, wird standardmäßig ein Filter zum Ausblenden von doppelten Dokumenten im Arbeitsmappen-Objekt angewendet.</span><span class="sxs-lookup"><span data-stu-id="1143e-108">Hide duplicates by default: if this setting is on, a filter to hide duplicate documents will be applied in the working set by default.</span></span> <span data-ttu-id="1143e-109">Der Filter kann bei Bedarf manuell im Arbeitsmappe entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="1143e-109">The filter can be removed manually in the working set if necessary.</span></span>

- <span data-ttu-id="1143e-110">Minimale/maximale Anzahl von Wörtern: nahe Duplikate und e-Mail-Threading werden nur für Dokumente ausgeführt, die mindestens die minimale Anzahl von Wörtern und höchstens die maximale Anzahl von Wörtern aufweisen.</span><span class="sxs-lookup"><span data-stu-id="1143e-110">Minimum/maximum number of words: near duplicates and email threading will run only on documents that have at least the minimum number of words and at most the maximum number of words.</span></span>
<span data-ttu-id="1143e-111">Weitere Informationen finden Sie [in der Nähe der doppelten Erkennung](near-duplicates.md) und des [e-Mail-Threadings](email-threading.md).</span><span class="sxs-lookup"><span data-stu-id="1143e-111">For more information, see [Near duplicate detection](near-duplicates.md) and [Email threading](email-threading.md).</span></span>

## <a name="themes"></a><span data-ttu-id="1143e-112">Designs</span><span class="sxs-lookup"><span data-stu-id="1143e-112">Themes</span></span>

<span data-ttu-id="1143e-113">In diesem Abschnitt können Sie Parameter für Designs festlegen.</span><span class="sxs-lookup"><span data-stu-id="1143e-113">In this section, you can set parameters for themes.</span></span>

- <span data-ttu-id="1143e-114">Aktivieren/deaktivieren: einbeziehen von Designs beim Clustering als Teil des Analyse Flusses, falls aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1143e-114">Enable/disable: include themes clustering as part of analytics flow if enabled.</span></span>
- <span data-ttu-id="1143e-115">Anpassen der maximalen Anzahl von Designs dynamisch dynamisch: in bestimmten Fällen gibt es nicht genügend Dokumente, um die gewünschte Anzahl von Designs zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1143e-115">Adjust maximum number of themes dynamically dynamically: in certain cases, there are not enough documents to produce the desired number of themes.</span></span> <span data-ttu-id="1143e-116">Wenn diese Einstellung aktiviert ist, wird nicht versucht, die gewünschte maximale Anzahl von Designs zu erzwingen, sondern das System passt die maximale Anzahl von Designs dynamisch an.</span><span class="sxs-lookup"><span data-stu-id="1143e-116">If this setting is turned on, then rather than trying to force the desired maximum number of themes, the system adjusts maximum number of themes dynamically.</span></span>
- <span data-ttu-id="1143e-117">Maximale Anzahl von Designs: gewünschte Anzahl von Designs</span><span class="sxs-lookup"><span data-stu-id="1143e-117">Maximum number of themes: desired number of themes</span></span>
- <span data-ttu-id="1143e-118">Zahlen in Designs einbeziehen: Wenn diese Option aktiviert ist, werden beim Generieren von Designs Zahlen in enthalten.</span><span class="sxs-lookup"><span data-stu-id="1143e-118">Include numbers in themes: When enabled, it will include numbers in when generating themes.</span></span>  

## <a name="optical-character-recognition-ocr"></a><span data-ttu-id="1143e-119">Optische Zeichenerkennung (OCR)</span><span class="sxs-lookup"><span data-stu-id="1143e-119">Optical character recognition (OCR)</span></span>

<span data-ttu-id="1143e-120">Wenn diese Einstellung aktiviert ist, wird die OCR für Bilder ausgeführt, die in Arbeitsmappen aufgenommen werden, sodass Sie durchsuchbar sein können.</span><span class="sxs-lookup"><span data-stu-id="1143e-120">When this setting is turned on, OCR will be run on images that are ingested into working sets so that they can be searchable.</span></span>

## <a name="ignore-text"></a><span data-ttu-id="1143e-121">Text ignorieren</span><span class="sxs-lookup"><span data-stu-id="1143e-121">Ignore text</span></span>

<span data-ttu-id="1143e-122">Es gibt Fälle, in denen bestimmte Texte die Qualität von Analysen vermindern, wie lange Haftungsausschlüsse, die zu bestimmten e-Mails hinzugefügt werden, unabhängig vom Inhalt der e-Mail.</span><span class="sxs-lookup"><span data-stu-id="1143e-122">There are instances where certain texts will diminish the quality of analytics, such as lengthy disclaimers that get added to certain emails regardless of the content of the email.</span></span> <span data-ttu-id="1143e-123">Wenn Sie solche Fälle kennen, können Sie diesen Text aus Analysen ausschließen, indem Sie den Text angeben (Regex wird unterstützt) und welche Module für den Text ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1143e-123">If you are aware of such cases, you can exclude this text from analytics by specifying the text (RegEx is supported) and which modules that text should be excluded for.</span></span>