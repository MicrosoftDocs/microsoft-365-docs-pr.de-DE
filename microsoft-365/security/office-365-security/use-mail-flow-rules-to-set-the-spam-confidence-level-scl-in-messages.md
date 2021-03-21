---
title: Verwenden von Nachrichtenflussregeln für die SCL in Nachrichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie Sie Nachrichtenflussregeln (Transportregeln) erstellen, um Nachrichten zu identifizieren und die Spamsicherheitsstufe (Spam Confidence Level, SCL) von Nachrichten in Exchange Online Protection festlegen.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1d7d1de194d8529fd3cf3e2d1da68c1f928ffcfa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921132"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a>Verwenden von Nachrichtenflussregeln zum Festlegen der Spamsicherheitsstufe (Spam Confidence Level, SCL) in Nachrichten in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer verwendet EOP Antispamrichtlinien (auch als Spamfilterrichtlinien oder Inhaltsfilterrichtlinien bezeichnet), um eingehende Nachrichten auf Spam zu überprüfen. Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).

Wenn Sie bestimmte Nachrichten als Spam markieren möchten, bevor sie sogar von der Spamfilterung gescannt werden, oder Nachrichten markieren möchten, damit sie die Spamfilterung überspringen, können Sie Nachrichtenflussregeln erstellen (auch als Transportregeln bekannt), um die Nachrichten zu identifizieren und die Spamsicherheitsstufe (Spam Confidence Level, SCL) festlegen. Weitere Informationen zum SCL finden Sie unter [Spam Confidence Level (SCL) in EOP](spam-confidence-levels.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen in Exchange Online oder Exchange Online Protection berechtigungen zugewiesen werden. Insbesondere benötigen Sie die Rolle **Transportregeln,** die standardmäßig den Rollengruppen **Organisationsverwaltung,** **Complianceverwaltung** (globale Administratoren) und **Datensatzverwaltung** zugewiesen ist.

  Weitere Informationen finden Sie in den folgenden Themen:

  - [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo)
  - [Berechtigungen in EOP als eigenständige Lösung](feature-permissions-in-eop.md)
  - [Ändern der Liste der Mitglieder in Rollengruppen mithilfe der EAC](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Informationen zum Öffnen der EAC in Exchange Online finden Sie unter [Exchange Admin Center in Exchange Online](/Exchange/exchange-admin-center). Informationen zum Öffnen der EAC im eigenständigen EOP finden Sie unter [Exchange Admin Center im eigenständigen EOP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Weitere Informationen zu Nachrichtenflussregeln in Exchange Online und Exchange Online Protection finden Sie unter [Nachrichtenflussregeln (Transportregeln) in Exchange Online.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>Verwenden der EAC zum Erstellen einer Nachrichtenflussregel, die die SCL einer Nachricht legt

1. Navigieren Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln**.

2. Klicken **Sie auf** Hinzufügen ![ ](../../media/ITPro-EAC-AddIcon.png) (Symbol) und wählen Sie **dann Neue Regel erstellen aus.**

3. Konfigurieren Sie auf der daraufhin geöffneten Seite **Neue Regel** die folgenden Einstellungen:

   - **Name**: Geben Sie einen eindeutigen, beschreibenden Namen für die Regel ein.

   - Klicken Sie auf **Weitere Optionen**.

   - **Wenden Sie diese Regel an,** wenn : Wählen Sie eine oder mehrere Bedingungen aus, um Nachrichten zu identifizieren. Weitere Informationen finden Sie unter [Nachrichtenflussregelbedingungen und Ausnahmen (Prädikate) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

   - **Gehen Sie wie folgt** vor: Wählen Sie **Ändern der Nachrichteneigenschaften** \> **festlegen die Spamsicherheitsstufe (Spam Confidence Level, SCL) aus.** Konfigurieren Sie im angezeigten Dialogfeld **SCL** angeben einen der folgenden Werte:

   - **Spamfilter umgehen:** Die Nachrichten überspringen die Spamfilterung.

     > [!CAUTION]
     > Achten Sie darauf, dass Nachrichten die Spamfilterung überspringen können. Angreifer können diese Sicherheitsanfälligkeit verwenden, um Phishing und andere schädliche Nachrichten an Ihre Organisation zu senden. Die Nachrichtenflussregeln erfordern mehr als nur die E-Mail-Adresse oder Domäne des Absenders. Weitere Informationen finden Sie unter [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).

   - **0 bis 4**: Die Nachricht wird zur weiteren Verarbeitung über die Spamfilterung gesendet.

   - **5 oder 6**: Die Nachricht ist als **Spam gekennzeichnet.** Die Aktion, die Sie  für Spamfilterungen in Ihren Antispamrichtlinien konfiguriert haben, wird auf die Nachricht angewendet (der Standardwert ist Nachrichten in Junk-E-Mail-Ordner **verschieben).**

   - **7 bis 9**: Die Nachricht ist als Spam mit **hoher Vertrauen gekennzeichnet.** Die Aktion, die Sie  für Die Spamfilterung mit hoher Sicherheit in Ihren Antispamrichtlinien konfiguriert haben, wird auf die Nachricht angewendet (der Standardwert ist Nachrichten in Junk-E-Mail-Ordner **verschieben).**

4. Geben Sie alle zusätzlichen Eigenschaften an, die Sie für die Regel wünschen. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

## <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Wenn Sie verifizieren möchten, dass das Verfahren ordnungsgemäß funktioniert, senden Sie eine E-Mail-Nachricht an einen Mitarbeiter in Ihrer Organisation, und prüfen Sie, ob die erwartete Aktion mit der Nachricht durchgeführt wird. Wenn Sie beispielsweise die Spamsicherheitsstufe **(Spam Confidence Level, SCL)** auf **Spamfilter** umgehen festlegen, sollte die Nachricht an den Posteingang des angegebenen Empfängers gesendet werden. Wenn Sie jedoch die Spamsicherheitsstufe **(Spam Confidence Level, SCL)** auf **9** festlegen und die Aktion Spam mit hoher Sicherheit für Ihre geltenden Antispamrichtlinien die Nachricht in den Junk-E-Mail-Ordner verschieben soll, sollte die Nachricht an den Junk-E-Mail-Ordner des angegebenen Empfängers gesendet werden. 