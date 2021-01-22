---
title: Verwalten von Windows 10 Pro-Geräterichtlinien mit Microsoft 365 Business Premium
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
description: Erfahren Sie, wie Sie Windows 10 Pro-Geräterichtlinien mit Microsoft 365 Business Premium verwalten.
ms.openlocfilehash: f42c175543ae16ae645c17997b20ed67aa5d705c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926006"
---
# <a name="manage-windows-10-pro-device-policies"></a><span data-ttu-id="bfa44-103">Verwalten von Windows 10 Pro-Geräterichtlinien</span><span class="sxs-lookup"><span data-stu-id="bfa44-103">Manage Windows 10 Pro device policies</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSL?autoplay=false]

<span data-ttu-id="bfa44-104">Sie können Microsoft 365 Business verwenden, um sicherzustellen, dass Windows Defender Antivirus auf Windows 10-Geräten aktiviert ist und die Updates von Microsoft automatisch auf die Geräte der Benutzer heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="bfa44-104">You can use Microsoft 365 Business to ensure that Windows Defender Antivirus is activated on Windows 10 devices and Microsoft updates are automatically downloaded to users' devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="bfa44-105">Probieren Sie es aus!</span><span class="sxs-lookup"><span data-stu-id="bfa44-105">Try it!</span></span>

1. <span data-ttu-id="bfa44-106">Melden Sie sich beim Microsoft 365 Admin Center an.</span><span class="sxs-lookup"><span data-stu-id="bfa44-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="bfa44-107">Wählen **Sie unter "Richtlinien"** die Option "Richtlinie hinzufügen" aus.</span><span class="sxs-lookup"><span data-stu-id="bfa44-107">Under **Policies**, choose Add policy.</span></span>
1. <span data-ttu-id="bfa44-108">Geben Sie **im Bereich "Richtlinie hinzufügen"** einen Namen unter "Richtlinienname" **ein,** und wählen Sie dann unter "Richtlinientyp" die **Windows 10-Gerätekonfiguration** **aus.**</span><span class="sxs-lookup"><span data-stu-id="bfa44-108">In the **Add policy** pane, enter a name under **Policy name**, and then select **Windows 10 Device Configuration** under **Policy type**.</span></span>
1. <span data-ttu-id="bfa44-109">Wählen **Sie "Sichere Windows 10-Geräte"** aus, um die Untereinstellungen zu sehen.</span><span class="sxs-lookup"><span data-stu-id="bfa44-109">Choose **Secure Windows 10 devices** to see the sub-settings.</span></span>
1. <span data-ttu-id="bfa44-110">Stellen Sie sicher, dass PCs mithilfe von **Windows Defender Antivirus-** und Windows **10-Geräte** automatisch auf dem neuesten Stand sind.</span><span class="sxs-lookup"><span data-stu-id="bfa44-110">Make sure that **Help protect PCs from viruses and other threats using Windows Defender Antivirus** and **Keep Windows 10 devices up to date automatically** are turned on.</span></span>
1. <span data-ttu-id="bfa44-111">Unter **"Wer wird diese Einstellungen erhalten?"** werden standardmäßig alle Benutzer ausgewählt, Aber Sie können **"Ändern"** auswählen, um alle sicherheitsgruppen auszuwählen, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="bfa44-111">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="bfa44-112">Um die Erstellung der Richtlinie zu beenden, wählen Sie **"Hinzufügen" aus.**</span><span class="sxs-lookup"><span data-stu-id="bfa44-112">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="bfa44-113">Wählen Sie **auf der Seite "Richtlinie hinzufügen"** die Option **"Schließen" aus.**</span><span class="sxs-lookup"><span data-stu-id="bfa44-113">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="bfa44-114">Bestätigen Sie auf der Admin Center-Startseite, dass  Die neue Richtlinie hinzugefügt wurde, indem Sie auf der Seite "Richtlinien" die Richtlinien auswählen und ihre **Richtlinie** überprüfen.</span><span class="sxs-lookup"><span data-stu-id="bfa44-114">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>
1. <span data-ttu-id="bfa44-115">Um zu überprüfen, ob die Richtlinie wirksam wurde, wechseln Sie auf dem Windows 10-Gerät eines Benutzers zu Windows Update, wählen Sie **"Erweiterte** Optionen" aus, und vergewissern Sie sich, dass die Einstellungen abgeblendet sind.</span><span class="sxs-lookup"><span data-stu-id="bfa44-115">To verify that the policy has taken effect, on a user's Windows 10 device, go to Windows Update, choose **Advanced options**, and confirm that settings are grayed out.</span></span>

    <span data-ttu-id="bfa44-116">Klicken Sie dann auf "Wie Updates zugestellt werden", und vergewissern Sie sich, dass die Einstellungen ausgegraut sind und die folgende Meldung angezeigt wird: Einige Einstellungen werden von Ihrer Organisation **ausgeblendet oder verwaltet.**</span><span class="sxs-lookup"><span data-stu-id="bfa44-116">Then, click **Choose how updates are delivered**, and confirm that settings are grayed out and the following message appears: **Some settings are hidden or managed by your organization**.</span></span>

