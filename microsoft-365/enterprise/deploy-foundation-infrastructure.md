---
title: Microsoft 365 Enterprise-Foundation-Infrastruktur
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/22/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen Sie die Hauptphasen der Bereitstellung der Foundation-Infrastruktur für Microsoft 365 Enterprise in Ihrer Organisation, auch bekannt als die zentrale Bereitstellung.
ms.openlocfilehash: 0c683f771609c847556f82fe84a17dad13ee34d4
ms.sourcegitcommit: d9b462e035416bfa4b3d42467902c75859c55381
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2019
ms.locfileid: "36055021"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure"></a>Microsoft 365 Enterprise-Foundation-Infrastruktur

Wenn Sie die End-to-End-Bereitstellung von Microsoft 365 Enterprise selbst durchführen, sollten Sie zunächst eine solide Grundlage schaffen, auf der Anwendungen und Dienste Kreativität und Teamarbeit in einer sicheren Umgebung freisetzen können. Diese Grundlage wird manchmal als die *zentrale Bereitstellung* bezeichnet.

Für einen definierten End-to-End-Pfad für die Bereitstellung können Sie diese Phasen verwenden, um die Basisinfrastruktur von Microsoft 365 Enterprise zu planen und bereitzustellen:

| | Phase | Ergebnisse |
|:-------|:-----|:-----|
|![](./media/deploy-foundation-infrastructure/networking_icon-small.png)|[Phase 1: Netzwerke](networking-infrastructure.md)| Ihr Netzwerk ist für den Zugriff auf die cloudbasiert Dienste von Microsoft 365 optimiert. |
|![](./media/deploy-foundation-infrastructure/identity_icon-small.png)|[Phase 2: Identität](identity-infrastructure.md)| Ihre Admin-Konten sind geschützt, Ihre Benutzer und Gruppen sind synchronisiert, und Ihre Benutzerauthentifizierung ist stark. |
|![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)|[Phase 3: Windows 10 Enterprise](windows10-infrastructure.md)| Ihre vorhandenen Windows-basierten Computer können auf Windows 10 Enterprise aktualisiert werden, und neue Geräte sind mit Windows 10 Enterprise ausgestattet. |
|![](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)|[Phase 4: Office 365 ProPlus](office365proplus-infrastructure.md)| Ihre vorhandenen Benutzer von Microsoft Office können ein Upgrade auf Office 365 ProPlus durchführen. |
|![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)|[Phase 5: Verwaltung mobiler Geräte](mobility-infrastructure.md)| Ihre Geräte können registriert und verwaltet werden. |
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)|[Phase 6: Information Protection](infoprotect-infrastructure.md)| Ihre Bezeichnungen sind bereit, Dokumente zu schützen, und Office 365-Sicherheitsfunktionen sind aktiviert. |

Die Phasen beginnen mit den grundlegendsten Elementen (Netzwerk und Identität), und erstellen dann Schichten von Infrastruktur-Einstellungen und Gruppen zu:

- Installieren Sie die aktuellste und sicherste Version von Windows auf Ihren Geräten.
- Installieren Sie die aktuellste Version von Microsoft Office auf Ihren Geräten.
- Verwalten Sie die Geräte Ihrer Organisation.
- Schützen Sie die Informationen auf diesen Geräten und in der Cloud.

Sie haben jedoch die Flexibilität, die Phasen oder Schritte innerhalb der Phasen zu konfigurieren und bereitzustellen, um sie Ihren IT-Ressourcen und Geschäftsanforderungen anzupassen.

- **Wenn Sie eine kleinere oder neueren Organisation sind**, folgen Sie den Phasen, die erforderlich sind, um Ihre Infrastruktur methodisch aufzubauen.

-  **Wenn Sie eine Unternehmensorganisation sind**, betrachten Sie die Phasen als Schichten der IT-Infrastruktur und nicht als einen definierten Pfad, und bestimmen Sie, wie Sie am besten auf die Einhaltung der Anforderungen für jede Schicht in Ihrer Organisation hinarbeiten können.

Am Ende jeder Phase sollten Sie die Beendigungskriterien prüfen, einschließlich der erforderlichen Bedingungen, die Sie erfüllen müssen, und der optionalen Bedingungen, die Sie berücksichtigen müssen. Die Beendigungskriterien für jede Phase stellen sicher, dass Ihre lokale und Cloud-Infrastruktur und die daraus resultierende End-to-End-Konfiguration die Anforderungen für eine Microsoft 365 Enterprise Bereitstellung erfüllen.

Um zu erfahren, wie der Inhalt strukturiert ist, schauen Sie sich dieses kurze Video an.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE23VRG]

Hier ist die Foundation-Infrastruktur im gesamten Microsoft 365 Enterprise Bereitstellungshandbuch:

![](./media/deploy-foundation-infrastructure/m365-deploy-content-arch-foundation.png)

## <a name="at-a-glance"></a>Auf einen Blick

