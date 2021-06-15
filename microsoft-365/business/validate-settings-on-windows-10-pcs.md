---
title: Überprüfen der App-Schutzeinstellungen für Windows 10-PCs
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Erfahren Sie, wie Sie überprüfen, ob Microsoft 365 Für Unternehmen-App-Schutzeinstellungen auf den Geräten ihrer Benutzer Windows 10 wirksam wurden.
ms.openlocfilehash: 464a246a0da65dcffeb70946287ce4fa0e67ae7c
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925257"
---
# <a name="validate-device-protection-settings-for-windows-10-pcs"></a>Überprüfen der Geräteschutzeinstellungen für Windows 10 PCs

## <a name="verify-that-windows-10-device-policies-are-set"></a>Sicherstellen, dass Windows 10-Geräterichtlinien festgelegt sind

Nachdem Sie [Geräterichtlinien eingerichtet haben](protection-settings-for-windows-10-pcs.md), kann es einige Stunden dauern, bis die jeweilige Richtlinie auf den Geräten der Benutzer in Kraft tritt. Sie können bestätigen, dass die Richtlinien in Kraft getreten sind, indem Sie sich auf den Geräten der Benutzer die verschiedenen Bildschirme der Windows-Einstellungen ansehen. Da die Benutzer die Einstellungen für Windows Update und Windows Defender Antivirus auf ihren Windows 10 Geräten nicht ändern können, sind viele Optionen ausgegraut.
  
1. Wechseln Sie zu **Einstellungen** \> **&amp; Updatesicherheits-Windows** \>  \> **Update-Neustartoptionen,** und vergewissern Sie sich, dass alle Einstellungen ausgegraut sind. 
    
    ![Alle Neustartoptionen sind ausgegraut.](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. Wechseln Sie zu **Einstellungen** \> **&amp; Updatesicherheit** Windows erweiterten \>  \> **Updateoptionen,** und vergewissern Sie sich, dass alle Einstellungen ausgegraut sind. 
    
    ![Windows Erweiterte Updateoptionen sind alle ausgegraut.](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.
    
    Vergewissern Sie sich, dass die Meldung (rot) angezeigt wird, dass einige Einstellungen von Ihrer Organisation ausgeblendet oder verwaltet werden und alle Optionen ausgegraut sind.
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**. 
    
5. Stellen Sie sicher, dass alle Optionen ausgegraut sind. 
    
    ![Die Einstellungen für Viren- und Bedrohungsschutz sind ausgegraut.](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>Verwandte Themen

[Microsoft 365 für Unternehmen – Dokumentation und Ressourcen](./index.yml)
  
[Erste Schritte mit Microsoft 365 for Business](microsoft-365-business-overview.md)
  
[Verwalten von Microsoft 365 für Unternehmen](manage.md)
  
[Festlegen von Geräteschutzeinstellungen für Windows 10-PCs](protection-settings-for-windows-10-pcs.md)
