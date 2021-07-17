---
title: Überprüfen von Architekturanforderungen und Planungskonzepten für Microsoft Defender für Office 365- und Konstruktions-, Gebäude- und Designframeworks
description: Das technische Diagramm für Microsoft Defender für Office 365 in Microsoft 365 Defender hilft Ihnen, die Identität in Microsoft 365 zu verstehen, bevor Sie Ihre Testumgebung oder Pilotumgebung erstellen.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 07/01/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 15c84921dcfb4644241cf83ce4ffb6403180b9d4
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458280"
---
# <a name="review-microsoft-defender-for-office-365-architecture-requirements-and-key-concepts"></a>Überprüfen von Microsoft Defender auf Office 365 Architekturanforderungen und Schlüsselkonzepte


**Gilt für:**
- Microsoft 365 Defender

Dieser Artikel ist [Schritt 1 von 3](eval-defender-office-365-overview.md) beim Einrichten der Evaluierungsumgebung für Microsoft Defender für Office 365. Weitere Informationen zu diesem Prozess finden Sie im [Übersichtsartikel.](eval-defender-office-365-overview.md)

Bevor Sie Defender für Office 365 aktivieren, müssen Sie die Architektur verstehen und die Anforderungen erfüllen. In diesem Artikel werden die Architektur, die wichtigsten Konzepte und die Voraussetzungen beschrieben, die Ihre Exchange Online Umgebung erfüllen muss.

## <a name="understand-the-architecture"></a>Grundlegendes zur Architektur

Das folgende Diagramm veranschaulicht die Basisarchitektur für Microsoft Defender für Office, die ein SMTP-Gateway eines Drittanbieters oder eine lokale Integration umfassen kann. Hybrid koexistenzszenarien (d. h. Produktionspostfächer sind sowohl lokal als auch online) erfordern komplexere Konfigurationen und werden in diesem Artikel oder in den Evaluierungsleitlinien nicht behandelt.

![Architektur für Microsoft Defender für Office 365](../../media/defender/m365-defender-office-architecture.png)

In der folgenden Tabelle wird diese Abbildung beschrieben.

|Call-out  |Beschreibung  |
|---------|---------|
|1     | Der Hostserver für den externen Absender führt in der Regel eine öffentliche DNS-Suche nach einem MX-Eintrag durch, der den Zielserver zum Weiterleiten der Nachricht bereitstellt.  Dieser Verweis kann entweder Exchange Online (EXO) direkt oder ein SMTP-Gateway sein, das für die Weiterleitung an EXO konfiguriert wurde.  |
|2     | Exchange Online Protection die eingehende Verbindung aushandelt und überprüft und die Nachrichtenkopfzeilen und -inhalte überprüft, um zu ermitteln, welche zusätzlichen Richtlinien, Markierungen oder Verarbeitungen erforderlich sind.  |
|3     | Exchange Online lässt sich in Microsoft Defender für Office 365 integrieren, um erweiterten Bedrohungsschutz, Risikominderung und Behebung zu bieten. |
|4      | Eine Nachricht, die nicht bösartig, blockiert oder isoliert ist, wird verarbeitet und an den Empfänger in EXO übermittelt, wo Benutzereinstellungen im Zusammenhang mit Junk-E-Mails, Postfachregeln oder anderen Einstellungen ausgewertet und ausgelöst werden. |
|5      | Die Integration in lokales Active Directory kann mithilfe von Azure AD-Verbinden aktiviert werden, um E-Mail-aktivierte Objekte und Konten zu synchronisieren und für Azure Active Directory und letztendlich Exchange Online bereitzustellen. |
|6      | Bei der Integration einer lokalen Umgebung wird dringend empfohlen, einen Exchange Server für die unterstützte Verwaltung von E-Mail-bezogenen Attributen, Einstellungen und Konfigurationen zu verwenden. |
|7      | Microsoft Defender für Office 365 teilt Microsoft 365 Defender Signale für die erweiterte Erkennung und Reaktion (XDR) mit.|

Die lokale Integration ist üblich, aber optional. Wenn Ihre Umgebung rein cloudgeschützt ist, funktioniert diese Anleitung auch für Sie.

## <a name="understand-key-concepts"></a>Grundlegendes zu den wichtigsten Konzepten

In der folgenden Tabelle sind wichtige Konzepte aufgeführt, die beim Auswerten, Konfigurieren und Bereitstellen von MDO zu verstehen sind.


