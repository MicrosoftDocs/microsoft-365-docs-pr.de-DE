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
description: Erfahren Sie, wie Sie E-Mail-Benutzer in Exchange Online Protection (EOP) verwalten, einschließlich Verzeichnissynchronisierung, EAC und PowerShell zum Verwalten von Benutzern.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6a0dc1c0c343be77c6d6f713ee6b68a08a4fe5be
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289913"
---
# <a name="manage-mail-users-in-standalone-eop"></a>Verwalten von E-Mail-Benutzern in EOP als eigenständige Lösung

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
-  [Exchange Online Protection als eigenständige Lösung](exchange-online-protection-overview.md)

In eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer sind E-Mail-Benutzer der grundlegende Benutzerkontotyp. Ein E-Mail-Benutzer verfügt über Kontoanmeldeinformationen in Ihrer eigenständigen EOP-Organisation und kann auf Ressourcen zugreifen (berechtigungen zugewiesen haben). Die E-Mail-Adresse eines E-Mail-Benutzers ist extern (z. B. in Ihrer lokalen E-Mail-Umgebung).

> [!NOTE]
> Wenn Sie einen E-Mail-Benutzer erstellen, ist das entsprechende Benutzerkonto im Microsoft 365 Admin Center verfügbar. Wenn Sie ein Benutzerkonto im Microsoft 365 Admin Center erstellen, können Sie dieses Konto nicht zum Erstellen eines E-Mail-Benutzers verwenden.

