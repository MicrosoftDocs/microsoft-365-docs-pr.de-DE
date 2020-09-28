---
title: Pushen von Inhaltstypen an einen Hub
description: Informationen zum Pushen von Inhaltstypen an einen Hub
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a852207bfd1a2a7643ce8895a533371d194954cf
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296099"
---
# <a name="push-content-types-to-a-hub"></a>Pushen von Inhaltstypen an einen Hub

Damit SharePoint-Bibliotheken und-Listen wichtige Inhaltstypen konsistenter verfügbar gemacht werden, können Sie Sie an die ausgewählten Hubs weitergeben. Dadurch werden Sie automatisch neuen Listen und Bibliotheken hinzugefügt, die auf den dem Hub zugeordneten Websites erstellt wurden, sowie auf alle neuen Websites, die dem Hub hinzugefügt wurden.

Damit dieses Feature funktioniert, müssen die gepushten Inhaltstypen bereits veröffentlicht werden.

So verschieben Sie Inhaltstypen in Hubs

1. Erweitern Sie im SharePoint Admin Center die Option **Inhaltsdienste**, und klicken Sie dann auf **Inhaltstypkatalog**.

2. Klicken Sie auf den Inhaltstyp, den Sie in Hubs verschieben möchten.

3. Klicken Sie in der Befehlsleiste auf **Bearbeiten** .
 
4. Klicken Sie auf **Hub-Standorte auswählen**.
 
5. Wählen Sie die gewünschten Hub-Standorte aus, und klicken Sie dann auf **OK**.
 
6. Klicken Sie auf **Speichern**.

Wenn ein Inhaltstyp an einen vorhandenen Hub & seinen vorhandenen verbundenen Standorten zum ersten Mal übertragen wird, kann es bis zu einer Stunde dauern, bis der Hub oder die zugehörigen Standorte besucht werden, damit die Einstellungen am Standort aktualisiert werden können. Für alle neuen Zuordnungen zum Hub ist diese Wartezeit nicht erforderlich, und die Einstellungen werden in einigen Minuten wiedergegeben. 

Sobald dieser konfiguriert ist, wird der Inhaltstyp mit diesen Einstellungen in ein paar Minuten in jedem neu zugeordneten Standort mit dem Hub zur Verfügung stehen. Sobald eine neue Liste oder Bibliothek erstellt wurde, wird der Inhaltstyp innerhalb weniger Minuten nach der Erstellung automatisch hinzugefügt. Ein gepushten Inhaltstyp wird nur dann zu einer Dokumentbibliothek hinzugefügt, wenn er direkt oder indirekt aus dem Dokumentinhaltstyp abgeleitet wird und ein Inhaltstyp nur einer Liste hinzugefügt wird, wenn er nicht direkt oder indirekt vom Dokumentinhaltstyp abgeleitet wird.

## <a name="see-also"></a>Siehe auch



  






