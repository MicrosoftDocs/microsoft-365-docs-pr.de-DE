---
title: Bereitstellen von Microsoft Defender for Endpoint unter Android mit Microsoft Intune
description: Beschreibt die Bereitstellung von Microsoft Defender for Endpoint unter Android mit Microsoft Intune
keywords: microsoft, defender, atp, mde, android, installation, deploy, deinstallation,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 350345acbaadcdd6bc8ef901f03c419a7f8decff
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687721"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-android-with-microsoft-intune"></a><span data-ttu-id="0e070-104">Bereitstellen von Microsoft Defender for Endpoint unter Android mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="0e070-104">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0e070-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="0e070-105">**Applies to:**</span></span>
- [<span data-ttu-id="0e070-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="0e070-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0e070-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0e070-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0e070-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="0e070-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0e070-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="0e070-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="0e070-110">Erfahren Sie, wie Sie Defender for Endpoint für Android auf registrierten Geräten des Intune-Unternehmensportals bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0e070-110">Learn how to deploy Defender for Endpoint for Android on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="0e070-111">Weitere Informationen zur Registrierung von Intune-Geräten finden Sie  [unter Registrieren Ihres Geräts](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal).</span><span class="sxs-lookup"><span data-stu-id="0e070-111">For more information about Intune device enrollment, see  [Enroll your device](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal).</span></span>

> [!NOTE]
> <span data-ttu-id="0e070-112">**Defender for Endpoint für Android ist jetzt auf [Google Play verfügbar.](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**</span><span class="sxs-lookup"><span data-stu-id="0e070-112">**Defender for Endpoint for Android is now available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**</span></span> <br>
> <span data-ttu-id="0e070-113">Sie können von Intune aus eine Verbindung mit Google Play herstellen, um die Defender for Endpoint-App über geräteadministrator- und Android Enterprise-Entrollungsmodi bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="0e070-113">You can connect to Google Play from Intune to deploy Defender for Endpoint app across Device Administrator and Android Enterprise entrollment modes.</span></span>
<span data-ttu-id="0e070-114">Updates für die App werden automatisch über Google Play angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e070-114">Updates to the app are automatic via Google Play.</span></span>

## <a name="deploy-on-device-administrator-enrolled-devices"></a><span data-ttu-id="0e070-115">Bereitstellen auf vom Geräteadministrator registrierten Geräten</span><span class="sxs-lookup"><span data-stu-id="0e070-115">Deploy on Device Administrator enrolled devices</span></span>

<span data-ttu-id="0e070-116">**Bereitstellen von Defender for Endpoint für Android im Intune-Unternehmensportal – Geräteadministrator registrierte Geräte**</span><span class="sxs-lookup"><span data-stu-id="0e070-116">**Deploy Defender for Endpoint for Android on Intune Company Portal - Device Administrator enrolled devices**</span></span>

<span data-ttu-id="0e070-117">Erfahren Sie, wie Sie Defender for Endpoint für Android im Intune-Unternehmensportal – Geräteadministrator registrierte Geräte bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0e070-117">Learn how to deploy Defender for Endpoint for Android on Intune Company Portal - Device Administrator enrolled devices.</span></span> 

### <a name="add-as-android-store-app"></a><span data-ttu-id="0e070-118">Hinzufügen als Android Store-App</span><span class="sxs-lookup"><span data-stu-id="0e070-118">Add as Android store app</span></span>

1. <span data-ttu-id="0e070-119">Wechseln [Sie im Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431) zu **Apps** \> **Android Apps** Android store \> **\> app** hinzufügen, und wählen Sie **Auswählen aus.**</span><span class="sxs-lookup"><span data-stu-id="0e070-119">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) , go to **Apps** \> **Android Apps** \> **Add \> Android store app** and choose **Select**.</span></span>

   ![Abbildung der Microsoft Endpoint Manager Admin Center hinzufügen Android Store-Anwendung](images/mda-addandroidstoreapp.png)

2. <span data-ttu-id="0e070-121">Geben Sie **auf der Seite** App hinzufügen und im Abschnitt *App-Informationen* ein:</span><span class="sxs-lookup"><span data-stu-id="0e070-121">On the **Add app** page and in the *App Information* section enter:</span></span> 

   - <span data-ttu-id="0e070-122">**Name**</span><span class="sxs-lookup"><span data-stu-id="0e070-122">**Name**</span></span> 
   - <span data-ttu-id="0e070-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="0e070-123">**Description**</span></span>
   - <span data-ttu-id="0e070-124">**Publisher** als Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0e070-124">**Publisher** as Microsoft.</span></span>
   - <span data-ttu-id="0e070-125">**App Store-URL** als https://play.google.com/store/apps/details?id=com.microsoft.scmx (Defender for Endpoint-App Google Play Store-URL)</span><span class="sxs-lookup"><span data-stu-id="0e070-125">**App store URL** as https://play.google.com/store/apps/details?id=com.microsoft.scmx (Defender for Endpoint app Google Play Store URL)</span></span> 

   <span data-ttu-id="0e070-126">Andere Felder sind optional.</span><span class="sxs-lookup"><span data-stu-id="0e070-126">Other fields are optional.</span></span> <span data-ttu-id="0e070-127">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="0e070-127">Select **Next**.</span></span>

   ![Abbildung von Microsoft Endpoint Manager Admin Center add app info](images/mda-addappinfo.png)

3. <span data-ttu-id="0e070-129">Wechseln Sie *im Abschnitt Zuweisungen* zum Abschnitt **Erforderlich,** und wählen Sie **Gruppe hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="0e070-129">In the *Assignments* section, go to the **Required** section and select **Add group.**</span></span> <span data-ttu-id="0e070-130">Sie können dann die Benutzergruppen auswählen, für die Sie Defender for Endpoint für Android-App verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="0e070-130">You can then choose the user group(s) that you would like to target Defender for Endpoint for Android app.</span></span> <span data-ttu-id="0e070-131">Wählen **Sie Auswählen** und dann Weiter **aus.**</span><span class="sxs-lookup"><span data-stu-id="0e070-131">Choose **Select** and then **Next**.</span></span>

    >[!NOTE]
    ><span data-ttu-id="0e070-132">Die ausgewählte Benutzergruppe sollte aus in Intune registrierten Benutzern bestehen.</span><span class="sxs-lookup"><span data-stu-id="0e070-132">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]

    > ![Abbildung der ausgewählten Benutzergruppen im Microsoft Endpoint Manager Admin Center](images/363bf30f7d69a94db578e8af0ddd044b.png)

