---
title: Suche und Kennzeichnung
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 22f5adad-1bc0-460d-94a9-8732929f5b99
description: In Advanced eDiscovery können Sie mit dem Such-und Markierungs Modul die Dokumente in Ihrem Fall durchsuchen, in der Vorschau anzeigen und organisieren. Derzeit befindet sich dieses Modul in der Betaphase.
ms.openlocfilehash: f5e192988519a9190aa53efef35a8e584e0987cc
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802898"
---
# <a name="search-and-tagging"></a>Suche und Kennzeichnung

In Advanced eDiscovery können Sie mit dem Such-und Markierungs Modul die Dokumente in Ihrem Fall durchsuchen, in der Vorschau anzeigen und organisieren. Derzeit befindet sich dieses Modul in der Betaphase. Eine kurze Demonstration der Suche und Kennzeichnung finden Sie unter [Verwalten von Daten mit erweiterten eDiscovery](https://www.youtube.com/watch?v=VaPYL3DHP6I) -Videos.

> [!NOTE]
> Für Advanced eDiscovery ist ein Office 365 E3-Abonnement mit dem Add-On für erweiterte Compliance oder ein E5-Abonnement für Ihre Organisation erforderlich. Wenn Sie nicht über diesen Plan verfügen und Advanced eDiscovery ausprobieren möchten, können Sie sich [für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
## <a name="search-the-documents-in-your-case"></a>Durchsuchen der Dokumente in Ihrem Fall

Nachdem Sie Dokumente in einem erweiterten eDiscovery-Fall verarbeitet haben (und optional das Modul "Analyze" oder "Relevanz" ausführen), können Sie die Such-und Kennzeichnung zum Durchsuchen von Dokumenten verwenden und diese dann organisieren, indem Sie fallspezifische Tags (auch Bezeichnungen genannt) anwenden. Sie können eine Suchabfrage mithilfe der bereitgestellten Bedingungs Karten oder mithilfe einer KQL-ähnliche Abfragesprache in der Bedingungsliste Stichwörter definieren. Es werden allgemeine KQL-Syntax wie and, or, Not und Near (n) unterstützt, sowie nachstehende mehrstellige Platzhalterzeichen (*). 

In der folgenden Tabelle sind die Eigenschaften aufgeführt, nach denen Sie mithilfe einer KQL-Stichwortabfrage suchen können. Alternativ können Sie eine Bedingungs Karte für im erweiterten eDiscovery-Such Tool verwenden, um einer Suchabfrage eine Bedingung (für ausgewählte Eigenschaften) hinzuzufügen.

|**Eigenschaft**|**Beschreibung**|
|:-----|:-----|
|**caselabel** <br/> | Der Name des Tags, das erstellt/angewendet wird, wenn ein Dokument markiert wird. <br/> |
|**Depotbank** <br/> | Die einem Dokument zugeordnete Depotbank; Einschränkungen vorbehalten. <br/> |
|**date** <br/> | Gesendet am-Datum für e-Mail; das geänderte Datum für Website Dokumente. <br/> |
|**FileID** <br/> | Die Datei-ID in der Groß-/Kleinschreibung. <br/> |
|**filetype** <br/> | Die systemeigene Dateierweiterung. <br/> |
|**fileclass** <br/> | E-Mail, Dokument oder Anlage. <br/> |
|**senderauthor** <br/> | Der Absender für e-Mail; der Autor für Website Dokumente. <br/> |
|**size** <br/> | Die Größe der Datei in KB. <br/> |
|**Betreff erstellt** <br/> | Betreff für e-Mail; der Titel für Website Dokumente. <br/> |
|**bcc** <br/> | Das Feld "Bcc" einer e-Mail. <br/> |
|**cc** <br/> | Das CC-Feld einer e-Mail. <br/> |
|**Teilnehmer** <br/> | Die e-Mail-Adresse aller Teilnehmer an einem e-Mail-Thread, einschließlich fehlender Links. <br/> |
|**Empfangen** <br/> | Das Datum, an dem eine e-Mail empfangen wurde. <br/> |
|**recipients** <br/> | Empfänger einer e-Mail, die in den Feldern "an", "CC" oder "Bcc" enthalten sind. <br/> |
|**sender** <br/> | Der Absender einer e-Mail. <br/> |
|**LastModifiedDate** <br/> | Das Datum der letzten Änderung eines Website Dokuments. <br/> |
|**Gesendet** <br/> | Das gesendete Datum einer e-Mail. <br/> |
|**to** <br/> | Der Empfänger, der im Feld an einer e-Mail aufgeführt ist. <br/> |
|**Autor** <br/> | Der Autor eines Website Dokuments. <br/> |
|**title** <br/> | Der Titel eines Website Dokuments. <br/> |
|**dominanttheme**\* <br/> | Das dominante Design eines Elements. <br/> |
|**themeslist**\* <br/> | Designs, die einem Element zugeordnet sind. <br/> |
|**readpercentile_ [issuenum]**\*\* <br/> | Das Lese-Quantil eines Elements für das von [issuenum] definierte Problem. <br/> |
|**relevancescore_ [issuenum]**\*\* <br/> | Das Relevanz-Ergebnis eines Elements für das von [issuenum] definierte Problem. <br/> |
|**relevancetag_ [Tagname]**\*\* <br/> | Wenn ein Element für die Relevanz manuell markiert wurde, wird das von [Tagname] definierte Tag verwendet. <br/> |
|||

\*Nur verfügbar, wenn das Designmodul ausgeführt wurde.

\*\*Nur verfügbar, wenn das Modul Relevanz ausgeführt wurde.

Alternativ können Sie eine Bedingungs Karte im erweiterten eDiscovery-Such Tool verwenden, um einer Suchabfrage eine Bedingung (für ausgewählte Eigenschaften) hinzuzufügen. Im folgenden Screenshot sind die Bedingungen dargestellt, die einer Abfrage hinzugefügt werden können. Die Spalte **Group** gibt an, ob die Eigenschaft auf e-Mail, Website Dokumente oder beides angewendet wird (angegeben durch den *gemeinsamen*Wert). In dieser Spalte werden auch die durchsuchbaren Eigenschaften identifiziert, die nach dem Ausführen des Moduls Relevanz verfügbar sind.

![Suchbedingungen im erweiterten eDiscovery-Such Tool](media/AeDSearchConditions.png)

Weitere Informationen zu durchsuchbaren Eigenschaften finden Sie unter [Keyword-Abfragen und Suchbedingungen](keyword-queries-and-search-conditions.md).
  
## <a name="see-also"></a>Siehe auch

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Grundlegendes zur Relevanz der Bewertung](assessment-in-relevance-in-advanced-ediscovery.md)
  
[Tagging und Bewertung](tagging-and-assessment-in-advanced-ediscovery.md)
  
[Tagging und Relevanz Training](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[Analyse der nach Verfolgungs Relevanz](track-relevance-analysis-in-advanced-ediscovery.md)
  
[Entscheidung basierend auf den Ergebnissen](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[Testen der Relevanz-Analyse](test-relevance-analysis-in-advanced-ediscovery.md)

