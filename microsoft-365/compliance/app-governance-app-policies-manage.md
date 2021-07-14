---
title: Verwalten von App-Richtlinien
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Verwalten Ihrer App-Governancerichtlinien.
ms.openlocfilehash: 756402f86d6b65d48afb02c49b3e5bfc4e73fe3d
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420208"
---
# <a name="manage-app-policies"></a><span data-ttu-id="f4735-103">Verwalten von App-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="f4735-103">Manage app policies</span></span>

><span data-ttu-id="f4735-104">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="f4735-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="f4735-105">Um mit den neuesten Apps, die Ihr Unternehmen verwendet, Schritt zu halten, auf neue App-basierte Angriffe zu reagieren und die laufenden Änderungen an Ihren App-Complianceanforderungen umzusetzen, müssen Sie Ihre App-Richtlinien möglicherweise auf diese Weise verwalten:</span><span class="sxs-lookup"><span data-stu-id="f4735-105">To keep up with the latest apps your organization is using, respond to new app-based attacks, and for ongoing changes to your app compliance needs, you might need to manage your app policies in these ways:</span></span>

- <span data-ttu-id="f4735-106">Erstellen neuer Richtlinien für neue Apps</span><span class="sxs-lookup"><span data-stu-id="f4735-106">Create new policies targeted at new apps</span></span>
- <span data-ttu-id="f4735-107">Ändern des Status einer vorhandenen Richtlinie (aktiv, inaktiv, Überwachungsmodus)</span><span class="sxs-lookup"><span data-stu-id="f4735-107">Change the status of an existing policy (active, inactive, audit mode)</span></span>
- <span data-ttu-id="f4735-108">Ändern der Bedingungen einer vorhandenen Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f4735-108">Change the conditions of an existing policy</span></span>
- <span data-ttu-id="f4735-109">Ändern der Aktionen einer vorhandenen Richtlinie für die automatische Korrektur bei Warnungen</span><span class="sxs-lookup"><span data-stu-id="f4735-109">Change the actions of an existing policy for auto-remediation of alerts</span></span>

<span data-ttu-id="f4735-110">Hier ist ein Beispiel für einen Prozess zum Verwalten einer vorhandenen Richtlinie:</span><span class="sxs-lookup"><span data-stu-id="f4735-110">Here's an example of a process for managing an existing policy:</span></span>

1. <span data-ttu-id="f4735-111">Bearbeiten der Richtlinie:</span><span class="sxs-lookup"><span data-stu-id="f4735-111">Edit the policy:</span></span>

  - <span data-ttu-id="f4735-112">Ändern Sie die Einstellungen der Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="f4735-112">Change the settings of the policy.</span></span>
  - <span data-ttu-id="f4735-113">Ändern Sie bei Bedarf den Status zum Testen in **Überwachungsmodus**.</span><span class="sxs-lookup"><span data-stu-id="f4735-113">If needed, change the status to **Audit mode** for testing.</span></span>

2. <span data-ttu-id="f4735-114">Überprüfen Sie auf erwartetes Verhalten, z. B. generierte Warnungen.</span><span class="sxs-lookup"><span data-stu-id="f4735-114">Check for expected behavior, such as alerts generated.</span></span>
1. <span data-ttu-id="f4735-115">Wenn das Verhalten nicht den Erwartungen entspricht, fahren Sie mit Schritt 1 fort.</span><span class="sxs-lookup"><span data-stu-id="f4735-115">If the behavior is not expected, go back to step 1.</span></span>
1. <span data-ttu-id="f4735-116">Wenn das Verhalten den Erwartungen entspricht, bearbeiten Sie die Richtlinie, und ändern Sie ihren Status ggf. in „Aktiv“.</span><span class="sxs-lookup"><span data-stu-id="f4735-116">If the behavior is expected, edit the policy and change its status to active (if needed).</span></span>

![Der Workflow zum Verwalten von App-Richtlinien](../media/manage-app-protection-governance/mapg-manage-policy-process.png)

## <a name="editing-an-app-policy-configuration"></a><span data-ttu-id="f4735-118">Bearbeiten einer App-Richtlinienkonfiguration</span><span class="sxs-lookup"><span data-stu-id="f4735-118">Editing an app policy configuration</span></span>

<span data-ttu-id="f4735-119">So ändern Sie die Konfiguration einer vorhandenen App-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f4735-119">To change the configuration of an existing app policy:</span></span>

