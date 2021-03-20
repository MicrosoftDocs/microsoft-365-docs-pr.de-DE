---
title: Bereitstellen des Zugriffs auf verwaltete Sicherheitsdienstanbieter (Managed Security Service Provider, MSSP)
description: Informationen zu Änderungen vom Microsoft Defender Security Center zum Microsoft 365 Security Center
keywords: Erste Schritte mit dem Microsoft 365 Security Center, OATP, MDATP, MDO, MDE, einzelnem Fensterausschnitt, konvergenten Portal, Sicherheitsportal, Defender-Sicherheitsportal
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: db9279ba1bc5fe11f3a31884a05b4403f0cb67f3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906700"
---
# <a name="provide-managed-security-service-provider-mssp-access"></a>Bereitstellen des Zugriffs auf verwaltete Sicherheitsdienstanbieter (Managed Security Service Provider, MSSP) 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Gilt für:**

- [Microsoft 365 Defender](./microsoft-threat-protection.md)
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)

Gehen Sie wie folgt vor, um eine mehr mandantendelegierte Zugriffslösung zu implementieren:

1. Aktivieren [Sie die rollenbasierte Zugriffssteuerung](/windows/security/threat-protection/microsoft-defender-atp/rbac) in Defender for Endpoint im Microsoft 365 Security Center, und stellen Sie eine Verbindung mit Azure Active Directory (Azure AD)-Gruppen bereit.

2. Konfigurieren [von Governance-Zugriffspaketen](/azure/active-directory/governance/identity-governance-overview) für Zugriffsanforderung und -bereitstellung.

3. Verwalten von Zugriffsanforderungen und -überwachungen in [Microsoft Myaccess](/azure/active-directory/governance/entitlement-management-request-approve).

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint-in-microsoft-365-security-center"></a>Aktivieren von rollenbasierten Zugriffssteuerelementen in Microsoft Defender for Endpoint im Microsoft 365 Security Center

1. **Erstellen von Zugriffsgruppen für MSSP-Ressourcen in Customer AAD: Groups**

    Diese Gruppen werden mit den Rollen verknüpft, die Sie in Defender for Endpoint im Microsoft 365 Security Center erstellen. Erstellen Sie dazu im Kunden-AD-Mandanten drei Gruppen. In unserem Beispielansatz erstellen wir die folgenden Gruppen:

    - Tier 1 Analyst 
    - Tier 2 Analyst 
    - Genehmiger von MSSP-Analysten  


2. Erstellen Sie Defender for Endpoint-Rollen für geeignete Zugriffsebenen in Customer Defender for Endpoint in Microsoft 365 Security Center-Rollen und -Gruppen.

    Um rbAC im Microsoft 365 Security Center des Kunden zu aktivieren, greifen Sie auf Berechtigungen > Endpunktrollen & Gruppen **>** Rollen mit einem Benutzerkonto mit globalen Administrator- oder Sicherheitsadministratorrechten zu.

    ![Abbildung des MSSP-Zugriffs](../../media/mssp-access.png)

    Erstellen Sie dann ROLLENAC-Rollen, um die Anforderungen der MSSP-SOC-Ebene zu erfüllen. Verknüpfen Sie diese Rollen mit den erstellten Benutzergruppen über "Zugewiesene Benutzergruppen".

    Zwei mögliche Rollen:

    - **Analysten der Stufe 1** <br>
      Führen Sie alle Aktionen mit Ausnahme von Liveantworten aus und verwalten Sie Sicherheitseinstellungen.

    - **Analysten der Stufe 2** <br>
      Funktionen der Stufe 1 mit der Ergänzung zur [Liveantwort](/windows/security/threat-protection/microsoft-defender-atp/live-response)

    Weitere Informationen finden Sie unter [Verwenden der rollenbasierten Zugriffssteuerung](/windows/security/threat-protection/microsoft-defender-atp/rbac).



## <a name="configure-governance-access-packages"></a>Konfigurieren von Steuerungszugriffspaketen

