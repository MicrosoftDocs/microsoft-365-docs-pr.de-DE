---
title: Dienstverschlüsselung mit Kundenschlüssel
ms.author: krowley
author: kccross
manager: laurawi
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
description: In diesem Artikel erfahren Sie, wie die Dienstverschlüsselung mit Customer Key in Microsoft 365 funktioniert.
ms.openlocfilehash: d12a5d2f80de11a69fc4a36146a511c5f9a306f8
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52769449"
---
# <a name="service-encryption-with-customer-key"></a>Dienstverschlüsselung mit Kundenschlüssel

Microsoft 365 bietet grundlegende Verschlüsselung auf Volumenebene, die über BitLocker und Distributed Key Manager (DKM) aktiviert wird. Microsoft 365 bietet eine zusätzliche Verschlüsselungsebene für Ihre Inhalte. Dieser Inhalt enthält Daten aus Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business und Microsoft Teams.

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a>Zusammenarbeit von Dienstverschlüsselung, BitLocker und Customer Key

Ihre Ruhedaten werden im Microsoft 365-Dienst immer mit BitLocker und DKM verschlüsselt. Weitere Informationen finden Sie unter [So schützt Exchange Online Ihre geheimen E-Mail-Schlüssel.](exchange-online-secures-email-secrets.md) Customer Key bietet zusätzlichen Schutz vor der Anzeige von Daten durch nicht autorisierte Systeme oder Mitarbeiter und ergänzt BitLocker Datenträgerverschlüsselung in Microsoft-Rechenzentren. Die Dienstverschlüsselung soll nicht verhindern, dass Microsoft-Mitarbeiter auf Ihre Daten zugreifen. Stattdessen hilft Ihnen Customer Key bei der Einhaltung behördlicher oder Compliance-Verpflichtungen zur Steuerung von Stammschlüsseln. Sie autorisieren Microsoft 365 Dienste explizit, Ihre Verschlüsselungsschlüssel zur Bereitstellung von Mehrwert-Clouddiensten wie eDiscovery, Antischadsoftware, Antispam, Suchindizierung usw. zu verwenden.

