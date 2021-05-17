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
ms.openlocfilehash: d6dfb2f7f432a40c5b6e96a9437f50ba47e23387
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500881"
---
# <a name="restrict-access-to-topics-in-microsoft-viva-topics"></a>Einschränken des Zugriffs auf Themen in Microsoft Viva Topics

In Microsoft Viva möchten Die Beteiligten in Ihrer Organisation möglicherweise sicherstellen, dass bestimmte Themen nicht entdeckt und für Ihre lizenzierten Benutzer verfügbar gemacht werden. Sie arbeiten beispielsweise an einem Projekt, zu dem Sie noch keine Informationen verfügbar machen möchten. Während Office 365 Berechtigungen für Websites, Dateien und andere Ressourcen verhindern, dass Benutzer von Themenerfahrungen vertrauliche Informationen in Themen anzeigen, gibt es zusätzliche Garantien, um zu verhindern, dass bestimmte Themen jemals entdeckt werden.

Während Wissensadministratoren die Einstellungen steuern, um zu verhindern, dass Themen gefunden werden, müssen Wissensmanager und andere Beteiligte wissen, wie dies geschieht, damit sie zusammenarbeiten können.

> [!Important] 
> In diesem Artikel werden Möglichkeiten beschrieben, um zu verhindern, dass Themen über KI identifiziert oder in Ihrer Umgebung als zusätzlicher Sicherheitsschutz angezeigt werden. Es ist wichtig zu beachten, dass Benutzer in Themen von "Viva" in einem Thema nichts anzeigen dürfen, auf das sie nicht über berechtigungen Office 365 dürfen. Auch wenn ein Benutzer ein Thema anzeigen kann, sind seine Dateien, Websites und Seiten, für die er nicht über Office 365 berechtigungen zum Anzeigen nicht sichtbar. Stellen Sie sicher, dass Berechtigungen für vertrauliche Dateien ordnungsgemäß festgelegt sind, sollten Ihre primären Sicherheitsvorkehrungen sein.

## <a name="prevent-topics-from-being-identified"></a>Verhindern, dass Themen identifiziert werden

Der Wissensadministrator kann den Zugriff auf bestimmte Themen einschränken, indem er verhindert, dass er in der anfänglichen Indizierung gefunden wird. Es gibt zwei Möglichkeiten, diese Aufgabe in den Einstellungen des Viva Topics-Admins im Microsoft 365 auszuführen.
 
- [Wählen SharePoint Websites aus,](./topic-experiences-discovery.md#select-sharepoint-topic-sources)die von der Themenerkennung ausgeschlossen werden: Sie können diese Einstellung verwenden, um zu verhindern, dass bestimmte websites SharePoint nach Themen gecrawlt werden.
- [Themen nach Name ausschließen:](./topic-experiences-discovery.md#exclude-topics-by-name)Administratoren können diese Einstellung verwenden, um zu verhindern, dass bestimmte Themen nach Namen erkannt werden. In den Einstellungen des Viva Topics-Admins kann ein Administrator eine Liste der Themen hochladen, die in einer CSV-Datei ausgeschlossen werden sollen. Sie können Themen ausschließen, die genaue oder teilweise Übereinstimmungen mit einem Themennamen haben.

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a>Verhindern, dass Themen von bestimmten Benutzern angezeigt werden

Wissensadministratoren können auch [auswählen, wer Themen in Ihrer Organisation anzeigen kann.](./topic-experiences-knowledge-rules.md) Mit dieser Einstellung können Sie auswählen, welche lizenzierten Benutzer alle Themen anzeigen können. In einer Pilotumgebung können Sie beispielsweise nur einer kleinen Gruppe von Benutzern erlauben, Themen anzeigen zu können.

## <a name="remove-topics-from-being-viewed"></a>Entfernen von Themen aus der Anzeige

Wissensmanager können Themen [entfernen,](./manage-topics.md) damit benutzer sie nicht mehr sehen können. Auf der **Seite Themen verwalten** im **Themencenter** können Wissensmanager bestimmte Themen ablehnen, um zu verhindern, dass sie angezeigt werden. Themen können unabhängig davon entfernt werden, ob sie sich in einem vorgeschlagenen oder bestätigten Zustand befinden.

Entfernte Themen können später bei Bedarf wieder als angezeigte Themen hinzugefügt werden. 


## <a name="see-also"></a>Weitere Informationen:



