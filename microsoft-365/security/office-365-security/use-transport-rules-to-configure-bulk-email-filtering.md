---
title: Konfigurieren der Massen-e-Mail-Filterung in Exchange Online Protection mithilfe von Nachrichtenfluss Regeln
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
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
ms.openlocfilehash: 81b0f4cc58d712c3a1c1e09dab02d1c6f56cb69d
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42081818"
---
# <a name="use-mail-flow-rules-to-configure-bulk-email-filtering-in-exchange-online-protection"></a>Konfigurieren der Massen-e-Mail-Filterung in Exchange Online Protection mithilfe von Nachrichtenfluss Regeln

Sie können den unternehmensweiten Inhaltsfilter für Spam und Massen-E-Mails über die Standardrichtlinien für die Spam-Inhaltsfilterung festlegen. Informationen zum Festlegen der Richtlinien für die Inhaltsfilterung finden Sie unter [Konfigurieren von Spamfilterrichtlinien](configure-your-spam-filter-policies.md) und [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy).

Wenn Sie mehr Optionen zum Filtern von Massennachrichten wünschen, können Sie Nachrichtenfluss Regeln (auch bekannt als Transportregeln) erstellen, um nach Textmustern oder Ausdrücken zu suchen, die häufig in Massen-e-Mails gefunden werden. Alle Nachrichten, die diese Merkmale enthalten, werden als Spam markiert. Mithilfe dieser Regeln können Sie die Menge an unterwünschten Massen-E-Mails verringern, die Ihre Organisation empfängt.

> [!IMPORTANT]
> Bevor Sie die Nachrichtenfluss Regeln erstellen, die dieses Thema dokumentiert haben, sollten Sie zuerst den [Unterschied zwischen Junk-e-Mail und Massen-e-](what-s-the-difference-between-junk-email-and-bulk-email.md) Mails lesen und [Werte für Massen Reklamations Stufen](bulk-complaint-level-values.md)lesen.<br>Durch die folgenden Verfahren wird eine Nachricht für Ihre gesamte Organisation als Spam markiert. Sie können jedoch eine andere Bedingung hinzufügen, damit diese Regeln nur für bestimmte Empfänger in Ihrer Organisation gelten. Auf diese Weise können die aggressiven Filtereinstellungen für Massen-E-Mails nur für einige wenige Benutzer gelten, die verstärkt anvisiert werden, während der Rest Ihrer Benutzer (die zumeist die Massen-E-Mails erhalten, für die sie sich registriert haben) nicht betroffen sind.

## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-text-patterns"></a>Erstellen einer e-Mail-Fluss Regel zum Filtern von Massen-e-Mails basierend auf Textmustern

1. Navigieren Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln**.

