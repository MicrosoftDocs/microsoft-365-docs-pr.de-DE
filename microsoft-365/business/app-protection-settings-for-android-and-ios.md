---
title: Festlegen von App-Schutzeinstellungen für Android- oder iOS-Geräte
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: Informationen Sie zum Erstellen, bearbeiten oder löschen eine Richtlinie zur Verwaltung von app und Arbeitsdateien auf Android oder iOS-Geräten zu schützen.
ms.openlocfilehash: ed03227496120369b94bf2396974eebfd7798678
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868129"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a><span data-ttu-id="f568d-103">Festlegen von App-Schutzeinstellungen für Android- oder iOS-Geräte</span><span class="sxs-lookup"><span data-stu-id="f568d-103">Set app protection settings for Android or iOS devices</span></span>

## <a name="create-an-app-management-policy"></a><span data-ttu-id="f568d-104">Erstellen einer App-Verwaltungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="f568d-104">Create an app management policy</span></span>

1. <span data-ttu-id="f568d-105">Melden Sie sich bei [Microsoft 365 Business](https://portal.office.com) mit globalen Administratoranmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="f568d-105">Sign in to [Microsoft 365 Business](https://portal.office.com) with global admin credentials.</span></span> 
    
2. <span data-ttu-id="f568d-106">Wählen Sie im Admin Center auf der Karte **Geräterichtlinien** die Option **Richtlinie hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="f568d-106">In the admin center, on the **Device policies** card, choose **Add policy**.</span></span>
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. <span data-ttu-id="f568d-108">Geben Sie im Bereich **Richtlinie hinzufügen** einen eindeutigen Namen für diese Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="f568d-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="f568d-109">Wählen Sie unter **Richtlinientyp** eine der Optionen **Anwendungsverwaltung für Android** oder **Anwendungsverwaltung für iOS** aus - je nachdem, welchen Richtliniensatz Sie erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="f568d-109">Under **Policy type**, choose **Application Management for Android** or **Application Management for iOS** depending on which set of policies you want to create.</span></span> 
    
5. <span data-ttu-id="f568d-p101">Erweitern Sie **Protect Arbeitsdateien bei verlorenen oder gestohlenen Geräten sind** und **den Zugriff von Benutzern auf Office-Dateien auf mobilen Geräten verwalten** \> konfigurieren Sie die Einstellungen wie möchten Sie. Der **Zugriff von Benutzern auf Office-Dateien auf mobilen Geräten verwalten** ist standardmäßig **deaktiviert** , aber es wird empfohlen, dass Sie **es aktivieren** , und übernehmen Sie die Standardwerte. Weitere Informationen finden Sie unter [Einstellungen verfügbar](app-protection-settings-for-android-and-ios.md#bkmk_availablesettings) .</span><span class="sxs-lookup"><span data-stu-id="f568d-p101">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** \> configure the settings how you would like. The **Manage how users access Office files on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values. See [Available settings](app-protection-settings-for-android-and-ios.md#bkmk_availablesettings) for more information.</span></span> 
    
    <span data-ttu-id="f568d-113">Mit dem Link **Standardeinstellungen zurücksetzen** können Sie jederzeit die Standardeinstellungen wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="f568d-113">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. <span data-ttu-id="f568d-p102">Als Nächstes entscheiden **erhalten, die diese Einstellungen?** Wenn Sie nicht die Standardsicherheitsgruppe für **Alle Benutzer** verwenden möchten, **Ändern**, wählen Sie die Sicherheitsgruppen, die diese Einstellungen erhalten \> **auswählen**.</span><span class="sxs-lookup"><span data-stu-id="f568d-p102">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="f568d-117">Wählen Sie schließlich **Fertig** aus, um die Richtlinie zu speichern, und weisen Sie sie Geräten zu.</span><span class="sxs-lookup"><span data-stu-id="f568d-117">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="edit-an-app-management-policy"></a><span data-ttu-id="f568d-118">Bearbeiten einer App-Verwaltungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="f568d-118">Edit an app management policy</span></span>

1. <span data-ttu-id="f568d-119">Wählen Sie auf der Karte **Richtlinien** **Richtlinie bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="f568d-119">On the **Policies** card, choose **Edit policy**.</span></span>
    
2. <span data-ttu-id="f568d-120">Wählen Sie im Bereich **Richtlinie bearbeiten** die Richtlinie aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="f568d-120">On the **Edit policy** pane, choose the policy you want to change</span></span> 
    
3. <span data-ttu-id="f568d-p103">Wählen Sie neben jeder Einstellung **Bearbeiten** aus, um die Werte in der Richtlinie zu ändern. Wenn Sie einen Wert ändern, wird er in der Richtlinie automatisch gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f568d-p103">Choose **Edit** next to each setting to change the values in the policy. When you change a value, it is automatically saved into the policy</span></span> 
    
4. <span data-ttu-id="f568d-123">Wenn Sie fertig sind, schließen Sie den Bereich **Richtlinie bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="f568d-123">When you are finished, close the **Edit policy** pane.</span></span> 
    
## <a name="delete-an-app-management-policy"></a><span data-ttu-id="f568d-124">Löschen einer App-Verwaltungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="f568d-124">Delete an app management policy</span></span>

1. <span data-ttu-id="f568d-125">Wählen Sie auf der Registerkarte **Richtlinien** die Option **Richtlinie löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="f568d-125">On the **Policies** card, choose **Delete policy**.</span></span>
    
2. <span data-ttu-id="f568d-126">Wählen Sie die Richtlinien, die Sie löschen möchten, im Bereich **Löschrichtlinie** \> **Wählen**und dann **bestätigen** , löschen die Richtlinie oder Richtlinien, die Sie ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="f568d-126">On the **Delete policy** pane, choose the policies you want to delete \> **Select**, then **Confirm** to delete the policy or policies you chose.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="f568d-127">Verfügbare Einstellungen</span><span class="sxs-lookup"><span data-stu-id="f568d-127">Available settings</span></span>

<span data-ttu-id="f568d-128">Die nachstehenden Tabellen enthalten detaillierte Informationen zu den verfügbaren Einstellungen zum Schutz von Arbeitsdateien auf Geräten und den Einstellungen zur Steuerung, wie Benutzer über ihre mobilen Geräte auf Office-Dateien zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="f568d-128">The following tables give detailed information about the available settings to protect work files on devices and the settings that control how users access Office files from their mobile devices.</span></span>
  
 <span data-ttu-id="f568d-129">Weitere Informationen finden Sie unter [Zuordnung von Microsoft 365 Business-Schutzfunktionen zu Intune-Einstellungen](map-protection-features-to-intune-settings.md).</span><span class="sxs-lookup"><span data-stu-id="f568d-129">See [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md) for more information.</span></span> 
  
### <a name="settings-that-protect-work-files"></a><span data-ttu-id="f568d-130">Einstellungen zum Schutz von Arbeitsdateien</span><span class="sxs-lookup"><span data-stu-id="f568d-130">Settings that protect work files</span></span>

<span data-ttu-id="f568d-131">Die folgenden Einstellungen stehen zum Schutz von Arbeitsdateien zur Verfügung, wenn das Gerät eines Benutzers verloren geht oder gestohlen wird:</span><span class="sxs-lookup"><span data-stu-id="f568d-131">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f568d-132">Einstellung</span><span class="sxs-lookup"><span data-stu-id="f568d-132">Setting</span></span>  <br/> |<span data-ttu-id="f568d-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f568d-133">Description</span></span>  <br/> |
|<span data-ttu-id="f568d-134">Arbeitsdateien von einem inaktiven Gerät löschen nach diesem Zeitraum (Tage)</span><span class="sxs-lookup"><span data-stu-id="f568d-134">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="f568d-135">Wenn ein Gerät während der hier festgelegten Anzahl von Tagen nicht genutzt wird, werden alle auf dem Gerät gespeicherten Arbeitsdateien automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f568d-135">If a device is not used for the number of days that you specify here, any work files stored on the device will automatically be deleted.</span></span>  <br/> |
|<span data-ttu-id="f568d-136">Benutzer zum Speichern aller Arbeitsdateien auf OneDrive for Business zwingen</span><span class="sxs-lookup"><span data-stu-id="f568d-136">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="f568d-137">Wenn diese Einstellung auf **Ein** festgelegt wurde, ist der einzige verfügbare Speicherort für Arbeitsdateien OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="f568d-137">If this setting is **On**, the only available save location for work files will be OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="f568d-138">Arbeitsdateien verschlüsseln</span><span class="sxs-lookup"><span data-stu-id="f568d-138">Encrypt work files</span></span>  <br/> |<span data-ttu-id="f568d-p104">Behalten Sie für diese Einstellung **Ein** bei, damit Arbeitsdateien durch Verschlüsselung geschützt werden. Selbst wenn das Gerät verloren geht oder gestohlen wird, kann niemand Ihre Unternehmensdaten lesen.  </span><span class="sxs-lookup"><span data-stu-id="f568d-p104">Keep this setting **On** so that work files are protected by encryption. Even if the device is lost or stolen, no one will be able to read your company data.  </span></span><br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="f568d-141">Einstellungen, die steuern, wie Benutzer auf Office-Dateien auf mobilen Geräten zugreifen</span><span class="sxs-lookup"><span data-stu-id="f568d-141">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="f568d-142">Mit den folgenden Einstellungen können Sie den Zugriff von Benutzern auf Office-Arbeitsdateien verwalten:</span><span class="sxs-lookup"><span data-stu-id="f568d-142">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f568d-143">Einstellung</span><span class="sxs-lookup"><span data-stu-id="f568d-143">Setting</span></span>  <br/> |<span data-ttu-id="f568d-144">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f568d-144">Description</span></span>  <br/> |
|<span data-ttu-id="f568d-145">Für den Zugriff auf Office-Apps PIN bzw. digitalen Fingerabdruck anfordern</span><span class="sxs-lookup"><span data-stu-id="f568d-145">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="f568d-146">Ist diese Einstellung **aktiviert**, müssen Benutzer zusätzlich zum Benutzernamen und Kennwort eine andere Form der Authentifizierung angeben, bevor sie Office-Apps auf ihren mobilen Geräten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="f568d-146">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="f568d-147">PIN nach dieser Anzahl von fehlerhaften Anmeldeversuchen zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="f568d-147">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="f568d-148">Um zu verhindern, dass ein nicht autorisierter Benutzer eine PIN nach dem Zufallsprinzip errät, wird die PIN, die nach der angegebenen Anzahl von Fehlversuchen zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="f568d-148">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="f568d-149">Benutzer müssen sich erneut anmelden, nachdem Office-Apps im Leerlauf waren für</span><span class="sxs-lookup"><span data-stu-id="f568d-149">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="f568d-150">Diese Einstellung bestimmt, wie lange ein Benutzer inaktiv sein kann, bevor er dazu aufgefordert wird, sich erneut anzumelden.</span><span class="sxs-lookup"><span data-stu-id="f568d-150">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="f568d-151">Zugriff auf Arbeitsdateien auf Geräten mit entfernten Nutzungsbeschränkungen verweigern</span><span class="sxs-lookup"><span data-stu-id="f568d-151">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="f568d-p105">Clevere Benutzer verfügen möglicherweise über ein Gerät, bei dem die Nutzungsbeschränkungen entfernt wurden. Dies bedeutet, dass der Benutzer das Betriebssystem ändern kann, wodurch das Gerät empfänglicher für Schadsoftware werden kann. Solche Geräte können gesperrt werden, wenn die Einstellung auf **Ein** festgelegt wurde.  </span><span class="sxs-lookup"><span data-stu-id="f568d-p105">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="f568d-155">Benutzern das Kopieren von Inhalten aus Office-Apps in persönliche Apps erlauben</span><span class="sxs-lookup"><span data-stu-id="f568d-155">Allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="f568d-p106">Wir lassen dies standardmäßig, jedoch ist die Einstellung **auf**der Benutzer konnte Informationen in einer Datei in eine persönliche Datei kopieren. Wenn die Einstellung **deaktiviert**ist, kann der Benutzer kann nicht zum Kopieren von Informationen aus einem Konto Arbeit in einer persönlichen app oder persönliches Konto verwendet.</span><span class="sxs-lookup"><span data-stu-id="f568d-p106">We do allow this by default, but if the setting is **On**, the user could copy information in a work file to a personal file. If the setting is **Off**, the user will be unable to copy information from a work account into a personal app or personal account.  </span></span><br/> |
   

  

