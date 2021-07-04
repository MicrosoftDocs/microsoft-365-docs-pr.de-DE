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
description: Erfahren Sie, wie Microsoft Verschlüsselungstechnologie verwendet, um Kundendaten in Microsoft Dynamics 365 zu schützen, während sie sich in einer Microsoft-Datenbank und während der Übertragung befinden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0e2691a2f02ecee5b346fcda3335ca7e5d4becc2
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288287"
---
# <a name="encryption-in-microsoft-dynamics-365"></a>Verschlüsselung in Microsoft Dynamics 365

Microsoft verwendet Verschlüsselungstechnologie, um Kundendaten in Dynamics 365 zu schützen, während sie sich in einer Microsoft-Datenbank befinden und sich während der Übertragung zwischen Benutzergeräten und unseren Rechenzentren befinden. Verbindungen, die zwischen Kunden und Microsoft-Rechenzentren hergestellt werden, werden verschlüsselt, und alle öffentlichen Endpunkte werden mithilfe von TLS nach Branchenstandard gesichert. TLS stellt effektiv eine sicherheitsverstärkte Browser-zu-Server-Verbindung her, um die Vertraulichkeit und Integrität von Daten zwischen Desktops und Rechenzentren sicherzustellen. Nachdem die Datenverschlüsselung aktiviert wurde, kann sie nicht deaktiviert werden. Weitere Informationen finden Sie unter [Datenverschlüsselung auf Feldebene.](/previous-versions/dynamicscrm-2016/developers-guide/dn481562(v=crm.8))

Dynamics 365 verwendet standard Microsoft SQL Server Verschlüsselung auf Zellebene für eine Reihe von Standardentitätsattributen, die vertrauliche Informationen enthalten, z. B. Benutzernamen und E-Mail-Kennwörter. Dieses Feature kann Organisationen dabei helfen, die Complianceanforderungen im Zusammenhang mit FIPS 140-2 zu erfüllen. Die Datenverschlüsselung auf Feldebene ist besonders wichtig in Szenarien, die den [Microsoft Dynamics CRM E-Mail-Router](/previous-versions/dynamicscrm-2016/administering-dynamics-365/hh699800(v=crm.8))nutzen, der Benutzernamen und Kennwörter speichern muss, um die Integration zwischen einer Dynamics 365-Instanz und einem E-Mail-Dienst zu ermöglichen.

Alle Instanzen von Dynamics 365 verwenden [Microsoft SQL Server Transparent Data Encryption](/sql/relational-databases/security/encryption/transparent-data-encryption) (TDE), um Daten beim Schreiben auf den Datenträger (im Ruhezustand) in Echtzeit zu verschlüsseln. TDE verschlüsselt SQL Server-, Azure SQL-Datenbank- und Azure SQL Data Warehouse-Datendateien. Standardmäßig speichert und verwaltet Microsoft die Datenbankverschlüsselungsschlüssel für Ihre Instanzen von Dynamics 365. (Die schlüssel, die von Dynamics 365 for Financials verwendet werden, werden von der .NET Framework Data Protection API generiert.)

Das Feature zum Verwalten von Schlüsseln im Dynamics 365 Administration Center bietet Administratoren die Möglichkeit, die Datenbankverschlüsselungsschlüssel, die Instanzen von Dynamics 365 zugeordnet sind, selbst zu verwalten. (Selbstverwaltete Datenbankverschlüsselungsschlüssel sind nur im Januar 2017-Update für Microsoft Dynamics 365 verfügbar und werden möglicherweise nicht für spätere Versionen zur Verfügung gestellt. Weitere Informationen finden Sie unter [Verwalten der Verschlüsselungsschlüssel für Ihre Dynamics 365 (Online)-Instanz.)](/dynamics365/customer-engagement/admin/manage-encryption-keys-instance) Das Schlüsselverwaltungsfeature unterstützt sowohl PFX- als auch BYOK-Verschlüsselungsschlüsseldateien, z. B. in einem HSM gespeicherte Dateien. (Weitere Informationen zum Generieren und Übertragen eines HSM-geschützten Schlüssels über das Internet finden Sie unter Generieren und Übertragen von [HSM-geschützten Schlüsseln für Azure Key Vault.)](/azure/key-vault/key-vault-hsm-protected-keys)

Um die Option zum Hochladen des Verschlüsselungsschlüssels zu verwenden, benötigen Sie sowohl den öffentlichen als auch den privaten Verschlüsselungsschlüssel.

Mit dem Schlüsselverwaltungsfeature wird die Komplexität der Verwaltung von Verschlüsselungsschlüsseln durch die Verwendung von Azure Key Vault zum sicheren Speichern von Verschlüsselungsschlüsseln vereinfacht. Azure Key Vault schützt kryptografische Schlüssel und geheime Schlüssel, die von Cloudanwendungen und -diensten verwendet werden. Das Schlüsselverwaltungsfeature erfordert nicht, dass Sie über ein Azure Key Vault-Abonnement verfügen, und in den meisten Situationen ist es nicht erforderlich, auf Verschlüsselungsschlüssel zuzugreifen, die für Dynamics 365 im Tresor verwendet werden.