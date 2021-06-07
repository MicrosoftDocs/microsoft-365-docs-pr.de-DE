---
title: Microsoft Defender für Endpunkt Flow Connector
ms.reviewer: ''
description: Verwenden Sie Microsoft Defender für Endpunkt Flow Connector, um die Sicherheit zu automatisieren und einen Fluss zu erstellen, der jedes Mal ausgelöst wird, wenn eine neue Warnung auf Ihrem Mandanten auftritt.
keywords: Flow, unterstützte APIs, API, Microsoft-Fluss, Abfrage, Automatisierung
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: dd0cc3c2da134750f905b1f80746d6ec65cc70b2
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769703"
---
# <a name="microsoft-power-automate-formerly-microsoft-flow-and-azure-functions"></a><span data-ttu-id="c4615-104">Microsoft Power Automate (früher Microsoft Flow) und Azure-Funktionen</span><span class="sxs-lookup"><span data-stu-id="c4615-104">Microsoft Power Automate (formerly Microsoft Flow), and Azure Functions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c4615-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c4615-105">**Applies to:**</span></span>
- [<span data-ttu-id="c4615-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="c4615-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c4615-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c4615-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="c4615-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="c4615-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c4615-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="c4615-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="c4615-110">Die Automatisierung von Sicherheitsverfahren ist eine Standardanforderung für jedes moderne Security Operations Center.</span><span class="sxs-lookup"><span data-stu-id="c4615-110">Automating security procedures is a standard requirement for every modern Security Operations Center.</span></span> <span data-ttu-id="c4615-111">Der Mangel an professionellen Cyber defendern zwingt SOC, auf die effizienteste Weise zu arbeiten, und Automatisierung ist ein Muss.</span><span class="sxs-lookup"><span data-stu-id="c4615-111">The lack of professional cyber defenders forces SOC to work in the most efficient way and automation is a must.</span></span> <span data-ttu-id="c4615-112">Microsoft Power Automate unterstützt verschiedene Connectors, die genau dafür erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="c4615-112">Microsoft Power Automate supports different connectors that were built exactly for that.</span></span> <span data-ttu-id="c4615-113">Sie können innerhalb weniger Minuten eine End-to-End-Prozedurautomatisierung erstellen.</span><span class="sxs-lookup"><span data-stu-id="c4615-113">You can build an end-to-end procedure automation within a few minutes.</span></span>

<span data-ttu-id="c4615-114">Die Microsoft Defender-API verfügt über einen offiziellen Flow Connector mit vielen Funktionen.</span><span class="sxs-lookup"><span data-stu-id="c4615-114">Microsoft Defender API has an official Flow Connector with many capabilities.</span></span>

![Abbildung der Anmeldeinformationen bearbeiten1](images/api-flow-0.png)

> [!NOTE]
> <span data-ttu-id="c4615-116">Weitere Informationen zu den Voraussetzungen für die Lizenzierung von Premium-Connectors finden Sie unter ["Lizenzierung für Premium-Connectors".](https://docs.microsoft.com/power-automate/triggers-introduction#licensing-for-premium-connectors)</span><span class="sxs-lookup"><span data-stu-id="c4615-116">For more details about premium connectors licensing prerequisites, see [Licensing for premium connectors](https://docs.microsoft.com/power-automate/triggers-introduction#licensing-for-premium-connectors).</span></span>


## <a name="usage-example"></a><span data-ttu-id="c4615-117">Verwendungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="c4615-117">Usage example</span></span>

<span data-ttu-id="c4615-118">Im folgenden Beispiel wird veranschaulicht, wie Sie ein Flow erstellen, das jedes Mal ausgelöst wird, wenn eine neue Warnung auf Ihrem Mandanten auftritt.</span><span class="sxs-lookup"><span data-stu-id="c4615-118">The following example demonstrates how to create a Flow that is triggered any time a new Alert occurs on your tenant.</span></span>

1. <span data-ttu-id="c4615-119">Melden Sie sich bei [Microsoft Power Automate](https://flow.microsoft.com)an.</span><span class="sxs-lookup"><span data-stu-id="c4615-119">Log in to [Microsoft Power Automate](https://flow.microsoft.com).</span></span>

2. <span data-ttu-id="c4615-120">Wechseln Sie zu **"My flows**  >  **New**  >  **Automated-from blank".**</span><span class="sxs-lookup"><span data-stu-id="c4615-120">Go to **My flows** > **New** > **Automated-from blank**.</span></span>

    ![Abbildung der Anmeldeinformationen bearbeiten2](images/api-flow-1.png)

3. <span data-ttu-id="c4615-122">Wählen Sie einen Namen für Ihre Flow aus, suchen Sie nach "Microsoft Defender ATP Triggers" als Auslöser, und wählen Sie dann den neuen Trigger "Alerts" aus.</span><span class="sxs-lookup"><span data-stu-id="c4615-122">Choose a name for your Flow, search for "Microsoft Defender ATP Triggers" as the trigger, and then select the new Alerts trigger.</span></span>

    ![Abbildung der Anmeldeinformationen bearbeiten3](images/api-flow-2.png)

<span data-ttu-id="c4615-124">Jetzt haben Sie eine Flow, die jedes Mal ausgelöst wird, wenn eine neue Warnung auftritt.</span><span class="sxs-lookup"><span data-stu-id="c4615-124">Now you have a Flow that is triggered every time a new Alert occurs.</span></span>

![Abbildung der Anmeldeinformationen bearbeiten4](images/api-flow-3.png)

<span data-ttu-id="c4615-126">Sie müssen nur noch die nächsten Schritte auswählen.</span><span class="sxs-lookup"><span data-stu-id="c4615-126">All you need to do now is choose your next steps.</span></span>
<span data-ttu-id="c4615-127">Sie können das Gerät beispielsweise isolieren, wenn der Schweregrad der Warnung hoch ist, und eine E-Mail darüber senden.</span><span class="sxs-lookup"><span data-stu-id="c4615-127">For example, you can isolate the device if the Severity of the Alert is High and send an email about it.</span></span>
<span data-ttu-id="c4615-128">Der Warnungsauslöser stellt nur die Warnungs-ID und die Computer-ID bereit.</span><span class="sxs-lookup"><span data-stu-id="c4615-128">The Alert trigger provides only the Alert ID and the Machine ID.</span></span> <span data-ttu-id="c4615-129">Sie können den Connector verwenden, um diese Entitäten zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="c4615-129">You can use the connector to expand these entities.</span></span>

### <a name="get-the-alert-entity-using-the-connector"></a><span data-ttu-id="c4615-130">Abrufen der Warnungsentität mithilfe des Connectors</span><span class="sxs-lookup"><span data-stu-id="c4615-130">Get the Alert entity using the connector</span></span>

1. <span data-ttu-id="c4615-131">Wählen Sie **Microsoft Defender ATP** für den neuen Schritt aus.</span><span class="sxs-lookup"><span data-stu-id="c4615-131">Choose **Microsoft Defender ATP** for the new step.</span></span>

2. <span data-ttu-id="c4615-132">Wählen Sie **Warnungen aus – Rufen Sie die api für einzelne Warnungen** ab.</span><span class="sxs-lookup"><span data-stu-id="c4615-132">Choose **Alerts - Get single alert API**.</span></span>

3. <span data-ttu-id="c4615-133">Legen Sie die **Warnungs-ID** aus dem letzten Schritt als **Eingabe** fest.</span><span class="sxs-lookup"><span data-stu-id="c4615-133">Set the **Alert ID** from the last step as **Input**.</span></span>

    ![Abbildung der Anmeldeinformationen bearbeiten5](images/api-flow-4.png)

### <a name="isolate-the-device-if-the-alerts-severity-is-high"></a><span data-ttu-id="c4615-135">Isolieren des Geräts, wenn der Schweregrad der Warnung hoch ist</span><span class="sxs-lookup"><span data-stu-id="c4615-135">Isolate the device if the Alert's severity is High</span></span>

1. <span data-ttu-id="c4615-136">Fügen Sie **"Bedingung"** als neuen Schritt hinzu.</span><span class="sxs-lookup"><span data-stu-id="c4615-136">Add **Condition** as a new step.</span></span>

2. <span data-ttu-id="c4615-137">Überprüfen Sie, ob der Schweregrad der Warnung **"Hoch" ist.**</span><span class="sxs-lookup"><span data-stu-id="c4615-137">Check if the Alert severity **is equal to** High.</span></span>

   <span data-ttu-id="c4615-138">Wenn ja, fügen Sie die **Microsoft Defender ATP – Computeraktion isolieren** mit der Computer-ID und einem Kommentar hinzu.</span><span class="sxs-lookup"><span data-stu-id="c4615-138">If yes, add the **Microsoft Defender ATP - Isolate machine** action with the Machine ID and a comment.</span></span>

    ![Abbildung der Anmeldeinformationen bearbeiten6](images/api-flow-5.png)

3. <span data-ttu-id="c4615-140">Fügen Sie einen neuen Schritt für die E-Mail-Nachricht über die Warnung und die Isolation hinzu.</span><span class="sxs-lookup"><span data-stu-id="c4615-140">Add a new step for emailing about the Alert and the Isolation.</span></span> <span data-ttu-id="c4615-141">Es gibt mehrere E-Mail-Connectors, die sehr einfach zu verwenden sind, z. B. Outlook oder Gmail.</span><span class="sxs-lookup"><span data-stu-id="c4615-141">There are multiple email connectors that are very easy to use, such as Outlook or Gmail.</span></span>

4. <span data-ttu-id="c4615-142">Speichern Sie Ihren Flow.</span><span class="sxs-lookup"><span data-stu-id="c4615-142">Save your flow.</span></span>

<span data-ttu-id="c4615-143">Sie können auch einen **geplanten** Fluss erstellen, der Abfragen der erweiterten Suche ausführt und vieles mehr!</span><span class="sxs-lookup"><span data-stu-id="c4615-143">You can also create a **scheduled** flow that runs Advanced Hunting queries and much more!</span></span>

## <a name="related-topic"></a><span data-ttu-id="c4615-144">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="c4615-144">Related topic</span></span>
- [<span data-ttu-id="c4615-145">Microsoft Defender für Endpunkt-APIs</span><span class="sxs-lookup"><span data-stu-id="c4615-145">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
