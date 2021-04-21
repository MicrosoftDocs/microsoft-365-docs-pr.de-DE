---
title: Im Aktivitäts-Explorer gemeldete Bezeichnungsaktionen
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Auflistung von Bezeichnungsaktionen, die im Aktivitäts-Explorer verfügbar sind.
ms.openlocfilehash: ed51c908d6968e3aeae0adbe06d9ba55887bcf83
ms.sourcegitcommit: 1c53f114a810e7aaa2dc876b84d66348492ea36c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51902946"
---
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a>Im Aktivitäts-Explorer verfügbare Bezeichnungsaktivitäten

## <a name="sensitivity-label-applied"></a>Angewendete Vertraulichkeitsbezeichnung

Dieses Ereignis wird jedes Mal generiert, wenn ein nicht gekennzeichnetes Dokument gekennzeichnet oder eine E-Mail mit einer Bezeichnung gesendet wird. 

- Sie wird zum Zeitpunkt des Speicherns in systemeigenen Office-Anwendungen und Webanwendungen erfasst. 
- Sie wird zum Zeitpunkt des Auftretens in Azure Information Protection-Add-Ins erfasst. 
- Aktualisierungs- und Herabstufungsaktionen von Bezeichnungen können auch über das Feld *Bezeichnungsereignistyp und* -filter überwacht werden.   


|Source  |Im Aktivitäts-Explorer gemeldet | Hinweis  |
|---------|---------|---------|
| Word, Excel, PowerPoint|ja |
|Outlook| ja |von Win 32 |
|SharePoint online, OneDrive|ja | |
|Exchange        |ja         | |
|Einheitlicher Azure Information Protection (AIP)-Client und einheitlicher AIP-Scanner |ja |Die Neue *Bezeichnungsaktion* für AIP wird der *bezeichnung zugeordnet, die im* Aktivitäts-Explorer angewendet wird   |
|Microsoft information protection (MIP) SDK         |ja|Die Neue *Bezeichnungsaktion* für AIP wird der *bezeichnung zugeordnet, die im* Aktivitäts-Explorer angewendet wird|
|Rights Management Service (RMS)         |nicht zutreffend         | |
|Power BI Desktop und Web        | nein| Zugriff in den Microsoft 365-Überwachungsprotokollen         |
|Microsoft Cloud App Security (MCAS)         |nein|         |

## <a name="sensitivity-label-changed"></a>Vertraulichkeitsbezeichnung geändert

Dieses Ereignis wird jedes Mal generiert, wenn eine Bezeichnung für das Dokument oder die E-Mail aktualisiert wird.

- Für die AIP Unified-Client-, Unified Scanner- und MIP-SDK-Quellen wurden die *AIP-Upgradebezeichnung* und die *Downgrade-Bezeichnungsaktion* der Aktivitäts-Explorer-Bezeichnung *geändert.*

- Sie wird zum Zeitpunkt des Speicherns in systemeigenen Office-Anwendungen und Webanwendungen erfasst. 
- Sie wird zum Zeitpunkt des Auftretens in einheitlichen Azure Information Protection-Client-Add-Ins und Scannerersetzungen erfasst.
- Aktualisierungs- und Herabstufungsaktionen von Bezeichnungen können auch über das Feld *Bezeichnungsereignistyp und* -filter überwacht werden. Der *Begründungstext* wird auch mit Ausnahme von SharePoint Online und OneDrive erfasst.
- Vertraulichkeitsbezeichnungen, die in officeeigenen Apps in Outlook durchgeführt werden, erfassen die letzte Aktion, die vor Aktionen zum Speichern von Dateien/E-Mail-Senden generiert wurde. Wenn der Benutzer beispielsweise vor dem Senden die Bezeichnung für eine E-Mail mehrmals ändert, wird die letzte Bezeichnung, die in der E-Mail gefunden wurde, wenn sie gesendet wird, im Überwachungsprotokoll erfasst und dann im Aktivitäts-Explorer gemeldet. 


