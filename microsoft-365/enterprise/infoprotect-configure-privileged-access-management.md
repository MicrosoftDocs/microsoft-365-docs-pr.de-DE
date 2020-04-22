---
title: 'Schritt 7: Konfigurieren der privilegierten Zugriffsverwaltung'
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Verstehen und Konfigurieren der privilegierten Zugriffsverwaltung.
ms.openlocfilehash: 4fed4daacc17a34563825bf0575880ce06ec6ebd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636988"
---
# <a name="step-7-configure-privileged-access-management"></a><span data-ttu-id="8786f-103">Schritt 7: Konfigurieren der privilegierten Zugriffsverwaltung</span><span class="sxs-lookup"><span data-stu-id="8786f-103">Step 7: Configure privileged access management</span></span>

<span data-ttu-id="8786f-104">*Dieser Schritt ist optional und gilt nur für die Versionen E5 und Advanced Compliance von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="8786f-104">*This step is optional and applies only to the E5 and Advanced Compliance versions of Microsoft 365 Enterprise*</span></span>

![Phase 6: Schutz von Daten](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="8786f-106">Die Verwaltung privilegierter Zugriffsrechte wird durch Konfigurieren von Richtlinien aktiviert, die den Just-in-Time-Zugriff für aufgabenbasierte Aktivitäten in Ihrem Mandanten angeben.</span><span class="sxs-lookup"><span data-stu-id="8786f-106">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your tenant.</span></span> <span data-ttu-id="8786f-107">Damit können Sie Ihre Organisation vor Verstößen schützen, die vorhandene privilegierte Administratorkonten mit einem ständigen Zugriff auf vertrauliche Daten oder den Zugriff auf wichtige Konfigurationseinstellungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="8786f-107">It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="8786f-108">Sie können beispielsweise eine Richtlinie für privilegierte Zugriffsverwaltung konfigurieren, die eine explizite Genehmigung für den Zugriff auf und die Änderung der Organisations Postfacheinstellungen in Ihrem Mandanten erfordert.</span><span class="sxs-lookup"><span data-stu-id="8786f-108">For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your tenant.</span></span>

<span data-ttu-id="8786f-109">In diesem Schritt aktivieren Sie die privilegierte Zugriffsverwaltung in Ihrem Mandanten und konfigurieren privilegierte Zugriffsrichtlinien, die zusätzliche Sicherheit für den aufgabenbasierten Zugriff auf Daten und Konfigurationseinstellungen für Ihre Organisation bieten.</span><span class="sxs-lookup"><span data-stu-id="8786f-109">In this step, you'll enable privileged access management in your tenant and configure privileged access policies that provide additional security for task-based access to data and configuration settings for your organization.</span></span> <span data-ttu-id="8786f-110">Es gibt drei grundlegende Schritte für die ersten Schritte mit privilegiertem Zugriff in Ihrer Organisation:</span><span class="sxs-lookup"><span data-stu-id="8786f-110">There are three basic steps to get started with privileged access in your organization:</span></span>
- <span data-ttu-id="8786f-111">Erstellen einer Gruppe einer genehmigenden Person</span><span class="sxs-lookup"><span data-stu-id="8786f-111">Creating an approver's group</span></span>
- <span data-ttu-id="8786f-112">Aktivieren des privilegierten Zugriffs</span><span class="sxs-lookup"><span data-stu-id="8786f-112">Enabling privileged access</span></span>
- <span data-ttu-id="8786f-113">Erstellen von Genehmigungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="8786f-113">Creating approval policies</span></span>

<span data-ttu-id="8786f-p103">Nach der Konfiguration kann Ihre Organisation mit Privileged Access Management ohne ständige Berechtigungen arbeiten und eine Schutzebene für Sicherheitslücken bereitstellen, die aufgrund eines derartigen ständigen Administratorzugriffs entstehen. Für privilegierten Zugriff sind Genehmigungen zum Ausführen von Aufgaben erforderlich, für die eine zugewiesene Genehmigungsrichtlinie definiert wurde. Benutzer, die Aufgaben ausführen müssen, die in einer Genehmigungsrichtlinie enthalten sind, müssen Zugriff anfordern und diesen gewährt bekommen, um die erforderlichen Berechtigungen zum Ausführen der in der Richtlinie definierten Aufgaben zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8786f-p103">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access. Privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="8786f-117">Informationen zum Aktivieren der Verwaltung privilegierten Zugriffs finden Sie im Thema [configure privileged Access Management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) .</span><span class="sxs-lookup"><span data-stu-id="8786f-117">To enable privileged access management, see the [Configure privileged access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="8786f-118">Weitere Informationen finden Sie im Thema [privilegierte Zugriffsverwaltung](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) .</span><span class="sxs-lookup"><span data-stu-id="8786f-118">For more information, see the [Privileged access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>


|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="8786f-120">Wenn Sie diese Konfiguration in einer Testumgebung ausführen möchten, lesen Sie die [Testumgebungsanleitung: Privileged Access Management](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="8786f-120">To practice this configuration in a test lab environment, see the [Privileged access management Test Lab Guide](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span></span> |
|||

<span data-ttu-id="8786f-121">Als Zwischenprüfung können Sie die [Beendigungskriterien](infoprotect-exit-criteria.md#crit-infoprotect-step7) für diesen Schritt betrachten.</span><span class="sxs-lookup"><span data-stu-id="8786f-121">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step7) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="8786f-122">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="8786f-122">Next Step</span></span>

[<span data-ttu-id="8786f-123">Beendigungskriterien für die Information Protection-Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="8786f-123">Information protection infrastructure exit criteria</span></span>](infoprotect-exit-criteria.md)
