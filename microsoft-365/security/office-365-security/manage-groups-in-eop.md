---
title: Verwalten von Gruppen in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: Administratoren in eigenständigen Exchange Online Schutzorganisationen können Informationen zum Erstellen, ändern und Entfernen von Verteilergruppen und e-Mail-aktivierten Sicherheitsgruppen in der Exchange-Verwaltungskonsole (EAC) und in der eigenständigen Exchange Online Protection (EoP) PowerShell EoP.
ms.openlocfilehash: 42086b67e22df4725bf07bf227853c070f936f24
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616502"
---
# <a name="manage-groups-in-eop"></a>Verwalten von Gruppen in EOP

In Organisationen mit eigenständigen Exchange Online Schutz (EoP) ohne Exchange Online Postfächer können Sie die folgenden Gruppentypen erstellen, ändern und entfernen:

- **Verteilergruppen**: eine Sammlung von e-Mail-Benutzern oder anderen Verteilergruppen. Beispielsweise Teams oder andere Ad-hoc-Gruppen, die in einem gemeinsamen Interessenbereich e-Mails empfangen oder senden müssen. Verteilergruppen dienen ausschließlich zum Verteilen von e-Mail-Nachrichten und sind keine Sicherheitsprinzipale (Ihnen können keine Berechtigungen zugewiesen werden).

- **E-Mail-aktivierte Sicherheitsgruppen**: eine Sammlung von e-Mail-Benutzern und anderen Sicherheitsgruppen, die Zugriffsberechtigungen für Administratorrollen benötigen. Beispielsweise können Sie bestimmten Gruppen von Benutzern Administratorberechtigungen erteilen, damit diese Einstellungen für Antispam-und Antischadsoftware konfigurieren können.

    > [!NOTE]
    > <ul><li>Standardmäßig lehnen neue e-Mail-aktivierte Sicherheitsgruppen Nachrichten von externen (nicht authentifizierten) Absendern ab.</li><li>Fügen Sie keine Verteilergruppen zu e-Mail-aktivierten Sicherheitsgruppen hinzu.</li></ul>.

