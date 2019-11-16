---
title: Verwenden von AllowSelfServicePurchase zum Aktivieren oder Deaktivieren von Self-Service-Käufen
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: Hier erfahren Sie, wie Sie das AllowSelfServicePurchase PowerShell-Cmdlet verwenden, um Self-Service-Käufe ein-oder auszuschalten.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 9093e018ed24a9e9735f5b6b71084246967cb59d
ms.sourcegitcommit: 8ca97fa879ae4ea44468be629d6c32b429efeeec
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "38676267"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>Verwenden von AllowSelfServicePurchase für das MSCommerce-PowerShell-Modul

Das **MSCommerce** PowerShell-Modul steht nun im [PowerShell-Katalog](https://aka.ms/allowselfservicepurchase-powershell-gallery)zur Verfügung. Das Modul enthält einen Parameterwert für die **Richtlinien** - **AllowSelfServicePurchase** , mit dem Sie steuern können, ob Benutzer in Ihrer Organisation Self-Service-Käufe tätigen können.

Sie können das **MSCommerce** -PowerShell-Modul verwenden, um Folgendes zu tun:

- Anzeigen des Standardstatus des **AllowSelfServicePurchase** -Parameterwerts – unabhängig davon, ob er aktiviert oder deaktiviert ist
- Anzeigen einer Liste der anwendbaren Produkte und der Aktivierung oder Deaktivierung von Self-Service-Käufen
- Anzeigen oder Ändern der aktuellen Einstellung für ein bestimmtes Produkt, um es entweder zu aktivieren oder zu deaktivieren

## <a name="requirements"></a>Anforderungen

Um das **MSCommerce** PowerShell-Modul verwenden zu können, benötigen Sie Folgendes:

- Ein Windows 10-Gerät
- Administrator Berechtigung für das Gerät
- Globale oder abrechnungsadministrator Rolle für Ihren Mandanten

## <a name="install-the-mscommerce-powershell-module"></a>Installieren des MSCommerce PowerShell-Moduls

Sie installieren das **MSCommerce** PowerShell-Modul auf Ihrem Windows 10-Gerät einmal und importieren es dann in jede von Ihnen gestartete PowerShell-Sitzung. Laden Sie das **MSCommerce** PowerShell-Modul aus dem [PowerShell-Katalog](https://aka.ms/allowselfservicepurchase-powershell-gallery)herunter.

Führen Sie den folgenden Befehl aus, um das **MSCommerce** PowerShell-Modul mit **PowerShellGet**zu installieren:

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a>Importieren von MSCommerce in die PowerShell-Sitzung

Nachdem Sie das Modul auf Ihrem Windows 10-Gerät installiert haben, importieren Sie es in jede PowerShell-Sitzung, die Sie starten. Führen Sie den folgenden Befehl aus, um ihn in eine PowerShell-Sitzung zu importieren:

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a>Herstellen einer Verbindung mit MSCommerce mit Ihren Anmeldeinformationen

Führen Sie den folgenden Befehl aus, um eine Verbindung mit dem PowerShell-Modul mit Ihren Anmeldeinformationen herzustellen.

```powershell
Connect-MSCommerce
```

Mit diesem Befehl wird die aktuelle PowerShell-Sitzung mit einem Azure-Active Directory-Mandanten verbunden. Mit dem Befehl werden Sie aufgefordert, einen Benutzernamen und ein Kennwort für den Mandanten einzugeben, mit dem Sie eine Verbindung herstellen möchten. Wenn die mehrstufige Authentifizierung für Ihre Anmeldeinformationen aktiviert ist, verwenden Sie die interaktive Option, um sich anzumelden.

## <a name="view-details-for-allowselfservicepurchase"></a>Anzeigen von Details für AllowSelfServicePurchase

Führen Sie den folgenden Befehl aus, um eine Beschreibung des **AllowSelfServicePurchase** -Parameterwerts und des Standardstatus basierend auf Ihrer Organisation anzuzeigen:

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a>Anzeigen einer Liste von Self-Service-Kauf Produkten und deren Status

Führen Sie den folgenden Befehl aus, um eine Liste aller verfügbaren Self-Service-Einkaufsprodukte und den jeweiligen Status anzuzeigen:

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

In der folgenden Tabelle sind die verfügbaren Produkte und deren **ProductID**aufgeführt.

| Produkt | ProductID |
|-----------------------------|--------------|
| Power-apps pro Benutzer | CFQ7TTC0KP0P |
| Power-Automatisierung pro Benutzer | CFQ7TTC0KP0N |
| Power BI Pro | CFQ7TTC0L3PB |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a>Anzeigen oder Festlegen des Status für AllowSelfServicePurchase

Nachdem Sie die Liste der Produkte angezeigt haben, die für Self-Service-Einkauf verfügbar sind, können Sie die Einstellung für ein bestimmtes Produkt anzeigen oder ändern.

Um die Richtlinieneinstellung für ein bestimmtes Produkt abzurufen, führen Sie den folgenden Befehl aus:

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

Im folgenden Beispiel wird erläutert, wie Sie das **MSCommerce** -Modul importieren, sich mit Ihrem Konto anmelden, die **ProductID** für Power automatisieren und dann **AllowSelfServicePurchase** für dieses Produkt deaktivieren.

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->