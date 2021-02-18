---
title: Schützen von lokalen Postfächern in China mit EOP als eigenständige Lösung
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- GEU150
- GMA150
- GPA150
- MET150
ms.assetid: c5e95951-da67-4ec7-92c5-982abd477e69
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratoren in China, die Office 365, betrieben von 21Vianet verwenden, können erfahren, wie sie eigenständigen Exchange Online Protection (EOP) verwenden, um ihre lokalen Postfächer zu schützen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f4f27fa9237d76422e936555c9872b83655d7b6b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289425"
---
# <a name="protect-on-premises-mailboxes-in-china-with-standalone-eop"></a>Schützen von lokalen Postfächern in China mit EOP als eigenständige Lösung

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Dieser Artikel bezieht sich nur auf Office 365, betrieben von 21Vianet in China.

Auch wenn Sie planen, einige oder alle Postfächer lokal zu hosten, können Sie die Postfächer weiterhin mit Exchange Online Protection (EOP) schützen. Zum Konfigurieren von Connectors muss Ihr Konto ein globaler Administrator oder ein Exchange-Unternehmensadministrator (rollengruppe "Organisationsverwaltung"). Informationen zum Zusammenhang von Office 365-Berechtigungen zu Exchange-Berechtigungen finden Sie unter Zuweisen von Administratorrollen [in Office 365, betrieben von 21Vianet.](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-21vianet&preserve-view=true) Wenn alle Ihre Exchange-Postfächer lokal sind, führen Sie die folgenden Schritte aus, um Ihren EOP-Dienst zu einrichten.

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Schritt 1: Verwenden des Microsoft 365 Admin Centers zum Hinzufügen und Überprüfen Ihrer Domäne

1. Navigieren Sie im Microsoft 365 Admin Center zu Setup, um Ihre Domäne zum Dienst hinzuzufügen.

2. Führen Sie die Schritte im Portal aus, um ihrem DNS-Hostinganbieter die entsprechenden DNS-Einträge hinzuzufügen, um den Domänenbesitz zu überprüfen.

