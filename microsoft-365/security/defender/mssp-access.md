---
title: Bereitstellen des Zugriffs auf verwaltete Sicherheitsdienstanbieter (Managed Security Service Provider, MSSP)
description: Erfahren Sie mehr über Änderungen vom Microsoft Defender Security Center zum Microsoft 365 Security Center
keywords: Erste Schritte mit dem Microsoft 365 Security Center, Microsoft Defender für Office 365, Microsoft Defender für Endpunkt, MDO, MDE, einzelner Bereich, konvergentes Portal, Sicherheitsportal, Defender-Sicherheitsportal
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
localization_priority: Normal
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
ms.openlocfilehash: ddc28149ca2ab43b7c14d3bdbaeeecdad1b18387
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289763"
---
# <a name="provide-managed-security-service-provider-mssp-access"></a>Bereitstellen des Zugriffs auf verwaltete Sicherheitsdienstanbieter (Managed Security Service Provider, MSSP) 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Gilt für:**

- [Microsoft 365 Defender](microsoft-365-defender.md)
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Führen Sie die folgenden Schritte aus, um eine mehrinstanzenfähige lösung für delegierten Zugriff zu implementieren:

1. Aktivieren Sie die [rollenbasierte Zugriffssteuerung](/windows/security/threat-protection/microsoft-defender-atp/rbac) in Defender für Endpunkt im Microsoft 365 Security Center, und stellen Sie eine Verbindung mit Azure Active Directory (Azure AD)-Gruppen her.

2. Konfigurieren von [Governance-Zugriffspaketen](/azure/active-directory/governance/identity-governance-overview) für Zugriffsanfragen und -bereitstellungen.

3. Verwalten von Zugriffsanforderungen und Überwachungen in [Microsoft Myaccess.](/azure/active-directory/governance/entitlement-management-request-approve)

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint-in-microsoft-365-security-center"></a>Aktivieren von rollenbasierten Zugriffssteuerungen in Microsoft Defender für Endpunkt im Microsoft 365 Security Center

1. **Erstellen von Zugriffsgruppen für MSSP-Ressourcen in Customer AAD: Groups**

    Diese Gruppen werden mit den Rollen verknüpft, die Sie in Defender für Endpunkt im Microsoft 365 Security Center erstellen. Erstellen Sie dazu im AD-Mandanten des Kunden drei Gruppen. In unserem Beispielansatz erstellen wir die folgenden Gruppen:

    - Analyst der Stufe 1
    - Analyst der Stufe 2
    - Genehmiger für MSSP-Analysten  

2. Erstellen Sie Defender für Endpunkt-Rollen für die entsprechenden Zugriffsebenen in Customer Defender für Endpunkt in Microsoft 365 Sicherheitscenterrollen und -gruppen.

    Um RBAC im Kunden-Microsoft 365 Security Center zu aktivieren, greifen Sie auf **Die Rollen "Berechtigungen > Endpunkte" & Gruppen > Rollen** mit einem Benutzerkonto mit globalen Administrator- oder Sicherheitsadministratorrechten zu.

    ![Abbildung des MSSP-Zugriffs](../../media/mssp-access.png)

    Erstellen Sie dann RBAC-Rollen, um die Anforderungen der MSSP-SOC-Ebene zu erfüllen. Verknüpfen Sie diese Rollen mit den erstellten Benutzergruppen über "Zugewiesene Benutzergruppen".

    Zwei mögliche Rollen:

    - **Analysten der Stufe 1** <br>
      Führen Sie alle Aktionen mit Ausnahme von Liveantworten aus, und verwalten Sie Sicherheitseinstellungen.

    - **Analysten der Stufe 2** <br>
      Funktionen der Stufe 1 mit zusätzlicher [Liveantwort](/windows/security/threat-protection/microsoft-defender-atp/live-response)

    Weitere Informationen finden Sie unter [Verwenden der rollenbasierten Zugriffssteuerung.](/windows/security/threat-protection/microsoft-defender-atp/rbac)

## <a name="configure-governance-access-packages"></a>Konfigurieren von Governance-Zugriffspaketen

