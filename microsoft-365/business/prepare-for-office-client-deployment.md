---
title: Vorbereiten der Office Clientbereitstellung durch Microsoft 365 for Business
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
description: Erfahren Sie, wie Sie die 32-Bit-Office-Apps automatisch auf Windows 10 Computern installieren und auf dem neuesten Stand halten.
ms.openlocfilehash: 843be426d817da1173769b3b66dc4c054179f0fd
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924225"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a><span data-ttu-id="1141b-103">Vorbereiten der Office Clientbereitstellung durch Microsoft 365 for Business</span><span class="sxs-lookup"><span data-stu-id="1141b-103">Prepare for Office client deployment by Microsoft 365 for business</span></span>

<span data-ttu-id="1141b-104">Dieser Artikel bezieht sich auf Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="1141b-104">This article applies to Microsoft 365 Business Premium.</span></span>

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a><span data-ttu-id="1141b-105">Vorbereiten der automatischen Installation von Office-Apps auf Clientcomputern</span><span class="sxs-lookup"><span data-stu-id="1141b-105">Prepare to automatically install Office apps to client computers</span></span>

<span data-ttu-id="1141b-106">Sie können Microsoft 365 Business Premium verwenden, um die 32-Bit-Office-Apps automatisch auf Windows 10 Computern zu installieren und sie mit Updates auf dem aktuellen Stand zu halten.</span><span class="sxs-lookup"><span data-stu-id="1141b-106">You can use Microsoft 365 Business Premium to automatically install the 32-bit Office apps on Windows 10 computers and keep them current with updates.</span></span>
  
<span data-ttu-id="1141b-107">Die automatische Installation funktioniert am besten, wenn sich der Computer des Endbenutzers auf Windows 10 Business befindet und:</span><span class="sxs-lookup"><span data-stu-id="1141b-107">Automatic installation works best if the end user's computer is on Windows 10 Business and:</span></span>
  
- <span data-ttu-id="1141b-108">Es sind keine Office-Desktop-Apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access und OneDrive) vorhanden.</span><span class="sxs-lookup"><span data-stu-id="1141b-108">Doesn't have existing Office desktop apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access, and OneDrive).</span></span>
    
    <span data-ttu-id="1141b-109">oder</span><span class="sxs-lookup"><span data-stu-id="1141b-109">or</span></span>
    
- <span data-ttu-id="1141b-110">Auf dem Computer ist eine Version von Office Klick-und-Los installiert.</span><span class="sxs-lookup"><span data-stu-id="1141b-110">Has an existing version of Click-to-Run Office installed.</span></span>
    
<span data-ttu-id="1141b-111">Wenn Sie feststellen möchten, ob Sie über die Office Klick-und-Los-Version verfügen, wechseln Sie in einer beliebigen Office-App zu **Datei** \> **Konto** ( **Office-Konto** in Outlook).</span><span class="sxs-lookup"><span data-stu-id="1141b-111">To determine if you have the Click-to-Run version of Office, in any Office app go to **File** \> **Account** ( **Office Account** in Outlook).</span></span> <span data-ttu-id="1141b-112">Wenn **Office Updates** wie in der folgenden Abbildung dargestellt angezeigt wird, wurde die Installation mithilfe von Klick-und-Los durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="1141b-112">If you see **Office Updates** as shown in the following figure, then the installation was done by using Click-to-Run.</span></span> 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 <span data-ttu-id="1141b-114">**Wer Vorteile dieser Funktion**</span><span class="sxs-lookup"><span data-stu-id="1141b-114">**Who benefits from having this feature**</span></span>
  
<span data-ttu-id="1141b-115">Der Endbenutzer, für dessen PC Folgendes zutrifft:</span><span class="sxs-lookup"><span data-stu-id="1141b-115">The end user whose PC:</span></span>
  
- <span data-ttu-id="1141b-116">**Verfügt** über eine Windows 10 Business Benutzerlizenz, eine aktive Microsoft 365 für Unternehmen-Lizenz, Windows 10 Creators Update und ist Azure Active Directory beigetreten.</span><span class="sxs-lookup"><span data-stu-id="1141b-116">**Has**  a Windows 10 Business user license, an active Microsoft 365 for business license, Windows 10 Creators Update, and is joined to Azure Active Directory.</span></span> 
    
