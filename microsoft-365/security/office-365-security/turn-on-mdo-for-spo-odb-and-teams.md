---
title: Aktivieren von Sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: Administratoren erfahren, wie Sie sichere Anlagen für SharePoint, OneDrive und Microsoft Teams aktivieren, einschließlich des Festlegens von Warnungen für erkannte Dateien.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 374e67626eab07cc8ab89a52554658a31e661eec
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929947"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Aktivieren von Sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft Defender für Office 365 für SharePoint, OneDrive und Microsoft Teams schützt Ihre Organisation davor, versehentlich schädliche Dateien freizugeben. Weitere Informationen finden Sie unter ["Sichere Anlagen" für SharePoint, OneDrive und Microsoft Teams.](mdo-for-spo-odb-and-teams.md)

Dieser Artikel enthält die Schritte zum Aktivieren und Konfigurieren von sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com>. Um direkt zur Seite **"Sichere Anlagen"** zu wechseln, öffnen Sie <https://security.microsoft.com/safeattachmentv2> .

- Um sichere Anlagen für SharePoint, OneDrive und Microsoft Teams zu aktivieren, müssen Sie Mitglied der Rollengruppen **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** im Microsoft 365 Defender-Portal sein. Weitere Informationen finden Sie unter [Berechtigungen im Microsoft 365 Defender-Portal.](permissions-in-the-security-and-compliance-center.md)

- Um SharePoint Online-PowerShell zu verwenden, um zu verhindern, dass Personen schädliche Dateien herunterladen, müssen Sie Mitglied der Rollen ["Globaler Administrator"](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) oder ["SharePoint"-Administrator](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) in Azure AD sein.

- Stellen Sie sicher, dass die Überwachungsprotokollierung für Ihre Organisation aktiviert ist. Weitere Informationen finden Sie unter [Aktivieren und Deaktivieren der Überwachungsprotokollsuche](../../compliance/turn-audit-log-search-on-or-off.md).

- Es kann bis zu 30 Minuten dauern, bis die Einstellungen wirksam werden.

## <a name="step-1-use-the-microsoft-365-defender-portal-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Schritt 1: Verwenden des Microsoft 365 Defender-Portals zum Aktivieren von sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams

1. Wechseln Sie im Microsoft 365 Defender-Portal zu **Richtlinien & Regeln** Für \> **Bedrohungsrichtlinien** sichere \> **Anlagen,** und klicken Sie auf **"Globale Einstellungen".**

2. Wechseln Sie in den angezeigten **globalen Einstellungen** zur Einstellung **"Defender für Office 365 aktivieren" für SharePoint, OneDrive und Microsoft Teams.** Verschieben Sie den Umschalter nach ![ rechts, ](../../media/scc-toggle-on.png) um sichere Anlagen für SharePoint, OneDrive und Microsoft Teams zu aktivieren.

   Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Verwenden von Exchange Online PowerShell zum Aktivieren von sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams

Wenn Sie lieber PowerShell verwenden möchten, um sichere Anlagen für SharePoint, OneDrive und Microsoft Teams zu aktivieren, [stellen Sie eine Verbindung mit Exchange Online PowerShell her,](/powershell/exchange/connect-to-exchange-online-powershell) und führen Sie den folgenden Befehl aus:

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-AtpPolicyForO365".](/powershell/module/exchange/set-atppolicyforo365)

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a>Schritt 2: (Empfohlen) Verwenden sie SharePoint Online-PowerShell, um zu verhindern, dass Benutzer schädliche Dateien herunterladen

Standardmäßig können Benutzer keine schädlichen Dateien öffnen, verschieben, kopieren oder freigeben, die von ATP erkannt werden. Sie können jedoch schädliche Dateien löschen und herunterladen.

Um zu verhindern, dass Benutzer schädliche Dateien herunterladen, [stellen Sie eine Verbindung mit SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) her, und führen Sie den folgenden Befehl aus:

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

**Hinweise**:

- Diese Einstellung wirkt sich sowohl auf Benutzer als auch auf Administratoren aus.
- Personen können weiterhin schädliche Dateien löschen.

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-SPOTenant".](/powershell/module/sharepoint-online/Set-SPOTenant)

## <a name="step-3-recommended-use-the-microsoft-365-defender-portal-to-create-an-alert-policy-for-detected-files"></a>Schritt 3 (Empfohlen) Verwenden sie das Microsoft 365 Defender-Portal, um eine Warnungsrichtlinie für erkannte Dateien zu erstellen.

Sie können eine Benachrichtigungsrichtlinie erstellen, die Sie und andere Administratoren benachrichtigt, wenn sichere Anlagen für SharePoint, OneDrive und Microsoft Teams eine schädliche Datei erkennt. Weitere Informationen zu Warnungen finden Sie unter [Erstellen von Aktivitätswarnungen im Microsoft 365 Defender-Portal.](../../compliance/create-activity-alerts.md)

