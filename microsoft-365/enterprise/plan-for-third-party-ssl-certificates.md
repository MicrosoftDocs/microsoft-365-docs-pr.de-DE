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
description: 'Zusammenfassung: Beschreibt die ssl-Zertifikate, die für Exchange lokale und hybride Dienste, SSO mit AD FS, Exchange Online-Dienste und Exchange Webdienste erforderlich sind.'
ms.openlocfilehash: f2505a40e87ab36c96c0ed24514420b56d1479d5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927488"
---
# <a name="plan-for-third-party-ssl-certificates-for-microsoft-365"></a>Planen von Drittanbieter-SSL-Zertifikaten für Microsoft 365

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Zum Verschlüsseln der Kommunikation zwischen Ihren Clients und der Microsoft 365 müssen SSL-Zertifikate (Secure Socket Layer) von Drittanbietern auf Ihren Infrastrukturservern installiert sein.

Dieser Artikel ist Teil der [Netzwerkplanung und Leistungsoptimierung für Microsoft 365.](./network-planning-and-performance.md)
   
Zertifikate sind für die folgenden Microsoft 365 erforderlich:
  
- Exchange lokal
    
- Einmaliges Anmelden (Single Sign-On, SSO) (für active Directory Federation Services (AD FS)-Verbundserver und AD FS-Verbundserver-Proxys)
    
- Exchange Online, z. B. AutoErmittlung, Outlook Anywhere und Exchange Webdienste
    
- Exchange Hybridserver
    
## <a name="certificates-for-exchange-on-premises"></a>Zertifikate für Exchange Lokal

Eine Übersicht darüber, wie Sie digitale Zertifikate verwenden, um die Kommunikation zwischen der lokalen Exchange und Exchange Online zu gewährleisten, finden Sie im TechNet-Artikel Understanding [Certificate Requirements](/previous-versions/exchange-server/exchange-141/gg476123(v=exchg.141)).
  
## <a name="certificates-for-single-sign-on"></a>Zertifikate für einmalige Anmeldung (SSO)

Um Ihren Benutzern eine vereinfachte einmalige Anmeldung mit robuster Sicherheit zu bieten, sind die in der folgenden Tabelle aufgeführten Zertifikate entweder auf den Verbundservern oder auf den Verbundserver-Proxys erforderlich. Die folgende Tabelle konzentriert sich auf Active Directory Federation Services (AD FS), außerdem finden Sie weitere Informationen zur Verwendung von [Identitätsanbietern von Drittanbietern.](/azure/active-directory/hybrid/how-to-connect-fed-compatibility)
  
| Zertifikattyp | Beschreibung | Was Sie vor der Bereitstellung wissen müssen |
|:-----|:-----|:-----|
|**SSL-Zertifikat (auch als Serverauthentifizierungszertifikat bezeichnet)** <br/> |Dies ist ein standardmäßiges SSL-Zertifikat, mit dem die Kommunikation zwischen Verbundservern, Clients und Verbundserverproxycomputern gesichert wird.  <br/> |AD FS erfordert ein SSL-Zertifikat. Standardmäßig verwendet AD FS das SSL-Zertifikat, das für die Standardwebsite in Internetinformationsdienste (IIS) konfiguriert ist.  <br/> Der Betreffname dieses SSL-Zertifikats wird verwendet, um den Namen des Verbunddiensts (Fs) für jede Instanz von AD FS zu bestimmen, die Sie bereitstellen. Erwägen Sie, einen Betreffnamen für alle von einer neuen Zertifizierungsstelle ausgestellten Zertifikate zu wählen, die den Namen Ihres Unternehmens oder Ihrer Organisation am besten für Microsoft 365. Dieser Name muss internetroutable sein.  <br/>**Vorsicht:** AD FS erfordert, dass dieses SSL-Zertifikat keinen punktlosen (Kurznamen) Betreffnamen hat.          <br/> **Empfehlung:** Da dieses Zertifikat von Clients von AD FS als vertrauenswürdig eingestuft werden muss, wird empfohlen, ein #A0 zu verwenden, das von einer öffentlichen Zertifizierungsstelle (Drittanbieter) oder von einer Zertifizierungsstelle ausgestellt wurde, die einem öffentlich vertrauenswürdigen Stamm untergeordnet ist. z. B. VeriSign oder Thawte.  <br/> |
|**Tokensignaturzertifikat** <br/> |Dies ist ein X.509-Standardzertifikat, das zum sicheren Signieren aller Token verwendet wird, die vom Verbundserver ausgestellt werden und die Microsoft 365 akzeptiert und überprüft.  <br/> |Das Tokensignaturzertifikat muss einen privaten Schlüssel enthalten, der mit einem vertrauenswürdigen Stamm in der FS verkettet wird. Standardmäßig erstellt AD FS ein selbst signiertes Zertifikat. Je nach den Anforderungen Ihrer Organisation können Sie dieses Zertifikat jedoch mithilfe des AD FS-Verwaltungs-Snap-Ins in ein von der Zertifizierungsstelle ausgestelltes Zertifikat ändern.  <br/>**Vorsicht:** Das Tokensignaturzertifikat ist für die Stabilität der FS von entscheidender Bedeutung. Wenn das Zertifikat geändert wird, Microsoft 365 die Änderung benachrichtigt werden. Wenn keine Benachrichtigung bereitgestellt wird, können sich Benutzer nicht bei ihren Microsoft 365 anmelden.<br/>**Empfehlung:** Es wird empfohlen, das selbstsignierte Tokensignaturzertifikat zu verwenden, das von AD FS generiert wird. Dadurch wird dieses Zertifikat standardmäßig für Sie verwaltet. Wenn dieses Zertifikat beispielsweise bald abläuft, generiert AD FS ein neues selbst signiertes Zertifikat.  <br/> |
   
