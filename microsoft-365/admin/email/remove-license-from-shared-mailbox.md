---
title: Entfernen der Lizenz aus einem freigegebenen Postfach
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: bb229ee9-e7be-4990-b3eb-354e75740496
description: 'Entfernen Sie die Lizenz aus einem freigegebenen Postfach, um Sie einem anderen Benutzer zuzuweisen. '
ms.openlocfilehash: 401b334efeccf6d7c4caca20be3cc9767b2df945
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2020
ms.locfileid: "44432219"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a>Entfernen einer Lizenz aus einem freigegebenen Postfach

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Freigegebene Postfächer benötigen normalerweise keine Lizenz. Befolgen Sie diese Anweisungen, um eine Lizenz aus einem freigegebenen Postfach zu entfernen, damit Sie Sie entweder einem Benutzer zuweisen oder die Lizenz zurückgeben können, damit Sie nicht für eine Lizenz bezahlen, die Sie nicht benötigen.

> [!NOTE]
> In den folgenden Szenarien ist eine Lizenz erforderlich:
> 1. Das freigegebene Postfach verfügt über mehr als 50 GB Speicherplatz.
> 2. Das freigegebene Postfach verwendet die in-Place-Archivierung.
> 3. Das freigegebene Postfach wird in einem Beweissicherungsverfahren aufbewahrt.

  
## <a name="remove-the-license"></a>Entfernen der Lizenz

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.

   > [!NOTE]
   > Sie müssen die Lizenz von der Seite "aktive Benutzer" entfernen. Sie können die Lizenz nicht von der Seite freigegebene Postfächer entfernen, da Lizenzen Benutzereinstellungen sind. 
  
2. Wählen Sie das freigegebene Postfach aus.

3. Erweitern Sie auf der Registerkarte **Lizenzen und apps** den Knoten **Lizenzen** , und deaktivieren Sie das Kontrollkästchen für die Lizenz, die Sie entfernen möchten.

4. Wählen Sie **Änderungen speichern** aus.

5. Wenn Sie zur Seite **aktive Benutzer** zurückkehren, wird der Status des freigegebenen Postfachs nicht **lizenziert**.

6. Sie zahlen noch immer für die Lizenz. Um das bezahlen zu beenden, [Entfernen Sie die Lizenz aus Ihrem Abonnement](../../commerce/licenses/remove-licenses-from-subscription.md).

::: moniker-end

::: moniker range="o365-germany"

 1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.

   > [!NOTE]
   > Sie müssen die Lizenz von der Seite "aktive Benutzer" entfernen. Sie können die Lizenz nicht von der Seite freigegebene Postfächer entfernen, da Lizenzen Benutzereinstellungen sind.

2. Wählen Sie das freigegebene Postfach aus, und wählen Sie neben **Produktlizenzen** **Bearbeiten** aus.

3. Legen Sie auf der Seite **Produktlizenzen** die Umschaltfläche für die Lizenz, die Sie entfernen möchten, auf **aus** fest.

4. Klicken Sie auf **Speichern**.

5. Wenn Sie zur Seite **aktive Benutzer** zurückkehren, wird der Status des freigegebenen Postfachs nicht **lizenziert**.

6. Sie zahlen noch immer für die Lizenz. Um das bezahlen zu beenden, [Entfernen Sie die Lizenz aus Ihrem Abonnement](../../commerce/licenses/remove-licenses-from-subscription.md).

::: moniker-end

::: moniker range="o365-21vianet"

 1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.

   > [!NOTE]
   > Sie müssen die Lizenz von der Seite "aktive Benutzer" entfernen. Sie können die Lizenz nicht von der Seite freigegebene Postfächer entfernen, da Lizenzen Benutzereinstellungen sind.

2. Wählen Sie das freigegebene Postfach aus, und wählen Sie neben **Produktlizenzen** **Bearbeiten** aus.

3. Legen Sie auf der Seite **Produktlizenzen** die Umschaltfläche für die Lizenz, die Sie entfernen möchten, auf **aus** fest.

4. Klicken Sie auf **Speichern**.

5. Wenn Sie zur Seite **aktive Benutzer** zurückkehren, wird der Status des freigegebenen Postfachs nicht **lizenziert**.

6. Sie zahlen noch immer für die Lizenz. Um das bezahlen zu beenden, [Entfernen Sie die Lizenz aus Ihrem Abonnement](../../commerce/licenses/remove-licenses-from-subscription.md).

::: moniker-end 

## <a name="related-articles"></a>Verwandte Artikel

[Informationen zu freigegebenen Postfächern](about-shared-mailboxes.md)

[Erstellen eines freigegebenen Postfachs](create-a-shared-mailbox.md)

[Konfigurieren eines freigegebenen Postfachs](configure-a-shared-mailbox.md)

[Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach](convert-user-mailbox-to-shared-mailbox.md)

[Beheben von Problemen mit freigegebenen Postfächern](resolve-issues-with-shared-mailboxes.md)
