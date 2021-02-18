---
title: Office 365 Security, Microsoft Defender für Office 365, EOP, MSDO
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 08/13/2020
audience: Admin
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Sicherheit in Office 365, von EOP zu Defender für Office 365 Pläne 1 und 2, Standard- und strenge Sicherheitskonfigurationen und vieles mehr. Verstehen Sie, was Sie haben, und wie Sie Ihre Eigenschaften schützen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cbe95946ab7214efded8feca39578c364b948df0
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287901"
---
# <a name="office-365-security-overview"></a>Office 365 Security Overview

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)


Dieser Artikel führt Sie in Ihre neuen Sicherheitseigenschaften in der Cloud ein. Ganz gleich, ob Sie Teil eines Security Operations Centers sind, ein Sicherheitsadministrator sind, der neu in diesem Bereich ist, oder ob Sie eine Auffrischung wünschen, beginnen wir.

> [!CAUTION]
> Wenn Sie **Outlook.com,** Microsoft **365 Family** oder **Microsoft 365 Personal**  verwenden und  Informationen zu sicheren Links oder sicheren Anlagen ***benötigen,*** klicken Sie auf diesen Link : Advanced Outlook.com Security für [Microsoft 365-Abonnenten.](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)

## <a name="office-365-security-spelled-out"></a>Office 365-Sicherheit mit Schreibschutz

Jedes Office 365-Abonnement verfügt über Sicherheitsfunktionen. Welche Ziele und Aktionen Sie ausführen können, hängt vom Fokus dieser verschiedenen Abonnements ab. In Der Office 365-Sicherheit gibt es drei wichtige Sicherheitsdienste (oder -produkte), die an Ihren Abonnementtyp gebunden sind:

1. Exchange Online Protection (EOP)
1. Microsoft Defender für Office 365 Plan 1 (Defender für Office P1)
1. Microsoft Defender für Office 365 Plan 2 (Defender für Office P2)

> [!NOTE]
> Wenn Sie Ihr Abonnement gekauft haben und sicherheitsfeatures sofort rollouten *müssen,* fahren Sie mit den Schritten im Artikel zum Schutz [vor Bedrohungen](protect-against-threats.md) um. If you're new to your subscription and would like to know your license before you begin, browse Billing > Your Products in the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal/#/homepage).

Die Sicherheit von Office 365 basiert auf den wichtigsten Schutzmaßnahmen von EOP. EOP ist in jedem Abonnement vorhanden, in dem Exchange Online-Postfächer zu finden sind (denken Sie daran, dass alle hier erläuterten Sicherheitsprodukte cloudbasierte Produkte sind).

Möglicherweise sind Sie es gewohnt, diese drei Komponenten auf diese Weise zu diskutieren:

|EOP|Microsoft Defender für Office 365 P1|Microsoft Defender für Office 365 P2|
|---|---|---|
|Verhindert umfassende, volumebasierte, bekannte Angriffe.|Schützt E-Mails und die Zusammenarbeit vor Zero-Day-Schadsoftware, Phishing und geschäftlichen E-Mail-Angriffen.|Fügt Untersuchung, Suche und Reaktion nach der Verletzung sowie Automatisierung und Simulation (für Schulungen) hinzu.|
|

Doch im Hinblick auf die Architektur betrachten wir zunächst jeden Teil als kumulative Sicherheitsebenen, die jeweils einen Schwerpunkt auf der Sicherheit haben. Weitere Informationen finden Sie hier:

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="EOP und Microsoft Defender für Office 365 und ihre Beziehungen miteinander mit Schwerpunkt auf dem Dienst, einschließlich eines Hinweises für die E-Mail-Authentifizierung.":::

Obwohl jeder dieser Dienste ein Ziel von "Protect", "Detect", "Investigate" und "Respond" unterstreicht,***** können alle *_Dienste_* _ beliebige * der Ziele des Schützens, Erkennens, Untersuchens und Reagierens durchführen.

Der Kern der Office 365-Sicherheit ist der EOP-Schutz. Microsoft Defender für Office 365 P1 enthält EOP. Defender für Office 365 P2 enthält P1 und EOP. Die Struktur ist kumulativ. Deshalb sollten Sie beim Konfigurieren dieses Produkts mit EOP beginnen und mit Defender für Office 365 arbeiten.

