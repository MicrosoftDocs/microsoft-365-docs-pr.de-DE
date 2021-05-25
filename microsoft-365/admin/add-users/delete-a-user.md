---
title: Löschen eines Benutzers aus Ihrer Organisation
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
- AdminSurgePortfolio
search.appverid:
- MET150
ms.assetid: d5155593-3bac-4d8d-9d8b-f4513a81479e
description: Erfahren Sie, wie Sie ein Benutzerkonto löschen und was Sie mit den E-Mails des Benutzers tun und OneDrive inhalten und ob die Produktlizenz erhalten werden soll.
ms.openlocfilehash: ff10d3289eae87f84685c22b81db03798ca9d7eb
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52634208"
---
# <a name="delete-a-user-from-your-organization"></a>Löschen eines Benutzers aus Ihrer Organisation
  
**Möchten Sie wissen, wie Sie *Ihr* eigenes Microsoft 365, das Sie bei der Arbeit oder in der Schule verwenden, löschen? Wenden Sie sich an den technischen Support ihrer Arbeit oder Universität, um diese Schritte für Sie zu tun.**

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Nur Personen, die [über Microsoft 365 Administrator-](about-admin-roles.md) oder Benutzerverwaltungsberechtigungen für das Unternehmen oder die Schule verfügen, können Benutzerkonten löschen.
- Sie haben 30 Tage Zeit, das Konto [wiederherzustellen](restore-user.md), bevor die Daten des Benutzers endgültig gelöscht werden.
- Wenn Sie die Daten des Benutzers OneDrive speichern möchten, verschieben Sie sie an einen anderen Speicherort. Sie können die Daten sogar bis zu 30 Tage nach dem Löschen des Kontos verschieben. Weitere Informationen finden Sie unter Zugriff auf und Sichern der Daten eines [ehemaligen Benutzers.](get-access-to-and-back-up-a-former-user-s-data.md) Sie müssen ihre Dateien nicht SharePoint verschieben. Sie haben weiterhin Zugriff auf diese.
- Wenn Sie die E-Mails des Benutzers behalten möchten, müssen Sie diese an einen anderen Speicherort verschieben, **BEVOR** Sie das Konto löschen. Wenn Sie das Konto bereits gelöscht haben und dies weniger als 30 Tage her ist, können Sie das Konto wiederherstellen und dann die E-Mail-Daten verschieben. Anschließend löschen Sie das Konto. Weitere Informationen finden Sie unter [Zugreifen auf die und Sichern der Daten eines ehemaligen Mitarbeiters](get-access-to-and-back-up-a-former-user-s-data.md).
- Wenn Sie über ein Enterprise wie Office 365 Enterprise E3 verfügen, können Sie die Postfachdaten eines gelöschten Benutzerkontos beibehalten, indem Sie es in ein inaktives Postfach *ändern.* Weitere Informationen dazu finden Sie unter [Verwalten inaktiver Postfächer in Exchange Online](../../compliance/inactive-mailboxes-in-office-365.md).

## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a>Globaler Administrator: Löschen eines Benutzers, Beenden der Zahlung für seine Lizenz und Auswählen, was mit seinen E-Mails und OneDrive-Inhalten geschehen soll.

Wenn Sie ein globaler Administrator sind und einen Benutzer löschen, können Sie auch einem anderen Benutzer Zugriff auf die E-Mails des gelöschten Benutzers gewähren und auswählen, was mit einem OneDrive-Inhalt geschehen soll.

### <a name="things-to-consider"></a>Zu berücksichtigende Aspekte

Bevor Sie beginnen, sollten Sie sich überlegen, was mit den E-Mails und OneDrive-Inhalten des Benutzers geschehen soll, und ob die Lizenz beibehalten oder die Zahlung für die Lizenz beendet werden soll.
  
