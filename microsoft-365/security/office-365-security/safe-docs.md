---
title: Sichere Dokumente in Microsoft Defender für Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Erfahren Sie mehr über sichere Dokumente in Microsoft 365 E5 oder Microsoft 365 E5 Security.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 75dfa9e5687a4c4b561067190e7ce338074b2f66
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407420"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Sichere Dokumente in Microsoft 365 E5

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 – Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Sichere Dokumente ist ein Feature in Microsoft 365 E5 oder Microsoft 365 E5 Security, das [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) zum Überprüfen von Dokumenten und Dateien verwendet, die in der geschützten Ansicht geöffnet [werden.](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sichere Dokumente sind nur für Benutzer mit *Microsoft 365 E5-* oder *Microsoft 365 E5-Sicherheitslizenzen* verfügbar. Diese Lizenzen sind nicht in Microsoft Defender für Office 365-Pläne enthalten.

- Sichere Dokumente werden in Microsoft 365 Apps for Enterprise (früher als Office 365 ProPlus bezeichnet) Version 2004 oder höher unterstützt.

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com>. Öffnen Sie , um direkt zur **Seite "ATP-sichere Anlagen" zu** <https://protection.office.com/safeattachmentv2> wechseln.

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen in **Exchange Online** die entsprechenden Berechtigungen zugewiesen werden:
  - Zum Konfigurieren der Einstellungen für sichere Dokumente müssen Sie Mitglied der Rollengruppen **Organisationsverwaltung** oder **Sicherheitsadministrator** sein.
  - Für den schreibgeschützten Zugriff auf Einstellungen für sichere Dokumente müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Sicherheitsleser"** sein.

  Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - Durch hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft  365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen und Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).
  >
  > - Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.

### <a name="how-does-microsoft-handle-your-data"></a>Wie geht Microsoft mit Ihren Daten um?

Um Sie zu schützen, sendet Safe Documents Dateien zur Analyse an die [Microsoft Defender for Endpoint-Cloud.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) Details dazu, wie Microsoft Defender for Endpoint Ihre Daten verarbeitet, finden Sie hier: [Microsoft Defender for Endpoint Datenspeicherung und Datenschutz.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)

Von sicheren Dokumenten gesendete Dateien werden in Defender nicht über die für die Analyse benötigte Zeit (in der Regel weniger als 24 Stunden) aufbewahrt.

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>Konfigurieren sicherer Dokumente mithilfe & Security & Compliance Center

1. Wechseln Sie im Security & Compliance Center **zu** Richtlinie für die Bedrohungsverwaltung \>  \> **ATP Sichere** Anlagen, und klicken Sie dann auf **Globale Einstellungen**.

2. Konfigurieren Sie **im angezeigten** Fly-Out der globalen Einstellungen die folgenden Einstellungen:

   - **Aktivieren Sie sichere Dokumente für Office-Clients:** Verschieben Sie die Umschalte nach rechts, um das Feature zu aktivieren: ![ Umschalten auf ](../../media/scc-toggle-on.png) .

   - **Zulassen,** dass Personen durch die geschützte Ansicht klicken, auch wenn sichere Dokumente die Datei als schädlich identifizieren: Es wird empfohlen, diese Option deaktiviert zu lassen (lassen Sie die Umschalte nach links: ![ Umschalten ](../../media/scc-toggle-off.png) aus ).

   Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

   ![Einstellungen für sichere Dokumente nach Auswahl der globalen Einstellungen auf der Seite Sichere Anlagen.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>Konfigurieren sicherer Dokumente mithilfe von Exchange Online PowerShell

Verwenden Sie die folgende Syntax:

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- Der _Parameter EnableSafeDocs_ aktiviert oder deaktiviert sichere Dokumente für die gesamte Organisation.
- Der _Parameter AllowSafeDocsOpen_ ermöglicht oder verhindert, dass Benutzer die geschützte Ansicht verlassen (d. h. das Dokument öffnen), wenn das Dokument als schadhaft identifiziert wurde.

In diesem Beispiel werden sichere Dokumente für die gesamte Organisation aktiviert und verhindert, dass Benutzer Dokumente öffnen, die in der geschützten Ansicht als bösartig identifiziert wurden.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).

### <a name="how-do-i-know-this-worked"></a>Woher weiß ich, dass der Vorgang erfolgreich war?

Gehen Sie wie folgt vor, um zu überprüfen, ob Sie sichere Dokumente aktiviert und konfiguriert haben:

- Wechseln Sie im Security & Compliance  Center zu Bedrohungsverwaltungsrichtlinie \>  \> **ATP**    Sichere Anlagen, klicken Sie auf Globale Einstellungen, und überprüfen Sie die Schaltfläche Sichere Dokumente für Office-Clients aktivieren und Personen das Klicken auf geschützte Ansicht erlauben, auch wenn sichere Dokumente die Datei als schädliche Einstellungen identifizieren.

- Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, und überprüfen Sie die Eigenschaftswerte:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- Die folgenden Dateien stehen zum Testen des Schutzes sicherer Dokumente zur Verfügung. Diese Dokumente ähneln der EICAR.TXT zum Testen von An malware- und Antivirenlösungen. Die Dateien sind nicht schädlich, lösen aber schutz vor sicheren Dokumenten aus.

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
