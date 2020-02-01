---
title: Überprüfen der APP-Schutzeinstellungen auf Android-oder IOS-Geräten
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: f3433b6b-02f7-447f-9d62-306bf03638b0
description: Learn how to validate the Microsoft 365 Business app protection settings in your Android or iOS devices.
ms.openlocfilehash: 47ce137f785c595992886c756ad85b80957272fe
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594973"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a><span data-ttu-id="75921-103">Überprüfen der APP-Schutzeinstellungen auf Android-oder IOS-Geräten</span><span class="sxs-lookup"><span data-stu-id="75921-103">Validate app protection settings on Android or iOS devices</span></span>

<span data-ttu-id="75921-104">Befolgen Sie die Anweisungen in den folgenden Abschnitten, um Einstellungen für den App-Schutz auf Android-oder IOS-Geräten zu validieren.</span><span class="sxs-lookup"><span data-stu-id="75921-104">Follow the instructions in the following sections to validate app protection settings on Android or iOS devices.</span></span>
  
## <a name="android"></a><span data-ttu-id="75921-105">Android</span><span class="sxs-lookup"><span data-stu-id="75921-105">Android</span></span>
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="75921-106">Überprüfen, ob die Einstellungen für den App-Schutz auf Benutzergeräten funktionieren</span><span class="sxs-lookup"><span data-stu-id="75921-106">Check that the app protection settings are working on user devices</span></span>

<span data-ttu-id="75921-107">Nachdem Sie [App-Konfigurationen für Android-Geräte festgelegt haben](app-protection-settings-for-android-and-ios.md), um die Apps zu schützen, können Sie folgendermaßen überprüfen, ob die gewählten Einstellungen funktionieren.</span><span class="sxs-lookup"><span data-stu-id="75921-107">After you [set app configurations for Android devices](app-protection-settings-for-android-and-ios.md) to protect the apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="75921-108">Stellen Sie zunächst sicher, dass die Richtlinie auf die APP angewendet wird, in der Sie Sie validieren möchten.</span><span class="sxs-lookup"><span data-stu-id="75921-108">First, make sure that the policy applies to the app in which you're going to validate it.</span></span>
  
