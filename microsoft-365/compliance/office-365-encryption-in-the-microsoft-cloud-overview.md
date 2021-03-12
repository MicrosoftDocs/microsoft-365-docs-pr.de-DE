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
description: Lesen Sie in diesem Artikel eine Übersicht über die verschiedenen Verschlüsselungsmethoden, die zum Schutz von Kundendaten in der Microsoft Cloud verwendet werden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 20236e67432ad5bc7e837b91590387355022ccb5
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727576"
---
# <a name="encryption-in-the-microsoft-cloud"></a>Verschlüsselung in der Microsoft-Cloud

Kundendaten innerhalb der Clouddienste von Microsoft enterprise sind durch verschiedene Technologien und Prozesse geschützt, einschließlich verschiedener Verschlüsselungsmethoden. (Kundendaten in diesem Dokument umfassen Exchange Online-Postfachinhalte, E-Mail-Nachrichtentext, Kalendereinträge und den Inhalt von E-Mail-Anlagen und ggf. Skype for Business-Inhalte), SharePoint #A0 und die auf Websites gespeicherten Dateien sowie dateien, die in OneDrive for Business oder Skype for Business hochgeladen wurden.) Microsoft verwendet mehrere Verschlüsselungsmethoden, Protokolle und Chiffren in seinen Produkten und Diensten, um kundendaten einen sicheren Weg zu bieten, um durch unsere Clouddienste zu reisen, und um die Vertraulichkeit von Kundendaten zu schützen, die in unseren Clouddiensten gespeichert sind. Microsoft verwendet einige der stärksten und sichersten Verschlüsselungsprotokolle, die verfügbar sind, um Hindernisse gegen den nicht autorisierten Zugriff auf Kundendaten zu bieten. Die ordnungsgemäße Schlüsselverwaltung ist auch ein wesentliches Element bewährter Verschlüsselungsmethoden, und Microsoft arbeitet daran, sicherzustellen, dass alle von Microsoft verwalteten Verschlüsselungsschlüssel ordnungsgemäß gesichert sind.

