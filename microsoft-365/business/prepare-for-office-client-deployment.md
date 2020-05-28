---
title: Vorbereiten der Office-Clientbereitstellung von Microsoft 365 for Business
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: ed34fff3-2881-4ed4-9906-1ba6bb8dd804
description: In diesem Artikel erfahren Sie, wie Sie die 32-Bit-Office-Apps auf Windows 10-Computern automatisch installieren und auf dem neuesten Stand halten.
ms.openlocfilehash: 6f3a80be9729a3818607c0f42e2cc7ece66a07ee
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401320"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a>Vorbereiten der Office-Clientbereitstellung von Microsoft 365 for Business

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>Vorbereiten der automatischen Installation von Office-Apps auf Clientcomputern

Sie können Microsoft 365 for Business verwenden, um die 32-Bit-Office-Apps auf Windows 10-Computern automatisch zu installieren und diese mit Updates auf dem neuesten Stand zu halten.
  
Die automatische Installation funktioniert am besten, wenn sich der Computer des Endbenutzers in Windows 10 Business befindet und:
  
- Es sind keine Office-Desktop-Apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access und OneDrive) vorhanden.
    
    oder
    
- Auf dem Computer ist eine Version von Office Klick-und-Los installiert.
    
Wenn Sie feststellen möchten, ob Sie über die Office Klick-und-Los-Version verfügen, wechseln Sie in einer beliebigen Office-App zu **Datei** \> **Konto** ( **Office-Konto** in Outlook). Wenn Office- **Updates** wie in der folgenden Abbildung dargestellt angezeigt werden, wurde die Installation mithilfe von Klick-und-Los ausgeführt. 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **Wer profitiert von dieser Funktion**
  
Der Endbenutzer, für dessen PC Folgendes zutrifft:
  
- **Verfügt über** eine Windows 10-Geschäftsbenutzer Lizenz, eine aktive Microsoft 365 for Business-Lizenz, ein Windows 10 Creators-Update und ist mit Azure Active Directory verbunden. 
    
- Verfügt **nicht über** 64-Bit-Office-Apps (Beispiel: Word, Excel, PowerPoint). Wenn 64-Bit-Office-Apps erforderlich sind, ist dieses Feature nicht geeignet, da es keine Unterstützung für die Auslösung einer 64-Bit-2016-Klick-und-Los-Version von Office von der Microsoft 365 for Business-Verwaltungskonsole gibt. 
    
- Verfügt **nicht über** 2016 eigenständige Windows Installer (MSI)-Apps (beispielsweise Visio oder Project). Microsoft 365 for Business aktualisiert Office auf die Klick-und-Los-Version von Office 2016 und funktioniert nicht mit eigenständigen Office 2016 MSI-apps. 
    
Die folgende Tabelle zeigt, welche Aktion die Endbenutzer/Administratoren je nach Anfangsstatus möglicherweise ausführen müssen, um eine erfolgreiche 32-Bit-Klick-und-Los-Version der Office-Bereitstellung von der Microsoft 365 for Business-Verwaltungskonsole zu erhalten.
  
|**Status "Office-Installation starten"**|**Auszuführende Aktion vor der Installation von Microsoft 365 for Business Office**|**Endstatus**|
|:-----|:-----|:-----|
|Keine Office-Suite installiert  <br/> |Keine  <br/> |Office 2016 32-Bit wird mithilfe von Klick-und-Los installiert  <br/> |
|Vorhandene 32-Bit-Klick-und-Los-Version von Office (2016 oder früher) und keine eigenständigen Apps  <br/> |Keine  <br/> |Upgrade auf die neueste 32-Bit-Klick-und-Los-Version von Office 2016, je nach Bedarf **\*** <br/> |
|Vorhandene Klick-und-Los-32-Bit-Version von Office-und Klick-und-Los-32-Bit-oder 64-Bit-eigenständigen Office-Apps (beispielsweise Visio, Project)  <br/> |Keine  <br/> |Eigenständige apps sind davon nicht betroffen. Suite wird auf 32-Bit-Klick-und-Los-Version von Office 2016 aktualisiert.  <br/> |
|Vorhandene 32-Bit-Klick-und-Los-Version von Office und alle eigenständigen 32-Bit- oder 64-Bit-MSI-Office-Apps (mit Ausnahme von 2016)  <br/> |Keine  <br/> |Eigenständige apps sind davon nicht betroffen. Suite wird auf 32-Bit-Klick-und-Los-Version von Office 2016 aktualisiert.  <br/> ||||
|Beliebige vorhandene 64-Bit-Klick-und-Los-Version von Office  <br/> |Deinstallieren Sie die 64-Bit-Office-Apps, wenn es OK ist, um Sie durch 32-Bit-Office-Apps zu ersetzen.  <br/> |Wenn die 64-Bit-Office-Apps entfernt wurden, wird die 32-Bit-Klick-und-Los-Version von Office 2016 installiert  <br/> |
|Eine vorhandene MSI-Installation von Office 2016 mit oder ohne eigenständige Apps  <br/> |MSI-Office 2016 deinstallieren  <br/> |Die 32-Bit-Klick-und-Los-Version von Office 2016 wird installiert. Keine Änderung an eigenständigen Apps  <br/> |
|Vorhandene MSI-Installation von Office 2013 (oder früher) und/oder eigenständigen Office-Apps  <br/> |Keine  <br/> |32-Bit-Klick-und-Los-Version von Office 2016 mit der bereits vorhandenen MSI-Office-Installation (und eigenständigen Apps) existieren nebeneinander.  <br/> |
||||
   
 **(\*) Hinweis:** Führt aufgrund eines bekannten Fehlers kein Upgrade auf die 32-Bit-Klick-und-Los-Version von Office 2016 durch. Eine Korrektur wird ausgeführt. 
  
