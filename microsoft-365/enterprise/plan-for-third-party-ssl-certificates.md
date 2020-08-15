---
title: Planen von Drittanbieter-SSL-Zertifikaten für Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.date: 05/15/2019
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: b48cdf63-07e0-4cda-8c12-4871590f59ce
description: 'Zusammenfassung: Beschreibung der SSL-Zertifikate, die für lokale und hybride Exchange-Dienste erforderlich sind, SSO mit AD FS, Exchange Online Diensten und Exchange Webdienste.'
ms.openlocfilehash: 1738e4c316772d928138adc654372bd0b9efae65
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690534"
---
# <a name="plan-for-third-party-ssl-certificates-for-microsoft-365"></a>Planen von Drittanbieter-SSL-Zertifikaten für Microsoft 365

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Zum Verschlüsseln der Kommunikation zwischen ihren Clients und der Microsoft 365-Umgebung müssen SSL-Zertifikate (Secure Socket Layer) von Drittanbietern auf Ihren Infrastrukturservern installiert sein.

Dieser Artikel ist Teil der [Netzwerkplanung und Leistungsoptimierung für Microsoft 365](https://aka.ms/tune).
   
Zertifikate sind für die folgenden Microsoft 365-Komponenten erforderlich:
  
- Exchange lokal
    
- Einmaliges Anmelden (SSO) (sowohl für die Active Directory Verbunddienste (AD FS)-Verbundserver als auch für AD FS-Verbundserverproxys)
    
- Exchange Online Dienste, wie AutoErmittlung, Outlook Anywhere und Exchange Webdienste
    
- Exchange-hybridserver
    
## <a name="certificates-for-exchange-on-premises"></a>Zertifikate für Exchange lokal

Eine Übersicht darüber, wie Sie digitale Zertifikate verwenden, um die Kommunikation zwischen der lokalen Exchange-Organisation und Exchange Online sicherzustellen, finden Sie im TechNet-Artikel [Understanding Certificate Requirements](https://go.microsoft.com/fwlink/p/?LinkID=243657).
  
## <a name="certificates-for-single-sign-on"></a>Zertifikate für einmaliges Anmelden

Um Ihren Benutzern eine vereinfachte einmalige Anmeldung zu ermöglichen, die eine robuste Sicherheit umfasst, sind die in der folgenden Tabelle aufgeführten Zertifikate entweder auf den Verbundservern oder den Verbundserverproxys erforderlich. Die folgende Tabelle konzentriert sich auf Active Directory Verbunddienste (AD FS), wir haben auch weitere Informationen zur [Verwendung von Drittanbieter-Identitätsanbietern](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-fed-compatibility).
  
| Zertifikattyp | Beschreibung | Was Sie wissen müssen, bevor Sie bereitstellen |
|:-----|:-----|:-----|
|**SSL-Zertifikat (auch Serverauthentifizierungszertifikat genannt)** <br/> |Hierbei handelt es sich um ein Standardmäßiges SSL-Zertifikat, das verwendet wird, um die Kommunikation zwischen Verbundservern, Clients und Verbundserver-Proxy Computern zu sichern.  <br/> |Für AD FS ist ein SSL-Zertifikat erforderlich. Standardmäßig verwendet AD FS das SSL-Zertifikat, das für die Standardwebsite in Internet Information Services (IIS) konfiguriert ist.  <br/> Der Antragstellername dieses SSL-Zertifikats wird verwendet, um den Verbunddienst Namen (FS) für jede bereitgestellte AD FS-Instanz zu ermitteln. Wählen Sie einen Antragstellernamen für eine neue Zertifizierungsstelle aus – ausgestellte Zertifikate, die den Namen Ihres Unternehmens oder Ihrer Organisation am besten für Microsoft 365 darstellen. Dieser Name muss über das Internet routingfähig sein.  <br/>**Vorsicht:** Für AD FS ist es erforderlich, dass dieses SSL-Zertifikat keinen punktlosen (Short-Name)-Antragstellernamen hat.          <br/> **Empfehlung:** Da dieses Zertifikat von den Clients von AD FS als vertrauenswürdig eingestuft werden muss, wird empfohlen, ein SSL-Zertifikat zu verwenden, das von einer öffentlichen Zertifizierungsstelle (Drittanbieter) oder von einer Zertifizierungsstelle ausgestellt wurde, die einem öffentlich vertrauenswürdigen Stamm untergeordnet ist. zum Beispiel VeriSign oder Thawte.  <br/> |
|**Token Signing Certificate** <br/> |Hierbei handelt es sich um ein Standardmäßiges X. 509-Zertifikat, das für die sichere Signierung aller Token verwendet wird, die der Verbundserver ausgibt und die von Microsoft 365 akzeptiert und überprüft werden.  <br/> |Das Token signierende Zertifikat muss einen privaten Schlüssel enthalten, der mit einem vertrauenswürdigen Stamm in der FS verkettet wird. Standardmäßig erstellt AD FS ein selbstsigniertes Zertifikat. Je nach den Anforderungen Ihrer Organisation können Sie dieses Zertifikat jedoch mithilfe des AD FS-Verwaltungs-Snap-Ins in ein von der Zertifizierungsstelle ausgestelltes Zertifikat ändern.  <br/>**Vorsicht:** Das Token signierende Zertifikat ist für die Stabilität des FS entscheidend. Wenn das Zertifikat geändert wird, muss Microsoft 365 über die Änderung informiert werden. Wenn keine Benachrichtigung angegeben wird, können sich Benutzer nicht bei Ihren Microsoft 365-Dienst angeboten anmelden.<br/>**Empfehlung:** Es wird empfohlen, das von AD FS generierte selbstsignierte Token-Signing-Zertifikat zu verwenden. Dadurch wird dieses Zertifikat standardmäßig verwaltet. Wenn beispielsweise das Zertifikat abläuft, generiert AD FS ein neues selbstsigniertes Zertifikat.  <br/> |
   
Verbundserverproxys erfordern das Zertifikat, das in der folgenden Tabelle beschrieben wird.
  
| Zertifikattyp | Beschreibung | Was Sie wissen müssen, bevor Sie bereitstellen |
|:-----|:-----|:-----|
|SSL-Zertifikat  <br/> |Hierbei handelt es sich um ein Standardmäßiges SSL-Zertifikat, das zum Sichern der Kommunikation zwischen einem Verbundserver, einem Verbundserverproxy und Internet Clientcomputern verwendet wird.  <br/> |Dieses SSL-Zertifikat muss an die Standardwebsite in IIS gebunden sein, bevor Sie den Assistenten für die AD FS-Verbund Server Proxy Konfiguration erfolgreich ausführen können.  <br/> Dieses Zertifikat muss denselben Antragstellernamen aufweisen wie das SSL-Zertifikat, das auf dem Verbundserver im Unternehmensnetzwerk konfiguriert wurde.  <br/> **Empfehlung:** Es wird empfohlen, dass Sie das gleiche Serverauthentifizierungszertifikat verwenden, das auf dem Verbundserver konfiguriert ist, mit dem dieser Verbundserverproxy eine Verbindung herstellt.  <br/> |
   
## <a name="certificates-for-autodiscover-outlook-anywhere-and-active-directory-synchronization"></a>Zertifikate für AutoErmittlung, Outlook Anywhere und Active Directory Synchronisierung

Für externe Exchange 2013, Exchange 2010, Exchange 2007 und Exchange 2003-Client Zugriffsserver (CASs) ist ein Drittanbieter-SSL-Zertifikat für sichere Verbindungen für AutoErmittlung, Outlook Anywhere und Active Directory Synchronization Services erforderlich. Dieses Zertifikat ist möglicherweise bereits in Ihrer lokalen Umgebung installiert.
  
## <a name="certificate-for-an-exchange-hybrid-server"></a>Zertifikat für einen Exchange-Hybrid Server

Für externe Exchange-hybridserver oder-Server ist ein Drittanbieter-SSL-Zertifikat für die sichere Konnektivität mit dem Exchange Online Dienst erforderlich. Sie müssen dieses Zertifikat von Ihrem Drittanbieter-SSL-Anbieter erhalten.
  
## <a name="microsoft-365-certificate-chains"></a>Microsoft 365-Zertifikatketten

In diesem Artikel werden die Zertifikate beschrieben, die Sie möglicherweise in Ihrer Infrastruktur installieren müssen. Weitere Informationen zu den Zertifikaten, die auf unseren Microsoft 365-Servern installiert sind, finden Sie unter [Microsoft 365 Certificate Chains](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb).
  
## <a name="see-also"></a>Siehe auch

[Übersicht zu Microsoft 365 Enterprise](microsoft-365-overview.md)
