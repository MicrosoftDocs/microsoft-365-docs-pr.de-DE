---
title: Ihre Apps anzeigen
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
description: Zeigen Sie Ihre Apps an.
ms.openlocfilehash: 48a1a2140a3b59091796ca013a12eeefb8a284b9
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420130"
---
# <a name="view-your-apps"></a><span data-ttu-id="7e7e8-103">Ihre Apps anzeigen</span><span class="sxs-lookup"><span data-stu-id="7e7e8-103">View your apps</span></span>

><span data-ttu-id="7e7e8-104">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="7e7e8-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="7e7e8-105">Mit der Microsoft-App-Governance können Sie schnell tiefe Insights in die Microsoft 365 Apps in Ihrem Mandanten gewinnen.</span><span class="sxs-lookup"><span data-stu-id="7e7e8-105">Microsoft app governance allows you to quickly gain deep insights into the Microsoft 365 apps in your tenant.</span></span> <span data-ttu-id="7e7e8-106">Sie können beispielsweise Folgendes sehen:</span><span class="sxs-lookup"><span data-stu-id="7e7e8-106">For example, you can see:</span></span>

- <span data-ttu-id="7e7e8-107">Eine Liste der OAuth-fähigen Apps im Mandanten, welche die Microsoft Graph-API verwenden, zusammen mit relevanten App-Metadaten und Nutzungsdaten.</span><span class="sxs-lookup"><span data-stu-id="7e7e8-107">A list of OAuth-enabled apps in the tenant that use the Microsoft Graph API, together with relevant app metadata and usage data.</span></span>
- <span data-ttu-id="7e7e8-108">App-Details mit tieferen Insights und Informationen, indem Sie eine App in der Liste auswählen.</span><span class="sxs-lookup"><span data-stu-id="7e7e8-108">App details with deeper insights and information by selecting an app in the list.</span></span>

## <a name="getting-a-list-of-all-the-apps-in-your-tenant"></a><span data-ttu-id="7e7e8-109">Abrufen einer Liste aller Apps in Ihrem Mandanten</span><span class="sxs-lookup"><span data-stu-id="7e7e8-109">Getting a list of all the apps in your tenant</span></span>

<span data-ttu-id="7e7e8-110">Eine Zusammenfassung der Apps in Ihrem Mandanten finden Sie unter **Microsoft 365 Compliance Center > App-Schutz & Governance > Apps**.</span><span class="sxs-lookup"><span data-stu-id="7e7e8-110">For a summary of apps in your tenant, go to **Microsoft 365 Compliance Center > App protection & governance > Apps**.</span></span>

![Die MAPG-App-Übersichtsseite im Microsoft 365 Compliance Center](..\media\manage-app-protection-governance\mapg-cc-apps.png)

