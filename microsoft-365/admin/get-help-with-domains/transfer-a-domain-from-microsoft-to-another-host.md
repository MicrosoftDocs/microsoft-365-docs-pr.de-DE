---
title: Übertragen einer Domäne von Microsoft auf einen anderen Host
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: 'Hier finden Sie die Schritte zum Übertragen einer Domäne von Microsoft an eine andere Registrierungsstelle. '
ms.openlocfilehash: d960b57a2c82b804d61ead1c672c00f0543b3ae8
ms.sourcegitcommit: 33afa334328cc4e3f2474abd611c1411adabd39f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "48370324"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a>Übertragen einer Domäne von Microsoft auf einen anderen Host

Sie können eine Microsoft 365-Domäne nicht für 60 Tage nach dem Erwerb der Domäne von Microsoft an eine andere Registrierungsstelle übertragen.

> [!NOTE]
> Eine _Whois_   -Abfrage zeigt eine von Microsoft erworbene Domänenregistrierungsstelle als Wild West Domains LLC. Allerdings sollte nur Microsoft bezüglich ihrer erworbenen Microsoft 365-Domäne kontaktiert werden.

Führen Sie die folgenden Schritte aus, um einen Code bei Microsoft 365 zu erhalten, und wechseln Sie dann zur anderen Domänenregistrierungsstellen-Website, um die Übertragung Ihres Domänennamens auf die neue Registrierungsstelle einzurichten.

## <a name="transfer-a-domain"></a>Übertragen einer Domäne

1. Wechseln Sie im Admin Center zu  **Einstellungen**   >  **Domänen**.

2. Wählen Sie auf der Seite **Domänen** die Microsoft 365-Domäne aus, die Sie an eine andere Domänenregistrierungsstelle übertragen möchten, und wählen Sie dann **Integrität überprüfen**aus.

3. Wählen Sie oben auf der Seite **Domäne übertragen**aus.

4. Wählen Sie auf der Seite Wählen Sie aus, **wo die Domäne übertragen werden soll** **eine andere Registrierungs**Stelle aus, und klicken Sie dann auf **weiter**.

5. Wählen Sie auf der Seite **Domänen Übertragung entsperren** die Option **Übertragung für <_Ihrer Domäne_ > entsperren**aus, und wählen Sie dann **weiter**aus.

6. Überprüfen Sie Ihre Domänen Übertragungs Kontaktinformationen, und wählen Sie dann **weiter**aus.

7. Kopieren Sie den Autorisierungscode, und warten Sie etwa 30 Minuten, bis Ihr Domänen Übertragungsstatus auf der Registerkarte **Registrierung** auf für **Übertragung für entsperrt** geändert wurde, bevor Sie mit den nächsten Schritten fortfahren.

8. Wechseln Sie zur Website der Domänenregistrierungsstelle, für die Sie Ihren Domänennamen weiterleiten möchten. Befolgen Sie die Anweisungen für die Übertragung einer Domäne (Suche nach Hilfe auf Ihrer Website). Dies bedeutet normalerweise, dass Sie Überweisungsgebühren bezahlen und dem neuen Registrar die AuthCode geben, damit Sie die Übertragung initiieren können. Microsoft wird Ihnen eine e-Mail senden, um zu bestätigen, dass die Übertragungsanforderung empfangen wurde, und die Domäne wird innerhalb von 5 Tagen übertragen.

    Die Registerkarte Autorisierungscode **Registrierung** befindet sich auf der Seite  **Domänen** in Microsoft 365.
    
    > [!TIP]
    > . uk-Domänen erfordern ein anderes Verfahren. Wenden Sie sich an den Microsoft-Support, und fordern Sie eine **IPS-Tag-Änderung** an, die der Registrierungsstelle entspricht, für die Sie Ihre Domäne verwalten möchten. Nachdem sich das Tag geändert hat, wird die Domäne sofort an die neue Registrierungsstelle übertragen. Anschließend müssen Sie mit der neuen Registrierungsstelle zusammenarbeiten, um die Übertragung abzuschließen, wahrscheinlich Gebühren für die Übertragung zu bezahlen und die übertragene Domäne Ihrem Konto bei ihrer neuen Registrierungsstelle hinzuzufügen.

9. Nach Abschluss der Übertragung erneuern Sie Ihre Domäne bei der neuen Domänenregistrierungsstelle.

10. Um den Vorgang abzuschließen, wechseln Sie zurück zur Seite **Domänen** im Admin Center, und wählen Sie dann  **vollständige Domänen Übertragung**aus. Dadurch wird die Domäne als nicht mehr erworben von Microsoft 365 gekennzeichnet, und das Domänen Abonnement wird deaktiviert. Die Domäne wird nicht aus dem Mandanten entfernt, und es werden keine Auswirkungen auf vorhandene Benutzer und Postfächer in der Domäne gehabt.

> [!NOTE]
> Erworbene Microsoft 365-Domänen sind nicht für Namenserver Änderungen oder die Übertragung der Domäne zwischen Microsoft 365-Organisationen berechtigt. Wenn eine dieser Anforderungen erforderlich ist, muss die Domänenregistrierung an eine andere Registrierungsstelle übertragen werden.
