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
description: Verwenden Sie den Kommunikations-Editor, um Text zu ändern und Feldvariablen zusammenzuführen, wenn Sie Ihre Inhalte formatieren.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 26076ff82ba226c2993c7c40e36bca2e08cbf683
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288119"
---
# <a name="use-the-communications-editor"></a><span data-ttu-id="3099e-103">Verwenden des Kommunikations-Editors</span><span class="sxs-lookup"><span data-stu-id="3099e-103">Use the communications editor</span></span>

<span data-ttu-id="3099e-104">Wenn Sie die Inhalte Ihrer Portalinhalte, Benachrichtigungen über gesetzliche Aufbewahrungspflicht und zugehörige Erinnerungen/Eskalationen definieren, können Sie den Kommunikations-Editor verwenden, um Ihre Inhalte zu formatieren und dynamisch anzupassen.</span><span class="sxs-lookup"><span data-stu-id="3099e-104">As you define the content of your portal content, legal hold notifications, and related reminders/escalations, you can use the Communications Editor to format and dynamically customize your content.</span></span>

## <a name="rich-text-editor"></a><span data-ttu-id="3099e-105">Rich-Text-Editor</span><span class="sxs-lookup"><span data-stu-id="3099e-105">Rich text editor</span></span>

<span data-ttu-id="3099e-106">Mit dem Kommunikations-Editor können Benutzer den Text mithilfe der Editoroptionen anpassen.</span><span class="sxs-lookup"><span data-stu-id="3099e-106">The Communications Editor allows user to customize the text using the editor options.</span></span> <span data-ttu-id="3099e-107">Beispielsweise können Benutzer Schriftartentypen ändern, Aufzählungen erstellen, Inhalte hervorheben und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="3099e-107">For example, users can change font types, create bulleted lists, highlight content, and more.</span></span>

## <a name="merge-field-variables"></a><span data-ttu-id="3099e-108">Zusammenführen von Feldvariablen</span><span class="sxs-lookup"><span data-stu-id="3099e-108">Merge field variables</span></span>

<span data-ttu-id="3099e-109">Sie können E-Mail-Seriendruckvariablen aus dem Kommunikations-Editor verwenden, um angepasste Verwahrerattribute in den Textkörper einer Kommunikation einzubetten.</span><span class="sxs-lookup"><span data-stu-id="3099e-109">You can use email merge variables from the Communications Editor to embed customized custodian attributes into a communication's body text.</span></span> <span data-ttu-id="3099e-110">Wenn es an den Verwahrer gesendet wird, wird das Seriendruckfeld mit dem entsprechenden Feld aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="3099e-110">When sent to the custodian, the merge field will be populated with the corresponding field.</span></span> <span data-ttu-id="3099e-111">Wenn sie beispielsweise an den Verwalter John Smith gesendet werden, wird das Seriendruckfeld [Verwahrername] mit dem entsprechenden Namen übersetzt.</span><span class="sxs-lookup"><span data-stu-id="3099e-111">For example, when sent to custodian John Smith, the merge field [Custodian Name] would be translated with the corresponding name.</span></span>

<span data-ttu-id="3099e-112">Sie können Seriendruckfelder verwenden, indem Sie die **Seriendruckfeldsymbole** oben im Rich-Text-Editor-Steuerelement auswählen.</span><span class="sxs-lookup"><span data-stu-id="3099e-112">You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control.</span></span> <span data-ttu-id="3099e-113">Der Platzhalter wird basierend auf der Position des Cursors des Benutzers hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3099e-113">The placeholder will be added based off the location of the users' cursor.</span></span>

### <a name="list-of-merge-field-variables"></a><span data-ttu-id="3099e-114">Liste der Zusammenführungsfeldvariablen</span><span class="sxs-lookup"><span data-stu-id="3099e-114">List of merge field variables</span></span>

<br>

****

|<span data-ttu-id="3099e-115">Feldname</span><span class="sxs-lookup"><span data-stu-id="3099e-115">Field name</span></span>|<span data-ttu-id="3099e-116">Felddetails</span><span class="sxs-lookup"><span data-stu-id="3099e-116">Field details</span></span>|
|---|---|
|<span data-ttu-id="3099e-117">Anzeigename</span><span class="sxs-lookup"><span data-stu-id="3099e-117">Display Name</span></span>|<span data-ttu-id="3099e-118">Vor- und Nachname des Verwalters.</span><span class="sxs-lookup"><span data-stu-id="3099e-118">The custodian's first and last name.</span></span>|
|<span data-ttu-id="3099e-119">Bestätigungslink</span><span class="sxs-lookup"><span data-stu-id="3099e-119">Acknowledgment Link</span></span>|<span data-ttu-id="3099e-120">Ein angepasster Link zum Aufzeichnen der Bestätigung jedes Verwahrers.</span><span class="sxs-lookup"><span data-stu-id="3099e-120">A customized link to record each custodian's acknowledgment.</span></span>|
|<span data-ttu-id="3099e-121">Portallink</span><span class="sxs-lookup"><span data-stu-id="3099e-121">Portal Link</span></span>|<span data-ttu-id="3099e-122">Ein angepasster Link für das Compliance-Portal des Verwalters.</span><span class="sxs-lookup"><span data-stu-id="3099e-122">A customized link for the custodian's Compliance Portal.</span></span>|
|<span data-ttu-id="3099e-123">Ausstellende Beauftragte</span><span class="sxs-lookup"><span data-stu-id="3099e-123">Issuing Officer</span></span>|<span data-ttu-id="3099e-124">Die E-Mail-Adresse des angegebenen Ausstellenden Beauftragten.</span><span class="sxs-lookup"><span data-stu-id="3099e-124">The email address of the specified issuing officer.</span></span>|
|<span data-ttu-id="3099e-125">Ausgabedatum</span><span class="sxs-lookup"><span data-stu-id="3099e-125">Issuing Date</span></span>|<span data-ttu-id="3099e-126">Das Datum, an dem die Benachrichtigung ausgegeben wurde (UTC).</span><span class="sxs-lookup"><span data-stu-id="3099e-126">The date that the notice was issued (UTC).</span></span>|
|
