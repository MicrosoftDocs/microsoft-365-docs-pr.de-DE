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
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a>Vorbereiten der Office Clientbereitstellung durch Microsoft 365 Business

Dieser Artikel gilt für Microsoft 365 Business Premium.

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>Vorbereiten der automatischen Installation von Office-Apps auf Clientcomputern

Sie können Microsoft 365 Business Premium verwenden, um die 32-Bit-Office auf Windows 10 zu installieren und mit Updates auf dem neuesten Stand zu halten.
  
Die automatische Installation funktioniert am besten, wenn sich der Computer des Endbenutzers auf Windows 10 Business und:
  
- Es sind keine Office-Desktop-Apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access und OneDrive) vorhanden.
    
    oder
    
- Auf dem Computer ist eine Version von Office Klick-und-Los installiert.
    
Wenn Sie feststellen möchten, ob Sie über die Office Klick-und-Los-Version verfügen, wechseln Sie in einer beliebigen Office-App zu **Datei** \> **Konto** ( **Office-Konto** in Outlook). Wenn Sie Office **Updates wie** in der folgenden Abbildung gezeigt sehen, wurde die Installation mithilfe von Klick-und-Ausführen durchgeführt. 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **Wer von diesem Feature profitieren**
  
Der Endbenutzer, für dessen PC Folgendes zutrifft:
  
- **Verfügt** über Windows 10 Business Benutzerlizenz, eine aktive Microsoft 365 business-Lizenz, Windows 10 Creators Update und ist Azure Active Directory. 
    
- **Hat keine** 64-Bit-Office (Beispiel: Word, Excel, PowerPoint). Wenn 64-Bit-Office-Apps erforderlich sind, ist dieses Feature nicht geeignet, da es keine Unterstützung für das Auslösen einer 64-Bit-2016-Klick-und-Ausführen-Version von Office von der Microsoft 365 for Business Admin Console gibt. 
    
- **Enthält keine** eigenständigen 2016 Windows Installer (MSI) (z. B. Visio oder Project). Microsoft 365 business upgrades Office auf die Click-to-Run-Version von Office 2016 und dies funktioniert nicht mit Office 2016 MSI-eigenständigen Apps. 
    
Die folgende Tabelle zeigt, welche Aktion endbenutzer/admins je nach Startzustand ausführen müssen, um eine erfolgreiche 32-Bit-Klick-und-Ausführen-Version der Office-Bereitstellung von der Microsoft 365 for Business Admin Console zu haben.
  
|**Status "Office-Installation starten"**|**Aktion vor der Installation Microsoft 365 für Office Unternehmen**|**Endstatus**|
|:-----|:-----|:-----|
|Keine Office-Suite installiert  <br/> |Keine  <br/> |Office 32-Bit 2016 wird mithilfe von Klick-und-Ausführen installiert  <br/> |
|Vorhandene 32-Bit-Klick-und-Los-Version von Office (2016 oder früher) und keine eigenständigen Apps  <br/> |Keine  <br/> |Upgrade auf die neueste 32-Bit-Klick-und-Los-Version von Office 2016, je nach Bedarf **\*** <br/> |
|Vorhandene 32-Bit-Click-to-Run-Version von Office- und Click-to-Run-32-Bit- oder 64-Bit-eigenständigen Office-Apps (z. B. Visio, Project)  <br/> |Keine  <br/> |Eigenständige Apps sind nicht betroffen. Suite wird auf 32-Bit-Klick-und-Los-Version von Office 2016 aktualisiert.  <br/> |
|Vorhandene 32-Bit-Klick-und-Los-Version von Office und alle eigenständigen 32-Bit- oder 64-Bit-MSI-Office-Apps (mit Ausnahme von 2016)  <br/> |Keine  <br/> |Eigenständige Apps sind nicht betroffen. Suite wird auf 32-Bit-Klick-und-Los-Version von Office 2016 aktualisiert.  <br/> ||||
|Beliebige vorhandene 64-Bit-Klick-und-Los-Version von Office  <br/> |Deinstallieren der 64-Bit-Office-Apps, wenn es in Ordnung ist, sie durch 32-Bit-Apps Office ersetzen  <br/> |Wenn die 64-Bit-Office-Apps entfernt wurden, wird die 32-Bit-Klick-und-Los-Version von Office 2016 installiert  <br/> |
|Eine vorhandene MSI-Installation von Office 2016 mit oder ohne eigenständige Apps  <br/> |MSI-Office 2016 deinstallieren  <br/> |Die 32-Bit-Klick-und-Los-Version von Office 2016 wird installiert. Keine Änderung an eigenständigen Apps  <br/> |
|Vorhandene MSI-Installation von Office 2013 (oder früher) und/oder eigenständigen Office-Apps  <br/> |Keine  <br/> |32-Bit-Klick-und-Los-Version von Office 2016 mit der bereits vorhandenen MSI-Office-Installation (und eigenständigen Apps) existieren nebeneinander.  <br/> |
||||
   
 **(\*) Hinweis:** Führt aufgrund eines bekannten Fehlers kein Upgrade auf die 32-Bit-Klick-und-Los-Version von Office 2016 durch. Es wird eine Korrektur ausgeführt. 
  
