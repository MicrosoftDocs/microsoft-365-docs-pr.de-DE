---
title: Gewähren des Zugriffs auf verwalteten Sicherheitsdienstanbieter (Managed Security Service Provider, MSSP)
description: Führen Sie die erforderlichen Schritte aus, um die MSSP-Integration mit Microsoft Defender für Endpunkt zu konfigurieren.
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
ms.openlocfilehash: 311903cdd1409f4ab997641cc842ff199ce2500d
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843106"
---
# <a name="grant-managed-security-service-provider-mssp-access-preview"></a>Gewähren des Zugriffs auf verwalteten Sicherheitsdienstanbieter (Managed Security Service Provider, MSSP) (Vorschau)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!IMPORTANT] 
>Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

Führen Sie die folgenden Schritte aus, um eine mehrinstanzenfähige lösung für delegierten Zugriff zu implementieren:

1. Aktivieren Sie [die rollenbasierte Zugriffssteuerung](rbac.md) in Defender für Endpunkt, und stellen Sie eine Verbindung mit Active Directory(AD)-Gruppen her.

2. Konfigurieren von [Governance-Zugriffspaketen](/azure/active-directory/governance/identity-governance-overview) für Zugriffsanfragen und -bereitstellungen.

3. Verwalten von Zugriffsanforderungen und Überwachungen in [Microsoft Myaccess.](/azure/active-directory/governance/entitlement-management-request-approve)

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint"></a>Aktivieren rollenbasierter Zugriffssteuerungen in Microsoft Defender für Endpunkt

1. **Erstellen von Zugriffsgruppen für MSSP-Ressourcen in Customer AAD: Groups**

    Diese Gruppen werden mit den Rollen verknüpft, die Sie in Defender für Endpunkt erstellen. Erstellen Sie dazu im AD-Mandanten des Kunden drei Gruppen. In unserem Beispielansatz erstellen wir die folgenden Gruppen:

    - Analyst der Stufe 1 
    - Analyst der Stufe 2 
    - Genehmiger für MSSP-Analysten  


2. Erstellen Sie Defender für Endpunkt-Rollen für die entsprechenden Zugriffsebenen in Customer Defender für Endpunkt.

    Um RBAC im Microsoft Defender Security Center des Kunden zu aktivieren, greifen Sie über ein Benutzerkonto mit globalen Administrator- oder Sicherheitsadministratorrechten auf **Einstellungen > Berechtigungen > Rollen** und "Rollen aktivieren" zu.

    ![Abbildung des MSSP-Zugriffs](images/mssp-access.png)

    Erstellen Sie dann RBAC-Rollen, um die Anforderungen der MSSP-SOC-Ebene zu erfüllen. Verknüpfen Sie diese Rollen mit den erstellten Benutzergruppen über "Zugewiesene Benutzergruppen".

    Zwei mögliche Rollen:

    - **Analysten der Stufe 1** <br>
      Führen Sie alle Aktionen mit Ausnahme von Liveantworten aus, und verwalten Sie Sicherheitseinstellungen.

    - **Analysten der Stufe 2** <br>
      Funktionen der Stufe 1 mit zusätzlicher [Liveantwort](live-response.md)

    Weitere Informationen finden Sie unter [Verwenden der rollenbasierten Zugriffssteuerung.](rbac.md)



## <a name="configure-governance-access-packages"></a>Konfigurieren von Governance-Zugriffspaketen

1.  **Hinzufügen von MSSP als verbundene Organisation in Customer AAD: Identity Governance**
    
    Das Hinzufügen des MSSP als verbundene Organisation ermöglicht es dem MSSP, Zugriffe anzufordern und bereitzustellen. 

    Greifen Sie dazu im AD-Mandanten des Kunden auf Identity Governance: verbundene Organisation zu. Fügen Sie eine neue Organisation hinzu, und suchen Sie nach Ihrem MSSP-Analystenmandanten über die Mandanten-ID oder Domäne. Wir empfehlen, einen separaten AD-Mandanten für Ihre MSSP-Analysten zu erstellen.

