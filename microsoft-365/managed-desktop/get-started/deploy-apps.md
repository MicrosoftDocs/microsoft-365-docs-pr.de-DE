---
title: Bereitstellen von apps auf Geräten
description: Informationen zum Hinzufügen und Bereitstellen von apps auf Microsoft Managed Desktop-Geräten.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation, apps, Branchenanwendungen, Lob-apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5f1e2bd2440b5c38c958d3182684e87643f2e853
ms.sourcegitcommit: 3d37043c0447359c952dc99026c219dd69f6fb8d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/06/2019
ms.locfileid: "38012026"
---
# <a name="deploy-apps-to-devices"></a><span data-ttu-id="9b03a-104">Bereitstellen von apps auf Geräten</span><span class="sxs-lookup"><span data-stu-id="9b03a-104">Deploy apps to devices</span></span>
<span data-ttu-id="9b03a-105">Ein Teil des onboardings für Microsoft Managed Desktop umfasst das Hinzufügen und Bereitstellen von apps auf den Geräten Ihrer Benutzer.</span><span class="sxs-lookup"><span data-stu-id="9b03a-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user’s devices.</span></span> <span data-ttu-id="9b03a-106">Nachdem Sie das Microsoft Managed Desktop Portal verwendet haben, können Sie Ihre apps hinzufügen und bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="9b03a-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="9b03a-107">Der Gesamtprozess sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="9b03a-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="9b03a-108">[Hinzufügen von apps zu Microsoft Managed Desktop Portal](#1) -Dies kann vorhandene Branchen-Apps oder Apps aus dem Microsoft Store for Business sein, die Sie mit InTune synchronisiert haben.</span><span class="sxs-lookup"><span data-stu-id="9b03a-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="9b03a-109">[Erstellen von Azure Active Directory (AD)-Gruppen für die APP-Zuweisung](#2) -Sie verwenden diese Gruppen zum Verwalten der APP-Zuweisung.</span><span class="sxs-lookup"><span data-stu-id="9b03a-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="9b03a-110">Zuweisen von apps zu Benutzern</span><span class="sxs-lookup"><span data-stu-id="9b03a-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="9b03a-111">Schritt 1: Hinzufügen von apps zu Microsoft Managed Desktop Portal</span><span class="sxs-lookup"><span data-stu-id="9b03a-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="9b03a-112">Sie können [Win32-oder Windows MSI-basierte apps](#lob-apps)oder [Microsoft Store for Business-Apps](#msfb-apps) zu Microsoft Managed Desktop hinzufügen und diese dann auf Microsoft Managed Desktop-Geräten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="9b03a-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="9b03a-113">Win32-oder Windows MSI-basierte apps auf Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="9b03a-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="9b03a-114">Sie können Ihre Branchen-apps zu Microsoft Managed Desktop Portal hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9b03a-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="9b03a-115">Informationen zu den Anforderungen für apps, die auf Microsoft Managed Desktop-Geräten installiert sind, finden Sie unter [Microsoft Managed Desktop App Requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span><span class="sxs-lookup"><span data-stu-id="9b03a-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="9b03a-116">In diesem Verfahren wählen Sie aus, welche App-Art Sie hinzufügen möchten, und konfigurieren und laden dann die APP-Quelle.</span><span class="sxs-lookup"><span data-stu-id="9b03a-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="9b03a-117">**So fügen Sie Ihre Branchen-APP oder Windows-APP zu einem Microsoft Managed Desktop-Portal hinzu**</span><span class="sxs-lookup"><span data-stu-id="9b03a-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="9b03a-118">Sie können sich bei Microsoft Managed Desktop Portal anmelden oder sich bei InTune anmelden und dann nach Microsoft Managed Desktop suchen.</span><span class="sxs-lookup"><span data-stu-id="9b03a-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="9b03a-119">Wir zeigen, dass Sie sich bei Microsoft Managed Desktop Portal anmelden.</span><span class="sxs-lookup"><span data-stu-id="9b03a-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.  <span data-ttu-id="9b03a-120">Melden Sie sich beim [Microsoft Managed Desktop-Verwaltungsportal](https://aka.ms/mmdportal)an.</span><span class="sxs-lookup"><span data-stu-id="9b03a-120">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span> 
2.  <span data-ttu-id="9b03a-121">Wählen Sie unter **Inventar**die Option **apps**aus.</span><span class="sxs-lookup"><span data-stu-id="9b03a-121">Under **Inventory**, select **Apps**.</span></span>
3.  <span data-ttu-id="9b03a-122">Wählen Sie in der Arbeitsauslastung von apps die Option **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="9b03a-122">In the Apps workload, select **Add**.</span></span>
4.  <span data-ttu-id="9b03a-123">Wählen Sie unter **app hinzufügen**die Option **Branchen-App** oder **Windows-app (Win32)** aus.</span><span class="sxs-lookup"><span data-stu-id="9b03a-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32)**.</span></span>
    - <span data-ttu-id="9b03a-124">Wenn Sie die Branchen **-App**ausgewählt haben, finden Sie unter [Hinzufügen einer Windows-Branchen-APP zu Microsoft InTune](https://docs.microsoft.com/intune/lob-apps-windows) Anweisungen zum Hinzufügen und Konfigurieren von Branchen-apps.</span><span class="sxs-lookup"><span data-stu-id="9b03a-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="9b03a-125">Wenn Sie **Windows-app (Win32)** ausgewählt haben, finden Sie unter [Win32 App Management](https://docs.microsoft.com/intune/apps-win32-app-management) Anweisungen zum Hinzufügen und Konfigurieren von Windows-apps.</span><span class="sxs-lookup"><span data-stu-id="9b03a-125">If you selected **Windows app (Win32)**, see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="9b03a-126">Microsoft Store for Business-Apps</span><span class="sxs-lookup"><span data-stu-id="9b03a-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="9b03a-127">Wenn Sie sich nicht bei Microsoft Store for Business angemeldet haben, können Sie sich anmelden, wenn Sie apps kaufen.</span><span class="sxs-lookup"><span data-stu-id="9b03a-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="9b03a-128">Nachdem Sie Ihre apps haben, können Sie Sie mit dem Microsoft Managed Desktop synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="9b03a-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="9b03a-129">**So kaufen Sie Apps aus dem Microsoft Store for Business**</span><span class="sxs-lookup"><span data-stu-id="9b03a-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="9b03a-130">Melden Sie sich mit Ihrem Microsoft Store for Business-Administratorkonto bei [Microsoft Store for Business](https://businessstore.microsoft.com) an.</span><span class="sxs-lookup"><span data-stu-id="9b03a-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="9b03a-131">Wählen Sie **für meine Gruppe Shop**aus.</span><span class="sxs-lookup"><span data-stu-id="9b03a-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="9b03a-132">Verwenden Sie die Suche, um die gewünschte APP zu finden, und wählen Sie die APP aus.</span><span class="sxs-lookup"><span data-stu-id="9b03a-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="9b03a-133">Wählen Sie auf den Produkt Details **die Option App abrufen**aus.</span><span class="sxs-lookup"><span data-stu-id="9b03a-133">On the product details, select **Get the App**.</span></span> <span data-ttu-id="9b03a-134">Microsoft Store fügt die APP den **Produkten #a0 Diensten** für Ihre Organisation hinzu.</span><span class="sxs-lookup"><span data-stu-id="9b03a-134">Microsoft Store adds the app to **Products & services** for your organization.</span></span>

<span data-ttu-id="9b03a-135">**So erzwingen Sie eine Synchronisierung zwischen InTune und Microsoft Store for Business**</span><span class="sxs-lookup"><span data-stu-id="9b03a-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="9b03a-136">Melden Sie sich beim [Azure-Portal](https://portal.azure.com/) als InTune-Administrator oder globaler Administrator für Ihren Mandanten an.</span><span class="sxs-lookup"><span data-stu-id="9b03a-136">Sign in to [Azure Portal](https://portal.azure.com/) as Intune Admin or Global Admin for your tenant</span></span>
2. <span data-ttu-id="9b03a-137">Wählen Sie **alle Dienste #a0 InTune**aus.</span><span class="sxs-lookup"><span data-stu-id="9b03a-137">Select **All services > Intune**.</span></span> <span data-ttu-id="9b03a-138">InTune befindet sich im Abschnitt Überwachung + Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="9b03a-138">Intune is in the Monitoring + Management section.</span></span>
3. <span data-ttu-id="9b03a-139">Wählen Sie im Bereich InTune die Option **Client apps**aus, und wählen Sie dann **Microsoft Store for Business**aus.</span><span class="sxs-lookup"><span data-stu-id="9b03a-139">In the Intune pane, select **Client Apps**, and then select **Microsoft Store for Business**.</span></span>
4. <span data-ttu-id="9b03a-140">Wählen Sie **aktivieren** aus, um Ihren Microsoft Store for Business-Apps mit InTune zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="9b03a-140">Select **Enable** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="9b03a-141">Wenn Sie noch nicht angemeldet sind, registrieren und Ihr Microsoft Store for Business-Konto mit InTune verknüpfen</span><span class="sxs-lookup"><span data-stu-id="9b03a-141">If you haven't already, sign up and associate your Microsoft Store for Business account with Intune</span></span>
    - <span data-ttu-id="9b03a-142">Wählen Sie die Sprache aus, in der Apps aus dem Microsoft Store for Business in ihrer InTune-Konsole angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9b03a-142">Select the language in which apps from the Microsoft Store for Business will be displayed in your Intune console</span></span>
    - <span data-ttu-id="9b03a-143">Wählen Sie **Sync** aus, um Ihren Microsoft Store for Business-Apps mit InTune zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="9b03a-143">Select **Sync** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="9b03a-144">Stellen Sie sicher, dass die Synchronisierung zwischen Microsoft Store for Business und InTune aktiv ist (nächster Schritt).</span><span class="sxs-lookup"><span data-stu-id="9b03a-144">Verify that the sync between Microsoft Store for Business and Intune is active (next step).</span></span> 

<span data-ttu-id="9b03a-145">**So stellen Sie sicher, dass eine Synchronisierung zwischen InTune und Microsoft Store for Business aktiv ist**</span><span class="sxs-lookup"><span data-stu-id="9b03a-145">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="9b03a-146">Melden Sie sich mit Ihrem Microsoft Store for Business-Administratorkonto bei [Microsoft Store for Business](https://businessstore.microsoft.com) an.</span><span class="sxs-lookup"><span data-stu-id="9b03a-146">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="9b03a-147">Wählen Sie **Manage**aus.</span><span class="sxs-lookup"><span data-stu-id="9b03a-147">Select **Manage**.</span></span>
3. <span data-ttu-id="9b03a-148">Wählen Sie **Einstellungen** aus, und wählen Sie dann **verteilen**aus.</span><span class="sxs-lookup"><span data-stu-id="9b03a-148">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="9b03a-149">Überprüfen Sie unter **Verwaltungstools**, ob InTune aufgeführt ist und ob der Status **aktiv**ist.</span><span class="sxs-lookup"><span data-stu-id="9b03a-149">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="9b03a-150">Schritt 2: Erstellen von Azure Ad Gruppen</span><span class="sxs-lookup"><span data-stu-id="9b03a-150">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="9b03a-151">Erstellen Sie für jede APP drei Azure Ad Gruppen.</span><span class="sxs-lookup"><span data-stu-id="9b03a-151">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="9b03a-152">In dieser Tabelle werden die Gruppen beschrieben, die Sie benötigen (verfügbar, erforderlich und Uninstall).</span><span class="sxs-lookup"><span data-stu-id="9b03a-152">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="9b03a-153">Zuordnungstyp "App"</span><span class="sxs-lookup"><span data-stu-id="9b03a-153">App assignment type</span></span> |   <span data-ttu-id="9b03a-154">Gruppenverwendung</span><span class="sxs-lookup"><span data-stu-id="9b03a-154">Group use</span></span>   | <span data-ttu-id="9b03a-155">Beispiel Azure Ad Name</span><span class="sxs-lookup"><span data-stu-id="9b03a-155">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="9b03a-156">Available</span><span class="sxs-lookup"><span data-stu-id="9b03a-156">Available</span></span> |  <span data-ttu-id="9b03a-157">Die APP wird über die APP oder Website des Unternehmensportals verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="9b03a-157">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="9b03a-158">MMD – *App-Name* – verfügbar</span><span class="sxs-lookup"><span data-stu-id="9b03a-158">MMD – *app name* – Available</span></span>
<span data-ttu-id="9b03a-159">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="9b03a-159">Required</span></span> |  <span data-ttu-id="9b03a-160">Die APP wird auf Geräten in den ausgewählten Gruppen installiert.</span><span class="sxs-lookup"><span data-stu-id="9b03a-160">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="9b03a-161">MMD – *App-Name* – erforderlich</span><span class="sxs-lookup"><span data-stu-id="9b03a-161">MMD – *app name* – Required</span></span>
<span data-ttu-id="9b03a-162">Uninstall</span><span class="sxs-lookup"><span data-stu-id="9b03a-162">Uninstall</span></span> |  <span data-ttu-id="9b03a-163">Die APP wird auf den Geräten in den ausgewählten Gruppen deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="9b03a-163">TThe app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="9b03a-164">MMD – *App-Name* – deinstallieren</span><span class="sxs-lookup"><span data-stu-id="9b03a-164">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="9b03a-165">Fügen Sie Ihre Benutzer zu diesen Gruppen hinzu, um entweder die app verfügbar zu machen, die APP zu installieren oder die APP von Ihrem von Microsoft verwalteten Desktop Gerät zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="9b03a-165">Add your users to these groups to either make the app availabe, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="9b03a-166">Schritt 3: Zuweisen von apps zu Benutzern</span><span class="sxs-lookup"><span data-stu-id="9b03a-166">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="9b03a-167">**So weisen Sie die APP Ihren Benutzern zu**</span><span class="sxs-lookup"><span data-stu-id="9b03a-167">**To assign the app to your users**</span></span>

1. <span data-ttu-id="9b03a-168">Melden Sie sich beim [Microsoft Managed Desktop-Verwaltungsportal](https://aka.ms/mmdportal)an.</span><span class="sxs-lookup"><span data-stu-id="9b03a-168">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="9b03a-169">Wählen Sie im Bereich verwalteter Desktop die Option **apps**aus.</span><span class="sxs-lookup"><span data-stu-id="9b03a-169">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="9b03a-170">Wählen Sie in der Arbeitsauslastung Apps die APP aus, der Sie Benutzer zuweisen möchten, und wählen Sie **Benutzergruppen zuweisen**aus.</span><span class="sxs-lookup"><span data-stu-id="9b03a-170">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="9b03a-171">Wählen Sie für die jeweilige APP einen Zuordnungstyp (verfügbar, erforderlich, deinstallieren) aus, und weisen Sie die entsprechende Gruppe zu.</span><span class="sxs-lookup"><span data-stu-id="9b03a-171">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="9b03a-172">Wählen Sie im Bereich apps zuweisen die Option **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="9b03a-172">In the Assign Apps pane, select **OK**.</span></span>


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="9b03a-173">Schritte zum Einstieg in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="9b03a-173">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="9b03a-174">Hinzufügen und Überprüfen von Administrator Kontakten im Administratorportal</span><span class="sxs-lookup"><span data-stu-id="9b03a-174">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="9b03a-175">Anpassen des bedingten Zugriffs</span><span class="sxs-lookup"><span data-stu-id="9b03a-175">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="9b03a-176">Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="9b03a-176">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="9b03a-177">Bereitstellen des InTune-Unternehmensportals</span><span class="sxs-lookup"><span data-stu-id="9b03a-177">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="9b03a-178">Aktivieren des Enterprise-Status-Roaming</span><span class="sxs-lookup"><span data-stu-id="9b03a-178">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="9b03a-179">Einrichten von Geräten</span><span class="sxs-lookup"><span data-stu-id="9b03a-179">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="9b03a-180">Vorbereiten Ihrer Benutzer für die Verwendung von Geräten</span><span class="sxs-lookup"><span data-stu-id="9b03a-180">Get your users ready to use devices</span></span>](get-started-devices.md)
8. <span data-ttu-id="9b03a-181">Bereitstellen von apps (dieses Thema)</span><span class="sxs-lookup"><span data-stu-id="9b03a-181">Deploy apps (this topic)</span></span>


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
