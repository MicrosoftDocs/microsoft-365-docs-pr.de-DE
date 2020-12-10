---
title: Office 365 Sicherheit, Microsoft Defender für Office 365, EoP, MSDO
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
- M365-security-compliance
- m365initiative-m365-defender
description: Sicherheit in Office 365, vom EoP zum Verteidiger für Office 365 Pläne 1 und 2, Standard mäßige und strenge Sicherheitskonfigurationen und vieles mehr. Verstehen Sie, was Sie haben und wie Sie Ihre Eigenschaften sichern.
ms.openlocfilehash: 84d7dcfc68ce78bfde92f3d7096cd4104355ce94
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616248"
---
# <a name="office-365-security-overview"></a>Office 365 Sicherheit (Übersicht)

In diesem Artikel werden die neuen Sicherheitseigenschaften in der Cloud vorgestellt. Unabhängig davon, ob Sie Teil eines Security Operations Centers sind, Sie sind ein Sicherheits Administrator, der neu in diesem Bereich ist, oder wenn Sie eine Aktualisierung wünschen, Let es Get Started.

> [!CAUTION]
> Wenn Sie **Outlook.com**, **Microsoft 365-Familie** oder **Microsoft 365 Personal** verwenden und *sichere Links* oder Informationen zu *sicheren Anlagen* benötigen, ***Klicken Sie auf diesen Link** _: [Erweiterte Outlook.com-Sicherheit für Microsoft 365-Abonnenten](https://support.microsoft.com/office/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).

## <a name="office-365-security-spelled-out"></a>Office 365 Sicherheit geschrieben

Jedes Office 365 Abonnement verfügt über Sicherheitsfunktionen. Die Ziele und Aktionen, die Sie ausführen können, hängen vom Fokus dieser unterschiedlichen Abonnements ab. In Office 365 Sicherheit gibt es drei wichtige Sicherheitsdienste (oder Produkte), die mit Ihrem Abonnementtyp verbunden sind:

1. Exchange Online Schutz (EoP)
1. Microsoft Defender für Office 365 Plan 1 (Defender for Office P1)
1. Microsoft Defender für Office 365 Plan 2 (Defender for Office P2)

> [!NOTE]
> Wenn Sie Ihr Abonnement erworben haben und Sicherheitsfeatures _Right jetzt * bereitstellen müssen, wechseln Sie zu den Schritten im Artikel [Protect Against Threats](protect-against-threats.md) . Wenn Sie noch nicht mit Ihrem Abonnement vertraut sind und Ihre Lizenz vor dem Start wissen möchten, suchen Sie in der [Microsoft 365 Admin Center](https://admin.microsoft.com/AdminPortal/#/homepage)die Abrechnung > Ihre Produkte.

Office 365 Sicherheit basiert auf den von EoP angebotenen kernschutz Funktionen. EoP ist in jedem Abonnement vorhanden, in dem Exchange Online Postfächer gefunden werden können (denken Sie daran, dass alle hier besprochenen Sicherheitsprodukte auf der Cloud basieren).

Möglicherweise sind Sie daran gewöhnt, dass diese drei Komponenten auf diese Weise behandelt werden:

|EOP|Microsoft Defender für Office 365 P1|Microsoft Defender für Office 365 P2|
|---|---|---|
|Verhindert allgemeine, volumenbasierte, bekannte Angriffe.|Schützt e-Mails und die Zusammenarbeit von Zero-Day-Malware, Phishing und geschäftlichen e-Mail-Kompromissen.|Hinzufügen von Untersuchungen, Jagden und Antworten nach einem Verstoß sowie Automatisierung und Simulation (für Schulungen).|
|

Aber im Hinblick auf die Architektur, beginnen wir mit dem Gedanken an jedes Stück als kumulative Schichten von Sicherheit, die jeweils mit einem Sicherheits Schwerpunkt. Mehr wie folgt aus:

<!--:::image type="content" source="../../media/tp-EOPATPStack.PNG" alt-text="Placeholder graphic":::-->

:::image type="content" source="../../media/tp_GraphicEOPATPP1P2_2.png" alt-text="EoP und Microsoft Defender für Office 365 und ihre Beziehungen miteinander mit Schwerpunkt auf Dienstleistung, einschließlich einer Notiz für die e-Mail-Authentifizierung.":::

Obwohl jeder dieser Dienste ein Ziel unter schützen, erkennen, untersuchen und Antworten hervorhebt, können die Dienste **alle Ziele** _*_des Schutzes_*_ , Erkennens, Ermittelns und Reagierens erfüllen.

Der Kern Office 365 Sicherheit besteht in EoP Schutz. Microsoft Defender für Office 365 P1 enthält EoP. Defender für Office 365 P2 enthält P1 und EOP. Die Struktur ist kumulativ. Deshalb sollten Sie bei der Konfiguration dieses Produkts mit EoP beginnen und für Office 365 auf Defender arbeiten.

Obwohl die e-Mail-Authentifizierungskonfiguration im öffentlichen DNS erfolgt, ist es wichtig, dieses Feature zu konfigurieren, um die Verteidigung vor Spoofing zu unterstützen. _Wenn Sie über EoP verfügen,**sollten Sie die [e-Mail-Authentifizierung konfigurieren](email-validation-and-authentication.md)**_.

Wenn Sie über eine Office 365 E3 oder darunter verfügen, verfügen Sie über EoP, jedoch mit der Option zum erwerben von eigenständigem Defender für Office 365 P1 durch ein Upgrade. Wenn Sie Office 365 E5 haben, haben Sie bereits Defender für Office 365 P2.

> [!TIP]
> Wenn Ihr Abonnement weder Office 365 E3 noch E5 ist, können Sie weiterhin überprüfen, ob Sie die Option haben, ein Upgrade auf Microsoft Defender für Office 365 P1 vorzusehen. Wenn Sie Interesse haben, werden auf [dieser Webseite](https://www.microsoft.com/microsoft-365/exchange/advance-threat-protection#coreui-contentrichblock-x07wids) Abonnements aufgeführt, die für Microsoft Defender für Office 365 P1-Upgrade berechtigt sind (überprüfen Sie das Ende der Seite für den fein Druck).

## <a name="the-office-365-security-ladder-from-eop-to-microsoft-defender-for-office-365"></a>Die Office 365 Security Ladder von EoP zu Microsoft Defender für Office 365

![EoP und Microsoft Defender für Office 365 und Ihre Sicherheits Schwerpunkte, die von Protect und Detect zur Untersuchung und Reaktion abgehen. Die e-Mail-Authentifizierungskonfiguration (mindestens DKIM und DMARC) sollte für EoP und up eingerichtet werden.](../../media/tp_EOPATPP1P2Take6.gif#lightbox)

> [!IMPORTANT]
> Lesen Sie die Details auf diesen Seiten: [Exchange Online Schutz](exchange-online-protection-overview.md)und [Verteidiger für Office 365](office-365-atp.md).

Was das Hinzufügen von Microsoft Defender für Office 365 Pläne einen Vorteil für pure EoP Threat Management bietet, kann auf den ersten Blick schwer zu erkennen sein. Um zu helfen, zu klären, ob ein Upgrade-Pfad für Ihre Organisation richtig ist, sehen wir uns die Funktionen der einzelnen Produkte an, wenn es um Folgendes geht:

- verhindern und erkennen von Bedrohungen
- untersuchen
- reagiert

beginnend mit _ * Exchange Online Protection * *:
<p>

|Verhindern/erkennen|Untersuchen|Reagieren|
|---|---|---|
|Zu den Technologien gehören:<ul><li>Spam</li><li>phishingfilterrichtlinie</li><li>Schadsoftware</li><li>Massen-e-Mail</li><li>Spoof Intelligence</li><li>Identitätswechsel Erkennung</li><li>Administrator Quarantäne</li><li>Administrator-und Benutzerübermittlungen falsch positiver und falsch negativer Ergebnisse</li><li>Allow/Block für URLs und Dateien</li><li>Berichte</li></u1>|<li>Durchsuchen von Überwachungsprotokollen</li><li>Nachrichtenablaufverfolgung</li>|<li>Automatische Bereinigung ohne Stunden (zap)</li><li>Einschränkung und Testen von Zulassungs-und Sperrlisten</li>|
|

Wenn Sie in EoP graben möchten, wechseln Sie **[zu diesem Artikel](exchange-online-protection-overview.md)**.

Da diese Produkte kumulativ sind, wenn Sie Microsoft Defender für Office 365 P1 bewerten und beschließen, es zu abonnieren, fügen Sie diese Fähigkeiten hinzu.

Gewinne mit **Defender für Office 365, Plan 1** (bis Datum):
<p>

|Verhindern/erkennen|Untersuchen|Reagieren|
|---|---|---|
|Technologien umfassen alles in EoP Plus:<u1><li>Sichere Anlagen</li><li>Sichere Links<li>Microsoft Defender für Office 365 Schutz für Arbeitslasten (z. b. SharePoint Online, Teams, OneDrive für Unternehmen)</li><li>Zeit-zu-Klick-Schutz in e-Mails, Office-Clients und Teams</li><li>Anti-Phishing in Defender für Office 365</li><li>Schutz von Benutzer-und Domänen Identitätswechsel</li><li>Warnungen und die Siem-Integrations-API für Warnungen</li>|<li>Siem-Integrations-API für Erkennungen</li><li>**Echt Zeit Erkennungstool**</li><li>URL-Ablaufverfolgung</li>|<li>Gleich</li></u1>

Microsoft Defender für Office 365 P1 erweitert also die Seite "**_Prevention_* _" des Hauses und fügt zusätzliche _*_Erkennungs_*_ Formen hinzu.

Microsoft Defender für Office 365 P1 fügt außerdem _ *Echt Zeit Erkennungen** für Untersuchungen hinzu. Dieser Name des Threat Hunting-Tools ist fett formatiert, da es eindeutig ist, *dass Sie Defender* für Office 365 P1 haben. Es wird nicht in Defender für Office 365 P2 angezeigt.

Gewinne mit **Defender für Office 365, Plan 2** (bis Datum):
<p>

|Verhindern/erkennen|Untersuchen|Reagieren|
|---|---|---|
|Technologien umfassen alles in EoP und Microsoft Defender für Office 365 P1 Plus:<u1><li>Gleich</li>|<li>**Sicherheitsrisiken-Explorer**</li><li>Nachverfolgungslisten für Bedrohungen</li><li>Kampagnen Ansichten</li>|<li>Automatische Untersuchung und Reaktion (Air)</li><li>Air from Threat Explorer</li><li>Air für kompromittierte Benutzer</li><li>Siem-Integrations-API für automatisierte Untersuchungen</li>

Microsoft Defender für Office 365 P2 erweitert also die **_Untersuchung und Antwort_* _ Seite des Hauses und fügt eine neue Jagd Stärke hinzu. Automatisierung.

In Microsoft Defender für Office 365 P2 wird das primäre Jagd Tool _ *Threat Explorer** anstatt Echt Zeit Erkennungen genannt. Wenn Sie Threat Explorer beim Navigieren zum Sicherheitscenter sehen, befinden Sie sich in Microsoft Defender für Office 365 P2.

Wenn Sie die Details von Microsoft Defender für Office 365 P1 und P2 erhalten möchten, **[wechseln Sie zu diesem Artikel](office-365-atp.md)**.

> [!TIP]
> EoP und Microsoft Defender für Office 365 sind auch unterschiedlich, wenn es um Endbenutzer geht. In EoP und Defender für Office 365 P1 liegt der Schwerpunkt auf dem *Bewusstsein*, und daher umfassen diese beiden Dienste das *Outlook-Add-in "Berichtsnachricht* ", damit Benutzer e-Mails, die Sie verdächtig finden, zur weiteren Analyse melden können. <p> In Defender für Office 365 P2 (das alles in EoP und P1 enthält) wird der Fokus auf die *Weiterbildung* für Endbenutzer verschoben, und so hat das Security Operations Center Zugriff auf ein leistungsfähiges *Threat Simulator* -Tool und die von ihm bereitgestellten Endbenutzer Metriken.

## <a name="microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet"></a>Microsoft Defender für Office 365 Plan 1 vs. Plan 2 Cheat Sheet

Diese Schnellreferenz hilft Ihnen zu verstehen, welche Funktionen mit jedem Microsoft Defender für Office 365 Abonnement geliefert werden. In Kombination mit ihren Kenntnissen über EoP-Funktionen kann es Entscheidungsträgern in Unternehmen helfen, festzulegen, was Microsoft Defender für Office 365 am besten für Ihre Anforderungen ist.

|Verteidiger für Office 365 Plan 1|Verteidiger für Office 365 Plan 2|
|---|---|
|Konfigurations-, Schutz- und Erkennungsfunktionen: <ul><li>[Sichere Anlagen](atp-safe-attachments.md)</li><li>[Sichere Links](atp-safe-links.md)</li><li>[ATP für SharePoint, OneDrive und Microsoft Teams](atp-for-spo-odb-and-teams.md)</li><li>[Anti-Phishing-Schutz in Defender für Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[Echtzeiterkennungen](threat-explorer.md)</li></ul>|Verteidiger für Office 365-Plan 1-Funktionen <p> --- plus --- <p> Automatisierungs-, Untersuchungs-, Fehlerbehebungs- und Schulungsfunktionen: <ul><li>[Bedrohungs-Tracker](threat-trackers.md)</li><li>[Sicherheitsrisiken-Explorer](threat-explorer.md)</li><li>[Automatische Untersuchung und Reaktion](office-365-air.md)</li><li>[Angriffssimulator](attack-simulator.md)</li></ul>|
|

- Microsoft Defender für Office 365 Plan 2 ist in Office 365 E5, Office 365 a5 und Microsoft 365 E5 enthalten.

- Microsoft Defender für Office 365 Plan 1 ist in Microsoft 365 Business Premium enthalten.

- Microsoft Defender für Office 365 Plan 1 und Defender für Office 365 Plan 2 sind jeweils als Add-on für bestimmte Abonnements verfügbar. Weitere Informationen finden Sie hier: eine weitere Link [Feature-Verfügbarkeit in Microsoft Defender für Office 365 Pläne](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).

- Das Feature " [sichere Dokumente](safe-docs.md) " steht nur Benutzern mit den Sicherheits Lizenzen von Microsoft 365 E5 oder Microsoft 365 E5 zur Verfügung (nicht in Microsoft Defender für Office 365 Pläne enthalten).

- Wenn Ihr aktuelles Abonnement nicht Microsoft Defender für Office 365 enthält und Sie es möchten, wenden Sie sich [an den Vertrieb, um eine Testversion zu starten](https://go.microsoft.com/fwlink/p/?LinkId=518644), und erfahren Sie, wie Microsoft Defender für Office 365 in Ihrer Organisation arbeiten kann.

> [!TIP]
> ***Insider Tipp** _. Sie können das docs.Microsoft.com-Inhaltsverzeichnis verwenden, um mehr über EoP und Microsoft Defender für Office 365 zu erfahren. Navigieren Sie zurück zu dieser Seite, [Office 365 Übersicht über die Sicherheit](https://docs.microsoft.com/microsoft-365/security/office-365-security), und Sie werden feststellen, dass die Inhaltsverzeichnis-Organisation in der Seitenleiste angezeigt wird. Er beginnt mit der Bereitstellung (einschließlich Migration) und wird dann in die Prävention, Erkennung, Untersuchung und Reaktion fortgesetzt. <p> Diese Struktur ist so unterteilt, dass _ *Security Administration** Themen von **Sicherheits-Operations** Themen gefolgt werden. Wenn Sie ein neues Mitglied einer der beiden Auftrags Rollen sind, verwenden Sie den Link in diesem Tipp und Ihr Wissen über das Inhaltsverzeichnis, um den Raum zu erlernen. Denken Sie daran, *Feedback Links* zu verwenden und die *Artikel bewerten* , wie Sie gehen. Feedback hilft uns, das zu verbessern, was wir Ihnen bieten.

## <a name="where-to-go-next"></a>Weiter zu wechseln

Wenn Sie ein Sicherheitsadministrator sind, müssen Sie möglicherweise DKIM oder DMARC für Ihre e-Mails konfigurieren. Möglicherweise möchten Sie "strenge" Sicherheitsvoreinstellungen für Ihre Prioritäts Benutzer bereitstellen oder nach neuen Funktionen im Produkt suchen. Oder wenn Sie mit Security OPS arbeiten, können Sie Echt Zeit Erkennungen oder Threat Explorer nutzen, um zu untersuchen und zu reagieren oder die Endbenutzer Erkennung mit dem Angriffs Simulator zu trainieren. Wie dem auch sei, hier sind einige zusätzliche Empfehlungen dafür, was Sie als nächstes sehen sollten.

[E-Mail-Authentifizierung, einschließlich SPF, DKIM und DMARC (mit Links zum Setup aller drei)](email-validation-and-authentication.md)

[Lesen Sie die speziellen empfohlenen "goldenen" configs](recommended-settings-for-eop-and-office365-atp.md) , und verwenden Sie die [empfohlenen Voreinstellungen, um Sicherheitsrichtlinien schnell zu konfigurieren](preset-security-policies.md) .

Informieren Sie sich über Neuigkeiten [in Microsoft Defender für Office 365 (einschließlich EoP-Entwicklungen)](whats-new-in-office-365-atp.md) .

[Verwenden von Threat Explorer oder Echtzeiterkennung](threat-explorer.md)

Verwenden des [Angriffs Simulators in Microsoft Defender für Office 365](attack-simulator.md)
