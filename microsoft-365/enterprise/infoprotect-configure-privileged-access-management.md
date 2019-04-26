---
title: 'Schritt 6: Konfigurieren von privileged Access Management für Office 365'
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Verstehen und Konfigurieren von Privileged Access Management für Office 365.
ms.openlocfilehash: 60b52825ead068cd0f068f78c1bbce263e8d7720
ms.sourcegitcommit: 9d4319a015e493fb88c7e1855bca0121654eb39d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/25/2019
ms.locfileid: "33304155"
---
# <a name="step-6-configure-privileged-access-management-for-office-365"></a><span data-ttu-id="e4627-103">Schritt 6: Konfigurieren von privileged Access Management für Office 365</span><span class="sxs-lookup"><span data-stu-id="e4627-103">Step 6: Configure privileged access management for Office 365</span></span>

<span data-ttu-id="e4627-104">*Dieser Schritt ist optional und gilt nur für die Versionen E5 und Advanced Compliance von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="e4627-104">*This step is optional and applies only to the E5 and Advanced Compliance versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="e4627-p101">Privileged Access Management wird durch Konfigurieren von Richtlinien aktiviert, die Just-in-Time-Zugriff für aufgabenbasierte Aktivitäten in Ihrem Office 365-Mandanten angeben. Dadurch kann Ihre Organisation vor Sicherheitsverletzungen geschützt werden, bei denen vorhandene Privileged Access Management-Konten mit ständigem Zugriff auf vertrauliche Daten oder Zugriff auf kritische Konfigurationseinstellungen verwenden. Sie könnten beispielsweise eine Privileged Access Management-Richtlinie konfigurieren, die für den Zugriff und das Ändern von Postfacheinstellungen in der Organisation eine explizite Genehmigung in Ihrem Office 365-Mandanten benötigt. </span><span class="sxs-lookup"><span data-stu-id="e4627-p101">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your Office 365 tenant. It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings. For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your Office 365 tenant.</span></span>

<span data-ttu-id="e4627-p102">In diesem Schritt aktivieren Sie Privileged Access Management in Ihrem Office 365-Mandanten und konfigurieren Richtlinien für privilegierten Zugriff, die zusätzliche Sicherheit für aufgabenbasierten Zugriff auf Office 365-Daten und Konfigurationseinstellungen für Ihre Organisation bereitstellen. Es gibt drei grundlegende Schritte, um mit dem privilegierten Zugriff in Ihrer Office 365-Organisation zu beginnen:</span><span class="sxs-lookup"><span data-stu-id="e4627-p102">In this step, you'll enable privileged access management in your Office 365 tenant and configure privileged access policies that provide additional security for task-based access to Office 365 data and configuration settings for your organization. There are three basic steps to get started with privileged access in your Office 365 organization:</span></span>
- <span data-ttu-id="e4627-110">Erstellen einer Gruppe einer genehmigenden Person</span><span class="sxs-lookup"><span data-stu-id="e4627-110">Creating an approver's group</span></span>
- <span data-ttu-id="e4627-111">Aktivieren des privilegierten Zugriffs</span><span class="sxs-lookup"><span data-stu-id="e4627-111">Enabling privileged access</span></span>
- <span data-ttu-id="e4627-112">Erstellen von Genehmigungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="e4627-112">Creating approval policies</span></span>

<span data-ttu-id="e4627-p103">Nach der Konfiguration kann Ihre Organisation mit Privileged Access Management ohne ständige Berechtigungen arbeiten und eine Schutzebene für Sicherheitslücken bereitstellen, die aufgrund eines derartigen ständigen Administratorzugriffs entstehen. Für privilegierten Zugriff sind Genehmigungen zum Ausführen von Aufgaben erforderlich, für die eine zugewiesene Genehmigungsrichtlinie definiert wurde. Benutzer, die Aufgaben ausführen müssen, die in einer Genehmigungsrichtlinie enthalten sind, müssen Zugriff anfordern und diesen gewährt bekommen, um die erforderlichen Berechtigungen zum Ausführen der in der Richtlinie definierten Aufgaben zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e4627-p103">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access. Privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="e4627-116">Weitere Informationen zum Aktivieren von Privileged Access Management in Office 365 finden Sie im Thema [Konfigurieren von Privileged Access Management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration).</span><span class="sxs-lookup"><span data-stu-id="e4627-116">To enable Office 365 privileged access management, see the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="e4627-117">Weitere Informationen finden Sie im Thema [Privileged Access Management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span><span class="sxs-lookup"><span data-stu-id="e4627-117">For more information, see the [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>

## <a name="results"></a><span data-ttu-id="e4627-118">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="e4627-118">Results</span></span>

<span data-ttu-id="e4627-119">Das Ergebnis dieses Schritts ist, dass Sie die Sicherheit von Office 365 durch Aktivieren der Just-in-Time-Zugriffssteuerung für wichtige Daten und Konfigurationseinstellungen für Ihre Organisation erhöht haben.</span><span class="sxs-lookup"><span data-stu-id="e4627-119">The result of this step is that you've increased the security of Office 365 by enabling just-in-time access control for key data and configuration settings for your organization.</span></span>

<span data-ttu-id="e4627-120">Als Zwischenprüfung können Sie die [Beendigungskriterien](infoprotect-exit-criteria.md#crit-infoprotect-step6) für diesen Schritt betrachten.</span><span class="sxs-lookup"><span data-stu-id="e4627-120">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step6) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="e4627-121">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="e4627-121">Next Step</span></span>

[<span data-ttu-id="e4627-122">Beendigungskriterien für die Information Protection-Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="e4627-122">Information protection infrastructure exit criteria</span></span>](infoprotect-exit-criteria.md)