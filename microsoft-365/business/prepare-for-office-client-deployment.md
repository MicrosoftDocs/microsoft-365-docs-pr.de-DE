---
title: Vorbereiten der Office-Clientbereitstellung durch Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 10/31/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Erfahren Sie, wie automatisch die 32-Bit-Office-apps auf Windows 10 Computern installieren und aufbewahrt aktualisiert werden.
ms.openlocfilehash: 16a8230d60157f1c6731ac639d89533b05aa3afe
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26867556"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business"></a><span data-ttu-id="2fc0e-103">Vorbereiten der Office-Clientbereitstellung durch Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="2fc0e-103">Prepare for Office client deployment by Microsoft 365 Business</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="2fc0e-104">Vorbereiten der automatischen Installation von Office-Apps auf Clientcomputern</span><span class="sxs-lookup"><span data-stu-id="2fc0e-104">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="2fc0e-105">Sie können die 32-Bit-Office-Apps mithilfe von Microsoft 365 Business auf Windows 10-Computern automatisch installieren und mit Updates auf dem neuesten Stand halten.</span><span class="sxs-lookup"><span data-stu-id="2fc0e-105">You can use Microsoft 365 Business to automatically install the 32-bit Office apps to Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="2fc0e-106">Das funktioniert am besten, wenn auf dem Computer des Endbenutzers Windows 10 Business ausgeführt wird und außerdem Folgendes zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2fc0e-106">This works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="2fc0e-107">Es sind keine Office-Desktop-Apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access und OneDrive) vorhanden.</span><span class="sxs-lookup"><span data-stu-id="2fc0e-107">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="2fc0e-108">oder</span><span class="sxs-lookup"><span data-stu-id="2fc0e-108">or</span></span>
    
- <span data-ttu-id="2fc0e-109">Auf dem Computer ist eine Version von Office Klick-und-Los installiert.</span><span class="sxs-lookup"><span data-stu-id="2fc0e-109">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="2fc0e-p101">Wenn Sie feststellen möchten, ob Sie über die Office Klick-und-Los-Version verfügen, wechseln Sie in einer beliebigen Office-App zu **Datei** \> **Konto** ( **Office-Konto** in Outlook). Wenn "Office-Updates" wie in der nachstehenden Abbildung angezeigt wird, erfolgte die Installation mithilfe von Klick-und-Los.</span><span class="sxs-lookup"><span data-stu-id="2fc0e-p101">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook). If you see Office Updates as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="2fc0e-113">**Wer von diesem Feature profitiert**</span><span class="sxs-lookup"><span data-stu-id="2fc0e-113">**Who will benefit from having this feature**</span></span>
  
<span data-ttu-id="2fc0e-114">Der Endbenutzer, für dessen PC Folgendes zutrifft:</span><span class="sxs-lookup"><span data-stu-id="2fc0e-114">The end user whose PC:</span></span>
  
- <span data-ttu-id="2fc0e-115">**Verfügt** über eine Windows 10 Business-Benutzerlizenz, eine aktive Microsoft 365 Business-Lizenz, Windows 10 Creators Update und ist in Azure Active Directory eingebunden.</span><span class="sxs-lookup"><span data-stu-id="2fc0e-115">**Has**  a Windows 10 Business user license, an active Microsoft 365 Business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="2fc0e-p102">**Verfügt über keine** 64-Bit-Office-Apps (Beispiel: Word, Excel, PowerPoint). Wenn die 64-Bit-Office-Apps benötigt werden, ist dieses Feature ungeeignet, weil es keinen Support für das Auslösen einer 64-Bit-Version von Office 2016 Klick-und-Los über die Microsoft 365 Business-Verwaltungskonsole gibt.</span><span class="sxs-lookup"><span data-stu-id="2fc0e-p102">**Doesn't have** 64-bit Office apps (example: Word, Excel, Powerpoint). If 64-bit Office apps are required, then this feature is not a good fit because there is no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 Business admin console.</span></span> 
    
- <span data-ttu-id="2fc0e-p103">**Verfügt über keine** eigenständigen 2016 Windows Installer-Apps (MSI-Apps) wie z. B. Visio oder Project. Microsoft 365 Business aktualisiert Office auf die Klick-und-Los-Version von Office 2016 und funktioniert nicht bei eigenständigen Office 2016-MSI-Apps.</span><span class="sxs-lookup"><span data-stu-id="2fc0e-p103">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project). Microsoft 365 Business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="2fc0e-120">In der nachstehenden Tabelle wird erläutert, welche Maßnahme die Endbenutzer/Administratoren - je nach ihrem Anfangsstatus - möglicherweise ergreifen müssen, um eine erfolgreiche 32-Bit-Klick-und-Los-Version einer Office-Bereitstellung über die Microsoft 365 Business-Verwaltungskonsole zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2fc0e-120">The following table details what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 Business admin console.</span></span>
  
