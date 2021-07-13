---
title: Erste Schritte mit der DLP-Standardrichtlinie
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
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie den Bericht verwenden, um die Standardrichtlinie zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) Ihrer Organisation zu verfeinern.
ms.openlocfilehash: 98f2a95d66860695034fa958969d1c195e9d58be
ms.sourcegitcommit: 8c698d1a0c41baf5f35d07b0d765b4a5ead593d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2021
ms.locfileid: "53408960"
---
# <a name="get-started-with-the-default-dlp-policy"></a>Erste Schritte mit der DLP-Standardrichtlinie

Bevor Sie sogar Ihre erste Richtlinie zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) erstellen, trägt DLP dazu bei, Ihre vertraulichen Informationen mit einer Standardrichtlinie zu schützen. Diese Standardrichtlinie und ihre Empfehlung (siehe unten) tragen dazu bei, Ihre vertraulichen Inhalte zu schützen, indem Sie benachrichtigt werden, wenn E-Mails oder Dokumente mit einer Kreditkartennummer für jemanden außerhalb Ihrer Organisation freigegeben wurden. Diese Empfehlung wird auf der **Startseite** des Security &amp; Compliance Centers angezeigt. 
  
Sie können dieses Widget verwenden, um schnell anzuzeigen, wann und wie viele vertrauliche Informationen freigegeben wurden, und dann die Standard-DLP-Richtlinie in nur ein oder zwei Klicks zu verfeinern. Sie können die DLP-Standardrichtlinie auch jederzeit bearbeiten, da sie vollständig anpassbar ist. Wenn die Empfehlung zunächst nicht angezeigt wird, klicken Sie unten im Abschnitt **"Empfohlen für Sie"** auf **"+Mehr".** 
  
![Widget mit dem Namen "Weiter schützen freigegebene Inhalte"](../media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a>Anzeigen des Berichts und Verfeinern der DLP-Standardrichtlinie

Wenn das Widget anzeigt, dass Benutzer vertrauliche Informationen für Personen außerhalb Ihrer Organisation freigegeben haben, wählen Sie unten die **DLP-Richtlinie verfeinern.** 
  
Der detaillierte Bericht zeigt Ihnen, wann und wie viele Inhalte mit Kreditkartennummern in den letzten 30 Tagen freigegeben wurden. Beachten Sie, dass es bis zu 48 Stunden dauern kann, bis Regelüberstimmungen im Widget angezeigt werden.
  
Um die vertraulichen Informationen zu schützen, gilt die standardmäßige DLP-Richtlinie:
  
- Erkennt, wenn Inhalte in Exchange, SharePoint und OneDrive, die mindestens eine Kreditkartennummer enthalten, für Personen außerhalb Ihrer Organisation freigegeben werden.
    
- Zeigt einen Richtlinientipp und sendet eine E-Mail-Benachrichtigung an Benutzer, wenn sie versuchen, diese vertraulichen Informationen für Personen außerhalb Ihrer Organisation freizugeben. Weitere Informationen zu diesen Optionen finden Sie unter [Senden von E-Mail-Benachrichtigungen und Anzeigen von Richtlinientipps für DLP-Richtlinien.](use-notifications-and-policy-tips.md)
    
- Generiert detaillierte Aktivitätsberichte, damit Sie Dinge nachverfolgen können, z. B. wer die Inhalte für Personen außerhalb Ihrer Organisation freigegeben hat und wann sie dies getan haben. Sie können die [DLP-Berichte](view-the-dlp-reports.md) und [Überwachungsprotokolldaten](search-the-audit-log-in-security-and-compliance.md) (d. h. Aktivitäts-DLP)   =  verwenden, um diese Informationen anzuzeigen.
    
Um die Standardmäßige DLP-Richtlinie schnell zu verfeinern, können Sie sie verwenden:
  
- Senden Sie Eine Vorfallbericht-E-Mail, wenn Benutzer diese vertraulichen Informationen für Personen außerhalb Ihrer Organisation freigeben.
    
- Fügen Sie dem E-Mail-Vorfallbericht weitere Benutzer hinzu.
    
- Blockieren Sie den Zugriff auf den Inhalt, der die vertraulichen Informationen enthält, aber ermöglichen Sie es dem Benutzer, diese außer Kraft zu setzen und freizugeben oder zu senden, wenn dies erforderlich ist.
    
Weitere Informationen zu Vorfallberichten oder zum Einschränken des Zugriffs finden Sie in der [Referenz zur Verhinderung von Datenverlust.](data-loss-prevention-policies.md)
  
Wenn Sie diese Optionen später ändern möchten, können Sie die Standard-DLP-Richtlinie jederzeit bearbeiten . Weitere Informationen finden Sie im nächsten Abschnitt.
  
![Einstellungen für das Widget mit dem Namen "Freigegebene Inhalte weiter schützen"](../media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a>Bearbeiten der Standard-DLP-Richtlinie

Diese Richtlinie heißt **"Standard-DLP-Richtlinie"** und wird auf der Seite **"Richtlinie"** des Security Compliance Centers unter "Verhinderung von **Datenverlust"** &amp; angezeigt. 
  
Diese Richtlinie kann vollständig angepasst werden, genauso wie jede DLP-Richtlinie, die Sie selbst von Grund auf erstellen. Sie können die Richtlinie auch deaktivieren oder löschen, damit Ihre Benutzer keine Richtlinientipps oder E-Mail-Benachrichtigungen mehr erhalten.
  
![DLP-Richtlinie mit dem Namen "Standard-DLP-Richtlinie"](../media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a>Wann das Widget angezeigt wird

Das Widget mit dem Namen **"Freigegebene Inhalte weiter schützen"** wird im Abschnitt **"Empfohlen für Sie"** auf der **Startseite** des Security &amp; Compliance Centers angezeigt. 
  
Dieses Widget wird nur angezeigt, wenn:
  
- Es gibt keine Richtlinien zur Verhinderung von Datenverlust im Security &amp; Compliance Center oder Exchange Admin Center. Dieses Widget soll Ihnen bei den ersten Schritten mit DLP helfen, sodass es nicht angezeigt wird, wenn Sie bereits über DLP-Richtlinien verfügen.
    
- Inhalte, die mindestens eine Kreditkarte enthalten, wurden in den letzten 30 Tagen für Personen außerhalb Ihrer Organisation freigegeben.
    
Beachten Sie, dass es bis zu 48 Stunden dauern kann, bis Regelüberstimmungen für das Widget verfügbar sind. Nach dem Erkennen extern freigegebener vertraulicher Informationen kann es also bis zu zwei Tage dauern, bis die Empfehlung angezeigt wird.
  
Nachdem Sie das Widget zum Verfeinern der standardmäßigen DLP-Richtlinie verwendet haben, wird das Widget auf der **Startseite** ausgeblendet. 
  

