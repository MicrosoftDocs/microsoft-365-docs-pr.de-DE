---
title: Onboarding von Windows 10-Geräten mithilfe von Configuration Manager
description: Verwenden Sie Configuration Manager, um das Konfigurationspaket auf Geräten bereitzustellen, sodass Geräte in den Dienst integriert werden.
keywords: Onboarding von Geräten mit sccm, Geräteverwaltung, Konfigurieren von Microsoft Defender für Endpunktgeräte
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
ms.date: 02/07/2020
ms.technology: mde
ms.openlocfilehash: d7c319e37fb804ee4dac3b6bff402942bbc2fa79
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339658"
---
# <a name="onboard-the-windows-10-devices-using-configuration-manager"></a>Onboarding der Windows 10-Geräte mithilfe von Configuration Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Endpoint Configuration Manager aktuelle Verzweigung
- System Center 2012 R2 Configuration Manager

>Möchten Sie Defender für Endpunkt erfahren? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointssccm-abovefoldlink)

## <a name="supported-client-operating-systems"></a>Unterstützte Clientbetriebssysteme

Basierend auf der Version von Configuration Manager, die Sie ausführen, können die folgenden Clientbetriebssysteme integriert werden:

#### <a name="configuration-manager-version-1910-and-prior"></a>Configuration Manager, Version 1910 und früher

- Clients, auf denen Windows 10 ausgeführt wird 

#### <a name="configuration-manager-version-2002-and-later"></a>Configuration Manager, Version 2002 und höher

Ab Configuration Manager, Version 2002, können Sie die folgenden Betriebssysteme integrieren:

- Windows 8.1
- Windows 10
- Windows Server 2012 R2
- Windows Server 2016
- Windows Server 2016, Version 1803 oder höher
- Windows Server 2019

>[!NOTE]
>Weitere Informationen zum Onboarding von Windows Server 2012 R2, Windows Server 2016 und Windows Server 2019 finden Sie unter [Onboarding Windows Server.](configure-server-endpoints.md)



### <a name="onboard-devices-using-system-center-configuration-manager"></a>Onboarding von Geräten mit System Center Configuration Manager


