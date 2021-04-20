---
title: Onboarding von Windows 10-Geräten mithilfe von Configuration Manager
description: Verwenden Sie Configuration Manager, um das Konfigurationspaket auf Geräten so zu bereitstellen, dass sie in den Dienst integrierte werden.
keywords: Onboarding von Geräten mithilfe von sccm, Geräteverwaltung, Konfigurieren von Windows ATP-Geräten, Konfigurieren von Microsoft Defender for Endpoint-Geräten
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
ms.openlocfilehash: 3550bec28945ab888efbe2ca46f12ca7f96aab4a
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51892863"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a>Onboarding von Windows 10-Geräten mithilfe von Configuration Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Aktuelle Verzweigung von Microsoft Endpoint Configuration Manager
- System Center 2012 R2 Configuration Manager

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointssccm-abovefoldlink)

## <a name="supported-client-operating-systems"></a>Unterstützte Clientbetriebssysteme

Basierend auf der version von Configuration Manager, die Sie ausführen, können die folgenden Clientbetriebssysteme onboardiert werden:

#### <a name="configuration-manager-version-1910-and-prior"></a>Configuration Manager, Version 1910 und früher

- Clients computer running Windows 10 

#### <a name="configuration-manager-version-2002-and-later"></a>Configuration Manager, Version 2002 und höher

Ab Configuration Manager, Version 2002, können Sie die folgenden Betriebssysteme integrieren:

- Windows 8.1
- Windows 10
- Windows Server 2012 R2
- Windows Server 2016
- Windows Server 2016, Version 1803 oder höher
- Windows Server 2019

>[!NOTE]
>Weitere Informationen zum Onboarding von Windows Server 2012 R2, Windows Server 2016 und Windows Server 2019 finden Sie unter [Onboarding von Windows-Servern](configure-server-endpoints.md).



### <a name="onboard-devices-using-system-center-configuration-manager"></a>Onboarding von Geräten mithilfe von System Center Configuration Manager


