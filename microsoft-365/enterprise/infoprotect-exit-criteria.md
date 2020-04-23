---
title: Beendigungskriterien für die Information Protection-Infrastruktur
f1.keywords:
- NOCSH
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
description: Informieren Sie sich über die Kriterien für Information Protection-basierte Dienste und -Infrastruktur, um sicherzustellen, dass Ihre Konfiguration die Anforderungen von Microsoft 365Enterprise erfüllt.
ms.openlocfilehash: c0b4ff6a0d289b8a8c63255d817ea455df00bf13
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631633"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="fa3dd-103">Beendigungskriterien für die Information Protection-Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="fa3dd-103">Information protection infrastructure exit criteria</span></span>

![Phase 6: Schutz von Daten](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="fa3dd-105">Stellen Sie sicher, dass Ihre Information Protection-Infrastruktur die folgenden erforderlichen Kriterien erfüllt, und dass Sie die optionalen Kriterien berücksichtigt haben.</span><span class="sxs-lookup"><span data-stu-id="fa3dd-105">Make sure your information protection infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="fa3dd-106">Erforderlich: Sicherheits- und Information Protection-Stufen sind für Ihre Organisation definiert</span><span class="sxs-lookup"><span data-stu-id="fa3dd-106">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="fa3dd-p101">Sie haben die Planung und Definition der Sicherheitsstufen abgeschlossen, die Ihre Organisation benötigt. Diese Stufen definieren ein Mindestmaß an Sicherheit sowie zusätzliche Sicherheitsstufen für zunehmend vertrauliche Informationen und die erforderliche Datensicherheit.</span><span class="sxs-lookup"><span data-stu-id="fa3dd-p101">You've planned for and determined the security levels that your organization needs. These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="fa3dd-109">Sie verwenden mindestens drei Sicherheitsstufen:</span><span class="sxs-lookup"><span data-stu-id="fa3dd-109">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="fa3dd-110">Baseline</span><span class="sxs-lookup"><span data-stu-id="fa3dd-110">Baseline</span></span>
- <span data-ttu-id="fa3dd-111">Vertraulich</span><span class="sxs-lookup"><span data-stu-id="fa3dd-111">Sensitive</span></span>
- <span data-ttu-id="fa3dd-112">Streng geregelt</span><span class="sxs-lookup"><span data-stu-id="fa3dd-112">Highly regulated</span></span>

<span data-ttu-id="fa3dd-113">Gegebenenfalls hilft Ihnen [Schritt 1](infoprotect-define-sec-infoprotect-levels.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="fa3dd-113">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a><span data-ttu-id="fa3dd-114">Erforderlich: Erhöhte Sicherheit für Microsoft 365 ist konfiguriert</span><span class="sxs-lookup"><span data-stu-id="fa3dd-114">Required: Increased security for Microsoft 365 is configured</span></span>

<span data-ttu-id="fa3dd-115">Sie haben die folgenden Einstellungen für [höhere Sicherheit von Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security) konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="fa3dd-115">You've configured the following settings for [Microsoft 365 increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span></span>

- <span data-ttu-id="fa3dd-116">Richtlinien für die Bedrohungsverwaltung im Microsoft 365 Security Center</span><span class="sxs-lookup"><span data-stu-id="fa3dd-116">Threat management policies in the Microsoft 365 security Center</span></span>
- <span data-ttu-id="fa3dd-117">Zusätzliche mandantenweite Exchange Online-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="fa3dd-117">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="fa3dd-118">Mandantenweite Freigaberichtlinien im SharePoint Admin Center</span><span class="sxs-lookup"><span data-stu-id="fa3dd-118">Tenant-wide sharing policies in SharePoint Online admin center</span></span>
- <span data-ttu-id="fa3dd-119">Azure Active Directory-Einstellungen (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="fa3dd-119">Settings in Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="fa3dd-120">Sie haben zudem [Office 365 Advanced Threat Protection (ATP) für SharePoint, OneDrive und Microsoft Teams aktiviert](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="fa3dd-120">You've also [enabled Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span></span>

<span data-ttu-id="fa3dd-121">Gegebenenfalls hilft Ihnen [Schritt 3](infoprotect-configure-increased-security-office-365.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="fa3dd-121">If needed, [Step 3](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step2"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="fa3dd-122">Optional: Klassifikation ist in der gesamten Umgebung konfiguriert</span><span class="sxs-lookup"><span data-stu-id="fa3dd-122">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="fa3dd-123">Sie haben mit Ihrer Rechts- und Complianceabteilung eine entsprechende Klassifikation und ein Bezeichnungsschema für Data Governance- und Sicherheitsrichtlinien in Ihrer Organisation erarbeitet.</span><span class="sxs-lookup"><span data-stu-id="fa3dd-123">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization's data governance and security policies.</span></span> 

<span data-ttu-id="fa3dd-124">Diese Richtlinien entsprechen der Konfiguration und Bereitstellung von:</span><span class="sxs-lookup"><span data-stu-id="fa3dd-124">Those policies correspond to the configuration and deployment of:</span></span>

- <span data-ttu-id="fa3dd-125">Typen vertraulicher Daten</span><span class="sxs-lookup"><span data-stu-id="fa3dd-125">Sensitive data types</span></span>
- <span data-ttu-id="fa3dd-126">Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="fa3dd-126">Retention labels</span></span>
- <span data-ttu-id="fa3dd-127">Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="fa3dd-127">Sensitivity labels</span></span>
- <span data-ttu-id="fa3dd-128">Azure Information Protection-Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="fa3dd-128">Azure Information Protection labels</span></span>

<span data-ttu-id="fa3dd-129">Gegebenenfalls hilft Ihnen [Schritt 2](infoprotect-configure-classification.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="fa3dd-129">If needed, [Step 2](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 


<a name="crit-infoprotect-step4"></a>
## <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a><span data-ttu-id="fa3dd-130">Optional: Windows Information Protection wird in Ihrer Umgebung eingesetzt.</span><span class="sxs-lookup"><span data-stu-id="fa3dd-130">Optional: Windows Information Protection is deployed across your environment</span></span>

<span data-ttu-id="fa3dd-131">Für Ihre angemeldeten Windows 10 Enterprise-Geräte wird eine Intune-Richtlinie bereitgestellt und angewendet, die definiert:</span><span class="sxs-lookup"><span data-stu-id="fa3dd-131">Your enrolled Windows 10 Enterprise devices have an Intune policy deployed and applied that defines:</span></span>

- <span data-ttu-id="fa3dd-132">Welche Apps geschützt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fa3dd-132">Which apps to protect.</span></span>
- <span data-ttu-id="fa3dd-133">Der Schutzgrad.</span><span class="sxs-lookup"><span data-stu-id="fa3dd-133">The level of protection.</span></span>
- <span data-ttu-id="fa3dd-134">Wo der Schutz gilt.</span><span class="sxs-lookup"><span data-stu-id="fa3dd-134">Where the protection extends.</span></span>

<span data-ttu-id="fa3dd-135">Gegebenenfalls hilft Ihnen [Schritt 4](infoprotect-deploy-windows-information-protection.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="fa3dd-135">If needed, [Step 4](infoprotect-deploy-windows-information-protection.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-data-loss-prevention-dlp-is-deployed"></a><span data-ttu-id="fa3dd-136">Optional: Verhinderung von Datenverlust (DLP) wird bereitgestellt</span><span class="sxs-lookup"><span data-stu-id="fa3dd-136">Optional: Data Loss Prevention (DLP) is deployed</span></span>

<span data-ttu-id="fa3dd-137">Sie haben die DLP-Richtlinien analysiert, getestet und dann eingeführt, mit Standorten und Regeln, Bedingungen und Maßnahmen, die Ihre Organisation benötigt, um Kunden und andere Arten von privaten Daten zu schützen und branchenspezifische und regionale Vorschriften und Anforderungen einzuhalten.</span><span class="sxs-lookup"><span data-stu-id="fa3dd-137">You have analyzed, tested, and then rolled out the set of DLP policies—with locations and rules with conditions and actions—that your organization requires to protect customer and other types of private data and to adhere to industry and regional regulations and requirements.</span></span>

<span data-ttu-id="fa3dd-138">Ihre Datenkompatibilität- und Ihr Sicherheits-Personal nutzt das Security & Compliance Dashboard zur Überwachung von DLP-Vorfällen.</span><span class="sxs-lookup"><span data-stu-id="fa3dd-138">Your data compliance and security staff are using the Security & Compliance dashboard to monitor DLP incidents.</span></span>

<span data-ttu-id="fa3dd-139">Gegebenenfalls hilft Ihnen [Schritt 5](infoprotect-data-loss-prevention.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="fa3dd-139">If needed, [Step 5](infoprotect-data-loss-prevention.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step6"></a>
## <a name="optional-email-encryption-is-configured"></a><span data-ttu-id="fa3dd-140">Optional: E-Mail-Verschlüsselung ist konfiguriert</span><span class="sxs-lookup"><span data-stu-id="fa3dd-140">Optional: Email encryption is configured</span></span>

<span data-ttu-id="fa3dd-141">Sie haben die folgende E-Mail-Verschlüsselung nach Bedarf für Ihre Organisation konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="fa3dd-141">You've configured the following email encryption as needed for your organization:</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="fa3dd-142">**Verschlüsselungsmethode**</span><span class="sxs-lookup"><span data-stu-id="fa3dd-142">**Encryption method**</span></span> | <span data-ttu-id="fa3dd-143">**Für gesendete E-Mails**</span><span class="sxs-lookup"><span data-stu-id="fa3dd-143">**For email sent**</span></span> |
| [<span data-ttu-id="fa3dd-144">Office 365-Nachrichtenverschlüsselung (OME)</span><span class="sxs-lookup"><span data-stu-id="fa3dd-144">Office 365 Message Encryption (OME)</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/ome)  | <span data-ttu-id="fa3dd-145">Außerhalb Ihres Unternehmens mit Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="fa3dd-145">Outside your organization with encryption</span></span> |
| [<span data-ttu-id="fa3dd-146">Verwaltung von Informationsrechten (Information Rights Management, IRM)</span><span class="sxs-lookup"><span data-stu-id="fa3dd-146">Information Rights Management (IRM)</span></span>](https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online) | <span data-ttu-id="fa3dd-147">Verschlüsselung und Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="fa3dd-147">With both encryption and permissions</span></span> |
| [<span data-ttu-id="fa3dd-148">S/MIME (Secure/Multipurpose Internet Mail Extensions)</span><span class="sxs-lookup"><span data-stu-id="fa3dd-148">Secure/Multipurpose Internet Mail Extensions (S/MIME)</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/smime) | <span data-ttu-id="fa3dd-149">Verschlüsselung und digitale Signaturen unter Verwendung der Kryptografie mit öffentlichen Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="fa3dd-149">With both encryption and digital signatures using public key cryptography</span></span> |
|||

<span data-ttu-id="fa3dd-150">Gegebenenfalls hilft Ihnen [Schritt 6](infoprotect-email-encryption.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="fa3dd-150">If needed, [Step 6](infoprotect-email-encryption.md) can help you meet this requirement.</span></span>

<a name="crit-infoprotect-step7"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="fa3dd-151">Optional: Konfigurieren von Privileged Access Management in Office 365</span><span class="sxs-lookup"><span data-stu-id="fa3dd-151">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="fa3dd-152">Sie haben die Informationen im Thema [Konfigurieren von Privileged Access Management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) verwendet, um privilegierten Zugriff zu aktivieren und eine oder mehrere Richtlinien für privilegierten Zugriff in Ihrer Organisation zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fa3dd-152">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access and create one or more privileged access policies in your organization.</span></span> <span data-ttu-id="fa3dd-153">Sie haben diese Richtlinien konfiguriert, und Just-in-Time-Zugriff ist für Zugriff auf vertrauliche Daten oder Zugriff auf kritische Konfigurationseinstellungen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="fa3dd-153">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="fa3dd-154">Gegebenenfalls hilft Ihnen [Schritt 7](infoprotect-configure-privileged-access-management.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="fa3dd-154">If needed, [Step 7](infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 

## <a name="results-and-next-steps"></a><span data-ttu-id="fa3dd-155">Ergebnisse und nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="fa3dd-155">Results and next steps</span></span>

<span data-ttu-id="fa3dd-156">Ihre Informationsschutzinfrastruktur für Microsoft 365 Enterprise verwendet definierte Sicherheitsstufen, erhöhte Sicherheit für Office 365, Klassifizierung mithilfe von Datentypen und Bezeichnungen für vertrauliche Daten, Windows Information Protection, Verhinderung von Datenverlust, E-Mail-Verschlüsselung und Privileged Access Management.</span><span class="sxs-lookup"><span data-stu-id="fa3dd-156">Your information protection infrastructure for Microsoft 365 Enterprise uses defined security levels, increased security for Office 365, classification using sensitive data types and labels, Windows Information Protection, Data Loss Prevention, email encryption, and privileged access management.</span></span>

<span data-ttu-id="fa3dd-157">Wenn Sie die Ende-zu-Ende-Bereitstellung von Microsoft 365 Enterprise befolgen, Sie können jetzt für alle Ihre [Arbeitslasten und Szenarien](deploy-workloads.md) die Vorteile der Funktionen und Konfiguration der Foundation-Infrastruktur nutzen.</span><span class="sxs-lookup"><span data-stu-id="fa3dd-157">If you're following the end-to-end deployment of Microsoft 365 Enterprise, you're now ready to have your [workloads and scenarios](deploy-workloads.md) take advantage of all the features and configuration of your foundation infrastructure.</span></span>
