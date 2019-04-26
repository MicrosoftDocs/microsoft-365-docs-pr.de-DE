---
title: Beendigungskriterien für die Information Protection-Infrastruktur
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Informieren Sie sich über die Kriterien für Information Protection-basierte Dienste und -Infrastruktur, um sicherzustellen, dass Ihre Konfiguration die Anforderungen von Microsoft 365Enterprise erfüllt.
ms.openlocfilehash: 681b3bb2500680b4f5d5801486347aec1b801714
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283696"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="b1cb4-103">Beendigungskriterien für die Information Protection-Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="b1cb4-103">Information protection infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="b1cb4-104">Stellen Sie sicher, dass Ihre Information Protection-Infrastruktur die folgenden erforderlichen Kriterien erfüllt, und dass Sie die optionalen Kriterien berücksichtigt haben.</span><span class="sxs-lookup"><span data-stu-id="b1cb4-104">Make sure your information protection infrastructure meets the following required criteria and that you've considered those that are optional.</span></span>

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="b1cb4-105">Erforderlich: Sicherheits- und Information Protection-Stufen sind für Ihre Organisation definiert</span><span class="sxs-lookup"><span data-stu-id="b1cb4-105">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="b1cb4-p101">Sie haben die Planung und Definition der Sicherheitsstufen abgeschlossen, die Ihre Organisation benötigt. Diese Stufen definieren ein Mindestmaß an Sicherheit sowie zusätzliche Sicherheitsstufen für zunehmend vertrauliche Informationen und die erforderliche Datensicherheit.</span><span class="sxs-lookup"><span data-stu-id="b1cb4-p101">You've planned for and determined the security levels that your organization needs. These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="b1cb4-108">Sie verwenden mindestens drei Sicherheitsstufen:</span><span class="sxs-lookup"><span data-stu-id="b1cb4-108">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="b1cb4-109">Baseline</span><span class="sxs-lookup"><span data-stu-id="b1cb4-109">Baseline</span></span>
- <span data-ttu-id="b1cb4-110">Vertraulich</span><span class="sxs-lookup"><span data-stu-id="b1cb4-110">Sensitive</span></span>
- <span data-ttu-id="b1cb4-111">Streng geregelt</span><span class="sxs-lookup"><span data-stu-id="b1cb4-111">Highly regulated</span></span>

