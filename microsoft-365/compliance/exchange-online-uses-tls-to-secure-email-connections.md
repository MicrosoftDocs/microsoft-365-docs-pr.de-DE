---
title: Wie Exchange Online TLS zum Sichern von e-Mail-Verbindungen verwendet
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/2/2018
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4cde0cda-3430-4dc0-b489-f2c0736c929f
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: Erfahren Sie, wie Exchange Online und Microsoft 365 TLS (Transport Layer Security) und das Weiterleitungs Geheimnis (FS) zum Sichern von e-Mail-Kommunikationen verwenden. Erhalten Sie auch Informationen über das von Microsoft ausgestellte Zertifikat für Exchange Online.
ms.openlocfilehash: 4136303e9c90e377788a7168351a5e126912a93c
ms.sourcegitcommit: 758263ad484e00f5a561a47c8c22d5787af7671e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "44170964"
---
# <a name="how-exchange-online-uses-tls-to-secure-email-connections"></a>Wie Exchange Online TLS zum Sichern von e-Mail-Verbindungen verwendet

Erfahren Sie, wie Exchange Online und Microsoft 365 TLS (Transport Layer Security) und das Weiterleitungs Geheimnis (FS) zum Sichern von e-Mail-Kommunikationen verwenden. Bietet außerdem Informationen über das von Microsoft für Exchange Online ausgestellte Zertifikat.
  
## <a name="tls-basics-for-microsoft-365-and-exchange-online"></a>TLS-Grundlagen für Microsoft 365 und Exchange Online

Transport Layer Security (TLS) und SSL, das vor TLS vorhanden war, sind kryptografische Protokolle, die die Kommunikation über ein Netzwerk sichern, indem Sicherheitszertifikate zum Verschlüsseln einer Verbindung zwischen Computern verwendet werden. TLS ersetzt Secure Sockets Layer (SSL) und wird häufig als SSL 3.1 bezeichnet. Für Exchange Online verwenden wir TLS, um die Verbindungen zwischen unseren Exchange-Servern und den Verbindungen zwischen unseren Exchange-Servern und anderen Servern wie Ihren lokalen Exchange-Servern oder den e-Mail-Servern Ihrer Empfänger zu verschlüsseln. Nachdem die Verbindung verschlüsselt ist, werden alle über diese Verbindung gesendeten Daten über den verschlüsselten Kanal gesendet. Wenn Sie eine Nachricht weiterleiten, die über eine TLS-verschlüsselte Verbindung gesendet wurde, ist diese Nachricht nicht unbedingt verschlüsselt. Dies liegt daran, dass TLS die Nachricht in einfachen Worten nicht verschlüsselt, sondern nur die Verbindung.
  
Wenn Sie die Nachricht verschlüsseln möchten, müssen Sie eine Verschlüsselungstechnologie verwenden, die den Nachrichteninhalt verschlüsselt, z. B. Office-Nachrichtenverschlüsselung. Unter [Email encryption in Office 365](email-encryption.md) und [Office 365 Message Encryption (OME)](ome.md) erhalten Sie weitere Informationen zu den Verschlüsselungsoptionen für Nachrichten in Office 365. 
  
Wir empfehlen die Verwendung von TLS in Situationen, in denen Sie einen sicheren Kanal der Korrespondenz zwischen Microsoft und ihrer lokalen Organisation oder einer anderen Organisation wie einem Partner einrichten möchten. Exchange Online versucht immer, TLS zuerst zu verwenden, um Ihre e-Mails zu sichern, dies jedoch nicht immer, wenn der andere Anbieter keine TLS-Sicherheit anbietet. Lesen Sie weiter, um zu erfahren, wie Sie alle e-Mails an Ihren lokalen Servern oder wichtigen Partnern mithilfe von *Connectors*sichern können. 
  
## <a name="how-exchange-online-uses-tls-between-exchange-online-customers"></a>Wie Exchange Online TLS bei Exchange Online-Kunden verwendet

Exchange Online-Server verschlüsseln Verbindungen mit anderen Exchange Online-Servern in unseren Datencentern immer mithilfe von TLS 1.2. Wenn Sie e-Mails an einen Empfänger innerhalb Ihrer Organisation senden, wird diese e-Mail automatisch über eine Verbindung gesendet, die mit TLS verschlüsselt ist. Außerdem werden alle e-Mails, die Sie an andere Kunden senden, über Verbindungen gesendet, die mit TLS verschlüsselt sind und unter Verwendung des Weiterleitungs Geheimnisses gesichert sind.
  
## <a name="how-microsoft-365-uses-tls-between-microsoft-365-and-external-trusted-partners"></a>So verwendet Microsoft 365 TLS zwischen Microsoft 365 und externen, vertrauenswürdigen Partnern

