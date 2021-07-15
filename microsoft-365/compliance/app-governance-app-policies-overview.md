---
title: Erfahren Sie mehr über App-Richtlinien
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
description: Erfahren Sie mehr über App-Richtlinien.
ms.openlocfilehash: 6d4ff23ca0e09f5e410d32d6ced144afc0c4bb15
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420185"
---
# <a name="learn-about-app-policies"></a><span data-ttu-id="aaa9e-103">Erfahren Sie mehr über App-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="aaa9e-103">Learn about app policies</span></span>

><span data-ttu-id="aaa9e-104">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit & Compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="aaa9e-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="aaa9e-105">Die Microsoft-App-Governance erkennt anomales App-Verhalten in Ihrem Microsoft 365-Mandanten und generiert Warnungen, die Sie sehen, untersuchen und beheben können.</span><span class="sxs-lookup"><span data-stu-id="aaa9e-105">Microsoft app governance detects anomalous app behavior in your Microsoft 365 tenant and generates alerts that you can see, investigate, and resolve.</span></span> <span data-ttu-id="aaa9e-106">Über diese integrierte Erkennungsfunktion hinaus können Sie eine Reihe von Standardvorlagen verwenden, um Ihre eigenen App-Richtlinien zu erstellen, die andere Warnungen generieren.</span><span class="sxs-lookup"><span data-stu-id="aaa9e-106">Beyond this built-in detection capability, you can use a set of default templates to create your own app policies that generate other alerts.</span></span>

<span data-ttu-id="aaa9e-107">Diese Richtlinien für App- und Benutzerverhaltensmuster können Ihre Benutzer vor der Verwendung nicht konformer oder bösartiger Apps schützen und den Zugriff riskanter Apps auf Ihre Mandantendaten einschränken.</span><span class="sxs-lookup"><span data-stu-id="aaa9e-107">These policies for app and user patterns and behaviors can protect your users from using non-compliant or malicious apps and limit the access of risky apps to your tenant data.</span></span>

<span data-ttu-id="aaa9e-108">Hier finden Sie eine kurze Übersicht über die erforderlichen Administratorrollen für die Verwaltung von App-Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="aaa9e-108">Here's a quick review of required administrator roles for app policy management.</span></span>

| <span data-ttu-id="aaa9e-109">Rolle</span><span class="sxs-lookup"><span data-stu-id="aaa9e-109">Role</span></span> | <span data-ttu-id="aaa9e-110">Richtlinien lesen</span><span class="sxs-lookup"><span data-stu-id="aaa9e-110">Read policies</span></span> | <span data-ttu-id="aaa9e-111">Richtlinien erstellen, aktualisieren oder löschen</span><span class="sxs-lookup"><span data-stu-id="aaa9e-111">Create, update, or delete policies</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="aaa9e-112">Complianceadministrator</span><span class="sxs-lookup"><span data-stu-id="aaa9e-112">Compliance Administrator</span></span> | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) |
| <span data-ttu-id="aaa9e-115">Complianceleseberechtigter</span><span class="sxs-lookup"><span data-stu-id="aaa9e-115">Compliance Reader</span></span> | ![Häkchen](..\media\checkmark.png) |  |
| <span data-ttu-id="aaa9e-117">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="aaa9e-117">Global Administrator</span></span> | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) |
| <span data-ttu-id="aaa9e-120">Globaler Leser</span><span class="sxs-lookup"><span data-stu-id="aaa9e-120">Global Reader</span></span>  | ![Häkchen](..\media\checkmark.png) |  |
| <span data-ttu-id="aaa9e-122">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="aaa9e-122">Security Administrator</span></span> | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) |
| <span data-ttu-id="aaa9e-125">Sicherheitsleseberechtigter</span><span class="sxs-lookup"><span data-stu-id="aaa9e-125">Security Reader</span></span>  | ![Häkchen](..\media\checkmark.png) |  |
| <span data-ttu-id="aaa9e-127">Sicherheitsoperator</span><span class="sxs-lookup"><span data-stu-id="aaa9e-127">Security Operator</span></span> | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) |
||||

<!--
How app policies are the method by which MAPG detects app anomolies resulting in detection (alerts) and remediation (manual or automatic) 


CFA #2 Scenario 1: As an admin, I can quickly set up policies to govern M365 apps in my tenant using MAPG out-of-the-box templates
CFA #2 Scenario 2: As an admin, I can create customized policies to govern M365 apps in my tenant to meet my organizations requirements.
CFA #2 Scenario 3: As an admin or policy reviewer, I can view all policies created in my environment and quickly see which policies have associated alerts. 
CFA #2 Scenario 4: As an admin, I can adjust policies efficiently to meet changing needs.

App policy templates

- Basic info
- Policy settings and conditions
- Actions
- Status

--> 

## <a name="next-step"></a><span data-ttu-id="aaa9e-130">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="aaa9e-130">Next step</span></span>

[<span data-ttu-id="aaa9e-131">Erste Schritte mit App-Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="aaa9e-131">Get started with app policies.</span></span>](app-governance-app-policies-get-started.md)
