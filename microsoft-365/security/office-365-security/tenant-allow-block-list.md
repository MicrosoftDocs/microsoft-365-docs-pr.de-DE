---
title: Verwalten Ihrer Zulässigen und Blöcke in der Liste "Mandanten zulassen/blockieren"
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
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie im Sicherheitsportal in der Liste "Mandanten zulassen/blockieren" Zulassen und Blockieren von Zulassen und Blockieren konfigurieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 636114180a1814f5ef842b2a704f2df98488f46e
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694485"
---
# <a name="manage-the-tenant-allowblock-list"></a>Verwalten der Zulassungs-/Sperrliste des Mandanten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> Die in diesem Artikel beschriebenen Features befinden sich in Vorschau, können geändert werden und sind nicht in allen Organisationen verfügbar.  Wenn Ihre Organisation nicht über die in diesem Artikel beschriebenen Spooffunktionen verfügt, lesen Sie die ältere [Spoofverwaltungserfahrung unter Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP](walkthrough-spoof-intelligence-insight.md).
>
> Sie können zu **diesem** Zeitpunkt keine zulässigen URL- oder Dateielemente in der Mandanten zulassen/blockieren-Liste konfigurieren.

In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online Postfächer können Sie mit dem EOP-Filter-Urteil nicht einverstanden sein. Beispielsweise kann eine gute Nachricht als ungültig (falsch positiv) gekennzeichnet werden, oder eine schlechte Nachricht kann als ungültig (falsch negativ) zugelassen werden.

Mit der Mandanten-Allow/Block-Liste im Security & Compliance Center können Sie die Filterungs-Microsoft 365 manuell außer Kraft setzen. Die Mandanten zulassen/blockieren Liste wird während des Nachrichtenflusses und zum Zeitpunkt der Benutzerklicks verwendet. Sie können die folgenden Arten von Außerkraftsetzungen angeben:

- ZU blockierende URLs.
- Zu blockierende Dateien.
- Spoofed senders to allow or block. Wenn Sie das Allow- oder Block-Urteil in der [Spoof Intelligence-Einsicht](learn-about-spoof-intelligence.md)außer Kraft setzen, wird der gefälschte Absender zu einem manuellen Zulassen- oder Blockiereneintrag, der nur auf der Registerkarte **Spoof** in der Mandanten-Zulassen-/Sperrliste angezeigt wird. Sie können hier auch manuell Zulassen oder Blockieren von Einträgen für spoofierte Absender erstellen, bevor sie von Spoof Intelligence erkannt werden.

In diesem Artikel wird beschrieben, wie Sie Einträge in der Mandanten zulassen/blockieren-Liste im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange Online-Postfächer) konfigurieren.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Um direkt zur Seite **Mandanten zulassen/blockieren zu** wechseln, verwenden Sie <https://protection.office.com/tenantAllowBlockList> .

- Sie geben Dateien mithilfe des SHA256-Hashwerts der Datei an. Führen Sie den folgenden Befehl in einer Eingabeaufforderung aus, um den SHA256-Hashwert einer Datei in Windows zu finden:

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  Ein Beispielwert ist `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` . #A0 (Perceptual Hash) werden nicht unterstützt.

- Die verfügbaren #A0 werden weiter unten in diesem Artikel in der #A1 für den Abschnitt [Mandanten zulassen/blockieren](#url-syntax-for-the-tenant-allowblock-list) beschrieben.

- Die Mandantenzu-/-sperrliste ermöglicht maximal 500 Einträge für URLs und 500 Einträge für Dateihashes.

- Die maximale Anzahl von Zeichen für jeden Eintrag ist:
  - Dateihashes = 64
  - URL = 250

- Ein Eintrag sollte innerhalb von 30 Minuten aktiv sein.

