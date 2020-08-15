---
title: Einrichten der Verzeichnissynchronisierung für Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/15/2020
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED15
- MBS150
- BCS160
ms.assetid: 1b3b5318-6977-42ed-b5c7-96fa74b08846
description: In diesem Artikel erfahren Sie, wie Sie die Verzeichnissynchronisierung zwischen Microsoft 365 und Ihrem lokalen Active Directory einrichten.
ms.openlocfilehash: 3a846a6c558f221c1869dce6da27e3d34680f75d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690343"
---
# <a name="set-up-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="6dc19-103">Einrichten der Verzeichnissynchronisierung für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6dc19-103">Set up directory synchronization for Microsoft 365</span></span>

<span data-ttu-id="6dc19-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="6dc19-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="6dc19-105">Microsoft 365 verwendet einen Azure Active Directory (Azure AD)-Mandanten, um Identitäten für die Authentifizierung und Berechtigungen für den Zugriff auf Cloud-basierte Ressourcen zu speichern und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="6dc19-105">Microsoft 365 uses an Azure Active Directory (Azure AD) tenant to store and manage identities for authentication and permissions to access cloud-based resources.</span></span> 

<span data-ttu-id="6dc19-106">Wenn Sie über eine lokale Active Directory-Domänendienste (AD DS) verfügen, können Sie Ihre AD DS Benutzerkonten, Gruppen und Kontakte mit dem Azure AD Mandanten Ihres Microsoft 365-Abonnements synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="6dc19-106">If you have an on-premises Active Directory Domain Services (AD DS), you can synchronize your AD DS user accounts, groups, and contacts with the Azure AD tenant of your Microsoft 365 subscription.</span></span> <span data-ttu-id="6dc19-107">Dies ist eine hybride Identität für Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6dc19-107">This is hybrid identity for Microsoft 365.</span></span> <span data-ttu-id="6dc19-108">Dies sind ihre Komponenten.</span><span class="sxs-lookup"><span data-stu-id="6dc19-108">Here are its components.</span></span>

