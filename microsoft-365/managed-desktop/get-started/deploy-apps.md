---
title: Bereitstellen von Apps auf Geräten
description: Informationen zum Hinzufügen und Bereitstellen von Apps auf Microsoft Managed Desktop Geräten.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation, Apps, Branchen-Apps, Branchen-Apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8bfc53d46bdcb91c16e9f4a1ddbc8ab3f6dfb47e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922026"
---
# <a name="deploy-apps-to-devices"></a><span data-ttu-id="0e814-104">Bereitstellen von Apps auf Geräten</span><span class="sxs-lookup"><span data-stu-id="0e814-104">Deploy apps to devices</span></span>
<span data-ttu-id="0e814-105">Ein Teil des Onboardings Microsoft Managed Desktop umfasst das Hinzufügen und Bereitstellen von Apps auf den Geräten Ihres Benutzers.</span><span class="sxs-lookup"><span data-stu-id="0e814-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user's devices.</span></span> <span data-ttu-id="0e814-106">Sobald Sie das Microsoft Managed Desktop verwenden, können Sie Ihre Apps hinzufügen und bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0e814-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="0e814-107">Der Gesamteindruck sieht wie dies aus:</span><span class="sxs-lookup"><span data-stu-id="0e814-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="0e814-108">[Hinzufügen von Apps zu Microsoft Managed Desktop](#1) Portal : Dies kann vorhandene Branchen-Apps (Line-of-Business) oder Apps aus Microsoft Store für Unternehmen, die Sie mit Intune synchronisiert haben.</span><span class="sxs-lookup"><span data-stu-id="0e814-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="0e814-109">[Erstellen Azure Active Directory (AD)-Gruppen](#2) für die App-Zuweisung – Sie verwenden diese Gruppen zum Verwalten der App-Zuweisung.</span><span class="sxs-lookup"><span data-stu-id="0e814-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="0e814-110">Zuweisen von Apps zu Ihren Benutzern</span><span class="sxs-lookup"><span data-stu-id="0e814-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="0e814-111">Schritt 1: Hinzufügen von Apps zum Microsoft Managed Desktop Portal</span><span class="sxs-lookup"><span data-stu-id="0e814-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="0e814-112">Sie können [Win32 oder Windows MSI-basierten](#lob-apps)Apps oder [Microsoft Store für Unternehmen-Apps](#msfb-apps) zu Microsoft Managed Desktop hinzufügen und dann auf Microsoft Managed Desktop bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0e814-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="0e814-113">Win32 oder Windows MSI-basierten Apps für Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="0e814-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="0e814-114">Sie können Ihre Branchen-Apps (Line-of-Business) zu Microsoft Managed Desktop hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0e814-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="0e814-115">Informationen zu den Anforderungen für Apps, die auf Microsoft Managed Desktop installiert sind, finden Sie [unter Microsoft Managed Desktop App Requirements](../service-description/mmd-app-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e814-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>

<span data-ttu-id="0e814-116">In diesem Verfahren wählen Sie aus, welche Art von App Sie hinzufügen möchten, und konfigurieren und laden die App-Quelle hoch.</span><span class="sxs-lookup"><span data-stu-id="0e814-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="0e814-117">**So fügen Sie Ihre Branchen-App oder Windows-App zum Microsoft Managed Desktop hinzu**</span><span class="sxs-lookup"><span data-stu-id="0e814-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="0e814-118">Sie können sich bei Microsoft Managed Desktop oder bei Intune anmelden und dann nach Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="0e814-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="0e814-119">Wir zeigen die Anmeldung beim Microsoft Managed Desktop an.</span><span class="sxs-lookup"><span data-stu-id="0e814-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.    <span data-ttu-id="0e814-120">Melden Sie sich bei [Microsoft Managed Desktop Administratorportal an.](https://aka.ms/mmdportal)</span><span class="sxs-lookup"><span data-stu-id="0e814-120">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span> 
2.    <span data-ttu-id="0e814-121">Wählen **Sie unter Inventar** die Option **Apps aus.**</span><span class="sxs-lookup"><span data-stu-id="0e814-121">Under **Inventory**, select **Apps**.</span></span>
3.    <span data-ttu-id="0e814-122">Wählen Sie in der Arbeitsauslastung apps die Option **Hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="0e814-122">In the Apps workload, select **Add**.</span></span>
4.    <span data-ttu-id="0e814-123">Wählen **Sie in App** hinzufügen die Option **Business-App** oder **Windows App (Win32) aus.**</span><span class="sxs-lookup"><span data-stu-id="0e814-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32)**.</span></span>
    - <span data-ttu-id="0e814-124">Wenn Sie **die Line-of-Business-App** ausgewählt haben, finden Sie [unter Add a Windows line-of-business app to Microsoft Intune](/intune/lob-apps-windows) anweisungen zum Hinzufügen und Konfigurieren von Business-Apps.</span><span class="sxs-lookup"><span data-stu-id="0e814-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="0e814-125">Wenn Sie eine **Windows (Win32)** ausgewählt haben, finden Sie unter [Win32-App-Verwaltung](/intune/apps-win32-app-management) Anweisungen zum Hinzufügen und Konfigurieren Windows Apps.</span><span class="sxs-lookup"><span data-stu-id="0e814-125">If you selected **Windows app (Win32)**, see [Win32 app management](/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="0e814-126">Microsoft Store für Unternehmen Apps</span><span class="sxs-lookup"><span data-stu-id="0e814-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="0e814-127">Wenn Sie sich nicht bei Microsoft Store für Unternehmen angemeldet haben, können Sie sich registrieren, wenn Sie apps kaufen.</span><span class="sxs-lookup"><span data-stu-id="0e814-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="0e814-128">Nachdem Sie Ihre Apps installiert haben, können Sie sie mit Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="0e814-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="0e814-129">**So kaufen Sie Apps aus Microsoft Store für Unternehmen**</span><span class="sxs-lookup"><span data-stu-id="0e814-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="0e814-130">Melden Sie sich [bei Microsoft Store für Unternehmen](https://businessstore.microsoft.com) mit Ihrem Microsoft Store für Unternehmen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="0e814-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="0e814-131">Wählen **Sie Shop für meine Gruppe aus.**</span><span class="sxs-lookup"><span data-stu-id="0e814-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="0e814-132">Verwenden Sie Die Suche, um die gesuchte App zu finden, und wählen Sie die App aus.</span><span class="sxs-lookup"><span data-stu-id="0e814-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="0e814-133">Wählen Sie in den Produktdetails die Option **App erhalten aus.**</span><span class="sxs-lookup"><span data-stu-id="0e814-133">On the product details, select **Get the App**.</span></span> <span data-ttu-id="0e814-134">Microsoft Store fügt die App Zu **Ihren Produkten für** Ihre Organisation hinzu.</span><span class="sxs-lookup"><span data-stu-id="0e814-134">Microsoft Store adds the app to **Your products** for your organization.</span></span>

<span data-ttu-id="0e814-135">**So erzwingen Sie eine Synchronisierung zwischen Intune und Microsoft Store für Unternehmen**</span><span class="sxs-lookup"><span data-stu-id="0e814-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="0e814-136">Melden Sie sich beim [Microsoft Endpoint Manager Admin Center an.](https://go.microsoft.com/fwlink/?linkid=2109431)</span><span class="sxs-lookup"><span data-stu-id="0e814-136">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>
2. <span data-ttu-id="0e814-137">Wählen **Sie Mandantenverwaltungsconnectors**  >  **und Token**  >  **Microsoft Store für Unternehmen**.</span><span class="sxs-lookup"><span data-stu-id="0e814-137">Select **Tenant administration** > **Connectors and tokens** > **Microsoft Store for Business**.</span></span>
3. <span data-ttu-id="0e814-138">Wählen **Sie Synchronisierung** aus, um die Apps, die Sie aus dem Microsoft Store in Intune erworben haben, zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0e814-138">Select **Sync** to get the apps you've purchased from the Microsoft Store into Intune.</span></span>

<span data-ttu-id="0e814-139">**So überprüfen Sie, ob eine Synchronisierung zwischen Intune und Microsoft Store für Unternehmen aktiv ist**</span><span class="sxs-lookup"><span data-stu-id="0e814-139">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="0e814-140">Melden Sie sich [bei Microsoft Store für Unternehmen](https://businessstore.microsoft.com) mit Ihrem Microsoft Store für Unternehmen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="0e814-140">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="0e814-141">Wählen Sie **Verwalten aus.**</span><span class="sxs-lookup"><span data-stu-id="0e814-141">Select **Manage**.</span></span>
3. <span data-ttu-id="0e814-142">Wählen **Einstellungen** und dann **Verteilen aus.**</span><span class="sxs-lookup"><span data-stu-id="0e814-142">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="0e814-143">Überprüfen **Sie unter Verwaltungstools,** ob Intune aufgeführt ist und ob der Status **Aktiv ist.**</span><span class="sxs-lookup"><span data-stu-id="0e814-143">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="0e814-144">Schritt 2: Erstellen von Azure AD-Gruppen</span><span class="sxs-lookup"><span data-stu-id="0e814-144">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="0e814-145">Erstellen Sie drei Azure AD-Gruppen für jede App.</span><span class="sxs-lookup"><span data-stu-id="0e814-145">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="0e814-146">In dieser Tabelle sind die benötigten Gruppen (Verfügbar, Erforderlich und Deinstallieren) aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="0e814-146">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="0e814-147">App-Zuweisungstyp</span><span class="sxs-lookup"><span data-stu-id="0e814-147">App assignment type</span></span> |    <span data-ttu-id="0e814-148">Gruppennutzung</span><span class="sxs-lookup"><span data-stu-id="0e814-148">Group use</span></span>    | <span data-ttu-id="0e814-149">Azure AD-Beispielname</span><span class="sxs-lookup"><span data-stu-id="0e814-149">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="0e814-150">Available</span><span class="sxs-lookup"><span data-stu-id="0e814-150">Available</span></span> |  <span data-ttu-id="0e814-151">Die App ist über Unternehmensportal oder Website verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0e814-151">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="0e814-152">MMD – *App-Name* – Verfügbar</span><span class="sxs-lookup"><span data-stu-id="0e814-152">MMD – *app name* – Available</span></span>
<span data-ttu-id="0e814-153">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="0e814-153">Required</span></span> |  <span data-ttu-id="0e814-154">Die App wird auf Geräten in den ausgewählten Gruppen installiert.</span><span class="sxs-lookup"><span data-stu-id="0e814-154">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="0e814-155">MMD – *App-Name* – Erforderlich</span><span class="sxs-lookup"><span data-stu-id="0e814-155">MMD – *app name* – Required</span></span>
<span data-ttu-id="0e814-156">Deinstallieren</span><span class="sxs-lookup"><span data-stu-id="0e814-156">Uninstall</span></span> |  <span data-ttu-id="0e814-157">Die App wird von Geräten in den ausgewählten Gruppen deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="0e814-157">The app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="0e814-158">MMD – *App-Name* – Deinstallieren</span><span class="sxs-lookup"><span data-stu-id="0e814-158">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="0e814-159">Fügen Sie Ihre Benutzer zu diesen Gruppen hinzu, um die App entweder verfügbar zu machen, die App zu installieren oder die App von ihrem Microsoft Managed Desktop entfernen.</span><span class="sxs-lookup"><span data-stu-id="0e814-159">Add your users to these groups to either make the app available, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="0e814-160">Schritt 3: Zuweisen von Apps zu Ihren Benutzern</span><span class="sxs-lookup"><span data-stu-id="0e814-160">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="0e814-161">**So weisen Sie die App Ihren Benutzern zu**</span><span class="sxs-lookup"><span data-stu-id="0e814-161">**To assign the app to your users**</span></span>

1. <span data-ttu-id="0e814-162">Melden Sie sich bei [Microsoft Managed Desktop Administratorportal an.](https://aka.ms/mmdportal)</span><span class="sxs-lookup"><span data-stu-id="0e814-162">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="0e814-163">Wählen Sie im Bereich Verwalteter Desktop die Option **Apps aus.**</span><span class="sxs-lookup"><span data-stu-id="0e814-163">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="0e814-164">Wählen Sie in der Arbeitslast Apps die App aus, der Sie Benutzer zuweisen möchten, und wählen Sie **Benutzergruppen zuweisen aus.**</span><span class="sxs-lookup"><span data-stu-id="0e814-164">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="0e814-165">Wählen Sie für die spezifische App einen Zuweisungstyp (Verfügbar, Erforderlich, Deinstallieren) aus, und weisen Sie die entsprechende Gruppe zu.</span><span class="sxs-lookup"><span data-stu-id="0e814-165">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="0e814-166">Wählen Sie im Bereich Apps zuweisen die Option **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="0e814-166">In the Assign Apps pane, select **OK**.</span></span>


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="0e814-167">Schritte zum Einstieg in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="0e814-167">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="0e814-168">Hinzufügen und Überprüfen von Administrator-Kontakten im-Administratorportal</span><span class="sxs-lookup"><span data-stu-id="0e814-168">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="0e814-169">Bedingten Zugriff anpassen</span><span class="sxs-lookup"><span data-stu-id="0e814-169">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="0e814-170">Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="0e814-170">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="0e814-171">Intune-Unternehmensportal bereitstellen</span><span class="sxs-lookup"><span data-stu-id="0e814-171">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="0e814-172">Aktivieren von Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="0e814-172">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="0e814-173">Einrichten von Geräten</span><span class="sxs-lookup"><span data-stu-id="0e814-173">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="0e814-174">Vorbereiten Ihrer Benutzer für die Verwendung von Geräten</span><span class="sxs-lookup"><span data-stu-id="0e814-174">Get your users ready to use devices</span></span>](get-started-devices.md)
8. <span data-ttu-id="0e814-175">Bereitstellen von Apps (in diesem Thema)</span><span class="sxs-lookup"><span data-stu-id="0e814-175">Deploy apps (this topic)</span></span>


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->