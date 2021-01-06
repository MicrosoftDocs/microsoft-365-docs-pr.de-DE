---
title: Einrichten des eigenständigen EoP-Diensts
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
ms.assetid: d74c6ddf-11b0-43ee-b298-8bb0340895f0
description: Administratoren können erfahren, wie Sie eigenständige Exchange Online Schutz (EoP) einrichten, um lokale e-Mail-Umgebungen zu schützen.
ms.openlocfilehash: ca95f7dce30e8e751e293bf4e5de9caf0c845d29
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760494"
---
# <a name="set-up-your-standalone-eop-service"></a>Einrichten des eigenständigen EoP-Diensts

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In diesem Thema wird erläutert, wie Sie eigenständige Exchange Online Schutz einrichten (EoP). Wenn Sie vom Office 365-Assistenten für Domänen hierher geführt wurden, wechseln Sie zurück zum Office 365-Assistenten für Domänen, wenn Sie Exchange Online Protection nicht verwenden möchten. Wenn Sie weitere Informationen zum Konfigurieren von Connectors suchen, finden Sie diese unter [Configure mail flow using connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

> [!NOTE]
> In diesem Thema wird davon ausgegangen, dass lokale Postfächer verwendet werden, die mit EOP geschützt werden sollen - dies wird als eigenständiges Szenario bezeichnet. Wenn Sie alle ihre Postfächer in der Cloud mit Exchange Online hosten möchten, müssen Sie nicht alle Schritte in diesem Artikel ausführen. Wechseln Sie zu [Exchange Online Pläne](https://products.office.com/exchange/compare-microsoft-exchange-online-plans) zum Registrieren und kaufen von Cloud-Postfächern.
>
> Wenn Sie die Postfächer teils lokal und teils in der Cloud hosten möchten, handelt es sich um ein hybrides Szenario. Für ein solches Szenario sind erweiterte Nachrichtenflusseinstellungen erforderlich. [Exchange Server hybridbereitstellungen](https://docs.microsoft.com/exchange/exchange-hybrid) erläutert den Hybriden Nachrichtenfluss und enthält Links zu Ressourcen, die zeigen, wie es eingerichtet wird.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Geschätzte Zeit bis zum Abschließen dieser Aufgabe: 1 Stunde

- Sie müssen Berechtigungen in Exchange Online Protection zugewiesen werden, bevor Sie die Verfahren in diesem Artikel ausführen können. Insbesondere benötigen Sie die Rolle " **Remote" und "akzeptierte Domänen** ", die standardmäßig den Rollengruppen " **Organisationsverwaltung** " (globale Administratoren) und **"Nachrichtenfluss-Administrator** " zugewiesen ist. Weitere Informationen finden Sie unter [Berechtigungen in eigenständigen EoP](feature-permissions-in-eop.md) und [Verwenden der Exchange-Verwaltungskonsole ändern der Liste der Mitglieder in Rollengruppen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Wenn Sie sich noch nicht bei EOP registriert haben, rufen Sie [Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection) auf, und erwerben oder testen Sie den Dienst.

- Informationen zu Tastenkombinationen, die möglicherweise für die Verfahren in diesem Artikel gelten, finden Sie unter [Tastenkombinationen für das Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Liegt ein Problem vor? Bitten Sie im [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)-Forum um Hilfe.

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Schritt 1: Verwenden des Microsoft 365 Admin Center zum Hinzufügen und Überprüfen Ihrer Domäne

1. Wechseln Sie im [Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/admin-overview/about-the-admin-center)zu **Setup** , um Ihre Domäne dem Dienst hinzuzufügen.

2. Befolgen Sie die Schritte, um Ihrem DNS-Hostinganbieter die entsprechenden DNS-Datensätze hinzuzufügen, um die Domäneneigentümerschaft zu überprüfen.

> [!TIP]
> [Hinzufügen einer Domäne zu Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) und [Erstellen von DNS-Einträgen bei einem beliebigen DNS-Hostinganbieter für Office 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) sind hilfreiche Ressourcen, die Sie beim Hinzufügen Ihrer Domäne zum Dienst und Konfigurieren von DNS referenzieren.

## <a name="step-2-add-recipients-and-optionally-enable-dbeb"></a>Schritt 2: Hinzufügen von Empfängern und optionales Aktivieren der verzeichnisbasierten Edge-Blockierung (DBEB)

Bevor Sie die Übermittlung Ihrer E-Mails zum und vom EOP-Dienst konfigurieren, empfehlen wir, Ihre Empfänger zum Dienst hinzuzufügen. Es gibt dazu verschiedene Möglichkeiten, die in [Verwalten von E-Mail-Benutzern in EOP](manage-mail-users-in-eop.md) dokumentiert sind. Wenn Sie verzeichnisbasierte Edge-Blockierung (Directory Based Edge Blocking, DBEB) aktivieren möchten, um im Dienst eine Empfängerprüfung zu erzwingen, nachdem Sie Ihre Empfänger hinzugefügt haben, müssen Sie den Domänentyp außerdem auf "Autorisierend" festlegen. Weitere Informationen zur verzeichnisbasierten Edge-Blockierung finden Sie unter [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Schritt 3: Einrichten des Nachrichtenflusses mithilfe der Exchange-Verwaltungskonsole

Erstellen Sie in der Exchange-Verwaltungskonsole (EAC) Connectors, die den Nachrichtenfluss zwischen EOP und Ihren lokalen E-Mail-Servern ermöglichen. Ausführliche Anweisungen finden Sie unter [Einrichten von Connectors zum Weiterleiten von e-Mails zwischen Microsoft 365 und ihren eigenen e-Mail-Servern](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail).

### <a name="how-do-you-know-this-task-worked"></a>Woher wissen Sie, dass diese Aufgabe erfolgreich war?

Überprüfen Sie den Nachrichtenfluss zwischen dem Dienst und ihrer Umgebung. Weitere Informationen finden Sie unter [Testen der Nachrichtenübermittlung durch validieren Ihrer Microsoft 365-Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Schritt 4: Zulassen eingehender SMTP-Verbindungen an Port 25

Nachdem Sie Connectors konfiguriert haben, warten Sie 72 Stunden, um die Weitergabe Ihrer DNS-Eintragsaktualisierungen zu ermöglichen. Schränken Sie anschließend in Ihrer Firewall oder auf Ihren E-Mail-Servern den eingehenden SMTP-Datenverkehr für Port 25 so ein, dass nur E-Mails von EOP-Rechenzentren, genauer gesagt von den unter [Exchange Online Protection-IP-Adressen](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges) aufgeführten IP-Adressen, zugelassen werden. So schützen Sie Ihre lokale Umgebung, indem Sie den Bereich eingehender Nachrichten einschränken, die Sie empfangen können. Wenn Ihr E-Mail-Server Einstellungen aufweist, welche die IP-Adressen steuern, die für E-Mail-Relay eine Verbindung herstellen dürfen, sollten Sie zusätzlich diese Einstellungen aktualisieren.

> [!TIP]
> Konfigurieren Sie Einstellungen auf dem SMTP-Server mit einem Verbindungstimeout von 60 Sekunden. Diese Einstellung ist für die meisten Situationen akzeptabel, sodass eine gewisse Verzögerung im Fall einer Nachricht, die mit einer großen Anlage gesendet wird, beispielsweise ermöglicht wird.

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Schritt 5: sicherstellen, dass Spam an den Junk-e-Mail-Ordner der einzelnen Benutzer weitergeleitet wird

Sie müssen eine Reihe von Konfigurationsschritten ausführen, um wirklich sicherzustellen, dass Junk-E-Mail (Spam) in die Junk-E-Mail-Ordner der Benutzer umgeleitet werden. Die Schritte werden in [Konfigurieren von eigenständigen EoP zur Zustellung von Spam an den Junk-e-Mail-Ordner in Hybrid Umgebungen](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)bereitgestellt.

Wenn Sie keine Nachrichten in den Junk-e-Mail-Ordner der einzelnen Benutzer übertragen möchten, können Sie eine andere Aktion auswählen, indem Sie Ihre Anti-Spam-Richtlinien bearbeiten. Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien in Office 365](configure-your-spam-filter-policies.md).

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Schritt 6: Verwenden des Microsoft 365 Admin Center zum Verweisen Ihres MX-Eintrags auf EoP

Führen Sie die Schritte zur Domänenkonfiguration aus, um den MX-Eintrag für Ihre Domäne zu aktualisieren, damit die eingehenden e-Mails über EoP fließen. Stellen Sie sicher, dass Ihr MX-Eintrag direkt auf EOP verweist, damit kein Filterungsdienstrelais eines Drittanbieters eine E-Mail an EOP schreibt. Weitere Informationen finden Sie auch hierzu unter [Erstellen von DNS-Einträgen für Office 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

> [!NOTE]
> Wenn Sie den MX-Eintrag auf einen anderen Server oder Dienst zeigen müssen, der sich vor EoP befindet, finden Sie weitere Informationen unter [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

### <a name="how-do-you-know-this-task-worked"></a>Woher wissen Sie, dass diese Aufgabe erfolgreich war?

Zu diesem Zeitpunkt haben Sie die Dienstübermittlung für einen ordnungsgemäß konfigurierten Ausgang auf dem lokalen Connector geprüft und sichergestellt, dass Ihr MX-Eintrag auf EOP verwiesen wurde. Sie können nun zusätzlich die folgenden Tests ausführen, um sicherzustellen, dass der Dienst eine E-Mail erfolgreich an Ihre lokale Umgebung versendet hat:

- Überprüfen Sie den Nachrichtenfluss zwischen dem Dienst und ihrer Umgebung. Weitere Informationen finden Sie unter [Testen der Nachrichtenübermittlung durch validieren Ihrer Microsoft 365-Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).

- Senden Sie von einem webbasierten E-Mail-Konto eine E-Mail an einen E-Mail-Empfänger in Ihrer Organisation, dessen Domäne der Domäne entspricht, die Sie dem Dienst hinzugefügt haben. Bestätigen Sie mithilfe von Microsoft Outlook oder einem anderen E-Mail-Client die Zustellung der Nachricht an das lokale Postfach.

- Wenn Sie einen Test für ausgehende E-Mails durchführen möchten, können Sie von einem Benutzer in Ihrer Organisation aus eine E-Mail an ein webbasiertes E-Mail-Konto senden und überprüfen, ob die Nachricht übermittelt wurde.

> [!TIP]
> Nachdem Sie das Setup abgeschlossen haben, müssen Sie nichts weiter tun, um EOP für das Entfernen von Spam und Malware zu konfigurieren. Spam und Malware werden von EOP automatisch entfernt. Sie können Ihre Einstellungen jedoch auf der Grundlage ihrer geschäftlichen Anforderungen optimieren. Weitere Informationen finden Sie unter [Anti-Spam and Anti-Malware Protection in Office 365](anti-spam-and-anti-malware-protection.md) und [configure Spoof Intelligence](learn-about-spoof-intelligence.md).
>
> Nun, da Ihr Dienst aktiv ist, wird empfohlen, [bewährte Methoden zum Konfigurieren von EoP zu](best-practices-for-configuring-eop.md)lesen, in dem Empfohlene Einstellungen und Überlegungen für nach dem Einrichten von EoP beschrieben werden.
