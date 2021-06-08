---
title: Hostfirewall-Berichterstellung in Microsoft Defender für Endpunkt
description: Hosten und Anzeigen von Firewallberichten in Microsoft 365 Security Center.
keywords: Windows Defender, Firewall
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 0289d6f920fd6ff35fd446f9c2b8c5516883a4d2
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809308"
---
# <a name="host-firewall-reporting-in-microsoft-defender-for-endpoint"></a>Hostfirewall-Berichterstellung in Microsoft Defender für Endpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Wenn Sie Administrator sind, können Sie jetzt Firewallberichte für [Microsoft 365 Security Center hosten.](https://security.microsoft.com) Mit diesem Feature können Sie Windows 10 und Windows Server 2019-Firewallberichte von einem zentralen Ort anzeigen. 

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen? 

- Sie müssen Windows 10 oder Windows Server 2019 ausführen.
- Informationen zum Onboarding von Geräten in den Microsoft Defender für Endpunktdienst finden Sie [hier.](onboard-configure.md) 
- Damit Microsoft 365 Security Center mit dem Empfangen der Daten beginnt, müssen Sie **Überwachungsereignisse** für Windows Defender Firewall mit erweiterter Sicherheit aktivieren: 
    - [Audit Filtering Platform Packet Drop](/windows/security/threat-protection/auditing/audit-filtering-platform-packet-drop)
    - [Überwachen der Filterplattformverbindung](/windows/security/threat-protection/auditing/audit-filtering-platform-connection) 
- Aktivieren Sie diese Ereignisse mithilfe des Gruppenrichtlinienobjekt-Editors, der lokalen Sicherheitsrichtlinie oder der befehle auditpol.exe. Weitere Informationen finden Sie [hier.](/windows/win32/fwp/auditing-and-logging) 
    - Die beiden PowerShell-Befehle sind:
        - **auditpol /set /subcategory:"Filtering Platform Packet Drop" /failure:enable** 
        - **auditpol /set /subcategory:"Filtering Platform Connection" /failure:enable** 

## <a name="the-process"></a>Der Prozess
> [!NOTE]
> Stellen Sie sicher, dass Sie die Anweisungen aus dem obigen Abschnitt befolgen und Ihre Geräte ordnungsgemäß für die frühe Vorschauteilnahme konfigurieren.

- Nach dem Aktivieren der Ereignisse beginnt Microsoft 365 Security Center mit der Überwachung der Daten.
    - Remote-IP, Remoteport, lokaler Port, lokale IP, Computername, Prozess über eingehende und ausgehende Verbindungen.
- Administratoren können jetzt Windows Firewallaktivität [sehen.](https://security.microsoft.com/firewall)
    - Zusätzliche Berichte können durch Herunterladen des Skripts für [benutzerdefinierte Berichterstellung](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) erleichtert werden, um die Windows Defender Firewall Aktivitäten mithilfe von Power BI zu überwachen. 
    - Es kann bis zu 12 Stunden dauern, bis die Daten widergespiegelt werden.

## <a name="supported-scenarios"></a>Unterstützte Szenarien
Die folgenden Szenarien werden während der Ring0-Vorschau unterstützt. 

### <a name="firewall-reporting-in-security-center"></a>Firewall-Berichterstellung im Security Center

Nachfolgend finden Sie einige Beispiele für die Firewallberichtsseiten. Hier finden Sie eine Zusammenfassung der eingehenden, ausgehenden und Anwendungsaktivitäten. Sie können direkt auf diese Seite zugreifen, indem Sie zu https://security.microsoft.com/firewall . 

> [!div class="mx-imgBorder"]
> ![Hostfirewall-Berichtsseite](\images\host-firewall-reporting-page.png)

Auf diese Berichte können Sie auch zugreifen, indem Sie zum Abschnitt  >    >  **"Berichtssicherheitsberichtsgeräte"** am unteren Rand der Karte **"Firewall blocked Inbound Connections"** wechseln.

### <a name="from-computers-with-a-blocked-connection-to-device"></a>Von "Computer mit blockierter Verbindung" zum Gerät

Karten unterstützen interaktive Objekte. Sie können einen Drilldown zur Aktivität eines Geräts ausführen, indem Sie auf den Gerätenamen klicken, der auf einer neuen Registerkarte gestartet https://securitycenter.microsoft.com wird, und Sie direkt zur Registerkarte **"Gerätezeitachse"** führen. 

> [!div class="mx-imgBorder"]
> ![Computer mit einer blockierten Verbindung](\images\firewall-reporting-blocked-connection.png)

Sie können jetzt die Registerkarte **"Zeitachse"** auswählen, auf der Sie eine Liste der Ereignisse erhalten, die diesem Gerät zugeordnet sind. 

Nachdem Sie auf die Schaltfläche **"Filter"** in der oberen rechten Ecke des Anzeigebereichs geklickt haben, wählen Sie den gewünschten Ereignistyp aus. Wählen Sie in diesem Fall **Firewall-Ereignisse** aus, und der Bereich wird nach Firewallereignissen gefiltert. 

> [!div class="mx-imgBorder"]
> ![Filterschaltfläche](\images\firewall-reporting-filters-button.png)

### <a name="drill-into-advanced-hunting-preview-refresh"></a>Drilldown zur erweiterten Suche (Vorschauaktualisierung)

Firewallberichte unterstützen das Drillthrough von der Karte direkt in die **erweiterte Suche,** indem Sie auf die Schaltfläche **"Erweiterte Suche öffnen"** klicken. Die Abfrage wird vorab ausgefüllt. 

> [!div class="mx-imgBorder"]
> ![Schaltfläche "Erweiterte Suche öffnen"](\images\firewall-reporting-advanced-hunting.png)

Die Abfrage kann jetzt ausgeführt werden, und alle zugehörigen Firewallereignisse der letzten 30 Tage können untersucht werden. 

Für zusätzliche Berichte oder benutzerdefinierte Änderungen kann die Abfrage zur weiteren Analyse in Power BI exportiert werden. Benutzerdefinierte Berichte können durch Herunterladen des Skripts für [benutzerdefinierte Berichterstellung](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) erleichtert werden, um die Windows Defender Firewall Aktivitäten mithilfe von Power BI zu überwachen. 

 