- <span data-ttu-id="f4735-120">Wählen Sie die Richtlinie in der Richtlinienliste und dann im Bereich „App-Richtlinie“ die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="f4735-120">Select the policy in the policy list, and then select **Edit** on the app policy pane.</span></span>
- <span data-ttu-id="f4735-121">Wählen Sie die vertikalen Auslassungspunkte für die Richtlinie in der Liste und dann **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="f4735-121">Select the vertical ellipses for the policy in the list, and then select **Edit**.</span></span>

<span data-ttu-id="f4735-122">Gehen Sie auf der Seite **Richtlinie bearbeiten** schrittweise durch die Optionen, und nehmen Sie die entsprechenden Änderungen vor:</span><span class="sxs-lookup"><span data-stu-id="f4735-122">For the **Edit policy** page, step through the pages and make the appropriate changes:</span></span>

- <span data-ttu-id="f4735-123">**Beschreibung**: Ändern Sie die Beschreibung, um den Zweck der Richtlinie besser verständlich zu machen.</span><span class="sxs-lookup"><span data-stu-id="f4735-123">**Description**: Change the description to make it easier to understand the policy's purpose.</span></span>
- <span data-ttu-id="f4735-124">**Schweregrad**</span><span class="sxs-lookup"><span data-stu-id="f4735-124">**Severity**</span></span>
- <span data-ttu-id="f4735-125">**Richtlinieneinstellungen**: Ändern Sie den Satz von Apps, auf die die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="f4735-125">**Policy settings**: Change the set of apps to which the policy applies.</span></span> <span data-ttu-id="f4735-126">Sie können die vorhandenen Bedingungen verwenden oder die Bedingungen ändern.</span><span class="sxs-lookup"><span data-stu-id="f4735-126">You can also choose to use the existing conditions or modify the conditions</span></span>
- <span data-ttu-id="f4735-127">**Aktionen**: Ändern automatischen Korrekturmaßnahmen für die Warnungen, die von der Richtlinie generiert werden.</span><span class="sxs-lookup"><span data-stu-id="f4735-127">**Actions**: Change the auto-remediation action for alerts generated by the policy.</span></span>
- <span data-ttu-id="f4735-128">**Status**: Ändern Sie den Richtlinienstatus.</span><span class="sxs-lookup"><span data-stu-id="f4735-128">**Status**: Change the policy status.</span></span>

## <a name="deleting-an-app-policy"></a><span data-ttu-id="f4735-129">Löschen einer App-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f4735-129">Deleting an app policy</span></span>

<span data-ttu-id="f4735-130">Zum Löschen einer App-Richtlinie haben Sie folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="f4735-130">To delete an app policy, you can:</span></span>

- <span data-ttu-id="f4735-131">Wählen Sie die Richtlinie in der Richtlinienliste und dann im Bereich „App-Richtlinie“ die Option **Löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="f4735-131">Select the policy in the policy list, and then select **Delete** on the app policy pane.</span></span>
- <span data-ttu-id="f4735-132">Wählen Sie die vertikalen Auslassungspunkte für die Richtlinie in der Liste und dann **Löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="f4735-132">Select the vertical ellipses for the policy in the list, and then select **Delete**.</span></span>

<span data-ttu-id="f4735-133">Eine Alternative zum Löschen einer App-Richtlinie besteht darin, ihren Status in „Inaktiv“ zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f4735-133">An alternative to deleting an app policy is to change its status to inactive.</span></span> <span data-ttu-id="f4735-134">Sobald sie inaktiv ist, werden keine Warnungen mehr generiert.</span><span class="sxs-lookup"><span data-stu-id="f4735-134">Once inactive, it will not generate alerts.</span></span> <span data-ttu-id="f4735-135">Anstatt beispielsweise eine App-Richtlinie für eine App mit einem bestimmten Satz von Bedingungen, die für eine zukünftige Richtlinie nützlich sind, zu löschen, können Sie die App-Richtlinie umbenennen, um deren Nützlichkeit zu verdeutlichen, und ihren Status auf inaktiv festlegen.</span><span class="sxs-lookup"><span data-stu-id="f4735-135">For example, rather than deleting an app policy for an app with a specific set of conditions that are useful for a future policy, rename the app policy to indicate its usefulness and set its status to inactive.</span></span> <span data-ttu-id="f4735-136">So können Sie später zur Richtlinie zurückkehren, sie für eine ähnliche App anpassen und ihren Status auf „Überwachungsmodus“ oder „Inaktiv“ festlegen.</span><span class="sxs-lookup"><span data-stu-id="f4735-136">You can later return to the policy and modify it for a similar app and set its status to audit mode or inactive.</span></span>
