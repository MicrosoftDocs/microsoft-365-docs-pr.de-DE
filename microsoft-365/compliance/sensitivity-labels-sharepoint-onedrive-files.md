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
ms.openlocfilehash: d049cdd61d2155267f4e55c612885929e27adaaa
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845721"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive"></a>Aktivieren von Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

Bevor Sie Vertraulichkeits Bezeichnungen für Office-Dateien in SharePoint und OneDrive aktivieren, können Sie Ihre [Vertraulichkeits Bezeichnungen](sensitivity-labels.md) nicht in Office im Internet anwenden. Die Schaltfläche " **Empfindlichkeit** " auf dem Menüband oder der zugewiesene Beschriftungsname auf der Statusleiste wird nicht angezeigt. Wenn Sie außerdem Desktop-Apps zum Beschriften Ihrer Dateien verwenden und diese dann in SharePoint oder OneDrive speichern, kann der Dienst den Inhalt dieser Dateien nicht verarbeiten, wenn die Bezeichnung die Verschlüsselung angewendet hat. Die gemeinsame Dokumenterstellung, eDiscovery, Verhinderung von Datenverlust, die Suche und andere kollaborative Features funktionieren unter diesen Umständen nicht.

Wenn Sie Sensitivitäts Bezeichnungen für Office-Dateien in SharePoint und OneDrive aktivieren, werden alle diese Funktionen aktiviert. Zusätzlich zur Anzeige von Sensitivitäts Bezeichnungen für Benutzer, für neue und geänderte Dateien, für die eine Vertraulichkeits Bezeichnung angewendet wurde, die die Verschlüsselung mit einem cloudbasierten Schlüssel enthält (und keine [Doppelschlüssel Verschlüsselung](double-key-encryption.md)verwendet):

- Für Word-, Excel-und PowerPoint-Dateien erkennt SharePoint die Bezeichnung und kann nun den Inhalt der verschlüsselten Datei verarbeiten.

- Wenn Sie diese Dateien aus SharePoint oder OneDrive herunterladen oder darauf zugreifen, werden die Vertraulichkeits Bezeichnung und alle Verschlüsselungseinstellungen von der Bezeichnung erzwungen und verbleiben bei der Datei, unabhängig davon, wo Sie gespeichert ist. Stellen Sie sicher, dass Sie Benutzeranleitungen zur Verwendung nur von Bezeichnungen zum Schutz von Dokumenten bereitstellen. Weitere Informationen finden Sie unter [Information Rights Management (IRM) Options and Sensitivity Labels](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels).

- Wenn Benutzer beschriftete und verschlüsselte Dateien in SharePoint hochladen, müssen Sie mindestens über die Berechtigung "anzeigen" für diese Dateien verfügen. Beispielsweise können Sie die Dateien außerhalb von SharePoint öffnen. Wenn Sie nicht über dieses minimale Nutzungsrecht verfügen, ist der Upload erfolgreich, aber SharePoint erkennt die Bezeichnung nicht und kann die Dateiinhalte nicht verarbeiten.

- Verwenden Sie Office im Internet (Word, Excel, PowerPoint) zum Öffnen und Bearbeiten von Office-Dateien mit Vertraulichkeits Bezeichnungen, die Verschlüsselung anwenden. Die Berechtigungen, die der Verschlüsselung zugewiesen wurden, werden erzwungen. Mit Word im Internet können Sie auch die automatische Kennzeichnung verwenden, wenn Sie diese Dokumente bearbeiten.

