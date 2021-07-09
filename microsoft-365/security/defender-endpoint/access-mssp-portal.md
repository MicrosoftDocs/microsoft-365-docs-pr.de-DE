---
title: Zugreifen auf das Microsoft 365 Defender MSSP-Kundenportal
description: Zugreifen auf das Microsoft 365 Defender MSSP-Kundenportal
keywords: managed security service provider, mssp, configure, integration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8583b28adecd892ec6875faa934fd7ab08e5db11
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339586"
---
# <a name="access-the-microsoft-365-defender-mssp-customer-portal"></a>Zugreifen auf das Microsoft 365 Defender MSSP-Kundenportal

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

>Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)




>[!NOTE] 
>Diese Schritte werden an den MSSP weitergeleitet. 

Mssp-Kunden greifen standardmäßig über die folgende URL auf ihren Microsoft Defender Security Center Mandanten `https://securitycenter.windows.com` zu:
 

MSSPs müssen jedoch eine mandantenspezifische URL im folgenden Format verwenden:  `https://securitycenter.windows.com?tid=customer_tenant_id` für den Zugriff auf das MSSP-Kundenportal. 

Im Allgemeinen müssen MSSPs jedem Azure AD des MSSP-Kunden hinzugefügt werden, den er verwalten möchte.


Führen Sie die folgenden Schritte aus, um die MSSP-Kundenmandanten-ID abzurufen, und verwenden Sie dann die ID, um auf die mandantenspezifische URL zuzugreifen:

1. Melden Sie sich als MSSP mit Ihren Anmeldeinformationen bei Azure AD an. 

2. Wechseln Sie zum Verzeichnis zum Mandanten des MSSP-Kunden.

3.  Wählen Sie **Azure Active Directory > Eigenschaften** aus. Sie finden die Mandanten-ID im Verzeichnis-ID-Feld. 

4. Greifen Sie auf das MSSP-Kundenportal zu, indem Sie den `customer_tenant_id` Wert in der folgenden URL ersetzen: `https://securitycenter.windows.com?tid=customer_tenant_id` .


## <a name="related-topics"></a>Verwandte Themen
- [Gewähren von MSSP-Zugriff auf das Portal](grant-mssp-access.md)
- [Warnungsbenachrichtigungen konfigurieren](configure-mssp-notifications.md)
- [Abrufen von Benachrichtigungen vom Kunden-Mandanten](fetch-alerts-mssp.md)
