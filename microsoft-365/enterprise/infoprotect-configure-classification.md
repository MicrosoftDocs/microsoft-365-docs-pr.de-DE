---
title: 'Schritt 3: Konfigurieren der Klassifizierung für Ihre Umgebung'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen und Konfigurieren verschiedener Methoden zum Klassifizieren von Daten in Ihrer Organisation.
ms.openlocfilehash: a9fc2a1394c9fb7f32c8dcbb754cb529ba06a71a
ms.sourcegitcommit: df0ed4e9097acfee3cb128882102b3081144eb68
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2018
ms.locfileid: "23938610"
---
# <a name="step-3-configure-classification-for-your-environment"></a><span data-ttu-id="77f6c-103">Schritt 3: Konfigurieren der Klassifizierung für Ihre Umgebung</span><span class="sxs-lookup"><span data-stu-id="77f6c-103">Step 3: Configure classification for your environment</span></span>

<span data-ttu-id="77f6c-104">*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="77f6c-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="77f6c-105">In Schritt 3 arbeiten Sie mit der Rechts- und Complianceabteilung zusammen, um ein Klassifizierungsschema für die Daten in Ihrer Organisation zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="77f6c-105">In Step 3, you work with your legal and compliance teams to define a classification scheme for your organization’s data.</span></span>

## <a name="microsoft-classifications"></a><span data-ttu-id="77f6c-106">Microsoft-Klassifizierungen</span><span class="sxs-lookup"><span data-stu-id="77f6c-106">Microsoft classifications</span></span>

<span data-ttu-id="77f6c-107">Microsoft 365 umfasst drei Typen von Klassifizierung:</span><span class="sxs-lookup"><span data-stu-id="77f6c-107">Microsoft 365 includes three types of classification:</span></span>

- <span data-ttu-id="77f6c-108">Typen vertraulicher Informationen für Office 365</span><span class="sxs-lookup"><span data-stu-id="77f6c-108">Sensitive information types for Office 365</span></span>
- <span data-ttu-id="77f6c-109">Office 365-Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="77f6c-109">Office 365 labels</span></span>
- <span data-ttu-id="77f6c-110">Bezeichnungen und Schutz in Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="77f6c-110">Azure Information Protection labels and protection</span></span>

### <a name="sensitive-information-types-for-office-365"></a><span data-ttu-id="77f6c-111">Typen vertraulicher Informationen für Office 365</span><span class="sxs-lookup"><span data-stu-id="77f6c-111">Sensitive information types for Office 365</span></span>

