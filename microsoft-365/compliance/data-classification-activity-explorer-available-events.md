---
title: Beschriftungsaktionen, die im Aktivitäten-Explorer gemeldet wurden
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
description: Auflistung von Bezeichnungsaktivitäten, die im Aktivitäts-Explorer verfügbar sind.
ms.openlocfilehash: d4f6884ad39b16aeb0345f0c976d6ad87f03c05a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52532254"
---
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a>Im Aktivitäts-Explorer verfügbare Bezeichnungsaktivitäten

## <a name="sensitivity-label-applied"></a>Angewendete Vertraulichkeitsbezeichnung

Dieses Ereignis wird jedes Mal generiert, wenn ein nicht gekennzeichnetes Dokument gekennzeichnet oder eine E-Mail mit einer Vertraulichkeitsbezeichnung gesendet wird. 

- Sie wird zum Zeitpunkt des Speicherns in Office und Webanwendungen erfasst. 
- Sie wird zum Zeitpunkt des Auftretens in Azure Information Protection-Add-Ins erfasst. 
- Aktualisierungs- und Herabstufungsaktionen von Bezeichnungen können auch über das Feld *Bezeichnungsereignistyp und* -filter überwacht werden.   


|Quelle  |Im Aktivitäts-Explorer gemeldet | Hinweis  |
|---------|---------|---------|
| Word, Excel, PowerPoint|ja |
|Outlook| ja |von Win 32 |
|SharePoint online, OneDrive|ja | |
|Exchange        |ja         | |
|Einheitlicher Azure Information Protection (AIP)-Client und einheitlicher AIP-Scanner |ja |Die Neue *Bezeichnungsaktion* für AIP wird der *bezeichnung zugeordnet, die im* Aktivitäts-Explorer angewendet wird   |
|Microsoft information protection (MIP) SDK         |ja|Die Neue *Bezeichnungsaktion* für AIP wird der *bezeichnung zugeordnet, die im* Aktivitäts-Explorer angewendet wird|
|Rights Management Service (RMS)         |nicht zutreffend         | |
|Power BI Desktop und Web        | nein| Zugriff in den Microsoft 365 Überwachungsprotokollen         |
|Microsoft Cloud App Security (MCAS)         |nein|         |

## <a name="sensitivity-label-changed"></a>Vertraulichkeitsbezeichnung geändert

Dieses Ereignis wird jedes Mal generiert, wenn eine Vertraulichkeitsbezeichnung für das Dokument oder die E-Mail aktualisiert wird.

- Für die AIP Unified-Client-, Unified Scanner- und MIP-SDK-Quellen wurden die *AIP-Upgradebezeichnung* und die *Downgrade-Bezeichnungsaktion* der Aktivitäts-Explorer-Bezeichnung *geändert.*

- Sie wird zum Zeitpunkt des Speicherns in Office und Webanwendungen erfasst. 
- Sie wird zum Zeitpunkt des Auftretens in einheitlichen Azure Information Protection-Client-Add-Ins und Scannerersetzungen erfasst.
- Aktualisierungs- und Herabstufungsaktionen von Bezeichnungen können auch über das Feld *Bezeichnungsereignistyp und* -filter überwacht werden. Der *Begründungstext* wird auch mit Ausnahme von SharePoint Online und OneDrive.
- Vertraulichkeitsbezeichnungen in Office systemeigenen Apps auf Outlook erfasst die letzte Aktion, die vor Aktionen zum Speichern von Dateien/E-Mail-Senden generiert wurde. Wenn der Benutzer beispielsweise vor dem Senden die Bezeichnung für eine E-Mail mehrmals ändert, wird die letzte Bezeichnung, die in der E-Mail gefunden wurde, wenn sie gesendet wird, im Überwachungsprotokoll erfasst und dann im Aktivitäts-Explorer gemeldet. 


