---
title: Absichern von Windows 10-Geräten
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4WindowsConfig
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: 'Hier finden Sie Informationen zu Standard-und anderen Einstellungen zum Sichern von Windows 10-Geräten. '
ms.openlocfilehash: 9560bb4e299dba8f92d435a64670261b0e7e0290
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593443"
---
# <a name="secure-windows-10-devices"></a><span data-ttu-id="f307f-103">Absichern von Windows 10-Geräten</span><span class="sxs-lookup"><span data-stu-id="f307f-103">Secure Windows 10 devices</span></span>

<span data-ttu-id="f307f-104">[] Die Einstellungen, die Sie hier konfigurieren, sind Teil der standardmäßigen Geräterichtlinie für Windows 10.</span><span class="sxs-lookup"><span data-stu-id="f307f-104">The settings that you configure here are part of the default device policy for Windows 10.</span></span> <span data-ttu-id="f307f-105">Alle Benutzer, die ein Windows 10-Gerät, einschließlich mobiler Geräte und PCs, durch Anmeldung mit Ihrem Arbeitskonto verbinden, erhalten automatisch diese Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="f307f-105">All users who connect a Windows 10 device, including mobile devices and PCs, by signing in with their work account will automatically receive these settings.</span></span> <span data-ttu-id="f307f-106">Wir empfehlen, während des Setups die Standardrichtlinie zu übernehmen und später Richtlinien für bestimmte Benutzergruppen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="f307f-106">We recommend that you accept the default policy during setup and add policies later that target specific groups of users.</span></span>
  
## <a name="settings-to-secure-windows-10-devices"></a><span data-ttu-id="f307f-107">Einstellungen zum Absichern von Windows 10-Geräten</span><span class="sxs-lookup"><span data-stu-id="f307f-107">Settings to secure Windows 10 devices</span></span>

<span data-ttu-id="f307f-p102">Standardmäßig sind alle Einstellungen auf **Ein** festgelegt. Die folgenden Einstellungen stehen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="f307f-p102">By default all settings are **On**. The following settings are available:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f307f-110">Einstellung</span><span class="sxs-lookup"><span data-stu-id="f307f-110">Setting</span></span>  <br/> |<span data-ttu-id="f307f-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f307f-111">Description</span></span>  <br/> |
|<span data-ttu-id="f307f-112">PCs vor Viren und anderen Bedrohungen mithilfe von Windows Defender Antivirus schützen</span><span class="sxs-lookup"><span data-stu-id="f307f-112">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="f307f-113">Setzt voraus, dass Windows Defender Antivirus aktiviert ist, um PCs vor den Gefahren bei einer Verbindung mit dem Internet zu schützen.</span><span class="sxs-lookup"><span data-stu-id="f307f-113">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="f307f-114">PCs vor webbasierten Bedrohungen in Microsoft Edge schützen</span><span class="sxs-lookup"><span data-stu-id="f307f-114">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="f307f-115">Aktiviert Einstellungen in Edge, die Benutzer vor Websites und Downloads mit Schadsoftware schützen.</span><span class="sxs-lookup"><span data-stu-id="f307f-115">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="f307f-116">Bildschirm deaktivieren, wenn ein Gerät im Leerlauf ist seit dieser Zeitdauer</span><span class="sxs-lookup"><span data-stu-id="f307f-116">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="f307f-p103">Stellt sicher, dass die Unternehmensdaten bei Benutzerinaktivität geschützt sind. Vielleicht arbeitet ein Benutzer an einem Ort mit Publikumsverkehr, z. B. in einem Café, und entfernt sich von seinem Gerät oder ist nur einen Augenblick abgelenkt, wodurch das Gerät für zufällige Blicke anfällig ist. Mit dieser Einstellung können Sie steuern, wie lange der Benutzer inaktiv sein kann, bevor der Bildschirm abgeschaltet wird.</span><span class="sxs-lookup"><span data-stu-id="f307f-p103">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
|<span data-ttu-id="f307f-120">Benutzern den Download von Apps aus dem Microsoft Store erlauben</span><span class="sxs-lookup"><span data-stu-id="f307f-120">Allow users to download apps from Microsoft Store</span></span>  <br/> |<span data-ttu-id="f307f-p104">Ermöglicht es Benutzern, Apps aus dem Microsoft Store herunterzuladen und zu installieren. Weil Apps alles umfassen - von Spielen bis zu Produktivitätstools - behalten Sie für diese Einstellung **Ein** bei. Sie können sie aber auch deaktivieren, um die Sicherheit zu erhöhen.  </span><span class="sxs-lookup"><span data-stu-id="f307f-p104">Lets users download and install apps from the Microsoft Store. Apps include everything from games to productivity tools, so we leave this setting **On**, but you can turn it off for extra security.  </span></span><br/> |
|<span data-ttu-id="f307f-123">Benutzern den Zugriff auf Cortana erlauben</span><span class="sxs-lookup"><span data-stu-id="f307f-123">Allow users to access Cortana</span></span>  <br/> |<span data-ttu-id="f307f-124">Cortana kann sehr hilfreich sein!</span><span class="sxs-lookup"><span data-stu-id="f307f-124">Cortana can be very helpful!</span></span> <span data-ttu-id="f307f-125">Cortana kann Einstellungen für Sie aktivieren oder deaktivieren, Anweisungen geben und sicherstellen, dass Sie pünktlich für Termine sind, sodass diese Einstellung standardmäßig **aktiviert** bleibt.</span><span class="sxs-lookup"><span data-stu-id="f307f-125">Cortana can turn settings on or off for you, give directions, and make sure you're on time for appointments, so we keep this setting **On** by default.</span></span>  <br/> |
|<span data-ttu-id="f307f-126">Benutzern erlauben, Windows-Tipps und Werbung von Microsoft zu empfangen</span><span class="sxs-lookup"><span data-stu-id="f307f-126">Allow users to receive Windows tips and advertisements from Microsoft</span></span>  <br/> |<span data-ttu-id="f307f-127">Windows-Tipps können nützlich sein und Benutzern die Orientierung erleichtern, wenn neue Features veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="f307f-127">Windows tips can be handy and help orient users when new features are released.</span></span>  <br/> |
|<span data-ttu-id="f307f-128">Windows 10-Geräte automatisch auf dem neuesten Stand halten</span><span class="sxs-lookup"><span data-stu-id="f307f-128">Keep Windows 10 devices up to date automatically</span></span>  <br/> |<span data-ttu-id="f307f-129">Stellt sicher, dass Windows 10-Geräte die neuesten Updates automatisch erhalten.</span><span class="sxs-lookup"><span data-stu-id="f307f-129">Makes sure that Windows 10 devices automatically receive the latest updates.</span></span>  <br/> |
   

