---
title: Nachrichtenfluss in EOP
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
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: Der Administrator kann Informationen zu den Optionen zum Konfigurieren von Nachrichtenfluss und Routing in Exchange Online Protection (EoP) erhalten.
ms.openlocfilehash: cb2ae7370d50fe32802ad5c279cc2170eb35f581
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208330"
---
# <a name="mail-flow-in-eop"></a>Nachrichtenfluss in EOP

In Microsoft 365-Organisationen mit Exchange Online Postfächern oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer werden alle an Ihre Organisation gesendeten Nachrichten über EoP geleitet, bevor Ihre Mitarbeiter Sie sehen. Sie haben Optionen zum Weiterleiten von Nachrichten, die EoP zur Verarbeitung übergeben, bevor Sie an die Postfächer der Arbeitskraft weitergeleitet werden.

## <a name="working-with-messages-and-message-access-options"></a>Arbeiten mit Nachrichten und Nachrichtenzugangsoptionen

EoP bietet Flexibilität bei der Weiterleitung Ihrer Nachrichten. In den folgenden Themen werden Schritte im Nachrichtenflussprozess erklärt.

[Verwenden der verzeichnisbasierten Edge-Blockierung zum ablehnen von Nachrichten, die an ungültige Empfänger gesendet wurden](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Beschreibt das Feature für die verzeichnisbasierte Edge-Blockierung, mit dem Sie Nachrichten für ungültige Empfänger im Dienst Netzwerkumkreis ablehnen können.

[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) beschreibt die Verwaltung von Domänen, die mit Ihrem EOP-Dienst verbunden sind.

Wenn Sie Ihrer Organisation Unterdomänen hinzufügen, können Sie auch diese mit dem EOP-Dienst verwalten. Weitere Informationen zu Unterdomänen finden Sie unter [Aktivieren des Nachrichtenflusses für Unterdomänen in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).

[Konfigurieren des Nachrichtenflusses mit Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) stellt Connectors vor und zeigt, wie Sie das e-Mail-Routing anpassen können. Dazu gehören Szenarien zur Gewährleistung sicherer Kommunikation mit einer Partnerorganisation sowie das Einrichten eines Smarthosts.

[Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) beschreibt, wie Connectors konfiguriert werden, wenn Ihre e-Mails vor EoP an einen Dienst oder ein Gerät weitergeleitet werden.

In eigenständigen EoP-Organisationen müssen Sie eine Reihe von Konfigurationsschritten ausführen, um sicherzustellen, dass Junk-e-Mails ordnungsgemäß an den Junk-e-Mail-Ordner jedes Benutzers weitergeleitet werden. Diese werden in [Konfigurieren von eigenständigen EoP zur Zustellung von Spam an den Junk-e-Mail-Ordner in Hybrid Umgebungen](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)detailliert beschrieben. Wenn Sie keine Nachrichten in den Junk-e-Mail-Ordner der einzelnen Benutzer übertragen möchten, können Sie eine andere Aktion auswählen, indem Sie Ihre Anti-Spam-Richtlinien (auch bekannt als Inhaltsfilter-Richtlinien) bearbeiten. Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md).

## <a name="verify-mail-flow"></a>Überprüfen des Nachrichtenflusses

Weitere Informationen zum Überprüfen des EOP-Setups und der Connectorkonfiguration finden Sie im Abschnitt "Woher wissen Sie, dass diese Aufgabe erfolgreich war?" unter [Einrichten Ihres EOP-Diensts](set-up-your-eop-service.md).

[Testen des Nachrichtenflusses durch Validieren der Microsoft 365-Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) enthält Anweisungen zum Testen, ob der Nachrichtenfluss ordnungsgemäß eingerichtet ist.
