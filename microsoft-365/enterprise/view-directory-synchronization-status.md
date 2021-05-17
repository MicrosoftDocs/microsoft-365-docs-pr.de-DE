---
title: Anzeigen des Verzeichnissynchronisierungsstatus in Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: 18be3b98-34ae-47be-9337-ab6c3fb372ac
description: In diesem Artikel erfahren Sie, wie Sie den Status Ihrer Verzeichnissynchronisierung in Office 365.
ms.openlocfilehash: cbaae8bbd31f6124c2b0f4984b9a625ffbde538f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924660"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a><span data-ttu-id="d00ae-103">Anzeigen des Verzeichnissynchronisierungsstatus in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d00ae-103">View directory synchronization status in Microsoft 365</span></span>

<span data-ttu-id="d00ae-104">Wenn Sie Ihre lokalen Active Directory Domain Services (AD DS) in Azure Active Directory (Azure AD) integriert haben, indem Sie Ihre lokale Umgebung mit Microsoft 365 synchronisieren, können Sie auch den Status Ihrer Synchronisierung überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d00ae-104">If you have integrated your on-premises Active Directory Domain Services (AD DS) with Azure Active Directory (Azure AD) by synchronizing your on-premises environment with Microsoft 365, you can also check the status of your synchronization.</span></span>
  
## <a name="view-directory-synchronization-status"></a><span data-ttu-id="d00ae-105">Anzeigen des Status der Verzeichnissynchronisierung</span><span class="sxs-lookup"><span data-stu-id="d00ae-105">View directory synchronization status</span></span>

