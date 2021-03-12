---
title: Wie Exchange Online mithilfe von TLS E-Mail-Verbindungen schützt
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
description: Erfahren Sie, wie Exchange Online und Microsoft 365 Transport Layer Security (TLS) und Forward Secrecy (FS) zum Sichern der E-Mail-Kommunikation verwenden. Außerdem erhalten Sie Informationen zum von Microsoft für Exchange Online ausgestellten Zertifikat.
ms.openlocfilehash: 6e23ebc6451b9d139f1b18838007411028a059f3
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727456"
---
# <a name="how-exchange-online-uses-tls-to-secure-email-connections"></a>Wie Exchange Online mithilfe von TLS E-Mail-Verbindungen schützt

Erfahren Sie, wie Exchange Online und Microsoft 365 Transport Layer Security (TLS) und Forward Secrecy (FS) zum Sichern der E-Mail-Kommunikation verwenden. Bietet außerdem Informationen über das von Microsoft für Exchange Online ausgestellte Zertifikat.
  
## <a name="tls-basics-for-microsoft-365-and-exchange-online"></a>TLS-Grundlagen für Microsoft 365 und Exchange Online

Transport Layer Security (TLS) und SSL, das vor TLS vorhanden war, sind kryptografische Protokolle, die die Kommunikation über ein Netzwerk sichern, indem Sicherheitszertifikate zum Verschlüsseln einer Verbindung zwischen Computern verwendet werden. TLS ersetzt Secure Sockets Layer (SSL) und wird häufig als SSL 3.1 bezeichnet. Für Exchange Online verwenden wir TLS, um die Verbindungen zwischen unseren Exchange-Servern und den Verbindungen zwischen unseren Exchange-Servern und anderen Servern wie Ihren lokalen Exchange-Servern oder den E-Mail-Servern Ihrer Empfänger zu verschlüsseln. Nachdem die Verbindung verschlüsselt ist, werden alle über diese Verbindung gesendeten Daten über den verschlüsselten Kanal gesendet. Wenn Sie eine Nachricht weiterleiten, die über eine TLS-verschlüsselte Verbindung gesendet wurde, ist diese Nachricht nicht unbedingt verschlüsselt. Dies liegt daran, dass TLS die Nachricht einfach nicht verschlüsselt, sondern nur die Verbindung.
  
Wenn Sie die Nachricht verschlüsseln möchten, müssen Sie eine Verschlüsselungstechnologie verwenden, die den Nachrichteninhalt verschlüsselt, z. B. Office-Nachrichtenverschlüsselung. Unter [Email encryption in Office 365](email-encryption.md) und [Office 365 Message Encryption (OME)](ome.md) erhalten Sie weitere Informationen zu den Verschlüsselungsoptionen für Nachrichten in Office 365. 
  
Es wird empfohlen, TLS in Situationen zu verwenden, in denen Sie einen sicheren Korrespondenzkanal zwischen Microsoft und Ihrer lokalen Organisation oder einer anderen Organisation einrichten möchten, z. B. einem Partner. Exchange Online versucht immer, zunächst TLS zum Sichern Ihrer E-Mails zu verwenden, kann dies jedoch nicht immer tun, wenn die andere Seite keine TLS-Sicherheit bietet. Lesen Sie weiter, um herauszufinden, wie Sie alle E-Mails mithilfe von Connectors an Ihre lokalen Server oder wichtigen Partner *sichern können.* 

Um unseren Kunden die beste Verschlüsselung zu bieten, verfügt Microsoft über veraltete Transport Layer Security (TLS)-Versionen 1.0 und 1.1 in [Office 365](tls-1.0-and-1.1-deprecation-for-office-365.md) und [Office 365 GCC](tls-1-2-in-office-365-gcc.md). Sie können jedoch weiterhin eine unverschlüsselte SMTP-Verbindung ohne TLS verwenden. Es wird keine E-Mail-Übertragung ohne Verschlüsselung empfohlen.  
  
## <a name="how-exchange-online-uses-tls-between-exchange-online-customers"></a>Wie Exchange Online TLS bei Exchange Online-Kunden verwendet

Exchange Online-Server verschlüsseln Verbindungen mit anderen Exchange Online-Servern in unseren Datencentern immer mithilfe von TLS 1.2. Wenn Sie E-Mails an einen Empfänger in Ihrer Organisation senden, wird diese E-Mail automatisch über eine Verbindung gesendet, die mit TLS verschlüsselt ist. Darüber hinaus werden alle E-Mails, die Sie an andere Kunden senden, über Verbindungen gesendet, die mit TLS verschlüsselt und mithilfe von Forward Secrecy gesichert werden.
  
## <a name="how-microsoft-365-uses-tls-between-microsoft-365-and-external-trusted-partners"></a>Verwenden von TLS zwischen Microsoft 365 und externen, vertrauenswürdigen Partnern in Microsoft 365

