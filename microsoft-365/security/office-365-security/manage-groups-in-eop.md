---
title: Verwalten von Gruppen in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: Administratoren in eigenständigen Exchange Online Protection (EOP)-Organisationen können erfahren, wie Sie Verteilergruppen und E-Mail-aktivierte Sicherheitsgruppen im Exchange Admin Center (EAC) und in der eigenständigen Exchange Online Protection (EOP) PowerShell erstellen, ändern und entfernen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 01fe5c6ab1555749d38f9c092b05aca9befb67fe
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166963"
---
# <a name="manage-groups-in-eop"></a>Verwalten von Gruppen in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
-  [Exchange Online Protection als eigenständige Lösung](https://go.microsoft.com/fwlink/?linkid=2148611)

In eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer können Sie die folgenden Gruppentypen erstellen, ändern und entfernen:

- **Verteilergruppen:** Eine Sammlung von E-Mail-Benutzern oder anderen Verteilergruppen. Beispielsweise Teams oder andere Ad-hoc-Gruppen, die E-Mails in einem europäischen Bereich empfangen oder senden müssen. Verteilergruppen dienen ausschließlich der Verteilung von E-Mail-Nachrichten und sind keine Sicherheitsprinzipale (ihnen können keine Berechtigungen zugewiesen werden).

- **E-Mail-aktivierte Sicherheitsgruppen:** Eine Sammlung von E-Mail-Benutzern und anderen Sicherheitsgruppen, die Zugriffsberechtigungen für Administratorrollen benötigen. Beispielsweise möchten Sie einer bestimmten Gruppe von Benutzern Administratorberechtigungen erteilen, damit sie Antispam- und Ansoftwareeinstellungen konfigurieren können.

    > [!NOTE]
    >
    > - Standardmäßig lehnen neue E-Mail-aktivierte Sicherheitsgruppen Nachrichten von externen (nicht authentifizierten) Absendern ab.
    >
    > - Fügen Sie keine Verteilergruppen zu E-Mail-aktivierten Sicherheitsgruppen hinzu.

Sie können Gruppen im Exchange Admin Center (EAC) und in der eigenständigen EOP PowerShell verwalten.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Informationen zum Öffnen des Exchange Admin Centers finden Sie im [Exchange Admin Center in EOP als eigenständige Lösung.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Wenn Sie Gruppen in der eigenständigen EOP PowerShell verwalten, können Drosselungen auftreten. Die PowerShell-Verfahren in diesem Artikel verwenden eine Batchverarbeitungsmethode, die zu einer Verteilungsverzögerung von ein paar Minuten führt, bevor die Ergebnisse der Befehle angezeigt werden.

- Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen in Exchange Online Protection die entsprechenden Berechtigungen zugewiesen werden. Insbesondere benötigen Sie die Rolle **"Verteilergruppen",** die standardmäßig den Rollengruppen **"Organisationsverwaltung"** und **"Empfängerverwaltung"** zugewiesen ist. Weitere Informationen finden Sie unter "Berechtigungen [in EOP als eigenständige](feature-permissions-in-eop.md) Lösung", und ändern Sie mithilfe der EAC die Liste der Mitglieder in [Rollengruppen.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Informationen zu Tastenkombinationen, die für die Verfahren in diesem Artikel gelten können, finden Sie unter Tastenkombinationen für das [Exchange Admin Center in Exchange Online.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Liegt ein Problem vor? Bitten Sie im [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)-Forum um Hilfe.

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a>Verwalten von Verteilergruppen mithilfe des Exchange Admin Centers

### <a name="use-the-eac-to-create-groups"></a>Erstellen von Gruppen mithilfe der EAC

1. Navigieren Sie in der EAC zu **Empfänger** \> **Gruppen**.

2. Klicken **Sie auf das** Symbol ![ ](../../media/ITPro-EAC-AddIcon.png) "Neu neu", und wählen Sie dann eine der folgenden Optionen aus:

   - **Verteilergruppe**

   - **E-Mail-aktivierte Sicherheitsgruppe**

3. Konfigurieren Sie auf der neuen Gruppenseite, die geöffnet wird, die folgenden Einstellungen. Einstellungen, die mit einer <sup>\*</sup> gekennzeichnet sind, sind erforderlich.

   - <sup>\*</sup>**Anzeigename:** Dieser Name wird im Adressbuch Ihrer Organisation, in der Zeile "An:"  angezeigt, wenn E-Mails an diese Gruppe gesendet werden, und in der Gruppenliste in der EAC. Der Anzeigename ist erforderlich, muss eindeutig sein und benutzerfreundlich sein, damit die Benutzer erkennen, was er ist.

   - <sup>\*</sup>**Alias:** Geben Sie in diesem Feld den Namen des Alias für die Gruppe ein. Der Alias darf 64 Zeichen nicht überschreiten und muss eindeutig sein. Wenn ein Benutzer den Alias in die Zeile "An" einer E-Mail ein eingeben, wird er in den Anzeigenamen der Gruppe aufgelöst.

   - <sup>\*</sup>**E-Mail-Adresse:** Die E-Mail-Adresse besteht aus dem Alias auf der linken Seite des @-Symbols und einer Domäne auf der rechten Seite. Standardmäßig wird der Wert von Alias für den **Aliaswert** verwendet, Sie können ihn jedoch ändern. Klicken Sie für den Domänenwert auf die Dropdownliste, und wählen Sie die akzeptierte Domäne in Ihrer Organisation aus.

   - **Beschreibung:** Diese Beschreibung wird im Adressbuch und im Detailbereich der EAC angezeigt.

   - <sup>\*</sup>**Besitzer:** Ein Gruppenbesitzer kann die Gruppenmitgliedschaft verwalten. Standardmäßig ist die Person, die eine Gruppe erstellt, deren Besitzer. Jede Gruppe muss mindestens einen Besitzer aufweisen.

     Klicken Sie zum Hinzufügen von Besitzern auf **das Symbol** ![ "Hinzufügen". ](../../media/ITPro-EAC-AddIcon.png) Suchen Und wählen Sie im angezeigten Dialogfeld einen Empfänger oder eine Gruppe aus, und klicken Sie dann auf **"Add ->".** Wiederholen Sie diesen Schritt so oft wie nötig. Klicken Sie nach Abschluss des Vorgangs auf **OK**.

     Um einen Besitzer zu entfernen, wählen  Sie den Besitzer aus, und klicken Sie dann auf ![ "Entfernen". ](../../media/ITPro-EAC-RemoveIcon.gif)

   - **Mitglieder:** Gruppenmitglieder hinzufügen und entfernen.

     Klicken Sie zum Hinzufügen von Mitgliedern auf **das Symbol** ![ "Hinzufügen". ](../../media/ITPro-EAC-AddIcon.png) Suchen Und wählen Sie im angezeigten Dialogfeld einen Empfänger oder eine Gruppe aus, und klicken Sie dann auf **"Add ->".** Wiederholen Sie diesen Schritt so oft wie nötig. Klicken Sie nach Abschluss des Vorgangs auf **OK**.

     Um ein Mitglied zu entfernen, wählen Sie das Mitglied aus, und klicken Sie dann auf **"Entfernen"** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) (Symbol).

4. Wenn Sie fertig sind, klicken Sie auf **"Speichern",** um die Verteilergruppe zu erstellen.

### <a name="use-the-eac-to-modify-distribution-groups"></a>Ändern von Verteilergruppen mithilfe der EAC

1. Navigieren Sie in der EAC zu **Empfänger** \> **Gruppen**.

2. Wählen Sie in der Liste der Gruppen die Verteilergruppe oder E-Mail-aktivierte Sicherheitsgruppe aus, die Sie ändern möchten, und klicken Sie dann auf das Symbol  ![ "Bearbeiten". ](../../media/ITPro-EAC-AddIcon.png)

3. Klicken Sie auf der Seite mit den Verteilergruppeneigenschaften, die geöffnet wird, auf eine der folgenden Registerkarten, um Eigenschaften anzeigen oder ändern zu können.

   Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

#### <a name="general"></a>Allgemein

Verwenden Sie diese Registerkarte, um grundlegende Informationen zur Gruppe anzuzeigen oder zu ändern.

- **Anzeigename:** Dieser Name wird im Adressbuch, in der Zeile "An" beim Senden von E-Mails an diese Gruppe und in der **Gruppenliste angezeigt.** Der Anzeigename ist erforderlich und sollte benutzerfreundlich sein, damit Benutzer erkennen, was er ist. Sie muss auch in Ihrer Domäne eindeutig sein.

  Wenn Sie eine Gruppenbenennungsrichtlinie implementiert haben, muss der Anzeigename dem von der Richtlinie definierten Namensformat entsprechen.

- **Alias:** Dies ist der Teil der E-Mail-Adresse, der links vom @-Symbol angezeigt wird. Wenn Sie den Alias ändern, wird die primäre SMTP-Adresse für die Gruppe ebenfalls geändert, die dann den neuen Alias enthält. Zusätzlich bleibt die E-Mail-Adresse mit dem vorherigen Alias als Proxyadresse für die Gruppe erhalten.

- **E-Mail-Adresse:** Die E-Mail-Adresse besteht aus dem Alias auf der linken Seite des @-Symbols und einer Domäne auf der rechten Seite. Standardmäßig wird der Wert von Alias für den **Aliaswert** verwendet, Sie können ihn jedoch ändern. Klicken Sie für den Domänenwert auf die Dropdownliste, und wählen Sie die akzeptierte Domäne in Ihrer Organisation aus.

- **Beschreibung:** Diese Beschreibung wird im Adressbuch und im Detailbereich der EAC angezeigt.

#### <a name="ownership"></a>Besitz

Verwenden Sie diese Registerkarte, um Gruppenbesitzer zuzuordnen. Ein Gruppenbesitzer kann die Gruppenmitgliedschaft verwalten. Standardmäßig ist die Person, die eine Gruppe erstellt, deren Besitzer. Jede Gruppe muss mindestens einen Besitzer aufweisen.

Klicken Sie zum Hinzufügen von Besitzern auf **das Symbol** ![ "Hinzufügen". ](../../media/ITPro-EAC-AddIcon.png) Suchen Und wählen Sie im angezeigten Dialogfeld einen Empfänger aus, und klicken Sie dann auf **"Add ->".** Wiederholen Sie diesen Schritt so oft wie nötig. Klicken Sie nach Abschluss des Vorgangs auf **OK**.

Um einen Besitzer zu entfernen, wählen  Sie den Besitzer aus, und klicken Sie dann auf ![ "Entfernen". ](../../media/ITPro-EAC-RemoveIcon.gif)

#### <a name="membership"></a>Mitgliedschaft

Verwenden Sie diese Registerkarte, um Gruppenmitglieder hinzuzufügen oder zu entfernen. Gruppenbesitzer müssen keine Mitglieder der Gruppe sein.

Klicken Sie zum Hinzufügen von Mitgliedern auf **das Symbol** ![ "Hinzufügen". ](../../media/ITPro-EAC-AddIcon.png) Suchen Und wählen Sie im angezeigten Dialogfeld einen Empfänger oder eine Gruppe aus, und klicken Sie dann auf **"Add ->".** Wiederholen Sie diesen Schritt so oft wie nötig. Klicken Sie nach Abschluss des Vorgangs auf **OK**.

Um ein Mitglied zu entfernen, wählen Sie das Mitglied aus, und klicken Sie dann auf **"Entfernen"** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) (Symbol).

### <a name="use-the-eac-to-remove-groups"></a>Entfernen von Gruppen mithilfe der EAC

1. Navigieren Sie in der EAC zu **Empfänger** \> **Gruppen**.

2. Wählen Sie in der Liste der Gruppen die Verteilergruppe aus, die Sie entfernen möchten, und klicken Sie dann auf  ![ "Entfernen". ](../../media/ITPro-EAC-RemoveIcon.gif)

## <a name="use-powershell-to-manage-groups"></a>Verwenden von PowerShell zum Verwalten von Gruppen

### <a name="use-standalone-eop-powershell-to-view-groups"></a>Verwenden der eigenständigen EOP PowerShell zum Anzeigen von Gruppen

Führen Sie den folgenden Befehl aus, um eine Übersichtsliste aller Verteilergruppen und E-Mail-aktivierten Sicherheitsgruppen in EOP PowerShell als eigenständige Lösung zurückzukehren:

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

Ersetzen Sie zum Zurückgeben der Liste der Gruppenmitglieder den Namen, alias oder die E-Mail-Adresse der Gruppe, und führen Sie \<GroupIdentity\> den folgenden Befehl aus:

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-Recipient"](https://docs.microsoft.com/powershell/module/exchange/get-recipient) und ["Get-DistributionGroupMember".](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember)

### <a name="use-standalone-eop-powershell-to-create-groups"></a>Verwenden der eigenständigen EOP PowerShell zum Erstellen von Gruppen

Verwenden Sie die folgende Syntax, um Verteilergruppen oder E-Mail-aktivierte Sicherheitsgruppen in EOP PowerShell als eigenständige Lösung zu erstellen:

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

**Hinweise**:

- Der _Parameter "Name"_ ist erforderlich, hat eine maximale Länge von 64 Zeichen und muss eindeutig sein. Wenn Sie den _DisplayName_-Parameter nicht verwenden, wird der Wert des _Name_-Parameters für den Anzeigenamen verwendet.

- Wenn Sie den Parameter _"Alias"_ nicht verwenden, wird der Parameter _"Name"_ als Aliaswert verwendet. Leerzeichen werden entfernt, und nicht unterstützte Zeichen werden in Fragezeichen (?) umgewandelt.

- Wenn Sie den Parameter _"PrimarySmtpAddress"_ nicht verwenden, wird der Aliaswert im Parameter _"PrimarySmtpAddress"_ verwendet.

- Wenn Sie den Parameter _"Type"_ nicht verwenden, ist der Standardwert "Distribution".

In diesem Beispiel wird eine Verteilergruppe namens "IT Administrators" mit den angegebenen Eigenschaften erstellt.

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup).

### <a name="use-standalone-eop-powershell-to-modify-groups"></a>Verwenden der eigenständigen EOP PowerShell zum Ändern von Gruppen

Verwenden Sie die folgende Syntax, um Gruppen in der eigenständigen EOP PowerShell zu ändern:

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

In diesem Beispiel wird die primäre SMTP-Adresse (auch als Antwortadresse bezeichnet) für die Gruppe "Seattle Employees" in sea.employees@contoso.com.

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

In diesem Beispiel werden die aktuellen Mitglieder der Gruppe "Security Team" durch Kitty Petersen und Tyson Fawcett ersetzt.

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

In diesem Beispiel wird der Gruppe "Security Team" der neue Benutzer Tyson Fawcett unter Beibehaltung der aktuellen Mitglieder der Gruppe hinzufügt.

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) und [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).

