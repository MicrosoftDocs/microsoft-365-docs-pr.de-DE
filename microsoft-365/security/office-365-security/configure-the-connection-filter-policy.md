---
title: Konfigurieren der Standardmäßigen Verbindungsfilterrichtlinie
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
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie die Verbindungsfilterung in Exchange Online Protection (EOP) konfigurieren, um E-Mails von E-Mail-Servern zu erlauben oder zu blockieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ef81d602e1f6da368e9d469bf1deaf0ef2c0a6af
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165751"
---
# <a name="configure-connection-filtering"></a>Konfigurieren von Verbindungsfiltern

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Wenn Sie ein Microsoft 365-Kunde mit Postfächern in Exchange Online oder ein eigenständiger Exchange Online Protection (EOP)-Kunde ohne Exchange Online-Postfächer sind, verwenden Sie die Verbindungsfilterung in EOP (insbesondere die Standardverbindungsfilterrichtlinie), um gute oder ungültige Quell-E-Mail-Server nach ihren IP-Adressen zu identifizieren. Die Hauptkomponenten der Standardverbindungsfilter-Richtlinie sind:

- **IP Allow List**: Skip spam filtering for all incoming messages from the source email servers that you specify by IP address or IP address range. Szenarien, in denen die Spamfilterung für Nachrichten aus diesen Quellen weiterhin auftreten kann, finden Sie in den Szenarien, in denen Nachrichten aus Quellen [in](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) der Liste der zulässigen IP-Adressen weiter unten in diesem Artikel gefiltert werden. Weitere Informationen dazu, wie die Liste der zulässigen IP-Adressen in Ihre Gesamtstrategie für sichere Absender passen sollte, finden Sie unter Erstellen von Listen sicherer Absender [in EOP.](create-safe-sender-lists-in-office-365.md)

- **IP-Sperrliste:** Blockieren Sie alle eingehenden Nachrichten von den Quell-E-Mail-Servern, die Sie durch die IP-Adresse oder den IP-Adressbereich angeben. Die eingehenden Nachrichten werden abgelehnt, nicht als Spam gekennzeichnet, und es findet keine zusätzliche Filterung statt. Weitere Informationen dazu, wie die Liste blockierter IP in Ihre Strategie für blockierte Absender passen sollte, finden Sie unter Erstellen von Listen blockierter Absender [in EOP](create-block-sender-lists-in-office-365.md).

- **Sichere Liste:** Die Liste sicherer Daten *ist* eine dynamische Liste zulässiger Daten im Microsoft-Rechenzentrum, für die keine Kundenkonfiguration erforderlich ist. Microsoft identifiziert diese vertrauenswürdigen E-Mail-Quellen aus Abonnements für verschiedene Drittanbieterlisten. Sie aktivieren oder deaktivieren die Verwendung der Sicheren Liste. Sie können die Quell-E-Mail-Server nicht in der Sicheren Liste konfigurieren. Die Spamfilterung wird für eingehende Nachrichten von den E-Mail-Servern in der Liste sicherer Nachrichten übersprungen.

In diesem Thema wird beschrieben, wie Sie die standardmäßige Verbindungsfilterrichtlinie im Security & Compliance Center oder in PowerShell konfigurieren (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange Online-Postfächer). Weitere Informationen dazu, wie EOP die Verbindungsfilterung verwendet, sind Teil der allgemeinen Antispameinstellungen Ihrer Organisation, siehe [Antispamschutz.](anti-spam-protection.md)

