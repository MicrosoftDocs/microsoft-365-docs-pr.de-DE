---
title: Dienstverschlüsselung mit Kundenschlüssel
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
- m365solution-mip
- m365initiative-compliance
ms.custom: seo-marvel-apr2020
description: In diesem Artikel erfahren Sie, wie die Dienstverschlüsselung mit dem Kundenschlüssel in Microsoft 365 funktioniert.
ms.openlocfilehash: 21291dc45cd634cd5b6a88c4e58972c17486724f
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51394723"
---
# <a name="service-encryption-with-customer-key"></a>Dienstverschlüsselung mit Kundenschlüssel

Microsoft 365 bietet eine grundlegende Verschlüsselung auf Volumeebene, die über BitLocker und Distributed Key Manager (DKM) aktiviert ist. Microsoft 365 bietet eine zusätzliche Verschlüsselungsebene auf der Anwendungsebene für Ihre Inhalte. Dieser Inhalt enthält Daten aus Exchange Online-, Skype for Business-, SharePoint Online-, OneDrive for Business- und #A0 Diese hinzugefügte Verschlüsselungsebene wird als Dienstverschlüsselung bezeichnet.

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a>Zusammenarbeit von Dienstverschlüsselung, BitLocker und Customer Key

Die Dienstverschlüsselung stellt sicher, dass ruhende Inhalte auf der Dienstebene verschlüsselt werden. **Ihre Daten werden im Microsoft 365-Dienst mit BitLocker** und DKM immer im Ruhedienst verschlüsselt. Weitere Informationen finden Sie unter "Sicherheits-, Datenschutz- und Complianceinformationen" und Wie [Exchange Online Ihre E-Mail-Geheimnisse sichert.](exchange-online-secures-email-secrets.md) Customer Key bietet zusätzlichen Schutz vor der Anzeige von Daten durch nicht autorisierte Systeme oder Mitarbeiter und ergänzt die BitLocker-Datenträgerverschlüsselung in Microsoft-Rechenzentren. Die Dienstverschlüsselung soll nicht verhindern, dass Microsoft-Mitarbeiter auf Kundendaten zugreifen. Der Hauptzweck besteht in der Unterstützung von Kunden bei der Erfüllung gesetzlicher oder Complianceverpflichtungen für die Steuerung von Stammschlüsseln. Kunden autorisieren O365-Dienste explizit, ihre Verschlüsselungsschlüssel zu verwenden, um mehrwertige Clouddienste wie eDiscovery, Anti-Malware, Antispam, Suchindizierung usw. zur Verfügung zu stellen.