[![Abbildung der PDF mit den verschiedenen Bereitstellungspfaden](images/onboard-config-mgr.png)](images/onboard-config-mgr.png#lightbox)


Sehen Sie sich [die PDF-](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  oder  [Visio-Datei](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) an, um die verschiedenen Pfade bei der Bereitstellung von Microsoft Defender for Endpoint zu sehen. 



1. Öffnen Sie die ZIP-Datei des *Configuration Manager-Konfigurationspakets*(WindowsDefenderATPOnboardingPackage.zip), die Sie aus dem Assistenten zum Onboarding des Diensts heruntergeladen haben. Sie können das Paket auch über [das Microsoft Defender Security Center erhalten:](https://securitycenter.windows.com/)

    1. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Onboarding aus.**
    
    1. Wählen Sie Windows 10 als Betriebssystem aus.

    1. Wählen Sie **im Feld Bereitstellungsmethode** die Option **System Center Configuration Manager 2012/2012 R2/1511/1602 aus.**
    
    1. Wählen **Sie Paket herunterladen** aus, und speichern Sie die ZIP-Datei.

2. Extrahieren Sie den Inhalt der ZIP-Datei an einen freigegebenen schreibgeschützten Speicherort, auf den die Netzwerkadministratoren zugreifen können, die das Paket bereitstellen. Sie sollten über eine Datei mit dem Namen *WindowsDefenderATPOnboardingScript.cmd verfügen.*

3. Stellen Sie das Paket zur Verfügung, indem Sie die Schritte im Artikel Pakete und Programme [in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) ausführen.

    a. Wählen Sie eine vordefinierte Gerätesammlung aus, auf der das Paket bereitgestellt werden soll.

> [!NOTE]
> Defender for Endpoint unterstützt das Onboarding während der [Out-Of-Box Experience (OOBE)-Phase](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) nicht. Stellen Sie sicher, dass Benutzer nach der Ausführung der Windows-Installation oder des Upgrades OOBE abschließen.

>[!TIP]
> Nach dem Onboarding des Geräts können Sie einen Erkennungstest ausführen, um sicherzustellen, dass ein Gerät ordnungsgemäß in den Dienst integrierte ist. Weitere Informationen finden Sie unter Ausführen eines Erkennungstests auf einem neu integrierten [Defender for Endpoint-Gerät.](run-detection-test.md)
>
> Beachten Sie, dass es möglich ist, eine Erkennungsregel für eine Configuration Manager-Anwendung zu erstellen, um kontinuierlich zu überprüfen, ob ein Gerät onboardiert wurde. Eine Anwendung ist ein anderer Objekttyp als ein Paket und Programm.
> Wenn ein Gerät noch nicht onboarded ist (aufgrund ausstehender OOBE-Fertigstellung oder aus einem anderen Grund), wird der Configuration Manager versuchen, das Gerät so lange zu integrieren, bis die Regel die Statusänderung erkennt.
> 
> Dieses Verhalten kann erreicht werden, indem eine Erkennungsregel erstellt wird, die überprüft, ob der Registrierungswert "OnboardingState" (vom Typ REG_DWORD) = 1 ist.
> Dieser Registrierungswert befindet sich unter "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status".
Weitere Informationen finden Sie unter [Configure Detection Methods in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type).

### <a name="configure-sample-collection-settings"></a>Konfigurieren von Beispielsammlungseinstellungen

Für jedes Gerät können Sie einen Konfigurationswert festlegen, um zu bestimmen, ob Beispiele vom Gerät gesammelt werden können, wenn über das Microsoft Defender Security Center eine Anforderung zum Übermitteln einer Datei zur tiefen Analyse gestellt wird.

>[!NOTE]
>Diese Konfigurationseinstellungen werden in der Regel über Configuration Manager durchgeführt. 

Sie können eine Complianceregel für das Konfigurationselement in Configuration Manager festlegen, um die Beispielfreigabeeinstellung auf einem Gerät zu ändern.

Diese Regel sollte  ein Konfigurationselement zur Behebung der Complianceregel sein, das den Wert eines Registrierungsschlüssels auf zielgerichteten Geräten fest legt, um sicherzustellen, dass sie sich beschweren.

Die Konfiguration wird über den folgenden Registrierungsschlüsseleintrag festgelegt:

```console
Path: "HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection"
Name: "AllowSampleCollection"
Value: 0 or 1
```

Dabei gilt:<br>
Der Schlüsseltyp ist D-WORD. <br>
Die folgenden Werte sind möglich:
- 0 – lässt keine Beispielfreigabe von diesem Gerät zu
- 1 – Ermöglicht die Freigabe aller Dateitypen von diesem Gerät

Der Standardwert für den Fall, dass der Registrierungsschlüssel nicht vorhanden ist, ist 1.

Weitere Informationen zur System Center Configuration Manager Compliance finden Sie [unter Einführung in Complianceeinstellungen in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).


## <a name="other-recommended-configuration-settings"></a>Weitere empfohlene Konfigurationseinstellungen
Nach dem Onboarding von Geräten in den Dienst ist es wichtig, die enthaltenen Funktionen zum Schutz vor Bedrohungen zu nutzen, indem Sie sie mit den folgenden empfohlenen Konfigurationseinstellungen aktivieren.

### <a name="device-collection-configuration"></a>Gerätesammlungskonfiguration
Wenn Sie Endpoint Configuration Manager, Version 2002 oder höher, verwenden, können Sie die Bereitstellung auf Server oder Clients auf ebener Ebene erweitern.


### <a name="next-generation-protection-configuration"></a>Schutzkonfiguration der nächsten Generation
Die folgenden Konfigurationseinstellungen werden empfohlen:

**Überprüfung** <br>
- Überprüfen von Wechselmediengeräten wie USB-Laufwerken: Ja

**Echtzeitschutz** <br>
- Aktivieren der Verhaltensüberwachung: Ja
- Aktivieren des Schutzes vor potenziell unerwünschten Anwendungen beim Herunterladen und vor der Installation: Ja

**Cloud Protection Service**
- Cloud Protection Service-Mitgliedschaftstyp: Erweiterte Mitgliedschaft

**Reduzierung der Angriffsfläche** Konfigurieren Sie alle verfügbaren Regeln für Überwachung.

>[!NOTE]
> Das Blockieren dieser Aktivitäten kann legitime Geschäftsprozesse unterbrechen. Der beste Ansatz besteht in der Festlegung der Überwachung, der Identifizierung derjenigen, die sicher aktiviert werden können, und dem Aktivieren dieser Einstellungen auf Endpunkten, die keine falsch positiven Erkennungen haben.


**Netzwerkschutz** <br>
Stellen Sie vor dem Aktivieren des Netzwerkschutzes im Überwachungs- oder Blockmodus sicher, dass Sie das Update der Antischalwareplattform installiert haben, das sie auf der [Supportseite erhalten können.](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)


**Kontrollierter Ordnerzugriff**<br>
Aktivieren Sie das Feature im Überwachungsmodus für mindestens 30 Tage. Überprüfen Sie nach diesem Zeitraum die Erkennungen, und erstellen Sie eine Liste der Anwendungen, die in geschützte Verzeichnisse schreiben dürfen.

Weitere Informationen finden Sie unter [Evaluate controlled folder access](evaluate-controlled-folder-access.md).


## <a name="offboard-devices-using-configuration-manager"></a>Offboardgeräte mit Configuration Manager

Aus Sicherheitsgründen läuft das für Offboard-Geräte verwendete Paket 30 Tage nach dem Downloaddatum ab. Abgelaufene offboarding-Pakete, die an ein Gerät gesendet werden, werden abgelehnt. Beim Herunterladen eines offboarding-Pakets werden Sie über das Ablaufdatum der Pakete benachrichtigt und es wird auch im Paketnamen enthalten sein.

> [!NOTE]
> Onboarding- und Offboardingrichtlinien dürfen nicht gleichzeitig auf demselben Gerät bereitgestellt werden, da andernfalls unvorhersehbare Kollisionen verursacht werden.

### <a name="offboard-devices-using-microsoft-endpoint-manager-current-branch"></a>Offboardgeräte, die den aktuellen Microsoft Endpoint Manager verwenden

Wenn Sie den aktuellen Microsoft Endpoint Manager-Zweig verwenden, finden Sie weitere Informationen unter [Create an offboarding configuration file](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file).

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a>Offboardgeräte mit System Center 2012 R2 Configuration Manager

1. Das offboarding-Paket aus [dem Microsoft Defender Security Center erhalten:](https://securitycenter.windows.com/)

    1. Wählen Sie im Navigationsbereich **Einstellungen**  >   **Offboarding aus.**

    1. Wählen Sie Windows 10 als Betriebssystem aus.

    1. Wählen Sie **im Feld Bereitstellungsmethode** die Option **System Center Configuration Manager 2012/2012 R2/1511/1602 aus.**
    
    1. Wählen **Sie Paket herunterladen** aus, und speichern Sie die ZIP-Datei.

2. Extrahieren Sie den Inhalt der ZIP-Datei an einen freigegebenen schreibgeschützten Speicherort, auf den die Netzwerkadministratoren zugreifen können, die das Paket bereitstellen. Sie sollten über eine Datei namens *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd verfügen.*

3. Stellen Sie das Paket zur Verfügung, indem Sie die Schritte im Artikel Pakete und Programme [in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) ausführen.

    a. Wählen Sie eine vordefinierte Gerätesammlung aus, auf der das Paket bereitgestellt werden soll.

> [!IMPORTANT]
> Offboarding bewirkt, dass das Gerät das Senden von Sensordaten an das Portal beendet, aber Daten vom Gerät, einschließlich Verweis auf alle Warnungen, die es erhalten hat, werden für bis zu 6 Monate aufbewahrt.


## <a name="monitor-device-configuration"></a>Überwachen der Gerätekonfiguration

Wenn Sie den aktuellen Microsoft Endpoint Manager-Zweig verwenden, verwenden Sie das integrierte Defender for Endpoint-Dashboard in der Configuration Manager-Konsole. Weitere Informationen finden Sie unter [Defender for Endpoint - Monitor](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor).

Wenn Sie System Center 2012 R2 Configuration Manager verwenden, besteht die Überwachung aus zwei Teilen:

1. Bestätigen, dass das Konfigurationspaket ordnungsgemäß bereitgestellt wurde und auf den Geräten in Ihrem Netzwerk ausgeführt wird (oder erfolgreich ausgeführt wurde).

2. Überprüfen, ob die Geräte mit dem Defender for Endpoint-Dienst kompatibel sind (dadurch wird sichergestellt, dass das Gerät den Onboardingvorgang abschließen und weiterhin Daten an den Dienst melden kann).

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a>Bestätigen, dass das Konfigurationspaket ordnungsgemäß bereitgestellt wurde

1. Klicken Sie in der Configuration Manager-Konsole unten **im** Navigationsbereich auf Überwachung.

2. Wählen **Sie Übersicht** und dann **Bereitstellungen aus.**

3. Wählen Sie die Bereitstellung mit dem Paketnamen aus.

4. Überprüfen Sie die Statusindikatoren unter **Abschlussstatistik** und **Inhaltsstatus**.

    Bei fehlgeschlagenen Bereitstellungen (Geräte mit **Fehler,** **Nicht** erfüllten Anforderungen oder fehlgeschlagenen **Status)** müssen Sie möglicherweise Probleme mit den Geräten beheben. Weitere Informationen finden Sie unter [Troubleshoot Microsoft Defender for Endpoint onboarding issues](troubleshoot-onboarding.md).

    ![Configuration Manager zeigt eine erfolgreiche Bereitstellung ohne Fehler an](images/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-defender-for-endpoint-service"></a>Überprüfen, ob die Geräte mit dem Microsoft Defender for Endpoint-Dienst kompatibel sind

Sie können eine Complianceregel für das Konfigurationselement in System Center 2012 R2 Configuration Manager festlegen, um Ihre Bereitstellung zu überwachen.

Bei dieser Regel sollte es sich um ein Konfigurationselement *zur Nichtbehendung* der Complianceregel, das den Wert eines Registrierungsschlüssels auf zielgerichteten Geräten überwacht.

Überwachen Sie den folgenden Registrierungsschlüsseleintrag:

```console
Path: "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status"
Name: "OnboardingState"
Value: "1"
```

Weitere Informationen finden Sie [unter Einführung in Complianceeinstellungen in System Center 2012 R2 Configuration Manager](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\)).

## <a name="related-topics"></a>Verwandte Themen
- [Onboarding von Windows 10-Geräten mithilfe von Gruppenrichtlinien](configure-endpoints-gp.md)
- [Onboarding von Windows 10-Geräten mithilfe von Tools für die Verwaltung von Mobilgeräten](configure-endpoints-mdm.md)
- [Onboarding von Windows 10-Geräten mithilfe eines lokalen Skripts](configure-endpoints-script.md)
- [Onboarding von nicht-persistenten Geräten einer VD-Infrastruktur (Virtual Desktop)](configure-endpoints-vdi.md)
- [Ausführen eines Erkennungstests auf einem neu integrierten Microsoft Defender for Endpoint-Gerät](run-detection-test.md)
- [Behandeln von Problemen beim Onboarding von Microsoft Defender for Endpoint](troubleshoot-onboarding.md)
