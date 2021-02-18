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
description: In diesem Artikel erfahren Sie, wie Sie von einer lokalen E-Mail-Schutz-Appliance oder einem cloudbasierten Schutzdienst zu Exchange Online Protection (EOP) wechseln.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0cb946fbb60393657aab21195bc4dd723458f16e
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290189"
---
# <a name="switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco-ironport"></a>Wechseln zu EOP von Google Postini, Barracuda Spam & Virus Firewall oder Cisco IronPort

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

 In diesem Thema wird der Wechsel von einer lokalen E-Mail-Schutzvorrichtung oder einem cloudbasierten Schutzdienst zu Exchange Online Protection (EOP) näher erläutert. Zur Erleichterung des Einstiegs werden hier außerdem einige Hilferessourcen genannt. Es gibt zahlreiche Lösungen zum Filtern von Spam, doch läuft der Wechsel zu EOP in den meisten Fällen ähnlich ab.

Wenn Sie noch keine Erfahrung mit EOP haben und eine Übersicht über die Features lesen möchten, bevor Sie sich für einen Wechsel entscheiden, beginnen Sie mit dem [Exchange Online Protection-Übersichtsthema.](exchange-online-protection-overview.md)

Bevor Sie zu EOP wechseln, sollten Sie zuerst überlegen, ob Sie die EOP-geschützten Postfächer in der Cloud, mit Exchange Online, lokal oder in einem hybriden Szenario hosten möchten. (Bei einem hybriden Szenario werden Postfächer teils lokal und teils mit Exchange Online gehostet.) Jedes dieser Hostingszenarios - cloudbasiert, lokal oder hybrid - ist möglich, wird jedoch u. U. unterschiedlich eingerichtet. Die folgenden Überlegungen sollen Ihnen bei der Wahl der richtigen Bereitstellung helfen:

- **EOP-Schutz** mit lokalen Postfächern: Dieses Szenario ist geeignet, wenn Sie über eine vorhandene E-Mail-Hostinginfrastruktur verfügen, die Sie verwenden möchten, oder sie geschäftliche Anforderungen haben, um Postfächer lokal zu halten, und Sie EOP als cloudbasierten E-Mail-Schutz verwenden möchten. Eine genauere Beschreibung dieses Szenarios finden Sie unter [Wechseln zu EOP als eigenständige Lösung](#switch-to-eop-standalone).

- **EOP-Schutz mit Exchange** Online-Postfächern: Dieses Szenario ist geeignet, wenn Sie den Schutz von EOP und alle Ihre Postfächer in der Cloud hosten möchten. Dadurch verringert sich die Komplexität, da Sie keine lokalen Messagingserver unterhalten müssen. Dieses Szenario wird unter [Wechseln zu Exchange Online](#switch-to-exchange-online) beschrieben.

- **EOP-Schutz mit** Hybridpostfächern: Vielleicht möchten Sie Cloudpostfächer, aber Sie müssen Postfächer für einige Benutzer lokal behalten. Wählen Sie dieses Szenario, wenn Sie Postfächer teils lokal und teils mit Exchange Online hosten möchten. Dieses Szenario wird unter [Wechseln zu einer Hybridlösung](#switch-to-a-hybrid-solution) beschrieben.

## <a name="switch-to-eop-standalone"></a>Wechseln zu EOP als eigenständige Lösung

Wenn Sie Postfächer derzeit lokal hosten und eine lokale Schutzvorrichtung oder einen cloudbasierten Messagingschutzdienst verwenden, können Sie zu EOP wechseln, um von seinen Schutzfunktionen und seiner Verfügbarkeit zu profitieren. Wenn Sie EOP als eigenständige Lösung einrichten möchten, d. h. mit lokal gehosteten Postfächern und EOP als E-Mail-Schutz, befolgen Sie die Anleitung unter [Einrichten Ihres EOP-Diensts](set-up-your-eop-service.md). Sie umfasst die Schritte zum Einrichten von EOP-Schutz, wie das Anmelden, das Hinzufügen einer Domäne und das Einrichten des Nachrichtenflusses mit Connectors.

## <a name="switch-to-exchange-online"></a>Wechseln zu Exchange Online

Vielleicht verfügen Sie über lokale Postfächer, die durch eine lokale Appliance geschützt sind, und sie möchten zu in der Cloud gehosteten Exchange Online-Postfächern und dem EOP-Schutz wechseln, um die Microsoft 365-Cloud-Messaging- und -Schutzfunktionen zu nutzen. Um zu beginnen, können Sie sich für Microsoft 365 registrieren und Ihre Domäne hinzufügen. In diesem Szenario müssen Sie keine Connectors einrichten, da es kein Routing an lokale Postfächer gibt. Beginnen Sie [mit den neuesten erweiterten Features mit Microsoft 365,](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans) um sich zu registrieren und sich mit den Features vertraut zu machen.

Während des Microsoft 365-Setupprozesses erstellen Sie Ihre cloudbasierten Postfachbenutzer.

## <a name="switch-to-a-hybrid-solution"></a>Wechseln zu einer Hybridlösung

Unter Umständen möchten Sie aufgrund geschäftlicher Anforderungen oder aus Vorschriftsgründen nur einen Teil Ihrer Postfächer in die Cloud verschieben. Wenn Sie ein hybrides Szenario bereitstellen, können Sie Postfächer je nach geschäftlichen Anforderungen in die Cloud verschieben. Die Migration zu einem hybriden Szenario mit EOP-Schutz ist zwar komplizierter als die Umstellung auf ein rein cloudbasiertes Szenario, doch bietet Microsoft volle Unterstützung für Hybridlösungen und zahlreiche Ressourcen, um diesen Vorgang zu erleichtern.

Wenn Sie eine Hybridbereitstellung in Betracht ziehen, sollten Sie am besten mit Exchange Server [hybriden Bereitstellungen beginnen.](https://docs.microsoft.com/exchange/exchange-hybrid) Außerdem stehen in einem hybriden Szenario verschiedene Möglichkeiten zum Weiterleiten von E-Mails zur Verfügung, mit denen Sie sich vertraut machen sollten. [Transportrouting in Exchange-Hybridbereitstellungen](https://docs.microsoft.com/exchange/transport-routing) erläutert jeden Typ, sodass Sie basierend auf Ihren Geschäftsanforderungen das beste Routingszenario auswählen können.

## <a name="migration-planning"></a>Migrationsplanung

Wenn Sie sich für einen Wechsel zu EOP entscheiden, sollten Sie unbedingt folgenden Bereichen Beachtung schenken:

- **Benutzerdefinierte Filterregeln:** Wenn Sie über benutzerdefinierte Filterungs- oder Geschäftsrichtlinienregeln verfügen, um bestimmte Spamnachrichten zu fangen, sollten Sie EOP mit den Standardeinstellungen für einen bestimmten Zeitraum testen, bevor Sie die Regeln migrieren. Die Standardeinstellungen von EOP bieten unternehmensgerechten Spamschutz, sodass einige Ihrer eigenen Regeln möglicherweise nicht zu EOP migriert werden müssen. Sollten bei Ihnen Regeln zur Umsetzung bestimmter benutzerdefinierter Unternehmensrichtlinien gelten, können Sie diese natürlich erstellen. [Nachrichtenflussregeln (Transportregeln) in Exchange Online Protection](mail-flow-rules-transport-rules-0.md) enthält ausführliche Anweisungen zum Erstellen von Nachrichtenflussregeln in EOP.

- **Listen mit zulässigen** und blockierten IP-Adressen: Wenn Sie über Listen mit zulässigen und blockierten Listen pro Benutzer verfügen, lassen Sie sich im Rahmen des Setupprozesses etwas Zeit, um die Listen nach EOP zu kopieren. Weitere Informationen zur Liste zulässiger und blockierter IP-Adressen finden Sie unter ["Konfigurieren der Verbindungsfilterrichtlinie".](configure-the-connection-filter-policy.md)

- **Sichere Kommunikation:** Wenn Sie über einen Partner verfügen, der verschlüsseltes Messaging erfordert, sollten Sie dies im Exchange Admin Center einrichten. Informationen zum Konfigurieren dieses Szenarios finden Sie unter ["Einrichten von Connectors für den sicheren Nachrichtenfluss mit einer Partnerorganisation".](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

> [!TIP]
> Beim Wechsel von einer lokalen Vorrichtung zu EOP können Sie diese oder einen Server weiterhin einsetzen, um Geschäftsregeln zu überprüfen. Wenn Ihre Appliance beispielsweise benutzerdefinierte Filterung für ausgehende E-Mails durchführt und sie dies weiterhin tun soll, können Sie EOP so konfigurieren, dass E-Mails zur weiteren Filterung direkt an die Appliance gesendet werden, bevor sie an das Internet geroutet werden.
