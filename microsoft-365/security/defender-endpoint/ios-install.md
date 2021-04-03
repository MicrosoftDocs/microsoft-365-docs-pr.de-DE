---
title: App-basierte Bereitstellung für Microsoft Defender ATP für iOS
ms.reviewer: ''
description: Beschreibt die Bereitstellung von Microsoft Defender ATP für iOS mithilfe einer App
keywords: microsoft, defender, atp, ios, app, installation, deploy, deinstallation, intune
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c076a64b1e35978f09999b288b6849580df24972
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579698"
---
# <a name="deploy-microsoft-defender-for-endpoint-for-ios"></a><span data-ttu-id="d51b5-104">Bereitstellen von Microsoft Defender for Endpoint für iOS</span><span class="sxs-lookup"><span data-stu-id="d51b5-104">Deploy Microsoft Defender for Endpoint for iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d51b5-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="d51b5-105">**Applies to:**</span></span>
- [<span data-ttu-id="d51b5-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="d51b5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d51b5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d51b5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d51b5-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="d51b5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d51b5-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="d51b5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="d51b5-110">In diesem Thema wird die Bereitstellung von Defender for Endpoint für iOS auf registrierten Geräten des Intune-Unternehmensportals beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d51b5-110">This topic describes deploying Defender for Endpoint for iOS on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="d51b5-111">Weitere Informationen zur Registrierung von Intune-Geräten finden Sie unter [Registrieren von iOS-/iPadOS-Geräten in Intune](https://docs.microsoft.com/mem/intune/enrollment/ios-enroll).</span><span class="sxs-lookup"><span data-stu-id="d51b5-111">For more information about Intune device enrollment, see [Enroll iOS/iPadOS devices in Intune](https://docs.microsoft.com/mem/intune/enrollment/ios-enroll).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d51b5-112">Bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="d51b5-112">Before you begin</span></span>

- <span data-ttu-id="d51b5-113">Stellen Sie sicher, dass Sie Zugriff auf [Microsoft Endpoint Manager Admin Center haben.](https://go.microsoft.com/fwlink/?linkid=2109431)</span><span class="sxs-lookup"><span data-stu-id="d51b5-113">Ensure you have access to [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>

- <span data-ttu-id="d51b5-114">Stellen Sie sicher, dass die iOS-Registrierung für Ihre Benutzer erfolgt.</span><span class="sxs-lookup"><span data-stu-id="d51b5-114">Ensure iOS enrollment is done for your users.</span></span> <span data-ttu-id="d51b5-115">Benutzern muss eine Defender for Endpoint-Lizenz zugewiesen sein, um Defender for Endpoint für iOS verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="d51b5-115">Users need to have a Defender for Endpoint license assigned in order to use Defender for Endpoint for iOS.</span></span> <span data-ttu-id="d51b5-116">Anweisungen zum [Zuweisen von](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) Lizenzen finden Sie unter Zuweisen von Lizenzen zu Benutzern.</span><span class="sxs-lookup"><span data-stu-id="d51b5-116">Refer to [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) for instructions on how to assign licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="d51b5-117">Microsoft Defender ATP (Microsoft Defender for Endpoint) für iOS ist jetzt im [Apple App Store verfügbar.](https://aka.ms/mdatpiosappstore)</span><span class="sxs-lookup"><span data-stu-id="d51b5-117">Microsoft Defender ATP (Microsoft Defender for Endpoint) for iOS is now available in the [Apple App Store](https://aka.ms/mdatpiosappstore).</span></span>

## <a name="deployment-steps"></a><span data-ttu-id="d51b5-118">Bereitstellungsschritte</span><span class="sxs-lookup"><span data-stu-id="d51b5-118">Deployment steps</span></span>

<span data-ttu-id="d51b5-119">Bereitstellen von Defender for Endpoint für iOS über das Intune-Unternehmensportal.</span><span class="sxs-lookup"><span data-stu-id="d51b5-119">Deploy Defender for Endpoint for iOS via Intune Company Portal.</span></span>

### <a name="add-ios-store-app"></a><span data-ttu-id="d51b5-120">Hinzufügen einer iOS-Store-App</span><span class="sxs-lookup"><span data-stu-id="d51b5-120">Add iOS store app</span></span>

1. <span data-ttu-id="d51b5-121">Wechseln [Sie im Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431)zu **Apps**  ->  **iOS/iPadOS**  ->    ->  **iOS Store-App** hinzufügen, und klicken Sie auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="d51b5-121">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Apps** -> **iOS/iPadOS** -> **Add** -> **iOS store app** and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d51b5-122">![Abbildung von Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)</span><span class="sxs-lookup"><span data-stu-id="d51b5-122">![Image of Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)</span></span>

1. <span data-ttu-id="d51b5-123">Klicken Sie auf der Seite App hinzufügen auf **Den App Store durchsuchen,** und geben Sie **Microsoft Defender Endpoint** in die Suchleiste ein.</span><span class="sxs-lookup"><span data-stu-id="d51b5-123">On the Add app page, click on **Search the App Store** and type **Microsoft Defender Endpoint** in the search bar.</span></span> <span data-ttu-id="d51b5-124">Klicken Sie im Abschnitt Suchergebnisse auf *Microsoft Defender Endpoint,* und klicken Sie auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="d51b5-124">In the search results section, click on *Microsoft Defender Endpoint* and click **Select**.</span></span>

1. <span data-ttu-id="d51b5-125">Wählen **Sie iOS 11.0 als** Mindestbetriebssystem aus.</span><span class="sxs-lookup"><span data-stu-id="d51b5-125">Select **iOS 11.0** as the Minimum operating system.</span></span> <span data-ttu-id="d51b5-126">Überprüfen Sie die restlichen Informationen zur App, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d51b5-126">Review the rest of information about the app and click **Next**.</span></span>

1. <span data-ttu-id="d51b5-127">Wechseln Sie *im Abschnitt Zuweisungen* zum Abschnitt **Erforderlich,** und wählen Sie **Gruppe hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="d51b5-127">In the *Assignments* section, go to the **Required** section and select **Add group**.</span></span> <span data-ttu-id="d51b5-128">Sie können dann die Benutzergruppen auswählen, für die Sie Defender for Endpoint für iOS-App verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="d51b5-128">You can then choose the user group(s) that you would like to target Defender for Endpoint for iOS app.</span></span> <span data-ttu-id="d51b5-129">Klicken **Sie auf Auswählen** und dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d51b5-129">Click **Select** and then **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d51b5-130">Die ausgewählte Benutzergruppe sollte aus in Intune registrierten Benutzern bestehen.</span><span class="sxs-lookup"><span data-stu-id="d51b5-130">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d51b5-131">![Abbildung von Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)</span><span class="sxs-lookup"><span data-stu-id="d51b5-131">![Image of Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)</span></span>

1. <span data-ttu-id="d51b5-132">Überprüfen Sie *im Abschnitt Überprüfen +* Erstellen, ob alle eingegebenen Informationen korrekt sind, und wählen Sie dann Erstellen **aus.**</span><span class="sxs-lookup"><span data-stu-id="d51b5-132">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span> <span data-ttu-id="d51b5-133">In wenigen Momenten sollte die Defender for Endpoint-App erfolgreich erstellt werden, und in der oberen rechten Ecke der Seite sollte eine Benachrichtigung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d51b5-133">In a few moments, the Defender for Endpoint app should be created successfully, and a notification should show up at the top-right corner of the page.</span></span>

1. <span data-ttu-id="d51b5-134">Wählen Sie auf der angezeigten App-Informationsseite  im Abschnitt **Monitor** die Option Geräteinstallationsstatus aus, um sicherzustellen, dass die Geräteinstallation erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="d51b5-134">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d51b5-135">![Abbildung des Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)</span><span class="sxs-lookup"><span data-stu-id="d51b5-135">![Image of Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)</span></span>

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="d51b5-136">Vollständiger Onboarding- und Überprüfungsstatus</span><span class="sxs-lookup"><span data-stu-id="d51b5-136">Complete onboarding and check status</span></span>

1. <span data-ttu-id="d51b5-137">Sobald Defender for Endpoint für iOS auf dem Gerät installiert wurde, wird das App-Symbol angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d51b5-137">Once Defender for Endpoint for iOS has been installed on the device, you  will see the app icon.</span></span>

    ![Ein Screenshot eines automatisch generierten Smartphones Beschreibung](images/41627a709700c324849bf7e13510c516.png)

2. <span data-ttu-id="d51b5-139">Tippen Sie auf das Symbol der Defender for Endpoint-App, und befolgen Sie die Anweisungen auf dem Bildschirm, um die Onboardingschritte zu ausführen.</span><span class="sxs-lookup"><span data-stu-id="d51b5-139">Tap the Defender for Endpoint app icon and follow the on-screen instructions to complete the onboarding steps.</span></span> <span data-ttu-id="d51b5-140">Die Details umfassen die Endbenutzerakzeptanz der iOS-Berechtigungen, die von Defender for Endpoint für iOS erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="d51b5-140">The details include end-user acceptance of iOS permissions required by Defender for Endpoint for iOS.</span></span>

3. <span data-ttu-id="d51b5-141">Nach dem erfolgreichen Onboarding wird das Gerät in der Liste Geräte im Microsoft Defender Security Center angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d51b5-141">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d51b5-142">![Screenshot eines automatisch generierten Mobiltelefons Beschreibung](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span><span class="sxs-lookup"><span data-stu-id="d51b5-142">![A screenshot of a cell phone Description automatically generated](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span></span>

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a><span data-ttu-id="d51b5-143">Konfigurieren von Microsoft Defender for Endpoint für den überwachten Modus</span><span class="sxs-lookup"><span data-stu-id="d51b5-143">Configure Microsoft Defender for Endpoint for Supervised Mode</span></span>

<span data-ttu-id="d51b5-144">Die Microsoft Defender for Endpoint für iOS-App verfügt über spezielle Funktionen für überwachte iOS/iPadOS-Geräte, da die Plattform auf diesen Gerätetypen mehr Verwaltungsfunktionen bietet.</span><span class="sxs-lookup"><span data-stu-id="d51b5-144">The Microsoft Defender for Endpoint for iOS app has specialized ability on supervised iOS/iPadOS devices, given the increased management capabilities provided by the platform on these types of devices.</span></span> <span data-ttu-id="d51b5-145">Um diese Funktionen nutzen zu können, muss die Defender for Endpoint-App wissen, ob sich ein Gerät im überwachten Modus befindet.</span><span class="sxs-lookup"><span data-stu-id="d51b5-145">To take advantage of these capabilities, the Defender for Endpoint app needs to know if a device is in Supervised Mode.</span></span>

### <a name="configure-supervised-mode-via-intune"></a><span data-ttu-id="d51b5-146">Konfigurieren des überwachten Modus über Intune</span><span class="sxs-lookup"><span data-stu-id="d51b5-146">Configure Supervised Mode via Intune</span></span>

<span data-ttu-id="d51b5-147">Mit Intune können Sie die Defender für iOS-App über eine App-Konfigurationsrichtlinie konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d51b5-147">Intune allows you to configure the Defender for iOS app through an App Configuration policy.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d51b5-148">Diese App-Konfigurationsrichtlinie für überwachte Geräte gilt nur für verwaltete Geräte und sollte als bewährte Methode für alle verwalteten iOS-Geräte gelten.</span><span class="sxs-lookup"><span data-stu-id="d51b5-148">This app configuration policy for supervised devices is applicable only to managed devices and should be targeted for all managed iOS devices as a best practice.</span></span>

1. <span data-ttu-id="d51b5-149">Melden Sie sich beim [Microsoft Endpoint Manager Admin Center an,](https://go.microsoft.com/fwlink/?linkid=2109431) und wechseln Sie zu **Apps**  >  **App-Konfigurationsrichtlinien**  >  **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d51b5-149">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Apps** > **App configuration policies** > **Add**.</span></span> <span data-ttu-id="d51b5-150">Klicken Sie auf **Verwaltete Geräte**.</span><span class="sxs-lookup"><span data-stu-id="d51b5-150">Click on **Managed devices**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d51b5-151">![Abbildung von Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)</span><span class="sxs-lookup"><span data-stu-id="d51b5-151">![Image of Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)</span></span>

1. <span data-ttu-id="d51b5-152">Geben Sie *auf der Seite App-Konfigurationsrichtlinie erstellen* die folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="d51b5-152">In the *Create app configuration policy* page, provide the following information:</span></span>
    - <span data-ttu-id="d51b5-153">Policy Name</span><span class="sxs-lookup"><span data-stu-id="d51b5-153">Policy Name</span></span>
    - <span data-ttu-id="d51b5-154">Plattform: Auswählen von iOS/iPadOS</span><span class="sxs-lookup"><span data-stu-id="d51b5-154">Platform: Select iOS/iPadOS</span></span>
    - <span data-ttu-id="d51b5-155">Ziel-App: Wählen **Sie Microsoft Defender ATP** aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="d51b5-155">Targeted app: Select **Microsoft Defender ATP** from the list</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d51b5-156">![Abbildung von Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)</span><span class="sxs-lookup"><span data-stu-id="d51b5-156">![Image of Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)</span></span>

1. <span data-ttu-id="d51b5-157">Wählen Sie im nächsten Bildschirm **Konfigurations-Designer als** Format verwenden aus.</span><span class="sxs-lookup"><span data-stu-id="d51b5-157">In the next screen, select **Use configuration designer** as the format.</span></span> <span data-ttu-id="d51b5-158">Geben Sie die folgende Eigenschaft an:</span><span class="sxs-lookup"><span data-stu-id="d51b5-158">Specify the following property:</span></span>
    - <span data-ttu-id="d51b5-159">Konfigurationsschlüssel: issupervised</span><span class="sxs-lookup"><span data-stu-id="d51b5-159">Configuration Key: issupervised</span></span>
    - <span data-ttu-id="d51b5-160">Werttyp: Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d51b5-160">Value type: String</span></span>
    - <span data-ttu-id="d51b5-161">Konfigurationswert: {{issupervised}}</span><span class="sxs-lookup"><span data-stu-id="d51b5-161">Configuration Value: {{issupervised}}</span></span>
    
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d51b5-162">![Abbildung von Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span><span class="sxs-lookup"><span data-stu-id="d51b5-162">![Image of Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span></span>

1. <span data-ttu-id="d51b5-163">Klicken **Sie auf Weiter,** um die **Seite Bereichstags zu** öffnen.</span><span class="sxs-lookup"><span data-stu-id="d51b5-163">Click **Next** to open the **Scope tags** page.</span></span> <span data-ttu-id="d51b5-164">Bereichstags sind optional.</span><span class="sxs-lookup"><span data-stu-id="d51b5-164">Scope tags are optional.</span></span> <span data-ttu-id="d51b5-165">Klicken Sie auf **Weiter**, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="d51b5-165">Click **Next** to continue.</span></span>

1. <span data-ttu-id="d51b5-166">Wählen Sie **auf** der Seite Zuordnungen die Gruppen aus, die dieses Profil erhalten.</span><span class="sxs-lookup"><span data-stu-id="d51b5-166">On the **Assignments** page, select the groups that will receive this profile.</span></span> <span data-ttu-id="d51b5-167">Für dieses Szenario ist es bewährte Methode, alle **Geräte als Ziel zu verwenden.**</span><span class="sxs-lookup"><span data-stu-id="d51b5-167">For this scenario, it is best practice to target **All Devices**.</span></span> <span data-ttu-id="d51b5-168">Weitere Informationen zum Zuweisen von Profilen finden Sie unter [Assign user and device profiles](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span><span class="sxs-lookup"><span data-stu-id="d51b5-168">For more information on assigning profiles, see [Assign user and device profiles](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

   <span data-ttu-id="d51b5-169">Bei der Bereitstellung in Benutzergruppen muss sich ein Benutzer bei einem Gerät anmelden, bevor die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="d51b5-169">When deploying to user groups, a user must sign in to a device before the policy applies.</span></span>

   <span data-ttu-id="d51b5-170">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d51b5-170">Click **Next**.</span></span>

1. <span data-ttu-id="d51b5-171">Wählen Sie auf der Seite Überprüfen **+** Erstellen die Option Erstellen aus, wenn Sie **fertig sind.**</span><span class="sxs-lookup"><span data-stu-id="d51b5-171">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="d51b5-172">Das neue Profil wird in der Liste der Konfigurationsprofile angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d51b5-172">The new profile is displayed in the list of configuration profiles.</span></span>

1. <span data-ttu-id="d51b5-173">Als Nächstes können Sie für erweiterte Antiphishingfunktionen ein benutzerdefiniertes Profil auf den überwachten iOS-Geräten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d51b5-173">Next, for enhanced Anti-phishing capabilities, you can deploy a custom profile on the supervised iOS devices.</span></span> <span data-ttu-id="d51b5-174">Führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="d51b5-174">Follow the steps below:</span></span>
    - <span data-ttu-id="d51b5-175">Laden Sie das Konfigurationsprofil von herunter. [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span><span class="sxs-lookup"><span data-stu-id="d51b5-175">Download the config profile from [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span></span>
    - <span data-ttu-id="d51b5-176">Navigieren Sie **zu**  ->  **Geräte iOS/iPadOS**  ->  **Konfigurationsprofile**  ->  **Profil erstellen**</span><span class="sxs-lookup"><span data-stu-id="d51b5-176">Navigate to **Devices** -> **iOS/iPadOS** -> **Configuration profiles** -> **Create Profile**</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d51b5-177">![Abbildung von Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)</span><span class="sxs-lookup"><span data-stu-id="d51b5-177">![Image of Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)</span></span>

    - <span data-ttu-id="d51b5-178">Geben Sie einen Namen des Profils an.</span><span class="sxs-lookup"><span data-stu-id="d51b5-178">Provide a name of the profile.</span></span> <span data-ttu-id="d51b5-179">Wenn Sie aufgefordert werden, eine Konfigurationsprofildatei zu importieren, wählen Sie die oben heruntergeladene aus.</span><span class="sxs-lookup"><span data-stu-id="d51b5-179">When prompted to import a Configuration profile file, select the one downloaded above.</span></span>
    - <span data-ttu-id="d51b5-180">Wählen Sie **im Abschnitt Zuordnung** die Gerätegruppe aus, auf die Sie dieses Profil anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="d51b5-180">In the **Assignment** section, select the device group to which you want to apply this profile.</span></span> <span data-ttu-id="d51b5-181">Dies sollte als bewährte Methode auf alle verwalteten iOS-Geräte angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="d51b5-181">As a best practice, this should be applied to all managed iOS devices.</span></span> <span data-ttu-id="d51b5-182">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d51b5-182">Click **Next**.</span></span>
    - <span data-ttu-id="d51b5-183">Wählen Sie auf der Seite Überprüfen **+** Erstellen die Option Erstellen aus, wenn Sie **fertig sind.**</span><span class="sxs-lookup"><span data-stu-id="d51b5-183">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="d51b5-184">Das neue Profil wird in der Liste der Konfigurationsprofile angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d51b5-184">The new profile is displayed in the list of configuration profiles.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d51b5-185">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="d51b5-185">Next Steps</span></span>

[<span data-ttu-id="d51b5-186">Konfigurieren von Defender for Endpoint für iOS-Features</span><span class="sxs-lookup"><span data-stu-id="d51b5-186">Configure Defender for Endpoint for iOS features</span></span>](ios-configure-features.md)