- Standardmäßig laufen Einträge in der Mandanten-Zulassen-/Sperrliste nach 30 Tagen ab. Sie können ein Datum angeben oder festlegen, dass es nie abläuft.

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Sie müssen in Exchange Online Berechtigungen erhalten, bevor Sie die in diesem Artikel beschriebenen Schritte ausführen können:
  - **URLs und Dateien**:
    - Zum Hinzufügen und Entfernen von Werten aus der Mandantenberechtigungs-/Sperrliste müssen Sie Mitglied der Rollengruppen Organisationsverwaltung oder **Sicherheitsadministrator** sein. 
    - Für den schreibgeschützten Zugriff auf die Mandantenzugriffs-/Sperrliste müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Sicherheitsleser"** sein.
  - **Spoofing**: Eine der folgenden Kombinationen:
    - **Organisationsverwaltung**
    - **Sicherheitsadministrator** und **Nur-Ansicht-Konfiguration** oder **Nur-Ansicht-Organisationsverwaltung**. <u></u>

  Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).
  >
  > - Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.

## <a name="use-the-security--compliance-center-to-create-block-url-entries-in-the-tenant-allowblock-list"></a>Verwenden des Security & Compliance Center zum Erstellen von Block-URL-Einträgen in der Mandantenzu-/-sperrliste

1. Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.

2. Überprüfen Sie auf der Seite Mandanten **zulassen/blockieren,** ob die Registerkarte **URLs** ausgewählt ist, und klicken Sie dann auf **Blockieren.**

3. Konfigurieren Sie **im angezeigten** Flyout UrLs blockieren die folgenden Einstellungen:

   - **Zu blockierende URLs hinzufügen:** Geben Sie eine URL pro Zeile ein, bis zu maximal 20. Weitere Informationen zur Syntax für #A0 finden Sie in der URL-Syntax für den Abschnitt [Mandantenzu-/Sperrliste](#url-syntax-for-the-tenant-allowblock-list) weiter unten in diesem Artikel.

   - **Nie ablaufen:** Gehen Sie wie folgt vor:

     - Überprüfen Sie, ob die Einstellung deaktiviert ist ( Umschalten ) und verwenden Sie das Feld Läuft auf, um das ![ ](../../media/scc-toggle-off.png) Ablaufdatum für die Einträge anzugeben. 

       oder

     - Verschieben Sie den Umschalter nach rechts, um die Einträge so zu konfigurieren, dass sie nie ablaufen: ![Umschaltfläche ein](../../media/scc-toggle-on.png).

   - **Optionaler Hinweis:** Geben Sie beschreibenden Text für die Einträge ein.

4. Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.

## <a name="use-the-security--compliance-center-to-create-block-file-entries-in-the-tenant-allowblock-list"></a>Verwenden des Security & Compliance Center zum Erstellen von Blockdateieinträgen in der Mandantenzu-/-sperrliste

1. Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.

2. Wählen Sie auf der Seite Mandanten **zulassen/blockieren** die Registerkarte **Dateien** aus, und klicken Sie dann auf **Blockieren**.

3. Konfigurieren Sie **im angezeigten Flyout** Dateien zum Blockieren von Dateien hinzufügen die folgenden Einstellungen:

   - **Hinzufügen von Dateihashes:** Geben Sie einen SHA256-Hashwert pro Zeile ein, bis zu maximal 20.

   - **Nie ablaufen:** Gehen Sie wie folgt vor:

     - Überprüfen Sie, ob die Einstellung deaktiviert ist ( Umschalten ) und verwenden Sie das Feld Läuft auf, um das ![ ](../../media/scc-toggle-off.png) Ablaufdatum für die Einträge anzugeben. 

     oder

     - Verschieben Sie den Umschalter nach rechts, um die Einträge so zu konfigurieren, dass sie nie ablaufen: ![Umschaltfläche ein](../../media/scc-toggle-on.png).

   - **Optionaler Hinweis:** Geben Sie beschreibenden Text für die Einträge ein.

4. Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.

