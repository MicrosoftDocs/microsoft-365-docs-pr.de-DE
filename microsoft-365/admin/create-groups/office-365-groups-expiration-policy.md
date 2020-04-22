---
title: Ablaufrichtlinie für Gruppen
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
description: Erfahren Sie mehr über Ablaufrichtlinien für Microsoft 365-Gruppen.
ms.openlocfilehash: be61c66b310ada07876c5b3b005e6a7eb660092d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630055"
---
# <a name="microsoft-365-group-expiration-policy"></a>Microsoft 365-Gruppen Ablaufrichtlinie

Durch die zunehmende Nutzung von Microsoft 365-Gruppen benötigen Administratoren und Benutzer eine Möglichkeit, nicht verwendete Gruppen zu bereinigen. Mithilfe von Ablaufrichtlinien können inaktive Gruppen aus dem System entfernt und die Dinge sauberer gemacht werden.

Wenn eine Gruppe abläuft, werden auch alle zugehörigen Dienste (Postfach, Planer, SharePoint-Website, Team usw.) gelöscht.

Wenn eine Gruppe abläuft, wird Sie "vorläufig gelöscht", was bedeutet, dass Sie noch bis zu 30 Tage wiederhergestellt werden kann.

Administratoren können einen Ablaufzeitraum angeben, und alle inaktiven Gruppen, die das Ende dieses Zeitraums erreichen und nicht erneuert werden, werden gelöscht. Der Ablaufzeitraum beginnt beim Erstellen der Gruppe oder am Datum der letzten Verlängerung. Gruppenbesitzer erhalten vor dem Ablauf automatisch eine E-Mail, die es ihnen erlaubt, die Gruppe für ein weiteres Ablaufintervall zu erneuern. Microsoft Teams-Benutzer können persistente Benachrichtigungen in Microsoft Teams anzeigen.

Gruppen, die aktiv verwendet werden, werden automatisch erneuert. Durch eine der folgenden Aktionen wird automatisch eine Gruppe erneuert:
- SharePoint – anzeigen, bearbeiten, herunterladen, weiterleiten, freigeben oder Hochladen von Dateien.
- Outlook – beitreten einer Gruppe, lesen oder Schreiben von Gruppen Nachrichten der Gruppe und wie eine Nachricht (Outlook im Web).
- Teams – besuchen eines Teams-Kanals.

> [!IMPORTANT]
> Wenn Sie die Ablaufrichtlinie ändern, berechnet der Dienst das Ablaufdatum für jede Gruppe neu. Er beginnt immer ab dem Datum, an dem die Gruppe erstellt wurde, und wendet dann die neue Ablaufrichtlinie an.

Es ist wichtig zu wissen, dass der Ablauf standardmäßig deaktiviert ist. Administratoren müssen Sie für Ihre Organisation aktivieren, wenn Sie Sie verwenden möchten.

> [!NOTE]
> Bei der Konfiguration und Verwendung der Ablaufrichtlinie für Microsoft 365-Gruppen müssen Sie Azure AD Premium-Lizenzen für die Mitglieder aller Gruppen, auf die die Ablaufrichtlinie angewendet wird, besitzen, jedoch nicht unbedingt zuweisen. Weitere Informationen finden Sie unter [Erste Schritte mit Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium).

## <a name="who-can-configure-and-use-the-microsoft-365-groups-expiration-policy"></a>Wer kann die Ablaufrichtlinie für Microsoft 365-Gruppen konfigurieren und verwenden?

|Rolle|Was Sie tun können|
|---------|---------|
|Globaler Administrator (in Azure, der Unternehmensadministrator), Benutzer Administrator|Erstellen, lesen, aktualisieren oder löschen Sie die Microsoft 365 Groups-Ablaufrichtlinien Einstellungen.|
|Benutzer|Erneuern oder [Wiederherstellen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted) einer eigenen Microsoft 365-Gruppe|

## <a name="how-to-set-the-expiration-policy"></a>Vorgehensweise Festlegen der Ablaufrichtlinie