4. <span data-ttu-id="0e070-134">Überprüfen Sie **im Abschnitt Überprüfen+Erstellen,** ob alle eingegebenen Informationen korrekt sind, und wählen Sie dann **Erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="0e070-134">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

    <span data-ttu-id="0e070-135">In wenigen Momenten wurde die Defender for Endpoint-App erfolgreich erstellt, und eine Benachrichtigung wird oben rechts auf der Seite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e070-135">In a few moments, the Defender for Endpoint app would be created successfully, and a notification would show up at the top-right corner of the page.</span></span>

    ![Abbildung der Microsoft Endpoint Manager Admin Center-Benachrichtigung der Defender-Endpunkt-App](images/86cbe56f88bb6e93e9c63303397fc24f.png)

5. <span data-ttu-id="0e070-137">Wählen Sie auf der angezeigten App-Informationsseite  im Abschnitt **Monitor** die Option Geräteinstallationsstatus aus, um sicherzustellen, dass die Geräteinstallation erfolgreich abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="0e070-137">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0e070-138">![Abbildung der Installation von Microsoft Endpoint Manager Admin Center-Geräten](images/513cf5d59eaaef5d2b5bc122715b5844.png)</span><span class="sxs-lookup"><span data-stu-id="0e070-138">![Image of Microsoft Endpoint Manager Admin Center device install](images/513cf5d59eaaef5d2b5bc122715b5844.png)</span></span>

### <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="0e070-139">Vollständiger Onboarding- und Überprüfungsstatus</span><span class="sxs-lookup"><span data-stu-id="0e070-139">Complete onboarding and check status</span></span>

1. <span data-ttu-id="0e070-140">Sobald Defender for Endpoint für Android auf dem Gerät installiert wurde, wird das App-Symbol angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e070-140">Once Defender for Endpoint for Android has been installed on the device, you'll see the app icon.</span></span>

    ![Symbol auf mobilem Gerät](images/7cf9311ad676ec5142002a4d0c2323ca.jpg)

2. <span data-ttu-id="0e070-142">Tippen Sie auf das Microsoft Defender ATP-App-Symbol, und befolgen Sie die Anweisungen auf dem Bildschirm, um das Onboarding der App zu abschließen.</span><span class="sxs-lookup"><span data-stu-id="0e070-142">Tap the Microsoft Defender ATP app icon and follow the on-screen instructions to complete onboarding the app.</span></span> <span data-ttu-id="0e070-143">Die Details umfassen die Endbenutzerakzeptanz der von Defender for Endpoint für Android benötigten Android-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="0e070-143">The details include end-user acceptance of Android permissions required by Defender for Endpoint for Android.</span></span>

3. <span data-ttu-id="0e070-144">Nach dem erfolgreichen Onboarding wird das Gerät in der Liste Geräte im Microsoft Defender Security Center angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e070-144">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    ![Abbildung des Geräts im Defender for Endpoint-Portal](images/9fe378a1dce0f143005c3aa53d8c4f51.png)

## <a name="deploy-on-android-enterprise-enrolled-devices"></a><span data-ttu-id="0e070-146">Bereitstellen auf registrierten Android Enterprise-Geräten</span><span class="sxs-lookup"><span data-stu-id="0e070-146">Deploy on Android Enterprise enrolled devices</span></span>

