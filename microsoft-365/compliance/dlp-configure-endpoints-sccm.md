---
title: Onboarding von Windows 10-Geräten mithilfe von Configuration Manager
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Verwenden Sie Configuration Manager, um das Konfigurationspaket auf Geräten bereitzustellen, sodass sie in den Dienst integriert sind.
ms.openlocfilehash: d2db35e50d31a0a19076965da6dcecf9cfeef826
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226897"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a>Onboarding von Windows 10-Geräten mithilfe von Configuration Manager

**Gilt für:**

- [Microsoft 365 Verhinderung von Datenverlust am Endpunkt (Endpoint Data Loss Prevention, DLP)](./endpoint-dlp-learn-about.md)
- System Center 2012 R2 Configuration Manager

### <a name="onboard-devices-using-system-center-configuration-manager"></a>Onboarding von Geräten mit System Center Configuration Manager

1. Öffnen Sie das Configuration Manager-Konfigurationspaket .zip Datei (*DeviceComplianceOnboardingPackage.zip*), die Sie aus dem Dienst-Onboarding-Assistenten heruntergeladen haben. Sie können das Paket auch aus dem [Microsoft Compliance Center](https://compliance.microsoft.com/)abrufen.

2. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Onboarding** von Geräten  >  **aus.**

3. Wählen Sie im Feld **"Bereitstellungsmethode"** **Microsoft Endpoint Configuration Manager 2012.02.1511/1602 aus.**

4. Wählen Sie **"Paket herunterladen"** aus, und speichern Sie die .zip Datei.

5. Extrahieren Sie den Inhalt der .zip-Datei an einen freigegebenen, schreibgeschützten Speicherort, auf den die Netzwerkadministratoren zugreifen können, die das Paket bereitstellen. Sie sollten über eine Datei mit dem Namen *DeviceComplianceOnboardingScript.cmd verfügen.*

6. Stellen Sie das Paket bereit, indem Sie die Schritte im Artikel ["Pakete und Programme" in System Center 2012 R2 Configuration Manager ausführen.](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10))

7. Wählen Sie eine vordefinierte Gerätesammlung aus, in der das Paket bereitgestellt werden soll.

> [!NOTE]
> Microsoft 365 Die Verhinderung von Datenverlust am Endpunkt unterstützt das Onboarding während der [Out-Of-Box Experience (OOBE)-Phase](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) nicht. Stellen Sie sicher, dass Benutzer die Windows-Willkommensseite abschließen, nachdem sie Windows Installation oder ein Upgrade ausgeführt haben.

