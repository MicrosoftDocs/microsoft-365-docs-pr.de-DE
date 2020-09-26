---
title: Microsoft Productivity Score – Datenschutz
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ROBOTS: NOINDEX, NOFOLLOW
description: Wie Datenschutz mit dem Produktivitäts Ergebnis geschützt wird.
ms.openlocfilehash: 799d532ca1f0abd5fa6234052d4875a79d629601
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2020
ms.locfileid: "48287301"
---
# <a name="privacy-controls-for-productivity-score"></a>Datenschutz-Steuerelemente für Produktivitäts Bewertung

Die Produktivitäts Bewertung unterstützt Organisationen beim Transformieren der Arbeit mit Einblicken in die Verwendung von Microsoft 365 und den Technologie Erfahrungen, die diese Benutzer unterstützen. Die Bewertung spiegelt Ihre Organisation&#39;Leistung gegen Mitarbeiter-und Technologie Erfahrungs Maßnahmen wider und vergleicht Ihre Bewertung mit Organisationen wie Ihrem. Weitere Informationen finden Sie im Thema [Productivity Score Overview](productivity-score.md) .

Ihr Datenschutz ist uns wichtig, und Sie können die Datenschutzerklärung von Microsoft [hier](https://privacy.microsoft.com/privacystatement)anzeigen. In der Produktivitäts Bewertung gibt es wichtige Informationen, die wir zur Funktionsweise von Personen in ihren Organisationen bereitstellen. Daher zielen wir auch darauf ab, Ihnen Steuerelemente zur Verfügung zu stellen, um sicherzustellen, dass die Informationen auf sinnvolle Weise handlungsfähig sind, ohne dabei das Vertrauen zu gefährden, das Sie in uns platzieren.

Wir stellen die folgenden Steuerelemente bereit, um eine sicherere Verarbeitung von Daten zu ermöglichen:

- Flexible Administratorrollen, um zu steuern, wer die Informationen in der Produktivitäts Bewertung sehen kann.
- Anonymisierung von Metriken auf Benutzerebene.
- Möglichkeit, die Mitarbeiter Erfahrung abzulehnen.

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>Flexible Administratorrollen, um zu steuern, wer die Informationen im Produktivitäts Ergebnis sehen kann

Um die gesamte Produktivitäts BEWERTUNGSUMGEBUNG mit einer Administratorrolle anzuzeigen, einschließlich Einblicke in Mandantenebene und Details auf Benutzerebene, sollte ihre Rolle einer der folgenden sein:

- Globaler Administrator
- Exchange-Administratoren
- SharePoint-Administrator
- Skype for Business-Administrator
- Teams Administrator
- Globaler Leser
- Berichtleseberechtigter

Um Personen einzuladen, die für die Änderungsverwaltung und-Einführung zuständig sind, aber keine IT-Administratoren sind, können Sie den Benutzern den Zugriff auf die vollständige Erfahrung einschließlich Einblicke in Mandantenebene und Details auf Benutzerebene ermöglichen, indem Sie Ihnen die Rolle "berichtsleser" zuweisen.

Im Rahmen der Mitarbeiter Erfahrung stellen wir Aktivitätsdetails auf Benutzerebene im Rasterformat für jede Kategorie-Detailseite bereit. Da diese Detailebene nicht für alle potenziellen Besucher von Produktivitätseinbußen geeignet ist, haben wir eine benutzerdefinierte Rolle in Azure AD – Verwendungs Zusammenfassungsberichte-Leserrolle – erstellt, um den Zugriff auf eine breitere Gruppe von Besuchern in Ihrer Organisation nur auf die aggregierten Metriken und keine Details auf Einzelebene innerhalb der Erfahrung zu ermöglichen.

:::image type="content" source="../../media/communicationspage.jpg" alt-text="Seite "Kommunikation" in Produktivitäts Berichten.":::

## <a name="anonymization-of-user-level-metrics"></a>Anonymisierung von Metriken auf Benutzerebene

Damit die Daten, die für alle Berichte erfasst werden, anonym sind, müssen Sie ein globaler Administrator sein. Dadurch werden identifizierbare Informationen wie Benutzer-, Gruppen-und Websitenamen in allen Berichten ausgeblendet – einschließlich Produktivitäts Bewertung und Microsoft 365-Nutzung.

1. Wechseln Sie im Admin Center zu den **Einstellungen**der   >   **org** -Einstellungen, und wählen Sie unter **Dienste** die Registerkarte **Berichte**aus.
2. Wählen Sie  **Berichte** aus, und wählen Sie dann  **Anonyme Bezeichner für Benutzer-, Gruppen-und Websitenamen in Produktivitäts Bewertung und Verwendungsberichten anzeigen**aus. Diese Einstellung wird sowohl auf die Verwendungsberichte als auch auf die Vorlagen-App angewendet.
3. Wählen Sie  **Save Changes**aus.

:::image type="content" source="../../media/orgsettings_anonymous.jpg" alt-text="Benutzerinformationen anonym für Berichte erstellen.":::

## <a name="capability-to-opt-out-of-employee-experience"></a>Möglichkeit zum Deaktivieren der Mitarbeiter Erfahrung

Darüber hinaus bieten wir die Möglichkeit, den Bereich "Employee Experience" des Produktivitäts Ergebnisses bei allgemeiner Verfügbarkeit abzulehnen. Wenn Sie diese Einstellung aktivieren, wird verhindert, dass Personen in Ihrer Organisation diese Metriken anzeigen und Ihre Organisation aus Berechnungen mit Kategorien von Kommunikation, Besprechungen, Zusammenarbeit, Inhalts Zusammenarbeit und Mobilität entfernen können.

1. Wechseln Sie im Admin Center zu den **Einstellungen**der   >   **org** -Einstellungen, und wählen Sie unter **Dienste** die Registerkarte **Berichte**aus.
2. Wählen Sie  **Berichte** aus, und aktivieren Sie dann das Kontrollkästchen  **Freigabe ihrer org&#39;s-Daten mit Produktivitäts Bewertung Einblicke in die Mitarbeiter Erfahrung**. Um zu erfahren, wie Sie die Einstellungen für die Datenfreigabe für die Endpunktanalyse im InTune-Konfigurations-Manager ändern, klicken Sie auf weitere **Informationen**.
3. Wählen Sie  **Save Changes**aus.

:::image type="content" source="../../media/orgsettingspageoptout.jpg" alt-text="Seite "org-Einstellungen", auf der Sie die Mitarbeiter Erfahrung deaktivieren können.":::