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
description: Erfahren Sie, wie Sie mit der Microsoft 365 Usage Analytics-Vorlagen-app in Power BI mit dem Sammeln von Daten für Ihren Mandanten beginnen.
ms.openlocfilehash: 347256fa7acaae18cd31f0c8c6b7eca20ad2e9dd
ms.sourcegitcommit: 36795a6735cd3fc678c7d5db71ddc97fac3f6f8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/06/2020
ms.locfileid: "48941331"
---
# <a name="enable-microsoft-365-usage-analytics"></a>Aktivieren von Microsoft 365-Nutzungsanalysen

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Microsoft 365-Verwendungsanalyse ist noch nicht für Microsoft 365 US Government Community verfügbar.
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a>Schritte zum Aktivieren von Microsoft 365-Nutzungsanalysen

Für den Einstieg in die Microsoft 365-Verwendungsanalyse müssen Sie zunächst die Daten im Microsoft 365 Admin Center verfügbar machen und dann die Vorlagen-app in Power BI initiieren.
  
### <a name="get-power-bi"></a>So erhalten Sie Power BI

Wenn Sie noch nicht über Power BI verfügen, können Sie [sich für Power BI pro registrieren](https://go.microsoft.com/fwlink/p/?linkid=845347). Wählen Sie **kostenlos testen** aus, um sich für eine Testversion anzumelden, oder **kaufen Sie jetzt** , um Power BI pro zu erhalten.
  
  
Sie können auch **Produkte** erweitern, um eine Power BI-Version zu erwerben. 

> [!NOTE]
> Sie benötigen eine Power BI pro-Lizenz zum Installieren, anpassen und Verteilen einer Vorlagen-app. Weitere Informationen finden Sie unter [Voraussetzungen](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).

Um Ihre Daten freizugeben, benötigen Sie und die Personen, mit denen Sie die Daten teilen, eine Power BI pro-Lizenz, oder der Inhalt muss sich in einem Arbeitsbereich in einem [Power BI Premium-Dienst](https://docs.microsoft.com/power-bi/service-premium-what-is)befinden. 
  
### <a name="enable-the-template-app"></a>Aktivieren der Vorlagen-App

Um die Vorlagen-APP zu aktivieren, müssen Sie ein **globaler Administrator** sein.
  
Weitere Informationen finden Sie unter Informationen [zu Administratorrollen](../add-users/about-admin-roles.md) . 
  
1. Wechseln Sie im Admin Center zur Seite **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a>. 
    
2. Suchen Sie auf der Seite **Nutzung** die **Microsoft 365-Verwendungsanalyse** Karte, und wählen Sie **Erste Schritte** aus.
    
3. Legen Sie im Bereich Berichte, der geöffnet wird, für **Power BI den Eintrag Daten für Microsoft 365-Verwendungsanalyse verfügbar machen** **auf** \> **Speichern** fest. 
  
Der Datensammlungsprozess wird in Abhängigkeit von der Größe des Mandanten in zwei bis 48 Stunden abgeschlossen. Die Schaltfläche **Gehe zu Power BI** wird aktiviert (nicht mehr grau), wenn die Datenerfassung abgeschlossen ist. 
    
### <a name="start-the-template-app"></a>Starten der Vorlagen-App

Um die Vorlagen-APP zu starten, müssen Sie entweder **globaler Administrator** , **berichtsleser** , **Exchange-Administrator** , **Skype for Business Administrator** oder **SharePoint-Administrator** sein. 
  
1. Kopieren Sie die Mandanten-ID, und wählen Sie **zu Power BI wechseln** aus.
    
2.  Wenn Power BI angezeigt wird, melden Sie sich an. **Wählen Sie dann apps** -> **Get apps** aus dem Navigationsmenü aus.    
  
3. Geben Sie auf der Registerkarte **apps** in das Suchfeld Microsoft 365 ein, und wählen Sie dann **Microsoft 365 Verwendungsanalyse** \> **Abrufen** aus.

    [![Wählen Sie Get it now aus.](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)
    
4.  Sobald die APP installiert ist. Wählen Sie die Kachel aus, um Sie zu öffnen.

5.  Wählen Sie **App erkunden** aus, um die APP mit Beispieldaten anzuzeigen. Wählen Sie **Connect** aus, um die APP mit den Daten Ihrer Organisation zu verbinden.

6.  Klicken Sie auf der Seite **Connect to Microsoft 365 Usage Analytics** auf **verbinden** , und geben Sie dann die Mandanten-ID (ohne Bindestriche) ein, die Sie in Schritt (1) kopiert haben, und wählen Sie **weiter** aus.
    
7. Wählen Sie auf dem nächsten Bildschirm **OAuth2** als **Authentifizierungsmethode** \> **Anmelden** aus. Wenn Sie eine andere Authentifizierungsmethode auswählen, tritt bei der Verbindung zur Vorlagen-App ein Fehler auf.
    
    ![Auswählen von Microsoft-Konto als Authentifizierungsmethode](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. Nachdem die Vorlagen-App instanziiert wurde, steht das Microsoft 365-Dashboard für die Verwendungsanalyse in Power BI im Internet zur Verfügung. Das erste Laden des Dashboards dauert zwischen 2 und 30 Minuten.
  
Aggregate auf Mandantenebene sind in allen Berichten verfügbar. **Details auf Benutzerebene werden erst nach dem 1. oder 15. Tag des Kalendermonats nach der Entscheidung verfügbar**. Dies wirkt sich auf alle Berichte unter Benutzeraktivität aus. Tipps zum Anzeigen und Verwenden dieser Berichte finden Sie unter [navigieren und Verwenden der Berichte in Microsoft 365-Verwendungsanalyse](navigate-and-utilize-reports.md) .
    
## <a name="make-the-collected-data-anonymous"></a>Anonymisieren der gesammelten Daten

Sie müssen ein globaler Administrator sein, um die für alle Berichte gesammelten Daten anonymisieren zu können. Dadurch werden identifizierbare Informationen wie Benutzer-, Gruppen-und Websitenamen in Berichten und in der Vorlagen-App ausgeblendet.
  
1. Wechseln Sie im Admin Center zu den **Einstellungen** der \> **org** -Einstellungen, und wählen Sie unter **Dienste** die Registerkarte **Berichte** aus.
    
2. Wählen Sie **Berichte** aus, und wählen Sie dann **Anonyme Bezeichner anzeigen** aus. Diese Einstellung wird sowohl auf die Verwendungsberichte als auch auf die Vorlagen-App angewendet.
  
3. Wählen Sie **Änderungen speichern** aus.
