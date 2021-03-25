---
title: Installieren und Verwenden des Junk-E-Mail-Berichts-Add-Ins für Microsoft Outlook
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie Sie das Microsoft Junk Email Reporting-Add-In installieren und verwenden, um Spam-, Nichtspam- und Phishingnachrichten an Microsoft zu melden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e120ceec355ffc135e00e13a89a0f29085946a3b
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204239"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a>Installieren und Verwenden des Junk-E-Mail-Berichts-Add-Ins für Microsoft Outlook

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Wenn Sie das Junk-E-Mail-Berichterstellungs-Add-In derzeit nicht verwenden, wird stattdessen das [Add-In](enable-the-report-message-add-in.md) Nachricht melden oder das [Phishing-Add-In](enable-the-report-phish-add-in.md) melden empfohlen. Weitere Informationen finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).

Das Junk-E-Mail-Berichterstellungs-Add-In für Microsoft Outlook ermöglicht Es Benutzern, falsch positive Nachrichten (gute E-Mails, die als Spam gekennzeichnet sind), falsch negative Nachrichten (ungültige E-Mails zulässig) und Phishingnachrichten an Microsoft zu senden. Wenn Ihre Organisation Exchange Online Protection nicht verwendet (z. B. lokale Exchange- oder E-Mail-Dienste, die keine Exchange Online sind), wirkt sich ihre Übermittlung von Junk-E-Mail-Berichten nicht auf Ihre Spamfilterung aus.

