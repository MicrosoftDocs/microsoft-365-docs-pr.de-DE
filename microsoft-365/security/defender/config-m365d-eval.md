---
title: Konfigurieren von Microsoft 365 Defender-Säulen für die Testumgebung oder Pilotumgebung
description: Konfigurieren Sie Microsoft 365 Defender-Säulen, z. B. Microsoft Defender für Office 365, Microsoft Defender for Identity, Microsoft Cloud App Security und Microsoft Defender for Endpoint, für Ihre Testumgebung oder Pilotumgebung.
keywords: Konfigurieren der Microsoft 365 Defender-Testversion, Microsoft 365 Defender-Testkonfiguration, Konfigurieren des Microsoft 365 Defender-Pilotprojekts, Konfigurieren von Microsoft 365 Defender-Säulen, Microsoft 365 Defender-Säulen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 05bdc9cbb678a3d6c1cee726fc4d8c2e45d2d360
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933505"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a>Konfigurieren von Microsoft 365 Defender-Säulen für Ihre Testumgebung oder Pilotumgebung

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender


Das Erstellen einer Microsoft 365 Defender-Testumgebung oder Pilotumgebung und deren Bereitstellung ist ein drei phasenweiser Prozess:

|[![Phase 1: Vorbereiten](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)<br/>[Phase 1: Vorbereiten](prepare-m365d-eval.md) |[![Phase 2: Einrichten](../../media/phase-diagrams/setup.png)](setup-m365deval.md)<br/>[Phase 2: Einrichten](setup-m365deval.md) |![Phase 3: Onboarding](../../media/phase-diagrams/onboard.png)<br/>Phase 3: Onboarding | [![Zurück zum Pilotprojekt](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)<br/>[Zurück zum Testspielbuch](m365d-pilot.md) |
|--|--|--|--|
|| |*Sie sind hier!* | |

Sie sind derzeit in der Konfigurationsphase.

Die Vorbereitung ist der Schlüssel zu jeder erfolgreichen Bereitstellung. In diesem Artikel werden Sie zu den Punkten geführt, die Sie bei der Vorbereitung der Bereitstellung von Microsoft Defender for Endpoint berücksichtigen müssen.


## <a name="microsoft-365-defender-pillars"></a>Microsoft 365 Defender-Säulen
Microsoft 365 Defender besteht aus vier Säulen. Obwohl eine Säule bereits einen Mehrwert für die Sicherheit Ihrer Netzwerkorganisation bieten kann, bietet das Aktivieren der vier Microsoft 365 Defender-Säulen Ihrer Organisation den größten Nutzen.

![Image of_Microsoft 365 Defender-Lösung für Benutzer, Microsoft Defender for Identity, für Endpunkte Microsoft Defender for Endpoint, für Cloud-Apps, Microsoft Cloud App Security und für Daten, Microsoft Defender für Office 365](../../media/mtp/m365pillars.png)

In diesem Abschnitt werden Sie beim Konfigurieren von:
-   Microsoft Defender für Office 365
-   Microsoft Defender for Identity 
-   Microsoft Cloud App Security
-   Microsoft Defender für Endpunkt


## <a name="configure-microsoft-defender-for-office-365"></a>Konfigurieren von Microsoft Defender für Office 365

>[!NOTE]
>Überspringen Sie diesen Schritt, wenn Sie Defender für Office 365 bereits aktiviert haben. 

Es gibt ein PowerShell-Modul namens *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA),* das einige dieser Einstellungen bestimmt. Wenn get-ORCAReport als Administrator in Ihrem Mandanten ausgeführt wird, wird eine Bewertung der Antispam-, Antispam- und anderen Nachrichtenhygieneeinstellungen generiert. Sie können dieses Modul von https://www.powershellgallery.com/packages/ORCA/ herunterladen. 

1. Navigieren Sie [zu Office 365 Security & Compliance Center](https://protection.office.com/homepage)Threat  >  **Management**  >  **Policy**.

   ![Abbildung of_Office 365 Security & Compliance Center Threat Management Policy Page](../../media/mtp-eval-32.png)
 
2. Klicken **Sie auf Antiphishing,** wählen **Sie Erstellen** aus, und geben Sie den Richtliniennamen und die Beschreibung ein. Klicken Sie auf **Weiter**.

   ![Abbildung of_Office 365 Security & Compliance Center–Antiphishingrichtlinienseite, auf der Sie Ihre Richtlinie benennen können](../../media/mtp-eval-33.png)

   > [!NOTE]
   > Bearbeiten Sie Ihre Erweiterte Antiphishingrichtlinie in Microsoft Defender für Office 365. Ändern **des erweiterten Phishingschwellenwerts** **auf 2 – Aggressiv**.

3. Klicken Sie **auf das Dropdownmenü** Bedingung hinzufügen, und wählen Sie Ihre Domäne als Empfängerdomäne aus. Klicken Sie auf **Weiter**.

   ![Abbildung of_Office 365 Security & Compliance Center–Antiphishingrichtlinienseite, auf der Sie eine Bedingung für die Anwendung hinzufügen können](../../media/mtp-eval-34.png)
 
4. Überprüfen Sie Ihre Einstellungen. Klicken **Sie auf Diese Richtlinie erstellen,** um dies zu bestätigen. 

   ![Abbildung of_Office 365 Security & Compliance Center– Antiphishingrichtlinienseite, auf der Sie Ihre Einstellungen überprüfen und auf die Schaltfläche Diese Richtlinie erstellen klicken können](../../media/mtp-eval-35.png)
 
5. Wählen **Sie Sichere Anlagen** aus, und wählen Sie die Option **ATP für SharePoint, OneDrive** und Microsoft Teams aktivieren aus.

   ![Image of_Office 365 Security & Compliance Center-Seite, auf der Sie ATP für SharePoint, OneDrive und Microsoft Teams aktivieren können](../../media/mtp-eval-36.png)

6. Klicken Sie auf das Symbol +, um eine neue Richtlinie für sichere Anlagen zu erstellen, und wenden Sie sie als Empfängerdomäne auf Ihre Domänen an. Klicken Sie auf **Speichern**.

   ![Abbildung of_Office 365 Security & Compliance Center-Seite, auf der Sie eine neue Richtlinie für sichere Anlagen erstellen können](../../media/mtp-eval-37.png)
 
7. Wählen Sie als Nächstes die Richtlinie für **sichere** Links aus, und klicken Sie dann auf das Stiftsymbol, um die Standardrichtlinie zu bearbeiten.

8. Stellen Sie sicher, dass die Option Nicht **nachverfolgen, wenn** Benutzer auf sichere Links klicken, nicht ausgewählt ist, während die restlichen Optionen ausgewählt sind. Weitere [Informationen finden Sie unter Einstellungen für sichere](/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365) Links. Klicken Sie auf **Speichern**. 

   ![Abbildung of_Office 365 Security & Compliance Center-Seite, die zeigt, dass die Option Nicht nachverfolgen, wenn Benutzer auf sicher klicken nicht ausgewählt ist](../../media/mtp-eval-38.png)

9. Wählen Sie als Nächstes **die Richtlinie An malware** aus, wählen Sie die Standardeinstellung aus, und wählen Sie das Stiftsymbol aus.

10. Klicken **Sie auf** Einstellungen, und wählen Sie Ja aus, und verwenden Sie den Standardbenachrichtigungstext, um die Reaktion auf  **schadsoftwareerkennung zu aktivieren.** Aktivieren Sie **den Filter für allgemeine Anlagentypen.** Klicken Sie auf **Speichern**.

    ![Abbildung of_Office 365 Security & Compliance Center-Seite, die zeigt, dass die Reaktion auf schadsoftwareerkennung mit Standardbenachrichtigung aktiviert ist und der Filter für allgemeine Anlagentypen aktiviert ist.](../../media/mtp-eval-39.png)
  
11. Navigieren Sie [zu Office 365 Security & Compliance Center](https://protection.office.com/homepage)Search  >  **Audit** log  >  **search,** und aktivieren Sie die Überwachung.

    ![Image of_Office 365 Security & Compliance Center-Seite, auf der Sie die Überwachungsprotokollsuche aktivieren können](../../media/mtp-eval-40.png)

12. Integrieren Sie Microsoft Defender für Office 365 in Microsoft Defender for Endpoint. Navigieren Sie [zu Office 365 Security & Compliance Center](https://protection.office.com/homepage)Threat Management Explorer, und wählen Sie microsoft Defender for Endpoint Settings in der oberen rechten Ecke des  >    >   Bildschirms aus.  Aktivieren Sie im Dialogfeld Verbindung mit Defender for Endpoint die Verbindung **mit Microsoft Defender for Endpoint verbinden.**

    ![Abbildung of_Office 365 Security & Compliance Center-Seite, auf der Sie die Microsoft Defender for Endpoint-Verbindung aktivieren können](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a>Konfigurieren von Microsoft Defender for Identity

>[!NOTE]
>Überspringen Sie diesen Schritt, wenn Sie Microsoft Defender for Identity bereits aktiviert haben.

1. Navigieren Sie [zu Microsoft 365 Security Center,](https://security.microsoft.com/info) > Weitere **Ressourcen** Microsoft Defender for  >  **Identity auswählen.**

   ![Bild of_Microsoft 365 Security Center-Seite, auf der eine Option zum Öffnen von Microsoft Defender for Identity verfügbar ist](../../media/mtp-eval-42.png)

2. Klicken **Sie auf Erstellen,** um den Microsoft Defender for Identity-Assistenten zu starten. 

   ![Image of_Microsoft Defender for Identity Wizard-Seite, auf der Sie auf Schaltfläche Erstellen klicken sollten](../../media/mtp-eval-43.png)

3. Wählen **Sie Geben Sie einen Benutzernamen und ein Kennwort an, um eine Verbindung mit Ihrer Active Directory-Gesamtstruktur herzustellen.**  

   ![Willkommensseite of_Microsoft Defender for Identity](../../media/mtp-eval-44.png)

4. Geben Sie Ihre lokalen Active Directory-Anmeldeinformationen ein. Dies kann ein beliebiges Benutzerkonto sein, das Lesezugriff auf Active Directory hat.

   ![Abbildung of_Microsoft Defender for Identity Directory-Dienstseite, auf der Sie Ihre Anmeldeinformationen eingeben sollten](../../media/mtp-eval-45.png)

5. Wählen Sie als Nächstes **Sensoreinrichtung herunterladen aus,** und übertragen Sie die Datei auf den Domänencontroller.

   ![Image of_Microsoft Defender for Identity-Seite, auf der Sie Sensoreinrichtung herunterladen auswählen können](../../media/mtp-eval-46.png)

6. Führen Sie das Microsoft Defender for Identity Sensor Setup aus, und beginnen Sie mit dem Ausführen des Assistenten.

   ![Bild of_Microsoft Defender for Identity-Seite, auf der Sie neben dem Microsoft Defender for Identity-Sensor-Assistenten klicken sollten](../../media/mtp-eval-47.png)
 
7. Klicken **Sie im** Sensorbereitstellungstyp auf Weiter.

   ![Bild of_Microsoft Defender for Identity-Seite, auf die Sie klicken sollten, um zur nächsten Seite zu wechseln](../../media/mtp-eval-48.png)
 
8. Kopieren Sie den Zugriffsschlüssel, da Sie ihn als Nächstes im Assistenten eingeben müssen.

   ![Abbildung of_the-Sensorseite, auf der Sie die Zugriffstaste kopieren sollten, die Sie auf der nächsten Seite des Microsoft Defender for Identity-Sensor-Setup-Assistenten eingeben müssen.](../../media/mtp-eval-49.png)
 
9. Kopieren Sie die Zugriffstaste in den Assistenten, und klicken Sie auf **Installieren**. 

   ![Abbildung of_Microsoft Defender for Identity-Sensor-Assistentenseite, auf der Sie die Zugriffstaste bereitstellen und dann auf die Schaltfläche Installieren klicken sollten](../../media/mtp-eval-50.png)

10. Herzlichen Glückwunsch, Sie haben Microsoft Defender for Identity auf Ihrem Domänencontroller erfolgreich konfiguriert.

    ![Abbildung of_Microsoft Defender for Identity-Sensor-Assistent-Installation abgeschlossen, in der Sie auf die Schaltfläche Fertig stellen klicken sollten](../../media/mtp-eval-51.png)
 
11. Wählen Sie [im Abschnitt Microsoft Defender for Identity-Einstellungen](https://go.microsoft.com/fwlink/?linkid=2040449) **Microsoft Defender for Endpoint **, und aktivieren Sie dann den Umschalter. Klicken Sie auf **Speichern**. 

    ![Bild of_the Microsoft Defender for Identity-Einstellungsseite, auf der Sie die Microsoft Defender for Endpoint-Umschaltseite aktivieren sollten](../../media/mtp-eval-52.png)


## <a name="configure-microsoft-cloud-app-security"></a>Konfigurieren von Microsoft Cloud App Security

> [!NOTE]
> Überspringen Sie diesen Schritt, wenn Sie Microsoft Cloud App Security bereits aktiviert haben. 

1. Navigieren Sie [zu Microsoft 365 Security Center](https://security.microsoft.com/info)Weitere  >  **Ressourcen** Microsoft Cloud  >  **App Security**.

   ![Bild of_Microsoft 365 Security Center-Seite, auf der Sie die Microsoft Cloud App-Karte sehen können und auf die Schaltfläche Öffnen klicken sollten](../../media/mtp-eval-53.png)

2. Wählen Sie an der Eingabeaufforderung zum Integrieren von Microsoft Defender for Identity die Option **Microsoft Defender for Identity-Datenintegration aktivieren aus.**
  
   ![Bild of_the Eingabeaufforderung zur Integration von Microsoft Defender for Identity, in der Sie den Link Microsoft Defender for Identity-Datenintegration aktivieren auswählen sollten](../../media/mtp-eval-54.png)

   > [!NOTE]
   > Wenn diese Eingabeaufforderung nicht angezeigt wird, kann dies bedeuten, dass Ihre Microsoft Defender for Identity-Datenintegration bereits aktiviert wurde. Wenn Sie jedoch nicht sicher sind, wenden Sie sich an Ihren IT-Administrator, um dies zu bestätigen. 

3. Wechseln Sie zu **Einstellungen,** aktivieren Sie die **Umschalte Microsoft Defender for Identity-Integration,** und klicken Sie dann auf **Speichern**. 

   ![Bild of_the Einstellungsseite, auf der Sie die Microsoft Defender for Identity-Integration aktivieren sollten, und klicken Sie dann auf Speichern.](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > Bei neuen Microsoft Defender for Identity-Instanzen wird diese Integrationsschalte automatisch aktiviert. Vergewissern Sie sich, dass Ihre Microsoft Defender for Identity-Integration aktiviert wurde, bevor Sie mit dem nächsten Schritt fortfahren.
 
4. Wählen Sie unter cloud discovery settings **die Option Microsoft Defender for Endpoint integration** aus, und aktivieren Sie dann die Integration. Klicken Sie auf **Speichern**.

   ![Abbildung of_the Microsoft Defender for Endpoint-Seite, auf der das Kontrollkästchen nicht installierte Apps blockieren unter Microsoft Defender for Endpoint-Integration aktiviert ist. Klicken Sie auf Speichern.](../../media/mtp-eval-56.png)

5. Wählen Sie unter Einstellungen für die Clouderkennung **die Option Benutzererweiterung** aus, und aktivieren Sie dann die Integration in Azure Active Directory.

   ![Abbildung des Abschnitts "Benutzererweiterung", in dem das Kontrollkästchen "Anreichern ermittelter Benutzerbezeichner mit Azure Active Directory-Benutzernamen" aktiviert ist](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a>Konfigurieren von Microsoft Defender for Endpoint

>[!NOTE]
>Überspringen Sie diesen Schritt, wenn Sie Microsoft Defender for Endpoint bereits aktiviert haben.

1. Navigieren Sie [zu Microsoft 365 Security Center](https://security.microsoft.com/info)Weitere  >  **Ressourcen** Microsoft Defender  >  **Security Center**. Klicken Sie auf **Öffnen**.

   ![Option of_Microsoft Defender Security Center auf der Microsoft 365 Security Center-Seite](../../media/mtp-eval-58.png)
 
2. Folgen Sie dem Microsoft Defender for Endpoint-Assistenten. Klicken Sie auf **Weiter**. 

   ![Bild of_the Microsoft Defender Security Center-Willkommens-Assistentenseite](../../media/mtp-eval-59.png)

3. Wählen Sie basierend auf Dem bevorzugten Datenspeicherort, Datenaufbewahrungsrichtlinie, Organisationsgröße und Opt-In für Vorschaufeatures aus.

   ![Bild of_the seite, um Ihr Datenspeicherland, die Aufbewahrungsrichtlinie und die Organisationsgröße auszuwählen. Klicken Sie auf Weiter, wenn Sie mit der Auswahl fertig sind.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > Sie können einige der Einstellungen, z. B. den Datenspeicherort, danach nicht mehr ändern. 

   Klicken Sie auf **Weiter**. 

4. Klicken **Sie auf Weiter,** und der Microsoft Defender for Endpoint-Mandant wird bereitgestellt.

   ![Bild of_the Seite, auf der Sie auf die Schaltfläche Weiter klicken, um Ihre Cloudinstanz zu erstellen](../../media/mtp-eval-61.png)

5. Onboarding Ihrer Endpunkte über Gruppenrichtlinien, Microsoft Endpoint Manager oder durch Ausführen eines lokalen Skripts für Microsoft Defender for Endpoint. Der Einfachheit halber verwendet dieses Handbuch das lokale Skript.

6. Klicken **Sie auf Paket herunterladen,** und kopieren Sie das Onboardingskript auf Ihre Endpunkte.

   ![Abbildung of_page, mit der Sie auf die Schaltfläche Paket herunterladen klicken, um das Onboardingskript auf Ihren Endpunkt oder Ihre Endpunkte zu kopieren.](../../media/mtp-eval-62.png)

7. Führen Sie auf Ihrem Endpunkt das Onboardingskript als Administrator aus, und wählen Sie Y aus. 

   ![Abbildung of_the Befehlszeile, in der Sie das Onboardingskript ausführen und Y auswählen, um fortzufahren](../../media/mtp-eval-63.png)

8. Herzlichen Glückwunsch, Sie haben Ihren ersten Endpunkt onboardiert.

   ![Abbildung of_the Befehlszeile, in der Sie die Bestätigung erhalten, dass Sie Ihren ersten Endpunkt onboardiert haben. Drücken Sie eine beliebige Taste, um fortzufahren](../../media/mtp-eval-64.png)

9. Kopieren Sie den Erkennungstest aus dem Microsoft Defender for Endpoint-Assistenten.

   ![Image of_the einen Erkennungstestschritt ausführen, in dem Sie auf Kopieren klicken sollten, um das Erkennungstestskript zu kopieren, das Sie in die Eingabeaufforderung einfügen sollten](../../media/mtp-eval-65.png)

10. Kopieren Sie das PowerShell-Skript in eine Eingabeaufforderung mit erhöhten Rechten, und führen Sie es aus. 

    ![Bild of_command Eingabeaufforderung, an der Sie das PowerShell-Skript in eine Eingabeaufforderung mit erhöhten Rechten kopieren und ausführen sollten](../../media/mtp-eval-66.png)

11. Wählen **Sie im Assistenten Starten mit Microsoft Defender for Endpoint** aus.

    ![Bild of_the Bestätigungsaufforderung aus dem Assistenten, in dem Sie auf Starten mit Microsoft Defender for Endpoint klicken sollten](../../media/mtp-eval-67.png)
 
12. Besuchen Sie [das Microsoft Defender Security Center](https://securitycenter.windows.com/). Wechseln Sie zu **Einstellungen,** und wählen Sie **dann Erweiterte Features aus.** 

    ![Menü of_Microsoft Einstellungen von Defender Security Center, in dem Sie erweiterte Features auswählen sollten](../../media/mtp-eval-68.png)

13. Aktivieren Sie die Integration in **Microsoft Defender for Identity**.  

    ![Image of_Microsoft Defender Security Center Advanced-Features, Microsoft Defender for Identity-Option umschalten, die Sie aktivieren müssen](../../media/mtp-eval-69.png)

14. Aktivieren Sie die Integration in **Office 365 Threat Intelligence**.

    ![Image of_Microsoft Defender Security Center Advanced-Features, Office 365 Threat Intelligence-Option umschalten, die Sie aktivieren müssen](../../media/mtp-eval-70.png)

15. Aktivieren der Integration in **Microsoft Cloud App Security**.

    ![Image of_Microsoft Defender Security Center Advanced-Features, Microsoft Cloud App Security-Option umschalten, die Sie aktivieren müssen](../../media/mtp-eval-71.png)

16. Scrollen Sie nach unten, und klicken **Sie auf Einstellungen speichern,** um die neuen Integrationen zu bestätigen.

    ![Schaltfläche of_Save Einstellungen, auf die Sie klicken müssen](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a>Starten des Microsoft 365 Defender-Diensts

>[!NOTE]
>Ab dem 1. Juni 2020 aktiviert Microsoft automatisch Microsoft 365 Defender-Features für alle berechtigten Mandanten. Weitere Informationen finden Sie in diesem [Microsoft Tech Community-Artikel](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) zur Lizenzberechtigung. 


Wechseln Sie zu [Microsoft 365 Security Center](https://security.microsoft.com/homepage). Navigieren Sie zu **Einstellungen,** und wählen Sie **dann Microsoft 365 Defender aus.**

![Screenshot of_Microsoft 365 Defender-Optionen auf der Seite Microsoft 365 Security Center-Einstellungen ](../../media/mtp-eval-72b.png) <br>

Eine umfassendere Anleitung finden Sie unter [Turn on Microsoft 365 Defender](m365d-enable.md). 

Glückwunsch! Sie haben gerade Ihre Microsoft 365 Defender-Testumgebung oder Pilotumgebung erstellt! Jetzt können Sie sich mit der Microsoft 365 Defender-Benutzeroberfläche vertraut machen! Erfahren Sie, was Sie aus dem folgenden interaktiven Microsoft 365 Defender-Leitfaden lernen können, und erfahren Sie, wie Sie jedes Dashboard für Ihre täglichen Sicherheitsaufgaben verwenden.

[Sehen Sie sich den interaktiven Leitfaden an](https://aka.ms/MTP-Interactive-Guide)

Als Nächstes können Sie einen Angriff simulieren und sehen, wie produktübergreifende Funktionen Warnungen erkennen, erstellen und automatisch auf einen dateilosen Angriff auf einen Endpunkt reagieren.

## <a name="next-step"></a>Nächster Schritt

- [Generieren einer Testwarnung](generate-test-alert.md) – Führen Sie eine Angriffssimulation in Ihrem Microsoft 365 Defender-Testlabor aus.