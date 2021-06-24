---
title: Auswerten von Microsoft Defender für Office 365
description: Defender für Office 365 im Evaluierungsmodus erstellt Defender für Office 365 E-Mail-Richtlinien, die Bewertungen protokollieren, z. B. Schadsoftware, aber nicht auf Nachrichten reagieren.
keywords: auswerten Office 365, Microsoft Defender für Office 365, Office 365-Evaluierung, Office 365, Microsoft Defender, Microsoft Defender für Endpunkt testen
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
ms.openlocfilehash: 0cf2d19b06dc1cce154785d8c42742fdc12d3259
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108331"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a>Auswerten von Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Die Evaluierung von Microsoft Defender für Office 365 befindet sich in der öffentlichen Vorschau. Diese Vorschauversion wird ohne Vereinbarung zum Servicelevel bereitgestellt. Bestimmte Features werden möglicherweise nicht unterstützt oder verfügen über eingeschränkte Funktionen.

Die Durchführung einer sorgfältigen Sicherheitsproduktbewertung kann Ihnen helfen, fundierte Entscheidungen in Bezug auf Upgrades und Einkäufe zu treffen. Es hilft, die Funktionen des Sicherheitsprodukts auszuprobieren, um zu bewerten, wie es Ihrem Sicherheitsteam bei ihren täglichen Aufgaben helfen kann.

Die Evaluierungsumgebung von [Microsoft Defender für Office 365](defender-for-office-365.md) wurde entwickelt, um die Komplexität der Geräte- und Umgebungskonfiguration zu vermeiden, sodass Sie sich auf die Bewertung der Funktionen von Microsoft Defender für Office 365 konzentrieren können. Im Evaluierungsmodus können alle Nachrichten, die an Exchange Online Postfächer gesendet werden, ausgewertet werden, ohne mx-Einträge auf Microsoft zu verweisen. Das Feature gilt nur für den E-Mail-Schutz und nicht für Office Clients wie Word, SharePoint oder Teams.

Wenn Sie noch nicht über eine Lizenz verfügen, die Microsoft Defender für Office 365 unterstützt, können Sie eine [kostenlose 30-Tage-Evaluierung](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) starten und die Funktionen im Microsoft 365 Defender-Portal unter <https://security.microsoft.com> testen. Sie werden die schnelle Einrichtung genießen und sie bei Bedarf ganz einfach deaktivieren.

> [!NOTE]
> Wenn Sie sich im Microsoft 365 Defender-Portal ( ) befinden, <https://security.microsoft.com> können Sie hier einen Defender für Office 365 Evaluierung starten: **E-Mail-& Richtlinien** für die Zusammenarbeit & Seite \> **"Regelbedrohungsrichtlinien"** im Abschnitt \>  \> "Evaluierungsmodus".  \> 

## <a name="how-the-evaluation-works"></a>Funktionsweise der Auswertung

Defender für Office 365 im Evaluierungsmodus erstellt Defender für Office 365 E-Mail-Richtlinien, die Bewertungen protokollieren, z. B. Schadsoftware, aber nicht auf Nachrichten reagieren. Sie müssen ihre MX-Eintragskonfiguration nicht ändern.

Im [Evaluierungsmodus](safe-attachments.md)werden Tresor Anlagen, [Tresor Links](safe-links.md)und [Postfachintelligenz-basierte Identitätswechselrichtlinien](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) in Ihrem Auftrag eingerichtet. Alle Defender für Office 365 Richtlinien werden im Nichterzwingungsmodus im Hintergrund erstellt und sind für Sie nicht sichtbar.

Im Rahmen des Setups wird im Evaluierungsmodus auch die [erweiterte Filterung für Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)konfiguriert. Die Filtergenauigkeit wird verbessert, indem IP-Adresse und Absenderinformationen beibehalten werden, die andernfalls verloren gehen, wenn E-Mails über ein E-Mail-Sicherheitsgateway (ESG) vor Defender für Office 365 übergeben werden. Die erweiterte Filterung für Connectors verbessert auch die Filtergenauigkeit für Ihre vorhandenen Antispam- und Antiphishingrichtlinien für Exchange Online Protection (EOP).

