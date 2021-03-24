---
title: Verwenden von Identitäts-, Geräte- und Bedrohungsschutz für Datenschutzbestimmungen
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Verhindern von Verletzungen personenbezogener Daten mit Identitäts-, Geräte- und Bedrohungsschutzdiensten von Microsoft 365.
ms.openlocfilehash: 145b8a59f7eafb95adf71dc24613ee15ef1c2cca
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052350"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="94c1c-103">Verwenden von Identitäts-, Geräte- und Bedrohungsschutz für Datenschutzbestimmungen</span><span class="sxs-lookup"><span data-stu-id="94c1c-103">Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="94c1c-104">Microsoft 365 bietet eine Reihe von Identitäts-, Geräte- und Bedrohungsschutzfunktionen, die Organisationen zur Einhaltung datenschutzbezogener Compliancebestimmungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="94c1c-104">Microsoft 365 provides a number of identity, device, and threat protection capabilities that organizations can employ to help comply with data privacy-related compliance regulations.</span></span> <span data-ttu-id="94c1c-105">In diesem Artikel wird beschrieben, was die Datenschutzbestimmungen in diesen Bereichen erfordern, und enthält eine Liste der zugehörigen Microsoft 365-Features und -Dienste mit Links zu weiteren Informationen, mit denen Sie Implementierungsanforderungen erfüllen können.</span><span class="sxs-lookup"><span data-stu-id="94c1c-105">This article describes what the data privacy regulations require in these areas and provides a listing of related Microsoft 365 features and services with links to more information to help you address implementation requirements.</span></span>

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a><span data-ttu-id="94c1c-106">Beziehung zwischen Identitäts-, Geräte- und Bedrohungsschutz in Bezug auf Datenschutzbestimmungen</span><span class="sxs-lookup"><span data-stu-id="94c1c-106">How identity, device, and threat protection relate to data privacy regulation</span></span>

<span data-ttu-id="94c1c-107">Während die Datenschutzbestimmungen in ihrer Spezifizität variieren, ist das Wesentliche dessen, was sie fordern, in Artikel 5 Absatz 1 (f) der DSGVO enthalten, in dem es heißt, dass:</span><span class="sxs-lookup"><span data-stu-id="94c1c-107">While the data privacy regulations vary in their specificity, the essence of what they call for is embodied in the GDPR’s Article 5(1)(f), which states that:</span></span>

- <span data-ttu-id="94c1c-108">Personenbezogene Daten werden auf eine Weise verarbeitet, die eine angemessene Sicherheit der personenbezogenen Daten gewährleistet, einschließlich des Schutzes vor nicht autorisierter oder unrechtmäßiger Verarbeitung und vor versehentlichem Verlust, Zerstörung oder Schaden, unter Verwendung geeigneter technischer oder organisatorischer Maßnahmen ("Integrität und Vertraulichkeit").</span><span class="sxs-lookup"><span data-stu-id="94c1c-108">Personal data shall be processed in a manner that ensures appropriate security of the personal data, including protection against unauthorized or unlawful processing and against accidental loss, destruction or damage, using appropriate technical or organizational measures ('integrity and confidentiality').</span></span>

<span data-ttu-id="94c1c-109">Da Verletzungen personenbezogener Daten häufig durch administrative oder Endbenutzerkontoverstöße und böswilligen Systemzugriff verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="94c1c-109">Because personal data breaches are often caused by administrative or end-user account compromise and malicious system access.</span></span> <span data-ttu-id="94c1c-110">Beispielsweise kann ein Administratorkonto-Hack zu einer Exfiltration von Kunden-Kreditkartennummern oder anderen persönlichen Informationen führen.</span><span class="sxs-lookup"><span data-stu-id="94c1c-110">For example, an admin account hack can result in exfiltration of customer credit card numbers or other personal information.</span></span> <span data-ttu-id="94c1c-111">Alle allgemein empfohlenen Identitäts-, Geräte- und Bedrohungsschutz, die mit Microsoft 365 verfügbar sind, sollten implementiert werden, was sich in Ihrer Compliance-Bewertung widerspiegelt, die im Compliance-Manager zu finden ist.</span><span class="sxs-lookup"><span data-stu-id="94c1c-111">All the generally advisable identity, device, and threat protection available with Microsoft 365 potentially should be implemented, which will be reflected in your compliance score, found in Compliance Manager.</span></span>

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a><span data-ttu-id="94c1c-112">Verwenden der Ergebnisse Ihrer Bewertungsarbeit und des Compliance-Managers</span><span class="sxs-lookup"><span data-stu-id="94c1c-112">Using the results of your assessment work and Compliance Manager</span></span>

<span data-ttu-id="94c1c-113">Compliance Manager umfasst Identitäts-, Geräte- und Bedrohungsschutz unter Verwendung der folgenden Kategorien:</span><span class="sxs-lookup"><span data-stu-id="94c1c-113">Compliance Manager includes identity, device, and threat protection using these categories:</span></span>

