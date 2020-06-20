---
title: Dienst Verschlüsselung mit Kundenschlüssel
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
ms.custom: seo-marvel-apr2020
description: In diesem Artikel erfahren Sie, wie die Dienst Verschlüsselung mit dem Kundenschlüssel in Microsoft 365 verwendet werden kann.
ms.openlocfilehash: 217e23eff89427e5bd30a1da4dd36729110ed563
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817954"
---
# <a name="service-encryption-with-customer-key"></a>Dienst Verschlüsselung mit Kundenschlüssel

Microsoft 365 bietet eine grundlegende, auf Volumen Ebene verschlüsselte Verschlüsselung, die über BitLocker und den verteilten Schlüssel-Manager (DKM) aktiviert ist. Microsoft 365 bietet eine zusätzliche Verschlüsselungsebene auf Anwendungsebene für Ihre Inhalte. Dieser Inhalt enthält Daten aus Exchange Online-, Skype for Business-, SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien. Diese hinzugefügte Verschlüsselungsebene wird als Dienst Verschlüsselung bezeichnet.

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a>Zusammenarbeit von Dienst Verschlüsselung, BitLocker und Kunden Schlüsseln

Durch die Dienst Verschlüsselung wird sichergestellt, dass Inhalte im Ruhezustand auf Anwendungsebene verschlüsselt werden. **Ihre Daten werden immer im Rest im Microsoft 365-Dienst mit BitLocker und DKM verschlüsselt**. Weitere Informationen finden Sie unter "Informationen zu Sicherheit, Datenschutz und Kompatibilität" sowie dazu, [wie Exchange Online Ihre e-Mail-Geheimnisse sichert](exchange-online-secures-email-secrets.md). Der Kundenschlüssel bietet zusätzlichen Schutz vor dem Anzeigen von Daten durch nicht autorisierte Systeme oder Mitarbeiter und ergänzt die BitLocker-Datenträgerverschlüsselung in Microsoft-Rechenzentren. Die Dienst Verschlüsselung soll nicht verhindern, dass Microsoft-Mitarbeiter auf Kundendaten zugreifen können. Der Hauptzweck besteht darin, Kunden bei der Erfüllung behördlicher oder Compliance-rechtlicher Verpflichtungen zur Steuerung von Stamm Schlüsseln zu unterstützen. Kunden autorisieren O365 Services ausdrücklich, ihre Verschlüsselungsschlüssel zur Bereitstellung von Mehrwert-Cloud-Diensten wie eDiscovery, Antischadsoftware, Spam Schutz, Suchindizierung usw. zu verwenden.

