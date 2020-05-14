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
description: Lesen Sie in diesem Artikel eine Übersicht über die verschiedenen Verschlüsselungs Formen, die verwendet werden, um Kundendaten in der Microsoft-Cloud zu schützen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e48cc4fc54f0bc4553bab655611900523e11bd4d
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214273"
---
# <a name="encryption-in-the-microsoft-cloud"></a>Verschlüsselung in der Microsoft-Cloud

Kundendaten innerhalb von Microsoft Enterprise Cloud Services sind durch eine Vielzahl von Technologien und Prozessen geschützt, einschließlich verschiedener Formen der Verschlüsselung. (Kundendaten in diesem Dokument umfassen Exchange Online Postfachinhalt, e-Mail-Text, Kalendereinträge und den Inhalt von e-Mail-Anlagen sowie gegebenenfalls Skype for Business Inhalt), SharePoint Online Websiteinhalte und die in Websites gespeicherten Dateien sowie Dateien, die in OneDrive für Unternehmen oder Skype for Business hochgeladen werden.) Microsoft verwendet mehrere Verschlüsselungsmethoden, Protokolle und Chiffren für seine Produkte und Dienste, um einen sicheren Pfad für Kundendaten bereitzustellen, um durch unsere Cloud-Dienste zu reisen, und um die Vertraulichkeit von Kundendaten zu schützen, die in unseren Cloud-Diensten gespeichert sind. Microsoft verwendet einige der stärksten, sichersten Verschlüsselungsprotokolle, die zur Verfügung stehen, um Barrieren gegen nicht autorisierten Zugriff auf Kundendaten bereitzustellen. Die ordnungsgemäße Schlüsselverwaltung ist auch ein wesentliches Element der bewährten Verschlüsselungsmethoden, und Microsoft arbeitet, um sicherzustellen, dass alle von Microsoft verwalteten Verschlüsselungsschlüssel ordnungsgemäß gesichert sind.

