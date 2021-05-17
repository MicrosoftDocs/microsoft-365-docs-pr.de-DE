---
title: App-basierte Bereitstellung für Microsoft Defender for Endpoint unter iOS
ms.reviewer: ''
description: Beschreibt die Bereitstellung von Microsoft Defender for Endpoint unter iOS mithilfe einer App
keywords: microsoft, defender, Microsoft Defender for Endpoint, ios, app, installation, deploy, deinstallation, intune
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
ms.openlocfilehash: a3711018034bcabdde10c21b3c968c3e813d0565
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245257"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="c0877-104">Bereitstellen von Microsoft Defender for Endpoint unter iOS</span><span class="sxs-lookup"><span data-stu-id="c0877-104">Deploy Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c0877-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c0877-105">**Applies to:**</span></span>
- [<span data-ttu-id="c0877-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="c0877-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c0877-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c0877-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c0877-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="c0877-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c0877-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="c0877-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="c0877-110">In diesem Thema wird die Bereitstellung von Defender for Endpoint unter iOS auf Intune-Unternehmensportal registrierten Geräten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c0877-110">This topic describes deploying Defender for Endpoint on iOS on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="c0877-111">Weitere Informationen zur Registrierung von Intune-Geräten finden Sie unter [Registrieren von iOS-/iPadOS-Geräten in Intune](https://docs.microsoft.com/mem/intune/enrollment/ios-enroll).</span><span class="sxs-lookup"><span data-stu-id="c0877-111">For more information about Intune device enrollment, see [Enroll iOS/iPadOS devices in Intune](https://docs.microsoft.com/mem/intune/enrollment/ios-enroll).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c0877-112">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="c0877-112">Before you begin</span></span>

- <span data-ttu-id="c0877-113">Stellen Sie sicher, dass Sie Zugriff auf [Microsoft Endpoint Manager Admin Center haben.](https://go.microsoft.com/fwlink/?linkid=2109431)</span><span class="sxs-lookup"><span data-stu-id="c0877-113">Ensure you have access to [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>

- <span data-ttu-id="c0877-114">Stellen Sie sicher, dass die iOS-Registrierung für Ihre Benutzer erfolgt.</span><span class="sxs-lookup"><span data-stu-id="c0877-114">Ensure iOS enrollment is done for your users.</span></span> <span data-ttu-id="c0877-115">Benutzern muss eine Defender for Endpoint-Lizenz zugewiesen sein, um Defender for Endpoint unter iOS verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="c0877-115">Users need to have a Defender for Endpoint license assigned in order to use Defender for Endpoint on iOS.</span></span> <span data-ttu-id="c0877-116">Anweisungen zum [Zuweisen von](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) Lizenzen finden Sie unter Zuweisen von Lizenzen zu Benutzern.</span><span class="sxs-lookup"><span data-stu-id="c0877-116">Refer to [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) for instructions on how to assign licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="c0877-117">Microsoft Defender for Endpoint unter iOS ist jetzt im [Apple App-Store.](https://aka.ms/mdatpiosappstore)</span><span class="sxs-lookup"><span data-stu-id="c0877-117">Microsoft Defender for Endpoint on iOS is now available in the [Apple App Store](https://aka.ms/mdatpiosappstore).</span></span>

## <a name="deployment-steps"></a><span data-ttu-id="c0877-118">Bereitstellungsschritte</span><span class="sxs-lookup"><span data-stu-id="c0877-118">Deployment steps</span></span>

<span data-ttu-id="c0877-119">Bereitstellen von Defender for Endpoint unter iOS über Intune-Unternehmensportal.</span><span class="sxs-lookup"><span data-stu-id="c0877-119">Deploy Defender for Endpoint on iOS via Intune Company Portal.</span></span>

### <a name="add-ios-store-app"></a><span data-ttu-id="c0877-120">Hinzufügen einer iOS-Store-App</span><span class="sxs-lookup"><span data-stu-id="c0877-120">Add iOS store app</span></span>

1. <span data-ttu-id="c0877-121">Wechseln [Sie im Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431)zu **Apps**  ->  **iOS/iPadOS**  ->    ->  **iOS Store-App** hinzufügen, und klicken Sie auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="c0877-121">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Apps** -> **iOS/iPadOS** -> **Add** -> **iOS store app** and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c0877-122">![Abbildung des Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)</span><span class="sxs-lookup"><span data-stu-id="c0877-122">![Image of Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)</span></span>

1. <span data-ttu-id="c0877-123">Klicken Sie auf der Seite App hinzufügen auf App **Store** und geben Sie **Microsoft Defender Endpoint** in die Suchleiste ein.</span><span class="sxs-lookup"><span data-stu-id="c0877-123">On the Add app page, click on **Search the App Store** and type **Microsoft Defender Endpoint** in the search bar.</span></span> <span data-ttu-id="c0877-124">Klicken Sie im Abschnitt Suchergebnisse auf *Microsoft Defender Endpoint,* und klicken Sie auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="c0877-124">In the search results section, click on *Microsoft Defender Endpoint* and click **Select**.</span></span>

1. <span data-ttu-id="c0877-125">Wählen **Sie iOS 11.0 als** Mindestbetriebssystem aus.</span><span class="sxs-lookup"><span data-stu-id="c0877-125">Select **iOS 11.0** as the Minimum operating system.</span></span> <span data-ttu-id="c0877-126">Überprüfen Sie die restlichen Informationen zur App, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c0877-126">Review the rest of information about the app and click **Next**.</span></span>

1. <span data-ttu-id="c0877-127">Wechseln Sie *im Abschnitt Zuweisungen* zum Abschnitt **Erforderlich,** und wählen Sie **Gruppe hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="c0877-127">In the *Assignments* section, go to the **Required** section and select **Add group**.</span></span> <span data-ttu-id="c0877-128">Sie können dann die Benutzergruppen auswählen, für die Sie Defender for Endpoint in der iOS-App verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="c0877-128">You can then choose the user group(s) that you would like to target Defender for Endpoint on iOS app.</span></span> <span data-ttu-id="c0877-129">Klicken **Sie auf Auswählen** und dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c0877-129">Click **Select** and then **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c0877-130">Die ausgewählte Benutzergruppe sollte aus in Intune registrierten Benutzern bestehen.</span><span class="sxs-lookup"><span data-stu-id="c0877-130">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c0877-131">![Abbildung des Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)</span><span class="sxs-lookup"><span data-stu-id="c0877-131">![Image of Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)</span></span>

1. <span data-ttu-id="c0877-132">Überprüfen Sie *im Abschnitt Überprüfen +* Erstellen, ob alle eingegebenen Informationen korrekt sind, und wählen Sie dann Erstellen **aus.**</span><span class="sxs-lookup"><span data-stu-id="c0877-132">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span> <span data-ttu-id="c0877-133">In wenigen Momenten sollte die Defender for Endpoint-App erfolgreich erstellt werden, und in der oberen rechten Ecke der Seite sollte eine Benachrichtigung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c0877-133">In a few moments, the Defender for Endpoint app should be created successfully, and a notification should show up at the top-right corner of the page.</span></span>

1. <span data-ttu-id="c0877-134">Wählen Sie auf der angezeigten App-Informationsseite  im Abschnitt **Monitor** die Option Geräteinstallationsstatus aus, um sicherzustellen, dass die Geräteinstallation erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="c0877-134">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c0877-135">![Abbildung des Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)</span><span class="sxs-lookup"><span data-stu-id="c0877-135">![Image of Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)</span></span>

## <a name="auto-onboarding-of-vpn-profile-simplified-onboarding"></a><span data-ttu-id="c0877-136">Automatisches Onboarding des VPN-Profils (vereinfachtes Onboarding)</span><span class="sxs-lookup"><span data-stu-id="c0877-136">Auto-Onboarding of VPN profile (Simplified Onboarding)</span></span>

> [!NOTE]
> <span data-ttu-id="c0877-137">Das automatische Onboarding des VPN-Profils befindet sich derzeit in der Vorschau, und die in diesem Abschnitt erwähnten Schritte werden möglicherweise erheblich geändert, bevor es kommerziell veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="c0877-137">Auto-onboarding of VPN profile is currently in preview and the steps mentioned in this section may be substantially modified before it's commercially released.</span></span>

<span data-ttu-id="c0877-138">Administratoren können die automatische Einrichtung des VPN-Profils konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c0877-138">Admins can configure auto-setup of VPN profile.</span></span> <span data-ttu-id="c0877-139">Dadurch wird das Defender for Endpoint-VPN-Profil automatisch eingerichtet, ohne dass der Benutzer dies beim Onboarding tun muss.</span><span class="sxs-lookup"><span data-stu-id="c0877-139">This will automatically setup the Defender for Endpoint VPN profile without having the user to do so while onboarding.</span></span> <span data-ttu-id="c0877-140">Beachten Sie, dass VPN verwendet wird, um das Web Protection-Feature zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="c0877-140">Note that VPN is used in order to provide the Web Protection feature.</span></span> <span data-ttu-id="c0877-141">Dies ist kein normales VPN und ein lokales VPN mit selbstschleifender Schleife, das keinen Datenverkehr außerhalb des Geräts verwendet.</span><span class="sxs-lookup"><span data-stu-id="c0877-141">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

1. <span data-ttu-id="c0877-142">Wechseln [Sie im Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431)zu   ->  **Gerätekonfigurationsprofile**  ->    ->  **Erstellen einer iOS-Store-App,** und klicken Sie auf **Auswählen.**</span><span class="sxs-lookup"><span data-stu-id="c0877-142">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Configuration Profiles** -> **Create** -> **iOS store app** and click **Select**.</span></span>
1. <span data-ttu-id="c0877-143">Wählen **Sie Plattform** als **iOS/iPadOS-** und **Profiltyp** als **VPN aus.**</span><span class="sxs-lookup"><span data-stu-id="c0877-143">Choose **Platform** as **iOS/iPadOS** and **Profile type** as **VPN**.</span></span> <span data-ttu-id="c0877-144">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="c0877-144">Click **Create**.</span></span>
1. <span data-ttu-id="c0877-145">Geben Sie einen Namen für das Profil ein, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c0877-145">Type a name for the profile and click **Next**.</span></span>
1. <span data-ttu-id="c0877-146">Wählen **Sie Benutzerdefiniertes VPN** für Verbindungstyp aus, und geben Sie im Abschnitt **Basis-VPN** Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="c0877-146">Select **Custom VPN** for Connection Type and in the **Base VPN** section, enter the following:</span></span>
    - <span data-ttu-id="c0877-147">Verbindungsname = Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c0877-147">Connection Name = Microsoft Defender for Endpoint</span></span>
    - <span data-ttu-id="c0877-148">VPN-Serveradresse = 127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="c0877-148">VPN server address = 127.0.0.1</span></span>
    - <span data-ttu-id="c0877-149">Auth-Methode = "Benutzername und Kennwort"</span><span class="sxs-lookup"><span data-stu-id="c0877-149">Auth method = "Username and password"</span></span>
    - <span data-ttu-id="c0877-150">Split Tunneling = Disable</span><span class="sxs-lookup"><span data-stu-id="c0877-150">Split Tunneling = Disable</span></span>
    - <span data-ttu-id="c0877-151">VPN-ID = com.microsoft.scmx</span><span class="sxs-lookup"><span data-stu-id="c0877-151">VPN identifier = com.microsoft.scmx</span></span>
    - <span data-ttu-id="c0877-152">Geben Sie in den Schlüssel-Wert-Paaren den Schlüssel **AutoOnboard ein,** und legen Sie den Wert auf **True .**</span><span class="sxs-lookup"><span data-stu-id="c0877-152">In the key-value pairs, enter the key **AutoOnboard** and set the value to **True**.</span></span>
    - <span data-ttu-id="c0877-153">Typ des automatischen VPN = On-Demand-VPN</span><span class="sxs-lookup"><span data-stu-id="c0877-153">Type of Automatic VPN = On-demand VPN</span></span>
    - <span data-ttu-id="c0877-154">Klicken **Sie auf** Bei Bedarf **regeln** hinzufügen, und wählen Sie I want to do the following = Establish **VPN**, I want to restrict to = All domains **aus.**</span><span class="sxs-lookup"><span data-stu-id="c0877-154">Click **Add** for **On Demand Rules** and select **I want to do the following = Establish VPN**, **I want to restrict to = All domains**.</span></span>

    ![Screenshot der VPN-Profilkonfiguration](images/ios-deploy-8.png)

1. <span data-ttu-id="c0877-156">Klicken Sie auf Weiter, und weisen Sie das Profil gezielten Benutzern zu.</span><span class="sxs-lookup"><span data-stu-id="c0877-156">Click Next and assign the profile to targeted users.</span></span>
1. <span data-ttu-id="c0877-157">Überprüfen Sie *im Abschnitt Überprüfen +* Erstellen, ob alle eingegebenen Informationen korrekt sind, und wählen Sie dann Erstellen **aus.**</span><span class="sxs-lookup"><span data-stu-id="c0877-157">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="c0877-158">Vollständiger Onboarding- und Überprüfungsstatus</span><span class="sxs-lookup"><span data-stu-id="c0877-158">Complete onboarding and check status</span></span>

1. <span data-ttu-id="c0877-159">Sobald Defender for Endpoint unter iOS auf dem Gerät installiert wurde, wird das App-Symbol angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c0877-159">Once Defender for Endpoint on iOS has been installed on the device, you  will see the app icon.</span></span>

    ![Ein Screenshot eines automatisch generierten Smartphones Beschreibung](images/41627a709700c324849bf7e13510c516.png)

2. <span data-ttu-id="c0877-161">Tippen Sie auf das Symbol der Defender for Endpoint-App, und befolgen Sie die Anweisungen auf dem Bildschirm, um die Onboardingschritte zu ausführen.</span><span class="sxs-lookup"><span data-stu-id="c0877-161">Tap the Defender for Endpoint app icon and follow the on-screen instructions to complete the onboarding steps.</span></span> <span data-ttu-id="c0877-162">Die Details umfassen die Endbenutzerakzeptanz der iOS-Berechtigungen, die von Defender for Endpoint unter iOS erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="c0877-162">The details include end-user acceptance of iOS permissions required by Defender for Endpoint on iOS.</span></span>

3. <span data-ttu-id="c0877-163">Nach dem erfolgreichen Onboarding wird das Gerät in der Liste Geräte in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="c0877-163">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c0877-164">![Screenshot eines automatisch generierten Mobiltelefons Beschreibung](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span><span class="sxs-lookup"><span data-stu-id="c0877-164">![A screenshot of a cell phone Description automatically generated](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span></span>

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a><span data-ttu-id="c0877-165">Konfigurieren von Microsoft Defender for Endpoint für den überwachten Modus</span><span class="sxs-lookup"><span data-stu-id="c0877-165">Configure Microsoft Defender for Endpoint for Supervised Mode</span></span>

<span data-ttu-id="c0877-166">Die Microsoft Defender for Endpoint auf iOS-App verfügt über spezielle Funktionen für überwachte iOS/iPadOS-Geräte, da die Plattform auf diesen Gerätetypen mehr Verwaltungsfunktionen bietet.</span><span class="sxs-lookup"><span data-stu-id="c0877-166">The Microsoft Defender for Endpoint on iOS app has specialized ability on supervised iOS/iPadOS devices, given the increased management capabilities provided by the platform on these types of devices.</span></span> <span data-ttu-id="c0877-167">Um diese Funktionen nutzen zu können, muss die Defender for Endpoint-App wissen, ob sich ein Gerät im überwachten Modus befindet.</span><span class="sxs-lookup"><span data-stu-id="c0877-167">To take advantage of these capabilities, the Defender for Endpoint app needs to know if a device is in Supervised Mode.</span></span>

### <a name="configure-supervised-mode-via-intune"></a><span data-ttu-id="c0877-168">Konfigurieren des überwachten Modus über Intune</span><span class="sxs-lookup"><span data-stu-id="c0877-168">Configure Supervised Mode via Intune</span></span>

<span data-ttu-id="c0877-169">Mit Intune können Sie die Defender für iOS-App über eine App-Konfigurationsrichtlinie konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c0877-169">Intune allows you to configure the Defender for iOS app through an App Configuration policy.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c0877-170">Diese App-Konfigurationsrichtlinie für überwachte Geräte gilt nur für verwaltete Geräte und sollte als bewährte Methode für alle verwalteten iOS-Geräte gelten.</span><span class="sxs-lookup"><span data-stu-id="c0877-170">This app configuration policy for supervised devices is applicable only to managed devices and should be targeted for all managed iOS devices as a best practice.</span></span>

1. <span data-ttu-id="c0877-171">Melden Sie sich beim [Microsoft Endpoint Manager Admin Center an,](https://go.microsoft.com/fwlink/?linkid=2109431) und wechseln Sie zu **Apps**  >  **App-Konfigurationsrichtlinien**  >  **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c0877-171">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Apps** > **App configuration policies** > **Add**.</span></span> <span data-ttu-id="c0877-172">Klicken Sie auf **Verwaltete Geräte**.</span><span class="sxs-lookup"><span data-stu-id="c0877-172">Click on **Managed devices**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c0877-173">![Abbildung des Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)</span><span class="sxs-lookup"><span data-stu-id="c0877-173">![Image of Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)</span></span>

1. <span data-ttu-id="c0877-174">Geben Sie *auf der Seite App-Konfigurationsrichtlinie erstellen* die folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="c0877-174">In the *Create app configuration policy* page, provide the following information:</span></span>
    - <span data-ttu-id="c0877-175">Policy Name</span><span class="sxs-lookup"><span data-stu-id="c0877-175">Policy Name</span></span>
    - <span data-ttu-id="c0877-176">Plattform: Auswählen von iOS/iPadOS</span><span class="sxs-lookup"><span data-stu-id="c0877-176">Platform: Select iOS/iPadOS</span></span>
    - <span data-ttu-id="c0877-177">Ziel-App: Wählen **Microsoft Defender ATP** aus der Liste aus</span><span class="sxs-lookup"><span data-stu-id="c0877-177">Targeted app: Select **Microsoft Defender ATP** from the list</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c0877-178">![Abbildung des Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)</span><span class="sxs-lookup"><span data-stu-id="c0877-178">![Image of Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)</span></span>

1. <span data-ttu-id="c0877-179">Wählen Sie im nächsten Bildschirm **Konfigurations-Designer als** Format verwenden aus.</span><span class="sxs-lookup"><span data-stu-id="c0877-179">In the next screen, select **Use configuration designer** as the format.</span></span> <span data-ttu-id="c0877-180">Geben Sie die folgende Eigenschaft an:</span><span class="sxs-lookup"><span data-stu-id="c0877-180">Specify the following property:</span></span>
    - <span data-ttu-id="c0877-181">Konfigurationsschlüssel: issupervised</span><span class="sxs-lookup"><span data-stu-id="c0877-181">Configuration Key: issupervised</span></span>
    - <span data-ttu-id="c0877-182">Werttyp: Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c0877-182">Value type: String</span></span>
    - <span data-ttu-id="c0877-183">Konfigurationswert: {{issupervised}}</span><span class="sxs-lookup"><span data-stu-id="c0877-183">Configuration Value: {{issupervised}}</span></span>
    
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c0877-184">![Abbildung des Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span><span class="sxs-lookup"><span data-stu-id="c0877-184">![Image of Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span></span>

1. <span data-ttu-id="c0877-185">Klicken **Sie auf Weiter,** um die **Seite Bereichstags zu** öffnen.</span><span class="sxs-lookup"><span data-stu-id="c0877-185">Click **Next** to open the **Scope tags** page.</span></span> <span data-ttu-id="c0877-186">Bereichstags sind optional.</span><span class="sxs-lookup"><span data-stu-id="c0877-186">Scope tags are optional.</span></span> <span data-ttu-id="c0877-187">Klicken Sie auf **Weiter**, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="c0877-187">Click **Next** to continue.</span></span>

1. <span data-ttu-id="c0877-188">Wählen Sie **auf** der Seite Zuordnungen die Gruppen aus, die dieses Profil erhalten.</span><span class="sxs-lookup"><span data-stu-id="c0877-188">On the **Assignments** page, select the groups that will receive this profile.</span></span> <span data-ttu-id="c0877-189">Für dieses Szenario ist es bewährte Methode, alle **Geräte als Ziel zu verwenden.**</span><span class="sxs-lookup"><span data-stu-id="c0877-189">For this scenario, it is best practice to target **All Devices**.</span></span> <span data-ttu-id="c0877-190">Weitere Informationen zum Zuweisen von Profilen finden Sie unter [Assign user and device profiles](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span><span class="sxs-lookup"><span data-stu-id="c0877-190">For more information on assigning profiles, see [Assign user and device profiles](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

   <span data-ttu-id="c0877-191">Bei der Bereitstellung in Benutzergruppen muss sich ein Benutzer bei einem Gerät anmelden, bevor die Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="c0877-191">When deploying to user groups, a user must sign in to a device before the policy applies.</span></span>

   <span data-ttu-id="c0877-192">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c0877-192">Click **Next**.</span></span>

1. <span data-ttu-id="c0877-193">Wählen Sie auf der Seite Überprüfen **+** Erstellen die Option Erstellen aus, wenn Sie **fertig sind.**</span><span class="sxs-lookup"><span data-stu-id="c0877-193">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="c0877-194">Das neue Profil wird in der Liste der Konfigurationsprofile angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c0877-194">The new profile is displayed in the list of configuration profiles.</span></span>

1. <span data-ttu-id="c0877-195">Als Nächstes können Sie für erweiterte Antiphishingfunktionen ein benutzerdefiniertes Profil auf den überwachten iOS-Geräten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c0877-195">Next, for enhanced Anti-phishing capabilities, you can deploy a custom profile on the supervised iOS devices.</span></span> <span data-ttu-id="c0877-196">Führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="c0877-196">Follow the steps below:</span></span>
    - <span data-ttu-id="c0877-197">Laden Sie das Konfigurationsprofil von herunter. [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span><span class="sxs-lookup"><span data-stu-id="c0877-197">Download the config profile from [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span></span>
    - <span data-ttu-id="c0877-198">Navigieren Sie **zu**  ->  **Geräte iOS/iPadOS**  ->  **Konfigurationsprofile**  ->  **Profil erstellen**</span><span class="sxs-lookup"><span data-stu-id="c0877-198">Navigate to **Devices** -> **iOS/iPadOS** -> **Configuration profiles** -> **Create Profile**</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c0877-199">![Abbildung des Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)</span><span class="sxs-lookup"><span data-stu-id="c0877-199">![Image of Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)</span></span>

    - <span data-ttu-id="c0877-200">Geben Sie einen Namen des Profils an.</span><span class="sxs-lookup"><span data-stu-id="c0877-200">Provide a name of the profile.</span></span> <span data-ttu-id="c0877-201">Wenn Sie aufgefordert werden, eine Konfigurationsprofildatei zu importieren, wählen Sie die oben heruntergeladene aus.</span><span class="sxs-lookup"><span data-stu-id="c0877-201">When prompted to import a Configuration profile file, select the one downloaded above.</span></span>
    - <span data-ttu-id="c0877-202">Wählen Sie **im Abschnitt Zuordnung** die Gerätegruppe aus, auf die Sie dieses Profil anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="c0877-202">In the **Assignment** section, select the device group to which you want to apply this profile.</span></span> <span data-ttu-id="c0877-203">Dies sollte als bewährte Methode auf alle verwalteten iOS-Geräte angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="c0877-203">As a best practice, this should be applied to all managed iOS devices.</span></span> <span data-ttu-id="c0877-204">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c0877-204">Click **Next**.</span></span>
    - <span data-ttu-id="c0877-205">Wählen Sie auf der Seite Überprüfen **+** Erstellen die Option Erstellen aus, wenn Sie **fertig sind.**</span><span class="sxs-lookup"><span data-stu-id="c0877-205">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="c0877-206">Das neue Profil wird in der Liste der Konfigurationsprofile angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c0877-206">The new profile is displayed in the list of configuration profiles.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c0877-207">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="c0877-207">Next Steps</span></span>

[<span data-ttu-id="c0877-208">Konfigurieren von Defender for Endpoint unter iOS-Features</span><span class="sxs-lookup"><span data-stu-id="c0877-208">Configure Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