<span data-ttu-id="0e070-147">Defender for Endpoint für Android unterstützt registrierte Android Enterprise-Geräte.</span><span class="sxs-lookup"><span data-stu-id="0e070-147">Defender for Endpoint for Android supports Android Enterprise enrolled devices.</span></span>

<span data-ttu-id="0e070-148">Weitere Informationen zu den von Intune unterstützten Registrierungsoptionen finden Sie unter [Registrierungsoptionen](https://docs.microsoft.com/mem/intune/enrollment/android-enroll).</span><span class="sxs-lookup"><span data-stu-id="0e070-148">For more information on the enrollment options supported by Intune, see [Enrollment Options](https://docs.microsoft.com/mem/intune/enrollment/android-enroll).</span></span>

<span data-ttu-id="0e070-149">**Zurzeit werden geräteeigene Geräte mit Geschäftsprofil und vollständig verwalteten Geräteregistrierungen im Besitz des Unternehmens für die Bereitstellung unterstützt.**</span><span class="sxs-lookup"><span data-stu-id="0e070-149">**Currently, Personally owned devices with work profile and Corporate-owned fully managed user device enrollments are supported for deployment.**</span></span>

## <a name="add-microsoft-defender-for-endpoint-on-android-as-a-managed-google-play-app"></a><span data-ttu-id="0e070-150">Hinzufügen von Microsoft Defender für Endpoint unter Android als verwaltete Google Play-App</span><span class="sxs-lookup"><span data-stu-id="0e070-150">Add Microsoft Defender for Endpoint on Android as a Managed Google Play app</span></span>

<span data-ttu-id="0e070-151">Führen Sie die folgenden Schritte aus, um Microsoft Defender for Endpoint-App zu Ihrer verwalteten Google Play hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="0e070-151">Follow the steps below to add Microsoft Defender for Endpoint app into your managed Google Play.</span></span>

1. <span data-ttu-id="0e070-152">Wechseln [Sie im Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431) zu Apps **Android** \> **Apps** \> **Add,** und wählen Sie **Verwaltete Google Play-App aus.**</span><span class="sxs-lookup"><span data-stu-id="0e070-152">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) , go to **Apps** \> **Android Apps** \> **Add** and select **Managed Google Play app**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0e070-153">![Abbildung des verwalteten Google Play in Microsoft Endpoint Manager Admin Center](images/579ff59f31f599414cedf63051628b2e.png)</span><span class="sxs-lookup"><span data-stu-id="0e070-153">![Image of Microsoft Endpoint Manager admin center managed google play](images/579ff59f31f599414cedf63051628b2e.png)</span></span>

2. <span data-ttu-id="0e070-154">Wechseln Sie auf der verwalteten Google Play-Seite, die anschließend geladen wird, zum Suchfeld, und suchen Sie **Microsoft Defender.**</span><span class="sxs-lookup"><span data-stu-id="0e070-154">On your managed Google Play page that loads subsequently, go to the search box and lookup **Microsoft Defender.**</span></span> <span data-ttu-id="0e070-155">Ihre Suche sollte die Microsoft Defender for Endpoint-App in Ihrer verwalteten Google Play anzeigen.</span><span class="sxs-lookup"><span data-stu-id="0e070-155">Your search should display the Microsoft Defender for Endpoint app in your Managed Google Play.</span></span> <span data-ttu-id="0e070-156">Klicken Sie im Apps-Suchergebnis auf die Microsoft Defender for Endpoint-App.</span><span class="sxs-lookup"><span data-stu-id="0e070-156">Click on the Microsoft Defender for Endpoint app from the Apps search result.</span></span>

    ![Abbildung der Microsoft Endpoint Manager Admin Center Apps-Suche](images/0f79cb37900b57c3e2bb0effad1c19cb.png)

3. <span data-ttu-id="0e070-158">Auf der Seite App-Beschreibung, die als Nächstes angezeigt wird, sollten Sie app-Details auf Defender for Endpoint anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="0e070-158">In the App description page that comes up next, you should be able to see app details on Defender for Endpoint.</span></span> <span data-ttu-id="0e070-159">Überprüfen Sie die Informationen auf der Seite, und wählen Sie dann **Genehmigen aus.**</span><span class="sxs-lookup"><span data-stu-id="0e070-159">Review the information on the page and then select **Approve**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0e070-160">![Screenshot eines verwalteten Google Play](images/07e6d4119f265037e3b80a20a73b856f.png)</span><span class="sxs-lookup"><span data-stu-id="0e070-160">![A screenshot of a Managed Google Play](images/07e6d4119f265037e3b80a20a73b856f.png)</span></span>

4. <span data-ttu-id="0e070-161">Ihnen werden die Berechtigungen präsentiert, die Defender for Endpoint für die Arbeit erhält.</span><span class="sxs-lookup"><span data-stu-id="0e070-161">You'll be presented with the permissions that Defender for Endpoint obtains for it to work.</span></span> <span data-ttu-id="0e070-162">Überprüfen Sie sie, und wählen Sie dann **Genehmigen aus.**</span><span class="sxs-lookup"><span data-stu-id="0e070-162">Review them and then select **Approve**.</span></span>

    ![Screenshot der Genehmigung der Defender for Endpoint-Vorschau-App](images/206b3d954f06cc58b3466fb7a0bd9f74.png)

