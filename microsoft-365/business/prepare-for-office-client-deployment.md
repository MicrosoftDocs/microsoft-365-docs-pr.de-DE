---
title: Vorbereiten der Office-Clientbereitstellung durch Microsoft 365 Business
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 10/31/2017
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: In diesem Artikel erfahren Sie, wie Sie die 32-Bit-Office-Apps auf Windows 10-Computern automatisch installieren und auf dem neuesten Stand halten.
ms.openlocfilehash: fa5b2ce1852ebdb1e76c1fa844793fee56af3d68
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593617"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business"></a><span data-ttu-id="91d8b-103">Vorbereiten der Office-Clientbereitstellung durch Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="91d8b-103">Prepare for Office client deployment by Microsoft 365 Business</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="91d8b-104">Vorbereiten der automatischen Installation von Office-Apps auf Clientcomputern</span><span class="sxs-lookup"><span data-stu-id="91d8b-104">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="91d8b-105">Sie können Microsoft 365 Business verwenden, um die 32-Bit-Office-Apps auf Windows 10-Computern automatisch zu installieren und diese mit Updates auf dem neuesten Stand zu halten.</span><span class="sxs-lookup"><span data-stu-id="91d8b-105">You can use Microsoft 365 Business to automatically install the 32-bit Office apps on Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="91d8b-106">Die automatische Installation funktioniert am besten, wenn sich der Computer des Endbenutzers in Windows 10 Business befindet und:</span><span class="sxs-lookup"><span data-stu-id="91d8b-106">Automatic installation works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="91d8b-107">Es sind keine Office-Desktop-Apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access und OneDrive) vorhanden.</span><span class="sxs-lookup"><span data-stu-id="91d8b-107">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="91d8b-108">oder</span><span class="sxs-lookup"><span data-stu-id="91d8b-108">or</span></span>
    
- <span data-ttu-id="91d8b-109">Auf dem Computer ist eine Version von Office Klick-und-Los installiert.</span><span class="sxs-lookup"><span data-stu-id="91d8b-109">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="91d8b-110">Wenn Sie feststellen möchten, ob Sie über die Office Klick-und-Los-Version verfügen, wechseln Sie in einer beliebigen Office-App zu **Datei** \> **Konto** ( **Office-Konto** in Outlook).</span><span class="sxs-lookup"><span data-stu-id="91d8b-110">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook).</span></span> <span data-ttu-id="91d8b-111">Wenn Office- **Updates** wie in der folgenden Abbildung dargestellt angezeigt werden, wurde die Installation mithilfe von Klick-und-Los ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="91d8b-111">If you see **Office Updates** as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="91d8b-113">**Wer profitiert von dieser Funktion**</span><span class="sxs-lookup"><span data-stu-id="91d8b-113">**Who benefits from having this feature**</span></span>
  
<span data-ttu-id="91d8b-114">Der Endbenutzer, für dessen PC Folgendes zutrifft:</span><span class="sxs-lookup"><span data-stu-id="91d8b-114">The end user whose PC:</span></span>
  
- <span data-ttu-id="91d8b-115">**Verfügt** über eine Windows 10 Business-Benutzerlizenz, eine aktive Microsoft 365 Business-Lizenz, Windows 10 Creators Update und ist in Azure Active Directory eingebunden.</span><span class="sxs-lookup"><span data-stu-id="91d8b-115">**Has**  a Windows 10 Business user license, an active Microsoft 365 Business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="91d8b-116">Verfügt **nicht über** 64-Bit-Office-Apps (Beispiel: Word, Excel, PowerPoint).</span><span class="sxs-lookup"><span data-stu-id="91d8b-116">**Doesn't have** 64-bit Office apps (example: Word, Excel, PowerPoint).</span></span> <span data-ttu-id="91d8b-117">Wenn 64-Bit-Office-Apps erforderlich sind, ist dieses Feature nicht geeignet, da es keine Unterstützung für das Auslösen einer 64-Bit-2016-Klick-und-Los-Version von Office über die Microsoft 365 Business-Verwaltungskonsole gibt.</span><span class="sxs-lookup"><span data-stu-id="91d8b-117">If 64-bit Office apps are required, then this feature isn't a good fit because there's no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 Business admin console.</span></span> 
    
- <span data-ttu-id="91d8b-118">Verfügt **nicht über** 2016 eigenständige Windows Installer (MSI)-Apps (beispielsweise Visio oder Project).</span><span class="sxs-lookup"><span data-stu-id="91d8b-118">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project).</span></span> <span data-ttu-id="91d8b-119">Microsoft 365 Business aktualisiert Office auf die Klick-und-Los-Version von Office 2016 und funktioniert nicht mit Office 2016 MSI-eigenständigen apps.</span><span class="sxs-lookup"><span data-stu-id="91d8b-119">Microsoft 365 Business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="91d8b-120">Die folgende Tabelle zeigt, welche Aktion die Endbenutzer/Administratoren je nach Anfangsstatus möglicherweise ausführen müssen, um eine erfolgreiche 32-Bit-Klick-und-Los-Version der Office-Bereitstellung über die Microsoft 365 Business Admin Console zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="91d8b-120">The following table shows what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 Business admin console.</span></span>
  
