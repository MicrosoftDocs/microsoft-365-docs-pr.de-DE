---
title: Problembehandlung Microsoft 365 Verwendungsanalysen
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: Erfahren Sie, wie Sie Probleme mit der Microsoft 365 Usage Analytics-Vorlagen-App behandeln.
ms.openlocfilehash: 74ee32ae015421a2352474daefa0eaa0a53fbbc9
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52293735"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a>Problembehandlung Microsoft 365 Verwendungsanalysen

Sehen Sie sich die folgende Liste von Fehlermeldungen an, um Hilfe zu den häufigsten Problemen mit Microsoft 365 zu erhalten.
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a>Ihre Anfrage kann nicht bearbeitet werden. Sie müssen diese Daten zuerst über das Microsoft 365 abonnieren.

 **Fehlercode:** 422 
  
 **Hier sehen Sie diese Meldung:** In Power BI, wenn Sie eine Verbindung mit der Microsoft 365 Usage Analytics-Vorlagen-App herstellen oder die Microsoft 365 berichterstattungs-APIs direkt aufrufen. 
  
 **Ursache:** Bevor Sie eine Verbindung mit der App herstellen können, müssen Sie die Daten aus dem Microsoft 365 abonnieren. Wenn dieser Schritt nicht zuerst durchgeführt wird, können Sie keine Verbindung mit der Vorlagen-App herstellen, auch wenn Sie Ihre Microsoft 365 bereitstellen. 
  
 **So beheben Sie diesen Fehler:** Um die Daten zu abonnieren, wechseln Sie zum Admin Center Reports Usage, und suchen Sie die Kachel Microsoft 365 Verwendungsanalyse auf der \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Hauptdashboardseite. Wählen Sie die **Schaltfläche** Erste  Schritte aus, und  aktivieren Sie dann im bereich Berichte, der geöffnet wird, die Einstellung Daten Microsoft 365 Verwendungsanalyse für Power BI verfügbar machen und **speichern**.
  
## <a name="we-are-processing-your-data"></a>Ihre Daten werden verarbeitet.

 **Hier sehen Sie diese Meldung:** In der **Microsoft 365 der Verwendungsanalyse** im Verwendungsdashboard im Microsoft 365 Admin Center.  
  
 **Ursache:** Wenn Sie [sich für das](enable-usage-analytics.md) Anzeigen von Daten in der Vorlagen-App aus dem Microsoft 365 Admin Center entscheiden, beginnt das Microsoft 365 System, historische Nutzungsdaten für Ihre Organisation zu generieren. Je nach Größe des Mandanten kann die Zeit für das Ausführen dieses Schritts zwischen 2 und 48 Stunden betragen. 
  
 **So beheben Sie dies:** Haben Sie einfach Geduld, aber wenn  sich die Nachricht nicht in Ihre Daten nach 3 Tagen ändert, wenden Sie sich an Microsoft 365 [business support](../../business-video/get-help-support.md).
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a>Ihre Anfrage kann derzeit nicht bearbeitet werden. Die Daten werden immer noch für Ihre Organisation vorbereitet.

 **Fehlercode:** 423 
  
 **Hier sehen Sie diese Meldung:** In Power BI, wenn Sie eine Verbindung mit der Microsoft 365 Usage Analytics-Vorlagen-App herstellen oder die Microsoft 365 berichterstattungs-APIs direkt aufrufen. 
  
 **Ursache:** Wenn Sie [sich für das](enable-usage-analytics.md) Anzeigen von Daten in der Vorlagen-App aus dem Admin Center entscheiden, beginnt das Microsoft 365, historische Nutzungsdaten für Ihre Organisation zu generieren. Je nach Größe Ihres Mandanten kann dieser Schritt zwischen zwei Stunden und 48 Stunden dauern. 
  
 **So beheben Sie dies:** Haben Sie einfach Geduld, aber wenn  sich die Nachricht nicht in Ihre Daten ändert, können Sie sich auch 3 Tage nach der Initiierung an Microsoft 365 [Business Support wenden.](../../business-video/get-help-support.md)
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a>Die von Ihnen angegebene Mandanten-ID weist nicht das richtige Format auf.

 **Fehlercode:** 400 
  
 **Hier sehen Sie diese Meldung:** In Power BI, wenn Sie eine Verbindung mit der Microsoft 365 Usage Analytics-Vorlagen-App herstellen oder die Microsoft 365 berichterstattungs-APIs direkt aufrufen. 
  
 **Ursache:** Die Mandanten-ID ist eine Guid und muss im Format xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx vorliegen. Wenn Sie eine andere Zeichenfolge in das Eingabefeld des Mandanten eingeben, wird dieser Fehler angezeigt. 
  
 **So beheben Sie diesen Fehler:** Wechseln Sie zum Admin Center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage,</a> und suchen Sie die Kachel Microsoft 365 Verwendungsanalyse auf der Hauptdashboardseite. Die Mandanten-ID wird auf der Kachel aufgeführt. Sie können es hier kopieren und in das Dialogfeld einfügen, um eine Verbindung mit der Vorlagen-App zu herstellen. 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a>Die von Ihnen angegebene Mandanten-ID wird von unserem System nicht erkannt.

 **Fehlercode:** 404 
  
 **Hier sehen Sie diese Meldung:** In Power BI, wenn Sie eine Verbindung mit der Microsoft 365 Usage Analytics-Vorlagen-App herstellen oder die Microsoft 365 berichterstattungs-APIs direkt aufrufen. 
  
 **Ursache:** Die von Ihnen bereitgestellte Mandanten-ID ist ungültig oder nicht vorhanden. 
  
 **So beheben Sie diesen Fehler:** Wechseln Sie zum Admin Center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage,</a> und suchen Sie die Kachel Microsoft 365 Verwendungsanalyse auf der Hauptdashboardseite. Die Mandanten-ID wird auf der Kachel aufgeführt. Sie können es hier kopieren und in das Dialogfeld einfügen, um eine Verbindung mit der Vorlagen-App zu herstellen. 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a>Geben Sie Ihre Anmeldeinformationen erneut ein, um sich wieder bei Power BI anzumelden.

