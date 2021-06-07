---
title: Konfigurieren der Standardverbindungsfilterrichtlinie
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
description: Administratoren erfahren, wie Sie die Verbindungsfilterung in Exchange Online Protection (EOP) konfigurieren, um E-Mails von E-Mail-Servern zuzulassen oder zu blockieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 27c8cbbc70a4844e11bf85003215d2798a57a7ff
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/07/2021
ms.locfileid: "52792980"
---
# <a name="configure-connection-filtering"></a>Konfigurieren von Verbindungsfiltern

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)


Wenn Sie ein Microsoft 365 Kunde mit Postfächern in Exchange Online oder ein EOP-Kunde (Standalone Exchange Online Protection) ohne Exchange Online Postfächer sind, verwenden Sie die Verbindungsfilterung in EOP (insbesondere die Standardverbindungsfilterrichtlinie), um gute oder ungültige Quell-E-Mail-Server anhand ihrer IP-Adressen zu identifizieren. Die Hauptkomponenten der Standardverbindungsfilter-Richtlinie sind:

- **IP-Zulassungsliste:** Überspringen Sie die Spamfilterung für alle eingehenden Nachrichten von den Quell-E-Mail-Servern, die Sie anhand der IP-Adresse oder des IP-Adressbereichs angeben. Szenarien, in denen die Spamfilterung möglicherweise weiterhin für Nachrichten aus diesen Quellen auftritt, finden Sie unter den [Szenarien, in denen Nachrichten aus Quellen in der LISTE zugelassener IP-Adressen weiter](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) unten in diesem Artikel gefiltert werden. Weitere Informationen dazu, wie die LISTE zugelassener IP-Adressen in Ihre allgemeine Strategie für sichere Absender passt, finden Sie unter [Erstellen von Listen sicherer Absender in EOP.](create-safe-sender-lists-in-office-365.md)

- **IP-Sperrliste:** Blockieren aller eingehenden Nachrichten von den Quell-E-Mail-Servern, die Sie anhand der IP-Adresse oder des IP-Adressbereichs angeben. Die eingehenden Nachrichten werden abgelehnt, nicht als Spam gekennzeichnet, und es erfolgt keine zusätzliche Filterung. Weitere Informationen dazu, wie die LISTE blockierter IP-Adressen in Ihre gesamte Strategie für blockierte Absender passt, finden Sie unter [Erstellen von Listen blockierter Absender in EOP.](create-block-sender-lists-in-office-365.md)

- **Sichere Liste:** Die *sichere Liste* ist eine dynamische Zulassungsliste im Microsoft-Rechenzentrum, die keine Kundenkonfiguration erfordert. Microsoft identifiziert diese vertrauenswürdigen E-Mail-Quellen aus Abonnements für verschiedene Listen von Drittanbietern. Sie aktivieren oder deaktivieren die Verwendung der sicheren Liste. Sie können die Quell-E-Mail-Server in der sicheren Liste nicht konfigurieren. Die Spamfilterung wird bei eingehenden Nachrichten von den E-Mail-Servern in der sicheren Liste übersprungen.

In diesem Artikel wird beschrieben, wie Sie die Standardverbindungsfilterrichtlinie im Microsoft 365 Security Center oder in PowerShell konfigurieren (Exchange Online PowerShell für Microsoft 365 Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange Online Postfächer). Weitere Informationen dazu, wie EOP die Verbindungsfilterung verwendet, ist Teil der allgemeinen Antispameinstellungen Ihrer Organisation. Weitere Informationen finden Sie unter [Antispamschutz.](anti-spam-protection.md)

