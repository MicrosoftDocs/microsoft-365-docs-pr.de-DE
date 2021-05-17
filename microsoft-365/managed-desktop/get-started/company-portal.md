---
title: Installieren des Intune-Unternehmensportals auf Geräten
description: Informationen zum Installieren der Unternehmensportal-App auf Microsoft Managed Desktop-Geräten
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
# <a name="install-intune-company-portal-on-devices"></a><span data-ttu-id="14103-104">Installieren des Intune-Unternehmensportals auf Geräten</span><span class="sxs-lookup"><span data-stu-id="14103-104">Install Intune Company Portal on devices</span></span>

<span data-ttu-id="14103-105">Microsoft Managed Desktop erfordert, dass IT-Administratoren das Intune-Unternehmensportal für ihre Benutzer mit Microsoft Managed Desktop-Geräten installieren.</span><span class="sxs-lookup"><span data-stu-id="14103-105">Microsoft Managed Desktop requires that IT administrators install Intune Company Portal for their users with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="14103-106">Hier sind einige Vorteile für Ihre Organisation:</span><span class="sxs-lookup"><span data-stu-id="14103-106">Here are some benefits for your organization:</span></span>
- <span data-ttu-id="14103-107">Benutzer haben eine einzige Stelle, um verfügbare Anwendungen zu durchsuchen und zu installieren.</span><span class="sxs-lookup"><span data-stu-id="14103-107">Users have one place to browse and install available applications.</span></span> 
- <span data-ttu-id="14103-108">IT-Administratoren können Anwendungen nach Kategorien für ihre Benutzer organisieren.</span><span class="sxs-lookup"><span data-stu-id="14103-108">IT administrators can organize applications by categories for their users.</span></span>  
- <span data-ttu-id="14103-109">Für einige Anwendungen (z. B. Microsoft Project und Microsoft Visio) muss das Unternehmensportal mit Microsoft Managed Desktop bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="14103-109">Some applications (like Microsoft Project and Microsoft Visio) require Company Portal to deploy with Microsoft Managed Desktop.</span></span>
- <span data-ttu-id="14103-110">IT-Administratoren können das Unternehmensportal für ihre Organisation anpassen.</span><span class="sxs-lookup"><span data-stu-id="14103-110">IT administrators can customize Company Portal for their organization.</span></span> <span data-ttu-id="14103-111">Dies umfasst die Markendarstellung, das Hinzufügen lokaler Supportkontakte und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="14103-111">This includes brand imaging, adding in local support contacts, and more.</span></span> <span data-ttu-id="14103-112">Weitere Informationen finden Sie unter [Konfigurieren der Microsoft Intune-Unternehmensportal-App](/intune/company-portal-app).</span><span class="sxs-lookup"><span data-stu-id="14103-112">For more information, see [How to Configure the Microsoft Intune Company Portal app](/intune/company-portal-app).</span></span>   