- <span data-ttu-id="94c1c-114">Identität entspricht der **Kategorie "Zugriffssteuerung"**</span><span class="sxs-lookup"><span data-stu-id="94c1c-114">Identity corresponds to the **Control Access** category</span></span>
- <span data-ttu-id="94c1c-115">Gerät entspricht der **Kategorie Geräte** verwalten</span><span class="sxs-lookup"><span data-stu-id="94c1c-115">Device corresponds to the **Manage Devices** category</span></span>
- <span data-ttu-id="94c1c-116">Bedrohungsschutz entspricht der **Kategorie Schutz vor Bedrohungen**</span><span class="sxs-lookup"><span data-stu-id="94c1c-116">Threat protection corresponds to the **Protect Against Threats** category</span></span>
 
<span data-ttu-id="94c1c-117">Wenn diese in unserem Beispielsatz mit vier wichtigen Datenschutzbestimmungen ausgewählt werden, gibt der Compliance-Manager 90 Verbesserungsmaßnahmen an, von denen die meisten als "27" bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="94c1c-117">If these are selected across our sample set of four major data privacy regulations, Compliance Manager specifies 90 improvement actions, most of which are scored a "27".</span></span> <span data-ttu-id="94c1c-118">Da eine so große Anzahl vom Compliance-Manager für diese Kategorien aufgerufen wird, werden einige der gängigen Kategorien hier aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="94c1c-118">Since such a large number are called out by Compliance Manager for these categories, some of the more common ones are listed here, for reference.</span></span>

<span data-ttu-id="94c1c-119">Verwenden [Sie Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) für die Identität und die Kategorie Control **Access,** mit der Sie:</span><span class="sxs-lookup"><span data-stu-id="94c1c-119">Use [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) for identity and the **Control Access** category, with which you can:</span></span>

- <span data-ttu-id="94c1c-120">Implementieren der wiedergabesicheren Authentifizierung (um Angriffe von "Man in der Mitte" zu verhindern)</span><span class="sxs-lookup"><span data-stu-id="94c1c-120">Implement replay-resistant authentication (to prevent “Man in the middle” attacks)</span></span>
- <span data-ttu-id="94c1c-121">Blockieren Sie die Legacyauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="94c1c-121">Block legacy authentication.</span></span>
- <span data-ttu-id="94c1c-122">Konfigurieren von Risikorichtlinien für Benutzerrisiken und Benutzer-Anmelderisiken.</span><span class="sxs-lookup"><span data-stu-id="94c1c-122">Configure user risk and user sign-in risk policies.</span></span>
- <span data-ttu-id="94c1c-123">Aktivieren Sie bedingten Zugriff und mehrstufige Authentifizierung (MFA) für Administratoren und Nicht-Administratoren.</span><span class="sxs-lookup"><span data-stu-id="94c1c-123">Enable Conditional Access and multi-factor authentication (MFA) for admins and non-admins.</span></span>
- <span data-ttu-id="94c1c-124">Konfigurieren und Erzwingen von Kennwortrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="94c1c-124">Configure and enforce password policies.</span></span>
- <span data-ttu-id="94c1c-125">Einschränken des Zugriffs auf privilegierte Konten mit Azure AD Privileged Identity Management.</span><span class="sxs-lookup"><span data-stu-id="94c1c-125">Restrict access to privileged accounts with Azure AD Privileged Identity Management.</span></span>
- <span data-ttu-id="94c1c-126">Deaktivieren sie den Zugriff bei Beendigung.</span><span class="sxs-lookup"><span data-stu-id="94c1c-126">Disable access upon termination.</span></span>
- <span data-ttu-id="94c1c-127">Überwachen von Benutzerkonten und Statusänderungen.</span><span class="sxs-lookup"><span data-stu-id="94c1c-127">Audit user accounts and status changes.</span></span>
- <span data-ttu-id="94c1c-128">Überprüfen von Rollengruppen- und administrativen Änderungen.</span><span class="sxs-lookup"><span data-stu-id="94c1c-128">Review role group and administrative changes.</span></span>

<span data-ttu-id="94c1c-129">Verwenden [Sie Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) für Geräte und die Kategorie **Geräte** verwalten, mit der Sie:</span><span class="sxs-lookup"><span data-stu-id="94c1c-129">Use [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) for devices and the **Manage Devices** category, with which you can:</span></span>