2. **Erstellen eines Ressourcenkatalogs in Customer AAD: Identity Governance**

    Ressourcenkataloge sind eine logische Sammlung von Zugriffspaketen, die im AD-Mandanten des Kunden erstellt werden.

    Greifen Sie dazu im AD-Mandanten des Kunden auf Identity Governance: Kataloge zu, und fügen Sie **neuen Katalog** hinzu. In unserem Beispiel nennen wir es **MSSP Accesses**. 

    ![Abbildung des neuen Katalogs](images/goverance-catalog.png)

    Weitere Informationen finden Sie unter [Erstellen eines Ressourcenkatalogs.](/azure/active-directory/governance/entitlement-management-catalog-create)


3. **Erstellen von Zugriffspaketen für MSSP-Ressourcen Kunden-AAD: Identity Governance**

    Zugriffspakete sind die Sammlung von Rechten und Zugriffen, die einem Anforderer nach Genehmigung gewährt werden. 

    Greifen Sie dazu im AD-Mandanten des Kunden auf Identity Governance zu: Zugriffspakete, und fügen Sie **ein neues Zugriffspaket hinzu.** Erstellen Sie ein Zugriffspaket für die MSSP-Genehmiger und jede Analystenebene. Die folgende Analystenkonfiguration der Stufe 1 erstellt beispielsweise ein Zugriffspaket, das:

    - Erfordert ein Mitglied der AD-Gruppe **MSSP Analyst Approvers,** um neue Anforderungen zu autorisieren
    - Verfügt über jährliche Zugriffsüberprüfungen, bei denen die SOC-Analysten eine Zugriffserweiterung anfordern können.
    - Kann nur von Benutzern im MSSP-SOC-Mandanten angefordert werden
    - Automatischer Zugriff läuft nach 365 Tagen ab

    > [!div class="mx-imgBorder"]
    > ![Abbildung des neuen Zugriffspakets](images/new-access-package.png)

    Weitere Informationen finden Sie unter [Erstellen eines neuen Zugriffspakets.](/azure/active-directory/governance/entitlement-management-access-package-create)


4. **Bereitstellen eines Zugriffsanforderungslinks zu MSSP-Ressourcen von Kunden-AAD: Identity Governance**

    Der My Access-Portallink wird von MSSP SOC-Analysten verwendet, um den Zugriff über die erstellten Zugriffspakete anzufordern. Der Link ist dauerhaft, d. h. derselbe Link kann im Laufe der Zeit für neue Analysten verwendet werden. Die Analystenanforderung wird zur Genehmigung durch die **Genehmigenden von MSSP-Analysten** in eine Warteschlange eingereiht.

    > [!div class="mx-imgBorder"]
    > ![Abbildung der Zugriffseigenschaften](images/access-properties.png)

    Der Link befindet sich auf der Übersichtsseite jedes Zugriffspakets.

## <a name="manage-access"></a>Zugriff verwalten 

1. Überprüfen und autorisieren Sie Zugriffsanforderungen in "Customer" und/oder "MSSP myaccess".

    Zugriffsanfragen werden im Kunden "My Access" von Mitgliedern der Gruppe der Genehmiger für MSSP-Analysten verwaltet.

    Um dies zu tun, greifen Sie auf das MyAccess des Kunden zu, indem Sie:  `https://myaccess.microsoft.com/@<Customer Domain >` . 

    Beispiel:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`   
2. Genehmigen oder Verweigern von Anforderungen im Abschnitt **"Genehmigungen"** der Benutzeroberfläche.

    Zu diesem Zeitpunkt wurde der Analystenzugriff bereitgestellt, und jeder Analyst sollte in der Lage sein, auf die Microsoft Defender Security Center des Kunden zuzugreifen:`https://securitycenter.Microsoft.com/?tid=<CustomerTenantId>`

## <a name="related-topics"></a>Verwandte Themen
- [Zugreifen auf das MSSP-Kundenportal](access-mssp-portal.md)
- [Warnungsbenachrichtigungen konfigurieren](configure-mssp-notifications.md)
- [Abrufen von Benachrichtigungen vom Kunden-Mandanten](fetch-alerts-mssp.md)



 