Obwohl die E-Mail-Authentifizierungskonfiguration im öffentlichen DNS erfolgt, ist es wichtig, dieses Feature zur Verteidigung vor Spoofing zu konfigurieren. *Wenn Sie über EOP verfügen,* ***sollten Sie die [E-Mail-Authentifizierung konfigurieren.](email-validation-and-authentication.md)***

Wenn Sie über Office 365 E3 oder darunter verfügen, verfügen Sie über EOP, aber mit der Option, eigenständigen Defender für Office 365 P1 über ein Upgrade zu erwerben. Wenn Sie office 365 E5 haben, verfügen Sie bereits über Defender für Office 365 P2.

> [!TIP]
> Wenn Ihr Abonnement weder Office 365 E3 noch E5 ist, können Sie weiterhin überprüfen, ob Sie die Option zum Upgrade auf Microsoft Defender für Office 365 P1 haben. Wenn Sie daran interessiert [sind,](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) werden auf dieser Webseite Abonnements aufgeführt, die für das Upgrade von Microsoft Defender für Office 365 P1 berechtigt sind (überprüfen Sie das Ende der Seite auf das Fine print).

## <a name="the-office-365-security-ladder-from-eop-to-microsoft-defender-for-office-365"></a>Die Sicherheit von Office 365 von EOP zu Microsoft Defender für Office 365

