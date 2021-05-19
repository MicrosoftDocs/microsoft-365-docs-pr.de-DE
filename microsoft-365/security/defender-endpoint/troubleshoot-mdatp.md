---
title: Behandeln von Problemen mit dem Dienst "Microsoft Defender für Endpunkt"
description: Hier finden Sie Lösungen und Problemumgehungen für bekannte Probleme, z. B. Serverfehler beim Zugriff auf den Dienst.
keywords: Problembehandlung für Microsoft Defender for Endpoint, Serverfehler, Zugriff verweigert, ungültige Anmeldeinformationen, keine Daten, Dashboardportal, zulassen, Ereignisanzeige
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 8aaea65c617300a16f99a9a3e3a62d94b7983198
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538351"
---
# <a name="troubleshoot-service-issues"></a>Behandeln von Dienstproblemen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


In diesem Abschnitt werden Probleme behandelt, die bei der Verwendung des Microsoft Defender for Endpoint-Diensts auftreten können.

## <a name="server-error---access-is-denied-due-to-invalid-credentials"></a>Serverfehler : Zugriff wird aufgrund ungültiger Anmeldeinformationen verweigert
Wenn beim Zugriff auf den Dienst ein Serverfehler auftritt, müssen Sie ihre Browsercookieeinstellungen ändern.
Konfigurieren Sie Ihren Browser so, dass Cookies zulässig sind.

## <a name="elements-or-data-missing-on-the-portal"></a>Elemente oder Daten fehlen im Portal
Wenn einige Elemente oder Daten auf der Microsoft Defender Security Center ist es möglich, dass Proxyeinstellungen sie blockieren.

Stellen Sie sicher, `*.securitycenter.windows.com` dass die Proxy-Allowlist enthalten ist.


> [!NOTE]
> Sie müssen das HTTPS-Protokoll verwenden, wenn Sie die folgenden Endpunkte hinzufügen.

## <a name="microsoft-defender-for-endpoint-service-shows-event-or-error-logs-in-the-event-viewer"></a>Microsoft Defender for Endpoint-Dienst zeigt Ereignis- oder Fehlerprotokolle in der Ereignisanzeige an.

Eine Liste der Ereignis-IDs, die vom Microsoft Defender for Endpoint-Dienst gemeldet werden, finden Sie unter Überprüfen von Ereignissen und Fehlern mithilfe der Ereignisanzeige. [](event-error-codes.md) Der Artikel enthält auch Schritte zur Problembehandlung bei Ereignisfehlern.

## <a name="microsoft-defender-for-endpoint-service-fails-to-start-after-a-reboot-and-shows-error-577"></a>Microsoft Defender for Endpoint-Dienst kann nach einem Neustart nicht gestartet werden und zeigt Fehler 577 an.

Wenn das Onboarding von Geräten erfolgreich abgeschlossen wurde, Microsoft Defender for Endpoint jedoch nach einem Neustart nicht gestartet wird und Fehler 577 angezeigt wird, überprüfen Sie, ob Windows Defender nicht durch eine Richtlinie deaktiviert ist.

Weitere Informationen finden Sie unter [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).

## <a name="known-issues-with-regional-formats"></a>Bekannte Probleme mit regionalen Formaten

**Datums- und Uhrzeitformate**<br>
Es gibt einige bekannte Probleme mit den Uhrzeit- und Datumsformaten. 

Die folgenden Datumsformate werden unterstützt:
- MM/dd/yyyy
- dd/MM/yyyy

Die folgenden Datums- und Uhrzeitformate werden derzeit nicht unterstützt:
- Datumsformat yyyy/MM/dd
- Datumsformat dd/MM/yy
- Datumsformat mit yy. Zeigt nur yyyy an.
- Das Zeitformat HH:mm:ss wird nicht unterstützt (das 12-Stunden-FORMAT am/PM wird nicht unterstützt). Es wird nur das 24-Stunden-Format unterstützt.

**Verwenden von Komma zur Angabe von Tausend**<br>
Die Verwendung von Kommas als Trennzeichen in Zahlen wird nicht unterstützt. Regionen, in denen eine Zahl durch ein Komma getrennt ist, um tausend anzugeben, wird nur die Verwendung eines Punkts als Trennzeichen angezeigt. Beispielsweise wird 15,5K als 15,5K angezeigt.

>Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshoot-belowfoldlink)

## <a name="microsoft-defender-for-endpoint-tenant-was-automatically-created-in-europe"></a>Microsoft Defender for Endpoint-Mandant wurde automatisch in Europa erstellt
Wenn Sie Azure Defender zum Überwachen von Servern verwenden, wird automatisch ein Microsoft Defender for Endpoint-Mandant erstellt. Die Microsoft Defender for Endpoint-Daten werden standardmäßig in Europa gespeichert.





## <a name="related-topics"></a>Verwandte Themen
- [Behandeln von Problemen beim Onboarding von Microsoft Defender for Endpoint](troubleshoot-onboarding.md)
- [Überprüfen von Ereignissen und Fehlern mithilfe der Ereignisanzeige](event-error-codes.md)
