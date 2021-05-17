---
title: Onboarding mithilfe des Microsoft Endpoint Configuration Manager
description: Erfahren Sie, wie Sie microsoft Defender for Endpoint mithilfe von Microsoft Endpoint Configuration Manager
keywords: Onboarding, Konfiguration, Bereitstellung, Bereitstellung, Endpunktkonfigurations-Manager, Microsoft Defender for Endpoint, Sammlungserstellung, Endpunkterkennungsantwort, Schutz der nächsten Generation, Reduzierung der Angriffsfläche, Microsoft Endpoint Configuration Manager
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 84273ce3e060eb86ee246a5cc6a8cae3cba743b5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934489"
---
# <a name="onboarding-using-microsoft-endpoint-configuration-manager"></a>Onboarding mithilfe des Microsoft Endpoint Configuration Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Dieser Artikel ist Teil des Bereitstellungshandbuchs und dient als Beispiel für ein Onboarding. 

Im Thema [Planning](deployment-strategy.md) wurden verschiedene Methoden zum Onboarding von Geräten in den Dienst bereitgestellt. In diesem Thema wird die Architektur der gemeinsamen Verwaltung behandelt. 

![Abbildung der cloudeigenen Architektur ](images/co-management-architecture.png)
 *Diagramm der Umgebungsarchitekturen*


Während Defender for Endpoint das Onboarding verschiedener Endpunkte und Tools unterstützt, werden diese in diesem Artikel nicht behandelt. Informationen zum allgemeinen Onboarding mit anderen unterstützten Bereitstellungstools und -methoden finden Sie unter [Onboarding overview](onboarding.md).



In diesem Thema werden Benutzer in den themen:
- Schritt 1: Onboarding Windows Geräte in den Dienst 
- Schritt 2: Konfigurieren von Defender for Endpoint-Funktionen

In diesem Onboardingleitfaden werden Sie durch die folgenden grundlegenden Schritte bei der Verwendung von Microsoft Endpoint Configuration Manager:
- **Erstellen einer Auflistung in Microsoft Endpoint Configuration Manager**
- **Konfigurieren von Microsoft Defender for Endpoint-Funktionen mithilfe Microsoft Endpoint Configuration Manager**

>[!NOTE]
>Nur Windows werden in dieser Beispielbereitstellung behandelt. 



## <a name="step-1-onboard-windows-devices-using-microsoft-endpoint-configuration-manager"></a>Schritt 1: Onboarding Windows Geräte mithilfe Microsoft Endpoint Configuration Manager

### <a name="collection-creation"></a>Sammlungserstellung
Zum Onboarding Windows 10 geräte mit Microsoft Endpoint Configuration Manager kann die Bereitstellung auf eine vorhandene Auflistung oder eine neue Sammlung zu Testzwecken erstellt werden. 

Beim Onboarding mithilfe von Tools wie Gruppenrichtlinien oder manuellen Methoden wird kein Agent auf dem System installiert. 

Innerhalb der Microsoft Endpoint Configuration Manager wird der Onboardingprozess als Teil der Kompatibilitätseinstellungen in der Konsole konfiguriert.

Jedes System, das diese erforderliche Konfiguration empfängt, wird diese Konfiguration beibehalten, solange der Configuration Manager-Client diese Richtlinie weiterhin vom Verwaltungspunkt empfängt. 

Führen Sie die folgenden Schritte aus, um Endpunkte mithilfe von Microsoft Endpoint Configuration Manager.

1. Navigieren Microsoft Endpoint Configuration Manager Konsole zu **Assets and Compliance Overview Device \> \> Collections**.            

    ![Abbildung des Microsoft Endpoint Configuration Manager Assistenten1](images/configmgr-device-collections.png)

2. Klicken Sie mit **der rechten Maustaste auf Gerätesammlung,** und wählen Sie **Gerätesammlung erstellen aus.**

    ![Abbildung des Microsoft Endpoint Configuration Manager-Assistenten2](images/configmgr-create-device-collection.png)

