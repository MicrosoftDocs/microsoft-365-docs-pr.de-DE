---
title: 'Schritt 7: Konfigurieren von Privileged Access Management für Office 365'
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
description: Verstehen und Konfigurieren von Privileged Access Management für Office 365.
ms.openlocfilehash: e9c68e4fafb1e9537b403965b4360806938c6a6f
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370422"
---
# <a name="step-7-configure-privileged-access-management-for-office-365"></a>Schritt 7: Konfigurieren von Privileged Access Management für Office 365

*Dieser Schritt ist optional und gilt nur für die Versionen E5 und Advanced Compliance von Microsoft 365 Enterprise.*

![Phase 6: Informationsschutz](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Privileged Access Management wird durch Konfigurieren von Richtlinien aktiviert, die Just-in-Time-Zugriff für aufgabenbasierte Aktivitäten in Ihrem Office 365-Mandanten angeben. Dadurch kann Ihre Organisation vor Sicherheitsverletzungen geschützt werden, bei denen vorhandene Privileged Access Management-Konten mit ständigem Zugriff auf vertrauliche Daten oder Zugriff auf kritische Konfigurationseinstellungen verwenden. Sie könnten beispielsweise eine Privileged Access Management-Richtlinie konfigurieren, die für den Zugriff und das Ändern von Postfacheinstellungen in der Organisation eine explizite Genehmigung in Ihrem Office 365-Mandanten benötigt. 

In diesem Schritt aktivieren Sie Privileged Access Management in Ihrem Office 365-Mandanten und konfigurieren Richtlinien für privilegierten Zugriff, die zusätzliche Sicherheit für aufgabenbasierten Zugriff auf Office 365-Daten und Konfigurationseinstellungen für Ihre Organisation bereitstellen. Es gibt drei grundlegende Schritte, um mit dem privilegierten Zugriff in Ihrer Office 365-Organisation zu beginnen:
- Erstellen einer Gruppe einer genehmigenden Person
- Aktivieren des privilegierten Zugriffs
- Erstellen von Genehmigungsrichtlinien

Nach der Konfiguration kann Ihre Organisation mit Privileged Access Management ohne ständige Berechtigungen arbeiten und eine Schutzebene für Sicherheitslücken bereitstellen, die aufgrund eines derartigen ständigen Administratorzugriffs entstehen. Für privilegierten Zugriff sind Genehmigungen zum Ausführen von Aufgaben erforderlich, für die eine zugewiesene Genehmigungsrichtlinie definiert wurde. Benutzer, die Aufgaben ausführen müssen, die in einer Genehmigungsrichtlinie enthalten sind, müssen Zugriff anfordern und diesen gewährt bekommen, um die erforderlichen Berechtigungen zum Ausführen der in der Richtlinie definierten Aufgaben zu erhalten.

Weitere Informationen zum Aktivieren von Privileged Access Management in Office 365 finden Sie im Thema [Konfigurieren von Privileged Access Management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration).

Weitere Informationen finden Sie im Thema [Privileged Access Management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).


|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  Um diese Konfiguration in einer Testlaborumgebung zu üben, lesen Sie den Leitfaden für die [privilegierte Zugriffs Verwaltungs Test-Übungseinheit](privileged-access-microsoft-365-enterprise-dev-test-environment.md). |
|||

Als Zwischenprüfung können Sie die [Beendigungskriterien](infoprotect-exit-criteria.md#crit-infoprotect-step7) für diesen Schritt betrachten.

## <a name="next-step"></a>Nächster Schritt

[Beendigungskriterien für die Information Protection-Infrastruktur](infoprotect-exit-criteria.md)
