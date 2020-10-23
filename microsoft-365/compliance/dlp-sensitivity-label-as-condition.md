---
title: Verwenden von Vertraulichkeitsbezeichnungen als Bedingungen in DLP-Richtlinien (Vorschau)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie mehr über die Dienste und Elementtypen, die Sie mit Vertraulichkeitsbezeichnungen als Bedingungen in DLP-Richtlinien verwenden können.
ms.openlocfilehash: 2f8eb30e23d722a5e8faf7d0ddaca6b9a94e279b
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649634"
---
# <a name="use-sensitivity-labels-as-conditions-in-dlp-policies-preview"></a>Verwenden von Vertraulichkeitsbezeichnungen als Bedingungen in DLP-Richtlinien (Vorschau)

Sie können [Vertraulichkeitsbezeichnungen](sensitivity-labels.md) als Bedingung in DLP-Richtlinien für folgende Speicherorte verwenden:

- Exchange Online-E-Mails
- Microsoft Office SharePoint Online
- OneDrive for Business-Websites
- Windows 10-Geräte

Vertraulichkeitsbezeichnungen werden als Option in der Liste **Inhalt enthält** angezeigt.

> [!div class="mx-imgBorder"]
> ![Vertraulichkeitsbezeichnungen als Bedingung](../media/dlp-sensitivity-label-as-a-condition.png)

> [!IMPORTANT]
> **Vertraulichkeitsbezeichnungen** als Bedingung werden nicht verfügbar sein, wenn Sie **Teams-Chat und Kanalnachrichten**als Ort für die Anwendung der DLP-Richtlinie ausgewählt haben.


## <a name="supported-items-scenarios-and-policy-tips"></a>Unterstützte Elemente, Szenarien und Richtlinientipps

Sie können Vertraulichkeitsbezeichnungen als Bedingungen für diese Elemente und in diesen Szenarien verwenden.

### <a name="supported-items"></a>unterstützte Elemente

|Dienst  |Elementtyp  |Verfügbar für Richtlinientipps  |Durchsetzbar  |
|---------|---------|---------|---------|
|Exchange    |E-Mail-Nachricht         |ja         |ja         |
|Exchange    |E-Mail-Anlage         |nein *         |nein *         |
|Microsoft Office SharePoint Online     |Elemente in Microsoft Office SharePoint Online         |ja         |ja         |
|OneDrive for Business     |Elemente         |ja         |ja         |
|Teams     |Microsoft Teams- und Kanalnachrichten         |nicht zutreffend         |nicht zutreffend         |
|Teams     |Anlagen         |ja **         |ja **         |
|Windows 10-Geräte (Vorschau)     |Elemente         |ja         |ja         |
|MCAS (Vorschau) |Elemente         |ja         |ja         |

\* DLP-Erkennung von Vertraulichkeitsbezeichnungen in E-Mails wird unterstützt. DLP-Erkennung von Vertraulichkeitsbezeichnungen in E-Mails wird nicht unterstützt.

\** Anlagen, die in Teams über einen 1:1-Chat oder über Kanäle gesendet werden, werden automatisch auf OneDrive for Business und Microsoft Office SharePoint Online hochgeladen. Wenn also Microsoft Office SharePoint Online oder OneDrive for Business als Speicherorte in ihrer DLP-Richtlinie enthalten sind, werden bezeichnete Anlagen, die in Teams gesendet wurden, automatisch in den Umfang dieser Bedingung einbezogen. Teams muss in der DLP-Richtlinie nicht als Speicherort ausgewählt werden.

### <a name="supported-scenarios"></a>Unterstützte Szenarien

- Der DLP-Administrator kann eine Liste aller Vertraulichkeitsbezeichnugen im Mandanten anzeigen, wenn er eine oder mehrere Vertraulichkeitsbezeichnungen als Bedingung einschließt.

- Die Verwendung von Vertraulichkeitsbezeichnungen als Bedingung wird in allen Workloads unterstützt, wie in der obigen Supportmatrix angegeben.

- DLP-Richtlinientipps werden weiterhin für Workloads (mit Ausnahme von Outlook Win32) angezeigt, die eine Vertraulichkeitsbezeichnung als Bedingung enthalten.

- Vertraulichkeitsbezeichnungen werden auch als Bestandteil der Schadensbericht-E-Mail angezeigt, wenn eine DLP-Richtlinie mit einer Vertraulichkeitsbezeichnung als Bedingung übereinstimmt.

- Details zur Vertraulichkeitsbezeichnung werden auch im Überwachungsprotokoll „DLP-Regelabgleich“ für eine Übereinstimmung mit einer DLP-Richtlinie angezeigt, die die Vertraulichkeitsbezeichnung als Bedingung enthält.


### <a name="support-policy-tips"></a>Support-Richtlinientipps


|Workload  |Richtlinientipps unterstützt / nicht unterstützt  |
|---------|---------|
|OWA |    unterstützt     |
|Outlook Win 32    |  nicht unterstützt       |
|Microsoft Office SharePoint Online   |   unterstützt      |
|OneDrive for Business    |    unterstützt     |
|Endpunktgeräte   |  nicht unterstützt       |
