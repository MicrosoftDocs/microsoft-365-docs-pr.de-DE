---
title: Erste Schritte mit der Microsoft Compliance Erweiterung
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Vorbereitung und Bereitstellung der Microsoft Compliance Erweiterung.
ms.openlocfilehash: 084d8fea1bffb012b4a4685dd28ec93df8e29b19
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730510"
---
# <a name="get-started-with-microsoft-compliance-extension"></a>Erste Schritte mit der Microsoft Compliance Erweiterung

Verwenden Sie diese Verfahren, um die Microsoft Compliance Erweiterung auszurollen.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Um Microsoft Compliance Erweiterung zu verwenden, muss das Gerät in Endpunkt-DLP eingebunden sein. Lesen Sie diese Artikel, wenn Sie neu im Bereich DLP oder Endpunkt-DLP sind

- [Erfahren Sie mehr über die Microsoft Compliance Erweiterung](dlp-chrome-learn-about.md)
- [Informationen zur Verhinderung von Datenverlust](dlp-learn-about-dlp.md)
- [Erstellen, Testen und Optimieren einer DLP-Richtlinie](create-test-tune-dlp-policy.md)
- [Erstellen einer DLP-Richtlinie aus einer Vorlage](create-a-dlp-policy-from-a-template.md)
- [Informationen zur Verhinderung von Datenverlust am Endpunkt](endpoint-dlp-learn-about.md)
- [Verhinderung von Datenverlust am Endpunkt – Erste Schritte](endpoint-dlp-getting-started.md)
- [Onboarding-Tools und -Methoden für Windows 10-Computer](dlp-configure-endpoints.md)
- [Konfigurieren von Geräteproxy- und Internetverbindungseinstellungen für die Verhinderung von Datenverlust am Endpunkt](endpoint-dlp-configure-proxy.md)
- [Nutzen der Verhinderung von Datenverlust am Endpunkt](endpoint-dlp-using.md)

### <a name="skusubscriptions-licensing"></a>SKU/Abonnement-Lizenzierung

Bevor Sie loslegen, sollten Sie Ihr [Microsoft 365-Abonnement](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) und alle Add-Ons bestätigen. Für den Zugriff auf und die Verwendung von Endpunkt-DLP-Funktionen müssen Sie über eines der folgenden Abonnements oder Add-Ons verfügen.

- Microsoft 365 E5
- Microsoft 365 A5 (EDU)
- Microsoft 365 E5 Compliance
- Microsoft 365 A5 Compliance
- Microsoft 365 E5 Information Protection und Governance
- Microsoft 365 A5 Information Protection und Governance

Ausführliche Informationen zur Lizenzierung finden Sie unter: [Microsoft 365-Lizenzierungsrichtlinien für Sicherheit und Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).

- Ihre Organisation muss für Endpoint-DLP lizenziert sein
- Auf Ihren Geräten muss Windows 10 x64 Build 1809 oder höher ausgeführt werden.
- Auf dem Gerät muss die Antimalware Client Version 4.18.2101.9 oder höher sein. Überprüfen Sie die aktuelle Version, indem Sie die **Windows-Sicherheits**-App öffnen, das Symbol **Einstellungen** und dann **Info** auswählen.


### <a name="permissions"></a>Berechtigungen

Endpunkt-DLP-Daten können im [Aktivitäten-Explorer](data-classification-activity-explorer.md) angezeigt werden. Es gibt sieben Rollen, die Berechtigungen für den Aktivitäten-Explorer gewähren. Das Konto, das Sie für den Zugriff auf die Daten verwenden, muss Mitglied einer dieser Rollen sein.

- Globaler Administrator
- Compliance-Administrator
- Sicherheitsadministrator
- Compliancedaten-Administrator
- Globale Leseberechtigung
- Benutzer mit Leseberechtigung für Sicherheitsfunktionen
- Berichtleseberechtigter

