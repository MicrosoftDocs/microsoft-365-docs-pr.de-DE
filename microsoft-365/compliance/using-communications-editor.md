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
description: ''
ms.openlocfilehash: 4b98f02a45809d034795792a1078f02bc7fc1d7d
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597272"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="98f84-102">Verwenden des Kommunikations-Editors</span><span class="sxs-lookup"><span data-stu-id="98f84-102">Use the communications editor</span></span>

<span data-ttu-id="98f84-103">Wenn Sie den Inhalt Ihrer Portalinhalte, Benachrichtigungen über rechtliche Aufbewahrungszeit und zugehörige Erinnerungen/Eskalationen definieren, können Sie den Kommunikations-Editor nutzen, um Ihre Inhalte zu formatieren und dynamisch anzupassen.</span><span class="sxs-lookup"><span data-stu-id="98f84-103">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can leverage the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="98f84-104">Rich-Text-Editor</span><span class="sxs-lookup"><span data-stu-id="98f84-104">Rich text editor</span></span> 

<span data-ttu-id="98f84-105">Mit dem Kommunikations-Editor können Benutzer den Text mithilfe der Editor-Optionen anpassen.</span><span class="sxs-lookup"><span data-stu-id="98f84-105">The Communications Editor allows user to customize the text using the editor options.</span></span> <span data-ttu-id="98f84-106">Beispielsweise können Benutzer Schriftarttypen ändern, Aufzählungslisten erstellen, Inhalte hervorheben und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="98f84-106">For example, users can change font types, create bulleted lists, highlight content, and more.</span></span> 

## <a name="merge-field-variables"></a><span data-ttu-id="98f84-107">Zusammenführen von Feld Variablen</span><span class="sxs-lookup"><span data-stu-id="98f84-107">Merge field variables</span></span>

<span data-ttu-id="98f84-108">Sie können e-Mail-Zusammenführungs Variablen aus dem Kommunikations-Editor nutzen, um angepasste Depot Attribute in den Textkörper einer Kommunikation einzubetten.</span><span class="sxs-lookup"><span data-stu-id="98f84-108">You can leverage email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text.</span></span> <span data-ttu-id="98f84-109">Beim Senden an die Depotbank wird das Seriendruckfeld mit dem entsprechenden Feld aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="98f84-109">When sent to the custodian, the merge field will be populated with the corresponding field.</span></span> <span data-ttu-id="98f84-110">Wenn beispielsweise an den Depotbank John Smith gesendet wird, würde das Seriendruckfeld [Depot Name] mit dem entsprechenden Namen übersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="98f84-110">For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span> 

<span data-ttu-id="98f84-111">Sie können Seriendruckfelder verwenden, indem Sie die **Seriendruckfeld** Symbole oben im Rich-Text-Editor-Steuerelement auswählen.</span><span class="sxs-lookup"><span data-stu-id="98f84-111">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span></span> <span data-ttu-id="98f84-112">Der Platzhalter wird basierend auf dem Speicherort des Cursors der Benutzer hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="98f84-112">The placeholder will be added based off the location of the users' cursor.</span></span> 

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="98f84-113">Liste der Seriendruckfeld Variablen</span><span class="sxs-lookup"><span data-stu-id="98f84-113">List of merge field variables</span></span>

| <span data-ttu-id="98f84-114">Feldname</span><span class="sxs-lookup"><span data-stu-id="98f84-114">Field name</span></span>                  | <span data-ttu-id="98f84-115">Feld Details</span><span class="sxs-lookup"><span data-stu-id="98f84-115">Field details</span></span> | 
| :------------------- | :------------------- |
| <span data-ttu-id="98f84-116">Anzeigename</span><span class="sxs-lookup"><span data-stu-id="98f84-116">Display Name</span></span>  | <span data-ttu-id="98f84-117">Der vor-und Nachname des Depotbank.</span><span class="sxs-lookup"><span data-stu-id="98f84-117">The custodian's first and last name.</span></span> | 
| <span data-ttu-id="98f84-118">Bestätigungs Link</span><span class="sxs-lookup"><span data-stu-id="98f84-118">Acknowledgement Link</span></span> | <span data-ttu-id="98f84-119">Ein benutzerdefinierter Link zum Aufzeichnen der Bestätigung jedes Verwalters.</span><span class="sxs-lookup"><span data-stu-id="98f84-119">A customized link to record each custodian's acknowledgement.</span></span>|                 |
| <span data-ttu-id="98f84-120">Portal Link</span><span class="sxs-lookup"><span data-stu-id="98f84-120">Portal Link</span></span>     | <span data-ttu-id="98f84-121">Ein benutzerdefinierter Link für das Compliance-Portal des Depotbank.</span><span class="sxs-lookup"><span data-stu-id="98f84-121">A customized link for the custodian's Compliance Portal.</span></span>|                |
| <span data-ttu-id="98f84-122">Ausstellenden Offizier</span><span class="sxs-lookup"><span data-stu-id="98f84-122">Issuing Officer</span></span>                   | <span data-ttu-id="98f84-123">Die e-Mail-Adresse des angegebenen ausstellenden Offiziers.</span><span class="sxs-lookup"><span data-stu-id="98f84-123">The email address of the specified issuing officer.</span></span>|                   |
| <span data-ttu-id="98f84-124">Ausstellendes Datum</span><span class="sxs-lookup"><span data-stu-id="98f84-124">Issuing Date</span></span>                   | <span data-ttu-id="98f84-125">Das Datum, an dem der Hinweis ausgegeben wurde (UTC).</span><span class="sxs-lookup"><span data-stu-id="98f84-125">The date that the notice was issued (UTC).</span></span>              |