---
title: Hinzufügen einer Domäne zu einem Clientmandanten mit Windows PowerShell für DAP-Partner
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
ms.assetid: f49b4d24-9aa0-48a6-95dd-6bae9cf53d2c
description: 'Zusammenfassung: Verwenden Sie PowerShell für Microsoft 365, um einem vorhandenen Kundenmandanten einen alternativen Domänennamen hinzuzufügen.'
ms.openlocfilehash: 3bcdb40e2c72e5aac8103b0b55ff6fccfe6a9fcc
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229083"
---
# <a name="add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-permission-dap-partners"></a>Hinzufügen einer Domäne zu einem Kundenmandanten mit Windows PowerShell für Partner mit delegierten Zugriffsberechtigungen (Delegated Access Permission, DAP)

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Sie können mit PowerShell neue Domänen erstellen und dem Mandanten Ihres Kunden zuordnen, um Microsoft 365 schneller als die verwendung der Microsoft 365 Admin Center.

DAP-Partner (Delegated Access Permission, delegierte Zugriffsberechtigung) sind Syndication-Partner und Cloudlösungsanbieter (Cloud Solution Providers, CSP). Häufig handelt es sich um Netzwerk- oder Telekom-Anbieter für andere Unternehmen. Sie bündeln Microsoft 365 Abonnements in ihren Serviceangeboten für ihre Kunden. Wenn sie ein Microsoft 365 Abonnement verkaufen, wird ihnen automatisch die Berechtigung "Verwalten im Auftrag von" (Administer On Behalf Of, AOBO) für die Kundenmandanten gewährt, damit sie die Kundenmandanten verwalten und darüber berichten können.
## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

Für die Verfahren in diesem Thema müssen Sie eine Verbindung mit [Verbinden mit Microsoft 365 mit PowerShell](connect-to-microsoft-365-powershell.md)herstellen.

Sie benötigen auch die Administratoranmeldeinformationen Ihres Partnermandanten.

Sie benötigen außerdem die folgenden Informationen:

- Sie benötigen den vollqualifizierten Domänennamen (FQDN), den der Kunde verwenden möchte.

- Sie benötigen die **TenantId** des Kunden.

- Der FQDN muss bei einer Registrierungsstelle für Internetdomänennamen, wie z. B. GoDaddy, registriert sein. Weitere Informationen für die öffentliche Registrierung eines Domänennamens finden Sie unter [Erwerben eines Domänennamens](../admin/get-help-with-domains/buy-a-domain-name.md).

- Sie müssen wissen, wie Sie einen TXT-Eintrag zur registrierten DNS-Zone für die DNS-Registrierungsstelle hinzufügen. Weitere Informationen zum Hinzufügen eines TXT-Eintrags finden Sie unter [Hinzufügen von DNS-Einträgen zum Verbinden Ihrer Domäne.](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) Wenn Sie diese Verfahren nicht durchführen können, müssen Sie die für die DNS-Registrierungsstelle anwendbaren Verfahren ermitteln.

## <a name="create-domains"></a>Erstellen von Domänen

 Ihre Kunden werden Sie wahrscheinlich bitten, weitere Domänen für ihren Mandanten zu erstellen, da sie die Standarddomäne<Domäne>.onmicrosoft.comwahrscheinlich nicht als primären Domäne verwenden möchten, um ihr Unternehmen im Internet weltweit zu repräsentieren. Dieses Verfahren leitet Sie durch die Schritte zum Erstellen einer neuen Domäne, die Sie mit dem Kundenmandanten verknüpfen können.

