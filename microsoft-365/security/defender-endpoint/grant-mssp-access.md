---
title: Gewähren des Zugriffs auf verwaltete Sicherheitsdienstanbieter (Managed Security Service Provider, MSSP)
description: Ausführen der erforderlichen Schritte zum Konfigurieren der MSSP-Integration mit Microsoft Defender for Endpoint
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
ms.openlocfilehash: 320355f838db5dbb1540350e95e4cc0645acd805
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932751"
---
# <a name="grant-managed-security-service-provider-mssp-access-preview"></a>Gewähren des Zugriffs auf verwalteten Sicherheitsdienstanbieter (Managed Security Service Provider, MSSP) (Vorschau)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!IMPORTANT] 
>Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

Gehen Sie wie folgt vor, um eine mehr mandantendelegierte Zugriffslösung zu implementieren:

1. Aktivieren [Sie die rollenbasierte Zugriffssteuerung](rbac.md) in Defender for Endpoint, und stellen Sie eine Verbindung mit Active Directory (AD)-Gruppen herzustellen.

2. Konfigurieren [von Governance-Zugriffspaketen](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) für Zugriffsanforderung und -bereitstellung.

3. Verwalten von Zugriffsanforderungen und -überwachungen in [Microsoft Myaccess](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve).

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint"></a>Aktivieren von rollenbasierten Zugriffssteuerelementen in Microsoft Defender for Endpoint

1. **Erstellen von Zugriffsgruppen für MSSP-Ressourcen in Customer AAD: Groups**

    Diese Gruppen werden mit den Rollen verknüpft, die Sie in Defender for Endpoint erstellen. Erstellen Sie dazu im Kunden-AD-Mandanten drei Gruppen. In unserem Beispielansatz erstellen wir die folgenden Gruppen:

    - Tier 1 Analyst 
    - Tier 2 Analyst 
    - Genehmiger von MSSP-Analysten  


2. Erstellen Sie Defender for Endpoint-Rollen für geeignete Zugriffsebenen in Customer Defender for Endpoint.

    Um rbAC im Microsoft Defender Security Center des Kunden zu aktivieren, greifen Sie über ein Benutzerkonto mit globalen Administrator- oder Sicherheitsadministratorrechten auf Einstellungen > Berechtigungen **>** Rollen und "Rollen aktivieren" zu.

    ![Abbildung des MSSP-Zugriffs](images/mssp-access.png)

    Erstellen Sie dann ROLLENAC-Rollen, um die Anforderungen der MSSP-SOC-Ebene zu erfüllen. Verknüpfen Sie diese Rollen mit den erstellten Benutzergruppen über "Zugewiesene Benutzergruppen".

    Zwei mögliche Rollen:

    - **Analysten der Stufe 1** <br>
      Führen Sie alle Aktionen mit Ausnahme von Liveantworten aus und verwalten Sie Sicherheitseinstellungen.

    - **Analysten der Stufe 2** <br>
      Funktionen der Stufe 1 mit der Ergänzung zur [Liveantwort](live-response.md)

    Weitere Informationen finden Sie unter [Verwenden der rollenbasierten Zugriffssteuerung](rbac.md).



## <a name="configure-governance-access-packages"></a>Konfigurieren von Steuerungszugriffspaketen

1.  **Hinzufügen von MSSP als verbundene Organisation in Customer AAD: Identity Governance**
    
    Das Hinzufügen des MSSP als verbundene Organisation ermöglicht dem MSSP das Anfordern und Bereitstellen von Zugriffen. 

    Greifen Sie dazu im Kunden-AD-Mandanten auf Identity Governance: Verbundene Organisation zu. Fügen Sie eine neue Organisation hinzu, und suchen Sie nach Ihrem MSSP Analyst-Mandanten über Mandanten-ID oder Domäne. Wir empfehlen, einen separaten AD-Mandanten für Ihre MSSP-Analysten zu erstellen.

