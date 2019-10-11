---
title: Mail Flow Intelligence in Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Administratoren können sich über die Fehlercodes informieren, die mit der Nachrichtenzustellung in Office 365 (auch als Nachrichtenfluss-Intelligence bezeichnet) verbunden sind.
ms.openlocfilehash: 088af4b6924fde0277901a19437d17c4506ff22b
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441542"
---
# <a name="mail-flow-intelligence-in-office-365"></a>Intelligente Nachrichtenübermittlung in Office 365

Normalerweise verwenden Sie einen Connector, um e-Mail-Nachrichten von Ihrer Office 365 Organisation an Ihre lokale e-Mail-Umgebung weiterzuleiten. Sie können auch einen Konnektor verwenden, um Nachrichten von Office 365 zu einer Partnerorganisation weiterzuleiten. Wenn Office 365 diese Nachrichten nicht über den Konnektor senden kann, werden sie in die Office 365-Warteschlange gestellt. Office 365 versucht 48 Stunden, die Nachrichten zu senden. Nach 48 Stunden läuft die Nachricht in der Warteschlange ab, und die Nachricht wird an den ursprünglichen Absender in einem Unzustellbarkeitsbericht zurückgegeben (auch bekannt als NDR oder Unzustellbarkeitsnachricht).

Office 365 generiert einen Fehler, wenn eine Nachricht nicht mithilfe eines Konnektors gesendet werden kann. In diesem Thema werden die am häufigsten auftretenden Fehler und die dazugehörigen Lösungen beschrieben. Gemeinsam werden Warteschlangen-und Benachrichtigungsfehler für unzustellbare Nachrichten, die über Connectors gesendet werden, als _Nachrichtenfluss-Intelligence_bezeichnet.

## <a name="error-code-450-44312-dns-query-failed"></a>Fehlercode: 450 4.4.312 DNS-Abfragefehler

Dieser Fehler bedeutet normalerweise, dass Office 365 versucht haben, eine Verbindung mit dem Smarthost herzustellen, der in dem Connector angegeben ist, aber die DNS-Abfrage zum Auffinden der IP-Adressen des Smarthosts ist fehlgeschlagen. Mögliche Ursachen für diesen Fehler sind:

- Es gibt ein Problem mit dem DNS-Hostingdienst Ihrer Domäne (Partei, die die autoritativen Namensserver für Ihre Domäne verwaltet).

- Ihre Domäne ist vor kurzem abgelaufen. D.h. der MX-Eintrag kann nicht abgerufen werden.

- Der MX-Eintrag Ihrer Domäne hat sich kürzlich geändert, und die Office 365-DNS-Server enthalten weiterhin zuvor zwischengespeicherte DNS-Informationen für Ihre Domäne.

### <a name="how-do-i-fix-error-code-450-44312"></a>Wie behebe ich den Fehlercode 450 4.4.312?

- Arbeiten Sie mit Ihrem DNS-Hostdienst zusammen, um das Problem mit Ihrer Domäne zu identifizieren und zu beheben.

- Wenn der Fehler von ihrer Partnerorganisation stammt (beispielsweise ein Drittanbieter-Cloud-Dienstanbieter), wenden Sie sich an Ihren Partner, um das Problem zu beheben.

## <a name="error-code-450-44315-connection-timed-out"></a>Fehlercode: 450 4.4.315 Timeout bei der Verbindung

Dies bedeutet in der Regel, dass Office 365 keine Verbindung zum Ziel-e-Mail-Server herstellen können. Die Fehlerdetails erläutern das Problem. Beispiel:

- Der lokale e-Mail-Server ist nicht verfügbar.

- Es ist ein Fehler in den Einstellungen des intelligenten Hosts des Konnektors vorhanden. Office 365 versucht, ein Verbindung zur falschen IP-Adresse herzustellen.

### <a name="how-do-i-fix-error-code-450-44315"></a>Wie behebe ich den Fehlercode 450 4.4.315?