> [!NOTE]
> Die IP-Zulassungsliste, die sichere Liste und die BLOCKIERTE IP-Sperrliste sind ein Teil Ihrer Gesamtstrategie, um E-Mails in Ihrer Organisation zuzulassen oder zu blockieren. Weitere Informationen finden Sie unter [Erstellen von Listen sicherer Absender](create-safe-sender-lists-in-office-365.md) und Erstellen [blockierter Absenderlisten.](create-block-sender-lists-in-office-365.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security Center über <https://security.microsoft.com/>. Wechseln Sie direkt zur Seite **Antispamrichtlinien**, verwenden Sie <https://security.microsoft.com/antispam>.

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Sie müssen in **Exchange Online** Berechtigungen erhalten, bevor Sie die in diesem Artikel beschriebenen Schritte ausführen können:
  - Um die Standardverbindungsfilterrichtlinie zu ändern, müssen Sie Mitglied der Rollengruppen **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** sein.
  - Für den schreibgeschützten Zugriff auf die Standardverbindungsfilterrichtlinie müssen Sie Mitglied der Rollengruppe **"Globaler Leser"** oder **"Sicherheitsleseberechtigter"** sein.

  Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Hinweise**:

  - Durch Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).
  - Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.

- Um die Quell-IP-Adressen der E-Mail-Server (Absender) zu finden, die Sie zulassen oder blockieren möchten, können Sie das Headerfeld für die Verbindungs-IP **(CIP)** im Nachrichtenheader überprüfen. Informationen zum Anzeigen einer Nachrichtenkopfzeile in verschiedenen E-Mail-Clients finden Sie unter Anzeigen von [Internet-Nachrichtenkopfzeilen in Outlook.](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)

- Die IP-Zulassungsliste hat Vorrang vor der IP-Sperrliste (eine Adresse in beiden Listen wird nicht blockiert).

- Die IP-Zulassungsliste und die IP-Sperrliste unterstützen jeweils maximal 1273 Einträge, wobei ein Eintrag eine einzelne IP-Adresse, ein IP-Adressbereich oder eine CLASSless InterDomain Routing (CIDR)-IP ist.

## <a name="use-the-security-center-to-modify-the-default-connection-filter-policy"></a>Verwenden des Sicherheitscenters zum Ändern der Standardverbindungsfilterrichtlinie

1. Wechseln Sie im Security Center zum Abschnitt **E-Mail und Zusammenarbeit** \> **Richtlinien und Regeln** \> **Bedrohungsrichtlinien** \> **Richtlinien**\> **Antispam**.

2. Wählen Sie auf der Seite **"Antispamrichtlinien"** die **Verbindungsfilterrichtlinie (Standard)** aus der Liste aus, indem Sie auf den Namen der Richtlinie klicken.

3. Konfigurieren Sie im angezeigten Richtliniendetails-Flyout eine der folgenden Einstellungen:

   - **Description** section: Click **Edit name and description**. Geben Sie im angezeigten Flyout **"Name bearbeiten" und "Beschreibung"** optionalen beschreibenden Text in das **Feld Beschreibung** ein.

     Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

   - **Abschnitt "Verbindungsfilterung":** Klicken Sie auf **"Verbindungsfilterrichtlinie bearbeiten".** Konfigurieren Sie im angezeigten Flyout die folgenden Einstellungen:

     - **Nachrichten aus den folgenden IP-Adressen oder Adressbereich immer zulassen:** Dies ist die Liste zugelassener IP-Adressen. Klicken Sie in das Feld, geben Sie einen Wert ein, und drücken Sie die EINGABETASTE, oder wählen Sie den vollständigen Wert aus, der unterhalb des Felds angezeigt wird. Gültige Werte sind:
       - Single IP: For example, 192.168.1.1.
       - IP-Bereich: Beispiel: 192.168.0.1-192.168.0.254.
       - CIDR-IP: Beispiel: 192.168.0.1/25. Gültige Subnetzmaskenwerte sind /24 bis /32. Informationen zum Überspringen der Spamfilterung für /1 bis /23 finden Sie unter "Überspringen der [Spamfilterung für eine CIDR-IP außerhalb des verfügbaren Bereichsabschnitts](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) weiter unten in diesem Artikel".

       Wiederholen Sie diesen Schritt so oft wie nötig. Um einen vorhandenen Wert zu entfernen, klicken Sie auf das ![Symbol „Entfernen“](../../media/m365-cc-sc-remove-selection-icon.png) neben dem Wert.

     Um die IP-Adresse oder den Adressbereich hinzuzufügen, klicken Sie in das Feld, und geben **Sie "Hinzufügen"-Symbol** ![ ](../../media/ITPro-EAC-AddIcon.png) ein. Um einen Eintrag zu entfernen, wählen Sie den Eintrag in **der zulässigen IP-Adresse** aus, und klicken Sie dann auf **Entfernen** ![ ](../../media/scc-remove-icon.png) . Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

   - **Nachrichten aus den folgenden IP-Adressen oder Adressbereich immer blockieren:** Dies ist die IP-Sperrliste. Geben Sie eine einzelne IP-, IP-Bereichs- oder CIDR-IP in das Feld ein, wie zuvor in der Einstellung **"Nachrichten von den folgenden IP-Adressen oder Adressbereichseinstellungen immer zulassen"** beschrieben.

   - **Sichere Liste aktivieren:** Aktivieren oder deaktivieren Sie die Verwendung der sicheren Liste, um bekannte, gute Absender zu identifizieren, die die Spamfilterung überspringen. Aktivieren Sie das Kontrollkästchen, um die sichere Liste zu verwenden.

   Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

