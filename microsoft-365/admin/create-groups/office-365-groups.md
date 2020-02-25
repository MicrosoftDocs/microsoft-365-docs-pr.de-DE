---
title: Übersicht über Office 365-Gruppen für Administratoren
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: v-teflor
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
description: Weitere Informationen zu Office 365-Gruppen.
ms.openlocfilehash: e7a65c41d4ecdbc91e163d9a84241ae549a2f9ec
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241316"
---
# <a name="overview-of-office-365-groups-for-administrators"></a>Übersicht über Office 365-Gruppen für Administratoren

Office 365-Gruppen ist der grundlegende Mitgliedschaftsdienst, der die gesamte Teamarbeit in Microsoft 365 unterstützt. Bei Office 365-Gruppen können Sie einer Gruppe von Personen Zugriff auf eine Sammlung von Ressourcen zur Zusammenarbeit ermöglichen, die diese Personen wiederum freigeben können. Diese Ressourcen enthalten:

- Einen freigegebenen Outlook-Posteingang
- Einen freigegebenen Kalender
- Eine SharePoint-Dokumentbibliothek
- Einen Planner
- Power BI
- Yammer (wenn die Gruppe in Yammer erstellt wurde)
- Ein Team (wenn die Gruppe in Teams erstellt wurde)
- Roadmap (wen Sie Project für das Web verwenden)

Bei einer Office 365-Gruppe müssen Sie Berechtigungen für alle diese Ressourcen müssen nicht manuell zuweisen, denn wenn Sie der Gruppe Mitglieder hinzufügen, erhalten diese automatisch alle erforderlichen Berechtigungen zum Verwenden der für Ihre Gruppe bereitgestellten Tools.

Jeder Office 365-Benutzer kann eine Gruppe erstellen, es sei denn, Sie [beschränken die Gruppenerstellung auf bestimmte Personen](manage-creation-of-groups.md). Beachten Sie: Wenn Sie die Gruppenerstellung einschränken, können Benutzer, die keine Gruppen erstellen können, auch keine SharePoint-Websites, -Planner oder -Teams erstellen. Diese Dienste müssen in der Lage sein, eine Gruppe mithilfe des Benutzerkontexts zu erstellen. Benutzer können weiterhin an Gruppenaktivitäten teilnehmen, z. B. am Erstellen von Aufgaben in Planner oder am Beantworten von Unterhaltungen in Outlook, vorausgesetzt, sie sind ein Mitglied der Gruppe.

Gruppen weisen die folgenden Rollen auf:

- **Besitzer**: Sie können Mitglieder hinzufügen oder entfernen und über eindeutige Berechtigungen wie die Möglichkeit zum Löschen von Unterhaltungen aus dem geteilten Posteingang oder zum Ändern verschiedener Einstellungen für die Gruppe verfügen. Gruppenbesitzer können Sie die Gruppe umbenennen, die Beschreibung oder das Bild aktualisieren und mehr.
- **Mitglieder**: Sie können auf alle Inhalte der Gruppe zugreifen, aber keine Gruppeneinstellungen ändern.
- **Gäste**: Gruppengäste sind Mitglieder von außerhalb Ihrer Organisation. Standardmäßig können Gruppenmitglieder Gäste einladen, Ihrer Gruppe beizutreten, und Sie können [diese Einstellung steuern](manage-guest-access-in-groups.md).

Nur globale Administratoren und Benutzerverwaltungsadministratoren können Gruppen im Admin Center erstellen und verwalten. Sie dürfen kein delegierter Administrator sein (z. B. ein Berater als beauftragter Administrator).

Als Administrator haben Sie die folgenden Möglichkeiten:

- [Festlegen, wer Gruppen erstellen kann](manage-creation-of-groups.md)
- [Erstellen einer Benennungsrichtlinie für Gruppen in Ihrer Organisation](groups-naming-policy.md)
- [Auswählen, welche Domäne beim Erstellen einer Gruppe verwendet werden soll](choose-domain-to-create-groups.md)
- [Verwalten des Gastzugriffs auf Gruppen](manage-guest-access-in-groups.md)
- [Wiederherstellen einer gelöschten Gruppe](restore-deleted-group.md) (innerhalb von 30 Tagen nach dem Löschvorgang)

Wenn Sie den Lebenszyklus Ihrer Office 365-Gruppen lieber automatisierter verwalten möchten, können Sie Ablaufrichtlinien verwenden, um festzulegen, dass die Gültigkeit von Gruppen nach einem bestimmten Zeitraum abläuft. Die Besitzer der Gruppe erhalten-30 Tage, 15 Tage und 1 Tag vor Gruppenablauf Benachrichtigungen per E-Mail, sodass sie die Gruppe einfach verlängern können, falls diese noch benötigt wird. Siehe [Ablaufrichtlinien für Office 365-Gruppen](office-365-groups-expiration-policy.md).

Sie können Gruppen entweder über das Microsoft 365 Admin Center oder [mithilfe von PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell) durchführen.

