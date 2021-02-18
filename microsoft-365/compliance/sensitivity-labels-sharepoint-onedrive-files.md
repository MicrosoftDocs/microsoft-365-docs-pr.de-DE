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
description: 'Administratoren können die Unterstützung von Vertraulichkeitsbezeichnungen für Word-, Excel- und #A0 in SharePoint und OneDrive aktivieren.'
ms.openlocfilehash: f84407046d2b1d91d834d090f49fc385df36ec51
ms.sourcegitcommit: 88820cd2536a7da868e472d10b4d265c52e5692b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/17/2021
ms.locfileid: "50279353"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive"></a>Aktivieren von Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

Aktivieren Sie Vertraulichkeitsbezeichnungen für #A0 in SharePoint und OneDrive, damit Benutzer Ihre Vertraulichkeitsbezeichnungen [in](sensitivity-labels.md) Office im Web anwenden können. Wenn dieses Feature aktiviert ist,  wird den Benutzern die Schaltfläche "Vertraulichkeit" auf dem Menüband angezeigt, damit sie Bezeichnungen anwenden und jeden angewendeten Bezeichnungsnamen auf der Statusleiste sehen können. 

Das Aktivieren dieses Features führt auch dazu, dass SharePoint und OneDrive den Inhalt von Dateien verarbeiten können, die mithilfe einer Vertraulichkeitsbezeichnung verschlüsselt wurden. Die Bezeichnung kann in Office für das Web oder in Office-Desktop-Apps angewendet und in SharePoint und OneDrive hochgeladen oder gespeichert werden. Bis Sie dieses Feature aktivieren, können diese Dienste keine verschlüsselten Dateien verarbeiten, was bedeutet, dass die gemeinsame Dokumentverfassung, eDiscovery, Verhinderung von Datenverlust, Suche und andere Features für die Zusammenarbeit für diese Dateien nicht funktionieren.

Nachdem Sie Vertraulichkeitsbezeichnungen für #A0 in SharePoint und OneDrive aktiviert haben, für neue und geänderte Dateien mit einer Vertraulichkeitsbezeichnung, die verschlüsselung mit einem cloudbasierten Schlüssel angewendet wird (und keine Doppelschlüsselverschlüsselung [verwendet):](double-key-encryption.md)

- Bei Word-, Excel- und #A0 erkennen SharePoint und OneDrive die Bezeichnung und können jetzt den Inhalt der verschlüsselten Datei verarbeiten.

- Wenn Benutzer diese Dateien aus SharePoint oder OneDrive herunterladen oder darauf zugreifen, werden die Vertraulichkeitsbezeichnung und alle Verschlüsselungseinstellungen der Bezeichnung erzwungen und verbleiben bei der Datei, unabhängig davon, wo sie gespeichert wird. Stellen Sie sicher, dass Sie Benutzerleitfäden bereitstellen, um nur Bezeichnungen zum Schutz von Dokumenten zu verwenden. Weitere Informationen finden Sie unter [Information Rights Management (IRM)-Optionen und Vertraulichkeitsbezeichnungen.](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels)

- Wenn Benutzer mit Bezeichnungen versehene und verschlüsselte Dateien in SharePoint oder OneDrive hochladen, müssen sie mindestens über Anzeigerechte für diese Dateien verfügen. Beispielsweise können sie die Dateien außerhalb von SharePoint öffnen. Wenn sie nicht über dieses Mindestnutzungsrecht verfügen, ist der Upload erfolgreich, aber der Dienst erkennt die Bezeichnung nicht und kann den Dateiinhalt nicht verarbeiten.

- Verwenden Sie Office im Web (Word, Excel, PowerPoint) zum Öffnen und Bearbeiten von Office-Dateien mit Vertraulichkeitsbezeichnungen, die Verschlüsselung anwenden. Die Berechtigungen, die mit der Verschlüsselung zugewiesen wurden, werden erzwungen. Sie können auch die [automatische Bezeichnung für](apply-sensitivity-label-automatically.md) diese Dokumente verwenden.

