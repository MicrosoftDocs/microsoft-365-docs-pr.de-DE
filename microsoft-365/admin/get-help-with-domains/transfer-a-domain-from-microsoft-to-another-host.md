---
title: Übertragen einer Domäne von Microsoft auf einen anderen Host
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
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: 'Hier finden Sie die Schritte zum Übertragen einer Domäne von Microsoft auf eine andere Registrierungsstelle. '
ms.openlocfilehash: f34e9733ab53c8bdc6f4432c96e6232ecc26ee06
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126347"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a>Übertragen einer Domäne von Microsoft auf einen anderen Host

Sie können eine Microsoft 365 60 Tage nach dem Kauf der Domäne von Microsoft nicht an eine andere Registrierungsstelle übertragen.

> [!NOTE]
> Eine _Whois-Abfrage_   zeigt eine von Microsoft erworbene Domänenregistrierungsstelle als Wild West Domains LLC an. Allerdings sollte nur Microsoft bezüglich Ihrer erworbenen Microsoft 365 kontaktiert werden.

Führen Sie die folgenden Schritte aus, um einen Code unter Microsoft 365 zu erhalten, und wechseln Sie dann zur anderen Website der Domänenregistrierungsstelle, um die Übertragung Ihres Domänennamens an die neue Registrierungsstelle zu einrichten.

## <a name="transfer-a-domain"></a>Übertragen einer Domäne

1. Wechseln Sie im Admin Center zu   **Einstellungen**   >  **Domänen**.

2. Wählen Sie **auf** der Seite Domänen die Microsoft 365 Domäne aus, die Sie an eine andere Domänenregistrierungsstelle übertragen möchten, und wählen Sie **dann Integrität überprüfen aus.**

3. Wählen Sie oben auf der Seite Die Option **Domäne übertragen aus.**

4. Wählen Sie **auf der Seite Auswählen, wo** Ihre Domäne übertragen werden soll eine andere Registrierungsstelle aus, und klicken Sie dann auf **Weiter**. 

5. Wählen Sie **auf der Seite Domänenübertragung** entsperren **die  >** Option Übertragung <Domäne entsperren aus, und wählen Sie dann **Weiter aus.**

6. Überprüfen Sie ihre Kontaktinformationen für die Domänenübertragung, und wählen Sie dann **Weiter aus.**

7. Kopieren Sie den Autorisierungscode, und warten Sie ca. 30 Minuten, bis Ihr Domänenübertragungsstatus auf der Registerkarte Registrierung zu **Entsperrt** geändert wird, bevor Sie mit den nächsten Schritten fortfahren. 

8. Wechseln Sie zur Website der Domänenregistrierungsstelle, die Sie ihren Domänennamen in Zukunft verwalten möchten. Befolgen Sie die Anweisungen für die Übertragung einer Domäne (suchen Sie auf ihrer Website nach Hilfe). Dies bedeutet in der Regel, dass Sie Übertragungsgebühren zahlen und der neuen Registrierungsstelle den Authcode geben, damit sie die Übertragung initiieren können. Microsoft wird Ihnen eine E-Mail senden, um zu bestätigen, dass wir die Übertragungsanforderung erhalten haben, und die Domäne wird innerhalb von 5 Tagen übertragen.

    Die Registerkarte Autorisierungscoderegistrierung finden Sie auf der  **Seite Domänen** in Microsoft 365. 
    
    > [!TIP]
    > .uk-Domänen erfordern ein anderes Verfahren. Wenden Sie sich an den Microsoft-Support, und fordern Sie eine Änderung des **IPS-Tags** an, um der Registrierungsstelle zu entsprechen, die Sie Ihre Domäne in Zukunft verwalten möchten. Sobald sich das Tag ändert, wird die Domäne sofort an die neue Registrierungsstelle übertragen. Sie müssen dann mit der neuen Registrierungsstelle zusammenarbeiten, um die Übertragung abschließen zu können, und wahrscheinlich Übertragungsgebühren bezahlen und die übertragene Domäne ihrem Konto mit Ihrer neuen Registrierungsstelle hinzufügen.

9. Nachdem die Übertragung abgeschlossen ist, erneuern Sie Ihre Domäne bei der neuen Domänenregistrierungsstelle.

10. Um den Vorgang zu beenden, wechseln Sie zurück zur Seite **Domänen** im Admin Center, und wählen Sie   **dann Domänenübertragung abschließen aus.** Dadurch wird die Domäne als nicht mehr von Microsoft 365 erworben und das Domänenabonnement deaktiviert. Die Domäne wird nicht aus dem Mandanten entfernt und hat keine Auswirkungen auf vorhandene Benutzer und Postfächer in der Domäne.

> [!NOTE]
> Microsoft 365 erworbene Domänen sind nicht berechtigt, Namensserveränderungen vorzunehmen oder die Domäne zwischen Microsoft 365 übertragen. Wenn eine dieser Registrierungen erforderlich ist, muss die Domänenregistrierung an eine andere Registrierungsstelle übertragen werden.
