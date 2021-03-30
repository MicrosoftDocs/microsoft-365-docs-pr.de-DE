---
title: Office 365 US Government DOD-Endpunkte
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/29/2021
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
search.appverid:
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: 5d7dce60-4892-4b58-b45e-ee42fe8a907f
f1.keywords:
- NOCSH
description: Office 365 setzt eine Internetverbindung voraus. Die unten aufgeführten Endpunkte sollten nur für Kunden erreichbar sein, die Office 365 U.S. Government DoD-Pläne verwenden.
hideEdit: true
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e236a41833f09684ce69330d78138160c2ddb2b2
ms.sourcegitcommit: b56a8ff9bb496bf2bc1991000afca3d251f45b72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51418097"
---
# <a name="office-365-us-government-dod-endpoints"></a>Office 365 U.S. Government DoD-Endpunkte

*Gültig für Office 365 Admin*

 Office 365 setzt eine Internetverbindung voraus. Die unten aufgeführten Endpunkte sollten nur für Kunden erreichbar sein, die Office 365 U.S. Government DoD-Pläne verwenden.
  
 **Office 365-Endpunkte:** [Weltweit (einschließlich GCC)](urls-and-ip-address-ranges.md) | [Office 365, betrieben von 21Vianet](urls-and-ip-address-ranges-21vianet.md)  | [Office 365 Deutschland](microsoft-365-germany-endpoints.md) | *Office 365 U.S. Government DoD* | [Office 365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) |
  