Standardmäßig verwendet Exchange Online immer opportunistisches TLS. Dies bedeutet, dass Exchange Online immer versucht, Verbindungen mit der sichersten Version von TLS zuerst zu verschlüsseln und dann die Liste der TLS-Chiffren nach unten arbeitet, bis eine gefunden wird, auf der sich beide Parteien einigen können. Sofern Sie Exchange Online nicht konfiguriert haben, um sicherzustellen, dass Nachrichten an diesen Empfänger nur über sichere Verbindungen gesendet werden, wird die Nachricht standardmäßig unverschlüsselt gesendet, wenn die Empfängerorganisation keine TLS-Verschlüsselung unterstützt. Opportunistisches TLS ist für die meisten Unternehmen ausreichend. Für Unternehmen mit Compliance-Anforderungen wie medizinischen, Bank-oder Regierungsorganisationen können Sie jedoch Exchange Online konfigurieren, dass TLS benötigt oder erzwungen wird. Anweisungen finden Sie unter [Configure Mail Flow using Connectors in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx).
  
Wenn Sie TLS zwischen Ihrer Organisation und einer vertrauenswürdigen Partnerorganisation konfigurieren möchten, kann Exchange Online die erzwungene TLS verwenden, um vertrauenswürdige Kommunikationskanäle zu erstellen. Bei der erzwungenen TLS ist es erforderlich, dass sich die Partnerorganisation bei Exchange Online mit einem Sicherheitszertifikat authentifiziert, sodass E-Mail-Nachrichten an Sie gesendet werden können. Ihr Partner muss seine eigenen Zertifikate verwalten, um dies zu tun. In Exchange Online verwenden wir Connectors zum Schutz von Nachrichten, die Sie von nicht autorisiertem Zugriff senden, bevor Sie beim e-Mail-Anbieter des Empfängers ankommen. Informationen zur Verwendung von Connectors zum Konfigurieren des Nachrichtenflusses finden Sie unter [Configure Mail Flow using Connectors in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx).
  
## <a name="tls-and-hybrid-exchange-server-deployments"></a>TLS und Exchange Server-Hybridbereitstellungen

