---
title: Verwalten Ihrer Zulassungen und Blöcke in der Mandanten-Zulassungs-/Sperrliste
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
description: Administratoren können im Sicherheitsportal erfahren, wie Sie Zulassungen und Blöcke in der Mandanten-Zulassungs-/Sperrliste konfigurieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dbd4694a7442b3898d24304dc78fc95c28c9a905
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394953"
---
# <a name="manage-the-tenant-allowblock-list"></a>Verwalten der Zulassungs-/Sperrliste des Mandanten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> Die in diesem Artikel beschriebenen Features befinden sich in der Vorschau, können geändert werden und sind nicht in allen Organisationen verfügbar.  Wenn Ihre Organisation nicht über die in diesem Artikel beschriebenen Spoofingfeatures verfügt, lesen Sie die ältere Spoofverwaltungserfahrung unter [Verwalten von gefälschten Absendern mithilfe der Spoof Intelligence-Richtlinie und des Einblicks in spoofintelligenz in EOP.](walkthrough-spoof-intelligence-insight.md)
>
> Sie können derzeit keine zulässigen URL- oder Dateielemente in der Mandanten-Zulassungs-/Sperrliste **konfigurieren.**

In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online Postfächer können Sie mit der EOP-Filterbewertung nicht einverstanden sein. Beispielsweise kann eine gute Nachricht als falsch markiert werden (ein falsch positives Ergebnis), oder eine ungültige Nachricht kann durchgelassen werden (ein falsch negativer Wert).

Die Mandanten-Zulassungs-/Sperrliste im Microsoft 365 Defender-Portal bietet Ihnen die Möglichkeit, die Microsoft 365 Filterbewertungen manuell zu überschreiben. Die Mandanten-Zulassungs-/Sperrliste wird während des Nachrichtenflusses für eingehende Nachrichten verwendet (gilt nicht für organisationsinterne Nachrichten) und zum Zeitpunkt der Benutzerklicks. Sie können die folgenden Arten von Außerkraftsetzungen angeben:

- Zu blockierende URLs.
- Zu blockierende Dateien.
- Gefälschte Absender, die zugelassen oder blockiert werden sollen. Wenn Sie die Zulassungs- oder Blockbewertung im Einblick in die [Spoofintelligenz](learn-about-spoof-intelligence.md)außer Kraft setzen, wird der gefälschte Absender zu einem manuellen Zulassungs- oder Blockierungseintrag, der nur auf der Registerkarte **"Spoofing"** in der Mandanten-Zulassungs-/Sperrliste angezeigt wird. Sie können hier auch manuell Zulassungseinträge für gefälschte Absender erstellen oder blockieren, bevor sie durch Spoofintelligenz erkannt werden.

In diesem Artikel wird beschrieben, wie Sie Einträge in der Mandanten-Zulassungs-/Sperrliste im Microsoft 365 Defender-Portal oder in PowerShell konfigurieren (Exchange Online PowerShell für Microsoft 365 Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange Online Postfächer).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com/>. Um direkt zur Seite **"Mandanten-Zulassungs-/Sperrlisten"** zu wechseln, verwenden Sie <https://security.microsoft.com/tenantAllowBlockList> .

- Sie geben Dateien mithilfe des SHA256-Hashwerts der Datei an. Um den SHA256-Hashwert einer Datei in Windows zu finden, führen Sie den folgenden Befehl an einer Eingabeaufforderung aus:

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  Ein Beispielwert ist `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a` . Perceptual Hash (pHash)-Werte werden nicht unterstützt.

