---
title: Sicherheitstipps in E-Mail-Nachrichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- BCS160
ms.assetid: fb4f8e49-0468-4be2-8fa6-99501f1ad9d5
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie EoP und Office 365 Sie mit Spam, Phishing und Schadsoftware schützen, indem Sie oben in e-Mails einen Sicherheitstipp hinzufügen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3da52a8ef2913c30c281fec74f92142847e29792
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201983"
---
# <a name="safety-tips-in-email-messages"></a>Sicherheitstipps in E-Mail-Nachrichten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange Online Protection (EoP) und Microsoft 365 schützen Sie mit Spam, Phishing und Malware Prävention. Heute sind einige dieser Angriffe so gut gestaltet, dass Sie legitim erscheinen. Das Senden von Nachrichten an den Junk-e-Mail-Ordner ist nicht immer ausreichend. Wenn Sie nun Ihre e-Mails in Outlook oder Outlook im Internet oder in einem beliebigen e-Mail-Client überprüfen, überprüft EoP automatisch den Absender und fügt einen Sicherheitshinweis oben in der e-Mail hinzu.

Sicherheitstipps in Outlook hängen nicht davon ab, welche Version von Outlook Sie verwenden, da der Sicherheitstipp geöffnet und direkt in den Nachrichtentext eingefügt wird. Dies bedeutet, dass der Sicherheitshinweis in dem von Ihnen verwendeten e-Mail-Client angezeigt wird. Er wird auf der Ebene der e-Mail-Filter ausgeführt und nicht auf der Ebene des e-Mail-Clients gerendert, sodass er nicht nur in einer beliebigen Version von Outlook angezeigt wird, sondern auch in einem beliebigen e-Mail-Client.

Der Sicherheitstipp – eine farbcodierte Nachricht – warnt Sie vor potenziell schädlichen Nachrichten. Die meisten Nachrichten in Ihrem Posteingang verfügen nicht über einen Sicherheitshinweis. Sie werden nur angezeigt, wenn EoP und Microsoft 365 Informationen enthalten, die Sie bei der Vermeidung von Spam-, Phishing-und Schadsoftware-Angriffen unterstützen müssen. Wenn in Ihrem Posteingang Sicherheitstipps angezeigt werden, können Sie anhand der folgenden Beispiele Weitere Informationen zu den einzelnen Sicherheitstipp Typen erhalten.

- Verdächtige e-Mails (roter Sicherheitshinweis).

    ![Screenshot, der einen roten Sicherheitstipp zeigt.](../../media/5078a0be-e556-44a1-b169-09d780d26898.png)

    Ein roter Sicherheitstipp in einer e-Mail bedeutet, dass die Nachricht, die Sie erhalten haben, etwas Verdächtiges enthält, beispielsweise einen Phishing-Betrug. Es wird empfohlen, diese Art von e-Mail-Nachrichten aus dem Posteingang zu löschen, ohne Sie zu öffnen.

- Safe Mail (grüner Sicherheitstipp).

    ![Screenshot, der eine grüne Sicherheitsspitze zeigt.](../../media/acbc11d0-f626-4848-9fbf-66eeeda3f803.png)

    Neben unsicheren Nachrichten informieren wir Sie auch über gültige Nachrichten von Absendern, denen wir Vertrauen, mit einem grünen Sicherheitstipp. Ein grüner Sicherheitstipp in einer e-Mail bedeutet, dass wir den Absender der Nachricht überprüft und überprüft haben, dass Sie sicher ist. Microsoft verwaltet diese Liste vertrauenswürdiger Absender, die Finanzorganisationen und andere häufig gefälschte oder imitierte Personen umfassen.

- Ungefiltertes Mail (grauer Sicherheitstipp).

    ![Screenshot, der einen grauen Sicherheitstipp zeigt.](../../media/c4d0cf8f-08e9-4c84-beee-1d9e0b022e0a.png)

    Wir sagen Ihnen auch, wann die Überprüfung einer e-Mail übersprungen wurde, da Sie von einem Absender stammt, dem Sie Ihre Liste sicherer Absender Vertrauen, oder wenn eine Nachrichtenfluss Regel zur Umgehung der Filterung vorhanden ist.

    Die graue Sicherheitsspitze wird auch angezeigt, wenn externe Bilder blockiert werden, das heißt, die Nachricht befindet sich in Ihrem Posteingang und scheint nicht Spam zu sein, sondern enthält externe Bilder, die Sie nicht zum Herunterladen entschieden haben.

## <a name="working-with-safety-tips"></a>Arbeiten mit Sicherheitstipps

Sicherheitstipps sind für Outlook im Internet immer aktiviert, obwohl nicht jede Nachricht eine erhalten wird. Administratoren können Sicherheitstipps für andere e-Mail-Clients wie Outlook deaktivieren. Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien in Office 365](configure-your-spam-filter-policies.md).

Wenn Sie mit der Kategorisierung einer Nachricht durch EoP nicht einverstanden sind (das heißt, die Nachricht ist kein Spam oder Sie sollte als Spam gekennzeichnet worden sein), können Sie die Nachrichten zur Analyse an Microsoft übermitteln, um eine bessere Benutzerfreundlichkeit zu ermöglichen. Anweisungen finden Sie unter [Report Messages and files to Microsoft](report-junk-email-messages-to-microsoft.md). Sie können auch auf den Link Feedback im Sicherheitstipp klicken, um Kommentare direkt an Microsoft zu senden und uns dabei zu verbessern.
