---
title: Verschlüsselung in der Microsoft-Cloud
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
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: In diesem Artikel finden Sie eine Übersicht über die verschiedenen Verschlüsselungsformen, die verwendet werden, um Kundendaten in der Microsoft-Cloud zu schützen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0d05c904fc70d02d8694b8f2d3b451fd1d51dc91
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841294"
---
# <a name="encryption-in-the-microsoft-cloud"></a>Verschlüsselung in der Microsoft-Cloud

Kundendaten innerhalb der Unternehmensclouddienste von Microsoft werden durch mehrere Technologien und Prozesse geschützt, einschließlich verschiedener Verschlüsselungsformen. (Kundendaten in diesem Dokument umfassen Exchange Online Postfachinhalt, E-Mail-Text, Kalendereinträge und den Inhalt von E-Mail-Anlagen und ggf. Skype for Business Inhalte), SharePoint Onlinewebsiteinhalt und die auf Websites gespeicherten Dateien sowie dateien, die in OneDrive for Business oder Skype for Business hochgeladen wurden.) Microsoft verwendet mehrere Verschlüsselungsmethoden, Protokolle und Verschlüsselungen in seinen Produkten und Diensten, um einen sicheren Pfad für Kundendaten bereitzustellen, um durch unsere Clouddienste zu gelangen, und um die Vertraulichkeit von Kundendaten zu schützen, die in unseren Clouddiensten gespeichert sind. Microsoft verwendet einige der sichersten Verschlüsselungsprotokolle, die verfügbar sind, um Barrieren gegen den unbefugten Zugriff auf Kundendaten bereitzustellen. Eine ordnungsgemäße Schlüsselverwaltung ist auch ein wesentliches Element bewährter Verschlüsselungsmethoden, und Microsoft arbeitet daran, sicherzustellen, dass alle von Microsoft verwalteten Verschlüsselungsschlüssel ordnungsgemäß gesichert sind.

