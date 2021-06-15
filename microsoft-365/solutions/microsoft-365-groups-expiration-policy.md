---
title: Ablaufrichtlinie für Microsoft 365-Gruppe
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
- m365solution-collabgovernance
search.appverid:
- MET150
recommendations: false
description: Erfahren Sie mehr über ablaufrichtlinien für Microsoft 365 Gruppen.
ms.openlocfilehash: a5a57591e1659cf04b46f419bda3d3bca672729c
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925923"
---
# <a name="microsoft-365-group-expiration-policy"></a>Ablaufrichtlinie für Microsoft 365-Gruppe

Aufgrund der erhöhten Nutzung von Microsoft 365 Gruppen und Microsoft Teams benötigen Administratoren und Benutzer eine Möglichkeit, nicht verwendete Gruppen und Teams zu bereinigen. Eine Microsoft 365 Ablaufrichtlinie für Gruppen kann dazu beitragen, inaktive Gruppen aus dem System zu entfernen und die Dinge übersichtlicher zu gestalten.

Wenn eine Gruppe abläuft, werden alle zugehörigen Dienste (Postfach, Planner, SharePoint Website, Team usw.) ebenfalls gelöscht.

Wenn eine Gruppe abläuft, wird sie "vorläufig gelöscht", was bedeutet, dass sie bis zu 30 Tage lang wiederhergestellt werden kann.

Administratoren können einen Ablaufzeitraum angeben, und jede inaktive Gruppe, die das Ende dieses Zeitraums erreicht und nicht verlängert wird, wird gelöscht. (Dies umfasst archivierte Teams.) Der Ablaufzeitraum beginnt, wenn die Gruppe erstellt wird, oder an dem Datum, an dem sie zuletzt verlängert wurde. Gruppenbesitzer erhalten vor dem Ablauf automatisch eine E-Mail, die es ihnen erlaubt, die Gruppe für ein weiteres Ablaufintervall zu erneuern. Teams Benutzern werden in Teams beständige Benachrichtigungen angezeigt.

Gruppen, die aktiv verwendet werden, werden automatisch verlängert. Eine der folgenden Aktionen erneuert automatisch eine Gruppe:
- SharePoint – Anzeigen, Bearbeiten, Herunterladen, Verschieben, Freigeben oder Hochladen von Dateien. (Das Anzeigen einer SharePoint Seite zählt nicht als Aktion für die automatische Verlängerung.)
- Outlook : Gruppenbeitritt, Lesen oder Schreiben von Gruppennachrichten aus der Gruppe und wie eine Nachricht (Outlook im Web).
- Teams – Einen Teams-Kanal besuchen.

Beachten Sie, dass die einzige Yammer Aktivität, die eine automatische Gruppenverlängerung auslöst, das Hochladen eines Dokuments in SharePoint innerhalb der Community ist.

> [!IMPORTANT]
> Wenn Sie die Ablaufrichtlinie ändern, berechnet der Dienst das Ablaufdatum für jede Gruppe neu. Er beginnt immer ab dem Datum, an dem die Gruppe erstellt wurde, und wendet dann die neue Ablaufrichtlinie an.

Es ist wichtig zu wissen, dass der Ablauf standardmäßig deaktiviert ist. Administratoren müssen sie für ihre Organisation aktivieren, wenn sie sie verwenden möchten.

> [!NOTE]
> Wenn Sie die Ablaufrichtlinie für Microsoft 365 Gruppen konfigurieren und verwenden, müssen Sie azure AD Premium Lizenzen für die Mitglieder aller Gruppen, auf die die Ablaufrichtlinie angewendet wird, besitzen, aber nicht unbedingt zuweisen. Weitere Informationen finden Sie unter [Erste Schritte mit Azure Active Directory Premium](/azure/active-directory/active-directory-get-started-premium).

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a>Wer können die Ablaufrichtlinie für Microsoft 365 Gruppen konfigurieren und verwenden?

|Rolle|Möglichkeiten|
|---------|---------|
|Office 365 globaler Administrator (in Azure, Unternehmensadministrator), Benutzeradministrator|Erstellen, Lesen, Aktualisieren oder Löschen der Ablaufrichtlinieneinstellungen für Microsoft 365 Gruppen.|
|Benutzer|Erneuern oder [Wiederherstellen](/azure/active-directory/users-groups-roles/groups-restore-deleted) einer Microsoft 365 Gruppe, die sie besitzen|

## <a name="how-to-set-the-expiration-policy"></a>So legen Sie die Ablaufrichtlinie fest