> [!NOTE]
> Um einige dieser Vorgänge auszuführen, muss das Partneradministratorkonto, mit dem Sie sich anmelden, auf **"Vollständige Verwaltung"** für die **Zuweisung des administrativen Zugriffs auf Unternehmen** festgelegt werden, die Sie in den Details des Administratorkontos im Microsoft 365 Admin Center unterstützen. Weitere Informationen zum Verwalten von Partneradministratorrollen finden Sie unter ["Partner: Anbieten delegierter Verwaltung".](https://go.microsoft.com/fwlink/p/?LinkId=532435)

### <a name="create-the-domain-in-azure-active-directory"></a>Erstellen Sie die Domäne in Azure Active Directory

Dieser Befehl erstellt die Domäne in Azure Active Directory, ordnet sie jedoch nicht der öffentlich registrierten Domäne zu. Dies kommt, wenn Sie nachweisen, dass Sie die öffentlich registrierte Domäne bei Microsoft Microsoft 365 für Unternehmen besitzen.

```powershell
New-MsolDomain -TenantId <customer TenantId> -Name <FQDN of new domain>
```

> [!NOTE]
> PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets mit **Msol** im Namen. Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über Windows PowerShell ausführen.

### <a name="get-the-data-for-the-dns-txt-verification-record"></a>Abrufen der Daten für den DNS-TXT-Überprüfungseintrag

 Microsoft 365 generiert die spezifischen Daten, die Sie in den DNS TXT-Überprüfungseintrag eingeben müssen. Führen Sie diesen Befehl aus, um die Daten abzurufen.

```powershell
Get-MsolDomainVerificationDNS -TenantId <customer TenantId> -DomainName <FQDN of new domain> -Mode DnsTxtRecord
```

Dadurch erhalten Sie die folgende Ausgabe:

 `Label: domainname.com`

 `Text: MS=ms########`

 `Ttl: 3600`

> [!NOTE]
> Sie benötigen diesen Text, um den TXT-Eintrag in der öffentlich registrierten DNS-Zone zu erstellen. Stellen Sie sicher, dass Sie ihn kopieren und speichern.

### <a name="add-a-txt-record-to-the-publically-registered-dns-zone"></a>Hinzufügen eines TXT-Eintrags zur öffentlich registrierten DNS-Zone

Bevor Microsoft 365 beginnen, Datenverkehr zu akzeptieren, der an den öffentlich registrierten Domänennamen weitergeleitet wird, müssen Sie nachweisen, dass Sie der Besitzer der Domäne sind und über Administratorberechtigungen für die Domäne verfügen. Sie weisen nach, dass Sie die Domäne besitzen, indem Sie einen TXT-Eintrag in der Domäne erstellen. Ein TXT-Eintrag hat keine Auswirkungen auf die Domäne, und er kann gelöscht werden, nachdem die Besitzrechte an der Domäne nachgewiesen wurden. Um die TXT-Einträge zu erstellen, führen Sie die Verfahren unter [Hinzufügen von DNS-Einträgen aus, um Ihre Domäne zu verbinden.](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) Wenn Sie diese Verfahren nicht durchführen können, müssen Sie die für die DNS-Registrierungsstelle anwendbaren Verfahren ermitteln.

Bestätigen Sie die erfolgreiche Erstellung des TXT-Eintrags über Nslookup. Verwenden Sie die folgende Syntax.

```console
nslookup -type=TXT <FQDN of registered domain>
```

Dadurch erhalten Sie die folgende Ausgabe:

 `Non-authoritative answer:`

 `FQDN of the registered domain`

 `text=MS=ms########`

### <a name="validate-domain-ownership-in-microsoft-365"></a>Überprüfen des Domänenbesitzes in Microsoft 365

In diesem letzten Schritt überprüfen Sie, Microsoft 365, dass Sie die öffentlich registrierte Domäne besitzen. Nach diesem Schritt akzeptiert Microsoft 365 den Datenverkehr, der an den neuen Domänennamen weitergeleitet wird. Um das Erstellen und Registrieren der neuen Domäne abzuschließen, führen Sie den folgenden Befehl aus.

```powershell
Confirm-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

Dieser Befehl gibt keine Ausgabe zurück. Um sicherzustellen, dass dies funktioniert hat, führen Sie den folgenden Befehl aus.

```powershell
Get-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

Dadurch wird in etwa Folgendes zurückgegeben

```console
Name                   Status      Authentication
--------------------   ---------   --------------
FQDN of new domain     Verified    Managed
```


## <a name="see-also"></a>Siehe auch

####

[Hilfe für Partner](https://go.microsoft.com/fwlink/p/?LinkID=533477)