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
description: Administratoren können die Unterstützung von Vertraulichkeitsbezeichnungen für Word-, Excel- und PowerPoint dateien in SharePoint und OneDrive aktivieren.
ms.openlocfilehash: 695084443ee10de87f091d358b63fad079e03093
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861515"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive"></a>Aktivieren von Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Aktivieren Sie Vertraulichkeitsbezeichnungen für Office Dateien in SharePoint und OneDrive, damit Benutzer Ihre [Vertraulichkeitsbezeichnungen](sensitivity-labels.md) in Office für das Web anwenden können. Wenn dieses Feature aktiviert ist, wird benutzern die Schaltfläche **"Vertraulichkeit"** auf dem Menüband angezeigt, sodass sie Bezeichnungen anwenden können, und alle angewendeten Bezeichnungsnamen werden auf der Statusleiste angezeigt.

Das Aktivieren dieses Features führt auch dazu, dass SharePoint und OneDrive den Inhalt von Dateien verarbeiten können, die mithilfe einer Vertraulichkeitsbezeichnung verschlüsselt wurden. Die Bezeichnung kann in Office für das Web oder in Office Desktop-Apps angewendet und in SharePoint und OneDrive hochgeladen oder gespeichert werden. Bis Sie dieses Feature aktivieren, können diese Dienste verschlüsselte Dateien nicht verarbeiten, was bedeutet, dass die gemeinsame Dokumenterstellung, eDiscovery, Verhinderung von Datenverlust, Suche und andere Features für die Zusammenarbeit für diese Dateien nicht funktionieren.

Nachdem Sie Vertraulichkeitsbezeichnungen für Office Dateien in SharePoint und OneDrive aktiviert haben, für neue und geänderte Dateien mit einer Vertraulichkeitsbezeichnung, die Verschlüsselung mit einem cloudbasierten Schlüssel anwendet (und keine [Doppelschlüsselverschlüsselung](double-key-encryption.md)verwendet):

- Für Word-, Excel- und PowerPoint-Dateien SharePoint und OneDrive die Bezeichnung erkennen und können nun den Inhalt der verschlüsselten Datei verarbeiten.

- Wenn Benutzer diese Dateien von SharePoint oder OneDrive herunterladen oder darauf zugreifen, werden die Vertraulichkeitsbezeichnung und alle Verschlüsselungseinstellungen aus der Bezeichnung erzwungen und verbleiben bei der Datei, unabhängig davon, wo sie gespeichert ist. Stellen Sie sicher, dass Sie Anleitungen für Benutzer bereitstellen, um nur Bezeichnungen zum Schutz von Dokumenten zu verwenden. Weitere Informationen finden Sie unter [IRM-Optionen (Information Rights Management) und Vertraulichkeitsbezeichnungen.](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels)

- Wenn Benutzer mit Bezeichnungen versehene und verschlüsselte Dateien in SharePoint oder OneDrive hochladen, müssen sie mindestens über Anzeigerechte für diese Dateien verfügen. Beispielsweise können sie die Dateien außerhalb SharePoint öffnen. Wenn sie nicht über dieses Mindestnutzungsrecht verfügen, ist der Upload erfolgreich, aber der Dienst erkennt die Bezeichnung nicht und kann den Dateiinhalt nicht verarbeiten.

- Verwenden Sie Office für das Web (Word, Excel, PowerPoint), um Office Dateien mit Vertraulichkeitsbezeichnungen zu öffnen und zu bearbeiten, die Verschlüsselung anwenden. Die Berechtigungen, die der Verschlüsselung zugewiesen wurden, werden erzwungen. Sie können auch die [automatische Bezeichnung](apply-sensitivity-label-automatically.md) für diese Dokumente verwenden.

