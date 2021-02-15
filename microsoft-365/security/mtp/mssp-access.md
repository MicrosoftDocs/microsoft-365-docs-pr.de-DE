---
title: Microsoft Defender für Endpunkt im Microsoft 365 Security Center
description: Erfahren Sie mehr über Änderungen vom Microsoft Defender Security Center zum Microsoft 365 Security Center
keywords: Erste Schritte mit dem Microsoft 365 Security Center, OATP, MDATP, MDO, MDE, einzelner Bereich, zusammengeführtes Portal, Sicherheitsportal, Defender-Sicherheitsportal
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
ms.openlocfilehash: 96d5a3bdbd0acbf428f01cc3bb5afefaa95950b4
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242963"
---
# <a name="provide-managed-security-service-provider-mssp-access"></a>Bereitstellen des Zugriffs auf verwaltete Sicherheitsdienstanbieter (Managed Security Service Provider, MSSP) 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Gilt für:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)

Gehen Sie wie folgt vor, um eine lösung mit delegiertem Zugriff mit mehreren Mandanten zu implementieren:

1. Aktivieren [Sie die rollenbasierte Zugriffssteuerung](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac) in Defender for Endpoint im Microsoft 365 Security Center, und stellen Sie eine Verbindung mit Azure Active Directory (Azure AD)-Gruppen bereit.

2. Konfigurieren [sie Steuerungszugriffspakete](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) für Zugriffsanforderung und -bereitstellung.

3. Verwalten von Zugriffsanforderungen und Überwachungen in [Microsoft Myaccess](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve).

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint-in-microsoft-365-security-center"></a>Aktivieren von rollenbasierten Zugriffssteuerungen in Microsoft Defender for Endpoint im Microsoft 365 Security Center

1. **Erstellen von Zugriffsgruppen für MSSP-Ressourcen in Kunden-AAD: Gruppen**

    Diese Gruppen werden mit den Rollen verknüpft, die Sie in Defender for Endpoint im Microsoft 365 Security Center erstellen. Erstellen Sie dazu im Kunden-AD-Mandanten drei Gruppen. In unserem Beispielansatz erstellen wir die folgenden Gruppen:

    - Analyst der Stufe 1 
    - Analyst der Stufe 2 
    - Genehmigende Genehmiger für msSP-Analysten  


2. Erstellen Sie Defender für Endpunktrollen für geeignete Zugriffsebenen in Customer Defender for Endpoint in Microsoft 365 Security Center-Rollen und -Gruppen.

    Um rbAC im Microsoft 365 Security Center des Kunden zu aktivieren, greifen Sie auf Berechtigungen > Endpunktrollen & Gruppen **>** Rollen mit einem Benutzerkonto mit globalen Administrator- oder Sicherheitsadministratorrechten zu.

    ![Abbildung des MSSP-Zugriffs](../../media/mssp-access.png)

    Erstellen Sie dann rollen rbAC-Rollen, um die Anforderungen der MSSP-SOC-Ebene zu erfüllen. Verknüpfen Sie diese Rollen mit den erstellten Benutzergruppen über "Zugewiesene Benutzergruppen".

    Zwei mögliche Rollen:

    - **Analysten der Stufe 1** <br>
      Führen Sie alle Aktionen mit Ausnahme der Liveantwort aus, und verwalten Sie Sicherheitseinstellungen.

    - **Analysten der Stufe 2** <br>
      Funktionen der Stufe 1 mit der Ergänzung zur [Liveantwort](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)

    Weitere Informationen finden Sie unter [Verwenden der rollenbasierten Zugriffssteuerung.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)



## <a name="configure-governance-access-packages"></a>Konfigurieren von Steuerungszugriffspaketen

1.  **Hinzufügen von MSSP als verbundene Organisation in Customer AAD: Identity Governance**
    
    Das Hinzufügen des MSSP als verbundene Organisation ermöglicht dem MSSP das Anfordern und Bereitstellen von Zugriffen. 

    Greifen Sie dazu im Kunden-AD-Mandanten auf "Identity Governance: Verbundene Organisation" zu. Fügen Sie eine neue Organisation hinzu, und suchen Sie über die Mandanten-ID oder Domäne nach Ihrem MSSP-Analysten-Mandanten. Wir empfehlen die Erstellung eines separaten AD-Mandanten für Ihre MSSP-Analysten.

