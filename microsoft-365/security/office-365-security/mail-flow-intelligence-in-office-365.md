---
title: Nachrichtenflussintelligenz
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Administratoren können mithilfe von Connectors (auch als Nachrichtenflussintelligenz bezeichnet) mehr über die Fehlercodes erfahren, die der Nachrichtenübermittlung zugeordnet sind.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 44f2272c98f0c011c05cbe728e720f4d3180c09d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844670"
---
# <a name="mail-flow-intelligence-in-eop"></a>Intelligenter Nachrichtenfluss in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online Postfächer verwenden Sie in der Regel einen Connector, um E-Mail-Nachrichten von EOP an Ihre lokale E-Mail-Umgebung weiterzuleiten. Sie können auch einen Connector verwenden, um Nachrichten von Microsoft 365 an eine Partnerorganisation weiterzuleiten. Wenn Microsoft 365 diese Nachrichten nicht über den Connector übermitteln können, werden sie in Microsoft 365 in die Warteschlange eingereiht. Microsoft 365 wiederholen die Zustellung für jede Nachricht 24 Stunden lang. Nach 24 Stunden läuft die Nachricht in der Warteschlange ab, und die Nachricht wird in einem Unzustellbarkeitsbericht (auch als Unzustellbarkeitsbericht bezeichnet) an den ursprünglichen Absender zurückgegeben.

Microsoft 365 generiert einen Fehler, wenn eine Nachricht nicht mithilfe eines Connectors zugestellt werden kann. Die häufigsten Fehler und deren Lösungen werden in diesem Artikel beschrieben. Zusammengefasst werden Warteschlangen- und Benachrichtigungsfehler für nicht zustellbare Nachrichten, die über Connectors gesendet werden, als _Nachrichtenflussintelligenz_ bezeichnet.

## <a name="error-code-450-44312-dns-query-failed"></a>Fehlercode: 450 4.4.312 DNS-Abfragefehler

In der Regel bedeutet dieser Fehler, dass Microsoft 365 versucht haben, eine Verbindung mit dem smarthost herzustellen, der im Connector angegeben ist, aber die DNS-Abfrage zum Suchen der IP-Adressen des Smarthosts ist fehlgeschlagen. Mögliche Ursachen für diesen Fehler sind:

- Es gibt ein Problem mit dem DNS-Hostingdienst Ihrer Domäne (Partei, die die autoritativen Namensserver für Ihre Domäne verwaltet).

- Ihre Domäne ist vor kurzem abgelaufen. D.h. der MX-Eintrag kann nicht abgerufen werden.

- Der MX-Eintrag Ihrer Domäne hat sich kürzlich geändert, und die DNS-Server verfügen weiterhin über zuvor zwischengespeicherte DNS-Informationen für Ihre Domäne.

### <a name="how-do-i-fix-error-code-450-44312"></a>Wie behebt ich Fehlercode 450 4.4.312?

- Arbeiten Sie mit Ihrem DNS-Hostingdienst, um das Problem mit Ihrer Domäne zu identifizieren und zu beheben.

- Wenn der Fehler von Ihrer Partnerorganisation stammt (z. B. einem Clouddienstanbieter eines Drittanbieters), wenden Sie sich an Ihren Partner, um das Problem zu beheben.

## <a name="error-code-450-44315-connection-timed-out"></a>Fehlercode: 450 4.4.315 Timeout bei der Verbindung

In der Regel bedeutet dies, dass Microsoft 365 keine Verbindung mit dem Ziel-E-Mail-Server herstellen können. Die Fehlerdetails erläutern das Problem. Beispiel:

- Ihr lokaler E-Mail-Server ist ausgefallen.

- In den Smarthosteinstellungen des Connectors tritt ein Fehler auf, daher versucht Microsoft 365, eine Verbindung mit der falschen IP-Adresse herzustellen.

### <a name="how-do-i-fix-error-code-450-44315"></a>Wie behebt ich Fehlercode 450 4.4.315?

- Erfahren Sie, welches Szenario für Sie gilt, und nehmen Sie die erforderlichen Korrekturen vor. Wenn beispielsweise der Nachrichtenfluss ordnungsgemäß funktioniert hat und Sie die Connectoreinstellungen nicht geändert haben, müssen Sie Ihre lokale E-Mail-Umgebung überprüfen, um festzustellen, ob der Server ausgefallen ist oder ob Änderungen an Ihrer Netzwerkinfrastruktur vorgenommen wurden (z. B. haben Sie Internetdienstanbieter geändert, sodass Sie jetzt über unterschiedliche IP-Adressen verfügen).

