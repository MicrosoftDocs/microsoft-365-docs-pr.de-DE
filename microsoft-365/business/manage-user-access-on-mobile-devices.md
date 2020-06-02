---
title: Den Benutzerzugriff auf Office-Dokumente auf mobilen Geräten verwalten
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4OfficeMobile
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: Erfahren Sie mehr über Schutzrichtlinien, mit denen Sie steuern können, wie Benutzer auf mobilen Geräten auf Office-Apps und Arbeitsdateien zugreifen.
ms.openlocfilehash: b2b828cf2e201360f12b8fadcb395e72958230f6
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2020
ms.locfileid: "44471065"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="a876d-103">Den Benutzerzugriff auf Office-Dokumente auf mobilen Geräten verwalten</span><span class="sxs-lookup"><span data-stu-id="a876d-103">Manage how users access Office documents on mobile devices</span></span>

<span data-ttu-id="a876d-104">Dieser Artikel bezieht sich auf Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="a876d-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="a876d-105">[] Richtlinieneinstellungen zum Steuern, wie Benutzer mit ihren mobilen Geräten auf Office-Dateien zugreifen können, sind standardmäßig auf **Aus** eingestellt.</span><span class="sxs-lookup"><span data-stu-id="a876d-105">Policy settings that control how users access Office files from their mobile devices are **Off** by default.</span></span> <span data-ttu-id="a876d-106">Es wird empfohlen, während des Setups die Standardwerte zu übernehmen, um Anwendungsrichtlinien für Android, IOS und Windows 10 zu erstellen, die für alle Benutzer gelten.</span><span class="sxs-lookup"><span data-stu-id="a876d-106">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="a876d-107">Nach Abschluss des Setups können Sie weitere Richtlinien erstellen.</span><span class="sxs-lookup"><span data-stu-id="a876d-107">You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="a876d-108">Einstellungen, die steuern, wie Benutzer auf mobilen Geräten auf Office-Dateien zugreifen</span><span class="sxs-lookup"><span data-stu-id="a876d-108">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="a876d-109">Mit den folgenden Einstellungen können Sie den Zugriff von Benutzern auf Office-Arbeitsdateien verwalten:</span><span class="sxs-lookup"><span data-stu-id="a876d-109">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="a876d-110">Einstellung</span><span class="sxs-lookup"><span data-stu-id="a876d-110">Setting</span></span>  <br/> |<span data-ttu-id="a876d-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a876d-111">Description</span></span>  <br/> |
|<span data-ttu-id="a876d-112">Für den Zugriff auf Office-Apps PIN bzw. digitalen Fingerabdruck anfordern</span><span class="sxs-lookup"><span data-stu-id="a876d-112">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="a876d-113">Wenn diese Einstellung **auf**ein festzulegen ist, müssen Benutzer zusätzlich zum Benutzernamen und Kennwort eine andere Form der Authentifizierung bereitstellen, bevor Sie Office-Apps auf Ihrem mobilen Gerät verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a876d-113">If this setting is **On**, users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="a876d-114">PIN nach dieser Anzahl von fehlerhaften Anmeldeversuchen zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="a876d-114">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="a876d-115">Um zu verhindern, dass ein nicht autorisierter Benutzer eine PIN nach dem Zufallsprinzip errät, wird die PIN, die nach der angegebenen Anzahl von Fehlversuchen zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="a876d-115">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="a876d-116">Benutzer müssen sich erneut anmelden, nachdem Office-Apps im Leerlauf waren für</span><span class="sxs-lookup"><span data-stu-id="a876d-116">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="a876d-117">Diese Einstellung bestimmt, wie lange sich ein Benutzer im Leerlauf befinden kann, bevor er zur erneuten Anmeldung aufgefordert wird.</span><span class="sxs-lookup"><span data-stu-id="a876d-117">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="a876d-118">Zugriff auf Arbeitsdateien auf Geräten mit entfernten Nutzungsbeschränkungen verweigern</span><span class="sxs-lookup"><span data-stu-id="a876d-118">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="a876d-119">Clevere Benutzer verfügen möglicherweise über ein Gerät, bei dem die Nutzungsbeschränkungen entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="a876d-119">Clever users may have a device that is jailbroken or rooted.</span></span> <span data-ttu-id="a876d-120">Dies bedeutet, dass der Benutzer das Betriebssystem ändern kann, wodurch das Gerät anfälliger für Schadsoftware wird.</span><span class="sxs-lookup"><span data-stu-id="a876d-120">This means that the user can modify the operating system, which can make the device more susceptible to malware.</span></span> <span data-ttu-id="a876d-121">Solche Geräte können gesperrt werden, wenn die Einstellung auf **Ein** festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="a876d-121">These devices are blocked when this setting is **On**.</span></span>  <br/> |
|<span data-ttu-id="a876d-122">Benutzer dürfen keine Inhalte aus Office-Apps in persönliche apps kopieren.</span><span class="sxs-lookup"><span data-stu-id="a876d-122">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="a876d-123">Wenn die Einstellung **auf**ein festgelegt ist, kann der Benutzer keine Informationen in einer Arbeitsdatei in eine persönliche Datei kopieren.</span><span class="sxs-lookup"><span data-stu-id="a876d-123">When the setting is **On**, the user can't copy information in a work file to a personal file.</span></span> <span data-ttu-id="a876d-124">Wenn die Einstellung **deaktiviert**ist, kann der Benutzerinformationen aus einer Arbeitsdatei in eine persönliche APP oder ein persönliches Konto kopieren.</span><span class="sxs-lookup"><span data-stu-id="a876d-124">If the setting is **Off**, the user can copy information from a work file to a personal app or personal account.</span></span>  <br/> |
   

