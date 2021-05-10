---
title: Vorbereiten der Bereitstellung von Microsoft Defender für Endpunkte
description: Vorbereiten der Genehmigung, Zeitachsen, Umgebungsüberlegungen und Einführungsreihenfolge bei der Bereitstellung von Microsoft Defender for Endpoint
keywords: Bereitstellen, Vorbereiten, Interessengruppen, Zeitachse, Umgebung, Endpunkt, Server, Verwaltung, Einführung
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e3df1286c69132c960c412f6f74512bb49c32b28
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52291043"
---
# <a name="prepare-microsoft-defender-for-endpoint-deployment"></a>Vorbereiten der Bereitstellung von Microsoft Defender für Endpunkte

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Die Bereitstellung von Defender for Endpoint ist ein drei phasenweiser Prozess:

| ![Bereitstellungsphase – Vorbereiten](images/phase-diagrams/prepare.png)<br>Phase 1: Vorbereiten | [![Bereitstellungsphase – Setup](images/phase-diagrams/setup.png)](production-deployment.md)<br>[Phase 2: Setup](production-deployment.md) | [![Bereitstellungsphase – onboard](images/phase-diagrams/onboard.png)](onboarding.md)<br>[Phase 3: Onboarding](onboarding.md) |
| ----- | ----- | ----- |
|*Sie sind hier!* | ||


Sie befinden sich derzeit in der Vorbereitungsphase.


Die Vorbereitung ist der Schlüssel zu jeder erfolgreichen Bereitstellung. In diesem Artikel werden Sie zu den Punkten geführt, die Sie bei der Vorbereitung der Bereitstellung von Defender for Endpoint berücksichtigen müssen.


## <a name="stakeholders-and-approval"></a>Interessengruppen und Genehmigung
Im folgenden Abschnitt werden alle Beteiligten identifiziert, die am Projekt beteiligt sind, und müssen genehmigt, überprüft oder auf dem Laufenden bleiben.

Fügen Sie der tabelle unten aufgeführten Projektbeteiligten entsprechend Ihrer Organisation hinzu.

-   SO = Projekt genehmigen

-   R = Überprüfen dieses Projekts und Bereitstellen von Eingaben

-   I = Informiert über dieses Projekt

| Name                 | Rolle                                                                                                                                                                                                          | Maßnahme |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| Geben Sie Namen und E-Mail ein. | **Chief Information Security Officer (CISO)** Ein Leitender Vertreter, der innerhalb der Organisation als Sponsor für die *neue Technologiebereitstellung fungiert.*                                                  | Also     |
| Geben Sie Namen und E-Mail ein. | **Leiter des Cyber Defense Operations Center (CDOC)** Ein Vertreter des CDOC-Teams, der die Ausrichtung dieser Änderung an den Prozessen im Sicherheitsteam der Kunden *definiert.*       | Also     |
| Geben Sie Namen und E-Mail ein. | **Security Architect** Ein Vertreter des Sicherheitsteams, der für die Definition der Ausrichtung dieser Änderung an der zentralen Sicherheitsarchitektur *in der Organisation zuständig ist.*                         | R      |
| Geben Sie Namen und E-Mail ein. | **Workplace Architect** Ein Vertreter des IT-Teams, der für die Definition der Ausrichtung dieser Änderung an die zentrale Arbeitsplatzarchitektur *in der Organisation zuständig ist.*                             | R      |
| Geben Sie Namen und E-Mail ein. | **Security Analyst** *Ein Vertreter des CDOC-Teams,* der Informationen zu Erkennungsfunktionen, Benutzererfahrung und gesamter Nützlichkeit dieser Änderung aus Sicht des Sicherheitsbetriebs bereitstellen kann. | I      |


## <a name="environment"></a>Umgebung 


Dieser Abschnitt wird verwendet, um sicherzustellen, dass Ihre Umgebung von den Beteiligten tief verstanden wird, wodurch potenzielle Abhängigkeiten und/oder Änderungen identifiziert werden, die in Technologien oder Prozessen erforderlich sind.

| Was                                  | Beschreibung |
|---------------------------------------|-------------|
| Anzahl der Endpunkte                        |    Gesamtanzahl der Endpunkte nach Betriebssystem.         |
| Serveranzahl                          |    Gesamtanzahl der Server nach Betriebssystemversion.    |
| Verwaltungsmodul                     |    Name und Version des Verwaltungsmoduls (z. B. System Center Configuration Manager Current Branch 1803).         |
| #A0                     |    High level CDOC structure (for example, Tier 1 outsourced to Contoso, Tier 2 and Tier 3 in-house distributed across Europe and Asia).         |
| Sicherheitsinformationen und -ereignisse (SIEM) |    SIEM-Technologie im Einsatz.         |


