---
title: Konfigurieren von Microsoft Threat Protection-Säulen für die Test Labor-oder Pilotumgebung
description: Konfigurieren Sie Microsoft Threat Protection-Säulen wie Office 365 ATP, Azure ATP, Microsoft Cloud App Security und Microsoft Defender ATP für Ihre Test Labor-oder Pilotumgebung.
keywords: Konfigurieren von Microsoft Threat Protection-Testversion, Microsoft Threat Protection-Testkonfiguration, Microsoft Threat Protection-Pilotprojekt konfigurieren, Microsoft Threat Protection-Säulen konfigurieren, Microsoft Threat Protection-Säulen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
- m365solution-evalutatemtp
ms.topic: article
ms.openlocfilehash: 79e141ad85eecab827e0caa98fe022f88335c671
ms.sourcegitcommit: 9d8d071659e662c266b101377e24549963e43fef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2020
ms.locfileid: "48368149"
---
# <a name="configure-microsoft-threat-protection-pillars-for-your-trial-lab-or-pilot-environment"></a>Konfigurieren von Microsoft Threat Protection-Säulen für Ihre Test Labor-oder Pilotumgebung

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft Threat Protection


Das Erstellen eines Microsoft Threat Protection-Testlabors oder einer Pilotumgebung und deren Bereitstellung ist ein dreistufiger Prozess:

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="Vorbereiten Ihrer Testlabor-oder Pilotumgebung für den Microsoft Threat Protection-Test" />
      <br/>Phase 1: Vorbereiten </a><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab or pilot environment" title="Einrichten Ihres Microsoft Threat Protection-Testlabors oder einer Pilotumgebung" />
      <br/>Phase 2: Setup </a><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="Konfigurieren der einzelnen Microsoft Threat Protection-Pfeiler für Ihr Microsoft Threat Protection-Test Labor oder Ihre Pilotumgebung sowie Onboard-Endpunkte" />
      <br/>Phase 3: Konfigurieren von & Onboard </a><br>
</td>
  </tr>
</table>

Sie befinden sich derzeit in der Konfigurationsphase.


Die Vorbereitung ist für eine erfolgreiche Bereitstellung entscheidend. In diesem Artikel werden Sie auf die Punkte hingewiesen, die Sie bei der Vorbereitung der Bereitstellung von Microsoft Defender ATP berücksichtigen müssen.


## <a name="microsoft-threat-protection-pillars"></a>Microsoft Threat Protection-Säulen
Microsoft Threat Protection besteht aus vier Pfeilern. Auch wenn ein Pfeiler bereits einen Mehrwert für die Sicherheit ihrer Netzwerkorganisation bieten kann, bietet die Aktivierung der vier Microsoft-Bedrohungsschutz-Pfeiler Ihrer Organisation den größten Nutzen.

![Image of_Microsoft Threat Protection-Lösung für Benutzer, Azure Advanced Threat Protection, für Endpoint Microsoft Defender Advanced Threat Protection, für Cloud-apps, Microsoft Cloud App Security und für Daten, Office 365 Advanced Threat Protection  ](../../media/mtp-eval-31.png)

In diesem Abschnitt erhalten Sie Informationen zu configure:
-   Office 365 Advanced Threat Protection
-   Azure Advanced Threat Protection 
-   Microsoft Cloud App-Sicherheit
-   Microsoft Defender Advanced Threat Protection


## <a name="configure-office-365-advanced-threat-protection"></a>Konfigurieren Office 365 Advanced Threat Protection

>[!NOTE]
>Überspringen Sie diesen Schritt, wenn Sie bereits Office 365 Advanced Threat Protection aktiviert haben. 

Es gibt ein PowerShell-Modul mit dem Namen *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (Orca)* , mit dem einige dieser Einstellungen ermittelt werden können. Wenn Sie als Administrator in Ihrem Mandanten ausgeführt wird, hilft Get-ORCAReport bei der Erstellung einer Bewertung der Anti-Spam-, Anti-Phishing-und anderer Nachrichten Hygiene Einstellungen. Sie können dieses Modul aus herunterladen https://www.powershellgallery.com/packages/ORCA/ . 

