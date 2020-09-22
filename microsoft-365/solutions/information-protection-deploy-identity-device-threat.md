---
title: Verwenden von Identitäts-, Geräte-und Bedrohungsschutz für die Datenschutzverordnung
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
ms.custom: ''
description: Verhindern von Verletzungen personenbezogener Daten mit Identitäts-, Geräte-und Bedrohungsschutz Diensten von Microsoft 365.
ms.openlocfilehash: a0efdcfe8e9d27e19b6cf1355a6d0943b7cdaa59
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195663"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="ee0bc-103">Verwenden von Identitäts-, Geräte-und Bedrohungsschutz für die Datenschutzverordnung</span><span class="sxs-lookup"><span data-stu-id="ee0bc-103">Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="ee0bc-104">Microsoft 365 bietet eine Reihe von Funktionen für Identitäts-, Geräte-und Bedrohungsschutz, die von Organisationen eingesetzt werden können, um die Einhaltung von Datenschutzbestimmungen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ee0bc-104">Microsoft 365 provides a number of identity, device, and threat protection capabilities that organizations can employ to help comply with data privacy-related compliance regulations.</span></span> <span data-ttu-id="ee0bc-105">In diesem Artikel wird beschrieben, was die Datenschutzbestimmungen in diesen Bereichen erfordern und enthält eine Liste der zugehörigen Microsoft 365-Features und-Dienste mit Links zu weiteren Informationen, die Ihnen dabei helfen, die Implementierungsanforderungen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="ee0bc-105">This article describes what the data privacy regulations require in these areas and provides a listing of related Microsoft 365 features and services with links to more information to help you address implementation requirements.</span></span>

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a><span data-ttu-id="ee0bc-106">Wie Identitäts-, Geräte-und Bedrohungsschutz mit der Datenschutzverordnung in Zusammenhangstehen</span><span class="sxs-lookup"><span data-stu-id="ee0bc-106">How identity, device, and threat protection relate to data privacy regulation</span></span>

<span data-ttu-id="ee0bc-107">Während die Datenschutzbestimmungen sich in ihrer Besonderheit unterscheiden, ist die Essenz dessen, was Sie bezeichnen, im dsgvo-Artikel 5 (1) (f) aufgeführt, in dem Folgendes heißt:</span><span class="sxs-lookup"><span data-stu-id="ee0bc-107">While the data privacy regulations vary in their specificity, the essence of what they call for is embodied in the GDPR’s Article 5(1)(f), which states that:</span></span> 

- <span data-ttu-id="ee0bc-108">Personenbezogene Daten werden in einer Weise verarbeitet, die eine angemessene Sicherheit der personenbezogenen Daten einschließlich des Schutzes vor unbefugter oder unrechtmäßiger Verarbeitung sowie vor versehentlichem Verlust, Zerstörung oder Beschädigung durch geeignete technische oder organisatorische Maßnahmen ("Integrität und Vertraulichkeit") gewährleistet.</span><span class="sxs-lookup"><span data-stu-id="ee0bc-108">Personal data shall be processed in a manner that ensures appropriate security of the personal data, including protection against unauthorized or unlawful processing and against accidental loss, destruction or damage, using appropriate technical or organizational measures ('integrity and confidentiality').</span></span>

<span data-ttu-id="ee0bc-109">Da Verletzungen von personenbezogenen Daten häufig durch Administrator-oder Endbenutzerkonto Kompromisse und böswilligen Systemzugriff verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="ee0bc-109">Because personal data breaches are often caused by administrative or end-user account compromise and malicious system access.</span></span> <span data-ttu-id="ee0bc-110">Beispielsweise kann ein Administratorkonto-hacken dazu führen, dass Kundenkreditkartennummern oder andere persönliche Informationen ausgefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="ee0bc-110">For example, an admin account hack can result in exfiltration of customer credit card numbers or other personal information.</span></span> <span data-ttu-id="ee0bc-111">Der in Microsoft 365 allgemein empfohlene Identitäts-, Geräte-und Bedrohungsschutz sollte möglicherweise implementiert werden, was sich in der Konformitätsbewertung im Compliance-Manager widerspiegelt.</span><span class="sxs-lookup"><span data-stu-id="ee0bc-111">All the generally advisable identity, device, and threat protection available with Microsoft 365 potentially should be implemented, which will be reflected in your compliance score, found in Compliance Manager.</span></span>

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a><span data-ttu-id="ee0bc-112">Verwenden der Ergebnisse ihrer Assessment Work and Compliance Manager</span><span class="sxs-lookup"><span data-stu-id="ee0bc-112">Using the results of your assessment work and Compliance Manager</span></span>

<span data-ttu-id="ee0bc-113">Compliance-Manager umfasst Identitäts-, Geräte-und Bedrohungsschutz mithilfe dieser Kategorien:</span><span class="sxs-lookup"><span data-stu-id="ee0bc-113">Compliance Manager includes identity, device, and threat protection using these categories:</span></span>

