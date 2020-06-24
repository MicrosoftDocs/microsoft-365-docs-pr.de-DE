---
title: Testumgebungsanleitungen für Microsoft 365 Enterprise
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: Verwenden Sie die folgenden Testumgebungsanleitungen, um Demos, Machbarkeitsstudien oder Entwicklungs-/Testumgebungen für Microsoft 365 Enterprise einzurichten.
ms.openlocfilehash: 5907edd1bc42b9d679ed020331f225ef2d2b2594
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818741"
---
# <a name="microsoft-365-for-enterprise-test-lab-guides"></a><span data-ttu-id="bf1c3-103">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bf1c3-103">Microsoft 365 for enterprise Test Lab Guides</span></span>

<span data-ttu-id="bf1c3-104">*Dies gilt sowohl für Microsoft 365 Enterprise als auch Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="bf1c3-104">*This applies to both Microsoft 365 for enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="bf1c3-105">Test Lab Guides (TLGs) help you quickly learn about Microsoft products.</span><span class="sxs-lookup"><span data-stu-id="bf1c3-105">Test Lab Guides (TLGs) help you quickly learn about Microsoft products.</span></span> <span data-ttu-id="bf1c3-106">They provide prescriptive instructions to configure simplified but representative test environments.</span><span class="sxs-lookup"><span data-stu-id="bf1c3-106">They provide prescriptive instructions to configure simplified but representative test environments.</span></span> <span data-ttu-id="bf1c3-107">You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span><span class="sxs-lookup"><span data-stu-id="bf1c3-107">You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span></span> 

<span data-ttu-id="bf1c3-108">TLGs are designed to be modular.</span><span class="sxs-lookup"><span data-stu-id="bf1c3-108">TLGs are designed to be modular.</span></span> <span data-ttu-id="bf1c3-109">They build upon each other to create multiple configurations that more closely match your learning or test configuration needs.</span><span class="sxs-lookup"><span data-stu-id="bf1c3-109">They build upon each other to create multiple configurations that more closely match your learning or test configuration needs.</span></span> <span data-ttu-id="bf1c3-110">The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario so you can better plan for hosting it in production.</span><span class="sxs-lookup"><span data-stu-id="bf1c3-110">The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario so you can better plan for hosting it in production.</span></span>

<span data-ttu-id="bf1c3-111">Testumgebungsanleitungen ermöglichen die Erstellung repräsentativer Umgebungen zum Entwickeln und Testen von Anwendungen, auch als Entwicklungs-/Testumgebungen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="bf1c3-111">You can also use TLGs to create representative environments for development and testing of applications, also known as dev/test environments.</span></span>
  
