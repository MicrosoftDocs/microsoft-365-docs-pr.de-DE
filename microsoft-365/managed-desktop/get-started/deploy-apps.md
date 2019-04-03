---
title: Bereitstellen von Apps für Microsoft Managed Desktop-Geräte
description: Informationen zum Hinzufügen und Bereitstellen von Apps für auf Microsoft verwaltete Desktop Geräte.
keywords: Microsoft Managed Desktop, Microsoft 365, Service, Dokumentation, apps, Branchen-apps, LOB-apps
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5ccb240460958d5978f4fd19e08652123790784e
ms.sourcegitcommit: 2211f57c268754d242d6331c188143f818f5a9f4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "31039594"
---
# <a name="deploy-apps-to-microsoft-managed-desktop-devices"></a><span data-ttu-id="e24e9-104">Bereitstellen von apps auf Microsoft Managed Desktop-Geräten</span><span class="sxs-lookup"><span data-stu-id="e24e9-104">Deploy apps to Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="e24e9-105">Ein Teil des onboardings für Microsoft Managed Desktop umfasst das Hinzufügen und Bereitstellen von apps auf den Geräten Ihrer Benutzer.</span><span class="sxs-lookup"><span data-stu-id="e24e9-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user’s devices.</span></span> <span data-ttu-id="e24e9-106">Nachdem Sie das Microsoft Managed Desktop-Portal verwendet haben, können Sie Ihre apps hinzufügen und bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e24e9-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="e24e9-107">Der Gesamtprozess sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="e24e9-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="e24e9-108">[Hinzufügen von apps zu einem Microsoft Managed Desktop-Portal](#1) – Dies können vorhandene LOB-Apps oder Apps aus Microsoft Store for Business sein, die Sie mit InTune synchronisiert haben.</span><span class="sxs-lookup"><span data-stu-id="e24e9-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="e24e9-109">[Erstellen von Azure Active Directory (AD)-Gruppen für die APP-Zuweisung](#2) : Sie verwenden diese Gruppen zum Verwalten der APP-Zuweisung.</span><span class="sxs-lookup"><span data-stu-id="e24e9-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="e24e9-110">Zuweisen von apps zu Ihren Benutzern</span><span class="sxs-lookup"><span data-stu-id="e24e9-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="e24e9-111">Schritt 1: Hinzufügen von apps zu Microsoft Managed Desktop Portal</span><span class="sxs-lookup"><span data-stu-id="e24e9-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="e24e9-112">Sie können [Win32-oder Windows-MSI-basierte apps](#lob-apps)oder [Microsoft Store for Business-Apps](#msfb-apps) zu Microsoft Managed Desktop hinzufügen und diese dann auf Microsoft Managed Desktop-Geräten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e24e9-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="e24e9-113">Win32-oder Windows-MSI-basierte Apps für Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="e24e9-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="e24e9-114">Sie können Ihre Branchen-apps zu Microsoft Managed Desktop Portal hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e24e9-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="e24e9-115">Informationen zu den Anforderungen für apps, die auf verwalteten Desktopgeräten von Microsoft installiert sind, finden Sie unter [Microsoft Managed Desktop App Requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span><span class="sxs-lookup"><span data-stu-id="e24e9-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="e24e9-116">In diesem Verfahren wählen Sie die Art der APP aus, die Sie hinzufügen möchten, und konfigurieren und Hochladen der APP-Quelle.</span><span class="sxs-lookup"><span data-stu-id="e24e9-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

**<span data-ttu-id="e24e9-117">So fügen Sie Ihre Branchen-APP oder Windows-APP zu Microsoft Managed Desktop Portal hinzu</span><span class="sxs-lookup"><span data-stu-id="e24e9-117">To add your LOB app or Windows app to Microsoft Managed Desktop portal</span></span>**

