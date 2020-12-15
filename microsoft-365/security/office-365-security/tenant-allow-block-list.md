---
title: Verwalten Ihrer zulässigen und blockierten URLs in der Liste "Mandanten zulassen/blockieren"
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
description: Administratoren können erfahren, wie Sie URL-Einträge in der Liste Mandanten-Allow/Block im Security & Compliance Center konfigurieren.
ms.openlocfilehash: f60e2f29bf9b880e9d2247fa59554300ae348a03
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683211"
---
# <a name="manage-urls-in-the-tenant-allowblock-list"></a>Verwalten von URLs in der Zulassungs-/Sperrliste des Mandanten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Die in diesem Artikel beschriebenen Funktionen befinden sich in der Vorschau, können Änderungen unterliegen und sind nicht in allen Organisationen verfügbar.

In Microsoft 365-Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer können Sie mit dem EoP-Filter Urteil nicht einverstanden sein. Beispielsweise kann eine gute Nachricht als "schlecht" markiert werden (ein falsch positives Ergebnis), oder es ist möglicherweise eine ungültige Meldung zulässig (ein falsches negativ).

In der Liste Mandanten-Allow/Block im Security & Compliance Center haben Sie die Möglichkeit, die Microsoft 365-Filter Urteile manuell außer Kraft zu setzen. Die Mandanten-Zulassungs-und Sperrliste wird während des e-Mail-Flusses und zum Zeitpunkt der Benutzerklicks verwendet. In der Liste Mandanten-Allow/Block können Sie URLs angeben, die zugelassen oder blockiert werden sollen.

In diesem Thema wird beschrieben, wie Sie Einträge in der Liste "Allow/Block" des Mandanten im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EoP PowerShell für Organisationen ohne Exchange Online Postfächer) konfigurieren.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Wenn Sie direkt zur Seite **Mandanten-Zulassungs-und Sperrliste** wechseln möchten, verwenden Sie <https://protection.office.com/tenantAllowBlockList> .

