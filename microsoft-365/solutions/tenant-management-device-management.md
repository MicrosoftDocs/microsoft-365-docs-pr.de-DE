---
title: 'Schritt 5: Geräte- und App-Verwaltung für Ihre Microsoft 365 for Enterprise-Mandanten'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Stellen Sie die richtige Option für die Geräte- und App-Verwaltung für Ihre Microsoft 365-Mandanten zur Auswahl.
ms.openlocfilehash: 994ab7d21ae70307fa78e1f7249d39ac314a7358
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904612"
---
# <a name="step-5-device-and-app-management-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="90a3e-104">Schritt 5:</span><span class="sxs-lookup"><span data-stu-id="90a3e-104">Step 5.</span></span> <span data-ttu-id="90a3e-105">Geräte- und App-Verwaltung für Ihre Microsoft 365 for Enterprise-Mandanten</span><span class="sxs-lookup"><span data-stu-id="90a3e-105">Device and app management for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="90a3e-106">Microsoft 365 for Enterprise enthält Features, mit denen Sie Geräte und die Verwendung von Apps auf diesen Geräten in Ihrer Organisation mit mobiler Geräteverwaltung (Mobile Device Management, MDM) und mobiler Anwendungsverwaltung (MOBILE Application Management, MAM) verwalten können.</span><span class="sxs-lookup"><span data-stu-id="90a3e-106">Microsoft 365 for enterprise includes features to help manage devices and the use of apps on those devices within your organization with mobile device management (MDM) and mobile application management (MAM).</span></span> <span data-ttu-id="90a3e-107">Sie können iOS-, Android-, macOS- und Windows-Geräte verwalten, um den Zugriff auf die Ressourcen Ihrer Organisation, einschließlich Ihrer Daten, zu schützen.</span><span class="sxs-lookup"><span data-stu-id="90a3e-107">You can manage iOS, Android, macOS, and Windows devices to protect access to your organization's resources, including your data.</span></span> <span data-ttu-id="90a3e-108">Sie können beispielsweise verhindern, dass E-Mails an Personen außerhalb Ihrer Organisation gesendet werden, oder Sie können Organisationsdaten von personenbezogenen Daten auf den persönlichen Geräten Ihrer Mitarbeiter isolieren.</span><span class="sxs-lookup"><span data-stu-id="90a3e-108">For example, you can prevent emails from being sent to people outside your organization or isolate organization data from personal data on your worker's personal devices.</span></span>

<span data-ttu-id="90a3e-109">Hier ist ein Beispiel für die Überprüfung und Verwaltung von Benutzern, deren Geräten und deren Verwendung lokaler und Cloudproduktivitäts-Apps wie Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="90a3e-109">Here is an example of the validation and management of users, their devices, and their use of local and cloud productivity apps like Microsoft Teams.</span></span>

![Überprüfung und Verwaltung von Benutzern, Geräten und Apps](../media/tenant-management-overview/tenant-management-device-app-mgmt.png)

<span data-ttu-id="90a3e-111">Um Die Ressourcen Ihrer Organisation zu schützen und zu schützen, enthält Microsoft 365 For Enterprise Features, mit deren Hilfe Geräte und deren Zugriff auf Apps verwaltet werden können.</span><span class="sxs-lookup"><span data-stu-id="90a3e-111">To help you secure and protect your organization's resources, Microsoft 365 for enterprise includes features to help manage devices and their access to apps.</span></span> <span data-ttu-id="90a3e-112">Es gibt zwei Optionen für die Geräteverwaltung:</span><span class="sxs-lookup"><span data-stu-id="90a3e-112">There are two options for device management:</span></span>

- <span data-ttu-id="90a3e-113">Microsoft Intune, eine umfassende Geräte- und App-Verwaltungslösung für Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="90a3e-113">Microsoft Intune, which is a comprehensive device and app management solution for enterprises.</span></span>
- <span data-ttu-id="90a3e-114">Grundlegende Mobilität und Sicherheit, eine Teilmenge der Intune-Dienste, die in allen Microsoft 365-Produkten zum Verwalten von Geräten in Ihrer Organisation enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="90a3e-114">Basic Mobility and Security, which is a subset of Intune services included with all Microsoft 365 products for managing devices in your organization.</span></span> <span data-ttu-id="90a3e-115">Weitere Informationen finden Sie unter [Capabilities of Basic Mobility and Security](../admin/basic-mobility-security/capabilities.md).</span><span class="sxs-lookup"><span data-stu-id="90a3e-115">For more information, see [Capabilities of Basic Mobility and Security](../admin/basic-mobility-security/capabilities.md).</span></span>

