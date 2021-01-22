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
description: Erfahren Sie mehr über Microsoft 365-Gruppen.
ms.openlocfilehash: b3bc0c30f4ac292da7af46678fc742854984db12
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925350"
---
# <a name="overview-of-microsoft-365-groups-for-administrators"></a>Übersicht über Microsoft 365-Gruppen für Administratoren

Microsoft 365-Gruppen ist der Basismitgliedschaftsdienst, der die gesamte Teamarbeit in Microsoft 365 steuert. Mit Microsoft 365-Gruppen können Sie einer Gruppe von Personen Zugriff auf eine Sammlung freigegebener Ressourcen geben. Diese Ressourcen enthalten:

- Einen freigegebenen Outlook-Posteingang
- Einen freigegebenen Kalender
- Eine SharePoint-Dokumentbibliothek
- Einen Planner
- Ein OneNote-Notizbuch
- Power BI
- Yammer (wenn die Gruppe in Yammer erstellt wurde)
- Ein Team (wenn die Gruppe in Teams erstellt wurde)
- Roadmap (wenn Sie über Project für das Web verfügen)

Bei einer Microsoft 365-Gruppe müssen Sie diesen Ressourcen nicht manuell Berechtigungen zuweisen. Durch das Hinzufügen von Personen zur Gruppe erhalten sie automatisch die erforderlichen Berechtigungen.

Jeder Benutzer kann eine Gruppe erstellen, es sei denn, Sie beschränken die Gruppenerstellung auf eine [bestimmte Gruppe von Personen.](manage-creation-of-groups.md) Wenn Sie die Gruppenerstellung einschränken, können Benutzer, die keine Gruppen erstellen können, keine SharePoint-Websites, -Planer oder -Teams erstellen. Für diese Dienste müssen die Personen, die sie erstellen, in der Lage sein, eine Gruppe zu erstellen. Benutzer können weiterhin an Gruppenaktivitäten teilnehmen, z. B. an der Erstellung von Aufgaben in Planner oder an der Verwendung von Teams-Chats, sofern sie Mitglied der Gruppe sind.

Gruppen weisen die folgenden Rollen auf:

- **Besitzer**: Sie können Mitglieder hinzufügen oder entfernen und über eindeutige Berechtigungen wie die Möglichkeit zum Löschen von Unterhaltungen aus dem geteilten Posteingang oder zum Ändern verschiedener Einstellungen für die Gruppe verfügen. Gruppenbesitzer können Sie die Gruppe umbenennen, die Beschreibung oder das Bild aktualisieren und mehr.
- **Mitglieder**: Sie können auf alle Inhalte der Gruppe zugreifen, aber keine Gruppeneinstellungen ändern. Standardmäßig können Gruppenmitglieder Gäste einladen, Ihrer Gruppe beizutreten, und Sie können [diese Einstellung steuern](manage-guest-access-in-groups.md).
- **Gäste**: Gruppengäste sind Mitglieder von außerhalb Ihrer Organisation.

Nur globale Administratoren, Benutzeradministratoren und Gruppenadministratoren können Gruppen im Microsoft 365 Admin Center erstellen und verwalten. Sie dürfen kein delegierter Administrator sein (z. B. ein Berater als beauftragter Administrator).

Als Administrator haben Sie die folgenden Möglichkeiten:

- [Festlegen, wer Gruppen erstellen kann](manage-creation-of-groups.md)
- [Erstellen einer Benennungsrichtlinie für Gruppen in Ihrer Organisation](groups-naming-policy.md)
- [Auswählen, welche Domäne beim Erstellen einer Gruppe verwendet werden soll](choose-domain-to-create-groups.md)
- [Verwalten des Gastzugriffs auf Gruppen](manage-guest-access-in-groups.md)
- [Wiederherstellen einer gelöschten Gruppe](restore-deleted-group.md) (innerhalb von 30 Tagen nach dem Löschvorgang)

Wenn Sie eine automatisiertere Möglichkeit zum Verwalten des Lebenszyklus Ihrer Microsoft 365-Gruppen bevorzugen, können Sie Ablaufrichtlinien verwenden, um Gruppen in einem bestimmten Zeitintervall zu ablaufen. Die Besitzer der Gruppe erhalten 30, 15 und 1 Tag vor Ablauf der Gruppe eine E-Mail, mit der sie die Gruppe verlängern können, wenn sie noch benötigt wird. Siehe: [Ablaufrichtlinie für Microsoft 365-Gruppen.](office-365-groups-expiration-policy.md)

Sie können Gruppen entweder über das Microsoft 365 Admin Center oder [mithilfe von PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershel) durchführen.

Wenn Sie viele Benutzer haben, z. B. in einem großen Unternehmen oder Unternehmen, haben Sie möglicherweise viele Benutzer, die Gruppen für verschiedene Zwecke erstellen. Es wird dringend empfohlen, den [Plan für governance in Microsoft 365-Gruppen](plan-for-groups-governance.md) auf bewährte Methoden zu überprüfen.

## <a name="group-limits"></a>Grenzwerte für Gruppen

Die folgenden Grenzwerte gelten für Microsoft 365-Gruppen:

|Maximale Anzahl für|Wert|
|:---------|:----|
|Besitzer pro Gruppe|100|
|Gruppen, die ein Benutzer erstellen kann|250|
|Gruppen, die ein Administrator erstellen kann|Bis zum standardmäßigen Mandantenlimit von 500 K|
|Anzahl Mitglieder |Mehr als 1 000, obwohl nur 1 000 gleichzeitig auf die Gruppen-Chats zugreifen können. <br>Benutzer bemerken möglicherweise Verzögerungen beim Zugriff auf den Kalender und Unterhaltungen in großen Gruppen in Outlook.|
|Anzahl von Gruppen, in denen ein Benutzer Mitglied sein kann|7,000|
|Dateispeicher|1 Terabyte + 10 GB pro abonniertem Benutzer + jeder andere gekaufte Speicher. Sie können eine unbegrenzte Menge an zusätzlichem Speicher erwerben.|
|Größe des Gruppenpostfachs|50 GB|

Die standardmäßige maximale Anzahl von Microsoft 365-Gruppen, die eine Organisation haben kann, beträgt 500.000. Um den Standardgrenzwert zu überschreiten, müssen Sie sich an den Microsoft-Support wenden. Weitere Informationen zu Microsoft 365-Gruppenbeschränkungen finden Sie in der Hilfe zu [Microsoft 365-Gruppen – Administrator.](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

Die Verwaltung Ihrer Microsoft 365-Gruppen ist effektiver, wenn Sie über Informationen mit Aktionen zur Gruppennutzung verfügen. Das Microsoft 365 Admin Center verfügt über ein Berichterstellungstool, mit dem Sie sehen können, wie viele aktive Gruppen Sie verwenden und wie Benutzer die Gruppen verwenden. Weitere Informationen [finden Sie unter: Microsoft 365-Berichte](../activity-reports/office-365-groups.md) im Admin Center.

## <a name="sensitivity-labels"></a>Vertraulichkeitsbezeichnungen

Sie können Vertraulichkeitsbezeichnungen erstellen, die die Benutzer in Ihrer Organisation festlegen können, wenn sie eine Microsoft 365-Gruppe erstellen. Mit Vertraulichkeitsbezeichnungen können Sie: 

- Datenschutz (öffentlich oder privat)
- Zugriff externer Benutzer
- Nicht verwalteter Gerätezugriff

Sie können z. B. eine Bezeichnung mit dem Namen "Streng *vertraulich"* erstellen und angeben, dass alle mit dieser Bezeichnung erstellten Gruppen privat sind und keine externen Benutzer zulassen. Wenn Benutzer in Ihrer Organisation diese Bezeichnung während der Gruppenerstellung auswählen, wird die Gruppe auf "Privat" festgelegt, und Gruppenmitglieder können der Gruppe keine externen Benutzer hinzufügen.

> [!IMPORTANT]
> Wenn Sie zurzeit Klassifizierungsbezeichnungen verwenden, stehen sie Benutzern, die Gruppen erstellen, nach der Aktivierung von Vertraulichkeitsbezeichnungen nicht mehr zur Verfügung. 

Informationen zum Erstellen, Verwalten und Verwenden von Vertraulichkeitsbezeichnungen finden Sie unter Verwenden von Vertraulichkeitsbezeichnungen zum Schutz von [Inhalten in Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

## <a name="which-microsoft-365-plans-include-groups"></a>Welche Microsoft 365-Pläne enthalten Gruppen?

Alle Microsoft 365-Abonnements mit Exchange Online und SharePoint Online unterstützen Gruppen. Dazu gehören die Business Essentials- und Business Premium-Pläne sowie die Enterprise E1-, E3- und E5-Pläne. Die Gruppe übernimmt die Lizenzierung der Person, die die Gruppe erstellt (auch als "Organisator" der Gruppe bezeichnet). Solange der Organisator über die richtige Lizenz für alle Features verfügt, die die Gruppe haben soll, wird diese Lizenz an die Gruppe übermittelt.

> [!NOTE]
> Weitere Informationen zu Microsoft 365-Dienstfamilien und -Plänen finden Sie unter [Microsoft 365-Planoptionen.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)

Wenn Sie über einen Nur-Exchange-Plan verfügen, können Sie weiterhin die Features für freigegebenen Posteingang und freigegebenen Kalender von Gruppen in Outlook erhalten, aber Sie erhalten nicht die Dokumentbibliothek, Planner oder eine der anderen Funktionen.

Microsoft 365-Gruppen funktionieren mit Azure Active Directory. Welche Gruppenfeatures Sie erhalten, hängt davon ab, über welches Azure Active Directory-Abonnement Sie verfügen und welche Lizenzen dem Organisator der Gruppe zugewiesen sind.

> [!IMPORTANT]
> Wenn Sie über ein Azure AD -Premium-Abonnement verfügen, können Benutzer für alle Gruppenfeatures der Gruppe beitreten, unabhängig davon, ob ihnen eine AAD -P1-Lizenz zugewiesen ist. Die Lizenzierung wird nicht erzwungen.
> In regelmäßigen Abständen werden Verwendungsberichte generiert, die Ihnen mitteilen, welchen Benutzer eine Lizenz fehlt oder eine zugewiesene Lizenz benötigen, damit sie die Lizenzierungsanforderungen erfüllen. Nehmen wir beispielsweise an, dass ein Benutzer nicht über eine Lizenz verfügt und er einer Gruppe hinzugefügt wird, in der die Benennungsrichtlinie erzwungen wird. In dem Bericht wird für Sie gekennzeichnet, dass der Benutzer eine Lizenz benötigt.

## <a name="related-articles"></a>Verwandte Artikel

[Informationen zu Microsoft 365-Gruppen](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Aktualisieren von Verteilerlisten auf Microsoft 365-Gruppen](../manage/upgrade-distribution-lists.md)

[Verwalten von Microsoft 365-Gruppen mit PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)

[SharePoint Online-Beschränkungen](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
