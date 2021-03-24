---
title: Überprüfen von Warnungen in Microsoft Defender for Endpoint
description: Überprüfen Sie Warnungsinformationen, einschließlich einer visualisierten Warnungsgeschichte und Details für jeden Schritt der Kette.
keywords: Vorfall, Vorfälle, Computer, Geräte, Benutzer, Warnungen, Warnung, Untersuchung, Diagramm, Nachweise
ms.prod: m365-security
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: daniha
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.date: 5/1/2020
ms.technology: mde
ms.openlocfilehash: b791f2b62cb4a3f8062c80ceeb04ccfa72f704bc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062135"
---
# <a name="review-alerts-in-microsoft-defender-for-endpoint"></a>Überprüfen von Warnungen in Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

Die Warnungsseite in Microsoft Defender for Endpoint bietet den vollständigen Kontext für die Warnung, indem Angriffssignale und Warnungen im Zusammenhang mit der ausgewählten Warnung kombiniert werden, um eine detaillierte Warnungsgeschichte zu erstellen.

Schnelles Triagen, Untersuchen und Ergreifen effektiver Maßnahmen für Warnungen, die Sich auf Ihre Organisation auswirken. Verstehen Sie, warum sie ausgelöst wurden, und ihre Auswirkungen von einem Ort aus. Weitere Informationen finden Sie in dieser Übersicht.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4yiO5]

## <a name="getting-started-with-an-alert"></a>Erste Schritte mit einer Warnung

Wenn Sie den Namen einer Warnung in Defender for Endpoint auswählen, werden Sie auf der Warnungsseite angezeigt. Auf der Warnungsseite werden alle Informationen im Kontext der ausgewählten Warnung angezeigt. Jede Warnungsseite besteht aus 4 Abschnitten:

1. **Der Warnungstitel** zeigt den Namen der Warnung an und erinnert Sie daran, welche Warnung Ihre aktuelle Untersuchung gestartet hat, unabhängig davon, was Sie auf der Seite ausgewählt haben.
2. [**Betroffene Objekte**](#review-affected-assets) listet Karten von Geräten und Benutzern auf, die von dieser Warnung betroffen sind und auf die für weitere Informationen und Aktionen geklickt werden kann.
3. Der **Warnungsstory** zeigt alle Entitäten im Zusammenhang mit der Warnung an, die durch eine Strukturansicht verbunden sind. Die Warnung im Titel steht im Fokus, wenn Sie zum ersten Mal auf der Seite der ausgewählten Warnung landen. Entitäten im Warnungsstory können erweitert und angeklickt werden, um zusätzliche Informationen zur Verfügung zu stellen und die Antwort zu beschleunigen, indem Sie Aktionen direkt im Kontext der Warnungsseite ausführen können. Verwenden Sie den Warnungsstory, um Ihre Untersuchung zu starten. Weitere Informationen finden Sie unter [Untersuchen von Warnungen in Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts).
4. Im **Detailbereich** werden zunächst die Details der ausgewählten Warnung mit Details und Aktionen im Zusammenhang mit dieser Warnung angezeigt. Wenn Sie eine der betroffenen Objekte oder Entitäten im Warnungsstory auswählen, wird der Detailbereich geändert, um kontextbezogene Informationen und Aktionen für das ausgewählte Objekt zur Verfügung zu stellen.

Notieren Sie sich den Erkennungsstatus für Ihre Warnung. 
- Verhindert – Die versuchte verdächtige Aktion wurde vermieden. Beispielsweise wurde eine Datei entweder nicht auf den Datenträger geschrieben oder ausgeführt.
![Eine Warnungsseite, auf der bedrohungen angezeigt werden, wurde verhindert](images/detstat-prevented.png)
- Blockiert – Verdächtiges Verhalten wurde ausgeführt und dann blockiert. Beispielsweise wurde ein Prozess ausgeführt, aber da er in der Folge verdächtige Verhaltensweisen gezeigt hat, wurde der Prozess beendet.
![Eine Warnungsseite, auf der die Bedrohung angezeigt wird, wurde blockiert.](images/detstat-blocked.png)
- Erkannt – Ein Angriff wurde erkannt und ist möglicherweise noch aktiv.
![Eine Warnungsseite, auf der die Bedrohung erkannt wurde](images/detstat-detected.png)




Anschließend können Sie auch  die Details zur automatischen Untersuchung im Detailbereich Ihrer Warnung überprüfen, um zu sehen, welche Aktionen bereits ergriffen wurden, sowie die Beschreibung der Warnung für empfohlene Aktionen lesen.

![Ein Codeausschnitt des Detailbereichs mit hervorgehobener Warnungsbeschreibung und automatischen Untersuchungsabschnitten](images/alert-air-and-alert-description.png)

Weitere Informationen, die beim Öffnen der Warnung im Detailbereich verfügbar sind, umfassen MITRE-Techniken, Quelle und zusätzliche Kontextdetails.




## <a name="review-affected-assets"></a>Überprüfen betroffener Objekte

Wenn Sie ein Gerät oder eine Benutzerkarte in den betroffenen Ressourcenabschnitten auswählen, wechseln Sie zu den Details des Geräts oder Benutzers im Detailbereich.

- **Bei Geräten** werden im Detailbereich Informationen zum Gerät selbst angezeigt, z. B. Domäne, Betriebssystem und IP. Aktive Warnungen und die angemeldeten Benutzer auf diesem Gerät sind ebenfalls verfügbar. Sie können sofort maßnahmen, indem Sie das Gerät isolieren, die Ausführung von Apps einschränken oder einen Antivirenscan ausführen. Alternativ können Sie ein Untersuchungspaket sammeln, eine automatisierte Untersuchung initiieren oder zur Geräteseite wechseln, um die Untersuchung aus Der Sicht des Geräts zu untersuchen.

   ![Ein Codeausschnitt des Detailbereichs, wenn ein Gerät ausgewählt ist](images/device-page-details.png)

- **Für** Benutzer werden im Detailbereich detaillierte Benutzerinformationen angezeigt, z. B. der SAM-Name und die SID des Benutzers sowie Anmeldetypen, die von diesem Benutzer ausgeführt werden, sowie alle Warnungen und Vorfälle im Zusammenhang mit diesem Benutzer. Sie können *benutzerseite öffnen auswählen,* um die Untersuchung aus der Sicht dieses Benutzers fortzufahren.

   ![Ein Codeausschnitt des Detailbereichs, wenn ein Benutzer ausgewählt wird](images/user-page-details.png)


## <a name="related-topics"></a>Verwandte Themen

- [Anzeigen und Organisieren der Warteschlange für Vorfälle](view-incidents-queue.md)
- [Untersuchen von Vorfällen](investigate-incidents.md)
- [Verwalten von Vorfällen](manage-incidents.md)
