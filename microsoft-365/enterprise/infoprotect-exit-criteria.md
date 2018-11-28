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
ms.openlocfilehash: ade8f7640b6b8e12a13cff29d934e55dcd368432
ms.sourcegitcommit: 0221fa79642bc9ed5a052800fb2234facbb99731
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "22449325"
---
# <a name="information-protection-infrastructure-exit-criteria"></a><span data-ttu-id="5bd63-103">Beendigungskriterien für die Information Protection-Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="5bd63-103">Information protection infrastructure exit criteria</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="5bd63-104">Bevor Sie Ihre Foundation-Infrastruktur fertig stellen, stellen Sie sicher, dass die Information Protection-Infrastruktur diese Bedingungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="5bd63-104">Before you are complete with your foundation infrastructure, make sure that your information protection infrastructure meets these conditions.</span></span> 

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a><span data-ttu-id="5bd63-105">Erforderlich: Sicherheits- und Information Protection-Stufen sind für Ihre Organisation definiert</span><span class="sxs-lookup"><span data-stu-id="5bd63-105">Required: Security and information protection levels for your organization are defined</span></span>

<span data-ttu-id="5bd63-p101">Sie haben die Planung und Definition der Sicherheitsstufen abgeschlossen, die Ihre Organisation benötigt. Diese Stufen definieren ein Mindestmaß an Sicherheit sowie zusätzliche Sicherheitsstufen für zunehmend vertrauliche Informationen und die erforderliche Datensicherheit.</span><span class="sxs-lookup"><span data-stu-id="5bd63-p101">You've planned for and determined the security levels that your organization needs. These levels define a minimum level of security and additional levels for increasingly sensitive information and their required data security.</span></span>

<span data-ttu-id="5bd63-108">Sie verwenden mindestens drei Sicherheitsstufen:</span><span class="sxs-lookup"><span data-stu-id="5bd63-108">At a minimum, you are using three security levels:</span></span>

- <span data-ttu-id="5bd63-109">Baseline</span><span class="sxs-lookup"><span data-stu-id="5bd63-109">Baseline</span></span>
- <span data-ttu-id="5bd63-110">Vertraulich</span><span class="sxs-lookup"><span data-stu-id="5bd63-110">Sensitive</span></span>
- <span data-ttu-id="5bd63-111">Streng geregelt</span><span class="sxs-lookup"><span data-stu-id="5bd63-111">Highly regulated</span></span>

