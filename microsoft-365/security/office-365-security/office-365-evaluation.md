---
title: Auswerten von Microsoft Defender für Office 365
description: Defender für Office 365 im Evaluierungsmodus erstellt Defender für Office 365 e-Mail-Richtlinien, die Urteile wie Schadsoftware protokollieren, jedoch nicht auf Nachrichten reagieren.
keywords: Auswerten von Office 365, Microsoft Defender für Office 365, Office 365 Evaluation, Testen von Office 365, Microsoft Defender, ATP
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b5b095a1d75ead0f963a71d816e7d879b7cd3697
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49614798"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a>Auswerten von Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Bewerten Sie Microsoft Defender für Office 365 bald in der öffentlichen Vorschau angezeigt werden. Diese Vorschauversion wird ohne Vereinbarung zum Service Level bereitgestellt. Bestimmte Features werden möglicherweise nicht unterstützt oder verfügen möglicherweise über eingeschränkte Funktionen.

Durch die Durchführung einer umfassenden Sicherheitsprodukt Bewertung können Sie fundierte Entscheidungen zu Upgrades und Käufen treffen. Es hilft, die Funktionen des Sicherheitsprodukts auszuprobieren, um zu bewerten, wie das Sicherheits Betriebsteam bei seinen täglichen Aufgaben helfen kann.

Der [Microsoft Defender für Office 365](office-365-atp.md) Evaluierungs Erfahrung wurde entwickelt, um die Komplexität der Konfiguration von Geräten und Umgebungen zu eliminieren, damit Sie sich auf die Bewertung der Funktionen der Sicherheitslösung konzentrieren können. Dies gilt nur für e-Mail-Schutz und nicht für SharePoint, Office-Clients oder Teams.

