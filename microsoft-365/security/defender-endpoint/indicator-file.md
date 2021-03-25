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
ms.openlocfilehash: 35a0b66a4cdc4cf39c15329eda2e0aafced79f34
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199609"
---
# <a name="create-indicators-for-files"></a>Erstellen von Indikatoren für Dateien

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



> [!TIP]
> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

Sie können die weitere Verbreitung eines Angriffs in Ihrer Organisation verhindern, indem Sie potenziell schädliche Dateien oder mutmaßliche Schadsoftware verbieten. Wenn Sie eine potenziell schädliche ausführbare Datei (PE) kennen, können Sie sie blockieren. Dieser Vorgang verhindert, dass er auf Computern in Ihrer Organisation gelesen, geschrieben oder ausgeführt wird.

Es gibt zwei Möglichkeiten zum Erstellen von Indikatoren für Dateien:
- Durch Erstellen eines Indikators über die Einstellungsseite
- Durch Erstellen eines kontextbezogenen Indikators mithilfe der Schaltfläche "Indikator hinzufügen" auf der Seite "Dateidetails"

### <a name="before-you-begin"></a>Bevor Sie beginnen
Es ist wichtig, die folgenden Voraussetzungen zu kennen, bevor Sie Indikatoren für Dateien erstellen:

- Dieses Feature ist verfügbar, wenn Ihre Organisation Windows Defender Antivirus und cloudbasierter Schutz aktiviert ist. Weitere Informationen finden Sie unter [Use next-generation technologies in Microsoft Defender Antivirus through cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus).
- Die Antischalwareclientversion muss 4.18.1901.x oder höher sein.
- Unterstützt auf Computern unter Windows 10, Version 1703 oder höher, Windows Server 2016 und 2019.
- Um mit dem Blockieren von Dateien zu beginnen, müssen Sie zunächst das [ **Feature Blockieren**](advanced-features.md) oder Zulassen unter Einstellungen aktivieren.
- Dieses Feature soll verhindern, dass mutmaßliche Schadsoftware (oder potenziell schädliche Dateien) aus dem Web heruntergeladen werden. Es unterstützt zurzeit portable ausführbare (PE)-Dateien, einschließlich _EXE-_ und _DLL-Dateien._ Die Abdeckung wird im Laufe der Zeit erweitert.

Die Leistung kann beeinträchtigt werden, wenn Sie große Dateien aus einer Netzwerkfreigabe auf Ihr lokales Gerät kopieren, insbesondere über eine VPN-Verbindung. 

> [!IMPORTANT]
> - Die Funktion "Zulassen" oder "Blockieren" kann nicht für Dateien durchgeführt werden, wenn die Dateiklassifizierung im Cache des Geräts vor der Aktion "Zulassen" oder "Blockieren" vorhanden ist 
> - Vertrauenswürdige signierte Dateien werden unterschiedlich behandelt. Defender for Endpoint ist für die Verarbeitung schädlicher Dateien optimiert. Der Versuch, vertrauenswürdige signierte Dateien zu blockieren, kann in einigen Fällen Auswirkungen auf die Leistung haben.
> - In der Regel werden Dateiblöcke innerhalb weniger Minuten erzwungen, können jedoch bis zu 30 Minuten dauern.
> - Wenn Richtlinien für Dateiindikator in Konflikt stehen, wird die Erzwingungsrichtlinie der sichereren Richtlinie angewendet. Beispielsweise hat eine SHA-256-Dateihashindikatorrichtlinie Vorrang vor einer MD5-Dateihashindikatorrichtlinie, wenn beide Hashtypen dieselbe Datei definieren.

### <a name="create-an-indicator-for-files-from-the-settings-page"></a>Erstellen eines Indikators für Dateien auf der Einstellungsseite

1. Wählen Sie im Navigationsbereich **Einstellungsindikatoren**  >  **aus.**  

2. Wählen Sie die **Registerkarte Dateihash** aus.

3. Wählen **Sie Indikator hinzufügen aus.**

4. Geben Sie die folgenden Details an:
   - Indikator – Geben Sie die Entitätsdetails an, und definieren Sie den Ablauf des Indikators.
   - Aktion – Geben Sie die zu ergreifende Aktion an, und geben Sie eine Beschreibung an.
   - Bereich : Definieren Sie den Bereich der Computergruppe.

5. Überprüfen Sie die Details auf der Registerkarte Zusammenfassung, und klicken Sie dann auf **Speichern**.

### <a name="create-a-contextual-indicator-from-the-file-details-page"></a>Erstellen eines Kontextindikators auf der Seite mit den Dateidetails
Eine der Optionen beim Ausführen von [Reaktionsaktionen für eine](respond-file-alerts.md) Datei ist das Hinzufügen eines Indikators für die Datei. 

Wenn Sie einen Indikatorhash für eine Datei hinzufügen, können Sie eine Warnung ausgelöst und die Datei blockieren, wenn ein Computer in Ihrer Organisation versucht, sie zu ausführen.

Dateien, die automatisch von einem Indikator blockiert werden, werden nicht im Aktionscenter der Datei angezeigt, aber die Warnungen werden weiterhin in der Warnungswarteschlange angezeigt.


## <a name="related-topics"></a>Verwandte Themen
- [Erstellen von Indikatoren](manage-indicators.md)
- [Erstellen von Indikatoren für IPs und URLs/Domänen](indicator-ip-domain.md)
- [Erstellen von Indikatoren basierend auf Zertifikaten](indicator-certificates.md)
- [Verwalten von Indikatoren](indicator-manage.md)
