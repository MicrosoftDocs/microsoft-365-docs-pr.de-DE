---
title: Insider Risk Management-Benutzer (Vorschau)
description: Erfahren Sie mehr über Insider Risk Management-Benutzer in Microsoft 365
keywords: Microsoft 365, Insider-Risikomanagement, Risikomanagement, Compliance
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: f79fcebf220f1aee98ba97c537ff80b65b6e3881
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41582854"
---
# <a name="insider-risk-management-users-preview"></a><span data-ttu-id="9d775-104">Insider Risk Management-Benutzer (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="9d775-104">Insider risk management users (preview)</span></span>

<span data-ttu-id="9d775-105">Insider Risk Management-Benutzer sind Mitarbeiter in Ihrer Organisation, die in einem oder mehreren Richtlinien für das Insider Risikomanagement enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="9d775-105">Insider risk management users are employees in your organization that are included in one or more insider risk management policies.</span></span> <span data-ttu-id="9d775-106">Verwenden Sie das **benutzerdashboard** , um Risikoinformationen zu Mitarbeitern schnell zu überprüfen und einen Mitarbeiter zu einer vorhandenen Richtlinie für Insider Risikomanagement hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9d775-106">Use the **Users dashboard** to quickly review risk information about employees and to add an employee to an existing insider risk management policy.</span></span> <span data-ttu-id="9d775-107">Für jeden Benutzer, der in eine Richtlinie für das Insider Risikomanagement eingeschlossen ist, werden im **benutzerdashboard**folgende Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="9d775-107">Each user included in an insider risk management policy has the following information displayed on the **Users dashboard**:</span></span>

- <span data-ttu-id="9d775-108">**Users**: der Benutzername für einen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="9d775-108">**Users**: The user name for a user.</span></span>
- <span data-ttu-id="9d775-109">**Risikostufe**:</span><span class="sxs-lookup"><span data-stu-id="9d775-109">**Risk level**:</span></span> 
- <span data-ttu-id="9d775-110">**Aktive Warnungen**: die Anzahl der aktiven Warnungen für alle Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="9d775-110">**Active alerts**: The number of active alerts for all policies.</span></span>
- <span data-ttu-id="9d775-111">**Bestätigte Verstöße**: die Anzahl der Fälle, die als *bestätigte Richtlinienverletzung* für den Benutzer aufgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="9d775-111">**Confirmed violations**: The number of cases resolved as *confirmed policy violation* for the user.</span></span>
- <span data-ttu-id="9d775-112">**Case**: der aktuell aktive Fall für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="9d775-112">**Case**: The current active case for the user.</span></span>

![Benutzerdashboard für das Insider Risikomanagement](media/insider-risk-users-dashboard.png)

## <a name="view-user-details"></a><span data-ttu-id="9d775-114">Anzeigen von Benutzer Details</span><span class="sxs-lookup"><span data-stu-id="9d775-114">View user details</span></span>

<span data-ttu-id="9d775-115">Wenn Sie weitere Details zur Risiko Aktivität für einen Benutzer anzeigen möchten, öffnen Sie den Bereich Benutzer Details, indem Sie auf einen Benutzer im **Dashboard Benutzer**doppelklicken.</span><span class="sxs-lookup"><span data-stu-id="9d775-115">To view more details about risk activity for a user, open the user details pane by double-clicking a user in the **Users dashboard**.</span></span> <span data-ttu-id="9d775-116">Im Detailbereich können Sie die folgenden Informationen anzeigen:</span><span class="sxs-lookup"><span data-stu-id="9d775-116">On the details pane, you can view the following information:</span></span>

- <span data-ttu-id="9d775-117">Registerkarte ' **Benutzerprofil** '</span><span class="sxs-lookup"><span data-stu-id="9d775-117">**User profile** tab</span></span>
    - <span data-ttu-id="9d775-118">**Name und Title**: der Name und der Position-Titel für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="9d775-118">**Name and title**: The name and position title for the user.</span></span>
    - <span data-ttu-id="9d775-119">**Benutzer-e-Mail**: die e-Mail-Adresse für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="9d775-119">**User email**: The email address for the user.</span></span>
    - <span data-ttu-id="9d775-120">**Alias**: der Netzwerk Alias für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="9d775-120">**Alias**: The network alias for the user.</span></span>
    - <span data-ttu-id="9d775-121">**Organisation oder Abteilung**: die Organisation oder Abteilung für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="9d775-121">**Organization or department**: The organization or department for the user.</span></span>

