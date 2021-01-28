---
title: Einblick und Bericht für SMTP-Authentifizierungsclients im Dashboard für den Nachrichtenfluss
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie den Einblick in die SMTP-Authentifizierung und den Bericht im Nachrichtenflussdashboard im Security & Compliance Center verwenden, um E-Mail-Absender in ihrer Organisation zu überwachen, die authentifizierte SMTP (SMTP AUTH) zum Senden von E-Mail-Nachrichten verwenden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: afceb767f6ebfeed96deb6362e05bb088b548c3d
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029162"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a>Einblick und Bericht für SMTP-Authentifizierungsclients im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In den Einblicken der [](mail-flow-insights-v2.md) **SMTP-Authentifizierungsclients** im Nachrichtenflussdashboard und dem zugehörigen [SMTP-Authentifizierungsclientbericht](#smtp-auth-clients-report) im Security & Compliance Center wird die Verwendung des SMTP AUTH-Clientübermittlungsprotokolls durch Benutzer oder Systemkonten in Ihrer Organisation hervorgehoben. [](https://protection.office.com) Dieses Legacyprotokoll (das die Endpunkt-smtp.office365.com verwendet) bietet nur die Standardauthentifizierung und ist anfällig für die Verwendung durch gefährdete Konten zum Senden von E-Mails. Der Einblick und der Bericht ermöglichen es Ihnen, ungewöhnliche Aktivitäten für SMTP AUTH-E-Mail-Übermittlungen zu überprüfen. Außerdem werden die TLS-Verwendungsdaten für Clients oder Geräte mit SMTP AUTH angezeigt.

Das Widget gibt die Anzahl der Benutzer oder Dienstkonten an, die das SMTP-Authentifizierungsprotokoll in den letzten 7 Tagen verwendet haben.

![WIDGET für SMTP-Authentifizierungsclients im Nachrichtenflussdashboard im Security & Compliance Center](../../media/mfi-smtp-auth-clients-report-widget.png)

Wenn Sie auf die Anzahl der Nachrichten im Widget klicken, wird ein Flyout für **SMTP-Authentifizierungsclients** angezeigt. Das Flyout bietet eine aggregierte Ansicht der Verwendung und der Volumes von TLS für die letzte Woche.

![Detailf flyout nach dem Klicken auf das Widget "SMTP-Authentifizierungsclients" im Nachrichtenflussdashboard](../../media/mfi-smtp-auth-clients-report-details.png)

Sie können auf den Bericht **"SMTP-Authentifizierungsclients"** klicken, um zum Bericht "SMTP-Authentifizierungsclients" zu wechseln, wie im nächsten Abschnitt beschrieben.

## <a name="smtp-auth-clients-report"></a>SMTP-Auth-Clientbericht

### <a name="report-view-for-the-smtp-auth-clients-report"></a>Berichtsansicht für den Bericht "SMTP-Authentifizierungsclients"

Standardmäßig werden im Bericht Daten für die letzten 7 Tage angezeigt, die Daten sind jedoch für die letzten 90 Tage verfügbar.

Der Abschnitt "Übersicht" enthält die folgenden Diagramme:

- **Daten anzeigen nach:** Sendevolume: Standardmäßig zeigt das Diagramm die Anzahl der SMTP-Authentifizierungsclientnachrichten an, die von allen Domänen gesendet wurden ( Daten anzeigen **für:** Alle Absenderdomänen sind standardmäßig ausgewählt). Sie können die Ergebnisse nach einer bestimmten Absenderdomäne filtern, indem Sie in der Dropdownliste auf "Daten anzeigen" klicken und die Absenderdomäne auswählen.  Wenn Sie auf einen bestimmten Datenpunkt (Tag) zeigen, wird die Anzahl der Nachrichten angezeigt.

  ![Senden der Volumeansicht im Bericht "SMTP-Authentifizierungsclients" im Security & Compliance Center](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- **Daten nach: TLS-Verwendung anzeigen:** Das Diagramm zeigt den Prozentsatz der TLS-Verwendung für alle NACHRICHTEN des SMTP-Authentifizierungsclients während des ausgewählten Zeitraums. In diesem Diagramm können Sie Benutzer und Systemkonten identifizieren und Maßnahmen ergreifen, die weiterhin ältere Versionen von TLS verwenden.

  ![TLS-Verwendungsansicht im Bericht "SMTP-Authentifizierungsclients" im Security & Compliance Center](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

Wenn Sie **in** einer Berichtsansicht auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**

Klicken **Sie auf "Anforderungsbericht",** um eine ausführlichere Version des Berichts in einer E-Mail-Nachricht zu erhalten. Sie können den Datumsbereich und die Empfänger angeben, die den Bericht empfangen sollen.

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a>Detailtabelle für den Bericht "SMTP-Authentifizierungsclients"

Wenn Sie auf **"Details anzeigen" klicken,** hängen die angezeigten Informationen vom Diagramm ab, das Sie betrachtet haben:

- **Daten anzeigen nach: Sendevolume:** Die folgenden Informationen sind in einer Tabelle dargestellt:

  - **Absenderadresse**
  - **Nachrichtenanzahl**

  Wenn Sie eine Zeile auswählen, werden die gleichen Details in einem Flyout angezeigt.

- **Anzeigen von Daten nach: TLS-Verwendung:** Die folgenden Informationen sind in einer Tabelle dargestellt:

  - **Absenderadresse**
  - **TLS1.0%**<sup>\*</sup>
  - **TLS1.1%**<sup>\*</sup>
  - **TLS1,2 %**<sup>\*</sup>
  - **Nachrichtenanzahl**

  <sup>\*</sup> In dieser Spalte werden der Prozentsatz und die Anzahl der Nachrichten des Absenders angezeigt.

Wenn Sie in einer **Detailtabelle auf Filter** klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**

Wenn Sie eine Zeile auswählen, werden ähnliche Details in einem Flyout angezeigt:

![Detailf flyout aus der Detailtabelle der TLS-Verwendungsansicht im SMTP-Authentifizierungsclientbericht](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

Klicken **Sie auf "Anforderungsbericht",** um eine ausführlichere Version des Berichts in einer E-Mail-Nachricht zu erhalten. Sie können den Datumsbereich und die Empfänger angeben, die den Bericht empfangen sollen.

Klicken Sie auf "Bericht anzeigen", um zur **Berichtsansicht zurück zu wechseln.**

## <a name="related-topics"></a>Verwandte Themen

Weitere Informationen zu anderen Einblicken im Nachrichtenflussdashboard finden Sie unter "Einblicke in den Nachrichtenfluss" [im Security & Compliance Center.](mail-flow-insights-v2.md)