2. **Erstellen eines Ressourcenkatalogs in Customer AAD: Identity Governance**

    Ressourcenkataloge sind eine logische Sammlung von Zugriffspaketen, die im Kunden-AD-Mandanten erstellt werden.

    Greifen Sie dazu im Kunden-AD-Mandanten auf Identity Governance zu: Kataloge, und fügen Sie **einen neuen Katalog hinzu.** In unserem Beispiel nennen wir es **MSSP Accesses**. 

    ![Abbildung des neuen Katalogs](../../media/goverance-catalog.png)

    Weitere Informationen finden Sie unter [Erstellen eines Ressourcenkatalogs.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create)


3. **Erstellen von Zugriffspaketen für die MSSP-Ressourcen Customer AAD: Identity Governance**

    Zugriffspakete sind die Sammlung von Rechten und Zugriffen, die einem Anfordernden bei genehmigung erteilt werden. 

    Greifen Sie dazu im Kunden-AD-Mandanten auf Identity Governance zu: Access-Pakete, und fügen Sie **ein neues Zugriffspaket hinzu.** Erstellen Sie ein Zugriffspaket für die genehmigen msSP-Genehmiger und die einzelnen Analystenebenen. Mit der folgenden Konfiguration der Stufe 1 wird beispielsweise ein Zugriffspaket erstellt, das:

    - Erfordert ein Mitglied der AD-Gruppe **MSSP Analyst Approvers,** um neue Anforderungen zu autorisieren
    - Verfügt über jährliche Zugriffsüberprüfungen, bei denen die SOC-Analysten eine Zugriffserweiterung anfordern können
    - Kann nur von Benutzern im MSSP-SOC-Mandanten angefordert werden
    - Access auto läuft nach 365 Tagen ab

    ![Abbildung des neuen Zugriffspakets](../../media/new-access-package.png)

    Weitere Informationen finden Sie unter [Erstellen eines neuen Zugriffspakets.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create)


4. **Bereitstellen eines Zugriffsanforderungslinks zu den MSSP-Ressourcen von Customer AAD: Identity Governance**

    Der My Access-Portal-Link wird von MSSP-SOC-Analysten verwendet, um den Zugriff über die erstellten Zugriffspakete an verlangen. Der Link ist dauerhaft, d. h., derselbe Link kann im Laufe der Zeit für neue Analysten verwendet werden. Die Analystenanfrage wird zur Genehmigung durch die Genehmiger des MSSP Analysten in eine Warteschlange **eingereiht.**


    ![Abbildung der Zugriffseigenschaften](../../media/access-properties.png)

    Der Link befindet sich auf der Übersichtsseite jedes Zugriffspakets.

## <a name="manage-access"></a>Zugriff verwalten 

1. Überprüfen und autorisieren Sie Zugriffsanforderungen in Customer und/oder MSSP myaccess.

    Zugriffsanforderungen werden im Kunden "My Access" von Mitgliedern der Gruppe "MsSP Analyst Approvers" verwaltet.

    Greifen Sie dazu auf den MyAccess des Kunden zu, indem Sie:  `https://myaccess.microsoft.com/@<Customer Domain >` . 

    Beispiel:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`   
2. Genehmigen oder Verweigern von Anforderungen im Abschnitt **"Genehmigungen"** der Benutzeroberfläche.

     Zu diesem Zeitpunkt wurde der Analystenzugriff bereitgestellt, und jeder Analyst sollte auf das Microsoft 365 Security Center des Kunden zugreifen können: 

    `https://security.microsoft.com/?tid=<CustomerTenantId>` mit den Berechtigungen und Rollen, denen sie zugewiesen wurden.

> [!IMPORTANT]
> Der delegierte Zugriff auf Microsoft Defender for Endpoint im Microsoft 365 Security Center ermöglicht derzeit den Zugriff auf einen einzelnen Mandanten pro Browserfenster. 