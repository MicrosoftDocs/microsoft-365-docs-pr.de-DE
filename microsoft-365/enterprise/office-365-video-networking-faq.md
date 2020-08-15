---
title: Häufig gestellte Fragen zu Office 365 Video Netzwerken
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
description: Hier finden Sie Antworten auf die am häufigsten gestellten Fragen zur Bandbreitenplanung, Verschlüsselung und &, wie der Dienst Inhalts Übermittlungs Netzwerke nutzt (CDNs).
ms.openlocfilehash: e08a67988290e7ead87ff30a5ebdf9c8560f4825
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695922"
---
# <a name="office-365-video-networking-frequently-asked-questions"></a>Häufig gestellte Fragen zu Office 365 Video Netzwerken

Die Office 365 Video-Repository und Streaming-Dienste machen das Speichern und Streaming von Videos in Ihrer Organisation einfach. Es gibt eine Menge toller [Informationen über Office 365 Video](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50); Diese häufig gestellten Fragen zur Netzwerkarbeit dienen der Beantwortung der am häufigsten gestellten Fragen rund um die Bandbreitenplanung, Verschlüsselung sowie darüber, wie der Dienst [Inhalts Bereitstellungs Netzwerke](content-delivery-networks.md) nutzt (CDNs).
  
Wenn Sie noch nicht wissen, was passiert, wenn ein Video hochgeladen oder wiedergegeben wird, schauen Sie sich dieses Video an, das wir zusammengestellt haben, [was mit einer Videodatei passiert, wenn Sie in Office 365 Video hochgeladen](https://www.youtube.com/watch?v=HXSZ0jYBKlM)wird.
  
## <a name="what-are-the-office-365-video-bandwidth-requirements"></a>Was sind die Anforderungen für die Office 365 Video Bandbreite?

Es gibt zahlreiche [Unterstützte Videoformate](https://support.office.com/article/dd1af01c-fd8e-4640-b17b-93ee02b9b817) , die in Office 365 hochgeladen werden können. Jede Videodatei wird dann in einem Standardformat mit verschiedenen videoqualitäten für die Wiedergabe codiert. In Office 365 Video wird das Streaming adaptiver Bitraten verwendet, um die beste Videowiedergabequalität basierend auf der verfügbaren Netzwerkbandbreite und-Größe des Video Players auszuwählen. Hierzu fordert der Player zunächst die niedrigste Wiedergabequalität an. Der Dienst beginnt dann, 2 Sekunden Videosegmente an den Video Player zu senden. Der Player kann dann eine höhere oder niedrigere Wiedergabequalität anfordern, je nachdem, wie schnell jedes Segment zugestellt wird.
  
Das Streaming der adaptiven Bitrate wird im Hintergrund ausgeführt, während das Video mit der geringsten Unterbrechung oder Pufferung abgespielt wird. Während der Videowiedergabe ermöglicht der Video Player dem Betrachter, die automatische Wiedergabequalität manuell außer Kraft zu setzen, um eine bestimmte Videowiedergabequalität auszuwählen.
  
Im folgenden finden Sie eine schnell Tabelle, in der die Netzwerkanforderungen für die einzelnen Videowiedergabe Qualitäten erläutert werden. Die minimale Bandbreite pro Person, die für die Wiedergabe eines Videos benötigt wird, ist 802Kbps.
  
| Wiedergabequalität | Netzwerkgeschwindigkeit |
|:-----|:-----|
|288p  <br/> |802Kbps  <br/> |
|360p  <br/> |1,2 Mbit/s  <br/> |
|576p  <br/> |2,5 MBit/s  <br/> |
|720p  <br/> |3,8 Mbit/s  <br/> |

([Zurück zum Seitenanfang](office-365-video-networking-faq.md))
  
## <a name="how-do-content-delivery-networks-cdns-help-video-playback"></a>Wie helfen Inhalts Zustellungs Netzwerke (CDNs) bei der Videowiedergabe?

Wenn mehrere Personen derselben Organisation innerhalb desselben geografischen Standorts dasselbe Video (n) streamen, speichert CDNs eine Kopie dieser Videos an einem Ort, der sich näher an dieser geografischen Region befindet. Wenn das Video gespeichert oder am nächstgelegenen Ort zwischengespeichert wurde, strömt jede Person das Video von dem Standort aus, der Ihnen am nächsten liegt, anstatt an einem weiteren Standort. Office 365 Video verwendet Azure Media-Dienste, um zu verwalten, was in der Azure-CDNs zwischengespeichert ist, und wie lange. Azure Media-Dienste können alle [Azure CDN-Speicherorte](https://azure.microsoft.com/documentation/articles/cdn-pop-locations/) verwenden, um Videofragmente und Manifeste für ein paar Tage zwischenzuspeichern. Wenn Personen in Ihrer Organisation weiterhin die zwischengespeicherten Videos ansehen, bleiben Sie im Cache. Wenn mehrere Tage lang kein Zugriff auf das Video erfolgt, wird das Video schließlich aus dem Cache gelöscht. Das nächste Mal, wenn jemand versucht, das Video anzusehen, wird es erneut am nächsten CDN-Standort zwischengespeichert.
  
Jeder, der versucht, das Video anzusehen, während der Inhalt in einem nahe gelegenen CDN zwischengespeichert wird, profitiert davon, dass das Video näher und in den meisten Fällen weniger Hops entfernt ist. Dies verbessert die Wiedergabegeschwindigkeit für Videos; die Netzwerkanforderung wird jedoch nicht geändert, um das Video wiederzugeben.
  
> [!NOTE]
> Es gibt einige Umstände, wie etwa unsere Kapazitätsgrenze erreicht wird, wo das Video entfernt werden kann, bevor die drei Tage erreicht wurde.
  
([Zurück zum Seitenanfang](office-365-video-networking-faq.md))
  
## <a name="can-i-cache-the-videos-locally-for-faster-playback"></a>Kann ich die Videos lokal zwischenspeichern, um eine schnellere Wiedergabe zu erhalten?

Ja. Office 365 hindert Sie nicht daran, einen lokalen CDN oder einen Caching-Proxy zu verwenden, um Video-oder andere Office 365 Inhalte für einen schnelleren Zugriff in Ihr lokales Netzwerk zu integrieren. Es gibt verschiedene Möglichkeiten, eine lokale zwischen Speicherungs Lösung in Ihrem Netzwerk zu implementieren, die gängigste Methode ist die Verwendung einer Proxy Lösung, mit der Inhalte lokal zwischengespeichert werden. Nachdem ein Proxy oder ein privates CDN die Videofragmente und-Manifeste zwischengespeichert hat, werden zukünftige Anforderungen für die Dateien, die über den Proxy oder das private CDN weitergeleitet werden, aus dem lokalen Cache abgerufen und nicht von einem Internetstandort abgerufen. Betrachten Sie die Netzwerkbandbreite, Kapazität und Videowiedergabe Parallelität bei der Planung einer solchen Lösung.
  
([Zurück zum Seitenanfang](office-365-video-networking-faq.md))
  
## <a name="how-videos-are-encrypted-and-secured"></a>Wie werden Videos verschlüsselt und gesichert?

Office 365 Video weiß, wie wichtig es ist, Ihre Daten sicher und privat zu halten. [Microsoft Trust Center](https://products.office.com/business/office-365-trust-center-welcome) beschreibt unser Engagement für den Datenschutz und die Sicherheit Ihrer Inhalte. Bei der Videowiedergabe ist die Geschwindigkeit wichtig für eine gute Erfahrung; Allerdings gefährden wir Ihre Sicherheit oder Ihren Datenschutz in Exchange für die Geschwindigkeit nicht. Hier erfahren Sie, wie wir Geschwindigkeit, Sicherheit und Datenschutz berücksichtigen.
  
Wenn Sie oder eine Person in Ihrer Organisation ein neues Video hochladen, wird dieses Video transcodiert, mit AES-128-Verschlüsselung verschlüsselt und in Azure Media Services gespeichert. Dies bedeutet, dass die Videos sowohl in Transit als auch in Ruhe verschlüsselt sind.
  
Wenn jemand in Ihrer Organisation versucht, ein neues Video anzusehen, führen Sie die folgenden Schritte aus:
  
1. Fragen Sie SharePoint Online, ob Sie über die Berechtigung zum Anzeigen des Videos verfügen.

2. SharePoint Online verwendet die Dateiberechtigungen, um festzustellen, ob die Person das Video ansehen kann.

3. Wenn diese zulässig sind, ruft SharePoint Online ein Token aus Azure ab, das dem Video Player zur Verfügung steht.

4. Der Video Player verwendet dann das Token, um den Entschlüsselungsschlüssel von Azure anzufordern.

5. Wenn der Entschlüsselungsschlüssel in der Hand ist, kann der Video Player das Video streamen.

![O365-Video Wiedergabe](../media/9d3c6e76-151d-48a3-a30e-ba8dd07db0b7.png)
  
([Zurück zum Seitenanfang](office-365-video-networking-faq.md))
  
## <a name="what-are-the-requirements-to-playback-office-365-video"></a>Was sind die Voraussetzungen für die Wiedergabe Office 365 Videos?

Office 365 von Video unterstützten Betriebssystemen und Webbrowsern entsprechen den SharePoint Online Anforderungen in [Office 365 Systemanforderungen](https://support.office.com/article/Office-365-system-requirements-719254c0-2671-4648-9c84-c6a3d4f3be45). Je nachdem, welches Betriebssystem und welche Webbrowserkonfiguration Sie haben, werden die spezifischen Anforderungen des Videoplayers bestimmt. Hier finden Sie weitere Informationen zu den Anforderungen für die [Videowiedergabe](https://support.office.com/article/ca1cc1a9-a615-46e1-b6a3-40dbd99939a6).
  
([Zurück zum Seitenanfang](office-365-video-networking-faq.md))
  
## <a name="i-cant-get-office-365-video-to-work-where-should-i-start"></a>Ich kann Office 365 Video nicht funktionieren, wo sollte ich beginnen?

Die Problembehandlung bei der Konnektivität mit Office 365 Video umfasst die Problembehandlung in Ihrem Netzwerk, in ihren Internetdienstanbietern und in der Konfiguration von Office 365. Der erste Anlaufpunkt ist das Service-Integritäts Dashboard. Dadurch wird Ihnen mitgeteilt, dass Office 365 Video ein Problem hat oder nicht. Wenn alles gut aussieht, gibt es hier einige zusätzliche Ressourcen, die Ihnen helfen.
  
- Stellen Sie sicher, dass Sie eine Verbindung mit den [für Office 365 Video erforderlichen Netzwerkendpunkten](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)herstellen können.

- Überprüfen Sie Ihre Netzwerkkonnektivität mit unserem [Office 365 Network Troubleshooting Guide](https://support.office.com/article/Office-365-performance-tuning-and-troubleshooting-Admin-and-IT-Pro-1492cb94-bd62-43e6-b8d0-2a61ed88ebae).

- Sehen Sie [sich unsere bewährten Methoden für die Verwendung von Office 365 in einem langsamen Netzwerk an](https://support.office.com/article/Best-practices-for-using-Office-365-on-a-slow-network-fd16c8d2-4799-4c39-8fd7-045f06640166).

- [Hier finden Sie Hilfe zu Office 365 Video Konfiguration](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50).

([Zurück zum Seitenanfang](office-365-video-networking-faq.md))
  
## <a name="office-365-video-resources"></a>Office 365 von Video Ressourcen

Im folgenden finden Sie einige weitere Ressourcen, die Sie bei der erfolgreichen Bereitstellung und Verwendung Office 365 Videos unterstützen:
  
[Hilfe zu Office 365 Video Konfiguration finden](https://support.office.com/article/Find-help-about-Office-365-Video-b435f99a-f47e-4ebd-a946-f5c965844f50)
  
[Erkunden von Office 365 Video](https://support.office.com/article/Meet-Office-365-Video-ca1cc1a9-a615-46e1-b6a3-40dbd99939a6)
  
[Erstellen und Verwalten eines Kanals in Office 365 Video](https://support.office.com/article/Create-and-manage-a-channel-in-Office-365-Video-1fede4cc-13c0-435a-b585-e7fbf1c83bb2)
  
[Verwalten Ihres Office 365 Video-Portals](https://support.office.com/article/Manage-your-Office-365-Video-portal-c059465b-eba9-44e1-b8c7-8ff7793ff5da)
  
[Videoformate, die in Office 365 Video funktionieren](https://support.office.com/article/Video-formats-that-work-in-Office-365-Video-dd1af01c-fd8e-4640-b17b-93ee02b9b817)
  
([Zurück zum Seitenanfang](office-365-video-networking-faq.md))
  
Mit diesem kurzen Link gelangen Sie wieder hierher zurück: [https://aka.ms/video365networkfaq](https://aka.ms/video365networkfaq)
