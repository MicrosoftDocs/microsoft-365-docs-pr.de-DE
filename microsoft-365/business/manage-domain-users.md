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
ms.openlocfilehash: 9495d893eb6870ef7c417a78f921296bfc0e6705
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306447"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a><span data-ttu-id="6fe01-103">Synchronisieren von Domänenbenutzern mit Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6fe01-103">Synchronize domain users to Microsoft 365</span></span>

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="6fe01-104">1. Vorbereiten der Verzeichnissynchronisierung</span><span class="sxs-lookup"><span data-stu-id="6fe01-104">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="6fe01-105">Bevor Sie Ihre Benutzer und Computer aus der lokalen Active Directory Domäne synchronisieren, überprüfen Sie die [Verzeichnissynchronisierung auf Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="6fe01-105">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization).</span></span> <span data-ttu-id="6fe01-106">Insbesondere:</span><span class="sxs-lookup"><span data-stu-id="6fe01-106">In particular:</span></span>

   - <span data-ttu-id="6fe01-107">Stellen Sie sicher, dass in Ihrem Verzeichnis keine Duplikate für die folgenden Attribute vorhanden sind: **Mail**, **proxyAddresses**und **userPrincipalName**.</span><span class="sxs-lookup"><span data-stu-id="6fe01-107">Make sure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="6fe01-108">Diese Werte müssen eindeutig sein, und alle Duplikate müssen entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="6fe01-108">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="6fe01-109">Es wird empfohlen, das UPN-Attribut ( **userPrincipalName** ) für jedes lokale Benutzerkonto so zu konfigurieren, dass es mit der primären e-Mail-Adresse übereinstimmt, die dem lizenzierten Microsoft 365-Benutzer entspricht.</span><span class="sxs-lookup"><span data-stu-id="6fe01-109">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="6fe01-110">Beispiel: *Mary.Shelley@contoso.com* statt *Mary@contoso. local*</span><span class="sxs-lookup"><span data-stu-id="6fe01-110">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="6fe01-111">Wenn die Active Directory Domäne in einem nicht routingfähigen Suffix wie *. local* oder *. LAN*endet, müssen Sie anstelle eines über das Internet routingfähigen Suffixes wie *. com* oder *. org*das UPN-Suffix der lokalen Benutzerkonten anpassen, wie unter [Vorbereiten einer nicht routingfähigen Domäne für die Verzeichnissynchronisierung](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6fe01-111">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span></span> 

<span data-ttu-id="6fe01-112">Mit dem unten **ausgeführten IdFix** in Schritt 4 (4) wird außerdem sichergestellt, dass Ihre lokale Active Directory für dir Sync bereit ist.</span><span class="sxs-lookup"><span data-stu-id="6fe01-112">The **Run IdFix** in step four (4) below, will also make sure your on-premises Active Directory is ready for dir sync.</span></span>

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="6fe01-113">2. installieren und Konfigurieren von Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="6fe01-113">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="6fe01-114">Wenn Sie Ihre Benutzer, Gruppen und Kontakte vom lokalen Active Directory in Azure Active Directory synchronisieren möchten, installieren Sie Azure Active Directory Connect, und richten Sie die Verzeichnissynchronisierung ein.</span><span class="sxs-lookup"><span data-stu-id="6fe01-114">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> 

 1. <span data-ttu-id="6fe01-115">Wählen Sie im Admin Center <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> unter **Setup** im linken Navigationsbereich aus.</span><span class="sxs-lookup"><span data-stu-id="6fe01-115">In the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> select **Setup** in the left nav.</span></span>

 2. <span data-ttu-id="6fe01-116">Wählen Sie unter **Anmeldung und Sicherheit**die Option **Ansicht**  unter **Synchronisierungs Benutzer aus dem Verzeichnis Ihrer Organisation aus**.</span><span class="sxs-lookup"><span data-stu-id="6fe01-116">Under **Sign-in and security**, choose **View**  under **Sync users from your org's directory**.</span></span>

 3. <span data-ttu-id="6fe01-117">Wählen Sie auf der Seite **Benutzer aus der org-Verzeichnissynchronisierung synchronisieren** die Option **Erste Schritte**aus.</span><span class="sxs-lookup"><span data-stu-id="6fe01-117">On the **Sync users from your org's directory** page, choose **Get started**.</span></span>

 4. <span data-ttu-id="6fe01-118">Im ersten Schritt führen Sie das IdFix-Tool aus, um die Verzeichnissynchronisierung vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="6fe01-118">In the first step  run IdFix tool to prepare for Directory sync.</span></span>

 5. <span data-ttu-id="6fe01-119">Befolgen Sie die Schritte des Assistenten zum Herunterladen Azure AD Connect, und verwenden Sie diese, um Ihre domänengesteuerten Benutzer mit Microsoft 365 zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="6fe01-119">Follow the wizard steps to download Azure AD Connect and use it to synchronize your domain-controlled users to Microsoft 365.</span></span>


<span data-ttu-id="6fe01-120">Weitere Informationen finden Sie unter [Einrichten der Verzeichnissynchronisierung für Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) .</span><span class="sxs-lookup"><span data-stu-id="6fe01-120">See [Set up directory synchronization for Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) to learn more.</span></span>

<span data-ttu-id="6fe01-121">Wenn Sie Ihre Optionen für Azure AD Connect konfigurieren, wird empfohlen, dass Sie die **Kennwortsynchronisierung**, das **nahtlose einmalige Anmelden**und das **Kenn Wort Rückschreibe** Feature aktivieren, das auch in Microsoft 365 for Business unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="6fe01-121">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization**, **Seamless Single Sign-On**, and the **password writeback** feature, which is also supported in Microsoft 365 for business.</span></span>

> [!NOTE]
> <span data-ttu-id="6fe01-122">Es gibt einige zusätzliche Schritte für das Kenn Wort Rückschreiben über das Kontrollkästchen in Azure AD Connect hinaus.</span><span class="sxs-lookup"><span data-stu-id="6fe01-122">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="6fe01-123">Weitere Informationen finden Sie unter [Vorgehensweise: Konfigurieren des Kenn Wort](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)Rückschreibens.</span><span class="sxs-lookup"><span data-stu-id="6fe01-123">For more information, see [How-to: configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

<span data-ttu-id="6fe01-124">Wenn Sie auch Domänen verbundene Windows 10-Geräte verwalten möchten, finden Sie weitere Informationen unter [enable Domain-Joined Windows 10 Devices to manage by Microsoft 365 Business Premium](manage-windows-devices.md) , um eine hybride Azure AD Join einzurichten.</span><span class="sxs-lookup"><span data-stu-id="6fe01-124">If you want to manage domain-joined Windows 10 devices also, see [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set up a hybrid Azure AD Join.</span></span> 