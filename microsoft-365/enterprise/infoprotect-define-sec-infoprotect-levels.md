---
title: 'Schritt 1: Definieren von Sicherheits- und Informationsschutzebenen'
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
description: Verstehen und konfigurieren Sie Sicherheits- und Informationsschutzebenen für Ihre Organisation.
ms.openlocfilehash: 91274ec2bcd4e4472969a7cd65660742daaef5bd
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286998"
---
# <a name="step-1-define-security-and-information-protection-levels"></a><span data-ttu-id="538e3-103">Schritt 1: Definieren von Sicherheits- und Informationsschutzebenen</span><span class="sxs-lookup"><span data-stu-id="538e3-103">Step 1: Define security and information protection levels</span></span>

<span data-ttu-id="538e3-104">*Dieser Schritt ist erforderlich und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="538e3-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="538e3-105">In diesem Schritt definieren Sie die Sicherheits- und Schutzebenen für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="538e3-105">In this step, you'll define the levels of security and protection for your organization.</span></span> <span data-ttu-id="538e3-106">Für die Vertriebsabteilung ist vielleicht nur eine niedrige Sicherheitsstufe erforderlich.</span><span class="sxs-lookup"><span data-stu-id="538e3-106">For example, your sales department might only require a low security level.</span></span> <span data-ttu-id="538e3-107">Für die Forschungsabteilung und das äußerst wertvolle geistige Eigentum ist aber vielleicht eine hohe Sicherheitsstufe erforderlich, die Dateien verschlüsselt und den Zugriff auf die Forschungsmitarbeiter beschränkt.</span><span class="sxs-lookup"><span data-stu-id="538e3-107">In this step, you'll define the levels of security and protection for your organization. For example, your sales department might only require a low security level, However, your research department and its highly valuable intellectual property might require a high security level that encrypts files and limits access to only research staff.</span></span>

<span data-ttu-id="538e3-108">Obwohl Sie eigene Sicherheitsebenen definieren können und möglicherweise bereits einige haben, empfiehlt Microsoft, dass Sie beim Entwickeln eines Plans mindestens drei unterschiedliche Ebenen von Sicherheit und Schutz verwenden, die angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="538e3-108">Although you can define your own security levels and might already have some in place, Microsoft recommendations that you develop a plan to use at least three different levels of security and protection that can be applied. Here is a list to get you started:</span></span> <span data-ttu-id="538e3-109">Es folgt eine Liste für die ersten Schritte:</span><span class="sxs-lookup"><span data-stu-id="538e3-109">Here is a list to get you started:</span></span> 

- <span data-ttu-id="538e3-p103">**Baseline:** Dies ist ein Minimumstandard zum Schutz von Daten und für die Identitäten und Geräte, die auf Ihre Daten zugreifen. Sie können die Baseline-Empfehlungen für Sicherheit und Schutz befolgen, um starken Standardschutz bereitzustellen, der die Anforderungen vieler Organisationen oder ihrer Abteilungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="538e3-p103">**Baseline:** This is a minimum standard for protecting data and for the identities and devices that access your data. You can follow baseline security and protection recommendations to provide strong default protection that meets the needs of many organizations or their departments.</span></span>
- <span data-ttu-id="538e3-p104">**Vertraulich:** Dies ist zusätzlicher Schutz für eine Teilmenge Ihrer Daten, die über die Baseline-Ebene hinaus geschützt werden müssen. Sie können diesen erhöhten Schutz auf spezifische Datensätze in Ihrer Office 365-Umgebung anwenden. Microsoft empfiehlt auch da Anwenden der vertraulichen Sicherheitsebene auf Identitäten und Geräte, die auf vertrauliche Daten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="538e3-p104">**Sensitive:** This is additional protection for a subset of your data that must be protected beyond the baseline level. You can apply this increased protection to specific data sets in your Office 365 environment. Microsoft also recommends applying the sensitive security level to identities and devices that access sensitive data.</span></span>
- <span data-ttu-id="538e3-p105">**Hoch reguliert:** Dies ist die höchste Schutzebene für Organisationen, die in der Regel eine kleine Menge an streng klassifizierten Daten haben (geistiges Eigentum oder Betriebsgeheimnisse) oder Daten haben, die strengen Sicherheitsvorschriften unterliegen. Microsoft 365 Enterprise bietet Funktionen, damit Organisationen diese hohen Sicherheitsanforderungen erfüllen, einschließlich äquivalenter Schutz für Identitäten und Geräte.</span><span class="sxs-lookup"><span data-stu-id="538e3-p105">**Highly regulated:** This is the highest level of protection for organizations that typically have a very small amount of data that is highly classified, considered intellectual property or trade secrets, or data that must adhere to strict security regulations. Microsoft 365 Enterprise has capabilities to help organizations meet these high security requirements, including equivalent protection for identities and devices.</span></span>

<span data-ttu-id="538e3-117">Weitere Informationen finden Sie unter [Drei Schutzebenen](microsoft-365-policies-configurations.md#three-tiers-of-protection).</span><span class="sxs-lookup"><span data-stu-id="538e3-117">For more information, see [Three tiers of protection](microsoft-365-policies-configurations.md#three-tiers-of-protection).</span></span>

<span data-ttu-id="538e3-118">Als Zwischenprüfung können Sie die [Beendigungskriterien](infoprotect-exit-criteria.md#crit-infoprotect-step1) für diesen Schritt betrachten.</span><span class="sxs-lookup"><span data-stu-id="538e3-118">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step1) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="538e3-119">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="538e3-119">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)|[<span data-ttu-id="538e3-120">Konfigurieren der Klassifizierung für Ihre Umgebung</span><span class="sxs-lookup"><span data-stu-id="538e3-120">Configure classification for your environment</span></span>](infoprotect-configure-classification.md)|
