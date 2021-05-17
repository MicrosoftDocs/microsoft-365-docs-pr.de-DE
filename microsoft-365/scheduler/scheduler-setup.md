---
title: Einrichten von Scheduler für Microsoft 365.
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: Einrichten von Scheduler für Microsoft 365.
ms.openlocfilehash: 79e1596288836770c720cb312580fc706bb7b95f
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286190"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a>Einrichten von Scheduler für Microsoft 365

Zum Einrichten des Schedulers für Microsoft 365 sind die folgenden Voraussetzungen erfüllt:

|**Was muss ich tun?** |**Beschreibung** |
|-------------------|-------------|
|Cortana-Postfach |Mandantenadministratoren müssen ein Postfach als "Cortana"-Postfach festlegen (d. h. cortana@yourdomain.com).         |
|Exchange Online-Postfach |Benutzer müssen über Exchange Online E-Mail und Kalender verfügen         |
|Scheduler-Lizenz |Informationen zu Lizenzierung und Preisen finden Sie unter [Scheduler for Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing).        |

## <a name="create-a-mailbox-for-cortana"></a>Erstellen eines Postfachs für Cortana
Ein Exchange in Ihrem Mandanten fungiert als Cortana-Postfach für Ihren Mandanten zum Senden und Empfangen von E-Mails an und von Cortana. Alle an Cortana gesendeten E-Mails werden basierend auf Ihrer Aufbewahrungsrichtlinie im Cortana-Postfach Ihres Mandanten aufbewahrt.

- Verwenden Sie Microsoft 365 Admin Center, um ein neues Postfach zu erstellen. Es wird eine 30-tägige Aufbewahrungsrichtlinie empfohlen. Verwenden Sie den Namen Cortana in der primären SMTP-Adresse Ihres Postfachs. Namen wie "Cortana@yourdomain.com", "CortanaScheduler@contoso.com" oder "Cortana.Scheduler@yourdomain.com" werden empfohlen.
- Wenden Sie sich an Microsoft (scheduler_m365@microsoft.com), um Ihr Cortana-Postfach zu aktivieren. 

> [!IMPORTANT]
> Sie müssen sich an Microsoft wenden, um Ihr Cortana-Postfach für die Verwendung des Scheduler-Diensts per E-Mail scheduler_m365@microsoft.com. Die Aktivierung Ihres Cortana-Postfachs kann bis zu zwei Wochen dauern.

## <a name="exchange-online-mailbox"></a>Exchange Online-Postfach
Scheduler ist ein Add-On für Microsoft 365. Besprechungsorganisatoren müssen über ein Exchange Online postfach und kalender verfügen, damit Scheduler funktioniert.

## <a name="exchange-requirements"></a>Exchange-Systemanforderungen

Zusätzlich zur Lizenzierung von Scheduler benötigen Sie eine der folgenden Lizenzen:

- Microsoft 365 E3, A3, E5, A5
- Business Basic, Business, Business Standard, Business Premium
- Office 365 E1, A1, E3, A3, E5, A5
- Business Essentials, Business Premium
- Exchange Online Plan 1- oder Plan 2-Lizenz. 

> [!Note]
> **Scheduler für Microsoft 365** ist für Benutzer von Office 365, die von 21Vianet in China betrieben werden, nicht verfügbar. Sie ist auch nicht für Benutzer von Microsoft 365 mit der deutschen Cloud verfügbar, die den Datentreuhänder Deutsche Telekom verwendet. Es wird für Benutzer in Deutschland unterstützt, deren Datenspeicherort sich nicht im deutschen Rechenzentrum befindet.
>
>Dieses Feature wird auch nicht für Benutzer der Government Cloud unterstützt (GCC, Consumer, GCC High oder DoD).