2. Klicken Sie auf Add](../../media/ITPro-EAC-AddIcon.gif) -Symbol **Hinzufügen** ![, und wählen Sie dann **neue Regel erstellen**aus.

3. Geben Sie einen Namen für die Regel ein.

4. Klicken Sie auf **Weitere** ![Optionen mehr](../../media/ITPro-EAC-MoreOptionsIcon.png)Optionen Symbol. Aktivieren Sie unter **Diese Regel anwenden, wenn,** die Option **Betreff oder Nachrichtentext** \> **Betreff oder Nachrichtentext entspricht diesen Textmustern**.

5. Fügen Sie im Dialogfeld **Wörter oder Ausdrücke angeben** die folgenden regulären Ausdrücke hinzu, die häufig in Massen-e-Mails gefunden werden, und klicken Sie auf **OK** , wenn Sie fertig sind:

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

   Die obige Liste ist keine vollständige Sammlung regulärer Ausdrücke, die in Massen-e-Mails gefunden werden. mehr kann bei Bedarf hinzugefügt oder entfernt werden. Dies ist jedoch ein guter Ausgangspunkt.

   Die Suche nach Wörtern oder Textmustern im Betreff oder anderen Kopfzeilenfeldern in der Nachricht tritt *nach* der Decodierung der Nachricht aus der MIME-Inhaltsübertragungscodierungsmethode ein, die für die Übermittlung der binären Nachricht zwischen SMTP-Servern im ASCII-Text verwendet wurde. Sie können keine Bedingungen oder Ausnahmen für die Suche nach Rohwerten (in der Regel Base64-codiert) im Betreff oder in anderen Kopfzeilenfeldern in Nachrichten verwenden.

6. Wählen Sie unter **Gehen Sie folgendermaßen vor...** die Option **Nachrichteneigenschaften ändern** \> **SCL-Bewertung (Spam Confidence Level) festlegen** aus.

7. Legen Sie im Dialogfeld **SCL angeben** den SCL auf **5**, **6** oder **9** fest, und klicken Sie auf **OK**.

   Wenn der SCL auf 5 oder 6 festgelegt wird, wird die **Spam**-Aktion ausgeführt, und wenn der SCL auf 9 festgelegt wird, wird die Aktion **Nachricht mit hoher Spamwahrscheinlichkeit** ausgeführt, wie in der Inhaltsfilterrichtlinie konfiguriert. Der Dienst führt die in der Inhaltsfilterrichtlinie festgelegte Aktion aus. Die Standardaktion ist, die Nachricht an den Junk-E-Mail-Ordner der Empfänger zuzustellen. Es können allerdings, wie in [Konfigurieren von Spamfilterrichtlinien](configure-your-spam-filter-policies.md) beschrieben, andere Aktionen konfiguriert werden.

   Wenn Ihre konfigurierte Aktion darin besteht, die Nachricht zu isolieren, anstatt Sie an den Junk-e-Mail-Ordner des Empfängers zu senden, wird die Nachricht an die Administrator Quarantäne als e-Mail-Fluss-Regelübereinstimmung gesendet, und Sie ist in der Endbenutzer-Spamquarantäne oder über Endbenutzer nicht verfügbar. Spambenachrichtigungen.

   Weitere Informationen zu SCL-Werten im Dienst finden Sie unter [SCL-Bewertungen (Spam Confidence Level)](spam-confidence-levels.md).

8. Speichern Sie die Regel.

## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-phrases"></a>Erstellen einer e-Mail-Fluss Regel zum Filtern von Massen-e-Mails basierend auf Phrasen

1. Navigieren Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln**.

2. Klicken Sie auf Add](../../media/ITPro-EAC-AddIcon.gif) -Symbol **Hinzufügen** ![, und wählen Sie dann **neue Regel erstellen**aus.

3. Geben Sie einen Namen für die Regel ein.

4. Click **More options**. Under **Apply this rule if**, select **The subject or body** \> **subject or body includes any of these words**.

5. Geben Sie im Dialogfeld **Wörter oder Ausdrücke angeben** die folgenden häufig in Massen-E-Mails vorkommenden Ausdrücke nacheinander ein, und klicken Sie auf **OK**, sobald Sie fertig sind:

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

   Diese Liste ist kein umfassender Satz von Ausdrücken, die in Massen-e-Mails gefunden werden. mehr kann bei Bedarf hinzugefügt oder entfernt werden. Dies ist jedoch ein guter Ausgangspunkt.

6. Wählen Sie unter **Gehen Sie folgendermaßen vor...** die Option **Nachrichteneigenschaften ändern** \> **SCL-Bewertung (Spam Confidence Level) festlegen** aus.

7. Legen Sie im Dialogfeld **SCL angeben** den SCL auf **5**, **6** oder **9** fest, und klicken Sie auf **OK**.

   Wenn der SCL auf 5 oder 6 festgelegt wird, wird die **Spam**-Aktion ausgeführt, und wenn der SCL auf 9 festgelegt wird, wird die Aktion **Nachricht mit hoher Spamwahrscheinlichkeit** ausgeführt, wie in der Inhaltsfilterrichtlinie konfiguriert. Der Dienst führt die in der Inhaltsfilterrichtlinie festgelegte Aktion aus. Die Standardaktion ist, die Nachricht an den Junk-E-Mail-Ordner der Empfänger zuzustellen. Es können allerdings, wie in [Konfigurieren von Spamfilterrichtlinien](configure-your-spam-filter-policies.md) beschrieben, andere Aktionen konfiguriert werden.

   Wenn Ihre konfigurierte Aktion darin besteht, die Nachricht zu isolieren, anstatt Sie an den Junk-e-Mail-Ordner des Empfängers zu senden, wird die Nachricht an die Administrator Quarantäne als e-Mail-Fluss-Regelübereinstimmung gesendet, und Sie ist in der Endbenutzer-Spamquarantäne oder über Endbenutzer nicht verfügbar. Spambenachrichtigungen.

   Weitere Informationen zu SCL-Werten im Dienst finden Sie unter [SCL-Bewertungen (Spam Confidence Level)](spam-confidence-levels.md).

8. Speichern Sie die Regel.

## <a name="for-more-information"></a>Weitere Informationen

[Worin besteht der Unterschied zwischen Junk-E-Mail und Massen-E-Mail?](what-s-the-difference-between-junk-email-and-bulk-email.md)

[BCL-Werte (Bulk Complaint Level)](bulk-complaint-level-values.md)

[Konfigurieren von Spamfilterrichtlinien](configure-your-spam-filter-policies.md)

[Erweiterte Spam Filterungsoptionen](advanced-spam-filtering-asf-options.md)
