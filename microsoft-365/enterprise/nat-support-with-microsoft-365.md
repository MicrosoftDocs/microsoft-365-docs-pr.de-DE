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
description: In diesem Artikel erfahren Sie, wie Sie die Anzahl der Clients, die pro IP-Adresse in Ihrer Organisation verwendet werden können, mithilfe von NAT annähernd annähern.
ms.openlocfilehash: f48874853c3acb80927933761862b14379b6d4bd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690280"
---
# <a name="nat-support-with-office-365"></a>NAT-Unterstützung mit Office 365

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Früher wurde vorgeschlagen, dass die maximale Anzahl von Exchange-Clients, die Sie pro IP-Adresse verwenden sollten, zum Herstellen einer Verbindung mit Office 365 etwa 2.000 Clients pro Netzwerkport war.
  
## <a name="why-use-nat"></a>Gründe für die Verwendung von NAT

Durch die Verwendung von NAT können Tausende von Personen in einem Unternehmensnetzwerk einige öffentlich routingfähige IP-Adressen "freigeben".
  
Die meisten Unternehmensnetzwerke verwenden privaten (RFC1918)-IP-Adressraum. Privater Adressraum wird von der IANA (Internet Assigned Numbers Authority) zugewiesen und ausschließlich für Netzwerke bestimmt, die nicht direkt ins und aus dem globalen Internet weitergeleitet werden.
  
Um Internet Zugriff auf Geräte in einem privaten IP-Adressraum bereitzustellen, verwenden Organisationen Gateway-Technologien wie Firewalls und Proxys, die Netzwerkadressübersetzung (NAT) oder Pat-Dienste (Port Address Translation) bereitstellen. Diese Gateways führen dazu, dass der Datenverkehr von internen Geräten zum Internet (einschließlich Office 365) von einer oder mehreren öffentlich routingfähigen IP-Adressen stammt. Jede ausgehende Verbindung von einem internen Gerät wird in einen anderen Quell-TCP-Port für die öffentliche IP-Adresse übersetzt. 
  
## <a name="why-do-you-need-to-have-so-many-connections-open-to-office-365-at-the-same-time"></a>Warum müssen so viele Verbindungen für Office 365 gleichzeitig geöffnet sein?

Outlook kann acht oder mehr Verbindungen öffnen (in Situationen, in denen Add-Ins, freigegebene Kalender, Postfächer usw. vorhanden sind). Da auf einem Windows-basierten NAT-Gerät maximal 64.000 Ports verfügbar sind, können maximal 8.000 Benutzer hinter einer IP-Adresse stehen, bevor die Ports erschöpft sind. Beachten Sie, dass die verfügbaren Ports je nachdem, welche NAT-Geräte oder-Software verwendet wird, wenn Kunden nicht-Windows-Betriebssystembasierte Geräte für NAT verwenden. In diesem Szenario kann die maximale Anzahl von Ports kleiner als 64.000 sein. Die Verfügbarkeit von Ports ist auch von anderen Faktoren betroffen, beispielsweise von Windows, die 4.000-Ports für die eigene Verwendung einschränken, wodurch die Gesamtzahl der verfügbaren Ports auf 60.000 reduziert wird. Es gibt möglicherweise andere Anwendungen wie Internet Explorer, die gleichzeitig eine Verbindung herstellen können und zusätzliche Ports erfordern.
  
## <a name="calculating-maximum-supported-devices-behind-a-single-public-ip-address-with-office-365"></a>Berechnen der maximal unterstützten Geräte hinter einer einzelnen öffentlichen IP-Adresse mit Office 365

Um die maximale Anzahl von Geräten hinter einer einzelnen öffentlichen IP-Adresse zu ermitteln, sollten Sie den Netzwerkdatenverkehr überwachen, um den maximalen Port Verbrauch pro Client zu ermitteln. Außerdem sollte ein Spitzen Faktor für die Port Nutzung (mindestens 4) verwendet werden. 
  
 **Verwenden Sie die folgende Formel, um die Anzahl unterstützter Geräte pro IP-Adresse zu berechnen:**
  
Maximal unterstützte Geräte hinter einer einzelnen öffentlichen IP-Adresse = (64.000-eingeschränkte Ports)/(Spitzen Port Verbrauch + Spitzen Faktor)
  
 **Wenn beispielsweise Folgendes zutrifft:**
  
- **Eingeschränkte Ports:** 4.000 für das Betriebssystem

- **Maximaler Port Verbrauch:** 6 pro Gerät

- **Spitzen Faktor:** 4

Anschließend werden die maximal unterstützten Geräte hinter einer einzelnen öffentlichen IP-Adresse = (64.000-4000)/(6 + 4) = 6.000
  
Mit der Veröffentlichung von Office 365 Hosting Pack, das in den Updates vom September 2011 für Microsoft Office Outlook 2007 oder November 2011 für Microsoft Outlook 2010 oder ein höheres Update enthalten ist, kann die Anzahl der Verbindungen von Outlook (beide Office Outlook 2007 mit Service Pack 2 und Outlook 2010) so gering wie 2 sein. Sie müssen die unterschiedlichen Betriebssysteme, Benutzerverhalten usw. berücksichtigen, um die Mindest-und Höchstzahl der Ports zu ermitteln, die für Ihr Netzwerk am Höhepunkt benötigt werden.
  
Wenn Sie weitere Geräte hinter einer einzelnen öffentlichen IP-Adresse unterstützen möchten, führen Sie die folgenden Schritte aus, um die maximale Anzahl von Geräten zu bewerten, die unterstützt werden können:
  
Überwachen Sie den Netzwerkdatenverkehr, um den maximalen Port Verbrauch pro Client zu ermitteln. Sie sollten diese Daten sammeln:
  
- Von mehreren Standorten
    
- Von mehreren Geräten
    
- Mehrmals
    
Verwenden Sie die obige Formel, um die maximalen Benutzer pro IP-Adresse zu berechnen, die in Ihrer Umgebung unterstützt werden können.
  
Es gibt verschiedene Methoden für die Verteilung der Clientlast auf zusätzliche öffentliche IP-Adressen. Verfügbare Strategien hängen von den Funktionen der Unternehmens Gateway-Lösung ab. Die einfachste Lösung besteht darin, den Benutzeradressraum zu segmentieren und jedem Gateway statisch eine Reihe von IP-Adressen zuzuweisen. Eine andere Alternative, die viele Gateway-Geräte bieten, ist die Möglichkeit, einen Pool von IP-Adressen zu verwenden. Der Vorteil des Adresspools liegt darin, dass er viel dynamischer ist und bei steigender Benutzerbasis weniger wahrscheinlich Anpassungen erfordert.
  
## <a name="see-also"></a>Siehe auch

[Verwalten von Office 365-Endpunkten](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Häufig gestellte Fragen zu Office 365-Endpunkten](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