<span data-ttu-id="14103-113">In diesem Thema wird der Prozess für die Bereitstellung des Intune-Unternehmensportals für Ihre Microsoft Managed Desktop-Benutzer dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="14103-113">This topic documents the process for deploying the Intune Company Portal to your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="14103-114">Der Gesamteindruck sieht wie dies aus:</span><span class="sxs-lookup"><span data-stu-id="14103-114">The overall process looks like this:</span></span>
1. <span data-ttu-id="14103-115">Erwerben des Unternehmensportals aus dem Microsoft Store für Unternehmen und Synchronisieren mit Intune</span><span class="sxs-lookup"><span data-stu-id="14103-115">Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
2. <span data-ttu-id="14103-116">Zuweisen des Unternehmensportals zu Ihren Benutzern</span><span class="sxs-lookup"><span data-stu-id="14103-116">Assign Company Portal to your users</span></span>
3. <span data-ttu-id="14103-117">Kommunizieren von Änderungen an Ihre Benutzer</span><span class="sxs-lookup"><span data-stu-id="14103-117">Communicate change to your users</span></span>

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a><span data-ttu-id="14103-118">Schritt 1 – Erwerben des Unternehmensportals aus dem Microsoft Store für Unternehmen und Synchronisieren mit Intune</span><span class="sxs-lookup"><span data-stu-id="14103-118">Step 1 - Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
<span data-ttu-id="14103-119">Informationen zum Kauf der Apps und zur Synchronisierung mit Intune finden Sie unter [Microsoft Store for Business apps](deploy-apps.md#msfb-apps) in Deploy apps to Microsoft Managed Desktop *devices*.</span><span class="sxs-lookup"><span data-stu-id="14103-119">For info on how to purchase the apps and sync with Intune, see [Microsoft Store for Business apps](deploy-apps.md#msfb-apps) in *Deploy apps to Microsoft Managed Desktop devices*.</span></span>

<span data-ttu-id="14103-120">In diesem Thema finden Sie Informationen zu:</span><span class="sxs-lookup"><span data-stu-id="14103-120">This topic provides info on how to:</span></span> 
- <span data-ttu-id="14103-121">Erwerben des Unternehmensportals aus dem Microsoft Store für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="14103-121">Purchase Company Portal from Microsoft Store for Business</span></span> 
- <span data-ttu-id="14103-122">Erzwingen der Synchronisierung zwischen Intune und Microsoft Store für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="14103-122">Force sync between Intune and Microsoft Store for Business</span></span>
- <span data-ttu-id="14103-123">Überprüfen der aktiven Synchronisierung zwischen Intune und Microsoft Store für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="14103-123">Verify active sync between Intune and Microsoft Store for Business</span></span> 

## <a name="step-2---assign-company-portal-to-your-users"></a><span data-ttu-id="14103-124">Schritt 2 – Zuweisen des Unternehmensportals zu Ihren Benutzern</span><span class="sxs-lookup"><span data-stu-id="14103-124">Step 2 - Assign Company Portal to your users</span></span>
<span data-ttu-id="14103-125">Nach der Registrierung bei Microsoft Managed Desktop stellen wir das Unternehmensportal automatisch für Ihren Mandanten zur Verfügung und installieren die App auf Microsoft Managed Desktop-Geräten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="14103-125">Following your enrollment in Microsoft Managed Desktop, we will automatically deploy Company Portal to your tenant and install the app on Microsoft Managed Desktop devices in your organization.</span></span>

## <a name="step-3---communicate-change-to-your-users"></a><span data-ttu-id="14103-126">Schritt 3 – Kommunizieren von Änderungen an Ihre Benutzer</span><span class="sxs-lookup"><span data-stu-id="14103-126">Step 3 - Communicate change to your users</span></span>
<span data-ttu-id="14103-127">Als IT-Administrator für Ihre Organisation ist es wichtig, Ihren Benutzern die Verwendung des Unternehmensportals in Ihrer Organisation zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="14103-127">As the IT administrator for your organization, it’s important to let your users know how to use Company Portal in your organization.</span></span> <span data-ttu-id="14103-128">Microsoft Managed Desktop empfiehlt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="14103-128">Microsoft Managed Desktop recommends:</span></span>
- <span data-ttu-id="14103-129">Schritte zum Installieren von Anwendungen aus dem Unternehmensportal.</span><span class="sxs-lookup"><span data-stu-id="14103-129">Steps on installing applications from the Company Portal.</span></span> <span data-ttu-id="14103-130">Weitere Informationen finden Sie unter [Installieren und Freigeben von Apps auf Ihrem Gerät.](/intune-user-help/install-apps-cpapp-windows)</span><span class="sxs-lookup"><span data-stu-id="14103-130">For more information, see [Install and share apps on your device](/intune-user-help/install-apps-cpapp-windows).</span></span>
- <span data-ttu-id="14103-131">Senden von Anforderungen an IT-Administratoren für Anwendungen, die derzeit nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="14103-131">How to send requests to IT administrators for applications that are not currently available.</span></span> <span data-ttu-id="14103-132">Weitere Informationen finden Sie unter [Request an app for work or school](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school).</span><span class="sxs-lookup"><span data-stu-id="14103-132">For more information, see [Request an app for work or school](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school).</span></span>  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="14103-133">Schritte zum Einstieg in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="14103-133">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="14103-134">Hinzufügen und Überprüfen von Administrator-Kontakten im-Administratorportal</span><span class="sxs-lookup"><span data-stu-id="14103-134">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="14103-135">Bedingten Zugriff anpassen</span><span class="sxs-lookup"><span data-stu-id="14103-135">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="14103-136">Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="14103-136">Assign licenses</span></span>](assign-licenses.md)
4. <span data-ttu-id="14103-137">Bereitstellen des Intune-Unternehmensportals (dieses Thema)</span><span class="sxs-lookup"><span data-stu-id="14103-137">Deploy Intune Company Portal (this topic)</span></span>
5. [<span data-ttu-id="14103-138">Aktivieren von Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="14103-138">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="14103-139">Einrichten von Geräten</span><span class="sxs-lookup"><span data-stu-id="14103-139">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="14103-140">Vorbereiten Ihrer Benutzer für die Verwendung von Geräten</span><span class="sxs-lookup"><span data-stu-id="14103-140">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="14103-141">Bereitstellen von Apps</span><span class="sxs-lookup"><span data-stu-id="14103-141">Deploy apps</span></span>](deploy-apps.md)