|Quelle  |Im Aktivitäts-Explorer gemeldet|Hinweis  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |ja         |
|Outlook         |ja         |Win 32|
|SharePoint Online, OneDrive         |ja         |
|Exchange         |ja         |
|Einheitlicher AIP-Client         |ja         |
|AIP Unified Scanner         |ja         |
|MIP SDK         |ja         |
|RMS-Dienst         |nicht zutreffend         |
|Power BI Desktop und Web         |nein         |Zugriff in den Microsoft 365 Überwachungsprotokollen |
|MCAS     |nein         |         |

## <a name="sensitivity-label-removed"></a>Vertraulichkeitsbezeichnung entfernt

Dieses Ereignis wird jedes Mal generiert, wenn eine Vertraulichkeitsbezeichnung aus einer Datei oder einem Dokument entfernt wird.

- Dieses Ereignis wird zum Zeitpunkt des Speicherns in Office und Webanwendungen erfasst.
- Sie wird zum Zeitpunkt des Auftretens in Azure Information Protection-Add-Ins erfasst. 
- Die Vertraulichkeitsbezeichnung mit Office systemeigenen MIP-Bezeichnung auf Outlook erfasst das letzte Bezeichnungsereignis, das vor Datei speichern/E-Mail-Sendeaktionen generiert wurde.

|Quelle  |Im Aktivitäts-Explorer gemeldet | Hinweis  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |ja         |
|Outlook         |ja         |Win 32|
|SharePoint Online, OneDrive         |ja         |
|Exchange         |ja         |
|Einheitlicher AIP-Client         |ja         |Die *AIP-Entfernen-Bezeichnungsaktion* wird der Aktion "Bezeichnung *entfernt"* im Aktivitäts-Explorer zugeordnet|
|AIP Unified Scanner         |ja         |Die *AIP-Entfernen-Bezeichnungsaktion* wird der Aktion "Bezeichnung *entfernt"* im Aktivitäts-Explorer zugeordnet |
|MIP SDK         |ja         |Die *AIP-Entfernen-Bezeichnungsaktion* wird der Aktion "Bezeichnung *entfernt"* im Aktivitäts-Explorer zugeordnet |
|RMS-Dienst         |nicht zutreffend         |
|Power BI Desktop und Web         |nein         |Zugriff in den Microsoft 365 Überwachungsprotokollen |
|MCAS     |nein         |         |
 

## <a name="sensitivity-label-file-read"></a>Datei mit Vertraulichkeitsbezeichnungen lesen

Dieses Ereignis wird jedes Mal generiert, wenn ein vertraulichkeitsbeschriftungs- oder geschütztes Dokument geöffnet wird.

|Quelle  |Im Aktivitäts-Explorer gemeldet | Hinweis  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |ja         |
|Outlook         |nein         |
|SharePoint Online, OneDrive         |nein         |
|Exchange         |nein         |
|Einheitlicher AIP-Client         |ja         |Die *AIP-Zugriffsaktion* wird  der Datei lesen-Aktion im Aktivitäts-Explorer zugeordnet|
|AIP Unified Scanner         |ja         |Die *AIP-Zugriffsaktion* wird  der Datei lesen-Aktion im Aktivitäts-Explorer zugeordnet|
|MIP SDK         |ja         |Die *AIP-Zugriffsaktion* wird  der Datei lesen-Aktion im Aktivitäts-Explorer zugeordnet|
|RMS-Dienst         |ja         |Die *Zugriffsaktion* wird der Datei lesen-Aktion *im* Aktivitäts-Explorer zugeordnet |
|Power BI Desktop und Web         |nein         |Zugriff in den Microsoft 365 Überwachungsprotokollen |
|MCAS     |nein         |         |


## <a name="files-discovered"></a>Gefundene Dateien

Dieses Ereignis wird jedes Mal generiert, wenn Dateien erkannt werden, wenn AIP Scanner zum Scannen vertraulicher Daten an verschiedenen Speicherorten verwendet wird und Dateien gefunden werden.