Wenn Sie viele Benutzer haben, z. B. in einem großen Unternehmen oder Konzern, haben Sie möglicherweise viele Benutzer, die Gruppen für unterschiedliche Zwecke erstellen. Es wird dringend empfohlen, dass Sie die bewährten Methoden unter [Planen der Governance in Office 365-Gruppen durchlesen.](plan-for-groups-governance.md)

## <a name="group-limits"></a>Grenzwerte für Gruppen

Die folgenden Grenzwerte gelten für alle Office 365-Gruppen:

|Maximale Anzahl für|Wert|
|:---------|:----|
|Besitzer pro Gruppe|100|
|Gruppen, die ein Benutzer erstellen kann|250|
|Gruppen, die ein Administrator erstellen kann|Bis zu 500.000 (Mandanten-Standardgrenzwert)|
|Anzahl Mitglieder |Mehr als 1 000, obwohl nur 1 000 gleichzeitig auf die Gruppen-Chats zugreifen können. <br>Möglicherweise kommt es in großen Gruppen in Outlook zu Verzögerungen beim Zugreifen auf Kalender und Unterhaltungen.|
|Anzahl von Gruppen, in denen ein Benutzer Mitglied sein kann|1 000|
|Dateispeicher|1 TB plus 10 GB pro Abonnementbenutzer plus zusätzlich gekaufter Speicher. Sie können eine unbegrenzte Menge weiteren Speichers kaufen.|
|Größe des Gruppenpostfachs|50 GB|

Die Standardanzahl von Office 365-Gruppen, die eine Office 365-Organisation aufweisen kann, beträgt derzeit maximal 500.000, kann jedoch auf Anfrage erhöht werden. Weitere Informationen zu Grenzwerten für Office 365-Gruppen finden Sie unter [Office 365-Gruppen - Hilfe für Administratoren](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx).

Sie können Ihre Office 365-Gruppen effizienter verwalten, wenn Sie über aussagekräftige Informationen zur Gruppennutzung verfügen. Im Microsoft 365 Admin Center ist ein Berichterstellungstool verfügbar, dem Sie Angaben wie die Speichernutzung und die Anzahl Ihrer aktiven Gruppen und sogar entnehmen können, wie Ihre Benutzer die Gruppen verwenden. Weitere Informationen finden Sie unter [Office 365-Berichte im Admin Center](../activity-reports/office-365-groups.md).

## <a name="which-office-365-plans-include-groups"></a>Welche Office 365-Pläne enthalten Gruppen?

Alle Office 365-Abonnements, die über Exchange Server und SharePoint Online verfügen, unterstützen Gruppen. Dazu gehören die Business Essentials- und Business Premium-Pläne sowie die Pläne Enterprise E1, E3 und E5. Die Gruppe übernimmt die Lizenzierung der Person, die die Gruppe erstellt (auch als "Organisator" der Gruppe bezeichnet). Solange der Organisator die richtige Lizenz für die Features hat, die für die Gruppe verwendet werden sollen, wird diese Lizenz auf die Gruppe übertragen.

> [!NOTE]
> Weitere Informationen über Office 365 Dienst Familien und-Pläne finden Sie unter [Office 365 Plan Options](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)

Wenn Sie über einen Plan verfügen, der nur Exchange enthält, können Sie trotzdem die Features "Freigegebener Posteingang" und "Freigegebener Kalender" von Gruppen in Outlook erhalten; die Dokumentbibliothek, Planner oder eine der anderen Funktionen stehen Ihnen jedoch nicht zur Verfügung.

Office 365-Gruppen funktionieren mit Azure Active Directory (AAD). Die Gruppenfeatures, die Sie erhalten, sind davon abhängig, welches Azure Active Directory-Abonnement Sie haben und welche Lizenz(en) dem Organisator der Gruppe zugewiesen wird/werden.

> [!IMPORTANT]
> Wenn Sie über ein Azure AD Premium-Abonnement verfügen, können Benutzer für alle Gruppenfeatures der Gruppe beitreten – unabhängig davon, ob ihnen eine AAD P1-Lizenz zugewiesen wurde. Die Lizenzierung wird nicht erzwungen.
> In regelmäßigen Abständen werden Verwendungsberichte generiert, die Ihnen mitteilen, welchen Benutzer eine Lizenz fehlt oder eine zugewiesene Lizenz benötigen, damit sie die Lizenzierungsanforderungen erfüllen. Nehmen wir beispielsweise an, dass ein Benutzer nicht über eine Lizenz verfügt und er einer Gruppe hinzugefügt wird, in der die Benennungsrichtlinie erzwungen wird. In dem Bericht wird für Sie gekennzeichnet, dass der Benutzer eine Lizenz benötigt.

## <a name="related-articles"></a>Verwandte Artikel

[Weitere Informationen zu Office 365-Gruppen](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Upgraden von Verteilerlisten zu Office 365-Gruppen](../manage/upgrade-distribution-lists.md)

[Verwalten von Office 365-Gruppen mit PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)

[SharePoint Online-Beschränkungen](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
