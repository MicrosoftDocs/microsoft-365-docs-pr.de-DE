---
title: E-Mail-Verschlüsselung
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: c0d87cbe-6d65-4c03-88ad-5216ea5564e8
ms.collection:
- M365-security-compliance
description: Vergleichen Sie die Verschlüsselungsoptionen, einschließlich Office-Nachrichtenverschlüsselung (Office Message Encryption, OME), S/MIME und Information Rights Management (IRM), und erfahren Sie mehr über Transport Layer Security (TLS).
ms.openlocfilehash: 43c3b25fb5a7b045590d1c3e2f16df681e48ecc0
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631750"
---
# <a name="email-encryption"></a>E-Mail-Verschlüsselung

In diesem Artikel werden die Verschlüsselungsoptionen in Microsoft 365, einschließlich Office-Nachrichtenverschlüsselung (Office Message Encryption, OME), S/MIME und Information Rights Management (IRM) verglichen und Transport Layer Security (TLS) eingeführt.
  
Microsoft 365 bietet mehrere Verschlüsselungsoptionen, die Sie bei der Erfüllung Ihrer geschäftlichen Anforderungen hinsichtlich E-Mail-Sicherheit unterstützen. In diesem Artikel werden drei Methoden zum Verschlüsseln von E-Mail in Office 365 präsentiert. Weitere Informationen zu allen Sicherheitsfeatures in Office 365 erhalten Sie im [Office 365 Trust Center](https://go.microsoft.com/fwlink/p/?LinkID=282470). In diesem Artikel werden die drei Verschlüsselungstypen vorgestellt, die Office 365-Administratoren zum Sichern von E-Mails in Microsoft 365 zur Verfügung stehen:
  
- Office-Nachrichtenverschlüsselung (Office Message Encryption, OME)

- Secure/Multipurpose Internet Mail Extensions (S/MIME)

- Information Rights Management (IRM).

## <a name="what-is-email-encryption-and-how-does-microsoft-365-use-it"></a>Was ist E-Mail-Verschlüsselung, und wie wird sie in Microsoft 365 verwendet?

Verschlüsselung ist der Prozess, mit dem Informationen codiert werden, sodass nur autorisierte Empfänger sie decodieren und die Informationen nutzen können. Microsoft 365 verwendet Verschlüsselung auf zwei Arten: im Dienst und als Kundensteuerelement. Im Dienst wird Verschlüsselung in Microsoft 365 standardmäßig verwendet. Sie müssen keine Konfiguration vornehmen. Microsoft 365 verwendet z. B. Transport Layer Security (TLS), um die Verbindung bzw. die Sitzung zwischen zwei Servern zu verschlüsseln. 
  
So funktioniert die E-Mail-Verschlüsselung in der Regel:
  
- Eine Nachricht wird entweder lokal auf dem Computer des Absenders oder durch einen zentralen Server während der Nachrichtenübertragung verschlüsselt, d. h. aus Nur-Text in nicht lesbaren Chiffretext umgewandelt.

- Die Nachricht verbleibt während der gesamten Übertragung im Chiffretextformat, um zu verhindern, dass sie gelesen werden kann, falls sie abgefangen werden sollte.

- Nachdem die Nachricht vom Empfänger empfangen wurde, wird sie mit einer der folgenden zwei Methoden wieder in lesbaren Nur-Text umgewandelt:

  - Der Computer des Empfängers entschlüsselt die Nachricht mithilfe eines Schlüssels.

  - Ein zentraler Server entschlüsselt die Nachricht im Auftrag des Empfängers, nachdem er die Identität des Empfängers überprüft hat.

Weitere Informationen zur Sicherung der Kommunikation zwischen Servern in Microsoft 365, z. B. zwischen Organisationen innerhalb von Microsoft 365 oder zwischen Microsoft 365 und einem vertrauenswürdigen Geschäftspartner außerhalb von Microsoft 365, finden Sie unter [Verwenden von TLS durch Exchange Online zum Absichern von E-Mail-Verbindungen in Microsoft 365](exchange-online-uses-tls-to-secure-email-connections.md).
  
In diesem Video sehen Sie eine Einführung in die [Verschlüsselung in Office 365](https://www.youtube.com/watch?v=KmfxCd5ublI).
  
## <a name="comparing-email-encryption-options-available-in-office-365"></a>Vergleichen der in Office 365 verfügbaren E-Mail-Verschlüsselungsoptionen

||![Konzeptionelle Grafik, die OME beschreibt.](../media/2bf27b5e-bbb3-46d1-95bf-884dc27a746c.png)|![Konzeptionelle Grafik, die IRM beschreibt.](../media/9c0cc444-9448-40c6-b244-8fcc593a64e0.png)|![Konzeptionelle Grafik, die SMIME beschreibt.](../media/ae4613a8-c17e-47e1-8e13-12e891e43744.png)|
|:-----|:-----|:-----|:-----|
|Was ist das?|Office 365-Nachrichtenverschlüsselung (Office Message Encryption, OME) ist ein Dienst, der auf Azure Rights Management (Azure RMS) aufbaut und mit dem Sie verschlüsselte E-Mails an Personen innerhalb oder außerhalb Ihrer Organisation senden können, unabhängig von der E-Mail-Zieladresse (Gmail, Yahoo! Mail, Outlook.com usw.). <br/> Als Administrator können Sie Transportregeln einrichten, die die Bedingungen für die Verschlüsselung definieren. Wenn ein Benutzer eine Nachricht sendet, die mit einer Regel übereinstimmt, wird die Verschlüsselung automatisch angewendet. <br/> Zum Anzeigen verschlüsselter Nachrichten können Empfänger eine einmalige Kennung abrufen, sich mit einem Microsoft-Konto anmelden oder sich mit einem Geschäfts-, Schul- oder Unikonto, das Office 365 zugeordnet ist, anmelden. Empfänger können auch verschlüsselte Antworten senden. Sie benötigen kein Microsoft 365-Abonnement, um verschlüsselte Nachrichten anzuzeigen oder verschlüsselte Antworten zu senden.|IRM ist eine Verschlüsselungslösung, die auch Nutzungseinschränkungen auf E-Mail-Nachrichten anwendet. Mit dieser Lösung können Sie verhindern, dass vertrauliche Informationen von nicht autorisierten Personen gedruckt, weitergeleitet oder kopiert werden. <br/> IRM-Funktionen in Microsoft 365 verwenden Azure Rights Management (Azure RMS).|S/MIME ist eine zertifikatbasierte Verschlüsselungslösung, die es Ihnen gestattet, eine Nachricht sowohl zu verschlüsseln als auch digital zu signieren. Die Nachrichtenverschlüsselung hilft Ihnen bei der Sicherstellung, dass nur der beabsichtigte Empfänger die Nachricht öffnen und lesen kann. Eine digitale Signatur hilft dem Empfänger, die Identität des Absenders zu überprüfen. <br/> Sowohl digitale Signaturen als auch Nachrichtenverschlüsselung werden durch die Verwendung eindeutiger digitale Zertifikate ermöglicht, die die Schlüssel für die Überprüfung digitaler Signaturen und die Verschlüsselung bzw. Entschlüsselung von Nachrichten enthalten. <br/> Um S/MIME zu verwenden, müssen Sie für jeden Empfänger öffentliche Schlüssel besitzen. Empfänger müssen ihre eigenen privaten Schlüssel verwalten, die dauerhaft gesichert sein müssen. Wenn der private Schlüssel eines Empfängers gefährdet ist, muss der Empfänger einen neuen privaten Schlüssel abrufen und neue öffentliche Schlüssel an alle potenziellen Absender verteilen.|
|Vorhandene Funktionen|OME: <br/> Verschlüsselt Nachrichten, die an interne oder externe Empfänger gesendet werden. <br/>  Ermöglicht Benutzern das Senden verschlüsselter Nachrichten an beliebige E-Mail-Adressen, einschließlich Outlook.com, Yahoo! Mail und Gmail. <br/>  Ermöglicht es Ihnen als Administrator, das E-Mail-Anzeigeportal entsprechend der Marke Ihrer Organisation anzupassen. <br/> Die Schlüssel werden von Microsoft sicher verwaltet und gespeichert, Sie müssen sich nicht darum kümmern. <br/> Es ist keine spezielle clientseitige Software erforderlich, sofern die verschlüsselte Nachricht (als HTML-Anlage gesendet) in einem Browser geöffnet werden kann.|IRM: <br/> Verwendet Verschlüsselung und Verwendungseinschränkungen, um Online- und Offlineschutz für E-Mails und Anlagen bereitzustellen. <br/> Gibt Ihnen als Administrator die Möglichkeit, Transportregeln oder Outlook-Schutzregeln einzurichten, um IRM automatisch auf ausgewählte Nachrichten anzuwenden. <br/> Ermöglicht Benutzern das manuelle Anwenden von Vorlagen in Outlook im Web (früher Outlook Web App).|In S/MIME erfolgt die Absenderauthentifizierung durch digitale Signaturen, und die Vertraulichkeit von Nachrichten wird durch Verschlüsselung sichergestellt.|
|Nicht vorhandene Funktionen|Mit OME können keine Nutzungseinschränkungen auf Nachrichten angewendet werden. Sie können damit z. B. nicht verhindern, dass Empfänger eine verschlüsselte Nachricht weiterleiten oder drucken.|Einige Anwendungen unterstützen IRM-E-Mails möglicherweise nicht auf allen Geräten. Weitere Informationen zu diesen und anderen Produkten, die IRM-E-Mail unterstützen, finden Sie unter [Client-Gerätefunktionen](https://technet.microsoft.com/library/dn655136.aspx#BKMK_ClientCapabilities).|Mit S/MIME können verschlüsselte Nachrichten nicht auf Schadsoftware, Spam oder Richtlinien überprüft werden.|
|Empfehlungen und Beispielszenarien|Die Verwendung von OME wird empfohlen, wenn Sie vertrauliche Geschäftsinformationen an Personen außerhalb Ihrer Organisation senden möchten, unabhängig davon, ob es sich um Verbraucher oder andere Unternehmen handelt. Beispiel:  <br/>  Ein Bankangestellter sendet Kreditkartenabrechnungen an Kunden  <br/>  Eine Arztpraxis sendet eine Krankenakte an einen Patienten.  <br/>  Ein Anwalt sendet vertrauliche Rechtsinformationen an einen anderen Anwalt.|Die Verwendung von IRM wird empfohlen, wenn Sie Nutzungseinschränkungen und Verschlüsselung anwenden möchten. Beispiel:  <br/>  Ein Vorgesetzter, der vertrauliche Details über ein neues Produkt an sein Team sendet, wendet die Option "Nicht weiterleiten" an.  <br/>  Eine Führungskraft muss ein Angebot für ein anderes Unternehmen freigeben, das eine Anlage von einem Partner enthält, der Office 365 verwendet, und sowohl die E-Mail als auch die Anlage müssen geschützt werden.|Die Verwendung von S/MIME wird empfohlen, wenn Ihre Organisation oder die Organisation des Empfängers in eine echte Peer-zu-Peer-Verschlüsselung benötigt.  <br/>  S/MIME wird am häufigsten in den folgenden Szenarien verwendet:  <br/>  Kommunikation zwischen Behörden  <br/>  Kommunikation zwischen einem Unternehmen und einer Behörde|
||

## <a name="what-encryption-options-are-available-for-my-microsoft-365-subscription"></a>Welche Verschlüsselungsoptionen sind für mein Microsoft 365-Abonnement verfügbar?

Informationen zu den E-Mail-Verschlüsselungsoptionen für Ihr Microsoft 365-Abonnement finden Sie unter [Exchange Online-Dienstbeschreibung](https://technet.microsoft.com/library/exchange-online-service-description.aspx). Hier finden Sie Informationen zu den folgenden Verschlüsselungsfeatures:
  
- Azure RMS, einschließlich IRM-Funktionen und OME

- S/MIME

- TLS

- Verschlüsselung von Daten im Ruhezustand (über BitLocker)

Sie können auch Verschlüsselungstools von Drittanbietern mit Microsoft 365 verwenden, z. B. PGP (Pretty Good Privacy). Microsoft 365 unterstützt kein PGP/MIME, und Sie können PGP-verschlüsselte E-Mails nur mit PGP/Inline senden und empfangen.

## <a name="what-about-encryption-for-data-at-rest"></a>Wissenswertes zur Verschlüsselung von Daten im Ruhezustand

"Daten im Ruhezustand" bezieht sich auf Daten, für die derzeit keine Übertragung aktiv ist. In Microsoft 365 werden E-Mail-Daten im Ruhezustand mit der BitLocker-Laufwerkverschlüsselung verschlüsselt. BitLocker verschlüsselt die Festplatten in Microsoft-Datencentern, um verbesserten Schutz vor nicht autorisiertem Zugriff bereitzustellen. Weitere Informationen finden Sie unter [BitLocker-Übersicht](https://go.microsoft.com/fwlink/p/?LinkId=394737).
  
## <a name="more-information-about-email-encryption-options"></a>Weitere Informationen zu E-Mail-Verschlüsselungsoptionen

Weitere Informationen zu den E-Mail-Verschlüsselungsoptionen in diesem Artikel sowie zu TLS finden Sie in diesen Artikeln:
  
**OME**
  
[Office 365-Nachrichtenverschlüsselung (OME)](ome.md)
  
**IRM**
  
[Verwaltung von Informationsrechten in Exchange Online](https://technet.microsoft.com/library/jj983436%28v=exchg.150%29.aspx)
  
[Was ist Azure Rights Management?](https://technet.microsoft.com/library/jj585026)
  
**S/MIME**
  
[S/MIME für die Nachrichtensignierung und -verschlüsselung](https://technet.microsoft.com/library/dn626158)
  
[Grundlegendes zu S/MIME](https://technet.microsoft.com/library/aa995740%28v=exchg.65%29.aspx)
  
[Grundlegendes zur Verschlüsselung mit öffentlichen Schlüsseln](https://technet.microsoft.com/library/aa998077%28v=exchg.65%29.aspx)
  
**TLS**
  
[Konfigurieren des benutzerdefinierten E-Mail-Flusses mithilfe von Connectors](https://technet.microsoft.com/library/jj723138%28v=exchg.150%29.aspx)
