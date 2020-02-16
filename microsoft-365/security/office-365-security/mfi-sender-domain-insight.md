---
title: Einblick in Absenderdomäne
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: Administratoren können sich über das Fix Sender Domain Insight im Nachrichtenfluss-Dashboard im Security & Compliance Center informieren.
ms.openlocfilehash: 2db1b971ef39f8b207b349ca53237ff87cc9193e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42082566"
---
# <a name="fix-sender-domain-insight"></a>Einblick in Absenderdomäne

Office 365 erfordert, dass Nachrichten, die von internen lokalen e-Mail-Umgebungen gesendet werden, Office 365 werden, um bestimmte Sicherheitskriterien zu erfüllen:

- Sie haben in Office 365 einen eingehenden Connector erstellt, um SMTP-Verbindungen von Ihrem lokalen e-Mail-Server mithilfe der Quell-IP-Adresse oder eines Zertifikats zu authentifizieren.

- Sie haben ihren lokalen e-Mail-Server so konfiguriert, dass e-Mails über Office 365 an die externe weltweiter geleitet werden.

- In Ihrer Konfiguration ist eine der folgenden Aussagen zutreffend:

  - Die e-Mail-Domäne des Absenders wird in Ihrer Office 365 Organisation registriert. Weitere Informationen finden Sie unter Hinzufügen von Domänen in Office 365.

  - Der lokale e-Mail-Server ist für die Verwendung eines Zertifikats zum Senden von e-Mails an Office 365 konfiguriert, das Zertifikat enthält einen Domänennamen, den Sie in Office 365 registriert haben, oder stimmt genau überein und Sie haben einen zertifikatbasierten Connector in Office 365 mit diesem erstellt. Domäne. 

Nachrichten, die die Kriterien nicht erfüllen, werden nicht der Organisation zugeordnet und können zurückgewiesen werden.

Das **Fix Sender Domain** Insight zeigt Ihnen e-Mails von Ihrer lokalen Umgebung, die die Kriterien nicht erfüllen, unterstützt Sie bei der Ermittlung potenziell gefährdeter Computer und Benutzerkonten in Ihrer lokalen e-Mail-Umgebung und unterstützt Sie bei der Durchführung von Korrekturaktionen.

![Der Fix Sender Domain Insight im Nachrichtenfluss-Dashboard im Security & Compliance Center](../../media/sender-domain-insight-selected.png)

Wenn Sie auf **Details anzeigen**klicken, werden Sie zu einem anderen Widget mit weiteren Details weitergeleitet, wie im folgenden Diagramm dargestellt:

![Das Detail-Widget im Fix Sender Domain Insight](../../media/sender-domain-view-details.png)

Sie sehen den eingehenden Connector, der für die Zustellung der Nachrichten an Office 365 verwendet wurde. Sie können auch auf **Beispiel Meldungs-IDs anzeigen** klicken, um Details zu den Nachrichten anzuzeigen, die von Ihrer lokalen e-Mail-Umgebung gesendet wurden. Da diese Nachrichten von Office 365 abgelehnt wurden, können Sie die Nachrichtenablaufverfolgung nicht verwenden, aber Sie können die Beispiel Nachrichten-IDs verwenden, um die Nachrichten in Ihrer lokalen e-Mail-Umgebung nachzuverfolgen.

![Anzeigen von Beispiel Meldungs-IDs im Fix Sender Domain Insight](../../media/sender-domain-view-sample-message-ids.png)

## <a name="see-also"></a>Siehe auch

Weitere Informationen zu anderen e-Mail-Fluss-Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).