> [!TIP]
> Fügen Sie Ihre Domäne und Ihre Benutzer zu [Office 365, betrieben von 21Vianet,](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain?view=o365-21vianet&preserve-view=true) hinzu, und erstellen Sie DNS-Einträge für [Office 365,](https://docs.microsoft.com/microsoft-365/admin/services-in-china/create-dns-records-when-you-manage-your-dns-records?view=o365-21vianet&preserve-view=true) wenn Sie Ihre DNS-Einträge verwalten, sind hilfreiche Ressourcen, auf die Verwiesen werden kann, wenn Sie Ihre Domäne zum Dienst hinzufügen und DNS konfigurieren.

### <a name="step-2-add-recipients-and-configure-the-domain-type"></a>Schritt 2: Hinzufügen von Empfängern und Konfigurieren des Domänentyps

Bevor Sie die Übermittlung Ihrer E-Mails zum und vom EOP-Dienst konfigurieren, empfehlen wir, Ihre Empfänger zum Dienst hinzuzufügen. Es gibt dazu verschiedene Möglichkeiten, die in [Verwalten von E-Mail-Benutzern in EOP](manage-mail-users-in-eop.md) dokumentiert sind. Wenn Sie verzeichnisbasierte Edge-Blockierung (Directory Based Edge Blocking, DBEB) aktivieren möchten, um im Dienst eine Empfängerprüfung zu erzwingen, nachdem Sie Ihre Empfänger hinzugefügt haben, müssen Sie den Domänentyp außerdem auf "Autorisierend" festlegen. Weitere Informationen zu DBEB finden Sie unter Verwenden der verzeichnisbasierten Edge-Blockierung, um An [ungültige Empfänger gesendete Nachrichten abzulehnen.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Schritt 3: Einrichten des Nachrichtenflusses mithilfe der Exchange-Verwaltungskonsole

Erstellen Sie in der Exchange-Verwaltungskonsole (EAC) Connectors, die den Nachrichtenfluss zwischen EOP und Ihren lokalen E-Mail-Servern ermöglichen. Ausführliche Anweisungen finden Sie unter ["Konfigurieren des Nachrichtenflusses mithilfe von Connectors in Office 365".](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)

 Woher wissen Sie, dass diese Aufgabe erfolgreich war?

 Weitere [Informationen finden Sie unter "Testen des Nachrichtenflusses", indem Sie Ihre Office 365-Connectors überprüfen.](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Schritt 4: Zulassen eingehender SMTP-Verbindungen an Port 25

Nachdem Sie Connectors konfiguriert haben, sollten Sie 72 Stunden warten, bis Ihre DNS-Datensatzaktualisierungen weitergegeben wurden. Beschränken Sie anschließend den eingehenden Port-25-SMTP-Datenverkehr auf Ihrer Firewall oder Ihren E-Mail-Servern so, dass nur E-Mails von den EOP-Rechenzentren akzeptiert werden, insbesondere von den IP-Adressen, die unter URLs und IN-Adressbereichen für [Office 365](../../enterprise/managing-office-365-endpoints.md)aufgeführt sind. So schützen Sie Ihre lokale Umgebung, indem Sie den Bereich eingehender Nachrichten einschränken, die Sie empfangen können. Wenn Ihr E-Mail-Server Einstellungen aufweist, welche die IP-Adressen steuern, die für E-Mail-Relay eine Verbindung herstellen dürfen, sollten Sie zusätzlich diese Einstellungen aktualisieren.

> [!TIP]
> Konfigurieren Sie Einstellungen auf dem SMTP-Server mit einem Verbindungstimeout von 60 Sekunden. Diese Einstellung ist in den meisten Fällen sinnvoll, da sie eine gewisse Verzögerung erlaubt, falls z. B. eine Nachricht mit einem großen Anhang gesendet wird.

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Schritt 5: Sicherstellen, dass Spam an den Junk-E-Mail-Ordner jedes Benutzers geroutet wird

Sie müssen eine Reihe von Konfigurationsschritten ausführen, um wirklich sicherzustellen, dass Junk-E-Mail (Spam) in die Junk-E-Mail-Ordner der Benutzer umgeleitet werden. Die Schritte finden Sie unter Konfigurieren von EOP als eigenständige Lösung, um Spam an den [Junk-E-Mail-Ordner in Hybridumgebungen zu senden.](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) Wenn Sie Nachrichten nicht in den Junk-E-Mail-Ordner jedes Benutzers verschieben möchten, können Sie eine andere Aktion auswählen, indem Sie Ihre Antispamrichtlinien (auch als Inhaltsfilterrichtlinien bekannt) bearbeiten. Weitere Informationen finden Sie unter [Konfigurieren von Anti-Spam-Richtlinien in Office 365](configure-your-spam-filter-policies.md).

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Schritt 6: Verwenden des Microsoft 365 Admin Centers, um Ihren MX-Eintrag auf EOP zu verweisen

Befolgen Sie die Konfigurationsschritte für Office 365-Domänen, um den MX-Eintrag für die Domäne zu aktualisieren, damit Ihre eingehenden E-Mails über EOP weitergeleitet werden. Weitere Informationen finden Sie, wenn Sie Ihre DNS-Einträge verwalten, um erneut auf "Erstellen von DNS-Einträgen für [Office 365" zu verweisen.](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider?view=o365-21vianet&preserve-view=true)

Woher wissen Sie, dass diese Aufgabe erfolgreich war?

 Weitere [Informationen finden Sie unter "Testen des Nachrichtenflusses", indem Sie Ihre Office 365-Connectors überprüfen.](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)

Zu diesem Zeitpunkt haben Sie die Dienstübermittlung für einen ordnungsgemäß konfigurierten Ausgang auf dem lokalen Connector geprüft und sichergestellt, dass Ihr MX-Eintrag auf EOP verwiesen wurde. Sie können nun zusätzlich die folgenden Tests ausführen, um sicherzustellen, dass der Dienst eine E-Mail erfolgreich an Ihre lokale Umgebung versendet hat:

- Klicken Sie in der Remoteverbindungsuntersuchung auf die Registerkarte **Office 365**, führen Sie anschließend den **Eingehende SMTP-E-Mail**-Test unter **Internet E-Mail-Tests** aus.

- Senden Sie von einem webbasierten E-Mail-Konto eine E-Mail an einen E-Mail-Empfänger in Ihrer Organisation, dessen Domäne der Domäne entspricht, die Sie dem Dienst hinzugefügt haben. Bestätigen Sie mithilfe von Microsoft Outlook oder einem anderen E-Mail-Client die Zustellung der Nachricht an das lokale Postfach.

- Wenn Sie einen Test für ausgehende E-Mails durchführen möchten, können Sie von einem Benutzer in Ihrer Organisation aus eine E-Mail an ein webbasiertes E-Mail-Konto senden und überprüfen, ob die Nachricht übermittelt wurde.

## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a>Weniger häufig: Ein Hybrid-Setup mit lokalen Postfächern und in der Cloud

Wenn Sie über lokale Exchange-Postfächer und mindestens ein Postfach in der Cloud  in Exchange Online verfügen, verfügen Sie über ein Hybrid-Setup. In einer Hybrideinrichtung arbeiten Features wie die Freigabe von Frei/Gebucht-Kalendern und das E-Mail-Routing in Ihren lokalen und Cloudumgebungen zusammen. Möglicherweise haben Sie eine Hybrideinrichtung eingerichtet, während Sie Postfächer zu Exchange Online überwechseln. Eine Hybridumgebung ist anders eingerichtet als der eigenständige EOP-Schutz.

Sie können sich für ein Hybridszenario entscheiden, um cloudbasierte E-Mails für die meisten Ihrer Mitarbeiter zu nutzen. Sie können dies tun und gleichzeitig einige Postfächer lokal hosten. Beispielsweise für Ihre Rechtsabteilung.

Eine Hybrideinrichtung kann komplex sein, hat aber viele Vorteile. Weitere Informationen zum Einrichten von Hybridszenarien mit Exchange finden Sie unter [Exchange Server Hybridbereitstellungen.](https://docs.microsoft.com/Exchange/exchange-hybrid)
