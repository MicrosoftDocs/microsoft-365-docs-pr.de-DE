---
title: Übersicht über Exchange Online Schutz (EoP)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Exchange Online Protection (EoP) zum Schutz Ihrer lokalen e-Mail-Organisation in eigenständigen und Hybriden Umgebungen beitragen kann.
ms.openlocfilehash: a3f71ea5366224465cdaf3922c6c467fcb49f3cc
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616986"
---
# <a name="exchange-online-protection-overview"></a>Exchange Online Protection im Überblick

Exchange Online Protection (EoP) ist ein Cloud-basierter Filterdienst, der Ihre Organisation vor Spam und Schadsoftware schützen kann. EoP ist in allen Microsoft 365-Organisationen mit Exchange Online-Postfächern enthalten.

EoP ist jedoch auch in den folgenden lokalen Szenarien verfügbar:

- **In einem eigenständigen Szenario**: EoP bietet Cloud-basierten e-Mail-Schutz für Ihre lokale Exchange-Organisation oder eine andere lokale SMTP-e-Mail-Lösung.

- **In einer hybridbereitstellung**: EoP kann konfiguriert werden, um Ihre e-Mail-Umgebung zu schützen und das e-Mail-Routing zu steuern, wenn Sie eine Mischung aus lokalen und Cloud-Postfächern haben.

In diesen Szenarien kann EoP die Verwaltung Ihrer e-Mail-Umgebung vereinfachen und viele der Belastungen verringern, die mit der Wartung lokaler Hardware und Software verbunden sind.

Im weiteren Verlauf dieses Themas wird erläutert, wie EoP in eigenständigen und Hybriden Umgebungen funktioniert.

## <a name="how-eop-works"></a>Funktionsweise von EOP

Die Funktionsweise von EOP lässt sich am besten an der Verarbeitung eingehender E-Mails veranschaulichen:

![E-Mail-Prozessdiagramm](../../media/emailprocessingineop1.png)

- Eine eingehende Nachricht übergibt zunächst die Verbindungsfilterung, die die Reputation des Absenders überprüft und die Nachricht auf Schadsoftware überprüft. Die Mehrzahl der Spam-Mails wird an dieser Position angehalten und von EoP gelöscht. Weitere Informationen finden Sie unter [Konfigurieren der Richtlinie für Verbindungsfilter](configure-the-connection-filter-policy.md).

- Nachrichten werden durch die Richtlinienfilterung fortgesetzt, wobei Nachrichten anhand von benutzerdefinierten Nachrichtenfluss Regeln (auch bekannt als Transportregeln) ausgewertet werden, die Sie aus einer Vorlage erstellen oder erzwingen. Beispielsweise können Sie eine Regel haben, die eine Benachrichtigung an einen Vorgesetzten sendet, wenn e-Mails von einem bestimmten Absender eintreffen. An dieser Position (Exchange Enterprise CAL with Services) treten auch DLP-Prüfungen (Data Loss Prevention, Verhinderung von Datenverlust) auf.

- Als nächstes passieren Nachrichten die Anti-Spam-Filterung (auch bekannt als Inhaltsfilterung). Eine Nachricht, die als Spam festgelegt wurde, kann unter anderem an den Junk-e-Mail-Ordner eines Benutzers oder an die Quarantäne gesendet werden. Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md).

- Nachdem eine Nachricht alle diese Schutzschichten erfolgreich übergeben hat, wird Sie an den Empfänger übermittelt.

Weitere Informationen finden Sie unter [Reihenfolge und Rangfolge des e-Mail-Schutzes](how-policies-and-protections-are-combined.md).

### <a name="eop-datacenters"></a>EOP-Datencenter

EoP wird in einem weltweiten Netzwerk von Rechenzentren ausgeführt, die für die beste Verfügbarkeit vorgesehen sind. Wenn beispielsweise ein Rechenzentrum nicht mehr verfügbar ist, werden e-Mail-Nachrichten ohne Unterbrechung des Diensts automatisch an ein anderes Rechenzentrum weitergeleitet. Server in jedem Datencenter akzeptieren Nachrichten in Ihrem Namen und bieten eine Schicht Trennung zwischen Ihrer Organisation und dem Internet, wodurch die Last auf Ihren Servern reduziert wird. Mithilfe dieses hoch verfügbaren Netzwerks kann Microsoft sicherstellen, dass e-Mails in Ihrer Organisation rechtzeitig erreicht werden.

EOP führt einen Lastenausgleich zwischen Rechenzentren aus, jedoch nur innerhalb einer Region. Wenn Sie über eine Bereitstellung in einer bestimmten Region verfügen, werden alle Nachrichten mit dem E-Mail-Routing für diese Region verarbeitet. Die folgende Liste zeigt, wie regionales E-Mail-Routing für die EOP-Datencenter funktioniert:

- In Europa, dem Nahen Osten und Afrika (EMEA) befinden sich alle Exchange Online-Postfächer in EMEA-Rechenzentren, und alle Nachrichten werden zur EOP-Filterung über EMEA-Rechenzentren geleitet.

- Im asiatisch-pazifischen Raum (APAC) befinden sich alle Exchange Online Postfächer in APAC-Rechenzentren, und Nachrichten werden derzeit über APAC-Rechenzentren für die EoP-Filterung weitergeleitet.

