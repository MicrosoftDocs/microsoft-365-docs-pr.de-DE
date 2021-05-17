---
title: Zugreifen auf das Microsoft Defender Security Center MSSP-Kundenportal
description: Zugreifen auf das Microsoft Defender Security Center MSSP-Kundenportal
keywords: Managed Security Service Provider, mssp, configure, integration
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
ms.openlocfilehash: 97122decede91e8b4f059b3b66999ac12b300172
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164857"
---
# <a name="access-the-microsoft-defender-security-center-mssp-customer-portal"></a>Zugreifen auf das Microsoft Defender Security Center MSSP-Kundenportal

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

>Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)




>[!NOTE] 
>Diese Schritte richten sich an den MSSP. 

Standardmäßig greifen MSSP-Kunden über die folgende URL auf Microsoft Defender Security Center Mandanten zu: `https://securitycenter.windows.com` .
 

MSSPs müssen jedoch eine mandantenspezifische URL im folgenden Format verwenden: für den Zugriff  `https://securitycenter.windows.com?tid=customer_tenant_id` auf das MSSP-Kundenportal. 

Im Allgemeinen müssen MSSPs jedem Azure AD des MSSP-Kunden hinzugefügt werden, den er verwalten möchte.


Verwenden Sie die folgenden Schritte, um die MSSP-Kunden-Mandanten-ID zu erhalten, und verwenden Sie dann die ID, um auf die mandantenspezifische URL zu zugreifen:

1. Melden Sie sich als MSSP mit Ihren Anmeldeinformationen bei Azure AD an. 

2. Wechseln Sie zum Mandanten des MSSP-Kunden.

3.  Wählen **Azure Active Directory > Eigenschaften aus.** Sie finden die Mandanten-ID im Feld Verzeichnis-ID. 

4. Greifen Sie auf das MSSP-Kundenportal zu, indem Sie den `customer_tenant_id` Wert in der folgenden URL ersetzen: `https://securitycenter.windows.com?tid=customer_tenant_id` .


## <a name="related-topics"></a>Verwandte Themen
- [Gewähren von MSSP-Zugriff auf das Portal](grant-mssp-access.md)
- [Warnungsbenachrichtigungen konfigurieren](configure-mssp-notifications.md)
- [Abrufen von Benachrichtigungen vom Kunden-Mandanten](fetch-alerts-mssp.md)
