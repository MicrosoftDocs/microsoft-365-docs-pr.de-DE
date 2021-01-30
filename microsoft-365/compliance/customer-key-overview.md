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
ms.openlocfilehash: efb2ba9c2532973a096c509b57639544fc2ddbe5
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058488"
---
# <a name="service-encryption-with-customer-key"></a>Dienstverschlüsselung mit Kundenschlüssel

Microsoft 365 bietet grundlegende Verschlüsselung auf Volumeebene, die über BitLocker und Distributed Key Manager (DKM) aktiviert ist. Microsoft 365 bietet eine zusätzliche Verschlüsselungsebene auf der Anwendungsebene für Ihre Inhalte. Dieser Inhalt enthält Daten aus Exchange Online-, Skype for Business-, SharePoint Online-, OneDrive for Business- und Teams-Dateien. Diese hinzugefügte Verschlüsselungsebene wird als Dienstverschlüsselung bezeichnet.

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a>Zusammenarbeit von Dienstverschlüsselung, BitLocker und Customer Key

Die Dienstverschlüsselung stellt sicher, dass ruhede Inhalte auf dienstebene verschlüsselt werden. **Ihre Daten werden im Microsoft 365-Dienst** immer mit BitLocker und DKM verschlüsselt. Weitere Informationen finden Sie unter "Sicherheits-, Datenschutz- und Complianceinformationen" und wie Exchange Online Ihre geheimen [E-Mail-Schlüssel sichert.](exchange-online-secures-email-secrets.md) Customer Key bietet zusätzlichen Schutz vor der Anzeige von Daten durch nicht autorisierte Systeme oder Mitarbeiter und ergänzt die BitLocker-Datenträgerverschlüsselung in Microsoft-Rechenzentren. Die Dienstverschlüsselung soll nicht verhindern, dass Mitarbeiter von Microsoft auf Kundendaten zugreifen. Der Hauptzweck besteht in der Unterstützung von Kunden bei der Erfüllung gesetzlicher oder Complianceverpflichtungen für die Kontrolle von Stammschlüsseln. Kunden autorisieren explizit O365-Dienste, ihre Verschlüsselungsschlüssel zu verwenden, um mehrwertige Clouddienste wie eDiscovery, Ansoftware, Antispam, Suchindizierung usw. zur Verfügung zu stellen.

