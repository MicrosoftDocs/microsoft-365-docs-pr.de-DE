---
title: Pull detections to your SIEM tools from Microsoft Defender for Endpoint
description: Erfahren Sie, wie Sie die REST-API verwenden und unterstützte Sicherheitsinformationen und Ereignisverwaltungstools für den Empfang und das Abrufen von Erkennungen konfigurieren.
keywords: Konfigurieren von Siem, Verwaltungstools für Sicherheitsinformationen und Ereignisse, Splunk, Arcsight, benutzerdefinierte Indikatoren, Rest-API, Warnungsdefinitionen, Kompromissindikatoren
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
ms.openlocfilehash: 97a64c8537ff2a6f9948ed6ed056b8aa7379ce69
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222335"
---
# <a name="pull-detections-to-your-siem-tools"></a>Ziehen von Erkennungen an Ihre SIEM-Tools

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="pull-detections-using-security-information-and-events-management-siem-tools"></a>Pull detections using security information and events management (SIEM) tools

>[!NOTE]
>- [Microsoft Defender for Endpoint Alert](alerts.md) besteht aus einer oder mehreren Erkennungen.
>- [Microsoft Defender for Endpoint Detection](api-portal-mapping.md) besteht aus dem verdächtigen Ereignis, das auf dem Gerät aufgetreten ist, und den zugehörigen Warnungsdetails.
>-Die Microsoft Defender for Endpoint Alert-API ist die neueste API für den Warnungsverbrauch und enthält eine detaillierte Liste verwandter Nachweise für jede Warnung. Weitere Informationen finden Sie unter [Warnungsmethoden und -eigenschaften und](alerts.md) [Warnungen auflisten.](get-alerts.md)

Defender for Endpoint unterstützt Sicherheitsinformations- und Ereignisverwaltungstools (SIEM) zum Ziehen von Erkennungen. Defender for Endpoint macht Warnungen über einen in Azure gehosteten HTTPS-Endpunkt verfügbar. Der Endpunkt kann so konfiguriert werden, dass Erkennungen von Ihrem Unternehmens mandanten in Azure Active Directory (AAD) mithilfe des OAuth 2.0-Authentifizierungsprotokolls für eine AAD-Anwendung, die den spezifischen SIEM-Connector darstellt, der in Ihrer Umgebung installiert ist, verwendet werden.

Defender for Endpoint unterstützt derzeit die folgenden spezifischen SIEM-Lösungstools über ein dediziertes SIEM-Integrationsmodell:

- IBM QRadar
- Micro Focus ArcSight

Andere SIEM-Lösungen (z. B. Splunk, RSA NetWitness) werden über ein anderes Integrationsmodell unterstützt, das auf der neuen Warnungs-API basiert. Weitere Informationen finden Sie auf der [Seite Partneranwendung,](https://securitycenter.microsoft.com/interoperability/partners) und wählen Sie den Abschnitt Sicherheitsinformationen und Analysen aus, um ausführliche Informationen zu erhalten.

Um eines dieser unterstützten SIEM-Tools zu verwenden, müssen Sie:

- [Aktivieren der SIEM-Integration in Defender for Endpoint](enable-siem-integration.md)
- Konfigurieren Des unterstützten SIEM-Tools:
     - [Konfigurieren von Micro Focus ArcSight zum Ziehen von Defender for Endpoint-Erkennungen](configure-arcsight.md)
     - Konfigurieren von IBM QRadar zum Ziehen von Defender for Endpoint-Erkennungen Weitere Informationen finden Sie unter [IBM Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/com.ibm.dsm.doc/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1).

Weitere Informationen zur Liste der in der Erkennungs-API verfügbar gemachten Felder finden Sie unter [Defender for Endpoint Detection fields](api-portal-mapping.md).
