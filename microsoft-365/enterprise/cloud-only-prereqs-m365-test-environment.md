---
title: Voraussetzungen für Identitäts- und Gerätezugriff für reine Cloudbereitstellung in Ihrer Microsoft 365-Testumgebung
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
description: Erstellen Sie eine Microsoft 365-Umgebung zum Testen des Identitäts- und Gerätezugriffs anhand der Voraussetzungen für die Authentifizierung der reinen Cloudbereitstellung.
ms.openlocfilehash: 08f805f77771a056cc9d847dd064b472a46cb166
ms.sourcegitcommit: d9b462e035416bfa4b3d42467902c75859c55381
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2019
ms.locfileid: "36055007"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a><span data-ttu-id="b3862-103">Voraussetzungen für Identitäts- und Gerätezugriff für reine Cloudbereitstellung in Ihrer Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="b3862-103">Identity and device access for your Microsoft 365 test environment</span></span>

<span data-ttu-id="b3862-104">[Identitäts- und Gerätezugriffskonfigurationen](microsoft-365-policies-configurations.md) sind eine Reihe von Konfigurationen und Richtlinien zum Schutz des Zugriffs auf alle in Azure Active Directory (Azure AD) integrierten Dienste, einschließlich Office 365 und Microsoft Intune in Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="b3862-104">[Identity and device access configurations](microsoft-365-policies-configurations.md) are a set of features and conditional access policies to protect access to all services that are integrated with Azure Active Directory (Azure AD), including Office 365 and Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="b3862-105">In diesem Artikel wird beschrieben, wie eine Microsoft 365 Test-Umgebung konfiguriert wird, die die Anforderungen der [erforderlichen Konfiguration für die reine Cloudbereitstellung](identity-access-prerequisites.md#prerequisites) für den Identitäts- und Gerätezugriff erfüllt.</span><span class="sxs-lookup"><span data-stu-id="b3862-105">This article describes how to configure a Microsoft 365 test environment that meets the requirements of the [cloud only prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span>

<span data-ttu-id="b3862-106">Es gibt sieben Hauptphasen bei der Einrichtung dieser Testumgebung:</span><span class="sxs-lookup"><span data-stu-id="b3862-106">There are two phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="b3862-107">Erstellen einer einfachen Testumgebung</span><span class="sxs-lookup"><span data-stu-id="b3862-107">Build out your lightweight test environment</span></span>
2.  <span data-ttu-id="b3862-108">Konfigurieren benannter Orte</span><span class="sxs-lookup"><span data-stu-id="b3862-108">Configure named locations</span></span>
3.  <span data-ttu-id="b3862-109">Konfigurieren von Kennwortrückschreiben</span><span class="sxs-lookup"><span data-stu-id="b3862-109">Configure password writeback</span></span>
4.  <span data-ttu-id="b3862-110">Konfigurieren von Self-Service-Kennwortzurücksetzungen</span><span class="sxs-lookup"><span data-stu-id="b3862-110">Configure self-service password resets</span></span>
5.  <span data-ttu-id="b3862-111">Konfigurieren der mehrstufigen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="b3862-111">Configure multifactor authentication</span></span>
6.  <span data-ttu-id="b3862-112">Aktivieren von Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="b3862-112">Azure AD Identity Protection</span></span>
7.  <span data-ttu-id="b3862-113">Aktivieren der modernen Authentifizierung für Exchange Online und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b3862-113">Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a><span data-ttu-id="b3862-114">Phase 1: Erstellen einer einfachen Microsoft 365-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="b3862-114">Phase 1: Build out your lightweight or simulated enterprise Office 365 dev/test environment</span></span>

<span data-ttu-id="b3862-115">Befolgen Sie die Anweisungen unter [Einfache Basiskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="b3862-115">Follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
<span data-ttu-id="b3862-116">Nachfolgend sehen Sie die daraus resultierende Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="b3862-116">Here is the resulting configuration.</span></span>

![Einfache Microsoft 365 Enterprise-Testumgebung](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 

## <a name="phase-2-configure-named-locations"></a><span data-ttu-id="b3862-118">Phase 2: Konfigurieren benannter Orte</span><span class="sxs-lookup"><span data-stu-id="b3862-118">Phase 2: Configure named locations</span></span>

<span data-ttu-id="b3862-119">Ermitteln Sie zunächst die öffentlichen IP-Adressen oder Adressbereiche, die von Ihrer Organisation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b3862-119">First, determine the public IP addresses or address ranges used by your organization.</span></span>

<span data-ttu-id="b3862-120">Befolgen Sie dann die Anweisungen unter [Konfigurieren benannter Orte in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations), um die Adressen oder Adressbereiche als benannte Orte hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b3862-120">Next, follow the instructions in [Configure named locations in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) to add the addresses or address ranges as named locations.</span></span> 

## <a name="phase-3-configure-password-writeback"></a><span data-ttu-id="b3862-121">Phase 3: Konfigurieren von Kennwortrückschreiben</span><span class="sxs-lookup"><span data-stu-id="b3862-121">Phase 3: Configure password writeback</span></span>

<span data-ttu-id="b3862-122">Folgen Sie anschließend den Anweisungen unter [Phase 2 der Kennwortrückschreibung](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain) der Testumgebungsanleitungen.</span><span class="sxs-lookup"><span data-stu-id="b3862-122">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).</span></span>

## <a name="phase-4-configure-self-service-password-reset"></a><span data-ttu-id="b3862-123">Phase 4: Konfigurieren der Self-Service-Kennwortzurücksetzung</span><span class="sxs-lookup"><span data-stu-id="b3862-123">Phase 4: Configure self-service password reset</span></span>

<span data-ttu-id="b3862-124">Folgen Sie anschließend den Anweisungen unter [Phase 3 der Kennwortzurücksetzung](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset) der Testumgebungsanleitungen.</span><span class="sxs-lookup"><span data-stu-id="b3862-124">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset).</span></span> 

<span data-ttu-id="b3862-125">Wenn Sie das Zurücksetzen des Kennworts für die Konten in einer bestimmten Azure AD-Gruppe aktivieren, fügen Sie diese Konten der Gruppe **Kennwort zurücksetzen** hinzu:</span><span class="sxs-lookup"><span data-stu-id="b3862-125">When enabling password reset for the accounts in a specific Azure AD group, add these accounts to the **Password reset** group:</span></span>

- <span data-ttu-id="b3862-126">Benutzer 2</span><span class="sxs-lookup"><span data-stu-id="b3862-126">User: %2</span></span>
- <span data-ttu-id="b3862-127">Benutzer 3</span><span class="sxs-lookup"><span data-stu-id="b3862-127">User Defined 3</span></span>
- <span data-ttu-id="b3862-128">Benutzer 4</span><span class="sxs-lookup"><span data-stu-id="b3862-128">User: %4</span></span>
- <span data-ttu-id="b3862-129">Benutzer 5</span><span class="sxs-lookup"><span data-stu-id="b3862-129">User 5</span></span>

<span data-ttu-id="b3862-130">Testen Sie die Kennwortzurücksetzung für das Konto von Benutzer 2.</span><span class="sxs-lookup"><span data-stu-id="b3862-130">Next, you test password reset for the User 2 account.</span></span>

## <a name="phase-5-configure-multi-factor-authentication"></a><span data-ttu-id="b3862-131">Phase 5: Konfigurieren der mehrstufigen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="b3862-131">Phase 5: Configure multi-factor authentication</span></span>

<span data-ttu-id="b3862-132">Befolgen Sie die Anweisungen unter [Phase 2 der mehrstufige Authentifizierung](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) der Testumgebungsanleitungen für die folgenden Benutzerkonten:</span><span class="sxs-lookup"><span data-stu-id="b3862-132">Follow the instructions in [Phase 2 of the multi-factor authentication Test Lab Guide](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) for the following user accounts:</span></span>

- <span data-ttu-id="b3862-133">Benutzer 2</span><span class="sxs-lookup"><span data-stu-id="b3862-133">User: %2</span></span>
- <span data-ttu-id="b3862-134">Benutzer 3</span><span class="sxs-lookup"><span data-stu-id="b3862-134">User Defined 3</span></span>
- <span data-ttu-id="b3862-135">Benutzer 4</span><span class="sxs-lookup"><span data-stu-id="b3862-135">User: %4</span></span>
- <span data-ttu-id="b3862-136">Benutzer 5</span><span class="sxs-lookup"><span data-stu-id="b3862-136">User 5</span></span>

<span data-ttu-id="b3862-137">Testen der mehrstufigen Authentifizierung für das Konto „Benutzer 2“.</span><span class="sxs-lookup"><span data-stu-id="b3862-137">Enable and test multi-factor authentication for the User 2 account.</span></span>

## <a name="phase-6-enable-azure-ad-identity-protection"></a><span data-ttu-id="b3862-138">Phase 6: Aktivieren von Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="b3862-138">Phase 6: Enable Azure AD Identity Protection</span></span>

<span data-ttu-id="b3862-139">Befolgen Sie die Anweisungen unter [Phase 2 der Testumgebungsanleitungen für Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="b3862-139">Follow the instructions in [Phase 2 of the password writeback Test Lab Guide](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-enable-and-use-azure-ad-identity-protection).</span></span> 

## <a name="phase-7-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="b3862-140">Phase 7: Aktivieren der modernen Authentifizierung für Exchange Online und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b3862-140">Phase 7: Enable modern authentication for Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="b3862-141">Befolgen Sie die [folgenden Anweisungen](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later) für Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b3862-141">For Exchange Online, follow [these instructions](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later).</span></span> 

<span data-ttu-id="b3862-142">Für Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="b3862-142">Skype for Business Online</span></span>

1. <span data-ttu-id="b3862-143">Stellen Sie eine Verbindung zu [Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) her.</span><span class="sxs-lookup"><span data-stu-id="b3862-143">[Migrate to Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). (Administrator)</span></span>

2. <span data-ttu-id="b3862-144">Führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="b3862-144">Run this command:</span></span>

  ```
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. <span data-ttu-id="b3862-145">Führen Sie den folgenden Befehl aus, um sich zu vergewissern, dass die Änderung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="b3862-145">Ensure that the download was successful with this command.</span></span>

  ```
  Get-CsOAuthConfiguration
  ```

<span data-ttu-id="b3862-146">Das Ergebnis ist eine Testumgebung, die die Anforderungen der [erforderlichen Konfiguration für reine Cloudbereitstellung](identity-access-prerequisites.md#prerequisites) für den Identitäts- und Gerätezugriff erfüllt.</span><span class="sxs-lookup"><span data-stu-id="b3862-146">The result is a test environment that meets the requirements of the [cloud only prerequisite configuration](identity-access-prerequisites.md#prerequisites) for identity and device access.</span></span> 

## <a name="next-step"></a><span data-ttu-id="b3862-147">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="b3862-147">Next step</span></span>

<span data-ttu-id="b3862-148">Verwenden Sie [Gemeinsame Identitäts- und Gerätezugriffsrichtlinien](identity-access-policies.md), um die Richtlinien zu konfigurieren, die auf den Voraussetzungen aufbauen und Identitäten und Geräte schützen.</span><span class="sxs-lookup"><span data-stu-id="b3862-148">Use [Common identity and device access policies](identity-access-policies.md) to configure the policies that build on the prerequisites and test protection for identities and devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3862-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3862-149">See also</span></span>

[<span data-ttu-id="b3862-150">Testumgebungsanleitungen für zusätzliche Identitäten</span><span class="sxs-lookup"><span data-stu-id="b3862-150">Additional identity Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md#identity)

[<span data-ttu-id="b3862-151">Phase 2: Identität</span><span class="sxs-lookup"><span data-stu-id="b3862-151">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="b3862-152">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b3862-152">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="b3862-153">Microsoft 365 Enterprise-Bereitstellungshandbuch</span><span class="sxs-lookup"><span data-stu-id="b3862-153">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="b3862-154">Dokumentation zu Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b3862-154">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
