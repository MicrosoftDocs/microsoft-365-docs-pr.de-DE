---
title: Vorbereiten ihrer Microsoft 365 Defender-Testumgebung
description: Vorbereiten der Anmeldung von Projektbeteiligten, Zeitplänen, Umgebungsaspekten und der Einführungsreihenfolge beim Einrichten Ihrer Microsoft 365 Defender-Testumgebung oder Pilotumgebung
keywords: Microsoft 365 Vorbereitung der Defender-Testversion, Microsoft 365 Vorbereitung des Defender-Pilotprojekts, Vorbereitung für die Ausführung eines Microsoft 365 Defender-Pilotprojekts, Ausführen eines Pilotprojekts Microsoft 365 Defender-Projekts, Bereitstellen, Vorbereiten, Projektbeteiligten, Zeitachse, Umgebung, Endpunkt, Server, Verwaltung, Einführung
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
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
ms.openlocfilehash: 7ebb7074b0e06eda96d21142044bd8b9997e094b
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841654"
---
# <a name="prepare-your-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Vorbereiten ihrer Microsoft 365 Defender-Testumgebung oder Pilotumgebung

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Das Erstellen einer Microsoft 365 Defender-Testumgebung oder -Pilotumgebung und deren Bereitstellung erfolgt in drei Phasen:

|![Phase 1: Vorbereiten](../../media/phase-diagrams/prepare.png)<br/>Phase 1: Vorbereiten |[![Phase 2: Einrichten](../../media/phase-diagrams/setup.png)](setup-m365deval.md)<br/>[Phase 2: Einrichten](setup-m365deval.md) |[![Phase 3: Onboarding](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)<br/>[Phase 3: Onboarding](config-m365d-eval.md) | [![Zurück zum Pilotprojekt](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)<br/>[Zurück zum Pilot-Playbook](m365d-pilot.md) |
|--|--|--|--|
|*Sie sind hier!* | || |

Sie befinden sich derzeit in der Vorbereitungsphase.


Die Vorbereitung ist der Schlüssel für eine erfolgreiche Bereitstellung. Dieser Abschnitt führt Sie durch das, was Sie bei der Vorbereitung auf die Erstellung einer Testumgebung oder Pilotumgebung für Ihre Microsoft 365 Defender-Bereitstellung berücksichtigen müssen.

## <a name="prerequisites"></a>Voraussetzungen
Erfahren Sie mehr über die Lizenzierungs-, Hardware- und Softwareanforderungen sowie andere Konfigurationseinstellungen für die Bereitstellung und Verwendung von Microsoft 365 Defender. Lesen Sie die Mindestanforderungen für [Microsoft 365 Defender](/microsoft-365/security/defender/prerequisites), Microsoft Defender [für Endpunkt](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements), Microsoft Defender für [Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description), Microsoft Defender [for Identity](/azure-advanced-threat-protection/atp-prerequisites), [Microsoft Cloud App Security](/azure-advanced-threat-protection/atp-prerequisites).

## <a name="stakeholders-and-sign-off"></a>Projektbeteiligten und Abmeldung
Identifizieren Sie alle Projektbeteiligten, die am Projekt beteiligt sind und die sich möglicherweise abmelden, überprüfen oder auf dem Laufenden bleiben müssen, sei es für die Evaluierung oder die Ausführung eines Pilotprojekts.

>[!NOTE]
>Möglicherweise verfügen nicht alle Organisationen über die Fälligkeit der Sicherheitsorganisation, solche Rollen zu haben. Wenden Sie sich in diesem Fall an Ihr Führungsteam, um Überprüfungs- und Genehmigungskonten zu besprechen.

Fügen Sie in der tabelle unten aufgeführte Projektbeteiligten nach Bedarf für Ihre Organisation hinzu.

-   SO = Anmeldung bei diesem Projekt

-   R = Überprüfen Sie dieses Projekt, und geben Sie Eingaben ein.

-   I = Über dieses Projekt informiert

| Name                 | Rolle                                                                                                                                                                                                          | Aktion |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| Geben Sie Namen und E-Mail ein. | **Chief Information Security Officer (CISO)** *Ein leitender Vertreter, der innerhalb der Organisation als Sponsor für die neue Technologiebereitstellung fungiert.*                                                  | Also     |
| Geben Sie Namen und E-Mail ein. | **Leiter des Cyber Defense Operations Centers (CDOC)** *Ein Vertreter des CDOC-Teams, der definiert, wie diese Änderung an die Prozesse im Sicherheitsteam des Kunden angepasst wird.*       | Also     |
| Geben Sie Namen und E-Mail ein. | **Sicherheitsarchitekt** *Ein Vertreter des Sicherheitsteams, der definiert, wie diese Änderung an die kernbezogene Sicherheitsarchitektur in der Organisation angepasst wird.*                         | R      |
| Geben Sie Namen und E-Mail ein. | **Workplace Architect** *Ein Vertreter des IT-Teams, der definiert, wie diese Änderung an die zentrale Arbeitsplatzarchitektur in der Organisation angepasst wird.*                             | R      |
| Geben Sie Namen und E-Mail ein. | **Sicherheitsanalyst** *Ein Vertreter des CDOC-Teams, der Feedback zu den Erkennungsfunktionen, der Benutzererfahrung und der allgemeinen Nützlichkeit dieser Änderung aus Sicht des Sicherheitsbetriebs geben kann.* | I      |

## <a name="prepare-your-azure-active-directory"></a>Vorbereiten der Azure Active Directory
Überspringen Sie diesen Schritt, wenn Sie die Synchronisierung zwischen Active Directory und Azure Active Directory lokal bereits aktiviert haben. Überprüfen Sie die vorhandene Dokumentation zu bewährten Methoden aus Azure Active Directory. Die folgenden Schritte sind optimiert, um ein Pilotprojekt Microsoft 365 Defender-Projekts auszuwerten oder auszuführen.

1. Wechseln Sie zum [Azure Active Directory-Portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) > **Azure AD-Verbinden.** 
![Abbildung Azure Active Directory Portalseite](../../media/mtp-eval-1.png) <br> 

2. Klicken Sie auf **"Von Microsoft Azure Active Directory Verbinden** **herunterladen",** und übertragen Sie sie an Ihren Domänencontroller.
![Abbildung der Downloadseite von Azure Active Directoru Verbinden](../../media/mtp-eval-2.png) <br>

3. Folgen Sie auf dem Domänencontroller dem Assistenten Azure Active Directory Verbinden. Lesen Sie die Lizenzbedingungen und den Datenschutzhinweis, und aktivieren Sie das Kontrollkästchen, wenn Sie damit einverstanden sind. Klicken Sie auf **Weiter**.
![Abbildung der Willkommensseite von Azure AD Verbinden](../../media/mtp-eval-3.png) <br>

4. Navigieren Sie zu **Express Einstellungen**.
![Abbildung der Express Einstellungen Seite](../../media/mtp-eval-4.png) <br>

5. Geben Sie Ihre globalen Administratoranmeldeinformationen ein. Klicken Sie auf **Weiter**.
![Abbildung der Verbinden auf der Azure AD-Seite, auf der Sie Ihre globalen Administratoranmeldeinformationen eingeben sollten](../../media/mtp-eval-5.png) <br>

6. Geben Sie Ihre Anmeldeinformationen für den Active Directory Domain Services-Unternehmensadministrator ein. Klicken Sie auf **Weiter**.
![Abbildung der Verbinden auf der AD DS-Seite, auf der Sie Ihre Anmeldeinformationen eingeben sollten](../../media/mtp-eval-6.png) <br>

7. Klicken Sie auf **"Installieren",** um die Konfiguration zu bestätigen.
![Abbildung der Seite zur Bestätigung der Konfiguration](../../media/mtp-eval-7.png) <br>

8. Herzlichen Glückwunsch, Sie haben Azure Active Directory Verbinden erfolgreich konfiguriert.
![Abbildung einer erfolgreich konfigurierten Azure Active Directory Verbinden Seite](../../media/mtp-eval-8.png) <br>

Sie können nun [Benutzer und Gruppen zu Active Directory hinzufügen](/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) und eine [SAM-R-Richtlinie konfigurieren.](/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc)  


## <a name="configuration-order"></a>Konfigurationsreihenfolge
In der folgenden Tabelle ist die Reihenfolge aufgeführt, die Microsoft für die Konfiguration der Microsoft 365 Defender-Komponenten für die Bereitstellung Ihrer Testumgebung oder Pilotumgebung empfiehlt.

| Komponente                               | Beschreibung                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Rang der Konfigurationsreihenfolge |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
|Microsoft Defender für Office 365|Microsoft Defender für Office 365 schützt Ihre Organisation vor bösartigen Bedrohungen durch E-Mail-Nachrichten, Links (URLs) und Tools für die Zusammenarbeit. <br> [Weitere Informationen.](/microsoft-365/security/office-365-security/defender-for-office-365)                                                                                                                                                                                                                                             | 1                   |
|Microsoft Defender for Identity|Microsoft Defender for Identity verwendet Active Directory-Signale, um erweiterte Bedrohungen, kompromittierte Identitäten und böswillige Insideraktionen gegen Ihre Organisation zu identifizieren, zu erkennen und zu untersuchen. <br> [Weitere Informationen](/azure-advanced-threat-protection/).| 2 |
|Microsoft Cloud App Security| Microsoft Cloud App Security ist ein Cloud Access Security Broker (CASB), der in mehreren Clouds ausgeführt wird. Es bietet umfassende Sichtbarkeit, Kontrolle über datenbasierte Reisen und komplexe Analysen, um Cyberbedrohungen in allen Ihren Clouddiensten zu erkennen und zu bekämpfen. <br> [Weitere Informationen](/cloud-app-security/).                                                                                                                                                                                                                                                                                                                                                                       |3                   |
|Microsoft Defender für Endpunkt | Die Microsoft Defender für Endpunkt-Funktionen für die Endpunkterkennung und Beantwortung bieten erweiterte Angriffserkennungen, die nahezu in Echtzeit umgesetzt werden können. Sicherheitsanalysten können Benachrichtigungen effektiv priorisieren, Einblick in den gesamten Umfang einer Verletzung erhalten und Aktionen ergreifen, um Bedrohungen zu beheben. <br> [Weitere Informationen.](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |4                    |                                                                                                                                                                                                                                    

## <a name="next-step"></a>Nächster Schritt
|![Phase 2: Setup](../../media/setup.png) <br>[Phase 2: Setup](setup-m365deval.md) | Einrichten Ihrer Microsoft 365 Defender-Testumgebung oder Pilotumgebung
|:-------|:-----|
