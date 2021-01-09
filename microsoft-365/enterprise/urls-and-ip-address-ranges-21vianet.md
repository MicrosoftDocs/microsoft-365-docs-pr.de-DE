---
title: URLs und IP-Adressbereiche für Office 365, betrieben von 21Vianet
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 01/04/2021
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
search.appverid:
- GMA150
- GPA150
- GEA150
ms.assetid: 5c47c07d-f9b6-4b78-a329-bfdc1b6da7a0
ms.custom: seo-marvel-apr2020
f1.keywords:
- NOCSH
description: In diesem Artikel werden die URLs und die IP-Adressbereiche für Office 365 aufgeführt, wenn sie von 21Vianet in China betrieben werden.
hideEdit: true
ms.openlocfilehash: 8a17cb9da5cf552615abf1ac20a67463e8430eb7
ms.sourcegitcommit: a76de3d1604d755b29053e7bf557c0008be6ad23
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2021
ms.locfileid: "49787809"
---
# <a name="urls-and-ip-address-ranges-for-office-365-operated-by-21vianet"></a>URLs und IP-Adressbereiche für Office 365, betrieben von 21Vianet

 *Betrifft: Office 365, betrieben von 21Vianet – Small Business-Administrator, Office 365, betrieben von 21Vianet – Administrator*

**Zusammenfassung**: Die folgenden Endpunkte (FQDNs, Ports, URLs, IPv4- und IPv6-Präfixe) gelten für Office 365, betrieben von 21Vianet, und sind für die Bereitstellung von Produktivitätsdiensten nur im Rahmen der genannten Pläne ausgelegt.
  
 **Office 365-Endpunkte:** [Weltweit (einschließlich GCC)](urls-and-ip-address-ranges.md)  | *Office 365, betrieben von 21Vianet* | [Office 365 Deutschland](microsoft-365-germany-endpoints.md) | [Office 365 U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md) | [Office 365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) |
  
|||
|:-----|:-----|
|**Letzte Aktualisierung:** 04.01.2021 – ![RSS](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Abonnement des Änderungsprotokolls](https://endpoints.office.com/version/China?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)|**Download:** alle erforderlichen und optionalen Ziele in einer Liste im [JSON-Format](https://endpoints.office.com/endpoints/China?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).  <br/> |

Beginnen Sie mit [Verwalten von Office 365-Endpunkten](managing-office-365-endpoints.md), um unsere Empfehlungen für das Verwalten der Netzwerkkonnektivität unter Nutzung dieser Daten nachzuvollziehen. Die Endpunktdaten werden am Anfang jedes Monats mit neuen IP-Adressen und URLs aktualisiert, die 30 Tage vor ihrem Inkrafttreten veröffentlicht werden. Dies gibt Kunden, die ihre Updates noch nicht automatisiert haben, die Möglichkeit, ihre Prozesse abzuschließen, bevor neue Verbindungsinformationen erforderlich sind. Endpunkte können darüber hinaus bei Bedarf auch innerhalb eines Monats aktualisiert werden, wenn dies erforderlich ist, um Supporteskalationen, Sicherheitsvorfällen oder sonstigen unmittelbaren Betriebserfordernissen Rechnung zu tragen. Die unten auf dieser Seite dargestellten Daten wurden alle von den REST-basierten Webdiensten generiert. Wenn Sie ein Skript oder ein Netzwerkgerät für den Zugriff auf diese Daten verwenden, sollten Sie direkt zum [Webdienst](microsoft-365-ip-web-service.md) navigieren.

In den Endpunktdaten unten sind Anforderungen für Netzwerkkonnektivität zwischen dem Computer eines Benutzers und Office 365 aufgelistet. Sie umfassen keine Netzwerkverbindungen von Microsoft mit einem Kundennetzwerk, manchmal auch als hybride oder eingehende Netzwerkverbindungen bezeichnet.

Die Endpunkte sind in vier Dienstbereichen zusammengefasst. Die ersten drei Dienstbereiche können zu Konnektivitätszwecken unabhängig voneinander ausgewählt werden. Beim vierten Dienstbereich besteht eine gemeinsame Abhängigkeit (als Microsoft 365 Common und Office bezeichnet); er muss immer über Netzwerkkonnektivität verfügen.

Dies sind die dargestellten Datenspalten:

- **ID**: Die ID-Nummer der Zeile, auch als Endpunktsatz bezeichnet. Dies ist die ID, die auch vom Webdienst für den Endpunktsatz zurückgegeben wird.

- **Kategorie**: Zeigt, ob der Endpunktsatz als "Optimize" (Optimieren), "Allow" (Zulassen) oder "Default" (Standard) kategorisiert ist. Informationen zu diesen Kategorien und eine Anleitung zu ihrer Verwaltung finden Sie unter [https://aka.ms/pnc](https://aka.ms/pnc). In dieser Spalte sind außerdem die Endpunktsätze aufgelistet, die für Netzwerkkonnektivität erforderlich sind. Für Endpunktsätze, für die keine Netzwerkkonnektivität erforderlich ist, geben wir in diesem Feld Anmerkungen, aus denen hervorgeht, welche Funktionalität durch ein Blockieren des Endpunktsatzes entfallen würde. Wenn Sie einen gesamten Dienstbereich ausschließen, ist für dessen als erforderlich aufgeführte Endpunktsätze keine Konnektivität erforderlich.

- **ER**: Der Wert ist **Yes** (Ja), wenn der Endpunktsatz über Azure ExpressRoute mit Office 365-Routingpräfixen unterstützt wird. Die BGP-Community, die die angegebenen Routingpräfixe enthält, ist dem aufgeführten Dienstbereich zugeordnet. Der Wert **No** (Nein) für ER bedeutet, dass ExpressRoute für den betreffenden Endpunktsatz nicht unterstützt wird. Es sollte jedoch nicht davon ausgegangen werden, dass für einen Endpunktsatz mit **No** für ER keine Routen angekündigt werden.

- **Adressen**: Listet die FQDNs oder Platzhalter-Domänennamen und IP-Adressbereiche für den Endpunktsatz auf. Beachten Sie, dass IP-Adressbereiche im CIDR-Format angegeben sind und viele Einzel-IP-Adressen im angegebenen Netzwerk einschließen können.
 
- **Ports**: Listet die TCP- oder UDP-Ports auf, die zusammen mit den Adressen die Netzwerkendpunkte bilden. Wenn verschiedene Ports aufgeführt sind, fallen Ihnen möglicherweise Doppelungen bei den IP-Adressbereichen auf.

[!INCLUDE [Office 365 operated by 21Vianet endpoints](../includes/office-365-operated-by-21vianet-endpoints.md)]


