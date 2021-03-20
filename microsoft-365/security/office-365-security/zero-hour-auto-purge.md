---
title: Automatisches Löschen (Zero-Hour Auto Purge, ZAP)
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
description: Administratoren können erfahren, wie das automatische Löschen (Zero-Hour Auto Purge, ZAP) zugestellte Nachrichten in einem Exchange Online-Postfach rückwirkend in den Junk-E-Mail-Ordner oder in die Quarantäne verschieben kann, bei der es sich rückwirkend um Spam oder Phishing handelt.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b5744fdd4ce371f62fcb4b07a4cbcd003405c3db
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907976"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>Automatisches Löschen (Zero-Hour Auto Purge, ZAP) in Exchange Online

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-zap"></a>Grundlegende Features von ZAP

In Microsoft 365-Organisationen mit Postfächern in Exchange Online ist zap (Zero-Hour Auto Purge) ein E-Mail-Schutzfeature, das schädliche Phishing-, Spam- oder Schadsoftwarenachrichten, die bereits an Exchange Online-Postfächer zugestellt wurden, nachträglich erkennt und neutralisiert.

ZAP funktioniert nicht in eigenständigen Exchange Online Protection (EOP)-Umgebungen, die lokale Exchange-Postfächer schützen.

## <a name="how-zap-works"></a>Funktionsweise von ZAP

Spam- und Schadsoftwaresignaturen werden täglich in Echtzeit im Dienst aktualisiert. Benutzer können jedoch aus verschiedenen Gründen weiterhin schädliche Nachrichten empfangen, z. B. wenn Inhalte nach der Zugestellten an Benutzer mit Waffen bewaffnt werden. Zap behebt dieses Problem, indem Updates für Spam- und Schadsoftwaresignaturen im Dienst kontinuierlich überwacht werden. ZAP kann Nachrichten finden und entfernen, die sich bereits im Postfach eines Benutzers befinden.

Die #A0 ist für den Benutzer nahtlos. sie werden nicht benachrichtigt, wenn eine Nachricht erkannt und verschoben wird.

[Listen sicherer Absender,](create-safe-sender-lists-in-office-365.md)Nachrichtenflussregeln (auch als Transportregeln bezeichnet), Posteingangsregeln oder zusätzliche Filter haben Vorrang vor ZAP. Ähnlich wie beim Nachrichtenfluss bedeutet dies, dass die Nachricht aufgrund der Konfiguration sicherer Absender nicht reagiert wird, auch wenn der Dienst bestimmt, dass die zugestellte Nachricht ZAP benötigt. Dies ist ein weiterer Grund, um beim Konfigurieren von Nachrichten zur Umgehung der Filterung vorsichtig zu sein.

### <a name="malware-zap"></a>Schadsoftware ZAP

Für **lese- oder ungelesene** Nachrichten, die nach der Zustellung Schadsoftware enthalten, isoliert ZAP die Nachricht, die die Schadsoftwareanlage enthält. Nur Administratoren können Schadsoftwarenachrichten aus Quarantäne anzeigen und verwalten.

Schadsoftware-ZAP ist standardmäßig in Anti-Malware-Richtlinien aktiviert. Weitere Informationen finden Sie unter [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).

### <a name="phish-zap"></a>Phish ZAP

Für lese- oder **ungelesene** Nachrichten, die nach der Zustellung als Phishing identifiziert  werden, hängt das ERGEBNIS von der Aktion ab, die für ein Phishing-E-Mail-Filterergebnis in der entsprechenden Antispamrichtlinie konfiguriert ist. Die verfügbaren Filterungsaktionen für Phishing und deren mögliche ZAP-Ergebnisse werden in der folgenden Liste beschrieben:

- X-Header hinzufügen, **Betreffzeile** vorab mit Text, **Nachricht** an **E-Mail-Adresse** umleiten, Nachricht löschen : ZAP ergreift keine Aktion für die Nachricht.

