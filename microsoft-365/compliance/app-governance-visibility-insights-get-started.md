---
title: Erste Schritte mit Sichtbarkeit und Insights
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
description: Beginnen Sie mit Sichtbarkeit und Insights.
ms.openlocfilehash: 93be3557c32345e81c7126b669ead8edf8ebac21
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430480"
---
# <a name="get-started-with-visibility-and-insights"></a><span data-ttu-id="cfbb3-103">Erste Schritte mit Sichtbarkeit und Insights</span><span class="sxs-lookup"><span data-stu-id="cfbb3-103">Get started with visibility and insights</span></span>

><span data-ttu-id="cfbb3-104">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="cfbb3-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="cfbb3-105">Der Ort für die ersten Schritte ist das App-Governance-Dashboard auf [https://aka.ms/appgovernance](https://aka.ms/appgovernance).</span><span class="sxs-lookup"><span data-stu-id="cfbb3-105">The first place to get started is the app governance dashboard at [https://aka.ms/appgovernance](https://aka.ms/appgovernance).</span></span> <span data-ttu-id="cfbb3-106">Beachten Sie, dass Ihr Anmeldekonto über eine [dieser App-Governance-Administratorrollen](app-governance-get-started.md#administrator-roles) verfügen muss, um App-Governance-Daten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="cfbb3-106">Note that your sign-in account must have one of [these app governance administrator roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>

![Die Übersichtsseite der App-Governance im Microsoft 365 Compliance Center](..\media\manage-app-protection-governance\mapg-cc-overview.png)

<span data-ttu-id="cfbb3-108">Sie können auch über **Microsoft 365 Admin Center > Microsoft 365 Compliance Center > App-Governance > Übersichtsseite** auf das Dashboard für die App-Governance zugreifen.</span><span class="sxs-lookup"><span data-stu-id="cfbb3-108">You can also access the app governance dashboard from **Microsoft 365 admin center > Microsoft 365 Compliance Center > App governance > Overview page**.</span></span>

## <a name="whats-available-on-the-dashboard"></a><span data-ttu-id="cfbb3-109">Was ist auf dem Dashboard verfügbar</span><span class="sxs-lookup"><span data-stu-id="cfbb3-109">What’s available on the dashboard</span></span>

<span data-ttu-id="cfbb3-110">Das Dashboard enthält eine Zusammenfassung der Komponenten des Microsoft 365 App-Ökosystems im Mandanten:</span><span class="sxs-lookup"><span data-stu-id="cfbb3-110">The dashboard contains a summary of the components of the Microsoft 365 app ecosystem in the tenant:</span></span>