- <span data-ttu-id="9d775-122">Registerkarte " **Benutzeraktivität** "</span><span class="sxs-lookup"><span data-stu-id="9d775-122">**User activity** tab</span></span>
    - <span data-ttu-id="9d775-123">**Verlauf der letzten Benutzeraktivität**: listet sowohl Richtlinien auslösende Ereignisse als auch Risikoindikatoren für Benutzeraktivitäten auf.</span><span class="sxs-lookup"><span data-stu-id="9d775-123">**History of recent user activity**: Lists both policy triggering events and risk indicators for user activities.</span></span> <span data-ttu-id="9d775-124">Ein auslösendes Ereignis kann die Annahme eines Rücktritts Datums oder des letzten geplanten Arbeitsdatums für den Mitarbeiter sein.</span><span class="sxs-lookup"><span data-stu-id="9d775-124">A triggering event may be the acceptance of a resignation date or the last scheduled date of work for the employee.</span></span> <span data-ttu-id="9d775-125">Risikoindikatoren sind Aktivitäten, die für ein Element des Risikos bestimmt sind und mit Richtlinien abgeglichen werden, in denen der Benutzer enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="9d775-125">Risk indicators are activities that are determined to have an element of risk and that are matched to policies that the user is included in.</span></span> <span data-ttu-id="9d775-126">Ereignisse und Risiko Aktivitäten werden mit dem letzten Element aufgeführt, das zuerst aufgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9d775-126">Events and risk activities are listed with the most recent item listed first.</span></span>

## <a name="add-a-user-to-a-policy"></a><span data-ttu-id="9d775-127">Hinzufügen eines Benutzers zu einer Richtlinie</span><span class="sxs-lookup"><span data-stu-id="9d775-127">Add a user to a policy</span></span>

<span data-ttu-id="9d775-128">Zum Hinzufügen eines Benutzers zu einer Richtlinie für Insider Risiken verwenden Sie entweder den Assistenten für neue Richtlinien oder die Registerkarte **Benutzer** in der Lösung für das **Insider Risikomanagement** im Microsoft 365 Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="9d775-128">To add a user to an insider risk management policy, you'll either use the new policy wizard or the **Users** tab in the **Insider risk management** solution in the Microsoft 365 compliance center.</span></span>

<span data-ttu-id="9d775-129">Führen Sie die folgenden Schritte aus, um einen Benutzer zu einer vorhandenen Insider Risiko Richtlinie hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="9d775-129">Complete the following steps to add a user to an existing insider risk policy:</span></span>

1. <span data-ttu-id="9d775-130">Wechseln Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu **Insider Risk Management** , und wählen Sie die Registerkarte **Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="9d775-130">In the [Microsoft 365 compliance center](https://compliance.microsoft.com), go to **Insider risk management** and select the **Users** tab.</span></span>
2. <span data-ttu-id="9d775-131">Wählen Sie auf der Symbolleiste **einen Benutzer zu einer Richtlinie hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="9d775-131">Select **Add a user to a policy** on the toolbar.</span></span>
3. <span data-ttu-id="9d775-132">Beginnen Sie im Dialogfeld **neuen Benutzer hinzufügen** mit der Eingabe eines Benutzernamens in das Feld **Benutzer** .</span><span class="sxs-lookup"><span data-stu-id="9d775-132">On the **Add a new user** dialog, start typing a user name in the **User** field.</span></span> <span data-ttu-id="9d775-133">Wählen Sie den Benutzer aus, den Sie einer Richtlinie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="9d775-133">Select the user you want to add to a policy.</span></span>
4. <span data-ttu-id="9d775-134">Wählen Sie den Dropdownpfeil für das Feld **Richtlinie** aus, um konfigurierte Richtlinien für die Verwaltung von Insider Risiken anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9d775-134">Select the dropdown arrow for the **Policy** field to display configured insider risk management policies.</span></span> <span data-ttu-id="9d775-135">Wählen Sie die Richtlinie aus, der der Benutzer hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9d775-135">Select the policy to add the user to.</span></span>
5. <span data-ttu-id="9d775-136">Definieren Sie mit dem Slider-Steuerelement des **Überwachungsfensters** die...... Der Bereich für das Überwachungsfenster beträgt 5 bis 30 Tage.</span><span class="sxs-lookup"><span data-stu-id="9d775-136">Use the **Monitoring window** slider control to define the...... The range for the monitoring window is 5 to 30 days.</span></span>
6. <span data-ttu-id="9d775-137">Wählen Sie **Hinzufügen** und **bestätigen** Sie dann, um den Benutzer zur Richtlinie hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9d775-137">Select **Add** and then **Confirm** to add the user to the policy.</span></span>
