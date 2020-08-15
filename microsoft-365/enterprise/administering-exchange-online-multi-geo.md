---
title: Verwalten von Exchange Online-Postfächern in einer Multi-Geo-Umgebung
ms.reviewer: adwood
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
localization_priority: normal
description: Hier erfahren Sie, wie Sie Exchange Online Multi-Geo-Einstellungen in Ihrer Microsoft 365-Umgebung mit PowerShell verwalten.
ms.openlocfilehash: 645d48066ca02dbf3480e20ae30dc187f84293cf
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690281"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a>Verwalten von Exchange Online-Postfächern in einer Multi-Geo-Umgebung

Remote-PowerShell ist erforderlich, um Multi-Geo-Eigenschaften in Ihrer Microsoft 365-Umgebung anzuzeigen und zu konfigurieren. Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

Sie benötigen das [Microsoft Azure Active Directory PowerShell-Modul](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 oder später in v1.x, um die **PreferredDataLocation**-Eigenschaft an Benutzerobjekten anzuzeigen. Benutzerobjekte, die über AAD Connect mit AAD synchronisiert werden, können ihren **PreferredDataLocation**-Wert direkt über AAD PowerShell ändern lassen. Nur-Cloud-Benutzerobjekte können über AAD PowerShell geändert werden. Wie Sie eine Verbindung mit Azure AD PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit PowerShell](connect-to-microsoft-365-powershell.md).

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a>Stellen Sie über Exchange Online PowerShell eine direkte Verbindung zu einem geografischem Standort her.

Normalerweise verbindet sich Exchange Online PowerShell mit dem zentralen geografischen Standort. Sie können sich aber auch direkt mit geografischen Satellitenstandorten verbinden. Aufgrund von Leistungsverbesserungen empfehlen wir, sich direkt mit dem geografischen Satellitenstandort zu verbinden, wenn Sie nur Benutzer an diesem geografischem Standort verwalten.

Um eine Verbindung zu einem bestimmten geografischen Standort herzustellen, unterscheidet sich der Parameter *ConnectionUri* von den üblichen Verbindungsanweisungen. Die restlichen Befehle und Werte sind identisch. Das sind die Schritte:

1. Öffnen Sie auf Ihrem lokalen Computer Windows PowerShell und führen Sie den folgenden Befehl aus:

   ```powershell
   $UserCredential = Get-Credential
   ```

   Geben Sie im Dialogfeld **Bei Windows PowerShell anmelden** Ihr Geschäfts-, Schul- oder Unikonto und das Kennwort ein und klicken Sie dann auf **OK**.

2. Ersetzen Sie `<emailaddress>` mit der E-Mail-Adresse des ** jedes ** Postfach im geografischen Zielstandort und führen den folgenden Befehl aus. Ihre Berechtigungen für das Postfach und die Beziehung zu Ihren Anmeldeinformationen in Schritt 1 sind kein Faktor, die E-Mail-Adresse weist Exchange Online einfach darauf hin, wo eine Verbindung hergestellt werden sollte.
  
   ```powershell
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell?email=<emailaddress> -Credential $UserCredential -Authentication  Basic -AllowRedirection
   ```

   Wenn beispielsweise olga@contoso.onmicrosoft.com die E-Mail-Adresse eines gültigen Postfachs an dem geografischen Standort ist, den Sie verbinden möchten, führen Sie den folgenden Befehl aus:

   ```powershell
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com -Credential $UserCredential -Authentication  Basic -AllowRedirection
   ```

3. Führen Sie den folgenden Befehl aus:

    ```powershell
    Import-PSSession $Session
    ```

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a>Anzeigen der verfügbaren geografischen Standorte, die in Ihrer Exchange Online-Organisation konfiguriert sind

Um die Liste der konfigurierten geografischen Standorte in Microsoft 365 Multi-Geo anzuzeigen, führen Sie den folgenden Befehl in Exchange Online PowerShell aus:

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a>Anzeigen des zentralen geografischen Standorts für Ihre Exchange Online-Organisation

Um den zentralen geografischen Standort Ihres Mandanten anzuzeigen, führen Sie den folgenden Befehl in Exchange Online PowerShell aus:

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a>Suchen des geografischen Standorts eines Postfachs

Die **Get-Mailbox** cmdlet in Exchange Online PowerShell zeigt die folgenden Multi-Geo-bezogenen Eigenschaften für Postfächer:

- **Datenbank**: Die ersten 3 Buchstaben des Datenbanknamens entsprechen dem Geo-Code, der Ihnen mitteilt, wo sich das Postfach derzeit befindet. Für Online-Archivpostfächer sollte die **Archivdatenbank** verwendet werden.

- **MailboxRegion**: Gibt den geografischen Standortcode an, der vom Administrator festgelegt wurde (synchronisiert von **PreferredDataLocation** in Azure AD).

