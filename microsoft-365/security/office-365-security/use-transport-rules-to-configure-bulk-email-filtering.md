---
title: Verwenden von Nachrichtenfluss Regeln zum Filtern von Massen-e-Mails in Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie Nachrichtenfluss Regeln in Exchange Online Schutz für Massen-e-Mail-Filterung verwenden.
ms.openlocfilehash: 229a66658e041be737efbc4cbb7c36ba667d3aed
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631073"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-office-365"></a>Verwenden von Nachrichtenfluss Regeln zum Filtern von Massen-e-Mails in Office 365

Wenn Sie ein Microsoft 365-Kunde mit Postfächern in Exchange Online oder einem eigenständigen Exchange Online Schutz-Kunden (EoP) ohne Exchange Online Postfächer sind, verwendet EoP Antispam-Richtlinien (auch bekannt als Spamfilter-oder Inhaltsfilter Richtlinien), um eingehende Nachrichten für Spam und Massen-e-Mails zu scannen (auch als graue e-Mail bezeichnet). Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien in Office 365](configure-your-spam-filter-policies.md).

Wenn Sie weitere Optionen zum Filtern von Massen-e-Mails wünschen, können Sie Nachrichtenfluss Regeln (auch bekannt als Transportregeln) erstellen, um nach Textmustern oder Ausdrücken zu suchen, die häufig in Massen-e-Mails gefunden werden, und diese Nachrichten als Spam markieren. Weitere Informationen zu Massen-e-Mails finden Sie unter [Was ist der Unterschied zwischen Junk-e-Mail und Massen-e-Mail? und der](what-s-the-difference-between-junk-email-and-bulk-email.md) [Massen Reklamations Stufe (BCL) in Office 365](bulk-complaint-level-values.md).

In diesem Thema wird erläutert, wie diese Nachrichtenfluss Regeln in der Exchange-Verwaltungskonsole (EAC) und PowerShell (Exchange Online PowerShell für Microsoft 365-Kunden erstellt werden; Exchange Online Protection PowerShell für eigenständige EoP-Kunden).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie müssen Berechtigungen in Exchange Online zugewiesen werden, bevor Sie diese Verfahren ausführen können. Insbesondere müssen Sie die Rolle " **Transport Rules** " erhalten, die standardmäßig der Rollen " **Organisationsverwaltung**", " **Richtlinientreue Verwaltung**" und " **Datensatzverwaltung** " zugewiesen ist. Weitere Informationen finden Sie unter [Verwalten von Rollengruppen in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).

