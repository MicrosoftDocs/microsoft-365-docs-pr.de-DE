---
title: 'Schritt 8: Überwachen des Synchronisierungsstatus'
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
ms.openlocfilehash: 21cfd88617bccab3f0a2bdb51c0d320cd4568a56
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867981"
---
# <a name="step-8-monitor-synchronization-health"></a><span data-ttu-id="5f7ef-103">Schritt 8: Überwachen des Synchronisierungsstatus</span><span class="sxs-lookup"><span data-stu-id="5f7ef-103">Step 8: Monitor synchronization health</span></span>

<span data-ttu-id="5f7ef-104">*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="5f7ef-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="5f7ef-p101">In diesem Schritt installieren Sie einen Azure AD Connect Health-Agenten auf jedem Identitätsserver, um Ihre Identitätsinfrastruktur und die von Azure AD Connect bereitgestellten Synchronisierungsdienste zu überwachen. Die Überwachungsinformationen stehen im Azure AD Connect Health-Portal zur Verfügung. Dort können Sie Warnungen, Informationen zur Leistungsüberwachung, Verwendungsanalysen und andere Informationen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="5f7ef-p101">In Step 4, you'll install an Azure AD Connect Health agent on each of your on-premises identity servers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect. The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

![Komponenten von Azure AD Connect Health](./media/identity-azure-ad-connect-health/identity-azure-ad-connect-health.png)

<span data-ttu-id="5f7ef-108">Die wichtigste Entwurfsentscheidung hinsichtlich der Verwendung von Azure AD Connect Health basiert auf der Art und Weise, wie Sie Azure AD Connect verwenden:</span><span class="sxs-lookup"><span data-stu-id="5f7ef-108">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="5f7ef-109">Wenn Sie die **verwaltete Authentifizierung** verwenden, beginnen Sie mit [Verwenden von Azure AD Connect Health mit Synchronisierung](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync), um Informationen zur Funktionsweise und Konfiguration von Azure AD Connect Health zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5f7ef-109">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="5f7ef-110">Wenn Sie nur die Namen der Konten und Gruppen mithilfe der **Verbundauthentifizierung** mit Active Directory-Verbunddiensten (AD FS) synchronisieren, beginnen Sie mit [Verwenden von Azure AD Connect Health mit AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs), um Informationen zur Funktionsweise und zur Konfiguration von Azure AD Connect Health zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5f7ef-110">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="5f7ef-111">Wenn Sie diesen Schritt abgeschlossen haben, verfügen Sie über Folgendes:</span><span class="sxs-lookup"><span data-stu-id="5f7ef-111">When you complete this step, you’ll have:</span></span>

- <span data-ttu-id="5f7ef-112">Der Azure AD Connect Health-Agent ist auf jedem Ihrer lokalen Identitätsanbieterserver installiert.</span><span class="sxs-lookup"><span data-stu-id="5f7ef-112">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="5f7ef-113">Das Azure AD Connect Health-Portal zeigt den aktuellen Status Ihrer lokalen Infrastruktur und der Synchronisierungsaktivitäten mit dem Azure AD-Mandanten für Ihre Office 365- und EMS-Abonnements.</span><span class="sxs-lookup"><span data-stu-id="5f7ef-113">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Office 365 and EMS subscriptions.</span></span>

<span data-ttu-id="5f7ef-114">Als Zwischenprüfpunkt können Sie sich die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-sync-health) für diesen Schritt ansehen.</span><span class="sxs-lookup"><span data-stu-id="5f7ef-114">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sync-health) for this step.</span></span>


## <a name="next-step"></a><span data-ttu-id="5f7ef-115">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="5f7ef-115">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step9.png)| [<span data-ttu-id="5f7ef-116">Vereinfachen der Kennwortaktualisierungen</span><span class="sxs-lookup"><span data-stu-id="5f7ef-116">Simplify password updates</span></span>](identity-password-writeback.md) |