![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

<span data-ttu-id="bf1c3-113">Wechseln Sie zum [Test Labor Leitfaden](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) für eine visuelle Karte aller Artikel im Microsoft 365 for Enterprise Test Lab-Ratgeber Stapel.</span><span class="sxs-lookup"><span data-stu-id="bf1c3-113">Go to the [Test Lab Guide Stack](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>

<span data-ttu-id="bf1c3-114">[![Testumgebungsanleitungen für Microsoft 365 Enterprise](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="bf1c3-114">[![The Microsoft 365 for enterprise Test Lab Guide stack](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)</span></span>

## <a name="base-configuration"></a><span data-ttu-id="bf1c3-115">Standardkonfiguration</span><span class="sxs-lookup"><span data-stu-id="bf1c3-115">Base configuration</span></span>

<span data-ttu-id="bf1c3-116">First, you create a test environment for [Microsoft 365 for enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) that includes Office 365 E5, Enterprise Mobility + Security (EMS) E5, and Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="bf1c3-116">First, you create a test environment for [Microsoft 365 for enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) that includes Office 365 E5, Enterprise Mobility + Security (EMS) E5, and Windows 10 Enterprise.</span></span> <span data-ttu-id="bf1c3-117">You can create two different types of base configurations:</span><span class="sxs-lookup"><span data-stu-id="bf1c3-117">You can create two different types of base configurations:</span></span>

- <span data-ttu-id="bf1c3-118">Verwenden Sie die [einfache Standardkonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md), wenn Sie die Features und Funktionen von Microsoft 365 Enterprise in einer reinen Cloudumgebung konfigurieren und demonstrieren möchten, die keine lokalen Komponenten umfasst.</span><span class="sxs-lookup"><span data-stu-id="bf1c3-118">Use the [lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a cloud-only environment, which does not include any on-premises components.</span></span>

- <span data-ttu-id="bf1c3-119">Verwenden Sie die [simulierte Unternehmensstandardkonfiguration](simulated-ent-base-configuration-microsoft-365-enterprise.md), wenn Sie die Features und Funktionen von Microsoft 365 Enterprise in einer hybriden Cloudumgebung konfigurieren und demonstrieren möchten, die lokale Komponenten wie eine Active Directory Domain Services (AD DS)-Domäne verwendet.</span><span class="sxs-lookup"><span data-stu-id="bf1c3-119">Use the [simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a hybrid cloud environment, which uses on-premises components such as an Active Directory Domain Services (AD DS) domain.</span></span>

<span data-ttu-id="bf1c3-120">Sie können auch Testumgebungen für Office 365 E5 erstellen, ohne die Microsoft 365 E5-Lizenz zu Ihrer Test- oder Produktionstestumgebung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="bf1c3-120">You can also create test environments for Office 365 E5 by not adding the Microsoft 365 E5 license to your trial or production test environment.</span></span>
    
## <a name="identity"></a><span data-ttu-id="bf1c3-121">Identität</span><span class="sxs-lookup"><span data-stu-id="bf1c3-121">Identity</span></span>

<span data-ttu-id="bf1c3-122">Wie Sie identitätsbezogene Features und Funktionen demonstrieren können, erfahren Sie hier:</span><span class="sxs-lookup"><span data-stu-id="bf1c3-122">To demonstrate identity-related features and capabilities, see:</span></span>

- [<span data-ttu-id="bf1c3-123">Kennworthashsynchronisierung</span><span class="sxs-lookup"><span data-stu-id="bf1c3-123">Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)
  
   <span data-ttu-id="bf1c3-124">Aktivieren und testen Sie die auf Kennworthash basierte Verzeichnissynchronisierung von einem AD DS-Domänencontroller aus.</span><span class="sxs-lookup"><span data-stu-id="bf1c3-124">Enable and test password hash-based directory synchronization from an AD DS domain controller.</span></span>

- [<span data-ttu-id="bf1c3-125">Pass-Through-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="bf1c3-125">Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md)
  
   <span data-ttu-id="bf1c3-126">Aktivieren und testen Sie die Pass-Through-Authentifizierung an einen AD DS-Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="bf1c3-126">Enable and test pass-through authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="bf1c3-127">Verbundauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="bf1c3-127">Federated authentication</span></span>](federated-identity-for-your-office-365-dev-test-environment.md)
  
   <span data-ttu-id="bf1c3-128">Aktivieren und testen Sie die Verbundauthentifizierung an einen AD DS-Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="bf1c3-128">Enable and test federated authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="bf1c3-129">Nahtloses einmaliges Anmelden in Azure AD</span><span class="sxs-lookup"><span data-stu-id="bf1c3-129">Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md)
  
   <span data-ttu-id="bf1c3-130">Aktivieren und testen Sie das nahtlose einmalige Anmelden in Azure AD mit einem AD DS-Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="bf1c3-130">Enable and test Azure AD Seamless Single Sign-on (SSO) with an AD DS domain controller.</span></span>

- [<span data-ttu-id="bf1c3-131">Mehrstufige Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="bf1c3-131">Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md)
  
   <span data-ttu-id="bf1c3-132">Aktivieren und testen Sie die Smartphone-basierte mehrstufige Authentifizierung für ein bestimmtes Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="bf1c3-132">Enable and test smart phone-based multi-factor authentication for a specific user account.</span></span>

- [<span data-ttu-id="bf1c3-133">Schützen von globalen Administratorkonten</span><span class="sxs-lookup"><span data-stu-id="bf1c3-133">Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   <span data-ttu-id="bf1c3-134">Sperren Sie Ihre globalen Administratorkonten mit Richtlinien für bedingten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="bf1c3-134">Lock down your global administrator accounts with conditional access policies.</span></span>

- [<span data-ttu-id="bf1c3-135">Rückschreiben des Kennworts</span><span class="sxs-lookup"><span data-stu-id="bf1c3-135">Password writeback</span></span>](password-writeback-m365-ent-test-environment.md)

   <span data-ttu-id="bf1c3-136">Verwenden Sie das Rückschreiben des Kennworts, um das Kennwort in Ihrem AD DS-Benutzerkonto aus Azure AD zu ändern.</span><span class="sxs-lookup"><span data-stu-id="bf1c3-136">Use password writeback to change the password on your AD DS user account from Azure AD.</span></span>

- [<span data-ttu-id="bf1c3-137">Kennwortzurücksetzung</span><span class="sxs-lookup"><span data-stu-id="bf1c3-137">Password reset</span></span>](password-reset-m365-ent-test-environment.md)

   <span data-ttu-id="bf1c3-138">Verwenden Sie die Self-Service-Kennwortzurücksetzung, um Ihr Kennwort zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="bf1c3-138">Use self-service password reset (SSPR) to reset your password.</span></span>

- [<span data-ttu-id="bf1c3-139">Automatische Lizenzierung und Gruppenmitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="bf1c3-139">Automatic licensing and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md)

   <span data-ttu-id="bf1c3-140">Machen Sie die Verwaltung neuer Konten durch automatische Lizenzierung und dynamische Gruppenmitgliedschaft einfacher als je zuvor.</span><span class="sxs-lookup"><span data-stu-id="bf1c3-140">Make administering new accounts easier than ever with automatic licensing and dynamic group membership.</span></span>

- [<span data-ttu-id="bf1c3-141">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="bf1c3-141">Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md)

   <span data-ttu-id="bf1c3-142">Überprüfen Sie Ihre aktuellen Benutzerkonten auf Sicherheitsrisiken.</span><span class="sxs-lookup"><span data-stu-id="bf1c3-142">Scan your current user accounts for vulnerabilities.</span></span>

- [<span data-ttu-id="bf1c3-143">Identitäts- und Gerätezugriff</span><span class="sxs-lookup"><span data-stu-id="bf1c3-143">Identity and device access</span></span>](identity-device-access-m365-test-environment.md)

   <span data-ttu-id="bf1c3-144">Erstellen Sie eine Umgebung, um empfohlene Konfigurationen für Identitäts- und Gerätezugriff sowie Richtlinien für bedingten Zugriff zu testen.</span><span class="sxs-lookup"><span data-stu-id="bf1c3-144">Create an environment to test recommended identity and device access configurations and conditional access policies.</span></span>


## <a name="mobile-device-management"></a><span data-ttu-id="bf1c3-145">Verwaltung mobiler Geräte</span><span class="sxs-lookup"><span data-stu-id="bf1c3-145">Mobile device management</span></span>

<span data-ttu-id="bf1c3-146">Eine Veranschaulichung von Features und Funktionen im Zusammenhang mit der Verwaltung mobiler Geräte finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="bf1c3-146">To demonstrate mobile device management-related features and capabilities, see:</span></span>

- [<span data-ttu-id="bf1c3-147">Gerätekompatibilitätsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="bf1c3-147">Device compliance policies</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="bf1c3-148">Erstellen Sie eine Benutzergruppe und eine Gerätekompatibilitätsrichtlinie für Windows 10-Geräte.</span><span class="sxs-lookup"><span data-stu-id="bf1c3-148">Create a user group and a device compliance policy for Windows 10 devices.</span></span>
    
- [<span data-ttu-id="bf1c3-149">Registrieren von iOS- und Android-Geräten</span><span class="sxs-lookup"><span data-stu-id="bf1c3-149">Enroll iOS and Android devices</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   <span data-ttu-id="bf1c3-150">Registrieren Sie iOS- oder Android-Geräte, und verwalten Sie sie remote.</span><span class="sxs-lookup"><span data-stu-id="bf1c3-150">Enroll iOS or Android devices and manage them remotely.</span></span>


## <a name="information-protection"></a><span data-ttu-id="bf1c3-151">Schutz von Daten</span><span class="sxs-lookup"><span data-stu-id="bf1c3-151">Information protection</span></span>

<span data-ttu-id="bf1c3-152">Eine Veranschaulichung der schutzbezogenen Features und Funktionen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="bf1c3-152">To demonstrate information protection-related features and capabilities, see:</span></span>

- [<span data-ttu-id="bf1c3-153">Erhöhte Sicherheit in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bf1c3-153">Increased Microsoft 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="bf1c3-154">Konfigurieren der Einstellungen für höhere Sicherheit von Microsoft 365 und Prüfen der integrierten Sicherheitstools.</span><span class="sxs-lookup"><span data-stu-id="bf1c3-154">Configure settings for increased Microsoft 365 security and investigate built-in security tools.</span></span>
  
- [<span data-ttu-id="bf1c3-155">Datenklassifikation</span><span class="sxs-lookup"><span data-stu-id="bf1c3-155">Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="bf1c3-156">Konfigurieren und Anwenden von Bezeichnungen auf ein Dokument in einer SharePoint Online-Teamwebsite.</span><span class="sxs-lookup"><span data-stu-id="bf1c3-156">Configure and apply labels to a document in a SharePoint Online team site.</span></span>
    
- [<span data-ttu-id="bf1c3-157">Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="bf1c3-157">Privileged access management</span></span>](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="bf1c3-158">Konfigurieren von Privileged Access Management für Just-in-Time-Zugriff auf privilegierte Aufgaben mit erhöhten Rechten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="bf1c3-158">Configure privileged access management for just-in-time access to elevated and privileged tasks in your organization.</span></span>


