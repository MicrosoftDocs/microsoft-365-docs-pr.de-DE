---
title: 'Schritt 7: Konfigurieren der privilegierten Zugriffsverwaltung'
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Verstehen und Konfigurieren der privilegierten Zugriffsverwaltung.
ms.openlocfilehash: 4fed4daacc17a34563825bf0575880ce06ec6ebd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636988"
---
# <a name="step-7-configure-privileged-access-management"></a>Schritt 7: Konfigurieren der privilegierten Zugriffsverwaltung

*Dieser Schritt ist optional und gilt nur für die Versionen E5 und Advanced Compliance von Microsoft 365 Enterprise.*

![Phase 6: Schutz von Daten](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Die Verwaltung privilegierter Zugriffsrechte wird durch Konfigurieren von Richtlinien aktiviert, die den Just-in-Time-Zugriff für aufgabenbasierte Aktivitäten in Ihrem Mandanten angeben. Damit können Sie Ihre Organisation vor Verstößen schützen, die vorhandene privilegierte Administratorkonten mit einem ständigen Zugriff auf vertrauliche Daten oder den Zugriff auf wichtige Konfigurationseinstellungen verwenden können. Sie können beispielsweise eine Richtlinie für privilegierte Zugriffsverwaltung konfigurieren, die eine explizite Genehmigung für den Zugriff auf und die Änderung der Organisations Postfacheinstellungen in Ihrem Mandanten erfordert.

In diesem Schritt aktivieren Sie die privilegierte Zugriffsverwaltung in Ihrem Mandanten und konfigurieren privilegierte Zugriffsrichtlinien, die zusätzliche Sicherheit für den aufgabenbasierten Zugriff auf Daten und Konfigurationseinstellungen für Ihre Organisation bieten. Es gibt drei grundlegende Schritte für die ersten Schritte mit privilegiertem Zugriff in Ihrer Organisation:
- Erstellen einer Gruppe einer genehmigenden Person
- Aktivieren des privilegierten Zugriffs
- Erstellen von Genehmigungsrichtlinien

Nach der Konfiguration kann Ihre Organisation mit Privileged Access Management ohne ständige Berechtigungen arbeiten und eine Schutzebene für Sicherheitslücken bereitstellen, die aufgrund eines derartigen ständigen Administratorzugriffs entstehen. Für privilegierten Zugriff sind Genehmigungen zum Ausführen von Aufgaben erforderlich, für die eine zugewiesene Genehmigungsrichtlinie definiert wurde. Benutzer, die Aufgaben ausführen müssen, die in einer Genehmigungsrichtlinie enthalten sind, müssen Zugriff anfordern und diesen gewährt bekommen, um die erforderlichen Berechtigungen zum Ausführen der in der Richtlinie definierten Aufgaben zu erhalten.

Informationen zum Aktivieren der Verwaltung privilegierten Zugriffs finden Sie im Thema [configure privileged Access Management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) .

Weitere Informationen finden Sie im Thema [privilegierte Zugriffsverwaltung](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) .


|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  Wenn Sie diese Konfiguration in einer Testumgebung ausführen möchten, lesen Sie die [Testumgebungsanleitung: Privileged Access Management](privileged-access-microsoft-365-enterprise-dev-test-environment.md). |
|||

Als Zwischenprüfung können Sie die [Beendigungskriterien](infoprotect-exit-criteria.md#crit-infoprotect-step7) für diesen Schritt betrachten.

## <a name="next-step"></a>Nächster Schritt

[Beendigungskriterien für die Information Protection-Infrastruktur](infoprotect-exit-criteria.md)
