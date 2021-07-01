---
title: Einrichten von Verschlüsselung in Office 365 Enterprise
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/2/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e86fc991-0161-4f01-9c1c-d25e87733d06
description: Bei Office 365 sind einige Verschlüsselungsfunktionen standardmäßig aktiviert. andere Funktionen können konfiguriert werden, um bestimmte Compliance- oder gesetzliche Anforderungen zu erfüllen.
ms.openlocfilehash: a9a3170fdb99a4acfec8cf4d3b03ab9b584197bd
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228471"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>Einrichten von Verschlüsselung in Office 365 Enterprise

Die Verschlüsselung kann Verhindern, dass Ihre Inhalte von nicht autorisierten Benutzern gelesen werden. Da [die Verschlüsselung in Office 365](encryption.md) mit verschiedenen Technologien und Methoden erfolgen kann, gibt es keinen einzigen Ort, an dem Sie die Verschlüsselung aktivieren oder einrichten. Dieser Artikel enthält Informationen zu verschiedenen Methoden zum Einrichten oder Konfigurieren der Verschlüsselung als Teil Ihrer Informationsschutzstrategie.

> [!TIP]
> Wenn Sie weitere technische Details zur Verschlüsselung suchen, finden Sie [technische Referenzdetails zur Verschlüsselung in Office 365.](technical-reference-details-about-encryption.md)

Mit Office 365 sind standardmäßig mehrere Verschlüsselungsfunktionen verfügbar. Zusätzliche Verschlüsselungsfunktionen können konfiguriert werden, um bestimmte Compliance- oder gesetzliche Anforderungen zu erfüllen. In der folgenden Tabelle werden mehrere Verschlüsselungsmethoden für verschiedene Szenarien beschrieben.

<br>

****

|Szenario|Verschlüsselungsmethoden|
|---|---|
|Dateien werden auf Windows Computern gespeichert.|Die Verschlüsselung auf Computerebene kann mit BitLocker auf Windows Geräten erfolgen. Als Unternehmensadministrator oder IT-Pro können Sie dies mit dem Microsoft Deployment Toolkit (MDT) einrichten. Weitere Informationen finden Sie unter [Einrichten von MDT für BitLocker.](/windows/deployment/deploy-windows-mdt/set-up-mdt-for-bitlocker)|
|Dateien werden auf mobilen Geräten gespeichert|Einige Arten von mobilen Geräten verschlüsseln Dateien, die standardmäßig auf diesen Geräten gespeichert werden. Mit [funktionen von integrierten Verwaltung mobiler Geräte für Office 365](https://support.microsoft.com/office/capabilities-of-built-in-mobile-device-management-for-microsoft-365-a1da44e5-7475-4992-be91-9ccec25905b0)können Sie Richtlinien festlegen, die bestimmen, ob mobile Geräte auf Daten in Office 365 zugreifen dürfen. Sie können z. B. eine Richtlinie festlegen, die nur Geräten, die Inhalte verschlüsseln, den Zugriff auf Office 365 Daten gestattet. Siehe [Erstellen und Bereitstellen von Gerätesicherheitsrichtlinien.](https://support.microsoft.com/office/create-and-deploy-device-security-policies-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6) <p> Um zusätzliche Kontrolle darüber zu erhalten, wie mobile Geräte mit Office 365 interagieren, können Sie [erwägen, Microsoft Intune](/mem/intune/fundamentals/setup-steps)hinzuzufügen.|
|Sie benötigen die Kontrolle über die Verschlüsselungsschlüssel, die zum Verschlüsseln Ihrer Daten in den Rechenzentren von Microsoft verwendet werden.|Als Office 365-Administrator können Sie die Verschlüsselungsschlüssel Ihrer Organisation steuern und dann Office 365 so konfigurieren, dass sie diese verwenden, um Ihre ruhenden Daten in den Rechenzentren von Microsoft zu verschlüsseln. <p> [Dienstverschlüsselung mit Kundenschlüssel in Office 365](customer-key-overview.md)|
|Personen kommunizieren per E-Mail (Exchange Online)|Als Exchange Online-Administrator haben Sie mehrere Optionen zum Konfigurieren der E-Mail-Verschlüsselung. Zu diesen zählen: <ul><li>Verwenden [Office 365 Nachrichtenverschlüsselung (Message Encryption, OME)](set-up-new-message-encryption-capabilities.md) mit Azure Rights Management (Azure RMS), um Benutzern das Senden verschlüsselter Nachrichten innerhalb oder außerhalb Ihrer Organisation zu ermöglichen</li><li>Verwenden von [S/MIME](/exchange/security-and-compliance/smime-exo/smime-exo) zum Verschlüsseln und digitalen Signieren von E-Mail-Nachrichten</li><li>Verwenden von TLS zum [Einrichten von Connectors für den sicheren Nachrichtenfluss mit einer anderen Organisation](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)</li></ul> <p> Siehe [E-Mail-Verschlüsselung in Office 365](./email-encryption.md).|
|Auf Dateien wird von Teamwebsites oder Dokumentbibliotheken (OneDrive for Business oder SharePoint Online) zugegriffen.|Wenn Personen mit Dateien arbeiten, die in OneDrive for Business oder SharePoint Online gespeichert sind, werden TLS-Verbindungen verwendet. Dies ist automatisch in Office 365 integriert. Siehe [Datenverschlüsselung in OneDrive for Business und SharePoint Online.](./data-encryption-in-odb-and-spo.md)|
|Dateien werden in Onlinebesprechungen und Chatunterhaltungen (Skype for Business Online) freigegeben.|Wenn Benutzer mit Dateien arbeiten, die Skype for Business Online verwenden, wird TLS für die Verbindung verwendet. Dies ist automatisch in Office 365 integriert. Siehe [Sicherheit und Archivierung (Skype for Business Online).](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)|
|Dateien werden in Onlinebesprechungen und Chatunterhaltungen freigegeben (Microsoft Teams)|Wenn Personen mit Dateien arbeiten, die Microsoft Teams verwenden, wird TLS für die Verbindung verwendet. Dies ist automatisch in Office 365 integriert. Microsoft Teams unterstützt derzeit das Inlinerendering verschlüsselter E-Mails nicht. Um zu verhindern, dass verschlüsselte E-Mails in Microsoft Teams als verschlüsselt landen, lesen Sie [häufig gestellte Fragen zur Nachrichtenverschlüsselung.](./ome-faq.yml#can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail-)|
|

## <a name="additional-information"></a>Weitere Informationen

Weitere Informationen zu Dateischutzlösungen, die Verschlüsselungsoptionen enthalten, finden Sie [unter "Lösungen zum Schutz](https://www.microsoft.com/download/details.aspx?id=55523)von Dateien" in Office 365 .
