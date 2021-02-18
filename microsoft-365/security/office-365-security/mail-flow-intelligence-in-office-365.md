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
ms.openlocfilehash: 32a98459ce3d3494e576b10d5c5b097393ee2335
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289663"
---
# <a name="mail-flow-intelligence-in-eop"></a>Intelligenter Nachrichtenfluss in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer verwenden Sie normalerweise einen Connector, um E-Mail-Nachrichten von EOP an Ihre lokale E-Mail-Umgebung weiter zu routen. Sie können auch einen Connector verwenden, um Nachrichten von Microsoft 365 an eine Partnerorganisation weiter zu routen. Wenn Microsoft 365 diese Nachrichten nicht über den Connector zu senden kann, werden sie in die Warteschlange in Microsoft 365 eingereiht. Microsoft 365 wird die Zustellung für jede Nachricht 24 Stunden lang wiederholen. Nach 24 Stunden läuft die Nachricht in der Warteschlange ab, und die Nachricht wird an den ursprünglichen Absender in einem Unzustellbarkeitsbericht (auch als NDR oder Unzustellbarkeitsnachricht bekannt) zurückgegeben.

Microsoft 365 generiert einen Fehler, wenn eine Nachricht nicht über einen Connector zugestellt werden kann. Die häufigsten Fehler und deren Lösungen werden in diesem Artikel beschrieben. Warteschlangen- und Benachrichtigungsfehler für nicht zustellbare Nachrichten, die über Connectors gesendet werden, werden als _Nachrichtenflussintelligenz bezeichnet._

## <a name="error-code-450-44312-dns-query-failed"></a>Fehlercode: 450 4.4.312 DNS-Abfragefehler

Dieser Fehler bedeutet normalerweise, dass Microsoft 365 versucht hat, eine Verbindung mit dem smarthost herzustellen, der im Connector angegeben ist, aber die DNS-Abfrage, um die IP-Adressen des Smarthosts zu finden, ist fehlgeschlagen. Mögliche Ursachen für diesen Fehler sind:

- Es gibt ein Problem mit dem DNS-Hostingdienst Ihrer Domäne (Partei, die die autoritativen Namensserver für Ihre Domäne verwaltet).

- Ihre Domäne ist vor kurzem abgelaufen. D.h. der MX-Eintrag kann nicht abgerufen werden.

- Der MX-Eintrag Ihrer Domäne hat sich kürzlich geändert, und die DNS-Server verfügen weiterhin über zuvor zwischengespeicherte DNS-Informationen für Ihre Domäne.

### <a name="how-do-i-fix-error-code-450-44312"></a>Wie behebt ich fehlercode 450 4.4.312?

- Arbeiten Sie mit Ihrem DNS-Hostingdienst zusammen, um das Problem mit Ihrer Domäne zu identifizieren und zu beheben.

- Wenn der Fehler von Ihrer Partnerorganisation (z. B. einem Drittanbieter für Clouddienste) auftritt, wenden Sie sich an Ihren Partner, um das Problem zu beheben.

## <a name="error-code-450-44315-connection-timed-out"></a>Fehlercode: 450 4.4.315 Timeout bei der Verbindung

In der Regel bedeutet dies, dass Microsoft 365 keine Verbindung mit dem Ziel-E-Mail-Server herstellen kann. Die Fehlerdetails erläutern das Problem. Beispiel:

- Der lokale E-Mail-Server ist nicht verfügbar.

- Es liegt ein Fehler in den Smarthosteinstellungen des Connectors vor, sodass Microsoft 365 versucht, eine Verbindung mit der falschen IP-Adresse herzustellen.

### <a name="how-do-i-fix-error-code-450-44315"></a>Wie kann ich fehlercode 450 4.4.315 beheben?

- Erfahren Sie, welches Szenario für Sie gilt, und nehmen Sie die erforderlichen Korrekturen vor. Wenn beispielsweise der Nachrichtenfluss ordnungsgemäß funktioniert hat und Sie die Connectoreinstellungen nicht geändert haben, müssen Sie Ihre lokale E-Mail-Umgebung überprüfen, um zu überprüfen, ob der Server nicht verfügbar ist oder ob Änderungen an Ihrer Netzwerkinfrastruktur vorgenommen wurden (z. B. haben Sie Internetdienstanbieter geändert, sodass Sie jetzt über unterschiedliche IP-Adressen verfügen).

