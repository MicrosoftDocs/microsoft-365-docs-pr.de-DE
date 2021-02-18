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
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie mithilfe des Angriffssimulationstrainings simulierte Phishing- und Kennwortangriffe in ihren Microsoft 365 E5- oder Microsoft Defender für Office 365 Plan 2-Organisationen ausführen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1ec5b8175db6eb03e59a31a4dc21d9649c5e7616
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289894"
---
# <a name="get-started-using-attack-simulation-training"></a>Erste Schritte mit dem Angriffssimulationstraining

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Wenn Ihre Organisation über Microsoft 365 E5 oder Microsoft Defender für Office 365 Plan 2 verfügt, der Funktionen zur Untersuchung und Reaktion auf Bedrohungen [umfasst,](office-365-ti.md)können Sie die Angriffssimulationsschulung im Microsoft Security Center verwenden, um realistische Angriffsszenarien in Ihrer Organisation durchzuführen. Diese simulierten Angriffe können Ihnen helfen, anfällige Benutzer zu identifizieren und zu finden, bevor sich ein tatsächlicher Angriff auf Ihr Endergebnis ausdingt. Lesen Sie diesen Artikel, um mehr zu erfahren.

> [!NOTE]
> Das Training zur Angriffssimulation ersetzt die alte Angriffssimulator v1-Erfahrung, die im Angriffssimulator [in Microsoft Defender für Office 365 beschrieben wird.](attack-simulator.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Um das Microsoft Security Center zu öffnen, wechseln Sie zu <https://security.microsoft.com/> . Das Training zur Angriffssimulation ist im **E-Mail- und Zusammenarbeitstraining** \> **zur Angriffssimulation verfügbar.** Öffnen Sie das , um direkt zum Training zur Angriffssimulation zu <https://security.microsoft.com/attacksimulator> wechseln.

- Weitere Informationen zur Verfügbarkeit von Attack Simulation Training in verschiedenen Microsoft 365-Abonnements finden Sie in [der Microsoft Defender für Office 365-Dienstbeschreibung.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

- Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen im Security & Compliance Center oder in Azure Active Directory Berechtigungen zugewiesen werden. Insbesondere müssen Sie Mitglied der Organisationsverwaltung, des Sicherheitsadministrators oder einer der folgenden Rollen sein:  
  - **Administratoren des Angriffssimulators:** Erstellen und Verwalten aller Aspekte von Angriffssimulationskampagnen.
  - **Autoren der Angriffssimulatornutzlast:** Erstellen Sie Angriffsnutzlasten, die ein Administrator später initiieren kann.

  Weitere Informationen finden Sie unter ["Berechtigungen" im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) oder zu [Administratorrollen.](../../admin/add-users/about-admin-roles.md)

- Es gibt keine entsprechenden PowerShell-Cmdlets für das Training zur Angriffssimulation.

- Daten zu Angriffssimulation und Schulung werden mit anderen Kundendaten für Microsoft 365-Dienste gespeichert. Weitere Informationen finden Sie unter [Microsoft 365-Datenspeicherorte.](/microsoft-365/enterprise/o365-data-locations) Die Angriffssimulation ist derzeit nicht in den folgenden Regionen verfügbar: SGP, NOR, UAE, ZAF, GER, BRA und CHE.

## <a name="simulations"></a>Simulationen

*Phishing* ist ein allgemeiner Begriff für E-Mail-Angriffe, die versuchen, vertrauliche Informationen in Nachrichten zu stehlen, die von legitimen oder vertrauenswürdigen Absendern zu sein scheinen. *Phishing* ist Teil einer Teilmenge von Techniken, die wir als _Social Engineering klassifizieren._

Im Training zur Angriffssimulation sind mehrere Arten von Social -Engineering-Techniken verfügbar:

- **Datenergreifung** mit Anmeldeinformationen: Ein Angreifer sendet dem Empfänger eine Nachricht, die eine URL enthält. Wenn der Empfänger auf die URL klickt, wird er zu einer Website weitergeleitet, in der normalerweise ein Dialogfeld angezeigt wird, in dem der Benutzer nach benutzername und Kennwort gefragt wird. In der Regel ist die Zielseite so umdeutend, dass sie eine bekannte Website repräsentiert, um eine Vertrauensstellung für den Benutzer zu schaffen.

- **Schadsoftwareanlage:** Ein Angreifer sendet dem Empfänger eine Nachricht, die eine Anlage enthält. Wenn der Empfänger die Anlage öffnet, wird beliebiger Code (z. B. ein Makro) auf dem Gerät des Benutzers ausgeführt, um dem Angreifer zu helfen, zusätzlichen Code zu installieren oder sich weiter zu verfestigen.

- **Link in Anlage:** Dies ist eine Hybridbereitstellung einer Anmeldeinformationsernte. Ein Angreifer sendet dem Empfänger eine Nachricht, die eine URL innerhalb einer Anlage enthält. Wenn der Empfänger die Anlage öffnet und auf die URL klickt, wird er zu einer Website weitergeleitet, in der normalerweise ein Dialogfeld angezeigt wird, in dem der Benutzer nach benutzername und Kennwort gefragt wird. In der Regel ist die Zielseite so umdeutend, dass sie eine bekannte Website repräsentiert, um eine Vertrauensstellung für den Benutzer zu schaffen.

- **Link zu Schadsoftware:** Ein Angreifer sendet dem Empfänger eine Nachricht, die einen Link zu einer Anlage auf einer bekannten Dateifreigabewebsite enthält (z. B. SharePoint Online oder Dropbox). Wenn der Empfänger auf die URL klickt, wird die Anlage geöffnet, und auf dem Gerät des Benutzers wird beliebiger Code (z. B. ein Makro) ausgeführt, damit der Angreifer zusätzlichen Code installieren oder sich weiter verfestigen kann.

- **Laufwerk-nach-URL:** Ein Angreifer sendet dem Empfänger eine Nachricht, die eine URL enthält. Wenn der Empfänger auf die URL klickt, wird er zu einer Website weitergeleitet, die versucht, Hintergrundcode ausführen. Dieser Hintergrundcode versucht, Informationen über den Empfänger zu sammeln oder beliebigen Code auf dem Gerät zu bereitstellen. In der Regel ist die Zielwebsite eine bekannte Website, die gefährdet wurde, oder ein Klon einer bekannten Website. Die Vertrautheit mit der Website trägt dazu bei, den Benutzer davon zu überzeugen, dass der Link sicher angeklickt werden kann. Diese Technik wird auch als _Grubenangriff bezeichnet._

> [!NOTE]
> Überprüfen Sie die Verfügbarkeit der simulierten Phishing-URL in Ihren unterstützten Webbrowsern, bevor Sie die URL in einer Phishingkampagne verwenden. Während wir mit vielen Anbietern von URL-Reputation zusammenarbeiten, um diese Simulations-URLs immer zu erlauben, verfügen wir nicht immer über vollständige Abdeckung (z. B. Google Safe Browsing). Die meisten Anbieter bieten Anleitungen, mit denen Sie immer bestimmte URLs zulassen können (z. B. <https://support.google.com/chrome/a/answer/7532419> ).

Die URLs, die von der Attack Simulation Training verwendet werden, werden in der folgenden Liste beschrieben:

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

Schritt-für-Schritt-Anleitungen zum Erstellen und Senden einer neuen Simulation finden Sie unter [Simulieren eines Phishingangriffs.](attack-simulation-training.md)

### <a name="create-a-payload"></a>Erstellen einer Nutzlast

Schrittweise Anweisungen zum Erstellen einer Nutzlast für die Verwendung innerhalb einer Simulation finden Sie unter Erstellen einer benutzerdefinierten Nutzlast für [attack simulation training](attack-simulation-training-payloads.md).

### <a name="gaining-insights"></a>Gewinnen von Einblicken

Schritt-für-Schritt-Anleitungen zum Gewinnen von Einblicken in die Berichterstellung finden Sie unter ["Einblicke durch Attack Simulation Training".](attack-simulation-training-insights.md)
