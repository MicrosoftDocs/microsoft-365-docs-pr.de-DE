---
title: Festlegen von Geräteschutzeinstellungen für Windows 10-PCs
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
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: bd66c26c-73a4-45a8-8642-3ea4ee7cd89d
description: Erfahren Sie mehr über die standardmäßigen und anderen Einstellungen, die in Microsoft 365 Business zum Sichern von Windows 10-Geräten verfügbar sind.
ms.openlocfilehash: 844bddc4b93c7dc543ad6c6a79f5cf92c96ceff0
ms.sourcegitcommit: 0c1227dc79b66bab529bf178c5672791369ba471
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "35630607"
---
# <a name="set-device-protection-settings-for-windows-10-pcs"></a><span data-ttu-id="2ab2f-103">Festlegen von Geräteschutzeinstellungen für Windows 10-PCs</span><span class="sxs-lookup"><span data-stu-id="2ab2f-103">Set device protection settings for Windows 10 PCs</span></span>

## <a name="secure-windows-10-devices"></a><span data-ttu-id="2ab2f-104">Absichern von Windows 10-Geräten</span><span class="sxs-lookup"><span data-stu-id="2ab2f-104">Secure Windows 10 devices</span></span>

<span data-ttu-id="2ab2f-105">Schauen Sie sich ein Video mit Informationen zum Sichern von Windows 10-Geräten mit Microsoft 365 Business an:</span><span class="sxs-lookup"><span data-stu-id="2ab2f-105">View a video on how to secure Windows 10 devices with Microsoft 365 Business:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/a5734146-620a-4cec-8618-536b3ca37972?autoplay=false]
  
1. <span data-ttu-id="2ab2f-106">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="2ab2f-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="2ab2f-107">Wählen Sie im linken Navigationsbereich **Geräte** \> **Richtlinien** \> **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="2ab2f-107">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
  
3. <span data-ttu-id="2ab2f-108">Geben Sie im Bereich **Richtlinie hinzufügen** einen eindeutigen Namen für diese Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="2ab2f-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="2ab2f-109">Wählen Sie unter **Richtlinientyp** die Option **Windows 10-Gerätekonfiguration** aus.</span><span class="sxs-lookup"><span data-stu-id="2ab2f-109">Under **Policy type**, choose **Windows 10 Device Configuration**.</span></span>
    
