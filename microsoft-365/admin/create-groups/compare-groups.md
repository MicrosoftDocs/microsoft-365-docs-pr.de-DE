---
title: Vergleichen von Gruppen in Office 365
ms.reviewer: arvaradh
f1.keywords:
- CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 758759ad-63ee-4ea9-90a3-39f941897b7d
description: Hier erfahren Sie, welche Arten von Gruppen Sie in Office 365 verwenden können.
ms.openlocfilehash: 5b8a3a7859a510a07b579f3b1da255e555d6ae1f
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241406"
---
# <a name="compare-groups"></a>Vergleichen von Gruppen

Im Microsoft 365 Admin Center können Sie im Bereich **Gruppen** die folgenden Gruppentypen erstellen und verwalten: 

- **Office 365-Gruppen** werden für die Zusammenarbeit zwischen Benutzern innerhalb und außerhalb Ihres Unternehmens verwendet.
- **Verteilergruppen** werden verwendet, um Benachrichtigungen an eine Gruppe von Personen zu senden.
- **Sicherheitsgruppen** werden verwendet, um den Zugriff auf SharePoint-Ressourcen zu gewähren.
- **E-Mail-aktivierte Sicherheitsgruppen** werden verwendet, um den Zugriff auf SharePoint-Ressourcen zu gewähren und Benachrichtigungen an diese Benutzer zu senden.
- **Freigegebene Postfächer** werden verwendet, wenn mehrere Personen Zugriff auf dasselbe Postfach benötigen, z. B. eine E-Mail-Adresse für Unternehmensinformationen oder Support.

## <a name="office-365-groups"></a>Office 365-Gruppen

Office 365-Gruppen werden für die Zusammenarbeit zwischen Benutzern innerhalb und außerhalb Ihres Unternehmens verwendet. Bei jeder Office 365-Gruppe erhalten Mitglieder eine Gruppen-E-Mail und einen freigegebenen Arbeitsbereich für Unterhaltungen, Dateien und Kalenderereignisse sowie einen Planner.

Sie können einer Gruppe Benutzer von außerhalb Ihres Unternehmens hinzufügen, sofern dieses Feature [vom Administrator aktiviert wurde](manage-guest-access-in-groups.md). Sie können externen Absendern das Senden von E-Mails an die Gruppen-E-Mail-Adresse gestatten.

Office 365-Gruppen können [für die dynamische Mitgliedschaft in Azure Active Directory-konfiguriert](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type) werden, sodass Gruppenmitglieder basierend auf Benutzerattributen wie Abteilung, Standort, Position usw. automatisch hinzugefügt oder entfernt werden können.

Auf Office 365-Gruppen kann über Mobile Apps wie Outlook für iOS und Outlook für Android zugegriffen werden.

Gruppenmitglieder können Nachrichten mit der "Senden als"- oder "Senden im Auftrag von"-Gruppen-E-Mail-Adresse senden, sofern dieses Feature [vom Administrator aktiviert wurde](allow-members-to-send-as-or-send-on-behalf-of-group.md).

## <a name="distribution-groups"></a>Verteilergruppen

[Verteilergruppen](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups) werden verwendet, um Benachrichtigungen an eine Gruppe von Personen zu senden. Verteilergruppen können externe E-Mails empfangen, sofern dieses Feature vom Administrator aktiviert wurde.

Verteilergruppen eignen sich am besten für Situationen, in denen Sie Informationen an eine Gruppe von Personen übermitteln müssen, z. B. "Personen in Gebäude A" oder "Jeder bei Contoso".

## <a name="security-groups"></a>Sicherheitsgruppen

[Sicherheitsgruppen](../email/create-edit-or-delete-a-security-group.md) werden verwendet, um den Zugriff auf Office 365-Ressourcen wie z. B. SharePoint zu gewähren. Sicherheitsgruppen können die Verwaltung vereinfachen, weil Sie nur die Gruppe verwalten müssen, anstatt Benutzer zu jeder Ressource einzeln hinzuzufügen.

Sicherheitsgruppen können Benutzer oder Geräte enthalten. Das Erstellen einer Sicherheitsgruppe für Geräte kann mit Verwaltungsdiensten für mobile Geräte (z. B. Intune) erfolgen.

Sicherheitsgruppen können [für die dynamische Mitgliedschaft in Azure Active Directory-konfiguriert](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type) werden, sodass Gruppenmitglieder oder Geräte basierend auf Benutzerattributen wie Abteilung, Standort oder Position bzw. Geräteattributen wie Betriebssystemversion automatisch hinzugefügt oder entfernt werden können.

## <a name="mail-enabled-security-groups"></a>E-Mail-aktivierte Sicherheitsgruppen

E-Mail-aktivierte Sicherheitsgruppen funktionieren wie normale Sicherheitsgruppen, mit dem Unterschied, dass sie nicht dynamisch über Azure Active Directory verwaltet werden können und keine Geräte enthalten können.

Sie bieten die Möglichkeit, E-Mails an alle Mitglieder der Gruppe zu senden.

## <a name="shared-mailboxes"></a>Freigegebene Postfächer

[Freigegebene Postfächer](../email/create-a-shared-mailbox.md) werden verwendet, wenn mehrere Personen Zugriff auf dasselbe Postfach benötigen, z. B. eine E-Mail-Adresse für Unternehmensinformationen oder Support, den Empfangstresen oder andere Funktionen, die von mehreren Personen geteilt werden.

Freigegebene Postfächer können externe E-Mails empfangen, wenn der Administrator dieses Feature aktiviert hat.

Benutzer, die über Berechtigungen für das Gruppenpostfach verfügen, können Nachrichten mit der "Senden als"- oder "Senden im Auftrag von"-Postfach-E-Mail-Adresse senden, sofern der Administrator dem jeweiligen Benutzer die entsprechende Berechtigung erteilt hat. Dies ist besonders nützlich für Hilfe- und Support-Postfächer, da Benutzer E-Mails von "Contoso-Support" oder der "Rezeption von Gebäude A" senden können.

Aktuell ist es nicht möglich, ein freigegebenes Postfach zu einer Office 365-Gruppe zu migrieren. Möchten Sie dies tun? Erzählen Sie uns davon. **[Stimmen Sie hier ab](https://go.microsoft.com/fwlink/?linkid=871518)**

## <a name="related-articles"></a>Verwandte Artikel

[Weitere Informationen zu Office 365-Gruppen](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2)
