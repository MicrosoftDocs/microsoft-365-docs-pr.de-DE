---
title: Berichtsinformationen für Microsoft Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 03a9acc9-f29c-456b-9fb2-0f49474b2708
description: Erfahren Sie, wie Sie eine 4-monatige Ansicht Ihrer Bookings-Aktivität anzeigen können.
ms.openlocfilehash: ad0a21454cfe28cec521e545e587105e8f8a7454
ms.sourcegitcommit: 76f3c75413cc960289489d0ca29efadb8a9a5b31
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2021
ms.locfileid: "51887227"
---
# <a name="reporting-info-for-bookings"></a>Berichterstellungsinformationen für Bookings

Sie können nun eine viermonatige Ansicht Ihres Bookings-Kalenders in einer TSV-Datei anzeigen. Die TSV-Datei zeigt Ihnen vier Monate Daten an, Sie können jedoch im Laufe eines Jahres verschiedene Zeiträume für vier Monate auswählen.

Diese Informationen auf Terminebene können verwendet werden, um die Kundenaktivitäten rund um Ihren Bookings-Kalender zu visualisieren. BEI TSV-Dateien handelt es sich um Dateien mit getrennten Registerkarten. Sie können eine Datei wie diese mit einem beliebigen Text-Editor oder Tabellenkalkulationsprogramm, z. B. Excel, anzeigen oder bearbeiten.

## <a name="see-four-months-of-booking-activity"></a>Siehe vier Monate Buchungsaktivität

1. Wählen Sie im Bookings-Kalenderdashboard Die Option **Weitere Daten als TSV exportieren aus.**

:::image type="content" source="../media/bookings-activities.png" alt-text="Screenshot: 4 Monate Bookings-Aktivität":::

1. Speichern Sie die Datei mit einem neuen Namen, und geben Sie das XLS- oder xlsx-Format an.

1. Öffnen Sie die Datei, um die viermonatige Ansicht Ihres Bookings-Kalenders anzuzeigen.

1. Wählen Sie das Datum für Ihren Bericht aus, und wählen Sie **Exportieren aus.**

:::image type="content" source="../media/bookings-reporting-dates.png" alt-text="Screenshot: Wählen Sie einen Zeitraum aus, und exportieren Sie Daten in die TSV-Datei.":::

1. Der heruntergeladene Bericht enthält zusätzlich zu den vorhandenen Feldern einen neuen Satz von Feldern.

Der Bericht enthält die folgenden Felder.

 - **Datum & Zeit**
- **Name des Kunden**
- **Kunden-E-Mail**
- **Kundentelefon**
- **Kundenadresse**
- **Stab**
- **Dienst**
- **Standort**
- **Dauer (Minuten)**
- **Ereignistyp**

Der verbesserte Bericht enthält nun die folgenden Felder.

- **Preistyp**   Standardpreistyp, der für einen Dienst beim Erstellen des Diensts festgelegt ist.
- **Preis**   Preis, der dem gewählten Preistyp entspricht.
- **Währung**   Für ein Unternehmen festgelegter Währungstyp.
- **Cc-Teilnehmer**   Die Empfänger, die die E-Mail-Benachrichtigungen für eine Buchung erhalten. Dies kann in der Teams-App beim Erstellen einer Buchung angegeben werden.
- **Anzahl der angemeldeten Teilnehmer**   Wie viele Kunden einen Gruppenbuchungsdienst gebucht haben.
- **Aktivierte Textbenachrichtigungen**   Gibt an, ob Kunden SMS-textbezogene Benachrichtigungen erhalten können.
- **Benutzerdefinierte Felder**   Alle Fragen und Antworten im Zusammenhang mit einer einzelnen Buchung werden in diesem Feld kombiniert.
- **Buchungs-ID**   Dies ist hilfreich, um die gleichen Buchungen eines Gruppendiensts zu identifizieren.
