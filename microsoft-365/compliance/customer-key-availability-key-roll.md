---
title: Rollen oder Drehen eines Kundenschlüssels oder eines Verfügbarkeitsschlüssels
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: In diesem Artikel erfahren Sie, wie Sie die in Azure Key Vault gespeicherten Kundenstamm Schlüssel, die mit dem Kundenschlüssel verwendet werden, verrollen. Zu den Diensten gehören Exchange Online-, Skype for Business-, SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien.
ms.openlocfilehash: 29a36636253f5f01181f231941d0c3a9e26abacc
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633642"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a>Rollen oder Drehen eines Kundenschlüssels oder eines Verfügbarkeitsschlüssels

> [!CAUTION]
> Rollen Sie nur einen Verschlüsselungsschlüssel, den Sie mit dem Kundenschlüssel verwenden, wenn Ihre Sicherheits-oder Compliance-Anforderungen es erfordern, dass Sie den Schlüsselrollen müssen. Löschen Sie darüber hinaus keine Schlüssel, die Richtlinien zugeordnet sind oder waren. Wenn Sie Rolling-Codes für Ihre Schlüssel generieren, wird Inhalt mit den vorhergehenden Schlüsseln verschlüsselt. Werden beispielsweise aktive Postfächer häufig neu verschlüsselt, so werden inaktive, abgeschaltete oder deaktivierte Postfächer möglicherweise weiterhin mit den vorhergehenden Schlüsseln verschlüsselt. SharePoint Online führt Sicherungen von Inhalten durch, um die Verlagerung der Speicherorte dieser sowie deren Wiederherstellung zu ermöglichen, weshalb es durchaus vorkommen kann, dass weiterhin Inhalte archiviert sind, die ältere Schlüssel verwendet.

## <a name="about-rolling-the-availability-key"></a>Informationen zum Rollen des Verfügbarkeits Schlüssels

Microsoft stellt Kunden keine direkte Steuerung des Verfügbarkeits Schlüssels offen. Sie können beispielsweise nur die Schlüssel, die Sie in Azure Key Vault besitzen, Rollen (Drehen). Microsoft 365 rollt die Verfügbarkeits Schlüssel nach einem intern definierten Zeitplan. Für diese Schlüsselrollen gibt es keine Vereinbarung zum Service Level (SLA) für Kunden. Microsoft 365 dreht den Verfügbarkeits Schlüssel mithilfe des Microsoft 365-Dienstcodes in einem automatisierten, nicht manuellen Prozess. Microsoft-Administratoren können den Rollvorgang initiieren. Der Schlüssel wird mithilfe von automatisierten Mechanismen ohne direkten Zugriff auf den Schlüsselspeicher gerollt. Der Zugriff auf den geheimen Schlüsselspeicher für Verfügbarkeit wird nicht für Microsoft-Administratoren bereitgestellt. Das Rollen für die Verfügbarkeit von Schlüsseln nutzt denselben Mechanismus, der zum anfänglichen generieren des Schlüssels verwendet wird. Weitere Informationen zum Verfügbarkeits Schlüssel finden Sie unter [Grundlegendes zum Verfügbarkeits Schlüssel](customer-key-availability-key-understand.md).

> [!IMPORTANT]
> Exchange Online-und Skype for Business-Verfügbarkeits Schlüssel können von Kunden effektiv ausgeführt werden, indem Sie eine neue DEP erstellen, da für jede von Ihnen erstellte Datenausführungsverhinderung ein eindeutiger Verfügbarkeits Schlüssel generiert wird. Verfügbarkeits Schlüssel für SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien sind auf Gesamtstrukturebene vorhanden und werden für DEPs und Kunden freigegeben, was bedeutet, dass das Walzen nur bei einem intern definierten Microsoft-Zeitplan erfolgt. Um das Risiko zu minimieren, den Verfügbarkeits Schlüssel nicht jedes Mal zu reduzieren, wenn eine neue DEP erstellt wird, Rollen SharePoint, OneDrive und Teams den Mandanten-zwischen Schlüssel (tik), den Schlüssel, der von den Stamm Schlüsseln des Kunden und dem Verfügbarkeits Schlüssel umschlossen ist, jedes Mal, wenn eine neue DEP erstellt wird.

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a>Fordern Sie eine neue Version jedes vorhandenen Stammschlüssels an, den Sie Rollen möchten.

