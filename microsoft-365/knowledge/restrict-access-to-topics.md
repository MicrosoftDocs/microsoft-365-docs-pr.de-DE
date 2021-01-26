---
title: Einschränken des Zugriffs auf Themen
description: So schließen Sie Themen aus, um zu verhindern, dass sie gefunden werden.
author: efrene
ms.author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-topics
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: f7e8406ee7090387d4500f69955330466f28c6c0
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976145"
---
# <a name="restrict-access-to-topics-in-topic-experiences"></a>Einschränken des Zugriffs auf Themen in Themenerfahrungen

In den Themenerfahrungen möchten Die Beteiligten in Ihrer Organisation möglicherweise sicherstellen, dass bestimmte Themen nicht ermittelt und für Ihre lizenzierten Benutzer verfügbar gemacht werden. Sie arbeiten beispielsweise an einem Projekt, zu dem Sie noch keine Informationen verfügbar machen möchten. Während Office 365-Berechtigungen für Websites, Dateien und andere Ressourcen Verhindern, dass Benutzer von Themenerfahrungen vertrauliche Informationen in Themen anzeigen, gibt es zusätzliche Sicherheitsvorkehrungen, um zu verhindern, dass bestimmte Themen jemals gefunden werden.

Während Wissensadministratoren die Einstellungen des Wissensnetzwerks steuern, um zu verhindern, dass Themen gefunden werden, müssen Wissensmanager und andere Beteiligte wissen, wie dies geschieht, damit sie gemeinsam daran arbeiten können.

> [!Important] 
> In diesem Artikel werden Möglichkeiten beschrieben, wie Sie verhindern können, dass Themen über KI identifiziert oder in Ihrer Umgebung als zusätzliche Sicherheitsvorkehrungen angezeigt werden. Es ist wichtig zu beachten, dass Benutzer in den Themenerfahrungen nichts in einem Thema anzeigen dürfen, auf das sie nicht über Office 365-Berechtigungen zugreifen dürfen. Auch wenn ein Benutzer ein Thema anzeigen kann, sind seine Dateien, Websites und Seiten, für die er keine Office 365-Berechtigungen zum Anzeigen hat, für sie nicht sichtbar. Stellen Sie sicher, dass Berechtigungen für vertrauliche Dateien ordnungsgemäß festgelegt sind, damit die Sicherheit gewährleistet ist.

## <a name="prevent-topics-from-being-identified"></a>Verhindern, dass Themen identifiziert werden

Der Wissensadministrator kann den Zugriff auf bestimmte Themen einschränken, indem er verhindert, dass sie bei der anfänglichen Indizierung gefunden werden. Es gibt zwei Möglichkeiten, dies in den Administratoreinstellungen des Knowledge Network im Microsoft 365 Admin Center zu tun.
 
- [Auswählen von SharePoint-Websites, die von der](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources)Themenermittlung ausgeschlossen werden: Sie können diese Einstellung verwenden, um zu verhindern, dass bestimmte SharePoint-Websites nach Themen gecrawlt werden.
- [Themen nach Namen ausschließen:](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name)Administratoren können diese Einstellung verwenden, um zu verhindern, dass bestimmte Themen nach Namen ermittelt werden. In den Administratoreinstellungen des Knowledge Network kann ein Administrator eine Liste von Themen hochladen, die in einer CSV-Datei ausgeschlossen werden sollen. Sie können Themen ausschließen, die genaue oder teilweise Übereinstimmungen mit einem Themennamen haben.

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a>Verhindern, dass Themen von bestimmten Benutzern angezeigt werden

Wissensadministratoren können auch [auswählen, wer Themen in Ihrer Organisation anzeigen kann.](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules) Mit dieser Einstellung können Sie auswählen, welche lizenzierten Benutzer alle Themen anzeigen können. In einer Pilotumgebung können Sie beispielsweise nur einer kleinen Gruppe von Benutzern erlauben, Themen anzeigen zu können.

## <a name="remove-topics-from-being-viewed"></a>Entfernen von Themen aus der Anzeige

Wissensmanager können Themen [entfernen,](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) damit Benutzer sie nicht mehr sehen können. Auf der **Seite "Themen verwalten"** im **Themencenter** können Knowledge Manager bestimmte Themen ablehnen, um zu verhindern, dass sie angezeigt werden. Themen können unabhängig davon entfernt werden, ob sie sich in einem vorgeschlagenen oder bestätigten Zustand befinden.

Entfernte Themen können später bei Bedarf wieder als angezeigte Themen hinzugefügt werden. 


## <a name="see-also"></a>Weitere Informationen:



  






