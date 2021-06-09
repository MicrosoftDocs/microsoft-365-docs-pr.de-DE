---
title: Mindestanforderungen für Microsoft Defender für Endpunkt
description: Grundlegendes zu den Lizenzierungsanforderungen und Anforderungen für das Onboarding von Geräten in den Dienst
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
ms.openlocfilehash: ccff6abcfcd1a2da32a8e1614a2de45afed69aef
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842998"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a>Mindestanforderungen für Microsoft Defender für Endpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink)


Es gibt einige Mindestanforderungen für das Onboarding von Geräten in den Dienst. Erfahren Sie mehr über die Lizenzierungs-, Hardware- und Softwareanforderungen und andere Konfigurationseinstellungen zum Onboarding von Geräten in den Dienst.

> [!TIP]
> - Erfahren Sie mehr über die neuesten Verbesserungen in Defender für Endpunkt: [Defender für Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).
> - Defender für Endpunkt hat in der letzten MITRE-Evaluierung branchenführende Optik- und Erkennungsfunktionen demonstriert. Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).

## <a name="licensing-requirements"></a>Lizenzierungsanforderungen

Microsoft Defender für Endpunkt erfordert eines der folgenden Microsoft-Volumenlizenzierungsangebote:

- Windows 10 Enterprise E5
- Windows 10 Education A5
- Microsoft 365 E5 (M365 E5), das Windows 10 Enterprise E5 enthält
- Microsoft 365 A5 (M365 A5)
- Microsoft 365 E5 Security
- Microsoft 365 A5 Security
- Microsoft Defender für Endpunkt

> [!NOTE]
> Berechtigte lizenzierte Benutzer können Microsoft Defender für Endpunkt auf bis zu fünf gleichzeitigen Geräten verwenden.
> Microsoft Defender für Endpunkt steht auch zum Kauf über einen Cloud Solution Provider (CSP) zur Verfügung.
> RDSH-VMs erfordern keine separate Defender für Endpunkt-Lizenz.

Microsoft Defender für Endpunkt für Server erfordert eine der folgenden Lizenzierungsoptionen:

- [Azure Security Center mit aktiviertem Azure Defender](/azure/security-center/security-center-pricing)
- Microsoft Defender für Endpunkt für Server (eine pro abgedeckten Server)

> [!NOTE]
> Kunden können Serverlizenzen (eine pro abgedeckter Serverbetriebssystemumgebung (OSE)) für Microsoft Defender für Endpunkt für Server erwerben, wenn sie insgesamt mindestens 50 Lizenzen für eine oder mehrere der folgenden Benutzerlizenzen besitzen:
>
> * Microsoft Defender für Endpunkt
> * Windows E5/A5
> * Microsoft 365 E5/A5
> * Microsoft 365 E5/A5 Security

