---
title: Bewerten von Microsoft Defender für Office 365
description: Defender für Office 365 erstellt im Evaluierungsmodus Defender für Office 365-E-Mail-Richtlinien, die Bewertungen protokollieren, z. B. Schadsoftware, aber keine Nachrichten verwenden.
keywords: Bewerten von Office 365, Microsoft Defender für Office 365, Office 365-Evaluierung, Testen von Office 365, Microsoft Defender, ATP
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2e97e510cbc3188f8cc6117c5d7bd1e1d23897eb
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205903"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a>Bewerten von Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Die Microsoft Defender for Office 365-Evaluierung befindet sich in der öffentlichen Vorschau. Diese Vorschauversion wird ohne Vereinbarung zum Servicelevel bereitgestellt. Bestimmte Features werden möglicherweise nicht unterstützt oder verfügen möglicherweise über eingeschränkte Funktionen.

Durch die Durchführung einer umfassenden Sicherheitsproduktbewertung können Sie fundierte Entscheidungen zu Upgrades und Käufen treffen. Es hilft, die Funktionen des Sicherheitsprodukts auszuprobieren, um zu bewerten, wie es Ihrem Sicherheitsbetriebsteam bei seinen täglichen Aufgaben helfen kann.

Die Evaluierungsumgebung von [Microsoft Defender für Office 365](defender-for-office-365.md) soll die Komplexität der Geräte- und Umgebungskonfiguration beseitigen, sodass Sie sich auf die Auswertung der Funktionen von Microsoft Defender für Office 365 konzentrieren können. Im Auswertungsmodus können alle Nachrichten, die an Exchange Online-Postfächer gesendet werden, ausgewertet werden, ohne auf Microsoft zu verweisen. Das Feature gilt nur für den E-Mail-Schutz und nicht für Office-Clients wie Word, SharePoint oder Teams.