|Quelle  |Im Aktivitäts-Explorer gemeldet | Hinweis  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |nicht zutreffend         |
|Outlook         |nicht zutreffend         |
|SharePoint Online, OneDrive         |nicht zutreffend         |
|Exchange         |nicht zutreffend         |
|Einheitlicher AIP-Client         |nicht zutreffend       |
|AIP Unified Scanner         |ja         |Die Aktion *"AIP-Aufgefunden"* wird der *Dateierknungsaktion* im Aktivitäts-Explorer zugeordnet|
|MIP SDK         |ja         |Die Aktion *"AIP-Aufgefunden"* wird der *Dateierknungsaktion* im Aktivitäts-Explorer zugeordnet.|
|RMS-Dienst         |nicht zutreffend         |
|Power BI Desktop und Web         |nicht zutreffend         |
|MCAS     |nicht zutreffend         |         |


## <a name="sensitivity-label-file-renamed"></a>Datei mit Vertraulichkeitsbezeichnung umbenannt

Dieses Ereignis wird jedes Mal generiert, wenn ein Dokument mit einer Vertraulichkeitsbezeichnung umbenannt wird. 

|Quelle  | Im Aktivitäts-Explorer gemeldet | Hinweis  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |ja         |
|Outlook         |nicht zutreffend         |
|SharePoint Online, OneDrive         |nein        |
|Exchange         |nicht zutreffend         |
|Einheitlicher AIP-Client         |nein         |
|AIP Unified Scanner         |nein         |
|MIP SDK         |nein         |
|RMS-Dienst         |nein      |
|Power BI Desktop und Web         |nein         |
|MCAS     |nein         |         |


## <a name="file-removed"></a>Datei entfernt

Dieses Ereignis wird jedes Mal generiert, wenn der AIP-Scanner erkennt, dass eine zuvor gescannte Datei entfernt wurde.

|Quelle  |Im Aktivitäts-Explorer gemeldet | Hinweis  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |nicht zutreffend         |
|Outlook         |nicht zutreffend         |
|SharePoint Online, OneDrive         |nicht zutreffend           |
|Exchange         |nicht zutreffend         |
|Einheitlicher AIP-Client         |nicht zutreffend            |
|AIP Unified Scanner         |ja         |
|MIP SDK         |nicht zutreffend            |
|RMS-Dienst         |nicht zutreffend         |
|Power BI Desktop und Web         |nicht zutreffend  |
|MCAS     |nicht zutreffend        |         |

### <a name="protection-applied"></a>Angewendeter Schutz

Dieses Ereignis wird generiert, wenn der erste Schutz manuell zu einem Element hinzugefügt wird, das keine Bezeichnung hat.

|Quelle  |Im Aktivitäts-Explorer gemeldet | Hinweis  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |nein         |
|Outlook         |nein         |
|SharePoint Online, OneDrive         |nicht zutreffend           |
|Exchange         |nein       |
|Einheitlicher AIP-Client         |ja            |
|AIP Unified Scanner         |nicht zutreffend         |
|MIP SDK         |ja            |
|RMS-Dienst         |nicht zutreffend         |
|Power BI Desktop und Web         |nicht zutreffend            |
|MCAS     |nicht zutreffend        |         |

## <a name="protection-changed"></a>Schutz geändert

Dieses Ereignis wird jedes Mal generiert, wenn der Schutz für ein nicht gekennzeichnetes Dokument manuell geändert wird.

|Quelle  |Im Aktivitäts-Explorer gemeldet |
|---------|---------| 
|Word, Excel, PowerPoint         |nein         |
|Outlook         |nein         |
|SharePoint Online, OneDrive         |nicht zutreffend           |
|Exchange         |nein       |
|Einheitlicher AIP-Client         |ja            |
|AIP Unified Scanner         |nicht zutreffend         |
|MIP SDK         |ja            |
|RMS-Dienst         |nicht zutreffend         |
|Power BI Desktop und Web         |nicht zutreffend            |
|MCAS     |nicht zutreffend        |