Wenn Sie eine Exchange-hybridbereitstellung verwalten, muss sich Ihr lokaler Exchange-Server bei Microsoft 365 mit einem Sicherheitszertifikat authentifizieren, um e-Mails an Empfänger zu senden, deren Postfächer sich nur in Office 365 befinden. Daher müssen Sie Ihre eigenen Sicherheitszertifikate für Ihre lokalen Exchange-Server verwalten. Sie müssen diese Serverzertifikate auch sicher speichern und verwalten. Weitere Informationen zum Verwalten von Zertifikaten in hybridbereitstellungen finden Sie unter [Zertifikatanforderungen für hybridbereitstellungen](https://technet.microsoft.com/library/hh563848%28v=exchg.150%29.aspx).
  
## <a name="how-to-set-up-forced-tls-for-exchange-online-in-office-365"></a>Einrichten von erzwungener TLS für Exchange Online in Office 365

Damit bei Exchange Online-Kunden die erzwungene TLS so funktioniert, dass alle Ihre gesendeten und empfangenen E-Mails gesichert werden, müssen Sie mehrere Connectors einrichten, für die TLS erforderlich ist. Sie benötigen einen Connector für E-Mails, die an Ihre Benutzerpostfächer gesendet werden, und ein weiterer Connector ist für E-Mails erforderlich, die von Ihren Benutzerpostfächern gesendet werden. Erstellen Sie diese Connectors in der Exchange-Verwaltungskonsole in Office 365. Anweisungen finden Sie unter [Configure Mail Flow using Connectors in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx).
  
## <a name="tls-certificate-information-for-exchange-online"></a>TLS-Zertifikatinformationen für Exchange Online

Die von Exchange Online verwendeten Zertifikatinformationen werden in der folgenden Tabelle beschrieben. Wenn Ihr Geschäftspartner erzwungenes TLS auf dem e-Mail-Server eingerichtet hat, müssen Sie diese Informationen bereitstellen. Beachten Sie, dass sich unsere Zertifikate aus Sicherheitsgründen von Zeit zu Zeit ändern. Wir haben ein Update für unser Zertifikat in unseren Rechenzentren eingeführt. Das neue Zertifikat ist vom 3. September 2018 gültig.
  
 **Aktuelle Zertifikatinformationen gültig ab 3. September 2018**
  
|**Attribut**|**Wert**|
|:-----|:-----|
|Aussteller des Stammzertifikats der Zertifizierungsstelle  <br/> |GlobalSign-Stammzertifizierungsstelle – R1 <br/> |
|Name des Zertifikats  <br/> |mail.protection.outlook.com  <br/> |
|Organisation  <br/> |Microsoft Corporation  <br/> |
|Organisationseinheit  <br/> |  <br/> |
|Schlüsselstärke des Zertifikats  <br/> |2048  <br/> |
   
 **Veraltete Zertifikatinformationen gültig bis 3. September 2018**
  
Um einen reibungslosen Übergang sicherzustellen, werden wir weiterhin die alten Zertifikatinformationen für Ihren Verweis bereitstellen, allerdings sollten Sie die aktuellen Zertifikatinformationen ab sofort verwenden.
  
****

|**Attribut**|**Wert**|
|:-----|:-----|
|Aussteller des Stammzertifikats der Zertifizierungsstelle  <br/> |Baltimore CyberTrust Root  <br/> |
|Name des Zertifikats  <br/> |mail.protection.outlook.com  <br/> |
|Organisation  <br/> |Microsoft Corporation  <br/> |
|Organisationseinheit  <br/> |Microsoft Corporation  <br/> |
|Schlüsselstärke des Zertifikats  <br/> |2048  <br/> |
   
## <a name="prepare-for-the-new-exchange-online-certificate"></a>Vorbereiten des neuen Exchange Online Zertifikats

Das neue Zertifikat wird von einer anderen Zertifizierungsstelle aus dem vorherigen Zertifikat ausgestellt, das von Exchange Online verwendet wurde. Daher müssen Sie möglicherweise einige Aktionen ausführen, um das neue Zertifikat zu verwenden.

Das neue Zertifikat erfordert eine Verbindung mit den Endpunkten der neuen Zertifizierungsstelle als Teil der Überprüfung des Zertifikats. Wenn Sie dies nicht tun, kann dies dazu führen, dass der Nachrichtenfluss negativ beeinflusst wird. Wenn Sie Ihre e-Mail-Server mit Firewalls schützen, die nur die Verbindung von e-Mail-Servern mit bestimmten Zielen zulassen, müssen Sie überprüfen, ob Ihr Server das neue Zertifikat überprüfen kann. Führen Sie die folgenden Schritte aus, um zu bestätigen, dass Ihr Server das neue Zertifikat verwenden kann:

1. Stellen Sie über Windows PowerShell eine Verbindung mit Ihrem lokalen Exchange Server her, und führen Sie dann den folgenden Befehl aus:  
  `certutil -URL https://crl.globalsign.com/gsorganizationvalsha2g3.crl`
2. Wählen Sie im angezeigten Fenster die Option **Abrufen**aus.
3. Wenn das Dienstprogramm seine Prüfung abgeschlossen hat, wird ein Status zurückgegeben. Wenn der Status **"OK"** angezeigt wird, kann Ihr e-Mail-Server das neue Zertifikat erfolgreich überprüfen. Wenn dies nicht der Fall ist, müssen Sie ermitteln, was dazu führt, dass die Verbindungen fehlschlagen. Höchstwahrscheinlich müssen Sie die Einstellungen einer Firewall aktualisieren. Die vollständige Liste der Endpunkte, auf die zugegriffen werden muss, umfasst Folgendes:
    - ocsp.globalsign.com
     - crl.globalsign.com
     - secure.globalsign.com   

Normalerweise erhalten Sie Aktualisierungen an Ihren Stammzertifikaten automatisch über Windows Update. Einige Bereitstellungen verfügen jedoch über zusätzliche Sicherheitseinstellungen, die verhindern, dass diese Updates automatisch ausgeführt werden. In diesen gesperrten Bereitstellungen, in denen die Stammzertifikate von Windows Update nicht automatisch aktualisiert werden können, müssen Sie sicherstellen, dass das richtige Zertifikat der Stammzertifizierungsstelle installiert ist, indem Sie die folgenden Schritte ausführen:
1.  Stellen Sie über Windows PowerShell eine Verbindung mit Ihrem lokalen Exchange Server her, und führen Sie dann den folgenden Befehl aus:  
  `certmgr.msc`
2. Vergewissern Sie sich unter **Vertrauenswürdige Stammzertifizierungsstelle/Zertifikate**, dass das neue Zertifikat aufgelistet ist.

## <a name="get-more-information-about-tls-and-microsoft-365"></a>Erhalten Sie weitere Informationen zu TLS und Microsoft 365

Eine Liste der unterstützten Verschlüsselungs Pakete finden Sie unter [technische Referenzdetails zur Verschlüsselung](technical-reference-details-about-encryption.md).
  
[Einrichten von Connectors für den sicheren Nachrichtenfluss mit einer Partnerorganisation](https://technet.microsoft.com/library/dn751021%28v=exchg.150%29.aspx)
  
[Connectors mit erweiterter E-Mail-Sicherheit](https://technet.microsoft.com/library/261d92e4-7371-4555-b781-2062b5bb5278.aspx)
  
[Verschlüsselung in Microsoft 365](encryption.md)
  

