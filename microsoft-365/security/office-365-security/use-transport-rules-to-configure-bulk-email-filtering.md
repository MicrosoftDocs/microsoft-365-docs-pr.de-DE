---
title: Verwenden von Nachrichtenflussregeln zum Filtern von Massen-E-Mails
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie Nachrichtenflussregeln (Transportregeln) verwenden, um Massen-E-Mails (graue E-Mails) in Exchange Online Protection (EOP) zu identifizieren und zu filtern.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c86f229d6c7371854878a67937cc38374ed00961
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206071"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a>Verwenden von Regeln zum Filtern von Massen-E-Mails in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer verwendet EOP Antispamrichtlinien (auch als Spamfilterrichtlinien oder Inhaltsfilterrichtlinien bekannt), um eingehende Nachrichten auf Spam und Massennachrichten (auch als graue E-Mails bekannt) zu überprüfen. Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).

Wenn Sie mehr Optionen zum Filtern von Massennachrichten wünschen, können Sie Nachrichtenflussregeln (auch transport rules) erstellen, um nach Textmustern oder Ausdrücken zu suchen, die häufig in Massennachrichten gefunden werden, und diese Nachrichten als Spam markieren. Weitere Informationen zu Massen-E-Mails finden Sie unter [Was ist der](what-s-the-difference-between-junk-email-and-bulk-email.md) Unterschied zwischen Junk-E-Mail und Massen-E-Mail? und Massenbeschwerdestufe [(Bulk Complaint Level, BCL) in EOP](bulk-complaint-level-values.md).

