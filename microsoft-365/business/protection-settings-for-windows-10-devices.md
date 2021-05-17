---
title: Bearbeiten oder Festlegen von Anwendungsschutzeinstellungen für Windows 10 Geräte
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: Erfahren Sie, wie Sie App-Verwaltungsrichtlinien erstellen oder bearbeiten und Arbeitsdateien auf den persönlichen Geräten Windows 10 schützen.
ms.openlocfilehash: aa270c563e6bdce6fd48f8713d7db3ce23921925
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580012"
---
# <a name="set-or-edit-application-protection-settings-for-windows-10-devices"></a><span data-ttu-id="b0e97-103">Festlegen oder Bearbeiten von Anwendungsschutzeinstellungen für Windows 10 Geräte</span><span class="sxs-lookup"><span data-stu-id="b0e97-103">Set or edit application protection settings for Windows 10 devices</span></span>

<span data-ttu-id="b0e97-104">Dieser Artikel gilt für Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="b0e97-104">This article applies to Microsoft 365 Business Premium.</span></span>

## <a name="edit-an-app-management-policy-for-windows-10"></a><span data-ttu-id="b0e97-105">Bearbeiten einer App-Verwaltungsrichtlinie für Windows 10</span><span class="sxs-lookup"><span data-stu-id="b0e97-105">Edit an app management policy for Windows 10</span></span>

1. <span data-ttu-id="b0e97-106">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="b0e97-106">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>     
2. <span data-ttu-id="b0e97-107">Wählen Sie im  linken Navigationsgerät \> **Geräterichtlinien aus.**</span><span class="sxs-lookup"><span data-stu-id="b0e97-107">On the left nav, choose **Devices** \> **Policies** .</span></span>
1. <span data-ttu-id="b0e97-108">Wählen Sie eine vorhandene Windows-App-Richtlinie und dann **Bearbeiten aus.**</span><span class="sxs-lookup"><span data-stu-id="b0e97-108">Choose an existing Windows app policy and then **Edit**.</span></span>
1. <span data-ttu-id="b0e97-109">Wählen **Sie Bearbeiten** neben einer Einstellung aus, die Sie ändern möchten, und **speichern.**</span><span class="sxs-lookup"><span data-stu-id="b0e97-109">Choose **Edit** next to a setting you want to change and then **Save**.</span></span>

## <a name="create-an-app-management-policy-for-windows-10"></a><span data-ttu-id="b0e97-110">Erstellen einer App-Verwaltungsrichtlinie für Windows 10</span><span class="sxs-lookup"><span data-stu-id="b0e97-110">Create an app management policy for Windows 10</span></span>

<span data-ttu-id="b0e97-111">Wenn Ihre Benutzer Arbeitsaufgaben auf ihren privaten Windows 10-Geräte ausführen, können Sie Ihre Daten auch auf diesen Geräten schützen.</span><span class="sxs-lookup"><span data-stu-id="b0e97-111">If your users have personal Windows 10 devices on which they perform work tasks, you can protect your data on those devices as well.</span></span>
  
