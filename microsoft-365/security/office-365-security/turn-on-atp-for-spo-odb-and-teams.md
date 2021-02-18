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
description: Administratoren können erfahren, wie Sie sichere Anlagen für SharePoint, OneDrive und Microsoft Teams aktivieren, einschließlich der Einrichtung von Warnungen für erkannte Dateien.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9688af82d194b1818d6bd3323d39bde51db20cb2
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286369"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Aktivieren von Sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Microsoft Defender für Office 365 für SharePoint, OneDrive und Microsoft Teams schützt Ihre Organisation vor der versehentlichen Freigabe schädlicher Dateien. Weitere Informationen finden Sie unter ["Sichere Anlagen" für SharePoint, OneDrive und Microsoft Teams.](atp-for-spo-odb-and-teams.md)

Dieser Artikel enthält die Schritte zum Aktivieren und Konfigurieren sicherer Anlagen für SharePoint, OneDrive und Microsoft Teams.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com>. Öffnen Sie die Seite **"ATP-sichere Anlagen", um** direkt zur Seite "AtP-sichere Anlagen" zu <https://protection.office.com/safeattachmentv2> wechseln.

- Um sichere Anlagen für SharePoint, OneDrive und Microsoft Teams zu aktivieren, müssen  Sie Mitglied der Rollengruppen "Organisationsverwaltung" oder "Sicherheitsadministrator" im Security & Compliance Center sein.  Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

- Um SharePoint Online PowerShell zu verwenden, um zu verhindern, dass Benutzer schädliche Dateien herunterladen, müssen Sie Mitglied der Globalen [Administratorrolle](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) oder der Rolle des [SharePoint-Administrators](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) in Azure AD sein.

- Stellen Sie sicher, dass die Überwachungsprotokollierung für Ihre Organisation aktiviert ist. Weitere Informationen finden Sie unter [Aktivieren und Deaktivieren der Überwachungsprotokollsuche](../../compliance/turn-audit-log-search-on-or-off.md).

- Es kann bis zu 30 Minuten dauern, bis die Einstellungen wirksam werden.

## <a name="step-1-use-the-security--compliance-center-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Schritt 1: Aktivieren sicherer Anlagen für SharePoint, OneDrive und Microsoft Teams mithilfe des Security & Compliance Centers

1. Wechseln Sie im Security & Compliance  Center zu "Richtlinie für die Bedrohungsverwaltung " \>  \> **ATP Sichere Anlagen",** und klicken Sie auf **"Globale Einstellungen".**

2. Wechseln Sie in den **angezeigten** globalen Einstellungen zur Einstellung "Defender für **Office 365 für SharePoint, OneDrive** und Microsoft Teams aktivieren". Verschieben Sie die Umschalte in die rechte Umschaltschalte, um "Sichere ![ ](../../media/scc-toggle-on.png) Anlagen" für SharePoint, OneDrive und Microsoft Teams zu aktivieren.

   Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Verwenden von Exchange Online PowerShell zum Aktivieren sicherer Anlagen für SharePoint, OneDrive und Microsoft Teams

Wenn Sie powerShell verwenden möchten, um sichere Anlagen für SharePoint, OneDrive und Microsoft Teams zu aktivieren, stellen Sie eine Verbindung mit [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) sicher, und führen Sie den folgenden Befehl aus:

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a>Schritt 2: (Empfohlen) Verwenden von SharePoint Online PowerShell, um zu verhindern, dass Benutzer schädliche Dateien herunterladen

Standardmäßig können Benutzer schädliche Dateien, die von ATP erkannt werden, nicht öffnen, verschieben, kopieren oder freigeben. Sie können jedoch schädliche Dateien löschen und herunterladen.

Um zu verhindern, dass Benutzer schädliche Dateien herunterladen, stellen Sie eine Verbindung mit [SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) bereit, und führen Sie den folgenden Befehl aus:

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

**Hinweise**:

- Diese Einstellung wirkt sich sowohl auf Benutzer als auch auf Administratoren aus.
- Personen können weiterhin schädliche Dateien löschen.

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a>Schritt 3 (empfohlen) Verwenden des Security & Compliance Center zum Erstellen einer Warnungsrichtlinie für erkannte Dateien

Sie können eine Warnungsrichtlinie erstellen, die Sie und andere Administratoren benachrichtigt, wenn sichere Anlagen für SharePoint, OneDrive und Microsoft Teams eine schädliche Datei erkennen. Weitere Informationen zu Warnungen finden Sie unter ["Erstellen von Aktivitätswarnungen" im Security & Compliance Center.](../../compliance/create-activity-alerts.md)

