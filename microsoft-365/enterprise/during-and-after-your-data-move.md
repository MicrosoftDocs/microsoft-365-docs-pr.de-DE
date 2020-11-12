---
title: Während und nach der Datenverschiebung
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.collection: SPO_Content
search.appverid:
- MET150
localization_priority: Normal
ms.assetid: f47e3e09-b1dc-4b80-b6ea-fd6e0933407f
f1.keywords:
- NOCSH
description: Bei Datenverschiebungen handelt es sich um Back-End-Vorgänge, die stattfinden, wenn Microsoft Dienste und zugeordnete Daten für Ihren Mandanten in eine neue Rechenzentrumsregion verschiebt.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 63536a46e28f264f49e8071710221b0847f62414
ms.sourcegitcommit: 86e878849a8bdd456cee6a3f49939d26223fb626
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2020
ms.locfileid: "48997791"
---
# <a name="during-and-after-your-data-move"></a>Während und nach der Datenverschiebung

Datenverschiebungen sind eine Back-End-Operation mit minimalen Auswirkungen auf die Endbenutzer. Es sind keine Maßnahmen erforderlich, während Microsoft jeden Dienst und die zugehörigen Daten für Ihren Mandanten in ein neues Geo-Rechenzentrum verschiebt. Der Datentransfer und die Validierung erfolgen im Hintergrund im Voraus mit minimalen Auswirkungen auf die Benutzer.
  
> [!NOTE]
> Die Verschiebungen werden zu unterschiedlichen Zeiten für jeden Dienst ausgeführt. Dadurch sehen Sie die beschriebene eingeschränkte Funktionalität für jeden Dienst zu unterschiedlichen Zeiten. 
  
Sehen Sie sich das Microsoft 365-Nachrichten Center zur Bestätigung an, wenn Moves für jeden Exchange Online, SharePoint Online und Teamchat Dienst abgeschlossen werden. Wie in der folgenden Tabelle dargestellt, kann es bis zu 24 Monate nach dem Ende des Registrierungszeitraums dauern, um die wichtigsten Kundendaten bei Rest-Verschiebungen an das neue Rechenzentrum Geo zu vervollständigen.   

|**Kunden mit Anmeldeland in**|**Alle Verschiebungen abgeschlossen bis**|
|:-----|:-----|
|Australien, Neuseeland, Fidschi  <br/> |1. Juli 2022  <br/> |
|Japan  <br/> |1. Juli 2022  <br/> |
|Indien  <br/> |1. Juli 2022  <br/> |
|Kanada  <br/> |1. Juli 2022  <br/> |
|Südkorea  <br/> |1. Juli 2022  <br/> |
|Vereinigtes Königreich  <br/> |1. Juli 2022  <br/> |
|Frankreich  <br/> |1. Juli 2022  <br/> |
|Vereinigte Arabische Emirate  <br/> |1. Juli 2022  <br/> |
|Südafrika  <br/> |1. Juli 2022  <br/> |
|Schweiz, Liechtenstein  <br/> |1. Juli 2022  <br/> |
|Norwegen  <br/> |1. November 2022  <br/> |
|Deutschland  <br/> |1. Mai 2023  <br/> |

## <a name="exchange-online"></a>Exchange Online

Da die Verschiebung der einzelnen Benutzer in das neue Geo-Rechenzentrum für einen einzelnen Mandanten einige Zeit in Anspruch nimmt, werden sich einige Benutzer während der Verschiebung noch im alten Geo-Rechenzentrum befinden, während sich andere im neuen Geo-Rechenzentrum befinden. Das bedeutet, dass einige Funktionen, die den Zugriff auf mehrere Postfächer beinhalten, während eines Zeitraums des Verschiebevorgangs, der Wochen dauern kann, möglicherweise nicht vollständig funktionieren. Diese Funktionen werden in den folgenden Abschnitten ausführlich behandelt.
  
