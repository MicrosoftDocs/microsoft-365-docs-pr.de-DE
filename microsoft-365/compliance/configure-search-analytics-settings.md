---
title: Konfigurieren von Such-und Analyse Einstellungen-Daten Untersuchungen
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: In diesem Artikel erfahren Sie, wie Sie Such-und Analyse Einstellungen wie etwa Duplikate, e-Mail-Threading und Designs beim Verwalten von Daten Untersuchungen konfigurieren.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ebc04e68c4d8854c91ceae75b164cc061e77aad4
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277073"
---
# <a name="configure-search-and-analytics-settings-in-data-investigations"></a><span data-ttu-id="d3897-103">Konfigurieren von Such-und Analyse Einstellungen in Daten Untersuchungen</span><span class="sxs-lookup"><span data-stu-id="d3897-103">Configure search and analytics settings in Data Investigations</span></span>

## <a name="near-duplicates-and-email-threading"></a><span data-ttu-id="d3897-104">Erkennung von Quasiduplikaten und E-Mail-Threading</span><span class="sxs-lookup"><span data-stu-id="d3897-104">Near duplicates and email threading</span></span>

<span data-ttu-id="d3897-105">In diesem Abschnitt können Sie Parameter für die doppelte Erkennung, in der Nähe der doppelten Erkennung und beim e-Mail-Threading festlegen.</span><span class="sxs-lookup"><span data-stu-id="d3897-105">In this section, you can set parameters for duplicate detection, near duplicate detection, and email threading.</span></span>

- <span data-ttu-id="d3897-106">Aktivieren/deaktivieren: doppelte Erkennung, nahezu doppelte Erkennung und e-Mail-Threading als Teil des Analyse Flusses einschließen, falls aktiviert.</span><span class="sxs-lookup"><span data-stu-id="d3897-106">Enable/disable: include duplicate detection, near duplicate detection, and email threading as part of analytics flow if enabled.</span></span> <span data-ttu-id="d3897-107">Da Sie sich übereinander aufbauen, müssen Sie alle aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="d3897-107">Because they build on top of each other, you must enable all of them or disable all of them.</span></span>

- <span data-ttu-id="d3897-108">Schwellenwert: Wenn sich die Ähnlichkeits Ebene von zwei Dokumenten über dem Schwellenwert befindet, werden Sie in derselben nahe doppelten Gruppe platziert.</span><span class="sxs-lookup"><span data-stu-id="d3897-108">Threshold: if the similarity level of two documents is above the threshold, they will be put in the same near duplicate set.</span></span>

- <span data-ttu-id="d3897-109">Duplikate standardmäßig ausblenden: Wenn diese Einstellung aktiviert ist, wird standardmäßig ein Filter zum Ausblenden von doppelten Dokumenten im Arbeitsmappen-Objekt angewendet.</span><span class="sxs-lookup"><span data-stu-id="d3897-109">Hide duplicates by default: if this setting is on, a filter to hide duplicate documents will be applied in the working set by default.</span></span> <span data-ttu-id="d3897-110">Der Filter kann bei Bedarf manuell im Arbeitsmappe entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="d3897-110">The filter can be removed manually in the working set if necessary.</span></span>

- <span data-ttu-id="d3897-111">Minimale/maximale Anzahl von Wörtern: nahe Duplikate und e-Mail-Threading werden nur für Dokumente ausgeführt, die mindestens die minimale Anzahl von Wörtern und höchstens die maximale Anzahl von Wörtern aufweisen.</span><span class="sxs-lookup"><span data-stu-id="d3897-111">Minimum/maximum number of words: near duplicates and email threading will run only on documents that have at least the minimum number of words and at most the maximum number of words.</span></span>

<span data-ttu-id="d3897-112">Weitere Informationen finden Sie [in der Nähe der doppelten Erkennung](near-duplicates.md) und des [e-Mail-Threadings](email-threading.md).</span><span class="sxs-lookup"><span data-stu-id="d3897-112">For more information, see [Near duplicate detection](near-duplicates.md) and [Email threading](email-threading.md).</span></span>

