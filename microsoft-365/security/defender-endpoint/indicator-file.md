---
title: Erstellen von Indikatoren für Dateien
ms.reviewer: ''
description: Erstellen Sie Indikatoren für einen Dateihash, der die Erkennung, Verhinderung und den Ausschluss von Entitäten definiert.
keywords: datei, hash, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 103f5d0ad9d12a37f3a3b8065f39c24d592cc252
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995057"
---
# <a name="create-indicators-for-files"></a>Erstellen von Indikatoren für Dateien

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

Verhindern Sie die weitere Verbreitung eines Angriffs in Ihrer Organisation, indem Sie potenziell schädliche Dateien oder mutmaßliche Schadsoftware verbieten. Wenn Sie eine potenziell schädliche ausführbare Datei (PE) kennen, können Sie sie blockieren. Dieser Vorgang verhindert, dass er auf Geräten in Ihrer Organisation gelesen, geschrieben oder ausgeführt wird.

Es gibt drei Möglichkeiten zum Erstellen von Indikatoren für Dateien:

- Durch Erstellen eines Indikators über die Einstellungsseite
- Durch Erstellen eines kontextbezogenen Indikators mithilfe der Schaltfläche "Indikator hinzufügen" auf der Seite "Dateidetails"
- Durch Erstellen eines Indikators über die [Indikator-API](ti-indicator.md)

## <a name="before-you-begin"></a>Bevor Sie beginnen

Es ist wichtig, die folgenden Voraussetzungen zu kennen, bevor Sie Indikatoren für Dateien erstellen:

- Dieses Feature ist verfügbar, wenn Ihre Organisation **Microsoft Defender Antivirus (im** aktiven Modus) verwendet und der **cloudbasierte Schutz aktiviert ist.** Weitere Informationen finden Sie unter [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).

- Die Antischalwareclientversion muss 4.18.1901.x oder höher sein. Siehe [Monatliche Plattform- und Modulversionen](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)

- Unterstützt auf Geräten mit Windows 10, Version 1703 oder höher, Windows Server 2016 und 2019.

- Um mit dem Blockieren von Dateien zu beginnen, müssen Sie zunächst das Feature ["Blockieren oder Zulassen"](advanced-features.md) in den Einstellungen aktivieren.

Dieses Feature soll verhindern, dass mutmaßliche Schadsoftware (oder potenziell schädliche Dateien) aus dem Web heruntergeladen werden. Es unterstützt zurzeit portable ausführbare (PE)-Dateien, einschließlich EXE- und DLL-Dateien. Die Abdeckung wird im Laufe der Zeit erweitert.

## <a name="create-an-indicator-for-files-from-the-settings-page"></a>Erstellen eines Indikators für Dateien auf der Einstellungsseite

1. Wählen Sie im Navigationsbereich Einstellungen **> Indikatoren aus.**

2. Wählen Sie die **Registerkarte Dateihash**   aus.

3. Wählen **Sie Indikator hinzufügen aus.**

4. Geben Sie die folgenden Details an:
    - Indikator – Geben Sie die Entitätsdetails an, und definieren Sie den Ablauf des Indikators.
    - Aktion – Geben Sie die zu ergreifende Aktion an, und geben Sie eine Beschreibung an.
    - Bereich : Definieren Sie den Bereich der Gerätegruppe.

5. Überprüfen Sie die Details auf der Registerkarte Zusammenfassung, und wählen Sie dann **Speichern aus.**

## <a name="create-a-contextual-indicator-from-the-file-details-page"></a>Erstellen eines Kontextindikators auf der Seite mit den Dateidetails

Eine der Optionen beim Ausführen von [Reaktionsaktionen für eine](respond-file-alerts.md)Datei ist das   Hinzufügen eines Indikators für die Datei. Wenn Sie einen Indikatorhash für eine Datei hinzufügen, können Sie eine Warnung ausgelöst und die Datei blockieren, wenn ein Gerät in Ihrer Organisation versucht, sie zu ausführen.

