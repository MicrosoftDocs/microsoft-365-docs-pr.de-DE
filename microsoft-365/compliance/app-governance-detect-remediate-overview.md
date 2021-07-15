---
title: Informationen zu Erkennung und Behebung von App-Bedrohungen
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Erfahren Sie mehr zur Erkennung und Behebung von App-Bedrohungen.
ms.openlocfilehash: 26cd8501fdd8bd828357f8adb7d4e90f96e70114
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420172"
---
# <a name="learn-about-app-threat-detection-and-remediation"></a>Informationen zu Erkennung und Behebung von App-Bedrohungen

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

Mit der Microsoft App-Governance können Sie:

- Die Bedrohungsbenachrichtigungen einfach überwachen, die durch systemeigene App-Governance-Erkennungsmethoden für Aktivitäten bösartiger Apps erzeugt werden, und richtlinienbasierte Benachrichtigungen, die durch von Ihnen erstellte aktive App-Richtlinien erzeugt werden. Diese Benachrichtigungen können auf Anomalien in der App-Aktivität hinweisen, und wenn nicht konforme, schädliche oder riskante Apps verwendet werden.  Sie können auch Muster in Benachrichtigungen verwenden, um neue App-Richtlinien zu erstellen, oder die Einstellungen vorhandener Richtlinien für restriktivere Aktionen zu ändern.
- Die Benachrichtigungen einfach beheben, entweder manuell nach der Untersuchung oder automatisch über die Aktionseinstellungen für aktive App-Richtlinien.


>[!Note]
>Anomale Aktivitäten von nur-Azure-Apps, denen keine Berechtigungen für den Zugriff auf Microsoft 365-Ressourcen gewährt wurden, sind in der Erkennung und Benachrichtigung der App-Governance nicht enthalten.
>

Sehen Sie sich an, welche [Administratorrollen](app-governance-get-started.md#administrator-roles) auf die App-Governance-Seiten zugreifen können.


## <a name="app-governance-integration-with-azure-active-directory-and-microsoft-cloud-app-security"></a>App-Governance-Integration mit Azure Active Directory und Microsoft Cloud App Security

App-Governance, Azure Active Directory (Azure AD) und Microsoft Cloud App Security sammeln verschiedene Datasets und stellen diese bereit:

- Azure AD stellt grundlegende App-Metadaten und detaillierte Informationen zu Anmeldungen bei Apps bereit.
- App-Governance bietet detaillierte Informationen zur Aktivität einer App auf API-Ebene.
- Microsoft Cloud App Security stellt Informationen zum App-Risiko bereit.

Indem Sie Informationen über App-Governance, Azure AD und Microsoft Cloud App Security teilen, können Sie aggregierte Informationen in einem Portal anzeigen und mühelos eine Verknüpfung mit einem anderen Portal herstellen, um weitere Informationen zu erhalten. Hier sind einige Beispiele:

- Informationen zu App-Anmeldungen in App-Governance:

  Im App-Governance-Portal können Sie die aggregierte Anmeldeaktivität für jede App anzeigen, und einen Link zurück zum Azure Active Directory Admin Center erstellen, um Details zu Anmeldeereignissen zu erhalten.

- App-API-Nutzungsinformationen im Azure Active Directory Admin Center:

  Im Azure Active Directory Admin Center können Sie die aggregierten App-Nutzungsinformationen sehen, und einen Link zum App-Governance-Portal für die Details der App-Nutzung erstellen.

- API-Nutzungsinformationen im Microsoft Cloud App Security-Portal: 

  Im Microsoft Cloud App Security-Portal können Sie die API-Nutzungsebene und aggregierte Datenübertragungen anzeigen, sowie über einen Link zum App-Governance-Portal mit weiteren Details zugreifen.

Nachfolgend finden Sie eine Zusammenfassung der Integration.

![Die Integration von App-Governance mit Azure AD und Microsoft Cloud App Security](..\media\manage-app-protection-governance\mapg-integration.png)

Zusätzlich sendet App-Governance seine Warnungen als Signale an Microsoft Cloud App Security und Microsoft 365 Defender für eine detailliertere Analyse von App-basierten Sicherheitsvorfällen.

<!--

CFA #3 Scenario 1:  As an admin, I can investigate alerts associated to my M365 apps through MAPG.
CFA #3 Scenario 2: As an admin, I can manually remediate 
CFA #3 Scenario 3: As an admin, I can configure policies to perform automatic 
--> 

## <a name="next-step"></a>Nächster Schritt

[Beginnen Sie mit der App-Bedrohungserkennung und -Behebung.](app-governance-detect-remediate-get-started.md)
