---
title: Bereitstellen von apps für Microsoft verwalteter Desktop-Geräte
description: Informationen zum Hinzufügen und Bereitstellen von apps für Microsoft verwalteter Desktop-Geräte.
keywords: Microsoft verwalteter Desktop, Microsoft 365, Dienst, Dokumentation, apps, Line-of-Business-apps, LOB-apps
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/17/2019
ms.openlocfilehash: 65d45be5ddb21d8f2cac876a1c8f93b2bbddf7b8
ms.sourcegitcommit: 0fc00286d7dc8cafddf9d17a98a375503b9551e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/18/2019
ms.locfileid: "29341606"
---
# <a name="deploy-apps-to-microsoft-managed-desktop-devices"></a><span data-ttu-id="a5d5d-104">Bereitstellen von apps in Microsoft verwalteter Desktop-Geräte</span><span class="sxs-lookup"><span data-stu-id="a5d5d-104">Deploy apps to Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="a5d5d-p101">Teil Onboarding auf Microsoft Managed Desktop umfasst hinzufügen und Bereitstellen von apps für Geräte des Benutzers. Nachdem Sie das Microsoft verwalteter Desktop-Portal verwenden, können Sie hinzufügen und Bereitstellen Ihrer apps.</span><span class="sxs-lookup"><span data-stu-id="a5d5d-p101">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user’s devices. Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="a5d5d-107">Der Gesamtprozess sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="a5d5d-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="a5d5d-108">[Hinzufügen von apps verwalteter Microsoft-Desktop-Portal](#1) – dies apps Line-of-Business (LOB) oder apps aus Microsoft Store für Unternehmen, die Sie synchronisiert haben mit Intune vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="a5d5d-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="a5d5d-109">[Erstellen von Azure Active Directory (AD) Gruppen für die Zuweisung von app](#2) - verwenden Sie diese Gruppen zum Verwalten von app-Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="a5d5d-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="a5d5d-110">Zuweisen von apps für Ihre Benutzer</span><span class="sxs-lookup"><span data-stu-id="a5d5d-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="a5d5d-111">Schritt 1: Hinzufügen von apps verwalteter Microsoft-Desktop-Portal</span><span class="sxs-lookup"><span data-stu-id="a5d5d-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="a5d5d-112">Sie können Microsoft verwalteter Desktop [Win32 Windows MSI-basierte apps](#lob-apps)oder [Microsoft Store für Business apps](#msfb-apps) hinzugefügt werden und klicken Sie dann auf Microsoft verwalteter Desktop Geräte bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a5d5d-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="a5d5d-113">Win32- oder Windows MSI-basierte apps an Microsoft verwalteten Desktops</span><span class="sxs-lookup"><span data-stu-id="a5d5d-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="a5d5d-p102">Sie können Ihre apps Line-of-Business (LOB) Microsoft verwalteter Desktop-Portal hinzufügen. Informationen zu Anforderungen für apps, die auf Microsoft verwalteter Desktop Geräten installiert finden Sie unter [Microsoft verwalteter Desktop-app-Anforderungen](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span><span class="sxs-lookup"><span data-stu-id="a5d5d-p102">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal. For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="a5d5d-116">In diesem Verfahren wählen Sie die Art der app aus, den, die Sie hinzufügen möchten, und klicken Sie dann konfigurieren und Hochladen der app-Quelle möchten.</span><span class="sxs-lookup"><span data-stu-id="a5d5d-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="a5d5d-117">**So fügen Sie Ihre LOB-app oder Windows-app verwalteter Microsoft-Desktop-Portal hinzu**</span><span class="sxs-lookup"><span data-stu-id="a5d5d-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="a5d5d-p103">Melden Sie sich bei Microsoft verwalteter Desktop-Portal oder Intune melden Sie sich, und suchen Sie dann nach Microsoft verwalteter Desktop. Anmelden bei Microsoft verwalteter Desktop Portal erfahren.</span><span class="sxs-lookup"><span data-stu-id="a5d5d-p103">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop. We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.  <span data-ttu-id="a5d5d-120">Melden Sie sich bei [verwalteten Desktops Verwaltungsportal von Microsoft](http://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="a5d5d-120">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span> 
2.  <span data-ttu-id="a5d5d-121">Wählen Sie unter **Inventar** **Apps**.</span><span class="sxs-lookup"><span data-stu-id="a5d5d-121">Under **Inventory**, select **Apps**.</span></span>
3.  <span data-ttu-id="a5d5d-122">Wählen Sie in der Arbeitslast Apps **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="a5d5d-122">In the Apps workload, select **Add**.</span></span>
4.  <span data-ttu-id="a5d5d-123">Wählen Sie in **app hinzufügen** **Branchen app** oder **Windows-Anwendung (Win32) - Vorschau anzuzeigen**.</span><span class="sxs-lookup"><span data-stu-id="a5d5d-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32) - preview**.</span></span>
    - <span data-ttu-id="a5d5d-124">Wenn Sie **LOB app**ausgewählt haben, finden Sie unter [Hinzufügen einer Windows LOB app zu Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) Anweisung zum Hinzufügen und Konfigurieren von Line-of-Business-apps.</span><span class="sxs-lookup"><span data-stu-id="a5d5d-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="a5d5d-125">Wenn Sie **Windows-Anwendung (Win32) - Vorschau anzeigen**ausgewählt haben, finden Sie unter [Win32-app-Verwaltung](https://docs.microsoft.com/intune/apps-win32-app-management) erhalten Sie Anleitungen hinzufügen und Konfigurieren von apps für Windows.</span><span class="sxs-lookup"><span data-stu-id="a5d5d-125">If you selected **Windows app (Win32) - preview**, see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="a5d5d-126">Microsoft-Speichers für die Business-apps</span><span class="sxs-lookup"><span data-stu-id="a5d5d-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="a5d5d-p104">Wenn Sie nicht mit Microsoft Store for Business angemeldet haben, können Sie sich anmelden, wenn Sie für apps kaufen. Nachdem Sie Ihre apps haben, können Sie diese mit Microsoft verwalteter Desktop synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="a5d5d-p104">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps. After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="a5d5d-129">**Zum Erwerben von apps aus dem Microsoft Store for Business**</span><span class="sxs-lookup"><span data-stu-id="a5d5d-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="a5d5d-130">Melden Sie sich an [Microsoft Store for Business](https://businessstore.microsoft.com) mit Ihrem Microsoft Store für Business Administratorkonto.</span><span class="sxs-lookup"><span data-stu-id="a5d5d-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="a5d5d-131">Wählen Sie **Meine Gruppe kaufen**.</span><span class="sxs-lookup"><span data-stu-id="a5d5d-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="a5d5d-132">Anhand der Suche, die die app zu suchen, und wählen Sie die app.</span><span class="sxs-lookup"><span data-stu-id="a5d5d-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="a5d5d-p105">Wählen Sie auf Produktdetails **rufen Sie die App**. Microsoft Store hinzugefügt **Produkte & Dienstleistungen** für Ihre Organisation die app.</span><span class="sxs-lookup"><span data-stu-id="a5d5d-p105">On the product details, select **Get the App**. Microsoft Store adds the app to **Products & services** for your organization.</span></span>

