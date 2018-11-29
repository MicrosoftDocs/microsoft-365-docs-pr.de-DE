---
title: Beendigungskriterien für die Information Protection-Infrastruktur
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
description: Informieren Sie sich über die Kriterien für Information Protection-basierte Dienste und -Infrastruktur, um sicherzustellen, dass Ihre Konfiguration die Anforderungen von Microsoft 365Enterprise erfüllt.
ms.openlocfilehash: 10d7b3b888999b65e5faff81e9a2d32e595294cf
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868087"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="b939a-103">Beendigungskriterien für die Information Protection-Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="b939a-103">Information protection infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="b939a-104">Bevor Sie Ihre Foundation-Infrastruktur fertig stellen, stellen Sie sicher, dass die Information Protection-Infrastruktur diese Bedingungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="b939a-104">Before you are complete with your foundation infrastructure, make sure that your information protection infrastructure meets these conditions.</span></span> 

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="b939a-105">Erforderlich: Sicherheits- und Information Protection-Stufen sind für Ihre Organisation definiert</span><span class="sxs-lookup"><span data-stu-id="b939a-105">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="b939a-p101">Sie haben die Planung und Definition der Sicherheitsstufen abgeschlossen, die Ihre Organisation benötigt. Diese Stufen definieren ein Mindestmaß an Sicherheit sowie zusätzliche Sicherheitsstufen für zunehmend vertrauliche Informationen und die erforderliche Datensicherheit.</span><span class="sxs-lookup"><span data-stu-id="b939a-p101">You've planned for and determined the security levels that your organization needs. These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="b939a-108">Sie verwenden mindestens drei Sicherheitsstufen:</span><span class="sxs-lookup"><span data-stu-id="b939a-108">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="b939a-109">Baseline</span><span class="sxs-lookup"><span data-stu-id="b939a-109">Baseline</span></span>
- <span data-ttu-id="b939a-110">Vertraulich</span><span class="sxs-lookup"><span data-stu-id="b939a-110">Sensitive</span></span>
- <span data-ttu-id="b939a-111">Streng geregelt</span><span class="sxs-lookup"><span data-stu-id="b939a-111">Highly regulated</span></span>

<span data-ttu-id="b939a-112">Gegebenenfalls hilft Ihnen [Schritt 1](infoprotect-define-sec-infoprotect-levels.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="b939a-112">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step4"></a>
## <a name="required-increased-security-for-office-365-is-configured"></a><span data-ttu-id="b939a-113">Erforderlich: Erhöhte Sicherheit für Office 365 ist konfiguriert</span><span class="sxs-lookup"><span data-stu-id="b939a-113">Required: Increased security for Office 365 is configured</span></span>

<span data-ttu-id="b939a-114">Sie haben die folgenden Einstellungen für erhöhte Sicherheit basierend auf den Informationen unter [Konfigurieren von Ihrem Office 365-Mandanten zur Erhöhung der Sicherheit](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355) konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="b939a-114">You've configured the following settings for increased security based on the information in [Configure your Office 365 tenant for increased security](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355):</span></span>

- <span data-ttu-id="b939a-115">Richtlinien für die Bedrohungsverwaltung im Office 365 Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="b939a-115">Threat management policies in the Office 365 Security & Compliance Center</span></span>
- <span data-ttu-id="b939a-116">Zusätzliche mandantenweite Exchange Online-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="b939a-116">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="b939a-117">Mandantenweite Freigaberichtlinien im SharePoint Admin Center</span><span class="sxs-lookup"><span data-stu-id="b939a-117">Tenant-wide sharing policies in SharePoint admin center</span></span>
- <span data-ttu-id="b939a-118">Azure Active Directory-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="b939a-118">Settings in Azure Active Directory</span></span>

<span data-ttu-id="b939a-119">Sie haben auch [Office 365 Advanced Threat Protection (ATP) aktiviert](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).</span><span class="sxs-lookup"><span data-stu-id="b939a-119">You've also [enabled Office 365 Advanced Threat Protection (ATP)](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).</span></span>

<span data-ttu-id="b939a-120">Gegebenenfalls hilft Ihnen [Schritt 3](infoprotect-configure-increased-security-office-365.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="b939a-120">If needed, [Step 3](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="b939a-121">Optional: Klassifikation ist in der gesamten Umgebung konfiguriert</span><span class="sxs-lookup"><span data-stu-id="b939a-121">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="b939a-122">Sie haben mit Ihrer Rechts- und Complianceabteilung eine entsprechende Klassifikation und ein Bezeichnungsschema für die Daten in Ihrer Organisation erarbeitet, darunter Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b939a-122">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization’s data, which include the following:</span></span>

- <span data-ttu-id="b939a-123">Typen vertraulicher Daten</span><span class="sxs-lookup"><span data-stu-id="b939a-123">Sensitive data types</span></span>
- <span data-ttu-id="b939a-124">Office 365-Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="b939a-124">Office 365 labels</span></span>
- <span data-ttu-id="b939a-125">Azure Information Protection-Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="b939a-125">Azure Information Protection labels</span></span>

<span data-ttu-id="b939a-126">Gegebenenfalls hilft Ihnen [Schritt 2](infoprotect-configure-classification.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="b939a-126">If needed, [Step 2](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="b939a-127">Optional: Konfigurieren von Privileged Access Management in Office 365</span><span class="sxs-lookup"><span data-stu-id="b939a-127">Optional: Configure privileged access management in Office 365</span></span>

<span data-ttu-id="b939a-p102">Sie haben die Informationen im Thema [Konfigurieren von Privileged Access Management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) verwendet, um privilegierten Zugriff zu aktivieren und eine oder mehrere Richtlinien für privilegierten Zugriff in Ihrer Office 365-Konfiguration zu erstellen. Sie haben diese Richtlinien konfiguriert, und Just-in-Time-Zugriff ist für Zugriff auf vertrauliche Daten oder Zugriff auf kritische Konfigurationseinstellungen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b939a-p102">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access  and create one or more privileged access policies in your Office 365 organization. You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="b939a-130">Gegebenenfalls hilft Ihnen [Schritt 4](infoprotect-configure-privileged-access-management.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="b939a-130">If needed, [Step 4](infoprotect-configure-privileged-access-management.md) can help you meet this requirement.</span></span> 

## <a name="next-step"></a><span data-ttu-id="b939a-131">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="b939a-131">Next Step</span></span>

<span data-ttu-id="b939a-132">Sie können jetzt [Arbeitslasten und Szenarien](deploy-workloads.md) wie Microsoft Teams und Exchange Online bereitstellen, die zusätzlich zu Ihrer Microsoft 365 Enterprise Foundation-Infrastruktur ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b939a-132">You're now ready to deploy [workloads and scenarios](deploy-workloads.md), such as Microsoft Teams and Exchange Online, that run on top of your Microsoft 365 Enterprise foundation infrastructure.</span></span>