[![Abbildung der PDF-Datei mit den verschiedenen Bereitstellungspfaden](images/onboard-config-mgr.png)](images/onboard-config-mgr.png#lightbox)


Sehen Sie sich die [PDF-](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) oder [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) an, um die verschiedenen Pfade bei der Bereitstellung von Microsoft Defender für Endpunkt anzuzeigen. 



1. Öffnen Sie das Configuration Manager-Konfigurationspaket .zip Datei (*WindowsDefenderATPOnboardingPackage.zip*), die Sie aus dem Dienst-Onboarding-Assistenten heruntergeladen haben. Sie können das Paket auch aus [Microsoft 365 Defender Portal](https://security.microsoft.com/)abrufen:

    1. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Endpoints**  >  **Device Management**  >  **Onboarding** aus.
    
    1. Wählen Sie Windows 10 als Betriebssystem aus.

    1. Wählen Sie im Feld **"Bereitstellungsmethode"** **System Center Configuration Manager 2012/2012 R2/1511/1602** aus.
    
    1. Wählen Sie **"Paket herunterladen"** aus, und speichern Sie die .zip Datei.

2. Extrahieren Sie den Inhalt der .zip-Datei an einen freigegebenen, schreibgeschützten Speicherort, auf den die Netzwerkadministratoren zugreifen können, die das Paket bereitstellen. Sie sollten über eine Datei mit dem Namen *WindowsDefenderATPOnboardingScript.cmd verfügen.*

3. Stellen Sie das Paket bereit, indem Sie die Schritte im Artikel ["Pakete und Programme" in System Center 2012 R2 Configuration Manager ausführen.](/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))

    a. Wählen Sie eine vordefinierte Gerätesammlung aus, in der das Paket bereitgestellt werden soll.

> [!NOTE]
> Defender für Endpunkt unterstützt das Onboarding während der [Out-Of-Box Experience (OOBE)-Phase](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) nicht. Stellen Sie sicher, dass Benutzer die Windows-Willkommensseite abschließen, nachdem sie Windows Installation oder ein Upgrade ausgeführt haben.

>[!TIP]
> Nach dem Onboarding des Geräts können Sie einen Erkennungstest ausführen, um zu überprüfen, ob ein Gerät ordnungsgemäß in den Dienst integriert ist. Weitere Informationen finden Sie unter [Ausführen eines Erkennungstests auf einem neu integrierten Defender für Endpunkt-Gerät.](run-detection-test.md)
>
> Beachten Sie, dass es möglich ist, eine Erkennungsregel für eine Configuration Manager-Anwendung zu erstellen, um kontinuierlich zu überprüfen, ob ein Gerät integriert wurde. Eine Anwendung ist ein anderer Objekttyp als ein Paket und ein Programm.
> Wenn ein Gerät noch nicht integriert ist (aufgrund eines ausstehenden OoBE-Abschlusses oder aus einem anderen Grund), versucht Configuration Manager erneut, das Gerät zu integrieren, bis die Regel die Statusänderung erkennt.
> 
> Dieses Verhalten kann erreicht werden, indem eine Erkennungsregel erstellt wird, die überprüft, ob der Registrierungswert "OnboardingState" (vom Typ REG_DWORD) = 1 ist.
> Dieser Registrierungswert befindet sich unter "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".
Weitere Informationen finden Sie unter [Konfigurieren von Erkennungsmethoden in System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)

### <a name="configure-sample-collection-settings"></a>Konfigurieren von Beispielsammlungseinstellungen

Für jedes Gerät können Sie einen Konfigurationswert festlegen, um anzugeben, ob Beispiele vom Gerät erfasst werden können, wenn eine Anforderung über Microsoft 365 Defender zum Übermitteln einer Datei für eine umfassende Analyse gestellt wird.

>[!NOTE]
>Diese Konfigurationseinstellungen werden in der Regel über Configuration Manager durchgeführt.

Sie können eine Complianceregel für ein Konfigurationselement in Configuration Manager festlegen, um die Beispielfreigabeeinstellung auf einem Gerät zu ändern.

Diese Regel sollte *ein* Konfigurationselement zur Behebung der Complianceregel sein, das den Wert eines Registrierungsschlüssels auf Zielgeräten festlegt, um sicherzustellen, dass diese beschwerden.

Die Konfiguration wird über den folgenden Registrierungsschlüsseleintrag festgelegt:

```console
Path: "HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection"
Name: "AllowSampleCollection"
Value: 0 or 1
```

Dabei gilt Folgendes:<br>
Der Schlüsseltyp ist D-WORD. <br>
Die folgenden Werte sind möglich:
- 0 – lässt keine Beispielfreigabe von diesem Gerät zu
- 1 – ermöglicht die Freigabe aller Dateitypen von diesem Gerät

Der Standardwert für den Fall, dass der Registrierungsschlüssel nicht vorhanden ist, ist 1.

Weitere Informationen zu System Center Configuration Manager Compliance finden Sie unter [Einführung in Complianceeinstellungen in System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))


## <a name="other-recommended-configuration-settings"></a>Andere empfohlene Konfigurationseinstellungen
Nach dem Onboarding von Geräten in den Dienst ist es wichtig, die enthaltenen Bedrohungsschutzfunktionen zu nutzen, indem Sie diese mit den folgenden empfohlenen Konfigurationseinstellungen aktivieren.

### <a name="device-collection-configuration"></a>Gerätesammlungskonfiguration
Wenn Sie Endpoint Configuration Manager, Version 2002 oder höher, verwenden, können Sie die Bereitstellung erweitern, um Server oder Untergeordnete Clients einzuschließen.


