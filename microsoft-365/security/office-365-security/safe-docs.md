---
title: Sichere Dokumente in Microsoft Defender für Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Erfahren Sie mehr über sichere Dokumente in Microsoft 365 E5 oder Microsoft 365 E5 Security.
ms.openlocfilehash: 0acb5d4ee0c80deebc4d0b040b046d63037037a7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659873"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Sichere Dokumente in Microsoft 365 E5

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Safe Documents ist ein Feature in Microsoft 365 E5 oder Microsoft 365 E5 Security, das [Microsoft Defender für Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) zum Überprüfen von Dokumenten und Dateien verwendet, die in der [geschützten Ansicht](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)geöffnet werden.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sichere Dokumente sind nur für Benutzer mit *Microsoft 365 E5* -oder *Microsoft 365 E5-Sicherheits* Lizenzen verfügbar. Diese Lizenzen sind nicht in Microsoft Defender für Office 365 Pläne enthalten.

- Sichere Dokumente werden in Microsoft 365 apps for Enterprise (früher als Office 365 ProPlus bezeichnet) Version 2004 oder höher unterstützt.

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com>. Um direkt zur Seite **ATP-sichere Anlagen** zu wechseln, öffnen Sie <https://protection.office.com/safeattachmentv2> .

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Security & Compliance Center Berechtigungen zugewiesen werden.
  - Zum Konfigurieren von Einstellungen für sichere Dokumente müssen Sie Mitglied der Rollengruppen " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " sein.
  - Für den schreibgeschützten Zugriff auf Einstellungen für sichere Dokumente müssen Sie Mitglied der Rollengruppen " **globaler Leser** " oder " **Sicherheits Leser** " sein.

  Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

  **Hinweise**:

  - Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.

### <a name="how-does-microsoft-handle-your-data"></a>Wie verarbeitet Microsoft Ihre Daten?

Damit Sie geschützt bleiben, sendet Safe Documents Dateien zur Analyse an den [Microsoft Defender für die Endpunkt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) Wolke. Ausführliche Informationen dazu, wie Microsoft Defender für Endpoint Ihre Daten verarbeitet, finden Sie hier: [Microsoft Defender for Endpoint Data Storage and Privacy](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).

Dateien, die von sicheren Dokumenten gesendet werden, werden in Defender nicht über die für die Analyse erforderliche Zeit hinweg aufbewahrt (in der Regel weniger als 24 Stunden).

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>Konfigurieren sicherer Dokumente mithilfe des Security & Compliance Center

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Safe Attachments**, und klicken Sie dann auf **globale Einstellungen**.

2. Konfigurieren Sie in den angezeigten **globalen Einstellungen** die folgenden Einstellungen:

   - **Aktivieren sicherer Dokumente für Office-Clients**: bewegen Sie die Umschaltfläche nach rechts, um das Feature zu aktivieren: Einschalten ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .

   - **Personen können durch die geschützte Ansicht klicken, selbst wenn sichere Dokumente die Datei als bösartig Kenn** zeichnen: Es wird empfohlen, diese Option deaktiviert zu lassen (lassen Sie die Umschaltfläche Links: ![ Deaktivieren ](../../media/scc-toggle-off.png) ).

   Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

   ![Einstellungen für sichere Dokumente nach dem auswählen globaler Einstellungen auf der Seite sichere Anlagen.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>Konfigurieren sicherer Dokumente mithilfe Exchange Online PowerShell

Verwenden Sie die folgende Syntax:

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- Der Parameter _EnableSafeDocs_ aktiviert oder deaktiviert sichere Dokumente für die gesamte Organisation.
- Der Parameter _AllowSafeDocsOpen_ ermöglicht oder verhindert, dass Benutzer die geschützte Ansicht (also das Öffnen des Dokuments) verlassen, wenn das Dokument als bösartig gekennzeichnet wurde.

In diesem Beispiel werden sichere Dokumente für die gesamte Organisation aktiviert, und es wird verhindert, dass Benutzer Dokumente öffnen, die als "bösartig" aus geschützter Ansicht identifiziert wurden.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).

### <a name="how-do-i-know-this-worked"></a>Woher weiß ich, dass der Vorgang erfolgreich war?

Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie sichere Dokumente aktiviert und konfiguriert haben:

- Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **ATP Attachments**, klicken Sie auf **globale Einstellungen**, und überprüfen Sie die **Option sichere Dokumente für Office-Clients aktivieren** , und **ermöglichen Sie den Benutzern, durch die geschützte Ansicht zu klicken, selbst wenn die Datei von sicheren Dokumenten als schädliche Einstellungen identifiziert** wird.

- Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, und überprüfen Sie die Eigenschaftswerte:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- Die folgenden Dateien sind verfügbar, um den Schutz geschützter Dokumente zu testen. Diese Dokumente ähneln der EICAR.TXT Datei zum Testen von Antischadsoftware-und Antivirenprogramme. Die Dateien sind nicht schädlich, aber Sie werden Schutz für sichere Dokumente auslösen.

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
