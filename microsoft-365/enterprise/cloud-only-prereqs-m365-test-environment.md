---
title: Voraussetzungen für Identitäts- und Gerätezugriff für reine Cloudbereitstellung in Ihrer Microsoft 365-Testumgebung
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Erstellen Sie eine Microsoft 365-Umgebung zum Testen des Identitäts- und Gerätezugriffs anhand der Voraussetzungen für die Authentifizierung der reinen Cloudbereitstellung.
ms.openlocfilehash: 2d40eca964cc338186f17b1b03423526e36ac196
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068482"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a><span data-ttu-id="80d41-103">Voraussetzungen für Identitäts- und Gerätezugriff für reine Cloudbereitstellung in Ihrer Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="80d41-103">Identity and device access prerequisites for cloud only in your Microsoft 365 test environment</span></span>

<span data-ttu-id="80d41-104">*Diese Testumgebungsanleitung kann nur für Microsoft 365 Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="80d41-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="80d41-105">[Identitäts- und Gerätezugriffskonfigurationen](microsoft-365-policies-configurations.md) sind eine Reihe von Konfigurationen und Richtlinien zum Schutz des Zugriffs auf alle in Azure Active Directory (Azure AD) integrierten Dienste, einschließlich Office 365 und Microsoft Intune in Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="80d41-105">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of configurations and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Microsoft Intune in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="80d41-106">In diesem Artikel wird beschrieben, wie eine Microsoft 365 Test-Umgebung konfiguriert wird, die die Anforderungen der [erforderlichen Konfiguration für die reine Cloudbereitstellung](identity-access-prerequisites.md#prerequisites) für den Identitäts- und Gerätezugriff erfüllt.</span><span class="sxs-lookup"><span data-stu-id="80d41-106">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [cloud only prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="80d41-107">Es gibt sieben Hauptphasen bei der Einrichtung dieser Testumgebung:</span><span class="sxs-lookup"><span data-stu-id="80d41-107">There are seven phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="80d41-108">Erstellen einer einfachen Testumgebung</span><span class="sxs-lookup"><span data-stu-id="80d41-108">Build out your lightweight test environment</span></span>
2.  <span data-ttu-id="80d41-109">Konfigurieren benannter Orte</span><span class="sxs-lookup"><span data-stu-id="80d41-109">Configure named locations</span></span>
3.  <span data-ttu-id="80d41-110">Konfigurieren von Kennwortrückschreiben</span><span class="sxs-lookup"><span data-stu-id="80d41-110">Configure password writeback</span></span>
4.  <span data-ttu-id="80d41-111">Konfigurieren von Self-Service-Kennwortzurücksetzungen</span><span class="sxs-lookup"><span data-stu-id="80d41-111">Configure self-service password resets</span></span>
5.  <span data-ttu-id="80d41-112">Konfigurieren der mehrstufigen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="80d41-112">Configure multifactor authentication</span></span>
6.  <span data-ttu-id="80d41-113">Aktivieren von Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="80d41-113">Enable Azure AD Identity Protection</span></span>
7.  <span data-ttu-id="80d41-114">Aktivieren der modernen Authentifizierung für Exchange Online und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="80d41-114">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a><span data-ttu-id="80d41-115">Phase 1: Erstellen einer einfachen Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="80d41-115">Phase 1: Build out your lightweight Microsoft 365 test environment</span></span>

