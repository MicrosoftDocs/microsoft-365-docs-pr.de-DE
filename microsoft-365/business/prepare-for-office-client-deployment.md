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
# <a name="prepare-for-office-client-deployment-by-microsoft-365-for-business"></a>Vorbereiten der Office Clientbereitstellung durch Microsoft 365 for Business

Dieser Artikel bezieht sich auf Microsoft 365 Business Premium.

## <a name="prepare-to-automatically-install-office-apps-to-client-computers"></a>Vorbereiten der automatischen Installation von Office-Apps auf Clientcomputern

Sie können Microsoft 365 Business Premium verwenden, um die 32-Bit-Office-Apps automatisch auf Windows 10 Computern zu installieren und sie mit Updates auf dem aktuellen Stand zu halten.
  
Die automatische Installation funktioniert am besten, wenn sich der Computer des Endbenutzers auf Windows 10 Business befindet und:
  
- Es sind keine Office-Desktop-Apps (Word, Excel, PowerPoint, Outlook, OneNote, Publisher, Access und OneDrive) vorhanden.
    
    oder
    
- Auf dem Computer ist eine Version von Office Klick-und-Los installiert.
    
Wenn Sie feststellen möchten, ob Sie über die Office Klick-und-Los-Version verfügen, wechseln Sie in einer beliebigen Office-App zu **Datei** \> **Konto** ( **Office-Konto** in Outlook). Wenn **Office Updates** wie in der folgenden Abbildung dargestellt angezeigt wird, wurde die Installation mithilfe von Klick-und-Los durchgeführt. 
  
![Screenshot of Office updates in Office app Account](../media/e3439380-fa43-4ed6-ae5d-64851c297df5.png)
  
 **Wer Vorteile dieser Funktion**
  
Der Endbenutzer, für dessen PC Folgendes zutrifft:
  
- **Verfügt** über eine Windows 10 Business Benutzerlizenz, eine aktive Microsoft 365 für Unternehmen-Lizenz, Windows 10 Creators Update und ist Azure Active Directory beigetreten. 
    
- **Verfügt nicht** über 64-Bit-Office-Apps (Beispiel: Word, Excel, PowerPoint). Wenn 64-Bit-Office-Apps erforderlich sind, eignet sich dieses Feature nicht gut, da es keine Unterstützung für das Auslösen einer 64-Bit-Klick-und-Los-Version von Office in der Microsoft 365 for Business-Administratorkonsole gibt. 
    
- **Verfügt nicht** über eigenständige 2016-Apps für Windows Installer (MSI) (z. B. Visio oder Project). Microsoft 365 for Business upgrades Office to the Click-to-Run version of Office 2016 and that doesn't work with Office 2016 MSI standalone apps. 
    
Die folgende Tabelle zeigt, welche Aktion Endbenutzer/Administratoren je nach Ihrem Anfangsstatus ausführen müssen, um eine erfolgreiche 32-Bit-Klick-und-Los-Version von Office Bereitstellung über die Microsoft 365 for Business-Verwaltungskonsole zu erhalten.<br/>


|Status "Office-Installation starten"|Vor der Installation von Microsoft 365 for Business Office auszuführende Aktion|Endzustand|
|:-----|:-----|:-----|
|Keine Office-Suite installiert  <br/> |Keine  <br/> |Office 2016 32-Bit-Version wird mithilfe von Klick-und-Los installiert.  <br/> |
|Vorhandene 32-Bit-Klick-und-Los-Version von Office (2016 oder früher) und keine eigenständigen Apps  <br/> |Keine  <br/> |Upgrade auf die neueste 32-Bit-Klick-und-Los-Version von Office 2016, je nach Bedarf **\*** <br/> |
|Vorhandene Klick-und-Los-32-Bit-Version von Office und Klick-und-Los-32-Bit- oder eigenständige 64-Bit-Office-Apps (z. B. Visio, Project)  <br/> |Keine  <br/> |Eigenständige Apps sind davon nicht betroffen. Suite wird auf 32-Bit-Klick-und-Los-Version von Office 2016 aktualisiert.  <br/> |
|Vorhandene 32-Bit-Klick-und-Los-Version von Office und alle eigenständigen 32-Bit- oder 64-Bit-MSI-Office-Apps (mit Ausnahme von 2016)  <br/> |Keine  <br/> |Eigenständige Apps sind davon nicht betroffen. Suite wird auf 32-Bit-Klick-und-Los-Version von Office 2016 aktualisiert.  <br/> |
|Beliebige vorhandene 64-Bit-Klick-und-Los-Version von Office  <br/> |Deinstallieren Sie die 64-Bit-Office-Apps, wenn es in Ordnung ist, sie durch 32-Bit-Office-Apps zu ersetzen.  <br/> |Wenn die 64-Bit-Office-Apps entfernt wurden, wird die 32-Bit-Klick-und-Los-Version von Office 2016 installiert  <br/> |
|Eine vorhandene MSI-Installation von Office 2016 mit oder ohne eigenständige Apps  <br/> |MSI-Office 2016 deinstallieren  <br/> |Die 32-Bit-Klick-und-Los-Version von Office 2016 wird installiert. Keine Änderung an eigenständigen Apps  <br/> |
|Vorhandene MSI-Installation von Office 2013 (oder früher) und/oder eigenständigen Office-Apps  <br/> |Keine  <br/> |32-Bit-Klick-und-Los-Version von Office 2016 mit der bereits vorhandenen MSI-Office-Installation (und eigenständigen Apps) existieren nebeneinander.  <br/> |
||||
   
 **(\*) Hinweis:** Führt aufgrund eines bekannten Fehlers kein Upgrade auf die 32-Bit-Klick-und-Los-Version von Office 2016 durch. Eine Korrektur wird ausgeführt. 
  
