---
title: Absichern von Windows 10-Geräten
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- O365E_BCSSetup4WindowsConfig
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
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: 'Informationen Sie zu standardmäßigen und andere Einstellungen zum Sichern der Windows-10-Geräte. '
ms.openlocfilehash: 0bdf6a56d880cb84f4a4f50550539d97c006ba49
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868117"
---
# <a name="secure-windows-10-devices"></a><span data-ttu-id="ab81d-103">Absichern von Windows 10-Geräten</span><span class="sxs-lookup"><span data-stu-id="ab81d-103">Secure Windows 10 devices</span></span>

<span data-ttu-id="ab81d-p101">[] Die Einstellungen, die Sie hier konfigurieren, sind Teil der standardmäßigen Geräterichtlinie für Windows 10. Allen Benutzer, die die Verbindung mit einem Windows 10-Gerät herstellen (einschließlich mobilen Geräte und PCs), indem sie sich mit ihrem Geschäftskonto anmelden, werden diese Einstellungen automatisch zugewiesen. Wir empfehlen, während des Setups die Standardrichtlinie zu übernehmen und später Richtlinien für bestimmte Benutzergruppen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ab81d-p101">The settings that you configure here are part of the default device policy for Windows 10. All users that connect a Windows 10 device, including mobile devices and PCs, by signing in with their work account, will automatically receive these settings. We recommend that you accept the default policy during setup and add policies later that target specific groups of users.</span></span>
  
## <a name="settings-to-secure-windows-10-devices"></a><span data-ttu-id="ab81d-107">Einstellungen zum Absichern von Windows 10-Geräten</span><span class="sxs-lookup"><span data-stu-id="ab81d-107">Settings to secure Windows 10 devices</span></span>

<span data-ttu-id="ab81d-p102">Standardmäßig sind alle Einstellungen auf **Ein** festgelegt. Die folgenden Einstellungen stehen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="ab81d-p102">By default all settings are **On**. The following settings are available:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ab81d-110">Einstellung</span><span class="sxs-lookup"><span data-stu-id="ab81d-110">Setting</span></span>  <br/> |<span data-ttu-id="ab81d-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ab81d-111">Description</span></span>  <br/> |
|<span data-ttu-id="ab81d-112">PCs vor Viren und anderen Bedrohungen mithilfe von Windows Defender Antivirus schützen</span><span class="sxs-lookup"><span data-stu-id="ab81d-112">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="ab81d-113">Setzt voraus, dass Windows Defender Antivirus aktiviert ist, um PCs vor den Gefahren bei einer Verbindung mit dem Internet zu schützen.</span><span class="sxs-lookup"><span data-stu-id="ab81d-113">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="ab81d-114">PCs vor webbasierten Bedrohungen in Microsoft Edge schützen</span><span class="sxs-lookup"><span data-stu-id="ab81d-114">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="ab81d-115">Aktiviert Einstellungen in Edge, die Benutzer vor Websites und Downloads mit Schadsoftware schützen.</span><span class="sxs-lookup"><span data-stu-id="ab81d-115">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="ab81d-116">Bildschirm deaktivieren, wenn ein Gerät im Leerlauf ist seit dieser Zeitdauer</span><span class="sxs-lookup"><span data-stu-id="ab81d-116">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="ab81d-p103">Stellt sicher, dass die Unternehmensdaten bei Benutzerinaktivität geschützt sind. Vielleicht arbeitet ein Benutzer an einem Ort mit Publikumsverkehr, z. B. in einem Café, und entfernt sich von seinem Gerät oder ist nur einen Augenblick abgelenkt, wodurch das Gerät für zufällige Blicke anfällig ist. Mit dieser Einstellung können Sie steuern, wie lange der Benutzer inaktiv sein kann, bevor der Bildschirm abgeschaltet wird.</span><span class="sxs-lookup"><span data-stu-id="ab81d-p103">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
|<span data-ttu-id="ab81d-120">Benutzern den Download von Apps aus dem Microsoft Store erlauben</span><span class="sxs-lookup"><span data-stu-id="ab81d-120">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="ab81d-p104">Ermöglicht es Benutzern, Apps aus dem Microsoft Store herunterzuladen und zu installieren. Weil Apps alles umfassen - von Spielen bis zu Produktivitätstools - behalten Sie für diese Einstellung **Ein** bei. Sie können sie aber auch deaktivieren, um die Sicherheit zu erhöhen.  </span><span class="sxs-lookup"><span data-stu-id="ab81d-p104">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|<span data-ttu-id="ab81d-123">Benutzern den Zugriff auf Cortana erlauben</span><span class="sxs-lookup"><span data-stu-id="ab81d-123">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="ab81d-p105">Cortana kann sehr hilfreich sein! Sie kann Einstellungen automatisch aktivieren oder deaktivieren, Wegbeschreibungen liefern und sicherstellen, dass Sie Ihre Termine einhalten. Deshalb ist diese Einstellung standardmäßig auf **Ein** festgelegt.  </span><span class="sxs-lookup"><span data-stu-id="ab81d-p105">Cortana can be very helpful! She can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this **On** by default.  </span></span><br/> |
|<span data-ttu-id="ab81d-126">Benutzern erlauben, Windows-Tipps und Werbung von Microsoft zu empfangen</span><span class="sxs-lookup"><span data-stu-id="ab81d-126">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="ab81d-127">Windows-Tipps können nützlich sein und Benutzern die Orientierung erleichtern, wenn neue Features veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="ab81d-127">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="ab81d-128">Windows 10-Geräte automatisch auf dem neuesten Stand halten</span><span class="sxs-lookup"><span data-stu-id="ab81d-128">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="ab81d-129">Stellt sicher, dass Windows 10-Geräte die neuesten Updates automatisch erhalten.</span><span class="sxs-lookup"><span data-stu-id="ab81d-129">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
   

