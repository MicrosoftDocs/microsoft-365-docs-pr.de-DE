---
title: 'Schritt 4: Geben Sie einem anderen Mitarbeiter Zugriff auf OneDrive und Outlook Daten'
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
description: Führen Sie die Schritte in diesem Artikel aus, um einem anderen Mitarbeiter Zugriff auf die Daten des ehemaligen Mitarbeiters OneDrive Outlook geben.
ms.openlocfilehash: cb5c27cbc7f1c184af8f0d1ad32b822660e93791
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2021
ms.locfileid: "52582692"
---
# <a name="step-4---give-another-employee-access-to-onedrive-and-outlook-data"></a>Schritt 4: Geben Sie einem anderen Mitarbeiter Zugriff auf OneDrive und Outlook Daten

Wenn ein Mitarbeiter Ihre Organisation verlässt, möchten Sie auf ihre OneDrive- und Outlook-Daten zugreifen, diese sichern und auswählen, ob sie einem anderen Mitarbeiter zur Auswahl stehen.
  
## <a name="access-a-former-users-onedrive-documents"></a>Zugreifen auf die Dokumente eines ehemaligen OneDrive

Wenn Sie die Lizenz eines Benutzers entfernen, das Konto jedoch nicht löschen, können Sie sich selbst Zugriff auf die Inhalte in der Website des Benutzers OneDrive. Wenn Sie das Konto des Benutzers löschen, haben Sie standardmäßig 30 Tage Zeit, um auf die Daten des OneDrive zugreifen. [Erfahren Sie, wie Sie OneDrive aufbewahrung für gelöschte Benutzer festlegen.](/onedrive/set-retention) Wenn Sie innerhalb [dieser](/office365/admin/add-users/restore-user) Zeit kein Benutzerkonto wiederherstellen, wird OneDrive gelöscht.

Um die Dateien eines ehemaligen Benutzers OneDrive zu erhalten, geben Sie sich zunächst Zugriff auf ihre OneDrive, und verschieben Sie dann die Dateien, die Sie beibehalten möchten.

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.  

2. Wählen Sie einen Benutzer aus.

3. Wählen Sie im rechten Bereich **die Option OneDrive** aus. Wählen **Sie unter Zugriff auf Dateien erhalten** die Option Link zu Dateien erstellen **aus.**

4. Wählen Sie den Link aus, um den Dateispeicherort zu öffnen. Laden Sie die Dateien auf Ihren  Computer herunter, oder wählen Sie **Verschieben** zu oder Kopieren aus, um sie in Ihre eigene OneDrive oder in eine freigegebene Bibliothek zu verschieben oder zu kopieren.

> [!NOTE]
> Sie können bis zu 500 MB an Dateien und Ordnern gleichzeitig verschieben oder kopieren.<br/>
> Wenn Sie Dokumente mit Versionsverlauf verschieben oder kopieren, wird nur die neueste Version verschoben.  

### <a name="revoke-admin-access-to-a-users-onedrive"></a>Widerrufen des Administratorzugriffs auf die OneDrive

Sie können sich Selbstzugriff auf die Inhalte in der Website eines Benutzers OneDrive, aber Sie können Ihren Zugriff entfernen, wenn Sie ihn nicht mehr benötigen.

1. Melden Sie sich beim <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Admin Center</a> als globaler Administrator oder SharePoint an.

    Wenn Sie eine Meldung erhalten, dass Sie nicht über die Berechtigung zum Zugriff auf das Admin Center verfügen, verfügen Sie nicht über Administratorberechtigungen in Ihrer Organisation.

2. Wählen Sie im linken Bereich **Admin Center SharePoint.** \>  (Möglicherweise müssen Sie **Alle anzeigen** auswählen, um die Liste der Admin Center anzuzeigen.)

3. Wenn das klassische SharePoint Admin Center  angezeigt wird, wählen Sie jetzt öffnen oben auf der Seite aus, um das SharePoint zu öffnen.

4. Wählen Sie im linken Bereich Weitere **Features aus.**

5. Wählen Sie unter **Benutzerprofile** **Öffnen** aus.

6. Wählen **Sie unter Personen** die Option **Benutzerprofile verwalten aus.**

7. Geben Sie den Namen des Benutzers ein, und wählen Sie **Suchen aus.**

8. Klicken Sie mit der rechten Maustaste auf den Benutzer, und wählen Sie **dann Websitesammlungsbesitzer verwalten aus.**

9. Entfernen Sie die Person, die keinen Zugriff mehr auf die Daten des Benutzers benötigt, und wählen Sie dann **OK aus.**

## <a name="access-the-outlook-data-of-a-former-user"></a>Zugreifen auf Outlook Daten eines ehemaligen Benutzers

Zum Speichern der E-Mail-Nachrichten, Kalender, Aufgaben und Kontakte des ehemaligen Mitarbeiters exportieren Sie die Informationen in eine Outlook-Datendatei (PST).
  
1. [Fügen Sie die](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) E-Mail des ehemaligen Mitarbeiters zu Outlook (Wenn Sie das Kennwort des Benutzers [zurücksetzen,](reset-passwords.md)können Sie sie auf etwas festlegen, das Ihnen bekannt ist.)

