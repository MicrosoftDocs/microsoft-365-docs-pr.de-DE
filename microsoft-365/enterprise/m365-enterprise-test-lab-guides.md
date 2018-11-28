---
title: Testumgebungsanleitungen für Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2018
ms.audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: Verwenden Sie die folgenden Testumgebungsanleitungen, um Demos, Machbarkeitsstudien oder Entwicklungs-/Testumgebungen für Microsoft 365 Enterprise einzurichten.
ms.openlocfilehash: 77c330772fe1dd145c999eeea6932af68eb7407e
ms.sourcegitcommit: 485273c1679d30443c23366bbaadb53402287c20
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/27/2018
ms.locfileid: "26700648"
---
# <a name="microsoft-365-enterprise-test-lab-guides"></a><span data-ttu-id="7364d-103">Testumgebungsanleitungen für Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7364d-103">Microsoft 365 Enterprise Test Lab Guides</span></span>

<span data-ttu-id="7364d-p101">Mithilfe von Testumgebungsanleitungen können Sie schnell mehr zu Microsoft-Produkten erfahren. Sie enthalten Anweisungen zum Konfigurieren vereinfachter, aber repräsentativer Testumgebungen. Sie können diese Umgebungen für Demos, Anpassungen oder das Erstellen komplexer Machbarkeitsstudien für die Dauer eines Test- oder bezahlten Abonnements verwenden.</span><span class="sxs-lookup"><span data-stu-id="7364d-p101">Test Lab Guides (TLGs) help you quickly learn about Microsoft products. They provide prescriptive instructions to configure simplified but representative test environments. You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription.</span></span> 

<span data-ttu-id="7364d-p102">Testumgebungsanleitungen sind modular aufgebaut. Sie bauen aufeinander auf, sodass mehrere Konfigurationen entstehen, die Ihren Lern- oder Testkonfigurationsanforderungen besser entsprechen. Diese praktische Erfahrung erweitert Ihre Kenntnisse der Bereitstellungsanforderungen neuer Produkte oder Szenarien, sodass Sie besser planen können, wie diese in der Produktionsumgebung gehostet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7364d-p102">TLGs are designed to be modular. They build upon each other to create multiple configurations that more closely match your learning or test configuration needs. The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario so you can better plan for hosting it in production.</span></span>

<span data-ttu-id="7364d-110">Testumgebungsanleitungen ermöglichen die Erstellung repräsentativer Umgebungen zum Entwickeln und Testen von Anwendungen, auch als Entwicklungs-/Testumgebungen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="7364d-110">You can also use TLGs to create representative environments for development and testing of applications, also known as dev/test environments.</span></span>
  