|Source  |Im Aktivitäts-Explorer gemeldet|Hinweis  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |ja         |
|Outlook         |ja         |Win 32|
|SharePoint Online, OneDrive         |ja         |
|Exchange         |ja         |
|Einheitlicher AIP-Client         |ja         |
|AIP Unified Scanner         |ja         |
|MIP SDK         |ja         |
|RMS-Dienst         |nicht zutreffend         |
|Power BI-Desktop und Web         |nein         |Zugriff in den Microsoft 365-Überwachungsprotokollen |
|MCAS     |nein         |         |

## <a name="sensitivity-label-removed"></a>Vertraulichkeitsbezeichnung entfernt

Dieses Ereignis wird jedes Mal generiert, wenn eine Bezeichnung aus einer Datei oder einem Dokument entfernt wird.

- Dieses Ereignis wird zum Zeitpunkt des Speicherns in systemeigenen Office-Anwendungen und Webanwendungen erfasst.
- Sie wird zum Zeitpunkt des Auftretens in Azure Information Protection-Add-Ins erfasst. 
- Die Vertraulichkeitsbezeichnung mit der systemeigenen Office-MIP-Bezeichnung in Outlook erfasst das letzte Bezeichnungsereignis, das vor Datei speichern/E-Mail-Sendeaktionen generiert wurde.

|Source  |Im Aktivitäts-Explorer gemeldet | Hinweis  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |ja         |
|Outlook         |ja         |Win 32|
|SharePoint Online, OneDrive         |ja         |
|Exchange         |ja         |
|Einheitlicher AIP-Client         |ja         |Die *AIP-Entfernen-Bezeichnungsaktion* wird der Aktion "Bezeichnung *entfernt"* im Aktivitäts-Explorer zugeordnet|
|AIP Unified Scanner         |ja         |Die *AIP-Entfernen-Bezeichnungsaktion* wird der Aktion "Bezeichnung *entfernt"* im Aktivitäts-Explorer zugeordnet |
|MIP SDK         |ja         |Die *AIP-Entfernen-Bezeichnungsaktion* wird der Aktion "Bezeichnung *entfernt"* im Aktivitäts-Explorer zugeordnet |
|RMS-Dienst         |nicht zutreffend         |
|Power BI-Desktop und Web         |nein         |Zugriff in den Microsoft 365-Überwachungsprotokollen |
|MCAS     |nein         |         |
 

## <a name="sensitivity-label-file-read"></a>Datei mit Vertraulichkeitsbezeichnungen lesen

Dieses Ereignis wird jedes Mal generiert, wenn ein gekennzeichnetes oder geschütztes Dokument geöffnet wird.

|Source  |Im Aktivitäts-Explorer gemeldet | Hinweis  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |ja         |
|Outlook         |nein         |
|SharePoint Online, OneDrive         |nein         |
|Exchange         |nein         |
|Einheitlicher AIP-Client         |ja         |Die *AIP-Zugriffsaktion* wird  der Datei lesen-Aktion im Aktivitäts-Explorer zugeordnet|
|AIP Unified Scanner         |ja         |Die *AIP-Zugriffsaktion* wird  der Datei lesen-Aktion im Aktivitäts-Explorer zugeordnet|
|MIP SDK         |ja         |Die *AIP-Zugriffsaktion* wird  der Datei lesen-Aktion im Aktivitäts-Explorer zugeordnet|
|RMS-Dienst         |ja         |Die *Zugriffsaktion* wird der Datei lesen-Aktion *im* Aktivitäts-Explorer zugeordnet |
|Power BI-Desktop und Web         |nein         |Zugriff in den Microsoft 365-Überwachungsprotokollen |
|MCAS     |nein         |         |


## <a name="sensitivity-label-files-discovered"></a>Gefundene Vertraulichkeitsbezeichnungsdateien

Dieses Ereignis wird jedes Mal generiert, wenn Dateien erkannt werden, wenn AIP Scanner zum Scannen vertraulicher Daten an verschiedenen Speicherorten verwendet wird und Dateien gefunden werden.

