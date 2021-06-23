---
title: Automatische Bereinigung zur Nullstunde in Microsoft Defender für Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 06/22/2021
audience: Admin
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Zap (Zero-Hour Auto Purge) verschiebt übermittelte Nachrichten in einem Exchange Online Postfach in den Junk-E-Mail-Ordner oder in die Quarantäne, die nach der Zustellung als Spam oder Phishing eingestuft wurden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fdfc39b8bd18d33f95b85028e3661008a17a1209
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083500"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>Automatische Bereinigung (ZERO-Hour Auto Purge, ZAP) in Exchange Online

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="zero-hour-auto-purge-zap-basics"></a>Zero-Hour Auto Purge (ZAP)-Grundlagen

In Microsoft 365 Organisationen mit Postfächern in Exchange Online ist ZAP (Zero-Hour Auto Purge) ein Feature zum Schutz von E-Mails, das böswillige Phishing-, Spam- oder Schadsoftwarenachrichten erkennt und neutralisiert, die bereits an Exchange Online Postfächer übermittelt wurden.

ZAP funktioniert nicht in eigenständigen Exchange Online Protection(EOP)-Umgebungen, die lokale Exchange Postfächer schützen.

## <a name="how-zap-works"></a>Funktionsweise von ZAP

Spam- und Schadsoftwaresignaturen werden täglich in Echtzeit im Dienst aktualisiert. Benutzer können jedoch aus einer Vielzahl von Gründen weiterhin bösartige Nachrichten empfangen, z. B. wenn Inhalte nach der Zustellung an benutzerdekantiert werden. ZAP behebt dieses Problem, indem updates für die Spam- und Schadsoftwaresignaturen im Dienst kontinuierlich überwacht werden. ZAP kann Nachrichten suchen und entfernen, die sich bereits im Postfach eines Benutzers befinden.

Die ZAP-Aktion ist für den Benutzer nahtlos. sie werden nicht benachrichtigt, wenn eine Nachricht erkannt und verschoben wird.

[Tresor Absenderlisten,](create-safe-sender-lists-in-office-365.md)Nachrichtenflussregeln (auch als Transportregeln bezeichnet), Posteingangsregeln oder zusätzliche Filter haben Vorrang vor ZAP. Ähnlich wie beim Nachrichtenfluss bedeutet dies, dass selbst wenn der Dienst feststellt, dass die zugestellte Nachricht ZAP benötigt, die Nachricht aufgrund der Konfiguration sicherer Absender nicht bearbeitet wird. Dies ist ein weiterer Grund, bei der Konfiguration von Nachrichten zur Umgehung der Filterung vorsichtig zu sein.

### <a name="zero-hour-auto-purge-zap-for-malware"></a>Automatische Bereinigung zur Nullstunde (ZAP) für Schadsoftware

Für **gelesene oder ungelesene Nachrichten,** die nach der Übermittlung Schadsoftware enthalten, isoliert ZAP die Nachricht, die die Antischadsoftwareanlage enthält. Nur Administratoren können Schadsoftwarenachrichten unter Quarantäne stellen und verwalten.

ZAP für Schadsoftware ist in Antischadsoftwarerichtlinien standardmäßig aktiviert. Weitere Informationen finden Sie unter [Konfigurieren von Antischadsoftwarerichtlinien in EOP.](configure-anti-malware-policies.md)

### <a name="zero-hour-auto-purge-zap-for-phishing"></a>Automatische Bereinigung zur Nullstunde (ZAP) für Phishing

Für **gelesene oder ungelesene Nachrichten,** die nach der Zustellung als Phishing erkannt werden, hängt das ZAP-Ergebnis von der Aktion ab, die für eine **Phishing-E-Mail-Filterbewertung** in der geltenden Antispamrichtlinie konfiguriert ist. Die verfügbaren Filterbewertungsaktionen für Phishing und deren mögliche ZAP-Ergebnisse werden in der folgenden Liste beschrieben:

- **X-Header hinzufügen,** **Betreffzeile mit Text vorangestellt,** **Nachricht an E-Mail-Adresse umleiten,** **Nachricht löschen:** ZAP führt keine Aktion für die Nachricht aus.

