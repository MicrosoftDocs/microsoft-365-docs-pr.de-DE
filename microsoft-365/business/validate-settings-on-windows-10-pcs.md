---
title: Überprüfen der Einstellungen für den App-Schutz auf Windows 10-PCs
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Erfahren Sie, wie Microsoft 365 Business app Protection Settings in Windows-10-Geräte zu überprüfen.
ms.openlocfilehash: db05c86bd75cc30e22e025034a3dab478d0f5365
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26867726"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a>Überprüfen von Geräteschutzeinstellungen auf Windows 10-PCs

## <a name="verify-that-windows-10-device-policies-are-set"></a>Sicherstellen, dass Windows 10-Geräterichtlinien festgelegt sind

Nachdem Sie [Geräterichtlinien eingerichtet haben](protection-settings-for-windows-10-pcs.md), kann es einige Stunden dauern, bis die jeweilige Richtlinie auf den Geräten der Benutzer in Kraft tritt. Sie können bestätigen, dass die Richtlinien in Kraft getreten sind, indem Sie sich auf den Geräten der Benutzer die verschiedenen Bildschirme der Windows-Einstellungen ansehen. Weil die Benutzer die Einstellungen für Windows Update und Windows Defender Antivirus auf ihren Windows 10-Geräten nicht ändern können, sind viele dieser Optionen abgeblendet.
  
1. Wechseln Sie zu **Einstellungen** \> **Update &amp; Security** \> **Windows Update** \> **Neustart-Optionen** , und bestätigen Sie, dass alle Einstellungen abgeblendet sind. 
    
    ![All the Restart options are greyed out.](media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. Wechseln Sie zu **Einstellungen** \> **Update &amp; Security** \> **Windows Update** \> **Erweiterte Optionen** ein, und bestätigen Sie, dass alle Einstellungen abgeblendet sind. 
    
    ![Windows Advanced updates options are all greyed out.](media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Wechseln Sie zu **Einstellungen** \> **Update &amp; Security** \> **Windows Update** \> **Erweiterte Optionen** \> **auswählen, wie Updates übermittelt werden**.
    
    Vergewissern Sie sich, dass Sie die Meldung (in Rot) sehen können, dass einige Einstellungen ausgeblendet sind oder von Ihrer Organisation verwaltet werden und alle Optionen abgeblendet sind.
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. Wechseln Sie zum Öffnen der Windows Defender Security Center auf **Einstellungen** \> **Update &amp; Security** \> **Windows Defender** \> klicken Sie auf **Öffnen Windows Defender Sicherheitscenter** \> **Virus &amp; Thread Schutz** \> **Virus &amp; Bedrohung Protection Settings**. 
    
5. Stellen Sie sicher, dass alle Optionen abgeblendet sind. 
    
    ![The Virus and threat protection settings are greyed out.](media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>Verwandte Themen

[Microsoft 365 Business-Dokumentation und -Ressourcen](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Erste Schritte mit Microsoft 365 Business](microsoft-365-business-overview.md)
  
[Verwalten von Microsoft 365 Business](manage.md)
  
[Festlegen von Geräteschutzeinstellungen für Windows 10-PCs](protection-settings-for-windows-10-pcs.md)
  