- In Nord-und Südamerika befinden sich alle Exchange Online Postfächer in US-Rechenzentren, mit Ausnahme von Südamerika, in dem Rechenzentren in Brasilien und Chile verwendet werden, und in Kanada, in dem Rechenzentren in Kanada verwendet werden. Alle e-Mail-Nachrichten, einschließlich Nachrichten für Kunden in Südamerika und Kanada, werden über lokale Rechenzentren für die EoP-Filterung weitergeleitet. in Quarantäne befindliche e-Mails werden im Rechenzentrum gespeichert, in dem sich der Mandant befindet.

- Alle Exchange Online-Postfächer für die Government Community Cloud (GCC) befinden sich in US-Rechenzentren, und alle Nachrichten werden zur EOP-Filterung über US-Rechenzentren geleitet.

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a>EoP-Pläne und-Features für lokale e-Mail-Organisationen

Die verfügbaren EoP-Abonnement Pläne lauten wie folgt:

- **EoP Standalone**: Sie registrieren sich in EoP, um Ihre lokale e-Mail-Organisation zu schützen.

- **EoP-Features in Exchange Online**: jedes Abonnement, das Exchange Online enthält (eigenständig oder als Teil von Microsoft 365), verwendet EoP, um Ihre Exchange Online Postfächer zu schützen.

- **Exchange Enterprise CAL mit Diensten**: Wenn Sie über eine lokale Exchange-Organisation verfügen, in der Sie zusätzliche Lizenzen für Exchange Enterprise CAL mit Diensten erworben haben, ist EoP Teil der enthaltenen Dienste.

Informationen zu Anforderungen, wichtigen Grenzwerten und Verfügbarkeit von Funktionen in allen EoP-Abonnement Plänen finden Sie in der [Beschreibung des Exchange Online Protection-Diensts](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

## <a name="setting-up-eop-for-on-premises-email-organizations"></a>Einrichten von EoP für lokale e-Mail-Organisationen

EOP-Bereitstellungen können einfach sein. Dies gilt insbesondere für kleine Organisationen mit einer Handvoll Regeln für die Richtlinientreue. Verfügen Sie jedoch über eine große Organisation mit mehreren Domänen, benutzerdefinierten Richtlinienregeln oder Hybridnachrichtenübermittlung, kann die Einrichtung einen höheren Planungs- und Zeitaufwand erfordern.

Sollten Sie bereits EOP erworben haben, können Sie mit den Hinweisen unter [Einrichten Ihres EOP-Diensts](set-up-your-eop-service.md) sicherstellen, dass Sie alle für die Konfiguration von EOP zum Schutz Ihrer Nachrichtenumgebung erforderlichen Schritte ausgeführt haben.

## <a name="eop-help-for-admins"></a>EoP-Hilfe für Administratoren

Der Hilfeinhalt für EOP-Administratoren umfasst die folgenden übergeordneten Kategorien:

- [Übersicht über den Exchange Online Schutz](exchange-online-protection-overview.md): Einführung in die Funktionsweise von EoP und Links zu zusätzlichen Informationen.

- [EoP-Features](eop-features.md): enthält eine Liste der in EoP verfügbaren Features.

- [Richten Sie Ihren EoP-Dienst ein](set-up-your-eop-service.md): Hier finden Sie eine schrittweise Anleitung zum Einrichten Ihres EoP-Diensts sowie Links zu weiteren Informationen.

- [Wechseln Sie zu EoP von Google Postini, der Barracuda Spam and Virus Firewall oder Cisco IronPort](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md): Beschreibt den Vorgang für das Wechseln zu EoP von einem anderen e-Mail-Schutz Produkt.

- [Verwalten von Empfängern in eigenständigen EoP](manage-recipients-in-eop.md): Beschreibt, wie e-Mail-Benutzer und-Gruppen in EoP verwaltet werden.

- [Nachrichtenfluss in EoP](mail-flow-in-eop.md): Beschreibt, wie benutzerdefinierte Nachrichtenübermittlungsszenarien mithilfe von Connectors konfiguriert werden, wie Domänen im Zusammenhang mit dem Dienst verwaltet werden und wie Sie das Feature für die verzeichnisbasierte Edge-Blockierung (Blockierung) aktivieren.

- [Bewährte Methoden für das Konfigurieren von EoP](best-practices-for-configuring-eop.md): Beschreibt Empfohlene Konfigurationseinstellungen und Überlegungen für nach dem Einrichten und der Dienstbereitstellung.

- [Überwachungsberichte in eigenständigen EoP](auditing-reports-in-eop.md): Beschreibt die Verwendung von Überwachungsberichten zum Nachverfolgen von Konfigurationsänderungen am Dienst.

- [Antispam-und Antischadsoftware-Schutz in EoP](anti-spam-and-anti-malware-protection.md): Beschreibung der Spamfilterung und der Malware Filterung und zeigt, wie diese angepasst werden, um die Anforderungen Ihrer Organisation optimal zu erfüllen. Beschreibt außerdem Aufgaben, die Administratoren und Endbenutzer für isolierte Nachrichten ausführen können.

- [Berichterstellung und Nachrichtenablaufverfolgung in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md): Beschreibt die verfügbaren Berichte und Problembehandlungstools.

- [Exchange Admin Center in eigenständiger EoP](exchange-admin-center-in-exchange-online-protection-eop.md): Beschreibt, wie auf die Verwaltungsschnittstelle der Exchange-Verwaltungskonsole zugegriffen und diese navigiert wird, um den EoP-Dienst zu verwalten.

- [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell): enthält Informationen zur Remote-PowerShell, mit der Sie Ihren EoP-Dienst über die Befehlszeile verwalten können.

- [Hilfe und Support für EOP](help-and-support-for-eop.md) Informationen zum Anfordern von Hilfe und technischem Support.