- **Nachricht in Junk-E-Mail** verschieben: ZAP verschiebt die Nachricht in den Junk-E-Mail-Ordner, solange die Junk-E-Mail-Regel für das Postfach aktiviert ist (sie ist standardmäßig aktiviert). Weitere Informationen finden Sie unter [Konfigurieren von Junk-E-Mail-Einstellungen für Exchange Online-Postfächer in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Quarantänenachricht:** ZAP isoliert die Nachricht.

Standardmäßig ist phish ZAP in Antispamrichtlinien aktiviert, und  die Standardaktion für das Phishing-E-Mail-Filter-Urteil ist **Quarantänenachricht,** was bedeutet, dass die Nachricht standardmäßig von phish ZAP isoliert wird.

Weitere Informationen zum Konfigurieren von Spamfilterungsverkündungen finden Sie unter [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).

### <a name="spam-zap"></a>Spam-ZAP

Bei **ungelesenen** Nachrichten, die nach der Zustellung als Spam identifiziert werden,  hängt das Ergebnis des Zap von der Aktion ab, die für das Spamfilter-Urteil in der entsprechenden Antispamrichtlinie konfiguriert ist. Die verfügbaren Filterungsaktionen für Spam und deren mögliche ZAP-Ergebnisse werden in der folgenden Liste beschrieben:

- X-Header hinzufügen, **Betreffzeile** vorab mit Text, **Nachricht** an **E-Mail-Adresse** umleiten, Nachricht löschen : ZAP ergreift keine Aktion für die Nachricht.

- **Nachricht in Junk-E-Mail** verschieben: ZAP verschiebt die Nachricht in den Junk-E-Mail-Ordner, solange die Junk-E-Mail-Regel für das Postfach aktiviert ist (sie ist standardmäßig aktiviert). Weitere Informationen finden Sie unter [Konfigurieren von Junk-E-Mail-Einstellungen für Exchange Online-Postfächer in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Quarantänenachricht:** ZAP isoliert die Nachricht. Endbenutzer können ihre eigenen Nachrichten mit Spamquarantäne anzeigen und verwalten.

Standardmäßig ist die Spam-ZAP in Antispamrichtlinien aktiviert,  und die Standardaktion für das Spamfilter-Urteil  ist **Verschieben** von Nachrichten in den Junk-E-Mail-Ordner, was bedeutet, dass die Spam-ZAP ungelesene Nachrichten standardmäßig in den Junk-E-Mail-Ordner verschiebt.

Weitere Informationen zum Konfigurieren von Spamfilterungsverkündungen finden Sie unter [Configure anti-spam policies in Microsoft 365](configure-your-spam-filter-policies.md).

### <a name="zap-considerations-for-microsoft-defender-for-office-365"></a>Überlegungen zu ZAP für Microsoft Defender für Office 365

Zap isoliert keine Nachrichten, die sich im Prozess der Überprüfung der dynamischen Übermittlung [in](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) sicheren Anlagen oder in der EOP-Schadsoftwarefilterung die Anlage bereits durch die Datei **"Malware Alert Text.txt" ersetzt** hat. Wenn für diese Arten von Nachrichten ein Phishing- oder Spamsignal empfangen wird und das Filterverknappungs-Urteil in der Antispamrichtlinie so festgelegt ist, dass eine Aktion für die Nachricht (Zu Junk, Umleitung, Löschen oder Quarantäne verschoben wird) zu ergreifen ist, wird für ZAP standardmäßig die Aktion "Zu Junk verschieben" verwendet.

## <a name="how-to-see-if-zap-moved-your-message"></a>So sehen Sie, ob ZAP Ihre Nachricht verschoben hat

Um festzustellen, ob zap Ihre Nachricht verschoben hat, können Sie entweder den [Threat Protection Status-Bericht](view-email-security-reports.md#threat-protection-status-report) oder den [Threat Explorer (und Echtzeiterkennungen) verwenden.](threat-explorer.md) Beachten Sie, dass ZAP als Systemaktion nicht in den Exchange-Postfach-Überwachungsprotokollen protokolliert wird.

## <a name="zap-faq"></a>HÄUFIG gestellte Fragen zu ZAP

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>Was geschieht, wenn eine legitime Nachricht in den Junk-E-Mail-Ordner verschoben wird?

Sie sollten den normalen Berichterstellungsprozess für falsch [positive Ergebnisse befolgen.](report-junk-email-messages-to-microsoft.md) Der einzige Grund, warum die Nachricht aus dem Posteingang in den Junk-E-Mail-Ordner verschoben würde, liegt daran, dass der Dienst festgestellt hat, dass die Nachricht Spam oder schadhaft war.

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>Was passiert, wenn ich den Ordner Quarantäne anstelle des Junk-E-Mail-Ordners verwende?

ZAP wird auf der Grundlage der Konfiguration Ihrer Antispamrichtlinien, wie weiter oben in diesem Artikel beschrieben, Maßnahmen für eine Nachricht ergreifen.

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>Was passiert, wenn ich sichere Absender, Nachrichtenflussregeln oder zugelassene/blockierte Absenderlisten verwendet?

Sichere Absender, Nachrichtenflussregeln oder Blockieren und Zulassen von Organisationseinstellungen haben Vorrang. Diese Nachrichten werden von ZAP ausgeschlossen, da der Dienst die von Ihnen konfigurierten Maßnahmen vorn hat. Dies ist ein weiterer Grund, um beim Konfigurieren von Nachrichten zur Umgehung der Filterung vorsichtig zu sein.

### <a name="what-are-the-licensing-requirements-for-zap-to-work"></a>Welche Lizenzierungsanforderungen gelten für ZAP?

Es gibt keine Einschränkungen für Lizenzen. ZAP funktioniert auf allen Postfächern, die auf Exchange online gehostet werden. ZAP funktioniert nicht in eigenständigen Exchange Online Protection (EOP)-Umgebungen, die lokale Exchange-Postfächer schützen.

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>Was passiert, wenn eine Nachricht in einen anderen Ordner verschoben wird (z. B. Posteingangsregeln)?

ZAP funktioniert weiterhin, solange die Nachricht nicht gelöscht wurde oder solange die gleiche oder stärkere Aktion noch nicht angewendet wurde. Wenn die Antiphishingrichtlinie beispielsweise auf Quarantäne festgelegt ist und sich die Nachricht bereits in der Junk-E-Mail befindet, wird ZAP Maßnahmen ergreifen, um die Nachricht zu isolieren.

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>Wie wirkt sich ZAP auf postfächer im Halteraum aus?

Zap isoliert Nachrichten nicht aus Postfächern, die sich im Haltebereich halten. ZAP kann Nachrichten basierend auf der Aktion, die für ein Spam- oder Phishing-Urteil in Antispamrichtlinien konfiguriert ist, in den Junk-E-Mail-Ordner verschieben.

Weitere Informationen zu Halterechten in Exchange Online finden Sie unter [In-Place Hold and Litigation Hold in Exchange Online](/Exchange/security-and-compliance/in-place-and-litigation-holds).