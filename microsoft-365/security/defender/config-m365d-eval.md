---
title: Konfigurieren Microsoft 365 Defender Säulen für die Testumgebung oder Pilotumgebung
description: Konfigurieren Sie Microsoft 365 Defender Säulen, z. B. Microsoft Defender für Office 365, Microsoft Defender for Identity, Microsoft Cloud App Security und Microsoft Defender für Endpunkt, für Ihre Testumgebung oder Pilotumgebung.
keywords: Konfigurieren Microsoft 365 Defender Testversion, Microsoft 365 Defender Konfiguration der Testversion, Konfigurieren Microsoft 365 Defender Pilotprojekts, Konfigurieren Microsoft 365 Defender Säulen, Microsoft 365 Defender Säulen
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
ms.openlocfilehash: e50210f02d14be33c357517515d456318aac4bb6
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229779"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a>Konfigurieren Microsoft 365 Defender Säulen für Ihre Testumgebung oder Pilotumgebung

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender


Das Erstellen einer Microsoft 365 Defender Testumgebung oder Pilotumgebung und deren Bereitstellung erfolgt in drei Phasen:

|[![Phase 1: Vorbereiten](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)<br/>[Phase 1: Vorbereiten](prepare-m365d-eval.md) |[![Phase 2: Einrichten](../../media/phase-diagrams/setup.png)](setup-m365deval.md)<br/>[Phase 2: Einrichten](setup-m365deval.md) |![Phase 3: Onboarding](../../media/phase-diagrams/onboard.png)<br/>Phase 3: Onboarding | [![Zurück zum Pilotprojekt](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)<br/>[Zurück zum Pilot-Playbook](m365d-pilot.md) |
|--|--|--|--|
|| |*Sie sind hier!* | |

Sie befinden sich derzeit in der Konfigurationsphase.

Die Vorbereitung ist der Schlüssel für eine erfolgreiche Bereitstellung. In diesem Artikel werden Sie zu den Punkten geführt, die Sie bei der Vorbereitung der Bereitstellung von Microsoft Defender für Endpunkt berücksichtigen müssen.

## <a name="microsoft-365-defender-pillars"></a>Microsoft 365 Defender Säulen
Microsoft 365 Defender besteht aus vier Säulen. Obwohl eine Säule bereits einen Wert für die Sicherheit Ihrer Netzwerkorganisation bieten kann, bietet die Aktivierung der vier Microsoft 365 Defender Säulen Ihrer Organisation den größten Nutzen.

![Image of_Microsoft 365 Defender-Lösung für Benutzer, Microsoft Defender for Identity, für Endpunkte Microsoft Defender für Endpunkt, für Cloud-Apps, Microsoft Cloud App Security und für Daten, Microsoft Defender für Office 365](../../media/mtp/m365pillars.png)

In diesem Abschnitt erfahren Sie, wie Sie Folgendes konfigurieren:

- Microsoft Defender für Office 365
- Microsoft Defender for Identity
- Microsoft Cloud App Security
- Microsoft Defender für Endpunkt

## <a name="configure-microsoft-defender-for-office-365"></a>Konfigurieren von Microsoft Defender für Office 365

> [!NOTE]
> Überspringen Sie diesen Schritt, wenn Sie Defender bereits für Office 365 aktiviert haben.

Es gibt ein PowerShell-Modul namens *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA),* das einige dieser Einstellungen bestimmt. Wenn sie als Administrator in Ihrem Mandanten ausgeführt wird, hilft get-ORCAReport beim Generieren einer Bewertung der Antispam-, Antiphishing- und anderen Nachrichtenschutzeinstellungen. Sie können dieses Modul von https://www.powershellgallery.com/packages/ORCA/ herunterladen.

1. Navigieren Sie zu [Office 365 Security & Compliance Center](https://protection.office.com/homepage)Threat  >  **Management**  >  **Policy.**

   ![Seite "Image of_Office 365 Security & Compliance Center Threat Management Policy"](../../media/mtp-eval-32.png)

2. Klicken Sie auf **"Antiphishing",** wählen Sie **"Erstellen"** aus, und geben Sie den Richtliniennamen und die Beschreibung ein. Klicken Sie auf **Weiter**.

   ![Abbildung of_Office 365 Security & Compliance Center-Antiphishingrichtlinienseite, auf der Sie Ihre Richtlinie benennen können](../../media/mtp-eval-33.png)

   > [!NOTE]
   > Bearbeiten Sie Ihre erweiterte Antiphishingrichtlinie in Microsoft Defender für Office 365. Ändern Sie den **Erweiterten Phishingschwellenwert** auf **2 – Aggressiv.**

3. Klicken Sie auf das Dropdownmenü **"Bedingung hinzufügen",** und wählen Sie Ihre Domäne(n) als Empfängerdomäne aus. Klicken Sie auf **Weiter**.

   ![Abbildung of_Office Seite "365 Security & Compliance Center antiphishing policy", auf der Sie eine Bedingung für die Anwendung hinzufügen können](../../media/mtp-eval-34.png)

4. Überprüfen Sie Ihre Einstellungen. Klicken Sie auf **"Diese Richtlinie** erstellen", um dies zu bestätigen.

   ![Abbildung of_Office Seite "365 Security & Compliance Center antiphishing policy", auf der Sie Ihre Einstellungen überprüfen und auf die Schaltfläche zum Erstellen dieser Richtlinie klicken können](../../media/mtp-eval-35.png)

5. Wählen Sie **Tresor Anlagen** aus, und aktivieren Sie **atp für SharePoint, OneDrive und Microsoft Teams** Option.

   ![Abbildung of_Office Seite 365 Security & Compliance Center, auf der Sie ATP für SharePoint, OneDrive und Microsoft Teams aktivieren können](../../media/mtp-eval-36.png)

6. Klicken Sie auf das Symbol +, um eine neue Richtlinie für sichere Anlagen zu erstellen und sie als Empfängerdomäne auf Ihre Domänen anzuwenden. Klicken Sie auf **Speichern**.

   ![Abbildung of_Office Seite "365 Security & Compliance Center", auf der Sie eine neue Richtlinie für sichere Anlagen erstellen können](../../media/mtp-eval-37.png)

7. Wählen Sie als Nächstes die **Richtlinie Tresor Links** aus, und klicken Sie dann auf das Stiftsymbol, um die Standardrichtlinie zu bearbeiten.

8. Stellen Sie sicher, dass die Option **"Nicht nachverfolgen", wenn Benutzer auf** die Option "Sichere Links" klicken, nicht ausgewählt ist, während die restlichen Optionen ausgewählt sind. Weitere Informationen finden Sie [unter Tresor Links-Einstellungen.](/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365) Klicken Sie auf **Speichern**.

   ![Abbildung of_Office Seite 365 Security & Compliance Center, die zeigt, dass die Option "Nicht nachverfolgen" angezeigt wird, wenn Benutzer auf "Sicher" klicken, nicht ausgewählt ist](../../media/mtp-eval-38.png)

9. Wählen Sie als Nächstes die **Antischadsoftwarerichtlinie** aus, wählen Sie die Standardeinstellung aus, und wählen Sie das Stiftsymbol aus.

10. Klicken Sie auf **Einstellungen,** und wählen Sie **"Ja" aus, und verwenden Sie den Standardbenachrichtigungstext,** um die **Schadsoftwareerkennungsantwort** zu aktivieren. Aktivieren Sie den **Filter für allgemeine Anlagentypen.** Klicken Sie auf **Speichern**.

    ![Abbildung of_Office Seite 365 Security & Compliance Center, die zeigt, dass die Schadsoftwareerkennungsantwort mit Standardbenachrichtigung aktiviert ist und der allgemeine Filter für Anlagentypen aktiviert ist](../../media/mtp-eval-39.png)

11. Navigieren Sie zu Office 365 Überwachungsprotokollsuche [im Security & Compliance](https://protection.office.com/homepage)  >    >   Center, und aktivieren Sie die Überwachung.

    ![Abbildung of_Office Seite 365 Security & Compliance Center, auf der Sie die Überwachungsprotokollsuche aktivieren können](../../media/mtp-eval-40.png)

12. Integrieren Sie Microsoft Defender für Office 365 in Microsoft Defender für Endpunkt. Navigieren Sie zu [Office 365 Security & Compliance Center](https://protection.office.com/homepage)Threat  >  **Management**  >  **Explorer,** und wählen Sie **Microsoft Defender für Endpunkt Einstellungen** in der oberen rechten Ecke des Bildschirms aus. Aktivieren Sie im Dialogfeld "Defender für Endpunkt-Verbindung" **Verbinden zu Microsoft Defender für Endpunkt.**

    ![Abbildung of_Office Seite 365 Security & Compliance Center, auf der Sie die Microsoft Defender für Endpunkt-Verbindung aktivieren können](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a>Konfigurieren von Microsoft Defender for Identity

> [!NOTE]
> Überspringen Sie diesen Schritt, wenn Sie Microsoft Defender for Identity bereits aktiviert haben.

1. Navigieren Sie zu [Microsoft 365 Security Center](https://security.microsoft.com/info) > wählen Sie weitere **Ressourcen** Microsoft Defender  >  **for Identity** aus.

   ![Abbildung of_Microsoft 365 Security Center-Seite, auf der es eine Option zum Öffnen von Microsoft Defender for Identity gibt](../../media/mtp-eval-42.png)

2. Klicken Sie auf **"Erstellen",** um den Microsoft Defender for Identity-Assistenten zu starten.

   ![Abbildung of_Microsoft Seite des Defender for Identity-Assistenten, auf der Sie auf die Schaltfläche "Erstellen" klicken sollten](../../media/mtp-eval-43.png)

3. Wählen **Sie Einen Benutzernamen und ein Kennwort angeben, um eine Verbindung mit Ihrer Active Directory-Gesamtstruktur herzustellen.**

   ![Willkommensseite für Image of_Microsoft Defender for Identity](../../media/mtp-eval-44.png)

4. Geben Sie Ihre lokalen Active Directory-Anmeldeinformationen ein. Dies kann ein beliebiges Benutzerkonto sein, das Lesezugriff auf Active Directory hat.

   ![Abbildung of_Microsoft Seite der Defender for Identity Directory-Dienste, auf der Sie Ihre Anmeldeinformationen ablegen sollten](../../media/mtp-eval-45.png)

5. Wählen Sie als Nächstes **"Sensorsetup herunterladen"** aus, und übertragen Sie die Datei an Ihren Domänencontroller.

   ![Abbildung of_Microsoft Defender for Identity-Seite, auf der Sie "Sensorsetup herunterladen" auswählen können](../../media/mtp-eval-46.png)

6. Führen Sie das Microsoft Defender for Identity Sensor-Setup aus, und beginnen Sie mit dem Folgen des Assistenten.

   ![Abbildung of_Microsoft Defender for Identity-Seite, auf der Sie neben dem Microsoft Defender for Identity-Sensor-Assistenten klicken sollten](../../media/mtp-eval-47.png)

7. Klicken Sie im Sensorbereitstellungstyp auf **"Weiter".**

   ![Abbildung of_Microsoft Defender for Identity-Seite, auf der Sie neben klicken sollten, um zur nächsten Seite zu wechseln](../../media/mtp-eval-48.png)

8. Kopieren Sie die Zugriffstaste, da Sie sie als Nächstes im Assistenten eingeben müssen.

   ![Abbildung of_the Sensorseite, auf der Sie die Zugriffstaste kopieren sollten, die Sie auf der nächsten Microsoft Defender for Identity-Assistenten-Assistentenseite eingeben müssen](../../media/mtp-eval-49.png)

9. Kopieren Sie die Zugriffstaste in den Assistenten, und klicken Sie auf **"Installieren".**

   ![Abbildung of_Microsoft Defender for Identity-Sensor-Assistentenseite, auf der Sie die Zugriffstaste bereitstellen und dann auf die Schaltfläche "Installieren" klicken sollten](../../media/mtp-eval-50.png)

10. Herzlichen Glückwunsch, Sie haben Microsoft Defender for Identity auf Ihrem Domänencontroller erfolgreich konfiguriert.

    ![Abbildung of_Microsoft Abschluss der Installation des Defender for Identity-Sensor-Assistenten, in dem Sie auf die Schaltfläche "Fertig stellen" klicken sollten](../../media/mtp-eval-51.png)

11. Wählen Sie im Abschnitt ["Einstellungen für Microsoft Defender for Identity"](https://go.microsoft.com/fwlink/?linkid=2040449) **Microsoft Defender für Endpunkt ** aus, und aktivieren Sie dann die Umschaltfläche. Klicken Sie auf **Speichern**.

    ![Abbildung of_the Einstellungsseite von Microsoft Defender for Identity, auf der Sie die Microsoft Defender für Endpunkt-Umschaltfläche aktivieren sollten](../../media/mtp-eval-52.png)

## <a name="configure-microsoft-cloud-app-security"></a>Konfigurieren Microsoft Cloud App Security

> [!NOTE]
> Überspringen Sie diesen Schritt, wenn Sie Microsoft Cloud App Security bereits aktiviert haben.

1. Navigieren Sie zu [Microsoft 365 Security Center](https://security.microsoft.com/info)Weitere  >  **Ressourcen**  >  **Microsoft Cloud App Security**.

   ![Abbildung of_Microsoft 365 Security Center-Seite, auf der Sie die Microsoft Cloud App-Karte sehen können und auf die Schaltfläche "Öffnen" klicken sollten](../../media/mtp-eval-53.png)

2. Wählen Sie an der Informationsaufforderung zum Integrieren von Microsoft Defender for Identity die Option **"Microsoft Defender for Identity-Datenintegration aktivieren"** aus.

   ![Abbildung of_the Eingabeaufforderung zur Integration von Microsoft Defender for Identity, wobei Sie den Link "Microsoft Defender for Identity"-Datenintegration aktivieren sollten](../../media/mtp-eval-54.png)

   > [!NOTE]
   > Wenn diese Aufforderung nicht angezeigt wird, bedeutet dies möglicherweise, dass Die Microsoft Defender for Identity-Datenintegration bereits aktiviert wurde. Wenn Sie sich jedoch nicht sicher sind, wenden Sie sich an Ihren IT-Administrator, um dies zu bestätigen.

3. Wechseln Sie zu **Einstellungen,** aktivieren Sie die Microsoft Defender for Identity-Integrations-Umschaltfläche, und klicken Sie dann auf **"Speichern".** 

   ![Abbildung of_the Einstellungsseite, auf der Sie die Microsoft Defender for Identity-Integrationsschaltfläche aktivieren sollten, und klicken Sie dann auf "Speichern".](../../media/mtp-eval-55.png)

   > [!NOTE]
   > Bei neuen Microsoft Defender for Identity-Instanzen wird diese Integrationsschaltfläche automatisch aktiviert. Vergewissern Sie sich, dass Ihre Microsoft Defender for Identity-Integration aktiviert wurde, bevor Sie mit dem nächsten Schritt fortfahren.

4. Wählen Sie unter den Cloud-Ermittlungseinstellungen **die Integration von Microsoft Defender für Endpunkt** aus, und aktivieren Sie dann die Integration. Klicken Sie auf **Speichern**.

   ![Abbildung of_the Microsoft Defender für Endpunkt-Seite, auf der das Kontrollkästchen "Nicht autorisierte Apps blockieren" unter Microsoft Defender für Endpunktintegration aktiviert ist. Klicken Sie auf "Speichern".](../../media/mtp-eval-56.png)

5. Wählen Sie unter "Cloud Discovery"-Einstellungen **"Benutzererweiterung"** aus, und aktivieren Sie dann die Integration mit Azure Active Directory.

   ![Abbildung des Abschnitts "Benutzererweiterung", in dem das Kontrollkästchen "Benutzeranreicherung" mit Azure Active Directory Benutzernamen aktiviert ist](../../media/mtp-eval-57.png)

## <a name="configure-microsoft-defender-for-endpoint"></a>Konfigurieren von Microsoft Defender für Endpunkt

> [!NOTE]
> Überspringen Sie diesen Schritt, wenn Sie Microsoft Defender für Endpunkt bereits aktiviert haben.

1. Navigieren Sie zu [Microsoft 365 Security Center](https://security.microsoft.com/info)Weitere  >  **Ressourcen**  >  **Microsoft Defender Security Center**. Klicken Sie auf **Öffnen**.

   ![Abbildung of_Microsoft Defender Security Center-Option auf der Seite Microsoft 365 Security Center](../../media/mtp-eval-58.png)

2. Folgen Sie dem Microsoft Defender für Endpunkt-Assistenten. Klicken Sie auf **Weiter**.

   ![Abbildung of_the Microsoft Defender Security Center Willkommens-Assistentenseite](../../media/mtp-eval-59.png)

3. Wählen Sie basierend auf Ihrem bevorzugten Datenspeicherort, der Datenaufbewahrungsrichtlinie, der Organisationsgröße und dem Opt-In für Vorschaufeatures.

   ![Abbildung of_the Seite, um Ihr Datenspeicherland, Ihre Aufbewahrungsrichtlinie und die Organisationsgröße auszuwählen. Klicken Sie auf "Weiter", wenn Sie die Auswahl abgeschlossen haben.](../../media/mtp-eval-60.png)

   > [!NOTE]
   > Sie können einige Einstellungen, z. B. den Datenspeicherort, danach nicht ändern.

   Klicken Sie auf **Weiter**.

4. Klicken Sie auf **"Weiter",** und es wird Ihr Microsoft Defender für Endpunkt-Mandant bereitgestellt.

   ![Abbildung of_the Seite, auf der Sie auf die Schaltfläche "Weiter" klicken, um Ihre Cloudinstanz zu erstellen](../../media/mtp-eval-61.png)

5. Integrieren Sie Ihre Endpunkte über Gruppenrichtlinien, Microsoft Endpoint Manager oder durch Ausführen eines lokalen Skripts in Microsoft Defender für Endpunkt. Der Einfachheit halber wird in diesem Leitfaden das lokale Skript verwendet.

6. Klicken Sie auf **"Paket herunterladen",** und kopieren Sie das Onboarding-Skript auf Ihre Endpunkte.

   ![Abbildung of_page Aufforderung, auf die Schaltfläche "Paket herunterladen" zu klicken, um das Integrationsskript auf Ihren Endpunkt oder Ihre Endpunkte zu kopieren](../../media/mtp-eval-62.png)

7. Führen Sie auf Ihrem Endpunkt das Onboardingskript als Administrator aus, und wählen Sie "Y" aus.

   ![Abbildung of_the Befehlszeile, in der Sie das Onboarding-Skript ausführen und Y auswählen, um fortzufahren](../../media/mtp-eval-63.png)

8. Herzlichen Glückwunsch, Sie haben Ihren ersten Endpunkt integriert.

   ![Abbildung of_the Befehlszeile, in der Sie die Bestätigung erhalten, dass Sie Ihren ersten Endpunkt integriert haben. Drücken Sie eine beliebige Taste, um fortzufahren.](../../media/mtp-eval-64.png)

9. Kopieren Sie den Erkennungstest aus dem Microsoft Defender für Endpunkt-Assistenten.

   ![Abbildung of_the Ausführen eines Erkennungstestschritts, in dem Sie auf "Kopieren" klicken sollten, um das Erkennungstestskript zu kopieren, das Sie in die Eingabeaufforderung einfügen sollten](../../media/mtp-eval-65.png)

10. Kopieren Sie das PowerShell-Skript in eine Eingabeaufforderung mit erhöhten Rechten, und führen Sie es aus.

    ![Abbildung of_command Eingabeaufforderung, in der Sie das PowerShell-Skript in eine Eingabeaufforderung mit erhöhten Rechten kopieren und ausführen sollten](../../media/mtp-eval-66.png)

11. Wählen Sie **"Start using Microsoft Defender for Endpoint"** aus dem Assistenten aus.

    ![Abbildung of_the Bestätigungsaufforderung des Assistenten, in der Sie auf "Verwenden von Microsoft Defender für Endpunkt starten" klicken sollten](../../media/mtp-eval-67.png)

12. Besuchen Sie die [Microsoft Defender Security Center](https://securitycenter.windows.com/). Wechseln Sie zu **Einstellungen,** und wählen Sie dann **"Erweiterte Features" aus.**

    ![Image of_Microsoft Defender Security Center Einstellungen Menü, in dem Sie erweiterte Features auswählen sollten](../../media/mtp-eval-68.png)

13. Aktivieren Sie die Integration in **Microsoft Defender for Identity.**

    ![Image of_Microsoft Defender Security Center Advanced-Features, Umschaltfläche der Microsoft Defender for Identity-Option, die Sie aktivieren müssen](../../media/mtp-eval-69.png)

14. Aktivieren Sie die Integration mit **Office 365 Threat Intelligence.**

    ![Erweiterte Features von Image of_Microsoft Defender Security Center Office 365 Option "Threat Intelligence", die Sie aktivieren müssen](../../media/mtp-eval-70.png)

15. Aktivieren Sie die Integration in **Microsoft Cloud App Security.**

    ![Image of_Microsoft Defender Security Center Advanced-Features, Microsoft Cloud App Security Umschaltfläche, die Sie aktivieren müssen](../../media/mtp-eval-71.png)

16. Scrollen Sie nach unten, und klicken Sie auf **"Einstellungen speichern",** um die neuen Integrationen zu bestätigen.

    ![Bild of_Save Schaltfläche "Einstellungen", auf die Sie klicken müssen](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a>Starten des Microsoft 365 Defender-Diensts

> [!NOTE]
> Ab dem 1. Juni 2020 aktiviert Microsoft automatisch Microsoft 365 Defender Features für alle berechtigten Mandanten. Weitere Informationen finden Sie in diesem [Microsoft Tech Community Artikel zur Lizenzberechtigung.](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426)

Wechseln Sie zu [Microsoft 365 Security Center.](https://security.microsoft.com/homepage) Navigieren Sie zu **Einstellungen,** und wählen Sie dann **Microsoft 365 Defender** aus.

![Screenshot of_Microsoft 365 Defender-Option auf der Seite Microsoft 365 Security Center Einstellungen](../../media/mtp-eval-72b.png)

Eine umfassendere Anleitung finden Sie unter [Aktivieren von Microsoft 365 Defender.](m365d-enable.md)

Herzlichen Glückwunsch! Sie haben gerade Ihre Microsoft 365 Defender Testumgebung oder Pilotumgebung erstellt! Jetzt können Sie sich mit der Microsoft 365 Defender Benutzeroberfläche vertraut machen! Erfahren Sie, was Sie aus dem folgenden Microsoft 365 Defender interaktiven Leitfaden lernen und wissen, wie Sie jedes Dashboard für Ihre täglichen Sicherheitsaufgaben verwenden.

[Sehen Sie sich den interaktiven Leitfaden an](https://aka.ms/MTP-Interactive-Guide)

Als Nächstes können Sie einen Angriff simulieren und sehen, wie die produktübergreifenden Funktionen Warnungen erkennen, erstellen und automatisch auf einen dateilosen Angriff auf einen Endpunkt reagieren.

## <a name="next-step"></a>Nächster Schritt

- [Generieren Sie eine Testwarnung–](generate-test-alert.md) Führen Sie eine Angriffssimulation in Ihrem Microsoft 365 Defender Testlabor aus.