## <a name="protection-removed"></a>Schutz entfernt

Dieses Ereignis wird jedes Mal generiert, wenn der Schutz für ein nicht gekennzeichnetes Dokument manuell geändert wird.

|Quelle  |Im Aktivitäts-Explorer gemeldet |
|---------|---------| 
|Word, Excel, PowerPoint         |nein         |
|Outlook         |nein         |
|SharePoint Online, OneDrive         |nicht zutreffend           |
|Exchange         |nein       |
|Einheitlicher AIP-Client         |ja            |
|AIP Unified Scanner         |nicht zutreffend         |
|MIP SDK         |ja            |
|RMS-Dienst         |nicht zutreffend         |
|Power BI Desktop und Web         |nicht zutreffend            |
|MCAS     |nicht zutreffend        |

## <a name="dlp-policy-matched"></a>Übereinstimmung der DLP-Richtlinie

Dieses Ereignis wird jedes Mal generiert, wenn eine DLP-Richtlinie für ein Dokument oder eine E-Mail-Adresse abgestimmt wird.

|Quelle  |Im Aktivitäts-Explorer gemeldet |
|---------|---------| 
|Exchange         |ja       |
|SharePoint Online|ja          |
|OneDrive |ja|
|Teams |ja   |
|Windows 10-Geräte         |ja |
|MAC         |nein     |
|Lokal         |nein|
|MCAS     |nein        | 

Die Ereignisse für Windows 10 (Endpoint DLP) sind:

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

Dieses Ereignis wird jedes Mal generiert, wenn ein nicht gekennzeichnetes Dokument gekennzeichnet oder eine E-Mail mit einer Aufbewahrungsbezeichnung gesendet wird.

- Sie wird zum Zeitpunkt des Speicherns für ein Dokument und zum Zeitpunkt des Sendens für eine E-Mail erfasst.

|Quelle  |Im Aktivitäts-Explorer gemeldet |
|---------|---------| 
|Exchange         |nein       |
|SharePoint Online|ja          |
|OneDrive |ja|

## <a name="retention-label-changed"></a>Aufbewahrungsbezeichnung geändert

Dieses Ereignis wird jedes Mal generiert, wenn eine Bezeichnung für ein Dokument oder eine E-Mail aktualisiert wird.

- Sie wird zum Zeitpunkt des Speicherns für ein Dokument und zum Zeitpunkt des Sendens für eine E-Mail erfasst.

|Quelle  |Im Aktivitäts-Explorer gemeldet |
|---------|---------| 
|Exchange         |nein       |
|SharePoint Online|ja          |
|OneDrive |ja|
 
## <a name="retention-label-removed"></a>Aufbewahrungsbezeichnung entfernt

Dieses Ereignis wird jedes Mal generiert, wenn eine Bezeichnung aus einer Datei oder einem Dokument entfernt wird.

- Sie wird zum Zeitpunkt des Speicherns für ein Dokument und zum Zeitpunkt des Sendens für eine E-Mail erfasst.

|Quelle  |Im Aktivitäts-Explorer gemeldet |
|---------|---------| 
|Exchange         |nein       |
|SharePoint Online|ja          |
|OneDrive |ja|


## <a name="known-issues"></a>Bekannte Probleme
  
- Wenn einem Endbenutzer die empfohlene Bezeichnungstooltipp angezeigt wird, wird sie nicht erfasst. Wenn sich der Benutzer jedoch dafür entscheidet, die empfohlene Bezeichnung anzuwenden, wird die Bezeichnung im Feld *Anwenden wie* *empfohlen angezeigt.*  

- Begründungstext ist derzeit nicht für die Herabstufung von Vertraulichkeitsbezeichnungen von Sharepoint und OneDrive.  

- Typen vertraulicher Informationen sind derzeit nicht für Aktivitäten zur automatischen Kennzeichnung von Word, Excel, PowerPoint und Outlook sowie SharePoint Online und OneDrive.
