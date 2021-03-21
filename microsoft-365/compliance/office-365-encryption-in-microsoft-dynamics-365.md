---
title: Verschlüsselung in Microsoft Dynamics 365
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
description: Erfahren Sie, wie Microsoft Verschlüsselungstechnologie verwendet, um Kundendaten in Microsoft Dynamics 365 während des Ruhens in einer Microsoft-Datenbank und während der Übertragung zu schützen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b1c55c4ac233c61f7a583f4f1a94222133f1d7c1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926214"
---
# <a name="encryption-in-microsoft-dynamics-365"></a>Verschlüsselung in Microsoft Dynamics 365

Microsoft verwendet Verschlüsselungstechnologie, um Kundendaten in Dynamics 365 zu schützen, während sie sich in einer Microsoft-Datenbank befinden und während der Übertragung zwischen Benutzergeräten und unseren Rechenzentren. Verbindungen zwischen Kunden und Microsoft-Rechenzentren werden verschlüsselt, und alle öffentlichen Endpunkte werden mit branchenüblichem TLS gesichert. TLS richtet effektiv eine sicherheitsgef nente Browser-zu-Server-Verbindung ein, um die Vertraulichkeit und Integrität von Daten zwischen Desktops und Rechenzentren sicherzustellen. Nachdem die Datenverschlüsselung aktiviert wurde, kann sie nicht mehr deaktiviert werden. Weitere Informationen finden Sie unter [Datenverschlüsselung auf Feldebene](/previous-versions/dynamicscrm-2016/developers-guide/dn481562(v=crm.8)).

Dynamics 365 verwendet Microsoft SQL Server Standardverschlüsselung auf Zellenebene für eine Reihe von Standardentitätsattributen, die vertrauliche Informationen wie Benutzernamen und E-Mail-Kennwörter enthalten. Dieses Feature kann Organisationen dabei unterstützen, die mit FIPS 140-2 verbundenen Complianceanforderungen zu erfüllen. Die Verschlüsselung von Daten auf Feldebene ist besonders wichtig in Szenarien, in denen der [Microsoft Dynamics CRM-E-Mail-Router](/previous-versions/dynamicscrm-2016/administering-dynamics-365/hh699800(v=crm.8))verwendet wird, der Benutzernamen und Kennwörter speichern muss, um die Integration zwischen einer Dynamics 365-Instanz und einem E-Mail-Dienst zu ermöglichen. 

Alle Instanzen von Dynamics 365 verwenden Microsoft SQL Server Transparente Datenverschlüsselung [(TRANSPARENT Data Encryption,](/sql/relational-databases/security/encryption/transparent-data-encryption?view=sql-server-2017) TDE), um die Echtzeitverschlüsselung von Daten durchzuführen, wenn sie auf den Datenträger geschrieben werden (im Ruhedienst). TDE verschlüsselt SQL Server, Azure SQL Database und Azure SQL Data Warehouse-Datendateien. Standardmäßig speichert und verwaltet Microsoft die Datenbankverschlüsselungsschlüssel für Ihre Instanzen von Dynamics 365. (Die Schlüssel, die von Dynamics 365 for Financials verwendet werden, werden von der .NET Framework Data Protection API generiert.) 

Mit dem Feature "Schlüssel verwalten" im Dynamics 365 Administration Center können Administratoren die Datenbankverschlüsselungsschlüssel, die Instanzen von Dynamics 365 zugeordnet sind, selbst verwalten. (Selbstver verwaltete Datenbankverschlüsselungsschlüssel sind nur im Update vom Januar 2017 für Microsoft Dynamics 365 verfügbar und möglicherweise nicht für spätere Versionen verfügbar. Weitere Informationen finden Sie unter [Manage the encryption keys for your Dynamics 365 (online) instance](/dynamics365/customer-engagement/admin/manage-encryption-keys-instance).) Das Schlüsselverwaltungsfeature unterstützt sowohl PFX- als auch BYOK-Verschlüsselungsschlüsseldateien, z. B. dateien, die in einem HSM gespeichert sind. (Weitere Informationen zum Generieren und Übertragen eines HSM-geschützten Schlüssels über das Internet finden Sie unter Generieren und Übertragen von [HSM-geschützten](/azure/key-vault/key-vault-hsm-protected-keys)Schlüsseln für Azure Key Vault .) 

Um die Option zum Hochladen des Verschlüsselungsschlüssels zu verwenden, benötigen Sie sowohl den öffentlichen als auch den privaten Verschlüsselungsschlüssel.

Das Schlüsselverwaltungsfeature entnimmt die Komplexität der Verschlüsselungsschlüsselverwaltung, indem Azure Key Vault zum sicheren Speichern von Verschlüsselungsschlüsseln verwendet wird. Azure Key Vault schützt kryptografische Schlüssel und Geheimschlüssel, die von Cloudanwendungen und -diensten verwendet werden. Das Schlüsselverwaltungsfeature erfordert nicht, dass Sie über ein Azure Key Vault-Abonnement verfügen, und in den meisten Situationen ist kein Zugriff auf Verschlüsselungsschlüssel erforderlich, die für Dynamics 365 im Tresor verwendet werden.