---
title: Aktivieren von Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Administratoren können die Unterstützung für die Sensitivitäts Bezeichnung für Word-, Excel-und PowerPoint-Dateien in SharePoint und OneDrive aktivieren.
ms.openlocfilehash: bdf66e4160e324fa3b83cc58214b16fbacf5c233
ms.sourcegitcommit: fa6a1e432747e150df945050a3744b4408ceb2d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/01/2020
ms.locfileid: "43957285"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive"></a>Aktivieren von Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

Bevor Sie Vertraulichkeits Bezeichnungen für Office-Dateien in SharePoint und OneDrive aktivieren, können Sie Ihre [Vertraulichkeits Bezeichnungen](sensitivity-labels.md) nicht in Office im Internet anwenden. Die Schaltfläche " **Empfindlichkeit** " auf dem Menüband oder der zugewiesene Beschriftungsname auf der Statusleiste wird nicht angezeigt. Wenn Sie außerdem Desktop-Apps zum Beschriften Ihrer Dateien verwenden und diese dann in SharePoint oder OneDrive speichern, kann der Dienst den Inhalt dieser Dateien nicht verarbeiten, wenn die Bezeichnung die Verschlüsselung angewendet hat. Die gemeinsame Dokumenterstellung, eDiscovery, Verhinderung von Datenverlust, die Suche und andere kollaborative Features funktionieren unter diesen Umständen nicht.

Wenn Sie Sensitivitäts Bezeichnungen für Office-Dateien in SharePoint und OneDrive aktivieren, werden alle diese Funktionen aktiviert. Zusätzlich zur Anzeige von Sensitivitäts Bezeichnungen für Benutzer, für neue und geänderte Dateien, für die eine Vertraulichkeits Bezeichnung angewendet wurde, die die Verschlüsselung mit einem cloudbasierten Schlüssel umfasst:

- SharePoint erkennt Vertraulichkeits Bezeichnungen, die auf Word-, Excel-und PowerPoint-Dateien in SharePoint und OneDrive angewendet werden: während die Datei in SharePoint gespeichert wird, wird die Verschlüsselung von Azure Information Protection entfernt, sodass der Dateiinhalt verarbeitet werden kann. Informationen dazu, wie Dokumente geschützt werden, während Sie in SharePoint gespeichert werden, finden Sie unter [Datenverschlüsselung in OneDrive für Unternehmen und SharePoint Online](data-encryption-in-odb-and-spo.md).

- Wenn Sie diese Datei aus SharePoint oder OneDrive herunterladen oder darauf zugreifen, werden die Vertraulichkeits Bezeichnung und alle Verschlüsselungseinstellungen aus der Bezeichnung erneut mit der Datei angewendet, und diese Einstellungen bleiben überall dort bestehen, wo die Datei gespeichert wird. Stellen Sie aufgrund dieses Verhaltens sicher, dass Sie Benutzeranleitungen zur Verwendung nur von Bezeichnungen zum Schützen von Dokumenten bereitstellen. Weitere Informationen finden Sie unter [Information Rights Management (IRM) Options and Sensitivity Labels](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels).

- Damit SharePoint die Verschlüsselung aus der Datei beim Hochladen entfernen kann, muss der Benutzer, der die beschriftete und verschlüsselte Datei hochlädt, über Nutzungsrechte verfügen, um die Datei mindestens anzuzeigen. In SharePoint wird die Verschlüsselung von Dateien nicht entfernt, wenn der Benutzer Sie nicht außerhalb von SharePoint öffnen kann.

- Verwenden Sie Office im Internet (Word, Excel, PowerPoint) zum Öffnen und Bearbeiten von Office-Dateien mit Vertraulichkeits Bezeichnungen, die Verschlüsselung anwenden. Die Berechtigungen, die der Verschlüsselung zugewiesen wurden, werden erzwungen. Mit Word im Internet können Sie auch die automatische Kennzeichnung verwenden, wenn Sie diese Dokumente bearbeiten.

- Office 365 eDiscovery unterstützt die Volltextsuche für diese Dateien. DLP-Richtlinien (Data Loss Prevention) decken Inhalte in diesen Dateien ab.

