---
title: Konfigurieren der standardmäßigen Verbindungsfilter Richtlinie
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie die Verbindungsfilterung in Exchange Online Protection (EoP) konfigurieren, um e-Mails von e-Mail-Servern zuzulassen oder zu blockieren.
ms.openlocfilehash: d69ec30c9d6d812bf3bbcc6dc5b6df332d9dd0b5
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203371"
---
# <a name="configure-connection-filtering"></a>Konfigurieren von Verbindungsfiltern

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Wenn Sie ein Microsoft 365-Kunde mit Postfächern in Exchange Online oder einem eigenständigen Exchange Online Schutz-Kunden (EoP) ohne Exchange Online Postfächer sind, verwenden Sie die Verbindungsfilterung in EoP (insbesondere die standardmäßige Verbindungsfilter Richtlinie), um gute oder ungültige Quell-e-Mail-Server anhand ihrer IP-Adressen zu identifizieren. Die Hauptkomponenten der Standardverbindungsfilter-Richtlinie sind:

- **IP-Zulassungsliste**: Überspringen der Spamfilterung für alle eingehenden Nachrichten von den Quell-e-Mail-Servern, die Sie über die IP-Adresse oder den IP-Adressbereich angeben. In Szenarien, in denen die Spamfilterung bei Nachrichten aus diesen Quellen möglicherweise weiterhin auftritt, lesen Sie die Szenarien, in [denen Nachrichten von Quellen in der Liste der zugelassenen IP-Adressen](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) weiter unten in diesem Thema gefiltert werden. Weitere Informationen dazu, wie die IP-Zulassungsliste in Ihre allgemeine Strategie für sichere Absender passt, finden Sie unter [Create Safe Sender Lists in EoP](create-safe-sender-lists-in-office-365.md).

- **IP-Sperrliste**: blockieren Sie alle eingehenden Nachrichten von den Quell-e-Mail-Servern, die Sie über die IP-Adresse oder den IP-Adressbereich angeben. Die eingehenden Nachrichten werden abgelehnt, nicht als Spam gekennzeichnet, und es erfolgt keine zusätzliche Filterung. Weitere Informationen dazu, wie die IP-Sperrliste in Ihre gesamte blockierte Absender Strategie passt, finden Sie unter [Create Block Sender Lists in EoP](create-block-sender-lists-in-office-365.md).

- Liste **sicherer**Adressen: die Liste *sicherer* Adressen ist eine dynamische Zulassungsliste im Microsoft-Rechenzentrum, für die keine Kundenkonfiguration erforderlich ist. Microsoft identifiziert diese vertrauenswürdigen e-Mail-Quellen von Abonnements für verschiedene Drittanbieter Listen. Sie können die Verwendung der Liste sicherer Adressen aktivieren oder deaktivieren. Sie können die Quell-e-Mail-Server nicht in der Liste sicherer Adressen konfigurieren. Die Spam Filterung wird bei eingehenden Nachrichten von den e-Mail-Servern in der Liste sicherer Adressen übersprungen.

In diesem Thema wird beschrieben, wie Sie die standardmäßige Verbindungsfilter Richtlinie im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EoP PowerShell für Organisationen ohne Exchange Online Postfächer) konfigurieren. Weitere Informationen darüber, wie die Verbindungsfilterung in EoP verwendet wird, sind Teil der allgemeinen Antispam-Einstellungen in Ihrer Organisation, siehe [Anti-Spam Protection](anti-spam-protection.md).

