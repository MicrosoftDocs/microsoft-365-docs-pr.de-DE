---
title: Festlegen von Anwendungsschutzeinstellungen für Windows 10-Geräte
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Informationen Sie zum Erstellen einer app Richtlinie zur Verwaltung und schützen Sie Arbeitsdateien auf Windows-10-Geräten.
ms.openlocfilehash: acf19a72d994185a35b2e425f8334a73a121ee10
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26867761"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="1b5ae-103">Festlegen von Anwendungsschutzeinstellungen für Windows 10-Geräte</span><span class="sxs-lookup"><span data-stu-id="1b5ae-103">Set application protection settings for Windows 10 devices</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="1b5ae-104">Erstellen einer App-Verwaltungsrichtlinie für Windows 10</span><span class="sxs-lookup"><span data-stu-id="1b5ae-104">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="1b5ae-105">Wenn Ihre Benutzer Arbeitsaufgaben auf ihren privaten Windows 10-Geräte ausführen, können Sie Ihre Daten auch auf diesen Geräten schützen.</span><span class="sxs-lookup"><span data-stu-id="1b5ae-105">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="1b5ae-p101">Melden Sie sich bei [Microsoft 365 Business](https://portal.office.com) mit globalen Administratoranmeldeinformationen an. Klicken Sie auf die Kachel **Admin**, um zum Admin Center zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="1b5ae-p101">Sign in to [Microsoft 365 Business](https://portal.office.com) with global admin credentials. Choose the **Admin** tile to go to the admin center.</span></span> 
    
2. <span data-ttu-id="1b5ae-108">Wählen Sie auf der Karte **Geräterichtlinien** des Admin-Portals **Richtlinie hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="1b5ae-108">On the **Device policies** card of the admin portal, choose **Add policy**.</span></span>
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. <span data-ttu-id="1b5ae-110">Geben Sie im Bereich **Richtlinie hinzufügen** einen eindeutigen Namen für diese Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="1b5ae-110">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="1b5ae-111">Wählen Sie unter **Richtlinientyp** die Option **Anwendungsverwaltung für Windows 10** aus.</span><span class="sxs-lookup"><span data-stu-id="1b5ae-111">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
    
5. <span data-ttu-id="1b5ae-112">Klicken Sie unter \*\* Gerätetyp \*\*, wählen Sie **Persönliche** oder **Unternehmen gehören**.</span><span class="sxs-lookup"><span data-stu-id="1b5ae-112">Under \*\* Device type \*\*, choose either **Personal** or **Company Owned**.</span></span>
    
6. <span data-ttu-id="1b5ae-113">Die Option **Arbeitsdateien verschlüsseln** wird automatisch aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1b5ae-113">The **Encrypt work files** is turned on automatically.</span></span> 
    
7. <span data-ttu-id="1b5ae-114">Aktivieren Sie die Optionen **Benutzer daran hindern, Unternehmensdaten in persönliche Dateien zu kopieren** und **Benutzer zum Speichern aller Arbeitsdateien auf OneDrive for Business zwingen**, wenn Sie nicht zulassen möchten, dass Benutzer Arbeitsdateien auf den eigenen PCs speichern.</span><span class="sxs-lookup"><span data-stu-id="1b5ae-114">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
    
