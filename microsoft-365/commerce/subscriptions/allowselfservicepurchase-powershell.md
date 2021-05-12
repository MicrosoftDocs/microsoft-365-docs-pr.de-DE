---
title: Verwenden von AllowSelfServicePurchase für das MS Commerce PowerShell-Modul
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: mijeffer, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_ssp
search.appverid:
- MET150
description: Erfahren Sie, wie Sie das AllowSelfServicePurchase PowerShell-Cmdlet verwenden, um den Self-Service-Kauf ein- oder auszuschalten.
ROBOTS: NOINDEX, NOFOLLOW
ms.date: 03/18/2021
ms.openlocfilehash: 09161f69e72babe8270b339243d73444b93d9959
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333374"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>Verwenden von AllowSelfServicePurchase für das MS Commerce PowerShell-Modul

Das **MS Commerce** PowerShell-Modul ist jetzt im [PowerShell Gallery verfügbar.](https://aka.ms/allowselfservicepurchase-powershell-gallery) Das Modul enthält einen **PolicyID-Parameterwert** für **AllowSelfServicePurchase,** mit dem Sie steuern können, ob Benutzer in Ihrer Organisation Self-Service-Käufe tätigen können.

Sie können das **MS Commerce PowerShell-Modul** verwenden, um:

- Anzeigen des Standardzustands des **Parameterwerts AllowSelfServicePurchase** – unabhängig davon, ob er aktiviert oder deaktiviert ist
- Anzeigen einer Liste der zutreffenden Produkte und ob der Self-Service-Kauf aktiviert oder deaktiviert ist
- Anzeigen oder Ändern der aktuellen Einstellung für ein bestimmtes Produkt, um sie entweder zu aktivieren oder zu deaktivieren

## <a name="requirements"></a>Anforderungen

Für die Verwendung des **MS Commerce** PowerShell-Moduls benötigen Sie:

- Ein Windows 10 Gerät
- Administratorberechtigung für das Gerät
- Rolle "Globaler Administrator" oder "Abrechnungsadministrator" für Ihren Mandanten

## <a name="install-the-mscommerce-powershell-module"></a>Installieren des MS Commerce PowerShell-Moduls

Sie installieren das **MS Commerce** PowerShell-Modul einmal auf Ihrem Windows 10 und importieren es dann in jede gestartete PowerShell-Sitzung. Laden Sie **das MS Commerce** PowerShell-Modul aus dem [PowerShell-Katalog herunter.](https://aka.ms/allowselfservicepurchase-powershell-gallery)

Führen Sie den folgenden Befehl **aus,** um das MS Commerce PowerShell-Modul mit **PowerShellGet** zu installieren:

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a>Importieren von MSCommerce in die PowerShell-Sitzung

Nachdem Sie das Modul auf Ihrem Windows 10 installiert haben, importieren Sie es in jede gestartete PowerShell-Sitzung. Führen Sie den folgenden Befehl aus, um ihn in eine PowerShell-Sitzung zu importieren:

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a>Verbinden mit Ihren Anmeldeinformationen zu MSCommerce

Führen Sie den folgenden Befehl aus, um eine Verbindung mit dem PowerShell-Modul mit Ihren Anmeldeinformationen herzustellen.

```powershell
Connect-MSCommerce
```

Dieser Befehl verbindet die aktuelle PowerShell-Sitzung mit einem Azure Active Directory Mandanten. Der Befehl fordert Sie auf, einen Benutzernamen und ein Kennwort für den Mandanten einzugeben, mit dem Sie eine Verbindung herstellen möchten. Wenn die mehrstufige Authentifizierung für Ihre Anmeldeinformationen aktiviert ist, verwenden Sie die interaktive Option zum Anmelden.

## <a name="view-details-for-allowselfservicepurchase"></a>Anzeigen von Details für AllowSelfServicePurchase

Führen Sie zum Anzeigen einer Beschreibung des **AllowSelfServicePurchase-Parameterwerts** und des Standardstatus basierend auf Ihrer Organisation den folgenden Befehl aus:

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a>Anzeigen einer Liste der Self-Service-Einkaufsprodukte und deren Status

Führen Sie den folgenden Befehl aus, um eine Liste aller verfügbaren Self-Service-Einkaufsprodukte und den Status der einzelnen Produkte anzeigen zu können:

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

In der folgenden Tabelle sind die verfügbaren Produkte und deren **ProductId aufgeführt.**

| Produkt | ProductId |
|-----------------------------|--------------|
| Power Apps pro Benutzer | CFQ7TTC0KP0P |
| Power Automate pro Benutzer | CFQ7TTC0KP0N |
| Power Automate RPA | CFQ7TTC0KXG6  |
| Power BI Premium (eigenständig) | CFQ7TTC0KXG7  |
| Power BI Pro | CFQ7TTC0L3PB |
| Project Plan 1 | CFQ7TTC0KXND |
| Project Plan 3 | CFQ7TTC0KXNC |
| Visio Plan 1 | CFQ7TTC0KXN9 |
| Visio Plan 2 | CFQ7TTC0KXN8 |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a>Anzeigen oder Festlegen des Status für AllowSelfServicePurchase

Nachdem Sie die Liste der Produkte angezeigt haben, die für den Self-Service-Kauf verfügbar sind, können Sie die Einstellung für ein bestimmtes Produkt anzeigen oder ändern.

Führen Sie den folgenden Befehl aus, um die Richtlinieneinstellung für ein bestimmtes Produkt zu erhalten:

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

Führen Sie den folgenden Befehl aus, um die Richtlinieneinstellung für ein bestimmtes Produkt zu aktivieren:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

Führen Sie den folgenden Befehl aus, um die Richtlinieneinstellung für ein bestimmtes Produkt zu deaktivieren:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a>Beispielskript zum Deaktivieren von AllowSelfServicePurchase

Im folgenden Beispiel erfahren Sie, wie Sie das **MS Commerce-Modul** importieren, sich mit Ihrem Konto anmelden, **die ProductId** für Power Automate erhalten und **dann AllowSelfServicePurchase** für dieses Produkt deaktivieren.

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a>Problembehandlung

### <a name="problem"></a>Problem

Die folgende Fehlermeldung wird angezeigt:

> HandleError : Fehler beim Abrufen der Richtlinie mit PolicyId 'AllowSelfServicePurchase', ErrorMessage – Die zugrunde liegende Verbindung wurde geschlossen: Bei einem Senden ist ein unerwarteter Fehler aufgetreten.

Dies liegt möglicherweise an einer älteren Version von Transport Layer Security (TLS). Zum Verbinden dieses Diensts müssen Sie TLS 1.2 oder höher verwenden.

### <a name="solution"></a>Lösung

Upgrade auf TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](/mem/configmgr/core/plan-design/security/enable-tls-1-2)

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
