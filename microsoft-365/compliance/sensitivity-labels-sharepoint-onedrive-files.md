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
description: Administratoren können die Unterstützung von Vertraulichkeitsbezeichnungen für Word-, Excel- und PowerPoint in SharePoint und OneDrive.
ms.openlocfilehash: f610e04a9115b7654332bcc1f479144b4d100618
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311928"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive"></a>Aktivieren von Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

> [!NOTE]
> Es gibt ein aktuelles Problem, das dazu führt, dass gekennzeichnete und verschlüsselte Dateien nicht in einem Office im Web:
>
> Während wir ein Problem im Zusammenhang mit bestimmten Dokumenteigenschaften untersuchen, können Sie nicht viele Dateien in Office im Web. Für diese Dateien können Sie sie weiterhin in Ihren Desktop- und mobilen Apps öffnen und Office bearbeiten. Gehen Sie auch wie folgt vor:
>
> 1. Öffnen Sie die Datei in Office Desktop-App.
> 2. Entfernen Sie die Bezeichnung, für die die Verschlüsselung angewendet wird.
> 3. Speichern Sie die Datei am ursprünglichen Speicherort (SharePoint oder OneDrive), und schließen Sie die Desktop-App.
> 4. Öffnen Sie die Datei in Office im Web, und verwenden Sie die ursprüngliche Bezeichnung, die die Verschlüsselung angewendet hat, erneut.
> 
> Dateien, die nur in einem Office im Web erstellt und bearbeitet werden, sind nicht betroffen.

Aktivieren Sie Vertraulichkeitsbezeichnungen für Office Dateien in SharePoint und OneDrive, damit Benutzer Ihre Vertraulichkeitsbezeichnungen [in](sensitivity-labels.md) Office web anwenden können. Wenn dieses Feature aktiviert ist,  wird den Benutzern die Schaltfläche Vertraulichkeit auf dem Menüband angezeigt, damit sie Bezeichnungen anwenden und einen beliebigen angewendeten Bezeichnungsnamen auf der Statusleiste sehen können.

Wenn Sie dieses Feature aktivieren, können SharePoint und OneDrive inhalte von Dateien verarbeiten, die mithilfe einer Vertraulichkeitsbezeichnung verschlüsselt wurden. Die Bezeichnung kann in Office für das Web oder in Office Desktop-Apps angewendet und in SharePoint und OneDrive. Bis Sie dieses Feature aktivieren, können diese Dienste keine verschlüsselten Dateien verarbeiten, was bedeutet, dass die gemeinsame Dokumentierung, eDiscovery, Verhinderung von Datenverlust, die Suche und andere funktionen für die Zusammenarbeit für diese Dateien nicht funktionieren.

Nachdem Sie Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive aktiviert haben, für neue und geänderte Dateien mit einer Vertraulichkeitsbezeichnung, die die Verschlüsselung mit einem cloudbasierten Schlüssel an wendet (und keine Doppelschlüsselverschlüsselung [verwendet):](double-key-encryption.md)

- Für Word-, Excel- und PowerPoint-Dateien erkennen SharePoint und OneDrive die Bezeichnung und können nun den Inhalt der verschlüsselten Datei verarbeiten.

- Wenn Benutzer diese Dateien von SharePoint oder OneDrive herunterladen oder darauf zugreifen, werden die Vertraulichkeitsbezeichnung und alle Verschlüsselungseinstellungen aus der Bezeichnung erzwungen und verbleiben bei der Datei, unabhängig davon, wo sie gespeichert wird. Stellen Sie sicher, dass Sie Benutzerleitfäden bereitstellen, um nur Bezeichnungen zum Schutz von Dokumenten zu verwenden. Weitere Informationen finden Sie unter [Information Rights Management (IRM)-Optionen und Vertraulichkeitsbezeichnungen](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels).

- Wenn Benutzer gekennzeichnete und verschlüsselte Dateien in SharePoint oder OneDrive hochladen, müssen sie mindestens über Anzeigerechte für diese Dateien verfügen. Sie können z. B. die Dateien außerhalb der SharePoint. Wenn sie nicht über dieses Mindestnutzungsrecht verfügen, ist der Upload erfolgreich, aber der Dienst erkennt die Bezeichnung nicht und kann den Dateiinhalt nicht verarbeiten.

