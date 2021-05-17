---
title: Vorbereiten der Office Clientbereitstellung durch Microsoft 365 Business
f1.keywords:
- CSH
ms.author: efrene
author: efrene
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: Erfahren Sie, wie Sie die 32-Bit-Office auf Windows 10 installieren und aktualisieren.
ms.openlocfilehash: 868d06fadfef0f55b41131b7fdfbb368b9128405
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580052"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a><span data-ttu-id="abe33-103">Vorbereiten der Office Clientbereitstellung durch Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="abe33-103">Prepare for Office client deployment by Microsoft 365 for business</span></span>

<span data-ttu-id="abe33-104">Dieser Artikel gilt für Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="abe33-104">This article applies to Microsoft 365 Business Premium.</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="abe33-105">Vorbereiten der automatischen Installation von Office-Apps auf Clientcomputern</span><span class="sxs-lookup"><span data-stu-id="abe33-105">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="abe33-106">Sie können Microsoft 365 Business Premium verwenden, um die 32-Bit-Office auf Windows 10 zu installieren und mit Updates auf dem neuesten Stand zu halten.</span><span class="sxs-lookup"><span data-stu-id="abe33-106">You can use Microsoft 365 Business Premium to automatically install the 32-bit Office apps on Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="abe33-107">Die automatische Installation funktioniert am besten, wenn sich der Computer des Endbenutzers auf Windows 10 Business und:</span><span class="sxs-lookup"><span data-stu-id="abe33-107">Automatic installation works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="abe33-108">Es sind keine Office-Desktop-Apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access und OneDrive) vorhanden.</span><span class="sxs-lookup"><span data-stu-id="abe33-108">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="abe33-109">oder</span><span class="sxs-lookup"><span data-stu-id="abe33-109">or</span></span>
    
- <span data-ttu-id="abe33-110">Auf dem Computer ist eine Version von Office Klick-und-Los installiert.</span><span class="sxs-lookup"><span data-stu-id="abe33-110">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="abe33-111">Wenn Sie feststellen möchten, ob Sie über die Office Klick-und-Los-Version verfügen, wechseln Sie in einer beliebigen Office-App zu **Datei** \> **Konto** ( **Office-Konto** in Outlook).</span><span class="sxs-lookup"><span data-stu-id="abe33-111">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook).</span></span> <span data-ttu-id="abe33-112">Wenn Sie Office **Updates wie** in der folgenden Abbildung gezeigt sehen, wurde die Installation mithilfe von Klick-und-Ausführen durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="abe33-112">If you see **Office Updates** as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="abe33-114">**Wer von diesem Feature profitieren**</span><span class="sxs-lookup"><span data-stu-id="abe33-114">**Who benefits from having this feature**</span></span>
  
<span data-ttu-id="abe33-115">Der Endbenutzer, für dessen PC Folgendes zutrifft:</span><span class="sxs-lookup"><span data-stu-id="abe33-115">The end user whose PC:</span></span>
  
- <span data-ttu-id="abe33-116">**Verfügt** über Windows 10 Business Benutzerlizenz, eine aktive Microsoft 365 business-Lizenz, Windows 10 Creators Update und ist Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="abe33-116">**Has**  a Windows 10 Business user license, an active Microsoft 365 for business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="abe33-117">**Hat keine** 64-Bit-Office (Beispiel: Word, Excel, PowerPoint).</span><span class="sxs-lookup"><span data-stu-id="abe33-117">**Doesn't have** 64-bit Office apps (example: Word, Excel, PowerPoint).</span></span> <span data-ttu-id="abe33-118">Wenn 64-Bit-Office-Apps erforderlich sind, ist dieses Feature nicht geeignet, da es keine Unterstützung für das Auslösen einer 64-Bit-2016-Klick-und-Ausführen-Version von Office von der Microsoft 365 for Business Admin Console gibt.</span><span class="sxs-lookup"><span data-stu-id="abe33-118">If 64-bit Office apps are required, then this feature isn't a good fit because there's no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 for business admin console.</span></span> 
    
- <span data-ttu-id="abe33-119">**Enthält keine** eigenständigen 2016 Windows Installer (MSI) (z. B. Visio oder Project).</span><span class="sxs-lookup"><span data-stu-id="abe33-119">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project).</span></span> <span data-ttu-id="abe33-120">Microsoft 365 business upgrades Office auf die Click-to-Run-Version von Office 2016 und dies funktioniert nicht mit Office 2016 MSI-eigenständigen Apps.</span><span class="sxs-lookup"><span data-stu-id="abe33-120">Microsoft 365 for business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="abe33-121">Die folgende Tabelle zeigt, welche Aktion endbenutzer/admins je nach Startzustand ausführen müssen, um eine erfolgreiche 32-Bit-Klick-und-Ausführen-Version der Office-Bereitstellung von der Microsoft 365 for Business Admin Console zu haben.</span><span class="sxs-lookup"><span data-stu-id="abe33-121">The following table shows what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 for business admin console.</span></span>
  