Ausführliche Informationen zur Lizenzierung finden Sie auf der [Website der Produktbedingungen](https://www.microsoft.com/licensing/terms/) und in Zusammenarbeit mit Ihrem Kontoteam, um mehr über die Geschäftsbedingungen zu erfahren.

Weitere Informationen zum Array von Features in Windows 10 Editionen finden Sie unter [Vergleichen Windows 10 Editionen.](https://www.microsoft.com/windowsforbusiness/compare)

Eine detaillierte Vergleichstabelle Windows 10 Vergleichs der kommerziellen Edition finden Sie in der [PDF-Vergleichstabelle.](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf)

## <a name="browser-requirements"></a>Browseranforderungen

Der Zugriff auf Defender für Endpunkt erfolgt über einen Browser, der die folgenden Browser unterstützt:

- Microsoft Edge
- Google Chrome

> [!NOTE]
> Während andere Browser möglicherweise funktionieren, werden die erwähnten Browser unterstützt.


## <a name="hardware-and-software-requirements"></a>Hardware- und Softwareanforderungen

### <a name="supported-windows-versions"></a>Unterstützte Windows Versionen

- Windows 7 SP1-Enterprise ([Erfordert ESU für Support.)](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)
- Windows 7 SP1-Pro ([Erfordert ESU für Support.)](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)
- Windows 8.1 Enterprise
- Windows 8.1 Pro
- Windows 10 Enterprise
- [Windows 10 Enterprise LTSC 2016 (oder höher)](/windows/whats-new/ltsc/)
- Windows 10 Education
- Windows 10 Pro
- Windows 10 Pro Education
- Windows-Server
  - Windows Server 2008 R2 SP1
  - Windows Server 2012 R2
  - Windows Server 2016
  - Windows Server, Version 1803 oder höher
  - Windows Server 2019
- Windows Virtual Desktop

Auf Geräten in Ihrem Netzwerk muss eine dieser Editionen ausgeführt werden.

Die Hardwareanforderungen für Defender für Endpunkt auf Geräten sind für die unterstützten Editionen identisch.

> [!NOTE]
> Computer mit mobilen Versionen von Windows (z. B. Windows CE und Windows 10 Mobile) werden nicht unterstützt.
>
> Bei virtuellen Computern, die Windows 10 Enterprise 2016 LTSB ausgeführt werden, können Leistungsprobleme auftreten, wenn sie auf Nicht-Microsoft-Virtualisierungsplattformen ausgeführt werden.
>
> Für virtuelle Umgebungen empfehlen wir die Verwendung Windows 10 Enterprise LTSC 2019 oder höher.


### <a name="other-supported-operating-systems"></a>Andere unterstützte Betriebssysteme

- [Android](microsoft-defender-endpoint-android.md)
- [iOS](microsoft-defender-endpoint-ios.md)
- [Linux](microsoft-defender-endpoint-linux.md)
- [macOS](microsoft-defender-endpoint-mac.md)

> [!NOTE]
> Sie müssen bestätigen, dass die Linux-Distributionen und -Versionen von Android, iOS und macOS mit Defender für Endpunkt kompatibel sind, damit die Integration funktioniert.



### <a name="network-and-data-storage-and-configuration-requirements"></a>Netzwerk- und Datenspeicherungs- und Konfigurationsanforderungen

Wenn Sie den Onboarding-Assistenten zum ersten Mal ausführen, müssen Sie auswählen, wo Ihre Microsoft Defender für Endpunkt-bezogenen Informationen gespeichert werden: in der Europäischen Union, im Vereinigten Königreich oder im Rechenzentrum der Vereinigten Staaten.

> [!NOTE]
> - Sie können ihren Datenspeicherort nach der erstmaligen Einrichtung nicht mehr ändern.
> - Weitere Informationen dazu, wo und wie Microsoft Ihre Daten speichert, finden Sie im [Microsoft Defender für Endpunkt-Datenspeicherungs- und -datenschutz.](data-storage-privacy.md)


### <a name="diagnostic-data-settings"></a>Diagnosedateneinstellungen

> [!NOTE]
> Microsoft Defender für Endpunkt erfordert keine bestimmte Diagnosestufe, solange es aktiviert ist.

Stellen Sie sicher, dass der Diagnosedatendienst auf allen Geräten in Ihrer Organisation aktiviert ist.
Standardmäßig ist dieser Dienst aktiviert. Es empfiehlt sich, zu überprüfen, ob Sie Sensordaten von diesen abrufen.

**Verwenden Sie die Befehlszeile, um den Starttyp Windows 10 Diagnosedatendiensts zu überprüfen:**

1. Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten auf dem Gerät:

   1.  Wechseln Sie zu **Start**, und geben Sie **cmd** ein.

   1.  Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.

2. Geben Sie den folgenden Befehl ein, und drücken Sie die **EINGABETASTE:**

   ```console
   sc qc diagtrack
   ```

   Wenn der Dienst aktiviert ist, sollte das Ergebnis wie im folgenden Screenshot aussehen:

   ![Ergebnis des Sc-Abfragebefehls für diagtrack](images/windefatp-sc-qc-diagtrack.png)


Sie müssen festlegen, dass der Dienst automatisch gestartet wird, wenn der **START_TYPE** nicht auf **AUTO_START** festgelegt ist.


**Verwenden Sie die Befehlszeile, um den Windows 10 Diagnosedatendienst so festzulegen, dass er automatisch gestartet wird:**

1.  Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten auf dem Endpunkt:

    1. Wechseln Sie zu **Start**, und geben Sie **cmd** ein.

    1. Klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und wählen Sie **Als Administrator ausführen** aus.

2.  Geben Sie den folgenden Befehl ein, und drücken Sie die **EINGABETASTE:**

    ```console
    sc config diagtrack start=auto
    ```

3.  Eine Erfolgsmeldung wird angezeigt. Überprüfen Sie die Änderung, indem Sie den folgenden Befehl eingeben, und drücken Sie die **EINGABETASTE:**

    ```console
    sc qc diagtrack
    ```


#### <a name="internet-connectivity"></a>Internetverbindung

Internetkonnektivität auf Geräten ist entweder direkt oder über Proxy erforderlich.

Der Defender für Endpunkt-Sensor kann eine tägliche durchschnittliche Bandbreite von 5 MB verwenden, um mit dem Defender für Endpunkt-Clouddienst zu kommunizieren und Cyberdaten zu melden. Einmalige Aktivitäten wie Dateiuploads und Untersuchungspaketsammlungen sind in dieser durchschnittlichen Täglichen Bandbreite nicht enthalten.

Weitere Informationen zu zusätzlichen Proxykonfigurationseinstellungen finden Sie unter [Konfigurieren von Geräteproxy- und Internetkonnektivitätseinstellungen.](configure-proxy-internet.md)

Bevor Sie Geräte integrieren, muss der Diagnosedatendienst aktiviert sein. Der Dienst ist in Windows 10 standardmäßig aktiviert.


## <a name="microsoft-defender-antivirus-configuration-requirement"></a>Microsoft Defender Antivirus Konfigurationsanforderung

Der Defender für Endpunkt-Agent hängt von der Fähigkeit von Microsoft Defender Antivirus ab, Dateien zu scannen und Informationen darüber bereitzustellen.

Konfigurieren Von Security Intelligence-Updates auf den Defender für Endpunkt-Geräten, unabhängig davon, ob Microsoft Defender Antivirus die aktive Antischadsoftware ist oder nicht. Weitere Informationen finden Sie unter [Verwalten Microsoft Defender Antivirus Updates und Anwenden von Basisplänen.](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)

Wenn Microsoft Defender Antivirus nicht die aktive Antischadsoftware in Ihrer Organisation ist und Sie den Defender für Endpunkt-Dienst verwenden, wechselt Microsoft Defender Antivirus in den passiven Modus.

Wenn Ihre Organisation Microsoft Defender Antivirus über Gruppenrichtlinien oder andere Methoden deaktiviert hat, müssen die integrierten Geräte von dieser Gruppenrichtlinie ausgeschlossen werden.

Wenn Sie Server integrieren und Microsoft Defender Antivirus nicht die aktive Antischadsoftware auf Ihren Servern ist, müssen Microsoft Defender Antivirus entweder für den passiven Modus konfiguriert oder deinstalliert werden. Die Konfiguration hängt von der Serverversion ab. Weitere Informationen finden Sie unter [Microsoft Defender Antivirus Kompatibilität.](/security/defender-endpoint/microsoft-defender-antivirus-compatibility)

> [!NOTE]
> Ihre reguläre Gruppenrichtlinie gilt nicht für Manipulationsschutz, und Änderungen an Microsoft Defender Antivirus Einstellungen werden ignoriert, wenn der Manipulationsschutz aktiviert ist.


## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a>Microsoft Defender Antivirus ELAM-Treiber (Early Launch Antimalware) ist aktiviert

Wenn Sie Microsoft Defender Antivirus als primäres Antischadsoftwareprodukt auf Ihren Geräten ausführen, wird der Defender für Endpunkt-Agent erfolgreich integriert.

Wenn Sie einen Antischadsoftwareclient eines Drittanbieters ausführen und Lösungen für die mobile Geräteverwaltung oder Microsoft Endpoint Manager (current branch) verwenden, müssen Sie sicherstellen, dass der Microsoft Defender Antivirus ELAM-Treiber aktiviert ist. Weitere Informationen finden Sie unter [Sicherstellen, dass Microsoft Defender Antivirus nicht durch eine Richtlinie deaktiviert ist.](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)


## <a name="related-topics"></a>Verwandte Themen

- [Einrichten der Bereitstellung von Microsoft Defender für Endpunkt](production-deployment.md)
- [Onboarding von Geräten](onboard-configure.md)