- Verwenden Office für das Web (Word, Excel, PowerPoint) zum Öffnen und Bearbeiten Office Dateien mit Vertraulichkeitsbezeichnungen, die Verschlüsselung anwenden. Die berechtigungen, die mit der Verschlüsselung zugewiesen wurden, werden erzwungen. Sie können auch [die automatische Bezeichnung für](apply-sensitivity-label-automatically.md) diese Dokumente verwenden.

- Externe Benutzer können mithilfe von Gastkonten auf Dokumente zugreifen, die mit Verschlüsselung gekennzeichnet sind. Weitere Informationen finden Sie unter [Support for external users and labeled content](sensitivity-labels-office-apps.md#support-for-external-users-and-labeled-content). 

- Office 365 eDiscovery unterstützt die Volltextsuche für diese Dateien, und Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) unterstützen Inhalte in diesen Dateien.

> [!NOTE]
> Wenn die Verschlüsselung mit einem lokalen Schlüssel angewendet wurde (eine Schlüsselverwaltungstopologie, die häufig als "eigenen Schlüssel" oder HYOK bezeichnet wird) oder mithilfe der Double [Key Encryption](double-key-encryption.md), ändert sich das Dienstverhalten für die Verarbeitung des Dateiinhalts nicht. Für diese Dateien funktioniert die Gemeinsame Dokumentierung, eDiscovery, Verhinderung von Datenverlust, Suche und andere funktionen für die Zusammenarbeit also nicht.
>
> Das SharePoint und OneDrive verhalten ändert sich auch nicht für vorhandene Dateien an diesen Speicherorten, die mithilfe eines einzelnen Azure-basierten Schlüssels mit Verschlüsselung gekennzeichnet sind. Damit diese Dateien von den neuen Funktionen profitieren, nachdem Sie Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive aktiviert haben, müssen die Dateien entweder erneut heruntergeladen und hochgeladen oder bearbeitet werden.

Nachdem Sie Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive aktiviert [](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) haben, stehen drei neue Überwachungsereignisse zur Überwachung von Vertraulichkeitsbezeichnungen zur Verfügung, die auf Dokumente in SharePoint und OneDrive:
- **Vertraulichkeitsbezeichnung wurde auf Datei angewendet**
- **Auf Datei angewendete Vertraulichkeitsbezeichnung wurde geändert**
- **Vertraulichkeitsbezeichnung wurde von Datei entfernt**

Sehen Sie sich das folgende Video (kein Audio) an, um die neuen Funktionen in Aktion zu sehen:

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

