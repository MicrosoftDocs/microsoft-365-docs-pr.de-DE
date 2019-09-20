---
title: 'Schritt 2: Konfigurieren der Klassifizierung für Ihre Umgebung'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen und Konfigurieren verschiedener Methoden zum Klassifizieren von Daten in Ihrer Organisation.
ms.openlocfilehash: ca1b4aefca7ee63f1c8fe098c115fc4f0074d9f6
ms.sourcegitcommit: 63e35b846d964dde5919a08c2fe432e749e8eff6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047298"
---
# <a name="step-2-configure-classification-for-your-environment"></a><span data-ttu-id="c28e8-103">Schritt 2: Konfigurieren der Klassifizierung für Ihre Umgebung</span><span class="sxs-lookup"><span data-stu-id="c28e8-103">Step 2: Configure classification for your environment</span></span>

<span data-ttu-id="c28e8-104">*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="c28e8-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="c28e8-105">In diesem Schritt arbeiten Sie mit der Rechts- und Complianceabteilung zusammen, um ein Klassifizierungsschema für die Daten in Ihrer Organisation zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c28e8-105">In this step, you work with your legal and compliance teams to define a classification scheme for your organization’s data.</span></span>

## <a name="microsoft-365-classification-types"></a><span data-ttu-id="c28e8-106">Microsoft 365 Klassifizierungstypen</span><span class="sxs-lookup"><span data-stu-id="c28e8-106">Microsoft 365 classification types</span></span>

<span data-ttu-id="c28e8-107">Microsoft 365 umfasst vier Typen von Klassifizierung:</span><span class="sxs-lookup"><span data-stu-id="c28e8-107">Microsoft 365 includes four types of classification:</span></span>

- <span data-ttu-id="c28e8-108">Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="c28e8-108">Sensitive information types</span></span>
- <span data-ttu-id="c28e8-109">Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="c28e8-109">Retention labels</span></span>
- <span data-ttu-id="c28e8-110">Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="c28e8-110">Sensitivity labels</span></span>
- <span data-ttu-id="c28e8-111">Bezeichnungen und Schutz in Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="c28e8-111">Azure Information Protection labels and protection</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="c28e8-112">Typen vertraulicher Informationen</span><span class="sxs-lookup"><span data-stu-id="c28e8-112">Sensitive information types</span></span>

<span data-ttu-id="c28e8-113">Typen vertraulicher Informationen für Microsoft 365 definieren, wie automatisierte Prozesse wie z. B. „Suche“ bestimmte Informationstypen erkennen.</span><span class="sxs-lookup"><span data-stu-id="c28e8-113">Sensitive information types for Microsoft 365 define how automated processes such as search recognize specific information types.</span></span> <span data-ttu-id="c28e8-114">Dazu gehören sensible Mitarbeiter- oder Kundendaten wie Nummern des Gesundheitsdiensts und Kreditkartennummern.</span><span class="sxs-lookup"><span data-stu-id="c28e8-114">These include sensitive employee or customer data such as health service numbers and credit card numbers.</span></span> <span data-ttu-id="c28e8-115">Sie verwenden die Typen sensibler Informationen, um sensible Daten zu finden und wenden DLP-Regeln und Richtlinien zum Schutz dieser Daten an.</span><span class="sxs-lookup"><span data-stu-id="c28e8-115">You use sensitive information types to find sensitive data and apply data loss prevention (DLP) rules and policies to protect this data.</span></span> <span data-ttu-id="c28e8-116">Weitere Informationen finden Sie unter [Was eine DLP-Richtlinie enthält](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains).</span><span class="sxs-lookup"><span data-stu-id="c28e8-116">For more information, see [what a DLP policy contains](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains).</span></span> 

<span data-ttu-id="c28e8-117">Typen vertraulicher Informationen sind besonders hilfreich, um Compliance- und Regulierungsanforderungen zu erfüllen, wie zum Beispiel die Datenschutz-Grundverordnung  (DSGVO).</span><span class="sxs-lookup"><span data-stu-id="c28e8-117">Sensitive information types are especially helpful for meeting compliance and regulation requirements, such as for the General Data Protection Regulation (GDPR).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="c28e8-118">Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="c28e8-118">Retention labels</span></span>