> [!NOTE]
> Wenn die Verschlüsselung nicht mit einem cloudbasierten Schlüssel, sondern einem lokalen Schlüssel, einer Schlüssel Verwaltungstopologie, die häufig als "eigenen Schlüssel halten" (Hyok) verwendet wurde, wird das SharePoint-Verhalten bei der Verarbeitung des Dateiinhalts nicht geändert.
>
> Das SharePoint-Verhalten ändert sich auch nicht für vorhandene beschriftete und verschlüsselte Dateien in SharePoint. Damit diese Dateien von den neuen Funktionen profitieren, müssen Sie entweder heruntergeladen und hochgeladen oder bearbeitet werden, nachdem Sie den Befehl ausgeführt haben, um Sensitivitäts Bezeichnungen für SharePoint und OneDrive zu aktivieren. Sie werden dann beispielsweise in Such-und eDiscovery-Ergebnissen zurückgegeben.

Nachdem Sie Sensitivitäts Bezeichnungen für Office-Dateien in SharePoint und OneDrive aktiviert haben, stehen drei neue [Überwachungsereignisse](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) für die Überwachung von Sensitivitäts Bezeichnungen zur Verfügung, die auf Dokumente in SharePoint und OneDrive angewendet werden:
- **Vertraulichkeitsbezeichnung wurde auf Datei angewendet**
- **Auf Datei angewendete Vertraulichkeitsbezeichnung wurde geändert**
- **Vertraulichkeitsbezeichnung wurde von Datei entfernt**

Sehen Sie sich das folgende Video (kein Audio) an, um die neuen Funktionen in Aktion anzuzeigen:

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

Sie haben immer die Wahl, um Vertraulichkeits Bezeichnungen für Office-Dateien in SharePoint und OneDrive zu jeder Zeit zu deaktivieren.

## <a name="requirements"></a>Anforderungen

Diese neuen Funktionen funktionieren nur mit [Vertraulichkeits Bezeichnungen](sensitivity-labels.md) . Wenn Sie derzeit über Azure Information Protection-Bezeichnungen verfügen, migrieren Sie Sie zunächst zu Sensitivitäts Bezeichnungen, sodass Sie diese Funktionen für neue Dateien, die Sie hochladen, aktivieren können. Anweisungen finden Sie unter [How to migrate Azure Information Protection Labels to Unified Sensitivity Labels](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)

Verwenden Sie die OneDrive-Synchronisierungs-App-Version 19.002.0121.0008 oder höher unter Windows und Version 19.002.0107.0008 oder höher unter Mac. Beide Versionen wurden am 28. Januar 2019 veröffentlicht und sind derzeit für alle Ringe freigegeben. Weitere Informationen finden Sie in den [Anmerkungen zur OneDrive-Version](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0). Nachdem Sie Sensitivitäts Bezeichnungen für Office-Dateien in SharePoint und OneDrive aktiviert haben, werden Benutzer, die eine ältere Version der Synchronisierungs-app ausführen, aufgefordert, Sie zu aktualisieren.

## <a name="limitations"></a>Einschränkungen

- Wenn Sie Sensitivitäts Bezeichnungen für Office-Dateien in SharePoint und OneDrive aktivieren, können Benutzer, die eine Bezeichnung für eine Datei in einem OneDrive-synchronisierungsordner ändern, möglicherweise keine anderen an der Datei vorgenommenen Änderungen speichern. Dieses Szenario bezieht sich auf Dateien, die mit Verschlüsselung versehen sind, und auch dann, wenn die Bezeichnungs Änderung von einer Bezeichnung stammt, die die Verschlüsselung nicht auf eine Bezeichnung angewendet hat, die die Verschlüsselung verwendet. Benutzer sehen einen [roten Kreis mit einem weißen Kreuz Symbol Fehler](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3), und Sie werden aufgefordert, neue Änderungen als separate Kopie zu speichern.  
    
    Neben Bezeichnungsänderungen, die von Benutzern initiiert werden, kann dasselbe Verhalten auftreten, wenn ein Administratoreinstellungen für eine veröffentlichte Bezeichnung ändert, die bereits auf Dateien angewendet wird, die auf den synchronisierungsclient des Benutzers heruntergeladen wurden.
    
    Führen Sie eine der folgenden Aktionen aus, um den Verlust von Arbeit für diese Szenarien zu vermeiden:
    - Verwenden Sie die Webversionen der Office-Apps, um Bezeichnungen anzuwenden.
    - Schließen Sie eine Datei, nachdem Sie eine Bezeichnung angewendet haben, und öffnen Sie die Datei erneut, um weitere Änderungen vorzunehmen.

