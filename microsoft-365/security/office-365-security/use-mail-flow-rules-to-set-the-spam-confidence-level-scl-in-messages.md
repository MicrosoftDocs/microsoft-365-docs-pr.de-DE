---
title: Verwenden von Nachrichtenfluss Regeln für die SCL-Bewertung in Nachrichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie Sie Nachrichtenfluss Regeln (Transportregeln) erstellen, um Nachrichten zu identifizieren und die SCL-Bewertung (Spam Confidence Level) von Nachrichten in Exchange Online Schutz festzulegen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 447333eb968ba7d91a1673c57b11afdb16b90469
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659837"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a>Verwenden von Nachrichtenfluss Regeln zum Festlegen der SCL-Bewertung (Spam Confidence Level) in Nachrichten in EoP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer verwendet EoP Antispam-Richtlinien (auch als Spamfilter Richtlinien oder Inhaltsfilter Richtlinien bezeichnet), um eingehende Nachrichten auf Spam zu überprüfen. Weitere Informationen finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md).

Wenn Sie bestimmte Nachrichten als Spam kennzeichnen möchten, bevor Sie sogar durch Spamfilterung gescannt werden, oder um Nachrichten zu markieren, damit Sie die Spamfilterung überspringen, können Sie Nachrichtenfluss Regeln (auch bekannt als Transportregeln) erstellen, um die Nachrichten zu identifizieren und die SCL-Bewertung (Spam Confidence Level) festzulegen. Weitere Informationen zur SCL-Bewertung finden Sie unter [Spam Confidence Level (SCL) in EoP](spam-confidence-levels.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie müssen Berechtigungen in Exchange Online oder Exchange Online Schutz zugewiesen werden, bevor Sie die Verfahren in diesem Artikel ausführen können. Insbesondere benötigen Sie die **Transport Regel** Rolle, die standardmäßig der Rollengruppe **"Organisationsverwaltung**", " **Compliance-Verwaltung** " (globale Administratoren) und der Rolle " **Datensatzverwaltung** " zugewiesen ist.

  Weitere Informationen hierzu finden Sie in den folgenden Themen:

  - [Berechtigungen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [Berechtigungen in EOP als eigenständige Lösung](feature-permissions-in-eop.md)
  - [Verwenden der Exchange-Verwaltungskonsole ändern der Liste der Mitglieder in Rollengruppen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Informationen zum Öffnen des EAC in Exchange Online finden Sie unter [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center). Informationen zum Öffnen der Exchange-Verwaltungskonsole in eigenständigen EoP finden Sie unter [Exchange Admin Center in Standalone EoP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Weitere Informationen zu Nachrichtenfluss Regeln in Exchange Online und Exchange Online Schutz finden Sie unter [Mail Flow Rules (Transport Rules) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>Verwenden der Exchange-Verwaltungskonsole zum Erstellen einer e-Mail-Fluss Regel, die den SCL-Wert einer Nachricht festlegt

1. Navigieren Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln**.

2. Klicken Sie auf Add-Symbol **Hinzufügen** ![ ](../../media/ITPro-EAC-AddIcon.png) , und wählen Sie dann **neue Regel erstellen** aus.

3. Konfigurieren Sie auf der daraufhin geöffneten Seite **Neue Regel** die folgenden Einstellungen:

   - **Name**: Geben Sie einen eindeutigen, beschreibenden Namen für die Regel ein.

   - Klicken Sie auf **Weitere Optionen**.

   - **Diese Regel anwenden, wenn**: Wählen Sie eine oder mehrere Bedingungen aus, um Nachrichten zu identifizieren. Weitere Informationen finden Sie unter [Nachrichtenfluss Regelbedingungen und Ausnahmen (Prädikate) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

   - **Gehen Sie folgen** dermaßen vor: Wählen Sie **ändern die Nachrichteneigenschaften** \> **Festlegen der SCL-Bewertung (Spam Confidence Level)**. Konfigurieren Sie im angezeigten **SCL** -Dialogfeld einen der folgenden Werte:

   - **Spamfilterung umgehen**: durch die Nachrichten wird die Spamfilterung übersprungen.

     > [!CAUTION]
     > Achten Sie darauf, dass Nachrichten Spamfilterung überspringen. Angreifer können diese Sicherheitsanfälligkeit verwenden, um Phishing-und andere schädliche Nachrichten an Ihre Organisation zu senden. Die Nachrichtenfluss Regeln erfordern mehr als nur die e-Mail-Adresse oder Domäne des Absenders. Weitere Informationen finden Sie unter [Erstellen sicherer Absenderlisten in EoP](create-safe-sender-lists-in-office-365.md).

   - **0 bis 4**: die Nachricht wird über Spamfilterung zur zusätzlichen Verarbeitung gesendet.

   - **5 oder 6**: die Nachricht wird als **Spam** gekennzeichnet. Die Aktion, die Sie für **Spam** Filter Urteile in ihren Anti-Spam-Richtlinien konfiguriert haben, wird auf die Nachricht angewendet (der Standardwert ist **"Nachricht in Junk-e-Mail-Ordner"**).

   - **7 bis 9**: die Nachricht wird als **Spam mit hoher Vertrauens** Würdigkeit gekennzeichnet. Die Aktion, die Sie für Spam Filterungs Urteile mit **hoher Zuverlässigkeit** in ihren Anti-Spam-Richtlinien konfiguriert haben, wird auf die Nachricht angewendet (der Standardwert ist **"Nachricht in Junk-e-Mail-Ordner"**).

4. Geben Sie alle zusätzlichen Eigenschaften an, die für die Regel gewünscht werden. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

## <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Wenn Sie verifizieren möchten, dass das Verfahren ordnungsgemäß funktioniert, senden Sie eine E-Mail-Nachricht an einen Mitarbeiter in Ihrer Organisation, und prüfen Sie, ob die erwartete Aktion mit der Nachricht durchgeführt wird. Wenn Sie beispielsweise **die SCL-Bewertung (Spam Confidence Level) so festlegen** , dass die **Spamfilterung umgangen** wird, sollte die Nachricht an den Posteingang des angegebenen Empfängers gesendet werden. Wenn Sie jedoch **die SCL-Bewertung (Spam Confidence Level)** auf **9** festgelegt haben und die Spam-Aktion mit **hohem Vertrauens** Wert für ihre geltenden Antispampolitik die Nachricht in den Junk-e-Mail-Ordner verschiebt, sollte die Nachricht an den Junk-e-Mail-Ordner des angegebenen Empfängers gesendet werden.
