---
title: Einblicke in den Nachrichtenfluss im Nachrichtenfluss-Dashboard
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: Administratoren können sich über die Einblicke und Berichte informieren, die im Nachrichtenfluss-Dashboard im Security & Compliance Center zur Verfügung stehen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 977dcef82a4f32980898c7b4392d011340e3d0a2
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577789"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>Nachrichtenfluss-Einblicke im Security & Compliance Center

Administratoren können das Nachrichtenfluss-Dashboard im Security & Compliance Center verwenden, um Trends, Einblicke zu ermitteln und Aktionen zum Beheben von Problemen im Zusammenhang mit dem Nachrichtenfluss in Ihrer Organisation durchführen.

![Das Nachrichtenfluss-Dashboard im Security & Compliance Center](../../media/mail-flow-dashboard-v2.png)

Die verfügbaren Einblicke sind:

- [Einblicke automatisch weitergeleitete Nachrichten](mfi-auto-forwarded-messages-report.md)

- [Fix possible Mail Loop Insight](mfi-mail-loop-insight.md)<sup>1</sup>

- [Fix Slow Mail Flow Rules Insight](mfi-slow-mail-flow-rules-insight.md)<sup>1</sup>

- [Nachrichtenfluss Zuordnung](mfi-mail-flow-map-report.md)

- [Neue Domänen werden weitergeleitet e-Mail Insight](mfi-new-domains-being-forwarded-email.md)<sup>2</sup>

- [Neue Benutzer, die e-Mail Insight 2 weiterleiten](mfi-new-users-forwarding-email.md)<sup>2</sup>

- [Bericht "nicht akzeptierte Domäne"](mfi-non-accepted-domain-report.md)

- [Unzustellbarkeitsbericht](mfi-non-delivery-report.md)

- [Einblicke in ausgehenden und eingehenden Nachrichtenfluss](mfi-outbound-and-inbound-mail-flow.md)

- [Warteschlangen Einblicke](mfi-queue-alerts-and-queues.md)

- [Einblicke und Berichte von SMTP-Authentifizierungsclients](mfi-smtp-auth-clients-report.md)

- [Übersicht über den Top-Domain-e-Mail-Datenstrom](mfi-domain-mail-flow-status-insight.md)

<sup>1</sup> diese Einblicke wird nur dann im Bereich " **empfohlen für Sie** " des Nachrichtenfluss-Dashboards angezeigt, nachdem das Problem erkannt wurde. Andernfalls wird es nicht angezeigt.

<sup>2</sup> diese Einsicht wird nicht im Nachrichtenfluss-Dashboard angezeigt, aber auf der Seite [Weiterleiten des Berichts](view-mail-flow-reports.md#forwarding-report) , nachdem das Problem erkannt wurde. Andernfalls wird es nicht angezeigt.

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>Erforderliche Berechtigungen zum Anzeigen des Nachrichtenfluss-Dashboards

Das Nachrichtenfluss-Dashboard steht Mitgliedern der folgenden routengruppen zur Verfügung:

- **Organisationsverwaltung** im Security & Compliance Center (globale Administratoren).

- **[Exchange-Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** in Azure AD.

- **Nachrichtenfluss-Administrator** im Security & Compliance Center: Wenn ein Mitglied dieser Rollengruppe nicht auch Mitglied der Rollengruppen globaler Administrator oder Exchange-Administrator ist, beachten Sie die folgenden Probleme und Anforderungen:

  - Der Benutzer muss sich direkt bei dem Security & Compliance Center anmelden <https://protection.office.com> .
  - Der Benutzer verfügt nur über eine schreibgeschützte Berechtigung für das Nachrichtenfluss-Dashboard.
  - Der Benutzer hat keinen Zugriff auf das Microsoft 365 Admin Center.

Weitere Informationen zu Berechtigungen im Security & Compliance Center finden Sie unter [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) und [erteilen Benutzern den Zugriff auf das Security & Compliance Center](grant-access-to-the-security-and-compliance-center.md).

## <a name="where-to-find-the-mail-flow-dashboard"></a>So finden Sie das Nachrichtenfluss-Dashboard

Öffnen Sie das Security & Compliance Center unter <https://protection.office.com> , erweitern Sie **Nachrichtenfluss**, und wählen Sie dann **Dashboard**aus.

Wenn Sie direkt zum Nachrichtenfluss-Dashboard wechseln möchten, öffnen Sie <https://protection.office.com/mailflow/dashboard> .
