---
title: Hinzufügen einer Domäne zu einer Client Mandantschaft mit Windows PowerShell für DAP-Partner
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
description: 'Zusammenfassung: Verwenden Sie PowerShell für Microsoft 365, um einen alternativen Domänennamen zu einem vorhandenen Kundenmandanten hinzuzufügen.'
ms.openlocfilehash: 23137d2e2461e75a22d0403f9b8246a29e48019f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690863"
---
# <a name="add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-permission-dap-partners"></a>Hinzufügen einer Domäne zu einem Kundenmandanten mit Windows PowerShell für Partner mit delegierten Zugriffsberechtigungen (Delegated Access Permission, DAP)

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Sie können neue Domänen mit dem Mandanten Ihres Kunden mit PowerShell für Microsoft 365 schneller erstellen und zuordnen als mit dem Microsoft 365 Admin Center.
  
DAP-Partner (Delegated Access Permission, delegierte Zugriffsberechtigung) sind Syndication-Partner und Cloudlösungsanbieter (Cloud Solution Providers, CSP). Häufig handelt es sich um Netzwerk- oder Telekom-Anbieter für andere Unternehmen. Sie bündeln Microsoft 365-Abonnements für Ihre Kunden in ihren Dienst angeboten. Wenn Sie ein Microsoft 365-Abonnement verkaufen, werden Ihnen automatisch Administratoren im Namen von (AOBO) Berechtigungen für den Kundenmandanten erteilt, damit Sie den Kundenmandanten verwalten und melden können.
## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

Für die Verfahren in diesem Thema müssen Sie eine Verbindung herstellen, um [eine Verbindung mit Microsoft 365 mit PowerShell](connect-to-microsoft-365-powershell.md)herzustellen.
  
Sie benötigen auch die Administratoranmeldeinformationen Ihres Partnermandanten.
  
Sie benötigen außerdem die folgenden Informationen:
  
- Sie benötigen den vollqualifizierten Domänennamen (FQDN), den der Kunde verwenden möchte.
    
- Sie benötigen die **TenantId** des Kunden.
    
- Der FQDN muss bei einer Registrierungsstelle für Internetdomänennamen, wie z. B. GoDaddy, registriert sein. Weitere Informationen für die öffentliche Registrierung eines Domänennamens finden Sie unter [Erwerben eines Domänennamens](https://go.microsoft.com/fwlink/p/?LinkId=532541).
    
- Sie müssen wissen, wie Sie einen TXT-Eintrag zur registrierten DNS-Zone für die DNS-Registrierungsstelle hinzufügen. Weitere Informationen zum Hinzufügen eines txt-Eintrags finden Sie unter [Hinzufügen von DNS-Einträgen zum Verbinden Ihrer Domäne](https://go.microsoft.com/fwlink/p/?LinkId=532542). Wenn Sie diese Verfahren nicht durchführen können, müssen Sie die für die DNS-Registrierungsstelle anwendbaren Verfahren ermitteln.
    
## <a name="create-domains"></a>Erstellen von Domänen

 Ihre Kunden werden Sie wahrscheinlich bitten, weitere Domänen für ihren Mandanten zu erstellen, da sie die Standarddomäne<Domäne>.onmicrosoft.comwahrscheinlich nicht als primären Domäne verwenden möchten, um ihr Unternehmen im Internet weltweit zu repräsentieren. Dieses Verfahren leitet Sie durch die Schritte zum Erstellen einer neuen Domäne, die Sie mit dem Kundenmandanten verknüpfen können.
  
> [!NOTE]
> Um einige dieser Vorgänge ausführen zu können, muss das Partneradministrator Konto, mit dem Sie sich anmelden, auf **vollständige Verwaltung** für die Einstellung **administrativer Zugriff für Unternehmen zuweisen, die Sie unterstützen** in den Details des Administratorkontos im Microsoft 365 Admin Center festgelegt sein. Weitere Informationen zum Verwalten von Partneradministrator Rollen finden Sie unter [Partners: Offer delegierte Administration](https://go.microsoft.com/fwlink/p/?LinkId=532435). 
  
### <a name="create-the-domain-in-azure-active-directory"></a>Erstellen Sie die Domäne in Azure Active Directory

Dieser Befehl erstellt die Domäne in Azure Active Directory, ordnet sie jedoch nicht der öffentlich registrierten Domäne zu. Das kommt, wenn Sie nachweisen, dass Sie die öffentlich registrierte Domäne für Microsoft Microsoft 365 für Unternehmen besitzen.
  
```powershell
New-MsolDomain -TenantId <customer TenantId> -Name <FQDN of new domain>
```

>[!Note]
>PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets mit **Msol** im Namen. Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über Windows PowerShell ausführen.
>

### <a name="get-the-data-for-the-dns-txt-verification-record"></a>Abrufen der Daten für den DNS-TXT-Überprüfungseintrag

 Microsoft 365 generiert die spezifischen Daten, die Sie in den DNS TXT-Überprüfungs Eintrag einfügen müssen. Führen Sie diesen Befehl aus, um die Daten abzurufen.
  
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

Bevor Microsoft 365 beginnt, Datenverkehr zu akzeptieren, der an den öffentlich registrierten Domänennamen weitergeleitet wird, müssen Sie nachweisen, dass Sie Eigentümer der Domäne sind und über Administratorrechte verfügen. Sie weisen nach, dass Sie die Domäne besitzen, indem Sie einen TXT-Eintrag in der Domäne erstellen. Ein TXT-Eintrag hat keine Auswirkungen auf die Domäne, und er kann gelöscht werden, nachdem die Besitzrechte an der Domäne nachgewiesen wurden. Zum Erstellen der TXT-Einträge führen Sie die Verfahren unter [Hinzufügen von DNS-Einträgen aus, um eine Verbindung mit Ihrer Domäne herzustellen](https://go.microsoft.com/fwlink/p/?LinkId=532542). Wenn Sie diese Verfahren nicht durchführen können, müssen Sie die für die DNS-Registrierungsstelle anwendbaren Verfahren ermitteln.
  
Bestätigen Sie die erfolgreiche Erstellung des TXT-Eintrags über Nslookup. Verwenden Sie die folgende Syntax.
  
```console
nslookup -type=TXT <FQDN of registered domain>
```

Dadurch erhalten Sie die folgende Ausgabe:
  
 `Non-authoritative answer:`
  
 `FQDN of the registered domain`
  
 `text=MS=ms########`
  
### <a name="validate-domain-ownership-in-microsoft-365"></a>Überprüfen des Domänenbesitzes in Microsoft 365

In diesem letzten Schritt validieren Sie Microsoft 365, dass Sie die Domäne mit öffentlichem Namen besitzen. Nach diesem Schritt akzeptiert Microsoft 365 den Datenverkehr, der an den neuen Domänennamen weitergeleitet wird. Um das Erstellen und Registrieren der neuen Domäne abzuschließen, führen Sie den folgenden Befehl aus. 
  
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