- **Nachricht in Junk-E-Mail verschieben:** ZAP verschiebt die Nachricht in den Junk-E-Mail-Ordner, solange die Junk-E-Mail-Regel für das Postfach aktiviert ist (sie ist standardmäßig aktiviert). Weitere Informationen finden Sie unter [Konfigurieren von Junk-E-Mail-Einstellungen für Exchange Online Postfächer in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Quarantänenachricht:** ZAP isoliert die Nachricht.

Standardmäßig ist ZAP für Phishing in Antispamrichtlinien aktiviert, und die Standardaktion für die **Phishing-E-Mail-Filterbewertung** lautet **"Quarantänenachricht",** was bedeutet, dass ZAP für Phishing die Nachricht standardmäßig unter Quarantäne stellt.

Weitere Informationen zum Konfigurieren von Spamfilterbewertungen finden Sie unter [Konfigurieren von Antispamrichtlinien in Microsoft 365.](configure-your-spam-filter-policies.md)

### <a name="zero-hour-auto-purge-zap-for-high-confidence-phishing"></a>Automatische Bereinigung zur Nullstunde (ZAP) für Phishing mit hoher Vertrauenswürdigkeit

Für **gelesene oder ungelesene Nachrichten,** die nach der Zustellung als Phishing mit hoher Konfidenz erkannt werden, unter quarantäneet ZAP die Nachricht. Nur Administratoren können Phishingnachrichten mit hoher Vertrauenswürdigkeit aus der Quarantäne anzeigen und verwalten.

ZAP für Phishing mit hoher Konfidenz ist standardmäßig aktiviert. Weitere Informationen finden Sie unter ["Standardmäßig sichern" in Office 365.](secure-by-default.md)

### <a name="zero-hour-auto-purge-zap-for-spam"></a>Automatische Bereinigung zur Nullstunde (ZAP) für Spam

Für **ungelesene Nachrichten,** die nach der Zustellung als Spam erkannt werden, hängt das ZAP-Ergebnis von der Aktion ab, die für die **Spamfilterbewertung** in der entsprechenden Antispamrichtlinie konfiguriert ist. Die verfügbaren Filterbewertungsaktionen für Spam und deren mögliche ZAP-Ergebnisse werden in der folgenden Liste beschrieben:

- **X-Header hinzufügen,** **Betreffzeile mit Text vorangestellt,** **Nachricht an E-Mail-Adresse umleiten,** **Nachricht löschen:** ZAP führt keine Aktion für die Nachricht aus.

- **Nachricht in Junk-E-Mail verschieben:** ZAP verschiebt die Nachricht in den Junk-E-Mail-Ordner, solange die Junk-E-Mail-Regel für das Postfach aktiviert ist (sie ist standardmäßig aktiviert). Weitere Informationen finden Sie unter [Konfigurieren von Junk-E-Mail-Einstellungen für Exchange Online Postfächer in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Quarantänenachricht:** ZAP isoliert die Nachricht. Endbenutzer können ihre eigenen in Spamquarantäne befindlichen Nachrichten anzeigen und verwalten.

Standardmäßig ist Spam ZAP in Antispamrichtlinien aktiviert, und die Standardaktion für die **Spamfilterbewertung** lautet "Nachricht in **Junk-E-Mail-Ordner verschieben",** was bedeutet, dass Spam-ZAP **ungelesene** Nachrichten standardmäßig in den Junk-E-Mail-Ordner verschiebt.

Weitere Informationen zum Konfigurieren von Spamfilterbewertungen finden Sie unter [Konfigurieren von Antispamrichtlinien in Microsoft 365.](configure-your-spam-filter-policies.md)

### <a name="zero-hour-auto-purge-zap-considerations-for-microsoft-defender-for-office-365"></a>Überlegungen zur automatischen Bereinigung (Zero-Hour Auto Purge, ZAP) für Microsoft Defender für Office 365

ZAP unter quarantäne stellt keine Nachricht unter Quarantäne, die sich im Prozess der [dynamischen Übermittlung](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) in Tresor Attachments-Überprüfung befindet oder bei der die EOP-Schadsoftwarefilterung die Anlage bereits durch die Datei **"Schadsoftwarewarnung Text.txt"** ersetzt hat. Wenn für diese Nachrichtentypen ein Phishing- oder Spamsignal empfangen wird und die Filterbewertung in der Antispamrichtlinie so festgelegt ist, dass eine Aktion für die Nachricht ausgeführt wird (Verschieben zu Junk, Umleiten, Löschen oder Quarantäne), wird ZAP standardmäßig als Aktion "Zu Junk verschieben" verwendet.

## <a name="how-to-see-if-zap-moved-your-message"></a>So sehen Sie, ob ZAP Ihre Nachricht verschoben hat

Um festzustellen, ob ZAP Ihre Nachricht verschoben hat, können Sie entweder den [Bedrohungsschutzstatusbericht](view-email-security-reports.md#threat-protection-status-report) oder [den Bedrohungs-Explorer (und Echtzeiterkennungen)](threat-explorer.md)verwenden. Beachten Sie, dass ZAP als Systemaktion nicht in den Exchange Postfachüberwachungsprotokollen protokolliert wird.

## <a name="zero-hour-auto-purge-zap-faq"></a>Zero-hour auto purge (ZAP) FAQ

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>Was geschieht, wenn eine seriöse Nachricht in den Junk-E-Mail-Ordner verschoben wird?

Sie sollten den normalen Berichterstellungsprozess für [falsch positive Ergebnisse](report-junk-email-messages-to-microsoft.md)befolgen. Der einzige Grund, warum die Nachricht aus dem Posteingang in den Junk-E-Mail-Ordner verschoben werden würde, wäre, weil der Dienst festgestellt hat, dass die Nachricht Spam oder bösartig war.

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>Was geschieht, wenn ich den Quarantäneordner anstelle des Junk-E-Mail-Ordners verwende?

ZAP ergreift Maßnahmen für eine Nachricht basierend auf der Konfiguration Ihrer Antispamrichtlinien, wie weiter oben in diesem Artikel beschrieben.

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>Was geschieht, wenn ich sichere Absender, Nachrichtenflussregeln oder Listen zugelassener/blockierter Absender verwende?

Tresor Absender, Nachrichtenflussregeln oder Blockieren und Zulassen von Organisationseinstellungen haben Vorrang. Diese Nachrichten werden von ZAP ausgeschlossen, da der Dienst die von Ihnen konfigurierte Aktion ausführt. Dies ist ein weiterer Grund, bei der Konfiguration von Nachrichten zur Umgehung der Filterung vorsichtig zu sein.

### <a name="what-are-the-licensing-requirements-for-zero-hour-auto-purge-zap-to-work"></a>Wie funktionieren die Lizenzierungsanforderungen für die automatische Bereinigung zur Nullstunde (Zero-Hour Auto Purge, ZAP) ?

Es gibt keine Einschränkungen für Lizenzen. ZAP funktioniert für alle Postfächer, die auf Exchange Online gehostet werden. ZAP funktioniert nicht in eigenständigen Exchange Online Protection(EOP)-Umgebungen, die lokale Exchange Postfächer schützen.

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>Was geschieht, wenn eine Nachricht in einen anderen Ordner verschoben wird (z. B. Posteingangsregeln)?

Die automatische Bereinigung zur Nullstunde funktioniert weiterhin, solange die Nachricht nicht gelöscht wurde oder solange die gleiche oder stärkere Aktion noch nicht angewendet wurde. Wenn beispielsweise die Antiphishingrichtlinie auf Quarantäne festgelegt ist und die Nachricht bereits in der Junk-E-Mail enthalten ist, wird ZAP Maßnahmen ergreifen, um die Nachricht unter Quarantäne zu stellen.

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>Wie wirkt sich ZAP auf postfächer im Haltebereich aus?

Die automatische Bereinigung zur 0-Stunden-Bereinigung unter Quarantäne stellt Nachrichten aus Postfächern in der Warteschleife unter Quarantäne. ZAP kann Nachrichten basierend auf der Aktion, die für eine Spam- oder Phishingbewertung in Antispamrichtlinien konfiguriert ist, in den Junk-E-Mail-Ordner verschieben.

Weitere Informationen zu Haltebereichen in Exchange Online finden Sie unter [In-Situ-Archiv und Beweissicherungsverfahren in Exchange Online.](/Exchange/security-and-compliance/in-place-and-litigation-holds)