- Die verfügbaren URL-Werte werden in der [URL-Syntax für den Abschnitt "Mandanten zulassen/blockieren"](#url-syntax-for-the-tenant-allowblock-list) weiter unten in diesem Artikel beschrieben.

- Die Mandanten-Zulassungs-/Sperrliste lässt maximal 500 Einträge für URLs und 500 Einträge für Dateihashes zu.

- Die maximale Anzahl von Zeichen für jeden Eintrag lautet:
  - Dateihashes = 64
  - URL = 250

- Ein Eintrag sollte innerhalb von 30 Minuten aktiv sein.

- Standardmäßig laufen Einträge in der Mandanten-Zulassungs-/Sperrliste nach 30 Tagen ab. Sie können ein Datum angeben oder festlegen, dass es nie abläuft.

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Sie müssen in Exchange Online Berechtigungen erhalten, bevor Sie die in diesem Artikel beschriebenen Schritte ausführen können:
  - **URLs und Dateien:**
    - Um Werte aus der Mandanten-Zulassungs-/Sperrliste hinzuzufügen und zu entfernen, müssen Sie Mitglied der Rollengruppen **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** sein.
    - Für den schreibgeschützten Zugriff auf die Mandanten-Zulassungs-/Sperrliste müssen Sie Mitglied der Rollengruppe **"Globaler Leser"** oder **"Sicherheitsleseberechtigter"** sein.
  - **Spoofing:** Eine der folgenden Kombinationen:
    - **Organisationsverwaltung**
    - **Sicherheitsadministrator** <u>und</u> **Nur-Ansicht-Konfiguration** oder **Nur-Ansicht-Organisationsverwaltung**.

  Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).
  >
  > - Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.

## <a name="use-the-microsoft-365-defender-portal-to-create-block-url-entries-in-the-tenant-allowblock-list"></a>Verwenden des Microsoft 365 Defender Portals zum Erstellen von Block-URL-Einträgen in der Mandanten-Zulassungs-/Sperrliste

1. Wechseln Sie im Portal Microsoft 365 Defender zu **Richtlinien &** \> **Regel-Bedrohungsrichtlinien** \>  Abschnitt \> **"Mandanten-Zulassungs-/Sperrlisten".**

2. Überprüfen Sie auf der Seite **"Mandanten-Zulassungs-/Sperrliste",** ob die Registerkarte **"URLs"** ausgewählt ist, und klicken Sie dann auf ![ das Symbol ](../../media/m365-cc-sc-create-icon.png) **"Blockieren".**

