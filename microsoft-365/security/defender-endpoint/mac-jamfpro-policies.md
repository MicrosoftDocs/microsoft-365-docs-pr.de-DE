---
title: Einrichten der Microsoft Defender for Endpoint für macOS-Richtlinien in Jamf Pro
description: Informationen zum Einrichten von Microsoft Defender for Endpoint für macOS-Richtlinien in Jamf Pro
keywords: policies, microsoft, defender, Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 84d0b37632dc23615a37bbbd73c17fe509dedae5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934681"
---
# <a name="set-up-the-microsoft-defender-for-endpoint-on-macos-policies-in-jamf-pro"></a>Einrichten der Microsoft Defender for Endpoint für macOS-Richtlinien in Jamf Pro

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Defender for Endpoint auf Dem Mac](microsoft-defender-endpoint-mac.md)

Diese Seite führt Sie durch die Schritte, die Sie zum Einrichten von macOS-Richtlinien in Jamf Pro ausführen müssen.

Sie müssen die folgenden Schritte ausführen:

1. [Holen Sie sich das Microsoft Defender for Endpoint-Onboardingpaket](#step-1-get-the-microsoft-defender-for-endpoint-onboarding-package)

2. [Erstellen eines Konfigurationsprofils in Jamf Pro mithilfe des Onboardingpakets](#step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package)

3. [Konfigurieren von Microsoft Defender für Endpunkteinstellungen](#step-3-configure-microsoft-defender-for-endpoint-settings)

4. [Konfigurieren von Microsoft Defender for Endpoint-Benachrichtigungseinstellungen](#step-4-configure-notifications-settings)

5. [Konfigurieren von Microsoft AutoUpdate (MAU)](#step-5-configure-microsoft-autoupdate-mau)

6. [Gewähren des vollständigen Datenträgerzugriffs auf Microsoft Defender for Endpoint](#step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint)

7. [Genehmigen der Kernelerweiterung für Microsoft Defender for Endpoint](#step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint)

8. [Genehmigen von Systemerweiterungen für Microsoft Defender for Endpoint](#step-8-approve-system-extensions-for-microsoft-defender-for-endpoint)

9. [Konfigurieren der Netzwerkerweiterung](#step-9-configure-network-extension)

10. [Planen von Scans mit Microsoft Defender for Endpoint unter macOS](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp)

11. [Bereitstellen von Microsoft Defender for Endpoint unter macOS](#step-11-deploy-microsoft-defender-for-endpoint-on-macos)


## <a name="step-1-get-the-microsoft-defender-for-endpoint-onboarding-package"></a>Schritt 1: Erstellen des Microsoft Defender for Endpoint-Onboardingpakets

1. Navigieren [Sie im Microsoft Defender Security Center](https://securitycenter.microsoft.com )zu Einstellungen > **Onboarding**. 

2. Wählen Sie macOS als Betriebssystem und Mobile Device Management /Microsoft Intune als Bereitstellungsmethode aus.

    ![Abbildung von Microsoft Defender Security Center](images/onboarding-macos.png)

3. Wählen **Sie Onboardingpaket** herunterladen (WindowsDefenderATPOnboardingPackage.zip).

4. Extrahieren `WindowsDefenderATPOnboardingPackage.zip` .

5. Kopieren Sie die Datei an Ihren bevorzugten Speicherort. Zum Beispiel: `C:\Users\JaneDoe_or_JohnDoe.contoso\Downloads\WindowsDefenderATPOnboardingPackage_macOS_MDM_contoso\jamf\WindowsDefenderATPOnboarding.plist`.


## <a name="step-2-create-a-configuration-profile-in-jamf-pro-using-the-onboarding-package"></a>Schritt 2: Erstellen eines Konfigurationsprofils in Jamf Pro mithilfe des Onboardingpakets

1. Suchen Sie die `WindowsDefenderATPOnboarding.plist` Datei aus dem vorherigen Abschnitt.

   ![Abbildung der WindowsDefenderATPOnboarding-Datei](images/plist-onboarding-file.png)

 
2. Wählen Sie im Jamf Pro-Dashboard Neu **aus.**

    ![Abbildung des Erstellens eines neuen Jamf Pro-Dashboards](images/jamf-pro-configure-profile.png)

3. Geben Sie die folgenden Details ein:

   **Allgemein**
   - Name: MDATP-Onboarding für macOS
   - Beschreibung: MDATP EDR-Onboarding für macOS
   - Kategorie: Keine
   - Verteilungsmethode: Automatisch installieren
   - Ebene: Computerebene

4. Wählen **Sie unter & Benutzerdefinierte Einstellungen konfigurieren** **aus.**

    ![Abbildung der Konfiguration von Apps und benutzerdefinierten Einstellungen](images/jamfpro-mac-profile.png)

5. Wählen **Sie Datei hochladen (PLIST-Datei)** aus, und geben Sie dann unter Einstellung **Domäne** ein: `com.microsoft.wdav.atp` . 

    ![Abbildung der Jamfpro-Plist-Uploaddatei](images/jamfpro-plist-upload.png)

    ![Abbildung der Uploaddateieigenschaft Listendatei](images/jamfpro-plist-file.png)

7. Wählen **Sie Öffnen** aus, und wählen Sie die Onboardingdatei aus.

    ![Abbildung der Onboardingdatei](images/jamfpro-plist-file-onboard.png)

8. Wählen Sie **Hochladen** aus. 

    ![Abbildung des Hochladens der plist-Datei](images/jamfpro-upload-plist.png)


9. Wählen Sie die **Registerkarte Bereich** aus.

    ![Registerkarte "Bild des Bereichs"](images/jamfpro-scope-tab.png)

10. Wählen Sie die Zielcomputer aus.

    ![Abbildung von Zielcomputern](images/jamfpro-target-computer.png)

    ![Abbildung von Zielen](images/jamfpro-targets.png) 

11. Klicken Sie auf **Speichern**.

    ![Abbildung von Bereitstellungszielcomputern](images/jamfpro-deployment-target.png)

    ![Abbildung der ausgewählten Zielcomputer](images/jamfpro-target-selected.png)

12. Wählen Sie **Fertig** aus.

    ![Abbildung von Zielgruppencomputern](images/jamfpro-target-group.png)

    ![Liste der Konfigurationsprofile](images/jamfpro-configuration-policies.png)

## <a name="step-3-configure-microsoft-defender-for-endpoint-settings"></a>Schritt 3: Konfigurieren von Microsoft Defender für Endpunkteinstellungen

1.  Verwenden Sie die folgenden Microsoft Defender for Endpoint-Konfigurationseinstellungen:

    - enableRealTimeProtection
    - passiveMode
    
    >[!NOTE]
    >Nicht standardmäßig aktiviert, wenn Sie planen, einen Av eines Drittanbieters für macOS ausführen zu können, legen Sie ihn auf `true` fest.

    - Ausschlüsse
    - excludedPath
    - excludedFileExtension
    - excludedFileName
    - exclusionsMergePolicy
    - allowedThreats
    
    >[!NOTE]
    >EICAR befindet sich im Beispiel, wenn Sie einen Proof-of-Concept durchprobieren, entfernen Sie es insbesondere, wenn Sie EICAR testen.
        
    - disallowedThreatActions
    - potentially_unwanted_application
    - archive_bomb
    - cloudService
    - automaticSampleSubmission
    - tags
    - hideStatusMenuIcon
    
     Weitere Informationen finden Sie unter [Property list for Jamf configuration profile](mac-preferences.md#property-list-for-jamf-configuration-profile).

     ```XML
     <?xml version="1.0" encoding="UTF-8"?>
     <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
     <plist version="1.0">
     <dict>
         <key>antivirusEngine</key>
         <dict>
             <key>enableRealTimeProtection</key>
             <true/>
             <key>passiveMode</key>
             <false/>
             <key>exclusions</key>
             <array>
                 <dict>
                     <key>$type</key>
                     <string>excludedPath</string>
                     <key>isDirectory</key>
                     <false/>
                     <key>path</key>
                     <string>/var/log/system.log</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedPath</string>
                     <key>isDirectory</key>
                     <true/>
                     <key>path</key>
                     <string>/home</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedFileExtension</string>
                     <key>extension</key>
                     <string>pdf</string>
                 </dict>
                 <dict>
                     <key>$type</key>
                     <string>excludedFileName</string>
                     <key>name</key>
                     <string>cat</string>
                 </dict>
             </array>
             <key>exclusionsMergePolicy</key>
             <string>merge</string>
             <key>allowedThreats</key>
             <array>
                 <string>EICAR-Test-File (not a virus)</string>
             </array>
             <key>disallowedThreatActions</key>
             <array>
                 <string>allow</string>
                 <string>restore</string>
             </array>
             <key>threatTypeSettings</key>
             <array>
                 <dict>
                     <key>key</key>
                     <string>potentially_unwanted_application</string>
                     <key>value</key>
                     <string>block</string>
                 </dict>
                 <dict>
                     <key>key</key>
                     <string>archive_bomb</string>
                     <key>value</key>
                     <string>audit</string>
                 </dict>
             </array>
             <key>threatTypeSettingsMergePolicy</key>
             <string>merge</string>
         </dict>
         <key>cloudService</key>
         <dict>
             <key>enabled</key>
             <true/>
             <key>diagnosticLevel</key>
             <string>optional</string>
             <key>automaticSampleSubmission</key>
             <true/>
         </dict>
         <key>edr</key>
         <dict>
             <key>tags</key>
             <array>
                 <dict>
                     <key>key</key>
                     <string>GROUP</string>
                     <key>value</key>
                     <string>ExampleTag</string>
                 </dict>
             </array>
         </dict>
         <key>userInterface</key>
         <dict>
             <key>hideStatusMenuIcon</key>
             <false/>
         </dict>
     </dict>
     </plist>
     ```

2. Speichern Sie die Datei unter `MDATP_MDAV_configuration_settings.plist` .


3.  Wählen Sie im Jamf Pro-Dashboard Die Option **Allgemein aus.**

    ![Abbildung des neuen Jamf Pro-Dashboards](images/644e0f3af40c29e80ca1443535b2fe32.png)

4. Geben Sie die folgenden Details ein:

    **Allgemein**
    
    - Name: MDATP-MDAV-Konfigurationseinstellungen
    - Beschreibung:\<blank\>
    - Kategorie: Keine (Standard)
    - Verteilungsmethode: Automatisch installieren(Standard)
    - Ebene: Computerebene(Standard)

    ![Abbildung der MDATP-MDAV-Konfigurationseinstellungen](images/3160906404bc5a2edf84d1d015894e3b.png)

5. Wählen **Sie unter & Benutzerdefinierte Einstellungen konfigurieren** **aus.**

    ![Abbildung der App und benutzerdefinierter Einstellungen](images/e1cc1e48ec9d5d688087b4d771e668d2.png)

6. Wählen **Sie Datei hochladen (PLIST-Datei)** aus.

    ![Abbildung der Plistdatei für Konfigurationseinstellungen](images/6f85269276b2278eca4bce84f935f87b.png)

7. Geben **Sie unter Einstellungen Domäne** `com.microsoft.wdav` ein, und wählen Sie dann **PLIST-Datei hochladen aus.**

    ![Abbildung der Einstellungsdomäne für Konfigurationseinstellungen](images/db15f147dd959e872a044184711d7d46.png)

8. Wählen **Sie Datei auswählen aus.**

    ![Abbildung der Konfigurationseinstellungen Auswählen der Datei](images/526e978761fc571cca06907da7b01fd6.png)

9. Wählen Sie **MDATP_MDAV_configuration_settings.plist** aus, und wählen Sie dann **Öffnen aus.**

    ![Abbildung der mdatpmdav-Konfigurationseinstellungen](images/98acea3750113b8dbab334296e833003.png)

10. Wählen Sie **Hochladen** aus.

    ![Abbildung des Uploads von Konfigurationseinstellungen](images/0adb21c13206861ba9b30a879ade93d3.png)

    ![Abbildung des Bilds zum Hochladen von Konfigurationseinstellungen](images/f624de59b3cc86e3e2d32ae5de093e02.png)

    >[!NOTE]
    >Wenn Sie die Intune-Datei hochladen, erhalten Sie den folgenden Fehler:<br>
    >![Abbildung der Konfigurationseinstellungen intune-Dateiupload](images/8e69f867664668796a3b2904896f0436.png)


11. Klicken Sie auf **Speichern**. 

    ![Abbildung der Konfigurationseinstellungen Bild speichern](images/1b6b5a4edcb42d97f1e70a6a0fa48e3a.png)

12. Die Datei wird hochgeladen.

    ![Abbildung des hochgeladenen Bilds der Konfigurationseinstellungendatei](images/33e2b2a1611fdddf6b5b79e54496e3bb.png)

    ![Abbildung der hochgeladenen Konfigurationseinstellungendatei](images/a422e57fe8d45689227e784443e51bd1.png)

13. Wählen Sie die **Registerkarte Bereich** aus.

    ![Abbildung des Konfigurationseinstellungenbereichs](images/9fc17529e5577eefd773c658ec576a7d.png)

14. Wählen **Sie Contosos Computergruppe aus.** 

15. Wählen **Sie Hinzufügen** aus, und wählen Sie dann Speichern **aus.**

    ![Abbildung der Konfigurationseinstellungen addsav](images/cf30438b5512ac89af1d11cbf35219a6.png)

    ![Abbildung der Konfigurationseinstellungen Hinzufügen speichern](images/6f093e42856753a3955cab7ee14f12d9.png)

16. Wählen Sie **Fertig** aus. Das neue Konfigurationsprofil **wird angezeigt.**

    ![Abbildung des Konfigurationseinstellungen-Konfigurationsprofilbilds](images/dd55405106da0dfc2f50f8d4525b01c8.png)


## <a name="step-4-configure-notifications-settings"></a>Schritt 4: Konfigurieren von Benachrichtigungseinstellungen

Diese Schritte gelten für macOS 10.15 (Catalina) oder neuer.

1. Wählen Sie im Jamf Pro-Dashboard **Computer** und dann **Konfigurationsprofile aus.**

2. Klicken **Sie auf Neu,** und geben Sie die folgenden Details für Optionen **ein:**
    
    - Registerkarte **Allgemein**: 
        - **Name**: MDATP MDAV-Benachrichtigungseinstellungen
        - **Beschreibung**: macOS 10.15 (Catalina) oder neuer
        - **Kategorie**: Keine *(Standard)*
        - **Verteilungsmethode**: Automatisch installieren *(Standardeinstellung)*
        - **Ebene**: Computerebene *(Standard)*

        ![Abbildung des neuen MacOS-Konfigurationsprofilbildschirms](images/c9820a5ff84aaf21635c04a23a97ca93.png)

    - Registerkarte Benachrichtigungen, klicken **Sie auf Hinzufügen**, und geben Sie die folgenden Werte ein:
        - **Bundle-ID**: `com.microsoft.wdav.tray`
        - **Kritische Warnungen**: Klicken Sie auf **Deaktivieren.**
        - **Benachrichtigungen**: Klicken Sie auf **Aktivieren**
        - **Bannerbenachrichtigungstyp**: Wählen **Sie Include** und **Temporary** *(Standard) aus.*
        - **Benachrichtigungen auf dem Sperrbildschirm**: Klicken Sie auf **Ausblenden**
        - **Benachrichtigungen im Benachrichtigungscenter**: Klicken Sie auf **Anzeigen**
        - **Symbol der Badge-App**: Klicken Sie auf **Anzeigen**

        ![Abbildung der Konfigurationseinstellungen mdatpmdav-Benachrichtigungen](images/7f9138053dbcbf928e5182ee7b295ebe.png)

    - Registerkarte **Benachrichtigungen**, klicken **Sie auf** Weitere Zeit hinzufügen, scrollen Sie nach unten zu Neue **Benachrichtigungseinstellungen**
        - **Bundle-ID**: `com.microsoft.autoupdate2`
        - Konfigurieren der restlichen Einstellungen auf die gleichen Werte wie oben

        ![Abbildung der Konfigurationseinstellungen mdatpmdav-Benachrichtigungen mau](images/4bac6ce277aedfb4a674f2d9fcb2599a.png)

        Beachten Sie, dass Sie jetzt über zwei "Tabellen" mit Benachrichtigungskonfigurationen verfügen, eine für **Bundle-ID: com.microsoft.wdav.tray** und eine weitere für **Bundle-ID: com.microsoft.autoupdate2**. Während Sie Benachrichtigungseinstellungen nach Ihren Anforderungen konfigurieren können, müssen Bündel-IDs genau die gleichen wie zuvor beschrieben sein, und **die Option** Include muss für Benachrichtigungen **ein** **sein.**

3. Wählen Sie die **Registerkarte** Bereich aus, und wählen Sie **dann Hinzufügen aus.**

    ![Abbildung des Konfigurationseinstellungenbereichs hinzufügen](images/441aa2ecd36abadcdd8aed03556080b5.png)

4. Wählen **Sie Contosos Computergruppe aus.** 

5. Wählen **Sie Hinzufügen** aus, und wählen Sie dann Speichern **aus.**
    
    ![Abbildung der Konfigurationseinstellungen contoso machine grp save](images/09a275e321268e5e3ac0c0865d3e2db5.png)
    
    ![Abbildung der Konfigurationseinstellungen zum Speichern hinzufügen](images/4d2d1d4ee13d3f840f425924c3df0d51.png)

6. Wählen Sie **Fertig** aus. Das neue Konfigurationsprofil **wird angezeigt.**
    ![Abbildung der Konfigurationseinstellung fertig img](images/633ad26b8bf24ec683c98b2feb884bdf.png)

## <a name="step-5-configure-microsoft-autoupdate-mau"></a>Schritt 5: Konfigurieren von Microsoft AutoUpdate (MAU)

1. Verwenden Sie die folgenden Microsoft Defender for Endpoint-Konfigurationseinstellungen:

      ```XML
   <?xml version="1.0" encoding="UTF-8"?>
   <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
   <plist version="1.0">
   <dict>
    <key>ChannelName</key>
    <string>Current</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
   </dict>
   </plist>
   ```

2. Speichern Sie sie unter `MDATP_MDAV_MAU_settings.plist` .

3. Wählen Sie im Jamf Pro-Dashboard Die Option **Allgemein aus.** 

    ![Abbildung des allgemeinen Bilds der Konfigurationseinstellung](images/eaba2a23dd34f73bf59e826217ba6f15.png)

4. Geben Sie die folgenden Details ein:

    **Allgemein** 
    
    - Name: MDATP MDAV MAU-Einstellungen
    - Beschreibung: Microsoft AutoUpdate-Einstellungen für MDATP für macOS
    - Kategorie: Keine (Standard)
    - Verteilungsmethode: Automatisch installieren(Standard)
    - Ebene: Computerebene(Standard)

5. Wählen **Sie unter & Benutzerdefinierte Einstellungen konfigurieren** **aus.**

    ![Abbildung der App für Konfigurationseinstellungen und benutzerdefinierter Einstellungen](images/1f72e9c15eaafcabf1504397e99be311.png)

6. Wählen **Sie Datei hochladen (PLIST-Datei)** aus.

    ![Abbildung der Konfigurationseinstellung plist](images/1213872db5833aa8be535da57653219f.png)  

7. Geben **Sie unter Einstellung Domäne:** `com.microsoft.autoupdate2` ein, und wählen Sie dann **PLIST-Datei hochladen aus.**

    ![Abbildung der Konfigurationseinstellung pref domain](images/1213872db5833aa8be535da57653219f.png)

8. Wählen **Sie Datei auswählen aus.**

    ![Abbildung der Konfigurationseinstellung choosefile](images/335aff58950ce62d1dabc289ecdce9ed.png)

9. Wählen **MDATP_MDAV_MAU_settings.plist aus.**

    ![Abbildung der Konfigurationseinstellung mdatpmdavmau-Einstellungen](images/a26bd4967cd54bb113a2c8d32894c3de.png)

10. Wählen Sie **Hochladen** aus.
    ![Abbildung der Konfigurationseinstellung uplimage](images/4239ca0528efb0734e4ca0b490bfb22d.png)

    ![Abbildung der Konfigurationseinstellung uplimg](images/4ec20e72c8aed9a4c16912e01692436a.png)

11. Klicken Sie auf **Speichern**.

    ![Abbildung der Konfigurationseinstellung saveimg](images/253274b33e74f3f5b8d475cf8692ce4e.png)

12. Wählen Sie die **Registerkarte Bereich** aus.
   
     ![Abbildung der Bereichstabelle für Konfigurationseinstellungen](images/10ab98358b2d602f3f67618735fa82fb.png)

13. Klicken Sie auf **Hinzufügen**.
    
    ![Abbildung der Konfigurationseinstellung addimg1](images/56e6f6259b9ce3c1706ed8d666ae4947.png)

    ![Abbildung der Konfigurationseinstellung addimg2](images/38c67ee1905c4747c3b26c8eba57726b.png)

    ![Abbildung der Konfigurationseinstellung addimg3](images/321ba245f14743c1d5d51c15e99deecc.png)

14. Wählen Sie **Fertig** aus.
    
    ![Abbildung der Konfigurationseinstellung doneimage](images/ba44cdb77e4781aa8b940fb83e3c21f7.png)

## <a name="step-6-grant-full-disk-access-to-microsoft-defender-for-endpoint"></a>Schritt 6: Gewähren des vollständigen Festplattenzugriffs auf Microsoft Defender for Endpoint

1. Wählen Sie im Jamf Pro-Dashboard **Konfigurationsprofile aus.**

    ![Abbildung des Konfigurationseinstellungskonfigurationsprofils](images/264493cd01e62c7085659d6fdc26dc91.png)

2. Wählen Sie **+ Neu aus.** 

3. Geben Sie die folgenden Details ein:

    **Allgemein** 
    - Name: MDATP MDAV – Gewähren des vollständigen Festplattenzugriffs auf EDR und AV
    - Beschreibung: Unter macOS Catalina oder neuer wird das neue Richtliniensteuerelement für Datenschutzeinstellungen
    - Kategorie: Keine
    - Verteilungsmethode: Automatisch installieren
    - Ebene: Computerebene


    ![Abbildung der Konfigurationseinstellung allgemein](images/ba3d40399e1a6d09214ecbb2b341923f.png)

4. Wählen **Sie unter Richtliniensteuerelement Datenschutzeinstellungen konfigurieren** die Option Konfigurieren **aus.**

    ![Abbildung der Konfigurationsdatenschutzrichtliniensteuerung](images/715ae7ec8d6a262c489f94d14e1e51bb.png)

5. Geben **Sie unter Datenschutzeinstellungsrichtliniensteuerung** die folgenden Details ein:

    - Bezeichner: `com.microsoft.wdav`
    - Bezeichnertyp: Bundle-ID
    - Codeanforderung: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`


    ![Abbildung der Details der Datenschutzeinstellungsrichtlinien für Konfigurationseinstellungen](images/22cb439de958101c0a12f3038f905b27.png)

6. Wählen Sie **+ Hinzufügen** aus.

    ![Abbildung der Konfigurationseinstellung hinzufügen Systemrichtlinie alle Dateien](images/bd93e78b74c2660a0541af4690dd9485.png)

    - Unter App oder Dienst: Auf **SystemPolicyAllFiles festlegen**

    - Unter "Zugriff": Auf Zulassen **festlegen**

7. Wählen **Sie Speichern** aus (nicht unten rechts).

    ![Abbildung der Konfigurationseinstellung Speichern von Bildern](images/6de50b4a897408ddc6ded56a09c09fe2.png)

8. Klicken Sie auf `+` das Zeichen neben App **Access,** um einen neuen Eintrag hinzuzufügen.

    ![Abbildung des App-Zugriffs auf Konfigurationseinstellungen](images/tcc-add-entry.png)

9. Geben Sie die folgenden Details ein:

    - Bezeichner: `com.microsoft.wdav.epsext`
    - Bezeichnertyp: Bundle-ID
    - Codeanforderung: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

10. Wählen Sie **+ Hinzufügen** aus.

    ![Abbildung der Konfigurationseinstellung tcc epsext-Eintrag](images/tcc-epsext-entry.png)

    - Unter App oder Dienst: Auf **SystemPolicyAllFiles festlegen**

    - Unter "Zugriff": Auf Zulassen **festlegen**

11. Wählen **Sie Speichern** aus (nicht unten rechts).

    ![Abbildung der Konfigurationseinstellung tcc epsext image2](images/tcc-epsext-entry2.png)

12. Wählen Sie die **Registerkarte Bereich** aus.

    ![Abbildung des Konfigurationseinstellungsbereichs](images/2c49b16cd112729b3719724f581e6882.png)

13. Wählen Sie **+ Hinzufügen** aus.

    ![Abbildung der Konfigurationseinstellung addimage](images/57cef926d1b9260fb74a5f460cee887a.png)

14. Wählen **Sie Computergruppen** > **unter Gruppenname >** Wählen Sie **Contosos MachineGroup aus.** 

    ![Abbildung der Konfigurationseinstellung contoso machinegrp](images/368d35b3d6179af92ffdbfd93b226b69.png)

15. Klicken Sie auf **Hinzufügen**. 

16. Klicken Sie auf **Speichern**. 
    
17. Wählen Sie **Fertig** aus.
    
    ![Abbildung der Konfigurationseinstellung donimg](images/809cef630281b64b8f07f20913b0039b.png)
    
    ![Abbildung der Konfigurationseinstellung donimg2](images/6c8b406ee224335a8c65d06953dc756e.png)

Alternativ können Sie [fulldisk.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/fulldisk.mobileconfig) herunterladen und in JAMF-Konfigurationsprofile hochladen, wie unter [Deploying Custom Configuration Profiles using Jamf Pro beschrieben| Methode 2: Hochladen eines Konfigurationsprofils in Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).

## <a name="step-7-approve-kernel-extension-for-microsoft-defender-for-endpoint"></a>Schritt 7: Genehmigen der Kernelerweiterung für Microsoft Defender for Endpoint

> [!CAUTION]
> Apple Silicon (M1)-Geräte unterstützen KEXT nicht. Bei der Installation eines Konfigurationsprofils, das aus KEXT-Richtlinien besteht, wird auf diesen Geräten ein Fehler angezeigt.

1. Wählen Sie **in den Konfigurationsprofilen** **+ Neu aus.**

    ![Screenshot eines automatisch generierten Social Media-Beitrags Beschreibung](images/6c8b406ee224335a8c65d06953dc756e.png)

2. Geben Sie die folgenden Details ein:

    **Allgemein** 
    
    - Name: MDATP MDAV Kernel Extension
    - Beschreibung: MDATP-Kernelerweiterung (kext)
    - Kategorie: Keine
    - Verteilungsmethode: Automatisch installieren
    - Ebene: Computerebene

    ![Abbildung der Konfigurationseinstellungen mdatpmdav kernel](images/24e290f5fc309932cf41f3a280d22c14.png)

3. Wählen **Sie unter Configure Approved Kernel Extensions** die Option Configure **aus.**

    ![Image of configuration settings approved kernel ext](images/30be88b63abc5e8dde11b73f1b1ade6a.png)

   
4. Geben **Sie unter Genehmigte Kernelerweiterungen** die folgenden Details ein:

    - Anzeigename: Microsoft Corp.
    - Team-ID: UBF8T346G9

    ![Abbildung der Konfigurationseinstellungen für die Kernelerweiterung](images/39cf120d3ac3652292d8d1b6d057bd60.png)

5. Wählen Sie die **Registerkarte Bereich** aus.

    ![Abbildung des Bereichsregisterkartenbereichs für Konfigurationseinstellungen img](images/0df36fc308ba569db204ee32db3fb40a.png)

6. Wählen Sie **+ Hinzufügen** aus.

7. Wählen **Sie Computergruppen** > **unter Gruppenname >** Computergruppe von Contoso **aus.**

8. Wählen Sie **+ Hinzufügen** aus.

    ![Abbildung der Konfigurationseinstellungen Zum Hinzufügen von Bildern](images/0dde8a4c41110dbc398c485433a81359.png)

9. Klicken Sie auf **Speichern**.

    ![Abbildung der Konfigurationseinstellungen saveimag](images/0add8019b85a453b47fa5c402c72761b.png)

10. Wählen Sie **Fertig** aus.

    ![Abbildung der Konfigurationseinstellungen doneimag](images/1c9bd3f68db20b80193dac18f33c22d0.png)

Alternativ können Sie [kext.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/kext.mobileconfig) herunterladen und in JAMF-Konfigurationsprofile hochladen, wie [unter Deploying Custom Configuration Profiles using Jamf Pro beschrieben| Methode 2: Hochladen eines Konfigurationsprofils in Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).

## <a name="step-8-approve-system-extensions-for-microsoft-defender-for-endpoint"></a>Schritt 8: Genehmigen von Systemerweiterungen für Microsoft Defender for Endpoint

1. Wählen Sie **in den Konfigurationsprofilen** **+ Neu aus.**

    ![Screenshot eines automatisch generierten Social Media-Beitrags Beschreibung](images/6c8b406ee224335a8c65d06953dc756e.png)

2. Geben Sie die folgenden Details ein:

    **Allgemein**
    
    - Name: MDATP MDAV System Extensions
    - Beschreibung: MDATP-Systemerweiterungen
    - Kategorie: Keine
    - Verteilungsmethode: Automatisch installieren
    - Ebene: Computerebene

    ![Abbildung der Konfigurationseinstellungen sysext new prof](images/sysext-new-profile.png)

3. Wählen **Sie in Systemerweiterungen** **Konfigurieren aus.**

   ![Abbildung der Konfigurationseinstellungen sysext config](images/sysext-configure.png)

4. Geben **Sie unter Systemerweiterungen** die folgenden Details ein:

   - Anzeigename: Microsoft Corp. SystemErweiterungen
   - Systemerweiterungstypen: Zulässige Systemerweiterungen
   - Teambezeichner: UBF8T346G9
   - Zulässige Systemerweiterungen:
     - **com.microsoft.wdav.epsext**
     - **com.microsoft.wdav.netext**

    ![Abbildung der Konfigurationseinstellungen sysextconfig2](images/sysext-configure2.png)

5. Wählen Sie die **Registerkarte Bereich** aus.

    ![Abbildung des Bereichsimages für Konfigurationseinstellungen](images/0df36fc308ba569db204ee32db3fb40a.png)

6. Wählen Sie **+ Hinzufügen** aus.

7. Wählen **Sie Computergruppen** > **unter Gruppenname >** Computergruppe von Contoso **aus.**

8. Wählen Sie **+ Hinzufügen** aus.

   ![Abbildung der Konfigurationseinstellungen addima](images/0dde8a4c41110dbc398c485433a81359.png)

9. Klicken Sie auf **Speichern**.

   ![Abbildung des sysext-Bereichs der Konfigurationseinstellungen](images/sysext-scope.png)

10. Wählen Sie **Fertig** aus.

    ![Abbildung der Konfigurationseinstellungen sysext-final](images/sysext-final.png)

## <a name="step-9-configure-network-extension"></a>Schritt 9: Konfigurieren der Netzwerkerweiterung

Im Rahmen der Endpunkterkennungs- und -reaktionsfunktionen prüft Microsoft Defender for Endpoint auf macOS den Socketdatenverkehr und meldet diese Informationen an das Microsoft Defender Security Center-Portal. Mit der folgenden Richtlinie kann die Netzwerkerweiterung diese Funktionalität ausführen.

Diese Schritte gelten für macOS 10.15 (Catalina) oder neuer.

1. Wählen Sie im Jamf Pro-Dashboard **Computer** und dann **Konfigurationsprofile aus.**

2. Klicken **Sie auf Neu,** und geben Sie die folgenden Details für Optionen **ein:**

    - Registerkarte **Allgemein**: 
        - **Name**: Microsoft Defender ATP Network Extension
        - **Beschreibung**: macOS 10.15 (Catalina) oder neuer
        - **Kategorie**: Keine *(Standard)*
        - **Verteilungsmethode**: Automatisch installieren *(Standardeinstellung)*
        - **Ebene**: Computerebene *(Standard)*

    - Registerkarte **Inhaltsfilter**:
        - **Filtername**: Microsoft Defender ATP-Inhaltsfilter
        - **Bezeichner**: `com.microsoft.wdav`
        - **Dienstadresse**, **Organisation**, **Benutzername**, **Kennwort**, **Zertifikat** leer lassen (**Include** ist *nicht* ausgewählt)
        - **Filterreihenfolge**: Inspector
        - **Socketfilter**: `com.microsoft.wdav.netext`
        - **Festgelegte Anforderung des Socketfilters:**`identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
        - Lassen **Sie Netzwerkfilterfelder** leer (**Include** *ist nicht* ausgewählt)

        Beachten **Sie, dass Identifier**, **Socket Filter** und Socket Filter **Designated Requirement** genaue Werte wie oben angegeben.

        ![Abbildung der Konfigurationseinstellung mdatpmdav](images/netext-create-profile.png)

3. Wählen Sie die **Registerkarte Bereich** aus.

   ![Abbildung der Registerkarte "Sco"-Registerkarte "Konfigurationseinstellungen"](images/0df36fc308ba569db204ee32db3fb40a.png)

4. Wählen Sie **+ Hinzufügen** aus.

5. Wählen **Sie Computergruppen** > **unter Gruppenname >** Computergruppe von Contoso **aus.**

6. Wählen Sie **+ Hinzufügen** aus.

    ![Abbildung der Konfigurationseinstellungen adim](images/0dde8a4c41110dbc398c485433a81359.png)

7. Klicken Sie auf **Speichern**.

    ![Abbildung der Konfigurationseinstellungen savimg netextscop](images/netext-scope.png)

8. Wählen Sie **Fertig** aus.

    ![Abbildung der Konfigurationseinstellungen netextfinal](images/netext-final.png)

Alternativ können Sie [netfilter.mobileconfig](https://github.com/microsoft/mdatp-xplat/blob/master/macos/mobileconfig/profiles/netfilter.mobileconfig) herunterladen und in JAMF-Konfigurationsprofile hochladen, wie unter [Deploying Custom Configuration Profiles using Jamf Pro beschrieben| Methode 2: Hochladen eines Konfigurationsprofils in Jamf Pro](https://www.jamf.com/jamf-nation/articles/648/deploying-custom-configuration-profiles-using-jamf-pro).


## <a name="step-10-schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a>Schritt 10: Planen von Scans mit Microsoft Defender for Endpoint unter macOS
Befolgen Sie die Anweisungen unter [Planen von Scans mit Microsoft Defender for Endpoint unter macOS](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/mac-schedule-scan-atp).


## <a name="step-11-deploy-microsoft-defender-for-endpoint-on-macos"></a>Schritt 11: Bereitstellen von Microsoft Defender for Endpoint unter macOS

1. Navigieren Sie zu dem Ort, an dem Sie gespeichert `wdav.pkg` haben.

    ![Bild des Datei-Explorers wdav pkg](images/8dde76b5463047423f8637c86b05c29d.png)

2. Benennen Sie ihn in `wdav_MDM_Contoso_200329.pkg` um.

    ![Bild von Datei-Explorer1 wdavmdmpkg](images/fb2220fed3a530f4b3ef36f600da0c27.png)

3. Öffnen Sie das Jamf Pro-Dashboard.

    ![Abbildung der Konfigurationseinstellungen jamfpro](images/990742cd9a15ca9fdd37c9f695d1b9f4.png)

4. Wählen Sie Ihren Computer aus, und klicken Sie oben auf das Zahnradsymbol, und wählen Sie **dann Computerverwaltung aus.**

    ![Abbildung der Konfigurationseinstellungen compmgmt](images/b6d671b2f18b89d96c1c8e2ea1991242.png)

5. Wählen **Sie unter Pakete**+ Neu **aus.** 
    ![Ein Bild mit VogelBeschreibung automatisch generiertes Paket neu](images/57aa4d21e2ccc65466bf284701d4e961.png)

6. Geben **Sie unter Neues Paket** die folgenden Details ein:

    **Registerkarte Allgemein**
    - Anzeigename: Lassen Sie ihn vorerm leer. Da es zurückgesetzt wird, wenn Sie Ihr pkg auswählen.
    - Kategorie: Keine (Standard)
    - Filename: Choose File

    ![Abbildung der allgemeinen Registerkarte "Konfigurationseinstellungen"](images/21de3658bf58b1b767a17358a3f06341.png)

    Öffnen Sie die Datei, und zeigen Sie sie auf `wdav.pkg` oder `wdav_MDM_Contoso_200329.pkg` .
    
    ![Screenshot eines Computerbildschirms Beschreibung automatisch generiert](images/1aa5aaa0a387f4e16ce55b66facc77d1.png)

7. Klicken Sie auf **Öffnen**. Legen Sie **den Anzeigenamen** **auf Microsoft Defender Advanced Threat Protection und Microsoft Defender Antivirus .**

    **Manifestdatei** ist nicht erforderlich. Microsoft Defender for Endpoint funktioniert ohne Manifestdatei.
    
    **Registerkarte "Optionen"**<br> Behalten Sie die Standardwerte bei.

    **Registerkarte "Einschränkungen"**<br> Behalten Sie die Standardwerte bei.
    
     ![Abbildung der Registerkarte "Einschränkung der Konfigurationseinstellungen"](images/56dac54634d13b2d3948ab50e8d3ef21.png)
   
8. Klicken Sie auf **Speichern**. Das Paket wird in Jamf Pro hochgeladen. 

   ![Abbildung der Konfigurationseinstellungen Pack upl jamf pro](images/33f1ecdc7d4872555418bbc3efe4b7a3.png)

   Es kann einige Minuten dauern, bis das Paket für die Bereitstellung verfügbar ist.
   
   ![Abbildung der Konfigurationseinstellungen pack upl](images/1626d138e6309c6e87bfaab64f5ccf7b.png)

9. Navigieren Sie zur **Seite Richtlinien.**

    ![Abbildung von Konfigurationseinstellungen](images/f878f8efa5ebc92d069f4b8f79f62c7f.png)

10. Wählen **Sie + Neu** aus, um eine neue Richtlinie zu erstellen.

    ![Abbildung der neuen Richtlinie für Konfigurationseinstellungen](images/847b70e54ed04787e415f5180414b310.png)


11. Geben **Sie im Allgemeinen** die folgenden Details ein:

    - Anzeigename: MDATP Onboarding Contoso 200329 v100.86.92 oder höher

    ![Abbildung der Konfigurationseinstellungenmdatponboard ](images/625ba6d19e8597f05e4907298a454d28.png)

12. Wählen **Sie Wiederkehrendes Einchecken aus.** 
    
    ![Image of configuration settings recur checkin](images/68bdbc5754dfc80aa1a024dde0fce7b0.png)

  
13. Klicken Sie auf **Speichern**. 
 
14. Wählen **Sie Pakete > Konfigurieren aus.**
 
    ![Abbildung der Konfiguration von Konfigurationseinstellungen Pack konfigurieren](images/8fb4cc03721e1efb4a15867d5241ebfb.png)

15. Wählen Sie **die Schaltfläche** Hinzufügen neben Microsoft Defender Advanced Threat Protection und Microsoft Defender **Antivirus aus.**

    ![Abbildung der Konfigurationseinstellungen MDATP und MDA add](images/526b83fbdbb31265b3d0c1e5fbbdc33a.png)

16. Klicken Sie auf **Speichern**.

    ![Abbildung der Konfigurationseinstellungenavimg](images/9d6e5386e652e00715ff348af72671c6.png)

17. Wählen Sie die **Registerkarte Bereich** aus.  

    ![Abbildung der Konfigurationseinstellungen scptab](images/8d80fe378a31143db9be0bacf7ddc5a3.png)

18. Wählen Sie die Zielcomputer aus.

    ![Abbildung der Konfigurationseinstellungen tgtcomp](images/6eda18a64a660fa149575454e54e7156.png)

    **Scope**
    
    Klicken Sie auf **Hinzufügen**.
    
    ![Abbildung der Konfigurationseinstellungen ad1img](images/1c08d097829863778d562c10c5f92b67.png)

    ![Abbildung der Konfigurationseinstellungen ad2img](images/216253cbfb6ae738b9f13496b9c799fd.png)

    **Self-Service**
    
    ![Abbildung des Selfservice für Konfigurationseinstellungen](images/c9f85bba3e96d627fe00fc5a8363b83a.png)

19. Wählen Sie **Fertig** aus. 

    ![Abbildung der Konfigurationseinstellungen do1img](images/99679a7835b0d27d0a222bc3fdaf7f3b.png)

    ![Abbildung der Konfigurationseinstellungen do2img](images/632aaab79ae18d0d2b8e0c16b6ba39e2.png)




