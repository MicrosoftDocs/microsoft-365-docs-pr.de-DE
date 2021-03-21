---
title: Einrichten von Information Rights Management (IRM) im SharePoint Admin Center
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
description: Erfahren Sie, wie Sie SharePoint Online IRM über Microsoft Azure Active Directory-Rechteverwaltungsdienste (RMS) zum Schutz von SharePoint-Listen und Dokumentbibliotheken verwenden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 68db84118ac8ccd7c734152aa28816db819198f7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919401"
---
# <a name="set-up-information-rights-management-irm-in-sharepoint-admin-center"></a>Einrichten von Information Rights Management (IRM) im SharePoint Admin Center

Innerhalb von SharePoint Online greift der IRM-Schutz für Dateien auf der Ebene von Listen und Bibliotheken. Bevor Ihre Organisation IRM-Schutz verwenden kann, müssen Sie zuerst Rights Management einrichten. Bei der Verschlüsselung und Zuweisung von Benutzereinschränkungen basiert IRM auf dem Azure Rights Management-Dienst (Azure RMS) aus Azure Information Protection. Einige Microsoft 365-Pläne umfassen Azure Rights Management, aber nicht alle. Weitere Informationen finden Sie unter [How Office applications and services support Azure Rights Management](/azure/information-protection/understand-explore/office-apps-services-support).
  
## <a name="turn-on-irm-service-using-sharepoint-admin-center"></a>Aktivieren des IRM-Diensts mithilfe des SharePoint Admin Center

Bevor Ihre Organisation SharePoint-Listen und -Bibliotheken durch IRM schützen kann, müssen Sie zuerst den Rechteverwaltungsdienst für Ihre Organisation aktivieren. Weitere Informationen finden Sie unter [Aktivieren von Azure Rights Management](/information-protection/deploy-use/activate-service). Sie müssen ein Arbeits- oder Schulkonto verwenden, das über globale Administratorrechte verfügt, um den Rechteverwaltungsdienst zu aktivieren. Andernfalls können Sie keine IRM-Features mit SharePoint Online verwenden.
  
Melden Sie sich nach dem Aktivieren des Rechteverwaltungsdiensts beim SharePoint Admin Center an, um IRM zu aktivieren.
  
1. Melden Sie sich als globaler Administrator oder SharePoint-Administrator an.
    
2. Wählen Sie das Symbol für das App-Startfeld ![The app launcher icon in Office 365](../media/e5aee650-c566-4100-aaad-4cc2355d909f.png) in der oberen linken Ecke und dann **Administrator** aus, um das Microsoft 365 Admin Center zu öffnen. (Wenn die Kachel "Admin" nicht angezeigt wird, verfügen Sie nicht über Administratorberechtigungen in Ihrer Organisation.) 
    
3. Wählen Sie im linken Bereich **Admin Center** \>**SharePoint** aus.
    
4. Wählen Sie im linken Bereich **Einstellungen** aus, und wählen Sie dann klassische **Einstellungsseite aus.**
    
5. Wählen Sie im Abschnitt Verwaltung von Informationsrechten **(Information Rights Management, IRM)** die Option Verwenden des in Ihrer Konfiguration angegebenen **IRM-Diensts** aus, und wählen Sie **dann Aktualisieren von IRM-Einstellungen aus.** Nach dem Aktualisieren der IRM-Einstellungen können Personen in Ihrer Organisation mit der Verwendung von IRM in ihren SharePoint-Listen und Dokumentbibliotheken beginnen. Allerdings kann es bis zu einer Stunde dauern, bis die Optionen in den Bibliothekseinstellungen und Listeneinstellungen angezeigt werden.
    
## <a name="irm-enable-sharepoint-document-libraries-and-lists"></a>IRM-aktivierende SharePoint-Dokumentbibliotheken und -listen
<a name="__toc220831191"> </a>

Nach dem Aktualisieren der IRM-Einstellungen können Websitebesitzer ihre SharePoint-Listen und Dokumentbibliotheken durch IRM schützen. Weitere Informationen finden Sie unter [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).
  