1. **Hinzufügen von MSSP als verbundene Organisation in Customer AAD: Identity Governance**

    Das Hinzufügen des MSSP als verbundene Organisation ermöglicht es dem MSSP, Zugriffe anzufordern und bereitzustellen. 

    Greifen Sie dazu im AD-Mandanten des Kunden auf Identity Governance: verbundene Organisation zu. Fügen Sie eine neue Organisation hinzu, und suchen Sie nach Ihrem MSSP-Analystenmandanten über die Mandanten-ID oder Domäne. Wir empfehlen, einen separaten AD-Mandanten für Ihre MSSP-Analysten zu erstellen.

2. **Erstellen eines Ressourcenkatalogs in Customer AAD: Identity Governance**

    Ressourcenkataloge sind eine logische Sammlung von Zugriffspaketen, die im AD-Mandanten des Kunden erstellt werden.

    Greifen Sie dazu im AD-Mandanten des Kunden auf Identity Governance: Kataloge zu, und fügen Sie **neuen Katalog** hinzu. In unserem Beispiel wird es **MSSP Accesses** nennen.

    ![Abbildung des neuen Katalogs](../../media/goverance-catalog.png)

    Weitere Informationen finden Sie unter [Erstellen eines Ressourcenkatalogs.](/azure/active-directory/governance/entitlement-management-catalog-create)

3. **Erstellen von Zugriffspaketen für MSSP-Ressourcen Kunden-AAD: Identity Governance**

    Zugriffspakete sind die Sammlung von Rechten und Zugriffen, die einem Anforderer nach Genehmigung gewährt werden. 

    Greifen Sie dazu im AD-Mandanten des Kunden auf Identity Governance zu: Zugriffspakete, und fügen Sie **ein neues Zugriffspaket hinzu.** Erstellen Sie ein Zugriffspaket für die MSSP-Genehmiger und jede Analystenebene. Die folgende Analystenkonfiguration der Stufe 1 erstellt beispielsweise ein Zugriffspaket, das:

    - Erfordert ein Mitglied der AD-Gruppe **MSSP Analyst Approvers,** um neue Anforderungen zu autorisieren
    - Verfügt über jährliche Zugriffsüberprüfungen, bei denen die SOC-Analysten eine Zugriffserweiterung anfordern können.
    - Kann nur von Benutzern im MSSP-SOC-Mandanten angefordert werden
    - Automatischer Zugriff läuft nach 365 Tagen ab

    ![Abbildung des neuen Zugriffspakets](../../media/new-access-package.png)

    Weitere Informationen finden Sie unter [Erstellen eines neuen Zugriffspakets.](/azure/active-directory/governance/entitlement-management-access-package-create)

4. **Bereitstellen eines Zugriffsanforderungslinks zu MSSP-Ressourcen von Kunden-AAD: Identity Governance**

    Der My Access-Portallink wird von MSSP SOC-Analysten verwendet, um den Zugriff über die erstellten Zugriffspakete anzufordern. Der Link ist dauerhaft, d. h. derselbe Link kann im Laufe der Zeit für neue Analysten verwendet werden. Die Analystenanforderung wird zur Genehmigung durch die **Genehmigenden von MSSP-Analysten** in eine Warteschlange eingereiht.

    ![Abbildung der Zugriffseigenschaften](../../media/access-properties.png)

    Der Link befindet sich auf der Übersichtsseite jedes Zugriffspakets.

## <a name="manage-access"></a>Zugriff verwalten

1. Überprüfen und autorisieren Sie Zugriffsanforderungen in "Customer" und/oder "MSSP myaccess".

    Zugriffsanfragen werden im Kunden "My Access" von Mitgliedern der Gruppe der Genehmiger für MSSP-Analysten verwaltet.

    Um dies zu tun, greifen Sie auf das MyAccess des Kunden zu, indem Sie: `https://myaccess.microsoft.com/@<Customer Domain>` .

    Beispiel: `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`

2. Genehmigen oder Verweigern von Anforderungen im Abschnitt **"Genehmigungen"** der Benutzeroberfläche.

     Zu diesem Zeitpunkt wurde der Analystenzugriff bereitgestellt, und jeder Analyst sollte in der Lage sein, auf das Microsoft 365 Security Center des Kunden zuzugreifen:

    `https://security.microsoft.com/?tid=<CustomerTenantId>` mit den Berechtigungen und Rollen, die ihnen zugewiesen wurden.

> [!IMPORTANT]
> Der delegierte Zugriff auf Microsoft Defender für Endpunkt im Microsoft 365 Security Center ermöglicht derzeit den Zugriff auf einen einzelnen Mandanten pro Browserfenster.
