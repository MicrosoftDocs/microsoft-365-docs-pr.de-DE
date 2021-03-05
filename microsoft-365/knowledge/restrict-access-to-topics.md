---
title: Einschränken des Zugriffs auf Themen in Microsoft Viva Topics
description: So schließen Sie Themen aus, um zu verhindern, dass sie gefunden werden.
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: b8c49c96ace14ac1ba03411b5670d8e77268109a
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453908"
---
# <a name="restrict-access-to-topics-in-microsoft-viva-topics"></a>Einschränken des Zugriffs auf Themen in Microsoft Viva Topics

In Microsoft Viva möchten Die Beteiligten in Ihrer Organisation möglicherweise sicherstellen, dass bestimmte Themen nicht entdeckt und für Ihre lizenzierten Benutzer verfügbar gemacht werden. Sie arbeiten beispielsweise an einem Projekt, zu dem Sie noch keine Informationen verfügbar machen möchten. Während Office 365-Berechtigungen auf Websites, Dateien und anderen Ressourcen verhindern, dass Benutzer von Themenerfahrungen vertrauliche Informationen in Themen anzeigen, gibt es zusätzliche Garantien, um zu verhindern, dass bestimmte Themen jemals entdeckt werden.

Während Wissensadministratoren die Einstellungen des Wissensnetzwerks steuern, um zu verhindern, dass Themen gefunden werden, müssen Wissensmanager und andere Beteiligte wissen, wie dies geschieht, damit sie zusammenarbeiten können.

> [!Important] 
> In diesem Artikel werden Möglichkeiten beschrieben, um zu verhindern, dass Themen über KI identifiziert oder in Ihrer Umgebung als zusätzlicher Sicherheitsschutz angezeigt werden. Beachten Sie, dass Benutzer in Themen von "Viva" in einem Thema nichts anzeigen dürfen, auf das sie nicht über Office 365-Berechtigungen zugreifen dürfen. Auch wenn ein Benutzer ein Thema anzeigen kann, sind seine Dateien, Websites und Seiten, die nicht über Office 365-Berechtigungen zum Anzeigen verfügen, für sie nicht sichtbar. Stellen Sie sicher, dass Berechtigungen für vertrauliche Dateien ordnungsgemäß festgelegt sind, sollten Ihre primären Sicherheitsvorkehrungen sein.

## <a name="prevent-topics-from-being-identified"></a>Verhindern, dass Themen identifiziert werden

Der Wissensadministrator kann den Zugriff auf bestimmte Themen einschränken, indem er verhindert, dass er in der anfänglichen Indizierung gefunden wird. Es gibt zwei Möglichkeiten, diese Aufgabe in den Administratoreinstellungen des Knowledge Network im Microsoft 365 Admin Center auszuführen.
 
- [Wählen Sie SharePoint-Websites](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources)aus, die von der Themenerkennung ausgeschlossen werden: Sie können diese Einstellung verwenden, um zu verhindern, dass bestimmte SharePoint-Websites nach Themen gecrawlt werden.
- [Themen nach Name ausschließen:](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name)Administratoren können diese Einstellung verwenden, um zu verhindern, dass bestimmte Themen nach Namen erkannt werden. In den Administratoreinstellungen des Wissensnetzwerks kann ein Administrator eine Liste der Themen hochladen, die in einer CSV-Datei ausgeschlossen werden sollen. Sie können Themen ausschließen, die genaue oder teilweise Übereinstimmungen mit einem Themennamen haben.

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a>Verhindern, dass Themen von bestimmten Benutzern angezeigt werden

Wissensadministratoren können auch [auswählen, wer Themen in Ihrer Organisation anzeigen kann.](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules) Mit dieser Einstellung können Sie auswählen, welche lizenzierten Benutzer alle Themen anzeigen können. In einer Pilotumgebung können Sie beispielsweise nur einer kleinen Gruppe von Benutzern erlauben, Themen anzeigen zu können.

## <a name="remove-topics-from-being-viewed"></a>Entfernen von Themen aus der Anzeige

Wissensmanager können Themen [entfernen,](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) damit benutzer sie nicht mehr sehen können. Auf der **Seite Themen verwalten** im **Themencenter** können Wissensmanager bestimmte Themen ablehnen, um zu verhindern, dass sie angezeigt werden. Themen können unabhängig davon entfernt werden, ob sie sich in einem vorgeschlagenen oder bestätigten Zustand befinden.

Entfernte Themen können später bei Bedarf wieder als angezeigte Themen hinzugefügt werden. 


## <a name="see-also"></a>Weitere Informationen:



  






