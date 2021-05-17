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
description: Der Administrator kann sich über die Optionen zum Konfigurieren des Nachrichtenflusses und des Routings in Exchange Online Protection (EOP) informieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7cd5bfcc95227c59f645422d4939ea6ff77bee1e
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206364"
---
# <a name="mail-flow-in-eop"></a>Nachrichtenfluss in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365 Organisationen mit Exchange Online Postfächern oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer werden alle Nachrichten, die an Ihre Organisation gesendet werden, über EOP übergeben, bevor die Mitarbeiter sie sehen. Sie haben Optionen zum Routen von Nachrichten, die EOP zur Verarbeitung übergeben, bevor sie an Ihre Arbeitsboxen geroutet werden.

## <a name="working-with-messages-and-message-access-options"></a>Arbeiten mit Nachrichten und Nachrichtenzugangsoptionen

EOP bietet Flexibilität bei der Routenführung Ihrer Nachrichten. In den folgenden Themen werden Schritte im Nachrichtenflussprozess erklärt.

[Verwenden der verzeichnisbasierten Edgeblockierung zum Ablehnen von Nachrichten, die an ungültige Empfänger gesendet werden](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Beschreibt das Verzeichnisbasierte Edgeblockierungsfeature, mit dem Sie Nachrichten für ungültige Empfänger im Umkreis des Dienstnetzwerks ablehnen können.

[View or Edit Managed Domains in EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) beschreibt die Verwaltung von Domänen, die mit Ihrem EOP-Dienst verbunden sind.

Wenn Sie Ihrer Organisation Unterdomänen hinzufügen, können Sie auch diese mit dem EOP-Dienst verwalten. Weitere Informationen zu Unterdomänen finden Sie unter Aktivieren des [Nachrichtenflusses](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)für Unterdomänen in Exchange Online .

[Das Konfigurieren des Nachrichtenflusses mithilfe von Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) führt Connectors ein und zeigt, wie Sie sie zum Anpassen des E-Mail-Routings verwenden können. Dazu gehören Szenarien zur Gewährleistung sicherer Kommunikation mit einer Partnerorganisation sowie das Einrichten eines Smarthosts.

[Erweiterte Filterung für Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) beschreibt, wie Sie Connectors konfigurieren, wenn Ihre E-Mails vor EOP an einen Dienst oder ein Gerät geroutet werden.

In eigenständigen EOP-Organisationen müssen Sie einige Konfigurationsschritte ausführen, um sicherzustellen, dass Junk-E-Mails ordnungsgemäß an den Junk-E-Mail-Ordner jedes Benutzers geroutet werden. Diese finden Sie unter Konfigurieren eigenständiger EOP zum Senden von Spam an den [Junk-E-Mail-Ordner in Hybridumgebungen.](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) Wenn Sie Nachrichten nicht in den Junk-E-Mail-Ordner jedes Benutzers verschieben möchten, können Sie eine andere Aktion auswählen, indem Sie Ihre Antispamrichtlinien bearbeiten (auch als Inhaltsfilterrichtlinien bekannt). Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md).

## <a name="verify-mail-flow"></a>Überprüfen des Nachrichtenflusses

Weitere Informationen zum Überprüfen des EOP-Setups und der Connectorkonfiguration finden Sie im Abschnitt "Woher wissen Sie, dass diese Aufgabe erfolgreich war?" unter [Einrichten Ihres EOP-Diensts](set-up-your-eop-service.md).

[Test mail flow by validating your Microsoft 365 connectors](/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.