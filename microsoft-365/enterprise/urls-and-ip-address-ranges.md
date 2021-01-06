---
title: URLs und IP-Adressbereiche für Office 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 01/04/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- MOM160
- BCS160
ms.assetid: 8548a211-3fe7-47cb-abb1-355ea5aa88a2
description: 'Zusammenfassung: Office 365 erfordert eine Internetverbindung. Die unten aufgeführten Endpunkte sollten für Kunden, die Office 365-Pläne verwenden, einschließlich Government Community Cloud (GCC), erreichbar sein.'
hideEdit: true
ms.openlocfilehash: c5a1b4852d128329641a700cbd9ba0e5468cc01c
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750835"
---
# <a name="office-365-urls-and-ip-address-ranges"></a>Office 365-URLs und -IP-Adressbereiche

Office 365 erfordert eine Internetverbindung. Die unten aufgeführten Endpunkte sollten für Kunden, die Office 365-Pläne verwenden, einschließlich Government Community Cloud (GCC), erreichbar sein.
  
*Office 365 Weltweit (+GCC)* | [Office 365, betrieben von 21Vianet](urls-and-ip-address-ranges-21vianet.md) | [Office 365 Deutschland](microsoft-365-germany-endpoints.md) | [Office 365 U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md)  | [Office 365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) |

||||
|:-----|:-----|:-----|
|**Letzte Aktualisierung:** 04.01.2021 – ![RSS](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Abonnement des Änderungsprotokolls](https://endpoints.office.com/version/worldwide?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |**Download:** alle erforderlichen und optionalen Ziele in einer Liste im [JSON-Format](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).  <br/> | **Verwendung:** unsere Proxy-[PAC-Dateien](managing-office-365-endpoints.md#pacfiles) <br/> |

 Beginnen Sie mit [Managing Office 365 endpoints](managing-office-365-endpoints.md) (Verwalten von Office 365-Endpunkten), um unsere Empfehlungen für das Verwalten der Netzwerkkonnektivität unter Nutzung dieser Daten nachzuvollziehen. Die Endpunktdaten werden am Anfang jedes Monats mit neuen IP-Adressen und URLs aktualisiert, die 30 Tage vor ihrem Inkrafttreten veröffentlicht werden. Dies gibt Kunden, die ihre Updates noch nicht automatisiert haben, die Möglichkeit, ihre Prozesse abzuschließen, bevor neue Verbindungsinformationen erforderlich sind. Endpunkte können darüber hinaus bei Bedarf auch innerhalb eines Monats aktualisiert werden, wenn dies erforderlich ist, um Supporteskalationen, Sicherheitsvorfällen oder sonstigen unmittelbaren Betriebserfordernissen Rechnung zu tragen. Die unten auf dieser Seite dargestellten Daten wurden alle von den REST-basierten Webdiensten generiert. Wenn Sie ein Skript oder ein Netzwerkgerät für den Zugriff auf diese Daten verwenden, sollten Sie direkt zum [Webdienst](microsoft-365-ip-web-service.md) navigieren.

In den Endpunktdaten unten sind Anforderungen für Netzwerkkonnektivität zwischen dem Computer eines Benutzers und Office 365 aufgelistet. Sie umfassen keine Netzwerkverbindungen von Microsoft mit einem Kundennetzwerk, manchmal auch als hybride oder eingehende Netzwerkverbindungen bezeichnet. Weitere Informationen finden Sie unter [Zusätzliche Endpunkte](additional-office365-ip-addresses-and-urls.md).

Die Endpunkte sind in vier Dienstbereichen zusammengefasst. Die ersten drei Dienstbereiche können zu Konnektivitätszwecken unabhängig voneinander ausgewählt werden. Beim vierten Dienstbereich besteht eine gemeinsame Abhängigkeit (als Microsoft 365 Common und Office bezeichnet); er muss immer über Netzwerkkonnektivität verfügen.

Dies sind die dargestellten Datenspalten:

- **ID**: Die ID-Nummer der Zeile, auch als Endpunktsatz bezeichnet. Dies ist die ID, die auch vom Webdienst für den Endpunktsatz zurückgegeben wird.

- **Kategorie**: Zeigt, ob der Endpunktsatz als "Optimize" (Optimieren), "Allow" (Zulassen) oder "Default" (Standard) kategorisiert ist. Informationen zu diesen Kategorien und eine Anleitung zu ihrer Verwaltung finden Sie unter [Neue Office 365 Endpunkt-Kategorien](microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories). In dieser Spalte sind außerdem die Endpunktsätze aufgelistet, die für Netzwerkkonnektivität erforderlich sind. Für Endpunktsätze, für die keine Netzwerkkonnektivität erforderlich ist, geben wir in diesem Feld Anmerkungen, aus denen hervorgeht, welche Funktionalität durch ein Blockieren des Endpunktsatzes entfallen würde. Wenn Sie einen gesamten Dienstbereich ausschließen, ist für dessen als erforderlich aufgeführte Endpunktsätze keine Konnektivität erforderlich.

- **ER**: Der Wert ist **Yes** (Ja), wenn der Endpunktsatz über Azure ExpressRoute mit Office 365-Routingpräfixen unterstützt wird. Die BGP-Community, die die angegebenen Routingpräfixe enthält, ist dem aufgeführten Dienstbereich zugeordnet. Der Wert **No** (Nein) für ER bedeutet, dass ExpressRoute für den betreffenden Endpunktsatz nicht unterstützt wird. Es sollte jedoch nicht davon ausgegangen werden, dass für einen Endpunktsatz mit **No** für ER keine Routen angekündigt werden.

- **Adressen**: Listet die FQDNs oder Platzhalter-Domänennamen und IP-Adressbereiche für den Endpunktsatz auf. Beachten Sie, dass IP-Adressbereiche im CIDR-Format angegeben sind und viele Einzel-IP-Adressen im angegebenen Netzwerk einschließen können.
 
- **Ports**: Listet die TCP- oder UDP-Ports auf, die zusammen mit den Adressen die Netzwerkendpunkte bilden. Wenn verschiedene Ports aufgeführt sind, fallen Ihnen möglicherweise Doppelungen bei den IP-Adressbereichen auf.

[!INCLUDE [Office 365 worldwide endpoints](../includes/office-365-worldwide-endpoints.md)]

>[!Note]
>Empfehlungen zu Yammer-IP-Adressen und -URLs finden Sie [in diesem Blogbeitrag](https://techcommunity.microsoft.com/t5/Yammer-Blog/Using-hard-coded-IP-addresses-for-Yammer-is-not-recommended/ba-p/276592).
>

## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Office 365-Endpunkten](managing-office-365-endpoints.md)

[Allgemeine Microsoft Stream Endpunkte](https://docs.microsoft.com/stream/network-overview#general-microsoft-stream-endpoints)
  
[Überwachen der Microsoft 365-Konnektivität](https://docs.microsoft.com/microsoft-365/enterprise/monitor-connectivity?view=o365-worldwide)

[Rooten Sie das ZS und das ZS-Paket auf das Anwendungssystem des Drittanbieters](../compliance/encryption-office-365-certificate-chains.md)
  
[Clientkonnektivität](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[Netzwerke für die Inhaltsübermittlung](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[IP-Bereiche von Microsoft Azure-Rechenzentren](https://www.microsoft.com/download/details.aspx?id=41653)
  
[Öffentlicher Microsoft IP-Bereich](https://www.microsoft.com/download/details.aspx?id=53602)
