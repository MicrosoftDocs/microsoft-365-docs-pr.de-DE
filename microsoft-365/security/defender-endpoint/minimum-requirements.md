---
title: Mindestanforderungen für Microsoft Defender for Endpoint
description: Verstehen der Lizenzierungsanforderungen und -anforderungen für das Onboarding von Geräten in den Dienst
keywords: Mindestanforderungen, Lizenzierung, Vergleichstabelle
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 7581c606a7903bd6d32c1e192f35992899289f30
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51061399"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a>Mindestanforderungen für Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Es gibt einige Mindestanforderungen für das Onboarding von Geräten in den Dienst. Erfahren Sie mehr über die Lizenzierungs-, Hardware- und Softwareanforderungen sowie andere Konfigurationseinstellungen, um Geräte in den Dienst zu integrieren.

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink).

> [!TIP]
> - Erfahren Sie mehr über die neuesten Verbesserungen in Defender for Endpoint: [Defender for Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).
> - Defender for Endpoint hat in der kürzlichen MITRE-Evaluierung branchenführende Optik- und Erkennungsfunktionen gezeigt. Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).

## <a name="licensing-requirements"></a>Lizenzierungsanforderungen
Microsoft Defender for Endpoint erfordert eines der folgenden Microsoft Volumenlizenzangebote:

- Windows 10 Enterprise E5
- Windows 10 Education A5
- Microsoft 365 E5 (M365 E5) einschließlich Windows 10 Enterprise E5
- Microsoft 365 A5 (M365 A5)
- Microsoft 365 E5 Security
- Microsoft 365 A5 Security
- Microsoft Defender für Endpunkt

> [!NOTE]
> Berechtigte lizenzierte Benutzer können Microsoft Defender for Endpoint auf bis zu fünf gleichzeitigen Geräten verwenden.
> Microsoft Defender for Endpoint steht auch bei einem Cloud Solution Provider (CSP) zum Kauf zur Verfügung.

Microsoft Defender for Endpoint für Server erfordert eine der folgenden Lizenzierungsoptionen:

- [Azure Security Center mit aktivierter Azure Defender](https://docs.microsoft.com/azure/security-center/security-center-pricing)
- Microsoft Defender for Endpoint for Server (1 pro abgedeckten Server)

> [!NOTE]
> Kunden können Serverlizenzen (eine pro abgedeckte Serverbetriebssystemumgebung (OSE)) für Microsoft Defender for Endpoint für Server erwerben, wenn sie über mindestens 50 Lizenzen für eine oder mehrere der folgenden Benutzerlizenzen verfügen:
>
> * Microsoft Defender für Endpunkt
> * Windows E5/A5
> * Microsoft 365 E5/A5
> * Microsoft 365 E5/A5 Security

Ausführliche Lizenzierungsinformationen finden Sie auf der [Website "Produktbedingungen",](https://www.microsoft.com/licensing/terms/) und arbeiten Sie mit Ihrem Kontoteam zusammen, um mehr über die Geschäftsbedingungen zu erfahren.

Weitere Informationen zum Array von Features in Windows 10-Editionen finden Sie unter [Compare Windows 10 editions](https://www.microsoft.com/windowsforbusiness/compare).

Eine ausführliche Vergleichstabelle des Vergleichs der kommerziellen Windows 10-Edition finden Sie in der [PDF-Vergleichstabelle](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf).

## <a name="browser-requirements"></a>Browseranforderungen
Der Zugriff auf Defender for Endpoint erfolgt über einen Browser, der die folgenden Browser unterstützt:

- Microsoft Edge
- Internet Explorer, Version 11
- Google Chrome

> [!NOTE]
> Während andere Browser möglicherweise funktionieren, werden die genannten Browser unterstützt.


## <a name="hardware-and-software-requirements"></a>Hardware- und Softwareanforderungen

### <a name="supported-windows-versions"></a>Unterstützte Windows-Versionen
- Windows 7 SP1 Enterprise ([Erfordert ESU für die Unterstützung](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)
- Windows 7 SP1 Pro ([Erfordert ESU für die Unterstützung](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)
- Windows 8.1 Enterprise
- Windows 8.1 Pro
- Windows 10 Enterprise
- [Windows 10 Enterprise LTSC](https://docs.microsoft.com/windows/whats-new/ltsc/)
- Windows 10 Education
- Windows 10 Pro
- Windows 10 Pro Education
- Windows Server
  - Windows Server 2008 R2 SP1
  - Windows Server 2012 R2
  - Windows Server 2016
  - Windows Server, Version 1803 oder höher
  - Windows Server 2019
- Windows Virtual Desktop

Auf Geräten in Ihrem Netzwerk muss eine dieser Editionen ausgeführt werden.

Die Hardwareanforderungen für Defender for Endpoint auf Geräten sind für die unterstützten Editionen identisch.

> [!NOTE]
> Computer mit mobilen Versionen von Windows (z. B. Windows CE und Windows 10 Mobile) werden nicht unterstützt.
>
> Bei virtuellen Computern mit Windows 10 Enterprise 2016 LTSB können Leistungsprobleme auftreten, wenn sie auf Nicht-Microsoft-Virtualisierungsplattformen ausgeführt werden.
>
> Für virtuelle Umgebungen wird die Verwendung von Windows 10 Enterprise LTSC 2019 oder höher empfohlen.


### <a name="other-supported-operating-systems"></a>Andere unterstützte Betriebssysteme
- Android
- Linux
- macOS

> [!NOTE]
> Sie müssen die genauen Linux-Verteilungen und -Versionen von Android und macOS kennen, die mit Defender for Endpoint kompatibel sind, damit die Integration funktioniert.



### <a name="network-and-data-storage-and-configuration-requirements"></a>Anforderungen an Netzwerk- und Datenspeicherung und -konfiguration
Wenn Sie den Onboarding-Assistenten zum ersten Mal ausführen, müssen Sie auswählen, wo Ihre Microsoft Defender for Endpoint-bezogenen Informationen gespeichert sind: in der Europäischen Union, im Vereinigten Königreich oder im Rechenzentrum der Vereinigten Staaten.

> [!NOTE]
> - Der Datenspeicherort kann nach dem ersten Setup nicht mehr geändert werden.
> - Weitere Informationen dazu, wo und wie Microsoft Ihre Daten speichert, finden Sie unter Datenspeicherung und Datenschutz von Microsoft Defender for [Endpoint.](data-storage-privacy.md)


### <a name="diagnostic-data-settings"></a>Diagnosedateneinstellungen

> [!NOTE]
> Microsoft Defender for Endpoint erfordert keine bestimmte Diagnosestufe, solange sie aktiviert ist.

Stellen Sie sicher, dass der Diagnosedatendienst auf allen Geräten in Ihrer Organisation aktiviert ist.
Standardmäßig ist dieser Dienst aktiviert. Es ist eine bewährte Methode, um sicherzustellen, dass Sie Sensordaten von ihnen erhalten.

**Verwenden Sie die Befehlszeile, um den Starttyp des Windows 10-Diagnosedatendiensts zu überprüfen:**

1. Öffnen Sie eine Befehlszeilenaufforderung mit erhöhten Rechten auf dem Gerät:

   1.  Wechseln Sie zu **Start**, und geben Sie **cmd** ein.

   1.  Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.

2. Geben Sie den folgenden Befehl ein, und drücken Sie die **EINGABETASTE**:

   ```console
   sc qc diagtrack
   ```

   Wenn der Dienst aktiviert ist, sollte das Ergebnis wie der folgende Screenshot aussehen:

   ![Ergebnis des sc-Abfragebefehls für diagtrack](images/windefatp-sc-qc-diagtrack.png)


Sie müssen festlegen, dass der Dienst  automatisch gestartet wird, START_TYPE nicht auf **AUTO_START.**


**Verwenden Sie die Befehlszeile, um den Windows 10-Diagnosedatendienst so zu legen, dass er automatisch gestartet wird:**

1.  Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten am Endpunkt:

    1. Wechseln Sie zu **Start**, und geben Sie **cmd** ein.

    1. Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.

2.  Geben Sie den folgenden Befehl ein, und drücken Sie die **EINGABETASTE**:

    ```console
    sc config diagtrack start=auto
    ```

3.  Es wird eine Erfolgsmeldung angezeigt. Überprüfen Sie die Änderung, indem Sie den folgenden Befehl eingeben, und drücken Sie die **EINGABETASTE:**

    ```console
    sc qc diagtrack
    ```


#### <a name="internet-connectivity"></a>Internetverbindung
Die Internetverbindung auf Geräten ist entweder direkt oder über Proxy erforderlich.

Der Defender for Endpoint-Sensor kann eine tägliche durchschnittliche Bandbreite von 5 MB nutzen, um mit dem Defender for Endpoint-Clouddienst zu kommunizieren und Cyberdaten zu melden. One-off-Aktivitäten wie Dateiuploads und Untersuchungspaketsammlungen sind in dieser täglichen durchschnittlichen Bandbreite nicht enthalten.

Weitere Informationen zu zusätzlichen Proxykonfigurationseinstellungen finden Sie unter [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).

Bevor Sie Geräte integrieren, muss der Diagnosedatendienst aktiviert sein. Der Dienst ist in Windows 10 standardmäßig aktiviert.


## <a name="microsoft-defender-antivirus-configuration-requirement"></a>Konfigurationsanforderung für Microsoft Defender Antivirus
Der Defender for Endpoint-Agent hängt von der Fähigkeit von Microsoft Defender Antivirus ab, Dateien zu überprüfen und Informationen darüber zur Verfügung zu stellen.

Konfigurieren Sie Sicherheitsintelligenzupdates auf den Defender for Endpoint-Geräten, unabhängig davon, ob Microsoft Defender Antivirus die aktive Antischalware ist oder nicht. Weitere Informationen finden Sie unter [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus).

Wenn Microsoft Defender Antivirus nicht die aktive Antischalware in Ihrer Organisation ist und Sie den Defender for Endpoint-Dienst verwenden, wechselt Microsoft Defender Antivirus in den passiven Modus.

Wenn Microsoft Defender Antivirus in Ihrer Organisation über Gruppenrichtlinien oder andere Methoden deaktiviert wurde, müssen integrierte Geräte von dieser Gruppenrichtlinie ausgeschlossen werden.

Wenn Sie Server onboardieren und Microsoft Defender Antivirus nicht die aktive Antischalware auf Ihren Servern ist, muss Microsoft Defender Antivirus entweder für den passiven Modus konfiguriert oder deinstalliert werden. Die Konfiguration hängt von der Serverversion ab. Weitere Informationen finden Sie unter [Microsoft Defender Antivirus Compatibility](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md).

> [!NOTE]
> Ihre reguläre Gruppenrichtlinie gilt nicht für Tamper Protection, und Änderungen an Microsoft Defender Antivirus-Einstellungen werden ignoriert, wenn Tamper Protection installiert ist.


## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a>Microsoft Defender Antivirus Early Launch Antimalware (ELAM)-Treiber ist aktiviert
Wenn Sie Microsoft Defender Antivirus als primäres Antischalwareprodukt auf Ihren Geräten ausführen, wird der Defender for Endpoint-Agent erfolgreich onboarding.

Wenn Sie einen Antischasoftwareclient eines Drittanbieters ausführen und Mobile Device Management-Lösungen oder Microsoft Endpoint Manager (aktuelle Zweigstelle) verwenden, müssen Sie sicherstellen, dass der Microsoft Defender Antivirus -ELAM-Treiber aktiviert ist. Weitere Informationen finden Sie unter [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).


## <a name="related-topics"></a>Verwandte Themen
- [Einrichten der Bereitstellung von Microsoft Defender for Endpoint](production-deployment.md)
- [Onboarding von Geräten](onboard-configure.md)