- Externe Benutzer können mithilfe von Gastkonten auf Dokumente zugreifen, die mit Verschlüsselung gekennzeichnet sind. Weitere Informationen finden Sie unter [Support für externe Benutzer und mit Bezeichnungen versehene Inhalte.](sensitivity-labels-office-apps.md#support-for-external-users-and-labeled-content) 

- Office 365 eDiscovery unterstützt die Volltextsuche für diese Dateien, und Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) unterstützen Inhalte in diesen Dateien.

> [!NOTE]
> Wenn die Verschlüsselung mit einem lokalen Schlüssel (einer Schlüsselverwaltungstopologie, die häufig als "Eigenen Schlüssel speichern" oder HYOK bezeichnet wird) oder mithilfe der Verschlüsselung mit Doppelschlüssel angewendet [wurde,](double-key-encryption.md)ändert sich das Dienstverhalten für die Verarbeitung des Dateiinhalts nicht. Bei diesen Dateien funktioniert die gemeinsame Dokumentierung, eDiscovery, Verhinderung von Datenverlust, Suche und andere Features für die Zusammenarbeit also nicht.
>
> Das SharePoint- und #A0 ändert sich auch nicht für vorhandene Dateien an diesen Speicherorten, die mithilfe eines einzelnen Azure-basierten Schlüssels mit Verschlüsselung gekennzeichnet sind. Damit diese Dateien von den neuen Funktionen profitieren, nachdem Sie Vertraulichkeitsbezeichnungen für #A0 in SharePoint und OneDrive aktiviert haben, müssen die Dateien entweder heruntergeladen und erneut hochgeladen oder bearbeitet werden.

Nachdem Sie Vertraulichkeitsbezeichnungen für #A0 in [](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) SharePoint und OneDrive aktiviert haben, stehen drei neue Überwachungsereignisse zur Überwachung von Vertraulichkeitsbezeichnungen zur Verfügung, die auf Dokumente in SharePoint und OneDrive angewendet werden:
- **Vertraulichkeitsbezeichnung wurde auf Datei angewendet**
- **Auf Datei angewendete Vertraulichkeitsbezeichnung wurde geändert**
- **Vertraulichkeitsbezeichnung wurde von Datei entfernt**

Sehen Sie sich das folgende Video (kein Audio) an, um die neuen Funktionen in Aktion zu sehen:

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

Sie haben immer die Möglichkeit, Vertraulichkeitsbezeichnungen für #A0 in SharePoint und OneDrive[(abmelden)](#how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out)jederzeit zu deaktivieren.

