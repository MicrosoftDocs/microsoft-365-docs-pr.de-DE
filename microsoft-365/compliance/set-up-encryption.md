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
description: Bei Office 365 sind einige Verschlüsselungsfunktionen standardmäßig aktiviert. andere Funktionen können so konfiguriert werden, dass bestimmte Compliance-oder gesetzliche Anforderungen erfüllt werden.
ms.openlocfilehash: bce7487f1cb57c04e262f068ea7e192808e43e8a
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943476"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>Einrichten von Verschlüsselung in Office 365 Enterprise

Durch die Verschlüsselung kann verhindert werden, dass Ihre Inhalte von nicht autorisierten Benutzern gelesen werden. Da die [Verschlüsselung in Office 365](encryption.md) mithilfe verschiedener Technologien und Methoden erfolgen kann, gibt es keine einzige Stelle, an der Sie die Verschlüsselung aktivieren oder einrichten. Dieser Artikel enthält Informationen zu verschiedenen Möglichkeiten zum Einrichten oder Konfigurieren der Verschlüsselung im Rahmen ihrer Informationsschutz Strategie.
  
> [!TIP]
> Wenn Sie weitere technische Details zur Verschlüsselung benötigen, lesen Sie [technische Referenzdetails zur Verschlüsselung in Office 365](technical-reference-details-about-encryption.md).
  
Mit Office 365 stehen standardmäßig mehrere Verschlüsselungsfunktionen zur Verfügung. Zusätzliche Verschlüsselungsfunktionen können so konfiguriert werden, dass bestimmte Compliance-oder gesetzliche Anforderungen erfüllt werden. In der folgenden Tabelle werden verschiedene Verschlüsselungsmethoden für verschiedene Szenarien beschrieben.
  
|**Szenario**|**Verschlüsselungsmethoden**|
|:-----|:-----|
|Dateien werden auf Windows-Computern gespeichert  <br/> |Die Verschlüsselung auf Computerebene kann mithilfe von BitLocker auf Windows-Geräten erfolgen. Als Unternehmensadministrator oder IT-Experte können Sie dies mit dem Microsoft Deployment Toolkit (MDT) einrichten. Weitere Informationen finden Sie unter [Einrichten von MDT für BitLocker](https://go.microsoft.com/fwlink/?linkid=849282).  <br/> |
|Dateien werden auf mobilen Geräten gespeichert  <br/> |Einige Arten von mobilen Geräten verschlüsseln Dateien, die standardmäßig auf diesen Geräten gespeichert werden. Mit [Funktionen der integrierten Verwaltung mobiler Geräte für Office 365](https://support.office.com/article/a1da44e5-7475-4992-be91-9ccec25905b0)können Sie Richtlinien festlegen, die bestimmen, ob mobile Geräte auf Daten in Office 365 zugreifen dürfen. Sie können beispielsweise eine Richtlinie festlegen, mit der nur Geräte, die Inhalte verschlüsseln, auf Office 365 Daten zugreifen können. Weitere Informationen finden Sie unter [Erstellen und Bereitstellen von Gerätesicherheitsrichtlinien](https://support.office.com/article/d310f556-8bfb-497b-9bd7-fe3c36ea2fd6).  <br/> Für eine zusätzliche Kontrolle darüber, wie mobile Geräte mit Office 365 interagieren, können Sie das Hinzufügen von [Microsoft InTune](https://docs.microsoft.com/mem/intune/fundamentals/setup-steps)in Frage stellen.  <br/> |
|Sie benötigen die Kontrolle über die Verschlüsselungsschlüssel, die zum Verschlüsseln Ihrer Daten in den Microsoft-Rechenzentren verwendet werden.  <br/> | Als Office 365 Administrator können Sie die Verschlüsselungsschlüssel in Ihrer Organisation steuern und dann Office 365 so konfigurieren, dass Sie zum Verschlüsseln Ihrer Daten im Ruhezustand in den Microsoft-Rechenzentren verwendet werden.  <br/> [Dienstverschlüsselung mit Kundenschlüssel in Office 365](customer-key-overview.md) <br/> |
|Personen kommunizieren per e-Mail (Exchange Online)  <br/> | Als Exchange Online Administrator haben Sie mehrere Optionen zum Konfigurieren der e-Mail-Verschlüsselung. Zu diesen zählen:  <br/>  Verwenden [Office 365 Nachrichtenverschlüsselung (OM)](set-up-new-message-encryption-capabilities.md) mit Azure Rights Management (Azure RMS), damit Personen verschlüsselte Nachrichten innerhalb oder außerhalb Ihrer Organisation senden können  <br/>  Verwenden [von S/MIME für die Nachrichtensignierung und-Verschlüsselung](https://aka.ms/c6dozg) zum Verschlüsseln und digitalen Signieren von e-Mail-Nachrichten  <br/>  Verwenden von TLS zum [Einrichten von Connectors für den sicheren e-Mail-Fluss mit einer anderen Organisation](https://aka.ms/hs809p) <br/>  Siehe [e-Mail-Verschlüsselung in Office 365](https://aka.ms/hic3f7).  <br/> |
|Auf Dateien wird von Teamwebsites oder Dokumentbibliotheken (OneDrive für Unternehmen oder SharePoint Online) zugegriffen.  <br/> |Wenn Benutzer mit Dateien arbeiten, die in OneDrive für Unternehmen oder SharePoint Online gespeichert sind, werden TLS-Verbindungen verwendet. Dieser wird automatisch in Office 365 integriert. Siehe [Datenverschlüsselung in OneDrive für Unternehmen und SharePoint Online](https://go.microsoft.com/fwlink/?linkid=526379).  <br/> |
|Dateien werden in Onlinebesprechungen und Chat Unterhaltungen (Skype for Business Online) freigegeben.  <br/> |Wenn Benutzer mit Dateien mit Skype for Business Online arbeiten, wird TLS für die Verbindung verwendet. Dieser wird automatisch in Office 365 integriert. Siehe [Sicherheit und Archivierung (Skype for Business Online)](https://aka.ms/nuq4ws).  <br/> |

## <a name="additional-information"></a>Weitere Informationen

Weitere Informationen zu Dateischutz Lösungen, die Verschlüsselungsoptionen enthalten, finden Sie unter [File Protection Solutions in Office 365](https://www.microsoft.com/download/details.aspx?id=55523).
 
