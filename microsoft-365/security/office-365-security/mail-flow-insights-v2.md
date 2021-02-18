---
title: Einblicke in den Nachrichtenfluss im Nachrichtenflussdashboard
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: Administratoren können sich über die Einblicke und Berichte informieren, die im Dashboard für den Nachrichtenfluss im Security & Compliance Center verfügbar sind.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7432eca577fb264126b9fc8f10bdd83de32711cf
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289675"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>Nachrichtenfluss-Einblicke im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Administratoren können das Nachrichtenflussdashboard im Security & Compliance Center verwenden, um Trends, Einblicke zu erkennen und Maßnahmen zur Behebung von Problemen im Zusammenhang mit dem Nachrichtenfluss in ihrer Organisation zu ergreifen.

![Das Nachrichtenflussdashboard im Security & Compliance Center](../../media/mail-flow-dashboard-v2.png)

Die verfügbaren Einblicke sind:

- [Einblick in automatisch weitergeleitete Nachrichten](mfi-auto-forwarded-messages-report.md)

- [Beheben möglicher Einblicke in die E-Mail-Schleife](mfi-mail-loop-insight.md)<sup>1</sup>

- [Beheben von Einblicken in langsame Nachrichtenflussregeln](mfi-slow-mail-flow-rules-insight.md)<sup>1</sup>

- [Zuordnung der Nachrichtenübermittlung](mfi-mail-flow-map-report.md)

- [Neue Domänen, die E-Mail-Einblicke](mfi-new-domains-being-forwarded-email.md)<sup>2 weitergeleitet werden</sup>

- [Neue Benutzer, die E-Mail-Einblicke](mfi-new-users-forwarding-email.md)<sup>2 weiterleiten</sup>

- [Bericht "nicht akzeptierte Domäne"](mfi-non-accepted-domain-report.md)

- [Unzustellbarkeitsbericht](mfi-non-delivery-report.md)

- [Einblick in den Fluss eingehender und ausgehender E-Mails](mfi-outbound-and-inbound-mail-flow.md)

- [Einblick in die Warteschlange](mfi-queue-alerts-and-queues.md)

- [Einblick und Berichte zu SMTP-AUTH-Clients](mfi-smtp-auth-clients-report.md)

- [Übersicht über den Top-Domain-e-Mail-Datenstrom](mfi-domain-mail-flow-status-insight.md)

<sup>1</sup> Dieser Einblick wird im Bereich **"Empfohlen** für Sie" des Dashboards für den Nachrichtenfluss erst angezeigt, nachdem das Problem erkannt wurde. Andernfalls wird sie nicht mehr zu sehen sein.

<sup>2</sup> Dieser Einblick wird nicht im Nachrichtenflussdashboard angezeigt, sondern auf der Seite ["Weiterleitungsbericht",](view-mail-flow-reports.md#forwarding-report) nachdem das Problem erkannt wurde. Andernfalls wird sie nicht mehr zu sehen sein.

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>Erforderliche Berechtigungen zum Anzeigen des Nachrichtenflussdashboards

Das Nachrichtenflussdashboard ist für Mitglieder der folgenden Rollengruppen verfügbar:

- **Organisationsverwaltung** im Security & Compliance Center (globale Administratoren).

- **[Exchange-Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** in Azure Active Directory.

- **MailFlow-Administrator** im Security & Compliance Center. Wenn das Konto nicht auch Mitglied der Rollengruppe "Organisationsverwaltung" oder "Exchange-Administrator" ist, sollten Sie die folgenden Probleme berücksichtigen:
  - Der Benutzer muss sich direkt beim Security & Compliance Center <https://protection.office.com> anmelden.
  - Der Benutzer verfügt nur über schreibgeschützte Berechtigungen für das Nachrichtenflussdashboard.
  - Der Benutzer hat keinen Zugriff auf das Microsoft 365 Admin Center.

Weitere Informationen zu Berechtigungen finden Sie unter "Berechtigungen" im [Security & Compliance Center,](permissions-in-the-security-and-compliance-center.md) und gewähren Sie Benutzern Zugriff auf das [Security & Compliance Center.](grant-access-to-the-security-and-compliance-center.md)

## <a name="where-to-find-the-mail-flow-dashboard"></a>Wo das Dashboard für den Nachrichtenfluss zu finden ist

Öffnen Sie das Security & Compliance Center unter , erweitern Sie <https://protection.office.com> **den Nachrichtenfluss,** und wählen Sie dann **Dashboard aus.**

Um direkt zum Dashboard für den Nachrichtenfluss zu wechseln, öffnen Sie <https://protection.office.com/mailflow/dashboard> .
