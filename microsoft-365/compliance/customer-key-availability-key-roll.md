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
description: 'Erfahren Sie, wie Sie die in Azure Key Vault gespeicherten Kundenstammschlüssel rollen, die mit dem Kundenschlüssel verwendet werden. Zu den Diensten gehören Exchange Online-, Skype for Business-, SharePoint Online-, OneDrive for Business- und #A0 .'
ms.openlocfilehash: 980d6b198b326cb75bb2b4ef4d2c980f605f23e5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923331"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a>Rollen oder Drehen eines Kundenschlüssels oder eines Verfügbarkeitsschlüssels

> [!CAUTION]
> Rollen Sie nur einen Verschlüsselungsschlüssel, den Sie mit dem Kundenschlüssel verwenden, wenn Ihre Sicherheits- oder Complianceanforderungen es vorschreiben, dass Sie den Schlüssel rollen müssen. Löschen Sie darüber hinaus keine Schlüssel, die Richtlinien zugeordnet sind oder waren. Wenn Sie Rolling-Codes für Ihre Schlüssel generieren, wird Inhalt mit den vorhergehenden Schlüsseln verschlüsselt. Werden beispielsweise aktive Postfächer häufig neu verschlüsselt, so werden inaktive, abgeschaltete oder deaktivierte Postfächer möglicherweise weiterhin mit den vorhergehenden Schlüsseln verschlüsselt. SharePoint Online führt Sicherungen von Inhalten durch, um die Verlagerung der Speicherorte dieser sowie deren Wiederherstellung zu ermöglichen, weshalb es durchaus vorkommen kann, dass weiterhin Inhalte archiviert sind, die ältere Schlüssel verwendet.

## <a name="about-rolling-the-availability-key"></a>Informationen zum Rolling des Verfügbarkeitsschlüssels

Microsoft macht keine direkte Kontrolle über den Verfügbarkeitsschlüssel für Kunden verfügbar. Sie können z. B. nur die Schlüssel rollen (drehen), die Sie in Azure Key Vault besitzen. Microsoft 365 rollt die Verfügbarkeitsschlüssel nach einem intern definierten Zeitplan. Für diese Schlüsselrollen gibt es keine vereinbarung für kundenorientierte Servicelevels (Service Level Agreement, SLA). Microsoft 365 dreht den Verfügbarkeitsschlüssel mithilfe von Microsoft 365-Dienstcode in einem automatisierten, nicht manuellen Prozess. Microsoft-Administratoren können den Rollprozess initiieren. Der Schlüssel wird mithilfe automatisierter Mechanismen ohne direkten Zugriff auf den Schlüsselspeicher rollt. Der Zugriff auf den geheimen Informationsspeicher des Verfügbarkeitsschlüssels wird für Microsoft-Administratoren nicht bereitgestellt. Das Rollen von Verfügbarkeitsschlüsseln nutzt denselben Mechanismus, der zum anfänglichen Generieren des Schlüssels verwendet wird. Weitere Informationen zum Verfügbarkeitsschlüssel finden Sie unter [Verstehen des Verfügbarkeitsschlüssels](customer-key-availability-key-understand.md).

> [!IMPORTANT]
> Exchange Online- und Skype for Business-Verfügbarkeitsschlüssel können von Kunden, die eine neue DEP erstellen, effektiv gerollt werden, da für jede erstellte DEP ein eindeutiger Verfügbarkeitsschlüssel generiert wird. Verfügbarkeitsschlüssel für SharePoint Online-, OneDrive for Business- und #A0 sind auf Gesamtstrukturebene vorhanden und werden von DEPs und Kunden gemeinsam genutzt, was bedeutet, dass das Rolling nur nach einem intern von Microsoft definierten Zeitplan erfolgt. Um das Risiko zu verringern, dass der Verfügbarkeitsschlüssel nicht jedes Mal rollt, wenn eine neue DEP erstellt wird, rollen SharePoint, OneDrive und Teams den Mandantenzwingschlüssel (TIK), den Schlüssel, der von den Stammschlüsseln und dem Verfügbarkeitsschlüssel des Kunden umschlossen wird, jedes Mal, wenn eine neue DEP erstellt wird.

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a>Anfordern einer neuen Version jedes vorhandenen Stammschlüssels, den Sie rollen möchten