1. <span data-ttu-id="b0e97-112">Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="b0e97-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span> 
2. <span data-ttu-id="b0e97-113">Wählen Sie im  linken Navigationsgerät \> **Geräterichtlinien** \> **hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="b0e97-113">On the left nav, choose **Devices** \> **Policies** \> **Add**.</span></span>
3. <span data-ttu-id="b0e97-114">Geben Sie im Bereich **Richtlinie hinzufügen** einen eindeutigen Namen für diese Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="b0e97-114">On the **Add policy** pane, enter a unique name for this policy.</span></span> 
4. <span data-ttu-id="b0e97-115">Wählen Sie unter **Richtlinientyp** die Option **Anwendungsverwaltung für Windows 10** aus.</span><span class="sxs-lookup"><span data-stu-id="b0e97-115">Under **Policy type**, choose **Application Management for Windows 10**.</span></span>
5. <span data-ttu-id="b0e97-116">Wählen **Sie unter Gerätetyp** entweder **Privat oder** **Unternehmensbesitz aus.**</span><span class="sxs-lookup"><span data-stu-id="b0e97-116">Under **Device type**, choose either **Personal** or **Company Owned**.</span></span>
6. <span data-ttu-id="b0e97-117">Die Option **Arbeitsdateien verschlüsseln** wird automatisch aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b0e97-117">The **Encrypt work files** is turned on automatically.</span></span> 
7. <span data-ttu-id="b0e97-118">Aktivieren Sie die Optionen **Benutzer daran hindern, Unternehmensdaten in persönliche Dateien zu kopieren** und **Benutzer zum Speichern aller Arbeitsdateien auf OneDrive for Business zwingen**, wenn Sie nicht zulassen möchten, dass Benutzer Arbeitsdateien auf den eigenen PCs speichern.</span><span class="sxs-lookup"><span data-stu-id="b0e97-118">Set **Prevent users from copying company data to personal files and force them to save work files to OneDrive for Business** to **On** if you don't want the users to save work files on their PC.</span></span> 
9. <span data-ttu-id="b0e97-119">Erweitern Sie **Daten auf Windows wiederherstellen.**</span><span class="sxs-lookup"><span data-stu-id="b0e97-119">Expand **Recover data on Windows devices**.</span></span> <span data-ttu-id="b0e97-120">Es wird empfohlen, dies zu **aktivieren.**</span><span class="sxs-lookup"><span data-stu-id="b0e97-120">We recommend that you turn it **On**.</span></span>
    <span data-ttu-id="b0e97-121">Bevor Sie zum Speicherort des Zertifikats des Datenwiederherstellungs-Agent navigieren können, müssen Sie zuerst ein Zertifikat erstellen.</span><span class="sxs-lookup"><span data-stu-id="b0e97-121">Before you can browse to the location of the Data Recovery Agent certificate, you have to first create one.</span></span> <span data-ttu-id="b0e97-122">Anweisungen finden Sie unter [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](/windows/security/information-protection/windows-information-protection/create-and-verify-an-efs-dra-certificate).</span><span class="sxs-lookup"><span data-stu-id="b0e97-122">For instructions, see [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](/windows/security/information-protection/windows-information-protection/create-and-verify-an-efs-dra-certificate).</span></span>
    
    <span data-ttu-id="b0e97-123">Standardmäßig werden Arbeitsdateien mithilfe eines geheimen Schlüssels verschlüsselt, der auf dem Gerät gespeichert und mit dem Profil des Benutzers verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="b0e97-123">By default, work files are encrypted using a secret key that is stored on the device and associated with the user's profile.</span></span> <span data-ttu-id="b0e97-124">Nur der Benutzer kann die Datei öffnen und entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="b0e97-124">Only the user can open and decrypt the file.</span></span> <span data-ttu-id="b0e97-125">Wenn ein Gerät jedoch verloren geht oder ein Benutzers entfernt wird, kann eine Datei im verschlüsselten Zustand zurückbleiben.</span><span class="sxs-lookup"><span data-stu-id="b0e97-125">However, if a device is lost or a user is removed, a file can be stuck in an encrypted state.</span></span> <span data-ttu-id="b0e97-126">Ein Administrator kann das Data Recovery Agent (DRA)-Zertifikat verwenden, um die Datei zu entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="b0e97-126">An admin can use the Data Recovery Agent (DRA) certificate to decrypt the file.</span></span>
    
    ![Browse to Data Recovery Agent certificate.](../media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. <span data-ttu-id="b0e97-128">Erweitern **Sie Weitere Netzwerk- und Cloudstandorte** schützen, wenn Sie zusätzliche Domänen oder SharePoint Onlinestandorte hinzufügen möchten, um sicherzustellen, dass Dateien in allen aufgeführten Apps geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="b0e97-128">Expand **Protect additional network and cloud locations** if you want to add additional domains or SharePoint Online locations to make sure that files in all the listed apps are protected.</span></span> <span data-ttu-id="b0e97-129">Wenn Sie für eines der Felder mehr als ein Element eingeben müssen, verwenden Sie ein Semikolon (;) zwischen den Elementen.</span><span class="sxs-lookup"><span data-stu-id="b0e97-129">If you need to enter more than one item for either field, use a semicolon (;) between the items.</span></span>
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](../media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. <span data-ttu-id="b0e97-p104">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span><span class="sxs-lookup"><span data-stu-id="b0e97-p104">Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.</span></span>
12. <span data-ttu-id="b0e97-133">Wählen Sie schließlich **Hinzufügen** aus, um die Richtlinie zu speichern, und weisen Sie sie Geräten zu.</span><span class="sxs-lookup"><span data-stu-id="b0e97-133">Finally, choose **Add** to save the policy, and assign it to devices.</span></span>