- Externe Benutzer können mithilfe von Gastkonten auf Dokumente zugreifen, die mit Verschlüsselung versehen sind. Weitere Informationen finden Sie unter [Support für externe Benutzer und beschriftete Inhalte](sensitivity-labels-office-apps.md#support-for-external-users-and-labeled-content).

- Office 365 eDiscovery unterstützt die Volltextsuche für diese Dateien und DLP-Richtlinien (Data Loss Prevention) unterstützen Inhalte in diesen Dateien.

> [!NOTE]
> Wenn die Verschlüsselung mit einem lokalen Schlüssel (eine wichtige Verwaltungstopologie, die häufig als "eigenen Schlüssel halten" oder "Hyok" bezeichnet wird) oder mithilfe der [Doppelschlüssel Verschlüsselung](double-key-encryption.md)angewendet wurde, ändert sich das SharePoint-Verhalten bei der Verarbeitung des Dateiinhalts nicht.
>
> Das SharePoint-Verhalten ändert sich auch nicht für vorhandene Dateien in SharePoint, die mit einer Verschlüsselung mit einem einzelnen Azure-basierten Schlüssel gekennzeichnet sind. Damit diese Dateien von den neuen Funktionen profitieren, nachdem Sie Vertraulichkeits Bezeichnungen für Office-Dateien in SharePoint und OneDrive aktiviert haben, müssen die Dateien entweder heruntergeladen und erneut hochgeladen oder bearbeitet werden. Sie werden dann beispielsweise in Such-und eDiscovery-Ergebnissen zurückgegeben.

Nachdem Sie Sensitivitäts Bezeichnungen für Office-Dateien in SharePoint und OneDrive aktiviert haben, stehen drei neue [Überwachungsereignisse](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) für die Überwachung von Sensitivitäts Bezeichnungen zur Verfügung, die auf Dokumente in SharePoint und OneDrive angewendet werden:

- **Vertraulichkeitsbezeichnung wurde auf Datei angewendet**
- **Auf Datei angewendete Vertraulichkeitsbezeichnung wurde geändert**
- **Vertraulichkeitsbezeichnung wurde von Datei entfernt**

Sehen Sie sich das folgende Video (kein Audio) an, um die neuen Funktionen in Aktion anzuzeigen:

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

Sie haben immer die Wahl, um Vertraulichkeits Bezeichnungen für Office-Dateien in SharePoint und OneDrive ([Opt-out](#how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out) zu jeder Zeit zu deaktivieren.

Wenn Sie Dokumente in SharePoint derzeit mithilfe von SharePoint Information Rights Management (IRM) schützen, müssen Sie den Abschnitt [SharePoint Information Rights Management (IRM) and Sensitivity Labels](#sharepoint-information-rights-management-irm-and-sensitivity-labels) auf dieser Seite überprüfen.

## <a name="requirements"></a>Anforderungen

Diese neuen Funktionen funktionieren nur mit [Vertraulichkeits Bezeichnungen](sensitivity-labels.md) . Wenn Sie derzeit über Azure Information Protection-Bezeichnungen verfügen, migrieren Sie Sie zunächst zu Sensitivitäts Bezeichnungen, sodass Sie diese Funktionen für neue Dateien, die Sie hochladen, aktivieren können. Anweisungen finden Sie unter [How to migrate Azure Information Protection Labels to Unified Sensitivity Labels](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)

Verwenden Sie die OneDrive-Synchronisierungs-App-Version 19.002.0121.0008 oder höher unter Windows und Version 19.002.0107.0008 oder höher unter Mac. Beide Versionen wurden am 28. Januar 2019 veröffentlicht und sind derzeit für alle Ringe freigegeben. Weitere Informationen finden Sie in den [Anmerkungen zur OneDrive-Version](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0). Nachdem Sie Sensitivitäts Bezeichnungen für Office-Dateien in SharePoint und OneDrive aktiviert haben, werden Benutzer, die eine ältere Version der Synchronisierungs-app ausführen, aufgefordert, Sie zu aktualisieren.

## <a name="limitations"></a>Einschränkungen

- SharePoint wendet keine Vertraulichkeits Bezeichnungen automatisch auf vorhandene Dateien an, die Sie bereits mithilfe von Azure Information Protection-Bezeichnungen verschlüsselt haben. Führen Sie diese Aufgaben stattdessen aus, damit die Funktionen nach dem Aktivieren von Sensitivitäts Bezeichnungen für Office-Dateien in SharePoint und OneDrive funktionieren:

    1. Stellen Sie sicher, dass Sie [die Azure Information Protection-Bezeichnungen](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels) zu Sensitivitäts Bezeichnungen migriert und diese im Microsoft 365 Compliance Center oder in einer entsprechenden Bezeichnungs Verwaltungskonsole [veröffentlicht](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) haben.

    2. Laden Sie die Dateien herunter, und laden Sie Sie dann in SharePoint hoch.

- In SharePoint können keine verschlüsselten Dateien verarbeitet werden, wenn die Bezeichnung, auf die die Verschlüsselung angewendet wird, eine der folgenden [Konfigurationen für die Verschlüsselung](encryption-sensitivity-labels.md#configure-encryption-settings)aufweist:

  - **Zulassen, dass Benutzerberechtigungen zuweisen, wenn Sie die Bezeichnung anwenden** , und das Kontrollkästchen für **in Word, PowerPoint und Excel fordern Sie Benutzer zur Angabe von Berechtigungen aufgefordert** wird ausgewählt ist. Diese Einstellung wird manchmal auch als "benutzerdefinierte Berechtigungen" bezeichnet.
  - Der **Benutzer Zugriff auf Inhalts Ablauf** wird auf einen anderen Wert als **Never**festgelegt.
  - Die **Verschlüsselung mit doppeltem Schlüssel** wird ausgewählt.

  Bei Beschriftungen mit einer dieser Verschlüsselungs Konfigurationen werden die Bezeichnungen nicht für Benutzer in Office im Internet angezeigt. Darüber hinaus können die neuen Funktionen nicht mit beschrifteten Dokumenten verwendet werden, die bereits über diese Verschlüsselungseinstellungen verfügen. Beispielsweise werden diese Dokumente nicht in den Suchergebnissen zurückgegeben, auch wenn Sie aktualisiert werden.

- Für ein verschlüsseltes Dokument, das Bearbeitungsberechtigungen für einen Benutzer gewährt, kann das Kopieren in den Webversionen der Office-Apps nicht blockiert werden.

- Die Dokument Verfolgungs Website für Azure Information Protection wird nicht unterstützt.

- Office-Desktop-Apps und-Mobile Apps unterstützen nicht die gemeinsame Dokumenterstellung für Dateien, die mit Verschlüsselung gekennzeichnet sind. Diese apps öffnen weiterhin beschriftete und verschlüsselte Dateien im exklusiven Bearbeitungsmodus.

- Wenn ein Administratoreinstellungen für eine veröffentlichte Bezeichnung ändert, die bereits auf Dateien angewendet wurde, die auf den synchronisierungsclient der Benutzer heruntergeladen wurden, können Benutzer möglicherweise die an der Datei vorgenommenen Änderungen in Ihrem OneDrive-synchronisierungsordner nicht speichern. Dieses Szenario bezieht sich auf Dateien, die mit Verschlüsselung versehen sind, und auch dann, wenn die Bezeichnungs Änderung von einer Bezeichnung stammt, die die Verschlüsselung nicht auf eine Bezeichnung angewendet hat, die die Verschlüsselung verwendet. Benutzer sehen einen [roten Kreis mit einem weißen Kreuz Symbol Fehler](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3), und Sie werden aufgefordert, neue Änderungen als separate Kopie zu speichern. Stattdessen können Sie die Datei schließen und erneut öffnen oder Office im Internet verwenden.

- Wenn ein beschriftetes Dokument in SharePoint hochgeladen wird und die Bezeichnung angewandte Verschlüsselung mithilfe eines Kontos aus einem Dienstprinzipalnamen verwendet wird, kann das Dokument nicht in Office im Internet geöffnet werden. Zu den Beispielszenarien zählen Microsoft Cloud-App-Sicherheit und eine Datei, die per e-Mail an Teams gesendet wird.

- Benutzer können Speicherprobleme nach dem Wechseln in den Standbymodus oder in einen Ruhemodus haben, wenn anstelle von Office für das Internet der Desktop und der Mobile Apps für Word, Excel oder PowerPoint verwendet werden. Wenn diese Benutzer Ihre Office-App-Sitzung fortsetzen und versuchen, Änderungen zu speichern, wird eine Fehlermeldung zum hochladen angezeigt, in der Sie eine Kopie speichern können, anstatt die Originaldatei zu speichern.

- Dokumente, die auf folgende Weise verschlüsselt wurden, können nicht in Office im Internet geöffnet werden:

  - Verschlüsselung, die einen lokalen Schlüssel verwendet ("eigenen Schlüssel halten" oder Hyok)
  - Verschlüsselung, die mithilfe der [Doppelschlüssel Verschlüsselung](double-key-encryption.md) angewendet wurde
  - Verschlüsselung, die unabhängig von einer Bezeichnung angewendet wurde, beispielsweisedurch direkte Anwendung einer Vorlage zum Schutz von Rechteverwaltung.

- Wenn Sie eine Bezeichnung löschen, die auf ein Dokument in SharePoint angewendet wurde, anstatt die Beschriftung aus der entsprechenden Bezeichnungsrichtlinie zu entfernen, wird das Dokument beim Herunterladen nicht mit einer Bezeichnung versehen oder verschlüsselt. Im Vergleich dazu bleibt das Dokument verschlüsselt, wenn das beschriftete Dokument außerhalb von SharePoint gespeichert wird, wenn die Bezeichnung gelöscht wird. Beachten Sie, dass Sie zwar während einer Testphase Beschriftungen löschen können, es aber sehr selten ist, eine Bezeichnung in einer Produktionsumgebung zu löschen.

## <a name="how-to-enable-sensitivity-labels-for-sharepoint-and-onedrive-opt-in"></a>Aktivieren von Sensitivitäts Bezeichnungen für SharePoint und OneDrive (Opt-in)

Sie können die neuen Funktionen mithilfe des Microsoft 365 Compliance Center oder mithilfe von PowerShell aktivieren.

### <a name="use-the-compliance-center-to-enable-support-for-sensitivity-labels"></a>Aktivieren der Unterstützung für Vertraulichkeits Bezeichnungen mithilfe des Compliance Centers

Diese Option ist die einfachste Möglichkeit, um Vertraulichkeits Bezeichnungen für SharePoint und OneDrive zu aktivieren.

Der globale Administrator für Ihre Organisation verfügt über vollständige Berechtigungen zum Erstellen und Verwalten aller Aspekte von Vertraulichkeitsbezeichnungen. Wenn Sie sich nicht als globaler Administrator anmelden, lesen Sie [Zum Erstellen und Verwalten von Vertraulichkeitsbezeichnungen erforderliche Berechtigungen](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels).

1. Melden Sie sich beim [Microsoft 365 Compliance Center](https://compliance.microsoft.com/)an, und navigieren Sie zu **Lösungs**  >  **Informationsschutz**

    Wenn diese Option nicht sofort angezeigt wird, wählen Sie zunächst **Alle anzeigen** aus.

2. Wenn eine Meldung angezeigt wird, um die Möglichkeit zum Verarbeiten von Inhalt in Office Online-Dateien zu aktivieren, wählen Sie **jetzt aktivieren**aus:

    ![Schaltfläche "jetzt aktivieren", um Sensitivitäts Bezeichnungen für Office Online zu aktivieren](../media/sensitivity-labels-turn-on-banner.png)

    Der Befehl wird sofort ausgeführt, und wenn die Seite als nächstes aktualisiert wird, wird die Nachricht oder Schaltfläche nicht mehr angezeigt.

> [!NOTE]
> Wenn Sie über Microsoft 365 Multi-Geo verfügen, müssen Sie PowerShell verwenden, um diese Funktionen für alle geografischen Standorte zu aktivieren. Ausführliche Informationen finden Sie im nächsten Abschnitt.

### <a name="use-powershell-to-enable-support-for-sensitivity-labels"></a>Verwenden von PowerShell zum Aktivieren der Unterstützung für Vertraulichkeits Bezeichnungen

Als Alternative zur Verwendung des Compliance Centers können Sie die Unterstützung für Sensitivitäts Bezeichnungen mithilfe des Cmdlets " [SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) " aus SharePoint Online PowerShell aktivieren.

Wenn Sie über Microsoft 365 Multi-Geo verfügen, müssen Sie PowerShell verwenden, um diese Unterstützung für alle geografischen Standorte zu aktivieren.

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

1. Stellen Sie eine Verbindung mit SharePoint her, indem Sie ein Arbeits-oder Schulkonto mit globalen Administrator-oder SharePoint-Administratorrechten in Microsoft 365 verwenden. Eine Anleitung dazu finden Sie unter [Erste Schritte mit der Microsoft Office SharePoint Online-Verwaltungsshell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

    Hinweis: Wenn Sie über Microsoft 365 Multi-Geo verfügen, verwenden Sie den Parameter-URL mit [Connect-SPOService](https://docs.microsoft.com/powershell/module/sharepoint-online/connect-sposervice?view=sharepoint-ps), und geben Sie die Website-URL SharePoint Online Administration Center für einen ihrer geografischen Standorte an.

2. Führen Sie den folgenden Befehl aus, und drücken Sie **Y** , um Folgendes zu bestätigen:

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true
    ```

3. Für Microsoft 365 Multi-Geo: Wiederholen Sie die Schritte 1 und 2 für jeden ihrer verbleibenden geografischen Standorte.

## <a name="publishing-and-changing-sensitivity-labels"></a>Veröffentlichen und Ändern von Vertraulichkeits Bezeichnungen

Beachten Sie beim Verwenden von Sensitivitäts Bezeichnungen mit SharePoint und OneDrive, dass Sie die Replikationszeit bei der Veröffentlichung neuer Sensitivitäts Bezeichnungen oder beim Aktualisieren vorhandener Sensitivitäts Bezeichnungen berücksichtigen müssen. Dies ist besonders wichtig für neue Bezeichnungen, die die Verschlüsselung anwenden.

Beispiel: Sie erstellen und veröffentlichen eine neue Sensitivitäts Bezeichnung, die die Verschlüsselung anwendet, und Sie wird sehr schnell in der Desktop-App eines Benutzers angezeigt. Der Benutzer wendet diese Bezeichnung auf ein Dokument an und lädt diese dann in SharePoint oder OneDrive hoch. Wenn die Bezeichnungs Replikation für den Dienst nicht abgeschlossen wurde, werden die neuen Funktionen nicht auf das Dokument beim Hochladen angewendet. Das Dokument wird daher nicht in der Suche oder für eDiscovery zurückgegeben, und das Dokument kann nicht in Office für das Internet geöffnet werden.

- Die folgenden Änderungen werden innerhalb einer Stunde repliziert: neue und gelöschte Vertraulichkeits Bezeichnungen und Richtlinieneinstellungen für Sensitivitäts Bezeichnungen, die angeben, welche Bezeichnungen in der Richtlinie enthalten sind.

- Die folgenden Änderungen werden innerhalb von 24 Stunden repliziert: Änderungen an Einstellungen für die Sensitivitäts Bezeichnung für vorhandene Bezeichnungen.

Da die Replikationsverzögerung jetzt nur eine Stunde für neue Sensitivitäts Bezeichnungen ist, wird das Szenario in dem Beispiel wahrscheinlich nicht ausgeführt. Als Schutz wird jedoch empfohlen, neue Bezeichnungen zunächst nur für einige Testbenutzer zu veröffentlichen, eine Stunde zu warten und dann das Bezeichnungs Verhalten in SharePoint und OneDrive zu überprüfen. Als letzten Schritt stellen Sie die Bezeichnung für mehr Benutzer zur Verfügung, indem Sie entweder der vorhandenen Bezeichnungsrichtlinie mehr Benutzer hinzufügen oder die Bezeichnung einer vorhandenen Bezeichnungsrichtlinie für Ihre Standardbenutzer hinzufügen. Wenn die Standardbenutzer die Bezeichnung sehen, wurde Sie bereits mit SharePoint und OneDrive synchronisiert.

## <a name="sharepoint-information-rights-management-irm-and-sensitivity-labels"></a>SharePoint-Informationsrechteverwaltung (IRM) und Vertraulichkeits Bezeichnungen

[SharePoint Information Rights Management (IRM)](set-up-irm-in-sp-admin-center.md) ist eine ältere Technologie zum Schutz von Dateien auf Listen-und Bibliotheksebene, indem beim Herunterladen von Dateien Verschlüsselung und Einschränkungen angewendet werden. Diese ältere Schutztechnologie wurde entwickelt, um zu verhindern, dass nicht autorisierte Benutzer die Datei öffnen, während Sie sich außerhalb von SharePoint befinden.

Im Vergleich dazu bieten Sensitivitäts Beschriftungen zusätzlich zur Verschlüsselung die Schutzeinstellungen von visuellen Markierungen (Kopfzeilen, Fußzeilen, Wasserzeichen). Die Verschlüsselungseinstellungen unterstützen die gesamte Palette an [Nutzungsrechten](https://docs.microsoft.com/azure/information-protection/configure-usage-rights) , um zu beschränken, was Benutzer mit dem Inhalt tun können, und die gleichen Vertraulichkeits Bezeichnungen werden für [viele Szenarien](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels)unterstützt. Durch die Verwendung derselben Schutzmethode mit konsistenten Einstellungen für Arbeitslasten und apps ergibt sich eine konsistente Schutzstrategie.

Sie können jedoch beide Protection-Lösungen zusammen verwenden, und das Verhalten lautet wie folgt:

- Wenn Sie eine Datei mit einer Vertraulichkeits Bezeichnung hochladen, die die Verschlüsselung anwendet, kann SharePoint diese Datei nicht verarbeiten, sodass die gemeinsame Erstellung, eDiscovery, DLP und Suche für diese Datei nicht funktionieren.

- Wenn Sie eine Datei mit Office im Internet bezeichnen, werden alle Verschlüsselungseinstellungen von der Bezeichnung erzwungen. Für diese Dateien werden die gemeinsame Dokumenterstellung, eDiscovery, DLP und die Suche unterstützt.

- Wenn Sie eine Datei herunterladen, die mit Office im Internet gekennzeichnet ist, wird die Bezeichnung beibehalten, und alle Verschlüsselungseinstellungen von der Bezeichnung werden anstelle der IRM-Einschränkungseinstellungen erzwungen.

- Wenn Sie eine Office-oder PDF-Datei herunterladen, die nicht mit einer Vertraulichkeits Bezeichnung verschlüsselt wurde, werden IRM-Einstellungen angewendet.

- Wenn Sie eine der zusätzlichen IRM-Bibliothekseinstellungen aktiviert haben, die verhindern, dass Benutzer Dokumente hochladen können, die IRM nicht unterstützen, werden diese Einstellungen erzwungen.

Mit diesem Verhalten können Sie sicher sein, dass alle Office-und PDF-Dateien vor nicht autorisiertem Zugriff geschützt werden, wenn Sie heruntergeladen werden, auch wenn Sie nicht mit einer Bezeichnung versehen sind. Beschriftete Dateien, die hochgeladen werden, profitieren jedoch nicht von den neuen Funktionen.

## <a name="search-for-documents-by-sensitivity-label"></a>Suchen nach Dokumenten nach Sensitivitäts Bezeichnung

Verwenden Sie die verwaltete Eigenschaft **InformationProtectionLabelId** , um nach allen Dokumenten in SharePoint oder OneDrive zu suchen, die eine bestimmte Vertraulichkeits Bezeichnung aufweisen. Verwenden Sie die folgende Syntax: `InformationProtectionLabelId:<GUID>`

Um beispielsweise nach allen Dokumenten zu suchen, die als "vertraulich" bezeichnet wurden und diese Bezeichnung eine GUID von "8faca7b8-8d20-48a3-8ea2-0f96310a848e" aufweist, geben Sie Folgendes im Suchfeld ein:

`InformationProtectionLabelId: 8faca7b8-8d20-48a3-8ea2-0f96310a848e`

Verwenden Sie das [Get-Label-](https://docs.microsoft.com/powershell/module/exchange/get-label?view=exchange-ps) Cmdlet, um die GUIDs für Ihre Vertraulichkeits Bezeichnungen abzurufen:

1. Stellen Sie [zunächst eine Verbindung mit Office 365 Security & Compliance Center PowerShell her](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

    Melden Sie sich beispielsweise in einer PowerShell-Sitzung, die Sie als Administrator ausführen, mit einem globalen Administratorkonto an.

2. Führen Sie dann den folgenden Befehl aus:

    ```powershell
    Get-Label |ft Name, Guid
    ```

Weitere Informationen zur Verwendung von verwalteten Eigenschaften finden Sie unter [Verwalten des Suchschemas in SharePoint](https://docs.microsoft.com/sharepoint/manage-search-schema).

## <a name="how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out"></a>Deaktivieren von Sensitivitäts Bezeichnungen für SharePoint und OneDrive (Opt-out)

Wenn Sie diese neuen Funktionen deaktivieren, werden Dateien, die Sie nach dem Aktivieren von Sensitivitäts Bezeichnungen für SharePoint und OneDrive hochgeladen haben, weiterhin durch die Bezeichnung geschützt, da die Beschriftungseinstellungen weiterhin erzwungen werden. Wenn Sie Sensitivitäts Bezeichnungen auf neue Dateien anwenden, nachdem Sie diese neuen Funktionen deaktiviert haben, können die Volltextsuche, eDiscovery und die gemeinsame Dokumenterstellung nicht mehr verwendet werden.

Um diese neuen Funktionen zu deaktivieren, müssen Sie PowerShell verwenden. Verwenden Sie die SharePoint Online [-](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) Verwaltungsshell und das Cmdlet "SPOTenant", und geben Sie den gleichen *EnableAIPIntegration* -Parameter wie im Abschnitt [Verwenden von PowerShell zum Aktivieren der Unterstützung für Sensitivitäts Bezeichnungen](#use-powershell-to-enable-support-for-sensitivity-labels) beschrieben an. Legen Sie dieses Mal den Parameterwert auf false fest, und drücken Sie **Y** , um Folgendes zu bestätigen:

```PowerShell
Set-SPOTenant -EnableAIPIntegration $false
```

Wenn Sie über Microsoft 365 Multi-Geo verfügen, müssen Sie diesen Befehl für jeden ihrer geografischen Standorte ausführen.

## <a name="next-steps"></a>Weitere Schritte

Nachdem Sie die Sensitivitäts Bezeichnungen für Office-Dateien in SharePoint und OneDrive aktiviert haben, sollten Sie diese Dateien automatisch mithilfe von Richtlinien mit automatischer Benennung bezeichnen. Weitere Informationen finden Sie unter [Anwenden einer Vertraulichkeits Bezeichnung auf Inhalte automatisch](apply-sensitivity-label-automatically.md).
