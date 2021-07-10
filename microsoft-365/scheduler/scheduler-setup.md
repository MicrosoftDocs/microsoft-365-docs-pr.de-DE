---
title: Einrichten des Schedulers für Microsoft 365.
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: Einrichten des Schedulers für Microsoft 365.
ms.openlocfilehash: 924b25e3d921f402c97632f7475ed5beea98d5c7
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362546"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a>Einrichten des Planers für Microsoft 365


Zum Einrichten des Schedulers für Microsoft 365 sind die folgenden Voraussetzungen erforderlich:

| Was benöte ich? | Beschreibung |
|-------------------|-------------|
|Cortana Postfach |Mandantenadministratoren müssen ein Postfach so festlegen, dass es als "Cortana"-Postfach (d. cortana@yourdomain.com) dient.         |
|Exchange Online-Postfach |Benutzer müssen über eine Exchange Online E-Mail und einen Kalender verfügen         |
|Scheduler-Lizenz |Informationen zu Lizenzierung und Preisen finden Sie unter [Scheduler für Microsoft 365.](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing)        |

## <a name="create-a-mailbox-for-cortana"></a>Erstellen eines Postfachs für Cortana

Ein Exchange Postfach in Ihrem Mandanten fungiert als Cortana Postfach, mit dem Ihr Mandant E-Mails an und von Cortana senden und empfangen kann. Alle an Cortana gesendeten E-Mails werden basierend auf Ihrer Aufbewahrungsrichtlinie im Cortana Postfach Ihres Mandanten aufbewahrt.

- Verwenden Sie die Microsoft 365 Admin Center, um ein Benutzerpostfach zu erstellen. Es wird eine Aufbewahrungsrichtlinie für 30 Tage empfohlen. 
- Verwenden Sie den Namen Cortana in der primären SMTP-Adresse Ihres Postfachs. Namen wie "Cortana@yourdomain.com", "CortanaScheduler@contoso.com" oder "Cortana". Scheduler@yourdomain.com' werden empfohlen.

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a>Festlegen des Postfachs als Planer-Assistent

Nachdem ein eindeutiges Postfach für Cortana Scheduler erstellt wurde, müssen Sie das Postfach formell Microsoft 365. Nachdem Sie das Cortana Scheduler-Postfach festgelegt haben, steht es zur Verfügung, um Besprechungen im Namen Ihrer Benutzer zu planen.

Um das Cortana Scheduler-Postfach festzulegen, muss ein autorisierter Administrator einen einzeiligen PowerShell-Befehl ausführen. 

1. Verbinden zum Microsoft 365 Remote-PowerShell-Ausführungsspeicherplatz für Ihre Organisation.

2. Führen Sie das folgende PowerShell-Skript aus, um das Postfach für Scheduler festzulegen:

    ```powershell
    Set-mailbox cortana@contoso.com -SchedulerAssistant:$true
    ```
    
    Nachdem Sie diesen Befehl "festlegen" im Cortana Scheduler-Postfach ausgeführt haben, wird für das Postfach eine neue "PersistedCapability" festgelegt, um zu beachten, dass dieses Postfach "SchedulerAssistant" ist.

> [!NOTE]
> Führen Sie die folgenden Schritte aus, um Ihre Organisation mit PowerShell zu verbinden, wenn Sie dies zuvor noch nicht getan haben: [Verbinden Microsoft 365 mit PowerShell.](../enterprise/connect-to-microsoft-365-powershell.md)

Führen Sie die Get-Funktion aus, um zu ermitteln, welches Postfach in Ihrer Organisation derzeit als Cortana Scheduler-Assistent festgelegt ist:

```powershell
Get-mailbox | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}
```

> [!IMPORTANT]
> Es kann bis zu zwei Stunden dauern, bis das Scheduler-Postfach die vollständige Bereitstellung abgeschlossen hat, um die SchedulerAssistant-Funktion festzulegen.

## <a name="exchange-online-mailbox"></a>Exchange Online-Postfach
Eine Scheduler-Lizenz ist ein Add-On für Microsoft 365, mit dem der Besprechungsorganisator seine Besprechungsplanungsaufgaben an den Planer-Assistenten delegieren kann. Damit der Planer funktioniert, in der Regel über Microsoft 365 Lizenz, benötigen Besprechungsorganisatoren die folgenden Komponenten:

- Ein Postfach, das als Postfach des Planer-Assistenten festgelegt ist
- Scheduler-Lizenz
- Exchange Online Postfach und Kalender

Die Besprechungsteilnehmer benötigen keine Scheduler- oder Microsoft 365-Lizenz.

## <a name="scheduler-end-user-license-requirements"></a>Lizenzanforderungen für Scheduler-Endbenutzer

Eine Scheduler-Lizenz erfordert eine der folgenden Lizenzen:

- Microsoft 365 E3, A3, E5, A5
- Business Basic, Business, Business Standard, Business Premium
- Office 365 E1, A1, E3, A3, E5, A5
- Business Essentials, Business Premium
- Exchange Online Plan 1- oder Plan 2-Lizenz. 

> [!Note]

> Scheduler für Microsoft 365 ist nur in weltweiten mehrinstanzenfähigen Umgebungen in Englisch verfügbar. **Der Scheduler für Microsoft 365** ist für Benutzer von:

- Microsoft 365 betrieben von 21Vianet in China
- Microsoft 365 mit der deutschen Cloud, die den Datentreuhänder Deutsche Telekom verwendet
- Government Cloud, einschließlich GCC, Consumer, GCC High oder DoD

Der Scheduler unterstützt Benutzer in Deutschland, deren Datenspeicherort sich nicht im deutschen Rechenzentrum befindet.
