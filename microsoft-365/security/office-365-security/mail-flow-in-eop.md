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
description: In diesem Artikel können Kunden Exchange Online Protection (EoP) erfahren, wie Sie benutzerdefiniertes e-Mail-Routing konfigurieren können, das Ihren geschäftlichen Anforderungen entspricht.
ms.openlocfilehash: cdc919c628f2254ffc971678f7887c37786d2528
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034232"
---
# <a name="mail-flow-in-eop"></a>Nachrichtenfluss in EOP

Als ein Exchange Online Protection (EOP) Kunde werden alle Nachrichten, die an Ihre Organisation gesendet werden, durch EOP geleitet, bevor die Mitarbeiter sie sehen. Ob Sie alle Ihre Postfächer in der Cloud mit Exchange Online hosten oder ob Sie Ihre Postfächer vor Ort hosten (genannt eigenständiges Szenario), haben Sie Optionen für die Art der Weiterleitung von Nachrichten, die zur Bearbeitung EOP durchlaufen, bevor sie an die Postfächer Ihrer Mitarbeiter weitergeleitet werden, um weiterhin die Vorteile Ihrer bestehenden Infrastruktur nutzen zu können.

Sie können eine benutzerdefinierte Mail-Weiterleitung konfigurieren, um Ihr Massaging an Ihre Unternehmensanforderung anzupassen. Angenommen, Sie möchten alle ausgehenden Nachrichten durch eine Richtlinienprüfungsvorrichtung leiten.

## <a name="working-with-messages-and-message-access-options"></a>Arbeiten mit Nachrichten und Nachrichtenzugangsoptionen

EOP bietet viel Flexibilität bezüglich der Weiterleitung Ihrer Nachrichten. In den folgenden Themen werden Schritte im Nachrichtenflussprozess erklärt.

[Verwenden der verzeichnisbasierten Edge-Blockierung zum ablehnen von Nachrichten, die an ungültige Empfänger gesendet wurden](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Beschreibt das Feature für die verzeichnisbasierte Edge-Blockierung, mit dem Sie Nachrichten für ungültige Empfänger im Dienst Netzwerkumkreis ablehnen können.

[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) beschreibt die Verwaltung von Domänen, die mit Ihrem EOP-Dienst verbunden sind.

Wenn Sie Ihrer Organisation Unterdomänen hinzufügen, können Sie auch diese mit dem EOP-Dienst verwalten. Weitere Informationen zu Unterdomänen finden Sie unter [Aktivieren des Nachrichtenflusses für Unterdomänen in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).

Unter [Configure mail flow using connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) erhalten Sie eine Einführung in Connectors und erfahren, wie diese zum Anpassen von E-Mail-Routing verwendet werden können. Dazu gehören Szenarien zur Gewährleistung sicherer Kommunikation mit einer Partnerorganisation sowie das Einrichten eines Smarthosts.

Sie müssen eine Reihe von Konfigurationsschritten ausführen, um wirklich sicherzustellen, dass Junk-E-Mail in die Junk-E-Mail-Ordner der Benutzer umgeleitet werden. Diese werden in [Konfigurieren von eigenständigen EoP zur Zustellung von Spam an den Junk-e-Mail-Ordner in Hybrid Umgebungen](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)detailliert beschrieben. Wenn die Nachrichten nicht in die Junk-E-Mail-Ordner der Benutzer verschoben werden sollen, können Sie eine andere Aktion auswählen, indem Sie die standardmäßige Inhaltsfilterrichtlinie im Exchange Admin Center bearbeiten. Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md).

## <a name="verify-mail-flow"></a>Überprüfen des Nachrichtenflusses

Weitere Informationen zum Überprüfen des EOP-Setups und der Connectorkonfiguration finden Sie im Abschnitt "Woher wissen Sie, dass diese Aufgabe erfolgreich war?" unter [Einrichten Ihres EOP-Diensts](set-up-your-eop-service.md).

[Testen des Nachrichtenflusses durch Validieren der Microsoft 365-Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) enthält Anweisungen zum Testen, ob der Nachrichtenfluss ordnungsgemäß eingerichtet ist.