Sie können Gruppen in der Exchange-Verwaltungskonsole (EAC) und in der eigenständigen EoP PowerShell verwalten.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Informationen zum Öffnen des Exchange Admin Center finden Sie unter [Exchange Admin Center in Standalone EoP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Wenn Sie Gruppen in eigenständigen EoP PowerShell verwalten, treten möglicherweise Einschränkungen auf. In den PowerShell-Verfahren in diesem Thema wird eine Batch Verarbeitungsmethode verwendet, die zu einer Ausbreitungs Verzögerung von ein paar Minuten führt, bevor die Ergebnisse der Befehle angezeigt werden.

- Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Insbesondere benötigen Sie die Rolle "Verteilergruppen", die standardmäßig den Rollengruppenmitglied (globale Administratoren) und RecipientManagement zugewiesen ist. Weitere Informationen finden Sie unter [Berechtigungen in eigenständigen EoP](feature-permissions-in-eop.md) und [Verwenden der Exchange-Verwaltungskonsole ändern der Liste der Mitglieder in Rollengruppen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Informationen zu Tastenkombinationen, die möglicherweise für die Verfahren in diesem Thema gelten, finden Sie unter [Tastenkombinationen für das Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Liegt ein Problem vor? Fragen Sie im Forum [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) nach Hilfe.

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a>Verwalten von Verteilergruppen mithilfe der Exchange-Verwaltungskonsole

### <a name="use-the-eac-to-create-groups"></a>Erstellen von Gruppen mithilfe der Exchange-Verwaltungskonsole

1. Navigieren Sie in der EAC zu **Empfänger** \> **Gruppen**.

2. Klicken Sie auf **Neues** ![ Neues Symbol ](../../media/ITPro-EAC-AddIcon.png) , und wählen Sie dann eine der folgenden Optionen aus:

   - **Verteilergruppe**

   - **E-Mail-aktivierte Sicherheitsgruppe**

3. Konfigurieren Sie auf der Seite neue Gruppe, die geöffnet wird, die folgenden Einstellungen. Mit einem markierte Einstellungen <sup>\*</sup> sind erforderlich.

   - <sup>\*</sup>**Anzeigename**: dieser Name wird im Adressbuch Ihrer Organisation, in der an:-Adresse angezeigt, wenn e-Mail an diese Gruppe gesendet wird, und in der Liste **Gruppen** in der Exchange-Verwaltungskonsole. Der Anzeigename ist erforderlich, muss eindeutig sein und sollte benutzerfreundlich sein, damit Personen erkennen, was er ist.

   - <sup>\*</sup>**Alias**: Geben Sie in diesem Feld den Namen des Alias für die Gruppe ein. Der Alias darf 64 Zeichen nicht überschreiten und muss eindeutig sein. Wenn ein Benutzer den Alias in der an-Codezeile einer e-Mail-Nachricht eingibt, wird er in den Anzeigenamen der Gruppe aufgelöst.

   - <sup>\*</sup>**E-Mail-Adresse**: die e-Mail-Adresse besteht aus dem Alias links neben dem @-Symbol und einer Domäne auf der rechten Seite. Standardmäßig wird der Wert von **Alias** für den Alias Wert verwendet, aber Sie können ihn ändern. Klicken Sie für den Wert Domäne auf die Dropdownliste und dann auf die Domäne auswählen und akzeptieren in Ihrer Organisation.

   - **Beschreibung**: Diese Beschreibung wird im Adressbuch und im Detailbereich der Exchange-Verwaltungskonsole angezeigt.

   - <sup>\*</sup>**Besitzer**: ein Gruppenbesitzer kann Gruppenmitgliedschaften verwalten. Standardmäßig ist die Person, die eine Gruppe erstellt, deren Besitzer. Jede Gruppe muss mindestens einen Besitzer aufweisen.

     Klicken Sie zum Hinzufügen von Besitzern auf Add-Symbol **Hinzufügen** ![ ](../../media/ITPro-EAC-AddIcon.png) . Suchen Sie im angezeigten Dialogfeld einen Empfänger oder eine Gruppe, und wählen Sie ihn aus, und klicken Sie dann auf **Add->**. Wiederholen Sie diesen Schritt so oft wie nötig. Klicken Sie nach Abschluss des Vorgangs auf **OK**.

     Wenn Sie einen Besitzer entfernen möchten, wählen Sie den Besitzer aus, und klicken Sie dann auf entfernen-Symbol **Entfernen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .

   - **Mitglieder**: Gruppenmitglieder hinzufügen und entfernen.

     Klicken Sie zum Hinzufügen von Mitgliedern auf Add-Symbol **Hinzufügen** ![ ](../../media/ITPro-EAC-AddIcon.png) . Suchen Sie im angezeigten Dialogfeld einen Empfänger oder eine Gruppe, und wählen Sie ihn aus, und klicken Sie dann auf **Add->**. Wiederholen Sie diesen Schritt so oft wie nötig. Klicken Sie nach Abschluss des Vorgangs auf **OK**.

     Wenn Sie ein Mitglied entfernen möchten, wählen Sie das Mitglied aus, und klicken Sie dann auf entfernen-Symbol **Entfernen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .

4. Wenn Sie fertig sind, klicken Sie auf **Speichern** , um die Verteilergruppe zu erstellen.

### <a name="use-the-eac-to-modify-distribution-groups"></a>Ändern von Verteilergruppen mithilfe der Exchange-Verwaltungskonsole

1. Navigieren Sie in der EAC zu **Empfänger** \> **Gruppen**.

2. Wählen Sie in der Liste der Gruppen die Verteilergruppe oder die e-Mail-aktivierte Sicherheitsgruppe aus, die Sie ändern möchten, und klicken Sie dann auf Bearbeitungssymbol **Bearbeiten** ![ ](../../media/ITPro-EAC-AddIcon.png) .

3. Klicken Sie auf der Seite Eigenschaften der Verteilergruppe, die geöffnet wird, auf eine der folgenden Registerkarten, um Eigenschaften anzuzeigen oder zu ändern.

   Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

#### <a name="general"></a>Allgemein

Verwenden Sie diese Registerkarte, um grundlegende Informationen zur Gruppe anzuzeigen oder zu ändern.

- **Anzeigename**: dieser Name wird im Adressbuch, in der an-Adresse angezeigt, wenn e-Mail-Nachrichten an diese Gruppe gesendet werden, und in der **Liste Gruppen**. Der Anzeigename ist erforderlich und sollte benutzerfreundlich sein, damit Personen erkennen, was es ist. Es muss auch in Ihrer Domäne eindeutig sein.

  Wenn Sie eine Gruppenbenennungsrichtlinie implementiert haben, muss der Anzeigename dem von der Richtlinie definierten Namensformat entsprechen.

- **Alias**: Dies ist der Teil der e-Mail-Adresse, der Links neben dem @-Symbol angezeigt wird. Wenn Sie den Alias ändern, wird die primäre SMTP-Adresse für die Gruppe ebenfalls geändert, die dann den neuen Alias enthält. Zusätzlich bleibt die E-Mail-Adresse mit dem vorherigen Alias als Proxyadresse für die Gruppe erhalten.

- **E-Mail-Adresse**: die e-Mail-Adresse besteht aus dem Alias links neben dem @-Symbol und einer Domäne auf der rechten Seite. Standardmäßig wird der Wert von **Alias** für den Alias Wert verwendet, aber Sie können ihn ändern. Klicken Sie für den Wert Domäne auf die Dropdownliste und dann auf die Domäne auswählen und akzeptieren in Ihrer Organisation.

- **Beschreibung**: Diese Beschreibung wird im Adressbuch und im Detailbereich der Exchange-Verwaltungskonsole angezeigt.

#### <a name="ownership"></a>Besitz

Verwenden Sie diese Registerkarte, um Gruppenbesitzer zuzuweisen. Ein Gruppenbesitzer kann Gruppenmitgliedschaften verwalten. Standardmäßig ist die Person, die eine Gruppe erstellt, deren Besitzer. Jede Gruppe muss mindestens einen Besitzer aufweisen.

Klicken Sie zum Hinzufügen von Besitzern auf Add-Symbol **Hinzufügen** ![ ](../../media/ITPro-EAC-AddIcon.png) . Suchen und wählen Sie im daraufhin angezeigten Dialogfeld einen Empfänger aus, und klicken Sie dann auf **Add->**. Wiederholen Sie diesen Schritt so oft wie nötig. Klicken Sie nach Abschluss des Vorgangs auf **OK**.

Wenn Sie einen Besitzer entfernen möchten, wählen Sie den Besitzer aus, und klicken Sie dann auf entfernen-Symbol **Entfernen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .

#### <a name="membership"></a>Mitgliedschaft

Verwenden Sie diese Registerkarte, um Gruppenmitglieder hinzuzufügen oder zu entfernen. Gruppenbesitzer müssen nicht Mitglieder der Gruppe sein.

Klicken Sie zum Hinzufügen von Mitgliedern auf Add-Symbol **Hinzufügen** ![ ](../../media/ITPro-EAC-AddIcon.png) . Suchen Sie im angezeigten Dialogfeld einen Empfänger oder eine Gruppe, und wählen Sie ihn aus, und klicken Sie dann auf **Add->**. Wiederholen Sie diesen Schritt so oft wie nötig. Klicken Sie nach Abschluss des Vorgangs auf **OK**.

Wenn Sie ein Mitglied entfernen möchten, wählen Sie das Mitglied aus, und klicken Sie dann auf entfernen-Symbol **Entfernen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .

### <a name="use-the-eac-to-remove-groups"></a>Entfernen von Gruppen mithilfe der Exchange-Verwaltungskonsole

1. Navigieren Sie in der EAC zu **Empfänger** \> **Gruppen**.

2. Wählen Sie in der Liste der Gruppen die Verteilergruppe aus, die Sie entfernen möchten, und klicken Sie dann auf entfernen Symbol **Entfernen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .

## <a name="use-powershell-to-manage-groups"></a>Verwenden von PowerShell zum Verwalten von Gruppen

### <a name="use-standalone-eop-powershell-to-view-groups"></a>Verwenden eigenständiger EoP PowerShell zum Anzeigen von Gruppen

Führen Sie den folgenden Befehl aus, um eine Zusammenfassungsliste aller Verteilergruppen und e-Mail-aktivierten Sicherheitsgruppen in eigenständiger EoP PowerShell zurückzugeben:

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

Um die Liste der Gruppenmitglieder zurückzugeben, ersetzen Sie \<GroupIdentity\> durch den Namen, den Alias oder die e-Mail-Adresse der Gruppe, und führen Sie den folgenden Befehl aus:

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) und [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember).

### <a name="use-standalone-eop-powershell-to-create-groups"></a>Verwenden eigenständiger EoP PowerShell zum Erstellen von Gruppen

Verwenden Sie die folgende Syntax, um Verteilergruppen oder e-Mail-aktivierte Sicherheitsgruppen in eigenständigen EoP PowerShell zu erstellen:

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

**Hinweise**:

- Der _Name_ -Parameter ist erforderlich, hat eine maximale Länge von 64 Zeichen und muss eindeutig sein. Wenn Sie den _DisplayName_-Parameter nicht verwenden, wird der Wert des _Name_-Parameters für den Anzeigenamen verwendet.

- Wenn Sie den Parameter _Alias_ nicht verwenden, wird der _Name_ -Parameter für den Alias-Wert verwendet. Leerzeichen werden entfernt, und nicht unterstützte Zeichen werden in Fragezeichen (?) konvertiert.

- Wenn Sie den Parameter _PrimarySmtpAddress_ nicht verwenden, wird der Alias Wert im Parameter _PrimarySmtpAddress_ verwendet.

- Wenn Sie den Parameter _Type_ nicht verwenden, lautet der Standardwert Distribution.

In diesem Beispiel wird eine Verteilergruppe mit dem Namen "IT Administrators" mit den angegebenen Eigenschaften erstellt.

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup).

### <a name="use-standalone-eop-powershell-to-modify-groups"></a>Verwenden eigenständiger EoP PowerShell zum Ändern von Gruppen

Verwenden Sie die folgende Syntax, um Gruppen in eigenständigen EoP PowerShell zu ändern:

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

In diesem Beispiel wird die primäre SMTP-Adresse (auch als Antwortadresse bezeichnet) für die Gruppe "Seattle Employees" in Sea.Employees@contoso.com verwendet.

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

In diesem Beispiel werden die aktuellen Mitglieder der Sicherheits Team Gruppe durch Kitty Petersen und Tyson Fawcett ersetzt.

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

In diesem Beispiel wird der Gruppe "Security Team" ein neuer Benutzernamens "Tyson Fawcett" hinzugefügt, während die aktuellen Mitglieder der Gruppe beibehalten werden.

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) und [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).

### <a name="remove-a-group-using-remote-windows-powershell"></a>Entfernen einer Gruppe mithilfe von Remote Windows PowerShell

In diesem Beispiel wird die Verteilergruppe "IT-Administratoren" entfernt.

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).

## <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie eine Verteilergruppe oder eine e-Mail-aktivierte Sicherheitsgruppe erfolgreich erstellt, geändert oder entfernt haben:

- Navigieren Sie in der EAC zu **Empfänger** \> **Gruppen**. Stellen Sie sicher, dass die Gruppe aufgeführt (oder nicht aufgeführt) ist, und überprüfen Sie den Wert des **Gruppentyps** . Wählen Sie die Gruppe aus, und zeigen Sie die Informationen im Detailbereich an, oder klicken Sie auf Bearbeitungssymbol **Bearbeiten** ![ ](../../media/ITPro-EAC-AddIcon.png) , um die Einstellungen anzuzeigen.

- Führen Sie in eigenständiger EoP-PowerShell den folgenden Befehl aus, um zu überprüfen, ob die Gruppe aufgeführt (oder nicht aufgeführt) ist:

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- Ersetzen \<GroupIdentity\> Sie durch den Namen, den Alias oder die e-Mail-Adresse der Gruppe, und führen Sie den folgenden Befehl aus, um die Einstellungen zu überprüfen:

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- Um die Gruppenmitglieder anzuzeigen, ersetzen Sie \<GroupIdentity\> durch den Namen, den Alias oder die e-Mail-Adresse der Gruppe, und führen Sie den folgenden Befehl aus:

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