Dateien, die automatisch von einem Indikator blockiert werden, werden nicht im Aktionscenter der Datei angezeigt, aber die Warnungen werden weiterhin in der Warnungswarteschlange angezeigt.

>[!IMPORTANT]
>- In der Regel werden Dateiblöcke innerhalb weniger Minuten erzwungen und entfernt, können jedoch bis zu 30 Minuten dauern.
>- Wenn Richtlinien für Dateiindikator in Konflikt stehen, wird die Erzwingungsrichtlinie der sichereren Richtlinie angewendet. Beispielsweise hat eine SHA-256-Dateihashindikatorrichtlinie Vorrang vor einer MD5-Dateihashindikatorrichtlinie, wenn beide Hashtypen dieselbe Datei definieren.
>- Wenn die Gruppenrichtlinie EnableFileHashComputation deaktiviert ist, wird die Sperrgenauigkeit der Datei IoC reduziert. Das Aktivieren von EnableFileHashComputation kann sich jedoch auf die Geräteleistung auswirken.
>    - Das Kopieren großer Dateien aus einer Netzwerkfreigabe auf Ihr lokales Gerät, insbesondere über eine VPN-Verbindung, kann sich beispielsweise auf die Geräteleistung auswirken.
>    - Weitere Informationen zur Gruppenrichtlinie EnableFileHashComputation finden Sie unter [Defender CSP](/windows/client-management/mdm/defender-csp)

## <a name="policy-conflict-handling"></a>Behandlung von Richtlinienkonflikten  

Die Behandlung von Konflikten zwischen Cert- und File IoC-Richtlinien folgt der folgenden Reihenfolge:

- Wenn die Datei nicht von Windows Defender Anwendungssteuerung und AppLocker Richtlinien/Richtlinien für den Erzwungenen Modus zulässig ist, dann **Blockieren**

- Andern falls die Datei vom Defender Anti-Virus Exclusion zugelassen ist, dann **Zulassen**

- Andern falls die Datei durch einen Block oder eine Warndatei blockiert oder gewarnt wird, dann **Blockieren/Warnen**

- Wenn die Datei von einer IOC-Richtlinie für zugelassene Dateien zulässig ist, wird **"Zulassen"**

- Andern falls die Datei durch #A0 blockiert wird, CFA, AV, SmartScreen und **dann Blockieren**  

- Else **Allow** (passes Windows Defender Application Control & AppLocker policy, es gelten keine IoC-Regeln)

Wenn #A0 in Konflikt stehen, die denselben Erzwingungstyp und dasselbe Ziel haben, wird die Richtlinie des sichereren (d. h. längeren) Hashs angewendet. Eine SHA-256-Dateihash-IoC-Richtlinie z. B. gewinnt eine #A0 für MD5-Dateihash, wenn beide Hashtypen dieselbe Datei definieren.

Beachten Sie, dass die Features für die Blockierung anfälliger Anwendungen der Bedrohungs- und Sicherheitsrisikoverwaltung die Datei-IoCs für die Erzwingung verwenden und die oben aufgeführte Reihenfolge für die Konfliktbehandlung befolgen.

### <a name="examples"></a>Beispiele

|Komponente |Komponentenersetzung |Dateiindikatoraktion |Ergebnis
|--|--|--|--|
|Dateipfadausschluss zur Attack Surface Reduction |Zulassen |Blockieren |Blockieren
|Regel zur Reduzierung der Angriffsfläche |Blockieren |Zulassen |Zulassen
|Windows Defender Application Control |Zulassen |Blockieren |Zulassen |
|Windows Defender Application Control |Blockieren |Zulassen |Blockieren
|Microsoft Defender Antivirus-Ausschluss |Zulassen |Blockieren |Zulassen

## <a name="see-also"></a>Siehe auch

- [Indikatoren erstellen](manage-indicators.md)
- [Erstellen von Indikatoren für IPs und URLs/Domänen](indicator-ip-domain.md)
- [Erstellen von Indikatoren basierend auf Zertifikaten](indicator-certificates.md)
- [Indikatoren verwalten](indicator-manage.md)
