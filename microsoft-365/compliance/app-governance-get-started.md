---
title: Erste Schritte mit App-Governance
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Erste Schritte mit App-Governance-Funktionen zum Steuern Ihrer Apps.
ms.openlocfilehash: 0fc00819947d3d472de9199b0381c6f33de0acd6
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420166"
---
# <a name="get-started-with-app-governance-in-preview"></a>Erste Schritte mit App-Governance (Vorschau)

So beginnen Sie mit der Verwendung des App-Governance-Features für Microsoft Cloud App Security

1. Vergewissern Sie sich, dass Ihr Konto über die erforderliche Lizenzierungsstufe verfügt. App-Governance ist ein Add-On-Feature für Microsoft Cloud App Security (MCAS). Daher muss MCAS in Ihrem Konto entweder als eigenständiges Produkt oder als Teil einer der unten aufgeführten Lizenzpakete vorhanden sein.
1. Sie müssen über eine der unten aufgeführten Administratorrollen verfügen, um auf die App-Governance-Seiten im Portal zugreifen zu können.

## <a name="licensing-for-app-governance"></a>Lizenzierung für App-Governance

Bevor Sie mit App-Governance beginnen, sollten Sie Ihr [Microsoft 365-Abonnement](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) und etwaige Add-Ons überprüfen. Für den Zugriff auf und die Nutzung von App-Governance muss Ihre Organisation über eines der folgenden Abonnements oder Add-Ons verfügen:

- Microsoft Cloud App Security
- Microsoft 365 E5
- Microsoft 365 E5 Compliance
- Microsoft 365 E5 Developer (ohne Windows und Audiokonferenz)
- Microsoft 365 E5 Information Protection und Governance
- Microsoft 365 E5 Security
- Microsoft 365 E5 mit Gesprächsminuten
- Microsoft 365 E5 ohne Audiokonferenz
- Microsoft 365 A5-Compliance für Lehrpersonal
- Microsoft 365 A5-Compliance für Schüler/Studenten
- Microsoft 365 A5 für Lehrpersonal
- Microsoft 365 A5 für Schüler und Studenten
- Microsoft 365 A5 Information Protection und Governance für Lehrpersonal
- Microsoft 365 A5 Information Protection und Governance für Schüler und Studenten
- Microsoft 365 A5-Sicherheit für Lehrpersonal
- Microsoft 365 A5-Sicherheit für Schüler/Studenten
- Microsoft 365 A5 – Vorteile für Schüler und Studenten
- Microsoft 365 A5 mit Gesprächsminuten für Lehrpersonal
- Microsoft 365 A5 mit Gesprächsminuten für Schüler und Studenten
- Microsoft 365 A5 ohne Audiokonferenz für Lehrpersonal
- Microsoft 365 A5 ohne Audiokonferenz für Schüler und Studenten
- Microsoft 365 A5 ohne Audiokonferenz für Schüler und Studenten – Vorteilsprogramm

## <a name="administrator-roles"></a>Administratorrollen

Eine der folgenden Administratorrollen ist erforderlich, um App-Governance-Seiten anzuzeigen oder Richtlinien und Einstellungen zu verwalten:

- Anwendungsadministrator
- Cloudanwendungsadministrator
- Unternehmensadministrator
- Complianceadministrator
- Compliancedatenadministrator
- Complianceleseberechtigter (schreibgeschützt)
- Globaler Leseberechtigter
- Sicherheitsadministrator
- Sicherheitsoperator
- Sicherheitsleseberechtigter (schreibgeschützt)

Im Folgenden sind die Funktionen für die einzelnen Rollen aufgeführt.