> [!NOTE]
> Die IP-Zulassungsliste, die Liste sicherer Adressen und die IP-Sperrliste sind ein Teil ihrer allgemeinen Strategie zum Zulassen oder Blockieren von e-Mails in Ihrer Organisation. Weitere Informationen finden Sie unter [Erstellen sicherer Absenderlisten](create-safe-sender-lists-in-office-365.md) und [Erstellen blockierter Absenderlisten](create-block-sender-lists-in-office-365.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Um direkt zur Seite **Antispameinstellungen** zu wechseln, verwenden Sie <https://protection.office.com/antispam>.

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Bevor Sie die in diesem Artikel besprochenen Verfahren ausführen können, müssen Ihnen Berechtigungen zugewiesen werden:

  - Um die standardmäßige Verbindungsfilter Richtlinie zu ändern, müssen Sie Mitglied einer der folgenden Rollengruppen sein:

    - **Organisationsverwaltung** oder **Sicherheitsadministrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
    - **Organisationsverwaltung** oder **Nachrichtenschutz** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Für den schreibgeschützten Zugriff auf die standardmäßige Verbindungsfilter Richtlinie müssen Sie Mitglied einer der folgenden Rollengruppen sein:

    - **Security Reader** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
    - **Schreibgeschützte Organisationsverwaltung** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Um die Quell-IP-Adressen der e-Mail-Server (Absender) zu finden, die Sie zulassen oder blockieren möchten, können Sie das Kopfzeilenfeld Connecting IP (**CIP**) im Nachrichtenkopf überprüfen. Informationen zum Anzeigen einer Nachrichtenkopfzeile in verschiedenen e-Mail-Clients finden Sie unter [View Internet Message Headers in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).

- Die IP-Zulassungsliste hat Vorrang vor der IP-Sperrliste (eine Adresse in beiden Listen wird nicht blockiert).

- Die IP-Zulassungsliste und die IP-Sperrliste unterstützen jeweils maximal 1273 Einträge, wobei es sich bei einem Eintrag um eine einzelne IP-Adresse, einen IP-Adressbereich oder eine CIDR-IP (classly InterDomain Routing) handelt.

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a>Verwenden des Security & Compliance Center zum Ändern der standardmäßigen Verbindungsfilter Richtlinie

1. Im Security & Compliance Center und wechseln Sie zu **Threat Management** \> **Policy** \> **Anti-Spam**.

2. Erweitern Sie auf der Seite **Anti-Spam-Einstellungen** die Option **Verbindungsfilter Richtlinie** , indem ![ Sie auf Symbol erweitern klicken ](../../media/scc-expand-icon.png) und dann auf **Richtlinie bearbeiten**klicken.

3. Konfigurieren Sie im **Standard** Flyout, das angezeigt wird, eine der folgenden Einstellungen:

   - **Beschreibung**: Geben Sie optionalen beschreibenden Text ein.

   - **IP-Zulassungsliste**: Klicken Sie auf **Bearbeiten**. Geben Sie im Flyout **IP-Zulassungsliste** , das angezeigt wird, eine IPv4-Adresse in das Feld **Adresse oder Adressbereich** ein, indem Sie die folgende Syntax verwenden:

     - Einzelne IP-Adresse: zum Beispiel 192.168.1.1.

     - IP-Bereich: beispielsweise 192.168.0.1-192.168.0.254.

     - CIDR-IP: beispielsweise 192.168.0.1/25. Gültige Netzwerkmasken Werte sind/24 bis/32. Wenn Sie die Spamfilterung für CIDR-IP-Masken Werte/1 bis/23 überspringen möchten, lesen Sie den Abschnitt [Spamfilterung für eine CIDR-IP außerhalb des verfügbaren Bereichs](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) weiter unten in diesem Thema.

     Klicken Sie zum Hinzufügen der IP-Adresse oder des Adressbereichs auf Add-Symbol **Hinzufügen** ![ ](../../media/ITPro-EAC-AddIcon.png) . Um einen Eintrag zu entfernen, wählen Sie den Eintrag in **zulässiger IP-Adresse** aus, **und klicken Sie dann auf Entfernen** ![ ](../../media/scc-remove-icon.png) . Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

   - **IP-Sperrliste**: Klicken Sie auf **Bearbeiten**. Geben Sie im Flyout **IP-Sperrliste** , das angezeigt wird, eine einzelne IP-Adresse, einen IP-Bereich oder eine CIDR-IP in das Feld **Adresse oder Adressbereich** ein, wie zuvor in der Einstellung **IP-Zulassungsliste** beschrieben.

     Klicken Sie zum Hinzufügen der IP-Adresse oder des Adressbereichs auf Add-Symbol **Hinzufügen** ![ ](../../media/ITPro-EAC-AddIcon.png) . Um einen Eintrag zu entfernen, wählen Sie den Eintrag unter **blockierte IP-Adresse** aus, **und klicken Sie dann auf Entfernen** ![ ](../../media/scc-remove-icon.png) . Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

   - Aktivieren Sie die Option **sichere Liste**: Aktivieren oder deaktivieren Sie die Verwendung der Liste sicherer Adressen, um bekannte, gute Absender zu identifizieren, die die Spamfilterung überspringen sollen.

4. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a>Verwenden Sie das Security & Compliance Center, um die standardmäßige Verbindungsfilter Richtlinie anzuzeigen.

1. Im Security & Compliance Center und wechseln Sie zu **Threat Management** \> **Policy** \> **Anti-Spam**.

2. Klicken Sie auf der Seite **Anti-Spam-Einstellungen** auf die Dropdownliste neben der Standardrichtlinie **Verbindungsfilter Richtlinie**.

3. Die Richtlinieneinstellungen werden in der Dropdownliste angezeigt, die geöffnet wird.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a>Verwenden Exchange Online PowerShell oder eigenständiger EoP PowerShell zum Ändern der standardmäßigen Verbindungsfilter Richtlinie

Verwenden Sie die folgende Syntax:

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

**Hinweise**:

- Gültige IP-Adress-oder Adressbereichs Werte sind:

  - Einzelne IP-Adresse: zum Beispiel 192.168.1.1.

  - IP-Bereich: beispielsweise 192.168.0.1-192.168.0.254.

  - CIDR-IP: beispielsweise 192.168.0.1/25. Gültige Netzwerkmasken Werte sind/24 bis/32.

- Verwenden Sie die folgende Syntax, um vorhandene Einträge mit den angegebenen Werten zu über *Schreiben* : `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` .

- Verwenden Sie die folgende Syntax, um IP-Adressen oder Adressbereiche *hinzuzufügen oder zu entfernen* , ohne andere vorhandene Einträge zu beeinträchtigen: `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` .

- Verwenden Sie den Wert, um die IP-Zulassungsliste oder IP-Sperrliste zu leeren `$null` .

In diesem Beispiel werden die IP-Zulassungsliste und die IP-Sperrliste mit den angegebenen IP-Adressen und Adressbereichen konfiguriert.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

In diesem Beispiel werden die angegebenen IP-Adressen und Adressbereiche aus der IP-Zulassungsliste hinzugefügt und entfernt.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-HostedConnectionFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedconnectionfilterpolicy).

