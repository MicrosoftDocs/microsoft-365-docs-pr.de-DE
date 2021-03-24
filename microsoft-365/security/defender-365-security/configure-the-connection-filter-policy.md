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
description: Administratoren erfahren, wie Sie die Verbindungsfilterung in Exchange Online Protection (EOP) konfigurieren, um E-Mails von E-Mail-Servern zu erlauben oder zu blockieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2b940aadb4ff5f2c4676ac2411ea3e95a25c7855
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065360"
---
# <a name="configure-connection-filtering"></a>Konfigurieren von Verbindungsfiltern

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)


Wenn Sie ein Microsoft 365-Kunde mit Postfächern in Exchange Online oder ein eigenständiger Exchange Online Protection (EOP)-Kunde ohne Exchange Online-Postfächer sind, verwenden Sie die Verbindungsfilterung in EOP (insbesondere die Standardverbindungsfilterrichtlinie), um gute oder ungültige Quell-E-Mail-Server nach ihren IP-Adressen zu identifizieren. Die Hauptkomponenten der Standardverbindungsfilter-Richtlinie sind:

- **IP-Zulässige Liste**: Überspringen Sie die Spamfilterung für alle eingehenden Nachrichten von den Quell-E-Mail-Servern, die Sie nach IP-Adresse oder IP-Adressbereich angeben. Szenarien, in denen die Spamfilterung für Nachrichten aus diesen Quellen weiterhin auftreten kann, finden Sie im Abschnitt Szenarien, in denen Nachrichten aus Quellen in der [Liste](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) der zulässigen IP-Adressen weiter unten in diesem Artikel gefiltert werden. Weitere Informationen dazu, wie die Liste der zulässigen IP-Adressen in Ihre Strategie für sichere Absender passen sollte, finden Sie unter [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).

- **IP-Sperrliste**: Alle eingehenden Nachrichten von den Quell-E-Mail-Servern blockieren, die Sie nach IP-Adresse oder IP-Adressbereich angeben. Die eingehenden Nachrichten werden zurückgewiesen, nicht als Spam gekennzeichnet, und es wird keine zusätzliche Filterung angezeigt. Weitere Informationen dazu, wie die IP-Sperrliste in Ihre Strategie für blockierte Absender passen sollte, finden Sie unter [Create block sender lists in EOP](create-block-sender-lists-in-office-365.md).

- **Sichere Liste:** Die *Liste sicherer* Daten ist eine dynamische Liste zulässiger Daten im Microsoft-Rechenzentrum, für die keine Kundenkonfiguration erforderlich ist. Microsoft identifiziert diese vertrauenswürdigen E-Mail-Quellen aus Abonnements für verschiedene Drittanbieterlisten. Sie aktivieren oder deaktivieren die Verwendung der sicheren Liste. Sie können die Quell-E-Mail-Server in der Liste sicherer Adressen nicht konfigurieren. Die Spamfilterung wird auf eingehenden Nachrichten von den E-Mail-Servern in der Sicheren Liste übersprungen.

In diesem Thema wird beschrieben, wie Sie die Standardverbindungsfilterrichtlinie im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange &) konfigurieren. Weitere Informationen zur Verwendung der Verbindungsfilterung durch EOP in Ihrer Organisation finden Sie unter [Antispamschutz](anti-spam-protection.md).

> [!NOTE]
> Die Liste der zulässigen IP-Adressen, die Liste der sicheren Adressen und die Liste der blockierten IP-Adressen sind Ein Teil Ihrer Gesamtstrategie zum Zulassen oder Blockieren von E-Mails in Ihrer Organisation. Weitere Informationen finden Sie unter [Create safe sender lists](create-safe-sender-lists-in-office-365.md) und Create blocked sender [lists](create-block-sender-lists-in-office-365.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Um direkt zur Seite **Antispameinstellungen** zu wechseln, verwenden Sie <https://protection.office.com/antispam>.

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Sie müssen in **Exchange Online** Berechtigungen erhalten, bevor Sie die in diesem Artikel beschriebenen Schritte ausführen können:
  - Zum Ändern der Standardverbindungsfilterrichtlinie müssen Sie Mitglied der Rollengruppen Organisationsverwaltung **oder** **Sicherheitsadministrator** sein.
  - Für den schreibgeschützten Zugriff auf die Standardverbindungsfilterrichtlinie müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Sicherheitsleser"** sein.

  Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Hinweise**:

  - Durch Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).
  - Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.