Wenn Sie noch nicht über eine Lizenz verfügen, die Microsoft Defender für Office 365 unterstützt, können Sie eine [﻿Kostenlose 30-tägige Testversion](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) starten und die Funktionen im Office 365 Security & Compliance Center ( https://protection.office.com/homepage) . Sie genießen die schnelle Einrichtung und können Sie bei Bedarf ganz einfach deaktivieren.

## <a name="how-the-evaluation-works"></a>Funktionsweise der Evaluierung

Defender für Office 365 im Evaluierungsmodus erstellt Defender für Office 365 e-Mail-Richtlinien, die Urteile wie Schadsoftware protokollieren, jedoch nicht auf Nachrichten reagieren. Sie müssen Ihre MX-Eintrags Konfiguration nicht ändern.

Mit dem Evaluierungsmodus werden [sichere Anlagen](atp-safe-attachments.md), [sichere Links](atp-safe-links.md)und [Richtlinien für den Identitätswechsel von AntiPhishing](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) in Ihrem Auftrag eingerichtet. Alle Verteidiger für Office 365-Richtlinien werden im nicht-Durchsetzungs Modus im Hintergrund erstellt und sind für Sie nicht sichtbar.

Im Evaluierungsmodus wird im Rahmen des Setups auch die [Erweiterte Filterung für Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)konfiguriert. Die Filtergenauigkeit wird verbessert, indem IP-Adress-und Absenderinformationen beibehalten werden, die andernfalls verloren gehen, wenn e-Mails über ein e-Mail-Sicherheitsgateway (ESG) vor Defender für Office 365 geleitet werden. Dadurch wird auch die Filtergenauigkeit für Ihre Exchange Online Protection (EoP) Anti-Spam-und Anti-Phishing-Richtlinien verbessert.

Um potenzielle Produktions Auswirkungen auf einige nicht unterstützte Szenarien zu minimieren, können Sie alle EoP-Filterung umgehen, indem Sie eine Transportregel erstellen, um die SCL-Bewertung (Spam Confidence Level) auf-1 festzulegen. Weitere Informationen finden Sie unter [Verwenden der Exchange-Verwaltungskonsole zum Erstellen einer e-Mail-Fluss Regel, die den SCL-Wert einer Nachricht festlegt](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)   .

Wenn der Bewertungsmodus eingerichtet ist, wird ein Bericht täglich mit bis zu 90 Tagen aktualisiert, in dem die Nachrichten quantifiziert werden, bei denen die Richtlinien blockiert wären und implementiert wurden (beispielsweise "Löschen", "an Junk senden", "Quarantäne"). Berichte werden für alle Verteidiger für Office 365-und EOP-Erkennungen generiert. Sie werden pro Erkennungstechnologie aggregiert (beispielsweise Identitätswechsel) und können nach Zeitbereich gefiltert werden. Darüber hinaus können Nachrichten Berichte bei Bedarf erstellt werden, um benutzerdefinierte Pivots oder Deep Dive-Nachrichten mithilfe von Threat Explorer zu erstellen.

Dank der vereinfachten Setup-Erfahrung können Sie sich auf Folgendes konzentrieren:

- Durchführen der Auswertung
- Aufrufen eines detaillierten Berichts
- Analysieren des Berichts für Aktionen
- Präsentieren des Evaluierungs Ergebnisses

## <a name="before-you-begin"></a>Bevor Sie beginnen:

### <a name="licensing"></a>Lizenzierung

Um auf die Evaluierung zuzugreifen, müssen Sie die Lizenzierungsanforderungen erfüllen. Die folgenden Lizenzen können verwendet werden:

- Microsoft Defender für Office 365 Plan 1
- Microsoft Defender für Office 365 Plan 2
- Microsoft 365 E5, Microsoft 365 E5-Sicherheit
- Office 365 E5

Wenn Sie nicht über eine dieser Lizenzen verfügen, müssen Sie eine Testlizenz anfordern.

#### <a name="trial"></a>Testversion

Um eine Testlizenz für Microsoft Defender für Office 365 zu erhalten, müssen Sie über die Rolle **"abrechnungsadministrator"** oder " **Globale Administratorrolle**" verfügen. Fordern Sie die Berechtigung von einem Benutzer an, der über die globale Administratorrolle verfügt. [Informationen zu Abonnements und Lizenzen](https://docs.microsoft.com/microsoft-365/commerce/licenses/subscriptions-and-licenses)

Sobald Sie über die richtige Rolle verfügen, wird empfohlen, eine Testlizenz für Microsoft Defender für Office 365 (Plan 2) im Microsoft 365 Admin Center zu erhalten, indem Sie auf Billing > Services kaufen gehen. Die Testversion umfasst eine 30-tägige ﻿kostenlose Testversion für 25 Lizenzen. [Erhalten Sie eine Testversion für Microsoft Defender für Office 365 (Plan 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).

Sie haben ein 30-tägiges Fenster mit der Bewertung zur Überwachung und Berichterstattung über erweiterte Bedrohungen. Sie haben auch die Möglichkeit, ein kostenpflichtiges Abonnement zu erwerben, wenn Sie den vollständigen Verteidiger für Office 365 Funktionen verwenden möchten.

### <a name="roles"></a>Rollen

Exchange Online Rollen sind erforderlich, um Defender für Office 365 im Evaluierungsmodus einzurichten. Die folgenden Rollen sind erforderlich:

|Aufgabe|Rolle|
|---|---|
|﻿Kostenlose Testversion anfordern oder Microsoft Defender für Office 365 kaufen (Plan 2)|Rolle "abrechnungsadministrator" oder globale Administratorrolle|
|Erstellen einer Evaluierungs Richtlinie|Rolle "Remote" und "akzeptierte Domänen"; Rolle "Sicherheitsadministrator"|
|Bearbeiten der Evaluierungs Richtlinie|Rolle "Remote" und "akzeptierte Domänen"; Rolle "Sicherheitsadministrator"|
|Löschen einer Evaluierungs Richtlinie|Rolle "Remote" und "akzeptierte Domänen"; Rolle "Sicherheitsadministrator" |
|Anzeigen des Auswertungs Berichts|Rolle "Sicherheitsadministrator" oder "Sicherheits Leser"|
|

### <a name="enhanced-filtering"></a>Erweiterte Filterung

Ihre Exchange Online Schutzrichtlinien wie Massen-und Spam Schutz bleiben erhalten. Die Nachrichtenzustellung bleibt ebenfalls erhalten. Bei der Evaluierung wird jedoch die erweiterte Filterung für Connectors aktiviert, was sich auf Ihre Nachrichtenfluss-und Exchange Online Schutzrichtlinien auswirkt, sofern Sie nicht umgangen werden.

Durch die verstärkte Filterung von Connectors können Mandanten den Schutz vor Spoofing verwenden. Anti-Spoofing wird nicht unterstützt, wenn Sie ein e-Mail-Sicherheitsgateway (ESG) verwenden, ohne die erweiterte Filterung für Connectors aktiviert zu haben.

### <a name="urls"></a>URLs

URLs werden während des Nachrichtenflusses gezündet. Wenn Sie nicht möchten, dass bestimmte URLs gezündet werden, verwalten Sie die Liste der zulässigen URLs entsprechend. Details finden Sie unter [Verwalten von URLs in der Liste Mandanten-Allow/Block](tenant-allow-block-list.md) .

URL-Links in e-Mail-Nachrichtentext Körpern werden nicht umbrochen, um die Auswirkungen auf die Kunden zu verringern.

### <a name="email-routing"></a>E-Mail-Routing

Sie müssen die entsprechenden Details vorbereiten, die Sie zum Einrichten der aktuellen e-Mail-Weiterleitung benötigen, einschließlich des Namens des eingehenden Connectors, der Ihre e-Mails weiterleitet. Wenn Sie nur Exchange Online Schutz verwenden, verfügen Sie über keinen Connector. Informationen  [zum Nachrichtenfluss und e-Mail-Routing](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/mail-flow)

Zu den unterstützten e-Mail-Routingszenarien zählen:

- **Drittanbieterpartner und/oder lokaler Dienstanbieter**: der eingehende Connector, den Sie auswerten möchten, verwendet einen Drittanbieter und/oder Sie verwenden eine Lösung für die lokale e-Mail-Sicherheit.
- **Nur Microsoft Exchange Online Schutz**: der Mandant, den Sie auswerten möchten, verwendet Office 365 für die e-Mail-Sicherheit und die e-Mail-Exchange (MX)-Eintrags Punkte auf Microsoft.

### <a name="email-security-gateway"></a>E-Mail-Sicherheitsgateway

Wenn Sie ein Drittanbieter-e-Mail-Sicherheitsgateway (ESG) verwenden, müssen Sie den Namen des Anbieters kennen. Wenn Sie einen lokalen oder nicht unterstützten Anbieter von ESG verwenden, müssen Sie die öffentliche IP-Adresse (n) für die Geräte kennen.

Unterstützte drittanbieterpartner umfassen Folgendes:

- Barracuda
- IronPort
- Mimecast
- Proofpoint
- Sophos
- Symantec
- Trend Micro

### <a name="scoping"></a>Bereichsdefinition

Sie können den Bereich der Auswertung auf einen eingehenden Connector umstellen. Wenn kein Connector konfiguriert ist, ermöglicht der Evaluierungs Bereich Administratoren das Sammeln von Daten von einem beliebigen Benutzer in Ihrem Mandanten, um Defender für Office 365 auszuwerten.

## <a name="get-started-with-the-evaluation"></a>Erste Schritte mit der Evaluierung

Suchen Sie im Compliance Center von Office 365 Security & ( https://protection.office.com/homepage) von drei Zugriffspunkten aus) nach der Microsoft Defender for Office 365 Evaluation-Einricht Karte.

- Threat Management > Dashboard
- Threat Management >-Richtlinie
- Berichte > Dashboard

## <a name="setting-up-the-evaluation"></a>Einrichten der Auswertung

Nachdem Sie den Setup Ablauf für Ihre Bewertung gestartet haben, werden zwei Routingoptionen angegeben. Je nach e-Mail-Routing-Setup und Evaluierungs Anforderungen in Ihrer Organisation können Sie auswählen, ob Sie einen Drittanbieter und/oder lokalen Dienstanbieter verwenden oder nur Microsoft Exchange Online.

- Wenn Sie einen drittanbieterpartner und/oder lokalen Dienstanbieter verwenden, müssen Sie den Namen des Anbieters aus dem Dropdownmenü auswählen. Geben Sie die anderen Connector-bezogenen Details an.

- Wählen Sie Microsoft Exchange Online aus, wenn der MX-Eintrag auf Microsoft verweist und Sie über ein Exchange Online Postfach verfügen.

Überprüfen Sie Ihre Einstellungen, und bearbeiten Sie Sie bei Bedarf. Wählen Sie dann **Auswertung erstellen** aus. Sie sollten eine Bestätigungsmeldung erhalten, um anzugeben, dass die Einrichtung abgeschlossen ist.

Ihr Microsoft Defender für Office 365 Evaluierungsbericht wird einmal pro Tag generiert. Es kann bis zu 24 Stunden dauern, bis die Daten aufgefüllt wurden.

### <a name="exchange-rules-optional"></a>Exchange-Regeln (optional)

Wenn Sie über ein vorhandenes Gateway verfügen, sollten Sie die Filterung möglicherweise umgehen, da dadurch die erweiterte Filterung für Connectors aktiviert und die IP-Adresse des eingehenden Absenders geändert wird. Navigieren Sie zum umgehen mit dem Exchange Admin Center, und erstellen Sie eine Richtlinie für SCL-1 (falls noch keins vorhanden ist). Ausführliche Informationen zu den Regelkomponenten und deren Funktionsweise finden Sie unter Nachrichtenfluss Regeln (Transportregeln) in Exchange Online.

## <a name="evaluate-capabilities"></a>Auswerten von Funktionen

Nachdem der Evaluierungsbericht generiert wurde, erfahren Sie, wie viele erweiterte Bedrohungs Links, erweiterte Bedrohungs Anlagen und potenzielle Identitätswechsel in den Arbeitsbereichen e-Mail und Zusammenarbeit in Ihrer Organisation identifiziert wurden.

Nachdem die Testversion abgelaufen ist, können Sie den Zugriff auf den Bericht für 90 Tage fortsetzen. Es werden jedoch keine weiteren Informationen gesammelt. Wenn Sie Microsoft Defender für Office 365 nach Ablauf der Testversion weiterhin verwenden möchten, stellen Sie sicher, dass Sie [ein kostenpflichtiges Abonnement für Microsoft Defender für Office 365 (Plan 2) erwerben](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).

Sie können zu den **Einstellungen** wechseln, um Ihr Routing zu aktualisieren oder die Bewertung zu jeder Zeit zu deaktivieren. Sie müssen den gleichen Setup-Vorgang jedoch erneut durchlaufen, wenn Sie sich entscheiden, die Auswertung fortzusetzen, nachdem Sie sie deaktiviert haben.

## <a name="provide-feedback"></a>Feedback geben

Ihr Feedback hilft uns, Ihre Umgebung vor fortgeschrittenen Angriffen besser zu schützen. Teilen Sie Ihre Erfahrungen und Impressionen von Produktfunktionen und Evaluierungsergebnissen.

Wählen Sie **Feedback geben** , um uns Ihre Meinung mitzuteilen.