5. <span data-ttu-id="0e070-164">Ihnen wird die Seite Genehmigungseinstellungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e070-164">You'll be presented with the Approval settings page.</span></span> <span data-ttu-id="0e070-165">Die Seite bestätigt, dass Sie neue App-Berechtigungen behandeln möchten, die Defender for Endpoint für Android möglicherweise fordert.</span><span class="sxs-lookup"><span data-stu-id="0e070-165">The page confirms your preference to handle new app permissions that Defender for Endpoint for Android might ask.</span></span> <span data-ttu-id="0e070-166">Überprüfen Sie die Auswahlmöglichkeiten, und wählen Sie Ihre bevorzugte Option aus.</span><span class="sxs-lookup"><span data-stu-id="0e070-166">Review the choices and select your preferred option.</span></span> <span data-ttu-id="0e070-167">Wählen Sie **Fertig** aus.</span><span class="sxs-lookup"><span data-stu-id="0e070-167">Select **Done**.</span></span>

    <span data-ttu-id="0e070-168">Standardmäßig wählt verwaltete Google Play die Option *Genehmigt bleiben aus, wenn App neue Berechtigungen anfordert*</span><span class="sxs-lookup"><span data-stu-id="0e070-168">By default, managed Google Play selects *Keep approved when app requests new permissions*</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0e070-169">![Abbildung der Registerkarte "Benachrichtigungen"](images/ffecfdda1c4df14148f1526c22cc0236.png)</span><span class="sxs-lookup"><span data-stu-id="0e070-169">![Image of notifications tab](images/ffecfdda1c4df14148f1526c22cc0236.png)</span></span>

6. <span data-ttu-id="0e070-170">Nachdem die Auswahl für die Berechtigungsbehandlung getroffen wurde, wählen Sie **Synchronisieren** aus, um Microsoft Defender for Endpoint mit Ihrer Apps-Liste zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="0e070-170">After the permissions handling selection is made, select **Sync** to sync Microsoft Defender for Endpoint to your apps list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0e070-171">![Abbildung der Synchronisierungsseite](images/34e6b9a0dae125d085c84593140180ed.png)</span><span class="sxs-lookup"><span data-stu-id="0e070-171">![Image of sync page](images/34e6b9a0dae125d085c84593140180ed.png)</span></span>

7. <span data-ttu-id="0e070-172">Die Synchronisierung wird in wenigen Minuten abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="0e070-172">The sync will complete in a few minutes.</span></span>

    ![Abbildung der Android-App](images/9fc07ffc150171f169dc6e57fe6f1c74.png)

8. <span data-ttu-id="0e070-174">Wählen Sie **die Schaltfläche Aktualisieren** auf dem Bildschirm für Android-Apps aus, und Microsoft Defender ATP sollte in der Liste apps sichtbar sein.</span><span class="sxs-lookup"><span data-stu-id="0e070-174">Select the **Refresh** button in the Android apps screen and Microsoft Defender ATP should be visible in the apps list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0e070-175">![Abbildung der Liste der Android-Apps](images/fa4ac18a6333335db3775630b8e6b353.png)</span><span class="sxs-lookup"><span data-stu-id="0e070-175">![Image of list of Android apps](images/fa4ac18a6333335db3775630b8e6b353.png)</span></span>