- <span data-ttu-id="94c1c-130">Blockieren von beschädigten und verankerten mobilen Geräten im Jail.</span><span class="sxs-lookup"><span data-stu-id="94c1c-130">Block jail broken and rooted mobile devices.</span></span>
- <span data-ttu-id="94c1c-131">Konfigurieren von Intune für die Verwaltung mobiler Geräte.</span><span class="sxs-lookup"><span data-stu-id="94c1c-131">Configure Intune for mobile device management.</span></span>
- <span data-ttu-id="94c1c-132">Erstellen von Compliancerichtlinien für Android-, iOS-, macOS- und Windows-Geräte.</span><span class="sxs-lookup"><span data-stu-id="94c1c-132">Create compliance policies for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="94c1c-133">Erstellen Sie ein Gerätekonfigurationsprofil für Android-, iOS-, macOS- und Windows-Geräte.</span><span class="sxs-lookup"><span data-stu-id="94c1c-133">Create a device configuration profile for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="94c1c-134">Erstellen von App-Schutzrichtlinien für iOS und Windows.</span><span class="sxs-lookup"><span data-stu-id="94c1c-134">Create app protection policies for iOS and Windows.</span></span>
- <span data-ttu-id="94c1c-135">Verbergen von Informationen mit Sperrbildschirm.</span><span class="sxs-lookup"><span data-stu-id="94c1c-135">Conceal information with lock screen.</span></span>
- <span data-ttu-id="94c1c-136">Implementieren sie Kennwortrichtlinien für mobile Geräte.</span><span class="sxs-lookup"><span data-stu-id="94c1c-136">Implement password policies for mobile devices.</span></span>
- <span data-ttu-id="94c1c-137">Mobile Geräte müssen bei Inaktivität gesperrt werden.</span><span class="sxs-lookup"><span data-stu-id="94c1c-137">Require mobile devices to lock upon inactivity.</span></span>
- <span data-ttu-id="94c1c-138">Mobile Geräte müssen bei mehreren Anmeldefehlern wischen.</span><span class="sxs-lookup"><span data-stu-id="94c1c-138">Require mobile devices to wipe on multiple sign-in failures.</span></span>

<span data-ttu-id="94c1c-139">Verwenden [Sie Exchange Online Protection und Microsoft Defender für Office 365](../security/defender-365-security/defender-for-office-365.md) für die Kategorie **Schutz** vor Bedrohungen, mit der Sie:</span><span class="sxs-lookup"><span data-stu-id="94c1c-139">Use [Exchange Online Protection and Microsoft Defender for Office 365](../security/defender-365-security/defender-for-office-365.md) for the **Protect Against Threats** category, with which you can:</span></span>

- <span data-ttu-id="94c1c-140">Aktivieren der Absenderauthentifizierung (SPF, DMARC und DKIM).</span><span class="sxs-lookup"><span data-stu-id="94c1c-140">Enable sender authentication (SPF, DMARC and DKIM).</span></span>
- <span data-ttu-id="94c1c-141">Richten Sie Microsoft Defender für Office 365-Antiphishingrichtlinien ein.</span><span class="sxs-lookup"><span data-stu-id="94c1c-141">Set up Microsoft Defender for Office 365 anti-phishing policies.</span></span>
- <span data-ttu-id="94c1c-142">Implementieren sie sichere Anlagen.</span><span class="sxs-lookup"><span data-stu-id="94c1c-142">Implement Safe Attachments.</span></span>
- <span data-ttu-id="94c1c-143">Implementieren sicherer Links.</span><span class="sxs-lookup"><span data-stu-id="94c1c-143">Implement Safe Links.</span></span>
- <span data-ttu-id="94c1c-144">Implementieren von Richtlinien für die Erkennung und Reaktion auf Schadsoftware.</span><span class="sxs-lookup"><span data-stu-id="94c1c-144">Implement malware detection and response policies.</span></span>
- <span data-ttu-id="94c1c-145">Implementieren Sie ausgehende und eingehende Spamrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="94c1c-145">Implement outbound and inbound spam policies.</span></span>

### <a name="references"></a><span data-ttu-id="94c1c-146">Verweise:</span><span class="sxs-lookup"><span data-stu-id="94c1c-146">References:</span></span>

- [<span data-ttu-id="94c1c-147">Allgemeine Identitäts- und Gerätezugriffsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="94c1c-147">Common identity and device access policies</span></span>](../security/defender-365-security/identity-access-policies.md)
- [<span data-ttu-id="94c1c-148">Schutz vor Bedrohungen in Office 365</span><span class="sxs-lookup"><span data-stu-id="94c1c-148">Protect against threats in Office 365</span></span>](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [<span data-ttu-id="94c1c-149">Sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="94c1c-149">Safe Attachments</span></span>](../security/defender-365-security/safe-attachments.md)
- [<span data-ttu-id="94c1c-150">Sichere Links</span><span class="sxs-lookup"><span data-stu-id="94c1c-150">Safe Links</span></span>](../security/defender-365-security/safe-links.md)
- [<span data-ttu-id="94c1c-151">Sichere Dokumente</span><span class="sxs-lookup"><span data-stu-id="94c1c-151">Safe Documents</span></span>](../security/defender-365-security/safe-docs.md)
