---
title: Verschlüsselung in Azure
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
description: Informationen zur in Azure verfügbaren Verschlüsselung, z. B. Azure Disk Encryption
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ee4eb2bec814d7e06d418518bb9be272f1bd5aaa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926253"
---
# <a name="encryption-in-azure"></a>Verschlüsselung in Azure

Technische Sicherheitsvorkehrungen in Azure, z. B. verschlüsselte Kommunikation und betriebsbereite Prozesse, helfen, Ihre Daten zu schützen. Sie haben auch die Flexibilität, zusätzliche Verschlüsselungsfunktionen zu implementieren und Eigene Kryptografieschlüssel zu verwalten. Unabhängig von der Kundenkonfiguration wendet Microsoft eine Verschlüsselung an, um Kundendaten in Azure zu schützen. Microsoft ermöglicht es Ihnen außerdem, Ihre in Azure gehosteten Daten über eine Reihe von erweiterten Technologien zum Verschlüsseln, Steuern und Verwalten von kryptografischen Schlüsseln sowie zum Steuern und Überwachen des Zugriffs auf Daten zu steuern. Darüber hinaus bietet Azure Storage eine umfassende Reihe von Sicherheitsfunktionen, mit denen Entwickler gemeinsam sichere Anwendungen erstellen können.

Azure bietet viele Mechanismen zum Schützen von Daten, wenn es von einem Speicherort an einen anderen wechselt. Microsoft verwendet TLS, um Daten zu schützen, wenn es zwischen den Clouddiensten und Kunden unterwegs ist. Die Rechenzentren von Microsoft verhandeln eine TLS-Verbindung mit Clientsystemen, die eine Verbindung mit Azure-Diensten herstellen. Perfect Forward Secrecy (PFS) schützt Verbindungen zwischen kundenbasierten Clientsystemen und den Clouddiensten von Microsoft durch eindeutige Schlüssel. Verbindungen verwenden auch RSA-basierte 2.048-Bit-Verschlüsselungsschlüssellängen. Diese Kombination erschwert es jemandem, Daten abzufangen und auf diese zu zugreifen, die sich im Transit befindet.