- <span data-ttu-id="ee0bc-114">Identity entspricht der **Steuerelement Zugriffs** Kategorie</span><span class="sxs-lookup"><span data-stu-id="ee0bc-114">Identity corresponds to the **Control Access** category</span></span>
- <span data-ttu-id="ee0bc-115">Gerät entspricht der Kategorie " **Geräte verwalten** "</span><span class="sxs-lookup"><span data-stu-id="ee0bc-115">Device corresponds to the **Manage Devices** category</span></span>
- <span data-ttu-id="ee0bc-116">Bedrohungsschutz entspricht der Kategorie " **Schutz vor Bedrohungen** "</span><span class="sxs-lookup"><span data-stu-id="ee0bc-116">Threat protection corresponds to the **Protect Against Threats** category</span></span>
 
<span data-ttu-id="ee0bc-117">Wenn diese in unserem Beispielsatz mit vier wichtigen Datenschutzbestimmungen ausgewählt wurden, gibt Compliance-Manager 90 Verbesserungs Aktionen an, von denen die meisten eine "27" erzielt haben.</span><span class="sxs-lookup"><span data-stu-id="ee0bc-117">If these are selected across our sample set of four major data privacy regulations, Compliance Manager specifies 90 improvement actions, most of which are scored a "27".</span></span> <span data-ttu-id="ee0bc-118">Da eine solche große Zahl vom Compliance-Manager für diese Kategorien aufgerufen wird, werden einige der häufigsten hier aufgeführten als Referenz aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="ee0bc-118">Since such a large number are called out by Compliance Manager for these categories, some of the more common ones are listed here, for reference.</span></span>

<span data-ttu-id="ee0bc-119">Verwenden Sie [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) für Identity und die Kategorie **Steuerelement Zugriff** , mit der Sie folgende Möglichkeiten haben:</span><span class="sxs-lookup"><span data-stu-id="ee0bc-119">Use [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) for identity and the **Control Access** category, with which you can:</span></span>

- <span data-ttu-id="ee0bc-120">Implementieren der Wiedergabe-resistenten Authentifizierung (um "Menschen in der Mitte"-Angriffe zu verhindern)</span><span class="sxs-lookup"><span data-stu-id="ee0bc-120">Implement replay-resistant authentication (to prevent “Man in the middle” attacks)</span></span>
- <span data-ttu-id="ee0bc-121">Blockieren Sie die Legacyauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="ee0bc-121">Block legacy authentication.</span></span>
- <span data-ttu-id="ee0bc-122">Konfigurieren von Risikorichtlinien für Benutzer Risiken und Benutzeranmeldungen</span><span class="sxs-lookup"><span data-stu-id="ee0bc-122">Configure user risk and user sign-in risk policies.</span></span>
- <span data-ttu-id="ee0bc-123">Aktivieren Sie den bedingten Zugriff und die mehrstufige Authentifizierung (MFA) für Administratoren und nicht-Administratoren.</span><span class="sxs-lookup"><span data-stu-id="ee0bc-123">Enable Conditional Access and multi-factor authentication (MFA) for admins and non-admins.</span></span>
- <span data-ttu-id="ee0bc-124">Konfigurieren und Erzwingen von Kennwortrichtlinien</span><span class="sxs-lookup"><span data-stu-id="ee0bc-124">Configure and enforce password policies.</span></span>
- <span data-ttu-id="ee0bc-125">Einschränken des Zugriffs auf privilegierte Konten mit Azure AD privilegierten Identitätsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="ee0bc-125">Restrict access to privileged accounts with Azure AD Privileged Identity Management.</span></span>
- <span data-ttu-id="ee0bc-126">Zugriff beim Beenden deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="ee0bc-126">Disable access upon termination.</span></span>
- <span data-ttu-id="ee0bc-127">Überwachen von Benutzerkonten und Statusänderungen.</span><span class="sxs-lookup"><span data-stu-id="ee0bc-127">Audit user accounts and status changes.</span></span>
- <span data-ttu-id="ee0bc-128">Überprüfen Sie die Rollengruppe und die administrativen Änderungen.</span><span class="sxs-lookup"><span data-stu-id="ee0bc-128">Review role group and administrative changes.</span></span>

<span data-ttu-id="ee0bc-129">Verwenden Sie [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) für Geräte und die Kategorie **Manage Devices** , mit der Sie folgende Möglichkeiten haben:</span><span class="sxs-lookup"><span data-stu-id="ee0bc-129">Use [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) for devices and the **Manage Devices** category, with which you can:</span></span>