<span data-ttu-id="c28e8-119">Ein Teil der Definition einer Datenkontrolle-Strategie ist die Entscheidung, wie lange bestimmte Arten von Dokumenten oder Dokumente mit bestimmten Inhalten in Übereinstimmung mit den Organisationsrichtlinien und regionalen Vorschriften aufbewahrt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c28e8-119">Part of defining a data governance strategy is deciding how long specific types of documents or documents with specific contents should be retained in compliance with organization policies and regional regulations.</span></span> <span data-ttu-id="c28e8-120">Beispielsweise sollten einige Arten von Dokumenten für eine bestimmte Zeit aufbewahrt und dann gelöscht werden, während andere auf unbestimmte Zeit aufbewahrt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="c28e8-120">For example, some types of documents should be retained for a set amount of time and then deleted and others must be retained indefinitely.</span></span>

<span data-ttu-id="c28e8-121">Für Dokumente, die in Microsoft 365 gespeichert sind, definieren und wenden Sie Aufbewahrungsbezeichnungen auf Dokumente und Daten an, die in Exchange-E-Mails, SharePoint Online, OneDrive for Business und Teams gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="c28e8-121">For documents stored in Microsoft 365, you define and apply retention labels to documents and data stored in Exchange email, SharePoint Online, OneDrive for Business, and Teams chat and channel messages.</span></span> 

<span data-ttu-id="c28e8-122">Wenn Sie Aufbewahrungsbezeichnungen verwenden, sollten Sie für jede Kategorie von Dateien, für die eine Aufbewahrungsrichtlinie angewendet werden muss, eine Bezeichnung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c28e8-122">If you use retention labels, you should configure a label for each category of file that needs to have a retention policy applied.</span></span> <span data-ttu-id="c28e8-123">Innerhalb der Aufbewahrungskennzeichnung können Sie folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="c28e8-123">Within the retention label, you can specify:</span></span>

- <span data-ttu-id="c28e8-124">Eine Reihe von Deskriptoren für die Dateien (z.B. nach Fachabteilung, Dateityp oder Verordnung).</span><span class="sxs-lookup"><span data-stu-id="c28e8-124">A set of descriptors for the files (for example, by business department, file category, or regulation).</span></span>
- <span data-ttu-id="c28e8-125">Die Aufbewahrungseinstellungen für die Dateien, die mit der Aufbewahrungskennzeichnung versehen sind, wie z.B. Aufbewahrungszeiten und -verhalten nach Erreichen der Aufbewahrungszeit.</span><span class="sxs-lookup"><span data-stu-id="c28e8-125">The retention settings for the files that have the retention label attached, such as retain times and behaviors after the retain time has been reached.</span></span>

<span data-ttu-id="c28e8-126">Sie können Dateien auch automatisch mit einer Aufbewahrungsbezeichnung versehen, indem Sie eine SharePoint Online-Site so konfigurieren, dass alle neuen Dokumente in der Site mit einer Standard-Aufbewahrungsbezeichnung versehen werden.</span><span class="sxs-lookup"><span data-stu-id="c28e8-126">You can also apply a retention label to files automatically by configuring a SharePoint Online site to apply a default retention label to all new documents in the site.</span></span> 

