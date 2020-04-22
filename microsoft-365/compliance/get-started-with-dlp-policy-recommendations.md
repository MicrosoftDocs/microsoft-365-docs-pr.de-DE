---
title: Empfohlene erste Schritte mit DLP-Richtlinienvorlagen
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 8/7/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
description: Diese Erkenntnis gesteuerte Empfehlung hilft Ihrer Organisation, vertrauliche Inhalte zu schützen, wenn Sie in Microsoft 365 gespeichert und freigegeben wird, indem Sie darüber informiert werden, wenn eine mögliche Lücke in ihrer DLP-Richtlinien Abdeckung besteht. Diese Empfehlung wird auf der Startseite des Security &amp; Compliance Centers angezeigt, wenn Ihre Dokumente eine der fünf häufigsten Arten von vertraulichen Informationen enthalten, die jedoch nicht durch eine DLP-Richtlinie geschützt sind.
ms.openlocfilehash: 73c45c477942533d5668c225144950a0fde4279b
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632466"
---
# <a name="get-started-with-dlp-policy-recommendations"></a>Empfohlene erste Schritte mit DLP-Richtlinienvorlagen

Diese Erkenntnis gesteuerte Empfehlung hilft Ihrer Organisation, vertrauliche Inhalte zu schützen, wenn Sie in Microsoft 365 gespeichert und freigegeben wird, indem Sie darüber informiert werden, wenn eine mögliche Lücke in ihrer DLP-Richtlinien Abdeckung besteht. Diese Empfehlung wird auf der **Start** Seite des Security &amp; Compliance Centers angezeigt, wenn Ihre Dokumente eine der fünf häufigsten Arten von vertraulichen Informationen enthalten, die jedoch nicht durch eine Richtlinie zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) geschützt sind. 
  
Sie können dieses Widget verwenden, um schnell eine angepasste DLP-Richtlinie mit nur einem Mausklick oder zwei zu erstellen, und nachdem Sie diese DLP-Richtlinie erstellt haben, ist sie vollständig anpassbar. Wenn die Empfehlung zunächst nicht angezeigt wird, klicken Sie im unteren Bereich des Abschnitts **empfohlen für Sie** auf **+ mehr** . 
  
![Widget mit dem Namen "ungeschützte vertrauliche Informationen"](../media/91bc04d2-6eff-4294-8b73-b2d56d26ffc4.png)
  
## <a name="create-the-recommended-dlp-policy"></a>Erstellen der empfohlenen DLP-Richtlinie

Wenn das Widget Ihnen ungeschützte vertrauliche Informationen zeigt, wählen Sie am unteren Rand **Erste Schritte** aus, um schnell eine DLP-Richtlinie zu erstellen. 
  
Zum Schutz der vertraulichen Informationen wird diese DLP-Richtlinie wie folgt unterstützt:
  
- Erkennt, wenn Inhalte in Exchange, SharePoint und OneDrive, die einen der ungeschützten Typen vertraulicher Informationen enthalten, für Personen außerhalb Ihrer Organisation freigegeben werden.
    
- Generiert detaillierte Aktivitätsberichte, sodass Sie nachverfolgen können, wie wer die Inhalte für Personen außerhalb Ihrer Organisation freigegeben hat. Sie können die [DLP-Berichte](view-the-dlp-reports.md) und [Überwachungsprotokolldaten](search-the-audit-log-in-security-and-compliance.md) (Where **Activity** = **DLP**) verwenden, um diese Informationen anzuzeigen.
    
Sie können auch die DLP-Richtlinie festlegen:
  
- Senden Sie eine Vorfall Berichts-e-Mail, wenn Benutzer viele dieser vertraulichen Informationen für Personen außerhalb Ihrer Organisation freigeben.
    
- Fügen Sie dem e-Mail-Vorfall Bericht weitere Benutzer hinzu.
    
- Zeigen Sie einen richtlinientipp an, und senden Sie eine e-Mail-Benachrichtigung an Benutzer, wenn Sie versuchen, diese vertraulichen Informationen für Personen außerhalb Ihrer Organisation freizugeben. Weitere Informationen zu diesen Optionen finden Sie unter [Senden von e-Mail-Benachrichtigungen und Anzeigen von Richtlinien Tipps für DLP-Richtlinien](use-notifications-and-policy-tips.md).
    
Wenn Sie diese Optionen später ändern möchten, können Sie die DLP-Richtlinie nach ihrer Erstellung bearbeiten. Beispielsweise können Sie die Richtlinie restriktiver machen, indem Sie auch Personen daran hindern, Inhalte freizugeben, die vertrauliche Informationen an erster Stelle enthalten-siehe den nächsten Abschnitt.
  
![Einstellungen für das Widget mit dem Namen ungeschützte vertrauliche Informationen](../media/b6106cbd-1bed-4582-aaef-b678de470c9b.png)
  
## <a name="edit-the-recommended-dlp-policy"></a>Bearbeiten der empfohlenen DLP-Richtlinie

Nachdem Sie das Widget zum Erstellen einer DLP-Richtlinie verwendet haben, wird die Richtlinie unter **Verhinderung von Datenverlust** auf der Seite **Richtlinie** des Security &amp; Compliance Centers angezeigt. 
  
Standardmäßig wird die Richtlinie **als System empfohlene Richtlinie für die Freigabe vertraulicher Informationen**bezeichnet. Diese Richtlinie ist vollständig anpassbar, genauso wie jede DLP-Richtlinie, die Sie selbst von Grund auf neu erstellen. Wenn Sie beispielsweise entschieden haben, bei der Verwendung des Widgets keine vorfallberichte und Richtlinien Tipps zu aktivieren, können Sie die Richtlinie jederzeit bearbeiten und diese Optionen jederzeit aktivieren.
  
![Vom System empfohlene Richtlinie für die Freigabe vertraulicher Informationen](../media/2fc49f25-ec25-4433-add4-d60f73888f13.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a>Wenn das Widget funktioniert und nicht angezeigt wird

Das Widget namens **ungeschützte vertrauliche Informationen** wird im Abschnitt **empfohlen für Sie** der **Start** Seite des Security &amp; Compliance Center angezeigt. 
  
Dieses Widget wird nur angezeigt, wenn:
  
- Neue Dokumente, die eine der fünf häufigsten Arten von vertraulichen Informationen enthalten, werden in SharePoint oder OneDrive in den letzten 30 Tagen erkannt.
    
- Diese vertraulichen Informationen sind nicht bereits durch eine vorhandene DLP-Richtlinie geschützt.
    
Im Gegensatz zu DLP-Richtlinien, die Ihre Daten ständig überprüfen, überprüft diese Empfehlung nach Lücken in ihrer DLP-Richtlinien Abdeckung etwa alle 48 Stunden, sodass nach dem Hochladen neuer Inhalte bis zu zwei Tage dauern kann, bis die Empfehlung angezeigt wird.
  
Nachdem Sie das Widget zum Erstellen einer empfohlenen DLP-Richtlinie verwendet haben, wird das Widget nicht mehr auf der **Start** Seite angezeigt. 
  

