---
title: Verschlüsselung in Microsoft 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 0a322724-08ca-43db-b69a-afbfa20484cd
ms.collection:
- M365-security-compliance
- Strat_O365_IP
- m365solution-mip
- m365initiative-compliance
description: Mit Office 365 werden Ihre Inhalte im Ruhe- und Übertragungsverkehr mit der stärksten verfügbaren Verschlüsselung, Protokollen und Technologien verschlüsselt. Erhalten Sie eine Übersicht über die Verschlüsselung in Office 365.
ms.openlocfilehash: c54508434c5ae5126a79eba1cb6dab3851d8f746
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926443"
---
# <a name="encryption"></a>Verschlüsselung

Verschlüsselung ist ein wichtiger Bestandteil Ihrer Strategie zum Schutz von Dateien und Informationen. Dieser Artikel enthält eine Übersicht über die Verschlüsselung für Office 365. Erhalten Sie Hilfe zu Verschlüsselungsaufgaben, z. B. zum Einrichten der Verschlüsselung für Ihre Organisation und zum Kennwortschutz von Office-Dokumenten.
  
- Informationen zu Zertifikaten und Technologien wie TLS finden Sie unter [Technische Referenzdetails zur Verschlüsselung in Office 365](technical-reference-details-about-encryption.md).

- Informationen zum Konfigurieren oder Einrichten der Verschlüsselung für Ihre Organisation finden Sie unter Einrichten der Verschlüsselung [in Office 365 Enterprise](set-up-encryption.md).

## <a name="what-is-encryption-and-how-does-it-work-in-office-365"></a>Was ist Verschlüsselung, und wie funktioniert sie in Office 365?

Der Verschlüsselungsprozess codiert Ihre Daten (als Klartext bezeichnet) in Chiffretext. Im Gegensatz zu Klartext kann Chiffretext nur dann von Personen oder Computern verwendet werden, wenn der Chiffretext entschlüsselt ist. Die Entschlüsselung erfordert einen Verschlüsselungsschlüssel, über den nur autorisierte Benutzer verfügen. Die Verschlüsselung trägt dazu bei, dass nur autorisierte Empfänger Ihre Inhalte entschlüsseln können. Der Inhalt umfasst Dateien, E-Mail-Nachrichten, Kalendereinträge und so weiter.
  
Die Verschlüsselung allein verhindert nicht das Abfangen von Inhalten. Verschlüsselung ist Teil einer umfangreicheren Strategie zum Schutz von Informationen für Ihre Organisation. Mithilfe der Verschlüsselung stellen Sie sicher, dass nur autorisierte Parteien die verschlüsselten Daten verwenden können.
  
Sie können mehrere Verschlüsselungsebenen gleichzeitig verwenden. Beispielsweise können Sie E-Mail-Nachrichten und auch die Kommunikationskanäle verschlüsseln, über die Ihre E-Mails fließen. Mit Office 365 werden Ihre Daten im Ruhe- und Übertragungsverkehr verschlüsselt, mit mehreren starken Verschlüsselungsprotokollen und Technologien, die Transport Layer Security/Secure Sockets Layer (TLS/SSL), Internet Protocol Security (IPSec) und Advanced Encryption Standard (AES) umfassen.
  
## <a name="encryption-for-data-at-rest-and-data-in-transit"></a>Verschlüsselung für ruhende Daten und Daten, die übertragen werden

  Beispiele für Ruhedaten sind Dateien, die Sie in eine #A0 hochgeladen haben, Project #A1, Dokumente, die Sie in einer Skype for #A1 hochgeladen haben, E-Mail-Nachrichten und Anlagen, die Sie in Ordnern in Ihrem Postfach gespeichert haben, und Dateien, die Sie in OneDrive for Business hochgeladen haben.
  
 **Beispiele für Daten bei der Übertragung** sind E-Mail-Nachrichten, die gerade zugestellt werden, oder Unterhaltungen, die in einer Online-Besprechung stattfinden. In Office 365 werden Daten übertragen, wenn das Gerät eines Benutzers mit einem Microsoft-Server kommuniziert oder wenn ein Microsoft-Server mit einem anderen Server kommuniziert.
  
Mit Office 365 arbeiten mehrere Ebenen und Arten von Verschlüsselung zusammen, um Ihre Daten zu schützen. Die folgende Tabelle enthält einige Beispiele mit Links zu zusätzlichen Informationen.
  
