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
ms.openlocfilehash: 444a7f2a8342102c2222cc734b2592f46632f8d3
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035010"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a>Verwenden von Nachrichtenflussregeln zum Festlegen der SCL-Bewertung (Spam Confidence Level) in Nachrichten

Wenn Sie ein Microsoft 365-Kunde mit Postfächern in Exchange Online oder ein eigenständiger Exchange Online Schutz (EoP)-Kunde ohne Exchange Online Postfächer sind, verwendet EoP Antispam-Richtlinien (auch bekannt als Spamfilter-oder Inhaltsfilter Richtlinien), um eingehende Nachrichten auf Spam zu überprüfen. Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien in Office 365](configure-your-spam-filter-policies.md).

Wenn Sie bestimmte Nachrichten als Spam kennzeichnen möchten, bevor Sie sogar durch Spamfilterung gescannt werden, oder um Nachrichten zu markieren, damit Sie die Spamfilterung überspringen, können Sie Nachrichtenfluss Regeln (auch bekannt als Transportregeln) erstellen, um die Nachrichten zu identifizieren und die SCL-Bewertung (Spam Confidence Level) festzulegen. Weitere Informationen zur SCL-Bewertung finden Sie unter [Spam Confidence Level (SCL) in Office 365](spam-confidence-levels.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie müssen Berechtigungen in Exchange Online zugewiesen werden, bevor Sie diese Verfahren ausführen können. Insbesondere müssen Sie die Rolle " **Transport Rules** " erhalten, die standardmäßig der Rollen " **Organisationsverwaltung**", " **Richtlinientreue Verwaltung**" und " **Datensatzverwaltung** " zugewiesen ist. Weitere Informationen finden Sie unter [Verwalten von Rollengruppen in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).

- Informationen zum Öffnen des EAC in Exchange Online finden Sie unter [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).

- Weitere Informationen zu Nachrichtenfluss Regeln in Exchange Online finden Sie unter [Mail Flow Rules (Transport Rules) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>Verwenden der Exchange-Verwaltungskonsole zum Erstellen einer e-Mail-Fluss Regel, die den SCL-Wert einer Nachricht festlegt

1. Navigieren Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln**.

2. Klicken Sie auf Add](../../media/ITPro-EAC-AddIcon.png) -Symbol **Hinzufügen** ![, und wählen Sie dann **neue Regel erstellen**aus.

3. Konfigurieren Sie auf der daraufhin geöffneten Seite **Neue Regel** die folgenden Einstellungen:

   - **Name**: Geben Sie einen eindeutigen, beschreibenden Namen für die Regel ein.

   - Klicken Sie auf **Weitere Optionen**.

   - **Diese Regel anwenden, wenn**: Wählen Sie eine oder mehrere Bedingungen aus, um Nachrichten zu identifizieren. Weitere Informationen finden Sie unter [Nachrichtenfluss Regelbedingungen und Ausnahmen (Prädikate) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

   - **Gehen Sie folgen**dermaßen vor: Wählen Sie **ändern die Nachrichteneigenschaften** \> **Festlegen der SCL-Bewertung (Spam Confidence Level)**. Konfigurieren Sie im angezeigten **SCL** -Dialogfeld einen der folgenden Werte:

   - **Spamfilterung umgehen**: Hiermit wird der SCL-Wert auf-1 festgelegt, was bedeutet, dass die Nachrichten die Spamfilterung überspringen.

     > [!CAUTION]
     > Achten Sie darauf, dass Nachrichten Spamfilterung überspringen. Angreifer können diese Sicherheitsanfälligkeit verwenden, um Phishing-und andere schädliche Nachrichten an Ihre Organisation zu senden. Die Nachrichtenfluss Regeln erfordern mehr als nur die e-Mail-Adresse oder Domäne des Absenders. Weitere Informationen finden Sie unter [Erstellen von Listen sicherer Absender in Office 365](create-safe-sender-lists-in-office-365.md).

   - **0 bis 4**: die Nachricht wird über Spamfilterung zur zusätzlichen Verarbeitung gesendet.

   - **5 oder 6**: die Nachricht wird als **Spam**gekennzeichnet. Die Aktion, die Sie für **Spam** Filter Urteile in ihren Anti-Spam-Richtlinien konfiguriert haben, wird auf die Nachricht angewendet (der Standardwert ist **"Nachricht in Junk-e-Mail-Ordner"**).

   - **7 bis 9**: die Nachricht wird als **Spam mit hoher Vertrauens**Würdigkeit gekennzeichnet. Die Aktion, die Sie für Spam Filterungs Urteile mit **hoher Zuverlässigkeit** in ihren Anti-Spam-Richtlinien konfiguriert haben, wird auf die Nachricht angewendet (der Standardwert ist **"Nachricht in Junk-e-Mail-Ordner"**).

4. Geben Sie alle zusätzlichen Eigenschaften an, die für die Regel gewünscht werden. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

## <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Wenn Sie verifizieren möchten, dass das Verfahren ordnungsgemäß funktioniert, senden Sie eine E-Mail-Nachricht an einen Mitarbeiter in Ihrer Organisation, und prüfen Sie, ob die erwartete Aktion mit der Nachricht durchgeführt wird. Wenn Sie z. B. **den SCL-Wert (Spam Confidence Level)** auf **Spamfilterung umgehen** setzen, sollte die Nachricht an das Postfach des angegebenen Empfängers gesendet werden. Wenn Sie allerdings **den SCL-Wert (Spam Confidence Level)** auf **9** gesetzt haben und die Aktion in der entsprechenden Inhaltsfilterungsrichtlinie für eine **Nachricht mit hoher Spamwahrscheinlichkeit** darin besteht, die Nachricht in den Junk-E-Mail-Ordner zu verschieben, sollte die Nachricht an den Junk-E-Mail-Ordner des angegebenen Empfängers gesendet werden.