|||
|:-----|:-----|
|**Last updated:** 29.03.2021 - ![ ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [RSS-Änderungsprotokollabonnement](https://endpoints.office.com/version/USGOVDoD?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |**Download:** die vollständige Liste im [JSON-Format](https://endpoints.office.com/endpoints/USGOVDoD?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |

 Beginnen Sie mit [Verwalten von Office 365-Endpunkten](managing-office-365-endpoints.md), um unsere Empfehlungen zum Verwalten der Netzwerkverbindungen anhand dieser Daten zu verstehen. Endpunktdaten werden bei Bedarf zu Beginn jedes Monats 30 Tage vor ihrer Aktivierung mit neuen IP-Adressen und URLs aktualisiert und veröffentlicht. Auf diese Weise können Kunden, die noch nicht über automatisierte Updates verfügen, Ihre Prozesse abschließen, bevor eine neue Verbindung erforderlich ist. Endpunktdaten werden unter Umständen auch bei Bedarf aktualisiert, um Support-Probleme, Sicherheitsvorfälle oder andere sofortige betriebliche Erfordernisse zu adressieren. Die auf dieser Seite unten angezeigten Daten werden alle aus den REST-basierten Webdiensten generiert. Wenn Sie für den Zugriff auf diese Daten ein Skript oder ein Netzwerkgerät verwenden, sollten Sie direkt zum [Webdienst](microsoft-365-ip-web-service.md) wechseln.

Die nachstehenden Endpunktdaten zeigen die Voraussetzungen für die Verbindung vom Computer eines Benutzers zu Office 365 auf. Sie umfassen keine Netzwerkverbindungen von Microsoft mit einem Kundennetzwerk, manchmal auch als hybride oder eingehende Netzwerkverbindungen bezeichnet. Weitere Informationen finden Sie unter [Zusätzliche Endpunkte, die nicht im Webdienst enthalten sind.](additional-office365-ip-addresses-and-urls.md) 

Die Endpunkte sind in vier Dienstbereichen zusammengefasst. Die ersten drei Dienstbereiche können zu Konnektivitätszwecken unabhängig voneinander ausgewählt werden. Beim vierten Dienstbereich besteht eine gemeinsame Abhängigkeit (als Microsoft 365 Common und Office bezeichnet); er muss immer über Netzwerkkonnektivität verfügen.

Dies sind die dargestellten Datenspalten:

- **ID**: Die ID-Nummer der Zeile, auch als Endpunktsatz bezeichnet. Dies ist die ID, die auch vom Webdienst für den Endpunktsatz zurückgegeben wird.

- **Kategorie**: Zeigt, ob der Endpunktsatz als "Optimize" (Optimieren), "Allow" (Zulassen) oder "Default" (Standard) kategorisiert ist. Informationen zu diesen Kategorien und eine Anleitung zu ihrer Verwaltung finden Sie unter [https://aka.ms/pnc](./microsoft-365-network-connectivity-principles.md). In dieser Spalte sind außerdem die Endpunktsätze aufgelistet, die für Netzwerkkonnektivität erforderlich sind. Für Endpunktsätze, für die keine Netzwerkkonnektivität erforderlich ist, geben wir in diesem Feld Anmerkungen, aus denen hervorgeht, welche Funktionalität durch ein Blockieren des Endpunktsatzes entfallen würde. Wenn Sie einen gesamten Dienstbereich ausschließen, ist für dessen als erforderlich aufgeführte Endpunktsätze keine Konnektivität erforderlich.

- **ER**: Dies ist **Ja,** wenn der Endpunktsatz über Azure ExpressRoute mit Office 365-Routenpräfixen unterstützt wird. Die BGP-Community, die die angezeigten Routenpräfixe enthält, entspricht dem aufgelisteten Dienstbereich. Wenn ER **nein ist,** bedeutet dies, dass ExpressRoute für diesen Endpunktsatz nicht unterstützt wird. Es sollte jedoch nicht davon ausgegangen werden, dass keine Routen für einen Endpunktsatz angekündigt werden, bei dem ER Nein **ist.** Wenn Sie Azure AD Connect verwenden [](/azure/active-directory/hybrid/reference-connect-instances#microsoft-azure-government) möchten, lesen Sie den Abschnitt spezielle Überlegungen, um sicherzustellen, dass Sie über die entsprechende Azure AD Connect-Konfiguration verfügen.

- **Adressen**: Listet die FQDNs oder Platzhalter-Domänennamen und IP-Adressbereiche für den Endpunktsatz auf. Beachten Sie, dass IP-Adressbereiche im CIDR-Format angegeben sind und viele Einzel-IP-Adressen im angegebenen Netzwerk einschließen können.
 
- **Ports**: Listet die TCP- oder UDP-Ports auf, die zusammen mit den Adressen die Netzwerkendpunkte bilden. Wenn verschiedene Ports aufgeführt sind, fallen Ihnen möglicherweise Doppelungen bei den IP-Adressbereichen auf.
 
[!INCLUDE [Office 365 U.S. Government DoD endpoints](../includes/office-365-u.s.-government-dod-endpoints.md)]
  
Hinweise zu dieser Tabelle:

- Das Security and Compliance Center (SCC) bietet Unterstützung für Azure ExpressRoute für Office 365. Dasselbe gilt für viele Features, die über den SCC verfügbar gemacht werden, z. B. Reporting, Auditing, Advanced eDiscovery, Unified DLP und Data Governance. Zwei spezifische Features, PST-Import und eDiscovery-Export, unterstützen derzeit Azure ExpressRoute aufgrund ihrer Abhängigkeit von Azure Blob Storage nicht mit nur Office 365-Routenfiltern. Um diese Features nutzen zu können, benötigen Sie eine separate Konnektivität mit Azure Blob Storage mit allen unterstützten Azure-Konnektivitätsoptionen, z. B. Internetkonnektivität oder Azure ExpressRoute mit Azure Public-Routenfiltern. Sie müssen das Einrichten einer solchen Verbindung für beide Features auswerten. Das Office 365 Information Protection-Team ist sich dieser Einschränkung bewusst und arbeitet aktiv daran, Unterstützung für Azure ExpressRoute für Office 365 als beschränkt auf Office 365-Routenfilter für beide Features zu bieten.

- Es gibt zusätzliche optionale Endpunkte für Microsoft 365 Apps for Enterprise, die nicht aufgeführt sind und nicht erforderlich sind, damit Benutzer Microsoft 365 Apps für Unternehmensanwendungen starten und Dokumente bearbeiten können. Optionale Endpunkte werden in Microsoft-Rechenzentren gehostet und verarbeiten, übertragen oder speichern keine Kundendaten. Es wird empfohlen, dass Benutzerverbindungen zu diesen Endpunkten an den standardmäßigen Internet-Ausgangsperimeter geleitet werden.