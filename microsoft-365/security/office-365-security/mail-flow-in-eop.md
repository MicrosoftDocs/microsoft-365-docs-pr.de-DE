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
ms.openlocfilehash: 2ad80c4176c1b8b1c47b6b9ecafd34b4ca301f3f
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623417"
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

In Hybridumgebungen, in denen EOP lokale Exchange-Postfächer schützt, müssen Sie Nachrichtenflussregeln (auch als Transportregeln bezeichnet) in der lokalen Exchange konfigurieren, um das EOP-Spamfilter-Urteil zu übersetzen, damit die Junk-E-Mail-Regel die Nachricht in den Junk-E-Mail-Ordner verschieben kann. Weitere Informationen finden Sie unter [Configure EOP to deliver spam to the Junk Email folder in hybrid environments](/exchange/standalone-eop/configure-eop-spam-protection-hybrid). Wenn Sie Nachrichten nicht in den Junk-E-Mail-Ordner der einzelnen Benutzer verschieben möchten, können Sie eine andere Aktion auswählen, indem Sie Ihre Antispamrichtlinien bearbeiten (auch als Inhaltsfilterrichtlinien bekannt). Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md).

## <a name="verify-mail-flow"></a>Überprüfen des Nachrichtenflusses

Weitere Informationen zum Überprüfen des EOP-Setups und der Connectorkonfiguration finden Sie im Abschnitt "Woher wissen Sie, dass diese Aufgabe erfolgreich war?" unter [Einrichten Ihres EOP-Diensts](/exchange/standalone-eop/set-up-your-eop-service).

[Test mail flow by validating your Microsoft 365 connectors](/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.
