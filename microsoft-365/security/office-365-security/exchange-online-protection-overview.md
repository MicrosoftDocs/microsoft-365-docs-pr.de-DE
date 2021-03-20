---
title: Übersicht über Exchange Online Protection (EOP)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 09/18/2020
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Exchange Online Protection (EOP) Ihre lokale E-Mail-Organisation in eigenständigen und Hybridumgebungen schützen kann.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9aa2925ed5a9a6088fab81a09754b479740411cc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910834"
---
# <a name="exchange-online-protection-overview"></a>Exchange Online Protection im Überblick

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Exchange Online Protection (EOP) ist der cloudbasierte Filterdienst, der Ihre Organisation vor Spam und Schadsoftware schützt. EOP ist in allen Microsoft 365-Organisationen mit Exchange Online-Postfächern enthalten. EOP ist jedoch auch in den folgenden lokalen Szenarien verfügbar:

- **In einem eigenständigen Szenario:** EOP bietet cloudbasierten E-Mail-Schutz für Ihre lokale Exchange-Organisation oder jede andere lokale SMTP-E-Mail-Lösung.

- **In einer Hybridbereitstellung:** EOP kann konfiguriert werden, um Ihre E-Mail-Umgebung zu schützen und das E-Mail-Routing zu steuern, wenn Sie über eine Mischung aus lokalen und Cloudpostfächern verfügen.

In diesen Szenarien kann EOP die Verwaltung Ihrer E-Mail-Umgebung vereinfachen und viele der Lasten verringern, die durch die Verwaltung der lokalen Hardware und Software entstehen.

Im rest dieses Themas wird erläutert, wie EOP in eigenständigen und Hybridumgebungen funktioniert.

## <a name="how-eop-works"></a>Funktionsweise von EOP

Die Funktionsweise von EOP lässt sich am besten an der Verarbeitung eingehender E-Mails veranschaulichen:

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="Grafik von E-Mails aus dem Internet oder Kundenfeedback, die an EOP und über connection, Anti-Malware, Mailflow Rules-slash-Policy Filtering und Content Filtering übergeben werden, vor dem Urteil der Junk-E-Mail oder Quarantäne oder der Endbenutzer-E-Mail-Zustellung.":::

- Wenn eine eingehende Nachricht EOP eingibt, überläuft sie zunächst die Verbindungsfilterung, die die Reputation des Absenders überprüft. Die Mehrzahl der Spamnachrichten wird zu diesem Zeitpunkt beendet und von EOP abgelehnt. Weitere Informationen finden Sie unter [Konfigurieren der Richtlinie für Verbindungsfilter](configure-the-connection-filter-policy.md).

- Anschließend wird die Nachricht auf Anzeichen von Schadsoftware überprüft. Wenn schadsoftware in der Nachricht oder in den Anlagen gefunden wird, wird die Nachricht an einen Nur-Administrator-Quarantänespeicher geroutet. Weitere Informationen zum Konfigurieren von An malware finden Sie [hier.](configure-anti-malware-policies.md)

- Nachrichten werden über die Richtlinienfilterung fortgesetzt, wobei sie anhand von benutzerdefinierten Nachrichtenflussregeln (auch als Transportregeln bezeichnet) ausgewertet werden, die Sie in einer Vorlage erstellen oder erzwingen. Sie können beispielsweise eine Regel verwenden, die eine Benachrichtigung an einen Vorgesetzten sendet, wenn E-Mails von einem bestimmten Absender eintreffen. Prüfungen zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) werden auch an dieser Stelle durchgeführt (Exchange Enterprise CAL mit Diensten).

- Als Nächstes durchläuft die Nachricht die Inhaltsfilterung (auch als Antispam bekannt). Eine Nachricht, die von  diesem Filter als Spam oder Phishing ermittelt wird, kann unter anderem in quarantäne oder in den Junk-E-Mail-Ordner eines Benutzers gesendet werden. Weitere Informationen finden Sie [unter Konfigurieren von Antispamrichtlinien und](configure-your-spam-filter-policies.md) Konfigurieren von [Antiphishingrichtlinien.](configure-anti-phishing-policies-eop.md)