3. Geben Sie **einen Namen und** eine **Einschränkende Auflistung an,** und wählen Sie dann **Weiter aus.**

    ![Abbildung des Microsoft Endpoint Configuration Manager Assistenten3](images/configmgr-limiting-collection.png)

4. Wählen **Sie Regel hinzufügen** aus, und wählen Sie **Abfrageregel aus.**

    ![Abbildung des Microsoft Endpoint Configuration Manager Assistenten4](images/configmgr-query-rule.png)

5.  Klicken **Sie im** Assistenten für direkte **Mitgliedschaft** auf Weiter, und klicken Sie auf **Abfrageanweisung bearbeiten.**

     ![Abbildung des Microsoft Endpoint Configuration Manager Assistenten5](images/configmgr-direct-membership.png)

6. Wählen **Sie Kriterien** aus, und wählen Sie dann das Sternsymbol aus.

     ![Abbildung des Microsoft Endpoint Configuration Manager Assistenten6](images/configmgr-criteria.png)

7. Halten Sie den Kriterientyp als einfachen **Wert,** wählen  Sie als Betriebssystem **- Buildnummer**, Operator, größer oder gleich und Wert **14393** aus, und klicken Sie auf **OK**.

    ![Abbildung des Microsoft Endpoint Configuration Manager Assistenten7](images/configmgr-simple-value.png)

8. Wählen **Sie Weiter** und Schließen **aus.**

    ![Abbildung des Microsoft Endpoint Configuration Manager Assistenten8](images/configmgr-membership-rules.png)

9. Wählen Sie **Weiter** aus.

    ![Abbildung des Microsoft Endpoint Configuration Manager Assistenten9](images/configmgr-confirm.png)


Nachdem Sie diese Aufgabe abgeschlossen haben, verfügen Sie nun über eine Gerätesammlung mit allen Windows 10 endpunkten in der Umgebung. 


## <a name="step-2-configure-microsoft-defender-for-endpoint-capabilities"></a>Schritt 2: Konfigurieren von Microsoft Defender for Endpoint-Funktionen 
In diesem Abschnitt werden Sie beim Konfigurieren der folgenden Funktionen mithilfe von Microsoft Endpoint Configuration Manager auf Windows unterstützt:

- [**Erkennung und Reaktion am Endpunkt**](#endpoint-detection-and-response)
- [**Schutzlösungen der nächsten Generation**](#next-generation-protection)
- [**Reduzierung der Angriffsfläche**](#attack-surface-reduction)


### <a name="endpoint-detection-and-response"></a>Erkennung und Reaktion am Endpunkt
#### <a name="windows-10"></a>Windows 10
Innerhalb der Microsoft Defender Security Center ist es möglich, die Richtlinie ".onboarding" herunterzuladen, mit der die Richtlinie in System Center Configuration Manager erstellt und auf Windows 10 bereitgestellt werden kann.

1. Wählen Sie Microsoft Defender Security Center Portal Einstellungen [und dann Onboarding aus.](https://securitycenter.windows.com/preferences2/onboarding)



2. Wählen Sie unter Bereitstellungsmethode die unterstützte Version von **Microsoft Endpoint Configuration Manager**.

    ![Abbildung des Microsoft Defender for Endpoint-Onboarding-Assistenten10](images/mdatp-onboarding-wizard.png)

3. Wählen **Sie Paket herunterladen aus.**

    ![Abbildung des Microsoft Defender for Endpoint-Onboarding-Assistenten11](images/mdatp-download-package.png)

4. Speichern Sie das Paket an einem barrierefreien Speicherort.
5. Navigieren Microsoft Endpoint Configuration Manager zu: Assets **and Compliance > Overview > Endpoint Protection > Microsoft Defender ATP Policies**.

6. Klicken Sie mit **der rechten Microsoft Defender ATP auf Richtlinien,** und wählen Sie Microsoft Defender ATP Erstellen **aus.**

    ![Abbildung des Microsoft Endpoint Configuration Manager Assistenten12](images/configmgr-create-policy.png)

7. Geben Sie den Namen und die Beschreibung ein, überprüfen Sie, ob **onboarding** ausgewählt ist, und wählen Sie dann **Weiter aus.**

    ![Abbildung des Microsoft Endpoint Configuration Manager Assistenten13](images/configmgr-policy-name.png)


8. Klicken Sie auf **Durchsuchen**.

9. Navigieren Sie aus Schritt 4 oben zum Speicherort der heruntergeladenen Datei.

10. Klicken Sie auf **Weiter**.
11. Konfigurieren Sie den Agent mit den entsprechenden Beispielen (**Keine** oder **Alle Dateitypen**).

    ![Abbildung der Konfigurationseinstellungen1](images/configmgr-config-settings.png)

12. Wählen Sie die entsprechende Telemetrie (**Normal** oder **Expedited**) aus, und klicken Sie dann auf **Weiter**.

    ![Abbildung der Konfigurationseinstellungen2](images/configmgr-telemetry.png)

14. Überprüfen Sie die Konfiguration, und klicken Sie dann auf **Weiter**.

     ![Abbildung der Konfigurationseinstellungen3](images/configmgr-verify-configuration.png)

15. Klicken **Sie auf Schließen,** wenn der Assistent abgeschlossen ist.

16.  Klicken Sie Microsoft Endpoint Configuration Manager mit der rechten Maustaste auf die gerade erstellte Defender for Endpoint-Richtlinie, und wählen Sie **Bereitstellen aus.**

     ![Abbildung der Konfigurationseinstellungen4](images/configmgr-deploy.png)

17. Wählen Sie im rechten Bereich die zuvor erstellte Auflistung aus, und klicken Sie auf **OK**.

    ![Abbildung der Konfigurationseinstellungen5](images/configmgr-select-collection.png)


#### <a name="previous-versions-of-windows-client-windows-7-and-windows-81"></a>Frühere Versionen von Windows Client (Windows 7 und Windows 8.1)
Führen Sie die folgenden Schritte aus, um die Defender for Endpoint Workspace ID und den Arbeitsbereichsschlüssel zu identifizieren, die für das Onboarding früherer Versionen von Windows.

1. Wählen Sie Microsoft Defender Security Center Portal Einstellungen > **Onboarding aus.**

2. Wählen Sie unter Betriebssystem **Windows 7 SP1 und 8.1 aus.**

3. Kopieren Sie **die Arbeitsbereichs-ID** und **den Arbeitsbereichsschlüssel,** und speichern Sie sie. Sie werden später im Prozess verwendet.

    ![Abbildung des Onboardings](images/91b738e4b97c4272fd6d438d8c2d5269.png)

4. Installieren Sie Microsoft Monitoring Agent (MMA). <br>
    MMA wird derzeit (ab Januar 2019) auf den folgenden Betriebssystemen Windows unterstützt:

    -   Server-SKUs: Windows Server 2008 SP1 oder neuer

    -   Client-SKUs: Windows 7 SP1 und höher

    Der MMA-Agent muss auf Windows installiert werden. Zum Installieren des Agents müssen einige Systeme das [Update](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) für die Benutzererfahrung und die Diagnosetelemetrie herunterladen, um die Daten mit MMA zu erfassen. Diese Systemversionen umfassen u. U. folgende Versionen:

    -   Windows 8.1

    -   Windows 7

    -   Windows Server 2016

    -   Windows Server 2012 R2

    -   Windows Server 2008 R2

    Insbesondere für Windows 7 SP1 müssen die folgenden Patches installiert werden:

    -   Installieren [von KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)

    -   Installieren Sie [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (oder höher) **oder** 
         [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework).
        Installieren Sie beide nicht auf demselben System.

5. Wenn Sie einen Proxy zum Herstellen einer Verbindung mit dem Internet verwenden, lesen Sie den Abschnitt Konfigurieren von Proxyeinstellungen.

Sobald sie abgeschlossen sind, sollten integrierte Endpunkte innerhalb einer Stunde im Portal angezeigt werden.

### <a name="next-generation-protection"></a>Schutz der nächsten Generation 
Microsoft Defender Antivirus ist eine integrierte Lösung zur Bekämpfung von Schadsoftware, die Schutz der nächsten Generation für Desktops, tragbare Computer und Server bietet.

1. Navigieren Sie Microsoft Endpoint Configuration Manager in der Konsole zu Ressourcen und **\> Complianceübersicht \> Endpoint Protection \> Antischalwarerichtlinien,** und wählen Sie **Antischalwarerichtlinie erstellen aus.**

    ![Abbildung der Antischabschmierenrichtlinie](images/9736e0358e86bc778ce1bd4c516adb8b.png)

2. Wählen **Sie Geplante Scans**, **Scaneinstellungen**, **Standardaktionen**, **Echtzeitschutz** **,** Ausschlusseinstellungen , **Erweitert**, **Bedrohungsüberschreibungen**, Cloud **Protection Service-** und **Security Intelligence-Updates aus,** und wählen Sie **OK aus.**

    ![Abbildung des Schutzbereichs der nächsten Generation1](images/1566ad81bae3d714cc9e0d47575a8cbd.png)

    In bestimmten Branchen oder einigen ausgewählten Unternehmenskunden können bestimmte Anforderungen an die Konfiguration von Antivirus erfüllt sein.

  
    [Schnellscan im Vergleich zu vollständiger Überprüfung und benutzerdefinierter Überprüfung](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/scheduled-catch-up-scans-microsoft-defender-antivirus#quick-scan-versus-full-scan-and-custom-scan)

    Weitere Informationen finden Sie unter [Windows-Sicherheit Configuration Framework](https://docs.microsoft.com/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)
  
    ![Abbildung des Schutzbereichs der nächsten Generation2](images/cd7daeb392ad5a36f2d3a15d650f1e96.png)

    ![Abbildung des Schutzbereichs der nächsten Generation3](images/36c7c2ed737f2f4b54918a4f20791d4b.png)

    ![Abbildung des Schutzbereichs der nächsten Generation4](images/a28afc02c1940d5220b233640364970c.png)

    ![Abbildung des Schutzbereichs der nächsten Generation5](images/5420a8790c550f39f189830775a6d4c9.png)

    ![Abbildung des Schutzbereichs der nächsten Generation6](images/33f08a38f2f4dd12a364f8eac95e8c6b.png)

    ![Abbildung des Schutzbereichs der nächsten Generation7](images/41b9a023bc96364062c2041a8f5c344e.png)

    ![Abbildung des Schutzbereichs der nächsten Generation8](images/945c9c5d66797037c3caeaa5c19f135c.png)

    ![Abbildung des Schutzbereichs der nächsten Generation9](images/3876ca687391bfc0ce215d221c683970.png)

3. Klicken Sie mit der rechten Maustaste auf die neu erstellte Antischalwarerichtlinie, und wählen Sie **Bereitstellen aus.**

    ![Abbildung des Schutzbereichs der nächsten Generation10](images/f5508317cd8c7870627cb4726acd5f3d.png)

4. Wählen Sie die neue Antischalwarerichtlinie auf Ihre Windows 10 aus, und klicken Sie auf **OK**.

     ![Abbildung des Schutzbereichs der nächsten Generation11](images/configmgr-select-collection.png)

Nachdem Sie diese Aufgabe abgeschlossen haben, haben Sie die Windows Defender Antivirus.

### <a name="attack-surface-reduction"></a>Verringerung der Angriffsfläche
Die Angriffsflächenreduzierungssäule von Defender for Endpoint umfasst den Funktionssatz, der unter Exploit Guard verfügbar ist. Attack Surface Reduction (ASR)-Regeln, kontrollierter Ordnerzugriff, Netzwerkschutz und Exploit-Schutz. 

Alle diese Features bieten einen Überwachungsmodus und einen Blockmodus. Im Überwachungsmodus gibt es keine Auswirkungen auf endbenutzer. Es werden nur zusätzliche Telemetriedaten gesammelt und in der Microsoft Defender Security Center. Das Ziel einer Bereitstellung besteht in der schrittweisen Bewegung von Sicherheitssteuerelementen in den Blockmodus.

So legen Sie ASR-Regeln im Überwachungsmodus ein:

1. Navigieren Sie Microsoft Endpoint Configuration Manager in der Konsole zu Ressourcen und **\> Complianceübersicht \> Endpoint Protection Windows Defender Exploit \> Guard,** und wählen Sie **Exploit Guard-Richtlinie erstellen aus.**

   ![Abbildung der Microsoft Endpoint Configuration Manager Konsole0](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2.  Wählen Sie **Attack Surface Reduction aus.**
   

3. Legen Sie Regeln auf **Überwachung** und klicken Sie auf **Weiter**.


    ![Abbildung der Microsoft Endpoint Configuration Manager Konsole1](images/d18e40c9e60aecf1f9a93065cb7567bd.png)

4. Bestätigen Sie die neue Exploit Guard-Richtlinie, indem Sie auf **Weiter klicken.**

    ![Abbildung der Microsoft Endpoint Configuration Manager Konsole2](images/0a6536f2c4024c08709cac8fcf800060.png)

    
5. Klicken Sie nach dem Erstellen der Richtlinie auf **Schließen**.

    ![Abbildung der Microsoft Endpoint Configuration Manager Konsole3](images/95d23a07c2c8bc79176788f28cef7557.png)

    ![Abbildung der Microsoft Endpoint Manager Konsole1](images/95d23a07c2c8bc79176788f28cef7557.png)
   

6.  Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und wählen Sie **Bereitstellen aus.**
    
    ![Abbildung der Microsoft Endpoint Configuration Manager Konsole4](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. Zielen Sie die Richtlinie auf die neu erstellte Windows 10, und klicken Sie auf **OK**.

    ![Abbildung der Microsoft Endpoint Configuration Manager Konsole5](images/0ccfe3e803be4b56c668b220b51da7f7.png)

Nachdem Sie diese Aufgabe abgeschlossen haben, haben Sie jetzt erfolgreich DIE REGELN im Überwachungsmodus konfiguriert.  
  
Im Folgenden finden Sie weitere Schritte, um zu überprüfen, ob DIE REGELN ordnungsgemäß auf Endpunkte angewendet werden. (Dies kann einige Minuten dauern)


1. Navigieren Sie in einem Webbrowser zu <https://securitycenter.windows.com> .

2.  Wählen **Sie im linken** Menü Konfigurationsverwaltung aus.

3. Klicken **Sie im Bereich Angriffsoberflächenverwaltung** auf Gehe, um die Oberflächenverwaltung zu attackieren. 
    
    ![Abbildung der Angriffsoberflächenverwaltung](images/security-center-attack-surface-mgnt-tile.png)

4. Klicken **Sie auf der** Registerkarte Konfiguration in Berichten zu Attack surface reduction rules. Es zeigt eine Übersicht über die Konfiguration von ASR-Regeln und den Status von ASR-Regeln auf jedem Gerät.

    ![Screenshot von Berichten zu Angriffsflächenreduzierungsregeln1](images/f91f406e6e0aae197a947d3b0e8b2d0d.png)

5. Klicken Sie auf jedes Gerät, um Konfigurationsdetails der ASR-Regeln anzuzeigen.

    ![Ein Screenshot der Berichte über Angriffsflächenreduzierungsregeln2](images/24bfb16ed561cbb468bd8ce51130ca9d.png)

Weitere Informationen finden Sie unter [Optimize ASR rule deployment and detections.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-asr)  


#### <a name="set-network-protection-rules-in-audit-mode"></a>Festlegen von Netzwerkschutzregeln im Überwachungsmodus:
1. Navigieren Sie Microsoft Endpoint Configuration Manager in der Konsole zu Ressourcen und **\> Complianceübersicht \> Endpoint Protection Windows Defender Exploit \> Guard,** und wählen Sie **Exploit Guard-Richtlinie erstellen aus.**

    ![Screenshot System Center Configuration Manager1](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. Wählen Sie **Netzwerkschutz aus.**

3. Legen Sie die Einstellung auf **Überwachung** und klicken Sie auf **Weiter**. 

    ![Screenshot System Center Confirugatiom Manager2](images/c039b2e05dba1ade6fb4512456380c9f.png)

4. Bestätigen Sie die neue Exploit Guard-Richtlinie, indem Sie auf **Weiter klicken.**
    
    ![Screenshot Exploit GUard policy1](images/0a6536f2c4024c08709cac8fcf800060.png)

5. Klicken Sie nach dem Erstellen der Richtlinie auf **Schließen**.

    ![Screenshot Exploit-GUard-Richtlinie2](images/95d23a07c2c8bc79176788f28cef7557.png)

6. Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und wählen Sie **Bereitstellen aus.**

    ![A screenshot Microsoft Endpoint Configuration Manager1](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. Wählen Sie die Richtlinie für die neu erstellte Windows 10 aus, und wählen Sie **OK aus.**

    ![Screenshot Von Microsoft Endpoint Configuration Manager2](images/0ccfe3e803be4b56c668b220b51da7f7.png)



Nachdem Sie diese Aufgabe abgeschlossen haben, haben Sie Network Protection im Überwachungsmodus erfolgreich konfiguriert.

#### <a name="to-set-controlled-folder-access-rules-in-audit-mode"></a>So legen Sie Regeln für den kontrollierten Ordnerzugriff im Überwachungsmodus ein:

1. Navigieren Sie Microsoft Endpoint Configuration Manager in der Konsole zu Ressourcen und **\> Complianceübersicht \> Endpoint Protection Windows Defender Exploit \> Guard,** und wählen Sie **Exploit Guard-Richtlinie erstellen aus.**

    ![Screenshot von Microsoft Endpoint Configuration Manager3](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. Wählen **Sie Kontrollierter Ordnerzugriff aus.**
    
3. Legen Sie die Konfiguration auf **Überwachung und** klicken Sie auf **Weiter**.

    ![Screenshot von Microsoft Endpoint Configuration Manager4](images/a8b934dab2dbba289cf64fe30e0e8aa4.png)    
    
4. Bestätigen Sie die neue Exploit Guard-Richtlinie, indem Sie auf **Weiter klicken.**

    ![Screenshot von Microsoft Endpoint Configuration Manager5](images/0a6536f2c4024c08709cac8fcf800060.png)

5. Klicken Sie nach dem Erstellen der Richtlinie auf **Schließen**.

    ![Screenshot von Microsoft Endpoint Configuration Manager6](images/95d23a07c2c8bc79176788f28cef7557.png)

6. Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und wählen Sie **Bereitstellen aus.**

    ![Screenshot von Microsoft Endpoint Configuration Manager7](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7.  Zielen Sie die Richtlinie auf die neu erstellte Windows 10, und klicken Sie auf **OK**.

    ![Screenshot von Microsoft Endpoint Configuration Manager8](images/0ccfe3e803be4b56c668b220b51da7f7.png)

Sie haben nun den kontrollierten Ordnerzugriff im Überwachungsmodus erfolgreich konfiguriert.

## <a name="related-topic"></a>Verwandtes Thema
- [Onboarding mithilfe des Microsoft Endpoint Manager](onboarding-endpoint-manager.md)
