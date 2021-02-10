---
title: Senden von Inhaltstypen per Push auf einen Hub
description: Lernen wie Inhaltstypen per Push auf einen Hub gesendet wird
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
ms.openlocfilehash: 22d146b1d376bab134e82ad7d1313cb7881ca45b
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50144971"
---
# <a name="push-content-types-to-a-hub"></a>Senden von Inhaltstypen per Push auf einen Hub

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GyeV]  

</br>


Um wichtige Inhaltstypen für SharePoint-Bibliotheken und -Listen durchweg verfügbar zu machen, können Sie sie an die von Ihnen ausgewählten Hubs senden. Durch das Senden der Inhaltstypen per Push werden sie automatisch zu allen neuen Listen und Bibliotheken hinzugefügt, die auf den mit dem Hub verknüpften Sites erstellt wurden, sowie zu allen neuen Sites, die dem Hub hinzugefügt wurden. Dieses Feature benötigt eine [SharePoint Syntex](index.md)-Lizenz.

Damit diese Funktion funktioniert, müssen die geposteten Inhaltstypen bereits veröffentlicht sein.

So übertragen Sie Inhaltstypen auf Hubs

1. Erweitern Sie im SharePoint Admin Center **Inhaltsdienste**, und wählen Sie dann **Inhaltstyp-Galerie** aus.
2. Wählen Sie den Inhaltstyp aus, den Sie an Hubs senden möchten.
3. Wählen Sie in der Befehlsleiste **Bearbeiten** aus.
4. Wählen Sie **Hubwebsites auswählen** aus.
5. Wählen Sie die gewünschten Hubwebsites aus, und wählen Sie dann **OK** aus.
6. Wählen Sie **Speichern** aus.

Wenn Sie einen Inhaltstyp zum ersten Mal auf einen vorhandenen Hub und die vorhandenen zugeordneten Sites übertragen, kann es bis zu einer Stunde dauern, bis die Einstellungen auf der Site aktualisiert werden. Neue Zuordnungen zum Hub erfordern diese Wartezeit nicht und die Einstellungen werden in wenigen Minuten wiedergegeben.

Nachdem die Einstellungen aktualisiert wurden, ist der Inhaltstyp mit diesen Einstellungen in wenigen Minuten auf jeder neu mit dem Hub verknüpften Site verfügbar. Dann wird jeder neu erstellten Liste oder Bibliothek der Inhaltstyp innerhalb weniger Minuten nach der Erstellung automatisch hinzugefügt. Ein übertragener Inhaltstyp wird einer Dokumentbibliothek nur hinzugefügt, wenn er direkt oder indirekt vom Dokumentinhaltstyp abgeleitet ist, und ein Inhaltstyp wird nur dann zu einer Liste hinzugefügt, wenn er nicht direkt oder indirekt vom Dokumentinhaltstyp abgeleitet ist.

## <a name="see-also"></a>Weitere Informationen:
