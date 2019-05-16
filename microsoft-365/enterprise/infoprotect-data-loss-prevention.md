---
title: 'Schritt 5: Konfigurieren von Office 365 Data Loss Prevention'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen und Bereitstellen von Office 365 Data Loss Prevention in Microsoft 365.
ms.openlocfilehash: f6b9291a2965552837f989c98b32674f6093b383
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073558"
---
# <a name="step-5-configure-office-365-data-loss-prevention"></a>Schritt 5: Konfigurieren von Office 365 Data Loss Prevention

*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Mithilfe von Data Loss Prevention-Richtlinien (DLP) im Office 365 Security & Compliance Center können Sie vertrauliche Informationen in Microsoft 365 identifizieren, überwachen und automatisch schützen. Mit DLP-Richtlinien können Sie folgende Aktionen ausführen:

- Identifizieren vertraulicher Informationen an vielen Orten, zum Beispiel Exchange Online, SharePoint Online, OneDrive for Business und Microsoft Teams.
- Verhindern der versehentlichen Freigabe von vertraulichen Informationen durch das Sperren des Zugriffs auf ein Dokument oder durch das Blockieren der E-Mail, die es enthält.
- Überwachen und Schützen von vertraulichen Informationen in den Desktopversionen von Excel, PowerPoint und Word.
- Unterstützen von Benutzern mit E-Mail-Benachrichtigungen und Richtlinientipps, die erfahren, wie sie die Anforderungen erfüllen, ohne dabei ihren Arbeitsablauf unterbrechen zu müssen. 
- Anzeigen von DLP-Berichten mit Inhalten, die mit den DLP-Richtlinien Ihrer Organisation übereinstimmen.

Eine DLP-Richtlinie gibt Folgendes an:

- **Wo:** Orte, zum Beispiel Exchange Online-, SharePoint Online- und OneDrive for Business-Websites sowie Microsoft Teams-Chats und -Kanäle.
- **Wann:** Bedingungen, die der Inhalt innerhalb einer bestimmten Richtlinienregel erfüllen muss.
- **Wie:** Aktionen in dieser Abgleichsrichtlinienregel, die automatisch für die übereinstimmenden Bedingungen durchgeführt werden.

Anders ausgedrückt:

- Wenn für ein Dokument an diesem Ort (wo) der Inhalt die Kriterien einer Regel erfüllt (wenn), dann werden automatisch die Aktionen in der Regel durchgeführt (wie).

Um die Gruppe von DLP-Richtlinien zu ermitteln, die Sie benötigen, müssen Sie Ihre Dokumente und die Arten von Daten in ihnen analysieren, die vor Datenverlust geschützt werden sollen. Eine Finanzorganisation in den Vereinigten Staaten von Amerika würde beispielsweise eine DLP-Richtlinie erstellen, die verhindert, dass Dokumente mit Sozialversicherungsnummern nach außen gelangen oder per E-Mail an Orte außerhalb des Unternehmens gesendet. werden.

Als Nächstes konfigurieren und testen Sie die Richtlinien mit Testorten, um das richtige DLP-Verhalten sicherzustellen und falsch positive Ergebnisse zu minimieren.

Zum Schluss implementieren Sie sie für Ihre Organisation, indem Sie die Mitarbeiter über die neuen Richtlinien und das gewünschte Verhalten informieren und den Umfang der Orte erweitern.

Weitere Informationen erhalten Sie unter [Empfohlene erste Schritte mit DLP-Richtlinienvorlagen](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations).

Als Zwischenprüfung können Sie die [Beendigungskriterien](infoprotect-exit-criteria.md#crit-infoprotect-step5) für diesen Schritt betrachten.

## <a name="next-step"></a>Nächster Schritt


|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)|[Konfigurieren von Privileged Access Management für Office 365](infoprotect-configure-privileged-access-management.md)|


