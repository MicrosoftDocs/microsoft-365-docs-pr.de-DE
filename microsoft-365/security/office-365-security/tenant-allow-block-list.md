---
title: Verwalten Der zulässigen und blockierten Mandanten in der Liste der zulässigen/blockierten Mandanten
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
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie Dies in der Liste der zulässigen/blockierten Mandanten im Sicherheitsportal konfigurieren.
ms.openlocfilehash: c789b09224d00f5bb41ae29d6d2a6efa64d23a8d
ms.sourcegitcommit: 495b66b77d6dbe6d69e5b06b304089e4e476e568
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799713"
---
# <a name="managing-allows-and-blocks-in-the-tenant-allowblock-list"></a>Verwalten von Zulässigen und Blöcken in der Liste der zulässigen/blockierten Mandanten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Die in diesem Artikel beschriebenen Features befinden sich in der Vorschau, können geändert werden und sind nicht in allen Organisationen verfügbar.

In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer sind Sie möglicherweise mit der EOP-Filterungs-Ansicht nicht einverstanden. Beispielsweise kann eine gute Nachricht als "schlecht" (ein falsch positives Ergebnis) oder eine ungültige Nachricht als "schlecht" (falsch negativ) markiert werden.

Mit der Liste der zulässigen/blockierten Mandanten im Security & Compliance Center können Sie die Microsoft 365-Filterungsverkn/-nkungen manuell außer Kraft setzen. Die Liste der zulässigen/blockierten Mandanten wird während des Nachrichtenflusses und zum Zeitpunkt der Klicks des Benutzers verwendet. Sie können URLs angeben, die in der Liste der zulässigen/blockierten Mandanten zulässig oder blockiert werden.

In diesem Thema wird beschrieben, wie Sie Einträge in der Liste der zulässigen/blockierten Mandanten im Security & Compliance Center oder in PowerShell konfigurieren (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange Online-Postfächer).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Verwenden Sie dies, um direkt zur Seite **"Mandanten-Allow/Block List"** zu <https://protection.office.com/tenantAllowBlockList> wechseln.

- Die verfügbaren #A0 werden weiter unten in diesem Artikel in der #A1 für den Abschnitt "Mandanten [zulassen/blockieren"](#url-syntax-for-the-tenant-allowblock-list) beschrieben.

- Die Liste der zulässigen/blockierten Mandanten lässt maximal 500 Einträge für URLs zu.

- Ein Eintrag sollte innerhalb von 15 Minuten aktiv sein.

- Blockeinträge haben Vorrang vor Zulässigen Einträgen.

- Standardmäßig laufen Einträge in der Liste der zulässigen/blockierten Mandanten nach 30 Tagen ab. Sie können ein Datum angeben oder festlegen, dass es nie abläuft.

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Security & Compliance Center Berechtigungen zugewiesen werden.
  - Zum Hinzufügen und Entfernen von Werten aus der Liste zulässiger/blockierter Mandanten müssen Sie Mitglied der Rollengruppe "Organisationsverwaltung" oder **"Sicherheitsadministrator"** sein. 
  - Für den schreibgeschützten Zugriff auf die Liste zulässiger/blockierter  Mandanten müssen Sie Mitglied der Rollengruppe "Globaler Leser" oder **"Sicherheitsleser"** sein.

  Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

  **Hinweise**:

  - Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a>Verwenden des Security & Compliance Center zum Erstellen von URL-Einträgen in der Liste der zulässigen/blockierten Mandanten

Weitere Informationen zur Syntax für #A0 finden Sie in der #A1 für den Abschnitt ["Mandanten-Zulassen/Sperrliste"](#url-syntax-for-the-tenant-allowblock-list) weiter unten in diesem Artikel.

1. Wechseln Sie im Security & Compliance  Center zu "Richtlinienrichtlinien-Mandanten-Allow/Block \>  \> **Lists".**

2. Überprüfen Sie **auf der** Seite "Mandanten-Zulassen/Sperrliste", ob die Registerkarte **"URLs"** ausgewählt ist, und klicken Sie dann auf "Hinzufügen". 