<span data-ttu-id="80d41-116">Befolgen Sie die Anweisungen unter [Einfache Basiskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="80d41-116">Follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
<span data-ttu-id="80d41-117">Nachfolgend sehen Sie die daraus resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="80d41-117">Here is the resulting configuration.</span></span>

![Einfache Microsoft 365 Enterprise-Testumgebung](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 

## <a name="phase-2-configure-named-locations"></a><span data-ttu-id="80d41-119">Phase 2: Konfigurieren benannter Orte</span><span class="sxs-lookup"><span data-stu-id="80d41-119">Phase 2: Configure named locations</span></span>

<span data-ttu-id="80d41-120">Ermitteln Sie zunächst die öffentlichen IP-Adressen oder Adressbereiche, die von Ihrer Organisation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="80d41-120">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="80d41-121">Befolgen Sie dann die Anweisungen unter [Konfigurieren benannter Orte in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations), um die Adressen oder Adressbereiche als benannte Orte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="80d41-121">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-3-configure-password-writeback"></a><span data-ttu-id="80d41-122">Phase 3: Konfigurieren von Kennwortrückschreiben</span><span class="sxs-lookup"><span data-stu-id="80d41-122">Phase 3: Configure password writeback</span></span>

<span data-ttu-id="80d41-123">Folgen Sie anschließend den Anweisungen unter [Phase 2 der Kennwortrückschreibung](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) der Testumgebungsanleitungen.</span><span class="sxs-lookup"><span data-stu-id="80d41-123">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-4-configure-self-service-password-reset"></a><span data-ttu-id="80d41-124">Phase 4: Konfigurieren der Self-Service-Kennwortzurücksetzung</span><span class="sxs-lookup"><span data-stu-id="80d41-124">Phase 4: Configure self-service password reset</span></span>

<span data-ttu-id="80d41-125">Folgen Sie anschließend den Anweisungen unter [Phase 3 der Kennwortzurücksetzung](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) der Testumgebungsanleitungen.</span><span class="sxs-lookup"><span data-stu-id="80d41-125">Follow the instructions in [Phase 3 of the password reset Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="80d41-126">Wenn Sie das Zurücksetzen des Kennworts für die Konten in einer bestimmten Azure AD-Gruppe aktivieren, fügen Sie diese Konten der Gruppe **Kennwort zurücksetzen** hinzu:</span><span class="sxs-lookup"><span data-stu-id="80d41-126">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="80d41-127">Benutzer 2</span><span class="sxs-lookup"><span data-stu-id="80d41-127">User 2</span></span>
- <span data-ttu-id="80d41-128">Benutzer 3</span><span class="sxs-lookup"><span data-stu-id="80d41-128">User 3</span></span>
- <span data-ttu-id="80d41-129">Benutzer 4</span><span class="sxs-lookup"><span data-stu-id="80d41-129">User 4</span></span>
- <span data-ttu-id="80d41-130">Benutzer 5</span><span class="sxs-lookup"><span data-stu-id="80d41-130">User 5</span></span>

<span data-ttu-id="80d41-131">Testen Sie die Kennwortzurücksetzung für das Konto von Benutzer 2.</span><span class="sxs-lookup"><span data-stu-id="80d41-131">Test password reset only for the User 2 account.</span></span>

## <a name="phase-5-configure-multi-factor-authentication"></a><span data-ttu-id="80d41-132">Phase 5: Konfigurieren der mehrstufigen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="80d41-132">Phase 5: Configure multi-factor authentication</span></span>

<span data-ttu-id="80d41-133">Befolgen Sie die Anweisungen unter [Phase 2 der mehrstufige Authentifizierung](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) der Testumgebungsanleitungen für die folgenden Benutzerkonten:</span><span class="sxs-lookup"><span data-stu-id="80d41-133">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="80d41-134">Benutzer 2</span><span class="sxs-lookup"><span data-stu-id="80d41-134">User 2</span></span>
- <span data-ttu-id="80d41-135">Benutzer 3</span><span class="sxs-lookup"><span data-stu-id="80d41-135">User 3</span></span>
- <span data-ttu-id="80d41-136">Benutzer 4</span><span class="sxs-lookup"><span data-stu-id="80d41-136">User 4</span></span>
- <span data-ttu-id="80d41-137">Benutzer 5</span><span class="sxs-lookup"><span data-stu-id="80d41-137">User 5</span></span>

<span data-ttu-id="80d41-138">Testen der mehrstufigen Authentifizierung für das Konto „Benutzer 2“.</span><span class="sxs-lookup"><span data-stu-id="80d41-138">Test multi-factor authentication only for the User 2 account.</span></span>

## <a name="phase-6-enable-azure-ad-identity-protection"></a><span data-ttu-id="80d41-139">Phase 6: Aktivieren von Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="80d41-139">Phase 6: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="80d41-140">Befolgen Sie die Anweisungen unter [Phase 2 der Testumgebungsanleitungen für Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="80d41-140">Follow the instructions in [Phase 2 of the Azure AD Identity Protection Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-7-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="80d41-141">Phase 7: Aktivieren der modernen Authentifizierung für Exchange Online und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="80d41-141">Phase 7: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="80d41-142">Befolgen Sie die [folgenden Anweisungen](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later) für Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="80d41-142">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="80d41-143">Für Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="80d41-143">For Skype for Business Online:</span></span>

1. <span data-ttu-id="80d41-144">Stellen Sie eine Verbindung zu [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) her.</span><span class="sxs-lookup"><span data-stu-id="80d41-144">Connect to [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

2. <span data-ttu-id="80d41-145">Führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="80d41-145">Run this command.</span></span>

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="80d41-146">Führen Sie den folgenden Befehl aus, um sich zu vergewissern, dass die Änderung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="80d41-146">Verify that the change was successful with this command.</span></span>

  ```powershell
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="80d41-147">Das Ergebnis ist eine Testumgebung, die die Anforderungen der [erforderlichen Konfiguration für reine Cloudbereitstellung](identity-access-prerequisites.md#prerequisites) für den Identitäts- und Gerätezugriff erfüllt.</span><span class="sxs-lookup"><span data-stu-id="80d41-147">The result is a test environment that meets the requirements of the [cloud only prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="80d41-148">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="80d41-148">Next step</span></span>

<span data-ttu-id="80d41-149">Verwenden Sie [Gemeinsame Identitäts- und Gerätezugriffsrichtlinien](identity-access-policies.md), um die Richtlinien zu konfigurieren, die auf den Voraussetzungen aufbauen und Identitäten und Geräte schützen.</span><span class="sxs-lookup"><span data-stu-id="80d41-149">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and protect identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="80d41-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80d41-150">See also</span></span>

[<span data-ttu-id="80d41-151">Testumgebungsanleitungen für zusätzliche Identitäten</span><span class="sxs-lookup"><span data-stu-id="80d41-151">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="80d41-152">Phase 2: Identität</span><span class="sxs-lookup"><span data-stu-id="80d41-152">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="80d41-153">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="80d41-153">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="80d41-154">Microsoft 365 Enterprise-Bereitstellungshandbuch</span><span class="sxs-lookup"><span data-stu-id="80d41-154">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="80d41-155">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="80d41-155">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
