---
title: Verschlüsselung
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
description: Mit Office 365 werden Ihre Inhalte im Ruhezustand und in der Übertragung mit der stärksten Verschlüsselung, den verfügbaren Protokollen und Technologien verschlüsselt. Erhalten Sie eine Übersicht über die Verschlüsselung in Office 365.
ms.openlocfilehash: 7a14cb1ab203ef1ee75962f4e55b4220c4ba06d9
ms.sourcegitcommit: 234726a1795d984c4659da68f852d30a4dda5711
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "46794174"
---
# <a name="encryption"></a>Verschlüsselung

Die Verschlüsselung ist ein wichtiger Bestandteil ihrer Dateischutz-und Informationsschutz Strategie. Dieser Artikel enthält eine Übersicht über die Verschlüsselung für Office 365. Erhalten Sie Hilfe zu Verschlüsselungsaufgaben, beispielsweise zum Einrichten der Verschlüsselung für Ihre Organisation und zum Kennwortschutz für Office-Dokumente.
  
- Informationen zu Zertifikaten und Technologien wie TLS finden Sie unter [technische Referenzdetails zur Verschlüsselung in Office 365](technical-reference-details-about-encryption.md).

- Informationen zum Konfigurieren oder Einrichten der Verschlüsselung für Ihre Organisation finden Sie unter Einrichten der [Verschlüsselung in Office 365 Enterprise](set-up-encryption.md).

## <a name="what-is-encryption-and-how-does-it-work-in-office-365"></a>Was ist Verschlüsselung und wie funktioniert Sie in Office 365?

Durch den Verschlüsselungsprozess werden Ihre Daten (als Klartext bezeichnet) in verschlüsselter Textform codiert. Im Gegensatz zum Klartext kann der verschlüsselte Text nicht von Personen oder Computern verwendet werden, es sei denn, der verschlüsselte verschlüsselt wird. Für die Entschlüsselung ist ein Verschlüsselungsschlüssel erforderlich, den nur autorisierte Benutzer besitzen. Durch die Verschlüsselung wird sichergestellt, dass nur autorisierte Empfänger Ihre Inhalte entschlüsseln können. Inhalt umfasst Dateien, e-Mail-Nachrichten, Kalendereinträge usw.
  
Durch die Verschlüsselung allein wird das Abhören von Inhalten nicht verhindert. Die Verschlüsselung ist Teil einer umfassenderen Informationsschutz Strategie für Ihre Organisation. Mithilfe der Verschlüsselung stellen Sie sicher, dass nur autorisierte Personen die verschlüsselten Daten verwenden können.
  
Sie können mehrere Verschlüsselungsebenen gleichzeitig einsetzen. Beispielsweise können Sie e-Mail-Nachrichten und auch die Kommunikationskanäle verschlüsseln, über die Ihre e-Mails fließt. Mit Office 365 werden Ihre Daten im Ruhezustand und in der Übertragung verschlüsselt, wobei mehrere starke Verschlüsselungsprotokolle und Technologien verwendet werden, die Transport Layer Security/Secure Sockets Layer (TLS/SSL), Internet Protocol Security (IPSec) und Advanced Encryption Standard (AES) umfassen.
  
## <a name="encryption-for-data-at-rest-and-data-in-transit"></a>Verschlüsselung von Daten im Ruhezustand und Daten während der Übertragung

 **Beispiele für Daten im Ruhezustand** sind Dateien, die Sie in eine SharePoint-Bibliothek hochgeladen haben, Project Online Daten, Dokumente, die Sie in einer Skype for Business Besprechung hochgeladen haben, e-Mail-Nachrichten und Anlagen, die Sie in Ordnern in Ihrem Postfach gespeichert haben, und Dateien, die Sie in OneDrive für Unternehmen hochgeladen haben.
  
 **Beispiele für Daten in Transit** sind e-Mail-Nachrichten, die gerade zugestellt werden, oder Unterhaltungen, die in einer Onlinebesprechung stattfinden. In Office 365 werden Daten immer dann übertragen, wenn das Gerät eines Benutzers mit einem Microsoft-Server kommuniziert oder wenn ein Microsoft-Server mit einem anderen Server kommuniziert.
  
Mit Office 365 arbeiten mehrere Ebenen und Verschlüsselungstypen zusammen, um Ihre Daten zu schützen. Die folgende Tabelle enthält einige Beispiele mit Links zu zusätzlichen Informationen.
  
