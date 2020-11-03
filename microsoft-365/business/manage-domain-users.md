---
title: Synchronisieren von Domänenbenutzern mit Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
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
description: Synchronisieren Sie Domänen gesteuerte Benutzer mit Microsoft 365 for Business.
ms.openlocfilehash: b40a995a1723808d2fd171c534e9131a891840ba
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841357"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a><span data-ttu-id="7dd36-103">Synchronisieren von Domänenbenutzern mit Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7dd36-103">Synchronize domain users to Microsoft 365</span></span>

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="7dd36-104">1. Vorbereiten der Verzeichnissynchronisierung</span><span class="sxs-lookup"><span data-stu-id="7dd36-104">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="7dd36-105">Bevor Sie Ihre Benutzer und Computer aus der lokalen Active Directory Domäne synchronisieren, überprüfen Sie die [Verzeichnissynchronisierung auf Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="7dd36-105">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization).</span></span> <span data-ttu-id="7dd36-106">Insbesondere:</span><span class="sxs-lookup"><span data-stu-id="7dd36-106">In particular:</span></span>

   - <span data-ttu-id="7dd36-107">Stellen Sie sicher, dass in Ihrem Verzeichnis keine Duplikate für die folgenden Attribute vorhanden sind: **Mail** , **proxyAddresses** und **userPrincipalName** .</span><span class="sxs-lookup"><span data-stu-id="7dd36-107">Make sure that no duplicates exist in your directory for the following attributes: **mail** , **proxyAddresses** , and **userPrincipalName** .</span></span> <span data-ttu-id="7dd36-108">Diese Werte müssen eindeutig sein, und alle Duplikate müssen entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="7dd36-108">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="7dd36-109">Es wird empfohlen, das UPN-Attribut ( **userPrincipalName** ) für jedes lokale Benutzerkonto so zu konfigurieren, dass es mit der primären e-Mail-Adresse übereinstimmt, die dem lizenzierten Microsoft 365-Benutzer entspricht.</span><span class="sxs-lookup"><span data-stu-id="7dd36-109">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="7dd36-110">Beispiel: *Mary.Shelley@contoso.com* statt *Mary@contoso. local*</span><span class="sxs-lookup"><span data-stu-id="7dd36-110">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="7dd36-111">Wenn die Active Directory Domäne in einem nicht routingfähigen Suffix wie *. local* oder *. LAN* endet, müssen Sie anstelle eines über das Internet routingfähigen Suffixes wie *. com* oder *. org* das UPN-Suffix der lokalen Benutzerkonten anpassen, wie unter [Vorbereiten einer nicht routingfähigen Domäne für die Verzeichnissynchronisierung](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7dd36-111">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan* , instead of an internet routable suffix such as *.com* or *.org* , adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span></span> 

<span data-ttu-id="7dd36-112">Mit dem unten **ausgeführten IdFix** in Schritt 4 (4) wird außerdem sichergestellt, dass Ihre lokale Active Directory für die Verzeichnissynchronisierung bereit ist.</span><span class="sxs-lookup"><span data-stu-id="7dd36-112">The **Run IdFix** in step four (4) below, will also make sure your on-premises Active Directory is ready for directory synchronization.</span></span>

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="7dd36-113">2. installieren und Konfigurieren von Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="7dd36-113">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="7dd36-114">Wenn Sie Ihre Benutzer, Gruppen und Kontakte vom lokalen Active Directory in Azure Active Directory synchronisieren möchten, installieren Sie Azure Active Directory Connect, und richten Sie die Verzeichnissynchronisierung ein.</span><span class="sxs-lookup"><span data-stu-id="7dd36-114">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> 

 1. <span data-ttu-id="7dd36-115">Wählen Sie im [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2024339)im linken Navigationsbereich die Option **Setup** aus.</span><span class="sxs-lookup"><span data-stu-id="7dd36-115">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), select **Setup** in the left nav.</span></span>

 2. <span data-ttu-id="7dd36-116">Wählen Sie unter **Anmeldung und Sicherheit** die Option **Ansicht**  unter **Synchronisierungs Benutzer aus dem Verzeichnis Ihrer Organisation aus** .</span><span class="sxs-lookup"><span data-stu-id="7dd36-116">Under **Sign-in and security** , choose **View**  under **Sync users from your org's directory** .</span></span>

 3. <span data-ttu-id="7dd36-117">Wählen Sie auf der Seite **Benutzer aus der org-Verzeichnissynchronisierung synchronisieren** die Option **Erste Schritte** aus.</span><span class="sxs-lookup"><span data-stu-id="7dd36-117">On the **Sync users from your org's directory** page, choose **Get started** .</span></span>

 4. <span data-ttu-id="7dd36-118">Im ersten Schritt führen Sie das IdFix-Tool aus, um die Verzeichnissynchronisierung vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="7dd36-118">In the first step  run IdFix tool to prepare for Directory sync.</span></span>

 5. <span data-ttu-id="7dd36-119">Befolgen Sie die Schritte des Assistenten zum Herunterladen Azure AD Connect, und verwenden Sie diese, um Ihre domänengesteuerten Benutzer mit Microsoft 365 zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="7dd36-119">Follow the wizard steps to download Azure AD Connect and use it to synchronize your domain-controlled users to Microsoft 365.</span></span>


<span data-ttu-id="7dd36-120">Weitere Informationen finden Sie unter [Einrichten der Verzeichnissynchronisierung für Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) .</span><span class="sxs-lookup"><span data-stu-id="7dd36-120">See [Set up directory synchronization for Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) to learn more.</span></span>

<span data-ttu-id="7dd36-121">Wenn Sie Ihre Optionen für Azure AD Connect konfigurieren, wird empfohlen, dass Sie die **Kennwortsynchronisierung** , das **nahtlose einmalige Anmelden** und das **Kenn Wort Rückschreibe** Feature aktivieren, das auch in Microsoft 365 for Business unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="7dd36-121">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization** , **Seamless Single Sign-On** , and the **password writeback** feature, which is also supported in Microsoft 365 for business.</span></span>

> [!NOTE]
> <span data-ttu-id="7dd36-122">Es gibt einige zusätzliche Schritte für das Kenn Wort Rückschreiben über das Kontrollkästchen in Azure AD Connect hinaus.</span><span class="sxs-lookup"><span data-stu-id="7dd36-122">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="7dd36-123">Weitere Informationen finden Sie unter [Vorgehensweise: Konfigurieren des Kenn Wort](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)Rückschreibens.</span><span class="sxs-lookup"><span data-stu-id="7dd36-123">For more information, see [How-to: configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

<span data-ttu-id="7dd36-124">Wenn Sie auch Domänen verbundene Windows 10-Geräte verwalten möchten, finden Sie weitere Informationen unter [Aktivieren von Domänen verbundenen Windows 10-Geräten, die von Microsoft 365 Business Premium verwaltet werden](manage-windows-devices.md) sollen, um eine hybride Azure AD Join einzurichten.</span><span class="sxs-lookup"><span data-stu-id="7dd36-124">If you also want to manage domain-joined Windows 10 devices, see [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set up a hybrid Azure AD Join.</span></span> 