|Konzept  |Beschreibung |Weitere Informationen  |
|---------|---------|---------|
|Exchange Online Protection      |    Exchange Online Protection (EOP) ist der cloudbasierte Filterdienst, der Ihre Organisation vor Spam- und Schadsoftware-E-Mails schützt. EOP ist in allen Microsoft 365 Lizenzen enthalten, die Exchange Online enthalten.     |   [Exchange Online Protection im Überblick](../office-365-security/exchange-online-protection-overview.md)      |
|Schutz vor Schadsoftware     |    Organisationen mit Postfächern in EXO werden automatisch vor Schadsoftware geschützt.     |  [Antischadsoftwareschutz in EOP](../office-365-security/anti-malware-protection.md)       |
|Antispamschutz     |   Organisationen mit Postfächern in EXO werden automatisch vor Junk-E-Mails und Spamrichtlinien geschützt.      |  [Antispamschutz in EOP](../office-365-security/anti-spam-protection.md)       |
|Antiphishingschutz |  MDO bietet einen erweiterten Antiphishingschutz im Zusammenhang mit Spear-Phishing, Whaling, Ransomware und anderen bösartigen Aktivitäten.   | [Zusätzlicher Antiphishingschutz in Microsoft Defender für Office 365](../office-365-security/anti-phishing-protection.md)   |
|Antispoofingschutz     |   EOP enthält Features zum Schutz Ihrer Organisation vor gefälschten Absendern.      |   [Schutz vor Spoofing in EOP](../office-365-security/anti-spoofing-protection.md)      |
|Sichere Anlagen     |   Tresor Anlagen bieten eine zusätzliche Schutzebene, indem sie eine virtuelle Umgebung verwenden, um Anlagen in E-Mail-Nachrichten zu überprüfen und zu "detonieren", bevor sie zugestellt werden.      |   [Tresor Anlagen in Microsoft Defender für Office 365](../office-365-security/safe-attachments.md)      |
|Tresor Anlagen für SharePoint, OneDrive und Microsoft Teams     |    Darüber hinaus bietet Tresor Anlagen für SharePoint, OneDrive und Microsoft Teams eine zusätzliche Schutzebene für Dateien, die in Cloudspeicherrepositorys hochgeladen wurden.     |  [Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams](../office-365-security/mdo-for-spo-odb-and-teams.md)       |
|Sichere Links     | Tresor Links sind ein Feature, das URL-Überprüfung und -Umschreibung in eingehenden E-Mail-Nachrichten ermöglicht und die Überprüfung dieser Links anbietet, bevor sie übermittelt oder angeklickt werden.        |   [Tresor Links in Microsoft Defender für Office 365](../office-365-security/safe-links.md)      |
|    |         |         |

Ausführlichere Informationen zu den in Microsoft Defender für Office enthaltenen Funktionen finden Sie unter [Microsoft Defender für Office 365 Dienstbeschreibung.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

## <a name="review-architecture-requirements"></a>Überprüfen der Architekturanforderungen
Eine erfolgreiche MDO-Evaluierung oder ein erfolgreiches Produktionspilotprojekt setzt die folgenden Voraussetzungen voraus:
- Alle Ihre Empfängerpostfächer befinden sich derzeit in Exchange Online.
- Ihr öffentlicher MX-Eintrag wird direkt zu EOP oder einem SMTP-Gateway eines Drittanbieters aufgelöst, das eingehende externe E-Mails direkt an EOP weiterleitet.
- Ihre primäre E-Mail-Domäne ist in Exchange Online als *autoritativ* konfiguriert.
- Sie haben die *verzeichnisbasierte Edgeblockierung (Directory Based Edge Blocking,* DBEB) nach Bedarf erfolgreich bereitgestellt und konfiguriert. Weitere Informationen finden Sie unter [Verwenden der verzeichnisbasierten Edgeblockierung zum Ablehnen von Nachrichten, die an ungültige Empfänger gesendet werden](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).

> [!IMPORTANT]
> Wenn diese Anforderungen nicht anwendbar sind oder Sie sich noch in einem Hybrid-Koexistenzszenario befinden, kann eine Microsoft Defender für Office 365 Evaluierung komplexere oder komplexere Konfigurationen erfordern, die in diesem Leitfaden nicht vollständig behandelt werden.

## <a name="siem-integration"></a>SIEM-Integration

Sie können Microsoft Defender für Office 365 in Azure Sentinel integrieren, um Sicherheitsereignisse in Ihrer Organisation umfassender zu analysieren und Playbooks für eine effektive und sofortige Reaktion zu erstellen. Weitere Informationen finden Sie unter [Verbinden Warnungen von Microsoft Defender für Office 365.](/azure/sentinel/connect-office-365-advanced-threat-protection)

Microsoft Defender für Office 365 kann auch mithilfe der [Office 365 Activity Management-API](/office/office-365-management-api/office-365-management-activity-api-reference)in andere SIEM-Lösungen (Security Information and Event Management) integriert werden.

## <a name="next-steps"></a>Nächste Schritte

Schritt 2 von 3: [Aktivieren der Evaluierungsumgebung von Microsoft Defender für Office 365](eval-defender-office-365-enable-eval.md)

Kehren Sie zur Übersicht über [das Auswerten von Microsoft Defender für Office 365](eval-defender-office-365-overview.md)

Kehren Sie zur Übersicht für [Evaluierungs- und Pilot-Microsoft 365 Defender](eval-overview.md) 

