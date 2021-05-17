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
description: Administratoren können mithilfe von Connectors (auch als Nachrichtenflussintelligenz bekannt) mehr über die Fehlercodes erfahren, die der Nachrichtenzustellung zugeordnet sind.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2cb52e5865415440b3b2924a3ebcc96a7f8e17e5
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206284"
---
# <a name="mail-flow-intelligence-in-eop"></a>Intelligenter Nachrichtenfluss in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer verwenden Sie in der Regel einen Connector, um E-Mail-Nachrichten von EOP an Ihre lokale E-Mail-Umgebung weiter zu senden. Sie können auch einen Connector verwenden, um Nachrichten von einer Microsoft 365 an eine Partnerorganisation weiter zu senden. Wenn Microsoft 365 diese Nachrichten nicht über den Connector senden können, werden sie in der Warteschlange Microsoft 365. Microsoft 365 versuchen weiterhin, die Zustellung für jede Nachricht 24 Stunden lang zu wiederholen. Nach 24 Stunden läuft die Nachricht in der Warteschlange ab, und die Nachricht wird in einem Unzustellbarkeitsbericht (auch als Unzustellbarkeitsnachricht oder Unzustellbarkeitsnachricht bekannt) an den ursprünglichen Absender zurückgegeben.

Microsoft 365 generiert einen Fehler, wenn eine Nachricht nicht über einen Connector zugestellt werden kann. Die häufigsten Fehler und deren Lösungen werden in diesem Artikel beschrieben. Insgesamt werden Warteschlangen- und Benachrichtigungsfehler für nicht zustellbare Nachrichten, die über Connectors gesendet werden, als _Nachrichtenflussintelligenz bezeichnet._

## <a name="error-code-450-44312-dns-query-failed"></a>Fehlercode: 450 4.4.312 DNS-Abfragefehler

Normalerweise bedeutet dieser Fehler, Microsoft 365 versucht haben, eine Verbindung mit dem Smarthost herzustellen, der im Connector angegeben ist, aber die DNS-Abfrage zum Suchen der IP-Adressen des Smarthosts ist fehlgeschlagen. Mögliche Ursachen für diesen Fehler sind:

- Es gibt ein Problem mit dem DNS-Hostingdienst Ihrer Domäne (Partei, die die autoritativen Namensserver für Ihre Domäne verwaltet).

- Ihre Domäne ist vor kurzem abgelaufen. D.h. der MX-Eintrag kann nicht abgerufen werden.

- Der MX-Eintrag Ihrer Domäne wurde kürzlich geändert, und die DNS-Server verfügen weiterhin über zuvor zwischengespeicherte DNS-Informationen für Ihre Domäne.

### <a name="how-do-i-fix-error-code-450-44312"></a>Wie kann ich fehlercode 450 4.4.312 beheben?

- Arbeiten Sie mit Ihrem DNS-Hostingdienst zusammen, um das Problem mit Ihrer Domäne zu identifizieren und zu beheben.

- Wenn der Fehler von Ihrer Partnerorganisation (z. B. einem Clouddienstanbieter eines Drittanbieters) kommt, wenden Sie sich an Ihren Partner, um das Problem zu beheben.

## <a name="error-code-450-44315-connection-timed-out"></a>Fehlercode: 450 4.4.315 Timeout bei der Verbindung

Normalerweise bedeutet dies, Microsoft 365 keine Verbindung mit dem Ziel-E-Mail-Server herstellen können. Die Fehlerdetails erläutern das Problem. Beispiel:

- Der lokale E-Mail-Server ist nicht verfügbar.

- Es liegt ein Fehler in den Smarthosteinstellungen des Connectors vor, sodass Microsoft 365 versucht, eine Verbindung mit der falschen IP-Adresse herzustellen.

### <a name="how-do-i-fix-error-code-450-44315"></a>Wie kann ich fehlercode 450 4.4.315 beheben?