- <span data-ttu-id="ee0bc-130">Gesperrte beschädigte und verwurzelte Mobile Geräte blockieren.</span><span class="sxs-lookup"><span data-stu-id="ee0bc-130">Block jail broken and rooted mobile devices.</span></span>
- <span data-ttu-id="ee0bc-131">Konfigurieren von InTune für die Verwaltung mobiler Geräte.</span><span class="sxs-lookup"><span data-stu-id="ee0bc-131">Configure Intune for mobile device management.</span></span>
- <span data-ttu-id="ee0bc-132">Erstellen Sie Konformitätsrichtlinien für Android-, Ios-, macOS-und Windows-Geräte.</span><span class="sxs-lookup"><span data-stu-id="ee0bc-132">Create compliance policies for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="ee0bc-133">Erstellen Sie ein Geräte Konfigurationsprofil für Android-, Ios-, macOS-und Windows-Geräte.</span><span class="sxs-lookup"><span data-stu-id="ee0bc-133">Create a device configuration profile for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="ee0bc-134">Erstellen von App-Schutzrichtlinien für IOS und Windows.</span><span class="sxs-lookup"><span data-stu-id="ee0bc-134">Create app protection policies for iOS and Windows.</span></span>
- <span data-ttu-id="ee0bc-135">Informationen mit Sperrbildschirm verbergen.</span><span class="sxs-lookup"><span data-stu-id="ee0bc-135">Conceal information with lock screen.</span></span>
- <span data-ttu-id="ee0bc-136">Implementieren von Kennwortrichtlinien für mobile Geräte.</span><span class="sxs-lookup"><span data-stu-id="ee0bc-136">Implement password policies for mobile devices.</span></span>
- <span data-ttu-id="ee0bc-137">Erfordern, dass Mobile Geräte nach Inaktivität sperren.</span><span class="sxs-lookup"><span data-stu-id="ee0bc-137">Require mobile devices to lock upon inactivity.</span></span>
- <span data-ttu-id="ee0bc-138">Erfordern, dass Mobile Geräte bei mehreren Anmeldefehlern gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="ee0bc-138">Require mobile devices to wipe on multiple sign-in failures.</span></span>

<span data-ttu-id="ee0bc-139">Verwenden Sie [Exchange Online Schutz und Office 365 Advanced Threat Protection (ATP)](../security/office-365-security/office-365-atp.md) für die Kategorie **Protect Against Threats** , mit der Sie folgende Schritte durchführen können:</span><span class="sxs-lookup"><span data-stu-id="ee0bc-139">Use [Exchange Online Protection and Office 365 Advanced Threat Protection (ATP)](../security/office-365-security/office-365-atp.md) for the **Protect Against Threats** category, with which you can:</span></span>

- <span data-ttu-id="ee0bc-140">Aktivieren Sie die Sender Authentifizierung (SPF, DMARC und DKIM).</span><span class="sxs-lookup"><span data-stu-id="ee0bc-140">Enable sender authentication (SPF, DMARC and DKIM).</span></span>
- <span data-ttu-id="ee0bc-141">Richten Sie Office 365 Anti-Phishing-Richtlinien für Advanced Threat Protection (ATP) ein.</span><span class="sxs-lookup"><span data-stu-id="ee0bc-141">Set up Office 365 Advanced Threat Protection (ATP) anti-phishing policies.</span></span>
- <span data-ttu-id="ee0bc-142">Implementieren Sie ATP-sichere Anlagen.</span><span class="sxs-lookup"><span data-stu-id="ee0bc-142">Implement ATP Safe Attachments.</span></span>
- <span data-ttu-id="ee0bc-143">Implementieren Sie ATP-sichere Links.</span><span class="sxs-lookup"><span data-stu-id="ee0bc-143">Implement ATP Safe Links.</span></span>
- <span data-ttu-id="ee0bc-144">Implementieren von Malware Erkennungs-und-Antwort Richtlinien</span><span class="sxs-lookup"><span data-stu-id="ee0bc-144">Implement malware detection and response policies.</span></span>
- <span data-ttu-id="ee0bc-145">Implementieren Sie ausgehende und eingehende Spam Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="ee0bc-145">Implement outbound and inbound spam policies.</span></span>

### <a name="references"></a><span data-ttu-id="ee0bc-146">Referenzen</span><span class="sxs-lookup"><span data-stu-id="ee0bc-146">References:</span></span>

- [<span data-ttu-id="ee0bc-147">Allgemeine Identitäts- und Gerätezugriffsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="ee0bc-147">Common identity and device access policies</span></span>](../enterprise/identity-access-policies.md)
- [<span data-ttu-id="ee0bc-148">Schutz vor Bedrohungen in Office 365</span><span class="sxs-lookup"><span data-stu-id="ee0bc-148">Protect against threats in Office 365</span></span>](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [<span data-ttu-id="ee0bc-149">Sichere Anlagen in ATP</span><span class="sxs-lookup"><span data-stu-id="ee0bc-149">ATP Safe Attachments</span></span>](../security/office-365-security/atp-safe-attachments.md)
- [<span data-ttu-id="ee0bc-150">ATP-sichere Links</span><span class="sxs-lookup"><span data-stu-id="ee0bc-150">ATP Safe Links</span></span>](../security/office-365-security/atp-safe-links.md)
- [<span data-ttu-id="ee0bc-151">Sichere Dokumente in ATP</span><span class="sxs-lookup"><span data-stu-id="ee0bc-151">ATP Safe Documents</span></span>](../security/office-365-security/safe-docs.md)
