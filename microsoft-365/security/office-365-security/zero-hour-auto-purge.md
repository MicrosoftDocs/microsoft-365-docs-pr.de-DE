---
title: Automatische Bereinigung ohne Stunden (zap)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
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
description: Administratoren können sich darüber informieren, wie die automatische Bereinigung durch Null Stunden rückwirkend zugestellte Nachrichten in einem Exchange Online Postfach in den Junk-e-Mail-Ordner oder in die Quarantäne verschieben kann, die rückwirkend als Spam oder Phishing eingestuft wurden.
ms.openlocfilehash: 31e546ddf6e93ed0a265aef3737182cf30ae5a95
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327975"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>Automatische Bereinigung ohne Stunden in Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-zap"></a>Grundlegende Funktionen von zap

In Microsoft 365-Organisationen mit Postfächern in Exchange Online ist Zero-Hour Auto Purge (zap) eine e-Mail-Schutzfunktion, die bösartige Phishing-, Spam-oder Schadsoftware-Nachrichten, die bereits an Exchange Online Postfächer gesendet wurden, rückwirkend erkennt und neutralisiert.

Zap funktioniert nicht in eigenständigen Exchange Online Schutz Umgebungen (EoP), die lokale Exchange-Postfächer schützen.

## <a name="how-zap-works"></a>Funktionsweise von zap

Spam-und Malware Signaturen werden täglich im Dienst Real-Time aktualisiert. Allerdings können Benutzer nach wie vor Schadsoftware aus einer Vielzahl von Gründen erhalten, einschließlich, wenn der Inhalt nach der Zustellung an die Benutzer Waffen basiert. Zap behebt dieses Problem durch kontinuierliche Überwachung von Aktualisierungen der Spam-und Malware Signaturen im Dienst. Zap kann Nachrichten suchen und entfernen, die sich bereits im Postfach eines Benutzers befinden.

Die ZAP-Aktion ist für den Benutzer nahtlos; Sie werden nicht benachrichtigt, wenn eine Nachricht erkannt und verschoben wird.

[Listen sicherer Absender](create-safe-sender-lists-in-office-365.md), Nachrichtenfluss Regeln (auch bekannt als Transportregeln), Posteingangsregeln oder zusätzliche Filter haben Vorrang vor zap. Ähnlich dem, was im Nachrichtenfluss geschieht, bedeutet dies, dass selbst dann, wenn der Dienst feststellt, dass die zugestellte Nachricht zap benötigt, die Nachricht aufgrund der Konfiguration sicherer Absender nicht verarbeitet wird. Dies ist ein weiterer Grund, um mit der Konfiguration von Nachrichten für die Umgehung der Filterung vorsichtig zu sein.

### <a name="malware-zap"></a>Malware zap

Bei **Lese-oder ungelesenen Nachrichten** , die nach der Zustellung Schadsoftware enthalten, wird die Nachricht, die die Schadsoftware enthält, in zap unter Quarantäne gestellt. Nur Administratoren können Schadsoftware-Nachrichten aus der Quarantäne anzeigen und verwalten.

Malware zap ist in Anti-Malware-Richtlinien standardmäßig aktiviert. Weitere Informationen finden Sie unter [configure Anti-Malware Policies in EoP](configure-anti-malware-policies.md).

### <a name="phish-zap"></a>Phishing-zap

Für **Lese-oder ungelesene Nachrichten** , die nach der Zustellung als Phishing identifiziert werden, hängt das zap-Ergebnis von der Aktion ab, die für ein **Phishing-e-Mail-** Filter Urteil in der entsprechenden Antispampolitik konfiguriert ist. Die verfügbaren Filter Urteils Aktionen für Phishing und ihre möglichen zap-Ergebnisse werden in der folgenden Liste beschrieben:

- **X-Header hinzufügen**, **Betreffzeile mit Text**voranstellen: Zap nimmt keine Aktion für die Nachricht vor.

