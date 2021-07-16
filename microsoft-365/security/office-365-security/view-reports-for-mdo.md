---
title: Microsoft Defender für Office 365-Berichte anzeigen
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratoren können erfahren, wie Sie defender für Office 365 Berichte finden und verwenden, die im Microsoft 365 Defender Portal verfügbar sind.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e8bb03202139137adf55c4c10230b1c4e99253ba
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454721"
---
# <a name="view-defender-for-office-365-reports-in-the-microsoft-365-defender-portal"></a>Anzeigen von Defender für Office 365 Berichte im Microsoft 365 Defender Portal

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft Defender für Office 365 Organisationen (z. B. Microsoft 365 E5-Abonnements oder Microsoft Defender für Office 365 Plan 1 oder Microsoft Defender für Office 365 Plan 2-Add-Ons) enthalten eine Vielzahl von sicherheitsrelevanten Berichten. Wenn Sie über die [erforderlichen Berechtigungen](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)verfügen, können Sie diese Berichte im Microsoft 365 Defender-Portal anzeigen, indem Sie zu  \> **E-Mail-Berichte &** \> **Zusammenarbeit e-Mail & Zusammenarbeitsberichte wechseln.** Um direkt zur Seite **"E-Mail & Zusammenarbeitsberichte"** zu wechseln, öffnen Sie <https://security.microsoft.com/emailandcollabreport> .