Customer Key basiert auf der Dienstverschlüsselung und ermöglicht es Ihnen, Verschlüsselungsschlüssel bereitzustellen und zu steuern. Microsoft 365 verwendet dann diese Schlüssel, um Ihre ruhenden Daten zu verschlüsseln, wie in den [Onlinedienstbedingungen (OST)](https://www.microsoft.com/licensing/product-licensing/products.aspx)beschrieben. Customer Key hilft Ihnen bei der Einhaltung von Compliance-Verpflichtungen, da Sie die Verschlüsselungsschlüssel steuern, die Microsoft 365 zum Verschlüsseln und Entschlüsseln von Daten verwendet.
  
Customer Key verbessert die Fähigkeit Ihrer Organisation, die Anforderungen der Complianceanforderungen zu erfüllen, die wichtige Vereinbarungen mit dem Clouddienstanbieter festlegen. Mit Customer Key stellen Sie die Stammverschlüsselungsschlüssel für Ihre Microsoft 365 ruhenden Daten auf Anwendungsebene bereit und steuern sie. Daher haben Sie die Kontrolle über die Schlüssel Ihrer Organisation.

## <a name="customer-key-with-hybrid-deployments"></a>Kundenschlüssel mit Hybridbereitstellungen

Customer Key verschlüsselt nur ruhenden Daten in der Cloud. Customer Key funktioniert nicht, um Ihre lokalen Postfächer und Dateien zu schützen. Sie können Ihre lokalen Daten mit einer anderen Methode verschlüsseln, z. B. BitLocker.

## <a name="about-data-encryption-policies"></a>Informationen zu Datenverschlüsselungsrichtlinien

Eine Datenverschlüsselungsrichtlinie (Data Encryption Policy, DEP) definiert die Verschlüsselungshierarchie. Diese Hierarchie wird vom Dienst verwendet, um Daten mithilfe jedes von Ihnen verwalteten Schlüssels und des durch Microsoft geschützten Verfügbarkeitsschlüssels zu verschlüsseln. Sie erstellen DEPs mithilfe von PowerShell-Cmdlets und weisen diese DEPs dann zum Verschlüsseln von Anwendungsdaten zu. Es gibt drei Typen von DEPs, die von Microsoft 365 Customer Key unterstützt werden. Jeder Richtlinientyp verwendet unterschiedliche Cmdlets und bietet Eine Abdeckung für einen anderen Datentyp. Zu den DEPs, die Sie definieren können, gehören:

**DEP für mehrere Microsoft 365 Workloads** Diese DEPs verschlüsseln Daten über mehrere M365-Workloads für alle Benutzer innerhalb des Mandanten. Zu diesen Workloads gehören:

- Teams Chatnachrichten (1:1-Chats, Gruppenchats, Besprechungschats und Kanalunterhaltungen)
- Teams Mediennachrichten (Bilder, Codeausschnitte, Videonachrichten, Audionachrichten, Wiki-Bilder)
- Teams in Teams Speicher gespeicherte Anruf- und Besprechungsaufzeichnungen
- Teams Chatbenachrichtigungen
- Teams von Chatvorschlägen von Cortana
- Teams Statusmeldungen
- Benutzer- und Signalinformationen für Exchange Online
- Exchange Online Postfächer, die noch nicht durch Postfach-DEPs verschlüsselt wurden
- Microsoft Information Protection:

  - Genaue Datenübereinstimmungsdaten (EDM), einschließlich Datendateischemas, Regelpakete und die Salts, die zum Hashen der vertraulichen Daten verwendet werden. Bei EDM und Microsoft Teams verschlüsselt die DEP mit mehreren Workloads neue Daten ab dem Zeitpunkt, an dem Sie dem Mandanten die DATENverschlüsselungsrichtlinie zuweisen. Für Exchange Online verschlüsselt Customer Key alle vorhandenen und neuen Daten.

  - Bezeichnungskonfiguration für Vertraulichkeitsbezeichnungen

DePs mit mehreren Workloads verschlüsseln die folgenden Datentypen nicht. Stattdessen verwendet Microsoft 365 andere Arten der Verschlüsselung, um diese Daten zu schützen.

- daten SharePoint und OneDrive for Business.
- Microsoft Teams Dateien und einige Teams in OneDrive for Business und SharePoint Online gespeicherten Anruf- und Besprechungsaufzeichnungen werden mithilfe der SharePoint Online-DEP verschlüsselt.
- Andere Microsoft 365 Workloads wie Yammer und Planner, die derzeit nicht von Customer Key unterstützt werden.
- Teams Live Events and Q&A in Live Events. Für Teams ist dieses Szenario das einzige Szenario, das nicht mithilfe von DEP mit mehreren Workloads von Customer Key verschlüsselt wird.

Sie können mehrere DEPs pro Mandant erstellen, aber jeweils nur eine DATENdeskription zuweisen. Wenn Sie die Datenverschlüsselungsrichtlinie zuweisen, beginnt die Verschlüsselung automatisch, dauert aber je nach Größe Ihres Mandanten einige Zeit.

**DEPs für Exchange Online Postfächer** Postfach-DEPs bieten eine präziseere Kontrolle über einzelne Postfächer innerhalb Exchange Online. Verwenden Sie Postfach-DEPs zum Verschlüsseln von Daten, die in EXO-Postfächern unterschiedlicher Typen wie UserMailbox, MailUser, Group, PublicFolder und Freigegebene Postfächer gespeichert sind. Sie können bis zu 50 aktive DEPs pro Mandant haben und diese DEPs einzelnen Postfächern zuweisen. Sie können mehreren Postfächern eine DATENDEP zuweisen.

Standardmäßig werden Ihre Postfächer mit von Microsoft verwalteten Schlüsseln verschlüsselt. Wenn Sie einem Postfach eine Kundenschlüssel-DEP zuweisen:

- Wenn das Postfach mithilfe einer DEP mit mehreren Workloads verschlüsselt wird, wird das Postfach mithilfe der neuen Postfach-DEP neu erstellt, solange ein Benutzer oder ein Systemvorgang auf die Postfachdaten zugreift.

- Wenn das Postfach bereits mit von Microsoft verwalteten Schlüsseln verschlüsselt wurde, wird das Postfach mithilfe der neuen Postfach-DEP neu wiederherstellen, solange ein Benutzer oder ein Systemvorgang auf die Postfachdaten zugreift.

- Wenn das Postfach noch nicht mit der Standardverschlüsselung verschlüsselt ist, markiert der Dienst das Postfach für eine Verschiebung. Die Verschlüsselung erfolgt, sobald die Verschiebung abgeschlossen ist. Postfachverschiebungen werden auf der Grundlage von Prioritäten gesteuert, die für alle Microsoft 365 festgelegt wurden. Weitere Informationen finden Sie unter [Move requests in the Microsoft 365 service](/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service). Wenn die Postfächer innerhalb des angegebenen Zeitraums nicht verschlüsselt sind, wenden Sie sich an Microsoft.

Später können Sie entweder die DEP aktualisieren oder dem Postfach eine andere DATENdeaktivierung zuweisen, wie unter [Verwalten des Kundenschlüssels für Office 365](customer-key-manage.md)beschrieben. Jedes Postfach muss über die entsprechenden Lizenzen verfügen, um eine Datenzugriffsrichtlinie (DEP) zuzuweisen. Weitere Informationen zur Lizenzierung finden Sie unter "Vor dem Einrichten von [Customer Key".](customer-key-set-up.md#before-you-set-up-customer-key)

DEPs können einem freigegebenen Postfach, einem Postfach für öffentliche Ordner und Microsoft 365 Gruppenpostfach für Mandanten zugewiesen werden, die die Lizenzierungsanforderung für Benutzerpostfächer erfüllen. Sie benötigen keine separaten Lizenzen für nicht benutzerspezifische Postfächer, um Kundenschlüssel-DEP zuzuweisen.

Für Kundenschlüssel-DEPs, die Sie einzelnen Postfächern zuweisen, können Sie anfordern, dass Microsoft bestimmte DEPs löscht, wenn Sie den Dienst verlassen. Informationen zum Datenbereinigungsprozess und zum Sperren von Schlüsseln finden Sie unter [Widerrufen Ihrer Schlüssel und Starten des Datenbereinigungspfadprozesses.](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)

Wenn Sie den Zugriff auf Ihre Schlüssel im Rahmen des Verlassens des Diensts widerrufen, wird der Verfügbarkeitsschlüssel gelöscht, was zu einer kryptografischen Löschung Ihrer Daten führt. Das Löschen kryptografischer Daten verringert das Risiko der Datenwiederherstellung, was wichtig ist, um sowohl Sicherheits- als auch Compliance-Verpflichtungen zu erfüllen.

**DEP für SharePoint Online und OneDrive for Business** Diese Datenverschlüsselungsrichtlinie wird verwendet, um in SPO und OneDrive for Business gespeicherte Inhalte zu verschlüsseln, einschließlich Microsoft Teams in SPO gespeicherten Dateien. Wenn Sie das Multi-Geo-Feature verwenden, können Sie eine DATEN-DeP pro Geo für Ihre Organisation erstellen. Wenn Sie das Multi-Geo-Feature nicht verwenden, können Sie nur einen DeP pro Mandant erstellen. Weitere Informationen finden Sie unter Einrichten des [Kundenschlüssels.](customer-key-set-up.md)

### <a name="encryption-ciphers-used-by-customer-key"></a>Verschlüsselungschiffren, die von Customer Key verwendet werden

Customer Key verwendet verschiedene Verschlüsselungschiffren, um Schlüssel zu verschlüsseln, wie in den folgenden Abbildungen dargestellt.

Die Schlüsselhierarchie, die für DEPs verwendet wird, die Daten für mehrere Microsoft 365 Workloads verschlüsseln, ähnelt der Hierarchie, die für DEPs für einzelne Exchange Online Postfächer verwendet wird. Der einzige Unterschied besteht darin, dass der Postfachschlüssel durch den entsprechenden Microsoft 365 Workloadschlüssel ersetzt wird.

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Verschlüsselungschiffren zum Verschlüsseln von Schlüsseln für Exchange Online und Skype for Business

![Verschlüsselungschiffren für Exchange Online Kundenschlüssel](../media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Verschlüsselungschiffren, die zum Verschlüsseln von Schlüsseln für SharePoint Online-, OneDrive for Business- und Teams dateien verwendet werden

![Verschlüsselungschiffren für SharePoint Online Customer Key](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>Verwandte Artikel

- [Einrichten des Kundenschlüssels](customer-key-set-up.md)

- [Verwalten des Kundenschlüssels](customer-key-manage.md)

- [Rollen oder Drehen eines Kundenschlüssels oder eines Verfügbarkeitsschlüssels](customer-key-availability-key-roll.md)

- [Erfahren Sie mehr über den Verfügbarkeitsschlüssel](customer-key-availability-key-understand.md)

- [Customer Lockbox](customer-lockbox-requests.md)

- [Dienstverschlüsselung](office-365-service-encryption.md)