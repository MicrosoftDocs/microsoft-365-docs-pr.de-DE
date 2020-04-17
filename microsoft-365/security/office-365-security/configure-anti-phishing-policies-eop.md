---
title: Konfigurieren der standardmäßigen Antiphishing-Richtlinie in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratoren erfahren, wie Sie die Antispoofing-Einstellungen ändern können, die in der standardmäßigen Anti-Phishing-Richtlinie in Office 365 Organisationen mit Exchange Online Postfächern verfügbar sind.
ms.openlocfilehash: 1a8527a55796910e79fbf70b824de828ca48591b
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537533"
---
# <a name="configure-the-default-anti-phishing-policy-in-eop"></a>Konfigurieren der standardmäßigen Antiphishing-Richtlinie in EOP

Office 365 Organisationen mit Exchange Online Postfächern und eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer verfügen über eine Standard-Anti-Phishing-Richtlinie. Diese Richtlinie enthält eine beschränkte Anzahl von Anti-Spoofing-Features, die standardmäßig aktiviert sind. Weitere Informationen finden Sie unter [Spoof Settings in Anti-Phishing Policies](set-up-anti-phishing-policies.md#spoof-settings).

Office 365 Organisationen mit Exchange Online Postfächern können die standardmäßige Anti-Phishing-Richtlinie im Office 365 Security & Compliance Center oder in Exchange Online PowerShell ändern. Eigenständige EoP-Organisationen ohne Exchange Online Postfächer können Ihre standardmäßige Anti-Phishing-Richtlinie nicht ändern.

Informationen zum Erstellen und Ändern der erweiterten ATP-Richtlinien für die Anti-Phishing, die in Office 365 Advanced Threat Protection verfügbar sind, finden Sie unter [configure ATP Anti-Phishing Policies in Office 365](configure-atp-anti-phishing-policies.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Wenn Sie direkt zur Seite **Anti-Phishing** wechseln möchten, verwenden <https://protection.office.com/antiphishing>Sie.

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

- Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Zum Hinzufügen, ändern und Löschen von Anti-Phishing-Richtlinien müssen Sie Mitglied der Rollengruppen " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " sein. Für den schreibgeschützten Zugriff auf Anti-Phishing-Richtlinien müssen Sie Mitglied der Rollengruppe **Sicherheits Leser** sein. Weitere Informationen zu Rollengruppen im Security & Compliance Center finden Sie unter [Berechtigungen im Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

- Unsere empfohlenen Einstellungen für die standardmäßige Anti-Phishing-Richtlinie finden Sie unter [EoP default Anti-Phishing Policy Settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).

- Lassen Sie bis zu 30 Minuten für die Anwendung der aktualisierten Richtlinie zu.

- Informationen dazu, wo Anti-Phishing-Richtlinien in der Filter Pipeline angewendet werden, finden Sie unter [Order and Ranges of Email Protection in Office 365](how-policies-and-protections-are-combined.md).

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a>Verwenden des Security & Compliance Center zum Ändern der standardmäßigen Anti-Phishing-Richtlinie

Die standardmäßige Anti-Phishing-Richtlinie heißt Office365 AntiPhishing Default, und Sie wird nicht in der Liste der Richtlinien angezeigt. Führen Sie die folgenden Schritte aus, um die standardmäßige Anti-Phishing-Richtlinie zu ändern:

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Anti-Phishing**.

2. Klicken Sie auf der Seite **Anti-Phishing** auf **Standardrichtlinie**.

3. Die **Standardseite Ihre Richtlinie Office365 AntiPhishing bearbeiten** wird angezeigt. Klicken Sie im Abschnitt **Spoof** auf **Bearbeiten**.

   Beachten Sie, dass diese Einstellungen mit den spoofeinstellungen identisch sind, die in den ATP-Richtlinien zum Schutz vor Phishing verfügbar sind.

   - **Spoofing-Filtereinstellungen**: der Standardwert ist " **on**", und es wird empfohlen, dass Sie die Einstellung aktiviert lassen. Um sie auszublenden, schieben Sie die Umschaltfläche auf **aus**. Weitere Informationen finden Sie unter [configure Spoof Intelligence in Office 365](learn-about-spoof-intelligence.md).

     > [!NOTE]
     > Sie müssen den Schutz vor Spoofing nicht deaktivieren, wenn Ihr MX-Eintrag nicht auf Office 365 verweist; Stattdessen aktivieren Sie die erweiterte Filterung für Connectors. Anweisungen finden Sie unter [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

   - Nicht **authentifizierte Absender Funktion aktivieren**: Fügt dem Foto des Absenders ein Fragezeichen hinzu, wenn die Nachricht e-Mail-Authentifizierungsprüfungen fehlschlägt. Weitere Informationen finden Sie unter [Spoof Settings in Anti-Phishing Policies](set-up-anti-phishing-policies.md#spoof-settings). Der Standardwert ist **Aktiviert**. Um sie auszublenden, schieben Sie die Umschaltfläche auf **aus**.

   - **Actions: geben**Sie die Aktion an, die für Nachrichten ausgeführt werden soll, die Spoof Intelligence nicht ausführen:

     **Wenn e-Mails von Benutzern gesendet werden, die Ihre Domäne nicht spoofen dürfen**:

     - **Nachricht in die Junk-e-Mail-Ordner der Empfänger über** tragen (Dies ist der Standardwert).
     - **Nachricht isolieren**

   - **Überprüfen Sie Ihre Einstellungen**: anstatt auf jeden einzelnen Schritt zu klicken, werden die Einstellungen in einer Zusammenfassung angezeigt.

     - Sie können in jedem Abschnitt auf **Bearbeiten** klicken, um zurück zur entsprechenden Seite zu wechseln.
     - Sie können die **folgenden Einstellungen direkt auf dieser** Seite aktivieren oder **Deaktivieren** :

       - **Aktivieren von Schutz vor Spoofing**
       - **Nicht authentifizierte Absender Funktion aktivieren**

   Wenn Sie fertig sind, klicken Sie auf jeder Seite auf **Speichern** .

4. Überprüfen Sie die Einstellungen auf der **Standardseite Richtlinie Office365 bearbeiten** , und klicken Sie dann auf **Schließen**.

## <a name="use-the-security--compliance-center-to-view-the-default-anti-phishing-policy"></a>Verwenden des Security & Compliance Center zum Anzeigen der standardmäßigen Anti-Phishing-Richtlinie

1. Im Security & Compliance Center und wechseln Sie zu **Threat Management** \> **Policy** \> **ATP Anti-Phishing**.

2. Klicken Sie auf **Standardrichtlinie** , um die standardmäßige Anti-Phishing-Richtlinie anzuzeigen.

## <a name="use-exchange-online-powershell-to-configure-the-default-anti-phishing-policy"></a>Konfigurieren der standardmäßigen Anti-Phishing-Richtlinie mithilfe Exchange Online PowerShell

### <a name="use-powershell-to-view-the-default-anti-phish-policy"></a>Verwenden von PowerShell zum Anzeigen der standardmäßigen Anti-Phishing-Richtlinie

Führen Sie den folgenden Befehl aus, um die standardmäßige Anti-Phishing-Richtlinie anzuzeigen:

```PowerShell
Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy).

### <a name="use-powershell-to-modify-the-default-anti-phish-policy"></a>Verwenden von PowerShell zum Ändern der standardmäßigen Anti-Phishing-Richtlinie

Verwenden Sie die folgende Syntax, um die standardmäßige Anti-Phishing-Richtlinie zu ändern:

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableAntispoofEnforcement <$true | $false>] [-EnableUnauthenticatedSender <$true | $false>]
```

In diesem Beispiel wird die Aktion für gefälschte Nachrichten geändert, bei denen die Authentifizierung nicht in Quarantäne überprüft wird.

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" -AuthenticationFailAction Quarantine
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy).

## <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie die standardmäßige Anti-Phishing-Richtlinie erfolgreich konfiguriert haben:

- Wechseln \> Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Anti-Phishing** klicken Sie auf **Standardrichtlinie** , und zeigen Sie die Details im Flyout an.

- Führen Sie in Exchange Online PowerShell den folgenden Befehl aus, und überprüfen Sie die Einstellungen:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
  ```