<span data-ttu-id="b1cb4-112">Gegebenenfalls hilft Ihnen [Schritt 1](infoprotect-define-sec-infoprotect-levels.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="b1cb4-112">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step4"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a><span data-ttu-id="b1cb4-113">Erforderlich: Erhöhte Sicherheit für Microsoft 365 ist konfiguriert</span><span class="sxs-lookup"><span data-stu-id="b1cb4-113">Required: Increased security for Office 365 is configured</span></span>

<span data-ttu-id="b1cb4-114">Sie haben die folgenden Einstellungen für [höhere Sicherheit von Office 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security) konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="b1cb4-114">You've configured the following settings for increased security based on the information in [Configure your Office 365 tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):</span></span>

- <span data-ttu-id="b1cb4-115">Richtlinien für die Bedrohungsverwaltung im Microsoft 365 Security Center</span><span class="sxs-lookup"><span data-stu-id="b1cb4-115">Threat management policies in the Microsoft 365 security Center</span></span>
- <span data-ttu-id="b1cb4-116">Zusätzliche mandantenweite Exchange Online-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="b1cb4-116">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="b1cb4-117">Mandantenweite Freigaberichtlinien im SharePoint Admin Center</span><span class="sxs-lookup"><span data-stu-id="b1cb4-117">Tenant-wide sharing policies in SharePoint admin center</span></span>
- <span data-ttu-id="b1cb4-118">Azure Active Directory-Einstellungen (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="b1cb4-118">Settings in Azure Active Directory</span></span>

<span data-ttu-id="b1cb4-119">Sie haben zudem [Office 365 Advanced Threat Protection (ATP) für SharePoint, OneDrive und Microsoft Teams aktiviert](https://docs.microsoft.com/de-DE/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="b1cb4-119">You've also [enabled Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/de-DE/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).</span></span>

<span data-ttu-id="b1cb4-120">Gegebenenfalls hilft Ihnen [Schritt 3](infoprotect-configure-increased-security-office-365.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="b1cb4-120">If needed, [Step 3](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="b1cb4-121">Optional: Klassifikation ist in der gesamten Umgebung konfiguriert</span><span class="sxs-lookup"><span data-stu-id="b1cb4-121">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="b1cb4-122">Sie haben mit Ihrer Rechts- und Complianceabteilung eine entsprechende Klassifikation und ein Bezeichnungsschema für Data Governance- und Sicherheitsrichtlinien in Ihrer Organisation erarbeitet.</span><span class="sxs-lookup"><span data-stu-id="b1cb4-122">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization’s data, which include the following:</span></span> 

<span data-ttu-id="b1cb4-123">Diese Richtlinien entsprechen der Konfiguration und Bereitstellung von:</span><span class="sxs-lookup"><span data-stu-id="b1cb4-123">Those policies correspond to the configuration and deployment of:</span></span>

- <span data-ttu-id="b1cb4-124">Typen vertraulicher Daten</span><span class="sxs-lookup"><span data-stu-id="b1cb4-124">Sensitive data types</span></span>
- <span data-ttu-id="b1cb4-125">Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="b1cb4-125">Retention labels</span></span>
- <span data-ttu-id="b1cb4-126">Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="b1cb4-126">Sensitivity labels</span></span>
- <span data-ttu-id="b1cb4-127">Azure Information Protection-Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="b1cb4-127">Azure Information Protection labels</span></span>

<span data-ttu-id="b1cb4-128">Gegebenenfalls hilft Ihnen [Schritt 2](infoprotect-configure-classification.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="b1cb4-128">If needed, [Step 2](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="b1cb4-129">Optional: Konfigurieren von Privileged Access Management in Office 365</span><span class="sxs-lookup"><span data-stu-id="b1cb4-129">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="b1cb4-130">Sie haben die Informationen im Thema [Konfigurieren von Privileged Access Management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) verwendet, um privilegierten Zugriff zu aktivieren und eine oder mehrere Richtlinien für privilegierten Zugriff in Ihrer Organisation zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b1cb4-130">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access  and create one or more privileged access policies in your Office 365 organization. You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="b1cb4-131">Sie haben diese Richtlinien konfiguriert, und Just-in-Time-Zugriff ist für Zugriff auf vertrauliche Daten oder Zugriff auf kritische Konfigurationseinstellungen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b1cb4-131">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="b1cb4-132">Gegebenenfalls hilft Ihnen [Schritt 4](infoprotect-configure-privileged-access-management.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="b1cb4-132">If needed, [Step 4](infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 

## <a name="results-and-next-steps"></a><span data-ttu-id="b1cb4-133">Ergebnisse und nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="b1cb4-133">Validation and next steps</span></span>

<span data-ttu-id="b1cb4-134">Ihre Information Protection-Infrastruktur für Microsoft 365 Enterprise verwendet definierte Sicherheitsstufen, erhöhte Sicherheit für Office 365, Klassifizierungen anhand vertraulicher Datentypen und -bezeichnungen und privilegierte Zugriffsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="b1cb4-134">Your information protection infrastructure for Microsoft 365 Enterprise uses defined security levels, increased security for Office 365, classification using sensitive data types and labels, and privileged access management.</span></span>

<span data-ttu-id="b1cb4-135">Wenn Sie die Ende-zu-Ende-Bereitstellung von Microsoft 365 Enterprise befolgen, Sie können jetzt für alle Ihre [Arbeitslasten und Szenarien](deploy-workloads.md) die Vorteile der Funktionen und Konfiguration der Foundation-Infrastruktur nutzen.</span><span class="sxs-lookup"><span data-stu-id="b1cb4-135">If you're following the end-to-end deployment of Microsoft 365 Enterprise, you're now ready to have your [workloads and scenarios](deploy-workloads.md) take advantage of all the features and configuration of your foundation infrastructure.</span></span>
