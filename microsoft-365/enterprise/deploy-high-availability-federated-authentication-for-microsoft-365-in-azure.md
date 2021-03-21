---
title: Bereitstellen der Verbundauthentifizierung mit Hochverfügbarkeit für Microsoft 365 in Azure
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150s
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_Solutions
ms.assetid: 34b1ab9c-814c-434d-8fd0-e5a82cd9bff6
description: 'Zusammenfassung: Konfigurieren der Hochverfügbarkeits-Verbundauthentifizierung für Ihr Microsoft 365-Abonnement in Microsoft Azure.'
ms.openlocfilehash: 3989ebb06b4ac5dfa1cded5e07c086c4778f94e7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919152"
---
# <a name="deploy-high-availability-federated-authentication-for-microsoft-365-in-azure"></a>Bereitstellen der Verbundauthentifizierung mit Hochverfügbarkeit für Microsoft 365 in Azure

Dieser Artikel enthält Links zu den schrittweisen Anweisungen zum Bereitstellen der Hochverfügbarkeits-Verbundauthentifizierung für Microsoft Microsoft 365 in Azure-Infrastrukturdiensten mit diesen virtuellen Computern:
  
- Zwei Webanwendungsproxy-Server
    
- Zwei Active Directory-Verbunddienste (AD FS)
    
- Zwei replizierte Domänencontroller
    
- Ein Verzeichnissynchronisierungsserver, auf dem Azure AD Connect ausgeführt wird.
    
Nachfolgend sehen Sie die Konfiguration mit Platzhalternamen für jeden Server.
  
**Eine Hochverfügbarkeits-Verbundauthentifizierung für Die Microsoft 365-Infrastruktur in Azure**

![Die endgültige Konfiguration der Hochverfügbarkeit der Microsoft 365-Verbundauthentifizierungsinfrastruktur in Azure](../media/c5da470a-f2aa-489a-a050-df09b4d641df.png)
  
Alle virtuellen Computer befinden sich in einem einzigen standortübergreifenden virtuellen Azure-Netzwerk (VNet). 
  
> [!NOTE]
> Für die Verbundauthentifizierung einzelner Benutzer ist kein Rückgriff auf lokale Ressourcen erforderlich. Sollte die standortübergreifende Verbindung jedoch ausfallen, empfangen die Domänencontroller im VNet keine im lokalen AD DS (Active Directory Domain Services) vorgenommenen Updates an Benutzerkonten und Gruppen. Zur Vermeidung eines solchen Szenarios können Sie Hochverfügbarkeit für die standortübergreifende Verbindung konfigurieren. Weitere Informationen finden Sie unter [Standortübergreifende Verbindungen und VNet-zu-VNet-Verbindungen mit hoher Verfügbarkeit](/azure/vpn-gateway/vpn-gateway-highlyavailable).
  
Jedes Paar virtuelle Computer für eine bestimmte Rolle befindet sich in einem eigenen Subnetz und einer eigenen Verfügbarkeitsgruppe.
  
> [!NOTE]
> Da dieses VNet mit dem lokalen Netzwerk verbunden ist, umfasst diese Konfiguration keinen virtuellen Jumpbox- oder Überwachungscomputer in einem Verwaltungssubnetz. Weitere Informationen finden Sie unter [Ausführen von virtuellen Windows-Computern für eine Architektur mit N-Ebenen](/azure/guidance/guidance-compute-n-tier-vm). 
  
Das Ergebnis dieser Konfiguration ist, dass Sie über eine Verbundauthentifizierung für alle Microsoft 365-Benutzer verfügen, in denen sie ihre AD DS-Anmeldeinformationen verwenden können, um sich anstatt ihres Microsoft 365-Kontos zu anmelden. Die Verbundauthentifizierungsinfrastruktur nutzt einen redundanten Satz von Servern, die in den Azure-Infrastrukturdiensten bereitgestellt sind, nicht in Ihrem lokalen Umkreisnetzwerk. Das ist eine deutlich einfacher zu implementierende Konstellation.
  
## <a name="bill-of-materials"></a>Erforderliche Komponenten

