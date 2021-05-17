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
ms.openlocfilehash: 1186c7856d0b979c483cf6dd1c0a010ab582e2ce
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644752"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Sichere Dokumente in Microsoft 365 E5

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Sichere Dokumente ist ein Feature in Microsoft 365 E5 oder Microsoft 365 E5 Security, das [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) zum Überprüfen von Dokumenten und Dateien verwendet, die in der geschützten Ansicht oder in Application [Guard](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46)für Office. [](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sichere Dokumente sind nur für Benutzer mit Microsoft 365 E5 *oder* *Microsoft 365 E5 Security* verfügbar. Diese Lizenzen sind nicht in Microsoft Defender für Office 365 enthalten.

- Sichere Dokumente werden in Microsoft 365 Apps for Enterprise (früher als Office 365 ProPlus bezeichnet) Version 2004 oder höher unterstützt.

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com>. Öffnen Sie , um direkt zur **Seite "ATP-sichere Anlagen" zu** <https://protection.office.com/safeattachmentv2> wechseln.

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen in **Exchange Online** Berechtigungen zugewiesen werden:
  - Zum Konfigurieren der Einstellungen für sichere Dokumente müssen Sie Mitglied der Rollengruppen **Organisationsverwaltung** oder **Sicherheitsadministrator** sein.
  - Für den schreibgeschützten Zugriff auf Einstellungen für sichere Dokumente müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Sicherheitsleser"** sein.

  Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).
  >
  > - Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.

### <a name="how-does-microsoft-handle-your-data"></a>Wie geht Microsoft mit Ihren Daten um?

Um Sie zu schützen, sendet Safe Documents Dateien zur Analyse an die [Microsoft Defender for Endpoint-Cloud.](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) Details dazu, wie Microsoft Defender for Endpoint Ihre Daten verarbeitet, finden Sie hier: [Microsoft Defender for Endpoint Datenspeicherung und Datenschutz.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)

Von sicheren Dokumenten gesendete Dateien werden in Defender nicht über die für die Analyse benötigte Zeit (in der Regel weniger als 24 Stunden) aufbewahrt.

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>Konfigurieren sicherer Dokumente mithilfe & Security & Compliance Center

1. Wechseln Sie im Security & Compliance Center **zu** Richtlinie für die Bedrohungsverwaltung \>  \> **ATP Sichere** Anlagen, und klicken Sie dann auf **Globale Einstellungen**.

2. Konfigurieren Sie **im angezeigten** Fly-Out der globalen Einstellungen die folgenden Einstellungen:

   - **Aktivieren Sie sichere Dokumente für Office** Clients: Verschieben Sie die Umschalte nach rechts, um das Feature zu aktivieren: ![ Umschalten auf ](../../media/scc-toggle-on.png) .

   - **Zulassen,** dass Personen durch die geschützte Ansicht klicken, auch wenn sichere Dokumente die Datei als schädlich identifizieren: Es wird empfohlen, diese Option deaktiviert zu lassen (lassen Sie die Umschalte nach links: ![ Umschalten ](../../media/scc-toggle-off.png) aus ).

   Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

   ![Einstellungen für sichere Dokumente nach Auswahl der globalen Einstellungen auf der Seite Sichere Anlagen.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>Verwenden Exchange Online PowerShell zum Konfigurieren sicherer Dokumente

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

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).

### <a name="onboard-to-the-microsoft-defender-for-endpoint-service-to-enable-auditing-capabilities"></a>Onboarding im Microsoft Defender for Endpoint Service, um Überwachungsfunktionen zu aktivieren

Um Microsoft Defender for Endpoint bereitstellen zu können, müssen Sie die verschiedenen Phasen der Bereitstellung durchgehen. Nach dem Onboarding können Sie die Überwachungsfunktionen im Security & Compliance Center konfigurieren.

Weitere Informationen finden Sie [unter Onboard to the Microsoft Defender for Endpoint service](/microsoft-365/security/defender-endpoint/onboarding). Wenn Sie zusätzliche Hilfe benötigen, lesen Sie [Troubleshoot Microsoft Defender for Endpoint onboarding issues](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding).

### <a name="how-do-i-know-this-worked"></a>Woher weiß ich, dass der Vorgang erfolgreich war?

Gehen Sie wie folgt vor, um zu überprüfen, ob Sie sichere Dokumente aktiviert und konfiguriert haben:

- Wechseln Sie im Security & Compliance  Center zu Bedrohungsverwaltungsrichtlinie \>  \> **ATP** Sichere Anlagen,   klicken Sie auf Globale Einstellungen, und überprüfen Sie die Schaltfläche Sichere Dokumente für **Office-Clients** aktivieren und Personen das Klicken auf geschützte Ansicht erlauben, auch wenn sichere Dokumente die Datei als schädliche Einstellungen identifizieren.

- Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, und überprüfen Sie die Eigenschaftswerte:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- Die folgenden Dateien stehen zum Testen des Schutzes sicherer Dokumente zur Verfügung. Diese Dokumente ähneln der EICAR.TXT zum Testen von An malware- und Antivirenlösungen. Die Dateien sind nicht schädlich, lösen aber schutz vor sicheren Dokumenten aus.

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