- Informationen zum Öffnen des EAC in Exchange Online finden Sie unter [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Weitere Informationen zu Nachrichtenfluss Regeln in Exchange Online und eigenständigen EoP finden Sie in den folgenden Themen:

  - [Nachrichtenflussregeln (Transportregeln) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Nachrichtenflussregel-Bedingungen und -Ausnahmen (Prädikate) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Aktionen für Nachrichtenflussregeln in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- Die Liste der Wörter und Textmuster, die zum Identifizieren von Massennachrichten in den Beispielen verwendet werden, sind nicht erschöpfend; Sie können Einträge bei Bedarf hinzufügen und entfernen. Sie sind jedoch ein guter Ausgangspunkt.

- Die Suche nach Wörtern oder Textmustern im Betreff oder anderen Kopfzeilenfeldern in der Nachricht tritt *nach* der Decodierung der Nachricht aus der MIME-Inhaltsübertragungscodierungsmethode ein, die für die Übermittlung der binären Nachricht zwischen SMTP-Servern im ASCII-Text verwendet wurde. Sie können keine Bedingungen oder Ausnahmen für die Suche nach Rohwerten (in der Regel Base64-codiert) im Betreff oder in anderen Kopfzeilenfeldern in Nachrichten verwenden.

- Die folgenden Verfahren kennzeichnen eine Massen Nachricht als Spam für Ihre gesamte Organisation. Sie können jedoch eine weitere Bedingung hinzufügen, um diese Regeln nur auf bestimmte Empfänger anzuwenden, sodass Sie eine aggressive Filterung für einige wenige, sehr gezielte Benutzer verwenden können, während die restlichen Benutzer (die meistens die Massen-e-Mails erhalten, für die Sie sich angemeldet haben) nicht betroffen sind.

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>Verwenden der Exchange-Verwaltungskonsole zum Erstellen von Nachrichtenfluss Regeln zum Filtern von Massen-e-Mails

1. Navigieren Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln**.

2. Klicken Sie auf Add](../../media/ITPro-EAC-AddIcon.png) -Symbol **Hinzufügen** ![, und wählen Sie dann **neue Regel erstellen**aus.

3. Konfigurieren Sie auf der daraufhin geöffneten Seite **Neue Regel** die folgenden Einstellungen:

   - **Name**: Geben Sie einen eindeutigen, beschreibenden Namen für die Regel ein.

   - Klicken Sie auf **Weitere Optionen**.

   - **Diese Regel anwenden, wenn**: eine der folgenden Einstellungen zum Suchen nach Inhalten in Nachrichten mithilfe regulärer Ausdrücke (Regex) oder Wörtern oder Ausdrücken konfigurieren:

     - **Der Betreff oder** \> Textkörper des Unternehmens **entspricht diesen Textmustern**: Geben Sie im angezeigten Dialogfeld **Wörter oder Ausdrücke angeben** einen der folgenden Werte ein, klicken Sie](../../media/ITPro-EAC-AddIcon.png)auf Add-Symbol **Hinzufügen** ![, und wiederholen Sie diese Schritte, bis Sie alle Werte eingegeben haben.

       - `If you are unable to view the content of this email\, please`

       - `\>(safe )?unsubscribe( here)?\</a\>`

       - `If you do not wish to receive further communications like this\, please`

       - `\<img height\="?1"? width\="?1"? sr\c=.?http\://`

       - `To stop receiving these+emails\:http\://`

       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`

       - `no longer (wish )?(to )?(be sent|receive) w+ email`

       - `If you are unable to view the content of this email\, please click here`

       - `To ensure you receive (your daily deals|our e-?mails)\, add`

       - `If you no longer wish to receive these emails`

       - `to change your (subscription preferences|preferences or unsubscribe)`

       - `click (here to|the) unsubscribe`

      Um einen Eintrag zu bearbeiten, wählen Sie ihn **Edit** ![aus, und](../../media/ITPro-EAC-EditIcon.png)klicken Sie auf Bearbeitungssymbol bearbeiten. Um einen Eintrag zu entfernen, wählen Sie ihn **Remove** ![aus, und](../../media/ITPro-EAC-DeleteIcon.png)klicken Sie auf entfernen-Symbol entfernen.

       Klicken Sie nach Abschluss des Vorgangs auf **OK**.

     - **Das Subjekt oder der Text** \> Körper des Betreffs oder Text **Körpers enthält eines dieser Wörter**: Geben Sie im angezeigten Dialogfeld **Wörter oder Ausdrücke angeben** einen der folgenden Werte ein, klicken](../../media/ITPro-EAC-AddIcon.png)Sie auf Add-Symbol **Hinzufügen** ![, und wiederholen Sie diese Schritte, bis Sie alle Werte eingegeben haben.

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

      Um einen Eintrag zu bearbeiten, wählen Sie ihn **Edit** ![aus, und](../../media/ITPro-EAC-EditIcon.png)klicken Sie auf Bearbeitungssymbol bearbeiten. Um einen Eintrag zu entfernen, wählen Sie ihn **Remove** ![aus, und](../../media/ITPro-EAC-DeleteIcon.png)klicken Sie auf entfernen-Symbol entfernen.

       Klicken Sie nach Abschluss des Vorgangs auf **OK**.

   - **Gehen Sie folgen**dermaßen vor: Wählen Sie **ändern die Nachrichteneigenschaften** \> **Festlegen der SCL-Bewertung (Spam Confidence Level)**. Konfigurieren Sie im angezeigten **SCL** -Dialogfeld eine der folgenden Einstellungen:

     - Um Nachrichten als **Spam**zu markieren, wählen Sie **6**aus. Die Aktion, die Sie für **Spam** Filterungs Urteile in ihren Anti-Spam-Richtlinien konfiguriert haben, wird auf die Nachrichten angewendet (der Standardwert ist **"Nachricht in Junk-e-Mail-Ordner"**).

     - So markieren Sie Nachrichten als **Spam mit hoher Zuverlässigkeit** wählen Sie **9**aus. Die Aktion, die Sie für Spam Filterungs Urteile mit **hoher Vertrauens** Würdigkeit in ihren Anti-Spam-Richtlinien konfiguriert haben, wird auf die Nachrichten angewendet (der Standardwert ist **"Nachricht in Junk-e-Mail-Ordner"**).

    Weitere Informationen zu SCL-Werten finden Sie unter [Spam Confidence Level (SCL) in Office 365](spam-confidence-levels.md).

   Wenn Sie fertig sind, klicken Sie auf **Speichern**

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a>Verwenden von PowerShell zum Erstellen von Nachrichtenfluss Regeln zum Filtern von Massen-e-Mails

Verwenden Sie die folgende Syntax, um eine oder beide Nachrichtenfluss Regeln (reguläre Ausdrücke Vs. Wörter) zu erstellen:

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPrhase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

In diesem Beispiel wird eine neue Regel mit dem Namen "Massen-e-Mail-Filterung-Regex" erstellt, die die gleiche Liste regulärer Ausdrücke aus der früheren Version des Themas verwendet, um Nachrichten als **Spam**festzulegen.

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

In diesem Beispiel wird eine neue Regel mit dem Namen "Massen-e-Mail-Filterung-Wörter" erstellt, die die gleiche Liste von Wörtern wie oben im Thema verwendet, um Nachrichten als **Spam mit hoher Vertrauens**Würdigkeit festzulegen.

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

Detaillierte Informationen zur Syntax und den Parametern finden Sie unter [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob e-Mail-Flussregeln zum Filtern von Massen-e-Mails konfiguriert wurden:

- Wechseln Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln** \> \> wählen Sie die Regel](../../media/ITPro-EAC-EditIcon.png)klicken Sie auf Bearbeitungssymbol **Bearbeiten** ![, und überprüfen Sie die Einstellungen.

- Ersetzen \<Sie in PowerShell den Regel\> Namen durch den Namen der Regel, und führen Sie den folgenden Befehl aus, um die Einstellungen zu überprüfen:

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- Senden Sie von einem externen Konto eine Testnachricht an einen betroffenen Empfänger, der eines der Ausdrücke oder Textmuster enthält, und überprüfen Sie die Ergebnisse.