<span data-ttu-id="a5d5d-135">**So erzwingen Sie eine Synchronisierung zwischen Intune und Microsoft Store for Business**</span><span class="sxs-lookup"><span data-stu-id="a5d5d-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="a5d5d-136">Melden Sie sich [Azure-Portal](https://portal.azure.com/) als Intune Admin oder globaler Administrator für Ihre Mandanten</span><span class="sxs-lookup"><span data-stu-id="a5d5d-136">Sign in to [Azure Portal](https://portal.azure.com/) as Intune Admin or Global Admin for your tenant</span></span>
2. <span data-ttu-id="a5d5d-p106">Wählen Sie **alle Dienste > Intune**aus. Intune befindet sich in der Überwachung + Management Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="a5d5d-p106">Select **All services > Intune**. Intune is in the Monitoring + Management section.</span></span>
3. <span data-ttu-id="a5d5d-139">Klicken Sie im Bereich Intune wählen Sie **Client-Apps**, und wählen Sie dann **Microsoft Store for Business**aus.</span><span class="sxs-lookup"><span data-stu-id="a5d5d-139">In the Intune pane, select **Client Apps**, and then select **Microsoft Store for Business**.</span></span>
4. <span data-ttu-id="a5d5d-140">Wählen Sie Ihre Microsoft Store für Business-apps mit Intune synchronisieren **Aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="a5d5d-140">Select **Enable** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="a5d5d-141">Wenn Sie noch nicht geschehen ist, Sign up und Zuordnen Ihrer Microsoft Speichern Business-Kontos mit Intune</span><span class="sxs-lookup"><span data-stu-id="a5d5d-141">If you haven't already, sign up and associate your Microsoft Store for Business account with Intune</span></span>
    - <span data-ttu-id="a5d5d-142">Wählen Sie die Sprache, in der apps aus dem Microsoft Store for Business in Ihre Konsole Intune angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="a5d5d-142">Select the language in which apps from the Microsoft Store for Business will be displayed in your Intune console</span></span>
    - <span data-ttu-id="a5d5d-143">Wählen Sie **Synchronisierung** Ihrer Microsoft Store für Business-apps mit Intune synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="a5d5d-143">Select **Sync** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="a5d5d-144">Stellen Sie sicher, dass die Synchronisierung zwischen Microsoft Store for Business und Intune aktiv ist (Nächster Schritt).</span><span class="sxs-lookup"><span data-stu-id="a5d5d-144">Verify that the sync between Microsoft Store for Business and Intune is active (next step).</span></span> 

