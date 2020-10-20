---
title: Verwenden von Nachrichtenfluss Regeln zum Filtern von Massen-e-Mails
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie Nachrichtenfluss Regeln (Transportregeln) verwenden, um Massen-e-Mails (Gray Mail) in Exchange Online Protection (EoP) zu identifizieren und zu filtern.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 82a93cdc7375468748f241e2d15d729811095330
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600309"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a>Verwenden von Regeln zum Filtern von Massen-E-Mails in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer verwendet EoP Antispam-Richtlinien (auch als Spamfilter Richtlinien oder Inhaltsfilter Richtlinien bezeichnet), um eingehende Nachrichten für Spam und Massen-e-Mails zu scannen (auch als graue e-Mail bezeichnet). Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).

Wenn Sie weitere Optionen zum Filtern von Massen-e-Mails wünschen, können Sie Nachrichtenfluss Regeln (auch bekannt als Transportregeln) erstellen, um nach Textmustern oder Ausdrücken zu suchen, die häufig in Massen-e-Mails gefunden werden, und diese Nachrichten als Spam markieren. Weitere Informationen zu Massen-e-Mails finden Sie unter [Was ist der Unterschied zwischen Junk-e-Mail und Massen-e-Mail? und der](what-s-the-difference-between-junk-email-and-bulk-email.md) [Massen Reklamations Stufe (BCL) in EoP](bulk-complaint-level-values.md).