Standardmäßig verwendet Exchange Online immer opportunistisches TLS. Dies bedeutet, dass Exchange Online immer versucht, Verbindungen mit der sichersten Version von TLS zuerst zu verschlüsseln, und arbeitet dann in der Liste der TLS-Chiffren nach unten, bis eine gefunden wird, auf die sich beide Parteien einigen können. Wenn Sie Exchange Online nicht so konfiguriert haben, dass Nachrichten an diesen Empfänger nur über sichere Verbindungen gesendet werden, wird die Nachricht standardmäßig unverschlüsselt gesendet, wenn die Empfängerorganisation die TLS-Verschlüsselung nicht unterstützt. Opportunistisches TLS ist für die meisten Unternehmen ausreichend. Für Unternehmen mit Complianceanforderungen wie z. B. medizinischen, Bank- oder Behördenorganisationen können Sie Exchange Online jedoch so konfigurieren, dass TLS erforderlich oder erzwingen wird. Anweisungen finden Sie unter [Configure mail flow using connectors in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx).
  
Wenn Sie TLS zwischen Ihrer Organisation und einer vertrauenswürdigen Partnerorganisation konfigurieren möchten, kann Exchange Online die erzwungene TLS verwenden, um vertrauenswürdige Kommunikationskanäle zu erstellen. Bei der erzwungenen TLS ist es erforderlich, dass sich die Partnerorganisation bei Exchange Online mit einem Sicherheitszertifikat authentifiziert, sodass E-Mail-Nachrichten an Sie gesendet werden können. Ihr Partner muss seine eigenen Zertifikate verwalten, um dies zu tun. In Exchange Online verwenden wir Connectors, um Nachrichten zu schützen, die Sie vor unbefugtem Zugriff senden, bevor sie beim E-Mail-Anbieter des Empfängers eintreffen. Informationen zur Verwendung von Connectors zum Konfigurieren des Nachrichtenflusses finden Sie unter [Configure mail flow using connectors in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx).
  
## <a name="tls-and-hybrid-exchange-server-deployments"></a>TLS und Exchange Server-Hybridbereitstellungen