- **MailboxRegionLastUpdateTime**: Gibt an, wann MailboxRegion zuletzt aktualisiert wurde (automatisch oder manuell).

Um diese Eigenschaften für ein Postfach anzuzeigen, verwenden Sie die folgende Syntax:

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

Um beispielsweise die geografische Information für das Postfach chris@contoso.onmicrosoft.com anzuzeigen, führen Sie den folgenden Befehl aus:

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

Die Ausgabe des Befehls sieht wie folgt aus:

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> Wenn der Geo-Standortcode im Datenbanknamen nicht mit dem **MailboxRegion** -Wert übereinstimmt, wird das Postfach automatisch in eine Verschiebungs Warteschlange verschoben und an den durch den **MailboxRegion** -Wert angegebenen geografischen Speicherort verschoben (Exchange Online sucht nach einem Missverhältnis zwischen diesen Eigenschaftswerten).

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a>Verschieben eines bereits vorhandenen Nur-Cloud-Postfachs an einen bestimmten geografischen Standort

Ein Nur-Cloud-Benutzer ist ein Benutzer, der nicht über AAD Connect mit dem Mandanten synchronisiert ist. Dieser Benutzer wurde direkt in Azure AD erstellt. Verwenden der **Get-MsolUser** und **Set-MsolUser**-Cmdlets in Azure AD-Modul für Windows PowerShell zum Anzeigen oder Angeben des geografischen Standorts, wo ein Nur-Cloud-Postfach eines Benutzers gespeichert wird.

Um den **PreferredDataLocation**-Wert für einen Benutzer anzuzeigen, verwenden Sie diese Syntax in Azure AD PowerShell:

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

Um z. B. den **PreferredDataLocation**-Wert für den Benutzer michelle@contoso.onmicrosoft.com anzuzeigen, führen Sie den folgenden Befehl aus:

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

Um den **PreferredDataLocation**-Wert für ein Nur-Cloud-Benutzerobjekt zu ändern, verwenden Sie die folgende Syntax in Azure AD PowerShell:

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

Um z. B. den **PreferredDataLocation**-Wert auf die Geodaten der  Europäischen Union (EUR) für den Benutzer michelle@contoso.onmicrosoft.com festzulegen, führen Sie den folgenden Befehl aus:

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
> - Wie bereits erwähnt, können Sie dieses Verfahren nicht für synchronisierte Benutzerobjekte aus lokalen Active Directory verwenden. Sie müssen den **PreferredDataLocation**-Wert in Active Directory ändern und mithilfe von AAD Connect synchronisieren. Weitere Informationen finden Sie unter [Azure Active Directory Connect-Synchronisierung: Konfigurieren von bevorzugten Datenspeicherorten für Microsoft 365-Ressourcen](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).
> 
> - Wie lange es dauert, ein Postfach an einen neuen geografischen Standort zu verschieben, hängt von mehreren Faktoren ab:
> 
>   - Der Größe und Art des Postfachs.
> 
>   - Der Anzahl der zu verschiebenden Postfächern.
> 
>   - Der Verfügbarkeit von Umzugsressourcen.

### <a name="move-disabled-mailboxes-that-are-on-litigation-hold"></a>Dem Verschieben deaktivierter Postfächer, die einem Beweissicherungsverfahren unterliegen

Deaktivierte Postfächer, die einem Beweissicherungsverfahren unterliegen und für eDiscovery-Zwecke aufbewahrt werden, können nicht verschoben werden, indem ihr **PreferredDataLocation**-Wert in einen deaktivierten Status geändert wird. So verschieben Sie ein deaktiviertes Postfach, das einem Beweissicherungsverfahren unterliegt:

1. Weisen Sie dem Postfach vorübergehend eine Lizenz zu.

2. Ändern Sie die **PreferredDataLocation**.

3. Entfernen Sie die Lizenz vom Postfach, nachdem es an den ausgewählten geografischen Standort verschoben wurde, um es wieder in den deaktivierten Status zu versetzen.

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a>Neue Cloud-Postfächer an einem bestimmten geografischen Standort erstellen

Um ein neues Postfach an einem bestimmten geografischen Standort zu erstellen, müssen Sie einen der folgenden Schritte ausführen:

- Konfigurieren Sie den **PreferredDataLocation**-Wert wie im vorherigen Abschnitt beschrieben, *bevor* das Postfach in Exchange Online erstellt wird. Konfigurieren Sie z. B. den **PreferredDataLocation**-Wert für einen Benutzer, bevor Sie eine Lizenz zuweisen.

- Weisen Sie eine Lizenz zu, während Sie gleichzeitig den **PreferredDataLocation**-Wert festlegen.