2. **Erstellen eines Ressourcenkatalogs in Customer AAD: Identity Governance**

    Ressourcenkataloge sind eine logische Auflistung von Zugriffspaketen, die im Kunden-AD-Mandanten erstellt wurden.

    Greifen Sie dazu im Kunden-AD-Mandanten auf Identity Governance: Catalogs zu, und fügen Sie **neuen Katalog hinzu.** In unserem Beispiel nennen wir es **MSSP Accesses**. 

    ![Abbildung des neuen Katalogs](images/goverance-catalog.png)

    Weitere Informationen finden Sie unter [Create a catalog of resources](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create).


3. **Erstellen von Zugriffspaketen für MSSP-Ressourcen Customer AAD: Identity Governance**

    Bei Zugriffspaketen handelt es sich um die Sammlung von Rechten und Zugriffen, die einem Anfordernden bei genehmigung erteilt werden. 

    Greifen Sie dazu im Kunden-AD-Mandanten auf Identity Governance: Access Packages zu, und fügen Sie **New Access Package hinzu.** Erstellen Sie ein Zugriffspaket für die MSSP-Genehmiger und die einzelnen Analystenebenen. Die folgende Konfiguration von Tier 1 Analyst erstellt beispielsweise ein Zugriffspaket, das:

    - Erfordert, dass ein Mitglied der **AD-Gruppe MSSP Analyst Approvers** neue Anforderungen autorisiert
    - Verfügt über jährliche Zugriffsüberprüfungen, bei denen die SOC-Analysten eine Zugriffserweiterung anfordern können
    - Kann nur von Benutzern im MSSP-SOC-Mandanten angefordert werden
    - Access auto läuft nach 365 Tagen ab

    > [!div class="mx-imgBorder"]
    > ![Abbildung des neuen Zugriffspakets](images/new-access-package.png)

    Weitere Informationen finden Sie unter [Create a new access package](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create).


4. **Bereitstellen eines Zugriffsanforderungslinks zu MSSP-Ressourcen vom Kunden-AAD: Identity Governance**

    Der Link My Access-Portal wird von MSSP SOC-Analysten verwendet, um zugriff über die erstellten Zugriffspakete an zu fordern. Der Link ist dauerhaft, d. h. derselbe Link kann im Laufe der Zeit für neue Analysten verwendet werden. Die Analystenanforderung wird von den Genehmigern von MSSP Analysten in eine Warteschlange **eingereiht.**

    > [!div class="mx-imgBorder"]
    > ![Abbildung der Zugriffseigenschaften](images/access-properties.png)

    Der Link befindet sich auf der Übersichtsseite der einzelnen Zugriffspakete.

## <a name="manage-access"></a>Zugriff verwalten 

1. Überprüfen und Autorisieren von Zugriffsanforderungen in Customer und/oder MSSP myaccess.

    Zugriffsanforderungen werden im Kunden My Access von Mitgliedern der Gruppe "Genehmiger von MSSP Analysten" verwaltet.

    Greifen Sie dazu auf myaccess des Kunden zu, indem Sie:  `https://myaccess.microsoft.com/@<Customer Domain >` . 

    Beispiel:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`   
2. Genehmigen oder Verweigern von Anforderungen im **Abschnitt Genehmigungen** der Benutzeroberfläche.

    Zu diesem Zeitpunkt wurde der Analystenzugriff bereitgestellt, und jeder Analyst sollte auf das Microsoft Defender Security Center des Kunden zugreifen können: `https://securitycenter.Microsoft.com/?tid=<CustomerTenantId>`

## <a name="related-topics"></a>Verwandte Themen
- [Zugreifen auf das MSSP-Kundenportal](access-mssp-portal.md)
- [Warnungsbenachrichtigungen konfigurieren](configure-mssp-notifications.md)
- [Abrufen von Benachrichtigungen vom Kunden-Mandanten](fetch-alerts-mssp.md)



 

