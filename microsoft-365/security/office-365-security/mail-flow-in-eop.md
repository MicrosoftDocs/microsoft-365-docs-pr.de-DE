---
title: Nachrichtenfluss in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: Der Administrator kann sich über die Optionen zum Konfigurieren des Nachrichtenflusses und Routings in Exchange Online Protection (EOP) informieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9636025796aee1ba2027edff38a16f131974134f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842494"
---
# <a name="mail-flow-in-eop"></a>Nachrichtenfluss in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365 Organisationen mit Exchange Online Postfächern oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online Postfächer werden alle nachrichten, die an Ihre Organisation gesendet werden, EOP durchlaufen, bevor ihre Mitarbeiter sie sehen. Sie haben Optionen zum Weiterleiten von Nachrichten, die EOP zur Verarbeitung durchlaufen, bevor sie an die Postfächer Ihrer Mitarbeiter weitergeleitet werden.

## <a name="working-with-messages-and-message-access-options"></a>Arbeiten mit Nachrichten und Nachrichtenzugangsoptionen

EOP bietet Flexibilität bei der Weiterleitung Ihrer Nachrichten. In den folgenden Themen werden Schritte im Nachrichtenflussprozess erklärt.

[Verwenden der verzeichnisbasierten Edgeblockierung zum Ablehnen von Nachrichten, die an ungültige Empfänger gesendet werden](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Beschreibt das Feature zum blockieren von verzeichnisbasierten Edges, mit dem Sie Nachrichten für ungültige Empfänger am Dienstnetzwerkperimeter ablehnen können.

[Das Anzeigen oder Bearbeiten akzeptierter Domänen in EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) beschreibt, wie Domänen verwaltet werden, die Ihrem EOP-Dienst zugeordnet sind.

Wenn Sie Ihrer Organisation Unterdomänen hinzufügen, können Sie auch diese mit dem EOP-Dienst verwalten. Weitere Informationen zu Unterdomänen finden Sie unter Aktivieren des [Nachrichtenflusses für Unterdomänen in Exchange Online.](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)

[Beim Konfigurieren des Nachrichtenflusses mithilfe von Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) werden Connectors eingeführt und gezeigt, wie Sie diese zum Anpassen des E-Mail-Routings verwenden können. Dazu gehören Szenarien zur Gewährleistung sicherer Kommunikation mit einer Partnerorganisation sowie das Einrichten eines Smarthosts.

[Die erweiterte Filterung für Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) beschreibt, wie Connectors konfiguriert werden, wenn Ihre E-Mails vor EOP an einen Dienst oder ein Gerät weitergeleitet werden.

In Hybridumgebungen, in denen EOP lokale Exchange-Postfächer schützt, müssen Sie im lokalen Exchange Nachrichtenflussregeln zur Übersetzung der EOP-Spamfilterbewertung konfigurieren (auch als Transportregeln bezeichnet), damit die Junk-E-Mail-Regel die Nachricht in den Junk-E-Mail-Ordner verschieben kann. Ausführliche Informationen finden Sie unter [Konfigurieren von EOP zum Verschieben von Spam in den Junk-E-Mail-Ordner in Hybridumgebungen](/exchange/standalone-eop/configure-eop-spam-protection-hybrid). Wenn Sie Nachrichten nicht in den Junk-E-Mail-Ordner jedes Benutzers verschieben möchten, können Sie eine andere Aktion auswählen, indem Sie Ihre Antispamrichtlinien bearbeiten (auch als Inhaltsfilterrichtlinien bezeichnet). Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md).

## <a name="verify-mail-flow"></a>Überprüfen des Nachrichtenflusses

Weitere Informationen zum Überprüfen des EOP-Setups und der Connectorkonfiguration finden Sie im Abschnitt "Woher wissen Sie, dass diese Aufgabe erfolgreich war?" unter [Einrichten Ihres EOP-Diensts](/exchange/standalone-eop/set-up-your-eop-service).

[Testen Sie den Nachrichtenfluss, indem Sie Ihre Microsoft 365 Connectors überprüfen,](/exchange/mail-flow-best-practices/test-mail-flow) finden Sie Anweisungen zum Testen, ob der Nachrichtenfluss ordnungsgemäß eingerichtet ist.
