---
title: Übersicht über Microsoft 365-Gruppen für Administratoren
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: Mit Microsoft 365 Gruppen können Sie die Teamarbeit über Microsoft 365 fördern, indem Sie einer Gruppe von Personen Zugriff auf eine Sammlung freigegebener Ressourcen gewähren.
ms.openlocfilehash: 69f7e47bcfb9e0704f8c373cf1addf98ef898cfa
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782393"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>Übersicht über Microsoft 365-Gruppen für Administratoren

Microsoft 365 Gruppen sind der grundlegende Mitgliedschaftsdienst, der die gesamte Teamarbeit über Microsoft 365 hinweg steuert. Mit Microsoft 365 Gruppen können Sie einer Gruppe von Personen Zugriff auf eine Sammlung freigegebener Ressourcen gewähren. Diese Ressourcen enthalten:

- Einen freigegebenen Outlook-Posteingang
- Einen freigegebenen Kalender
- Eine SharePoint-Dokumentbibliothek
- Einen Planner
- Ein OneNote-Notizbuch
- Power BI
- Yammer (wenn die Gruppe in Yammer erstellt wurde)
- Ein Team (wenn die Gruppe in Teams erstellt wurde)
- Roadmap (wenn Sie Project für das Web haben)
- Stream

Bei einer Microsoft 365 Gruppe müssen Sie keiner dieser Ressourcen manuell Berechtigungen zuweisen. Wenn Sie Personen zur Gruppe hinzufügen, erhalten sie automatisch die berechtigungen, die sie benötigen.

Jeder Benutzer kann eine Gruppe erstellen, es sei denn, Sie [beschränken die Gruppenerstellung auf eine bestimmte Gruppe von Personen.](../../solutions/manage-creation-of-groups.md) Wenn Sie die Gruppenerstellung einschränken, können Benutzer, die keine Gruppen erstellen können, keine SharePoint Websites, Planner, Teams, Outlook Gruppenkalender, Streamgruppen, Yammer Gruppen, freigegebene Bibliotheken in OneDrive oder freigegebene Power BI Arbeitsbereiche erstellen. Diese Dienste erfordern, dass die Personen, die sie erstellen, in der Lage sind, eine Gruppe zu erstellen. Benutzer können weiterhin an Gruppenaktivitäten teilnehmen, z. B. aufgaben in Planner erstellen oder Teams Chat verwenden, sofern sie Mitglied der Gruppe sind.

Gruppen weisen die folgenden Rollen auf:

- **Besitzer**: Sie können Mitglieder hinzufügen oder entfernen und über eindeutige Berechtigungen wie die Möglichkeit zum Löschen von Unterhaltungen aus dem geteilten Posteingang oder zum Ändern verschiedener Einstellungen für die Gruppe verfügen. Gruppenbesitzer können Sie die Gruppe umbenennen, die Beschreibung oder das Bild aktualisieren und mehr.
- **Mitglieder**: Sie können auf alle Inhalte der Gruppe zugreifen, aber keine Gruppeneinstellungen ändern. Standardmäßig können Gruppenmitglieder Gäste einladen, Ihrer Gruppe beizutreten, und Sie können [diese Einstellung steuern](manage-guest-access-in-groups.md).
- **Gäste**: Gruppengäste sind Mitglieder von außerhalb Ihrer Organisation.

Nur globale Administratoren, Benutzeradministratoren und Gruppenadministratoren können Gruppen im Microsoft 365 Admin Center erstellen und verwalten. Sie dürfen kein delegierter Administrator sein (z. B. ein Berater als beauftragter Administrator).

Als Administrator haben Sie die folgenden Möglichkeiten:

- [Festlegen, wer Gruppen erstellen kann](../../solutions/manage-creation-of-groups.md)
- [Erstellen einer Benennungsrichtlinie für Gruppen in Ihrer Organisation](../../solutions/groups-naming-policy.md)
- [Auswählen, welche Domäne beim Erstellen einer Gruppe verwendet werden soll](../../solutions/choose-domain-to-create-groups.md)
- [Verwalten des Gastzugriffs auf Gruppen](manage-guest-access-in-groups.md)
- [Wiederherstellen einer gelöschten Gruppe](restore-deleted-group.md) (innerhalb von 30 Tagen nach dem Löschvorgang)

