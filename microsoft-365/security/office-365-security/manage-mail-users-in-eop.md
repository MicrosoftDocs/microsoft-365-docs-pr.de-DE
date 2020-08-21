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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 4bfaf2ab-e633-4227-8bde-effefb41a3db
description: In diesem Artikel erfahren Sie, wie Sie e-Mail-Benutzer in Exchange Online Protection (EoP) verwalten, einschließlich der Verwendung der Verzeichnissynchronisierung, der Exchange-Verwaltungskonsole und PowerShell zum Verwalten von Benutzern.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 64b7effadd96b6dc025677139c4303acd538dadb
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827075"
---
# <a name="manage-mail-users-in-standalone-eop"></a>Verwalten von E-Mail-Benutzern in EOP als eigenständige Lösung

In Organisationen mit eigenständigen Exchange Online Schutz (EoP) ohne Exchange Online Postfächer sind e-Mail-Benutzer der grundlegende Typ des Benutzerkontos. Ein e-Mail-Benutzer verfügt über Kontoanmeldeinformationen in ihrer eigenständigen EoP-Organisation und kann auf Ressourcen zugreifen (Berechtigungen zugewiesen). Die e-Mail-Adresse eines e-Mail-Benutzers ist extern (beispielsweise in Ihrer lokalen e-Mail-Umgebung).

> [!NOTE]
> Wenn Sie einen e-Mail-Benutzer erstellen, ist das entsprechende Benutzerkonto im Microsoft 365 Admin Center verfügbar. Wenn Sie ein Benutzerkonto im Microsoft 365 Admin Center erstellen, können Sie dieses Konto nicht verwenden, um einen e-Mail-Benutzer zu erstellen.

