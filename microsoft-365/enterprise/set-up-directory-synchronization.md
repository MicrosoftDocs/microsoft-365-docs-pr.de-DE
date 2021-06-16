---
title: Einrichten der Verzeichnissynchronisierung für Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
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
description: Erfahren Sie, wie Sie die Verzeichnissynchronisierung zwischen Microsoft 365 und Ihrem lokalen Active Directory einrichten.
ms.openlocfilehash: 14b44523c0a560a71ed8dc9182f677f2ebc0b865
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926526"
---
# <a name="set-up-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="efeb1-103">Einrichten der Verzeichnissynchronisierung für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="efeb1-103">Set up directory synchronization for Microsoft 365</span></span>

<span data-ttu-id="efeb1-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="efeb1-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="efeb1-105">Microsoft 365 verwendet einen Azure Active Directory (Azure AD)-Mandanten zum Speichern und Verwalten von Identitäten für die Authentifizierung und Berechtigungen für den Zugriff auf cloudbasierte Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="efeb1-105">Microsoft 365 uses an Azure Active Directory (Azure AD) tenant to store and manage identities for authentication and permissions to access cloud-based resources.</span></span> 

<span data-ttu-id="efeb1-106">Wenn Sie über eine lokale Active Directory Domain Services (AD DS)-Domäne oder -Gesamtstruktur verfügen, können Sie Ihre AD DS-Benutzerkonten, -Gruppen und -Kontakte mit dem Azure AD-Mandanten Ihres Microsoft 365-Abonnements synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="efeb1-106">If you have an on-premises Active Directory Domain Services (AD DS) domain or forest, you can synchronize your AD DS user accounts, groups, and contacts with the Azure AD tenant of your Microsoft 365 subscription.</span></span> <span data-ttu-id="efeb1-107">Dies ist eine Hybrididentität für Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="efeb1-107">This is hybrid identity for Microsoft 365.</span></span> <span data-ttu-id="efeb1-108">Dies sind ihre Komponenten.</span><span class="sxs-lookup"><span data-stu-id="efeb1-108">Here are its components.</span></span>

