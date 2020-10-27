---
title: Stellen Sie Anwendungen auf Geräten bereit
description: Informationen zum Hinzufügen und Bereitstellen von apps auf Microsoft Managed Desktop-Geräten.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation, apps, Branchenanwendungen, Lob-apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2eb8b984550f301af9d99e738f6db4623aa2cc86
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769106"
---
# <a name="deploy-apps-to-devices"></a><span data-ttu-id="eae79-104">Stellen Sie Anwendungen auf Geräten bereit</span><span class="sxs-lookup"><span data-stu-id="eae79-104">Deploy apps to devices</span></span>
<span data-ttu-id="eae79-105">Ein Teil des onboardings für Microsoft Managed Desktop umfasst das Hinzufügen und Bereitstellen von apps auf den Geräten Ihrer Benutzer.</span><span class="sxs-lookup"><span data-stu-id="eae79-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user's devices.</span></span> <span data-ttu-id="eae79-106">Nachdem Sie das Microsoft Managed Desktop Portal verwendet haben, können Sie Ihre apps hinzufügen und bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="eae79-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="eae79-107">Der Gesamtprozess sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="eae79-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="eae79-108">[Hinzufügen von apps zu Microsoft Managed Desktop Portal](#1) -Dies kann vorhandene Branchen-Apps oder Apps aus dem Microsoft Store for Business sein, die Sie mit InTune synchronisiert haben.</span><span class="sxs-lookup"><span data-stu-id="eae79-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="eae79-109">[Erstellen von Azure Active Directory (AD)-Gruppen für die APP-Zuweisung](#2) -Sie verwenden diese Gruppen zum Verwalten der APP-Zuweisung.</span><span class="sxs-lookup"><span data-stu-id="eae79-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="eae79-110">Zuweisen von apps zu Benutzern</span><span class="sxs-lookup"><span data-stu-id="eae79-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="eae79-111">Schritt 1: Hinzufügen von apps zu Microsoft Managed Desktop Portal</span><span class="sxs-lookup"><span data-stu-id="eae79-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="eae79-112">Sie können [Win32-oder Windows MSI-basierte apps](#lob-apps)oder [Microsoft Store for Business-Apps](#msfb-apps) zu Microsoft Managed Desktop hinzufügen und diese dann auf Microsoft Managed Desktop-Geräten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="eae79-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="eae79-113">Win32-oder Windows MSI-basierte apps auf Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="eae79-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="eae79-114">Sie können Ihre Branchen-apps zu Microsoft Managed Desktop Portal hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="eae79-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="eae79-115">Informationen zu den Anforderungen für apps, die auf Microsoft Managed Desktop-Geräten installiert sind, finden Sie unter [Microsoft Managed Desktop App Requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span><span class="sxs-lookup"><span data-stu-id="eae79-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="eae79-116">In diesem Verfahren wählen Sie aus, welche App-Art Sie hinzufügen möchten, und konfigurieren und laden dann die APP-Quelle.</span><span class="sxs-lookup"><span data-stu-id="eae79-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="eae79-117">**So fügen Sie Ihre Branchen-APP oder Windows-APP zu einem Microsoft Managed Desktop-Portal hinzu**</span><span class="sxs-lookup"><span data-stu-id="eae79-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="eae79-118">Sie können sich bei Microsoft Managed Desktop Portal anmelden oder sich bei InTune anmelden und dann nach Microsoft Managed Desktop suchen.</span><span class="sxs-lookup"><span data-stu-id="eae79-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="eae79-119">Wir zeigen, dass Sie sich bei Microsoft Managed Desktop Portal anmelden.</span><span class="sxs-lookup"><span data-stu-id="eae79-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.    <span data-ttu-id="eae79-120">Melden Sie sich beim [Microsoft Managed Desktop-Verwaltungsportal](https://aka.ms/mmdportal)an.</span><span class="sxs-lookup"><span data-stu-id="eae79-120">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span> 
2.    <span data-ttu-id="eae79-121">Wählen Sie unter **Inventar** die Option **apps** aus.</span><span class="sxs-lookup"><span data-stu-id="eae79-121">Under **Inventory** , select **Apps** .</span></span>
3.    <span data-ttu-id="eae79-122">Wählen Sie in der Arbeitsauslastung von apps die Option **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="eae79-122">In the Apps workload, select **Add** .</span></span>
4.    <span data-ttu-id="eae79-123">Wählen Sie unter **app hinzufügen** die Option **Branchen-App** oder **Windows-app (Win32)** aus.</span><span class="sxs-lookup"><span data-stu-id="eae79-123">In **Add app** , select **Line-of-business app** or **Windows app (Win32)** .</span></span>
    - <span data-ttu-id="eae79-124">Wenn Sie die Branchen **-App** ausgewählt haben, finden Sie unter [Hinzufügen einer Windows-Branchen-APP zu Microsoft InTune](https://docs.microsoft.com/intune/lob-apps-windows) Anweisungen zum Hinzufügen und Konfigurieren von Branchen-apps.</span><span class="sxs-lookup"><span data-stu-id="eae79-124">If you selected **Line-of-business app** , see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="eae79-125">Wenn Sie **Windows-app (Win32)** ausgewählt haben, finden Sie unter [Win32 App Management](https://docs.microsoft.com/intune/apps-win32-app-management) Anweisungen zum Hinzufügen und Konfigurieren von Windows-apps.</span><span class="sxs-lookup"><span data-stu-id="eae79-125">If you selected **Windows app (Win32)** , see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="eae79-126">Microsoft Store for Business-Apps</span><span class="sxs-lookup"><span data-stu-id="eae79-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="eae79-127">Wenn Sie sich nicht bei Microsoft Store for Business angemeldet haben, können Sie sich anmelden, wenn Sie apps kaufen.</span><span class="sxs-lookup"><span data-stu-id="eae79-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="eae79-128">Nachdem Sie Ihre apps haben, können Sie Sie mit dem Microsoft Managed Desktop synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="eae79-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="eae79-129">**So kaufen Sie Apps aus dem Microsoft Store for Business**</span><span class="sxs-lookup"><span data-stu-id="eae79-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="eae79-130">Melden Sie sich mit Ihrem Microsoft Store for Business-Administratorkonto bei [Microsoft Store for Business](https://businessstore.microsoft.com) an.</span><span class="sxs-lookup"><span data-stu-id="eae79-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="eae79-131">Wählen Sie **für meine Gruppe Shop** aus.</span><span class="sxs-lookup"><span data-stu-id="eae79-131">Select **Shop for my group** .</span></span>
3. <span data-ttu-id="eae79-132">Verwenden Sie die Suche, um die gewünschte APP zu finden, und wählen Sie die APP aus.</span><span class="sxs-lookup"><span data-stu-id="eae79-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="eae79-133">Wählen Sie auf den Produkt Details **die Option App abrufen** aus.</span><span class="sxs-lookup"><span data-stu-id="eae79-133">On the product details, select **Get the App** .</span></span> <span data-ttu-id="eae79-134">Mit dem Microsoft Store wird die APP **ihren Produkten** für Ihre Organisation hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="eae79-134">Microsoft Store adds the app to **Your products** for your organization.</span></span>

<span data-ttu-id="eae79-135">**So erzwingen Sie eine Synchronisierung zwischen InTune und Microsoft Store for Business**</span><span class="sxs-lookup"><span data-stu-id="eae79-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="eae79-136">Melden Sie sich beim [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431)an.</span><span class="sxs-lookup"><span data-stu-id="eae79-136">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>
2. <span data-ttu-id="eae79-137">Wählen Sie **Mandanten Administrations**  >  **-Konnektoren und Token**  >  **für Microsoft Store for Business** aus.</span><span class="sxs-lookup"><span data-stu-id="eae79-137">Select **Tenant administration** > **Connectors and tokens** > **Microsoft Store for Business** .</span></span>
3. <span data-ttu-id="eae79-138">Wählen Sie **Synchronisieren** aus, um die apps, die Sie aus dem Microsoft Store erworben haben, in InTune zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="eae79-138">Select **Sync** to get the apps you've purchased from the Microsoft Store into Intune.</span></span>

<span data-ttu-id="eae79-139">**So stellen Sie sicher, dass eine Synchronisierung zwischen InTune und Microsoft Store for Business aktiv ist**</span><span class="sxs-lookup"><span data-stu-id="eae79-139">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="eae79-140">Melden Sie sich mit Ihrem Microsoft Store for Business-Administratorkonto bei [Microsoft Store for Business](https://businessstore.microsoft.com) an.</span><span class="sxs-lookup"><span data-stu-id="eae79-140">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="eae79-141">Wählen Sie **Manage** aus.</span><span class="sxs-lookup"><span data-stu-id="eae79-141">Select **Manage** .</span></span>
3. <span data-ttu-id="eae79-142">Wählen Sie **Einstellungen** aus, und wählen Sie dann **verteilen** aus.</span><span class="sxs-lookup"><span data-stu-id="eae79-142">Select **Settings** and then select **Distribute** .</span></span>
4. <span data-ttu-id="eae79-143">Überprüfen Sie unter **Verwaltungstools** , ob InTune aufgeführt ist und ob der Status **aktiv** ist.</span><span class="sxs-lookup"><span data-stu-id="eae79-143">Under **Management tools** , verify that Intune is listed and that the status is **Active** .</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="eae79-144">Schritt 2: Erstellen von Azure Ad Gruppen</span><span class="sxs-lookup"><span data-stu-id="eae79-144">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="eae79-145">Erstellen Sie für jede APP drei Azure Ad Gruppen.</span><span class="sxs-lookup"><span data-stu-id="eae79-145">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="eae79-146">In dieser Tabelle werden die Gruppen beschrieben, die Sie benötigen (verfügbar, erforderlich und Uninstall).</span><span class="sxs-lookup"><span data-stu-id="eae79-146">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="eae79-147">Zuordnungstyp "App"</span><span class="sxs-lookup"><span data-stu-id="eae79-147">App assignment type</span></span> |    <span data-ttu-id="eae79-148">Gruppenverwendung</span><span class="sxs-lookup"><span data-stu-id="eae79-148">Group use</span></span>    | <span data-ttu-id="eae79-149">Beispiel Azure Ad Name</span><span class="sxs-lookup"><span data-stu-id="eae79-149">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="eae79-150">Available</span><span class="sxs-lookup"><span data-stu-id="eae79-150">Available</span></span> |  <span data-ttu-id="eae79-151">Die APP wird über die APP oder Website des Unternehmensportals verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="eae79-151">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="eae79-152">MMD – *App-Name* – verfügbar</span><span class="sxs-lookup"><span data-stu-id="eae79-152">MMD – *app name* – Available</span></span>
<span data-ttu-id="eae79-153">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="eae79-153">Required</span></span> |  <span data-ttu-id="eae79-154">Die APP wird auf Geräten in den ausgewählten Gruppen installiert.</span><span class="sxs-lookup"><span data-stu-id="eae79-154">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="eae79-155">MMD – *App-Name* – erforderlich</span><span class="sxs-lookup"><span data-stu-id="eae79-155">MMD – *app name* – Required</span></span>
<span data-ttu-id="eae79-156">Uninstall</span><span class="sxs-lookup"><span data-stu-id="eae79-156">Uninstall</span></span> |  <span data-ttu-id="eae79-157">Die APP wird von Geräten in den ausgewählten Gruppen deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="eae79-157">The app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="eae79-158">MMD – *App-Name* – deinstallieren</span><span class="sxs-lookup"><span data-stu-id="eae79-158">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="eae79-159">Fügen Sie Ihre Benutzer zu diesen Gruppen hinzu, um entweder die APP zur Verfügung zu stellen, die APP zu installieren oder die APP von Ihrem von Microsoft verwalteten Desktop Gerät zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="eae79-159">Add your users to these groups to either make the app available, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="eae79-160">Schritt 3: Zuweisen von apps zu Benutzern</span><span class="sxs-lookup"><span data-stu-id="eae79-160">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="eae79-161">**So weisen Sie die APP Ihren Benutzern zu**</span><span class="sxs-lookup"><span data-stu-id="eae79-161">**To assign the app to your users**</span></span>

1. <span data-ttu-id="eae79-162">Melden Sie sich beim [Microsoft Managed Desktop-Verwaltungsportal](https://aka.ms/mmdportal)an.</span><span class="sxs-lookup"><span data-stu-id="eae79-162">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="eae79-163">Wählen Sie im Bereich verwalteter Desktop die Option **apps** aus.</span><span class="sxs-lookup"><span data-stu-id="eae79-163">In Managed Desktop pane, select **Apps** .</span></span>
3. <span data-ttu-id="eae79-164">Wählen Sie in der Arbeitsauslastung Apps die APP aus, der Sie Benutzer zuweisen möchten, und wählen Sie **Benutzergruppen zuweisen** aus.</span><span class="sxs-lookup"><span data-stu-id="eae79-164">In the Apps workload, select the app you want to assign users to and select **Assign users groups** .</span></span>
4. <span data-ttu-id="eae79-165">Wählen Sie für die jeweilige APP einen Zuordnungstyp (verfügbar, erforderlich, deinstallieren) aus, und weisen Sie die entsprechende Gruppe zu.</span><span class="sxs-lookup"><span data-stu-id="eae79-165">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="eae79-166">Wählen Sie im Bereich apps zuweisen die Option **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="eae79-166">In the Assign Apps pane, select **OK** .</span></span>


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="eae79-167">Schritte zum Einstieg in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="eae79-167">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="eae79-168">Hinzufügen und Überprüfen von Administrator-Kontakten im-Administratorportal</span><span class="sxs-lookup"><span data-stu-id="eae79-168">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="eae79-169">Bedingten Zugriff anpassen</span><span class="sxs-lookup"><span data-stu-id="eae79-169">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="eae79-170">Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="eae79-170">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="eae79-171">Intune-Unternehmensportal bereitstellen</span><span class="sxs-lookup"><span data-stu-id="eae79-171">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="eae79-172">Aktivieren von Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="eae79-172">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="eae79-173">Einrichten von Geräten</span><span class="sxs-lookup"><span data-stu-id="eae79-173">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="eae79-174">Vorbereiten Ihrer Benutzer für die Verwendung von Geräten</span><span class="sxs-lookup"><span data-stu-id="eae79-174">Get your users ready to use devices</span></span>](get-started-devices.md)
8. <span data-ttu-id="eae79-175">Bereitstellen von apps (dieses Thema)</span><span class="sxs-lookup"><span data-stu-id="eae79-175">Deploy apps (this topic)</span></span>


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
