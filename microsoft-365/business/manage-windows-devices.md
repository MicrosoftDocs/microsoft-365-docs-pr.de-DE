---
title: Aktivieren von Domänenbeitritt zu Windows 10-Geräten, die von Microsoft 365 Business verwaltet werden
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
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
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Erfahren Sie, wie Sie mit Microsoft 365 lokale AD-verbundene Windows 10-Geräte schützen können.
ms.openlocfilehash: d61b3bf6be50d6b21e7b883774567bb63995e60e
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278075"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="25aa2-103">Aktivieren von Domänenbeitritt zu Windows 10-Geräten, die von Microsoft 365 Business verwaltet werden</span><span class="sxs-lookup"><span data-stu-id="25aa2-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="25aa2-104">Wenn Ihre Organisation Windows Server Active Directory lokal verwendet, können Sie Microsoft 365 Business einrichten, um Ihre Windows 10-Geräte zu schützen, ohne dabei den Zugriff auf lokale Ressourcen zu gewährleisten, die lokal authentifiziert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="25aa2-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="25aa2-105">Sie können dies einrichten, indem Sie zunächst Ihr Active Directory mit Azure Active Directory synchronisieren, gefolgt von der Registrierung der Windows 10-Geräte mit Azure AD und der Anmeldung für die Verwaltung mobiler Geräte durch Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="25aa2-105">You can set this up by first synchronizing your Active Directory with Azure Active Directory, followed by registering the Windows 10 devices with Azure AD and enrolling them for mobile device management by Microsoft 365 Business.</span></span>
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="25aa2-106">Einrichten von Domänen verbundenen Geräten, die von Microsoft 365 Business verwaltet werden</span><span class="sxs-lookup"><span data-stu-id="25aa2-106">Set up domain-joined devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="25aa2-107">Zum Einrichten der Domänen verbundenen Geräte Ihrer Organisation, die zusätzlich zu lokalen Active Directory-Funktionen von Azure Active Directory bereitgestellt werden, können Sie **hybride Azure AD-verbundene Geräte**implementieren.</span><span class="sxs-lookup"><span data-stu-id="25aa2-107">To set up your organization's domain-joined devices to benefit from the capabilities provided by Azure Active Directory in addition to on-premises Active Directory, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="25aa2-108">Dabei handelt es sich um Geräte, die sowohl mit Ihrem lokalen Active Directory als auch mit Ihrem Azure Active Directory verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="25aa2-108">These are devices that are joined both to your on-premises Active Directory and your Azure Active Directory.</span></span> <span data-ttu-id="25aa2-109">Hybride Azure AD-verbundene Geräte können von Microsoft 365 Business geschützt und verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="25aa2-109">Hybrid Azure AD joined devices can be protected and managed by Microsoft 365 Business..</span></span> 
  
<span data-ttu-id="25aa2-110">Führen Sie die folgenden Schritte aus, um Ihre Windows 10-Geräte Hybrid Azure AD zu verbinden und von Microsoft 365 Business zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="25aa2-110">Complete the steps below to make your Windows 10 devices Hybrid Azure AD joined and managed by Microsoft 365 Business.</span></span>
  
1. <span data-ttu-id="25aa2-111">Führen Sie den Assistenten für die Verzeichnissynchronisierung und Azure Active Directory Connect wie unter [Einrichten der Verzeichnissynchronisierung für Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)beschrieben aus, um Ihre Benutzer, Gruppen und Kontakte aus dem lokalen Active Directory in Azure Active Directory zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="25aa2-111">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure Active Directory Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="25aa2-112">Die Schritte sind für Microsoft 365 Business identisch.</span><span class="sxs-lookup"><span data-stu-id="25aa2-112">The steps are exactly the same for Microsoft 365 Business.</span></span> 
  
2. <span data-ttu-id="25aa2-113">Bevor Sie Schritt 3 abschließen, um Windows 10-Geräte als Hybriden Azure AD-Beitritt zu aktivieren, müssen Sie sicherstellen, dass die folgenden Voraussetzungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="25aa2-113">Before you complete step 3 to enable Windows 10 devices to be Hybrid Azure AD joined, you need to make sure that you meet the following prerequisites:</span></span>
    
   - <span data-ttu-id="25aa2-114">Sie führen die neueste Version von Azure AD Connect aus.</span><span class="sxs-lookup"><span data-stu-id="25aa2-114">You are running the latest version of Azure AD connect.</span></span>
    
   - <span data-ttu-id="25aa2-115">Azure AD Connect hat alle Computerobjekte der Geräte synchronisiert, für die eine hybride Azure AD-Verknüpfung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="25aa2-115">Azure AD connect has synchronized all the computer objects of the devices you want to be hybrid Azure AD joined.</span></span> <span data-ttu-id="25aa2-116">Wenn die Computerobjekte zu bestimmten Organisationseinheiten (OU) gehören, stellen Sie sicher, dass diese OUs auch für die Synchronisierung in Azure AD Connect festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="25aa2-116">If the computer objects belong to specific organizational units (OU), then make sure these OUs are set for synchronization in Azure AD connect as well.</span></span>
    
3. <span data-ttu-id="25aa2-117">Registrieren Sie vorhandene mit der Domäne verbundene Windows 10-Geräte als hybrides Azure AD-Mitglied, und registrieren Sie Sie für die Verwaltung mobiler Geräte von InTune (Microsoft 365 Business):</span><span class="sxs-lookup"><span data-stu-id="25aa2-117">Register existing domain-joined Windows 10 devices to be hybrid Azure AD Joined and enroll them for mobile device management by Intune (Microsoft 365 Business):</span></span>
    
4. <span data-ttu-id="25aa2-118">BeFolgen Sie die Schritt-für-Schritt-Anweisungen unter [How to configure Hybrid Azure Active Directory Joined Devices](https://go.microsoft.com/fwlink/p/?linkid=872870).</span><span class="sxs-lookup"><span data-stu-id="25aa2-118">Follow the step by step instructions in [How to configure hybrid Azure Active Directory joined devices](https://go.microsoft.com/fwlink/p/?linkid=872870).</span></span> <span data-ttu-id="25aa2-119">Dadurch wird die Synchronisierung Ihrer lokalen Active Directory-Verbindung mit Windows 10-Computern aktiviert, sodass diese Cloud-fähig ist.</span><span class="sxs-lookup"><span data-stu-id="25aa2-119">This will enable the synchronization of your on-premises Active Directory joined Windows 10 computers and make them cloud ready.</span></span>
    
5. <span data-ttu-id="25aa2-120">Informationen zum Registrieren eines Windows 10-Geräts für die Verwaltung mobiler Geräte finden Sie unter [Registrieren eines Windows 10-Geräts mit InTune mithilfe einer Gruppenrichtlinie](https://go.microsoft.com/fwlink/p/?linkid=872871) .</span><span class="sxs-lookup"><span data-stu-id="25aa2-120">In order to enroll a Windows 10 device for mobile device management, see [Enroll a Windows 10 device with Intune by using a Group Policy](https://go.microsoft.com/fwlink/p/?linkid=872871) for instructions.</span></span> <span data-ttu-id="25aa2-121">Sie können die Gruppenrichtlinie auf lokaler Computerebene oder für Massenvorgänge festlegen, indem Sie diese Gruppenrichtlinieneinstellung auf dem Domänencontrollerserver erstellen.</span><span class="sxs-lookup"><span data-stu-id="25aa2-121">You can set the Group Policy at a local computer level or for bulk operations, you can create this group policy setting on your domain controller server.</span></span> 
    