- Die verfügbaren URL-Werte werden in der [URL-Syntax für den Abschnitt Mandanten-Zulassungs-und Sperrliste](#url-syntax-for-the-tenant-allowblock-list) weiter unten in diesem Artikel beschrieben.

- Die Liste Mandanten Allow/Block erlaubt maximal 500 Einträge für URLs.

- Ein Eintrag sollte innerhalb von 15 Minuten aktiv sein.

- Block Einträge haben Vorrang vor Zulassungs Einträgen.

- Standardmäßig laufen Einträge in der Liste Mandanten-Allow/Block nach 30 Tagen ab. Sie können ein Datum angeben oder festlegen, dass es nie abläuft.

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Security & Compliance Center Berechtigungen zugewiesen werden.
  - Sie müssen Mitglied der Rollengruppen " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " sein, um Werte aus der Liste "Allow/Block" für Mandanten hinzuzufügen und daraus zu entfernen.
  - Für den schreibgeschützten Zugriff auf die Liste der Mandanten zulassen/blockieren müssen Sie ein Mitglied der Rollengruppen " **globaler Leser** " oder " **Sicherheits Leser** " sein.

  Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

  **Hinweise**:

  - Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.

## <a name="use-the-security--compliance-center-to-create-url-entries-in-the-tenant-allowblock-list"></a>Verwenden Sie das Security & Compliance Center, um URL-Einträge in der Liste Mandanten-Allow/Block zu erstellen.

Ausführliche Informationen zur Syntax für URL-Einträge finden Sie in der [URL-Syntax für den Abschnitt Allow/Block List für Mandanten](#url-syntax-for-the-tenant-allowblock-list) weiter unten in diesem Artikel.

1. Wechseln Sie im Security & Compliance Center zu **Bedrohungs Verwaltungs** \> **Richtlinie** \> **Mandanten-Zulassungs-/Sperrlisten**.

2. Überprüfen Sie auf der Seite **Mandantenliste zulassen/blockieren** , dass die Registerkarte **URLs** ausgewählt ist, und klicken Sie dann auf **Hinzufügen** .

3. Konfigurieren Sie im Flyout **neue URLs hinzufügen** , das angezeigt wird, die folgenden Einstellungen:

   - **URLs mit Platzhaltern hinzufügen**: Geben Sie eine URL pro Reihe bis maximal 20 ein.

   - **Block/Allow**: Wählen Sie aus, ob die angegebenen URLs **zugelassen** oder **blockiert** werden sollen.

   - **Nie ablaufen**: führen Sie einen der folgenden Schritte aus:

     - Stellen Sie sicher, dass die Einstellung deaktiviert ist (deaktivieren ![ ](../../media/scc-toggle-off.png) ), und verwenden Sie das Feld **expires on** , um das Ablaufdatum für die Einträge anzugeben.

     oder

     - Bewegen Sie die Umschaltfläche nach rechts, um die Einträge so zu konfigurieren, dass Sie nie ablaufen: ![Umschaltfläche ein](../../media/scc-toggle-on.png).

   - **Optional Hinweis**: Geben Sie einen beschreibenden Text für die Einträge ein.

4. Wenn Sie fertig sind, klicken Sie auf **Hinzufügen**.

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a>Verwenden Sie das Security & Compliance Center, um Einträge in der Liste Mandanten-Allow/Block anzuzeigen.

1. Wechseln Sie im Security & Compliance Center zu **Bedrohungs Verwaltungs** \> **Richtlinie** \> **Mandanten-Zulassungs-/Sperrlisten**.

2. Wählen Sie die Registerkarte **URLs** aus.

Klicken Sie auf die folgenden Spaltenüberschriften, um Sie in aufsteigender oder absteigender Reihenfolge zu sortieren:

- **Wert**
- **Aktion**: **blockieren** oder **zulassen**.
- **Datum der letzten Aktualisierung**
- **Ablaufdatum**
- **Hinweis**

Klicken Sie auf **Gruppieren** , um die Einträge nach **Aktion** (**blockieren** oder **zulassen**) oder **ohne** zu gruppieren.

Klicken Sie auf **Suchen**, geben Sie einen Wert ganz oder teilweise ein, und drücken Sie dann die EINGABETASTE, um einen bestimmten Wert zu suchen. Wenn Sie fertig sind, klicken Sie auf **Such** ![ Symbol Löschen ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .

Klicken Sie auf **Filter**. Konfigurieren Sie im angezeigten **Filter** Flyout die folgenden Einstellungen:

- **Aktion**: Wählen Sie **zulassen**, **blockieren** oder beides aus.

- **Nie ablaufen**: Auswahl aus: schaltet ![ ab ](../../media/scc-toggle-off.png) oder ein: schaltet ![ ein ](../../media/scc-toggle-on.png) .

- **Letzte Aktualisierung**: Wählen Sie ein Startdatum (von), ein Enddatum (**an**) oder beides **aus**.

- **Ablaufdatum**: Wählen Sie ein Startdatum (von), ein Enddatum (**an**) oder beides **aus**.

Wenn Sie fertig sind, klicken Sie auf über **nehmen**.

Wenn Sie vorhandene Filter löschen möchten, klicken Sie auf **Filter**, und klicken Sie im daraufhin angezeigten **Filter** Flyout auf Filter **Löschen**.

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a>Verwenden des Security & Compliance Center zum Ändern von Einträgen in der Liste "Mandanten zulassen/blockieren"

Sie können den URL-Wert selbst nicht ändern. Stattdessen müssen Sie den Eintrag löschen und neu erstellen.

1. Wechseln Sie im Security & Compliance Center zu **Bedrohungs Verwaltungs** \> **Richtlinie** \> **Mandanten-Zulassungs-/Sperrlisten**.

2. Wählen Sie die Registerkarte **URLs** aus.

3. Wählen Sie den Eintrag aus, den Sie ändern möchten, und klicken Sie dann auf Bearbeitungssymbol **Bearbeiten** ![ ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) .

4. Konfigurieren Sie im Flyout, das angezeigt wird, die folgenden Einstellungen:

   - **Blockieren/zulassen**: Wählen Sie **zulassen** oder **blockieren** aus.

   - **Nie ablaufen**: führen Sie einen der folgenden Schritte aus:

     - Stellen Sie sicher, dass die Einstellung deaktiviert ist (deaktivieren ![ ](../../media/scc-toggle-off.png) ), und verwenden Sie das Feld **expires on** , um das Ablaufdatum für den Eintrag anzugeben.

     oder

     - Bewegen Sie die Umschaltfläche nach rechts, um den Eintrag so zu konfigurieren, dass er nie abläuft: ![Umschaltfläche ein](../../media/scc-toggle-on.png).

   - **Optional Hinweis**: Geben Sie einen beschreibenden Text für den Eintrag ein.

5. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a>Verwenden des Security & Compliance Center zum Entfernen von Einträgen aus der Liste "Mandanten zulassen/blockieren"

1. Wechseln Sie im Security & Compliance Center zu **Bedrohungs Verwaltungs** \> **Richtlinie** \> **Mandanten-Zulassungs-/Sperrlisten**.

2. Wählen Sie die Registerkarte **URLs** aus.

3. Wählen Sie den Eintrag aus, den Sie entfernen möchten, und klicken Sie **dann auf Delete** ![ Delete Icon ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .

4. Klicken Sie im angezeigten Warndialogfeld auf **Löschen**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Verwenden Exchange Online PowerShell oder eigenständiger EoP PowerShell zum Konfigurieren der Liste "Mandanten zulassen/blockieren"

### <a name="use-powershell-to-add-entries-in-the-tenant-allowblock-list"></a>Verwenden von PowerShell zum Hinzufügen von Einträgen in der Liste "Mandanten zulassen/blockieren"

Verwenden Sie die folgende Syntax, um Einträge in der Liste Mandanten Allow/Block hinzuzufügen:

```powershell
New-TenantAllowBlockListItems -ListType Url -Action <Allow | Block> -Entries <String[]> [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

In diesem Beispiel wird ein URL-Sperreintrag für contoso.com und alle Unterdomänen hinzugefügt (beispielsweise contoso.com, www.contoso.com und XYZ.ABC.contoso.com). Da die Parameter ExpirationDate oder NOEXPIRE nicht verwendet wurden, läuft der Eintrag nach 30 Tagen ab.

```powershell
New-TenantAllowBlockListItem -ListType Url -Action Block -Entries ~contoso.com
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/new-tenantallowblocklistitems).

### <a name="use-powershell-to-view-entries-in-the-tenant-allowblock-list"></a>Verwenden von PowerShell zum Anzeigen von Einträgen in der Liste "Mandanten zulassen/blockieren"

Verwenden Sie die folgende Syntax, um Einträge in der Liste Mandanten Allow/Block anzuzeigen:

```powershell
Get-TenantAllowBlockListItems -ListType Url [-Entry <URLValue>] [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration]
```

In diesem Beispiel werden alle blockierten URLs zurückgegeben.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Action Block
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/get-tenantallowblocklistitems).

### <a name="use-powershell-to-modify-entries-in-the-tenant-allowblock-list"></a>Verwenden von PowerShell zum Ändern von Einträgen in der Liste "Mandanten zulassen/blockieren"

Sie können den URL-Wert selbst nicht ändern. Stattdessen müssen Sie den Eintrag löschen und neu erstellen.

Verwenden Sie die folgende Syntax, um Einträge in der Liste Mandanten Allow/Block zu ändern:

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN"> [-Action <Allow | Block>] [-ExpirationDate <DateTime>] [-NoExpiration] [-Notes <String>]
```

In diesem Beispiel wird das Ablaufdatum des angegebenen Eintrags geändert.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate (Get-Date "5/30/2020 9:30 AM").ToUniversalTime()
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/set-tenantallowblocklistitems).

### <a name="use-powershell-to-remove-entries-from-the-tenant-allowblock-list"></a>Verwenden von PowerShell zum Entfernen von Einträgen aus der Liste "Mandanten zulassen/blockieren"

Verwenden Sie die folgende Syntax, um Einträge aus der Liste Mandanten Allow/Block zu entfernen:

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids <"Id1","Id2",..."IdN">
```

In diesem Beispiel wird der angegebene URL-Eintrag aus der Liste Mandanten-Allow/Block entfernt.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-TenantAllowBlockListItems](https://docs.microsoft.com/powershell/module/exchange/remove-tenantallowblocklistitems).

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>URL-Syntax für die Liste "Mandanten zulassen/blockieren"

- IP4v-und IPv6-Adressen sind zulässig, TCP/UDP-Ports jedoch nicht.

- Dateierweiterungen sind nicht zulässig (beispielsweise test.pdf).

- Unicode wird nicht unterstützt, aber Punycode ist.

- Hostnames sind zulässig, wenn alle der folgenden Aussagen zutreffen:

  - Der Hostname enthält einen Punkt.
  - Es gibt mindestens ein Zeichen auf der linken Seite des Punkts.
  - Rechts vom Punkt befinden sich mindestens zwei Zeichen.

  Beispielsweise `t.co` ist zulässig; `.com` oder ist `contoso.` nicht zulässig.

- Unterpfade sind nicht impliziert.

  Enthält beispielsweise `contoso.com` nicht `contoso.com/a` .

- Platzhalterzeichen (*) sind in den folgenden Szenarien zulässig:

  - Auf einen linken Platzhalter muss ein Punkt folgen, um eine Unterdomäne anzugeben.

    Beispielsweise `*.contoso.com` ist zulässig; `*contoso.com` ist nicht zulässig.

  - Ein rechter Platzhalter muss einem Schrägstrich (/) entsprechen, um einen Pfad anzugeben.

    Beispielsweise `contoso.com/*` ist zulässig; `contoso.com*` oder ist `contoso.com/ab*` nicht zulässig.

  - Alle untergeordneten Pfade sind nicht durch einen richtigen Platzhalter impliziert.

    Enthält beispielsweise `contoso.com/*` nicht `contoso.com/a` .

  - `*.com*` ist ungültig (keine auflösbare Domäne, und der Rechte Platzhalter folgt keinem Schrägstrich).

  - Platzhalter sind in IP-Adressen nicht zulässig.

- Das Tildezeichen (~) steht in den folgenden Szenarien zur Verfügung:

  - Eine linke Tilde impliziert eine Domäne und alle Unterdomänen.

    Beispielsweise `~contoso.com` enthält `contoso.com` und `*.contoso.com` .

- URL-Einträge, die Protokolle enthalten (beispielsweise,, `http://` `https://` oder `ftp://` ) schlagen fehl, da URL-Einträge auf alle Protokolle angewendet werden.

- Ein Benutzername oder ein Kennwort werden nicht unterstützt oder erforderlich.

- Anführungszeichen (' oder ') sind ungültige Zeichen.

- Eine URL sollte nach Möglichkeit alle Umleitungen enthalten.

### <a name="url-entry-scenarios"></a>URL-Eintrags Szenarien

In den folgenden Abschnitten werden gültige URL-Einträge und ihre Ergebnisse beschrieben.

#### <a name="scenario-no-wildcards"></a>Szenario: keine Platzhalter

**Eintrag**: `contoso.com`

- **Übereinstimmung zulassen**: contoso.com

- **Zulassen nicht abgeglichen**:

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www. contoso. com/q = a@contoso. com

- **Block Übereinstimmung**:

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www. contoso. com/q = a@contoso. com

- **Block nicht abgeglichen**: ABC-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>Szenario: Linker Platzhalter (Unterdomäne)

**Eintrag**: `*.contoso.com`

- Übereinstimmung und **Block Übereinstimmung** **zulassen** :

  - www.contoso.com
  - xyz.abc.contoso.com

- **Zulassen nicht abgeglichen** und **Block nicht abgeglichen**:

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-at-top-of-path"></a>Szenario: rechter Platzhalter oben im Pfad

**Eintrag**: `contoso.com/a/*`

- Übereinstimmung und **Block Übereinstimmung** **zulassen** :

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso. com/a/? q = Joe@t. com

- **Zulassen nicht abgeglichen** und **Block nicht abgeglichen**:

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www. contoso. com/q = a@contoso. com

#### <a name="scenario-left-tilde"></a>Szenario: linke Tilde

**Eintrag**: `~contoso.com`

- Übereinstimmung und **Block Übereinstimmung** **zulassen** :

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **Zulassen nicht abgeglichen** und **Block nicht abgeglichen**:

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>Szenario: Rechtes Platzhalter Suffix

**Eintrag**: `contoso.com/*`

- Übereinstimmung und **Block Übereinstimmung** **zulassen** :

  - contoso. com/? q = whatever@fabrikam. com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **Allow NOT MATCHED** and **Block NOT MATCHED**: contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>Szenario: linke Platzhalter-Unterdomäne und Rechte Platzhalter Suffix

**Eintrag**: `*.contoso.com/*`

- Übereinstimmung und **Block Übereinstimmung** **zulassen** :

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **Allow NOT MATCHED** and **Block NOT MATCHED**: contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>Szenario: linke und Rechte Tilde

**Eintrag**: `~contoso.com~`

- Übereinstimmung und **Block Übereinstimmung** **zulassen** :

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **Zulassen nicht abgeglichen** und **Block nicht abgeglichen**:

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>Szenario: IP-Adresse

**Eintrag**: `1.2.3.4`

- Übereinstimmung **zulassen** und **Block Übereinstimmung**: 1.2.3.4

- **Zulassen nicht abgeglichen** und **Block nicht abgeglichen**:

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>IP-Adresse mit dem richtigen Platzhalter

**Eintrag**: `1.2.3.4/*`

- Übereinstimmung und **Block Übereinstimmung** **zulassen** :

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>Beispiele für ungültige Einträge

Die folgenden Einträge sind ungültig:

- **Fehlende oder ungültige Domänenwerte**:

  - contoso
  - \*contoso.\*
  - \*. com
  - \*. PDF

- **Platzhalter für Text oder ohne Leerzeichen**:

  - \*contoso.com
  - contoso.com\*
  - \*1.2.3.4
  - 1.2.3.4\*
  - contoso.com/a\*
  - contoso.com/ab\*

- **IP-Adressen mit Ports**:

  - contoso.com:443
  - abc.contoso.com:25

- **Nicht beschreibende Platzhalter**:

  - \*
  - \*.\*

- **Mittlere Platzhalter**:

  - Conto \* so.com
  - Conto ~ so. com

- **Doppelte Platzhalter**

  - contoso.com/\*\*
  - contoso.com/\*/\*
