---
title: Ändern des Namenservers zum Einrichten von Microsoft 365 mit einer beliebigen Domänenregistrierungsstelle.
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- okr_smb
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEU150
- GEA150
ms.assetid: a8b487a9-2a45-4581-9dc4-5d28a47010a2
description: 'Erfahren Sie, wie Sie Ihre Domäne in Microsoft 365 hinzufügen und einrichten, damit Ihre Dienste wie E-Mail und Skype for Business Online Ihren eigenen Domänennamen verwenden. '
ms.openlocfilehash: c2de2d8b75aaf50bd1d19d3fd3b507fd476d4847
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393931"
---
# <a name="change-nameservers-to-set-up-microsoft-365-with-any-domain-registrar"></a>Ändern des Namenservers zum Einrichten von Microsoft 365 mit einer beliebigen Domänenregistrierungsstelle.

 **[Lesen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.yml)**, wenn Sie nicht finden, wonach Sie suchen.

Befolgen Sie diese Anweisungen, um Ihre Domäne in Microsoft 365 hinzuzufügen und einzurichten, damit Ihre Dienste wie E-Mail und Teams Ihren eigenen Domänennamen verwenden. Hierzu überprüfen Sie Ihre Domäne und ändern dann deren Namenserver zu Microsoft 365, damit die richtigen DNS-Einträge für Sie eingerichtet werden können. Befolgen Sie diese Schritte, wenn die folgenden Aussagen auf Ihre Situation zutreffen:

- Sie verfügen über eine eigene Domäne und möchten diese in Verbindung mit Microsoft 365 einrichten.

- Sie wollen, dass Microsoft 365 Ihre DNS-Einträge für Sie verwaltet. (Wenn Sie es Ihnen lieber ist, können Sie [Ihre eigenen DNS-Einträge verwalten](../setup/add-domain.md).)

## <a name="add-a-txt-or-mx-record-for-verification"></a>Hinzufügen eines TXT- oder MX-Eintrags zur Überprüfung

> [!NOTE]
> Sie müssen nur einen der beiden Einträge erstellen. TXT ist der bevorzugte Eintragstyp, jedoch wird er von einigen DNS-Hostinganbietern nicht unterstützt. In diesem Fall können Sie stattdessen einen MX-Datensatz erstellen.

Bevor Sie Ihre Domäne in Microsoft 365 verwenden können, müssen wir uns vergewissern, dass Sie deren Besitzer sind. Ihre Fähigkeit, sich bei Ihrem Konto bei Ihrer Domänenregistrierungsstelle anzumelden und den DNS-Eintrag zu erstellen, ist für Microsoft 365 der Nachweis, dass Sie der Besitzer der Domäne sind.

> [!NOTE]
> Dieser Eintrag wird nur verwendet, um zu überprüfen, ob Sie der Besitzer Ihrer Domäne sind. Er hat keine weiteren Auswirkungen. Sie können ihn später ggf. löschen.

### <a name="find-the-area-on-your-dns-hosting-providers-website-where-you-can-create-a-new-record"></a>Suchen Sie den Bereich auf der Website Ihres DNS-Hostinganbieters, in dem ein neuer Eintrag erstellt werden kann.

1. Melden Sie sich bei der Website Ihres DNS-Hostinganbieters an.

2.  Wählen Sie Ihre Domäne aus.

3. Suchen Sie die Seite, auf der Sie DNS-Datensätze für Ihre Domäne bearbeiten können.

### <a name="create-the-record"></a>Erstellen des Eintrags

Je nachdem, ob Sie einen TXT-Eintrag oder einen MX-Eintrag erstellen möchten, führen Sie einen der folgenden Schritte aus:

**Wenn Sie einen TXT-Eintrag erstellen, verwenden Sie die folgenden Werte:**

<br>

****

|Eintragstyp|Alias oder Hostname|Wert|TTL|
|---|---|---|---|
|TXT|Führen Sie eine der folgenden Aktionen aus: Geben Sie **@** ein, lassen Sie das Feld leer, oder geben Sie Ihren Domänennamen ein.    <p> **Hinweis:** Unterschiedliche DNS-Hosts haben unterschiedliche Anforderungen für dieses Feld.|MS=ms *XXXXXXXX* <p> **Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen Wert für **Ziel oder verweisende Adresse** aus der Tabelle in Microsoft 365. [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)|Legen Sie diesen Wert auf **1 Stunde** oder die entsprechende Anzahl von Minuten ( **60** ), Sekunden ( **3600** ) usw. fest.|
|||||

**Wenn Sie einen MX-Eintrag erstellen, verwenden Sie die folgenden Werte:**

<br>

****

|Eintragstyp|Alias oder Hostname|Wert|Priority|TTL|
|---|---|---|---|---|
|MX|Geben Sie **@** oder Ihren Domänennamen ein. |MS=ms *XXXXXXXX* **Hinweis:** Dies ist ein Beispiel. Verwenden Sie hier Ihren spezifischen Wert für **Ziel oder verweisende Adresse** aus der Tabelle in Microsoft 365. [Wie finde ich diese Angabe?](../get-help-with-domains/information-for-dns-records.md)|Für **Priority** (Priorität) verwenden Sie eine geringere Priorität als für die bereits vorhandenen MX-Einträge, um Konflikte mit dem MX-Eintrag für den E-Mail-Verkehr zu vermeiden. Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](../setup/domains-faq.yml)|Legen Sie diesen Wert auf **1 Stunde** oder die entsprechende Anzahl von Minuten ( **60** ), Sekunden ( **3600** ) usw. fest.|
||||||

