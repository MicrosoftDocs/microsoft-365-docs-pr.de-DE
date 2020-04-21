---
title: Switch to EOP from Google Postini, the Barracuda Spam and Virus Firewall, or Cisco IronPort
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
ms.assetid: 81b75194-3b04-48da-8b81-951afbabedde
description: Dieser Artikel soll Ihnen helfen, den Prozess für die Umstellung auf Exchange Online Schutz (EoP) von einer lokalen e-Mail-Hygiene-Appliance oder einem Cloud-basierten Schutzdienst zu verstehen und Ihnen dann Hilferessourcen für den Einstieg bereitzustellen.
ms.openlocfilehash: e6a25d6477741f5796dd08b5811d97e2d0c76b51
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631193"
---
# <a name="switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco-ironport"></a>Wechseln zu EOP von Google Postini, Barracuda Spam & Virus Firewall oder Cisco IronPort

 In diesem Thema wird der Wechsel von einer lokalen E-Mail-Schutzvorrichtung oder einem cloudbasierten Schutzdienst zu Exchange Online Protection (EOP) näher erläutert. Zur Erleichterung des Einstiegs werden hier außerdem einige Hilferessourcen genannt. Es gibt zahlreiche Lösungen zum Filtern von Spam, doch läuft der Wechsel zu EOP in den meisten Fällen ähnlich ab.

Wenn Sie neu in EoP sind und eine Übersicht über seine Funktionen lesen möchten, bevor Sie sich für einen Wechsel entscheiden, beginnen Sie mit dem Thema [Exchange Online Protection Overview](exchange-online-protection-overview.md) .

Bevor Sie zu EOP wechseln, sollten Sie zuerst überlegen, ob Sie die EOP-geschützten Postfächer in der Cloud, mit Exchange Online, lokal oder in einem hybriden Szenario hosten möchten. (Bei einem hybriden Szenario werden Postfächer teils lokal und teils mit Exchange Online gehostet.) Jedes dieser Hostingszenarios - cloudbasiert, lokal oder hybrid - ist möglich, wird jedoch u. U. unterschiedlich eingerichtet. Die folgenden Überlegungen sollen Ihnen bei der Wahl der richtigen Bereitstellung helfen:

- **EoP-Schutz mit lokalen Postfächern**: Dieses Szenario eignet sich, wenn Sie über eine vorhandene e-Mail-Hosting-Infrastruktur verfügen oder geschäftliche Anforderungen haben, um Postfächer lokal zu verwalten, und Sie möchten EoP als cloudbasierten e-Mail-Schutz verwenden. Eine genauere Beschreibung dieses Szenarios finden Sie unter [Wechseln zu EOP als eigenständige Lösung](#switch-to-eop-standalone).

- **EoP-Schutz mit Exchange Online Postfächern**: Dieses Szenario ist geeignet, wenn EoP-Schutz und alle ihre Postfächer in der Cloud gehostet werden sollen. Dadurch verringert sich die Komplexität, da Sie keine lokalen Messagingserver unterhalten müssen. Dieses Szenario wird unter [Wechseln zu Exchange Online](#switch-to-exchange-online) beschrieben.

- **EoP-Schutz mit Hybrid Postfächern**: möglicherweise möchten Sie Cloud-Postfächer, aber Sie müssen Postfächer für einige Benutzer lokal aufbewahren. Wählen Sie dieses Szenario, wenn Sie Postfächer teils lokal und teils mit Exchange Online hosten möchten. Dieses Szenario wird unter [Wechseln zu einer Hybridlösung](#switch-to-a-hybrid-solution) beschrieben.

## <a name="switch-to-eop-standalone"></a>Wechseln zu EOP als eigenständige Lösung

Wenn Sie Postfächer derzeit lokal hosten und eine lokale Schutzvorrichtung oder einen cloudbasierten Messagingschutzdienst verwenden, können Sie zu EOP wechseln, um von seinen Schutzfunktionen und seiner Verfügbarkeit zu profitieren. Wenn Sie EOP als eigenständige Lösung einrichten möchten, d. h. mit lokal gehosteten Postfächern und EOP als E-Mail-Schutz, befolgen Sie die Anleitung unter [Einrichten Ihres EOP-Diensts](set-up-your-eop-service.md). Sie umfasst die Schritte zum Einrichten von EOP-Schutz, wie das Anmelden, das Hinzufügen einer Domäne und das Einrichten des Nachrichtenflusses mit Connectors.

## <a name="switch-to-exchange-online"></a>Wechseln zu Exchange Online

Möglicherweise haben Sie lokale Postfächer, die durch eine lokale Appliance geschützt sind, und Sie möchten zu Exchange Online in der Cloud gehosteten Postfächern und zum Schutz vor EoP wechseln, um die Microsoft 365 Cloud Messaging and Protection-Funktionen nutzen zu können. Um zu beginnen, können Sie sich für Microsoft 365 registrieren und Ihre Domäne hinzufügen. In diesem Szenario müssen Sie keine Connectors einrichten, da kein Routing an lokale Postfächer erfolgt. Beginnen [Sie mit dem Abrufen der neuesten erweiterten Funktionen mit Microsoft 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans) , um sich anzumelden und sich mit den Funktionen vertraut zu machen.

Während des Setupvorgangs von Microsoft 365 erstellen Sie die cloudbasierten Postfachbenutzer.

## <a name="switch-to-a-hybrid-solution"></a>Wechseln zu einer Hybridlösung

Unter Umständen möchten Sie aufgrund geschäftlicher Anforderungen oder aus Vorschriftsgründen nur einen Teil Ihrer Postfächer in die Cloud verschieben. Wenn Sie ein hybrides Szenario bereitstellen, können Sie Postfächer je nach geschäftlichen Anforderungen in die Cloud verschieben. Die Migration zu einem hybriden Szenario mit EOP-Schutz ist zwar komplizierter als die Umstellung auf ein rein cloudbasiertes Szenario, doch bietet Microsoft volle Unterstützung für Hybridlösungen und zahlreiche Ressourcen, um diesen Vorgang zu erleichtern.

Der beste Ausgangspunkt für eine hybridbereitstellung ist [Exchange Server hybridbereitstellungen](https://docs.microsoft.com/exchange/exchange-hybrid). Außerdem stehen in einem hybriden Szenario verschiedene Möglichkeiten zum Weiterleiten von E-Mails zur Verfügung, mit denen Sie sich vertraut machen sollten. [In Transport Routing in Exchange-hybridbereitstellungen](https://docs.microsoft.com/exchange/transport-routing) werden die einzelnen Typen erläutert, sodass Sie basierend auf Ihren geschäftlichen Anforderungen das beste Routing Szenario auswählen können.

## <a name="migration-planning"></a>Migrationsplanung

Wenn Sie sich für einen Wechsel zu EOP entscheiden, sollten Sie unbedingt folgenden Bereichen Beachtung schenken:

- **Benutzerdefinierte Filterregeln**: Wenn Sie benutzerdefinierte Filter-oder Geschäftsrichtlinien Regeln zum Abfangen bestimmter Spam-Nachrichten verwenden, sollten Sie EoP mit den Standardeinstellungen für einen bestimmten Zeitraum testen, bevor Sie die Regeln migrieren. Die Standardeinstellungen von EOP bieten unternehmensgerechten Spamschutz, sodass einige Ihrer eigenen Regeln möglicherweise nicht zu EOP migriert werden müssen. Sollten bei Ihnen Regeln zur Umsetzung bestimmter benutzerdefinierter Unternehmensrichtlinien gelten, können Sie diese natürlich erstellen. [Nachrichtenfluss Regeln (Transportregeln) in Exchange Online Protection](mail-flow-rules-transport-rules-0.md) enthält detaillierte Anweisungen zum Erstellen von Nachrichtenfluss Regeln in EoP.

- **IP-Zulassungslisten und IP-Sperrlisten**: Wenn Sie Listen mit zugelassenen Benutzern und blockierten Listen verwenden, lassen Sie die Listen in EoP im Rahmen des Setupprozesses auf einige Zeit kopieren. Weitere Informationen zu IP-Zulassungslisten und IP-Sperrlisten finden Sie unter [Konfigurieren der Verbindungsfilter Richtlinie](configure-the-connection-filter-policy.md).

- **Sichere Kommunikation**: Wenn Sie über einen Partner verfügen, der verschlüsselte Nachrichten benötigt, wird empfohlen, diese im Exchange Admin Center einzurichten. Informationen zum Konfigurieren dieses Szenarios finden Sie unter [Einrichten von Connectors für den sicheren e-Mail-Fluss mit einer Partnerorganisation](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner).

> [!TIP]
> Beim Wechsel von einer lokalen Vorrichtung zu EOP können Sie diese oder einen Server weiterhin einsetzen, um Geschäftsregeln zu überprüfen. Wenn Ihre Appliance beispielsweise eine benutzerdefinierte Filterung für ausgehende e-Mails ausführt und Sie dies weiterhin tun möchten, können Sie EoP so konfigurieren, dass e-Mails direkt an die Appliance gesendet werden, um eine zusätzliche Filterung durchzuführen, bevor Sie an das Internet weitergeleitet wird.
