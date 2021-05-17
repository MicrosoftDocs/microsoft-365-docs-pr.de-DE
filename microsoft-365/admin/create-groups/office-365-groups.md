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
description: Erfahren Sie mehr Microsoft 365 Gruppen.
ms.openlocfilehash: 18cb37a4aae7a163d2e198194251abc727b48848
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910606"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>Übersicht über Microsoft 365-Gruppen für Administratoren

Microsoft 365 Gruppen ist der Basismitgliedschaftsdienst, der die gesamte Teamarbeit Microsoft 365. Mit Microsoft 365 Gruppen können Sie einer Gruppe von Personen Zugriff auf eine Sammlung freigegebener Ressourcen geben. Diese Ressourcen enthalten:

- Einen freigegebenen Outlook-Posteingang
- Einen freigegebenen Kalender
- Eine SharePoint-Dokumentbibliothek
- Einen Planner
- Ein OneNote-Notizbuch
- Power BI
- Yammer (wenn die Gruppe in Yammer erstellt wurde)
- Ein Team (wenn die Gruppe in Teams erstellt wurde)
- Roadmap (wenn Sie eine Project für das Web haben)
- Stream

Bei einer Microsoft 365 müssen Sie diesen Ressourcen nicht manuell Berechtigungen zuweisen. Durch das Hinzufügen von Personen zur Gruppe erhalten sie automatisch die erforderlichen Berechtigungen.

Jeder Benutzer kann eine Gruppe erstellen, es sei denn, Sie beschränken die Gruppenerstellung auf eine [bestimmte Gruppe von Personen.](../../solutions/manage-creation-of-groups.md) Wenn Sie die Gruppenerstellung einschränken, können Benutzer, die keine Gruppen erstellen können, keine SharePoint, Planer oder Teams erstellen. Diese Dienste erfordern, dass die Personen, die sie erstellen, eine Gruppe erstellen können. Benutzer können weiterhin an Gruppenaktivitäten teilnehmen, z. B. beim Erstellen von Aufgaben in Planner oder Teams Chat, sofern sie Mitglied der Gruppe sind.

Gruppen weisen die folgenden Rollen auf:

- **Besitzer**: Sie können Mitglieder hinzufügen oder entfernen und über eindeutige Berechtigungen wie die Möglichkeit zum Löschen von Unterhaltungen aus dem geteilten Posteingang oder zum Ändern verschiedener Einstellungen für die Gruppe verfügen. Gruppenbesitzer können Sie die Gruppe umbenennen, die Beschreibung oder das Bild aktualisieren und mehr.
- **Mitglieder**: Sie können auf alle Inhalte der Gruppe zugreifen, aber keine Gruppeneinstellungen ändern. Standardmäßig können Gruppenmitglieder Gäste einladen, Ihrer Gruppe beizutreten, und Sie können [diese Einstellung steuern](manage-guest-access-in-groups.md).
- **Gäste**: Gruppengäste sind Mitglieder von außerhalb Ihrer Organisation.

Nur globale Administratoren, Benutzeradministratoren und Gruppenadministratoren können Gruppen im Microsoft 365 verwalten. Sie dürfen kein delegierter Administrator sein (z. B. ein Berater als beauftragter Administrator).

Als Administrator haben Sie die folgenden Möglichkeiten:

- [Festlegen, wer Gruppen erstellen kann](../../solutions/manage-creation-of-groups.md)
- [Erstellen einer Benennungsrichtlinie für Gruppen in Ihrer Organisation](../../solutions/groups-naming-policy.md)
- [Auswählen, welche Domäne beim Erstellen einer Gruppe verwendet werden soll](../../solutions/choose-domain-to-create-groups.md)
- [Verwalten des Gastzugriffs auf Gruppen](manage-guest-access-in-groups.md)
- [Wiederherstellen einer gelöschten Gruppe](restore-deleted-group.md) (innerhalb von 30 Tagen nach dem Löschvorgang)

Wenn Sie eine automatisiertere Methode zum Verwalten des Lebenszyklus Ihrer Microsoft 365 bevorzugen, können Sie Ablaufrichtlinien verwenden, um Gruppen in einem bestimmten Zeitintervall zu ablaufen. Die Besitzer der Gruppe erhalten eine E-Mail 30, 15 und 1 Tag vor Ablauf der Gruppe, mit der sie die Gruppe verlängern können, wenn sie noch benötigt wird. Weitere Informationen finden [Sie Microsoft 365 Ablaufrichtlinie für Gruppen.](../../solutions/microsoft-365-groups-expiration-policy.md)

Sie können Gruppen entweder über das Microsoft 365 Admin Center oder [mithilfe von PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) durchführen.

Wenn Sie über viele Benutzer verfügen, z. B. in einem großen Unternehmen oder Unternehmen, haben Sie möglicherweise viele Benutzer, die Gruppen für verschiedene Zwecke erstellen. Es wird dringend empfohlen, dass Sie [plan for governance in Microsoft 365 auf](../../solutions/collaboration-governance-overview.md) bewährte Methoden überprüfen.

## <a name="group-limits"></a>Grenzwerte für Gruppen

Die folgenden Grenzwerte gelten für Microsoft 365 Gruppen:

