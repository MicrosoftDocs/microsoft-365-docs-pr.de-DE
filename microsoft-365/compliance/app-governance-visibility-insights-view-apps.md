---
title: Ihre Apps anzeigen
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
description: Zeigen Sie Ihre Apps an.
ms.openlocfilehash: 48a1a2140a3b59091796ca013a12eeefb8a284b9
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420130"
---
# <a name="view-your-apps"></a>Ihre Apps anzeigen

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

Mit der Microsoft-App-Governance können Sie schnell tiefe Insights in die Microsoft 365 Apps in Ihrem Mandanten gewinnen. Sie können beispielsweise Folgendes sehen:

- Eine Liste der OAuth-fähigen Apps im Mandanten, welche die Microsoft Graph-API verwenden, zusammen mit relevanten App-Metadaten und Nutzungsdaten.
- App-Details mit tieferen Insights und Informationen, indem Sie eine App in der Liste auswählen.

## <a name="getting-a-list-of-all-the-apps-in-your-tenant"></a>Abrufen einer Liste aller Apps in Ihrem Mandanten

Eine Zusammenfassung der Apps in Ihrem Mandanten finden Sie unter **Microsoft 365 Compliance Center > App-Schutz & Governance > Apps**.

![Die MAPG-App-Übersichtsseite im Microsoft 365 Compliance Center](..\media\manage-app-protection-governance\mapg-cc-apps.png)

>[!Note]
> Ihr Anmeldekonto muss über eine [dieser Rollen](app-governance-get-started.md#administrator-roles) verfügen, um App-Governance-Daten anzeigen zu können.
>

Sie werden eine Liste von Apps und diese Informationen sehen:

- App-Name
- Herausgeber
- App-Zertifizierung

  Gibt an, ob die App mit Microsoft-Technologien kompatibel ist, die den bewährten Methoden für Cloud-App-Sicherheit entsprechen und von Microsoft unterstützt werden.

- Zuletzt geändert

  Zeigt das Datum an, an dem die App-Governance auf dem Client installiert wurde, wenn dieses Datum aktueller als das Datum ist, an dem die App zuletzt geändert wurde.

- Installationsdatum
- Berechtigungsebene
- Anzahl der Benutzer
- Datenzugriff

  Die Summe des Hochladens und Herunterladens der App-Daten im Mandanten über den letzten Tag, sowie die Änderung im Vergleich zum vorherigen Tag.

Die App-Governance sortiert die App-Liste standardmäßig nach **App-Namen**. Um die Liste nach einem anderen App-Attribut zu sortieren, wählen Sie den Attributnamen aus.

Sie können auch **Suchen** auswählen, um nach einer App anhand des Namens zu suchen.

## <a name="getting-detailed-information-on-an-app"></a>Abrufen detaillierter Informationen zu einer App

Für detaillierte Informationen zu einer bestimmten App in Ihrem Mandanten wechseln sie zu **Microsoft 365 Compliance Center > App Governance > Apps-Seite > *App-Name***.

![Der App-Detailbereich der App-Governance im Microsoft 365 Compliance Center](..\media\manage-app-protection-governance\mapg-cc-apps-app.png)

Der App-Detailbereich enthält zusätzliche Informationen auf diesen Registerkarten:

| Registerkartenname | Description |
|:-------|:-----|
| Details | Sehen Sie sich zusätzliche Daten zur App an, z. B. das Datum der ersten Zustimmung und die App-ID. Um die Eigenschaften der App wie in Azure AD registriert anzuzeigen, wählen Sie **App in Azure AD anzeigen** aus. |
| Nutzung | Hier sehen Sie die Daten, auf welche die App im Mandanten zugreift, zeichnen die Datennutzung auf, und zeigen die Nutzung durch die obersten \<x> Benutzer und Benutzer mit [Prioritätskonten](/microsoft-365/admin/setup/priority-accounts) an. |
| Benutzer | Hier sehen Sie eine Liste der Benutzer, welche die App verwenden, ob es sich um ein Prioritätskonto handelt, sowie die Menge der heruntergeladenen und hochgeladenen Daten. |
| Berechtigungen | Hier sehen Sie eine Zusammenfassung der Berechtigungen, die der App gewährt und von ihr verwendet werden, sowie die Liste der spezifischen Berechtigungen. Lesen Sie die [Referenz zu den Microsoft Graph-Berechtigungen](/graph/permissions-reference) für weitere Informationen. |
|||

Für eine aktivierte App gibt es auch ein Steuerelement **App deaktivieren**, um die Verwendung der ausgewählten App zu deaktivieren, und ein Steuerelement **App aktivieren**, um die Verwendung der deaktivierten App zu ermöglichen. Für diese Aktionen sind diese [Administratorrollen](app-governance-get-started.md#administrator-roles)erforderlich:

- Compliance-Administrator
- Globaler Administrator
- Sicherheitsadministrator
- Sicherheitsoperator

## <a name="next-step"></a>Nächster Schritt

[Bestimmen Sie Ihre allgemeinen App-Compliance-Ausrichtung](app-governance-visibility-insights-compliance-posture.md).
