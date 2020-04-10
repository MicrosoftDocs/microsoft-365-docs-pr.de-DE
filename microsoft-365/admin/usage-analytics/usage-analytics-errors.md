---
title: Problembehandlung bei Microsoft 365-Verwendungsanalysen
f1.keywords:
- NOCSH
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: Hier erfahren Sie, wie Sie Probleme mit der Vorlagen-App für Microsoft 365 Usage Analytics beheben können.
ms.openlocfilehash: 7164aa246a79a8d8c5aa50d995b53b6221003c01
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212149"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a>Problembehandlung bei Microsoft 365-Verwendungsanalysen

Untersuchen Sie die folgende Liste von Fehlermeldungen, um Hilfe zu den am häufigsten auftretenden Problemen mit Microsoft 365 Usage Analytics zu erhalten.
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a>Ihre Anfrage kann nicht bearbeitet werden. Sie müssen zuerst diese Daten im Microsoft 365 Admin Center abonnieren.

 **Fehlercode:** 422 
  
 **Die folgende Meldung wird angezeigt:** In Power BI, wenn Sie eine Verbindung mit der Microsoft 365 Usage Analytics-Vorlagen-App herstellen oder wenn Sie die Microsoft 365-Berichts-APIs direkt aufrufen. 
  
 **Ursache:** Bevor Sie eine Verbindung mit der App herstellen können, müssen Sie die Daten im Microsoft 365 Admin Center abonnieren. Wenn dieser Schritt nicht zuerst ausgeführt wird, können Sie keine Verbindung mit der Vorlagen-App herstellen, auch wenn Sie Ihre Microsoft 365-Mandanten-ID angeben. 
  
 **So beheben Sie diesen Fehler:** Wenn Sie die Daten abonnieren möchten, wechseln Sie zur Verwaltungs \> Konsole **Berichte** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a> , und suchen Sie die Kachel Microsoft 365 Usage Analytics auf der Hauptseite des Dashboards. Wählen Sie die Schaltfläche **Erste Schritte** aus, und aktivieren Sie dann im Bereich **Berichte** , der geöffnet wird, die Option **Daten für Microsoft 365-Verwendungsanalyse für Power BI verfügbar machen** und **Speichern**.
  
## <a name="we-are-processing-your-data"></a>Ihre Daten werden verarbeitet.

 **Die folgende Meldung wird angezeigt:** In der Kachel **Microsoft 365 Usage Analytics** im **Nutzungs** Dashboard im Microsoft 365 Admin Center. 
  
 **Ursache:** Wenn Sie [sich für das Anzeigen von Daten in der Vorlagen-App](enable-usage-analytics.md) aus dem Microsoft 365 Admin Center entscheiden, beginnt das Microsoft 365-System mit der Generierung historischer Verwendungsdaten für Ihre Organisation. Je nach Größe des Mandanten kann die Zeit für das Ausführen dieses Schritts zwischen 2 und 48 Stunden betragen. 
  
 **So beheben Sie dieses Problem:** Seien Sie nur geduldig, aber wenn sich die Nachricht nicht ändert, wenn Ihre Daten nach 3 Tagen **verfügbar sind** , [wenden Sie sich an Microsoft 365 for Business Support](../contact-support-for-business-products.md).
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a>Ihre Anfrage kann derzeit nicht bearbeitet werden. Die Daten werden immer noch für Ihre Organisation vorbereitet.

 **Fehlercode:** 423 
  
 **Die folgende Meldung wird angezeigt:** In Power BI, wenn Sie eine Verbindung mit der Microsoft 365 Usage Analytics-Vorlagen-App herstellen oder wenn Sie die Microsoft 365-Berichts-APIs direkt aufrufen. 
  
 **Ursache:** Wenn Sie [sich für das Anzeigen von Daten in der Vorlagen-App](enable-usage-analytics.md) aus dem Admin Center entscheiden, beginnt das Microsoft 365-System mit der Generierung historischer Verwendungsdaten für Ihre Organisation. Je nach Größe des Mandanten kann die Zeit für das Ausführen dieses Schritts zwischen 2 und 48 Stunden betragen. 
  
 **So beheben Sie dieses Problem:** Seien Sie nur geduldig, aber wenn sich die Nachricht nicht ändert, **sind Ihre Daten** sogar 3 Tage seit der Initiierung nicht mehr verfügbar, [wenden Sie sich an den Support von Microsoft 365 for Business](../contact-support-for-business-products.md).
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a>Die von Ihnen angegebene Mandanten-ID weist nicht das richtige Format auf.

 **Fehlercode:** 400 
  
 **Die folgende Meldung wird angezeigt:** In Power BI, wenn Sie eine Verbindung mit der Microsoft 365 Usage Analytics-Vorlagen-App herstellen oder wenn Sie die Microsoft 365-Berichts-APIs direkt aufrufen. 
  
 **Ursache:** Die Mandanten-ID ist eine GUID und muss das Format xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx aufweisen. Wenn Sie eine andere Zeichenfolge in das Eingabefeld für den Mandanten eingeben, wird diese Fehlermeldung angezeigt. 
  
 **So beheben Sie diesen Fehler:** Wechseln Sie zur Admin Center \> - **Berichts** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a> , und suchen Sie die Kachel Microsoft 365 Usage Analytics auf der Hauptseite des Dashboards. Die Mandanten-ID ist auf der Kachel aufgeführt. Sie können es von hier kopieren und in das Dialogfeld zum Herstellen einer Verbindung mit der Vorlagen-App einfügen. 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a>Die von Ihnen angegebene Mandanten-ID wird von unserem System nicht erkannt.

 **Fehlercode:** 404 
  
 **Die folgende Meldung wird angezeigt:** In Power BI, wenn Sie eine Verbindung mit der Microsoft 365 Usage Analytics-Vorlagen-App herstellen oder wenn Sie die Microsoft 365-Berichts-APIs direkt aufrufen. 
  
 **Ursache:** Die von Ihnen angegebene Mandanten-ID ist nicht gültig oder nicht vorhanden. 
  
 **So beheben Sie diesen Fehler:** Wechseln Sie zur Admin Center \> - **Berichts** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Verwendung</a> , und suchen Sie die Kachel Microsoft 365 Usage Analytics auf der Hauptseite des Dashboards. Die Mandanten-ID ist auf der Kachel aufgeführt. Sie können es von hier kopieren und in das Dialogfeld zum Herstellen einer Verbindung mit der Vorlagen-App einfügen. 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a>Geben Sie Ihre Anmeldeinformationen erneut ein, um sich wieder bei Power BI anzumelden.