Der Kundenschlüssel baut auf der Dienstverschlüsselung auf und ermöglicht ihnen die Bereitstellung und Steuerung von Verschlüsselungsschlüsseln. Microsoft 365 verwendet dann diese Schlüssel, um Ihre Ruhedaten zu verschlüsseln, wie in den [Onlinedienstebedingungen (OST) beschrieben.](https://www.microsoft.com/licensing/product-licensing/products.aspx) Customer Key hilft Ihnen bei der Erfüllung von Complianceverpflichtungen, da Sie die Verschlüsselungsschlüssel steuern, die Microsoft 365 zum Verschlüsseln und Entschlüsseln von Daten verwendet.
  
Customer Key verbessert die Fähigkeit Ihrer Organisation, die Anforderungen der Complianceanforderungen zu erfüllen, die wichtige Vereinbarungen mit dem Clouddienstanbieter angeben. Mit dem Kundenschlüssel stellen Sie die Stammverschlüsselungsschlüssel für Ihre Ruhedaten von Microsoft 365 auf Anwendungsebene zur Verfügung und steuern sie. Dies hat zur Folge, dass Sie die Kontrolle über die Schlüssel Ihrer Organisation ausüben. Wenn Sie den Dienst beenden möchten, widerrufen Sie den Zugriff auf die Stammschlüssel Ihrer Organisation. Für alle Microsoft 365-Dienste ist das Löschen des Zugriffs auf die Schlüssel der erste Schritt auf dem Weg zum Löschen von Daten. Durch das Wehren des Zugriffs auf die Schlüssel sind die Daten für den Dienst unlesbar.

## <a name="customer-key-encrypts-data-at-rest-in-office-365"></a>Kundenschlüssel verschlüsselt ruhende Daten in Office 365

Mithilfe von schlüsseln, die Sie bereitstellen, verschlüsselt der Kundenschlüssel auf Anwendungsebene:

- SharePoint Online-, OneDrive for Business- und #A0
- Auf OneDrive for Business hochgeladene Dateien.
- Exchange Online-Postfachinhalte, einschließlich E-Mail-Textkörperinhalten, Kalendereinträgen und inhalten in E-Mail-Anlagen.
- Textunterhaltungen von Skype for Business.

Wir bieten derzeit keine Kundensteuerung der Verschlüsselungsschlüssel für Skype-Besprechungsübertragungen und Skype-Besprechungsinhaltsuploads an. Stattdessen wird dieser Inhalt zusammen mit allen anderen Inhalten in Office 365 verschlüsselt.

### <a name="customer-key-with-hybrid-deployments"></a>Customer Key mit Hybridbereitstellungen

Der Kundenschlüssel verschlüsselt nur ruhende Daten in der Cloud. Der Kundenschlüssel funktioniert nicht, um Ihre lokalen Postfächer und Dateien zu schützen. Sie können Ihre lokalen Daten mit einer anderen Methode verschlüsseln, z. B. BitLocker.

## <a name="about-the-data-encryption-policy-dep"></a>Informationen zur Datenverschlüsselungsrichtlinie (Data Encryption Policy, DEP)

Eine Datenverschlüsselungsrichtlinie definiert die Verschlüsselungshierarchie zum Verschlüsseln von Daten mithilfe der einzelnen von Ihnen zur Verfügung en sten Schlüssel sowie des von Microsoft geschützten Verfügbarkeitsschlüssels. Sie erstellen DEPs mithilfe von PowerShell-Cmdlets, die für jeden Dienst unterschiedlich sind, und weisen diese DEPs zum Verschlüsseln von Anwendungsdaten zu. Beispiel:

**Exchange Online und Skype for Business** Sie können bis zu 50 DEPs pro Mandant erstellen. Sie ordnen DEPs Ihren Kundenschlüsseln in Azure Key Vault zu und weisen dann DEPs einzelnen Postfächern zu. Wenn Sie einem Postfach eine DEP zuweisen:

- das Postfach für eine Postfach verschieben markiert ist. Basierend auf Prioritäten in Microsoft 365, wie hier [beschrieben, verschieben Sie Anforderungen im Microsoft 365-Dienst](/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service).

- Die Verschlüsselung erfolgt, während das Postfach verschoben wird. Lassen Sie 72 Stunden zu, bis das Postfach mit der neuen DEP verschlüsselt wird. Wenn die Postfächer nach dem Warten von 72 Stunden nach dem Zeitpunkt, zu dem Sie die DEP zugewiesen haben, nicht verschlüsselt sind, wenden Sie sich an Microsoft.

Später können Sie entweder die DEP aktualisieren oder dem Postfach eine andere DEP zuweisen, wie unter Verwalten des [Kundenschlüssels für Office 365 beschrieben.](customer-key-manage.md) Jedes Postfach muss über entsprechende Lizenzen verfügen, um eine DEP zuweisen zu können. Weitere Informationen zur Lizenzierung finden Sie unter [Before you set up Customer Key](customer-key-set-up.md#before-you-set-up-customer-key).

> [!NOTE]
> Die DEP kann auf ein freigegebenes Postfach, ein Postfach für öffentliche Ordner und ein Microsoft 365-Gruppenpostfach für Mandanten angewendet werden, die die Lizenzierungsanforderung für Benutzerpostfächer erfüllen, auch wenn einige dieser Postfachtypen keine zugewiesene Lizenz (Postfach für öffentliche Ordner und Microsoft 365-Gruppenpostfach) sein können oder eine Lizenz zum Erhöhen des Speichers (freigegebenes Postfach) benötigen.

**SharePoint Online-, OneDrive for Business- und #A0** Wenn Sie das Multi-Geo-Feature verwenden, können Sie bis zu eine DEP pro Geo für Ihre Organisation erstellen. Sie können für jeden geografischen Standort unterschiedliche Kundenschlüssel verwenden. Wenn Sie das Multi-Geo-Feature nicht verwenden, können Sie nur eine DEP pro Mandant erstellen. Wenn Sie die DEP zuweisen, beginnt die Verschlüsselung automatisch, kann jedoch einige Zeit dauern. Weitere Informationen finden Sie unter [Einrichten des Kundenschlüssels](customer-key-set-up.md).

## <a name="leaving-the-service"></a>Verlassen des Diensts

Der Customer Key unterstützt Sie bei der Einhaltung von Complianceverpflichtungen, indem Sie Ihre Schlüssel widerrufen können, wenn Sie den Microsoft 365-Dienst verlassen. Wenn Sie Ihre Schlüssel im Rahmen des Verlassens des Diensts widerrufen, wird der Verfügbarkeitsschlüssel gelöscht, was zu einer kryptografischen Löschung Ihrer Daten führt. Die kryptografische Löschung verringert das Risiko der Datenkonformität, die für die Erfüllung von Sicherheits- und Complianceverpflichtungen wichtig ist. Weitere Informationen zum Datenbereinigungsprozess und zum Widerruf von Schlüsseln finden Sie unter [Revoke your keys and start the data purge path process](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process).

### <a name="encryption-ciphers-used-by-customer-key"></a>Verschlüsselungschiffren, die vom Kundenschlüssel verwendet werden

Customer Key verwendet eine Vielzahl von Verschlüsselungschiffren zum Verschlüsseln von Schlüsseln, wie in den folgenden Abbildungen dargestellt.

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Verschlüsselungschiffren zum Verschlüsseln von Schlüsseln für Exchange Online und Skype for Business

![Verschlüsselungschiffren für Exchange Online Customer Key](../media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Verschlüsselungschiffren zum Verschlüsseln von Schlüsseln für SharePoint Online-, OneDrive for Business- und #A0

![Verschlüsselungschiffren für SharePoint Online Customer Key](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>Verwandte Artikel

- [Einrichten des Kundenschlüssels](customer-key-set-up.md)

- [Verwalten des Kundenschlüssels](customer-key-manage.md)

- [Rollen oder Drehen eines Kundenschlüssels oder eines Verfügbarkeitsschlüssels](customer-key-availability-key-roll.md)

- [Informationen zum Verfügbarkeitsschlüssel](customer-key-availability-key-understand.md)

- [Customer Lockbox](customer-lockbox-requests.md)

- [Dienstverschlüsselung](office-365-service-encryption.md)