> [!NOTE]
> Die IP-Liste, die Liste sicherer Adressen und die Liste blockierter IP-Adressen sind ein Teil Ihrer Gesamtstrategie zum Zulassen oder Blockieren von E-Mails in Ihrer Organisation. Weitere Informationen finden Sie unter ["Listen sicherer Absender erstellen"](create-safe-sender-lists-in-office-365.md) und ["Listen blockierter Absender erstellen".](create-block-sender-lists-in-office-365.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Um direkt zur Seite **Antispameinstellungen** zu wechseln, verwenden Sie <https://protection.office.com/antispam>.

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Security & Compliance Center Berechtigungen zugewiesen werden.
  - Zum Ändern der Standardmäßigen Verbindungsfilterrichtlinie müssen Sie Mitglied der Rollengruppe **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** sein.
  - Für den schreibgeschützten Zugriff auf die standardmäßige Verbindungsfilterrichtlinie  müssen Sie Mitglied der Rollengruppe "Globaler Leser" oder **"Sicherheitsleseprogramm"** sein.

  Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

  **Hinweise**:

  - Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.

- Um die Quell-IP-Adressen der E-Mail-Server (Absender) zu finden, die Sie zulassen oder blockieren möchten, können Sie das Kopfzeilenfeld für die IP -Verbindung (**CIP**) im Nachrichtenkopf überprüfen. Informationen zum Anzeigen einer Nachrichtenkopfzeile in verschiedenen E-Mail-Clients finden Sie unter [Anzeigen von Internetnachrichtenkopfzeilen in Outlook.](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)

- Die Liste der zulässigen IP-Adressen hat Vorrang vor der IP-Sperrliste (eine Adresse in beiden Listen ist nicht blockiert).

- Die Ip-Allow-Liste und die Ip-Sperrliste unterstützen jeweils maximal 1273 Einträge, wobei es sich bei einem Eintrag um eine einzelne IP-Adresse, einen IP-Adressbereich oder eine CIDR-IP (Classless InterDomain Routing) handelt.

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a>Ändern der standardverbindungsfilterrichtlinie mithilfe des Security & Compliance Center

1. Wechseln Sie im Security & Compliance  Center zu "Antispamrichtlinie für die \>  \> **Bedrohungsverwaltung".**

2. Erweitern Sie auf der Seite  **"Antispameinstellungen"** die Verbindungsfilterrichtlinie, indem Sie auf das Symbol "Erweitern" und dann auf ![ ](../../media/scc-expand-icon.png) **"Richtlinie bearbeiten" klicken.**

3. Konfigurieren Sie **im angezeigten** Standardf flyout eine der folgenden Einstellungen:

   - **Beschreibung**: Geben Sie optionalen beschreibenden Text ein.

   - **IP Allow List**: Click **Edit**. Geben Sie **im** angezeigten Flyout für die #A0 mithilfe der folgenden Syntax eine #A1 in das Feld "Adresse" oder "Adressbereich" ein: 

     - Einzelne IP: Beispiel: 192.168.1.1.

     - IP-Bereich: Beispiel: 192.168.0.1-192.168.0.254.

     - CIDR-IP: Beispiel: 192.168.0.1/25. Gültige Netzwerkmaskenwerte sind /24 bis /32. Informationen zum Überspringen der Spamfilterung für CIDR-IP-Maskenwerte /1 bis /23 finden Sie unter "Spamfilterung für [eine CIDR-IP](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) außerhalb des abschnitts verfügbarer Bereich" weiter unten in diesem Artikel.

     Klicken Sie zum Hinzufügen der IP-Adresse oder des Adressbereichs auf **"Hinzufügen"** ![ (Symbol). ](../../media/ITPro-EAC-AddIcon.png) Um einen Eintrag zu entfernen, wählen Sie den Eintrag unter **"Zugelassene IP-Adresse"** aus, und klicken Sie dann auf **"Entfernen".** ![ ](../../media/scc-remove-icon.png) Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

   - **IP-Sperrliste:** Klicken Sie auf **"Bearbeiten".** Geben Sie **im** angezeigten Flyout "IP-Sperrliste" eine einzelne IP-, IP-Bereich- oder CIDR-IP in das Feld "Adresse" oder "Adressbereich" ein, wie zuvor in der Einstellung für die Ip-Zulassen-Liste **beschrieben.** 

     Klicken Sie zum Hinzufügen der  IP-Adresse oder des Adressbereichs auf ![ "Hinzufügen". ](../../media/ITPro-EAC-AddIcon.png) Um einen Eintrag zu entfernen, wählen Sie den Eintrag in **"Blockierte IP-Adresse"** aus, und klicken Sie dann auf  ![ "Entfernen". ](../../media/scc-remove-icon.png) Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

   - **Aktivieren Sie "Sichere Liste":** Aktivieren oder deaktivieren Sie die Verwendung der Liste sicherer Absender, um bekannte, gute Absender zu identifizieren, die die Spamfilterung überspringen.

4. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a>Verwenden des Security & Compliance Center zum Anzeigen der Standardmäßigen Verbindungsfilterrichtlinie

1. Wechseln Sie im Security & Compliance  Center zu "Antispamrichtlinie für die \>  \> **Bedrohungsverwaltung".**

2. Klicken Sie **auf der Seite "Antispameinstellungen"** auf die Dropdownliste neben der Standardrichtlinie namens **"Verbindungsfilterrichtlinie".**

3. Die Richtlinieneinstellungen werden in der Dropdownliste angezeigt, die geöffnet wird.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a>Verwenden von Exchange Online PowerShell oder der eigenständigen EOP PowerShell zum Ändern der Standardmäßigen Verbindungsfilterrichtlinie

Verwenden Sie die folgende Syntax:

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

**Hinweise**:

- Gültige Werte für die IP-Adresse oder den Adressbereich sind:

  - Einzelne IP: Beispiel: 192.168.1.1.

  - IP-Bereich: Beispiel: 192.168.0.1-192.168.0.254.

  - CIDR-IP: Beispiel: 192.168.0.1/25. Gültige Netzwerkmaskenwerte sind /24 bis /32.

- Verwenden *Sie die* folgende Syntax, um vorhandene Einträge mit den angegebenen Werten zu überschreiben: `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN`

- Verwenden *Sie die folgende* Syntax, um #A0 oder Adressbereiche ohne Auswirkungen auf andere Einträge hinzuzufügen oder zu entfernen: `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}`

- Verwenden Sie den Wert, um die Liste der zulässigen oder blockierten IP-Adressen zu `$null` leeren.

In diesem Beispiel werden die Liste der zulässigen IP-Adressen und die Liste blockierter IP-Adressen mit den angegebenen IP-Adressen und Adressbereichen konfiguriert.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

In diesem Beispiel werden die angegebenen IP-Adressen und Adressbereiche aus der Liste der zulässigen IP-Adressen hinzugefügt und entfernt.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-HostedConnectionFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedconnectionfilterpolicy).

