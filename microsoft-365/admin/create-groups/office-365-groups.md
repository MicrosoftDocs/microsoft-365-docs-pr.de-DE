---
title: Übersicht über Microsoft 365-Gruppen für Administratoren
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Erfahren Sie mehr über Microsoft 365 Gruppen.
ms.openlocfilehash: 5d85204687641e74f9a705162df01cebd7eeee26
ms.sourcegitcommit: 3f8e573244bc082518125e339a385c41ef6ee800
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2020
ms.locfileid: "48337169"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>Übersicht über Microsoft 365-Gruppen für Administratoren

Microsoft 365 Groups ist der grundlegende Mitgliedschaftsdienst, der alle Teamarbeit in Microsoft 365 steuert. Mit Microsoft 365-Gruppen können Sie einer Gruppe von Personen Zugriff auf eine Sammlung von Ressourcen für die Zusammenarbeit geben, die diese Personen freigeben möchten. Diese Ressourcen enthalten:

- Einen freigegebenen Outlook-Posteingang
- Einen freigegebenen Kalender
- Eine SharePoint-Dokumentbibliothek
- Einen Planner
- Ein OneNote-Notizbuch
- Power BI
- Yammer (wenn die Gruppe in Yammer erstellt wurde)
- Ein Team (wenn die Gruppe in Teams erstellt wurde)
- Roadmap (wenn Sie Project für das Internet haben)

Bei einer Microsoft 365-Gruppe müssen Sie keine Berechtigungen für jede dieser Ressourcen manuell zuweisen, da Ihnen das Hinzufügen von Personen zur Gruppe automatisch die Berechtigungen erteilt, die Sie für die von der Gruppe bereitgestellten Tools benötigen.

Jeder Benutzer kann eine Gruppe erstellen, es sei denn [, Sie beschränken die Gruppenerstellung auf eine bestimmte Gruppe von Personen](manage-creation-of-groups.md). Beachten Sie: Wenn Sie die Gruppenerstellung einschränken, können Benutzer, die keine Gruppen erstellen können, auch keine SharePoint-Websites, -Planner oder -Teams erstellen. Diese Dienste erfordern, dass die Personen, die Sie erstellen, eine Gruppe erstellen können. Benutzer können weiterhin an Gruppenaktivitäten teilnehmen, beispielsweise Erstellen von Aufgaben im Planer oder Verwenden von Microsoft Teams Chat, vorausgesetzt, Sie sind Mitglied der Gruppe.

Gruppen weisen die folgenden Rollen auf:

- **Besitzer**: Sie können Mitglieder hinzufügen oder entfernen und über eindeutige Berechtigungen wie die Möglichkeit zum Löschen von Unterhaltungen aus dem geteilten Posteingang oder zum Ändern verschiedener Einstellungen für die Gruppe verfügen. Gruppenbesitzer können Sie die Gruppe umbenennen, die Beschreibung oder das Bild aktualisieren und mehr.
- **Mitglieder**: Sie können auf alle Inhalte der Gruppe zugreifen, aber keine Gruppeneinstellungen ändern. Standardmäßig können Gruppenmitglieder Gäste einladen, Ihrer Gruppe beizutreten, und Sie können [diese Einstellung steuern](manage-guest-access-in-groups.md).
- **Gäste**: Gruppengäste sind Mitglieder von außerhalb Ihrer Organisation.

Nur globale Administratoren, Benutzer Administratoren und Gruppen Administratoren können Gruppen im Microsoft 365 Admin Center erstellen und verwalten. Sie dürfen kein delegierter Administrator sein (z. B. ein Berater als beauftragter Administrator).

Als Administrator haben Sie die folgenden Möglichkeiten:

- [Festlegen, wer Gruppen erstellen kann](manage-creation-of-groups.md)
- [Erstellen einer Benennungsrichtlinie für Gruppen in Ihrer Organisation](groups-naming-policy.md)
- [Auswählen, welche Domäne beim Erstellen einer Gruppe verwendet werden soll](choose-domain-to-create-groups.md)
- [Verwalten des Gastzugriffs auf Gruppen](manage-guest-access-in-groups.md)
- [Wiederherstellen einer gelöschten Gruppe](restore-deleted-group.md) (innerhalb von 30 Tagen nach dem Löschvorgang)

Wenn Sie eine automatisiertere Möglichkeit zum Verwalten des Lebenszyklus Ihrer Microsoft 365-Gruppen bevorzugen, können Sie Ablaufrichtlinien zum Ablaufen von Gruppen in einem bestimmten Zeitintervall verwenden. Die Besitzer der Gruppe erhalten-30 Tage, 15 Tage und 1 Tag vor Gruppenablauf Benachrichtigungen per E-Mail, sodass sie die Gruppe einfach verlängern können, falls diese noch benötigt wird. Siehe: [Microsoft 365 Group-Ablaufrichtlinie](office-365-groups-expiration-policy.md).

Sie können Gruppen entweder über das Microsoft 365 Admin Center oder [mithilfe von PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershel) durchführen.

Wenn Sie viele Benutzer haben, z. B. in einem großen Unternehmen oder Konzern, haben Sie möglicherweise viele Benutzer, die Gruppen für unterschiedliche Zwecke erstellen. Es wird dringend empfohlen, [Plan for Governance in Microsoft 365 Groups](plan-for-groups-governance.md) for Best Practices zu überprüfen.

## <a name="group-limits"></a>Grenzwerte für Gruppen

Die folgenden Grenzwertegelten für Microsoft 365-Gruppen:

|Maximale Anzahl für|Wert|
|:---------|:----|
|Besitzer pro Gruppe|100|
|Gruppen, die ein Benutzer erstellen kann|250|
|Gruppen, die ein Administrator erstellen kann|Bis zu 500.000 (Mandanten-Standardgrenzwert)|
|Anzahl Mitglieder |Mehr als 1 000, obwohl nur 1 000 gleichzeitig auf die Gruppen-Chats zugreifen können. <br>Möglicherweise kommt es in großen Gruppen in Outlook zu Verzögerungen beim Zugreifen auf Kalender und Unterhaltungen.|
|Anzahl von Gruppen, in denen ein Benutzer Mitglied sein kann|7.000|
|Dateispeicher|1 TB plus 10 GB pro Abonnementbenutzer plus zusätzlich gekaufter Speicher. Sie können eine unbegrenzte Menge weiteren Speichers kaufen.|
|Größe des Gruppenpostfachs|50 GB|

Die standardmäßige maximale Anzahl von Microsoft 365-Gruppen, die eine Organisation haben kann, ist 500.000. Um über den Standardgrenzwert hinauszugehen, müssen Sie sich an den Microsoft-Support wenden. Weitere Informationen zu den Grenzwerten für Microsoft 365-Gruppen finden Sie unter [Microsoft 365 groups-admin Help](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2).

Die Verwaltung Ihrer Microsoft 365-Gruppen ist effektiver, wenn Sie über Aktions fähige Informationen zur Verwendung von Gruppen verfügen. Das Microsoft 365 Admin Center verfügt über ein Berichtstool, mit dem Sie Dinge wie die Speichernutzung, die Anzahl der aktiven Gruppen und sogar die Verwendung der Gruppen durch Ihre Benutzer anzeigen können. Weitere Informationen finden Sie unter: [Microsoft 365 Reports im Admin Center](../activity-reports/office-365-groups.md) .

## <a name="sensitivity-labels"></a>Vertraulichkeitsbezeichnungen

Sie können Sensitivitäts Bezeichnungen erstellen, die die Benutzer in Ihrer Organisation festlegen können, wenn Sie eine Microsoft 365-Gruppe erstellen. Mit Sensitivitäts Bezeichnungen können Sie Folgendes konfigurieren: 