Wenn Sie einen Schlüssel ausrollen, fordern Sie eine neue Version eines vorhandenen Schlüssels an. Um eine neue Version eines vorhandenen Schlüssels anzufordern, verwenden Sie dasselbe Cmdlet, [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey), mit der gleichen Syntax, die Sie zum Erstellen des Schlüssels in erster Linie verwendet haben. Nachdem Sie alle Schlüssel, die einer Daten Verschlüsselungsrichtlinie (DEP) zugeordnet sind, fertig gestellt haben, führen Sie ein anderes Cmdlet aus, um sicherzustellen, dass der Kundenschlüssel mit dem neuen Schlüssel beginnt. Führen Sie diesen Schritt in jedem Azure Key Vault (AKV) aus.

Beispiel:

1. Melden Sie sich bei Ihrem Azure-Abonnement mit Azure PowerShell an. Anweisungen finden Sie unter [Anmelden mit Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

2. Führen Sie das Cmdlet Add-AzKeyVaultKey aus, wie im folgenden Beispiel gezeigt:

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   In diesem Beispiel erstellt das Cmdlet eine neue Version des Schlüssels, da im **contoso-O365EX-na-VaultA1** -Tresor ein Schlüssel namens " **contoso-O365EX-na-VaultA1-Key001** " vorhanden ist. Bei diesem Vorgang werden die vorherigen Schlüssel Versionen im Versionsverlauf für den Schlüssel beibehalten. Sie benötigen die vorherige Schlüssel Version, um die Daten zu entschlüsseln, die Sie noch verschlüsselt. Nachdem Sie alle einem DEP zugeordneten Schlüssel ausgeführt haben, führen Sie ein zusätzliches Cmdlet aus, um sicherzustellen, dass der Kundenschlüssel mit dem neuen Schlüssel beginnt. In den folgenden Abschnitten werden die Cmdlets ausführlicher beschrieben.
  
## <a name="update-the-customer-key-for-exchange-online-and-skype-for-business"></a>Aktualisieren des Kunden Schlüssels für Exchange Online und Skype for Business

Wenn Sie eine der Azure Key Vault-Schlüsselrollen, die einer DEP zugeordnet sind, die mit Exchange Online und Skype for Business verwendet wird, müssen Sie die DEP so aktualisieren, dass Sie auf den neuen Schlüssel verweist. Dadurch wird der Verfügbarkeits Schlüssel nicht gedreht.

Führen Sie das Cmdlet "DataEncryptionPolicy" wie folgt aus, um den Kundenschlüssel zur Verwendung des neuen Schlüssels zum Verschlüsseln von Postfächern zu instruieren:

1. Führen Sie das Cmdlet "DataEncryptionPolicy" in Azure PowerShell aus:
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

   Innerhalb von 72 Stunden werden die aktiven Postfächer, die dieser DEP zugeordnet sind, mit dem neuen Schlüssel verschlüsselt.

2. Um den Wert für die DataEncryptionPolicyID-Eigenschaft für das Postfach zu überprüfen, führen Sie die Schritte unter [bestimmen der einem Postfach zugewiesenen DEP](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox)aus. Der Wert für diese Eigenschaft ändert sich, sobald der Dienst den aktualisierten Schlüssel anwendet.
  
## <a name="update-the-customer-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>Aktualisieren des Kunden Schlüssels für SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien

Mit SharePoint Online können Sie jeweils nur einen Schlüsselrollen. Wenn Sie beide Schlüssel in einem schlüsseltresor verrollen möchten, warten Sie, bis der erste Vorgang abgeschlossen ist. Microsoft empfiehlt, dass Sie Ihre Vorgänge Staffeln, um dieses Problem zu vermeiden. Wenn Sie eine der Azure Key Vault-Schlüsselrollen, die einer DEP zugeordnet sind, die mit SharePoint Online und OneDrive für Unternehmen verwendet wird, müssen Sie die DEP so aktualisieren, dass Sie auf den neuen Schlüssel verweist. Dadurch wird der Verfügbarkeits Schlüssel nicht gedreht.

1. Führen Sie das Cmdlet Update-SPODataEncryptionPolicy wie folgt aus:
  
   ```powershell
   Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   Während dieses Cmdlet den Schlüsselrollen Vorgang für SharePoint Online und OneDrive für Unternehmen startet, wird die Aktion nicht sofort abgeschlossen.

2. Zum Anzeigen des Fortschritts der Generierung eines Rolling-Code für einen Schlüssel, müssen Sie das Cmdlet „Get-SPODataEncryptionPolicy“ wie folgt ausführen:

   ```powershell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a>Verwandte Artikel

- [Dienst Verschlüsselung mit Kundenschlüssel für Office 365](customer-key-overview.md)

- [Einrichten des Kundenschlüssels für Office 365](customer-key-set-up.md)

- [Verwalten des Kundenschlüssels für Office 365](customer-key-manage.md)

- [Informationen zum Verfügbarkeits Schlüssel](customer-key-availability-key-understand.md)
