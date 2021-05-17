---
title: Den Benutzerzugriff auf Office-Dokumente auf mobilen Geräten verwalten
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: Erfahren Sie mehr über Schutzrichtlinien, mit denen Sie verwalten können, wie Benutzer auf Office und Arbeitsdateien von mobilen Geräten zugreifen können.
ms.openlocfilehash: a48aa241c9e70cf087da3f1701e859dae7238024
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578385"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="eb4ba-103">Den Benutzerzugriff auf Office-Dokumente auf mobilen Geräten verwalten</span><span class="sxs-lookup"><span data-stu-id="eb4ba-103">Manage how users access Office documents on mobile devices</span></span>

<span data-ttu-id="eb4ba-104">Dieser Artikel gilt für Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="eb4ba-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="eb4ba-105">[] Richtlinieneinstellungen zum Steuern, wie Benutzer mit ihren mobilen Geräten auf Office-Dateien zugreifen können, sind standardmäßig auf **Aus** eingestellt.</span><span class="sxs-lookup"><span data-stu-id="eb4ba-105">Policy settings that control how users access Office files from their mobile devices are **Off** by default.</span></span> <span data-ttu-id="eb4ba-106">Es wird empfohlen, die Standardwerte während des Setups zu akzeptieren, um Anwendungsrichtlinien für Android, iOS und Windows 10 zu erstellen, die für alle Benutzer gelten.</span><span class="sxs-lookup"><span data-stu-id="eb4ba-106">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="eb4ba-107">Nach Abschluss des Setups können Sie weitere Richtlinien erstellen.</span><span class="sxs-lookup"><span data-stu-id="eb4ba-107">You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="eb4ba-108">Einstellungen, die steuern, wie Benutzer auf mobilen Geräten auf Office-Dateien zugreifen</span><span class="sxs-lookup"><span data-stu-id="eb4ba-108">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="eb4ba-109">Mit den folgenden Einstellungen können Sie den Zugriff von Benutzern auf Office-Arbeitsdateien verwalten:</span><span class="sxs-lookup"><span data-stu-id="eb4ba-109">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="eb4ba-110">Einstellung</span><span class="sxs-lookup"><span data-stu-id="eb4ba-110">Setting</span></span>  <br/> |<span data-ttu-id="eb4ba-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb4ba-111">Description</span></span>  <br/> |
|<span data-ttu-id="eb4ba-112">Für den Zugriff auf Office-Apps PIN bzw. digitalen Fingerabdruck anfordern</span><span class="sxs-lookup"><span data-stu-id="eb4ba-112">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="eb4ba-113">Wenn diese Einstellung **Auf** ist, müssen Benutzer zusätzlich zu Ihrem Benutzernamen und Kennwort eine andere Form der Authentifizierung bereitstellen, bevor sie Office apps auf ihrem mobilen Gerät verwenden können.</span><span class="sxs-lookup"><span data-stu-id="eb4ba-113">If this setting is **On**, users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="eb4ba-114">PIN nach dieser Anzahl von fehlerhaften Anmeldeversuchen zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="eb4ba-114">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="eb4ba-115">Um zu verhindern, dass ein nicht autorisierter Benutzer eine PIN nach dem Zufallsprinzip errät, wird die PIN, die nach der angegebenen Anzahl von Fehlversuchen zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="eb4ba-115">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="eb4ba-116">Benutzer müssen sich erneut anmelden, nachdem Office-Apps im Leerlauf waren für</span><span class="sxs-lookup"><span data-stu-id="eb4ba-116">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="eb4ba-117">Diese Einstellung bestimmt, wie lange ein Benutzer im Leerlauf sein kann, bevor er zur erneuten Anmeldung aufgefordert wird.</span><span class="sxs-lookup"><span data-stu-id="eb4ba-117">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="eb4ba-118">Zugriff auf Arbeitsdateien auf Geräten mit entfernten Nutzungsbeschränkungen verweigern</span><span class="sxs-lookup"><span data-stu-id="eb4ba-118">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="eb4ba-119">Clevere Benutzer verfügen möglicherweise über ein Gerät, bei dem die Nutzungsbeschränkungen entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="eb4ba-119">Clever users may have a device that is jailbroken or rooted.</span></span> <span data-ttu-id="eb4ba-120">Dies bedeutet, dass der Benutzer das Betriebssystem ändern kann, wodurch das Gerät anfälliger für Schadsoftware werden kann.</span><span class="sxs-lookup"><span data-stu-id="eb4ba-120">This means that the user can modify the operating system, which can make the device more susceptible to malware.</span></span> <span data-ttu-id="eb4ba-121">Solche Geräte können gesperrt werden, wenn die Einstellung auf **Ein** festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="eb4ba-121">These devices are blocked when this setting is **On**.</span></span>  <br/> |
|<span data-ttu-id="eb4ba-122">Nicht zulassen, dass Benutzer Inhalte aus Office apps in persönliche Apps kopieren</span><span class="sxs-lookup"><span data-stu-id="eb4ba-122">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="eb4ba-123">Wenn die Einstellung **Auf** ist, kann der Benutzer keine Informationen in einer Arbeitsdatei in eine persönliche Datei kopieren.</span><span class="sxs-lookup"><span data-stu-id="eb4ba-123">When the setting is **On**, the user can't copy information in a work file to a personal file.</span></span> <span data-ttu-id="eb4ba-124">Wenn die Einstellung **deaktiviert ist,** kann der Benutzer Informationen aus einer Arbeitsdatei in eine persönliche App oder ein persönliches Konto kopieren.</span><span class="sxs-lookup"><span data-stu-id="eb4ba-124">If the setting is **Off**, the user can copy information from a work file to a personal app or personal account.</span></span>  <br/> |
   