<span data-ttu-id="90a3e-116">Wenn Sie über Microsoft 365 E3 oder E5 verfügen, sollten Sie Intune verwenden.</span><span class="sxs-lookup"><span data-stu-id="90a3e-116">If you have Microsoft 365 E3 or E5, you should use Intune.</span></span>

## <a name="microsoft-intune"></a><span data-ttu-id="90a3e-117">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="90a3e-117">Microsoft Intune</span></span>

<span data-ttu-id="90a3e-118">Sie verwenden [Microsoft Intune,](/mem/intune/fundamentals/planning-guide) um den Zugriff auf Ihre Organisation mithilfe von MDM oder MAM zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="90a3e-118">You use [Microsoft Intune](/mem/intune/fundamentals/planning-guide) to manage access to your organization using MDM or MAM.</span></span> <span data-ttu-id="90a3e-119">MDM ist, wenn Benutzer ihre Geräte in Intune "registrieren".</span><span class="sxs-lookup"><span data-stu-id="90a3e-119">MDM is when users "enroll" their devices in Intune.</span></span> <span data-ttu-id="90a3e-120">Nach der Registrierung eines Geräts handelt es sich um ein verwaltetes Gerät, das die Richtlinien, Regeln und Einstellungen Ihrer Organisation empfangen kann.</span><span class="sxs-lookup"><span data-stu-id="90a3e-120">After a device is enrolled, it is a managed device and can receive your organization's  policies, rules, and settings.</span></span> <span data-ttu-id="90a3e-121">Sie können beispielsweise bestimmte Apps installieren, eine Kennwortrichtlinie erstellen, eine VPN-Verbindung installieren und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="90a3e-121">For example, you can install specific apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="90a3e-122">Benutzer mit ihren eigenen persönlichen Geräten möchten ihre Geräte möglicherweise nicht registrieren oder von Intune und den Richtlinien Ihrer Organisation verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="90a3e-122">Users with their own personal devices may not want to enroll their devices or be managed by Intune and your organization's policies.</span></span> <span data-ttu-id="90a3e-123">Sie müssen jedoch weiterhin die Ressourcen und Daten Ihrer Organisation schützen.</span><span class="sxs-lookup"><span data-stu-id="90a3e-123">But you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="90a3e-124">In diesem Szenario können Sie Ihre Apps mithilfe von MAM schützen.</span><span class="sxs-lookup"><span data-stu-id="90a3e-124">In this scenario, you can protect your apps using MAM.</span></span> <span data-ttu-id="90a3e-125">Sie können beispielsweise eine MAM-Richtlinie verwenden, für die ein Benutzer beim Zugriff auf SharePoint auf dem Gerät eine PIN eingeben muss.</span><span class="sxs-lookup"><span data-stu-id="90a3e-125">For example, you can use an MAM policy that requires a user to enter a PIN when accessing SharePoint on the device.</span></span>

<span data-ttu-id="90a3e-126">Außerdem bestimmen Sie, wie Sie persönliche Geräte und geräte im Besitz der Organisation verwalten.</span><span class="sxs-lookup"><span data-stu-id="90a3e-126">You'll also determine how you're going to manage personal devices and organization-owned devices.</span></span> <span data-ttu-id="90a3e-127">Sie können Geräte je nach Verwendung unterschiedlich behandeln.</span><span class="sxs-lookup"><span data-stu-id="90a3e-127">You might want to treat devices differently, depending on their uses.</span></span>

## <a name="identity-and-device-access-configurations"></a><span data-ttu-id="90a3e-128">Konfigurationen für den Identitäts- und Gerätezugriff</span><span class="sxs-lookup"><span data-stu-id="90a3e-128">Identity and device access configurations</span></span>

<span data-ttu-id="90a3e-129">Microsoft bietet eine Reihe von Konfigurationen für den Identitäts- und [Gerätezugriff,](../security/office-365-security/microsoft-365-policies-configurations.md) um eine sichere und produktive Belegschaft sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="90a3e-129">Microsoft provides a set of configurations for [identity and device access](../security/office-365-security/microsoft-365-policies-configurations.md) to ensure a secure and productive workforce.</span></span> <span data-ttu-id="90a3e-130">Diese Konfigurationen umfassen die Verwendung von:</span><span class="sxs-lookup"><span data-stu-id="90a3e-130">These configurations include the use of:</span></span>

