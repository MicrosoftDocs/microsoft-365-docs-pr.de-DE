---
title: Aktivieren von Microsoft 365-Nutzungsanalysen
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Erfahren Sie, wie Sie mit dem Sammeln von Daten für Ihren Mandanten mithilfe der Microsoft 365 Usage Analytics-Vorlagen-App in Power BI beginnen.
ms.openlocfilehash: 734712994d47fcb234ba988bb4d185d09f3267d0
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "51471057"
---
# <a name="enable-microsoft-365-usage-analytics"></a>Aktivieren von Microsoft 365-Nutzungsanalysen

Microsoft 365-Verwendungsanalysen sind für die Microsoft 365 US Government Community noch nicht verfügbar.
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a>Schritte zum Aktivieren von Microsoft 365-Nutzungsanalysen

Um mit microsoft 365-Verwendungsanalysen zu beginnen, müssen Sie die Daten zuerst im Microsoft 365 Admin Center verfügbar machen und dann die Vorlagen-App in Power BI initiieren.
  
### <a name="get-power-bi"></a>So erhalten Sie Power BI

Wenn Sie noch nicht über Power BI verfügen, können Sie [sich für Power BI Pro registrieren.](https://go.microsoft.com/fwlink/p/?linkid=845347) Wählen **Sie Kostenlos testen,** um sich für eine Testversion zu registrieren, oder **Kaufen Sie jetzt,** um Power BI Pro zu erhalten.
  
  
Sie können auch **Produkte** erweitern, um eine Power BI-Version zu erwerben. 

> [!NOTE]
> Sie benötigen eine Power BI Pro-Lizenz zum Installieren, Anpassen und Verteilen einer Vorlagen-App. Weitere Informationen finden Sie unter [Voraussetzungen](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).

Um Ihre Daten zu teilen, benötigen Sie und die Personen, für die Sie die Daten freigeben, eine Power BI Pro-Lizenz, oder der Inhalt muss sich in einem Arbeitsbereich in einem [Power BI Premium-Dienst befinden.](/power-bi/service-premium-what-is) 
  
### <a name="enable-the-template-app"></a>Aktivieren der Vorlagen-App

Um die Vorlagen-App zu aktivieren, müssen Sie ein **globaler Administrator sein.**
  
Weitere [Informationen finden Sie unter Informationen](../add-users/about-admin-roles.md) zu Administratorrollen. 
  
1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>. 
    
2. Suchen Sie **auf** der Seite Verwendung die **Microsoft 365-Verwendungsanalysekarte,** und wählen Sie **Erste Schritte aus.**
    
3. Legen Sie im bereich Berichte, der geöffnet wird, Daten für **Microsoft 365-Verwendungsanalysen** für Power BI verfügbar machen auf **On** \> **Save fest.** 
  
Der Datensammlungsprozess wird in zwei bis 48 Stunden abgeschlossen, abhängig von der Größe Ihres Mandanten. Die **Schaltfläche Zu Power BI** wechseln wird aktiviert (nicht mehr grau), wenn die Datensammlung abgeschlossen ist. 
    
### <a name="start-the-template-app"></a>Starten der Vorlagen-App

Zum Starten der Vorlagen-App müssen Sie entweder globaler **Administrator,** Berichtsleser, Exchange-Administrator, **Skype for Business-Administrator** oder  **SharePoint-Administrator sein.** 
  
1. Kopieren Sie die Mandanten-ID, und wählen **Sie Zu Power BI wechseln aus.**
    
2.  Wenn Power BI angezeigt wird, melden Sie sich an. Wählen Sie **dann Apps Apps** aus -> **dem** Navigationsmenü herunterladen aus.    
  
3. Geben Sie **auf der** Registerkarte Apps Microsoft 365 in das Suchfeld ein, und wählen Sie dann **Microsoft 365-Nutzungsanalyse** \> **jetzt herunterladen aus.**

    [![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)
    
4.  Sobald die App installiert ist. Wählen Sie die Kachel aus, um sie zu öffnen.

5.  Wählen **Sie App durchsuchen** aus, um die App mit Beispieldaten zu sehen. Wählen **Sie Verbinden** aus, um die App mit den Daten Ihrer Organisation zu verbinden.

6.  Wählen **Sie Verbinden** auf dem Bildschirm Verbindung mit Microsoft **365-Verwendungsanalyse** herstellen aus, geben Sie dann die Mandanten-ID (ohne Bindestriche) ein, die Sie in Schritt (1) kopiert haben, und wählen Sie **Weiter aus.**
    
7. Wählen Sie auf dem nächsten Bildschirm **OAuth2** als **Authentifizierungsmethode** \> **Anmelden aus.** Wenn Sie eine andere Authentifizierungsmethode auswählen, wird die Verbindung mit der Vorlagen-App fehlschlagen.
    
    ![Auswählen des Microsoft-Kontos als Authentifizierungsmethode](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. Nachdem die Vorlagen-App instanziiert wurde, steht das Microsoft 365 Usage Analytics-Dashboard in Power BI im Web zur Verfügung. Das anfängliche Laden des Dashboards dauert zwischen 2 und 30 Minuten.
  
Aggregate auf Mandantenebene sind nach der Opt-in allen Berichten verfügbar. **Details auf Benutzerebene werden erst am 5. des** nächsten Kalendermonats nach der Opting in verfügbar. Dies wirkt sich auf alle Berichte unter Benutzeraktivität aus (Tipps zum Anzeigen und Verwenden dieser Berichte finden Sie [unter Navigate and use the reports in Microsoft 365 usage analytics).](navigate-and-utilize-reports.md)
    
## <a name="make-the-collected-data-anonymous"></a>Anonymisieren der gesammelten Daten

Sie müssen ein globaler Administrator sein, um die für alle Berichte gesammelten Daten anonymisieren zu können. Dadurch werden identifizierbare Informationen wie Benutzer-, Gruppen- und Websitenamen in Berichten und in der Vorlagen-App ausgeblendet.
  
1. Wechseln Sie im Admin Center zu **Einstellungen** \> **Organisationseinstellungen,** und wählen Sie unter Dienste die Option **Berichte aus.** 
    
2. Wählen **Sie Berichte** aus, und wählen Sie dann **anonyme Bezeichner anzeigen aus.** Diese Einstellung wird sowohl auf die Verwendungsberichte als auch auf die Vorlagen-App angewendet.
  
3. Wählen Sie **Änderungen speichern** aus.