## <a name="role-based-access-control"></a>Rollenbasierte Zugriffssteuerung

Microsoft empfiehlt die Verwendung des Konzepts der geringsten Rechte. Defender for Endpoint nutzt integrierte Rollen innerhalb Azure Active Directory. Microsoft [empfiehlt, die verschiedenen verfügbaren](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal) Rollen zu überprüfen und die richtige zu wählen, um Ihre Anforderungen für jede Persona für diese Anwendung zu erfüllen. Einige Rollen müssen möglicherweise vorübergehend angewendet und entfernt werden, nachdem die Bereitstellung abgeschlossen wurde.

| Personas                     | Rollen | Azure AD Role (falls erforderlich) | Zuweisen zu |
|------------------------------|-------|-----------------------------|-----------|
| Sicherheitsadministrator       |       |                             |           |
| Security Analyst             |       |                             |           |
| Endpunktadministrator       |       |                             |           |
| Infrastrukturadministrator |       |                             |           |
| Geschäftsbesitzer/Stakeholder   |       |                             |           |

Microsoft empfiehlt die [Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) zum Verwalten Ihrer Rollen, um benutzern mit Verzeichnisberechtigungen zusätzliche Überwachung, Kontrolle und Zugriffsüberprüfung zu ermöglichen.

Defender for Endpoint unterstützt zwei Möglichkeiten zum Verwalten von Berechtigungen:

-   **Grundlegende Berechtigungsverwaltung:** Legen Sie Berechtigungen auf Vollzugriff oder schreibgeschützt. Im Fall der grundlegenden Berechtigungsverwaltung haben Benutzer mit der Rolle "Globaler Administrator" oder "Sicherheitsadministrator" in Azure Active Directory Vollzugriff, während die Rolle "Sicherheitsleser" über schreibgeschützten Zugriff verfügt.

-   **Rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC):** Legen Sie präzise Berechtigungen durch Definieren von Rollen, Zuweisen von Azure AD-Benutzergruppen zu den Rollen und Gewähren von Benutzergruppenzugriff auf Gerätegruppen. Weitere Informationen. Weitere [Informationen finden Sie unter Verwalten des Portalzugriffs mithilfe der rollenbasierten Zugriffssteuerung](rbac.md).

Microsoft empfiehlt die Nutzung von RBAC, um sicherzustellen, dass nur Benutzer mit einer geschäftlichen Begründung auf Defender for Endpoint zugreifen können.