|Source  |Im Aktivitäts-Explorer gemeldet | Hinweis  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |nicht zutreffend         |
|Outlook         |nicht zutreffend         |
|SharePoint Online, OneDrive         |nicht zutreffend         |
|Exchange         |nicht zutreffend         |
|Einheitlicher AIP-Client         |nicht zutreffend       |
|AIP Unified Scanner         |ja         |Die Aktion *"AIP-Aufgefunden"* wird der *Dateierknungsaktion* im Aktivitäts-Explorer zugeordnet|
|MIP SDK         |ja         |Die Aktion *"AIP-Aufgefunden"* wird der *Dateierknungsaktion* im Aktivitäts-Explorer zugeordnet.|
|RMS-Dienst         |nicht zutreffend         |
|Power BI-Desktop und Web         |nicht zutreffend         |
|MCAS     |nicht zutreffend         |         |


## <a name="sensitivity-label-file-renamed"></a>Datei mit Vertraulichkeitsbezeichnung umbenannt

Dieses Ereignis wird jedes Mal generiert, wenn ein Dokument mit einer Vertraulichkeitsbezeichnung umbenannt wird. 

|Source  | Im Aktivitäts-Explorer gemeldet | Hinweis  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |ja         |
|Outlook         |nicht zutreffend         |
|SharePoint Online, OneDrive         |nein        |
|Exchange         |nicht zutreffend         |
|Einheitlicher AIP-Client         |nein         |
|AIP Unified Scanner         |nein         |
|MIP SDK         |nein         |
|RMS-Dienst         |nein      |
|Power BI-Desktop und Web         |nein         |
|MCAS     |nein         |         |


## <a name="sensitivity-label-file-removed"></a>Datei mit Vertraulichkeitsbezeichnungen entfernt

Dieses Ereignis wird jedes Mal generiert, wenn der AIP-Scanner erkennt, dass eine zuvor gescannte Datei entfernt wurde.

|Source  |Im Aktivitäts-Explorer gemeldet | Hinweis  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |nicht zutreffend         |
|Outlook         |nicht zutreffend         |
|SharePoint Online, OneDrive         |nicht zutreffend           |
|Exchange         |nicht zutreffend         |
|Einheitlicher AIP-Client         |nicht zutreffend            |
|AIP Unified Scanner         |ja         |
|MIP SDK         |nicht zutreffend            |
|RMS-Dienst         |nicht zutreffend         |
|Power BI-Desktop und Web         |nicht zutreffend  |
|MCAS     |nicht zutreffend        |         |

### <a name="sensitivity-label-protection-applied"></a>Angewendeter Vertraulichkeitsbezeichnungsschutz

Dieses Ereignis wird generiert, wenn der erste Schutz manuell zu einem Element hinzugefügt wird, das keine Bezeichnung hat.

|Source  |Im Aktivitäts-Explorer gemeldet | Hinweis  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |nein         |
|Outlook         |nein         |
|SharePoint Online, OneDrive         |nicht zutreffend           |
|Exchange         |nein       |
|Einheitlicher AIP-Client         |ja            |
|AIP Unified Scanner         |nicht zutreffend         |
|MIP SDK         |ja            |
|RMS-Dienst         |nicht zutreffend         |
|Power BI-Desktop und Web         |nicht zutreffend            |
|MCAS     |nicht zutreffend        |         |

## <a name="sensitivity-label-protection-changed"></a>Schutz von Vertraulichkeitsbezeichnungen geändert

Dieses Ereignis wird jedes Mal generiert, wenn der Schutz für ein nicht gekennzeichnetes Dokument manuell geändert wird.

|Source  |Im Aktivitäts-Explorer gemeldet |
|---------|---------| 
|Word, Excel, PowerPoint         |nein         |
|Outlook         |nein         |
|SharePoint Online, OneDrive         |nicht zutreffend           |
|Exchange         |nein       |
|Einheitlicher AIP-Client         |ja            |
|AIP Unified Scanner         |nicht zutreffend         |
|MIP SDK         |ja            |
|RMS-Dienst         |nicht zutreffend         |
|Power BI-Desktop und Web         |nicht zutreffend            |
|MCAS     |nicht zutreffend        |

## <a name="sensitivity-label-protection-removed"></a>Schutz von Vertraulichkeitsbezeichnungen entfernt

