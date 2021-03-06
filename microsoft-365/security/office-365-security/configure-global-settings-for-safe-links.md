---
title: Konfigurieren globaler Einstellungen für Tresor Links-Einstellungen in Defender für Office 365
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
description: Administratoren erfahren, wie sie globale Einstellungen (die Liste "Die folgenden URLs blockieren" und den Schutz für Office 365-Apps) für Tresor Links in Microsoft Defender für Office 365 anzeigen und konfigurieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 46bafd89400dfa551641c055f6f0e208c0ecd49f
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108043"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>Konfigurieren globaler Einstellungen für Tresor Links in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Dieser Artikel richtet sich an Geschäftskunden, die über [Microsoft Defender für Office 365](defender-for-office-365.md) verfügen. Wenn Sie ein Privatbenutzer sind, der nach Informationen zu Safelinks in Outlook sucht, finden Sie weitere Informationen unter [Advanced Outlook.com Security.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)

Tresor Links ist ein Feature in [Microsoft Defender für Office 365,](defender-for-office-365.md) das die URL-Überprüfung eingehender E-Mail-Nachrichten im E-Mail-Fluss sowie den Zeitpunkt der Klicküberprüfung von URLs und Links in E-Mail-Nachrichten und an anderen Speicherorten ermöglicht. Weitere Informationen finden Sie unter [Tresor Links in Microsoft Defender für Office 365](safe-links.md).

Sie konfigurieren die meisten Einstellungen für Tresor Links in Tresor Links-Richtlinien. Anweisungen finden Sie unter ["Einrichten Tresor Links"-Richtlinien in Microsoft Defender für Office 365.](set-up-safe-links-policies.md)

Tresor Links verwendet jedoch auch die folgenden globalen Einstellungen, die Sie außerhalb der Richtlinien für Tresor Links selbst konfigurieren:

- Die **Liste der folgenden URLs blockieren.** Diese Einstellung gilt für alle Benutzer, die in allen aktiven Richtlinien für Tresor Links enthalten sind. Weitere Informationen finden Sie unter ["Blockieren der folgenden URLs" für Tresor Links](safe-links.md#block-the-following-urls-list-for-safe-links)
- Tresor Linksschutz für Office 365 Apps. Diese Einstellungen gelten für alle Benutzer in der Organisation, die für Defender für Office 365 lizenziert sind, unabhängig davon, ob die Benutzer in den aktiven Richtlinien für Tresor Links enthalten sind oder nicht. Weitere Informationen finden Sie unter [Tresor Links-Einstellungen für Office 365 Apps.](safe-links.md#safe-links-settings-for-office-365-apps)

Sie können die einstellungen für globale Tresor Links im Microsoft 365 Defender-Portal oder in PowerShell konfigurieren (Exchange Online PowerShell für berechtigte Microsoft 365 Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange Online Postfächer, aber mit Microsoft Defender für Office 365 Add-On-Abonnements).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Es gibt keine integrierte oder standardmäßige richtlinie für Tresor Links. Daher müssen Sie mindestens eine Tresor Verknüpfungsrichtlinie erstellen, damit **die Liste der folgenden URLs** blockiert wird. Anweisungen finden Sie unter ["Einrichten Tresor Links"-Richtlinien in Microsoft Defender für Office 365.](set-up-safe-links-policies.md)

- Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com>. To go directly to the **Tresor Links** page, use <https://security.microsoft.com/safelinksv2> .

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Sie müssen in **Exchange Online** Berechtigungen erhalten, bevor Sie die in diesem Artikel beschriebenen Schritte ausführen können:
  - Um die globalen Einstellungen für Tresor Links zu konfigurieren, müssen Sie Mitglied der Rollengruppen **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** sein.
  - Für den schreibgeschützten Zugriff auf die globalen Einstellungen für Tresor Links müssen Sie Mitglied der Rollengruppe **"Globaler Leser"** oder **"Sicherheitsleseberechtigter"** sein.

  Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Hinweise**:

  - Durch Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).
  - Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.

- Unsere empfohlenen Werte für die globalen Einstellungen für Tresor Links finden Sie unter [Tresor Links settings](recommended-settings-for-eop-and-office365.md#safe-links-settings).

- Es kann bis zu 30 Minuten dauern, bis eine neue oder aktualisierte Richtlinie angewendet wird.

- [Microsoft Defender werden kontinuierlich neue Features für Office 365 hinzugefügt.](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365) Wenn neue Features hinzugefügt werden, müssen Sie möglicherweise Anpassungen an Ihren vorhandenen Richtlinien für Tresor Links vornehmen.

## <a name="configure-the-block-the-following-urls-list-in-the-microsoft-365-defender-portal"></a>Konfigurieren der Liste "Blockieren der folgenden URLs" im Microsoft 365 Defender Portal

The **Block the following URLs** list identifies the links that should always be blocked by Tresor Links scanning in supported apps. Weitere Informationen finden Sie in [der Liste "Blockieren der folgenden URLs" für Tresor Links.](safe-links.md#block-the-following-urls-list-for-safe-links)

1. Wechseln Sie im Portal Microsoft 365 Defender zu Richtlinien für **die E-Mail-& Zusammenarbeit** & Richtlinien für \> **Bedrohungsregeln** Tresor \>  \>  \> **Links.**

2. Klicken Sie auf der Seite **Tresor Links** auf **globale Einstellungen.** Wechseln Sie in der **angezeigten Tresor-Verknüpfungsrichtlinie für Ihre Organisation** zum **Feld "Folgende URLs blockieren".**

3. Konfigurieren Sie einen oder mehrere Einträge, wie in [der Eintragssyntax für die Liste "Blockieren der folgenden URLs"](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)beschrieben.

   Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>Konfigurieren der Liste "Blockieren der folgenden URLs" in PowerShell

Ausführliche Informationen zur Eintragssyntax finden Sie unter [Eintragssyntax für die Liste "Blockieren der folgenden URLs".](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)

Sie können das Cmdlet **"Get-AtpPolicyForO365"** verwenden, um vorhandene Einträge in der _BlockURLs-Eigenschaft_ anzuzeigen.

- Um Werte hinzuzufügen, die vorhandene Einträge ersetzen, verwenden Sie die folgende Syntax in Exchange Online PowerShell oder Exchange Online Protection PowerShell:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  In diesem Beispiel werden der Liste die folgenden Einträge hinzugefügt:

  - Blockieren Sie die Domäne, Unterdomänen und Pfade für fabrikam.com.
  - Blockieren der Unterdomänen-Recherche, aber nicht der übergeordneten Domäne oder anderer Unterdomänen in tailspintoys.com

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- Verwenden Sie die folgende Syntax, um Werte hinzuzufügen oder zu entfernen, ohne dass sich dies auf andere Einträge auswirkt:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  In diesem Beispiel wird ein neuer Eintrag für adatum.com hinzugefügt und der Eintrag für fabrikam.com entfernt.

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-microsoft-365-defender-portal"></a>Konfigurieren Tresor Links-Schutzes für Office 365 Apps im Microsoft 365 Defender-Portal

Tresor Der Linksschutz für Office 365 Apps gilt für Dokumente in unterstützten Office Desktop-, Mobil- und Web-Apps. Weitere Informationen finden Sie unter [Tresor Links-Einstellungen für Office 365 Apps.](safe-links.md#safe-links-settings-for-office-365-apps)

1. Wechseln Sie im Portal Microsoft 365 Defender zu Richtlinien für **die E-Mail-& Zusammenarbeit** & Richtlinien für \> **Bedrohungsregeln** Tresor \>  \>  \> **Links.**

2. Klicken Sie auf der Seite **Tresor Links** auf **globale Einstellungen.** Konfigurieren Sie in der **angezeigten Tresor-Verknüpfungsrichtlinie für Ihre Organisation** die folgenden Einstellungen im Einstellungen, die für Inhalte im Abschnitt **"Unterstützte Office 365 Apps" gelten:**

   - **Verwenden Sie Tresor Links in Office 365 Apps:** Überprüfen Sie, ob die Umschaltfläche rechts ist, um Tresor Links für unterstützte Office 365 Apps zu aktivieren: ![ Einschalten. ](../../media/scc-toggle-on.png)

   - **Nicht nachverfolgen, wenn Benutzer in Office 365 Apps auf geschützte Links klicken:** Verschieben Sie die Umschaltfläche nach links, um Benutzerklicks im Zusammenhang mit blockierten URLs in unterstützten Office 365 Apps nachzuverfolgen: ![ Deaktivieren ](../../media/scc-toggle-off.png) .

   - **Benutzer dürfen nicht auf die ursprüngliche URL in Office 365 Apps klicken:** Stellen Sie sicher, dass sich die Umschaltfläche rechts befindet, um zu verhindern, dass Benutzer in unterstützten Office 365 Apps durch die ursprüngliche blockierte URL klicken: ![ Einschalten. ](../../media/scc-toggle-on.png)

   Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>Konfigurieren des Tresor Link-Schutzes für Office 365-Apps in PowerShell

Wenn Sie lieber PowerShell zum Konfigurieren Tresor Links-Schutzes für Office 365 Apps verwenden möchten, verwenden Sie die folgende Syntax in Exchange Online PowerShell oder Exchange Online Protection PowerShell:

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

In diesem Beispiel werden die folgenden Einstellungen für den Schutz von Tresor Links in Office 365 Apps konfiguriert:

- Tresor Links für Office 365 Apps sind aktiviert (der _Parameter EnableSafeLinksForO365Clients_ wird nicht verwendet, und der Standardwert ist $true).
- Benutzerklicks im Zusammenhang mit blockierten URLs in unterstützten Office 365 Apps werden nachverfolgt.
- Benutzer können in unterstützten Office 365 Apps nicht auf die ursprüngliche blockierte URL klicken (wir verwenden nicht den _Parameter "AllowClickThrough",_ und der Standardwert ist $false).

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-AtpPolicyForO365".](/powershell/module/exchange/set-atppolicyforo365)

## <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie die globalen Einstellungen für Tresor Links (die Liste **der folgenden URLs** blockieren und die Office 365 App-Schutzeinstellungen) erfolgreich konfiguriert haben:

- Wechseln Sie im Microsoft 365 Defender Portal zur Seite "Richtlinien für **E-Mail-& Zusammenarbeit** & Richtlinien für \>  \> **Bedrohungsregeln",** \>  \> **Tresor Links** auf \> **"Globale Einstellungen"** klicken, und überprüfen Sie die Einstellungen im angezeigten Flyout.

- Führen Sie in Exchange Online PowerShell oder Exchange Online Protection PowerShell den folgenden Befehl aus, und überprüfen Sie die Einstellungen:

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-AtpPolicyForO365".](/powershell/module/exchange/get-atppolicyforo365)