- <span data-ttu-id="cfbb3-111">**Mandantenzusammenfassung**: Die Anzahl der wichtigsten App- und Benachrichtigungskategorien.</span><span class="sxs-lookup"><span data-stu-id="cfbb3-111">**Tenant summary**: The count of key app and alert categories.</span></span>
- <span data-ttu-id="cfbb3-112">**Erkennungs- und Richtlinienbenachrichtigungen**: Die neuesten aktiven Benachrichtigungen im Mandanten</span><span class="sxs-lookup"><span data-stu-id="cfbb3-112">**Detection and policy alerts**: The most recent active alerts in the tenant</span></span>
- <span data-ttu-id="cfbb3-113">**Daten- und Ressourcenzugriff**: Aggregieren Sie den Zugriff auf die Anwendungs-API und die Gesamtnutzung der wichtigsten Ressourcen im Mandanten.</span><span class="sxs-lookup"><span data-stu-id="cfbb3-113">**Data and resources access**: Aggregate application API access and overall usage of top resources in the tenant.</span></span> <span data-ttu-id="cfbb3-114">Bewegen Sie den Mauszeiger über jede Monatsspalte im Diagramm, um den entsprechenden Wert anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="cfbb3-114">Mouse over each month column in the graph to see the corresponding value.</span></span>
- <span data-ttu-id="cfbb3-115">**Verbessern des Schutzes und der Governance Ihrer App**: Empfohlene Aktionen wie das Erstellen einer App-Nutzungs- oder Berechtigungsrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="cfbb3-115">**Improve your app protection and governance**: Recommended actions such as creating an app usage or permissions policy.</span></span>
- <span data-ttu-id="cfbb3-116">**Wichtigste Apps nach Kategorien**: Die wichtigsten Apps, sortiert nach diesen Kategorien:</span><span class="sxs-lookup"><span data-stu-id="cfbb3-116">**Top apps by categories**: The top apps sorted by these categories:</span></span>
  
  - <span data-ttu-id="cfbb3-117">**Alle Kategorien**: Sortiert über alle verfügbaren Kategorien.</span><span class="sxs-lookup"><span data-stu-id="cfbb3-117">**All categories**: Sorts across all available categories.</span></span>
  - <span data-ttu-id="cfbb3-118">**Hohe Berechtigung**: „Hohe Berechtigung“ ist eine intern festgelegte Kategorie, die auf maschinellem Lernen und Signalen der Plattform basiert.</span><span class="sxs-lookup"><span data-stu-id="cfbb3-118">**High privilege**: High privilege is an internally determined category based on platform machine learning and signals.</span></span>
  - <span data-ttu-id="cfbb3-119">**Überprivilegiert**: Wenn die App-Governance Telemetriedaten empfängt, die angeben, dass eine einer Anwendung erteilte Berechtigung in den letzten 90 Tagen nicht verwendet wurde, ist diese Anwendung überprivilegiert.</span><span class="sxs-lookup"><span data-stu-id="cfbb3-119">**Overprivileged**: When app governance receives telemetry that indicates that a permission granted to an application has not been used in the last 90 days, that application is overprivileged.</span></span> <span data-ttu-id="cfbb3-120">Die App-Governance muss mindestens 90 Tage lang ausgeführt werden, um festzustellen, ob eine App überprivilegiert ist.</span><span class="sxs-lookup"><span data-stu-id="cfbb3-120">App governance must be operating for at least 90 days to determine if any app is overprivileged.</span></span>  
  - <span data-ttu-id="cfbb3-121">**Nicht überprüft**: Anwendungen, die keine [Herausgeberzertifizierung](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview) erhalten haben, werden als nicht überprüft betrachtet.</span><span class="sxs-lookup"><span data-stu-id="cfbb3-121">**Unverified**: Applications that have not received [publisher certification](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview) are considered unverified.</span></span>
  - <span data-ttu-id="cfbb3-122">**Nur App**: [Anwendungsberechtigungen](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#permission-types) werden von Apps verwendet, die ohne die Anwesenheit eines angemeldeten Benutzers ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="cfbb3-122">**App only**: [Application permissions](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#permission-types) are used by apps that can run without a signed-in user present.</span></span> <span data-ttu-id="cfbb3-123">Apps mit mandantenübergreifenden Zugriffsberechtigungen auf Daten stellen ein potenziell höheres Risiko dar.</span><span class="sxs-lookup"><span data-stu-id="cfbb3-123">Apps with permissions to access data across the tenant are potentially a higher risk.</span></span>
  - <span data-ttu-id="cfbb3-124">**Neue Apps**: Neue Microsoft 365 Apps, die in den letzten sieben Tagen registriert wurden.</span><span class="sxs-lookup"><span data-stu-id="cfbb3-124">**New apps**: New Microsoft 365 apps that have been registered in the last seven days.</span></span>  

## <a name="next-step"></a><span data-ttu-id="cfbb3-125">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="cfbb3-125">Next step</span></span>

<span data-ttu-id="cfbb3-126">[Erhalten Sie detaillierte Insights in eine bestimmte App](app-governance-visibility-insights-view-apps.md).</span><span class="sxs-lookup"><span data-stu-id="cfbb3-126">[Get detailed insights on a specific app](app-governance-visibility-insights-view-apps.md).</span></span>