- <span data-ttu-id="1141b-117">**Verfügt nicht** über 64-Bit-Office-Apps (Beispiel: Word, Excel, PowerPoint).</span><span class="sxs-lookup"><span data-stu-id="1141b-117">**Doesn't have** 64-bit Office apps (example: Word, Excel, PowerPoint).</span></span> <span data-ttu-id="1141b-118">Wenn 64-Bit-Office-Apps erforderlich sind, eignet sich dieses Feature nicht gut, da es keine Unterstützung für das Auslösen einer 64-Bit-Klick-und-Los-Version von Office in der Microsoft 365 for Business-Administratorkonsole gibt.</span><span class="sxs-lookup"><span data-stu-id="1141b-118">If 64-bit Office apps are required, then this feature isn't a good fit because there's no support for triggering a 64-bit 2016 Click-to-Run version of Office from the Microsoft 365 for business admin console.</span></span> 
    
- <span data-ttu-id="1141b-119">**Verfügt nicht** über eigenständige 2016-Apps für Windows Installer (MSI) (z. B. Visio oder Project).</span><span class="sxs-lookup"><span data-stu-id="1141b-119">**Doesn't have** any 2016 Windows Installer (MSI) standalone apps (for example, Visio or Project).</span></span> <span data-ttu-id="1141b-120">Microsoft 365 for Business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with Office 2016 MSI standalone apps.</span><span class="sxs-lookup"><span data-stu-id="1141b-120">Microsoft 365 for business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with Office 2016 MSI standalone apps.</span></span> 
    
<span data-ttu-id="1141b-121">Die folgende Tabelle zeigt, welche Aktion Endbenutzer/Administratoren je nach Ihrem Anfangsstatus ausführen müssen, um eine erfolgreiche 32-Bit-Klick-und-Los-Version von Office Bereitstellung über die Microsoft 365 for Business-Verwaltungskonsole zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1141b-121">The following table shows what action the end users/admins may need to take, depending on their beginning state, to have a successful 32-bit Click-to-Run version of Office deployment from the Microsoft 365 for business admin console.</span></span><br/>