Wenn Websitebesitzer IRM für eine Liste oder Bibliothek aktivieren, können sie alle unterstützten Dateitypen in dieser Liste oder Bibliothek schützen. Wenn IRM für eine Bibliothek aktiviert ist, gilt die Rechteverwaltung für alle Dateien in dieser Bibliothek. Wenn Sie IRM für eine Liste aktivieren, gilt die Rechteverwaltung nur für Dateien, die Listenelementen zugeordnet sind, nicht den tatsächlichen Listenelementen.
  
Wenn Benutzer Dateien in einer IRM-aktivierten Liste oder Bibliothek herunterladen, werden die Dateien verschlüsselt, sodass nur autorisierte Personen sie anzeigen können. Jede Datei mit verwalteten Rechten enthält auch eine Ausstellungslizenz, die den Personen, die die Datei anzeigen, Einschränkungen auferlegt. Typische Einschränkungen sind das schreibgeschützte Erstellen einer Datei, das Deaktivieren des Kopierens von Text, das Verhindern des Speicherns einer lokalen Kopie und das Verhindern, dass Personen die Datei drucken. Clientprogramme, die IRM-unterstützte Dateitypen lesen können, verwenden die Ausstellungslizenz innerhalb der Datei mit verwalteten Rechten, um diese Einschränkungen durchzusetzen. Auf diese Weise behält eine Datei mit verwalteten Rechten ihren Schutz auch nach dem Herunterladen bei. Informationen zum Aktivieren von IRM in einer Liste oder Bibliothek finden Sie unter [Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).
  
Sie können Dokumente nicht in einer IRM-aktivierten Bibliothek mit Office in einem Browser erstellen oder bearbeiten. Stattdessen kann eine Person gleichzeitig IRM-verschlüsselte Dateien herunterladen und bearbeiten. Verwenden Sie das Ein- und Auschecken, um  *die gemeinsamen*  Erstellungen oder die Erstellung über mehrere Benutzer hinweg zu verwalten. 
  
Wenn Sie eine PDF-Datei aus einer IRM-geschützten Bibliothek herunterladen, erstellt Microsoft 365 eine geschützte PDF-Datei. Die Dateierweiterung ändert sich nicht, aber die Datei ist geschützt. Zum Anzeigen dieser Datei benötigen Sie den Azure Information Protection-Viewer, den vollständigen Azure Information Protection-Client oder eine andere Anwendung, die das Anzeigen geschützter PDF-Dateien unterstützt. 
  
SharePoint Online unterstützt die Verschlüsselung der folgenden Dateitypen:
  
- PDF
    
- Die Dateiformate 97-2003 für die folgenden Microsoft Office: Word, Excel und PowerPoint
    
- Die Office Open XML-Formate für die folgenden Microsoft Office: Word, Excel und PowerPoint
    
- Das XML Paper Specification (XPS)-Format
 
> [!NOTE]
> Der IRM-Schutz kann nicht auf geschützte Dokumente (z. B. digital signierte PDF-Dateien) angewendet werden, da SharePoint das Dokument beim Hochladen öffnen muss. 

## <a name="next-steps"></a>Nächste Schritte
<a name="__toc220831191"> </a>

Nachdem Sie IRM für SharePoint Online aktiviert haben, können Sie mit der Anwendung der Rechteverwaltung auf Listen und Bibliotheken beginnen. Weitere Informationen finden Sie [unter Apply Information Rights Management to a list or library](apply-irm-to-a-list-or-library.md).
  
Der neue #A0 für Windows unterstützt jetzt die Synchronisierung von IRM-geschützten SharePoint-Dokumentbibliotheken und #A1 (solange die #A1 für die Bibliothek nicht auf ablaufende Dokumentzugriffsrechte festgelegt ist). Weitere Informationen oder erste Schritte zur Bereitstellung des neuen Synchronisierungsclients finden Sie unter [Deploy the new OneDrive sync client for Windows](/onedrive/deploy-on-windows).
  
[Seitenanfang](set-up-irm-in-sp-admin-center.md)