<span data-ttu-id="c28e8-127">Weitere Informationen finden Sie unter [Übersicht zu Aufbewahrungsbezeichnungen](https://docs.microsoft.com/office365/securitycompliance/labels).</span><span class="sxs-lookup"><span data-stu-id="c28e8-127">For more information, see the [overview of retention labels](https://docs.microsoft.com/office365/securitycompliance/labels).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="c28e8-128">Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="c28e8-128">Sensitivity labels</span></span>

<span data-ttu-id="c28e8-129">Zum Schutz und zur Implementierung der Sicherheit für bestimmte Arten von Dokumenten oder Dokumenten mit bestimmten Inhalten gehört es, diese mit einer Bezeichnung zu versehen, damit die zusätzliche Sicherheit angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c28e8-129">Part of protecting and implementing security for specific types of documents or documents with specific contents is marking them with a label so that the additional security can be applied.</span></span> <span data-ttu-id="c28e8-130">Mit Vertraulichkeitsbezeichnungen in Microsoft 365 können Sie:</span><span class="sxs-lookup"><span data-stu-id="c28e8-130">With sensitivity labels in Microsoft 365, you can:</span></span>

- <span data-ttu-id="c28e8-131">Erzwingen von Schutzeinstellungen, wie Verschlüsselung, Berechtigungen oder das Hinzufügen eines Wasserzeichens.</span><span class="sxs-lookup"><span data-stu-id="c28e8-131">Enforce protection settings such as encryption, permissions, or adding a watermark.</span></span>
- <span data-ttu-id="c28e8-132">Verwenden von Windows Information Protection (WIP) Endpoint Protection, um zu verhindern, dass Inhalte in eine Drittanbieteranwendung wie Twitter oder Gmail kopiert oder auf einen Wechselspeicher wie ein USB-Laufwerk kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="c28e8-132">Use Windows Information Protection (WIP) endpoint protection to prevent that content from being copied to a third-party app, such as Twitter or Gmail, or being copied to removable storage, such as a USB drive.</span></span>
- <span data-ttu-id="c28e8-133">Verwenden von Microsoft Cloud App Security (CAS) zum Schutz von Inhalten in Anwendungen und Diensten von Drittanbietern.</span><span class="sxs-lookup"><span data-stu-id="c28e8-133">Use Microsoft Cloud App Security to protect content in third-party apps and services.</span></span> 
- <span data-ttu-id="c28e8-134">Klassifizieren von Inhalten ohne Verwendung von Schutzeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="c28e8-134">Classify content without using any protection settings.</span></span>

<span data-ttu-id="c28e8-135">Wenn Sie Vertraulichkeitsbezeichnungen verwenden, sollten Sie für jede Sicherheits- und Information Protection-Stufe eine Bezeichnung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c28e8-135">If you use sensitivity labels, you should configure a label for each security and information protection level.</span></span> <span data-ttu-id="c28e8-136">Beispielsweise, können Sie drei Vertraulichkeitsbezeichnungen erstellen für:</span><span class="sxs-lookup"><span data-stu-id="c28e8-136">For example, create three sensitivity labels for:</span></span>

- <span data-ttu-id="c28e8-137">Baseline</span><span class="sxs-lookup"><span data-stu-id="c28e8-137">Baseline</span></span>
- <span data-ttu-id="c28e8-138">Vertraulich</span><span class="sxs-lookup"><span data-stu-id="c28e8-138">Sensitive</span></span>
- <span data-ttu-id="c28e8-139">Streng geregelt</span><span class="sxs-lookup"><span data-stu-id="c28e8-139">Highly regulated</span></span>

<span data-ttu-id="c28e8-140">Wenn Sie Dateien mit stark regulierten Daten auf einer SharePoint Online-Website speichern und möchten, dass diese Dateien auch bei Verlassen der Website über dieselben Berechtigungen wie die Website verfügen, müssen Sie eine zusätzliche Vertraulichkeitsbezeichnung erstellen, deren Berechtigungen mit denjenigen der Website identisch sind.</span><span class="sxs-lookup"><span data-stu-id="c28e8-140">If you store files with highly regulated data in a SharePoint Online site and want those files to have the same permissions as the site if the files leave the site, you need to create an additional sensitivity label whose permissions are the same as the site.</span></span>

<span data-ttu-id="c28e8-141">Weitere Informationen finden Sie unter [Übersicht über Vertraulichkeitsbezeichnungen](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels).</span><span class="sxs-lookup"><span data-stu-id="c28e8-141">For more information, see this [overview of sensitivity labels](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels).</span></span>

### <a name="azure-information-protection-labels-and-protection"></a><span data-ttu-id="c28e8-142">Bezeichnungen und Schutz in Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="c28e8-142">Azure Information Protection labels and protection</span></span>

<span data-ttu-id="c28e8-143">Sie können die Azure Information Protection-Bezeichnungen verwenden, um die Dokumente und E-Mails Ihrer Organisation zu klassifizieren und optional zu schützen.</span><span class="sxs-lookup"><span data-stu-id="c28e8-143">You can use Azure Information Protection labels to classify, and optionally protect, your organization’s documents and emails.</span></span> <span data-ttu-id="c28e8-144">Diese Bezeichnungen können sich auf Dokumente anwenden, die außerhalb von Microsoft 365 gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="c28e8-144">These labels can apply to documents that are stored outside of Microsoft 365.</span></span> <span data-ttu-id="c28e8-145">Diese Bezeichnungen können von Administratoren, die Regeln und Bedingungen definieren, automatisch angewendet werden, von Benutzern manuell oder in einer Kombination, bei der den Benutzern Empfehlungen gegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c28e8-145">These labels can be applied automatically by administrators who define rules and conditions, manually by users, or a combination where users are given recommendations.</span></span>

<span data-ttu-id="c28e8-146">Gehen Sie zum Planen und Bereitstellen von Bezeichnungen und Schutz in Azure Information Protection folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="c28e8-146">To plan and deploy Azure Information Protection labels and protection, do the following:</span></span>

1. <span data-ttu-id="c28e8-147">Überprüfen der [Anforderungen für Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span><span class="sxs-lookup"><span data-stu-id="c28e8-147">Review the [requirements for Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span></span>
2. <span data-ttu-id="c28e8-148">Befolgen der [Roadmap für die Bereitstellung von Klassifizierung, Bezeichnung und Schutz](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span><span class="sxs-lookup"><span data-stu-id="c28e8-148">Follow the [deployment roadmap for classification, labeling, and protection](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span></span>

<span data-ttu-id="c28e8-149">Weitere Informationen finden Sie in der [Bibliothek mit der Azure Information Protection-Dokumentation](https://docs.microsoft.com/information-protection/).</span><span class="sxs-lookup"><span data-stu-id="c28e8-149">For more information, see the [library of Azure Information Protection documentation](https://docs.microsoft.com/information-protection/).</span></span>

<span data-ttu-id="c28e8-150">Bestehende Azure Information Protection Bezeichnungen arbeiten nahtlos mit Vertraulichkeitsbezeichnungen zusammen.</span><span class="sxs-lookup"><span data-stu-id="c28e8-150">Existing Azure Information Protection labels work seamlessly with sensitivity labels.</span></span> <span data-ttu-id="c28e8-151">Beispielsweise können Sie Ihre vorhandenen Azure Information Protection-Bezeichnungen sowie die Bezeichnungen, die auf Dokumente und E-Mails angewendet werden, beibehalten.</span><span class="sxs-lookup"><span data-stu-id="c28e8-151">For example, you can keep your existing Azure Information Protection labels and the labels that are applied to documents and email.</span></span>

<span data-ttu-id="c28e8-152">Wenn Sie sowohl über Vertraulichkeits- als auch über Azure Information Protection-Bezeichnungen verfügen, sollten Sie Ihre[Azure Information Protection-Bezeichnungen auf Vertraulichkeitsbezeichnungen migrieren](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#how-sensitivity-labels-work-with-existing-azure-information-protection-labels). </span><span class="sxs-lookup"><span data-stu-id="c28e8-152">If you have both sensitivity and Azure Information Protection labels, you should [migrate your Azure Information Protection labels to sensitivity labels](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#how-sensitivity-labels-work-with-existing-azure-information-protection-labels).</span></span>

## <a name="example-classification-for-gdpr"></a><span data-ttu-id="c28e8-153">Beispiel: Klassifizierung für die DSGVO</span><span class="sxs-lookup"><span data-stu-id="c28e8-153">Example: Classification for GDPR</span></span>

<span data-ttu-id="c28e8-154">Ein Beispiel für ein Klassifizierungsschema, das personenbezogene Daten für die DSGVO enthält, finden Sie unter [Entwerfen eines Klassifikationsschemas für personenbezogene Daten](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span><span class="sxs-lookup"><span data-stu-id="c28e8-154">For an example classification scheme that includes personal data for GDPR, see [Architect a classification schema for personal data](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span></span>

## <a name="take-it-for-a-test-drive"></a><span data-ttu-id="c28e8-155">Probieren Sie es aus</span><span class="sxs-lookup"><span data-stu-id="c28e8-155">Take it for a test drive</span></span>

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="c28e8-157">Testumgebungsanleitung: Klassifizierung von Daten</span><span class="sxs-lookup"><span data-stu-id="c28e8-157">Test Lab Guide: Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

<span data-ttu-id="c28e8-158">Als Zwischenprüfung können Sie die [Beendigungskriterien](infoprotect-exit-criteria.md#crit-infoprotect-step2) für diesen Schritt betrachten.</span><span class="sxs-lookup"><span data-stu-id="c28e8-158">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step2) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="c28e8-159">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="c28e8-159">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[<span data-ttu-id="c28e8-160">Konfigurieren der erhöhten Sicherheit für Office 365</span><span class="sxs-lookup"><span data-stu-id="c28e8-160">Configure increased security for Office 365</span></span>](infoprotect-configure-increased-security-office-365.md)|

