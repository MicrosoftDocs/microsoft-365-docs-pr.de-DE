---
title: Vorbereiten Ihrer Microsoft 365 Defender-Testumgebung
description: Vorbereiten der Abmelde-, Zeitachsen, Umgebungsüberlegungen und der Einführungsreihenfolge beim Einrichten Ihrer Microsoft 365 Defender-Testumgebung oder Pilotumgebung
keywords: MTP-Testvorbereitung, MTP-Pilotvorbereitung, Vorbereitung für die Ausführung eines MTP-Pilotprojekts, Ausführen eines MTP-Pilotprojekts, Bereitstellen, Vorbereiten, Interessengruppen, Zeitachse, Umgebung, Endpunkt, Server, Verwaltung, Einführung
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
ms.openlocfilehash: f0e0bf29068bea0f213f8b00403213969f5b9106
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066751"
---
# <a name="prepare-your-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Vorbereiten Ihrer Microsoft 365 Defender-Testumgebung oder Pilotumgebung

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender

Das Erstellen einer Microsoft 365 Defender-Testumgebung oder Pilotumgebung und deren Bereitstellung ist ein drei phasenweiser Prozess:

|![Phase 1: Vorbereiten](../../media/phase-diagrams/prepare.png)<br/>Phase 1: Vorbereiten |[![Phase 2: Einrichten](../../media/phase-diagrams/setup.png)](setup-m365deval.md)<br/>[Phase 2: Einrichten](setup-m365deval.md) |[![Phase 3: Onboarding](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)<br/>[Phase 3: Onboarding](config-m365d-eval.md) | [![Zurück zum Pilotprojekt](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)<br/>[Zurück zum Testspielbuch](m365d-pilot.md) |
|--|--|--|--|
|*Sie sind hier!* | || |

Sie sind derzeit in der Vorbereitungsphase.


Die Vorbereitung ist der Schlüssel zu jeder erfolgreichen Bereitstellung. Dieser Abschnitt führt Sie durch das, was Sie bei der Vorbereitung der Erstellung einer Testumgebung oder Pilotumgebung für Ihre Microsoft 365 Defender-Bereitstellung berücksichtigen müssen.

## <a name="prerequisites"></a>Voraussetzungen
Erfahren Sie mehr über die Lizenzierungs-, Hardware- und Softwareanforderungen sowie andere Konfigurationseinstellungen für die Bereitstellung und Verwendung von Microsoft 365 Defender. Siehe die Mindestanforderungen für [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/prerequisites), [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements), Microsoft Defender für Office [365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description), [Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites), Microsoft Cloud App [Security](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites).

## <a name="stakeholders-and-sign-off"></a>Interessengruppen und Abmelden
Identifizieren Sie alle Interessengruppen, die an dem Projekt beteiligt sind und die möglicherweise abmelden, überprüfen oder auf dem Laufenden bleiben müssen, unabhängig davon, ob es sich um eine Evaluierung oder das Ausführen eines Pilotprojekts handelt.

>[!NOTE]
>Möglicherweise verfügen nicht alle Organisationen über die Fälligkeit der Sicherheitsorganisation, um über solche Rollen zu verfügen. Wenden Sie sich in diesem Fall an Ihr Führungsteam zur Überprüfung und Genehmigung von Kontorabilitäten.

Fügen Sie der tabelle unten aufgeführten Projektbeteiligten entsprechend Ihrer Organisation hinzu.

-   SO = Abmelden für dieses Projekt

-   R = Überprüfen dieses Projekts und Bereitstellen von Eingaben

-   I = Informiert über dieses Projekt

| Name                 | Rolle                                                                                                                                                                                                          | Aktion |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| Geben Sie Namen und E-Mail ein. | **Chief Information Security Officer (CISO)** Ein Leitender Vertreter, der innerhalb der Organisation als Sponsor für die *neue Technologiebereitstellung fungiert.*                                                  | Also     |
| Geben Sie Namen und E-Mail ein. | **Leiter des Cyber Defense Operations Center (CDOC)** Ein Vertreter des CDOC-Teams, der die Ausrichtung dieser Änderung an den Prozessen im Sicherheitsteam der Kunden *definiert.*       | Also     |
| Geben Sie Namen und E-Mail ein. | **Security Architect** Ein Vertreter des Sicherheitsteams, der für die Definition der Ausrichtung dieser Änderung an der zentralen Sicherheitsarchitektur *in der Organisation zuständig ist.*                         | R      |
| Geben Sie Namen und E-Mail ein. | **Workplace Architect** Ein Vertreter des IT-Teams, der für die Definition der Ausrichtung dieser Änderung an die zentrale Arbeitsplatzarchitektur *in der Organisation zuständig ist.*                             | R      |
| Geben Sie Namen und E-Mail ein. | **Security Analyst** Ein Vertreter des CDOC-Teams, der Feedback zu den Erkennungsfunktionen, der Benutzererfahrung und der allgemeinen Nützlichkeit dieser Änderung aus Sicht des *Sicherheitsbetriebs geben kann.* | I      |

## <a name="prepare-your-azure-active-directory"></a>Vorbereiten Ihres Azure Active Directory
Überspringen Sie diesen Schritt, wenn Sie die Synchronisierung zwischen Active Directory und Azure Active Directory bereits lokal aktiviert haben. Überprüfen Sie die vorhandene Dokumentation zu bewährten Methoden aus Azure Active Directory. Die folgenden Schritte sind für die Auswertung oder Ausführung eines Microsoft 365 Defender-Pilotprojekts optimiert.

1. Wechseln Sie zum [Azure Active Directory-Portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) > **Azure AD Connect**. 
![Abbildung der Azure Active Directory-Portalseite](../../media/mtp-eval-1.png) <br> 

2. Klicken **Sie auf Herunterladen** von Microsoft Azure Active Directory **Connect,** und übertragen Sie es an Ihren Domänencontroller.
![Abbildung der Azure Active Directoru Connect-Downloadseite](../../media/mtp-eval-2.png) <br>

3. Folgen Sie auf dem Domänencontroller dem Azure Active Directory Connect-Assistenten. Lesen Sie die Lizenzbedingungen und den Datenschutzhinweise, und aktivieren Sie das Kontrollkästchen, wenn Sie zustimmen. Klicken Sie auf **Weiter**.
![Bild der Azure AD Connect-Willkommensseite](../../media/mtp-eval-3.png) <br>

4. Navigieren Sie zu **Express-Einstellungen**.
![Bild der Seite "Express-Einstellungen"](../../media/mtp-eval-4.png) <br>

5. Geben Sie Ihre globalen Administratoranmeldeinformationen ein. Klicken Sie auf **Weiter**.
![Abbildung der Seite Herstellen einer Verbindung mit Azure AD, auf der Sie Ihre globalen Administratoranmeldeinformationen eingeben sollten](../../media/mtp-eval-5.png) <br>

6. Geben Sie Ihre Active Directory Domain Services-Unternehmensadministratoranmeldeinformationen ein. Klicken Sie auf **Weiter**.
![Abbildung der Ad DS-Seite verbinden, auf der Sie Ihre Anmeldeinformationen eingeben sollten](../../media/mtp-eval-6.png) <br>

7. Klicken **Sie auf Installieren,** um die Konfiguration zu bestätigen.
![Abbildung der Konfigurationsbestätigungsseite](../../media/mtp-eval-7.png) <br>

8. Herzlichen Glückwunsch, Sie haben Azure Active Directory Connect erfolgreich konfiguriert.
![Abbildung einer erfolgreich konfigurierten Azure Active Directory Connect-Seite](../../media/mtp-eval-8.png) <br>

Sie können nun [Benutzer und Gruppen zu Active Directory hinzufügen](/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) und eine [SAM-R-Richtlinie konfigurieren.](/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc)  


## <a name="configuration-order"></a>Konfigurationsreihenfolge
In der folgenden Tabelle ist die Reihenfolge aufgeführt, die Microsoft zum Konfigurieren der Microsoft 365 Defender-Komponenten für Ihre Testumgebungs- oder Pilotumgebungsbereitstellung empfiehlt.

| Komponente                               | Beschreibung                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Rangfolge der Konfigurationsreihenfolge |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
|Microsoft Defender für Office 365|Microsoft Defender für Office 365 schützt Ihre Organisation vor bösartigen Bedrohungen durch E-Mail-Nachrichten, Links (URLs) und Tools für die Zusammenarbeit. <br> [Weitere Informationen.](/microsoft-365/security/defender-365-security/defender-for-office-365)                                                                                                                                                                                                                                             | 1                   |
|Microsoft Defender for Identity|Microsoft Defender for Identity verwendet Active Directory-Signale, um erweiterte Bedrohungen, gefährdete Identitäten und schädliche Insideraktionen zu identifizieren, zu erkennen und zu untersuchen, die auf Ihre Organisation gerichtet sind. <br> [Weitere Informationen](/azure-advanced-threat-protection/).| 2 |
|Microsoft Cloud App Security| Microsoft Cloud App Security ist ein Cloud Access Security Broker (CASB), der auf mehreren Clouds arbeitet. Es bietet umfassende Sichtbarkeit, Kontrolle über Den Datenverkehr und ausgefeilte Analysen, um Cyberangriffe in allen Clouddiensten zu identifizieren und zu bekämpfen. <br> [Weitere Informationen](/cloud-app-security/).                                                                                                                                                                                                                                                                                                                                                                       |3                   |
|Microsoft Defender für Endpunkt | Die Microsoft Defender für Endpunkt-Funktionen für die Endpunkterkennung und Beantwortung bieten erweiterte Angriffserkennungen, die nahezu in Echtzeit umgesetzt werden können. Sicherheitsanalysten können Benachrichtigungen effektiv priorisieren, Einblick in den gesamten Umfang einer Verletzung erhalten und Aktionen ergreifen, um Bedrohungen zu beheben. <br> [Weitere Informationen.](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |4                    |                                                                                                                                                                                                                                    

## <a name="next-step"></a>Nächster Schritt
|![Phase 2: Setup](../../media/setup.png) <br>[Phase 2: Setup](setup-m365deval.md) | Einrichten Ihrer Microsoft 365 Defender-Testumgebung oder Pilotumgebung
|:-------|:-----|