## <a name="use-the-security--compliance-center-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>Verwenden des Security & Compliance Center zum Erstellen oder Blockieren gefälschter Absendereinträge in der Mandantenzu-/Sperrliste

**Hinweise**:

- Nur die _Kombination_ aus dem  spoofierten Benutzer und der sendenden Infrastruktur, wie im Domänenpaar definiert, ist ausdrücklich zulässig oder von Spoofing blockiert.
- Wenn Sie einen zulässigen oder blockierten Eintrag für ein Domänenpaar konfigurieren, werden Nachrichten dieses Domänenpaars nicht mehr in der Spoof Intelligence-Einsicht angezeigt.
- Einträge für spoofierte Absender laufen nie ab.

1. Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.

2. Wählen Sie auf der Seite Mandanten **zulassen/blockieren** die Registerkarte **Spoofing** aus, und klicken Sie dann auf **Hinzufügen**.

3. Konfigurieren Sie **im angezeigten** Flyout Neue Domänenpaare hinzufügen die folgenden Einstellungen:

   - **Hinzufügen neuer Domänenpaare mit Platzhaltern:** Geben Sie ein Domänenpaar pro Zeile ein, bis maximal 20. Weitere Informationen zur Syntax für spoofierte Absendereinträge finden Sie in der Syntax des Domänenpaars für spoofierte Absendereinträge im Abschnitt [Mandantenzu-/-sperrliste](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) weiter unten in diesem Artikel.

   - **Spooftyp**: Wählen Sie einen der folgenden Werte aus:
     - **Intern:** Der gefälschte Absender befindet sich in einer Domäne, die zu Ihrer Organisation gehört (eine [akzeptierte Domäne](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).
     - **Extern:** Der gefälschte Absender befindet sich in einer externen Domäne.

   - **Aktion**: Wählen Sie **Zulassen** oder **Blockieren aus.**

4. Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.

## <a name="use-the-security--compliance-center-to-view-entries-in-the-tenant-allowblock-list"></a>Verwenden des Security & Compliance Center zum Anzeigen von Einträgen in der Mandantenzu-/-sperrliste

1. Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.

2. Wählen Sie die registerkarte aus, die Sie möchten. Die verfügbaren Spalten hängen von der ausgewählten Registerkarte ab:

   - **URLs**:
     - **Wert**: Die URL.
     - **Aktion**: Der Wert **Block**.
     - **Datum der letzten Aktualisierung**
     - **Ablaufdatum**
     - **Hinweis**

   - **Files**
     - **Wert**: Der Dateihash.
     - **Aktion**: Der Wert **Block**.
     - **Datum der letzten Aktualisierung**
     - **Ablaufdatum**
     - **Hinweis**

   - **Spoofing**
     - **Spoofed user**
     - **Senden von Infrastruktur**
     - **Spooftyp**: Der Wert **Internal** oder **External**.
     - **Aktion**: Der Wert **Block** oder **Allow**.

   Sie können auf eine Spaltenüberschrift klicken, um in aufsteigender oder absteigender Reihenfolge zu sortieren.

   Sie können auf **Gruppe klicken,** um die Ergebnisse zu gruppieren. Die verfügbaren Werte hängen von der ausgewählten Registerkarte ab:

   - **URLs**: Sie können die Ergebnisse nach **Aktion gruppieren.**
   - **Dateien**: Sie können die Ergebnisse nach **Aktion gruppieren.**
   - **Absenderdomänen für die BCL-Umgehung:** **Die Gruppe** ist auf dieser Registerkarte nicht verfügbar.
   - **Spoofing**: Sie können die Ergebnisse nach **Aktions-** oder **Spooftyp gruppieren.**

   Klicken **Sie auf Suchen,** geben Sie einen Wert ganz oder teilweise ein, und drücken Sie die EINGABETASTE, um einen bestimmten Wert zu finden. Wenn Sie fertig sind, klicken Sie auf **Suche löschen Suchsymbol** ![ löschen ](../../media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) .

   Klicken **Sie auf Filtern,** um die Ergebnisse zu filtern. Die im angezeigten **Filterf** flyout verfügbaren Werte hängen von der ausgewählten Registerkarte ab:

   - **URLs**
     - **Action**
     - **Nie ablaufen**
     - **Datum der letzten Aktualisierung**
     - **Ablaufdatum**

   - **Files**
     - **Action**
     - **Nie ablaufen**
     - **Datum der letzten Aktualisierung**
     - **Ablaufdatum**

   - **Absenderdomänen für die BCL-Umgehung**
     - **Nie ablaufen**
     - **Datum der letzten Aktualisierung**
     - **Ablaufdatum**

   - **Spoofing**
     - **Action**
     - **Spooftyp**

   Klicken Sie nach Abschluss des Abschlusses auf **Übernehmen**. Klicken Sie zum Löschen vorhandener Filter auf **Filter,** und klicken Sie im angezeigten **Flyout** Filter **auf Filter löschen.**

## <a name="use-the-security--compliance-center-to-modify-entries-in-the-tenant-allowblock-list"></a>Verwenden des Security & Compliance Center zum Ändern von Einträgen in der Mandantenzu-/-sperrliste

1. Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.

2. Wählen Sie die Registerkarte aus, die den Typ des Eintrags enthält, den Sie ändern möchten:
   - **URLs**
   - **Files**
   - **Absenderdomänen für die BCL-Umgehung**
   - **Spoofing**

3. Wählen Sie den Eintrag aus, den Sie ändern möchten, und klicken Sie dann auf **Bearbeiten** ![ (Symbol). ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) Die Werte, die Sie im angezeigten Flyout ändern können, hängen von der Registerkarte ab, die Sie im vorherigen Schritt ausgewählt haben:

   - **URLs**
     - **Niemals ablaufen** und/oder Ablaufdatum.
     - **Optionaler Hinweis**

   - **Files**
     - **Niemals ablaufen** und/oder Ablaufdatum.
     - **Optionaler Hinweis**

   - **Absenderdomänen für die BCL-Umgehung**
     - **Niemals ablaufen** und/oder Ablaufdatum.

   - **Spoofing**
     - **Aktion**: Sie können den Wert in **Zulassen oder** **Blockieren ändern.**

4. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

## <a name="use-the-security--compliance-center-to-remove-entries-from-the-tenant-allowblock-list"></a>Verwenden des Security & Compliance Center zum Entfernen von Einträgen aus der Mandantenzu-/-sperrliste

1. Wechseln Sie im Security & Compliance Center zu Richtlinien für die **Bedrohungsverwaltung** \>  \> **Mandanten zulassen/blockieren Listen**.

2. Wählen Sie die Registerkarte aus, die den Typ des Eintrags enthält, den Sie entfernen möchten:
   - **URLs**
   - **Files**
   - **Absenderdomänen für die BCL-Umgehung**
   - **Spoofing**

3. Wählen Sie den Eintrag aus, den Sie entfernen möchten, und klicken Sie dann **auf Löschen** ![ -Symbol ](../../media/87565fbb-5147-4f22-9ed7-1c18ce664392.png) .

4. Klicken Sie im angezeigten Warnungsdialogfeld auf **Löschen**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Verwenden Exchange Online PowerShell oder eigenständiger EOP PowerShell zum Konfigurieren der Mandanten zulassen/Blockieren-Liste

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a>Verwenden von PowerShell zum Hinzufügen von Blockdatei- oder URL-Einträgen zur Mandantenzu-/Sperrliste

Verwenden Sie die folgende Syntax, um Blockdatei- oder #A0 in der Mandanten zulassen/blockieren-Liste hinzuzufügen:

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

In diesem Beispiel wird ein Blockdateieintrag für die angegebenen Dateien, die nie abläuft, hinzufügt.

```powershell
New-TenantAllowBlockListItem -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

In diesem Beispiel wird ein Block-URL-Eintrag für contoso.com und alle Unterdomänen hinzugefügt (z. B. contoso.com, www.contoso.com und xyz.abc.contoso.com). Da wir die Parameter ExpirationDate oder NoExpiration nicht verwendet haben, läuft der Eintrag nach 30 Tagen ab.

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a>Verwenden von PowerShell zum Hinzufügen zulässiger oder blockieren von gefälschten Absendereinträgen zur Mandantenzu-/Sperrliste

Verwenden Sie die folgende Syntax, um spoofierte Absendereinträge in der Mandanten zulassen/blockieren-Liste hinzuzufügen:

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a>Verwenden von PowerShell zum Anzeigen von Blockdatei- oder URL-Einträgen in der Mandantenzu-/-sperrliste

Verwenden Sie die folgende Syntax, um Blockdatei- oder #A0 in der Mandanten zulassen/blockieren-Liste anzeigen zu können:

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash | URL> [-Entry <FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

In diesem Beispiel werden Informationen für den angegebenen Dateihashwert zurückgegeben.

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

In diesem Beispiel werden alle blockierten URLs zurückgegeben.

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>Verwenden von PowerShell zum Anzeigen zulässiger oder blockierter Absendereinträge in der Mandantenzu-/Sperrliste

Verwenden Sie die folgende Syntax, um spoofierte Absendereinträge in der Mandantenzu-/Sperrliste anzeigen zu können:

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

In diesem Beispiel werden alle spoofierten Absendereinträge in der Mandanten zulassen/blockieren-Liste zurückgegeben.

```powershell
Get-TenantAllowBlockListSpoofItems
```

In diesem Beispiel werden alle zulässigen spoofierten Absendereinträge zurückgegeben, die intern sind.

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

In diesem Beispiel werden alle blockierten spoofierten Absendereinträge zurückgegeben, die extern sind.

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems).

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a>Verwenden von PowerShell zum Ändern von Blockdatei- und URL-Einträgen in der Mandantenzu-/Sperrliste

Verwenden Sie die folgende Syntax, um Blockdatei- und #A0 in der Mandanten-Allow/Block List zu ändern:

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

In diesem Beispiel wird das Ablaufdatum des angegebenen Block-URL-Eintrags geändert.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>Verwenden von PowerShell zum Ändern zulässiger oder blockierter Absendereinträge in der Mandantenzu-/Sperrliste

Verwenden Sie die folgende Syntax, um gefälschte Absendereinträge in der Mandanten zulassen/blockieren-Liste zu ändern oder zu blockieren:

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

In diesem Beispiel wird der Spoofing-Absendereintrag von "Blockieren" geändert.

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-TenantAllowBlockListSpoofItems](/powershell/module/exchange/set-tenantallowblocklistspoofitems).

### <a name="use-powershell-to-remove-url-or-file-entries-from-the-tenant-allowblock-list"></a>Verwenden von PowerShell zum Entfernen von URL- oder Dateieinträgen aus der Liste mandanten zulassen/blockieren

Verwenden Sie die folgende Syntax, um Datei- und URL-Einträge aus der Mandantenzu-/Sperrliste zu entfernen:

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

In diesem Beispiel wird der angegebene Block-URL-Eintrag aus der Mandanten-Allow/Block List entfernt.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a>Verwenden von PowerShell zum Entfernen zulässiger oder blockierter Gefälschter Absendereinträge aus der Mandantenzu-/Sperrliste

Verwenden Sie die folgende Syntax, um Spoof-Absendereinträge aus der Mandanten zulassen/blockieren-Liste zu entfernen oder zu blockieren:

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>#A0 für die Mandanten-Allow/Block List

- IP4v- und IPv6-Adressen sind zulässig, TCP/UDP-Ports jedoch nicht.

- Dateinamenerweiterungen sind nicht zulässig (z. B. test.pdf).

- Unicode wird nicht unterstützt, Punycode jedoch.

- Hostnamen sind zulässig, wenn alle folgenden Anweisungen zutreffen:
  - Der Hostname enthält einen Zeitraum.
  - Es gibt mindestens ein Zeichen links vom Zeitraum.
  - Rechts neben dem Zeitraum befinden sich mindestens zwei Zeichen.

  Beispielsweise ist `t.co` zulässig oder nicht `.com` `contoso.` zulässig.

- Unterpfade werden nicht impliziert.

  Enthält z. `contoso.com` B. nicht `contoso.com/a` .

- Platzhalter (*) sind in den folgenden Szenarien zulässig:

  - Auf einen linken Platzhalter muss ein Zeitraum folgen, um eine Unterdomäne anzugeben.

    Ist beispielsweise `*.contoso.com` zulässig; `*contoso.com` ist nicht zulässig.

  - Ein rechter Platzhalter muss einem Schrägstrich (/) folgen, um einen Pfad anzugeben.

    Beispielsweise ist `contoso.com/*` zulässig oder nicht `contoso.com*` `contoso.com/ab*` zulässig.

  - Alle Unterpfade werden nicht durch einen rechten Platzhalter impliziert.

    Enthält z. `contoso.com/*` B. nicht `contoso.com/a` .

  - `*.com*` ist ungültig (keine auflösbare Domäne, und der rechte Platzhalter folgt keinem Schrägstrich).

  - Platzhalter sind in IP-Adressen nicht zulässig.

- Das Tildezeichen (~) ist in den folgenden Szenarien verfügbar:

  - Eine linke Tilde impliziert eine Domäne und alle Unterdomänen.

    Enthält `~contoso.com` z. `contoso.com` B. und `*.contoso.com` .

- URL-Einträge, die Protokolle (z. B. , oder ) enthalten, werden fehlschlagen, da `http://` URL-Einträge für alle Protokolle `https://` `ftp://` gelten.

- Ein Benutzername oder Kennwort wird nicht unterstützt oder ist nicht erforderlich.

- Anführungszeichen (' oder ") sind ungültige Zeichen.

- Eine URL sollte nach Möglichkeit alle Umleitungen enthalten.

### <a name="url-entry-scenarios"></a>Szenarien für den URL-Eintrag

Gültige URL-Einträge und deren Ergebnisse werden in den folgenden Abschnitten beschrieben.

#### <a name="scenario-no-wildcards"></a>Szenario: Keine Platzhalter

**Eintrag**: `contoso.com`

- **Übereinstimmung zulassen**: contoso.com

- **Nicht übereinstimmend zulassen:**

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **Übereinstimmung blockieren**:

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **Block nicht übereinstimmend**: abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>Szenario: Linker Platzhalter (Unterdomäne)

**Eintrag**: `*.contoso.com`

- **Übereinstimmung zulassen** und **Übereinstimmung blockieren**:

  - www.contoso.com
  - xyz.abc.contoso.com

- **Allow not matched** and **Block not matched**:

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-at-top-of-path"></a>Szenario: Rechter Platzhalter am oberen Rand des Pfads

**Eintrag**: `contoso.com/a/*`

- **Übereinstimmung zulassen** und **Übereinstimmung blockieren**:

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso.com/a/?q=joe@t.com

- **Allow not matched** and **Block not matched**:

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

#### <a name="scenario-left-tilde"></a>Szenario: Left tilde

**Eintrag**: `~contoso.com`

- **Übereinstimmung zulassen** und **Übereinstimmung blockieren**:

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **Allow not matched** and **Block not matched**:

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>Szenario: Rechtes Platzhaltersuffix

**Eintrag**: `contoso.com/*`

- **Übereinstimmung zulassen** und **Übereinstimmung blockieren**:

  - contoso.com/?q=whatever@fabrikam.com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **Nicht übereinstimmend zulassen und** **Block nicht** übereinstimmen: contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>Szenario: Linke Platzhalterunterdomäne und rechtes Platzhaltersuffix

**Eintrag**: `*.contoso.com/*`

- **Übereinstimmung zulassen** und **Übereinstimmung blockieren**:

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **Nicht übereinstimmend zulassen und** **Block nicht** übereinstimmen : contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>Szenario: Linker und rechter Tilde

**Eintrag**: `~contoso.com~`

- **Übereinstimmung zulassen** und **Übereinstimmung blockieren**:

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **Allow not matched** and **Block not matched**:

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>Szenario: IP-Adresse

**Eintrag**: `1.2.3.4`

- **Übereinstimmung zulassen** und **Übereinstimmung blockieren**: 1.2.3.4

- **Allow not matched** and **Block not matched**:

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>IP-Adresse mit rechtem Platzhalter

**Eintrag**: `1.2.3.4/*`

- **Übereinstimmung zulassen** und **Übereinstimmung blockieren**:

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>Beispiele für ungültige Einträge

Die folgenden Einträge sind ungültig:

- **Fehlende oder ungültige Domänenwerte**:

  - contoso
  - \*.contoso.\*
  - \*.com
  - \*.PDF

- **Platzhalter für Text oder ohne Abstandszeichen**:

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

  - conto \* so.com
  - conto~so.com

- **Doppelte Platzhalter**

  - contoso.com/\*\*
  - contoso.com/\*/\*

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>Domänenpaarsyntax für spoofierte Absendereinträge in der Mandantenzu-/-sperrliste

Ein Domänenpaar für einen gefälschten Absender in der Mandanten-Allow/Block List verwendet die folgende Syntax: `<Spoofed user>, <Sending infrastructure>` .

- **Spoofed user**: Dieser Wert umfasst die E-Mail-Adresse des spoofierten Benutzers, der im Feld **Von** in E-Mail-Clients angezeigt wird. Diese Adresse wird auch als Adresse `5322.From` bezeichnet. Gültige Werte sind:
  - Eine einzelne E-Mail-Adresse (z. B. chris@contoso.com).
  - Eine E-Mail-Domäne (z. B. contoso.com).
  - Das Platzhalterzeichen (z. B. \* ).

- **Sendende Infrastruktur:** Dieser Wert gibt die Quelle von Nachrichten des spoofierten Benutzers an. Gültige Werte sind:
  - Die Domäne in einer Reverse-DNS-Suche (PTR-Eintrag) der IP-Adresse des Quell-E-Mail-Servers (z. B. fabrikam.com).
  - Wenn die Quell-IP-Adresse keinen PTR-Eintrag enthält, wird die sendende Infrastruktur als \<source IP\> /24 identifiziert (z. B. 192.168.100.100/24).

Im Folgenden finden Sie einige Beispiele für gültige Domänenpaare zum Identifizieren gefälschter Absender:

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

Das Hinzufügen eines Domänenpaars ermöglicht oder blockiert nur die *Kombination* des spoofierten Benutzers *und der sendenden* Infrastruktur. E-Mails vom spoofierten Benutzer aus einer Beliebigen Quelle werden nicht zulässig, und es werden auch keine E-Mails aus der sendenden Infrastrukturquelle für spoofierte Benutzer zulässig.

Beispielsweise fügen Sie einen zulässigen Eintrag für das folgende Domänenpaar hinzu:

- **Domäne**: gmail.com
- **Infrastruktur**: tms.mx.com

Nur Nachrichten von dieser Domäne und *dem sendenden* Infrastrukturpaar dürfen spoofen. Andere Absender, die versuchen, gmail.com zu spoofen, sind nicht zulässig. Nachrichten von Absendern in anderen Domänen, die von tms.mx.com stammen, werden durch Spoof intelligence überprüft.
