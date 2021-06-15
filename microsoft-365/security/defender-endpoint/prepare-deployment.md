---
title: Vorbereiten der Bereitstellung von Microsoft Defender für Endpunkte
description: Vorbereiten der Genehmigung von Projektbeteiligten, Zeitplänen, Umgebungsaspekten und der Einführungsreihenfolge für die Bereitstellung von Microsoft Defender für Endpunkt
keywords: bereitstellen, vorbereiten, Projektbeteiligten, Zeitachse, Umgebung, Endpunkt, Server, Verwaltung, Einführung
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
ms.openlocfilehash: fb10e65258f6264b21851f8325b97b1bad19bf16
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925651"
---
# <a name="prepare-microsoft-defender-for-endpoint-deployment"></a>Vorbereiten der Bereitstellung von Microsoft Defender für Endpunkte

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Die Bereitstellung von Defender für Endpunkt ist ein dreistufiger Prozess:

| ![Bereitstellungsphase – Vorbereiten](images/phase-diagrams/prepare.png)<br>Phase 1: Vorbereiten | [![Bereitstellungsphase – Einrichtung](images/phase-diagrams/setup.png)](production-deployment.md)<br>[Phase 2: Setup](production-deployment.md) | [![Bereitstellungsphase – Onboarding](images/phase-diagrams/onboard.png)](onboarding.md)<br>[Phase 3: Onboarding](onboarding.md) |
| ----- | ----- | ----- |
|*Sie sind hier!* | ||


Sie befinden sich derzeit in der Vorbereitungsphase.


Die Vorbereitung ist der Schlüssel für eine erfolgreiche Bereitstellung. In diesem Artikel werden Sie zu den Punkten geführt, die Sie bei der Vorbereitung der Bereitstellung von Defender für Endpunkt berücksichtigen müssen.


## <a name="stakeholders-and-approval"></a>Projektbeteiligten und Genehmigung
Der folgende Abschnitt dient dazu, alle Projektbeteiligten zu identifizieren, die am Projekt beteiligt sind und genehmigt, überprüft oder auf dem Laufenden bleiben müssen.

Fügen Sie in der tabelle unten aufgeführte Projektbeteiligten nach Bedarf für Ihre Organisation hinzu.

-   SO = Projekt genehmigen

-   R = Überprüfen Sie dieses Projekt, und geben Sie Eingaben ein.

-   I = Über dieses Projekt informiert

| Name                 | Rolle                                                                                                                                                                                                          | Aktion |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| Geben Sie Namen und E-Mail ein. | **Chief Information Security Officer (CISO)** *Ein leitender Vertreter, der innerhalb der Organisation als Sponsor für die neue Technologiebereitstellung fungiert.*                                                  | Also     |
| Geben Sie Namen und E-Mail ein. | **Leiter des Cyber Defense Operations Centers (CDOC)** *Ein Vertreter des CDOC-Teams, der definiert, wie diese Änderung an die Prozesse im Sicherheitsteam des Kunden angepasst wird.*       | Also     |
| Geben Sie Namen und E-Mail ein. | **Sicherheitsarchitekt** *Ein Vertreter des Sicherheitsteams, der definiert, wie diese Änderung an die kernbezogene Sicherheitsarchitektur in der Organisation angepasst wird.*                         | R      |
| Geben Sie Namen und E-Mail ein. | **Workplace Architect** *Ein Vertreter des IT-Teams, der definiert, wie diese Änderung an die zentrale Arbeitsplatzarchitektur in der Organisation angepasst wird.*                             | R      |
| Geben Sie Namen und E-Mail ein. | **Sicherheitsanalyst** *Ein Vertreter des CDOC-Teams, der Beiträge zu den Erkennungsfunktionen, der Benutzererfahrung und der allgemeinen Nützlichkeit dieser Änderung aus Sicht des Sicherheitsbetriebs bereitstellen kann.* | I      |


## <a name="environment"></a>Umgebung 


Dieser Abschnitt wird verwendet, um sicherzustellen, dass Ihre Umgebung von den Projektbeteiligten tief verstanden wird, wodurch potenzielle Abhängigkeiten und/oder Änderungen identifiziert werden können, die in Technologien oder Prozessen erforderlich sind.

| Was                                  | Beschreibung |
|---------------------------------------|-------------|
| Endpunktanzahl                        |    Gesamtanzahl der Endpunkte nach Betriebssystem.         |
| Serveranzahl                          |    Gesamtanzahl der Server nach Betriebssystemversion.    |
| Verwaltungsmodul                     |    Name und Version des Verwaltungsmoduls (z. B. System Center Configuration Manager Current Branch 1803).         |
| CDOC-Verteilung                     |    Allgemeine CDOC-Struktur (z. B. Ebene 1, ausgelagert an Contoso, Ebene 2 und Stufe 3 im Unternehmen verteilt in Europa und Asien).         |
| Sicherheitsinformationen und -ereignis (SIEM) |    Siem-Technologie wird verwendet.         |


