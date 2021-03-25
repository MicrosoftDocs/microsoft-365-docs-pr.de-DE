---
title: Anzeigen und Verwalten von benutzerdefinierten Erkennungsregeln in Microsoft Defender ATP
ms.reviewer: ''
description: Informationen zum Anzeigen und Verwalten von benutzerdefinierten Erkennungsregeln
keywords: Benutzerdefinierte Erkennungen, Anzeigen, Verwalten, Warnungen, Bearbeiten, Ausführen bei Bedarf, Erkennungsregeln, erweiterte Suche, Suche, Abfrage, Reaktionsaktionen, mdatp, microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f6a7fc4d4141b19f9c5129eea9b89943d07695b2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165777"
---
# <a name="view-and-manage-custom-detection-rules"></a><span data-ttu-id="b3815-104">Anzeigen und Verwalten von benutzerdefinierten Erkennungsregeln</span><span class="sxs-lookup"><span data-stu-id="b3815-104">View and manage custom detection rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b3815-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b3815-105">**Applies to:**</span></span>
- [<span data-ttu-id="b3815-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b3815-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b3815-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b3815-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="b3815-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="b3815-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b3815-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="b3815-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="b3815-110">Verwalten Sie Ihre [vorhandenen benutzerdefinierten Erkennungsregeln,](custom-detection-rules.md) um sicherzustellen, dass sie Bedrohungen effektiv finden und Aktionen ergreifen.</span><span class="sxs-lookup"><span data-stu-id="b3815-110">Manage your existing [custom detection rules](custom-detection-rules.md) to ensure they are effectively finding threats and taking actions.</span></span> <span data-ttu-id="b3815-111">Erfahren Sie, wie Sie die Liste der Regeln anzeigen, ihre vorherigen Läufe überprüfen und die ausgelösten Warnungen überprüfen.</span><span class="sxs-lookup"><span data-stu-id="b3815-111">Explore how to view the list of rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="b3815-112">Sie können auch eine Regel bei Bedarf ausführen und ändern.</span><span class="sxs-lookup"><span data-stu-id="b3815-112">You can also run a rule on demand and modify it.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="b3815-113">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="b3815-113">Required permissions</span></span>

<span data-ttu-id="b3815-114">Zum Erstellen oder Verwalten von benutzerdefinierten Erkennungen muss [Ihre Rolle](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) über die Berechtigung zum Verwalten **von Sicherheitseinstellungen** verfügen.</span><span class="sxs-lookup"><span data-stu-id="b3815-114">To create or manage custom detections, [your role](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) needs to have the **manage security settings** permission.</span></span>

## <a name="view-existing-rules"></a><span data-ttu-id="b3815-115">Anzeigen vorhandener Regeln</span><span class="sxs-lookup"><span data-stu-id="b3815-115">View existing rules</span></span>

<span data-ttu-id="b3815-116">Navigieren Sie zum Anzeigen aller vorhandenen benutzerdefinierten Erkennungsregeln zu **Einstellungen**  >  **Benutzerdefinierte Erkennungen**.</span><span class="sxs-lookup"><span data-stu-id="b3815-116">To view all existing custom detection rules, navigate to **Settings** > **Custom detections**.</span></span> <span data-ttu-id="b3815-117">Auf der Seite sind alle Regeln mit den folgenden Ausführungsinformationen aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="b3815-117">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="b3815-118">**Letzte Ausführung**– bei der letzten Ausführung einer Regel zum Überprüfen von Abfrage übereinstimmungen und Generieren von Warnungen</span><span class="sxs-lookup"><span data-stu-id="b3815-118">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="b3815-119">**Status der letzten Ausführung**– gibt an, ob eine Regel erfolgreich ausgeführt wurde</span><span class="sxs-lookup"><span data-stu-id="b3815-119">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="b3815-120">**Nächste Ausführung**– die nächste geplante Ausführung</span><span class="sxs-lookup"><span data-stu-id="b3815-120">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="b3815-121">**Status –** gibt an, ob eine Regel aktiviert oder deaktiviert wurde</span><span class="sxs-lookup"><span data-stu-id="b3815-121">**Status**—whether a rule has been turned on or off</span></span>

## <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="b3815-122">Anzeigen von Regeldetails, Ändern der Regel und Ausführen der Regel</span><span class="sxs-lookup"><span data-stu-id="b3815-122">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="b3815-123">Wenn Sie umfassende Informationen zu einer benutzerdefinierten Erkennungsregel anzeigen möchten, wählen Sie in der Liste der Regeln unter **Einstellungen** Benutzerdefinierte Erkennungen den Namen  >  **der Regel aus.**</span><span class="sxs-lookup"><span data-stu-id="b3815-123">To view comprehensive information about a custom detection rule, select the name of rule from the list of rules in **Settings** > **Custom detections**.</span></span> <span data-ttu-id="b3815-124">Eine Seite über die ausgewählte Regel zeigt die folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="b3815-124">A page about the selected rule displays the following information:</span></span>

- <span data-ttu-id="b3815-125">Allgemeine Informationen zur Regel, einschließlich der Details der Warnung, des Ausführungsstatus und des Gültigkeitsbereichs</span><span class="sxs-lookup"><span data-stu-id="b3815-125">General information about the rule, including the details of the alert, run status, and scope</span></span>
- <span data-ttu-id="b3815-126">Liste der ausgelösten Warnungen</span><span class="sxs-lookup"><span data-stu-id="b3815-126">List of triggered alerts</span></span>
- <span data-ttu-id="b3815-127">Liste der ausgelösten Aktionen</span><span class="sxs-lookup"><span data-stu-id="b3815-127">List of triggered actions</span></span>

<span data-ttu-id="b3815-128">![Benutzerdefinierte Erkennungsregelseite](images/atp-custom-detection-rule-details.png)</span><span class="sxs-lookup"><span data-stu-id="b3815-128">![Custom detection rule page](images/atp-custom-detection-rule-details.png)</span></span><br>
<span data-ttu-id="b3815-129">*Benutzerdefinierte Erkennungsregelseite*</span><span class="sxs-lookup"><span data-stu-id="b3815-129">*Custom detection rule page*</span></span>

<span data-ttu-id="b3815-130">Sie können auf dieser Seite auch die folgenden Aktionen für die Regel ausführen:</span><span class="sxs-lookup"><span data-stu-id="b3815-130">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="b3815-131">**Ausführen**– Führen Sie die Regel sofort aus.</span><span class="sxs-lookup"><span data-stu-id="b3815-131">**Run**—run the rule immediately.</span></span> <span data-ttu-id="b3815-132">Mit dieser Aktion wird auch das Intervall für die nächste Ausführung zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="b3815-132">This action also resets the interval for the next run.</span></span>
- <span data-ttu-id="b3815-133">**Bearbeiten**– Ändern der Regel, ohne die Abfrage zu ändern</span><span class="sxs-lookup"><span data-stu-id="b3815-133">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="b3815-134">**Abfrage ändern**– Bearbeiten der Abfrage bei der erweiterten Suche</span><span class="sxs-lookup"><span data-stu-id="b3815-134">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="b3815-135">**Aktivieren**  /  **Deaktivieren –** Aktivieren der Regel oder Beenden der Ausführung</span><span class="sxs-lookup"><span data-stu-id="b3815-135">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="b3815-136">**Löschen**– Deaktivieren der Regel und Entfernen der Regel</span><span class="sxs-lookup"><span data-stu-id="b3815-136">**Delete**—turn off the rule and remove it</span></span>

>[!TIP]
><span data-ttu-id="b3815-137">Verwenden Sie die Auswahlspalte [&#10003;] links neben der Tabelle, um Informationen schnell anzeigen und Aktionen für ein Element in einer Tabelle ergreifen zu können.</span><span class="sxs-lookup"><span data-stu-id="b3815-137">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b3815-138">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b3815-138">Related topics</span></span>
- [<span data-ttu-id="b3815-139">Benutzerdefinierte Erkennungen – Übersicht</span><span class="sxs-lookup"><span data-stu-id="b3815-139">Custom detections overview</span></span>](overview-custom-detections.md)
- [<span data-ttu-id="b3815-140">Erstellen von Erkennungsregeln</span><span class="sxs-lookup"><span data-stu-id="b3815-140">Create detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="b3815-141">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="b3815-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="b3815-142">Anzeigen und Organisieren von Warnungen</span><span class="sxs-lookup"><span data-stu-id="b3815-142">View and organize alerts</span></span>](alerts-queue.md)
