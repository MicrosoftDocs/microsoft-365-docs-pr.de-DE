---
title: Übersicht über Office 365 Gruppen für Administratoren
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
search.appverid:
- BCS160
- MET150
- MOE150
description: Weitere Informationen zu Office 365-Gruppen.
ms.openlocfilehash: c45c78a26d421c5c16e6ca0769e8adc7ba6e79a8
ms.sourcegitcommit: 0da80ba7b504841c502ab06fea659a985c06fe8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2020
ms.locfileid: "43547544"
---
# <a name="overview-of-office-365-groups-for-administrators"></a>Übersicht über Office 365 Gruppen für Administratoren

Office 365 Gruppen ist der grundlegende Mitgliedschaftsdienst, der die gesamte Teamarbeit in Microsoft 365 steuert. Mit Office 365 Gruppen können Sie einer Gruppe von Personen Zugriff auf eine Sammlung von Ressourcen für die Zusammenarbeit geben, die diese Personen freigeben möchten. Diese Ressourcen enthalten:

- Einen freigegebenen Outlook-Posteingang
- Einen freigegebenen Kalender
- Eine SharePoint-Dokumentbibliothek
- Einen Planner
- Ein OneNote-Notizbuch
- Power BI
- Yammer (wenn die Gruppe in Yammer erstellt wurde)
- Ein Team (wenn die Gruppe in Teams erstellt wurde)
- Roadmap (wenn Sie Project für das Internet haben)

Mit einer Office 365 Gruppe müssen Sie keine Berechtigungen für jede dieser Ressourcen manuell zuweisen, da die Benutzer, die der Gruppe hinzugefügt werden, automatisch die erforderlichen Berechtigungen für die von der Gruppe bereitgestellten Tools erhalten.

Jeder Office 365-Benutzer kann eine Gruppe erstellen, es sei denn, Sie [beschränken die Gruppenerstellung auf bestimmte Personen](manage-creation-of-groups.md). Beachten Sie: Wenn Sie die Gruppenerstellung einschränken, können Benutzer, die keine Gruppen erstellen können, auch keine SharePoint-Websites, -Planner oder -Teams erstellen. Diese Dienste erfordern, dass die Personen, die Sie erstellen, eine Gruppe erstellen können. Benutzer können weiterhin an Gruppenaktivitäten teilnehmen, beispielsweise Erstellen von Aufgaben im Planer oder Verwenden von Microsoft Teams Chat, vorausgesetzt, Sie sind Mitglied der Gruppe.

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

Wenn Sie eine automatisiertere Möglichkeit zum Verwalten des Lebenszyklus Ihrer Office 365 Gruppen bevorzugen, können Sie Ablaufrichtlinien zum Ablaufen von Gruppen in einem bestimmten Zeitintervall verwenden. Die Besitzer der Gruppe erhalten-30 Tage, 15 Tage und 1 Tag vor Gruppenablauf Benachrichtigungen per E-Mail, sodass sie die Gruppe einfach verlängern können, falls diese noch benötigt wird. Siehe [Ablaufrichtlinien für Office 365-Gruppen](office-365-groups-expiration-policy.md).

Sie können Gruppen entweder über das Microsoft 365 Admin Center oder [mithilfe von PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell) durchführen.

Wenn Sie viele Benutzer haben, z. B. in einem großen Unternehmen oder Konzern, haben Sie möglicherweise viele Benutzer, die Gruppen für unterschiedliche Zwecke erstellen. Es wird dringend empfohlen, dass Sie die bewährten Methoden unter [Planen der Governance in Office 365-Gruppen durchlesen.](plan-for-groups-governance.md)

## <a name="group-limits"></a>Grenzwerte für Gruppen

Die folgenden Grenzwertegelten für Office 365 Gruppen:

|Maximale Anzahl für|Wert|
|:---------|:----|
|Besitzer pro Gruppe|100|
|Gruppen, die ein Benutzer erstellen kann|250|
|Gruppen, die ein Administrator erstellen kann|Bis zu 500.000 (Mandanten-Standardgrenzwert)|
|Anzahl Mitglieder |Mehr als 1 000, obwohl nur 1 000 gleichzeitig auf die Gruppen-Chats zugreifen können. <br>Möglicherweise kommt es in großen Gruppen in Outlook zu Verzögerungen beim Zugreifen auf Kalender und Unterhaltungen.|
|Anzahl von Gruppen, in denen ein Benutzer Mitglied sein kann|1 000|
|Dateispeicher|1 TB plus 10 GB pro Abonnementbenutzer plus zusätzlich gekaufter Speicher. Sie können eine unbegrenzte Menge weiteren Speichers kaufen.|
|Größe des Gruppenpostfachs|50 GB|

Die standardmäßige maximale Anzahl von Office 365 Gruppen, die eine Office 365 Organisation haben kann, ist 500.000, kann aber auf Anforderung erhöht werden. Weitere Informationen zu Grenzwerten für Office 365 Gruppen finden Sie unter [Office 365 groups-admin Help](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx).

Das Verwalten Ihrer Office 365 Gruppen ist effektiver, wenn Sie über Aktions fähige Informationen zur Verwendung von Gruppen verfügen. Das Microsoft 365 Admin Center verfügt über ein Berichtstool, mit dem Sie Dinge wie die Speichernutzung, die Anzahl der aktiven Gruppen und sogar die Verwendung der Gruppen durch Ihre Benutzer anzeigen können. Weitere Informationen finden Sie unter [Office 365-Berichte im Admin Center](../activity-reports/office-365-groups.md).

## <a name="which-office-365-plans-include-groups"></a>Welche Office 365 Pläne umfassen Gruppen?

Alle Office 365-Abonnements, die über Exchange Server und SharePoint Online verfügen, unterstützen Gruppen. Dazu gehören die Business Essentials- und Business Premium-Pläne sowie die Pläne Enterprise E1, E3 und E5. Die Gruppe übernimmt die Lizenzierung der Person, die die Gruppe erstellt (auch als "Organisator" der Gruppe bezeichnet). Solange der Organisator über die richtige Lizenz für alle Funktionen verfügt, die die Gruppe aufweisen soll, wird die Lizenz an die Gruppe übermittelt.

> [!NOTE]
> Weitere Informationen über Office 365 Dienst Familien und-Pläne finden Sie unter [Office 365 Plan Options](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)

Wenn Sie über einen Exchange-only-Plan verfügen, können Sie weiterhin den freigegebenen Posteingang und die freigegebenen Kalenderfunktionen von Gruppen in Outlook abrufen, aber Sie erhalten nicht die Dokumentbibliothek, den Planer oder andere Funktionen.

Office 365 Gruppen arbeiten mit Azure Active Directory (AAD). Die von Ihnen erhaltenen Gruppenfeatures hängen davon ab, welches Azure Active Directory-Abonnement Sie besitzen und welche Lizenzen dem Organisator der Gruppe zugewiesen sind.

> [!IMPORTANT]
> Wenn Sie über ein Azure AD Premium-Abonnement verfügen, können Benutzer für alle Gruppenfeatures der Gruppe beitreten, unabhängig davon, ob Ihnen eine Aad P1-Lizenz zugewiesen wurde oder nicht. Die Lizenzierung wird nicht erzwungen.
> In regelmäßigen Abständen werden Verwendungsberichte generiert, die Ihnen mitteilen, welchen Benutzer eine Lizenz fehlt oder eine zugewiesene Lizenz benötigen, damit sie die Lizenzierungsanforderungen erfüllen. Nehmen wir beispielsweise an, dass ein Benutzer nicht über eine Lizenz verfügt und er einer Gruppe hinzugefügt wird, in der die Benennungsrichtlinie erzwungen wird. In dem Bericht wird für Sie gekennzeichnet, dass der Benutzer eine Lizenz benötigt.

## <a name="related-articles"></a>Verwandte Artikel

[Weitere Informationen zu Office 365-Gruppen](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Upgraden von Verteilerlisten zu Office 365-Gruppen](../manage/upgrade-distribution-lists.md)

[Verwalten von Office 365-Gruppen mit PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)

[SharePoint Online-Beschränkungen](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
