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
description: Administratoren können erfahren, wie Sie angriffssimulationsschulungen verwenden, um simulierte Phishing- und Kennwortangriffe in ihren Microsoft 365 E5 oder Microsoft Defender für Office 365 Plan 2-Organisationen auszuführen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ad86f77399cfa2a3a780d3fed7e483e3c11bc08d
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082900"
---
# <a name="get-started-using-attack-simulation-training"></a>Erste Schritte mit dem Angriffssimulationstraining

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt** [für Microsoft Defender für Office 365 Plan 2](defender-for-office-365.md)

Wenn Ihre Organisation über Microsoft 365 E5 oder Microsoft Defender für Office 365 Plan 2 verfügt, der Funktionen für [die Untersuchung und Reaktion auf Bedrohungen](office-365-ti.md)umfasst, können Sie die Angriffssimulationsschulung im Microsoft 365 Defender Portal verwenden, um realistische Angriffsszenarien in Ihrer Organisation auszuführen. Diese simulierten Angriffe können Ihnen helfen, anfällige Benutzer zu identifizieren und zu finden, bevor sich ein realer Angriff auf Ihre Unterlinie auswirkt. Lesen Sie diesen Artikel, um mehr zu erfahren.

> [!NOTE]
> Das Angriffssimulationstraining ersetzt die alte Angriffssimulator-V1-Erfahrung, die im [Angriffssimulator in Microsoft Defender für Office 365](attack-simulator.md)beschrieben ist.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wissenswertes, bevor Sie anfangen

- Um das Microsoft 365 Defender-Portal zu öffnen, gehen Sie zu <https://security.microsoft.com>. Angriffssimulationsschulungen sind im Angriffssimulationstraining für **E-Mail und Zusammenarbeit** \> verfügbar. Um direkt zum Angriffssimulationstraining zu wechseln, öffnen Sie <https://security.microsoft.com/attacksimulator> .

