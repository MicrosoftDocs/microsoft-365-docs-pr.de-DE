---
title: Einschränken des Zugriffs auf Themen
description: Vorgehensweise Ausschließen von Themen, damit diese nicht erkannt werden.
author: efrene
ms.author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: b23d01585d9282132d9e55c74bb22bcdc6ca314a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698960"
---
# <a name="restrict-access-to-topics-in-topic-experiences"></a>Einschränken des Zugriffs auf Themen in Thema Erfahrungen

In Themenbereichen sollten die Beteiligten in Ihrer Organisation möglicherweise sicherstellen, dass bestimmte Themen nicht erkannt und für Ihre lizenzierten Benutzer verfügbar gemacht werden. Sie arbeiten beispielsweise an einem Projekt, für das Sie noch keine Informationen verfügbar machen möchten. Während Office 365 Berechtigungen für Websites, Dateien und andere Ressourcen verhindern, dass Benutzer in Themen vertrauliche Informationen von Benutzern anzeigen können, gibt es zusätzliche Schutzvorkehrungen, um zu verhindern, dass bestimmte Themen jemals erkannt werden.

Während Knowledge-Administratoren die Einstellungen für das Wissensnetzwerk steuern, um zu verhindern, dass Themen entdeckt werden, müssen Wissensmanager und andere Beteiligte wissen, wie dies geschieht, damit Sie gemeinsam daran arbeiten können.

> [!Important] 
> In diesem Artikel wird beschrieben, wie Sie verhindern können, dass Themen über AI identifiziert oder in Ihrer Umgebung als zusätzliche Sicherheitsvorkehrungen betrachtet werden. Es ist wichtig zu beachten, dass die Benutzer in den Themen Erfahrungen keine Elemente in einem Thema anzeigen dürfen, auf die Sie über Office 365 Berechtigungen nicht zugreifen können. Selbst wenn ein Benutzer ein Thema, dessen Dateien, Websites und Seiten anzeigen kann, sind ihm keine Office 365 Berechtigungen zur Anzeige angezeigt. Stellen Sie sicher, dass die Berechtigungen für vertrauliche Dateien ordnungsgemäß festgelegt sind, sollten Sie die primäre Sicherheits Sicherung sein.

## <a name="prevent-topics-from-being-identified"></a>Verhindern, dass Themen identifiziert werden

Der Wissens Administrator kann den Zugriff auf bestimmte Themen einschränken, indem er verhindert, dass er in der anfänglichen Indizierung gefunden wird. Es gibt zwei Möglichkeiten, dies in den Einstellungen des Knowledge Network-Administrators im Microsoft 365 Admin Center zu tun.
 
- [Wählen Sie SharePoint-Websites aus, die von der Themen Ermittlung ausgeschlossen](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources)werden sollen: mit dieser Einstellung können Sie verhindern, dass bestimmte SharePoint-Websites für Themen gecrawlt werden.
- [Themen nach Namen ausschließen](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name): Administratoren können diese Einstellung verwenden, um zu verhindern, dass bestimmte Themen nach Namen erkannt werden. In den Einstellungen des Wissensnetzwerk Administrators kann ein Administrator eine Liste von Themen hochladen, die in einer CSV-Datei ausgeschlossen werden sollen. Sie können Themen ausschließen, die genaue oder partielle Übereinstimmungen mit einem Themen Namen aufweisen.

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a>Verhindern, dass Themen von bestimmten Benutzern angezeigt werden

Wissens Administratoren können auch [auswählen, wer Themen in Ihrer Organisation anzeigen kann](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules). Mit dieser Einstellung können Sie auswählen, welche lizenzierten Benutzer alle Themen anzeigen können. In einer Pilotumgebung können Sie beispielsweise nur zulassen, dass eine kleine Gruppe von Benutzern Themen anzeigen kann.

## <a name="remove-topics-from-being-viewed"></a>Entfernen von Themen aus der Ansicht

Wissensmanager können auswählen, [Themen zu entfernen](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) , damit Benutzer Sie nicht mehr sehen können. Auf der Seite **Themen verwalten** im **Themen Center** können Knowledge Manager auswählen, bestimmte Themen abzulehnen, um zu verhindern, dass Sie angezeigt werden. Themen können entfernt werden, unabhängig davon, ob Sie den Status "vorgeschlagen" oder "bestätigt" aufweisen.

Entfernte Themen können bei Bedarf später als sichtbare Themen wieder hinzugefügt werden. 


## <a name="see-also"></a>Weitere Informationen:



  






