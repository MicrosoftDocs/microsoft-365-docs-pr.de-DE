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
description: Erfahren Sie, wie Sie den Bericht verwenden, um die standardmäßige DLP-Richtlinie (Data Loss Prevention) Ihrer Organisation zu verfeinern.
ms.openlocfilehash: 7c8f0460f9cd02ee3d26197965f5ea74737ac833
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817614"
---
# <a name="get-started-with-the-default-dlp-policy"></a>Erste Schritte mit der DLP-Standardrichtlinie

Bevor Sie sogar Ihre erste DLP-Richtlinie (Data Loss Prevention, Verhinderung von Datenverlust) erstellen, hilft DLP, Ihre vertraulichen Informationen mit einer Standardrichtlinie zu schützen. Diese Standardrichtlinie und ihre Empfehlung (unten abgebildet) helfen Ihnen, Ihre vertraulichen Inhalte zu schützen, indem Sie darüber informiert werden, dass e-Mails oder Dokumente, die eine Kreditkartennummer enthalten, für eine Person außerhalb Ihrer Organisation freigegeben wurden. Diese Empfehlung wird auf der **Start** Seite des Security &amp; Compliance Centers angezeigt. 
  
Sie können dieses Widget verwenden, um schnell anzuzeigen, wann und wie viel vertrauliche Informationen freigegeben wurden, und dann die standardmäßige DLP-Richtlinie in nur einem Mausklick oder zwei zu verfeinern. Sie können auch die standardmäßige DLP-Richtlinie jederzeit bearbeiten, da Sie vollständig anpassbar ist. Wenn die Empfehlung zunächst nicht angezeigt wird, klicken Sie im unteren Bereich des Abschnitts **empfohlen für Sie** auf **+ mehr** . 
  
![Widget mit dem Namen weiter freigegebene Inhalte schützen](../media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a>Anzeigen des Berichts und verfeinern der standardmäßigen DLP-Richtlinie

Wenn das Widget zeigt, dass Benutzer vertrauliche Informationen für Personen außerhalb Ihrer Organisation freigegeben haben, wählen Sie unten die Option **DLP-Richtlinie verfeinern** aus. 
  
Der ausführliche Bericht zeigt Ihnen an, wann und wie viel Inhalt in den letzten 30 Tagen freigegeben wurde, der Kreditkartennummern enthält. Beachten Sie, dass Regel Übereinstimmungen bis zu 48 Stunden in Anspruch nehmen können, um im Widget angezeigt zu werden.
  
Zum Schutz der vertraulichen Informationen wird die standardmäßige DLP-Richtlinie verwendet:
  
- Erkennt, wenn Inhalte in Exchange, SharePoint und OneDrive, die mindestens eine Kreditkartennummer enthalten, für Personen außerhalb Ihrer Organisation freigegeben werden.
    
- Zeigt einen richtlinientipp an und sendet eine e-Mail-Benachrichtigung an Benutzer, wenn Sie versuchen, diese vertraulichen Informationen für Personen außerhalb Ihrer Organisation freizugeben. Weitere Informationen zu diesen Optionen finden Sie unter [Senden von e-Mail-Benachrichtigungen und Anzeigen von Richtlinien Tipps für DLP-Richtlinien](use-notifications-and-policy-tips.md).
    
- Generiert detaillierte Aktivitätsberichte, sodass Sie nachverfolgen können, wie wer die Inhalte für Personen außerhalb Ihrer Organisation freigegeben hat. Sie können die [DLP-Berichte](view-the-dlp-reports.md) und [Überwachungsprotokolldaten](search-the-audit-log-in-security-and-compliance.md) (Where **Activity**  =  **DLP**) verwenden, um diese Informationen anzuzeigen.
    
Um die standardmäßige DLP-Richtlinie schnell zu verfeinern, können Sie Folgendes festlegen:
  
- Senden Sie eine Vorfall Berichts-e-Mail, wenn Benutzer diese vertraulichen Informationen für Personen außerhalb Ihrer Organisation freigeben.
    
- Fügen Sie dem e-Mail-Vorfall Bericht weitere Benutzer hinzu.
    
- Blockieren Sie den Zugriff auf die Inhalte, die vertrauliche Informationen enthalten, aber lassen Sie den Benutzer das außer Kraft setzen und freigeben oder senden, wenn dies erforderlich ist.
    
Weitere Informationen zu Vorfall Berichten oder zum Einschränken des Zugriffs finden Sie unter [Übersicht über Richtlinien zur Verhinderung von Datenverlust](data-loss-prevention-policies.md).
  
Wenn Sie diese Optionen zu einem späteren Zeitpunkt ändern möchten, können Sie die standardmäßige DLP-Richtlinie jederzeit bearbeiten – siehe den nächsten Abschnitt.
  
![Einstellungen für Widget "weiter zum Schutz von freigegebenen Inhalten"](../media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a>Bearbeiten der standardmäßigen DLP-Richtlinie

Diese Richtlinie wird als **standardmäßige DLP-Richtlinie** bezeichnet und wird auf der Seite **Richtlinie** des Security Compliance Center unter **Verhinderung von Datenverlust** angezeigt &amp; . 
  
Diese Richtlinie ist vollständig anpassbar, genauso wie jede DLP-Richtlinie, die Sie selbst von Grund auf neu erstellen. Sie können die Richtlinie auch deaktivieren oder löschen, sodass Ihre Benutzer keine Richtlinien Tipps oder e-Mail-Benachrichtigungen mehr erhalten.
  
![DLP-Richtlinie mit dem Namen Standard-DLP-Richtlinie](../media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a>Wenn das Widget funktioniert und nicht angezeigt wird

Das Widget **weiterer Schutz für freigegebene Inhalte** wird im Abschnitt **empfohlen für Sie** der **Start** Seite des Security &amp; Compliance Center angezeigt. 
  
Dieses Widget wird nur angezeigt, wenn:
  
- Es gibt keine Richtlinien zur Verhinderung von Datenverlust im Security &amp; Compliance Center oder im Exchange Admin Center. Dieses Widget unterstützt Sie bei der ersten Schritte mit DLP, sodass es nicht angezeigt wird, wenn Sie bereits über DLP-Richtlinien verfügen.
    
- Inhalte, die mindestens eine Kreditkarte enthalten, wurden in den letzten 30 Tagen für eine Person außerhalb Ihrer Organisation freigegeben.
    
Beachten Sie, dass Regel Übereinstimmungen bis zu 48 Stunden für das Widget verfügbar sein können, sodass nach dem erkennen vertraulicher Informationen, die extern freigegeben wurden, es bis zu zwei Tage dauern kann, bis die Empfehlung angezeigt wird.
  
Nachdem Sie das Widget zum Verfeinern der standardmäßigen DLP-Richtlinie verwendet haben, wird das Widget nicht mehr auf der **Start** Seite angezeigt. 
  

