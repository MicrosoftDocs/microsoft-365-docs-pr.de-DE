---
title: Verwenden des Kommunikations-Editors
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
description: Verwenden Sie den Kommunikations-Editor, um Text-und Seriendruckfeld Variablen beim Formatieren Ihres Inhalts zu ändern.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 6dcfb58dff3a3acf99340895872bb2da9795d9c8
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769160"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="23bb9-103">Verwenden des Kommunikations-Editors</span><span class="sxs-lookup"><span data-stu-id="23bb9-103">Use the communications editor</span></span>

<span data-ttu-id="23bb9-104">Wenn Sie den Inhalt Ihrer Portalinhalte, Benachrichtigungen über rechtliche Aufbewahrungszeit und zugehörige Erinnerungen/Eskalationen definieren, können Sie den Kommunikations-Editor verwenden, um Ihre Inhalte zu formatieren und dynamisch anzupassen.</span><span class="sxs-lookup"><span data-stu-id="23bb9-104">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can use the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="23bb9-105">Rich-Text-Editor</span><span class="sxs-lookup"><span data-stu-id="23bb9-105">Rich text editor</span></span>

<span data-ttu-id="23bb9-106">Mit dem Kommunikations-Editor können Benutzer den Text mithilfe der Editor-Optionen anpassen.</span><span class="sxs-lookup"><span data-stu-id="23bb9-106">The Communications Editor allows user to customize the text using the editor options.</span></span> <span data-ttu-id="23bb9-107">Beispielsweise können Benutzer Schriftarttypen ändern, Aufzählungslisten erstellen, Inhalte hervorheben und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="23bb9-107">For example, users can change font types, create bulleted lists, highlight content, and more.</span></span>

## <a name="merge-field-variables"></a><span data-ttu-id="23bb9-108">Zusammenführen von Feld Variablen</span><span class="sxs-lookup"><span data-stu-id="23bb9-108">Merge field variables</span></span>

<span data-ttu-id="23bb9-109">Sie können e-Mail-Zusammenführungs Variablen aus dem Kommunikations-Editor verwenden, um angepasste Depot Attribute in den Textkörper einer Kommunikation einzubetten.</span><span class="sxs-lookup"><span data-stu-id="23bb9-109">You can use email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text.</span></span> <span data-ttu-id="23bb9-110">Beim Senden an die Depotbank wird das Seriendruckfeld mit dem entsprechenden Feld aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="23bb9-110">When sent to the custodian, the merge field will be populated with the corresponding field.</span></span> <span data-ttu-id="23bb9-111">Wenn beispielsweise an den Depotbank John Smith gesendet wird, würde das Seriendruckfeld [Depot Name] mit dem entsprechenden Namen übersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="23bb9-111">For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span>

<span data-ttu-id="23bb9-112">Sie können Seriendruckfelder verwenden, indem Sie die **Seriendruckfeld** Symbole oben im Rich-Text-Editor-Steuerelement auswählen.</span><span class="sxs-lookup"><span data-stu-id="23bb9-112">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span></span> <span data-ttu-id="23bb9-113">Der Platzhalter wird basierend auf dem Speicherort des Cursors der Benutzer hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="23bb9-113">The placeholder will be added based off the location of the users' cursor.</span></span>

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="23bb9-114">Liste der Seriendruckfeld Variablen</span><span class="sxs-lookup"><span data-stu-id="23bb9-114">List of merge field variables</span></span>

| <span data-ttu-id="23bb9-115">Feldname</span><span class="sxs-lookup"><span data-stu-id="23bb9-115">Field name</span></span>                  | <span data-ttu-id="23bb9-116">Feld Details</span><span class="sxs-lookup"><span data-stu-id="23bb9-116">Field details</span></span> |
| :------------------- | :------------------- |
| <span data-ttu-id="23bb9-117">Anzeigename</span><span class="sxs-lookup"><span data-stu-id="23bb9-117">Display Name</span></span>  | <span data-ttu-id="23bb9-118">Der vor-und Nachname des Depotbank.</span><span class="sxs-lookup"><span data-stu-id="23bb9-118">The custodian's first and last name.</span></span> | 
| <span data-ttu-id="23bb9-119">Bestätigungs Link</span><span class="sxs-lookup"><span data-stu-id="23bb9-119">Acknowledgment Link</span></span> | <span data-ttu-id="23bb9-120">Ein benutzerdefinierter Link zum Aufzeichnen der Bestätigung jeder Depotbank.</span><span class="sxs-lookup"><span data-stu-id="23bb9-120">A customized link to record each custodian's acknowledgment.</span></span>|                 |
| <span data-ttu-id="23bb9-121">Portal Link</span><span class="sxs-lookup"><span data-stu-id="23bb9-121">Portal Link</span></span>     | <span data-ttu-id="23bb9-122">Ein benutzerdefinierter Link für das Compliance-Portal des Depotbank.</span><span class="sxs-lookup"><span data-stu-id="23bb9-122">A customized link for the custodian's Compliance Portal.</span></span>|                |
| <span data-ttu-id="23bb9-123">Ausstellenden Offizier</span><span class="sxs-lookup"><span data-stu-id="23bb9-123">Issuing Officer</span></span>                   | <span data-ttu-id="23bb9-124">Die e-Mail-Adresse des angegebenen ausstellenden Offiziers.</span><span class="sxs-lookup"><span data-stu-id="23bb9-124">The email address of the specified issuing officer.</span></span>|                   |
| <span data-ttu-id="23bb9-125">Ausstellendes Datum</span><span class="sxs-lookup"><span data-stu-id="23bb9-125">Issuing Date</span></span>                   | <span data-ttu-id="23bb9-126">Das Datum, an dem der Hinweis ausgegeben wurde (UTC).</span><span class="sxs-lookup"><span data-stu-id="23bb9-126">The date that the notice was issued (UTC).</span></span>              |
|||