|Element | Beschreibung |
|:-----|:-----|
|Produktlizenzen  <br/> |Sie können die Lizenz des Benutzers entfernen und aus ihren Abonnements löschen, damit keine weiteren Kosten dafür anfallen. Wenn Sie diese Option auswählen, wird die Lizenz automatisch aus ihren Abonnements entfernt.  <br/><br/> **Sie können die Lizenz nicht entfernen**, wenn Sie sie über einen Partner oder eine Volumenlizenzierung erworben haben. Wenn Sie einen Jahresplan bezahlen oder sich mitten in einem Abrechnungszyklus befindet, können Sie die Lizenz erst aus Ihrem Abonnement entfernen, wenn Ihre Zusage abgeschlossen ist.  <br/> |
|OneDrive-Inhalt  <br/> |Wenn der Benutzer seine Dateien auf OneDrive gespeichert hat, können Sie einem anderen Benutzer Zugriff auf diese Dateien gewähren.  <br/><br/> Sie müssen die Dateien, die Sie behalten möchten, innerhalb des für OneDrive-Dateien festgelegten Aufbewahrungszeitraums, der verschieben. **Die Standardeinstellung für den Aufbewahrungszeitraum ist 30 Tage.** Wenn Sie die Dateien nach dem Löschen des Benutzers nicht innerhalb des Aufbewahrungszeitraums verschieben, wird der OneDrive-Inhalt endgültig gelöscht. Wenn Sie den Aufbewahrungszeitraum für die OneDrive-Dateien gelöschter Konten erhöhen möchten, lesen Sie [Festlegen der OneDrive-Aufbewahrung für gelöschte Benutzer](/onedrive/set-retention).  <br/><br/> **Wichtig!** Wenn der gelöschte Benutzer seinen privaten PC zum Herunterladen von Dateien aus SharePoint und OneDrive verwendet hat, haben Sie keine Möglichkeit, die auf diesem Computer gespeicherten Dateien zu bereinigen. Er hat weiterhin Zugriff auf alle Dateien, die mit OneDrive synchronisiert wurden.           |
|E-Mail  <br/> | Wenn Sie einem anderen Benutzer den Zugriff auf die E-Mails des gelöschten Benutzers gewähren, wird das Postfach des gelöschten Benutzers in ein freigegebenes Postfach konvertiert. Der neue Postfachbesitzer kann dann auf das Postfach zugreifen und es auf neue E-Mails überwachen. Sie haben zudem folgende Möglichkeiten:  <br/>  <br/>Ändern des Anzeigenamens – Es wird empfohlen, den Anzeigenamen so zu ändern, dass das freigegebene Postfach in der Liste **Aktive Benutzer leicht identifiziert werden** kann.  <br/>  Aktivieren von automatischen Antworten – Wir haben bereits eine höfliche automatische Antwort für Sie geschrieben. Sie können unterschiedliche automatische Antworten an Personen innerhalb Ihrer Organisation und Personen von außerhalb Ihrer Organisation senden.  <br/> <br/> Bereinigen von Aliasnamen – Aliasnamen sind zusätzliche E-Mail-Adressen für Benutzer. In einigen Organisationen werden sie nicht verwendet. Wenn Sie also keine Aliasnamen verwenden, müssen Sie nichts weiter tun. Wenn der Benutzer über Aliase verfügt, wird empfohlen, sie zu entfernen, damit Sie diese E-Mail-Adressen wiederverwenden können. Andernfalls können Sie diese E-Mail-Adressen erst wiederverwenden, wenn der Aufbewahrungszeitraum für gelöschte Postfächer verstrichen ist. Standardmäßig kann ein gelöschtes Postfach 30 Tage lang wiederhergestellt werden. Weitere Informationen finden Sie unter [Exchange Online-Benutzerpostfächer löschen oder wiederherstellen](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox). <br/> |
|Active Directory Domain Services  <br/> |Wenn Ihr Unternehmen **Active Directory** verwendet und mit Azure AD synchronisiert, müssen Sie das Benutzerkonto aus Active Directory löschen. Dies ist nicht über Office 365 möglich. Entsprechende Anweisungen finden Sie unter [Löschen eines Benutzerkontos](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).  <br/> |

### <a name="get-started"></a>Erste Schritte

Da Sie in der geführten Oberfläche durch die Schritte zum Löschen eines Benutzers geleitet werden, beginnen Sie folgendermaßen:

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.

::: moniker-end

2. Wählen Sie den Benutzer aus, den Sie löschen möchten, und wählen Sie dann **Benutzer löschen aus.**

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a>Benutzerverwaltungsadministrator – Löschen von Benutzern aus Office 365

