---
title: Office 365 Verschlüsselung in Azure
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
description: 'Zusammenfassung: eine Erläuterung der Verschlüsselung in Azure.'
ms.openlocfilehash: 9828da8b2d39a3b80784d57ed71a335857cfaea5
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41602112"
---
# <a name="office-365-encryption-in-azure"></a>Office 365 Verschlüsselung in Azure

## <a name="introduction"></a>Einführung

Technologische Schutzvorkehrungen in Azure, wie verschlüsselte Kommunikation und Betriebsprozesse, tragen dazu bei, dass Ihre Daten sicher sind. Sie haben auch die Flexibilität, zusätzliche Verschlüsselungsfunktionen zu implementieren und eigene kryptografische Schlüssel zu verwalten. Unabhängig von der Kundenkonfiguration wendet Microsoft die Verschlüsselung an, um Kundendaten in Azure zu schützen. Mit Microsoft können Sie auch die in Azure gehosteten Daten über eine Reihe fortschrittlicher Technologien steuern, um kryptografische Schlüssel zu verschlüsseln, zu steuern und zu verwalten, den Zugriff auf Daten zu steuern und zu überwachen. Darüber hinaus bietet Azure Storage einen umfassenden Satz an Sicherheitsfunktionen, mit denen Entwickler sichere Anwendungen erstellen können.

Azure bietet viele Mechanismen zum Schutz von Daten, die von einem Standort an einen anderen verschoben werden. Microsoft verwendet TLS, um Daten zu schützen, wenn es zwischen den Cloud-Diensten und Kunden reist. In den Rechenzentren von Microsoft wird eine TLS-Verbindung mit Clientsystemen ausgehandelt, die eine Verbindung mit Azure Services herstellen. Perfect Forward Verschwiegenheit (PFS) schützt die Verbindungen zwischen Clientsystemen von Kunden und den Cloud-Diensten von Microsoft mit eindeutigen Schlüsseln. Verbindungen verwenden auch RSA-basierte 2.048-Bit-Verschlüsselungsschlüssel Längen. Diese Kombination erschwert das Abfangen und Zugreifen auf Daten, die während der Übertragung durch den Benutzer durchführt werden.