In diesem Thema wird erläutert, wie Sie diese Nachrichtenfluss Regeln in der Exchange-Verwaltungskonsole (EAC) und PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EoP PowerShell für Organisationen ohne Exchange Online Postfächer) erstellen.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie müssen Berechtigungen zugewiesen haben, bevor Sie diese Verfahren ausführen können:

  - Lesen Sie in Exchange Online den Eintrag "Nachrichtenfluss" unter [Feature Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions).
  
  - In eigenständigen EoP benötigen Sie die Transport Regel Rolle, die standardmäßig den Rollenmitglied, ComplianceManagement und RecordsManagement zugewiesen ist. Weitere Informationen finden Sie unter [Berechtigungen in eigenständigen EoP](feature-permissions-in-eop.md) und [Verwenden der Exchange-Verwaltungskonsole ändern der Liste der Mitglieder in Rollengruppen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Informationen zum Öffnen des EAC in Exchange Online finden Sie unter [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center). Informationen zum Öffnen der Exchange-Verwaltungskonsole in eigenständigen EoP finden Sie unter [Exchange Admin Center in Standalone EoP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Weitere Informationen zu Nachrichtenfluss Regeln in Exchange Online und eigenständigen EoP finden Sie in den folgenden Themen:

  - [Nachrichtenflussregeln (Transportregeln) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Nachrichtenflussregel-Bedingungen und -Ausnahmen (Prädikate) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Aktionen für Nachrichtenflussregeln in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- Die Liste der Wörter und Textmuster, die zum Identifizieren von Massennachrichten in den Beispielen verwendet werden, sind nicht erschöpfend; Sie können Einträge bei Bedarf hinzufügen und entfernen. Sie sind jedoch ein guter Ausgangspunkt.

- Die Suche nach Wörtern oder Textmustern im Betreff oder anderen Kopfzeilenfeldern in der Nachricht tritt *nach* der Decodierung der Nachricht aus der MIME-Inhaltsübertragungscodierungsmethode ein, die für die Übermittlung der binären Nachricht zwischen SMTP-Servern im ASCII-Text verwendet wurde. Sie können keine Bedingungen oder Ausnahmen für die Suche nach Rohwerten (in der Regel Base64-codiert) im Betreff oder in anderen Kopfzeilenfeldern in Nachrichten verwenden.

- Die folgenden Verfahren kennzeichnen eine Massen Nachricht als Spam für Ihre gesamte Organisation. Sie können jedoch eine weitere Bedingung hinzufügen, um diese Regeln nur auf bestimmte Empfänger anzuwenden, sodass Sie eine aggressive Filterung für einige wenige, sehr gezielte Benutzer verwenden können, während die restlichen Benutzer (die meistens die Massen-e-Mails erhalten, für die Sie sich angemeldet haben) nicht betroffen sind.

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>Verwenden der Exchange-Verwaltungskonsole zum Erstellen von Nachrichtenfluss Regeln zum Filtern von Massen-e-Mails

1. Navigieren Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln**.

2. Klicken Sie auf Add-Symbol **Hinzufügen** ![ ](../../media/ITPro-EAC-AddIcon.png) , und wählen Sie dann **neue Regel erstellen**aus.

3. Konfigurieren Sie auf der daraufhin geöffneten Seite **Neue Regel** die folgenden Einstellungen:

   - **Name**: Geben Sie einen eindeutigen, beschreibenden Namen für die Regel ein.

   - Klicken Sie auf **Weitere Optionen**.

   - **Diese Regel anwenden, wenn**: eine der folgenden Einstellungen zum Suchen nach Inhalten in Nachrichten mithilfe regulärer Ausdrücke (Regex) oder Wörtern oder Ausdrücken konfigurieren:

     - **Der Betreff oder Textkörper** \> **Betreff oder Text entspricht diesen Textmustern**: Geben Sie im angezeigten Dialogfeld **Wörter oder Ausdrücke angeben** einen der folgenden Werte ein, klicken Sie auf Add-Symbol **Hinzufügen** ![ ](../../media/ITPro-EAC-AddIcon.png) , und wiederholen Sie diese Schritte, bis Sie alle Werte eingegeben haben.

       - `If you are unable to view the content of this email\, please`
       - `\>(safe )?unsubscribe( here)?\</a\>`
       - `If you do not wish to receive further communications like this\, please`
       - `<img height="?1"? width="?1"? src=.?http\://`
       - `To stop receiving these+emails\:http\://`
       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
       - `no longer (wish )?(to )?(be sent|receive) w+ email`
       - `If you are unable to view the content of this email\, please click here`
       - `To ensure you receive (your daily deals|our e-?mails)\, add`
       - `If you no longer wish to receive these emails`
       - `to change your (subscription preferences|preferences or unsubscribe)`
       - `click (here to|the) unsubscribe`

      Um einen Eintrag zu bearbeiten, wählen Sie ihn aus, und klicken Sie auf Bearbeitungssymbol **Bearbeiten** ![ ](../../media/ITPro-EAC-EditIcon.png) . Um einen Eintrag zu entfernen, wählen Sie ihn aus, und klicken Sie auf entfernen-Symbol **Entfernen** ![ ](../../media/ITPro-EAC-DeleteIcon.png) .

       Klicken Sie nach Abschluss des Vorgangs auf **OK**.

     - **Der Betreff oder Textkörper** \> **Betreff oder Textkörper enthält eines dieser Wörter**: Geben Sie im angezeigten Dialogfeld **Wörter oder Ausdrücke angeben** einen der folgenden Werte ein, klicken Sie auf Add-Symbol **Hinzufügen** ![ ](../../media/ITPro-EAC-AddIcon.png) , und wiederholen Sie diese Schritte, bis Sie alle Werte eingegeben haben.

       - `to change your preferences or unsubscribe`
       - `Modify email preferences or unsubscribe`
       - `This is a promotional email`
       - `You are receiving this email because you requested a subscription`
       - `click here to unsubscribe`
       - `You have received this email because you are subscribed`
       - `If you no longer wish to receive our email newsletter`
       - `to unsubscribe from this newsletter`
       - `If you have trouble viewing this email`
       - `This is an advertisement`
       - `you would like to unsubscribe or change your`
       - `view this email as a webpage`
       - `You are receiving this email because you are subscribed`

      Um einen Eintrag zu bearbeiten, wählen Sie ihn aus, und klicken Sie auf Bearbeitungssymbol **Bearbeiten** ![ ](../../media/ITPro-EAC-EditIcon.png) . Um einen Eintrag zu entfernen, wählen Sie ihn aus, und klicken Sie auf entfernen-Symbol **Entfernen** ![ ](../../media/ITPro-EAC-DeleteIcon.png) .

       Klicken Sie nach Abschluss des Vorgangs auf **OK**.

   - **Gehen Sie folgen**dermaßen vor: Wählen Sie **ändern die Nachrichteneigenschaften** \> **Festlegen der SCL-Bewertung (Spam Confidence Level)**. Konfigurieren Sie im angezeigten **SCL** -Dialogfeld eine der folgenden Einstellungen:

     - Um Nachrichten als **Spam**zu markieren, wählen Sie **6**aus. Die Aktion, die Sie für **Spam** Filterungs Urteile in ihren Anti-Spam-Richtlinien konfiguriert haben, wird auf die Nachrichten angewendet (der Standardwert ist **"Nachricht in Junk-e-Mail-Ordner"**).

     - So markieren Sie Nachrichten als **Spam mit hoher Zuverlässigkeit** wählen Sie **9**aus. Die Aktion, die Sie für Spam Filterungs Urteile mit **hoher Vertrauens** Würdigkeit in ihren Anti-Spam-Richtlinien konfiguriert haben, wird auf die Nachrichten angewendet (der Standardwert ist **"Nachricht in Junk-e-Mail-Ordner"**).

    Weitere Informationen zu SCL-Werten finden Sie unter [Spam Confidence Level (SCL) in EoP](spam-confidence-levels.md).

   Wenn Sie fertig sind, klicken Sie auf **Speichern**

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a>Verwenden von PowerShell zum Erstellen von Nachrichtenfluss Regeln zum Filtern von Massen-e-Mails

Verwenden Sie die folgende Syntax, um eine oder beide Nachrichtenfluss Regeln (reguläre Ausdrücke Vs. Wörter) zu erstellen:

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

In diesem Beispiel wird eine neue Regel mit dem Namen "Massen-e-Mail-Filterung-Regex" erstellt, die die gleiche Liste regulärer Ausdrücke aus der früheren Version des Themas verwendet, um Nachrichten als **Spam**festzulegen.

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? src=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

In diesem Beispiel wird eine neue Regel mit dem Namen "Massen-e-Mail-Filterung-Wörter" erstellt, die die gleiche Liste von Wörtern wie oben im Thema verwendet, um Nachrichten als **Spam mit hoher Vertrauens**Würdigkeit festzulegen.

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

Detaillierte Informationen zur Syntax und den Parametern finden Sie unter [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob e-Mail-Flussregeln zum Filtern von Massen-e-Mails konfiguriert wurden:

- Wechseln Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln** \> Wählen Sie die Regel \> Klicken Sie auf Bearbeitungssymbol **Bearbeiten** ![ ](../../media/ITPro-EAC-EditIcon.png) , und überprüfen Sie die Einstellungen.

- Ersetzen Sie in PowerShell \<Rule Name\> durch den Namen der Regel, und führen Sie den folgenden Befehl aus, um die Einstellungen zu überprüfen:

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- Senden Sie von einem externen Konto eine Testnachricht an einen betroffenen Empfänger, der eines der Ausdrücke oder Textmuster enthält, und überprüfen Sie die Ergebnisse.
