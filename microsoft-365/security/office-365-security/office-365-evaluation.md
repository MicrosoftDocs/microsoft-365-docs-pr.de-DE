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
ms.openlocfilehash: 7c0bb1701cf030692bc98218b38be00cae57a2bd
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080701"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a>Bewerten von Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Die Microsoft Defender für Office 365-Evaluierung befindet sich in der öffentlichen Vorschau. Diese Vorschauversion wird ohne Vereinbarung zum Servicelevel bereitgestellt. Bestimmte Features werden möglicherweise nicht unterstützt oder verfügen über eingeschränkte Funktionen.

Die Durchführung einer umfassenden Sicherheitsproduktbewertung kann Ihnen helfen, fundierte Entscheidungen zu Upgrades und Einkäufen zu treffen. Es hilft, die Funktionen des Sicherheitsprodukts auszuprobieren, um zu bewerten, wie es Ihrem Sicherheitsteam bei ihren täglichen Aufgaben helfen kann.

Die Evaluierungsumgebung von [Microsoft Defender für Office 365](office-365-atp.md) soll die Komplexität der Geräte- und Umgebungskonfiguration beseitigen, sodass Sie sich auf die Bewertung der Funktionen der Sicherheitslösung konzentrieren können. Sie gilt nur für den E-Mail-Schutz und nicht für SharePoint, Office Clients oder Teams.

Wenn Sie noch nicht über eine Lizenz verfügen, die Microsoft Defender für Office 365 unterstützt, können Sie eine kostenlose [30-tägige](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) Evaluierung starten und die Funktionen im Office 365 Security & Compliance Center ( ) https://protection.office.com/homepage) testen. Sie profitieren von der schnellen Einrichtung und können sie bei Bedarf ganz einfach deaktivieren.

## <a name="how-the-evaluation-works"></a>Funktionsweise der Auswertung

Defender für Office 365 erstellt im Evaluierungsmodus Defender für Office 365-E-Mail-Richtlinien, die Bewertungen protokollieren, z. B. Schadsoftware, aber keine Nachrichten verwenden. Sie müssen ihre Konfiguration des MX-Eintrags nicht ändern.

Mit dem Evaluierungsmodus [](atp-safe-links.md)werden Richtlinien für [sichere Anlagen,](atp-safe-attachments.md)sichere Links und [Antiphishing-Identitätswechsel](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) in Ihrem Auftrag eingerichtet. Alle Defender für Office 365-Richtlinien werden im Nichtersetzungsmodus im Hintergrund erstellt und sind für Sie nicht sichtbar.

Im Rahmen des Setups wird im Evaluierungsmodus auch die erweiterte [Filterung für Connectors konfiguriert.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) Dadurch wird die Filtergenauigkeit verbessert, indem die Informationen zu IP-Adressen und Absendern beibehalten werden, die andernfalls verloren gehen, wenn E-Mails ein E-Mail-Sicherheitsgateway (ESG) vor Defender für Office 365 durchläuft. Die erweiterte Filterung verbessert auch die Filtergenauigkeit für Ihre Exchange Online Protection (EOP)-Antispam- und Antiphishingrichtlinien.

Um die potenziellen Auswirkungen auf die Produktion in einigen nicht unterstützten Szenarien zu minimieren, können Sie alle EOP-Filter umgehen, indem Sie eine Transportregel erstellen, um die SCL (Spam Confidence Level) auf -1 zu setzen. Weitere Informationen finden Sie unter Verwenden der EAC zum Erstellen einer Nachrichtenflussregel, die [den SCL einer](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)Nachricht fest   legt.

Wenn der Evaluierungsmodus eingerichtet ist, wird täglich ein Bericht mit bis zu 90 Tagen Daten aktualisiert, die die Nachrichten quantifizieren, die bei Implementierung der Richtlinien blockiert worden wären (z. B. Löschen, Senden an Junk-E-Mail, Quarantäne). Berichte werden für alle Defender für Office 365- und EOP-Erkennungen generiert. Sie werden pro Erkennungstechnologie aggregiert (z. B. Identitätswechsel) und können nach Zeitbereich gefiltert werden. Darüber hinaus können Nachrichtenberichte bei Bedarf erstellt werden, um benutzerdefinierte Pivots zu erstellen oder Um nachrichten mithilfe des Bedrohungs-Explorers zu vertiefen.

Mit der vereinfachten Einrichtung können Sie sich auf:

- Ausführen der Evaluierung
- Abrufen eines detaillierten Berichts
- Analysieren des Berichts für Eine Aktion
- Präsentieren des Bewertungsergebniss

## <a name="before-you-begin"></a>Bevor Sie beginnen

### <a name="licensing"></a>Lizenzierung

Um auf die Evaluierung zugreifen zu können, müssen Sie die Lizenzierungsanforderungen erfüllen. Eine der folgenden Lizenzen funktioniert:

- Microsoft Defender für Office 365 Plan 1
- Microsoft Defender für Office 365 Plan 2
- Microsoft 365 E5, Microsoft 365 E5 Security
- Office 365 E5

