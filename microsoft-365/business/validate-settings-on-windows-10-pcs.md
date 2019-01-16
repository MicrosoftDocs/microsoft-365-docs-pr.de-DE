---
title: Überprüfen der Einstellungen für den App-Schutz auf Windows 10-PCs
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Erfahren Sie, wie Microsoft 365 Business app Protection Settings in Windows-10-Geräte zu überprüfen.
ms.openlocfilehash: db05c86bd75cc30e22e025034a3dab478d0f5365
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26867726"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a><span data-ttu-id="152e7-103">Überprüfen von Geräteschutzeinstellungen auf Windows 10-PCs</span><span class="sxs-lookup"><span data-stu-id="152e7-103">Validate device protection settings on Windows 10 PCs</span></span>

## <a name="verify-that-windows-10-device-policies-are-set"></a><span data-ttu-id="152e7-104">Sicherstellen, dass Windows 10-Geräterichtlinien festgelegt sind</span><span class="sxs-lookup"><span data-stu-id="152e7-104">Verify that Windows 10 device policies are set</span></span>

<span data-ttu-id="152e7-p101">Nachdem Sie [Geräterichtlinien eingerichtet haben](protection-settings-for-windows-10-pcs.md), kann es einige Stunden dauern, bis die jeweilige Richtlinie auf den Geräten der Benutzer in Kraft tritt. Sie können bestätigen, dass die Richtlinien in Kraft getreten sind, indem Sie sich auf den Geräten der Benutzer die verschiedenen Bildschirme der Windows-Einstellungen ansehen. Weil die Benutzer die Einstellungen für Windows Update und Windows Defender Antivirus auf ihren Windows 10-Geräten nicht ändern können, sind viele dieser Optionen abgeblendet.</span><span class="sxs-lookup"><span data-stu-id="152e7-p101">After you [set up devices policies](protection-settings-for-windows-10-pcs.md), it may take up to a few hours for the policy to take effect on users' devices. You can confirm that the policies took effect by looking at various Windows Settings screens on the users' devices. Because the users won't be able to modify the Windows Update and Windows Defender Antivirus settings on their Windows 10 devices, a lot of those options will be greyed out.</span></span>
  
1. <span data-ttu-id="152e7-108">Wechseln Sie zu **Einstellungen** \> **Update &amp; Security** \> **Windows Update** \> **Neustart-Optionen** , und bestätigen Sie, dass alle Einstellungen abgeblendet sind.</span><span class="sxs-lookup"><span data-stu-id="152e7-108">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Restart options** and confirm that all settings are greyed out.</span></span> 
    
    ![All the Restart options are greyed out.](media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. <span data-ttu-id="152e7-110">Wechseln Sie zu **Einstellungen** \> **Update &amp; Security** \> **Windows Update** \> **Erweiterte Optionen** ein, und bestätigen Sie, dass alle Einstellungen abgeblendet sind.</span><span class="sxs-lookup"><span data-stu-id="152e7-110">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** and confirm that all settings are greyed out.</span></span> 
    
    ![Windows Advanced updates options are all greyed out.](media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. <span data-ttu-id="152e7-112">Wechseln Sie zu **Einstellungen** \> **Update &amp; Security** \> **Windows Update** \> **Erweiterte Optionen** \> **auswählen, wie Updates übermittelt werden**.</span><span class="sxs-lookup"><span data-stu-id="152e7-112">Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.</span></span>
    
    <span data-ttu-id="152e7-113">Vergewissern Sie sich, dass Sie die Meldung (in Rot) sehen können, dass einige Einstellungen ausgeblendet sind oder von Ihrer Organisation verwaltet werden und alle Optionen abgeblendet sind.</span><span class="sxs-lookup"><span data-stu-id="152e7-113">Confirm that you can see the message (in red) that some settings are hidden or managed by your organization, and all the options are greyed out.</span></span>
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. <span data-ttu-id="152e7-115">Wechseln Sie zum Öffnen der Windows Defender Security Center auf **Einstellungen** \> **Update &amp; Security** \> **Windows Defender** \> klicken Sie auf **Öffnen Windows Defender Sicherheitscenter** \> **Virus &amp; Thread Schutz** \> **Virus &amp; Bedrohung Protection Settings**.</span><span class="sxs-lookup"><span data-stu-id="152e7-115">To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**.</span></span> 
    
5. <span data-ttu-id="152e7-116">Stellen Sie sicher, dass alle Optionen abgeblendet sind.</span><span class="sxs-lookup"><span data-stu-id="152e7-116">Verify that all options are greyed out.</span></span> 
    
    ![The Virus and threat protection settings are greyed out.](media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a><span data-ttu-id="152e7-118">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="152e7-118">Related Topics</span></span>

[<span data-ttu-id="152e7-119">Microsoft 365 Business-Dokumentation und -Ressourcen</span><span class="sxs-lookup"><span data-stu-id="152e7-119">Microsoft 365 Business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="152e7-120">Erste Schritte mit Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="152e7-120">Get started with Microsoft 365 Business</span></span>](microsoft-365-business-overview.md)
  
[<span data-ttu-id="152e7-121">Verwalten von Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="152e7-121">Manage Microsoft 365 Business</span></span>](manage.md)
  
[<span data-ttu-id="152e7-122">Festlegen von Geräteschutzeinstellungen für Windows 10-PCs</span><span class="sxs-lookup"><span data-stu-id="152e7-122">Set device configurations for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  