|<span data-ttu-id="91d8b-121">**Status "Office-Installation starten"**</span><span class="sxs-lookup"><span data-stu-id="91d8b-121">**Starting Office install status**</span></span>|<span data-ttu-id="91d8b-122">**Zu ergreifende Maßnahme vor Microsoft 365 Business Office-Installation**</span><span class="sxs-lookup"><span data-stu-id="91d8b-122">**Action to take before Microsoft 365 Business Office install**</span></span>|<span data-ttu-id="91d8b-123">**Endstatus**</span><span class="sxs-lookup"><span data-stu-id="91d8b-123">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="91d8b-124">Keine Office-Suite installiert</span><span class="sxs-lookup"><span data-stu-id="91d8b-124">No Office suite installed</span></span>  <br/> |<span data-ttu-id="91d8b-125">Keine</span><span class="sxs-lookup"><span data-stu-id="91d8b-125">None</span></span>  <br/> |<span data-ttu-id="91d8b-126">Office 2016 32-Bit wird mithilfe von Klick-und-Los installiert</span><span class="sxs-lookup"><span data-stu-id="91d8b-126">Office 2016 32-bit is installed by using Click-to-Run</span></span>  <br/> |
|<span data-ttu-id="91d8b-127">Vorhandene 32-Bit-Klick-und-Los-Version von Office (2016 oder früher) und keine eigenständigen Apps</span><span class="sxs-lookup"><span data-stu-id="91d8b-127">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="91d8b-128">Keine</span><span class="sxs-lookup"><span data-stu-id="91d8b-128">None</span></span>  <br/> |<span data-ttu-id="91d8b-129">Upgrade auf die neueste 32-Bit-Klick-und-Los-Version von Office 2016, je nach Bedarf **\***</span><span class="sxs-lookup"><span data-stu-id="91d8b-129">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="91d8b-130">Vorhandene Klick-und-Los-32-Bit-Version von Office-und Klick-und-Los-32-Bit-oder 64-Bit-eigenständigen Office-Apps (beispielsweise Visio, Project)</span><span class="sxs-lookup"><span data-stu-id="91d8b-130">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32-bit or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="91d8b-131">Keine</span><span class="sxs-lookup"><span data-stu-id="91d8b-131">None</span></span>  <br/> |<span data-ttu-id="91d8b-132">Eigenständige apps sind davon nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="91d8b-132">Standalone apps aren't affected.</span></span> <span data-ttu-id="91d8b-133">Suite wird auf 32-Bit-Klick-und-Los-Version von Office 2016 aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="91d8b-133">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="91d8b-134">Vorhandene 32-Bit-Klick-und-Los-Version von Office und alle eigenständigen 32-Bit- oder 64-Bit-MSI-Office-Apps (mit Ausnahme von 2016)</span><span class="sxs-lookup"><span data-stu-id="91d8b-134">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="91d8b-135">Keine</span><span class="sxs-lookup"><span data-stu-id="91d8b-135">None</span></span>  <br/> |<span data-ttu-id="91d8b-136">Eigenständige apps sind davon nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="91d8b-136">Standalone apps aren't affected.</span></span> <span data-ttu-id="91d8b-137">Suite wird auf 32-Bit-Klick-und-Los-Version von Office 2016 aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="91d8b-137">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="91d8b-138">Beliebige vorhandene 64-Bit-Klick-und-Los-Version von Office</span><span class="sxs-lookup"><span data-stu-id="91d8b-138">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="91d8b-139">Deinstallieren Sie die 64-Bit-Office-Apps, wenn es OK ist, um Sie durch 32-Bit-Office-Apps zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="91d8b-139">Uninstall the 64-bit Office apps, if it's OK to replace them with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="91d8b-140">Wenn die 64-Bit-Office-Apps entfernt wurden, wird die 32-Bit-Klick-und-Los-Version von Office 2016 installiert</span><span class="sxs-lookup"><span data-stu-id="91d8b-140">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="91d8b-141">Eine vorhandene MSI-Installation von Office 2016 mit oder ohne eigenständige Apps</span><span class="sxs-lookup"><span data-stu-id="91d8b-141">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="91d8b-142">MSI-Office 2016 deinstallieren</span><span class="sxs-lookup"><span data-stu-id="91d8b-142">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="91d8b-p106">Die 32-Bit-Klick-und-Los-Version von Office 2016 wird installiert. Keine Änderung an eigenständigen Apps</span><span class="sxs-lookup"><span data-stu-id="91d8b-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="91d8b-145">Vorhandene MSI-Installation von Office 2013 (oder früher) und/oder eigenständigen Office-Apps</span><span class="sxs-lookup"><span data-stu-id="91d8b-145">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="91d8b-146">Keine</span><span class="sxs-lookup"><span data-stu-id="91d8b-146">None</span></span>  <br/> |<span data-ttu-id="91d8b-147">32-Bit-Klick-und-Los-Version von Office 2016 mit der bereits vorhandenen MSI-Office-Installation (und eigenständigen Apps) existieren nebeneinander.</span><span class="sxs-lookup"><span data-stu-id="91d8b-147">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="91d8b-148">**(\*) Hinweis:** Führt aufgrund eines bekannten Fehlers kein Upgrade auf die 32-Bit-Klick-und-Los-Version von Office 2016 durch.</span><span class="sxs-lookup"><span data-stu-id="91d8b-148">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug.</span></span> <span data-ttu-id="91d8b-149">Eine Korrektur wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="91d8b-149">A fix is in progress.</span></span> 
  