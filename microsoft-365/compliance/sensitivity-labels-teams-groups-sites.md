---
title: Verwenden von Vertraulichkeitsbezeichnungen für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites (öffentliche Vorschau)
ms.author: krowley
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Sie können Bezeichnungen auf Microsoft Teams, Office 365-Gruppen und SharePoint-Websites anwenden.
ms.openlocfilehash: 4a8cf810ba29c2bb025b50e1529081a1a9ba6843
ms.sourcegitcommit: 72d0280c2481250cf9114d32317ad2be59ab6789
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40966893"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a>Verwenden von Vertraulichkeitsbezeichnungen für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites (öffentliche Vorschau)

Wenn Sie im [Microsoft 365 Compliance Center](https://protection.office.com/) Vertraulichkeitsbezeichnungen erstellen, können Sie diese jetzt auf Microsoft Teams, Office 365-Gruppen und SharePoint-Websites anwenden. Sie können den Bezeichnungen Richtlinien zuordnen, um Folgendes zu steuern:

- Öffentliche/private-Einstellungen
- Gastzugriff
- Zugriff von nicht verwalteten Geräten aus

Wenn Sie eine Bezeichnung auf ein Team oder eine Gruppe anwenden, wird die Bezeichnung automatisch auf die verbundene SharePoint-Teamwebsite und umgekehrt angewendet.

Außerdem können Sie Vertraulichkeitsbezeichnungen jetzt auch für Office-Dateien in SharePoint und OneDrive aktivieren. Weitere Informationen finden Sie unter [Aktivieren von Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive (öffentliche Vorschau)](sensitivity-labels-sharepoint-onedrive-files.md).

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a>Informationen zur öffentlichen Vorschau für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites

Vertraulichkeitsbezeichnungen für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites werden schrittweise für Mandanten bereitgestellt und können sich vor der endgültigen Version ändern.

Diese öffentliche Vorschau kann nicht mit Office 365-Netzwerken für die Inhaltsübermittlung (Content Delivery Network, CDN) verwendet werden.

## <a name="overview"></a>Übersicht

Wenn Sie Vertraulichkeitsbezeichnungen veröffentlichen, haben alle Benutzer in Office 365 Zugriff auf dieselbe Liste von Bezeichnungen.

Die folgenden Bilder verdeutlichen:

- Wie die Liste aussieht, wenn eine neue Teamwebsite in SharePoint erstellt wird

- Wann die Liste in Word angezeigt wird

Beispiel:

![Eine Vertraulichkeitsbezeichnung beim Erstellen einer Teamwebsite in SharePoint](media/sensitivity-label-new-team-site.png)

![Eine in der Word-Desktop-App angezeigte Vertraulichkeitsbezeichnung](media/sensitivity-label-word.png)

## <a name="enable-this-preview"></a>Aktivieren dieser Vorschau

Sie müssen die Vorschauversion von [Azure Active Directory PowerShell für Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) (Modulname **AzureADPreview**) verwenden, um diese Vorschau von Vertraulichkeitsbezeichnungen mit Microsoft Teams, Office 365-Gruppen und SharePoint-Websites zu aktivieren:

- Wenn Sie zuvor noch keine Version des Azure AD PowerShell-Moduls installiert haben, lesen Sie [Installieren des Azure AD-Moduls](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module), und folgen Sie den Anweisungen zum Installieren der öffentlichen Vorschauversion.

- Wenn Sie die allgemein verfügbare Version 2.0 des Azure AD PowerShell-Moduls (AzureAD) installiert haben, müssen Sie sie deinstallieren, indem Sie `Uninstall-Module AzureAD` in ihrer PowerShell-Sitzung ausführen, und dann mit `Install-Module AzureADPreview` die Vorschauversion installieren.

- Wenn Sie die Vorschauversion bereits installiert haben, führen Sie `Install-Module AzureADPreview` aus, um sicherzustellen, dass es sich um die neueste Version dieses Moduls handelt.

Jetzt sind Sie bereit zum Aktivieren der Vorschau der Vertraulichkeitsbezeichnungen für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites:

1. Stellen Sie in einer PowerShell-Sitzung unter Verwendung eines Geschäfts-, Schul-, oder Unikontos mit globalen Administratorberechtigungen eine Verbindung mit Azure Active Directory her. Führen Sie beispielsweise den folgenden Befehl aus:
    
    ```powershell
    Connect-AzureAD
    ````
    
    Vollständige Anweisungen finden Sie unter [Herstellen einer Verbindung mit Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#connect-to-azure-ad).

2. Führen Sie die folgenden Befehle aus:
    
    ```powershell
    $setting=(Get-AzureADDirectorySetting | where -Property DisplayName -Value "Group.Unified" -EQ)
    if ($setting -eq $null)
    {
    $template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b
    $setting = $template.CreateDirectorySetting()
    $setting["EnableMIPLabels"] = "True"
    New-AzureADDirectorySetting -DirectorySetting $setting
    }
    else
    {
    $setting["EnableMIPLabels"] = "True"
    Set-AzureADDirectorySetting -Id $setting.Id -DirectorySetting $setting
    }
    ```
    
    > [!NOTE]
    > Wenn Sie diese Vorschau aktivieren, verwendet Office 365 die alten Klassifizierungen nicht mehr für neue Gruppen und SharePoint-Websites. Wenn Sie die [Azure Ad-Websiteklassifizierung](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($setting["ClassificationList"]) verwendet haben, zeigen vorhandene Gruppen und Websites weiterhin die alten Klassifizierungen an. Um die neuen Klassifizierungen anzuzeigen, konvertieren Sie sie. Informationen zur Konvertierung finden Sie unter [Sie haben die klassische Azure AD-Websiteklassifizierung verwendet](#if-you-used-classic-azure-ad-site-classification). 

3. Stellen Sie in derselben PowerShell-Sitzung nun mithilfe eines Geschäfts-, Schul- oder Unikontos, das über globale Administratorberechtigungen verfügt, eine Verbindung mit dem Security & Compliance Center her. Anweisungen hierzu finden Sie unter [Herstellen einer Verbindung mit Office 365 Security & Compliance Center PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

4. Führen Sie die folgenden Befehle aus, um Ihre Bezeichnungen mit Azure AD zu synchronisieren, damit sie mit Office 365-Gruppen verwendet werden können:
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    Execute-AzureAdLabelSync
    ```
## <a name="set-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a>Festlegen von Website- und Gruppeneinstellungen beim Erstellen oder Bearbeiten von Vertraulichkeitsbezeichnungen

Nachdem Sie die Vorschau aktiviert haben, führen Sie die folgenden Schritte aus, um Vertraulichkeitsbezeichnungen zu erstellen oder zu bearbeiten. Sie müssen diese Schritte ausführen, damit die neuen Vertraulichkeitsbezeichnungen mit Websites und Gruppen verwendet werden können, auch wenn Sie bereits Bezeichnungen definiert haben. Die Synchronisierung der Änderungen an diesen Einstellungen kann bis zu 24 Stunden dauern.

1. Wählen Sie im Microsoft 365 Compliance Center **Klassifizierung** > **Vertraulichkeitsbezeichnungen** aus.

2. Wählen Sie **Bezeichnung erstellen** aus. Wenn Sie bereits über eine Bezeichnung verfügen, fahren Sie mit dem nächsten Schritt fort.

3. Wählen Sie die gewünschten Optionen und dann auf der Registerkarte **Website- und Gruppeneinstellungen** die folgenden Optionen aus:
    
    - Datenschutz (Öffentlich/Privat): "Privat" bedeutet, dass nur genehmigte Mitglieder in Ihrer Organisation die Inhalte der Gruppe sehen können. Alle anderen Benutzer in Ihrer Organisation können keine Inhalte der Gruppe anzeigen. [Weitere Informationen](https://support.office.com/article/36236e39-26d3-420b-b0ac-8072d2d2bedc)
    - Gastzugriff: Sie können steuern, ob Gäste einer Gruppe hinzugefügt werden können. [Weitere Informationen zum Verwalten des Gastzugriffs in Office 365-Gruppen](/office365/admin/create-groups/manage-guest-access-in-groups)
    - Nicht verwaltete Geräte: Mit dieser Einstellung können Sie den Zugriff auf SharePoint-Inhalte von Geräten aus, die keine in Azure AD eingebundenen Hybridgeräte oder nicht Intune-konform sind, blockieren oder einschränken. Wenn Sie "Nicht verwaltete Geräte" auswählen, müssen Sie zu Azure AD wechseln, um das Einrichten der Richtlinie abzuschließen. Informationen hierzu finden Sie unter [Steuern des Zugriffs von nicht verwalteten Geräten aus](/sharepoint/control-access-from-unmanaged-devices).
    
    ![Die Registerkarte "Website- und Gruppeneinstellungen"](media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> Wenn Sie eine Bezeichnung auf ein Team, eine Gruppe oder eine Website anwenden, werden nur die Website- und Gruppeneinstellungen wirksam. Andere Einstellungen (z. B. Verschlüsselung und Inhaltskennzeichnung) werden nicht auf alle Inhalte innerhalb des Teams, der Gruppen oder der Website angewendet.
> 
> Ähnlich verhält es sich, wenn Sie eine Bezeichnung erstellen und Website- und Gruppeneinstellungen nicht aktivieren. Die Bezeichnung ist dann weiterhin verfügbar, wenn Benutzer Teams, Gruppen und Websites erstellen, aber die Klassifizierung erfolgt ohne Anwendung irgendwelcher Einstellungen.

[Weitere Informationen zum Veröffentlichen von Vertraulichkeitsbezeichnungen](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

## <a name="sensitivity-label-management"></a>Verwaltung von Vertraulichkeitsbezeichnungen

> [!WARNING]
> Das Erstellen, Ändern und Löschen von Vertraulichkeitsbezeichnungen, die Sie für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites verwenden, erfordert eine sorgfältige Abstimmung mit der Veröffentlichung von Bezeichnungsrichtlinien für Benutzer. 

Vermeiden Sie Erstellungsfehler für Websites und Gruppen, die sich auf alle Benutzer auswirken, indem Sie die nachstehenden Anweisungen beachten.

**Erstellen und Veröffentlichen von Bezeichnungen:**

Nach der Erstellung und Veröffentlichung einer Vertraulichkeitsbezeichnung kann es bis zu 24 Stunden dauern, bis die Bezeichnung für Benutzer in Teams, Gruppen und Websites sichtbar wird. Führen Sie die folgenden Schritte aus, um eine Bezeichnung für alle Benutzer im Mandanten zu veröffentlichen:

1. Erstellen Sie die Vertraulichkeitsbezeichnung, und veröffentlichen Sie sie nur für einige Benutzerkonten im Mandanten.

2. Warten Sie 24 Stunden.

3. Nach Ablauf dieser 24 Stunden erstellen Sie mit einem der in Schritt 1 angegebenen Benutzerkonten ein Team, eine Office 365-Gruppe oder eine SharePoint-Website mit der Bezeichnung, die Sie in Schritt 1 erstellt haben.

4. Wenn während des Erstellungsvorgangs für Schritt 3 keine Fehler auftreten, veröffentlichen Sie die Bezeichnung für alle Benutzer in Ihrem Mandanten. Wenn Fehler auftreten, wenden Sie sich an den Microsoft-Support.

**Ändern und Löschen von veröffentlichten Bezeichnungen:**

Wenn Sie eine Vertraulichkeitsbezeichnung ändern oder löschen, die in einer oder mehreren Bezeichnungsrichtlinien enthalten ist, kann dies zu Erstellungsfehlern für alle Teams, Gruppen und Websites führen. Folgen Sie dieser Anleitung, um dieses Problem zu vermeiden:

1. Entfernen Sie die Vertraulichkeitsbezeichnung aus allen Bezeichnungsrichtlinien, in denen die Bezeichnung enthalten ist.

2. Warten Sie 48 Stunden.

3. Versuchen Sie nach 48 Stunden, ein Team, eine Gruppe oder eine Website zu erstellen, und vergewissern Sie sich, dass die Bezeichnung nicht mehr angezeigt wird.

4. Wenn die Vertraulichkeitsbezeichnung nicht angezeigt wird, können Sie sie jetzt bedenkenlos ändern oder löschen. Wird die Bezeichnung weiterhin angezeigt, wenden Sie sich an den Microsoft-Support.

## <a name="troubleshoot-sensitivity-label-deployment"></a>Problembehandlung bei der Bereitstellung von Vertraulichkeitsbezeichnungen

### <a name="labels-not-visible-after-publishing"></a>Bezeichnungen sind nach der Veröffentlichung nicht sichtbar
Wenn beim Erstellen eines Teams oder einer Office 365-Gruppe Probleme auftreten, nachdem Sie diese Einstellungen aktiviert oder die Beschreibung einer Vertraulichkeitsbezeichnung geändert haben, speichern Sie die Bezeichnung, warten Sie ein paar Stunden, und versuchen Sie dann erneut, das Team oder die Gruppe zu erstellen. Informationen hierzu finden Sie unter [Planen des Rollouts nach Erstellung oder Änderung einer Vertraulichkeitsbezeichnung](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).

Wenn die neue Vertraulichkeitsbezeichnung in SharePoint Online weiterhin nicht angezeigt wird, wenden Sie sich an den Microsoft-Support.

### <a name="team-group-or-sharepoint-site-creation-errors"></a>Fehler beim Erstellen von Teams, Gruppen oder SharePoint-Websites
Wenn während der öffentlichen Vorschau Erstellungsfehler auftreten, haben Sie zwei Möglichkeiten:

- Stellen Sie sicher, dass Vertraulichkeitsbezeichnungen für keinen Benutzer obligatorisch sind.

- Sie können Vertraulichkeitsbezeichnungen für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites unter Verwendung der Anweisungen im Abschnitt [Aktivieren dieser Vorschau](#enable-this-preview) auf dieser Seite deaktivieren. Wenn Sie die Vorschau jedoch deaktivieren, müssen Sie nach der Zeile `$setting["EnableMIPLabels"] = "True"` suchen und den Wert **True** in **False** ändern.

## <a name="apply-a-sensitivity-label-to-a-new-team"></a>Anwenden einer Vertraulichkeitsbezeichnung auf ein neues Team

Benutzer können Vertraulichkeitsbezeichnungen auswählen, wenn sie neue Teams in Microsoft Teams erstellen. Beim Auswählen der Vertraulichkeitsstufe werden die Datenschutzeinstellung bei Bedarf entsprechend geändert. Abhängig von der für die Bezeichnung festgelegten Einstellung für den Gastzugriff können Benutzer Personen außerhalb der Organisation zum Team hinzufügen oder nicht.

[Weitere Informationen Vertraulichkeitsbezeichnungen für Teams](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![Datenschutzeinstellung beim Erstellen eines neuen Teams](media/privacy-setting-new-team.png)

Nachdem Sie das Team erstellt haben, wird die Vertraulichkeitsbezeichnung in der oberen rechten Ecke aller Kanäle angezeigt.

![Die Vertraulichkeitsbezeichnung wird im Team angezeigt](media/privacy-setting-teams.png)

Der Dienst wendet auf die Office 365-Gruppe und die verbundene SharePoint-Teamwebsite automatisch die gleiche Vertraulichkeitsbezeichnung an.

## <a name="apply-a-sensitivity-label-to-a-new-group"></a>Anwenden einer Vertraulichkeitsbezeichnung auf eine neue Gruppe

In Outlook im Web enthält das neue Feld **Vertraulichkeit** veröffentlichte Bezeichnungen. Wenn Benutzer weitere Informationen benötigen, können sie auf das Hilfesymbol klicken, um Details zu den verfügbaren Bezeichnungen und den zugehörigen Richtlinien anzuzeigen.

![Erstellen einer Gruppe und Auswählen einer Option unter "Vertraulichkeit"](media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a>Anwenden einer Vertraulichkeitsbezeichnung auf eine neue Website

Administratoren und Endbenutzer können beim Erstellen moderner Teamwebsites und Kommunikationswebsites Vertraulichkeitsbezeichnungen auswählen.

[Weitere Informationen zum Erstellen einer Website im neuen SharePoint Admin Center](/sharepoint/create-site-collection).

Wenn Benutzer moderne Teamwebsites und Kommunikationswebsites erstellen, ist standardmäßig bereits eine Vertraulichkeitsbezeichnung aktiviert. Benutzer können das Hilfesymbol auswählen, um weitere Informationen zu den Bezeichnungen zu erhalten.

![Erstellen einer Website und Auswählen einer Option unter "Vertraulichkeit"](media/sensitivity-label-new-communication-site.png)

Wenn Benutzer zu der Website navigieren, werden der Name der Bezeichnung und die angewendeten Richtlinien angezeigt.

![Eine Website, auf die eine Vertraulichkeitsbezeichnung angewendet wurde](media/sensitivity-label-site.png)

## <a name="manage-sensitivity-labels-in-the-sharepoint-admin-center"></a>Verwalten von Vertraulichkeitsbezeichnungen im SharePoint Online Admin Center

Wenn Sie die Bezeichnung anzeigen und bearbeiten möchten, verwenden Sie die Seite "Aktive Websites" im neuen SharePoint Admin Center.

![Die Spalte "Vertraulichkeit" auf der Seite "Aktive Websites"](media/manage-site-sensitivity-labels.png)

[Weitere Informationen zum Verwalten von Websites im neuen SharePoint Admin Center](/sharepoint/manage-sites-in-new-admin-center).

## <a name="change-site-and-group-settings-for-a-label"></a>Ändern von Website- und Gruppeneinstellungen für eine Bezeichnung

Wenn Sie eine Änderung an den Website- und Gruppeneinstellungen für eine Bezeichnung vornehmen, müssen Sie die folgenden PowerShell-Befehle ausführen, damit Ihre Teams, Websites und Gruppen die neuen Einstellungen verwenden können. Es wird empfohlen, die Website- und Gruppeneinstellungen für eine Bezeichnung nicht zu ändern, nachdem Sie die Bezeichnung auf mehrere Teams, Gruppen oder Websites angewendet haben.

1. Führen Sie die folgenden Befehle aus, um eine Verbindung mit PowerShell im Office 365 Security & Compliance Center herzustellen und die Liste der Vertraulichkeitsbezeichnungen und deren GUIDs abzurufen.
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid
    ```

2. Notieren Sie sich die GUID für die Bezeichnung(en), die Sie geändert haben.

3. Stellen Sie jetzt eine Verbindung mit Exchange Online PowerShell her, und führen Sie das Cmdlet "Get-UnifiedGroup" aus. Geben Sie dabei die GUID der Bezeichnung anstelle der Beispiel-GUID "e48058ea-98e8-4940-8db0-ba1310fd955e" an: 
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    $Groups= Get-UnifiedGroup | Where {$_.SensitivityLabel  -eq "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

4. Wenden Sie die Vertraulichkeitsbezeichnung für jede Gruppe unter Verwendung der Bezeichnungs-GUID anstelle der Beispiel-GUID "e48058ea-98e8-4940-8db0-ba1310fd955e" erneut an:
    
    ```powershell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

## <a name="support-for-the-new-sensitivity-labels"></a>Unterstützung der neuen Vertraulichkeitsbezeichnungen

Die folgenden Apps und Dienste unterstützen die Vertraulichkeitsbezeichnungen in dieser Vorschau:

- Microsoft 365 Compliance Center
- SharePoint
- Outlook im Web
- Microsoft Teams
- SharePoint Admin Center
- Azure AD Admin Center

Die folgenden Apps und Dienste können Sie nicht verwenden, um Office 365-Gruppen mit den neuen Vertraulichkeitsbezeichnungen zu erstellen:

- Outlook für Mac
- Outlook Mobile  
- Outlook Desktop für Windows
- Forms  
- Dynamics 365  
- Yammer  
- Stream  
- Planner  
- Project  
- PowerBI  
- Teams Admin Center  
- Microsoft 365 Admin Center  
- Exchange Admin Center

## <a name="if-you-used-classic-azure-ad-site-classification"></a>Sie haben die klassische Azure AD-Websiteklassifizierung verwendet

Wenn Sie diese Vorschau aktivieren, unterstützt Office 365 die alten Klassifizierungen nicht mehr für neue Gruppen und SharePoint-Websites. Bei vorhandenen Gruppen und Websites werden die alten Klassifizierungen jedoch weiterhin angezeigt, es sei denn, Sie konvertieren sie. Alte Klassifizierungen schließen die Klassifizierung von "modernen" Websites ein, die Sie möglicherweise über Azure AD PowerShell oder die PnP Core-Bibliothek eingerichtet haben, in der Werte für die `ClassificationList`-Einstellung definiert werden.

Beispielsweise in PowerShell:

```powershell
   ($setting["ClassificationList"])
```

Weitere Informationen zur alten Klassifizierungsmethode finden Sie unter ["" ](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).

Basierend auf Ihrer aktuellen Bereitstellung stehen Ihnen zwei Optionen zum Konvertieren Ihrer alten Klassifizierungen in die neuen Klassifizierungen zur Verfügung.

### <a name="if-you-never-used-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a>Sie haben noch nie Vertraulichkeitsbezeichnungen (einheitliche Microsoft Information Protection-Bezeichnungen) für Dateien und E-Mail verwendet

Wir empfehlen, dass Sie wie folgt vorgehen:

1. Erstellen Sie im Microsoft 365 Compliance Center neue Vertraulichkeitsbezeichnungen mit denselben Namen wie Ihre vorhandenen Klassifizierungen.
2. Verwenden Sie PowerShell, um die neuen Bezeichnungen mithilfe von Namenszuordnung auf vorhandene Office 365-Gruppen und SharePoint-Websites anzuwenden.
3. Löschen Sie die alten Klassifizierungen.

Apps und Dienste, die die neuen Vertraulichkeitsbezeichnungen unterstützen, werden angezeigt. Sie erstellen neue Teams, Gruppen und Websites mit den neuen Bezeichnungen. Benutzer können weiterhin Gruppen aus Apps und Diensten erstellen, die die neuen Bezeichnungen nicht unterstützen. Benutzer können jedoch keine Bezeichnung auf diese Gruppen anwenden. Verwenden Sie PowerShell, um die neuen Vertraulichkeitsbezeichnungen auf diese Gruppen anzuwenden.

Sie können Ihre alten Klassifizierungen beibehalten. Allerdings wird dringend empfohlen, PowerShell zu verwenden, um auf diese Gruppen die neuen Vertraulichkeitsbezeichnungen anzuwenden.

Apps und Dienste, die die neuen Vertraulichkeitsbezeichnungen unterstützen, werden mit den neuen Bezeichnungen erstellt. Wenn Benutzer Gruppen aus Apps und Diensten erstellen, die die neuen Bezeichnungen nicht unterstützen, können sie eine Klassifizierung auswählen.

### <a name="if-you-use-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a>Sie verwenden bereits Vertraulichkeitsbezeichnungen (einheitliche Microsoft Information Protection-Bezeichnungen) für Dateien und E-Mail

Nachdem Sie diese Vorschau aktiviert haben, wechseln Sie zu den einzelnen Bezeichnungen im Microsoft 365 Compliance Center, und wenden Sie die gewünschten Richtlinien für Websites und Gruppen an. Benutzer sehen nun Ihre vorhandenen Bezeichnungen, die für Websites und Gruppen zur Verfügung stehen.

### <a name="prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups"></a>Vorbereiten der SharePoint Online-Verwaltungsshell vor dem Anwenden neuer Bezeichnungen auf Office 365-Gruppen

Bevor Sie neue Bezeichnungen anwenden, stellen Sie sicher, dass Sie die neueste SharePoint Online-Verwaltungsshell ausführen. Wenn Sie bereits über die neueste Version verfügen, können Sie fortfahren und [Office 365-Gruppen neue Vertraulichkeitsbezeichnungen zuweisen](#relabel-office-365-groups-with-new-sensitivity-labels).

So bereiten Sie die SharePoint Online-Verwaltungsshell für die Vorschau vor

1. Wenn Sie eine frühere Version der SharePoint Online-Verwaltungsshell installiert haben, wechseln Sie zu **Software hinzufügen oder entfernen**, und deinstallieren Sie die "SharePoint Online-Verwaltungsshell".

2. Wechseln Sie in einem Webbrowser zur Download Center-Seite, und [laden Sie die neueste SharePoint Online-Verwaltungsshell herunter](https://go.microsoft.com/fwlink/p/?LinkId=255251).

3. Wählen Sie die gewünschte Sprache aus, und klicken Sie auf **Download**.

4. Wählen Sie zwischen der x64- und der x86-Version der MSI-Datei aus. Laden Sie die x64-Datei herunter, wenn Sie die 64-Bit-Version von Windows ausführen, bzw. die x86-Datei, wenn Sie die 32-Bit-Version ausführen. Wenn Sie sich nicht sicher sind, ziehen Sie [Welche Version des Windows-Betriebssystems verwende ich?](https://support.microsoft.com/help/13443/windows-which-operating-system) zurate.

5. Nachdem Sie die Datei heruntergeladen haben, führen Sie sie aus, und folgen Sie den Schritten im Setup-Assistenten.

### <a name="relabel-office-365-groups-with-new-sensitivity-labels"></a>Zuweisen der neuen Vertraulichkeitsbezeichnungen zu Office 365-Gruppen

1. Stellen Sie sicher, dass Sie die neueste Version der SharePoint Online-Verwaltungsshell verwenden. Anweisungen finden Sie unter [Vorbereiten der SharePoint Online-Verwaltungsshell vor dem Anwenden neuer Bezeichnungen auf Office 365-Gruppen](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).

2. Stellen Sie unter Verwendung eines Geschäfts-, Schul- oder Unikontos, das über globale Administrator- oder SharePoint-Administratorberechtigungen in Office 365 verfügt, eine Verbindung mit der SharePoint Online-Verwaltungsshell her. Eine Anleitung dazu finden Sie unter [Erste Schritte mit der SharePoint Online-Verwaltungsshell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

3. Führen Sie den folgenden Befehl aus, um die Liste der Vertraulichkeitsbezeichnungen und deren GUIDs abzurufen.

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

4. Notieren Sie sich die GUID für die Bezeichnung, die Sie überschreiben möchten. Beispielsweise die Bezeichnung "Allgemein".

5. Verwenden Sie den folgenden Befehl, um die Liste der Gruppen abzurufen, die die Klassifizierung "Allgemein" aufweisen. Wenn Sie diesen Befehl ausführen, stellen Sie eine Verbindung mit Exchange Online PowerShell her und führen das Cmdlet "Get-UnifiedGroup" aus.

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $UserCredential = Get-Credential
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   Import-PSSession $Session
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. Fügen Sie für jede Gruppe die neue Vertraulichkeitsbezeichnungs-GUID hinzu.

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```