1. <span data-ttu-id="75921-109">Wechseln Sie im Microsoft 365 Business [Admin Center](https://portal.office.com) zu **Richtlinien** \> **Richtlinie bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="75921-109">In the Microsoft 365 Business [admin center](https://portal.office.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="75921-110">Wählen Sie **Anwendungsrichtlinie für Android** für die Einstellungen, die Sie beim Setup erstellt haben, oder eine andere Richtlinie, die Sie erstellt haben, und stellen Sie sicher, dass Sie für Outlook erzwungen wird, beispielsweise.</span><span class="sxs-lookup"><span data-stu-id="75921-110">Choose **Application policy for Android** for the settings you created at setup, or another policy you created, and verify that it's enforced for Outlook, for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a><span data-ttu-id="75921-112">Überprüfen von "Für den Zugriff auf Office-Apps PIN bzw. Fingerabdruck anfordern"</span><span class="sxs-lookup"><span data-stu-id="75921-112">Validate Require a PIN or a fingerprint to access Office apps</span></span>

<span data-ttu-id="75921-113">Wählen Sie im Bereich **Richtlinie bearbeiten** neben **Zugriffssteuerung für Office-Dokumente** die Option **Bearbeiten** aus, erweitern Sie **Benutzerzugriff auf Office-Dateien auf mobilen Geräten verwalten**, und stellen Sie sicher, dass **Für den Zugriff auf Office-Apps PIN bzw. Fingerabdruck anfordern** auf **Ein** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="75921-113">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Stellen Sie sicher, dass für den Zugriff auf Office-Apps eine PIN oder ein Fingerabdruck erforderlich ist auf ein festgelegt ist.](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="75921-115">Öffnen Sie Outlook auf dem Android-Gerät des Benutzers, und melden Sie sich mit dessen Microsoft 365 Business-Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="75921-115">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="75921-116">Sie werden auch aufgefordert, eine PIN einzugeben oder einen Fingerabdruck zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="75921-116">You'll also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your Android device to access Office apps.](media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="75921-118">Überprüfen von "PIN nach dieser Anzahl von fehlgeschlagenen Versuchen zurücksetzen"</span><span class="sxs-lookup"><span data-stu-id="75921-118">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="75921-119">Klicken Sie im Bereich **Richtlinie bearbeiten** neben Office- **Dokumenten-Zugriffssteuerung**auf **Bearbeiten** , erweitern Sie **verwalten, wie Benutzer auf Office-Dateien auf mobilen Geräten zugreifen**, und stellen Sie sicher, dass die **Zurücksetzen-PIN nach der Anzahl der Fehlversuche** auf eine bestimmte Zahl festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="75921-119">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number.</span></span> <span data-ttu-id="75921-120">Dies ist standardmäßig 5.</span><span class="sxs-lookup"><span data-stu-id="75921-120">This is 5 by default.</span></span> 
  
1. <span data-ttu-id="75921-121">Öffnen Sie Outlook auf dem Android-Gerät des Benutzers, und melden Sie sich mit dessen Microsoft 365 Business-Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="75921-121">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="75921-122">Geben Sie so oft, wie in der Richtlinie angegeben, eine falsche PIN ein.</span><span class="sxs-lookup"><span data-stu-id="75921-122">Enter an incorrect PIN as many times as specified by the policy.</span></span> <span data-ttu-id="75921-123">Es wird eine Aufforderung angezeigt, die besagt, dass der **Grenzwert für PIN-Versuche erreicht** wurde, um die PIN zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="75921-123">You'll see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. <span data-ttu-id="75921-125">Drücken Sie **PIN zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="75921-125">Press **Reset PIN**.</span></span> <span data-ttu-id="75921-126">Sie werden aufgefordert, sich mit den Microsoft 365 Business-Anmeldeinformationen des Benutzers anzumelden und dann eine neue PIN einzurichten.</span><span class="sxs-lookup"><span data-stu-id="75921-126">You'll be prompted to sign in with the user's Microsoft 365 Business credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="75921-127">Überprüfen von "Benutzer zum Speichern aller Arbeitsdateien auf OneDrive for Business zwingen"</span><span class="sxs-lookup"><span data-stu-id="75921-127">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="75921-128">Wählen Sie im Bereich **Richtlinie bearbeiten** neben **Schutz bei verlorenen oder gestohlenen Geräten** die Option **Bearbeiten** aus, erweitern Sie **Arbeitsdateien schützen, wenn Geräte verloren gehen oder gestohlen werden**, und stellen Sie sicher, dass **Benutzer zum Speichern aller Arbeitsdateien auf OneDrive for Business zwingen** auf **Ein** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="75921-128">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="75921-130">Öffnen Sie Outlook auf dem Android-Gerät des Benutzers, melden Sie sich mit dessen Microsoft 365 Business-Anmeldeinformationen an, und geben Sie eine PIN ein, falls Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="75921-130">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="75921-131">Öffnen Sie eine E-Mail mit einer Anlage, und tippen Sie neben den Informationen zur Anlage auf den Abwärtspfeil.</span><span class="sxs-lookup"><span data-stu-id="75921-131">Open an email that contains an attachment and tap the down arrow icon next to the attachment's information.</span></span>
    
    ![Tap the down arrow next to an attachment to try to save it.](media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    <span data-ttu-id="75921-133">Im unteren Bereich des Bildschirms sehen Sie **nicht auf dem Gerät speichern** .</span><span class="sxs-lookup"><span data-stu-id="75921-133">You'll see **Cannot save to device** on the bottom of the screen.</span></span> 
    
    ![Warning text that indicates cannot save a file locally to an Android.](media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > <span data-ttu-id="75921-135">Da "Auf OneDrive for Business speichern" für Android zu diesem Zeitpunkt nicht aktiviert ist, können Sie nur sehen, dass lokales Speichern blockiert ist.</span><span class="sxs-lookup"><span data-stu-id="75921-135">Saving to OneDrive for Business is not enabled for Android at this time, so you can only see that saving locally is blocked.</span></span> 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="75921-136">Überprüfen von "Benutzer müssen sich erneut anmelden, nachdem Office-Apps für eine bestimmte Zeit im Leerlauf waren"</span><span class="sxs-lookup"><span data-stu-id="75921-136">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="75921-137">Wählen Sie im Bereich **Richtlinie bearbeiten** neben Office- **Dokumenten-Zugriffssteuerung** **Bearbeiten** , erweitern Sie **verwalten, wie Benutzer auf Office-Dateien auf mobilen Geräten zugreifen**, und stellen Sie sicher, dass **Benutzer sich erneut anmelden müssen, nachdem Office-Apps im Leerlauf waren** , auf eine bestimmte Anzahl von Minuten festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="75921-137">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes.</span></span> <span data-ttu-id="75921-138">Dies ist standardmäßig 30 Minuten.</span><span class="sxs-lookup"><span data-stu-id="75921-138">This is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="75921-139">Öffnen Sie Outlook auf dem Android-Gerät des Benutzers, melden Sie sich mit dessen Microsoft 365 Business-Anmeldeinformationen an, und geben Sie eine PIN ein, falls Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="75921-139">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="75921-p105">Jetzt sollte der Outlook-Posteingang angezeigt werden. Lassen Sie das Android-Gerät im Leerlauf für mindestens 30 Minuten unberührt liegen (oder einen anderen Zeitraum, der länger als die in der Richtlinie festgelegte Einstellung ist). Wahrscheinlich wird der Bildschirm des Geräts dunkel.</span><span class="sxs-lookup"><span data-stu-id="75921-p105">You should now see Outlook's inbox. Let the Android device idle untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="75921-143">Greifen Sie erneut auf Outlook auf dem Android-Gerät zu.</span><span class="sxs-lookup"><span data-stu-id="75921-143">Access Outlook on the Android device again.</span></span>
    
4. <span data-ttu-id="75921-144">Sie werden aufgefordert, Ihre PIN einzugeben, bevor Sie erneut auf Outlook zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="75921-144">You'll be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="75921-145">Überprüfen von "Arbeitsdateien mit Verschlüsselung schützen"</span><span class="sxs-lookup"><span data-stu-id="75921-145">Validate Protect work files with encryption</span></span>

<span data-ttu-id="75921-146">Wählen Sie im Bereich **Richtlinie bearbeiten** neben **Schutz bei verlorenen oder gestohlenen Geräten** die Option **Bearbeiten** aus, erweitern Sie **Arbeitsdateien schützen, wenn Geräte verloren gehen oder gestohlen werden**, und stellen Sie sicher, dass **Arbeitsdateien mit Verschlüsselung schützen** auf **Ein** und **Benutzer zum Speichern aller Arbeitsdateien auf OneDrive for Business zwingen** auf **Aus** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="75921-146">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="75921-147">Öffnen Sie Outlook auf dem Android-Gerät des Benutzers, melden Sie sich mit dessen Microsoft 365 Business-Anmeldeinformationen an, und geben Sie eine PIN ein, falls Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="75921-147">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="75921-148">Öffnen Sie eine e-Mail mit einigen Bild Dateianlagen.</span><span class="sxs-lookup"><span data-stu-id="75921-148">Open an email that contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="75921-149">Tippen Sie neben den Informationen zur Anlage auf den Abwärtspfeil, um sie zu speichern.</span><span class="sxs-lookup"><span data-stu-id="75921-149">Tap the down arrow icon next to the attachment's info to save it.</span></span>
    
    ![Tap the down arrow to save the figure file to the Android device.](media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. <span data-ttu-id="75921-p106">Möglicherweise werden Sie aufgefordert, Outlook den Zugriff auf Fotos, Medien und Dateien auf Ihrem Gerät zu erlauben. Tippen Sie auf **Zulassen**.</span><span class="sxs-lookup"><span data-stu-id="75921-p106">You may be prompted to allow Outlook to access photos, media, and files on your device. Tap **Allow**.</span></span>
    
5. <span data-ttu-id="75921-153">Wählen Sie unten auf dem Bildschirm **Auf Gerät speichern** aus, und öffnen Sie die App **Katalog**.</span><span class="sxs-lookup"><span data-stu-id="75921-153">At the bottom of the screen, choose to **Save to Device** and then open the **Gallery** app.</span></span> 
    
6. <span data-ttu-id="75921-p107">Es sollte ein verschlüsseltes Foto (oder mehrere Fotos, falls Sie mehrere Bildanlagedateien gespeichert haben) in der Liste angezeigt werden. Dieses Foto kann in der Liste "Bilder" als graues Quadrat mit einem weißen Ausrufezeichen in einem weißen Kreis in der Mitte des Quadrats angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="75921-p107">You should see an encrypted photo (or more, if you saved multiple image file attachments) in the list. It may appear in the Pictures list as a gray square with a white exclamation point within a white circle in the center of the gray square.</span></span>
    
    ![An encrypted image file in the Gallery app.](media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="ios"></a><span data-ttu-id="75921-157">iOS</span><span class="sxs-lookup"><span data-stu-id="75921-157">iOS</span></span>
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="75921-158">Überprüfen, ob die Einstellungen für den App-Schutz auf Benutzergeräten funktionieren</span><span class="sxs-lookup"><span data-stu-id="75921-158">Check that the App protection settings are working on user devices</span></span>

<span data-ttu-id="75921-159">Nachdem Sie [App-Konfigurationen für iOS-Geräte festgelegt haben](app-protection-settings-for-android-and-ios.md), um Apps zu schützen, können Sie folgendermaßen überprüfen, ob die gewählten Einstellungen funktionieren.</span><span class="sxs-lookup"><span data-stu-id="75921-159">After you [set app configurations for iOS devices](app-protection-settings-for-android-and-ios.md) to protect apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="75921-160">Stellen Sie zunächst sicher, dass die Richtlinie auf die APP angewendet wird, in der Sie Sie validieren möchten.</span><span class="sxs-lookup"><span data-stu-id="75921-160">First, make sure that the policy applies to the app in which you're going to validate it.</span></span>
  
1. <span data-ttu-id="75921-161">Wechseln Sie im Microsoft 365 Business [Admin Center](https://portal.office.com) zu **Richtlinien** \> **Richtlinie bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="75921-161">In the Microsoft 365 Business [admin center](https://portal.office.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="75921-162">Wählen Sie **Anwendungsrichtlinie für IOS** für die Einstellungen, die Sie beim Setup erstellt haben, oder eine andere Richtlinie, die Sie erstellt haben, und stellen Sie sicher, dass Sie für Outlook erzwungen wird.</span><span class="sxs-lookup"><span data-stu-id="75921-162">Choose **Application policy for iOS** for the settings you created at setup, or another policy you created, and verify that it's enforced for Outlook for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a><span data-ttu-id="75921-164">Überprüfen von "Für den Zugriff auf Office-Apps PIN anfordern"</span><span class="sxs-lookup"><span data-stu-id="75921-164">Validate Require a PIN to access Office apps</span></span>

<span data-ttu-id="75921-165">Wählen Sie im Bereich **Richtlinie bearbeiten** neben **Zugriffssteuerung für Office-Dokumente** die Option **Bearbeiten** aus, erweitern Sie **Benutzerzugriff auf Office-Dateien auf mobilen Geräten verwalten**, und stellen Sie sicher, dass **Für den Zugriff auf Office-Apps PIN bzw. Fingerabdruck anfordern** auf **Ein** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="75921-165">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Stellen Sie sicher, dass für den Zugriff auf Office-Apps eine PIN oder ein Fingerabdruck erforderlich ist auf ein festgelegt ist.](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="75921-167">Öffnen Sie Outlook auf dem iOS-Gerät des Benutzers, und melden Sie sich mit den Microsoft 365 Business-Anmeldeinformationen des Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="75921-167">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="75921-168">Sie werden auch aufgefordert, eine PIN einzugeben oder einen Fingerabdruck zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="75921-168">You'll also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your IOS device to access Office apps.](media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="75921-170">Überprüfen von "PIN nach dieser Anzahl von fehlgeschlagenen Versuchen zurücksetzen"</span><span class="sxs-lookup"><span data-stu-id="75921-170">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="75921-171">Klicken Sie im Bereich **Richtlinie bearbeiten** neben Office- **Dokumenten-Zugriffssteuerung**auf **Bearbeiten** , erweitern Sie **verwalten, wie Benutzer auf Office-Dateien auf mobilen Geräten zugreifen**, und stellen Sie sicher, dass die **Zurücksetzen-PIN nach der Anzahl der Fehlversuche** auf eine bestimmte Zahl festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="75921-171">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number.</span></span> <span data-ttu-id="75921-172">Dies ist standardmäßig 5.</span><span class="sxs-lookup"><span data-stu-id="75921-172">This is 5 by default.</span></span> 
  
1. <span data-ttu-id="75921-173">Öffnen Sie Outlook auf dem iOS-Gerät des Benutzers, und melden Sie sich mit den Microsoft 365 Business-Anmeldeinformationen des Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="75921-173">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="75921-174">Geben Sie so oft, wie in der Richtlinie angegeben, eine falsche PIN ein.</span><span class="sxs-lookup"><span data-stu-id="75921-174">Enter an incorrect PIN as many times as specified by the policy.</span></span> <span data-ttu-id="75921-175">Es wird eine Aufforderung angezeigt, die besagt, dass der **Grenzwert für PIN-Versuche erreicht** wurde, um die PIN zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="75921-175">You'll see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. <span data-ttu-id="75921-177">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="75921-177">Press **OK**.</span></span> <span data-ttu-id="75921-178">Sie werden aufgefordert, sich mit den Microsoft 365 Business-Anmeldeinformationen des Benutzers anzumelden und dann eine neue PIN einzurichten.</span><span class="sxs-lookup"><span data-stu-id="75921-178">You'll be prompted to sign in with the user's Microsoft 365 Business credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="75921-179">Überprüfen von "Benutzer zum Speichern aller Arbeitsdateien auf OneDrive for Business zwingen"</span><span class="sxs-lookup"><span data-stu-id="75921-179">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="75921-180">Wählen Sie im Bereich **Richtlinie bearbeiten** neben **Schutz bei verlorenen oder gestohlenen Geräten** die Option **Bearbeiten** aus, erweitern Sie **Arbeitsdateien schützen, wenn Geräte verloren gehen oder gestohlen werden**, und stellen Sie sicher, dass **Benutzer zum Speichern aller Arbeitsdateien auf OneDrive for Business zwingen** auf **Ein** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="75921-180">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="75921-182">Öffnen Sie Outlook auf dem iOS-Gerät des Benutzers, melden Sie sich mit den Microsoft 365 Business-Anmeldeinformationen des Benutzers an, und geben Sie eine PIN ein, falls Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="75921-182">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="75921-183">Öffnen Sie eine E-Mail-Nachricht, die eine Anlage enthält, öffnen Sie die Anlage, und klicken Sie am unteren Rand des Bildschirms auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="75921-183">Open an email that contains an attachment, open the attachment and choose **Save** on the bottom of the screen.</span></span> 
    
    ![Tap the Save option after you open an attachment to try to save it.](media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. <span data-ttu-id="75921-185">Es sollte nur eine Option für OneDrive for Business angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="75921-185">You should only see an option for OneDrive for Business.</span></span> <span data-ttu-id="75921-186">Wenn dies nicht der Fall ist, tippen Sie auf **Konto hinzufügen** und wählen Sie **OneDrive für Unternehmen** auf dem Bildschirm **Speicherkonto hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="75921-186">If not, tap **Add Account** and select **OneDrive for Business** from the **Add Storage Account** screen.</span></span> <span data-ttu-id="75921-187">Stellen Sie das Microsoft 365 Business des Endbenutzers zum Anmelden bereit, falls Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="75921-187">Provide the end user's Microsoft 365 Business to sign in when prompted.</span></span> 
    
    <span data-ttu-id="75921-188">Tippen Sie auf **Speichern**, und wählen Sie **OneDrive for Business** aus.</span><span class="sxs-lookup"><span data-stu-id="75921-188">Tap **Save** and select **OneDrive for Business**.</span></span>
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="75921-189">Überprüfen von "Benutzer müssen sich erneut anmelden, nachdem Office-Apps für eine bestimmte Zeit im Leerlauf waren</span><span class="sxs-lookup"><span data-stu-id="75921-189">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="75921-190">Wählen Sie im Bereich **Richtlinie bearbeiten** neben Office- **Dokumenten-Zugriffssteuerung** **Bearbeiten** , erweitern Sie **verwalten, wie Benutzer auf Office-Dateien auf mobilen Geräten zugreifen**, und stellen Sie sicher, dass **Benutzer sich erneut anmelden müssen, nachdem Office-Apps im Leerlauf waren** , auf eine bestimmte Anzahl von Minuten festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="75921-190">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes.</span></span> <span data-ttu-id="75921-191">Dies ist standardmäßig 30 Minuten.</span><span class="sxs-lookup"><span data-stu-id="75921-191">This is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="75921-192">Öffnen Sie Outlook auf dem iOS-Gerät des Benutzers, melden Sie sich mit den Microsoft 365 Business-Anmeldeinformationen des Benutzers an, und geben Sie eine PIN ein, falls Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="75921-192">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="75921-p113">Jetzt sollte der Outlook-Posteingang angezeigt werden. Lassen Sie die iOS-Gerät für mindestens 30 Minuten unberührt liegen (oder einen anderen Zeitraum, der länger als die in der Richtlinie angegebene Einstellung ist). Wahrscheinlich wird der Bildschirm des Geräts dunkel.</span><span class="sxs-lookup"><span data-stu-id="75921-p113">You should now see Outlook's inbox. Let the iOS device untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="75921-196">Greifen Sie erneut auf Outlook auf dem IOS-Gerät zu.</span><span class="sxs-lookup"><span data-stu-id="75921-196">Access Outlook on the iOS device again.</span></span>
    
4. <span data-ttu-id="75921-197">Sie werden aufgefordert, Ihre PIN einzugeben, bevor Sie erneut auf Outlook zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="75921-197">You'll be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="75921-198">Überprüfen von "Arbeitsdateien mit Verschlüsselung schützen"</span><span class="sxs-lookup"><span data-stu-id="75921-198">Validate Protect work files with encryption</span></span>

<span data-ttu-id="75921-199">Wählen Sie im Bereich **Richtlinie bearbeiten** die Option **Bearbeiten** neben **Schutz bei verlorenen oder gestohlenen Geräten** aus, erweitern Sie **Arbeitsdateien schützen, wenn Geräte verloren gehen oder gestohlen werden**, und stellen Sie sicher, dass **Arbeitsdateien mit Verschlüsselung schützen** auf **Ein** und **Benutzer zum Speichern aller Arbeitsdateien auf OneDrive for Business zwingen** auf **Aus** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="75921-199">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="75921-200">Öffnen Sie Outlook auf dem iOS-Gerät des Benutzers, melden Sie sich mit den Microsoft 365 Business-Anmeldeinformationen des Benutzers an, und geben Sie eine PIN ein, falls Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="75921-200">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="75921-201">Öffnen Sie eine e-Mail mit einigen Bild Dateianlagen.</span><span class="sxs-lookup"><span data-stu-id="75921-201">Open an email that contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="75921-202">Tippen Sie auf die Anlage und dann darunter auf die Option **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="75921-202">Tap the attachment and then tap the **Save** option under it.</span></span> 
    
4. <span data-ttu-id="75921-p114">Öffnen Sie die App **Fotos** auf dem Startbildschirm. Es sollte ein verschlüsseltes Foto (oder mehrere, falls Sie mehrere Bildanlagedateien gespeichert haben) angezeigt werden, gespeichert, aber verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="75921-p114">Open **Photos** app from the home screen. You should see an encrypted photo (or more, if you saved multiple image file attachments) saved, but encrypted.</span></span> 
    
---

