---
title: Bereitstellen von Microsoft Defender ATP für Android mit Microsoft Intune
description: Beschreibt die Bereitstellung von Microsoft Defender ATP für Android mit Microsoft Intune
keywords: microsoft, defender, atp, android, installation, deploy, deinstallation,
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
ms.openlocfilehash: e557f60346b2f68354df621b6e4812eac775d812
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165669"
---
# <a name="deploy-microsoft-defender-for-endpoint-for-android-with-microsoft-intune"></a>Bereitstellen von Microsoft Defender for Endpoint für Android mit Microsoft Intune 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

Erfahren Sie, wie Sie Defender for Endpoint für Android auf registrierten Geräten des Intune-Unternehmensportals bereitstellen. Weitere Informationen zur Registrierung von Intune-Geräten finden Sie  [unter Registrieren Ihres Geräts](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal).

> [!NOTE]
> **Defender for Endpoint für Android ist jetzt auf [Google Play verfügbar.](https://play.google.com/store/apps/details?id=com.microsoft.scmx)** <br>
> Sie können von Intune aus eine Verbindung mit Google Play herstellen, um die Defender for Endpoint-App über geräteadministrator- und Android Enterprise-Entrollungsmodi bereitzustellen.
Updates für die App werden automatisch über Google Play angezeigt.

## <a name="deploy-on-device-administrator-enrolled-devices"></a>Bereitstellen auf vom Geräteadministrator registrierten Geräten

**Bereitstellen von Defender for Endpoint für Android im Intune-Unternehmensportal – Geräteadministrator registrierte Geräte**

Erfahren Sie, wie Sie Defender for Endpoint für Android im Intune-Unternehmensportal – Geräteadministrator registrierte Geräte bereitstellen. 

### <a name="add-as-android-store-app"></a>Hinzufügen als Android Store-App

1. Wechseln [Sie im Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431) zu **Apps** \> **Android Apps** Android store \> **\> app** hinzufügen, und wählen Sie **Auswählen aus.**

   ![Abbildung der Microsoft Endpoint Manager Admin Center hinzufügen Android Store-Anwendung](images/mda-addandroidstoreapp.png)

2. Geben Sie **auf der Seite** App hinzufügen und im Abschnitt *App-Informationen* ein: 

   - **Name** 
   - **Beschreibung**
   - **Publisher** als Microsoft.
   - **App Store-URL** als https://play.google.com/store/apps/details?id=com.microsoft.scmx (Defender for Endpoint-App Google Play Store-URL) 

   Andere Felder sind optional. Wählen Sie **Weiter** aus.

   ![Abbildung von Microsoft Endpoint Manager Admin Center add app info](images/mda-addappinfo.png)

3. Wechseln Sie *im Abschnitt Zuweisungen* zum Abschnitt **Erforderlich,** und wählen Sie **Gruppe hinzufügen aus.** Sie können dann die Benutzergruppen auswählen, für die Sie Defender for Endpoint für Android-App verwenden möchten. Wählen **Sie Auswählen** und dann Weiter **aus.**

    >[!NOTE]
    >Die ausgewählte Benutzergruppe sollte aus in Intune registrierten Benutzern bestehen.

    > [!div class="mx-imgBorder"]

    > ![Abbildung der ausgewählten Benutzergruppen im Microsoft Endpoint Manager Admin Center](images/363bf30f7d69a94db578e8af0ddd044b.png)

4. Überprüfen Sie **im Abschnitt Überprüfen+Erstellen,** ob alle eingegebenen Informationen korrekt sind, und wählen Sie dann **Erstellen aus.**

    In wenigen Momenten wurde die Defender for Endpoint-App erfolgreich erstellt, und eine Benachrichtigung wird oben rechts auf der Seite angezeigt.

    ![Abbildung der Microsoft Endpoint Manager Admin Center-Benachrichtigung der Defender-Endpunkt-App](images/86cbe56f88bb6e93e9c63303397fc24f.png)

5. Wählen Sie auf der angezeigten App-Informationsseite  im Abschnitt **Monitor** die Option Geräteinstallationsstatus aus, um sicherzustellen, dass die Geräteinstallation erfolgreich abgeschlossen wurde.

    > [!div class="mx-imgBorder"]
    > ![Abbildung der Installation von Microsoft Endpoint Manager Admin Center-Geräten](images/513cf5d59eaaef5d2b5bc122715b5844.png)

### <a name="complete-onboarding-and-check-status"></a>Vollständiger Onboarding- und Überprüfungsstatus

1. Sobald Defender for Endpoint für Android auf dem Gerät installiert wurde, wird das App-Symbol angezeigt.

    ![Symbol auf mobilem Gerät](images/7cf9311ad676ec5142002a4d0c2323ca.jpg)

2. Tippen Sie auf das Microsoft Defender ATP-App-Symbol, und befolgen Sie die Anweisungen auf dem Bildschirm, um das Onboarding der App zu abschließen. Die Details umfassen die Endbenutzerakzeptanz der von Defender for Endpoint für Android benötigten Android-Berechtigungen.

3. Nach dem erfolgreichen Onboarding wird das Gerät in der Liste Geräte im Microsoft Defender Security Center angezeigt.

    ![Abbildung des Geräts im Defender for Endpoint-Portal](images/9fe378a1dce0f143005c3aa53d8c4f51.png)

## <a name="deploy-on-android-enterprise-enrolled-devices"></a>Bereitstellen auf registrierten Android Enterprise-Geräten

Defender for Endpoint für Android unterstützt registrierte Android Enterprise-Geräte.

Weitere Informationen zu den von Intune unterstützten Registrierungsoptionen finden Sie unter [Registrierungsoptionen](https://docs.microsoft.com/mem/intune/enrollment/android-enroll).

**Zurzeit werden geräteeigene Geräte mit Geschäftsprofil und vollständig verwalteten Geräteregistrierungen im Besitz des Unternehmens für die Bereitstellung unterstützt.**

## <a name="add-microsoft-defender-for-endpoint-for-android-as-a-managed-google-play-app"></a>Hinzufügen von Microsoft Defender für Endpoint für Android als verwaltete Google Play-App

Führen Sie die folgenden Schritte aus, um Microsoft Defender for Endpoint-App zu Ihrer verwalteten Google Play hinzuzufügen.

1. Wechseln [Sie im Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431) zu Apps **Android** \> **Apps** \> **Add,** und wählen Sie **Verwaltete Google Play-App aus.**

    > [!div class="mx-imgBorder"]
    > ![Abbildung des verwalteten Google Play in Microsoft Endpoint Manager Admin Center](images/579ff59f31f599414cedf63051628b2e.png)

2. Wechseln Sie auf der verwalteten Google Play-Seite, die anschließend geladen wird, zum Suchfeld, und suchen Sie **Microsoft Defender.** Ihre Suche sollte die Microsoft Defender for Endpoint-App in Ihrer verwalteten Google Play anzeigen. Klicken Sie im Apps-Suchergebnis auf die Microsoft Defender for Endpoint-App.

    ![Abbildung der Microsoft Endpoint Manager Admin Center Apps-Suche](images/0f79cb37900b57c3e2bb0effad1c19cb.png)

3. Auf der Seite App-Beschreibung, die als Nächstes angezeigt wird, sollten Sie app-Details auf Defender for Endpoint anzeigen können. Überprüfen Sie die Informationen auf der Seite, und wählen Sie dann **Genehmigen aus.**

    > [!div class="mx-imgBorder"]
    > ![Screenshot eines verwalteten Google Play](images/07e6d4119f265037e3b80a20a73b856f.png)

4. Ihnen werden die Berechtigungen präsentiert, die Defender for Endpoint für die Arbeit erhält. Überprüfen Sie sie, und wählen Sie dann **Genehmigen aus.**

    ![Screenshot der Genehmigung der Defender for Endpoint-Vorschau-App](images/206b3d954f06cc58b3466fb7a0bd9f74.png)

5. Ihnen wird die Seite Genehmigungseinstellungen angezeigt. Die Seite bestätigt, dass Sie neue App-Berechtigungen behandeln möchten, die Defender for Endpoint für Android möglicherweise fordert. Überprüfen Sie die Auswahlmöglichkeiten, und wählen Sie Ihre bevorzugte Option aus. Wählen Sie **Fertig** aus.

    Standardmäßig wählt verwaltete Google Play die Option *Genehmigt bleiben aus, wenn App neue Berechtigungen anfordert*

    > [!div class="mx-imgBorder"]
    > ![Abbildung der Registerkarte "Benachrichtigungen"](images/ffecfdda1c4df14148f1526c22cc0236.png)

6. Nachdem die Auswahl für die Berechtigungsbehandlung getroffen wurde, wählen Sie **Synchronisieren** aus, um Microsoft Defender for Endpoint mit Ihrer Apps-Liste zu synchronisieren.

    > [!div class="mx-imgBorder"]
    > ![Abbildung der Synchronisierungsseite](images/34e6b9a0dae125d085c84593140180ed.png)

7. Die Synchronisierung wird in wenigen Minuten abgeschlossen.

    ![Abbildung der Android-App](images/9fc07ffc150171f169dc6e57fe6f1c74.png)

8. Wählen Sie **die Schaltfläche Aktualisieren** auf dem Bildschirm für Android-Apps aus, und Microsoft Defender ATP sollte in der Liste apps sichtbar sein.

    > [!div class="mx-imgBorder"]
    > ![Abbildung der Liste der Android-Apps](images/fa4ac18a6333335db3775630b8e6b353.png)

9. Defender for Endpoint unterstützt App-Konfigurationsrichtlinien für verwaltete Geräte über Intune. Diese Funktion kann verwendet werden, um anwendbare Android-Berechtigungen automatisch zugranaten, sodass der Endbenutzer diese Berechtigungen nicht akzeptieren muss.

    1. Wechseln Sie **auf** der Seite Apps zu **Richtlinien > App-Konfigurationsrichtlinien > Hinzufügen > verwalteten Geräten**.

       ![Abbildung der verwalteten Microsoft Endpoint Manager Admin Center-Android-Geräte](images/android-mem.png)

    1. Geben Sie auf der Seite **App-Konfigurationsrichtlinie erstellen** die folgenden Details ein:
    
        - Name: Microsoft Defender ATP.
        - Wählen **Sie Android Enterprise** als Plattform aus.
        - Wählen **Sie Arbeitsprofil nur als** Profiltyp aus.
        - Klicken **Sie auf App auswählen,** wählen Sie Microsoft Defender **ATP** aus, wählen **Sie OK** und dann Weiter **aus.**
    
        > [!div class="mx-imgBorder"]
        > ![Abbildung der Seite "App-Konfigurationsrichtlinie erstellen"](images/android-create-app.png)

    1. Wechseln Sie **auf** der Seite Einstellungen zum Abschnitt Berechtigungen, klicken Sie auf Hinzufügen, um die Liste der unterstützten Berechtigungen zu sehen. Wählen Sie im Abschnitt Berechtigungen hinzufügen die folgenden Berechtigungen aus:

       - Externer Speicher (Lesen)
       - Externer Speicher (Schreiben)

       Wählen Sie dann **OK** aus.

       > [!div class="mx-imgBorder"]
      > ![Abbildung der Android-App-Konfigurationsrichtlinie erstellen](images/android-create-app-config.png)

    1. Sie sollten nun sowohl die aufgeführten Berechtigungen als auch jetzt autogrant  sehen, indem Sie autogrant in der Dropdownliste Berechtigungsstatus auswählen und dann **Weiter auswählen.**

       > [!div class="mx-imgBorder"]
       > ![Abbildung der automatischen Android-Erteilung erstellen einer App-Konfigurationsrichtlinie](images/android-auto-grant.png)

    1. Wählen Sie **auf** der Seite Zuweisungen die Benutzergruppe aus, der diese App-Konfigurationsrichtlinie zugewiesen werden soll. Klicken **Sie auf Gruppen auswählen, um** die entsprechende Gruppe ein- und auszuwählen, und wählen Sie dann Weiter **aus.**  Die hier ausgewählte Gruppe ist in der Regel dieselbe Gruppe, der Sie Microsoft Defender for Endpoint Android App zuweisen würden. 

       > [!div class="mx-imgBorder"]
       > ![Abbildung der Konfigurationsrichtlinie für die App erstellen](images/android-select-group.png)
    

     1. Überprüfen Sie **auf der** Seite Überprüfen + Erstellen, die als Nächstes angezeigt wird, alle Informationen, und wählen Sie dann **Erstellen aus.** <br>
    
        Die App-Konfigurationsrichtlinie für Defender for Endpoint, in der die Speicherberechtigung automatischgraniert wird, wird nun der ausgewählten Benutzergruppe zugewiesen.

        > [!div class="mx-imgBorder"]
        > ![Image of android review create app config policy](images/android-review-create.png)


10. Wählen Sie in der Liste Eigenschaftenzuweisungen Bearbeiten die **Option Microsoft Defender ATP-App** \>  \>  \> **aus.**

    ![Abbildung der Liste der Apps](images/mda-properties.png)


11. Weisen Sie die App *einer* Benutzergruppe als erforderliche App zu. Es wird automatisch  während der nächsten Synchronisierung des Geräts über die Unternehmensportal-App im Arbeitsprofil installiert. Diese Zuordnung kann durchgeführt werden,  indem Sie zum Abschnitt Erforderliche Gruppe hinzufügen navigieren, die Benutzergruppe auswählen und \>  auf **Auswählen klicken.**

    > [!div class="mx-imgBorder"]
    > ![Abbildung der Seite "Anwendung bearbeiten"](images/ea06643280075f16265a596fb9a96042.png)


12. Überprüfen Sie **auf** der Seite Anwendung bearbeiten alle oben eingegebenen Informationen. Wählen Sie dann **Überprüfen + Speichern** und dann erneut **speichern** aus, um mit der Zuordnung zu beginnen.

### <a name="auto-setup-of-always-on-vpn"></a>Automatisches Einrichten von Always-On-VPN 
Defender for Endpoint unterstützt Gerätekonfigurationsrichtlinien für verwaltete Geräte über Intune. Diese Funktion kann für die automatische Einrichtung von **Always-on-VPN** auf registrierten Android Enterprise-Geräten genutzt werden, sodass der Endbenutzer beim Onboarding keinen VPN-Dienst einrichten muss.
1.  Wählen **Sie auf** Geräten **konfigurationsprofile** Profilplattform erstellen Android Enterprise Geräteeinschränkungen auswählen unter einer der folgenden Optionen aus, basierend auf Ihrem  >    >    >   Geräteregistrierungstyp  
- **Vollständig verwaltetes, dediziertes und Corporate-Owned Arbeitsprofil**
- **Persönliches Arbeitsprofil**

Wählen Sie **Erstellen** aus.
 
   > ![Abbildung des Gerätekonfigurationsprofils Erstellen](images/1autosetupofvpn.png)
    
2. **Konfigurationseinstellungen** Geben Sie **einen Namen und** eine Beschreibung **an,** um das Konfigurationsprofil eindeutig zu identifizieren. 

   > ![Abbildung des Gerätekonfigurationsprofils Name und Beschreibung](images/2autosetupofvpn.png)
   
 3. Wählen Sie **Konnektivität** aus, und konfigurieren Sie VPN:
- Aktivieren **Sie always-on VPN** Setup einen VPN-Client im Arbeitsprofil, um nach Möglichkeit automatisch eine Verbindung mit dem VPN herzustellen und wieder herzustellen. Auf einem bestimmten Gerät kann nur ein VPN-Client für das always-on-VPN konfiguriert werden. Stellen Sie daher sicher, dass nur eine always-on-VPN-Richtlinie auf einem einzelnen Gerät bereitgestellt ist. 
- Wählen **Sie** Benutzerdefiniertes in der Dropdownliste Benutzerdefiniertes VPN in diesem Fall Defender for Endpoint VPN aus, das zum Bereitstellen des Web Protection-Features verwendet wird. 
    > [!NOTE]
    > Die Microsoft Defender ATP-App muss auf dem Gerät des Benutzers installiert sein, damit die automatische Einrichtung dieses VPN funktioniert.

- Geben **Sie die Paket-ID** der Microsoft Defender ATP-App im Google Play Store ein. Für die Defender-App-URL https://play.google.com/store/apps/details?id=com.microsoft.scmx ist Paket-ID **com.microsoft.scmx**  
- **Sperrmodus** Nicht konfiguriert (Standard) 

     ![Abbildung des Gerätekonfigurationsprofils aktivieren Always-On-VPN](images/3autosetupofvpn.png)
   
4. **Zuordnung** Wählen Sie  **auf**   der Seite Zuweisungen die Benutzergruppe aus, der diese App-Konfigurationsrichtlinie zugewiesen werden soll. Klicken **Sie auf Gruppen auswählen,** um die entsprechende Gruppe ein- und auszuwählen, und klicken Sie dann auf **Weiter**. Die hier ausgewählte Gruppe ist in der Regel dieselbe Gruppe, der Sie Microsoft Defender for Endpoint Android App zuweisen würden. 

     ![Abbildung der Gerätekonfigurationsprofilzuweisung](images/4autosetupofvpn.png)

5. Überprüfen Sie **auf der** Seite Überprüfen + Erstellen, die als Nächstes angezeigt wird, alle Informationen, und wählen Sie dann **Erstellen aus.** Das Gerätekonfigurationsprofil wird nun der ausgewählten Benutzergruppe zugewiesen.    

    ![Abbildung des Gerätekonfigurationsprofils Überprüfen und Erstellen](images/5autosetupofvpn.png)

## <a name="complete-onboarding-and-check-status"></a>Vollständiger Onboarding- und Überprüfungsstatus

1. Bestätigen Sie den Installationsstatus von Microsoft Defender for Endpoint für Android, indem Sie auf **Geräteinstallationsstatus klicken.** Stellen Sie sicher, dass das Gerät hier angezeigt wird.

    > [!div class="mx-imgBorder"]
    > ![Abbildung des Geräteinstallationsstatus](images/900c0197aa59f9b7abd762ab2b32e80c.png)


2. Auf dem Gerät können Sie den Onboardingstatus überprüfen, indem Sie zum **Arbeitsprofil gehen.** Vergewissern Sie sich, dass Defender for Endpoint verfügbar ist und Dass Sie bei den persönlichen Geräten mit **Arbeitsprofil registriert sind.**  Wenn Sie auf einem vollständig verwalteten Gerät des Unternehmens registriert sind, verfügen Sie über ein einzelnes Profil auf dem Gerät, in dem Sie bestätigen **können,** dass Defender for Endpoint verfügbar ist.

    ![Abbildung der App auf mobilen Geräten](images/c2e647fc8fa31c4f2349c76f2497bc0e.png)

3. Wenn die App installiert ist, öffnen Sie die App, akzeptieren Sie die Berechtigungen, und das Onboarding sollte erfolgreich sein.

    ![Abbildung des mobilen Geräts mit der Microsoft Defender for Endpoint-App](images/mda-devicesafe.png)

4. In dieser Phase wird das Gerät erfolgreich in Defender for Endpoint für Android onboardiert. Sie können dies im [Microsoft Defender Security Center überprüfen,](https://securitycenter.microsoft.com) indem Sie zur Seite **Geräte** navigieren.

    ![Abbildung des Microsoft Defender for Endpoint-Portals](images/9fe378a1dce0f143005c3aa53d8c4f51.png)


## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über Microsoft Defender for Endpoint für Android](microsoft-defender-endpoint-android.md)
- [Konfigurieren von Microsoft Defender for Endpoint für Android-Features](android-configure.md)
