---
title: Office 365 Security, Microsoft Defender für Office 365, EOP, MSDO
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 08/13/2020
audience: Admin
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Sicherheit in Office 365, von EOP zu Defender for Office 365 Plans 1 and 2, Standard vs. Strict security configurations und vieles mehr. Verstehen Sie, was Sie haben, und wie Sie Ihre Eigenschaften sichern.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e1c6e768098cd59892c2572fb52497c873aef1a3
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/10/2021
ms.locfileid: "50711940"
---
# <a name="office-365-security-overview"></a>Office 365 Security Overview

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)


In diesem Artikel werden Die neuen Sicherheitseigenschaften in der Cloud erläutert. Ganz gleich, ob Sie Teil eines Security Operations Center sind, ein Sicherheitsadministrator neu im Bereich sind oder eine Aktualisierung wünschen, beginnen wir.

> [!CAUTION]
> Wenn Sie **Outlook.com**, Microsoft **365 Family** oder **Microsoft 365 Personal** verwenden  und Informationen zu sicheren Links oder sicheren Anlagen benötigen, klicken Sie auf diesen ***Link***: Erweiterte Outlook.com Sicherheit für [Microsoft 365-Abonnenten](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2). 

## <a name="office-365-security-spelled-out"></a>Office 365-Sicherheit mit Schreibweise

Jedes Office 365-Abonnement verfügt über Sicherheitsfunktionen. Die Ziele und Aktionen, die Sie ausführen können, hängen vom Fokus dieser verschiedenen Abonnements ab. In Office 365 Security gibt es drei Hauptsicherheitsdienste (oder Produkte), die an Ihren Abonnementtyp gebunden sind:

1. Exchange Online Protection (EOP)
1. Microsoft Defender für Office 365 Plan 1 (Defender für Office P1)
1. Microsoft Defender for Office 365 Plan 2 (Defender for Office P2)

