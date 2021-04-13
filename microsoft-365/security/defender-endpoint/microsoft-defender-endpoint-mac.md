---
title: Microsoft Defender für Endpoint auf Dem Mac
ms.reviewer: ''
description: Erfahren Sie, wie Sie Microsoft Defender for Endpoint auf Mac installieren, konfigurieren, aktualisieren und verwenden.
keywords: microsoft, defender, atp, mac, installation, deploy, uninstallation, intune, jamf, macos, big sur, catalina, mojave, mde for mac
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
ms.openlocfilehash: 406a0e699ea563670f41355d122aa54ba8667a0e
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687745"
---
# <a name="microsoft-defender-for-endpoint-on-mac"></a>Microsoft Defender für Endpoint auf Dem Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

In diesem Thema wird beschrieben, wie Sie Defender for Endpoint auf Dem Mac installieren, konfigurieren, aktualisieren und verwenden.

> [!CAUTION]
> Das Ausführen anderer Endpunktschutzprodukte von Drittanbietern zusammen mit Microsoft Defender for Endpoint auf Mac führt wahrscheinlich zu Leistungsproblemen und unvorhersehbaren Nebenwirkungen. Wenn in Ihrer Umgebung kein Microsoft-Endpunktschutz eine absolute Anforderung ist, können Sie die Funktionen von Defender for Endpoint auf Mac EDR weiterhin sicher nutzen, nachdem Sie die Antivirenfunktionen so konfiguriert haben, dass sie im passiven Modus [ausgeführt werden.](mac-preferences.md#enable--disable-passive-mode)

## <a name="whats-new-in-the-latest-release"></a>Neuigkeiten in der neuesten Version

[Neuigkeiten in Microsoft Defender für Endpunkt](whats-new-in-microsoft-defender-atp.md)

[Neues in Microsoft Defender for Endpoint auf Mac](mac-whatsnew.md)

> [!TIP]
> Wenn Sie Feedback haben, das Sie freigeben möchten, übermitteln Sie es, indem Sie Microsoft Defender for Endpoint auf Dem Mac auf Ihrem Gerät öffnen und navigieren, um Feedback zu  >  senden.

Um die neuesten Features, einschließlich Vorschaufunktionen (z. B. Endpunkterkennung und -antwort für Ihre Mac-Geräte), zu erhalten, konfigurieren Sie Ihr macOS-Gerät, auf dem Microsoft Defender for Endpoint ausgeführt wird, als "Insider"-Gerät.

## <a name="how-to-install-microsoft-defender-for-endpoint-on-mac"></a>Installieren von Microsoft Defender for Endpoint auf Dem Mac

### <a name="prerequisites"></a>Voraussetzungen

- Ein Defender for Endpoint-Abonnement und Zugriff auf das Microsoft Defender Security Center-Portal
- Erfahrung auf Anfängerebene in macOS- und BASH-Skripting
- Administratorrechte auf dem Gerät (bei manueller Bereitstellung)

### <a name="installation-instructions"></a>Installationsanweisungen

Es gibt mehrere Methoden und Bereitstellungstools, die Sie zum Installieren und Konfigurieren von Defender for Endpoint auf Dem Mac verwenden können.

- Verwaltungstools von Drittanbietern:
    - [Microsoft-Intune-basierte Bereitstellung](mac-install-with-intune.md)
    - [JAMF-basierte Bereitstellung](mac-install-with-jamf.md)
    - [Andere MDM-Produkte](mac-install-with-other-mdm.md)

- Befehlszeilentool:
    - [Manuelle Bereitstellung](mac-install-manually.md)

### <a name="system-requirements"></a>Systemanforderungen

Die drei neuesten Hauptversionen von macOS werden unterstützt.

> [!IMPORTANT]
> Unter macOS 11 (Big Sur) erfordert Microsoft Defender for Endpoint zusätzliche Konfigurationsprofile. Wenn Sie ein vorhandenes Kunden-Upgrade von früheren Versionen von macOS sind, stellen Sie sicher, dass Sie die zusätzlichen Konfigurationsprofile bereitstellen, die unter Neue Konfigurationsprofile für [macOS Catalina](mac-sysext-policies.md)und neuere Versionen von macOS aufgeführt sind.

> [!IMPORTANT]
> Die Unterstützung für macOS 10.13 (High Sierra) wurde ab dem 15. Februar 2021 eingestellt.

- 11 (Big Sur), 10.15 (Catalina), 10.14 (Mojave)
- Speicherplatz: 1 GB

Betaversionen von macOS werden nicht unterstützt.

Nachdem Sie den Dienst aktiviert haben, müssen Sie möglicherweise Ihr Netzwerk oder ihre Firewall so konfigurieren, dass ausgehende Verbindungen zwischen dem Dienst und Ihren Endpunkten zulässig sind.

### <a name="licensing-requirements"></a>Lizenzierungsanforderungen

Microsoft Defender für Endpoint auf Mac erfordert eines der folgenden Microsoft Volumenlizenzangebote:

- Microsoft 365 E5 (M365 E5)
- Microsoft 365 E5 Security
- Microsoft 365 A5 (M365 A5)

> [!NOTE]
> Berechtigte lizenzierte Benutzer können Microsoft Defender for Endpoint auf bis zu fünf gleichzeitigen Geräten verwenden.
> Microsoft Defender for Endpoint steht auch bei einem Cloud Solution Provider (CSP) zum Kauf zur Verfügung. Wenn sie über einen CSP erworben werden, sind keine Microsoft Volumenlizenzangebote aufgeführt.

### <a name="network-connections"></a>Netzwerkverbindungen

In der folgenden herunterladbaren Kalkulationstabelle sind die Dienste und die zugehörigen URLs aufgeführt, mit deren Netzwerk eine Verbindung herstellen kann. Sie sollten sicherstellen, dass es keine Firewall- oder Netzwerkfilterregeln gibt, die den  Zugriff auf diese URLs verweigern würden, oder Sie müssen möglicherweise eine speziell für sie zulässige Regel erstellen.



|**Tabellenkalkulation der Domänenliste**|**Beschreibung**|
|:-----|:-----|
|![Thumb image for Microsoft Defender for Endpoint URLs spreadsheet](images/mdatp-urls.png)<br/>  | Tabellenkalkulation bestimmter DNS-Einträge für Dienststandorte, geografische Standorte und Betriebssysteme. <br><br>Laden Sie die Kalkulationstabelle [ hier herunter:mdatp-urls.xlsx](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx).

Microsoft Defender for Endpoint kann einen Proxyserver mithilfe der folgenden Ermittlungsmethoden ermitteln:
- Proxy autoconfig (PAC)
- Webproxy-AutoErmittlungsprotokoll (WPAD)
- Manuelle Konfiguration statischer Proxys

Wenn ein Proxy oder eine Firewall anonymen Datenverkehr blockiert, stellen Sie sicher, dass anonymer Datenverkehr in den zuvor aufgeführten URLs zulässig ist.

> [!WARNING]
> Authentifizierte Proxys werden nicht unterstützt. Stellen Sie sicher, dass nur PAC, WPAD oder ein statischer Proxy verwendet wird.
>
> Ssl-Überprüfung und Abfangen von Proxys werden aus Sicherheitsgründen ebenfalls nicht unterstützt. Konfigurieren Sie eine Ausnahme für die SSL-Überprüfung und Ihren Proxyserver, um Daten von Microsoft Defender for Endpoint auf macOS direkt an die relevanten URLs ohne Abfangen zu übergeben. Wenn Sie Ihr Abfangzertifikat zum globalen Speicher hinzufügen, ist das Abfangen nicht zulässig.

Öffnen Sie und in einem Browser, um zu testen, ob eine Verbindung [https://x.cp.wd.microsoft.com/api/report](https://x.cp.wd.microsoft.com/api/report) [https://cdn.x.cp.wd.microsoft.com/ping](https://cdn.x.cp.wd.microsoft.com/ping) nicht blockiert ist.

Wenn Sie die Befehlszeile bevorzugen, können Sie die Verbindung auch überprüfen, indem Sie den folgenden Befehl im Terminal ausführen:

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

Die Ausgabe dieses Befehls sollte der folgenden ähneln:

 `OK https://x.cp.wd.microsoft.com/api/report`

 `OK https://cdn.x.cp.wd.microsoft.com/ping`

> [!CAUTION]
> Es wird empfohlen, den [Systemintegritätsschutz (System Integrity Protection,](https://support.apple.com/en-us/HT204899) SIP) auf Clientgeräten aktiviert zu lassen. SIP ist ein integriertes macOS-Sicherheitsfeature, das Fälschungen auf niedriger Ebene am Betriebssystem verhindert und standardmäßig aktiviert ist.

Sobald Microsoft Defender for Endpoint installiert ist, kann die Konnektivität überprüft werden, indem der folgende Befehl im Terminal ausgeführt wird:
```bash
mdatp connectivity test
```

## <a name="how-to-update-microsoft-defender-for-endpoint-on-mac"></a>Aktualisieren von Microsoft Defender for Endpoint auf Dem Mac

Microsoft veröffentlicht regelmäßig Softwareupdates, um leistung, Sicherheit und neue Features zu verbessern. Zum Aktualisieren von Microsoft Defender for Endpoint auf Mac wird ein Programm namens Microsoft AutoUpdate (MAU) verwendet. Weitere Informationen finden Sie unter [Deploy updates for Microsoft Defender for Endpoint on Mac](mac-updates.md).

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-mac"></a>Konfigurieren von Microsoft Defender for Endpoint auf Dem Mac

Anleitungen zum Konfigurieren des Produkts in Unternehmensumgebungen finden Sie unter [Set preferences for Microsoft Defender for Endpoint on Mac](mac-preferences.md).

## <a name="macos-kernel-and-system-extensions"></a>macOS-Kernel und Systemerweiterungen

In Übereinstimmung mit der macOS-Weiterentwicklung bereiten wir ein Microsoft Defender for Endpoint on Mac-Update vor, das Systemerweiterungen anstelle von Kernelerweiterungen nutzt. Relevante Details finden Sie unter [What's new in Microsoft Defender for Endpoint on Mac](mac-whatsnew.md).

## <a name="resources"></a>Ressourcen

- Weitere Informationen zum Protokollieren, Deinstallieren oder anderen Themen finden Sie unter [Ressourcen für Microsoft Defender for Endpoint auf Mac](mac-resources.md).

- [Datenschutz für Microsoft Defender for Endpoint auf Mac](mac-privacy.md).