1. Wechseln Sie [im Security & Compliance Center](https://protection.office.com)zu Warnungsrichtlinien, oder öffnen Sie  \>  . <https://protection.office.com/alertpolicies>

2. Klicken Sie **auf der Seite "Warnungsrichtlinien"** auf **"Neue Warnungsrichtlinie".**

3. Der **Assistent für neue Benachrichtigungsrichtlinien** wird in einem Flyout geöffnet. Konfigurieren Sie **auf der Seite "Warnung benennen"** die folgenden Einstellungen:

   - **Name**: Geben Sie einen eindeutigen und beschreibenden Namen ein. Beispiel: Bösartige Dateien in Bibliotheken.
   - **Beschreibung:** Geben Sie eine optionale Beschreibung ein. Beispielsweise werden Administratoren benachrichtigt, wenn bösartige Dateien in SharePoint Online, OneDrive oder Microsoft Teams erkannt werden.
   - **Schweregrad:** Lassen Sie den Standardwert **"Niedrig"** ausgewählt, oder wählen Sie **"Mittel"** oder **"Hoch" aus.**
   - **Wählen Sie eine Kategorie aus:** Wählen Sie **Bedrohungsverwaltung aus.**

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

4. Konfigurieren Sie **auf der Seite "Benachrichtigungseinstellungen erstellen"** die folgenden Einstellungen:

   - **Was möchten Sie warnen?: Aktivität ist:** Erkannte **Schadsoftware in Datei auswählen.**
   - **Wie soll die Warnung ausgelöst werden?**: Lassen Sie den Standardwert jedes Mal, wenn eine **Aktivität der ausgewählten Regel** entspricht.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

5. Konfigurieren Sie **auf der Seite "Empfänger festlegen"** die folgenden Einstellungen:

   - **E-Mail-Benachrichtigungen** senden: Stellen Sie sicher, dass diese Einstellung ausgewählt ist. Wählen Sie im Feld "E-Mail-Empfänger" einen oder mehrere globale Administratoren, Sicherheitsadministratoren oder Sicherheitsleser aus, die eine Benachrichtigung erhalten sollen, wenn eine schädliche Datei erkannt wird. 
   - **Grenzwert für tägliche Benachrichtigungen:** Lassen Sie den Standardwert **"No limit"** ausgewählt.

   Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.

6. Überprüfen Sie auf der Seite "Einstellungen **überprüfen"** die Einstellungen, und klicken Sie **in** einem der Abschnitte auf "Bearbeiten", um Änderungen vorzunehmen.

   Lassen Sie **im Abschnitt "Möchten Sie die** Richtlinie sofort aktivieren?" den Standardwert "Ja" und "Sofort **aktivieren"** ausgewählt.

   Klicken Sie nach Abschluss des Vorgangs auf **Fertig stellen**.

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a>Verwenden von Security & Compliance PowerShell zum Erstellen einer Warnungsrichtlinie für erkannte Dateien

Wenn Sie powerShell verwenden möchten, um dieselbe Warnungsrichtlinie wie im vorherigen Abschnitt beschrieben zu erstellen, stellen Sie eine Verbindung mit [Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) auf, und führen Sie den folgenden Befehl aus:

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

**Hinweis:** Der Standardwert _für den Schweregrad_ ist "Niedrig". Um "Medium" oder "High" anzugeben, schließen Sie den _Parameter "Severity"_ und den Wert in den Befehl ein.

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).

### <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

- Verwenden Sie einen der folgenden Schritte, um sicherzustellen, dass Sie sichere Anlagen für SharePoint, OneDrive und Microsoft Teams erfolgreich aktiviert haben:

  - Wechseln Sie [im Security & Compliance](https://protection.office.com)  Center zur & "AtP-sichere Anlagen", wählen Sie globale Einstellungen aus, und überprüfen Sie den Wert der Einstellung "Defender für \>  \>  **Office 365 für SharePoint, OneDrive** und Microsoft Teams aktivieren". 

  - Führen Sie in Exchange Online PowerShell den folgenden Befehl aus, um die Einstellung der Eigenschaft zu überprüfen:

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).

- Öffnen Sie SharePoint Online PowerShell, und führen Sie den folgenden Befehl aus, um den Eigenschaftswert zu überprüfen, um zu überprüfen, ob Personen erfolgreich schädliche Dateien heruntergeladen haben:

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).

- Verwenden Sie einen der folgenden Schritte, um sicherzustellen, dass Sie eine Warnungsrichtlinie für erkannte Dateien erfolgreich konfiguriert haben:

  - Wechseln Sie im Security & Compliance  Center zu Warnungsrichtlinien, wählen Sie die Warnungsrichtlinie \>  \> aus, und überprüfen Sie die Einstellungen.

  - Ersetzen Sie & Security & Compliance Center PowerShell durch den Namen der Warnungsrichtlinie, führen Sie den folgenden Befehl aus, und überprüfen Sie \<AlertPolicyName\> die Eigenschaftswerte:

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).

- Verwenden Sie [den Statusbericht zum Bedrohungsschutz,](view-email-security-reports.md#threat-protection-status-report) um Informationen zu erkannten Dateien in SharePoint, OneDrive und Microsoft Teams anzeigen. Insbesondere können Sie die Ansicht "Daten **anzeigen" verwenden, indem Sie die Ansicht \> "Schadsoftware für Inhalte"** verwenden.