Wenn Sie noch nicht über eine Lizenz verfügen, die Microsoft Defender für Office 365 unterstützt, können Sie eine kostenlose [30-tägige](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) Evaluierung starten und die Funktionen im Office 365 Security & Compliance Center ( https://protection.office.com/homepage) testen. Sie genießen die schnelle Einrichtung und können sie bei Bedarf ganz einfach deaktivieren.

## <a name="how-the-evaluation-works"></a>Funktionsweise der Auswertung

Defender für Office 365 erstellt im Evaluierungsmodus Defender für Office 365-E-Mail-Richtlinien, die Bewertungen protokollieren, z. B. Schadsoftware, aber keine Nachrichten verwenden. Sie müssen die Konfiguration des MX-Eintrags nicht ändern.

Im Auswertungsmodus werden richtlinien für sichere [Anlagen,](safe-attachments.md)sichere [Links](safe-links.md)und Postfachintelligenz in Ihrem Namen eingerichtet. [](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) Alle Defender for Office 365-Richtlinien werden im Nichtersetzungsmodus im Hintergrund erstellt und sind für Sie nicht sichtbar.

Im Rahmen des Setups wird im Evaluierungsmodus auch die erweiterte [Filterung für Connectors konfiguriert.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) Es verbessert die Filtergenauigkeit, indem IP-Adresse und Absenderinformationen beibehalten werden, die andernfalls verloren gehen, wenn E-Mails über ein E-Mail-Sicherheitsgateway (E-Mail Security Gateway, ESG) vor Defender for Office 365 gehen. Die erweiterte Filterung für Connectors verbessert außerdem die Filtergenauigkeit für Ihre vorhandenen Exchange Online Protection (EOP)-Antispam- und Antiphishingrichtlinien.

Aktivierte erweiterte Filterung für Connectors verbessert die Filtergenauigkeit, kann jedoch die Zuleitung für bestimmte Nachrichten ändern, wenn Sie über eine ESG vor Defender for Office 365 verfügen und die EOP-Filterung derzeit nicht umgehen. Die Auswirkungen sind auf #A0 beschränkt. Die im Rahmen der Evaluierung eingerichteten MDO-Richtlinien werden im Nichtdurchsetzungsmodus erstellt. Um potenzielle Produktionsauswirkungen zu minimieren, können Sie die EOP-Filterung umgehen, indem Sie eine Transportregel erstellen, um die Spamsicherheitsstufe (Spam Confidence Level, SCL) auf -1 zu setzen. Weitere Informationen finden Sie unter Use [the EAC to create a mail flow rule that sets the SCL of a](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)   message.

Wenn der Auswertungsmodus eingerichtet ist, wird täglich ein Bericht mit bis zu 90 Tagen Daten aktualisiert, die die Nachrichten quantifizieren, die blockiert worden wären, wenn die Richtlinien implementiert wurden (z. B. löschen, an Junk senden, Quarantäne). Berichte werden für alle Defender for Office 365- und EOP-Erkennungen generiert. Sie werden pro Erkennungstechnologie (z. B. Identitätswechsel) aggregiert und können nach Zeitbereich gefiltert werden. Darüber hinaus können Nachrichtenberichte bei Bedarf erstellt werden, um benutzerdefinierte Pivots zu erstellen oder nachrichten mit dem Threat Explorer zu vertiefen.

Mit der vereinfachten Einrichtungserfahrung können Sie sich auf:

- Ausführen der Auswertung
- Abrufen eines detaillierten Berichts
- Analysieren des Berichts für Aktionen
- Präsentieren des Bewertungsergebniss

## <a name="before-you-begin"></a>Bevor Sie beginnen

### <a name="licensing"></a>Lizenzierung

Um auf die Auswertung zu zugreifen, müssen Sie die Lizenzierungsanforderungen erfüllen. Eine der folgenden Lizenzen funktioniert:

- Microsoft Defender für Office 365 Plan 1
- Microsoft Defender für Office 365 Plan 2
- Microsoft 365 E5, Microsoft 365 E5 Security
- Office 365 E5

Wenn Sie nicht über eine dieser Lizenzen verfügen, müssen Sie eine Testlizenz erwerben.

#### <a name="trial"></a>Testversion

Um eine Testlizenz für Microsoft Defender für Office 365 zu erhalten, benötigen Sie die Administratorrolle **"Abrechnung"** oder **"Globaler Administrator".** Fordern Sie die Berechtigung von einer Person an, die über die Rolle "Globaler Administrator" verfügt. [Informationen zu Abonnements und Lizenzen](../../commerce/licenses/subscriptions-and-licenses.md)

Sobald Sie über die richtige Rolle verfügen, wird empfohlen, eine Testlizenz für Microsoft Defender für Office 365 (Plan 2) im Microsoft 365 Admin Center zu erhalten, indem Sie zu Abrechnung > Dienste erwerben. Die Testversion umfasst eine 30-tägige kostenlose Testversion für 25 Lizenzen. [Hier erhalten Sie eine Testversion für Microsoft Defender für Office 365 (Plan 2).](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)

Sie verfügen über ein 30-Tage-Fenster mit der Auswertung, um erweiterte Bedrohungen zu überwachen und zu melden. Sie haben auch die Möglichkeit, ein kostenpflichtiges Abonnement zu erwerben, wenn Sie die vollständigen Defender for Office 365-Funktionen benötigen.

### <a name="roles"></a>Rollen

**Exchange Online-Rollen sind erforderlich,** um Defender for Office 365 im Evaluierungsmodus einrichten zu können. Das Zuweisen einer Microsoft 365-Compliance- oder Sicherheitsadministratorrolle funktioniert nicht.

- [Informationen zu Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo)
- [Informationen zum Zuweisen von Administratorrollen](../../admin/add-users/assign-admin-roles.md)

Die folgenden Rollen sind erforderlich:

|Aufgabe|Rolle (in Exchange Online)|
|---|---|
|Kostenlose Testversion erhalten oder Microsoft Defender für Office 365 kaufen (Plan 2)|Abrechnungsadministratorrolle ODER globale Administratorrolle|
|Erstellen einer Evaluierungsrichtlinie|Rolle "Remotedomänen" und "Akzeptierte Domänen"; Rolle des Sicherheitsadministrators|
|Bearbeiten der Evaluierungsrichtlinie|Rolle "Remotedomänen" und "Akzeptierte Domänen"; Rolle des Sicherheitsadministrators|
|Evaluierungsrichtlinie löschen|Rolle "Remotedomänen" und "Akzeptierte Domänen"; Rolle des Sicherheitsadministrators |
|Auswertungsbericht anzeigen|Rolle "Sicherheitsadministrator" ODER "Sicherheitsleserolle"|
|

### <a name="enhanced-filtering"></a>Erweiterte Filterung

Ihre Exchange Online Protection-Richtlinien, z. B. Massen- und Spamschutz, bleiben unverändert. Bei der Auswertung wird jedoch die erweiterte Filterung für Connectors aktiviert, was sich auf den Nachrichtenfluss und die Exchange Online Protection-Richtlinien auswirken kann, sofern sie nicht umgangen werden.

Erweiterte Filterung für Connectors ermöglicht Mandanten die Verwendung von Anti-Spoofing-Schutz. Antis spoofing wird nicht unterstützt, wenn Sie ein E-Mail-Sicherheitsgateway (E-Mail Security Gateway, ESG) verwenden, ohne die erweiterte Filterung für Connectors aktiviert zu haben.

### <a name="urls"></a>URLs

URLs werden während des Nachrichtenflusses detoniert. Wenn sie nicht möchten, dass bestimmte URLs detoniert werden, verwalten Sie Ihre Liste der zulässigen URLs entsprechend. Weitere Informationen finden Sie unter [Manage the Tenant Allow/Block List.](tenant-allow-block-list.md)

URL-Links in den E-Mail-Nachrichtentexten werden nicht umschließen, um die Kundenbelastung zu mindern.

### <a name="email-routing"></a>E-Mail-Routing

Bereiten Sie die entsprechenden Details vor, die Sie zum Einrichten der Derzeitroute Ihrer E-Mails benötigen, einschließlich des Namens des eingehenden Connectors, der Ihre E-Mails weiter leitet. Wenn Sie nur Exchange Online Protection verwenden, haben Sie keinen Connector.  [Informationen zum Nachrichtenfluss und zum E-Mail-Routing](/office365/servicedescriptions/exchange-online-service-description/mail-flow)

Zu den unterstützten E-Mail-Routingszenarien gehören:

- Drittanbieter und/oder lokale Dienstanbieter: Der eingehende Connector, den Sie auswerten möchten, verwendet einen Drittanbieter **und/oder** Sie verwenden eine Lösung für die lokale E-Mail-Sicherheit.
- **Microsoft Exchange Online Protection:** Der zu bewertende Mandant verwendet Office 365 für die E-Mail-Sicherheit, und der Mail Exchange (MX)-Eintrag verweist auf Microsoft.

### <a name="email-security-gateway"></a>E-Mail-Sicherheitsgateway

Wenn Sie ein E-Mail-Sicherheitsgateway (E-Mail Security Gateway, ESG) eines Drittanbieters verwenden, müssen Sie den Namen des Anbieters kennen. Wenn Sie eine lokale oder nicht unterstützte ESG verwenden, müssen Sie die öffentliche IP-Adresse(n) für die Geräte kennen.

Zu den unterstützten Drittanbieterpartnern gehören:

- Barracuda
- IronPort
- Mimecast
- Proofpoint
- Sophos
- Symantec
- Trend Micro

### <a name="scoping"></a>Bereichsdefinition

Sie können die Auswertung auf einen eingehenden Connector ausdingen. Wenn kein Connector konfiguriert ist, können Administratoren im Auswertungsbereich Daten von jedem Benutzer in Ihrem Mandanten sammeln, um Defender für Office 365 auszuwerten.

## <a name="get-started-with-the-evaluation"></a>Erste Schritte mit der Auswertung

Suchen Sie die Microsoft Defender für Office 365-Evaluierungsset-Up-Karte im Office 365 Security & Compliance Center ( https://protection.office.com/homepage) von drei Zugriffpunkten aus:

- Bedrohungsverwaltung > Dashboard
- Bedrohungsverwaltung > Richtlinie
- Berichte > Dashboard

## <a name="setting-up-the-evaluation"></a>Einrichten der Auswertung

Sobald Sie den Einrichtungsfluss für Ihre Auswertung gestartet haben, erhalten Sie zwei Routingoptionen. Je nach den Anforderungen für die Einrichtung und Auswertung von E-Mail-Routing in Ihrer Organisation können Sie auswählen, ob Sie einen Drittanbieter und/oder einen lokalen Dienstanbieter verwenden oder Microsoft Exchange Online.

- Wenn Sie einen Drittanbieterpartner und/oder lokalen Dienstanbieter verwenden, müssen Sie den Namen des Anbieters im Dropdownmenü auswählen. Geben Sie die anderen connectorbezogenen Details an.

- Wählen Microsoft Exchange Online, wenn der MX-Eintrag auf Microsoft verweist und Sie über ein Exchange Online-Postfach verfügen.

Überprüfen Sie Ihre Einstellungen, und bearbeiten Sie sie bei Bedarf. Wählen Sie dann Auswertung **erstellen aus.** Sie sollten eine Bestätigungsnachricht erhalten, um anzugeben, dass Die Einrichtung abgeschlossen ist.

Ihr Microsoft Defender for Office 365-Evaluierungsbericht wird einmal pro Tag generiert. Es kann bis zu 24 Stunden dauern, bis die Daten auffüllen.

### <a name="exchange-rules-optional"></a>Exchange-Regeln (optional)

Wenn Sie über ein vorhandenes Gateway verfügen, aktiviert das Aktivieren des Auswertungsmodus die erweiterte Filterung für Connectors. Dadurch wird die Filtergenauigkeit verbessert, indem die IP-Adresse des eingehenden Absenders geändert wird. Dies kann die Filterbesprechungen ändern, und wenn Sie Exchange Online Protection nicht umgehen, kann dies die Zusicherung für bestimmte Nachrichten ändern. In diesem Fall sollten Sie die Filterung vorübergehend umgehen, um die Auswirkungen zu analysieren. Navigieren Sie zum Umgehen zum Exchange Admin Center, und erstellen Sie eine Richtlinie von SCL -1 (wenn Sie noch nicht über eine verfügen). Weitere Informationen zu den Regelkomponenten und deren Funktionsweise finden Sie unter Nachrichtenflussregeln (Transportregeln) in Exchange Online.

## <a name="evaluate-capabilities"></a>Auswerten von Funktionen

Nachdem der Evaluierungsbericht generiert wurde, sehen Sie sich an, wie viele erweiterte Bedrohungslinks, erweiterte Bedrohungsanlagen und potenzielle Identitätswechsel in den E-Mails und Arbeitsbereichen für die Zusammenarbeit in Ihrer Organisation identifiziert wurden.

Nach Ablauf der Testversion können Sie weiterhin 90 Tage auf den Bericht zugreifen. Es werden jedoch keine weiteren Informationen gesammelt. Wenn Sie Microsoft Defender für Office 365 nach Ablauf der Testversion weiterhin verwenden möchten, müssen Sie ein kostenpflichtiges Abonnement für [Microsoft Defender für Office 365 (Plan 2) kaufen.](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)

Sie können zu Einstellungen **wechseln,** um Ihr Routing zu aktualisieren oder die Auswertung jederzeit zu deaktivieren. Sie müssen jedoch den gleichen Einrichtungsprozess erneut durchgehen, wenn Sie die Auswertung fortsetzen möchten, nachdem Sie sie deaktiviert haben.

## <a name="provide-feedback"></a>Feedback geben

Ihr Feedback hilft uns, Ihre Umgebung besser vor erweiterten Angriffen zu schützen. Teilen Sie Ihre Erfahrungen und Impressionen von Produktfunktionen und Bewertungsergebnissen.

Wählen **Sie Feedback geben** aus, um uns ihre Meinung zu sagen.