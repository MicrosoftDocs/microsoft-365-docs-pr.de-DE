---
title: 'Schritt 4: Einem anderen Mitarbeiter Zugriff auf OneDrive- und Outlook-Daten gewähren'
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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
description: Führen Sie die Schritte in diesem Artikel aus, um einem anderen Mitarbeiter Zugriff auf die OneDrive und Outlook Daten des ehemaligen Mitarbeiters zu gewähren.
ms.openlocfilehash: b5868ab1622fea68cc3dabb54a3d06208ccaa165
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394303"
---
# <a name="step-4---give-another-employee-access-to-onedrive-and-outlook-data"></a>Schritt 4: Einem anderen Mitarbeiter Zugriff auf OneDrive- und Outlook-Daten gewähren

Wenn ein Mitarbeiter Ihre Organisation verlässt, möchten Sie auf seine OneDrive und Outlook Daten zugreifen, diese sichern und auswählen, ob sie einem anderen Mitarbeiter übergeben werden sollen.
  
## <a name="access-a-former-users-onedrive-documents"></a>Zugreifen auf OneDrive Dokumente eines ehemaligen Benutzers

Wenn Sie eine Benutzerlizenz entfernen, aber das Konto nicht löschen, können Sie sich selbst Zugriff auf die Inhalte im OneDrive des Benutzers gewähren. Wenn Sie das Konto des Benutzers löschen, haben Sie standardmäßig 30 Tage Zeit, um auf die OneDrive Daten des ehemaligen Benutzers zuzugreifen. [Erfahren Sie, wie Sie die OneDrive Aufbewahrung für gelöschte Benutzer festlegen.](/onedrive/set-retention) Wenn Sie ein Benutzerkonto innerhalb dieses Zeitraums nicht [wiederherstellen,](/office365/admin/add-users/restore-user) wird dessen OneDrive Inhalt gelöscht.

Um die OneDrive Dateien eines ehemaligen Benutzers beizubehalten, gewähren Sie sich zuerst Zugriff auf seine OneDrive, und verschieben Sie dann die Dateien, die Sie behalten möchten.

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.  

2. Wählen Sie einen Benutzer aus.

3. Wählen Sie im rechten Bereich **OneDrive** aus. Wählen Sie unter **"Zugriff auf Dateien abrufen"** **den Link "Dateien erstellen"** aus.

4. Wählen Sie den Link aus, um den Dateispeicherort zu öffnen. Laden Sie die Dateien auf Ihren Computer herunter, oder wählen Sie **"Wechseln zu"** oder **"Kopieren"** aus, um sie in Ihre eigene OneDrive oder in eine freigegebene Bibliothek zu verschieben oder zu kopieren.

> [!NOTE]
> Sie können jeweils bis zu 500 MB Dateien und Ordner verschieben oder kopieren.<br/>
> Wenn Sie Dokumente mit Versionsverlauf verschieben oder kopieren, wird nur die neueste Version verschoben.  

Sie können auch einem anderen Benutzer Zugriff auf die OneDrive eines ehemaligen Mitarbeiters gewähren.

1. Melden Sie sich beim <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Admin Center</a> als globaler Administrator oder SharePoint-Administrator an.

    Wenn Sie eine Meldung erhalten, dass Sie nicht über die Berechtigung für den Zugriff auf das Admin Center verfügen, verfügen Sie in Ihrer Organisation nicht über Administratorberechtigungen.

2. Wählen Sie im linken Bereich **Admin Center** \> **SharePoint** aus. (Möglicherweise müssen Sie **Alle anzeigen** auswählen, um die Liste der Admin Center anzuzeigen.)

3. Wenn das klassische SharePoint Admin Center angezeigt wird, wählen Sie **es jetzt** oben auf der Seite öffnen aus, um das SharePoint Admin Center zu öffnen.

4. Wählen Sie im linken Bereich **weitere Features** aus.

5. Wählen Sie unter **Benutzerprofile** **Öffnen** aus.

6. Wählen Sie unter **"Personen"** die Option **"Benutzerprofile verwalten" aus.**

7. Geben Sie den Namen des ehemaligen Mitarbeiters ein, und wählen Sie **"Suchen"** aus.

8. Klicken Sie mit der rechten Maustaste auf den Benutzer, und wählen Sie dann **"Websitesammlungsbesitzer verwalten" aus.**

9. Fügen Sie den Benutzer zu **Websitesammlungsadministratoren hinzu,** und wählen Sie **OK** aus.

