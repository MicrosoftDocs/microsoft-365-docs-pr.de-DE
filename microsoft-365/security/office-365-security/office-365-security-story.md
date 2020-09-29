---
title: Sicherheit in Office 365
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 08/13/2020
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- microsoft-365-docs-pr
description: Sicherheit in Office 365, von EoP bis ATP-Pläne 1 und 2, Standard mäßige und strenge Sicherheitskonfigurationen und mehr, damit Sie verstehen, was Sie haben und wie Sie Ihre Eigenschaften sichern können.
ms.openlocfilehash: 680066f58850f59523ae6fb8a8168459dd813fc1
ms.sourcegitcommit: 888b9355ef7b933c55ca6c18639c12426ff3fbde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/29/2020
ms.locfileid: "48304846"
---
# <a name="office-365-security-outline"></a>Office 365 Sicherheits Gliederung

In diesem Artikel werden die neuen Sicherheitseigenschaften in der Cloud vorgestellt. Unabhängig davon, ob Sie Teil eines Security Operations Centers sind, Sie sind ein Sicherheits Administrator, der neu in diesem Bereich ist, oder wenn Sie eine Aktualisierung wünschen, Let es Get Started.

> [!CAUTION]
> Hallo. Wenn Sie **Outlook.com**, **Microsoft 365-Familie**oder **Microsoft 365 Personal**verwenden und *sichere Links* oder Informationen zu *sicheren Anlagen* benötigen, ***Klicken Sie auf diesen Link***: [Advanced Outlook.com Security for Microsoft 365 subscribers](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2). Dank!

## <a name="office-365-security-spelled-out"></a>Office 365 Sicherheit geschrieben

Jedes Office 365 Abonnement verfügt über Sicherheitsfunktionen. Die Ziele und Aktionen, die Sie ausführen können, hängen vom Fokus dieser unterschiedlichen Abonnements ab. In Office 365 Sicherheit gibt es drei wichtige Sicherheitsdienste (oder Produkte), die mit Ihrem Abonnementtyp verbunden sind:

1. Exchange Online Schutz (EoP)
1. Erweiterter Bedrohungsschutz, Plan 1 (ATP P1)
1. Advanced Threat Protection, Plan 2 (ATP P2)

