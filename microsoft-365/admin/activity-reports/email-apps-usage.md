---
title: Microsoft 365-Berichte im Admin Center-Nutzung von e-Mail-apps
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
description: In diesem Artikel erfahren Sie, wie Sie über e-Mail-apps, die eine Verbindung mit Exchange Online herstellen, und die Outlook-Version, die von Benutzern verwendet werden, über die Verwendung
ms.openlocfilehash: c6ee72390f0b9e9ead0f07c41d64bf5b7264fc1b
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948244"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-apps-usage"></a>Microsoft 365-Berichte im Admin Center-Nutzung von e-Mail-apps

Im Microsoft 365 **Reports** -Dashboard wird die Aktivitätsübersicht für die Produkte in Ihrer Organisation angezeigt. Sie können Drilldowns zu Einzelberichten auf Produktebene ausführen und auf diese Weise genauere Einblicke in die Aktivitäten innerhalb der einzelnen Produkte erhalten. Sehen Sie sich die [Übersicht über Berichte](activity-reports.md) an. Im Bericht über die Verwendung von e-Mail-Apps können Sie sehen, wie viele e-Mail-apps sich mit Exchange Online verbinden. Außerdem werden Versionsinformationen der von den Benutzern verwendeten Outlook-Apps angezeigt, sodass Sie die Benutzer, die nicht unterstützte Versionen verwenden, auffordern können, unterstützte Versionen von Outlook zu installieren.
  
> [!NOTE]
> Sie müssen ein globaler Administrator, ein globaler Leser oder ein Leser von Berichten in Microsoft 365 oder einer Exchange-, SharePoint-, Teams-Dienst-, Microsoft Teams-oder Skype for Business-Administrator sein, um Berichte anzuzeigen.  
 
## <a name="how-to-get-to-the-email-apps-report"></a>So gelangen Sie zum Bericht "e-Mail-Apps"

1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>.

    
2. Wählen Sie in der Dropdownliste **Bericht auswählen** die Option **Exchange** \> **-e-Mail-App-Nutzung**aus.
  
## <a name="interpret-the-email-apps-report"></a>Interpretieren des Berichts über e-Mail-apps

Sie können eine Ansicht in die e-Mail-apps-Aktivität abrufen, indem Sie die Diagramme **Users** and **Clients** betrachten. 
  
![Verwendete e-Mail-Clients](../../media/2a775e46-750f-4fa6-8197-de4b24614bd7.png)
  
|Element|Beschreibung|
|:-----|:-----|
|1.  <br/> |Der **Verwendungsbericht "e-Mail-apps** " kann für Trends in den letzten 7 Tagen, 30 Tagen, 90 Tagen oder 180 Tagen angezeigt werden. Wenn Sie im Bericht jedoch einen bestimmten Tag auswählen, werden in der Tabelle (7) Daten für bis zu 28 Tage ab dem aktuellen Datum angezeigt (nicht ab dem Datum, an dem der Bericht generiert wurde).  <br/> |
|2.  <br/> |Die Daten in den einzelnen Berichten decken in der Regel die letzten 24 bis 48 Stunden ab.  <br/> |
|3.  <br/> |In der Ansicht **Benutzer** wird die Anzahl der eindeutigen Benutzer angezeigt, die mit einer beliebigen E-Mail-App eine Verbindung mit Exchange Online hergestellt haben.  <br/> |
|4.  <br/> |In der Ansicht **Apps** wird die Anzahl der eindeutigen Benutzer im ausgewählten Zeitraum nach App angezeigt.  <br/> |
|5.  <br/> |In der Ansicht **Versionen** wird die Anzahl der eindeutigen Benutzer für jede Version von Outlook in Windows angezeigt.  <br/> |
|6.  <br/> | Im Diagramm **Benutzer** gibt die y-Achse die Gesamtanzahl der eindeutigen Benutzer an, die an einem beliebigen Tag innerhalb des Berichtszeitraums eine Verbindung mit einer App hergestellt haben.  <br/>  Im Diagramm **Benutzer** gibt die x-Achse die Anzahl der eindeutigen Benutzer an, die die App in diesem Berichtszeitraum verwendet haben.  <br/>  Im Diagramm **Apps** gibt die y-Achse die Gesamtanzahl der eindeutigen Benutzer an, die eine bestimmte App im Berichtszeitraum verwendet haben.  <br/>  Im Diagramm **Apps** gibt die x-Achse die Liste der Apps in Ihrer Organisation an.  <br/>  Im Diagramm **Versionen** gibt die y-Achse die Gesamtanzahl der eindeutigen Benutzer an, die eine bestimmte Version der Outlook-Desktop-App verwenden. Wenn der Bericht die Versionsnummer von Outlook nicht auflösen kann, wird die Menge als nicht **bestimmt**angezeigt.  <br/>  Im Diagramm **Versionen** gibt die x-Achse die Liste der Apps in Ihrer Organisation an.  <br/> |
|7.  <br/> |Sie können die im Diagramm angezeigte Datenreihe filtern, indem Sie in der Legende ein Element auswählen. Wählen Sie beispielsweise im Diagramm **Benutzer** die Option **Mac Mail** oder **Outlook** ![ -Liste der e-Mail-Clients aus. Wählen Sie den e-Mail-Client aus, um weitere Berichtsdaten für diesen Client zu erhalten.](../../media/19b9da1b-7b69-4a04-8527-38349f859e84.png) , um nur die Informationen anzuzeigen, die sich auf jede einzelne beziehen. Durch das Ändern dieser Auswahl werden die Informationen in der Gitternetztabelle nicht geändert. Mac Mail, Outlook für Mac, Outlook Mobile, Outlook Desktop und Outlook im Internet sind Beispiele für e-Mail-apps, die Sie möglicherweise in Ihrer Organisation haben.  <br/> |
|8.  <br/> | Möglicherweise werden alle Elemente in der nachstehenden Liste in den Spalten erst angezeigt, wenn Sie diese hinzugefügt haben.<br/> **Username** ist der Name des Besitzers der e-Mail-app.  <br/> **Datum der letzten Aktivität** ist das letzte Datum, an dem der Benutzer eine e-Mail-Nachricht gelesen oder gesendet hat.  <br/> **Mac Mail**, **Outlook für Mac** sowie **Outlook**, **Outlook Mobile** und **Outlook im Web** sind Beispiele für E-Mail-Apps, die möglicherweise in Ihrer Organisation verwendet werden.  <br/>  Wenn die Richtlinien Ihrer Organisation eine Anzeige von Berichten verhindern, in denen Benutzerinformationen identifizierbar sind, können Sie die Datenschutzeinstellung für alle diese Berichte ändern. Lesen Sie den Abschnitt zum **Ausblenden von Details auf Benutzerebene** in den [Aktivitätsberichten im Microsoft 365 Admin Center](activity-reports.md).  <br/> |
|9.  <br/> |Wählen Sie **Spalten verwalten** aus, um Spalten zum Bericht hinzuzufügen oder daraus zu entfernen.  <br/> ![Verwendungsbericht für e-Mail-apps – Spalten auswählen](../../media/82008680-cd28ab00-9686-11ea-8692-b3d72117c20b.png)|
|10.  <br/> |Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie den Link **Exportieren** auswählen. Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren.  <br/> |
|||
   