Kundendaten, die in den Clouddiensten von Microsoft für Unternehmen gespeichert sind, werden mithilfe einer oder mehreren Verschlüsselungsformen geschützt. (Die Überprüfung unserer Kryptorichtlinie und ihrer Durchsetzung wird unabhängig von mehreren Prüfern von Drittanbietern überprüft, und Berichte über diese Prüfungen sind im [Service Trust Portal verfügbar.)](https://aka.ms/stp)

Microsoft stellt dienstseitige Technologien zur Verfügung, die Ruhe- und Transitdaten von Kunden verschlüsseln. Für ruhende Kundendaten verwendet Microsoft Azure beispielsweise [BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) und [DM-Crypt,](https://en.wikipedia.org/wiki/Dm-crypt)und Microsoft 365 verwendet BitLocker, [Azure Storage Service Encryption,](https://docs.microsoft.com/azure/) [Distributed Key Manager](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-secures-email-secrets) (DKM) und Microsoft 365-Dienstverschlüsselung. Für Kundendaten während der Übertragung verwenden Azure, Office 365, Microsoft Commercial Support, Microsoft Dynamics 365, Microsoft Power BI und Visual Studio Team Services branchenübliche sichere Transportprotokolle, z. B. Internet Protocol Security (IPsec) und Transport Layer Security (TLS), zwischen Microsoft-Rechenzentren und zwischen Benutzergeräten und Microsoft-Rechenzentren.

Neben der von Microsoft bereitgestellten Grundlegenden Stufe der kryptografischen Sicherheit umfassen unsere Clouddienste auch Kryptografieoptionen, die Sie verwalten können. Beispielsweise können Sie die Verschlüsselung für den Datenverkehr zwischen ihren virtuellen Computern (VMs) und ihren Benutzern aktivieren. Mit [virtuellen Azure-Netzwerken](https://azure.microsoft.com/services/virtual-network/)können Sie das branchenübliche IPsec-Protokoll verwenden, um den Datenverkehr zwischen Ihrem Unternehmens-VPN-Gateway und Azure zu verschlüsseln. Sie können den Datenverkehr zwischen den virtuellen Computern in Ihrem virtuellen Netzwerk auch verschlüsseln. Darüber hinaus können [Sie mit neuen Office 365-Nachrichtenverschlüsselungsfunktionen](set-up-new-message-encryption-capabilities.md) verschlüsselte E-Mails an alle Benutzer senden.

Nach dem Public Key Infrastructure Operational Security Standard, einer Komponente der [Microsoft-Sicherheitsrichtlinie,](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5868ecc8-50b7-4f91-b43f-640e2b99e86e&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ%20and%20White%20Papers)verwendet Microsoft die im Windows-Betriebssystem enthaltenen Kryptografiefunktionen für Zertifikate und Authentifizierungsmechanismen. Diese Mechanismen umfassen die Verwendung von kryptografischen Modulen, die den [Federal Information Processing Standards](https://csrc.nist.gov/publications/PubsFIPS.html) (FIPS) 140-2 der US-Regierung entsprechen. Sie können die relevanten NIST-Zertifikatnummern für Microsoft mithilfe des CmVP für das [Kryptografiemodulüberprüfungsprogramm suchen.](https://csrc.nist.gov/projects/cryptographic-module-validation-program/validated-modules/search)

> [HINWEIS] Um auf die Microsoft-Sicherheitsrichtlinie als Ressource zu zugreifen, müssen Sie sich mit Ihrem Arbeits- oder Schulkonto anmelden. Wenn Sie noch kein Abonnement haben, können Sie [sich für eine kostenlose Testversion registrieren.](https://servicetrust.microsoft.com/Home/TrialSubscriptions)

FIPS 140-2 ist ein Standard, der speziell für die Validierung von Produktmodulen entwickelt wurde, die Kryptografie implementieren und nicht die Produkte, die sie verwenden. Kryptografiemodule, die in einem Dienst implementiert werden, können zertifiziert werden, um die Anforderungen an hash strength, key management und deren Anforderungen zu erfüllen. Die kryptografischen Module und Verschlüsselungen, die zum Schutz der Vertraulichkeit, Integrität oder Verfügbarkeit von Daten in den Clouddiensten von Microsoft verwendet werden, entsprechen dem FIPS 140-2-Standard.

Microsoft zertifiziert die zugrunde liegenden kryptografischen Module, die in unseren Clouddiensten verwendet werden, mit jeder neuen Version des Windows-Betriebssystems:

- Azure und Azure U.S. Government
- Dynamics 365 und Dynamics 365 U.S. Government
- Office 365, Office 365 U.S. Government, Office 365 U.S. Government Defense

Die Verschlüsselung ruherer Kundendaten wird von mehreren dienstseitigen Technologien bereitgestellt, einschließlich BitLocker, DKM, Azure Storage Service Encryption und Dienstverschlüsselung in Exchange Online, Skype for Business, OneDrive for Business und SharePoint Online. Die Office 365-Dienstverschlüsselung umfasst eine Option zum Verwenden von vom Kunden verwalteten Verschlüsselungsschlüsseln, die in Azure Key Vault gespeichert sind. Diese vom Kunden verwaltete Schlüsseloption namens [Customer Key](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview)ist für Exchange Online, SharePoint Online, Skype for Business und OneDrive for Business verfügbar.

Für Kundendaten, die übertragen werden, verhandeln alle Office 365-Server standardmäßig sichere Sitzungen mit TLS mit Clientcomputern, um Kundendaten zu schützen. Beispielsweise werden in Office 365 sichere Sitzungen mit Skype for Business, Outlook und Outlook im Web, mobilen Clients und Webbrowsern aushandelt.

(Alle kundenorientierten Server verhandeln standardmäßig mit TLS 1.2.)

## <a name="related-links"></a>Links zu verwandten Themen

- [Verschlüsselung in Azure](office-365-azure-encryption.md)
- [BitLocker und Distributed Key Manager (DKM) für die Verschlüsselung](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)
- [Office 365-Dienstverschlüsselung](office-365-service-encryption.md)
- [Office 365-Verschlüsselung für Skype for Business, OneDrive for Business, SharePoint Online und Exchange Online](office-365-encryption-for-skype-onedrive-sharepoint-and-exchange.md)
- [Verschlüsselung von Daten während der Übertragung](office-365-encryption-for-data-in-transit.md)
- [Vom Kunden verwaltete Verschlüsselungsfunktionen](office-365-customer-managed-encryption-features.md)
- [Verschlüsselungsrisiken und Schutzfunktionen](office-365-encryption-risks-and-protections.md)
- [Verschlüsselung in Microsoft Dynamics 365](office-365-encryption-in-microsoft-dynamics-365.md)
