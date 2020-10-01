---
title: Aktivieren von Office 365 ATP – SharePoint, OneDrive, & Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: Hier erfahren Sie, wie Sie ATP für SharePoint, OneDrive und Microsoft Teams aktivieren, einschließlich der Vorgehensweise zum Festlegen von Benachrichtigungen für erkannte Dateien.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1cd345ae74b81c23f92b9e9b7d712efa8b875503
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326901"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Aktivieren von ATP für SharePoint, OneDrive und Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Office 365 Advanced Threat Protection (ATP) für SharePoint, OneDrive und Microsoft Teams schützt Ihre Organisation vor versehentlicher Freigabe schädlicher Dateien. Weitere Informationen finden Sie unter [ATP für SharePoint, OneDrive und Microsoft Teams](atp-for-spo-odb-and-teams.md).

Dieser Artikel enthält die Schritte zum Aktivieren und Konfigurieren von ATP für SharePoint, OneDrive und Microsoft Teams.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com>. Um direkt zur Seite **ATP-sichere Anlagen** zu wechseln, öffnen Sie <https://protection.office.com/safeattachmentv2> .

- Um ATP für SharePoint, OneDrive und Microsoft Teams zu aktivieren, müssen Sie Mitglied der Rollengruppen " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " im Security & Compliance Center sein. Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

- Um SharePoint Online PowerShell zu verwenden, um zu verhindern, dass Benutzer böswillige Dateien herunterladen können, müssen Sie Mitglied der Rolle [globaler Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) oder [SharePoint-Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) in Azure AD sein.

- Stellen Sie sicher, dass die Überwachungsprotokollierung für Ihre Organisation aktiviert ist. For more information, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).

- Erlauben Sie bis zu 30 Minuten, bis die Einstellungen wirksam werden.

## <a name="step-1-use-the-security--compliance-center-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Schritt 1: Verwenden Sie das Security & Compliance Center, um ATP für SharePoint, OneDrive und Microsoft Teams zu aktivieren.

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Safe Attachments**, und klicken Sie auf **globale Einstellungen**.

2. Wechseln Sie in den angezeigten **globalen Einstellungen** zur Option **ATP für SharePoint, OneDrive und Microsoft Teams aktivieren** . Bewegen Sie die Umschaltfläche nach rechts, ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) um ATP für SharePoint, OneDrive und Microsoft Teams zu aktivieren.

   Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

### <a name="use-exchange-online-powershell-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Aktivieren von ATP für SharePoint, OneDrive und Microsoft Teams mithilfe Exchange Online PowerShell

Wenn Sie lieber mithilfe von PowerShell ATP für SharePoint, OneDrive und Microsoft Teams aktivieren möchten, stellen Sie [eine Verbindung mit Exchange Online PowerShell her](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) , und führen Sie den folgenden Befehl aus:

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a>Schritt 2: (empfohlen) verwenden SharePoint Online PowerShell, um zu verhindern, dass Benutzer schädliche Dateien herunterladen

Standardmäßig können Benutzer schädliche Dateien, die von ATP erkannt werden, nicht öffnen, verlagern, kopieren oder freigeben. Sie können jedoch schädliche Dateien löschen und herunterladen.

Um zu verhindern, dass Benutzer schädliche Dateien herunterladen, stellen [Sie eine Verbindung mit SharePoint Online PowerShell her](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) , und führen Sie den folgenden Befehl aus:

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

**Hinweise**:

- Diese Einstellung wirkt sich sowohl auf Benutzer als auch auf Administratoren aus.
- Personen können weiterhin bösartige Dateien löschen.

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a>Schritt 3 (empfohlen) Verwenden des Security & Compliance Center zum Erstellen einer Warnungs Richtlinie für erkannte Dateien

Sie können eine Warnungs Richtlinie erstellen, die Sie und andere Administratoren benachrichtigt, wenn ATP für SharePoint, OneDrive und Microsoft Teams eine bösartige Datei erkennt. Weitere Informationen zu Warnungen finden Sie unter [Erstellen von Aktivitäts Warnungen im Security & Compliance Center](../../compliance/create-activity-alerts.md).

