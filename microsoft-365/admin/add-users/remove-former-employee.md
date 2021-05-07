---
title: Entfernen eines ehemaligen Mitarbeiters – Übersicht
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Führen Sie die Schritte in dieser Lösung aus, um einen ehemaligen Mitarbeiter aus Microsoft 365 zu entfernen und die Daten Ihrer Organisation zu schützen.
ms.openlocfilehash: 4b4cf59fdce81b3098ee333095daa8e1af1cd5c5
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241736"
---
# <a name="overview-remove-a-former-employee-and-secure-data"></a>Übersicht: Entfernen eines ehemaligen Mitarbeiters und Sichern von Daten

Eine Häufig gestellte Frage lautet: "Was soll ich tun, um Daten zu schützen und den Zugriff zu schützen, wenn ein Mitarbeiter meine Organisation verlässt?" In dieser Artikelreihe wird erläutert, wie Sie den Zugriff auf Microsoft 365 blockieren, welche Schritte Sie zum Sichern Ihrer Daten ausführen sollten, und wie anderen Mitarbeitern der Zugriff auf die Daten ermöglicht wird.

Sehen Sie sich ein kurzes Video zum Entfernen eines Mitarbeiters an. <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und diejenigen, für die Microsoft 365 neu ist](../../business-video/index.yml) an.

So verhindern Sie, dass sich ein Mitarbeiter anmelden kann:

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.
2. Wählen Sie das Feld neben dem Namen des Benutzers aus, und wählen Sie dann **Kennwort zurücksetzen aus.**
3. Geben Sie ein neues Kennwort ein, und wählen Sie dann **Zurücksetzen aus.** (Senden Sie es nicht an sie.)
4. Wählen Sie den Namen des Benutzers aus, um  zum Eigenschaftenbereich zu wechseln, und wählen Sie auf der Registerkarte Konto die Option **Abmelden initiieren aus.**

> [!NOTE]
> Sie müssen ein globaler Administrator sein, um das Abmelden zu initiieren.

Innerhalb einer Stunde – oder nachdem sie die aktuelle Seite Microsoft 365 verlassen, auf der sie sich befinden – werden sie aufgefordert, sich erneut zu melden. Ein Zugriffstoken ist für eine Stunde gut, daher hängt die Zeitachse davon ab, wie viel Zeit auf diesem Token noch bleibt und ob sie aus ihrer aktuellen Webseite navigieren.

> [!IMPORTANT]
> Obwohl wir die Schritte in dieser Lösung nummeriert haben und Sie die Lösung nicht in der genauen Reihenfolge abschließen müssen, wird empfohlen, die Schritte auf diese Weise zu tun.

## <a name="before-you-begin"></a>Vorabinformationen

Sie müssen ein globaler Administrator sein, um die Schritte in dieser Lösung ausführen zu können.

|||
|:-----|:-----|
|**Schritt** <br/> |**Zweck** <br/> |
|[Schritt 1 – Verhindern, dass sich ein ehemaliger Mitarbeiter an einem Dienst anmelden und den Zugriff auf Microsoft 365 blockieren](remove-former-employee-step-1.md) <br/> |Dadurch wird verhindert, dass sich Ihr ehemaliger Mitarbeiter bei Microsoft 365 anmelden und verhindert, dass die Person auf Microsoft 365 zugreifen kann. <br/> |
|[Schritt 2 : Speichern des Inhalts des Postfachs eines ehemaligen Mitarbeiters](remove-former-employee-step-2.md) <br/> |Dies ist nützlich für die Person, die die Arbeit des Mitarbeiters übernimmt, oder wenn ein Rechtsstreit besteht. <br/> |
|[Schritt 3 : Weiterleiten der E-Mail eines ehemaligen Mitarbeiters an einen anderen Mitarbeiter oder Konvertieren in ein freigegebenes Postfach](remove-former-employee-step-3.md) <br/> |Damit sorgen Sie dafür, dass die E-Mail-Adresse des ehemaligen Mitarbeiters aktiv bleibt. Wenn Kunden oder Partner E-Mails weiterhin an diese Adresse senden, werden sie hierdurch an die Person geleitet, die dessen Arbeit übernimmt. <br/> |
|[Schritt 4: Geben Sie einem anderen Mitarbeiter Zugriff auf OneDrive und Outlook Daten](remove-former-employee-step-6.md) <br/> |Wenn Sie nur die Lizenz eines Benutzers entfernen, aber das Konto nicht löschen, können Sie auch nach mehr als 30 Tagen auf den OneDrive-Inhalt des Benutzers zugreifen. <br/><br/> Bevor Sie das Konto löschen, sollten Sie einem anderen Benutzer OneDrive und Outlook zugriffen. Nachdem Sie das Konto eines Mitarbeiters gelöscht haben, werden die Inhalte in OneDrive und Outlook **30 Tage aufbewahrt.** Während dieser 30 Tage können Sie jedoch das Konto des Benutzers wiederherstellen und Zugriff auf deren Inhalte erhalten. Wenn Sie das Konto des Benutzers wiederherstellen, bleiben OneDrive und Outlook auch nach 30 Tagen für Sie zugänglich. <br/> |
|[Schritt 5: Löschen und Blockieren des mobilen Geräts eines ehemaligen Mitarbeiters](remove-former-employee-step-4.md) <br/> |Entfernt die Geschäftsdaten vom Smartphone oder Tablet.  <br/> |
|[Schritt 6 – Entfernen und Löschen Microsoft 365 Lizenz eines ehemaligen Mitarbeiters](remove-former-employee-step-7.md) <br/> |Wenn Sie eine Lizenz entfernen, können Sie sie einem anderen Benutzer zuweisen. Sie können die Lizenz auch löschen, damit Sie erst dann wieder dafür bezahlen, wenn Sie eine andere Person einstellen.  <br/><br/> Wenn Sie eine Lizenz entfernen oder löschen, werden die alten E-Mails, Kontakte und Kalender des Benutzers für **30 Tage** gespeichert und anschließend dauerhaft gelöscht. Wenn Sie eine Lizenz entfernen oder löschen, aber das Konto nicht löschen, können Sie auch nach mehr als 30 Tagen auf den OneDrive-Inhalt des Benutzers zugreifen.  <br/> |
|[Schritt 7 : Löschen des Benutzerkontos eines ehemaligen Mitarbeiters](remove-former-employee-step-7.md) <br/> |Dadurch wird das Konto aus Ihrem Admin Center entfernt. So behalten Sie die Übersicht. <br/> |

## <a name="related-articles"></a>Verwandte Artikel

[Wiederherstellen eines Benutzers](restore-user.md)
