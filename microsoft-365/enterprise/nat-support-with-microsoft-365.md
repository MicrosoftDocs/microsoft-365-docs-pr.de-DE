---
title: NAT-Unterstützung mit Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/24/2017
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: 170e96ea-d65d-4e51-acac-1de56abe39b9
description: Dieser Artikel enthält Details zur Ungefährung der Anzahl der Clients, die Sie pro IP-Adresse in Ihrer Organisation mithilfe von NAT verwenden können.
ms.openlocfilehash: f48874853c3acb80927933761862b14379b6d4bd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690280"
---
# <a name="nat-support-with-office-365"></a>NAT-Unterstützung mit Office 365

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Zuvor wurde empfohlen, dass die maximale Anzahl von Exchange Clients, die Sie pro IP-Adresse verwenden sollten, um eine Verbindung mit Office 365 herzustellen, ca. 2.000 Clients pro Netzwerkport war.
  
## <a name="why-use-nat"></a>Warum NAT verwenden?

Mithilfe von NAT können Tausende von Personen in einem Unternehmensnetzwerk einige öffentlich routingfähige IP-Adressen "freigeben".
  
Die meisten Unternehmensnetzwerke verwenden privaten (RFC1918)-IP-Adressraum. Der private Adressraum wird von der IANA (Internet Assigned Numbers Authority) zugewiesen und ist ausschließlich für Netzwerke vorgesehen, die nicht direkt zum und vom globalen Internet geroutet werden.
  
Um Den Internetzugriff auf Geräte in einem privaten IP-Adressraum zu ermöglichen, verwenden Organisationen Gatewaytechnologien wie Firewalls und Proxys, die Netzwerkadressenübersetzungsdienste (Network Address Translation, NAT) oder Portadressenübersetzungsdienste (Port Address Translation, PAT) bereitstellen. Diese Gateways sorgen dafür, dass Datenverkehr von internen Geräten zum Internet (einschließlich Office 365) von einer oder mehreren öffentlich routingbaren IP-Adressen kommt. Jede ausgehende Verbindung von einem internen Gerät wird in einen anderen Quell-TCP-Port für die öffentliche IP-Adresse übersetzt. 
  
## <a name="why-do-you-need-to-have-so-many-connections-open-to-office-365-at-the-same-time"></a>Warum müssen so viele Verbindungen gleichzeitig für Office 365 geöffnet sein?

Outlook können acht oder mehr Verbindungen öffnen (in Situationen, in denen Add-Ins, freigegebene Kalender, Postfächer usw. enthalten sind). Da auf einem Windows-basierten NAT-Gerät maximal 64.000 Ports verfügbar sind, können maximal 8.000 Benutzer hinter einer IP-Adresse stehen, bevor die Ports ausgeschöpft sind. Beachten Sie, dass, wenn Kunden nicht Windows betriebssystembasierte Geräte für NAT verwenden, die insgesamt verfügbaren Ports davon abhängen, welches NAT-Gerät oder welche Software verwendet wird. In diesem Szenario kann die maximale Anzahl von Ports unter 64.000 sein. Die Verfügbarkeit von Ports wird auch durch andere Faktoren beeinflusst, z. B. Windows die Beschränkung von 4.000 Ports für die eigene Verwendung, wodurch die Gesamtzahl der verfügbaren Ports auf 60.000 reduziert wird. Möglicherweise gibt es andere Anwendungen, z. B. Internet Explorer, die gleichzeitig eine Verbindung herstellen können, was zusätzliche Ports erfordert.
  
## <a name="calculating-maximum-supported-devices-behind-a-single-public-ip-address-with-office-365"></a>Berechnen der maximal unterstützten Geräte hinter einer einzelnen öffentlichen IP-Adresse mit Office 365

Um die maximale Anzahl von Geräten hinter einer einzelnen öffentlichen IP-Adresse zu ermitteln, sollten Sie den Netzwerkdatenverkehr überwachen, um den Spitzenportverbrauch pro Client zu ermitteln. Außerdem sollte ein Spitzenfaktor für die Portnutzung (mindestens 4) verwendet werden. 
  
 **Verwenden Sie die folgende Formel, um die Anzahl der unterstützten Geräte pro IP-Adresse zu berechnen:**
  
Maximal unterstützte Geräte hinter einer einzelnen öffentlichen IP-Adresse = (64.000 - eingeschränkte Ports)/(Spitzenportverbrauch + Spitzenfaktor)
  
 **Wenn beispielsweise Folgendes zutrifft:**
  
- **Eingeschränkte Ports:** 4.000 für das Betriebssystem

- **Spitzenportverbrauch:** 6 pro Gerät

- **Spitzenfaktor:** 4

Dann werden die maximal unterstützten Geräte hinter einer einzelnen öffentlichen IP-Adresse = (64.000 - 4.000)/(6 + 4) = 6.000
  
Mit der Veröffentlichung von Office 365 Hosting Pack, die in den Updates von September 2011 für Microsoft Office Outlook 2007 oder November 2011 für Microsoft Outlook 2010 oder einem späteren Update enthalten ist, kann die Anzahl der Verbindungen von Outlook (beide Office Outlook 2007 mit Service Pack 2 und Outlook 2010) bis Exchange bis zu 2 sein. Sie müssen die verschiedenen Betriebssysteme, Benutzerverhaltensmuster und so weiter einbezahlen, um die minimale und maximale Anzahl von Ports zu ermitteln, die Ihr Netzwerk in Spitzenzeiten benötigt.
  
Wenn Sie mehr Geräte hinter einer einzelnen öffentlichen IP-Adresse unterstützen möchten, führen Sie die beschriebenen Schritte aus, um die maximale Anzahl unterstützter Geräte zu bewerten:
  
Überwachen Sie den Netzwerkdatenverkehr, um den Spitzenportverbrauch pro Client zu ermitteln. Sie sollten diese Daten sammeln:
  
- Von mehreren Standorten
    
- Von mehreren Geräten
    
- Mehrmals
    
Verwenden Sie die vorstehende Formel, um die maximalen Benutzer pro IP-Adresse zu berechnen, die in ihrer Umgebung unterstützt werden können.
  
Es gibt verschiedene Methoden zum Verteilen der Clientlast über zusätzliche öffentliche IP-Adressen. Verfügbare Strategien hängen von den Funktionen der Unternehmensgatewaylösung ab. Die einfachste Lösung besteht in der Segmentierung des Benutzeradressenraums und dem statischen "Zuweisen" einer Reihe von IP-Adressen zu jedem Gateway. Eine weitere Alternative, die viele Gatewaygeräte bieten, ist die Möglichkeit, einen Pool mit IP-Adressen zu verwenden. Der Vorteil des Adresspools ist, dass er wesentlich dynamischer ist und weniger Wahrscheinlichkeit eine Anpassung erfordert, wenn Ihre Benutzerbasis wächst.
  
## <a name="see-also"></a>Siehe auch

[Verwalten von Office 365-Endpunkten](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Häufig gestellte Fragen zu Office 365-Endpunkten](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
