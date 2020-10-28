---
title: Integrierte Windows 10-Geräte mithilfe von Configuration Manager
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
description: Verwenden Sie den Konfigurations-Manager, um das Konfigurationspaket auf Geräten bereitzustellen, damit Sie für den Dienst an Bord sind.
ms.openlocfilehash: ea1b0cba10dc3e7120192e0c0ee87e2e354f1cc2
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769478"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a>Integrierte Windows 10-Geräte mithilfe von Configuration Manager

**Gilt für:**

- [Microsoft 365 Endpunkt-Datenverlust Verhinderung (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)
- System Center 2012 R2 Configuration Manager

### <a name="onboard-devices-using-system-center-configuration-manager"></a>Integrierte Geräte mithilfe von System Center Configuration Manager

1. Öffnen Sie die ZIP-Datei des Configuration Manager-Konfigurationspakets ( *DeviceComplianceOnboardingPackage.zip* ), die Sie aus dem Dienst-Onboarding-Assistenten heruntergeladen haben. Sie können das Paket auch aus dem [Microsoft Compliance Center](https://compliance.microsoft.com/)abrufen.

2. Wählen Sie im Navigationsbereich die Option **Einstellungen** für das  >  **Onboarding von Geräten** aus  >  **Onboarding** .

3. Wählen Sie im Feld **Bereitstellungsmethode** den **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** aus.
 
4. Wählen Sie **Paket herunterladen** aus, und speichern Sie die ZIP-Datei.

5. Extrahieren Sie den Inhalt der ZIP-Datei an einen freigegebenen, schreibgeschützten Speicherort, auf den die Netzwerkadministratoren zugreifen können, die das Paket bereitstellen werden. Sie sollten über eine Datei mit dem Namen " *DeviceComplianceOnboardingScript. cmd* " verfügen.

6. Stellen Sie das Paket bereit, indem Sie die Schritte im Artikel [Pakete und Programme in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) ausführen.

7. Wählen Sie eine vordefinierte gerätesammlung aus, in der das Paket bereitgestellt werden soll.

> [!NOTE]
> Die Microsoft 365-Endpunkt Datenverlust-Verhinderung unterstützt Onboarding während der [out-of-Box-Erfahrungs Phase (OOBE)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) nicht. Stellen Sie sicher, dass die Benutzer die OOBE nach Ausführung der Windows-Installation oder Aktualisierung vollständig ausführen.

>[!TIP]
> Nach dem Onboarding des Geräts können Sie einen Erkennungstest ausführen, um zu überprüfen, ob ein Gerät ordnungsgemäß mit dem Dienst an Bord ist. Weitere Informationen finden Sie unter [Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender-ATP-Gerät](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test).
>
> Beachten Sie, dass es möglich ist, eine Erkennungsregel für eine Configuration Manager-Anwendung zu erstellen, um kontinuierlich zu überprüfen, ob ein Gerät onboarded war. Eine Anwendung ist ein anderer Objekttyp als ein Paket und Programm.
> Wenn ein Gerät noch nicht an Bord ist (aufgrund einer ausstehenden OOBE-Fertigstellung oder aus einem anderen Grund), versucht Configuration Manager, das Gerät an Bord zu führen, bis die Regel die Statusänderung erkennt.
> 
> Dieses Verhalten kann durch Erstellen einer Erkennungsregel überprüft werden, wenn der Registrierungswert "OnboardingState" (vom Typ REG_DWORD) = 1 ist.
> Dieser Registrierungswert befindet sich unter "HKLM\Software\Microsoft\Windows Advanced Threat Protection\Status".
Weitere Informationen finden Sie unter [configure detection methods in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).

### <a name="configure-sample-collection-settings"></a>Konfigurieren von Einstellungen für die Beispielsammlung

Sie können für jedes Gerät einen Konfigurationswert festlegen, um anzugeben, ob Proben vom Gerät erfasst werden können, wenn eine Anforderung über das Microsoft Defender Security Center gestellt wird, um eine Datei zur tiefen Analyse zu übermitteln.

>[!NOTE]
>Diese Konfigurationseinstellungen werden normalerweise über den Konfigurations-Manager ausgeführt. 

Sie können eine Konformitätsregel für das Konfigurationselement in Configuration Manager festlegen, um die Beispiel Freigabe Einstellung auf einem Gerät zu ändern.

Bei dieser Regel muss es sich um ein Konfigurationselement für die richtlinienkonforme Konformitätsregel handeln, das den Wert eines Registrierungsschlüssels auf Zielgeräten festlegt, um sicherzustellen, dass es sich *um eine Reklamation* handelt.

Die Konfiguration wird über den folgenden Registrierungsschlüsseleintrag festgelegt:

```
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
Dabei gilt:<br>
Key-Typ ist ein D-Wort. <br>
Die folgenden Werte sind möglich:
- 0 – die Beispiel Freigabe für dieses Gerät wird nicht zugelassen.
- 1-ermöglicht die Freigabe aller Dateitypen von diesem Gerät

Der Standardwert für den Fall, dass der Registrierungsschlüssel nicht vorhanden ist, ist 1.

Weitere Informationen zur Compliance von System Center Configuration Manager finden Sie unter [Introduction to Compliance Settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).


## <a name="other-recommended-configuration-settings"></a>Weitere empfohlene Konfigurationseinstellungen
Nachdem Sie die Onboarding-Geräte für den Dienst verwendet haben, ist es wichtig, dass Sie die enthaltenen Funktionen zum Schutz vor Bedrohungen nutzen, indem Sie Sie mit den folgenden empfohlenen Konfigurationseinstellungen aktivieren.

### <a name="device-collection-configuration"></a>Konfiguration der gerätesammlung
Wenn Sie den Endpunkt Konfigurations-Manager (Version 2002 oder höher) verwenden, können Sie die Bereitstellung erweitern, um Server oder untergeordnete Clients einzubeziehen.


### <a name="next-generation-protection-configuration"></a>Schutzkonfiguration der nächsten Generation

Die folgenden Konfigurationseinstellungen werden empfohlen:

**Überprüfung**

- Scannen von Wechselmediengeräten wie USB-Laufwerken: Ja

**Echtzeitschutz**

- Aktivieren der Verhaltensüberwachung: Ja
- Aktivieren des Schutzes vor potenziell unerwünschten Anwendungen beim Herunterladen und vor der Installation: Ja

**Cloud Protection-Dienst**

- Typ der Cloud Protection-Dienst Mitgliedschaft: erweiterte Mitgliedschaft

**Angriffsflächen Reduzierung** Konfigurieren Sie alle verfügbaren Regeln für die Überwachung.

>[!NOTE]
> Das Blockieren dieser Aktivitäten kann legitime Geschäftsprozesse unterbrechen. Der beste Ansatz besteht darin, alles für die Überwachung festzulegen, zu ermitteln, welche sicher aktiviert werden sollen, und diese Einstellungen dann auf Endpunkten zu aktivieren, die keine falsch positiven Erkennungen aufweisen.

**Netzwerkschutz**

Vor dem Aktivieren von Netzwerkschutz im Überwachungs-oder Blockierungs Modus müssen Sie sicherstellen, dass Sie das Platt Form Update für Antischadsoftware installiert haben, das auf der [Support Seite](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)abgerufen werden kann.


**Zugriff auf kontrollierte Ordner**

Aktivieren Sie das Feature für mindestens 30 Tage im Überwachungsmodus. Überprüfen Sie nach diesem Zeitraum Erkennungen, und erstellen Sie eine Liste der Anwendungen, die in geschützte Verzeichnisse schreiben dürfen.

Weitere Informationen finden Sie unter [evaluieren des Zugriffs auf kontrollierte Ordner](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access).


## <a name="offboard-devices-using-configuration-manager"></a>Extern-Geräte mithilfe von Configuration Manager

Aus Sicherheitsgründen läuft das Paket, das für extern-Geräte verwendet wird, 30 Tage nach dem heruntergeladenen Datum ab. Abgelaufene offboarding-Pakete, die an ein Gerät gesendet werden, werden zurückgewiesen. Wenn Sie ein offboarding-Paket herunterladen, werden Sie über das Ablaufdatum der Pakete benachrichtigt, und es wird auch in den Paketnamen eingeschlossen.

> [!NOTE]
> Onboarding-und offboarding-Richtlinien dürfen nicht gleichzeitig auf demselben Gerät bereitgestellt werden, da dies andernfalls zu unvorhersehbaren Konflikten führen kann.

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a>Extern-Geräte mit dem aktuellen Zweig "Microsoft Endpoint Configuration Manager"

Wenn Sie den aktuellen Zweig Microsoft Endpoint Configuration Manager verwenden, lesen Sie [Erstellen einer offboarding-Konfigurationsdatei](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a>Extern-Geräte mit System Center 2012 R2-Konfigurations-Manager

1. Rufen Sie das offboarding-Paket im [Microsoft Compliance Center](https://compliance.microsoft.com/)ab:

2. Wählen Sie im Navigationsbereich **Einstellungen**  >   **Gerät Onboarding** >  **Offboarding** .

3. Wählen Sie als Betriebssystem Windows 10 aus.

4. Wählen Sie im Feld **Bereitstellungsmethode** den **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** aus.
    
5. Wählen Sie **Paket herunterladen** aus, und speichern Sie die ZIP-Datei.

6. Extrahieren Sie den Inhalt der ZIP-Datei an einen freigegebenen, schreibgeschützten Speicherort, auf den die Netzwerkadministratoren zugreifen können, die das Paket bereitstellen werden. Sie sollten über eine Datei mit dem Namen *DeviceComplianceOffboardingScript_valid_until_YYYY-mm-dd. cmd* verfügen.

7. Stellen Sie das Paket bereit, indem Sie die Schritte im Artikel [Pakete und Programme in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) ausführen.

8. Wählen Sie eine vordefinierte gerätesammlung aus, in der das Paket bereitgestellt werden soll.

> [!IMPORTANT]
> Offboarding bewirkt, dass das Gerät das Senden von Sensordaten an das Portal beendet, aber die Daten des Geräts, einschließlich des Verweises auf bereits gemachte Warnungen, werden bis zu 6 Monate aufbewahrt.


## <a name="monitor-device-configuration"></a>Überwachen der Gerätekonfiguration

Wenn Sie den Microsoft Endpoint Configuration Manager Current Branch verwenden, verwenden Sie das integrierte Microsoft Defender ATP-Dashboard in der Configuration Manager-Konsole. Weitere Informationen finden Sie unter [Advanced Threat Protection-Monitor von Microsoft Defender](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).

Wenn Sie den System Center 2012 R2-Konfigurations-Manager verwenden, besteht die Überwachung aus zwei Teilen:

1. Bestätigen, dass das Konfigurationspaket ordnungsgemäß bereitgestellt wurde und auf den Geräten in Ihrem Netzwerk ausgeführt (oder erfolgreich ausgeführt wurde).

2. Überprüfen, ob die Geräte mit dem Microsoft 365 Endpoint Data Loss Prevention-Dienst kompatibel sind (Dadurch wird sichergestellt, dass das Gerät den Onboarding-Prozess abschließen kann und weiterhin Daten an den Dienst melden kann).

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a>Bestätigen, dass das Konfigurationspaket ordnungsgemäß bereitgestellt wurde

1. Klicken Sie in der Configuration Manager-Konsole unten im Navigationsbereich auf **Überwachung** .

2. Wählen Sie **Übersicht** und dann **Bereitstellungen** aus.

3. Wählen Sie auf der Bereitstellung mit dem Paketnamen aus.

4. Überprüfen Sie die Statusindikatoren unter **abschlussstatistik** und **Inhaltsstatus** .

    Bei fehlgeschlagenen Bereitstellungen (Geräte mit **Fehlern** , **Anforderungen nicht erfüllt** oder **Status Fehler** ) müssen Sie möglicherweise eine Problembehandlung für die Geräte durchzuführen. Weitere Informationen finden Sie unter [Problembehandlung bei Onboarding-Problemen bei Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).

    ![Konfigurations-Manager zeigt eine erfolgreiche Bereitstellung ohne Fehler](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-365-endpoint-data-loss-prevention-service"></a>Überprüfen, ob die Geräte mit dem Microsoft 365 Endpoint Data Loss Prevention-Dienst kompatibel sind

Sie können eine Konformitätsregel für das Konfigurationselement in System Center 2012 R2 Configuration Manager festlegen, um Ihre Bereitstellung zu überwachen.

> [!NOTE]
> Diese Prozedur und der Registrierungseintrag gelten sowohl für die Endpunkt-DLP-Installation als auch für Advanced Threat Protection.

Diese Regel sollte ein Konfigurationselement für *die Konformitäts* Regel sein, das den Wert eines Registrierungsschlüssels auf Zielgeräten überwacht.

Überwachen Sie den folgenden Registrierungsschlüsseleintrag:
```
Path: “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status”
Name: “OnboardingState”
Value: “1”
```
Weitere Informationen finden Sie unter [Introduction to Compliance Settings in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).

## <a name="related-topics"></a>Verwandte Themen
- [Integrierte Windows 10-Geräte mithilfe von Gruppenrichtlinien](dlp-configure-endpoints-gp.md)
- [Integrierte Windows 10-Geräte mit Tools zur Verwaltung mobiler Geräte](dlp-configure-endpoints-mdm.md)
- [Onboard-Windows 10-Geräte mithilfe eines lokalen Skripts](dlp-configure-endpoints-script.md)
- [Onboard-VDI-Geräte (Non-persistent Virtual Desktop Infrastructure)](dlp-configure-endpoints-vdi.md)
- [Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender-ATP-Gerät](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Problembehandlung bei Onboarding-Problemen bei Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
