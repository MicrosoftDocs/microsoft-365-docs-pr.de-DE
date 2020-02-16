---
title: Festlegen von Anwendungsschutzeinstellungen für Windows 10-Geräte
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Hier erfahren Sie, wie Sie eine APP-Verwaltungsrichtlinie erstellen und Arbeitsdateien auf Windows 10-Geräten schützen.
ms.openlocfilehash: eb9c5465bf7376efa95162cd39be3f1c6840a3e4
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42065008"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="6693b-103">Festlegen von Anwendungsschutzeinstellungen für Windows 10-Geräte</span><span class="sxs-lookup"><span data-stu-id="6693b-103">Set application protection settings for Windows 10 devices</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="6693b-104">Erstellen einer App-Verwaltungsrichtlinie für Windows 10</span><span class="sxs-lookup"><span data-stu-id="6693b-104">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="6693b-105">Wenn Ihre Benutzer Arbeitsaufgaben auf ihren privaten Windows 10-Geräte ausführen, können Sie Ihre Daten auch auf diesen Geräten schützen.</span><span class="sxs-lookup"><span data-stu-id="6693b-105">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="6693b-106">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="6693b-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
    
2. <span data-ttu-id="6693b-107">Wählen Sie im linken Navigationsbereich **Geräte** \> **Richtlinien** \> **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="6693b-107">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>

3. <span data-ttu-id="6693b-108">Geben Sie im Bereich **Richtlinie hinzufügen** einen eindeutigen Namen für diese Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="6693b-108">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
    
4. <span data-ttu-id="6693b-109">Wählen Sie unter **Richtlinientyp** die Option **Anwendungsverwaltung für Windows 10** aus.</span><span class="sxs-lookup"><span data-stu-id="6693b-109">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
    
5. <span data-ttu-id="6693b-110">Wählen Sie unter **Gerätetyp**entweder **persönlich** oder **Unternehmensbesitz**aus.</span><span class="sxs-lookup"><span data-stu-id="6693b-110">Under **Device type**, choose either **Personal** or **Company Owned**.</span></span>
    
6. <span data-ttu-id="6693b-111">Die Option **Arbeitsdateien verschlüsseln** wird automatisch aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6693b-111">The **Encrypt work files** is turned on automatically.</span></span> 
    
7. <span data-ttu-id="6693b-112">Aktivieren Sie die Optionen **Benutzer daran hindern, Unternehmensdaten in persönliche Dateien zu kopieren** und **Benutzer zum Speichern aller Arbeitsdateien auf OneDrive for Business zwingen**, wenn Sie nicht zulassen möchten, dass Benutzer Arbeitsdateien auf den eigenen PCs speichern.</span><span class="sxs-lookup"><span data-stu-id="6693b-112">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
    
9. <span data-ttu-id="6693b-113">Erweitern Sie **Wiederherstellungsdaten auf Windows-Geräten**.</span><span class="sxs-lookup"><span data-stu-id="6693b-113">Expand **Recover data on Windows devices**.</span></span> <span data-ttu-id="6693b-114">Es **wird empfohlen, dass Sie es**aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6693b-114">We recommend that you turn it **On**.</span></span>
    
    <span data-ttu-id="6693b-115">Bevor Sie zum Speicherort des Zertifikats des Datenwiederherstellungs-Agent navigieren können, müssen Sie zuerst ein Zertifikat erstellen.</span><span class="sxs-lookup"><span data-stu-id="6693b-115">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one.</span></span> <span data-ttu-id="6693b-116">Anweisungen finden Sie unter [Erstellen und Überprüfen eines Daten Wiederherstellungs-Agents (DRA)-Zertifikats für das verschlüsselnde Datei System (EFS)](https://go.microsoft.com/fwlink/p/?linkid=853700).</span><span class="sxs-lookup"><span data-stu-id="6693b-116">For instructions, see [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](https://go.microsoft.com/fwlink/p/?linkid=853700).</span></span>
    
    <span data-ttu-id="6693b-117">Standardmäßig werden Arbeitsdateien mithilfe eines geheimen Schlüssels verschlüsselt, der auf dem Gerät gespeichert und mit dem Profil des Benutzers verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="6693b-117">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile.</span></span> <span data-ttu-id="6693b-118">Nur der Benutzer kann die Datei öffnen und entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="6693b-118">Only the user can open and decrypt the file.</span></span> <span data-ttu-id="6693b-119">Wenn ein Gerät jedoch verloren geht oder ein Benutzers entfernt wird, kann eine Datei im verschlüsselten Zustand zurückbleiben.</span><span class="sxs-lookup"><span data-stu-id="6693b-119">However, if a device is lost or a user is removed, a file can be stuck in an encrypted state.</span></span> <span data-ttu-id="6693b-120">Ein Administrator kann das DRA-Zertifikat (Data Recovery Agent) zum Entschlüsseln der Datei verwenden.</span><span class="sxs-lookup"><span data-stu-id="6693b-120">An admin can use the Data Recovery Agent (DRA) certificate to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](../media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="6693b-122">Erweitern Sie **Protect additional Network and Cloud Locations** , wenn Sie zusätzliche Domänen oder SharePoint Online Speicherorte hinzufügen möchten, um sicherzustellen, dass die Dateien in allen aufgeführten apps geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="6693b-122">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps are protected.</span></span> <span data-ttu-id="6693b-123">Wenn Sie für eines der Felder mehr als ein Element eingeben müssen, verwenden Sie ein Semikolon (;) zwischen den Elementen.</span><span class="sxs-lookup"><span data-stu-id="6693b-123">If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span>
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](../media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="6693b-p105">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span><span class="sxs-lookup"><span data-stu-id="6693b-p105">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
    
12. <span data-ttu-id="6693b-127">Wählen Sie schließlich **Hinzufügen** aus, um die Richtlinie zu speichern, und weisen Sie sie Geräten zu.</span><span class="sxs-lookup"><span data-stu-id="6693b-127">Finally, choose **Add** to save the policy, and assign it to devices.</span></span> 