Das [Poster "Microsoft 365 Enterprise-Foundation-Infrastruktur"](http://aka.ms/m365efoundinfraposter) bietet einen gute Übersicht über die einzelnen Phasen:

- Allgemeinen Ziele der Phase für Administratoren und Benutzer
- Dienste, Features und Tools
- Wichtige Entwurfsentscheidungen für die Planung
- Konfigurationsergebnisse
- Vorgehensweise für das Onboarding eines neuen Benutzers
- Überwachen und Aktualisieren

![](./media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.png)

Zum Herunterladen einer Kopie des Posters klicken Sie [hier](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.pdf).


## <a name="infrastructure-configuration-vs-user-rollout"></a>Konfiguration der Infrastruktur vs. Benutzer-Rollout

Die Foundation-Infrastruktur besteht aus einer Reihe von konfigurierter Software und Diensten, die wenn kombiniert, es einem Benutzer ermöglichen, das gesamte Spektrum der Funktionen und Schutzmaßnahmen von Microsoft 365 Enterprise zu nutzen. Das ultimative Ziel Ihrer End-to-End-Bereitstellung ist es, dass diese Infrastruktur für alle Ihre Benutzer und deren Windows-basierte Geräte verfügbar ist. 

Es ist jedoch wichtig zu beachten, dass die Microsoft 365 Enterprise Foundation-Infrastruktur unabhängig vom Rollout von Software und Diensten für Ihre Benutzer ist. ***Sie können die Schichten der Foundation-Infrastruktur konfigurieren, ohne diese Schichten für alle Ihre Benutzer bereitstellen zu müssen.***

Daher ist es möglich, Elemente der Foundation-Infrastruktur weit vor dem Rollout dieser Elemente für die Vielzahl Ihrer Benutzer in den Büros, Regionen oder Abteilungen Ihrer Organisation zu konfigurieren und zu testen.

Beispielsweise erstellen Sie die Einstellungen für:

| Phase | Ergebnisse |
|:-------|:-----|
| Identität | Kontosynchronisierung und Gruppen für identitätsbasierte Richtlinien für bedingten Zugriff. |
| Windows 10 Enterprise | Gruppen, die automatisch Computer mit Windows 7 oder Windows 8.1 auf Windows 10 Enterprise aktualisieren. |
| Office 365 ProPlus | Gruppen, die Office 365 ProPlus automatisch für Benutzer mit Office 2010, Office 2013 oder Office 2016 bereitstellen. |
| Verwaltung mobiler Geräte | Gruppen für Geräteregistrierung und gerätebasierte Richtlinien für bedingten Zugriff. |
| Schutz von Daten | Office 365-Vertraulichkeitsbezeichnungen und Azure Information Protection-Bezeichnungen und Gruppen. |

Wenn Sie bereit sind, Elemente dieser Infrastruktur für Benutzer bereitzustellen, können Sie:

| Phase | Rollouts Aktion |
|:-------|:-----|
| Identität | Hinzufügen von Benutzerkonten zu den Gruppen für identitätsbasierte Richtlinien für bedingten Zugriff. |
| Windows 10 Enterprise | Hinzufügen von Konten zu den Gruppen, um Windows 10 Enterprise automatisch für Benutzer mit Windows 7 oder Windows 8.1 bereitzustellen. |
| Office 365 ProPlus | Hinzufügen von Benutzerkonten zu den Gruppen, um Office 365 ProPlus automatisch für Benutzer mit Office 2010, Office 2013 oder Office 2016 bereitzustellen. |
| Verwaltung mobiler Geräte | Hinzufügen von Konten zu den Gruppen für die Geräteregistrierung und gerätebasierte Richtlinien für bedingten Zugriff. |
| Information Protection | Hinzufügen von Benutzerkonten zu den Gruppen für Information Protection Bezeichnungen. |

Sobald die Foundation-Infrastruktur fertiggestellt, getestet und erprobt ist, können Sie installierte Software, wie Windows 10 Enterprise und Office 365 ProPlus, sowie Cloud-basierte Dienste und Schutzmaßnahmen, wie Geräteregistrierung und Richtlinien für bedingten Zugriff, an Ihre Benutzer so bereitstellen, wie es Ihren Unternehmenszielen und IT-Ressourcen am besten entspricht.

## <a name="deployment-and-project-management-strategies"></a>Bereitstellungs- und Projektmanagement-Strategien

Um Ihnen einige Ideen zu geben, wie Sie das Projektmanagement der verschiedenen Phasen der Foundation-Infrastruktur für Erstanwender und den Rest Ihrer Organisation angehen können, siehe[Bereitstellungsstrategien](deployment-strategies-microsoft-365-enterprise.md). 

## <a name="deployment-for-non-enterprises"></a>Bereitstellung für Nicht-Unternehmen

Wenn Ihre Organisation kleiner und Microsoft 365 Business für Sie nicht geeignet ist, lesen Sie [Bereitstellung für Nicht-Unternehmen](deploy-foundation-infrastructure-non-enterprises.md).


## <a name="next-step"></a>Nächster Schritt


| Wo ich bin | Wo ich hin möchte |
|:-------|:-----|
| Ich verfüge über eine bestehende Infrastruktur für Office 365, Enterprise Mobility + Security (EMS) oder Windows 10 Enterprise. | Beginnen Sie mit [Bereitstellung mit vorhandener Infrastruktur](deploy-with-existing-infrastructure.md), die Sie durch die Beendigungskriterien für jede Phase führt. |
| Ich beginne als Unternehmen von Grund auf neu | Beginnen Sie Ihre End-to-End-Bereitstellung mit [Phase 1: Netzwerk](networking-infrastructure.md). |
| Ich beginne als Nicht-Unternehmen von Grund auf neu | Beginnen Sie Ihre End-to-End-Bereitstellung mit [Bereitstellung für Nicht-Unternehmen](deploy-foundation-infrastructure-non-enterprises.md). |
