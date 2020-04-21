---
title: Festlegen von App-Schutzeinstellungen für Android- oder iOS-Geräte
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
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: Hier erfahren Sie, wie Sie eine APP-Verwaltungsrichtlinie erstellen, bearbeiten oder löschen und Arbeitsdateien auf Android-oder IOS-Geräten schützen.
ms.openlocfilehash: 0d9e901cac94fe7692ffe705c6b0a51df2bc542f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627432"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a><span data-ttu-id="e47b7-103">Festlegen von App-Schutzeinstellungen für Android- oder iOS-Geräte</span><span class="sxs-lookup"><span data-stu-id="e47b7-103">Set app protection settings for Android or iOS devices</span></span>

![Banner, auf das https://aka.ms/aboutM365previewverwiesen wird.](../media/m365admincenterchanging.png)

## <a name="create-an-app-management-policy"></a><span data-ttu-id="e47b7-105">Erstellen einer App-Verwaltungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="e47b7-105">Create an app management policy</span></span>

1. <span data-ttu-id="e47b7-106">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="e47b7-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="e47b7-107">Wählen Sie im linken Navigationsbereich **Geräte** \> **Richtlinien** \> **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="e47b7-107">In the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
  
3. <span data-ttu-id="e47b7-108">Geben Sie im Bereich **Richtlinie hinzufügen** einen eindeutigen Namen für diese Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="e47b7-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="e47b7-109">Wählen Sie unter **Richtlinientyp**die Option **Anwendungsverwaltung für Android** oder **Anwendungsverwaltung für IOS**aus, je nachdem, welchen Richtliniensatz Sie erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="e47b7-109">Under **Policy type**, choose **Application Management for Android** or **Application Management for iOS**, depending on which set of policies you want to create.</span></span> 
    
5. <span data-ttu-id="e47b7-110">Erweitern Sie **Arbeitsdateien schützen, wenn Geräte verloren gehen oder gestohlen werden** , und verwalten Sie, **wie Benutzer auf mobilen Geräten auf Office-Dateien zugreifen**.</span><span class="sxs-lookup"><span data-stu-id="e47b7-110">Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices**.</span></span> <span data-ttu-id="e47b7-111">Konfigurieren Sie die Einstellungen, wie Sie möchten.</span><span class="sxs-lookup"><span data-stu-id="e47b7-111">Configure the settings how you would like.</span></span> <span data-ttu-id="e47b7-112">**Verwalten Sie, wie Benutzer auf Office-Dateien auf mobilen Geräten zugreifen** , standardmäßig **deaktiviert** , es wird jedoch empfohlen, dass Sie es **aktivieren und die** Standardwerte akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="e47b7-112">**Manage how users access Office files on mobile devices** is **Off** by default, but we recommend that you turn it **On** and accept the default values.</span></span> <span data-ttu-id="e47b7-113">Weitere Informationen finden Sie unter [Verfügbare Einstellungen](#available-settings).</span><span class="sxs-lookup"><span data-stu-id="e47b7-113">For more information, see [Available settings](#available-settings).</span></span> 
    
    <span data-ttu-id="e47b7-114">Mit dem Link **Standardeinstellungen zurücksetzen** können Sie jederzeit die Standardeinstellungen wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="e47b7-114">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Screenshot of Create a policy with Application management for Android selected](../media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. <span data-ttu-id="e47b7-116">Next decide **Who will get these settings?**</span><span class="sxs-lookup"><span data-stu-id="e47b7-116">Next decide **Who will get these settings?**</span></span> <span data-ttu-id="e47b7-117">Wenn Sie die standardmäßige Sicherheitsgruppe " **alle Benutzer** " nicht verwenden möchten, wählen Sie **ändern**aus, und wählen Sie \> die Sicherheitsgruppen aus, die **diese Einstellungen erhalten**.</span><span class="sxs-lookup"><span data-stu-id="e47b7-117">If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups that get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="e47b7-118">Wählen Sie schließlich **Fertig** aus, um die Richtlinie zu speichern, und weisen Sie sie Geräten zu.</span><span class="sxs-lookup"><span data-stu-id="e47b7-118">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="edit-an-app-management-policy"></a><span data-ttu-id="e47b7-119">Bearbeiten einer App-Verwaltungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="e47b7-119">Edit an app management policy</span></span>

1. <span data-ttu-id="e47b7-120">Wählen Sie auf der Karte **Richtlinien** die Option **Richtlinie bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="e47b7-120">On the **Policies** card, choose **Edit policy**.</span></span>
    
2. <span data-ttu-id="e47b7-121">Wählen Sie im Bereich **Richtlinie bearbeiten** die Richtlinie aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="e47b7-121">On the **Edit policy** pane, choose the policy you want to change</span></span> 
    
3. <span data-ttu-id="e47b7-122">Wählen Sie neben jeder Einstellung **Bearbeiten** aus, um die Werte in der Richtlinie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="e47b7-122">Choose **Edit** next to each setting to change the values in the policy.</span></span> <span data-ttu-id="e47b7-123">Wenn Sie einen Wert ändern, wird er automatisch in der Richtlinie gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e47b7-123">When you change a value, it's automatically saved in the policy.</span></span>
    
4. <span data-ttu-id="e47b7-124">Wenn Sie fertig sind, schließen Sie den Bereich **Richtlinie bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="e47b7-124">When you're finished, close the **Edit policy** pane.</span></span> 
    
## <a name="delete-an-app-management-policy"></a><span data-ttu-id="e47b7-125">Löschen einer App-Verwaltungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="e47b7-125">Delete an app management policy</span></span>

1. <span data-ttu-id="e47b7-126">Wählen Sie auf der Seite **Richtlinien** eine Richtlinie aus, und **Löschen**Sie dann.</span><span class="sxs-lookup"><span data-stu-id="e47b7-126">On the **Policies** page, choose a policy and then **Delete**.</span></span>
    
2. <span data-ttu-id="e47b7-127">Wählen Sie im Bereich **Richtlinie löschen** die Option **bestätigen** aus, um die ausgewählten Richtlinien zu löschen.</span><span class="sxs-lookup"><span data-stu-id="e47b7-127">On the **Delete policy** pane, choose **Confirm** to delete the policy or policies you chose.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="e47b7-128">Verfügbare Einstellungen</span><span class="sxs-lookup"><span data-stu-id="e47b7-128">Available settings</span></span>

<span data-ttu-id="e47b7-129">Die folgenden Tabellen enthalten ausführliche Informationen zu den verfügbaren Einstellungen zum Schutz von Arbeitsdateien auf Geräten und den Einstellungen, die Steuern, wie Benutzer auf Ihre mobilen Geräte auf Office-Dateien zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e47b7-129">The following tables give detailed information about settings available to protect work files on devices and the settings that control how users access Office files from their mobile devices.</span></span>
  
 <span data-ttu-id="e47b7-130">Weitere Informationen finden Sie unter [How do Protection Features in Microsoft 365 Business Premium zuordnen zu InTune-Einstellungen](map-protection-features-to-intune-settings.md).</span><span class="sxs-lookup"><span data-stu-id="e47b7-130">For more information, see [How do protection features in Microsoft 365 Business Premium map to Intune settings](map-protection-features-to-intune-settings.md).</span></span> 
  
### <a name="settings-that-protect-work-files"></a><span data-ttu-id="e47b7-131">Einstellungen zum Schutz von Arbeitsdateien</span><span class="sxs-lookup"><span data-stu-id="e47b7-131">Settings that protect work files</span></span>

<span data-ttu-id="e47b7-132">Die folgenden Einstellungen stehen zum Schutz von Arbeitsdateien zur Verfügung, wenn das Gerät eines Benutzers verloren geht oder gestohlen wird:</span><span class="sxs-lookup"><span data-stu-id="e47b7-132">The following settings are available to protect work files if a user's device is lost or stolen:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e47b7-133">Einstellung</span><span class="sxs-lookup"><span data-stu-id="e47b7-133">Setting</span></span>  <br/> |<span data-ttu-id="e47b7-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e47b7-134">Description</span></span>  <br/> |
|<span data-ttu-id="e47b7-135">Arbeitsdateien von einem inaktiven Gerät löschen nach diesem Zeitraum (Tage)</span><span class="sxs-lookup"><span data-stu-id="e47b7-135">Delete work files from an inactive device after this many days</span></span>  <br/> |<span data-ttu-id="e47b7-136">Wenn ein Gerät nicht für die Anzahl der Tage verwendet wird, die Sie hier angeben, werden alle auf dem Gerät gespeicherten Arbeitsdateien automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="e47b7-136">If a device isn't used for the number of days that you specify here, any work files stored on the device will be deleted automatically.</span></span>  <br/> |
|<span data-ttu-id="e47b7-137">Benutzer zum Speichern aller Arbeitsdateien auf OneDrive for Business zwingen</span><span class="sxs-lookup"><span data-stu-id="e47b7-137">Force users to save all work files to OneDrive for Business</span></span>  <br/> |<span data-ttu-id="e47b7-138">Wenn diese Einstellung **auf "ein**" festzulegen ist, ist der einzige verfügbare Speicherplatz für Arbeitsdateien OneDrive für Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="e47b7-138">If this setting is **On**, the only available save location for work files is OneDrive for Business.</span></span>  <br/> |
|<span data-ttu-id="e47b7-139">Arbeitsdateien verschlüsseln</span><span class="sxs-lookup"><span data-stu-id="e47b7-139">Encrypt work files</span></span>  <br/> |<span data-ttu-id="e47b7-140">Behalten Sie für diese Einstellung **Ein** bei, damit Arbeitsdateien durch Verschlüsselung geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="e47b7-140">Keep this setting **On** so that work files are protected by encryption.</span></span> <span data-ttu-id="e47b7-141">Selbst wenn das Gerät verloren geht oder gestohlen wird, kann niemand die Daten Ihres Unternehmens lesen.</span><span class="sxs-lookup"><span data-stu-id="e47b7-141">Even if the device is lost or stolen, no one can read your company data.</span></span>  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="e47b7-142">Einstellungen, die steuern, wie Benutzer auf mobilen Geräten auf Office-Dateien zugreifen</span><span class="sxs-lookup"><span data-stu-id="e47b7-142">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="e47b7-143">Mit den folgenden Einstellungen können Sie den Zugriff von Benutzern auf Office-Arbeitsdateien verwalten:</span><span class="sxs-lookup"><span data-stu-id="e47b7-143">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e47b7-144">Einstellung</span><span class="sxs-lookup"><span data-stu-id="e47b7-144">Setting</span></span>  <br/> |<span data-ttu-id="e47b7-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e47b7-145">Description</span></span>  <br/> |
|<span data-ttu-id="e47b7-146">Für den Zugriff auf Office-Apps PIN bzw. digitalen Fingerabdruck anfordern</span><span class="sxs-lookup"><span data-stu-id="e47b7-146">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="e47b7-147">Wenn diese Einstellung **auf** Benutzer muss eine andere Form der Authentifizierung neben Ihrem Benutzernamen und Kennwort bereitstellen, bevor Sie Office-Apps auf Ihren mobilen Geräten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="e47b7-147">If this setting is **On** users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile devices.</span></span><br/> |
|<span data-ttu-id="e47b7-148">PIN nach dieser Anzahl von fehlerhaften Anmeldeversuchen zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="e47b7-148">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="e47b7-149">Um zu verhindern, dass ein nicht autorisierter Benutzer eine PIN nach dem Zufallsprinzip errät, wird die PIN, die nach der angegebenen Anzahl von Fehlversuchen zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="e47b7-149">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="e47b7-150">Benutzer müssen sich erneut anmelden, nachdem Office-Apps im Leerlauf waren für</span><span class="sxs-lookup"><span data-stu-id="e47b7-150">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="e47b7-151">Diese Einstellung bestimmt, wie lange sich ein Benutzer im Leerlauf befinden kann, bevor er zur erneuten Anmeldung aufgefordert wird.</span><span class="sxs-lookup"><span data-stu-id="e47b7-151">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="e47b7-152">Zugriff auf Arbeitsdateien auf Geräten mit entfernten Nutzungsbeschränkungen verweigern</span><span class="sxs-lookup"><span data-stu-id="e47b7-152">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="e47b7-p105">Clevere Benutzer verfügen möglicherweise über ein Gerät, bei dem die Nutzungsbeschränkungen entfernt wurden. Dies bedeutet, dass der Benutzer das Betriebssystem ändern kann, wodurch das Gerät empfänglicher für Schadsoftware werden kann. Solche Geräte können gesperrt werden, wenn die Einstellung auf **Ein** festgelegt wurde.  </span><span class="sxs-lookup"><span data-stu-id="e47b7-p105">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="e47b7-156">Benutzer dürfen keine Inhalte aus Office-Apps in persönliche apps kopieren.</span><span class="sxs-lookup"><span data-stu-id="e47b7-156">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="e47b7-157">Dies ist standardmäßig zulässig, aber wenn die Einstellung **aktiviert**ist, kann der Benutzerinformationen in einer Arbeitsdatei in eine persönliche Datei kopieren.</span><span class="sxs-lookup"><span data-stu-id="e47b7-157">We do allow this by default, but if the setting is **On**, the user could copy information in a work file to a personal file.</span></span> <span data-ttu-id="e47b7-158">Wenn die Einstellung **deaktiviert**ist, kann der Benutzer keine Informationen aus einem Arbeitskonto in eine persönliche APP oder ein persönliches Konto kopieren.</span><span class="sxs-lookup"><span data-stu-id="e47b7-158">If the setting is **Off**, the user will be unable to copy information from a work account into a personal app or personal account.</span></span>  <br/> |