<span data-ttu-id="5bd63-112">Gegebenenfalls hilft Ihnen [Schritt 1](infoprotect-define-sec-infoprotect-levels.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="5bd63-112">If needed, [Step 1](infoprotect-define-sec-infoprotect-levels.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step2"></a>
## <a name="required-conditional-access-policies-are-configured"></a><span data-ttu-id="5bd63-113">Erforderlich: Richtlinien für bedingten Zugriff sind konfiguriert</span><span class="sxs-lookup"><span data-stu-id="5bd63-113">Required: Conditional access policies are configured</span></span>

<span data-ttu-id="5bd63-114">Sie haben die Informationen in den folgenden Artikeln verwendet, um die empfohlenen Richtlinien für bedingten Zugriff zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="5bd63-114">You've used the information in these articles to create the set of recommended conditional access policies:</span></span>

- [<span data-ttu-id="5bd63-115">Übersicht über die Identitäts- und Gerätezugriffsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="5bd63-115">Identity and device access policies overview</span></span>](microsoft-365-policies-configurations.md)
- [<span data-ttu-id="5bd63-116">Empfohlene Richtlinien für sichere E-Mails</span><span class="sxs-lookup"><span data-stu-id="5bd63-116">Secure email recommended policies</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="5bd63-117">Empfohlene Richtlinien für sichere Dokumente</span><span class="sxs-lookup"><span data-stu-id="5bd63-117">Recommended secure document policies</span></span>](sharepoint-file-access-policies.md)

<span data-ttu-id="5bd63-118">Sie haben diese Richtlinien konfiguriert und sie auf die drei empfohlenen Sicherheitsstufen oder ihre Äquivalente in Ihrer Organisation angewendet.</span><span class="sxs-lookup"><span data-stu-id="5bd63-118">You've configured these policies and applied them to the three recommended security levels or their equivalents in your organization.</span></span>

<span data-ttu-id="5bd63-119">Gegebenenfalls hilft Ihnen [Schritt 2](infoprotect-configure-conditional-access-policy-settings.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="5bd63-119">If needed, [Step 2](infoprotect-configure-conditional-access-policy-settings.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step4"></a>
## <a name="required-increased-security-for-office-365-is-configured"></a><span data-ttu-id="5bd63-120">Erforderlich: Erhöhte Sicherheit für Office 365 ist konfiguriert</span><span class="sxs-lookup"><span data-stu-id="5bd63-120">Required: Increased security for Office 365 is configured</span></span>

<span data-ttu-id="5bd63-121">Sie haben die folgenden Einstellungen für erhöhte Sicherheit basierend auf den Informationen unter [Konfigurieren von Ihrem Office 365-Mandanten zur Erhöhung der Sicherheit](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355) konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="5bd63-121">You've configured the following settings for increased security based on the information in [Configure your Office 365 tenant for increased security](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355):</span></span>

- <span data-ttu-id="5bd63-122">Richtlinien für die Bedrohungsverwaltung im Office 365 Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="5bd63-122">Threat management policies in the Office 365 Security & Compliance Center</span></span>
- <span data-ttu-id="5bd63-123">Zusätzliche mandantenweite Exchange Online-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="5bd63-123">Additional Exchange Online tenant-wide settings</span></span>
- <span data-ttu-id="5bd63-124">Mandantenweite Freigaberichtlinien im SharePoint Admin Center</span><span class="sxs-lookup"><span data-stu-id="5bd63-124">Tenant-wide sharing policies in SharePoint admin center</span></span>
- <span data-ttu-id="5bd63-125">Azure Active Directory-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="5bd63-125">Settings in Azure Active Directory</span></span>

<span data-ttu-id="5bd63-126">Sie haben auch [Office 365 Advanced Threat Protection (ATP) aktiviert](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).</span><span class="sxs-lookup"><span data-stu-id="5bd63-126">You've also [enabled Office 365 Advanced Threat Protection (ATP)](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).</span></span>

<span data-ttu-id="5bd63-127">Gegebenenfalls hilft Ihnen [Schritt 4](infoprotect-configure-increased-security-office-365.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="5bd63-127">If needed, [Step 4](infoprotect-configure-increased-security-office-365.md) can help you meet this requirement.</span></span> 

<a name="crit-infoprotect-step3"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a><span data-ttu-id="5bd63-128">Optional: Klassifikation ist in der gesamten Umgebung konfiguriert</span><span class="sxs-lookup"><span data-stu-id="5bd63-128">Optional: Classification is configured across your environment</span></span>

<span data-ttu-id="5bd63-129">Sie haben mit Ihrer Rechts- und Complianceabteilung eine entsprechende Klassifikation und ein Bezeichnungsschema für die Daten in Ihrer Organisation erarbeitet, darunter Folgendes:</span><span class="sxs-lookup"><span data-stu-id="5bd63-129">You've worked with your legal and compliance teams to develop an appropriate classification and labeling scheme for your organization’s data, which include the following:</span></span>

- <span data-ttu-id="5bd63-130">Typen vertraulicher Daten</span><span class="sxs-lookup"><span data-stu-id="5bd63-130">Sensitive data types</span></span>
- <span data-ttu-id="5bd63-131">Office 365-Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="5bd63-131">Office 365 labels</span></span>
- <span data-ttu-id="5bd63-132">Azure Information Protection-Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="5bd63-132">Azure Information Protection labels</span></span>

<span data-ttu-id="5bd63-133">Gegebenenfalls hilft Ihnen [Schritt 3](infoprotect-configure-classification.md), diese Anforderung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="5bd63-133">If needed, [Step 3](infoprotect-configure-classification.md) can help you meet this requirement.</span></span> 


## <a name="next-step"></a><span data-ttu-id="5bd63-134">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="5bd63-134">Next Step</span></span>

<span data-ttu-id="5bd63-135">Sie können jetzt [Arbeitslasten und Szenarien](deploy-workloads.md) wie Microsoft Teams und Exchange Online bereitstellen, die zusätzlich zu Ihrer Microsoft 365 Enterprise Foundation-Infrastruktur ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5bd63-135">You're now ready to deploy [workloads and scenarios](deploy-workloads.md), such as Microsoft Teams and Exchange Online, that run on top of your Microsoft 365 Enterprise foundation infrastructure.</span></span>