Unabhängig von der Kundenkonfiguration werden Kundendaten, die in den Enterprise Cloud-Diensten von Microsoft gespeichert sind, mit einer oder mehreren Verschlüsselungs Formen geschützt. (Die Validierung unserer Crypto-Richtlinie und deren Erzwingung wird unabhängig von mehreren Auditoren von Drittanbietern überprüft, und Berichte dieser Audits stehen im [Dienst Vertrauensstellungs Portal](https://aka.ms/stp)zur Verfügung.)

Microsoft stellt dienstseitige Technologien bereit, mit denen Kundendaten im Ruhezustand und bei der Übertragung verschlüsselt werden. Für Kundendaten im Ruhezustand verwendet Microsoft Azure beispielsweise [BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) und [dm-crypt](https://en.wikipedia.org/wiki/Dm-crypt), und Microsoft 365 verwendet BitLocker, [Azure Storage Service Encryption](https://docs.microsoft.com/azure/), [Distributed Key Manager](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-secures-email-secrets) (DKM) und Microsoft 365 Service Encryption. Für Kundendaten in Transit, Azure, Office 365, Microsoft Commercial Support, Microsoft Dynamics 365, Microsoft Power BI und Visual Studio Team Services werden branchenübliche sichere Transportprotokolle wie Internet Protocol Security (IPSec) und Transport Layer Security (TLS) zwischen Microsoft-Rechenzentren und zwischen Benutzergeräten und Microsoft-Rechenzentren verwendet.

Zusätzlich zur von Microsoft bereitgestellten Basisstufe der kryptografischen Sicherheit umfassen unsere Cloud-Dienste auch zusätzliche Kryptografiefunktionen, die Sie verwalten können. Sie können beispielsweise die Verschlüsselung für den Datenverkehr zwischen Ihren virtuellen Azure-Computern (VMS) und ihren Benutzern aktivieren. Bei [virtuellen Azure-Netzwerken](https://azure.microsoft.com/services/virtual-network/)können Sie das standardmäßige IPSec-Protokoll verwenden, um den Datenverkehr zwischen dem VPN-Gateway des Unternehmens und Azure sowie zwischen den VMS im virtuellen Netzwerk zu verschlüsseln. Darüber hinaus können Sie mit der [neuen Office 365 Nachrichten Verschlüsselungsfunktionen](set-up-new-message-encryption-capabilities.md) verschlüsselte e-Mails an alle Personen senden.

In Übereinstimmung mit dem Betriebs Sicherheits Standard der Public Key-Infrastruktur, der eine Komponente der [Microsoft-Sicherheitsrichtlinie](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5868ecc8-50b7-4f91-b43f-640e2b99e86e&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ%20and%20White%20Papers)ist, nutzt Microsoft die kryptografischen Funktionen des Windows-Betriebssystems für Zertifikate und Authentifizierungsmechanismen, einschließlich der Verwendung von kryptografischen Modulen, die dem FIPS ( [Federal Information Processing Standards](https://csrc.nist.gov/publications/PubsFIPS.html) ) 140-2-Standard der US-Regierung entsprechen. (Relevante NIST-Zertifikat Nummern für Microsoft finden Sie unterhttps://csrc.nist.gov/groups/STM/cmvp/documents/140-1/1401vend.htm.)

> Hinweis Um auf die Microsoft-Sicherheitsrichtlinie als Ressource zuzugreifen, müssen Sie sich mit Ihrem Arbeits-oder Schulkonto anmelden. Wenn Sie noch kein Abonnement haben, [können Sie sich für eine ﻿kostenlose Testversion registrieren](https://servicetrust.microsoft.com/Home/TrialSubscriptions).

FIPS 140-2 ist ein Standard, der speziell für das Validieren von Produktmodulen entwickelt wurde, die Kryptografie implementieren, statt die Produkte, die Sie verwenden. Kryptografische Module, die in einem Dienst implementiert werden, können zertifiziert werden, indem die Anforderungen für Hash Stärke, Schlüsselverwaltung und ähnliches erfüllt werden. Jedes Mal, wenn kryptografische Funktionen zum Schutz der Vertraulichkeit, Integrität oder Verfügbarkeit von Daten in den Cloud-Diensten von Microsoft eingesetzt werden, entsprechen die verwendeten Module und Chiffren dem FIPS 140-2-Standard.

Microsoft bescheinigt die zugrunde liegenden kryptografischen Module, die in unseren Cloud-Diensten verwendet werden, mit jeder neuen Version des Windows-Betriebssystems:

- Azure und Azure U.S. Government
- Dynamics 365 und Dynamics 365 U.S. Government
- Office 365, Office 365 U.S. Government, Office 365 U.S. Government Defense

Die Verschlüsselung von Kundendaten im Ruhezustand wird von mehreren dienstseitigen Technologien bereitgestellt, einschließlich BitLocker, DKM, Azure Storage Service Encryption und Service Encryption in Exchange Online, Skype for Business, OneDrive für Unternehmen und SharePoint Online. Office 365 Dienst Verschlüsselung enthält eine Option zur Verwendung von Kunden verwalteten Verschlüsselungsschlüsseln, die in Azure Key Vault gespeichert sind. Diese vom Kunden verwaltete Schlüssel Option, die als " [Kundenschlüssel](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview)" bezeichnet wird, ist für Exchange Online, SharePoint Online, Skype for Business und OneDrive für Unternehmen verfügbar.

Für Kundendaten während der Übertragung verhandeln alle Office 365 Server sichere Sitzungen mit TLS standardmäßig mit Clientcomputern, um Kundendaten zu sichern.  Dies gilt für Protokolle auf allen Geräten, die von Clients verwendet werden, beispielsweise Skype for Business, Outlook und Outlook im Internet, Mobile Clients und Webbrowser.

(Alle kundenorientierten Server verhandeln standardmäßig mit TLS 1,2, unterstützen jedoch auch die Aushandlung auf einem niedrigeren Standard, falls erforderlich.)

## <a name="related-links"></a>Links zu verwandten Themen

- [Verschlüsselung in Azure](office-365-azure-encryption.md)
- [BitLocker und Distributed Key Manager (DKM) für die Verschlüsselung](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)
- [Office 365-Dienstverschlüsselung](office-365-service-encryption.md)
- [Office 365 Verschlüsselung für Skype for Business, OneDrive für Unternehmen, SharePoint Online und Exchange Online](office-365-encryption-for-skype-onedrive-sharepoint-and-exchange.md)
- [Verschlüsselung von Daten während der Übertragung](office-365-encryption-for-data-in-transit.md)
- [Vom Kunden verwaltete Verschlüsselungsfunktionen](office-365-customer-managed-encryption-features.md)
- [Verschlüsselungsrisiken und Schutzfunktionen](office-365-encryption-risks-and-protections.md)
- [Verschlüsselung in Microsoft Dynamics 365](office-365-encryption-in-microsoft-dynamics-365.md)