4. Zurück auf dem Flyout der Richtliniendetails klicken Sie auf **Schließen**.

## <a name="use-the-security-center-to-view-the-default-connection-filter-policy"></a>Verwenden des Sicherheitscenters zum Anzeigen der Standardverbindungsfilterrichtlinie

1. Wechseln Sie im Security Center zum Abschnitt **E-Mail und Zusammenarbeit** \> **Richtlinien und Regeln** \> **Bedrohungsrichtlinien** \> **Richtlinien**\> **Antispam**.

2. Auf der Seite **"Antispamrichtlinien"** werden die folgenden Eigenschaften in der Liste der Richtlinien angezeigt:

   - **Name:** Dieser Wert ist **die Verbindungsfilterrichtlinie (Standard)** für die Standardverbindungsfilterrichtlinie.
   - **Status:** Dieser Wert ist für die Standardverbindungsfilterrichtlinie **immer aktiviert.**
   - **Priorität:** Dieser Wert ist **der niedrigste** Wert für die Standardverbindungsfilterrichtlinie.
   - **Typ:** Dieser Wert ist für die Standardverbindungsfilterrichtlinie leer.

3. Wenn Sie die Standardverbindungsfilterrichtlinie auswählen, werden die Richtlinieneinstellungen in einem Flyout angezeigt.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a>Verwenden Exchange Online PowerShell oder der eigenständigen EOP PowerShell zum Ändern der Standardverbindungsfilterrichtlinie

Verwenden Sie die folgende Syntax:

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

**Hinweise**:

- Gültige WERTE für IP-Adressen oder Adressbereiche sind:
  - Single IP: For example, 192.168.1.1.
  - IP-Bereich: Beispiel: 192.168.0.1-192.168.0.254.
  - CIDR-IP: Beispiel: 192.168.0.1/25. Gültige Netzwerkformatwerte sind /24 bis /32.
- Verwenden Sie die folgende Syntax, um vorhandene Einträge mit den von Ihnen angegebenen Werten zu *überschreiben:* `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN`
- Verwenden Sie die folgende Syntax, um IP-Adressen oder Adressbereiche hinzuzufügen oder zu *entfernen,* ohne dass sich dies auf andere Einträge `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` auswirkt:
- Verwenden Sie den Wert, um die IP-Zulassungsliste oder die IP-Sperrliste zu `$null` leeren.

In diesem Beispiel werden die IP-Zulassungsliste und die IP-Sperrliste mit den angegebenen IP-Adressen und Adressbereichen konfiguriert.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