|**Arten von Inhalten**|**Verschlüsselungstechnologien**|**Ressourcen mit mehr Informationen**|
|:-----|:-----|:-----|
|Dateien auf einem Gerät. Diese Dateien können e-Mail-Nachrichten enthalten, die in einem Ordner gespeichert sind, auf einem Computer, einem Tablet oder einem Telefon gespeicherte Office-Dokumente oder in der Microsoft-Cloud gespeicherte Daten.  <br/> |BitLocker in Microsoft-Datencentern. BitLocker kann auch auf Clientcomputern verwendet werden, wie Windows-Computer und Tablets  <br/> Distributed Key Manager (DKM) in Microsoft-Rechenzentren  <br/> Kundenschlüssel für Microsoft 365  <br/> |[Windows-IT-Center: BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) <br/> [Microsoft Trust Center: Verschlüsselung](https://www.microsoft.com/TrustCenter/Security/Encryption) <br/> [Cloud Security Controls Series: Verschlüsseln von Daten im Ruhezustand](https://blogs.microsoft.com/microsoftsecure/2015/09/10/cloud-security-controls-series-encrypting-data-at-rest) <br/> [Schützen von vertraulichen Inhalten in E-Mails mit Exchange Online](exchange-online-secures-email-secrets.md) <br/> [Dienstverschlüsselung mit dem Kundenschlüssel](customer-key-overview.md) <br/> |
|Dateien während der Übertragung zwischen Benutzern. Diese Dateien können Office-Dokumente oder SharePoint-Listenelemente enthalten, die von Benutzern gemeinsam verwendet werden.  <br/> |TLS für Dateien während der Übertragung  <br/> |[Datenverschlüsselung in OneDrive for Business und SharePoint Online](data-encryption-in-odb-and-spo.md) <br/> [Skype for Business Online: Sicherheit und Archivierung](https://technet.microsoft.com/library/skype-for-business-online-security-and-archiving.aspx) <br/> |
|E-Mails während der Übertragung zwischen Empfängern. Diese e-Mail enthält e-Mails, die von Exchange Online gehostet werden.  <br/> |Office 365 Nachrichtenverschlüsselung mit Azure Rights Management, S/MIME und TLS für e-Mails bei der Übertragung  <br/> |[Office 365-Nachrichtenverschlüsselung (OME)](ome.md) <br/> [E-Mail-Verschlüsselung in Office 365](email-encryption.md) <br/> [Wie Exchange Online mithilfe von TLS E-Mail-Verbindungen in Office 365 sichert](exchange-online-uses-tls-to-secure-email-connections.md) <br/> |
|Chats, Nachrichten und Dateien während der Übertragung zwischen Empfängern mithilfe von Microsoft Teams. <br/> |Microsoft Teams verwendet TLS und MTLS zum Verschlüsseln von Chatnachrichten. Der Mediendatenverkehr wird mithilfe von SRTP (Secure RTP) verschlüsselt. Microsoft Teams verwendet FIPS (Federal Information Processing Standard)-konforme Algorithmen für den Austausch von Verschlüsselungsschlüsseln. <br/> |[Verschlüsselung für Teams](https://docs.microsoft.com/microsoftteams/teams-security-guide#encryption-for-teams) <br/> |

## <a name="what-if-i-need-more-control-over-encryption-to-meet-security-and-compliance-requirements"></a>Was ist, wenn ich mehr Kontrolle über die Verschlüsselung brauche, um Sicherheits-und Compliance-Anforderungen zu erfüllen?

Microsoft 365 bietet von Microsoft verwaltete Lösungen für die Volumen Verschlüsselung, die Dateiverschlüsselung und die Postfachverschlüsselung in Office 365. Darüber hinaus bietet Microsoft Verschlüsselungslösungen, die Sie verwalten und steuern können. Diese Verschlüsselungslösungen sind auf Azure aufgebaut.
  
Weitere Informationen hierzu finden Sie in den folgenden Ressourcen:
  
- [Was ist Azure Rights Management?](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)

- [Aktivieren der Rechteverwaltung im Admin Center](https://docs.microsoft.com/office365/enterprise/activate-rms-in-office-365)

- [Set up Information Rights Management (IRM) in SharePoint admin center](set-up-irm-in-sp-admin-center.md)

- [Dienstverschlüsselung mit Kundenschlüssel in Office 365](customer-key-overview.md)

## <a name="how-do-i"></a>Gewusst wie...

|**So führen Sie diese Aufgabe aus**|**Siehe diese Ressourcen**|
|:-----|:-----|
|Einrichten der Verschlüsselung für meine Organisation  <br/> |[Einrichten der Verschlüsselung in Office 365 Enterprise](set-up-encryption.md) <br/> |
|Anzeigen von Details zu Zertifikaten, Technologien und TLS-Verschlüsselungs Paketen <br/> |[Technische Details zur Verschlüsselung](technical-reference-details-about-encryption.md) <br/> |
|Arbeiten mit verschlüsselten Nachrichten auf einem mobilen Gerät  <br/> |[Anzeigen von verschlüsselten Nachrichten auf Ihrem Android-Gerät](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> [Verschlüsselte Nachrichten auf Ihrem iPhone oder iPad anzeigen](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |
|Verschlüsseln eines Dokuments mithilfe des Kennwortschutzes  <br/><br/>  Der Kennwortschutz wird in einem Browser nicht unterstützt. Verwenden Sie Desktop Versionen von Word, Excel und PowerPoint für den Kennwortschutz. |[Hinzufügen oder Entfernen von Schutz in Ihrem Dokument, in einer Arbeitsmappe oder in einer Präsentation](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> Wählen Sie einen Abschnitt **Schutz hinzufügen** aus, und lesen Sie dann **verschlüsseln mit Kennwort**.  |
|Entfernen der Verschlüsselung aus einem Dokument  <br/> |[Hinzufügen oder Entfernen von Schutz in Ihrem Dokument, in einer Arbeitsmappe oder in einer Präsentation](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> Wählen Sie einen Abschnitt zum **Entfernen des Schutzes** aus, und entfernen Sie dann die **Kennwortverschlüsselung**.  |


## <a name="related-topics"></a>Verwandte Themen

[Planen der Sicherheits-und Informationsschutzfunktionen von Microsoft 365](plan-for-security-and-compliance.md)

[Die 10 wichtigsten Möglichkeiten zum Sichern von Microsoft 365 for Business-Plänen](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data?view=o365-worldwide)

[Microsoft Stream Video Level-Verschlüsselung und-Wiedergabe-Fluss](https://docs.microsoft.com/stream/network-overview#video-level-encryption-and-playback-flow)