3. Konfigurieren Sie **im angezeigten** Flyout "Neue URLs hinzufügen" die folgenden Einstellungen:

   - **Fügen Sie URLs mit Platzhaltern hinzu:** Geben Sie eine URL pro Zeile ein, bis zu maximal 20.

   - **Blockieren/Zulassen:** Wählen Sie  aus, ob Sie die **angegebenen** URLs zulassen oder blockieren möchten.

   - **Läuft nie** ab: Gehen Sie wie folgt vor:

     - Stellen Sie sicher, dass die Einstellung deaktiviert ist (Umschalten aus), und verwenden Sie das Feld "Abläuft bei", um das Ablaufdatum ![ ](../../media/scc-toggle-off.png) für die Einträge anzugeben. 

     oder

     - Verschieben Sie den Umschalter nach rechts, um die Einträge so zu konfigurieren, dass sie nie ablaufen: ![Umschaltfläche ein](../../media/scc-toggle-on.png).

   - **Optionaler Hinweis:** Geben Sie beschreibenden Text für die Einträge ein.

4. Klicken Sie nach Abschluss des Abschlusses auf **"Hinzufügen".**

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a>Verwenden des Security & Compliance Center zum Anzeigen von Einträgen in der Liste der zulässigen/blockierten Mandanten

1. Wechseln Sie im Security & Compliance  Center zu "Richtlinienrichtlinien-Mandanten-Allow/Block \>  \> **Lists".**

2. Wählen Sie die **Registerkarte "URLs"** aus.

Klicken Sie auf die folgenden Spaltenüberschriften, um in aufsteigender oder absteigender Reihenfolge zu sortieren:

- **Wert**
- **Aktion:** **Blockieren oder** **Zulassen**.
- **Datum der letzten Aktualisierung**
- **Ablaufdatum**
- **Hinweis**

Klicken **Sie auf "Gruppieren",** um die Einträge nach **Aktion** (**Blockieren** oder **Zulassen)** oder Keine **zu gruppieren.**

Klicken **Sie auf "Suchen",** geben Sie einen Wert ganz oder teilweise ein, und drücken Sie dann die EINGABETASTE, um einen bestimmten Wert zu finden. Klicken Sie nach Abschluss des Abschlusses auf "Suche **löschen",** ![ um das Suchsymbol zu ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) löschen.

Klicken Sie **auf Filter**. Konfigurieren Sie **im angezeigten** Filterf flyout eine der folgenden Einstellungen:

- **Aktion:** Wählen Sie **"Zulassen",** **"Blockieren"** oder beides aus.

- **Nie ablaufen:** Auswählen aus: ![ Umschalten ](../../media/scc-toggle-off.png) aus oder ein: ![ Umschalten ein ](../../media/scc-toggle-on.png) .

- **Last updated**: Select a start date (**From**), an end date (**To**) or both.

- **Ablaufdatum:** Wählen Sie ein Startdatum (**Von**), ein Enddatum (**bis**) oder beides aus.

Klicken Sie nach Abschluss des Abschlusses auf **"Übernehmen".**

Klicken Sie auf **"Filter",** und klicken Sie im angezeigten **Flyout "Filter"** auf "Filter löschen", um vorhandene **Filter zu löschen.**

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a>Verwenden des Security & Compliance Center zum Ändern von Einträgen in der Liste der zulässigen/blockierten Mandanten

Sie können den URL-Wert selbst nicht ändern. Stattdessen müssen Sie den Eintrag löschen und neu erstellen.

1. Wechseln Sie im Security & Compliance  Center zu "Richtlinienrichtlinien-Mandanten-Allow/Block \>  \> **Lists".**

2. Wählen Sie die **Registerkarte "URLs"** aus.

3. Wählen Sie den Eintrag aus, den Sie ändern möchten, und klicken Sie dann auf **das** ![ Symbol "Bearbeiten". ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png)

4. Konfigurieren Sie im angezeigten Flyout die folgenden Einstellungen:

   - **Block/Allow**: Select **Allow** or **Block**.

   - **Läuft nie** ab: Gehen Sie wie folgt vor:

     - Stellen Sie sicher, dass die Einstellung deaktiviert ist (Umschalten aus), und verwenden Sie das Feld "Abläuft bei", um das ![ ](../../media/scc-toggle-off.png) Ablaufdatum für den Eintrag anzugeben. 

     oder

     - Verschieben Sie den Umschalter nach rechts, um den Eintrag so zu konfigurieren, dass er nie abläuft: ![Umschaltfläche ein](../../media/scc-toggle-on.png).

   - **Optionaler Hinweis:** Geben Sie einen beschreibenden Text für den Eintrag ein.

5. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a>Verwenden des Security & Compliance Center zum Entfernen von Einträgen aus der Liste der zulässigen/blockierten Mandanten

1. Wechseln Sie im Security & Compliance  Center zu "Richtlinienrichtlinien-Mandanten-Allow/Block \>  \> **Lists".**

2. Wählen Sie die **Registerkarte "URLs"** aus.

3. Wählen Sie den Eintrag aus, den Sie entfernen möchten, und klicken Sie dann auf **das** Symbol ![ "Löschen". ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png)

4. Klicken Sie im angezeigten Warnungsdialogfeld auf **"Löschen".**

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Verwenden von Exchange Online PowerShell oder der eigenständigen EOP PowerShell zum Konfigurieren der Liste zulässiger/blockierter Mandanten

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a>Verwenden von PowerShell zum Hinzufügen von Einträgen in der Liste der zulässigen/blockierten Mandanten

Verwenden Sie die folgende Syntax, um Einträge in der Liste der zulässigen/blockierten Mandanten hinzuzufügen:

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

In diesem Beispiel wird für contoso.com und alle Unterdomänen (z. B. contoso.com, www.contoso.com und xyz.abc.contoso.com) ein Urlblockeintrag hinzugefügt. Da wir die Parameter "ExpirationDate" oder "NoExpiration" nicht verwendet haben, läuft der Eintrag nach 30 Tagen ab.

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a>Verwenden von PowerShell zum Anzeigen von Einträgen in der Liste der zulässigen/blockierten Mandanten

Verwenden Sie die folgende Syntax, um Einträge in der Liste der zulässigen/blockierten Mandanten anzeigen zu können:

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

In diesem Beispiel werden alle blockierten URLs zurückgegeben.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a>Verwenden von PowerShell zum Ändern von Einträgen in der Liste der zulässigen/blockierten Mandanten

Sie können den URL-Wert selbst nicht ändern. Stattdessen müssen Sie den Eintrag löschen und neu erstellen.

Verwenden Sie die folgende Syntax, um Einträge in der Liste der zulässigen/blockierten Mandanten zu ändern:

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

In diesem Beispiel wird das Ablaufdatum des angegebenen Eintrags geändert.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a>Verwenden von PowerShell zum Entfernen von Einträgen aus der Liste der zulässigen/blockierten Mandanten

Verwenden Sie die folgende Syntax, um Einträge aus der Liste der zulässigen/blockierten Mandanten zu entfernen:

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

In diesem Beispiel wird der angegebene URL-Eintrag aus der Liste der zulässigen/blockierten Mandanten entfernt.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>#A0 für die Liste der zulässigen/blockierten Mandanten

- IP4v- und IPv6-Adressen sind zulässig, TCP/UDP-Ports jedoch nicht.

- Dateinamenerweiterungen sind nicht zulässig (z. B. test.pdf).

- Unicode wird nicht unterstützt, Punycode jedoch.

- Hostnamen sind zulässig, wenn alle folgenden Anweisungen wahr sind:

  - Der Hostname enthält einen Zeitraum.
  - Links vom Zeitraum befindet sich mindestens ein Zeichen.
  - Rechts neben dem Zeitraum befinden sich mindestens zwei Zeichen.

  Beispielsweise ist `t.co` dies zulässig oder `.com` nicht `contoso.` zulässig.

- Unterpfade werden nicht impliziert.

  Enthält z. `contoso.com` B. nicht `contoso.com/a` .

- Platzhalter (*) sind in den folgenden Szenarien zulässig:

  - Auf einen linken Platzhalter muss ein Zeitraum folgen, um eine Unterdomäne anzugeben.

    Ist z. `*.contoso.com` B. zulässig; `*contoso.com` ist nicht zulässig.

  - Ein rechter Platzhalter muss einem Schrägstrich (/) folgen, um einen Pfad anzugeben.

    Beispielsweise ist `contoso.com/*` dies zulässig oder `contoso.com*` nicht `contoso.com/ab*` zulässig.

  - Alle Unterpfade werden nicht durch einen rechten Platzhalter impliziert.

    Enthält z. `contoso.com/*` B. nicht `contoso.com/a` .

  - `*.com*` ungültig ist (keine auflösbare Domäne, und der rechte Platzhalter folgt keinem Schrägstrich).

  - Platzhalter sind in IP-Adressen nicht zulässig.