### <a name="save-the-record"></a>Speichern des Eintrags

Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft 365 zurück und fordern Microsoft 365 auf, nach dem Eintrag zu suchen.

Wenn Microsoft 365 den richtigen TXT-Eintrag findet, ist die Domäne überprüft.

1. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.

2. Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.

3. Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.

4. Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.

> [!NOTE]
> Normalerweise dauert es ungefähr 15 Minuten, bis DNS-Änderungen wirksam werden. Es kann jedoch gelegentlich länger dauern, bis eine von Ihnen vorgenommene Änderung im Internet im DNS-System aktualisiert wurde. Wenn nach dem Hinzufügen von DNS-Einträgen Probleme mit dem E-Mail-Fluss oder andere Probleme auftreten, lesen Sie [Behandeln von Problemen nach Änderung des Domänennamens oder von DNS-Einträgen](../get-help-with-domains/find-and-fix-issues.md).

## <a name="change-your-domains-nameserver-ns-records"></a>Ändern der Namenservereinträge (NS-Einträge) Ihrer Domäne

Als letzten Schritt im Setupassistenten für Domänen in Microsoft 365 müssen Sie nur noch eine einzige Aufgabe ausführen. Um Ihre Domäne mit Microsoft 365-Diensten wie E-Mail einzurichten, ändern Sie die Namenservereinträge (oder NS-Einträge) bei Ihrer Domänenregistrierungsstelle so, dass diese auf die primären und sekundären Microsoft 365-Namenserver verweisen. Weil Ihr DNS von Microsoft 365 gehostet wird, werden anschließend die erforderlichen DNS-Einträge für Ihre Dienste für Sie automatisch eingerichtet. Sie können die Namenservereinträge selbst aktualisieren, indem Sie die Schritte durchführen, die Ihre Domänenregistrierungsstelle eventuell in den Hilfeinhalten auf ihrer Website bereitstellt. Wenn Sie mit DNS nicht vertraut sind, wenden Sie sich an den Support bei der Domänenregistrierungsstelle.

::: moniker range="o365-worldwide"

Wenn Sie die Namenserver der Domäne auf der Website Ihrer Domänenregistrierungsstelle selbst ändern möchten, führen Sie diese Schritte aus:

1. Suchen Sie den Bereich auf der Website der Domänenregistrierungsstelle, in dem Sie die Namenserver für Ihre Domäne bearbeiten können, oder einen Bereich, in dem Sie benutzerdefinierte Namensserver verwenden können.

2. Erstellen Sie Namenservereinträge, oder bearbeiten Sie die vorhandenen Namenservereinträge so, dass sie den folgenden Werten entsprechen:

    - Vornamenserver: ns1.bdm.microsoftonline.com
    - Zweiter Nameserver: ns2.bdm.microsoftonline.com
    - Dritter Nameserver: ns3.bdm.microsoftonline.com
    - Vierter Nameserver: ns4.bdm.microsoftonline.com

   > [!TIP]
   > Idealerweise fügen Sie alle vier Einträge hinzu, aber wenn Ihre Registrierungsstelle nur zwei unterstützt, fügen Sie **ns1.bdm.microsoftonline.com** und **ns2.bdm.microsoftonline.com** hinzu.

3. Speichern Sie Ihre Änderungen.

> [!CAUTION]
> Wenn Sie die NS-Einträge Ihrer Domäne so ändern, dass sie auf die Microsoft 365-Namenserver verweisen, sind alle Dienste betroffen, die derzeit Ihrer Domäne zugeordnet sind. Wenn Sie einzelne Schritte des Assistenten übersprungen haben, z. B. das Hinzufügen von E-Mail-Adressen, oder wenn Sie Ihre Domäne für Blogs, Warenkörbe oder andere Dienste verwenden, sind zusätzliche Schritte erforderlich. Andernfalls könnte diese Änderung zu Ausfallzeiten des Dienstes führen, z. B. mangelnder E-Mail-Zugriff oder fehlender Zugriff auf Ihre aktuelle Website.

::: moniker-end

::: moniker range="o365-21vianet"

1. Suchen Sie den Bereich auf der Website der Domänenregistrierungsstelle, in dem Sie die Namenserver für Ihre Domäne bearbeiten können.

2. Erstellen Sie zwei Namenservereinträge, oder bearbeiten Sie die vorhandenen Namenservereinträge so, dass sie den folgenden Werten entsprechen:

   - Vornamenserver: ns1.dns.partner.microsoftonline.cn
   - Zweiter Nameserver: ns2.dns.partner.microsoftonline.cn

   > [!TIP]
   > Sie sollten mindestens zwei Namenservereinträge verwenden. Wenn weitere Namenserver aufgelistet sind, können Sie diese entweder löschen oder ändern in **ns3.dns.partner.microsoftonline.com** und **ns4.dns.partner.microsoftonline.com**.

