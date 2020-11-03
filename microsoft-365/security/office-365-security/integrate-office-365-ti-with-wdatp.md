---
title: Verwenden von Microsoft Defender für Office 365 zusammen mit Microsoft Defender für Endpoint
f1.keywords:
- NOCSH
keywords: Integration, Microsoft Defender, ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 09/29/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Verwenden Sie Microsoft Defender für Office 365 zusammen mit Microsoft Defender für Endpoint, um ausführlichere Informationen zu Bedrohungen für Ihre Geräte und e-Mail-Inhalte zu erhalten.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6b8bec8d3ebe52de9b4e1b919b2aceee20b5b5b0
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842356"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Verwenden von Microsoft Defender für Office 365 zusammen mit Microsoft Defender für Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender für Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) kann für die Zusammenarbeit mit [Microsoft Defender für Endpoint](https://docs.microsoft.com/windows/security/threat-protection)konfiguriert werden.

Die Integration von Microsoft Defender für Office 365 mit Microsoft Defender für Endpoint kann Ihren sicherheitsvorgängen helfen, das Team zu überwachen und schnell Maßnahmen zu ergreifen, wenn die Geräte der Benutzer gefährdet sind. Wenn beispielsweise die Integration aktiviert ist, kann Ihr Sicherheits Betriebsteam die Geräte anzeigen, die von einer erkannten e-Mail-Nachricht potenziell betroffen sind, sowie die Anzahl der letzten Warnungen, die für diese Geräte in Microsoft Defender für Endpoint generiert wurden. 

In der folgenden Abbildung wird dargestellt, wie die Registerkarte **Geräte** aussieht, wenn Microsoft Defender für die Endpunkt Integration aktiviert ist:
  
![Wenn Microsoft Defender für Endpoint aktiviert ist, können Sie eine Liste der Geräte mit Warnungen anzeigen.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
In diesem Beispiel können Sie sehen, dass die Empfänger der erkannten e-Mail-Nachricht vier Geräte und eine Warnung besitzen. Wenn Sie auf den Link für ein Gerät klicken, wird seine Seite im Sicherheits Center von Microsoft Defender geöffnet ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

> [!TIP]
> **[Erfahren Sie mehr über das Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (auch als Microsoft Defender für Endpoint-Portal bezeichnet).
  
## <a name="requirements"></a>Anforderungen

- Ihre Organisation muss Microsoft Defender für Office 365 (oder Office 365 E5) und Microsoft Defender für Endpoint haben.
    
- Sie müssen ein globaler Administrator sein oder über eine Sicherheitsadministrator Rolle (wie etwa Sicherheitsadministrator) verfügen, die im [Security &amp; Compliance Center](https://protection.office.com)zugewiesen ist. (Siehe [Berechtigungen im Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))
    
- Sie müssen sowohl im Sicherheits & Compliance Center als auch im Sicherheitscenter von Microsoft Defender Zugriff auf beide [Explorer-(oder Echt Zeit Erkennungen)](threat-explorer.md) haben.
    
## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>So integrieren Sie Microsoft Defender für Office 365 mit Microsoft Defender für Endpoint

Die Integration von Microsoft Defender für Office 365 mit Microsoft Defender für Endpoint wird mithilfe des Security & Compliance Centers und des Sicherheitscenters von Microsoft Defender eingerichtet.
  
1. Wechseln Sie als globaler Administrator oder Sicherheitsadministrator zu und melden Sie sich an [https://protection.office.com](https://protection.office.com) . (Hiermit gelangen Sie zum Office 365 Security & Compliance Center.)
    
2. Wählen Sie im Navigationsbereich **Threat Management**  >  **Explorer** aus.<br>![Explorer im Menü "Threat Management"](../../media/ThreatMgmt-Explorer-nav.png)<br>
    
3. Wählen Sie in der oberen rechten Ecke des Bildschirms **Defender for Endpoint Settings** aus.
    
4. Aktivieren Sie im Dialogfeld Microsoft Defender für Endpunkt Verbindung die Option **Verbindung mit Microsoft Defender für Endpunkt herstellen**.<br>![Microsoft Defender für Endpunkt Verbindung](../../media/Explorer-WDATPConnection-dialog.png)<br>
    
5. Wechseln Sie zum Microsoft Defender-Sicherheits Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

6. Klicken Sie in der Navigationsleiste auf **Einstellungen**. Wählen Sie dann unter **Allgemein** die Option **Erweiterte Funktionen** aus.

7. Scrollen Sie nach unten zu **Office 365 Threat Intelligence-Verbindung** , und schalten Sie die Verbindung ein.<br/>![Office 365 Threat Intelligence-Verbindung](../../media/mdatp-oatptoggle.png)<br>

## <a name="related-articles"></a>Verwandte Artikel

[Funktionen für die Untersuchung und Reaktion auf Bedrohungen in Office 365](office-365-ti.md)
  
[Microsoft Defender für Office 365](office-365-atp.md)
  
[Microsoft Defender für Endpunkt](https://docs.microsoft.com/windows/security/threat-protection)