Die erweiterte Filterung für Connectors verbessert die Filtergenauigkeit, kann jedoch die Zustellbarkeit für bestimmte Nachrichten ändern, wenn Sie eine ESG vor Defender für Office 365 haben und derzeit die EOP-Filterung nicht umgehen. Die Auswirkungen sind auf EOP-Richtlinien beschränkt. MDO-Richtlinien, die im Rahmen der Auswertung eingerichtet wurden, werden im Nichterzwingungsmodus erstellt. Um potenzielle Auswirkungen auf die Produktion zu minimieren, können Sie die gesamte EOP-Filterung umgehen, indem Sie eine Nachrichtenflussregel (auch als Transportregel bezeichnet) erstellen, um die Spam-Konfidenzstufe (Spam Confidence Level, SCL) von Nachrichten auf -1 festzulegen. Weitere Informationen finden Sie unter [Verwenden von Nachrichtenflussregeln zum Festlegen der Spamzustimmungsstufe (Spam Confidence Level, SCL) in Nachrichten in Exchange Online.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)  

Wenn der Auswertungsmodus eingerichtet ist, wird täglich ein Bericht mit bis zu 90 Tagen Daten aktualisiert, in dem die Nachrichten quantifiziert werden, die blockiert worden wären, wenn die Richtlinien implementiert worden wären (z. B. Löschen, Senden an Junk, Quarantäne). Berichte werden für alle Defender für Office 365 und EOP-Erkennungen generiert. Sie werden pro Erkennungstechnologie (z. B. Identitätswechsel) aggregiert und können nach Zeitraum gefiltert werden. Darüber hinaus können Nachrichtenberichte bei Bedarf erstellt werden, um benutzerdefinierte Pivots oder Deep Dive-Nachrichten mithilfe von Explorer zu erstellen.

Mit der vereinfachten Einrichtungsoberfläche können Sie sich auf Folgendes konzentrieren:

- Ausführen der Auswertung
- Abrufen eines detaillierten Berichts
- Analysieren des Berichts auf Aktion
- Darstellen des Bewertungsergebnisses

## <a name="before-you-begin"></a>Bevor Sie beginnen

### <a name="licensing"></a>Lizenzierung

Um auf die Auswertung zugreifen zu können, müssen Sie die Lizenzierungsanforderungen erfüllen. Eine der folgenden Lizenzen funktioniert:

- Microsoft Defender für Office 365 Plan 1
- Microsoft Defender für Office 365 Plan 2
- Microsoft 365 E5, Microsoft 365 E5 Security
- Office 365 E5

Wenn Sie nicht über eine dieser Lizenzen verfügen, müssen Sie eine Testlizenz anfordern.

#### <a name="trial"></a>Testversion

Um eine Testlizenz für Microsoft Defender für Office 365 zu erhalten, benötigen Sie die **Rolle "Abrechnungsadministrator"** oder **"Globaler Administrator".** Fordern Sie die Berechtigung von einer Person an, die über die Rolle "Globaler Administrator" verfügt. [Informationen zu Abonnements und Lizenzen](../../commerce/licenses/subscriptions-and-licenses.md)

