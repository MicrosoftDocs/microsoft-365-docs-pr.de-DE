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
description: Erfahren Sie, wie Sie Windows 10 Pro-Geräterichtlinien mit Microsoft 365 Business Premium verwalten.
ms.openlocfilehash: 8d3e5107c0b2dfe3a84f31b98d9bd3ff8f7c5e4f
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50422123"
---
# <a name="manage-windows-10-pro-device-policies"></a><span data-ttu-id="f3951-103">Verwalten von Windows 10 Pro-Geräterichtlinien</span><span class="sxs-lookup"><span data-stu-id="f3951-103">Manage Windows 10 Pro device policies</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSL?autoplay=false]

<span data-ttu-id="f3951-104">Sie können Microsoft 365 Business verwenden, um sicherzustellen, dass Windows Defender Antivirus auf Windows 10-Geräten aktiviert ist und Microsoft-Updates automatisch auf die Geräte der Benutzer heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="f3951-104">You can use Microsoft 365 Business to ensure that Windows Defender Antivirus is activated on Windows 10 devices and Microsoft updates are automatically downloaded to users' devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="f3951-105">Probieren Sie es aus!</span><span class="sxs-lookup"><span data-stu-id="f3951-105">Try it!</span></span>

1. <span data-ttu-id="f3951-106">Melden Sie sich beim Microsoft 365 Admin Center an.</span><span class="sxs-lookup"><span data-stu-id="f3951-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="f3951-107">Wählen **Sie unter Richtlinien** die Option Richtlinie hinzufügen aus.</span><span class="sxs-lookup"><span data-stu-id="f3951-107">Under **Policies**, choose Add policy.</span></span>
1. <span data-ttu-id="f3951-108">Geben Sie **im Bereich** Richtlinie hinzufügen einen Namen unter Richtlinienname **ein,** und wählen Sie dann **Windows 10 Gerätekonfiguration** unter **Richtlinientyp aus.**</span><span class="sxs-lookup"><span data-stu-id="f3951-108">In the **Add policy** pane, enter a name under **Policy name**, and then select **Windows 10 Device Configuration** under **Policy type**.</span></span>
1. <span data-ttu-id="f3951-109">Wählen **Sie Secure Windows 10 devices aus,** um die Untereinstellungen zu sehen.</span><span class="sxs-lookup"><span data-stu-id="f3951-109">Choose **Secure Windows 10 devices** to see the sub-settings.</span></span>
1. <span data-ttu-id="f3951-110">Stellen Sie sicher, dass **PCs** mithilfe von Windows Defender Antivirus und Halten von **Windows 10-Geräten** automatisch auf dem neuesten Stand sind.</span><span class="sxs-lookup"><span data-stu-id="f3951-110">Make sure that **Help protect PCs from viruses and other threats using Windows Defender Antivirus** and **Keep Windows 10 devices up to date automatically** are turned on.</span></span>
1. <span data-ttu-id="f3951-111">Unter **Wer wird diese Einstellungen erhalten?** werden standardmäßig alle Benutzer ausgewählt, Sie können jedoch **Ändern** auswählen, um alle von Ihnen erstellten Sicherheitsgruppen auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="f3951-111">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="f3951-112">Wählen Sie Hinzufügen aus, um die Erstellung der Richtlinie **zu beenden.**</span><span class="sxs-lookup"><span data-stu-id="f3951-112">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="f3951-113">Wählen Sie **auf der Seite** Richtlinie hinzufügen die Option Schließen **aus.**</span><span class="sxs-lookup"><span data-stu-id="f3951-113">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="f3951-114">Vergewissern Sie sich auf der Admin Center-Homepage,  dass Ihre neue Richtlinie hinzugefügt wurde, indem Sie auf der Seite Richtlinien Richtlinien auswählen und Ihre **Richtlinie** überprüfen.</span><span class="sxs-lookup"><span data-stu-id="f3951-114">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>
1. <span data-ttu-id="f3951-115">Um zu überprüfen, ob die Richtlinie wirksam wurde, wechseln Sie auf dem Windows 10-Gerät eines Benutzers zu Windows Update, wählen Erweiterte Optionen **aus,** und vergewissern Sie sich, dass die Einstellungen ausgegraut sind.</span><span class="sxs-lookup"><span data-stu-id="f3951-115">To verify that the policy has taken effect, on a user's Windows 10 device, go to Windows Update, choose **Advanced options**, and confirm that settings are grayed out.</span></span>

    <span data-ttu-id="f3951-116">Klicken Sie dann auf Auswählen, wie Updates zugestellt **werden,** und vergewissern Sie sich, dass die Einstellungen ausgegraut sind und die folgende Meldung angezeigt wird: Einige Einstellungen werden von Ihrer Organisation ausgeblendet oder **verwaltet.**</span><span class="sxs-lookup"><span data-stu-id="f3951-116">Then, click **Choose how updates are delivered**, and confirm that settings are grayed out and the following message appears: **Some settings are hidden or managed by your organization**.</span></span>

