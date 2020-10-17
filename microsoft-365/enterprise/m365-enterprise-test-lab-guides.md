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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: Verwenden Sie die folgenden Testumgebungsanleitungen, um Demos, Machbarkeitsstudien oder Entwicklungs-/Testumgebungen für Microsoft 365 Enterprise einzurichten.
ms.openlocfilehash: fefbb18fd108dceba6f387fb8244619c4bb1c167
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487470"
---
# <a name="microsoft-365-for-enterprise-test-lab-guides"></a><span data-ttu-id="bb52a-103">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bb52a-103">Microsoft 365 for enterprise Test Lab Guides</span></span>

<span data-ttu-id="bb52a-104">*Dies gilt sowohl für Microsoft 365 Enterprise als auch Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="bb52a-104">*This applies to both Microsoft 365 for enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="bb52a-p101">Mithilfe von Testumgebungsanleitungen können Sie schnell mehr zu Microsoft-Produkten erfahren. Sie enthalten Anweisungen zum Konfigurieren vereinfachter, aber repräsentativer Testumgebungen. Sie können diese Umgebungen für Demos, Anpassungen oder das Erstellen komplexer Machbarkeitsstudien für die Dauer eines Test- oder bezahlten Abonnements verwenden.</span><span class="sxs-lookup"><span data-stu-id="bb52a-p101">Test Lab Guides (TLGs) help you quickly learn about Microsoft products. They provide prescriptive instructions to configure simplified but representative test environments. You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span></span>

<span data-ttu-id="bb52a-p102">TLGs sind modular aufgebaut. Sie basieren auf einander, um mehrere Konfigurationen zu erstellen, die ihren Lern-oder Test Konfigurationsanforderungen besser entsprechen. Das "Ich habe mich selbst und es funktioniert"-praktische Erfahrung hilft Ihnen, die Bereitstellungsanforderungen eines neuen Produkts oder Szenarios zu verstehen, damit Sie das Hosting in der Produktion besser planen können.</span><span class="sxs-lookup"><span data-stu-id="bb52a-p102">TLGs are designed to be modular. They build upon each other to create multiple configurations that more closely match your learning or test configuration needs. The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario, so that you can better plan for hosting it in production.</span></span>

<span data-ttu-id="bb52a-111">Sie können auch TLGs verwenden, um repräsentative Umgebungen zum entwickeln und Testen von Anwendungen zu erstellen, die auch als Entwicklungs-/Testumgebungen bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="bb52a-111">You can also use TLGs to create representative environments to develop and test applications, also known as dev/test environments.</span></span>
  
