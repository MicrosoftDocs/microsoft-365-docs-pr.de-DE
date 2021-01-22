---
title: Office-Apps unter iOS sichern
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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Erfahren Sie, wie Sie Office-Apps unter iOS mit Microsoft 365 Business Premium sichern.
ms.openlocfilehash: fd7fdd32500f9a2362ac29059abe9424d045c206
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928030"
---
# <a name="secure-office-apps-on-ios"></a><span data-ttu-id="d4675-103">Office-Apps unter iOS sichern</span><span class="sxs-lookup"><span data-stu-id="d4675-103">Secure Office apps on iOS</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

<span data-ttu-id="d4675-104">Sie können eine Benutzerzugriffsrichtlinie einrichten, die erfordert, dass mobile Benutzer eine PIN oder einen Fingerabdruck eingeben, um sich anmelden, und außerdem auf ihren Geräten gespeicherte Arbeitsdateien verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="d4675-104">You can set up a user access policy that requires mobile users to enter a PIN or fingerprint to sign in, and also encrypts work files stored on their devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="d4675-105">Probieren Sie es aus!</span><span class="sxs-lookup"><span data-stu-id="d4675-105">Try it!</span></span>

1. <span data-ttu-id="d4675-106">Melden Sie sich beim Microsoft 365 Admin Center an.</span><span class="sxs-lookup"><span data-stu-id="d4675-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="d4675-107">Wählen **Sie unter "Richtlinien"** die Option **"Richtlinie hinzufügen" aus.**</span><span class="sxs-lookup"><span data-stu-id="d4675-107">Under **Policies**, choose **Add policy**.</span></span>
1. <span data-ttu-id="d4675-108">Geben Sie **im Bereich "Richtlinie hinzufügen"** einen Namen unter "Richtlinienname" **ein,** und wählen Sie den Richtlinientyp aus, den Sie unter **Richtlinientyp auswählen möchten.**</span><span class="sxs-lookup"><span data-stu-id="d4675-108">In the **Add policy** pane, enter a name under **Policy name**, and choose the policy type that you want under **Policy type**.</span></span>
1. <span data-ttu-id="d4675-109">Aktivieren Sie **"Verwalten des Zugriffs von Benutzern** auf Office-Dateien auf mobilen Geräten", und stellen Sie dann sicher, dass die folgenden drei Einstellungen aktiviert sind:</span><span class="sxs-lookup"><span data-stu-id="d4675-109">Turn on **Manage how users access Office files on mobile devices**, and then make sure the following three settings are turned on:</span></span>
    - <span data-ttu-id="d4675-110">**Für den Zugriff auf Office-Apps PIN bzw. digitalen Fingerabdruck anfordern**</span><span class="sxs-lookup"><span data-stu-id="d4675-110">**Require a PIN or fingerprint to access Office apps**</span></span>
    - <span data-ttu-id="d4675-111">**Schützen von Arbeitsdateien, wenn Geräte verloren gehen oder gestohlen werden**</span><span class="sxs-lookup"><span data-stu-id="d4675-111">**Protect work files when devices are lost or stolen**</span></span>
    - <span data-ttu-id="d4675-112">**Verschlüsseln von Arbeitsdateien**</span><span class="sxs-lookup"><span data-stu-id="d4675-112">**Encrypt work files**</span></span>

1. <span data-ttu-id="d4675-113">Wählen **Sie unter "Dateien in** diesen Apps" die Office-Apps aus, die Sie auf mobilen Geräten schützen möchten.</span><span class="sxs-lookup"><span data-stu-id="d4675-113">Under **Files in these apps will be protected**, select the Office apps you want to protect on mobile devices.</span></span>
1. <span data-ttu-id="d4675-114">Unter **"Wer wird diese Einstellungen erhalten?"** werden standardmäßig alle Benutzer ausgewählt, Aber Sie können **"Ändern"** auswählen, um alle von Ihnen erstellten Sicherheitsgruppen auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="d4675-114">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="d4675-115">Um die Erstellung der Richtlinie fertig zu stellen, wählen Sie **"Hinzufügen" aus.**</span><span class="sxs-lookup"><span data-stu-id="d4675-115">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="d4675-116">Wählen Sie **auf der Seite "Richtlinie hinzufügen"** die Option **"Schließen" aus.**</span><span class="sxs-lookup"><span data-stu-id="d4675-116">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="d4675-117">Bestätigen Sie auf der Admin Center-Startseite, dass  Die neue Richtlinie hinzugefügt wurde, indem Sie auf der Seite "Richtlinien" die Richtlinien auswählen und ihre **Richtlinie** überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d4675-117">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>