<span data-ttu-id="77f6c-p101">Typen vertraulicher Informationen für Office 365 definieren wie automatisierte Prozesse, z. B. die Suche, bestimmte Informationstypen erkennen, z. B. Health Service-Nummern und Kreditkartennummern. Verwenden Sie Typen vertraulicher Informationen für die Suche nach vertraulichen Daten und zum Anwenden von DLP-Regeln und -Richtlinien zum Schutz dieser Daten. Weitere Informationen finden Sie unter [Überblick über DLP-Richtlinien](https://support.office.com/article/overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e). Typen vertraulicher Informationen sind besonders hilfreich, um Compliance- und gesetzliche Anforderungen zu erfüllen, z. B. die Datenschutz-Grundverordnung (DSGVO).</span><span class="sxs-lookup"><span data-stu-id="77f6c-p101">Sensitive information types for Office 365 define how automated processes such as search recognize specific information types such as health service numbers and credit card numbers. You use sensitive information types to find sensitive data and apply data loss prevention rules and policies to protect this data. For more information, see [Overview of data loss prevention policies](https://support.office.com/article/overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e). For example, sensitive information types are especially helpful for meeting compliance and regulation requirements, such as for the General Data Protection Regulation (GDPR).</span></span>

### <a name="office-365-labels"></a><span data-ttu-id="77f6c-116">Office 365-Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="77f6c-116">Office 365 labels</span></span>
<span data-ttu-id="77f6c-p102">Sie können Office 365-Bezeichnungen für persönliche Daten und streng geregelte Dateien und Dateien mit Betriebsgeheimnissen verwenden, die in SharePoint Online und OneDrive for Business gespeichert sind. Weitere Informationen, darunter Schritte zum Erstellen, finden Sie unter [Übersicht über Bezeichnungen](https://support.office.com/article/overview-of-labels-af398293-c69d-465e-a249-d74561552d30).</span><span class="sxs-lookup"><span data-stu-id="77f6c-p102">You can use Office 365 labels for personal data and for highly regulated and trade secret files stored in SharePoint Online and OneDrive for Business. For more information, including how to create them, see [Overview of labels](https://support.office.com/article/overview-of-labels-af398293-c69d-465e-a249-d74561552d30).</span></span>

<span data-ttu-id="77f6c-p103">Wenn Sie beschließen, Office 365-Bezeichnungen zu verwenden, sollten Sie mindestens eine für jede Schutzebene konfigurieren. Erstellen Sie beispielsweise drei Bezeichnungen für:</span><span class="sxs-lookup"><span data-stu-id="77f6c-p103">If you decide to use Office 365 labels, you should configure at least one for each level of protection. For example, create three labels for:</span></span>

- <span data-ttu-id="77f6c-121">Baseline</span><span class="sxs-lookup"><span data-stu-id="77f6c-121">Baseline</span></span>
- <span data-ttu-id="77f6c-122">Vertraulich</span><span class="sxs-lookup"><span data-stu-id="77f6c-122">Sensitive</span></span>
- <span data-ttu-id="77f6c-123">Streng geregelt</span><span class="sxs-lookup"><span data-stu-id="77f6c-123">Highly regulated</span></span>

### <a name="azure-information-protection-labels-and-protection"></a><span data-ttu-id="77f6c-124">Bezeichnungen und Schutz in Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="77f6c-124">Azure Information Protection labels and protection</span></span>

<span data-ttu-id="77f6c-p104">Sie können Azure Information Protection-Bezeichnungen zum Klassifizieren und für optionalen Schutz von Dokumenten und E-Mails in Ihrer Organisation verwenden. Diese Bezeichnungen können auf Dokumente angewendet werden, die außerhalb von Office 365 gespeichert sind. Diese Bezeichnungen können von Administratoren, die Regeln und Kriterien definieren, automatisch angewendet, manuell durch einen Benutzer oder eine Kombination aus beiden angewendet werden, indem Benutzern Empfehlungen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="77f6c-p104">You can use Azure Information Protection labels to classify, and optionally protect, your organization’s documents and emails. These labels can apply to documents that are stored outside of Office 365. These labels can be applied automatically by administrators who define rules and conditions, manually by users, or a combination where users are given recommendations.</span></span>

<span data-ttu-id="77f6c-128">Gehen Sie zum Planen und Bereitstellen von Bezeichnungen und Schutz in Azure Information Protection folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="77f6c-128">To plan and deploy Azure Information Protection labels and protection, do the following:</span></span>

1. <span data-ttu-id="77f6c-129">Überprüfen der [Anforderungen für Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span><span class="sxs-lookup"><span data-stu-id="77f6c-129">Review the [requirements for Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).</span></span>
2. <span data-ttu-id="77f6c-130">Befolgen der [Roadmap für die Bereitstellung von Klassifizierung, Bezeichnung und Schutz](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span><span class="sxs-lookup"><span data-stu-id="77f6c-130">Follow the [deployment roadmap for classification, labeling, and protection](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).</span></span>

<span data-ttu-id="77f6c-131">Weitere Informationen finden Sie in der [Bibliothek mit der Azure Information Protection-Dokumentation](https://docs.microsoft.com/information-protection/).</span><span class="sxs-lookup"><span data-stu-id="77f6c-131">For more information, see the [library of Azure Information Protection documentation](https://docs.microsoft.com/information-protection/).</span></span>

## <a name="classification-for-gdpr"></a><span data-ttu-id="77f6c-132">Klassifizierung für die DSGVO</span><span class="sxs-lookup"><span data-stu-id="77f6c-132">Classification for GDPR</span></span>

<span data-ttu-id="77f6c-133">Ein Beispiel für ein Klassifizierungsschema, das personenbezogene Daten für die DSGVO enthält, finden Sie unter [Entwerfen eines Klassifikationsschemas für personenbezogene Daten](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span><span class="sxs-lookup"><span data-stu-id="77f6c-133">For an example classification scheme that includes personal data for GDPR, see [Architect a classification schema for personal data](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).</span></span>

## <a name="results"></a><span data-ttu-id="77f6c-134">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="77f6c-134">Results</span></span>

<span data-ttu-id="77f6c-135">Sie haben Folgendes bestimmt:</span><span class="sxs-lookup"><span data-stu-id="77f6c-135">You've determined:</span></span>

- <span data-ttu-id="77f6c-136">Typen vertraulicher Daten</span><span class="sxs-lookup"><span data-stu-id="77f6c-136">Sensitive data types</span></span>
- <span data-ttu-id="77f6c-137">Office 365-Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="77f6c-137">Office 365 labels</span></span>
- <span data-ttu-id="77f6c-138">Bezeichnungen, Schutzrichtlinien und Bedingungen in Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="77f6c-138">Azure Information Protection labels and protection rules and conditions</span></span>

<span data-ttu-id="77f6c-139">Als Zwischenprüfung können Sie die [Beendigungskriterien](infoprotect-exit-criteria.md#crit-infoprotect-step3) für diesen Schritt betrachten.</span><span class="sxs-lookup"><span data-stu-id="77f6c-139">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step3) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="77f6c-140">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="77f6c-140">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)|[<span data-ttu-id="77f6c-141">Konfigurieren der erhöhten Sicherheit für Office 365</span><span class="sxs-lookup"><span data-stu-id="77f6c-141">Configure increased security for Office 365</span></span>](infoprotect-configure-increased-security-office-365.md)|

