---
title: Erste Schritte mit dem Angriffssimulationstraining
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Administratoren erfahren, wie Sie mithilfe von Attack Simulationsschulungen simulierte Phishing- und Kennwortangriffe in ihren organisationen Microsoft 365 E5 oder Microsoft Defender for Office 365 Plan 2 ausführen können.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a5986bbeebd49223ebfd74773346f27fc5297243
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730908"
---
# <a name="get-started-using-attack-simulation-training"></a>Erste Schritte mit dem Angriffssimulationstraining

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Wenn Ihre Organisation über Microsoft 365 E5 oder Microsoft Defender für Office 365 Plan 2 verfügt, der Bedrohungsuntersuchungs- und Reaktionsfunktionen [umfasst,](office-365-ti.md)können Sie attack simulation training im Microsoft Security Center verwenden, um realistische Angriffsszenarien in Ihrer Organisation durchzuführen. Diese simulierten Angriffe können Ihnen helfen, anfällige Benutzer zu identifizieren und zu finden, bevor sich ein tatsächlicher Angriff auf Ihr Endergebnis aus wirkt. Weitere Informationen finden Sie in diesem Artikel.

> [!NOTE]
> Das Training zur Angriffssimulation ersetzt die alte Angriffssimulator v1-Erfahrung, die unter [Attack Simulator in Microsoft Defender for Office 365.](attack-simulator.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Um das Microsoft Security Center zu öffnen, wechseln Sie zu <https://security.microsoft.com/> . Schulung zur Angriffssimulation finden Sie unter **E-Mail und Zusammenarbeit** \> **Attack simulation training**. Öffnen Sie , um direkt zu Attack simulation training zu <https://security.microsoft.com/attacksimulator> wechseln.

- Weitere Informationen zur Verfügbarkeit von Attack Simulationsschulungen in verschiedenen Microsoft 365 finden Sie unter [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

- Sie müssen im Security & Compliance Center oder in Azure Active Directory berechtigungen zugewiesen werden, bevor Sie die Verfahren in diesem Artikel tun können. Insbesondere müssen Sie Mitglied der Organisationsverwaltung, des Sicherheitsadministrators oder einer der folgenden Rollen sein:  
  - **Attack Simulator Administrators**: Erstellen und Verwalten aller Aspekte von Angriffssimulationskampagnen.
  - **Attack Simulator Payload Authors**: Erstellen von Angriffsnutzlasten, die ein Administrator später initiieren kann.

  Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) oder Informationen zu [Administratorrollen](../../admin/add-users/about-admin-roles.md).

- Es gibt keine entsprechenden PowerShell-Cmdlets für attack simulation training.

- Angriffssimulations- und Schulungsdaten werden zusammen mit anderen Kundendaten für Microsoft 365 gespeichert. Weitere Informationen finden Sie [unter Microsoft 365 Speicherorte](../../enterprise/o365-data-locations.md). Die Angriffssimulation ist in den folgenden Regionen verfügbar: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN und KOR.

- Ab dem 15. Juni 2021 ist das Training zur Angriffssimulation in GCC. Wenn Ihre Organisation über Office 365 G5 GCC oder Microsoft Defender für Office 365 (Plan 2) für Die Regierung verfügt, können Sie das Training zur Angriffssimulation im Microsoft Security Center verwenden, um realistische Angriffsszenarien in Ihrer Organisation wie in diesem Artikel beschrieben durchzuführen. Das Training zur Angriffssimulation ist in GCC oder DoD-Umgebungen noch nicht verfügbar.

> [!NOTE]
> Das Training zur Angriffssimulation bietet E3-Kunden eine Teilmenge der Funktionen als Testversion. Das Testangebot enthält die Möglichkeit, eine Nutzlast für die Verwendung von Credential Harvest zu verwenden, und die Möglichkeit, "ISA Phishing" oder "Massenmarktphishing" auszuwählen. Keine anderen Funktionen sind Teil des E3-Testangebots.

## <a name="simulations"></a>Simulationen

*Phishing* ist ein allgemeiner Begriff für E-Mail-Angriffe, die versuchen, vertrauliche Informationen in Nachrichten zu stehlen, die von legitimen oder vertrauenswürdigen Absendern zu sein scheinen. *Phishing* ist Teil einer Teilmenge von Techniken, die wir als _Social Engineering klassifizieren._

In Attack simulation training, multiple types of social engineering techniques are available:

- **Anmeldeinformationen:** Ein Angreifer sendet dem Empfänger eine Nachricht, die eine URL enthält. Wenn der Empfänger auf die URL klickt, wird er zu einer Website weitergeleitet, die in der Regel ein Dialogfeld zeigt, in dem der Benutzer nach benutzername und Kennwort gefragt wird. In der Regel ist die Zielseite so geordnet, dass sie eine bekannte Website repräsentiert, um vertrauen zu können.

- **Anlage für** Schadsoftware: Ein Angreifer sendet dem Empfänger eine Nachricht, die eine Anlage enthält. Wenn der Empfänger die Anlage öffnet, wird beliebiger Code (z. B. ein Makro) auf dem Gerät des Benutzers ausgeführt, um dem Angreifer zu helfen, zusätzlichen Code zu installieren oder sich weiter zu verfestigen.

- **Link in attachment**: Dies ist eine Hybridlösung einer Anmeldeinformationsernte. Ein Angreifer sendet dem Empfänger eine Nachricht, die eine URL innerhalb einer Anlage enthält. Wenn der Empfänger die Anlage öffnet und auf die URL klickt, wird er zu einer Website weitergeleitet, die in der Regel ein Dialogfeld zeigt, in dem der Benutzer nach benutzername und Kennwort gefragt wird. In der Regel ist die Zielseite so geordnet, dass sie eine bekannte Website repräsentiert, um vertrauen zu können.

- **Link zu Schadsoftware:** Ein Angreifer sendet dem Empfänger eine Nachricht, die einen Link zu einer Anlage auf einer bekannten Dateifreigabewebsite enthält (z. B. SharePoint Online oder Dropbox). Wenn der Empfänger auf die URL klickt, wird die Anlage geöffnet, und beliebiger Code (z. B. ein Makro) wird auf dem Gerät des Benutzers ausgeführt, um dem Angreifer zu helfen, zusätzlichen Code zu installieren oder sich weiter zu verfestigen.

- **Drive-by-url:** Ein Angreifer sendet dem Empfänger eine Nachricht, die eine URL enthält. Wenn der Empfänger auf die URL klickt, wird er zu einer Website weitergeleitet, auf der versucht wird, Hintergrundcode zu ausführen. Dieser Hintergrundcode versucht, Informationen über den Empfänger zu sammeln oder beliebigen Code auf dem Gerät zu bereitstellen. In der Regel ist die Zielwebsite eine bekannte Website, die gefährdet wurde, oder ein Klon einer bekannten Website. Die Vertrautheit mit der Website trägt dazu bei, den Benutzer davon zu überzeugen, dass der Link sicher geklickt werden kann. Diese Technik wird auch als _Wasserungsöffnungsangriff bezeichnet._

> [!NOTE]
> Überprüfen Sie die Verfügbarkeit der simulierten Phishing-URL in Ihren unterstützten Webbrowsern, bevor Sie die URL in einer Phishingkampagne verwenden. Wir arbeiten zwar mit vielen ANBIETERN für die URL-Reputation zusammen, um diese Simulations-URLs immer zu erlauben, aber wir verfügen nicht immer über vollständige Abdeckung (z. B. Google Safe Browsing). Die meisten Anbieter bieten Anleitungen, mit denen Sie bestimmte URLs (z. B. ) immer zulassen <https://support.google.com/chrome/a/answer/7532419> können.

Die URLs, die von attack simulation training verwendet werden, werden in der folgenden Liste beschrieben:

- <https://www.mcsharepoint.com>
- <https://www.attemplate.com>
- <https://www.doctricant.com>
- <https://www.mesharepoint.com>
- <https://www.officence.com>
- <https://www.officenced.com>
- <https://www.officences.com>
- <https://www.officentry.com>
- <https://www.officested.com>
- <https://www.prizegives.com>
- <https://www.prizemons.com>
- <https://www.prizewel.com>
- <https://www.prizewings.com>
- <https://www.shareholds.com>
- <https://www.sharepointen.com>
- <https://www.sharepointin.com>
- <https://www.sharepointle.com>
- <https://www.sharesbyte.com>
- <https://www.sharession.com>
- <https://www.sharestion.com>
- <https://www.templateau.com>
- <https://www.templatent.com>
- <https://www.templatern.com>
- <https://www.windocyte.com>

### <a name="create-a-simulation"></a>Erstellen einer Simulation

Schrittweise Anweisungen zum Erstellen und Senden einer neuen Simulation finden Sie unter [Simulate a phishing attack](attack-simulation-training.md).

### <a name="create-a-payload"></a>Erstellen einer Nutzlast

Schrittweise Anweisungen zum Erstellen einer Nutzlast für die Verwendung in einer Simulation finden Sie unter [Create a custom payload for Attack simulation training](attack-simulation-training-payloads.md).

### <a name="gaining-insights"></a>Gewinnen von Einblicken

Schrittweise Anweisungen zum Gewinnen von Einblicken in die Berichterstellung finden Sie unter [Gain insights through Attack simulation training](attack-simulation-training-insights.md).

> [!NOTE]
> Der **Angriffssimulator** verwendet sichere Links in Defender für Office 365 zum sicheren Nachverfolgen von Klickdaten für die URL in der Nutzlastnachricht, die an Zielempfänger einer Phishingkampagne gesendet wird, auch wenn die Einstellung Benutzerklicks nicht nachverfolgen in Richtlinien für sichere Links aktiviert ist.