Wenn Sie eine automatisierte Methode zum Verwalten des Lebenszyklus Ihrer Microsoft 365 Gruppen bevorzugen, können Sie Ablaufrichtlinien verwenden, um Gruppen in einem bestimmten Zeitintervall ablaufen zu lassen. Die Besitzer der Gruppe erhalten 30, 15 und 1 Tag vor ablaufen der Gruppe eine E-Mail, mit der sie die Gruppe verlängern können, wenn sie noch benötigt wird. Siehe: [Microsoft 365 Ablaufrichtlinie für Gruppen.](../../solutions/microsoft-365-groups-expiration-policy.md)

Sie können Gruppen entweder über das Microsoft 365 Admin Center oder [mithilfe von PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) durchführen.

Wenn Sie viele Benutzer haben, z. B. in einem großen Unternehmen oder Unternehmen, haben Sie möglicherweise viele Benutzer, die Gruppen für verschiedene Zwecke erstellen. Es wird dringend empfohlen, dass Sie den [Plan für Governance in Microsoft 365-Gruppen](../../solutions/collaboration-governance-overview.md) nach bewährten Methoden überprüfen.

## <a name="group-limits"></a>Beschränkungen für Gruppen

Die folgenden Grenzwerte gelten für Microsoft 365-Gruppen:

|Maximale Anzahl für|Wert|
|:---------|:----|
|Besitzer pro Gruppe|100|
|Gruppen, die ein Benutzer erstellen kann|250|
|Gruppen, die ein Administrator erstellen kann|Bis zum Standardmäßigen Mandantengrenzwert von 500 K|
|Anzahl Mitglieder |Mehr als 1 000, obwohl nur 1 000 gleichzeitig auf die Gruppen-Chats zugreifen können. <br>Benutzer bemerken möglicherweise Verzögerungen beim Zugriff auf den Kalender und Unterhaltungen in großen Gruppen in Outlook.|
|Anzahl von Gruppen, in denen ein Benutzer Mitglied sein kann|7,000|
|Dateispeicher|1 Terabyte + 10 GB pro abonniertem Benutzer und jeder andere erworbene Speicher. Sie können eine unbegrenzte Menge zusätzlicher Speicher erwerben.|
|Größe des Gruppenpostfachs|50 GB|