- Wenn der Fehler von Ihrer Partnerorganisation stammt (z. B. einem Clouddienstanbieter eines Drittanbieters), wenden Sie sich an Ihren Partner, um das Problem zu beheben.

## <a name="error-code-450-44316-connection-refused"></a>Fehlercode: 450 4.4.316 Verbindung abgelehnt

In der Regel bedeutet dieser Fehler, dass Microsoft 365 beim Versuch, eine Verbindung mit dem E-Mail-Zielserver herzustellen, auf einen Verbindungsfehler gestoßen ist. Eine wahrscheinliche Ursache für diesen Fehler ist, dass Ihre Firewall Verbindungen von Microsoft 365 IP-Adressen blockiert. Dieser Fehler kann auch beabsichtigt sein, wenn Sie Ihr lokales E-Mail-System vollständig migriert haben, um Ihre lokale E-Mail-Umgebung zu Microsoft 365 und herunterzufahren.

### <a name="how-do-i-fix-error-code-450-44316"></a>Wie behebt ich Fehlercode 450 4.4.316?

- Wenn Sich Postfächer in Ihrer lokalen Umgebung befinden, müssen Sie ihre Firewalleinstellungen ändern, um Verbindungen von Microsoft 365 IP-Adressen am TCP-Port 25 zu Ihren lokalen E-Mail-Servern zuzulassen. Eine Liste der Microsoft 365 IP-Adressen finden Sie unter [Microsoft 365 URLs und IP-Adressbereiche.](../../enterprise/urls-and-ip-address-ranges.md)

- Wenn keine weiteren Nachrichten an Ihre lokale Umgebung übermittelt werden sollen, klicken Sie in der Warnung **auf "Fix now",** damit Microsoft 365 die Nachrichten mit ungültigen Empfängern sofort ablehnen können. Dadurch wird das Risiko verringert, dass das Kontingent für ungültige Empfänger Ihrer Organisation überschritten wird, wodurch die normale Nachrichtenübermittlung beeinträchtigt werden könnte. Alternativ können Sie das Problem mit den folgenden Anweisungen manuell beheben:

  - Deaktivieren oder löschen Sie im [Exchange Admin Center (EAC)](/Exchange/exchange-admin-center)den Connector, der E-Mails von Microsoft 365 an Ihre lokale E-Mail-Umgebung übermittelt:

    1. Wechseln Sie im Exchange-Verwaltungskonsole zu **Nachrichtenflussconnectors.** \> 

    2. Wählen Sie den Connector mit dem **From-Wert** **Office 365** und dem **E-Mail-Server Ihrer Organisation** aus, und führen Sie einen der folgenden Schritte aus: 
       - Löschen Sie den Connector, indem Sie auf das Symbol **"Entfernen löschen"** klicken. ![](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)
       - Deaktivieren Sie den  Connector, indem Sie auf ![ das Bearbeitungssymbol klicken und ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) **deaktivieren.**

  - Ändern Sie die akzeptierte Domäne in Microsoft 365, die Ihrer lokalen E-Mail-Umgebung zugeordnet ist, von **"Internes Relay"** in **"Autoritativ".** Anweisungen finden Sie unter [Verwalten akzeptierter Domänen in Exchange Online.](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)

  **Hinweis:** In der Regel dauern diese Änderungen zwischen 30 Minuten und einer Stunde, bis sie wirksam werden. Stellen Sie nach einer Stunde sicher, dass der Fehler nicht mehr angezeigt wird.

- Wenn der Fehler von Ihrer Partnerorganisation generiert wurde (beispielsweise einem Drittanbieter von Clouddiensten), müssen Sie sich zur Problembehebung an Ihren Partner wenden.

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a>Fehlercode: 450 4.4.317 Fehler beim Herstellen der Verbindung mit Remote-Server

In der Regel bedeutet dieser Fehler, dass Microsoft 365 mit dem Ziel-E-Mail-Server verbunden ist, der Server jedoch sofort geantwortet hat oder die Verbindungsanforderungen nicht erfüllt. Die Fehlerdetails erläutern das Problem. Beispiel:

- Der Ziel-E-Mail-Server hat mit dem Fehler "Dienst nicht verfügbar" geantwortet, der angibt, dass der Server die Kommunikation mit Microsoft 365 nicht aufrechterhalten kann.
- Der Connector ist so konfiguriert, dass TLS erforderlich ist, aber der Ziel-E-Mail-Server unterstützt TLS nicht.

### <a name="how-do-i-fix-error-code-450-44317"></a>Wie behebt ich Fehlercode 450 4.4.317?

- Überprüfen Sie die TLS-Einstellungen und -Zertifikate auf Ihren lokalen E-Mail-Servern und die TLS-Einstellungen auf dem Connector.
- Wenn der Fehler von Ihrer Partnerorganisation generiert wurde (beispielsweise einem Drittanbieter von Clouddiensten), müssen Sie sich zur Problembehebung an Ihren Partner wenden.

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a>Fehlercode: 450 4.4.318 Verbindung wurde plötzlich geschlossen

In der Regel bedeutet dieser Fehler Microsoft 365 Schwierigkeiten bei der Kommunikation mit Ihrer lokalen E-Mail-Umgebung hat, sodass die Verbindung unterbrochen wurde. Mögliche Ursachen für diesen Fehler sind:

- Ihre Firewall verwendet SMTP-Paketprüfungsregeln, und diese Regeln funktionieren nicht ordnungsgemäß.
- Ihr lokaler E-Mail-Server funktioniert nicht ordnungsgemäß (z. B. dienstbehindungen, Abstürze oder geringe Systemressourcen), was dazu führt, dass der Server ein Timeout aufweist und die Verbindung mit Microsoft 365 schließt.
- Es gibt Netzwerkprobleme zwischen Ihrer lokalen Umgebung und Microsoft 365.

### <a name="how-do-i-fix-error-code-450-44318"></a>Wie behebt ich Fehlercode 450 4.4.318?

- Erfahren Sie, welches Szenario für Sie gilt, und nehmen Sie die erforderlichen Korrekturen vor.
- Wenn das Problem durch Netzwerkprobleme zwischen Ihrer lokalen Umgebung und Microsoft 365 verursacht wird, wenden Sie sich an Ihr Netzwerkteam, um das Problem zu beheben.
- Wenn der Fehler von Ihrer Partnerorganisation generiert wurde (beispielsweise einem Drittanbieter von Clouddiensten), müssen Sie sich zur Problembehebung an Ihren Partner wenden.

## <a name="error-code-450-47320-certificate-validation-failed"></a>Fehlercode: 450 4.7.320 Zertifikatüberprüfungsfehler

In der Regel bedeutet dieser Fehler Microsoft 365 beim Versuch, das Zertifikat des Ziel-E-Mail-Servers zu überprüfen, auf einen Fehler gestoßen ist. Die Fehlerdetails erläutern den Fehler. Beispiel:

- Zertifikat abgelaufen
- Konflikt mit dem Zertifikatantragsteller
- Zertifikat ist nicht mehr gültig

### <a name="how-do-i-fix-error-code-450-47320"></a>Wie behebt ich Fehlercode 450 4.7.320?

- Korrigieren Sie das Zertifikat oder die Einstellungen auf dem Connector, sodass Nachrichten in Microsoft 365 in der Warteschlange übermittelt werden können.
- Wenn der Fehler von Ihrer Partnerorganisation generiert wurde (beispielsweise einem Drittanbieter von Clouddiensten), müssen Sie sich zur Problembehebung an Ihren Partner wenden.

## <a name="other-error-codes"></a>Andere Fehlercodes

Microsoft 365 schwierigkeiten beim Übermitteln von Nachrichten an Ihren lokalen E-Mail-Server oder Partner-E-Mail-Server. Verwenden Sie die Informationen zum **Zielserver** im Fehler, um das Problem in Ihrer Umgebung zu untersuchen, oder ändern Sie den Konnektor bei einem Konfigurationsfehler.

Wenn der Fehler von Ihrer Partnerorganisation generiert wurde (beispielsweise einem Drittanbieter von Clouddiensten), müssen Sie sich zur Problembehebung an Ihren Partner wenden.