## <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Gehen Sie wie folgt vor, um die erfolgreiche Änderung der Standardverbindungsfilterrichtlinie zu überprüfen:

- Wechseln Sie im Security & Compliance  Center zu Richtlinie für die Bedrohungsverwaltung – Antispam klicken Sie auf die Dropdownliste neben der Verbindungsfilterrichtlinie \>  \>  \> **(immer EIN),** und überprüfen Sie die Einstellungen.

- Führen Sie in Exchange Online PowerShell oder der eigenständigen EOP PowerShell den folgenden Befehl aus, und überprüfen Sie die Einstellungen:

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- Senden Sie eine Testnachricht von einem Eintrag in der Liste der zulässigen IP-Adressen.

## <a name="additional-considerations-for-the-ip-allow-list"></a>Zusätzliche Überlegungen zur Liste der zulässigen IP-Adressen

In den folgenden Abschnitten werden zusätzliche Elemente aufgeführt, die Sie kennen müssen, wenn Sie die Liste der zulässigen IP-Adressen konfigurieren.

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>Überspringen der Spamfilterung für eine CIDR-IP außerhalb des verfügbaren Bereichs

Wie weiter oben in diesem Artikel beschrieben, können Sie eine CIDR-IP nur mit der Netzwerkmaske /24 bis /32 in der Liste der zulässigen IP-Adressen verwenden. Um die Spamfilterung für Nachrichten von Quell-E-Mail-Servern im Bereich /1 bis /23 zu überspringen, müssen Sie Exchange-Nachrichtenflussregeln (auch als Transportregeln bekannt) verwenden. Es wird jedoch empfohlen, dies nach Möglichkeit nicht zu tun, da die Nachrichten blockiert werden, wenn eine IP-Adresse im CIDR-IP-Bereich von /1 bis /23 in einer proprietären Oder Sperrliste von Drittanbietern von Microsoft angezeigt wird.

Da Sie nun die potenziellen Probleme vollständig kennen, können Sie eine Nachrichtenflussregel mit den folgenden Einstellungen (mindestens) erstellen, um sicherzustellen, dass Nachrichten von diesen IP-Adressen die Spamfilterung überspringen:

- Regelbedingung:  Wenden Sie diese Regel an, wenn sich die Absender-IP-Adresse in einem dieser Bereiche befindet oder exakt entspricht (geben Sie Ihre CIDR-IP mit einer \>  \>  \> Netzwerkmaske von /1 bis /23 ein).

- Regelaktion: **Ändern Sie die Nachrichteneigenschaften** Festlegen der Spam Confidence Level \> **(SCL)** \> **Spamfilter umgehen.**

