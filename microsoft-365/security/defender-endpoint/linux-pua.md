---
title: Erkennen und Blockieren potenziell unerwünschter Anwendungen mit Microsoft Defender for Endpoint unter Linux
description: Erkennen und Blockieren von potenziell unerwünschten Anwendungen (PUA) mithilfe von Microsoft Defender for Endpoint unter Linux.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, pua, pus
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 7ec3399129cc65d75b464f5d5f56bb11250ccaf2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933157"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-on-linux"></a>Erkennen und Blockieren potenziell unerwünschter Anwendungen mit Microsoft Defender for Endpoint unter Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Das Feature zum Schutz potenziell unerwünschter Anwendungen (PUA) in Defender for Endpoint unter Linux kann PUA-Dateien auf Endpunkten in Ihrem Netzwerk erkennen und blockieren.

Diese Anwendungen gelten nicht als Viren, Schadsoftware oder andere Arten von Bedrohungen, sie können jedoch Aktionen für Endpunkte ausführen, die sich negativ auf ihre Leistung oder Verwendung auswirken. PUA kann sich auch auf Anwendungen beziehen, die als schlecht angesehen werden.

Diese Anwendungen können das Risiko erhöhen, dass Ihr Netzwerk mit Schadsoftware infiziert wird, Schadsoftwareinfektionen schwieriger zu identifizieren sind und IT-Ressourcen beim Bereinigen der Anwendungen verschwenden.

## <a name="how-it-works"></a>Funktionsweise

Defender for Endpoint unter Linux kann PUA-Dateien erkennen und melden. Wenn sie im Sperrmodus konfiguriert sind, werden PUA-Dateien in die Quarantäne verschoben.

Wenn ein PUA auf einem Endpunkt erkannt wird, speichert Defender for Endpoint unter Linux eine Aufzeichnung der Infektion im Bedrohungsverlauf. Der Verlauf kann über das Microsoft Defender Security Center oder über das `mdatp` Befehlszeilentool visualisiert werden. Der Bedrohungsname enthält das Wort "Application".

## <a name="configure-pua-protection"></a>Konfigurieren des PUA-Schutzes

Der PUA-Schutz in Defender for Endpoint unter Linux kann auf eine der folgenden Arten konfiguriert werden:

- **Off**: Der PUA-Schutz ist deaktiviert.
- **Überwachung**: PUA-Dateien werden in den Produktprotokollen gemeldet, jedoch nicht in Microsoft Defender Security Center. Es werden keine Aufzeichnungen der Infektion im Bedrohungsverlauf gespeichert, und das Produkt hat keine Maßnahmen ergriffen.
- **Block**: PUA-Dateien werden in den Produktprotokollen und in den Microsoft Defender Security Center. Ein Datensatz der Infektion wird im Bedrohungsverlauf gespeichert, und das Produkt hat Maßnahmen ergriffen.

>[!WARNING]
>Standardmäßig ist der PUA-Schutz im **Überwachungsmodus** konfiguriert.

Sie können konfigurieren, wie PUA-Dateien über die Befehlszeile oder über die Verwaltungskonsole behandelt werden.

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a>Verwenden Sie das Befehlszeilentool, um den PUA-Schutz zu konfigurieren:

Führen Sie im Terminal den folgenden Befehl aus, um den PUA-Schutz zu konfigurieren:

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a>Konfigurieren des PUA-Schutzes mithilfe der Verwaltungskonsole:

In Ihrem Unternehmen können Sie den PUA-Schutz über eine Verwaltungskonsole wie "Puppet" oder "Ansible" konfigurieren, ähnlich wie andere Produkteinstellungen konfiguriert sind. Weitere Informationen finden Sie im Abschnitt [Bedrohungstypeinstellungen](linux-preferences.md#threat-type-settings) im Artikel Festlegen von Einstellungen [für Defender for Endpoint unter Linux.](linux-preferences.md)

## <a name="related-articles"></a>Verwandte Artikel

- [Festlegen von Einstellungen für Defender for Endpoint unter Linux](linux-preferences.md)