>[!Note]
> <span data-ttu-id="7e7e8-112">Ihr Anmeldekonto muss über eine [dieser Rollen](app-governance-get-started.md#administrator-roles) verfügen, um App-Governance-Daten anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="7e7e8-112">Your sign-in account must have one of [these roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>
>

<span data-ttu-id="7e7e8-113">Sie werden eine Liste von Apps und diese Informationen sehen:</span><span class="sxs-lookup"><span data-stu-id="7e7e8-113">You will see a list of apps and this information:</span></span>

- <span data-ttu-id="7e7e8-114">App-Name</span><span class="sxs-lookup"><span data-stu-id="7e7e8-114">App Name</span></span>
- <span data-ttu-id="7e7e8-115">Herausgeber</span><span class="sxs-lookup"><span data-stu-id="7e7e8-115">Publisher</span></span>
- <span data-ttu-id="7e7e8-116">App-Zertifizierung</span><span class="sxs-lookup"><span data-stu-id="7e7e8-116">App certification</span></span>

  <span data-ttu-id="7e7e8-117">Gibt an, ob die App mit Microsoft-Technologien kompatibel ist, die den bewährten Methoden für Cloud-App-Sicherheit entsprechen und von Microsoft unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="7e7e8-117">Indicates whether the app is compatible with Microsoft technologies, compliant with cloud app security best practices, and supported by Microsoft.</span></span>

- <span data-ttu-id="7e7e8-118">Zuletzt geändert</span><span class="sxs-lookup"><span data-stu-id="7e7e8-118">Last modified</span></span>

  <span data-ttu-id="7e7e8-119">Zeigt das Datum an, an dem die App-Governance auf dem Client installiert wurde, wenn dieses Datum aktueller als das Datum ist, an dem die App zuletzt geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="7e7e8-119">Shows the date app governance was installed in client if that date is more recent than the date the app was last modified.</span></span>

- <span data-ttu-id="7e7e8-120">Installationsdatum</span><span class="sxs-lookup"><span data-stu-id="7e7e8-120">Date installed</span></span>
- <span data-ttu-id="7e7e8-121">Berechtigungsebene</span><span class="sxs-lookup"><span data-stu-id="7e7e8-121">Privilege level</span></span>
- <span data-ttu-id="7e7e8-122">Anzahl der Benutzer</span><span class="sxs-lookup"><span data-stu-id="7e7e8-122">Number of users</span></span>
- <span data-ttu-id="7e7e8-123">Datenzugriff</span><span class="sxs-lookup"><span data-stu-id="7e7e8-123">Data access</span></span>

  <span data-ttu-id="7e7e8-124">Die Summe des Hochladens und Herunterladens der App-Daten im Mandanten über den letzten Tag, sowie die Änderung im Vergleich zum vorherigen Tag.</span><span class="sxs-lookup"><span data-stu-id="7e7e8-124">The sum of the app’s data upload and download in the tenant over the last day, along with the change over the prior day.</span></span>

<span data-ttu-id="7e7e8-125">Die App-Governance sortiert die App-Liste standardmäßig nach **App-Namen**.</span><span class="sxs-lookup"><span data-stu-id="7e7e8-125">App governance sorts the app list by **App name** by default.</span></span> <span data-ttu-id="7e7e8-126">Um die Liste nach einem anderen App-Attribut zu sortieren, wählen Sie den Attributnamen aus.</span><span class="sxs-lookup"><span data-stu-id="7e7e8-126">To sort the list by another app attribute, select the attribute name.</span></span>

<span data-ttu-id="7e7e8-127">Sie können auch **Suchen** auswählen, um nach einer App anhand des Namens zu suchen.</span><span class="sxs-lookup"><span data-stu-id="7e7e8-127">You can also select **Search** to search for an app by name.</span></span>

## <a name="getting-detailed-information-on-an-app"></a><span data-ttu-id="7e7e8-128">Abrufen detaillierter Informationen zu einer App</span><span class="sxs-lookup"><span data-stu-id="7e7e8-128">Getting detailed information on an app</span></span>

<span data-ttu-id="7e7e8-129">Für detaillierte Informationen zu einer bestimmten App in Ihrem Mandanten wechseln sie zu \*\*Microsoft 365 Compliance Center > App Governance > Apps-Seite > \*App-Name\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="7e7e8-129">For detailed information on a specific app in your tenant, go to \*\*Microsoft 365 Compliance Center > App governance > Apps page > \*app name\*\*\*.</span></span>

![Der App-Detailbereich der App-Governance im Microsoft 365 Compliance Center](..\media\manage-app-protection-governance\mapg-cc-apps-app.png)

<span data-ttu-id="7e7e8-131">Der App-Detailbereich enthält zusätzliche Informationen auf diesen Registerkarten:</span><span class="sxs-lookup"><span data-stu-id="7e7e8-131">The app details pane provides additional information on these tabs:</span></span>

| <span data-ttu-id="7e7e8-132">Registerkartenname</span><span class="sxs-lookup"><span data-stu-id="7e7e8-132">Tab name</span></span> | <span data-ttu-id="7e7e8-133">Description</span><span class="sxs-lookup"><span data-stu-id="7e7e8-133">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="7e7e8-134">Details</span><span class="sxs-lookup"><span data-stu-id="7e7e8-134">Details</span></span> | <span data-ttu-id="7e7e8-135">Sehen Sie sich zusätzliche Daten zur App an, z. B. das Datum der ersten Zustimmung und die App-ID.</span><span class="sxs-lookup"><span data-stu-id="7e7e8-135">See additional data on the app such as the date first consented and the App ID.</span></span> <span data-ttu-id="7e7e8-136">Um die Eigenschaften der App wie in Azure AD registriert anzuzeigen, wählen Sie **App in Azure AD anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="7e7e8-136">To see the properties of the app as registered in Azure AD, select **View app in Azure AD**.</span></span> |
| <span data-ttu-id="7e7e8-137">Nutzung</span><span class="sxs-lookup"><span data-stu-id="7e7e8-137">Usage</span></span> | <span data-ttu-id="7e7e8-138">Hier sehen Sie die Daten, auf welche die App im Mandanten zugreift, zeichnen die Datennutzung auf, und zeigen die Nutzung durch die obersten \<x> Benutzer und Benutzer mit [Prioritätskonten](/microsoft-365/admin/setup/priority-accounts) an.</span><span class="sxs-lookup"><span data-stu-id="7e7e8-138">See the data accessed by the app in the tenant, plot the data usage, and show usage by the top \<x> users and users with [priority accounts](/microsoft-365/admin/setup/priority-accounts).</span></span> |
| <span data-ttu-id="7e7e8-139">Benutzer</span><span class="sxs-lookup"><span data-stu-id="7e7e8-139">Users</span></span> | <span data-ttu-id="7e7e8-140">Hier sehen Sie eine Liste der Benutzer, welche die App verwenden, ob es sich um ein Prioritätskonto handelt, sowie die Menge der heruntergeladenen und hochgeladenen Daten.</span><span class="sxs-lookup"><span data-stu-id="7e7e8-140">See a list of users who are using the app, whether they are a priority account, and the amount of data downloaded and uploaded.</span></span> |
| <span data-ttu-id="7e7e8-141">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="7e7e8-141">Permissions</span></span> | <span data-ttu-id="7e7e8-142">Hier sehen Sie eine Zusammenfassung der Berechtigungen, die der App gewährt und von ihr verwendet werden, sowie die Liste der spezifischen Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="7e7e8-142">See a summary of the permissions granted to and used by the app and the list of specific permissions.</span></span> <span data-ttu-id="7e7e8-143">Lesen Sie die [Referenz zu den Microsoft Graph-Berechtigungen](/graph/permissions-reference) für weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="7e7e8-143">See the [Microsoft Graph permissions reference](/graph/permissions-reference) for more information.</span></span> |
|||

<span data-ttu-id="7e7e8-144">Für eine aktivierte App gibt es auch ein Steuerelement **App deaktivieren**, um die Verwendung der ausgewählten App zu deaktivieren, und ein Steuerelement **App aktivieren**, um die Verwendung der deaktivierten App zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="7e7e8-144">For an enabled app, there is also a **Disable app** control to disable the use of the selected app and an **Enable app** control to enable the use of the disabled app.</span></span> <span data-ttu-id="7e7e8-145">Für diese Aktionen sind diese [Administratorrollen](app-governance-get-started.md#administrator-roles)erforderlich:</span><span class="sxs-lookup"><span data-stu-id="7e7e8-145">These actions require these [administrator roles](app-governance-get-started.md#administrator-roles):</span></span>

- <span data-ttu-id="7e7e8-146">Compliance-Administrator</span><span class="sxs-lookup"><span data-stu-id="7e7e8-146">Compliance Administrator</span></span>
- <span data-ttu-id="7e7e8-147">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="7e7e8-147">Global Administrator</span></span>
- <span data-ttu-id="7e7e8-148">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="7e7e8-148">Security Administrator</span></span>
- <span data-ttu-id="7e7e8-149">Sicherheitsoperator</span><span class="sxs-lookup"><span data-stu-id="7e7e8-149">Security Operator</span></span>

## <a name="next-step"></a><span data-ttu-id="7e7e8-150">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="7e7e8-150">Next step</span></span>

<span data-ttu-id="7e7e8-151">[Bestimmen Sie Ihre allgemeinen App-Compliance-Ausrichtung](app-governance-visibility-insights-compliance-posture.md).</span><span class="sxs-lookup"><span data-stu-id="7e7e8-151">[Determine your overall app compliance posture](app-governance-visibility-insights-compliance-posture.md).</span></span>