3. Speichern Sie Ihre Änderungen.

> [!CAUTION]
> Wenn Sie die NS-Einträge Ihrer Domäne so ändern, dass sie auf Office 365 verweisen, das von 21Vianet-Namenservern betrieben wird, sind alle Dienste betroffen, die derzeit Ihrer Domäne zugeordnet sind. Wenn Sie einzelne Schritte des Assistenten übersprungen haben, z. B. das Hinzufügen von E-Mail-Adressen, oder wenn Sie Ihre Domäne für Blogs, Warenkörbe oder andere Dienste verwenden, sind zusätzliche Schritte erforderlich. Andernfalls könnte diese Änderung zu Ausfallzeiten des Dienstes führen, z. B. mangelnder E-Mail-Zugriff oder fehlender Zugriff auf Ihre aktuelle Website.

::: moniker-end

Hier einige weitere Schritte, die beispielsweise für E-Mail- und Websitehosting erforderlich sein können:

- Verschieben Sie alle E-Mail-Adressen, die Ihre Domäne verwenden, auf Microsoft 365, bevor Sie Ihre NS-Einträge ändern.

- Möchten Sie eine Domäne hinzufügen, die zurzeit mit einer Websiteadresse verwendet wird, beispielsweise „www.fourthcoffee.com“? Sie können die nachfolgenden Schritte beim Hinzufügen der Domäne durchführen, um den aktuellen Host als Host für die Website beizubehalten, sodass die Website weiterhin erreichbar ist, nachdem Sie die NS-Einträge der Domäne so geändert haben, dass sie auf Microsoft 365 verweisen.

1. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.

2. Wählen Sie auf der Seite **Domänen** eine Domäne aus.

3. Wählen Sie auf der Seite "Domänendetails" die Registerkarte **"DNS-Einträge"** aus.

4. Wählen Sie **Datensatz hinzufügen** aus.

5. Wählen Sie im Bereich **"Benutzerdefinierten DNS-Eintrag hinzufügen"** in der Dropdownliste **"Typ"** die Option **A (Adresse)** aus.

6. Geben Sie im Feld **Hostname oder Alias** **@** .

7. Geben Sie im **Feld "IP-Adresse"** die statische IP-Adresse für die Website ein, auf der sie derzeit gehostet wird. Beispiel: 172.16.140.1.

   > [!IMPORTANT]
   > Dies muss eine _statische_ IP-Adresse für die Website sein, keine _dynamische_ IP-Adresse. Um sicherzustellen, dass Sie eine statische IP-Adresse für Ihre öffentliche Website abrufen können, wenden Sie sich an die Website, auf der Ihre Website gehostet wird.

8. Wenn Sie die TTL-Einstellung für den Datensatz ändern möchten, wählen Sie eine neue Zeitspanne aus der **TTL-Dropdownliste** aus. Fahren Sie andernfalls mit Schritt 9 fort.

9. Klicken Sie auf **Speichern**.

Darüber hinaus können Sie einen CNAME-Eintrag erstellen, damit Kunden Ihre Website besser finden können.

1. Wählen Sie **Datensatz hinzufügen** aus.
2. Wählen Sie im Bereich **"Benutzerdefinierten DNS-Eintrag hinzufügen"** in der Dropdownliste **"Typ"** die Option **CNAME (Alias)** aus.
3. Geben Sie im Feld **Hostname oder Alias** **www** ein.
4. Geben Sie im Feld **"Punkte zu Adresse"** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für Ihre Website ein. Beispiel: **contoso.5om**.
5. Wenn Sie die TTL-Einstellung für den Datensatz ändern möchten, wählen Sie eine neue Zeitspanne aus der **TTL-Dropdownliste** aus. Fahren Sie andernfalls mit Schritt 6 fort.
6. Klicken Sie auf **Speichern**.

Nachdem die Namenservereinträge so aktualisiert wurden, dass sie auf Microsoft verweisen, ist Ihre Domäneneinrichtung abgeschlossen. E-Mails werden an Microsoft weitergeleitet, und der Datenverkehr zu Ihrer Websiteadresse wird weiterhin zu Ihrem aktuellen Websitehost geleitet."

> [!NOTE]
> Es kann mehrere Stunden dauern, bis Ihre Namenservereinträge im Internet im gesamten DNS-System aktualisiert wurden. Danach sind Ihre Microsoft-E-Mails und andere Dienste alle dafür eingerichtet, mit Ihrer Domäne zu funktionieren.

## <a name="related-content"></a>Verwandte Inhalte

[Hinzufügen von DNS-Einträgen zum Verbinden Ihrer Domäne](create-dns-records-at-any-dns-hosting-provider.md) (Artikel)\
[Suchen und Beheben von Problemen, nachdem Ihre Domäne oder DNS-Einträge hinzugefügt wurden](find-and-fix-issues.md) (Artikel)\
[Domänen verwalten](index.yml) (Linkseite)