Sie können die Regel überwachen, die Regel testen, die Regel während eines bestimmten Zeitraums aktivieren und andere Auswahlen treffen. Wir empfehlen, die Regel über eine bestimmte Zeit zu testen, bevor Sie sie erzwingen. Weitere Informationen finden Sie unter [Verwalten von Nachrichtenflussregeln in Exchange Online.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>Überspringen der Spamfilterung für selektive E-Mail-Domänen aus derselben Quelle

In der Regel bedeutet das Hinzufügen einer IP-Adresse oder eines Adressbereichs zur Liste der zulässigen IP-Adressen, dass Sie allen eingehenden Nachrichten aus dieser E-Mail-Quelle vertrauen. Aber was passiert, wenn diese Quelle E-Mails von mehreren Domänen sendet und Sie die Spamfilterung für einige dieser Domänen überspringen möchten, aber nicht für andere? Sie können dazu nicht nur die LISTE der zulässigen IP-Adressen verwenden, aber Sie können die Liste der zulässigen IP-Adressen in Kombination mit einer Nachrichtenflussregel verwenden.

Beispielsweise sendet der Quell-E-Mail-Server 192.168.1.25 E-Mails von den Domänen contoso.com, fabrikam.com und tailspintoys.com, aber Sie möchten nur die Spamfilterung für Nachrichten von Absendern in fabrikam.com. Gehen Sie dazu wie folgt vor:

1. Fügen Sie 192.168.1.25 zur Liste der zulässigen IP-Adressen hinzu.

2. Konfigurieren Sie eine Nachrichtenflussregel mit den folgenden Einstellungen (mindestens):

   - Regelbedingung:  Wenden Sie diese Regel an, wenn sich die Absender-IP-Adresse in einem dieser Bereiche befindet oder exakt mit \>  \>  192.168.1.25 (derselben IP-Adresse oder adressbereich, die Sie der Liste der zulässigen IP-Adressen im vorherigen Schritt hinzugefügt \> haben) entspricht.

   - Regelaktion: **Ändern der Nachrichteneigenschaften** \> **Festlegen der SCL (Spam Confidence Level)** \> **0**.

   - Regelausnahme: **Die** \> **Absenderdomäne ist fabrikam.com** (nur die Domänen, die Sie überspringen \> möchten).

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>Szenarien, in denen Nachrichten aus Quellen in der Liste der zulässigen IP-Adressen weiterhin gefiltert werden

Nachrichten von einem E-Mail-Server in Der Liste der zulässigen IP-Adressen unterliegen in den folgenden Szenarien weiterhin der Spamfilterung:

- Eine IP-Adresse in Ihrer Liste der zulässigen IP-Adressen wird auch in einem lokalen, IP-basierten eingehenden Connector *in* jedem Mandanten in Microsoft 365 konfiguriert (nennen wir diesen Mandanten **A),** und Mandant A und der EOP-Server, der die Nachricht zuerst trifft, befinden sich *beide* in derselben Active Directory-Gesamtstruktur in den Microsoft-Rechenzentren. In diesem Szenario wird **IPV:CAL**  den [Antispamnachrichtenkopfzeilen](anti-spam-message-headers.md) der Nachricht hinzugefügt (was die Spamfilterung der Nachricht angibt), die Nachricht unterliegt jedoch weiterhin der Spamfilterung.

- Ihr Mandant, der die LISTE der zulässigen IP-Adressen enthält, und der EOP-Server, der die Nachricht zuerst trifft, befinden sich *in* verschiedenen Active Directory-Gesamtstrukturen in den Microsoft-Rechenzentren. In diesem Szenario wird **IPV:CAL**  nicht den Nachrichtenkopfzeilen hinzugefügt, sodass die Nachricht weiterhin der Spamfilterung unterliegt.

Wenn eines dieser Szenarien vor sich geht, können Sie eine Nachrichtenflussregel mit den folgenden Einstellungen (mindestens) erstellen, um sicherzustellen, dass Nachrichten von den problematischen IP-Adressen die Spamfilterung überspringen:

- Regelbedingung: Wenden Sie **diese Regel an,** wenn sich die Absender-IP-Adresse in einem dieser Bereiche befindet oder exakt entspricht \>  \>  \> (Ihre IP-Adresse oder -Adressen).

- Regelaktion: **Ändern Sie die Nachrichteneigenschaften** Festlegen der Spam Confidence Level \> **(SCL)** \> **Spamfilter umgehen.**

## <a name="new-to-microsoft-365"></a>Neu bei Microsoft 365?

****

![Das kurze Symbol für LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?** Entdecken Sie kostenlose Videokurse für **Microsoft 365-Administratoren** und IT-Profis, die Ihnen von LinkedIn Learning angeboten werden.