In diesem Beispiel werden die angegebenen IP-Adressen und Adressbereiche aus der Liste zugelassener IP-Adressen hinzugefügt und entfernt.

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-HostedConnectionFilterPolicy".](/powershell/module/exchange/set-hostedconnectionfilterpolicy)

## <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie die Standardverbindungsfilterrichtlinie erfolgreich geändert haben:

- Wechseln Sie im Security Center zu **E-Mail-& Richtlinien** für die Zusammenarbeit & Richtlinien für \> **Bedrohungsrichtlinien** für Regeln, indem Sie in der Liste die \>  \>  \>  \> **Verbindungsfilterrichtlinie (Standard)** auswählen, indem Sie auf den Namen der Richtlinie klicken und die Einstellungen überprüfen.

- Führen Sie in Exchange Online PowerShell oder der eigenständigen EOP PowerShell den folgenden Befehl aus, und überprüfen Sie die Einstellungen:

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- Senden Sie eine Testnachricht aus einem Eintrag in der Liste zugelassener IP-Adressen.

## <a name="additional-considerations-for-the-ip-allow-list"></a>Zusätzliche Überlegungen zur IP-Zulassungsliste

In den folgenden Abschnitten werden zusätzliche Elemente aufgeführt, die Sie beim Konfigurieren der LISTE zugelassener IP-Adressen kennen müssen.

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>Überspringen der Spamfilterung für eine CIDR-IP außerhalb des verfügbaren Bereichs

Wie weiter oben in diesem Artikel beschrieben, können Sie nur eine CIDR-IP mit der Netzwerkmaske /24 bis /32 in der IP-Zulassungsliste verwenden. Um die Spamfilterung für Nachrichten von Quell-E-Mail-Servern im Bereich /1 bis /23 zu überspringen, müssen Sie Exchange Nachrichtenflussregeln (auch als Transportregeln bezeichnet) verwenden. Es wird jedoch empfohlen, dies möglichst nicht zu tun, da die Nachrichten blockiert werden, wenn eine IP-Adresse im IP-Bereich /1 bis /23 CIDR in einer der proprietären Oder Drittanbieter-Sperrlisten von Microsoft angezeigt wird.

Da Sie nun die potenziellen Probleme vollständig kennen, können Sie eine Nachrichtenflussregel mit den folgenden Einstellungen erstellen (zumindest), um sicherzustellen, dass Nachrichten von diesen IP-Adressen die Spamfilterung überspringen:

- Regelbedingung: **Wenden Sie diese Regel an, wenn** sich die \>  \> **Absender-IP-Adresse in einem dieser Bereiche befindet oder genau übereinstimmt** \> (geben Sie Ihre CIDR-IP mit einer /1- bis /23-Netzwerkmaske ein).
- Regelaktion: **Ändern Sie die Nachrichteneigenschaften** Festlegen der Spam confidence level \> **(SCL)** Bypass Spam \> **filtering**.

