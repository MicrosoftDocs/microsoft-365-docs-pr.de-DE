---
title: Office 365-Endpunkte in Deutschland
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid: MOE150
ms.assetid: 8a113a50-0071-4155-bb8e-eba5a8dbd4c8
description: In diesem Artikel finden Sie Endpunkte, die für Kunden mit Office 365 in Deutschland erreichbar sind.
hideEdit: true
ms.openlocfilehash: 27d7b3c895cb3a8cae148262ce3962f03fb417aa
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925806"
---
# <a name="office-365-germany-endpoints"></a>Endpunkte für Office 365 Deutschland

 *Gültig für Office 365 Admin*

Office 365 setzt eine Internetverbindung voraus. Die folgenden Endpunkte sollten nur für Kunden mit **Office 365 Deutschland**-Plänen erreichbar sein.

> [!NOTE]
> Für Kunden, die sich im Übergang zur neuen Microsoft 365 Rechenzentrumsregion in Deutschland befinden, ändern sich die Endpunkte.
> Weiter Informationen finden Sie in [Migration von Microsoft Cloud Deutschland zu Office 365-Diensten in den neuen deutschen Rechenzentrumsregionen](ms-cloud-germany-transition.md).
  
 **Office 365-Endpunkte:** [Weltweit (einschließlich GCC)](urls-and-ip-address-ranges.md)  | [Office 365, betrieben von 21Vianet](urls-and-ip-address-ranges-21vianet.md)  | *Office 365 Deutschland* | [Office 365 U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md) | [Office 365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md)  |
  
**Letzte Aktualisierung:** 01.12.2020 – ![RSS](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Abonnement des Änderungsprotokolls](https://endpoints.office.com/version/Germany?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)

**Download:** alle erforderlichen und optionalen Ziele in einer Liste im [JSON-Format](https://endpoints.office.com/endpoints/Germany?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).

Beginnen Sie mit [Verwalten von Office 365-Endpunkten](managing-office-365-endpoints.md), um unsere Empfehlungen für die Verwaltung der Netzwerkverbindung mit diesen Daten zu verstehen. Endpunktdaten werden zu Beginn jedes Monats nach Bedarf aktualisiert, wobei neue IP-Adressen und URLs 30 Tage vor der Aktivierung veröffentlicht werden. Dadurch können Kunden, die noch nicht über automatisierte Updates verfügen, ihre Prozesse abschließen, bevor neue Verbindungen erforderlich sind. Endpunkte können auch während des Monats aktualisiert werden, wenn dies erforderlich ist, um Supporteskalationen, Sicherheitsvorfälle oder andere sofortige betriebliche Anforderungen zu erfüllen. Sie können jederzeit auf das [Änderungsprotokollabonnement](https://endpoints.office.com/version/Germany?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)verweisen.

Die auf dieser Seite unten angezeigten Daten werden alle aus den REST-basierten Webdiensten generiert. Wenn Sie für den Zugriff auf diese Daten ein Skript oder ein Netzwerkgerät verwenden, sollten Sie direkt zum [Webdienst](microsoft-365-ip-web-service.md) wechseln.

In den Endpunktdaten unten sind Anforderungen für die Verbindung zwischen dem Computer eines Benutzers und Office 365 aufgelistet. Sie umfassen keine Netzwerkverbindungen von Microsoft mit einem Kundennetzwerk, manchmal auch als hybride oder eingehende Netzwerkverbindungen bezeichnet.

Die Endpunkte sind in vier Dienstbereichen zusammengefasst. Die ersten drei Dienstbereiche können zu Konnektivitätszwecken unabhängig voneinander ausgewählt werden. Beim vierten Dienstbereich besteht eine gemeinsame Abhängigkeit (als Microsoft 365 Common und Office bezeichnet); er muss immer über Netzwerkkonnektivität verfügen.

Dies sind die dargestellten Datenspalten:

- **ID**: Die ID-Nummer der Zeile, auch als Endpunktsatz bezeichnet. Dies ist die ID, die auch vom Webdienst für den Endpunktsatz zurückgegeben wird.

- **Kategorie**: Zeigt, ob der Endpunktsatz als "Optimize" (Optimieren), "Allow" (Zulassen) oder "Default" (Standard) kategorisiert ist. Informationen zu diesen Kategorien und eine Anleitung zu ihrer Verwaltung finden Sie unter [https://aka.ms/pnc](./microsoft-365-network-connectivity-principles.md). In dieser Spalte sind außerdem die Endpunktsätze aufgelistet, die für Netzwerkkonnektivität erforderlich sind. Für Endpunktsätze, für die keine Netzwerkkonnektivität erforderlich ist, geben wir in diesem Feld Anmerkungen, aus denen hervorgeht, welche Funktionalität durch ein Blockieren des Endpunktsatzes entfallen würde. Wenn Sie einen gesamten Dienstbereich ausschließen, ist für dessen als erforderlich aufgeführte Endpunktsätze keine Konnektivität erforderlich.

- **ER**: Der Wert ist **Yes** (Ja), wenn der Endpunktsatz über Azure ExpressRoute mit Office 365-Routingpräfixen unterstützt wird. Die BGP-Community, die die angegebenen Routingpräfixe enthält, ist dem aufgeführten Dienstbereich zugeordnet. Der Wert **No** (Nein) für ER bedeutet, dass ExpressRoute für den betreffenden Endpunktsatz nicht unterstützt wird. Es sollte jedoch nicht davon ausgegangen werden, dass für einen Endpunktsatz mit **No** für ER keine Routen angekündigt werden.

- **Adressen**: Listet die FQDNs oder Platzhalter-Domänennamen und IP-Adressbereiche für den Endpunktsatz auf. Beachten Sie, dass IP-Adressbereiche im CIDR-Format angegeben sind und viele Einzel-IP-Adressen im angegebenen Netzwerk einschließen können.
 
- **Ports**: Listet die TCP- oder UDP-Ports auf, die zusammen mit den Adressen die Netzwerkendpunkte bilden. Wenn verschiedene Ports aufgeführt sind, fallen Ihnen möglicherweise Doppelungen bei den IP-Adressbereichen auf.

[!INCLUDE [Office 365 Germany endpoints](../includes/office-365-germany-endpoints.md)]

