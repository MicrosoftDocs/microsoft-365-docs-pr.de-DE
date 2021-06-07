---
title: Konfigurieren und Validieren von Microsoft Defender Antivirus-Netzwerkverbindungen
description: Konfigurieren und testen Sie Ihre Verbindung mit dem Microsoft Defender Antivirus Cloud-Schutzdienst.
keywords: Antivirus, Microsoft Defender Antivirus, Antischadsoftware, Sicherheit, Defender, Cloud, Aggressivität, Schutzebene
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ca5737a0224825a0c88159c4a3931cc0c310b69b
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788451"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a>Konfigurieren und Validieren von Microsoft Defender Antivirus-Netzwerkverbindungen

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Um sicherzustellen, dass Microsoft Defender Antivirus über die Cloud bereitgestellte Schutz ordnungsgemäß funktioniert, muss Ihr Sicherheitsteam Ihr Netzwerk so konfigurieren, dass Verbindungen zwischen Ihren Endpunkten und bestimmten Microsoft-Servern zugelassen werden. Dieser Artikel listet die Verbindungen auf, die zulässig sein müssen, z. B. mithilfe von Firewallregeln, und enthält Anweisungen zum Überprüfen der Verbindung. Wenn Sie Ihren Schutz ordnungsgemäß konfigurieren, können Sie sicherstellen, dass Sie den besten Nutzen aus Ihren über die Cloud bereitgestellten Schutzdiensten erhalten.

Weitere Informationen zur Netzwerkkonnektivität finden Sie im Blogbeitrag ["Wichtige Änderungen am Microsoft Active Protection Services-Endpunkt".](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006)

> [!TIP]
> Besuchen Sie die Demowebsite von Microsoft Defender für Endpunkt unter [demo.wd.microsoft.com,](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) um zu bestätigen, dass die folgenden Features funktionieren:
>
> - Aus der Cloud gelieferter Schutz
> - Schnelles Lernen (einschließlich "Bei erster Anzeige blockieren")
> - Blockieren potenziell unerwünschter Anwendungen

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a>Verbindungen mit dem Microsoft Defender Antivirus Clouddienst zulassen

Der Microsoft Defender Antivirus Clouddienst bietet schnellen, starken Schutz für Ihre Endpunkte. Die Aktivierung des über die Cloud bereitgestellten Schutzdiensts ist optional, wird jedoch dringend empfohlen, da er wichtigen Schutz vor Schadsoftware auf Ihren Endpunkten und in Ihrem Netzwerk bietet. Weitere Informationen zum Aktivieren des Diensts mit Intune, Microsoft Endpoint Configuration Manager, Gruppenrichtlinien, PowerShell-Cmdlets oder auf einzelnen Clients in der Windows-Sicherheit-App finden Sie unter Aktivieren des über die [Cloud bereitgestellten Schutzes.](enable-cloud-protection-microsoft-defender-antivirus.md) 

Nachdem Sie den Dienst aktiviert haben, müssen Sie möglicherweise Ihr Netzwerk oder Ihre Firewall konfigurieren, um Verbindungen zwischen ihm und Ihren Endpunkten zuzulassen. Da Ihr Schutz ein Clouddienst ist, müssen Computer Zugriff auf das Internet haben und Microsoft Defender für Office 365 Machine Learning-Dienste erreichen. Schließen Sie die URL nicht `*.blob.core.windows.net` von jeder Art von Netzwerküberprüfung aus. 

> [!NOTE]
> Der Microsoft Defender Antivirus Clouddienst ist ein Mechanismus für die Bereitstellung eines aktualisierten Schutzes für Ihr Netzwerk und Ihre Endpunkte. Obwohl er als Clouddienst bezeichnet wird, ist er nicht nur Schutz für in der Cloud gespeicherte Dateien, sondern verwendet stattdessen verteilte Ressourcen und maschinelles Lernen, um Ihre Endpunkte in einer Geschwindigkeit zu schützen, die viel schneller als herkömmliche Security Intelligence-Updates ist.

## <a name="services-and-urls"></a>Dienste und URLs

In der Tabelle in diesem Abschnitt sind die Dienste und die zugehörigen Websiteadressen (URLs) aufgeführt. 

Stellen Sie sicher, dass keine Firewall- oder Netzwerkfilterregeln vorhanden sind, die den Zugriff auf diese URLs verweigern. Andernfalls müssen Sie möglicherweise eine Zulassungsregel speziell für sie erstellen (mit Ausnahme der `*.blob.core.windows.net` URL). Die URLs in der folgenden Tabelle verwenden Port 443 für die Kommunikation.

| Dienst und Beschreibung | URL |
|----|---- |
| Microsoft Defender Antivirus über die Cloud bereitgestellten Schutzdienst, auch als Microsoft Active Protection Service (MAPS) bezeichnet<p>Dieser Dienst wird von Microsoft Defender Antivirus verwendet, um über die Cloud bereitgestellten Schutz bereitzustellen.|`*.wdcp.microsoft.com` <p> `*.wdcpalt.microsoft.com` <p> `*.wd.microsoft.com`|
| Microsoft Update Service (MU) und Windows Update Service (WU) <p>Diese Dienste ermöglichen Sicherheitsintelligenz und Produktupdates   |`*.update.microsoft.com` <p> `*.delivery.mp.microsoft.com`<p> `*.windowsupdate.com` <p> Weitere Informationen finden Sie unter [Verbindungsendpunkte für Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)|
|Security Intelligence-Updates – Alternativer Downloadspeicherort (ADL)<p>Dies ist ein alternativer Speicherort für Microsoft Defender Antivirus Security Intelligence-Updates, wenn die installierte Security Intelligence veraltet ist (7 oder mehr Tage zurück)|  `*.download.microsoft.com`  <p> `*.download.windowsupdate.com`<p>  `go.microsoft.com`<p> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| Schadsoftwareübermittlungsspeicher <p>Dies ist der Uploadspeicherort für Dateien, die über das Übermittlungsformular oder die automatische Beispielübermittlung an Microsoft übermittelt wurden. | `ussus1eastprod.blob.core.windows.net` <p>    `ussus2eastprod.blob.core.windows.net` <p>    `ussus3eastprod.blob.core.windows.net` <p>    `ussus4eastprod.blob.core.windows.net` <p>    `wsus1eastprod.blob.core.windows.net` <p>    `wsus2eastprod.blob.core.windows.net` <p>    `ussus1westprod.blob.core.windows.net` <p>    `ussus2westprod.blob.core.windows.net` <p>    `ussus3westprod.blob.core.windows.net` <p>    `ussus4westprod.blob.core.windows.net` <p>    `wsus1westprod.blob.core.windows.net` <p>    `wsus2westprod.blob.core.windows.net` <p>    `usseu1northprod.blob.core.windows.net` <p>    `wseu1northprod.blob.core.windows.net` <p>    `usseu1westprod.blob.core.windows.net` <p>    `wseu1westprod.blob.core.windows.net` <p>    `ussuk1southprod.blob.core.windows.net` <p>    `wsuk1southprod.blob.core.windows.net` <p>    `ussuk1westprod.blob.core.windows.net` <p>    `wsuk1westprod.blob.core.windows.net` |
| Zertifikatsperrliste (Certificate Revocation List, CRL) <p>Diese Liste wird von Windows beim Erstellen der SSL-Verbindung mit MAPS zum Aktualisieren der CRL verwendet.   | `http://www.microsoft.com/pkiops/crl/` <p> `http://www.microsoft.com/pkiops/certs` <p>   `http://crl.microsoft.com/pki/crl/products` <p> `http://www.microsoft.com/pki/certs` |
| Symbol Store <p>Der Symbolspeicher wird von Microsoft Defender Antivirus verwendet, um bestimmte kritische Dateien während des Wartungsflusses wiederherzustellen.   | `https://msdl.microsoft.com/download/symbols` |
| Universeller Telemetrieclient <p>Dieser Client wird von Windows verwendet, um Clientdiagnosedaten zu senden.<p> Microsoft Defender Antivirus verwendet Telemetrie für Die Überwachung der Qualität der Produkte    | Das Update verwendet SSL (TCP-Port 443), um Manifeste herunterzuladen und Diagnosedaten an Microsoft hochzuladen, die die folgenden DNS-Endpunkte verwenden: <p> `vortex-win.data.microsoft.com` <p>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a>Überprüfen von Verbindungen zwischen Ihrem Netzwerk und der Cloud

