---
title: Erste Schritte mit der DLP-Standardrichtlinie
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 8/10/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie den Bericht verwenden, um die Standardmäßige Richtlinie zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) Ihrer Organisation zu verfeinern.
ms.openlocfilehash: 4530e570f0ce593a7d2cb62acc28dfa4e1658df0
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114083"
---
# <a name="get-started-with-the-default-dlp-policy"></a>Erste Schritte mit der DLP-Standardrichtlinie

Bevor Sie ihre erste Richtlinie zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) erstellen, hilft DLP dabei, Ihre vertraulichen Informationen mit einer Standardrichtlinie zu schützen. Diese Standardrichtlinie und ihre Empfehlung (siehe unten) helfen Ihnen, Ihre vertraulichen Inhalte zu schützen, indem Sie benachrichtigt werden, wenn E-Mails oder Dokumente mit einer Kreditkartennummer für jemanden außerhalb Ihrer Organisation freigegeben wurden. Diese Empfehlung wird auf der **Startseite des** Security Compliance &amp; Centers angezeigt. 
  
Sie können dieses Widget verwenden, um schnell anzuzeigen, wann und wie viele vertrauliche Informationen freigegeben wurden, und dann die Standard-DLP-Richtlinie in nur ein oder zwei Klicks zu verfeinern. Sie können die standardmäßige DLP-Richtlinie auch jederzeit bearbeiten, da sie vollständig anpassbar ist. Wenn die Empfehlung zunächst nicht angezeigt wird, klicken Sie unten im Abschnitt Empfohlen für Sie auf **+Mehr.**  
  
![Widget mit dem Namen Weiter schützen von freigegebenen Inhalten](../media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a>Anzeigen des Berichts und Verfeinern der Standard-DLP-Richtlinie

Wenn das Widget zeigt, dass Benutzer vertrauliche Informationen für Personen außerhalb Ihrer Organisation freigegeben haben, wählen Sie unten die Option **DLP-Richtlinie** verfeinern aus. 
  
Der detaillierte Bericht zeigt, wann und wie viel Inhalt mit Kreditkartennummern in den letzten 30 Tagen freigegeben wurde. Beachten Sie, dass es bis zu 48 Stunden dauern kann, bis Regel übereinstimmungen im Widget angezeigt werden.
  
Um die vertraulichen Informationen zu schützen, verwenden Sie die standardmäßige DLP-Richtlinie:
  
- Erkennt, wann Inhalte in Exchange, SharePoint und OneDrive, die mindestens eine Kreditkartennummer enthalten, für Personen außerhalb Ihrer Organisation freigegeben werden.
    
- Zeigt einen Richtlinientipp an und sendet eine E-Mail-Benachrichtigung an Benutzer, wenn sie versuchen, diese vertraulichen Informationen für Personen außerhalb Ihrer Organisation zu teilen. Weitere Informationen zu diesen Optionen finden Sie unter Senden von [E-Mail-Benachrichtigungen und Anzeigen von Richtlinientipps für DLP-Richtlinien.](use-notifications-and-policy-tips.md)
    
- Generiert detaillierte Aktivitätsberichte, damit Sie Dinge nachverfolgen können, z. B. wer die Inhalte für Personen außerhalb Ihrer Organisation freigegeben hat und wann sie dies getan haben. Sie können die [DLP-Berichte und](view-the-dlp-reports.md) [Überwachungsprotokolldaten](search-the-audit-log-in-security-and-compliance.md) (wobei **Activity** DLP ) verwendet werden,  =  um diese Informationen zu sehen.
    
Um die Standard-DLP-Richtlinie schnell zu verfeinern, können Sie sie verwenden:
  
- Senden Sie eine Vorfallbericht-E-Mail, wenn Benutzer diese vertraulichen Informationen für Personen außerhalb Ihrer Organisation freigeben.
    
- Fügen Sie dem E-Mail-Vorfallbericht weitere Benutzer hinzu.
    
- Blockieren Sie den Zugriff auf den Inhalt, der die vertraulichen Informationen enthält, lassen Sie es dem Benutzer jedoch zu, diese zu überschreiben und zu teilen oder zu senden, falls dies nötig ist.
    
Weitere Informationen zu Schadensberichten oder zum Einschränken des Zugriffs finden Sie unter Referenz zur Verhinderung [von Datenverlust](data-loss-prevention-policies.md).
  
Wenn Sie diese Optionen später ändern möchten, können Sie die Standardmäßige DLP-Richtlinie jederzeit bearbeiten – siehe den nächsten Abschnitt.
  
![Einstellungen für widget named Further protect shared content](../media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a>Bearbeiten der Standard-DLP-Richtlinie

Diese Richtlinie heißt **Standard-DLP-Richtlinie** und wird unter Verhinderung von Datenverlust auf der **Seite Richtlinie** des Security Compliance Center  &amp; angezeigt. 
  
Diese Richtlinie ist vollständig anpassbar, genauso wie jede DLP-Richtlinie, die Sie selbst von Grund auf erstellen. Sie können die Richtlinie auch deaktivieren oder löschen, damit Ihre Benutzer keine Richtlinientipps oder E-Mail-Benachrichtigungen mehr erhalten.
  
![DLP-Richtlinie mit dem Namen Standard-DLP-Richtlinie](../media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a>Wenn das Widget nicht angezeigt wird und nicht

Das Widget  **"Weiter schützen freigegebener Inhalte"** wird im Abschnitt Empfohlen für Sie auf der **Startseite** des Security Compliance Center &amp; angezeigt. 
  
Dieses Widget wird nur angezeigt, wenn:
  
- Es gibt keine Richtlinien zur Verhinderung von Datenverlust im Security &amp; Compliance Center oder Exchange Admin Center. Dieses Widget soll Ihnen bei den ersten Schritte mit DLP helfen, sodass es nicht angezeigt wird, wenn Sie bereits über DLP-Richtlinien verfügen.
    
- Inhalte, die mindestens eine Kreditkarte enthalten, wurden in den letzten 30 Tagen für personen außerhalb Ihrer Organisation freigegeben.
    
Beachten Sie, dass es bis zu 48 Stunden dauern kann, bis Regel übereinstimmungen für das Widget verfügbar sind. Wenn also vertrauliche Informationen erkannt wurden, die extern freigegeben wurden, kann es bis zu zwei Tage dauern, bis die Empfehlung angezeigt wird.
  
Nachdem Sie das Widget zum Verfeinern der Standard-DLP-Richtlinie verwendet haben, wird das Widget von der **Startseite** ausgeblendet. 
  