1. Wechseln Sie im [Security & Compliance Center](https://protection.office.com) **zu Alerts** \> **Alerts Policies** oder Open <https://protection.office.com/alertpolicies> .

2. Klicken Sie auf der Seite **Warnungsrichtlinien** auf **neue Warnungs Richtlinie**.

3. Der Assistent für **neue Warnungsrichtlinien** wird in einem Fly Out geöffnet. Konfigurieren Sie auf der Seite **Ihre Benachrichtigung benennen** die folgenden Einstellungen:

   - **Name**: Geben Sie einen eindeutigen und beschreibenden Namen ein. Beispielsweise schädliche Dateien in Bibliotheken.
   - **Beschreibung**: Geben Sie eine optionale Beschreibung ein. Beispielsweise werden Administratoren benachrichtigt, wenn schädliche Dateien in SharePoint Online, OneDrive oder Microsoft Teams erkannt werden.
   - **Schweregrad**: lassen Sie den Standardwert **niedrig** ausgewählt, oder wählen Sie **Mittel** oder **hoch**aus.
   - **Wählen Sie eine Kategorie**aus: Wählen Sie **Threat Management**aus.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

4. Konfigurieren Sie auf der Seite **Benachrichtigungseinstellungen erstellen** die folgenden Einstellungen:

   - **Worauf möchten Sie warnen?: Aktivität lautet**: Wählen Sie **erkannte Schadsoftware in der Datei**aus.
   - **Wie soll die Warnung ausgelöst werden?**: lassen Sie den Standardwert **jedes Mal, wenn eine Aktivität mit der ausgewählten Regel übereinstimmt** .

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

5. Konfigurieren Sie auf der Seite " **Empfänger festlegen** " die folgenden Einstellungen:

   - **E-Mail-Benachrichtigungen senden**: Vergewissern Sie sich, dass diese Einstellung ausgewählt ist. Wählen Sie im Feld **e-Mail-Empfänger** einen oder mehrere globale Administratoren, Sicherheitsadministratoren oder Sicherheits Leser aus, die eine Benachrichtigung erhalten sollen, wenn eine Schadsoftware erkannt wird.
   - **Grenzwert für tägliche Benachrichtigungen**: lassen Sie den Standardwert **kein Grenzwert** ausgewählt.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

6. Überprüfen Sie auf der Seite **Ihre Einstellungen überprüfen** die Einstellungen, und klicken Sie in einem der Abschnitte auf **Bearbeiten** , um Änderungen vorzunehmen.

   Lassen Sie in der Seite möchten **Sie die Richtlinie sofort aktivieren?** den Standardwert **Yes, aktivieren Sie ihn auf der rechten Seite** aktiviert.

   Klicken Sie nach Abschluss des Vorgangs auf **Fertig stellen**.

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a>Verwenden von Security & Compliance PowerShell zum Erstellen einer Warnungs Richtlinie für erkannte Dateien

Wenn Sie lieber mithilfe von PowerShell dieselbe Warnungs Richtlinie wie im vorherigen Abschnitt beschrieben erstellen möchten, stellen Sie [eine Verbindung mit Security & Compliance Center PowerShell her](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) , und führen Sie den folgenden Befehl aus:

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

**Hinweis**: der Standardwert für den _Schweregrad_ ist niedrig. Um Mittel oder hoch anzugeben, schließen Sie den _Severity_ -Parameter und den Wert in den Befehl ein.

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).

### <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

- Um zu überprüfen, ob Sie ATP für SharePoint, OneDrive und Microsoft Teams erfolgreich aktiviert haben, führen Sie einen der folgenden Schritte aus:

  - Wechseln Sie im [Security & Compliance Center](https://protection.office.com)zu Richtlinien für die **Bedrohungs Verwaltung** \> **Policy** \> **ATP-sichere Anlagen**, wählen Sie **globale Einstellungen**aus, und überprüfen Sie den Wert der Einstellung **ATP für SharePoint, OneDrive und Microsoft Teams aktivieren** .

  - Führen Sie in Exchange Online PowerShell den folgenden Befehl aus, um die Eigenschafteneinstellung zu überprüfen:

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).

- Um zu überprüfen, ob Sie Benutzer erfolgreich für das Herunterladen schädlicher Dateien gesperrt haben, öffnen Sie SharePoint Online PowerShell, und führen Sie den folgenden Befehl aus, um den Eigenschaftswert zu überprüfen:

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).

- Führen Sie einen der folgenden Schritte aus, um sicherzustellen, dass Sie eine Warnungs Richtlinie für erkannte Dateien erfolgreich konfiguriert haben:

  - Wechseln Sie im Security & Compliance **Center zu** Alerts- \> **Warnungs** Richtlinien \> Wählen Sie die Warnungs Richtlinie aus, und überprüfen Sie die Einstellungen.

  - Ersetzen Sie in Security & Compliance Center PowerShell \<AlertPolicyName\> durch den Namen der Warnungs Richtlinie, führen Sie den folgenden Befehl aus, und überprüfen Sie die Eigenschaftswerte:

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).

- Verwenden Sie den [Threat Protection-Statusbericht](view-email-security-reports.md#threat-protection-status-report) , um Informationen zu erkannten Dateien in SharePoint, OneDrive und Microsoft Teams anzuzeigen. Insbesondere können Sie die Ansicht **Daten nach: Inhalts- \> Schadsoftware** verwenden.
