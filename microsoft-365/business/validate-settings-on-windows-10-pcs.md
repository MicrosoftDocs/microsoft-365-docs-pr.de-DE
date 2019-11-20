---
title: Überprüfen der Einstellungen für den App-Schutz auf Windows 10-PCs
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Erfahren Sie, wie Sie Microsoft 365 Business App Protection-Einstellungen auf Windows 10-Geräten überprüfen.
ms.openlocfilehash: b8793ab7f77bbc7f608f237e2455f6fd12c3bb26
ms.sourcegitcommit: 6a413a65b8c2e10cea08f0a15635b28a1362a582
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2019
ms.locfileid: "38721798"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="60e8e-103">Überprüfen von Geräteschutzeinstellungen auf Windows 10-PCs</span><span class="sxs-lookup"><span data-stu-id="60e8e-103">Validate device protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-windows-10-device-policies-are-set"></a><span data-ttu-id="60e8e-104">Sicherstellen, dass Windows 10-Geräterichtlinien festgelegt sind</span><span class="sxs-lookup"><span data-stu-id="60e8e-104">Verify that Windows 10 device policies are set</span></span>

<span data-ttu-id="60e8e-105">Nachdem Sie [Geräterichtlinien eingerichtet haben](protection-settings-for-windows-10-pcs.md), kann es einige Stunden dauern, bis die jeweilige Richtlinie auf den Geräten der Benutzer in Kraft tritt.</span><span class="sxs-lookup"><span data-stu-id="60e8e-105">After you [set up devices policies](protection-settings-for-windows-10-pcs.md), it may take up to a few hours for the policy to take effect on users' devices.</span></span> <span data-ttu-id="60e8e-106">Sie können bestätigen, dass die Richtlinien in Kraft getreten sind, indem Sie sich auf den Geräten der Benutzer die verschiedenen Bildschirme der Windows-Einstellungen ansehen.</span><span class="sxs-lookup"><span data-stu-id="60e8e-106">You can confirm that the policies took effect by looking at various Windows Settings screens on the users' devices.</span></span> <span data-ttu-id="60e8e-107">Da die Benutzer nicht in der Lage sind, die Antivirus-Einstellungen für Windows Update und Windows Defender auf Ihren Windows 10-Geräten zu ändern, werden viele Optionen abgeblendet.</span><span class="sxs-lookup"><span data-stu-id="60e8e-107">Because the users won't be able to modify the Windows Update and Windows Defender Antivirus settings on their Windows 10 devices, many options will be grayed out.</span></span>
  
1. <span data-ttu-id="60e8e-108">Wechseln Sie **zu Einstellungen** \> **Update &amp; Security** \> **Windows Update** \> - **Neustartoptionen** , und vergewissern Sie sich, dass alle Einstellungen abgeblendet sind.</span><span class="sxs-lookup"><span data-stu-id="60e8e-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are grayed out.</span></span> 
    
    ![Alle Neustartoptionen sind abgeblendet.](media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. <span data-ttu-id="60e8e-110">Wechseln Sie **zu Einstellungen** \> **Update &amp; Security** \> **Windows Update** \> **Erweiterte Optionen** , und vergewissern Sie sich, dass alle Einstellungen abgeblendet sind.</span><span class="sxs-lookup"><span data-stu-id="60e8e-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are grayed out.</span></span> 
    
    ![Die Optionen für erweiterte Windows-Updates sind alle abgeblendet.](media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. <span data-ttu-id="60e8e-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span><span class="sxs-lookup"><span data-stu-id="60e8e-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span></span>
    
    <span data-ttu-id="60e8e-113">Vergewissern Sie sich, dass die Nachricht (in rot) angezeigt wird, dass einige Einstellungen von Ihrer Organisation ausgeblendet oder verwaltet werden und alle Optionen abgeblendet sind.</span><span class="sxs-lookup"><span data-stu-id="60e8e-113">Confirm that you can see the message (in red) that some settings are hidden or managed by your organization, and all the options are grayed out.</span></span>
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. <span data-ttu-id="60e8e-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span><span class="sxs-lookup"><span data-stu-id="60e8e-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span></span> 
    
5. <span data-ttu-id="60e8e-116">Stellen Sie sicher, dass alle Optionen abgeblendet sind.</span><span class="sxs-lookup"><span data-stu-id="60e8e-116">Verify that all options are grayed out.</span></span> 
    
    ![Die Viren-und Bedrohungsschutz Einstellungen sind abgeblendet.](media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a><span data-ttu-id="60e8e-118">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="60e8e-118">Related Topics</span></span>

[<span data-ttu-id="60e8e-119">Microsoft 365 Business-Dokumentation und -Ressourcen</span><span class="sxs-lookup"><span data-stu-id="60e8e-119">Microsoft 365 Business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="60e8e-120">Erste Schritte mit Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="60e8e-120">Get started with Microsoft 365 Business</span></span>](microsoft-365-business-overview.md)
  
[<span data-ttu-id="60e8e-121">Verwalten von Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="60e8e-121">Manage Microsoft 365 Business</span></span>](manage.md)
  
[<span data-ttu-id="60e8e-122">Festlegen von Geräteschutzeinstellungen für Windows 10-PCs</span><span class="sxs-lookup"><span data-stu-id="60e8e-122">Set device configurations for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  

