---
title: Hinzufügen von DNS-Einträgen zum Verbinden Ihrer Domäne
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge bei einem beliebigen DNS-Hostinganbieter für Microsoft 365 erstellen.
ms.custom:
- okr_smb
- AdminSurgePortfolio
ms.openlocfilehash: 06a5e7d081a16cd8d5aae28268b3aaf737981a43
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051042"
---
# <a name="add-dns-records-to-connect-your-domain"></a>Hinzufügen von DNS-Einträgen zum Verbinden Ihrer Domäne

Wenn Sie eine Domäne bei einem Drittanbieter-Hostinganbieter gekauft haben, können Sie diese mit Microsoft 365 verbinden, indem Sie die DNS-Einträge im Konto Ihrer Registrierungsstelle aktualisieren.

Am Ende dieser Schritte bleibt Ihre Domäne bei dem Host registriert, von dem Sie die Domäne gekauft haben. Microsoft 365 kann sie aber für E-Mail-Adressen (z. B. „Benutzer@IhreDomäne.com“) und andere Dienste verwenden.

Wenn Sie keine Domäne hinzufügen, verwenden Personen in Ihrer Organisation die Domäne „onmicrosoft.com“ für ihre E-Mail-Adressen, bis Sie dies tun. Es ist wichtig, dass Sie Ihre Domäne hinzufügen, bevor Sie Benutzer hinzufügen, damit Sie diese nicht zweimal einrichten müssen.

[Lesen Sie in den die häufig gestellten Fragen (FAQ) zu Domänen nach](../setup/domains-faq.yml), wenn Sie unten nicht finden, wonach Sie suchen.

## <a name="step-1-add-a-txt-or-mx-record-to-verify-you-own-the-domain"></a>Schritt 1: Fügen Sie einen TXT- oder MX-Eintrag hinzu, um den Besitz der Domäne zu verifizieren

### <a name="recommended-verify-with-a-txt-record"></a>Die Verifizierung anhand eines TXT-Eintrags wird empfohlen

Zunächst müssen Sie nachweisen, dass Sie der Besitzer der Domäne sind, die Sie Microsoft 365 hinzufügen möchten.

1. Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com/) an, und wählen Sie **Alle anzeigen** > **Einstellungen** > **Domänen** aus.
2. Melden Sie sich auf einer neuen Browserregisterkarte oder in einem neuen Browserfenster bei Ihrem DNS-Hostinganbieter an, und suchen Sie dann die Stelle, an der Sie Ihre DNS-Einstellungen verwalten (z. B. Zonendateieinstellungen, Domänen verwalten, Domänen-Manager, DNS-Manager).
3. Wechseln Sie zur Seite „DNS-Manager“ Ihres Anbieters, und fügen Sie den im Admin Center angegebenen TXT-Eintrag zu Ihrer Domäne hinzu.

Das Hinzufügen dieses Eintrags wirkt sich nicht auf Ihre bestehende E-Mail oder andere Dienste aus, und Sie können ihn bedenkenlos entfernen, sobald Ihre Domäne mit Microsoft 365 verbunden ist.

Beispiel:
- TXT-Name: `@`
- TXT-Wert: MS=ms######## (eindeutige ID aus dem Admin Center)
- TTL: `3600‎` (oder die Standardeinstellung Ihres Anbieters)

4. Speichern Sie den Eintrag, wechseln Sie zurück zum Admin Center, und wählen Sie **Überprüfen** aus. Normalerweise dauert es ungefähr 15 Minuten, bis Eintragsänderungen registriert werden, doch manchmal kann es auch länger dauern. Gewähren Sie dem Vorgang etwas Zeit sowie ein paar Versuche, um die Änderung zu übernehmen.

Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.

### <a name="verify-with-an-mx-record"></a>Verifizierung anhand eines MX-Eintrags

Wenn Ihre Registrierungsstelle das Hinzufügen von TXT-Einträgen nicht unterstützt, können Sie die Verifizierung anhand eines MX-Eintrags vornehmen.

1. Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com/) an, und wählen Sie **Alle anzeigen** > **Einstellungen** > **Domänen** aus.
2. Melden Sie sich auf einer neuen Browserregisterkarte oder in einem neuen Browserfenster bei Ihrem DNS-Hostinganbieter an, und suchen Sie dann die Stelle, an der Sie Ihre DNS-Einstellungen verwalten (z. B. Zonendateieinstellungen, Domänen verwalten, Domänen-Manager, DNS-Manager).
3. Wechseln Sie zur Seite „DNS-Manager“ Ihres Anbieters und fügen Sie den im Admin Center angegebenen MX-Eintrag zu Ihrer Domäne hinzu.

Die **Priorität** dieses MX-Eintrags muss die höchste für alle vorhandenen MX-Einträge der Domäne sein. Andernfalls kann dies Auswirkungen auf das Senden und Empfangen von E-Mails haben. Sie sollten diese Einträge löschen, sobald die Verifizierung der Domäne abgeschlossen ist.