- <span data-ttu-id="d00ae-106">Melden Sie sich beim [Microsoft 365 Admin Center an,](https://admin.microsoft.com) und wählen Sie auf der Startseite **den DirSync-Status** aus.</span><span class="sxs-lookup"><span data-stu-id="d00ae-106">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) and choose **DirSync Status** on the home page.</span></span>
- <span data-ttu-id="d00ae-107">Alternativ können Sie zu **Benutzer** Aktive Benutzer wechseln, und wählen Sie auf der Seite Aktive Benutzer die Option \>  **Weitere**  \> **Verzeichnissynchronisierung aus.**</span><span class="sxs-lookup"><span data-stu-id="d00ae-107">Alternately, you can go to **Users** \> **Active users**, and on the **Active users** page, choose **More** \> **Directory synchronization**.</span></span> <span data-ttu-id="d00ae-108">Wählen Sie **im Bereich** Verzeichnissynchronisierung die Option Go **to DirSync management aus.**</span><span class="sxs-lookup"><span data-stu-id="d00ae-108">On the **Directory Synchronization** pane, choose **Go to DirSync management**.</span></span>

## <a name="information-on-the-manage-directory-synchronization-page"></a><span data-ttu-id="d00ae-109">Informationen auf der Seite Verzeichnissynchronisierung verwalten</span><span class="sxs-lookup"><span data-stu-id="d00ae-109">Information on the Manage directory synchronization page</span></span>

<span data-ttu-id="d00ae-110">In der folgenden Tabelle sind die Features aufgeführt, über die Sie Informationen auf der Seite erhalten können.</span><span class="sxs-lookup"><span data-stu-id="d00ae-110">The following table lists the features you can get information about on the page.</span></span>
  
<span data-ttu-id="d00ae-111">Wenn ein Problem mit der Verzeichnissynchronisierung besteht, werden die Fehler auch auf dieser Seite aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="d00ae-111">If there is a problem with your directory synchronization, the errors are listed on this page as well.</span></span> <span data-ttu-id="d00ae-112">Weitere Informationen zu verschiedenen Fehlern, die auftreten können, finden Sie unter Identifizieren von Verzeichnissynchronisierungsfehlern [in Microsoft 365](identify-directory-synchronization-errors.md).</span><span class="sxs-lookup"><span data-stu-id="d00ae-112">For more information about different errors you might encounter, see [Identify directory synchronization errors in Microsoft 365](identify-directory-synchronization-errors.md).</span></span>
  
|<span data-ttu-id="d00ae-113">Element</span><span class="sxs-lookup"><span data-stu-id="d00ae-113">Item</span></span>|<span data-ttu-id="d00ae-114">Zweck</span><span class="sxs-lookup"><span data-stu-id="d00ae-114">What it's for</span></span>|
|:-----|:-----|
|<span data-ttu-id="d00ae-115">**Überprüfte Domänen**</span><span class="sxs-lookup"><span data-stu-id="d00ae-115">**Domains verified**</span></span> | <span data-ttu-id="d00ae-116">Die Anzahl der Domänen in Microsoft 365 Mandanten, die Sie überprüft haben.</span><span class="sxs-lookup"><span data-stu-id="d00ae-116">Number of domains in your Microsoft 365 tenant that you have verified you own.</span></span> |
|<span data-ttu-id="d00ae-117">**Domänen nicht überprüft**</span><span class="sxs-lookup"><span data-stu-id="d00ae-117">**Domains not verified**</span></span> | <span data-ttu-id="d00ae-118">Domänen, die Sie hinzugefügt, aber nicht überprüft haben.</span><span class="sxs-lookup"><span data-stu-id="d00ae-118">Domains you have added, but not verified.</span></span> |
|<span data-ttu-id="d00ae-119">**Verzeichnissynchronisierung aktiviert**</span><span class="sxs-lookup"><span data-stu-id="d00ae-119">**Directory sync enabled**</span></span> |<span data-ttu-id="d00ae-120">"True" oder "False".</span><span class="sxs-lookup"><span data-stu-id="d00ae-120">True or False.</span></span> <span data-ttu-id="d00ae-121">Gibt an, ob Sie die Verzeichnissynchronisierung aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="d00ae-121">Specifies whether you have enabled directory sync.</span></span> |
|<span data-ttu-id="d00ae-122">**Neueste Verzeichnissynchronisierung**</span><span class="sxs-lookup"><span data-stu-id="d00ae-122">**Latest directory sync**</span></span> | <span data-ttu-id="d00ae-123">Das letzte Mal, als die Verzeichnissynchronisierung gelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="d00ae-123">Last time directory sync ran.</span></span> <span data-ttu-id="d00ae-124">Zeigt eine Warnung und einen Link zu einem Problembehandlungstool an, wenn die letzte Synchronisierung vor mehr als drei Tagen war.</span><span class="sxs-lookup"><span data-stu-id="d00ae-124">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="d00ae-125">**Kennwortsynchronisierung aktiviert**</span><span class="sxs-lookup"><span data-stu-id="d00ae-125">**Password sync enabled**</span></span> | <span data-ttu-id="d00ae-126">"True" oder "False".</span><span class="sxs-lookup"><span data-stu-id="d00ae-126">True or False.</span></span> <span data-ttu-id="d00ae-127">Gibt an, ob Sie die Kennworthashsynchronisierung zwischen unserem lokalen und Ihrem Microsoft 365 haben.</span><span class="sxs-lookup"><span data-stu-id="d00ae-127">Specifies whether you have password hash sync between our on-premises and your Microsoft 365 tenant.</span></span> |
|<span data-ttu-id="d00ae-128">**Letzte Kennwortsynchronisierung**</span><span class="sxs-lookup"><span data-stu-id="d00ae-128">**Last Password Sync**</span></span> | <span data-ttu-id="d00ae-129">Letzte Kennworthashsynchronisierung.</span><span class="sxs-lookup"><span data-stu-id="d00ae-129">Last time password hash sync ran.</span></span> <span data-ttu-id="d00ae-130">Zeigt eine Warnung und einen Link zu einem Problembehandlungstool an, wenn die letzte Synchronisierung vor mehr als drei Tagen war.</span><span class="sxs-lookup"><span data-stu-id="d00ae-130">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="d00ae-131">**Verzeichnissynchronisierungsclientversion**</span><span class="sxs-lookup"><span data-stu-id="d00ae-131">**Directory sync client version**</span></span> | <span data-ttu-id="d00ae-132">Enthält einen Downloadlink, wenn eine neue Version von Azure AD Verbinden veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="d00ae-132">Contains a download link if a new version of Azure AD Connect has been released.</span></span> |
|<span data-ttu-id="d00ae-133">**Verzeichnissynchronisierungsdienstkonto**</span><span class="sxs-lookup"><span data-stu-id="d00ae-133">**Directory sync service account**</span></span> | <span data-ttu-id="d00ae-134">Zeigt den Namen Des Microsoft 365 Verzeichnissynchronisierungsdienstkontos an.</span><span class="sxs-lookup"><span data-stu-id="d00ae-134">Displays the name of your Microsoft 365 directory sync service account.</span></span> |
|||

## <a name="monitor-synchronization-health"></a><span data-ttu-id="d00ae-135">Überwachen des Synchronisierungsstatus</span><span class="sxs-lookup"><span data-stu-id="d00ae-135">Monitor synchronization health</span></span>

<span data-ttu-id="d00ae-136">In diesem Abschnitt installieren Sie einen Azure AD Connect Health-Agent auf den einzelnen lokalen AD DS-Domänencontrollern, um die Identitätsinfrastruktur und die von Azure AD Connect bereitgestellten Synchronisierungsdienste zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="d00ae-136">In this section, you'll install an Azure AD Connect Health agent on each of your on-premises AD DS domain controllers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect.</span></span> <span data-ttu-id="d00ae-137">Die Überwachungsinformationen werden in einem Azure AD Connect Health-Portal verfügbar gemacht, wo Sie Warnungen, Leistungsüberwachungsdaten, Nutzungsanalysen und andere Informationen anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="d00ae-137">The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

<span data-ttu-id="d00ae-138">Die wichtigste Entwurfsentscheidung hinsichtlich der Verwendung von Azure AD Connect Health basiert auf der Art und Weise, wie Sie Azure AD Connect verwenden:</span><span class="sxs-lookup"><span data-stu-id="d00ae-138">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="d00ae-139">Wenn Sie die **verwaltete Authentifizierung** verwenden, beginnen Sie mit [Verwenden von Azure AD Connect Health mit Synchronisierung](/azure/active-directory/connect-health/active-directory-aadconnect-health-sync), um Informationen zur Funktionsweise und Konfiguration von Azure AD Connect Health zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d00ae-139">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="d00ae-140">Wenn Sie nur die Namen der Konten und Gruppen mithilfe der **Verbundauthentifizierung** mit Active Directory-Verbunddiensten (AD FS) synchronisieren, beginnen Sie mit [Verwenden von Azure AD Connect Health mit AD FS](/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs), um Informationen zur Funktionsweise und zur Konfiguration von Azure AD Connect Health zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d00ae-140">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="d00ae-141">Wenn Sie fertig sind, haben Sie:</span><span class="sxs-lookup"><span data-stu-id="d00ae-141">When complete, you’ll have:</span></span>

- <span data-ttu-id="d00ae-142">Der Azure AD Connect Health-Agent ist auf jedem Ihrer lokalen Identitätsanbieterserver installiert.</span><span class="sxs-lookup"><span data-stu-id="d00ae-142">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="d00ae-143">Das Azure AD Connect Health-Portal zeigt den aktuellen Status Ihrer lokalen Infrastruktur und der Synchronisierungsaktivitäten mit dem Azure AD-Mandanten für Ihr Microsoft 365-Abonnement.</span><span class="sxs-lookup"><span data-stu-id="d00ae-143">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Microsoft 365 subscription.</span></span>