### <a name="open-shared-folder-in-outlook-web-access"></a>Öffnen von "Freigegebener Ordner" in Outlook Web Access

Einige Benutzer öffnen einen freigegebenen E-Mail-Ordner aus einem anderen Postfach (für das der Benutzer Lese- oder Schreibberechtigung hat) in Outlook Web Access mithilfe der Funktion "Freigegebener Ordner". In der folgenden Tabelle wird beschrieben, wie der Zugriff auf freigegebene Ordner während einer Postfachverschiebung funktioniert. Bitte beachten Sie, dass Benutzer mit uneingeschränkten Berechtigungen für ein freigegebenes Postfach das Postfach während der Verschiebung mit Outlook Web Access öffnen können. 
  
|**Konfiguration**|**Beschreibung**|
|:-----|:-----|
|Der Benutzer hat die Berechtigung für den Postfachordner eines anderen Postfachs  <br/> |Potenziell eingeschränkt.  <br/> Wenn sich Benutzer A und Postfach B während der Mandantenverschiebung nicht im selben Geo befinden, kann Benutzer A den Ordner von Postfach B in Outlook Web Access nicht öffnen, wenn Benutzer A nur über die Berechtigung für einen bestimmten Ordner in Postfach B verfügt.  <br/> Um einen freigegebenen Ordner hinzuzufügen, klicken Sie mit der rechten Maustaste auf den Benutzernamen in der linken Navigationsleiste und wählen Sie **Freigegebenen Ordner hinzufügen** aus.  <br/> |
|Der Benutzer hat uneingeschränkte Berechtigung für den Postfachordner eines anderen Postfachs  <br/> |Vollständig unterstützt.  <br/> Wenn Benutzer A über die Berechtigung "Vollzugriff" auf Postfach B verfügt, kann Benutzer A im linken Navigationsbereich in Outlook Web Access auf den freigegebenen Ordner klicken, um ein Fenster mit Postfach B zu öffnen.  Ein Benutzer kann ein freigegebenes Postfach mit Outlook Web Access während der Verschiebung ohne nachteilige Auswirkungen öffnen. Die Einschränkung gilt nur für die Freigabe auf Ordnerebene in einem Postfach.           |
  
## <a name="sharepoint-online"></a>SharePoint Online

Wenn SharePoint Online verschoben wird, werden auch Daten für die folgenden Dienste verschoben:
  
- One Drive for Business
    
- Microsoft 365-Videodienste
    
- Office in einem Browser
    
- Microsoft 365 Apps for Enterprise
    
- Visio Pro für Microsoft 365
    
Nach der Verschiebung Ihrer SharePoint Online-Daten könnten u. U. die folgenden Auswirkungen auftreten.
  
### <a name="microsoft-365-video-services"></a>Microsoft 365-Videodienste

- Die Datenverschiebung für Video dauert länger als die Verschiebungen für den Rest Ihrer Inhalte in SharePoint Online.
    
- Nachdem der SharePoint Online-Inhalt verschoben wurde, gibt es einen Zeitrahmen, in dem Videos nicht wiedergegeben werden können.
    
- Wir entfernen die transcodierten Kopien aus dem vorherigen Rechenzentrum und transcodieren sie im neuen Rechenzentrum erneut.
    
### <a name="search"></a>Suche

Während der Verschiebung Ihrer SharePoint Online-Daten migrieren wir Ihren Suchindex und Ihre Sucheinstellungen an einen neuen Speicherort. Bis wir die Verschiebung Ihrer SharePoint Online-Daten **abgeschlossen** haben, werden Ihre Benutzer weiterhin über den Index am ursprünglichen Speicherort bedient. Am neuen Speicherort beginnt die Suche automatisch mit der Durchforstung Ihrer Inhalte, nachdem wir Ihre SharePoint Online-Daten verschoben haben. Ab diesem Zeitpunkt werden Ihre Benutzer aus dem migrierten Index bedient. Änderungen an Ihren Inhalten, die nach der Migration aufgetreten sind, werden erst dann in den migrierten Index aufgenommen, wenn sie durch die Durchforstung erfasst werden. Die meisten Kunden bemerken nicht, dass die Ergebnisse weniger aktuell sind, nachdem wir ihre SharePoint Online-Daten verschoben haben, aber einige Kunden könnten in den ersten 24‑48 Stunden eine geringere Aktualität feststellen. 
  
