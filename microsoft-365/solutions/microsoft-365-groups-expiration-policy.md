---
title: Microsoft 365-Gruppenablaufrichtlinie
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
description: Erfahren Sie mehr über Ablaufrichtlinien für Microsoft 365-Gruppen.
ms.openlocfilehash: 8232e7df2a8390b905386773ed0656eb8239d5c5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920916"
---
# <a name="microsoft-365-group-expiration-policy"></a>Microsoft 365-Gruppenablaufrichtlinie

Mit der gestiegenen Nutzung von Microsoft 365-Gruppen und Microsoft Teams benötigen Administratoren und Benutzer eine Möglichkeit, nicht verwendete Gruppen und Teams zu bereinigen. Eine Ablaufrichtlinie für Microsoft 365-Gruppen kann dazu beitragen, inaktive Gruppen aus dem System zu entfernen und die Dinge sauberer zu machen.

Wenn eine Gruppe abläuft, werden alle zugehörigen Dienste (Postfach, Planner, SharePoint-Website, Team usw.) ebenfalls gelöscht.

Wenn eine Gruppe abläuft, wird sie "soft-deleted", was bedeutet, dass sie bis zu 30 Tage lang wiederhergestellt werden kann.

Administratoren können einen Ablaufzeitraum angeben, und alle inaktiven Gruppen, die das Ende dieses Zeitraums erreichen und nicht verlängert werden, werden gelöscht. (Dies umfasst archivierte Teams.) Der Ablaufzeitraum beginnt, wenn die Gruppe erstellt wird, oder an dem Datum, an dem sie zuletzt erneuert wurde. Gruppenbesitzer erhalten vor dem Ablauf automatisch eine E-Mail, die es ihnen erlaubt, die Gruppe für ein weiteres Ablaufintervall zu erneuern. Teams-Benutzern werden dauerhafte Benachrichtigungen in Teams angezeigt.

Gruppen, die aktiv verwendet werden, werden automatisch erneuert. Eine der folgenden Aktionen erneuert eine Gruppe automatisch:
- SharePoint – Anzeigen, Bearbeiten, Herunterladen, Verschieben, Freigeben oder Hochladen von Dateien. (Das Anzeigen einer SharePoint-Seite zählt nicht als Aktion für die automatische Verlängerung.)
- Outlook – Gruppe beitreten, Gruppennachricht aus der Gruppe lesen oder schreiben und wie eine Nachricht (Outlook im Web).
- Teams – Besuchen eines Teams-Kanals.

> [!IMPORTANT]
> Wenn Sie die Ablaufrichtlinie ändern, berechnet der Dienst das Ablaufdatum für jede Gruppe neu. Er beginnt immer ab dem Datum, an dem die Gruppe erstellt wurde, und wendet dann die neue Ablaufrichtlinie an.

Es ist wichtig zu wissen, dass der Ablauf standardmäßig deaktiviert ist. Administratoren müssen sie für ihre Organisation aktivieren, wenn sie sie verwenden möchten.

> [!NOTE]
> Zum Konfigurieren und Verwenden der Ablaufrichtlinie für Microsoft 365-Gruppen müssen Sie Azure AD Premium-Lizenzen für die Mitglieder aller Gruppen besitzen, auf die die Ablaufrichtlinie angewendet wird. Weitere Informationen finden Sie unter [Erste Schritte mit Azure Active Directory Premium](/azure/active-directory/active-directory-get-started-premium).

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a>Wer kann die Ablaufrichtlinie für Microsoft 365-Gruppen konfigurieren und verwenden?

|Rolle|Was sie tun können|
|---------|---------|
|Globaler Office 365-Administrator (in Azure der Unternehmensadministrator), Benutzeradministrator|Erstellen, Lesen, Aktualisieren oder Löschen der Ablaufrichtlinieneinstellungen für Microsoft 365-Gruppen.|
|Benutzer|Erneuern oder [Wiederherstellen](/azure/active-directory/users-groups-roles/groups-restore-deleted) einer Microsoft 365-Gruppe, die sie besitzen|

## <a name="how-to-set-the-expiration-policy"></a>Festlegen der Ablaufrichtlinie