![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

<span data-ttu-id="bb52a-113">Für eine visuelle Zuordnung zu allen Artikeln im Stapel Microsoft 365 for Enterprise Test Lab Guide erweitern Sie die folgende Grafik, oder wechseln Sie zu [Microsoft 365 für Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="bb52a-113">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, expand the following graphic or go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

<span data-ttu-id="bb52a-114">[![Testumgebungsanleitungen für Microsoft 365 Enterprise](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="bb52a-114">[![The Microsoft 365 for enterprise Test Lab Guide stack](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span></span>

## <a name="base-configuration"></a><span data-ttu-id="bb52a-115">Standardkonfiguration</span><span class="sxs-lookup"><span data-stu-id="bb52a-115">Base configuration</span></span>

<span data-ttu-id="bb52a-p103">Erstellen Sie zunächst eine Testumgebung für [Microsoft 365 für Unternehmen](https://docs.microsoft.com/microsoft-365-enterprise/). Sie können zwei verschiedene Typen von Basiskonfigurationen erstellen:</span><span class="sxs-lookup"><span data-stu-id="bb52a-p103">First, create a test environment for [Microsoft 365 for enterprise](https://docs.microsoft.com/microsoft-365-enterprise/). You can create two different types of base configurations:</span></span>

- <span data-ttu-id="bb52a-118">[Einfache Basiskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md) : Verwenden Sie dies, wenn Sie Microsoft 365 für Enterprise-Features und-Funktionen in einer nur-Cloud-Umgebung konfigurieren und demonstrieren möchten, die keine lokalen Komponenten enthält.</span><span class="sxs-lookup"><span data-stu-id="bb52a-118">[Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md) - Use this when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a cloud-only environment, which does not include any on-premises components.</span></span>

- <span data-ttu-id="bb52a-119">[Simulierte unternehmensbasierte Konfiguration](simulated-ent-base-configuration-microsoft-365-enterprise.md) : Verwenden Sie dies, wenn Sie Microsoft 365 für Enterprise-Features und-Funktionen in einer hybriden Cloud-Umgebung konfigurieren und demonstrieren möchten, in der lokale Komponenten wie eine Active Directory-Domänendienste (AD DS) Domäne verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bb52a-119">[Simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) - Use this when you want to configure and demonstrate Microsoft 365 for enterprise features and capabilities in a hybrid cloud environment, which uses on-premises components such as an Active Directory Domain Services (AD DS) domain.</span></span>

<span data-ttu-id="bb52a-120">Sie können auch Testumgebungen für Office 365 E5 erstellen, ohne die Microsoft 365 E5-Lizenz zu Ihrer Test- oder Produktionstestumgebung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="bb52a-120">You can also create test environments for Office 365 E5 by not adding the Microsoft 365 E5 license to your trial or production test environment.</span></span>
    
## <a name="identity"></a><span data-ttu-id="bb52a-121">Identität</span><span class="sxs-lookup"><span data-stu-id="bb52a-121">Identity</span></span>

<span data-ttu-id="bb52a-122">Wie Sie identitätsbezogene Features und Funktionen demonstrieren können, erfahren Sie hier:</span><span class="sxs-lookup"><span data-stu-id="bb52a-122">To demonstrate identity-related features and capabilities, see:</span></span>

- [<span data-ttu-id="bb52a-123">Kennworthashsynchronisierung</span><span class="sxs-lookup"><span data-stu-id="bb52a-123">Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)
  
   <span data-ttu-id="bb52a-124">Aktivieren und testen Sie die auf Kennworthash basierte Verzeichnissynchronisierung von einem AD DS-Domänencontroller aus.</span><span class="sxs-lookup"><span data-stu-id="bb52a-124">Enable and test password hash-based directory synchronization from an AD DS domain controller.</span></span>

- [<span data-ttu-id="bb52a-125">Pass-Through-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="bb52a-125">Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md)
  
   <span data-ttu-id="bb52a-126">Aktivieren und testen Sie die Pass-Through-Authentifizierung an einen AD DS-Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="bb52a-126">Enable and test pass-through authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="bb52a-127">Verbundauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="bb52a-127">Federated authentication</span></span>](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
   <span data-ttu-id="bb52a-128">Aktivieren und testen Sie die Verbundauthentifizierung an einen AD DS-Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="bb52a-128">Enable and test federated authentication to an AD DS domain controller.</span></span>

- [<span data-ttu-id="bb52a-129">Nahtloses einmaliges Anmelden in Azure AD</span><span class="sxs-lookup"><span data-stu-id="bb52a-129">Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md)
  
   <span data-ttu-id="bb52a-130">Aktivieren und testen Sie Azure AD nahtloses einmaliges Anmelden (Seamless SSO) mit einem AD DS Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="bb52a-130">Enable and test Azure AD Seamless Single Sign-on (Seamless SSO) with an AD DS domain controller.</span></span>

- [<span data-ttu-id="bb52a-131">Mehrstufige Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="bb52a-131">Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md)
  
   <span data-ttu-id="bb52a-132">Aktivieren und testen Sie die Smartphone-basierte mehrstufige Authentifizierung für ein bestimmtes Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="bb52a-132">Enable and test smart phone-based multi-factor authentication for a specific user account.</span></span>

- [<span data-ttu-id="bb52a-133">Schützen von globalen Administratorkonten</span><span class="sxs-lookup"><span data-stu-id="bb52a-133">Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md)

   <span data-ttu-id="bb52a-134">Sperren Sie Ihre globalen Administratorkonten mit Richtlinien für bedingten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="bb52a-134">Lock down your global administrator accounts with conditional access policies.</span></span>

- [<span data-ttu-id="bb52a-135">Rückschreiben des Kennworts</span><span class="sxs-lookup"><span data-stu-id="bb52a-135">Password writeback</span></span>](password-writeback-m365-ent-test-environment.md)

   <span data-ttu-id="bb52a-136">Verwenden Sie das Rückschreiben des Kennworts, um das Kennwort in Ihrem AD DS-Benutzerkonto aus Azure AD zu ändern.</span><span class="sxs-lookup"><span data-stu-id="bb52a-136">Use password writeback to change the password on your AD DS user account from Azure AD.</span></span>

- [<span data-ttu-id="bb52a-137">Kennwortzurücksetzung</span><span class="sxs-lookup"><span data-stu-id="bb52a-137">Password reset</span></span>](password-reset-m365-ent-test-environment.md)

   <span data-ttu-id="bb52a-138">Verwenden Sie die Self-Service-Kennwortzurücksetzung, um Ihr Kennwort zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="bb52a-138">Use self-service password reset to reset your password.</span></span>

- [<span data-ttu-id="bb52a-139">Automatische Lizenzierung und Gruppenmitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="bb52a-139">Automatic licensing and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md)

   <span data-ttu-id="bb52a-140">Machen Sie die Verwaltung neuer Konten durch automatische Lizenzierung und dynamische Gruppenmitgliedschaft einfacher als je zuvor.</span><span class="sxs-lookup"><span data-stu-id="bb52a-140">Make administering new accounts easier than ever with automatic licensing and dynamic group membership.</span></span>

- [<span data-ttu-id="bb52a-141">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="bb52a-141">Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md)

   <span data-ttu-id="bb52a-142">Überprüfen Sie Ihre aktuellen Benutzerkonten auf Sicherheitsrisiken.</span><span class="sxs-lookup"><span data-stu-id="bb52a-142">Scan your current user accounts for vulnerabilities.</span></span>

- [<span data-ttu-id="bb52a-143">Identitäts- und Gerätezugriff</span><span class="sxs-lookup"><span data-stu-id="bb52a-143">Identity and device access</span></span>](identity-device-access-m365-test-environment.md)

   <span data-ttu-id="bb52a-144">Erstellen Sie eine Umgebung, um empfohlene Konfigurationen für Identitäts- und Gerätezugriff sowie Richtlinien für bedingten Zugriff zu testen.</span><span class="sxs-lookup"><span data-stu-id="bb52a-144">Create an environment to test recommended identity and device access configurations and conditional access policies.</span></span>

## <a name="mobile-device-management"></a><span data-ttu-id="bb52a-145">Verwaltung mobiler Geräte</span><span class="sxs-lookup"><span data-stu-id="bb52a-145">Mobile device management</span></span>

<span data-ttu-id="bb52a-146">Eine Veranschaulichung von Features und Funktionen im Zusammenhang mit der Verwaltung mobiler Geräte finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="bb52a-146">To demonstrate mobile device management-related features and capabilities, see:</span></span>

- [<span data-ttu-id="bb52a-147">Gerätekompatibilitätsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="bb52a-147">Device compliance policies</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="bb52a-148">Erstellen Sie eine Benutzergruppe und eine Gerätekompatibilitätsrichtlinie für Windows 10-Geräte.</span><span class="sxs-lookup"><span data-stu-id="bb52a-148">Create a user group and a device compliance policy for Windows 10 devices.</span></span>
    
- [<span data-ttu-id="bb52a-149">Registrieren von iOS- und Android-Geräten</span><span class="sxs-lookup"><span data-stu-id="bb52a-149">Enroll iOS and Android devices</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   <span data-ttu-id="bb52a-150">Registrieren Sie iOS- oder Android-Geräte, und verwalten Sie sie remote.</span><span class="sxs-lookup"><span data-stu-id="bb52a-150">Enroll iOS or Android devices and manage them remotely.</span></span>

## <a name="information-protection"></a><span data-ttu-id="bb52a-151">Schutz von Daten</span><span class="sxs-lookup"><span data-stu-id="bb52a-151">Information protection</span></span>

<span data-ttu-id="bb52a-152">Eine Veranschaulichung der schutzbezogenen Features und Funktionen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="bb52a-152">To demonstrate information protection-related features and capabilities, see:</span></span>

- [<span data-ttu-id="bb52a-153">Erhöhte Sicherheit in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bb52a-153">Increased Microsoft 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="bb52a-154">Konfigurieren der Einstellungen für höhere Sicherheit von Microsoft 365 und Prüfen der integrierten Sicherheitstools.</span><span class="sxs-lookup"><span data-stu-id="bb52a-154">Configure settings for increased Microsoft 365 security and investigate built-in security tools.</span></span>
  
- [<span data-ttu-id="bb52a-155">Datenklassifikation</span><span class="sxs-lookup"><span data-stu-id="bb52a-155">Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="bb52a-156">Konfigurieren und Anwenden von Bezeichnungen auf ein Dokument in einer SharePoint Online-Teamwebsite.</span><span class="sxs-lookup"><span data-stu-id="bb52a-156">Configure and apply labels to a document in a SharePoint Online team site.</span></span>
    
- [<span data-ttu-id="bb52a-157">Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="bb52a-157">Privileged access management</span></span>](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="bb52a-158">Konfigurieren von Privileged Access Management für Just-in-Time-Zugriff auf privilegierte Aufgaben mit erhöhten Rechten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="bb52a-158">Configure privileged access management for just-in-time access to elevated and privileged tasks in your organization.</span></span>