Customer Key baut auf der Dienstverschlüsselung auf und ermöglicht ihnen die Bereitstellung und Steuerung von Verschlüsselungsschlüsseln. Microsoft 365 verwendet dann diese Schlüssel, um Ihre ruhen lassenen Daten zu verschlüsseln, wie in den [Onlinedienstbedingungen (OST) beschrieben.](https://www.microsoft.com/licensing/product-licensing/products.aspx) Customer Key hilft Ihnen bei der Erfüllung von Complianceverpflichtungen, da Sie die Verschlüsselungsschlüssel steuern, die Microsoft 365 zum Verschlüsseln und Entschlüsseln von Daten verwendet.
  
Customer Key verbessert die Fähigkeit Ihrer Organisation, die Anforderungen der Complianceanforderungen zu erfüllen, die wichtige Vereinbarungen mit dem Clouddienstanbieter festlegen. Mit Customer Key können Sie die Stammverschlüsselungsschlüssel für Ihre ruhen lassenen Microsoft 365-Daten auf Anwendungsebene bereitstellen und steuern. Als Ergebnis haben Sie die Kontrolle über die Schlüssel Ihrer Organisation. Wenn Sie den Dienst beenden möchten, widerrufen Sie den Zugriff auf die Stammschlüssel Ihrer Organisation. Für alle Microsoft 365-Dienste ist das Löschen des Zugriffs auf die Schlüssel der erste Schritt auf dem Weg zur Löschung von Daten. Durch das Wiederbeigen des Zugriffs auf die Schlüssel sind die Daten für den Dienst unlesbar.

## <a name="customer-key-encrypts-data-at-rest-in-office-365"></a>Kundenschlüssel verschlüsselt ruhende Daten in Office 365

Mithilfe von Schlüsseln, die Sie bereitstellen, verschlüsselt Customer Key:

- SharePoint Online-, OneDrive for Business- und Teams-Dateien.
- Dateien, die auf OneDrive for Business hochgeladen wurden.
- Exchange Online-Postfachinhalte, einschließlich E-Mail-Nachrichtentextinhalten, Kalendereinträgen und Inhalten in E-Mail-Anlagen.
- Textunterhaltungen von Skype for Business.

Wir bieten derzeit keine Kontrolle über die Verschlüsselungsschlüssel für Das Hochladen von Skype-Live- und Skype-Besprechungsinhalten. Stattdessen werden diese Inhalte zusammen mit allen anderen Inhalten in Office 365 verschlüsselt.

### <a name="customer-key-with-hybrid-deployments"></a>Customer Key mit Hybridbereitstellungen

Customer Key verschlüsselt nur ruhende Daten in der Cloud. Customer Key funktioniert nicht, um Ihre lokalen Postfächer und Dateien zu schützen. Sie können Ihre lokalen Daten mit einer anderen Methode verschlüsseln, z. B. BitLocker.

## <a name="about-the-data-encryption-policy-dep"></a>Informationen zur Datenverschlüsselungsrichtlinie (DEP)

Eine Datenverschlüsselungsrichtlinie definiert die Verschlüsselungshierarchie zum Verschlüsseln von Daten mithilfe der einzelnen schlüssel, die Sie bereitstellen, sowie des durch Microsoft geschützten Verfügbarkeitsschlüssels. Sie erstellen DEPs mithilfe von PowerShell-Cmdlets, die für jeden Dienst unterschiedlich sind, und weisen diese DEPs zum Verschlüsseln von Anwendungsdaten zu. Beispiel:

**Exchange Online und Skype for Business** Sie können bis zu 50 DEPs pro Mandant erstellen. Sie ordnen DEPs Ihren Kundenschlüsseln in Azure Key Vault zu und weisen dePs dann einzelnen Postfächern zu. Wenn Sie einem Postfach eine DEP zuweisen:

- das Postfach für eine Postfach verschieben gekennzeichnet ist. Basierend auf den Prioritäten in Microsoft 365, wie hier beschrieben, verschieben Sie Anforderungen [im Microsoft 365-Dienst.](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service)

- Die Verschlüsselung erfolgt, während das Postfach verschoben wird. Es kann 72 Stunden dauern, bis das Postfach mit der neuen DEP verschlüsselt wird. Wenn die Postfächer nach dem Warten von 72 Stunden ab dem Zeitpunkt, an dem Sie die DEP zugewiesen haben, nicht verschlüsselt sind, wenden Sie sich an Microsoft.

Später können Sie entweder die DEP aktualisieren oder dem Postfach eine andere DEP zuweisen, wie in "Verwalten von [Kundenschlüssel für Office 365" beschrieben.](customer-key-manage.md) Jedes Postfach muss über entsprechende Lizenzen verfügen, um eine DEP zuweisen zu können. Weitere Informationen zur Lizenzierung finden Sie unter ["Vor dem Einrichten von Customer Key".](customer-key-set-up.md#before-you-set-up-customer-key)

> [!NOTE]
> Die DEP kann auf ein freigegebenes Postfach, ein Postfach für öffentliche Ordner und ein Microsoft 365-Gruppenpostfach für Mandanten angewendet werden, die die Lizenzierungsanforderung für Benutzerpostfächer erfüllen, obwohl einige dieser Postfachtypen keine zugewiesene Lizenz (Postfach für öffentliche Ordner und Microsoft 365-Gruppenpostfach) sein können oder eine Lizenz zum Erhöhen des Speichers (freigegebenes Postfach) benötigen.

**SharePoint Online-, OneDrive for Business- und #A0** Wenn Sie das Multi-Geo-Feature verwenden, können Sie bis zu einer DEP pro geografischem Standort für Ihre Organisation erstellen. Sie können für jeden geografischen Standort unterschiedliche Kundenschlüssel verwenden. Wenn Sie das Multi-Geo-Feature nicht verwenden, können Sie nur eine DEP pro Mandant erstellen. Wenn Sie die Datenverschlüsselungsverschlüsselung (DEP) zuweisen, beginnt die Verschlüsselung automatisch, kann jedoch einige Zeit dauern. Weitere Informationen finden Sie unter ["Einrichten des Kundenschlüssels".](customer-key-set-up.md)

## <a name="leaving-the-service"></a>Verlassen des Diensts

Customer Key unterstützt Sie bei der Erfüllung der Complianceverpflichtungen, indem Sie Es Ihnen ermöglichen, Ihre Schlüssel zu widerrufen, wenn Sie den Microsoft 365-Dienst verlassen. Wenn Sie Ihre Schlüssel im Rahmen des Verlassens des Diensts widerrufen, wird der Verfügbarkeitsschlüssel gelöscht, was zu einer kryptografischen Löschung Ihrer Daten führt. Die kryptografische Löschung verringert das Risiko der Datenmanmanenz, was für die Erfüllung von Sicherheits- und Complianceverpflichtungen wichtig ist. Informationen zum Datenbereinigungsprozess und zum Widerrufen von Schlüsseln finden Sie unter Widerrufen Ihrer Schlüssel und Starten [des Datenbereinigungspfads.](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)

### <a name="encryption-ciphers-used-by-customer-key"></a>Verschlüsselungschiffren, die vom Kundenschlüssel verwendet werden

Customer Key verwendet eine Vielzahl von Verschlüsselungschiffren zum Verschlüsseln von Schlüsseln, wie in den folgenden Abbildungen dargestellt.

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Verschlüsselungschiffren zum Verschlüsseln von Schlüsseln für Exchange Online und Skype for Business

![Verschlüsselungschiffren für Exchange Online Customer Key](../media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Verschlüsselungschiffren zum Verschlüsseln von Schlüsseln für SharePoint Online-, OneDrive for Business- und #A0

![Verschlüsselungschiffren für SharePoint Online Customer Key](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>Verwandte Artikel

- [Einrichten des Kundenschlüssels](customer-key-set-up.md)

- [Verwalten von Kundenschlüsseln](customer-key-manage.md)

- [Rollen oder Drehen eines Kundenschlüssels oder eines Verfügbarkeitsschlüssels](customer-key-availability-key-roll.md)

- [Informationen zum Verfügbarkeitsschlüssel](customer-key-availability-key-understand.md)

- [Customer Lockbox](customer-lockbox-requests.md)

- [Dienstverschlüsselung](office-365-service-encryption.md)