Sie können die Regel überwachen, die Regel testen, die Regel während eines bestimmten Zeitraums und andere Auswahlen aktivieren. Wir empfehlen, die Regel über eine bestimmte Zeit zu testen, bevor Sie sie erzwingen. Weitere Informationen finden Sie unter [Verwalten von Nachrichtenflussregeln in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>Überspringen der Spamfilterung für selektive E-Mail-Domänen aus derselben Quelle

Normalerweise bedeutet das Hinzufügen einer IP-Adresse oder eines Adressbereichs zur IP-Zulassungsliste, dass Sie allen eingehenden Nachrichten aus dieser E-Mail-Quelle vertrauen. Aber was geschieht, wenn diese Quelle E-Mails von mehreren Domänen sendet und Sie die Spamfilterung für einige dieser Domänen überspringen möchten, aber nicht für andere? Sie können die IP-Zulassungsliste nicht allein verwenden, aber Sie können die IP-Zulassungsliste in Kombination mit einer Nachrichtenflussregel verwenden.

Beispielsweise sendet der Quell-E-Mail-Server 192.168.1.25 E-Mails von den Domänen contoso.com, fabrikam.com und tailspintoys.com, Sie möchten jedoch nur die Spamfilterung für Nachrichten von Absendern in fabrikam.com überspringen. Führen Sie dazu die folgenden Schritte aus:

1. Fügen Sie der LISTE zugelassener IP-Adressen 192.168.1.25 hinzu.

2. Konfigurieren Sie eine Nachrichtenflussregel mit den folgenden Einstellungen (mindestens):
   - Regelbedingung: **Wenden Sie diese Regel an, wenn** sich die \>  \> **ABSENDER-IP-Adresse in einem dieser Bereiche** befindet oder genau mit \> 192.168.1.25 übereinstimmt (die gleiche IP-Adresse oder derselbe Adressbereich, den Sie im vorherigen Schritt zur Liste zugelassener IP-Adressen hinzugefügt haben).
   - Regelaktion: **Ändern der Nachrichteneigenschaften** \> **Festlegen der Spam-Konfidenzstufe (Spam Confidence Level, SCL)** \> **0**.
   - Regelausnahme: **Die** \> **Absenderdomäne ist** \> fabrikam.com (nur die Domäne oder Domänen, die Sie die Spamfilterung überspringen möchten).

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>Szenarien, in denen Nachrichten aus Quellen in der LISTE zugelassener IP-Adressen weiterhin gefiltert werden

Nachrichten von einem E-Mail-Server in Ihrer IP-Zulassungsliste unterliegen in den folgenden Szenarien weiterhin der Spamfilterung:

- Eine IP-Adresse in Ihrer IP-Zulassungsliste wird auch in einem lokalen, IP-basierten eingehenden Connector in *jedem* Mandanten in Microsoft 365 konfiguriert (nennen wir diesen Mandanten A), **und** Mandant A und der EOP-Server, der zuerst auf die Nachricht trifft, befinden sich beide in *derselben* Active Directory-Gesamtstruktur in den Microsoft-Rechenzentren. In diesem Szenario *wird* **IPV:CAL** den [Antispam-Nachrichtenkopfzeilen](anti-spam-message-headers.md) der Nachricht hinzugefügt (was angibt, dass die Spamfilterung für die Nachricht umgangen wurde), aber die Nachricht unterliegt weiterhin der Spamfilterung.

- Ihr Mandant, der die IP-Zulassungsliste enthält, und der EOP-Server, der zuerst auf die Nachricht trifft, befinden sich beide in *verschiedenen* Active Directory-Gesamtstrukturen in den Microsoft-Rechenzentren. In diesem Szenario wird **IPV:CAL** *nicht* zu den Nachrichtenkopfzeilen hinzugefügt, sodass die Nachricht weiterhin der Spamfilterung unterliegt.

Wenn eines dieser Szenarien auftritt, können Sie eine Nachrichtenflussregel mit den folgenden Einstellungen erstellen (zumindest), um sicherzustellen, dass Nachrichten von den problematischen IP-Adressen die Spamfilterung überspringen:

- Regelbedingung: **Wenden Sie diese Regel an, wenn** sich die \>  \> **Absender-IP-Adresse in einem dieser Bereiche befindet oder genau übereinstimmt** \> (Ihre IP-Adresse oder Adressen).
- Regelaktion: **Ändern Sie die Nachrichteneigenschaften** Festlegen der Spam confidence level \> **(SCL)** Bypass Spam \> **filtering**.

## <a name="new-to-microsoft-365"></a>Neu bei Microsoft 365?

****

![Das kurze Symbol für LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?** Entdecken Sie kostenlose Videokurse für **Microsoft 365 Administratoren und IT-Spezialisten,** die Ihnen von LinkedIn Learning zur Verfügung gestellt werden.
