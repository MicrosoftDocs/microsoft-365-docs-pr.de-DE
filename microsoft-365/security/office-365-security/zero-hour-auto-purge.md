---
title: Automatische Bereinigung zur Nullstunde (ZAP)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
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
description: Administratoren erfahren, wie ZAP (Zero-Hour Auto Purge) zugestellte Nachrichten in einem Exchange Online-Postfach in den Junk-E-Mail-Ordner oder in Quarantäne verschieben kann, die als Spam oder Phishing identifiziert wurden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5fd41cf45ad2a49d74684ae3e20dded5c1b8f034
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287305"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>Automatische Bereinigung zur Nullstunde (ZAP) in Exchange Online

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-zap"></a>Grundlegende Features von ZAP

In Microsoft 365-Organisationen mit Postfächern in Exchange Online ist ZAP (Zero-Hour Auto Purge) eine E-Mail-Schutzfunktion, die schädliche Phishing-, Spam- oder Schadsoftwarenachrichten, die bereits an Exchange Online-Postfächer übermittelt wurden, nachträglich erkennt und neutralisiert.

ZAP funktioniert nicht in eigenständigen Exchange Online Protection (EOP)-Umgebungen, die lokale Exchange-Postfächer schützen.

## <a name="how-zap-works"></a>Funktionsweise von ZAP

Spam- und Schadsoftwaresignaturen werden täglich in Echtzeit im Dienst aktualisiert. Benutzer können jedoch weiterhin bösartige Nachrichten aus einer Vielzahl von Gründen empfangen, z. B. wenn Inhalte nach der Zugestellt werden. ZAP behebt dieses Problem, indem Updates der Spam- und Schadsoftwaresignaturen im Dienst kontinuierlich überwacht werden. ZAP kann Nachrichten finden und entfernen, die sich bereits im Postfach eines Benutzers befinden.

Die #A0 ist für den Benutzer nahtlos. sie werden nicht benachrichtigt, wenn eine Nachricht erkannt und verschoben wird.

[Listen sicherer Absender,](create-safe-sender-lists-in-office-365.md)Nachrichtenflussregeln (auch als Transportregeln bezeichnet), Posteingangsregeln oder zusätzliche Filter haben Vorrang vor ZAP. Ähnlich wie beim Nachrichtenfluss bedeutet dies, dass die Nachricht aufgrund der Konfiguration sicherer Absender nicht reagiert wird, auch wenn der Dienst feststellt, dass die zugestellte Nachricht ZAP benötigt. Dies ist ein weiterer Grund, bei der Konfiguration von Nachrichten zur Umgehung der Filterung vorsichtig zu sein.

### <a name="malware-zap"></a>Schadsoftware ZAP

Bei **gelesenen oder ungelesenen** Nachrichten, die nach der Zustellung Schadsoftware enthalten, isoliert ZAP die Nachricht, die die Schadsoftwareanlage enthält. Nur Administratoren können Schadsoftwarenachrichten aus der Quarantäne anzeigen und verwalten.

Schadsoftware ZAP ist in Ansoftwarerichtlinien standardmäßig aktiviert. Weitere Informationen finden Sie unter [Konfigurieren von An malware-Richtlinien in EOP](configure-anti-malware-policies.md).

### <a name="phish-zap"></a>Phish ZAP

Für **gelesene** oder ungelesene Nachrichten, die nach der Zustellung als Phishing identifiziert  werden, hängt das Ergebnis von ZAP von der Aktion ab, die für eine Phishing-E-Mail-Filterungs-Entscheidung in der entsprechenden Antispamrichtlinie konfiguriert ist. Die verfügbaren Filterfilterungsaktionen für Phishing und deren mögliche ZAP-Ergebnisse werden in der folgenden Liste beschrieben:

- **X-Header hinzufügen,** **Betreffzeile** mit Text vorausbeschriften: ZAP ergreift keine Aktion für die Nachricht.

- **Nachricht in Junk-E-Mail** verschieben: ZAP verschiebt die Nachricht in den Junk-E-Mail-Ordner, solange die Junk-E-Mail-Regel für das Postfach aktiviert ist (sie ist standardmäßig aktiviert). Weitere Informationen finden Sie unter ["Konfigurieren von Junk-E-Mail-Einstellungen für Exchange Online-Postfächer in Microsoft 365".](configure-junk-email-settings-on-exo-mailboxes.md)

- **Nachricht an E-Mail-Adresse umleiten,** **Nachricht löschen,** **Nachricht isolieren:** ZAP isoliert die Nachricht.

Standardmäßig ist Phish ZAP in Antispamrichtlinien aktiviert, und  die Standardaktion für die Phishing-E-Mail-Filterungs-Filterung ist "Quarantänenachricht", was bedeutet, dass phish ZAP die Nachricht standardmäßig isoliert.

Weitere Informationen zum Konfigurieren von Spamfilterungsverdingungen finden Sie unter ["Konfigurieren von Antispamrichtlinien in Microsoft 365".](configure-your-spam-filter-policies.md)

### <a name="spam-zap"></a>Spam ZAP

Bei **ungelesenen** Nachrichten, die nach der Zustellung als Spam identifiziert werden,  hängt das Ergebnis von ZAP von der Aktion ab, die für die Spamfilterungsausnahme in der entsprechenden Antispamrichtlinie konfiguriert ist. Die verfügbaren Filterfilterungsaktionen für Spam und deren mögliche ZAP-Ergebnisse werden in der folgenden Liste beschrieben:

- **X-Header hinzufügen,** **Betreffzeile** mit Text vorausbeschriften: ZAP ergreift keine Aktion für die Nachricht.

- **Nachricht in Junk-E-Mail** verschieben: ZAP verschiebt die Nachricht in den Junk-E-Mail-Ordner, solange die Junk-E-Mail-Regel für das Postfach aktiviert ist (sie ist standardmäßig aktiviert). Weitere Informationen finden Sie unter ["Konfigurieren von Junk-E-Mail-Einstellungen für Exchange Online-Postfächer in Microsoft 365".](configure-junk-email-settings-on-exo-mailboxes.md)

- **Nachricht an E-Mail-Adresse umleiten,** **Nachricht löschen,** **Nachricht isolieren:** ZAP isoliert die Nachricht. Endbenutzer können ihre eigenen Nachrichten in Spamquarantäne anzeigen und verwalten.

Standardmäßig ist Spam ZAP in Antispamrichtlinien aktiviert, und  die Standardaktion für die Spamfilterungs-Benachrichtigung  ist "Nachricht in Junk-E-Mail-Ordner verschieben", was bedeutet, dass Spam-ZAP ungelesene Nachrichten standardmäßig in den Junk-E-Mail-Ordner verschiebt.

Weitere Informationen zum Konfigurieren von Spamfilterungsverdingungen finden Sie unter ["Konfigurieren von Antispamrichtlinien in Microsoft 365".](configure-your-spam-filter-policies.md)

### <a name="zap-considerations-for-microsoft-defender-for-office-365"></a>Überlegungen zu ZAP für Microsoft Defender für Office 365

ZAP isoliert keine Nachrichten unter Quarantäne, [](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) die sich im Prozess der dynamischen Zustellung in der Überprüfung auf sichere Anlagen oder in der EOP-Schadsoftwarefilterung die Anlage bereits durch die Datei "Schadsoftwarewarnung" Text.txt **hat.** Wenn ein Phishing- oder Spamsignal für diese Art von Nachrichten empfangen wird und die Filterungsverknappung in der Antispamrichtlinie so festgelegt ist, dass eine Aktion für die Nachricht (In Junk-, Umleitungs-, Lösch- oder Quarantäne-E-Mail-Nachrichten verschoben) festgelegt ist, wird für ZAP standardmäßig die Aktion "Zu Junk verschieben" verwendet.

## <a name="how-to-see-if-zap-moved-your-message"></a>Erfahren Sie, ob ZAP Ihre Nachricht verschoben hat

Um festzustellen, ob ZAP Ihre Nachricht verschoben hat, können Sie entweder den [Threat Protection Status](view-email-security-reports.md#threat-protection-status-report) Report oder den Threat Explorer [(und Echtzeiterkennungen) verwenden.](threat-explorer.md) Beachten Sie, dass ZAP als Systemaktion nicht in den Exchange-Postfach-Überwachungsprotokollen protokolliert wird.

## <a name="zap-faq"></a>HÄUFIG gestellte Fragen zu ZAP

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>Was geschieht, wenn eine legitime Nachricht in den Junk-E-Mail-Ordner verschoben wird?

Sie sollten den normalen Berichterstellungsprozess für falsch [positive Ergebnisse befolgen.](report-junk-email-messages-to-microsoft.md) Der einzige Grund, warum die Nachricht aus dem Posteingang in den Junk-E-Mail-Ordner verschoben würde, liegt daran, dass der Dienst festgestellt hat, dass es sich bei der Nachricht um Spam oder Schadsoftware handelt.

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>Was passiert, wenn ich den Quarantäneordner anstelle des Junk-E-Mail-Ordners verwende?

ZAP wird Maßnahmen für eine Nachricht basierend auf der Konfiguration Ihrer Antispamrichtlinien ergreifen, wie weiter oben in diesem Artikel beschrieben.

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>Was passiert, wenn ich sichere Absender, Nachrichtenflussregeln oder Listen zugelassener/blockierter Absender verwendet?

Sichere Absender, Nachrichtenflussregeln oder Einstellungen der Organisation blockieren und zulassen haben Vorrang. Diese Meldungen werden von ZAP ausgeschlossen, da der Dienst die von Ihnen konfigurierte Arbeit vor sich hat. Dies ist ein weiterer Grund, bei der Konfiguration von Nachrichten zur Umgehung der Filterung vorsichtig zu sein.

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>Was passiert, wenn eine Nachricht in einen anderen Ordner verschoben wird (z. B. Posteingangsregeln)?

ZAP funktioniert weiterhin, solange die Nachricht nicht gelöscht wurde oder solange die gleiche oder stärkere Aktion noch nicht angewendet wurde. Wenn die Antiphishingrichtlinie beispielsweise auf "Quarantäne" festgelegt ist und sich die Nachricht bereits in der Junk-E-Mail befindet, wird ZAP Maßnahmen ergreifen, um die Nachricht unter Quarantäne zu stellen.

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>Wie wirkt sich ZAP auf die In-Archiv-Postfächer aus?

ZAP isoliert Nachrichten nicht aus postfächern, die in der Warteschleife gespeichert sind. ZAP kann Nachrichten in den Junk-E-Mail-Ordner verschieben, basierend auf der Aktion, die für eine Spam- oder Phishing-Benachrichtigung in Antispamrichtlinien konfiguriert ist.

Weitere Informationen zu Halterechten in Exchange Online finden Sie unter [In-Place Hold and Litigation Hold in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).
