---
title: Integration Office 365 Advanced Threat Protection mit Microsoft Defender Advanced Threat Protection
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 04/13/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: Integrieren Sie Office 365 Advanced Threat Protection mit Microsoft Defender Advanced Threat Protection, um detaillierte Informationen zur Bedrohungs Verwaltung zu erhalten.
ms.openlocfilehash: a2634a70bdbdd21efe2c59721e5532500eb4e4cc
ms.sourcegitcommit: 4c6af6530b4997055b8e60bf532e75cbc72fb6c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2020
ms.locfileid: "43284226"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a>Integration Office 365 Advanced Threat Protection mit Microsoft Defender Advanced Threat Protection

Wenn Sie Teil des Sicherheitsteams Ihrer Organisation sind, können Sie [Office 365 Advanced Threat Protection](office-365-atp.md) und zugehörige Ermittlungs-und Antwortfunktionen mit [Advanced Threat Protection von Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)integrieren. Dies kann Ihnen helfen, schnell zu verstehen, ob die Computer der Benutzer gefährdet sind, wenn Sie Bedrohungen in Office 365 untersuchen. Wenn die Integration beispielsweise aktiviert ist, können Sie eine Liste der Computer anzeigen, die von den Empfängern einer erkannten e-Mail-Nachricht verwendet werden, sowie die Anzahl der letzten Warnungen, die diese Computer in Microsoft Defender Advanced Threat Protection haben.
  
Die folgende Abbildung zeigt die Registerkarte **Geräte** , die angezeigt wird, wenn die Microsoft Defender ATP-Integration aktiviert ist:
  
![Wenn Microsoft Defender ATP aktiviert ist, können Sie eine Liste der Geräte mit Warnungen anzeigen.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
In diesem Beispiel können Sie sehen, dass die Empfänger der e-Mail-Nachricht vier Geräte und eine Warnung besitzen. Wenn Sie auf den Link für ein Gerät klicken, wird seine Seite im Sicherheits Center von Microsoft Defender geöffnet.
  
## <a name="requirements"></a>Anforderungen

- Ihre Organisation muss Office 365 ATP-Plan 2 (oder Office 365 E5) und Microsoft Defender ATP haben.
    
- Sie müssen ein Office 365 globaler Administrator sein oder über eine Sicherheitsadministrator Rolle (beispielsweise Sicherheitsadministrator) verfügen, die [im &amp; Security Compliance Center](https://protection.office.com)zugewiesen ist. (Siehe [Berechtigungen im Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))
    
- Sie müssen sowohl im Sicherheits & Compliance Center als auch im Sicherheitscenter von Microsoft Defender Zugriff auf beide [Explorer-(oder Echt Zeit Erkennungen)](threat-explorer.md) haben.
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a>So integrieren Sie Office 365 ATP mit Microsoft Defender ATP

Die Integration von Office 365 ATP mit Microsoft Defender ATP wird mithilfe des Office 365 Security & Compliance Centers und des Sicherheitscenters von Microsoft Defender eingerichtet.
  
1. Wechseln Sie als globaler Office 365 Administrator oder Sicherheitsadministrator zu, und [https://protection.office.com](https://protection.office.com) melden Sie sich an.
    
2. Wählen Sie **Threat Management** \> **Explorer**aus.<br>![Explorer im Menü "Threat Management"](../../media/ThreatMgmt-Explorer-nav.png)<br>
    
3. Wählen Sie in der oberen rechten Ecke des Bildschirms **Einstellungen für WDATP**aus.
    
4. Aktivieren Sie im Dialogfeld Microsoft Defender ATP Connection die Option **Connect to Windows ATP**.<br>![Microsoft Defender ATP-Verbindung](../../media/Explorer-WDATPConnection-dialog.png)<br>
    
5. Aktivieren Sie die Verbindung im Sicherheits Center von Microsoft Defender ([https://securitycenter.windows.com](https://securitycenter.windows.com)).

## <a name="related-topics"></a>Verwandte Themen

[Funktionen für die Untersuchung und Reaktion auf Bedrohungen in Office 365](office-365-ti.md)
  
[Office 365 Advanced Threat Protection](office-365-atp.md)
  