Stellen Sie sicher, dass die Felder auf die folgenden Werte festgelegt sind:

- Eintragstyp: `MX`
- Priorität: Legen Sie dies auf den höchsten verfügbaren Wert fest, in der Regel `0`.
- Hostname: `@`
- Verweist auf die Adresse: Kopieren Sie den Wert aus dem Admin Center, und fügen Sie ihn hier ein.
- TTL: `3600‎` (oder die Standardeinstellung Ihres Anbieters)

Wenn Microsoft den richtigen MX-Eintrag findet, ist die Domäne verifiziert.

## <a name="step-2-add-dns-records-to-connect-microsoft-services"></a>Schritt 2: Hinzufügen von DNS-Einträgen zum Verbinden von Microsoft-Diensten

Melden Sie sich auf einer neuen Browserregisterkarte oder in einem neuen Browserfenster bei Ihrem DNS-Hostinganbieter an, und suchen Sie die Stelle, an der Sie Ihre DNS-Einstellungen verwalten (z. B. Zonendateieinstellungen, Domänen verwalten, Domänen-Manager, DNS-Manager).

Sie fügen mehrere unterschiedliche Typen von DNS-Einträgen hinzu, je nachdem, welche Dienste Sie aktivieren möchten. 

### <a name="add-an-mx-record-for-email-outlook-exchange-online"></a>Hinzufügen eines MX-Eintrags für E-Mail (Outlook, Exchange Online)
**Bevor Sie beginnen:** Wenn Benutzer bereits über E-Mail-Adressen mit Ihrer Domäne verfügen (z. B. „Benutzer@IhreDomäne.com“), erstellen Sie deren Konten im Admin Center, bevor Sie Ihre MX-Einträge einrichten. Auf diese Weise erhalten sie weiterhin E-Mail. Nachdem Sie den MX-Eintrag Ihrer Domäne aktualisiert haben, treffen alle neuen E-Mails für jeden Benutzer Ihr Domäne in Microsoft 365 ein. Alle E-Mails, die Sie bereits erhalten haben, bleiben so lange auf Ihrem aktuellen E-Mail-Host gespeichert, bis Sie die [Migration von E-Mails und Kontakten zu Microsoft 365](../setup/migrate-email-and-contacts-admin.md) beschließen.

Sie erhalten nun die Informationen zu dem MX-Eintrag vom Assistenten für die Domäneneinrichtung im Admin Center.

Fügen Sie auf der Website Ihres Hostinganbieters einen neuen MX-Eintrag hinzu.
Stellen Sie sicher, dass die Felder auf die folgenden Werte festgelegt sind:

- Eintragstyp: `MX`
- Priorität: Legen Sie dies auf den höchsten verfügbaren Wert fest, in der Regel `0`.
- Hostname: `@`
- Verweist auf die Adresse: Kopieren Sie den Wert aus dem Admin Center, und fügen Sie ihn hier ein.
- TTL: `3600‎` (oder die Standardeinstellung Ihres Anbieters)

Speichern Sie den Eintrag, und entfernen Sie dann alle anderen MX-Einträge.

### <a name="add-cname-records-to-connect-other-services-teams-exchange-online-aad-mdm"></a>Hinzufügen von CNAME-Einträgen zum Verbinden anderer Dienste (Teams, Exchange Online, AAD, MDM)
Sie erhalten nun die Informationen zu den CNAME-Einträgen vom Assistenten für die Domäneneinrichtung im Admin Center.

Fügen Sie auf der Website Ihres Hostinganbieters CNAME-Einträge für jeden Dienst hinzu, den Sie verbinden möchten.
Stellen Sie sicher, dass jedes der Felder auf die jeweiligen folgenden Werte festgelegt ist:

- Eintragstyp: `CNAME (Alias)`
- Host: Fügen Sie hier die Werte ein, die Sie aus dem Admin Center kopieren.
- Verweist auf die Adresse: Kopieren Sie den Wert aus dem Admin Center, und fügen Sie ihn hier ein.
- TTL: `3600‎` (oder die Standardeinstellung Ihres Anbieters)


### <a name="add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online"></a>Hinzufügen oder Bearbeiten eines SPF TXT-Eintrags, um E-Mail-Spam zu verhindern (Outlook, Exchange Online)
**Bevor Sie beginnen:** Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft 365 keinen neuen. Fügen Sie stattdessen die erforderlichen Microsoft 365-Werte dem aktuellen Eintrag auf der Website Ihres Hostinganbieters hinzu. Damit verfügen Sie über einen *einzigen* SPF-Eintrag, in dem beide Wertemengen enthalten sind.

Bearbeiten Sie auf der Website Ihres Hostinganbieters den vorhandenen SPF-Eintrag, oder erstellen Sie einen neuen SPF-Eintrag.
Stellen Sie sicher, dass die Felder auf die folgenden Werte festgelegt sind:

- Eintragstyp: `TXT (Text)`
- Host: `@`
- TXT-Wert: `v=spf1 include:spf.protection.outlook.com -all`
- TTL: `3600‎` (oder die Standardeinstellung Ihres Anbieters)

Speichern Sie den Eintrag.

Überprüfen Sie Ihren SPF-Eintrag, indem Sie eines dieser [SPF-Überprüfungstools](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain) verwenden.

SPF ist dafür vorgesehen, Spoofing möglichst zu verhindern, es gibt aber Spoofing-Techniken, vor denen SPF nicht schützen kann. Zum Schutz vor diesen Techniken sollten Sie, nachdem Sie SPF eingerichtet haben, auch DKIM und DMARC für Microsoft 365 einrichten. 

Um hiermit zu beginnen, lesen Sie [Verwenden von DKIM zur Überprüfung von ausgehenden E-Mails, die von Ihrer Domäne in Microsoft 365 gesendet wurden](../../security/defender-365-security/use-dkim-to-validate-outbound-email.md) und [Verwenden von DMARC zum Überprüfen von E-Mail in Microsoft 365](../../security/defender-365-security/use-dmarc-to-validate-email.md).

### <a name="add-srv-records-for-communications-services-teams-skype-for-business"></a>Hinzufügen von SRV-Einträgen für Kommunikationsdienste (Teams, Skype for Business)

Fügen Sie auf der Website Ihres Hostinganbieters SRV-Einträge für jeden Dienst hinzu, den Sie verbinden möchten.
Stellen Sie sicher, dass jedes der Felder auf die jeweiligen folgenden Werte festgelegt ist:

- Eintragstyp: `SRV (Service)`
- Name: `@`
- Ziel: Kopieren Sie den Wert aus dem Admin Center, und fügen Sie ihn hier ein.
- Protokoll: Kopieren Sie den Wert aus dem Admin Center, und fügen Sie ihn hier ein.
- Dienst: Kopieren Sie den Wert aus dem Admin Center, und fügen Sie ihn hier ein.
- Priorität: `100`
- Gewichtung: `1`
- Port: Kopieren Sie den Wert aus dem Admin Center, und fügen Sie ihn hier ein.
- TTL: `3600‎` (oder die Standardeinstellung Ihres Anbieters)

Speichern Sie den Eintrag.

#### <a name="srv-record-field-restrictions-and-workarounds"></a>Einschränkungen und Problemumgehungen für SRV-Eintragsfelder
Einige Hostinganbieter richten Beschränkungen für Feldwerte in SRV-Einträgen ein. Hier finden Sie einige gängige Problemumgehungen für diese Einschränkungen.

##### <a name="name"></a>Name
Wenn Ihr Hostinganbieter die Einstellung dieses Felds auf **@** nicht zulässt, lassen Sie es leer. Verwenden Sie diesen Ansatz *nur*, wenn Ihr Hostinganbieter über separate Felder für die Werte „Dienst“ und „Protokoll“ verfügt. Andernfalls lesen Sie die Anmerkungen unten zu „Dienst“ und „Protokoll“.

##### <a name="service-and-protocol"></a>„Dienst“ und „Protokoll“
Wenn Ihr Hostinganbieter diese Felder für SRV-Einträge nicht bereitstellt, müssen Sie die Werte für **Dienst** und **Protokoll** im Feld **Name** des Eintrags angeben. (Hinweis: Abhängig von Ihrem Hostinganbieter kann das Feld **Name** auch anders heißen, z. B: **Host**, **Hostname** oder **Subdomäne**). Um diese Werte hinzuzufügen, erstellen Sie eine einzelne Zeichenfolge und trennen die Werte durch einen Punkt. 

Beispiel: `_sip._tls`

##### <a name="priority-weight-and-port-br"></a>„Priorität“, „Gewichtung“ und „Port“ <br>
Wenn Ihr Hostinganbieter diese Felder für SRV-Einträge nicht bereitstellt, müssen Sie sie im Feld **Ziel** des Eintrags angeben. (Hinweis: Abhängig von Ihrem Hostinganbieter kann das Feld **Ziel** auch anders heißen, z. B.: **Inhalt**, **IP-Adresse** oder **Zielhost**.) 

Um diese Werte hinzuzufügen, erstellen Sie eine einzelne Zeichenfolge, trennen die Werte durch Leerzeichen und lassen diese *manchmal mit einem Punkt enden* (wenden Sie sich an Ihren Anbieter, wenn Sie unsicher sind). Die Werte müssen in dieser Reihenfolge eingegeben werden: „Priorität“, „Gewichtung“, „Port“, „Ziel“. 

- Beispiel 1: `100 1 443 sipdir.online.lync.com.`
- Beispiel 2: `100 1 443 sipdir.online.lync.com`