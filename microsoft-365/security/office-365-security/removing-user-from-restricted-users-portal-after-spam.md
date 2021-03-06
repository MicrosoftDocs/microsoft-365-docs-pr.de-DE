---
title: Entfernen von blockierten Benutzern aus dem Portal „Eingeschränkte Benutzer“
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Hier erfahren Administratoren, wie sie Benutzer aus der Seite „Eingeschränkte Benutzer“ im Microsoft 365 Defender-Portal entfernen können. Benutzer werden aufgrund des Versands von ausgehenden Spamnachrichten zum Portal für eingeschränkte Benutzer hinzugefügt, in der Regel als Folge einer Kontokompromittierung.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 924db948103a4d3b45c499f433961762a45931af
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082852"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-microsoft-365"></a>Entfernen von blockierten Benutzern aus dem Portal „Eingeschränkte Benutzer“ in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Wenn ein Benutzer einen der Grenzwerte für den ausgehendem Versand überschreitet, wie unter[Sendegrenzwerte](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) oder [Richtlinien für ausgehenden Spam](configure-the-outbound-spam-policy.md) angegeben, wird der Benutzer am Senden von E-Mails gehindert, kann aber weiterhin E-Mails empfangen.

Der Benutzer wird zur Seite **Eingeschränkte Benutzer** im Microsoft 365 Defender-Portal hinzugefügt. Wenn der Benutzer versuch, eine E-Mail zu senden, wird die Nachricht in einem Unzustellbarkeitsbericht (auch als NDR- oder Unzustellbarkeitsnachricht bezeichnet) mit dem Fehlercode [5.1.8](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) und dem folgenden Text zurückgegeben:

> „Ihre Nachricht konnte nicht übermittelt werden, weil Sie nicht als gültiger Absender erkannt wurden. Der häufigste Grund dafür ist, dass der Verdacht besteht, dass von Ihrer E-Mail-Adresse Spam versandt wurde, und dass deshalb das Senden von E-Mails nicht mehr zugelassen wird.  Sollten Sie Unterstützung benötigen, wenden Sie sich an Ihren E-Mail-Administrator. Der Remoteserver hat „550 5.1.8 Zugriff verweigert, ungültiger ausgehender Absender“ zurückgegeben.“

Administratoren können Benutzer aus der Seite „Eingeschränkte Benutzer“ in Microsoft 365 Defender oder in Exchange Online PowerShell entfernen.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com>. Verwenden Sie <https://security.microsoft.com/restrictedusers>, um direkt zur Seite **Eingeschränkte Benutzer** zu wechseln.

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen in **Exchange Online** Berechtigungen zugewiesen werden:
  - Wenn Sie Benutzer aus dem Portal für eingeschränkte Benutzer entfernen möchten, müssen Sie Mitglied der Rollengruppen **Organisationsverwaltung** oder **Sicherheitsadministrator** sein.
  - Für den schreibgeschützten Zugriff auf das Portal für eingeschränkte Benutzer müssen Sie Mitglied der Rollengruppe **Globaler Leseberechtigter** oder **Sicherheitsleseberechtigter** sein.

  Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).
  >
  > - Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.

- Werden die Grenzwerte für ausgehende E-Mail-Nachrichten von einem Absender überschritten, ist dies ein Hinweis auf ein kompromittiertes Konto. Bevor Sie den Benutzer aus dem Portal für eingeschränkte Benutzer entfernen, führen Sie die erforderlichen Schritte aus, um die Kontrolle über das Konto wiederherzustellen. Weitere Informationen finden Sie unter [Reagieren auf ein kompromittiertes E-Mail-Konto in Office 365](responding-to-a-compromised-email-account.md).

## <a name="use-the-microsoft-365-defender-portal-to-remove-a-user-from-the-restricted-users-list"></a>Verwenden des Microsoft 365 Defender-Portals zum Entfernen eines Benutzers aus der Liste der eingeschränkten Benutzer

1. Gehen Sie im Microsoft 365 Defender-Portal zu **E-Mail & Zusammenarbeit** > **Überprüfung** > **Eingeschränkte Benutzer**.

2. Suchen Sie auf der Seite **Eingeschränkte Benutzer** den Benutzer, dessen Blockierung Sie entfernen möchten, und wählen Sie diesen aus, indem Sie darauf klicken.

3. Klicken Sie auf die Aktion **Blockierung aufheben**, die angezeigt wird.

4. Lesen Sie im angezeigten Flyout **Benutzer entsperren** die Details zum eingeschränkten Konto. Gehen Sie die Empfehlungen durch und stellen Sie sicher, dass Sie die richtigen Maßnahmen für den Fall ergreifen, dass das Konto kompromittiert ist.

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