Fehlercode: 302
  
 **Die folgende Meldung wird angezeigt:** In Power BI, wenn Sie eine Verbindung mit der Microsoft 365 Usage Analytics-Vorlagen-App herstellen oder wenn Sie die Microsoft 365-Berichts-APIs direkt aufrufen. 
  
 **Ursache:** Der Autorisierungscode ist fehlgeschlagen, und Sie müssen möglicherweise Ihre Anmeldeinformationen erneut eingeben. 
  
 **Fehlerbehebung:** Melden Sie sich bei Power BI ab und anschließend wieder an. 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a>Sie verfügen nicht über die richtige Autorisierung für den Zugriff auf diese Daten. Um von diesem Dienst aus auf die Daten zugreifen zu können, müssen Sie entweder ein globaler Administrator oder einer der Produktadministratoren sein.

 **Fehlercode:** 403 
  
 **Die folgende Meldung wird angezeigt:** In Power BI, wenn Sie eine Verbindung mit der Microsoft 365 Usage Analytics-Vorlagen-App herstellen oder wenn Sie die Microsoft 365-Berichts-APIs direkt aufrufen. 
  
 **Ursache:** Der Autorisierungscode ist fehlgeschlagen, da der Benutzer, der versucht hat, eine Verbindung mit der Vorlagen-App herzustellen, nicht über die richtige Berechtigungsstufe für den Zugriff auf diese Daten verfügt. 
  
 **So beheben Sie diesen Fehler:** Geben Sie die Anmeldeinformationen eines Benutzers an, der entweder **globaler Administrator**, **Exchange-Administrator**, **Skype for Business Administrator**, **SharePoint-Administrator**, **globaler Leser** oder **berichtsleser** ist, um eine Verbindung mit der Vorlagen-App herzustellen. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../add-users/about-admin-roles.md). 
  
## <a name="refresh-failed"></a>Fehler beim Aktualisieren.

 **Anzeigeort dieser Meldung:** E-Mail von Power BI oder Fehlerstatus im Aktualisierungsverlauf. 
  
 **Ursache:** Manchmal werden die Anmeldeinformationen des Benutzers, der mit der Vorlagen-App verbunden ist, zurückgesetzt und in den Verbindungseinstellungen der Vorlagen-APP nicht aktualisiert, wodurch der Benutzer Fehler bei der Aktualisierung von Fehlern sehen kann. 
  
 **So beheben Sie diesen Fehler:** Suchen Sie in Power BI nach dem DataSet, das der Microsoft 365 Usage Analytics-Vorlagen-App entspricht, wählen Sie **Aktualisierung planen** aus, und geben Sie Ihre Administratoranmeldeinformationen an. 
  
Wenn dies nicht funktioniert, löschen Sie den Cache, und erstellen Sie die Vorlagen-APP neu.
  
  
