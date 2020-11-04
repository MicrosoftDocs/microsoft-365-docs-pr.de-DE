---
title: Einblicke und Berichte von SMTP-Authentifizierungsclients im Nachrichtenfluss-Dashboard
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie die SMTP-Authentifizierungs Einblicke und den Bericht im Nachrichtenfluss-Dashboard im Security & Compliance Center verwenden, um e-Mail-Absender in Ihrer Organisation zu überwachen, die authentifizierte SMTP (SMTP-Authentifizierung) zum Senden von e-Mail-Nachrichten verwenden.
ms.openlocfilehash: 54798dfcad50c263705b027c879fdf71d0dabfba
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877561"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a>Einblicke und Berichte von SMTP-Authentifizierungsclients im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Die Einblicke der **SMTP-Authentifizierungsclients** im [Nachrichtenfluss-Dashboard](mail-flow-insights-v2.md) und den zugeordneten [SMTP AUTH Clients-Bericht](#smtp-auth-clients-report) im [Security & Compliance Center](https://protection.office.com) heben die Verwendung des SMTP-Authentifizierungs Client-Übermittlungsprotokolls durch Benutzer oder Systemkonten in Ihrer Organisation hervor. Dieses Legacy Protokoll (das den Endpunkt SMTP.office365.com verwendet) bietet nur die Standardauthentifizierung und ist anfällig für die Verwendung durch kompromittierte Konten zum Senden von e-Mails. Die Einblicke und der Bericht ermöglichen es Ihnen, nach ungewöhnlichen Aktivitäten für SMTP-e-Mail-Übermittlungen zu suchen. Außerdem werden die TLS-Nutzungsdaten für Clients oder Geräte mithilfe der SMTP-Authentifizierung angezeigt.

Das Widget gibt die Anzahl der Benutzer oder Dienstkonten an, die in den letzten 7 Tagen das SMTP-Authentifizierungsprotokoll verwendet haben.

![SMTP-Authentifizierungsclients-Widget im Nachrichtenfluss-Dashboard im Security & Compliance Center](../../media/mfi-smtp-auth-clients-report-widget.png)

Wenn Sie auf die Anzahl der Nachrichten im Widget klicken, wird ein Flyout für **SMTP-Authentifizierungsclients** angezeigt. Das Flyout bietet eine aggregierte Ansicht der TLS-Nutzung und-Volumes für die letzte Woche.

![Details-Flyout nach dem Klicken auf das SMTP-Authentifizierungsclients-Widget im Nachrichtenfluss-Dashboard](../../media/mfi-smtp-auth-clients-report-details.png)

Sie können auf den Link **SMTP AUTH Clients Report** klicken, um zum Bericht SMTP AUTH Clients zu wechseln, wie im nächsten Abschnitt beschrieben.

## <a name="smtp-auth-clients-report"></a>SMTP-Auth-Clientbericht

### <a name="report-view-for-the-smtp-auth-clients-report"></a>Berichtsansicht für den Bericht "SMTP AUTH Clients"

Standardmäßig zeigt der Berichtdaten für die letzten 7 Tage an, aber Daten sind für die letzten 90 Tage verfügbar.

Der Overview-Abschnitt enthält die folgenden Diagramme:

- **Daten nach: Sending Volume** : Standardmäßig zeigt das Diagramm die Anzahl von SMTP-AUTH-Client Nachrichten an, die von allen Domänen gesendet wurden ( **Daten anzeigen für: alle Absenderdomänen** sind standardmäßig ausgewählt). Sie können die Ergebnisse auf eine bestimmte Absenderdomäne filtern, indem Sie in der Dropdownliste auf **Daten für anzeigen** und die Absenderdomäne auswählen klicken. Wenn Sie auf einen bestimmten Datenpunkt (Tag) zeigen, wird die Anzahl der Nachrichten angezeigt.

  ![Senden der Volumen Ansicht im Bericht "SMTP AUTH Clients" im Security & Compliance Center](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- **Daten nach: TLS Usage** : das Diagramm zeigt den Prozentsatz der TLS-Nutzung für alle SMTP-AUTH-Client Nachrichten während des ausgewählten Zeitraums. Dieses Diagramm ermöglicht es Ihnen, Benutzer und Systemkonten zu identifizieren und zu ergreifen, die noch ältere Versionen von TLS verwenden.

  ![TLS-Verwendungs Ansicht im Bericht SMTP AUTH Clients im Security & Compliance Center](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum** angeben.

Klicken Sie auf **Anforderungsbericht** , um eine detailliertere Version des Berichts in einer e-Mail-Nachricht zu erhalten. Sie können den Datumsbereich und die Empfänger angeben, um den Bericht zu empfangen.

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a>Tabellenansicht "Details" für den Bericht "SMTP AUTH Clients"

Wenn Sie auf **Detailtabelle anzeigen** klicken, hängt die Anzeige der angezeigten Informationen von dem Diagramm ab, das Sie gesucht haben:

- **Daten anzeigen nach: Sending Volume** : die folgenden Informationen werden in einer Tabelle angezeigt:

  - **Absenderadresse**
  - **Nachrichtenanzahl**

  Wenn Sie eine Zeile auswählen, werden dieselben Details in einem Flyout angezeigt.

- **Daten nach: TLS-Verwendung anzeigen** : die folgenden Informationen werden in einer Tabelle angezeigt:

  - **Absenderadresse**
  - **TLS 1.0%**<sup>\*</sup>
  - **TLS 1.1%**<sup>\*</sup>
  - **TLS 1.2%**<sup>\*</sup>
  - **Nachrichtenanzahl**

  <sup>\*</sup> In dieser Spalte werden sowohl der Prozentsatz als auch die Anzahl der Nachrichten des Absenders angezeigt.

Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum** angeben.

Wenn Sie eine Zeile auswählen, werden ähnliche Details in einem Flyout angezeigt:

![Details-Flyout aus der Detailtabelle der TLS-Einsatzansicht im SMTP-AUTH-Client-Bericht](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

Klicken Sie auf **Anforderungsbericht** , um eine detailliertere Version des Berichts in einer e-Mail-Nachricht zu erhalten. Sie können den Datumsbereich und die Empfänger angeben, um den Bericht zu empfangen.

Klicken Sie auf **Bericht anzeigen** , um zur Ansicht Berichte zurückzukehren.

## <a name="related-topics"></a>Verwandte Themen

Informationen zu weiteren Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).
