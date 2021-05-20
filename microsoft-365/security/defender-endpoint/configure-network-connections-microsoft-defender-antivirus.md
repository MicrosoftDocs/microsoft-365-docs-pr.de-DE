---
title: Konfigurieren und Validieren von Microsoft Defender Antivirus-Netzwerkverbindungen
description: Konfigurieren und testen Sie Ihre Verbindung mit dem Microsoft Defender Antivirus Cloudschutzdienst.
keywords: Antivirus, Microsoft Defender Antivirus, Antimalware, Sicherheit, Verteidiger, Cloud, Aggressivität, Schutzstufe
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ef5a9ffdf45a2f8e7f262ae7f969cd19e848b7a5
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572525"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a>Konfigurieren und Validieren von Microsoft Defender Antivirus-Netzwerkverbindungen

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Um sicherzustellen, Microsoft Defender Antivirus Cloud-Schutz ordnungsgemäß funktioniert, müssen Sie Ihr Netzwerk so konfigurieren, dass Verbindungen zwischen Ihren Endpunkten und bestimmten Microsoft-Servern zugelassen werden. Dieser Artikel listet die Verbindungen auf, die zulässig sein müssen, z. B. mithilfe von Firewallregeln, und enthält Anweisungen zum Überprüfen der Verbindung. Wenn Sie Ihren Schutz richtig konfigurieren, können Sie sicherstellen, dass Sie den besten Nutzen aus Ihren in der Cloud bereitgestellten Schutzdiensten erhalten.

Weitere Informationen zur Netzwerkkonnektivität finden Sie im Blogbeitrag [Wichtige Änderungen am Microsoft Active Protection Services-Endpunkt.](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006)

> [!TIP]
> Sie können auch die Microsoft Defender for Endpoint-Demo-Website unter [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) besuchen, um zu bestätigen, dass die folgenden Funktionen funktionieren:
>
> - Aus der Cloud gelieferter Schutz
> - Schnelles Lernen (inklusive Block auf den ersten Blick)
> - Potenziell unerwünschte Anwendungsblockierung

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a>Verbindungen zum Microsoft Defender Antivirus Clouddienst zulassen

Der Microsoft Defender Antivirus Cloud-Dienst bietet schnellen und starken Schutz für Ihre Endpunkte. Das Aktivieren des in der Cloud bereitgestellten Schutzdienstes ist optional, wird jedoch dringend empfohlen, da er einen wichtigen Schutz vor Malware auf Ihren Endpunkten und im gesamten Netzwerk bietet.

> [!NOTE]
> Der Microsoft Defender Antivirus Clouddienst ist ein Mechanismus, mit dem Sie aktualisierten Schutz für Ihr Netzwerk und Ihre Endpunkte bereitstellen können. Obwohl es als Cloud-Dienst bezeichnet wird, ist es nicht einfach Schutz für Dateien, die in der Cloud gespeichert sind, sondern es verwendet verteilte Ressourcen und maschinelles Lernen, um Ihre Endpunkte mit einer Rate zu schützen, die viel schneller ist als herkömmliche Sicherheitsintelligenzupdates.

Weitere Informationen zum Aktivieren des Dienstes mit Intune, Microsoft Endpoint Configuration Manager, Gruppenrichtlinien, PowerShell-Cmdlets oder auf einzelnen Clients in der Windows-Sicherheit-App finden Sie unter Aktivieren des [von der Cloud bereitgestellten Schutzes.](enable-cloud-protection-microsoft-defender-antivirus.md) 

Nachdem Sie den Dienst aktiviert haben, müssen Sie möglicherweise Ihr Netzwerk oder Ihre Firewall so konfigurieren, dass Verbindungen zwischen dem Dienst und Ihren Endpunkten zugelassen werden.

Da es sich bei Ihrem Schutz um einen Clouddienst handelt, müssen Computer Zugriff auf das Internet haben und den Microsoft Defender für Office 365 Machine Learning-Dienste erreichen. Schließen Sie die URL nicht `*.blob.core.windows.net` von jeder Art von Netzwerkinspektion aus. 