<span data-ttu-id="a5d5d-145">**Um sicherzustellen, dass eine Synchronisierung zwischen Intune und Microsoft Store for Business aktiv ist.**</span><span class="sxs-lookup"><span data-stu-id="a5d5d-145">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="a5d5d-146">Melden Sie sich an [Microsoft Store for Business](https://businessstore.microsoft.com) mit Ihrem Microsoft Store für Business Administratorkonto.</span><span class="sxs-lookup"><span data-stu-id="a5d5d-146">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="a5d5d-147">Wählen Sie **Verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="a5d5d-147">Select **Manage**.</span></span>
3. <span data-ttu-id="a5d5d-148">Wählen Sie **Einstellungen** , und wählen Sie dann **verteilen**.</span><span class="sxs-lookup"><span data-stu-id="a5d5d-148">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="a5d5d-149">Klicken Sie unter **Verwaltungstools**sicherstellen Sie, dass Intune aufgeführt wird und der Status **aktiv**ist.</span><span class="sxs-lookup"><span data-stu-id="a5d5d-149">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="a5d5d-150">Schritt 2: Erstellen von Azure AD-Gruppen</span><span class="sxs-lookup"><span data-stu-id="a5d5d-150">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="a5d5d-p107">Erstellen Sie drei Azure Active Directory-Gruppen für die jeweilige app. Die folgende Tabelle beschreibt die Gruppen, die Sie benötigen (verfügbar, die erforderlich sind, und deinstallieren).</span><span class="sxs-lookup"><span data-stu-id="a5d5d-p107">Create three Azure AD groups for each app. This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="a5d5d-153">Typ der App-Zuordnung</span><span class="sxs-lookup"><span data-stu-id="a5d5d-153">App assignment type</span></span> |   <span data-ttu-id="a5d5d-154">Gruppe verwenden</span><span class="sxs-lookup"><span data-stu-id="a5d5d-154">Group use</span></span>   | <span data-ttu-id="a5d5d-155">Azure AD-Beispielname</span><span class="sxs-lookup"><span data-stu-id="a5d5d-155">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="a5d5d-156">Verfügbar</span><span class="sxs-lookup"><span data-stu-id="a5d5d-156">Available</span></span> |  <span data-ttu-id="a5d5d-157">Die app aus Unternehmensportal app oder Website zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="a5d5d-157">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="a5d5d-158">MMD – *app-Name* – verfügbar</span><span class="sxs-lookup"><span data-stu-id="a5d5d-158">MMD – *app name* – Available</span></span>
<span data-ttu-id="a5d5d-159">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="a5d5d-159">Required</span></span> |  <span data-ttu-id="a5d5d-160">Die app ist auf Geräten in den ausgewählten Gruppen installiert.</span><span class="sxs-lookup"><span data-stu-id="a5d5d-160">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="a5d5d-161">MMD – *app-Name* – erforderlich</span><span class="sxs-lookup"><span data-stu-id="a5d5d-161">MMD – *app name* – Required</span></span>
<span data-ttu-id="a5d5d-162">„Deinstallieren“</span><span class="sxs-lookup"><span data-stu-id="a5d5d-162">Uninstall</span></span> |  <span data-ttu-id="a5d5d-163">TThe app wird von Geräten in den ausgewählten Gruppen deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="a5d5d-163">TThe app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="a5d5d-164">MMD – *app-Name* – deinstallieren</span><span class="sxs-lookup"><span data-stu-id="a5d5d-164">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="a5d5d-165">Diese Gruppen, damit der app verfügbar machen, die app installieren oder Entfernen der app auf ihrem Gerät Microsoft verwalteter Desktop fügen Sie Ihrer Benutzer hinzu.</span><span class="sxs-lookup"><span data-stu-id="a5d5d-165">Add your users to these groups to either make the app availabe, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="a5d5d-166">Schritt 3: Zuweisen von apps für Ihre Benutzer</span><span class="sxs-lookup"><span data-stu-id="a5d5d-166">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="a5d5d-167">**Ihre Benutzer die app zuweisen**</span><span class="sxs-lookup"><span data-stu-id="a5d5d-167">**To assign the app to your users**</span></span>

1. <span data-ttu-id="a5d5d-168">Melden Sie sich bei [verwalteten Desktops Verwaltungsportal von Microsoft](http://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="a5d5d-168">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="a5d5d-169">Wählen Sie im Bereich verwalteter Desktop **Apps**ein.</span><span class="sxs-lookup"><span data-stu-id="a5d5d-169">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="a5d5d-170">Wählen Sie in der Arbeitslast Apps die app, den, die Sie Benutzern zuweisen, und wählen Sie **Benutzer und Gruppen zuweisen**möchten.</span><span class="sxs-lookup"><span data-stu-id="a5d5d-170">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="a5d5d-171">Wählen Sie für die bestimmte app eine Zuordnung (verfügbar, erforderlich, deinstallieren), und weisen Sie die entsprechende Gruppe.</span><span class="sxs-lookup"><span data-stu-id="a5d5d-171">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="a5d5d-172">Klicken Sie im Bereich weisen Sie Apps wählen Sie **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="a5d5d-172">In the Assign Apps pane, select **OK**.</span></span>

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