9. <span data-ttu-id="0e070-176">Defender for Endpoint unterstützt App-Konfigurationsrichtlinien für verwaltete Geräte über Intune.</span><span class="sxs-lookup"><span data-stu-id="0e070-176">Defender for Endpoint supports App configuration policies for managed devices via Intune.</span></span> <span data-ttu-id="0e070-177">Diese Funktion kann verwendet werden, um anwendbare Android-Berechtigungen automatisch zugranaten, sodass der Endbenutzer diese Berechtigungen nicht akzeptieren muss.</span><span class="sxs-lookup"><span data-stu-id="0e070-177">This capability can be leveraged to autogrant applicable Android permission(s), so the end user does not need to accept these permission(s).</span></span>

    1. <span data-ttu-id="0e070-178">Wechseln Sie **auf** der Seite Apps zu **Richtlinien > App-Konfigurationsrichtlinien > Hinzufügen > verwalteten Geräten**.</span><span class="sxs-lookup"><span data-stu-id="0e070-178">In the **Apps** page, go to **Policy > App configuration policies > Add > Managed devices**.</span></span>

       ![Abbildung der verwalteten Microsoft Endpoint Manager Admin Center-Android-Geräte](images/android-mem.png)

    1. <span data-ttu-id="0e070-180">Geben Sie auf der Seite **App-Konfigurationsrichtlinie erstellen** die folgenden Details ein:</span><span class="sxs-lookup"><span data-stu-id="0e070-180">In the **Create app configuration policy** page, enter the following details:</span></span>
    
        - <span data-ttu-id="0e070-181">Name: Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="0e070-181">Name: Microsoft Defender ATP.</span></span>
        - <span data-ttu-id="0e070-182">Wählen **Sie Android Enterprise** als Plattform aus.</span><span class="sxs-lookup"><span data-stu-id="0e070-182">Choose **Android Enterprise** as platform.</span></span>
        - <span data-ttu-id="0e070-183">Wählen **Sie Arbeitsprofil nur als** Profiltyp aus.</span><span class="sxs-lookup"><span data-stu-id="0e070-183">Choose **Work Profile only** as Profile Type.</span></span>
        - <span data-ttu-id="0e070-184">Klicken **Sie auf App auswählen,** wählen Sie Microsoft Defender **ATP** aus, wählen **Sie OK** und dann Weiter **aus.**</span><span class="sxs-lookup"><span data-stu-id="0e070-184">Click **Select App**, choose **Microsoft Defender ATP**, select **OK** and then **Next**.</span></span>
    
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="0e070-185">![Abbildung der Seite "App-Konfigurationsrichtlinie erstellen"](images/android-create-app.png)</span><span class="sxs-lookup"><span data-stu-id="0e070-185">![Image of create app configuration policy page](images/android-create-app.png)</span></span>

    1. <span data-ttu-id="0e070-186">Wechseln Sie **auf** der Seite Einstellungen zum Abschnitt Berechtigungen, klicken Sie auf Hinzufügen, um die Liste der unterstützten Berechtigungen zu sehen.</span><span class="sxs-lookup"><span data-stu-id="0e070-186">In the **Settings** page, go to the Permissions section click on Add to view the list of supported permissions.</span></span> <span data-ttu-id="0e070-187">Wählen Sie im Abschnitt Berechtigungen hinzufügen die folgenden Berechtigungen aus:</span><span class="sxs-lookup"><span data-stu-id="0e070-187">In the Add Permissions section, select the following permissions:</span></span>

       - <span data-ttu-id="0e070-188">Externer Speicher (Lesen)</span><span class="sxs-lookup"><span data-stu-id="0e070-188">External storage (read)</span></span>
       - <span data-ttu-id="0e070-189">Externer Speicher (Schreiben)</span><span class="sxs-lookup"><span data-stu-id="0e070-189">External storage (write)</span></span>

       <span data-ttu-id="0e070-190">Wählen Sie dann **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="0e070-190">Then select **OK**.</span></span>

       > [!div class="mx-imgBorder"]
      > <span data-ttu-id="0e070-191">![Abbildung der Android-App-Konfigurationsrichtlinie erstellen](images/android-create-app-config.png)</span><span class="sxs-lookup"><span data-stu-id="0e070-191">![Image of android create app configuration policy](images/android-create-app-config.png)</span></span>

    1. <span data-ttu-id="0e070-192">Sie sollten nun sowohl die aufgeführten Berechtigungen als auch jetzt autogrant  sehen, indem Sie autogrant in der Dropdownliste Berechtigungsstatus auswählen und dann **Weiter auswählen.**</span><span class="sxs-lookup"><span data-stu-id="0e070-192">You should now see both the permissions listed and now you can autogrant both by choosing autogrant in the **Permission state** drop-down and then select **Next**.</span></span>

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="0e070-193">![Abbildung der automatischen Android-Erteilung erstellen einer App-Konfigurationsrichtlinie](images/android-auto-grant.png)</span><span class="sxs-lookup"><span data-stu-id="0e070-193">![Image of android auto grant create app configuration policy](images/android-auto-grant.png)</span></span>

    1. <span data-ttu-id="0e070-194">Wählen Sie **auf** der Seite Zuweisungen die Benutzergruppe aus, der diese App-Konfigurationsrichtlinie zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="0e070-194">In the **Assignments** page, select the user group to which this app config policy would be assigned to.</span></span> <span data-ttu-id="0e070-195">Klicken **Sie auf Gruppen auswählen, um** die entsprechende Gruppe ein- und auszuwählen, und wählen Sie dann Weiter **aus.**</span><span class="sxs-lookup"><span data-stu-id="0e070-195">Click **Select groups to include** and selecting the applicable group and then selecting **Next**.</span></span>  <span data-ttu-id="0e070-196">Die hier ausgewählte Gruppe ist in der Regel dieselbe Gruppe, der Sie Microsoft Defender for Endpoint Android App zuweisen würden.</span><span class="sxs-lookup"><span data-stu-id="0e070-196">The group selected here is usually the same group to which you would assign Microsoft Defender for Endpoint Android app.</span></span> 

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="0e070-197">![Abbildung der Konfigurationsrichtlinie für die App erstellen](images/android-select-group.png)</span><span class="sxs-lookup"><span data-stu-id="0e070-197">![Image of the create app configuration policy](images/android-select-group.png)</span></span>
    

     1. <span data-ttu-id="0e070-198">Überprüfen Sie **auf der** Seite Überprüfen + Erstellen, die als Nächstes angezeigt wird, alle Informationen, und wählen Sie dann **Erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="0e070-198">In the **Review + Create** page that comes up next, review all the information and then select **Create**.</span></span> <br>
    
        <span data-ttu-id="0e070-199">Die App-Konfigurationsrichtlinie für Defender for Endpoint, in der die Speicherberechtigung automatischgraniert wird, wird nun der ausgewählten Benutzergruppe zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="0e070-199">The app configuration policy for Defender for Endpoint autogranting the storage permission is now assigned to the selected user group.</span></span>

        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="0e070-200">![Image of android review create app config policy](images/android-review-create.png)</span><span class="sxs-lookup"><span data-stu-id="0e070-200">![Image of android review create app config policy](images/android-review-create.png)</span></span>