![EOP und Microsoft Defender für Office 365 und ihre Sicherheitsbeosichtung, von "Schützen und erkennen" bis hin zu "Untersuchen und Reagieren". Die E-Mail-Authentifizierungskonfiguration (mindestens DKIM und DMARC) sollte für EOP und EOP eingerichtet werden.](../../media/tp_EOPATPP1P2Take6.gif#lightbox)

> [!IMPORTANT]
> Erfahren Sie mehr über die Details auf diesen Seiten: [Exchange Online Protection](exchange-online-protection-overview.md)und Defender für Office [365](office-365-atp.md).

Was das Hinzufügen von Microsoft Defender für Office 365-Plänen zu einem Vorteil des reinen EOP-Bedrohungsmanagements macht, ist auf den ersten Blick schwer zu erkennen. Um zu sortieren, ob ein Upgradepfad für Ihre Organisation richtig ist, sehen wir uns die Funktionen der einzelnen Produkte an, wenn es um:

- Verhindern und Erkennen von Bedrohungen
- investigating
- Reagieren

beginnend mit **Exchange Online Protection:**
<p>

|Verhindern/Erkennen|Untersuchen|Reagieren|
|---|---|---|
|Zu den Technologien gehören:<ul><li>Spam</li><li>Phish</li><li>Schadsoftware</li><li>Massen-E-Mail</li><li>Spoofintelligenz</li><li>Identitätswechselerkennung</li><li>Administratorquarantäne</li><li>Administrator- und Benutzerübermittlungen von falsch positiven und falsch negativen Ergebnisse</li><li>Zulassen/Blockieren für URLs und Dateien</li><li>Berichte</li></u1>|<li>Durchsuchen von Überwachungsprotokollen</li><li>Nachrichtenablaufverfolgung</li>|<li>Automatische Bereinigung zur Nullstunde (ZAP)</li><li>Einschränkung und Tests von Listen "Zulassen" und "Blockieren"</li>|
|

Wenn Sie sich in EOP einmächst, **[wechseln Sie zu diesem Artikel.](exchange-online-protection-overview.md)**

Da diese Produkte kumulativ sind, fügen Sie diese Fähigkeiten hinzu, wenn Sie Microsoft Defender für Office 365 P1 bewerten und sich dafür entscheiden, es zu abonnieren.

Vorteile mit **Defender für Office 365, Plan 1** (bis heute):
<p>

|Verhindern/Erkennen|Untersuchen|Reagieren|
|---|---|---|
|Zu den Technologien gehören alles in EOP sowie:<u1><li>Sichere Anlagen</li><li>Sichere Links<li>Microsoft Defender für Office 365-Schutz für Workloads (z. B. SharePoint Online, Teams, OneDrive for Business)</li><li>Time-of-Click-Schutz in E-Mails, Office-Clients und Teams</li><li>Antiphishing in Defender für Office 365</li><li>Schutz vor Identitätswechsel für Benutzer und Domäne</li><li>Warnungen und SIEM-Integrations-API für Warnungen</li>|<li>SIEM-Integrations-API für Erkennungen</li><li>**Tool zur Erkennung in Echtzeit**</li><li>URL-Ablaufverfolgung</li>|<li>Gleich</li></u1>

Microsoft Defender für Office 365 P1 erweitert sich also auf der Seite ***Prevention** _ des Hauses und fügt zusätzliche Formen der _*-Erkennung **hinzu.

Microsoft Defender für Office 365 P1 fügt außerdem **Echtzeiterkennungen für** Untersuchungen hinzu. Der Name dieses Tools für die Bedrohungssuche ist  fett formatiert, da klar ist, dass Sie Defender für Office 365 P1 verwenden. Sie wird in Defender für Office 365 P2 nicht angezeigt.

Vorteile mit **Defender für Office 365, Plan 2** (bis heute):
<p>

|Verhindern/Erkennen|Untersuchen|Reagieren|
|---|---|---|
|Zu den Technologien gehören alles in EOP und Microsoft Defender für Office 365 P1 plus:<u1><li>Gleich</li>|<li>**Sicherheitsrisiken-Explorer**</li><li>Nachverfolgungslisten für Bedrohungen</li><li>Kampagnenansichten</li>|<li>Automatisierte Untersuchung und Reaktion (AIR)</li><li>AIR aus Dem Bedrohungs-Explorer</li><li>AIR für gefährdete Benutzer</li><li>SIEM-Integrations-API für automatisierte Untersuchungen</li>

Microsoft Defender für Office 365 P2  erweitert daher die Untersuchungs- und Reaktionsseite des Haus und fügt eine neue Stärke für die Suche hinzu. Automatisierung.

In Microsoft Defender für Office 365 P2  wird das primäre Tool als Bedrohungs-Explorer und nicht als Echtzeiterkennung bezeichnet. Wenn der Bedrohungs-Explorer angezeigt wird, wenn Sie zum Security Center navigieren, sind Sie in Microsoft Defender für Office 365 P2.

Weitere Informationen zu Microsoft Defender für Office 365 P1 und P2 finden Sie **[in diesem Artikel.](office-365-atp.md)**

> [!TIP]
> EOP und Microsoft Defender für Office 365 unterscheiden sich auch bei Endbenutzern. In EOP und Defender für Office 365 P1 liegt der Fokus auf dem *Bewusstsein,* sodass diese beiden Dienste das *Outlook-Add-In* "Nachricht melden" enthalten, damit Benutzer verdächtige E-Mails zur weiteren Analyse melden können. <p> In Defender für Office 365 P2 (das alles in EOP  und P1 enthält) liegt der Fokus auf weiteren  Schulungen für Endbenutzer, sodass das Security Operations Center Zugriff auf ein leistungsfähiges Bedrohungssimulatortool und die von ihr zur Verfügung stellten Endbenutzermetriken hat.

## <a name="microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet"></a>Microsoft Defender für Office 365 Plan 1 und Plan 2

Diese Kurzübersicht hilft Ihnen zu verstehen, welche Funktionen in jedem Microsoft Defender für Office 365-Abonnement enthalten sind. In Kombination mit Ihren Kenntnissen über die Features von EOP kann dies geschäftliche Entscheidungsträger dabei unterstützen, zu bestimmen, was Microsoft Defender für Office 365 für ihre Anforderungen am besten ist.

|Defender für Office 365 Plan 1|Defender für Office 365 Plan 2|
|---|---|
|Konfigurations-, Schutz- und Erkennungsfunktionen: <ul><li>[Sichere Anlagen](atp-safe-attachments.md)</li><li>[Sichere Links](atp-safe-links.md)</li><li>[Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams](atp-for-spo-odb-and-teams.md)</li><li>[Antiphishingschutz in Defender für Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[Echtzeiterkennungen](threat-explorer.md)</li></ul>|Funktionen von Defender für Office 365 Plan 1 <p> --- plus --- <p> Automatisierungs-, Untersuchungs-, Fehlerbehebungs- und Schulungsfunktionen: <ul><li>[Bedrohungs-Tracker](threat-trackers.md)</li><li>[Sicherheitsrisiken-Explorer](threat-explorer.md)</li><li>[Automatische Untersuchung und Reaktion](office-365-air.md)</li><li>[Angriffssimulator](attack-simulator.md)</li></ul>|
|

- Microsoft Defender für Office 365 Plan 2 ist in Office 365 E5, Office 365 A5 und Microsoft 365 E5 enthalten.

- Microsoft Defender für Office 365 Plan 1 ist in Microsoft 365 Business Premium enthalten.

- Microsoft Defender für Office 365 Plan 1 und Defender für Office 365 Plan 2 sind jeweils als Add-On für bestimmte Abonnements verfügbar. Weitere Informationen finden Sie hier eine weitere [Link-Featureverfügbarkeit in Microsoft Defender für Office 365-Plänen.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)

- Das Feature [Sichere Dokumente](safe-docs.md) ist nur für Benutzer mit den Lizenzen für Microsoft 365 E5 oder Microsoft 365 E5 Security verfügbar (nicht in Microsoft Defender für Office 365-Plänen enthalten).

- Wenn Ihr aktuelles Abonnement Microsoft Defender für Office 365 nicht enthält und Sie es [wünschen,](https://info.microsoft.com/ww-landing-M365SMB-web-contact.html)wenden Sie sich an den Vertrieb, um eine Testversion zu starten, und erfahren Sie, wie Microsoft Defender für Office 365 in Ihrer Organisation funktionieren kann.

> [!TIP]
> ***Insidertipp** _. Sie können das docs.microsoft.com Inhaltsverzeichnis verwenden, um mehr über EOP und Microsoft Defender für Office 365 zu erfahren. Navigieren Sie zurück zu dieser Seite, [Office 365-Sicherheitsübersicht,](index.md)und Sie werden feststellen, dass das Inhaltsverzeichnis in der Seitenleiste angezeigt wird. Sie beginnt mit der Bereitstellung (einschließlich Der Migration) und setzt sich dann mit der Verhinderung, Erkennung, Untersuchung und Reaktion fort. <p> Diese Struktur ist so unterteilt, dass den Themen zur *_Sicherheitsverwaltung** Themen zu **Sicherheitsvorgängen folgen.** Wenn Sie ein neues Mitglied einer der Beiden Stellen sind, verwenden Sie den Link in diesem Tipp und Ihre Kenntnisse des Inhaltsverzeichnisses, um den Bereich zu erlernen. Denken Sie daran, *feedbacklinks zu verwenden* *und Artikel zu bewerten.* Feedback hilft uns, das zu verbessern, was wir Ihnen anbieten.

## <a name="where-to-go-next"></a>Where to go next

Wenn Sie ein Sicherheitsadministrator sind, müssen Sie möglicherweise DKIM oder DMARC für Ihre E-Mails konfigurieren. Möglicherweise möchten Sie "Strikte" Sicherheitsvoreinstellungen für Ihre Prioritätsbenutzer verwenden oder nach Neuen im Produkt suchen. Oder wenn Sie mit Sicherheits-Ops zusammenarbeiten, können Sie Echtzeiterkennungen oder den Bedrohungs-Explorer nutzen, um die Erkennung von Endbenutzern mit dem Angriffssimulator zu untersuchen und zu beantworten oder sie zu schulen. In beiden Fällen finden Sie hier einige zusätzliche Empfehlungen für die nächsten Schritte.

[E-Mail-Authentifizierung, einschließlich SPF, DKIM und DMARC (mit Links zum Einrichten aller drei)](email-validation-and-authentication.md)

[Sehen Sie sich die spezifischen empfohlenen "goldenen" Konfigurationen](recommended-settings-for-eop-and-office365-atp.md) an, und verwenden Sie die empfohlenen Voreinstellungen, um [Sicherheitsrichtlinien schnell zu konfigurieren.](preset-security-policies.md)

Informieren Sie sich [über die Neuen in Microsoft Defender für Office 365 (einschließlich EOP-Entwicklungen)](whats-new-in-office-365-atp.md)

[Verwenden von Threat Explorer oder Echtzeiterkennungen](threat-explorer.md)

Verwenden [des Angriffssimulators in Microsoft Defender für Office 365](attack-simulator.md)
