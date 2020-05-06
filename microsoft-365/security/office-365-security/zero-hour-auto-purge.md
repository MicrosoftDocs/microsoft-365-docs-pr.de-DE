---
title: Zero-Hour Auto Purge (zap) – e-Mail-Schutzfunktion
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
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
description: Erfahren Sie mehr über Zero-Hour Auto Purge (zap), eine e-Mail-Schutzfunktion in Microsoft 365, die Spam, Schadsoftware oder Phishing-Nachrichten erkennt, die bereits an Exchange Online übermittelt wurden.
ms.openlocfilehash: a6f21147e7beaadb3aa6430b299dea8b248561c1
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034926"
---
# <a name="zero-hour-auto-purge-zap---protection-against-spam-and-malware-in-microsoft-365"></a>Zero-Hour Auto Purge (zap) – Schutz vor Spam und Schadsoftware in Microsoft 365

## <a name="overview"></a>Übersicht

Zero-Hour Auto Purge (zap) ist eine e-Mail-Schutzfunktion in Microsoft 365, die schädliche Phishing-, Spam-oder Schadsoftware-Nachrichten, die bereits an Exchange Online Postfächer gesendet wurden, rückwirkend erkennt und neutralisiert.

ZAP ist mit dem standardmäßigen Exchange Online Schutz (EoP) verfügbar, der in einem Microsoft 365-Abonnement enthalten ist, das Exchange Online Postfächer enthält. Zap funktioniert nicht in eigenständigen EoP-Umgebungen, die lokale Exchange-Postfächer schützen.

## <a name="how-zap-works"></a>Funktionsweise von zap

Microsoft 365 aktualisiert täglich Spam-und Malware Signaturen in Echtzeit. Allerdings können Benutzer nach wie vor Schadsoftware aus einer Vielzahl von Gründen erhalten, einschließlich, wenn der Inhalt nach der Zustellung an die Benutzer Waffen basiert. Zap behebt dieses Problem, indem Updates für die Microsoft 365-Spam-und-Malware-Signaturen kontinuierlich überwacht werden. Zap kann Nachrichten suchen und entfernen, die sich bereits im Postfach eines Benutzers befinden.

Die ZAP-Aktion ist für den Benutzer nahtlos; Sie werden nicht benachrichtigt, wenn eine Nachricht erkannt und verschoben wird.

[Listen sicherer Absender](create-safe-sender-lists-in-office-365.md), Nachrichtenfluss Regeln (auch bekannt als Transportregeln), Posteingangsregeln oder zusätzliche Filter haben Vorrang vor zap.

### <a name="malware-zap"></a>Malware zap

Bei **Lese-oder ungelesenen Nachrichten** , die nach der Zustellung Schadsoftware enthalten, wird die Nachricht, die die Schadsoftware enthält, in zap unter Quarantäne gestellt. Nur Administratoren können Schadsoftware-Nachrichten aus der Quarantäne anzeigen und verwalten.

Malware zap ist in Anti-Malware-Richtlinien standardmäßig aktiviert. Weitere Informationen finden Sie unter [configure Anti-Malware Policies in Microsoft 365](configure-anti-malware-policies.md).

### <a name="phish-zap"></a>Phishing-zap

Für **Lese-oder ungelesene Nachrichten** , die nach der Zustellung als Phishing identifiziert werden, hängt das zap-Ergebnis von der Aktion ab, die für ein **Phishing-e-Mail-** Filter Urteil in der entsprechenden Antispampolitik konfiguriert ist. Die verfügbaren Filter Urteils Aktionen für Phishing und ihre möglichen zap-Ergebnisse werden in der folgenden Liste beschrieben:

- **X-Header hinzufügen**, **Betreffzeile mit Text**voranstellen: Zap nimmt keine Aktion für die Nachricht vor.

