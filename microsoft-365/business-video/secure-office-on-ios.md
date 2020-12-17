---
title: Sichern von Office-Apps auf IOS
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Hier erfahren Sie, wie Sie Office-Apps auf IOS mit Microsoft 365 Business Premium sichern.
ms.openlocfilehash: 1703faa7cd7731f0779bacc3d2fa3ad3e4556910
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702059"
---
# <a name="secure-office-apps-on-ios"></a><span data-ttu-id="0cab8-103">Sichern von Office-Apps auf IOS</span><span class="sxs-lookup"><span data-stu-id="0cab8-103">Secure Office apps on iOS</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

<span data-ttu-id="0cab8-104">Sie können eine Richtlinie für den Benutzer Zugriff einrichten, bei der Mobile Benutzer eine PIN oder einen Fingerabdruck eingeben müssen, um sich anzumelden, und auch auf Ihren Geräten gespeicherte Arbeitsdateien verschlüsseln müssen.</span><span class="sxs-lookup"><span data-stu-id="0cab8-104">You can set up a user access policy that requires mobile users to enter a PIN or fingerprint to sign in, and also encrypts work files stored on their devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="0cab8-105">Probieren Sie es aus!</span><span class="sxs-lookup"><span data-stu-id="0cab8-105">Try it!</span></span>

1. <span data-ttu-id="0cab8-106">Melden Sie sich beim Microsoft 365 Admin Center an.</span><span class="sxs-lookup"><span data-stu-id="0cab8-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="0cab8-107">Wählen Sie unter **Richtlinien** die Option **Richtlinie hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="0cab8-107">Under **Policies**, choose **Add policy**.</span></span>
1. <span data-ttu-id="0cab8-108">Geben Sie im Bereich **Richtlinie hinzufügen** unter **Richtlinienname** einen Namen ein, und wählen Sie unter **Richtlinientyp** den gewünschten Richtlinientyp aus.</span><span class="sxs-lookup"><span data-stu-id="0cab8-108">In the **Add policy** pane, enter a name under **Policy name**, and choose the policy type that you want under **Policy type**.</span></span>
1. <span data-ttu-id="0cab8-109">Aktivieren Sie **verwalten, wie Benutzer auf Office-Dateien auf mobilen Geräten zugreifen**, und stellen Sie sicher, dass die folgenden drei Einstellungen aktiviert sind:</span><span class="sxs-lookup"><span data-stu-id="0cab8-109">Turn on **Manage how users access Office files on mobile devices**, and then make sure the following three settings are turned on:</span></span>
    - <span data-ttu-id="0cab8-110">**Für den Zugriff auf Office-Apps PIN bzw. digitalen Fingerabdruck anfordern**</span><span class="sxs-lookup"><span data-stu-id="0cab8-110">**Require a PIN or fingerprint to access Office apps**</span></span>
    - <span data-ttu-id="0cab8-111">**Schützen von Arbeitsdateien, wenn Geräte verloren gehen oder gestohlen werden**</span><span class="sxs-lookup"><span data-stu-id="0cab8-111">**Protect work files when devices are lost or stolen**</span></span>
    - <span data-ttu-id="0cab8-112">**Verschlüsseln von Arbeitsdateien**</span><span class="sxs-lookup"><span data-stu-id="0cab8-112">**Encrypt work files**</span></span>

1. <span data-ttu-id="0cab8-113">Wählen Sie unter **Dateien in diesen apps geschützt werden** die Office-Apps aus, die Sie auf mobilen Geräten schützen möchten.</span><span class="sxs-lookup"><span data-stu-id="0cab8-113">Under **Files in these apps will be protected**, select the Office apps you want to protect on mobile devices.</span></span>
1. <span data-ttu-id="0cab8-114">Unter **wer werden diese Einstellungen erhalten?** sind alle Benutzer standardmäßig ausgewählt, Sie können jedoch die Option **Change** auswählen, um alle Sicherheitsgruppen auszuwählen, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="0cab8-114">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="0cab8-115">Um das Erstellen der Richtlinie abzuschließen, wählen Sie **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="0cab8-115">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="0cab8-116">Wählen Sie auf der Seite **Richtlinie hinzufügen** die Option **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="0cab8-116">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="0cab8-117">Bestätigen Sie auf der Admin Center-Startseite, dass Ihre neue Richtlinie hinzugefügt wurde, indem Sie **Richtlinien** auswählen und ihre Richtlinie auf der Seite **Richtlinien** überprüfen.</span><span class="sxs-lookup"><span data-stu-id="0cab8-117">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>