In diesem Thema wird erläutert, wie diese Nachrichtenflussregeln im Exchange Admin Center (EAC) und in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständiges EOP PowerShell für Organisationen ohne Exchange #A0) erstellt werden.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen in Exchange Online oder Exchange Online Protection berechtigungen zugewiesen werden. Insbesondere benötigen Sie die Rolle **Transportregeln,** die standardmäßig den Rollengruppen **Organisationsverwaltung,** **Complianceverwaltung** (globale Administratoren) und **Datensatzverwaltung** zugewiesen ist.

  Weitere Informationen finden Sie in den folgenden Themen:

  - [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo)
  - [Berechtigungen in EOP als eigenständige Lösung](feature-permissions-in-eop.md)
  - [Ändern der Liste der Mitglieder in Rollengruppen mithilfe der EAC](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Informationen zum Öffnen der EAC in Exchange Online finden Sie unter [Exchange Admin Center in Exchange Online](/Exchange/exchange-admin-center). Informationen zum Öffnen der EAC im eigenständigen EOP finden Sie unter [Exchange Admin Center im eigenständigen EOP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Weitere Informationen zu Nachrichtenflussregeln in Exchange Online und eigenständigem EOP finden Sie in den folgenden Themen:

  - [Nachrichtenflussregeln (Transportregeln) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Nachrichtenflussregel-Bedingungen und -Ausnahmen (Prädikate) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Aktionen für Nachrichtenflussregeln in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- Die Liste der Wörter und Textmuster, die zum Identifizieren von Massen-E-Mails in den Beispielen verwendet werden, ist nicht vollständig. Sie können Einträge nach Bedarf hinzufügen und entfernen. Sie sind jedoch ein guter Ausgangspunkt.

- Die Suche nach Wörtern oder Textmustern im Betreff oder anderen Kopfzeilenfeldern in der Nachricht tritt *nach* der Decodierung der Nachricht aus der MIME-Inhaltsübertragungscodierungsmethode ein, die für die Übermittlung der binären Nachricht zwischen SMTP-Servern im ASCII-Text verwendet wurde. Sie können keine Bedingungen oder Ausnahmen für die Suche nach Rohwerten (in der Regel Base64-codiert) im Betreff oder in anderen Kopfzeilenfeldern in Nachrichten verwenden.

- Die folgenden Verfahren kennzeichnen eine Massennachricht als Spam für Ihre gesamte Organisation. Sie können jedoch eine weitere Bedingung hinzufügen, um diese Regeln nur auf bestimmte Empfänger anzuwenden, sodass Sie eine aggressive Filterung für einige wenige Benutzer mit hohem Ziel verwenden können, während die restlichen Benutzer (die hauptsächlich die Massen-E-Mails erhalten, für die sie sich angemeldet haben) nicht betroffen sind.

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a>Verwenden der EAC zum Erstellen von Nachrichtenflussregeln zum Filtern von Massen-E-Mails

1. Navigieren Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln**.

2. Klicken **Sie auf** Hinzufügen ![ ](../../media/ITPro-EAC-AddIcon.png) (Symbol) und wählen Sie **dann Neue Regel erstellen aus.**

3. Konfigurieren Sie auf der daraufhin geöffneten Seite **Neue Regel** die folgenden Einstellungen:

   - **Name**: Geben Sie einen eindeutigen, beschreibenden Namen für die Regel ein.

   - Klicken Sie auf **Weitere Optionen**.

   - **Wenden Sie diese Regel an,** wenn : Konfigurieren Sie eine der folgenden Einstellungen, um inhalte in Nachrichten mithilfe regulärer Ausdrücke (RegEx) oder Wörter oder Ausdrücke zu suchen:

     - **Betreff oder Textkörper** \> **Betreff oder** Textkörper entspricht diesen  Textmustern: Geben Sie im angezeigten Dialogfeld  Wörter oder Ausdrücke angeben einen der folgenden Werte ein, klicken Sie auf Symbol hinzufügen, und wiederholen Sie den Vorgang, bis Sie alle Werte eingegeben ![ ](../../media/ITPro-EAC-AddIcon.png) haben.

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

      Um einen Eintrag zu bearbeiten, wählen Sie ihn aus, und klicken Sie **auf Bearbeiten** ![ (Symbol). ](../../media/ITPro-EAC-EditIcon.png) Um einen Eintrag zu entfernen, wählen Sie ihn aus, und klicken **Sie auf Entfernen** ![ ](../../media/ITPro-EAC-DeleteIcon.png) (Symbol).

       Klicken Sie nach Abschluss des Vorgangs auf **OK**.

     - **Betreff oder Textkörper** \> **Betreff oder** Textkörper enthält eines  der folgenden Wörter: Geben Sie im angezeigten Dialogfeld  Wörter oder Ausdrücke angeben einen der folgenden Werte ein, klicken Sie auf Symbol hinzufügen, und wiederholen Sie den Vorgang, bis Sie alle Werte eingegeben ![ ](../../media/ITPro-EAC-AddIcon.png) haben.

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

      Um einen Eintrag zu bearbeiten, wählen Sie ihn aus, und klicken Sie **auf Bearbeiten** ![ (Symbol). ](../../media/ITPro-EAC-EditIcon.png) Um einen Eintrag zu entfernen, wählen Sie ihn aus, und klicken **Sie auf Entfernen** ![ ](../../media/ITPro-EAC-DeleteIcon.png) (Symbol).

       Klicken Sie nach Abschluss des Vorgangs auf **OK**.

   - **Gehen Sie wie folgt** vor: Wählen Sie **Ändern der Nachrichteneigenschaften** \> **festlegen die Spamsicherheitsstufe (Spam Confidence Level, SCL) aus.** Konfigurieren Sie im angezeigten Dialogfeld **SCL** angeben eine der folgenden Einstellungen:

     - Wählen Sie 6 aus, um Nachrichten **als Spam** **zu markieren.** Die Aktion, die Sie  für Spamfilterungs-Urteile in Ihren Antispamrichtlinien konfiguriert haben, wird auf die Nachrichten angewendet (der Standardwert ist Nachrichten in Junk-E-Mail-Ordner **verschieben).**

     - Wählen Sie 9 **aus, um** Nachrichten als Spam mit hoher Sicherheit **zu markieren.** Die Aktion, die Sie  für Die Spamfilterung mit hoher Sicherheit in Ihren Antispamrichtlinien konfiguriert haben, wird auf die Nachrichten angewendet (der Standardwert ist Nachrichten in Junk-E-Mail-Ordner **verschieben).**

    Weitere Informationen zu SCL-Werten finden Sie unter [Spam Confidence Level (SCL) in EOP](spam-confidence-levels.md).

   Klicken Sie nach Abschluss des Abschlusses auf **Speichern.**

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a>Verwenden von PowerShell zum Erstellen von Nachrichtenflussregeln zum Filtern von Massen-E-Mails

Verwenden Sie die folgende Syntax, um eine oder beide Nachrichtenflussregeln zu erstellen (reguläre Ausdrücke im Vergleich zu Wörtern):

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

In diesem Beispiel wird eine neue Regel mit dem Namen "Massen-E-Mail-Filterung - RegEx" erstellt, die dieselbe Liste regulärer Ausdrücke aus früheren Themen verwendet, um Nachrichten als **Spam zu setzen.**

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? src=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

In diesem Beispiel wird eine neue Regel mit dem Namen "Massen-E-Mail-Filterung - Wörter" erstellt, die dieselbe Liste von Wörtern aus früheren Themen verwendet, um Nachrichten als Spam mit hoher Vertrauen **zu setzen.**

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

Detaillierte Informationen zur Syntax und den Parametern finden Sie unter [New-TransportRule](/powershell/module/exchange/new-transportrule).

## <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Gehen Sie wie folgt vor, um zu überprüfen, ob Sie Nachrichtenflussregeln zum Filtern von Massen-E-Mails konfiguriert haben:

- Wechseln Sie in der EAC zu **Nachrichtenfluss** Regeln wählen Sie die Regel auf Bearbeiten (Symbol bearbeiten) \>  \> \>  ![ ](../../media/ITPro-EAC-EditIcon.png) aus, und überprüfen Sie die Einstellungen.

- Ersetzen Sie in PowerShell durch den Namen der Regel, und führen Sie den \<Rule Name\> folgenden Befehl aus, um die Einstellungen zu überprüfen:

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- Senden Sie von einem externen Konto eine Testnachrichten an einen betroffenen Empfänger, der einen der Ausdrücke oder Textmuster enthält, und überprüfen Sie die Ergebnisse.