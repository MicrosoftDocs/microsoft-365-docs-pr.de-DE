---
title: 'Office 365-Endpunkte für U.S. Government GCC High '
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 05/28/2021
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
- Adm_O365
- seo-marvel-apr2020
search.appverid: MET150
ms.assetid: cbd2369c-fd96-464c-bf48-c99826b459ee
description: In diesem Artikel finden Sie Endpunkte, die für Kunden erreichbar sind, die Office 365 U.S. Government GCC High-Pläne verwenden.
hideEdit: true
ms.openlocfilehash: 2febfec744dfb527dd99b205f3b2b78f5b9af4e7
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286357"
---
# <a name="office-365-us-government-gcc-high-endpoints"></a>Office 365-Endpunkte für U.S. Government GCC High 

*Gültig für Office 365 Admin*

Office 365 setzt eine Internetverbindung voraus. Die folgenden Endpunkte sollten nur für Kunden erreichbar sein, die Office 365 U.S. Government GCC High-Pläne verwenden.
  
 **Office 365 Endpunkte:** [Weltweit (einschließlich GCC)](urls-and-ip-address-ranges.md) \| [Office 365 von 21 Vianet](urls-and-ip-address-ranges-21vianet.md) Office 365 \| [Deutschland](microsoft-365-germany-endpoints.md) \| [Office 365 U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md) Office 365 \| *U.S. Government GCC High* betrieben

<br>

****

