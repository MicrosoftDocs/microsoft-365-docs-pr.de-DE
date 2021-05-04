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
description: Bei Office 365 werden einige Verschlüsselungsfunktionen standardmäßig aktiviert. Andere Funktionen können so konfiguriert werden, dass bestimmte Compliance- oder gesetzliche Anforderungen erfüllt werden.
ms.openlocfilehash: f126e429e2c4601531ea419267c3a54a95bd76b4
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876314"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>Einrichten von Verschlüsselung in Office 365 Enterprise

Verschlüsselung kann verhindern, dass Ihre Inhalte von nicht autorisierten Benutzern gelesen werden. Da [die Verschlüsselung in Office 365](encryption.md) verschiedenen Technologien und Methoden durchgeführt werden kann, gibt es keinen einzigen Ort, an dem Sie die Verschlüsselung aktivieren oder einrichten. Dieser Artikel enthält Informationen zu verschiedenen Möglichkeiten zum Einrichten oder Konfigurieren der Verschlüsselung im Rahmen Ihrer Strategie zum Schutz von Informationen.
  
> [!TIP]
> Weitere technische Details zur Verschlüsselung finden Sie unter [Technical reference details about encryption in Office 365](technical-reference-details-about-encryption.md).
  
Bei Office 365 sind standardmäßig mehrere Verschlüsselungsfunktionen verfügbar. Zusätzliche Verschlüsselungsfunktionen können so konfiguriert werden, dass bestimmte Compliance- oder gesetzliche Anforderungen erfüllt werden. In der folgenden Tabelle werden verschiedene Verschlüsselungsmethoden für verschiedene Szenarien beschrieben.
  
|**Szenario**|**Verschlüsselungsmethoden**|
|:-----|:-----|
|Dateien werden auf Windows gespeichert  <br/> |Die Verschlüsselung auf Computerebene kann mithilfe von BitLocker auf Windows werden. Als Unternehmensadministrator oder IT-Pro können Sie dies mit dem Microsoft Deployment Toolkit (MDT) einrichten. Weitere Informationen finden Sie unter Einrichten [von MDT BitLocker](/windows/deployment/deploy-windows-mdt/set-up-mdt-for-bitlocker).  <br/> |
|Dateien werden auf mobilen Geräten gespeichert  <br/> |Einige Arten von mobilen Geräten verschlüsseln Dateien, die standardmäßig auf diesen Geräten gespeichert werden. Mit [Funktionen von integrierten](https://support.microsoft.com/en-us/office/capabilities-of-built-in-mobile-device-management-for-microsoft-365-a1da44e5-7475-4992-be91-9ccec25905b0)Verwaltung mobiler Geräte für Office 365 können Sie Richtlinien festlegen, die bestimmen, ob mobile Geräte auf Daten in einem Office 365. Sie können z. B. eine Richtlinie festlegen, die nur Geräten, die Inhalte verschlüsseln, den Zugriff auf Office 365 ermöglicht. Weitere [Informationen finden Sie unter Erstellen und Bereitstellen von Gerätesicherheitsrichtlinien](https://support.microsoft.com/office/create-and-deploy-device-security-policies-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6).  <br/> Um zusätzliche Kontrolle darüber zu erhalten, wie mobile Geräte mit Office 365 interagieren, können Sie das [Hinzufügen](/mem/intune/fundamentals/setup-steps)von Microsoft Intune.  <br/> |
|Sie benötigen Kontrolle über die Verschlüsselungsschlüssel, die zum Verschlüsseln Ihrer Daten in Den Rechenzentren von Microsoft verwendet werden.  <br/> | Als Office 365 können Sie die Verschlüsselungsschlüssel Ihrer Organisation steuern und dann Office 365 so konfigurieren, dass sie ihre Ruhedaten in den Rechenzentren von Microsoft verschlüsseln.  <br/> [Dienstverschlüsselung mit Kundenschlüssel in Office 365](customer-key-overview.md) <br/> |
|Personen kommunizieren per E-Mail (Exchange Online)  <br/> | Als Exchange Online haben Sie mehrere Optionen zum Konfigurieren der E-Mail-Verschlüsselung. Zu diesen zählen:  <br/>  Verwenden [Office 365 Nachrichtenverschlüsselung (OME)](set-up-new-message-encryption-capabilities.md) mit Azure Rights Management (Azure RMS), um Benutzern das Senden verschlüsselter Nachrichten innerhalb oder außerhalb Ihrer Organisation zu ermöglichen  <br/>  Verwenden [von S/MIME für die Nachrichtensignierung und -verschlüsselung](../security/office-365-security/s-mime-for-message-signing-and-encryption.md) zum Verschlüsseln und digitalen Signieren von E-Mail-Nachrichten  <br/>  Einrichten von Connectors [für den](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner) sicheren Nachrichtenfluss mit einer anderen Organisation mithilfe von TLS <br/>  Siehe [E-Mail-Verschlüsselung in Office 365](./email-encryption.md).  <br/> |
|Auf Dateien wird über Teamwebsites oder Dokumentbibliotheken zugegriffen (OneDrive for Business oder SharePoint Online)  <br/> |Wenn Personen mit Dateien arbeiten, die in OneDrive for Business oder SharePoint Online gespeichert sind, werden TLS-Verbindungen verwendet. Dies ist automatisch in Office 365 integrierte. Weitere [Informationen finden Sie unter Datenverschlüsselung in OneDrive for Business und SharePoint Online](./data-encryption-in-odb-and-spo.md).  <br/> |
|Dateien werden in Onlinebesprechungen und Chatunterhaltungen freigegeben (Skype for Business Online)  <br/> |Wenn Personen mit Dateien arbeiten, die Skype for Business Online verwenden, wird TLS für die Verbindung verwendet. Dies ist automatisch in Office 365 integrierte. Weitere [Informationen finden Sie unter Security and Archiving (Skype for Business Online).](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)  <br/> |
|Dateien werden in Onlinebesprechungen und Chatunterhaltungen freigegeben (Microsoft Teams)  <br/> |Wenn Personen mit Dateien arbeiten, die Microsoft Teams, wird TLS für die Verbindung verwendet. Dies ist automatisch in Office 365 integrierte. Microsoft Teams unterstützt derzeit keine Inlinewiedergabe verschlüsselter E-Mails. Informationen zum Verhindern, dass verschlüsselte E-Mails in Microsoft Teams wie verschlüsselt landen, finden Sie unter Häufig gestellte Fragen [zur Nachrichtenverschlüsselung](./ome-faq.yml?view=o365-worldwide&preserve-view=true#can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail-).  <br/> 

## <a name="additional-information"></a>Weitere Informationen

Weitere Informationen zu Dateischutzlösungen, die Verschlüsselungsoptionen enthalten, finden Sie unter [File Protection Solutions in Office 365](https://www.microsoft.com/download/details.aspx?id=55523).
