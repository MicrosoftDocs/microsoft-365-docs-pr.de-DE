---
title: Untersuchen einer einer Warnung zugeordneten IP-Adresse
description: Verwenden Sie die Untersuchungsoptionen, um die mögliche Kommunikation zwischen Geräten und externen IP-Adressen zu untersuchen.
keywords: Untersuchen, Untersuchen, IP-Adresse, Warnung, Microsoft Defender for Endpoint, externe IP
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: cb95deb890b52f0f5fde26a3a193181713b8ae5f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933829"
---
# <a name="investigate-an-ip-address-associated-with-a-microsoft-defender-for-endpoint-alert"></a>Untersuchen einer einer Microsoft Defender for Endpoint-Warnung zugeordneten IP-Adresse

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Untersuchen Sie die mögliche Kommunikation zwischen Ihren Geräten und externen Ip-Adressen (Internet Protocol).

Das Identifizieren aller Geräte in der Organisation, die mit einer verdächtigen oder bekannten schädlichen #A0 kommuniziert haben, z. B. Command and Control (C2)-Server, trägt dazu bei, den potenziellen Umfang von Sicherheitsverletzungen, zugeordneten Dateien und infizierten Geräten zu ermitteln.

Informationen finden Sie in den folgenden Abschnitten in der IP-Adressansicht:

- IP weltweit
- Reverse-DNS-Namen
- Warnungen im Zusammenhang mit dieser IP
- IP in der Organisation
- Prävalenz

## <a name="ip-worldwide-and-reverse-dns-names"></a>IP Weltweit und Reverse-DNS-Namen

Der Abschnitt "IP-Adressdetails" zeigt Attribute der IP-Adresse, z. B. den ASN und die Reverse-DNS-Namen.

## <a name="alerts-related-to-this-ip"></a>Warnungen im Zusammenhang mit dieser IP

Der **Abschnitt Warnungen im Zusammenhang** mit diesem IP enthält eine Liste der Warnungen, die der IP zugeordnet sind.

## <a name="ip-in-organization"></a>IP in der Organisation

Der **Abschnitt IP in Organization** enthält Details zur Verbreitung der IP-Adresse in der Organisation.

## <a name="prevalence"></a>Prävalenz

Im **Abschnitt Verbreitung** wird angezeigt, wie viele Geräte mit dieser IP-Adresse verbunden sind und wann die IP zuerst und zuletzt gesehen wurde. Sie können die Ergebnisse dieses Abschnitts nach Zeitraum filtern. Der Standardzeitraum beträgt 30 Tage.

## <a name="most-recent-observed-devices-with-ip"></a>Zuletzt beobachtete Geräte mit IP

Der **Abschnitt Zuletzt beobachtete** Geräte mit IP bietet eine chronologische Ansicht der Ereignisse und zugehörigen Warnungen, die an der IP-Adresse beobachtet wurden.

**Untersuchen einer externen IP:**

1. Wählen **Sie im** Dropdownmenü **Suchleiste** IP aus.
2. Geben Sie die IP-Adresse in das Feld **Suche** ein.
3. Klicken Sie auf das Suchsymbol, oder drücken Sie die **EINGABETASTE.**

Details zur IP-Adresse werden angezeigt, darunter: Registrierungsdetails (sofern verfügbar), Reverse-IPs (z. B. Domänen), Verbreitung von Geräten in der Organisation, die mit dieser IP-Adresse kommuniziert haben (während eines auswählbaren Zeitraums) und die Geräte in der Organisation, die beobachtet wurden, wie sie mit dieser IP-Adresse kommunizieren.

> [!NOTE]
> Suchergebnisse werden nur für IP-Adressen zurückgegeben, die in der Kommunikation mit Geräten in der Organisation beobachtet werden.

Verwenden Sie die Suchfilter, um die Suchkriterien zu definieren. Sie können auch das Zeitachsensuchfeld verwenden, um die angezeigten Ergebnisse aller Geräte in der Organisation zu filtern, die die Kommunikation mit der IP-Adresse, der der Kommunikation zugeordneten Datei und dem letzten beobachteten Datum beobachtet haben.

Wenn Sie auf einen der Gerätenamen klicken, werden Sie zur Ansicht dieses Geräts angezeigt, in der Sie gemeldete Warnungen, Verhaltensweisen und Ereignisse weiterhin untersuchen können.

## <a name="related-topics"></a>Verwandte Themen

- [Anzeigen und Organisieren der Microsoft Defender for Endpoint Alerts-Warteschlange](alerts-queue.md)
- [Verwalten von Microsoft Defender for Endpoint-Warnungen](manage-alerts.md)
- [Untersuchen von Microsoft Defender for Endpoint-Warnungen](investigate-alerts.md)
- [Untersuchen einer Datei, die einer Microsoft Defender for Endpoint-Warnung zugeordnet ist](investigate-files.md)
- [Untersuchen von Geräten in der Microsoft Defender for Endpoint Devices-Liste](investigate-machines.md)
- [Untersuchen einer Domäne, die einer Microsoft Defender for Endpoint-Warnung zugeordnet ist](investigate-domain.md)
- [Untersuchen eines Benutzerkontos in Microsoft Defender for Endpoint](investigate-user.md)