|Anmerkungen|Herunterladen|
|---|---|
|**Zuletzt aktualisiert:** 28.05.2021 – ![RSS](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Abonnement des Änderungsprotokolls](https://endpoints.office.com/version/USGOVGCCHigh?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)|**Herunterladen:** die vollständige Liste im [JSON-Format](https://endpoints.office.com/endpoints/USGOVGCCHigh?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)|
|

 Beginnen Sie mit [Verwalten von Office 365-Endpunkten](managing-office-365-endpoints.md), um unsere Empfehlungen zum Verwalten der Netzwerkverbindungen anhand dieser Daten zu verstehen. Endpunktdaten werden bei Bedarf zu Beginn jedes Monats 30 Tage vor ihrer Aktivierung mit neuen IP-Adressen und URLs aktualisiert und veröffentlicht. Auf diese Weise können Kunden, die noch nicht über automatisierte Updates verfügen, Ihre Prozesse abschließen, bevor eine neue Verbindung erforderlich ist. Endpunktdaten werden unter Umständen auch bei Bedarf aktualisiert, um Support-Probleme, Sicherheitsvorfälle oder andere sofortige betriebliche Erfordernisse zu adressieren. Die auf dieser Seite unten angezeigten Daten werden alle aus den REST-basierten Webdiensten generiert. Wenn Sie für den Zugriff auf diese Daten ein Skript oder ein Netzwerkgerät verwenden, sollten Sie direkt zum [Webdienst](microsoft-365-ip-web-service.md) wechseln.

In den Endpunktdaten unten sind Anforderungen für Netzwerkkonnektivität zwischen dem Computer eines Benutzers und Office 365 aufgelistet. Sie umfassen keine Netzwerkverbindungen von Microsoft mit einem Kundennetzwerk, manchmal auch als hybride oder eingehende Netzwerkverbindungen bezeichnet.

Die Endpunkte sind in vier Dienstbereichen zusammengefasst. Die ersten drei Dienstbereiche können zu Konnektivitätszwecken unabhängig voneinander ausgewählt werden. Beim vierten Dienstbereich besteht eine gemeinsame Abhängigkeit (als Microsoft 365 Common und Office bezeichnet); er muss immer über Netzwerkkonnektivität verfügen.

Dies sind die dargestellten Datenspalten:

- **ID**: Die ID-Nummer der Zeile, auch als Endpunktsatz bezeichnet. Dies ist die ID, die auch vom Webdienst für den Endpunktsatz zurückgegeben wird.

- **Kategorie**: Zeigt, ob der Endpunktsatz als "Optimize" (Optimieren), "Allow" (Zulassen) oder "Default" (Standard) kategorisiert ist. Informationen zu diesen Kategorien und eine Anleitung zu ihrer Verwaltung finden Sie unter [https://aka.ms/pnc](./microsoft-365-network-connectivity-principles.md). In dieser Spalte sind außerdem die Endpunktsätze aufgelistet, die für Netzwerkkonnektivität erforderlich sind. Für Endpunktsätze, für die keine Netzwerkkonnektivität erforderlich ist, geben wir in diesem Feld Anmerkungen, aus denen hervorgeht, welche Funktionalität durch ein Blockieren des Endpunktsatzes entfallen würde. Wenn Sie einen gesamten Dienstbereich ausschließen, ist für dessen als erforderlich aufgeführte Endpunktsätze keine Konnektivität erforderlich.

- **ER:** Dies ist **Ja,** wenn der Endpunktsatz über Azure ExpressRoute mit Office 365 Routenpräfixen unterstützt wird. Die BGP-Community, die die angezeigten Routenpräfixe enthält, richtet sich nach dem aufgeführten Servicebereich. Wenn ER **"Nein"** ist, bedeutet dies, dass ExpressRoute für diesen Endpunktsatz nicht unterstützt wird. Es sollte jedoch nicht davon ausgegangen werden, dass keine Routen für einen Endpunktsatz angekündigt werden, bei dem ER **"Nein"** ist. Wenn Sie beabsichtigen, Azure AD Verbinden zu verwenden, lesen Sie den Abschnitt mit [den besonderen Überlegungen,](/azure/active-directory/hybrid/reference-connect-instances#microsoft-azure-government) um sicherzustellen, dass Sie über die entsprechende Azure AD-Verbinden konfiguration verfügen.

- **Adressen**: Listet die FQDNs oder Platzhalter-Domänennamen und IP-Adressbereiche für den Endpunktsatz auf. Beachten Sie, dass IP-Adressbereiche im CIDR-Format angegeben sind und viele Einzel-IP-Adressen im angegebenen Netzwerk einschließen können.

- **Ports**: Listet die TCP- oder UDP-Ports auf, die zusammen mit den Adressen die Netzwerkendpunkte bilden. Wenn verschiedene Ports aufgeführt sind, fallen Ihnen möglicherweise Doppelungen bei den IP-Adressbereichen auf.

[!INCLUDE [Office 365 U.S. Government GCC High endpoints](../includes/office-365-u.s.-government-gcc-high-endpoints.md)]

Hinweise zu dieser Tabelle:

- Das Security and Compliance Center (SCC) bietet Unterstützung für Azure ExpressRoute für Office 365. Das gleiche gilt für viele Features, die über die SCC verfügbar gemacht werden, z. B. Berichterstellung, Überwachung, Advanced eDiscovery, einheitliche DLP und Datengovernance. Zwei spezifische Features, PST-Import und eDiscovery-Export, unterstützen Azure ExpressRoute aufgrund ihrer Abhängigkeit von Azure Blob Storage derzeit nicht mit nur Office 365 Routenfiltern. Um diese Features nutzen zu können, benötigen Sie separate Konnektivität zu Azure Blob Storage mit allen unterstützten Azure-Konnektivitätsoptionen, einschließlich Internetkonnektivität oder Azure ExpressRoute mit Azure Public Route-Filtern. Sie müssen die Einrichtung einer solchen Konnektivität für beide Features auswerten. Das Office 365 Information Protection-Team ist sich dieser Einschränkung bewusst und arbeitet aktiv daran, Unterstützung für Azure ExpressRoute für Office 365 zu bieten, die auf Office 365 Routenfilter für beide Features beschränkt ist.

- Es gibt zusätzliche optionale Endpunkte für Microsoft 365 Apps for Enterprise, die nicht aufgeführt sind und nicht erforderlich sind, damit Benutzer Microsoft 365 Apps for Enterprise Anwendungen starten und Dokumente bearbeiten können. Optionale Endpunkte werden in Microsoft-Rechenzentren gehostet und verarbeiten, übertragen oder speichern keine Kundendaten. Es wird empfohlen, dass Benutzerverbindungen zu diesen Endpunkten an den standardmäßigen Internetausgangsperimeter weitergeleitet werden.