10. <span data-ttu-id="0e070-201">Wählen Sie in der Liste Eigenschaftenzuweisungen Bearbeiten die **Option Microsoft Defender ATP-App** \>  \>  \> **aus.**</span><span class="sxs-lookup"><span data-stu-id="0e070-201">Select **Microsoft Defender ATP** app in the list \> **Properties** \> **Assignments** \> **Edit**.</span></span>

    ![Abbildung der Liste der Apps](images/mda-properties.png)


11. <span data-ttu-id="0e070-203">Weisen Sie die App *einer* Benutzergruppe als erforderliche App zu.</span><span class="sxs-lookup"><span data-stu-id="0e070-203">Assign the app as a *Required* app to a user group.</span></span> <span data-ttu-id="0e070-204">Es wird automatisch  während der nächsten Synchronisierung des Geräts über die Unternehmensportal-App im Arbeitsprofil installiert.</span><span class="sxs-lookup"><span data-stu-id="0e070-204">It is automatically installed in the *work profile* during the next sync of the device via Company Portal app.</span></span> <span data-ttu-id="0e070-205">Diese Zuordnung kann durchgeführt werden,  indem Sie zum Abschnitt Erforderliche Gruppe hinzufügen navigieren, die Benutzergruppe auswählen und \>  auf **Auswählen klicken.**</span><span class="sxs-lookup"><span data-stu-id="0e070-205">This assignment can be done by navigating to the *Required* section \> **Add group,** selecting the user group and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0e070-206">![Abbildung der Seite "Anwendung bearbeiten"](images/ea06643280075f16265a596fb9a96042.png)</span><span class="sxs-lookup"><span data-stu-id="0e070-206">![Image of edit application page](images/ea06643280075f16265a596fb9a96042.png)</span></span>


12. <span data-ttu-id="0e070-207">Überprüfen Sie **auf** der Seite Anwendung bearbeiten alle oben eingegebenen Informationen.</span><span class="sxs-lookup"><span data-stu-id="0e070-207">In the **Edit Application** page, review all the information that was entered above.</span></span> <span data-ttu-id="0e070-208">Wählen Sie dann **Überprüfen + Speichern** und dann erneut **speichern** aus, um mit der Zuordnung zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="0e070-208">Then select **Review + Save** and then **Save** again to commence assignment.</span></span>

### <a name="auto-setup-of-always-on-vpn"></a><span data-ttu-id="0e070-209">Automatisches Einrichten von Always-On-VPN</span><span class="sxs-lookup"><span data-stu-id="0e070-209">Auto Setup of Always-on VPN</span></span> 
<span data-ttu-id="0e070-210">Defender for Endpoint unterstützt Gerätekonfigurationsrichtlinien für verwaltete Geräte über Intune.</span><span class="sxs-lookup"><span data-stu-id="0e070-210">Defender for Endpoint supports Device configuration policies for managed devices via Intune.</span></span> <span data-ttu-id="0e070-211">Diese Funktion kann für die automatische Einrichtung von **Always-on-VPN** auf registrierten Android Enterprise-Geräten genutzt werden, sodass der Endbenutzer beim Onboarding keinen VPN-Dienst einrichten muss.</span><span class="sxs-lookup"><span data-stu-id="0e070-211">This capability can be leveraged to **Auto setup of Always-on VPN** on Android Enterprise enrolled devices, so the end user does not need to set up VPN service while onboarding.</span></span>
1.  <span data-ttu-id="0e070-212">Wählen **Sie auf** Geräten **konfigurationsprofile** Profilplattform erstellen Android Enterprise Geräteeinschränkungen auswählen unter einer der folgenden Optionen aus, basierend auf Ihrem  >    >    >   Geräteregistrierungstyp </span><span class="sxs-lookup"><span data-stu-id="0e070-212">On **Devices**, select **Configuration Profiles** > **Create Profile** > **Platform** > **Android Enterprise** Select **Device restrictions** under one of the following, based on your device enrollment type</span></span> 
- <span data-ttu-id="0e070-213">**Vollständig verwaltetes, dediziertes und Corporate-Owned Arbeitsprofil**</span><span class="sxs-lookup"><span data-stu-id="0e070-213">**Fully Managed, Dedicated, and Corporate-Owned Work Profile**</span></span>
- <span data-ttu-id="0e070-214">**Persönliches Arbeitsprofil**</span><span class="sxs-lookup"><span data-stu-id="0e070-214">**Personally owned Work Profile**</span></span>

