---
title: Konfigurieren globaler Einstellungen für Einstellungen für sichere Links in Defender für Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratoren erfahren, wie Sie globale Einstellungen (die Liste "Blockieren der folgenden URLs" und Schutz für Office 365-Apps) für sichere Links in Microsoft Defender für Office 365 anzeigen und konfigurieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 390177a24648cf860a78ab831d5dfe334b2c9590
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065383"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>Konfigurieren globaler Einstellungen für sichere Links in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Dieser Artikel richtet sich an Geschäftskunden, die über [Microsoft Defender für Office 365](defender-for-office-365.md) verfügen. Informationen zu Safelinks in Outlook finden Sie unter [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Sichere Links ist ein Feature in [Microsoft Defender für Office 365,](defender-for-office-365.md) das die URL-Überprüfung eingehender E-Mail-Nachrichten im E-Mail-Fluss sowie die Zeit der Klicküberprüfung von URLs und Links in E-Mail-Nachrichten und an anderen Speicherorten ermöglicht. Weitere Informationen finden Sie unter [Sichere Links in Microsoft Defender für Office 365](safe-links.md).

Sie konfigurieren die meisten Einstellungen für sichere Links in Richtlinien für sichere Links. Anweisungen finden Sie unter Einrichten von Richtlinien für sichere [Links in Microsoft Defender für Office 365](set-up-safe-links-policies.md).

Sichere Links verwenden jedoch auch globale Einstellungen, die für alle Benutzer gelten, die in allen aktiven Richtlinien für sichere Links enthalten sind. Diese globalen Einstellungen:

- The **Block the following URLs** list. Weitere Informationen finden Sie unter ["Blockieren der folgenden URLs" für sichere Links.](safe-links.md#block-the-following-urls-list-for-safe-links)
- Schutz für sichere Links für Office 365-Apps. Weitere Informationen finden Sie unter [Einstellungen für sichere Links für Office 365-Apps](safe-links.md#safe-links-settings-for-office-365-apps).

Sie können die globalen Einstellungen für sichere Links im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für berechtigte Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige eOP PowerShell für Organisationen ohne Exchange &, aber mit Microsoft Defender für Office 365-Add-On-Abonnements) konfigurieren.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Die features provided by global settings for Safe Links are applied only to users who are included in active Safe Links policies. Es gibt keine integrierte oder standardmäßige Richtlinie für sichere Links, daher müssen Sie mindestens eine Richtlinie für sichere Links erstellen, damit diese globalen Einstellungen aktiv sind. Anweisungen finden Sie unter Einrichten von Richtlinien für sichere [Links in Microsoft Defender für Office 365](set-up-safe-links-policies.md).

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Um direkt zur Seite **"Sichere Links" zu** wechseln, verwenden Sie <https://protection.office.com/safelinksv2> .

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Sie müssen in **Exchange Online** Berechtigungen erhalten, bevor Sie die in diesem Artikel beschriebenen Schritte ausführen können:
  - Zum Konfigurieren der globalen Einstellungen für sichere Links müssen  Sie Mitglied der Rollengruppen Organisationsverwaltung oder **Sicherheitsadministrator** sein.
  - Für den schreibgeschützten Zugriff auf die globalen Einstellungen für sichere Links müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Sicherheitsleser"** sein.

  Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Hinweise**:

  - Durch Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).
  - Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.