- Das Tildezeichen (~) ist in den folgenden Szenarien verfügbar:

  - Eine linke Tilde impliziert eine Domäne und alle Unterdomänen.

    Beispielsweise enthält `~contoso.com` `contoso.com` und `*.contoso.com` .

- BEI URL-Einträgen, die Protokolle (z. B. , oder ) enthalten, kann ein Fehler angezeigt werden, da die Urleinträge `http://` `https://` für alle Protokolle `ftp://` gelten.

- Ein Benutzername oder Kennwort wird nicht unterstützt oder ist nicht erforderlich.

- Anführungszeichen (' oder ") sind ungültige Zeichen.

- Eine URL sollte nach Möglichkeit alle Umleitungen enthalten.

### <a name="url-entry-scenarios"></a>Szenarien für die EINGABE VON URLs

Gültige URL-Einträge und deren Ergebnisse werden in den folgenden Abschnitten beschrieben.

#### <a name="scenario-no-wildcards"></a>Szenario: Keine Platzhalter

**Eintrag:**`contoso.com`

- **Übereinstimmung zulassen:** contoso.com

- **Nicht übereinstimmend zulassen:**

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **Übereinstimmung blockieren:**

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **Block nicht übereinstimmend:** abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>Szenario: Linker Platzhalter (Unterdomäne)

**Eintrag:**`*.contoso.com`

- **Übereinstimmung zulassen** und **Übereinstimmung blockieren:**

  - www.contoso.com
  - xyz.abc.contoso.com

- **Nicht übereinstimmend zulassen und** **Block nicht übereinstimmen:**

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-at-top-of-path"></a>Szenario: Rechter Platzhalter oben im Pfad

**Eintrag:**`contoso.com/a/*`

- **Übereinstimmung zulassen** und **Übereinstimmung blockieren:**

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso.com/a/?q=joe@t.com

- **Nicht übereinstimmend zulassen und** **Block nicht übereinstimmen:**

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

#### <a name="scenario-left-tilde"></a>Szenario: Left tilde

**Eintrag:**`~contoso.com`

- **Übereinstimmung zulassen** und **Übereinstimmung blockieren:**

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **Nicht übereinstimmend zulassen und** **Block nicht übereinstimmen:**

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>Szenario: Rechtes Platzhaltersuffix

**Eintrag:**`contoso.com/*`

- **Übereinstimmung zulassen** und **Übereinstimmung blockieren:**

  - contoso.com/?q=whatever@fabrikam.com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **Nicht übereinstimmend zulassen und** **Block nicht übereinstimmen:** contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>Szenario: Linke Platzhalterunterdomäne und rechtes Platzhaltersuffix

**Eintrag:**`*.contoso.com/*`

- **Übereinstimmung zulassen** und **Übereinstimmung blockieren:**

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **Nicht übereinstimmend zulassen und** **Block nicht übereinstimmen:** contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>Szenario: Linke und rechte Tilde

**Eintrag:**`~contoso.com~`

- **Übereinstimmung zulassen** und **Übereinstimmung blockieren:**

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **Nicht übereinstimmend zulassen und** **Block nicht übereinstimmen:**

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>Szenario: IP-Adresse

**Eintrag:**`1.2.3.4`

- **Übereinstimmung zulassen** und **Blockierung:** 1.2.3.4

- **Nicht übereinstimmend zulassen und** **Block nicht übereinstimmen:**

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>IP-Adresse mit rechtem Platzhalter

**Eintrag:**`1.2.3.4/*`

- **Übereinstimmung zulassen** und **Übereinstimmung blockieren:**

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>Beispiele für ungültige Einträge

Die folgenden Einträge sind ungültig:

- **Fehlende oder ungültige Domänenwerte:**

  - contoso
  - \*.contoso.\*
  - \*.com
  - \*.pdf

- **Platzhalter für Text oder ohne Leerzeichen:**

  - \*contoso.com
  - contoso.com\*
  - \*1.2.3.4
  - 1.2.3.4\*
  - contoso.com/a\*
  - contoso.com/ab\*

- **IP-Adressen mit Ports:**

  - contoso.com:443
  - abc.contoso.com:25

- **Nicht beschreibende Platzhalter:**

  - \*
  - \*.\*

- **Mittlere Platzhalter:**

  - conto \* so.com
  - conto~so.com

- **Doppelte Platzhalter**

  - contoso.com/\*\*
  - contoso.com/\*/\*