Wenn Sie Dokumente in SharePoint derzeit mithilfe der Verwaltung von Informationsrechten (IrM) von SharePoint schützen, überprüfen Sie den Abschnitt zur Verwaltung von Informationsrechten [(Information Rights Management, IRM)](#sharepoint-information-rights-management-irm-and-sensitivity-labels) und zu Vertraulichkeitsbezeichnungen in SharePoint auf dieser Seite. 

## <a name="requirements"></a>Anforderungen

Diese neuen Funktionen funktionieren nur mit [Vertraulichkeitsbezeichnungen.](sensitivity-labels.md) Wenn Sie derzeit über Azure Information Protection-Bezeichnungen verfügen, migrieren Sie sie zuerst zu Vertraulichkeitsbezeichnungen, damit Sie diese Features für neue Dateien aktivieren können, die Sie hochladen. Anweisungen finden Sie unter [Migrieren von Azure Information Protection-Bezeichnungen zu einheitlichen Vertraulichkeitsbezeichnungen.](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)

Verwenden Sie die OneDrive-Synchronisierungs-App, Version 19.002.0121.0008 oder höher unter Windows, und Version 19.002.0107.0008 oder höher für Mac. Beide Versionen wurden am 28. Januar 2019 veröffentlicht und sind derzeit für alle Ringe verfügbar. Weitere Informationen finden Sie in den [OneDrive-Versionshinweisen.](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0) Nachdem Sie Vertraulichkeitsbezeichnungen für #A0 in SharePoint und OneDrive aktiviert haben, werden Benutzer, die eine ältere Version der #A1 ausführen, aufgefordert, sie zu aktualisieren.

## <a name="limitations"></a>Einschränkungen

- SharePoint und OneDrive wenden Vertraulichkeitsbezeichnungen nicht automatisch auf vorhandene Dateien an, die Sie bereits mit Azure Information #A0 verschlüsselt haben. Führen Sie stattdessen die folgenden Aufgaben aus, damit die Features funktionieren, nachdem Sie Vertraulichkeitsbezeichnungen für #A0 in SharePoint und OneDrive aktiviert haben:
    
    1. Stellen Sie sicher, dass Sie die Azure [](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) [Information](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels) Protection-Bezeichnungen zu Vertraulichkeitsbezeichnungen migriert und aus dem Microsoft 365 Compliance Center oder dem entsprechenden Admin Center für Bezeichnungen veröffentlicht haben.
    
    2. Laden Sie die Dateien herunter, und laden Sie sie dann in SharePoint hoch.

- SharePoint und OneDrive können verschlüsselte Dateien nicht verarbeiten, wenn die Bezeichnung, mit der die Verschlüsselung angewendet wurde, eine der folgenden Konfigurationen für [die Verschlüsselung hat:](encryption-sensitivity-labels.md#configure-encryption-settings)
    - **Benutzern das Zuweisen von Berechtigungen** ermöglichen, wenn sie die Bezeichnung anwenden, und das Kontrollkästchen in **Word, PowerPoint** und Excel, Benutzer zum Angeben von Berechtigungen aufforderen, ist aktiviert. Diese Einstellung wird manchmal als "benutzerdefinierte Berechtigungen" bezeichnet.
    - **Der Benutzerzugriff auf Inhalte läuft ab und** ist auf einen anderen Wert als Never **festgelegt.**
    - **Doppelschlüsselverschlüsselung** ist ausgewählt.
    
    Bei Bezeichnungen mit einer dieser Verschlüsselungskonfigurationen werden die Bezeichnungen Benutzern in Office im Web nicht angezeigt. Darüber hinaus können die neuen Funktionen nicht mit mit Bezeichnungen versehenen Dokumenten verwendet werden, die bereits über diese Verschlüsselungseinstellungen verfügen. Beispielsweise werden diese Dokumente nicht in den Suchergebnissen zurückgegeben, auch wenn sie aktualisiert werden.

- Bei verschlüsselten Dokumenten wird das Drucken nicht unterstützt.

- Bei einem verschlüsselten Dokument, das einem Benutzer Bearbeitungsberechtigungen erteilt, kann das Kopieren in den Webversionen der Office-Apps nicht blockiert werden.

- Die Azure Information Protection-Dokumentverfolgungswebsite wird nicht unterstützt.

- Office-Desktop-Apps und mobile Apps unterstützen keine gemeinsamen Dokumentautorisierungen für Dateien, die mit Verschlüsselung gekennzeichnet sind. Diese Apps öffnen weiterhin mit Bezeichnungen versehene und verschlüsselte Dateien im exklusiven Bearbeitungsmodus.

- Wenn ein Administrator Einstellungen für eine veröffentlichte Bezeichnung ändert, die bereits auf Dateien angewendet wurde, die auf den Synchronisierungsclient des Benutzers heruntergeladen wurden, können Benutzer änderungen, die sie an der Datei vornehmen, möglicherweise nicht in ihrem #A0 speichern. Dieses Szenario gilt für Dateien, die mit Verschlüsselung gekennzeichnet sind, und auch, wenn sich die Bezeichnung von einer Bezeichnung ändert, die keine Verschlüsselung auf eine Bezeichnung angewendet hat, die Verschlüsselung angewendet hat. Benutzern wird ein roter Kreis mit einem Weißen [Kreuzsymbol](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)angezeigt, und sie werden aufgefordert, neue Änderungen als separate Kopie zu speichern. Stattdessen können sie die Datei schließen und erneut öffnen oder Office im Web verwenden.

- Wenn ein mit Bezeichnungen versehenes Dokument in SharePoint oder OneDrive hochgeladen wird und die Bezeichnung Verschlüsselung mithilfe eines Kontos aus einem Dienstprinzipalnamen angewendet hat, kann das Dokument nicht in Office im Web geöffnet werden. Zu den Beispielszenarien gehören Microsoft Cloud App Security und eine Per E-Mail an Teams gesendete Datei.

- Benutzer können Speicherprobleme nach dem Offlinebetrieb oder in einen Ruhezustand haben, wenn sie anstelle von Office für das Web die Desktop- und mobilen Apps für Word, Excel oder PowerPoint verwenden. Wenn diese Benutzer ihre Office-App-Sitzung fortsetzen und versuchen, Änderungen zu speichern, wird eine Uploadfehlermeldung mit der Option angezeigt, eine Kopie zu speichern, anstatt die Originaldatei zu speichern. 

- Dokumente, die auf folgende Weise verschlüsselt wurden, können in Office im Web nicht geöffnet werden:
    - Verschlüsselung, die einen lokalen Schlüssel verwendet ("eigenen Schlüssel halten" oder HYOK)
    - Verschlüsselung, die mithilfe der [Doppelschlüsselverschlüsselung angewendet wurde](double-key-encryption.md)
    - Verschlüsselung, die unabhängig von einer Bezeichnung angewendet wurde, z. B. durch direktes Anwenden einer Vorlage für den Rechteverwaltungsschutz.

- Bezeichnungen, die für [andere Sprachen](create-sensitivity-labels.md#additional-label-settings-with-security--compliance-center-powershell) konfiguriert sind, werden nicht unterstützt und zeigen nur die Ursprüngliche Sprache an.

- Bildschirmaufzeichnungen können für verschlüsselte Dokumente nicht verhindert werden. Weitere Informationen finden Sie unter ["Can Rights Management prevent screen captures"?](/azure/information-protection/faqs-rms#can-rights-management-prevent-screen-captures)

- Wenn Sie eine Bezeichnung löschen, die auf ein Dokument in SharePoint oder OneDrive angewendet wurde, anstatt die Bezeichnung aus der entsprechenden Bezeichnungsrichtlinie zu entfernen, wird das heruntergeladene Dokument nicht mit Bezeichnungen oder Verschlüsselten versehen. Im Vergleich dazu bleibt das Dokument verschlüsselt, wenn das bezeichnete Dokument außerhalb von SharePoint oder OneDrive gespeichert wird, wenn die Bezeichnung gelöscht wird. Beachten Sie, dass Bezeichnungen zwar während einer Testphase gelöscht werden können, es jedoch sehr selten ist, eine Bezeichnung in einer Produktionsumgebung zu löschen.

## <a name="how-to-enable-sensitivity-labels-for-sharepoint-and-onedrive-opt-in"></a>Aktivieren von Vertraulichkeitsbezeichnungen für SharePoint und OneDrive (Opt-in)

Sie können die neuen Funktionen mithilfe des Microsoft 365 Compliance Centers oder mithilfe von PowerShell aktivieren. Wie bei allen Konfigurationsänderungen auf Mandantenebene für SharePoint und OneDrive dauert es etwa 15 Minuten, bis die Änderung wirksam wird.

### <a name="use-the-compliance-center-to-enable-support-for-sensitivity-labels"></a>Aktivieren der Unterstützung für Vertraulichkeitsbezeichnungen mithilfe des Compliance Centers

Diese Option ist die einfachste Möglichkeit, Vertraulichkeitsbezeichnungen für SharePoint und OneDrive zu aktivieren, Sie müssen sich jedoch als globaler Administrator für Ihren Mandanten anmelden.

1. Melden Sie sich beim [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) als globaler Administrator an, und navigieren Sie zu **Lösungsinformationsschutz.**  >  
    
    Wenn diese Option nicht sofort angezeigt wird, wählen Sie zunächst **Alle anzeigen** aus. 

2. Wenn eine Meldung zum Aktivieren der Möglichkeit zum Verarbeiten von Inhalten in Office-Onlinedateien angezeigt wird, wählen Sie jetzt **"Jetzt aktivieren" aus:**
    
    ![Schaltfläche "Jetzt aktivieren" zum Aktivieren von Vertraulichkeitsbezeichnungen für Office Online](../media/sensitivity-labels-turn-on-banner.png)
    
    Der Befehl wird sofort ausgeführt, und wenn die Seite das nächste Mal aktualisiert wird, wird die Meldung oder Schaltfläche nicht mehr angezeigt.

> [!NOTE]
> Wenn Sie über Microsoft 365 Multi-Geo verfügen, müssen Sie PowerShell verwenden, um diese Funktionen für alle Geografischen Standorte zu aktivieren. Ausführliche Informationen finden Sie im nächsten Abschnitt.

### <a name="use-powershell-to-enable-support-for-sensitivity-labels"></a>Verwenden von PowerShell zum Aktivieren der Unterstützung von Vertraulichkeitsbezeichnungen

Als Alternative zur Verwendung des Compliance Centers können Sie die Unterstützung von Vertraulichkeitsbezeichnungen mithilfe des [Cmdlets "Set-SPOTenant"](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant) aus SharePoint Online PowerShell aktivieren. 

Wenn Sie über Microsoft 365 Multi-Geo verfügen, müssen Sie PowerShell verwenden, um diese Unterstützung für alle Geografischen Standorte zu aktivieren.

#### <a name="prepare-the-sharepoint-online-management-shell"></a>Vorbereiten der SharePoint Online-Verwaltungsshell

Bevor Sie den #A0 zum Aktivieren von Vertraulichkeitsbezeichnungen für #A1 in SharePoint und OneDrive ausführen, stellen Sie sicher, dass Sie SharePoint #A2 Version 16.0.19418.12000 oder höher ausführen. Wenn Sie bereits über die neueste Version verfügen, können Sie mit dem nächsten Verfahren zum [Ausführen](#run-the-powershell-command-to-enable-support-for-sensitivity-labels) des Befehls PowerShell springen.

1. Wenn Sie eine frühere Version der SharePoint-Online-Verwaltungsshell aus dem PowerShell-Katalog installiert haben, können Sie das Modul aktualisieren, indem Sie das folgende Cmdlet ausführen.

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. Wenn Sie eine frühere Version der SharePoint Online-Verwaltungsshell aus dem Microsoft  Download Center installiert haben, können Sie auch zu "Software hinzufügen" oder "Entfernen" wechseln und die SharePoint Online-Verwaltungsshell deinstallieren.

3. Wechseln Sie in einem Webbrowser zur Download Center-Seite, und [laden Sie die neueste SharePoint Online-Verwaltungsshell herunter](https://go.microsoft.com/fwlink/p/?LinkId=255251).

4. Wählen Sie die gewünschte Sprache aus, und klicken Sie auf **Download**.

5. Wählen Sie zwischen der x64- und der x86-Version der MSI-Datei aus. Laden Sie die x64-Datei herunter, wenn Sie die 64-Bit-Version von Windows oder die x86-Datei ausführen, wenn Sie die 32-Bit-Version ausführen. Wenn Sie nicht wissen, welche Version des Windows-Betriebssystems [ich ausführen soll?](https://support.microsoft.com/help/13443/windows-which-operating-system)

6. Nachdem Sie die Datei heruntergeladen haben, führen Sie die Datei aus, und führen Sie die Schritte im Setup-Assistenten aus.

#### <a name="run-the-powershell-command-to-enable-support-for-sensitivity-labels"></a>Ausführen des PowerShell-Befehls, um die Unterstützung für Vertraulichkeitsbezeichnungen zu aktivieren

Verwenden Sie zum Aktivieren der neuen Funktionen das [Cmdlet "Set-SPOTenant"](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant) mit dem Parameter *"EnableAIPIntegration":*

1. Stellen Sie mithilfe eines Arbeits- oder Schulkontos, das über globale Administrator- oder SharePoint-Administratorrechte in Microsoft 365 verfügt, eine Verbindung mit SharePoint herzustellen. Eine Anleitung dazu finden Sie unter [Erste Schritte mit der Microsoft Office SharePoint Online-Verwaltungsshell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
    
    Hinweis: Wenn Sie über Microsoft 365 Multi-Geo verfügen, verwenden Sie den Parameter "-Url" mit ["Connect-SPOService",](https://docs.microsoft.com/powershell/module/sharepoint-online/connect-sposervice)und geben Sie die URL der SharePoint Online-Verwaltungscenter-Website für einen Ihrer geografischen Standorte an.

2. Führen Sie den folgenden Befehl aus, und drücken **Sie Y,** um dies zu bestätigen:

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true
    ```
3. Für Microsoft 365 Multi-Geo: Wiederholen Sie die Schritte 1 und 2 für jeden der verbleibenden geografischen Standorte.

## <a name="publishing-and-changing-sensitivity-labels"></a>Veröffentlichen und Ändern von Vertraulichkeitsbezeichnungen

Wenn Sie Vertraulichkeitsbezeichnungen mit SharePoint und OneDrive verwenden, müssen Sie die Replikationszeit berücksichtigen, wenn Sie neue Vertraulichkeitsbezeichnungen veröffentlichen oder vorhandene Vertraulichkeitsbezeichnungen aktualisieren. Dies ist besonders wichtig für neue Bezeichnungen, die Verschlüsselung anwenden.

Beispiel: Sie erstellen und veröffentlichen eine neue Vertraulichkeitsbezeichnung, die Verschlüsselung angewendet, und sie wird sehr schnell in der Desktop-App eines Benutzers angezeigt. Der Benutzer wendet diese Bezeichnung auf ein Dokument an und lädt sie dann in SharePoint oder OneDrive hoch. Wenn die Bezeichnungsreplikation für den Dienst nicht abgeschlossen wurde, werden die neuen Funktionen beim Hochladen nicht auf dieses Dokument angewendet. Aus diesem Grund wird das Dokument nicht bei der Suche oder für eDiscovery zurückgegeben, und das Dokument kann nicht in Office für das Web geöffnet werden.  

Die folgenden Änderungen werden innerhalb einer Stunde repliziert: Neue und gelöschte Vertraulichkeitsbezeichnungen und Richtlinieneinstellungen für Vertraulichkeitsbezeichnungen, die enthalten, welche Bezeichnungen in der Richtlinie enthalten sind.

Die folgenden Änderungen werden innerhalb von 24 Stunden repliziert: Änderungen an den Einstellungen für Vertraulichkeitsbezeichnungen für vorhandene Bezeichnungen.

Da die Replikationsverzögerung für neue Vertraulichkeitsbezeichnungen nur eine Stunde beträgt, ist es unwahrscheinlich, dass das Szenario im Beispiel ausgeführt wird. Als Schutz wird jedoch empfohlen, neue Bezeichnungen zuerst nur für wenige Testbenutzer zu veröffentlichen, eine Stunde zu warten und dann das Bezeichnungsverhalten in SharePoint und OneDrive zu überprüfen. Als letzten Schritt können Sie die Bezeichnung für mehr Benutzer verfügbar machen, indem Sie der vorhandenen Bezeichnungsrichtlinie entweder weitere Benutzer hinzufügen oder die Bezeichnung einer vorhandenen Bezeichnungsrichtlinie für Ihre Standardbenutzer hinzufügen. Wenn Ihre Standardbenutzer die Bezeichnung sehen, wurde sie bereits mit SharePoint und OneDrive synchronisiert.

## <a name="sharepoint-information-rights-management-irm-and-sensitivity-labels"></a>Verwaltung von Informationsrechten in SharePoint (IRM) und Vertraulichkeitsbezeichnungen

Die Verwaltung von Informationsrechten [in SharePoint (IRM)](set-up-irm-in-sp-admin-center.md) ist eine ältere Technologie zum Schutz von Dateien auf Listen- und Bibliotheksebene durch Anwendung von Verschlüsselung und Einschränkungen beim Herunterladen von Dateien. Diese ältere Schutztechnologie soll verhindern, dass nicht autorisierte Benutzer die Datei öffnen, während sie sich außerhalb von SharePoint befindet.

Im Vergleich dazu stellen Vertraulichkeitsbezeichnungen zusätzlich zur Verschlüsselung die Schutzeinstellungen visueller Markierungen (Kopf- und Fußzeilen, Wasserzeichen) zur Verfügung. Die Verschlüsselungseinstellungen unterstützen [](https://docs.microsoft.com/azure/information-protection/configure-usage-rights) den vollständigen Bereich von Nutzungsrechten, um einzuschränken, was Benutzer mit dem Inhalt tun können, und die gleichen Vertraulichkeitsbezeichnungen werden für viele [Szenarien unterstützt.](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels) Die Verwendung derselben Schutzmethode mit konsistenten Einstellungen für alle Workloads und Apps führt zu einer konsistenten Schutzstrategie.

Sie können jedoch beide Schutzlösungen zusammen verwenden, und das Verhalten lautet wie folgt: 

- Wenn Sie eine Datei mit einer Vertraulichkeitsbezeichnung hochladen, die Verschlüsselung angewendet wird, kann SharePoint den Inhalt dieser Dateien nicht verarbeiten, sodass die gemeinsame Dokumentverfassung, eDiscovery, DLP und Suche für diese Dateien nicht unterstützt werden.

- Wenn Sie eine Datei mit Office im Web beschriften, werden alle Verschlüsselungseinstellungen der Bezeichnung erzwungen. Für diese Dateien werden die mitverfassende, eDiscovery-, DLP- und Suchfunktion unterstützt.

- Wenn Sie eine Datei herunterladen, die mit Office im Web beschriftet ist, wird die Bezeichnung beibehalten, und alle Verschlüsselungseinstellungen aus der Bezeichnung werden anstelle der Einstellungen für die IrM-Einschränkung erzwungen.

- Wenn Sie eine Office- oder PDF-Datei herunterladen, die nicht mit einer Vertraulichkeitsbezeichnung verschlüsselt ist, werden die IRM-Einstellungen angewendet.

- Wenn Sie eine der zusätzlichen Einstellungen für die IRM-Bibliothek aktiviert haben, die u. a. verhindern, dass Benutzer Dokumente hochladen, die IRM nicht unterstützen, werden diese Einstellungen erzwungen.

Mit diesem Verhalten können Sie sicher sein, dass alle Office- und PDF-Dateien vor unbefugtem Zugriff geschützt sind, wenn sie heruntergeladen werden, auch wenn sie nicht mit Bezeichnungen versehen sind. Hochgeladene Dateien mit Bezeichnungen profitieren jedoch nicht von den neuen Funktionen.


## <a name="search-for-documents-by-sensitivity-label"></a>Suchen nach Dokumenten nach Vertraulichkeitsbezeichnung

Verwenden Sie die verwaltete Eigenschaft **"InformationProtectionLabelId",** um alle Dokumente in SharePoint oder OneDrive zu suchen, die eine bestimmte Vertraulichkeitsbezeichnung haben. Verwenden Sie die folgende Syntax: `InformationProtectionLabelId:<GUID>`

Wenn Sie beispielsweise nach allen Dokumenten suchen möchten, die mit "Vertraulich" gekennzeichnet wurden und diese Bezeichnung die GUID "8faca7b8-8d20-48a3-8ea2-0f96310a848e" hat, geben Sie im Suchfeld folgenden Text ein:

`InformationProtectionLabelId: 8faca7b8-8d20-48a3-8ea2-0f96310a848e`    

Verwenden Sie das Cmdlet ["Get-Label",](https://docs.microsoft.com/powershell/module/exchange/get-label) um die GUIDs für Ihre Vertraulichkeitsbezeichnungen zu erhalten:  

1. Stellen Sie [zunächst eine Verbindung mit Office 365 Security & Compliance Center PowerShell her](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell). 
   
    Melden Sie sich beispielsweise in einer PowerShell-Sitzung, die Sie als Administrator ausführen, mit einem globalen Administratorkonto an.    

2. Führen Sie dann den folgenden Befehl aus:  

    ```powershell   
    Get-Label |ft Name, Guid    
    ``` 

Weitere Informationen zur Verwendung verwalteter Eigenschaften finden Sie unter [Verwalten des Suchschemas in SharePoint](https://docs.microsoft.com/sharepoint/manage-search-schema).

## <a name="remove-encryption-for-a-labeled-document"></a>Entfernen der Verschlüsselung für ein mit Bezeichnungen versehenes Dokument

Es kann seltenen Fälle geben, in denen ein SharePoint-Administrator die Verschlüsselung aus einem in SharePoint gespeicherten Dokument entfernen muss. Jeder Benutzer, [](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) dem das Nutzungsrecht "Rechteverwaltung" auf "Export" oder "Vollschutz" für dieses Dokument zugewiesen ist, kann die Verschlüsselung, die vom Azure Rights Management Service angewendet wurde, aus Azure Information Protection entfernen. Beispielsweise können Benutzer mit einem dieser Nutzungsrechte eine Bezeichnung ersetzen, die verschlüsselungsfrei durch eine Bezeichnung angewendet wird. Alternativ kann ein [Superbenutzer die](https://docs.microsoft.com/azure/information-protection/configure-super-users) Datei herunterladen und eine lokale Kopie ohne Verschlüsselung speichern.

Alternativ kann ein globaler Administrator oder ein [SharePoint-Administrator](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) das Cmdlet [Unlock-SPOSensitivityLabelEncryptedFile](https://docs.microsoft.com/powershell/module/sharepoint-online/unlock-sposensitivitylabelencryptedFile) ausführen, das sowohl die Vertraulichkeitsbezeichnung als auch die Verschlüsselung entfernt. Dieses Cmdlet wird auch dann ausgeführt, wenn der Administrator nicht über Zugriffsberechtigungen für die Website oder Datei verfügt oder wenn der Azure Rights Management Service nicht verfügbar ist. 

Zum Beispiel:

```powershell
Unlock-SPOSensitivityLabelEncryptedFile -FileUrl "https://contoso.com/sites/Marketing/Shared Documents/Doc1.docx" -JustificationText "Need to decrypt this file"
```

Anforderungen:

- SharePoint Online Management Shell, Version 16.0.20616.12000 oder höher.

- Die Verschlüsselung wurde von einer Vertraulichkeitsbezeichnung mit vom Administrator definierten Verschlüsselungseinstellungen angewendet (die Einstellungen zum Zuweisen von Berechtigungen [jetzt).](encryption-sensitivity-labels.md#assign-permissions-now) [Die Verschlüsselung mit](encryption-sensitivity-labels.md#double-key-encryption) Doppelschlüssel wird für dieses Cmdlet nicht unterstützt.

Der Begründungstext wird [](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) dem Überwachungsereignis der Vertraulichkeitsbezeichnung "Aus Datei entfernt" **hinzugefügt,** und die Entschlüsselungsaktion wird auch in der Schutzverwendungsprotokollierung für Azure Information [Protection aufgezeichnet.](https://docs.microsoft.com/azure/information-protection/log-analyze-usage)

## <a name="how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out"></a>Deaktivieren von Vertraulichkeitsbezeichnungen für SharePoint und OneDrive (Abmelden)

Wenn Sie diese neuen Funktionen deaktivieren, werden Dateien, die Sie hochgeladen haben, nachdem Sie Vertraulichkeitsbezeichnungen für SharePoint und OneDrive aktiviert haben, weiterhin durch die Bezeichnung geschützt, da die Bezeichnungseinstellungen weiterhin erzwungen werden. Wenn Sie vertraulichkeitsbezeichnungen auf neue Dateien anwenden, nachdem Sie diese neuen Funktionen deaktiviert haben, funktioniert die Volltextsuche, eDiscovery und die gemeinsamen Dokumentierung nicht mehr.

Um diese neuen Funktionen zu deaktivieren, müssen Sie PowerShell verwenden. Geben Sie mithilfe der SharePoint Online-Verwaltungsshell und des [Cmdlets "Set-SPOTenant"](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant) denselben *Parameter "EnableAIPIntegration"* an, wie im Abschnitt "Verwenden von [PowerShell](#use-powershell-to-enable-support-for-sensitivity-labels) zum Aktivieren der Unterstützung von Vertraulichkeitsbezeichnungen" beschrieben. Legen Sie dieses Mal jedoch den Parameterwert auf "false" und drücken **Sie Y,** um zu bestätigen:

```PowerShell
Set-SPOTenant -EnableAIPIntegration $false
```

Wenn Sie über Microsoft 365 Multi-Geo verfügen, müssen Sie diesen Befehl für jeden Ihrer geografischen Standorte ausführen.

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie Vertraulichkeitsbezeichnungen für #A0 in SharePoint und OneDrive aktiviert haben, sollten Sie diese Dateien mithilfe von Richtlinien für die automatische Bezeichnung automatisch beschriften. Weitere Informationen finden Sie unter ["Automatisches Anwenden einer Vertraulichkeitsbezeichnung auf Inhalte".](apply-sensitivity-label-automatically.md)

Müssen Sie Ihre gekennzeichneten und verschlüsselten Dokumente mit Personen außerhalb Ihrer Organisation teilen?  Informationen hierzu finden Sie unter [Teilen verschlüsselter Dokumente mit externen Benutzern](sensitivity-labels-office-apps.md#sharing-encrypted-documents-with-external-users).