Wie oben erwähnt, ist das Ablaufdatum standardmäßig deaktiviert. Ein Administrator muss die Ablaufrichtlinie aktivieren und die Eigenschaften festlegen, damit sie wirksam wird. Um dies zu aktivieren, wechseln Sie zu **Azure Active Directory**  >  **Groups**  >  **Expiration**. Hier können Sie die Standardgruppenlebensdauer festlegen und angeben, wie weit im Voraus die ersten und zweiten Ablaufbenachrichtigungen an den Gruppenbesitzer gehen sollen.

Die Gruppenlebensdauer wird in Tagen angegeben und kann auf 180, 365 oder auf einen von Ihnen angegebenen benutzerdefinierten Wert festgelegt werden. Der benutzerdefinierte Wert muss mindestens 30 Tage lang sein.

Wenn die Gruppe keinen Besitzer hat, gehen die Ablauf-E-Mails an den angegebenen Administrator.

Sie können die Richtlinie für alle Gruppen festlegen, nur für ausgewählte Gruppen, oder sie vollständig deaktivieren, indem Sie **Keine auswählen.** Beachten Sie, dass sie derzeit keine unterschiedlichen Richtlinien für unterschiedliche Gruppen haben können.

![Screenshot der Gruppenablaufeinstellungen in Azure Active Directory](../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a>Funktionsweise des Ablaufs mit der Aufbewahrungsrichtlinie

Wenn Sie eine Aufbewahrungsrichtlinie für Gruppen im Security and Compliance Center eingerichtet haben, funktioniert die Ablaufrichtlinie nahtlos mit der Aufbewahrungsrichtlinie. Wenn eine Gruppe abläuft, werden die Postfachunterhaltungen und Dateien der Gruppe auf dem Gruppenstandort im Aufbewahrungscontainer für die bestimmte Anzahl von Tagen aufbewahrt, die in der Aufbewahrungsrichtlinie definiert sind. Benutzer werden die Gruppe oder deren Inhalt nach ablaufen jedoch nicht mehr sehen.

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a>Wie und wann ein Gruppenbesitzer erfährt, ob seine Gruppen ablaufen

Gruppenbesitzer werden nur per E-Mail benachrichtigt. Wenn die Gruppe über Planner, SharePoint oder eine andere App erstellt wurde, werden die Ablaufbenachrichtigungen immer per E-Mail gesendet. Wenn die Gruppe über Teams erstellt wurde, erhält der Gruppenbesitzer eine Benachrichtigung zur Verlängerung über den Aktivitätsabschnitt. Es wird nicht empfohlen, den Ablauf für eine Gruppe zu aktivieren, wenn Ihr Gruppenbesitzer keine gültige E-Mail-Adresse hat.

30 Tage vor Ablauf der Gruppe erhalten die Gruppenbesitzer (oder die E-Mail-Adressen, die Sie für Gruppen ohne Besitzer angegeben haben) eine E-Mail, mit der sie die Gruppe problemlos verlängern können. Wenn sie sie nicht verlängern, erhalten sie 15 Tage vor Ablauf eine weitere Verlängerungs-E-Mail. Wenn sie es noch nicht verlängert haben, erhalten sie am Tag vor ablaufen eine weitere E-Mail-Benachrichtigung.

Wenn aus einem bestimmten Grund keiner der Besitzer oder Administratoren die Gruppe verlängert, bevor sie abläuft, kann der Administrator die Gruppe bis zu 30 Tage nach Ablauf wiederherstellen. Weitere Informationen finden Sie unter: [Wiederherstellen einer gelöschten Microsoft 365-Gruppe.](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)

## <a name="archiving-group-contents"></a>Archivierungsgruppeninhalte

Wenn Sie über eine Gruppe verfügen, die Sie nicht mehr verwenden möchten, aber deren Inhalte beibehalten möchten, finden Sie unter Archivieren von [Gruppen,](end-life-cycle-groups-teams-sites-yammer.md) Teams und Yammer Informationen zum Exportieren von Informationen aus den verschiedenen Gruppendiensten.

## <a name="related-topics"></a>Verwandte Themen

[Schritt-für-Schritt-Planung für die Zusammenarbeitsgovernance](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Erstellen eines Plans für die Zusammenarbeitsgovernance](collaboration-governance-first.md)

[Übersicht über Aufbewahrungsrichtlinien](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[Zuweisen eines neuen Besitzers zu einer verwaisten Gruppe](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[Konfigurieren des Ablaufs von Microsoft 365-Gruppen](/azure/active-directory/active-directory-groups-lifecycle-azure-portal)