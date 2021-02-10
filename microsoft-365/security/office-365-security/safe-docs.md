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
ms.openlocfilehash: 47bb6c66d51575c91b829e9688a074aaf9a18ab5
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166651"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Sichere Dokumente in Microsoft 365 E5

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

"Sichere Dokumente" ist ein Feature in Microsoft 365 E5 oder Microsoft 365 E5 Security, das [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) zum Überprüfen von Dokumenten und Dateien verwendet, die in der geschützten Ansicht geöffnet [werden.](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sichere Dokumente sind nur für Benutzer mit *Microsoft 365 E5-* oder *Microsoft 365 E5 -Sicherheitslizenzen* verfügbar. Diese Lizenzen sind nicht in Microsoft Defender für Office 365-Pläne enthalten.

- Sichere Dokumente werden in Microsoft 365 Apps for Enterprise (früher bekannt als Office 365 ProPlus) Version 2004 oder höher unterstützt.

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com>. Öffnen Sie die Seite **"ATP-sichere Anlagen", um** direkt zur Seite "AtP-sichere Anlagen" zu <https://protection.office.com/safeattachmentv2> wechseln.

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Security & Compliance Center Berechtigungen zugewiesen werden.
  - Zum Konfigurieren der Einstellungen für sichere Dokumente müssen Sie Mitglied der Rollengruppe **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** sein.
  - Für den schreibgeschützten Zugriff auf Einstellungen für sichere  Dokumente müssen Sie Mitglied der Rollengruppe "Globaler Leser" oder "Sicherheitsleser"  sein.

  Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

  > [!NOTE]
  > 
  > - Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  >
  > - Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.

### <a name="how-does-microsoft-handle-your-data"></a>Wie geht Microsoft mit Ihren Daten um?

Um Sie zu schützen, sendet "Sichere Dokumente" Dateien zur Analyse an die [Microsoft Defender for Endpoint-Cloud.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) Details dazu, wie Microsoft Defender for Endpoint Ihre Daten verarbeitet, finden Sie hier: [Microsoft Defender für Endpunkt-Datenspeicherung und Datenschutz.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)

Von "Sichere Dokumente" gesendete Dateien werden in Defender nicht über die für die Analyse benötigte Zeit hinaus aufbewahrt (in der Regel weniger als 24 Stunden).

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>Konfigurieren sicherer Dokumente mithilfe & Security & Compliance Center

1. Wechseln Sie im Security & Compliance  Center zu "Richtlinie für die Bedrohungsverwaltung " \>  \> **ATP Sichere Anlagen",** und klicken Sie dann auf **"Globale Einstellungen".**

2. Konfigurieren Sie **im angezeigten** Flyout der globalen Einstellungen die folgenden Einstellungen:

   - **Aktivieren Sie "Sichere Dokumente für Office-Clients":** Umschalten nach rechts, um das Feature zu aktivieren: ![ Umschalten. ](../../media/scc-toggle-on.png)

   - **Zulassen,** dass Benutzer durch die geschützte Ansicht klicken, auch wenn "Sichere Dokumente" die Datei als bösartig identifiziert: Es wird empfohlen, diese Option deaktiviert zu lassen (umschalten sie links zu lassen: ![ Umschalten). ](../../media/scc-toggle-off.png)

   Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

   ![Einstellungen für sichere Dokumente nach Auswahl der globalen Einstellungen auf der Seite "Sichere Anlagen".](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>Konfigurieren sicherer Dokumente mithilfe von Exchange Online PowerShell

Verwenden Sie die folgende Syntax:

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- Der _Parameter "EnableSafeDocs"_ aktiviert oder deaktiviert "Sichere Dokumente" für die gesamte Organisation.
- Der _Parameter "AllowSafeDocsOpen"_ ermöglicht oder verhindert, dass Benutzer die geschützte Ansicht verlassen (d. h. das Dokument öffnen), wenn das Dokument als bösartig identifiziert wurde.

In diesem Beispiel wird "Sichere Dokumente" für die gesamte Organisation aktiviert und verhindert, dass Benutzer Dokumente öffnen, die in der geschützten Ansicht als bösartig eingestuft wurden.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).

### <a name="how-do-i-know-this-worked"></a>Woher weiß ich, dass der Vorgang erfolgreich war?

Um zu überprüfen, ob Sie "Sichere Dokumente" aktiviert und konfiguriert haben, gehen Sie wie folgt vor:

- Wechseln Sie im Security & Compliance  Center zu "Bedrohungsverwaltungsrichtlinie \>  \> **ATP**    Sichere Anlagen", klicken Sie auf "Globale Einstellungen", und überprüfen Sie die Schaltfläche "Sichere Dokumente für Office-Clients aktivieren", und lassen Sie zu, dass Benutzer durch die geschützte Ansicht klicken, auch wenn "Sichere Dokumente" die Datei als schädliche Einstellungen identifiziert.

- Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, und überprüfen Sie die Eigenschaftswerte:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- Die folgenden Dateien stehen zum Testen des Schutzes sicherer Dokumente zur Verfügung. Diese Dokumente ähneln der EICAR.TXT zum Testen von Ansoftware- und Antivirenlösungen. Die Dateien sind nicht schädlich, lösen aber den Schutz sicherer Dokumente aus.

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