1. Navigieren Sie zu [Office 365 Security & Compliance Center](https://protection.office.com/homepage)  >  **Threat Management**  >  **Policy**.

   ![Image of_Office 365 Security & Compliance Center Threat Management-Richtlinie (Seite)](../../media/mtp-eval-32.png)
 
2. Klicken Sie auf **ATP-Anti-Phishing**, wählen Sie **Create** aus, und geben Sie den Richtliniennamen und die Beschreibung ein. Klicken Sie auf **Weiter**.

   ![Image of_Office 365 Security & Compliance Center-Richtlinie zur Anti-Phishing-Politik, auf der Sie Ihre Richtlinie benennen können](../../media/mtp-eval-33.png)

   > [!NOTE]
   > Bearbeiten Sie Ihre erweiterte ATP-Richtlinie zum Schutz vor Phishing. Ändern Sie den **Advanced Phishing Threshold** in **2-aggressive**.

3. Klicken Sie auf das Dropdownmenü **Bedingung hinzufügen** , und wählen Sie Ihre Domäne (n) als Empfängerdomäne aus. Klicken Sie auf **Weiter**.

   ![Image of_Office 365 Security & Compliance Center-Richtlinie zur Anti-Phishing-Politik, auf der Sie eine Bedingung für Ihre Anwendung hinzufügen können](../../media/mtp-eval-34.png)
 
4. Überprüfen Sie Ihre Einstellungen. Klicken Sie zum bestätigen auf **Diese Richtlinie erstellen** . 

   ![Image of_Office 365 Security & Compliance Center-Richtlinie zur Anti-Phishing-Politik, auf der Sie Ihre Einstellungen überprüfen und auf die Schaltfläche Richtlinie erstellen klicken können](../../media/mtp-eval-35.png)
 
5. Wählen Sie **ATP-sichere Anlagen** aus, und aktivieren Sie die Option **ATP für SharePoint, OneDrive und Microsoft Teams aktivieren** .

   ![Image of_Office 365 Security & Compliance Center Seite, auf der Sie ATP für SharePoint, OneDrive und Microsoft Teams aktivieren können](../../media/mtp-eval-36.png)

6. Klicken Sie auf das Symbol +, um eine neue Richtlinie für sichere Anlagen zu erstellen und diese als Empfängerdomäne auf Ihre Domänen anzuwenden. Klicken Sie auf **Speichern**.

   ![Image of_Office 365 Security & Compliance Center-Seite, auf der Sie eine neue Richtlinie zum Erstellen einer neuen sicheren Anlage erstellen können](../../media/mtp-eval-37.png)
 
7. Wählen Sie als nächstes die Richtlinie **ATP-sichere Links** aus, und klicken Sie dann auf das Bleistiftsymbol, um die Standardrichtlinie zu bearbeiten.

8. Stellen Sie sicher, dass die Option nicht **nachverfolgen, wenn Benutzer auf sichere Links klicken** ausgewählt ist, während die restlichen Optionen ausgewählt sind. Details finden Sie unter [Einstellungen für sichere Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) . Klicken Sie auf **Speichern**. 

   ![Image of_Office 365 Security & Compliance Center Seite, die zeigt, dass die Option nicht nachverfolgt werden kann, wenn Benutzer auf sicher klicken nicht ausgewählt ist.](../../media/mtp-eval-38.png)

9. Wählen Sie als nächstes die **Antischadsoftware-** Richtlinie aus, wählen Sie die Standardeinstellung aus, und wählen Sie das Bleistiftsymbol aus.

10. Klicken Sie auf **Einstellungen** und dann auf **Ja, und verwenden Sie den standardmäßigen Benachrichtigungstext** , um die **Malware Erkennungs Antwort**zu aktivieren. Aktivieren Sie den **Filter allgemeine Anlagentypen** . Klicken Sie auf **Speichern**.

    ![Image of_Office 365 Security & Compliance Center Seite, die zeigt, dass die Malware Erkennungs Antwort mit Standardbenachrichtigung aktiviert ist und der Filter "allgemeine Anlagentypen" aktiviert ist.](../../media/mtp-eval-39.png)
  
11. Navigieren Sie zu [Office 365 Security & Compliance Center](https://protection.office.com/homepage)  >  -**Such**  >  **Überwachungsprotokoll-Suche** , und aktivieren Sie die Überwachung.

    ![Image of_Office 365 Security & Compliance Center Seite, auf der Sie die Überwachungsprotokoll Suche aktivieren können](../../media/mtp-eval-40.png)

12. Integrieren Sie Office 365 ATP mit Microsoft Defender ATP. Navigieren Sie zu [Office 365 Security & Compliance Center](https://protection.office.com/homepage)  >  **Threat Management**  >  **Explorer** , und wählen Sie **WDATP-Einstellungen** in der oberen rechten Ecke des Bildschirms aus. Aktivieren Sie im Dialogfeld Microsoft Defender ATP Connection die Option **Connect to Windows ATP**.

    ![Image of_Office 365 Security & Compliance Center Seite, auf der Sie die ATP-Verbindung von Windows Defender aktivieren können](../../media/mtp-eval-41.png)

## <a name="configure-azure-advanced-threat-protection"></a>Konfigurieren von Azure Advanced Threat Protection

>[!NOTE]
>Überspringen Sie diesen Schritt, wenn Sie Azure Advanced Threat Protection bereits aktiviert haben.

1. Navigieren Sie zum [Microsoft 365 Security Center](https://security.microsoft.com/info) > wählen Sie **Weitere Ressourcen**  >  **Azure Advanced Threat Protection**aus.

   ![Image of_Microsoft 365-Sicherheits Center Seite, auf der eine Option zum Öffnen von Azure Advanced Threat Protection verfügbar ist](../../media/mtp-eval-42.png)

2. Klicken Sie auf **Erstellen** , um den Azure Advanced Threat Protection-Assistenten zu starten. 

   ![Seite "Image of_Azure Advanced Threat Protection", auf der Sie auf die Schaltfläche "erstellen" klicken sollten](../../media/mtp-eval-43.png)

3. Wählen Sie **Geben Sie einen Benutzernamen und ein Kennwort ein, um eine Verbindung mit Ihrer Active Directory Gesamtstruktur herzustellen**.  

   ![Willkommensseite für Image of_Azure Advanced Threat Protection](../../media/mtp-eval-44.png)

4. Geben Sie Ihre Active Directory lokalen Anmeldeinformationen ein. Hierbei kann es sich um ein beliebiges Benutzerkonto handeln, das über Lesezugriff auf Active Directory verfügt.

   ![Image of_Azure Advanced Threat Protection-Verzeichnisdienst Seite, auf der Sie Ihre Anmeldeinformationen platzieren sollten](../../media/mtp-eval-45.png)

5. Wählen Sie als nächstes **Download Sensor Setup** aus, und übertragen Sie die Datei auf Ihren Domänencontroller.

   ![Image of_Azure Advanced Threat Protection-Seite, auf der Sie Download Sensor Setup auswählen können](../../media/mtp-eval-46.png)

6. Führen Sie das Azure ATP-Sensor Setup aus, und folgen Sie dem Assistenten.

   ![Image of_Azure Advanced Threat Protection-Seite, auf der Sie auf Weiter klicken, um dem Azure ATP-Sensor-Assistenten zu entsprechen](../../media/mtp-eval-47.png)
 
7. Klicken Sie im Sensor Bereitstellungs auf **weiter** .

   ![Image of_Azure Advanced Threat Protection-Seite, auf der Sie auf Weiter klicken sollten, um zur nächsten Seite zu wechseln](../../media/mtp-eval-48.png)
 
8. Kopieren Sie die Zugriffstaste, da Sie Sie als nächstes im Assistenten eingeben müssen.

   ![Seite "Bild of_the Sensoren", auf der Sie die Zugriffstaste kopieren sollten, die Sie auf der nächsten Seite des Azure ATP-Sensor-Setup-Assistenten eingeben müssen](../../media/mtp-eval-49.png)
 
9. Kopieren Sie den Zugriffsschlüssel in den Assistenten, und klicken Sie auf **Installieren**. 

   ![Image of_Azure Advanced Threat Protection Azure ATP-Sensor-Assistent-Seite, auf der Sie die Zugriffstaste eingeben und dann auf die Schaltfläche "installieren" klicken sollten](../../media/mtp-eval-50.png)

10. Herzlichen Glückwunsch, Sie haben Azure Advanced Threat Protection erfolgreich auf Ihrem Domänencontroller konfiguriert.

    ![Image of_Azure Advanced Threat Protection Azure ATP-Sensor-Assistent-Installationsabschluss, in dem Sie auf die Schaltfläche Fertig stellen klicken sollten](../../media/mtp-eval-51.png)
 
11. Wählen Sie im Abschnitt [Azure Azure ATP](https://go.microsoft.com/fwlink/?linkid=2040449) -Einstellungen die Option **Windows Defender ATP**aus, und aktivieren Sie dann die Umschaltfläche. Klicken Sie auf **Speichern**. 

    ![Bild of_the Azure Azure ATP-Einstellungsseite, auf der Sie den Windows Defender ATP-Schalter aktivieren sollten](../../media/mtp-eval-52.png)

>[!NOTE]
>Windows Defender ATP wurde als Microsoft Defender ATP umbenannt. Das neubranding von Änderungen in allen Portalen wird für die Konsistenz eingeführt.


## <a name="configure-microsoft-cloud-app-security"></a>Konfigurieren der Microsoft Cloud-App-Sicherheit

>[!NOTE]
>Überspringen Sie diesen Schritt, wenn Sie Microsoft Cloud App Security bereits aktiviert haben. 

1. Navigieren Sie zu [Microsoft 365 Security Center](https://security.microsoft.com/info)  >  **Weitere Ressourcen**  >  **Microsoft Cloud-App-Sicherheit**.

   ![Image of_Microsoft 365-Sicherheits Center Seite, auf der Sie die Microsoft Cloud-App-Karte anzeigen und auf die Schaltfläche Öffnen klicken können](../../media/mtp-eval-53.png)

2. Wählen Sie an der Informations Aufforderung zur Integration von Azure ATP die Option **Azure ATP-Datenintegration aktivieren**aus.
  
   ![Bild of_the Informations Aufforderung zur Integration von Azure ATP, in der Sie den Link Azure ATP-Datenintegration aktivieren auswählen sollten](../../media/mtp-eval-54.png)

   > [!NOTE]
   > Wenn diese Eingabeaufforderung nicht angezeigt wird, kann dies bedeuten, dass Ihre Azure ATP-Datenintegration bereits aktiviert wurde. Wenn Sie sich jedoch nicht sicher sind, wenden Sie sich an Ihren IT-Administrator, um dies zu bestätigen. 

3. Wechseln Sie zu **Einstellungen**, aktivieren Sie die **Azure ATP Integration** Toggle, und klicken Sie dann auf **Speichern**. 

   ![Seite Image of_the Settings, auf der Sie die Azure ATP-Integration aktivieren und dann auf Speichern klicken.](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > Für neue Azure ATP-Instanzen wird diese Integrations Toggle automatisch aktiviert. Vergewissern Sie sich, dass Ihre Azure ATP-Integration aktiviert wurde, bevor Sie mit dem nächsten Schritt fortfahren.
 
4. Wählen Sie unter den Einstellungen für die Cloud-Ermittlung die Option **Microsoft Defender ATP-Integration**aus, und aktivieren Sie dann die Integration. Klicken Sie auf **Speichern**.

   ![Image of_the Microsoft Defender ATP-Seite, auf der das Kontrollkästchen nicht sanktionierte apps blockieren unter Microsoft Defender ATP-Integration ausgewählt ist. Klicken Sie auf speichern.](../../media/mtp-eval-56.png)

5. Wählen Sie unter Einstellungen für die Cloud-Ermittlung die Option **Benutzer Bereicherung**aus, und aktivieren Sie dann die Integration in Azure Active Directory.

   ![Bild des Abschnitts "Benutzer Anreicherung", in dem das Kontrollkästchen "ermittelte Benutzerbezeichner mit Azure Active Directory Benutzernamen erweitern" aktiviert ist](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-advanced-threat-protection"></a>Konfigurieren von Microsoft Defender Advanced Threat Protection

>[!NOTE]
>Überspringen Sie diesen Schritt, wenn Sie Microsoft Defender Advanced Threat Protection bereits aktiviert haben.

1. Navigieren Sie zu [Microsoft 365 Security Center](https://security.microsoft.com/info)  >  **Weitere Ressourcen**  >  **Microsoft Defender Security Center**. Klicken Sie auf **Öffnen**.

   ![Sicherheitscenter "Image of_Microsoft Defender" auf der Seite "Microsoft 365 Security Center"](../../media/mtp-eval-58.png)
 
2. Führen Sie den Microsoft Defender Advanced Threat Protection-Assistenten aus. Klicken Sie auf **Weiter**. 

   ![Seite "Image of_the Microsoft Defender Security Center-Willkommens Assistent"](../../media/mtp-eval-59.png)

3. Wählen Sie basierend auf dem bevorzugten Datenspeicherort, der Datenaufbewahrungsrichtlinie, der Organisationsgröße und dem Opt-in für Vorschau Features aus.

   ![Image of_the Page, um das Datenspeicher Land, die Aufbewahrungsrichtlinie und die Organisationsgröße auszuwählen. Klicken Sie auf Weiter, wenn Sie die Auswahl abgeschlossen haben.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > Einige Einstellungen wie der Datenspeicherort können anschließend nicht mehr geändert werden. 

   Klicken Sie auf **Weiter**. 

4. Klicken Sie auf **weiter** , und Sie wird Ihren Microsoft Defender ATP-Mandanten anbieten.

   ![Bild of_the Seite, die Sie anfordert, indem Sie auf die Schaltfläche Weiter klicken, um Ihre Cloud-Instanz zu erstellen](../../media/mtp-eval-61.png)

5. An Bord ihrer Endpunkte durch Gruppenrichtlinien, Microsoft Endpoint Manager oder durch Ausführen eines lokalen Skripts für Microsoft Defender ATP. Zur Vereinfachung verwendet dieses Handbuch das lokale Skript.

6. Klicken Sie auf **Paket herunterladen** , und kopieren Sie das Onboarding-Skript an Ihre (n) Endpunkte.

   ![Image of_page Sie auf die Schaltfläche Paket herunterladen klicken, um das Onboarding-Skript auf ihren Endpunkt oder ihre Endpunkte zu kopieren.](../../media/mtp-eval-62.png)

7. Führen Sie auf ihrem Endpunkt das Onboarding-Skript als Administrator aus, und wählen Sie Y aus. 

   ![Image of_the CommandLine, in der Sie das Onboarding-Skript ausführen, und wählen Sie Y, um fortzufahren.](../../media/mtp-eval-63.png)

8. Herzlichen Glückwunsch, Sie haben ihren ersten Endpunkt an Bord.

   ![Image of_the CommandLine, wo Sie die Bestätigung erhalten, dass Sie Ihren ersten Endpunkt an Bord haben. Drücken Sie eine beliebige Taste, um fortzufahren](../../media/mtp-eval-64.png)

9. Copy-fügen Sie den Erkennungstest aus dem Microsoft Defender ATP-Assistenten ein.

   ![Image of_the führen Sie einen Erkennungstest Schritt aus, in dem Sie auf Kopieren klicken sollten, um das Erkennungstest Skript zu kopieren, das Sie an der Eingabeaufforderung einfügen sollten.](../../media/mtp-eval-65.png)

10. Kopieren Sie das PowerShell-Skript an eine Eingabeaufforderung mit erhöhten Rechten, und führen Sie es aus. 

    ![Bild of_command Aufforderung, bei der das PowerShell-Skript in eine Eingabeaufforderung mit erhöhten Rechten kopiert und ausgeführt wird.](../../media/mtp-eval-66.png)

11. Wählen Sie im Assistenten die Option **mit Microsoft Defender ATP starten** aus.

    ![Bestätigungsaufforderung für Bild of_the aus dem Assistenten, auf der Sie mit Microsoft Defender ATP beginnen sollten](../../media/mtp-eval-67.png)
 
12. Besuchen Sie das [Microsoft Defender Security Center](https://securitycenter.windows.com/). Wechseln Sie zu **Einstellungen** , und wählen Sie dann **Erweiterte Funktionen**aus. 

    ![Image of_Microsoft Defender-Sicherheits Center-Einstellungsmenü, in dem Sie erweiterte Funktionen auswählen sollten](../../media/mtp-eval-68.png)

13. Aktivieren Sie die Integration in **Azure Advanced Threat Protection**.  

    ![Image of_Microsoft Defender Security Center erweiterte Funktionen, Azure Advanced Threat Protection Option Umschaltfläche, die Sie aktivieren müssen](../../media/mtp-eval-69.png)

14. Aktivieren Sie die Integration mit **Office 365 Threat Intelligence**.

    ![Erweiterte Features für Image of_Microsoft Defender Security Center, Office 365 Option Toggle für Threat Intelligence, die Sie aktivieren müssen](../../media/mtp-eval-70.png)

15. Aktivieren Sie die Integration in **Microsoft Cloud App Security**.

    ![Image of_Microsoft Defender Security Center erweiterte Funktionen, Microsoft Cloud App-Sicherheitsoption Umschaltfläche, die Sie aktivieren müssen](../../media/mtp-eval-71.png)

16. Scrollen Sie nach unten, und klicken Sie auf **Einstellungen speichern** , um die neuen Integrationen zu bestätigen.

    ![Schaltfläche "Bild of_Save Einstellungen", auf die Sie klicken müssen](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-threat-protection-service"></a>Microsoft Thread Protection-Dienst starten

>[!NOTE]
>Ab dem 1. Juni 2020 Microsoft Threat Protection-Features für alle berechtigten Mandanten automatisch aktiviert. Weitere Informationen finden Sie [in diesem Artikel Microsoft Tech Community on License Berechtigung](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) . 


Wechseln Sie zu [Microsoft 365 Security Center](https://security.microsoft.com/homepage). Navigieren Sie zu **Einstellungen** , und wählen Sie dann **Microsoft Threat Protection**aus.

![Screenshot der Option "Image of_Microsoft Threat Protection" auf der Seite "Microsoft 365 Security Center Settings" ](../../media/mtp-eval-72b.png) <br>

Eine umfassendere Anleitung finden Sie unter [Aktivieren von Microsoft Threat Protection](mtp-enable.md). 

Herzlichen Glückwunsch! Sie haben soeben Ihr Microsoft Threat Protection-Test Labor oder Ihre Pilotumgebung erstellt. Jetzt können Sie sich mit der Microsoft Threat Protection-Benutzeroberfläche vertraut machen. Erfahren Sie, was Sie im folgenden interaktiven Leitfaden für Microsoft Threat Protection erfahren und wie Sie die einzelnen Dashboards für Ihre täglichen Aufgaben im Zusammenarbeit mit dem Sicherheitsdienst verwenden können.


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

Als nächstes können Sie einen Angriff simulieren und sehen, wie die produktübergreifenden Funktionen erkennen, Warnungen erstellen und automatisch auf einen Datei übergreifenden Angriff auf einen Endpunkt reagieren.

## <a name="next-step"></a>Nächster Schritt
|![Angriffs Simulationsphase](../../media/mtp/run-sim.png) <br>[Angriffs Simulationsphase](mtp-pilot-simulate.md) | Führen Sie die Angriffssimulation für Ihre Microsoft Threat Protection-Pilotumgebung aus.
|:-------|:-----|
