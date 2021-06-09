---
title: Entfernen der Lizenz aus einem freigegebenen Postfach
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
ms.reviewer: nicholak
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_licensing
search.appverid:
- BCS160
- MET150
- MOE150
description: 'Entfernen Sie eine Lizenz aus einem freigegebenen Postfach, um es einem anderen Benutzer zuzuweisen, oder geben Sie die Lizenz zurück, damit Sie nicht dafür bezahlen. '
ms.date: 05/11/2021
ms.openlocfilehash: dd2d99d762a4a68a9b0400353d64dabb536a891c
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821428"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a>Entfernen einer Lizenz aus einem freigegebenen Postfach

Für freigegebene Postfächer ist in der Regel keine Lizenz erforderlich. Folgen Sie diesen Anweisungen, um eine Lizenz aus einem freigegebenen Postfach zu entfernen, damit Sie sie einem Benutzer zuweisen oder die Lizenz zurückgeben können, damit Sie keine Lizenz bezahlen, die Sie nicht benötigen.

> [!NOTE]
>
> In den folgenden Szenarien ist eine Lizenz erforderlich:
>
> 1. Das freigegebene Postfach verfügt über mehr als 50 GB Speicherplatz.
> 2. Das freigegebene Postfach verwendet die direkte Archivierung.
> 3. Das freigegebene Postfach befindet sich in der Beweissicherung für juristische Zwecke.
> 4. Dem freigegebenen Postfach ist eine Microsoft Defender-Lizenz zugewiesen.

## <a name="remove-the-license"></a>Entfernen der Lizenz

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.

::: moniker-end

   > [!NOTE]
   > Sie müssen die Lizenz von der Seite "Aktive Benutzer" entfernen. Sie können die Lizenz nicht von der Seite "Freigegebenes Postfach" entfernen, da Lizenzen Benutzereinstellungen sind.
  
2. Wählen Sie das freigegebene Postfach aus.

3. Erweitern Sie auf der Registerkarte **"Lizenzen und Apps"** die Option **"Lizenzen",** und deaktivieren Sie das Kontrollkästchen für die Lizenz, die Sie entfernen möchten.

4. Wählen Sie **Änderungen speichern** aus.

5. Wenn Sie zur Seite **"Aktive Benutzer"** zurückkehren, wird der Status des **freigegebenen Postfachs nicht lizenziert.**

6. Sie bezahlen weiterhin für die Lizenz. Um die Zahlung zu beenden, [entfernen Sie die Lizenz aus Ihrem Abonnement.](../../commerce/licenses/buy-licenses.md)

## <a name="related-content"></a>Verwandte Inhalte

[Informationen zu freigegebenen Postfächern](about-shared-mailboxes.md) (Artikel)\
[Erstellen eines freigegebenen Postfachs](create-a-shared-mailbox.md) (Artikel)\
[Konfigurieren eines freigegebenen Postfachs](configure-a-shared-mailbox.md) (Artikel)\
[Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach](convert-user-mailbox-to-shared-mailbox.md) (Artikel)\
[Beheben von Problemen mit freigegebenen Postfächern](resolve-issues-with-shared-mailboxes.md) (Artikel)
