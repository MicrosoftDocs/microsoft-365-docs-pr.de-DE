---
title: Onboarding von Windows 10-Geräten mithilfe von Configuration Manager
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
description: Verwenden Sie Configuration Manager, um das Konfigurationspaket auf Geräten so zu bereitstellen, dass sie in den Dienst integrierte werden.
ms.openlocfilehash: ac05581ce33e94859dbd67848197878595d5ed0f
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893296"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a>Onboarding von Windows 10-Geräten mithilfe von Configuration Manager

**Gilt für:**

- [Microsoft 365 Verhinderung von Endpunktdatenverlusten (Endpoint Data Loss Prevention, DLP)](./endpoint-dlp-learn-about.md)
- System Center 2012 R2 Configuration Manager

### <a name="onboard-devices-using-system-center-configuration-manager"></a>Onboarding von Geräten mithilfe System Center Configuration Manager

1. Öffnen Sie die Konfigurationspaketdatei .zip Configuration Manager (*DeviceComplianceOnboardingPackage.zip*), die Sie aus dem Dienst-Onboarding-Assistenten heruntergeladen haben. Sie können das Paket auch über das [Microsoft Compliance Center erhalten.](https://compliance.microsoft.com/)

2. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Onboarding**  >  **des Geräts aus.**

3. Wählen Sie **im** Feld **Bereitstellungsmethode Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602 aus.**
 
4. Wählen **Sie Paket herunterladen** aus, und speichern Sie .zip Datei.

5. Extrahieren Sie den Inhalt der .zip an einen freigegebenen, schreibgeschützten Speicherort, auf den die Netzwerkadministratoren zugreifen können, die das Paket bereitstellen. Sie sollten über eine Datei mit dem Namen *DeviceComplianceOnboardingScript.cmd verfügen.*

6. Stellen Sie das Paket zur Verfügung, indem Sie die Schritte im Artikel Pakete und Programme [in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10)) ausführen.

7. Wählen Sie eine vordefinierte Gerätesammlung aus, auf der das Paket bereitgestellt werden soll.

> [!NOTE]
> Microsoft 365 Die Verhinderung von Endpunktdatenverlusten unterstützt das Onboarding während der [Out-Of-Box Experience (OOBE)-Phase](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) nicht. Stellen Sie sicher, dass Benutzer OOBE abschließen, nachdem sie Windows oder Upgrade ausgeführt haben.