<span data-ttu-id="0e070-215">Wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="0e070-215">Select **Create**.</span></span>
 
   > ![Abbildung des Gerätekonfigurationsprofils Erstellen](images/1autosetupofvpn.png)
    
2. <span data-ttu-id="0e070-217">**Konfigurationseinstellungen** Geben Sie **einen Namen und** eine Beschreibung **an,** um das Konfigurationsprofil eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="0e070-217">**Configuration Settings** Provide a **Name** and a **Description** to uniquely identify the configuration profile.</span></span> 

   > ![Abbildung des Gerätekonfigurationsprofils Name und Beschreibung](images/2autosetupofvpn.png)
   
 3. <span data-ttu-id="0e070-219">Wählen Sie **Konnektivität** aus, und konfigurieren Sie VPN:</span><span class="sxs-lookup"><span data-stu-id="0e070-219">Select **Connectivity** and configure VPN:</span></span>
- <span data-ttu-id="0e070-220">Aktivieren **Sie always-on VPN** Setup einen VPN-Client im Arbeitsprofil, um nach Möglichkeit automatisch eine Verbindung mit dem VPN herzustellen und wieder herzustellen.</span><span class="sxs-lookup"><span data-stu-id="0e070-220">Enable **Always-on VPN** Setup a VPN client in the work profile to automatically connect and reconnect to the VPN whenever possible.</span></span> <span data-ttu-id="0e070-221">Auf einem bestimmten Gerät kann nur ein VPN-Client für das always-on-VPN konfiguriert werden. Stellen Sie daher sicher, dass nur eine always-on-VPN-Richtlinie auf einem einzelnen Gerät bereitgestellt ist.</span><span class="sxs-lookup"><span data-stu-id="0e070-221">Only one VPN client can be configured for always-on VPN on a given device, so be sure to have no more than one always-on VPN policy deployed to a single device.</span></span> 
- <span data-ttu-id="0e070-222">Wählen **Sie** Benutzerdefiniertes in der Dropdownliste Benutzerdefiniertes VPN in diesem Fall Defender for Endpoint VPN aus, das zum Bereitstellen des Web Protection-Features verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0e070-222">Select **Custom** in VPN client dropdown list Custom VPN in this case is Defender for Endpoint VPN which is used to provide the Web Protection feature.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="0e070-223">Die Microsoft Defender ATP-App muss auf dem Gerät des Benutzers installiert sein, damit die automatische Einrichtung dieses VPN funktioniert.</span><span class="sxs-lookup"><span data-stu-id="0e070-223">Microsoft Defender ATP app must be installed on user’s device, in order to functioning of auto setup of this VPN.</span></span>

- <span data-ttu-id="0e070-224">Geben **Sie die Paket-ID** der Microsoft Defender ATP-App im Google Play Store ein.</span><span class="sxs-lookup"><span data-stu-id="0e070-224">Enter **Package ID** of the Microsoft Defender ATP app in Google Play store.</span></span> <span data-ttu-id="0e070-225">Für die Defender-App-URL https://play.google.com/store/apps/details?id=com.microsoft.scmx ist Paket-ID **com.microsoft.scmx**</span><span class="sxs-lookup"><span data-stu-id="0e070-225">For the Defender app URL https://play.google.com/store/apps/details?id=com.microsoft.scmx, Package ID is **com.microsoft.scmx**</span></span>  
- <span data-ttu-id="0e070-226">**Sperrmodus** Nicht konfiguriert (Standard)</span><span class="sxs-lookup"><span data-stu-id="0e070-226">**Lockdown mode** Not configured (Default)</span></span> 

     ![Abbildung des Gerätekonfigurationsprofils aktivieren Always-On-VPN](images/3autosetupofvpn.png)
   
4. <span data-ttu-id="0e070-228">**Zuordnung** Wählen Sie  **auf**   der Seite Zuweisungen die Benutzergruppe aus, der diese App-Konfigurationsrichtlinie zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="0e070-228">**Assignment** In the **Assignments** page, select the user group to which this app config policy would be assigned to.</span></span> <span data-ttu-id="0e070-229">Klicken **Sie auf Gruppen auswählen,** um die entsprechende Gruppe ein- und auszuwählen, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="0e070-229">Click **Select groups** to include and selecting the applicable group and then click **Next**.</span></span> <span data-ttu-id="0e070-230">Die hier ausgewählte Gruppe ist in der Regel dieselbe Gruppe, der Sie Microsoft Defender for Endpoint Android App zuweisen würden.</span><span class="sxs-lookup"><span data-stu-id="0e070-230">The group selected here is usually the same group to which you would assign Microsoft Defender for Endpoint Android app.</span></span> 

     ![Abbildung der Gerätekonfigurationsprofilzuweisung](images/4autosetupofvpn.png)