5. <span data-ttu-id="2ab2f-p101">Expand **Secure Windows 10 Devices** \> configure the settings how you would like. See [Available settings](#available-settings) for more information.</span><span class="sxs-lookup"><span data-stu-id="2ab2f-p101">Expand **Secure Windows 10 Devices** \> configure the settings how you would like. See [Available settings](#available-settings) for more information.</span></span> 
    
    <span data-ttu-id="2ab2f-112">Über den Link **Standardeinstellungen zurücksetzen** können Sie die Standardeinstellung jederzeit wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="2ab2f-112">You can alway use the **Reset default settings** link to return to the default setting.</span></span> 
    
    ![Add policy pane with Windows 10 Device configuration selected](media/fa9e2dc2-7eae-4c96-af34-765a1f641ecf.png)
  
6. <span data-ttu-id="2ab2f-p102">Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.</span><span class="sxs-lookup"><span data-stu-id="2ab2f-p102">Next decide **Who will get these settings?** If you don't want to use the default **All users** security group, Choose **Change**, search for the security group who will get these settings \> **Select**.</span></span>
    
7. <span data-ttu-id="2ab2f-116">Wählen Sie schließlich **Fertig** aus, um die Richtlinie zu speichern, und weisen Sie sie Geräten zu.</span><span class="sxs-lookup"><span data-stu-id="2ab2f-116">Finally, choose **Done** to save the policy, and assign it to devices.</span></span> 
    
## <a name="available-settings"></a><span data-ttu-id="2ab2f-117">Verfügbare Einstellungen</span><span class="sxs-lookup"><span data-stu-id="2ab2f-117">Available settings</span></span>

<span data-ttu-id="2ab2f-p103">Standardmäßig sind alle Einstellungen auf **Ein** festgelegt. Die folgenden Einstellungen stehen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="2ab2f-p103">By default all settings are **On**. The following settings are available.</span></span>
  
<span data-ttu-id="2ab2f-120">Weitere Informationen finden Sie unter [Zuordnung von Microsoft 365 Business-Schutzfunktionen zu Intune-Einstellungen](map-protection-features-to-intune-settings.md).</span><span class="sxs-lookup"><span data-stu-id="2ab2f-120">See [How do protection features in Microsoft 365 Business map to Intune settings](map-protection-features-to-intune-settings.md) for more information.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2ab2f-121">Einstellung</span><span class="sxs-lookup"><span data-stu-id="2ab2f-121">Setting</span></span>  <br/> |<span data-ttu-id="2ab2f-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2ab2f-122">Description</span></span>  <br/> |
|<span data-ttu-id="2ab2f-123">PCs vor Viren und anderen Bedrohungen mithilfe von Windows Defender Antivirus schützen</span><span class="sxs-lookup"><span data-stu-id="2ab2f-123">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="2ab2f-124">Setzt voraus, dass Windows Defender Antivirus aktiviert ist, um PCs vor den Gefahren bei einer Verbindung mit dem Internet zu schützen.</span><span class="sxs-lookup"><span data-stu-id="2ab2f-124">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="2ab2f-125">PCs vor webbasierten Bedrohungen in Microsoft Edge schützen</span><span class="sxs-lookup"><span data-stu-id="2ab2f-125">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="2ab2f-126">Aktiviert Einstellungen in Edge, die Benutzer vor Websites und Downloads mit Schadsoftware schützen.</span><span class="sxs-lookup"><span data-stu-id="2ab2f-126">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="2ab2f-127">Regeln verwenden, die die Angriffsfläche von Geräten verringern</span><span class="sxs-lookup"><span data-stu-id="2ab2f-127">Use rules that reduce the attack surface of devices</span></span>  <br/> |<span data-ttu-id="2ab2f-p104">Wenn diese Option aktiviert ist, hilft die Reduzierung der Angriffsfläche, Aktionen und Apps zu blockieren, die häufig von Schadsoftware zum Infizieren von Geräten verwendet werden. Diese Einstellung ist nur verfügbar, wenn Windows Defender Antivirus aktiviert ist. Weitere Informationen finden Sie unter [Verringern der Angriffsfläche](https://go.microsoft.com/fwlink/?linkid=870417).  </span><span class="sxs-lookup"><span data-stu-id="2ab2f-p104">When turned On, attack surface reduction helps block actions and apps typically used by malware to infect devices. This setting is only available if Windows Defender Antivirus is set to On. See [Reduce attack surfaces](https://go.microsoft.com/fwlink/?linkid=870417) to learn more.  </span></span><br/> |
|<span data-ttu-id="2ab2f-131">Ordner vor Bedrohungen wie Ransomware schützen</span><span class="sxs-lookup"><span data-stu-id="2ab2f-131">Protect folders from threats such as ransomware</span></span>  <br/> |<span data-ttu-id="2ab2f-p105">Diese Einstellung verwendet kontrollierten Ordnerzugriff zum Schutz von Unternehmensdaten vor Änderungen durch verdächtige oder böswillige apps, z. B. Ransomware. Diese Arten von Apps werden daran gehindert, Änderungen in geschützten Ordnern vorzunehmen. Diese Einstellung ist nur verfügbar, wenn Windows Defender Antivirus aktiviert ist. Weitere Informationen finden Sie unter [Schützen von Ordnern durch kontrollierten Ordnerzugriff](https://go.microsoft.com/fwlink/?linkid=870418).  </span><span class="sxs-lookup"><span data-stu-id="2ab2f-p105">This setting uses controlled folder access to protect company data from modification by suspicious or malicious apps, such as ransomware. These types of apps are blocked from making changes in protected folders. This setting is only available if Windows Defender Antivirus is set to On. See [Protect folders with COntrolled folder access](https://go.microsoft.com/fwlink/?linkid=870418) to learn more.  </span></span><br/> |
|<span data-ttu-id="2ab2f-136">Netzwerkzugriff auf potenziell schädliche Inhalte im Internet verhindern</span><span class="sxs-lookup"><span data-stu-id="2ab2f-136">Prevent network access to potentially malicious content on the Internet</span></span>  <br/> |<span data-ttu-id="2ab2f-p106">Mithilfe dieser Einstellung können Sie ausgehende Benutzerverbindungen zu nicht vertrauenswürdigen Internetseiten blockieren, die Phishing-Betrügereien, Exploits oder andere schädliche Inhalte enthalten können. Diese Einstellung ist nur verfügbar, wenn Windows Defender Antivirus aktiviert ist. Weitere Informationen finden Sie unter [Schützen Sie Ihr Netzwerk](https://go.microsoft.com/fwlink/?linkid=870419).  </span><span class="sxs-lookup"><span data-stu-id="2ab2f-p106">Use this setting to block outbound user connections to low-reputation Internet locations that may host phishing scams, exploits or other malicious content. This setting is only available if Windows Defender Antivirus is set to On. See [Protect your network](https://go.microsoft.com/fwlink/?linkid=870419) for more information.  </span></span><br/> |
|<span data-ttu-id="2ab2f-140">Dateien und Ordner auf PCs mit BitLocker vor unbefugtem Zugriff schützen</span><span class="sxs-lookup"><span data-stu-id="2ab2f-140">Help protect files and folders on PCs from unauthorized access with BitLocker</span></span>  <br/> |<span data-ttu-id="2ab2f-p107">BitLocker schützt Daten durch Verschlüsselung der Computerfestplatten und bietet Schutz vor Datenverlusten, falls ein Computer verloren geht oder gestohlen wird. Weitere Informationen finden Sie unter [Häufig gestellte Fragen zu Bitlocker](https://go.microsoft.com/fwlink/?linkid=871000).  </span><span class="sxs-lookup"><span data-stu-id="2ab2f-p107">Bitlocker protects data by encrypting the computer hard drives and protect against data exposure if a computer is lost or stolen. See [Bitlocker FAQ](https://go.microsoft.com/fwlink/?linkid=871000) for more information.  </span></span><br/> |
|<span data-ttu-id="2ab2f-143">Benutzern den Download von Apps aus dem Microsoft Store erlauben</span><span class="sxs-lookup"><span data-stu-id="2ab2f-143">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="2ab2f-p108">Ermöglicht es Benutzern, Apps aus dem Microsoft Store herunterzuladen und zu installieren. Weil Apps alles umfassen - von Spielen bis zu Produktivitätstools - behalten Sie für diese Einstellung **Ein** bei. Sie können sie aber auch deaktivieren, um die Sicherheit zu erhöhen.  </span><span class="sxs-lookup"><span data-stu-id="2ab2f-p108">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|<span data-ttu-id="2ab2f-146">Benutzern den Zugriff auf Cortana erlauben</span><span class="sxs-lookup"><span data-stu-id="2ab2f-146">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="2ab2f-p109">Cortana kann sehr hilfreich sein! Sie kann Einstellungen automatisch aktivieren oder deaktivieren, Wegbeschreibungen liefern und sicherstellen, dass Sie Ihre Termine einhalten. Deshalb ist diese Einstellung standardmäßig auf **Ein** festgelegt.  </span><span class="sxs-lookup"><span data-stu-id="2ab2f-p109">Cortana can be very helpful! She can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this **On** by default.  </span></span><br/> |
|<span data-ttu-id="2ab2f-149">Benutzern erlauben, Windows-Tipps und Werbung von Microsoft zu empfangen</span><span class="sxs-lookup"><span data-stu-id="2ab2f-149">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="2ab2f-150">Windows-Tipps können nützlich sein und Benutzern die Orientierung erleichtern, wenn neue Features veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="2ab2f-150">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="2ab2f-151">Windows 10-Geräte automatisch auf dem neuesten Stand halten</span><span class="sxs-lookup"><span data-stu-id="2ab2f-151">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="2ab2f-152">Stellt sicher, dass Windows 10-Geräte die neuesten Updates automatisch erhalten.</span><span class="sxs-lookup"><span data-stu-id="2ab2f-152">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
|<span data-ttu-id="2ab2f-153">Bildschirm deaktivieren, wenn ein Gerät im Leerlauf ist seit dieser Zeitdauer</span><span class="sxs-lookup"><span data-stu-id="2ab2f-153">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="2ab2f-p110">Stellt sicher, dass die Unternehmensdaten bei Benutzerinaktivität geschützt sind. Vielleicht arbeitet ein Benutzer an einem Ort mit Publikumsverkehr, z. B. in einem Café, und entfernt sich von seinem Gerät oder ist nur einen Augenblick abgelenkt, wodurch das Gerät für zufällige Blicke anfällig ist. Mit dieser Einstellung können Sie steuern, wie lange der Benutzer inaktiv sein kann, bevor der Bildschirm abgeschaltet wird.</span><span class="sxs-lookup"><span data-stu-id="2ab2f-p110">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
   
  