### <a name="next-generation-protection-configuration"></a>Schutzkonfiguration der nächsten Generation
Die folgenden Konfigurationseinstellungen werden empfohlen:

**Überprüfung** <br>
- Scannen von Wechselmedien wie USB-Laufwerken: Ja

**Echtzeitschutz** <br>
- Aktivieren der Verhaltensüberwachung: Ja
- Aktivieren des Schutzes vor potenziell unerwünschten Anwendungen beim Download und vor der Installation: Ja

**Cloud Protection Service**
- Cloud Protection Service-Mitgliedschaftstyp: Erweiterte Mitgliedschaft

**Verringerung der Angriffsfläche** Konfigurieren Sie alle verfügbaren Regeln für die Überwachung.

>[!NOTE]
> Das Blockieren dieser Aktivitäten kann legitime Geschäftsprozesse unterbrechen. Der beste Ansatz besteht darin, alles zu überwachen, zu identifizieren, welche sicher aktiviert werden können, und dann die Einstellungen auf Endpunkten zu aktivieren, die keine falsch positiven Erkennungen aufweisen.


**Netzwerkschutz** <br>
Stellen Sie vor dem Aktivieren des Netzwerkschutzes im Überwachungs- oder Blockierungsmodus sicher, dass Sie das Antischadsoftware-Plattformupdate installiert haben, das über die [Supportseite](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)abgerufen werden kann.


**Kontrollierter Ordnerzugriff**<br>
Aktivieren Sie das Feature mindestens 30 Tage lang im Überwachungsmodus. Überprüfen Sie nach ablaufen diesem Zeitraum die Erkennungen, und erstellen Sie eine Liste der Anwendungen, die in geschützte Verzeichnisse schreiben dürfen.

Weitere Informationen finden Sie unter [Auswerten des kontrollierten Ordnerzugriffs.](evaluate-controlled-folder-access.md)


## <a name="offboard-devices-using-configuration-manager"></a>Offboarding von Geräten mit Configuration Manager

Aus Sicherheitsgründen läuft das Paket, das für Offboard-Geräte verwendet wird, 30 Tage nach dem Datum ab, an dem es heruntergeladen wurde. Abgelaufene Offboardingpakete, die an ein Gerät gesendet werden, werden abgelehnt. Beim Herunterladen eines Offboardingpakets werden Sie über das Ablaufdatum der Pakete benachrichtigt, und es wird auch in den Paketnamen aufgenommen.

> [!NOTE]
> Onboarding- und Offboarding-Richtlinien dürfen nicht gleichzeitig auf demselben Gerät bereitgestellt werden, andernfalls führt dies zu unvorhersehbaren Kollisionen.

### <a name="offboard-devices-using-microsoft-endpoint-manager-current-branch"></a>Offboarding von Geräten mit Microsoft Endpoint Manager current branch