> [!IMPORTANT]
> Löschen Sie das Konto eines Benutzers nicht, wenn Sie es in ein freigegebenes Postfach konvertiert haben oder die E-Mail-Weiterleitung für das Konto eingerichtet haben. [](../email/convert-user-mailbox-to-shared-mailbox.md) Diese Funktionen benötigen weiterhin das Konto. Für ein freigegebenes Postfach ist keine Lizenz erforderlich. Wenn Sie das Konto in ein freigegebenes Postfach konvertiert haben, können Sie [die Zahlung für die Lizenz beenden.](#stop-paying-for-the-license) Wenn Sie die E-Mail-Weiterleitung für das Konto eingerichtet haben, können Sie die Lizenz nicht entfernen. Dadurch wird die E-Mail-Weiterleitung beendet und das Postfach deaktiviert.
  
::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.  

2. Wählen Sie die Namen der Benutzer aus, die Sie löschen möchten, wählen Sie die drei Punkte (weitere Aktionen) aus, und wählen Sie dann **Benutzer löschen aus.**

   Obwohl Sie das Konto des Benutzers gelöscht haben, **bezahlen Sie weiterhin für die Lizenz**.   Im nächsten Verfahren wird erläutert, was Sie tun müssen, um nicht mehr für die Lizenz zu bezahlen.  Sie können die Lizenz auch einem anderen Benutzer zuweisen. Er wird nicht automatisch einer Person zugewiesen.

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.

2. Wählen Sie die Namen der Benutzer, die Sie löschen möchten, und dann im Bereich **Massenaktionen** die Option **Benutzer löschen** aus.

   Obwohl Sie das Konto des Benutzers gelöscht haben, **bezahlen Sie weiterhin für die Lizenz**.   Im nächsten Verfahren wird erläutert, was Sie tun müssen, um nicht mehr für die Lizenz zu bezahlen.  Sie können die Lizenz auch einem anderen Benutzer zuweisen. Er wird nicht automatisch einer Person zugewiesen.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.

2. Wählen Sie die Namen der Benutzer, die Sie löschen möchten, und dann im Bereich **Massenaktionen** die Option **Benutzer löschen** aus.

   Obwohl Sie das Konto des Benutzers gelöscht haben, **bezahlen Sie weiterhin für die Lizenz**.   Im nächsten Verfahren wird erläutert, was Sie tun müssen, um nicht mehr für die Lizenz zu bezahlen.  Sie können die Lizenz auch einem anderen Benutzer zuweisen. Er wird nicht automatisch einer Person zugewiesen.

::: moniker-end

### <a name="stop-paying-for-the-license"></a>Beenden der Zahlung für die Lizenz

Das Verringern der Anzahl von Lizenzen ist ein separater Schritt, der nur vom globalen Administrator oder dem Abrechnungsadministrator ausgeführt werden kann.
  
::: moniker range="o365-worldwide"

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>. Wird diese Option nicht angezeigt, sind Sie kein globaler Administrator oder Abrechnungsadministrator und können diesen Schritt nicht ausführen.

2. Wählen Sie **auf der** Registerkarte Produkte das Abonnement aus, für das Sie Lizenzen entfernen möchten.

3. Wählen Sie auf der Seite mit den Abonnementdetails **Lizenzen entfernen** aus.

4. Geben Sie **im Bereich** Lizenzen entfernen  unter **Neue Menge** im Feld Lizenzen insgesamt die Gesamtzahl der Lizenzen ein, die Sie für dieses Abonnement benötigen. Wenn Sie beispielsweise über 100 Lizenzen verfügen und fünf davon entfernen möchten, geben Sie 95 ein.

5. Klicken Sie auf **Speichern**.

Wenn Sie später die Schritte zum Hinzufügen einer anderen Person zu Ihrem Unternehmen ausführen, werden Sie aufgefordert, gleichzeitig eine Lizenz mit nur einem Schritt zu erwerben!

::: moniker-end

::: moniker range="o365-germany"

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Abonnements</a>. Wird diese Option nicht angezeigt, sind Sie kein globaler Administrator oder Abrechnungsadministrator und können diesen Schritt nicht ausführen.

2. Wenn Sie über mehrere Abonnements verfügen, wählen Sie das gewünschte Abonnement und dann **Lizenzen hinzufügen/entfernen** aus, um die Lizenz zu löschen und so die Zahlung für die Lizenz zu beenden, bis Sie einen neuen Mitarbeiter einstellen.  

   Wenn Sie später die Schritte zum Hinzufügen einer anderen Person zu Ihrem Unternehmen ausführen, werden Sie aufgefordert, gleichzeitig eine Lizenz mit nur einem Schritt zu erwerben!

::: moniker-end

::: moniker range="o365-21vianet"

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abonnements</a>. Wird diese Option nicht angezeigt, sind Sie kein globaler Administrator oder Abrechnungsadministrator und können diesen Schritt nicht ausführen.

2. Wenn Sie über mehrere Abonnements verfügen, wählen Sie das gewünschte Abonnement und dann **Lizenzen hinzufügen/entfernen** aus, um die Lizenz zu löschen und so die Zahlung für die Lizenz zu beenden, bis Sie einen neuen Mitarbeiter einstellen.  

   Wenn Sie später die Schritte zum Hinzufügen einer anderen Person zu Ihrem Unternehmen ausführen, werden Sie aufgefordert, gleichzeitig eine Lizenz mit nur einem Schritt zu erwerben!

::: moniker-end

## <a name="delete-many-users-at-the-same-time"></a>Gleichzeitiges Löschen von vielen Benutzern

Informationen hierzu finden Sie in den Informationen zum PowerShell-Cmdlet [Remove-MsolUser](/powershell/module/msonline/remove-msoluser).

## <a name="fix-issues-with-deleting-a-user"></a>Beheben von Problemen mit dem Löschen eines Benutzers

Nachfolgend sind die beim Löschen eines Benutzers am häufigsten auftretenden Probleme aufgeführt:
  
- **Sie erhalten eine Fehlermeldung mit den Zeilen "Benutzer kann nicht gelöscht werden. Versuchen Sie es später erneut."** Überprüfen Sie, ob für das Konto die E-Mail-Weiterleitung eingerichtet ist oder ob es in ein freigegebenes Postfach konvertiert wurde. Beide Fällen verursachen diesen Fehler. Wenn für das Konto die E-Mail-Weiterleitung eingerichtet wurde oder es in ein freigegebenes Postfach konvertiert wurde, löschen Sie es nicht.

- **Sie verfügen nicht über die entsprechenden Berechtigungen zum Löschen eines Benutzer** s. Nur Personen, die Microsoft 365 [oder Benutzerverwaltungsadministratoren](about-admin-roles.md) sind, können Benutzer löschen. Normalerweise ist das der technische Support in Ihrer Schule/Uni oder in Ihrem Unternehmen.

- **Sie haben den Benutzer gelöscht, aber dessen Name wird weiterhin in Ihrem globalen Adressbuch angezeigt**. Dies ist der Fall, wenn ein Unternehmen Active Directory verwendet. Sie müssen das Benutzerkonto aus Active Directory löschen. Anweisungen finden Sie unter [Löschen eines Benutzerkontos.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))

**Möchten Sie die Microsoft 365 von Ihrem Computer löschen? Wechseln Sie zu [Abonnement kündigen](../../commerce/subscriptions/cancel-your-subscription.md).**

## <a name="related-content"></a>Verwandte Inhalte

[Wiederherstellen eines Benutzers](restore-user.md) (Artikel)\
[Dauerhaftes Löschen eines Postfachs](/exchange/permanently-delete-a-mailbox-exchange-2013-help) (Artikel)\
[Entfernen eines ehemaligen Mitarbeiters aus Office 365](remove-former-employee.md) (Artikel)\
[Hinzufügen eines neuen Mitarbeiters zu Office 365](add-new-employee.md) (Artikel)\
[Löschen eines Benutzerkontos](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)): Folgen Sie diesen Anweisungen, wenn Ihr Unternehmen **Active Directory** verwendet und mit Azure AD synchronisiert. Dies ist nicht über Office 365 möglich. (Artikel)