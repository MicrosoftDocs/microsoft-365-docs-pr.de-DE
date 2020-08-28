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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: In diesem Artikel erfahren Sie, wie Sie die Einstellungen für die Standardgeräterichtlinie konfigurieren, die jedes Windows 10-Gerät beim Anmelden bei Ihrem Arbeits-oder Schulkonto erhält.
ms.openlocfilehash: 85448507835b6310ca4136849be6a40caf6bb919
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289075"
---
# <a name="secure-windows-10-devices"></a><span data-ttu-id="6d2ee-103">Absichern von Windows 10-Geräten</span><span class="sxs-lookup"><span data-stu-id="6d2ee-103">Secure Windows 10 devices</span></span>

<span data-ttu-id="6d2ee-104">Dieser Artikel bezieht sich auf Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="6d2ee-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="6d2ee-105">[] Die Einstellungen, die Sie hier konfigurieren, sind Teil der standardmäßigen Geräterichtlinie für Windows 10.</span><span class="sxs-lookup"><span data-stu-id="6d2ee-105">The settings that you configure here are part of the default device policy for Windows 10.</span></span> <span data-ttu-id="6d2ee-106">Alle Benutzer, die ein Windows 10-Gerät, einschließlich mobiler Geräte und PCs, durch Anmeldung mit Ihrem Arbeitskonto verbinden, erhalten automatisch diese Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="6d2ee-106">All users who connect a Windows 10 device, including mobile devices and PCs, by signing in with their work account will automatically receive these settings.</span></span> <span data-ttu-id="6d2ee-107">Wir empfehlen, während des Setups die Standardrichtlinie zu übernehmen und später Richtlinien für bestimmte Benutzergruppen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="6d2ee-107">We recommend that you accept the default policy during setup and add policies later that target specific groups of users.</span></span>
  
## <a name="settings-to-secure-windows-10-devices"></a><span data-ttu-id="6d2ee-108">Einstellungen zum Absichern von Windows 10-Geräten</span><span class="sxs-lookup"><span data-stu-id="6d2ee-108">Settings to secure Windows 10 devices</span></span>

<span data-ttu-id="6d2ee-p102">Standardmäßig sind alle Einstellungen auf **Ein** festgelegt. Die folgenden Einstellungen stehen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="6d2ee-p102">By default all settings are **On**. The following settings are available:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6d2ee-111">Einstellung</span><span class="sxs-lookup"><span data-stu-id="6d2ee-111">Setting</span></span>  <br/> |<span data-ttu-id="6d2ee-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6d2ee-112">Description</span></span>  <br/> |
|<span data-ttu-id="6d2ee-113">PCs vor Viren und anderen Bedrohungen mithilfe von Windows Defender Antivirus schützen</span><span class="sxs-lookup"><span data-stu-id="6d2ee-113">Help protect PCs from viruses and other threats using Windows Defender Antivirus</span></span>  <br/> |<span data-ttu-id="6d2ee-114">Setzt voraus, dass Windows Defender Antivirus aktiviert ist, um PCs vor den Gefahren bei einer Verbindung mit dem Internet zu schützen.</span><span class="sxs-lookup"><span data-stu-id="6d2ee-114">Requires that Windows Defender Antivirus is turned on to protect PCs from the dangers of being connected to the internet.</span></span>  <br/> |
|<span data-ttu-id="6d2ee-115">PCs vor webbasierten Bedrohungen in Microsoft Edge schützen</span><span class="sxs-lookup"><span data-stu-id="6d2ee-115">Help protect PCs from web-based threats in Microsoft Edge</span></span>  <br/> |<span data-ttu-id="6d2ee-116">Aktiviert Einstellungen in Edge, die Benutzer vor Websites und Downloads mit Schadsoftware schützen.</span><span class="sxs-lookup"><span data-stu-id="6d2ee-116">Turns on settings in Edge that help protect users from malicious sites and downloads.</span></span>  <br/> |
|<span data-ttu-id="6d2ee-117">Dateien und Ordner auf PCs mit BitLocker vor unbefugtem Zugriff schützen</span><span class="sxs-lookup"><span data-stu-id="6d2ee-117">Help protect files and folders on PCs from unauthorized access with BitLocker</span></span>  <br/> |<span data-ttu-id="6d2ee-118">BitLocker schützt Daten durch Verschlüsselung der Computerfestplatten und bietet Schutz vor Datenverlusten, falls ein Computer verloren geht oder gestohlen wird.</span><span class="sxs-lookup"><span data-stu-id="6d2ee-118">Bitlocker protects data by encrypting the computer hard drives and protect against data exposure if a computer is lost or stolen.</span></span> <span data-ttu-id="6d2ee-119">Weitere Informationen finden Sie unter [häufig gestellte Fragen zu BitLocker](https://go.microsoft.com/fwlink/?linkid=871000).</span><span class="sxs-lookup"><span data-stu-id="6d2ee-119">For more information, see [Bitlocker FAQ](https://go.microsoft.com/fwlink/?linkid=871000).</span></span>  <br/> |
|<span data-ttu-id="6d2ee-120">Bildschirm deaktivieren, wenn ein Gerät im Leerlauf ist seit dieser Zeitdauer</span><span class="sxs-lookup"><span data-stu-id="6d2ee-120">Turn off device screen when idle for this amount of time</span></span>  <br/> |<span data-ttu-id="6d2ee-p104">Stellt sicher, dass die Unternehmensdaten bei Benutzerinaktivität geschützt sind. Vielleicht arbeitet ein Benutzer an einem Ort mit Publikumsverkehr, z. B. in einem Café, und entfernt sich von seinem Gerät oder ist nur einen Augenblick abgelenkt, wodurch das Gerät für zufällige Blicke anfällig ist. Mit dieser Einstellung können Sie steuern, wie lange der Benutzer inaktiv sein kann, bevor der Bildschirm abgeschaltet wird.</span><span class="sxs-lookup"><span data-stu-id="6d2ee-p104">Makes sure that company data is protected if a user is idle. A user may be working in a public location, like a coffee shop, and step away or be distracted for just a moment, leaving their device vulnerable to random glances. This setting lets you control how long the user can be idle before the screen shuts off.</span></span>  <br/> |
|