2. Wählen sie Outlook Datei **aus.**

    ![So sieht das Menüband in der Outlook 2016.](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. Wählen **Sie Export &amp; öffnen** \> **Import/Export** aus.

    ![Befehl 'Importieren/Exportieren' in der Backstage-Ansicht](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. Wählen **Sie Exportieren in eine Datei** aus, und wählen Sie dann Weiter **aus.**

    ![Option zum Exportieren in eine Datei im Import/Export-Assistenten](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. Wählen **Outlook Datendatei (PST)** aus, und wählen Sie dann **Weiter aus.**

6. Wählen Sie das Konto aus, das Sie exportieren möchten, indem Sie den Namen oder die E-Mail-Adresse auswählen, z. B. Mailbox - Anne Weiler oder anne@contoso.com. Wenn Sie den gesamten Inhalt des Kontos exportieren möchten, einschließlich aller E-Mails, Kalender, Kontakte, Aufgaben und Notizen, stellen Sie sicher, dass das Kontrollkästchen **Unterordner einbeziehen** aktiviert ist.

    > [!NOTE]
    > Sie können immer ein Konto gleichzeitig exportieren. Wenn Sie mehrere Konten exportieren möchten, wiederholen Sie nach dem Export des einen Kontos diese Schritte.
  
    ![Dialogfeld 'Outlook-Datendatei exportieren' mit ausgewähltem Ordner der obersten Ebene und aktiviertem 'Unterordner einbeziehen'](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. Wählen Sie **Weiter** aus.

8. Wählen **Sie Durchsuchen** aus, um auszuwählen, wo die Outlook (PST) gespeichert werden soll. Geben Sie  *einen Dateinamen ein,* und wählen Sie **dann OK aus, um** fortzufahren.

    > [!NOTE]
    > Wenn Sie zuvor bereits Daten exportiert haben, werden der Pfad und Dateiname des vorherigen Ordners angezeigt. Geben Sie einen *anderen Dateinamen ein, bevor* Sie OK **auswählen.**
  
9. Wenn Sie in eine vorhandene Outlook-Datendatei (PST) exportieren möchten, geben Sie unter **Optionen** an, was beim Export von Elementen geschehen soll, die in der Datei bereits vorhanden sind.

10. Klicken Sie auf **Fertigstellen**.

Outlook beginnt den Exportvorgang sofort, es sei denn, es wird eine neue Outlook-Datendatei (PST) erstellt oder eine kennwortgeschützte Datei verwendet.
  
- Wenn Sie eine Outlook-Datendatei (PST) erstellen, können Sie diese optional mit einem Kennwort schützen. Wenn das Dialogfeld **Outlook** Datendatei erstellen angezeigt wird, geben  Sie das Kennwort *in* die Felder **Kennwort** und Kennwort überprüfen ein, und wählen Sie dann **OK aus.** Geben Sie **Outlook** Kennwort für die Datendatei ein, und wählen Sie dann **OK aus.**

- Wenn Sie in eine vorhandene Outlook-Datendatei (PST) exportieren, die kennwortgeschützt ist, geben Sie im Dialogfeld Outlook-Datendateikennwort das Kennwort *ein,* und wählen Sie dann  **OK** aus.

Weitere Informationen finden Sie unter Exportieren oder Sichern von [E-Mails,](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) Kontakten und Kalendern in Outlook PST-Datei in Outlook 2010.

  > [!NOTE]
  > Standardmäßig ist Ihre E-Mail für einen Zeitraum von 12 Monaten offline verfügbar. Weitere Informationen finden Sie unter How to [increase the data available offline](/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).

### <a name="give-another-user-access-to-a-former-users-email"></a>Zugriff eines anderen Benutzers auf die E-Mail eines ehemaligen Benutzers

Um einem anderen Mitarbeiter Zugriff auf E-Mail-Nachrichten, Kalender, Aufgaben und Kontakte des ehemaligen Mitarbeiters zu geben, importieren Sie die Informationen in den Posteingang eines Outlook Mitarbeiters.

> [!NOTE]
> Sie können auch [das Postfach des](/office365/admin/email/convert-user-mailbox-to-shared-mailbox) ehemaligen Benutzers in ein freigegebenes Postfach konvertieren oder die E-Mail eines ehemaligen Mitarbeiters an einen anderen Mitarbeiter [weiterleiten.](/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox)

1. Wechseln Outlook zu Datei  \> **öffnen &amp; Export** \> **Import/Export**.

    Hiermit wird der Import/Export-Assistent geöffnet.

2. Wählen **Sie Importieren aus einem anderen Programm oder** einer anderen Datei aus, und wählen Sie dann Weiter **aus.**

    ![Import/Export-Assistent](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. Wählen **Outlook Datendatei (PST)** aus, und wählen Sie **Weiter aus.**

4. Navigieren Sie zu der PST-Datei, die Sie importieren möchten.

5. Wählen Sie unter **Optionen** aus, wie Duplikate behandelt werden sollen.

6. Wählen Sie **Weiter** aus.

7. Wenn der Outlook -Datendatei (PST) ein Kennwort zugewiesen wurde, geben Sie das Kennwort ein, und wählen Sie **dann OK aus.**

8. Legen Sie die Optionen für den Import von Elementen fest. Im Normalfall müssen die Standardeinstellungen nicht geändert werden.

9. Klicken Sie auf **Fertigstellen**.

> [!NOTE]
> Die Schritte bleiben für den Zugriff auf die Daten und E-Mail-Daten OneDrive vorhandenen Benutzers identisch.

> [!TIP]
> Wenn Sie nur wenige Elemente aus einer Outlook (PST) importieren oder wiederherstellen möchten, können Sie die datei Outlook öffnen. Ziehen Sie dann im Navigationsbereich die Elemente aus Outlook Datendateiordnern in Ihre vorhandenen Outlook Ordner. 

## <a name="related-content"></a>Verwandte Inhalte

[Hinzufügen und Entfernen von Administratoren in einem OneDrive](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive) Konto (Artikel)

[Wiederherstellen eines gelöschten OneDrive](/onedrive/restore-deleted-onedrive) (Artikel)
  
[OneDrive Aufbewahrung und Löschung](/onedrive/retention-and-deletion) (Artikel)