Kundendaten, die in den Unternehmensclouddiensten von Microsoft gespeichert sind, werden mithilfe einer oder mehrerer Verschlüsselungsformen geschützt. (Die Validierung unserer Kryptorichtlinie und deren Durchsetzung wird unabhängig von mehreren Prüfern von Drittanbietern überprüft, und Berichte dieser Überprüfungen sind im [Service Trust Portal](https://aka.ms/stp)verfügbar.)

Microsoft stellt dienstseitige Technologien bereit, mit denen Ruhe- und Übertragungsdaten verschlüsselt werden. Bei ruhenden Kundendaten verwendet Microsoft Azure beispielsweise [BitLocker](/windows/device-security/bitlocker/bitlocker-overview) und [DM-Crypt,](https://en.wikipedia.org/wiki/Dm-crypt)und Microsoft 365 verwendet BitLocker, [Azure Storage Dienstverschlüsselung,](/azure/)Distributed Key [Manager](./exchange-online-secures-email-secrets.md) (DKM) und Microsoft 365 Dienstverschlüsselung. Für Kundendaten während der Übertragung verwenden Azure, Office 365, Microsoft Commercial Support, Microsoft Dynamics 365, Microsoft Power BI und Visual Studio Team Services sichere Transportprotokolle nach Branchenstandard, z. B. InternetProtokollsicherheit (Internet Protocol Security, IPsec) und Transport Layer Security (TLS), zwischen Microsoft-Rechenzentren und zwischen Benutzergeräten und Microsoft-Rechenzentren.

Zusätzlich zur grundlegenden Stufe der kryptografischen Sicherheit, die von Microsoft bereitgestellt wird, umfassen unsere Clouddienste auch Kryptografieoptionen, die Sie verwalten können. Sie können beispielsweise die Verschlüsselung für Datenverkehr zwischen ihren virtuellen Azure-Computern (VMs) und ihren Benutzern aktivieren. Mit [Azure Virtual Networks](https://azure.microsoft.com/services/virtual-network/)können Sie das IPsec-Protokoll nach Branchenstandard verwenden, um den Datenverkehr zwischen Ihrem VPN-Gateway des Unternehmens und Azure zu verschlüsseln. Sie können auch den Datenverkehr zwischen den virtuellen Computern in Ihrem virtuellen Netzwerk verschlüsseln. Darüber hinaus können Sie [mithilfe neuer Office 365-Nachrichtenverschlüsselung Funktionen](set-up-new-message-encryption-capabilities.md) verschlüsselte E-Mails an alle Personen senden.

Nach dem Public Key Infrastructure Operational Security Standard, einer Komponente der [Microsoft-Sicherheitsrichtlinie,](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5868ecc8-50b7-4f91-b43f-640e2b99e86e&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ%20and%20White%20Papers)verwendet Microsoft die kryptografischen Funktionen, die im Windows Betriebssystem enthalten sind, für Zertifikate und Authentifizierungsmechanismen. Diese Mechanismen umfassen die Verwendung kryptografischer Module, die den FIPS-Standards [(Federal Information Processing Standards)](https://csrc.nist.gov/publications/PubsFIPS.html) 140-2 der US-Regierung entsprechen. Sie können mit dem CMVP des [Kryptografiemodulvalidierungsprogramms](https://csrc.nist.gov/projects/cryptographic-module-validation-program/validated-modules/search)nach den relevanten NIST-Zertifikatnummern für Microsoft suchen.

> [HINWEIS] Um auf die Microsoft-Sicherheitsrichtlinie als Ressource zuzugreifen, müssen Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto anmelden. Wenn Sie noch kein Abonnement haben, [können Sie sich für eine kostenlose Testversion registrieren.](https://servicetrust.microsoft.com/Home/TrialSubscriptions)

FIPS 140-2 ist ein Standard, der speziell für die Überprüfung von Produktmodulen entwickelt wurde, die Kryptografie anstelle der Produkte implementieren, die sie verwenden. Kryptografische Module, die in einem Dienst implementiert sind, können zertifiziert werden, um die Anforderungen an hashstärke, Schlüsselverwaltung usw. zu erfüllen. Die kryptografischen Module und Verschlüsselungen, die zum Schutz der Vertraulichkeit, Integrität oder Verfügbarkeit von Daten in den Clouddiensten von Microsoft verwendet werden, erfüllen den FIPS 140-2-Standard.

Microsoft zertifiziert die zugrunde liegenden kryptografischen Module, die in unseren Clouddiensten verwendet werden, mit jeder neuen Version des Windows Betriebssystems:

- Azure und Azure U.S. Government
- Dynamics 365 und Dynamics 365 U.S. Government
- Office 365, Office 365 U.S. Government, Office 365 U.S. Government Defense

Die Verschlüsselung ruhenden Kundendaten wird von mehreren dienstseitigen Technologien bereitgestellt, einschließlich BitLocker, DKM, Azure Storage Dienstverschlüsselung und Dienstverschlüsselung in Exchange Online, Skype for Business, OneDrive for Business und SharePoint Online. Office 365 Dienstverschlüsselung umfasst eine Option zur Verwendung von vom Kunden verwalteten Verschlüsselungsschlüsseln, die in Azure Key Vault gespeichert sind. Diese vom Kunden verwaltete Schlüsseloption, die als [Kundenschlüssel](./customer-key-overview.md)bezeichnet wird, ist für Exchange Online, SharePoint Online, Skype for Business und OneDrive for Business verfügbar.

Bei Kundendaten während der Übertragung handeln alle Office 365 Server standardmäßig sichere Sitzungen mit TLS mit Clientcomputern aus, um Kundendaten zu schützen. Beispielsweise handelt Office 365 sichere Sitzungen mit Skype for Business, Outlook und Outlook im Web, mobilen Clients und Webbrowsern aus.

(Alle kundenorientierten Server handeln standardmäßig mit TLS 1.2 aus.)

## <a name="related-links"></a>Links zu verwandten Themen

- [Verschlüsselung in Azure](office-365-azure-encryption.md)
- [BitLocker und Distributed Key Manager (DKM) für die Verschlüsselung](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)
- [Office 365-Dienstverschlüsselung](office-365-service-encryption.md)
- [Office 365 Verschlüsselung für Skype for Business, OneDrive for Business, SharePoint Online und Exchange Online](/compliance/assurance/assurance-encryption-for-microsoft-365-services) 
- [Verschlüsselung von Daten während der Übertragung](/compliance/assurance/assurance-encryption-in-transit)
- [Vom Kunden verwaltete Verschlüsselungsfunktionen](office-365-customer-managed-encryption-features.md)
- [Verschlüsselungsrisiken und Schutzfunktionen](office-365-encryption-risks-and-protections.md)
- [Verschlüsselung in Microsoft Dynamics 365](office-365-encryption-in-microsoft-dynamics-365.md)