---
title: Vergleichen von Gruppen
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 758759ad-63ee-4ea9-90a3-39f941897b7d
description: Mitglieder von Microsoft 365-Gruppen erhalten eine Gruppen-E-Mail und einen gemeinsamen Arbeitsbereich für Unterhaltungen, Dateien, Kalenderereignisse, Stream sowie Planner.
ms.openlocfilehash: 12da954beb4d019b7652ef4df2e18cb30ff542ed
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393259"
---
# <a name="compare-groups"></a>Vergleichen von Gruppen

Im Microsoft 365 Admin Center können Sie im Bereich **Gruppen** die folgenden Gruppentypen erstellen und verwalten: 

- **Microsoft 365-Gruppen** (vormals Office 365-Gruppen) werden für die Zusammenarbeit zwischen Benutzern innerhalb und außerhalb Ihres Unternehmens verwendet.
- **Verteilergruppen** werden verwendet, um E-Mail-Benachrichtigungen an eine Gruppe von Personen zu senden.
- **Sicherheitsgruppen** werden verwendet, um Zugriff auf Ressourcen wie z. B. SharePoint-Sites zu gewähren.
- **E-Mail-aktivierte Sicherheitsgruppen** werden verwendet, um Zugriff auf Ressourcen wie z. B. Microsoft Office SharePoint Online zu gewähren und Benachrichtigungen per E-Mail an diese Benutzer zu senden.
- **Freigegebene Postfächer** werden verwendet, wenn mehrere Personen Zugriff auf dasselbe Postfach benötigen, z. B. eine E-Mail-Adresse für Unternehmensinformationen oder Support.

## <a name="microsoft-365-groups"></a>Microsoft 365-Gruppen

Microsoft 365-Gruppen werden für die Zusammenarbeit zwischen Benutzern innerhalb und außerhalb Ihres Unternehmens verwendet. Bei jeder Microsoft 365-Gruppe erhalten Mitglieder eine Gruppen-E-Mail und einen freigegebenen Arbeitsbereich für Unterhaltungen, Dateien, Kalenderereignisse, Stream sowie einen Planner.

Sie können einer Gruppe Personen von außerhalb Ihres Unternehmens hinzufügen, sofern dieses Feature [vom Administrator aktiviert wurde](manage-guest-access-in-groups.md). Sie können externen Absendern das Senden von E-Mails an die Gruppen-E-Mail-Adresse gestatten.

Microsoft 365-Gruppen können [für die dynamische Mitgliedschaft in Azure Active Directory-konfiguriert](/azure/active-directory/users-groups-roles/groups-change-type) werden, sodass Gruppenmitglieder basierend auf Benutzerattributen wie Abteilung, Standort, Position usw. automatisch hinzugefügt oder entfernt werden können.

Auf Microsoft 365-Gruppen kann über Mobile Apps wie Outlook für iOS und Outlook für Android zugegriffen werden.

Gruppenmitglieder können Nachrichten mit der "Senden als"- oder "Senden im Auftrag von"-Gruppen-E-Mail-Adresse senden, sofern dieses Feature [vom Administrator aktiviert wurde](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md).

Microsoft 365-Gruppen unterstützen keine Schachtelung mit anderen Microsoft 365-Gruppen oder mit Verteiler- oder Sicherheitsgruppen.

## <a name="distribution-groups"></a>Verteilergruppen

[Verteilergruppen](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups) werden verwendet, um Benachrichtigungen an eine Gruppe von Personen zu senden. Verteilergruppen können externe E-Mails empfangen, sofern dieses Feature vom Administrator aktiviert wurde.

Verteilergruppen eignen sich am besten für Situationen, in denen Sie Informationen an eine Gruppe von Personen übermitteln müssen, z. B. "Personen in Gebäude A" oder "Jeder bei Contoso".

Verteilergruppen können[auf Microsoft 365-Gruppen aktualisiert werden](../manage/upgrade-distribution-lists.md).

Verteilergruppen können in Microsoft Teams zu einem Team hinzugefügt werden.

Microsoft 365 Gruppen dürfen keine Mitglieder von Verteilergruppen sein.

## <a name="security-groups"></a>Sicherheitsgruppen

[Sicherheitsgruppen](../email/create-edit-or-delete-a-security-group.md) werden verwendet, um den Zugriff auf Microsoft 365-Ressourcen wie z. B. SharePoint zu gewähren. Sicherheitsgruppen können die Verwaltung vereinfachen, weil Sie nur die Gruppe verwalten müssen, anstatt Benutzer zu jeder Ressource einzeln hinzuzufügen.

Sicherheitsgruppen können Benutzer oder Geräte enthalten. Das Erstellen einer Sicherheitsgruppe für Geräte kann mit Verwaltungsdiensten für mobile Geräte (z. B. Intune) verwendet werden.

Sicherheitsgruppen können [für die dynamische Mitgliedschaft in Azure Active Directory-konfiguriert](/azure/active-directory/users-groups-roles/groups-change-type) werden, sodass Gruppenmitglieder oder Geräte basierend auf Benutzerattributen wie Abteilung, Standort oder Position bzw. Geräteattributen wie Betriebssystemversion automatisch hinzugefügt oder entfernt werden können.

Sicherheitsgruppen können zu einem Team hinzugefügt werden.

Microsoft 365 Gruppen dürfen keine Mitglieder von Sicherheitsgruppen sein.

## <a name="mail-enabled-security-groups"></a>E-Mail-aktivierte Sicherheitsgruppen

E-Mail-aktivierte Sicherheitsgruppen funktionieren wie normale Sicherheitsgruppen, mit dem Unterschied, dass sie nicht dynamisch über Azure Active Directory verwaltet werden können und keine Geräte enthalten können.

Sie bieten die Möglichkeit, E-Mails an alle Mitglieder der Gruppe zu senden.

E-Mail-aktivierte Sicherheitsgruppen können zu einem Team hinzugefügt werden.

## <a name="shared-mailboxes"></a>Freigegebene Postfächer

[Freigegebene Postfächer](../email/create-a-shared-mailbox.md) werden verwendet, wenn mehrere Personen Zugriff auf dasselbe Postfach benötigen, z. B. eine E-Mail-Adresse für Unternehmensinformationen oder Support, den Empfangstresen oder andere Funktionen, die von mehreren Personen geteilt werden.

Freigegebene Postfächer können externe E-Mails empfangen, wenn der Administrator dieses Feature aktiviert hat.

Freigegebene Postfächer beinhalten einen Kalender, der für die Zusammenarbeit verwendet werden kann.

Benutzer, die über Berechtigungen für das Gruppenpostfach verfügen, können Nachrichten mit der "Senden als"- oder "Senden im Auftrag von"-Postfach-E-Mail-Adresse senden, sofern der Administrator dem jeweiligen Benutzer die entsprechende Berechtigung erteilt hat. Dies ist besonders nützlich für Hilfe- und Support-Postfächer, da Benutzer E-Mails von "Contoso-Support" oder der "Rezeption von Gebäude A" senden können.

Es nicht möglich, ein freigegebenes Postfach zu einer Microsoft 365-Gruppe zu migrieren. 

## <a name="related-content"></a>Verwandte Inhalte

[Informationen zu Microsoft 365-Gruppen](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Upgraden von Verteilerlisten auf Microsoft 365-Gruppen in Outlook](/microsoft-365/admin/manage/upgrade-distribution-lists)

[Warum Sie Ihre Verteilerlisten für Gruppen in Outlook aktualisieren sollten](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)
