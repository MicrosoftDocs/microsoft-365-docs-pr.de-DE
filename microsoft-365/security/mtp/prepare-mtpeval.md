---
title: Vorbereiten Ihrer Microsoft 365 Defender Test Lab-Umgebung
description: Vorbereiten der Anmeldung von teilnehmenden, Zeitrahmen, Umgebungs Überlegungen und Adoptions Reihenfolge beim Einrichten Ihrer Microsoft 365 Defender Test Lab oder Pilotumgebung
keywords: MTP-Testvorbereitung, MTP-Pilotbereitstellung, Vorbereitung für das Ausführen eines MTP-Pilotprojekts, Ausführen eines Pilot-MTP-Projekts, bereitstellen, vorbereiten, Interessenvertreter, Zeitachse, Umgebung, Endpunkt, Server, Verwaltung, Einführung
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
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
ms.openlocfilehash: 7149524de868a3670807556f5f423ba0ee4a772a
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131265"
---
# <a name="prepare-your-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Vorbereiten des Testlabors oder der Pilotumgebung für den Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Das Erstellen eines Microsoft 365 Defender-Testlabors oder einer Pilotumgebung und deren Bereitstellung ist ein dreistufiger Prozess:

|![Phase 1: Vorbereiten](../../media/phase-diagrams/prepare.png)<br/>Phase 1: Vorbereiten |[![Phase 2: Einrichten](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)<br/>[Phase 2: Einrichten](setup-mtpeval.md) |[![Phase 3: Onboard](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)<br/>[Phase 3: Onboard](config-mtpeval.md) | [![Zurück zu Pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[Zurück zu Pilot Textbuch](mtp-pilot.md) |
|--|--|--|--|
|*Sie sind hier!* | || |

Sie befinden sich derzeit in der Vorbereitungsphase.


Die Vorbereitung ist für eine erfolgreiche Bereitstellung entscheidend. Dieser Abschnitt führt Sie durch die Schritte, die Sie bei der Vorbereitung der Erstellung einer Test Labor-oder Pilotumgebung für Ihre Microsoft 365 Defender-Bereitstellung überprüfen müssen.

## <a name="prerequisites"></a>Voraussetzungen
Erfahren Sie mehr über die Lizenzierungs-, Hardware-und Softwareanforderungen und andere Konfigurationseinstellungen für die Verwendung von Microsoft 365 Defender. Weitere Informationen finden Sie unter Mindestanforderungen für [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites), [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements), [Microsoft Defender for Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description), [Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites), [Microsoft Cloud App Security](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites).

## <a name="stakeholders-and-sign-off"></a>Interessengruppen und Abmelden
Identifizieren Sie alle Beteiligten, die an dem Projekt beteiligt sind und die sich möglicherweise für die Evaluierung oder die Ausführung eines Pilotprojekts anmelden, überprüfen oder informiert bleiben müssen.

>[!NOTE]
>Nicht alle Organisationen haben möglicherweise die Fälligkeit der Sicherheitsorganisation für solche Rollen. Wenden Sie sich in diesem Fall an Ihr Führungsteam unter Review and Approval Verantwortlichkeiten.

Hinzufügen von Beteiligten zur folgenden Tabelle entsprechend Ihrer Organisation

-   Also = Sign-off für dieses Projekt

-   R = dieses Projekt überprüfen und eingabebereit stellen

-   I = über dieses Projekt informiert

| Name                 | Rolle                                                                                                                                                                                                          | Aktion |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| Namen und e-Mail eingeben | **Chief Information Security Officer (CISO)** *ein Executive Representative, der innerhalb der Organisation als Sponsor für die neue Technologiebereitstellung fungiert.*                                                  | Also     |
| Namen und e-Mail eingeben | **Leiter des Cyber Defense Operations Center (Cdoc)** *ein Vertreter des Cdoc-Teams, das dafür verantwortlich ist, zu definieren, wie diese Änderung mit den Prozessen im Kunden-Sicherheits Betriebsteam abgeglichen wird.*       | Also     |
| Namen und e-Mail eingeben | **Security Architect** *ein Vertreter des Sicherheitsteams, das für die Definition dieser Änderung an der Kern Sicherheitsarchitektur in der Organisation verantwortlich ist.*                         | R      |
| Namen und e-Mail eingeben | **Arbeitsplatz Architekt** *ein Vertreter des IT-Teams, der dafür verantwortlich ist, zu definieren, wie diese Änderung an der zentralen Arbeitsplatz Architektur in der Organisation ausgerichtet ist.*                             | R      |
| Namen und e-Mail eingeben | **Security Analyst** *ein Vertreter des Cdoc-Teams, der aus Sicherheits betrieblichen Gründen Feedback zu den Erkennungsfunktionen, der Benutzererfahrung und zur allgemeinen Nützlichkeit dieser Änderung geben kann.* | I      |

## <a name="prepare-your-azure-active-directory"></a>Vorbereiten des Azure-Active Directory
Überspringen Sie diesen Schritt, wenn Sie die Synchronisierung zwischen Active Directory und Azure Active Directory lokal aktiviert haben. Lesen Sie die Dokumentation zu bewährten Methoden aus Azure Active Directory. Die folgenden Schritte sind optimiert, um ein Pilotprojekt von Microsoft 365 Defender auszuwerten oder auszuführen.

1. Wechseln Sie zum [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) -Portal > **Azure AD Connect**. 
![Bild von Azure Active Directory Portalseite](../../media/mtp-eval-1.png) <br> 

2. Klicken Sie auf **herunterladen** aus **Microsoft Azure Active Directory Connect** , und übertragen Sie Sie auf Ihren Domänen Controller.
![Bild der Azure Active Directoru Connect-Download Seite](../../media/mtp-eval-2.png) <br>

3. Führen Sie auf dem Domänencontroller den Azure Active Directory Connect-Assistenten aus. Lesen Sie die Lizenzbedingungen und die Datenschutzerklärung, und aktivieren Sie das Kontrollkästchen, wenn Sie zustimmen. Klicken Sie auf **Weiter**.
![Bild Azure AD Willkommensseite für Connect](../../media/mtp-eval-3.png) <br>

4. Navigieren Sie zu **Express Einstellungen**.
![Seite "Bild der Express-Einstellungen"](../../media/mtp-eval-4.png) <br>

5. Geben Sie Ihre globalen Administratoranmeldeinformationen ein. Klicken Sie auf **Weiter**.
![Image von Connect to Azure AD Page, auf der Sie Ihre globalen Administratoranmeldeinformationen eingeben sollten](../../media/mtp-eval-5.png) <br>

6. Geben Sie Ihre Active Directory-Domänendienste Anmeldeinformationen für den Unternehmensadministrator ein. Klicken Sie auf **Weiter**.
![Bild von Connect to AD DS Seite, auf der Sie Ihre Anmeldeinformationen eingeben sollten](../../media/mtp-eval-6.png) <br>

7. Klicken Sie auf **Installieren** , um die Konfiguration zu bestätigen.
![Seite "Bild der Konfigurations Bestätigung"](../../media/mtp-eval-7.png) <br>

8. Herzlichen Glückwunsch, Sie haben Azure Active Directory Connect erfolgreich konfiguriert.
![Bild einer erfolgreich konfigurierten Azure Active Directory Connect-Seite](../../media/mtp-eval-8.png) <br>

Sie können nun [Benutzer und Gruppen zu Active Directory hinzufügen](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) und [eine Sam-R-Richtlinie konfigurieren](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc).  


## <a name="configuration-order"></a>Konfigurations Reihenfolge
Die folgende Tabelle gibt die Bestellung an, die Microsoft für die Konfiguration der Microsoft 365 Defender-Komponenten für Ihre Test Labor-oder Pilot Umgebungs Bereitstellung empfiehlt.

| Komponente                               | Beschreibung                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Rangfolge der Konfigurations Reihenfolge |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
|Microsoft Defender für Office 365|Microsoft Defender für Office 365 schützt Ihre Organisation vor bösartigen Bedrohungen durch E-Mail-Nachrichten, Links (URLs) und Tools für die Zusammenarbeit. <br> [Weitere Informationen.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)                                                                                                                                                                                                                                             | 1                   |
|Microsoft Defender for Identity|Microsoft Defender for Identity verwendet Active Directory Signale, um erweiterte Bedrohungen, kompromittierte Identitäten und böswillige Insider Aktionen, die an Ihre Organisation gerichtet sind, zu identifizieren, zu erkennen und zu untersuchen. <br> [Weitere Informationen](https://docs.microsoft.com/azure-advanced-threat-protection/).| 2 |
|Microsoft Cloud App Security| Microsoft Cloud App Security ist ein Cloud Access Security Broker (CASB), der in mehreren Clouds arbeitet. Es bietet umfangreiche Sichtbarkeit, Kontrolle über Daten Reisen und ausgefeilte Analysen, um Bedrohungen für alle Cloud-Dienste zu identifizieren und zu bekämpfen. <br> [Weitere Informationen](https://docs.microsoft.com/cloud-app-security/).                                                                                                                                                                                                                                                                                                                                                                       |3                   |
|Microsoft Defender für Endpunkt | Die Erkennungs-und Antwortfunktionen von Microsoft Defender für Endpunkt Endpunkt bieten erweiterte Angriffs Erkennungen, die in der Nähe von Echtzeit-und aktionsfähig sind. Sicherheitsanalysten können Benachrichtigungen effektiv priorisieren, Einblick in den gesamten Umfang einer Verletzung erhalten und Aktionen ergreifen, um Bedrohungen zu beheben. <br> [Weitere Informationen.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |4                    |                                                                                                                                                                                                                                    

## <a name="next-step"></a>Nächster Schritt
|![Phase 2: Setup](../../media/setup.png) <br>[Phase 2: Setup](setup-mtpeval.md) | Einrichten Ihrer Microsoft 365 Defender Test Lab-oder Pilotumgebung
|:-------|:-----|