Fehlercode: 302
  
 **Hier sehen Sie diese Meldung:** In Power BI, wenn Sie eine Verbindung mit der Microsoft 365 Usage Analytics-Vorlagen-App herstellen oder die Microsoft 365 berichterstattungs-APIs direkt aufrufen. 
  
 **Ursache:** Der Autorisierungscode ist fehlgeschlagen, und Sie müssen möglicherweise Ihre Anmeldeinformationen erneut eingeben. 
  
 **Fehlerbehebung:** Melden Sie sich bei Power BI ab und anschließend wieder an. 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a>Sie verfügen nicht über die richtige Autorisierung für den Zugriff auf diese Daten. Um von diesem Dienst aus auf die Daten zugreifen zu können, müssen Sie entweder ein globaler Administrator oder einer der Produktadministratoren sein.

 **Fehlercode:** 403 
  
 **Hier sehen Sie diese Meldung:** In Power BI, wenn Sie eine Verbindung mit der Microsoft 365 Usage Analytics-Vorlagen-App herstellen oder die Microsoft 365 berichterstattungs-APIs direkt aufrufen. 
  
 **Ursache:** Der Autorisierungscode ist fehlgeschlagen, da der Benutzer, der versucht hat, eine Verbindung mit der Vorlagen-App zu herstellen, nicht über die richtige Autorisierungsebene für den Zugriff auf diese Daten verfügt. 
  
 **So beheben Sie diesen Fehler:** Geben Sie die Anmeldeinformationen eines Benutzers an, der entweder ein globaler Administrator **,** **Exchange-Administrator,** **Skype for Business-Administrator,** **SharePoint-Administrator,** globaler Leser oder **Berichtsleser** ist, um eine Verbindung mit der Vorlagen-App herzustellen.  Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../add-users/about-admin-roles.md). 
  
## <a name="refresh-failed"></a>Fehler beim Aktualisieren.

 **Anzeigeort dieser Meldung:** E-Mail von Power BI oder Fehlerstatus im Aktualisierungsverlauf. 
  
 **Ursache:** Manchmal werden die Anmeldeinformationen des Benutzers, der mit der Vorlagen-App verbunden ist, zurückgesetzt und in den Verbindungseinstellungen der Vorlagen-App nicht aktualisiert, sodass dem Benutzer Aktualisierungsfehler angezeigt werden. 
  
 **So beheben Sie diesen Fehler:** Suchen Power BI dataset entsprechend der Microsoft 365 Usage Analytics-Vorlagen-App, wählen  Sie Aktualisierung planen aus, und geben Sie Ihre Administratoranmeldeinformationen an. 
  
Wenn dies nicht funktioniert, löschen Sie den Cache, und erstellen Sie die Vorlagen-App neu.
  
  