- Um die Quell-IP-Adressen der E-Mail-Server (Absender) zu finden, die Sie zulassen oder blockieren möchten, können Sie das Verbindungs-IP - Headerfeld (**CIP**) im Nachrichtenkopf überprüfen. Informationen zum Anzeigen eines Nachrichtenkopfs in verschiedenen E-Mail-Clients finden Sie unter [Anzeigen von Internetnachrichtenkopfzeilen in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).

- Die Liste der zulässigen IP-Adressen hat Vorrang vor der IP-Sperrliste (eine Adresse in beiden Listen wird nicht blockiert).

- Die IP-Zulässige Liste und die IP-Sperrliste unterstützen jeweils maximal 1273 Einträge, wobei es sich bei einem Eintrag um eine einzelne IP-Adresse, einen IP-Adressbereich oder eine CIDR-IP (Classless InterDomain Routing) handelt.

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a>Verwenden des Security & Compliance Center zum Ändern der Standardverbindungsfilterrichtlinie

1. Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **Antispam**.

2. Erweitern Sie auf der Seite **Antispameinstellungen** die **Verbindungsfilterrichtlinie,** indem Sie auf Erweitern (Symbol) klicken, und klicken Sie dann ![ ](../../media/scc-expand-icon.png) auf Richtlinie **bearbeiten**.

3. Konfigurieren Sie **im angezeigten** Standardf flyout eine der folgenden Einstellungen:

   - **Beschreibung**: Geben Sie optionalen beschreibenden Text ein.

   - **LISTE der zulässigen IP-Adressen**: Klicken Sie auf **Bearbeiten**. Geben Sie **im angezeigten #A0** eine #A1 im Feld **Adresse** oder Adressbereich mit der folgenden Syntax ein:

     - Einzelne IP: Beispiel: 192.168.1.1.

     - IP-Bereich: Beispiel: 192.168.0.1-192.168.0.254.

     - CIDR-IP: Beispiel: 192.168.0.1/25. Gültige Netzwerkmaskenwerte sind /24 bis /32. Informationen zum Überspringen der Spamfilterung für CIDR-IP-Maskenwerte /1 bis /23 finden Sie im Abschnitt Spamfilterung für eine [CIDR-IP](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) außerhalb des verfügbaren Bereichs weiter unten in diesem Artikel.

     Klicken Sie zum Hinzufügen der IP-Adresse oder des Adressbereichs auf **HinzufügenSymbol** ![ ](../../media/ITPro-EAC-AddIcon.png) . Um einen Eintrag zu entfernen, wählen Sie den Eintrag unter **Zulässige IP-Adresse aus,** und klicken Sie dann **auf Entfernen** ![ ](../../media/scc-remove-icon.png) . Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

   - **IP-Sperrliste**: Klicken Sie auf **Bearbeiten**. Geben Sie im angezeigten **IP-Sperrlisten-Flyout** eine einzelne IP-, IP-Bereich- oder CIDR-IP in das Feld **Adresse** oder Adressbereich ein, wie zuvor in der Einstellung **IP Allow List** beschrieben.

     Klicken Sie zum Hinzufügen der IP-Adresse oder des Adressbereichs auf **HinzufügenSymbol** ![ ](../../media/ITPro-EAC-AddIcon.png) . Um einen Eintrag zu entfernen, wählen Sie den Eintrag unter **Blockierte IP-Adresse aus,** und klicken Sie dann **auf Entfernen** ![ ](../../media/scc-remove-icon.png) . Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

   - **Sichere Liste aktivieren:** Aktivieren oder deaktivieren Sie die Verwendung der sicheren Liste, um bekannte, gute Absender zu identifizieren, die die Spamfilterung überspringen.

4. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a>Verwenden des Security & Compliance Center zum Anzeigen der Standardverbindungsfilterrichtlinie

1. Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **Antispam**.

2. Klicken Sie auf der Seite **Antispameinstellungen** auf die Dropdownliste neben der Standardrichtlinie namens **Verbindungsfilterrichtlinie**.

3. Die Richtlinieneinstellungen werden in der Dropdownliste angezeigt, die geöffnet wird.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a>Verwenden von Exchange Online PowerShell oder eigenständiger EOP PowerShell zum Ändern der Standardverbindungsfilterrichtlinie

Verwenden Sie die folgende Syntax:

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

**Hinweise**:

- Gültige WERTE für IP-Adressen oder Adressbereich sind:

  - Einzelne IP: Beispiel: 192.168.1.1.

  - IP-Bereich: Beispiel: 192.168.0.1-192.168.0.254.

  - CIDR-IP: Beispiel: 192.168.0.1/25. Gültige Netzwerkmaskenwerte sind /24 bis /32.

- Verwenden *Sie die* folgende Syntax, um vorhandene Einträge mit den angegebenen Werten zu überschreiben: `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` .

- Verwenden *Sie die folgende* Syntax, um #A0 oder Adressbereiche hinzuzufügen oder zu entfernen, ohne sich auf andere vorhandene Einträge zu beeinträchtigen: `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` .

- Verwenden Sie den Wert, um die Liste der zulässigen IP-Adressen oder die Sperrliste für IP zu `$null` leeren.

In diesem Beispiel werden die Liste der zulässigen IP-Adressen und die SPERRLISTE mit den angegebenen IP-Adressen und Adressbereichen konfiguriert.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

In diesem Beispiel werden die angegebenen IP-Adressen und Adressbereiche aus der LISTE der zulässigen IP-Adressen hinzugefügt und entfernt.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-HostedConnectionFilterPolicy](/powershell/module/exchange/set-hostedconnectionfilterpolicy).

## <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Gehen Sie wie folgt vor, um zu überprüfen, ob Sie die Standardverbindungsfilterrichtlinie erfolgreich geändert haben:

- Wechseln Sie im Security & Compliance  Center zu Richtlinie für die Bedrohungsverwaltung Antispam klicken Sie auf das Dropdown neben Verbindungsfilterrichtlinie \>  \>  \> **(immer EIN),** und überprüfen Sie die Einstellungen.

- Führen Sie in Exchange Online PowerShell oder der eigenständigen EOP PowerShell den folgenden Befehl aus, und überprüfen Sie die Einstellungen:

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- Senden Sie eine Testnachricht von einem Eintrag in der Liste der zulässigen IP-Adressen.

## <a name="additional-considerations-for-the-ip-allow-list"></a>Zusätzliche Überlegungen zur Liste der zulässigen IP-Adressen

In den folgenden Abschnitten werden weitere Elemente aufgeführt, die Sie beim Konfigurieren der LISTE der zulässigen IP-Adressen kennen müssen.

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>Überspringen der Spamfilterung für eine CIDR-IP außerhalb des verfügbaren Bereichs

Wie weiter oben in diesem Artikel beschrieben, können Sie nur eine CIDR-IP mit der Netzwerkmaske /24 bis /32 in der Liste der zulässigen IP-Adressen verwenden. Zum Überspringen der Spamfilterung für Nachrichten von Quell-E-Mail-Servern im Bereich /1 bis /23 müssen Sie Exchange-Nachrichtenflussregeln (auch transport rules) verwenden. Es wird jedoch empfohlen, dies nach Möglichkeit nicht zu tun, da die Nachrichten blockiert werden, wenn eine IP-Adresse im IP-Bereich /1 bis /23 cidr in einer der proprietären oder Drittanbieterblocklisten von Microsoft angezeigt wird.

Nachdem Sie sich der potenziellen Probleme bewusst sind, können Sie eine Nachrichtenflussregel mit den folgenden Einstellungen (mindestens) erstellen, um sicherzustellen, dass Nachrichten von diesen IP-Adressen die Spamfilterung überspringen:

- Regelbedingung:  Wenden Sie diese Regel an, wenn sich die Absender-IP-Adresse in einem dieser Bereiche befindet oder genau mit der Regel entspricht (geben Sie Ihre CIDR-IP mit einer \>  \>  \> Netzwerkmaske von /1 bis /23 ein).

- Regelaktion: **Ändern der Nachrichteneigenschaften** \> **Festlegen der Spamsicherheitsstufe (Spam Confidence Level, SCL)** \> **Spamfilter umgehen**.