### <a name="overall-installation-workflow"></a>Gesamter Installationsablauf

Die Bereitstellung der Microsoft Compliance-Erweiterung ist ein mehrstufiger Prozess. Sie können sich für die Installation auf einem Computer entscheiden oder Microsoft Endpoint Manager oder Gruppenrichtlinien für organisationsweite Bereitstellungen verwenden.

1. [Bereiten Sie Ihre Geräte vor](#prepare-your-devices).
2. [Grundlegende Einrichtung Einzel Computer Selfhost](#basic-setup-single-machine-selfhost)
3. [Bereitstellen mit Microsoft Endpoint Manager](#deploy-using-microsoft-endpoint-manager)
4. [Bereitstellen über Gruppenrichtlinie](#deploy-using-group-policy)
5. [Testen der Erweiterung](#test-the-extension)
6. [Verwenden Sie das Verwaltung von Benachrichtigungen Dashboard, um Chrome DLP-Benachrichtigungen anzuzeigen](#use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts)
7. [Anzeigen von Chrome-DLP-Daten im Aktivitäten-Explorer](#viewing-chrome-dlp-data-in-activity-explorer)  

### <a name="prepare-infrastructure"></a>Infrastruktur vorbereiten

Wenn Sie die Microsoft Compliance Erweiterung auf alle Ihre überwachten Windows 10-Geräte ausrollen, sollten Sie Google Chrome aus der Liste der nicht zugelassenen Apps und unerlaubten Browser entfernen. Weitere Informationen finden Sie unter [Unerlaubte Browser](endpoint-dlp-using.md#unallowed-browsers). Wenn Sie es nur auf einige wenige Geräte ausrollen, können Sie Chrome auf der Liste der unerlaubten Browser oder nicht zugelassenen App belassen. Die Microsoft Compliance Erweiterung umgeht die Beschränkungen beider Listen für die Computer, auf denen sie installiert ist.  

### <a name="prepare-your-devices"></a>Bereiten Sie Ihre Geräte vor

1. Verwenden Sie die Verfahren in diesen Topics, um Ihre Geräte zu integrieren:
    1. [Verhinderung von Datenverlust am Endpunkt – Erste Schritte](endpoint-dlp-getting-started.md)
    1. [Onboarding-Tools und -Methoden für Windows 10-Computer](dlp-configure-endpoints.md)
    1. [Konfigurieren von Geräteproxy- und Internetverbindungseinstellungen für die Verhinderung von Datenverlust am Endpunkt](endpoint-dlp-configure-proxy.md)

### <a name="basic-setup-single-machine-selfhost"></a>Grundlegende Einrichtung Einzel Computer Selfhost

Diese Methode wird empfohlen. 

1. Melden Sie sich an dem Windows 10-Computer an, auf dem Sie die Microsoft Compliance Erweiterung installieren möchten, und führen Sie das PowerShell-Skript als Administrator aus. 

   ```powershell
   Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
   ``` 

2.  [Navigieren Sie zu Microsoft Compliance Erweiterung- Chrome Web Store (google.com)](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco).

3.  Installieren Sie die Erweiterung anhand der Anweisungen auf der Seite des Chrome Web Store.

### <a name="deploy-using-microsoft-endpoint-manager"></a>Bereitstellen mit Microsoft Endpoint Manager

Verwenden Sie diese Einrichtungsmethode für organisationsweite Bereitstellungen.


##### <a name="enabling-required-registry-key-via-microsoft-endpoint-manager"></a>Erforderlichen Registrierungsschlüssel über Microsoft Endpoint Manager aktivieren

1.  Erstellen Sie ein PowerShell-Skript mit dem folgenden Inhalt:

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

2.  Melden Sie sich beim [Microsoft Endpoint Manager Admin Center](https://endpoint.microsoft.com) an.

3.  Navigieren Sie zu **Geräte** > **-Skripte** und wählen Sie **Hinzufügen**.

4.  Navigieren Sie zu dem Speicherort des erstellten Skripts, wenn Sie dazu aufgefordert werden.

5.  Wählen Sie die folgenden Einstellungen aus:
    1. Führen Sie dieses Skript mit den angemeldeten Anmeldedaten aus: JA
    1. Skript-Signaturprüfung erzwingen: NEIN
    1. Skript in 64-Bit-PowerShell-Host ausführen: JA

6.  Wählen Sie die richtigen Gerätegruppen aus und wenden Sie die Richtlinie an.

#### <a name="microsoft-endpoint-manager-force-install-steps"></a>Microsoft Endpoint Manager Schritte zur erzwungenen Installation

Bevor Sie die Microsoft Compliance Erweiterung in die Liste der zwangsinstallierten Erweiterungen aufnehmen, ist es wichtig, das Chrome-ADMX einzulesen. Die Schritte für diesen Vorgang im Microsoft Endpoint Manager werden von Google dokumentiert: [Verwalten des Chrome-Browsers mit Microsoft Intune – Google Chrome Enterprise-Hilfe](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune).

 Nach dem Einlesen des ADMX können die folgenden Schritte ausgeführt werden, um ein Konfigurationsprofil für diese Erweiterung zu erstellen.

1.  Melden Sie sich beim Microsoft Endpoint Manager Admin Center an (https://endpoint.microsoft.com).

2.  Navigieren Sie zu den Konfigurationsprofilen.

3.  Wählen Sie **Profil erstellen**.

4.  Wählen Sie **Windows 10** als Plattform aus.

5.  Wählen Sie **Benutzerdefiniert** als Profiltyp.

6.  Wählen Sie die Registerkarte **Einstellungen**.

7.  Klicken Sie auf **Hinzufügen**.

8.  Geben Sie die folgenden Richtlinieninformationen ein.
    
    OMA-URI: `./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist`<br/>
    Datentyp: `String`<br/>
    Wert: `<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx"/>`

9.  Klicken Sie auf Erstellen.

### <a name="deploy-using-group-policy"></a>Bereitstellen über Gruppenrichtlinie

Wenn Sie Microsoft Endpoint Manager nicht verwenden möchten, können Sie Gruppenrichtlinien verwenden, um die Microsoft Compliance Erweiterung in Ihrem Unternehmen bereitzustellen

1. Ihre Geräte müssen über Gruppenrichtlinien verwaltbar sein, und Sie müssen alle Chrome-ADMXs in den zentralen Gruppenrichtlinienspeicher importieren. Weitere Informationen finden Sie unter [Erstellen und Verwalten des zentralen Speichers für administrative Gruppenrichtlinienvorlagen in Windows](https://docs.microsoft.com/troubleshoot/windows-client/group-policy/create-and-manage-central-store).

2.  Erstellen Sie ein PowerShell-Skript mit diesem PowerShell -Befehl:

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

3.  Öffnen Sie die **Gruppenrichtlinien-Verwaltungskonsole** und navigieren Sie zu Ihrer Organisationseinheit (OU).

4.  Klicken Sie mit der rechten Maustaste und wählen Sie **GPO in dieser Domäne erstellen und hier verlinken**. Wenn Sie dazu aufgefordert werden, geben Sie diesem Gruppenrichtlinienobjekt (GPO) einen beschreibenden Namen und schließen Sie die Erstellung ab.

5.  Klicken Sie mit der rechten Maustaste auf das GPO und wählen Sie **Bearbeiten**.

6.  Gehen Sie zu **Computerkonfiguration** > **Einstellungen** > **Systemsteuerung Einstellungen** > **Geplante Tasks**.

7.  Erstellen Sie eine neue Sofortaufgabe, indem Sie mit der rechten Maustaste klicken und **Neue** > **Sofortaufgabe wählen (mindestens Windows 7)**.

8.  Geben Sie der Aufgabe einen Namen und eine Beschreibung.

9.  Wählen Sie das entsprechende Konto, um die Sofortaufgabe auszuführen, z. B. NT Authority

10. Wählen Sie **Ausführen mit höchsten Rechten**.

11. Konfigurieren Sie die Richtlinie für Windows 10.

12. Wählen Sie auf der Registerkarte **Aktionen** die Aktion **Programm starten**.

13. Geben Sie den Pfad zu dem in Schritt 1 erstellten Programm/Skript ein.

14. Wählen Sie **Anwenden** aus.

#### <a name="adding-the-chrome-extension-to-the-forceinstall-list"></a>Hinzufügen der Chrome-Erweiterung zur ForceInstall-Liste

1.  Navigieren Sie im Gruppenrichtlinien-Verwaltungseditor zu Ihrer OU.

2.  Erweitern Sie den folgenden Pfad **Computer-/Benutzerkonfiguration** > **Richtlinien** > **Administrative Vorlagen** > **Klassische administrative Vorlagen** > **Google** > **Google Chrome** > **Erweiterungen**. Dieser Pfad kann je nach Ihrer Konfiguration variieren.

3.  Wählen Sie **Liste der zwangsinstallierten Erweiterungen konfigurieren**.

4.  Klicken Sie mit der rechten Maustaste und wählen Sie **Bearbeiten**.

5.  Wählen Sie **Aktiviert** aus.

6.  Wählen Sie **Anzeigen** aus.

7.  Fügen Sie unter **Wert** den folgenden Eintrag hinzu: `echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx`

8.  Wählen Sie **OK** und dann **Anwenden**.

### <a name="test-the-extension"></a>Testen der Erweiterung

#### <a name="upload-to-cloud-service-or-access-by-unallowed-browsers-cloud-egress"></a>Zum Cloud-Dienst hochladen oder Zugriff durch nicht zugelassene Browser Cloud Egress  

1. Ein vertrauliches Element erstellen oder beziehen und versuchen, eine Datei in eine der eingeschränkten Dienstdomänen Ihres Unternehmens hochzuladen. Die vertraulichen Daten müssen einem unserer eingebauten [Typen vertraulicher Informationen](sensitive-information-type-entity-definitions.md) oder einem der Typ vertraulicher Informationen Ihrer Organisation entsprechen. Sie sollten auf dem Gerät, von dem aus Sie testen, eine DLP-Popupbenachrichtigung erhalten, die anzeigt, dass diese Aktion nicht erlaubt ist, wenn die Datei geöffnet ist.

#### <a name="testing-other-dlp-scenarios-in-chrome"></a>Testen anderer DLP-Szenarien in Chrome 

Nachdem Sie nun Chrome aus der Liste der nicht zugelassenen Browser/Apps entfernt haben, können Sie die folgenden Szenarien testen, um zu bestätigen, dass das Verhalten den Anforderungen Ihrer Organisation entspricht:

- Daten aus einem vertraulichem Element in ein anderes Dokument über die Zwischenablage kopieren
    - Öffnen Sie zum Testen eine Datei, die gegen Aktionen von Kopieren in die Zwischenablage geschützt ist, im Chrome-Browser und versuchen Sie, Daten aus der Datei zu kopieren.
    - Erwartetes Ergebnis: Eine DLP-Popupbenachrichtigung, die anzeigt, dass diese Aktion nicht erlaubt ist, wenn die Datei geöffnet ist.
- Drucken eines Dokuments
    - Öffnen Sie zum Testen eine Datei, die gegen Druckaktionen geschützt ist, im Chrome-Browser und versuchen Sie, die Datei zu drucken.
    - Erwartetes Ergebnis: Eine DLP-Popupbenachrichtigung, die anzeigt, dass diese Aktion nicht erlaubt ist, wenn die Datei geöffnet ist.
- Auf USB-Wechseldatenträger kopieren
    - Versuchen Sie zum Test, die Datei auf einem Wechselmedium zu speichern.
    - Erwartetes Ergebnis: Eine DLP-Popupbenachrichtigung, die anzeigt, dass diese Aktion nicht erlaubt ist, wenn die Datei geöffnet ist.
- Auf Netzwerkfreigabe kopieren
    - Versuchen Sie zum Test, die Datei auf einer Netzwerkfreigabe zu speichern.
    - Erwartetes Ergebnis: Eine DLP-Popupbenachrichtigung, die anzeigt, dass diese Aktion nicht erlaubt ist, wenn die Datei geöffnet ist.


### <a name="use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts"></a>Verwenden Sie das Verwaltung von Benachrichtigungen Dashboard, um Chrome DLP-Benachrichtigungen anzuzeigen

1. Öffnen Sie die **Seite zur Verhinderung von Datenverlust** im [Microsoft 365 Compliance Center](https://compliance.microsoft.com) und wählen Sie **Benachrichtigungen** aus.

2. Wenden Sie in [Konfigurieren und Anzeigen von Benachrichtigungen für DLP-Richtlinien](dlp-configure-view-alerts-policies.md) beschriebenen Verfahrensweisen an, um Benachrichtigungen für Ihre Endpunkt-DLP-Richtlinien anzuzeigen.


### <a name="viewing-chrome-dlp-data-in-activity-explorer"></a>Anzeigen von Endpunkt-DLP-Daten im Aktivitäten-Explorer

1. Öffnen Sie im Microsoft 365 Compliance Center die Seite [Datenklassifizierung](https://compliance.microsoft.com/dataclassification?viewid=overview) für Ihre Domäne, und wählen Sie den **Aktivitäten-Explorer** aus.

2. Unter [Erste Schritte mit dem Aktivitäten-Explorer](data-classification-activity-explorer.md) erfahren Sie Näheres dazu, wie Sie auf alle Daten zu Ihren Endpunktgeräten zugreifen und diese filtern können.

   > [!div class="mx-imgBorder"]
   > ![Aktivitäten-Explorer-Filter für Endpunktgeräte](../media/endpoint-dlp-4-getting-started-activity-explorer.png)

### <a name="known-issues-and-limitations"></a>Bekannte Probleme und Einschränkungen

1. Die Erzwingung der Außerkraftsetzung von Sperren für den Cloudausgang wird nicht unterstützt.
2. Der Inkognito-Modus wird nicht unterstützt und muss deaktiviert werden.

## <a name="next-steps"></a>Nächste Schritte
Jetzt, da Geräte eingebunden sind und entsprechende Aktivitätsdaten im Aktivitäten-Explorer angezeigt werden, können Sie mit dem nächsten Schritt fortfahren, bei dem Sie DLP-Richtlinien zum Schutz Ihrer vertraulichen Elemente erstellen werden.

- [Nutzen der Verhinderung von Datenverlust am Endpunkt](endpoint-dlp-using.md)

## <a name="see-also"></a>Siehe auch

- [Informationen zur Verhinderung von Datenverlust am Endpunkt](endpoint-dlp-learn-about.md)
- [Verwenden der Verhinderung von Datenverlust am Endpunkt](endpoint-dlp-using.md)
- [Informationen zur Verhinderung von Datenverlust](dlp-learn-about-dlp.md)
- [Erstellen, Testen und Optimieren einer DLP-Richtlinie](create-test-tune-dlp-policy.md)
- [Erste Schritte mit dem Aktivitäten-Explorer](data-classification-activity-explorer.md)
- [Microsoft Defender für Endpunkt](https://docs.microsoft.com/windows/security/threat-protection/)
- [Onboarding-Tools und -Methoden für Windows 10-Computer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [Microsoft 365-Abonnement](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [Azure AD-verbundene Geräte](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [Herunterladen des auf Chromium basierenden neuen Microsoft Edge](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