Die empfohlene Methode zum Erstellen und Verwalten von e-Mail-Benutzern in eigenständigen EoP besteht in der Verwendung der Verzeichnissynchronisierung, wie im Abschnitt [Verwenden der Verzeichnissynchronisierung zum Verwalten von e-Mail-Benutzern](#use-directory-synchronization-to-manage-mail-users) weiter unten in diesem Thema beschrieben.

Für eigenständige EoP-Organisationen mit einer kleinen Anzahl von Benutzern können Sie e-Mail-Benutzer in der Exchange-Verwaltungskonsole (EAC) oder in der eigenständigen EoP-PowerShell hinzufügen und verwalten, wie in diesem Thema beschrieben.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Informationen zum Öffnen des Exchange Admin Center (EAC) finden Sie unter [Exchange Admin Center in Standalone EoP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Wenn Sie e-Mail-Benutzer in EoP PowerShell erstellen, stoßen Sie möglicherweise auf Drosselung. Außerdem verwenden die EoP-PowerShell-Cmdlets eine Batch Verarbeitungsmethode, die zu einer Ausbreitungs Verzögerung von ein paar Minuten führt, bevor die Ergebnisse der Befehle sichtbar sind.

- Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Insbesondere benötigen Sie die Rollen für die Erstellung von e-Mail-Empfängern (Create) und e-Mail-Empfänger (ändern), die standardmäßig den Rollengruppenmitglied (globale Administratoren) und RecipientManagement zugewiesen sind. Weitere Informationen finden Sie unter [Berechtigungen in eigenständigen EoP](feature-permissions-in-eop.md) und [Verwenden der Exchange-Verwaltungskonsole ändern der Liste der Mitglieder in Rollengruppen](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Informationen zu Tastenkombinationen, die möglicherweise für die Verfahren in diesem Thema gelten, finden Sie unter [Tastenkombinationen für das Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Liegt ein Problem vor? Bitten Sie in den Exchange-Foren um Hilfe. Besuchen Sie das [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) -Forum.

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a>Verwalten von e-Mail-Benutzern mithilfe der Exchange-Verwaltungskonsole

### <a name="use-the-eac-to-create-mail-users"></a>Erstellen von e-Mail-Benutzern mithilfe der Exchange-Verwaltungskonsole

1. Wechseln Sie in der Exchange-Verwaltungskonsole zu **Empfänger** \> **Kontakte**

2. Klicken Sie auf **Neues** ![ Neues Symbol ](../../media/ITPro-EAC-AddIcon.png) . Konfigurieren Sie auf der Seite **neuer e-Mail-Benutzer** , die geöffnet wird, die folgenden Einstellungen. Mit einem markierte Einstellungen <sup>\*</sup> sind erforderlich.

   - **Vorname**

   - **Initialen**: der mittlere Initialwert der Person.

   - **Nachname**

   - <sup>\*</sup>**Anzeigename**: Standardmäßig werden in diesem Feld die Werte aus den Feldern **Vorname**, **Initialen**und **Nachname** angezeigt. Sie können diesen Wert akzeptieren oder ändern. Der Wert sollte eindeutig sein und hat eine maximale Länge von 64 Zeichen.

   - <sup>\*</sup>**Alias**: Geben Sie einen eindeutigen Alias mit bis zu 64 Zeichen für den Benutzer ein.

   - **Externe e-Mail-Adresse**: Geben Sie die e-Mail-Adresse des Benutzers ein. Die Domäne sollte sich außerhalb ihrer cloudbasierten Organisation befinden.

   - <sup>\*</sup>**Benutzer-ID**: Geben Sie das Konto ein, mit dem sich die Person beim Dienst anmelden wird. Die Benutzer-ID besteht aus einem Benutzernamen auf der linken Seite des @-Symbols (@) und einer Domäne auf der rechten Seite.

   - <sup>\*</sup>**Neues Kennwort** und <sup>\*</sup> **Kennwort bestätigen**: Geben Sie das Kontokennwort ein, und geben Sie es erneut ein. Stellen Sie sicher, dass das Kennwort den Anforderungen in Bezug auf Länge, Komplexität und Verlauf Ihrer Organisation entspricht.

3. Wenn Sie fertig sind, klicken Sie auf **Speichern**, um den E-Mail-Benutzer zu erstellen.

### <a name="use-the-eac-to-modify-mail-users"></a>Ändern von e-Mail-Benutzern mithilfe der Exchange-Verwaltungskonsole

1. Navigieren Sie in der Exchange Admin Center zu **Empfänger** \> **Kontakte**.

2. Wählen Sie den e-Mail-Benutzer aus, den Sie ändern möchten, und klicken Sie dann auf Bearbeitungssymbol **Bearbeiten** ![ ](../../media/ITPro-EAC-AddIcon.png) .

3. Klicken Sie auf der Seite Eigenschaften von e-Mail-Benutzer, die geöffnet wird, auf eine der folgenden Registerkarten, um Eigenschaften anzuzeigen oder zu ändern.

   Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

#### <a name="general"></a>Allgemein

Verwenden Sie die Registerkarte **Allgemein** , um grundlegende Informationen zum e-Mail-Benutzer anzuzeigen oder zu ändern.

- **Vorname**

- **Initialen**

- **Nachname**

- **Anzeigename**: dieser Name wird im Adressbuch Ihrer Organisation, in den Zeilen "an:" und "von:" in e-Mail und in der Liste der Kontakte in der Exchange-Verwaltungskonsole angezeigt. Dieser Name darf keine Leerzeichen vor oder nach dem Anzeigenamen enthalten.

- **Benutzer-ID**: Dies ist das Konto des Benutzers in Microsoft 365. Sie können diesen Wert hier nicht ändern.

#### <a name="contact-information"></a>Kontaktinformationen

Verwenden Sie die Registerkarte **Kontaktinformationen** , um die Kontaktinformationen des Benutzers anzuzeigen oder zu ändern. Die Informationen auf dieser Seite werden im Adressbuch angezeigt.

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

#### <a name="organization"></a>Organization (Organisation)

Verwenden Sie die Registerkarte **Organisation** , um detaillierte Informationen zur Rolle des Benutzers in der Organisation aufzuzeichnen.

- **Titel**
- **Abteilung**
- **Company**

### <a name="use-the-eac-to-remove-mail-users"></a>Entfernen von e-Mail-Benutzern mithilfe der Exchange-Verwaltungskonsole

1. Navigieren Sie in der Exchange Admin Center zu **Empfänger** \> **Kontakte**.

2. Wählen Sie den e-Mail-Benutzer aus, den Sie entfernen möchten, und klicken Sie dann auf entfernen-Symbol **Entfernen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .

## <a name="use-powershell-to-manage-mail-users"></a>Verwenden von PowerShell zum Verwalten von e-Mail-Benutzern

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a>Verwenden von eigenständigen EoP PowerShell zum Anzeigen von e-Mail-Benutzern

Führen Sie den folgenden Befehl aus, um eine Zusammenfassungsliste aller e-Mail-Benutzer in eigenständiger EoP PowerShell zurückzugeben:

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

Wenn Sie detaillierte Informationen zu einem bestimmten e-Mail-Benutzer anzeigen möchten, ersetzen Sie \<MailUserIdentity\> durch den Namen, den Alias oder den Kontonamen des e-Mail-Benutzers, und führen Sie die folgenden Befehle aus:

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) und [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user).

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a>Verwenden eigenständiger EoP PowerShell zum Erstellen von e-Mail-Benutzern

Verwenden Sie die folgende Syntax, um e-Mail-Benutzer in eigenständiger EoP PowerShell zu erstellen:

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

**Hinweise**:

- Der _Name_ -Parameter ist erforderlich, hat eine maximale Länge von 64 Zeichen und muss eindeutig sein. Wenn Sie den _DisplayName_-Parameter nicht verwenden, wird der Wert des _Name_-Parameters für den Anzeigenamen verwendet.
- Wenn Sie den Parameter _Alias_ nicht verwenden, wird die linke Seite des _MicrosoftOnlineServicesID_ -Parameters für den Alias verwendet.
- Wenn Sie den Parameter _ExternalEmailAddress_ nicht verwenden, wird der _MicrosoftOnlineServicesID_ -Wert für die externe e-Mail-Adresse verwendet.

In diesem Beispiel wird ein e-Mail-Benutzer mit den folgenden Einstellungen erstellt:

- Der Name lautet JeffreyZeng, und der Anzeigename ist Jeffrey Zeng.
- Der Vorname ist "Jeffrey" und der Nachname ist "Zeng".
- Der Alias ist "jeffreyz".
- Die externe E-Mail-Adresse ist "jzeng@tailspintoys.com".
- Der Konto Name lautet jeffreyz@contoso.onmicrosoft.com.
- Das Kennwort lautet "Pa$$word1".

```PowerShell
New-EOPMailUser -Name JeffreyZeng -MicrosoftOnlineServicesID jeffreyz@contoso.onmicrosoft.com -Password (ConvertTo-SecureString -String 'Pa$$word1' -AsPlainText -Force) -ExternalEmailAddress jeffreyz@tailspintoys.com -DisplayName "Jeffrey Zeng" -Alias jeffreyz -FirstName Jeffrey -LastName Zeng
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).

### <a name="use-standalone-eop-powershell-to-modify-mail-users"></a>Verwenden eigenständiger EoP PowerShell zum Ändern von e-Mail-Benutzern

Verwenden Sie die folgende Syntax, um vorhandene e-Mail-Benutzer in eigenständiger EoP PowerShell zu ändern:

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

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a>Verwenden eigenständiger EoP PowerShell zum Entfernen von e-Mail-Benutzern

Wenn Sie e-Mail-Benutzer in eigenständiger EoP PowerShell entfernen möchten, ersetzen Sie \<MailUserIdentity\> durch den Namen, den Alias oder den Kontonamen des e-Mail-Benutzers, und führen Sie den folgenden Befehl aus:

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

In diesem Beispiel wird der e-Mail-Benutzer für Jeffrey Zeng entfernt.

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).

## <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

Verwenden Sie eines der folgenden Verfahren, um zu überprüfen, ob Sie e-Mail-Benutzer in eigenständigen EoP erfolgreich erstellt, geändert oder entfernt haben:

- Navigieren Sie in der Exchange Admin Center zu **Empfänger** \> **Kontakte**. Stellen Sie sicher, dass der e-Mail-Benutzer aufgelistet ist (oder nicht aufgeführt ist). Wählen Sie den e-Mail-Benutzer aus, und zeigen Sie die Informationen im Detailbereich an, oder klicken Sie auf Bearbeitungssymbol **Bearbeiten** ![ ](../../media/ITPro-EAC-AddIcon.png) , um die Einstellungen anzuzeigen.

- Führen Sie in eigenständiger EoP PowerShell den folgenden Befehl aus, um zu überprüfen, ob der e-Mail-Benutzer aufgelistet ist (oder nicht aufgeführt ist):

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- Ersetzen \<MailUserIdentity\> Sie durch den Namen, den Alias oder den Kontonamen des e-Mail-Benutzers, und führen Sie die folgenden Befehle aus, um die Einstellungen zu überprüfen:

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a>Verwalten von E-Mail-Benutzern durch Verzeichnissynchronisierung

In eigenständigen EoP steht die Verzeichnissynchronisierung für Kunden mit lokalem Active Directory zur Verfügung. Sie können diese Konten mit Azure Active Directory (Azure AD) synchronisieren, wobei Kopien der Konten in der Cloud gespeichert werden. Wenn Sie Ihre vorhandenen Benutzerkonten mit Azure Active Directory synchronisieren, können Sie diese Benutzer im Bereich **Empfänger** des Exchange Admin Centers (EAC) oder in der eigenständigen EoP PowerShell anzeigen.

**Hinweise**:

- Wenn Sie die Verzeichnissynchronisierung zum Verwalten Ihrer Empfänger verwenden, können Sie dennoch Benutzer im Microsoft 365 Admin Center hinzufügen und verwalten, Sie werden jedoch nicht mit Ihrer lokalen Active Directory synchronisiert. Dies liegt daran, dass die Verzeichnissynchronisierung nur Empfänger von Ihrem lokalen Active Directory zur Cloud synchronisiert.

- Für die folgenden Funktionen wird empfohlen, Verzeichnissynchronisierung zu verwenden:

  - Listen **sicherer Absender in Outlook und blockierte Absender**: Wenn Sie mit dem Dienst synchronisiert werden, haben diese Listen Vorrang vor der Spamfilterung im Dienst. Dadurch können Benutzer ihre eigene Liste sicherer Absender und blockierte Absender mit einzelnen Absender-und Domäneneinträgen verwalten. Weitere Informationen finden Sie unter [Konfigurieren der Einstellungen für Junk-E-Mails für Exchange Online-Postfächer](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes).

  - **Verzeichnisbasierte Edge-Blockierung (Blockierung)**: Weitere Informationen zu Blockierung finden Sie unter [Verwenden der verzeichnisbasierten Edge-Blockierung zum ablehnen von Nachrichten, die an ungültige Empfänger gesendet](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)werden.

  - **Endbenutzer Zugriff auf Quarantäne**: für den Zugriff auf Ihre isolierten Nachrichten benötigen Empfänger eine gültige Benutzer-ID und ein Kennwort im Dienst. Weitere Informationen zur Quarantäne finden Sie unter [Suchen und Freigeben von Nachrichten in Quarantäne als Benutzer](https://docs.microsoft.com/microsoft-365/security/office-365-security/find-and-release-quarantined-messages-as-a-user).

  - **Nachrichtenfluss Regeln (auch als Transportregeln bezeichnet)**: Wenn Sie die Verzeichnissynchronisierung verwenden, werden die vorhandenen Active Directory Benutzer und Gruppen automatisch in die Cloud hochgeladen, und Sie können dann Nachrichtenfluss Regeln erstellen, die auf bestimmte Benutzer und/oder Gruppen abzielen, ohne diese manuell im Dienst hinzufügen zu müssen. Bitte beachten Sie, dass [dynamische Verteilungsgruppen](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) nicht über die Verzeichnissynchronisierung synchronisiert werden können.

Rufen Sie die erforderlichen Berechtigungen ab, und bereiten Sie die Verzeichnissynchronisierung vor, wie unter [Was ist Hybrid Identität mit Azure Active Directory beschrieben?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity).

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a>Synchronisieren von Verzeichnissen mit Azure Active Directory Connect (AAD Connect)

1. Aktivieren Sie die Verzeichnissynchronisierung, wie unter [Azure AD Connect Sync: Understand and Customize Synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)beschrieben.

2. Installieren und konfigurieren Sie einen lokalen Computer für die Ausführung von Aad Connect, wie unter [Voraussetzungen für Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)beschrieben.

3. [Wählen Sie den Installationstyp aus, der für Azure AD Connect verwendet werden soll](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation):

   - [Express](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [Custom](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [Pass-Through-Authentifizierung](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> Wenn Sie den Konfigurationsassistent für Azure Active Directory-Synchronisierungstool abschließen, wird in Ihrer Active Directory-Gesamtstruktur das Konto **MSOL_AD_SYNC** erstellt. Dieses Konto wird zum Lesen und Synchronisieren der lokalen Active Directory-Informationen verwendet. Damit die Verzeichnissynchronisierung ordnungsgemäß ausgeführt wird, müssen Sie sicherstellen, dass TCP 443 auf dem lokalen Verzeichnissynchronisierungsserver geöffnet ist.

Vergewissern Sie sich nach dem Konfigurieren der Synchronisierung, dass Aad Connect ordnungsgemäß synchronisiert wird. Navigieren Sie in der Exchange-Verwaltungskonsole zu **Empfänger** \> **Kontakte**, und vergewissern Sie sich, dass die Liste der Benutzer in Ihrer lokalen Umgebung korrekt synchronisiert wird.
