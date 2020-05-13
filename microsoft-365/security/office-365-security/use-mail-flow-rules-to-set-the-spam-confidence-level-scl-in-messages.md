---
title: Verwenden von Nachrichtenfluss Regeln für die SCL-Bewertung in Nachrichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie Sie Nachrichtenfluss Regeln (Transportregeln) erstellen, um Nachrichten zu identifizieren und die SCL-Bewertung (Spam Confidence Level) von Nachrichten in Exchange Online Schutz festzulegen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f9af154a9f71992597e111147b792cd5286e2ad3
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208561"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a>Verwenden von Nachrichtenfluss Regeln zum Festlegen der SCL-Bewertung (Spam Confidence Level) in Nachrichten in EoP

In Microsoft 365-Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer verwendet EoP Antispam-Richtlinien (auch als Spamfilter Richtlinien oder Inhaltsfilter Richtlinien bezeichnet), um eingehende Nachrichten auf Spam zu überprüfen. Weitere Informationen finden Sie unter [configure Anti-Spam Policies in EoP](configure-your-spam-filter-policies.md).

Wenn Sie bestimmte Nachrichten als Spam kennzeichnen möchten, bevor Sie sogar durch Spamfilterung gescannt werden, oder um Nachrichten zu markieren, damit Sie die Spamfilterung überspringen, können Sie Nachrichtenfluss Regeln (auch bekannt als Transportregeln) erstellen, um die Nachrichten zu identifizieren und die SCL-Bewertung (Spam Confidence Level) festzulegen. Weitere Informationen zur SCL-Bewertung finden Sie unter [Spam Confidence Level (SCL) in EoP](spam-confidence-levels.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie müssen Berechtigungen in Exchange Online zugewiesen werden, bevor Sie diese Verfahren ausführen können. Insbesondere müssen Sie die Rolle " **Transport Rules** " erhalten, die standardmäßig der Rollen " **Organisationsverwaltung**", " **Richtlinientreue Verwaltung**" und " **Datensatzverwaltung** " zugewiesen ist. Weitere Informationen finden Sie unter [Verwalten von Rollengruppen in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).

- Informationen zum Öffnen des EAC in Exchange Online finden Sie unter [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).

- Weitere Informationen zu Nachrichtenfluss Regeln in Exchange Online finden Sie unter [Mail Flow Rules (Transport Rules) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>Verwenden der Exchange-Verwaltungskonsole zum Erstellen einer e-Mail-Fluss Regel, die den SCL-Wert einer Nachricht festlegt

1. Navigieren Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln**.

2. Klicken Sie auf Add-Symbol **Hinzufügen** ![ ](../../media/ITPro-EAC-AddIcon.png) , und wählen Sie dann **neue Regel erstellen**aus.

3. Konfigurieren Sie auf der daraufhin geöffneten Seite **Neue Regel** die folgenden Einstellungen:

   - **Name**: Geben Sie einen eindeutigen, beschreibenden Namen für die Regel ein.

   - Klicken Sie auf **Weitere Optionen**.

   - **Diese Regel anwenden, wenn**: Wählen Sie eine oder mehrere Bedingungen aus, um Nachrichten zu identifizieren. Weitere Informationen finden Sie unter [Nachrichtenfluss Regelbedingungen und Ausnahmen (Prädikate) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

   - **Gehen Sie folgen**dermaßen vor: Wählen Sie **ändern die Nachrichteneigenschaften** \> **Festlegen der SCL-Bewertung (Spam Confidence Level)**. Konfigurieren Sie im angezeigten **SCL** -Dialogfeld einen der folgenden Werte:

   - **Spamfilterung umgehen**: Hiermit wird der SCL-Wert auf-1 festgelegt, was bedeutet, dass die Nachrichten die Spamfilterung überspringen.

     > [!CAUTION]
     > Achten Sie darauf, dass Nachrichten Spamfilterung überspringen. Angreifer können diese Sicherheitsanfälligkeit verwenden, um Phishing-und andere schädliche Nachrichten an Ihre Organisation zu senden. Die Nachrichtenfluss Regeln erfordern mehr als nur die e-Mail-Adresse oder Domäne des Absenders. Weitere Informationen finden Sie unter [Erstellen sicherer Absenderlisten in EoP](create-safe-sender-lists-in-office-365.md).

   - **0 bis 4**: die Nachricht wird über Spamfilterung zur zusätzlichen Verarbeitung gesendet.

   - **5 oder 6**: die Nachricht wird als **Spam**gekennzeichnet. Die Aktion, die Sie für **Spam** Filter Urteile in ihren Anti-Spam-Richtlinien konfiguriert haben, wird auf die Nachricht angewendet (der Standardwert ist **"Nachricht in Junk-e-Mail-Ordner"**).

   - **7 bis 9**: die Nachricht wird als **Spam mit hoher Vertrauens**Würdigkeit gekennzeichnet. Die Aktion, die Sie für Spam Filterungs Urteile mit **hoher Zuverlässigkeit** in ihren Anti-Spam-Richtlinien konfiguriert haben, wird auf die Nachricht angewendet (der Standardwert ist **"Nachricht in Junk-e-Mail-Ordner"**).

4. Geben Sie alle zusätzlichen Eigenschaften an, die für die Regel gewünscht werden. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

## <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Wenn Sie verifizieren möchten, dass das Verfahren ordnungsgemäß funktioniert, senden Sie eine E-Mail-Nachricht an einen Mitarbeiter in Ihrer Organisation, und prüfen Sie, ob die erwartete Aktion mit der Nachricht durchgeführt wird. Wenn Sie beispielsweise **die SCL-Bewertung (Spam Confidence Level) so festlegen** , dass die **Spamfilterung umgangen**wird, sollte die Nachricht an den Posteingang des angegebenen Empfängers gesendet werden. Wenn Sie jedoch **die SCL-Bewertung (Spam Confidence Level)** auf **9**festgelegt haben und die Spam-Aktion mit **hohem Vertrauens** Wert für ihre geltenden Antispampolitik die Nachricht in den Junk-e-Mail-Ordner verschiebt, sollte die Nachricht an den Junk-e-Mail-Ordner des angegebenen Empfängers gesendet werden.
