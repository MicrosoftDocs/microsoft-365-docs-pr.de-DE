---
title: Bewerten von Microsoft Defender für Office 365
description: Defender for Office 365 im Evaluierungsmodus erstellt Defender für Office 365 E-Mail-Richtlinien, die Bewertungen protokollieren, z. B. Schadsoftware, aber keine Nachrichten verwenden.
keywords: evaluate Office 365, Microsoft Defender for Office 365, office 365 evaluation, try office 365, Microsoft Defender, Microsoft Defender for Endpoint
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 04/21/2021
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
ms.openlocfilehash: 005c1f6ad7806c8d1ba1d38e4e82edd25034075d
ms.sourcegitcommit: 682ed2c4e2bc6979025cdb89094866cef6c8751a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51942993"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a>Bewerten von Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Microsoft Defender für Office 365 wird in der öffentlichen Vorschau angezeigt. Diese Vorschauversion wird ohne Vereinbarung zum Servicelevel bereitgestellt. Bestimmte Features werden möglicherweise nicht unterstützt oder verfügen möglicherweise über eingeschränkte Funktionen.

Durch eine sorgfältige Sicherheitsproduktbewertung können Sie fundierte Entscheidungen zu Upgrades und Käufen treffen. Es hilft, die Funktionen des Sicherheitsprodukts auszuprobieren, um zu bewerten, wie es Ihrem Sicherheitsbetriebsteam bei seinen täglichen Aufgaben helfen kann.

Die [Evaluierungsumgebung von Microsoft Defender für Office 365](defender-for-office-365.md) soll die Komplexität der Geräte- und Umgebungskonfiguration beseitigen, sodass Sie sich auf die Auswertung der Funktionen von Microsoft Defender für Office 365. Im Auswertungsmodus können alle Nachrichten, die an Exchange Online gesendet werden, ausgewertet werden, ohne auf Microsoft zu verweisen. Das Feature gilt nur für den E-Mail-Schutz und nicht Office Clients wie Word, SharePoint oder Teams.