|**Arten von Inhalten**|**Verschlüsselungstechnologien**|**Ressourcen mit mehr Informationen**|
|:-----|:-----|:-----|
|Dateien auf einem Gerät. Diese Dateien können E-Mail-Nachrichten enthalten, die in einem Ordner gespeichert sind, Office-Dokumente, die auf einem Computer, Tablet oder Smartphone gespeichert sind, oder Daten, die in der Microsoft Cloud gespeichert sind.  <br/> |BitLocker in Microsoft-Rechenzentren. BitLocker kann auch auf Clientcomputern wie Windows-Computern und Tablets verwendet werden  <br/> Distributed Key Manager (DKM) in Microsoft-Rechenzentren  <br/> Kundenschlüssel für Microsoft 365  <br/> |[Windows IT Center: BitLocker](/windows/device-security/bitlocker/bitlocker-overview) <br/> [Microsoft Trust Center: Verschlüsselung](https://www.microsoft.com/TrustCenter/Security/Encryption) <br/> [Reihe von Cloudsicherheitssteuerelementen: Verschlüsseln von Ruhedaten](https://blogs.microsoft.com/microsoftsecure/2015/09/10/cloud-security-controls-series-encrypting-data-at-rest) <br/> [Schützen von vertraulichen Inhalten in E-Mails mit Exchange Online](exchange-online-secures-email-secrets.md) <br/> [Dienstverschlüsselung mit Kundenschlüssel](customer-key-overview.md) <br/> |
|Dateien, die zwischen Benutzern übertragen werden. Diese Dateien können Office-Dokumente oder SharePoint-Listenelemente enthalten, die von Benutzern freigegeben wurden.  <br/> |TLS für Übertragene Dateien  <br/> |[Datenverschlüsselung in OneDrive for Business und SharePoint Online](data-encryption-in-odb-and-spo.md) <br/> [Skype for Business Online: Sicherheit und Archivierung](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features) <br/> |
|E-Mails, die zwischen Empfängern gesendet werden. Diese E-Mail enthält E-Mails, die von Exchange Online gehostet werden.  <br/> |Office 365-Nachrichtenverschlüsselung mit Azure Rights Management, S/MIME und TLS für E-Mails bei der Übertragung  <br/> |[Office 365-Nachrichtenverschlüsselung (OME)](ome.md) <br/> [E-Mail-Verschlüsselung in Office 365](email-encryption.md) <br/> [Wie Exchange Online mithilfe von TLS E-Mail-Verbindungen in Office 365 sichert](exchange-online-uses-tls-to-secure-email-connections.md) <br/> |
|Chats, Nachrichten und Dateien, die zwischen Empfängern mit Microsoft Teams übertragen werden. <br/> |Teams verwendet TLS und MTLS zum Verschlüsseln von Chatnachrichten. Mediendatenverkehr wird mithilfe von Secure RTP (SRTP) verschlüsselt. Teams verwendet FIPS (Federal Information Processing Standard) kompatible Algorithmen für den Austausch von Verschlüsselungsschlüsseln. <br/> |[Verschlüsselung für Teams](/microsoftteams/teams-security-guide#encryption-for-teams) <br/> |

## <a name="what-if-i-need-more-control-over-encryption-to-meet-security-and-compliance-requirements"></a>Was passiert, wenn ich mehr Kontrolle über die Verschlüsselung benötigt, um Sicherheits- und Complianceanforderungen zu erfüllen?

Microsoft 365 bietet von Microsoft verwaltete Lösungen für volume encryption, file encryption und mailbox encryption in Office 365. Darüber hinaus bietet Microsoft Verschlüsselungslösungen, die Sie verwalten und steuern können. Diese Verschlüsselungslösungen sind auf Azure aufgebaut.
  
Weitere Informationen hierzu finden Sie in den folgenden Ressourcen:
  
- [Was ist Azure Rights Management?](/information-protection/understand-explore/what-is-azure-rms)

- [Aktivieren der Rechteverwaltung im Admin Center](../enterprise/activate-rms-in-microsoft-365.md)

- [Einrichten von Information Rights Management (IRM) im SharePoint Admin Center](set-up-irm-in-sp-admin-center.md)

- [Dienstverschlüsselung mit Kundenschlüssel in Office 365](customer-key-overview.md)

- [Doppelschlüsselverschlüsselung für Microsoft 365](double-key-encryption.md)

## <a name="how-do-i"></a>Gewusst wie...

|**So tun Sie diese Aufgabe**|**Siehe diese Ressourcen**|
|:-----|:-----|
|Einrichten der Verschlüsselung für meine Organisation  <br/> |[Einrichten der Verschlüsselung in Office 365 Enterprise](set-up-encryption.md) <br/> |
|Anzeigen von Details zu Zertifikaten, Technologien und TLS-Verschlüsselungssuiten <br/> |[Technische Details zur Verschlüsselung](technical-reference-details-about-encryption.md) <br/> |
|Arbeiten mit verschlüsselten Nachrichten auf einem mobilen Gerät  <br/> |[Anzeigen verschlüsselter Nachrichten auf Ihrem Android-Gerät](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> [Anzeigen verschlüsselter Nachrichten auf Ihrem iPhone oder iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |
|Verschlüsseln eines Dokuments mithilfe des Kennwortschutzes  <br/><br/>  Der Kennwortschutz wird in einem Browser nicht unterstützt. Verwenden Sie Desktopversionen von Word, Excel und PowerPoint für den Kennwortschutz. |[Hinzufügen oder Entfernen von Schutz in Ihrem Dokument, Ihrer Arbeitsmappe oder Präsentation](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> Wählen Sie einen **Abschnitt Schutz** hinzufügen aus, und lesen Sie verschlüsseln **mit Kennwort**.  |
|Entfernen der Verschlüsselung aus einem Dokument  <br/> |[Hinzufügen oder Entfernen von Schutz in Ihrem Dokument, Ihrer Arbeitsmappe oder Präsentation](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> Wählen Sie einen **Abschnitt Schutz** entfernen aus, und lesen Sie dann Entfernen **der Kennwortverschlüsselung**.  |


## <a name="related-topics"></a>Verwandte Themen

[Planen von Microsoft 365-Sicherheits- und Informationsschutzfunktionen](plan-for-security-and-compliance.md)

[Die 10 besten Methoden zum Sichern von Microsoft 365 For Business-Plänen](/office365/admin/security-and-compliance/secure-your-business-data)

[Verschlüsselung und Wiedergabefluss auf Microsoft Stream Videoebene](/stream/network-overview#video-level-encryption-and-playback-flow)