Verbundserver-Proxys benötigen das Zertifikat, das in der folgenden Tabelle beschrieben ist.
  
| Zertifikattyp | Beschreibung | Was Sie vor der Bereitstellung wissen müssen |
|:-----|:-----|:-----|
|SSL-Zertifikat  <br/> |Dies ist ein standardmäßiges SSL-Zertifikat, das zum Sichern der Kommunikation zwischen einem Verbundserver, einem Verbundserverproxy und Internetclientcomputern verwendet wird.  <br/> |Dieses SSL-Zertifikat muss an die Standardwebsite in IIS gebunden sein, bevor Sie den Ad FS-Verbundserverproxykonfigurations-Assistenten erfolgreich ausführen können.  <br/> Dieses Zertifikat muss denselben Betreffnamen wie das SSL-Zertifikat haben, das auf dem Verbundserver im Unternehmensnetzwerk konfiguriert wurde.  <br/> **Empfehlung:** Es wird empfohlen, das gleiche Serverauthentifizierungszertifikat zu verwenden, das auf dem Verbundserver konfiguriert ist, mit dem dieser Verbundserverproxy eine Verbindung herstellt.  <br/> |
   
## <a name="certificates-for-autodiscover-outlook-anywhere-and-active-directory-synchronization"></a>Zertifikate für AutoErmittlung, Outlook Anywhere und Active Directory-Synchronisierung

Ihre externen Exchange 2013-, Exchange 2010-, Exchange 2007- und Exchange 2003-Clientzugriffsserver erfordern ein DRITTANBIETER-SSL-Zertifikat für sichere Verbindungen für AutoErmittlungs-, Outlook Anywhere- und Active Directory-Synchronisierungsdienste. Möglicherweise ist dieses Zertifikat bereits in Ihrer lokalen Umgebung installiert.
  
## <a name="certificate-for-an-exchange-hybrid-server"></a>Zertifikat für einen Exchange Hybridserver

Für ihre externen Exchange oder Server ist ein SSL-Zertifikat eines Drittanbieters erforderlich, um eine sichere Verbindung mit dem Exchange Online herzustellen. Sie müssen dieses Zertifikat von Ihrem Drittanbieter-SSL-Anbieter erhalten.
  
## <a name="microsoft-365-certificate-chains"></a>Microsoft 365 Zertifikatketten

In diesem Artikel werden die Zertifikate beschrieben, die Sie möglicherweise in Ihrer Infrastruktur installieren müssen. Weitere Informationen zu den zertifikaten, die auf unseren Microsoft 365 installiert sind, finden Sie [unter Microsoft 365 Certificate Chains](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb).
  
## <a name="see-also"></a>Siehe auch

[Übersicht zu Microsoft 365 Enterprise](microsoft-365-overview.md)