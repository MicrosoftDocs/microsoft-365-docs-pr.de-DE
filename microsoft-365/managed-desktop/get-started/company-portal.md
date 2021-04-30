---
title: Installieren Intune-Unternehmensportal auf Geräten
description: Informationen zum Installieren der Unternehmensportal-App auf Microsoft Managed Desktop Geräten
keywords: Microsoft Managed Desktop, Microsoft 365, Unternehmensportal
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f9f36d6ca14be610ce9374380349264439282a6a
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086685"
---
# <a name="install-intune-company-portal-on-devices"></a><span data-ttu-id="41123-104">Installieren Intune-Unternehmensportal auf Geräten</span><span class="sxs-lookup"><span data-stu-id="41123-104">Install Intune Company Portal on devices</span></span>

<span data-ttu-id="41123-105">Microsoft Managed Desktop erfordert, dass IT-Administratoren Intune-Unternehmensportal Benutzer mit Microsoft Managed Desktop installieren.</span><span class="sxs-lookup"><span data-stu-id="41123-105">Microsoft Managed Desktop requires that IT administrators install Intune Company Portal for their users with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="41123-106">Hier sind einige Vorteile für Ihre Organisation:</span><span class="sxs-lookup"><span data-stu-id="41123-106">Here are some benefits for your organization:</span></span>
- <span data-ttu-id="41123-107">Benutzer haben eine einzige Stelle, um verfügbare Anwendungen zu durchsuchen und zu installieren.</span><span class="sxs-lookup"><span data-stu-id="41123-107">Users have one place to browse and install available applications.</span></span> 
- <span data-ttu-id="41123-108">IT-Administratoren können Anwendungen nach Kategorien für ihre Benutzer organisieren.</span><span class="sxs-lookup"><span data-stu-id="41123-108">IT administrators can organize applications by categories for their users.</span></span>  
- <span data-ttu-id="41123-109">Einige Anwendungen (z. B. Microsoft Project und Microsoft Visio) erfordern Unternehmensportal bereitstellung mit Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="41123-109">Some applications (like Microsoft Project and Microsoft Visio) require Company Portal to deploy with Microsoft Managed Desktop.</span></span>
- <span data-ttu-id="41123-110">IT-Administratoren können Unternehmensportal für ihre Organisation anpassen.</span><span class="sxs-lookup"><span data-stu-id="41123-110">IT administrators can customize Company Portal for their organization.</span></span> <span data-ttu-id="41123-111">Dies umfasst die Markendarstellung, das Hinzufügen lokaler Supportkontakte und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="41123-111">This includes brand imaging, adding in local support contacts, and more.</span></span> <span data-ttu-id="41123-112">Weitere Informationen finden Sie unter [Konfigurieren der Microsoft Intune Unternehmensportal App.](/intune/company-portal-app)</span><span class="sxs-lookup"><span data-stu-id="41123-112">For more information, see [How to Configure the Microsoft Intune Company Portal app](/intune/company-portal-app).</span></span>   