> [!TIP]
> Nach dem Onboarding des Geräts können Sie einen Erkennungstest ausführen, um zu überprüfen, ob ein Gerät ordnungsgemäß in den Dienst integriert ist. Weitere Informationen finden Sie unter [Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender für Endpunkt-Gerät.](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
>
> Beachten Sie, dass es möglich ist, eine Erkennungsregel für eine Configuration Manager-Anwendung zu erstellen, um kontinuierlich zu überprüfen, ob ein Gerät integriert wurde. Eine Anwendung ist ein anderer Objekttyp als ein Paket und ein Programm.
> Wenn ein Gerät noch nicht integriert ist (aufgrund eines ausstehenden OoBE-Abschlusses oder aus einem anderen Grund), versucht Configuration Manager erneut, das Gerät zu integrieren, bis die Regel die Statusänderung erkennt.
>
> Dieses Verhalten kann erreicht werden, indem eine Erkennungsregel erstellt wird, die überprüft, ob der Registrierungswert "OnboardingState" (vom Typ REG_DWORD) = 1 ist.
> Dieser Registrierungswert befindet sich unter "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".
Weitere Informationen finden Sie unter [Konfigurieren von Erkennungsmethoden in System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg682159(v=technet.10)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)

### <a name="configure-sample-collection-settings"></a>Konfigurieren von Beispielsammlungseinstellungen

Für jedes Gerät können Sie einen Konfigurationswert festlegen, um anzugeben, ob Beispiele vom Gerät erfasst werden können, wenn eine Anforderung über Microsoft Defender Security Center zum Übermitteln einer Datei für eine umfassende Analyse gestellt wird.

> [!NOTE]
> Diese Konfigurationseinstellungen werden in der Regel über Configuration Manager durchgeführt.

Sie können eine Complianceregel für ein Konfigurationselement in Configuration Manager festlegen, um die Beispielfreigabeeinstellung auf einem Gerät zu ändern.

Diese Regel sollte *ein* Konfigurationselement zur Behebung der Complianceregel sein, das den Wert eines Registrierungsschlüssels auf Zielgeräten festlegt, um sicherzustellen, dass diese beschwerden.

Die Konfiguration wird über den folgenden Registrierungsschlüsseleintrag festgelegt:

```
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
Dabei gilt Folgendes:<br>
Der Schlüsseltyp ist D-WORD. <br>
Die folgenden Werte sind möglich:
- 0 – lässt keine Beispielfreigabe von diesem Gerät zu
- 1 – ermöglicht die Freigabe aller Dateitypen von diesem Gerät

Der Standardwert für den Fall, dass der Registrierungsschlüssel nicht vorhanden ist, ist 1.

Weitere Informationen zu System Center Configuration Manager Compliance finden Sie unter [Einführung in Complianceeinstellungen in System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10))


## <a name="other-recommended-configuration-settings"></a>Andere empfohlene Konfigurationseinstellungen
Nach dem Onboarding von Geräten in den Dienst ist es wichtig, die enthaltenen Bedrohungsschutzfunktionen zu nutzen, indem Sie diese mit den folgenden empfohlenen Konfigurationseinstellungen aktivieren.

### <a name="device-collection-configuration"></a>Gerätesammlungskonfiguration
Wenn Sie Endpoint Configuration Manager, Version 2002 oder höher, verwenden, können Sie die Bereitstellung erweitern, um Server oder Untergeordnete Clients einzuschließen.


### <a name="next-generation-protection-configuration"></a>Schutzkonfiguration der nächsten Generation

Die folgenden Konfigurationseinstellungen werden empfohlen:

**Überprüfung**

- Scannen von Wechselmedien wie USB-Laufwerken: Ja

**Echtzeitschutz**

- Aktivieren der Verhaltensüberwachung: Ja
- Aktivieren des Schutzes vor potenziell unerwünschten Anwendungen beim Download und vor der Installation: Ja

**Cloud Protection Service**

- Cloud Protection Service-Mitgliedschaftstyp: Erweiterte Mitgliedschaft

**Verringerung der Angriffsfläche** Konfigurieren Sie alle verfügbaren Regeln für die Überwachung.

> [!NOTE]
> Das Blockieren dieser Aktivitäten kann legitime Geschäftsprozesse unterbrechen. Der beste Ansatz besteht darin, alles zu überwachen, zu identifizieren, welche sicher aktiviert werden können, und dann die Einstellungen auf Endpunkten zu aktivieren, die keine falsch positiven Erkennungen aufweisen.

**Netzwerkschutz**

Stellen Sie vor dem Aktivieren des Netzwerkschutzes im Überwachungs- oder Blockierungsmodus sicher, dass Sie das Antischadsoftware-Plattformupdate installiert haben, das über die [Supportseite](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)abgerufen werden kann.


**Kontrollierter Ordnerzugriff**

Aktivieren Sie das Feature mindestens 30 Tage lang im Überwachungsmodus. Überprüfen Sie nach ablaufen diesem Zeitraum die Erkennungen, und erstellen Sie eine Liste der Anwendungen, die in geschützte Verzeichnisse schreiben dürfen.

Weitere Informationen finden Sie unter [Auswerten des kontrollierten Ordnerzugriffs.](/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access)


## <a name="offboard-devices-using-configuration-manager"></a>Offboarding von Geräten mit Configuration Manager

Aus Sicherheitsgründen läuft das Paket, das für Offboard-Geräte verwendet wird, 30 Tage nach dem Datum ab, an dem es heruntergeladen wurde. Abgelaufene Offboardingpakete, die an ein Gerät gesendet werden, werden abgelehnt. Beim Herunterladen eines Offboardingpakets werden Sie über das Ablaufdatum der Pakete benachrichtigt, und es wird auch in den Paketnamen aufgenommen.

> [!NOTE]
> Onboarding- und Offboarding-Richtlinien dürfen nicht gleichzeitig auf demselben Gerät bereitgestellt werden, andernfalls führt dies zu unvorhersehbaren Kollisionen.

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a>Offboarding von Geräten mit Microsoft Endpoint Configuration Manager aktuellen Verzweigung

Wenn Sie Microsoft Endpoint Configuration Manager aktuelle Verzweigung verwenden, lesen [Sie Erstellen einer Offboarding-Konfigurationsdatei .](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a>Offboarding von Geräten mit System Center 2012 R2 Configuration Manager

1. Rufen Sie das Offboarding-Paket aus dem [Microsoft Compliance Center](https://compliance.microsoft.com/)ab:

2. Wählen Sie im Navigationsbereich **Einstellungen**  >   **Onboarding-Offboarding** des >  **Geräts** aus.

3. Wählen Sie Windows 10 als Betriebssystem aus.

4. Wählen Sie im Feld **"Bereitstellungsmethode"** **Microsoft Endpoint Configuration Manager 2012.02.1511/1602 aus.**

5. Wählen Sie **"Paket herunterladen"** aus, und speichern Sie die .zip Datei.

6. Extrahieren Sie den Inhalt der .zip-Datei an einen freigegebenen, schreibgeschützten Speicherort, auf den die Netzwerkadministratoren zugreifen können, die das Paket bereitstellen. Sie sollten über eine Datei mit dem Namen *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd verfügen.*

7. Stellen Sie das Paket bereit, indem Sie die Schritte im Artikel ["Pakete und Programme" in System Center 2012 R2 Configuration Manager ausführen.](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10))

8. Wählen Sie eine vordefinierte Gerätesammlung aus, in der das Paket bereitgestellt werden soll.

> [!IMPORTANT]
> Das Offboarding bewirkt, dass das Gerät das Senden von Sensordaten an das Portal beendet, aber Daten vom Gerät, einschließlich Verweise auf warnungen, die es gesendet hat, werden bis zu 6 Monate lang aufbewahrt.


## <a name="monitor-device-configuration"></a>Überwachen der Gerätekonfiguration

Wenn Sie Microsoft Endpoint Configuration Manager aktuelle Verzweigung verwenden, verwenden Sie das integrierte Microsoft Defender für Endpunkt-Dashboard in der Configuration Manager-Konsole. Weitere Informationen finden Sie unter [Microsoft Defender Advanced Threat Protection – Überwachen.](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)

Wenn Sie System Center 2012 R2 Configuration Manager verwenden, besteht die Überwachung aus zwei Teilen:

1. Bestätigen, dass das Konfigurationspaket ordnungsgemäß bereitgestellt wurde und auf den Geräten in Ihrem Netzwerk ausgeführt wird (oder erfolgreich ausgeführt wurde).

2. Überprüfen, ob die Geräte mit dem Microsoft 365 Endpunkt-Dienst zur Verhinderung von Datenverlust kompatibel sind (dadurch wird sichergestellt, dass das Gerät den Integrationsprozess abschließen und weiterhin Daten an den Dienst melden kann).

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a>Sicherstellen, dass das Konfigurationspaket ordnungsgemäß bereitgestellt wurde

1. Klicken Sie in der Configuration Manager-Konsole unten im Navigationsbereich auf **"Überwachung".**

2. Wählen Sie **"Übersicht"** und dann **"Bereitstellungen" aus.**

3. Wählen Sie die Bereitstellung mit dem Paketnamen aus.

4. Überprüfen Sie die Statusindikatoren unter **Abschlussstatistik** und **Inhaltsstatus.**

    Wenn fehlerbehinddete Bereitstellungen (Geräte mit **Fehler,** **Anforderungen nicht erfüllt** oder **Fehlerstatus)** auftreten, müssen Sie die Geräte möglicherweise beheben. Weitere Informationen finden Sie unter [Behandeln von Microsoft Defender Advanced Threat Protection-Integrationsproblemen.](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)

    ![Configuration Manager zeigt eine erfolgreiche Bereitstellung ohne Fehler an](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-365-endpoint-data-loss-prevention-service"></a>Überprüfen Sie, ob die Geräte mit dem Microsoft 365 Endpunkt-Dienst zur Verhinderung von Datenverlust kompatibel sind.

Sie können eine Complianceregel für Konfigurationselemente in System Center 2012 R2 Configuration Manager festlegen, um Ihre Bereitstellung zu überwachen.

> [!NOTE]
> Dieses Verfahren und der Registrierungseintrag gelten für Endpunkt-DLP und Advanced Threat Protection.

Bei dieser Regel sollte es sich um ein *nicht korrigierende* Complianceregel-Konfigurationselement handeln, das den Wert eines Registrierungsschlüssels auf Zielgeräten überwacht.

Überwachen Sie den folgenden Registrierungsschlüsseleintrag:
```
Path: “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status”
Name: “OnboardingState”
Value: “1”
```
Weitere Informationen finden Sie unter [Einführung in Complianceeinstellungen in System Center 2012 R2 Configuration Manager.](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10))

## <a name="related-topics"></a>Verwandte Themen
- [Onboarding von Windows 10 Geräten mithilfe von Gruppenrichtlinien](dlp-configure-endpoints-gp.md)
- [Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten](dlp-configure-endpoints-mdm.md)
- [Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts](dlp-configure-endpoints-script.md)
- [Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)](dlp-configure-endpoints-vdi.md)
- [Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender für Endpunkt-Gerät](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Behandeln von Problemen beim Onboarding von Microsoft Defender Advanced Threat Protection](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)