## <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie die standardmäßige Verbindungsfilter Richtlinie erfolgreich geändert haben:

- Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Anti-Spam** \> Klicken Sie neben **Verbindungsfilter Richtlinie (immer ein**) auf die Dropdownliste, und überprüfen Sie die Einstellungen.

- Führen Sie in Exchange Online PowerShell oder in der eigenständigen EoP PowerShell den folgenden Befehl aus, und überprüfen Sie die Einstellungen:

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- Senden Sie eine Testnachricht aus einem Eintrag in der Liste der zugelassenen IP-Adressen.

## <a name="additional-considerations-for-the-ip-allow-list"></a>Weitere Überlegungen zur IP-Zulassungsliste

In den folgenden Abschnitten werden zusätzliche Elemente aufgeführt, die Sie kennen müssen, wenn Sie die IP-Zulassungsliste konfigurieren.

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>Überspringen der Spamfilterung für eine CIDR-IP außerhalb des verfügbaren Bereichs

Wie weiter oben in diesem Thema beschrieben, können Sie nur eine CIDR-IP mit der Netzwerkmaske/24 to/32 in der Liste der zugelassenen IP-Adressen verwenden. Um die Spamfilterung bei Nachrichten von Quell-e-Mail-Servern im Bereich/1 bis/23 zu überspringen, müssen Sie Exchange-Nachrichtenfluss Regeln (auch bekannt als Transportregeln) verwenden. Es wird jedoch empfohlen, dass Sie dies nicht tun, wenn dies möglich ist, da die Nachrichten blockiert werden, wenn eine IP-Adresse im/1 to/23 CIDR-IP-Bereich in einem der proprietären oder von Drittanbieter-Sperrlisten von Microsoft angezeigt wird.

Da Sie sich nun vollständig mit den potenziellen Problemen vertraut machen, können Sie eine e-Mail-Fluss Regel mit den folgenden Einstellungen (mindestens) erstellen, um sicherzustellen, dass Nachrichten von diesen IP-Adressen die Spamfilterung überspringen:

- Regelbedingung: **diese Regel anwenden, wenn** \> sich die IP-Adresse **des Absenders** \> **in einem dieser Bereiche befindet oder genau übereinstimmt** \> (geben Sie Ihre CIDR-IP mit der Netzwerkmaske a/1 bis/23 ein).

- Regelaktion: **Ändern der Nachrichteneigenschaften** \> **legen Sie die Spam Confidence Level (SCL)** \> **Bypass-Spamfilterung**fest.