<span data-ttu-id="e24e9-118">Sie können sich bei Microsoft Managed Desktop Portal anmelden oder sich bei InTune anmelden und dann nach Microsoft Managed Desktop suchen.</span><span class="sxs-lookup"><span data-stu-id="e24e9-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="e24e9-119">Wir zeigen die Anmeldung beim Microsoft Managed Desktop-Portal an.</span><span class="sxs-lookup"><span data-stu-id="e24e9-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.  <span data-ttu-id="e24e9-120">Melden Sie sich beim [Microsoft Managed Desktop Admin Portal](http://aka.ms/mmdportal)an.</span><span class="sxs-lookup"><span data-stu-id="e24e9-120">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span> 
2.  <span data-ttu-id="e24e9-121">Wählen Sie unter **Inventar**die Option **apps**aus.</span><span class="sxs-lookup"><span data-stu-id="e24e9-121">Under **Inventory**, select **Apps**.</span></span>
3.  <span data-ttu-id="e24e9-122">Wählen Sie in der Arbeitsauslastung Apps die Option **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="e24e9-122">In the Apps workload, select **Add**.</span></span>
4.  <span data-ttu-id="e24e9-123">Wählen Sie unter **app hinzufügen**die Option **Branchen-App** oder **Windows-app (Win32)-Preview**aus.</span><span class="sxs-lookup"><span data-stu-id="e24e9-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32) - preview**.</span></span>
    - <span data-ttu-id="e24e9-124">Wenn Sie die Branchen **-App**ausgewählt haben, finden Sie unter [Hinzufügen einer Windows-Branchen-APP zu Microsoft InTune](https://docs.microsoft.com/intune/lob-apps-windows) Informationen zum Hinzufügen und Konfigurieren von Branchen-apps.</span><span class="sxs-lookup"><span data-stu-id="e24e9-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="e24e9-125">Wenn Sie **Windows-app (Win32)-Preview**ausgewählt haben, finden Sie unter [Win32-App-Verwaltung](https://docs.microsoft.com/intune/apps-win32-app-management) Anweisungen zum hinzuFügen und Konfigurieren von Windows-apps.</span><span class="sxs-lookup"><span data-stu-id="e24e9-125">If you selected **Windows app (Win32) - preview**, see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="e24e9-126">Microsoft Store for Business-Apps</span><span class="sxs-lookup"><span data-stu-id="e24e9-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="e24e9-127">Wenn Sie sich noch nicht bei Microsoft Store for Business registriert haben, können Sie sich registrieren, wenn Sie für apps einkaufen.</span><span class="sxs-lookup"><span data-stu-id="e24e9-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="e24e9-128">Nachdem Sie Ihre apps installiert haben, können Sie Sie mit Microsoft Managed Desktop synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="e24e9-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

**<span data-ttu-id="e24e9-129">So kaufen Sie apps im Microsoft Store for Business</span><span class="sxs-lookup"><span data-stu-id="e24e9-129">To buy apps from the Microsoft Store for Business</span></span>**

1. <span data-ttu-id="e24e9-130">Melden Sie sich mit Ihrem Microsoft Store for Business-Administratorkonto bei [Microsoft Store for Business](https://businessstore.microsoft.com) an.</span><span class="sxs-lookup"><span data-stu-id="e24e9-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="e24e9-131">Wählen Sie **Shop für meine Gruppe**aus.</span><span class="sxs-lookup"><span data-stu-id="e24e9-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="e24e9-132">Verwenden Sie die Suche, um die gewünschte APP zu finden, und wählen Sie die APP aus.</span><span class="sxs-lookup"><span data-stu-id="e24e9-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="e24e9-133">Wählen Sie in den Produkt Details **die Option App abrufen**aus.</span><span class="sxs-lookup"><span data-stu-id="e24e9-133">On the product details, select **Get the App**.</span></span> <span data-ttu-id="e24e9-134">Microsoft Store fügt der APP **Produkte & Dienste** für Ihre Organisation hinzu.</span><span class="sxs-lookup"><span data-stu-id="e24e9-134">Microsoft Store adds the app to **Products & services** for your organization.</span></span>

**<span data-ttu-id="e24e9-135">So erzwingen Sie eine Synchronisierung zwischen InTune und Microsoft Store for Business</span><span class="sxs-lookup"><span data-stu-id="e24e9-135">To force a sync between Intune and Microsoft Store for Business</span></span>**
1. <span data-ttu-id="e24e9-136">Melden Sie sich beim [Azure-Portal](https://portal.azure.com/) als InTune-Administrator oder globaler Administrator für Ihren Mandanten an.</span><span class="sxs-lookup"><span data-stu-id="e24e9-136">Sign in to [Azure Portal](https://portal.azure.com/) as Intune Admin or Global Admin for your tenant</span></span>
2. <span data-ttu-id="e24e9-137">Wählen Sie **alle Dienste _GT_ InTune**aus.</span><span class="sxs-lookup"><span data-stu-id="e24e9-137">Select **All services > Intune**.</span></span> <span data-ttu-id="e24e9-138">InTune befindet sich im Abschnitt Monitoring + Management.</span><span class="sxs-lookup"><span data-stu-id="e24e9-138">Intune is in the Monitoring + Management section.</span></span>
3. <span data-ttu-id="e24e9-139">Wählen Sie im Bereich InTune die Option **Client-apps**aus, und wählen Sie dann **Microsoft Store for Business**aus.</span><span class="sxs-lookup"><span data-stu-id="e24e9-139">In the Intune pane, select **Client Apps**, and then select **Microsoft Store for Business**.</span></span>
4. <span data-ttu-id="e24e9-140">Wählen Sie **aktivieren** aus, um Ihren Microsoft Store for Business-Apps mit InTune zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="e24e9-140">Select **Enable** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="e24e9-141">Falls noch nicht geschehen, registrieren Sie sich und ordnen Sie Ihr Microsoft Store for Business-Konto mit InTune zu.</span><span class="sxs-lookup"><span data-stu-id="e24e9-141">If you haven't already, sign up and associate your Microsoft Store for Business account with Intune</span></span>
    - <span data-ttu-id="e24e9-142">Wählen Sie die Sprache aus, in der Apps aus dem Microsoft Store for Business in ihrer InTune-Konsole angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e24e9-142">Select the language in which apps from the Microsoft Store for Business will be displayed in your Intune console</span></span>
    - <span data-ttu-id="e24e9-143">Wählen Sie **Synchronisieren** aus, um Ihren Microsoft Store for Business-Apps mit InTune zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="e24e9-143">Select **Sync** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="e24e9-144">Stellen Sie sicher, dass die Synchronisierung zwischen Microsoft Store for Business und InTune aktiv ist (nächster Schritt).</span><span class="sxs-lookup"><span data-stu-id="e24e9-144">Verify that the sync between Microsoft Store for Business and Intune is active (next step).</span></span> 

**<span data-ttu-id="e24e9-145">So überprüfen Sie, ob eine Synchronisierung zwischen InTune und Microsoft Store for Business aktiv ist</span><span class="sxs-lookup"><span data-stu-id="e24e9-145">To verify that a sync between Intune and Microsoft Store for Business is active</span></span>**
1. <span data-ttu-id="e24e9-146">Melden Sie sich mit Ihrem Microsoft Store for Business-Administratorkonto bei [Microsoft Store for Business](https://businessstore.microsoft.com) an.</span><span class="sxs-lookup"><span data-stu-id="e24e9-146">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="e24e9-147">Wählen Sie **Verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="e24e9-147">Select **Manage**.</span></span>
3. <span data-ttu-id="e24e9-148">Wählen Sie **Einstellungen** und dann **verteilen**aus.</span><span class="sxs-lookup"><span data-stu-id="e24e9-148">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="e24e9-149">Überprüfen Sie unter **Verwaltungstools**, dass InTune aufgeführt ist und dass der Status **aktiv**ist.</span><span class="sxs-lookup"><span data-stu-id="e24e9-149">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="e24e9-150">Schritt 2: Erstellen von Azure AD-Gruppen</span><span class="sxs-lookup"><span data-stu-id="e24e9-150">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="e24e9-151">Erstellen Sie für jede APP drei Azure AD-Gruppen.</span><span class="sxs-lookup"><span data-stu-id="e24e9-151">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="e24e9-152">In dieser Tabelle werden die benötigten Gruppen (verfügbar, erforderlich und deinstallieren) erläutert.</span><span class="sxs-lookup"><span data-stu-id="e24e9-152">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="e24e9-153">App-Zuordnungstyp</span><span class="sxs-lookup"><span data-stu-id="e24e9-153">App assignment type</span></span> |   <span data-ttu-id="e24e9-154">Gruppenverwendung</span><span class="sxs-lookup"><span data-stu-id="e24e9-154">Group use</span></span>   | <span data-ttu-id="e24e9-155">Beispiel Name für Azure AD</span><span class="sxs-lookup"><span data-stu-id="e24e9-155">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="e24e9-156">Available</span><span class="sxs-lookup"><span data-stu-id="e24e9-156">Available</span></span> |  <span data-ttu-id="e24e9-157">Die APP wird über die Unternehmens Portal-APP oder-Website zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="e24e9-157">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="e24e9-158">MMD – *App-Name* – verfügbar</span><span class="sxs-lookup"><span data-stu-id="e24e9-158">MMD – *app name* – Available</span></span>
<span data-ttu-id="e24e9-159">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="e24e9-159">Required</span></span> |  <span data-ttu-id="e24e9-160">Die APP wird auf Geräten in den ausgewählten Gruppen installiert.</span><span class="sxs-lookup"><span data-stu-id="e24e9-160">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="e24e9-161">MMD – *App-Name* – erforderlich</span><span class="sxs-lookup"><span data-stu-id="e24e9-161">MMD – *app name* – Required</span></span>
<span data-ttu-id="e24e9-162">Uninstall</span><span class="sxs-lookup"><span data-stu-id="e24e9-162">Uninstall</span></span> |  <span data-ttu-id="e24e9-163">Die APP wird von Geräten in den ausgewählten Gruppen deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="e24e9-163">TThe app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="e24e9-164">MMD – *App-Name* – deinstallieren</span><span class="sxs-lookup"><span data-stu-id="e24e9-164">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="e24e9-165">Fügen Sie Ihre Benutzer zu diesen Gruppen hinzu, um die APP entweder verfügbar zu machen, die APP zu installieren oder die APP von Ihrem von Microsoft verwalteten Desktop Gerät zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="e24e9-165">Add your users to these groups to either make the app availabe, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="e24e9-166">Schritt 3: Zuweisen von apps zu Ihren Benutzern</span><span class="sxs-lookup"><span data-stu-id="e24e9-166">Step 3: Assign apps to your users</span></span>

**<span data-ttu-id="e24e9-167">So weisen Sie die APP Ihren Benutzern zu</span><span class="sxs-lookup"><span data-stu-id="e24e9-167">To assign the app to your users</span></span>**

1. <span data-ttu-id="e24e9-168">Melden Sie sich beim [Microsoft Managed Desktop Admin Portal](http://aka.ms/mmdportal)an.</span><span class="sxs-lookup"><span data-stu-id="e24e9-168">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="e24e9-169">Wählen Sie im Bereich verwalteter Desktop die Option **apps**aus.</span><span class="sxs-lookup"><span data-stu-id="e24e9-169">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="e24e9-170">Wählen Sie in der apps-Arbeitsauslastung die APP aus, der Sie Benutzer zuweisen möchten, und wählen Sie **Benutzergruppen zuweisen**aus.</span><span class="sxs-lookup"><span data-stu-id="e24e9-170">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="e24e9-171">Wählen Sie für die jeweilige APP einen Zuordnungstyp aus (verfügbar, erforderlich, deinstallieren), und weisen Sie die entsprechende Gruppe zu.</span><span class="sxs-lookup"><span data-stu-id="e24e9-171">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="e24e9-172">Wählen Sie im Bereich apps zuweisen die Option **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="e24e9-172">In the Assign Apps pane, select **OK**.</span></span>

<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

Applications: supported/onboard/deployment
 
Microsoft and Microsoft Managed Desktop customers have equally critical, yet different responsibilities around applications used with Microsoft Managed Desktop.

## Microsoft responsibilities
**Office 365 apps**
Microsoft will provide full service for the deployment, update, and support of specific Office 365 apps. All users will receive the base set of Office 365 click to run, 64 bit version of applications included in the device’s image so that a user can quickly become productive. The Project and Visio applications in of the Office 365 suite are licensed separately.  Microsoft Managed Desktop will provide deployment groups allowing the IT Administrator to manage licenses and deploy these applications appropriately for their organization. Microsoft will support end users of these applications through the Microsoft Managed Desktop Support channels.

**Line-of-business apps**
Microsoft provides tooling for IT Administrators to manage and deploy their line-of-business (LOB) applications to end users as a part of the Intune product. Microsoft will support application deployment issues as detailed in [Line-of-business applications](#line-of-business-applications) 

**Deploy with Intune**
Intune will be linked to the **Microsoft Store for Business** during Microsoft Managed Desktop onboarding allowing procured apps to be deployed through Intune. Microsoft will also deploy the web-based version of the Company Portal to end users so that IT Administrators can provide a self-service experience for end users.

**App management**
Microsoft may identify restricted applications which are not suitable for the modern workplace because of their system impact. When such an application is identified Microsoft will notify the customer and that application will need to be removed from the tenant. 

For more information on restricted app behaviors and app requirements, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md)

## Customer responsibilities
The Office 365 Suite is core to Microsoft’s productivity offerings and is included in the Microsoft 365 License for all Microsoft Managed Desktop users. While Microsoft deploys, updates, and supports Office Applications to Microsoft Managed Desktop Devices there are still some areas for which the customer is responsible.
- **Assign licenses** - Customers are responsible for assigning the appropriate licenses to end users for Office 365. 
- **Add users to security groups** - For customers with users who need Project or Visio, the IT administrator must add those users to the appropriate deployment groups. IT administrators are also responsible for managing end of life for those users. 
- **Deploy Office 365 Add Ons** - Customers are responsible for deploying any plugins to the Office 365 suite which are deemed necessary. 

Since line-of-business (LOB) apps are unique for each customer, customers are responsible for managing all applications within their organization not deployed by Microsoft. This includes:
- Deciding which apps are needed and who needs them
- Assigning apps to those users
- Create and maintain Azure Active Directory (AD) groups for managing app assignments 

The customer must upload LOB apps to Intune. They are then responsible for deploying, updating, and decommissioning those applications over their respective lifecycles, as well as managing support for these apps for their users.

## Office applications
As part of the Microsoft 365 E5 license, Office 365 Standard Suite (64 Bit) is deployed by Microsoft. 

For details, see [Microsoft Managed Desktop technologies](../intro/technologies.md) <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.

## Line-of-business applications
This table summarizes responsibilities across the different phases for line-of-business (LOB) applications. 

Application work items |    Customer    | Microsoft
--- | --- | ---
**Onboarding apps** |  |
Identify applications needed for targeted user groups   | ![yes](images/checkmark.png)  |
Create and manage Azure AD groups for app deployment | ![yes](images/checkmark.png) |   
**App Packaging** |  |
Package apps to meet Intune deployment standards |  ![yes](images/checkmark.png) |  
Upload apps to Intune | ![yes](images/checkmark.png)     |
Test apps in Microsoft Managed Desktop environment |    ![yes](images/checkmark.png) |  
Test apps with end users    | ![yes](images/checkmark.png) |    
**Deployment** | |
Manage and assign users to applications  | ![yes](images/checkmark.png)  |
Intune deployment tools delivers application to remote clients| |   ![yes](images/checkmark.png)
Identify and deploy application updates through Intune | ![yes](images/checkmark.png)    |
Unistall and remove applications when they have been retired    | ![yes](images/checkmark.png) |    
**Management** | |
Procure and assign licenses |   ![yes](images/checkmark.png)     |
Provide end-user support for line-of-business apps  | ![yes](images/checkmark.png) |
Manage app settings remotely    | ![yes](images/checkmark.png) |

For information on LOB application requirements, see [Microsoft Managed Desktop application requirements](../service-description/mmd-app-requirements.md)


## Intune application deployment
Application management can be handled through the Microsoft Managed Desktop Admin portal, or through the Intune portal. Intune’s app management portal shows applications deployed for Windows, Android, and iOS. Microsoft Managed Desktop Admin portal limits the view to Windows 10 applications. Both are available through the Azure Portal. 
* [Intune app management basics](https://docs.microsoft.com/intune/app-management)
* [Add apps to Intune](https://docs.microsoft.com/intune/app-management)
   * [Add a line-of-business App](https://docs.microsoft.com/intune/lob-apps-windows)
   * [Add Win32 apps to Intune](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [Add web applications](https://docs.microsoft.com/intune/web-app)
* [Deploy apps](https://docs.microsoft.com/intune/apps-deploy)
   * [Deploy apps to Windows 10](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* Company Portal
   * [Deploy the Company Portal](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [Configure the Company Portal app](https://docs.microsoft.com/intune/company-portal-app)-->