In diesem Thema wird erläutert, wie Sie das Junk-E-Mail-Berichterstellungs-Add-In installieren und verwenden.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Informationen zum Installieren des Junk-E-Mail-Berichts-Add-Ins finden Sie im Abschnitt Installieren des [Junk-E-Mail-Berichts-Add-Ins](#install-the-junk-email-reporting-add-in) weiter später in diesem Artikel.

- Das Junk-E-Mail-Berichterstellungs-Add-In funktioniert mit den folgenden Versionen von Outlook:

  - Outlook 2013 oder höher
  - Outlook in Microsoft 365 Apps for Enterprise enthalten

- Weitere Informationen zum Melden von Nachrichten an Microsoft finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a>Verwenden des Junk-E-Mail-Berichts-Add-Ins zum Melden von Spam- und Phishingnachrichten

1. Verwenden Sie für Nachrichten im Posteingang oder in einem anderen E-Mail-Ordner mit Ausnahme von Junk-E-Mails eine der folgenden Methoden, um Spam- und Phishingnachrichten zu melden:

   - Wählen Sie die Nachricht aus, oder öffnen Sie die Nachricht. Klicken Sie  **auf der Registerkarte** Start oder Nachricht im Menüband auf **Junk,** und wählen Sie **dann Als** Junk melden oder Als Phishing **melden aus.**

     ![Melden von Junk- oder Phishing-E-Mails über das Menüband](../../media/junk-email-reporting-ribbon.png)

   - Klicken Sie mit der rechten Maustaste auf die Nachricht, wählen Sie **Junk** aus, und wählen Sie **dann Als** Junk melden oder Als Phishing **melden aus.**

     ![Melden von Junk- oder Phishing-E-Mails mit der rechten Maustaste](../../media/junk-email-reporting-right-click.png)

   - Wählen Sie mehrere Nachrichten aus, klicken Sie mit der rechten Maustaste, und wählen Sie **dann Als Junk melden** oder Als Phishing melden **aus.**

     ![Melden mehrerer Junk- oder Phishing-E-Mail-Nachrichten mit der rechten Maustaste](../../media/junk-email-reporting-right-click-multiple.png)

2. Lesen Sie im angezeigten Dialogfeld die Informationen, und klicken Sie auf **Bericht**. Wenn Sie Ihre Meinung ändern, klicken Sie auf **Nicht melden**.

   ![Melden als Junkdialogfeld](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Melden als Phishingdialogfeld](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. Die ausgewählten Nachrichten werden zur Analyse an Microsoft gesendet und:

   - In den Junk-E-Mail-Ordner verschoben, wenn er als Spam gemeldet wurde.
   - Gelöscht, wenn es als Phishing gemeldet wurde.

   Wenn Sie überprüfen möchten, ob die Nachrichten gesendet wurden, öffnen Sie den Ordner **Gesendete Objekte**, in dem die gesendeten Nachrichten angezeigt werden sollten.

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a>Verwenden des Junk-E-Mail-Berichts-Add-Ins zum Melden von Nichtspam- und Phishingnachrichten aus dem Junk-E-Mail-Ordner

1. Verwenden Sie im Ordner Junk-E-Mail eine der folgenden Methoden, um Spam falsch positive Nachrichten oder Phishingnachrichten zu melden:

   - Wählen Sie die Nachricht aus, oder öffnen Sie die Nachricht. Klicken Sie  **auf der** Registerkarte Start oder Nachricht im Menüband auf **Nicht** Junk, und wählen Sie dann Melden als Nicht **Junk** oder Als Phishing **melden aus.**

     ![Melden sie keine Junk- oder Phishing-E-Mails vom Menüband im Ordner Junk-E-Mail](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - Klicken Sie mit der rechten Maustaste auf die Nachricht, klicken Sie auf **Junk**, und wählen Sie **dann Als** Nicht Junk melden oder Als Phishing **melden aus.**

     ![Melden sie keine Junk- oder Phishing-E-Mails von der rechten Maustaste im Ordner Junk-E-Mail](../../media/junk-email-reporting-junk-folder-right-click.png)

   - Wählen Sie mehrere Nachrichten aus, klicken Sie mit der rechten Maustaste, und wählen Sie dann Melden als **Nicht Junk oder** Als Phishing melden **aus.**

     ![Melden mehrerer Junk- oder Phishing-E-Mail-Nachrichten mit der rechten Maustaste im Ordner Junk-E-Mail](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. Lesen Sie im angezeigten Dialogfeld die Informationen, und klicken Sie auf **Bericht**. Wenn Sie Ihre Meinung ändern, klicken Sie auf **Nicht melden**.

   ![Melden als Nicht-Junk-Dialogfeld](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Melden als Phishingdialogfeld](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. Die ausgewählten Nachrichten werden zur Analyse an Microsoft gesendet und:

   - In den Junk-E-Mail-Ordner verschoben, wenn er als Spam gemeldet wurde.
   - Gelöscht, wenn es als Phishing gemeldet wurde.

   Wenn Sie überprüfen möchten, ob die Nachrichten gesendet wurden, öffnen Sie den Ordner **Gesendete Objekte**, in dem die gesendeten Nachrichten angezeigt werden sollten.

## <a name="install-the-junk-email-reporting-add-in"></a>Installieren des Junk-E-Mail-Berichts-Add-Ins

- Sie benötigen Administratorrechte auf dem Computer, auf dem Sie das Add-In installieren.

- Wechseln Sie zu und laden Sie die entsprechende MSI-Datei für Ihre Office-Version an einen Speicherort herunter, der <https://www.microsoft.com/download/details.aspx?id=18275> leicht zu finden ist:

  - **32-Bit:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`
  - **64-Bit:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

- Für Outlook 2013 oder höher ist die einzige Voraussetzung das Microsoft .NET Framework 2.0. In Windows 10 installieren Sie die .NET Framework 2.0 nicht aus einem Download.

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a>Installieren des Junk-E-Mail-Berichts-Add-Ins mithilfe des Setup-Assistenten

1. Schließen Sie Outlook auf Ihrem Computer.

2. Überprüfen Sie in Windows 10, ob .NET Framework 2.0 aktiviert ist. Anweisungen finden Sie unter [Enable the .NET Framework 3.5 in Control Panel](/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).

3. Suchen Sie die heruntergeladene MSI-Datei, und doppelklicken Sie darauf.

4. Klicken Sie auf der Seite **Willkommen beim Setup des Microsoft-Add-Ins "Junk-E-Mail-Berichtsprogramm"** auf **Weiter**.

5. Überprüfen Sie den Lizenzvertrag, klicken Sie auf Ich stimme den **Bedingungen im** Lizenzvertrag zu, wenn Sie den Bedingungen zustimmen, und klicken Sie dann auf **Weiter**.

6. Klicken Sie nach Abschluss des Assistenten auf **Fertig stellen**.

Starten Sie Outlook.

Suchen Sie im **Outlook-Menüband** nach der Schaltfläche Junk. Sie können Microsoft nun Junk-E-Mails melden, indem Sie die entsprechenden E-Mails im Posteingang auswählen und dann auf die Schaltfläche **Junk-E-Mails melden** klicken.

Wählen Sie den Pfeil nach unten neben **Junk** aus, um weitere Optionen anzuzeigen, z. B. **Als betrügerischen Phishing-Versuch melden**, wenn Sie Phishing-Scam-E-Mails an Microsoft melden möchten. In Ihrem Junk-E-Mailordner können Sie auch **Keine Junk-E-Mail** auswählen, wenn eine E-Mail-Nachricht fälschlicherweise als Junk-E-Mail gekennzeichnet wurde.

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a>Installieren des Add-Ins „Junk-E-Mail-Berichtsprogramm“ im unbeaufsichtigten Modus

1. Schließen Sie Outlook auf Ihrem Computer.

2. Installieren Sie in Windows 10 die .NET Framework 2.0, indem Sie den folgenden Befehl ausführen:

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. Öffnen Sie eine Eingabeaufforderung, und verwenden Sie die folgende Syntax, um das #A0 ohne Benutzerinteraktion zu installieren:

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - `MaxMessageSelection` gibt die maximale Anzahl von Nachrichten an, die Sie für eine einzelne Übermittlung auswählen können. Gültige Werte liegen zwischen 1 und 50. Der Standardwert ist 15.

   - `BccEmailAddress` gibt zusätzliche Bcc-Empfänger an, die eine Kopie aller Benutzerübermittlungen erhalten. Der Standardwert ist leer (keine zusätzlichen Bcc-Empfänger).

   In diesem Beispiel wird die 64-Bit-Version des Add-Ins aus dem angegebenen Pfad mit den Standardeinstellungen installiert.

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   In diesem Beispiel wird die 32-Bit-Version des Add-Ins über den angegebenen Pfad mit den folgenden zusätzlichen Einstellungen installiert:

   - Bis zu 20 Nachrichten können in einer einzigen Übermittlung ausgewählt werden.
   - junkreports@contoso.com und hollyd@treyresearch.net erhalten Bcc-Kopien aller Übermittlungen.

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Gehen Sie wie folgt vor, um zu überprüfen, ob Sie das Junk-E-Mail-Berichterstellungs-Add-In erfolgreich installiert haben:

- Wählen Sie die Nachricht aus, oder öffnen Sie die Nachricht. Klicken Sie **auf der** Registerkarte **Start** oder Nachricht im Menüband auf **Junk,** und stellen Sie sicher, dass die folgenden Optionen verfügbar sind:

  - **Melden als Junk**
  - **Melden als Phishing**
  - **Junkberichtsoptionen**
  - **Junk-Online-Hilfe melden**

  ![Melden von Junk- oder Phishing-E-Mails über das Menüband](../../media/junk-email-reporting-ribbon.png)

- Klicken Sie mit der rechten Maustaste auf die Nachricht, wählen Sie **Junk** aus, und stellen Sie sicher, dass die folgenden Optionen verfügbar sind:

  - **Melden als Junk**
  - **Melden als Phishing**
  - **Junkberichtsoptionen**
  - **Junk-Online-Hilfe melden**

  ![Melden von Junk- oder Phishing-E-Mails mit der rechten Maustaste](../../media/junk-email-reporting-right-click.png)

- Wählen Sie mehrere Nachrichten aus, klicken Sie mit der rechten Maustaste, und überprüfen Sie, ob die folgenden Optionen verfügbar sind:

  - **Melden als Junk**
  - **Melden als Phishing**

  ![Melden mehrerer Junk- oder Phishing-E-Mail-Nachrichten mit der rechten Maustaste](../../media/junk-email-reporting-right-click-multiple.png)

- Gehen Sie wie zuvor im Ordner **Junk-E-Mail** vor, und überprüfen Sie, ob die vorherigen **Junkberichtsoptionen** jetzt **Nicht Junk sind.**

  ![Melden sie keine Junk- oder Phishing-E-Mails vom Menüband im Ordner Junk-E-Mail](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![Melden sie keine Junk- oder Phishing-E-Mails von der rechten Maustaste im Ordner Junk-E-Mail](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Melden mehrerer Junk- oder Phishing-E-Mail-Nachrichten mit der rechten Maustaste im Ordner Junk-E-Mail](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a>Deinstallieren des Add-Ins "Junk-E-Mail-Berichtsprogramm"

Verwenden Sie nach dem Schließen von Outlook eines der folgenden Verfahren, um das Junk-E-Mail-Berichterstellungs-Add-In zu deinstallieren:

- **Systemsteuerung**: Drücken Sie die Windows-TASTE + R. Geben Sie **im** geöffneten Dialogfeld Ausführen die Eingabe `control appwiz.cpl` ein, und klicken Sie dann auf **OK**.

  Suchen Sie das **Microsoft Junk-E-Mail-Berichterstellungs-Add-In,** und wählen Sie es in der Liste aus, und klicken Sie dann auf **Deinstallieren.**

- **Windows Installer-Paket:** Suchen oder laden Sie die entsprechende MSI-Datei herunter, und doppelklicken Sie darauf.

  - **32-Bit:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`

  - **64-Bit:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

  Wählen Sie im angezeigten Dialogfeld **Microsoft Junk-E-Mail-Berichterstellungs-Add-In** entfernen für Outlook aus, und klicken Sie dann auf **Weiter**.

- **Silent Mode**: Suchen oder laden Sie die entsprechende MSI-Datei herunter. Ersetzen Sie in einem Eingabeaufforderungsfenster durch den Speicherort der \<PathToFile\> MSI-Datei, und führen Sie einen der folgenden Befehle aus:

  - **32-Bit:**

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - **64-Bit:**

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

Wenn Sie Outlook nach der Deinstallation öffnen, sollten die Junk-, nicht Junk- und Phishingberichtsoptionen weg sein.

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a>Problembehandlung für das Junk-E-Mail-Bericht-Add-In

Gelegentlich können Probleme mit Outlook nach dem Hinzufügen des Junk-E-Mail-Berichts-Add-Ins angezeigt werden. In diesem Abschnitt werden Probleme beschrieben, die auftreten können, sowie Tipps zum Beheben dieser Probleme.

### <a name="troubleshooting-for-users"></a>Problembehandlung für Benutzer

Es gibt mindestens eines der folgenden Probleme:

- Das Programm reagiert nicht, wenn Sie auf **Junk-E-Mail melden** klicken
- Outlook reagiert nicht mehr, wenn Sie eine E-Mail auswählen
- Gemeldete Junk-E-Mails können nicht übermittelt werden, und es wird eine Unzustellbarkeitsnachricht angezeigt

Gehen Sie wie folgt vor, um dieses Problem zu beheben:

1. Schließen und starten Sie Outlook neu.
2. Erstellen und senden Sie eine Testnachricht, und vergewissern Sie sich, dass der Empfänger die Nachricht empfangen hat.
3. Wenn das Problem weiterhin besteht, wenden Sie sich an Ihren Administrator.

Weitere Methoden zum Übermitteln von Nachrichten an Microsoft finden Sie unter Melden von Nachrichten [und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).

### <a name="troubleshooting-for-admins"></a>Problembehandlung für Administratoren

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a>Problem: Es wird ständig eine Fehlermeldung angezeigt, in der Benutzer zur Kontaktaufnahme mit ihrem Systemadministrator gefragt werden.

1. Überprüfen oder festlegen Sie `LoggingLevel` den Registrierungsschlüssel auf den Wert "Verbose":

   - **32-Bit-Outlook unter 32-Bit-Windows**:

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - **32-Bit-Outlook unter 64-Bit-Windows**:

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - **64-Bit-Outlook**:

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. Starten Sie Outlook neu, und fordern Sie Benutzer auf, sich zu melden, wenn die Fehlermeldung angezeigt wird.

3. Erfassen Sie die Protokollinformationen am folgenden Speicherort:

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. Kontaktieren Sie den technischen Support für Exchange Online Protection, und übergeben Sie den Mitarbeitern diese Protokollinformationen.

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a>Problem: Benutzer haben ausgewählt, keine Bestätigungsaufforderung zu erhalten, wenn sie Nachrichten melden, und jetzt möchten sie die Eingabeaufforderung zurück

1. Erstellen Sie `ConfirmReportJunk` den Registrierungsschlüssel mit dem Wert "True":

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. Starten Sie Outlook neu.