Wenn Sie nicht über eine dieser Lizenzen verfügen, müssen Sie eine Testlizenz erwerben.

#### <a name="trial"></a>Testversion

Um eine Testlizenz für Microsoft Defender für Office 365 zu erhalten, benötigen Sie die Administratorrolle **"Abrechnung"** oder die **rolle "Globaler Administrator".** Fordern Sie die Berechtigung von einer Person an, die über die Rolle des globalen Administrator verfügt. [Informationen zu Abonnements und Lizenzen](https://docs.microsoft.com/microsoft-365/commerce/licenses/subscriptions-and-licenses)

Sobald Sie über die richtige Rolle verfügen, wird empfohlen, eine Testlizenz für Microsoft Defender für Office 365 (Plan 2) im Microsoft 365 Admin Center zu erhalten, indem Sie zu "Abrechnung > Dienste kaufen" gehen. Die Testversion umfasst eine 30-tägige kostenlose Testversion für 25 Lizenzen. [Erhalten Sie eine Testversion von Microsoft Defender für Office 365 (Plan 2).](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)

Sie haben ein 30-Tage-Fenster mit der Auswertung, um erweiterte Bedrohungen zu überwachen und Berichte zu diesen zu erstellen. Sie haben auch die Möglichkeit, ein kostenpflichtiges Abonnement zu erwerben, wenn Sie die vollständigen Funktionen von Defender für Office 365 nutzen möchten.

### <a name="roles"></a>Rollen

Exchange Online-Rollen sind erforderlich, um Defender für Office 365 im Evaluierungsmodus einrichten zu können.

- [Informationen zu Berechtigungen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
- [Informationen zum Zuweisen von Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles)

Die folgenden Rollen sind erforderlich:

|Aufgabe|Rolle|
|---|---|
|Kostenlose Testversion erwerben oder Microsoft Defender für Office 365 kaufen (Plan 2)|Rolle "Abrechnungsadministrator" ODER "Globaler Administrator"|
|Erstellen einer Evaluierungsrichtlinie|Rolle "Remote- und akzeptierte Domänen"; Rolle "Sicherheitsadministrator"|
|Bearbeiten der Evaluierungsrichtlinie|Rolle "Remote- und akzeptierte Domänen"; Rolle "Sicherheitsadministrator"|
|Löschen einer Evaluierungsrichtlinie|Rolle "Remote- und akzeptierte Domänen"; Rolle "Sicherheitsadministrator" |
|Auswertungsbericht anzeigen|Rolle "Sicherheitsadministrator" ODER Rolle "Sicherheitsleseprogramm"|
|


### <a name="enhanced-filtering"></a>Erweiterte Filterung

Ihre Exchange Online Protection-Richtlinien, z. B. Massen- und Spamschutz, bleiben unverändert. Die Nachrichtenzustellung bleibt ebenfalls unverändert. Bei der Auswertung wird jedoch die erweiterte Filterung für Connectors aktiviert, was sich auf den Nachrichtenfluss und die Exchange Online Protection-Richtlinien auswirken wird, sofern sie nicht umgangen werden.

Die erweiterte Filterung für Connectors ermöglicht Mandanten die Verwendung des Antis spoofing-Schutzes. Antis spoofing wird nicht unterstützt, wenn Sie ein E-Mail-Sicherheitsgateway (ESG) verwenden, ohne die erweiterte Filterung für Connectors aktiviert zu haben.

### <a name="urls"></a>URLs

URLs werden während des Nachrichtenflusses detoniert. Wenn Sie nicht möchten, dass bestimmte URLs detoniert werden, verwalten Sie Ihre Liste der zulässigen URLs entsprechend. Weitere [Informationen finden Sie unter "Verwalten der Liste zulässiger/blockierter Mandanten".](tenant-allow-block-list.md)

URL-Links in den Textkörpern der E-Mail-Nachricht werden nicht umschließen, um die Auswirkungen der Kunden zu mindern.

### <a name="email-routing"></a>E-Mail-Routing

Bereiten Sie die entsprechenden Details vor, die Sie zum Einrichten der art der E-Mail-Route benötigen, einschließlich des Namens des eingehenden Connectors, der Ihre E-Mails weiterroutet. Wenn Sie nur Exchange Online Protection verwenden, verfügen Sie nicht über einen Connector.  [Informationen zum E-Mail-Fluss und zum E-Mail-Routing](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/mail-flow)

Folgende E-Mail-Routingszenarien werden unterstützt:

- **Drittanbieter und/oder** lokale Dienstanbieter: Der eingehende Connector, den Sie evaluieren möchten, verwendet einen Drittanbieter und/oder Sie verwenden eine Lösung für die lokale E-Mail-Sicherheit.
- **Microsoft Exchange Online Nur Schutz:** Der mandant, den Sie auswerten möchten, verwendet Office 365 für E-Mail-Sicherheit, und der Mail Exchange (MX)-Eintrag verweist auf Microsoft.

### <a name="email-security-gateway"></a>E-Mail-Sicherheitsgateway

Wenn Sie ein E-Mail-Sicherheitsgateway eines Drittanbieters verwenden, müssen Sie den Namen des Anbieters kennen. Wenn Sie eine lokale oder nicht unterstützte ESG verwenden, müssen Sie die öffentliche IP-Adresse(en) für die Geräte kennen.

Zu den unterstützten Drittanbieterpartnern gehören:

- Barracuda
- IronPort
- Mimecast
- Proofpoint
- Sophos
- Symantec
- Trend Micro

### <a name="scoping"></a>Bereichsdefinition

Die Auswertung kann auf einen eingehenden Connector begrenzt werden. Wenn kein Connector konfiguriert ist, können Administratoren im Auswertungsbereich Daten von einem beliebigen Benutzer in Ihrem Mandanten sammeln, um Defender für Office 365 auszuwerten.

## <a name="get-started-with-the-evaluation"></a>Erste Schritte mit der Evaluierung

Suchen Sie die Microsoft Defender für Office 365-Evaluierungsset-Up-Karte im Office 365 Security & Compliance Center ( von drei https://protection.office.com/homepage) Zugriffpunkten aus:

- Bedrohungsverwaltung > Dashboard
- Bedrohungsmanagement > Richtlinie
- Berichte > Dashboard

## <a name="setting-up-the-evaluation"></a>Einrichten der Evaluierung

Sobald Sie den Einrichtungsfluss für Ihre Auswertung starten, erhalten Sie zwei Routingoptionen. Abhängig von den Anforderungen an die Einrichtung und Auswertung des E-Mail-Routings in Ihrer Organisation können Sie auswählen, ob Sie einen Drittanbieter und/oder einen lokalen Dienstanbieter oder nur einen Microsoft Exchange Online.

- Wenn Sie einen Drittanbieter und/oder einen lokalen Dienstanbieter verwenden, müssen Sie im Dropdownmenü den Namen des Anbieters auswählen. Geben Sie die anderen connectorbezogenen Details an.

- Wählen Microsoft Exchange Online aus, wenn der MX-Eintrag auf Microsoft verweist und Sie über ein Exchange Online-Postfach verfügen.

Überprüfen Sie Ihre Einstellungen, und bearbeiten Sie sie bei Bedarf. Wählen Sie dann "Auswertung **erstellen" aus.** Sie sollten eine Bestätigungsmeldung erhalten, um anzugeben, dass die Einrichtung abgeschlossen ist.

Ihr Microsoft Defender für Office 365-Evaluierungsbericht wird einmal pro Tag generiert. Es kann bis zu 24 Stunden dauern, bis die Daten auffüllen.

### <a name="exchange-rules-optional"></a>Exchange-Regeln (optional)

Wenn Sie über ein vorhandenes Gateway verfügen, aktiviert das Aktivieren des Evaluierungsmodus die erweiterte Filterung für Connectors. Dadurch wird die Filtergenauigkeit verbessert, indem die IP-Adresse des eingehenden Absenders geändert wird. Dies kann die Filterbesprechungen ändern, und wenn Sie Exchange Online Protection nicht umgehen, kann dies die Zusicherung für bestimmte Nachrichten ändern. In diesem Fall sollten Sie die Filterung vorübergehend umgehen, um die Auswirkungen zu analysieren. Um dies zu umgehen, navigieren Sie zum Exchange Admin Center, und erstellen Sie eine Richtlinie von SCL -1 (wenn Sie noch keine haben). Details zu den Regelkomponenten und deren Funktionsweise finden Sie unter Nachrichtenflussregeln (Transportregeln) in Exchange Online.

## <a name="evaluate-capabilities"></a>Auswerten von Funktionen

Nachdem der Auswertungsbericht generiert wurde, sehen Sie, wie viele erweiterte Bedrohungslinks, erweiterte Bedrohungsanlagen und potenzielle Identitätswechsel in den E-Mails und Arbeitsbereichen für die Zusammenarbeit in Ihrer Organisation identifiziert wurden.

Sobald die Testversion abgelaufen ist, können Sie 90 Tage lang weiterhin auf den Bericht zugreifen. Es werden jedoch keine weiteren Informationen gesammelt. Wenn Sie Microsoft Defender für Office 365 nach Ablauf der Testversion weiterhin verwenden möchten, stellen Sie sicher, dass Sie ein kostenpflichtiges Abonnement für [Microsoft Defender für Office 365 (Plan 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)kaufen.

Sie können zu **"Einstellungen"** wechseln, um Ihr Routing zu aktualisieren oder die Auswertung jederzeit zu deaktivieren. Sie müssen jedoch den gleichen Einrichtungsprozess erneut durchgehen, wenn Sie sich entschließen, die Auswertung nach dem Deaktivieren fortzufahren.

## <a name="provide-feedback"></a>Feedback geben

Ihr Feedback hilft uns, Ihre Umgebung besser vor erweiterten Angriffen zu schützen. Teilen Sie Ihre Erfahrungen und Einblicke in Produktfunktionen und Bewertungsergebnisse.

Wählen **Sie "Feedback geben"** aus, um uns Ihre Meinung zu teilen.
