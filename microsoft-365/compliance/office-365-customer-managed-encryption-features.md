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
ms.openlocfilehash: bb6f9fedf915fd261266a9ed5d0c561d1352ea09
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921555"
---
# <a name="customer-managed-encryption-features"></a>Vom Kunden verwaltete Verschlüsselungsfunktionen

Neben den verschlüsselungstechnologien in Microsoft 365, die von Microsoft verwaltet werden, arbeitet Microsoft 365 auch mit zusätzlichen Verschlüsselungstechnologien, die Sie verwalten und konfigurieren können, z. B.:

- [Azure Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)

- [Secure Multipurpose Internet Mail Extension](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)

- [Office 365-Nachrichtenverschlüsselung](https://products.office.com/en-us/exchange/office-365-message-encryption)

- [Sicherer E-Mail-Fluss mit einer Partnerorganisation](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

Weitere Informationen zu diesen Technologien finden Sie in den [Microsoft 365-Dienstbeschreibungen.](https://technet.microsoft.com/library/office-365-service-descriptions.aspx)

## <a name="azure-rights-management"></a>Azure Rights Management

[Azure Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) (Azure RMS) ist die Schutztechnologie, die von [Azure Information Protection verwendet wird.](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection) Es verwendet Verschlüsselungs-, Identitäts- und Autorisierungsrichtlinien, um Ihre Dateien und E-Mails auf mehreren Plattformen und Geräten – Smartphones, Tablets und PCs – zu schützen. Informationen können sowohl innerhalb als auch außerhalb Ihrer Organisation geschützt werden, da der Schutz der Daten erhalten bleibt. Azure RMS bietet dauerhaften Schutz für alle Dateitypen, schützt Dateien überall, unterstützt die Zusammenarbeit zwischen Unternehmen sowie eine Vielzahl von Windows- und Nicht-Windows-Geräten. Azure RMS Protection kann auch Richtlinien zur Verhinderung von Datenverlust [(Data Loss Prevention, DLP) erweitern.](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention) Weitere Informationen dazu, welche Anwendungen und Dienste den Azure Rights Management-Dienst von Azure Information Protection verwenden können, finden Sie unter Wie Anwendungen den [Azure Rights Management Service unterstützen.](https://docs.microsoft.com/information-protection/understand-explore/applications-support)

Azure RMS ist in Microsoft 365 integriert und für alle Kunden verfügbar. Informationen zum Konfigurieren von Microsoft 365 für die Verwendung von Azure RMS finden Sie unter "Konfigurieren von IRM für die Verwendung von Azure Rights Management und Einrichten von [Information Rights Management (IRM) im SharePoint Admin Center".](https://technet.microsoft.com/library/dn151475(v=exchg.150).aspx) Wenn Sie einen lokalen Active Directory (AD)-RMS-Server verwenden, können Sie IRM auch für die Verwendung eines lokalen [AD -RMS-Servers](https://docs.microsoft.com/office365/SecurityCompliance/configure-irm-to-use-an-on-premises-ad-rms-server)konfigurieren. Es wird jedoch dringend empfohlen, zu [Azure RMS](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms) zu migrieren, um neue Features wie die sichere Zusammenarbeit mit anderen Organisationen zu verwenden.

Wenn Sie Kundendaten mit Azure RMS schützen, verwendet Azure RMS einen asymmetrischen 2048-Bit-RSA-Schlüssel mit SHA-256-Hashalgorithmus, um die Daten zu verschlüsseln. Der symmetrische Schlüssel für Office-Dokumente und -E-Mails ist AES 128-Bit. Azure RMS erstellt für jedes Dokument oder jede E-Mail, das durch Azure RMS geschützt ist, einen einzelnen #A0 (den "Inhaltsschlüssel"), der in das Dokument eingebettet ist und über die Editionen des Dokuments beibehalten wird. Der Inhaltsschlüssel ist durch den RSA-Schlüssel (den "Azure Information Protection-Mandantenschlüssel") der Organisation als Teil der Richtlinie im Dokument geschützt, und die Richtlinie wird auch vom Autor des Dokuments signiert. Dieser Mandantenschlüssel ist für alle Dokumente und E-Mails verfügbar, die durch Azure RMS für die Organisation geschützt sind. Dieser Schlüssel kann nur von einem Azure Information Protection-Administrator geändert werden, wenn die Organisation einen mandantenverschlüsselten Schlüssel verwendet, der vom Kunden verwaltet wird. Weitere Informationen zu den von Azure RMS verwendeten kryptografischen Steuerelementen finden Sie [unter Funktionsweise von Azure RMS. Under the hood](https://docs.microsoft.com/information-protection/understand-explore/how-does-it-work).

In einer standardmäßigen Azure RMS-Implementierung generiert und verwaltet Microsoft den Stammschlüssel, der für jeden Mandanten eindeutig ist. Kunden können den Lebenszyklus ihres Stammschlüssels in Azure RMS mit Azure Key Vault Services verwalten, indem sie eine Schlüsselverwaltungsmethode namens ["Bring Your Own Key" (BYOK)](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key) verwenden, mit der Sie Ihren Schlüssel in lokalen HSMs (Hardwaresicherheitsmodulen) generieren und nach der Übertragung auf die von Microsoft FIPS 140-2 Level 2 überprüften HSMs die Kontrolle über diesen Schlüssel erhalten. Zugriff auf den Stammschlüssel wird keinem Personal gegeben, da die Schlüssel nicht exportiert oder aus den HSMs extrahiert werden können, die sie schützen. Darüber hinaus können Sie jederzeit auf ein Fast-Echtzeit-Protokoll zugreifen, in dem der zugriff auf den Stammschlüssel angezeigt wird. Weitere Informationen finden Sie unter [Protokollierung und Analyse der Azure Rights Management-Nutzung.](https://docs.microsoft.com/azure/information-protection/log-analyze-usage)

Azure Rights Management hilft dabei, Bedrohungen wie Das Abhören von Daten, Man-in-the-Middle-Angriffe, Datendiebstahl und unbeabsichtigte Verstöße gegen Freigaberichtlinien der Organisation abzuschwächen. Gleichzeitig wird der unbefugte Zugriff auf Kundendaten bei der Übertragung oder im Ruhefall durch einen nicht autorisierten Benutzer, der nicht über die entsprechenden Berechtigungen verfügt, über Richtlinien verhindert, die diesen Daten folgen, wodurch das Risiko, dass diese Daten bewusst oder unwissentlich in die falschen Hände fallen und Funktionen zur Verhinderung von Datenverlust bereitstellen, vermieden wird. Wenn Azure RMS als Teil von Azure Information Protection verwendet wird, bietet Azure RMS auch Funktionen zur Datenklassifizierung und -bezeichnung, Inhaltskennzeichnung, Nachverfolgung des Dokumentzugriffs und Zugriffssperrungsfunktionen. Weitere Informationen zu diesen Funktionen finden Sie unter ["Was ist Azure Information Protection",](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)eine [Azure Information Protection-Bereitstellungs-Roadmap](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap)und [ein Schnellstartlernprogramm für Azure Information Protection.](https://docs.microsoft.com/information-protection/get-started/infoprotect-quick-start-tutorial)

## <a name="secure-multipurpose-internet-mail-extension"></a>Secure Multipurpose Internet Mail Extension

Secure/Multipurpose Internet Mail Extensions (S/MIME) ist ein Standard für die Verschlüsselung öffentlicher Schlüssel und die digitale Signierung von MIME-Daten. S/MIME ist in rfCs 3369, 3370, 3850, 3851 und anderen definiert. Es ermöglicht einem Benutzer, eine E-Mail zu verschlüsseln und eine E-Mail digital zu signieren. Eine mit S/MIME verschlüsselte E-Mail kann nur vom Empfänger der E-Mail mithilfe des privaten Schlüssels entschlüsselt werden, der nur für den Empfänger verfügbar ist. Daher können die E-Mails nicht von einem anderen Benutzer als dem Empfänger der E-Mail entschlüsselt werden.

[Microsoft unterstützt S/MIME](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx). Öffentliche Zertifikate werden an das lokale Active Directory des Kunden verteilt und in Attributen gespeichert, die auf einen Microsoft 365-Mandanten repliziert werden können. Die privaten Schlüssel, die den öffentlichen Schlüsseln entsprechen, bleiben lokal und werden niemals an Office 365 übertragen. Benutzer können E-Mails zwischen zwei Benutzern in einer Organisation mithilfe von Outlook, Outlook im Web und Exchange ActiveSync erstellen, verschlüsseln, entschlüsseln, lesen und digital signieren. Weitere Informationen finden Sie jetzt in [Office 365 unter S/MIME-Verschlüsselung.](https://blogs.office.com/2014/02/26/smime-encryption-now-in-office-365/)

## <a name="office-365-message-encryption"></a>Office 365-Nachrichtenverschlüsselung

[Office 365-Nachrichtenverschlüsselung (Office 365 Message Encryption,](https://products.office.com/exchange/office-365-message-encryption) OME), die auf [Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection) (AIP) baut, ermöglicht es Ihnen, verschlüsselte und durch Rechte geschützte E-Mails an alle Benutzer zu senden. OME entschärft Bedrohungen wie Das Abhören von Daten und Man-in-the-Middle-Angriffe sowie andere Bedrohungen, z. B. den nicht berechtigten Zugriff auf Daten durch einen nicht autorisierten Benutzer, der nicht über die entsprechenden Berechtigungen verfügt. Wir haben Investitionen getätigt, die Ihnen eine einfachere, intuitivere und sichere E-Mail-Erfahrung bieten, die auf Azure Information Protection aufgebaut ist. Sie können Nachrichten schützen, die von Microsoft 365 an alle Personen innerhalb oder außerhalb Ihrer Organisation gesendet werden. Diese Nachrichten können in einer Vielzahl von E-Mail-Clients angezeigt werden, die eine beliebige Identität verwenden, einschließlich Azure Active Directory, Microsoft Account und Google IDs. Weitere Informationen dazu, wie Ihre Organisation verschlüsselte Nachrichten verwenden kann, finden Sie unter [Office 365-Nachrichtenverschlüsselung.](https://docs.microsoft.com/microsoft-365/compliance/ome)

## <a name="transport-layer-security"></a>Transport Layer Security   

Wenn Sie eine sichere Kommunikation mit einem Partner sicherstellen möchten, können Sie eingehende und ausgehende Connectors verwenden, um Sicherheit und Nachrichtenintegrität zu gewährleisten. Sie können erzwungene eingehende und ausgehende TLS auf jedem Connector mithilfe eines Zertifikats konfigurieren. Die Verwendung eines verschlüsselten SMTP-Kanals kann verhindern, dass Daten über einen Man-in-the-Middle-Angriff gestohlen werden. Weitere Informationen finden Sie unter Verwendung von TLS durch [Exchange Online zum Sichern von E-Mail-Verbindungen.](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)

## <a name="domain-keys-identified-mail"></a>Identifizierte E-Mail-Adresse für Domänenschlüssel

Exchange Online Protection (EOP) und Exchange Online unterstützen die eingehende Validierung von Domain Keys Identified Mail(DKIM)-Nachrichten. DKIM ist eine Methode, anhand derer validiert wird, dass eine Nachricht von der angegebenen Domian stammt und nicht von jemand anderem gefälscht wurde. Es bindet eine E-Mail-Nachricht an die Organisation, die für das Senden verantwortlich ist, und ist Teil eines größeren Paradigmas der E-Mail-Verschlüsselung. Weitere Informationen zu den drei Teilen dieses Paradigmas finden Sie unter:

- [Einrichten von SPF zum Verhindern von Spoofing](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)

- [Verwenden von DKIM zum Überprüfen ausgehender E-Mails, die von Ihrer benutzerdefinierten Domäne gesendet werden](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)

- [Verwenden von DMARC zum Überprüfen von E-Mails](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)