### <a name="remove-a-group-using-remote-windows-powershell"></a>Entfernen einer Gruppe mithilfe von Windows PowerShell

In diesem Beispiel wird die Verteilergruppe "IT Administrators" entfernt.

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).

## <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

Gehen Sie wie folgt vor, um sicherzustellen, dass Sie eine Verteilergruppe oder E-Mail-aktivierte Sicherheitsgruppe erfolgreich erstellt, geändert oder entfernt haben:

- Navigieren Sie in der EAC zu **Empfänger** \> **Gruppen**. Überprüfen Sie, ob die Gruppe aufgeführt ist (oder nicht), und überprüfen Sie den **Gruppentypwert.** Wählen Sie die Gruppe aus, und zeigen Sie die Informationen im Detailbereich an, oder klicken Sie auf **das** ![ Bearbeitungssymbol, ](../../media/ITPro-EAC-AddIcon.png) um die Einstellungen anzuzeigen.

- Führen Sie in der eigenständigen EOP PowerShell den folgenden Befehl aus, um zu überprüfen, ob die Gruppe aufgeführt ist (oder nicht aufgeführt ist):

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- Ersetzen Sie den Namen, alias oder die E-Mail-Adresse der Gruppe, und führen Sie den folgenden Befehl aus, \<GroupIdentity\> um die Einstellungen zu überprüfen:

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- Ersetzen Sie zum Anzeigen der Gruppenmitglieder den Namen, alias oder die E-Mail-Adresse der Gruppe, und führen Sie \<GroupIdentity\> den folgenden Befehl aus:

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