Die folgenden Suchfunktionen sind betroffen:
  
- Suchergebnisse und Webparts durchsuchen: Die Ergebnisse enthalten keine Änderungen, die nach der Migration aufgetreten sind, bis sie von der Durchforstung erfasst werden. 
    
- Delve: Delve enthält keine Änderungen, die nach der Migration aufgetreten sind, bis sie von der Durchforstung erfasst werden.
    
- Popularität und Suchberichte für die Website: Die Zählungen für Excel-Berichte am neuen Speicherort enthalten nur migrierte Zählungen und Zählungen aus Nutzungsberichten, die nach Abschluss der Verschiebung Ihrer SharePoint Online-Daten ausgeführt wurden. Jegliche Zählungen aus der Übergangszeit gehen verloren und können nicht wiederhergestellt werden. Dieser Zeitraum beträgt in der Regel ein paar Tage. Bei einigen Kunden kann es zu kürzeren oder längeren Verlusten kommen.
    
- Videoportal: Die Anzahl der Ansichten und Statistiken für das Videoportal hängen von den Statistiken für die Excel-Berichte ab, so dass die Anzahl der Ansichten und Statistiken für das Videoportal für den gleichen Zeitraum wie für die Excel-Berichte verloren gehen.
    
- eDiscovery: Elemente, die sich während der Migration geändert haben, werden erst angezeigt, wenn die Durchforstung die Änderungen erfasst hat.
    
- Schutz vor Datenverlust (DLP): Richtlinien werden nicht auf Elemente angewendet, die sich ändern, bis die Durchforstung die Änderungen erfasst hat.

## <a name="microsoft-teams"></a>Microsoft Teams

Zusätzlich zu Exchange Online, SharePoint Online und OneDrive für Unternehmen migriert Microsoft Teams-Chatdienst Daten in das lokale Rechenzentrum.

- Teams-Chatnachrichten, einschließlich privater Nachrichten und Kanalmeldungen.
- Bilder, die in Teams-Chats verwendet wurden.

Teams-Dateien werden in SharePoint Online gespeichert, und Teams-Chatdateien werden in OneDrive for Business gespeichert. Voicemail, Kalender, Chatverlauf und Kontakte werden in Exchange Online gesichert. In vielen Fällen werden Exchange Online, SharePoint Online und OneDrive for Business bereits vom Kunden in der lokalen Rechenzentrumsregion verwendet und sind auch Teil des Microsoft 365-Migrationsprogramms für berechtigte Kundenländer.

## <a name="skype-for-business"></a>Skype for Business

Skype for Business Verschiebungen sind nicht mehr verfügbar.  [Skype for Business Online wird](https://docs.microsoft.com/lifecycle/announcements/skype-for-business-online-retirement) am 31. Juli 2021 zurückgezogen. Nach dieser Zeit kann auf den Dienst nicht mehr zugegriffen werden. 
  
## <a name="related-topics"></a>Verwandte Themen 
 
[Anfordern der Datenverschiebung](request-your-data-move.md)
    
[Allgemeine häufig gestellte Fragen zur Datenverschiebung](data-move-faq.md)
  
[Neue Rechenzentrumsregionen für Microsoft Dynamics CRM Live](https://go.microsoft.com/fwlink/p/?Linkid=615924)
  
[Azure-Dienste nach Region](https://azure.microsoft.com/regions/)
