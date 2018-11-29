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
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867556"
---
# <a name="prepare-for-office-client-deployment-by-microsoft-365-business"></a>Vorbereiten der Office-Clientbereitstellung durch Microsoft 365 Business

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>Vorbereiten der automatischen Installation von Office-Apps auf Clientcomputern

Sie können die 32-Bit-Office-Apps mithilfe von Microsoft 365 Business auf Windows 10-Computern automatisch installieren und mit Updates auf dem neuesten Stand halten.
  
Das funktioniert am besten, wenn auf dem Computer des Endbenutzers Windows 10 Business ausgeführt wird und außerdem Folgendes zutrifft:
  
- Es sind keine Office-Desktop-Apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access und OneDrive) vorhanden.
    
    oder
    
- Auf dem Computer ist eine Version von Office Klick-und-Los installiert.
    
Wenn Sie feststellen möchten, ob Sie über die Office Klick-und-Los-Version verfügen, wechseln Sie in einer beliebigen Office-App zu **Datei** \> **Konto** ( **Office-Konto** in Outlook). Wenn "Office-Updates" wie in der nachstehenden Abbildung angezeigt wird, erfolgte die Installation mithilfe von Klick-und-Los. 
  
![Screenshot of Office updates in Office app Account](media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **Wer von diesem Feature profitiert**
  
Der Endbenutzer, für dessen PC Folgendes zutrifft:
  
- **Verfügt** über eine Windows 10 Business-Benutzerlizenz, eine aktive Microsoft 365 Business-Lizenz, Windows 10 Creators Update und ist in Azure Active Directory eingebunden. 
    
- **Verfügt über keine** 64-Bit-Office-Apps (Beispiel: Word, Excel, PowerPoint). Wenn die 64-Bit-Office-Apps benötigt werden, ist dieses Feature ungeeignet, weil es keinen Support für das Auslösen einer 64-Bit-Version von Office 2016 Klick-und-Los über die Microsoft 365 Business-Verwaltungskonsole gibt. 
    
- **Verfügt über keine** eigenständigen 2016 Windows Installer-Apps (MSI-Apps) wie z. B. Visio oder Project. Microsoft 365 Business aktualisiert Office auf die Klick-und-Los-Version von Office 2016 und funktioniert nicht bei eigenständigen Office 2016-MSI-Apps. 
    
In der nachstehenden Tabelle wird erläutert, welche Maßnahme die Endbenutzer/Administratoren - je nach ihrem Anfangsstatus - möglicherweise ergreifen müssen, um eine erfolgreiche 32-Bit-Klick-und-Los-Version einer Office-Bereitstellung über die Microsoft 365 Business-Verwaltungskonsole zu erhalten.
  
|**Status "Office-Installation starten"**|**Zu ergreifende Maßnahme vor Microsoft 365 Business Office-Installation**|**Endstatus**|
|:-----|:-----|:-----|
|Keine Office-Suite installiert  <br/> |Keine  <br/> |Die 32-Bit-Version von Office 2016 wurde mithilfe von Klick-und-Los installiert  <br/> |
|Vorhandene 32-Bit-Klick-und-Los-Version von Office (2016 oder früher) und keine eigenständigen Apps  <br/> |Keine  <br/> |Upgrade auf die neueste 32-Bit-Klick-und-Los-Version von Office 2016, je nach Bedarf **\*** <br/> |
|Vorhandene 32-Bit-Klick-und-Los-Version von Office und eigenständige 32- oder 64-Bit-Klick-und-Los-Office-Apps (z. B. Visio, Project)  <br/> |Keine  <br/> |Eigenständige Apps sind hiervon nicht betroffen. Suite wird auf 32-Bit-Klick-und-Los-Version von Office 2016 aktualisiert.  <br/> |
|Vorhandene 32-Bit-Klick-und-Los-Version von Office und alle eigenständigen 32-Bit- oder 64-Bit-MSI-Office-Apps (mit Ausnahme von 2016)  <br/> |Keine  <br/> |Eigenständige Apps sind hiervon nicht betroffen. Suite wird auf 32-Bit-Klick-und-Los-Version von Office 2016 aktualisiert.  <br/> ||||
|Beliebige vorhandene 64-Bit-Klick-und-Los-Version von Office  <br/> |64-Bit-Office-Apps deinstallieren, wenn es OK ist, dass sie durch die 32-Bit-Office-Apps ersetzt werden  <br/> |Wenn die 64-Bit-Office-Apps entfernt wurden, wird die 32-Bit-Klick-und-Los-Version von Office 2016 installiert  <br/> |
|Eine vorhandene MSI-Installation von Office 2016 mit oder ohne eigenständige Apps  <br/> |MSI-Office 2016 deinstallieren  <br/> |Die 32-Bit-Klick-und-Los-Version von Office 2016 wird installiert. Keine Änderung an eigenständigen Apps  <br/> |
|Vorhandene MSI-Installation von Office 2013 (oder früher) und/oder eigenständigen Office-Apps  <br/> |Keine  <br/> |32-Bit-Klick-und-Los-Version von Office 2016 mit der bereits vorhandenen MSI-Office-Installation (und eigenständigen Apps) existieren nebeneinander.  <br/> |
||||
   
 **(\*) Hinweis:** Führt aufgrund eines bekannten Fehlers kein Upgrade auf die 32-Bit-Klick-und-Los-Version von Office 2016 durch. Eine Fehlerkorrektur ist in Bearbeitung. 
  