1.  **Hinzufügen von MSSP als verbundene Organisation in Customer AAD: Identity Governance**
    
    Das Hinzufügen des MSSP als verbundene Organisation ermöglicht dem MSSP das Anfordern und Bereitstellen von Zugriffen. 

    Greifen Sie dazu im Kunden-AD-Mandanten auf Identity Governance: Verbundene Organisation zu. Fügen Sie eine neue Organisation hinzu, und suchen Sie nach Ihrem MSSP Analyst-Mandanten über Mandanten-ID oder Domäne. Wir empfehlen, einen separaten AD-Mandanten für Ihre MSSP-Analysten zu erstellen.

2. **Erstellen eines Ressourcenkatalogs in Customer AAD: Identity Governance**

    Ressourcenkataloge sind eine logische Auflistung von Zugriffspaketen, die im Kunden-AD-Mandanten erstellt wurden.

    Greifen Sie dazu im Kunden-AD-Mandanten auf Identity Governance: Catalogs zu, und fügen Sie **neuen Katalog hinzu.** In unserem Beispiel nennen wir es **MSSP Accesses**. 

    ![Abbildung des neuen Katalogs](../../media/goverance-catalog.png)

    Weitere Informationen finden Sie unter [Create a catalog of resources](/azure/active-directory/governance/entitlement-management-catalog-create).


3. **Erstellen von Zugriffspaketen für MSSP-Ressourcen Customer AAD: Identity Governance**

    Bei Zugriffspaketen handelt es sich um die Sammlung von Rechten und Zugriffen, die einem Anfordernden bei genehmigung erteilt werden. 

    Greifen Sie dazu im Kunden-AD-Mandanten auf Identity Governance: Access Packages zu, und fügen Sie **New Access Package hinzu.** Erstellen Sie ein Zugriffspaket für die MSSP-Genehmiger und die einzelnen Analystenebenen. Die folgende Konfiguration von Tier 1 Analyst erstellt beispielsweise ein Zugriffspaket, das:

    - Erfordert, dass ein Mitglied der **AD-Gruppe MSSP Analyst Approvers** neue Anforderungen autorisiert
    - Verfügt über jährliche Zugriffsüberprüfungen, bei denen die SOC-Analysten eine Zugriffserweiterung anfordern können
    - Kann nur von Benutzern im MSSP-SOC-Mandanten angefordert werden
    - Access auto läuft nach 365 Tagen ab

    ![Abbildung des neuen Zugriffspakets](../../media/new-access-package.png)

    Weitere Informationen finden Sie unter [Create a new access package](/azure/active-directory/governance/entitlement-management-access-package-create).


4. **Bereitstellen eines Zugriffsanforderungslinks zu MSSP-Ressourcen vom Kunden-AAD: Identity Governance**

    Der Link My Access-Portal wird von MSSP SOC-Analysten verwendet, um zugriff über die erstellten Zugriffspakete an zu fordern. Der Link ist dauerhaft, d. h. derselbe Link kann im Laufe der Zeit für neue Analysten verwendet werden. Die Analystenanforderung wird von den Genehmigern von MSSP Analysten in eine Warteschlange **eingereiht.**


    ![Abbildung der Zugriffseigenschaften](../../media/access-properties.png)

    Der Link befindet sich auf der Übersichtsseite der einzelnen Zugriffspakete.

## <a name="manage-access"></a>Zugriff verwalten 

1. Überprüfen und Autorisieren von Zugriffsanforderungen in Customer und/oder MSSP myaccess.

    Zugriffsanforderungen werden im Kunden My Access von Mitgliedern der Gruppe "Genehmiger von MSSP Analysten" verwaltet.

    Greifen Sie dazu auf myaccess des Kunden zu, indem Sie:  `https://myaccess.microsoft.com/@<Customer Domain >` . 

    Beispiel:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`   
2. Genehmigen oder Verweigern von Anforderungen im **Abschnitt Genehmigungen** der Benutzeroberfläche.

     Zu diesem Zeitpunkt wurde der Analystenzugriff bereitgestellt, und jeder Analyst sollte auf das Microsoft 365 Security Center des Kunden zugreifen können: 

    `https://security.microsoft.com/?tid=<CustomerTenantId>` mit den Berechtigungen und Rollen, denen sie zugewiesen wurden.

> [!IMPORTANT]
> Der delegierte Zugriff auf Microsoft Defender for Endpoint im Microsoft 365 Security Center ermöglicht derzeit den Zugriff auf einen einzelnen Mandanten pro Browserfenster.