## <a name="role-based-access-control"></a>Rollenbasierte Zugriffssteuerung

Microsoft empfiehlt die Verwendung des Konzepts der geringsten Berechtigungen. Defender für Endpunkt nutzt integrierte Rollen innerhalb Azure Active Directory. Microsoft [empfiehlt, die verschiedenen verfügbaren Rollen](/azure/active-directory/active-directory-assign-admin-roles-azure-portal) zu überprüfen und die richtige Rolle auszuwählen, um Ihre Anforderungen für jede Persona für diese Anwendung zu erfüllen. Einige Rollen müssen möglicherweise vorübergehend angewendet und entfernt werden, nachdem die Bereitstellung abgeschlossen wurde.

| Personas                     | Rollen | Azure AD-Rolle (falls erforderlich) | Zuweisen zu |
|------------------------------|-------|-----------------------------|-----------|
| Sicherheitsadministrator       |       |                             |           |
| Sicherheitsanalyst             |       |                             |           |
| Endpunktadministrator       |       |                             |           |
| Infrastrukturadministrator |       |                             |           |
| Geschäftsinhaber/Interessengruppen   |       |                             |           |

Microsoft empfiehlt die Verwendung [von Privileged Identity Management,](/azure/active-directory/active-directory-privileged-identity-management-configure) um Ihre Rollen zu verwalten, um zusätzliche Überwachung, Kontrolle und Zugriffsüberprüfung für Benutzer mit Verzeichnisberechtigungen bereitzustellen.

Defender für Endpunkt unterstützt zwei Möglichkeiten zum Verwalten von Berechtigungen:

-   **Grundlegende Berechtigungsverwaltung:** Legen Sie Berechtigungen entweder auf Vollzugriff oder schreibgeschützt fest. Im Fall der einfachen Berechtigungsverwaltung haben Benutzer mit globaler Administrator- oder Sicherheitsadministratorrolle in Azure Active Directory Vollzugriff, während die Rolle "Sicherheitsleseberechtigter" schreibgeschützt ist.

-   **Rollenbasierte Zugriffssteuerung (RBAC):** Legen Sie granulare Berechtigungen fest, indem Sie Rollen definieren, Den Rollen Azure AD-Benutzergruppen zuweisen und den Benutzergruppen Zugriff auf Gerätegruppen gewähren. Weitere Informationen. siehe [Verwalten des Portalzugriffs mithilfe der rollenbasierten Zugriffssteuerung.](rbac.md)

Microsoft empfiehlt die Nutzung von RBAC, um sicherzustellen, dass nur Benutzer mit einer geschäftlichen Begründung auf Defender für Endpunkt zugreifen können.