Sobald Sie über die richtige Rolle verfügen, wird empfohlen, eine Testlizenz für Microsoft Defender für Office 365 (Plan 2) im Microsoft 365 Admin Center zu erhalten, indem Sie zu Abrechnung > Dienste kaufen wechseln. Die Testversion umfasst eine 30-tägige kostenlose Testversion für 25 Lizenzen. [Rufen Sie eine Testversion für Microsoft Defender für Office 365 (Plan 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)ab.

Sie verfügen über ein 30-Tage-Fenster mit der Auswertung, um fortgeschrittene Bedrohungen zu überwachen und zu melden. Sie haben auch die Möglichkeit, ein kostenpflichtiges Abonnement zu kaufen, wenn Sie die vollständigen Defender for Office 365-Funktionen nutzen möchten.

### <a name="roles"></a>Rollen

**Exchange Online Rollen sind erforderlich,** um Defender für Office 365 im Evaluierungsmodus einzurichten. Das Zuweisen einer Microsoft 365 Compliance- oder Sicherheitsadministratorrolle funktioniert nicht.

- [Informationen zu Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo)
- [Informationen zum Zuweisen von Administratorrollen](../../admin/add-users/assign-admin-roles.md)

Die folgenden Rollen sind erforderlich:

|Aufgabe|Rolle (in Exchange Online)|
|---|---|
|Erhalten Sie eine kostenlose Testversion oder kaufen Sie Microsoft Defender für Office 365 (Plan 2)|Rolle "Abrechnungsadministrator" ODER "Globaler Administrator"|
|Erstellen einer Evaluierungsrichtlinie|Rolle "Remote- und akzeptierte Domänen"; Rolle "Sicherheitsadministrator"|
|Bearbeiten der Evaluierungsrichtlinie|Rolle "Remote- und akzeptierte Domänen"; Rolle "Sicherheitsadministrator"|
|Evaluierungsrichtlinie löschen|Rolle "Remote- und akzeptierte Domänen"; Rolle "Sicherheitsadministrator" |
|Bewertungsbericht anzeigen|Rolle "Sicherheitsadministrator" oder "Leserrolle "Sicherheit"|
|

### <a name="enhanced-filtering"></a>Erweiterte Filterung

Ihre Exchange Online Protection-Richtlinien, z. B. Massen- und Spamschutz, bleiben unverändert. Bei der Auswertung wird jedoch die erweiterte Filterung für Connectors aktiviert, was sich möglicherweise auf den Nachrichtenfluss und Exchange Online Protection Richtlinien auswirkt, sofern sie nicht umgangen wird.

Die erweiterte Filterung für Connectors ermöglicht Mandanten die Verwendung von Antispoofingschutz. Antispoofing wird nicht unterstützt, wenn Sie ein E-Mail-Sicherheitsgateway (ESG) verwenden, ohne die erweiterte Filterung für Connectors aktiviert zu haben.

### <a name="urls"></a>URLs

URLs werden während des Nachrichtenflusses detoniert. Wenn Sie nicht möchten, dass bestimmte URLs detoniert werden, verwalten Sie Ihre Liste der zulässigen URLs entsprechend. Weitere Informationen finden Sie unter [Verwalten der Mandanten-Zulassungs-/Sperrliste.](tenant-allow-block-list.md)

URL-Links in den E-Mail-Nachrichtentexten werden nicht umbrochen, um die Auswirkungen auf die Kunden zu mindern.

### <a name="email-routing"></a>E-Mail-Routing

Bereiten Sie die entsprechenden Details vor, die Sie zum Einrichten der aktuellen Weiterleitung Ihrer E-Mails benötigen, einschließlich des Namens des eingehenden Connectors, der Ihre E-Mails weiterleitet. Wenn Sie nur Exchange Online Protection verwenden, haben Sie keinen Connector.  [Informationen zum Nachrichtenfluss und zum E-Mail-Routing](/office365/servicedescriptions/exchange-online-service-description/mail-flow)

Zu den unterstützten E-Mail-Routingszenarien gehören:

- **Drittanbieterpartner und/oder lokaler Dienstanbieter:** Der eingehende Connector, den Sie auswerten möchten, verwendet einen Drittanbieter und/oder Sie verwenden eine Lösung für die lokale E-Mail-Sicherheit.
- **nur Microsoft Exchange Online Schutz:** Der Mandant, den Sie auswerten möchten, verwendet Office 365 für die E-Mail-Sicherheit, und der MX-Eintrag (Mail Exchange) verweist auf Microsoft.

### <a name="email-security-gateway"></a>E-Mail-Sicherheitsgateway

Wenn Sie ein E-Mail-Sicherheitsgateway eines Drittanbieters (E-Mail Security Gateway, ESG) verwenden, müssen Sie den Namen des Anbieters kennen. Wenn Sie lokale oder nicht unterstützte ESG-Anbieter verwenden, müssen Sie die öffentlichen IP-Adressen für die Geräte kennen.

Zu den unterstützten Drittanbietern gehören:

- Barracuda
- Ironport
- Mimecast
- Proofpoint
- Sophos
- Symantec
- Trend Micro

### <a name="scoping"></a>Bereichsdefinition

Sie können die Auswertung auf einen eingehenden Connector beschränken. Wenn kein Connector konfiguriert ist, ermöglicht der Auswertungsbereich Administratoren, Daten von jedem Benutzer in Ihrem Mandanten zu erfassen, um Defender für Office 365 auszuwerten.

## <a name="get-started-with-the-evaluation"></a>Erste Schritte mit der Auswertung

Suchen Sie die Setupkarte für Microsoft Defender für Office 365-Evaluierung im Microsoft 365 Defender-Portal ( <https://security.microsoft.com> ) von drei Zugriffspunkten aus:

- **Endpunkte** \> **Sicherheitsrisikoverwaltung** \> **Dashboard** ( <https://security.microsoft.com/tvm_dashboard> )
- **E-Mail-& Zusammenarbeit** \> **Richtlinien & Regeln** \> **Bedrohungsrichtlinien** ( <https://security.microsoft.com/threatpolicy> )
- **Berichte** \> **E-Mail-& Zusammenarbeit** \> **E-Mail & Zusammenarbeitsberichte** ( <https://security.microsoft.com/emailandcollabreport> )

## <a name="setting-up-the-evaluation"></a>Einrichten der Auswertung

Nachdem Sie den Einrichtungsfluss für Ihre Auswertung gestartet haben, erhalten Sie zwei Routingoptionen. Abhängig von den Anforderungen für die Einrichtung und Auswertung des E-Mail-Routings In Ihrer Organisation können Sie auswählen, ob Sie einen Drittanbieter und/oder lokalen Dienstanbieter verwenden oder nur Microsoft Exchange Online.

- Wenn Sie einen Drittanbieter und/oder lokalen Dienstanbieter verwenden, müssen Sie den Namen des Anbieters im Dropdownmenü auswählen. Geben Sie die anderen connectorbezogenen Details an.

- Wählen Sie Microsoft Exchange Online aus, wenn der MX-Eintrag auf Microsoft verweist und Sie über ein Exchange Online Postfach verfügen.

Überprüfen Sie Ihre Einstellungen, und bearbeiten Sie sie bei Bedarf. Wählen Sie dann **Auswertung erstellen** aus. Sie sollten eine Bestätigungsmeldung erhalten, um anzugeben, dass die Einrichtung abgeschlossen ist.

Ihr Microsoft Defender für Office 365 Evaluierungsbericht wird einmal pro Tag generiert. Es kann bis zu 24 Stunden dauern, bis die Daten aufgefüllt wurden.

### <a name="exchange-mail-flow-rules-optional"></a>Exchange Nachrichtenflussregeln (optional)

Wenn Sie über ein vorhandenes Gateway verfügen, aktiviert das Aktivieren des Evaluierungsmodus die erweiterte Filterung für Connectors. Dieses Feature verbessert die Filtergenauigkeit, indem die IP-Adresse des eingehenden Absenders geändert wird. Dieses Feature kann die Filterbewertungen ändern, und wenn Sie Exchange Online Protection nicht umgehen, kann dies die Zustellbarkeit für bestimmte Nachrichten ändern. In diesem Fall sollten Sie die Filterung vorübergehend umgehen, um die Auswirkungen zu analysieren. Um die Filterung zu umgehen, öffnen Sie das Exchange Admin Center (EAC), <https://admin.exchange.microsoft.com> und erstellen Sie eine Nachrichtenflussregel, die die SCL von Nachrichten auf -1 festlegt (falls Sie noch keine haben). Anweisungen finden Sie unter [Verwenden von Nachrichtenflussregeln, um die Spam-Konfidenzstufe (Spam Confidence Level, SCL) in Nachrichten in Exchange Online festzulegen.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)

## <a name="evaluate-capabilities"></a>Auswerten von Funktionen

Nachdem der Evaluierungsbericht generiert wurde, sehen Sie, wie viele erweiterte Bedrohungslinks, erweiterte Bedrohungsanlagen und potenzielle Identitätswechsel in den E-Mails und Arbeitsbereichen für die Zusammenarbeit in Ihrer Organisation identifiziert wurden.

Sobald die Testversion abgelaufen ist, können Sie 90 Tage lang auf den Bericht zugreifen. Es werden jedoch keine weiteren Informationen gesammelt. Wenn Sie Microsoft Defender weiterhin für Office 365 verwenden möchten, nachdem Ihre Testversion abgelaufen ist, stellen Sie sicher, dass Sie [ein kostenpflichtiges Abonnement für Microsoft Defender für Office 365 (Plan 2) kaufen.](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA)

Sie können zu **Einstellungen** wechseln, um Ihr Routing zu aktualisieren oder Die Auswertung jederzeit zu deaktivieren. Sie müssen jedoch den gleichen Einrichtungsprozess erneut durchlaufen, wenn Sie sich entscheiden, die Auswertung fortzusetzen, nachdem Sie sie deaktiviert haben.

## <a name="provide-feedback"></a>Feedback geben

Ihr Feedback hilft uns, Ihre Umgebung besser vor fortgeschrittenen Angriffen zu schützen. Teilen Sie Ihre Erfahrungen und Aufrufe von Produktfunktionen und Bewertungsergebnissen.

Wählen Sie **"Feedback geben",** um uns mitzuteilen, was Sie denken.
