---
title: Verwenden des Kommunikations-Editors
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
ms.openlocfilehash: 78865efc5c10ebcff9742f922f675b637bb9b2b0
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082127"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="5fea0-102">Verwenden des Kommunikations-Editors</span><span class="sxs-lookup"><span data-stu-id="5fea0-102">Use the communications editor</span></span>

<span data-ttu-id="5fea0-103">Wenn Sie den Inhalt Ihrer Portalinhalte, Benachrichtigungen über rechtliche Aufbewahrungszeit und zugehörige Erinnerungen/Eskalationen definieren, können Sie den Kommunikations-Editor nutzen, um Ihre Inhalte zu formatieren und dynamisch anzupassen.</span><span class="sxs-lookup"><span data-stu-id="5fea0-103">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can leverage the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="5fea0-104">Rich-Text-Editor</span><span class="sxs-lookup"><span data-stu-id="5fea0-104">Rich text editor</span></span> 

<span data-ttu-id="5fea0-105">Mit dem Kommunikations-Editor können Benutzer den Text mithilfe der Editor-Optionen anpassen.</span><span class="sxs-lookup"><span data-stu-id="5fea0-105">The Communications Editor allows user to customize the text using the editor options.</span></span> <span data-ttu-id="5fea0-106">Beispielsweise können Benutzer Schriftarttypen ändern, Aufzählungslisten erstellen, Inhalte hervorheben und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="5fea0-106">For example, users can change font types, create bulleted lists, highlight content, and more.</span></span> 

## <a name="merge-field-variables"></a><span data-ttu-id="5fea0-107">Zusammenführen von Feld Variablen</span><span class="sxs-lookup"><span data-stu-id="5fea0-107">Merge field variables</span></span>

<span data-ttu-id="5fea0-108">Sie können e-Mail-Zusammenführungs Variablen aus dem Kommunikations-Editor nutzen, um angepasste Depot Attribute in den Textkörper einer Kommunikation einzubetten.</span><span class="sxs-lookup"><span data-stu-id="5fea0-108">You can leverage email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text.</span></span> <span data-ttu-id="5fea0-109">Beim Senden an die Depotbank wird das Seriendruckfeld mit dem entsprechenden Feld aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="5fea0-109">When sent to the custodian, the merge field will be populated with the corresponding field.</span></span> <span data-ttu-id="5fea0-110">Wenn beispielsweise an den Depotbank John Smith gesendet wird, würde das Seriendruckfeld [Depot Name] mit dem entsprechenden Namen übersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="5fea0-110">For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span> 

<span data-ttu-id="5fea0-111">Sie können Seriendruckfelder verwenden, indem Sie die **Seriendruckfeld** Symbole oben im Rich-Text-Editor-Steuerelement auswählen.</span><span class="sxs-lookup"><span data-stu-id="5fea0-111">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span></span> <span data-ttu-id="5fea0-112">Der Platzhalter wird basierend auf dem Speicherort des Cursors der Benutzer hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5fea0-112">The placeholder will be added based off the location of the users' cursor.</span></span> 

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="5fea0-113">Liste der Seriendruckfeld Variablen</span><span class="sxs-lookup"><span data-stu-id="5fea0-113">List of merge field variables</span></span>

| <span data-ttu-id="5fea0-114">Feldname</span><span class="sxs-lookup"><span data-stu-id="5fea0-114">Field name</span></span>                  | <span data-ttu-id="5fea0-115">Feld Details</span><span class="sxs-lookup"><span data-stu-id="5fea0-115">Field details</span></span> | 
| :------------------- | :------------------- |
| <span data-ttu-id="5fea0-116">Anzeigename</span><span class="sxs-lookup"><span data-stu-id="5fea0-116">Display Name</span></span>  | <span data-ttu-id="5fea0-117">Der vor-und Nachname des Depotbank.</span><span class="sxs-lookup"><span data-stu-id="5fea0-117">The custodian's first and last name.</span></span> | 
| <span data-ttu-id="5fea0-118">Bestätigungs Link</span><span class="sxs-lookup"><span data-stu-id="5fea0-118">Acknowledgement Link</span></span> | <span data-ttu-id="5fea0-119">Ein benutzerdefinierter Link zum Aufzeichnen der Bestätigung jedes Verwalters.</span><span class="sxs-lookup"><span data-stu-id="5fea0-119">A customized link to record each custodian's acknowledgement.</span></span>|                 |
| <span data-ttu-id="5fea0-120">Portal Link</span><span class="sxs-lookup"><span data-stu-id="5fea0-120">Portal Link</span></span>     | <span data-ttu-id="5fea0-121">Ein benutzerdefinierter Link für das Compliance-Portal des Depotbank.</span><span class="sxs-lookup"><span data-stu-id="5fea0-121">A customized link for the custodian's Compliance Portal.</span></span>|                |
| <span data-ttu-id="5fea0-122">Ausstellenden Offizier</span><span class="sxs-lookup"><span data-stu-id="5fea0-122">Issuing Officer</span></span>                   | <span data-ttu-id="5fea0-123">Die e-Mail-Adresse des angegebenen ausstellenden Offiziers.</span><span class="sxs-lookup"><span data-stu-id="5fea0-123">The email address of the specified issuing officer.</span></span>|                   |
| <span data-ttu-id="5fea0-124">Ausstellendes Datum</span><span class="sxs-lookup"><span data-stu-id="5fea0-124">Issuing Date</span></span>                   | <span data-ttu-id="5fea0-125">Das Datum, an dem der Hinweis ausgegeben wurde (UTC).</span><span class="sxs-lookup"><span data-stu-id="5fea0-125">The date that the notice was issued (UTC).</span></span>              |