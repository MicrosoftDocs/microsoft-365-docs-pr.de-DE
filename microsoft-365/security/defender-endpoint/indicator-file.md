---
title: Erstellen von Indikatoren für Dateien
ms.reviewer: ''
description: Erstellen Sie Indikatoren für einen Dateihash, die die Erkennung, Verhinderung und den Ausschluss von Entitäten definieren.
keywords: Datei, Hash, verwalten, zulässig, blockiert, blockieren, sauber, bösartig, Dateihash, IP-Adresse, URLs, Domäne
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
ms.openlocfilehash: b56a18e1b35b65629318ab29f2189ef1f73373f5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256915"
---
# <a name="create-indicators-for-files"></a>Erstellen von Indikatoren für Dateien

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Möchten Sie Defender für Endpunkt erfahren? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

Verhindern Sie die weitere Verbreitung eines Angriffs in Ihrer Organisation, indem Sie potenziell schädliche Dateien oder verdächtige Schadsoftware verbieten. Wenn Sie eine potenziell schädliche portierbare ausführbare Datei (PE) kennen, können Sie sie blockieren. Dieser Vorgang verhindert, dass er auf Geräten in Ihrer Organisation gelesen, geschrieben oder ausgeführt wird.

Es gibt drei Möglichkeiten, Indikatoren für Dateien zu erstellen:

- Durch Erstellen eines Indikators über die Einstellungsseite
- Durch Erstellen eines Kontextindikators mithilfe der Schaltfläche "Indikator hinzufügen" auf der Dateidetailseite
- Durch Erstellen eines Indikators über die [Indikator-API](ti-indicator.md)

## <a name="before-you-begin"></a>Vorabinformationen

Es ist wichtig, die folgenden Voraussetzungen zu verstehen, bevor Sie Indikatoren für Dateien erstellen:

- Dieses Feature ist verfügbar, wenn Ihre Organisation **Microsoft Defender Antivirus (im aktiven Modus)** verwendet und **der cloudbasierte Schutz aktiviert ist.** Weitere Informationen finden Sie unter [Verwalten des cloudbasierten Schutzes.](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)