Daten können während der Übertragung zwischen einer Anwendung und Azure mithilfe der [clientseitigen Verschlüsselung](https://docs.microsoft.com/azure/storage/storage-client-side-encryption), HTTPS oder SMB 3,0 gesichert werden. Sie können die Verschlüsselung für den Datenverkehr zwischen ihren eigenen virtuellen Computern (VMS) und ihren Benutzern aktivieren. Bei [virtuellen Azure-Netzwerken](https://azure.microsoft.com/services/virtual-network/)können Sie das standardmäßige IPSec-Protokoll verwenden, um den Datenverkehr zwischen dem VPN-Gateway des Unternehmens und Azure sowie zwischen den VMS im virtuellen Netzwerk zu verschlüsseln.

Für Daten im Ruhezustand bietet Azure zahlreiche Verschlüsselungsoptionen wie Unterstützung für AES-256, die Ihnen die Flexibilität bieten, das Datenspeicher Szenario auszuwählen, das Ihren Anforderungen am besten entspricht. Daten können automatisch verschlüsselt werden, wenn Sie mithilfe der [Speicherdienst Verschlüsselung](https://docs.microsoft.com/azure/storage/storage-service-encryption)in Azure Storage geschrieben werden, und Betriebssystem-und Daten Datenträger, die von VMS verwendet werden, können verschlüsselt werden. Weitere Informationen finden Sie unter [Security Recommendations for Windows Virtual Machines in Azure](https://docs.microsoft.com/azure/security/azure-security-disk-encryption). Darüber hinaus kann der Delegierte Zugriff auf Datenobjekte im Azure-Speicher über [freigegebene Zugriffs Signaturen](https://docs.microsoft.com/azure/storage/storage-dotnet-shared-access-signature-part-1)erteilt werden. Azure bietet auch eine Verschlüsselung für Daten im Ruhezustand mithilfe der [transparenten Datenverschlüsselung für Azure SQL-Datenbank und Data Warehouse](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption-azure-sql).

Weitere Informationen zur Verschlüsselung in Azure finden Sie unter [Azure Encryption Overview](https://docs.microsoft.com/azure/security/security-azure-encryption-overview) und [Azure Data Encryption-at-Rest](https://docs.microsoft.com/azure/security/azure-security-encryption-atrest).

## <a name="azure-disk-encryption"></a>Azure-Datenträgerverschlüsselung

Azure Disk Encryption ermöglicht das Verschlüsseln Ihrer Windows-und Linux-Infrastruktur als Dienst (IaaS) VM-Datenträger. Azure Disk Encryption nutzt das BitLocker-Feature von Windows und das dm-crypt-Feature von Linux, um die Verschlüsselung auf Volumen Ebene für das Betriebssystem und die Datenträger bereitzustellen. Außerdem wird sichergestellt, dass alle Daten auf den VM-Datenträgern im Rest in Ihrem Azure-Speicher verschlüsselt werden. Azure-Datenträgerverschlüsselung ist in Azure Key Vault integriert, damit Sie die Verwendung der Verschlüsselungsschlüssel und-Geheimnisse steuern, verwalten und überwachen können.

Weitere Informationen finden Sie unter [Security Recommendations for Windows Virtual Machines in Azure](https://docs.microsoft.com/azure/security/azure-security-disk-encryption).

## <a name="azure-storage-service-encryption"></a>Azure Storage Service-Verschlüsselung

Bei der [Azure Storage Service-Verschlüsselung](https://docs.microsoft.com/azure/storage/storage-service-encryption)verschlüsselt Azure Storage automatisch Daten, bevor Sie gespeichert werden, und entschlüsselt Daten vor dem Abruf. Die Verschlüsselung, Entschlüsselung und die wichtigsten Verwaltungsprozesse sind für Benutzer vollkommen transparent. Azure Storage Service Encryption kann für Azure- [BLOB-Speicher](https://azure.microsoft.com/services/storage/blobs/) und [Azure-Dateien](https://azure.microsoft.com/services/storage/files/)verwendet werden. Sie können auch die von Microsoft verwalteten Verschlüsselungsschlüssel mit der Azure Storage Service-Verschlüsselung verwenden, oder Sie können eigene Verschlüsselungsschlüssel verwenden. (Informationen zur Verwendung eigener Schlüssel finden Sie unter [Speicherdienst Verschlüsselung mithilfe von Kunden verwalteten Schlüsseln in Azure Key Vault](https://docs.microsoft.com/azure/storage/common/storage-service-encryption-customer-managed-keys). Informationen zur Verwendung von von Microsoft verwalteten Schlüsseln finden Sie unter [Speicherdienst Verschlüsselung für Daten im Ruhezustand](https://docs.microsoft.com/azure/storage/storage-service-encryption).) Darüber hinaus können Sie die Verwendung der Verschlüsselung automatisieren. Beispielsweise können Sie die Speicherdienst Verschlüsselung für ein Speicherkonto programmgesteuert mithilfe der [Rest-API des Azure-Speicherressourcen Anbieters](https://msdn.microsoft.com/library/azure/mt163683.aspx), des [Speicherressourcen Anbieters Clientbibliothek für .net](https://msdn.microsoft.com/library/azure/mt131037.aspx), [Azure PowerShell](https://docs.microsoft.com/powershell/azureps-cmdlets-docs)oder der [Azure CLI](https://docs.microsoft.com/azure/storage/storage-azure-cli)aktivieren oder deaktivieren.

Einige Office 365 Dienste verwenden Azure zum Speichern von Daten. Beispielsweise SharePoint Online und OneDrive für Unternehmen Daten im Azure-BLOB-Speicher speichern, und Microsoft Teams speichert Daten für den Chatdienst in Tabellen, BLOBs und Warteschlangen. Darüber hinaus speichert das Feature für die Konformitätsbewertung im Microsoft 365 Compliance Center Kunden eingegebene Daten, die in verschlüsselter Form in [Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/database-encryption-at-rest)gespeichert sind, einer Plattform als Service (PaaS), global verteilte, mehrstufige Datenbank. Die Azure Storage Service-Verschlüsselung verschlüsselt Daten, die im Azure-BLOB-Speicher und in Tabellen gespeichert sind, und die Azure-Datenträgerverschlüsselung verschlüsselt Daten in Warteschlangen sowie Windows-und IaaS-Laufwerke virtueller Computer, um die Volumen Verschlüsselung für das Betriebssystem und den Datenträger bereitzustellen. Die Lösung stellt sicher, dass alle Daten auf den virtuellen Computer Datenträgern in der Ruhephase in Ihrem Azure-Speicher verschlüsselt sind. Die [Verschlüsselung in Rest in Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/database-encryption-at-rest) wird mithilfe verschiedener Sicherheitstechnologien implementiert, einschließlich sicherer Schlüsselspeicher Systeme, verschlüsselter Netzwerke und kryptografischer APIs.

## <a name="azure-key-vault"></a>Azure Key Vault

Die sichere Schlüsselverwaltung ist nicht nur der Kern für bewährte Methoden für die Verschlüsselung; Dies ist auch für den Schutz von Daten in der Cloud unerlässlich. [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-whatis) ermöglicht das Verschlüsseln von Schlüsseln und kleinen Geheimnissen wie Kennwörter, die Schlüssel verwenden, die in Hardware Security modules (HSMs) gespeichert sind. Azure Key Vault ist die empfohlene Lösung von Microsoft für die Verwaltung und Steuerung des Zugriffs auf Verschlüsselungsschlüssel, die von Cloud-Diensten verwendet werden. Berechtigungen für Zugriffstasten können Diensten oder Benutzern mit Azure Active Directory-Konten zugewiesen werden. Azure Key Vault erleichtert Organisationen die Notwendigkeit, HSMs und wichtige Verwaltungssoftware zu konfigurieren, zu patchen und zu warten. Mit Azure Key Vault sieht Microsoft nie Ihre Schlüssel und Anwendungen haben keinen direkten Zugriff auf diese. Sie verwalten die Steuerung. Sie können auch Keys in HSMs importieren oder generieren. Organisationen mit einem Abonnement, das Azure Information Protection umfasst, können Ihren Azure Information Protection-Mandanten so konfigurieren, dass er einen vom Kunden verwalteten Schlüssel verwendet, um einen [eigenen Schlüssel](https://docs.microsoft.com/information-protection/plan-design/byok-price-restrictions) zu verwenden (BYOK)) und [seine Verwendung protokollieren](https://docs.microsoft.com/information-protection/deploy-use/log-analyze-usage)kann.