Jede Nachricht, die alle diese Schutzebenen erfolgreich übergibt, wird an den Empfänger übermittelt.

Weitere Informationen finden Sie unter [Reihenfolge und Rangfolge des E-Mail-Schutzes](how-policies-and-protections-are-combined.md).

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a>EOP-Pläne und -Features für lokale E-Mail-Organisationen

Die verfügbaren EOP-Abonnementpläne sind:

- **EOP eigenständig:** Sie registrieren sich bei EOP, um Ihre lokale E-Mail-Organisation zu schützen.

- **EOP-Features in Exchange Online:** Jedes Abonnement, das Exchange Online (eigenständig oder als Teil von Microsoft 365) enthält, verwendet EOP zum Schutz Ihrer Exchange Online-Postfächer.

- **Exchange Enterprise CAL mit Diensten**: Wenn Sie über eine lokale Exchange-Organisation verfügen, in der Sie zusätzliche Exchange Enterprise CAL mit Services-Lizenzen erworben haben, ist EOP Teil der enthaltenen Dienste.

Informationen zu Anforderungen, wichtigen Grenzwerten und der Verfügbarkeit von Features in allen EOP-Abonnementplänen finden Sie in der [Exchange Online Protection-Dienstbeschreibung](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

## <a name="setting-up-eop-for-on-premises-email-organizations"></a>Einrichten von EOP für lokale E-Mail-Organisationen

EOP-Bereitstellungen können einfach sein. Dies gilt insbesondere für kleine Organisationen mit einer Handvoll Regeln für die Richtlinientreue. Verfügen Sie jedoch über eine große Organisation mit mehreren Domänen, benutzerdefinierten Richtlinienregeln oder Hybridnachrichtenübermittlung, kann die Einrichtung einen höheren Planungs- und Zeitaufwand erfordern.

Sollten Sie bereits EOP erworben haben, können Sie mit den Hinweisen unter [Einrichten Ihres EOP-Diensts](set-up-your-eop-service.md) sicherstellen, dass Sie alle für die Konfiguration von EOP zum Schutz Ihrer Nachrichtenumgebung erforderlichen Schritte ausgeführt haben.

### <a name="eop-datacenters"></a>EOP-Datencenter

EOP wird in einem weltweiten Netzwerk von Rechenzentren ausgeführt, die die beste Verfügbarkeit bieten. Wenn beispielsweise ein Datencenter nicht mehr verfügbar ist, werden E-Mail-Nachrichten automatisch ohne Dienstunterbrechung an ein anderes Datencenter geroutet. Server in jedem Datencenter akzeptieren Nachrichten in Ihrem Auftrag und bieten eine Schicht der Trennung zwischen Ihrer Organisation und dem Internet, wodurch die Last auf Ihren Servern reduziert wird. Über dieses hochverf nkte Netzwerk kann Microsoft sicherstellen, dass E-Mails ihre Organisation zeitnah erreichen.

EOP führt einen Lastenausgleich zwischen Rechenzentren aus, jedoch nur innerhalb einer Region. Wenn Sie über eine Bereitstellung in einer bestimmten Region verfügen, werden alle Nachrichten mit dem E-Mail-Routing für diese Region verarbeitet. Die folgende Liste zeigt, wie regionales E-Mail-Routing für die EOP-Datencenter funktioniert:

- In Europa, dem Nahen Osten und Afrika (EMEA) befinden sich alle Exchange Online-Postfächer in EMEA-Rechenzentren, und alle Nachrichten werden zur EOP-Filterung über EMEA-Rechenzentren geleitet.

- In Asia-Pacific (APAC) befinden sich alle Exchange Online-Postfächer in APAC-Rechenzentren, und Nachrichten werden derzeit zur EOP-Filterung über APAC-Rechenzentren geroutet.

- In Amerika werden Dienste an den folgenden Standorten verteilt:

  - Südamerika: Exchange Online-Postfächer befinden sich in Rechenzentren in Brasilien und Chile. Alle Nachrichten werden für die EOP-Filterung über lokale Rechenzentren geroutet. Isolierte Nachrichten werden im Datencenter gespeichert, in dem sich der Mandant befindet.

  - Kanada: Exchange Online-Postfächer befinden sich in Rechenzentren in Kanada. Alle Nachrichten werden für die EOP-Filterung über lokale Rechenzentren geroutet. Isolierte Nachrichten werden im Datencenter gespeichert, in dem sich der Mandant befindet.

  - USA: Exchange Online-Postfächer befinden sich in US-Rechenzentren. Alle Nachrichten werden für die EOP-Filterung über lokale Rechenzentren geroutet. Isolierte Nachrichten werden im Datencenter gespeichert, in dem sich der Mandant befindet.

- Alle Exchange Online-Postfächer für die Government Community Cloud (GCC) befinden sich in US-Rechenzentren, und alle Nachrichten werden zur EOP-Filterung über US-Rechenzentren geleitet.

## <a name="eop-help-for-admins"></a>EOP-Hilfe für Administratoren

Der Hilfeinhalt für EOP-Administratoren umfasst die folgenden übergeordneten Kategorien:

- [Konfigurieren von EOP, Tag 1, für Microsoft Defender für Office 365-Administratoren:](protect-against-threats.md)Konfigurieren von EOP-Schutz- und Erkennungstools im Kern von Microsoft Defender für Office 365.

- [EOP-Features](eop-features.md): Stellt eine Liste der Features bereit, die in EOP verfügbar sind.

- [Einrichten Ihres EOP-Diensts:](set-up-your-eop-service.md)Enthält Schritte zum Einrichten Ihres EOP-Diensts und Links zu zusätzlichen Informationen.

- [Wechseln Sie von Google Postini, der Barracuda Spam and Virus Firewall](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)oder Cisco IronPort zu EOP: Beschreibt den Prozess für den Wechsel von einem anderen E-Mail-Schutzprodukt zu EOP.

- [Verwalten von Empfängern in eigenständigem EOP:](manage-recipients-in-eop.md)Beschreibt, wie E-Mail-Benutzer und -Gruppen in EOP verwaltet werden.

- [E-Mail-Fluss in EOP:](mail-flow-in-eop.md)Beschreibt, wie Sie benutzerdefinierte Nachrichtenflussszenarien mithilfe von Connectors konfigurieren, wie Sie dem Dienst zugeordnete Domänen verwalten und das Feature "Verzeichnisbasierte Edgeblockierung" (Directory Based Edge Blocking, DBEB) aktivieren.

- [Bewährte Methoden für die Konfiguration von EOP](best-practices-for-configuring-eop.md): Beschreibt empfohlene Konfigurationseinstellungen und Überlegungen für nach dem Einrichten und Bereitstellen Ihres Diensts.

- [Überwachungsberichte im eigenständigen EOP:](auditing-reports-in-eop.md)Beschreibt, wie Sie Überwachungsberichte verwenden, um Konfigurationsänderungen am Dienst nachverfolgt zu werden.

- [Antispam- und Anti-Malware-Schutz in EOP](anti-spam-and-anti-malware-protection.md): Beschreibt Spamfilterung und Schadsoftwarefilterung und zeigt, wie sie an die Anforderungen Ihrer Organisation angepasst werden. Außerdem werden Aufgaben beschrieben, die Administratoren und Endbenutzer für isolierte Nachrichten ausführen können.

- [Berichterstellung und Nachrichtenverfolgung in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md): Beschreibt die verfügbaren Berichte und Problembehandlungstools.

- [Exchange Admin Center im eigenständigen EOP:](exchange-admin-center-in-exchange-online-protection-eop.md)Beschreibt, wie Sie auf die Verwaltungsschnittstelle des Exchange Admin Center (EAC) zugreifen und diese navigieren, um Ihren EOP-Dienst zu verwalten.

- [Exchange Online Protection PowerShell](/powershell/exchange/exchange-online-protection-powershell): Enthält Informationen zur Remote-PowerShell, mit der Sie Ihren EOP-Dienst über die Befehlszeile verwalten können.

- [Hilfe und Support für EOP](help-and-support-for-eop.md) Informationen zum Anfordern von Hilfe und technischem Support.