---
title: 'Schritt 4: Überwachen des Synchronisierungsstatus'
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
description: Grundlegendes und Konfiguration von Azure AD Connect Health
ms.openlocfilehash: 4d4ef922d0c6a0383c84eb858ce4b584c4776fe9
ms.sourcegitcommit: 3f145ce6b0960a073057bdb1bc190ca25dd31fb9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "18997256"
---
# <a name="step-4-monitor-synchronization-health"></a><span data-ttu-id="1eca4-103">Schritt 4: Überwachen des Synchronisierungsstatus</span><span class="sxs-lookup"><span data-stu-id="1eca4-103">Step 4: Monitor synchronization health</span></span>

<span data-ttu-id="1eca4-104">*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="1eca4-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="1eca4-p101">In Schritt 4 installieren Sie einen Azure AD Connect Health-Agenten auf jedem Identitätsserver, um Ihre Identitätsinfrastruktur und die von Azure AD Connect bereitgestellten Synchronisierungsdienste zu überwachen. Die Überwachungsinformationen stehen im Azure AD Connect Health-Portal zur Verfügung. Dort können Sie Warnungen, Informationen zur Leistungsüberwachung, Verwendungsanalysen und andere Informationen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1eca4-p101">In Step 4, you'll install an Azure AD Connect Health agent on each of your on-premises identity servers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect. The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

![Komponenten von Azure AD Connect Health](./media/identity-azure-ad-connect-health/identity-azure-ad-connect-health.png)

<span data-ttu-id="1eca4-108">Die wichtigste Entwurfsentscheidung hinsichtlich der Verwendung von Azure AD Connect Health basiert auf der Art und Weise, wie Sie Azure AD Connect verwenden:</span><span class="sxs-lookup"><span data-stu-id="1eca4-108">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="1eca4-109">Wenn Sie die **verwaltete Authentifizierung** verwenden, beginnen Sie mit [Verwenden von Azure AD Connect Health mit Synchronisierung](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync), um Informationen zur Funktionsweise und Konfiguration von Azure AD Connect Health zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1eca4-109">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="1eca4-110">Wenn Sie nur die Namen der Konten und Gruppen mithilfe der **Verbundauthentifizierung** mit Active Directory-Verbunddiensten (AD FS) synchronisieren, beginnen Sie mit [Verwenden von Azure AD Connect Health mit AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs), um Informationen zur Funktionsweise und zur Konfiguration von Azure AD Connect Health zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1eca4-110">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="1eca4-111">Wenn Sie diesen Schritt abgeschlossen haben, verfügen Sie über Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1eca4-111">When you complete this step, you’ll have:</span></span>

- <span data-ttu-id="1eca4-112">Der Azure AD Connect Health-Agent ist auf jedem Ihrer lokalen Identitätsanbieterserver installiert.</span><span class="sxs-lookup"><span data-stu-id="1eca4-112">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="1eca4-113">Das Azure AD Connect Health-Portal zeigt den aktuellen Status Ihrer lokalen Infrastruktur und der Synchronisierungsaktivitäten mit dem Azure AD-Mandanten für Ihre Office 365- und EMS-Abonnements.</span><span class="sxs-lookup"><span data-stu-id="1eca4-113">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Office 365 and EMS subscriptions.</span></span>

<span data-ttu-id="1eca4-114">Als Zwischenprüfpunkt können Sie sich die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-step4) für diesen Schritt ansehen.</span><span class="sxs-lookup"><span data-stu-id="1eca4-114">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-step4) for this step.</span></span>


## <a name="next-step"></a><span data-ttu-id="1eca4-115">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="1eca4-115">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)| [<span data-ttu-id="1eca4-116">Schützen von globalen Administratorkonten</span><span class="sxs-lookup"><span data-stu-id="1eca4-116">Protect global administrator accounts</span></span>](identity-designate-protect-admin-accounts.md) |

