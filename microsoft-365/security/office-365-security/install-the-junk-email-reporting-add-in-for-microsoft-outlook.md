---
title: Installation des Add-Ins „Junk-E-Mail-Berichtsprogramm“ für Microsoft Outlook
ms.author: MSFTTracyP
author: tracyp
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 8dcc752f-e22e-44ce-a104-4cc4d7e439f3
ms.collection:
- M365-security-compliance
description: In diesem articleSupported LanguagesInstall die Junk-e-Mail-Berichterstellung Add-Deinstallation des Junk-e-Mail-Berichts-Add-info Informationen
ms.openlocfilehash: 14c3914601ab8a6b3273b56a3915df9c909fc06c
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970391"
---
# <a name="install-the-junk-email-reporting-add-in-for-microsoft-outlook"></a>Installation des Add-Ins „Junk-E-Mail-Berichtsprogramm“ für Microsoft Outlook

In diesem Thema wird beschrieben, wie Sie das Microsoft-Add-In „Junk-E-Mail-Berichtsprogramm für Outlook“ auf Clientcomputern in Ihrer Organisation installieren und deinstallieren. Die aktuelle Version des Add-Ins (Januar 2016) enthält Unterstützung für Outlook 2016, Outlook 2013 und Outlook 2010.

Das Add-In (für alle unterstützten Sprachen) ermöglicht es Ihnen, Junk-E-Mails direkt aus dem Outlook-Menüband heraus zu melden. Die englische Version des-Add-Ins enthält zusätzliche Optionen zum Melden von E-Mail-Problemen an Microsoft direkt aus dem Menüband:

-  Melden von eingegangenen Phishing-Scam-E-Mails

- Melden von E-Mails, die fälschlicherweise als Junk-E-Mails identifiziert wurden.

## <a name="supported-languages"></a>Unterstützte Sprachen
<a name="sectionSection0"> </a>

Die folgenden Sprachen werden von dem Add-In "Junk-E-Mail-Berichtsprogramm" unterstützt:

- Chinesisch (vereinfacht)

- Chinesisch (traditionell)

- Niederländisch

- Englisch

- Französisch

- Deutsch

- Italienisch

- Japanisch

- Koreanisch

- Portugiesisch

- Portugiesisch (Brasilien)

- Spanisch

## <a name="install-the-junk-email-reporting-add-in"></a>Installieren des Add-Ins "Junk-E-Mail-Berichtsprogramm"

Sie können das Add-Ins „Junk-E-Mail-Berichtsprogramm“ installieren:

- Führen Sie das Windows Installer-Paket aus wie eine beliebige andere MSI-Datei. Wenn Sie das Add-In installieren, wird eine grafische Benutzeroberfläche geöffnet, und Sie werden durch die Installationsbildschirme geführt. Weitere Informationen finden Sie unter [Installieren des Junk-e-Mail-Berichts-Add-Ins mit dem Setup-Assistenten](#install-the-junk-email-reporting-add-in-using-the-setup-wizard).

ODER

- Führen Sie eine automatische Installation aus, bei der die Benutzeroberfläche für die Installation unterdrückt wird. Stattdessen geben Sie Befehlszeilenoptionen zum Ausführen eines Installationsskripts an. Wenn Sie das Add-In installieren, stehen Ihnen weitere Konfigurationsoptionen zur Verfügung, die über die grafische Benutzeroberfläche nicht verfügbar sind. Weitere Informationen finden Sie unter [Installieren des Junk-e-Mail-Berichts-Add-Ins mithilfe des unbeaufsichtigten Modus](#install-the-junk-email-reporting-add-in-using-silent-mode).

### <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Die **System Anforderungen** für das Add-in "Junk-e- [https://www.microsoft.com/download/details.aspx?id=18275](https://www.microsoft.com/download/details.aspx?id=18275)Mail-Berichterstellung" finden Sie unter.

> [!NOTE]
> Für den Computer, auf dem das Add-In installiert werden soll, sind Administratorrechte erforderlich.

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a>Installieren des Junk-e-Mail-Berichts-Add-Ins mithilfe des Setup-Assistenten

1. Schließen Sie Outlook auf Ihrem Computer.

2. Laden Sie im Abschnitt **Details** des [Microsoft Junk-e-Mail-Berichts-Add-Ins für Microsoft Outlook](https://www.microsoft.com/download/details.aspx?id=18275)die entsprechende MSI-Datei für Ihre Office-Version herunter.

3. Doppelklicken Sie auf die MSI-Datei.

4. Klicken Sie auf der Seite **Willkommen beim Setup des Microsoft-Add-Ins "Junk-E-Mail-Berichtsprogramm"** auf **Weiter**.

5. Lesen Sie den Lizenzvertrag, und wenn Sie mit den Installationsbedingungen einverstanden sind, klicken Sie auf **Ich stimme den Bedingungen des Lizenzvertrags zu** (zum Fortsetzen der Installation erforderlich). Klicken Sie auf **Weiter**, um den Vorgang fortzusetzen.

6. Klicken Sie nach Abschluss des Assistenten auf **Fertig stellen**.

7. Starten Sie Outlook.

8. Suchen Sie auf dem Outlook-Menüband nach der Schaltfläche **Junk** . Sie können Microsoft nun Junk-E-Mails melden, indem Sie die entsprechenden E-Mails im Posteingang auswählen und dann auf die Schaltfläche **Junk-E-Mails melden** klicken.

9. Wählen Sie den Pfeil nach unten neben **Junk** aus, um weitere Optionen anzuzeigen, z. B. **Als betrügerischen Phishing-Versuch melden**, wenn Sie Phishing-Scam-E-Mails an Microsoft melden möchten. In Ihrem Junk-E-Mailordner können Sie auch **Keine Junk-E-Mail** auswählen, wenn eine E-Mail-Nachricht fälschlicherweise als Junk-E-Mail gekennzeichnet wurde.

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a>Installieren des Add-Ins „Junk-E-Mail-Berichtsprogramm“ im unbeaufsichtigten Modus

1. Schließen Sie Outlook auf Ihrem Computer.

2. Öffnen Sie eine Eingabeaufforderung.

3. Falls Sie das Add-In direkt ohne optionale Parameter installieren möchten, geben Sie Folgendes an:

   - Computer mit x86 Outlook:`msiexec /qn /i JunkReportingAdd-in.x86-en.msi`

   - Computer mit x64 Outlook:`msiexec /qn /i JunkReportingAdd-in.x64-en.msi`

    Sie können auch die optionalen Parameter "MaxMessageSelection" und "BccEmailAddress" angeben:

   - MaxMessageSelection ermöglicht es Administratoren, die maximale Anzahl von Nachrichten zu definieren, die von Benutzern für die Übermittlung mit einem einzigen Mausklick ausgewählt werden können. Der Bereich umfasst 1 bis 50 Nachrichten; der Standardwert ist 10.

     Beispiel: Wenn Sie die maximale Anzahl von Nachrichten festlegen möchten, die von Benutzern zur Übermittlung in einem einzigen Mausklick auf 16 ausgewählt werden können, verwenden Sie die folgende Option als Teil des Installationsbefehls:`MaxMessageSelection=16`

   - Mit BccEmailAddress können Administratoren ein Postfach einrichten, um eine Kopie aller Benutzer Übermittlungen zu erhalten, indem Sie eine Bcc-e-Mail-Adresse festlegen. Nachdem das Postfach eingerichtet wurde, wird eine Kopie aller übermittelten E-Mails an die Bcc-E-Mail-Adresse gesendet. Andernfalls wird standardmäßig keine Bcc-E-Mail-Adresse verwendet.

     Beispiel: Wenn Sie junkReports@contoso.com als Bcc-e-Mail-Adresse für alle Übermittlungen verwenden möchten, verwenden Sie den folgenden Befehl:`BccEmailAddress="junkReports@contoso.com"`

     > [!NOTE]
     > Sie können mehrere Bcc-E-Mail-Adressen festlegen, indem Sie sie mit einem Semikolon voneinander trennen. Beispiel:  `BccEmailAddress="junkReports@contoso.com; hollyd@treyresearch.net"`

     Um beide optionalen Parameter basierend auf den vorherigen Beispielen hinzuzufügen, führen Sie den folgenden Befehl auf einem Computer aus, auf dem x86 Outlook ausgeführt wird:

     ```
     msiexec /qn /i JunkReportingAdd-in.x86-en.msi. MaxMessageSelection=16 BccEmailAddress="junkReports@contoso.com; hollyd@treyresearch.net"
     ```

4. Nachdem die Installation abgeschlossen ist, starten Sie Outlook.

5. Suchen Sie auf dem Outlook-Menüband nach der Schaltfläche **Junk** . Sie können Microsoft nun Junk-E-Mails melden, indem Sie die entsprechenden E-Mails im Posteingang auswählen und dann auf die Schaltfläche **Junk-E-Mails melden** klicken.

6. Wählen Sie den Pfeil nach unten neben **Junk** aus, um weitere Optionen anzuzeigen, z. B. **Als betrügerischen Phishing-Versuch melden**, wenn Sie Phishing-Scam-E-Mails an Microsoft melden möchten. In Ihrem Junk-E-Mailordner können Sie auch **Keine Junk-E-Mail** auswählen, wenn eine E-Mail-Nachricht fälschlicherweise als Junk-E-Mail gekennzeichnet wurde.

## <a name="uninstall-the-junk-email-reporting-add-in"></a>Deinstallieren des Add-Ins "Junk-E-Mail-Berichtsprogramm"

Verwenden Sie eine der in diesem Abschnitt beschriebenen Optionen, um das Add-in "Junk-e-Mail-Berichterstellung" zu deinstallieren:

- Entfernen Sie das Add-In über die Windows-Systemsteuerung.

- Führen Sie das Windows Installer-Paket aus, und wählen Sie die Option Deinstallieren aus.

- Führen Sie eine automatische Installation mithilfe der Deinstallationsoption aus.

> [!NOTE]
> Für den Computer, auf dem das Add-In deinstalliert werden soll, sind Administratorrechte erforderlich.

### <a name="uninstall-the-junk-email-reporting-add-in-from-control-panel"></a>Deinstallieren des Add-Ins "Junk-E-Mail-Berichtsprogramm" über die Systemsteuerung

1. Schließen Sie Outlook auf Ihrem Computer.

2. Wählen Sie im Startmenü des Computers die Option **Systemsteuerung**.

3. Wählen Sie **Programme und Funktionen**.

4. Wählen Sie **Microsoft-Add-In "Junk-E-Mail-Berichtsprogramm für Microsoft Office Outlook"**.

5. Wählen Sie **Deinstallieren**.

6. Starten Sie Outlook neu, um sich davon zu überzeugen, dass das Add-In nicht mehr in der Outlook-Menüleiste angezeigt wird.

### <a name="uninstall-the-junk-email-reporting-add-in-by-running-the-windows-installer-package"></a>Deinstallieren des Add-Ins "Junk-E-Mail-Berichtsprogramm" durch Ausführen des Windows Installer-Pakets

1. Schließen Sie Outlook auf Ihrem Computer.

   > [!NOTE]
   > Wenn Outlook während des Deinstallationsvorgangs ausgeführt wird, müssen Sie es neu starten, um das Add-In vollständig zu deinstallieren.

2. Führen Sie die MSI-Datei aus, die Sie zuvor ausgeführt haben, um das Add-In zu installieren.

   (Laden Sie im Abschnitt **Details** des [Add-Ins Microsoft Junk-e-Mail-Berichterstellung für Microsoft Outlook](https://www.microsoft.com/download/details.aspx?id=18275)die entsprechende MSI-Datei für Ihre Office-Version herunter, und doppelklicken Sie dann auf die MSI-Datei.)

3. Folgen Sie den Eingabeaufforderungen, um das Add-In zu deinstallieren.

4. Starten Sie Outlook neu, um sich davon zu überzeugen, dass das Add-In nicht mehr in der Outlook-Menüleiste angezeigt wird.

### <a name="uninstall-the-junk-email-reporting-add-in-in-silent-mode"></a>Deinstallieren des Add-Ins "Junk-E-Mail-Berichtsprogramm" im unbeaufsichtigten Modus

1. Schließen Sie Outlook auf Ihrem Computer.

   > [!NOTE]
   > Wenn Outlook während des Deinstallationsvorgangs ausgeführt wird, müssen Sie es neu starten, um das Add-In vollständig zu deinstallieren.

2. Öffnen Sie eine Eingabeaufforderung.

3. Geben Sie die folgenden Befehlszeilenparameter an:

   Outlook x86:`msiexec /x JunkReportingAdd-in.x86-en.msi /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"`

   Outlook x64:`msiexec /x JunkReportingAdd-in.x64-en.msi /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"`

4. Starten Sie Outlook neu, um sich davon zu überzeugen, dass das Add-In nicht mehr in der Outlook-Menüleiste angezeigt wird.

## <a name="for-more-information"></a>Weitere Informationen

[Melden von Junk-E-Mails an Microsoft](report-junk-email-messages-to-microsoft.md)

[Problembehandlung und Supportinformationen](troubleshooting-and-support-information.md)