Wenn Sie einen Schlüssel rollen, fordern Sie eine neue Version eines vorhandenen Schlüssels an. Wenn Sie eine neue Version eines vorhandenen Schlüssels anfordern möchten, verwenden Sie dasselbe Cmdlet, [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey), mit derselben Syntax wie zum Erstellen des Schlüssels. Nachdem Sie das Rolling eines Schlüssels abgeschlossen haben, der einer Datenverschlüsselungsrichtlinie (Data Encryption Policy, DEP) zugeordnet ist, führen Sie ein weiteres Cmdlet aus, um sicherzustellen, dass der Kundenschlüssel mit der Verwendung des neuen Schlüssels beginnt. Gehen Sie wie in jedem Azure Key Vault (AKV) vor.

Beispiel:

1. Melden Sie sich mit Azure PowerShell bei Ihrem Azure-Abonnement an. Anweisungen finden Sie unter [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).

2. Führen Sie Add-AzKeyVaultKey cmdlet aus, wie im folgenden Beispiel gezeigt:

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   Da in diesem Beispiel ein Schlüssel namens **Contoso-O365EX-NA-VaultA1-Key001** im **Contoso-O365EX-NA-VaultA1-Tresor** vorhanden ist, erstellt das Cmdlet eine neue Version des Schlüssels. Bei diesem Vorgang werden die vorherigen Schlüsselversionen im Versionsverlauf für den Schlüssel beibehalten. Sie benötigen die vorherige Schlüsselversion, um die Daten zu entschlüsseln, die weiterhin verschlüsselt werden. Nachdem Sie das Rolling eines schlüssels abgeschlossen haben, der einer DEP zugeordnet ist, führen Sie ein zusätzliches Cmdlet aus, um sicherzustellen, dass der Kundenschlüssel mit der Verwendung des neuen Schlüssels beginnt. In den folgenden Abschnitten werden die Cmdlets ausführlicher beschrieben.
  
## <a name="update-the-customer-key-for-exchange-online-and-skype-for-business"></a>Aktualisieren des Kundenschlüssels für Exchange Online und Skype for Business

Wenn Sie einen der Azure Key Vault-Schlüssel rollen, der einer mit Exchange Online und Skype for Business verwendeten DEP zugeordnet ist, müssen Sie die DEP aktualisieren, um auf den neuen Schlüssel zu zeigen. Dadurch wird der Verfügbarkeitsschlüssel nicht gedreht.

Führen Sie das cmdlet Set-DataEncryptionPolicy wie folgt aus, um Kundenschlüssel anweisen, den neuen Schlüssel zum Verschlüsseln von Postfächern zu verwenden:

1. Führen Sie Set-DataEncryptionPolicy cmdlet in Azure PowerShell aus:
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

   Innerhalb von 72 Stunden werden die aktiven Postfächer, die dieser DEP zugeordnet sind, mit dem neuen Schlüssel verschlüsselt.

2. Um den Wert für die DataEncryptionPolicyID-Eigenschaft für das Postfach zu überprüfen, verwenden Sie die Schritte unter [Determine the DEP assigned to a mailbox](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox). Der Wert für diese Eigenschaft ändert sich, sobald der Dienst den aktualisierten Schlüssel angewendet hat.
  
## <a name="update-the-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Aktualisieren der Dateien "Customer Key" für SharePoint Online, OneDrive for Business und Teams

Mit SharePoint Online können Sie nur einen Schlüssel gleichzeitig rollen. Wenn Sie beide Schlüssel in einem Schlüsseltresor rollen möchten, warten Sie, bis der erste Vorgang abgeschlossen ist. Microsoft empfiehlt, ihre Vorgänge zu staffeln, um dieses Problem zu vermeiden. Wenn Sie einen der Azure Key #A0 rollen, der einer mit SharePoint Online und OneDrive for Business verwendeten DEP zugeordnet ist, müssen Sie die DEP aktualisieren, um auf den neuen Schlüssel zu zeigen. Dadurch wird der Verfügbarkeitsschlüssel nicht gedreht.

1. Führen Sie Update-SPODataEncryptionPolicy cmdlet wie folgt aus:
  
   ```powershell
   Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   Während dieses Cmdlet den Schlüsselrollvorgang für SharePoint Online und OneDrive for Business startet, wird die Aktion nicht sofort abgeschlossen.

2. Zum Anzeigen des Fortschritts der Generierung eines Rolling-Code für einen Schlüssel, müssen Sie das Cmdlet „Get-SPODataEncryptionPolicy“ wie folgt ausführen:

   ```powershell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a>Verwandte Artikel

- [Dienstverschlüsselung mit Kundenschlüssel für Office 365](customer-key-overview.md)

- [Einrichten des Kundenschlüssels für Office 365](customer-key-set-up.md)

- [Verwalten des Kundenschlüssels für Office 365](customer-key-manage.md)

- [Informationen zum Verfügbarkeitsschlüssel](customer-key-availability-key-understand.md)