Daten können bei der Übertragung zwischen einer Anwendung und Azure mithilfe [der clientseitigen](/azure/storage/storage-client-side-encryption)Verschlüsselung, HTTPS oder SMB 3.0 gesichert werden. Sie können die Verschlüsselung für den Datenverkehr zwischen Ihren eigenen virtuellen Computern (VMs) und Ihren Benutzern aktivieren. Mit [virtuellen Azure-Netzwerken](https://azure.microsoft.com/services/virtual-network/)können Sie das branchenübliche IPsec-Protokoll verwenden, um den Datenverkehr zwischen Ihrem Unternehmens-VPN-Gateway und Azure sowie zwischen den virtuellen Computern in Ihrem virtuellen Netzwerk zu verschlüsseln.

Für ruhende Daten bietet Azure viele Verschlüsselungsoptionen, z. B. unterstützung für AES-256, was Ihnen die Flexibilität gibt, das Datenspeicherszenario zu wählen, das Ihren Anforderungen am besten entspricht. Daten können automatisch verschlüsselt werden, wenn sie mithilfe der [Speicherdienstverschlüsselung](/azure/storage/storage-service-encryption)in Azure Storage geschrieben werden, und von VMs verwendete Betriebssysteme und Datenträger können verschlüsselt werden. Weitere Informationen finden Sie unter [Sicherheitsempfehlungen für virtuelle Windows-Computer in Azure](/azure/security/azure-security-disk-encryption). Darüber hinaus kann delegierter Zugriff auf Datenobjekte in Azure Storage mithilfe von Signaturen für [gemeinsamen Zugriff gewährt werden.](/azure/storage/storage-dotnet-shared-access-signature-part-1) Azure bietet auch Verschlüsselung für ruhende Daten mithilfe [der transparenten Datenverschlüsselung für Azure SQL Database and Data Warehouse](/sql/relational-databases/security/encryption/transparent-data-encryption-azure-sql).

Weitere Informationen zur Verschlüsselung in Azure finden Sie unter [Azure encryption overview](/azure/security/security-azure-encryption-overview) und Azure Data [Encryption-at-Rest](/azure/security/azure-security-encryption-atrest).

## <a name="azure-disk-encryption"></a>Azure Disk Encryption

Mit der Azure Disk Encryption können Sie Ihre Windows- und Linux Infrastructure as a Service (IaaS)-VM-Datenträger verschlüsseln. Azure Disk Encryption nutzt das BitLocker-Feature von Windows und das DM-Crypt-Feature von Linux, um verschlüsselung auf Volumeebene für das Betriebssystem und die Datenträger zu bieten. Außerdem wird sichergestellt, dass alle Daten auf den VM-Datenträgern im Ruhetag in Ihrem Azure-Speicher verschlüsselt werden. Azure Disk Encryption ist in Azure Key Vault integriert, damit Sie die Verwendung der Verschlüsselungsschlüssel und Geheimschlüssel steuern, verwalten und überwachen können.

Weitere Informationen finden Sie unter [Sicherheitsempfehlungen für virtuelle Windows-Computer in Azure](/azure/virtual-machines/windows/security-recommendations).

## <a name="azure-storage-service-encryption"></a>Azure Storage Service Encryption

Mit [der Azure Storage Service Encryption](/azure/storage/storage-service-encryption)verschlüsselt Azure Storage Daten automatisch, bevor sie gespeichert werden, und entschlüsselt Daten vor dem Abruf. Die Verschlüsselungs-, Entschlüsselungs- und Schlüsselverwaltungsprozesse sind für die Benutzer vollkommen transparent. Azure Storage Service Encryption kann für [Azure Blob Storage und](https://azure.microsoft.com/services/storage/blobs/) Azure Files verwendet [werden.](https://azure.microsoft.com/services/storage/files/) Sie können auch von Microsoft verwaltete Verschlüsselungsschlüssel mit Azure Storage Service Encryption oder eigene Verschlüsselungsschlüssel verwenden. (Informationen zur Verwendung Eigener Schlüssel finden Sie unter [Storage Service Encryption using customer managed keys in Azure Key Vault](/azure/storage/common/storage-service-encryption-customer-managed-keys). Weitere Informationen zur Verwendung von von Microsoft verwalteten Schlüsseln finden Sie unter [Storage Service Encryption for Data at Rest](/azure/storage/storage-service-encryption).) Darüber hinaus können Sie die Verwendung der Verschlüsselung automatisieren. Sie können z. B. die Speicherdienstverschlüsselung für ein Speicherkonto programmgesteuert mithilfe der [REST-API](/rest/api/storagerp/)des Azure Storage Resource Provider, der Clientbibliothek des Speicherressourcenanbieters für [.NET,](/dotnet/api/overview/azure/storage) [Azure PowerShell](/powershell/azureps-cmdlets-docs)oder der Azure CLI aktivieren oder [deaktivieren.](/azure/storage/storage-azure-cli)

Einige Microsoft 365-Dienste verwenden Azure zum Speichern von Daten. Beispielsweise speichern SharePoint Online und OneDrive for Business Daten in Azure Blob Storage, und Microsoft Teams speichert Daten für seinen Chatdienst in Tabellen, Blobs und Warteschlangen. Darüber hinaus speichert das Compliance -Manager-Feature im Microsoft 365 Compliance Center vom Kunden eingegebene Daten, die in verschlüsselter Form in [Azure Cosmos DB](/azure/cosmos-db/database-encryption-at-rest), einer Plattform als Dienst (Platform as a Service, PaaS), einer global verteilten Mehrmodelldatenbank, gespeichert werden. Azure Storage Service Encryption verschlüsselt Daten, die im Azure Blob Storage und in Tabellen gespeichert sind, und Azure Disk Encryption verschlüsselt Daten in Warteschlangen sowie Datenträger virtueller Windows- und IaaS-Computer, um die Volumeverschlüsselung für das Betriebssystem und den Datenträger zu ermöglichen. Die Lösung stellt sicher, dass alle Daten auf den Datenträgern des virtuellen Computers im ruhen in Ihrem Azure-Speicher verschlüsselt werden. [Die ruhende Verschlüsselung in Azure Cosmos DB](/azure/cosmos-db/database-encryption-at-rest) wird mithilfe mehrerer Sicherheitstechnologien implementiert, einschließlich sicherer Schlüsselspeichersysteme, verschlüsselter Netzwerke und kryptografischer APIs.

## <a name="azure-key-vault"></a>Azure Key Vault

Die Sichere Schlüsselverwaltung ist nicht nur der Kern der bewährten Verschlüsselungsmethoden, sondern auch die sicherheitliche Schlüsselverwaltung. Sie ist auch für den Schutz von Daten in der Cloud unerlässlich. [Azure Key Vault](/azure/key-vault/key-vault-whatis) ermöglicht ihnen das Verschlüsseln von Schlüsseln und kleinen Geheimschlüsseln wie Kennwörtern, die Schlüssel verwenden, die in Hardwaresicherheitsmodulen (HSMs) gespeichert sind. Azure Key Vault ist die von Microsoft empfohlene Lösung zum Verwalten und Steuern des Zugriffs auf Verschlüsselungsschlüssel, die von Clouddiensten verwendet werden. Berechtigungen für den Zugriff auf Schlüssel können Diensten oder Benutzern mit Azure Active Directory-Konten zugewiesen werden. Azure Key Vault entlastet Organisationen von der Notwendigkeit, HSMs und Wichtige Verwaltungssoftware zu konfigurieren, zu patchen und zu warten. Mit Azure Key Vault sieht Microsoft niemals, dass Ihre Schlüssel und Anwendungen keinen direkten Zugriff darauf haben. Sie behalten die Kontrolle. Sie können auch Schlüssel in HSMs importieren oder generieren. Organisationen mit einem Abonnement, das Azure Information Protection umfasst, können ihren Azure Information Protection-Mandanten so konfigurieren, dass er einen vom Kunden verwalteten Schlüssel [Bring Your Own Key](/information-protection/plan-design/byok-price-restrictions) (BYOK) verwendet und dessen Verwendung [protokolliert.](/information-protection/deploy-use/log-analyze-usage)