| Rolle | Lesezugriff auf das Dashboard | Lesezugriff auf installierten Apps |Lesezugriff auf Richtlinien | Richtlinien erstellen, aktualisieren oder löschen | Lesezugriff auf Warnungen | Warnungen aktualisieren | Lesezugriff auf Einstellungen | Einstellungen aktualisieren | Lesezugriff auf Korrekturen | Korrekturen aktualisieren |
|:-------|:-----|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
| Anwendungsadministrator | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) |
| Cloudanwendungsadministrator | ![Häkchen](..\media\checkmark.png) | | | | | | | | | |
| Unternehmensadministrator | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) |
| Complianceadministrator | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) |  | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | |
| Compliancedatenadministrator | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) |  | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | |
| Complianceleseberechtigter | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) |  | ![Häkchen](..\media\checkmark.png) |  | ![Häkchen](..\media\checkmark.png) |  | | |
| Globaler Leseberechtigter  | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) |  | ![Häkchen](..\media\checkmark.png) |  | ![Häkchen](..\media\checkmark.png) |  | | |
| Sicherheitsadministrator | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) |  | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | |
| Sicherheitsoperator | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | |
| Sicherheitsleseberechtigter  | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) | ![Häkchen](..\media\checkmark.png) |  | ![Häkchen](..\media\checkmark.png) |  | ![Häkchen](..\media\checkmark.png) |  | ![Häkchen](..\media\checkmark.png) | |
|||||||||| | |

Weitere Informationen zu den einzelnen Rollen finden Sie unter [Administratorrollenberechtigungen](/azure/active-directory/roles/permissions-reference).

## <a name="add-app-governance-to-your-microsoft-365-account"></a>Hinzufügen von App-Governance zu Ihrem Microsoft 365-Konto

Für bestehende Microsoft 365-Kunden:

1. Navigieren Sie in Ihrem [Microsoft 365 Admin Center](https://admin.microsoft.com) zu **Abrechnung – Dienste kaufen**, und klicken Sie auf **Add-Ons**.
1. Klicken Sie auf der App-Governance-Karte auf **Details**.
1. Klicken Sie auf **Kostenlose Testversion starten**.
1. Füllen Sie die angeforderten Informationen aus, um App-Governance zu Ihrem ausgewählten Mandanten hinzuzufügen. Wenn Sie ein neuer Kunde sind, müssen Sie zuerst bestimmte Informationen angeben, um ein Konto einzurichten und einen Mandanten für Ihren Testzeitraum zu erstellen. Sobald dies abgeschlossen ist, können Sie App-Governance zur Testversion hinzufügen.

Für neue Microsoft 365-Kunden:

1. Klicken Sie oben auf dieser Seite auf die Schaltfläche **Kostenloses Konto**.
1. Klicken Sie unter **Microsoft 365 for Business testen** auf **1 Monat kostenlos testen**.

Für beide:

1. Geben Sie im Registrierungsportal Ihre E-Mail-Adresse für die Testversion an. Wenn Sie bereits Kunde sind, verwenden Sie die E-Mail-Adresse, die Ihrem Konto zugeordnet ist. Klicken Sie auf **Weiter**.
1. Nachdem Sie sich angemeldet haben, klicken Sie auf **Jetzt testen**, um die kostenlose Testversion zu erhalten.
1. Klicken Sie auf **Weiter**, um die Seite zu schließen und mit der Einrichtung der Testversion zu beginnen. Für neue App-Governance-Kunden dauert es bis zu zwei Stunden, bis die App Governance-Instanz verfügbar ist. Für Bestandskunden kommt es zu keiner Unterbrechung vorhandener Dienste.
  > [!NOTE]
Wenn Sie noch nicht über ein Konto verfügen, werden Sie aufgefordert, ein neues Konto einzurichten, bevor Sie mit der Testversion fortfahren können.

1. Geben Sie einen verfügbaren Domänennamen für Ihren AAD-Mandanten ein, und klicken Sie auf **Verfügbarkeit überprüfen**. Ihnen wird automatisch eine Administratorrolle zugewiesen (wenn Sie über keine vorhandene Rolle für die App-Governance verfügen). Sie können den Domänennamen jederzeit ändern und/oder später weitere Mandanten über das Microsoft 365 Admin Center erwerben.
1. Geben Sie den Benutzernamen und das Kennwort ein, die Sie für die Anmeldung bei Ihrem Konto verwenden möchten. Klicken Sie auf **Registrieren**.
1. Klicken Sie auf **Erste Schritte**, um zum App-Governance-Portal zu wechseln, oder auf **Abonnement verwalten**, um zum Microsoft 365 Admin Center zu wechseln.