![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="7364d-112">Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="7364d-112">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="base-configuration"></a><span data-ttu-id="7364d-113">Standardkonfiguration</span><span class="sxs-lookup"><span data-stu-id="7364d-113">Base configuration</span></span>

<span data-ttu-id="7364d-p103">Zuerst erstellen Sie eine Testumgebung für [Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/), die Office 365 E5, Enterprise Mobility + Security (EMS) E5 und Windows 10 Enterprise umfasst. Es stehen zwei unterschiedliche Typen von Standardkonfiguration zur Auswahl:</span><span class="sxs-lookup"><span data-stu-id="7364d-p103">First, you create a test environment for [Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) that includes Office 365 E5, Enterprise Mobility + Security (EMS) E5, and Windows 10 Enterprise. You can create two different types of base configurations:</span></span>

- <span data-ttu-id="7364d-116">Verwenden Sie die [einfache Standardkonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md), wenn Sie die Features und Funktionen von Microsoft 365 Enterprise in einer reinen Cloudumgebung konfigurieren und demonstrieren möchten, die keine lokalen Komponenten umfasst.</span><span class="sxs-lookup"><span data-stu-id="7364d-116">Use the [lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 Enterprise features and capabilities in a cloud-only environment, which does not include any on-premises components.</span></span>

- <span data-ttu-id="7364d-117">Verwenden Sie die [simulierte Unternehmensstandardkonfiguration](simulated-ent-base-configuration-microsoft-365-enterprise.md), wenn Sie die Features und Funktionen von Microsoft 365 Enterprise in einer hybriden Cloudumgebung konfigurieren und demonstrieren möchten, die lokale Komponenten wie eine Windows Server Active Directory (AD)-Domäne verwendet.</span><span class="sxs-lookup"><span data-stu-id="7364d-117">Use the [simulated enterprise base configuration](simulated-ent-base-configuration-microsoft-365-enterprise.md) when you want to configure and demonstrate Microsoft 365 Enterprise features and capabilities in a hybrid cloud environment, which uses on-premises components such as a Windows Server Active Directory (AD) domain.</span></span>
    
## <a name="identity"></a><span data-ttu-id="7364d-118">Identität</span><span class="sxs-lookup"><span data-stu-id="7364d-118">Identity</span></span>

<span data-ttu-id="7364d-119">Wie Sie identitätsbezogene Features und Funktionen demonstrieren können, erfahren Sie hier:</span><span class="sxs-lookup"><span data-stu-id="7364d-119">To demonstrate identity-related features and capabilities, see:</span></span>

- [<span data-ttu-id="7364d-120">Kennworthashsynchronisierung</span><span class="sxs-lookup"><span data-stu-id="7364d-120">Password hash synchronization</span></span>](password-hash-sync-m365-ent-test-environment.md)
  
   <span data-ttu-id="7364d-121">Aktivieren und testen Sie die hashbasierte Verzeichnissynchronisierung von einem Windows Server AD-Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="7364d-121">Enable and test password hash-based directory synchronization from a Windows Server AD domain controller.</span></span>

- [<span data-ttu-id="7364d-122">Pass-Through-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="7364d-122">Pass-through authentication</span></span>](pass-through-auth-m365-ent-test-environment.md)
  
   <span data-ttu-id="7364d-123">Aktivieren und testen Sie die Pass-Through-Authentifizierung an einen Windows Server AD-Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="7364d-123">Enable and test pass-through authentication to a Windows Server AD domain controller.</span></span>

- [<span data-ttu-id="7364d-124">Nahtloses einmaliges Anmelden in Azure AD</span><span class="sxs-lookup"><span data-stu-id="7364d-124">Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md)
  
   <span data-ttu-id="7364d-125">Aktivieren und testen Sie das nahtlose einmalige Anmelden in Azure AD mit einem Windows Server AD-Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="7364d-125">Enable and test Azure AD Seamless Single Sign-on (SSO) with a Windows Server AD domain controller.</span></span>

- [<span data-ttu-id="7364d-126">Mehrstufige Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="7364d-126">Multi-factor authentication</span></span>](multi-factor-authentication-microsoft-365-test-environment.md)
  
   <span data-ttu-id="7364d-127">Aktivieren und testen Sie die Smartphone-basierte mehrstufige Authentifizierung für ein bestimmtes Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="7364d-127">Enable and test smart phone-based multi-factor authentication for a specific user account.</span></span>

- [<span data-ttu-id="7364d-128">Schützen von globalen Administratorkonten</span><span class="sxs-lookup"><span data-stu-id="7364d-128">Protect global administrator accounts</span></span>](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   <span data-ttu-id="7364d-129">Sperren Sie Ihre globalen Administratorkonten mit Office 365 Cloud App Security und Richtlinien für bedingten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="7364d-129">Lock down your global administrator accounts with Office 365 Cloud App Security and conditional access policies.</span></span>

- [<span data-ttu-id="7364d-130">Kennwortzurücksetzung</span><span class="sxs-lookup"><span data-stu-id="7364d-130">Password reset</span></span>](password-reset-m365-ent-test-environment.md)

   <span data-ttu-id="7364d-131">Verwenden Sie die Self-Service-Kennwortzurücksetzung, um Ihr Kennwort zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="7364d-131">Use self-service password reset (SSPR) to reset your password.</span></span>

- [<span data-ttu-id="7364d-132">Rückschreiben des Kennworts</span><span class="sxs-lookup"><span data-stu-id="7364d-132">Password writeback</span></span>](password-writeback-m365-ent-test-environment.md)

   <span data-ttu-id="7364d-133">Verwenden Sie das Rückschreiben des Kennworts, um das Kennwort in Ihrem Windows Server AD-Benutzerkonto aus Azure AD zu ändern.</span><span class="sxs-lookup"><span data-stu-id="7364d-133">Use password writeback to change the password on your Windows Server AD user account from Azure AD.</span></span>

- [<span data-ttu-id="7364d-134">Automatische Lizenzierung und Gruppenmitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="7364d-134">Automatic licensing and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md)

   <span data-ttu-id="7364d-135">Machen Sie die Verwaltung neuer Konten durch automatische Lizenzierung und dynamische Gruppenmitgliedschaft einfacher als je zuvor.</span><span class="sxs-lookup"><span data-stu-id="7364d-135">Make administering new accounts easier than ever with automatic licensing and dynamic group membership.</span></span>

- [<span data-ttu-id="7364d-136">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="7364d-136">Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md)

   <span data-ttu-id="7364d-137">Überprüfen Sie Ihre aktuellen Benutzerkonten auf Sicherheitsrisiken.</span><span class="sxs-lookup"><span data-stu-id="7364d-137">Scan your current user accounts for vulnerabilities.</span></span>

## <a name="mobile-device-management"></a><span data-ttu-id="7364d-138">Verwaltung mobiler Geräte</span><span class="sxs-lookup"><span data-stu-id="7364d-138">Mobile device management</span></span>

<span data-ttu-id="7364d-139">Eine Veranschaulichung von Features und Funktionen im Zusammenhang mit der Verwaltung mobiler Geräte finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="7364d-139">To demonstrate mobile device management-related features and capabilities, see:</span></span>

- [<span data-ttu-id="7364d-140">Gerätekompatibilitätsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="7364d-140">Device compliance policies</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="7364d-141">Erstellen Sie eine Benutzergruppe und eine Gerätekompatibilitätsrichtlinie für Windows 10-Geräte.</span><span class="sxs-lookup"><span data-stu-id="7364d-141">Create a user group and a device compliance policy for Windows 10 devices.</span></span>
    
- [<span data-ttu-id="7364d-142">Registrieren von iOS- und Android-Geräten</span><span class="sxs-lookup"><span data-stu-id="7364d-142">Enroll iOS and Android devices</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   <span data-ttu-id="7364d-143">Registrieren Sie iOS- oder Android-Geräte, und verwalten Sie sie remote.</span><span class="sxs-lookup"><span data-stu-id="7364d-143">Enroll iOS or Android devices and manage them remotely.</span></span>


## <a name="information-protection"></a><span data-ttu-id="7364d-144">Schutz von Daten</span><span class="sxs-lookup"><span data-stu-id="7364d-144">Information protection</span></span>

<span data-ttu-id="7364d-145">Eine Veranschaulichung der schutzbezogenen Features und Funktionen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="7364d-145">To demonstrate information protection-related features and capabilities, see:</span></span>

- [<span data-ttu-id="7364d-146">Erhöhte Office 365-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7364d-146">Increased Office 365 security</span></span>](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="7364d-147">Konfigurieren der Einstellungen für höhere Sicherheit von Office 365 und Prüfen der integrierten Sicherheitstools.</span><span class="sxs-lookup"><span data-stu-id="7364d-147">Configure settings for increased Office 365 security and investigate built-in security tools.</span></span>
  
- [<span data-ttu-id="7364d-148">Datenklassifikation</span><span class="sxs-lookup"><span data-stu-id="7364d-148">Data classification</span></span>](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="7364d-149">Konfigurieren und Anwenden von Office 365-Bezeichnungen auf ein Dokument in einer SharePoint Online-Teamwebsite.</span><span class="sxs-lookup"><span data-stu-id="7364d-149">Configure and apply Office 365 labels to a document in a SharePoint Online team site.</span></span>
    
- [<span data-ttu-id="7364d-150">Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="7364d-150">Privileged access management</span></span>](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   <span data-ttu-id="7364d-151">Konfigurieren von Privileged Access Management für Just-in-Time-Zugriff auf privilegierte Aufgaben mit erhöhten Rechten in Ihrer Office 365-Organisation.</span><span class="sxs-lookup"><span data-stu-id="7364d-151">Configure privileged acccess management for just-in-time access to elevated and privileged tasks in your Office 365 organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="7364d-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7364d-152">See also</span></span>

[<span data-ttu-id="7364d-153">Testumgebungsanleitungen zur Cloudakzeptanz</span><span class="sxs-lookup"><span data-stu-id="7364d-153">Experience the Microsoft Cloud with Cloud Adoption Test Lab Guides</span></span>](https://mva.microsoft.com/training-courses/experience-the-microsoft-cloud-with-cloud-adoption-test-lab-guides-17960?l=LXNRdhSLE_1000115881)
    
[<span data-ttu-id="7364d-154">Die One Microsoft Cloud-Testumgebungsanleitung</span><span class="sxs-lookup"><span data-stu-id="7364d-154">One Microsoft Cloud Test Lab Guide stack</span></span>](http://aka.ms/catlgstack)
