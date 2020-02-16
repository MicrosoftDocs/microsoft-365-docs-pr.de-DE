---
title: SMTP-Auth-Clientbericht
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
description: Administratoren können sich im Nachrichtenfluss-Dashboard im Security & Compliance Center über den Bericht über SMTP-Authentifizierungsclients informieren.
ms.openlocfilehash: e80ee36fd7e94cc4dc2791f71ae594f0182b4269
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42082619"
---
# <a name="smtp-auth-clients-report"></a>SMTP-Auth-Clientbericht

Der Bericht über **SMTP-Authentifizierungsclients** zeigt die Verwendung des SMTP-Authentifizierungs Client-Übermittlungsprotokolls durch Benutzer oder Systemkonten in Ihrer Organisation an. Dieses Legacy Protokoll (das den Endpunkt SMTP.office365.com verwendet) bietet nur die Standardauthentifizierung und ist anfällig für die Verwendung durch kompromittierte Konten zum Senden von e-Mails.  In diesem Bericht können Sie nach ungewöhnlichen Aktivitäten suchen. Außerdem werden die TLS-Nutzungsdaten für Clients oder Geräte mithilfe der SMTP-Authentifizierung angezeigt.

Das Widget, das im Nachrichtenfluss-Dashboard angezeigt wird, gibt die Anzahl der Benutzer oder Dienstkonten an, die in den letzten 7 Tagen das SMTP-Authentifizierungsprotokoll verwendet haben.

![Der Bericht über SMTP-Authentifizierungsclients im Nachrichtenfluss-Dashboard im Security & Compliance Center](../../media/smtp-auth-clients-report-selected.png)

Durch Klicken auf das Widget wird ein Flyout geöffnet, das eine aggregierte Ansicht der TLS-Nutzung und-Volumes für die letzte Woche enthält.

![Das Flyout im Bericht "SMTP AUTH Clients"](../../media/smtp-auth-clients-flyout.png)

Wenn Sie auf den Link **SMTP AUTH Clients Report** klicken, werden zwei Hauptdaten Pivots und zwei Datenansichten angezeigt. Die Daten Pivots sind das **sendende Volume** und die **TLS-Verwendung**. Die Datenansichten sind das Diagramm und die Detailtabelle.

Die Ansicht **sendende Volumes** zeigt die Anzahl der Nachrichten an, die mit SMTP-Authentifizierung für den angegebenen Zeitraum gesendet wurden. Sie können den Bereich anpassen, indem Sie auf **Filter**klicken. Das Diagramm ist nach Absenderdomäne organisiert. Sie können separate Daten für jede Domäne anzeigen, indem Sie die Domäne in der Dropdownliste **Daten anzeigen für** auswählen.

![Senden des Volumes im Bericht "SMTP AUTH Clients"](../../media/smtp-auth-clients-report-sending-volume.png)

Sie können detaillierte Informationen zu den Absendern und ihren Nachrichten Zählern anzeigen, indem Sie auf **Tabelle Details anzeigen**klicken. Klicken Sie auf **Bericht anzeigen**, um zum Diagramm zurückzukehren.

![Tabelle "Details" für das Senden des Volumes im Bericht "SMTP AUTH Clients"](../../media/smtp-auth-clients-report-details-sending-volume.png)

Der **TLS-Verwendungs** Pivot ist aufgrund der bevorstehenden veralteten Version von TLS 1.0 und TLS 1.1 in Office 365 wichtig. Viele ältere Geräte und Anwendungen können keine e-Mails senden, wenn Sie nur TLS 1.0 mit SMTP-Authentifizierung verwenden können. Mit diesem Pivot können Sie Benutzer und Systemkonten identifizieren und ausführen, die noch ältere Versionen von TLS verwenden.

![TLS-Verwendung im Bericht "SMTP AUTH Clients"](../../media/smtp-auth-clients-report-tls-usage.png)

Sie können detaillierte Informationen über die Absender, die Versionen von TLS, die Sie mit SMTP-Authentifizierung verwenden, und deren Nachrichtenanzahl anzeigen, indem Sie auf **Detailtabelle anzeigen**klicken. Klicken Sie auf **Bericht anzeigen**, um zum Diagramm zurückzukehren.

Sie können auch eine detailliertere Version des Berichts herunterladen, indem Sie auf Anforderungsbericht klicken.

![Tabelle "Details" für die TLS-Verwendung im Bericht "SMTP AUTH Clients"](../../media/smtp-auth-clients-report-details-tls-usage.png)

## <a name="see-also"></a>Siehe auch

Weitere Informationen zu anderen e-Mail-Fluss-Einblicken im Nachrichtenfluss-Dashboard finden Sie unter [Mail Flow Insights in the Security & Compliance Center](mail-flow-insights-v2.md).
