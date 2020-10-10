---
title: Anzeigen von Berichten für Advanced Threat Protection
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365-initiative-defender-office365
description: Suchen und Verwenden von Berichten für Office 365 Advanced Threat Protection im Security &amp; Compliance Center.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c1e1df0d4c1da228da1e09a626dd388d8d7cf7aa
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413448"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a>Anzeigen von Berichten für Office 365 Advanced Threat Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Office 365 Advanced Threat Protection (ATP)-Organisationen (beispielsweise Microsoft 365 E5-Abonnements oder ATP Plan 1 oder ATP Plan 2-Add-ons) enthalten eine Vielzahl von sicherheitsbezogenen Berichten. Wenn Sie über die [erforderlichen Berechtigungen](#what-permissions-are-needed-to-view-the-atp-reports)verfügen, können Sie diese Berichte im Security & Compliance Center anzeigen, indem Sie **Reports** zum \> **Dashboard**Berichte wechseln. Wenn Sie direkt zum Dashboard Berichte wechseln möchten, öffnen Sie <https://protection.office.com/insightdashboard> .

![Das Dashboard "Berichte" im Security & Compliance Center](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="advanced-threat-protection-file-types-report"></a>Advanced Threat Protection-Bericht zu Dateitypen

Der Bericht über **Erweiterte Bedrohungsschutz-Dateitypen** zeigt Ihnen den Typ der Dateien an, die von [sicheren Anlagen](atp-safe-attachments.md)als schädlich erkannt wurden.

 Die aggregierte Ansicht des Berichts ermöglicht eine Filterung von 90 Tagen, während in der Detailansicht nur 10 Tage Filterung zulässig ist.

Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie zu **Berichte** \> - **Dashboard** , und wählen Sie **Office ATP-Dateitypen**aus. Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=ATPFileReport> .

![Office ATP-Dateitypen-Widget im Dashboard "Berichte"](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> Die Informationen in diesem Bericht sind auch im [Nachrichten Disposition-Bericht für erweiterte Bedrohungen](#advanced-threat-protection-message-disposition-report)verfügbar.

### <a name="report-view-for-the-advanced-threat-protection-file-types-report"></a>Berichtsansicht für den Bericht "Erweiterte Bedrohungsschutz-Dateitypen"

Die folgenden Ansichten sind verfügbar:

- **Daten nach: File anzeigen**: das Diagramm enthält die folgenden Informationen:

  - **Böswillige Excel-Anlagen**
  - **Böswillige Flash-Anlagen**
  - **Böswillige PDF-Anlagen**
  - **Böswillige PowerPoint-Anlagen**
  - **Böswillige URLs**
  - **Böswillige Word-Anlagen**
  - **Böswillige ausführbare Anlagen**
  - **Sonstige**

  Wenn Sie den Mauszeiger über einen bestimmten Tag (Datenpunkt) bewegen, sehen Sie die Aufschlüsselung der Typen von bösartigen Dateien, die durch [sichere Anlagen](atp-safe-attachments.md) und [Schutz vor Schadsoftware in EoP](anti-malware-protection.md)erkannt wurden.

  ![Datei Ansicht im Bericht "ATP-Dateitypen"](../../media/atp-file-types-report-file-view.png)

  Wenn Sie auf **Filter**klicken, können Sie den Bericht mit den folgenden Filtern ändern:

  - **Start Datum** und **Enddatum**
  - Die gleichen Dateityp Werte, die im Diagramm sichtbar sind.

- **Daten anzeigen nach: Nachricht**: das Diagramm enthält die folgenden Informationen:

  - **Zugriff blockieren**
  - **Ersetzte Nachrichten**
  - **Überwachte Nachrichten**
  - **Durch dynamische e-Mail-Zustellung ersetzt**: Weitere Informationen finden Sie unter [Dynamic Delivery in Policies for Safe Attachments](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).

  ![Nachrichtenansicht im Bericht "ATP-Dateitypen"](../../media/atp-file-types-report-message-view.png)

  Wenn Sie auf **Filter**klicken, können Sie den Bericht mit den folgenden Filtern ändern:

  - **Start Datum** und **Enddatum**
  - Dieselben Nachrichten Dispositions Werte, die im Diagramm zur Verfügung stehen, und der Wert der zusätzlichen **Nachrichten** , die übergeben wurden.

### <a name="details-table-view-for-the-advanced-threat-protection-file-types-report"></a>Detailtabellen Ansicht für den Bericht "Erweiterte Bedrohungsschutz-Dateitypen"

Wenn Sie auf **Detailtabelle anzeigen**klicken, bietet der Bericht eine nahezu Echtzeitansicht aller Klicks, die innerhalb der Organisation für die letzten 10 Tage stattfinden. Die angezeigten Informationen hängen von dem Diagramm ab, das Sie untersucht haben:

- **Daten nach: File anzeigen**:

  - **Date**
  - **Empfängeradresse**
  - **Absenderadresse**
  - **Nachrichten-ID**: verfügbar im Kopfzeilenfeld nach **richten-ID** im Nachrichtenkopf und sollte eindeutig sein. Ein Beispielwert ist `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (Beachten Sie die spitzen Klammern).
  - **Datei**

  Wenn Sie auf **Filter**klicken, können Sie den Bericht mit den folgenden Filtern ändern:

  - **Start Datum** und **Enddatum**
  - Die gleichen Dateityp Werte, die im Diagramm sichtbar sind.

- **Anzeigen von Daten nach: Nachricht**:

  - **Date**
  - **Empfängeradresse**
  - **Absenderadresse**
  - **Nachrichten-ID**
  - **Datei**
  - **Betreff**

  Wenn Sie auf **Filter**klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:

  - **Start Datum** und **Enddatum**
  - Dieselben Nachrichten Dispositions Werte, die im Diagramm zur Verfügung stehen, und der Wert der zusätzlichen **Nachrichten** , die übergeben wurden.

Klicken Sie auf **Bericht anzeigen**, um wieder zur Berichtsansicht zu gelangen.

## <a name="advanced-threat-protection-message-disposition-report"></a>Advanced Threat Protection-Bericht zum Nachrichtenstatus

Der Bericht " **ATP-Nachrichten Disposition** " zeigt die Aktionen an, die für e-Mail-Nachrichten durchgeführt wurden, die als schädliche Inhalte erkannt wurden.

Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **Office ATP-Nachrichten Disposition**aus. Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=ATPMessageReport> .

![Office 365 Widget "ATP-Nachrichten Disposition" im Dashboard "Berichte"](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> Die Informationen in diesem Bericht sind auch im [Bericht erweiterte Bedrohungsschutz-Dateitypen](#advanced-threat-protection-file-types-report)verfügbar.

### <a name="report-view-for-the-advanced-threat-protection-message-disposition-report"></a>Berichtsansicht für den Nachrichten Disposition-Bericht "Advanced Threat Protection"

Die folgenden Ansichten sind verfügbar:

- **Daten anzeigen nach: Nachricht**: das Diagramm enthält die folgenden Informationen:

  - **Zugriff blockieren**
  - **Ersetzte Nachrichten**
  - **Überwachte Nachrichten**
  - **Durch dynamische e-Mail-Zustellung ersetzt**: Weitere Informationen finden Sie unter [Dynamic Delivery in Policies for Safe Attachments](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).

  ![Nachrichtenansicht im Bericht "ATP-Dateitypen"](../../media/atp-file-types-report-message-view.png)

  Wenn Sie auf **Filter**klicken, können Sie den Bericht mit den folgenden Filtern ändern:

  - **Start Datum** und **Enddatum**
  - Dieselben Nachrichten Dispositions Werte, die im Diagramm zur Verfügung stehen, und der Wert der zusätzlichen **Nachrichten** , die übergeben wurden.

- **Daten nach: File anzeigen**: das Diagramm enthält die folgenden Informationen:

  - **Böswillige Excel-Anlagen**
  - **Böswillige Flash-Anlagen**
  - **Böswillige PDF-Anlagen**
  - **Böswillige PowerPoint-Anlagen**
  - **Böswillige URLs**
  - **Böswillige Word-Anlagen**
  - **Böswillige ausführbare Anlagen**
  - **Sonstige**

  Wenn Sie den Mauszeiger über einen bestimmten Tag (Datenpunkt) bewegen, sehen Sie die Aufschlüsselung der Typen von bösartigen Dateien, die durch [sichere Anlagen](atp-safe-attachments.md) und [Schutz vor Schadsoftware in EoP](anti-malware-protection.md)erkannt wurden.

  ![Datei Ansicht im Bericht "ATP-Dateitypen"](../../media/atp-file-types-report-file-view.png)

  Wenn Sie auf **Filter**klicken, können Sie den Bericht mit den folgenden Filtern ändern:

  - **Start Datum** und **Enddatum**
  - Die gleichen Dateityp Werte, die im Diagramm sichtbar sind.

### <a name="details-table-view-for-the-advanced-threat-protection-message-disposition-report"></a>Ansicht "Detailtabelle" für den Bericht "Erweiterte Bedrohungsschutz Nachrichten Disposition"

Wenn Sie auf **Detailtabelle anzeigen**klicken, bietet der Bericht eine nahezu Echtzeitansicht aller Klicks, die innerhalb der Organisation für die letzten 10 Tage stattfinden. Die angezeigten Informationen hängen von dem Diagramm ab, das Sie untersucht haben:

- **Anzeigen von Daten nach: Nachricht**:

  - **Date**
  - **Empfängeradresse**
  - **Absenderadresse**
  - **Nachrichten-ID**
  - **Datei**
  - **Betreff**

  Wenn Sie auf **Filter**klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:

  - **Start Datum** und **Enddatum**
  - Dieselben Nachrichten Dispositions Werte, die im Diagramm zur Verfügung stehen, und der Wert der zusätzlichen **Nachrichten** , die übergeben wurden.

- **Daten nach: File anzeigen**:

  - **Date**
  - **Empfängeradresse**
  - **Absenderadresse**
  - **Nachrichten-ID**
  - **Datei**

  Wenn Sie auf **Filter**klicken, können Sie den Bericht mit den folgenden Filtern ändern:

  - **Start Datum** und **Enddatum**
  - Die gleichen Dateityp Werte, die im Diagramm sichtbar sind.

Klicken Sie auf **Bericht anzeigen**, um wieder zur Berichtsansicht zu gelangen.

## <a name="threat-protection-status-report"></a>Threat Protection-Statusbericht

Der **Statusbericht "Threat Protection** " ist eine einzelne Ansicht, in der Informationen zu böswilligen Inhalten und böswilligen e-Mails zusammengefasst werden, die durch [Exchange Online Schutz](exchange-online-protection-overview.md) (EoP) und Office 365 ATP erkannt und blockiert wurden. Weitere Informationen finden Sie unter [Threat Protection-Statusbericht](view-email-security-reports.md#threat-protection-status-report).

## <a name="url-threat-protection-report"></a>URL-Bedrohungsschutz Bericht

Der **Bericht über den URL-Bedrohungsschutz** bietet zusammenfassende und Trend Ansichten für erkannte Bedrohungen und Aktionen, die bei URL-Klicks im Rahmen von [sicheren Links](atp-safe-links.md)ausgeführt werden. In diesem Bericht werden keine klickdaten von Benutzern angezeigt, bei denen die Richtlinie für sichere Links angewendet die Option **Benutzerklicks nicht nachverfolgen** aktiviert hat.

Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **URL-Schutzbericht**aus. Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=URLProtectionActionReport> .

![Widget "URL Protection-Bericht" im Dashboard "Berichte"](../../media/url-protection-report-widget.png)

> [!NOTE]
> Hierbei handelt es sich um einen *Schutz Trendbericht*, was bedeutet, dass Datentrends in einem größeren DataSet darstellen. Daher sind die Daten in der Aggregatansicht hier nicht in Echtzeit verfügbar, aber die Daten in der Detailtabellen Ansicht sind möglicherweise geringfügig Diskrepanz zwischen den beiden Ansichten angezeigt.

### <a name="report-view-for-the-url-threat-protection-report"></a>Berichtsansicht für den URL-Bedrohungsschutz Bericht

Der **URL Threat Protection** -Bericht enthält zwei aggregierte Ansichten, die einmal alle vier Stunden aktualisiert werden, sodass Daten für die letzten 90 Tage angezeigt werden:

- **Aktion zum Schutz vor URLs**: zeigt die Anzahl der URL-Klicks von Benutzern in der Organisation und die Ergebnisse des Klick Vorgangs an:

  - **Blockiert** (der Benutzer wurde für die Navigation zur URL gesperrt)
  - **Blockiert und durchgeklickt**
  - **Durch Klicken während der Überprüfung**

  Ein Klick gibt an, dass der Benutzer auf die Seite blockieren zur böswilligen Website geklickt hat (Administratoren können durch Klicken auf Richtlinien für sichere Links deaktivieren).

  Wenn Sie auf **Filter**klicken, können Sie den Bericht mit den folgenden Filtern ändern:

  - **Start Datum** und **Enddatum**
  - Die verfügbaren Klick Schutzaktionen sowie den **zulässigen** Wert (der Benutzer durfte zur URL navigieren).

  ![Aktionsansicht für URL-Klick Schutz im URL Threat Protection-Bericht](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- **URL-Klick nach Anwendung**: zeigt die Anzahl der URL-Klicks von Anwendungen an, die sichere Links unterstützen:

  - **E-Mail-Client**
  - **PowerPoint**
  - **Word**
  - **Excel**
  - **OneNote**
  - **Visio**
  - **Teams**
  - **Other**

  Wenn Sie auf **Filter**klicken, können Sie den Bericht mit den folgenden Filtern ändern:

  - **Start Datum** und **Enddatum**
  - Die verfügbaren Anwendungen.

### <a name="details-table-view-for-the-url-threat-protection-report"></a>Detailtabellen Ansicht für den URL Threat Protection-Bericht

Wenn Sie auf **Details-Tabelle anzeigen**klicken, bietet der Bericht eine nahezu Echtzeitansicht aller Klicks, die innerhalb der Organisation für die letzten 7 Tage mit den folgenden Details geschehen:

- **Klicken Sie auf Zeit**
- **Benutzende**
- **URL**
- **Aktion**
- **App**

Wenn Sie in der Detailtabellen Ansicht auf **Filter** klicken, können Sie nach denselben Kriterien wie in der Berichtsansicht filtern, auch nach **Domänen** oder **Empfängern** , die durch Kommas getrennt sind.

Klicken Sie auf **Bericht anzeigen**, um wieder zur Berichtsansicht zu gelangen.

## <a name="additional-reports-to-view"></a>Zusätzliche Berichte zur Anzeige

Zusätzlich zu den in diesem Thema beschriebenen ATP-Berichten stehen verschiedene andere Berichte zur Verfügung, wie in der folgenden Tabelle beschrieben:

****

|Bericht|Thema|
|---|---|
|**Explorer** (ATP-Plan 2) oder **Echt Zeit Erkennungen** (ATP-Plan 1)|[Sicherheitsrisiken-Explorer (und Echtzeit-Erkennung)](threat-explorer.md)|
|**E-Mail-Sicherheitsberichte**wie der Bericht über die häufigsten Absender und Empfänger, der Bericht "Spoof-e-Mail" und der Spam Erkennungs Bericht.|[Anzeigen von E-Mail-Sicherheitsberichten im Security & Compliance Center](view-email-security-reports.md)|
|**Nachrichtenfluss Berichte**, wie der Weiterleitungs Bericht, der e-Mail-Fluss Statusbericht und der Bericht über die obersten Absender und Empfänger.|[Anzeigen von Nachrichtenfluss Berichten im Security & Compliance Center](view-mail-flow-reports.md)|
|**URL-Ablaufverfolgung für sichere Links** (nur PowerShell). Die Ausgabe dieses Cmdlets zeigt die Ergebnisse von Aktionen für sichere Links in den letzten sieben Tagen an.|[Get-UrlTrace](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|**Ergebnisse von e-Mail-Datenverkehr für EoP und ATP** (nur PowerShell). Die Ausgabe dieses Cmdlets enthält Informationen zu Domäne, Datum, Ereignistyp, Richtung, Aktion und Nachrichtenanzahl.|[Get-MailTrafficATPReport](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|**E-Mail-Detailberichte für EoP und ATP-Erkennungen** (nur PowerShell). Die Ausgabe dieses Cmdlets enthält Details zu bösartigen Dateien oder URLs, Phishing-versuchen, Identitätswechsel und anderen potenziellen Bedrohungen in e-Mails oder Dateien.|[Get-MailDetailATPReport](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a>Welche Berechtigungen sind zum Anzeigen der ATP-Berichte erforderlich?

Damit Sie die in diesem Thema beschriebenen Berichte anzeigen und verwenden können, **muss Ihnen eine entsprechende Rolle sowohl für das Security &amp; Compliance Center als auch für das Exchange Admin Center zugewiesen sein**.

- Für das Security & Compliance Center muss eine der folgenden Rollen zugewiesen sein:

  - Organisationsverwaltung
  - Sicherheits Administrator (Dies kann im Azure Active Directory Admin Center zugewiesen werden ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))
  - Sicherheits Operator (Dies kann im Azure Active Directory Admin Center zugewiesen werden ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))
  - Sicherheitsleseberechtigter

- Für Exchange Online müssen Sie eine der folgenden Rollen entweder in der Exchange-Verwaltungskonsole ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) oder mit PowerShell-Cmdlets zugewiesen haben (siehe [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):

  - Organisationsverwaltung
  - Organisationsverwaltung mit Leserechten
  - Rolle „Empfänger mit Leserechten“
  - Complianceverwaltung

Weitere Informationen hierzu finden Sie in den folgenden Ressourcen:

- [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md)

- [Featureberechtigungen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a>Was geschieht, wenn die Berichte keine Daten anzeigen?

Wenn Sie keine Daten in ihren ATP-Berichten sehen, überprüfen Sie, ob Ihre Richtlinien ordnungsgemäß eingerichtet sind. In Ihrer Organisation müssen [Richtlinien für sichere Links](set-up-atp-safe-links-policies.md) und Richt [Linien für sichere Anlagen](set-up-atp-safe-attachments-policies.md) definiert sein, damit ATP-Schutz vorhanden ist. Siehe auch [Anti-Spam and Anti-Malware Protection](anti-spam-and-anti-malware-protection.md).

## <a name="related-topics"></a>Verwandte Themen

[Intelligente Berichte und Einblicke im Security & Compliance Center](reports-and-insights-in-security-and-compliance.md)
  
[Rollen Berechtigungen (Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
