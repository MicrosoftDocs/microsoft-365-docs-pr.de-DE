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
description: Administratoren können erfahren, wie Sie globale Einstellungen (die Liste "Folgende URLs blockieren" und Schutz für Office 365-Apps) für sichere Links in Microsoft Defender für Office 365 anzeigen und konfigurieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d52a4dc5ed35ec73c1410d6428a581b098bf2c52
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287461"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>Konfigurieren der globalen Einstellungen für sichere Links in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!IMPORTANT]
> Dieser Artikel richtet sich an Geschäftskunden, die über [Microsoft Defender für Office 365](office-365-atp.md) verfügen. Informationen zu Safelinks in Outlook finden Sie unter Advanced [Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Sichere Links ist ein Feature in [Microsoft Defender für Office 365,](office-365-atp.md) das die URL-Überprüfung eingehender E-Mail-Nachrichten im Nachrichtenfluss sowie die Zeit der Klicküberprüfung von URLs und Links in E-Mail-Nachrichten und an anderen Speicherorten ermöglicht. Weitere Informationen finden Sie unter ["Sichere Links" in Microsoft Defender für Office 365.](atp-safe-links.md)

Sie konfigurieren die meisten Einstellungen für sichere Links in Richtlinien für sichere Links. Anweisungen finden Sie unter [Einrichten von Richtlinien für sichere Links in Microsoft Defender für Office 365.](set-up-atp-safe-links-policies.md)

Sichere Links verwenden jedoch auch globale Einstellungen, die für alle Benutzer gelten, die in aktiven Richtlinien für sichere Links enthalten sind. Diese globalen Einstellungsbereich:

- Die **Liste der folgenden URLs blockieren.** Weitere Informationen finden Sie unter ["Blockieren der folgenden URLs" für sichere Links.](atp-safe-links.md#block-the-following-urls-list-for-safe-links)
- Schutz sicherer Links für Office 365-Apps. Weitere Informationen finden Sie unter Einstellungen für [sichere Links für Office 365-Apps.](atp-safe-links.md#safe-links-settings-for-office-365-apps)

Sie können die globalen Einstellungen für sichere Links im Security & Compliance Center oder in PowerShell konfigurieren (Exchange Online PowerShell für berechtigte Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange Online-Postfächer, aber mit Microsoft Defender für Office 365-Add-On-Abonnements).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Die von den globalen Einstellungen für sichere Links bereitgestellten Features werden nur auf Benutzer angewendet, die in aktiven Richtlinien für sichere Links enthalten sind. Es gibt keine integrierte oder standardmäßige Richtlinie für sichere Links. Daher müssen Sie mindestens eine Richtlinie für sichere Links erstellen, damit diese globalen Einstellungen aktiv sind. Anweisungen finden Sie unter [Einrichten von Richtlinien für sichere Links in Microsoft Defender für Office 365.](set-up-atp-safe-links-policies.md)

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Um direkt zur Seite "Sichere **Links" zu** wechseln, verwenden Sie <https://protection.office.com/safelinksv2> .

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Security & Compliance Center Berechtigungen zugewiesen werden.
  - Zum Konfigurieren der globalen Einstellungen für sichere Links müssen Sie Mitglied der Rollengruppe **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** sein.
  - Für den schreibgeschützten Zugriff auf die globalen Einstellungen für sichere  Links müssen Sie Mitglied der Rollengruppe "Globaler Leser" oder **"Sicherheitsleseprogramm"** sein.

  Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

  **Hinweise**:

  - Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).
  - Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.

- Die empfohlenen Werte für die globalen Einstellungen für sichere Links finden Sie unter "Einstellungen für [sichere Links".](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings)

- Es kann bis zu 30 Minuten dauern, bis eine neue oder aktualisierte Richtlinie angewendet wird.

- [Microsoft Defender für Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365)werden ständig neue Features hinzugefügt. Wenn neue Features hinzugefügt werden, müssen Sie möglicherweise Anpassungen an Ihren vorhandenen Richtlinien für sichere Links vornehmen.

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a>Konfigurieren der Liste "Blockieren der folgenden URLs" im Security & Compliance Center

In **der Liste "Blockieren" der folgenden URLs** werden die Links identifiziert, die von der Überprüfung auf sichere Links in unterstützten Apps immer blockiert werden sollten. Weitere Informationen finden Sie unter ["Blockieren der folgenden URLs" für sichere Links.](atp-safe-links.md#block-the-following-urls-list-for-safe-links)

1. Wechseln Sie im Security & Compliance  Center zu "AtP-Sichere Links" für die Bedrohungsverwaltungsrichtlinie, und klicken Sie dann auf \>  \>  **"Globale Einstellungen".**

2. Wechseln Sie **in der** angezeigten Richtlinie für sichere Links für Ihre Organisation zum Feld "Folgende **URLs** blockieren".

3. Konfigurieren Sie einen oder mehrere Einträge, wie in der Eintragssyntax für die Liste ["Folgende URLs blockieren" beschrieben.](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)

   Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>Konfigurieren der Liste "Folgende URLs blockieren" in PowerShell

Weitere Informationen zur Eintragssyntax finden Sie in der Eintragssyntax für die Liste ["Blockieren der folgenden URLs".](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)

Mit dem **Cmdlet "Get-AtpPolicyForO365"** können Sie vorhandene Einträge in der Eigenschaft _"BlockURLs"_ anzeigen.

- Verwenden Sie die folgende Syntax in Exchange Online PowerShell oder Exchange Online Protection PowerShell, um Werte hinzuzufügen, die vorhandene Einträge ersetzen:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  In diesem Beispiel werden der Liste die folgenden Einträge hinzugefügt:

  - Blockieren Sie die Domäne, Unterdomänen und Pfade für fabrikam.com.
  - Blockieren der Unterdomänenforschung, aber nicht der übergeordneten Domäne oder anderer Unterdomänen in tailspintoys.com

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- Verwenden Sie die folgende Syntax, um Werte ohne Auswirkungen auf andere Einträge hinzuzufügen oder zu entfernen:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  In diesem Beispiel wird ein neuer Eintrag für adatum.com und der Eintrag für die fabrikam.com.

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a>Konfigurieren des Schutzes sicherer Links für Office 365-Apps im Security & Compliance Center

Der Schutz sicherer Links für Office 365-Apps gilt für Dokumente in unterstützten Office-Desktop-, Mobile- und Web-Apps. Weitere Informationen finden Sie unter Einstellungen für [sichere Links für Office 365-Apps.](atp-safe-links.md#safe-links-settings-for-office-365-apps)

1. Wechseln Sie im Security & Compliance  Center zu "AtP-Sichere Links" für die Bedrohungsverwaltungsrichtlinie, und klicken Sie dann auf \>  \>  **"Globale Einstellungen".**

2. Konfigurieren Sie **in** der angezeigten Richtlinie für sichere Links für Ihre Organisation die folgenden Einstellungen in den Einstellungen, die für Inhalte außer im Abschnitt "E-Mail" **gelten:**

   - **Office 365-Anwendungen:** Stellen Sie sicher, dass der Umschalter rechts ist, um sichere Links für unterstützte Office 365-Apps zu aktivieren: ![ Umschalten. ](../../media/scc-toggle-on.png)

   - **Nicht nachverfolgen, wenn** Benutzer auf "Sichere Links" klicken: Umschalten nach links, um Benutzerklicks im Zusammenhang mit blockierten URLs in unterstützten Office 365-Apps nachverfolgt: ![ Umschalten ](../../media/scc-toggle-off.png) .

   - Benutzer dürfen nicht auf sichere Links zur ursprünglichen **URL** klicken: Überprüfen Sie, ob die Umschalte auf der rechten Seite ist, um zu verhindern, dass Benutzer auf die ursprüngliche blockierte URL in unterstützten Office 365-Apps klicken: ![ Umschalten. ](../../media/scc-toggle-on.png)

   Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>Konfigurieren des Schutzes sicherer Links für Office 365-Apps in PowerShell

Wenn Sie lieber PowerShell zum Konfigurieren des Schutzes sicherer Links für Office 365-Apps verwenden möchten, verwenden Sie die folgende Syntax in Exchange Online PowerShell oder Exchange Online Protection PowerShell:

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

In diesem Beispiel werden die folgenden Einstellungen für den Schutz sicherer Links in Office 365-Apps konfiguriert:

- Sichere Links für Office 365-Apps sind aktiviert (der Parameter _"EnableSafeLinksForO365Clients"_ wird nicht verwendet, und der Standardwert ist $true).
- Benutzerklicks im Zusammenhang mit blockierten URLs in unterstützten Office 365-Apps werden nachverfolgt.
- Benutzer dürfen nicht auf die ursprüngliche blockierte URL in unterstützten Office 365-Apps klicken (wir verwenden den Parameter _"AllowClickThrough"_ nicht, und der Standardwert ist $false).

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).

## <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

Gehen Sie wie folgt vor, um sicherzustellen, dass Sie die globalen Einstellungen für sichere Links (die Liste "Folgende **URLs** blockieren" und die Office 365-App-Schutzeinstellungen) erfolgreich konfiguriert haben:

- Wechseln Sie im Security & Compliance  Center zu "AtP-Sichere Links" für die Bedrohungsverwaltung, klicken Sie auf "Globale Einstellungen", und überprüfen Sie die angezeigten Einstellungen \>  \> im Flyout. 

- Führen Sie in Exchange Online PowerShell oder Exchange Online Protection PowerShell den folgenden Befehl aus, und überprüfen Sie die Einstellungen:

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).
