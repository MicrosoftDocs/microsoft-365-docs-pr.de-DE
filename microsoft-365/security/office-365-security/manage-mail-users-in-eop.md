---
title: Verwalten von E-Mail-Benutzern in EOP als eigenständige Lösung
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: Erfahren Sie, wie Sie E-Mail-Benutzer in Exchange Online Protection (EOP) verwalten, einschließlich der Verwendung von Verzeichnissynchronisierung, EAC und PowerShell zum Verwalten von Benutzern.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 863bde5ef860ee980f768ddc085379180e6a71aa
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203987"
---
# <a name="manage-mail-users-in-standalone-eop"></a>Verwalten von E-Mail-Benutzern in EOP als eigenständige Lösung

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
-  [Exchange Online Protection eigenständig](exchange-online-protection-overview.md)

In eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online sind E-Mail-Benutzer der grundlegende Typ des Benutzerkontos. Ein E-Mail-Benutzer verfügt über Kontoanmeldeinformationen in Ihrer eigenständigen EOP-Organisation und kann auf Ressourcen zugreifen (berechtigungen zugewiesen haben). Die E-Mail-Adresse eines E-Mail-Benutzers ist extern (z. B. in Ihrer lokalen E-Mail-Umgebung).

> [!NOTE]
> Wenn Sie einen E-Mail-Benutzer erstellen, ist das entsprechende Benutzerkonto im Microsoft 365 Admin Center verfügbar. Wenn Sie ein Benutzerkonto im Microsoft 365 Admin Center erstellen, können Sie dieses Konto nicht zum Erstellen eines E-Mail-Benutzers verwenden.

