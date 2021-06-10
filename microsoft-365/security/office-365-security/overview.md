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
description: Sicherheit in Office 365, von EOP bis Defender für Office 365 Pläne 1 und 2, Standard vs. Strenge Sicherheitskonfigurationen und mehr. Verstehen Sie, was Sie haben und wie Sie Ihr Eigentum sichern können.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 29602d5fe62c84b9293522a94b71c550d360b3e3
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52877800"
---
# <a name="office-365-security-overview"></a>Überblick über Office 365 Security

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)


Dieser Artikel führt Sie in Ihre neuen Sicherheitseigenschaften in der Cloud ein. Ganz gleich, ob Sie Teil eines Sicherheitsvorgangscenters oder ein Sicherheitsadministrator sind oder ob Sie eine Auffrischung wünschen – lassen Sie uns anfangen.

> [!CAUTION]
> Wenn Sie **Outlook.com**, **Microsoft 365 Family** oder **Microsoft 365 Single** verwenden und Informationen über *Sichere Links* oder *Sichere Anlagen* benötigen, ***klicken Sie auf diesen Link***: [Erweiterte Outlook.com-Sicherheit für Abonnenten von Microsoft 365](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

## <a name="office-365-security-spelled-out"></a>Office 365 Security im Detail

Jedes Office 365-Abonnement bietet Sicherheitsfunktionen. Die Ziele und Aktionen, die Sie ausführen können, sind vom Fokus dieser verschiedenen Abonnements abhängig. In Office 365 Security gibt es drei Hauptsicherheitsdienste (oder Produkte), die an Ihren Abonnementtyp gebunden sind:

1. Exchange Online Protection (EOP)
1. Microsoft Defender für Office 365 Plan 1 (Defender für Office P1)
1. Microsoft Defender für Office 365 Plan 2 (Defender für Office P2)

> [!NOTE]
> Wenn Sie Ihr Abonnement gekauft haben und Sicherheitsfeatures *sofort* benötigen, fahren Sie mit den Schritten im Artikel [Schutz vor Bedrohungen](protect-against-threats.md) fort. Wenn Sie ein neues Abonnement haben und Ihre Lizenz wissen möchten, bevor Sie beginnen, navigieren Sie im [Microsoft 365 Admin Center](https://admin.microsoft.com/AdminPortal/#/homepage) zu Abrechnung > Ihre Produkte.

Office 365 Security baut auf den von EOP gebotenen Kernschutzfunktionen auf. EOP ist in jedem Abonnement vorhanden, in dem Exchange Online-Postfächer zu finden sind (denken Sie daran, dass alle hier behandelten Sicherheitsprodukte cloudbasierte Produkte sind).

Möglicherweise sind Sie daran gewöhnt, dass diese drei Komponenten auf dies Weise besprochen werden:

|EOP|Microsoft Defender für Office 365 P1|Microsoft Defender für Office 365 P2|
|---|---|---|
|Verhindert umfangreiche, volumebasierte, bekannte Angriffe.|Schützt E-Mails und die Zusammenarbeit vor Zero-Day-Schadsoftware, Phishing und Kompromittierung von geschäftlichen E-Mails.|Fügt Untersuchungen im Nachfeld von Sicherheitsverletzung durch, sowie die Suche und Reaktion, die Automatisierung und die Simulation (für Schulungen).|
|

Im Hinblick auf die Architektur stellen wir uns aber zunächst jedes Einzelteil als kumulierte Sicherheitsebenen vor, jede mit Betonung auf Sicherheit. Mehr dazu:

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="EOP und Microsoft Defender für Office 365 und deren Beziehungen zueinander mit Hervorhebung des Diensts, einschließlich einer Notiz zur E-Mail-Authentifizierung.":::

Obwohl jeder dieser Dienste ein Ziel aus den Bereichen "Schützen", "Erkennen", "Untersuchen" und "Antworten" hervorhebt, *können **alle** _diese Dienste _ *_jedes_** der Ziele zum Schützen, Erkennen, Untersuchen und Reagieren auf Informationen durchführen.

Das Herzstück von Office 365 Security ist der EOP-Schutz. Microsoft Defender für Office 365 P1 enthält EOP. Defender für Office 365 P2 enthält P1 und EOP. Die Struktur ist kumuliert. Deshalb sollten Sie beim Konfigurieren dieses Produkts mit EOP beginnen und sich zu Defender für Office 365 vorarbeiten.

Obwohl die Konfiguration der E-Mail-Authentifizierung in öffentlichen DNS erfolgt, ist es wichtig, dieses Feature zum Schutz vor Spoofing zu konfigurieren. *Wenn Sie über EOP verfügen,* ***sollten Sie [E-Mail-Authentifizierung konfigurieren](email-validation-and-authentication.md)***.

Wenn Sie über ein Office 365 E3 oder niedriger verfügen, haben Sie EOP, aber mit der Option, den eigenständigen Defender für Office 365 P1 durch ein Upgrade zu erwerben. Wenn Sie über Office 365 E5 verfügen, habe Sie bereits Defender für Office 365 P2.

> [!TIP]
> Wenn Ihr Abonnement weder Office 365 E3 noch E5 ist, können Sie dennoch überprüfen, ob Sie die Option zum Upgrade auf Microsoft Defender für Office 365 P1 haben. Bei Interesse finden Sie auf [dieser Webseite](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) die Abonnements, die für das Upgrade von Microsoft Defender für Office 365 P1 geeignet sind (das Kleingedruckte finden Sie am Ende der Seite).

## <a name="the-office-365-security-ladder-from-eop-to-microsoft-defender-for-office-365"></a>Die Office 365 Security-Leiter von EOP zu Microsoft Defender für Office 365

![EOP und Microsoft Defender für Office 365 und deren Sicherheitsschwerpunkte, die von "Schützen" und "Erkennen" bis „Untersuchen“ und „Antworten“ reicht. Die E-Mail-Authentifizierungskonfiguration (mindestens DKIM und DMARC) sollte für EOP und höher eingerichtet sein.](../../media/tp_EOPATPP1P2Take6.gif#lightbox)

> [!IMPORTANT]
> Details finden Sie auf diesen Seiten: [Exchange Online Protection](exchange-online-protection-overview.md) und [Defender für Office 365](defender-for-office-365.md).

Was das Hinzufügen von Microsoft Defender für Office 365 Pläne zu einem Vorteil gegenüber dem reinen EOP-Bedrohungsmanagement macht, kann auf den ersten Blick schwer zu erkennen sein. Um dabei helfen, zu erkennen, ob ein Upgradepfad für Ihre Organisation der richtige ist, wollen wir uns die Funktionen der einzelnen Produkte in Bezug auf Folgendes betrachten:

- Bedrohungen verhindern und erkennen
- untersuchen
- reagieren

beginnend mit **Exchange Online Protection**:
<p>

|Verhindern/Erkennen|Untersuchen|Reagieren|
|---|---|---|
|Technologien enthalten:<ul><li>Spam</li><li>Phishing</li><li>Schadsoftware</li><li>Massen-E-Mail</li><li>Spoofintelligenz</li><li>Identitätswechselerkennung</li><li>Administrator-Quarantäne</li><li>Administrator- und Benutzerübermittlungen von Falsch positiven und Falsch negativen Ergebnissen</li><li>Zulassen/Blockieren von URLs und Dateien</li><li>Berichte</li></u1>|<li>Überwachungsprotokollsuche</li><li>Nachrichtenablaufverfolgung</li>|<li>Automatische Bereinigung zur Nullstunde (ZAP)</li><li>Einschränkung und Tests der Listen "Zulassen" und "Blockieren"</li>|
|

Wenn Sie sich mit EOP weiter beschäftigen möchten, **[springen Sie zu diesem Artikel](exchange-online-protection-overview.md)**.

Da diese Produkte kumulativ sind, fügen Sie diese Fähigkeiten hinzu, wenn Sie Microsoft Defender für Office 365 P1 auswerten und beschließen, es zu abonnieren.

Vorteile mit **Defender für Office 365, Plan 1**:
<p>

|Verhindern/Erkennen|Untersuchen|Reagieren|
|---|---|---|
|Technologien umfassen alles in EOP, plus:<u1><li>Sichere Anlagen</li><li>Sichere Links<li>Microsoft Defender für Office 365-Schutz für Workloads (Beispiel: SharePoint Online, Teams, OneDrive for Business)</li><li>Schutz beim Klicken in E-Mails, Office-Clients und Teams</li><li>Antiphishing in Defender für Office 365</li><li>Schutz des Identitätswechsels für Benutzer und Domänen</li><li>Benachrichtigungen, und SIEM-Integrations-API für Benachrichtigungen</li>|<li>SIEM-Integrations-API für Erkennungen</li><li>**Echtzeiterkennungstool**</li><li>URL-Spur</li>|<li>Gleich</li></u1>

Microsoft Defender für Office 365 P1 erweitert also den Bereich der ***Prävention** _ und fügt zusätzliche Formen der _*_Erkennung_** hinzu.

Microsoft Defender für Office 365 P1 fügt außerdem **Erkennungen in Echtzeit** für Untersuchungen hinzu. Der Name dieses Tools zur Bedrohungssuche ist fett formatiert, da es ein *klares Indiz* dafür ist, dass Sie Defender für Office 365 P1 haben. Es wird in Defender für Office 365 P2 nicht angezeigt.

Vorteile mit **Defender für Office 365, Plan 2** (bis dato):
<p>

|Verhindern/Erkennen|Untersuchen|Reagieren|
|---|---|---|
|Technologien umfassen alles in EOP sowie Microsoft Defender für Office 365 P1, plus:<u1><li>Gleich</li>|<li>**Sicherheitsrisiken-Explorer**</li><li>Nachverfolgungslisten für Bedrohungen</li><li>Kampagnenansichten</li>|<li>Automated Investigation and Response (AIR)</li><li>AIR vom Sicherheitsrisiken-Explorer. </li><li>AIR für kompromittierte Benutzer</li><li>SIEM Integration API für Automatisierte Untersuchungen</li>

Daher wird Microsoft Defender für Office 365 P2 im Bereich ***Untersuchung und Reaktion*** erweitert und fügt eine neue Suchstärke hinzu. Automatisierung.

In Microsoft Defender für Office 365 P2 heißt das primäre Suchtool **Sicherheitsrisiken-Explorer** statt Echtzeiterkennungen. Wenn der Bedrohungs-Explorer angezeigt wird, wenn Sie zum Microsoft 365 Defender-Portal navigieren, befinden Sie sich in Microsoft Defender für Office 365 P2.

Für Details zu Microsoft Defender für Office 365 P1 und P2 anzuzeigen, **[springen Sie zu diesem Artikel](defender-for-office-365.md)**.

> [!TIP]
> EOP und Microsoft Defender für Office 365 unterscheiden sich auch in Bezug auf Endbenutzer. In EOP und Defender für Office 365 P1 liegt der Fokus auf *Bewusstsein*, und daher umfassen diese beiden Dienste das *Outlook-Add-In „Nachricht melden“*, damit Benutzer E-Mails, die sie für verdächtig halten, zur weiteren Analyse melden können. <p> In Defender für Office 365 P2 (das alles in EOP und P1 enthält) wird der Fokus auf die *weitere Schulung* für Endbenutzer verschoben. Daher hat das Security Operations Center Zugriff auf ein leistungsfähiges Tool zur *Bedrohungssimulation* sowie die hierin bereitgestellten Endbenutzermetriken.

## <a name="microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet"></a>Microsoft Defender für Office 365 Plan 1 vs. Plan 2 – Spickzettel

Diese Kurzreferenz soll Ihnen helfen zu verstehen, welche Funktionen in den einzelnen Microsoft Defender für Office 365-Abonnements enthalten sind. In Kombination mit Ihren Kenntnissen über EOP-Features können Sie Entscheidungsträgern dabei helfen zu bestimmen, welcher Microsoft Defender für Office 365 ihre Anforderungen am besten erfüllen kann.

|Microsoft Defender für Office 365 Plan 1|Microsoft Defender für Office 365 Plan 2|
|---|---|
|Konfigurations-, Schutz- und Erkennungsfunktionen: <ul><li>[Sichere Anlagen](safe-attachments.md)</li><li>[Sichere Links](safe-links.md)</li><li>[Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams](mdo-for-spo-odb-and-teams.md)</li><li>[Anti-Phishing-Schutz in Defender für Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[Echtzeiterkennungen](threat-explorer.md)</li></ul>|Defender für Office 365 Plan 1 – Funktionen <p> --- plus --- <p> Automatisierungs-, Untersuchungs-, Fehlerbehebungs- und Schulungsfunktionen: <ul><li>[Bedrohungs-Tracker](threat-trackers.md)</li><li>[Sicherheitsrisiken-Explorer](threat-explorer.md)</li><li>[Automatische Untersuchung und Reaktion](office-365-air.md)</li><li>[Angriffssimulator](attack-simulator.md)</li></ul>|
|

- Microsoft Defender für Office 365 Plan 2 ist in Office 365 E5, Office 365 A5 und Microsoft 365 E5 enthalten.

- Microsoft Defender für Office 365 Plan 1 ist in Microsoft 365 Business Premium enthalten.

- Microsoft Defender für Office 365 Plan 1 und Microsoft Defender für Office 365 Plan 2 sind jeweils als Add-On für bestimmte Abonnements verfügbar. Weitere Informationen finden Sie auch unter folgendem Link: [Verfügbarkeit von Features in Microsoft Defender für Office 365-Plänen](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

- Das Feature [Sichere Dokumente](safe-docs.md) ist nur für Benutzer mit den Lizenzen für Microsoft 365 E5 oder Microsoft 365 E5 Security verfügbar (nicht in Microsoft Defender für Office 365-Plänen enthalten).

- Wenn Ihr aktuelles Abonnement Microsoft Defender für Office 365 nicht enthält, sie es aber haben möchten [wenden Sie sich an den Vertrieb, um eine Testversion zu starten](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html) und herauszufinden, wie Microsoft Defender für Office 365 für Ihre Organisation eingesetzt werden kann.

> [!TIP]
> ***Insider-Tipp** _. Sie können das Inhaltsverzeichnis von docs.microsoft.com verwenden, um Informationen zu EOP und Microsoft Defender für Office 365 zu erhalten. Navigieren Sie zurück zu dieser Seite, [Überblick über Office 365 Security](index.yml), und Sie werden feststellen, dass die Organisation des Inhaltsverzeichnisses in der Seitenleiste. Es beginnt mit der Bereitstellung (einschließlich Migration) und setzt sich dann mit Prävention, Erkennung, Untersuchung und Reaktion fort. <p> Diese Struktur ist unterteilt, sodass Themen zur _ *Sicherheitsverwaltung* gefolgt sind von Themen zu **Sicherheitsvorgänge**. Wenn Sie ein neues Mitglied einer der Jobrollen sind, verwenden Sie den Link in diesem Tipp und Ihre Kenntnisse zum Inhaltsverzeichnis, um den Bereich kennenzulernen. Denken Sie daran, im Verlauf *Feedbacklinks* zu verwenden und *Artikel zu bewerten*. Feedback hilft uns bei der Verbesserung des Angebots, das wir Ihnen bieten.

## <a name="where-to-go-next"></a>Nächste Schritte

Wenn Sie ein Sicherheitsadministrator sind, müssen Sie möglicherweise DKIM oder DMARC für Ihre E-Mails konfigurieren. Möglicherweise möchten Sie für Ihre Prioritätsbenutzer "Strenge" Sicherheitseinstellungen anwenden oder sehen, was beim Produkt neu ist. Oder wenn Sie im Bereich Security Ops tätig sind, möchten Sie vielleicht Echtzeit-Erkennungen oder den Sicherheitsrisiken-Explorer nutzen, um zu untersuchen und zu reagieren, oder die Erkennung durch Endbenutzer mit dem Angriffssimulator trainieren. In beiden Fällen finden Sie hier einige zusätzliche Empfehlungen, für das, was Sie sich als Nächstes ansehen sollten.

[E-Mail-Authentifizierung, einschließlich SPF, DKIM und DMARC (mit Links zum Setup aller drei)](email-validation-and-authentication.md)

[Lesen Sie die speziellen empfohlenen "goldenen" Konfigurationen](recommended-settings-for-eop-and-office365.md) und [verwenden Sie ihre empfohlenen Voreinstellungen, um Sicherheitsrichtlinien schnell zu konfigurieren.](preset-security-policies.md)

Informieren Sie sich [, was es Neues in Microsoft Defender für Office 365 gibt (einschließlich EOP-Entwicklungen)](whats-new-in-defender-for-office-365.md)

[Verwenden Sie den Sicherheitsrisiken-Explorer oder Echtzeit-Erkennung](threat-explorer.md)

Verwenden Sie den [Angriffssimulator in Microsoft Defender für Office 365](attack-simulator.md)