---
title: Häufig gestellte Fragen zu Office 365-Videonetzwerken
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 3/14/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 2bed67a1-4052-49ff-a4ce-b7e6530eb98e
ms.custom:
- Adm_O365
- seo-marvel-apr2020
description: Hier finden Sie Antworten auf einige der am häufigsten gestellten Fragen zur Bandbreitenplanung, Verschlüsselung und &, wie der Dienst Content Delivery Networks (CDNs) nutzt.
ms.openlocfilehash: 8bc0a69ff744967d24aa7d21ed6daee1a839f159
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921570"
---
# <a name="office-365-video-networking-frequently-asked-questions"></a>Häufig gestellte Fragen zu Office 365-Videonetzwerken

Das Office 365-Videorepository und Streamingdienste machen das Speichern und Streamen von Videos in Ihrer Organisation einfach. Es gibt viele großartige Informationen [zu Office 365 Video;](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50) Diese Häufig gestellten Fragen zu Netzwerken sollen die häufigsten Fragen zur Bandbreitenplanung, Verschlüsselung und zur Nutzung von [Content Delivery Networks](content-delivery-networks.md) (CDNs) beantworten.
  
Wenn Sie noch nicht genau wissen, was passiert, wenn ein Video hochgeladen oder wieder abgespielt wird, sehen Sie sich dieses Video an, das wir 2013 2013 2013 2013 2014 2013 [365 Video](https://www.youtube.com/watch?v=HXSZ0jYBKlM)hochgeladen haben.
  
## <a name="what-are-the-office-365-video-bandwidth-requirements"></a>Welche Anforderungen gelten für die Office 365 Videobandbreite?

Es gibt zahlreiche unterstützte [Videoformate,](https://support.office.com/article/dd1af01c-fd8e-4640-b17b-93ee02b9b817) die in Office 365 hochgeladen werden können. Jede Videodatei wird dann in ein Standardformat mit verschiedenen Videoqualitäten für die Wiedergabe codiert. Office 365 Video verwendet adaptives Bitratenstreaming, um die beste Videowiedergabequalität basierend auf der verfügbaren Netzwerkbandbreite und Größe des Videoplayers auszuwählen. Dazu fordert der Spieler zunächst die niedrigste Wiedergabequalität an. Der Dienst beginnt dann mit dem Senden von 2-Sekunden-Videosegmenten an den Videoplayer. Der Spieler kann dann eine höhere oder niedrigere Wiedergabequalität anfordern, je nach der Art und Weise, wie schnell die einzelnen Segmente zugestellt werden.
  
Das adaptive Bitratestreaming macht all dies im Hintergrund, während das Video mit der geringsten Unterbrechung oder Pufferung abspielt. Während der Videowiedergabe kann der Videoplayer die automatische Wiedergabequalität manuell überschreiben, um eine bestimmte Videowiedergabequalität auszuwählen.
  
Im Folgenden finden Sie eine Kurze Tabelle, in der die Netzwerkanforderungen für die einzelnen Videowiedergabequalitäten aufgeführt sind. Die mindestbandbreite pro Person, die für die Wiedergabe eines Videos benötigt wird, beträgt 802 KBit/s.
  
| Wiedergabequalität | Netzwerkgeschwindigkeit |
|:-----|:-----|
|288p  <br/> |802 Kbps  <br/> |
|360p  <br/> |1,2 MBit/s  <br/> |
|576p  <br/> |2,5 MBit/s  <br/> |
|720p  <br/> |3,8 MBit/s  <br/> |

([Zurück nach oben](office-365-video-networking-faq.md))
  
## <a name="how-do-content-delivery-networks-cdns-help-video-playback"></a>Wie helfen Inhaltszustellungsnetzwerke (Content Delivery Networks, CDNs) bei der Videowiedergabe?

Wenn mehrere Personen aus derselben Organisation innerhalb desselben geografischen Standorts dieselben Videos streamen, speichern CDNs eine Kopie dieser Videos an einem Ort, der näher an dieser geografischen Region liegt. Wenn das Video gespeichert oder am nächstgelegenen Speicherort zwischengespeichert wird, streamt jede Person das Video vom nächstgelegenen Speicherort anstatt von einem weiter entfernten Ort. Office 365 Video verwendet Azure Media Services, um zu verwalten, was in den Azure CDNs zwischengespeichert wird und wie lange. Azure Media Services kann einen beliebigen [Azure CDN-Speicherort](/azure/cdn/cdn-pop-locations) zum Zwischenspeichern von Videofragmenten und Manifesten für einige Tage verwenden. Wenn Personen in Ihrer Organisation die zwischengespeicherten Videos weiterhin ansehen, bleiben sie im Cache. Wenn mehrere Tage lang niemand auf das Video zutritt, wird das Video schließlich aus dem Cache gelöscht. Beim nächsten Versuch, das Video zu sehen, wird es erneut am nächstgelegenen CDN-Speicherort zwischengespeichert.
  
Jeder, der versucht, das Video zu sehen, während der Inhalt in einem nahe gelegenen CDN zwischengespeichert wird, profitiert davon, dass das Video näher und in den meisten Fällen weniger Hops entfernt ist. Dadurch wird die Videowiedergabegeschwindigkeit verbessert. Die Netzwerkanforderung für die Wiedergabe des Videos wird jedoch nicht geändert.
  
> [!NOTE]
> Es gibt einige Umstände, z. B. das Erreichen unserer Kapazitätsgrenze, bei denen das Video möglicherweise entfernt wird, bevor die drei Tage erreicht sind.
  
([Zurück nach oben](office-365-video-networking-faq.md))
  
## <a name="can-i-cache-the-videos-locally-for-faster-playback"></a>Kann ich die Videos lokal zwischenspeichern, um die Wiedergabe zu beschleunigen?

Ja. Office 365 verhindert nicht, dass Sie ein lokales CDN oder einen Zwischenspeicherproxy verwenden, um Video- oder andere Office 365-Inhalte in Ihr lokales Netzwerk zu bringen, um schnelleren Zugriff zu erhalten. Es gibt mehrere Möglichkeiten, eine lokale Zwischenspeicherungslösung in Ihrem Netzwerk zu implementieren. Die gängigste Methode ist die Verwendung einer Proxylösung, die Inhalte lokal zwischenspeichert. Nachdem ein Proxy oder ein privates CDN die Videofragmente und Manifeste zwischengespeichert hat, werden zukünftige Anforderungen für dateien, die über den Proxy oder das private CDN geroutet werden, aus dem lokalen Cache und nicht von einem Internetspeicherort gezogen. Berücksichtigen Sie die Parallelität von Netzwerkbandbreite, Kapazität und Videowiedergabe bei der Planung einer Lösung wie dieser.
  
([Zurück nach oben](office-365-video-networking-faq.md))
  
## <a name="how-videos-are-encrypted-and-secured"></a>Wie werden Videos verschlüsselt und gesichert?

Office 365 Video weiß, wie wichtig es ist, Ihre Daten sicher und privat zu halten. [Microsoft Trust Center](https://products.office.com/business/office-365-trust-center-welcome) beschreibt unser Engagement für den Datenschutz und die Sicherheit Ihrer Inhalte. Bei der Videowiedergabe ist Geschwindigkeit wichtig für eine gute Erfahrung. Wir gehen jedoch nicht gegen Geschwindigkeit auf Ihre Sicherheit oder Ihren Datenschutz ein. Hier erfahren Sie, wie wir Geschwindigkeit, Sicherheit und Datenschutz gewährleisten.
  
Wenn Sie oder jemand in Ihrer Organisation ein neues Video hochlädt, wird dieses Video transcodiert, mit AES-128-Verschlüsselung verschlüsselt und in Azure Media Services gespeichert. Dies bedeutet, dass die Videos sowohl während der Übertragung als auch im Ruhebereich verschlüsselt werden.
  
Wenn jemand in Ihrer Organisation versucht, ein neues Video zu sehen, führen sie die folgenden Schritte aus:
  
1. Fragen Sie SharePoint Online, ob sie über die Berechtigung zum Anzeigen des Videos verfügen.

2. SharePoint Online verwendet die Dateiberechtigungen, um zu bestimmen, ob die Person das Video ansehen kann.

3. Wenn dies zulässig ist, ruft SharePoint Online ein Token aus Azure ab, das dem Videoplayer zur Verfügung gestellt wird.

4. Der Videoplayer verwendet dann das Token, um den Entschlüsselungsschlüssel von Azure an anfordern.

5. Mit dem Entschlüsselungsschlüssel kann der Videoplayer das Video streamen.

![O365 Videowiedergabe](../media/9d3c6e76-151d-48a3-a30e-ba8dd07db0b7.png)
  
([Zurück nach oben](office-365-video-networking-faq.md))
  
## <a name="what-are-the-requirements-to-playback-office-365-video"></a>Welche Anforderungen gelten für die Wiedergabe von Office 365 Video?

Office 365 Video unterstützte Betriebssysteme und Webbrowser entsprechen den SharePoint Online-Anforderungen in [Office 365-Systemanforderungen.](https://support.office.com/article/Office-365-system-requirements-719254c0-2671-4648-9c84-c6a3d4f3be45) Je nachdem, welches Betriebssystem und welche Webbrowserkonfiguration Sie haben, bestimmen Sie die spezifischen Anforderungen des Videoplayers. Hier finden Sie weitere Informationen zu den [Anforderungen für die Videowiedergabe.](https://support.office.com/article/ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)
  
([Zurück nach oben](office-365-video-networking-faq.md))
  
## <a name="i-cant-get-office-365-video-to-work-where-should-i-start"></a>Ich kann office 365-Video nicht zur Arbeit erhalten, wo soll ich beginnen?

Die Problembehandlung bei der Konnektivität mit Office 365 Video umfasst die Problembehandlung ihres Netzwerks, Ihrer ISP und Ihrer Konfiguration von Office 365. Der erste Start ist das Dienstintegashboard. Dies wird Ihnen mitteilen, dass Office 365 Video ein Problem hat oder nicht. Wenn dort alles gut aussieht, finden Sie hier einige zusätzliche Ressourcen, die Ihnen helfen.
  
- Stellen Sie sicher, dass Sie eine Verbindung mit den [für Office 365 Video erforderlichen Netzwerkendpunkten herstellen können.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)

- Überprüfen Sie Ihre Netzwerkkonnektivität mithilfe unseres [Office 365-Netzwerkbehandlungshandbuchs](https://support.office.com/article/Office-365-performance-tuning-and-troubleshooting-Admin-and-IT-Pro-1492cb94-bd62-43e6-b8d0-2a61ed88ebae).

- Sehen Sie [sich unsere bewährten Methoden für die Verwendung von Office 365 in einem langsamen Netzwerk an.](https://support.office.com/article/Best-practices-for-using-Office-365-on-a-slow-network-fd16c8d2-4799-4c39-8fd7-045f06640166)

- [Hier finden Sie Hilfe zur Office 365-Videokonfiguration.](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)

([Zurück nach oben](office-365-video-networking-faq.md))
  
## <a name="office-365-video-resources"></a>Office 365-Videoressourcen

Hier sind einige weitere Ressourcen, mit deren Hilfe Sie Office 365 Video erfolgreich bereitstellen und verwenden können:
  
[Hilfe zur Office 365-Videokonfiguration finden](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)
  
[Erkunden von Office 365 Video](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)
  
[Erstellen und Verwalten eines Kanals in Office 365 Video](https://support.office.com/article/Create-and-manage-a-channel-in-Office-365-Video-1fede4cc-13c0-435a-b585-e7fbf1c83bb2)
  
[Verwalten Ihres Office 365 Video-Portals](https://support.office.com/article/Manage-your-Office-365-Video-portal-c059465b-eba9-44e1-b8c7-8ff7793ff5da)
  
[Videoformate, die in Office 365 Video funktionieren](https://support.office.com/article/Video-formats-that-work-in-Office-365-Video-dd1af01c-fd8e-4640-b17b-93ee02b9b817)
  
([Zurück nach oben](office-365-video-networking-faq.md))
  
Mit diesem kurzen Link gelangen Sie wieder hierher zurück: [https://aka.ms/video365networkfaq]()