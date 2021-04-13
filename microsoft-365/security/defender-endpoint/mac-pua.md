---
title: Erkennen und Blockieren potenziell unerwünschter Anwendungen mit Microsoft Defender ATP für Mac
description: Erkennen und Blockieren von potenziell unerwünschten Anwendungen (PUA) mithilfe von Microsoft Defender ATP für Mac.
keywords: microsoft, defender, atp, mac, pua, pus
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: cf61c6a501a53ac03d3c4cc28068f7af4c0f88d6
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688105"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-on-macos"></a>Erkennen und Blockieren potenziell unerwünschter Anwendungen mit Microsoft Defender for Endpoint unter macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


Das Feature zum Schutz potenziell unerwünschter Anwendungen (PUA) in Microsoft Defender for Endpoint auf macOS kann PUA-Dateien auf Endpunkten in Ihrem Netzwerk erkennen und blockieren.

Diese Anwendungen gelten nicht als Viren, Schadsoftware oder andere Arten von Bedrohungen, sie können jedoch Aktionen für Endpunkte ausführen, die sich negativ auf ihre Leistung oder Verwendung auswirken. PUA kann sich auch auf Anwendungen beziehen, die als schlecht angesehen werden.

Diese Anwendungen können das Risiko erhöhen, dass Ihr Netzwerk mit Schadsoftware infiziert wird, Schadsoftwareinfektionen schwieriger zu identifizieren sind und IT-Ressourcen beim Bereinigen der Anwendungen verschwenden.

## <a name="how-it-works"></a>Funktionsweise

Microsoft Defender for Endpoint auf macOS kann PUA-Dateien erkennen und melden. Wenn sie im Sperrmodus konfiguriert sind, werden PUA-Dateien in die Quarantäne verschoben.

Wenn ein PUA auf einem Endpunkt erkannt wird, stellt Microsoft Defender for Endpoint unter macOS eine Benachrichtigung für den Benutzer vor, es sei denn, Benachrichtigungen wurden deaktiviert. Der Bedrohungsname enthält das Wort "Application".

## <a name="configure-pua-protection"></a>Konfigurieren des PUA-Schutzes

Der PUA-Schutz in Microsoft Defender for Endpoint unter macOS kann auf eine der folgenden Arten konfiguriert werden:

- **Off**: Der PUA-Schutz ist deaktiviert.
- **Überwachung:** PUA-Dateien werden in den Produktprotokollen, jedoch nicht im Microsoft Defender Security Center gemeldet. Dem Benutzer wird keine Benachrichtigung angezeigt, und es werden keine Aktionen vom Produkt ergriffen.
- **Block**: PUA-Dateien werden in den Produktprotokollen und im Microsoft Defender Security Center gemeldet. Dem Benutzer wird eine Benachrichtigung angezeigt, und das Produkt wird aktiv.

>[!WARNING]
>Standardmäßig ist der PUA-Schutz im **Überwachungsmodus** konfiguriert.

Sie können konfigurieren, wie PUA-Dateien über die Befehlszeile oder über die Verwaltungskonsole behandelt werden.

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a>Verwenden Sie das Befehlszeilentool, um den PUA-Schutz zu konfigurieren:

Führen Sie im Terminal den folgenden Befehl aus, um den PUA-Schutz zu konfigurieren:

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a>Konfigurieren des PUA-Schutzes mithilfe der Verwaltungskonsole:

In Ihrem Unternehmen können Sie den PUA-Schutz über eine Verwaltungskonsole wie JAMF oder Intune konfigurieren, ähnlich wie andere Produkteinstellungen konfiguriert sind. Weitere Informationen finden Sie im Abschnitt [Bedrohungstypeinstellungen](mac-preferences.md#threat-type-settings) im Thema Festlegen von Einstellungen für [Microsoft Defender for Endpoint auf macOS.](mac-preferences.md)

## <a name="related-topics"></a>Verwandte Themen

- [Festlegen von Einstellungen für Microsoft Defender for Endpoint unter macOS](mac-preferences.md)