5. <span data-ttu-id="0e070-232">Überprüfen Sie **auf der** Seite Überprüfen + Erstellen, die als Nächstes angezeigt wird, alle Informationen, und wählen Sie dann **Erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="0e070-232">In the **Review + Create** page that comes up next, review all the information and then select **Create**.</span></span> <span data-ttu-id="0e070-233">Das Gerätekonfigurationsprofil wird nun der ausgewählten Benutzergruppe zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="0e070-233">The device configuration profile is now assigned to the selected user group.</span></span>    

    ![Abbildung des Gerätekonfigurationsprofils Überprüfen und Erstellen](images/5autosetupofvpn.png)

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="0e070-235">Vollständiger Onboarding- und Überprüfungsstatus</span><span class="sxs-lookup"><span data-stu-id="0e070-235">Complete onboarding and check status</span></span>

1. <span data-ttu-id="0e070-236">Bestätigen Sie den Installationsstatus von Microsoft Defender for Endpoint unter Android, indem Sie auf **Geräteinstallationsstatus klicken.**</span><span class="sxs-lookup"><span data-stu-id="0e070-236">Confirm the installation status of Microsoft Defender for Endpoint on Android by clicking on the **Device Install Status**.</span></span> <span data-ttu-id="0e070-237">Stellen Sie sicher, dass das Gerät hier angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0e070-237">Verify that the device is displayed here.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0e070-238">![Abbildung des Geräteinstallationsstatus](images/900c0197aa59f9b7abd762ab2b32e80c.png)</span><span class="sxs-lookup"><span data-stu-id="0e070-238">![Image of device installation status](images/900c0197aa59f9b7abd762ab2b32e80c.png)</span></span>


2. <span data-ttu-id="0e070-239">Auf dem Gerät können Sie den Onboardingstatus überprüfen, indem Sie zum **Arbeitsprofil gehen.**</span><span class="sxs-lookup"><span data-stu-id="0e070-239">On the device, you can validate the onboarding status by going to the **work profile**.</span></span> <span data-ttu-id="0e070-240">Vergewissern Sie sich, dass Defender for Endpoint verfügbar ist und Dass Sie bei den persönlichen Geräten mit **Arbeitsprofil registriert sind.**</span><span class="sxs-lookup"><span data-stu-id="0e070-240">Confirm that Defender for Endpoint is available and that you are enrolled to the **Personally owned devices with work profile**.</span></span>  <span data-ttu-id="0e070-241">Wenn Sie auf einem vollständig verwalteten Gerät des Unternehmens registriert sind, verfügen Sie über ein einzelnes Profil auf dem Gerät, in dem Sie bestätigen **können,** dass Defender for Endpoint verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="0e070-241">If you are enrolled to a **Corporate-owned, fully managed user device**, you will have a single profile on the device where you can confirm that Defender for Endpoint is available.</span></span>

    ![Abbildung der App auf mobilen Geräten](images/c2e647fc8fa31c4f2349c76f2497bc0e.png)

3. <span data-ttu-id="0e070-243">Wenn die App installiert ist, öffnen Sie die App, akzeptieren Sie die Berechtigungen, und das Onboarding sollte erfolgreich sein.</span><span class="sxs-lookup"><span data-stu-id="0e070-243">When the app is installed, open the app and accept the permissions and then your onboarding should be successful.</span></span>

    ![Abbildung des mobilen Geräts mit der Microsoft Defender for Endpoint-App](images/mda-devicesafe.png)

4. <span data-ttu-id="0e070-245">In dieser Phase wird das Gerät erfolgreich in Defender for Endpoint für Android onboardiert.</span><span class="sxs-lookup"><span data-stu-id="0e070-245">At this stage the device is successfully onboarded onto Defender for Endpoint for Android.</span></span> <span data-ttu-id="0e070-246">Sie können dies im [Microsoft Defender Security Center überprüfen,](https://securitycenter.microsoft.com) indem Sie zur Seite **Geräte** navigieren.</span><span class="sxs-lookup"><span data-stu-id="0e070-246">You can verify this on the [Microsoft Defender Security Center](https://securitycenter.microsoft.com) by navigating to the **Devices** page.</span></span>

    ![Abbildung des Microsoft Defender for Endpoint-Portals](images/9fe378a1dce0f143005c3aa53d8c4f51.png)


## <a name="related-topics"></a><span data-ttu-id="0e070-248">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="0e070-248">Related topics</span></span>
- [<span data-ttu-id="0e070-249">Übersicht über Microsoft Defender for Endpoint unter Android</span><span class="sxs-lookup"><span data-stu-id="0e070-249">Overview of Microsoft Defender for Endpoint on Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="0e070-250">Konfigurieren von Microsoft Defender for Endpoint unter Android-Features</span><span class="sxs-lookup"><span data-stu-id="0e070-250">Configure Microsoft Defender for Endpoint on Android features</span></span>](android-configure.md)