- Erfahren Sie, welches Szenario für Sie gilt, und nehmen Sie die erforderlichen Korrekturen vor. Wenn beispielsweise die Nachrichtenübermittlung ordnungsgemäß ausgeführt wurde und Sie die Connectoreinstellungen nicht geändert haben, müssen Sie Ihre lokale e-Mail-Umgebung überprüfen, um festzustellen, ob der Server nicht aktiv ist oder ob Änderungen an Ihrer Netzwerkinfrastruktur vorgenommen wurden (beispielsweise Sie haben Internetdienstanbieter geändert, sodass Sie nun unterschiedliche IP-Adressen haben.

- Wenn der Fehler von ihrer Partnerorganisation stammt (beispielsweise ein Drittanbieter-Cloud-Dienstanbieter), wenden Sie sich an Ihren Partner, um das Problem zu beheben.

## <a name="error-code-450-44316-connection-refused"></a>Fehlercode: 450 4.4.316 Verbindung abgelehnt

Dieser Fehler bedeutet normalerweise, dass Office 365 einen Verbindungsfehler bei dem Versuch gefunden hat, eine Verbindung mit dem Ziel-e-Mail-Server herzustellen. Eine mögliche Ursache für diesen Fehler ist, dass Ihre Firewall Verbindungen von Office 365-IP-Adressen blockiert. Dieser Fehler kann auch dann beabsichtigt sein, wenn Sie Ihr lokales e-Mail-System vollständig in Office 365 migriert und Ihre lokale e-Mail-Umgebung heruntergefahren haben.

### <a name="how-do-i-fix-error-code-450-44316"></a>Wie behebe ich den Fehlercode 450 4.4.316?

- Wenn Sie über Postfächer in Ihrer lokalen Umgebung verfügen, müssen Sie Ihre Firewalleinstellungen so ändern, dass Verbindungen zwischen Office 365-IP-Adressen an TCP-Port 25 und Ihren lokalen e-Mail-Servern zulässig sind. Eine Liste der Office 365-IP-Adressen finden Sie unter [Office 365-URLs und -IP-Adressbereiche](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2.aspx).

- Wenn keine weiteren Nachrichten an Ihre lokale Umgebung übermittelt werden sollen, klicken Sie in der Warnung auf **Jetzt korrigieren**, damit Office 365 die Nachrichten mit ungültigen Empfängern sofort ablehnen kann. Dadurch wird das Risiko verringert, dass das Kontingent für ungültige Empfänger Ihrer Organisation überschritten wird, wodurch die normale Nachrichtenübermittlung beeinträchtigt werden könnte. Alternativ können Sie das Problem mit den folgenden Anweisungen manuell beheben:

  - Deaktivieren oder löschen Sie in der [Exchange-Verwaltungskonsole (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center) in Office 365 den Connector, der e-Mails von Office 365 an Ihre lokale e-Mail-Umgebung sendet:

    1. Wechseln Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> - **Konnektoren**.

    2. Wählen Sie den Connector mit dem **from** -Wert **Office 365** und den **, um** den **e-Mail-Server Ihrer Organisation** zu schätzen, und führen Sie einen der folgenden Schritte aus:

       - Löschen Sie den Connector, indem Sie auf **Löschen** ![Symbol Entfernen klicken.](../media/adf01106-cc79-475c-8673-065371c1897b.gif)

       - Deaktivieren Sie den Connector, indem Sie auf](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) bearbeiten-Symbol **Bearbeiten** ![klicken und deaktivieren **aktivieren**.

  - Ändern Sie die akzeptierte Domäne in Office 365, die Ihrer lokalen e-Mail-Umgebung vom **internen Relay** an **autorisierend**zugeordnet ist. Anweisungen finden Sie unter [Manage accepted domains in Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=785428).

  **Hinweis**: in der Regel dauern diese Änderungen zwischen 30 Minuten und einer Stunde, um wirksam zu werden. Vergewissern Sie sich nach einer Stunde, dass der Fehler nicht mehr angezeigt wird.

- Wenn der Fehler von Ihrer Partnerorganisation generiert wurde (beispielsweise einem Drittanbieter von Clouddiensten), müssen Sie sich zur Problembehebung an Ihren Partner wenden.

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a>Fehlercode: 450 4.4.317 Fehler beim Herstellen der Verbindung mit Remote-Server

Dieser Fehler bedeutet normalerweise, dass Office 365 mit dem Ziel-e-Mail-Server verbunden ist, der Server jedoch mit einem unmittelbaren Fehler reagiert oder die Verbindungsanforderungen nicht erfüllt. Die Fehlerdetails erläutern das Problem. Beispiel:

- Der Ziel-e-Mail-Server hat mit dem Fehler "Dienst nicht verfügbar" geantwortet, der angibt, dass der Server die Kommunikation mit Office 365 nicht aufrecht erhalten kann.

- Der Connector ist so konfiguriert, dass er TLS erfordert, aber der Ziel-e-Mail-Server unterstützt TLS nicht.

### <a name="how-do-i-fix-error-code-450-44317"></a>Wie behebe ich den Fehlercode 450 4.4.317?

- Überprüfen Sie die TLS-Einstellungen und-Zertifikate auf Ihren lokalen e-Mail-Servern und die TLS-Einstellungen für den Connector.

- Wenn der Fehler von Ihrer Partnerorganisation generiert wurde (beispielsweise einem Drittanbieter von Clouddiensten), müssen Sie sich zur Problembehebung an Ihren Partner wenden.

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a>Fehlercode: 450 4.4.318 Verbindung wurde plötzlich geschlossen

Dieser Fehler bedeutet normalerweise, dass Office 365 Schwierigkeiten hat, mit Ihrer lokalen e-Mail-Umgebung zu kommunizieren, sodass die Verbindung getrennt wurde. Mögliche Ursachen für diesen Fehler sind:

- Ihre Firewall verwendet SMTP-Paketprüfungsregeln, und diese Regeln funktionieren nicht ordnungsgemäß.

- Der lokale e-Mail-Server funktioniert nicht ordnungsgemäß (beispielsweise Dienst hängt, stürzt ab oder niedrige Systemressourcen), was dazu führt, dass der Server eine Zeitüberschreitung verursacht und die Verbindung mit Office 365 schließt.

- Es treten Netzwerkprobleme zwischen Ihrer lokalen Umgebung und Office 365 auf.

### <a name="how-do-i-fix-error-code-450-44318"></a>Wie behebe ich den Fehlercode 450 4.4.318?

- Erfahren Sie, welches Szenario für Sie gilt, und nehmen Sie die erforderlichen Korrekturen vor.

- Wenn das Problem durch Netzwerkprobleme zwischen Ihrer lokalen Umgebung und Office 365 verursacht wird, wenden Sie sich an Ihr Netzwerkteam, um das Problem zu beheben.

- Wenn der Fehler von Ihrer Partnerorganisation generiert wurde (beispielsweise einem Drittanbieter von Clouddiensten), müssen Sie sich zur Problembehebung an Ihren Partner wenden.

## <a name="error-code-450-47320-certificate-validation-failed"></a>Fehlercode: 450 4.7.320 Zertifikatüberprüfungsfehler

Dieser Fehler bedeutet normalerweise, dass Office 365 bei dem Versuch, das Zertifikat des Ziel-e-Mail-Servers zu überprüfen, einen Fehler festgestellt haben. Die Fehlerdetails erläutern den Fehler. Beispiel:

- Zertifikat abgelaufen

- Konflikt mit dem Zertifikatantragsteller

- Zertifikat ist nicht mehr gültig

### <a name="how-do-i-fix-error-code-450-47320"></a>Wie behebe ich den Fehlercode 450 4.7.320?

- Korrigieren Sie das Zertifikat oder die Einstellungen für den Connector, damit Warteschlangen Nachrichten in Office 365 zugestellt werden können.

- Wenn der Fehler von Ihrer Partnerorganisation generiert wurde (beispielsweise einem Drittanbieter von Clouddiensten), müssen Sie sich zur Problembehebung an Ihren Partner wenden.

## <a name="other-error-codes"></a>Andere Fehlercodes

Office 365 Probleme bei der Zustellung von Nachrichten an Ihren lokalen oder Partner-e-Mail-Server. Verwenden Sie die Informationen zum **Zielserver** im Fehler, um das Problem in Ihrer Umgebung zu untersuchen, oder ändern Sie den Konnektor bei einem Konfigurationsfehler.

Wenn der Fehler von Ihrer Partnerorganisation generiert wurde (beispielsweise einem Drittanbieter von Clouddiensten), müssen Sie sich zur Problembehebung an Ihren Partner wenden.