- Wenn der Fehler von Ihrer Partnerorganisation (z. B. einem Drittanbieter für Clouddienste) auftritt, wenden Sie sich an Ihren Partner, um das Problem zu beheben.

## <a name="error-code-450-44316-connection-refused"></a>Fehlercode: 450 4.4.316 Verbindung abgelehnt

Dieser Fehler bedeutet in der Regel, dass microsoft 365 beim Herstellen einer Verbindung mit dem Ziel-E-Mail-Server einen Verbindungsfehler festgestellt hat. Eine wahrscheinliche Ursache für diesen Fehler ist, dass Ihre Firewall Verbindungen von Microsoft 365-IP-Adressen blockiert. Dieser Fehler kann entwurfsweise sein, wenn Sie Ihr lokales E-Mail-System vollständig zu Microsoft 365 migriert und Ihre lokale E-Mail-Umgebung heruntergefahren haben.

### <a name="how-do-i-fix-error-code-450-44316"></a>Wie kann ich fehlercode 450 4.4.316 beheben?

- Wenn Sich Postfächer in Ihrer lokalen Umgebung befinden, müssen Sie Ihre Firewalleinstellungen ändern, um Verbindungen von Microsoft 365-IP-Adressen auf dem TCP-Port 25 zu Ihren lokalen E-Mail-Servern zu ermöglichen. Eine Liste der Microsoft 365-IP-Adressen finden Sie unter [Microsoft 365-URLs und -IP-Adressbereiche.](../../enterprise/urls-and-ip-address-ranges.md)

- Wenn keine weiteren Nachrichten an Ihre lokale Umgebung zugestellt werden sollen, klicken Sie **in** der Warnung auf "Jetzt korrigieren", damit Microsoft 365 die Nachrichten mit ungültigen Empfängern sofort ablehnen kann. Dadurch wird das Risiko verringert, dass das Kontingent für ungültige Empfänger Ihrer Organisation überschritten wird, wodurch die normale Nachrichtenübermittlung beeinträchtigt werden könnte. Alternativ können Sie das Problem mit den folgenden Anweisungen manuell beheben:

  - Deaktivieren oder löschen Sie in der Exchange Admin [Center (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center)den Connector, der E-Mails von Microsoft 365 an Ihre lokale E-Mail-Umgebung übermittelt:

    1. Wechseln Sie in der EAC zu **"Nachrichtenflussconnectors".** \> 

    2. Wählen Sie den Connector mit dem **"Von"-Wert** **"Office 365"** und dem **"To** value **Your organization's email server"** aus, und gehen Sie wie folgt vor:

       - Löschen des Connectors durch Klicken auf das Symbol **"Entfernen** ![ löschen"](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)

       - Deaktivieren Sie den Connector, indem Sie **auf** das Bearbeitungssymbol klicken ![ und es ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) **deaktivieren.**

  - Ändern Sie die akzeptierte Domäne in Microsoft 365, die Ihrer lokalen E-Mail-Umgebung zugeordnet ist, von **"Internes Relay"** in **"Autoritativ".** Anweisungen finden Sie unter ["Verwalten akzeptierter Domänen in Exchange Online".](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)

  **Hinweis:** In der Regel dauert es zwischen 30 Minuten und einer Stunde, bis diese Änderungen wirksam werden. Stellen Sie nach einer Stunde sicher, dass der Fehler nicht mehr angezeigt wird.

- Wenn der Fehler von Ihrer Partnerorganisation generiert wurde (beispielsweise einem Drittanbieter von Clouddiensten), müssen Sie sich zur Problembehebung an Ihren Partner wenden.

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a>Fehlercode: 450 4.4.317 Fehler beim Herstellen der Verbindung mit Remote-Server

Dieser Fehler bedeutet normalerweise, dass Microsoft 365 mit dem Ziel-E-Mail-Server verbunden ist, der Server jedoch mit einem sofortigen Fehler geantwortet hat oder die Verbindungsanforderungen nicht erfüllt. Die Fehlerdetails erläutern das Problem. Beispiel:

- Der Ziel-E-Mail-Server hat mit dem Fehler "Dienst nicht verfügbar" geantwortet, der angibt, dass der Server keine Kommunikation mit Microsoft 365 aufrecht erhalten kann.

- Der Connector ist so konfiguriert, dass TLS erforderlich ist, aber der Ziel-E-Mail-Server unterstützt TLS nicht.

### <a name="how-do-i-fix-error-code-450-44317"></a>Wie behebt ich fehlercode 450 4.4.317?

- Überprüfen Sie die TLS-Einstellungen und -Zertifikate auf Ihren lokalen E-Mail-Servern und die TLS-Einstellungen auf dem Connector.

- Wenn der Fehler von Ihrer Partnerorganisation generiert wurde (beispielsweise einem Drittanbieter von Clouddiensten), müssen Sie sich zur Problembehebung an Ihren Partner wenden.

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a>Fehlercode: 450 4.4.318 Verbindung wurde plötzlich geschlossen

Dieser Fehler bedeutet in der Regel, dass Microsoft 365 Schwierigkeiten hat, mit Ihrer lokalen E-Mail-Umgebung zu kommunizieren, sodass die Verbindung verworfen wurde. Mögliche Ursachen für diesen Fehler sind:

- Ihre Firewall verwendet SMTP-Paketprüfungsregeln, und diese Regeln funktionieren nicht ordnungsgemäß.

- Ihr lokales E-Mail-Server funktioniert nicht ordnungsgemäß (z. B. Dienst hängt ab, stürzt ab oder geringe Systemressourcen), was dazu führt, dass der Server ein Zeit zeitverziert und die Verbindung mit Microsoft 365 schließt.

- Es gibt Netzwerkprobleme zwischen Ihrer lokalen Umgebung und Microsoft 365.

### <a name="how-do-i-fix-error-code-450-44318"></a>Wie kann ich fehlercode 450 4.4.318 beheben?

- Erfahren Sie, welches Szenario für Sie gilt, und nehmen Sie die erforderlichen Korrekturen vor.

- Wenn das Problem durch Netzwerkprobleme zwischen Ihrer lokalen Umgebung und Microsoft 365 verursacht wird, wenden Sie sich zur Problembehandlung an Ihr Netzwerkteam.

- Wenn der Fehler von Ihrer Partnerorganisation generiert wurde (beispielsweise einem Drittanbieter von Clouddiensten), müssen Sie sich zur Problembehebung an Ihren Partner wenden.

## <a name="error-code-450-47320-certificate-validation-failed"></a>Fehlercode: 450 4.7.320 Zertifikatüberprüfungsfehler

Dieser Fehler bedeutet normalerweise, dass microsoft 365 beim Versuch, das Zertifikat des Ziel-E-Mail-Servers zu überprüfen, einen Fehler festgestellt hat. Die Fehlerdetails erläutern den Fehler. Beispiel:

- Zertifikat abgelaufen

- Konflikt mit dem Zertifikatantragsteller

- Zertifikat ist nicht mehr gültig

### <a name="how-do-i-fix-error-code-450-47320"></a>Wie behebt ich den Fehlercode 450 4.7.320?

- Korrigieren Sie das Zertifikat oder die Einstellungen auf dem Connector, sodass Nachrichten in der Warteschlange in Microsoft 365 zugestellt werden können.

- Wenn der Fehler von Ihrer Partnerorganisation generiert wurde (beispielsweise einem Drittanbieter von Clouddiensten), müssen Sie sich zur Problembehebung an Ihren Partner wenden.

## <a name="other-error-codes"></a>Andere Fehlercodes

Microsoft 365 hat Schwierigkeiten beim Senden von Nachrichten an Ihren lokalen E-Mail-Server oder Partner-E-Mail-Server. Verwenden Sie die Informationen zum **Zielserver** im Fehler, um das Problem in Ihrer Umgebung zu untersuchen, oder ändern Sie den Konnektor bei einem Konfigurationsfehler.

Wenn der Fehler von Ihrer Partnerorganisation generiert wurde (beispielsweise einem Drittanbieter von Clouddiensten), müssen Sie sich zur Problembehebung an Ihren Partner wenden.
