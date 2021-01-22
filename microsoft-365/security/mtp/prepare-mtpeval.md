---
title: Vorbereiten der Microsoft 365 Defender-Testumgebung
description: Vorbereiten der Anmeldung von Beteiligten, Zeitachsen, Überlegungen zur Umgebung und der Einführungsreihenfolge beim Einrichten Ihrer Microsoft 365 Defender-Testumgebung oder Pilotumgebung
keywords: MTP-Testvorbereitung, MTP-Pilotvorbereitung, Vorbereitung für die Ausführung eines MTP-Pilotprojekts, Ausführen eines MTP-Pilotprojekts, Bereitstellen, Vorbereiten, Projektbeteiligten, Zeitachse, Umgebung, Endpunkt, Server, Verwaltung, Einführung
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 35f1d3f0b5cefb0f14508571511449fc2c7d58a9
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930150"
---
# <a name="prepare-your-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Vorbereiten ihrer Microsoft 365 Defender-Testumgebung oder -Pilotumgebung

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Das Erstellen einer Microsoft 365 Defender-Testumgebung oder -Pilotumgebung und deren Bereitstellung besteht aus drei Phasen:

|![Phase 1: Vorbereiten](../../media/phase-diagrams/prepare.png)<br/>Phase 1: Vorbereiten |[![Phase 2: Einrichten](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)<br/>[Phase 2: Einrichten](setup-mtpeval.md) |[![Phase 3: Onboarding](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)<br/>[Phase 3: Onboarding](config-mtpeval.md) | [![Zurück zum Pilotprojekt](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[Zurück zum Pilot-Playbook](mtp-pilot.md) |
|--|--|--|--|
|*Sie sind hier!* | || |

Sie sind derzeit in der Vorbereitungsphase.


Die Vorbereitung ist für eine erfolgreiche Bereitstellung entscheidend. Dieser Abschnitt führt Sie durch die Informationen, die Sie bei der Vorbereitung der Erstellung einer Testumgebung oder Pilotumgebung für Ihre Microsoft 365 Defender-Bereitstellung berücksichtigen müssen.

## <a name="prerequisites"></a>Voraussetzungen
Erfahren Sie mehr über die Lizenzierungs-, Hardware- und Softwareanforderungen sowie andere Konfigurationseinstellungen zum Bereitstellen und Verwenden von Microsoft 365 Defender. Siehe die Mindestanforderungen für [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites), [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements), Microsoft Defender für Office [365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description), [Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites), Microsoft Cloud App [Security](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites).

## <a name="stakeholders-and-sign-off"></a>Projektbeteiligten und Abmelden
Identifizieren Sie alle Projektbeteiligten, die am Projekt beteiligt sind, und wer sich abmelden, überprüfen oder auf dem Laufenden bleiben muss, sei es zur Evaluierung oder zum Ausführen eines Pilotprojekts.

>[!NOTE]
>Möglicherweise verfügen nicht alle Organisationen über die Fälligkeit einer Sicherheitsorganisation, über solche Rollen zu verfügen. Wenden Sie sich in diesem Fall an Ihr Führungsteam zur Überprüfung und Genehmigung von Konten.

Fügen Sie der nachstehenden Tabelle Projektbeteiligten hinzu, wenn dies für Ihre Organisation geeignet ist.

-   SO = Abmelden für dieses Projekt

-   R = Überprüfen Sie dieses Projekt, und geben Sie Eingaben an.

-   I = Informiert über dieses Projekt

| Name                 | Rolle                                                                                                                                                                                                          | Aktion |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| Geben Sie Den Namen und die E-Mail ein. | **Chief Information Security Officer (CISO)** Ein leitender Vertreter, der innerhalb der Organisation als Sponsor für *die neue Technologiebereitstellung fungiert.*                                                  | Also     |
| Geben Sie Den Namen und die E-Mail ein. | **Leiter des Cyber Defense Operations Centers (CDOC)** Ein Vertreter des CDOC-Teams, der für die Definition der Ausrichtung dieser Änderung an den Prozessen im Sicherheitsteam der Kunden *zuständig ist.*       | Also     |
| Geben Sie Den Namen und die E-Mail ein. | **Security Architect** *A representative from the Security team in charge of defining how this change is aligned with the core Security architecture in the organization.*                         | R      |
| Geben Sie Den Namen und die E-Mail ein. | **Workplace Architect** *A representative from the IT team in charge of defining how this change is aligned with the core workplace architecture in the organization.*                             | R      |
| Geben Sie Den Namen und die E-Mail ein. | **Security Analyst** *A representative from the CDOC team who can provide feedback on the detection capabilities, user experience, and overall usefulness of this change from a security operations perspective.* | I      |

## <a name="prepare-your-azure-active-directory"></a>Vorbereiten ihres Azure Active Directory
Überspringen Sie diesen Schritt, wenn Sie die Synchronisierung zwischen Active Directory und Azure Active Directory lokal bereits aktiviert haben. Überprüfen Sie die vorhandene Dokumentation zu bewährten Methoden aus Azure Active Directory. Die folgenden Schritte sind für die Evaluierung oder Ausführung eines Microsoft 365 -Pilotprojekts optimiert.

1. Wechseln Sie zum [Azure Active Directory-Portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) > **Azure AD Connect**. 
![Abbildung der Azure Active Directory-Portalseite](../../media/mtp-eval-1.png) <br> 

2. Klicken **Sie auf "Von** **Microsoft Azure Active Directory Connect herunterladen",** und übertragen Sie es auf Ihren Domänencontroller.
![Abbildung der Azure Active Directoru Connect-Downloadseite](../../media/mtp-eval-2.png) <br>

3. Folgen Sie auf dem Domänencontroller dem Azure Active Directory Connect-Assistenten. Lesen Sie die Lizenzbedingungen und den Datenschutzhinweise, und aktivieren Sie das Kontrollkästchen, wenn Sie zustimmen. Klicken Sie auf **Weiter**.
![Abbildung der Azure AD Connect-Willkommensseite](../../media/mtp-eval-3.png) <br>

4. Navigieren Sie zu **"Express-Einstellungen".**
![Abbildung der Seite "Express-Einstellungen"](../../media/mtp-eval-4.png) <br>

5. Geben Sie Ihre anmeldeinformationen für den globalen Administrator ein. Klicken Sie auf **Weiter**.
![Abbildung der Seite "Verbindung mit Azure AD herstellen", auf der Sie Ihre anmeldeinformationen für den globalen Administrator eingeben sollten](../../media/mtp-eval-5.png) <br>

6. Geben Sie die Anmeldeinformationen des Active Directory Domain Services-Unternehmensadministrators ein. Klicken Sie auf **Weiter**.
![Abbildung der Ad DS-Seite, auf der Sie Ihre Anmeldeinformationen eingeben sollten](../../media/mtp-eval-6.png) <br>

7. Klicken **Sie auf "Installieren",** um die Konfiguration zu bestätigen.
![Abbildung der Seite "Konfigurationsbestätigung"](../../media/mtp-eval-7.png) <br>

8. Herzlichen Glückwunsch, Sie haben Azure Active Directory Connect erfolgreich konfiguriert.
![Abbildung einer erfolgreich konfigurierten Azure Active Directory Connect-Seite](../../media/mtp-eval-8.png) <br>

Sie können nun [Benutzer und Gruppen zu Active Directory hinzufügen](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) und eine [SAM-R-Richtlinie konfigurieren.](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc)  


## <a name="configuration-order"></a>Konfigurationsreihenfolge
Die folgende Tabelle gibt die Reihenfolge an, die Microsoft für die Konfiguration der Microsoft 365 -Defender-Komponenten für Ihre Testumgebungs- oder Pilotumgebungsbereitstellung empfiehlt.

| Komponente                               | Beschreibung                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Rang der Konfigurationsreihenfolge |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
|Microsoft Defender für Office 365|Microsoft Defender für Office 365 schützt Ihre Organisation vor bösartigen Bedrohungen durch E-Mail-Nachrichten, Links (URLs) und Tools für die Zusammenarbeit. <br> [Weitere Informationen.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)                                                                                                                                                                                                                                             | 1                    |
|Microsoft Defender for Identity|Microsoft Defender for Identity verwendet Active Directory-Signale, um fortgeschrittene Bedrohungen, gefährdete Identitäten und böswillige Insideraktionen zu identifizieren, zu erkennen und zu untersuchen, die gegen Ihre Organisation gerichtet sind. <br> [Weitere Informationen](https://docs.microsoft.com/azure-advanced-threat-protection/).| 2  |
|Microsoft Cloud App-Sicherheit| Microsoft Cloud App Security ist ein Cloud Access Security Broker (CASB), der auf mehreren Clouds funktioniert. Es bietet umfassende Sichtbarkeit, Kontrolle über den Datenverkehr und komplexe Analysen, um Cyberbedrohungen in allen Ihren Clouddiensten zu identifizieren und zu bekämpfen. <br> [Weitere Informationen](https://docs.microsoft.com/cloud-app-security/).                                                                                                                                                                                                                                                                                                                                                                       |3                   |
|Microsoft Defender für Endpunkt | Die Erkennungs- und Antwortfunktionen von Microsoft Defender für Endpunkte bieten erweiterte Angriffserkennungen, die nahezu in Echtzeit verfügbar und umsetzbar sind. Sicherheitsanalysten können Benachrichtigungen effektiv priorisieren, Einblick in den gesamten Umfang einer Verletzung erhalten und Aktionen ergreifen, um Bedrohungen zu beheben. <br> [Weitere Informationen.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |4                    |                                                                                                                                                                                                                                    

## <a name="next-step"></a>Nächster Schritt
|![Phase 2: Einrichten](../../media/setup.png) <br>[Phase 2: Einrichten](setup-mtpeval.md) | Einrichten ihrer Microsoft 365 Defender-Testumgebung oder -Pilotumgebung
|:-------|:-----|