Die empfohlene Methode zum Erstellen und Verwalten von E-Mail-Benutzern in eigenständigem EOP ist die Verwendung der Verzeichnissynchronisierung, wie weiter unten in diesem Artikel im Abschnitt Verwenden der Verzeichnissynchronisierung zum Verwalten von [E-Mail-Benutzern](#use-directory-synchronization-to-manage-mail-users) beschrieben.

Für eigenständige EOP-Organisationen mit einer kleinen Anzahl von Benutzern können Sie E-Mail-Benutzer im Exchange Admin Center (EAC) oder in der eigenständigen EOP PowerShell hinzufügen und verwalten, wie in diesem Artikel beschrieben.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Informationen zum Öffnen Exchange Admin Center (EAC) finden Sie [unter Exchange Admin Center im eigenständigen EOP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Wenn Sie E-Mail-Benutzer in EOP PowerShell erstellen, kann eine Einschränkung auftreten. Außerdem verwenden die EOP PowerShell-Cmdlets eine Batchverarbeitungsmethode, die zu einer Übertragungsverzögerung von einigen Minuten führt, bevor die Ergebnisse der Befehle angezeigt werden.

- Bevor Sie die Verfahren in diesem Artikel Exchange Online Protection, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Insbesondere benötigen Sie die Rollen **E-Mail-Empfängererstellung** (erstellen) und E-Mail-Empfänger (ändern),  die standardmäßig den Rollengruppen Organisationsverwaltung **(globale** Administratoren) und Empfängerverwaltung zugewiesen sind.  Weitere Informationen finden Sie unter [Permissions in standalone EOP](feature-permissions-in-eop.md) und [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Informationen zu Tastenkombinationen, die für die Verfahren in diesem Artikel gelten können, finden Sie unter Tastenkombinationen für das [Exchange Admin Center in Exchange Online](/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Liegt ein Problem vor? Bitten Sie in den Exchange-Foren um Hilfe. Besuchen Sie [das Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) Forum.

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a>Verwenden des Exchange Admin Center zum Verwalten von E-Mail-Benutzern

### <a name="use-the-eac-to-create-mail-users"></a>Erstellen von E-Mail-Benutzern mithilfe der EAC

1. Wechseln Sie in der  EAC zu \> **Empfängerkontakte**

2. Klicken Sie **auf Neues** Neues ![ Symbol ](../../media/ITPro-EAC-AddIcon.png) . Konfigurieren Sie **auf der Seite** Neuer E-Mail-Benutzer, die geöffnet wird, die folgenden Einstellungen. Einstellungen, die mit einem <sup>\*</sup> gekennzeichnet sind, sind erforderlich.

   - **Vorname**

   - **Initialen**: Die mittlere Initiale der Person.

   - **Nachname**

   - <sup>\*</sup>**Anzeigename**: Standardmäßig werden in diesem Feld die Werte aus den Feldern **Vorname,** **Initialen** und **Nachname** angezeigt. Sie können diesen Wert akzeptieren oder ändern. Der Wert sollte eindeutig sein und eine maximale Länge von 64 Zeichen haben.

   - <sup>\*</sup>**Alias**: Geben Sie einen eindeutigen Alias mit bis zu 64 Zeichen für den Benutzer ein.

   - **Externe E-Mail-Adresse:** Geben Sie die E-Mail-Adresse des Benutzers ein. Die Domäne sollte sich außerhalb Ihrer cloudbasierten Organisation befinden.

   - <sup>\*</sup>**Benutzer-ID**: Geben Sie das Konto ein, mit dem sich die Person beim Dienst anmeldet. Die Benutzer-ID besteht aus einem Benutzernamen auf der linken Seite des @-Symbols (@) und einer Domäne auf der rechten Seite.

   - <sup>\*</sup>**Neues Kennwort** und Kennwort bestätigen: Geben Sie das <sup>\*</sup> Kontokennwort ein, und geben Sie es erneut ein. Stellen Sie sicher, dass das Kennwort den Kennwortlängen-, Komplexitäts- und Verlaufsanforderungen Ihrer Organisation entspricht.

3. Wenn Sie fertig sind, klicken Sie auf **Speichern**, um den E-Mail-Benutzer zu erstellen.

### <a name="use-the-eac-to-modify-mail-users"></a>Ändern von E-Mail-Benutzern mithilfe der EAC

1. Navigieren Sie in der Exchange Admin Center zu **Empfänger** \> **Kontakte**.

2. Wählen Sie den E-Mail-Benutzer aus, den Sie ändern möchten, und klicken Sie dann auf **Bearbeiten** ![ (Symbol). ](../../media/ITPro-EAC-AddIcon.png)

3. Klicken Sie auf der seite E-Mail-Benutzereigenschaften, die geöffnet wird, auf eine der folgenden Registerkarten, um Eigenschaften anzeigen oder ändern zu können.

   Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

#### <a name="general"></a>Allgemein

Verwenden Sie die **Registerkarte Allgemein,** um grundlegende Informationen zum E-Mail-Benutzer ein- oder zu ändern.

- **Vorname**

- **Initialen**

- **Nachname**

- **Anzeigename**: Dieser Name wird im Adressbuch Ihrer Organisation, in den Zeilen An: und Von: in E-Mail und in der Liste der Kontakte in der EAC angezeigt. Dieser Name darf keine Leerzeichen vor oder nach dem Anzeigenamen enthalten.

- **Benutzer-ID**: Dies ist das Konto des Benutzers in Microsoft 365. Sie können diesen Wert hier nicht ändern.

#### <a name="contact-information"></a>Kontaktinformationen

Verwenden Sie **die Registerkarte Kontaktinformationen,** um die Kontaktinformationen des Benutzers ein- oder zu ändern. Die Informationen auf dieser Seite werden im Adressbuch angezeigt.

- **Straße**
- **City**
- **Bundesland/Kanton**
- **PLZ**
- **Land/Region**
- **Telefon (geschäftlich)**
- **Mobiltelefon**
- **Fax**
- **Weitere Optionen**

  - **Office**
  - **Telefon (privat)**
  - **Webseite**
  - **Notizen**

#### <a name="organization"></a>Organisation

Verwenden Sie **die Registerkarte Organisation,** um detaillierte Informationen zur Rolle des Benutzers in der Organisation zu aufzeichnen.

- **Titel**
- **Abteilung**
- **Company**

### <a name="use-the-eac-to-remove-mail-users"></a>Entfernen von E-Mail-Benutzern mithilfe der EAC

1. Navigieren Sie in der Exchange Admin Center zu **Empfänger** \> **Kontakte**.

2. Wählen Sie den E-Mail-Benutzer aus, den Sie entfernen möchten, und klicken Sie dann auf **Entfernen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) (Symbol).

## <a name="use-powershell-to-manage-mail-users"></a>Verwalten von E-Mail-Benutzern mithilfe von PowerShell

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a>Verwenden der eigenständigen EOP PowerShell zum Anzeigen von E-Mail-Benutzern

Führen Sie den folgenden Befehl aus, um eine Zusammenfassungsliste aller E-Mail-Benutzer in eigenständigem EOP PowerShell zurück zu geben:

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

Ersetzen Sie zum Anzeigen detaillierter Informationen zu einem bestimmten E-Mail-Benutzer durch den Namen, Alias oder Kontonamen des E-Mail-Benutzers, und führen Sie \<MailUserIdentity\> die folgenden Befehle aus:

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-Recipient](/powershell/module/exchange/get-recipient) und [Get-User](/powershell/module/exchange/get-user).

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a>Verwenden der eigenständigen EOP PowerShell zum Erstellen von E-Mail-Benutzern

Verwenden Sie die folgende Syntax, um E-Mail-Benutzer in eigenständiger EOP PowerShell zu erstellen:

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

**Hinweise**:

- Der _Parameter Name_ ist erforderlich, hat eine maximale Länge von 64 Zeichen und muss eindeutig sein. Wenn Sie den _DisplayName_-Parameter nicht verwenden, wird der Wert des _Name_-Parameters für den Anzeigenamen verwendet.
- Wenn Sie den _Parameter Alias_ nicht verwenden, wird die linke Seite des _Parameters MicrosoftOnlineServicesID_ für den Alias verwendet.
- Wenn Sie den _Parameter ExternalEmailAddress_ nicht verwenden, wird der _MicrosoftOnlineServicesID-Wert_ für die externe E-Mail-Adresse verwendet.

In diesem Beispiel wird ein E-Mail-Benutzer mit den folgenden Einstellungen erstellt:

- Der Name ist JeffreyZeng, und der Anzeigename ist Jeffrey Zeng.
- Der Vorname ist "Jeffrey" und der Nachname ist "Zeng".
- Der Alias ist "jeffreyz".
- Die externe E-Mail-Adresse ist "jzeng@tailspintoys.com".
- Der Kontoname ist jeffreyz@contoso.onmicrosoft.com.
- Das Kennwort lautet "Pa$$word1".

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-EOPMailUser](/powershell/module/exchange/new-eopmailuser).

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a>Verwenden der eigenständigen EOP PowerShell zum Ändern von E-Mail-Benutzern

Verwenden Sie die folgende Syntax, um vorhandene E-Mail-Benutzer in der eigenständigen EOP PowerShell zu ändern:

```powershell
Set-EOPMailUser -Identity <MailUserIdentity> [-Alias <Text>] [-DisplayName <Text>] [-EmailAddresses <ProxyAddressCollection>] [-MicrosoftOnlineServicesID <SmtpAddress>]
```

```powershell
Set-EOPUser -Identity <MailUserIdentity> [-City <Text>] [-Company <Text>] [-CountryOrRegion <CountryInfo>] [-Department <Text>] [-Fax <PhoneNumber>] [-FirstName <Text>] [-HomePhone <PhoneNumber>] [-Initials <Text>] [-LastName <Text>] [-MobilePhone <PhoneNumber>] [-Notes <Text>] [-Office <Text>] [-Phone <PhoneNumber>] [-PostalCode <String>] [-StateOrProvince <String>] [-StreetAddress <Tet>] [-Title <Text>] [-WebPage <Text>]
```

In diesem Beispiel wird die externe E-Mail-Adresse für Pilar Pinella festgelegt.

```PowerShell
Set-EOPMailUser -Identity "Pilar Pinilla" -EmailAddresses pilarp@tailspintoys.com
```

In diesem Beispiel wird die Eigenschaft "Company" für alle E-Mail-Benutzer in "Contoso" geändert.

```PowerShell
$Recip = Get-Recipient -RecipientType MailUser -ResultSize unlimited
$Recip | foreach {Set-EOPUser -Identity $_.Alias -Company Contoso}
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-EOPMailUser](/powershell/module/exchange/set-eopmailuser).

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a>Verwenden der eigenständigen EOP PowerShell zum Entfernen von E-Mail-Benutzern

Um E-Mail-Benutzer in eigenständiger EOP PowerShell zu entfernen, ersetzen Sie durch den Namen, Alias oder Kontonamen des E-Mail-Benutzers, und führen Sie den \<MailUserIdentity\> folgenden Befehl aus:

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

In diesem Beispiel wird der E-Mail-Benutzer für Jeffrey Zeng entfernt.

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-EOPMailUser](/powershell/module/exchange/remove-eopmailuser).

## <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

Verwenden Sie eines der folgenden Verfahren, um zu überprüfen, ob E-Mail-Benutzer im eigenständigen EOP erfolgreich erstellt, geändert oder entfernt wurden:

- Navigieren Sie in der Exchange Admin Center zu **Empfänger** \> **Kontakte**. Stellen Sie sicher, dass der E-Mail-Benutzer aufgeführt ist (oder nicht aufgeführt ist). Wählen Sie den E-Mail-Benutzer aus,  und zeigen Sie die Informationen im Detailbereich an, oder klicken Sie auf Bearbeiten (Symbol bearbeiten), ![ um die Einstellungen ](../../media/ITPro-EAC-AddIcon.png) anzuzeigen.

- Führen Sie in der eigenständigen EOP PowerShell den folgenden Befehl aus, um zu überprüfen, ob der E-Mail-Benutzer aufgeführt ist (oder nicht aufgeführt ist):

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- Ersetzen Sie durch den Namen, Alias oder Kontonamen des E-Mail-Benutzers, und führen Sie die folgenden Befehle aus, um \<MailUserIdentity\> die Einstellungen zu überprüfen:

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a>Verwalten von E-Mail-Benutzern durch Verzeichnissynchronisierung

In eigenständigem EOP ist die Verzeichnissynchronisierung für Kunden mit lokalem Active Directory verfügbar. Sie können diese Konten mit Azure Active Directory (Azure AD) synchronisieren, in dem Kopien der Konten in der Cloud gespeichert sind. Wenn Sie Ihre vorhandenen Benutzerkonten mit Azure Active Directory synchronisieren, können  Sie diese Benutzer im Bereich Empfänger im Exchange Admin Center (EAC) oder in der eigenständigen EOP PowerShell anzeigen.

**Hinweise**:

- Wenn Sie die Verzeichnissynchronisierung zum Verwalten Ihrer Empfänger verwenden, können Sie weiterhin Benutzer im Microsoft 365 Admin Center hinzufügen und verwalten, aber sie werden nicht mit Ihrem lokalen Active Directory synchronisiert. Dies liegt daran, dass die Verzeichnissynchronisierung nur Empfänger aus Ihrem lokalen Active Directory mit der Cloud synchronisiert.

- Für die folgenden Funktionen wird empfohlen, Verzeichnissynchronisierung zu verwenden:

  - **Outlook Listen** sicherer Absender und Listen blockierter Absender : Bei der Synchronisierung mit dem Dienst haben diese Listen Vorrang vor der Spamfilterung im Dienst. Auf diese Weise können Benutzer ihre eigene Liste sicherer Absender und die Liste blockierter Absender mit einzelnen Absender- und Domäneneinträgen verwalten. Weitere Informationen finden Sie unter [Konfigurieren der Einstellungen für Junk-E-Mails für Exchange Online-Postfächer](configure-junk-email-settings-on-exo-mailboxes.md).

  - **Directory Based Edge Blocking (DBEB)**: Weitere Informationen zu DBEB finden Sie unter [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking).

  - **Endbenutzerzugriff auf Quarantäne:** Für den Zugriff auf ihre isolierten Nachrichten müssen Empfänger über eine gültige Benutzer-ID und ein Kennwort im Dienst verfügen. Weitere Informationen zur Quarantäne finden Sie unter [Suchen und Veröffentlichen isolierter](find-and-release-quarantined-messages-as-a-user.md)Nachrichten als Benutzer.

  - **Nachrichtenflussregeln (auch** als Transportregeln bezeichnet): Wenn Sie die Verzeichnissynchronisierung verwenden, werden Ihre vorhandenen Active Directory-Benutzer und -Gruppen automatisch in die Cloud hochgeladen, und Sie können dann Nachrichtenflussregeln für bestimmte Benutzer und/oder Gruppen erstellen, ohne sie manuell in den Dienst hinzufügen zu müssen. Bitte beachten Sie, dass [dynamische Verteilungsgruppen](/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) nicht über die Verzeichnissynchronisierung synchronisiert werden können.

Erhalten Sie die erforderlichen Berechtigungen, und bereiten Sie sich auf die Verzeichnissynchronisierung vor, wie unter [Was ist Hybrididentität mit Azure Active Directory? beschrieben.](/azure/active-directory/hybrid/whatis-hybrid-identity)

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a>Synchronisieren von Verzeichnissen mit Azure Active Directory Verbinden (AAD Verbinden)

1. Aktivieren Sie die Verzeichnissynchronisierung, wie in [Azure AD Verbinden Synchronisierung beschrieben: Verstehen und Anpassen der Synchronisierung](/azure/active-directory/hybrid/how-to-connect-sync-whatis).

2. Installieren und Konfigurieren eines lokalen Computers zum Ausführen von AAD-Verbinden wie unter [Voraussetzungen für Azure AD Verbinden](/azure/active-directory/hybrid/how-to-connect-install-prerequisites).

3. [Wählen Sie aus, welcher Installationstyp für Azure AD Verbinden:](/azure/active-directory/hybrid/how-to-connect-install-select-installation)

   - [Express](/azure/active-directory/hybrid/how-to-connect-install-express)

   - [Custom](/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [Pass-Through-Authentifizierung](/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> Wenn Sie den Konfigurationsassistent für Azure Active Directory-Synchronisierungstool abschließen, wird in Ihrer Active Directory-Gesamtstruktur das Konto **MSOL_AD_SYNC** erstellt. Dieses Konto wird zum Lesen und Synchronisieren der lokalen Active Directory-Informationen verwendet. Damit die Verzeichnissynchronisierung ordnungsgemäß ausgeführt wird, müssen Sie sicherstellen, dass TCP 443 auf dem lokalen Verzeichnissynchronisierungsserver geöffnet ist.

Stellen Sie nach dem Konfigurieren der Synchronisierung sicher, dass Verbinden AAD ordnungsgemäß synchronisiert wird. Navigieren Sie in der Exchange-Verwaltungskonsole zu **Empfänger** \> **Kontakte**, und vergewissern Sie sich, dass die Liste der Benutzer in Ihrer lokalen Umgebung korrekt synchronisiert wird.