Die standardmäßige maximale Anzahl von Microsoft 365 Gruppen, die eine Organisation haben kann, beträgt 500.000. Um das Standardlimit zu überschreiten, müssen Sie sich an den Microsoft-Support wenden. Weitere Informationen zu Microsoft 365 Gruppengrenzwerten finden Sie unter [Microsoft 365 Gruppen – Administratorhilfe.](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

Die Verwaltung Ihrer Microsoft 365 Gruppen ist effektiver, wenn Sie über umsetzbare Informationen zur Gruppennutzung verfügen. Das Microsoft 365 Admin Center verfügt über ein Berichterstellungstool, mit dem Sie sehen können, wie viele aktive Gruppen Sie haben und wie Benutzer die Gruppen verwenden. Weitere Informationen finden Sie [unter: Microsoft 365 Berichte im Admin Center.](../activity-reports/office-365-groups.md)

## <a name="sensitivity-labels"></a>Vertraulichkeitsbezeichnungen

Sie können Vertraulichkeitsbezeichnungen erstellen, die die Benutzer in Ihrer Organisation festlegen können, wenn sie eine Microsoft 365 Gruppe erstellen. Mit Vertraulichkeitsbezeichnungen können Sie Folgendes konfigurieren: 

- Datenschutz (öffentlich oder privat)
- Zugriff externer Benutzer
- Nicht verwalteter Gerätezugriff

Sie können z. B. eine Bezeichnung namens *"Streng vertraulich"* erstellen und angeben, dass mit dieser Bezeichnung erstellte Gruppen privat sind und externe Benutzer nicht zulassen. Wenn Benutzer in Ihrer Organisation diese Bezeichnung während der Gruppenerstellung auswählen, wird die Gruppe auf "Privat" festgelegt, und Gruppenmitglieder können der Gruppe keine externen Benutzer hinzufügen.

> [!IMPORTANT]
> Wenn Sie derzeit Klassifizierungsbezeichnungen verwenden, stehen sie benutzern nicht mehr zur Verfügung, die Gruppen erstellen, sobald Vertraulichkeitsbezeichnungen aktiviert sind. 

Informationen zum Erstellen, Verwalten und Verwenden von Vertraulichkeitsbezeichnungen finden Sie unter [Verwenden von Vertraulichkeitsbezeichnungen zum Schutz von Inhalten in Microsoft Teams, Microsoft 365 Gruppen und SharePoint Websites.](../../compliance/sensitivity-labels-teams-groups-sites.md)

## <a name="which-microsoft-365-plans-include-groups"></a>Welche Microsoft 365 Pläne umfassen Gruppen?

Jedes Microsoft 365-Abonnement mit Exchange Online und SharePoint Online unterstützt Gruppen. Dazu gehören die Pläne "Business Essentials" und "Business Premium" sowie die Pläne Enterprise E1, E3 und E5. Die Gruppe übernimmt die Lizenzierung der Person, die die Gruppe erstellt (auch als "Organisator" der Gruppe bezeichnet). Solange der Organisator über die richtige Lizenz für alle Features verfügt, die die Gruppe haben soll, wird diese Lizenz an die Gruppe übermittelt.

> [!NOTE]
> Weitere Informationen zu Microsoft 365 Dienstfamilien und -plänen finden Sie unter [Microsoft 365 Planoptionen.](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)

Wenn Sie über einen Nur-Exchange-Plan verfügen, können Sie weiterhin die Features des freigegebenen Posteingangs und des freigegebenen Kalenders von Gruppen in Outlook erhalten, aber Sie erhalten nicht die Dokumentbibliothek, Planner oder eine der anderen Funktionen.

Microsoft 365 Gruppen arbeiten mit Azure Active Directory. Welche Gruppenfeatures Sie erhalten, hängt davon ab, welche Azure Active Directory Abonnement Sie haben und welche Lizenzen dem Organisator der Gruppe zugewiesen sind.

> [!IMPORTANT]
> Wenn Sie über ein Azure AD Premium-Abonnement verfügen, können Benutzer für alle Gruppenfeatures der Gruppe beitreten, unabhängig davon, ob ihnen eine AAD P1-Lizenz zugewiesen wurde. Die Lizenzierung wird nicht erzwungen.
> In regelmäßigen Abständen werden Verwendungsberichte generiert, die Ihnen mitteilen, welchen Benutzer eine Lizenz fehlt oder eine zugewiesene Lizenz benötigen, damit sie die Lizenzierungsanforderungen erfüllen. Nehmen wir beispielsweise an, dass ein Benutzer nicht über eine Lizenz verfügt und er einer Gruppe hinzugefügt wird, in der die Benennungsrichtlinie erzwungen wird. In dem Bericht wird für Sie gekennzeichnet, dass der Benutzer eine Lizenz benötigt.

## <a name="related-content"></a>Verwandte Inhalte

[Weitere Informationen zu Microsoft 365-Gruppen](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2) (Artikel)\
[Aktualisieren von Verteilerlisten auf Microsoft 365 Gruppen](../manage/upgrade-distribution-lists.md) (Artikel)\
[Verwalten von Microsoft 365-Gruppen mit PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (Artikel)\
[SharePoint Onlinebeschränkungen](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) (Artikel)\
[Organisieren von Gruppen und Kanälen in Microsoft Stream](/stream/groups-channels-organization) (Artikel)
