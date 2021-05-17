---
title: Synchronisieren von Domänenbenutzern mit Microsoft 365
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Synchronisieren Sie domänengesteuerte Benutzer mit Microsoft 365 Business.
ms.openlocfilehash: b477b8a1f35a790d6c49937c973c141ad9f90ad4
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578405"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a><span data-ttu-id="52561-103">Synchronisieren von Domänenbenutzern mit Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="52561-103">Synchronize domain users to Microsoft 365</span></span>

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="52561-104">1. Vorbereiten der Verzeichnissynchronisierung</span><span class="sxs-lookup"><span data-stu-id="52561-104">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="52561-105">Bevor Sie Ihre Benutzer und Computer aus der lokalen Active Directory-Domäne synchronisieren, lesen Sie Vorbereiten der [Verzeichnissynchronisierung mit Microsoft 365](../enterprise/prepare-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="52561-105">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Microsoft 365](../enterprise/prepare-for-directory-synchronization.md).</span></span> <span data-ttu-id="52561-106">Insbesondere:</span><span class="sxs-lookup"><span data-stu-id="52561-106">In particular:</span></span>

   - <span data-ttu-id="52561-107">Stellen Sie sicher, dass in Ihrem Verzeichnis keine Duplikate für die folgenden Attribute vorhanden sind: **mail**, **proxyAddresses** und **userPrincipalName**.</span><span class="sxs-lookup"><span data-stu-id="52561-107">Make sure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="52561-108">Diese Werte müssen eindeutig sein, und alle Duplikate müssen entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="52561-108">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="52561-109">Es wird empfohlen, das **UserPrincipalName** (UPN)-Attribut für jedes lokale Benutzerkonto so zu konfigurieren, dass es der primären E-Mail-Adresse entspricht, die dem lizenzierten Benutzer Microsoft 365 entspricht.</span><span class="sxs-lookup"><span data-stu-id="52561-109">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="52561-110">Beispiel: *mary.shelley@contoso.com* anstatt *mary@contoso.local*</span><span class="sxs-lookup"><span data-stu-id="52561-110">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="52561-111">Wenn die Active Directory-Domäne in einem nicht routablen Suffix wie *.local* oder *.lan* endet, anstatt eines internetroutablen Suffixes wie *.com* oder *.org,* passen Sie zuerst das UPN-Suffix der lokalen Benutzerkonten an, wie unter [Prepare a non-routable domain for directory synchronization](../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="52561-111">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md).</span></span> 

<span data-ttu-id="52561-112">Das **Ausführen von IdFix** in Schritt 4 (4) unten sorgt außerdem dafür, dass Ihr lokales Active Directory für die Verzeichnissynchronisierung bereit ist.</span><span class="sxs-lookup"><span data-stu-id="52561-112">The **Run IdFix** in step four (4) below, will also make sure your on-premises Active Directory is ready for directory synchronization.</span></span>

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="52561-113">2. Installieren und Konfigurieren von Azure AD Verbinden</span><span class="sxs-lookup"><span data-stu-id="52561-113">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="52561-114">Um Ihre Benutzer, Gruppen und Kontakte aus dem lokalen Active Directory in Azure Active Directory zu synchronisieren, installieren Sie Azure Active Directory Verbinden Und richten Sie die Verzeichnissynchronisierung ein.</span><span class="sxs-lookup"><span data-stu-id="52561-114">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> 

 1. <span data-ttu-id="52561-115">Wählen Sie [im Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2024339) **setup** im linken Navigations navi aus.</span><span class="sxs-lookup"><span data-stu-id="52561-115">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), select **Setup** in the left nav.</span></span>

 2. <span data-ttu-id="52561-116">Wählen **Sie unter Anmeldung und Sicherheit** die Option **Anzeigen** aus dem Verzeichnis Ihrer Organisation unter Benutzer **synchronisieren aus.**</span><span class="sxs-lookup"><span data-stu-id="52561-116">Under **Sign-in and security**, choose **View**  under **Sync users from your org's directory**.</span></span>

 3. <span data-ttu-id="52561-117">Wählen Sie **auf der Verzeichnisseite Ihrer** Organisation Benutzer synchronisieren die Option Erste Schritte **aus.**</span><span class="sxs-lookup"><span data-stu-id="52561-117">On the **Sync users from your org's directory** page, choose **Get started**.</span></span>

 4. <span data-ttu-id="52561-118">Führen Sie im ersten Schritt das IdFix-Tool aus, um die Verzeichnissynchronisierung vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="52561-118">In the first step  run IdFix tool to prepare for Directory sync.</span></span>

 5. <span data-ttu-id="52561-119">Führen Sie die Schritte des Assistenten aus, um Azure AD Verbinden herunterzuladen und sie zum Synchronisieren ihrer domänengesteuerten Benutzer mit Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="52561-119">Follow the wizard steps to download Azure AD Connect and use it to synchronize your domain-controlled users to Microsoft 365.</span></span>


<span data-ttu-id="52561-120">Weitere Informationen finden Sie unter Set [up directory synchronization for Microsoft 365.](../enterprise/set-up-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="52561-120">See [Set up directory synchronization for Microsoft 365](../enterprise/set-up-directory-synchronization.md) to learn more.</span></span>

<span data-ttu-id="52561-121">Wenn Sie Ihre Optionen für Azure AD Verbinden konfigurieren, wird empfohlen, die Kennwortsynchronisierung, das nahtlose einmalige Anmelden und das Kennwortrückschreiben zu aktivieren, das auch in Microsoft 365 Business unterstützt wird. </span><span class="sxs-lookup"><span data-stu-id="52561-121">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization**, **Seamless Single Sign-On**, and the **password writeback** feature, which is also supported in Microsoft 365 for business.</span></span>

> [!NOTE]
> <span data-ttu-id="52561-122">Es gibt einige zusätzliche Schritte für das Kennwortrückschreiben, die über das Kontrollkästchen in Azure AD Verbinden.</span><span class="sxs-lookup"><span data-stu-id="52561-122">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="52561-123">Weitere Informationen finden Sie unter [How-to: configure password writeback](/azure/active-directory/authentication/howto-sspr-writeback).</span><span class="sxs-lookup"><span data-stu-id="52561-123">For more information, see [How-to: configure password writeback](/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

<span data-ttu-id="52561-124">Wenn Sie auch Mit der Domäne beigetretene Windows 10 verwalten möchten, finden Sie weitere Informationen unter [Enable domain-joined Windows 10 devices to](manage-windows-devices.md) be managed by Microsoft 365 Business Premium to set up a hybrid Azure AD Join.</span><span class="sxs-lookup"><span data-stu-id="52561-124">If you also want to manage domain-joined Windows 10 devices, see [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set up a hybrid Azure AD Join.</span></span>