Die empfohlene Methode zum Erstellen und Verwalten von E-Mail-Benutzern [](#use-directory-synchronization-to-manage-mail-users) in EOP als eigenständige Lösung ist die Verwendung der Verzeichnissynchronisierung, wie im Abschnitt "Verwalten von E-Mail-Benutzern" weiter unten in diesem Artikel beschrieben.

Für eigenständige EOP-Organisationen mit einer kleinen Anzahl von Benutzern können Sie E-Mail-Benutzer im Exchange Admin Center (EAC) oder in der eigenständigen EOP PowerShell hinzufügen und verwalten, wie in diesem Artikel beschrieben.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Informationen zum Öffnen des Exchange Admin Centers (EAC) finden Sie im [Exchange Admin Center in EOP als eigenständige Lösung.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Wenn Sie E-Mail-Benutzer in EOP PowerShell erstellen, können Drosselungen auftreten. Außerdem verwenden die EOP -PowerShell-Cmdlets eine Batchverarbeitungsmethode, die zu einer Verteilungsverzögerung von ein paar Minuten führt, bevor die Ergebnisse der Befehle angezeigt werden.

- Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen in Exchange Online Protection die entsprechenden Berechtigungen zugewiesen werden. Insbesondere benötigen Sie die Rollen "Erstellung von E-Mail-Empfängern" **(Erstellen)** und "E-Mail-Empfänger" **(Ändern),** die standardmäßig den Rollengruppen "Organisationsverwaltung" (globale Administratoren) und "Empfängerverwaltung" zugewiesen sind.   Weitere Informationen finden Sie unter "Berechtigungen [in EOP als eigenständige](feature-permissions-in-eop.md) Lösung", und ändern Sie mithilfe der EAC die Liste der Mitglieder in [Rollengruppen.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Informationen zu Tastenkombinationen, die für die Verfahren in diesem Artikel gelten können, finden Sie unter Tastenkombinationen für das [Exchange Admin Center in Exchange Online.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Liegt ein Problem vor? Bitten Sie in den Exchange-Foren um Hilfe. Besuchen Sie das [Exchange Online Protection-Forum.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)

## <a name="use-the-exchange-admin-center-to-manage-mail-users"></a>Verwalten von E-Mail-Benutzern mithilfe des Exchange Admin Centers

### <a name="use-the-eac-to-create-mail-users"></a>Erstellen von E-Mail-Benutzern mithilfe der EAC

1. Wechseln Sie in der EAC zu **"Empfängerkontakte".** \> 

2. Klicken Sie **auf das Symbol "Neu** ![ ](../../media/ITPro-EAC-AddIcon.png) neu". Konfigurieren Sie **auf der Seite "Neuer** E-Mail-Benutzer", die geöffnet wird, die folgenden Einstellungen. Einstellungen, die mit einer <sup>\*</sup> gekennzeichnet sind, sind erforderlich.

   - **Vorname**

   - **Initialen:** Die mittlere Initiale der Person.

   - **Nachname**

   - <sup>\*</sup>**Anzeigename:** Standardmäßig werden in diesem Feld die Werte aus den Feldern **"Vorname",** **"Initialen"** und **"Nachname"** angezeigt. Sie können diesen Wert akzeptieren oder ändern. Der Wert sollte eindeutig sein und eine maximale Länge von 64 Zeichen haben.

   - <sup>\*</sup>**Alias:** Geben Sie einen eindeutigen Alias mit bis zu 64 Zeichen für den Benutzer ein.

   - **Externe E-Mail-Adresse:** Geben Sie die E-Mail-Adresse des Benutzers ein. Die Domäne sollte sich außerhalb Ihrer cloudbasierten Organisation befinden.

   - <sup>\*</sup>**Benutzer-ID:** Geben Sie das Konto ein, mit dem sich die Person beim Dienst anmeldet. Die Benutzer-ID besteht aus einem Benutzernamen auf der linken Seite des @-Symbols (@) und einer Domäne auf der rechten Seite.

   - <sup>\*</sup>**Neues Kennwort** und <sup>\*</sup> **Kennwort bestätigen:** Geben Sie das Kontokennwort ein, und geben Sie es erneut ein. Stellen Sie sicher, dass das Kennwort den Kennwortlängen-, Komplexitäts- und Verlaufsanforderungen Ihrer Organisation entspricht.

3. Wenn Sie fertig sind, klicken Sie auf **Speichern**, um den E-Mail-Benutzer zu erstellen.

### <a name="use-the-eac-to-modify-mail-users"></a>Ändern von E-Mail-Benutzern mithilfe der EAC

1. Navigieren Sie in der Exchange Admin Center zu **Empfänger** \> **Kontakte**.

2. Wählen Sie den E-Mail-Benutzer aus, den Sie ändern möchten, und klicken Sie dann auf **das** ![ Symbol "Bearbeiten". ](../../media/ITPro-EAC-AddIcon.png)

3. Klicken Sie auf der Seite mit den E-Mail-Benutzereigenschaften, die geöffnet wird, auf eine der folgenden Registerkarten, um Eigenschaften anzeigen oder ändern zu können.

   Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

#### <a name="general"></a>Allgemein

Verwenden Sie **die Registerkarte "Allgemein",** um grundlegende Informationen zum E-Mail-Benutzer ein- oder zu ändern.

- **Vorname**

- **Initialen**

- **Nachname**

- **Anzeigename:** Dieser Name wird im Adressbuch Ihrer Organisation, in den Zeilen "An:" und "Von:" in der E-Mail und in der Liste der Kontakte in der EAC angezeigt. Dieser Name darf keine Leerzeichen vor oder nach dem Anzeigenamen enthalten.

- **Benutzer-ID:** Dies ist das Konto des Benutzers in Microsoft 365. Sie können diesen Wert hier nicht ändern.

#### <a name="contact-information"></a>Kontaktinformationen

Auf der **Registerkarte "Kontaktinformationen"** können Sie die Kontaktinformationen des Benutzers anzeigen oder ändern. Die Informationen auf dieser Seite werden im Adressbuch angezeigt.

- **Street**
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
  - **Hinweise**

#### <a name="organization"></a>Organisation

Auf der **Registerkarte "Organisation"** können Sie detaillierte Informationen zur Rolle des Benutzers in der Organisation aufzeichnen.

- **Titel**
- **Abteilung**
- **Company**

### <a name="use-the-eac-to-remove-mail-users"></a>Entfernen von E-Mail-Benutzern mithilfe der EAC

1. Navigieren Sie in der Exchange Admin Center zu **Empfänger** \> **Kontakte**.

2. Wählen Sie den E-Mail-Benutzer aus,  den Sie entfernen möchten, und klicken Sie dann auf ![ "Entfernen". ](../../media/ITPro-EAC-RemoveIcon.gif)

## <a name="use-powershell-to-manage-mail-users"></a>Verwenden von PowerShell zum Verwalten von E-Mail-Benutzern

### <a name="use-standalone-eop-powershell-to-view-mail-users"></a>Verwenden der eigenständigen EOP PowerShell zum Anzeigen von E-Mail-Benutzern

Führen Sie den folgenden Befehl aus, um eine Übersichtsliste aller E-Mail-Benutzer in der eigenständigen EOP PowerShell zurückzukehren:

```powershell
Get-Recipient -RecipientType MailUser -ResultSize unlimited
```

Um detaillierte Informationen zu einem bestimmten E-Mail-Benutzer anzuzeigen, ersetzen Sie ihn durch den Namen, den Alias oder den Kontonamen des E-Mail-Benutzers, und führen Sie \<MailUserIdentity\> die folgenden Befehle aus:

```powershell
Get-Recipient -Identity <MailUserIdentity> | Format-List
```

```powershell
Get-User -Identity <MailUserIdentity> | Format-List
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-Recipient"](https://docs.microsoft.com/powershell/module/exchange/get-recipient) und ["Get-User".](https://docs.microsoft.com/powershell/module/exchange/get-user)

### <a name="use-standalone-eop-powershell-to-create-mail-users"></a>Verwenden der eigenständigen EOP PowerShell zum Erstellen von E-Mail-Benutzern

Verwenden Sie die folgende Syntax, um E-Mail-Benutzer in EOP PowerShell als eigenständige Lösung zu erstellen:

```powershell
New-EOPMailUser -Name "<UniqueName>" -MicrosoftOnlineServicesID <Account> -Password (ConvertTo-SecureString -String '<password>' -AsPlainText -Force) [-Alias <AliasValue>] [-DisplayName "<Display Name>"] [-ExternalEmailAddress <ExternalEmailAddress>] [-FirstName <Text>] [-Initials <Text>] [-LastName <Text>]
```

**Hinweise**:

- Der _Parameter "Name"_ ist erforderlich, hat eine maximale Länge von 64 Zeichen und muss eindeutig sein. Wenn Sie den _DisplayName_-Parameter nicht verwenden, wird der Wert des _Name_-Parameters für den Anzeigenamen verwendet.
- Wenn Sie den Parameter _"Alias"_ nicht verwenden, wird die linke Seite des _Parameters "MicrosoftOnlineServicesID"_ für den Alias verwendet.
- Wenn Sie den Parameter _"ExternalEmailAddress"_ nicht verwenden, wird der _Wert "MicrosoftOnlineServicesID"_ für die externe E-Mail-Adresse verwendet.

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

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/new-eopmailuser).

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

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/set-eopmailuser).

### <a name="use-standalone-eop-powershell-to-remove-mail-users"></a>Verwenden der eigenständigen EOP PowerShell zum Entfernen von E-Mail-Benutzern

Um E-Mail-Benutzer in der eigenständigen EOP PowerShell zu entfernen, ersetzen Sie ihn durch den Namen, den Alias oder den Kontonamen des E-Mail-Benutzers, und führen Sie den \<MailUserIdentity\> folgenden Befehl aus:

```PowerShell
Remove-EOPMailUser -Identity <MailUserIdentity\>
```

In diesem Beispiel wird der E-Mail-Benutzer für Jeffrey Zeng entfernt.

```PowerShell
Remove-EOPMailUser -Identity "Jeffrey Zeng"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-EOPMailUser](https://docs.microsoft.com/powershell/module/exchange/remove-eopmailuser).

## <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

Verwenden Sie eines der folgenden Verfahren, um sicherzustellen, dass Sie E-Mail-Benutzer in EOP als eigenständige Lösung erfolgreich erstellt, geändert oder entfernt haben:

- Navigieren Sie in der Exchange Admin Center zu **Empfänger** \> **Kontakte**. Stellen Sie sicher, dass der E-Mail-Benutzer aufgeführt ist (oder nicht aufgeführt ist). Wählen Sie den E-Mail-Benutzer aus,  und zeigen Sie die Informationen im Detailbereich an, oder klicken Sie auf ![ "Bearbeiten", ](../../media/ITPro-EAC-AddIcon.png) um die Einstellungen anzuzeigen.

- Führen Sie in der eigenständigen EOP PowerShell den folgenden Befehl aus, um zu überprüfen, ob der E-Mail-Benutzer aufgeführt ist (oder nicht aufgeführt ist):

  ```powershell
  Get-Recipient -RecipientType MailUser -ResultSize unlimited
  ```

- Ersetzen Sie den Namen, Alias oder Kontonamen des E-Mail-Benutzers, und führen Sie die folgenden Befehle \<MailUserIdentity\> aus, um die Einstellungen zu überprüfen:

  ```powershell
  Get-Recipient -Identity <MailUserIdentity> | Format-List
  ```

  ```powershell
  Get-User -Identity <MailUserIdentity> | Format-List
  ```

## <a name="use-directory-synchronization-to-manage-mail-users"></a>Verwalten von E-Mail-Benutzern durch Verzeichnissynchronisierung

In EOP als eigenständige Lösung ist die Verzeichnissynchronisierung für Kunden mit lokalem Active Directory verfügbar. Sie können diese Konten mit Azure Active Directory (Azure AD) synchronisieren, wo Kopien der Konten in der Cloud gespeichert werden. Wenn Sie Ihre vorhandenen Benutzerkonten mit Azure Active Directory  synchronisieren, können Sie diese Benutzer im Empfängerbereich des Exchange Admin Centers (EAC) oder in der eigenständigen EOP PowerShell anzeigen.

**Hinweise**:

- Wenn Sie die Verzeichnissynchronisierung zum Verwalten Ihrer Empfänger verwenden, können Sie weiterhin Benutzer im Microsoft 365 Admin Center hinzufügen und verwalten, diese werden jedoch nicht mit Ihrem lokalen Active Directory synchronisiert. Dies liegt daran, dass die Verzeichnissynchronisierung nur Empfänger aus Ihrem lokalen Active Directory mit der Cloud synchronisiert.

- Für die folgenden Funktionen wird empfohlen, Verzeichnissynchronisierung zu verwenden:

  - Listen sicherer Absender und **blockierter Absender** in Outlook: Bei der Synchronisierung mit dem Dienst haben diese Listen Vorrang vor der Spamfilterung im Dienst. Auf diese Weise können Benutzer ihre eigene Liste sicherer Absender und blockierter Absender mit einzelnen Absender- und Domäneneinträgen verwalten. Weitere Informationen finden Sie unter [Konfigurieren der Einstellungen für Junk-E-Mails für Exchange Online-Postfächer](configure-junk-email-settings-on-exo-mailboxes.md).

  - **Verzeichnisbasierte Edgeblockierung (Directory Based Edge Blocking, DBEB):** Weitere Informationen zu DBEB finden Sie unter Verwenden der verzeichnisbasierten Edgeblockierung zum Ablehnen von Nachrichten, die an [ungültige Empfänger gesendet werden.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)

  - **Endbenutzerzugriff auf Quarantäne:** Für den Zugriff auf ihre isolierten Nachrichten müssen Empfänger über eine gültige Benutzer-ID und ein Kennwort im Dienst verfügen. Weitere Informationen zum Isolieren finden Sie unter "Suchen und Veröffentlichen von [Isolierten Nachrichten als Benutzer".](find-and-release-quarantined-messages-as-a-user.md)

  - **Nachrichtenflussregeln (auch** als Transportregeln bezeichnet): Wenn Sie die Verzeichnissynchronisierung verwenden, werden Ihre vorhandenen Active Directory-Benutzer und -Gruppen automatisch in die Cloud hochgeladen, und Sie können dann Nachrichtenflussregeln erstellen, die für bestimmte Benutzer und/oder Gruppen gelten, ohne sie manuell in den Dienst hinzufügen zu müssen. Bitte beachten Sie, dass [dynamische Verteilungsgruppen](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) nicht über die Verzeichnissynchronisierung synchronisiert werden können.

Erhalten Sie die erforderlichen Berechtigungen, und bereiten Sie sich auf die Verzeichnissynchronisierung vor, wie in ["Was ist hybride Identität mit Azure Active Directory" beschrieben?](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity)

### <a name="synchronize-directories-with-azure-active-directory-connect-aad-connect"></a>Synchronisieren von Verzeichnissen mit Azure Active Directory Connect (AAD Connect)

1. Aktivieren Sie die Verzeichnissynchronisierung, wie in [der Azure AD Connect-Synchronisierung beschrieben: Verstehen und Anpassen der Synchronisierung.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)

2. Installieren und konfigurieren Sie einen lokalen Computer zum Ausführen von AAD Connect, wie unter Voraussetzungen [für Azure AD Connect beschrieben.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)

3. [Wählen Sie aus, welcher Installationstyp für Azure AD Connect verwendet werden soll:](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-select-installation)

   - [Express](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express)

   - [Custom](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-custom)

   - [Pass-Through-Authentifizierung](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-quick-start)

> [!IMPORTANT]
> Wenn Sie den Konfigurationsassistent für Azure Active Directory-Synchronisierungstool abschließen, wird in Ihrer Active Directory-Gesamtstruktur das Konto **MSOL_AD_SYNC** erstellt. Dieses Konto wird zum Lesen und Synchronisieren der lokalen Active Directory-Informationen verwendet. Damit die Verzeichnissynchronisierung ordnungsgemäß ausgeführt wird, müssen Sie sicherstellen, dass TCP 443 auf dem lokalen Verzeichnissynchronisierungsserver geöffnet ist.

Stellen Sie nach dem Konfigurieren der Synchronisierung sicher, dass AAD Connect ordnungsgemäß synchronisiert wird. Navigieren Sie in der Exchange-Verwaltungskonsole zu **Empfänger** \> **Kontakte**, und vergewissern Sie sich, dass die Liste der Benutzer in Ihrer lokalen Umgebung korrekt synchronisiert wird.
