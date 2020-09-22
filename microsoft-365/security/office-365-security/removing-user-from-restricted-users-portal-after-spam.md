---
title: Entfernen von blockierten Benutzern aus dem Portal "Eingeschränkte Benutzer"
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
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Hier erfahren Administratoren, wie sie Benutzer aus dem Portal für eingeschränkte Benutzer in Office 365 entfernen können. Benutzer werden aufgrund des Versands von ausgehenden Spamnachrichten zum Portal für eingeschränkte Benutzer hinzugefügt, in der Regel als Folge einer Kontokompromittierung.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c63d50fcf24e19c6a3265d57ea34fb8ab852c61c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201555"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-office-365"></a>Entfernen von blockierten Benutzern aus dem Portal "Eingeschränkte Benutzer" in Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Wenn ein Benutzer einen der Grenzwerte für den ausgehendem Versand überschreitet, wie unter[Sendegrenzwerte](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) oder [Richtlinien für ausgehenden Spam](configure-the-outbound-spam-policy.md) angegeben, wird der Benutzer am Senden von E-Mails gehindert, kann aber weiterhin E-Mails empfangen.

Der Benutzer wird zum Portal für eingeschränkte Benutzer im Security & Compliance Center hinzugefügt. Wenn der Benutzer versuch, eine E-Mail zu senden, wird die Nachricht in einem Unzustellbarkeitsbericht (auch als NDR- oder Unzustellbarkeitsnachricht bezeichnet) mit dem Fehlercode [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) und dem folgenden Text zurückgegeben:

> „Ihre Nachricht konnte nicht übermittelt werden, weil Sie nicht als gültiger Absender erkannt wurden. Der häufigste Grund dafür ist, dass der Verdacht besteht, dass von Ihrer E-Mail-Adresse Spam versandt wurde, und dass deshalb das Senden von E-Mails nicht mehr zugelassen wird.  Sollten Sie Unterstützung benötigen, wenden Sie sich an Ihren E-Mail-Administrator. Der Remoteserver hat „550 5.1.8 Zugriff verweigert, ungültiger ausgehender Absender“ zurückgegeben.“

Im Security & Compliance Center oder in Exchange Online PowerShell können Administratoren Benutzer aus dem Portal mit eingeschränkte Absender entfernen.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Verwenden Sie <https://protection.office.com/restrictedusers>, um direkt zur Seite **Eingeschränkte Benutzer** zu wechseln.

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Bevor Sie die in diesem Artikel besprochenen Verfahren ausführen können, müssen Ihnen Berechtigungen zugewiesen werden:

  - Wenn Sie Benutzer aus dem Portal mit eingeschränkten Benutzern entfernen möchten, müssen Sie Mitglied einer der folgenden Rollengruppen sein:

    - **Organisationsverwaltung** oder **Sicherheitsadministrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
    - **Organisationsverwaltung** oder **Nachrichtenschutz** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Für den schreibgeschützten Zugriff auf das eingeschränkte Benutzerportal müssen Sie Mitglied einer der folgenden Rollengruppen sein:

    - **Security Reader** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
    - **Schreibgeschützte Organisationsverwaltung** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Werden die Grenzwerte für ausgehende E-Mail-Nachrichten von einem Absender überschritten, ist dies ein Hinweis auf ein kompromittiertes Konto. Bevor Sie den Benutzer aus dem Portal für eingeschränkte Benutzer entfernen, führen Sie die erforderlichen Schritte aus, um die Kontrolle über das Konto wiederherzustellen. Weitere Informationen finden Sie unter [Reagieren auf ein kompromittiertes E-Mail-Konto in Office 365](responding-to-a-compromised-email-account.md).

## <a name="use-the-security--compliance-center-to-remove-a-user-from-the-restricted-users-list"></a>Verwenden des Security & Compliance Centers zum Entfernen eines Benutzers aus der Liste der eingeschränkten Benutzer

1. Wechseln Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Überprüfung** \> **Eingeschränkte Benutzer**.