Nachdem Sie die oben aufgeführten URLs zugelassen haben, können Sie testen, ob Sie mit dem Microsoft Defender Antivirus Clouddienst verbunden sind und ordnungsgemäß Informationen melden und empfangen, um sicherzustellen, dass Sie vollständig geschützt sind.

### <a name="use-the-cmdline-tool-to-validate-cloud-delivered-protection"></a>Verwenden des Cmdline-Tools zum Überprüfen des über die Cloud bereitgestellten Schutzes

Verwenden Sie das folgende Argument mit dem Microsoft Defender Antivirus Befehlszeilenprogramm ( `mpcmdrun.exe` ), um zu überprüfen, ob Ihr Netzwerk mit dem Microsoft Defender Antivirus Clouddienst kommunizieren kann:

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> Sie müssen eine Version der Eingabeaufforderung auf Administratorebene öffnen. Klicken Sie im Startmenü mit der rechten Maustaste auf das Element, klicken Sie **auf "Als Administrator ausführen",** und klicken Sie an der Eingabeaufforderung "Berechtigungen" auf **"Ja".** Dieser Befehl funktioniert nur für Windows 10, Version 1703 oder höher.

Weitere Informationen finden Sie unter [Verwalten Microsoft Defender Antivirus mit dem mpcmdrun.exe-Befehlszeilentool.](command-line-arguments-microsoft-defender-antivirus.md)

### <a name="attempt-to-download-a-fake-malware-file-from-microsoft"></a>Versuch, eine gefälschte Schadsoftwaredatei von Microsoft herunterzuladen

Sie können eine Beispieldatei herunterladen, die Microsoft Defender Antivirus erkennt und blockiert, wenn Sie ordnungsgemäß mit der Cloud verbunden sind.

Laden Sie die Datei unter [https://aka.ms/ioavtest](https://aka.ms/ioavtest) .

> [!NOTE]
> Diese Datei ist keine tatsächliche Schadsoftware. Es handelt sich um eine gefälschte Datei, die entwickelt wurde, um zu testen, ob Sie ordnungsgemäß mit der Cloud verbunden sind.

Wenn Sie ordnungsgemäß verbunden sind, wird eine Warnung Microsoft Defender Antivirus Benachrichtigung angezeigt.

Wenn Sie Microsoft Edge verwenden, wird auch eine Benachrichtigung angezeigt:

![Microsoft Edge den Benutzer darüber informieren, dass Schadsoftware gefunden wurde](images/defender/wdav-bafs-edge.png)

Eine ähnliche Meldung tritt auf, wenn Sie Internet Explorer verwenden:

![Microsoft Defender Antivirus Benachrichtigung, die den Benutzer darüber informiert, dass Schadsoftware gefunden wurde](images/defender/wdav-bafs-ie.png)

Außerdem wird im Abschnitt **"Scanverlauf"** in der Windows-Sicherheit-App eine Erkennung unter **Quarantäne gestellten Bedrohungen** angezeigt:

1. Öffnen Sie die Windows-Sicherheit App, indem Sie auf das Schildsymbol in der Taskleiste klicken oder im Startmenü nach **Sicherheit** suchen.

2. Wählen Sie **"Viren- & Bedrohungsschutz"** und dann **"Schutzverlauf"** aus.

3. Wählen Sie im Abschnitt **"Isolierte Bedrohungen"** den **vollständigen Verlauf** aus, um die erkannte gefälschte Schadsoftware anzuzeigen.

   > [!NOTE]
   > Versionen von Windows 10 vor Version 1703 weisen eine andere Benutzeroberfläche auf. Siehe [Microsoft Defender Antivirus in der Windows-Sicherheit-App.](microsoft-defender-security-center-antivirus.md)

   Im Windows-Ereignisprotokoll wird auch [Windows Defender Clientereignis-ID 1116](troubleshoot-microsoft-defender-antivirus.md)angezeigt.