Details zu Berechtigungsrichtlinien finden Sie [hier](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/user-roles#create-roles-and-assign-the-role-to-an-azure-active-directory-group).

In der folgenden Beispieltabelle wird die Cyber Defense Operations Center-Struktur in Ihrer Umgebung identifiziert, die Ihnen bei der Ermittlung der für Ihre Umgebung erforderlichen RBAC-Struktur hilft.

| Ebene   | Beschreibung                                                                                                                                                                                                 | Erforderliche Berechtigung |
|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
| Ebene 1 | **Lokales Sicherheitsteam/IT-Team**<br>Dieses Team untersucht in der Regel Warnungen, die in ihrer Geolocation enthalten sind, und eskaliert in Fällen, in denen eine aktive Korrektur erforderlich ist, auf Ebene 2.                                              |                     |
| Ebene 2 | **Team für regionale Sicherheitsvorgänge**<br>Dieses Team kann alle Geräte für seine Region sehen und Korrekturaktionen ausführen.                                                                                                                        |        Anzeigen von Daten               |
| Ebene 3 | **Team für globale Sicherheitsvorgänge**<br>Dieses Team besteht aus Sicherheitsexperten und ist autorisiert, alle Aktionen aus dem Portal zu sehen und durchzuführen. | Anzeigen von Daten <br>  Warnungsuntersuchung Aktive Korrekturaktionen <br> Warnungsuntersuchung Aktive Korrekturaktionen <br> Verwalten von Portalsystemeinstellungen <br> Verwalten von Sicherheitseinstellungen |



## <a name="adoption-order"></a>Adoptionsreihenfolge
In vielen Fällen verfügen Organisationen über vorhandene Endpunktsicherheitsprodukte. Das Mindeste, was jede Organisation hätte als Antivirenlösung verwenden müssen. In einigen Fällen hat eine Organisation jedoch möglicherweise bereits eine lösung EDR implantiert.

In der Vergangenheit war das Ersetzen einer Sicherheitslösung zeitintensiv und aufgrund der engen Hooks in die Anwendungsschicht und Infrastrukturabhängigkeiten schwierig. Da Defender for Endpoint jedoch in das Betriebssystem eingebaut ist, ist das Ersetzen von Drittanbieterlösungen jetzt einfach zu erreichen.

Wählen Sie die Komponente von Defender for Endpoint aus, die verwendet werden soll, und entfernen Sie die Komponenten, die nicht gelten. Die folgende Tabelle gibt die Reihenfolge an, die Microsoft für die Aktivierung der Endpunktsicherheitssuite empfiehlt.

| Komponente                               | Beschreibung                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Rang der Adoptionsreihenfolge |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
| Endpoint Detection & Response (EDR)     | Defender for Endpoint EDR bietet erweiterte Angriffserkennungen, die nahezu in Echtzeit und mit Aktionen verbunden sind. Sicherheitsanalysten können Benachrichtigungen effektiv priorisieren, Einblick in den gesamten Umfang einer Sicherheitsverletzung erhalten und Aktionen ergreifen, um Bedrohungen zu beheben. <br> [Weitere Informationen.](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/overview-endpoint-detection-response)                                                                                                                                                                                                                                             | 1                   |
|Threat & Vulnerability Management (TVM)|Threat & Vulnerability Management ist eine Komponente von Microsoft Defender for Endpoint und bietet sowohl Sicherheitsadministratoren als auch Sicherheitsbetriebsteams einen eindeutigen Wert, einschließlich: <br> – Echtzeit-EDR (EDR) mit Endpunktrisiken korreliert <br> – Unbezahlbarer Sicherheitsrisikokontext für Geräte bei Vorfalluntersuchungen <br> – Integrierte Korrekturprozesse über Microsoft Intune und Microsoft System Center Configuration Manager <br> [Weitere Informationen](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Introducing-a-risk-based-approach-to-threat-and-vulnerability/ba-p/377845).| 2 |
| Next-Generation Protection (NGP)        | Microsoft Defender Antivirus ist eine integrierte Antischantischantischungslösung, die Schutz der nächsten Generation für Desktops, tragbare Computer und Server bietet. Microsoft Defender Antivirus umfasst: <br> -Cloud-delivered protection for near-instant detection and blocking of new and emerging threats. Zusammen mit maschinellem Lernen und Intelligent Security Graph gehört der von der Cloud bereitgestellte Schutz zu den Technologien der neuen Generation von Microsoft Defender Antivirus.   <br> - Kontinuierliche Überprüfung mit erweiterter Datei- und Prozessverhaltensüberwachung und anderen Heuristiken (auch als "Echtzeitschutz" bezeichnet). <br> – Dedizierte Schutzupdates basierend auf maschinellem Lernen, humaner und automatisierter Big-Data-Analyse und detaillierter Forschung zur Bedrohungsabwehr. <br> [Weitere Informationen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).                                                                                                                                                                                                                                                                                                                                                                       |3                   |
| Attack Surface Reduction (ASR)          | Funktionen zur Reduzierung der Angriffsfläche in Microsoft Defender for Endpoint schützen die Geräte und Anwendungen in der Organisation vor neuen und neuen Bedrohungen. <br> [Weitere Informationen.](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/overview-attack-surface-reduction)                                                                                                                                                                                                                                                                                                                                                                                       | 4                    |
| Auto Investigation & Remediation (AIR)  | Microsoft Defender for Endpoint verwendet automatisierte Untersuchungen, um das Volumen der Warnungen, die einzeln untersucht werden müssen, erheblich zu reduzieren. Das Feature für die automatisierte Untersuchung nutzt verschiedene Überprüfungsalgorithmen und Prozesse, die von Analysten (z. B. Playbooks) verwendet werden, um Warnungen zu untersuchen und sofortige Abhilfemaßnahmen zur Behebung von Verstößen zu ergreifen. Auf diese Weise wird das Warnungsvolumen erheblich reduziert, sodass sich Sicherheitsexperten auf komplexere Bedrohungen und andere Initiativen mit hoher Wertschöpfung konzentrieren können. <br>[Weitere Informationen.](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/automated-investigations-windows-defender-advanced-threat-protection) | Nicht zutreffend      |
| Microsoft-Bedrohungsexperten (MTE)          | Microsoft-Bedrohungsexperten ist ein verwalteter Suchesdienst, der Security Operation Centers (SOCs) mit Überwachung und Analyse auf Expertenebene bietet, um sicherzustellen, dass kritische Bedrohungen in ihren einzigartigen Umgebungen nicht übersehen werden. <br>[Weitere Informationen.](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/microsoft-threat-experts)                                                                                                                                                                                                                                                                                                                     | Nicht zutreffend      |

## <a name="next-step"></a>Nächster Schritt

![Phase 2: Setup](images/setup.png) <br>[Phase 2: Setup](production-deployment.md) | Einrichten der Bereitstellung von Microsoft Defender for Endpoint