2. Wählen Sie den Benutzer aus, dessen Blockierung Sie entfernen möchten. Klicken Sie in der Spalte **Aktionen** auf **Blockierung aufheben**.

3. Details zu dem Konto, für das das Senden eingeschränkt wurde, werden in einem Popup-Fenster angezeigt. Gehen Sie die Empfehlungen durch und stellen Sie sicher, dass Sie die richtigen Maßnahmen für den Fall ergreifen, dass das Konto tatsächlich kompromittiert ist. Klicken Sie abschließend auf **Weiter**.

4. Der nächste Bildschirm enthält Empfehlungen zur Verhinderung zukünftiger Kompromittierungen. Das Aktivieren der mehrstufigen Authentifizierung (MFA) und das Ändern der Kennwörter sind eine gute Abwehr. Klicken Sie abschließend auf **Benutzer entsperren**.

5. Klicken Sie zur Änderungsbestätigung auf **Ja**.

   > [!NOTE]
   > Es kann bis zu 30 Minuten oder länger dauern, bis Einschränkungen aufgehoben werden.

## <a name="verify-the-alert-settings-for-restricted-users"></a>Überprüfen der Warnungseinstellungen für eingeschränkte Benutzer

Die standardmäßige Benachrichtigungsrichtlinie mit dem Namen **Benutzer, dessen E-Mail-Versand blockiert wurde** benachrichtigt Administratoren automatisch, wenn Benutzer blockiert werden, damit sie keine ausgehenden E-Mails mehr senden können. Sie können diese Einstellungen überprüfen und weitere Benutzer hinzufügen, die benachrichtigt werden sollen. Weitere Informationen über Benachrichtigungsrichtlinien finden Sie unter [Benachrichtigungsrichtlinien im Security & Compliance Center](../../compliance/alert-policies.md).

> [!IMPORTANT]
> Damit Benachrichtigungen funktionieren, muss die Überwachungsprotokollsuche aktiviert sein. Weitere Informationen finden Sie unter [Aktivieren und Deaktivieren der Überwachungsprotokollsuche](../../compliance/turn-audit-log-search-on-or-off.md).

1. Wechseln Sie im Security & Compliance Center zu **Benachrichtigungen** \> **Benachrichtigungsrichtlinien**.

2. Wählen Sie die Benachrichtigung **Benutzer, dessen E-Mail-Versand blockiert wurde**.

3. Überprüfen oder konfigurieren Sie im Flyout die folgenden Einstellungen:

   - **Status**: Überprüfen Sie, ob die Benachrichtigung aktiviert ist ![Aktiviert](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **E-Mail-Empfänger**: Klicken Sie auf **Bearbeiten**, und überprüfen oder konfigurieren Sie die folgenden Einstellungen im angezeigten Flyout **Empfänger bearbeiten**:

     - **Senden von E-Mail-Benachrichtigungen**: Vergewissern Sie sich, ob das Kontrollkästchen aktiviert ist (**Ein**).

     - **E-Mail-Empfänger**: Der Standardwert ist **TenantAdmins** (dies bedeutet Mitglieder von **Globaler Administrator**). Wenn Sie weitere Empfänger hinzufügen möchten, klicken Sie auf einen leeren Bereich des Felds. Eine Liste von Empfängern wird angezeigt, und Sie können mit der Eingabe eines Namens beginnen, um die Liste zu filtern und einen Empfänger auszuwählen. Sie können einen vorhandenen Empfänger aus dem Feld entfernen, indem Sie auf das Symbol ![Entfernen](../../media/scc-remove-icon.png) neben seinem Namen klicken.

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

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/get-blockedsenderaddress).

Um einen Benutzer aus der Liste der eingeschränkten Benutzer zu entfernen, ersetzen Sie \<emailaddress\> durch seine E-Mail-Adresse, und führen Sie den folgenden Befehl aus:

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-BlockedSenderAddres](https://docs.microsoft.com/powershell/module/exchange/remove-blockedsenderaddress).
