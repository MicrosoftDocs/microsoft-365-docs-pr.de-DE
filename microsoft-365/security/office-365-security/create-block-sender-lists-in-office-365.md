---
title: Erstellen von Block Absenderlisten in Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/6/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
description: Die Optionen zum Blockieren von Absenderlisten umfassen Outlook blockierte Absender, Antispam-Sender/Domänen Sperrlisten, IP-Sperrlisten und Exchange-Transport Regeln (ETRs), die auch als Nachrichtenfluss Regeln bezeichnet werden.
ms.openlocfilehash: 27e0a1881c50031f180192b6bc02f3d606e7b76c
ms.sourcegitcommit: 3eae8fe39cea912d29e211a1c9fd035d6b606f91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "38793709"
---
# <a name="create-block-sender-lists-in-office-365"></a>Erstellen von Block Absenderlisten in Office 365

Manchmal ist es erforderlich, unerwünschte e-Mails von Absendern zu blockieren. Es stehen verschiedene Methoden zur Auswahl. Zu diesen Optionen gehören blockierte Absender in Outlook, Spam Schutz-und Domänen Sperrlisten, IP-Sperrlisten und Exchange-Transport Regeln (ETRs, die auch als Nachrichtenfluss Regeln bezeichnet werden).

> [!NOTE]
> Während Organisations Sperrlisten zum Adressieren von falsch negativen (verpassten Spam) verwendet werden können, sollten diese Kandidaten ebenfalls zur Analyse an Microsoft übermittelt werden. Durch das Verwalten von falsch negativen mithilfe von Sperrlisten wird der Verwaltungsaufwand erheblich gesteigert. Wenn Sie für diesen Zweck eine Sperrliste verwenden, müssen Sie den Artikel auch für die [Übermittlung von Spam-, nicht-Spam-und Phishing-Nachrichten an Microsoft zur Analyse](https://docs.microsoft.com/office365/SecurityCompliance/submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis)in Vorbereitung halten.

Die ordnungsgemäße Methode zum Konfigurieren blockierter Absenderlisten variiert je nach Wirkungsbereich. Für einzelne Benutzer wirkt sich die richtige Lösung möglicherweise auf die Verwendung von Outlook-blockierten Absendern aus, aber wenn mehrere Benutzer oder alle Benutzer betroffen sind, ist eine der anderen Optionen besser geeignet.

## <a name="options-from-least-to-broadest-scope"></a>Optionen vom kleinsten zum breitesten Bereich

Beim Erstellen einer Sperrliste ist es wichtig, die geeignete Methode basierend auf dem Wirkungsbereich auszuwählen (wie viele Personen werden betroffen sein), sodass Sie mit der Breite der Blockierungs Methode übereinstimmt. Die unten aufgeführten Optionen werden nach Umfang und Breite bewertet. Die Liste wird von schmal zu breit, aber *Lesen Sie die Details* für vollständige Empfehlungen.

- Blockierte Absender in Outlook
- Anti-Spam-Richtlinie: Absender/Domänen-Sperrlisten
- Exchange-Transport Regeln (ETRs auch als Nachrichtenfluss Regeln bezeichnet)
- Anti-Spam-Richtlinie: IP-Sperrlisten

## <a name="use-outlook-blocked-senders"></a>Verwenden von Outlook-blockierten Absendern

Wenn nur eine kleine Anzahl von Benutzern betroffen ist, sollte dies der Fall sein, wenn Outlook blockierte Absender verwendet werden sollen, da dies nur Auswirkungen auf e-Mails hat, die an Sie gesendet werden.

> [!IMPORTANT]
> Wenn es sich bei den unerwünschten Nachrichten um Newsletter von einer seriösen und erkennbaren Quelle handelt, ist das kündigen der e-Mail eine weitere Option, um zu verhindern, dass der Benutzer die e-Mails zukünftig erhält.

Die Schritte zum Einrichten dieser Einstellung unterscheiden sich zwischen [Outlook Web App](https://support.office.com/article/block-or-allow-junk-email-settings-48c9f6f7-2309-4f95-9a4d-de987e880e46) und dem [Outlook-Client](https://support.office.com/article/overview-of-the-junk-email-filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). **Wenn Nachrichten aufgrund blockierter Absender erfolgreich blockiert werden, sehen Sie SFV: BLK im X-Forefront-Antispam-Report** , der angibt, dass die Nachricht blockiert wird.

## <a name="use-anti-spam-policy-senderdomain-block-lists"></a>Verwenden von Absender-/Domänen Sperrlisten für Anti-Spam-Richtlinien

Wenn mehrere Benutzer betroffen sind, ist der Bereich breiter und Sie müssen eine unternehmensweite Anti-Spam-Richtlinie für Absender-/Domänen Sperrlisten verwenden. Die detaillierten Schritte finden [Sie unter Configure your Spamfilter Policies](https://docs.microsoft.com/office365/securitycompliance/configure-your-spam-filter-policies) Document. Alle Nachrichten, die mit dieser Methode blockiert werden, verfolgen die in der Richtlinie konfigurierte Spamaktion.

Die Höchstgrenze für diese Listen beträgt ungefähr 1000 Einträge; Sie können jedoch nur 30 Einträge in das Portal eingeben. Sie müssen PowerShell verwenden, um mehr als 30 Einträge hinzuzufügen.

## <a name="use-exchange-transport-rules-etrs-to-block-specific-senders"></a>Verwenden von Exchange-Transport Regeln (ETRs) zum Blockieren bestimmter Absender

Wenn das Senden von Nachrichten an bestimmte Benutzer oder die gesamte Organisation verhindert werden muss, kann ETRs (auch als Nachrichtenfluss Regeln bezeichnet) verwendet werden. ETRs sind flexibler, da Sie die Absender-e-Mail-Adresse oder-Domäne sowie Schlüsselwörter und andere Eigenschaften in der Nachricht auslösen können. Diese Flexibilität ermöglicht Ihnen das Erstellen von teilweise abgeschlossenen Blöcken. [Klicken Sie für die Schritte zum Erstellen einer ETR, die auch als Nachrichtenfluss Regeln bezeichnet](https://docs.microsoft.com/office365/SecurityCompliance/use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages)werden.

> [!IMPORTANT]
> Es ist ganz einfach, *übermäßig* aggressive Regeln zu erstellen, daher ist es wichtig, dass die verwendeten Kriterien so genau wie möglich sind. Stellen Sie außerdem sicher, dass Sie die Überwachung für die Regel aktivieren, die Sie erstellen, und testen Sie, um sicherzustellen, dass alles wie erwartet funktioniert.

## <a name="use-anti-spam-policy-ip-block-lists"></a>Verwenden von IP-Sperrlisten für Anti-Spam-Richtlinien

Wenn es nicht möglich ist, eine der anderen Optionen zum Blockieren eines Absenders zu verwenden, *kann die IP* -Sperrliste "Anti-Spam-Richtlinie" verwendet werden. [Ausführliche Schritte finden Sie im Artikel Konfigurieren der Verbindungsfilter Richtlinie](https://docs.microsoft.com/office365/securitycompliance/configure-the-connection-filter-policy). Es ist wichtig, dass die Liste der blockierten IPS auf ein *Minimum* festgehalten wird und dass die Verwendung von IP-Adressbereichen hier *nicht* empfohlen wird.

Sie sollten *insbesondere* verhindern, dass IP-Adressbereiche hinzugefügt werden, die zu Consumer Services oder gemeinsam genutzten Infrastrukturen gehören, und Sie sollten auch sicherstellen, dass Sie die Liste der zulässigen IP-Adressen im Rahmen der regulären Wartung überprüfen. **Da durch erlaubte Einträge Routen für Angriffe geöffnet werden können, müssen Sie diese Liste genau verwalten und die nicht mehr benötigten zulässigen Einträge regelmäßig entfernen.** Wenn Sie in einer Liste mit sicheren Absendern zulassen, müssen Sie auch die Risiken und Vorsichtsmaßnahmen in *[Erstellen von Listen sicherer Absender in Office 365](create-safe-sender-lists-in-office-365.md)* lesen und verstehen.