|<span data-ttu-id="abe33-122">**Status "Office-Installation starten"**</span><span class="sxs-lookup"><span data-stu-id="abe33-122">**Starting Office install status**</span></span>|<span data-ttu-id="abe33-123">**Aktion vor der Installation Microsoft 365 für Office Unternehmen**</span><span class="sxs-lookup"><span data-stu-id="abe33-123">**Action to take before Microsoft 365 for business Office install**</span></span>|<span data-ttu-id="abe33-124">**Endstatus**</span><span class="sxs-lookup"><span data-stu-id="abe33-124">**End state**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="abe33-125">Keine Office-Suite installiert</span><span class="sxs-lookup"><span data-stu-id="abe33-125">No Office suite installed</span></span>  <br/> |<span data-ttu-id="abe33-126">Keine</span><span class="sxs-lookup"><span data-stu-id="abe33-126">None</span></span>  <br/> |<span data-ttu-id="abe33-127">Office 32-Bit 2016 wird mithilfe von Klick-und-Ausführen installiert</span><span class="sxs-lookup"><span data-stu-id="abe33-127">Office 2016 32-bit is installed by using Click-to-Run</span></span>  <br/> |
|<span data-ttu-id="abe33-128">Vorhandene 32-Bit-Klick-und-Los-Version von Office (2016 oder früher) und keine eigenständigen Apps</span><span class="sxs-lookup"><span data-stu-id="abe33-128">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="abe33-129">Keine</span><span class="sxs-lookup"><span data-stu-id="abe33-129">None</span></span>  <br/> |<span data-ttu-id="abe33-130">Upgrade auf die neueste 32-Bit-Klick-und-Los-Version von Office 2016, je nach Bedarf **\***</span><span class="sxs-lookup"><span data-stu-id="abe33-130">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="abe33-131">Vorhandene 32-Bit-Click-to-Run-Version von Office- und Click-to-Run-32-Bit- oder 64-Bit-eigenständigen Office-Apps (z. B. Visio, Project)</span><span class="sxs-lookup"><span data-stu-id="abe33-131">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32-bit or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="abe33-132">Keine</span><span class="sxs-lookup"><span data-stu-id="abe33-132">None</span></span>  <br/> |<span data-ttu-id="abe33-133">Eigenständige Apps sind nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="abe33-133">Standalone apps aren't affected.</span></span> <span data-ttu-id="abe33-134">Suite wird auf 32-Bit-Klick-und-Los-Version von Office 2016 aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="abe33-134">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="abe33-135">Vorhandene 32-Bit-Klick-und-Los-Version von Office und alle eigenständigen 32-Bit- oder 64-Bit-MSI-Office-Apps (mit Ausnahme von 2016)</span><span class="sxs-lookup"><span data-stu-id="abe33-135">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="abe33-136">Keine</span><span class="sxs-lookup"><span data-stu-id="abe33-136">None</span></span>  <br/> |<span data-ttu-id="abe33-137">Eigenständige Apps sind nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="abe33-137">Standalone apps aren't affected.</span></span> <span data-ttu-id="abe33-138">Suite wird auf 32-Bit-Klick-und-Los-Version von Office 2016 aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="abe33-138">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> ||||
|<span data-ttu-id="abe33-139">Beliebige vorhandene 64-Bit-Klick-und-Los-Version von Office</span><span class="sxs-lookup"><span data-stu-id="abe33-139">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="abe33-140">Deinstallieren der 64-Bit-Office-Apps, wenn es in Ordnung ist, sie durch 32-Bit-Apps Office ersetzen</span><span class="sxs-lookup"><span data-stu-id="abe33-140">Uninstall the 64-bit Office apps, if it's OK to replace them with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="abe33-141">Wenn die 64-Bit-Office-Apps entfernt wurden, wird die 32-Bit-Klick-und-Los-Version von Office 2016 installiert</span><span class="sxs-lookup"><span data-stu-id="abe33-141">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="abe33-142">Eine vorhandene MSI-Installation von Office 2016 mit oder ohne eigenständige Apps</span><span class="sxs-lookup"><span data-stu-id="abe33-142">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="abe33-143">MSI-Office 2016 deinstallieren</span><span class="sxs-lookup"><span data-stu-id="abe33-143">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="abe33-p106">Die 32-Bit-Klick-und-Los-Version von Office 2016 wird installiert. Keine Änderung an eigenständigen Apps</span><span class="sxs-lookup"><span data-stu-id="abe33-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="abe33-146">Vorhandene MSI-Installation von Office 2013 (oder früher) und/oder eigenständigen Office-Apps</span><span class="sxs-lookup"><span data-stu-id="abe33-146">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="abe33-147">Keine</span><span class="sxs-lookup"><span data-stu-id="abe33-147">None</span></span>  <br/> |<span data-ttu-id="abe33-148">32-Bit-Klick-und-Los-Version von Office 2016 mit der bereits vorhandenen MSI-Office-Installation (und eigenständigen Apps) existieren nebeneinander.</span><span class="sxs-lookup"><span data-stu-id="abe33-148">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="abe33-149">**(\*) Hinweis:** Führt aufgrund eines bekannten Fehlers kein Upgrade auf die 32-Bit-Klick-und-Los-Version von Office 2016 durch.</span><span class="sxs-lookup"><span data-stu-id="abe33-149">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug.</span></span> <span data-ttu-id="abe33-150">Es wird eine Korrektur ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="abe33-150">A fix is in progress.</span></span> 
  
