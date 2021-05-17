---
title: Microsoft 365 Berichte im Admin Center – Verwendung von E-Mail-Apps
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
ms.assetid: c2ce12a2-934f-4dd4-ba65-49b02be4703d
description: Erfahren Sie, wie Sie E-Mail-Apps-Nutzungsbericht über E-Mail-Apps informieren, die eine Verbindung mit Exchange Online und Outlook verwenden.
ms.openlocfilehash: f2a7b79a00b47896dac4427c532f85dccb931c60
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921953"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-apps-usage"></a>Microsoft 365 Berichte im Admin Center – Verwendung von E-Mail-Apps

Das Microsoft 365 **-Dashboard** zeigt Ihnen die Übersicht über die Aktivitäten in den Produkten in Ihrer Organisation. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht über Berichte](activity-reports.md) an. Im Nutzungsbericht für E-Mail-Apps sehen Sie, wie viele E-Mail-Apps eine Verbindung mit Exchange Online. Außerdem werden Versionsinformationen der von den Benutzern verwendeten Outlook-Apps angezeigt, sodass Sie die Benutzer, die nicht unterstützte Versionen verwenden, auffordern können, unterstützte Versionen von Outlook zu installieren.
  
> [!NOTE]
> Sie müssen ein globaler Administrator, globaler Leser oder Berichtleser in Microsoft 365 oder ein Exchange-, SharePoint-, Teams-Dienst-, Teams-Kommunikations- oder Skype for Business-Administrator sein, um Berichte anzeigen zu können.  
 
## <a name="how-to-get-to-the-email-apps-report"></a>So erhalten Sie den E-Mail-Apps-Bericht

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>.
2. Wählen **Sie Weitere Anzeigen** unter **E-Mail-Aktivität aus.** 
3. Wählen Sie **in der** Dropdownliste E-Mail-Aktivität die Option Exchange  \> **E-Mail-Apps-Nutzung aus.**
  
## <a name="interpret-the-email-apps-report"></a>Interpretieren des Berichts für E-Mail-Apps

Sie können eine Ansicht der E-Mail-Apps-Aktivität erhalten, indem Sie sich die Diagramme **Benutzer** und **Clients** ansehen. 
  
![Verwendete E-Mail-Clients](../../media/d78af7db-2b41-4d37-8b6e-bc7e47edd1dd.png)
  
|Element|Beschreibung|
|:-----|:-----|
|1.  <br/> |Der **Nutzungsbericht** für E-Mail-Apps kann für Trends der letzten 7 Tage, 30 Tage, 90 Tage oder 180 Tage angezeigt werden. Wenn Sie im Bericht jedoch einen bestimmten Tag auswählen, werden in der Tabelle (7) Daten für bis zu 28 Tage ab dem aktuellen Datum angezeigt (nicht ab dem Datum, an dem der Bericht generiert wurde).  <br/> |
|2.  <br/> |Die Daten in den einzelnen Berichten decken in der Regel die letzten 24 bis 48 Stunden ab.  <br/> |
|3.  <br/> |In der Ansicht **Benutzer** wird die Anzahl der eindeutigen Benutzer angezeigt, die mit einer beliebigen E-Mail-App eine Verbindung mit Exchange Online hergestellt haben.  <br/> |
|4.  <br/> |In der Ansicht **Apps** wird die Anzahl der eindeutigen Benutzer im ausgewählten Zeitraum nach App angezeigt.  <br/> |
|5.  <br/> |Die **Versionsansicht** zeigt die Anzahl der eindeutigen Benutzer für jede Version von Outlook in Windows.  <br/> |
|6.  <br/> | Im Diagramm **Benutzer** gibt die y-Achse die Gesamtanzahl der eindeutigen Benutzer an, die an einem beliebigen Tag innerhalb des Berichtszeitraums eine Verbindung mit einer App hergestellt haben.  <br/>  Im Diagramm **Benutzer** gibt die x-Achse die Anzahl der eindeutigen Benutzer an, die die App in diesem Berichtszeitraum verwendet haben.  <br/>  Im Diagramm **Apps** gibt die y-Achse die Gesamtanzahl der eindeutigen Benutzer an, die eine bestimmte App im Berichtszeitraum verwendet haben.  <br/>  Im Diagramm **Apps** gibt die x-Achse die Liste der Apps in Ihrer Organisation an.  <br/>  Im Diagramm **Versionen** gibt die y-Achse die Gesamtanzahl der eindeutigen Benutzer an, die eine bestimmte Version der Outlook-Desktop-App verwenden. Wenn der Bericht die Versionsnummer der Outlook nicht auflösen kann, wird die Menge **als Undetermined angezeigt.**  <br/>  Im Diagramm **Versionen** gibt die x-Achse die Liste der Apps in Ihrer Organisation an.  <br/> |
|7.  <br/> |Sie können die im Diagramm angezeigte Datenreihe filtern, indem Sie in der Legende ein Element auswählen.  <br/> |
|8.  <br/> | Möglicherweise werden alle Elemente in der nachstehenden Liste in den Spalten erst angezeigt, wenn Sie diese hinzugefügt haben.<br/> **Benutzername** ist der Name des Besitzers der E-Mail-App.  <br/> **Das Datum der letzten Aktivität** ist das letzte Datum, an dem der Benutzer eine E-Mail-Nachricht gelesen oder gesendet hat.  <br/> **Mac Mail**, **Outlook für Mac** sowie **Outlook**, **Outlook Mobile** und **Outlook im Web** sind Beispiele für E-Mail-Apps, die möglicherweise in Ihrer Organisation verwendet werden.  <br/>  Wenn die Richtlinien Ihrer Organisation eine Anzeige von Berichten verhindern, in denen Benutzerinformationen identifizierbar sind, können Sie die Datenschutzeinstellung für alle diese Berichte ändern. Lesen Sie den Abschnitt zum **Ausblenden von Details auf Benutzerebene** in den [Aktivitätsberichten im Microsoft 365 Admin Center](activity-reports.md).  <br/> |
|9.  <br/> |Wählen **Sie Spalten auswählen** aus, um Spalten aus dem Bericht hinzuzufügen oder zu entfernen.  <br/> ![Verwendungsbericht für E-Mail-Apps – Spalten auswählen](../../media/041bd6ff-27e8-409d-9608-282edcfa2316.png)|
|10.  <br/> |Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren.  <br/> |
|||
   
