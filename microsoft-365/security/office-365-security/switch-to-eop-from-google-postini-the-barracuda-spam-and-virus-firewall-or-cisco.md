---
title: Wechseln von einem anderen Schutzdienst zu EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 81b75194-3b04-48da-8b81-951afbabedde
ms.custom:
- seo-marvel-apr2020
description: In diesem Artikel erfahren Sie, wie Sie von einer lokalen E-Mail-Hygiene-Appliance oder einem cloudbasierten Schutzdienst zu Exchange Online Protection (EOP) wechseln.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dfbbc44ebfed6cafb97e36b18a4fc34c91840d9b
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624013"
---
# <a name="switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco-ironport"></a>Wechseln zu EOP von Google Postini, Barracuda Spam & Virus Firewall oder Cisco IronPort

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

 In diesem Thema wird der Wechsel von einer lokalen E-Mail-Schutzvorrichtung oder einem cloudbasierten Schutzdienst zu Exchange Online Protection (EOP) näher erläutert. Zur Erleichterung des Einstiegs werden hier außerdem einige Hilferessourcen genannt. Es gibt zahlreiche Lösungen zum Filtern von Spam, doch läuft der Wechsel zu EOP in den meisten Fällen ähnlich ab.

Wenn Sie neu in EOP sind und eine Übersicht über die Features lesen möchten, bevor Sie sich für einen Wechsel entscheiden, beginnen Sie mit dem Thema [Exchange Online Protection Übersicht.](exchange-online-protection-overview.md)

Bevor Sie zu EOP wechseln, sollten Sie zuerst überlegen, ob Sie die EOP-geschützten Postfächer in der Cloud, mit Exchange Online, lokal oder in einem hybriden Szenario hosten möchten. (Bei einem hybriden Szenario werden Postfächer teils lokal und teils mit Exchange Online gehostet.) Jedes dieser Hostingszenarios - cloudbasiert, lokal oder hybrid - ist möglich, wird jedoch u. U. unterschiedlich eingerichtet. Die folgenden Überlegungen sollen Ihnen bei der Wahl der richtigen Bereitstellung helfen:

- **EOP-Schutz** mit lokalen Postfächern: Dieses Szenario ist geeignet, wenn Sie über eine vorhandene E-Mail-Hosting-Infrastruktur verfügen, die Sie verwenden möchten, oder wenn Sie geschäftliche Anforderungen haben, um Postfächer lokal zu halten, und Sie EOP als cloudbasierten E-Mail-Schutz verwenden möchten. Eine genauere Beschreibung dieses Szenarios finden Sie unter [Wechseln zu EOP als eigenständige Lösung](#switch-to-eop-standalone).

- **EOP-Schutz mit Exchange Online:** Dieses Szenario ist geeignet, wenn Sie den EOP-Schutz und alle Postfächer in der Cloud hosten möchten. Dadurch verringert sich die Komplexität, da Sie keine lokalen Messagingserver unterhalten müssen. Dieses Szenario wird unter [Wechseln zu Exchange Online](#switch-to-exchange-online) beschrieben.

- **EOP-Schutz mit Hybridpostfächern:** Vielleicht möchten Sie Cloudpostfächer, aber Sie müssen Postfächer für einige Benutzer lokal halten. Wählen Sie dieses Szenario, wenn Sie Postfächer teils lokal und teils mit Exchange Online hosten möchten. Dieses Szenario wird unter [Wechseln zu einer Hybridlösung](#switch-to-a-hybrid-solution) beschrieben.

## <a name="switch-to-eop-standalone"></a>Wechseln zu EOP als eigenständige Lösung

Wenn Sie Postfächer derzeit lokal hosten und eine lokale Schutzvorrichtung oder einen cloudbasierten Messagingschutzdienst verwenden, können Sie zu EOP wechseln, um von seinen Schutzfunktionen und seiner Verfügbarkeit zu profitieren. Wenn Sie EOP als eigenständige Lösung einrichten möchten, d. h. mit lokal gehosteten Postfächern und EOP als E-Mail-Schutz, befolgen Sie die Anleitung unter [Einrichten Ihres EOP-Diensts](/exchange/standalone-eop/set-up-your-eop-service). Sie umfasst die Schritte zum Einrichten von EOP-Schutz, wie das Anmelden, das Hinzufügen einer Domäne und das Einrichten des Nachrichtenflusses mit Connectors.

## <a name="switch-to-exchange-online"></a>Wechseln zu Exchange Online

Möglicherweise verfügen Sie über lokale Postfächer, die durch eine lokale Appliance geschützt sind, und Sie möchten zu Exchange Online in der Cloud gehosteten Postfächern und dem EOP-Schutz wechseln, um die Vorteile der Microsoft 365-Cloud-Messaging- und -Schutzfunktionen zu nutzen. Um zu beginnen, können Sie sich für Microsoft 365 registrieren und Ihre Domäne hinzufügen. In diesem Szenario müssen Sie keine Connectors einrichten, da es kein Routing zu lokalen Postfächern gibt. Beginnen Sie [bei Get the latest advanced features with Microsoft 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans) to sign up and get familiar with its features.

Während des Microsoft 365 erstellen Sie Ihre cloudbasierten Postfachbenutzer.

## <a name="switch-to-a-hybrid-solution"></a>Wechseln zu einer Hybridlösung

Unter Umständen möchten Sie aufgrund geschäftlicher Anforderungen oder aus Vorschriftsgründen nur einen Teil Ihrer Postfächer in die Cloud verschieben. Wenn Sie ein hybrides Szenario bereitstellen, können Sie Postfächer je nach geschäftlichen Anforderungen in die Cloud verschieben. Die Migration zu einem hybriden Szenario mit EOP-Schutz ist zwar komplizierter als die Umstellung auf ein rein cloudbasiertes Szenario, doch bietet Microsoft volle Unterstützung für Hybridlösungen und zahlreiche Ressourcen, um diesen Vorgang zu erleichtern.

Wenn Sie eine Hybridbereitstellung in Betracht ziehen, sollten Sie am besten Exchange Server [Hybridbereitstellungen verwenden.](/exchange/exchange-hybrid) Außerdem stehen in einem hybriden Szenario verschiedene Möglichkeiten zum Weiterleiten von E-Mails zur Verfügung, mit denen Sie sich vertraut machen sollten. [Transportrouting in Exchange hybriden](/exchange/transport-routing) Bereitstellungen erläutert jeden Typ, sodass Sie das beste Routingszenario basierend auf Ihren Geschäftlichen Anforderungen auswählen können.

## <a name="migration-planning"></a>Migrationsplanung

Wenn Sie sich für einen Wechsel zu EOP entscheiden, sollten Sie unbedingt folgenden Bereichen Beachtung schenken:

- **Benutzerdefinierte Filterregeln:** Wenn Sie über benutzerdefinierte Filterungs- oder Geschäftsrichtlinienregeln zum Abfangen bestimmter Spamregeln verfügen, wird empfohlen, EOP mit den Standardeinstellungen für einen Bestimmten Zeitraum auszuprobieren, bevor Sie Ihre Regeln migrieren. Die Standardeinstellungen von EOP bieten unternehmensgerechten Spamschutz, sodass einige Ihrer eigenen Regeln möglicherweise nicht zu EOP migriert werden müssen. Sollten bei Ihnen Regeln zur Umsetzung bestimmter benutzerdefinierter Unternehmensrichtlinien gelten, können Sie diese natürlich erstellen. Weitere Informationen finden Sie unter [Mail flow rules (transport rules) in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).

- **Listen mit zulässigen IP-Adressen** und IP-Sperrlisten: Wenn Sie benutzerfreundliche Listen und Sperrlisten haben, lassen Sie sich etwas Zeit, um die Listen im Rahmen des Setupprozesses in EOP zu kopieren. Weitere Informationen zur Liste der zulässigen IP-Adressen und der Sperrliste für IP finden Sie unter [Configure the connection filter policy](configure-the-connection-filter-policy.md).

- **Sichere Kommunikation**: Wenn Sie über einen Partner verfügen, der verschlüsselte Nachrichten erfordert, empfehlen wir, diese im Exchange einrichten. Informationen zum Konfigurieren dieses Szenarios finden Sie unter [Einrichten von Connectors für den sicheren Nachrichtenfluss mit einer Partnerorganisation](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner).

> [!TIP]
> Beim Wechsel von einer lokalen Vorrichtung zu EOP können Sie diese oder einen Server weiterhin einsetzen, um Geschäftsregeln zu überprüfen. Wenn Ihre Appliance beispielsweise benutzerdefinierte Filterung für ausgehende E-Mails durchführt und dies weiterhin tun soll, können Sie EOP so konfigurieren, dass E-Mails zur zusätzlichen Filterung direkt an die Appliance gesendet werden, bevor sie an das Internet geroutet wird.