![Komponenten der Verzeichnissynchronisierung für Microsoft 365](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="efeb1-110">Azure AD Connect wird auf einem lokalen Server ausgeführt und synchronisiert Ihre AD DS mit dem Azure AD-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="efeb1-110">Azure AD Connect runs on an on-premises server and synchronizes your AD DS with the Azure AD tenant.</span></span> <span data-ttu-id="efeb1-111">Zusammen mit der Verzeichnissynchronisierung können Sie auch die folgenden Authentifizierungsoptionen angeben:</span><span class="sxs-lookup"><span data-stu-id="efeb1-111">Along with directory synchronization, you can also specify these authentication options:</span></span>

- <span data-ttu-id="efeb1-112">Kennworthashsynchronisierung (Password hash synchronization, PHS)</span><span class="sxs-lookup"><span data-stu-id="efeb1-112">Password hash synchronization (PHS)</span></span>

  <span data-ttu-id="efeb1-113">Azure AD führt die Authentifizierung selbst durch.</span><span class="sxs-lookup"><span data-stu-id="efeb1-113">Azure AD performs the authentication itself.</span></span>

- <span data-ttu-id="efeb1-114">Passthrough-Authentifizierung (PTA)</span><span class="sxs-lookup"><span data-stu-id="efeb1-114">Pass-through authentication (PTA)</span></span>

  <span data-ttu-id="efeb1-115">Azure AD lässt AD DS die Authentifizierung durchführen.</span><span class="sxs-lookup"><span data-stu-id="efeb1-115">Azure AD has AD DS perform the authentication.</span></span>

- <span data-ttu-id="efeb1-116">Verbundauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="efeb1-116">Federated authentication</span></span>

  <span data-ttu-id="efeb1-117">Azure AD verweist den Clientcomputer, der die Authentifizierung anfordert, auf einen anderen Identitätsanbieter.</span><span class="sxs-lookup"><span data-stu-id="efeb1-117">Azure AD refers the client computer requesting authentication to another identity provider.</span></span>

<span data-ttu-id="efeb1-118">Weitere Informationen finden Sie unter [Hybrididentitäten](plan-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="efeb1-118">See [Hybrid identities](plan-for-directory-synchronization.md) for more information.</span></span>
  
## <a name="1-review-prerequisites-for-azure-ad-connect"></a><span data-ttu-id="efeb1-119">1. Voraussetzungen für Azure AD Connect überprüfen</span><span class="sxs-lookup"><span data-stu-id="efeb1-119">1. Review prerequisites for Azure AD Connect</span></span>

<span data-ttu-id="efeb1-120">Sie erhalten ein kostenloses Azure AD-Abonnement mit Ihrem Microsoft 365-Abonnement.</span><span class="sxs-lookup"><span data-stu-id="efeb1-120">You get a free Azure AD subscription with your Microsoft 365 subscription.</span></span> <span data-ttu-id="efeb1-121">Wenn Sie die Verzeichnissynchronisierung einrichten, installieren Sie Azure AD Connect auf einem Ihrer lokalen Server.</span><span class="sxs-lookup"><span data-stu-id="efeb1-121">When you set up directory synchronization, you will install Azure AD Connect on one of your on-premises servers.</span></span>
  
<span data-ttu-id="efeb1-122">Für Microsoft 365 müssen Sie:</span><span class="sxs-lookup"><span data-stu-id="efeb1-122">For Microsoft 365 you'll need to:</span></span>
  
- <span data-ttu-id="efeb1-123">Ihre lokale Domäne hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="efeb1-123">Verify your on-premises domain.</span></span> <span data-ttu-id="efeb1-124">Der Azure AD Connect-Assistent führt Sie schrittweise durch diesen Vorgang.</span><span class="sxs-lookup"><span data-stu-id="efeb1-124">The Azure AD Connect wizard guides you through this.</span></span>
- <span data-ttu-id="efeb1-125">Rufen Sie die Benutzernamen und Kennwörter für die Administratorkonten Ihres Microsoft 365 Mandanten und AD DS ab.</span><span class="sxs-lookup"><span data-stu-id="efeb1-125">Obtain the user names and passwords for the admin accounts of your Microsoft 365 tenant and AD DS.</span></span>

<span data-ttu-id="efeb1-126">Für Ihren lokalen Server, auf dem Sie Azure AD Connect installieren, benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="efeb1-126">For your on-premises server on which you install Azure AD Connect, you'll need:</span></span>
  
|<span data-ttu-id="efeb1-127">**Server-Betriebssystem**</span><span class="sxs-lookup"><span data-stu-id="efeb1-127">**Server OS**</span></span>|<span data-ttu-id="efeb1-128">**Weitere Software**</span><span class="sxs-lookup"><span data-stu-id="efeb1-128">**Other software**</span></span>|
|:-----|:-----|
|<span data-ttu-id="efeb1-129">Windows Server 2012 R2 oder neuer</span><span class="sxs-lookup"><span data-stu-id="efeb1-129">Windows Server 2012 R2 and later</span></span> | <span data-ttu-id="efeb1-130">– PowerShell wird standardmäßig installiert, keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="efeb1-130">- PowerShell is installed by default, no action is required.</span></span>  <br> <span data-ttu-id="efeb1-131">– .NET 4.5.1 und höhere Versionen werden über Windows Update bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="efeb1-131">- Net 4.5.1 and later releases are offered through Windows Update.</span></span> <span data-ttu-id="efeb1-132">Vergewissern Sie sich in der Systemsteuerung, dass die neuesten Updates für Windows Server installiert sind.</span><span class="sxs-lookup"><span data-stu-id="efeb1-132">Make sure you have installed the latest updates to Windows Server in the Control Panel.</span></span> |
|<span data-ttu-id="efeb1-133">Windows Server 2008 R2 mit Service Pack 1 (SP1)\*\* oder Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="efeb1-133">Windows Server 2008 R2 with Service Pack 1 (SP1)\*\* or Windows Server 2012</span></span> | <span data-ttu-id="efeb1-134">– Die neueste Version von PowerShell finden Sie im Windows Management Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="efeb1-134">- The latest version of PowerShell is available in Windows Management Framework 4.0.</span></span> <span data-ttu-id="efeb1-135">Suchen Sie im [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996) danach.</span><span class="sxs-lookup"><span data-stu-id="efeb1-135">Search for it on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span>  <br> <span data-ttu-id="efeb1-136">– .NET 4.5.1 und höhere Versionen finden Sie im [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span><span class="sxs-lookup"><span data-stu-id="efeb1-136">- .Net 4.5.1 and later releases are available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span> |
|<span data-ttu-id="efeb1-137">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="efeb1-137">Windows Server 2008</span></span> | <span data-ttu-id="efeb1-138">– Die neueste unterstützte Version von PowerShell befindet sich im Windows Management Framework 3.0, das Sie aus dem [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996) herunterladen können.</span><span class="sxs-lookup"><span data-stu-id="efeb1-138">- The latest supported version of PowerShell is available in Windows Management Framework 3.0, available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span>  <br> <span data-ttu-id="efeb1-139">– .NET 4.5.1 und höhere Versionen finden Sie im [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span><span class="sxs-lookup"><span data-stu-id="efeb1-139">- .Net 4.5.1 and later releases are available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span> |

<span data-ttu-id="efeb1-140">Zusätzliche Informationen zur Hardware, Software, Anforderungen an Konten, Berechtigungen und SSL Zertifikate sowie zu Objekteinschränkungen für Azure AD Connect finden Sie unter [Voraussetzungen für Azure Active Directory Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span><span class="sxs-lookup"><span data-stu-id="efeb1-140">See [Prerequisites for Azure Active Directory Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites) for the details of hardware, software, account and permissions requirements, SSL certificate requirements, and object limits for Azure AD Connect.</span></span>
  
<span data-ttu-id="efeb1-141">Sie können auch den [Versionsveröffentlichungsverlauf](/azure/active-directory/hybrid/reference-connect-version-history) von Azure AD Connect verfolgen, um zu sehen, welche Features und Funktionen in jeder Version enthalten sind und welche Fehler behoben wurden.</span><span class="sxs-lookup"><span data-stu-id="efeb1-141">You can also review the Azure AD Connect [version release history](/azure/active-directory/hybrid/reference-connect-version-history) to see what is included and fixed in each release.</span></span>

## <a name="2-install-azure-ad-connect-and-configure-directory-synchronization"></a><span data-ttu-id="efeb1-142">2. Installieren von Azure AD Connect und Konfigurieren der Verzeichnissynchronisierung</span><span class="sxs-lookup"><span data-stu-id="efeb1-142">2. Install Azure AD Connect and configure directory synchronization</span></span>

<span data-ttu-id="efeb1-143">Bevor Sie beginnen, sollten Sie sicherstellen, dass Sie über Folgendes verfügen:</span><span class="sxs-lookup"><span data-stu-id="efeb1-143">Before you begin, make sure you have:</span></span>

- <span data-ttu-id="efeb1-144">Benutzername und Kennwort eines Microsoft 365 globalen Administrators</span><span class="sxs-lookup"><span data-stu-id="efeb1-144">The user name and password of a Microsoft 365 global admin</span></span>
- <span data-ttu-id="efeb1-145">Den Benutzernamen und das Kennwort des AD-DS-Domänenadministrators.</span><span class="sxs-lookup"><span data-stu-id="efeb1-145">The user name and password of an AD DS domain administrator</span></span>
- <span data-ttu-id="efeb1-146">Welche Authentifizierungsmethode (PHS, PTA, Federated)</span><span class="sxs-lookup"><span data-stu-id="efeb1-146">Which authentication method (PHS, PTA, federated)</span></span>
- <span data-ttu-id="efeb1-147">Ob Sie [Azure AD Seamless Single Sign-On (SSO) verwenden möchten](/azure/active-directory/hybrid/how-to-connect-sso)</span><span class="sxs-lookup"><span data-stu-id="efeb1-147">Whether you want to use [Azure AD Seamless Single Sign-on (SSO)](/azure/active-directory/hybrid/how-to-connect-sso)</span></span>

<span data-ttu-id="efeb1-148">Führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="efeb1-148">Follow these steps:</span></span>

1. <span data-ttu-id="efeb1-149">Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an, (https://admin.microsoft.com) und wählen Sie im linken Navigationsbereich **Benutzer** \> **Aktive Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="efeb1-149">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) (https://admin.microsoft.com) and choose **Users** \> **Active Users** on the left navigation.</span></span>
2. <span data-ttu-id="efeb1-150">Wählen Sie auf der Seite **"Aktive Benutzer"** die Option **"Weitere** (drei Punkte) \> **Verzeichnissynchronisierung"** aus.</span><span class="sxs-lookup"><span data-stu-id="efeb1-150">On the **Active users** page, choose **More** (three dots) \> **Directory synchronization**.</span></span>
  
3. <span data-ttu-id="efeb1-151">Wählen Sie auf der **Azure Active Directory Vorbereitungsseite** das Download center aus, um den Link zum Azure AD Verbinden Tool für die ersten Schritte zu **erhalten.**</span><span class="sxs-lookup"><span data-stu-id="efeb1-151">On the **Azure Active Directory preparation** page, select the **Go to the Download center to get the Azure AD Connect tool** link to get started.</span></span> 
4. <span data-ttu-id="efeb1-152">Folgen Sie den Schritten in [Installationsübersicht: Azure AD Connect und Azure AD Connect Health](/azure/active-directory/hybrid/how-to-connect-install-roadmap).</span><span class="sxs-lookup"><span data-stu-id="efeb1-152">Follow the steps in [Azure AD Connect and Azure AD Connect Health installation roadmap](/azure/active-directory/hybrid/how-to-connect-install-roadmap).</span></span>

## <a name="3-finish-setting-up-domains"></a><span data-ttu-id="efeb1-153">3. Abschließen der Einrichtung von Domänen</span><span class="sxs-lookup"><span data-stu-id="efeb1-153">3. Finish setting up domains</span></span>

<span data-ttu-id="efeb1-154">Führen Sie die Schritte unter [Erstellen von DNS-Einträgen für Microsoft 365 aus, wenn Sie Ihre DNS-Einträge verwalten,](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) um die Einrichtung Ihrer Domänen abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="efeb1-154">Follow the steps in [Create DNS records for Microsoft 365 when you manage your DNS records](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) to finish setting up your domains.</span></span>

## <a name="next-step"></a><span data-ttu-id="efeb1-155">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="efeb1-155">Next step</span></span>

[<span data-ttu-id="efeb1-156">Zuweisen von Lizenzen für Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="efeb1-156">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts.md)