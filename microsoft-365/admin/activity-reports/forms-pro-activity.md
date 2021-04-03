---
title: Microsoft 365-Berichte im Admin Center – Dynamics 365 Customer Voice-Aktivität
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: Erfahren Sie, wie Sie einen Microsoft Dynamics 365 Customer Voice-Aktivitätsbericht mithilfe des Microsoft 365 Reports-Dashboards im Microsoft 365 Admin Center erhalten.
ms.openlocfilehash: 26d376602caebcb5276b77a3d2c962a14e5fead5
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579650"
---
# <a name="microsoft-365-reports-in-the-admin-center---dynamics-365-customer-voice-activity"></a>Microsoft 365-Berichte im Admin Center – Dynamics 365 Customer Voice-Aktivität

Das Microsoft 365 **Reports-Dashboard** zeigt Ihnen die Übersicht über die Aktivitäten in den Produkten in Ihrer Organisation. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht über Berichte](activity-reports.md) an.
  
Sie können beispielsweise die Aktivität jedes Benutzers verstehen, der für die Verwendung von Microsoft Dynamics 365 Customer Voice lizenziert ist, indem Sie sich deren Interaktionen mit Dynamics 365 Customer Voice anschauen. Es hilft Ihnen auch, den Grad der Zusammenarbeit zu verstehen, indem Sie sich die Anzahl der erstellten Pro-Umfragen und Pro-Umfragen anschaut, auf die die Benutzer geantwortet haben. 
  
> [!NOTE]
> Sie müssen ein globaler Administrator, globaler Leser oder Berichtleser in Microsoft 365 oder ein Exchange-, SharePoint-, Teams-Dienst-, Teams Communications- oder Skype for Business-Administrator sein, um Berichte anzeigen zu können. 

## <a name="how-to-get-to-the-forms-pro-activity-report"></a>So erhalten Sie den Forms Pro-Aktivitätsbericht

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>.

    
2. Wählen Sie **in der Dropdownliste** Bericht auswählen die **Option Dynamics 365 Customer Voice activity** \> **aus.**

## <a name="interpret-the-dynamics-365-customer-voice-activity-report"></a>Interpretieren des Dynamics 365 Customer Voice-Aktivitätsberichts

Sie können eine Ansicht der Dynamics 365 Customer Voice-Aktivität Ihres Benutzers erhalten, indem Sie sich die Diagramme **Aktivität** und **Benutzer** ansehen. 

![Formularaktivitätsbericht](../../media/formsproactivity.png)

|Element|Beschreibung|
|:-----|:-----|
|1.  <br/> |Der **Dynamics 365 Customer Voice-Aktivitätsbericht** kann für Trends der letzten 7 Tage, 30 Tage, 90 Tage oder 180 Tage angezeigt werden. Wenn Sie im Bericht jedoch einen bestimmten Tag auswählen, werden in der Tabelle (7) Daten für bis zu 28 Tage ab dem aktuellen Datum angezeigt (nicht ab dem Datum, an dem der Bericht generiert wurde).   <br/> |
|2.  <br/> |Die Daten in den einzelnen Berichten sind in der Regel so neu wie die letzten 48 Stunden.  <br/> |
|3.  <br/> |Die **Benutzeransicht** hilft Ihnen, den Trend bei der Anzahl aktiver Dynamics 365 Customer Voice-Benutzer zu verstehen. Ein Benutzer wird als aktiv betrachtet, wenn er innerhalb eines bestimmten Zeitraums eine Aktivität um eine Pro-Umfrage (Erstellen, Bearbeiten, Anzeigen usw.) ausgeführt hat.  <br/> |
|4.  <br/> |Die **Aktivitätsansicht** hilft Ihnen, den Trend bei der Anzahl aktiver Benutzer zu verstehen. Ein Benutzer wird als "aktiv" betrachtet, wenn er innerhalb eines bestimmten Zeitraums eine Dateiaktivität (Speichern, Synchronisieren, Ändern oder Freigeben) ausgeführt oder eine Seite besucht hat.<br/> HINWEIS: Eine Aktivität kann für eine einzelne Umfrage mehrmals auftreten, zählt jedoch nur als eine aktive Umfrage. Sie können z. B. eine Pro-Umfrage erstellen und dieselbe Umfrage über einen bestimmten Zeitraum mehrmals bearbeiten. Sie wird nur als einzelne Umfrage gezählt. <br>|
|5.<br/>|Im **Diagramm Benutzer** ist die Y-Achse die Anzahl eindeutiger Benutzer. X-Achse ist das Datum, an dem die eindeutigen Benutzer aktiv sind. Die Legenden sind:<br/><br/>**Designer** bedeutet, dass der Benutzer eine Dynamics 365 Customer Voice Survey erstellt oder bearbeitet hat.<br><br>Im Diagramm **Aktivität** ist die Y-Achse die Anzahl der Dynamics 365 Customer Voice-Antworten pro Umfrage. X-Achse ist das Datum, an dem die Umfrage- oder Reaktionsaktivität aufgetreten ist. Die Legenden sind:<br/><br/>**Erstellte Umfragen** sind die Anzahl der eindeutigen Dynamics 365 Customer Voice-Umfragen, die von den Benutzern erstellt wurden.<br>**Antworten** ist die Anzahl anonymer oder nicht anonymer Antworten, die die Benutzer, die die Umfrage erhalten haben, übermittelt haben. |
|6.<br/>|Sie können die im Diagramm angezeigte Datenreihe filtern, indem Sie in der Legende ein Element auswählen. Wählen Sie beispielsweise im Diagramm Benutzer Designer, Responder oder Benutzer insgesamt aus, um nur die Informationen zu den einzelnen Benutzern zu sehen. Wenn Sie diese Auswahl ändern, werden die Informationen in der darunter stehenden Rastertabelle nicht geändert.|
|7.<br/>|Die Tabelle zeigt eine Aufschlüsselung der Aktivitäten auf Benutzerebene. Die Legenden sind:<br/><br/>**Benutzername** ist die E-Mail-Adresse des Benutzers, der die Aktivität in Microsoft Forms ausgeführt hat.<br/>**Das Datum der letzten Aktivität (UTC)** ist das letzte Datum, an dem eine Formularaktivität vom Benutzer für den ausgewählten Datumsbereich ausgeführt wurde. Um Aktivitäten anzuzeigen, die an einem bestimmten Datum stattfanden, wählen Sie das Datum direkt im Diagramm aus.<br/>Dadurch wird die Tabelle so gefiltert, dass Dateiaktivitätsdaten nur für Benutzer angezeigt werden, die die Aktivität an diesem bestimmten Tag ausgeführt haben.<br/><br/>**Die Anzahl der erstellten Umfragen** ist die Anzahl der umfragen, die der Benutzer erstellt hat.<br/> **Die Anzahl der Umfrageantworten** ist die Anzahl der Antworten von Antwortenden, an die die Umfrage verteilt wurde.|
|8.<br/>|Wählen Sie das **Symbol Spalten** verwalten aus, um Spalten aus dem Bericht hinzuzufügen oder zu entfernen.|
|9.<br/>|Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten für alle Benutzer exportiert, und Sie können einfache Aggregation, Sortierung und Filterung für die weitere Analyse durchführen. Wenn Sie weniger als 100 Benutzer haben, können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Wenn Sie mehr als 100 Benutzer haben, müssen Sie die Daten exportieren, um filtern und sortieren zu können.|