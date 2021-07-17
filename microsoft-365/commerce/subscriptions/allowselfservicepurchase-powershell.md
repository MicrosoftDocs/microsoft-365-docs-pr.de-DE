---
title: Verwenden von AllowSelfServicePurchase für das MSShell-PowerShell-Modul
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
description: Erfahren Sie, wie Sie das PowerShell-Cmdlet "AllowSelfServicePurchase" verwenden, um den Self-Service-Kauf zu aktivieren oder zu deaktivieren.
ROBOTS: NOINDEX, NOFOLLOW
ms.date: 07/16/2021
ms.openlocfilehash: 77cb1c753db22929ea2c3d14226a3927e6406b89
ms.sourcegitcommit: ea8de1b48adb6df92fb9351ea862184a9f16cbbb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2021
ms.locfileid: "53461363"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>Verwenden von AllowSelfServicePurchase für das MSShell-PowerShell-Modul

Das **MSShell-PowerShell-Modul** ist jetzt im [PowerShell-Katalog](https://aka.ms/allowselfservicepurchase-powershell-gallery)verfügbar. Das Modul enthält einen **PolicyID-Parameterwert** für **AllowSelfServicePurchase,** mit dem Sie steuern können, ob Benutzer in Ihrer Organisation Self-Service-Käufe tätigen können.

Sie können das **MSShell-PowerShell-Modul** für Folgendes verwenden:

- Anzeigen des Standardzustands des **AllowSelfServicePurchase-Parameterwerts** – unabhängig davon, ob er aktiviert oder deaktiviert ist
- Anzeigen einer Liste der anwendbaren Produkte und ob self-service purchase aktiviert oder deaktiviert ist
- Anzeigen oder Ändern der aktuellen Einstellung für ein bestimmtes Produkt, um es zu aktivieren oder zu deaktivieren

## <a name="requirements"></a>Anforderungen

Zum Verwenden des **MSShell-PowerShell-Moduls** benötigen Sie Folgendes:

- Ein Windows 10 Gerät
- PowerShell 5 oder darunter. PowerShell 6.x/7.x wird derzeit mit diesem Modul nicht unterstützt.
- Administratorberechtigung für das Gerät
- Rolle "Globaler Administrator" oder "Abrechnungsadministrator" für Ihren Mandanten

## <a name="install-the-mscommerce-powershell-module"></a>Installieren des MSShell-PowerShell-Moduls

Installieren Sie das **MSShell-PowerShell-Modul** einmal auf Ihrem Windows 10 Gerät, und importieren Sie es dann in jede PowerShell-Sitzung, die Sie starten. Laden Sie das **MSShell-PowerShell-Modul** aus dem [PowerShell-Katalog herunter.](https://aka.ms/allowselfservicepurchase-powershell-gallery)

Führen Sie den folgenden Befehl aus, um das **MSShell PowerShell-Modul** mit **PowerShellGet** zu installieren:

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a>Importieren von MSImport in die PowerShell-Sitzung

Nachdem Sie das Modul auf Ihrem Windows 10 Gerät installiert haben, importieren Sie es in jede PowerShell-Sitzung, die Sie starten. Führen Sie den folgenden Befehl aus, um sie in eine PowerShell-Sitzung zu importieren:

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a>Verbinden mit Ihren Anmeldeinformationen zu MS Commerce

Führen Sie den folgenden Befehl aus, um eine Verbindung mit dem PowerShell-Modul mit Ihren Anmeldeinformationen herzustellen.

```powershell
Connect-MSCommerce
```

Mit diesem Befehl wird die aktuelle PowerShell-Sitzung mit einem Azure Active Directory Mandanten verbunden. Der Befehl fordert Sie auf, einen Benutzernamen und ein Kennwort für den Mandanten einzugeben, mit dem Sie eine Verbindung herstellen möchten. Wenn die mehrstufige Authentifizierung für Ihre Anmeldeinformationen aktiviert ist, verwenden Sie die interaktive Option zum Anmelden.

## <a name="view-details-for-allowselfservicepurchase"></a>Anzeigen von Details für AllowSelfServicePurchase

Führen Sie den folgenden Befehl aus, um eine Beschreibung des **AllowSelfServicePurchase-Parameterwerts** und des Standardstatus basierend auf Ihrer Organisation anzuzeigen:

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a>Anzeigen einer Liste von Self-Service-Einkaufsprodukten und deren Status

Führen Sie den folgenden Befehl aus, um eine Liste aller verfügbaren Self-Service Purchase-Produkte und den Status der einzelnen Produkte anzuzeigen:

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

In der folgenden Tabelle sind die verfügbaren Produkte und ihre **ProductId aufgeführt.**

| Produkt | Productid |
|-----------------------------|--------------|
| Power Apps pro Benutzer | CFQ7TTC0KP0P |
| Power Automate pro Benutzer | CFQ7TTC0KP0N |
| Power Automate Rpa | CFQ7TTC0KXG6  |
| Power BI Premium (eigenständig) | CFQ7TTC0KXG7  |
| Power BI Pro | CFQ7TTC0L3PB |
| Project Plan 1 | CFQ7TTC0KXND |
| Project Plan 3 | CFQ7TTC0KXNC |
| Visio Plan 1 | CFQ7TTC0KXN9 |
| Visio Plan 2 | CFQ7TTC0KXN8 |
| Windows 365 Enterprise | CFQ7TTC0HHS9 |
| Windows 365 Business | CFQ7TTC0J203 |
| Windows 365 Business mit Windows Hybridvorteil | CFQ7TTC0HX99 |
## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a>Anzeigen oder Festlegen des Status für AllowSelfServicePurchase

Nachdem Sie die Liste der für den Self-Service-Kauf verfügbaren Produkte angezeigt haben, können Sie die Einstellung für ein bestimmtes Produkt anzeigen oder ändern.

Führen Sie den folgenden Befehl aus, um die Richtlinieneinstellung für ein bestimmtes Produkt abzurufen:

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

Das folgende Beispiel führt Sie durch das Importieren des **MSBuild-Moduls,** das Anmelden mit Ihrem Konto, das Abrufen der **ProductId** für Power Automate und das Deaktivieren von **AllowSelfServicePurchase** für dieses Produkt.

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a>Problembehandlung

### <a name="problem"></a>Problem

Die folgende Fehlermeldung wird angezeigt:

> HandleError: Fehler beim Abrufen der Richtlinie mit "AllowSelfServicePurchase", ErrorMessage : Die zugrunde liegende Verbindung wurde geschlossen: Beim Senden ist ein unerwarteter Fehler aufgetreten.

Dies kann auf eine ältere Version von Transport Layer Security (TLS) zurückzuführen sein. Um diesen Dienst zu verbinden, müssen Sie TLS 1.2 oder höher verwenden.

### <a name="solution"></a>Lösung

Upgrade auf TLS 1.2: (/mem/configmgr/core/plan-design/security/enable-tls-1-2)

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->

## <a name="related-content"></a>Verwandte Inhalte

[Verwalten von Self-Service-Käufen (Administrator)](manage-self-service-purchases-admins.md) (Artikel)

[Faq zum Self-Service-Kauf](self-service-purchase-faq.yml) (Artikel)