Sie können die Regel überwachen, die Regel testen, die Regel während eines bestimmten Zeitraums und andere Auswahlen aktivieren. Wir empfehlen, die Regel über eine bestimmte Zeit zu testen, bevor Sie sie erzwingen. Weitere Informationen finden Sie unter [Verwalten von Nachrichtenflussregeln in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>Überspringen der Spamfilterung für ausgewählte E-Mail-Domänen aus derselben Quelle

In der Regel bedeutet das Hinzufügen einer IP-Adresse oder eines Adressbereichs zur LISTE der zulässigen IP-Adressen, dass Sie allen eingehenden Nachrichten aus dieser E-Mail-Quelle vertrauen. Was aber, wenn diese Quelle E-Mails von mehreren Domänen sendet und Sie die Spamfilterung für einige dieser Domänen überspringen möchten, aber nicht für andere? Sie können dazu nicht nur die LISTE der zulässigen IP-Adressen verwenden, aber Sie können die Liste der zulässigen IP-Adressen in Kombination mit einer Nachrichtenflussregel verwenden.

Beispielsweise sendet der Quell-E-Mail-Server 192.168.1.25 E-Mails von den Domänen contoso.com, fabrikam.com und tailspintoys.com, sie möchten jedoch nur die Spamfilterung für Nachrichten von Absendern in fabrikam.com. Gehen Sie dazu wie folgt vor:

1. Fügen Sie 192.168.1.25 zur Liste der zulässigen IP-Adressen hinzu.

2. Konfigurieren Sie eine Nachrichtenflussregel mit den folgenden Einstellungen (mindestens):

   - Regelbedingung:  Wenden Sie diese Regel an, wenn sich die Absender-IP-Adresse in einem dieser Bereiche befindet oder exakt \>  \>  \> mit 192.168.1.25 (derselben IP-Adresse oder demselben Adressbereich, die Sie im vorherigen Schritt zur Liste der zulässigen IP-Adressen hinzugefügt haben) entspricht.

   - Regelaktion: **Ändern der Nachrichteneigenschaften** Festlegen der Spamsicherheitsstufe \> **(Spam Confidence Level, SCL)** \> **0**.

   - Regelausnahme: **Die Absenderdomäne** ist fabrikam.com (nur die Domäne oder Domänen, die Sie die \>  \> Spamfilterung überspringen möchten).

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>Szenarien, in denen Nachrichten aus Quellen in der Liste der zulässigen IP-Adressen weiterhin gefiltert werden

Nachrichten von einem E-Mail-Server in Ihrer IP-Zulässigen Liste unterliegen in den folgenden Szenarien weiterhin der Spamfilterung:

- Eine IP-Adresse in Ihrer IP-Zulassen-Liste ist auch in einem lokalen, IP-basierten eingehenden Connector *in* einem beliebigen Mandanten in Microsoft 365 konfiguriert (nennen wir diesen Mandanten **A),** und Mandant A und der EOP-Server, auf dem die Nachricht zuerst angezeigt wird, befinden sich in den Microsoft-Rechenzentren in derselben *Active* Directory-Gesamtstruktur. In diesem Szenario wird **IPV:CAL**  den [Antispamnachrichtenkopfzeilen](anti-spam-message-headers.md) der Nachricht hinzugefügt (was die Spamfilterung angibt), die Nachricht unterliegt jedoch weiterhin der Spamfilterung.

- Ihr Mandant, der die LISTE der zulässigen IP-Adressen enthält, und der EOP-Server, auf dem die Nachricht zuerst angezeigt wird, befinden sich *in* verschiedenen Active Directory-Gesamtstrukturen in den Microsoft-Rechenzentren. In diesem Szenario wird **IPV:CAL**  nicht den Nachrichtenkopfzeilen hinzugefügt, sodass die Nachricht weiterhin der Spamfilterung unterliegt.

Bei einem dieser Szenarien können Sie eine Nachrichtenflussregel mit den folgenden Einstellungen (mindestens) erstellen, um sicherzustellen, dass Nachrichten von problematischen IP-Adressen die Spamfilterung überspringen:

- Regelbedingung: Wenden Sie **diese Regel an,** wenn sich die Absender-IP-Adresse in einem dieser Bereiche befindet oder genau mit \>  \>  \> der Regel (Ihre IP-Adresse oder -Adressen) entspricht.

- Regelaktion: **Ändern der Nachrichteneigenschaften** \> **Festlegen der Spamsicherheitsstufe (Spam Confidence Level, SCL)** \> **Spamfilter umgehen**.

## <a name="new-to-microsoft-365"></a>Neu bei Microsoft 365?

****

![Das kurze Symbol für LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New in Microsoft 365?** Entdecken Sie kostenlose Videokurse für **Microsoft 365-Administratoren** und IT-Profis, die Ihnen von LinkedIn Learning angeboten werden.