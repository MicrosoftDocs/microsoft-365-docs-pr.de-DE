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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie globale Einstellungen (die Liste "folgende URLs blockieren" und Schutz für Office 365-Apps) für sichere Links in Microsoft Defender für Office 365 anzeigen und konfigurieren.
ms.openlocfilehash: 655fba35bf3675bfd571c8e4923a00fbeba85304
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842428"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>Konfigurieren globaler Einstellungen für sichere Links in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Dieser Artikel richtet sich an Geschäftskunden, die [Microsoft Defender für Office 365](office-365-atp.md)haben. Wenn Sie ein Privatbenutzer sind, der nach Informationen zu Safelinks in Outlook sucht, lesen Sie [Erweiterte Outlook.com-Sicherheit](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

"Sichere Links" ist ein Feature in [Microsoft Defender für Office 365](office-365-atp.md) , das die URL-Überprüfung eingehender e-Mail-Nachrichten im Nachrichtenfluss und die Zeit der Klick Überprüfung von URLs und Links in e-Mail-Nachrichten und an anderen Speicherorten bereitstellt. Weitere Informationen finden Sie unter [sichere Links in Microsoft Defender für Office 365](atp-safe-links.md).

Sie konfigurieren die meisten Einstellungen für sichere Links in Richtlinien für sichere Links. Anweisungen finden Sie unter [Einrichten von Richtlinien zu sicheren Links in Microsoft Defender für Office 365](set-up-atp-safe-links-policies.md).

Aber sichere Links verwendet auch globale Einstellungen, die für alle Benutzer gelten, die in allen aktiven Richtlinien für sichere Links enthalten sind. Dieser Bereich für globale Einstellungen:

- Die Liste **folgende URLs blockieren** Weitere Informationen finden Sie in [der Liste "folgende URLs blockieren" für sichere Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links)
- Schutz für sichere Links für Office 365-apps. Weitere Informationen finden Sie unter [Einstellungen für sichere Links für Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).

Sie können die globalen Einstellungen für sichere Links im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für berechtigte Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EoP PowerShell für Organisationen ohne Exchange Online Postfächer, aber mit Microsoft Defender für Office 365 Add-on-Abonnements) konfigurieren.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Die Features, die von globalen Einstellungen für sichere Links bereitgestellt werden, werden nur auf Benutzer angewendet, die in Active Safe Links-Richtlinien enthalten sind. Es gibt keine integrierte Richtlinie oder Standardrichtlinie für sichere Links, daher müssen Sie mindestens eine Richtlinie für sichere Links erstellen, damit diese globalen Einstellungen aktiv sind. Anweisungen finden Sie unter [Einrichten von Richtlinien zu sicheren Links in Microsoft Defender für Office 365](set-up-atp-safe-links-policies.md).

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Wenn Sie direkt zur Seite **sichere Links** wechseln möchten, verwenden Sie <https://protection.office.com/safelinksv2> .

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Um die globalen Einstellungen für sichere Links anzuzeigen und zu konfigurieren, müssen Sie Mitglied einer der folgenden Rollengruppen sein:

  - **Organisationsverwaltung** oder **Sicherheitsadministrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
  - **Organisationsverwaltung** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Unsere empfohlenen Werte für die globalen Einstellungen für sichere Links finden Sie unter [Safe Links Settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).

- Erlauben Sie bis zu 30 Minuten, bis eine neue oder aktualisierte Richtlinie angewendet wird.