|Maximale Anzahl für|Wert|
|:---------|:----|
|Besitzer pro Gruppe|100|
|Gruppen, die ein Benutzer erstellen kann|250|
|Gruppen, die ein Administrator erstellen kann|Bis zu einem Standardmäßigen Mandantengrenzwert von 500 K|
|Anzahl Mitglieder |Mehr als 1 000, obwohl nur 1 000 gleichzeitig auf die Gruppen-Chats zugreifen können. <br>Benutzer bemerken möglicherweise Verzögerungen beim Zugriff auf den Kalender und Unterhaltungen in großen Gruppen in Outlook.|
|Anzahl von Gruppen, in denen ein Benutzer Mitglied sein kann|7,000|
|Dateispeicher|1 Terabyte + 10 GB pro abonniertem Benutzer + jeder andere erworbene Speicher. Sie können eine unbegrenzte Menge zusätzlichen Speichers erwerben.|
|Größe des Gruppenpostfachs|50 GB|

Die standardmäßige maximale Anzahl Microsoft 365 gruppen, die eine Organisation haben kann, ist 500.000. Um den Standardgrenzwert zu überschreiten, müssen Sie sich an den Microsoft-Support wenden. Weitere Informationen zu Microsoft 365 Gruppenbeschränkungen finden Sie [unter Microsoft 365 Groups - Admin help](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2).

Die Verwaltung Microsoft 365 Gruppen ist effektiver, wenn Sie über aktionenfähige Informationen zur Gruppennutzung verfügen. Das Microsoft 365 Admin Center verfügt über ein Berichterstellungstool, mit dem Sie sehen können, wie viele aktive Gruppen Sie haben und wie Benutzer die Gruppen verwenden. Weitere Informationen [finden Microsoft 365 Berichte im Admin Center.](../activity-reports/office-365-groups.md)

## <a name="sensitivity-labels"></a>Vertraulichkeitsbezeichnungen

Sie können Vertraulichkeitsbezeichnungen erstellen, die die Benutzer in Ihrer Organisation festlegen können, wenn sie eine Microsoft 365 erstellen. Mit Vertraulichkeitsbezeichnungen können Sie konfigurieren: 

- Datenschutz (öffentlich oder privat)
- Zugriff externer Benutzer
- Nicht verwalteter Gerätezugriff

Sie können beispielsweise eine Bezeichnung mit dem Namen *"Streng vertraulich"* erstellen und angeben, dass alle mit dieser Bezeichnung erstellten Gruppen privat sind und keine externen Benutzer zulassen. Wenn Benutzer in Ihrer Organisation diese Bezeichnung während der Gruppenerstellung auswählen, wird die Gruppe auf privat festgelegt, und Gruppenmitglieder dürfen der Gruppe keine externen Benutzer hinzufügen.

> [!IMPORTANT]
> Wenn Sie derzeit Klassifizierungsbezeichnungen verwenden, stehen sie Benutzern, die Gruppen erstellen, nach aktivierung von Vertraulichkeitsbezeichnungen nicht mehr zur Verfügung. 

Informationen zum Erstellen, Verwalten und Verwenden von Vertraulichkeitsbezeichnungen finden Sie unter Verwenden von Vertraulichkeitsbezeichnungen zum Schutz von [Inhalten in Microsoft Teams, Microsoft 365 Gruppen](../../compliance/sensitivity-labels-teams-groups-sites.md)und SharePoint Websites .

## <a name="which-microsoft-365-plans-include-groups"></a>Welche Microsoft 365 enthalten Gruppen?

Alle Microsoft 365, die über Exchange Online und SharePoint Online verfügen, unterstützen Gruppen. Dazu gehören die Business Essentials- Premium Business-Enterprise E1-, E3- und E5-Pläne. Die Gruppe übernimmt die Lizenzierung der Person, die die Gruppe erstellt (auch als "Organisator" der Gruppe bezeichnet). Solange der Organisator über die richtige Lizenz für alle Features verfügt, die die Gruppe haben soll, wird diese Lizenz an die Gruppe übermittelt.

> [!NOTE]
> Weitere Informationen zu Microsoft 365 Servicefamilien und -plänen finden Sie [unter Microsoft 365 plan options](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options).

Wenn Sie über einen Exchange-Plan verfügen, können Sie weiterhin die freigegebenen Posteingangs- und freigegebenen Kalenderfeatures von Gruppen in Outlook erhalten, sie erhalten jedoch keine Dokumentbibliothek, keinen Planner oder keine der anderen Funktionen.

Microsoft 365 gruppen arbeiten mit Azure Active Directory. Welche Gruppenfeatures Sie erhalten, hängt davon ab, Azure Active Directory Sie haben und welche Lizenzen dem Organisator der Gruppe zugewiesen sind.

> [!IMPORTANT]
> Wenn Sie über ein Azure AD Premium-Abonnement verfügen, können Benutzer für alle Gruppenfeatures der Gruppe beitreten, unabhängig davon, ob ihnen eine AAD P1-Lizenz zugewiesen ist. Die Lizenzierung wird nicht erzwungen.
> In regelmäßigen Abständen werden Verwendungsberichte generiert, die Ihnen mitteilen, welchen Benutzer eine Lizenz fehlt oder eine zugewiesene Lizenz benötigen, damit sie die Lizenzierungsanforderungen erfüllen. Nehmen wir beispielsweise an, dass ein Benutzer nicht über eine Lizenz verfügt und er einer Gruppe hinzugefügt wird, in der die Benennungsrichtlinie erzwungen wird. In dem Bericht wird für Sie gekennzeichnet, dass der Benutzer eine Lizenz benötigt.

## <a name="related-articles"></a>Verwandte Artikel

[Erfahren Sie mehr über Microsoft 365 Gruppen](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Aktualisieren von Verteilerlisten auf Microsoft 365 Gruppen](../manage/upgrade-distribution-lists.md)

[Verwalten von Microsoft 365-Gruppen mit PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md)

[SharePoint Online-Beschränkungen](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)

[Organisieren von Gruppen und Kanälen in Microsoft Stream](/stream/groups-channels-organization)