8. <span data-ttu-id="1b5ae-p102">Erweitern Sie **den Zugriff von Benutzern auf Office-Dateien auf Geräten verwalten** \> konfigurieren Sie die Einstellungen wie möchten Sie. Der **Zugriff von Benutzern auf Office-Geräte auf mobilen Geräten verwalten** ist standardmäßig **deaktiviert** , aber es wird empfohlen, dass Sie **es aktivieren** , und übernehmen Sie die Standardwerte. Weitere Informationen finden Sie unter [Einstellungen verfügbar](protection-settings-for-windows-10-devices.md#bkmk_settings) .</span><span class="sxs-lookup"><span data-stu-id="1b5ae-p102">Expand **Manage how users access Office files on devices** \> configure the settings how you would like. The **Manage how users access Office devices on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values. See [Available settings](protection-settings-for-windows-10-devices.md#bkmk_settings) for more information.</span></span> 
    
    <span data-ttu-id="1b5ae-118">Mit dem Link **Standardeinstellungen zurücksetzen** können Sie jederzeit die Standardeinstellungen wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="1b5ae-118">You can always use the **Reset default settings** link to return to the default setting.</span></span> 
    
9. <span data-ttu-id="1b5ae-119">Erweitern Sie **Daten auf Windows-Geräten wiederherstellen**, und es wird empfohlen, die Option zu **aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="1b5ae-119">Expand **Recover data on Windows devices** and it is recommended that you turn it **On**.</span></span>
    
    <span data-ttu-id="1b5ae-p103">Bevor Sie zum Speicherort des Zertifikats des Datenwiederherstellungs-Agent navigieren können, müssen Sie zuerst ein Zertifikat erstellen. Anweisungen finden Sie unter [Erstellen und Überprüfen eines DRA-Zertifikats (Data Recovery Agent, Datenwiederherstellungs-Agent) des verschlüsselnden Dateisystems (Encrypting File System, EFS)](https://go.microsoft.com/fwlink/p/?linkid=853700).</span><span class="sxs-lookup"><span data-stu-id="1b5ae-p103">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one. For instructions see, [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700).</span></span>
    
    <span data-ttu-id="1b5ae-p104">Standardmäßig werden Arbeitsdateien mithilfe eines geheimen Schlüssels verschlüsselt, der auf dem Gerät gespeichert und mit dem Profil des Benutzers verknüpft ist. Nur der Benutzer kann die Datei öffnen und entschlüsseln. Wenn ein Gerät jedoch verloren geht oder ein Benutzers entfernt wird, kann eine Datei im verschlüsselten Zustand zurückbleiben. Das Zertifikat des Datenwiederherstellungs-Agents (DRA) kann von einem Administrator verwendet werden, um die Datei zu entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="1b5ae-p104">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile. Only the user can open and decrypt the file. However, if a device is lost or a user is removed, a file can be stuck in an encrypted state. The Data Recovery Agent (DRA) certificate can be used by an admin to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="1b5ae-p105">Erweitern Sie **Zusätzliche Netzwerk- und Cloudspeicherorte schützen**, wenn Sie weitere Domänen oder SharePoint Online-Speicherorte hinzufügen möchten, um sicherzustellen, dass Dateien in allen aufgelisteten Apps geschützt werden. Wenn Sie für eines der Felder mehr als ein Element eingeben müssen, verwenden Sie ein Semikolon (;) zwischen den Elementen.</span><span class="sxs-lookup"><span data-stu-id="1b5ae-p105">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps will be protected. If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span> 
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="1b5ae-p106">Als Nächstes entscheiden **erhalten, die diese Einstellungen?** Wenn Sie nicht die Standardsicherheitsgruppe für **Alle Benutzer** verwenden möchten, **Ändern**, wählen Sie die Sicherheitsgruppen, die diese Einstellungen erhalten \> **auswählen**.</span><span class="sxs-lookup"><span data-stu-id="1b5ae-p106">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
12. <span data-ttu-id="1b5ae-132">Wählen Sie schließlich **Hinzufügen** aus, um die Richtlinie zu speichern, und weisen Sie sie Geräten zu.</span><span class="sxs-lookup"><span data-stu-id="1b5ae-132">Finally, choose **Add** to save the policy, and assign it to devices.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="1b5ae-133">Verfügbare Einstellungen</span><span class="sxs-lookup"><span data-stu-id="1b5ae-133">Available settings</span></span>

<span data-ttu-id="1b5ae-134">Mit den folgenden Einstellungen können Sie den Zugriff von Benutzern auf Office-Arbeitsdateien verwalten.</span><span class="sxs-lookup"><span data-stu-id="1b5ae-134">The following settings are available to manage how users access Office work files.</span></span>
  
<span data-ttu-id="1b5ae-135">Weitere Informationen finden Sie unter [Zuordnung von Microsoft 365 Business-Schutzfunktionen zu Intune-Einstellungen](map-protection-features-to-intune-settings.md).</span><span class="sxs-lookup"><span data-stu-id="1b5ae-135">For more information, see [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md).</span></span>
  
|<span data-ttu-id="1b5ae-136">**Einstellung**</span><span class="sxs-lookup"><span data-stu-id="1b5ae-136">**Setting**</span></span>|<span data-ttu-id="1b5ae-137">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="1b5ae-137">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1b5ae-138">Für den Zugriff auf Office-Apps PIN bzw. digitalen Fingerabdruck anfordern</span><span class="sxs-lookup"><span data-stu-id="1b5ae-138">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="1b5ae-139">Ist diese Einstellung **aktiviert**, müssen Benutzer zusätzlich zum Benutzernamen und Kennwort eine andere Form der Authentifizierung angeben, bevor sie Office-Apps auf ihren mobilen Geräten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="1b5ae-139">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="1b5ae-140">PIN nach dieser Anzahl von fehlerhaften Anmeldeversuchen zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="1b5ae-140">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="1b5ae-141">Um zu verhindern, dass ein nicht autorisierter Benutzer eine PIN nach dem Zufallsprinzip errät, wird die PIN, die nach der angegebenen Anzahl von Fehlversuchen zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="1b5ae-141">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="1b5ae-142">Benutzer müssen sich erneut anmelden, nachdem Office-Apps im Leerlauf waren für</span><span class="sxs-lookup"><span data-stu-id="1b5ae-142">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="1b5ae-143">Diese Einstellung bestimmt, wie lange ein Benutzer inaktiv sein kann, bevor er dazu aufgefordert wird, sich erneut anzumelden.</span><span class="sxs-lookup"><span data-stu-id="1b5ae-143">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
   