Um einen neuen, nur für die Cloud lizenzierten Benutzer (nicht AAD Connect synchronisiert) an einem bestimmten geografischen Standorts zu erstellen, verwenden Sie die folgende Syntax in Azure AD PowerShell:

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

In diesem Beispiel erstellen Sie ein neues Benutzerkonto für Elizabeth Brunner mit den folgenden Werten:

- Benutzerprinzipalname: ebrunner@contoso.onmicrosoft.com

- Vorname: Elizabeth

- Nachname: Brunner

- Anzeigename: Elizabeth Brunner

- Kennwort: nach dem Zufallsprinzip generiert und in den Ergebnissen des Befehls angezeigt (da wir nicht den Parameter *Kennwort* verwenden)

- Lizenz: `contoso:ENTERPRISEPREMIUM` (E5)

- Standort: Australien (AUS)

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

Weitere Informationen zum Erstellen neuer Benutzerkonten und Suchen von LicenseAssignment-Werten in Azure AD PowerShell finden Sie unter [Erstellen von Benutzerkonten mit PowerShell](create-user-accounts-with-microsoft-365-powershell.md) und [Anzeigen von Lizenzen und Diensten in PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).

> [!NOTE]
> Wenn Sie Exchange Online PowerShell verwenden, um ein Postfach zu aktivieren, und das Postfach direkt in der Geo erstellt werden muss, die in **PreferredDataLocation** angegeben ist, müssen Sie ein Exchange Online-Cmdlet wie **Enable-Mailbox** oder **New-Mailbox** direkt gegen den Cloud-Dienst verwenden. Wenn Sie das lokale Exchange-Cmdlet **Enable-RemoteMailbox** verwenden, wird das Postfach an dem geografischen Standort erstellt.

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a>Integrieren vorhandener lokaler Postfächer an einem bestimmten geografischen Standort

Sie können die standardmäßigen Onboarding-Tools und -Prozesse verwenden, um ein Postfach von einer lokalen Exchange-Organisation zu Exchange Online zu migrieren, einschließlich des [Migrations-Dashboards im EAC](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331) und des [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch)-Cmdlets in Exchange Online PowerShell.

Der erste Schritt besteht in der Überprüfung, ob für jedes zu integrierende Postfach ein Benutzerobjekt vorhanden ist und ob der korrekte **PreferredDataLocation**-Wert in Azure Active Directory konfiguriert ist. Die Onboarding-Tools berücksichtigen den **PreferredDataLocation**-Wert und migrieren die Postfächer direkt an den angegebenen geografischen Standorte.

Oder Sie können die folgenden Schritte ausführen, um Postfächer direkt an einem bestimmten geografischen Standort mit dem [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest)-Cmdlet in Exchange Online PowerShell zu integrieren.

1. Überprüfen Sie, ob das Benutzerobjekt für jedes zu integrierende Postfach vorhanden ist und ob **PreferredDataLocation** in Azure AD auf den gewünschten Wert festgelegt ist. Der Wert von **PreferredDataLocation** wird mit dem Attribut **MailboxRegion** des entsprechenden E-Mail-Benutzerobjekts in Exchange Online synchronisiert.

2. Verbinden Sie sich direkt mit dem spezifischen Satellitenstandort anhand der Verbindungsanweisungen weiter oben in diesem Thema.

3. Speichern Sie in Exchange Online PowerShell die lokalen Administrator-Anmeldeinformationen, mit denen eine Postfachmigration in einer Variablen durchgeführt wird, indem Sie den folgenden Befehl ausführen:

   ```powershell
   $RC = Get-Credential
   ```

4. Erstellen Sie in Exchange Online PowerShell einen neuen **New-MoveRequest**, ähnlich wie im folgenden Beispiel:

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. Wiederholen Sie Schritt 4 für jedes Postfach, das Sie vom lokalen Exchange zum geografischen Satellitenstandort migrieren müssen, mit dem Sie derzeit verbunden sind.

6. Wenn Sie zusätzliche Postfächer an einen anderen geografischen Satellitenstandort migrieren müssen, wiederholen Sie die Schritte 2 bis 4 für jeden einzelnen Satellitenstandort.

## <a name="multi-geo-reporting"></a>Multi-Geo-Berichterstellung

**Multi-Geo-Verwendungsberichte** im Admin Center von Microsoft 365 zeigen die Anzahl der Benutzer nach geografischem Standort an. Der Bericht zeigt die Verteilung der Benutzer für den aktuellen Monat und bietet Verlaufsdaten für die letzten 6 Monate.

## <a name="see-also"></a>Siehe auch

[Verwalten von Microsoft 365 und Exchange Online mit Windows PowerShell](https://support.office.com//article/06a743bb-ceb6-49a9-a61d-db4ffdf54fa6)
