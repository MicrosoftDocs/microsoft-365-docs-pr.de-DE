---
title: Identitäts- und Gerätezugriffsvoraussetzungen für die Kennworthashsynchronisierung in Ihrer Microsoft 365-Umgebung
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Erstellen Sie eine Microsoft 365-Umgebung zum Testen des Identitäts- und Gerätezugriffs anhand der Voraussetzungen für die Authentifizierung der Kennworthashsynchronisierung.
ms.openlocfilehash: 274f73b1cd6a925b972ab14417c9d854c48c2f00
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074155"
---
# <a name="identity-and-device-access-prerequisites-for-password-hash-synchronization-in-your-microsoft-365-test-environment"></a><span data-ttu-id="d5c0e-103">Identitäts- und Gerätezugriffsvoraussetzungen für die Kennworthashsynchronisierung in Ihrer Microsoft 365-Umgebung</span><span class="sxs-lookup"><span data-stu-id="d5c0e-103">Identity and device access prerequisites for password hash synchronization in your Microsoft 365 test environment</span></span>

<span data-ttu-id="d5c0e-104">[Identitäts- und Gerätezugriffskonfigurationen](microsoft-365-policies-configurations.md) sind eine Reihe von Konfigurationen und Richtlinien zum Schutz des Zugriffs auf alle in Azure Active Directory (Azure AD) integrierten Dienste, einschließlich Office 365 und Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="d5c0e-104">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="d5c0e-105">In diesem Artikel wird beschrieben, wie eine Microsoft 365 Test-Umgebung konfiguriert wird, die die Anforderungen von [Active Directory mit der erforderlichen Konfiguration für die Kennworthashsynchronisierung ](identity-access-prerequisites.md#prerequisites) für den Identitäts- und Gerätezugriff erfüllt.</span><span class="sxs-lookup"><span data-stu-id="d5c0e-105">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [Active Directory with password hash sync prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="d5c0e-106">Es gibt acht Hauptphasen bei der Einrichtung dieser Testumgebung:</span><span class="sxs-lookup"><span data-stu-id="d5c0e-106">There are two phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="d5c0e-107">Erstellen eines simulierten Unternehmens mit Kennworthashsynchronisierung für die Testumgebung</span><span class="sxs-lookup"><span data-stu-id="d5c0e-107">Create a simulated enterprise with password hash sync test environment</span></span>
2.  <span data-ttu-id="d5c0e-108">Konfigurieren des nahtlosen einmaligen Anmeldens in Azure AD</span><span class="sxs-lookup"><span data-stu-id="d5c0e-108">Configure Azure AD single sign-on</span></span>
3.  <span data-ttu-id="d5c0e-109">Konfigurieren benannter Orte</span><span class="sxs-lookup"><span data-stu-id="d5c0e-109">Configure named locations</span></span>
4.  <span data-ttu-id="d5c0e-110">Konfigurieren von Kennwortrückschreiben</span><span class="sxs-lookup"><span data-stu-id="d5c0e-110">Configure password writeback</span></span>
5.  <span data-ttu-id="d5c0e-111">Konfigurieren der Self-Service-Kennwortzurücksetzung für alle Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="d5c0e-111">Configure self-service password reset for all user accounts</span></span>
6.  <span data-ttu-id="d5c0e-112">Konfigurieren der mehrstufigen Authentifizierung für alle Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="d5c0e-112">Configure multifactor authentication for all user accounts</span></span>
7.  <span data-ttu-id="d5c0e-113">Aktivieren von Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="d5c0e-113">Azure AD Identity Protection</span></span>
8.  <span data-ttu-id="d5c0e-114">Aktivieren der modernen Authentifizierung für Exchange Online und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d5c0e-114">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-simulated-enterprise-with-password-hash-sync-microsoft-365-test-environment"></a><span data-ttu-id="d5c0e-115">Phase 1: Erstellen eines simulierten Unternehmens mit Kennworthashsynchronisierung für die Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="d5c0e-115">Phase 1: Build out your simulated enterprise with password hash sync Microsoft 365 test environment</span></span>

<span data-ttu-id="d5c0e-116">Befolgen Sie die Anweisungen unter [Kennworthashsynchronisierung](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="d5c0e-116">Follow the instructions in [Password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span>
<span data-ttu-id="d5c0e-117">Nachfolgend sehen Sie die daraus resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="d5c0e-117">Here is the resulting configuration.</span></span>

![Das simulierte Unternehmen mit Kennworthashsynchronisierung für die Testumgebung](media/password-hash-sync-m365-ent-test-environment/Phase3.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="d5c0e-119">Phase 2: Konfigurieren des nahtlosen einmaligen Anmeldens in Azure AD</span><span class="sxs-lookup"><span data-stu-id="d5c0e-119">Phase 2: Configure Azure AD seamless single sign-on</span></span>

<span data-ttu-id="d5c0e-120">Befolgen Sie die Anweisungen unter [Phase 2: Konfigurieren des nahtlosen einmaligen Anmeldens in Azure AD](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso) der Testumgebungsanleitungen.</span><span class="sxs-lookup"><span data-stu-id="d5c0e-120">Follow the instructions in [Phase 2 of the Azure AD Seamless Single Sign-on Test Lab Guide](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).</span></span>

## <a name="phase-3-configure-named-locations"></a><span data-ttu-id="d5c0e-121">Phase 3: Konfigurieren benannter Orte</span><span class="sxs-lookup"><span data-stu-id="d5c0e-121">Phase 3: Configure named locations</span></span>

<span data-ttu-id="d5c0e-122">Ermitteln Sie zunächst die öffentlichen IP-Adressen oder Adressbereiche, die von Ihrer Organisation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d5c0e-122">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="d5c0e-123">Befolgen Sie dann die Anweisungen unter [Konfigurieren benannter Orte in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations), um die Adressen oder Adressbereiche als benannte Orte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d5c0e-123">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-4-configure-password-writeback"></a><span data-ttu-id="d5c0e-124">Phase 4: Konfigurieren von Kennwortrückschreiben</span><span class="sxs-lookup"><span data-stu-id="d5c0e-124">Phase 4: Configure password writeback</span></span>

<span data-ttu-id="d5c0e-125">Folgen Sie anschließend den Anweisungen unter [Phase 2 der Kennwortrückschreibung](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) der Testumgebungsanleitungen.</span><span class="sxs-lookup"><span data-stu-id="d5c0e-125">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-5-configure-self-service-password-reset"></a><span data-ttu-id="d5c0e-126">Phase 5: Konfigurieren der Self-Service-Kennwortzurücksetzung</span><span class="sxs-lookup"><span data-stu-id="d5c0e-126">Phase 5: Configure self-service password reset</span></span>

<span data-ttu-id="d5c0e-127">Folgen Sie anschließend den Anweisungen unter [Phase 3 der Kennwortzurücksetzung](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) der Testumgebungsanleitungen.</span><span class="sxs-lookup"><span data-stu-id="d5c0e-127">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="d5c0e-128">Wenn Sie das Zurücksetzen des Kennworts für die Konten in einer bestimmten Azure AD-Gruppe aktivieren, fügen Sie diese Konten der Gruppe **Kennwort zurücksetzen** hinzu:</span><span class="sxs-lookup"><span data-stu-id="d5c0e-128">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="d5c0e-129">Benutzer 2</span><span class="sxs-lookup"><span data-stu-id="d5c0e-129">User: %2</span></span>
- <span data-ttu-id="d5c0e-130">Benutzer 3</span><span class="sxs-lookup"><span data-stu-id="d5c0e-130">User Defined 3</span></span>
- <span data-ttu-id="d5c0e-131">Benutzer 4</span><span class="sxs-lookup"><span data-stu-id="d5c0e-131">User: %4</span></span>
- <span data-ttu-id="d5c0e-132">Benutzer 5</span><span class="sxs-lookup"><span data-stu-id="d5c0e-132">User 5</span></span>

<span data-ttu-id="d5c0e-133">Testen Sie die Kennwortzurücksetzung für das Konto von Benutzer 2.</span><span class="sxs-lookup"><span data-stu-id="d5c0e-133">Next, you test password reset for the User 2 account.</span></span>

## <a name="phase-6-configure-multi-factor-authentication"></a><span data-ttu-id="d5c0e-134">Phase 6: Konfigurieren der mehrstufigen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="d5c0e-134">Phase 6: Configure multi-factor authentication</span></span>

<span data-ttu-id="d5c0e-135">Befolgen Sie die Anweisungen unter [Phase 2 der mehrstufige Authentifizierung](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) der Testumgebungsanleitungen für die folgenden Benutzerkonten:</span><span class="sxs-lookup"><span data-stu-id="d5c0e-135">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="d5c0e-136">Benutzer 2</span><span class="sxs-lookup"><span data-stu-id="d5c0e-136">User: %2</span></span>
- <span data-ttu-id="d5c0e-137">Benutzer 3</span><span class="sxs-lookup"><span data-stu-id="d5c0e-137">User Defined 3</span></span>
- <span data-ttu-id="d5c0e-138">Benutzer 4</span><span class="sxs-lookup"><span data-stu-id="d5c0e-138">User: %4</span></span>
- <span data-ttu-id="d5c0e-139">Benutzer 5</span><span class="sxs-lookup"><span data-stu-id="d5c0e-139">User 5</span></span>

<span data-ttu-id="d5c0e-140">Testen der mehrstufigen Authentifizierung für das Konto „Benutzer 2“.</span><span class="sxs-lookup"><span data-stu-id="d5c0e-140">Enable and test multi-factor authentication for the User 2 account.</span></span>

## <a name="phase-7-enable-azure-ad-identity-protection"></a><span data-ttu-id="d5c0e-141">Phase 7: Aktivieren von Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="d5c0e-141">Phase 7: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="d5c0e-142">Befolgen Sie die Anweisungen unter [Phase 2 der Testumgebungsanleitungen für Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="d5c0e-142">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="d5c0e-143">Phase 8: Aktivieren der modernen Authentifizierung für Exchange Online und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d5c0e-143">Phase 8: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="d5c0e-144">Befolgen Sie die [folgenden Anweisungen](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later) für Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d5c0e-144">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="d5c0e-145">Für Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="d5c0e-145">Skype for Business Online</span></span>

1. <span data-ttu-id="d5c0e-146">Stellen Sie eine Verbindung zu [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) her.</span><span class="sxs-lookup"><span data-stu-id="d5c0e-146">[Migrate to Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). (Administrator)</span></span>

2. <span data-ttu-id="d5c0e-147">Führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="d5c0e-147">Run this command:</span></span>

  ```
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="d5c0e-148">Führen Sie den folgenden Befehl aus, um sich zu vergewissern, dass die Änderung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="d5c0e-148">Ensure that the download was successful with this command.</span></span>

  ```
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="d5c0e-149">Das Ergebnis ist eine Test-Umgebung, die die Anforderungen von [Active Directory mit der erforderlichen Konfiguration für die Kennworthashsynchronisierung ](identity-access-prerequisites.md#prerequisites) für den Identitäts- und Gerätezugriff erfüllt.</span><span class="sxs-lookup"><span data-stu-id="d5c0e-149">The result is a test environment that meets the requirements of the [Active Directory with password hash sync prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="d5c0e-150">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="d5c0e-150">Next step</span></span>

<span data-ttu-id="d5c0e-151">Verwenden Sie [Gemeinsame Identitäts- und Gerätezugriffsrichtlinien](identity-access-policies.md), um die Richtlinien zu konfigurieren, die auf den Voraussetzungen aufbauen und Identitäten und Geräte schützen.</span><span class="sxs-lookup"><span data-stu-id="d5c0e-151">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5c0e-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5c0e-152">See also</span></span>

[<span data-ttu-id="d5c0e-153">Testumgebungsanleitungen für zusätzliche Identitäten</span><span class="sxs-lookup"><span data-stu-id="d5c0e-153">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="d5c0e-154">Phase 2: Identität</span><span class="sxs-lookup"><span data-stu-id="d5c0e-154">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="d5c0e-155">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d5c0e-155">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="d5c0e-156">Microsoft 365 Enterprise-Bereitstellungshandbuch</span><span class="sxs-lookup"><span data-stu-id="d5c0e-156">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="d5c0e-157">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d5c0e-157">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
