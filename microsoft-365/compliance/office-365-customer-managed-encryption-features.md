---
title: Office 365 von Kunden verwalteten Verschlüsselungsfeatures
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Zusammenfassung: Grundlegendes zur Ausfallsicherheit von Daten in Microsoft Office 365.'
ms.openlocfilehash: f96e87199b4f09ecce5c4c5b49212d4320b5ce8c
ms.sourcegitcommit: 93cef4906c5495ae293450ceb52d6cc336f52b53
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2019
ms.locfileid: "38690521"
---
# <a name="customer-managed-encryption-features-in-office-365"></a>Von Kunden verwaltete Verschlüsselungsfeatures in Office 365

Zusammen mit den Verschlüsselungstechnologien in Office 365, die von Microsoft verwaltet werden, arbeitet Office 365 auch mit zusätzlichen Verschlüsselungstechnologien, die Sie verwalten und konfigurieren können, beispielsweise:

- [Azure Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)

- [Sichere Mehrzweck-Internet-e-Mail-Erweiterung](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)

- [Office 365-Nachrichtenverschlüsselung](https://products.office.com/en-us/exchange/office-365-message-encryption)

- [Sicherer e-Mail-Fluss mit einer Partnerorganisation](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

Weitere Informationen zu diesen Technologien finden Sie in den [Office 365-Dienstbeschreibungen](https://technet.microsoft.com/library/office-365-service-descriptions.aspx).

## <a name="azure-rights-management"></a>Azure Rights Management

Azure [Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) (Azure RMS) ist die Schutztechnologie, die von [Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)verwendet wird. Es verwendet Verschlüsselungs-, Identitäts-und Autorisierungsrichtlinien, um Ihre Dateien und e-Mails auf mehreren Plattformen und Geräten zu schützen – Telefone, Tablets und PCs. Informationen können sowohl innerhalb als auch außerhalb Ihrer Organisation geschützt werden, da der Schutz mit den Daten verbleibt. Azure RMS bietet beständigen Schutz aller Dateitypen, schützt Dateien überall, unterstützt die Zusammenarbeit zwischen Business-to-Business und eine große Auswahl an Windows-und nicht-Windows-Geräten. Azure RMS Protection kann auch [Datenverlust Verhinderung (DLP)-Richtlinien](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)erweitern. Weitere Informationen darüber, welche Anwendungen und Dienste den Azure Rights Management-Dienst aus Azure Information Protection verwenden können, finden Sie unter [Unterstützung von Azure Rights Management Service durch Anwendungen](https://docs.microsoft.com/information-protection/understand-explore/applications-support).

Azure RMS ist in Office 365 integriert und steht allen Office 365-Kunden zur Verfügung. Informationen zum Konfigurieren von Office 365 für die Verwendung von Azure RMS finden Sie unter [Konfigurieren von IRM für die Verwendung von Azure Rights Management und Einrichten der Verwaltung von Informationsrechten (IRM) in SharePoint Admin Center](https://technet.microsoft.com/library/dn151475(v=exchg.150).aspx). Wenn Sie einen AD-RMS-Server (lokale Active Directory) verwenden, können Sie auch [IRM so konfigurieren, dass ein lokaler AD RMS-Server verwendet](https://docs.microsoft.com/office365/SecurityCompliance/configure-irm-to-use-an-on-premises-ad-rms-server)wird, es wird jedoch dringend empfohlen, zu [Azure RMS zu migrieren](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms) , um neue Features wie die sichere Zusammenarbeit mit anderen Organisationen zu nutzen.

Wenn Sie Kundendaten mit Azure RMS schützen, verwendet Azure RMS einen 2048-Bit-RSA-asymmetrischen Schlüssel mit SHA-256-Hashalgorithmus für die Integrität, um die Daten zu verschlüsseln. Der symmetrische Schlüssel für Office-Dokumente und e-Mails lautet AES 128-Bit (CBC-Modus mit PKCS # 7-Auffüllung). Für jedes Dokument oder jede e-Mail-Nachricht, die von Azure RMS geschützt ist, erstellt Azure RMS einen einzelnen AES-Schlüssel (den "Inhaltsschlüssel"), und dieser Schlüssel ist in das Dokument eingebettet und wird in Editionen des Dokuments gespeichert. Der Inhaltsschlüssel ist mit dem RSA-Schlüssel der Organisation (dem "Azure Information Protection-Mandanten Schlüssel") als Teil der Richtlinie im Dokument geschützt, und die Richtlinie wird auch vom Autor des Dokuments signiert. Dieser Mandanten Schlüssel ist für alle Dokumente und e-Mails üblich, die von Azure RMS für die Organisation geschützt sind, und dieser Schlüssel kann nur von einem Azure Information Protection-Administrator geändert werden, wenn die Organisation einen Mandanten Schlüssel verwendet, der vom Kunden verwaltet wird. Weitere Informationen zu den von Azure RMS verwendeten kryptografischen Steuerelementen finden Sie unter [wie funktioniert Azure RMS? Unter der Haube](https://docs.microsoft.com/information-protection/understand-explore/how-does-it-work).

In einer standardmäßigen Azure RMS-Implementierung generiert und verwaltet Microsoft den Stammschlüssel, der für jeden Mandanten eindeutig ist. Kunden können den Lebenszyklus Ihres Stammschlüssels in Azure RMS mit Azure Key Vault Services verwalten, indem Sie eine Schlüssel Verwaltungsmethode mit dem Namen " [Bring your own Key" (BYOK)](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key) verwenden, mit der Sie Ihren Schlüssel in lokalen HSMs (Hardwaresicherheitsmodulen) generieren und nach der Übertragung an den FIPS 140-2 Level 2-validierten HSMs von Microsoft die Kontrolle über diesen Schlüssel behalten können. Der Zugriff auf den Stammschlüssel wird keinem Personal gewährt, da die Schlüssel nicht aus dem HSMs exportiert oder extrahiert werden können, um Sie zu schützen. Außerdem können Sie jederzeit auf ein near-Echtzeitprotokoll zugreifen, in dem der gesamte Zugriff auf den Stammschlüssel angezeigt wird. Weitere Informationen finden Sie unter [Logging and Analyse Azure Rights Management Usage](https://docs.microsoft.com/azure/information-protection/log-analyze-usage).

Azure Rights Management hilft bei der Abwehr von Bedrohungen wie Draht Anschlägen, man-in-the-Middle-Angriffen, Datendiebstahl und unbeabsichtigten Verstößen gegen organisatorische Freigaberichtlinien. Gleichzeitig wird ein ungerechtfertigter Zugriff auf Kundendaten, die von einem nicht autorisierten Benutzer, der nicht über die entsprechenden Berechtigungen verfügt, über eine Richtlinie, die diesen Daten folgt, verhindert, wodurch das Risiko verringert wird, dass Daten in die falschen Hände fallen. wissentlich oder unwissentlich und Bereitstellen von Funktionen zur Verhinderung von Datenverlust. Wenn Azure RMS als Teil von Azure Information Protection verwendet wird, bietet er auch Daten Klassifizierungs-und Beschriftungsfunktionen, Inhalts Markierung, Dokumentzugriffs Verfolgung und Zugriffs Sperrfunktionen. Weitere Informationen zu diesen Funktionen finden Sie unter [Was ist Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection), [Azure Information Protection-Bereitstellungswegweiser](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap)und [Schnellstart-Lernprogramm für Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/infoprotect-quick-start-tutorial).

## <a name="secure-multipurpose-internet-mail-extension"></a>Sichere Mehrzweck-Internet-e-Mail-Erweiterung

Secure/Multipurpose Internet Mail Extensions (S/MIME) ist ein Standard für die Verschlüsselung von öffentlichen Schlüsseln und das digitale Signieren von MIME-Daten. S/MIME ist in den RFCs 3369, 3370, 3850, 3851 und anderen definiert. Damit kann ein Benutzer eine e-Mail verschlüsseln und eine e-Mail digital signieren. Eine e-Mail-Nachricht, die mit S/MIME verschlüsselt ist, kann nur vom Empfänger der e-Mail mithilfe des privaten Schlüssels entschlüsselt werden, der nur für diesen Empfänger verfügbar ist. Daher können die e-Mails von keinem anderen als dem Empfänger der e-Mail entschlüsselt werden.

[Microsoft unterstützt S/MIME in Office 365](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx). Öffentliche Zertifikate werden an die lokalen Active Directory des Kunden verteilt und in Attributen gespeichert, die an einen Office 365-Mandanten repliziert werden können. Die privaten Schlüssel, die den öffentlichen Schlüsseln entsprechen, bleiben lokal und werden nie an Office 365 übermittelt. Benutzer können e-Mails zwischen zwei Benutzern in einer Organisation mit Outlook, Outlook im Web und Exchange ActiveSync-Clients verfassen, verschlüsseln, entschlüsseln, lesen und digital signieren. Weitere Informationen finden Sie unter [S/MIME Encryption now in Office 365](https://blogs.office.com/2014/02/26/smime-encryption-now-in-office-365/).

## <a name="office-365-message-encryption"></a>Office 365-Nachrichtenverschlüsselung

Mit der [Office 365-Nachrichtenverschlüsselung](https://products.office.com/exchange/office-365-message-encryption) (OM), die auf dem [Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection) (AIP) basiert, können Sie verschlüsselte und durch Rechte geschützte e-Mails an alle Personen senden. Mit OM werden Bedrohungen wie Draht anzapfungen und man-in-the-Middle-Angriffe sowie andere Bedrohungen wie unbefugter Zugriff von Daten durch einen nicht autorisierten Benutzer, der nicht über die entsprechenden Berechtigungen verfügt, abgefedert. Wir haben Investitionen getätigt, die Ihnen eine einfachere, intuitivere, sichere e-Mail-Erfahrung bieten, die auf dem Azure Information Protection-Bereich basiert. Sie können Nachrichten schützen, die von Office 365 an Personen innerhalb oder außerhalb Ihrer Organisation gesendet werden. Diese Nachrichten können über eine Vielzahl von e-Mail-Clients mit einer beliebigen Identität angezeigt werden, einschließlich Azure Active Directory, Microsoft-Konto und Google IDs. Weitere Informationen dazu, wie Ihre Organisation verschlüsselte Nachrichten verwenden kann, finden Sie unter [Office 365 Nachrichtenverschlüsselung](https://support.office.com/article/F87CB016-7876-4317-AE3C-9169B311FF8A).

## <a name="transport-layer-security"></a>Transport Layer Security   

Wenn Sie eine sichere Kommunikation mit einem Partner sicherstellen möchten, können Sie eingehende und ausgehende Connectors zum Bereitstellen von Sicherheit und Nachrichtenintegrität verwenden. Sie können erzwungene eingehende und ausgehende TLS-Verbindungen für jeden Connector mit einem Zertifikat konfigurieren. Durch die Verwendung eines verschlüsselten SMTP-Kanals kann verhindert werden, dass Daten über einen man-in-the-Middle-Angriff gestohlen werden. Weitere Informationen finden Sie unter [how Exchange Online verwendet TLS zum Sichern von e-Mail-Verbindungen](https://support.office.com/article/How-Exchange-Online-uses-TLS-to-secure-email-connections-in-Office-365-4CDE0CDA-3430-4DC0-B489-F2C0736C929F).

## <a name="domain-keys-identified-mail"></a>Domänenschlüssel identifizierte e-Mail

Exchange Online Protection (EOP) und Exchange Online unterstützen die eingehende Validierung von Domain Keys Identified Mail(DKIM)-Nachrichten. DKIM ist eine Methode, anhand derer validiert wird, dass eine Nachricht von der angegebenen Domian stammt und nicht von jemand anderem gefälscht wurde. Es bindet eine e-Mail-Nachricht an die für das Senden zuständige Organisation und ist Teil eines größeren Paradigmas der e-Mail-Verschlüsselung. Weitere Informationen zu den drei Teilen dieses Paradigmas finden Sie unter:

- [Einrichten von SPF in Office 365 zum Verhindern von Spoofing](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)

- [Verwenden von DKIM zum Überprüfen ausgehender E-Mails, die von Ihrer benutzerdefinierten Domäne in Office 365 gesendet werden](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)

- [Verwenden von DMARC zum Validieren von E-Mails in Office 365](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)
