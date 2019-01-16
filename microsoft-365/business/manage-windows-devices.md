---
title: Aktivieren Sie in die Domäne eingebundener Windows 10 Geräte von Microsoft 365 Business verwaltet werden
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
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
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Erfahren Sie, wie Microsoft 365 schützen aktivieren lokalen AD Windows 10 Geräte verbunden.
ms.openlocfilehash: 6e66a2c5417c9037232c1ada654d4cac3c520607
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26867708"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="bca8b-103">Aktivieren Sie in die Domäne eingebundener Windows 10 Geräte von Microsoft 365 Business verwaltet werden</span><span class="sxs-lookup"><span data-stu-id="bca8b-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="bca8b-p101">Wenn Ihre Organisation Windows Server Active Directory lokalen verwendet wird, können Sie Microsoft 365 Business zum Schutz Ihrer Windows 10 Geräte bei gleichzeitiger Wahrung der Zugriff auf lokale Ressourcen, die erfordern lokale Authentifizierung festlegen. Sie können dies richten Sie durch die erste Synchronisierung Ihrer Active Directory mit Azure Active Directory, gefolgt von den Windows-10-Geräten mit Azure Active Directory registrieren und registrieren sie für die Verwaltung von mobilen Geräten von Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="bca8b-p101">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication. You can set this up by first synchronizing your Active Directory with Azure Active Directory, followed by registering the Windows 10 devices with Azure AD and enrolling them for mobile device management by Microsoft 365 Business.</span></span>
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="bca8b-106">Einrichten von Geräten in die Domäne eingebundener von Microsoft 365 Business verwaltet werden</span><span class="sxs-lookup"><span data-stu-id="bca8b-106">Set up domain-joined devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="bca8b-p102">Zum Einrichten Ihrer Organisation in die Domäne eingebundener Geräte profitieren von der Funktionen von Azure Active Directory zusätzlich zur lokalen Active Directory können Sie **Hybrid Azure AD verbunden Geräte**implementieren. Dies sind Geräte, die sowohl die lokale Active Directory und die Azure Active Directory verbunden sind. Hybride beigetreten Azure AD-Geräte können geschützt und Microsoft 365 Business verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="bca8b-p102">To set up your organization's domain-joined devices to benefit from the capabilities provided by Azure Active Directory in addition to on-premises Active Directory, you can implement **Hybrid Azure AD joined devices**. These are devices that are joined both to your on-premises Active Directory and your Azure Active Directory. Hybrid Azure AD joined devices can be protected and managed by Microsoft 365 Business..</span></span> 
  
<span data-ttu-id="bca8b-110">Führen Sie die Schritte unten, um Ihre Windows 10 Geräte Hybrid Azure AD beigetreten und verwaltet von Microsoft 365 Business stellen.</span><span class="sxs-lookup"><span data-stu-id="bca8b-110">Complete the steps below to make your Windows 10 devices Hybrid Azure AD joined and managed by Microsoft 365 Business.</span></span>
  
1. <span data-ttu-id="bca8b-111">Führen Sie zum Synchronisieren der Benutzer, Gruppen und Kontakte aus der lokalen Active Directory in Azure Active Directory den Assistenten für verzeichnissynchronisierung und Azure Active Directory verbinden gemäß [Directory-Synchronisierung für Office 365 einrichten](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span><span class="sxs-lookup"><span data-stu-id="bca8b-111">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure Active Directory Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bca8b-112">Die Schritte sind exakt identisch für Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="bca8b-112">The steps are exactly the same for Microsoft 365 Business.</span></span> 
  
2. <span data-ttu-id="bca8b-113">Bevor Sie Schritt 3, um Windows 10 Geräte können Hybrid werden Azure AD beigetreten ist abgeschlossen haben, müssen Sie sicherstellen, dass Sie die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="bca8b-113">Before you complete step 3 to enable Windows 10 devices to be Hybrid Azure AD joined, you need to make sure that you meet the following prerequisites:</span></span>
    
   - <span data-ttu-id="bca8b-114">Sie arbeiten mit die neueste Version von Azure Active Directory verbinden.</span><span class="sxs-lookup"><span data-stu-id="bca8b-114">You are running the latest version of Azure AD connect.</span></span>
    
   - <span data-ttu-id="bca8b-p103">Verbinden von Azure Active Directory synchronisiert hat die Computerobjekte der Geräte Hybrid werden Azure AD verknüpft werden soll. Eine Verbindung herstellen Sie sowie, wenn die Computerobjekte zu bestimmten Organisationseinheiten (OE) gehören, stellen Sie sicher, dass diese OUs für Azure AD-Synchronisierung festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="bca8b-p103">Azure AD connect has synchronized all the computer objects of the devices you want to be hybrid Azure AD joined. If the computer objects belong to specific organizational units (OU), then make sure these OUs are set for synchronization in Azure AD connect as well.</span></span>
    
3. <span data-ttu-id="bca8b-117">Registrieren Sie die vorhandenen Domäne eingebundener Windows 10 Geräte Hybrid Azure AD-beigetreten und für die Verwaltung von mobilen Geräten von Intune (Microsoft 365 Business) zu registrieren:</span><span class="sxs-lookup"><span data-stu-id="bca8b-117">Register existing domain-joined Windows 10 devices to be hybrid Azure AD Joined and enroll them for mobile device management by Intune (Microsoft 365 Business):</span></span>
    
4. <span data-ttu-id="bca8b-p104">Befolgen Sie die Schritt-für-Schritt-Anweisungen unter [How to configure Hybrid Azure Active Directory verbunden Geräte](https://go.microsoft.com/fwlink/p/?linkid=872870)aus. Auf diese Weise können die Synchronisierung der lokalen Active Directory beigetreten Windows 10 Computern und stellen sie die cloud bereit.</span><span class="sxs-lookup"><span data-stu-id="bca8b-p104">Follow the step by step instructions in [How to configure hybrid Azure Active Directory joined devices](https://go.microsoft.com/fwlink/p/?linkid=872870). This will enable the synchronization of your on-premises Active Directory joined Windows 10 computers and make them cloud ready.</span></span>
    
5. <span data-ttu-id="bca8b-p105">Um ein Windows-10-Gerät für die Verwaltung von mobilen Geräten zu registrieren, finden Sie unter [registrieren ein Geräts Windows 10 mit Intune mithilfe einer Gruppenrichtlinie](https://go.microsoft.com/fwlink/p/?linkid=872871) Anweisungen. Sie können die Gruppenrichtlinie auf einem lokalen Computer Ebene oder für Massenvorgänge, können Sie diese gruppenrichtlinieneinstellung auf Ihre Domänencontrollerserver erstellen.</span><span class="sxs-lookup"><span data-stu-id="bca8b-p105">In order to enroll a Windows 10 device for mobile device management, see [Enroll a Windows 10 device with Intune by using a Group Policy](https://go.microsoft.com/fwlink/p/?linkid=872871) for instructions. You can set the Group Policy at a local computer level or for bulk operations, you can create this group policy setting on your domain controller server.</span></span> 
    

