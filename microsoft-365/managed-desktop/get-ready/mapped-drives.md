---
title: Voraussetzungen zugeordneter Laufwerke für Microsoft Managed Desktop
description: Wichtige Schritte, um sicherzustellen, dass
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: cd45d6155fc0e01f6a285f6182aa051281d160e0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922908"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Voraussetzungen zugeordneter Laufwerke für Microsoft Managed Desktop

Viele Unternehmensumgebungen haben Legacyanforderungen für zugeordnete Laufwerke, um benutzern oder Teams das Freigeben und Speichern von Dateien oder für lokale Anwendungen zu ermöglichen. Microsoft empfiehlt die Verwendung von zugeordneten Laufwerken mit microsoft Managed Desktop nicht. Stattdessen wird empfohlen, ihre Dateizugriffslösungen wie folgt zu modernisieren:
  
- Migrieren Sie zugeordnete Laufwerke, die von einzelnen Benutzern verwendet werden, zu OneDrive for Business. 
- Migrieren Sie zugeordnete Laufwerke, die von Teams zum Freigeben von Dateien zu SharePoint Online verwendet werden. 
- Modernisieren oder ersetzen Sie alle Anwendungen, die lokale Dateifreigaben verwenden, um diese Anforderung zu entfernen.
  
Die Modernisierung dieser Dienste ermöglicht eine optimale Benutzeroberfläche mit Microsoft Managed Desktop. Microsoft FastTrack Services unterstützt Sie bei der Modernisierung Ihrer Umgebung mithilfe von Microsoft Cloud Services. Sie können unter Berechtigte Dienste und [](/fasttrack/m365-eligible-services-and-plans) Pläne überprüfen, ob Sie für FastTrack-Dienste berechtigt sind, und sie dann direkt kontaktieren, um sich auf Microsoft Managed Desktop vorzubereiten. Hintergrundinformationen zur FastTrack OneDrive for Business- oder SharePoint #A0 finden Sie unter [Data Migration](/fasttrack/o365-data-migration).

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Zugeordnete Laufwerke auf Microsoft Managed Desktop
 
Wenn Sie zugeordnete Laufwerke für einige Verwendungsfälle nicht entfernen oder ersetzen können, sollten Sie eine Supportanfrage im Microsoft Managed Desktop Admin Portal übermitteln, damit sie für Microsoft Managed Desktop-Benutzer bereitgestellt werden.
    
Für eine solche Anforderung müssen Sie die folgenden Details in der Supportanfrage bereitstellen: 

- Alle UNC-Pfade zu Dateifreigabestandorten, die für Microsoft Managed Desktop-Geräte zugeordnet werden müssen 
- Benutzergruppen, die Zugriff auf diese Dateifreigabestandorte benötigen 
- Jeder bestimmte Laufwerkbuchstabe, der zugewiesen werden muss (falls erforderlich)

Beispiel:

| Laufwerkbuchstabe | UNC-Pfad | Benutzergruppe |
|--------------|----------|------------|
| X:  | \\\server\share\Marketing | ContosoMarketing |

Es liegt in ihrer Verantwortung sicherzustellen, dass Benutzer und Gruppen über die richtigen Berechtigungen für den Zugriff auf Dateifreigabestandorte verfügen und darauf zugreifen können, dass auf die lokalen Dateidienste zugegriffen werden kann. Darüber hinaus sollten Sie ihre Anforderungen für solche Dateifreigaben so schnell wie möglich entfernen.

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>So verfügen Sie über zugeordnete Laufwerke, die in Microsoft Managed Desktop bereitgestellt werden
 
Stellen Sie sicher, dass zugeordnete Laufwerke nicht vermieden werden können, und Sie haben die Anforderungen sorgfältig überprüft, bevor Sie eine Dienstanforderung übermitteln. Führen Sie dann die folgenden Schritte aus:

1. Navigieren Sie [zu Microsoft Endpoint Manager,](https://endpoint.microsoft.com/) und wählen Sie "Problembehandlung + Support" aus, und suchen Sie dann im Abschnitt Microsoft Managed Desktop nach "Dienstanforderungen".  
2. Senden Sie eine Supportanfrage mit dem Titel "Bereitstellung zugeordneter Laufwerke" und geben Sie alle erforderlichen Dateifreigabedetails an.  
3. Microsoft Managed Desktop IT Operations wird mithilfe von Supportanforderungsupdates darüber informieren, wann die Anforderung abgeschlossen wurde. Anfangs wird diese Konfiguration nur auf Geräten in der Testbereitstellungsgruppe bereitgestellt.  
4. Sie müssen testen und bestätigen, ob die von den Microsoft Managed Desktop-IT-Vorgängen bereitgestellte Konfiguration wie erwartet funktioniert. Antworten Sie auf der Registerkarte Diskussion in den Details der gleichen Supportanfrage, um Microsoft Managed Desktop IT Operations zu benachrichtigen, sobald Sie ihre Tests abgeschlossen haben.  
5. Das Microsoft Managed Desktop IT Operations-Team stellt die Konfiguration dann für die anderen Bereitstellungsgruppen zur Bereitstellung zur Seite.