- SharePoint wendet keine Vertraulichkeits Bezeichnungen automatisch auf vorhandene Dateien an, die Sie bereits mithilfe von Azure Information Protection-Bezeichnungen verschlüsselt haben. Um die Funktionen zu erhalten, nachdem Sie Sensitivitäts Bezeichnungen für Office-Dateien in SharePoint und OneDrive aktiviert haben, müssen Sie diese Aufgaben stattdessen ausführen:
    
    1. Stellen Sie sicher, dass Sie die Azure Information Protection-Bezeichnungen zu Sensitivitäts Bezeichnungen migriert und diese im Microsoft 365 Compliance Center oder in einer entsprechenden Bezeichnungs Verwaltungskonsole veröffentlicht haben.
    
    2. Laden Sie die Dateien herunter, und laden Sie Sie dann in SharePoint hoch.

- In SharePoint können keine verschlüsselten Dateien verarbeitet werden, wenn die Bezeichnung, auf die die Verschlüsselung angewendet wird, eine der folgenden Konfigurationen für die Verschlüsselung aufweist:
    - **Zulassen, dass Benutzerberechtigungen zuweisen, wenn Sie die Bezeichnung anwenden** , und das Kontrollkästchen für **in Word, PowerPoint und Excel fordern Sie Benutzer zur Angabe von Berechtigungen aufgefordert** wird ausgewählt ist. Diese Einstellung wird manchmal auch als "benutzerdefinierte Berechtigungen" bezeichnet.
    - Der **Benutzer Zugriff auf Inhalts Ablauf** wird auf einen anderen Wert als **Never**festgelegt.
    
    Bei Beschriftungen mit einer dieser Verschlüsselungs Konfigurationen werden die Beschriftungen nicht für Benutzer in Office im Internet angezeigt. Darüber hinaus können die neuen Funktionen nicht mit beschrifteten Dokumenten verwendet werden, die bereits über diese Verschlüsselungseinstellungen verfügen. Beispielsweise werden diese Dokumente nicht in den Suchergebnissen zurückgegeben, auch wenn Sie aktualisiert werden.

- Für ein verschlüsseltes Dokument, das Bearbeitungsberechtigungen für einen Benutzer gewährt, kann das Kopieren in den Webversionen der Office-Apps nicht blockiert werden.

- Die Dokument Verfolgungs Website für Azure Information Protection wird nicht unterstützt.

- Office-Desktop-Apps und-Mobile Apps unterstützen nicht die gemeinsame Dokumenterstellung für Dateien, die mit Verschlüsselung gekennzeichnet sind. Diese apps öffnen weiterhin beschriftete und verschlüsselte Dateien im exklusiven Bearbeitungsmodus.

- Wenn ein beschriftetes Dokument in SharePoint hochgeladen wird und die Bezeichnung angewandte Verschlüsselung mithilfe eines Kontos aus einem Dienstprinzipalnamen verwendet wird, kann das Dokument nicht in Office im Internet geöffnet werden. Zu den Beispielszenarien zählen Microsoft Cloud-App-Sicherheit und eine Datei, die per e-Mail an Teams gesendet wird.

- Benutzer können Speicherprobleme nach dem Wechseln in den Standbymodus oder in einen Ruhemodus haben, wenn anstelle von Office für das Internet der Desktop und der Mobile Apps für Word, Excel oder PowerPoint verwendet werden. Wenn diese Benutzer Ihre Office-App-Sitzung fortsetzen und versuchen, Änderungen zu speichern, wird eine Fehlermeldung zum hochladen angezeigt, in der Sie eine Kopie speichern können, anstatt die Originaldatei zu speichern. 

- Dokumente, die auf folgende Weise verschlüsselt wurden, können nicht in Office im Internet geöffnet werden:
    - Verschlüsselung, die einen lokalen Schlüssel verwendet ("eigenen Schlüssel halten" oder Hyok)
    - Verschlüsselung, die unabhängig von einer Bezeichnung angewendet wurde, beispielsweisedurch direkte Anwendung einer Vorlage zum Schutz von Rechteverwaltung.

- Wenn Sie eine Bezeichnung löschen, die auf ein Dokument in SharePoint angewendet wurde, anstatt die Beschriftung aus der entsprechenden Bezeichnungsrichtlinie zu entfernen, wird das Dokument beim Herunterladen nicht mit einer Bezeichnung versehen oder verschlüsselt. Im Vergleich dazu bleibt das Dokument verschlüsselt, wenn das beschriftete Dokument außerhalb von SharePoint gespeichert wird, wenn die Bezeichnung gelöscht wird. Beachten Sie, dass Sie zwar während einer Testphase Beschriftungen löschen können, es aber sehr selten ist, eine Bezeichnung in einer Produktionsumgebung zu löschen.

## <a name="how-to-enable-sensitivity-labels-for-sharepoint-and-onedrive-opt-in"></a>Aktivieren von Sensitivitäts Bezeichnungen für SharePoint und OneDrive (Opt-in)