- Weitere Informationen zur Verfügbarkeit von Angriffssimulationsschulungen in verschiedenen Microsoft 365-Abonnements finden Sie unter [Microsoft Defender für Office 365 Dienstbeschreibung.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

- Ihnen müssen Berechtigungen im Microsoft 365 Defender Portal oder in Azure Active Directory zugewiesen werden, bevor Sie die Verfahren in diesem Artikel ausführen können. Insbesondere müssen Sie Mitglied der **Organisationsverwaltung,** des **Sicherheitsadministrators** oder einer der folgenden Rollen sein:
  - Administratoren des **Angriffssimulators:** Erstellen und Verwalten aller Aspekte von Angriffssimulationskampagnen.
  - Autoren der **Angriffssimulatornutzlast:** Erstellen Sie Angriffsnutzlasten, die ein Administrator später initiieren kann.

  Weitere Informationen finden Sie unter [Berechtigungen im Microsoft 365 Defender-Portal](permissions-microsoft-365-security-center.md) oder [über Administratorrollen.](../../admin/add-users/about-admin-roles.md)

- Es gibt keine entsprechenden PowerShell-Cmdlets für Angriffssimulationsschulungen.

- Angriffssimulations- und Schulungsdaten werden zusammen mit anderen Kundendaten für Microsoft 365-Dienste gespeichert. Weitere Informationen finden Sie unter [Microsoft 365 Datenspeicherorten.](../../enterprise/o365-data-locations.md) Die Angriffssimulation ist in den folgenden Regionen verfügbar: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN und KOR.

- Ab dem 15. Juni 2021 ist das Angriffssimulationstraining in GCC verfügbar. Wenn Ihre Organisation über Office 365 G5-GCC oder Microsoft Defender für Office 365 (Plan 2) für Behörden verfügt, können Sie die Angriffssimulationsschulung im Microsoft 365 Defender Portal verwenden, um realistische Angriffsszenarien in Ihrer Organisation auszuführen, wie in diesem Artikel beschrieben. Angriffssimulationsschulungen sind in GCC High- oder DoD-Umgebungen noch nicht verfügbar.

> [!NOTE]
> Die Angriffssimulationsschulung bietet E3-Kunden eine Teilmenge der Funktionen als Testversion. Das Testangebot enthält die Möglichkeit, eine Credential Harvest-Nutzlast zu verwenden, und die Möglichkeit, "ISA-Phishing" oder "Massenmarktphishing" auszuwählen. Keine anderen Funktionen sind Teil des E3-Testangebots.

## <a name="simulations"></a>Simulationen

*Phishing* ist ein allgemeiner Begriff für E-Mail-Angriffe, die versuchen, vertrauliche Informationen in Nachrichten zu stehlen, die scheinbar von legitimen oder vertrauenswürdigen Absendern stammen. *Phishing* ist Teil einer Teilmenge von Techniken, die wir als _Social Engineering_ klassifizieren.

Im Angriffssimulationstraining stehen mehrere Arten von Social Engineering-Techniken zur Verfügung:

- **Sammeln von Anmeldeinformationen:** Ein Angreifer sendet dem Empfänger eine Nachricht, die eine URL enthält. Wenn der Empfänger auf die URL klickt, wird er zu einer Website weitergeleitet, die in der Regel ein Dialogfeld anzeigt, in dem der Benutzer nach benutzername und kennwort gefragt wird. In der Regel ist die Zielseite so angeordnet, dass sie eine bekannte Website darstellt, um dem Benutzer vertrauen zu können.

- **Antischadsoftwareanlage:** Ein Angreifer sendet dem Empfänger eine Nachricht, die eine Anlage enthält. Wenn der Empfänger die Anlage öffnet, wird beliebiger Code (z. B. ein Makro) auf dem Gerät des Benutzers ausgeführt, um dem Angreifer zu helfen, zusätzlichen Code zu installieren oder sich weiter zu verfangen.

- **Link in Anlage:** Dies ist eine Hybridbereitstellung einer Anmeldeinformationsauswahl. Ein Angreifer sendet dem Empfänger eine Nachricht, die eine URL innerhalb einer Anlage enthält. Wenn der Empfänger die Anlage öffnet und auf die URL klickt, wird er zu einer Website geleitet, die in der Regel ein Dialogfeld anzeigt, in dem der Benutzer nach dem Benutzernamen und Kennwort gefragt wird. In der Regel ist die Zielseite so angeordnet, dass sie eine bekannte Website darstellt, um dem Benutzer vertrauen zu können.

- **Link zu Schadsoftware:** Ein Angreifer sendet dem Empfänger eine Nachricht mit einem Link zu einer Anlage auf einer bekannten Dateifreigabewebsite (z. B. SharePoint Online oder Dropbox). Wenn der Empfänger auf die URL klickt, wird die Anlage geöffnet, und beliebiger Code (z. B. ein Makro) wird auf dem Gerät des Benutzers ausgeführt, um dem Angreifer zu helfen, zusätzlichen Code zu installieren oder sich weiter zu verfeinern.

- **Drive-by-URL:** Ein Angreifer sendet dem Empfänger eine Nachricht, die eine URL enthält. Wenn der Empfänger auf die URL klickt, wird er zu einer Website geleitet, die versucht, Hintergrundcode auszuführen. Dieser Hintergrundcode versucht, Informationen über den Empfänger zu sammeln oder beliebigen Code auf dem Gerät bereitzustellen. In der Regel ist die Zielwebsite eine bekannte Website, die kompromittiert wurde, oder ein Klon einer bekannten Website. Wenn Sie mit der Website vertraut sind, können Sie den Benutzer davon überzeugen, dass der Link sicher angeklickt werden kann. Diese Technik wird auch als _Wasserangriff bezeichnet._

> [!NOTE]
> Überprüfen Sie die Verfügbarkeit der simulierten Phishing-URL in Ihren unterstützten Webbrowsern, bevor Sie die URL in einer Phishingkampagne verwenden. Während wir mit vielen ANBIETERN für die URL-Zuverlässigkeit zusammenarbeiten, um diese Simulations-URLs immer zuzulassen, verfügen wir nicht immer über eine vollständige Abdeckung (z. B. Google Tresor Browsen). Die meisten Anbieter bieten Anleitungen, mit denen Sie immer bestimmte URLs zulassen können (z. B. <https://support.google.com/chrome/a/answer/7532419> ).

Die von der Angriffssimulationsschulung verwendeten URLs werden in der folgenden Liste beschrieben:

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

Schrittweise Anleitungen zum Erstellen und Senden einer neuen Simulation finden Sie unter [Simulieren eines Phishingangriffs.](attack-simulation-training.md)

### <a name="create-a-payload"></a>Erstellen einer Nutzlast

Schrittweise Anleitungen zum Erstellen einer Nutzlast für die Verwendung innerhalb einer Simulation finden Sie unter [Erstellen einer benutzerdefinierten Nutzlast für Angriffssimulationsschulungen.](attack-simulation-training-payloads.md)

### <a name="gaining-insights"></a>Gewinnen von Einblicken

Schritt-für-Schritt-Anleitungen zum Gewinnen von Erkenntnissen mit der Berichterstellung finden Sie unter ["Gewinnen von Einblicken durch Angriffssimulationsschulungen".](attack-simulation-training-insights.md)

> [!NOTE]
> Der Angriffssimulator verwendet Tresor Links in Defender für Office 365, um Klickdaten für die URL in der Nutzlastnachricht, die an Zielempfänger einer Phishingkampagne gesendet wird, sicher nachzuverfolgen, auch wenn die Einstellung **"Benutzerklicks nicht nachverfolgen"** in Tresor Links-Richtlinien aktiviert ist.