Wie oben erwähnt, ist ablaufy standardmäßig deaktiviert. Ein Administrator muss die Ablaufrichtlinie aktivieren und die Eigenschaften festlegen, damit diese wirksam werden. Um Sie zu aktivieren, gehen Sie zu **Azure Active Directory (AAD)-** > **Gruppen** > **Ablauf**. Hier können Sie die standardmäßige Gruppen Lebensdauer festlegen und angeben, wie weit im Voraus die ersten und zweiten Ablaufbenachrichtigungen zum Gruppenbesitzer wechseln sollen.

Die Gruppen Lebensdauer wird in Tagen angegeben und kann auf 180, 365 oder auf einen benutzerdefinierten Wert festgelegt werden, den Sie angeben. Der benutzerdefinierte Wert muss mindestens 30 Tage lang sein.

Wenn die Gruppe nicht über einen Besitzer verfügt, werden die Ablauf-e-Mails an einen bestimmten Administrator weitergegeben.

Sie können die Richtlinie für alle Gruppen oder nur für ausgewählte Gruppen festlegen oder vollständig deaktivieren, indem Sie **keine**auswählen. Beachten Sie, dass Sie derzeit keine unterschiedlichen Richtlinien für verschiedene Gruppen haben können.

![Screenshot von Gruppen Ablaufeinstellungen in Azure Active Directory](../../media/azure-groups-expiration-settings.png)

## <a name="how-expiry-works-with-the-retention-policy"></a>Funktionsweise des Ablaufs mit der Aufbewahrungsrichtlinie

Wenn Sie im Security and Compliance Center für Gruppen eine Setup Aufbewahrungsrichtlinie haben, funktioniert die Ablaufrichtlinie nahtlos mit der Aufbewahrungsrichtlinie. Wenn eine Gruppe abläuft, werden die Unterhaltungen der Gruppe in e-Mail-Postfach und Dateien auf der Gruppen Website im Aufbewahrungscontainer für die bestimmte Anzahl von Tagen aufbewahrt, die in der Aufbewahrungsrichtlinie definiert sind. Benutzer sehen die Gruppe oder deren Inhalt nach Ablauf allerdings nicht.

## <a name="how-and-when-a-group-owner-learns-if-their-groups-are-going-to-expire"></a>Wie und wann ein Gruppenbesitzer lernt, ob seine Gruppen ablaufen

Gruppenbesitzer werden nur per e-Mail benachrichtigt. Wenn die Gruppe über Planner, SharePoint oder eine andere App erstellt wurde, werden die Ablaufbenachrichtigungen immer per e-Mail gesendet. Wenn die Gruppe über Teams erstellt wurde, erhält der Gruppenbesitzer eine Benachrichtigung, die über den Abschnitt "Aktivität" erneuert wird. Es wird nicht empfohlen, den Ablauf für eine Gruppe zu aktivieren, wenn der Gruppenbesitzer keine gültige e-Mail-Adresse hat.

30 Tage vor Ablauf der Gruppe erhalten die Gruppenbesitzer (oder die e-Mail-Adressen, die Sie für Gruppen ohne Besitzer angegeben haben) eine e-Mail-Nachricht, mit der Sie die Gruppe problemlos erneuern können. Wenn Sie es nicht erneuern, erhalten Sie eine weitere Verlängerungs-e-Mail 15 Tage vor Ablauf. Wenn Sie es noch nicht erneuert haben, erhalten Sie eine weitere e-Mail-Benachrichtigung am Tag vor Ablauf.

Wenn aus irgendeinem Grund keine der Besitzer oder Administratoren die Gruppe erneuern, bevor Sie abläuft, kann der Administrator die Gruppe noch bis zu 30 Tage nach Ablauf wiederherstellen. Ausführliche Informationen finden Sie unter: [Wiederherstellen einer gelöschten Microsoft 365-Gruppe](https://support.office.com/article/restore-a-deleted-office-365-group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54).

## <a name="related-articles"></a>Verwandte Artikel

[Übersicht über Aufbewahrungsrichtlinien](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)

[Zuweisen eines neuen Besitzers zu einer verwaisten Gruppe](https://support.office.com/article/86bb3db6-8857-45d1-95c8-f6d540e45732)

[Konfigurieren des Ablaufs von Microsoft 365-Gruppen](https://docs.microsoft.com/azure/active-directory/active-directory-groups-lifecycle-azure-portal) '