> [!NOTE]
> Wenn Sie Ihr Abonnement gekauft haben und sicherheitsfeatures jetzt ausführen *müssen,* fahren Sie mit den Schritten im [Artikel Schützen vor Bedrohungen](protect-against-threats.md) weiter. Wenn Sie neu in Ihrem Abonnement sind und Ihre Lizenz kennen möchten, bevor Sie beginnen, navigieren Sie zu Abrechnung > Ihre Produkte im [Microsoft 365 Admin Center](https://admin.microsoft.com/AdminPortal/#/homepage).

Die Office 365-Sicherheit baut auf den zentralen Schutzvorkehrungen von EOP auf. EOP ist in jedem Abonnement vorhanden, in dem Exchange Online-Postfächer gefunden werden können (denken Sie daran, dass alle hier behandelten Sicherheitsprodukte cloudbasierte Sind).

Möglicherweise sind Sie daran gewöhnt, diese drei Komponenten auf diese Weise zu diskutieren:

|EOP|Microsoft Defender für Office 365 P1|Microsoft Defender für Office 365 P2|
|---|---|---|
|Verhindert umfassende, volumenbasierte, bekannte Angriffe.|Schützt E-Mails und die Zusammenarbeit vor Zero-Day-Schadsoftware, Phishing und geschäftlichen E-Mail-Angriffen.|Fügt Untersuchung, Suche und Reaktion nach der Verletzung sowie Automatisierung und Simulation (für Schulungen) hinzu.|
|

Im Hinblick auf die Architektur betrachten wir jedoch zunächst jedes Einzelne als kumulative Sicherheitsebenen, die jeweils einen Sicherheitsa besonders hervorgehoben haben. Weitere Informationen finden Sie hier:

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="EOP und Microsoft Defender für Office 365 und ihre Beziehungen miteinander mit Service-Schwerpunkt, einschließlich einer Notiz für die E-Mail-Authentifizierung.":::

Obwohl jeder dieser Dienste ein Ziel zwischen Protect, Detect, Investigate und Respond unterstreicht,***** können alle *___* Dienste _ beliebige * der Ziele des Schützens, Erkennens, Untersuchens und Reagierens durchführen.

Der Kern der Office 365-Sicherheit ist der EOP-Schutz. Microsoft Defender für Office 365 P1 enthält EOP. Defender für Office 365 P2 enthält P1 und EOP. Die Struktur ist kumulativ. Deshalb sollten Sie bei der Konfiguration dieses Produkts mit EOP beginnen und mit Defender for Office 365 arbeiten.

Obwohl die E-Mail-Authentifizierungskonfiguration im öffentlichen DNS stattfindet, ist es wichtig, dieses Feature so zu konfigurieren, dass es vor Spoofing schützen kann. *Wenn Sie über EOP verfügen,* ***sollten Sie die [E-Mail-Authentifizierung konfigurieren.](email-validation-and-authentication.md)***

Wenn Sie über ein Office 365 E3 oder darunter verfügen, verfügen Sie über EOP, aber mit der Option, eigenständigen Defender für Office 365 P1 über ein Upgrade zu kaufen. Wenn Sie office 365 E5 haben, haben Sie bereits Defender für Office 365 P2.

> [!TIP]
> Wenn Ihr Abonnement weder Office 365 E3 noch E5 ist, können Sie dennoch überprüfen, ob Sie die Möglichkeit haben, ein Upgrade auf Microsoft Defender für Office 365 P1 zu durchführen. Wenn Sie daran interessiert [sind,](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) werden auf dieser Webseite Abonnements aufgeführt, die für das Upgrade von Microsoft Defender für Office 365 P1 berechtigt sind (überprüfen Sie das Ende der Seite für das Feindrucken).

## <a name="the-office-365-security-ladder-from-eop-to-microsoft-defender-for-office-365"></a>Die Sicherheitsleiter von Office 365 von EOP zu Microsoft Defender für Office 365

![EOP und Microsoft Defender für Office 365 und deren Sicherheitsgewicht, von Protect and Detect bis Investigate and Respond. Die E-Mail-Authentifizierungskonfiguration (mindestens DKIM und DMARC) sollte für EOP und up eingerichtet werden.](../../media/tp_EOPATPP1P2Take6.gif#lightbox)

> [!IMPORTANT]
> Erfahren Sie mehr über die Details auf diesen Seiten: [Exchange Online Protection](exchange-online-protection-overview.md)und Defender for Office [365](office-365-atp.md).

Was das Hinzufügen von Microsoft Defender für Office 365-Plänen zu einem Vorteil der reinen EOP-Bedrohungsverwaltung macht, ist auf den ersten Blick schwer zu erkennen. Um zu sortieren, ob ein Upgradepfad für Ihre Organisation richtig ist, sehen wir uns die Funktionen der einzelnen Produkte an, wenn es um:

- Verhindern und Erkennen von Bedrohungen
- untersuchen
- Reagieren

beginnend mit **Exchange Online Protection**:
<p>

|Verhindern/Erkennen|Untersuchen|Reagieren|
|---|---|---|
|Zu den Technologien gehören:<ul><li>Spam</li><li>phish</li><li>Schadsoftware</li><li>Massen-E-Mail</li><li>Spoof intelligence</li><li>Identitätswechselerkennung</li><li>Administratorquarantäne</li><li>Administrator- und Benutzerübermittlungen falsch positiver und falsch negativer Ergebnisse</li><li>Zulassen/Blockieren von URLs und Dateien</li><li>Berichte</li></u1>|<li>Durchsuchen von Überwachungsprotokollen</li><li>Nachrichtenablaufverfolgung</li>|<li>Zero-Hour Auto-Purge (ZAP)</li><li>Einschränkung und Tests von Listen mit zulässigen und blockierten Listen</li>|
|

Wenn Sie sich in EOP einmuchgen möchten, **[wechseln Sie zu diesem Artikel](exchange-online-protection-overview.md)**.

Da diese Produkte kumulativ sind, fügen Sie diese Fähigkeiten hinzu, wenn Sie Microsoft Defender für Office 365 P1 bewerten und sich für das Abonnement entscheiden.

Gewinne mit **Defender für Office 365, Plan 1** (bis heute):
<p>

|Verhindern/Erkennen|Untersuchen|Reagieren|
|---|---|---|
|Zu den Technologien gehören alles in EOP sowie:<u1><li>Sichere Anlagen</li><li>Sichere Links<li>Microsoft Defender für Office 365-Schutz für Arbeitsauslastungen (z. B. SharePoint Online, Teams, OneDrive for Business)</li><li>Time-of-Click-Schutz in E-Mails, Office-Clients und Teams</li><li>Antiphishing in Defender for Office 365</li><li>Schutz vor Identitätswechsel von Benutzern und Domänen</li><li>Warnungen und SIEM-Integrations-API für Warnungen</li>|<li>SIEM-Integrations-API für Erkennungen</li><li>**Tool zur Erkennung in Echtzeit**</li><li>URL-Ablaufverfolgung</li>|<li>Gleich</li></u1>

Microsoft Defender for Office 365 P1 erweitert sich also auf der Seite ***Prevention** _ des Hauses und fügt zusätzliche __*_ Erkennungsarten **hinzu.

Microsoft Defender für Office 365 P1 fügt außerdem **Echtzeiterkennungen** für Untersuchungen hinzu. Der Name dieses Tools für die Bedrohungssuche ist  fett formatiert, da dies ein klares Mittel ist, um zu wissen, dass Sie Defender für Office 365 P1 haben. Sie wird in Defender for Office 365 P2 nicht angezeigt.

Vorteile mit **Defender for Office 365, Plan 2** (bis heute):
<p>

|Verhindern/Erkennen|Untersuchen|Reagieren|
|---|---|---|
|Zu den Technologien gehören alles in EOP und Microsoft Defender für Office 365 P1 plus:<u1><li>Gleich</li>|<li>**Sicherheitsrisiken-Explorer**</li><li>Nachverfolgungslisten für Bedrohungen</li><li>Kampagnenansichten</li>|<li>Automatisierte Untersuchung und Reaktion (AIR)</li><li>AIR aus dem Bedrohungs-Explorer</li><li>AIR für gefährdete Benutzer</li><li>SIEM-Integrations-API für automatisierte Untersuchungen</li>

Microsoft Defender für Office 365 P2  erweitert also die Untersuchungs- und Reaktionsseite des Hauses und fügt eine neue Stärke für die Suche hinzu. Automatisierung.

In Microsoft Defender für Office 365 P2  wird das primäre Tool als Bedrohungs-Explorer und nicht als Echtzeiterkennung bezeichnet. Wenn Der Bedrohungs-Explorer angezeigt wird, wenn Sie zum Sicherheitscenter navigieren, sind Sie in Microsoft Defender für Office 365 P2.

Um sich mit den Details von Microsoft Defender für Office 365 P1 und P2 zurecht zu kommen, wechseln Sie **[zu diesem Artikel.](office-365-atp.md)**

> [!TIP]
> EOP und Microsoft Defender für Office 365 unterscheiden sich auch bei Endbenutzern. In EOP und Defender für Office 365 P1 liegt der Schwerpunkt auf dem *Bewusstsein,* und daher enthalten diese beiden Dienste das *Outlook-Add-In* Berichtsnachricht, damit Benutzer E-Mails melden können, die sie verdächtig finden, um weitere Analysen durchzuführen. <p> In Defender for Office 365 P2 (das alles in EOP  und P1 enthält) verlagert sich der Fokus auf weitere Schulungen für Endbenutzer, sodass das Security Operations Center Zugriff auf ein leistungsfähiges Threat *Simulator-Tool* und die von diesem zur Verfügung 2013 zur Verfügung 2013 zur Verfügung 2014 zur Verfügung 2013 von den Endbenutzern zur Verfügung stellenden Metriken hat.

## <a name="microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet"></a>Microsoft Defender for Office 365 Plan 1 vs. Plan 2 cheat sheet

Diese Kurzübersicht hilft Ihnen zu verstehen, welche Funktionen mit jedem Microsoft Defender for Office 365-Abonnement verfügbar sind. In Kombination mit Ihrem Wissen über EOP-Features können Entscheidungsträger in Unternehmen bestimmen, welche Microsoft Defender für Office 365 für ihre Anforderungen am besten ist.

|Defender für Office 365 Plan 1|Defender für Office 365 Plan 2|
|---|---|
|Konfigurations-, Schutz- und Erkennungsfunktionen: <ul><li>[Sichere Anlagen](atp-safe-attachments.md)</li><li>[Sichere Links](atp-safe-links.md)</li><li>[Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams](atp-for-spo-odb-and-teams.md)</li><li>[Antiphishingschutz in Defender for Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[Echtzeiterkennungen](threat-explorer.md)</li></ul>|Funktionen von Defender für Office 365 Plan 1 <p> --- plus --- <p> Automatisierungs-, Untersuchungs-, Fehlerbehebungs- und Schulungsfunktionen: <ul><li>[Bedrohungs-Tracker](threat-trackers.md)</li><li>[Sicherheitsrisiken-Explorer](threat-explorer.md)</li><li>[Automatische Untersuchung und Reaktion](office-365-air.md)</li><li>[Angriffssimulator](attack-simulator.md)</li></ul>|
|

- Microsoft Defender für Office 365 Plan 2 ist in Office 365 E5, Office 365 A5 und Microsoft 365 E5 enthalten.

- Microsoft Defender für Office 365 Plan 1 ist in Microsoft 365 Business Premium enthalten.

- Microsoft Defender für Office 365 Plan 1 und Defender for Office 365 Plan 2 sind jeweils als Add-On für bestimmte Abonnements verfügbar. Weitere Informationen finden Sie im folgenden link Featureverfügbarkeit [in Microsoft Defender für Office 365-Plänen.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)

- Das Feature [Sichere Dokumente](safe-docs.md) ist nur für Benutzer mit den Lizenzen für Microsoft 365 E5 oder Microsoft 365 E5 Security verfügbar (nicht in Microsoft Defender für Office 365-Plänen enthalten).

- Wenn Ihr aktuelles Abonnement Microsoft Defender für Office 365 nicht enthält und Sie es [wünschen,](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html)wenden Sie sich an den Vertrieb, um eine Testversion zu starten, und erfahren Sie, wie Microsoft Defender für Office 365 in Ihrer Organisation funktionieren kann.

> [!TIP]
> ***Insidertipp** _. Sie können das docs.microsoft.com inhaltsverzeichnis verwenden, um mehr über EOP und Microsoft Defender für Office 365 zu erfahren. Navigieren Sie zurück zu dieser Seite, [Office 365 Security Overview](index.md), und Sie werden feststellen, dass das Inhaltsverzeichnis in der Seitenleiste angezeigt wird. Sie beginnt mit der Bereitstellung (einschließlich Migration) und setzt dann die Prävention, Erkennung, Untersuchung und Reaktion fort. <p> Diese Struktur ist so unterteilt, dass den Themen *_Security Administration** Themen zu **Sicherheitsvorgängen folgen.** Wenn Sie ein neues Mitglied einer der Rollen sind, verwenden Sie den Link in diesem Tipp und Ihr Wissen über das Inhaltsverzeichnis, um den Bereich zu erlernen. Denken Sie daran, *feedbacklinks zu verwenden* *und Artikel zu bewerten,* während Sie gehen. Feedback hilft uns, das zu verbessern, was wir Ihnen anbieten.

## <a name="where-to-go-next"></a>Wohin mit dem nächsten Schritt

Wenn Sie ein Sicherheitsadministrator sind, müssen Sie möglicherweise DKIM oder DMARC für Ihre E-Mails konfigurieren. Möglicherweise möchten Sie "Strikte" Sicherheitsvoreinstellungen für Ihre Prioritätsbenutzer rollouten oder nach Neuen im Produkt suchen. Oder wenn Sie mit Security Ops zusammenarbeiten, können Sie Echtzeiterkennungen oder den Bedrohungs-Explorer nutzen, um die Erkennung von Endbenutzern mit dem Angriffssimulator zu untersuchen und zu beantworten oder die Erkennung von Endbenutzern zu schulen. In beiden Fällen finden Sie hier einige zusätzliche Empfehlungen für die nächsten Schritte.

[E-Mail-Authentifizierung, einschließlich SPF, DKIM und DMARC (mit Links zum Setup aller drei)](email-validation-and-authentication.md)

[Sehen Sie sich die spezifischen empfohlenen "goldenen" Konfigurationen](recommended-settings-for-eop-and-office365-atp.md) an, und verwenden Sie die empfohlenen Voreinstellungen, um [Sicherheitsrichtlinien schnell zu konfigurieren.](preset-security-policies.md)

Aufholen [der Neuen in Microsoft Defender für Office 365 (einschließlich EOP-Entwicklungen)](whats-new-in-office-365-atp.md)

[Verwenden von Bedrohungs-Explorer oder Echtzeiterkennungen](threat-explorer.md)

Verwenden [des Angriffssimulators in Microsoft Defender für Office 365](attack-simulator.md)