1. Wechseln Sie im [Microsoft 365 Defender-Portal](https://security.microsoft.com)zu **Richtlinien &** \> **Regelwarnungsrichtlinie,** oder öffnen Sie <https://security.microsoft.com/alertpolicies> .

2. Klicken Sie auf der Seite **"Warnungsrichtlinie"** auf **"Neue Warnungsrichtlinie".**

3. Der Assistent **für neue Warnungsrichtlinien** wird in einem Flyout geöffnet. Konfigurieren Sie auf der Seite **"Warnung benennen"** die folgenden Einstellungen:

   - **Name:** Geben Sie einen eindeutigen und beschreibenden Namen ein. Beispielsweise schädliche Dateien in Bibliotheken.
   - **Beschreibung:** Geben Sie eine optionale Beschreibung ein. Benachrichtigt Administratoren beispielsweise, wenn schädliche Dateien in SharePoint Online, OneDrive oder Microsoft Teams erkannt werden.
   - **Schweregrad:** Lassen Sie den Standardwert **Niedrig** ausgewählt, oder wählen Sie **Mittel** oder **Hoch** aus.
   - **Kategorie:** Auswählen **der Bedrohungsverwaltung**.

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

4. Konfigurieren Sie auf der Seite **"Warnungseinstellungen erstellen"** die folgenden Einstellungen:

   - **Was möchten Sie warnen?: Aktivität ist:** Wählen Sie **erkannte Schadsoftware in Datei** aus.
   - **Wie soll die Warnung ausgelöst werden?**: Behalten Sie den Standardwert **bei, wenn eine Aktivität mit der** ausgewählten Regel übereinstimmt.

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

5. Konfigurieren Sie auf der Seite **"Empfänger festlegen"** die folgenden Einstellungen:

   - **Senden von E-Mail-Benachrichtigungen:** Überprüfen Sie, ob diese Einstellung ausgewählt ist. Wählen Sie im Feld **"E-Mail-Empfänger"** einen oder mehrere globale Administratoren, Sicherheitsadministratoren oder Sicherheitsleser aus, die eine Benachrichtigung erhalten sollen, wenn eine schädliche Datei erkannt wird.
   - **Grenzwert für tägliche Benachrichtigungen:** Lassen Sie den Standardwert **Kein Grenzwert** ausgewählt.

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

6. Überprüfen Sie auf der Seite **"Einstellungen überprüfen"** die Einstellungen, und klicken Sie in einem der Abschnitte auf **"Bearbeiten",** um Änderungen vorzunehmen.

   Lassen Sie im Abschnitt **Möchten Sie die Richtlinie sofort aktivieren?** den Standardwert **Ja bei, und aktivieren Sie sie sofort.**

   Klicken Sie nach Abschluss des Vorgangs auf **Fertig stellen**.

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a>Verwenden von Security & Compliance PowerShell zum Erstellen einer Warnungsrichtlinie für erkannte Dateien

Wenn Sie lieber PowerShell verwenden möchten, um die gleiche Warnungsrichtlinie wie im vorherigen Abschnitt beschrieben zu erstellen, stellen Sie [eine Verbindung mit Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) her, und führen Sie den folgenden Befehl aus:

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

**Hinweis:** Der Standardwert _für den Schweregrad_ ist niedrig. Um Mittel oder Hoch anzugeben, fügen Sie den Parameter _"Severity"_ und den Wert in den Befehl ein.

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-ActivityAlert.](/powershell/module/exchange/new-activityalert)

### <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

- Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie sichere Anlagen für SharePoint, OneDrive und Microsoft Teams erfolgreich aktiviert haben:

  - Wechseln Sie im [Microsoft 365 Defender-Portal](https://security.microsoft.com)zu **Richtlinien & Regeln** für sichere \> Anlagen für **Bedrohungsrichtlinien,** wählen Sie globale Einstellungen aus, und überprüfen Sie den Wert der Einstellung \>  **"Defender für Office 365 aktivieren" für SharePoint, OneDrive und Microsoft Teams.** 

  - Führen Sie in Exchange Online PowerShell den folgenden Befehl aus, um die Eigenschafteneinstellung zu überprüfen:

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-AtpPolicyForO365".](/powershell/module/exchange/get-atppolicyforo365)

- Öffnen Sie SharePoint Online-PowerShell, und führen Sie den folgenden Befehl aus, um den Eigenschaftswert zu überprüfen, um zu überprüfen, ob Sie Personen erfolgreich am Herunterladen schädlicher Dateien gehindert haben:

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-SPOTenant".](/powershell/module/sharepoint-online/Set-SPOTenant)

- Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie eine Benachrichtigungsrichtlinie für erkannte Dateien erfolgreich konfiguriert haben:

  - Wechseln Sie im Microsoft 365 Defender-Portal zu **Richtlinien &** \> **Regelwarnungsrichtlinie,** \> wählen Sie die Warnungsrichtlinie aus, und überprüfen Sie die Einstellungen.

  - Ersetzen Sie in Microsoft 365 PowerShell des Defender-Portals \<AlertPolicyName\> durch den Namen der Warnungsrichtlinie, führen Sie den folgenden Befehl aus, und überprüfen Sie die Eigenschaftswerte:

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-ActivityAlert".](/powershell/module/exchange/get-activityalert)

- Verwenden Sie den [Bedrohungsschutzstatusbericht,](view-email-security-reports.md#threat-protection-status-report) um Informationen zu erkannten Dateien in SharePoint, OneDrive und Microsoft Teams anzuzeigen. Insbesondere können Sie die **Ansichtsdaten wie folgt verwenden: \> Inhalts-Schadsoftware-Ansicht.**