Details zu Berechtigungsrichtlinien finden Sie hier: [Erstellen von Rollen und Zuweisen der Rolle zu einer Azure Active Directory Gruppe.](/microsoft-365/security/defender-endpoint/user-roles#create-roles-and-assign-the-role-to-an-azure-active-directory-group)

Die folgende Beispieltabelle dient zur Identifizierung der Cyber Defense Operations Center-Struktur in Ihrer Umgebung, mit der Sie die für Ihre Umgebung erforderliche RBAC-Struktur ermitteln können.

| Ebene   | Beschreibung                                                                                                                                                                                                 | Erforderliche Berechtigung |
|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
| Ebene 1 | **Lokales Sicherheitsteam/IT-Team**<br>Dieses Team triaget und untersucht in der Regel Warnungen, die in seiner Geolocation enthalten sind, und eskaliert zu Ebene 2 in Fällen, in denen eine aktive Korrektur erforderlich ist.                                              |                     |
| Ebene 2 | **Regionales Sicherheitsteam**<br>Dieses Team kann alle Geräte für seine Region sehen und Korrekturmaßnahmen ausführen.                                                                                                                        |        Anzeigen von Daten               |
| Ebene 3 | **Globales Sicherheitsteam**<br>Dieses Team besteht aus Sicherheitsexperten und ist berechtigt, alle Aktionen über das Portal anzuzeigen und auszuführen. | Anzeigen von Daten <br>  Warnungen Untersuchung Aktive Abhilfemaßnahmen <br> Warnungen Untersuchung Aktive Abhilfemaßnahmen <br> Verwalten von Portalsystemeinstellungen <br> Verwalten von Sicherheitseinstellungen |



## <a name="adoption-order"></a>Einführungsreihenfolge
In vielen Fällen verfügen Organisationen über vorhandene Endpunktsicherheitsprodukte. Jede Organisation sollte mindestens eine Antivirenlösung sein. In einigen Fällen hat eine Organisation möglicherweise auch bereits eine EDR Lösung eingefügt.

In der Vergangenheit war das Ersetzen von Sicherheitslösungen aufgrund der engen Einbindung in die Anwendungsschicht und Infrastrukturabhängigkeiten zeitaufwendig und schwierig zu erreichen. Da Defender für Endpunkt jedoch in das Betriebssystem integriert ist, ist es jetzt einfach, Lösungen von Drittanbietern zu ersetzen.

Wählen Sie die Komponente von Defender für Endpunkt aus, die verwendet werden soll, und entfernen Sie die nicht zutreffenden Komponenten. Die folgende Tabelle gibt die Reihenfolge an, die Microsoft für die Aktivierung der Endpunktsicherheitssuite empfiehlt.

| Komponente                               | Beschreibung                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Reihenfolge der Einführung |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
| Endpunkterkennung & Antwort (EDR)     | Die Funktionen von Defender für Endpunkt EDR bieten erweiterte Angriffserkennungen, die nahezu in Echtzeit und umsetzbar sind. Sicherheitsanalysten können Benachrichtigungen effektiv priorisieren, Einblick in den gesamten Umfang einer Sicherheitsverletzung erhalten und Aktionen ergreifen, um Bedrohungen zu beheben. <br> [Weitere Informationen.](/windows/security/threat-protection/windows-defender-atp/overview-endpoint-detection-response)                                                                                                                                                                                                                                             | 1                   |
|Bedrohungs- &-Sicherheitsrisikoverwaltung (Threat & Vulnerability Management, TVM)|Threat & Vulnerability Management ist eine Komponente von Microsoft Defender für Endpunkt und bietet Sicherheitsadministratoren und Sicherheitsteams einen einzigartigen Nutzen, einschließlich: <br> – Einblicke in Echtzeit EDR (EDR) korreliert mit Endpunkt-Sicherheitsrisiken <br> – Wertvoller Sicherheitsrisikokontext für Geräte während Vorfalluntersuchungen <br> – Integrierte Korrekturprozesse über Microsoft Intune und Microsoft System Center Configuration Manager <br> [Weitere Informationen](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Introducing-a-risk-based-approach-to-threat-and-vulnerability/ba-p/377845).| 2 |
| Schutz der nächsten Generation (NGP)        | Microsoft Defender Antivirus ist eine integrierte Antischadsoftwarelösung, die Schutz der nächsten Generation für Desktops, tragbare Computer und Server bietet. Microsoft Defender Antivirus umfasst: <br> – Über die Cloud bereitgestellter Schutz für die nahezu sofortige Erkennung und Blockierung neuer und neuer Bedrohungen. Zusammen mit maschinellem Lernen und Intelligent Security Graph gehört der von der Cloud bereitgestellte Schutz zu den Technologien der neuen Generation von Microsoft Defender Antivirus.   <br> – Always-On-Überprüfung mithilfe der erweiterten Überwachung des Datei- und Prozessverhaltens und anderer Heuristiken (auch als "Echtzeitschutz" bezeichnet). <br> – Dedizierte Schutzupdates, die auf maschinellem Lernen, menschlichen und automatisierten Big Data-Analysen und detaillierten Forschungen zum Schutz vor Bedrohungen basieren. <br> [Weitere Informationen](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).                                                                                                                                                                                                                                                                                                                                                                       |3                   |
| Attack Surface Reduction (ASR)          | Die Funktionen zur Verringerung der Angriffsfläche in Microsoft Defender für Endpunkt tragen dazu bei, die Geräte und Anwendungen in der Organisation vor neuen und neuen Bedrohungen zu schützen. <br> [Weitere Informationen.](/windows/security/threat-protection/windows-defender-atp/overview-attack-surface-reduction)                                                                                                                                                                                                                                                                                                                                                                                       | 4                    |
| Auto Investigation & Remediation (AIR)  | Microsoft Defender für Endpunkt verwendet automatisierte Untersuchungen, um die Anzahl der Warnungen, die einzeln untersucht werden müssen, erheblich zu reduzieren. Das Feature für die automatische Untersuchung nutzt verschiedene Überprüfungsalgorithmen und Prozesse, die von Analysten (z. B. Playbooks) verwendet werden, um Warnungen zu untersuchen und sofortige Korrekturmaßnahmen zur Behebung von Verstößen zu ergreifen. Auf diese Weise wird das Warnungsvolumen erheblich reduziert, sodass sich Sicherheitsexperten auf komplexere Bedrohungen und andere Initiativen mit hoher Wertschöpfung konzentrieren können. <br>[Weitere Informationen.](/windows/security/threat-protection/windows-defender-atp/automated-investigations-windows-defender-advanced-threat-protection) | Nicht zutreffend      |
| Microsoft-Bedrohungsexperten (MTE)          | Microsoft-Bedrohungsexperten ist ein verwalteter Suchdienst, der Security Operation Center (SOCs) mit Überwachung und Analyse auf Expertenebene bereitstellt, um sicherzustellen, dass kritische Bedrohungen in ihren einzigartigen Umgebungen nicht übersehen werden. <br>[Weitere Informationen.](/windows/security/threat-protection/windows-defender-atp/microsoft-threat-experts)                                                                                                                                                                                                                                                                                                                     | Nicht zutreffend      |

## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![Phase 2: Setup](images/setup.png) <br>[Phase 2: Setup](production-deployment.md) | Einrichten der Bereitstellung von Microsoft Defender für Endpunkt |
