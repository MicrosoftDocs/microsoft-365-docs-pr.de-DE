---
title: Konfigurieren von Microsoft 365 Defender-Säulen für die Testumgebung oder Pilotumgebung
description: Konfigurieren Sie Die Microsoft 365 Defender-Säulen, z. B. Microsoft Defender für Office 365, Microsoft Defender for Identity, Microsoft Cloud App Security und Microsoft Defender für Endpoint, für Ihre Testumgebung oder Pilotumgebung.
keywords: Microsoft Threat Protection-Testversion konfigurieren, Microsoft Threat Protection-Testkonfiguration, Microsoft Threat Protection-Pilotprojekt konfigurieren, Microsoft Threat Protection-Säulen konfigurieren, Microsoft Threat Protection-Säulen
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 78b37d9d435eabce47d360efd630c2e55cadacd1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932238"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a>Konfigurieren von Microsoft 365 Defender-Säulen für Ihre Testumgebung oder Pilotumgebung

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender


Das Erstellen einer Microsoft 365 Defender-Testumgebung oder -Pilotumgebung und deren Bereitstellung besteht aus drei Phasen:

|[![Phase 1: Vorbereiten](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)<br/>[Phase 1: Vorbereiten](prepare-mtpeval.md) |[![Phase 2: Einrichten](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)<br/>[Phase 2: Einrichten](setup-mtpeval.md) |![Phase 3: Onboarding](../../media/phase-diagrams/onboard.png)<br/>Phase 3: Onboarding | [![Zurück zum Pilotprojekt](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[Zurück zum Pilot-Playbook](mtp-pilot.md) |
|--|--|--|--|
|| |*Sie sind hier!* | |

Sie sind derzeit in der Konfigurationsphase.

Die Vorbereitung ist für eine erfolgreiche Bereitstellung entscheidend. In diesem Artikel werden Sie zu den Punkten geführt, die Sie bei der Vorbereitung der Bereitstellung von Microsoft Defender for Endpoint berücksichtigen müssen.


## <a name="microsoft-365-defender-pillars"></a>Microsoft 365 Defender–Säulen
Microsoft 365 Defender besteht aus vier Säulen. Obwohl eine Säule bereits einen Nutzen für die Sicherheit Ihrer Netzwerkorganisation bieten kann, bietet die Aktivierung der vier Microsoft 365 -Defender-Säulen Ihrer Organisation den größten Nutzen.

![Abbildung of_Microsoft 365 Defender-Lösung für Benutzer, Microsoft Defender for Identity, für Endpunkte Microsoft Defender für Endpunkte, für Cloud-Apps, Microsoft Cloud App Security und für Daten, Microsoft Defender für Office 365](../../media/mtp/m365pillars.png)

Dieser Abschnitt enthält Anleitungen zur Konfiguration:
-   Microsoft Defender für Office 365
-   Microsoft Defender for Identity 
-   Microsoft Cloud App-Sicherheit
-   Microsoft Defender für Endpunkt


## <a name="configure-microsoft-defender-for-office-365"></a>Konfigurieren von Microsoft Defender für Office 365

>[!NOTE]
>Überspringen Sie diesen Schritt, wenn Sie Defender für Office 365 bereits aktiviert haben. 

Es gibt ein PowerShell-Modul, das als *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* bezeichnet wird, mit dem einige dieser Einstellungen ermittelt werden können. Wenn sie als Administrator in Ihrem Mandanten ausgeführt wird, hilft get-ORCAReport bei der Generierung einer Bewertung der Antispam-, Antispam-, Antispam- und anderen Nachrichtenschutzeinstellungen. Sie können dieses Modul von https://www.powershellgallery.com/packages/ORCA/ herunterladen. 

1. Navigieren Sie [zu Office 365 Security & Compliance Center](https://protection.office.com/homepage)Threat  >  **Management**  >  **Policy**.

   ![Abbildung of_Office 365 Security & Compliance Center Threat Management Policy Page](../../media/mtp-eval-32.png)
 
2. Klicken **Sie auf "Antiphishing",** wählen **Sie "Erstellen"** aus, und geben Sie den Richtliniennamen und die Beschreibung ein. Klicken Sie auf **Weiter**.

   ![Abbildung of_Office 365 Security & Compliance Center für Antiphishingrichtlinien, auf der Sie Ihre Richtlinie benennen können](../../media/mtp-eval-33.png)

   > [!NOTE]
   > Bearbeiten Sie Ihre erweiterte Antiphishingrichtlinie in Microsoft Defender für Office 365. Ändern **Sie den erweiterten Phishingschwellenwert** auf **2 – Aggressiv.**

3. Klicken Sie **auf das Dropdownmenü** "Bedingung hinzufügen", und wählen Sie Ihre(n) Domäne(n) als Empfängerdomäne aus. Klicken Sie auf **Weiter**.

   ![Abbildung of_Office 365 Security & Compliance Center für Antiphishingrichtlinien, auf der Sie eine Bedingung für die Anwendung hinzufügen können](../../media/mtp-eval-34.png)
 
4. Überprüfen Sie Ihre Einstellungen. Klicken **Sie zur Bestätigung auf "Diese** Richtlinie erstellen". 

   ![Abbildung of_Office 365 Security & Compliance Center für Antiphishingrichtlinien, auf der Sie Ihre Einstellungen überprüfen und auf die Schaltfläche zum Erstellen dieser Richtlinie klicken können](../../media/mtp-eval-35.png)
 
5. Wählen **Sie "Sichere Anlagen"** aus, und wählen Sie die **Option "ATP für SharePoint, OneDrive und Microsoft Teams aktivieren"** aus.

   ![Abbildung of_Office 365 Security & Compliance Center, auf der Sie ATP für SharePoint, OneDrive und Microsoft Teams aktivieren können](../../media/mtp-eval-36.png)

6. Klicken Sie auf das +-Symbol, um eine neue richtlinie für sichere Anlagen zu erstellen, und wenden Sie sie als Empfängerdomäne auf Ihre Domänen an. Klicken Sie auf **Speichern**.

   ![Abbildung of_Office 365 Security & Compliance Center, auf der Sie eine neue Richtlinie für sichere Anlagen erstellen können](../../media/mtp-eval-37.png)
 
7. Wählen Sie als Nächstes die Richtlinie für **sichere** Links aus, und klicken Sie dann auf das Stiftsymbol, um die Standardrichtlinie zu bearbeiten.

8. Stellen Sie sicher, dass die Option "Nicht **nachverfolgen, wenn** Benutzer auf sichere Links klicken" nicht aktiviert ist, während die restlichen Optionen ausgewählt sind. Weitere [Informationen finden Sie unter "Einstellungen für](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) sichere Links". Klicken Sie auf **Speichern**. 

   ![Abbildung of_Office 365 Security & Compliance Center, die zeigt, dass die Option "Nicht nachverfolgen" nicht aktiviert ist, wenn Benutzer auf "Sicher" klicken](../../media/mtp-eval-38.png)

9. Wählen Sie als Nächstes die **Ansoftwarerichtlinie** aus, wählen Sie die Standardeinstellung aus, und wählen Sie das Stiftsymbol aus.

10. Klicken **Sie auf "Einstellungen",** wählen **Sie "Ja" aus,** und verwenden Sie den Standardbenachrichtigungstext, um die Reaktion auf **schadsoftwareerkennung zu aktivieren.** Aktivieren Sie **den Filter "Allgemeine Anlagentypen".** Klicken Sie auf **Speichern**.

    ![Abbildung of_Office 365 Security & Compliance Center, auf der angezeigt wird, dass die Reaktion auf Schadsoftwareerkennung mit Standardbenachrichtigung aktiviert ist und der Allgemeine Anlagentypfilter aktiviert ist](../../media/mtp-eval-39.png)
  
11. Navigieren Sie [zur Office 365 Security & Compliance](https://protection.office.com/homepage)Center-Überwachungsprotokollsuche,  >    >   und aktivieren Sie die Überwachung.

    ![Abbildung of_Office 365 Security & Compliance Center, auf der Sie die Überwachungsprotokollsuche aktivieren können](../../media/mtp-eval-40.png)

12. Integrieren Sie Microsoft Defender für Office 365 in Microsoft Defender for Endpoint. Navigieren Sie [zu Office 365 Security & Compliance Center](https://protection.office.com/homepage)Threat Management Explorer, und wählen Sie in der oberen rechten Ecke des Bildschirms Microsoft Defender  >    >   **für** Endpunkteinstellungen aus. Aktivieren Sie im Dialogfeld "Verbindung mit Defender für Endpunkt" die Verbindung **mit Microsoft Defender für Endpunkt.**

    ![Abbildung of_Office 365 Security & Compliance Center, auf der Sie die Microsoft Defender for Endpoint-Verbindung aktivieren können](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a>Konfigurieren von Microsoft Defender for Identity

>[!NOTE]
>Überspringen Sie diesen Schritt, wenn Sie Microsoft Defender for Identity bereits aktiviert haben.

1. Navigieren Sie [zu Microsoft 365 Security Center,](https://security.microsoft.com/info) > **Microsoft** Defender for Identity weitere  >  **Ressourcen auswählen.**

   ![Abbildung of_Microsoft 365 Security Center- Seite, auf der es eine Option zum Öffnen von Microsoft Defender for Identity gibt](../../media/mtp-eval-42.png)

2. Klicken **Sie auf "Erstellen",** um den Microsoft Defender for Identity-Assistenten zu starten. 

   ![Abbildung of_Microsoft Defender for Identity-Assistentenseite, auf der Sie auf die Schaltfläche "Erstellen" klicken sollten](../../media/mtp-eval-43.png)

3. Wählen **Sie "Geben Sie einen Benutzernamen und ein Kennwort ein, um eine Verbindung mit Ihrer Active Directory-Gesamtstruktur herzustellen".**  

   ![Abbildung of_Microsoft Defender for Identity (Willkommensseite)](../../media/mtp-eval-44.png)

4. Geben Sie Ihre lokalen Active Directory-Anmeldeinformationen ein. Dies kann ein beliebiges Benutzerkonto mit Lesezugriff auf Active Directory sein.

   ![Abbildung of_Microsoft Defender for Identity Directory Services-Seite, auf der Sie Ihre Anmeldeinformationen eingeben sollten](../../media/mtp-eval-45.png)

5. Wählen Sie als Nächstes **"Sensor einrichten herunterladen" aus,** und übertragen Sie die Datei auf ihren Domänencontroller.

   ![Abbildung of_Microsoft Defender for Identity-Seite, auf der Sie "Sensor-Setup herunterladen" auswählen können](../../media/mtp-eval-46.png)

6. Führen Sie das Setup des Microsoft Defender für Identitätssensors aus, und beginnen Sie mit dem Folgen des Assistenten.

   ![Abbildung of_Microsoft Defender for Identity-Seite, auf die Sie neben dem Microsoft Defender for Identity -Sensor-Assistenten klicken sollten](../../media/mtp-eval-47.png)
 
7. Klicken **Sie im** Sensorbereitstellungstyp auf "Weiter".

   ![Abbildung of_Microsoft Defender for Identity-Seite, auf die Sie klicken sollten, um zur nächsten Seite zu wechseln](../../media/mtp-eval-48.png)
 
8. Kopieren Sie die Zugriffstaste, da Sie sie als Nächstes im Assistenten eingeben müssen.

   ![Abbildung of_the, auf der Sie die Zugriffstaste kopieren sollten, die Sie auf der nächsten Seite des Assistenten zum Einrichten des Microsoft Defender für Identitätssensors eingeben müssen](../../media/mtp-eval-49.png)
 
9. Kopieren Sie die Zugriffstaste in den Assistenten, und klicken Sie auf **"Installieren".** 

   ![Abbildung of_Microsoft Defender for Identity-Sensor-Assistentenseite, auf der Sie die Zugriffstaste bereitstellen und dann auf die Schaltfläche "Installieren" klicken sollten](../../media/mtp-eval-50.png)

10. Herzlichen Glückwunsch, Sie haben Microsoft Defender for Identity erfolgreich auf Ihrem Domänencontroller konfiguriert.

    ![Abbildung of_Microsoft Abschluss der Installation des Defender for Identity -Sensor-Assistenten, auf der Sie auf die Schaltfläche "Fertig stellen" klicken sollten](../../media/mtp-eval-51.png)
 
11. Wählen Sie [im Abschnitt "Einstellungen für Microsoft Defender für](https://go.microsoft.com/fwlink/?linkid=2040449) Identität" die Option **Microsoft Defender für Endpunkt **, und aktivieren Sie dann den Umschalter. Klicken Sie auf **Speichern**. 

    ![Abbildung of_the Microsoft Defender for Identity-Einstellungsseite, auf der Sie die Umschaltseite von Microsoft Defender für Endpunkt aktivieren sollten](../../media/mtp-eval-52.png)

>[!NOTE]
>Windows Defender ATP wurde als Microsoft Defender for Endpoint umbenannt. Das Umbranding von Änderungen in allen unseren Portalen wird aus Gründen der Konsistenz durchgeführt.


## <a name="configure-microsoft-cloud-app-security"></a>Konfigurieren von Microsoft Cloud App Security

>[!NOTE]
>Überspringen Sie diesen Schritt, wenn Sie Microsoft Cloud App Security bereits aktiviert haben. 

1. Navigieren Sie zu [Microsoft 365 Security Center](https://security.microsoft.com/info)weitere  >  **Ressourcen** microsoft Cloud  >  **App Security**.

   ![Abbildung of_Microsoft 365 Security Center-Seite, auf der Sie die Microsoft Cloud App-Karte sehen können und auf die Schaltfläche "Öffnen" klicken sollten](../../media/mtp-eval-53.png)

2. Wählen Sie an der Eingabeaufforderung zur Integration von Microsoft Defender for Identity die Option **"Microsoft Defender für die Integration von Identitätsdaten aktivieren" aus.**
  
   ![Abbildung of_the Eingabeaufforderung für die Integration von Microsoft Defender for Identity, in der Sie den Link "Microsoft Defender für Identitätsdatenintegration aktivieren" auswählen sollten](../../media/mtp-eval-54.png)

   > [!NOTE]
   > Wenn diese Eingabeaufforderung nicht angezeigt wird, bedeutet dies möglicherweise, dass Ihre Microsoft Defender for Identity-Datenintegration bereits aktiviert wurde. Wenn Sie jedoch nicht sicher sind, wenden Sie sich zur Bestätigung an Ihren IT-Administrator. 

3. Wechseln Sie **zu "Einstellungen",** aktivieren Sie den Umschalter für die Integration von **Microsoft Defender for Identity,** und klicken Sie dann auf **"Speichern".** 

   ![Bild of_the Einstellungsseite, auf der Sie den Umschalter für die Integration von Microsoft Defender for Identity aktivieren sollten, und klicken Sie dann auf "Speichern".](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > Bei neuen Microsoft Defender for Identity-Instanzen wird diese Integrationsschalt umgeschaltet. Vergewissern Sie sich, dass die Integration von Microsoft Defender for Identity aktiviert wurde, bevor Sie mit dem nächsten Schritt fortfahren.
 
4. Wählen Sie unter den Cloud-Discovery-Einstellungen **Microsoft Defender für Endpunktintegration** aus, und aktivieren Sie dann die Integration. Klicken Sie auf **Speichern**.

   ![Abbildung of_the Microsoft Defender für Endpunkt-Seite, auf der das Kontrollkästchen "Nicht konfigurierte Apps blockieren" unter der Integration von Microsoft Defender für Endpunkt aktiviert ist. Klicken Sie auf "Speichern".](../../media/mtp-eval-56.png)

5. Wählen Sie unter "Cloud-Discovery-Einstellungen" die Benutzeranreicherung aus, und aktivieren Sie dann die Integration in Azure Active Directory.

   ![Abbildung des Abschnitts "Benutzeranreicherung", in dem das Kontrollkästchen "Benutzerbezeichner mit Azure Active Directory-Benutzernamen anreichern" aktiviert ist](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a>Konfigurieren von Microsoft Defender für Endpunkt

>[!NOTE]
>Überspringen Sie diesen Schritt, wenn Sie Microsoft Defender for Endpoint bereits aktiviert haben.

1. Navigieren Sie [zu Microsoft 365 Security Center](https://security.microsoft.com/info)weitere  >  **Ressourcen** Microsoft Defender  >  **Security Center**. Klicken Sie auf **Öffnen**.

   ![Abbildung of_Microsoft Defender Security Center auf der Microsoft 365 Security Center-Seite](../../media/mtp-eval-58.png)
 
2. Folgen Sie dem Microsoft Defender für Endpoint-Assistenten. Klicken Sie auf **Weiter**. 

   ![Abbildung of_the Microsoft Defender Security Center –Willkommens-Assistentenseite](../../media/mtp-eval-59.png)

3. Wählen Sie basierend auf Dem bevorzugten Datenspeicherort, Datenaufbewahrungsrichtlinie, Organisationsgröße und Opt-in für Vorschaufeatures.

   ![Abbildung of_the, auf der Sie Ihr Datenspeicherland, die Aufbewahrungsrichtlinie und die Organisationsgröße auswählen können. Klicken Sie auf "Weiter", wenn Sie mit der Auswahl fertig sind.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > Sie können einige der Einstellungen, z. B. den Datenspeicherort, danach nicht mehr ändern. 

   Klicken Sie auf **Weiter**. 

4. Klicken **Sie auf** "Weiter", und es wird Ihr Microsoft Defender für Endpunkt-Mandant bereitgestellt.

   ![Abbildung of_the, auf der Sie auf die Schaltfläche "Weiter" klicken, um Ihre Cloudinstanz zu erstellen](../../media/mtp-eval-61.png)

5. Integrieren Sie Ihre Endpunkte über Gruppenrichtlinien, Microsoft Endpoint Manager oder durch Ausführen eines lokalen Skripts in Microsoft Defender for Endpoint. Der Einfachheit halber wird in diesem Handbuch das lokale Skript verwendet.

6. Klicken **Sie auf "Paket herunterladen",** und kopieren Sie das Onboardingskript auf Ihre Endpunkte.

   ![Abbildung of_page, in der Sie auf die Schaltfläche "Paket herunterladen" klicken, um das Onboardingskript auf Ihren Endpunkt oder Ihre Endpunkte zu kopieren.](../../media/mtp-eval-62.png)

7. Führen Sie auf Ihrem Endpunkt das Onboardingskript als Administrator aus, und wählen Sie Y aus. 

   ![Abbildung of_the Befehlszeile, in der Sie das Onboardingskript ausführen und Y auswählen, um fortzufahren](../../media/mtp-eval-63.png)

8. Herzlichen Glückwunsch, Sie haben Ihren ersten Endpunkt onboardiert.

   ![Abbildung of_the Befehlszeile, an der Sie die Bestätigung erhalten, dass Sie Ihren ersten Endpunkt onboardiert haben. Drücken Sie eine beliebige Taste, um fortzufahren.](../../media/mtp-eval-64.png)

9. Kopieren Sie den Erkennungstest aus dem Microsoft Defender für Endpunkt-Assistenten.

   ![Abbildung of_the Einen Erkennungstestschritt ausführen, in dem Sie auf "Kopieren" klicken sollten, um das Erkennungstestskript zu kopieren, das Sie in die Eingabeaufforderung einfügen sollten](../../media/mtp-eval-65.png)

10. Kopieren Sie das PowerShell-Skript in eine Eingabeaufforderung mit erhöhten Rechten, und führen Sie es aus. 

    ![Abbildung of_command Eingabeaufforderung, an der Sie das PowerShell-Skript in eine Eingabeaufforderung mit erhöhten Rechten kopieren und ausführen sollten](../../media/mtp-eval-66.png)

11. Wählen **Sie im Assistenten "Mit Microsoft Defender für Endpunkt** starten" aus.

    ![Abbildung of_the Bestätigungsaufforderung des Assistenten, in dem Sie auf "Start" mit Microsoft Defender for Endpoint klicken sollten](../../media/mtp-eval-67.png)
 
12. Besuchen Sie [das Microsoft Defender Security Center.](https://securitycenter.windows.com/) Wechseln Sie zu **"Einstellungen",** und wählen Sie dann **"Erweiterte Features" aus.** 

    ![Abbildung of_Microsoft Menüs "Einstellungen" von Defender Security Center, in dem Sie erweiterte Features auswählen sollten](../../media/mtp-eval-68.png)

13. Aktivieren Sie die Integration in **Microsoft Defender for Identity.**  

    ![Image of_Microsoft Defender Security Center Advanced-Features, Microsoft Defender for Identity-Option, die Sie aktivieren müssen](../../media/mtp-eval-69.png)

14. Aktivieren Sie die Integration in **Office 365 Threat Intelligence.**

    ![Abbildung of_Microsoft Defender Security Center Advanced-Features, Office 365 Threat Intelligence-Option, die Sie aktivieren müssen](../../media/mtp-eval-70.png)

15. Aktivieren Sie die Integration in **Microsoft Cloud App Security.**

    ![Abbildung of_Microsoft Defender Security Center Advanced-Features, Microsoft Cloud App Security-Option, die Sie aktivieren müssen](../../media/mtp-eval-71.png)

16. Scrollen Sie nach unten, und klicken **Sie auf "Einstellungen speichern",** um die neuen Integrationen zu bestätigen.

    ![Bild of_Save Einstellungsschaltfläche, auf die Sie klicken müssen](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a>Starten des Microsoft 365 Defender-Diensts

>[!NOTE]
>Ab dem 1. Juni 2020 aktiviert Microsoft automatisch Microsoft 365 Defender-Features für alle berechtigten Mandanten. Weitere Informationen zur [Lizenzberechtigung finden](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) Sie in diesem Microsoft Tech Community-Artikel. 


Wechseln Sie [zum Microsoft 365 Security Center.](https://security.microsoft.com/homepage) Navigieren Sie zu **"Einstellungen",** und wählen **Sie dann Microsoft 365 Defender aus.**

![Screenshot of_Microsoft 365 Defender-Option auf der Seite "Microsoft 365 Security Center-Einstellungen" ](../../media/mtp-eval-72b.png) <br>

Eine umfassendere Anleitung finden Sie unter ["Aktivieren von Microsoft 365 Defender".](mtp-enable.md) 

Herzlichen Glückwunsch! Sie haben gerade Ihre Microsoft 365 Defender-Testumgebung oder Pilotumgebung erstellt! Jetzt können Sie sich mit der Microsoft 365 Defender-Benutzeroberfläche vertraut machen! Erfahren Sie, was Sie aus dem folgenden interaktiven Microsoft 365 Defender-Leitfaden lernen können, und erfahren Sie, wie Sie jedes Dashboard für Ihre täglichen Sicherheitsaufgaben verwenden.


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

Als Nächstes können Sie einen Angriff simulieren und sehen, wie die produktübergreifenden Funktionen Warnungen erkennen, erstellen und automatisch auf einen dateilosen Angriff auf einen Endpunkt reagieren.

## <a name="next-step"></a>Nächster Schritt
|[Angriffssimulationsphase](mtp-pilot-simulate.md) | Führen Sie die Angriffssimulation für Ihre Microsoft 365 Defender-Pilotumgebung aus.
|:-------|:-----|