3. Konfigurieren Sie im angezeigten Flyout **"URLs blockieren"** die folgenden Einstellungen:
   - **Hinzufügen von URLs mit Platzhaltern:** Geben Sie eine URL pro Zeile ein, maximal 20. Ausführliche Informationen zur Syntax für URL-Einträge finden Sie in der [URL-Syntax für den Abschnitt "Mandanten-Zulassungs-/Sperrliste"](#url-syntax-for-the-tenant-allowblock-list) weiter unten in diesem Artikel.
   - **Läuft nie ab:** Führen Sie einen der folgenden Schritte aus:
     - Stellen Sie sicher, dass die Einstellung deaktiviert ist ( ![ Umschalten ](../../media/scc-toggle-off.png) ) und verwenden Sie das Feld **"Entfernen** auf", um das Ablaufdatum für die Einträge anzugeben.

       oder

     - Verschieben Sie den Umschalter nach rechts, um die Einträge so zu konfigurieren, dass sie nie ablaufen: ![Umschaltfläche ein](../../media/scc-toggle-on.png).
   - **Optionaler Hinweis:** Geben Sie beschreibenden Text für die Einträge ein.

4. Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.

## <a name="use-the-microsoft-365-defender-portal-to-create-block-file-entries-in-the-tenant-allowblock-list"></a>Verwenden des Microsoft 365 Defender Portals zum Erstellen von Blockierungsdateieinträgen in der Mandanten-Zulassungs-/Sperrliste

1. Wechseln Sie im Portal Microsoft 365 Defender zu **Richtlinien &** \> **Regel-Bedrohungsrichtlinien** \>  Abschnitt \> **"Mandanten-Zulassungs-/Sperrlisten".**

2. Wählen Sie auf der Seite **"Mandanten-Zulassungs-/Sperrliste"** die Registerkarte **"Dateien"** aus, und klicken Sie dann auf ![ das Symbol ](../../media/m365-cc-sc-create-icon.png) **"Blockieren".**

3. Konfigurieren Sie im angezeigten Flyout **"Dateien blockieren"** die folgenden Einstellungen:
   - **Hinzufügen von Dateihashes:** Geben Sie einen SHA256-Hashwert pro Zeile ein, bis maximal 20.
   - **Läuft nie ab:** Führen Sie einen der folgenden Schritte aus:
     - Stellen Sie sicher, dass die Einstellung deaktiviert ist ( ![ Umschalten ](../../media/scc-toggle-off.png) ) und verwenden Sie das Feld **"Entfernen** auf", um das Ablaufdatum für die Einträge anzugeben.

     oder

     - Verschieben Sie den Umschalter nach rechts, um die Einträge so zu konfigurieren, dass sie nie ablaufen: ![Umschaltfläche ein](../../media/scc-toggle-on.png).
   - **Optionaler Hinweis:** Geben Sie beschreibenden Text für die Einträge ein.

4. Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.

## <a name="use-the-microsoft-365-defender-portal-to-create-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>Verwenden des Microsoft 365 Defender Portals zum Erstellen oder Blockieren von Spoofing-Absendereinträgen in der Mandanten-Zulassungs-/Sperrliste

**Hinweise**:

- Nur die _Kombination aus_ dem gefälschten Benutzer _und_ der sendenden Infrastruktur, wie im Domänenpaar definiert, ist ausdrücklich zulässig oder am Spoofing gehindert.
- Wenn Sie einen Zulassungs- oder Blockeintrag für ein Domänenpaar konfigurieren, werden Nachrichten von diesem Domänenpaar nicht mehr in der Spoofintelligenz angezeigt.
- Einträge für gefälschte Absender laufen nie ab.

1. Wechseln Sie im Portal Microsoft 365 Defender zu **Richtlinien &** \> **Regel-Bedrohungsrichtlinien** \>  Abschnitt \> **"Mandanten-Zulassungs-/Sperrlisten".**

2. Wählen Sie auf der Seite **"Mandanten-Zulassungs-/Sperrliste"** die Registerkarte **"Spoofing"** aus, und klicken Sie dann auf ![ "Hinzufügen" auf das Symbol "Blockieren". ](../../media/m365-cc-sc-create-icon.png) 

3. Konfigurieren Sie im angezeigten Flyout **"Neue Domänenpaare hinzufügen"** die folgenden Einstellungen:
   - **Hinzufügen neuer Domänenpaare mit Platzhaltern:** Geben Sie ein Domänenpaar pro Zeile ein, maximal 20. Ausführliche Informationen zur Syntax für spoofierte Absendereinträge finden Sie in der [Domänenpaarsyntax für spoofierte Absendereinträge im Abschnitt "Mandanten-Zulassungs-/Sperrliste"](#domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list) weiter unten in diesem Artikel.
   - **Spooftyp:** Wählen Sie einen der folgenden Werte aus:
     - **Intern:** Der gefälschte Absender befindet sich in einer Domäne, die zu Ihrer Organisation gehört (einer [akzeptierten Domäne).](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)
     - **Extern:** Der gefälschte Absender befindet sich in einer externen Domäne.
   - **Aktion:** Wählen Sie **"Zulassen"** oder **"Blockieren"** aus.

4. Klicken Sie nach Abschluss des Vorgangs auf **Hinzufügen**.

## <a name="use-the-microsoft-365-defender-portal-to-view-entries-in-the-tenant-allowblock-list"></a>Verwenden des Microsoft 365 Defender Portals zum Anzeigen von Einträgen in der Mandanten-Zulassungs-/Sperrliste

1. Wechseln Sie im Portal Microsoft 365 Defender zu **Richtlinien &** \> **Regel-Bedrohungsrichtlinien** \>  Abschnitt \> **"Mandanten-Zulassungs-/Sperrlisten".**

2. Wählen Sie die gewünschte Registerkarte aus. Welche Spalten verfügbar sind, hängt von der ausgewählten Registerkarte ab:

   - **URLs:**
     - **Wert:** Die URL.
     - **Aktion:** Der Wert **Block**.
     - **Zuletzt aktualisiert**
     - **Entfernen von "On"**
     - **Notizen**
   - **Files**
     - **Wert:** Der Dateihash.
     - **Aktion:** Der Wert **Block**.
     - **Zuletzt aktualisiert**
     - **Entfernen von "On"**
     - **Notizen**
   - **Spoofing**
     - **Gefälschter Benutzer**
     - **Senden der Infrastruktur**
     - **Spooftyp:** Der Wert **Internal** oder **External**.
     - **Aktion:** Der Wert **Block** oder **Allow**.

   Sie können auf eine Spaltenüberschrift klicken, um sie in aufsteigender oder absteigender Reihenfolge zu sortieren.

   Sie können auf **"Gruppieren"** klicken, um die Ergebnisse zu gruppieren. Die verfügbaren Werte hängen von der ausgewählten Registerkarte ab:

   - **URLs:** Sie können die Ergebnisse nach **Aktion** gruppieren.
   - **Dateien:** Sie können die Ergebnisse nach **Aktion** gruppieren.
   - **Spoofing:** Sie können die Ergebnisse nach **Aktions-** oder **Spooftyp** gruppieren.

   Klicken Sie auf **"Suchen",** geben Sie einen Wert ganz oder teilweise ein, und drücken Sie dann die EINGABETASTE, um einen bestimmten Wert zu finden. Wenn Sie fertig sind, klicken Sie auf ![ Suchsymbol löschen ](../../media/m365-cc-sc-close-icon.png) **.**

   Klicken Sie auf **"Filtern",** um die Ergebnisse zu filtern. Die werte, die  im angezeigten Filter-Flyout verfügbar sind, hängen von der ausgewählten Registerkarte ab:

   - **Urls**
     - **Action**
     - **Nie ablaufen**
     - **Datum der letzten Aktualisierung**
     - **Entfernen von "On"**
   - **Files**
     - **Action**
     - **Nie ablaufen**
     - **Zuletzt aktualisiert**
     - **Entfernen von "On"**
   - **Spoofing**
     - **Action**
     - **Spooftyp**

   Wenn Sie fertig sind, klicken Sie auf **"Übernehmen".** Klicken Sie zum Löschen vorhandener Filter auf **"Filter",** und klicken Sie im angezeigten **Flyout "Filter"** auf **"Filter löschen".**

## <a name="use-the-microsoft-365-defender-portal-to-modify-entries-in-the-tenant-allowblock-list"></a>Verwenden des Microsoft 365 Defender Portals zum Ändern von Einträgen in der Mandanten-Zulassungs-/Sperrliste

1. Wechseln Sie im Portal Microsoft 365 Defender zu **Richtlinien &** \> **Regel-Bedrohungsrichtlinien** \>  Abschnitt \> **"Mandanten-Zulassungs-/Sperrlisten".**

2. Wählen Sie die Registerkarte aus, die den Eintragstyp enthält, den Sie ändern möchten:
   - **Urls**
   - **Files**
   - **Spoofing**

3. Wählen Sie den Eintrag aus, den Sie ändern möchten, und klicken Sie dann auf ![ ](../../media/m365-cc-sc-edit-icon.png) **"Bearbeiten".** Die Werte, die Sie im angezeigten Flyout ändern können, hängen von der Registerkarte ab, die Sie im vorherigen Schritt ausgewählt haben:
   - **Urls**
     - **Nie ablaufen** und/oder Ablaufdatum.
     - **Optionaler Hinweis**
   - **Files**
     - **Nie ablaufen** und/oder Ablaufdatum.
     - **Optionaler Hinweis**
   - **Spoofing**
     - **Aktion:** Sie können den Wert in **Zulassen** oder **Blockieren** ändern.
4. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

## <a name="use-the-microsoft-365-defender-portal-to-remove-entries-from-the-tenant-allowblock-list"></a>Verwenden des Microsoft 365 Defender Portals zum Entfernen von Einträgen aus der Mandanten-Zulassungs-/Sperrliste

1. Wechseln Sie im Portal Microsoft 365 Defender zu **Richtlinien &** \> **Regel-Bedrohungsrichtlinien** \>  Abschnitt \> **"Mandanten-Zulassungs-/Sperrlisten".**

2. Wählen Sie die Registerkarte aus, die den Eintragstyp enthält, den Sie entfernen möchten:
   - **Urls**
   - **Files**
   - **Spoofing**

3. Wählen Sie den Eintrag aus, den Sie entfernen möchten, und klicken Sie dann auf ![ ](../../media/m365-cc-sc-delete-icon.png) **"Löschen".**

4. Klicken Sie im angezeigten Warndialogfeld auf **"Löschen".**

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list"></a>Verwenden Exchange Online PowerShell oder der eigenständigen EOP PowerShell zum Konfigurieren der Mandanten-Zulassungs-/Sperrliste

### <a name="use-powershell-to-add-block-file-or-url-entries-to-the-tenant-allowblock-list"></a>Verwenden von PowerShell zum Hinzufügen von Blockierungsdateien oder URL-Einträgen zur Mandanten-Zulassungs-/Sperrliste

Verwenden Sie die folgende Syntax, um Blockierungsdateien oder URL-Einträge in der Mandanten-Zulassungs-/Sperrliste hinzuzufügen:

```powershell
New-TenantAllowBlockListItems -ListType <FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

In diesem Beispiel wird ein Blockdateieintrag für die angegebenen Dateien hinzugefügt, die nie ablaufen.

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

In diesem Beispiel wird ein Block-URL-Eintrag für contoso.com und alle Unterdomänen hinzugefügt (z. B. contoso.com, www.contoso.com und xyz.abc.contoso.com). Da wir die Parameter ExpirationDate oder NoExpiration nicht verwendet haben, läuft der Eintrag nach 30 Tagen ab.

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).

### <a name="use-powershell-to-add-allow-or-block-spoofed-sender-entries-to-the-tenant-allowblock-list"></a>Verwenden von PowerShell zum Hinzufügen oder Blockieren von Spoofing-Absendereinträgen zur Mandanten-Zulassungs-/Sperrliste

Verwenden Sie die folgende Syntax, um gefälschte Absendereinträge in der Mandanten-Zulassungs-/Sperrliste hinzuzufügen:

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).

### <a name="use-powershell-to-view-block-file-or-url-entries-in-the-tenant-allowblock-list"></a>Verwenden von PowerShell zum Anzeigen von Blockierungsdateien oder URL-Einträgen in der Mandanten-Zulassungs-/Sperrliste

Verwenden Sie die folgende Syntax, um Blockierungsdateien oder URL-Einträge in der Mandanten-Zulassungs-/Sperrliste anzuzeigen:

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

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-TenantAllowBlockListItems".](/powershell/module/exchange/get-tenantallowblocklistitems)

### <a name="use-powershell-to-view-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>Verwenden von PowerShell zum Anzeigen oder Blockieren von Spoofing-Absendereinträgen in der Mandanten-Zulassungs-/Sperrliste

Verwenden Sie die folgende Syntax, um gefälschte Absendereinträge in der Mandanten-Zulassungs-/Sperrliste anzuzeigen:

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

In diesem Beispiel werden alle gefälschten Absendereinträge in der Mandanten-Zulassungs-/Sperrliste zurückgegeben.

```powershell
Get-TenantAllowBlockListSpoofItems
```

This example returns all allow spoofed sender entries that are internal.

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

In diesem Beispiel werden alle blockierten spoofierten Absendereinträge zurückgegeben, die extern sind.

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-TenantAllowBlockListSpoofItems".](/powershell/module/exchange/get-tenantallowblocklistspoofitems)

### <a name="use-powershell-to-modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a>Verwenden von PowerShell zum Ändern von Blockdatei- und URL-Einträgen in der Mandanten-Zulassungs-/Sperrliste

Verwenden Sie die folgende Syntax, um Blockdatei- und URL-Einträge in der Mandanten-Zulassungs-/Sperrliste zu ändern:

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

In diesem Beispiel wird das Ablaufdatum des angegebenen Block-URL-Eintrags geändert.

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-TenantAllowBlockListItems".](/powershell/module/exchange/set-tenantallowblocklistitems)

### <a name="use-powershell-to-modify-allow-or-block-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>Verwenden von PowerShell zum Ändern oder Blockieren von Spoofing-Absendereinträgen in der Mandanten-Zulassungs-/Sperrliste

Verwenden Sie die folgende Syntax, um spoofierte Absendereinträge in der Mandanten-Zulassungs-/Sperrliste zu ändern oder zu blockieren:

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

In diesem Beispiel wird der Spoofing-Absendereintrag von "Blockieren zulassen" geändert.

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-TenantAllowBlockListSpoofItems".](/powershell/module/exchange/set-tenantallowblocklistspoofitems)

### <a name="use-powershell-to-remove-url-or-file-entries-from-the-tenant-allowblock-list"></a>Verwenden von PowerShell zum Entfernen von URL- oder Dateieinträgen aus der Mandanten-Zulassungs-/Sperrliste

Verwenden Sie die folgende Syntax, um Datei- und URL-Einträge aus der Mandanten-Zulassungs-/Sperrliste zu entfernen:

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

In diesem Beispiel wird der angegebene Block-URL-Eintrag aus der Mandanten-Zulassungs-/Sperrliste entfernt.

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).

### <a name="use-powershell-to-remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a>Verwenden von PowerShell zum Entfernen von Spoofing-Absendereinträgen aus der Mandanten-Zulassungs-/Sperrliste

Verwenden Sie die folgende Syntax, um Spoofing von Absendereinträgen aus der Mandanten-Zulassungs-/Sperrliste zu entfernen oder zu blockieren:

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems).

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>URL-Syntax für die Mandanten-Zulassungs-/Sperrliste

- IP4v- und IPv6-Adressen sind zulässig, TCP/UDP-Ports jedoch nicht.

- Dateinamenerweiterungen sind nicht zulässig (z. B. test.pdf).

- Unicode wird nicht unterstützt, Punycode jedoch.

- Hostnamen sind zulässig, wenn alle folgenden Anweisungen wahr sind:
  - Der Hostname enthält einen Punkt.
  - Links vom Punkt befindet sich mindestens ein Zeichen.
  - Rechts neben dem Punkt befinden sich mindestens zwei Zeichen.

  Ist beispielsweise `t.co` zulässig `.com` oder nicht `contoso.` zulässig.

- Unterpfade werden nicht impliziert.

  Enthält z. B. `contoso.com` nicht `contoso.com/a` .

- Platzhalter (*) sind in den folgenden Szenarien zulässig:

  - Auf einen linken Platzhalter muss ein Punkt folgen, um eine Unterdomäne anzugeben.

    Ist beispielsweise `*.contoso.com` zulässig; `*contoso.com` ist nicht zulässig.

  - Ein rechter Platzhalter muss einem Schrägstrich (/) folgen, um einen Pfad anzugeben.

    Ist beispielsweise `contoso.com/*` zulässig `contoso.com*` oder nicht `contoso.com/ab*` zulässig.

  - Alle Unterpfade werden nicht durch einen rechten Platzhalter impliziert.

    Enthält z. B. `contoso.com/*` nicht `contoso.com/a` .

  - `*.com*` ungültig ist (keine auflösbare Domäne, und der rechte Platzhalter folgt keinem Schrägstrich).

  - Platzhalter sind in IP-Adressen nicht zulässig.

- Das Tildezeichen (~) ist in den folgenden Szenarien verfügbar:

  - Eine linke Tilde impliziert eine Domäne und alle Unterdomänen.

    Beispiel: `~contoso.com` "includes" `contoso.com` und `*.contoso.com` ".

- URL-Einträge, die Protokolle enthalten (z. B. `http://` , oder ) schlagen `https://` `ftp://` fehl, da URL-Einträge für alle Protokolle gelten.

- Ein Benutzername oder Kennwort wird nicht unterstützt oder ist nicht erforderlich.

- Anführungszeichen (' oder ") sind ungültige Zeichen.

- Eine URL sollte nach Möglichkeit alle Umleitungen enthalten.

### <a name="url-entry-scenarios"></a>URL-Eintragsszenarien

Gültige URL-Einträge und deren Ergebnisse werden in den folgenden Abschnitten beschrieben.

#### <a name="scenario-no-wildcards"></a>Szenario: Keine Platzhalter

**Eintrag**: `contoso.com`

- **Übereinstimmung zulassen:** contoso.com

- **Nicht übereinstimmend zulassen:**

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **Blocküberstimmung:**

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **Block nicht abgeglichen:** abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>Szenario: Linker Platzhalter (Unterdomäne)

**Eintrag**: `*.contoso.com`

- **Übereinstimmung zulassen** und **Übereinstimmung blockieren:**

  - www.contoso.com
  - xyz.abc.contoso.com

- **Nicht übereinstimmende** und **nicht übereinstimmende Blockierung** zulassen:

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-at-top-of-path"></a>Szenario: Rechter Platzhalter oben im Pfad

**Eintrag**: `contoso.com/a/*`

- **Übereinstimmung zulassen** und **Übereinstimmung blockieren:**

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso.com/a/?q=joe@t.com

- **Nicht übereinstimmende** und **nicht übereinstimmende Blockierung** zulassen:

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

#### <a name="scenario-left-tilde"></a>Szenario: Linke Tilde

**Eintrag**: `~contoso.com`

- **Übereinstimmung zulassen** und **Übereinstimmung blockieren:**

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **Nicht übereinstimmende** und **nicht übereinstimmende Blockierung** zulassen:

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>Szenario: Rechtes Platzhaltersuffix

**Eintrag**: `contoso.com/*`

- **Übereinstimmung zulassen** und **Übereinstimmung blockieren:**

  - contoso.com/?q=whatever@fabrikam.com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **Nicht übereinstimmend** und **Block nicht übereinstimmend** zulassen: contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>Szenario: Linke Platzhalterunterdomäne und rechtes Platzhaltersuffix

**Eintrag**: `*.contoso.com/*`

- **Übereinstimmung zulassen** und **Übereinstimmung blockieren:**

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **Nicht übereinstimmende** und **nicht übereinstimmende Blockierung** zulassen: contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>Szenario: Linke und rechte Tilde

**Eintrag**: `~contoso.com~`

- **Übereinstimmung zulassen** und **Übereinstimmung blockieren:**

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **Nicht übereinstimmende** und **nicht übereinstimmende Blockierung** zulassen:

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>Szenario: IP-Adresse

**Eintrag**: `1.2.3.4`

- **Übereinstimmung zulassen** und **Übereinstimmung blockieren:** 1.2.3.4

- **Nicht übereinstimmende** und **nicht übereinstimmende Blockierung** zulassen:

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>IP-Adresse mit rechtem Platzhalter

**Eintrag**: `1.2.3.4/*`

- **Übereinstimmung zulassen** und **Übereinstimmung blockieren:**

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>Beispiele für ungültige Einträge

Die folgenden Einträge sind ungültig:

- **Fehlende oder ungültige Domänenwerte:**

  - Contoso
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

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>Domänenpaarsyntax für gefälschte Absendereinträge in der Mandanten-Zulassungs-/Sperrliste

Ein Domänenpaar für einen gefälschten Absender in der Mandanten-Zulassungs-/Sperrliste verwendet die folgende Syntax: `<Spoofed user>, <Sending infrastructure>` .

- **Gefälschter Benutzer:** Dieser Wert bezieht sich auf die E-Mail-Adresse des gefälschten Benutzers, der im **Feld "Von"** in E-Mail-Clients angezeigt wird. Diese Adresse wird auch als `5322.From` Adresse bezeichnet. Gültige Werte sind:
  - Eine einzelne E-Mail-Adresse (z. B. chris@contoso.com).
  - Eine E-Mail-Domäne (z. B. contoso.com).
  - Das Platzhalterzeichen (z. B. \* ).

- Senden der **Infrastruktur:** Dieser Wert gibt die Quelle von Nachrichten des gefälschten Benutzers an. Gültige Werte sind:
  - Die Domäne in einer Reverse-DNS-Suche (PTR-Eintrag) der IP-Adresse des Quell-E-Mail-Servers (z. B. fabrikam.com).
  - Wenn die Quell-IP-Adresse keinen PTR-Eintrag aufweist, wird die sendende Infrastruktur als \<source IP\> /24 identifiziert (z. B. 192.168.100.100/24).

Hier sind einige Beispiele für gültige Domänenpaare zum Identifizieren von gefälschten Absendern:

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

Die maximale Anzahl von gefälschten Absendereinträgen beträgt 1000.

Das Hinzufügen eines Domänenpaars erlaubt oder blockiert nur die *Kombination aus* dem gefälschten Benutzer *und* der sendenden Infrastruktur. Es erlaubt weder E-Mails vom gefälschten Benutzer aus einer Quelle noch E-Mails aus der sendenden Infrastrukturquelle für spoofierte Benutzer. 

Beispielsweise fügen Sie einen Zulassungseintrag für das folgende Domänenpaar hinzu:

- **Domäne:** gmail.com
- **Infrastruktur:** tms.mx.com

Nur Nachrichten aus dieser Domäne *und* dem sendenden Infrastrukturpaar dürfen Spoofing ausführen. Andere Absender, die versuchen, gmail.com zu spoofen, sind nicht zulässig. Nachrichten von Absendern in anderen Domänen, die von tms.mx.com stammen, werden durch Spoofintelligenz überprüft.