- [Für Office 365 werden fortlaufend neue Features zu Microsoft Defender hinzugefügt](office-365-atp.md#new-features-in-microsoft-defender-for-office-365). Wenn neue Features hinzugefügt werden, müssen Sie möglicherweise Anpassungen an Ihren bestehenden Richtlinien für sichere Links vornehmen.

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a>Konfigurieren der Liste "folgende URLs blockieren" im Security & Compliance Center

In der Liste der **folgenden URLs blockieren** werden die Links aufgeführt, die immer durch das Scannen sicherer Hyperlinks in unterstützten apps blockiert werden sollten. Weitere Informationen finden Sie in [der Liste "folgende URLs blockieren" für sichere Links](atp-safe-links.md#block-the-following-urls-list-for-safe-links).

1. Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Gefahrenmanagement** \> **Richtlinie** \> **ATP-sichere Links** , und klicken Sie dann auf **globale Einstellungen**.

2. Wechseln Sie in der Liste **Richtlinie für sichere Links für Ihre Organisation** , die angezeigt wird, zum Feld **folgende URLs blockieren** .

3. Konfigurieren Sie einen oder mehrere Einträge wie unter [Eingabesyntax für die Liste "Blockieren der folgenden URLs"](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)beschrieben.

   Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>Konfigurieren der Liste "Blockieren der folgenden URLs" in PowerShell

Ausführliche Informationen zur Eingabesyntax finden Sie unter [Entry-Syntax für die Liste "Blockieren der folgenden URLs"](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).

Sie können das Cmdlet **Get-AtpPolicyForO365** verwenden, um vorhandene Einträge in der _BlockURLs_ -Eigenschaft anzuzeigen.

- Verwenden Sie die folgende Syntax in Exchange Online PowerShell oder Exchange Online Protection PowerShell, um Werte hinzuzufügen, die vorhandene Einträge ersetzen sollen:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  In diesem Beispiel werden der Liste die folgenden Einträge hinzugefügt:

  - Blockieren Sie die Domäne, Unterdomänen und Pfade für fabrikam.com.
  - Untersuchung der Unterdomäne blockieren, jedoch nicht die übergeordnete Domäne oder andere Unterdomänen in tailspintoys.com

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- Verwenden Sie die folgende Syntax, um Werte hinzuzufügen oder zu entfernen, ohne andere vorhandene Einträge zu beeinflussen:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  In diesem Beispiel wird ein neuer Eintrag für adatum.com hinzugefügt, und der Eintrag für fabrikam.com wird entfernt.

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a>Konfigurieren von Schutz für sichere Links für Office 365 apps im Security & Compliance Center

Sicherer Links Schutz für Office 365 apps gilt für Dokumente in unterstützten Office-Desktop-, Mobil-und Webanwendungen. Weitere Informationen finden Sie unter [Einstellungen für sichere Links für Office 365 apps](atp-safe-links.md#safe-links-settings-for-office-365-apps).

1. Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Gefahrenmanagement** \> **Richtlinie** \> **ATP-sichere Links** , und klicken Sie dann auf **globale Einstellungen**.

2. Konfigurieren Sie in der angezeigten **Richtlinie für sichere Links für Ihre Organisation** , die angezeigt wird, die folgenden Einstellungen im Abschnitt **Einstellungen, die für Inhalt außer e-Mail gelten** :

   - **Office 365 Anwendungen** : Stellen Sie sicher, dass die Umschaltfläche auf der rechten Seite ist, um sichere Links für unterstützte Office 365 apps zu aktivieren: ![ Einschalten ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .

   - **Nicht nachverfolgen, wenn Benutzer auf sichere Links klicken** : bewegen Sie die Umschaltfläche nach links, um Benutzerklicks in Bezug auf blockierte URLs in unterstützten Office 365 apps nachzuverfolgen: ![ Deaktivieren ](../../media/scc-toggle-off.png) .

   - **Benutzer können nicht über sichere Links auf die ursprüngliche URL klicken** : Vergewissern Sie sich, dass die Umschaltfläche auf der rechten Seite ist, um zu verhindern, dass Benutzer die ursprüngliche Blockierte URL in unterstützten Office 365 apps: ![ Einschalten ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .

   Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>Konfigurieren von Schutz für sichere Links für Office 365 apps in PowerShell

Wenn Sie lieber mithilfe von PowerShell den Schutz für sichere Links für Office 365 apps konfigurieren möchten, verwenden Sie die folgende Syntax in Exchange Online PowerShell oder Exchange Online Protection PowerShell:

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

In diesem Beispiel werden die folgenden Einstellungen für den Schutz von sicheren Links in Office 365 apps konfiguriert:

- Sichere Links für Office 365 apps sind aktiviert (der Parameter _EnableSafeLinksForO365Clients_ wird nicht verwendet, und der Standardwert ist $true).
- Benutzerklicks im Zusammenhang mit blockierten URLs in unterstützten Office 365-apps werden nachverfolgt.
- Benutzer dürfen nicht auf die ursprüngliche Blockierte URL in unterstützten Office 365 apps klicken (der Parameter _AllowClickThrough_ wird nicht verwendet, und der Standardwert ist $false).

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).

## <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

Führen Sie einen der folgenden Schritte aus, um sicherzustellen, dass Sie die globalen Einstellungen für sichere Links erfolgreich konfiguriert haben (die Liste **folgende URLs blockieren** und die Office 365 Einstellungen für den App-Schutz):

- Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Gefahrenmanagement** \> **Richtlinie** \> **ATP-sichere Links** , klicken Sie auf **globale Einstellungen** , und überprüfen Sie die Einstellungen in der angezeigten ausklapp Leiste.

- Führen Sie in Exchange Online PowerShell oder Exchange Online Protection PowerShell den folgenden Befehl aus, und überprüfen Sie die Einstellungen:

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).
