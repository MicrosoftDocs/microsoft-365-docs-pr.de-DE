---
title: Office 365 US-Regierung gcc High Endpoint
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/28/2020
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
description: In diesem Artikel finden Sie Endpunkte, die für Kunden mit Office 365 US Government gcc High Plans erreichbar sind.
hideEdit: true
ms.openlocfilehash: 6c7424b487f107d1459996ac9ee6e880e11b08c5
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690296"
---
# <a name="office-365-us-government-gcc-high-endpoints"></a>Office 365 US-Regierung gcc High Endpoint

 *Gilt für: Office 365 Administrator*

Für Office 365 ist eine Verbindung mit dem Internet erforderlich. Die folgenden Endpunkte sollten für Kunden erreichbar sein, die nur Office 365 US-Regierung gcc High Plans verwenden.
  
 **Office 365-Endpunkte:** [Weltweit (einschließlich GCC)](urls-and-ip-address-ranges.md) | [Office 365, betrieben von 21Vianet](urls-and-ip-address-ranges-21vianet.md)  | [Office 365 Deutschland](microsoft-365-germany-endpoints.md)  | [Office 365 U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md) | *Office 365 U.S. Government GCC High* |
  
|||
|:-----|:-----|
|**Letzte Aktualisierung:** 07/28/2020- ![ RSS- ](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Änderungsprotokoll Abonnement](https://endpoints.office.com/version/USGOVGCCHigh?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |**Download:** die vollständige Liste im [JSON-Format](https://endpoints.office.com/endpoints/USGOVGCCHigh?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) <br/> |

 Beginnen Sie mit der [Verwaltung Office 365 Endpunkte](managing-office-365-endpoints.md) , um unsere Empfehlungen für die Verwaltung der Netzwerkkonnektivität mithilfe dieser Daten zu verstehen. Endpunkte-Daten werden zu Beginn jedes Monats mit neuen IP-Adressen und URLs aktualisiert, die 30 Tage vor der aktiven Veröffentlichung veröffentlicht wurden. Auf diese Weise können Kunden, die noch nicht über automatisierte Updates verfügen, Ihre Prozesse abschließen, bevor neue Verbindungen erforderlich sind. Endpunkte können auch während des Monats bei Bedarf aktualisiert werden, um Support Eskalationen, Sicherheitsvorfälle oder andere unmittelbare betriebliche Anforderungen zu beheben. Die auf dieser Seite unten gezeigten Daten werden aus den Rest-basierten Webdiensten generiert. Wenn Sie für den Zugriff auf diese Daten ein Skript oder ein Netzwerkgerät verwenden, sollten Sie direkt zum [Webdienst](microsoft-365-ip-web-service.md) wechseln.

In den Endpunktdaten unten sind Anforderungen für Netzwerkkonnektivität zwischen dem Computer eines Benutzers und Office 365 aufgelistet. Sie umfassen keine Netzwerkverbindungen von Microsoft mit einem Kundennetzwerk, manchmal auch als hybride oder eingehende Netzwerkverbindungen bezeichnet.

Die Endpunkte sind in vier Dienstbereichen zusammengefasst. Die ersten drei Dienstbereiche können zu Konnektivitätszwecken unabhängig voneinander ausgewählt werden. Beim vierten Dienstbereich besteht eine gemeinsame Abhängigkeit (als Microsoft 365 Common und Office bezeichnet); er muss immer über Netzwerkkonnektivität verfügen.

Dies sind die dargestellten Datenspalten:

- **ID**: Die ID-Nummer der Zeile, auch als Endpunktsatz bezeichnet. Dies ist die ID, die auch vom Webdienst für den Endpunktsatz zurückgegeben wird.

- **Kategorie**: Zeigt, ob der Endpunktsatz als "Optimize" (Optimieren), "Allow" (Zulassen) oder "Default" (Standard) kategorisiert ist. Informationen zu diesen Kategorien und eine Anleitung zu ihrer Verwaltung finden Sie unter [https://aka.ms/pnc](https://aka.ms/pnc). In dieser Spalte sind außerdem die Endpunktsätze aufgelistet, die für Netzwerkkonnektivität erforderlich sind. Für Endpunktsätze, für die keine Netzwerkkonnektivität erforderlich ist, geben wir in diesem Feld Anmerkungen, aus denen hervorgeht, welche Funktionalität durch ein Blockieren des Endpunktsatzes entfallen würde. Wenn Sie einen gesamten Dienstbereich ausschließen, ist für dessen als erforderlich aufgeführte Endpunktsätze keine Konnektivität erforderlich.

- **Er**: Dies ist **Ja** , wenn der Endpunkt Satz über Azure Express Route mit Office 365-Routen Präfixen unterstützt wird. Die BGP-Community, die die angegebenen Routen Präfixe enthält, wird mit dem angegebenen Dienstbereich ausgerichtet. Wenn er **Nein**ist, bedeutet dies, dass Express Route für diese endpunktgruppe nicht unterstützt wird. Es sollte jedoch nicht davon ausgegangen werden, dass keine Routen für einen Endpunkt festgelegt werden, in dem er **nicht ist.** Wenn Sie Azure AD Connect verwenden möchten, lesen Sie den [Abschnitt spezielle Überlegungen](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-instances#microsoft-azure-government) , um sicherzustellen, dass Sie über die entsprechende Azure AD Connect-Konfiguration verfügen.

- **Adressen**: Listet die FQDNs oder Platzhalter-Domänennamen und IP-Adressbereiche für den Endpunktsatz auf. Beachten Sie, dass IP-Adressbereiche im CIDR-Format angegeben sind und viele Einzel-IP-Adressen im angegebenen Netzwerk einschließen können.
 
- **Ports**: Listet die TCP- oder UDP-Ports auf, die zusammen mit den Adressen die Netzwerkendpunkte bilden. Wenn verschiedene Ports aufgeführt sind, fallen Ihnen möglicherweise Doppelungen bei den IP-Adressbereichen auf.
 
[!INCLUDE [Office 365 U.S. Government GCC High endpoints](../includes/office-365-u.s.-government-gcc-high-endpoints.md)]

Hinweise zu dieser Tabelle:

- Das Security and Compliance Center (SCC) bietet Unterstützung für Azure Express Route für Office 365. Gleiches gilt für viele Features, die über den SCC verfügbar gemacht werden, wie Berichterstellung, Überwachung, erweiterte eDiscovery, Unified DLP und Datensteuerung. Zwei spezifische Features, PST-Import und eDiscovery-Export, unterstützen derzeit keine Azure-Express Route mit nur Office 365 Routenfiltern aufgrund ihrer Abhängigkeit von Azure-BLOB-Speicher. Um diese Funktionen nutzen zu können, benötigen Sie eine separate Konnektivität mit Azure-BLOB-Speicher mithilfe aller unterstützenden Azure-Verbindungsoptionen, einschließlich Internet Konnektivität oder Azure Express Route mit Azure Public Route Filters. Sie müssen die Einrichtung einer solchen Konnektivität für diese beiden Features auswerten. Das Team für Office 365 Information Protection kennt diese Einschränkung und arbeitet aktiv an der Unterstützung von Azure Express Route für Office 365, die auf Office 365 Routenfilter für beide Features beschränkt sind.

- Es gibt zusätzliche optionale Endpunkte für Microsoft 365-Apps für Unternehmen, die nicht aufgeführt sind und für Benutzer nicht erforderlich sind, um Microsoft 365-Apps für Enterprise-Anwendungen zu starten und Dokumente zu bearbeiten. Optionale Endpunkte werden in Microsoft-Rechenzentren gehostet und verarbeiten, übertragen oder speichern keine Kundendaten. Es wird empfohlen, dass Benutzer Verbindungen mit diesen Endpunkten an den standardmäßigen Internet Ausgangs Perimeter weitergeleitet werden.