In der folgenden Tabelle sind die Dienste und die zugehörigen URLs aufgeführt. Stellen Sie sicher, dass keine Firewall- oder Netzwerkfilterregeln vorhanden sind, die den Zugriff auf diese URLs verweigern, oder Sie müssen möglicherweise eine Zulassungsregel speziell für sie erstellen (mit Ausnahme der URL `*.blob.core.windows.net` ). Unten erwähnen URLs verwenden Port 443 für die Kommunikation.


| **Dienst**| **Beschreibung** |**URL** |
| :--: | :-- | :-- |
| Microsoft Defender Antivirus Von der Cloud bereitgestellten Schutzdienst, auch als Microsoft Active Protection Service (MAPS) bezeichnet|Wird von Microsoft Defender Antivirus verwendet, um Cloud-bereitstellungsbasierten Schutz zu bieten|`*.wdcp.microsoft.com` <br/> `*.wdcpalt.microsoft.com` <br/> `*.wd.microsoft.com`|
| Microsoft Update Service (MU) <br/> Windows Update-Service (WU)|  Sicherheitsintelligenz und Produktaktualisierungen   |`*.update.microsoft.com` <br/> `*.delivery.mp.microsoft.com`<br/> `*.windowsupdate.com` <br/><br/> Weitere Informationen finden Sie unter [Verbindungsendpunkte für Windows Update](/windows/privacy/manage-windows-1709-endpoints#windows-update)|
|Security Intelligence aktualisiert Alternate Download Location (ADL)|   Alternativer Speicherort für Microsoft Defender Antivirus Security Intelligence-Updates, wenn die installierte Sicherheitsintelligenz veraltet ist (7 oder mehr Tage zurück)|    `*.download.microsoft.com`  </br> `*.download.windowsupdate.com`</br>  `go.microsoft.com`</br> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| Malware-Übermittlungsspeicher|Hochladen Speicherort für Dateien, die über das Übermittlungsformular oder die automatische Beispielübermittlung an Microsoft übermittelt wurden    | `ussus1eastprod.blob.core.windows.net` <br/>    `ussus2eastprod.blob.core.windows.net` <br/>    `ussus3eastprod.blob.core.windows.net` <br/>    `ussus4eastprod.blob.core.windows.net` <br/>    `wsus1eastprod.blob.core.windows.net` <br/>    `wsus2eastprod.blob.core.windows.net` <br/>    `ussus1westprod.blob.core.windows.net` <br/>    `ussus2westprod.blob.core.windows.net` <br/>    `ussus3westprod.blob.core.windows.net` <br/>    `ussus4westprod.blob.core.windows.net` <br/>    `wsus1westprod.blob.core.windows.net` <br/>    `wsus2westprod.blob.core.windows.net` <br/>    `usseu1northprod.blob.core.windows.net` <br/>    `wseu1northprod.blob.core.windows.net` <br/>    `usseu1westprod.blob.core.windows.net` <br/>    `wseu1westprod.blob.core.windows.net` <br/>    `ussuk1southprod.blob.core.windows.net` <br/>    `wsuk1southprod.blob.core.windows.net` <br/>    `ussuk1westprod.blob.core.windows.net` <br/>    `wsuk1westprod.blob.core.windows.net` |
| Zertifikatsperrliste (CRL)|Wird von Windows beim Erstellen der SSL-Verbindung zu MAPS zum Aktualisieren der Zertifikatsperrliste verwendet   | `http://www.microsoft.com/pkiops/crl/` <br/> `http://www.microsoft.com/pkiops/certs` <br/>   `http://crl.microsoft.com/pki/crl/products` <br/> `http://www.microsoft.com/pki/certs` |
| Symbol Store|Wird von Microsoft Defender Antivirus verwendet, um bestimmte kritische Dateien während der Behebungsflüsse wiederherzustellen  | `https://msdl.microsoft.com/download/symbols` |
| Universeller Telemetrieclient| Wird von Windows verwendet, um Clientdiagnosedaten zu senden; Microsoft Defender Antivirus verwendet Telemetrie zu Zwecken der Produktqualitätsüberwachung   | Das Update verwendet SSL (TCP Port 443), um Manifeste herunterzuladen und Diagnosedaten an Microsoft hochzuladen, das die folgenden DNS-Endpunkte verwendet:   `vortex-win.data.microsoft.com` <br/>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a>Überprüfen von Verbindungen zwischen Ihrem Netzwerk und der Cloud

Nachdem Sie die oben aufgeführten URLs zugelassen haben, können Sie testen, ob Sie mit dem Microsoft Defender Antivirus Cloud-Dienst verbunden sind und Informationen korrekt melden und empfangen, um sicherzustellen, dass Sie vollständig geschützt sind.

**Verwenden Sie das cmdline-Tool, um den von der Cloud bereitgestellten Schutz zu überprüfen:**

Verwenden Sie das folgende Argument mit dem Befehlszeilendienstprogramm Microsoft Defender Antivirus ( `mpcmdrun.exe` ), um zu überprüfen, ob Ihr Netzwerk mit dem Microsoft Defender Antivirus Clouddienst kommunizieren kann:

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> Sie müssen eine Version der Eingabeaufforderung auf Administratorebene öffnen. Klicken Sie im Startmenü mit der rechten Maustaste auf das Element, klicken Sie **auf Als Administrator ausführen** und klicken Sie auf **Ja** in der Eingabeaufforderung berechtigungen. Dieser Befehl funktioniert nur auf Windows 10, Version 1703 oder höher.

Weitere Informationen finden Sie unter [Verwalten Microsoft Defender Antivirus mit dem Befehlszeilentool mpcmdrun.exe](command-line-arguments-microsoft-defender-antivirus.md).

**Versuchen Sie, eine gefälschte Malware-Datei von Microsoft herunterzuladen:**

Sie können eine Beispieldatei herunterladen, die Microsoft Defender Antivirus erkennt und blockiert, wenn Sie ordnungsgemäß mit der Cloud verbunden sind.

Laden Sie die Datei herunter, indem Sie [https://aka.ms/ioavtest](https://aka.ms/ioavtest) .

> [!NOTE]
> Diese Datei ist kein tatsächliches Stück Malware. Es ist eine gefälschte Datei, die entwickelt wurde, um zu testen, ob Sie richtig mit der Cloud verbunden sind.

Wenn Sie ordnungsgemäß verbunden sind, wird eine Warnung Microsoft Defender Antivirus Benachrichtigung angezeigt.

Wenn Sie Microsoft Edge verwenden, wird außerdem eine Benachrichtigung angezeigt:

![Microsoft Edge, den Benutzer darüber zu informieren, dass Malware gefunden wurde](images/defender/wdav-bafs-edge.png)

Eine ähnliche Meldung tritt auf, wenn Sie Internet Explorer verwenden:

![Microsoft Defender Antivirus Benachrichtigung, die den Benutzer darüber informiert, dass Malware gefunden wurde](images/defender/wdav-bafs-ie.png)

Außerdem wird im Abschnitt **"Scanverlauf"** in der Windows-Sicherheit-App eine Erkennung unter **isolierte Bedrohungen** angezeigt:

1. Öffnen Sie die Windows-Sicherheit App, indem Sie auf das Schildsymbol in der Taskleiste klicken oder im Startmenü nach **Sicherheit** suchen.

2. Wählen Sie **Virus & Bedrohungsschutz** aus, und wählen Sie dann **Schutzverlauf** aus.

3. Wählen Sie im Abschnitt **Quarantänebedrohungen** die Option **Vollständige Historie anzeigen** aus, um die erkannte gefälschte Malware anzuzeigen.

   > [!NOTE]
   > Versionen von Windows 10 vor Version 1703 haben eine andere Benutzeroberfläche. Siehe [Microsoft Defender Antivirus in der Windows-Sicherheit-App](microsoft-defender-security-center-antivirus.md).

   Im Windows-Ereignisprotokoll wird auch [Windows Defender Clientereignis-ID 1116](troubleshoot-microsoft-defender-antivirus.md)angezeigt.

## <a name="related-articles"></a>Verwandte Artikel

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)

- [Aus der Cloud bereitgestellten Schutz aktivieren](enable-cloud-protection-microsoft-defender-antivirus.md)

- [Befehlszeilenargumente](command-line-arguments-microsoft-defender-antivirus.md)

- [Wichtige Änderungen am Microsoft Active Protection Services-Endpunkt](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006)
