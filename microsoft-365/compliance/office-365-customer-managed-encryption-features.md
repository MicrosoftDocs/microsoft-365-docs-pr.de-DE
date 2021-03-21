---
title: Vom Kunden verwaltete Verschlüsselungsfunktionen
f1.keywords:
- NOCSH
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
ms.custom:
- seo-marvel-mar2020
description: In diesem Artikel erfahren Sie mehr über Verschlüsselungstechnologien, die Sie in Microsoft 365 verwalten und konfigurieren können.
ms.openlocfilehash: 6a693c512100c59eef47414fdd6eab4a2924e835
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926233"
---
# <a name="customer-managed-encryption-features"></a>Vom Kunden verwaltete Verschlüsselungsfunktionen

Zusammen mit den von Microsoft verwalteten Verschlüsselungstechnologien in Microsoft 365 arbeitet Microsoft 365 auch mit zusätzlichen Verschlüsselungstechnologien, die Sie verwalten und konfigurieren können, z. B.:

- [Azure Rights Management](/azure/information-protection/what-is-azure-rms)

- [Secure Multipurpose Internet Mail Extension](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)

- [Office 365-Nachrichtenverschlüsselung](https://products.office.com/en-us/exchange/office-365-message-encryption)

- [Sicherer E-Mail-Fluss mit einer Partnerorganisation](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

Weitere Informationen zu diesen Technologien finden Sie in den [Microsoft 365-Dienstbeschreibungen](/office365/servicedescriptions/office-365-service-descriptions-technet-library).

## <a name="azure-rights-management"></a>Azure Rights Management

[Azure Rights Management](/azure/information-protection/what-is-azure-rms) (Azure RMS) ist die von Azure Information Protection verwendete [Schutztechnologie.](/information-protection/understand-explore/what-is-information-protection) Es verwendet Verschlüsselungs-, Identitäts- und Autorisierungsrichtlinien, um Ihre Dateien und E-Mails auf mehreren Plattformen und Geräten zu sichern – Smartphones, Tablets und PCs. Informationen können sowohl innerhalb als auch außerhalb Ihrer Organisation geschützt werden, da der Schutz bei den Daten verbleibt. Azure RMS bietet dauerhaften Schutz aller Dateitypen, schützt Dateien überall, unterstützt die Zusammenarbeit zwischen Unternehmen und eine breite Palette von Windows- und Nicht-Windows-Geräten. Azure RMS-Schutz kann auch Richtlinien zur Verhinderung [von Datenverlust (Data Loss Prevention, DLP) erweitern.](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention) Weitere Informationen dazu, welche Anwendungen und Dienste den Azure Rights Management-Dienst von Azure Information Protection verwenden können, finden Sie unter [How applications support the Azure Rights Management service](/information-protection/understand-explore/applications-support).

Azure RMS ist in Microsoft 365 integriert und für alle Kunden verfügbar. Informationen zum Konfigurieren von Microsoft 365 für die Verwendung von Azure RMS finden Sie unter [Configure IRM to use Azure Rights Management and Set up Information Rights Management (IRM) in SharePoint Admin Center](../enterprise/activate-rms-in-microsoft-365.md). Wenn Sie einen lokalen Active Directory (AD)-RMS-Server verwenden, können Sie IRM auch für die Verwendung eines lokalen [AD RMS-Servers](/office365/SecurityCompliance/configure-irm-to-use-an-on-premises-ad-rms-server)konfigurieren. Es wird jedoch dringend empfohlen, zu [Azure RMS](/azure/information-protection/migrate-from-ad-rms-to-azure-rms) zu migrieren, um neue Features wie die sichere Zusammenarbeit mit anderen Organisationen zu verwenden.

Wenn Sie Kundendaten mit Azure RMS schützen, verwendet Azure RMS einen asymmetrischen 2048-Bit-RSA-Schlüssel mit SHA-256-Hashalgorithmus, um die Daten zu verschlüsseln. Der symmetrische Schlüssel für Office-Dokumente und -E-Mails ist AES 128-Bit. Für jedes Dokument oder jede E-Mail, die durch Azure RMS geschützt ist, erstellt Azure RMS einen einzelnen AES-Schlüssel (den "Inhaltsschlüssel"), der in das Dokument eingebettet ist und über Editionen des Dokuments beibehalten wird. Der Inhaltsschlüssel ist mit dem RSA-Schlüssel der Organisation (dem "Azure Information Protection-Mandantenschlüssel") als Teil der Richtlinie im Dokument geschützt, und die Richtlinie wird auch vom Autor des Dokuments signiert. Dieser Mandantenschlüssel ist für alle Dokumente und E-Mails üblich, die von Azure RMS für die Organisation geschützt sind, und dieser Schlüssel kann nur von einem Azure Information Protection-Administrator geändert werden, wenn die Organisation einen Mandantenschlüssel verwendet, der vom Kunden verwaltet wird. Weitere Informationen zu den von Azure RMS verwendeten kryptografischen Steuerelementen finden Sie unter [Funktionsweise von Azure RMS? Unter der Blende](/information-protection/understand-explore/how-does-it-work).

In einer standardmäßigen Azure RMS-Implementierung generiert und verwaltet Microsoft den Stammschlüssel, der für jeden Mandanten eindeutig ist. Kunden können den Lebenszyklus ihres Stammschlüssels in Azure RMS mit Azure Key Vault Services verwalten, indem sie eine Schlüsselverwaltungsmethode namens [Bring Your Own Key (BYOK)](/azure/information-protection/plan-implement-tenant-key) verwenden, mit der Sie Ihren Schlüssel in lokalen HSMs (Hardwaresicherheitsmodulen) generieren können und diesen Schlüssel nach der Übertragung auf die von Microsoft fiPS 140-2 überprüften HSMs der Stufe 2 steuern können. Der Zugriff auf den Stammschlüssel wird keinem Personal gegeben, da die Schlüssel nicht exportiert oder aus den hsMs extrahiert werden können, die sie schützen. Darüber hinaus können Sie jederzeit auf ein Nahezu-Echtzeitprotokoll zugreifen, in dem der Zugriff auf den Stammschlüssel angezeigt wird. Weitere Informationen finden Sie unter [Logging and Analyzing Azure Rights Management Usage](/azure/information-protection/log-analyze-usage).

Azure Rights Management trägt dazu bei, Bedrohungen wie Drahtzapfen, Man-in-the-Middle-Angriffe, Datendiebstahl und unbeabsichtigte Verstöße gegen organisatorische Freigaberichtlinien zu mindern. Gleichzeitig wird ein ungerechtfertigter Zugriff von Kundendaten im Transit oder ruhendem Zugriff durch einen nicht autorisierten Benutzer, der nicht über entsprechende Berechtigungen verfügt, über Richtlinien verhindert, die diesen Daten folgen, wodurch das Risiko, dass diese Daten wissentlich oder unwissentlich in falsche Hände geraten und Funktionen zur Verhinderung von Datenverlust zur Verfügung stehen, gemildert wird. Wenn Azure RMS als Teil von Azure Information Protection verwendet wird, bietet Azure RMS auch Funktionen zur Datenklassifizierung und Bezeichnung, Inhaltskennzeichnung, Dokumentzugriffsverfolgung und Zugriffssperrung. Weitere Informationen zu diesen Funktionen finden Sie unter [What is Azure Information Protection](/information-protection/understand-explore/what-is-information-protection), Azure Information Protection deployment [roadmap](/information-protection/plan-design/deployment-roadmap)und Quick start tutorial for Azure [Information Protection](/information-protection/get-started/infoprotect-quick-start-tutorial).

## <a name="secure-multipurpose-internet-mail-extension"></a>Secure Multipurpose Internet Mail Extension

Secure/Multipurpose Internet Mail Extensions (S/MIME) ist ein Standard für die Verschlüsselung öffentlicher Schlüssel und die digitale Signatur von MIME-Daten. S/MIME ist in RFCs 3369, 3370, 3850, 3851 und anderen definiert. Es ermöglicht einem Benutzer, eine E-Mail zu verschlüsseln und eine E-Mail digital zu signieren. Eine E-Mail, die mit S/MIME verschlüsselt wird, kann nur vom Empfänger der E-Mail mithilfe des privaten Schlüssels entschlüsselt werden, der nur für den Empfänger verfügbar ist. Daher können die E-Mails nicht von einem anderen Benutzer als dem Empfänger der E-Mail entschlüsselt werden.

[Microsoft unterstützt S/MIME](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx). Öffentliche Zertifikate werden an das lokale Active Directory des Kunden verteilt und in Attributen gespeichert, die in einen Microsoft 365-Mandanten repliziert werden können. Die privaten Schlüssel, die den öffentlichen Schlüsseln entsprechen, bleiben lokal und werden niemals an Office 365 übertragen. Benutzer können E-Mails zwischen zwei Benutzern in einer Organisation erstellen, verschlüsseln, entschlüsseln, lesen und digital signieren, indem sie Outlook, Outlook im Web und Exchange ActiveSync verwenden. Weitere Informationen finden Sie unter [S/MIME-Verschlüsselung jetzt in Office 365](https://blogs.office.com/2014/02/26/smime-encryption-now-in-office-365/).

## <a name="office-365-message-encryption"></a>Office 365-Nachrichtenverschlüsselung

[Office 365 Message Encryption](https://products.office.com/exchange/office-365-message-encryption) (OME) baut auf [Azure Information Protection](/information-protection/understand-explore/what-is-information-protection) (AIP) auf und ermöglicht es Ihnen, verschlüsselte und rechtegeschützte E-Mails an alle Benutzer zu senden. OME entschärft Bedrohungen wie Drahtzapfen und Man-in-the-Middle-Angriffe sowie andere Bedrohungen, z. B. den ungerechtfertigten Zugriff auf Daten durch einen nicht autorisierten Benutzer, der nicht über entsprechende Berechtigungen verfügt. Wir haben Investitionen getätigt, die Ihnen eine einfachere, intuitivere und sichere E-Mail-Oberfläche bieten, die auf Azure Information Protection baut. Sie können Nachrichten, die von Microsoft 365 an alle Personen innerhalb oder außerhalb Ihrer Organisation gesendet werden, schützen. Diese Nachrichten können über verschiedene E-Mail-Clients mit einer beliebigen Identität angezeigt werden, einschließlich Azure Active Directory, Microsoft Account und Google IDs. Weitere Informationen dazu, wie Ihre Organisation verschlüsselte Nachrichten verwenden kann, finden Sie unter [Office 365 Message Encryption](./ome.md).

## <a name="transport-layer-security"></a>Transport Layer Security   

Wenn Sie eine sichere Kommunikation mit einem Partner sicherstellen möchten, können Sie eingehende und ausgehende Connectors verwenden, um Sicherheit und Nachrichtenintegrität zu gewährleisten. Sie können erzwungene eingehende und ausgehende TLS für jeden Connector mithilfe eines Zertifikats konfigurieren. Die Verwendung eines verschlüsselten SMTP-Kanals kann verhindern, dass Daten über einen Man-in-the-Middle-Angriff gestohlen werden. Weitere Informationen finden Sie unter [So verwendet Exchange Online TLS zum Sichern von E-Mail-Verbindungen.](./exchange-online-uses-tls-to-secure-email-connections.md)

## <a name="domain-keys-identified-mail"></a>Identifizierte E-Mail-Domänenschlüssel

Exchange Online Protection (EOP) und Exchange Online unterstützen die eingehende Validierung von Domain Keys Identified Mail(DKIM)-Nachrichten. DKIM ist eine Methode, anhand derer validiert wird, dass eine Nachricht von der angegebenen Domian stammt und nicht von jemand anderem gefälscht wurde. Sie bindet eine E-Mail-Nachricht an die Organisation, die sie sendet, und ist Teil eines größeren Paradigmas der E-Mail-Verschlüsselung. Weitere Informationen zu den drei Teilen dieses Paradigmas finden Sie unter:

- [Einrichten von SPF zum Verhindern von Spoofing](/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)

- [Verwenden von DKIM zum Überprüfen ausgehender E-Mails, die von Ihrer benutzerdefinierten Domäne gesendet werden](/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)

- [Verwenden von DMARC zum Überprüfen von E-Mails](/office365/SecurityCompliance/use-dmarc-to-validate-email)