Sie können die neuen Funktionen mithilfe des Microsoft 365 Compliance Center oder mithilfe von PowerShell aktivieren.

### <a name="use-the-compliance-center-to-enable-support-for-sensitivity-labels"></a>Aktivieren der Unterstützung für Vertraulichkeits Bezeichnungen mithilfe des Compliance Centers

Diese Option ist die einfachste Möglichkeit, um Vertraulichkeits Bezeichnungen für SharePoint und OneDrive zu aktivieren.

Der globale Administrator für Ihre Organisation verfügt über vollständige Berechtigungen zum Erstellen und Verwalten aller Aspekte von Vertraulichkeitsbezeichnungen. Wenn Sie sich nicht als globaler Administrator anmelden, lesen Sie [Zum Erstellen und Verwalten von Vertraulichkeitsbezeichnungen erforderliche Berechtigungen](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels).

1. Melden Sie sich beim [Microsoft 365 Compliance Center](https://compliance.microsoft.com/)an, und navigieren Sie zu **Lösungs** > **Informationsschutz**
    
    Wenn diese Option nicht sofort angezeigt wird, wählen Sie zunächst **Alle anzeigen** aus. 

2. Wenn eine Meldung angezeigt wird, um die Möglichkeit zum Verarbeiten von Inhalt in Office Online-Dateien zu aktivieren, wählen Sie **jetzt aktivieren**aus:
    
    ![Schaltfläche "jetzt aktivieren", um Sensitivitäts Bezeichnungen für Office Online zu aktivieren](../media/sensitivity-labels-turn-on-banner.png)
    
    Der Befehl wird sofort ausgeführt, und wenn die Seite als nächstes aktualisiert wird, wird die Nachricht oder Schaltfläche nicht mehr angezeigt. 

> [!NOTE]
> Wenn Sie über Office 365 Multi-Geo verfügen, müssen Sie PowerShell verwenden, um diese Funktionen für alle geografischen Standorte zu aktivieren. Ausführliche Informationen finden Sie im nächsten Abschnitt.

### <a name="use-powershell-to-enable-support-for-sensitivity-labels"></a>Verwenden von PowerShell zum Aktivieren der Unterstützung für Vertraulichkeits Bezeichnungen

Als Alternative zur Verwendung des Compliance Centers können Sie die Unterstützung für Sensitivitäts Bezeichnungen mithilfe des Cmdlets " [SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) " aus SharePoint Online PowerShell aktivieren. 

Wenn Sie über Office 365 Multi-Geo verfügen, müssen Sie PowerShell verwenden, um diese Unterstützung für alle geografischen Standorte zu aktivieren.

#### <a name="prepare-the-sharepoint-online-management-shell"></a>Vorbereiten der SharePoint Online Management-Shell

Bevor Sie den PowerShell-Befehl ausführen, um Sensitivitäts Bezeichnungen für Office-Dateien in SharePoint und OneDrive zu aktivieren, stellen Sie sicher, dass Sie SharePoint Online Management Shell Version 16.0.19418.12000 oder höher ausführen. Wenn Sie bereits über die neueste Version verfügen, können Sie zum [nächsten Verfahren](#run-the-powershell-command-to-enable-support-for-sensitivity-labels) wechseln, um den PowerShell-Befehl auszuführen.

1. Wenn Sie eine frühere Version der SharePoint-Online-Verwaltungsshell aus dem PowerShell-Katalog installiert haben, können Sie das Modul aktualisieren, indem Sie das folgende Cmdlet ausführen.

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. Wenn Sie eine frühere Version der SharePoint Online Management Shell aus dem Microsoft Download Center installiert haben, können Sie auch zum **Hinzufügen oder Entfernen von Software** wechseln und die SharePoint Online Management Shell deinstallieren.

3. Wechseln Sie in einem Webbrowser zur Download Center-Seite, und [laden Sie die neueste SharePoint Online-Verwaltungsshell herunter](https://go.microsoft.com/fwlink/p/?LinkId=255251).

4. Wählen Sie die gewünschte Sprache aus, und klicken Sie auf **Download**.

5. Wählen Sie zwischen der x64- und der x86-Version der MSI-Datei aus. Laden Sie die x64-Datei herunter, wenn Sie die 64-Bit-Version von Windows oder die x86-Datei ausführen, wenn Sie die 32-Bit-Version ausführen. Wenn Sie nicht wissen, finden Sie unter [welche Version des Windows-Betriebssystems soll ich ausführen?](https://support.microsoft.com/help/13443/windows-which-operating-system)

6. Nachdem Sie die Datei heruntergeladen haben, führen Sie die Datei aus, und führen Sie die Schritte im Setup-Assistenten aus.

#### <a name="run-the-powershell-command-to-enable-support-for-sensitivity-labels"></a>Ausführen des PowerShell-Befehls zum Aktivieren der Unterstützung für Vertraulichkeits Bezeichnungen

Verwenden Sie zum Aktivieren der neuen Funktionen das Cmdlet " [SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) " mit dem Parameter " *EnableAIPIntegration* ":

1. Stellen Sie eine Verbindung mit SharePoint her, indem Sie ein Arbeits-oder Schulkonto mit globalen Administrator-oder SharePoint-Administratorrechten in Office 365 verwenden. Eine Anleitung dazu finden Sie unter [Erste Schritte mit der SharePoint Online-Verwaltungsshell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
    
    Hinweis: Wenn Sie Office 365 Multi-Geo haben, verwenden Sie den Parameter "-URL" mit [Connect-SPOService](https://docs.microsoft.com/powershell/module/sharepoint-online/connect-sposervice?view=sharepoint-ps), und geben Sie die Website-URL SharePoint Online Administration Center für einen ihrer geografischen Standorte an.

2. Führen Sie den folgenden Befehl aus, und drücken Sie **Y** , um Folgendes zu bestätigen:

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```
3. Für Office 365 Multi-Geo: Wiederholen Sie die Schritte 1 und 2 für jeden ihrer verbleibenden geografischen Standorte.

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a>Planen des Roll-out nach dem Erstellen oder Ändern einer Sensitivitäts Bezeichnung

Nachdem Sie eine Sensitivitäts Bezeichnung im Microsoft 365 Compliance Center erstellt oder geändert haben, veröffentlichen Sie Sie in Phasen. Wenn Sie Bezeichnungen veröffentlichen, die nicht vollständig synchronisiert sind, können die Dateien nicht in den Webversionen der Office-Apps geöffnet werden, wenn die Benutzer die Bezeichnungen auf Dateien anwenden und in SharePoint hochladen. Such-und eDiscovery funktionieren auch nicht für die Dateien.

Es wird empfohlen, dass Sie die folgenden Schritte ausführen:

1. Veröffentlichen Sie die neue oder geänderte Vertraulichkeits Bezeichnung nur für eine oder zwei Personen.

2. Warten Sie mindestens 24 Stunden nach der ersten Veröffentlichung. Stellen Sie sicher, dass die Bezeichnung vollständig synchronisiert wurde.

3. Veröffentlichen Sie das Label breiter.

## <a name="how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out"></a>Deaktivieren von Sensitivitäts Bezeichnungen für SharePoint und OneDrive (Opt-out)

Wenn Sie diese neuen Funktionen deaktivieren, werden Dateien, die Sie nach dem Aktivieren von Sensitivitäts Bezeichnungen für SharePoint und OneDrive hochgeladen haben, weiterhin durch die Bezeichnung geschützt, da die Beschriftungseinstellungen weiterhin erzwungen werden. Wenn Sie Sensitivitäts Bezeichnungen auf neue Dateien anwenden, nachdem Sie diese neuen Funktionen deaktiviert haben, können die Volltextsuche, eDiscovery und die gemeinsame Dokumenterstellung nicht mehr verwendet werden.

Um diese neuen Funktionen zu deaktivieren, müssen Sie PowerShell verwenden. Verwenden Sie die SharePoint Online [-](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) Verwaltungsshell und das Cmdlet "SPOTenant", und geben Sie den gleichen *EnableAIPIntegration* -Parameter wie im Abschnitt [Verwenden von PowerShell zum Aktivieren der Unterstützung für Sensitivitäts Bezeichnungen](#use-powershell-to-enable-support-for-sensitivity-labels) beschrieben an. Legen Sie dieses Mal den Parameterwert auf false fest, und drücken Sie **Y** , um Folgendes zu bestätigen:

```PowerShell
Set-SPOTenant -EnableAIPIntegration $false
```

Wenn Sie über Office 365 Multi-Geo verfügen, müssen Sie diesen Befehl für jeden ihrer geografischen Standorte ausführen.

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie die Sensitivitäts Bezeichnungen für Office-Dateien in SharePoint und OneDrive aktiviert haben, sollten Sie diese Dateien automatisch mithilfe von Richtlinien mit automatischer Benennung bezeichnen. Weitere Informationen finden Sie unter [Anwenden einer Vertraulichkeits Bezeichnung auf Inhalte automatisch](apply-sensitivity-label-automatically.md).