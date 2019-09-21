---
title: Anzeigen von Berichten für Office 365 Advanced Threat Protection
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 05/21/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
description: Hier erfahren Sie, wie Sie Berichte für Office 365 Advanced Threat Protection im Security &amp; Compliance Center finden und verwenden können.
ms.openlocfilehash: d5f0958d199684a9d6ca6bfe4ed01c0ab9102a2a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082715"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a>Anzeigen von Berichten für Office 365 Advanced Threat Protection

Wenn Ihre Organisation über [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) verfügt und Sie über die [erforderlichen Berechtigungen](#what-permissions-are-needed-to-view-the-atp-reports)verfügen, können Sie mehrere ATP-Berichte im &amp; Security Compliance Center verwenden. (Wechseln Sie zum **Dashboard** **Berichte** \> .)
  
![Das Security &amp; Compliance Center-Dashboard hilft Ihnen, zu sehen, wo Advanced Threat Protection funktioniert.](../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
Zu den ATP-Berichten zählen folgende:
- [Status Bericht über den Bedrohungsschutz](#threat-protection-status-report)
- [Bericht "ATP-Dateitypen"](#atp-file-types-report)
- [Bericht zur ATP-Nachrichten Disposition](#atp-message-disposition-report)
- entweder [Echtzeiterkennung oder Explorer](threat-explorer.md) (je nachdem, ob Sie Office 365 ATP-Plan 1 oder 2 haben)
- ... [und vieles mehr](#additional-reports-to-view). 

Lesen Sie diesen Artikel, um eine Übersicht über ATP-Berichte und deren Verwendung zu erhalten.
  
## <a name="threat-protection-status-report"></a>Status Bericht über den Bedrohungsschutz

Der **Status Bericht "Threat Protection** " ist eine einzelne Ansicht, in der Informationen zu böswilligen Inhalten und böswilligen e-Mails zusammengefasst werden, die durch [Exchange Online Schutz](exchange-online-protection-overview.md) (EoP) und [Office 365 ATP](office-365-atp.md)erkannt und blockiert wurden. Dieser Bericht eignet sich zum Anzeigen von Erkennungen im Laufe der Zeit (bis zu 90 Tage) und ermöglicht es Sicherheitsadministratoren, Trends zu identifizieren oder zu bestimmen, ob Richtlinien angepasst werden müssen. 

Der Status Bericht zum Bedrohungsschutz enthält eine aggregierte Anzahl von eindeutigen e-Mail-Nachrichten mit bösartigen Inhalten wie Dateien oder Websiteadressen (URLs), die von der Antischadsoftware-Engine, der [automatischen Säuberungs-Funktion (zap)](zero-hour-auto-purge.md)und den ATP-Funktionen wie [ATP-sichere Links](atp-safe-links.md), [ATP-sichere Anhänge](atp-safe-attachments.md)und [ATP-Anti-Phishing-Funktionen](atp-anti-phishing.md). 

> [!NOTE]
> Ein Status Bericht über den Bedrohungsschutz steht Kunden zur Verfügung, die entweder [Office 365 ATP](office-365-atp.md) oder [Exchange Online Protection](exchange-online-protection-eop.md) (EoP) haben; die Informationen, die im Threat Protection-Status Bericht für ATP-Kunden angezeigt werden, enthalten jedoch wahrscheinlich unterschiedliche Daten, als EoP-Kunden möglicherweise sehen. Der Threat Protection-Status Bericht für ATP-Kunden enthält beispielsweise Informationen zu [schädlichen Dateien, die in SharePoint Online, OneDrive oder Microsoft Teams erkannt](atp-for-spo-odb-and-teams.md)wurden. Solche Informationen gelten nur für ATP, sodass Kunden, die über EoP, aber nicht ATP verfügen, diese Details nicht in Ihrem Threat Protection-Status Bericht sehen.
  
Wechseln Sie zum Anzeigen des Statusberichts für den Bedrohungsschutz im [ &amp; Security Compliance Center](https://protection.office.com)zu **Reports** \> **Dashboard** \> **Threat Protection Status**.
  
![Status Bericht über den ATP-Bedrohungsschutz](../media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
Wenn Sie einen detaillierten Status für einen Tag erhalten möchten, zeigen Sie mit der Maus auf das Diagramm.
  
![Status Daten für den ATP-Bedrohungsschutz für einen Tag](../media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
Standardmäßig zeigt der Status Bericht zum Bedrohungsschutz Daten für die letzten sieben Tage an. Sie können jedoch **Filter** auswählen und den Datumsbereich ändern, um Daten für bis zu 90 Tage anzuzeigen. (Wenn Sie ein Testabonnement verwenden, sind die Daten möglicherweise auf 30 Tage eingeschränkt.)
  
![Status Filter für den ATP-Bedrohungsschutz](../media/4f703369-642b-402b-9758-b9c828283410.png)
  
Sie können auch das Menü " **Daten anzeigen nach** " verwenden, um zu ändern, welche Informationen im Bericht angezeigt werden. 
  
![Anzeigen von Optionen für den Status Bericht für den ATP-Bedrohungsschutz](../media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## <a name="atp-file-types-report"></a>Bericht "ATP-Dateitypen"

Der Bericht " **ATP-Dateitypen** " zeigt Ihnen den Typ der Dateien, die von [ATP-Safe-Anlagen](atp-safe-attachments.md)als bösartig erkannt wurden.
  
Um diesen Bericht anzuzeigen, wechseln Sie [im &amp; Security Compliance Center](https://protection.office.com)zu **Reports** \> **Dashboard** \> **ATP-Dateitypen**.
  
![Bericht "ATP-Dateitypen"](../media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
Wenn Sie den Mauszeiger über einen bestimmten Tag bewegen, sehen Sie die Aufschlüsselung der Typen von bösartigen Dateien, die durch [ATP-sichere Anlagen](atp-safe-attachments.md) und [Anti &amp; -Spam-Schutz vor Schadsoftware in Office 365](anti-spam-and-anti-malware-protection.md)erkannt wurden.
  
![ATP-Dateitypen-Berichtsdaten für einen Tag](../media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a>Bericht zur ATP-Nachrichten Disposition

Der Bericht " **ATP-Nachrichten Disposition** " zeigt die Aktionen an, die für e-Mail-Nachrichten durchgeführt wurden, die als schädliche Inhalte erkannt wurden. 
  
Um diesen Bericht anzuzeigen, wechseln Sie [im &amp; Security Compliance Center](https://protection.office.com)zu **Berichte** \> **-Dashboard** \> **ATP-Nachrichten Disposition**.
  
![Bericht zur ATP-Nachrichten Disposition](../media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
Wenn Sie mit dem Mauszeiger auf einen Balken im Diagramm zeigen, können Sie sehen, welche Aktionen für erkannte e-Mails an diesem Tag ausgeführt wurden.
  
![ATP-Nachrichten Dispositions-Berichtsdaten für einen Tag](../media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a>Zusätzliche Berichte zur Anzeige

Zusätzlich zu den in diesem Artikel beschriebenen ATP-Berichten stehen verschiedene andere Berichte zur Verfügung, wie in der folgenden Tabelle beschrieben:

|Bericht (e)  |Details  |
|---------|---------|
|**Explorer** oder **Echtzeiterkennung** (Office 365 ATP-Plan 2-Kunden haben Explorer; Office 365 ATP-Plan 1 haben Kunden Echt Zeit Erkennungen.)| [Threat Explorer (und Echtzeiterkennung)](threat-explorer.md)       |
|**E-Mail-Sicherheitsberichte**wie ein Bericht über die wichtigsten Absender und Empfänger, ein spoof-e-Mail-Bericht und ein Spam Erkennungs Bericht. | [Anzeigen von e-Mail-Sicherheits &amp; Berichten im Security Compliance Center](../../compliance/view-email-security-reports.md)        |
|**URL-Ablaufverfolgung für ATP-sichere Links** (Dies ist ein Bericht, den Sie mithilfe von PowerShell generieren.) In diesem Bericht werden die Ergebnisse der Aktionen für ATP-sichere Links in den letzten sieben (7) Tagen dargestellt. |[Get-UrlTrace-Cmdlet-Referenz](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-urltrace?view=exchange-ps) |
|**EoP und ATP-Ergebnisse** (Dies ist ein benutzerdefinierter Bericht, den Sie mithilfe von PowerShell generieren). Dieser Bericht enthält Informationen wie Domäne, Datum, Ereignistyp, Richtung, Aktion und Nachrichtenanzahl.  | [Get-MailTrafficATPReport-Cmdlet-Referenz](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport?view=exchange-ps) |
|**EoP und ATP-Erkennungen** (Dies ist ein benutzerdefinierter Bericht, den Sie mithilfe von PowerShell generieren). Dieser Bericht enthält Details zu bösartigen Dateien oder URLs, Phishing-versuchen, Identitätswechsel und anderen potenziellen Bedrohungen in e-Mails oder Dateien.   | [Get-MailDetailATPReport-Cmdlet-Referenz](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport?view=exchange-ps)        |

  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a>Welche Berechtigungen sind zum Anzeigen der ATP-Berichte erforderlich?

Damit Sie die in diesem Artikel beschriebenen Berichte anzeigen und verwenden können, **muss Ihnen eine entsprechende Rolle sowohl für das Security &amp; Compliance Center als auch für das Exchange Admin Center zugewiesen sein**.

- Für das Security &amp; Compliance Center müssen Sie eine der folgenden Rollen zugewiesen haben:
    - Organisationsverwaltung
    - Sicherheits Administrator (Dies kann im Azure Active Directory Admin Center zugewiesen werden ([https://aad.portal.azure.com](https://aad.portal.azure.com)))
    - Sicherheits Leser

- Für Exchange Online müssen Sie eine der folgenden Rollen entweder in der Exchange-Verwaltungskonsole ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) oder mit PowerShell-Cmdlets zugewiesen haben (siehe [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):
    - Organisationsverwaltung
    - Organisationsverwaltung mit Leserechten
    - Rolle „Empfänger mit Leserechten“
    - Verwaltung der Richtlinientreue

Weitere Informationen finden Sie in den folgenden Ressourcen:

- [Berechtigungen im Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)

- [Featureberechtigungen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
## <a name="what-if-the-reports-arent-showing-data"></a>Was geschieht, wenn die Berichte keine Daten anzeigen?

Wenn Sie keine Daten in ihren ATP-Berichten sehen, überprüfen Sie, ob Ihre Richtlinien ordnungsgemäß eingerichtet sind. In Ihrer Organisation müssen Richtlinien für [ATP-sichere Links](set-up-atp-safe-links-policies.md) und [ATP-Richtlinien für sichere Anlagen](set-up-atp-safe-attachments-policies.md) definiert sein, damit ATP-Schutz vorhanden ist. Weitere Informationen finden Sie unter [Anti-Spam and Anti-Malware Protection in Office 365](anti-spam-and-anti-malware-protection.md).
  
## <a name="related-topics"></a>Verwandte Themen

[Berichte und Einblicke im Office 365 &amp; Security Compliance Center](reports-and-insights-in-security-and-compliance.md)
  
[Erstellen eines Zeitplans für einen Bericht im &amp; Security Compliance Center](create-a-schedule-for-a-report.md)
  
[Einrichten und Herunterladen eines benutzerdefinierten Berichts im Security &amp; Compliance Center](set-up-and-download-a-custom-report.md)
  