- **Nachricht in Junk-e-Mail verschieben**: Zap verschiebt die Nachricht in den Junk-e-Mail-Ordner, solange die Junk-e-Mail-Regel für das Postfach aktiviert ist (Sie ist standardmäßig aktiviert). Weitere Informationen finden Sie unter [Konfigurieren von Junk-e-Mail-Einstellungen für Exchange Online-Postfächer in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Nachricht an e-Mail-Adresse umleiten**, **Nachricht löschen**, **Nachricht isolieren**: Zap isoliert die Nachricht.

Standardmäßig ist Phishing zap in Anti-Spam-Richtlinien aktiviert, und die Standardaktion für das **Phishing-e-Mail-** Filter Urteil lautet **Quarantäne Nachricht**, was bedeutet, dass die Nachricht von Phishing zap standardmäßig isoliert wird.

Weitere Informationen zum Konfigurieren von Spamfilter Urteilen finden Sie unter [configure Anti-Spam Policies in Microsoft 365](configure-your-spam-filter-policies.md).

### <a name="spam-zap"></a>Spam zap

Für **Ungelesene Nachrichten** , die nach der Zustellung als Spam identifiziert werden, hängt das zap-Ergebnis von der Aktion ab, die für das **Spam** Filter Urteil in der entsprechenden Antispampolitik konfiguriert ist. Die verfügbaren Filter Urteils Aktionen für Spam und ihre möglichen zap-Ergebnisse werden in der folgenden Liste beschrieben:

- **X-Header hinzufügen**, **Betreffzeile mit Text**voranstellen: Zap nimmt keine Aktion für die Nachricht vor.

- **Nachricht in Junk-e-Mail verschieben**: Zap verschiebt die Nachricht in den Junk-e-Mail-Ordner, solange die Junk-e-Mail-Regel für das Postfach aktiviert ist (Sie ist standardmäßig aktiviert). Weitere Informationen finden Sie unter [Konfigurieren von Junk-e-Mail-Einstellungen für Exchange Online-Postfächer in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Nachricht an e-Mail-Adresse umleiten**, **Nachricht löschen**, **Nachricht isolieren**: Zap isoliert die Nachricht. Endbenutzer können Ihre eigenen Spam isolierten Nachrichten anzeigen und verwalten.

Standardmäßig ist Spam zap in Anti-Spam-Richtlinien aktiviert, und die Standardaktion für das **Spam** Filterungs Urteil wird Nachrichten in den **Junk-e-Mail-Ordner verschoben**, was bedeutet, dass Spam zap standardmäßig **Ungelesene** Nachrichten in den Junk-e-Mail-Ordner verschiebt.

Weitere Informationen zum Konfigurieren von Spamfilter Urteilen finden Sie unter [configure Anti-Spam Policies in Microsoft 365](configure-your-spam-filter-policies.md).

### <a name="zap-considerations-for-office-365-advanced-threat-protection-office-365-atp"></a>Zap-Überlegungen für Office 365 Advanced Threat Protection (Office 365 ATP)

Zap unter Quarantäne keine Nachrichten, die sich im Prozess der [dynamischen Zustellung](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) befinden, beim Scannen sicherer Anlagen, oder wenn die EoP-Malware Filterung die Anlage bereits durch die **Malware Warnung #b0 ** Datei ersetzt hat. Wenn ein Phishing-oder Spam Signal für diese Arten von Nachrichten empfangen wird und das Filter Urteil in der Antispampolitik so eingestellt ist, dass eine Aktion in der Nachricht ausgeführt wird (in Junk-e-Mails verschieben, umleiten, löschen oder isolieren), wird zap standardmäßig eine Aktion "in Junk-e-Mail verschieben" durchführen.

## <a name="how-to-see-if-zap-moved-your-message"></a>Wie Sie sehen, ob zap Ihre Nachricht verschoben hat

Um festzustellen, ob zap Ihre Nachricht verschoben hat, können Sie entweder den [Threat Protection-Status Bericht](view-email-security-reports.md#threat-protection-status-report) oder den [Threat-Explorer (und Echt Zeit Erkennungen)](threat-explorer.md)verwenden. Beachten Sie, dass zap als Systemaktion nicht in den Exchange-postfachüberwachungsprotokollen protokolliert wird.

## <a name="zap-faq"></a>Zap-FAQ

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>Was passiert, wenn eine legitime Nachricht in den Junk-e-Mail-Ordner verschoben wird?

Sie sollten den normalen Berichterstellungsprozess für [falsch positive Ergebnisse](report-junk-email-messages-to-microsoft.md)ausführen. Der einzige Grund, warum die Nachricht aus dem Posteingang in den Junk-e-Mail-Ordner verschoben würde, liegt daran, dass der Dienst festgestellt hat, dass die Nachricht Spam oder bösartig ist.

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>Was geschieht, wenn ich den Ordner "Quarantine" anstelle des Junk-e-Mail-Ordners verwende?

Zap wird auf einer Nachricht basierend auf der Konfiguration Ihrer Antispam-Richtlinien, wie weiter oben in diesem Thema beschrieben, Aktionen durchführen.

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>Was geschieht, wenn ich sichere Absender, Nachrichtenfluss Regeln oder zugelassene/blockierte Senderlisten verwende?

Sichere Absender, Nachrichtenfluss Regeln oder blockieren und zulassen von Organisationseinstellungen haben Vorrang. Diese Nachrichten werden von zap ausgeschlossen, da der Dienst das ausführt, was Sie konfiguriert haben. Dies ist ein weiterer Grund, um mit der Konfiguration von Nachrichten für die Umgehung der Filterung vorsichtig zu sein.

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>Was geschieht, wenn eine Nachricht in einen anderen Ordner verschoben wird (z. b. Posteingangsregeln)?

Zap funktioniert weiterhin, solange die Nachricht nicht gelöscht wurde oder solange die gleiche oder stärkere Aktion noch nicht angewendet wurde. Wenn beispielsweise die Phishing-Richtlinie auf "Quarantine" festgelegt ist und der Benutzer oder Administrator die e-Mail bereits junked hat, wird in der Quarantäne die Aktion zum Isolieren der Datei durchführen.

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>Wie wirkt sich Zap auf Postfächer in der Warteschleife aus?

Zap wird keine Nachrichten von Postfächern in der Warteschleife isolieren. Zap kann Nachrichten in den Junk-e-Mail-Ordner basierend auf der Aktion, die für ein Spam-oder Phishing-Urteil in Anti-Spam-Richtlinien konfiguriert ist.

Weitere Informationen zu Haltebereichen in Exchange Online finden Sie unter [in-situ-Speicher und Beweissicherungsverfahren in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).