![Komponenten der Verzeichnissynchronisierung für Microsoft 365](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="6dc19-110">Azure AD Connect wird auf einem lokalen Server ausgeführt und synchronisiert Ihre AD DS mit dem Azure AD-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="6dc19-110">Azure AD Connect runs on an on-premises server and synchronizes your AD DS with the Azure AD tenant.</span></span> <span data-ttu-id="6dc19-111">Zusammen mit der Verzeichnissynchronisierung können Sie auch die folgenden Authentifizierungsoptionen angeben:</span><span class="sxs-lookup"><span data-stu-id="6dc19-111">Along with directory synchronization, you can also specify these authentication options:</span></span>

- <span data-ttu-id="6dc19-112">Kennworthashsynchronisierung (Password hash synchronization, PHS)</span><span class="sxs-lookup"><span data-stu-id="6dc19-112">Password hash synchronization (PHS)</span></span>

  <span data-ttu-id="6dc19-113">Azure AD führt die Authentifizierung selbst durch.</span><span class="sxs-lookup"><span data-stu-id="6dc19-113">Azure AD performs the authentication itself.</span></span>

- <span data-ttu-id="6dc19-114">Passthrough-Authentifizierung (PTA)</span><span class="sxs-lookup"><span data-stu-id="6dc19-114">Pass-through authentication (PTA)</span></span>

  <span data-ttu-id="6dc19-115">Azure AD lässt AD DS die Authentifizierung durchführen.</span><span class="sxs-lookup"><span data-stu-id="6dc19-115">Azure AD has AD DS perform the authentication.</span></span>

- <span data-ttu-id="6dc19-116">Verbundauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="6dc19-116">Federated authentication</span></span>

  <span data-ttu-id="6dc19-117">Azure AD leitet den Clientcomputer um, der die Authentifizierung anfordert, um einen anderen Identitätsanbieter zu kontaktieren.</span><span class="sxs-lookup"><span data-stu-id="6dc19-117">Azure AD redirects the client computer requesting authentication to contact another identity provider.</span></span>

<span data-ttu-id="6dc19-118">Weitere Informationen finden Sie unter [Hybrididentitäten](plan-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="6dc19-118">See [Hybrid identities](plan-for-directory-synchronization.md) for more information.</span></span>
  
## <a name="1-review-prerequisites-for-azure-ad-connect"></a><span data-ttu-id="6dc19-119">1. Voraussetzungen für Azure AD Connect überprüfen</span><span class="sxs-lookup"><span data-stu-id="6dc19-119">1. Review prerequisites for Azure AD Connect</span></span>

<span data-ttu-id="6dc19-120">Sie erhalten ein kostenloses Azure AD-Abonnement mit Ihrem Microsoft 365-Abonnement.</span><span class="sxs-lookup"><span data-stu-id="6dc19-120">You get a free Azure AD subscription with your Microsoft 365 subscription.</span></span> <span data-ttu-id="6dc19-121">Wenn Sie die Verzeichnissynchronisierung einrichten, installieren Sie Azure AD Connect auf einem Ihrer lokalen Server.</span><span class="sxs-lookup"><span data-stu-id="6dc19-121">When you set up directory synchronization, you will install Azure AD Connect on one of your on-premises servers.</span></span>
  
<span data-ttu-id="6dc19-122">Für Microsoft 365 müssen Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="6dc19-122">For Microsoft 365 you'll need to:</span></span>
  
- <span data-ttu-id="6dc19-123">Ihre lokale Domäne hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6dc19-123">Verify your on-premises domain.</span></span> <span data-ttu-id="6dc19-124">Der Azure AD Connect-Assistent führt Sie schrittweise durch diesen Vorgang.</span><span class="sxs-lookup"><span data-stu-id="6dc19-124">The Azure AD Connect wizard guides you through this.</span></span>
- <span data-ttu-id="6dc19-125">Rufen Sie die Benutzernamen und Kennwörter für die Administratorkonten Ihres Microsoft 365-Mandanten und AD DS ab.</span><span class="sxs-lookup"><span data-stu-id="6dc19-125">Obtain the user names and passwords for the admin accounts of your Microsoft 365 tenant and AD DS.</span></span>

<span data-ttu-id="6dc19-126">Für Ihren lokalen Server, auf dem Sie Azure AD Connect installieren, benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6dc19-126">For your on-premises server on which you install Azure AD Connect, you'll need:</span></span>
  
|<span data-ttu-id="6dc19-127">**Server-Betriebssystem**</span><span class="sxs-lookup"><span data-stu-id="6dc19-127">**Server OS**</span></span>|<span data-ttu-id="6dc19-128">**Weitere Software**</span><span class="sxs-lookup"><span data-stu-id="6dc19-128">**Other software**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6dc19-129">Windows Server 2012 R2 oder neuer</span><span class="sxs-lookup"><span data-stu-id="6dc19-129">Windows Server 2012 R2 and later</span></span> | <span data-ttu-id="6dc19-130">– PowerShell wird standardmäßig installiert, keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6dc19-130">- PowerShell is installed by default, no action is required.</span></span>  <br> <span data-ttu-id="6dc19-131">– .NET 4.5.1 und höhere Versionen werden über Windows Update bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="6dc19-131">- Net 4.5.1 and later releases are offered through Windows Update.</span></span> <span data-ttu-id="6dc19-132">Vergewissern Sie sich in der Systemsteuerung, dass die neuesten Updates für Windows Server installiert sind.</span><span class="sxs-lookup"><span data-stu-id="6dc19-132">Make sure you have installed the latest updates to Windows Server in the Control Panel.</span></span> |
|<span data-ttu-id="6dc19-133">Windows Server 2008 R2 mit Service Pack 1 (SP1)\*\* oder Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="6dc19-133">Windows Server 2008 R2 with Service Pack 1 (SP1)\*\* or Windows Server 2012</span></span> | <span data-ttu-id="6dc19-134">– Die neueste Version von PowerShell finden Sie im Windows Management Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="6dc19-134">- The latest version of PowerShell is available in Windows Management Framework 4.0.</span></span> <span data-ttu-id="6dc19-135">Suchen Sie im [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996) danach.</span><span class="sxs-lookup"><span data-stu-id="6dc19-135">Search for it on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span>  <br> <span data-ttu-id="6dc19-136">– .NET 4.5.1 und höhere Versionen finden Sie im [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span><span class="sxs-lookup"><span data-stu-id="6dc19-136">- .Net 4.5.1 and later releases are available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span> |
|<span data-ttu-id="6dc19-137">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="6dc19-137">Windows Server 2008</span></span> | <span data-ttu-id="6dc19-138">– Die neueste unterstützte Version von PowerShell befindet sich im Windows Management Framework 3.0, das Sie aus dem [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996) herunterladen können.</span><span class="sxs-lookup"><span data-stu-id="6dc19-138">- The latest supported version of PowerShell is available in Windows Management Framework 3.0, available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span>  <br> <span data-ttu-id="6dc19-139">– .NET 4.5.1 und höhere Versionen finden Sie im [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span><span class="sxs-lookup"><span data-stu-id="6dc19-139">- .Net 4.5.1 and later releases are available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span> |

<span data-ttu-id="6dc19-140">Zusätzliche Informationen zur Hardware, Software, Anforderungen an Konten, Berechtigungen und SSL Zertifikate sowie zu Objekteinschränkungen für Azure AD Connect finden Sie unter [Voraussetzungen für Azure Active Directory Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span><span class="sxs-lookup"><span data-stu-id="6dc19-140">See [Prerequisites for Azure Active Directory Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites) for the details of hardware, software, account and permissions requirements, SSL certificate requirements, and object limits for Azure AD Connect.</span></span>
  
<span data-ttu-id="6dc19-141">Sie können auch den [Versionsveröffentlichungsverlauf](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history) von Azure AD Connect verfolgen, um zu sehen, welche Features und Funktionen in jeder Version enthalten sind und welche Fehler behoben wurden.</span><span class="sxs-lookup"><span data-stu-id="6dc19-141">You can also review the Azure AD Connect [version release history](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history) to see what is included and fixed in each release.</span></span>

## <a name="2-install-azure-ad-connect-and-configure-directory-synchronization"></a><span data-ttu-id="6dc19-142">2. Installieren von Azure AD Connect und Konfigurieren der Verzeichnissynchronisierung</span><span class="sxs-lookup"><span data-stu-id="6dc19-142">2. Install Azure AD Connect and configure directory synchronization</span></span>

<span data-ttu-id="6dc19-143">Bevor Sie beginnen, sollten Sie sicherstellen, dass Sie über Folgendes verfügen:</span><span class="sxs-lookup"><span data-stu-id="6dc19-143">Before you begin, make sure you have:</span></span>

- <span data-ttu-id="6dc19-144">Der Benutzername und das Kennwort eines globalen Administrators von Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6dc19-144">The user name and password of a Microsoft 365 global admin</span></span>
- <span data-ttu-id="6dc19-145">Den Benutzernamen und das Kennwort des AD-DS-Domänenadministrators.</span><span class="sxs-lookup"><span data-stu-id="6dc19-145">The user name and password of an AD DS domain administrator</span></span>
- <span data-ttu-id="6dc19-146">Welche Authentifizierungsmethode (PHS, PTA, Federated)</span><span class="sxs-lookup"><span data-stu-id="6dc19-146">Which authentication method (PHS, PTA, federated)</span></span>
- <span data-ttu-id="6dc19-147">Ob Sie [Azure AD Seamless Single Sign-On (SSO) verwenden möchten](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso)</span><span class="sxs-lookup"><span data-stu-id="6dc19-147">Whether you want to use [Azure AD Seamless Single Sign-on (SSO)](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso)</span></span>

<span data-ttu-id="6dc19-148">Führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="6dc19-148">Follow these steps:</span></span>

1. <span data-ttu-id="6dc19-149">Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an, (https://admin.microsoft.com) und wählen Sie im linken Navigationsbereich **Benutzer** \> \*\* Aktive Benutzer\*\* aus.</span><span class="sxs-lookup"><span data-stu-id="6dc19-149">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) (https://admin.microsoft.com) and choose **Users** \> **Active Users** on the left navigation.</span></span>
2. <span data-ttu-id="6dc19-150">Wählen Sie auf der Seite **aktive Benutzer** die Verzeichnissynchronisierung **more** (Three dots) aus \> **Directory synchronization**.</span><span class="sxs-lookup"><span data-stu-id="6dc19-150">On the **Active users** page, choose **More** (three dots) \> **Directory synchronization**.</span></span>
  
3. <span data-ttu-id="6dc19-151">Wählen Sie auf der Seite **Azure Active Directory Vorbereitung** die Option **zum Download Center wechseln** aus, um den Link zum Azure AD Connect-Tool zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6dc19-151">On the **Azure Active Directory preparation** page, select the **Go to the Download center to get the Azure AD Connect tool** link to get started.</span></span> 
4. <span data-ttu-id="6dc19-152">Folgen Sie den Schritten in [Installationsübersicht: Azure AD Connect und Azure AD Connect Health](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-roadmap).</span><span class="sxs-lookup"><span data-stu-id="6dc19-152">Follow the steps in [Azure AD Connect and Azure AD Connect Health installation roadmap](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-roadmap).</span></span>

## <a name="3-finish-setting-up-domains"></a><span data-ttu-id="6dc19-153">3. Abschließen der Einrichtung von Domänen</span><span class="sxs-lookup"><span data-stu-id="6dc19-153">3. Finish setting up domains</span></span>

<span data-ttu-id="6dc19-154">Führen Sie die Schritte unter [Erstellen von DNS-Einträgen für Microsoft 365 beim Verwalten Ihrer DNS-Einträge](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) aus, um die Einrichtung ihrer Domänen abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="6dc19-154">Follow the steps in [Create DNS records for Microsoft 365 when you manage your DNS records](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) to finish setting up your domains.</span></span>

## <a name="next-step"></a><span data-ttu-id="6dc19-155">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="6dc19-155">Next step</span></span>

[<span data-ttu-id="6dc19-156">Zuweisen von Lizenzen zu Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="6dc19-156">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts.md)