>[!TIP]
> Nach dem Onboarding des Geräts können Sie einen Erkennungstest ausführen, um sicherzustellen, dass ein Gerät ordnungsgemäß in den Dienst integrierte ist. Weitere Informationen finden Sie unter Ausführen eines Erkennungstests auf einem neu integrierten [Microsoft Defender for Endpoint-Gerät.](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
>
> Beachten Sie, dass es möglich ist, eine Erkennungsregel für eine Configuration Manager-Anwendung zu erstellen, um kontinuierlich zu überprüfen, ob ein Gerät onboardiert wurde. Eine Anwendung ist ein anderer Objekttyp als ein Paket und Programm.
> Wenn ein Gerät noch nicht onboarded ist (aufgrund ausstehender OOBE-Fertigstellung oder aus einem anderen Grund), wird der Configuration Manager versuchen, das Gerät so lange zu integrieren, bis die Regel die Statusänderung erkennt.
> 
> Dieses Verhalten kann erreicht werden, indem eine Erkennungsregel erstellt wird, die überprüft, ob der Registrierungswert "OnboardingState" (vom Typ REG_DWORD) = 1 ist.
> Dieser Registrierungswert befindet sich unter "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".
Weitere Informationen finden Sie unter [Configure Detection Methods in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682159(v=technet.10)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).

### <a name="configure-sample-collection-settings"></a>Konfigurieren von Beispielsammlungseinstellungen

Für jedes Gerät können Sie einen Konfigurationswert festlegen, um zu bestimmen, ob Beispiele vom Gerät erfasst werden können, wenn über Microsoft Defender Security Center eine Datei zur tiefen Analyse übermittelt wird.

>[!NOTE]
>Diese Konfigurationseinstellungen werden in der Regel über Configuration Manager durchgeführt. 

Sie können eine Complianceregel für das Konfigurationselement in Configuration Manager festlegen, um die Beispielfreigabeeinstellung auf einem Gerät zu ändern.

Diese Regel sollte  ein Konfigurationselement zur Behebung der Complianceregel sein, das den Wert eines Registrierungsschlüssels auf zielgerichteten Geräten fest legt, um sicherzustellen, dass sie sich beschweren.

Die Konfiguration wird über den folgenden Registrierungsschlüsseleintrag festgelegt:

```
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
Dabei gilt:<br>
Der Schlüsseltyp ist D-WORD. <br>
Die folgenden Werte sind möglich:
- 0 – lässt keine Beispielfreigabe von diesem Gerät zu
- 1 – Ermöglicht die Freigabe aller Dateitypen von diesem Gerät

Der Standardwert für den Fall, dass der Registrierungsschlüssel nicht vorhanden ist, ist 1.

Weitere Informationen zur System Center Configuration Manager finden Sie unter [Einführung in Complianceeinstellungen in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10)).


## <a name="other-recommended-configuration-settings"></a>Weitere empfohlene Konfigurationseinstellungen
Nach dem Onboarding von Geräten in den Dienst ist es wichtig, die enthaltenen Funktionen zum Schutz vor Bedrohungen zu nutzen, indem Sie sie mit den folgenden empfohlenen Konfigurationseinstellungen aktivieren.

### <a name="device-collection-configuration"></a>Gerätesammlungskonfiguration
Wenn Sie Endpoint Configuration Manager, Version 2002 oder höher, verwenden, können Sie die Bereitstellung auf Server oder Clients auf ebener Ebene erweitern.


### <a name="next-generation-protection-configuration"></a>Schutzkonfiguration der nächsten Generation

Die folgenden Konfigurationseinstellungen werden empfohlen:

**Überprüfung**

- Überprüfen von Wechselmediengeräten wie USB-Laufwerken: Ja

**Echtzeitschutz**

- Aktivieren der Verhaltensüberwachung: Ja
- Aktivieren des Schutzes vor potenziell unerwünschten Anwendungen beim Herunterladen und vor der Installation: Ja

**Cloud Protection Service**

- Cloud Protection Service-Mitgliedschaftstyp: Erweiterte Mitgliedschaft

**Reduzierung der Angriffsfläche** Konfigurieren Sie alle verfügbaren Regeln für Überwachung.

>[!NOTE]
> Das Blockieren dieser Aktivitäten kann legitime Geschäftsprozesse unterbrechen. Der beste Ansatz besteht in der Festlegung der Überwachung, der Identifizierung derjenigen, die sicher aktiviert werden können, und dem Aktivieren dieser Einstellungen auf Endpunkten, die keine falsch positiven Erkennungen haben.

**Netzwerkschutz**

Stellen Sie vor dem Aktivieren des Netzwerkschutzes im Überwachungs- oder Blockmodus sicher, dass Sie das Update der Antischalwareplattform installiert haben, das sie auf der [Supportseite erhalten können.](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)


**Kontrollierter Ordnerzugriff**

Aktivieren Sie das Feature im Überwachungsmodus für mindestens 30 Tage. Überprüfen Sie nach diesem Zeitraum die Erkennungen, und erstellen Sie eine Liste der Anwendungen, die in geschützte Verzeichnisse schreiben dürfen.

Weitere Informationen finden Sie unter [Evaluate controlled folder access](/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access).


## <a name="offboard-devices-using-configuration-manager"></a>Offboardgeräte mit Configuration Manager

Aus Sicherheitsgründen läuft das für Offboard-Geräte verwendete Paket 30 Tage nach dem Downloaddatum ab. Abgelaufene offboarding-Pakete, die an ein Gerät gesendet werden, werden abgelehnt. Beim Herunterladen eines offboarding-Pakets werden Sie über das Ablaufdatum der Pakete benachrichtigt und es wird auch im Paketnamen enthalten sein.

> [!NOTE]
> Onboarding- und Offboardingrichtlinien dürfen nicht gleichzeitig auf demselben Gerät bereitgestellt werden, da andernfalls unvorhersehbare Kollisionen verursacht werden.

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a>Offboardgeräte mit Microsoft Endpoint Configuration Manager aktuellen Verzweigung

Wenn Sie Microsoft Endpoint Configuration Manager aktuellen Zweigstelle verwenden, lesen [Sie Erstellen einer Offboardingkonfigurationsdatei](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a>Offboardgeräte mit System Center 2012 R2 Configuration Manager

1. Holen Sie sich das offboarding-Paket aus [dem Microsoft Compliance Center:](https://compliance.microsoft.com/)

2. Wählen Sie im Navigationsbereich die **option Einstellungen**  >   **Device onboarding** >  **Offboarding aus.**

3. Wählen Windows 10 als Betriebssystem aus.

4. Wählen Sie **im** Feld **Bereitstellungsmethode Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602 aus.**
    
5. Wählen **Sie Paket herunterladen** aus, und speichern Sie .zip Datei.

6. Extrahieren Sie den Inhalt der .zip an einen freigegebenen, schreibgeschützten Speicherort, auf den die Netzwerkadministratoren zugreifen können, die das Paket bereitstellen. Sie sollten über eine Datei namens *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd verfügen.*

7. Stellen Sie das Paket zur Verfügung, indem Sie die Schritte im Artikel Pakete und Programme [in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg699369(v=technet.10)) ausführen.

8. Wählen Sie eine vordefinierte Gerätesammlung aus, auf der das Paket bereitgestellt werden soll.

> [!IMPORTANT]
> Offboarding bewirkt, dass das Gerät das Senden von Sensordaten an das Portal beendet, aber Daten vom Gerät, einschließlich Verweis auf alle Warnungen, die es erhalten hat, werden für bis zu 6 Monate aufbewahrt.


## <a name="monitor-device-configuration"></a>Überwachen der Gerätekonfiguration

Wenn Sie die aktuelle Microsoft Endpoint Configuration Manager verwenden, verwenden Sie das integrierte Microsoft Defender for Endpoint-Dashboard in der Configuration Manager-Konsole. Weitere Informationen finden Sie unter [Microsoft Defender Advanced Threat Protection - Monitor](/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).

Wenn Sie den System Center 2012 R2 Configuration Manager verwenden, besteht die Überwachung aus zwei Teilen:

1. Bestätigen, dass das Konfigurationspaket ordnungsgemäß bereitgestellt wurde und auf den Geräten in Ihrem Netzwerk ausgeführt wird (oder erfolgreich ausgeführt wurde).

2. Überprüfen, ob die Geräte mit dem Microsoft 365 Endpoint Data Loss Prevention Service kompatibel sind (dadurch wird sichergestellt, dass das Gerät den Onboardingprozess abschließen und weiterhin Daten an den Dienst melden kann).

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a>Bestätigen, dass das Konfigurationspaket ordnungsgemäß bereitgestellt wurde

1. Klicken Sie in der Configuration Manager-Konsole unten **im** Navigationsbereich auf Überwachung.

2. Wählen **Sie Übersicht** und dann **Bereitstellungen aus.**

3. Wählen Sie die Bereitstellung mit dem Paketnamen aus.

4. Überprüfen Sie die Statusindikatoren unter **Abschlussstatistik** und **Inhaltsstatus**.

    Bei fehlgeschlagenen Bereitstellungen (Geräte mit **Fehler,** **Nicht** erfüllten Anforderungen oder fehlgeschlagenen **Status)** müssen Sie möglicherweise Probleme mit den Geräten beheben. Weitere Informationen finden Sie unter [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).

    ![Configuration Manager zeigt eine erfolgreiche Bereitstellung ohne Fehler an](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-365-endpoint-data-loss-prevention-service"></a>Überprüfen Sie, ob die Geräte mit dem Microsoft 365 Endpoint Data Loss Prevention Service kompatibel sind.

Sie können eine Kompatibilitätsregel für konfigurationselement in System Center 2012 R2 Configuration Manager festlegen, um Ihre Bereitstellung zu überwachen.

> [!NOTE]
> Dieses Verfahren und der Registrierungseintrag gelten für Endpoint DLP sowie Advanced Threat Protection.

Bei dieser Regel sollte es sich um ein Konfigurationselement *zur Nichtbehendung* der Complianceregel, das den Wert eines Registrierungsschlüssels auf zielgerichteten Geräten überwacht.

Überwachen Sie den folgenden Registrierungsschlüsseleintrag:
```
Path: “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status”
Name: “OnboardingState”
Value: “1”
```
Weitere Informationen finden Sie unter [Einführung in Complianceeinstellungen in System Center 2012 R2 Configuration Manager](/previous-versions/system-center/system-center-2012-R2/gg682139(v=technet.10)).

## <a name="related-topics"></a>Verwandte Themen
- [Onboarding Windows 10 Geräte mithilfe von Gruppenrichtlinien](dlp-configure-endpoints-gp.md)
- [Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten](dlp-configure-endpoints-mdm.md)
- [Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts](dlp-configure-endpoints-script.md)
- [Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)](dlp-configure-endpoints-vdi.md)
- [Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender for Endpoint-Gerät](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Problembehandlung bei Microsoft Defender Advanced Threat Protection Onboardingproblemen](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)