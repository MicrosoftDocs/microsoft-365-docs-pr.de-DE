---
title: Verwalten Microsoft 365 Mandanten mit Windows PowerShell für DAP-Partner
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: f92d5116-5b66-4150-ad20-1452fc3dd712
description: In diesem Artikel erfahren Sie, wie Sie PowerShell für Microsoft 365 zum Verwalten Ihrer Kundenmandschaften verwenden.
ms.openlocfilehash: 14290f04159e3ba0ce46971d204b71d3bb1600d9
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690413"
---
# <a name="manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a>Verwalten Microsoft 365 Mandanten mit Windows PowerShell für Partner mit delegierten Zugriffsberechtigungen (Delegated Access Permissions, DAP)

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Windows PowerShell ermöglicht Syndication- und Cloud Solution Provider (CSP)-Partnern die einfache Verwaltung und Berichtierung von Kunden-Mandationseinstellungen, die im Microsoft 365 Admin Center nicht verfügbar sind. Beachten Sie, dass Berechtigungen für die Verwaltung im Auftrag von (AOBO) erforderlich sind, damit das Partneradministratorkonto eine Verbindung mit seinen Kundenmandieren herstellen kann.
  
DAP-Partner (Delegated Access Permission, delegierte Zugriffsberechtigung) sind Syndication-Partner und Cloudlösungsanbieter (Cloud Solution Providers, CSP). Häufig handelt es sich um Netzwerk- oder Telekom-Anbieter für andere Unternehmen. Sie bündeln Microsoft 365 Abonnements in ihren Serviceangeboten für ihre Kunden. Wenn sie ein Microsoft 365-Abonnement verkaufen, erhalten sie automatisch Die Berechtigung Verwalten im Auftrag von (AOBO) für die Kundenmandschaften, damit sie die Kundenmandschaften verwalten und melden können.
## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

Für die Verfahren in diesem Thema müssen Sie eine Verbindung mit Verbinden [Herstellen Microsoft 365 PowerShell herstellen.](connect-to-microsoft-365-powershell.md)
  
Sie benötigen auch die Administratoranmeldeinformationen Ihres Partnermandanten.
  
## <a name="what-do-you-want-to-do"></a>Was möchten Sie machen?

### <a name="list-all-tenant-ids"></a>Auflisten aller Mandanten-IDs

> [!NOTE]
> Wenn Sie über mehr als 500 Mandanten verfügen, fügen Sie in die Cmdlet-Syntax entweder  _-All_ oder _-MaxResultsParameter_ ein. Dies gilt für andere Cmdlets mit einer umfangreichen Ausgabe, wie z. B. **Get-MsolUser**.
  
Führen Sie den folgenden Befehl aus, um alle Kundenmandanten-IDs aufzulisten, auf die Sie Zugriff haben.
  
```
Get-MsolPartnerContract -All | Select-Object TenantId
```

Dies zeigt eine Liste aller Kundenmandanten nach **TenantId** geordnet an.

>[!Note]
>PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets mit **Msol** im Namen. Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über Windows PowerShell ausführen.
>
  
### <a name="get-a-tenant-id-by-using-the-domain-name"></a>Abrufen einer Mandanten-ID mithilfe des Domänennamens

Zum Abrufen der **TenantId** eines bestimmten Kundenmandanten nach Domänenname führen Sie den folgenden Befehl aus. Ersetzen Sie _<domänenname.onmicrosoft.com>_ durch den eigentlichen Domänennamen des gewünschten Kundenmandanten.
  
```
Get-MsolPartnerContract -DomainName <domainname.onmicrosoft.com> | Select-Object TenantId
```

### <a name="list-all-domains-for-a-tenant"></a>Auflisten aller Domänen für einen Mandanten

Um alle Domänen für einen einzigen Kundenmandanten aufzurufen, führen Sie den folgenden Befehl aus. Ersetzen Sie  _<customer TenantId value>_ durch den eigentlichen Wert.
  
```
Get-MsolDomain -TenantId <customer TenantId value>
```

Wenn Sie zusätzliche Domänen registriert haben, werden alle Domänen zurückgegeben, die mit der **TenantId** des Kunden verknüpft sind.
  
### <a name="get-a-mapping-of-all-tenants-and-registered-domains"></a>Abrufen einer Zuordnung aller Mandanten und registrierten Domänen