|<span data-ttu-id="2fc0e-121">**Status "Office-Installation starten"**</span><span class="sxs-lookup"><span data-stu-id="2fc0e-121">**Starting Office install status**</span></span>|<span data-ttu-id="2fc0e-122">**Zu ergreifende Maßnahme vor Microsoft 365 Business Office-Installation**</span><span class="sxs-lookup"><span data-stu-id="2fc0e-122">**Action to take before Microsoft 365 Business Office install**</span></span>|<span data-ttu-id="2fc0e-123">**Endstatus**</span><span class="sxs-lookup"><span data-stu-id="2fc0e-123">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2fc0e-124">Keine Office-Suite installiert</span><span class="sxs-lookup"><span data-stu-id="2fc0e-124">No Office suite installed</span></span>  <br/> |<span data-ttu-id="2fc0e-125">Keine</span><span class="sxs-lookup"><span data-stu-id="2fc0e-125">None</span></span>  <br/> |<span data-ttu-id="2fc0e-126">Die 32-Bit-Version von Office 2016 wurde mithilfe von Klick-und-Los installiert</span><span class="sxs-lookup"><span data-stu-id="2fc0e-126">Office 2016 32-bit is installed by using click-to-run</span></span>  <br/> |
|<span data-ttu-id="2fc0e-127">Vorhandene 32-Bit-Klick-und-Los-Version von Office (2016 oder früher) und keine eigenständigen Apps</span><span class="sxs-lookup"><span data-stu-id="2fc0e-127">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="2fc0e-128">Keine</span><span class="sxs-lookup"><span data-stu-id="2fc0e-128">None</span></span>  <br/> |<span data-ttu-id="2fc0e-129">Upgrade auf die neueste 32-Bit-Klick-und-Los-Version von Office 2016, je nach Bedarf **\***</span><span class="sxs-lookup"><span data-stu-id="2fc0e-129">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="2fc0e-130">Vorhandene 32-Bit-Klick-und-Los-Version von Office und eigenständige 32- oder 64-Bit-Klick-und-Los-Office-Apps (z. B. Visio, Project)</span><span class="sxs-lookup"><span data-stu-id="2fc0e-130">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32- or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="2fc0e-131">Keine</span><span class="sxs-lookup"><span data-stu-id="2fc0e-131">None</span></span>  <br/> |<span data-ttu-id="2fc0e-p104">Eigenständige Apps sind hiervon nicht betroffen. Suite wird auf 32-Bit-Klick-und-Los-Version von Office 2016 aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="2fc0e-p104">Standalone apps are not affected. Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="2fc0e-134">Vorhandene 32-Bit-Klick-und-Los-Version von Office und alle eigenständigen 32-Bit- oder 64-Bit-MSI-Office-Apps (mit Ausnahme von 2016)</span><span class="sxs-lookup"><span data-stu-id="2fc0e-134">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="2fc0e-135">Keine</span><span class="sxs-lookup"><span data-stu-id="2fc0e-135">None</span></span>  <br/> |<span data-ttu-id="2fc0e-p105">Eigenständige Apps sind hiervon nicht betroffen. Suite wird auf 32-Bit-Klick-und-Los-Version von Office 2016 aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="2fc0e-p105">Standalone apps are not affected. Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="2fc0e-138">Beliebige vorhandene 64-Bit-Klick-und-Los-Version von Office</span><span class="sxs-lookup"><span data-stu-id="2fc0e-138">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="2fc0e-139">64-Bit-Office-Apps deinstallieren, wenn es OK ist, dass sie durch die 32-Bit-Office-Apps ersetzt werden</span><span class="sxs-lookup"><span data-stu-id="2fc0e-139">Uninstall the 64-bit Office apps, if it is OK to replace it with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="2fc0e-140">Wenn die 64-Bit-Office-Apps entfernt wurden, wird die 32-Bit-Klick-und-Los-Version von Office 2016 installiert</span><span class="sxs-lookup"><span data-stu-id="2fc0e-140">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="2fc0e-141">Eine vorhandene MSI-Installation von Office 2016 mit oder ohne eigenständige Apps</span><span class="sxs-lookup"><span data-stu-id="2fc0e-141">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="2fc0e-142">MSI-Office 2016 deinstallieren</span><span class="sxs-lookup"><span data-stu-id="2fc0e-142">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="2fc0e-p106">Die 32-Bit-Klick-und-Los-Version von Office 2016 wird installiert. Keine Änderung an eigenständigen Apps</span><span class="sxs-lookup"><span data-stu-id="2fc0e-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="2fc0e-145">Vorhandene MSI-Installation von Office 2013 (oder früher) und/oder eigenständigen Office-Apps</span><span class="sxs-lookup"><span data-stu-id="2fc0e-145">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="2fc0e-146">Keine</span><span class="sxs-lookup"><span data-stu-id="2fc0e-146">None</span></span>  <br/> |<span data-ttu-id="2fc0e-147">32-Bit-Klick-und-Los-Version von Office 2016 mit der bereits vorhandenen MSI-Office-Installation (und eigenständigen Apps) existieren nebeneinander.</span><span class="sxs-lookup"><span data-stu-id="2fc0e-147">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="2fc0e-p107">**(\*) Hinweis:** Führt aufgrund eines bekannten Fehlers kein Upgrade auf die 32-Bit-Klick-und-Los-Version von Office 2016 durch. Eine Fehlerkorrektur ist in Bearbeitung.</span><span class="sxs-lookup"><span data-stu-id="2fc0e-p107">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug. Fix is in progress.</span></span> 
  