Wenn Sie noch nicht über eine Lizenz verfügen, die Microsoft Defender für Office 365 unterstützt, können Sie eine kostenlose [30-tägige](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) Evaluierung starten und die Funktionen im Office 365 Security & Compliance Center testen ( https://protection.office.com/homepage) . Sie genießen die schnelle Einrichtung und können sie bei Bedarf ganz einfach deaktivieren.

> [!NOTE]
> Wenn Sie im einheitlichen Microsoft 365-Sicherheitsportal (security.microsoft.com) sind, können Sie hier eine Defender for Office 365-Evaluierung starten: Email & Collaboration > Policies & Rules > Threat Policies > Additional Policies.

## <a name="how-the-evaluation-works"></a>Funktionsweise der Auswertung

Defender for Office 365 im Evaluierungsmodus erstellt Defender für Office 365 E-Mail-Richtlinien, die Bewertungen protokollieren, z. B. Schadsoftware, aber keine Nachrichten verwenden. Sie müssen die Konfiguration des MX-Eintrags nicht ändern.

Im Auswertungsmodus werden richtlinien für sichere [Anlagen,](safe-attachments.md)sichere [Links](safe-links.md)und Postfachintelligenz in Ihrem Namen eingerichtet. [](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) Alle Defender for Office 365 werden im Nichtersetzungsmodus im Hintergrund erstellt und sind für Sie nicht sichtbar.

Im Rahmen des Setups wird im Evaluierungsmodus auch die erweiterte [Filterung für Connectors konfiguriert.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) Es verbessert die Filtergenauigkeit, indem IP-Adresse und Absenderinformationen beibehalten werden, die andernfalls verloren gehen, wenn E-Mails ein E-Mail-Sicherheitsgateway (E-Mail Security Gateway, ESG) vor Defender for Office 365. Die erweiterte Filterung für Connectors verbessert außerdem die Filtergenauigkeit für Ihre Exchange Online Protection (EOP)-Antispam- und Antiphishingrichtlinien.

Aktivierte erweiterte Filterung für Connectors verbessert die Filtergenauigkeit, kann jedoch die Zuleitung für bestimmte Nachrichten ändern, wenn Sie eine ESG vor Defender for Office 365 haben und die EOP-Filterung derzeit nicht umgehen. Die Auswirkungen sind auf #A0 beschränkt. Die im Rahmen der Evaluierung eingerichteten MDO-Richtlinien werden im Nichtdurchsetzungsmodus erstellt. Um potenzielle Produktionsauswirkungen zu minimieren, können Sie die EOP-Filterung umgehen, indem Sie eine Transportregel erstellen, um die Spamsicherheitsstufe (Spam Confidence Level, SCL) auf -1 zu setzen. Weitere Informationen finden Sie unter Use [the EAC to create a mail flow rule that sets the SCL of a](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)   message.

Wenn der Auswertungsmodus eingerichtet ist, wird täglich ein Bericht mit bis zu 90 Tagen Daten aktualisiert, die die Nachrichten quantifizieren, die blockiert worden wären, wenn die Richtlinien implementiert wurden (z. B. löschen, an Junk senden, Quarantäne). Berichte werden für alle Defender-Office 365 und EOP-Erkennungen generiert. Sie werden pro Erkennungstechnologie (z. B. Identitätswechsel) aggregiert und können nach Zeitbereich gefiltert werden. Darüber hinaus können Nachrichtenberichte bei Bedarf erstellt werden, um benutzerdefinierte Pivots zu erstellen oder nachrichten mit dem Threat Explorer zu vertiefen.

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

Um eine Testlizenz für Microsoft Defender for Office 365 zu  erhalten, benötigen Sie die Administratorrolle Abrechnung oder **globale Administratorrolle**. Fordern Sie die Berechtigung von einer Person an, die über die Rolle "Globaler Administrator" verfügt. [Informationen zu Abonnements und Lizenzen](../../commerce/licenses/subscriptions-and-licenses.md)

Sobald Sie über die richtige Rolle verfügen, wird empfohlen, eine Testlizenz für Microsoft Defender für Office 365 (Plan 2) im Microsoft 365 Admin Center zu erhalten, indem Sie zu Abrechnung > Dienste erwerben. Die Testversion umfasst eine 30-tägige kostenlose Testversion für 25 Lizenzen. [Hier erhalten Sie eine Testversion für Microsoft Defender for Office 365 (Plan 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).

Sie verfügen über ein 30-Tage-Fenster mit der Auswertung, um erweiterte Bedrohungen zu überwachen und zu melden. Sie haben auch die Möglichkeit, ein kostenpflichtiges Abonnement zu erwerben, wenn Sie den vollständigen Defender for Office 365 möchten.

### <a name="roles"></a>Rollen

**Exchange Online rollen sind erforderlich,** um Defender für Office 365 im Evaluierungsmodus einrichten. Das Zuweisen einer Microsoft 365 oder Sicherheitsadministratorrolle funktioniert nicht.

- [Erfahren Sie mehr über Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo)
- [Informationen zum Zuweisen von Administratorrollen](../../admin/add-users/assign-admin-roles.md)

Die folgenden Rollen sind erforderlich:

|Aufgabe|Rolle (in Exchange Online)|
|---|---|
|Kostenlose Testversion erhalten oder Microsoft Defender for Office 365 kaufen (Plan 2)|Abrechnungsadministratorrolle ODER globale Administratorrolle|
|Erstellen einer Evaluierungsrichtlinie|Rolle "Remotedomänen" und "Akzeptierte Domänen"; Rolle des Sicherheitsadministrators|
|Bearbeiten der Evaluierungsrichtlinie|Rolle "Remotedomänen" und "Akzeptierte Domänen"; Rolle des Sicherheitsadministrators|
|Evaluierungsrichtlinie löschen|Rolle "Remotedomänen" und "Akzeptierte Domänen"; Rolle des Sicherheitsadministrators |
|Auswertungsbericht anzeigen|Rolle "Sicherheitsadministrator" ODER "Sicherheitsleserolle"|
|

### <a name="enhanced-filtering"></a>Erweiterte Filterung

Ihre Exchange Online Protection, z. B. Massen- und Spamschutz, bleiben unverändert. Bei der Auswertung wird jedoch die erweiterte Filterung für Connectors aktiviert, was sich auf den Nachrichtenfluss und die Exchange Online Protection auswirken kann, sofern dies nicht umgangen wird.

Erweiterte Filterung für Connectors ermöglicht Mandanten die Verwendung von Anti-Spoofing-Schutz. Antis spoofing wird nicht unterstützt, wenn Sie ein E-Mail-Sicherheitsgateway (E-Mail Security Gateway, ESG) verwenden, ohne die erweiterte Filterung für Connectors aktiviert zu haben.

### <a name="urls"></a>URLs

URLs werden während des Nachrichtenflusses detoniert. Wenn sie nicht möchten, dass bestimmte URLs detoniert werden, verwalten Sie Ihre Liste der zulässigen URLs entsprechend. Weitere Informationen finden Sie unter [Manage the Tenant Allow/Block List.](tenant-allow-block-list.md)

URL-Links in den E-Mail-Nachrichtentexten werden nicht umschließen, um die Kundenbelastung zu mindern.

### <a name="email-routing"></a>E-Mail-Routing

Bereiten Sie die entsprechenden Details vor, die Sie zum Einrichten der Derzeitroute Ihrer E-Mails benötigen, einschließlich des Namens des eingehenden Connectors, der Ihre E-Mails weiter leitet. Wenn Sie nur eine Exchange Online Protection, haben Sie keinen Connector.  [Informationen zum Nachrichtenfluss und zum E-Mail-Routing](/office365/servicedescriptions/exchange-online-service-description/mail-flow)

Zu den unterstützten E-Mail-Routingszenarien gehören:

- Drittanbieter und/oder lokale Dienstanbieter: Der eingehende Connector, den Sie auswerten möchten, verwendet einen Drittanbieter **und/oder** Sie verwenden eine Lösung für die lokale E-Mail-Sicherheit.
- **Microsoft Exchange Online Nur** Schutz: Der zu bewertende Mandant verwendet Office 365 für die E-Mail-Sicherheit, und der Mail Exchange (MX)-Eintrag verweist auf Microsoft.

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

Sie können die Auswertung auf einen eingehenden Connector ausdingen. Wenn kein Connector konfiguriert ist, können Administratoren im Auswertungsbereich Daten von jedem Benutzer in Ihrem Mandanten sammeln, um Defender für die Office 365.

## <a name="get-started-with-the-evaluation"></a>Erste Schritte mit der Auswertung

Suchen Sie die Microsoft Defender for Office 365-Bewertungsset-Up-Karte im Office 365 Security & Compliance Center ( https://protection.office.com/homepage) von drei Zugriffpunkten aus:

- Bedrohungsverwaltung > Dashboard
- Bedrohungsverwaltung > Richtlinie
- Berichte > Dashboard

## <a name="setting-up-the-evaluation"></a>Einrichten der Auswertung

Sobald Sie den Einrichtungsfluss für Ihre Auswertung gestartet haben, erhalten Sie zwei Routingoptionen. Abhängig von den Anforderungen an die Einrichtung und Auswertung von E-Mail-Routing in Ihrer Organisation können Sie auswählen, ob Sie einen Drittanbieter und/oder einen lokalen Dienstanbieter verwenden oder Microsoft Exchange Online.

- Wenn Sie einen Drittanbieterpartner und/oder lokalen Dienstanbieter verwenden, müssen Sie den Namen des Anbieters im Dropdownmenü auswählen. Geben Sie die anderen connectorbezogenen Details an.

- Wählen Microsoft Exchange Online, wenn der MX-Eintrag auf Microsoft verweist und Sie über ein Exchange Online verfügen.

Überprüfen Sie Ihre Einstellungen, und bearbeiten Sie sie bei Bedarf. Wählen Sie dann Auswertung **erstellen aus.** Sie sollten eine Bestätigungsnachricht erhalten, um anzugeben, dass Die Einrichtung abgeschlossen ist.

Ihr Microsoft Defender for Office 365-Evaluierungsbericht wird einmal pro Tag generiert. Es kann bis zu 24 Stunden dauern, bis die Daten auffüllen.

### <a name="exchange-rules-optional"></a>Exchange Regeln (optional)

Wenn Sie über ein vorhandenes Gateway verfügen, aktiviert das Aktivieren des Auswertungsmodus die erweiterte Filterung für Connectors. Dadurch wird die Filtergenauigkeit verbessert, indem die IP-Adresse des eingehenden Absenders geändert wird. Dies kann die Filterverdingungen ändern, und wenn Sie diese Exchange Online Protection kann dies die Lieferfähigkeit für bestimmte Nachrichten ändern. In diesem Fall sollten Sie die Filterung vorübergehend umgehen, um die Auswirkungen zu analysieren. Navigieren Sie zum Umgehen zum Exchange Admin Center, und erstellen Sie eine Richtlinie von SCL -1 (sofern sie noch nicht vorhanden ist). Weitere Informationen zu den Regelkomponenten und deren Funktionsweise finden Sie unter Nachrichtenflussregeln (Transportregeln) in Exchange Online.

## <a name="evaluate-capabilities"></a>Auswerten von Funktionen

Nachdem der Evaluierungsbericht generiert wurde, sehen Sie sich an, wie viele erweiterte Bedrohungslinks, erweiterte Bedrohungsanlagen und potenzielle Identitätswechsel in den E-Mails und Arbeitsbereichen für die Zusammenarbeit in Ihrer Organisation identifiziert wurden.

Nach Ablauf der Testversion können Sie weiterhin 90 Tage auf den Bericht zugreifen. Es werden jedoch keine weiteren Informationen gesammelt. Wenn Sie Microsoft Defender for Office 365 nach Ablauf der Testversion weiter verwenden möchten, müssen Sie ein kostenpflichtiges Abonnement für [Microsoft Defender für Office 365 (Plan 2) kaufen.](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)

Sie können zu **Einstellungen,** um Ihr Routing zu aktualisieren oder die Auswertung jederzeit zu deaktivieren. Sie müssen jedoch den gleichen Einrichtungsprozess erneut durchgehen, wenn Sie die Auswertung fortsetzen möchten, nachdem Sie sie deaktiviert haben.

## <a name="provide-feedback"></a>Feedback geben

Ihr Feedback hilft uns, Ihre Umgebung besser vor erweiterten Angriffen zu schützen. Teilen Sie Ihre Erfahrungen und Impressionen von Produktfunktionen und Bewertungsergebnissen.

Wählen **Sie Feedback geben** aus, um uns ihre Meinung zu sagen.