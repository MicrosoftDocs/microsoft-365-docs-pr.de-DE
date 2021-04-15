---
title: Zugreifen auf die und Sichern der Daten eines ehemaligen Mitarbeiters
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a6f7f9ad-e3f5-43de-ade5-e5a0d7531604
description: Erfahren Sie, wie Sie die Dateien und E-Mails eines Mitarbeiters beibehalten, wenn die Person Ihre Organisation verlässt.
ms.openlocfilehash: 17911e4a4551bba07d2c2ad034941bba737dcc1d
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51755606"
---
# <a name="get-access-to-and-back-up-a-former-users-data"></a>Zugreifen auf die und Sichern der Daten eines ehemaligen Benutzers


Wenn ein Mitarbeiter Ihre Organisation verlässt, möchten Sie wahrscheinlich auf ihre Daten (Dokumente und E-Mails) zugreifen und diese entweder überprüfen, sichern oder an einen neuen Mitarbeiter senden.
  
    
## <a name="access-a-former-users-onedrive-documents"></a>Zugreifen auf die #A0 eines ehemaligen Benutzers

Wenn Sie die Lizenz eines Benutzers entfernen, das Konto jedoch nicht löschen, können Sie sich selbst Zugriff auf die Inhalte im OneDrive des Benutzers geben. Wenn Sie das Konto des Benutzers löschen, haben Sie standardmäßig 30 Tage Zeit, um auf die #A0 des ehemaligen Benutzers zu zugreifen. [Erfahren Sie, wie Sie die #A0 für gelöschte Benutzer festlegen.](/onedrive/set-retention) Wenn Sie innerhalb dieser Zeit [kein Benutzerkonto](/office365/admin/add-users/restore-user) wiederherstellen, werden deren #A0 gelöscht. 

Um die #A0 eines ehemaligen Benutzers zu erhalten, geben Sie sich zunächst Zugriff auf ihr OneDrive, und verschieben Sie dann die Dateien, die Sie behalten möchten. 

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.

::: moniker-end

2. Wählen Sie einen Benutzer aus.

3. Wählen Sie im rechten Bereich **OneDrive aus.** Wählen **Sie unter Zugriff auf Dateien erhalten** die Option Link zu Dateien erstellen **aus.**

4. Wählen Sie den Link aus, um den Dateispeicherort zu öffnen. Laden Sie die Dateien auf Ihren  Computer herunter, oder wählen Sie **Verschieben oder** Kopieren aus, um sie auf Ihr eigenes OneDrive oder in eine freigegebene Bibliothek zu verschieben oder zu kopieren. 

> [!NOTE]
> Sie können bis zu 500 MB an Dateien und Ordnern gleichzeitig verschieben oder kopieren.<br/>
> Wenn Sie Dokumente mit Versionsverlauf verschieben oder kopieren, wird nur die neueste Version verschoben.  

## <a name="revoke-admin-access-to-a-users-onedrive"></a>Widerrufen des Administratorzugriffs auf oneDrive eines Benutzers

Als globaler Administrator können Sie sich selbst Zugriff auf die Inhalte im OneDrive eines Benutzers geben, aber Sie können Ihren Zugriff entfernen, wenn Sie ihn nicht mehr benötigen. 

 ::: moniker range="o365-worldwide"

1. Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.

::: moniker-end 

2. Wählen Sie im linken Bereich **Admin Center** \> **SharePoint aus.** (Möglicherweise müssen Sie **Alle anzeigen** auswählen, um die Liste der Admin Center anzuzeigen.)

3. Wenn das klassische SharePoint Admin  Center angezeigt wird, wählen Sie jetzt öffnen oben auf der Seite aus, um das SharePoint Admin Center zu öffnen.

4. Wählen Sie im linken Bereich Weitere **Features aus.**

5. Wählen Sie unter **Benutzerprofile** **Öffnen** aus.

6. Wählen **Sie unter Personen** die Option **Benutzerprofile verwalten aus.**

7. Geben Sie den Namen des Benutzers ein, und wählen Sie **Suchen aus.**

8. Klicken Sie mit der rechten Maustaste auf den Benutzer, und wählen Sie **dann Websitesammlungsbesitzer verwalten aus.**

9. Entfernen Sie die Person, die keinen Zugriff mehr auf die Daten des Benutzers benötigt, und wählen Sie dann **OK aus.**

    
## <a name="access-the-outlook-data-of-a-former-user"></a>Zugreifen auf die Outlook-Daten eines ehemaligen Benutzers

Zum Speichern der E-Mail-Nachrichten, Kalender, Aufgaben und Kontakte des ehemaligen Mitarbeiters exportieren Sie die Informationen in eine Outlook-Datendatei (PST).
  
1. [Fügen Sie die E-Mail](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) des ehemaligen Mitarbeiters zu Ihrem Outlook hinzu (Wenn Sie das Kennwort des Benutzers [zurücksetzen,](reset-passwords.md)können Sie sie auf etwas festlegen, das Ihnen bekannt ist.)
    