Der Kundenschlüssel basiert auf der Dienst Verschlüsselung und ermöglicht Ihnen das Bereitstellen und Steuern von Verschlüsselungsschlüsseln. Microsoft 365 verwendet dann diese Schlüssel, um Ihre Daten im Ruhezustand zu verschlüsseln, wie in den [Online Services Terms (Ost)](https://www.microsoft.com/licensing/product-licensing/products.aspx)beschrieben. Mit dem Kundenschlüssel können Sie Compliance-Verpflichtungen erfüllen, da Sie die Verschlüsselungsschlüssel steuern, die von Microsoft 365 zum Verschlüsseln und Entschlüsseln von Daten verwendet werden.
  
Kundenschlüssel verbessert die Fähigkeit Ihrer Organisation, die Anforderungen der Compliance-Anforderungen zu erfüllen, die wichtige Vereinbarungen mit dem Cloud-Dienstanbieter festlegen. Mit dem Kundenschlüssel können Sie die Stamm Verschlüsselungsschlüssel für Ihre Microsoft 365-Daten auf Anwendungsebene bereitstellen und steuern. Folglich üben Sie die Kontrolle über die Schlüssel Ihrer Organisation aus. Wenn Sie sich entschließen, den Dienst zu beenden, widerrufen Sie den Zugriff auf die Stammschlüssel Ihrer Organisation. Für alle Microsoft 365-Dienste ist der Widerruf des Zugriffs auf die Schlüssel der erste Schritt auf dem Weg zum Löschen von Daten. Durch das widerrufen des Zugriffs auf die Schlüssel sind die Daten für den Dienst nicht lesbar.

## <a name="customer-key-encrypts-data-at-rest-in-office-365"></a>Kundenschlüssel verschlüsselt Daten im Ruhezustand in Office 365

Mithilfe der von Ihnen bereitgestellten Schlüssel verschlüsselt der Kundenschlüssel:

- SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien.
- In OneDrive für Unternehmen hochgeladene Dateien.
- Exchange Online Postfachinhalte einschließlich Inhalt von e-Mail-Text, Kalendereinträgen und Inhalt in e-Mail-Anlagen.
- Text Unterhaltungen aus Skype for Business.

Wir bieten derzeit keine Kunden Kontrolle über die Verschlüsselungsschlüssel für Uploads von Skype-Live Konferenzen und Skype-Besprechungsinhalten. Stattdessen werden diese Inhalte zusammen mit allen anderen Inhalten in Office 365 verschlüsselt.

### <a name="customer-key-with-hybrid-deployments"></a>Kundenschlüssel mit hybridbereitstellungen

Der Kundenschlüssel verschlüsselt nur Daten im Rest in der Cloud. Der Kundenschlüssel kann nicht zum Schutz Ihrer lokalen Postfächer und Dateien verwendet werden. Sie können Ihre lokalen Daten mithilfe einer anderen Methode wie BitLocker verschlüsseln.

## <a name="about-the-data-encryption-policy-dep"></a>Informationen zur Daten Verschlüsselungsrichtlinie (DEP)

Eine Daten Verschlüsselungsrichtlinie definiert die Verschlüsselungshierarchie zum Verschlüsseln von Daten mit jedem der von Ihnen bereitgestellten Schlüssel sowie den von Microsoft geschützten Verfügbarkeits Schlüssel. Sie erstellen DEPs mithilfe von PowerShell-Cmdlets, die für jeden Dienst unterschiedlich sind, und weisen diese DEPs zum Verschlüsseln von Anwendungsdaten zu. Beispiel:

**Exchange Online und Skype for Business** Sie können bis zu 50 DEPs pro Mandant erstellen. Sie ordnen DEPs ihren Kunden Schlüsseln in Azure Key Vault zu und weisen dann DEPs einzelnen Postfächern zu. Wenn Sie einer Datenausführungsverhinderung einem Postfach zuweisen:

- das Postfach ist für eine Post Fach Verlagerung markiert. Basierend auf den Prioritäten in Microsoft 365 wie hier beschrieben, [Verschiebeanforderungen im Microsoft 365-Dienst](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service).

- Die Verschlüsselung erfolgt, während das Postfach verschoben wird. Lassen Sie 72 Stunden zu, damit das Postfach mit der neuen DEP verschlüsselt wird. Wenn die Postfächer nach dem warten auf 72 Stunden ab dem Zeitpunkt, an dem Sie die DEP erhalten haben, nicht verschlüsselt sind, wenden Sie sich an Microsoft.

Später können Sie entweder die DEP aktualisieren oder eine andere DEP dem Postfach zuweisen, wie unter Verwalten des [Kunden Schlüssels für Office 365](customer-key-manage.md)beschrieben. Jedes Postfach muss über entsprechende Lizenzen verfügen, um eine Datenausführungsverhinderung zuzuweisen. Weitere Informationen zur Lizenzierung finden Sie unter [vor dem Einrichten des Kunden Schlüssels](customer-key-set-up.md#before-you-set-up-customer-key).

**SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien** Wenn Sie das Multi-Geo-Feature verwenden, können Sie bis zu einer Datenausführungsverhinderung pro Geo für Ihre Organisation erstellen. Sie können für jedes Geo unterschiedliche Kundenschlüssel verwenden. Wenn Sie das Multi-Geo-Feature nicht verwenden, können Sie nur eine DEP pro Mandanten erstellen. Wenn Sie die Datenausführungsverhinderung zuweisen, beginnt die Verschlüsselung automatisch, kann jedoch einige Zeit in Anspruch nehmen. Weitere Informationen finden Sie unter [Einrichten des Kunden Schlüssels](customer-key-set-up.md).

## <a name="leaving-the-service"></a>Verlassen des Diensts

Kundenschlüssel unterstützt Sie bei der Erfüllung der Compliance-Verpflichtungen, indem Sie Ihnen die Möglichkeit geben, Ihre Schlüssel zu widerrufen, wenn Sie den Microsoft 365-Dienst verlassen. Wenn Sie Ihre Schlüssel im Rahmen des Ausscheidens des Diensts widerrufen, wird der Verfügbarkeits Schlüssel gelöscht, was zu einer kryptografischen Löschung Ihrer Daten führt. Durch kryptografische Löschung wird das Risiko von Daten Remanenz verringert, die für die Erfüllung von Sicherheits-und Compliance-Verpflichtungen wichtig sind. Informationen zum Daten Löschprozess und zur Schlüssel Sperrung finden Sie unter [REVOKE your Keys und Start the Data Purge Path Process](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process).

### <a name="encryption-ciphers-used-by-customer-key"></a>Vom Kundenschlüssel verwendete Verschlüsselungs Chiffren

Der Kundenschlüssel verwendet eine Vielzahl von Verschlüsselungs Chiffren zum Verschlüsseln von Schlüsseln, wie in den folgenden Abbildungen dargestellt.

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Verschlüsselungs Chiffren, die zum Verschlüsseln von Schlüsseln für Exchange Online und Skype for Business verwendet werden

![Verschlüsselungs Chiffren für Exchange Online Kundenschlüssel](../media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Verschlüsselungs Chiffren, die zum Verschlüsseln von Schlüsseln für SharePoint Online-, OneDrive für Unternehmen-und Team Dateien verwendet werden

![Verschlüsselungs Chiffren für SharePoint Online Kundenschlüssel](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>Verwandte Artikel

- [Einrichten des Kunden Schlüssels](customer-key-set-up.md)

- [Verwalten des Kunden Schlüssels](customer-key-manage.md)

- [Rollen oder Drehen eines Kundenschlüssels oder eines Verfügbarkeitsschlüssels](customer-key-availability-key-roll.md)

- [Informationen zum Verfügbarkeits Schlüssel](customer-key-availability-key-understand.md)

- [Customer Lockbox](customer-lockbox-requests.md)

- [Dienst Verschlüsselung](office-365-service-encryption.md)
