---
title: Office 365 Verschlüsselung in Microsoft Dynamics 365
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
description: 'Zusammenfassung: Grundlegendes zur Verschlüsselung in Microsoft Dynamics 365.'
ms.openlocfilehash: 58afc2d35ece4b5bfd7594aad483606e6f867823
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "38690442"
---
# <a name="office-365-encryption-in-microsoft-dynamics-365"></a>Office 365 Verschlüsselung in Microsoft Dynamics 365

Microsoft verwendet Verschlüsselungstechnologien zum Schutz von Kundendaten in Dynamics 365, während Sie in einer Microsoft-Datenbank und während der Übertragung zwischen Benutzergeräten und unseren Rechenzentren in Ruhe bleiben. Zwischen Kunden und Microsoft-Rechenzentren hergestellte Verbindungen werden verschlüsselt, und alle öffentlichen Endpunkte werden mithilfe von TLS (Industry-Standard) gesichert. TLS richtet eine effektivere Browser-zu-Server-Verbindung für die Sicherheit ein, um die Vertraulichkeit und Integrität von Daten zwischen Desktops und Rechenzentren zu verbessern. Nachdem die Datenverschlüsselung aktiviert wurde, kann Sie nicht deaktiviert werden. Weitere Informationen finden Sie unter [Datenverschlüsselung auf Feldebene](https://msdn.microsoft.com/library/dn481562.aspx).

Dynamics 365 verwendet die standardmäßige Microsoft SQL Server Verschlüsselung auf Zellenebene für eine Reihe von Standard entitätsattributen, die vertrauliche Informationen enthalten, beispielsweise Benutzernamen und e-Mail-Kennwörter. Dieses Feature kann Organisationen dabei helfen, die mit FIPS 140-2 verbundenen Compliance-Anforderungen zu erfüllen. Die Datenverschlüsselung auf Feldebene ist besonders wichtig in Szenarien, in denen der [Microsoft Dynamics CRM-e-Mail-Router](https://technet.microsoft.com/library/hh699800.aspx)eingesetzt wird, der Benutzernamen und Kennwörter speichern muss, um die Integration zwischen einer Dynamics 365-Instanz und einem e-Mail-Dienst zu ermöglichen. 

Alle Instanzen von Dynamics 365 verwenden [Microsoft SQL Server transparente Datenverschlüsselung](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption?view=sql-server-2017) (DSA), um Daten in Echtzeit zu verschlüsseln, wenn Sie auf den Datenträger geschrieben werden (in Ruhe). DSA verschlüsselt SQL Server, Azure SQL-Datenbank und Azure SQL Data Warehouse-Datendateien. Standardmäßig speichert und verwaltet Microsoft die Datenbankverschlüsselungsschlüssel für Ihre Instanzen von Dynamics 365. (Die von Dynamics 365 für Financials verwendeten Tasten werden von der .NET Framework Data Protection-API generiert.) 

Das Feature "Schlüssel verwalten" im Dynamics 365-Verwaltungskonsole bietet Administratoren die Möglichkeit, die Datenbankverschlüsselungsschlüssel, die den Instanzen von Dynamics 365 zugeordnet sind, selbst zu verwalten. (Selbstverwaltete Datenbankverschlüsselungsschlüssel sind nur im Januar 2017-Update für Microsoft Dynamics 365 verfügbar und werden möglicherweise nicht für spätere Versionen zur Verfügung gestellt. Weitere Informationen finden Sie unter [Verwalten der Verschlüsselungsschlüssel für Ihre Dynamics 365 (Online)-Instanz](https://docs.microsoft.com/dynamics365/customer-engagement/admin/manage-encryption-keys-instance).) Das Schlüssel Verwaltungsfeature unterstützt sowohl PFX-als auch BYOK-Verschlüsselungsschlüssel Dateien, beispielsweise die in einem HSM gespeicherten. (Weitere Informationen zum Generieren und übertragen eines HSM-geschützten Schlüssels über das Internet finden Sie unter [Erstellen und übertragen von HSM-geschützten Schlüsseln für Azure Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-hsm-protected-keys).) 

Um die Option "Verschlüsselungsschlüssel hochladen" verwenden zu können, benötigen Sie sowohl den öffentlichen als auch den privaten Verschlüsselungsschlüssel.

Das Haupt Verwaltungsfeature nimmt die Komplexität aus der Verschlüsselungsschlüsselverwaltung, indem es Azure Key Vault zum sicheren Speichern von Verschlüsselungsschlüsseln verwendet. Azure Key Vault hilft beim Schutz von kryptografischen Schlüsseln und Geheimnissen, die von Cloud-Anwendungen und-Diensten verwendet werden. Das Schlüssel Verwaltungsfeature erfordert nicht, dass Sie über ein Azure Key Vault-Abonnement verfügen, und in den meisten Fällen ist es nicht erforderlich, auf die Verschlüsselungsschlüssel zuzugreifen, die für Dynamics 365 im Tresor verwendet werden.