5. Der nächste Bildschirm enthält Empfehlungen zur Verhinderung zukünftiger Kompromittierungen. Das Aktivieren der mehrstufigen Authentifizierung (MFA) und das Zurücksetzen des Kennworts ist eine gute Abwehr.

   Klicken Sie nach Abschluss des Vorgangs auf **Senden**.

6. Klicken Sie zur Änderungsbestätigung auf **Ja**.

   > [!NOTE]
   > Es kann bis zu 24 Stunden dauern, bis alle Einschränkungen für den Benutzer aufgehoben sind.

## <a name="verify-the-alert-settings-for-restricted-users"></a>Überprüfen der Warnungseinstellungen für eingeschränkte Benutzer

Die standardmäßige Benachrichtigungsrichtlinie mit dem Namen **Benutzer, dessen E-Mail-Versand blockiert wurde** benachrichtigt Administratoren automatisch, wenn Benutzer blockiert werden, damit sie keine ausgehenden E-Mails mehr senden können. Sie können diese Einstellungen überprüfen und weitere Benutzer hinzufügen, die benachrichtigt werden sollen. Weitere Informationen über Benachrichtigungsrichtlinien finden Sie unter [Benachrichtigungsrichtlinien in Microsoft 365](../../compliance/alert-policies.md).

> [!IMPORTANT]
> Damit Benachrichtigungen funktionieren, muss die Überwachungsprotokollsuche aktiviert sein. Weitere Informationen finden Sie unter [Aktivieren und Deaktivieren der Überwachungsprotokollsuche](../../compliance/turn-audit-log-search-on-or-off.md).

1. Gehen Sie im Microsoft 365 Defender-Portal zu **E-Mail & Zusammenarbeit** \> **Richtlinien und Regeln** \> **Warnungsrichtlinie**.

2. Suchen Sie auf der Seite **Warnungsrichtlinie** die Warnung mit dem Namen **Benutzer, dessen E-Mail-Versand blockiert wurde**, und wählen Sie sie aus. Sie können die Richtlinien nach Namen sortieren oder das **Suchfeld** verwenden, um die Richtlinie zu finden.

3. Überprüfen oder konfigurieren Sie im Flyout **Benutzer, dessen E-Mail-Versand blockiert wurde** die folgenden Einstellungen:
   - **Status**: Überprüfen Sie, ob die Benachrichtigung aktiviert ist ![Aktiviert](../../media/scc-toggle-on.png).
   - **E-Mail-Empfänger**: Klicken Sie auf **Bearbeiten**, und überprüfen oder konfigurieren Sie die folgenden Einstellungen im angezeigten Flyout **Empfänger bearbeiten**:
     - **Senden von E-Mail-Benachrichtigungen**: Vergewissern Sie sich, dass diese Option aktiviert ist (**Ein**).
     - **E-Mail-Empfänger**: Der Standardwert ist **TenantAdmins** (dies bedeutet Mitglieder von **Globaler Administrator**). Wenn Sie weitere Empfänger hinzufügen möchten, klicken Sie auf einen leeren Bereich des Felds. Eine Liste von Empfängern wird angezeigt, und Sie können mit der Eingabe eines Namens beginnen, um die Liste zu filtern und einen Empfänger auszuwählen. Sie können einen vorhandenen Empfänger aus dem Feld entfernen, indem Sie auf das Symbol ![Entfernen](../../media/m365-cc-sc-remove-selection-icon.png) neben seinem Namen klicken.
     - **Tägliche Benachrichtigungsgrenze**: Der Standardwert ist **Keine Grenze**, aber Sie können eine Grenze für die maximale Anzahl von Benachrichtigungen pro Tag festlegen.

     Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

4. Zurück im Flyout **Benutzer, dessen E-Mail-Versand blockiert wurde** klicken Sie auf **Schließen**.

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a>Verwenden Sie die Exchange Online-PowerShell, um die Liste der eingeschränkten Benutzer anzuzeigen und Benutzer daraus zu entfernen.

Um diese Liste der Benutzer anzuzeigen, deren E-Mail-Versand beschränkt ist, führen Sie den folgenden Befehl aus:

```powershell
Get-BlockedSenderAddress
```

Um Details zu einem bestimmten Benutzer anzuzeigen, ersetzen Sie \<emailaddress\> durch die E-Mail-Adresse des Benutzers, und führen Sie den folgenden Befehl aus:

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-BlockedSenderAddress](/powershell/module/exchange/get-blockedsenderaddress).

Um einen Benutzer aus der Liste der eingeschränkten Benutzer zu entfernen, ersetzen Sie \<emailaddress\> durch seine E-Mail-Adresse, und führen Sie den folgenden Befehl aus:

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-BlockedSenderAddres](/powershell/module/exchange/remove-blockedsenderaddress).