10. Der Benutzer kann nun über die ONEDRIVE-URL auf die OneDrive des ehemaligen Mitarbeiters zugreifen. 

### <a name="revoke-admin-access-to-a-users-onedrive"></a>Widerrufen des Administratorzugriffs auf die OneDrive eines Benutzers

Sie können sich selbst Zugriff auf die Inhalte in der OneDrive eines Benutzers gewähren, aber Sie können Den Zugriff entfernen, wenn Sie ihn nicht mehr benötigen.

1. Melden Sie sich beim <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Admin Center</a> als globaler Administrator oder SharePoint-Administrator an.

    Wenn Sie eine Meldung erhalten, dass Sie nicht über die Berechtigung für den Zugriff auf das Admin Center verfügen, verfügen Sie in Ihrer Organisation nicht über Administratorberechtigungen.

2. Wählen Sie im linken Bereich **Admin Center** \> **SharePoint** aus. (Möglicherweise müssen Sie **Alle anzeigen** auswählen, um die Liste der Admin Center anzuzeigen.)

3. Wenn das klassische SharePoint Admin Center angezeigt wird, wählen Sie **es jetzt** oben auf der Seite öffnen aus, um das SharePoint Admin Center zu öffnen.

4. Wählen Sie im linken Bereich **weitere Features** aus.

5. Wählen Sie unter **Benutzerprofile** **Öffnen** aus.

6. Wählen Sie unter **"Personen"** die Option **"Benutzerprofile verwalten" aus.**

7. Geben Sie den Namen des Benutzers ein, und wählen Sie **"Suchen"** aus.

8. Klicken Sie mit der rechten Maustaste auf den Benutzer, und wählen Sie dann **"Websitesammlungsbesitzer verwalten" aus.**

9. Entfernen Sie die Person, die keinen Zugriff mehr auf die Daten des Benutzers benötigt, und wählen Sie dann **OK** aus.

## <a name="access-the-outlook-data-of-a-former-user"></a>Zugreifen auf die Outlook Daten eines ehemaligen Benutzers

Zum Speichern der E-Mail-Nachrichten, Kalender, Aufgaben und Kontakte des ehemaligen Mitarbeiters exportieren Sie die Informationen in eine Outlook-Datendatei (PST).
  
1. [Fügen Sie die E-Mail-Adresse des ehemaligen Mitarbeiters](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) zu Ihrem Outlook hinzu (Wenn Sie [das Kennwort des Benutzers zurücksetzen,](reset-passwords.md)können Sie es auf etwas festlegen, das Nur Sie kennen.)