- Datenschutz (öffentlich oder privat)
- Zugriff externer Benutzer
- Zugriff auf nicht verwalteter Geräte

Sie können beispielsweise eine Bezeichnung mit dem Namen " *streng vertraulich* " erstellen und angeben, dass jede mit dieser Bezeichnung erstellte Gruppe privat ist und externe Benutzer nicht zulässt. Wenn Benutzer in Ihrer Organisation diese Bezeichnung während der Gruppenerstellung auswählen, wird die Gruppe auf privat festgelegt, und Gruppenmitglieder werden nicht berechtigt, externe Benutzer zur Gruppe hinzuzufügen.

> [!IMPORTANT]
> Wenn Sie derzeit Klassifizierungs Bezeichnungen verwenden, stehen diese nicht mehr für Benutzer zur Verfügung, die Gruppen erstellen, sobald die Vertraulichkeits Bezeichnungen aktiviert sind. 

Informationen zum Erstellen, verwalten und Verwenden von Sensitivitäts Bezeichnungen finden Sie unter [use Sensitivity Labels to Protect Content in Microsoft Teams, Microsoft 365 Groups und SharePoint Sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

## <a name="which-microsoft-365-plans-include-groups"></a>Welche Microsoft 365-Pläne umfassen Gruppen?

Jedes Microsoft 365-Abonnement, das über Exchange Online und SharePoint Online verfügt, wird Gruppen unterstützen. Dazu gehören die Business Essentials- und Business Premium-Pläne sowie die Pläne Enterprise E1, E3 und E5. Die Gruppe übernimmt die Lizenzierung der Person, die die Gruppe erstellt (auch als "Organisator" der Gruppe bezeichnet). Solange der Organisator über die richtige Lizenz für alle Funktionen verfügt, die die Gruppe aufweisen soll, wird die Lizenz an die Gruppe übermittelt.

> [!NOTE]
> Weitere Informationen zu Microsoft 365-Dienst Familien und-Plänen finden Sie unter [Microsoft 365-Planoptionen](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options).

Wenn Sie über einen Exchange-only-Plan verfügen, können Sie weiterhin den freigegebenen Posteingang und die freigegebenen Kalenderfunktionen von Gruppen in Outlook abrufen, aber Sie erhalten nicht die Dokumentbibliothek, den Planer oder andere Funktionen.

Microsoft 365 Gruppen arbeiten mit Azure Active Directory (AAD). Die von Ihnen erhaltenen Gruppenfeatures hängen davon ab, welches Azure Active Directory-Abonnement Sie besitzen und welche Lizenzen dem Organisator der Gruppe zugewiesen sind.

> [!IMPORTANT]
> Wenn Sie über ein Azure AD Premium-Abonnement verfügen, können Benutzer für alle Gruppenfeatures der Gruppe beitreten, unabhängig davon, ob Ihnen eine Aad P1-Lizenz zugewiesen wurde oder nicht. Die Lizenzierung wird nicht erzwungen.
> In regelmäßigen Abständen werden Verwendungsberichte generiert, die Ihnen mitteilen, welchen Benutzer eine Lizenz fehlt oder eine zugewiesene Lizenz benötigen, damit sie die Lizenzierungsanforderungen erfüllen. Nehmen wir beispielsweise an, dass ein Benutzer nicht über eine Lizenz verfügt und er einer Gruppe hinzugefügt wird, in der die Benennungsrichtlinie erzwungen wird. In dem Bericht wird für Sie gekennzeichnet, dass der Benutzer eine Lizenz benötigt.

## <a name="related-articles"></a>Verwandte Artikel

[Informationen zu Microsoft 365-Gruppen](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Aktualisieren von Verteilerlisten auf Microsoft 365-Gruppen](../manage/upgrade-distribution-lists.md)

[Verwalten von Microsoft 365-Gruppen mit PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)

[SharePoint Online-Beschränkungen](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