- Erfahren Sie, welches Szenario für Sie gilt, und nehmen Sie die erforderlichen Korrekturen vor. Wenn der Nachrichtenfluss z. B. ordnungsgemäß funktioniert hat und Sie die Connectoreinstellungen nicht geändert haben, müssen Sie ihre lokale E-Mail-Umgebung überprüfen, um zu überprüfen, ob der Server nicht verfügbar ist oder ob Änderungen an Ihrer Netzwerkinfrastruktur vorgenommen wurden (z. B. haben Sie die Internetdienstanbieter geändert, sodass Sie jetzt über unterschiedliche IP-Adressen verfügen).

- Wenn der Fehler von Ihrer Partnerorganisation (z. B. einem Clouddienstanbieter eines Drittanbieters) kommt, wenden Sie sich an Ihren Partner, um das Problem zu beheben.

## <a name="error-code-450-44316-connection-refused"></a>Fehlercode: 450 4.4.316 Verbindung abgelehnt

Normalerweise bedeutet dieser Fehler, Microsoft 365 beim Herstellen einer Verbindung mit dem Ziel-E-Mail-Server aufgetreten ist. Eine wahrscheinliche Ursache für diesen Fehler ist, dass Ihre Firewall Verbindungen von Microsoft 365 blockiert. Dieser Fehler kann auch entwurfsweise sein, wenn Sie Ihr lokales E-Mail-System vollständig zu Microsoft 365 und Ihre lokale E-Mail-Umgebung heruntergefahren haben.

### <a name="how-do-i-fix-error-code-450-44316"></a>Wie kann ich fehlercode 450 4.4.316 beheben?

- Wenn Sie postfächer in Ihrer lokalen Umgebung haben, müssen Sie ihre Firewalleinstellungen ändern, um Verbindungen von Microsoft 365-IP-Adressen an TCP-Port 25 zu Ihren lokalen E-Mail-Servern zu ermöglichen. Eine Liste der Microsoft 365-IP-Adressen finden Sie [unter Microsoft 365 URLs und IP-Adressbereiche](../../enterprise/urls-and-ip-address-ranges.md).

- Wenn keine weiteren Nachrichten an Ihre lokale Umgebung zugestellt werden sollen, klicken Sie **in** der Warnung auf Jetzt beheben, damit Microsoft 365 Nachrichten mit ungültigen Empfängern sofort ablehnen können. Dadurch wird das Risiko verringert, dass das Kontingent für ungültige Empfänger Ihrer Organisation überschritten wird, wodurch die normale Nachrichtenübermittlung beeinträchtigt werden könnte. Alternativ können Sie das Problem mit den folgenden Anweisungen manuell beheben:

  - Deaktivieren oder löschen Exchange Admin [Center (EAC)](/Exchange/exchange-admin-center)den Connector, der E-Mails aus Microsoft 365 ihrer lokalen E-Mail-Umgebung übermittelt, oder löschen Sie ihn:

    1. Wechseln Sie in der EAC zu **Nachrichtenflussconnectors** \> .

    2. Wählen Sie den Connector  mit dem **Office 365** und  dem E-Mail-Server Ihrer Organisation aus, und gehen Sie wie folgt vor: 

       - Löschen des Connectors durch Klicken **auf** Löschen ![ Entfernen (Symbol)](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)

       - Deaktivieren Sie den Connector, indem Sie auf **Bearbeiten** ![ (Symbol) ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) klicken, und deaktivieren Sie es **aktivieren**.

  - Ändern Sie die akzeptierte Domäne in Microsoft 365, die Ihrer lokalen E-Mail-Umgebung zugeordnet ist, von **Internes Relay** in **Autoritative .** Anweisungen finden Sie unter [Manage accepted domains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).

  **Hinweis**: In der Regel dauern diese Änderungen zwischen 30 Minuten und einer Stunde, bis sie wirksam werden. Stellen Sie nach einer Stunde sicher, dass der Fehler nicht mehr angezeigt wird.

- Wenn der Fehler von Ihrer Partnerorganisation generiert wurde (beispielsweise einem Drittanbieter von Clouddiensten), müssen Sie sich zur Problembehebung an Ihren Partner wenden.

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a>Fehlercode: 450 4.4.317 Fehler beim Herstellen der Verbindung mit Remote-Server

Normalerweise bedeutet dieser Fehler, Microsoft 365 mit dem Ziel-E-Mail-Server verbunden ist, der Server jedoch mit einem sofortigen Fehler geantwortet hat oder die Verbindungsanforderungen nicht erfüllt. Die Fehlerdetails erläutern das Problem. Beispiel:

- Der Ziel-E-Mail-Server hat mit dem Fehler "Dienst nicht verfügbar" geantwortet, der angibt, dass der Server keine Kommunikation mit Microsoft 365.

- Der Connector ist so konfiguriert, dass TLS erforderlich ist, aber der Ziel-E-Mail-Server unterstützt TLS nicht.

### <a name="how-do-i-fix-error-code-450-44317"></a>Wie kann ich fehlercode 450 4.4.317 beheben?

- Überprüfen Sie die TLS-Einstellungen und -Zertifikate auf Ihren lokalen E-Mail-Servern und die TLS-Einstellungen auf dem Connector.

- Wenn der Fehler von Ihrer Partnerorganisation generiert wurde (beispielsweise einem Drittanbieter von Clouddiensten), müssen Sie sich zur Problembehebung an Ihren Partner wenden.

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a>Fehlercode: 450 4.4.318 Verbindung wurde plötzlich geschlossen

In der Regel bedeutet dieser Fehler, Microsoft 365 Probleme mit der Kommunikation mit Ihrer lokalen E-Mail-Umgebung haben, sodass die Verbindung gelöscht wurde. Mögliche Ursachen für diesen Fehler sind:

- Ihre Firewall verwendet SMTP-Paketprüfungsregeln, und diese Regeln funktionieren nicht ordnungsgemäß.

- Der lokale E-Mail-Server funktioniert nicht ordnungsgemäß (z. B. Dienst hängt ab, stürzt ab oder niedrige Systemressourcen), was dazu führt, dass der Server ein Zeitvergezeit auszeiten und die Verbindung zu Microsoft 365.

- Es gibt Netzwerkprobleme zwischen Ihrer lokalen Umgebung und Microsoft 365.

### <a name="how-do-i-fix-error-code-450-44318"></a>Wie kann ich fehlercode 450 4.4.318 beheben?

- Erfahren Sie, welches Szenario für Sie gilt, und nehmen Sie die erforderlichen Korrekturen vor.

- Wenn das Problem durch Netzwerkprobleme zwischen Ihrer lokalen Umgebung und Microsoft 365 verursacht wird, wenden Sie sich an Ihr Netzwerkteam, um das Problem zu beheben.

- Wenn der Fehler von Ihrer Partnerorganisation generiert wurde (beispielsweise einem Drittanbieter von Clouddiensten), müssen Sie sich zur Problembehebung an Ihren Partner wenden.

## <a name="error-code-450-47320-certificate-validation-failed"></a>Fehlercode: 450 4.7.320 Zertifikatüberprüfungsfehler

In der Regel bedeutet dieser Fehler Microsoft 365 beim Versuch, das Zertifikat des Ziel-E-Mail-Servers zu überprüfen, einen Fehler aufgetreten ist. Die Fehlerdetails erläutern den Fehler. Beispiel:

- Zertifikat abgelaufen

- Konflikt mit dem Zertifikatantragsteller

- Zertifikat ist nicht mehr gültig

### <a name="how-do-i-fix-error-code-450-47320"></a>Wie kann ich fehlercode 450 4.7.320 beheben?

- Beheben Sie das Zertifikat oder die Einstellungen auf dem Connector, sodass nachrichten in warteschlangenbereihten Microsoft 365 zugestellt werden können.

- Wenn der Fehler von Ihrer Partnerorganisation generiert wurde (beispielsweise einem Drittanbieter von Clouddiensten), müssen Sie sich zur Problembehebung an Ihren Partner wenden.

## <a name="other-error-codes"></a>Andere Fehlercodes

Microsoft 365 es schwierig, Nachrichten an Ihren lokalen E-Mail-Server oder Partner zu senden. Verwenden Sie die Informationen zum **Zielserver** im Fehler, um das Problem in Ihrer Umgebung zu untersuchen, oder ändern Sie den Konnektor bei einem Konfigurationsfehler.

Wenn der Fehler von Ihrer Partnerorganisation generiert wurde (beispielsweise einem Drittanbieter von Clouddiensten), müssen Sie sich zur Problembehebung an Ihren Partner wenden.