Dieses Ereignis wird jedes Mal generiert, wenn der Schutz für ein nicht gekennzeichnetes Dokument manuell geändert wird.

|Source  |Im Aktivitäts-Explorer gemeldet |
|---------|---------| 
|Word, Excel, PowerPoint         |nein         |
|Outlook         |nein         |
|SharePoint Online, OneDrive         |nicht zutreffend           |
|Exchange         |nein       |
|Einheitlicher AIP-Client         |ja            |
|AIP Unified Scanner         |nicht zutreffend         |
|MIP SDK         |ja            |
|RMS-Dienst         |nicht zutreffend         |
|Power BI-Desktop und Web         |nicht zutreffend            |
|MCAS     |nicht zutreffend        |

## <a name="sensitivity-label-dlp-policy-matched"></a>Vertraulichkeitsbezeichnung DLP-Richtlinie abgestimmt

Dieses Ereignis wird bei jeder Übereinstimmung mit einer DLP-Richtlinie generiert.

|Source  |Im Aktivitäts-Explorer gemeldet |
|---------|---------| 
|Exchange         |ja       |
|SharePoint Online|ja          |
|Microsoft OneDrive-App |ja|
|Teams |ja   |
|Windows 10-Geräte         |ja |
|MAC         |nein     |
|Lokal         |nein|
|MCAS     |nein        | 

Die Ereignisse für Windows 10-Geräte (Endpoint DLP) sind:

- Datei gelöscht
- Datei erstellt
- Datei in die Zwischenablage kopiert
- Datei geändert
- Datei lesen
- Datei gedruckt
- Datei umbenannt
- Datei auf die Netzwerkfreigabe kopiert
- Datei, auf die von nicht zugelassener App zugegriffen wird


## <a name="retention-label-applied"></a>Angewendete Aufbewahrungsbezeichnung 

Dieses Ereignis wird jedes Mal generiert, wenn ein nicht gekennzeichnetes Dokument gekennzeichnet oder eine E-Mail mit einer Bezeichnung gesendet wird.

- Sie wird zum Zeitpunkt des Speicherns in systemeigenen Office-Anwendungen und Webanwendungen erfasst.

|Source  |Im Aktivitäts-Explorer gemeldet |
|---------|---------| 
|Exchange         |nein       |
|SharePoint Online|ja          |
|Microsoft OneDrive-App |ja|

## <a name="retention-label-changed"></a>Aufbewahrungsbezeichnung geändert

Dieses Ereignis wird jedes Mal generiert, wenn eine Bezeichnung für ein Dokument oder eine E-Mail aktualisiert wird.

- Sie wird zum Zeitpunkt des Speicherns erfasst.

|Source  |Im Aktivitäts-Explorer gemeldet |
|---------|---------| 
|Exchange         |nein       |
|SharePoint Online|ja          |
|Microsoft OneDrive-App |ja|
 
## <a name="retention-label-removed"></a>Aufbewahrungsbezeichnung entfernt

Dieses Ereignis wird jedes Mal generiert, wenn eine Bezeichnung aus einer Datei oder einem Dokument entfernt wird.

- Sie wird zum Zeitpunkt des Speicherns erfasst.

|Source  |Im Aktivitäts-Explorer gemeldet |
|---------|---------| 
|Exchange         |nein       |
|SharePoint Online|ja          |
|Microsoft OneDrive-App |ja|


## <a name="known-issues"></a>Bekannte Probleme
  
- Wenn einem Endbenutzer die empfohlene Bezeichnungstooltipp angezeigt wird, wird sie nicht erfasst. Wenn sich der Benutzer jedoch dafür entscheidet, die empfohlene Bezeichnung anzuwenden, wird die Bezeichnung im Feld *Anwenden wie* *empfohlen angezeigt.*  

- Begründungstext ist derzeit nicht für die Herabstufung von Vertraulichkeitsbezeichnungen aus Sharepoint und OneDrive verfügbar.  

- Typen vertraulicher Informationen stehen derzeit nicht für Aktivitäten zur automatischen Kennzeichnung von Word, Excel, PowerPoint und Outlook sowie SharePoint Online und OneDrive zur Verfügung.