Wenn Sie eine hybride Exchange-Bereitstellung verwalten, muss sich Der lokale Exchange-Server mit einem Sicherheitszertifikat bei Microsoft 365 authentifizieren, um E-Mails an Empfänger zu senden, deren Postfächer sich nur in Office 365 befinden. Deshalb müssen Sie ihre eigenen Sicherheitszertifikate für Ihre lokalen Exchange-Server verwalten. Sie müssen diese Serverzertifikate auch sicher speichern und verwalten. Weitere Informationen zum Verwalten von Zertifikaten in Hybridbereitstellungen finden Sie unter [Zertifikatanforderungen für Hybridbereitstellungen](https://technet.microsoft.com/library/hh563848%28v=exchg.150%29.aspx).
  
## <a name="how-to-set-up-forced-tls-for-exchange-online-in-office-365"></a>Einrichten von erzwungener TLS für Exchange Online in Office 365

Damit bei Exchange Online-Kunden die erzwungene TLS so funktioniert, dass alle Ihre gesendeten und empfangenen E-Mails gesichert werden, müssen Sie mehrere Connectors einrichten, für die TLS erforderlich ist. Sie benötigen einen Connector für E-Mails, die an Ihre Benutzerpostfächer gesendet werden, und ein weiterer Connector ist für E-Mails erforderlich, die von Ihren Benutzerpostfächern gesendet werden. Erstellen Sie diese Connectors in der Exchange-Verwaltungskonsole in Office 365. Anweisungen finden Sie unter [Configure mail flow using connectors in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx).
  
## <a name="tls-certificate-information-for-exchange-online"></a>TLS-Zertifikatinformationen für Exchange Online

Die von Exchange Online verwendeten Zertifikatinformationen werden in der folgenden Tabelle beschrieben. Wenn Ihr Geschäftspartner erzwungenes TLS auf dem E-Mail-Server eingerichtet hat, müssen Sie diese Informationen für sie bereitstellen. Beachten Sie, dass sich unsere Zertifikate aus Sicherheitsgründen von Zeit zu Zeit ändern. Wir haben ein Update für unser Zertifikat in unseren Rechenzentren durchgeführt. Das neue Zertifikat ist ab dem 3. September 2018 gültig.
  
 **Aktuelle Zertifikatinformationen gültig ab dem 3. September 2018**
  
| Attribut | Wert |
|:-----|:-----|
|Aussteller des Stammzertifikats der Zertifizierungsstelle  <br/> |Globale Stammzertifizierungsstelle – R1 <br/> |
|Name des Zertifikats  <br/> |mail.protection.outlook.com  <br/> |
|Organisation  <br/> |Microsoft Corporation  <br/> |
|Organisationseinheit  <br/> |  <br/> |
|Schlüsselstärke des Zertifikats  <br/> |2048  <br/> |
   
 **Veraltete Zertifikatinformationen gültig bis zum 3. September 2018**
  
Um einen reibungslosen Übergang sicherzustellen, stellen wir die alten Zertifikatinformationen für Ihre Referenz für einige Zeit zur Verfügung. Sie sollten jedoch ab jetzt die aktuellen Zertifikatinformationen verwenden.
  
****

| Attribut | Wert |
|:-----|:-----|
|Aussteller des Stammzertifikats der Zertifizierungsstelle  <br/> |Baltimore CyberTrust Root  <br/> |
|Name des Zertifikats  <br/> |mail.protection.outlook.com  <br/> |
|Organisation  <br/> |Microsoft Corporation  <br/> |
|Organisationseinheit  <br/> |Microsoft Corporation  <br/> |
|Schlüsselstärke des Zertifikats  <br/> |2048  <br/> |
   
## <a name="prepare-for-the-new-exchange-online-certificate"></a>Vorbereiten des neuen Exchange Online-Zertifikats

Das neue Zertifikat wird von einer anderen Zertifizierungsstelle (Certificate Authority, CA) ausgestellt als das vorherige von Exchange Online verwendete Zertifikat. Aus diesem Grund müssen Sie möglicherweise einige Aktionen ausführen, um das neue Zertifikat zu verwenden.

Das neue Zertifikat erfordert eine Verbindung mit den Endpunkten der neuen Zertifizierungsstelle im Rahmen der Validierung des Zertifikats. Wenn dies nicht der Fehler ist, kann dies zu negativen Auswirkungen auf den Nachrichtenfluss führen. Wenn Sie Ihre E-Mail-Server mit Firewalls schützen, mit denen die E-Mail-Server nur eine Verbindung mit bestimmten Zielen herstellen können, müssen Sie überprüfen, ob Ihr Server das neue Zertifikat überprüfen kann. Führen Sie die folgenden Schritte aus, um zu bestätigen, dass Ihr Server das neue Zertifikat verwenden kann:

1. Stellen Sie eine Verbindung Exchange Server lokalen Windows PowerShell, und führen Sie dann den folgenden Befehl aus:  
  `certutil -URL https://crl.globalsign.com/gsorganizationvalsha2g3.crl`

1. Wählen Sie im angezeigten Fenster Abrufen **aus.**

1. Wenn das Hilfsprogramm seine Überprüfung abgeschlossen hat, gibt es einen Status zurück. Wenn der Status **OK anzeigt,** kann ihr E-Mail-Server das neue Zertifikat erfolgreich überprüfen. Andern falls nicht, müssen Sie ermitteln, was dazu führt, dass die Verbindungen fehlschlagen. Wahrscheinlich müssen Sie die Einstellungen einer Firewall aktualisieren. Die vollständige Liste der Endpunkte, auf die zugegriffen werden muss, umfasst Folgendes:
    - ocsp.globalsign.com
    - crl.globalsign.com
    - secure.globalsign.com   

In der Regel erhalten Sie Updates für Ihre Stammzertifikate automatisch über Windows Update. Einige Bereitstellungen verfügen jedoch über zusätzliche Sicherheit, die verhindert, dass diese Updates automatisch ausgeführt werden. In diesen gesperrten Bereitstellungen, in denen Windows Update Stammzertifikate nicht automatisch aktualisieren kann, müssen Sie sicherstellen, dass das richtige Stammzertifizierungsstellenzertifikat installiert wird, indem Sie die folgenden Schritte ausführen:
1.  Stellen Sie eine Verbindung Exchange Server lokalen Windows PowerShell, und führen Sie dann den folgenden Befehl aus:  
  `certmgr.msc`

2. Vergewissern **Sie sich unter Vertrauenswürdige Stammzertifizierungsstelle/Zertifikate,** dass das neue Zertifikat aufgeführt ist.

## <a name="get-more-information-about-tls-and-microsoft-365"></a>Weitere Informationen zu TLS und Microsoft 365

Eine Liste der unterstützten Verschlüsselungssuiten finden Sie unter [Technische Referenzdetails zur Verschlüsselung](technical-reference-details-about-encryption.md).
  
[Einrichten von Connectors für den sicheren Nachrichtenfluss mit einer Partnerorganisation](https://technet.microsoft.com/library/dn751021%28v=exchg.150%29.aspx)
  
[Connectors mit erweiterter E-Mail-Sicherheit](https://technet.microsoft.com/library/261d92e4-7371-4555-b781-2062b5bb5278.aspx)
  
[Verschlüsselung in Microsoft 365](encryption.md)
  