- <span data-ttu-id="90a3e-131">Azure AD-Richtlinien für den bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="90a3e-131">Azure AD Conditional Access policies</span></span>
- <span data-ttu-id="90a3e-132">Microsoft Intune-Richtlinien für Gerätekonformität und App-Schutz</span><span class="sxs-lookup"><span data-stu-id="90a3e-132">Microsoft Intune device compliance and app protection policies</span></span>
- <span data-ttu-id="90a3e-133">Azure AD Identity Protection-Benutzerrisikorichtlinien</span><span class="sxs-lookup"><span data-stu-id="90a3e-133">Azure AD Identity Protection user risk policies</span></span>
- <span data-ttu-id="90a3e-134">Zusätzliche Richtlinien von Cloud-Apps</span><span class="sxs-lookup"><span data-stu-id="90a3e-134">Additional policies of cloud apps</span></span>

<span data-ttu-id="90a3e-135">Hier ist ein Beispiel für die Anwendung dieser Einstellungen und Richtlinien zum Überprüfen und Einschränken von Benutzern, deren Geräten und deren Verwendung lokaler und Cloudproduktivitäts-Apps wie Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="90a3e-135">Here is an example of the application of these settings and policies to validate and restrict users, their devices, and their use of local and cloud productivity apps like Microsoft Teams.</span></span>

![Identitäts- und Gerätezugriffskonfigurationen für Anforderungen und Einschränkungen für Benutzer, ihre Geräte und deren Verwendung von Apps](../media/tenant-management-overview/tenant-management-device-app-mgmt-golden-config.png)

<span data-ttu-id="90a3e-137">Verwenden Sie für den Gerätezugriff und die App-Verwaltung die Konfigurationen in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="90a3e-137">For device access and app management, use the configurations in these articles:</span></span>

- [<span data-ttu-id="90a3e-138">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="90a3e-138">Prerequisites</span></span>](../security/office-365-security/identity-access-prerequisites.md)
- [<span data-ttu-id="90a3e-139">Allgemeine Identitäts- und Gerätezugriffsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="90a3e-139">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)

## <a name="results-of-step-5"></a><span data-ttu-id="90a3e-140">Ergebnisse von Schritt 5</span><span class="sxs-lookup"><span data-stu-id="90a3e-140">Results of Step 5</span></span>

<span data-ttu-id="90a3e-141">Für die Geräte- und App-Verwaltung für Ihren Microsoft 365-Mandanten haben Sie die Intune-Einstellungen und -Richtlinien festgelegt, um Benutzer, ihre Geräte und deren Verwendung lokaler und Cloudproduktivitäts-Apps zu überprüfen und einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="90a3e-141">For device and app management for your Microsoft 365 tenant, you have determined the Intune settings and policies to validate and restrict users, their devices, and their use of local and cloud productivity apps.</span></span>

<span data-ttu-id="90a3e-142">Im Folgenden finden Sie ein Beispiel für einen Mandanten mit Intune-Geräte- und App-Verwaltung mit hervorgehobenen neuen Elementen.</span><span class="sxs-lookup"><span data-stu-id="90a3e-142">Here is an example of a tenant with Intune device and app management with the new elements highlighted.</span></span>

![Beispiel für einen Mandanten mit Intune-Geräte- und App-Verwaltung](../media/tenant-management-overview/tenant-management-tenant-build-step5.png)

<span data-ttu-id="90a3e-144">In dieser Abbildung verfügt der Mandant über:</span><span class="sxs-lookup"><span data-stu-id="90a3e-144">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="90a3e-145">Geräte im Besitz der Organisation, die in Intune registriert sind.</span><span class="sxs-lookup"><span data-stu-id="90a3e-145">Organization-owned devices enrolled in Intune.</span></span>
- <span data-ttu-id="90a3e-146">Intune-Geräte- und App-Richtlinien für registrierte und persönliche Geräte.</span><span class="sxs-lookup"><span data-stu-id="90a3e-146">Intune device and app policies for enrolled and personal devices.</span></span>

## <a name="ongoing-maintenance-for-device-and-app-management"></a><span data-ttu-id="90a3e-147">Fortlaufende Wartung der Geräte- und App-Verwaltung</span><span class="sxs-lookup"><span data-stu-id="90a3e-147">Ongoing maintenance for device and app management</span></span>

<span data-ttu-id="90a3e-148">Auf fortlaufender Basis müssen Sie möglicherweise:</span><span class="sxs-lookup"><span data-stu-id="90a3e-148">On an ongoing basis, you might need to:</span></span> 

- <span data-ttu-id="90a3e-149">Verwalten der Geräteregistrierung.</span><span class="sxs-lookup"><span data-stu-id="90a3e-149">Manage device enrollment.</span></span>
- <span data-ttu-id="90a3e-150">Überarbeiten Sie Ihre Einstellungen und Richtlinien für zusätzliche Apps, Geräte und Sicherheitsanforderungen.</span><span class="sxs-lookup"><span data-stu-id="90a3e-150">Revise your settings and policies for additional apps, devices, and security requirements.</span></span>