Sie haben immer die Wahl, Vertraulichkeitsbezeichnungen für Office dateien in SharePoint und OneDrive ([Opt-out](#how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out)) jederzeit zu deaktivieren.

Wenn Sie Dokumente derzeit in SharePoint mithilfe von SharePoint Information Rights Management (IRM) schützen, überprüfen Sie unbedingt den Abschnitt [SharePoint Information Rights Management (IRM)](#sharepoint-information-rights-management-irm-and-sensitivity-labels) und Vertraulichkeitsbezeichnungen auf dieser Seite. 

## <a name="requirements"></a>Anforderungen

Diese neuen Funktionen funktionieren nur mit [Vertraulichkeitsbezeichnungen.](sensitivity-labels.md) Wenn Sie derzeit über Azure Information Protection-Bezeichnungen verfügen, migrieren Sie sie zunächst zu Vertraulichkeitsbezeichnungen, damit Sie diese Features für neue Dateien aktivieren können, die Sie hochladen. Anleitungen dazu finden Sie unter [So migrieren Sie Azure Information Protection-Bezeichnungen zu einheitlichen Vertraulichkeitsbezeichnungen](/azure/information-protection/configure-policy-migrate-labels).

Verwenden Sie die OneDrive Synchronisierungs-App, Version 19.002.0121.0008 oder höher auf Windows und Version 19.002.0107.0008 oder höher auf dem Mac. Beide Versionen wurden am 28. Januar 2019 veröffentlicht und sind derzeit für alle Ringe freigegeben. Weitere Informationen finden Sie unter [OneDrive Versionshinweise .](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0) Nachdem Sie Vertraulichkeitsbezeichnungen für Office Dateien in SharePoint und OneDrive aktiviert haben, werden Benutzer, die eine ältere Version der Synchronisierungs-App ausführen, aufgefordert, sie zu aktualisieren.

## <a name="limitations"></a>Einschränkungen

- SharePoint und OneDrive nicht automatisch Vertraulichkeitsbezeichnungen auf vorhandene Dateien anwenden, die Sie bereits mit Azure Information Protection-Bezeichnungen verschlüsselt haben. Damit die Features funktionieren, nachdem Sie Vertraulichkeitsbezeichnungen für Office dateien in SharePoint und OneDrive aktiviert haben, führen Sie stattdessen die folgenden Aufgaben aus:
    
    1. Stellen Sie sicher, dass Sie die Azure [](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) [Information Protection-Bezeichnungen](/azure/information-protection/configure-policy-migrate-labels) zu Vertraulichkeitsbezeichnungen migriert und aus dem Microsoft 365 Compliance Center oder dem entsprechenden Labeling Admin Center veröffentlicht haben.
    2. Laden Sie die Dateien herunter, und laden Sie sie dann in SharePoint.

- SharePoint und OneDrive können verschlüsselte Dateien nicht verarbeiten, wenn die Bezeichnung, die die Verschlüsselung angewendet hat, über eine der folgenden Konfigurationen [für die Verschlüsselung verfügt:](encryption-sensitivity-labels.md#configure-encryption-settings)
    - **Benutzer können Berechtigungen zuweisen, wenn sie die Bezeichnung anwenden** und das Kontrollkästchen **In Word, PowerPoint und Excel Benutzer auffordern, Berechtigungen anzugeben** ausgewählt ist. Diese Einstellung wird manchmal als "benutzerdefinierte Berechtigungen" bezeichnet.
    - **Benutzerzugriff auf Inhalte läuft ab** ist auf einen anderen Wert als **Nie** eingestellt.
    - **Verschlüsselung mit Doppelschlüssel** ist ausgewählt.
    
    Bei Bezeichnungen mit einer dieser Verschlüsselungskonfigurationen werden die Bezeichnungen benutzern in Office Web nicht angezeigt. Darüber hinaus können die neuen Funktionen nicht mit mit Bezeichnungen versehenen Dokumenten verwendet werden, die bereits über diese Verschlüsselungseinstellungen verfügen. Beispielsweise werden diese Dokumente nicht in Suchergebnissen zurückgegeben, auch wenn sie aktualisiert werden.

- Im folgenden Szenario "Speichern unter" kann es zu Verzögerungen beim Öffnen verschlüsselter Dokumente kommen: Unter Verwendung einer Desktopversion von Office wählt ein Benutzer Speichern unter für ein Dokument mit einer Vertraulichkeitsbezeichnung aus, die verschlüsselungs gilt. Der Benutzer wählt SharePoint oder OneDrive für den Speicherort aus und versucht dann sofort, dieses Dokument im Office für das Web zu öffnen. Wenn der Dienst die Verschlüsselung weiterhin verarbeitet, wird dem Benutzer eine Meldung angezeigt, dass das Dokument in seiner Desktop-App geöffnet werden muss. Wenn sie es in ein paar Minuten erneut versuchen, wird das Dokument erfolgreich Office für das Web geöffnet. 

- Bei verschlüsselten Dokumenten wird das Drucken nicht unterstützt.

- Bei einem verschlüsselten Dokument, das einem Benutzer Bearbeitungsberechtigungen erteilt, kann das Kopieren nicht in den Webversionen der Office werden.

- Standardmäßig unterstützen Office Desktop-Apps und mobilen Apps die gemeinsamen Erstellung von Dateien, die mit Verschlüsselung gekennzeichnet sind, nicht. Diese Apps öffnen weiterhin mit Bezeichnungen versehene und verschlüsselte Dateien im exklusiven Bearbeitungsmodus.
    
    > [!NOTE]
    > Die co-authoring wird jetzt in der Vorschau unterstützt. Weitere Informationen finden Sie unter Aktivieren der gemeinsamen Erstellung von [Dateien, die mit Vertraulichkeitsbezeichnungen verschlüsselt sind.](sensitivity-labels-coauthoring.md)

- Wenn ein Administrator Einstellungen für eine veröffentlichte Bezeichnung ändert, die bereits auf Dateien angewendet wird, die auf den Synchronisierungsclient der Benutzer heruntergeladen wurden, können Benutzer änderungen, die sie an der Datei vornehmen, möglicherweise nicht in ihrem ordner OneDrive speichern. Dieses Szenario gilt für Dateien, die mit Verschlüsselung gekennzeichnet sind, und auch, wenn die Bezeichnungsänderung von einer Bezeichnung ist, die keine Verschlüsselung auf eine Bezeichnung angewendet hat, die Verschlüsselung angewendet hat. Benutzern wird ein [roter Kreis mit einem Weißkreuzsymbolfehler](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)angezeigt, und sie werden aufgefordert, neue Änderungen als separate Kopie zu speichern. Stattdessen können sie die Datei schließen und erneut öffnen oder Office für das Web verwenden.

- Wenn ein mit Bezeichnungen versehenes Dokument in SharePoint oder OneDrive hochgeladen wird und die Bezeichnung verschlüsselungs angewendet wird, indem ein Konto aus einem Dienstprinzipalnamen verwendet wird, kann das Dokument nicht in Office für das Web geöffnet werden. Beispielszenarien sind Microsoft Cloud App Security und eine Datei, die per E-Mail an Teams gesendet wird.

- Benutzer können Probleme beim Speichern nach dem Offlinemodus oder im Ruhemodus auftreten, wenn sie anstelle von Office für das Web die Desktop- und mobilen Apps für Word, Excel oder PowerPoint. Wenn diese Benutzer ihre Office-App fortsetzen und versuchen, Änderungen zu speichern, wird eine Uploadfehlermeldung mit der Option angezeigt, eine Kopie zu speichern, anstatt die originale Datei zu speichern. 

- Dokumente, die auf folgende Weise verschlüsselt wurden, können nicht Office für das Web geöffnet werden:
    - Verschlüsselung, die einen lokalen Schlüssel verwendet ("eigenen Schlüssel halten" oder HYOK)
    - Verschlüsselung, die mithilfe der [Doppelschlüsselverschlüsselung angewendet wurde](double-key-encryption.md)
    - Verschlüsselung, die unabhängig von einer Bezeichnung angewendet wurde, z. B. durch direktes Anwenden einer Vorlage zum Schutz der Rechteverwaltung.

- Bezeichnungen, die für [andere Sprachen](create-sensitivity-labels.md#additional-label-settings-with-security--compliance-center-powershell) konfiguriert sind, werden nicht unterstützt und zeigen nur die ursprüngliche Sprache an.

- Bildschirmaufzeichnungen können für verschlüsselte Dokumente nicht verhindert werden. Weitere Informationen finden Sie unter [Can Rights Management prevent screen captures?](/azure/information-protection/faqs-rms#can-rights-management-prevent-screen-captures)

- Wenn Sie eine Bezeichnung löschen, die auf ein Dokument in SharePoint oder OneDrive angewendet wurde, anstatt die Bezeichnung aus der entsprechenden Bezeichnungsrichtlinie zu entfernen, wird das heruntergeladene Dokument nicht mit Bezeichnungen oder Verschlüsselten versehen. Im Vergleich dazu bleibt das Dokument verschlüsselt, wenn es außerhalb SharePoint oder OneDrive gespeichert wird, wenn die Bezeichnung gelöscht wird. Beachten Sie, dass bezeichnungen zwar während einer Testphase gelöscht werden können, es jedoch sehr selten ist, eine Bezeichnung in einer Produktionsumgebung zu löschen.

## <a name="how-to-enable-sensitivity-labels-for-sharepoint-and-onedrive-opt-in"></a>Aktivieren von Vertraulichkeitsbezeichnungen für SharePoint und OneDrive (Opt-In)

Sie können die neuen Funktionen mithilfe des compliance center Microsoft 365 oder mithilfe von PowerShell aktivieren. Wie bei allen Konfigurationsänderungen auf Mandantenebene für SharePoint und OneDrive dauert es etwa 15 Minuten, bis die Änderung wirksam wird.

### <a name="use-the-compliance-center-to-enable-support-for-sensitivity-labels"></a>Verwenden des Compliance Centers zum Aktivieren der Unterstützung für Vertraulichkeitsbezeichnungen

Diese Option ist die einfachste Möglichkeit, Vertraulichkeitsbezeichnungen für SharePoint und OneDrive zu aktivieren. Sie müssen sich jedoch als globaler Administrator für Ihren Mandanten anmelden.

1. Melden Sie sich beim [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) als globaler Administrator an, und navigieren Sie zu **Lösungsinformationsschutz**  >  
    
    Wenn diese Option nicht sofort angezeigt wird, wählen Sie zunächst **Alle anzeigen** aus. 

2. Wenn eine Meldung angezeigt wird, um die Möglichkeit zum Verarbeiten von Inhalten in Office zu aktivieren, wählen Sie **Jetzt aktivieren aus:**
    
    ![Aktivieren der Schaltfläche jetzt, um Vertraulichkeitsbezeichnungen für Office Online zu aktivieren](../media/sensitivity-labels-turn-on-banner.png)
    
    Der Befehl wird sofort ausgeführt, und wenn die Seite das nächste Mal aktualisiert wird, wird die Nachricht oder Schaltfläche nicht mehr angezeigt.

> [!NOTE]
> Wenn Sie über Microsoft 365 Multi-Geo verfügen, müssen Sie PowerShell verwenden, um diese Funktionen für alle Geografischen Standorte zu aktivieren. Ausführliche Informationen finden Sie im nächsten Abschnitt.

### <a name="use-powershell-to-enable-support-for-sensitivity-labels"></a>Verwenden von PowerShell zum Aktivieren der Unterstützung für Vertraulichkeitsbezeichnungen

Als Alternative zur Verwendung des Compliance Centers können Sie die Unterstützung für Vertraulichkeitsbezeichnungen mithilfe des [Cmdlets Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) von SharePoint Online PowerShell aktivieren. 

Wenn Sie über Microsoft 365 Multi-Geo verfügen, müssen Sie PowerShell verwenden, um diese Unterstützung für alle Geografischen Standorte zu aktivieren.

#### <a name="prepare-the-sharepoint-online-management-shell"></a>Vorbereiten der SharePoint Onlineverwaltungsshell

Bevor Sie den Befehl PowerShell ausführen, um Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive zu aktivieren, stellen Sie sicher, dass Sie SharePoint Online Management Shell, Version 16.0.19418.12000 oder höher, ausführen. Wenn Sie bereits über die neueste Version verfügen, können Sie mit dem nächsten [Verfahren](#run-the-powershell-command-to-enable-support-for-sensitivity-labels) zum Ausführen des PowerShell-Befehls überspringen.

1. Wenn Sie eine frühere Version der SharePoint-Online-Verwaltungsshell aus dem PowerShell-Katalog installiert haben, können Sie das Modul aktualisieren, indem Sie das folgende Cmdlet ausführen.

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. Wenn Sie eine frühere Version der SharePoint Online-Verwaltungsshell aus dem Microsoft Download  Center installiert haben, können Sie auch zu Hinzufügen oder Entfernen von Programmen wechseln und die SharePoint Online-Verwaltungsshell deinstallieren.

3. Wechseln Sie in einem Webbrowser zur Download Center-Seite, und [laden Sie die neueste SharePoint Online-Verwaltungsshell herunter](https://go.microsoft.com/fwlink/p/?LinkId=255251).

4. Wählen Sie die gewünschte Sprache aus, und klicken Sie auf **Download**.

5. Wählen Sie zwischen der x64- und der x86-Version der MSI-Datei aus. Laden Sie die x64-Datei herunter, wenn Sie die 64-Bit-Version von Windows oder die x86-Datei ausführen, wenn Sie die 32-Bit-Version ausführen. Wenn Sie nicht wissen, welche [Version von Windows Betriebssystem ausgeführt wird?](https://support.microsoft.com/help/13443/windows-which-operating-system)

6. Nachdem Sie die Datei heruntergeladen haben, führen Sie die Datei aus, und führen Sie die Schritte im Setup-Assistenten aus.

#### <a name="run-the-powershell-command-to-enable-support-for-sensitivity-labels"></a>Ausführen des PowerShell-Befehls zum Aktivieren der Unterstützung für Vertraulichkeitsbezeichnungen

Verwenden Sie zum Aktivieren der neuen Funktionen das [Cmdlet Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) mit dem *Parameter EnableAIPIntegration:*

1. Stellen Sie mithilfe eines Arbeits- oder Schulkontos, das über globale Administrator- oder SharePoint Administratorrechte in Microsoft 365 verfügt, eine Verbindung mit SharePoint. Eine Anleitung dazu finden Sie unter [Erste Schritte mit der Microsoft Office SharePoint Online-Verwaltungsshell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
    
   > [!NOTE]
   > Wenn Sie Microsoft 365 Multi-Geo verwendet haben, verwenden Sie den -Url-Parameter mit [Verbinden-SPOService,](/powershell/module/sharepoint-online/connect-sposervice)und geben Sie die Website-URL des SharePoint Online Administration Center für einen Ihrer geografischen Standorte an.

2. Führen Sie den folgenden Befehl aus, und drücken **Sie Y,** um dies zu bestätigen:

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true
    ```
3. For Microsoft 365 Multi-Geo: Repeat steps 1 and 2 for each of your remaining geo-locations.

## <a name="publishing-and-changing-sensitivity-labels"></a>Veröffentlichen und Ändern von Vertraulichkeitsbezeichnungen

Wenn Sie Vertraulichkeitsbezeichnungen mit SharePoint und OneDrive verwenden, müssen Sie die Replikationszeit zulassen, wenn Sie neue Vertraulichkeitsbezeichnungen veröffentlichen oder vorhandene Vertraulichkeitsbezeichnungen aktualisieren. Dies ist besonders wichtig für neue Bezeichnungen, die Verschlüsselung anwenden.

Beispiel: Sie erstellen und veröffentlichen eine neue Vertraulichkeitsbezeichnung, die Verschlüsselung verwendet, und sie wird sehr schnell in der Desktop-App eines Benutzers angezeigt. Der Benutzer wendet diese Bezeichnung auf ein Dokument an und lädt es dann in SharePoint oder OneDrive. Wenn die Bezeichnungsreplikation für den Dienst nicht abgeschlossen ist, werden die neuen Funktionen beim Hochladen nicht auf dieses Dokument angewendet. Aus diesem Grund wird das Dokument nicht in der Suche oder nach eDiscovery zurückgegeben, und das Dokument kann nicht in der Office für das Web geöffnet werden.  

Die folgenden Änderungen werden innerhalb einer Stunde repliziert: Neue und gelöschte Vertraulichkeitsbezeichnungen und Richtlinieneinstellungen für Vertraulichkeitsbezeichnungen, die enthalten, welche Bezeichnungen in der Richtlinie enthalten sind.

Die folgenden Änderungen werden innerhalb von 24 Stunden repliziert: Änderungen an Einstellungen für Vertraulichkeitsbezeichnungen für vorhandene Bezeichnungen.

Da die Replikationsverzögerung für neue Vertraulichkeitsbezeichnungen nur eine Stunde beträgt, wird das Szenario im Beispiel wahrscheinlich nicht ausgeführt. Als Schutz empfehlen wir jedoch, neue Bezeichnungen zuerst für nur wenige Testbenutzer zu veröffentlichen, eine Stunde zu warten und dann das Bezeichnungsverhalten auf SharePoint und OneDrive. Als letzten Schritt können Sie die Bezeichnung für mehr Benutzer verfügbar machen, indem Sie der vorhandenen Bezeichnungsrichtlinie entweder weitere Benutzer hinzufügen oder die Bezeichnung einer vorhandenen Bezeichnungsrichtlinie für Ihre Standardbenutzer hinzufügen. Wenn Die Bezeichnung ihren Standardbenutzern zu sehen ist, wurde sie bereits mit SharePoint und OneDrive.

## <a name="sharepoint-information-rights-management-irm-and-sensitivity-labels"></a>SharePoint Verwaltung von Informationsrechten (Information Rights Management, IRM) und Vertraulichkeitsbezeichnungen

[SharePoint Information Rights Management (IRM)](set-up-irm-in-sp-admin-center.md) ist eine ältere Technologie zum Schutz von Dateien auf Listen- und Bibliotheksebene durch Anwenden von Verschlüsselung und Einschränkungen beim Herunterladen von Dateien. Diese ältere Schutztechnologie soll verhindern, dass nicht autorisierte Benutzer die Datei öffnen, während sie sich außerhalb SharePoint.

Im Vergleich dazu stellen Vertraulichkeitsbezeichnungen neben der Verschlüsselung die Schutzeinstellungen für visuelle Markierungen (Kopfzeilen, Fußzeilen, Wasserzeichen) zur Verfügung. Die Verschlüsselungseinstellungen unterstützen [](/azure/information-protection/configure-usage-rights) den vollständigen Bereich von Verwendungsrechten, um einzuschränken, was Benutzer mit dem Inhalt tun können, und für viele Szenarien werden dieselben Vertraulichkeitsbezeichnungen [unterstützt.](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels) Die Verwendung der gleichen Schutzmethode mit konsistenten Einstellungen in Arbeitslasten und Apps führt zu einer konsistenten Schutzstrategie.

Sie können jedoch beide Schutzlösungen zusammen verwenden, und das Verhalten lautet wie folgt: 

- Wenn Sie eine Datei mit einer Vertraulichkeitsbezeichnung hochladen, die Verschlüsselung angewendet wird, kann SharePoint den Inhalt dieser Dateien nicht verarbeiten, sodass die gemeinsamen Dokumentierungs-, eDiscovery-, DLP- und Suchfunktionsdateien für diese Dateien nicht unterstützt werden.

- Wenn Sie eine Datei mit Office für das Web beschriften, werden alle Verschlüsselungseinstellungen aus der Bezeichnung erzwungen. Für diese Dateien werden coauthoring, eDiscovery, DLP und Search unterstützt.

- Wenn Sie eine Datei herunterladen, die mithilfe von Office für das Web gekennzeichnet ist, wird die Bezeichnung beibehalten, und alle Verschlüsselungseinstellungen aus der Bezeichnung werden anstelle der IRM-Einschränkungseinstellungen erzwungen.

- Wenn Sie eine Office oder PDF-Datei herunterladen, die nicht mit einer Vertraulichkeitsbezeichnung verschlüsselt ist, werden IRM-Einstellungen angewendet.

- Wenn Sie eine der zusätzlichen IRM-Bibliothekseinstellungen aktiviert haben, die u. a. verhindern, dass Benutzer Dokumente hochladen, die IRM nicht unterstützen, werden diese Einstellungen erzwungen.

Mit diesem Verhalten können Sie sicher sein, dass alle Office- und PDF-Dateien vor unbefugtem Zugriff geschützt sind, wenn sie heruntergeladen werden, auch wenn sie nicht beschriftet sind. Hochgeladene Dateien mit Bezeichnungen profitieren jedoch nicht von den neuen Funktionen.


## <a name="search-for-documents-by-sensitivity-label"></a>Suchen nach Dokumenten nach Vertraulichkeitsbezeichnung

Verwenden Sie die verwaltete **Eigenschaft InformationProtectionLabelId,** um alle Dokumente in SharePoint oder OneDrive mit einer bestimmten Vertraulichkeitsbezeichnung zu suchen. Verwenden Sie die folgende Syntax: `InformationProtectionLabelId:<GUID>`

Geben Sie z. B. zum Suchen nach allen Dokumenten, die als "Vertraulich" gekennzeichnet wurden und für diese Bezeichnung die GUID "8faca7b8-8d20-48a3-8ea2-0f96310a848e" angegeben ist, in das Suchfeld ein:

`InformationProtectionLabelId: 8faca7b8-8d20-48a3-8ea2-0f96310a848e`    

Verwenden Sie das [Cmdlet Get-Label,](/powershell/module/exchange/get-label) um die GUIDs für Ihre Vertraulichkeitsbezeichnungen zu erhalten:    

1. Stellen Sie [zunächst eine Verbindung mit Office 365 Security & Compliance Center PowerShell her](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell). 
   
    Melden Sie sich beispielsweise in einer PowerShell-Sitzung, die Sie als Administrator ausführen, mit einem globalen Administratorkonto an.    

2. Führen Sie dann den folgenden Befehl aus:  

    ```powershell   
    Get-Label |ft Name, Guid    
    ``` 

Weitere Informationen zur Verwendung verwalteter Eigenschaften finden Sie unter [Verwalten des Suchschemas in SharePoint](/sharepoint/manage-search-schema).

## <a name="remove-encryption-for-a-labeled-document"></a>Entfernen der Verschlüsselung für ein mit Bezeichnungen versehenes Dokument

Es kann zu seltenen Gelegenheiten kommen, SharePoint ein Administrator die Verschlüsselung aus einem dokument entfernen muss, das in einem SharePoint. Jeder Benutzer, [](/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) dem das Nutzungsrecht für die Rechteverwaltung des Exports oder der Vollkontrolle für dieses Dokument zugewiesen ist, kann die verschlüsselung, die vom Azure Rights Management-Dienst angewendet wurde, aus Azure Information Protection entfernen. Beispielsweise können Benutzer mit einem dieser Nutzungsrechte eine Bezeichnung ersetzen, die verschlüsselungsfrei durch eine Bezeichnung angewendet wird. Alternativ kann ein [Superbenutzer](/azure/information-protection/configure-super-users) die Datei herunterladen und eine lokale Kopie ohne Verschlüsselung speichern.

Alternativ kann ein globaler [](/sharepoint/sharepoint-admin-role) Administrator oder SharePoint-Administrator das [Cmdlet Unlock-SPOSensitivityLabelEncryptedFile](/powershell/module/sharepoint-online/unlock-sposensitivitylabelencryptedFile) ausführen, das sowohl die Vertraulichkeitsbezeichnung als auch die Verschlüsselung entfernt. Dieses Cmdlet wird auch dann ausgeführt, wenn der Administrator nicht über Zugriffsberechtigungen für die Website oder Datei verfügt oder wenn der Azure Rights Management-Dienst nicht verfügbar ist. 

Beispiel:

```powershell
Unlock-SPOSensitivityLabelEncryptedFile -FileUrl "https://contoso.com/sites/Marketing/Shared Documents/Doc1.docx" -JustificationText "Need to decrypt this file"
```

Anforderungen:

- SharePoint Online-Verwaltungsshell, Version 16.0.20616.12000 oder höher.

- Die Verschlüsselung wurde von einer Vertraulichkeitsbezeichnung mit vom Administrator definierten Verschlüsselungseinstellungen angewendet (die Einstellungen [Berechtigungen jetzt](encryption-sensitivity-labels.md#assign-permissions-now) zuweisen). [Die Doppelschlüsselverschlüsselung](encryption-sensitivity-labels.md#double-key-encryption) wird für dieses Cmdlet nicht unterstützt.

Der Begründungstext wird [](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) dem Überwachungsereignis **"Vertraulichkeitsbezeichnung** aus Datei entfernt" hinzugefügt, und die Entschlüsselungsaktion wird auch in der Schutzverwendungsprotokollierung für [Azure Information Protection aufgezeichnet.](/azure/information-protection/log-analyze-usage)

## <a name="how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out"></a>Deaktivieren von Vertraulichkeitsbezeichnungen für SharePoint und OneDrive (Opt-out)

Wenn Sie diese neuen Funktionen deaktivieren, werden Dateien, die Sie hochgeladen haben, nachdem Sie Vertraulichkeitsbezeichnungen für SharePoint und OneDrive aktiviert haben, weiterhin durch die Bezeichnung geschützt, da die Bezeichnungseinstellungen weiterhin erzwungen werden. Wenn Sie Vertraulichkeitsbezeichnungen auf neue Dateien anwenden, nachdem Sie diese neuen Funktionen deaktiviert haben, funktioniert die Volltextsuche, eDiscovery und Die gemeinsamen Dokumentierung nicht mehr.

Um diese neuen Funktionen zu deaktivieren, müssen Sie PowerShell verwenden. Geben Sie mithilfe der SharePoint Online-Verwaltungsshell und des [Cmdlets Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) denselben *EnableAIPIntegration-Parameter* an, wie im Abschnitt Verwenden von [PowerShell](#use-powershell-to-enable-support-for-sensitivity-labels) beschrieben, um die Unterstützung für Vertraulichkeitsbezeichnungen zu aktivieren. Legen Sie dieses Mal jedoch den Parameterwert auf false ein, und drücken **Sie Y,** um zu bestätigen:

```PowerShell
Set-SPOTenant -EnableAIPIntegration $false
```

Wenn Sie über Microsoft 365 Multi-Geo verfügen, müssen Sie diesen Befehl für jeden Ihrer geografischen Standorte ausführen.

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie Vertraulichkeitsbezeichnungen für Office dateien in SharePoint und OneDrive aktiviert haben, sollten Sie diese Dateien mithilfe von Richtlinien für die automatische Bezeichnung automatisch beschriften. Weitere Informationen finden Sie unter [Automatisches Anwenden einer Vertraulichkeitsbezeichnung auf Inhalte.](apply-sensitivity-label-automatically.md)

Müssen Sie Ihre gekennzeichneten und verschlüsselten Dokumente mit Personen außerhalb Ihrer Organisation teilen?  Informationen hierzu finden Sie unter [Teilen verschlüsselter Dokumente mit externen Benutzern](sensitivity-labels-office-apps.md#sharing-encrypted-documents-with-external-users).
