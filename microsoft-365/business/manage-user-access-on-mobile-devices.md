---
title: Den Benutzerzugriff auf Office-Dokumente auf mobilen Geräten verwalten
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- 'O365E_BCSSetup4OfficeMobile '
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: Informationen Sie zu Richtlinien, die sicheren Zugriff von mobilen Geräten für apps für Office helfen kann.
ms.openlocfilehash: fe6cd9aa4dada0bba68180968a7b9687be0f0140
ms.sourcegitcommit: 25fec94d85afcd4dca585fd6ebce5d364ebe41c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2018
ms.locfileid: "25607790"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="234a4-103">Den Benutzerzugriff auf Office-Dokumente auf mobilen Geräten verwalten</span><span class="sxs-lookup"><span data-stu-id="234a4-103">Manage how users access Office documents on mobile devices</span></span>

 <span data-ttu-id="234a4-p101">[] Richtlinieneinstellungen zum Steuern, wie Benutzer mit ihren mobilen Geräten auf Office-Dateien zugreifen können, sind standardmäßig auf **Aus** eingestellt. Wir empfehlen, während des Setups die Standardwerte zu übernehmen, um Anwendungsrichtlinien für Android, iOS und Windows 10 zu erstellen, die für alle Benutzer gelten. Nach Abschluss des Setups können Sie weitere Richtlinien erstellen.</span><span class="sxs-lookup"><span data-stu-id="234a4-p101">Policy settings that control how users access Office files from their mobile devices are **Off** by default. We recommend you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users. You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="234a4-107">Einstellungen, die steuern, wie Benutzer auf mobilen Geräten auf Office-Dateien zugreifen</span><span class="sxs-lookup"><span data-stu-id="234a4-107">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="234a4-108">Mit den folgenden Einstellungen können Sie den Zugriff von Benutzern auf Office-Arbeitsdateien verwalten:</span><span class="sxs-lookup"><span data-stu-id="234a4-108">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="234a4-109">Einstellung</span><span class="sxs-lookup"><span data-stu-id="234a4-109">Setting</span></span>  <br/> |<span data-ttu-id="234a4-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="234a4-110">Description</span></span>  <br/> |
|<span data-ttu-id="234a4-111">Für den Zugriff auf Office-Apps PIN bzw. digitalen Fingerabdruck anfordern</span><span class="sxs-lookup"><span data-stu-id="234a4-111">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="234a4-112">Ist diese Einstellung **aktiviert**, müssen Benutzer zusätzlich zum Benutzernamen und Kennwort eine andere Form der Authentifizierung angeben, bevor sie Office-Apps auf ihren mobilen Geräten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="234a4-112">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="234a4-113">PIN nach dieser Anzahl von fehlerhaften Anmeldeversuchen zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="234a4-113">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="234a4-114">Um zu verhindern, dass ein nicht autorisierter Benutzer eine PIN nach dem Zufallsprinzip errät, wird die PIN, die nach der angegebenen Anzahl von Fehlversuchen zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="234a4-114">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="234a4-115">Benutzer müssen sich erneut anmelden, nachdem Office-Apps im Leerlauf waren für</span><span class="sxs-lookup"><span data-stu-id="234a4-115">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="234a4-116">Diese Einstellung bestimmt, wie lange ein Benutzer inaktiv sein kann, bevor er dazu aufgefordert wird, sich erneut anzumelden.</span><span class="sxs-lookup"><span data-stu-id="234a4-116">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="234a4-117">Zugriff auf Arbeitsdateien auf Geräten mit entfernten Nutzungsbeschränkungen verweigern</span><span class="sxs-lookup"><span data-stu-id="234a4-117">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="234a4-p102">Clevere Benutzer verfügen möglicherweise über ein Gerät, bei dem die Nutzungsbeschränkungen entfernt wurden. Dies bedeutet, dass der Benutzer das Betriebssystem ändern kann, wodurch das Gerät empfänglicher für Schadsoftware werden kann. Solche Geräte können gesperrt werden, wenn die Einstellung auf **Ein** festgelegt wurde.  </span><span class="sxs-lookup"><span data-stu-id="234a4-p102">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="234a4-121">Benutzern das Kopieren von Inhalten aus Office-Apps in persönliche Apps erlauben</span><span class="sxs-lookup"><span data-stu-id="234a4-121">Allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="234a4-p103">Dies ist standardmäßig zulässig. Wenn aber die Einstellung auf **Ein** festgelegt wird, kann der Benutzer die in einer Arbeitsdatei gespeicherten Informationen in eine persönliche Datei kopieren. Wenn die Einstellung auf **Aus** festgelegt ist, kann der Benutzer keine Informationen aus einer Arbeitsdatei in eine private App oder auf ein privates Konto kopieren.  </span><span class="sxs-lookup"><span data-stu-id="234a4-p103">We allow this by default, but when the setting is **On**, the user can copy information in a work file to a personal file. If the setting is **Off**, the user can't copy information from a work file to a personal app or personal account.  </span></span><br/> |
   

