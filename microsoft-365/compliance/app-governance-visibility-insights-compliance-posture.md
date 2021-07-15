---
title: Bestimmen Ihrer App-Compliance-Ausrichtung
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
description: Bestimmen Sie Ihre App-Compliance-Ausrichtung.
ms.openlocfilehash: 3d7cac319c31bac40a3aad2f6b9a4c16303f6a20
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420124"
---
# <a name="determine-your-app-compliance-posture"></a><span data-ttu-id="1dff3-103">Bestimmen Ihrer App-Compliance-Ausrichtung</span><span class="sxs-lookup"><span data-stu-id="1dff3-103">Determine your app compliance posture</span></span>

><span data-ttu-id="1dff3-104">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="1dff3-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="1dff3-105">Mit der Microsoft-App-Governance können Sie die Compliance-Ausrichtung der Drittanbieter-Apps und deren Zugriff auf Daten in Ihrem Microsoft 365 Mandanten schnell über die Übersichtsseite der App-Governance im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/appgovernance) beurteilen.</span><span class="sxs-lookup"><span data-stu-id="1dff3-105">Microsoft app governance allows you to quickly assess the compliance posture of the third-party apps and their access to data in your Microsoft 365 tenant from the app governance Overview page in the [Microsoft 365 Compliance Center](https://compliance.microsoft.com/appgovernance).</span></span>

![Die Übersichtsseite der App-Governance im Microsoft 365 Compliance Center](..\media\manage-app-protection-governance\mapg-cc-overview.png)

>[!Note]
> <span data-ttu-id="1dff3-107">Ihr Anmeldekonto muss über eine [dieser Rollen](app-governance-get-started.md#administrator-roles) verfügen, um App-Governance-Daten anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="1dff3-107">Your sign-in account must have one of [these roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>
>

<span data-ttu-id="1dff3-108">Von dieser Seite aus können Sie Folgendes sehen:</span><span class="sxs-lookup"><span data-stu-id="1dff3-108">From this page, you can see:</span></span>

- <span data-ttu-id="1dff3-109">Für OAuth-fähige Apps, welche die Microsoft Graph-API verwenden:</span><span class="sxs-lookup"><span data-stu-id="1dff3-109">For OAuth-enabled apps that use the Microsoft Graph API:</span></span>

  - <span data-ttu-id="1dff3-110">Wie viele befinden sich in Ihrem Mandanten?</span><span class="sxs-lookup"><span data-stu-id="1dff3-110">How many are in your tenant</span></span>
  - <span data-ttu-id="1dff3-111">Wie viele sind möglicherweise überprivilegiert?</span><span class="sxs-lookup"><span data-stu-id="1dff3-111">How many might be overprivileged</span></span>
  - <span data-ttu-id="1dff3-112">Wie viele haben hohe Berechtigungen?</span><span class="sxs-lookup"><span data-stu-id="1dff3-112">How many are high privilege</span></span>

  <span data-ttu-id="1dff3-113">Anhand dieser Informationen können Sie das Risiko für Ihre Organisation ermitteln, das überprivilegierte Apps und solche mit hohen Berechtigungen darstellen.</span><span class="sxs-lookup"><span data-stu-id="1dff3-113">From this information, you can determine the level of risk to your organization by overprivileged and high privilege apps.</span></span>

- <span data-ttu-id="1dff3-114">Für Benachrichtigungen:</span><span class="sxs-lookup"><span data-stu-id="1dff3-114">For alerts:</span></span>

  - <span data-ttu-id="1dff3-115">Wie viele aktive Benachrichtigungen Ihr Mandant hat</span><span class="sxs-lookup"><span data-stu-id="1dff3-115">How many active alerts your tenant has</span></span>
  - <span data-ttu-id="1dff3-116">Wie viele basieren auf Erkennungen der App-Governance (**Bedrohungsbenachrichtigungen**)</span><span class="sxs-lookup"><span data-stu-id="1dff3-116">How many are based on app governance detections (**Threat alerts**)</span></span>
  - <span data-ttu-id="1dff3-117">Wie viele basieren auf App-Richtlinien, die Sie eingerichtet haben (**Richtlinienbenachrichtigungen**)</span><span class="sxs-lookup"><span data-stu-id="1dff3-117">How many are based on app policies you have in place (**Policy alerts**)</span></span>
  - <span data-ttu-id="1dff3-118">Die letzten zehn 10 Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="1dff3-118">The 10 latest alerts</span></span>

  <span data-ttu-id="1dff3-119">Anhand dieser Informationen können Sie bestimmen, wie schnell Benachrichtigungen erstellt werden, und wie hoch die relative Anzahl der erkannten und richtlinienbasierten Alarme ist.</span><span class="sxs-lookup"><span data-stu-id="1dff3-119">From this information, you can determine how quickly alerts are being generated and the relative number of detected and policy-based alerts.</span></span>

- <span data-ttu-id="1dff3-120">Für Daten- und Ressourcenzugriff:</span><span class="sxs-lookup"><span data-stu-id="1dff3-120">For data and resources access:</span></span>

  - <span data-ttu-id="1dff3-121">Die API-Datenzugriffe der Anwendung in den letzten 90 Tagen</span><span class="sxs-lookup"><span data-stu-id="1dff3-121">The application API data access in the last 90 days</span></span>
  - <span data-ttu-id="1dff3-122">Die Nutzung der wichtigsten Ressourcen in den letzten 90 Tagen</span><span class="sxs-lookup"><span data-stu-id="1dff3-122">The usage of the top resources in the last 90 days</span></span>

  <span data-ttu-id="1dff3-123">Anhand dieser Informationen können Sie ermitteln, ob es anomale Spitzen beim Zugriff auf die Daten in Ihrem Microsoft 365-Mandanten gibt.</span><span class="sxs-lookup"><span data-stu-id="1dff3-123">From this information, you can determine if there are anomalous spikes in access to the data in your Microsoft 365 tenant.</span></span>