Sie können die Regel überwachen, die Regel testen, die Regel während eines bestimmten Zeitraums und andere Auswahlen aktivieren. Wir empfehlen, die Regel über eine bestimmte Zeit zu testen, bevor Sie sie erzwingen. Weitere Informationen finden Sie unter [Verwalten von Nachrichtenfluss Regeln in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>Überspringen der Spamfilterung für selektive e-Mail-Domänen aus derselben Quelle

Das Hinzufügen einer IP-Adresse oder eines Adressbereichs zur IP-Zulassungsliste bedeutet normalerweise, dass Sie allen eingehenden Nachrichten von dieser e-Mail-Quelle vertrauen. Was geschieht, wenn diese Quelle e-Mails aus mehreren Domänen sendet und Sie die Spamfilterung für einige dieser Domänen überspringen möchten, aber nicht für andere? Sie können nicht allein die IP-Zulassungsliste verwenden, aber Sie können die IP-Zulassungsliste in Kombination mit einer e-Mail-Fluss Regel verwenden.

Beispielsweise sendet der Quell-e-Mail-Server 192.168.1.25 e-Mails von den Domänen contoso.com, fabrikam.com und tailspintoys.com, aber Sie möchten die Spamfilterung für Nachrichten von Absendern in fabrikam.com nur überspringen. Führen Sie dazu die folgenden Schritte aus:

1. Fügen Sie 192.168.1.25 zur Liste der zugelassenen IP-Adressen hinzu.

2. Konfigurieren Sie eine e-Mail-Fluss Regel mit den folgenden Einstellungen (mindestens):

   - Regelbedingung: **diese Regel anwenden, wenn** \> sich die IP-Adresse **des Absenders** \> **in einem dieser Bereiche befindet oder genau mit 192.168.1.25 übereinstimmt** \> (die gleiche IP-Adresse oder der gleiche Adressbereich, die Sie der Liste der zugelassenen IP-Adressen im vorherigen Schritt hinzugefügt haben).

   - Regelaktion: **Ändern der Nachrichteneigenschaften** \> **legen Sie die SCL-Bewertung (Spam Confidence Level)** \> **0**fest.

   - Regel Ausnahme: **die Absender** \> **Domäne ist** \> Fabrikam.com (nur die Domäne oder Domänen, deren Spamfilterung übersprungen werden soll).

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>Szenarien, in denen Nachrichten von Quellen in der IP-Zulassungsliste weiterhin gefiltert werden

Nachrichten von einem e-Mail-Server in Ihrer IP-Zulassungsliste unterliegenweiterhin Spamfilterung in den folgenden Szenarien:

- Eine IP-Adresse in Ihrer IP-Zulassungsliste wird auch in einem lokalen, IP-basierten eingehenden Connector in *einem beliebigen* Mandanten in Microsoft 365 (nennen wir diesen Mandanten a) **und** dem Mandanten a und dem EoP-Server, der zuerst auf die Nachricht stößt, in der *gleichen* Active Directory Gesamtstruktur in den Microsoft-Rechenzentren konfiguriert. In diesem Szenario wird **IPV: Cal** *is* zu den [Antispam-Nachrichtenkopf Zeilen](anti-spam-message-headers.md) der Nachricht hinzugefügt (womit die Nachricht umgangen wird Spamfilterung), aber die Nachricht ist weiterhin Gegenstand der Spamfilterung.

- Ihr Mandant, der die Liste der zugelassenen IP-Adressen enthält, und der EoP-Server, der die Nachricht zuerst findet, befinden sich beide in *unterschiedlichen* Active Directory Gesamtstrukturen in den Microsoft-Rechenzentren. In diesem Szenario wird **IPV: Cal** *nicht* den Nachrichtenkopfzeilen hinzugefügt, sodass die Nachricht weiterhin der Spamfilterung unterliegt.

Wenn beide Szenarien auftreten, können Sie eine e-Mail-Fluss Regel mit den folgenden Einstellungen (mindestens) erstellen, um sicherzustellen, dass Nachrichten von den problematischen IP-Adressen die Spamfilterung überspringen:

- Regelbedingung: **diese Regel anwenden, wenn** \> sich die IP-Adresse **des Absenders** \> **in einem dieser Bereiche befindet oder genau übereinstimmt** \> (Ihre IP-Adresse oder Adressen).

- Regelaktion: **Ändern der Nachrichteneigenschaften** \> **legen Sie die Spam Confidence Level (SCL)** \> **Bypass-Spamfilterung**fest.

## <a name="new-to-microsoft-365"></a>Neu bei Microsoft 365?

|<!-- a -->|
|---|
|![Das kurze Symbol für LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?** Entdecken Sie ﻿kostenlose Video Kurse für **Administratoren und IT-Experten**, die Ihnen von LinkedIn Learning angeboten werden.|
|
