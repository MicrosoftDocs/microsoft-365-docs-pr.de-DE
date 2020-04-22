---
title: Set up Information Rights Management (IRM) in SharePoint admin center
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 239ce6eb-4e81-42db-bf86-a01362fed65c
description: In diesem Artikel erfahren Sie, wie Sie SharePoint Online IRM über Microsoft Azure Active Directory Rights Management Services (RMS) zum Schutz von SharePoint-Listen und-Dokumentbibliotheken verwenden.
ms.openlocfilehash: c981ceefde2cedb5f6c8731fd9a5ad9318174120
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634777"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a>Set up Information Rights Management (IRM) in SharePoint admin center

## <a name="introduction"></a>Einführung

In SharePoint Online wird der IRM-Schutz auf Dateien auf Listen-und Bibliotheksebene angewendet. Bevor Ihre Organisation den IRM-Schutz verwenden kann, müssen Sie zunächst die Rechteverwaltung einrichten. IRM verwendet den Azure Rights Management Service von Azure Information Protection, um Nutzungseinschränkungen zu verschlüsseln und zuzuweisen. Einige Microsoft 365-Pläne umfassen Azure Rights Management, aber nicht alle. Weitere Informationen finden Sie [unter Support für Azure Rights Management in Office-Anwendungen und-Dienste](https://docs.microsoft.com/azure/information-protection/understand-explore/office-apps-services-support).
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a>Aktivieren des IRM-Diensts mithilfe von SharePoint Admin Center

Bevor Ihre Organisation SharePoint-Listen und-Bibliotheken mit IRM schützen kann, müssen Sie zunächst den Rechteverwaltungsdienst für Ihre Organisation aktivieren. Weitere Informationen finden Sie unter [Aktivieren von Azure Rights Management](https://docs.microsoft.com/information-protection/deploy-use/activate-service). Sie müssen ein Geschäfts-oder Schulkonto verwenden, das über globale Administratorrechte verfügt, um den Rechteverwaltungsdienst zu aktivieren. Andernfalls können Sie IRM-Funktionen nicht mit SharePoint Online verwenden.
  
Melden Sie sich nach dem Aktivieren des Rights Management-Diensts beim SharePoint Admin Center an, um IRM zu aktivieren.
  
1. Melden Sie sich als globaler Administrator oder SharePoint-Administrator an.
    
2. Wählen Sie das Symbol für das App-Startfeld ![The app launcher icon in Office 365](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png) in der oberen linken Ecke und dann **Administrator** aus, um das Microsoft 365 Admin Center zu öffnen. (Wenn die Kachel "admin" nicht angezeigt wird, verfügen Sie nicht über Administratorberechtigungen in Ihrer Organisation.) 
    
3. Wählen Sie im linken Bereich **Admin Center** \>**SharePoint** aus.
    
4. Klicken Sie im linken Bereich auf **Einstellungen**, und wählen Sie dann die **Seite klassische Einstellungen**aus.
    
5. Wählen Sie im Abschnitt **Verwaltung von Informationsrechten (IRM)** **die Option in der Konfiguration angegebene IRM-Dienst verwenden**aus, und klicken Sie dann auf **IRM-Einstellungen aktualisieren**. Nachdem Sie IRM-Einstellungen aktualisiert haben, können Personen in Ihrer Organisation IRM in Ihren SharePoint-Listen und-Dokumentbibliotheken verwenden. Die entsprechenden Optionen können jedoch bis zu einer Stunde dauern, um Sie in den Einstellungen für Bibliothekseinstellungen und Listen anzuzeigen.
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a>IRM-enable SharePoint-Dokumentbibliotheken und-Listen
<a name="__toc220831191"> </a>

Nach dem Aktualisieren von IRM-Einstellungen können Websitebesitzer Ihre SharePoint-Listen und-Dokumentbibliotheken IRM-schützen. Weitere Informationen finden Sie unter [Anwenden der Verwaltung von Informationsrechten auf eine Liste oder Bibliothek](apply-irm-to-a-list-or-library.md).
  
Wenn Websitebesitzer IRM für eine Liste oder Bibliothek aktivieren, können Sie alle unterstützten Dateitypen in dieser Liste oder Bibliothek schützen. Wenn IRM für eine Bibliothek aktiviert ist, gilt die Rechteverwaltung für alle Dateien in dieser Bibliothek. Wenn Sie IRM für eine Liste aktivieren, gilt die Rechteverwaltung nur für Dateien, die Listenelementen zugeordnet sind, und nicht für die eigentlichen Listenelemente.
  
Wenn Personen Dateien in einer IRM-fähigen Liste oder Bibliothek herunterladen, werden die Dateien verschlüsselt, sodass nur autorisierte Personen Sie anzeigen können. Jede Datei mit verwalteten Rechten enthält auch eine Veröffentlichungslizenz, die den Personen, die die Datei anzeigen, Einschränkungen auferlegt. Zu den typischen Einschränkungen gehören das schreibgeschützte Erstellen einer Datei, das Deaktivieren des Kopierens von Text, das verhindern, dass Benutzer eine lokale Kopie speichern, und das verhindern, dass Benutzer die Datei drucken. Client Programme, die IRM-Unterstützte Dateitypen lesen können, verwenden die Veröffentlichungslizenz in der Datei mit verwalteten Rechten, um diese Einschränkungen zu erzwingen. Auf diese Weise behält eine Datei mit verwalteten Rechten ihren Schutz auch nach dem Herunterladen bei. Informationen zum Aktivieren von IRM für eine Liste oder Bibliothek finden Sie unter [Anwenden der Verwaltung von Informationsrechten auf eine Liste oder Bibliothek](apply-irm-to-a-list-or-library.md).
  
Sie können Dokumente in einer IRM-fähigen Bibliothek nicht mithilfe von Office in einem Browser erstellen oder bearbeiten. Stattdessen kann eine Person gleichzeitig IRM-verschlüsselte Dateien herunterladen und bearbeiten. Verwenden Sie das Einchecken und Auschecken, um die *gemeinsame Dokumenterstellung* oder die Erstellung für mehrere Benutzer zu verwalten. 
  
Wenn Sie eine PDF-Datei aus einer IRM-geschützten Bibliothek herunterladen, erstellt Microsoft 365 eine geschützte PDF-Datei. Die Dateierweiterung ändert sich nicht, die Datei ist jedoch geschützt. Zum Anzeigen dieser Datei benötigen Sie den Azure Information Protection-Viewer, den vollständigen Azure Information Protection-Client oder eine andere Anwendung, die das Anzeigen geschützter PDF-Dateien unterstützt. 
  
SharePoint Online unterstützt die Verschlüsselung der folgenden Dateitypen:
  
- PDF
    
- Die 97-2003-Dateiformate für die folgenden Microsoft Office Programme: Word, Excel und PowerPoint
    
- Die Office Open XML Formate für die folgenden Microsoft Office-Programme: Word, Excel und PowerPoint
    
- Das XML Paper Specification (XPS)-Format
 
> [!NOTE]
> Der IRM-Schutz kann nicht auf geschützte Dokumente (wie Digital signierte PDF-Dateien) angewendet werden, da SharePoint das Dokument beim Hochladen öffnen muss. 

## <a name="next-steps"></a>Nächste Schritte
<a name="__toc220831191"> </a>

Nachdem Sie IRM für SharePoint Online aktiviert haben, können Sie mit der Anwendung der Rechteverwaltung auf Listen und Bibliotheken beginnen. Weitere Informationen finden Sie unter [Anwenden der Verwaltung von Informationsrechten auf eine Liste oder Bibliothek](apply-irm-to-a-list-or-library.md).
  
Der neue OneDrive-synchronisierungsclient für Windows unterstützt jetzt das Synchronisieren von IRM-geschützten SharePoint-Dokumentbibliotheken und OneDrive-Speicherorten (solange die IRM-Einstellung für die Bibliothek nicht auf Ablauf von Dokumentzugriffs rechten festgelegt ist). Weitere Informationen oder erste Schritte zum Bereitstellen des neuen Synchronisierungs Clients finden Sie unter [deploy the New OneDrive Sync Client for Windows](https://support.office.com/article/3f3a511c-30c6-404a-98bf-76f95c519668).
  
[Seitenanfang](#introduction)  