Wie oben erwähnt, ist der Ablauf standardmäßig deaktiviert. Ein Administrator muss die Ablaufrichtlinie aktivieren und die Eigenschaften festlegen, damit sie wirksam wird. To enable it, go to **Azure Active Directory**  >  **Groups**  >  **Expiration**. Hier können Sie die Standardgruppenlebensdauer festlegen und angeben, wie weit im Voraus die erste und zweite Ablaufbenachrichtigung an den Gruppenbesitzer gehen soll.

Die Gruppenlebensdauer wird in Tagen angegeben und kann auf 180, 365 oder auf einen von Ihnen angegebenen benutzerdefinierten Wert festgelegt werden. Der benutzerdefinierte Wert muss mindestens 30 Tage betragen.

Wenn die Gruppe keinen Besitzer hat, werden die Ablauf-E-Mails an den angegebenen Administrator gesendet.

Sie können die Richtlinie für alle Ihre Gruppen festlegen, nur ausgewählte Gruppen (bis zu 500), oder sie vollständig deaktivieren, indem Sie **"Keine"** auswählen. Beachten Sie, dass sie derzeit keine unterschiedlichen Richtlinien für unterschiedliche Gruppen haben können.

![Screenshot der Ablaufeinstellungen für Gruppen in Azure Active Directory](../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a>Funktionsweise des Ablaufs mit der Aufbewahrungsrichtlinie

Wenn Sie eine Aufbewahrungsrichtlinie für Gruppen im Security and Compliance Center eingerichtet haben, funktioniert die Ablaufrichtlinie nahtlos mit der Aufbewahrungsrichtlinie. Wenn eine Gruppe abläuft, werden die Postfachunterhaltungen und Dateien der Gruppe auf der Gruppenwebsite im Aufbewahrungscontainer für die bestimmte Anzahl von Tagen aufbewahrt, die in der Aufbewahrungsrichtlinie definiert sind. Benutzern wird die Gruppe oder deren Inhalt nach dem Ablauf jedoch nicht angezeigt.

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a>Wie und wann ein Gruppenbesitzer erkennt, ob seine Gruppen ablaufen

Gruppenbesitzer werden nur per E-Mail benachrichtigt. Wenn die Gruppe über Planner, SharePoint oder eine andere App erstellt wurde, werden die Ablaufbenachrichtigungen immer per E-Mail gesendet. Wenn die Gruppe über Teams erstellt wurde, erhält der Gruppenbesitzer eine Benachrichtigung zur Verlängerung über den Aktivitätsbereich. Es wird nicht empfohlen, den Ablauf für eine Gruppe zu aktivieren, wenn Ihr Gruppenbesitzer keine gültige E-Mail-Adresse hat.

30 Tage vor Ablauf der Gruppe erhalten die Gruppenbesitzer (oder die E-Mail-Adressen, die Sie für Gruppen ohne Besitzer angegeben haben) eine E-Mail, mit der sie die Gruppe problemlos erneuern können. Wenn sie sie nicht verlängern, erhalten sie 15 Tage vor Ablauf eine weitere Verlängerungs-E-Mail. Wenn sie sie noch nicht verlängert haben, erhalten sie am Tag vor ablaufen eine weitere E-Mail-Benachrichtigung.

Wenn aus irgendeinem Grund keiner der Besitzer oder Administratoren die Gruppe verlängert, bevor sie abläuft, kann der Administrator die Gruppe bis zu 30 Tage nach Ablauf wiederherstellen. Weitere Informationen finden Sie unter: [Wiederherstellen einer gelöschten Microsoft 365 Gruppe.](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)

## <a name="archiving-group-contents"></a>Archivierung von Gruppeninhalten

Wenn Sie eine Gruppe haben, die Sie nicht mehr verwenden möchten, aber ihre Inhalte beibehalten möchten, finden Sie unter [Archivgruppen, Teams und Yammer](end-life-cycle-groups-teams-sites-yammer.md) Informationen zum Exportieren von Informationen aus den verschiedenen Gruppendiensten.

## <a name="related-topics"></a>Verwandte Themen

[Schritt-für-Schritt-Planung für die Zusammenarbeitsgovernance](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Erstellen eines Plans für die Zusammenarbeitsgovernance](collaboration-governance-first.md)

[Übersicht über Aufbewahrungsrichtlinien](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[Zuweisen eines neuen Besitzers zu einer verwaisten Gruppe](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[Konfigurieren Microsoft 365 Ablaufs von Gruppen](/azure/active-directory/active-directory-groups-lifecycle-azure-portal)