Wenn Sie Microsoft Endpoint Manager aktuelle Verzweigung verwenden, lesen [Sie Erstellen einer Offboarding-Konfigurationsdatei .](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a>Offboarding von Geräten mit System Center 2012 R2 Configuration Manager

1. Rufen Sie das Offboarding-Paket aus [Microsoft 365 Defender Portal](https://security.microsoft.com/)ab:

    1. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Endpoints**  >  **Device Management**  >   **Offboarding** aus.

    1. Wählen Sie Windows 10 als Betriebssystem aus.

    1. Wählen Sie im Feld **"Bereitstellungsmethode"** **System Center Configuration Manager 2012/2012 R2/1511/1602** aus.
    
    1. Wählen Sie **"Paket herunterladen"** aus, und speichern Sie die .zip Datei.

2. Extrahieren Sie den Inhalt der .zip-Datei an einen freigegebenen, schreibgeschützten Speicherort, auf den die Netzwerkadministratoren zugreifen können, die das Paket bereitstellen. Sie sollten über eine Datei mit dem Namen *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd verfügen.*

3. Stellen Sie das Paket bereit, indem Sie die Schritte im Artikel ["Pakete und Programme" in System Center 2012 R2 Configuration Manager ausführen.](/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\))

    a. Wählen Sie eine vordefinierte Gerätesammlung aus, in der das Paket bereitgestellt werden soll.

> [!IMPORTANT]
> Das Offboarding bewirkt, dass das Gerät das Senden von Sensordaten an das Portal beendet, aber Daten vom Gerät, einschließlich Verweise auf warnungen, die es gesendet hat, werden bis zu 6 Monate lang aufbewahrt.


## <a name="monitor-device-configuration"></a>Überwachen der Gerätekonfiguration

Wenn Sie Microsoft Endpoint Manager aktuelle Verzweigung verwenden, verwenden Sie das integrierte Defender für Endpunkt-Dashboard in der Configuration Manager-Konsole. Weitere Informationen finden Sie unter [Defender für Endpunkt – Überwachen.](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)

Wenn Sie System Center 2012 R2 Configuration Manager verwenden, besteht die Überwachung aus zwei Teilen:

1. Bestätigen, dass das Konfigurationspaket ordnungsgemäß bereitgestellt wurde und auf den Geräten in Ihrem Netzwerk ausgeführt wird (oder erfolgreich ausgeführt wurde).

2. Überprüfen, ob die Geräte mit dem Defender für Endpunkt-Dienst kompatibel sind (dadurch wird sichergestellt, dass das Gerät den Integrationsprozess abschließen und weiterhin Daten an den Dienst melden kann).

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a>Sicherstellen, dass das Konfigurationspaket ordnungsgemäß bereitgestellt wurde

1. Klicken Sie in der Configuration Manager-Konsole unten im Navigationsbereich auf **"Überwachung".**

2. Wählen Sie **"Übersicht"** und dann **"Bereitstellungen" aus.**

3. Wählen Sie die Bereitstellung mit dem Paketnamen aus.

4. Überprüfen Sie die Statusindikatoren unter **Abschlussstatistik** und **Inhaltsstatus.**

    Wenn fehlerbehinddete Bereitstellungen (Geräte mit **Fehler,** **Anforderungen nicht erfüllt** oder **Fehlerstatus)** auftreten, müssen Sie die Geräte möglicherweise beheben. Weitere Informationen finden Sie unter ["Behandeln von Problemen beim Onboarding von Microsoft Defender für Endpunkten".](troubleshoot-onboarding.md)

    ![Configuration Manager zeigt eine erfolgreiche Bereitstellung ohne Fehler an](images/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-defender-for-endpoint-service"></a>Überprüfen Sie, ob die Geräte mit dem Microsoft Defender für Endpunktdienst kompatibel sind.

Sie können eine Complianceregel für Konfigurationselemente in System Center 2012 R2 Configuration Manager festlegen, um Ihre Bereitstellung zu überwachen.

Bei dieser Regel sollte es sich um ein *nicht korrigierende* Complianceregel-Konfigurationselement handeln, das den Wert eines Registrierungsschlüssels auf Zielgeräten überwacht.

Überwachen Sie den folgenden Registrierungsschlüsseleintrag:

```console
Path: "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status"
Name: "OnboardingState"
Value: "1"
```

Weitere Informationen finden Sie unter [Einführung in Complianceeinstellungen in System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))

## <a name="related-topics"></a>Verwandte Themen
- [Onboarding von Windows 10 Geräten mithilfe von Gruppenrichtlinien](configure-endpoints-gp.md)
- [Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten](configure-endpoints-mdm.md)
- [Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts](configure-endpoints-script.md)
- [Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)](configure-endpoints-vdi.md)
- [Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender für Endpunkt-Gerät](run-detection-test.md)
- [Behandeln von Problemen beim Onboarding von Microsoft Defender für Endpunkten](troubleshoot-onboarding.md)