- Externe Benutzer können mithilfe von Gastkonten auf Dokumente zugreifen, die mit Verschlüsselung gekennzeichnet sind. Weitere Informationen finden Sie unter [Support für externe Benutzer und mit Bezeichnungen versehene Inhalte.](sensitivity-labels-office-apps.md#support-for-external-users-and-labeled-content) 

- Office 365 eDiscovery unterstützt die Volltextsuche für diese Dateien, und DLP-Richtlinien (Data Loss Prevention, Verhinderung von Datenverlust) unterstützen Inhalte in diesen Dateien.

> [!NOTE]
> Wenn die Verschlüsselung mit einem lokalen Schlüssel (einer Schlüsselverwaltungstopologie, die häufig als "Hold Your Own Key" oder HYOK bezeichnet wird) oder mithilfe der [Doppelschlüsselverschlüsselung](double-key-encryption.md)angewendet wurde, ändert sich das Dienstverhalten für die Verarbeitung der Dateiinhalte nicht. Für diese Dateien funktionieren also coauthoring, eDiscovery, Verhinderung von Datenverlust, Suche und andere Features für die Zusammenarbeit nicht.
>
> Das Verhalten SharePoint und OneDrive ändert sich auch nicht für vorhandene Dateien an diesen Speicherorten, die mithilfe eines einzelnen Azure-basierten Schlüssels mit Verschlüsselung gekennzeichnet sind. Damit diese Dateien von den neuen Funktionen profitieren können, nachdem Sie Vertraulichkeitsbezeichnungen für Office Dateien in SharePoint und OneDrive aktiviert haben, müssen die Dateien entweder heruntergeladen und erneut hochgeladen oder bearbeitet werden.

Nachdem Sie Vertraulichkeitsbezeichnungen für Office Dateien in SharePoint und OneDrive aktiviert haben, stehen drei neue [Überwachungsereignisse](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) für die Überwachung von Vertraulichkeitsbezeichnungen zur Verfügung, die auf Dokumente in SharePoint und OneDrive angewendet werden:
- **Vertraulichkeitsbezeichnung wurde auf Datei angewendet**
- **Auf Datei angewendete Vertraulichkeitsbezeichnung wurde geändert**
- **Vertraulichkeitsbezeichnung wurde von Datei entfernt**

Sehen Sie sich das folgende Video (kein Audio) an, um die neuen Funktionen in Aktion zu sehen:

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

Sie haben immer die Wahl, Vertraulichkeitsbezeichnungen für Office Dateien in SharePoint und OneDrive ([Opt-Out](#how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out)) jederzeit zu deaktivieren.

Wenn Sie derzeit Dokumente in SharePoint mithilfe von SharePoint Information Rights Management (IRM) schützen, sollten Sie den Abschnitt SharePoint Verwaltung von [Informationsrechten (Information Rights Management, IRM) und Vertraulichkeitsbezeichnungen](#sharepoint-information-rights-management-irm-and-sensitivity-labels) auf dieser Seite überprüfen. 

## <a name="requirements"></a>Anforderungen

Diese neuen Funktionen funktionieren nur mit [Vertraulichkeitsbezeichnungen.](sensitivity-labels.md) Wenn Sie derzeit über Azure Information Protection-Bezeichnungen verfügen, migrieren Sie sie zuerst zu Vertraulichkeitsbezeichnungen, damit Sie diese Features für neue Dateien aktivieren können, die Sie hochladen. Anleitungen dazu finden Sie unter [So migrieren Sie Azure Information Protection-Bezeichnungen zu einheitlichen Vertraulichkeitsbezeichnungen](/azure/information-protection/configure-policy-migrate-labels).

Verwenden Sie die OneDrive Synchronisierungs-App Version 19.002.0121.0008 oder höher auf Windows und Version 19.002.0107.0008 oder höher auf Mac. Beide Versionen wurden am 28. Januar 2019 veröffentlicht und werden derzeit für alle Ringe veröffentlicht. Weitere Informationen finden Sie in den [Versionshinweisen OneDrive.](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0) Nachdem Sie Vertraulichkeitsbezeichnungen für Office Dateien in SharePoint und OneDrive aktiviert haben, werden Benutzer, die eine ältere Version der Synchronisierungs-App ausführen, aufgefordert, sie zu aktualisieren.

## <a name="limitations"></a>Einschränkungen

- SharePoint und OneDrive können einige Dateien, die von Office Desktop-Apps bezeichnet und verschlüsselt sind, nicht verarbeiten, wenn diese Dateien PowerQuery-Daten, von benutzerdefinierten Add-Ins gespeicherte Daten oder benutzerdefinierte XML-Komponenten wie Deckblatteigenschaften, Inhaltstypschemas, benutzerdefinierten Dokumentinformationsbereich und benutzerdefinierte xsn enthalten. Diese Einschränkung gilt auch für Dateien, denen beim Hochladen eine [Dokument-ID](https://support.microsoft.com/office/enable-and-configure-unique-document-ids-ea7fee86-bd6f-4cc8-9365-8086e794c984) hinzugefügt wurde.
    
    Wenden Sie für diese Dateien entweder eine Bezeichnung ohne Verschlüsselung an, damit sie später in Office im Web geöffnet werden können, oder weisen Sie die Benutzer an, die Dateien in ihren Desktop-Apps zu öffnen. Dateien, die nur in Office im Web bezeichnet und verschlüsselt sind, sind davon nicht betroffen.

- SharePoint und OneDrive werden vertraulichkeitsbezeichnungen nicht automatisch auf vorhandene Dateien angewendet, die Sie bereits mithilfe von Azure Information Protection-Bezeichnungen verschlüsselt haben. Damit die Features funktionieren, nachdem Sie Vertraulichkeitsbezeichnungen für Office Dateien in SharePoint und OneDrive aktiviert haben, führen Sie stattdessen die folgenden Aufgaben aus:
    
    1. Stellen Sie sicher, dass Sie [die Azure Information Protection-Bezeichnungen](/azure/information-protection/configure-policy-migrate-labels) zu Vertraulichkeitsbezeichnungen migriert und aus dem Microsoft 365 Compliance Center [veröffentlicht](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) haben.
    2. Laden Sie die bezeichneten Dateien herunter, und laden Sie sie dann an ihren ursprünglichen Speicherort in SharePoint oder OneDrive hoch.

- SharePoint und OneDrive können verschlüsselte Dateien nicht verarbeiten, wenn die Bezeichnung, die die Verschlüsselung angewendet hat, eine der folgenden [Konfigurationen für](encryption-sensitivity-labels.md#configure-encryption-settings)die Verschlüsselung aufweist:
    - **Benutzer können Berechtigungen zuweisen, wenn sie die Bezeichnung anwenden** und das Kontrollkästchen **In Word, PowerPoint und Excel Benutzer auffordern, Berechtigungen anzugeben** ausgewählt ist. Diese Einstellung wird manchmal als "benutzerdefinierte Berechtigungen" bezeichnet.
    - **Benutzerzugriff auf Inhalte läuft ab** ist auf einen anderen Wert als **Nie** eingestellt.
    - **Verschlüsselung mit Doppelschlüssel** ist ausgewählt.
    
    Bei Bezeichnungen mit einer dieser Verschlüsselungskonfigurationen werden die Bezeichnungen benutzern in Office für das Web nicht angezeigt. Darüber hinaus können die neuen Funktionen nicht mit beschrifteten Dokumenten verwendet werden, die bereits über diese Verschlüsselungseinstellungen verfügen. Beispielsweise werden diese Dokumente nicht in suchergebnissen zurückgegeben, auch wenn sie aktualisiert werden.

- Wenn Sie ein Dokument hochladen oder in SharePoint speichern und die Bezeichnung der Datei keine Verschlüsselung anwendet, kann es aus Leistungsgründen eine Weile dauern, bis der Bezeichnungsname in der **Vertraulichkeitsspalte** in der Dokumentbibliothek angezeigt wird. Berücksichtigen Sie diese Verzögerung, wenn Sie Skripts oder Automatisierung verwenden, die vom Bezeichnungsnamen in dieser Spalte abhängen.

- Im folgenden Szenario "Speichern unter" kann es zu Verzögerungen beim Öffnen verschlüsselter Dokumente kommen: Bei Verwendung einer Desktopversion von Office wählt ein Benutzer "Speichern unter" für ein Dokument mit einer Vertraulichkeitsbezeichnung aus, die Verschlüsselung anwendet. Der Benutzer wählt SharePoint oder OneDrive für den Speicherort aus und versucht dann sofort, dieses Dokument in Office für das Web zu öffnen. Wenn der Dienst die Verschlüsselung noch verarbeitet, wird dem Benutzer eine Meldung angezeigt, dass das Dokument in seiner Desktop-App geöffnet werden muss. Wenn sie es innerhalb weniger Minuten erneut versuchen, wird das Dokument erfolgreich in Office für das Web geöffnet. 

- Bei verschlüsselten Dokumenten wird das Drucken nicht unterstützt.

- Bei einem verschlüsselten Dokument, das einem Benutzer Bearbeitungsberechtigungen gewährt, kann das Kopieren in den Webversionen der Office Apps nicht blockiert werden.

- Standardmäßig unterstützen Office Desktop-Apps und mobile Apps die gemeinsame Erstellung von Dateien, die mit Verschlüsselung gekennzeichnet sind, nicht. Diese Apps öffnen weiterhin mit Bezeichnungen versehene und verschlüsselte Dateien im exklusiven Bearbeitungsmodus.
    
    > [!NOTE]
    > Die gemeinsame Dokumenterstellung wird jetzt in der Vorschau unterstützt. Weitere Informationen finden Sie unter [Aktivieren der gemeinsamen Dokumenterstellung für Dateien, die mit Vertraulichkeitsbezeichnungen verschlüsselt sind.](sensitivity-labels-coauthoring.md)

- Wenn ein Administrator die Einstellungen für eine veröffentlichte Bezeichnung ändert, die bereits auf Dateien angewendet wurde, die auf den Synchronisierungsclient des Benutzers heruntergeladen wurden, können Benutzer möglicherweise keine Änderungen an der Datei in ihrem OneDrive Synchronisierungsordner speichern. Dieses Szenario gilt für Dateien, die mit Verschlüsselung gekennzeichnet sind, und auch, wenn sich die Bezeichnung von einer Bezeichnung ändert, die keine Verschlüsselung angewendet hat, auf eine Bezeichnung, die Verschlüsselung anwendet. Benutzern wird ein [roter Kreis mit einem weißen Kreuzsymbol angezeigt,](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)und sie werden aufgefordert, neue Änderungen als separate Kopie zu speichern. Stattdessen können sie die Datei schließen und erneut öffnen oder Office für das Web verwenden.

- Wenn ein bezeichnetes Dokument in SharePoint oder OneDrive hochgeladen wird und die Bezeichnung Verschlüsselung mithilfe eines Kontos aus einem Dienstprinzipalnamen angewendet hat, kann das Dokument nicht in Office für das Web geöffnet werden. Beispielszenarien sind Microsoft Cloud App Security und eine Datei, die per E-Mail an Teams gesendet wird.

- Bei Benutzern können Speicherprobleme auftreten, nachdem sie in den Offlinemodus oder in den Ruhezustand versetzt wurden, wenn sie nicht Office für das Web verwenden, sondern die Desktop- und mobilen Apps für Word, Excel oder PowerPoint verwenden. Wenn diese Benutzer ihre Office-App Sitzung fortsetzen und versuchen, Änderungen zu speichern, wird eine Uploadfehlermeldung mit einer Option zum Speichern einer Kopie angezeigt, anstatt die Originaldatei zu speichern. 

- Dokumente, die auf folgende Weise verschlüsselt wurden, können nicht in Office für das Web geöffnet werden:
    - Verschlüsselung, die einen lokalen Schlüssel verwendet ("Haltet Ihren eigenen Schlüssel" oder HYOK)
    - Verschlüsselung, die mithilfe der [Doppelschlüsselverschlüsselung](double-key-encryption.md) angewendet wurde
    - Verschlüsselung, die unabhängig von einer Bezeichnung angewendet wurde, z. B. durch direktes Anwenden einer Vorlage für den Rechteverwaltungsschutz.

- Bezeichnungen, die für andere Sprachen konfiguriert [sind,](create-sensitivity-labels.md#additional-label-settings-with-security--compliance-center-powershell) werden nicht unterstützt und zeigen nur die Originalsprache an.

- Bildschirmaufnahmen können für verschlüsselte Dokumente nicht verhindert werden. Weitere Informationen finden Sie unter ["Können Rechteverwaltung Bildschirmaufnahmen verhindern?"](/azure/information-protection/faqs-rms#can-rights-management-prevent-screen-captures)

- Wenn Sie eine Bezeichnung löschen, die auf ein Dokument in SharePoint oder OneDrive angewendet wurde, anstatt die Bezeichnung aus der entsprechenden Bezeichnungsrichtlinie zu entfernen, wird das heruntergeladene Dokument nicht mit Bezeichnungen versehen oder verschlüsselt. Im Vergleich dazu bleibt das Dokument verschlüsselt, wenn das bezeichnete Dokument außerhalb SharePoint oder OneDrive gespeichert wird, wenn die Bezeichnung gelöscht wird. Beachten Sie, dass es sehr selten ist, bezeichnungen in einer Produktionsumgebung zu löschen, obwohl Sie Bezeichnungen während einer Testphase löschen können.

## <a name="how-to-enable-sensitivity-labels-for-sharepoint-and-onedrive-opt-in"></a>Aktivieren von Vertraulichkeitsbezeichnungen für SharePoint und OneDrive (Opt-In)

Sie können die neuen Funktionen mithilfe des Microsoft 365 Compliance Centers oder mithilfe von PowerShell aktivieren. Wie bei allen Konfigurationsänderungen auf Mandantenebene für SharePoint und OneDrive dauert es etwa 15 Minuten, bis die Änderung wirksam wird.

### <a name="use-the-compliance-center-to-enable-support-for-sensitivity-labels"></a>Verwenden des Compliance Centers zum Aktivieren der Unterstützung für Vertraulichkeitsbezeichnungen

Diese Option ist die einfachste Möglichkeit, Vertraulichkeitsbezeichnungen für SharePoint und OneDrive zu aktivieren. Sie müssen sich jedoch als globaler Administrator für Ihren Mandanten anmelden.

1. Melden Sie sich beim [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) als globaler Administrator an, und navigieren Sie zum Lösungsinformationsschutz.  >  
    
    Wenn diese Option nicht sofort angezeigt wird, wählen Sie zunächst **Alle anzeigen** aus. 

2. Wenn eine Meldung angezeigt wird, um die Möglichkeit zum Verarbeiten von Inhalten in Office Onlinedateien zu aktivieren, wählen Sie **"Jetzt aktivieren"** aus:
    
    ![Schaltfläche "Jetzt aktivieren", um Vertraulichkeitsbezeichnungen für Office Online zu aktivieren](../media/sensitivity-labels-turn-on-banner.png)
    
    Der Befehl wird sofort ausgeführt, und wenn die Seite als Nächstes aktualisiert wird, wird die Nachricht oder Schaltfläche nicht mehr angezeigt.

> [!NOTE]
> Wenn Sie über Microsoft 365 Multi-Geo verfügen, müssen Sie PowerShell verwenden, um diese Funktionen für alle Ihre geografischen Standorte zu aktivieren. Ausführliche Informationen finden Sie im nächsten Abschnitt.

### <a name="use-powershell-to-enable-support-for-sensitivity-labels"></a>Verwenden von PowerShell zum Aktivieren der Unterstützung von Vertraulichkeitsbezeichnungen

Als Alternative zur Verwendung des Compliance Centers können Sie die Unterstützung für Vertraulichkeitsbezeichnungen mithilfe des [Cmdlets "Set-SPOTenant"](/powershell/module/sharepoint-online/set-spotenant) aus SharePoint Online PowerShell aktivieren. 

Wenn Sie über Microsoft 365 Multi-Geo verfügen, müssen Sie PowerShell verwenden, um diese Unterstützung für alle Ihre geografischen Standorte zu aktivieren.

#### <a name="prepare-the-sharepoint-online-management-shell"></a>Vorbereiten der SharePoint Onlineverwaltungsshell

Bevor Sie den PowerShell-Befehl ausführen, um Vertraulichkeitsbezeichnungen für Office Dateien in SharePoint und OneDrive zu aktivieren, stellen Sie sicher, dass Sie SharePoint Version 16.0.19418.12000 oder höher der Online-Verwaltungsshell ausführen. Wenn Sie bereits über die neueste Version verfügen, können Sie zum [nächsten Verfahren](#run-the-powershell-command-to-enable-support-for-sensitivity-labels) übergehen, um den PowerShell-Befehl auszuführen.

1. Wenn Sie eine frühere Version der SharePoint-Online-Verwaltungsshell aus dem PowerShell-Katalog installiert haben, können Sie das Modul aktualisieren, indem Sie das folgende Cmdlet ausführen.

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. Wenn Sie eine frühere Version der SharePoint Online-Verwaltungsshell aus dem Microsoft Download Center installiert haben, können Sie auch zum **Hinzufügen oder Entfernen** von Programmen wechseln und die SharePoint Online-Verwaltungsshell deinstallieren.

3. Wechseln Sie in einem Webbrowser zur Download Center-Seite, und [laden Sie die neueste SharePoint Online-Verwaltungsshell herunter](https://go.microsoft.com/fwlink/p/?LinkId=255251).

4. Wählen Sie die gewünschte Sprache aus, und klicken Sie auf **Download**.

5. Wählen Sie zwischen der x64- und der x86-Version der MSI-Datei aus. Laden Sie die x64-Datei herunter, wenn Sie die 64-Bit-Version von Windows oder die x86-Datei ausführen, wenn Sie die 32-Bit-Version ausführen. Wenn Sie dies nicht wissen, sehen Sie [sich an, welche Version von Windows Betriebssystem ausgeführt wird?](https://support.microsoft.com/help/13443/windows-which-operating-system)

6. Nachdem Sie die Datei heruntergeladen haben, führen Sie die Datei aus, und führen Sie die Schritte im Setup-Assistenten aus.

#### <a name="run-the-powershell-command-to-enable-support-for-sensitivity-labels"></a>Führen Sie den PowerShell-Befehl aus, um die Unterstützung für Vertraulichkeitsbezeichnungen zu aktivieren.

Verwenden Sie zum Aktivieren der neuen Funktionen das Cmdlet ["Set-SPOTenant"](/powershell/module/sharepoint-online/set-spotenant) mit dem *Parameter "EnableAIPIntegration":*

1. Stellen Sie unter Verwendung eines Geschäfts-, Schul- oder Unikontos, das über globale Administratorrechte oder SharePoint Administratorrechte in Microsoft 365 verfügt, eine Verbindung mit SharePoint her. Eine Anleitung dazu finden Sie unter [Erste Schritte mit der Microsoft Office SharePoint Online-Verwaltungsshell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
    
    > [!NOTE]
    > Wenn Sie über Microsoft 365 Multi-Geo verfügen, verwenden Sie den Parameter -Url mit [Verbinden-SPOService,](/powershell/module/sharepoint-online/connect-sposervice)und geben Sie die Website-URL SharePoint Online Administration Center für einen Ihrer geografischen Standorte an.

2. Führen Sie den folgenden Befehl aus, und drücken Sie **Y,** um dies zu bestätigen:

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true
    ```
3. Für Microsoft 365 Multi-Geo: Wiederholen Sie die Schritte 1 und 2 für jeden ihrer verbleibenden geografischen Standorte.

## <a name="publishing-and-changing-sensitivity-labels"></a>Veröffentlichen und Ändern von Vertraulichkeitsbezeichnungen

Wenn Sie Vertraulichkeitsbezeichnungen mit SharePoint und OneDrive verwenden, denken Sie daran, dass Sie replikationszeit zulassen müssen, wenn Sie neue Vertraulichkeitsbezeichnungen veröffentlichen oder vorhandene Vertraulichkeitsbezeichnungen aktualisieren. Dies ist besonders wichtig für neue Bezeichnungen, die Verschlüsselung anwenden.

Beispiel: Sie erstellen und veröffentlichen eine neue Vertraulichkeitsbezeichnung, die Verschlüsselung anwendet und sehr schnell in der Desktop-App eines Benutzers angezeigt wird. Der Benutzer wendet diese Bezeichnung auf ein Dokument an und lädt es dann in SharePoint oder OneDrive hoch. Wenn die Bezeichnungsreplikation für den Dienst noch nicht abgeschlossen wurde, werden die neuen Funktionen beim Hochladen nicht auf dieses Dokument angewendet. Daher wird das Dokument nicht in der Suche oder für eDiscovery zurückgegeben, und das Dokument kann nicht in Office für das Web geöffnet werden.  

Die folgenden Änderungen werden innerhalb einer Stunde repliziert: Neue und gelöschte Vertraulichkeitsbezeichnungen und Richtlinieneinstellungen für Vertraulichkeitsbezeichnungen, die angeben, welche Bezeichnungen in der Richtlinie enthalten sind.

Die folgenden Änderungen werden innerhalb von 24 Stunden repliziert: Änderungen an Den Einstellungen für Vertraulichkeitsbezeichnungen für vorhandene Bezeichnungen.

Da die Replikationsverzögerung für neue Vertraulichkeitsbezeichnungen nur eine Stunde beträgt, ist es unwahrscheinlich, dass das Szenario im Beispiel auftritt. Als Schutz empfehlen wir jedoch, neue Bezeichnungen zuerst für einige Testbenutzer zu veröffentlichen, eine Stunde zu warten und dann das Bezeichnungsverhalten auf SharePoint und OneDrive zu überprüfen. Stellen Sie als letzten Schritt die Bezeichnung für mehr Benutzer zur Verfügung, indem Sie entweder der vorhandenen Bezeichnungsrichtlinie weitere Benutzer hinzufügen oder die Bezeichnung einer vorhandenen Bezeichnungsrichtlinie für Ihre Standardbenutzer hinzufügen. Zu dem Zeitpunkt, zu dem die Standardbenutzer die Bezeichnung sehen, wurde sie bereits mit SharePoint und OneDrive synchronisiert.

## <a name="sharepoint-information-rights-management-irm-and-sensitivity-labels"></a>SharePoint Verwaltung von Informationsrechten (Information Rights Management, IRM) und Vertraulichkeitsbezeichnungen

[SharePoint Information Rights Management (IRM)](set-up-irm-in-sp-admin-center.md) ist eine ältere Technologie zum Schutz von Dateien auf Listen- und Bibliotheksebene, indem Verschlüsselung und Einschränkungen angewendet werden, wenn Dateien heruntergeladen werden. Diese ältere Schutztechnologie soll verhindern, dass nicht autorisierte Benutzer die Datei öffnen, während sie sich außerhalb SharePoint befindet.

Im Vergleich dazu stellen Vertraulichkeitsbezeichnungen zusätzlich zur Verschlüsselung die Schutzeinstellungen visueller Markierungen (Kopfzeilen, Fußzeilen, Wasserzeichen) bereit. Die Verschlüsselungseinstellungen unterstützen die gesamte Palette von [Nutzungsrechten,](/azure/information-protection/configure-usage-rights) um einzuschränken, was Benutzer mit den Inhalten tun können, und die gleichen Vertraulichkeitsbezeichnungen werden in [vielen Szenarien](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels)unterstützt. Die Verwendung der gleichen Schutzmethode mit konsistenten Einstellungen für Workloads und Apps führt zu einer konsistenten Schutzstrategie.

Sie können jedoch beide Schutzlösungen gemeinsam verwenden, und das Verhalten sieht wie folgt aus: 

- Wenn Sie eine Datei mit einer Vertraulichkeitsbezeichnung hochladen, die Verschlüsselung anwendet, können SharePoint den Inhalt dieser Dateien nicht verarbeiten, sodass die gemeinsame Dokumenterstellung, eDiscovery, DLP und Suche für diese Dateien nicht unterstützt werden.

- Wenn Sie eine Datei mit Office für das Web bezeichnen, werden alle Verschlüsselungseinstellungen der Bezeichnung erzwungen. Für diese Dateien werden gemeinsame Dokumenterstellung, eDiscovery, DLP und Suche unterstützt.

- Wenn Sie eine Datei herunterladen, die mithilfe von Office für das Web bezeichnet wird, wird die Bezeichnung beibehalten, und alle Verschlüsselungseinstellungen aus der Bezeichnung werden anstelle der IRM-Einschränkungseinstellungen erzwungen.

- Wenn Sie eine Office- oder PDF-Datei herunterladen, die nicht mit einer Vertraulichkeitsbezeichnung verschlüsselt ist, werden IRM-Einstellungen angewendet.

- Wenn Sie eine der zusätzlichen IRM-Bibliothekseinstellungen aktiviert haben, die u. a. verhindern, dass Benutzer Dokumente hochladen, die IRM nicht unterstützen, werden diese Einstellungen erzwungen.

Mit diesem Verhalten können Sie sicher sein, dass alle Office und PDF-Dateien vor unbefugtem Zugriff geschützt sind, wenn sie heruntergeladen werden, auch wenn sie nicht mit Bezeichnungen versehen sind. Mit Bezeichnungen versehene Dateien, die hochgeladen werden, profitieren jedoch nicht von den neuen Funktionen.


## <a name="search-for-documents-by-sensitivity-label"></a>Suchen nach Dokumenten nach Vertraulichkeitsbezeichnung

Verwenden Sie die verwaltete Eigenschaft **InformationProtectionLabelId,** um alle Dokumente in SharePoint oder OneDrive zu suchen, die über eine bestimmte Vertraulichkeitsbezeichnung verfügen. Verwenden Sie die folgende Syntax: `InformationProtectionLabelId:<GUID>`

Wenn Sie beispielsweise nach allen Dokumenten suchen möchten, die als "Vertraulich" bezeichnet wurden und diese Bezeichnung die GUID "8faca7b8-8d20-48a3-8ea2-0f96310a848e" aufweist, geben Sie im Suchfeld Folgendes ein:

```
InformationProtectionLabelId:8faca7b8-8d20-48a3-8ea2-0f96310a848e
```

Die Suche findet keine bezeichneten Dokumente in einer komprimierten Datei, z. B. einer .zip Datei.

Verwenden Sie das Cmdlet ["Get-Label",](/powershell/module/exchange/get-label) um die GUIDs für Ihre Vertraulichkeitsbezeichnungen abzurufen:    

1. Stellen Sie [zunächst eine Verbindung mit Office 365 Security & Compliance Center PowerShell her](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell). 
   
    Melden Sie sich beispielsweise in einer PowerShell-Sitzung, die Sie als Administrator ausführen, mit einem globalen Administratorkonto an.    

2. Führen Sie dann den folgenden Befehl aus:  

    ```powershell   
    Get-Label |ft Name, Guid    
    ``` 

Weitere Informationen zur Verwendung von verwalteten Eigenschaften finden Sie unter [Verwalten des Suchschemas in SharePoint](/sharepoint/manage-search-schema).

## <a name="remove-encryption-for-a-labeled-document"></a>Entfernen der Verschlüsselung für ein bezeichnetes Dokument

Es kann in seltenen Fällen vorkommen, dass ein SharePoint Administrator die Verschlüsselung aus einem in SharePoint gespeicherten Dokument entfernen muss. Jeder Benutzer, dem das [Rechteverwaltungsnutzungsrecht](/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) "Export" oder "Vollzugriff" für dieses Dokument zugewiesen ist, kann die Verschlüsselung entfernen, die vom Azure Rights Management-Dienst aus Azure Information Protection angewendet wurde. Beispielsweise können Benutzer mit einem dieser Nutzungsrechte eine Bezeichnung ersetzen, die Verschlüsselung durch eine Bezeichnung ohne Verschlüsselung anwendet. Alternativ kann ein [Superbenutzer](/azure/information-protection/configure-super-users) die Datei herunterladen und eine lokale Kopie ohne die Verschlüsselung speichern.

Alternativ kann ein globaler Administrator oder [SharePoint Administrator](/sharepoint/sharepoint-admin-role) das Cmdlet [Unlock-SPOSensitivityLabelEncryptedFile](/powershell/module/sharepoint-online/unlock-sposensitivitylabelencryptedFile) ausführen, das sowohl die Vertraulichkeitsbezeichnung als auch die Verschlüsselung entfernt. Dieses Cmdlet wird auch ausgeführt, wenn der Administrator keine Zugriffsberechtigungen für die Website oder Datei hat oder wenn der Azure Rights Management-Dienst nicht verfügbar ist. 

Beispiel:

```powershell
Unlock-SPOSensitivityLabelEncryptedFile -FileUrl "https://contoso.com/sites/Marketing/Shared Documents/Doc1.docx" -JustificationText "Need to decrypt this file"
```

Anforderungen:

- SharePoint Online-Verwaltungsshell, Version 16.0.20616.12000 oder höher.

- Die Verschlüsselung wurde durch eine Vertraulichkeitsbezeichnung mit vom Administrator definierten Verschlüsselungseinstellungen angewendet (die Einstellungen zum Zuweisen von [Berechtigungen jetzt](encryption-sensitivity-labels.md#assign-permissions-now) Bezeichnungen). [Die Doppelschlüsselverschlüsselung](encryption-sensitivity-labels.md#double-key-encryption) wird für dieses Cmdlet nicht unterstützt.

Der Begründungstext wird dem [Überwachungsereignis](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) **"Vertraulichkeitsbezeichnung aus Datei entfernt"** hinzugefügt, und die Entschlüsselungsaktion wird auch in der [Schutznutzungsprotokollierung für Azure Information Protection](/azure/information-protection/log-analyze-usage)aufgezeichnet.

## <a name="how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out"></a>So deaktivieren Sie Vertraulichkeitsbezeichnungen für SharePoint und OneDrive (Abmelden)

Wenn Sie diese neuen Funktionen deaktivieren, werden Dateien, die Sie hochgeladen haben, nachdem Sie Vertraulichkeitsbezeichnungen für SharePoint aktiviert haben, und OneDrive weiterhin durch die Bezeichnung geschützt, da die Bezeichnungseinstellungen weiterhin erzwungen werden. Wenn Sie vertraulichkeitsbezeichnungen auf neue Dateien anwenden, nachdem Sie diese neuen Funktionen deaktiviert haben, funktioniert die Volltextsuche, eDiscovery und gemeinsame Dokumenterstellung nicht mehr.

Um diese neuen Funktionen zu deaktivieren, müssen Sie PowerShell verwenden. Geben Sie mithilfe der SharePoint Online-Verwaltungsshell und des Cmdlets ["Set-SPOTenant"](/powershell/module/sharepoint-online/set-spotenant) denselben *EnableAIPIntegration-Parameter* an, wie im Abschnitt ["Verwenden von PowerShell zum Aktivieren der Unterstützung für Vertraulichkeitsbezeichnungen"](#use-powershell-to-enable-support-for-sensitivity-labels) beschrieben. Legen Sie den Parameterwert dieses Mal jedoch auf "false" fest, und drücken **Sie Y,** um folgendes zu bestätigen:

```PowerShell
Set-SPOTenant -EnableAIPIntegration $false
```

Wenn Sie über Microsoft 365 Multi-Geo verfügen, müssen Sie diesen Befehl für jeden Geografischen Standort ausführen.

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie Vertraulichkeitsbezeichnungen für Office Dateien in SharePoint und OneDrive aktiviert haben, sollten Sie erwägen, diese Dateien automatisch mithilfe von Richtlinien für die automatische Bezeichnung zu bezeichnen. Weitere Informationen finden Sie unter [Automatisches Anwenden einer Vertraulichkeitsbezeichnung auf Inhalte.](apply-sensitivity-label-automatically.md)

Müssen Sie Ihre gekennzeichneten und verschlüsselten Dokumente mit Personen außerhalb Ihrer Organisation teilen?  Informationen hierzu finden Sie unter [Teilen verschlüsselter Dokumente mit externen Benutzern](sensitivity-labels-office-apps.md#sharing-encrypted-documents-with-external-users).