2. Wählen Sie in Outlook **Datei** aus.

    ![So sieht das Menüband in Outlook 2016 aus.](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. Wählen Sie **&amp; "Exportieren** \> **öffnen" Import/Export** aus.

    ![Befehl 'Importieren/Exportieren' in der Backstage-Ansicht](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. Wählen Sie **"In Datei exportieren"** und dann **"Weiter"** aus.

    ![Option zum Exportieren in eine Datei im Import/Export-Assistenten](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. Wählen Sie **Outlook Datendatei (PST)** und dann **weiter** aus.

6. Wählen Sie das Konto aus, das Sie exportieren möchten, indem Sie den Namen oder die E-Mail-Adresse auswählen, z. B. Postfach - Anna Weiler oder anne@contoso.com. Wenn Sie den gesamten Inhalt des Kontos exportieren möchten, einschließlich aller E-Mails, Kalender, Kontakte, Aufgaben und Notizen, stellen Sie sicher, dass das Kontrollkästchen **Unterordner einbeziehen** aktiviert ist.

    > [!NOTE]
    > Sie können immer ein Konto gleichzeitig exportieren. Wenn Sie mehrere Konten exportieren möchten, wiederholen Sie nach dem Export des einen Kontos diese Schritte.
  
    ![Dialogfeld 'Outlook-Datendatei exportieren' mit ausgewähltem Ordner der obersten Ebene und aktiviertem 'Unterordner einbeziehen'](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. Klicken Sie auf **Weiter**.

8. Wählen Sie **"Durchsuchen"** aus, um auszuwählen, wo die Outlook-Datendatei (PST) gespeichert werden soll. Geben Sie einen  *Dateinamen* ein, und klicken Sie dann auf **"OK",** um fortzufahren.

    > [!NOTE]
    > Wenn Sie zuvor bereits Daten exportiert haben, werden der Pfad und Dateiname des vorherigen Ordners angezeigt. Geben Sie einen  *anderen Dateinamen*  ein, bevor Sie **OK** auswählen.
  
9. Wenn Sie in eine vorhandene Outlook-Datendatei (PST) exportieren möchten, geben Sie unter **Optionen** an, was beim Export von Elementen geschehen soll, die in der Datei bereits vorhanden sind.

10. Wählen Sie **Fertig stellen** aus.

Outlook beginnt den Exportvorgang sofort, es sei denn, es wird eine neue Outlook-Datendatei (PST) erstellt oder eine kennwortgeschützte Datei verwendet.
  
- Wenn Sie eine Outlook-Datendatei (PST) erstellen, können Sie diese optional mit einem Kennwort schützen. Wenn das Dialogfeld **Datendatei erstellen Outlook** angezeigt wird, geben Sie das *Kennwort* in die Felder **Kennwort** und Kennwort **überprüfen** ein, und wählen Sie dann **OK** aus. Geben Sie im Dialogfeld **Outlook Datendateikennwort** das *Kennwort* ein, und wählen Sie dann **OK** aus.

- Wenn Sie in eine vorhandene Outlook-Datendatei (PST) exportieren, die kennwortgeschützte ist, geben Sie im Dialogfeld Outlook Kennwort für **Datendatei** das *Kennwort* ein, und wählen Sie dann **OK** aus.

Informationen zum Exportieren oder Sichern von [E-Mails, Kontakten und Kalendern in einer Outlook PST-Datei](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) in Outlook 2010.

  > [!NOTE]
  > Standardmäßig ist Ihre E-Mail für einen Zeitraum von 12 Monaten offline verfügbar. Wenn erforderlich, erfahren Sie, wie [Sie die offline verfügbaren Daten erhöhen.](/outlook/troubleshoot/mailboxes/only-subset-items-synchronized)

### <a name="give-another-user-access-to-a-former-users-email"></a>Einem anderen Benutzer Zugriff auf die E-Mails eines ehemaligen Benutzers gewähren

Um einem anderen Mitarbeiter Zugriff auf E-Mail-Nachrichten, Kalender, Aufgaben und Kontakte des ehemaligen Mitarbeiters zu gewähren, importieren Sie die Informationen in den Posteingang eines anderen Mitarbeiters Outlook.

> [!NOTE]
> Sie können [auch das Postfach des ehemaligen Benutzers in ein freigegebenes Postfach konvertieren](/office365/admin/email/convert-user-mailbox-to-shared-mailbox) oder die [E-Mails eines ehemaligen Mitarbeiters an einen anderen Mitarbeiter weiterleiten.](/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox)

1. Wechseln Sie in Outlook zu **Datei** \> **öffnen &amp; Export** \> **Import/Export**.

    Hiermit wird der Import/Export-Assistent geöffnet.

2. Wählen Sie **"Aus einem anderen Programm oder einer anderen Datei importieren"** und dann **"Weiter"** aus.

    ![Import/Export-Assistent](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. Wählen Sie **Outlook Datendatei (PST)** aus, und wählen Sie **"Weiter"** aus.

4. Navigieren Sie zu der PST-Datei, die Sie importieren möchten.

5. Wählen Sie unter **Optionen** aus, wie Duplikate behandelt werden sollen.

6. Klicken Sie auf **Weiter**.

7. Wenn der Outlook-Datendatei (PST) ein Kennwort zugewiesen wurde, geben Sie das Kennwort ein, und wählen Sie dann **OK** aus.

8. Legen Sie die Optionen für den Import von Elementen fest. Im Normalfall müssen die Standardeinstellungen nicht geändert werden.

9. Wählen Sie **Fertig stellen** aus.

> [!NOTE]
> Die Schritte bleiben für den Zugriff auf die OneDrive- und E-Mail-Daten eines vorhandenen Benutzers gleich.

> [!TIP]
> Wenn Sie nur einige Elemente aus einer Outlook-Datendatei (PST) importieren oder wiederherstellen möchten, können Sie die Outlook-Datendatei öffnen. Ziehen Sie dann im Navigationsbereich die Elemente aus Outlook Datendateiordnern in ihre vorhandenen Outlook Ordner. 

## <a name="related-content"></a>Verwandte Inhalte

[Hinzufügen und Entfernen von Administratoren für ein OneDrive Konto](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive) (Artikel)\
[Wiederherstellen eines gelöschten OneDrive](/onedrive/restore-deleted-onedrive) (Artikel)\
[OneDrive Aufbewahrung und Löschung](/onedrive/retention-and-deletion) (Artikel)