|<span data-ttu-id="1141b-122">Status "Office-Installation starten"</span><span class="sxs-lookup"><span data-stu-id="1141b-122">Starting Office install status</span></span>|<span data-ttu-id="1141b-123">Vor der Installation von Microsoft 365 for Business Office auszuführende Aktion</span><span class="sxs-lookup"><span data-stu-id="1141b-123">Action to take before Microsoft 365 for business Office install</span></span>|<span data-ttu-id="1141b-124">Endzustand</span><span class="sxs-lookup"><span data-stu-id="1141b-124">End state</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1141b-125">Keine Office-Suite installiert</span><span class="sxs-lookup"><span data-stu-id="1141b-125">No Office suite installed</span></span>  <br/> |<span data-ttu-id="1141b-126">Keine</span><span class="sxs-lookup"><span data-stu-id="1141b-126">None</span></span>  <br/> |<span data-ttu-id="1141b-127">Office 2016 32-Bit-Version wird mithilfe von Klick-und-Los installiert.</span><span class="sxs-lookup"><span data-stu-id="1141b-127">Office 2016 32-bit is installed by using Click-to-Run</span></span>  <br/> |
|<span data-ttu-id="1141b-128">Vorhandene 32-Bit-Klick-und-Los-Version von Office (2016 oder früher) und keine eigenständigen Apps</span><span class="sxs-lookup"><span data-stu-id="1141b-128">Existing Click-to-Run 32-bit version of Office (2016 or earlier) and no standalone apps</span></span>  <br/> |<span data-ttu-id="1141b-129">Keine</span><span class="sxs-lookup"><span data-stu-id="1141b-129">None</span></span>  <br/> |<span data-ttu-id="1141b-130">Upgrade auf die neueste 32-Bit-Klick-und-Los-Version von Office 2016, je nach Bedarf **\***</span><span class="sxs-lookup"><span data-stu-id="1141b-130">Upgraded to the latest 32-bit Click-to-Run version of Office 2016, as needed **\***</span></span> <br/> |
|<span data-ttu-id="1141b-131">Vorhandene Klick-und-Los-32-Bit-Version von Office und Klick-und-Los-32-Bit- oder eigenständige 64-Bit-Office-Apps (z. B. Visio, Project)</span><span class="sxs-lookup"><span data-stu-id="1141b-131">Existing Click-to-Run 32-bit version of Office and Click-to-Run 32-bit or 64-bit standalone Office apps (for example, Visio, Project)</span></span>  <br/> |<span data-ttu-id="1141b-132">Keine</span><span class="sxs-lookup"><span data-stu-id="1141b-132">None</span></span>  <br/> |<span data-ttu-id="1141b-133">Eigenständige Apps sind davon nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="1141b-133">Standalone apps aren't affected.</span></span> <span data-ttu-id="1141b-134">Suite wird auf 32-Bit-Klick-und-Los-Version von Office 2016 aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="1141b-134">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="1141b-135">Vorhandene 32-Bit-Klick-und-Los-Version von Office und alle eigenständigen 32-Bit- oder 64-Bit-MSI-Office-Apps (mit Ausnahme von 2016)</span><span class="sxs-lookup"><span data-stu-id="1141b-135">Existing Click-to-Run 32-bit version of Office and any 32-bit or 64-bit (except 2016) MSI standalone Office apps</span></span>  <br/> |<span data-ttu-id="1141b-136">Keine</span><span class="sxs-lookup"><span data-stu-id="1141b-136">None</span></span>  <br/> |<span data-ttu-id="1141b-137">Eigenständige Apps sind davon nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="1141b-137">Standalone apps aren't affected.</span></span> <span data-ttu-id="1141b-138">Suite wird auf 32-Bit-Klick-und-Los-Version von Office 2016 aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="1141b-138">Suite is upgraded to Click-to-Run 32-bit version of Office 2016</span></span>  <br/> |
|<span data-ttu-id="1141b-139">Beliebige vorhandene 64-Bit-Klick-und-Los-Version von Office</span><span class="sxs-lookup"><span data-stu-id="1141b-139">Any existing Click-to-Run 64-bit version of Office</span></span>  <br/> |<span data-ttu-id="1141b-140">Deinstallieren Sie die 64-Bit-Office-Apps, wenn es in Ordnung ist, sie durch 32-Bit-Office-Apps zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="1141b-140">Uninstall the 64-bit Office apps, if it's OK to replace them with 32-bit Office apps</span></span>  <br/> |<span data-ttu-id="1141b-141">Wenn die 64-Bit-Office-Apps entfernt wurden, wird die 32-Bit-Klick-und-Los-Version von Office 2016 installiert</span><span class="sxs-lookup"><span data-stu-id="1141b-141">If Office 64-bit apps are removed, the Click-to-Run 32-bit version of Office 2016 is installed</span></span>  <br/> |
|<span data-ttu-id="1141b-142">Eine vorhandene MSI-Installation von Office 2016 mit oder ohne eigenständige Apps</span><span class="sxs-lookup"><span data-stu-id="1141b-142">An existing MSI install of Office 2016 with or without standalone apps</span></span>  <br/> |<span data-ttu-id="1141b-143">MSI-Office 2016 deinstallieren</span><span class="sxs-lookup"><span data-stu-id="1141b-143">Uninstall MSI Office 2016.</span></span>  <br/> |<span data-ttu-id="1141b-p106">Die 32-Bit-Klick-und-Los-Version von Office 2016 wird installiert. Keine Änderung an eigenständigen Apps</span><span class="sxs-lookup"><span data-stu-id="1141b-p106">Click-to-Run 32-bit version of Office 2016 is installed. No change to standalone apps</span></span>  <br/> |
|<span data-ttu-id="1141b-146">Vorhandene MSI-Installation von Office 2013 (oder früher) und/oder eigenständigen Office-Apps</span><span class="sxs-lookup"><span data-stu-id="1141b-146">Existing MSI install of Office 2013 (or earlier) and/or standalone Office apps</span></span>  <br/> |<span data-ttu-id="1141b-147">Keine</span><span class="sxs-lookup"><span data-stu-id="1141b-147">None</span></span>  <br/> |<span data-ttu-id="1141b-148">32-Bit-Klick-und-Los-Version von Office 2016 mit der bereits vorhandenen MSI-Office-Installation (und eigenständigen Apps) existieren nebeneinander.</span><span class="sxs-lookup"><span data-stu-id="1141b-148">Click-to-Run 32-bit version of Office 2016 with the pre-existing MSI Office install (and standalone apps) exist side-by-side</span></span>  <br/> |
||||
   
 <span data-ttu-id="1141b-149">**(\*) Hinweis:** Führt aufgrund eines bekannten Fehlers kein Upgrade auf die 32-Bit-Klick-und-Los-Version von Office 2016 durch.</span><span class="sxs-lookup"><span data-stu-id="1141b-149">**(\*) Note:** Does not upgrade to Click-to-Run 32-bit version of Office 2016 due to a known bug.</span></span> <span data-ttu-id="1141b-150">Eine Korrektur wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1141b-150">A fix is in progress.</span></span> 
  