2. Wählen Sie in Outlook **Datei aus.**
    
    ![So sieht das Menüband in Outlook 2016 aus.](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. Wählen **Sie &amp; Import/Export** \> **öffnen aus.**
    
    ![Befehl 'Importieren/Exportieren' in der Backstage-Ansicht](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. Wählen **Sie Exportieren in eine Datei** aus, und wählen Sie dann Weiter **aus.**
    
    ![Option zum Exportieren in eine Datei im Import/Export-Assistenten](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. Wählen **Sie Outlook-Datendatei (PST)** aus, und wählen Sie dann **Weiter aus.**
    
6. Wählen Sie das Konto aus, das Sie exportieren möchten, indem Sie den Namen oder die E-Mail-Adresse auswählen, z. B. Mailbox - Anne Weiler oder anne@contoso.com. Wenn Sie den gesamten Inhalt des Kontos exportieren möchten, einschließlich aller E-Mails, Kalender, Kontakte, Aufgaben und Notizen, stellen Sie sicher, dass das Kontrollkästchen **Unterordner einbeziehen** aktiviert ist. 
    
    > [!NOTE]
    > Sie können immer ein Konto gleichzeitig exportieren. Wenn Sie mehrere Konten exportieren möchten, wiederholen Sie nach dem Export des einen Kontos diese Schritte. 
  
    ![Dialogfeld 'Outlook-Datendatei exportieren' mit ausgewähltem Ordner der obersten Ebene und aktiviertem 'Unterordner einbeziehen'](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. Klicken Sie auf **Weiter**.
    
8. Wählen **Sie Durchsuchen** aus, um auszuwählen, wo die Outlook-Datendatei (PST) gespeichert werden soll. Geben Sie  *einen Dateinamen ein,* und wählen Sie **dann OK aus, um** fortzufahren. 
    
    > [!NOTE]
    > Wenn Sie zuvor bereits Daten exportiert haben, werden der Pfad und Dateiname des vorherigen Ordners angezeigt. Geben Sie einen *anderen Dateinamen ein, bevor* Sie OK **auswählen.** 
  
9. Wenn Sie in eine vorhandene Outlook-Datendatei (PST) exportieren möchten, geben Sie unter **Optionen** an, was beim Export von Elementen geschehen soll, die in der Datei bereits vorhanden sind.
    
10. Wählen Sie **Fertig stellen** aus.
    
Outlook beginnt den Exportvorgang sofort, es sei denn, es wird eine neue Outlook-Datendatei (PST) erstellt oder eine kennwortgeschützte Datei verwendet.
  
   - Wenn Sie eine Outlook-Datendatei (PST) erstellen, können Sie diese optional mit einem Kennwort schützen. Wenn das Dialogfeld **Outlook-Datendatei** erstellen angezeigt wird,  geben Sie *das* Kennwort in die Felder **Kennwort** und Kennwort überprüfen ein, und wählen Sie dann **OK aus.** Geben Sie **im Dialogfeld Outlook Data File Password** das Kennwort ein, und wählen Sie dann OK **aus.** 
    
  - Wenn Sie in eine vorhandene Outlook-Datendatei (PST) exportieren, die kennwortgeschützt ist, geben Sie im Dialogfeld **Outlook-Datendateikennwort** das Kennwort ein, und wählen Sie dann OK **aus.**
    
Informationen zum [Exportieren oder Sichern von E-Mails, Kontakten](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) und Kalendern in eine Outlook -PST-Datei in Outlook 2010. 
  
  
  > [!NOTE]
  > Standardmäßig ist Ihre E-Mail für einen Zeitraum von 12 Monaten offline verfügbar. Weitere Informationen finden Sie unter How to [increase the data available offline](/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).
 
## <a name="give-another-user-access-to-a-former-users-email"></a>Zugriff eines anderen Benutzers auf die E-Mail eines ehemaligen Benutzers 

Um einem anderen Mitarbeiter Zugriff auf E-Mail-Nachrichten, Kalender, Aufgaben und Kontakte des ehemaligen Mitarbeiters zu geben, importieren Sie die Informationen in den Outlook-Posteingang eines anderen Mitarbeiters.

> [!NOTE]
> Sie können auch [das Postfach des](/office365/admin/email/convert-user-mailbox-to-shared-mailbox) ehemaligen Benutzers in ein freigegebenes Postfach konvertieren oder die E-Mail eines ehemaligen Mitarbeiters an einen anderen Mitarbeiter [weiterleiten.](/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox)

  
1. Wechseln Sie in Outlook zu **Datei** \> **Öffnen Export &amp;** \> **Import/Export**.
    
    Hiermit wird der Import/Export-Assistent geöffnet.
    
2. Wählen **Sie Importieren aus einem anderen Programm oder** einer anderen Datei aus, und wählen Sie dann Weiter **aus.**
    
    ![Import/Export-Assistent](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. Wählen **Sie Outlook-Datendatei (PST)** aus, und wählen Sie **Weiter aus.**
    
4. Navigieren Sie zu der PST-Datei, die Sie importieren möchten.
    
5. Wählen Sie unter **Optionen** aus, wie Duplikate behandelt werden sollen.
    
6. Klicken Sie auf **Weiter**.
    
7. Wenn der Outlook-Datendatei (PST) ein Kennwort zugewiesen wurde, geben Sie das Kennwort ein, und wählen Sie dann **OK aus.**
    
8. Legen Sie die Optionen für den Import von Elementen fest. Im Normalfall müssen die Standardeinstellungen nicht geändert werden.
    
9. Wählen Sie **Fertig stellen** aus.

> [!NOTE]
> Die Schritte bleiben für den Zugriff auf die OneDrive- und E-Mail-Daten eines vorhandenen Benutzers identisch.
    
> [!TIP]
> Wenn Sie nur wenige Elemente aus einer Outlook-Datendatei (PST) importieren oder wiederherstellen möchten, können Sie die Outlook-Datendatei öffnen. Ziehen Sie dann im Navigationsbereich die Elemente aus Outlook Data File-Ordnern in Ihre vorhandenen Outlook-Ordner. 
  
  
## <a name="related-articles"></a>Verwandte Artikel
[Entfernen eines ehemaligen Mitarbeiters aus Office 365](remove-former-employee.md)

[Hinzufügen und Entfernen von Administratoren in einem #A0](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)

[Wiederherstellen eines gelöschten OneDrive](/onedrive/restore-deleted-onedrive)
  
[Aufbewahrung und Löschung in OneDrive](/onedrive/retention-and-deletion)