In den vorherigen PowerShell für Microsoft 365-Befehlen wurde gezeigt, wie Sie entweder Mandanten-IDs oder Domänen abrufen, aber nicht beide gleichzeitig und ohne klare Zuordnung zwischen allen. Dieser Befehl generiert eine Auflistung aller Kunden-Mandanten-IDs und deren Domänen.
  
```
$Tenants = Get-MsolPartnerContract -All; $Tenants | foreach {$Domains = $_.TenantId; Get-MsolDomain -TenantId $Domains | fl @{Label="TenantId";Expression={$Domains}},name}
```

### <a name="get-all-users-for-a-tenant"></a>Abrufen aller Benutzer für einen Mandanten

Hierdurch werden der **UserPrincipalName**, der **DisplayName** und der Status **isLicensed** für alle Benutzer eines bestimmten Mandanten angezeigt. Ersetzen Sie _<customer TenantId value>_ durch den eigentlichen Wert.
  
```
Get-MsolUser -TenantID <customer TenantId value>
```

### <a name="get-all-details-about-a-user"></a>Abrufen aller Details eines Benutzers

Wenn Sie alle Eigenschaften eines bestimmten Benutzers anzeigen möchten, führen Sie den folgenden Befehl aus:  Ersetzen Sie _<customer TenantId value>_ und _<user principal name value>_ durch die eigentlichen Werte.
  
```
Get-MsolUser -TenantId <customer TenantId value> -UserPrincipalName <user principal name value>
```

### <a name="add-users-set-options-and-assign-licenses"></a>Hinzufügen von Benutzern, Festlegen von Optionen und Zuweisen von Lizenzen

Die Massenerstellung, Konfiguration und Lizenzierung von Microsoft 365 benutzern ist besonders effizient, indem PowerShell für die Microsoft 365. In diesem zwei-Schritt-Prozess erstellen Sie zunächst Einträge für alle Benutzer, die Sie in einer CSV-Datei (Comma-separated Value) hinzufügen möchten, und importieren sie dann mithilfe von PowerShell für Microsoft 365. 
  
#### <a name="create-a-csv-file"></a>Erstellen einer CSV-Datei

Erstellen Sie eine CSV-Datei anhand dieses Formats:
  
-  `UserPrincipalName,FirstName,LastName,DisplayName,Password,TenantId,UsageLocation,LicenseAssignment`
    
Dabei gilt:
  
- **UsageLocation**: Der Wert hierfür ist der zweistellige ISO-Länder-/Regionscode des Benutzers. Die Länder-/Regioinscodes finden Sie auf der [ISO-Online-Browserplattform](https://go.microsoft.com/fwlink/p/?LinkId=532703). Der Code für die Vereinigten Staaten lautet z. B. „US", der Code für Brasilien „BR". 
    
- **LicenseAssignment**: Der Wert hierfür verwendet das folgende Format: `syndication-account:<PROVISIONING_ID>`. Wenn Sie Kundenmandantenbenutzern zum Beispiel O365_Business_Premium-Lizenzen zuweisen, sieht der Wert **LicenseAssignment** wie folgt aus: **syndication-account:O365_Business_Premium**. Sie finden die PROVISIONING_IDs im Syndication-Partnerportal, auf das Sie als Syndication- oder CSP-Partner Zugriff haben.
    
#### <a name="import-the-csv-file-and-create-the-users"></a>Importieren der CSV-Datei und Erstellen der Benutzer

Nachdem Sie die CSV-Datei erstellt haben, führen Sie den folgenden Befehl zum Erstellen von Benutzerkonten mit nicht ablaufenden Kennwörtern aus. Der Benutzer muss das Kennwort beim ersten Anmelden ändern, und es weist ihm die ausgewählte Lizenz zu. Achten Sie darauf, dass Sie den richtigen Namen der CSV-Datei angeben.
  
```
Import-Csv .\FILENAME.CSV | foreach {New-MsolUser -UserPrincipalName $_.UserPrincipalName -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -Password $_.Password -UsageLocation $_.UsageLocation -LicenseAssignment $_.LicenseAssignment -ForceChangePassword:$true -PasswordNeverExpires:$true -TenantId $_.TenantId}
```

## <a name="see-also"></a>Siehe auch

#### 

[Hilfe für Partner](https://go.microsoft.com/fwlink/p/?LinkId=533477)

