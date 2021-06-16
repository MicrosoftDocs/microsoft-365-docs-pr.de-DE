---
title: Beispiel für die erweiterte Suche für Microsoft Defender für Office 365
description: Erste Schritte bei der Suche nach E-Mail-Bedrohungen mithilfe der erweiterten Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyber-Bedrohungssuche, Microsoft 365 Defender, Microsoft 365, m365, Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d3ac49b4afde0951e7a034c5c11114afbc52c293
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2021
ms.locfileid: "52965144"
---
# <a name="advanced-hunting-example-for-microsoft-defender-for-office-365"></a>Beispiel für die erweiterte Suche für Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Möchten Sie mit der erweiterten Bedrohungssuche nach E-Mail-Bedrohungen beginnen? Dann probieren Sie Folgendes aus:

Der Abschnitt [Erste Schritte](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started) im Artikel [Microsoft Defender für Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) enthält logische erste Konfigurationsblöcke, die so aussehen:

1. Konfigurieren Sie alles mit "Anti" im Namen.
   - Antischadsoftware
   - Antiphishing
   - Antispam
2. Richten Sie alles mit "Safe" im Namen ein.
   - Sichere Links
   - Sichere Anlagen
3. Sichern Sie die Workloads (z. B. SharePoint Online, OneDrive und Teams).
4. Schützen Mit automatischer Nullstunde-Bereinigung.

Zusammen mit einem [Link](../office-365-security/protect-against-threats.md) für den Sofortstart und um schon am ersten Tag mit der Konfiguration zu beginnen.

Der letzte Schritt in **Erste Schritte** dient dem Schutz von Benutzern mittels **automatischer Bereinigung zur Nullstunde**, auch bekannt als ZAP (Zero-Hour auto purge). Es kann sehr wichtig sein zu wissen, ob Ihre Bemühungen, ZAP auf verdächtige oder schädliche E-Mails nach der Zustellung anzuwenden, erfolgreich waren.

Der schnelle Wechsel zur Kusto-Abfragesprache, um nach Problemen zu suchen, stellt einen Vorteil der Zusammenführung dieser beiden Sicherheitscenter dar. Sicherheitsteams können ZAP-Fehler überwachen, indem sie [hier](https://security.microsoft.com/advanced-hunting)unter **"Erweiterte Suche"** die nächsten Schritte \> ausführen.

1. Klicken Sie auf der Seite "Erweiterte Suche" auf **"Abfrage".**
1. Kopieren Sie die nachstehende Abfrage in das Abfragefenster.
1. Wählen Sie **Abfrage ausführen** aus.

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfullyconverge-2-endpoints-new.png
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

:::image type="content" source="../../media/converge-13-advanced-hunt-an-email-zap-new.png" alt-text="Die Seite &quot;Erweiterte Suche&quot; (unter &quot;Suche&quot;) mit ausgewählter Abfrage am oberen Rand des Abfragebereichs und ausführen einer Kusto-Abfrage, um ZAP-Aktionen in den letzten 7 Tagen zu erfassen.":::

Die Daten aus dieser Abfrage werden im Ergebnisbereich unterhalb der Abfrage selbst angezeigt. Die Ergebnisse enthalten Informationen wie "DeviceName", "AccountDisplayName" und "ZapTime" in einem anpassbaren Ergebnisset. Die Ergebnisse können auch zur Dokumentation exportiert werden. Wenn die Abfrage später erneut benötigt wird, wählen Sie **Speichern** > **Speichern unter**, und fügen Sie die Abfrage Ihrer Liste von Abfragen, freigegebenen oder Communityabfragen hinzu.

## <a name="related-information"></a>Verwandte Informationen
- [Bewährte Methoden für die erweiterte Suche](advanced-hunting-best-practices.md)
- [Übersicht – Erweiterte Suche](advanced-hunting-overview.md)
