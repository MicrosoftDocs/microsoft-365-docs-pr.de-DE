---
title: Beendigungskriterien für die Information Protection-Infrastruktur
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Informieren Sie sich über die Kriterien für Information Protection-basierte Dienste und -Infrastruktur, um sicherzustellen, dass Ihre Konfiguration die Anforderungen von Microsoft 365Enterprise erfüllt.
ms.openlocfilehash: 9c74a3994a1a404583326f65f1cec579fccbe659
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400039"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="a1ac3-103">Beendigungskriterien für die Information Protection-Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="a1ac3-103">Information protection infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="a1ac3-104">Stellen Sie sicher, dass Ihre Information Protection-Infrastruktur die folgenden erforderlichen Kriterien erfüllt, und dass Sie die optionalen Kriterien berücksichtigt haben.</span><span class="sxs-lookup"><span data-stu-id="a1ac3-104">Make sure your information protection infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="a1ac3-105">Erforderlich: Sicherheits- und Information Protection-Stufen sind für Ihre Organisation definiert</span><span class="sxs-lookup"><span data-stu-id="a1ac3-105">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="a1ac3-p101">Sie haben die Planung und Definition der Sicherheitsstufen abgeschlossen, die Ihre Organisation benötigt. Diese Stufen definieren ein Mindestmaß an Sicherheit sowie zusätzliche Sicherheitsstufen für zunehmend vertrauliche Informationen und die erforderliche Datensicherheit.</span><span class="sxs-lookup"><span data-stu-id="a1ac3-p101">You've planned for and determined the security levels that your organization needs. These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="a1ac3-108">Sie verwenden mindestens drei Sicherheitsstufen:</span><span class="sxs-lookup"><span data-stu-id="a1ac3-108">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="a1ac3-109">Baseline</span><span class="sxs-lookup"><span data-stu-id="a1ac3-109">Baseline</span></span>
- <span data-ttu-id="a1ac3-110">Vertraulich</span><span class="sxs-lookup"><span data-stu-id="a1ac3-110">Sensitive</span></span>
- <span data-ttu-id="a1ac3-111">Streng geregelt</span><span class="sxs-lookup"><span data-stu-id="a1ac3-111">Highly regulated</span></span>