- **Nachricht in Junk-e-Mail verschieben**: Zap verschiebt die Nachricht in den Junk-e-Mail-Ordner, solange die Junk-e-Mail-Regel für das Postfach aktiviert ist (Sie ist standardmäßig aktiviert). Weitere Informationen finden Sie unter [Konfigurieren von Junk-e-Mail-Einstellungen für Exchange Online-Postfächer in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Nachricht an e-Mail-Adresse umleiten**, **Nachricht löschen**, **Nachricht isolieren**: Zap isoliert die Nachricht. Nur Administratoren können Phishing-unter Quarantäne gestellte Nachrichten anzeigen und verwalten.

Standardmäßig ist Phishing zap in Anti-Spam-Richtlinien aktiviert, und die Standardaktion für das **Phishing-e-Mail-** Filter Urteil lautet **Quarantäne Nachricht**, was bedeutet, dass die Nachricht von Phishing zap standardmäßig isoliert wird.

Weitere Informationen zum Konfigurieren von Spamfilter Urteilen finden Sie unter [configure Anti-Spam Policies in Microsoft 365](configure-your-spam-filter-policies.md).

### <a name="spam-zap"></a>Spam zap

Für **Ungelesene Nachrichten** , die nach der Zustellung als Spam identifiziert werden, hängt das zap-Ergebnis von der Aktion ab, die für das **Spam** Filter Urteil in der entsprechenden Antispampolitik konfiguriert ist. Die verfügbaren Filter Urteils Aktionen für Spam und ihre möglichen zap-Ergebnisse werden in der folgenden Liste beschrieben:

- **X-Header hinzufügen**, **Betreffzeile mit Text**voranstellen: Zap nimmt keine Aktion für die Nachricht vor.

- **Nachricht in Junk-e-Mail verschieben**: Zap verschiebt die Nachricht in den Junk-e-Mail-Ordner, solange die Junk-e-Mail-Regel für das Postfach aktiviert ist (Sie ist standardmäßig aktiviert). Weitere Informationen finden Sie unter [Konfigurieren von Junk-e-Mail-Einstellungen für Exchange Online-Postfächer in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Nachricht an e-Mail-Adresse umleiten**, **Nachricht löschen**, **Nachricht isolieren**: Zap isoliert die Nachricht. Endbenutzer können Ihre eigenen Spam isolierten Nachrichten anzeigen und verwalten.

Standardmäßig ist Spam zap in Anti-Spam-Richtlinien aktiviert, und die Standardaktion für das **Spam** Filterungs Urteil wird Nachrichten in den **Junk-e-Mail-Ordner verschoben**, was bedeutet, dass Spam zap standardmäßig **Ungelesene** Nachrichten in den Junk-e-Mail-Ordner verschiebt.

Weitere Informationen zum Konfigurieren von Spamfilter Urteilen finden Sie unter [configure Anti-Spam Policies in Microsoft 365](configure-your-spam-filter-policies.md).

### <a name="zap-considerations-for-office-365-advanced-threat-protection-atp"></a>Zap-Überlegungen für Office 365 Advanced Threat Protection (ATP)

Zap unter Quarantäne keine Nachrichten, die sich im Prozess der Überprüfung der [dynamischen Zustellung](dynamic-delivery-and-previewing.md) befinden, oder bei denen die Malware Filterung die Anlage bereits durch die Datei " **Malware Alert Text. txt** " ersetzt hat. Wenn ein Phishing-oder Spam Signal für diese Arten von Nachrichten empfangen wird und das Filter Urteil in der Antispampolitik so eingestellt ist, dass eine Aktion in der Nachricht ausgeführt wird (in Junk-e-Mails verschieben, umleiten, löschen, isolieren), wird zap standardmäßig auf die Aktion "in Junk-e-Mail verschieben" angewendet.

## <a name="how-to-see-if-zap-moved-your-message"></a>Wie Sie sehen, ob zap Ihre Nachricht verschoben hat

Um festzustellen, ob zap Ihre Nachricht verschoben hat, können Sie entweder den [Threat Protection-Status Bericht](view-email-security-reports.md#threat-protection-status-report) oder den [Threat-Explorer (und Echt Zeit Erkennungen)](threat-explorer.md)verwenden. Beachten Sie, dass zap als Systemaktion nicht in den Exchange-postfachüberwachungsprotokollen protokolliert wird.

## <a name="zap-faq"></a>Zap-FAQ

### <a name="q-what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>F.: Was passiert, wenn eine legitime Nachricht in den Junk-e-Mail-Ordner verschoben wird?

A.: Sie sollten den normalen Berichterstellungsprozess für [falsch positive Ergebnisse](report-junk-email-messages-to-microsoft.md)ausführen. Der einzige Grund, warum die Nachricht aus dem Posteingang in den Junk-e-Mail-Ordner verschoben würde, liegt daran, dass der Dienst festgestellt hat, dass die Nachricht Spam oder bösartig ist.

### <a name="q-what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>F.: Was ist, wenn ich den Ordner "Quarantine" anstelle des Junk-e-Mail-Ordners verwende?

A.: Zap wird eine Aktion für eine Nachricht basierend auf der Konfiguration Ihrer Antispam-Richtlinien wie weiter oben in diesem Thema beschrieben durchführen.

### <a name="q-what-if-im-using-mail-flow-rules-or-allowedblocked-sender-lists"></a>F.: Was geschieht, wenn e-Mail-Flussregeln oder zugelassene/blockierte Absenderlisten verwendet werden?

A: Nachrichtenfluss Regeln oder blockieren und Organisationseinstellungen zulassen haben Vorrang. Diese Nachrichten werden von zap ausgeschlossen.

### <a name="q-what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>F.: Was geschieht, wenn eine Nachricht in einen anderen Ordner verschoben wird (z.b. Posteingangsregeln)?

A: Zap funktioniert weiterhin, solange die Nachricht nicht gelöscht wurde oder solange die gleiche oder stärkere Aktion noch nicht angewendet wurde. Wenn beispielsweise die Phishing-Richtlinie auf "Quarantine" festgelegt ist und der Benutzer oder Administrator die e-Mail bereits junked hat, wird in der Quarantäne die Aktion zum Isolieren der Datei durchführen.

### <a name="q-does-zap-change-the-message-header"></a>F.: ändert zap die Nachrichtenkopfzeile?

A: bei einer ZAP-Aktion werden keine Änderungen am Nachrichtenkopf vorgenommen.

### <a name="q-how-does-zap-affect-mailboxes-on-hold"></a>F.: wie wirkt sich Zap auf Postfächer in der Warteschleife aus?

A: Zap kann keine Nachrichten von Postfächern in der Warteschleife isolieren. Zap kann Nachrichten in den Junk-e-Mail-Ordner basierend auf der Aktion, die für ein Spam-oder Phishing-Urteil in Anti-Spam-Richtlinien konfiguriert ist.

Weitere Informationen zu Haltebereichen in Exchange Online finden Sie unter [in-situ-Speicher und Beweissicherungsverfahren in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).