<span data-ttu-id="41123-113">In diesem Thema wird der Prozess für die Bereitstellung Intune-Unternehmensportal Benutzer Microsoft Managed Desktop dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="41123-113">This topic documents the process for deploying the Intune Company Portal to your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="41123-114">Der Gesamteindruck sieht wie dies aus:</span><span class="sxs-lookup"><span data-stu-id="41123-114">The overall process looks like this:</span></span>
1. <span data-ttu-id="41123-115">Erwerben Unternehmensportal von Microsoft Store für Unternehmen und Synchronisierung mit Intune</span><span class="sxs-lookup"><span data-stu-id="41123-115">Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
2. <span data-ttu-id="41123-116">Zuweisen Unternehmensportal Benutzern</span><span class="sxs-lookup"><span data-stu-id="41123-116">Assign Company Portal to your users</span></span>
3. <span data-ttu-id="41123-117">Kommunizieren von Änderungen an Ihre Benutzer</span><span class="sxs-lookup"><span data-stu-id="41123-117">Communicate change to your users</span></span>

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a><span data-ttu-id="41123-118">Schritt 1 – Erwerben Unternehmensportal von Microsoft Store für Unternehmen und Synchronisierung mit Intune</span><span class="sxs-lookup"><span data-stu-id="41123-118">Step 1 - Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
<span data-ttu-id="41123-119">Informationen zum Kauf der Apps und zur Synchronisierung mit Intune finden Sie [unter Microsoft Store für Unternehmen apps](deploy-apps.md#msfb-apps) in Deploy apps to Microsoft Managed Desktop *devices*.</span><span class="sxs-lookup"><span data-stu-id="41123-119">For info on how to purchase the apps and sync with Intune, see [Microsoft Store for Business apps](deploy-apps.md#msfb-apps) in *Deploy apps to Microsoft Managed Desktop devices*.</span></span>

<span data-ttu-id="41123-120">In diesem Thema finden Sie Informationen zu:</span><span class="sxs-lookup"><span data-stu-id="41123-120">This topic provides info on how to:</span></span> 
- <span data-ttu-id="41123-121">Erwerben Unternehmensportal von Microsoft Store für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="41123-121">Purchase Company Portal from Microsoft Store for Business</span></span> 
- <span data-ttu-id="41123-122">Erzwingen der Synchronisierung zwischen Intune und Microsoft Store für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="41123-122">Force sync between Intune and Microsoft Store for Business</span></span>
- <span data-ttu-id="41123-123">Überprüfen der aktiven Synchronisierung zwischen Intune und Microsoft Store für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="41123-123">Verify active sync between Intune and Microsoft Store for Business</span></span> 

## <a name="step-2---assign-company-portal-to-your-users"></a><span data-ttu-id="41123-124">Schritt 2 – Zuweisen Unternehmensportal Benutzern</span><span class="sxs-lookup"><span data-stu-id="41123-124">Step 2 - Assign Company Portal to your users</span></span>
<span data-ttu-id="41123-125">Nach Der Registrierung in Microsoft Managed Desktop stellen wir automatisch Unternehmensportal Mandanten zur Verfügung und installieren die App auf Microsoft Managed Desktop In Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="41123-125">Following your enrollment in Microsoft Managed Desktop, we will automatically deploy Company Portal to your tenant and install the app on Microsoft Managed Desktop devices in your organization.</span></span>

## <a name="step-3---communicate-change-to-your-users"></a><span data-ttu-id="41123-126">Schritt 3 – Kommunizieren von Änderungen an Ihre Benutzer</span><span class="sxs-lookup"><span data-stu-id="41123-126">Step 3 - Communicate change to your users</span></span>
<span data-ttu-id="41123-127">Als IT-Administrator für Ihre Organisation ist es wichtig, Ihren Benutzern zu zeigen, wie sie Unternehmensportal in Ihrer Organisation verwenden.</span><span class="sxs-lookup"><span data-stu-id="41123-127">As the IT administrator for your organization, it’s important to let your users know how to use Company Portal in your organization.</span></span> <span data-ttu-id="41123-128">Microsoft Managed Desktop empfiehlt:</span><span class="sxs-lookup"><span data-stu-id="41123-128">Microsoft Managed Desktop recommends:</span></span>
- <span data-ttu-id="41123-129">Schritte zum Installieren von Anwendungen aus Unternehmensportal.</span><span class="sxs-lookup"><span data-stu-id="41123-129">Steps on installing applications from the Company Portal.</span></span> <span data-ttu-id="41123-130">Weitere Informationen finden Sie unter [Installieren und Freigeben von Apps auf Ihrem Gerät.](/intune-user-help/install-apps-cpapp-windows)</span><span class="sxs-lookup"><span data-stu-id="41123-130">For more information, see [Install and share apps on your device](/intune-user-help/install-apps-cpapp-windows).</span></span>
- <span data-ttu-id="41123-131">Senden von Anforderungen an IT-Administratoren für Anwendungen, die derzeit nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="41123-131">How to send requests to IT administrators for applications that are not currently available.</span></span> <span data-ttu-id="41123-132">Weitere Informationen finden Sie unter [Request an app for work or school](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school).</span><span class="sxs-lookup"><span data-stu-id="41123-132">For more information, see [Request an app for work or school](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school).</span></span>  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="41123-133">Schritte zum Einstieg in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="41123-133">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="41123-134">Hinzufügen und Überprüfen von Administrator-Kontakten im-Administratorportal</span><span class="sxs-lookup"><span data-stu-id="41123-134">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="41123-135">Bedingten Zugriff anpassen</span><span class="sxs-lookup"><span data-stu-id="41123-135">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="41123-136">Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="41123-136">Assign licenses</span></span>](assign-licenses.md)
4. <span data-ttu-id="41123-137">Bereitstellen Intune-Unternehmensportal (dieses Thema)</span><span class="sxs-lookup"><span data-stu-id="41123-137">Deploy Intune Company Portal (this topic)</span></span>
5. [<span data-ttu-id="41123-138">Aktivieren von Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="41123-138">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="41123-139">Einrichten von Geräten</span><span class="sxs-lookup"><span data-stu-id="41123-139">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="41123-140">Vorbereiten Ihrer Benutzer für die Verwendung von Geräten</span><span class="sxs-lookup"><span data-stu-id="41123-140">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="41123-141">Bereitstellen von Apps</span><span class="sxs-lookup"><span data-stu-id="41123-141">Deploy apps</span></span>](deploy-apps.md)