## <a name="themes"></a><span data-ttu-id="d3897-113">Designs</span><span class="sxs-lookup"><span data-stu-id="d3897-113">Themes</span></span>

<span data-ttu-id="d3897-114">In diesem Abschnitt können Sie Parameter für Designs festlegen.</span><span class="sxs-lookup"><span data-stu-id="d3897-114">In this section, you can set parameters for themes.</span></span>

- <span data-ttu-id="d3897-115">Aktivieren/deaktivieren: einbeziehen von Designs beim Clustering als Teil des Analyse Flusses, falls aktiviert.</span><span class="sxs-lookup"><span data-stu-id="d3897-115">Enable/disable: include themes clustering as part of analytics flow if enabled.</span></span>

- <span data-ttu-id="d3897-116">Anpassen der maximalen Anzahl von Designs dynamisch: in bestimmten Fällen gibt es nicht genügend Dokumente, um die gewünschte Anzahl von Designs zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d3897-116">Adjust maximum number of themes dynamically: in certain cases, there are not enough documents to produce the desired number of themes.</span></span> <span data-ttu-id="d3897-117">Wenn diese Einstellung aktiviert ist, wird nicht versucht, die gewünschte maximale Anzahl von Designs zu erzwingen, sondern das System passt die maximale Anzahl von Designs dynamisch an.</span><span class="sxs-lookup"><span data-stu-id="d3897-117">If this setting is turned on, then rather than trying to force the desired maximum number of themes, the system adjusts maximum number of themes dynamically.</span></span>

- <span data-ttu-id="d3897-118">Maximale Anzahl von Designs: gewünschte Anzahl von Designs.</span><span class="sxs-lookup"><span data-stu-id="d3897-118">Maximum number of themes: desired number of themes.</span></span>

- <span data-ttu-id="d3897-119">Zahlen in Designs einbeziehen: Wenn diese Option aktiviert ist, werden beim Generieren von Designs Zahlen in enthalten.</span><span class="sxs-lookup"><span data-stu-id="d3897-119">Include numbers in themes: When enabled, it will include numbers in when generating themes.</span></span>  

## <a name="optical-character-recognition-ocr"></a><span data-ttu-id="d3897-120">Optical Character Recognition (OCR; optische Zeichenerkennung)</span><span class="sxs-lookup"><span data-stu-id="d3897-120">Optical character recognition (OCR)</span></span>

<span data-ttu-id="d3897-121">Wenn diese Einstellung aktiviert ist, wird die OCR für Bilder ausgeführt, die in Arbeitsmappen aufgenommen werden, sodass Sie durchsuchbar sein können.</span><span class="sxs-lookup"><span data-stu-id="d3897-121">When this setting is turned on, OCR will be run on images that are ingested into working sets so that they can be searchable.</span></span>

## <a name="ignore-text"></a><span data-ttu-id="d3897-122">Ignorieren von Text</span><span class="sxs-lookup"><span data-stu-id="d3897-122">Ignore text</span></span>

<span data-ttu-id="d3897-123">Es gibt Fälle, in denen bestimmte Texte die Qualität von Analysen vermindern, wie lange Haftungsausschlüsse, die zu bestimmten e-Mails hinzugefügt werden, unabhängig vom Inhalt der e-Mail.</span><span class="sxs-lookup"><span data-stu-id="d3897-123">There are instances where certain texts will diminish the quality of analytics, such as lengthy disclaimers that get added to certain emails regardless of the content of the email.</span></span> <span data-ttu-id="d3897-124">Wenn Sie solche Fälle kennen, können Sie diesen Text aus Analysen ausschließen, indem Sie den Text angeben (Regex wird unterstützt) und welche Module für den Text ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d3897-124">If you are aware of such cases, you can exclude this text from analytics by specifying the text (RegEx is supported) and which modules that text should be excluded for.</span></span>