> [!NOTE]
> Wenn Sie Ihr Abonnement erworben haben und *jetzt*Sicherheitsfeatures bereitstellen müssen, fahren Sie mit den Schritten im Artikel [Protect Against Threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide) fort. Wenn Sie noch nicht mit Ihrem Abonnement vertraut sind und Ihre Lizenz vor dem Start wissen möchten, suchen Sie in der [Microsoft 365 Admin Center](https://admin.microsoft.com/AdminPortal/#/homepage)die Abrechnung > Ihre Produkte.

Office 365 Sicherheit basiert auf den von EoP angebotenen kernschutz Funktionen. EoP ist in jedem Abonnement vorhanden, in dem Exchange Online Postfächer gefunden werden können (denken Sie daran, dass alle hier besprochenen Sicherheitsprodukte auf der Cloud basieren).

Möglicherweise sind Sie daran gewöhnt, dass diese drei Komponenten auf diese Weise behandelt werden:

|EOP  | ATP P1 | ATP P2  |
|---------|---------|---------|
|Verhindert allgemeine, volumenbasierte, bekannte Angriffe.    |  Schützt e-Mails und die Zusammenarbeit von Zero-Day-Malware, Phishing und geschäftlichen e-Mail-Kompromissen.       | Hinzufügen von Untersuchungen, Jagden und Antworten nach einem Verstoß sowie Automatisierung und Simulation (für Schulungen).         |

Aber im Hinblick auf die Architektur, beginnen wir mit dem Gedanken an jedes Stück als kumulative Schichten von Sicherheit, die jeweils mit einem Sicherheits Schwerpunkt. Mehr wie folgt aus:

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_EOPandATPGraphic.png" alt-text="Placeholder graphic":::

Obwohl ***jeder dieser*** Dienste ein bestimmtes Ziel unter schützen, erkennen, untersuchen und reagieren hervorhebt, können ***alle Dienste alle*** Ziele zum Schutz, erkennen, untersuchen und reagieren erfüllen.

Der Kern Office 365 Sicherheit besteht in EoP Schutz. ATP P1 enthält EoP. ATP P2 enthält P1 und EOP. Die Struktur ist kumulativ. Deshalb sollten Sie beim Konfigurieren von ATP mit EoP beginnen und die Ebenen überarbeiten.

Obwohl die e-Mail-Authentifizierungskonfiguration im öffentlichen DNS erfolgt, ist es wichtig, dieses Feature zu konfigurieren, um die Verteidigung vor Spoofing zu unterstützen. *Wenn Sie über EoP verfügen,* ***sollten Sie die [e-Mail-Authentifizierung konfigurieren](https://docs.microsoft.com/microsoft-365/security/office-365-security/email-validation-and-authentication?view=o365-worldwide)***.

Wenn Sie über eine Office 365 E3 oder darunter verfügen, verfügen Sie über EoP, jedoch mit der Option zum erwerben eigenständiger ATP P1 durch Upgrades. Wenn Sie Office 365 E5 haben, haben Sie bereits ATP P2.

> [!TIP]
> Wenn Ihr Abonnement weder Office 365 E3 noch E5 lautet, können Sie weiterhin überprüfen, ob Sie die Möglichkeit haben, ein Upgrade auf ATP P1 vorzusehen. Wenn Sie Interesse haben, werden auf [dieser Webseite](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) Abonnements aufgeführt, die für das ATP P1-Upgrade berechtigt sind (überprüfen Sie das Ende der Seite für den Fine-Print).

## <a name="the-office-365-security-ladder-from-eop-to-atp"></a>Die Office 365 Security Ladder von EoP zu ATP

:::image type="content" source="../../media/tp_EOPATPEmailAuth4.gif" alt-text="Placeholder graphic":::

> [!IMPORTANT]
> Erfahren Sie mehr über die folgenden Seiten: [Exchange Online Schutz](https://docs.microsoft.com/microsoft-365/security/office-365-security/exchange-online-protection-overview?view=o365-worldwide)und [Erweiterter Bedrohungsschutz](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide).

Was das Hinzufügen von ATP-Plänen zu einem Vorteil des reinen EoP-Bedrohungs Managements leistet, kann auf den ersten Blick schwer zu erkennen sein. Um zu helfen, zu klären, ob ein Upgrade-Pfad für Ihre Organisation richtig ist, sehen wir uns die Funktionen der einzelnen Produkte an, wenn es um Folgendes geht:

 - verhindern und erkennen von Bedrohungen
 - untersuchen
 - reagiert

beginnend mit **Exchange Online Schutz**:
<p>

|Verhindern/erkennen  |Untersuchen  |Reaktion  |
|---------|---------|---------|
| Zu den Technologien gehören:<ul><li>Spam</li><li>phishingfilterrichtlinie</li><li>Schadsoftware</li><li>Massen-e-Mail</li><li>Spoof Intelligence</li><li>Identitätswechsel Erkennung</li><li>Administrator Quarantäne</li><li>Administrator-und Benutzerübermittlungen falsch positiver und falsch negativer Ergebnisse</li><li>Allow/Block für URLs und Dateien</li><li>Berichte</li></u1>|<li>Durchsuchen von Überwachungsprotokollen</li><li>Nachrichtenablaufverfolgung</li>|<li>Automatische Bereinigung ohne Stunden (zap)</li><li>Einschränkung und Testen von Zulassungs-und Sperrlisten</li>|

Wenn Sie in EoP graben möchten, wechseln Sie **[zu diesem Artikel](https://review.docs.microsoft.com/microsoft-365/security/office-365-security/exchange-online-protection-overview?view=o365-21vianet&branch=tp_EOPOverview)**.

Da diese Produkte kumulativ sind, wenn Sie ATP P1 auswerten und beschließen, es zu abonnieren, fügen Sie diese Fähigkeiten hinzu.

Gewinne mit **erweitertem Bedrohungsschutz, Plan 1** (bis Datum):
<p>

|Verhindern/erkennen  |Untersuchen  |Reaktion  |
|---------|---------|---------|
| Technologien umfassen alles in EoP Plus:<u1><li>Sichere Anlagen</li><li>Sichere Links<li>ATP-Schutz für Arbeitslasten (z. b. SharePoint Online, Teams, OneDrive für Unternehmen)</li><li>Zeit-zu-Klick-Schutz in e-Mails, Office-Clients und Teams</li><li>ATP-Anti-Phishing</li><li>Schutz von Benutzer-und Domänen Identitätswechsel</li><li>Warnungen und die Siem-Integrations-API für Warnungen</li>|<li>Siem-Integrations-API für Erkennungen</li><li>**Echt Zeit Erkennungstool**</li><li>URL-Ablaufverfolgung</li>|<li>Gleich</li></u1>

Daher wird ATP P1 auf der Seite " ***Prävention*** " des Hauses erweitert und zusätzliche ***Erkennungs***Formen hinzugefügt.

ATP P1 fügt auch **Echt Zeit Erkennungen** für Untersuchungen hinzu. Der Name dieses Bedrohungs Jagd Tools ist fett formatiert, da es klar ist, dass Sie ATP P1 *kennen* . Sie wird nicht in ATP P2 angezeigt.

Gewinne mit **Advanced Threat Protection, Plan 2** (bis Datum):
<p>

|Verhindern/erkennen  |Untersuchen  |Reaktion  |
|---------|---------|---------|
| Zu den Technologien zählen alles in EoP und ATP P1 Plus:<u1><li>Gleich</li>|<li>**Sicherheitsrisiken-Explorer**</li><li>Nachverfolgungslisten für Bedrohungen</li><li>Kampagnen Ansichten</li>|<li>Automatische Untersuchung und Reaktion (Air)</li><li>Air from Threat Explorer</li><li>Air für kompromittierte Benutzer</li><li>Siem-Integrations-API für automatisierte Untersuchungen</li>

Daher erweitert ATP P2 die ***Untersuchung und Antwort*** Seite des Hauses und fügt eine neue Jagd Stärke hinzu. Automatisierung.

In ATP P2 wird das primäre Jagd Werkzeug als **Bedrohungs-Explorer** und nicht als Echtzeiterkennung bezeichnet. Wenn Sie Threat Explorer sehen, wenn Sie zum Sicherheitscenter navigieren, sind Sie in ATP P2.

Um die Details von ATP P1 und P2 zu erhalten, **[wechseln Sie zu diesem Artikel](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)**.

> [!TIP]
> EoP und ATP sind auch unterschiedlich, wenn es um Endkunden geht. In EoP und ATP P1 liegt der Schwerpunkt auf der *Sensibilisierung*, und daher enthalten diese beiden Dienste das *Outlook-Add-in "Berichtsnachricht* ", damit Benutzer e-Mails, die Sie verdächtig finden, zur weiteren Analyse melden können. <p> In ATP P2 (das alles in EoP und P1 enthält) wird der Fokus auf die *Weiterbildung* von Endbenutzern verschoben, sodass das Security Operations Center Zugriff auf ein leistungsfähiges *Threat Simulator* -Tool und die von ihm bereitgestellten Metriken für Endbenutzer hat.

## <a name="office-365-atp-plan-1-vs-plan-2-cheat-sheet"></a>Office 365 ATP Plan 1 vs. Plan 2 Cheat Sheet

Diese Kurzübersicht hilft Ihnen zu verstehen, welche Funktionen mit den einzelnen ATP-Abonnements ausgestattet sind. In Kombination mit Ihrem Wissen über EoP-Funktionen kann es Entscheidungsträgern in Unternehmen helfen, zu bestimmen, welche ATP am besten für Ihre Anforderungen geeignet ist.

|Office 365 ATP Plan 1|Office 365 ATP Plan 2|
|---|---|
|<br/>Konfigurations-, Schutz- und Erkennungsfunktionen: <ul><li>[Sichere Anlagen](atp-safe-attachments.md)</li><li>[Sichere Links](atp-safe-links.md)</li><li>[ATP für SharePoint, OneDrive und Microsoft Teams](atp-for-spo-odb-and-teams.md)</li><li>[ATP Antiphishingschutz](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)</li><li>[Echtzeiterkennungen](threat-explorer.md)</li></ul>|Office 365 ATP Plan 1 – Funktionen<br/>--- plus ---<br/>Automatisierungs-, Untersuchungs-, Fehlerbehebungs- und Schulungsfunktionen:</li><li>[Bedrohungs-Tracker](threat-trackers.md)</li><li>[Sicherheitsrisiken-Explorer](threat-explorer.md)</li><li>[Automatische Untersuchung und Reaktion](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)</li><li>[Angriffssimulator](attack-simulator.md)</li></ul>|
|

- Office 365 ATP Plan 2 ist in Office 365 E5, Office 365 A5 und Microsoft 365 E5 enthalten.

- Office 365 ATP Plan 1 ist in Microsoft 365 Business Premium enthalten.

- Office 365 ATP Plan 1 und Office 365 ATP Plan 2 sind jeweils als Add-On für bestimmte Abonnements verfügbar. Weitere Informationen finden Sie hier: eine weitere Link [Feature-Verfügbarkeit in ATP-Plänen](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

- Das Feature [Sichere Dokumente](safe-docs.md) ist nur für Benutzer mit den Lizenzen für Microsoft 365 E5 oder Microsoft 365 E5 Security verfügbar (nicht in Office 365 ATP-Plänen enthalten).

- Wenn Ihr aktuelles Abonnement Office 365 ATP nicht enthält und Sie es wünschen, [wenden Sie sich an den Vertrieb, um eine Testversion zu starten](https://go.microsoft.com/fwlink/p/?LinkId=518644), und erfahren Sie, wie ATP in Ihrer Organisation funktionieren kann.

> [!TIP]
> ***Insider Tipp***. Sie können das docs.Microsoft.com-Inhaltsverzeichnis verwenden, um mehr über EoP und ATP zu erfahren. Navigieren Sie zu [Office 365 Sicherheits](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap?view=o365-worldwide) Artikel, und Sie werden feststellen, dass die Inhaltsverzeichnis-Organisation mit Evaluierung und Bereitstellung (einschließlich Migration) beginnt und dann in den Themen Prävention, Erkennung, Untersuchung und Reaktion weiterentwickelt wird. <p> Diese Struktur ist unterteilt, sodass Sicherheits **Verwaltungs** Themen mit Themen zu **sicherheitsvorgängen** befolgt werden. Wenn Sie ein neues Mitglied einer der beiden Auftrags Rollen sind, verwenden Sie den Link in diesem Tipp und Ihr Wissen über das Inhaltsverzeichnis, um den Raum zu erlernen. Denken Sie daran, *Feedback Links* zu verwenden und die *Artikel bewerten* , wie Sie gehen. Feedback hilft uns, das zu verbessern, was wir Ihnen bieten.