<span data-ttu-id="a1ac3-112">Gegebenenfalls hilft Ihnen [Schritt 1](infoprotect-define-sec-infoprotect-levels.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="a1ac3-112">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a><span data-ttu-id="a1ac3-113">Erforderlich: Erhöhte Sicherheit für Microsoft 365 ist konfiguriert</span><span class="sxs-lookup"><span data-stu-id="a1ac3-113">Required: Increased security for Microsoft 365 is configured</span></span>

<span data-ttu-id="a1ac3-114">Sie haben die folgenden Einstellungen für [höhere Sicherheit von Office 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security) konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="a1ac3-114">You've configured the following settings for [Office 365 increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span></span>

- <span data-ttu-id="a1ac3-115">Richtlinien für die Bedrohungsverwaltung im Microsoft 365 Security Center</span><span class="sxs-lookup"><span data-stu-id="a1ac3-115">Threat management policies in the Microsoft 365 security Center</span></span>
- <span data-ttu-id="a1ac3-116">Zusätzliche mandantenweite Exchange Online-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="a1ac3-116">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="a1ac3-117">Mandantenweite Freigaberichtlinien im SharePoint Admin Center</span><span class="sxs-lookup"><span data-stu-id="a1ac3-117">Tenant-wide sharing policies in SharePoint admin center</span></span>
- <span data-ttu-id="a1ac3-118">Azure Active Directory-Einstellungen (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="a1ac3-118">Settings in Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="a1ac3-119">Sie haben zudem [Office 365 Advanced Threat Protection (ATP) für SharePoint, OneDrive und Microsoft Teams aktiviert](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="a1ac3-119">You've also [enabled Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span></span>

<span data-ttu-id="a1ac3-120">Gegebenenfalls hilft Ihnen [Schritt 3](infoprotect-configure-increased-security-office-365.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="a1ac3-120">If needed, [Step 3](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step2"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="a1ac3-121">Optional: Klassifikation ist in der gesamten Umgebung konfiguriert</span><span class="sxs-lookup"><span data-stu-id="a1ac3-121">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="a1ac3-122">Sie haben mit Ihrer Rechts- und Complianceabteilung eine entsprechende Klassifikation und ein Bezeichnungsschema für Data Governance- und Sicherheitsrichtlinien in Ihrer Organisation erarbeitet.</span><span class="sxs-lookup"><span data-stu-id="a1ac3-122">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization’s data governance and security policies.</span></span> 

<span data-ttu-id="a1ac3-123">Diese Richtlinien entsprechen der Konfiguration und Bereitstellung von:</span><span class="sxs-lookup"><span data-stu-id="a1ac3-123">Those policies correspond to the configuration and deployment of:</span></span>

- <span data-ttu-id="a1ac3-124">Typen vertraulicher Daten</span><span class="sxs-lookup"><span data-stu-id="a1ac3-124">Sensitive data types</span></span>
- <span data-ttu-id="a1ac3-125">Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="a1ac3-125">Retention labels</span></span>
- <span data-ttu-id="a1ac3-126">Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="a1ac3-126">Sensitivity labels</span></span>
- <span data-ttu-id="a1ac3-127">Azure Information Protection-Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="a1ac3-127">Azure Information Protection labels</span></span>

<span data-ttu-id="a1ac3-128">Gegebenenfalls hilft Ihnen [Schritt 2](infoprotect-configure-classification.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="a1ac3-128">If needed, [Step 2](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 


<a name="crit-infoprotect-step4"></a>
## <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a><span data-ttu-id="a1ac3-129">Optional: Windows Information Protection wird in Ihrer Umgebung eingesetzt.</span><span class="sxs-lookup"><span data-stu-id="a1ac3-129">Optional: Windows Information Protection is deployed across your environment</span></span>

<span data-ttu-id="a1ac3-130">Für Ihre angemeldeten Windows 10 Enterprise-Geräte wird eine Intune-Richtlinie bereitgestellt und angewendet, die definiert:</span><span class="sxs-lookup"><span data-stu-id="a1ac3-130">Your enrolled Windows 10 Enterprise devices have an Intune policy deployed and applied that defines:</span></span>

- <span data-ttu-id="a1ac3-131">Welche Apps geschützt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a1ac3-131">Which apps to protect.</span></span>
- <span data-ttu-id="a1ac3-132">Der Schutzgrad.</span><span class="sxs-lookup"><span data-stu-id="a1ac3-132">The level of protection.</span></span>
- <span data-ttu-id="a1ac3-133">Wo der Schutz gilt.</span><span class="sxs-lookup"><span data-stu-id="a1ac3-133">Where the protection extends.</span></span>

<span data-ttu-id="a1ac3-134">Gegebenenfalls hilft Ihnen [Schritt 4](infoprotect-deploy-windows-information-protection.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="a1ac3-134">If needed, [Step 4](infoprotect-deploy-windows-information-protection.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-office-365-data-loss-prevention-dlp-is-deployed"></a><span data-ttu-id="a1ac3-135">Optional: Office 365 Verhinderung von Datenverlust (DLP) wird bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a1ac3-135">Optional: Office 365 Data Loss Prevention (DLP) is deployed</span></span>

<span data-ttu-id="a1ac3-136">Sie haben die DLP-Richtlinien analysiert, getestet und dann eingeführt, mit Standorten und Regeln, Bedingungen und Maßnahmen, die Ihre Organisation benötigt, um Kunden und andere Arten von privaten Daten zu schützen und branchenspezifische und regionale Vorschriften und Anforderungen einzuhalten.</span><span class="sxs-lookup"><span data-stu-id="a1ac3-136">You have analyzed, tested, and then rolled out the set of DLP policies—with locations and rules with conditions and actions—that your organization requires to protect customer and other types of private data and to adhere to industry and regional regulations and requirements.</span></span>

<span data-ttu-id="a1ac3-137">Ihre Datenkompatibilität- und Ihr Sicherheits-Personal nutzt das Office 365 Security & Compliance Dashboard zur Überwachung von DLP-Vorfällen.</span><span class="sxs-lookup"><span data-stu-id="a1ac3-137">Your data compliance and security staff are using the Office 365 Security & Compliance dashboard to monitor DLP incidents.</span></span>

<span data-ttu-id="a1ac3-138">Gegebenenfalls hilft Ihnen [Schritt 5](infoprotect-data-loss-prevention.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="a1ac3-138">If needed, [Step 4](infoprotect-data-loss-prevention.md) can help you meet this requirement.</span></span> 


<a name="crit-infoprotect-step6"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="a1ac3-139">Optional: Konfigurieren von Privileged Access Management in Office 365</span><span class="sxs-lookup"><span data-stu-id="a1ac3-139">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="a1ac3-140">Sie haben die Informationen im Thema [Konfigurieren von Privileged Access Management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) verwendet, um privilegierten Zugriff zu aktivieren und eine oder mehrere Richtlinien für privilegierten Zugriff in Ihrer Organisation zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a1ac3-140">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access and create one or more privileged access policies in your organization.</span></span> <span data-ttu-id="a1ac3-141">Sie haben diese Richtlinien konfiguriert, und Just-in-Time-Zugriff ist für Zugriff auf vertrauliche Daten oder Zugriff auf kritische Konfigurationseinstellungen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a1ac3-141">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="a1ac3-142">Gegebenenfalls hilft Ihnen [Schritt 6](infoprotect-configure-privileged-access-management.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="a1ac3-142">If needed, [Step 4](infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 

## <a name="results-and-next-steps"></a><span data-ttu-id="a1ac3-143">Ergebnisse und nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="a1ac3-143">Results and next steps</span></span>

<span data-ttu-id="a1ac3-144">Ihre Information Protection-Infrastruktur für Microsoft 365 Enterprise verwendet definierte Sicherheitsstufen, erhöhte Sicherheit für Office 365, Klassifizierungen anhand vertraulicher Datentypen und -bezeichnungen und privilegierte Zugriffsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="a1ac3-144">Your information protection infrastructure for Microsoft 365 Enterprise uses defined security levels, increased security for Office 365, classification using sensitive data types and labels, and privileged access management.</span></span>

<span data-ttu-id="a1ac3-145">Wenn Sie die Ende-zu-Ende-Bereitstellung von Microsoft 365 Enterprise befolgen, Sie können jetzt für alle Ihre [Arbeitslasten und Szenarien](deploy-workloads.md) die Vorteile der Funktionen und Konfiguration der Foundation-Infrastruktur nutzen.</span><span class="sxs-lookup"><span data-stu-id="a1ac3-145">If you're following the end-to-end deployment of Microsoft 365 Enterprise, you're now ready to have your [workloads and scenarios](deploy-workloads.md) take advantage of all the features and configuration of your foundation infrastructure.</span></span>