![Seite "E-Mail-& Zusammenarbeitsberichte" im Microsoft 365 Defender-Portal](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> E-Mail-Sicherheitsberichte, für die Defender nicht für Office 365 erforderlich ist, werden in [den E-Mail-Sicherheitsberichten im Microsoft 365 Defender-Portal](view-email-security-reports.md)beschrieben.
>
> Berichte, die sich auf den Nachrichtenfluss beziehen, befinden sich jetzt im Exchange Admin Center (EAC). Weitere Informationen zu diesen Berichten finden Sie unter [Nachrichtenflussberichte im neuen Exchange Admin Center.](/exchange/monitoring/mail-flow-reports/mail-flow-reports)

## <a name="safe-attachments-file-types-report"></a>Tresor Anlagendateitypenbericht

> [!NOTE]
> Der **Bericht Tresor Dateitypen "Anlagen"** wird schließlich entfernt. Die gleichen Informationen sind im [Bedrohungsschutzstatusbericht](#threat-protection-status-report)verfügbar.

## <a name="safe-attachments-message-disposition-report"></a>Tresor Dispositionsbericht über Anlagennachrichten

> [!NOTE]
> Der **Bericht Tresor Anlagen zur Nachrichtendisposition** wird schließlich entfernt. Die gleichen Informationen sind im [Bedrohungsschutzstatusbericht](#threat-protection-status-report)verfügbar.

## <a name="mail-latency-report"></a>E-Mail-Latenzbericht

Der **E-Mail-Latenzbericht** zeigt Ihnen eine aggregierte Ansicht der E-Mail-Zustellungs- und Detonationslatenz in Ihrer Organisation. Die E-Mail-Zustellungszeiten im Dienst werden von einer Reihe von Faktoren beeinflusst, und die absolute Zustellzeit in Sekunden ist häufig kein guter Indikator für Erfolg oder Problem. Eine langsame Zustellungszeit an einem Tag kann als durchschnittliche Zustellzeit an einem anderen Tag betrachtet werden oder umgekehrt. Dadurch wird versucht, die Nachrichtenübermittlung basierend auf statistischen Daten über die beobachteten Zustellungszeiten anderer Nachrichten zu qualifizieren.

Clientseitige und Netzwerklatenz sind nicht enthalten.

Um den Bericht anzuzeigen, öffnen Sie das [portal Microsoft 365 Defender](https://security.microsoft.com), wechseln Sie zu **Berichte** \> **E-Mail & Zusammenarbeit** \> **E-Mail & Zusammenarbeitsberichte.** Suchen Sie auf der Seite **"E-Mail-& Zusammenarbeitsberichte"** den **Bericht "E-Mail-Latenz",** und klicken Sie dann auf **"Details anzeigen".** Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/mailLatencyReport> .

![E-Mail-Latenzberichts-Widget auf der Seite "E-Mail & Zusammenarbeitsberichte"](../../media/mail-latency-report-widget.png)

Auf der Seite **"E-Mail-Latenzbericht"** sind die folgenden Registerkarten auf der Seite **"E-Mail-Latenzbericht"** verfügbar:

- **50. Quantil:** Dies ist die Mitte für die Nachrichtenübermittlungszeiten. Sie können diesen Wert als durchschnittliche Lieferzeit betrachten. Diese Registerkarte ist standardmäßig ausgewählt.
- **90. Perzentil:** Dies weist auf eine hohe Latenz für die Nachrichtenübermittlung hin. Nur 10 % der Nachrichten dauerten länger als dieser Wert für die Übermittlung.
- **99. Perzentil:** Gibt die höchste Latenz für die Nachrichtenübermittlung an.

Unabhängig von der ausgewählten Registerkarte zeigt das Diagramm Nachrichten in den folgenden Kategorien an:

- **E-Mail-Zustellungslatenz**
- **Detonationen**

Wenn Sie mit dem Mauszeiger auf eine Kategorie im Diagramm zeigen, sehen Sie eine Aufschlüsselung der Latenz in jeder Kategorie.

![50. Perzentilansicht des E-Mail-Latenzberichts](../../media/mail-latency-report-50th-percentile-view.png)

Wenn Sie auf **"Filtern"** klicken, können Sie sowohl das Diagramm als auch die Detailtabelle nach den folgenden Werten filtern:

- **Datum (UTC):** **Startdatum** und **Enddatum**
- **Nachrichtenansicht:** Einer der folgenden Werte:
  - **Alle Nachrichten**
  - **Nachrichten, die Anlagen oder URLs enthalten**
  - **Detonierte Nachrichten**

Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**

In der Detailtabelle unterhalb des Diagramms sind die folgenden Informationen verfügbar:

- **Datum (UTC)**
- **Perzentile:** **50**, **90** oder **99**
- **Nachrichtenanzahl**
- **Gesamtlatenz**

## <a name="threat-protection-status-report"></a>Threat Protection-Statusbericht

Der **Bedrohungsschutz-Statusbericht** ist eine einzelne Ansicht, die Informationen zu schädlichen Inhalten und schädlichen E-Mails zusammenführt, die von [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) und Microsoft Defender für Office 365 erkannt und blockiert wurden. Weitere Informationen finden Sie unter [Bedrohungsschutzstatusbericht.](view-email-security-reports.md#threat-protection-status-report)

## <a name="url-threat-protection-report"></a>URL-Bedrohungsschutzbericht

Der Bericht zum SCHUTZ VOR **URL-Bedrohungen** enthält Zusammenfassungen und Trendansichten für erkannte Bedrohungen und Aktionen, die bei URL-Klicks im Rahmen [Tresor Links](safe-links.md)ausgeführt werden. In diesem Bericht werden keine Klickdaten von Benutzern angezeigt, bei denen für die angewendete Richtlinie Tresor Verknüpfungen die Option **"Benutzerklicks nicht nachverfolgen"** ausgewählt ist.

Um den Bericht anzuzeigen, öffnen Sie das [portal Microsoft 365 Defender](https://security.microsoft.com), wechseln Sie zu **Berichte** \> **E-Mail & Zusammenarbeit** \> **E-Mail & Zusammenarbeitsberichte.** Suchen Sie auf der Seite **"E-Mail & Zusammenarbeitsberichte"** die **Seite "URL-Schutz",** und klicken Sie dann auf **"Details anzeigen".** Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/URLProtectionActionReport> .

![URL-Schutzberichts-Widget auf der Seite "E-Mail & Zusammenarbeitsberichte"](../../media/url-protection-report-widget.png)

Die verfügbaren Ansichten auf der Berichtsseite zum **URL-Bedrohungsschutz** werden in den folgenden Abschnitten beschrieben.

> [!NOTE]
> Dies ist ein *Schutztrendbericht,* d. h. Daten stellen Trends in einem größeren Dataset dar. Daher sind die Daten in den Diagrammen hier nicht in Echtzeit verfügbar, die Daten in der Detailtabelle sind jedoch so, dass eine geringfügige Abweichung zwischen den beiden angezeigt wird. Die Diagramme werden alle vier Stunden aktualisiert und enthalten Daten für die letzten 90 Tage.

### <a name="view-data-by-url-click-protection-action"></a>Anzeigen von Daten nach URL-Klickschutzaktion

![URL-Klickschutz-Aktionsansicht im URL-Bedrohungsschutzbericht](../../media/url-threat-protection-report-url-click-protection-action-view.png)

Die Aktionsansicht **"Daten nach URL anzeigen" zeigt** die Anzahl der URL-Klicks von Benutzern in der Organisation und die Ergebnisse des Klicks an:

- **Zulässig:** Der Benutzer konnte zur URL navigieren.
- **Blockiert:** Der Benutzer wurde am Navigieren zur URL gehindert.
- **Blockiert und durchgeklickt:** Der Benutzer hat sich entschieden, weiter zur URL zu navigieren.
- **Während des Scans durchgeklickt:** Der Benutzer hat auf den Link geklickt, bevor die Überprüfung abgeschlossen war.

Ein Klick gibt an, dass der Benutzer durch die Blockierungsseite zur schädlichen Website geklickt hat (Administratoren können click through in Tresor Links policies deaktivieren).

Wenn Sie auf **Filter** klicken, können Sie den Bericht und die Detailtabelle ändern, indem Sie einen oder mehrere der folgenden Werte im angezeigten Flyout auswählen:

- **Datum (UTC):** **Startdatum** und **Enddatum**
- **Erkennung:**
  - **Zulässig**
  - **Gesperrt**
  - **Blockiert und durchgeklickt**
  - **Während des Scans durchgeklickt**
- **Domänen:** Die in den Berichtergebnissen aufgeführten URL-Domänen.
- **Empfänger**

Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**

Die Detailtabelle unterhalb des Diagramms bietet die folgende Nahezu-Echtzeit-Ansicht aller Klicks, die in der Organisation während der letzten 7 Tage aufgetreten sind:

- **Klickzeit**
- **Benutzende**
- **URL**
- **Action**
- **App**

### <a name="view-data-by-url-click-by-application"></a>Anzeigen von Daten nach URL-Klick nach Anwendung

![URL-Klick nach Anwendungsansicht im URL-Bedrohungsschutzbericht](../../media/url-threat-protection-report-url-click-by-application-view.png)

Die **Ansichtsdaten nach URL klicken nach Anwendungsansicht** zeigt die Anzahl der URL-Klicks von Apps an, die Tresor Links unterstützen:

- **E-Mail-Client**
- **PowerPoint**
- **Word**
- **Excel**
- **OneNote**
- **Visio**
- **Teams**
- **Sonstige**

Wenn Sie auf **Filter** klicken, können Sie den Bericht und die Detailtabelle ändern, indem Sie einen oder mehrere der folgenden Werte im angezeigten Flyout auswählen:

- **Datum (UTC):** **Startdatum** und **Enddatum**
- **Erkennung:** Verfügbare Apps aus dem Diagramm.
- **Domänen:** Die in den Berichtergebnissen aufgeführten URL-Domänen.
- **Empfänger**

Wenn Sie die Konfiguration der Filter abgeschlossen haben, klicken Sie auf **"Anwenden",** **"Abbrechen"** oder **"Filter löschen".**

Die Detailtabelle unterhalb des Diagramms bietet die folgende Nahezu-Echtzeit-Ansicht aller Klicks, die in der Organisation während der letzten 7 Tage aufgetreten sind:

- **Klickzeit**
- **Benutzende**
- **URL**
- **Action**
- **App**

## <a name="additional-reports-to-view"></a>Weitere anzuzeigende Berichte

Zusätzlich zu den in diesem Artikel beschriebenen Berichten stehen weitere Berichte zur Verfügung, wie in der folgenden Tabelle beschrieben:

<br>

****

|Bericht|Thema|
|---|---|
|**Explorer** (Microsoft Defender für Office 365 Plan 2) oder **Echtzeiterkennungen** (Microsoft Defender für Office 365 Plan 1)|[Sicherheitsrisiken-Explorer (und Echtzeit-Erkennung)](threat-explorer.md)|
|E-Mail-Sicherheitsberichte, die Defender nicht für Office 365 erfordern|[Anzeigen von E-Mail-Sicherheitsberichten im Microsoft 365 Defender Portal](view-email-security-reports.md)|
|Nachrichtenflussberichte im Exchange Admin Center (EAC)|[Nachrichtenflussberichte im neuen Exchange Admin Center](/exchange/monitoring/mail-flow-reports/mail-flow-reports)|
|

PowerShell-Berichts-Cmdlets:

<br>

****

|Bericht|Thema|
|---|---|
|Häufigste Absender und Empfänger|[Get-MailTrafficTopReport](/powershell/module/exchange/get-mailtraffictopreport) <p> [Get-MailTrafficSummaryReport](/powershell/module/exchange/get-mailtrafficsummaryreport)|
|Häufigste Schadsoftware|[Get-MailTrafficSummaryReport](/powershell/module/exchange/get-mailtrafficsummaryreport)|
|E-Mail-Datenverkehr|[Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport) <p> [Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport)|
|Sichere Links|[Get-SafeLinksAggregateReport](/powershell/module/exchange/get-safelinksaggregatereport) <p> [Get-SafeLinksDetailReport](/powershell/module/exchange/get-safelinksdetailreport)|
|Kompromittierte Benutzer|[Get-CompromisedUserAggregateReport](/powershell/module/exchange/get-compromiseduseraggregatereport) <p> [Get-CompromisedUserDetailReport](/powershell/module/exchange/get-compromiseduserdetailreport)|
|Nachrichtenflussstatus|[Get-MailflowStatusReport](/powershell/module/exchange/get-mailflowstatusreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a>Welche Berechtigungen sind erforderlich, um den Defender für Office 365 Berichte anzuzeigen?

Um die in diesem Artikel beschriebenen Berichte anzuzeigen und zu verwenden, müssen Sie Mitglied einer der folgenden Rollengruppen im Microsoft 365 Defender Portal sein:

- **Organisationsverwaltung**
- **Sicherheitsadministrator**
- **Sicherheitsleseberechtigter**
- **Globaler Leseberechtigter**

Weitere Informationen finden Sie unter [Berechtigungen im Microsoft 365 Defender-Portal](permissions-microsoft-365-security-center.md).

**Hinweis:** Das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory Rolle im Microsoft 365 Admin Center bietet Benutzern die erforderlichen Berechtigungen im Microsoft 365 Defender-Portal _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).

## <a name="what-if-the-reports-arent-showing-data"></a>Was geschieht, wenn in den Berichten keine Daten angezeigt werden?

Wenn in Ihrem Defender keine Daten für Office 365-Berichte angezeigt werden, überprüfen Sie, ob Ihre Richtlinien ordnungsgemäß eingerichtet sind. In Ihrer Organisation müssen [Tresor Verknüpfungsrichtlinien](set-up-safe-links-policies.md) und [Tresor Anlagenrichtlinien](set-up-safe-attachments-policies.md) definiert sein, damit Defender für Office 365 Schutz vorhanden ist. Siehe auch [Antispam- und Antischadsoftwareschutz.](anti-spam-and-anti-malware-protection.md)

## <a name="related-topics"></a>Verwandte Themen

[Intelligente Berichte und Einblicke im Microsoft 365 Defender-Portal](reports-and-insights-in-security-and-compliance.md)

[Rollenberechtigungen (Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
