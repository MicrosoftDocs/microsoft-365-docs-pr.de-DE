---
title: App-basierte Bereitstellung für Microsoft Defender für Endpunkt unter iOS
ms.reviewer: ''
description: Beschreibt, wie Microsoft Defender für Endpunkt unter iOS mithilfe einer App bereitgestellt wird
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, ios, App, Installation, bereitstellen, Deinstallation, Intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 371208433cbb0f65ab5a2808318c03dae6bb6d8b
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842290"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="64457-104">Bereitstellen von Microsoft Defender für Endpunkt unter iOS</span><span class="sxs-lookup"><span data-stu-id="64457-104">Deploy Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="64457-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="64457-105">**Applies to:**</span></span>
- [<span data-ttu-id="64457-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="64457-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="64457-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="64457-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="64457-108">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="64457-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="64457-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="64457-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="64457-110">In diesem Thema wird die Bereitstellung von Defender für Endpunkt unter iOS auf Intune-Unternehmensportal registrierten Geräten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="64457-110">This topic describes deploying Defender for Endpoint on iOS on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="64457-111">Weitere Informationen zur Intune-Geräteregistrierung finden Sie unter [Registrieren von iOS/iPadOS-Geräten in Intune.](/mem/intune/enrollment/ios-enroll)</span><span class="sxs-lookup"><span data-stu-id="64457-111">For more information about Intune device enrollment, see [Enroll iOS/iPadOS devices in Intune](/mem/intune/enrollment/ios-enroll).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="64457-112">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="64457-112">Before you begin</span></span>

- <span data-ttu-id="64457-113">Stellen Sie sicher, dass Sie Zugriff auf [das Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431)haben.</span><span class="sxs-lookup"><span data-stu-id="64457-113">Ensure you have access to [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>

- <span data-ttu-id="64457-114">Stellen Sie sicher, dass die iOS-Registrierung für Ihre Benutzer erfolgt.</span><span class="sxs-lookup"><span data-stu-id="64457-114">Ensure iOS enrollment is done for your users.</span></span> <span data-ttu-id="64457-115">Benutzern muss eine Defender für Endpunkt-Lizenz zugewiesen sein, um Defender für Endpunkt unter iOS verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="64457-115">Users need to have a Defender for Endpoint license assigned in order to use Defender for Endpoint on iOS.</span></span> <span data-ttu-id="64457-116">Anweisungen zum Zuweisen von Lizenzen finden Sie unter ["Zuweisen von Lizenzen an Benutzer".](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="64457-116">Refer to [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign) for instructions on how to assign licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="64457-117">Microsoft Defender für Endpunkt unter iOS ist in der [Apple-App Store](https://aka.ms/mdatpiosappstore)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="64457-117">Microsoft Defender for Endpoint on iOS is available in the [Apple App Store](https://aka.ms/mdatpiosappstore).</span></span>

## <a name="deployment-steps"></a><span data-ttu-id="64457-118">Bereitstellungsschritte</span><span class="sxs-lookup"><span data-stu-id="64457-118">Deployment steps</span></span>

<span data-ttu-id="64457-119">Bereitstellen von Defender für Endpunkt unter iOS über Intune-Unternehmensportal.</span><span class="sxs-lookup"><span data-stu-id="64457-119">Deploy Defender for Endpoint on iOS via Intune Company Portal.</span></span>

### <a name="add-ios-store-app"></a><span data-ttu-id="64457-120">Hinzufügen einer iOS Store-App</span><span class="sxs-lookup"><span data-stu-id="64457-120">Add iOS store app</span></span>

1. <span data-ttu-id="64457-121">Wechseln Sie [im Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431)zu **Apps**  ->  **iOS/iPadOS**  ->    ->  **Hinzufügen der iOS Store-App,** und klicken Sie auf **"Auswählen".**</span><span class="sxs-lookup"><span data-stu-id="64457-121">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Apps** -> **iOS/iPadOS** -> **Add** -> **iOS store app** and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="64457-122">![Abbildung von Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)</span><span class="sxs-lookup"><span data-stu-id="64457-122">![Image of Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)</span></span>

1. <span data-ttu-id="64457-123">Klicken Sie auf der Seite "App hinzufügen" auf **"App Store durchsuchen",** und geben Sie **Microsoft Defender Endpoint** in der Suchleiste ein.</span><span class="sxs-lookup"><span data-stu-id="64457-123">On the Add app page, click on **Search the App Store** and type **Microsoft Defender Endpoint** in the search bar.</span></span> <span data-ttu-id="64457-124">Klicken Sie im Abschnitt mit den Suchergebnissen auf *Microsoft Defender Endpoint,* und klicken Sie auf **"Auswählen".**</span><span class="sxs-lookup"><span data-stu-id="64457-124">In the search results section, click on *Microsoft Defender Endpoint* and click **Select**.</span></span>

1. <span data-ttu-id="64457-125">Wählen Sie **iOS 11.0** als Mindestbetriebssystem aus.</span><span class="sxs-lookup"><span data-stu-id="64457-125">Select **iOS 11.0** as the Minimum operating system.</span></span> <span data-ttu-id="64457-126">Überprüfen Sie die restlichen Informationen zur App, und klicken Sie auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="64457-126">Review the rest of information about the app and click **Next**.</span></span>

1. <span data-ttu-id="64457-127">Wechseln Sie im Abschnitt *Aufgaben* zum Abschnitt **Erforderlich ,** und wählen Sie **Gruppe hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="64457-127">In the *Assignments* section, go to the **Required** section and select **Add group**.</span></span> <span data-ttu-id="64457-128">Sie können dann die Benutzergruppe(n) auswählen, für die Sie Defender für Endpunkt in der iOS-App als Ziel verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="64457-128">You can then choose the user group(s) that you would like to target Defender for Endpoint on iOS app.</span></span> <span data-ttu-id="64457-129">Klicken Sie auf **"Auswählen"** und dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="64457-129">Click **Select** and then **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="64457-130">Die ausgewählte Benutzergruppe sollte aus in Intune registrierten Benutzern bestehen.</span><span class="sxs-lookup"><span data-stu-id="64457-130">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="64457-131">![Abbildung von Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)</span><span class="sxs-lookup"><span data-stu-id="64457-131">![Image of Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)</span></span>

1. <span data-ttu-id="64457-132">Überprüfen Sie im Abschnitt *"Überprüfen + Erstellen",* ob alle eingegebenen Informationen korrekt sind, und wählen Sie dann **"Erstellen"** aus.</span><span class="sxs-lookup"><span data-stu-id="64457-132">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span> <span data-ttu-id="64457-133">In wenigen Momenten sollte die Defender für Endpunkt-App erfolgreich erstellt werden, und in der oberen rechten Ecke der Seite sollte eine Benachrichtigung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="64457-133">In a few moments, the Defender for Endpoint app should be created successfully, and a notification should show up at the top-right corner of the page.</span></span>

1. <span data-ttu-id="64457-134">Wählen Sie auf der angezeigten Seite "App-Informationen" im Abschnitt **"Monitor"** den **Geräteinstallationsstatus** aus, um zu überprüfen, ob die Geräteinstallation erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="64457-134">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="64457-135">![Abbildung von Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)</span><span class="sxs-lookup"><span data-stu-id="64457-135">![Image of Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)</span></span>

## <a name="auto-onboarding-of-vpn-profile-simplified-onboarding"></a><span data-ttu-id="64457-136">Automatisches Onboarding des VPN-Profils (vereinfachtes Onboarding)</span><span class="sxs-lookup"><span data-stu-id="64457-136">Auto-Onboarding of VPN profile (Simplified Onboarding)</span></span>

<span data-ttu-id="64457-137">Administratoren können die automatische Einrichtung des VPN-Profils konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="64457-137">Admins can configure auto-setup of VPN profile.</span></span> <span data-ttu-id="64457-138">Dadurch wird das Defender für Endpunkt-VPN-Profil automatisch eingerichtet, ohne dass der Benutzer dies während des Onboardings tun muss.</span><span class="sxs-lookup"><span data-stu-id="64457-138">This will automatically setup the Defender for Endpoint VPN profile without having the user to do so while onboarding.</span></span> <span data-ttu-id="64457-139">Beachten Sie, dass VPN verwendet wird, um das Webschutzfeature bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="64457-139">Note that VPN is used in order to provide the Web Protection feature.</span></span> <span data-ttu-id="64457-140">Dies ist kein reguläres VPN und ein lokales/selbstschleifendes VPN, das keinen Datenverkehr außerhalb des Geräts aufnimmt.</span><span class="sxs-lookup"><span data-stu-id="64457-140">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

1. <span data-ttu-id="64457-141">Wechseln Sie [im Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431)zu   ->  **"Gerätekonfigurationsprofile**  ->  **erstellen"**.</span><span class="sxs-lookup"><span data-stu-id="64457-141">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Configuration Profiles** -> **Create Profile**.</span></span>
1. <span data-ttu-id="64457-142">Wählen Sie **Plattform** als **iOS/iPadOS** und **Profiltyp** als **VPN** aus.</span><span class="sxs-lookup"><span data-stu-id="64457-142">Choose **Platform** as **iOS/iPadOS** and **Profile type** as **VPN**.</span></span> <span data-ttu-id="64457-143">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="64457-143">Click **Create**.</span></span>
1. <span data-ttu-id="64457-144">Geben Sie einen Namen für das Profil ein, und klicken Sie auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="64457-144">Type a name for the profile and click **Next**.</span></span>
1. <span data-ttu-id="64457-145">Wählen Sie **"Benutzerdefiniertes VPN** für Verbindungstyp" aus, und geben Sie im Abschnitt **"Basis-VPN"** Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="64457-145">Select **Custom VPN** for Connection Type and in the **Base VPN** section, enter the following:</span></span>
    - <span data-ttu-id="64457-146">Verbindungsname = Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="64457-146">Connection Name = Microsoft Defender for Endpoint</span></span>
    - <span data-ttu-id="64457-147">VPN-Serveradresse = 127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="64457-147">VPN server address = 127.0.0.1</span></span>
    - <span data-ttu-id="64457-148">Auth-Methode = "Benutzername und Kennwort"</span><span class="sxs-lookup"><span data-stu-id="64457-148">Auth method = "Username and password"</span></span>
    - <span data-ttu-id="64457-149">Split Tunneling = Deaktivieren</span><span class="sxs-lookup"><span data-stu-id="64457-149">Split Tunneling = Disable</span></span>
    - <span data-ttu-id="64457-150">VPN-ID = com.microsoft.scmx</span><span class="sxs-lookup"><span data-stu-id="64457-150">VPN identifier = com.microsoft.scmx</span></span>
    - <span data-ttu-id="64457-151">Geben Sie in den Schlüssel-Wert-Paaren das **Schlüssel-AutoOnboard** ein, und legen Sie den Wert auf **"True"** fest.</span><span class="sxs-lookup"><span data-stu-id="64457-151">In the key-value pairs, enter the key **AutoOnboard** and set the value to **True**.</span></span>
    - <span data-ttu-id="64457-152">Typ des automatischen VPN = On-Demand-VPN</span><span class="sxs-lookup"><span data-stu-id="64457-152">Type of Automatic VPN = On-demand VPN</span></span>
    - <span data-ttu-id="64457-153">Klicken Sie auf **"Regeln** bei **Bedarf hinzufügen",** und wählen **Sie "Ich möchte folgendermaßen vorgehen = VPN einrichten"** aus, **ich möchte dies auf = alle Domänen beschränken.**</span><span class="sxs-lookup"><span data-stu-id="64457-153">Click **Add** for **On Demand Rules** and select **I want to do the following = Establish VPN**, **I want to restrict to = All domains**.</span></span>

    ![Screenshot der VPN-Profilkonfiguration](images/ios-deploy-8.png)

1. <span data-ttu-id="64457-155">Klicken Sie auf "Weiter", und weisen Sie das Profil den Zielbenutzern zu.</span><span class="sxs-lookup"><span data-stu-id="64457-155">Click Next and assign the profile to targeted users.</span></span>
1. <span data-ttu-id="64457-156">Überprüfen Sie im Abschnitt *"Überprüfen + Erstellen",* ob alle eingegebenen Informationen korrekt sind, und wählen Sie dann **"Erstellen"** aus.</span><span class="sxs-lookup"><span data-stu-id="64457-156">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="64457-157">Abschließen des Onboardings und Überprüfen des Status</span><span class="sxs-lookup"><span data-stu-id="64457-157">Complete onboarding and check status</span></span>

1. <span data-ttu-id="64457-158">Sobald Defender für Endpunkt unter iOS auf dem Gerät installiert wurde, wird das App-Symbol angezeigt.</span><span class="sxs-lookup"><span data-stu-id="64457-158">Once Defender for Endpoint on iOS has been installed on the device, you  will see the app icon.</span></span>

    ![Screenshot einer automatisch generierten Smartphone-Beschreibung](images/41627a709700c324849bf7e13510c516.png)

2. <span data-ttu-id="64457-160">Tippen Sie auf das Symbol der Defender für Endpunkt-App (MSDefender), und befolgen Sie die Anweisungen auf dem Bildschirm, um die Integrationsschritte abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="64457-160">Tap the Defender for Endpoint app icon (MSDefender) and follow the on-screen instructions to complete the onboarding steps.</span></span> <span data-ttu-id="64457-161">Die Details umfassen die Akzeptanz von iOS-Berechtigungen durch Endbenutzer, die von Defender für Endpunkt unter iOS benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="64457-161">The details include end-user acceptance of iOS permissions required by Defender for Endpoint on iOS.</span></span>

3. <span data-ttu-id="64457-162">Nach erfolgreichem Onboarding wird das Gerät in der Liste "Geräte" in Microsoft Defender Security Center angezeigt.</span><span class="sxs-lookup"><span data-stu-id="64457-162">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="64457-163">![Screenshot einer automatisch generierten Mobiltelefonbeschreibung](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span><span class="sxs-lookup"><span data-stu-id="64457-163">![A screenshot of a cell phone Description automatically generated](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span></span>

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a><span data-ttu-id="64457-164">Konfigurieren von Microsoft Defender für Endpunkt für den überwachten Modus</span><span class="sxs-lookup"><span data-stu-id="64457-164">Configure Microsoft Defender for Endpoint for Supervised Mode</span></span>

<span data-ttu-id="64457-165">Die Microsoft Defender für Endpunkt unter iOS-App verfügt aufgrund der erweiterten Verwaltungsfunktionen der Plattform auf diesen Gerätetypen über spezielle Fähigkeiten auf überwachten iOS/iPadOS-Geräten.</span><span class="sxs-lookup"><span data-stu-id="64457-165">The Microsoft Defender for Endpoint on iOS app has specialized ability on supervised iOS/iPadOS devices, given the increased management capabilities provided by the platform on these types of devices.</span></span> <span data-ttu-id="64457-166">Um diese Funktionen nutzen zu können, muss die Defender für Endpunkt-App wissen, ob sich ein Gerät im überwachten Modus befindet.</span><span class="sxs-lookup"><span data-stu-id="64457-166">To take advantage of these capabilities, the Defender for Endpoint app needs to know if a device is in Supervised Mode.</span></span>

### <a name="configure-supervised-mode-via-intune"></a><span data-ttu-id="64457-167">Konfigurieren des überwachten Modus über Intune</span><span class="sxs-lookup"><span data-stu-id="64457-167">Configure Supervised Mode via Intune</span></span>

<span data-ttu-id="64457-168">Mit Intune können Sie die Defender für iOS-App über eine App-Konfigurationsrichtlinie konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="64457-168">Intune allows you to configure the Defender for iOS app through an App Configuration policy.</span></span>

   > [!NOTE]
   > <span data-ttu-id="64457-169">Diese App-Konfigurationsrichtlinie für überwachte Geräte gilt nur für verwaltete Geräte und sollte als bewährte Methode für alle verwalteten iOS-Geräte vorgesehen sein.</span><span class="sxs-lookup"><span data-stu-id="64457-169">This app configuration policy for supervised devices is applicable only to managed devices and should be targeted for all managed iOS devices as a best practice.</span></span>

1. <span data-ttu-id="64457-170">Melden Sie sich beim [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431) an, und wechseln Sie zu **App-Konfigurationsrichtlinien**  >    >  **hinzufügen.**</span><span class="sxs-lookup"><span data-stu-id="64457-170">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Apps** > **App configuration policies** > **Add**.</span></span> <span data-ttu-id="64457-171">Klicken Sie auf **verwaltete Geräte.**</span><span class="sxs-lookup"><span data-stu-id="64457-171">Click on **Managed devices**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="64457-172">![Abbildung von Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)</span><span class="sxs-lookup"><span data-stu-id="64457-172">![Image of Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)</span></span>

1. <span data-ttu-id="64457-173">Geben Sie auf der Seite *"App-Konfigurationsrichtlinie erstellen"* die folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="64457-173">In the *Create app configuration policy* page, provide the following information:</span></span>
    - <span data-ttu-id="64457-174">Policy Name</span><span class="sxs-lookup"><span data-stu-id="64457-174">Policy Name</span></span>
    - <span data-ttu-id="64457-175">Plattform: Auswählen von iOS/iPadOS</span><span class="sxs-lookup"><span data-stu-id="64457-175">Platform: Select iOS/iPadOS</span></span>
    - <span data-ttu-id="64457-176">Ziel-App: Microsoft **Defender-Endpunkt** aus der Liste auswählen</span><span class="sxs-lookup"><span data-stu-id="64457-176">Targeted app: Select **Microsoft Defender Endpoint** from the list</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="64457-177">![Abbildung von Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)</span><span class="sxs-lookup"><span data-stu-id="64457-177">![Image of Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)</span></span>

1. <span data-ttu-id="64457-178">Wählen Sie im nächsten Bildschirm **Konfigurations-Designer** als Format verwenden aus.</span><span class="sxs-lookup"><span data-stu-id="64457-178">In the next screen, select **Use configuration designer** as the format.</span></span> <span data-ttu-id="64457-179">Geben Sie die folgende Eigenschaft an:</span><span class="sxs-lookup"><span data-stu-id="64457-179">Specify the following property:</span></span>
    - <span data-ttu-id="64457-180">Konfigurationsschlüssel: issupervised</span><span class="sxs-lookup"><span data-stu-id="64457-180">Configuration Key: issupervised</span></span>
    - <span data-ttu-id="64457-181">Werttyp: Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="64457-181">Value type: String</span></span>
    - <span data-ttu-id="64457-182">Konfigurationswert: {{issupervised}}</span><span class="sxs-lookup"><span data-stu-id="64457-182">Configuration Value: {{issupervised}}</span></span>
    
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="64457-183">![Abbildung von Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span><span class="sxs-lookup"><span data-stu-id="64457-183">![Image of Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span></span>

1. <span data-ttu-id="64457-184">Klicken Sie auf **"Weiter",** um die Seite **"Bereichstags"** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="64457-184">Click **Next** to open the **Scope tags** page.</span></span> <span data-ttu-id="64457-185">Bereichstags sind optional.</span><span class="sxs-lookup"><span data-stu-id="64457-185">Scope tags are optional.</span></span> <span data-ttu-id="64457-186">Klicken Sie auf **Weiter**, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="64457-186">Click **Next** to continue.</span></span>

1. <span data-ttu-id="64457-187">Wählen Sie auf der Seite **"Aufgaben"** die Gruppen aus, die dieses Profil erhalten.</span><span class="sxs-lookup"><span data-stu-id="64457-187">On the **Assignments** page, select the groups that will receive this profile.</span></span> <span data-ttu-id="64457-188">Für dieses Szenario empfiehlt es sich, alle Geräte als Ziel zu **verwenden.**</span><span class="sxs-lookup"><span data-stu-id="64457-188">For this scenario, it is best practice to target **All Devices**.</span></span> <span data-ttu-id="64457-189">Weitere Informationen zum Zuweisen von Profilen finden Sie unter [Zuweisen von Benutzer- und Geräteprofilen.](/mem/intune/configuration/device-profile-assign)</span><span class="sxs-lookup"><span data-stu-id="64457-189">For more information on assigning profiles, see [Assign user and device profiles](/mem/intune/configuration/device-profile-assign).</span></span>

   <span data-ttu-id="64457-190">Bei der Bereitstellung in Benutzergruppen muss sich ein Benutzer bei einem Gerät anmelden, bevor die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="64457-190">When deploying to user groups, a user must sign in to a device before the policy applies.</span></span>

   <span data-ttu-id="64457-191">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="64457-191">Click **Next**.</span></span>

1. <span data-ttu-id="64457-192">Wenn Sie fertig sind, wählen Sie auf der Seite **"Überprüfen + Erstellen"** die Option **"Erstellen"** aus.</span><span class="sxs-lookup"><span data-stu-id="64457-192">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="64457-193">Das neue Profil wird in der Liste der Konfigurationsprofile angezeigt.</span><span class="sxs-lookup"><span data-stu-id="64457-193">The new profile is displayed in the list of configuration profiles.</span></span>

1. <span data-ttu-id="64457-194">Als Nächstes können Sie für erweiterte Antiphishingfunktionen ein benutzerdefiniertes Profil auf den überwachten iOS-Geräten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="64457-194">Next, for enhanced Anti-phishing capabilities, you can deploy a custom profile on the supervised iOS devices.</span></span> <span data-ttu-id="64457-195">Führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="64457-195">Follow the steps below:</span></span>
    - <span data-ttu-id="64457-196">Laden Sie das Konfigurationsprofil von [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span><span class="sxs-lookup"><span data-stu-id="64457-196">Download the config profile from [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span></span>
    - <span data-ttu-id="64457-197">Navigieren Sie zu  ->  **iOS-/iPadOS-Konfigurationsprofilen**  ->  **für**  ->  **Geräte– Profil erstellen**</span><span class="sxs-lookup"><span data-stu-id="64457-197">Navigate to **Devices** -> **iOS/iPadOS** -> **Configuration profiles** -> **Create Profile**</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="64457-198">![Abbildung von Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)</span><span class="sxs-lookup"><span data-stu-id="64457-198">![Image of Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)</span></span>

    - <span data-ttu-id="64457-199">Geben Sie einen Namen des Profils an.</span><span class="sxs-lookup"><span data-stu-id="64457-199">Provide a name of the profile.</span></span> <span data-ttu-id="64457-200">Wenn Sie aufgefordert werden, eine Konfigurationsprofildatei zu importieren, wählen Sie die oben heruntergeladene aus.</span><span class="sxs-lookup"><span data-stu-id="64457-200">When prompted to import a Configuration profile file, select the one downloaded above.</span></span>
    - <span data-ttu-id="64457-201">Wählen Sie im Abschnitt **"Zuordnung"** die Gerätegruppe aus, auf die Sie dieses Profil anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="64457-201">In the **Assignment** section, select the device group to which you want to apply this profile.</span></span> <span data-ttu-id="64457-202">Als bewährte Methode sollte dies auf alle verwalteten iOS-Geräte angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="64457-202">As a best practice, this should be applied to all managed iOS devices.</span></span> <span data-ttu-id="64457-203">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="64457-203">Click **Next**.</span></span>
    - <span data-ttu-id="64457-204">Wenn Sie fertig sind, wählen Sie auf der Seite **"Überprüfen + Erstellen"** die Option **"Erstellen"** aus.</span><span class="sxs-lookup"><span data-stu-id="64457-204">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="64457-205">Das neue Profil wird in der Liste der Konfigurationsprofile angezeigt.</span><span class="sxs-lookup"><span data-stu-id="64457-205">The new profile is displayed in the list of configuration profiles.</span></span>

## <a name="next-steps"></a><span data-ttu-id="64457-206">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="64457-206">Next Steps</span></span>

[<span data-ttu-id="64457-207">Konfigurieren von Defender für Endpunkt unter iOS-Features</span><span class="sxs-lookup"><span data-stu-id="64457-207">Configure Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