Diese geplante Konfiguration erfordert den folgenden Satz von Azure-Diensten und Komponenten:
  
- Sieben virtuelle Computer
    
- Ein standortübergreifendes virtuelles Netzwerk mit vier Subnetzen
    
- Vier Ressourcengruppen
    
- Drei Verfügbarkeitsgruppen.
    
- Ein Azure-Abonnement
    
Nachfolgend sehen Sie die virtuellen Computer und ihre Standardgrößen für diese Konfiguration.
  
|**Element**|**Beschreibung des virtuellen Computers**|**Azure-Katalogbild**|**Standardgröße**|
|:-----|:-----|:-----|:-----|
|1.  <br/> |Erster Domänencontroller  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
|2.  <br/> |Zweiter Domänencontroller  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
|3.  <br/> |Azure AD Connect-Server  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
|4.  <br/> |Erster AD FS-Server
  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
|5.  <br/> |Zweiter AD FS-Server
  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
|6.  <br/> |Erster Webanwendungsproxy-Server
  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
|7.  <br/> |Zweiter Webanwendungsproxy-Server
  <br/> |Windows Server 2016 Datacenter  <br/> |D2  <br/> |
   
Um die geschätzten Kosten für diese Konfiguration zu berechnen, finden Sie unter [Azure-Preisrechner](https://azure.microsoft.com/pricing/calculator/) weitere Informationen.
  
## <a name="phases-of-deployment"></a>Phasen der Bereitstellung

Sie stellen diese Arbeitslast in den folgenden Phasen bereit:
  
- [Phase 1: Konfigurieren von Azure](high-availability-federated-authentication-phase-1-configure-azure.md). Erstellen von Ressourcengruppen, Speicherkonten, Verfügbarkeitsgruppen und einem standortübergreifenden virtuellen Netzwerk.
    
- [Phase 2: Konfigurieren von Domänencontrollern](high-availability-federated-authentication-phase-2-configure-domain-controllers.md). Erstellen und Konfigurieren Sie AD DS-Replikatdomänencontroller und den Verzeichnissynchronisierungsserver.
    
- [Phase 3: Konfigurieren von AD FS-Servern](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md). Erstellen und Konfigurieren der beiden AD FS-Server.
    
- [Phase 4: Konfigurieren von Webanwendungsproxys](high-availability-federated-authentication-phase-4-configure-web-application-pro.md). Erstellen und Konfigurieren der beiden Webanwendungsproxy-Server.
    
- [Phase 5: Konfigurieren der Verbundauthentifizierung für Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md). Konfigurieren Sie die Verbundauthentifizierung für Ihr Microsoft 365-Abonnement.
    
Diese Artikel bieten eine präskriptive, phasenweise Anleitung für eine vordefinierte Architektur zum Erstellen einer funktionalen Verbundauthentifizierung mit hoher Verfügbarkeit für Microsoft 365 in Azure-Infrastrukturdiensten. Denken Sie dabei an Folgendes:
  
- Wenn Sie ein erfahrener AD FS-Implementierer sind, können Sie die Anweisungen in den Phasen 3 und 4 entsprechend anpassen und eine Gruppe von Servern erstellen, die Ihren Anforderungen am besten entspricht. 
    
- Wenn Sie bereits über eine vorhandene Azure-Hybridcloudbereitstellung mit einem vorhandenen standortübergreifenden virtuellen Netzwerk verfügen, können Sie die Anweisungen in den Phasen 1 und 2 entsprechend anpassen oder überspringen und die AD FS-Server und die Webanwendungsproxy-Server in den entsprechenden Subnetzen platzieren.
    
Informationen zum Erstellen einer Entwicklungs-/Testumgebung oder eines Proof-of-Concept dieser Konfiguration finden Sie unter Verbundidentität für Ihre [Microsoft 365-Entwicklungs-/Testumgebung.](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
## <a name="next-step"></a>Nächster Schritt

Starten Sie die Konfiguration dieser Arbeitslast mit [Phase 1: Konfigurieren von Azure](high-availability-federated-authentication-phase-1-configure-azure.md). 