- Unsere empfohlenen Werte für die globalen Einstellungen für sichere Links finden Sie unter [Safe Links settings](recommended-settings-for-eop-and-office365.md#safe-links-settings).

- Es ist bis zu 30 Minuten zulässig, bis eine neue oder aktualisierte Richtlinie angewendet wird.

- [Microsoft Defender für Office 365 werden](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)ständig neue Features hinzugefügt. Wenn neue Features hinzugefügt werden, müssen Sie möglicherweise Anpassungen an Ihren vorhandenen Richtlinien für sichere Links vornehmen.

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a>Konfigurieren der Liste "Blockieren der folgenden URLs" im Security & Compliance Center

In **der Liste Blockieren der folgenden URLs** werden die Links identifiziert, die von der Überprüfung sicherer Links in unterstützten Apps immer blockiert werden sollten. Weitere Informationen finden Sie unter ["Blockieren der folgenden URLs" für sichere Links](safe-links.md#block-the-following-urls-list-for-safe-links).

1. Wechseln Sie im Security & Compliance Center **zu** Richtlinie für die Bedrohungsverwaltung \>  \> **ATP Sichere Links,** und klicken Sie dann auf **Globale Einstellungen**.

2. Wechseln Sie **in der angezeigten** Richtlinie für sichere Links für Ihre Organisation zum Feld **Blockieren des folgenden URLs.**

3. Konfigurieren Sie einen oder mehrere Einträge, wie unter [Entry syntax for the "Block the following URLs" list beschrieben.](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)

   Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>Konfigurieren der Liste "Blockieren der folgenden URLs" in PowerShell

Weitere Informationen zur Eintragssyntax finden Sie unter [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).

Mit dem **Cmdlet Get-AtpPolicyForO365** können Sie vorhandene Einträge in der _BlockURLs-Eigenschaft_ anzeigen.

- Verwenden Sie die folgende Syntax in Exchange Online PowerShell oder Exchange Online Protection PowerShell, um Werte hinzuzufügen, die vorhandene Einträge ersetzen:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  In diesem Beispiel werden der Liste die folgenden Einträge hinzugefügt:

  - Blockieren sie die Domäne, Unterdomänen und Pfade für fabrikam.com.
  - Blockieren der Unterdomänenforschung, aber nicht der übergeordneten Domäne oder anderer Unterdomänen in tailspintoys.com

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- Verwenden Sie die folgende Syntax, um Werte hinzuzufügen oder zu entfernen, ohne sich auf andere vorhandene Einträge zu beeinflussen:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  In diesem Beispiel wird ein neuer Eintrag für adatum.com und der Eintrag für fabrikam.com.

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a>Konfigurieren des Schutzes sicherer Links für Office 365-Apps im Security & Compliance Center

Der Schutz sicherer Links für Office 365-Apps gilt für Dokumente in unterstützten Office-Desktop-, Mobile- und Web-Apps. Weitere Informationen finden Sie unter [Einstellungen für sichere Links für Office 365-Apps](safe-links.md#safe-links-settings-for-office-365-apps).

1. Wechseln Sie im Security & Compliance Center **zu** Richtlinie für die Bedrohungsverwaltung \>  \> **ATP Sichere Links,** und klicken Sie dann auf **Globale Einstellungen**.

2. Konfigurieren Sie **in** der angezeigten Richtlinie für sichere Links für Ihre Organisation die folgenden Einstellungen im Abschnitt Einstellungen, die für Inhalte außer E-Mail **gelten:**

   - **Office 365-Anwendungen:** Überprüfen Sie, ob der Umschalter rechts ist, um sichere Links für unterstützte Office 365-Apps zu ![ aktivieren: Umschalten auf ](../../media/scc-toggle-on.png) .

   - **Nicht nachverfolgen, wenn** Benutzer auf sichere Links klicken: Verschieben Sie die Umschalte nach links, um Benutzerklicks im Zusammenhang mit blockierten URLs in unterstützten Office 365-Apps nachverfolgt zu werden: ![ Umschalten ](../../media/scc-toggle-off.png) .

   - Benutzer dürfen nicht auf sichere Links zur ursprünglichen **URL** klicken: Überprüfen Sie, ob der Umschalter rechts ist, um zu verhindern, dass Benutzer zur ursprünglichen blockierten URL in unterstützten Office 365-Apps klicken: ![ Umschalten auf ](../../media/scc-toggle-on.png) .

   Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>Konfigurieren des Schutzes sicherer Links für Office 365-Apps in PowerShell

Wenn Sie lieber PowerShell zum Konfigurieren des Schutzes sicherer Links für Office 365-Apps verwenden möchten, verwenden Sie die folgende Syntax in Exchange Online PowerShell oder Exchange Online Protection PowerShell:

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

In diesem Beispiel werden die folgenden Einstellungen für den Schutz sicherer Links in Office 365-Apps konfiguriert:

- Sichere Links für Office 365-Apps sind aktiviert (wir verwenden nicht den _Parameter EnableSafeLinksForO365Clients,_ und der Standardwert ist $true).
- Benutzerklicks im Zusammenhang mit blockierten URLs in unterstützten Office 365-Apps werden nachverfolgt.
- Benutzer dürfen nicht zur ursprünglichen blockierten URL in unterstützten Office 365-Apps klicken (wir verwenden den _Parameter AllowClickThrough_ nicht, und der Standardwert ist $false).

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).

## <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

Gehen Sie wie folgt vor, um sicherzustellen, dass Sie die globalen Einstellungen für sichere Links erfolgreich konfiguriert haben (die Liste der folgenden **URLs** blockieren und die Office 365-App-Schutzeinstellungen):

- Wechseln Sie & Security & Compliance  Center zu Bedrohungsverwaltungsrichtlinie \>  \> **ATP Sichere Links,** klicken Sie auf **Globale** Einstellungen, und überprüfen Sie die Angezeigten Einstellungen.

- Führen Sie in Exchange Online PowerShell oder Exchange Online Protection PowerShell den folgenden Befehl aus, und überprüfen Sie die Einstellungen:

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).