- Die Antischadsoftware-Clientversion muss 4.18.1901.x oder höher sein. Siehe [monatliche Plattform- und Modulversionen](manage-updates-baselines-microsoft-defender-antivirus.md#monthly-platform-and-engine-versions)

- Unterstützt auf Geräten mit Windows 10, Version 1703 oder höher, Windows Server 2016 und 2019.

- Um mit dem Blockieren von Dateien zu beginnen, müssen Sie zuerst [das Feature "Blockieren oder Zulassen"](advanced-features.md) in Einstellungen aktivieren.

Dieses Feature soll verhindern, dass verdächtige Schadsoftware (oder potenziell schädliche Dateien) aus dem Web heruntergeladen wird. Derzeit werden portierbare ausführbare Dateien (PORTABLE Executable, PE) unterstützt, einschließlich .exe- und .dll dateien. Die Abdeckung wird im Laufe der Zeit erweitert.

## <a name="create-an-indicator-for-files-from-the-settings-page"></a>Erstellen eines Indikators für Dateien auf der Einstellungsseite

1. Wählen Sie im Navigationsbereich **Einstellungen > Indikatoren** aus.

2. Wählen Sie die Registerkarte **"Dateihash"**   aus.

3. Wählen Sie **"Indikator hinzufügen" aus.**

4. Geben Sie die folgenden Details an:
    - Indikator – Geben Sie die Entitätsdetails an, und definieren Sie den Ablauf des Indikators.
    - Aktion – Geben Sie die auszuführende Aktion an, und geben Sie eine Beschreibung an.
    - Bereich – Definieren Sie den Bereich der Gerätegruppe.

5. Überprüfen Sie die Details auf der Registerkarte "Zusammenfassung", und wählen Sie dann **"Speichern"** aus.

## <a name="create-a-contextual-indicator-from-the-file-details-page"></a>Erstellen eines Kontextindikators auf der Dateidetailseite

Eine der Optionen beim Ausführen von [Antwortaktionen für eine Datei](respond-file-alerts.md)ist das   Hinzufügen eines Indikators für die Datei. Wenn Sie einen Indikatorhash für eine Datei hinzufügen, können Sie eine Warnung auslösen und die Datei blockieren, wenn ein Gerät in Ihrer Organisation versucht, sie auszuführen.

Dateien, die automatisch durch einen Indikator blockiert werden, werden nicht im Info-Center der Datei angezeigt, aber die Warnungen werden weiterhin in der Warnungswarteschlange angezeigt.

>[!IMPORTANT]
>- Dateiblöcke werden in der Regel innerhalb weniger Minuten erzwungen und entfernt, können jedoch bis zu 30 Minuten dauern.
> 
>- Wenn es widersprüchliche Datei-IoC-Richtlinien mit demselben Erzwingungstyp und Ziel gibt, wird die Richtlinie des sichereren Hash angewendet. Eine SHA-256-Dateihash-IoC-Richtlinie hat Vorrang vor einer SHA-1-Dateihash-IoC-Richtlinie, die eine MD5-Dateihash-IoC-Richtlinie gewinnen wird, wenn die Hashtypen dieselbe Datei definieren. Dies gilt unabhängig von der Gerätegruppe. 
>   Wenn in allen anderen Fällen in Konflikt stehende Datei-IoC-Richtlinien mit demselben Erzwingungsziel auf alle Geräte und auf die Gruppe des Geräts angewendet werden, wird für ein Gerät die Richtlinie in der Gerätegruppe gewonnen. 
>   
>- Wenn die EnableFileHashComputation-Gruppenrichtlinie deaktiviert ist, wird die Blockiergenauigkeit der Datei IoC verringert. Die Aktivierung kann sich jedoch `EnableFileHashComputation` auf die Geräteleistung auswirken. Das Kopieren großer Dateien von einer Netzwerkfreigabe auf Ihr lokales Gerät, insbesondere über eine VPN-Verbindung, kann sich beispielsweise auf die Geräteleistung auswirken.
>
>   Weitere Informationen zur Gruppenrichtlinie "EnableFileHashComputation" finden Sie unter [Defender CSP.](/windows/client-management/mdm/defender-csp)

## <a name="policy-conflict-handling"></a>Behandlung von Richtlinienkonflikten  

Der Konflikt bei der Behandlung von Zertifikat- und Datei-IoC-Richtlinien folgt der folgenden Reihenfolge:

- Wenn die Datei von Windows Defender Anwendungssteuerung und AppLocker-Richtlinie/Richtlinien für den Erzwingungsmodus nicht zulässig ist, blockieren **Sie**

- Andernfalls, wenn die Datei durch den Microsoft Defender Antivirus Ausschluss zulässig ist, dann **zulassen**

- Andernfalls, wenn die Datei blockiert oder durch eine Blockierung oder warnungsdatei IoC gewarnt wird, dann **blockieren/warnen**

- Andernfalls, wenn die Datei durch eine Allow-Datei-IoC-Richtlinie zulässig ist, dann **zulassen**

- Andernfalls, wenn die Datei durch ASR-Regeln blockiert wird, CFA, AV, SmartScreen, dann **blockieren**  

- Else **Allow** (übergibt Windows Defender Anwendungssteuerung & AppLocker-Richtlinie, es gelten keine IoC-Regeln)

Wenn es widersprüchliche Datei-IoC-Richtlinien mit demselben Erzwingungstyp und Ziel gibt, wird die Richtlinie des sichereren (d. h. längeren) Hash angewendet. Beispielsweise wird eine IOC-Richtlinie mit SHA-256-Dateihash eine MD5-Dateihash-IoC-Richtlinie gewinnen, wenn beide Hashtypen dieselbe Datei definieren.

Die Features von Bedrohungen und Sicherheitsrisikomanagement blockieren anfällige Anwendungen verwenden die Datei-IoCs für die Erzwingung und folgen der oben genannten Konfliktbehandlungsreihenfolge.

### <a name="examples"></a>Beispiele

|Komponente |Erzwingung von Komponenten |Dateiindikatoraktion |Ergebnis
|--|--|--|--|
|Ausschluss des Dateipfads zur Verringerung der Angriffsfläche |Zulassen |Blockieren |Blockieren
|Regel zur Verringerung der Angriffsfläche |Blockieren |Zulassen |Zulassen
|Windows Defender Application Control |Zulassen |Blockieren |Zulassen |
|Windows Defender Application Control |Blockieren |Zulassen |Blockieren
|Microsoft Defender Antivirus Ausschluss |Zulassen |Blockieren |Zulassen

## <a name="see-also"></a>Siehe auch

- [Indikatoren erstellen](manage-indicators.md)
- [Erstellen von Indikatoren für IPs und URLs/Domänen](indicator-ip-domain.md)
- [Erstellen von Indikatoren basierend auf Zertifikaten](indicator-certificates.md)
- [Indikatoren verwalten](indicator-manage.md)
