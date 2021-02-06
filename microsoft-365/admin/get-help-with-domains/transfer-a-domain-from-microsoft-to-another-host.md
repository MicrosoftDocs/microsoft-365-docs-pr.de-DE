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

Sie können eine Microsoft 365-Domäne nach dem Kauf der Domäne von Microsoft 60 Tage lang nicht an eine andere Registrierungsstelle übertragen.

> [!NOTE]
> Eine _Whois-Abfrage_   zeigt eine von Microsoft erworbene Domänenregistrierungsstelle als Wild West Domains LLC an. Allerdings sollte nur Microsoft bezüglich Ihrer von Microsoft 365 erworbenen Domäne kontaktiert werden.

Führen Sie die folgenden Schritte aus, um einen Code bei Microsoft 365 zu erhalten, und wechseln Sie dann zur anderen Website der Domänenregistrierungsstelle, um die Übertragung Ihres Domänennamens an die neue Registrierungsstelle einrichten.

## <a name="transfer-a-domain"></a>Übertragen einer Domäne

1. Wechseln Sie im Admin Center zu  **"Einstellungsdomänen".**   >  

2. Wählen Sie **auf der Seite** "Domänen" die Microsoft 365-Domäne aus, die Sie an eine andere Domänenregistrierungsstelle übertragen möchten, und wählen Sie dann **"Integrität überprüfen" aus.**

3. Wählen Sie oben auf der Seite **"Domäne übertragen" aus.**

4. Wählen Sie **auf der Seite "Wählen** Sie aus, wo Ihre Domäne übertragen werden soll" **eine** andere Registrierungsstelle aus, und klicken Sie dann auf **"Weiter".**

5. Wählen Sie **auf der Seite "Domänenübertragung** entsperren" **die  >** Option "Übertragung für <Domäne entsperren" aus, und wählen Sie dann **"Weiter" aus.**

6. Überprüfen Sie die Kontaktinformationen für die Domänenübertragung, und wählen Sie dann **"Weiter" aus.**

7. Kopieren Sie den Autorisierungscode, und warten Sie etwa  30 Minuten,  bis ihr Domänenübertragungsstatus auf der Registerkarte "Registrierung" in "Entsperrt" geändert wird, bevor Sie mit den nächsten Schritten fortfahren.

8. Wechseln Sie zur Website der Domänenregistrierungsstelle, die Sie in Zukunft verwalten möchten. Befolgen Sie die Anweisungen zum Übertragen einer Domäne (suchen Sie auf ihrer Website nach Hilfe). Dies bedeutet normalerweise, dass Sie Übertragungsgebühren bezahlen und den Authentifizierungscode an die neue Registrierungsstelle überstellen, damit sie die Übertragung initiieren können. Microsoft benachrichtigt Sie per E-Mail, um zu bestätigen, dass wir die Übertragungsanforderung erhalten haben, und die Domäne wird innerhalb von 5 Tagen übertragen.

    Die Registerkarte "Registrierung  des Autorisierungscodes" finden Sie auf der Seite  **"Domänen"** in Microsoft 365.
    
    > [!TIP]
    > Für .uk-Domänen ist ein anderes Verfahren erforderlich. Wenden Sie sich an den Microsoft-Support, und fordern Sie eine Änderung des **IPS-Tags** an, die mit der Registrierungsstelle übereinstimmen soll, die Sie in Zukunft verwalten möchten. Sobald sich das Tag ändert, wird die Domäne sofort an die neue Registrierungsstelle übertragen. Sie müssen dann mit der neuen Registrierungsstelle zusammenarbeiten, um die Übertragung abschließen zu können, und wahrscheinlich Übertragungsgebühren bezahlen und die übertragene Domäne zu Ihrem Konto mit Ihrer neuen Registrierungsstelle hinzufügen.

9. Nach Abschluss der Übertragung erneuern Sie Ihre Domäne bei der neuen Domänenregistrierungsstelle.

10. Um den Vorgang zu beenden, wechseln Sie zurück zur Seite **"Domänen"** im Admin Center, und wählen Sie dann   **"Domänenübertragung abschließen" aus.** Dadurch wird die Domäne als nicht mehr von Microsoft 365 erworben und deaktiviert das Domänenabonnement. Die Domäne wird nicht aus dem Mandanten entfernt und wirkt sich nicht auf vorhandene Benutzer und Postfächer in der Domäne aus.

> [!NOTE]
> Von Microsoft 365 erworbene Domänen sind nicht berechtigt, Namensserveränderungen vorzunehmen oder die Domäne zwischen Microsoft 365-Organisationen zu übertragen. Wenn eine dieser Beiden erforderlich ist, muss die Domänenregistrierung auf eine andere Registrierungsstelle übertragen werden.
