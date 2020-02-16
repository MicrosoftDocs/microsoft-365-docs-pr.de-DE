---
title: Office 365 Bedrohungs Ermittlungs-und-Antwortfunktionen in Office 365 Advanced Threat Protection-Plan 2
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/09/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 32405da5-bee1-4a4b-82e5-8399df94c512
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie Sie mithilfe von Threat Intelligence-Funktionen in Office 365 Advanced Threat Protection Sicherheitsrisiken in Ihrer Organisation erforschen, auf Schadsoftware, Phishing und andere Angriffe reagieren können, die Office 365 in Ihrem Namen erkannt hat, und nach Bedrohungen suchen. Indikatoren.
ms.openlocfilehash: 4bd23dcafeed2faf04979b2c757d5517073a210d
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42082488"
---
# <a name="office-365-threat-investigation-and-response"></a>Untersuchung von und Antwort auf Bedrohungen in Office 365

Untersuchung und Antwortfunktionen für Bedrohungen in [Office 365 Advanced Threat Protection](office-365-atp.md) helfen Sicherheitsanalysten und Administratoren, die Office 365 Benutzer Ihrer Organisation zu schützen, indem Sie:
- Vereinfachen der Identifizierung, Überwachung und Verständlichkeit von Cyberangriffe
- Unterstützung bei der schnellen Adressierung von Bedrohungen in Exchange Online, SharePoint Online, OneDrive für Unternehmen und Microsoft Teams
- Bereitstellen von Einblicken und Wissen zur Unterstützung von Sicherheitsmaßnahmen beim verhindern von Cyberangriffe in Ihrer Organisation
- Einsatz von [automatisierten Untersuchungen und Antworten in Office 365](automated-investigation-response-office.md) für wichtige e-Mail-basierte Bedrohungen
    
Die Funktionen zur Ermittlung und Reaktion von Bedrohungen bieten Einblicke in Bedrohungen und zugehörige Reaktions Aktionen, die &amp; im Office 365 Security Compliance Center verfügbar sind. Diese Erkenntnisse können dazu beitragen, dass das Sicherheitsteam Ihrer Organisation Office 365 Benutzer vor e-Mail-oder dateibasierten Angriffen schützt. Die Funktionen helfen bei der Überwachung von Signalen und Sammeln von Daten aus mehreren Quellen wie Benutzeraktivität, Authentifizierung, e-Mail, kompromittierten PCs und Sicherheitsvorfällen. Geschäfts Entscheidungsträger und Ihr Sicherheits Betriebsteam können diese Informationen verwenden, um Bedrohungen Ihrer Organisation zu verstehen und zu reagieren und Ihr geistiges Eigentum zu schützen.

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a>Kennenlernen von Bedrohungs Ermittlungs-und-Antwort Tools

Die Funktionen zur Ermittlung und Reaktion auf Bedrohungen werden &amp; im Security Compliance Center als eine Reihe von Tools und Antwort Workflows angezeigt, einschließlich der folgenden:
- [Threat-Dashboard](#threat-dashboard)
- [Explorer](#threat-explorer)
- [Vorfälle](#incidents)
- [Angriffssimulator](#attack-simulator)
- [Automatische Untersuchung und Reaktion](automated-investigation-response-office.md)

### <a name="threat-dashboard"></a>Threat-Dashboard

Verwenden Sie das Threat-Dashboard (Dies wird auch als [Sicherheits Dashboard](security-dashboard.md)bezeichnet), um schnell zu sehen, welche Bedrohungen angesprochen wurden, und als visuelle Möglichkeit, um Geschäfts Entscheidungsträgern zu berichten, wie Office 365 Dienste Ihr Unternehmen schützen.
  
![Threat-Dashboard](../../media/ce013a31-3f80-4d09-bb95-bfb7623b8bc4.png)
  
Um dieses Dashboard anzuzeigen und zu verwenden, wechseln Sie im &amp; Office 365 Security Compliance Center zu **Threat Management** \> **Dashboard**.
  
### <a name="threat-explorer"></a>Sicherheitsrisiken-Explorer

Verwenden Sie [Threat Explorer (und Echtzeiterkennung)](threat-explorer.md) , um Bedrohungen zu analysieren, die Anzahl der Angriffe über einen bestimmten Zeitraum zu ermitteln und Daten nach Bedrohungs Familien, Angreifer-Infrastruktur und vielem mehr zu analysieren. Threat Explorer (auch als Explorer bezeichnet) ist der Ausgangspunkt für den unter Such Workflow eines Sicherheitsanalysten.
  
![Bedrohungs-Explorer](../../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)
  
Um diesen Bericht anzuzeigen und zu verwenden, wechseln Sie im &amp; Office 365 Security Compliance Center zu **Threat Management** \> **Explorer**.
  
### <a name="incidents"></a>Vorfälle

Verwenden Sie die Liste Vorfälle (Dies wird auch Untersuchungen genannt), um eine Liste der in Flight-Sicherheitsvorfälle anzuzeigen. Vorfälle werden verwendet, um Bedrohungen wie verdächtige e-Mail-Nachrichten nachzuverfolgen und weitere Untersuchungen und Korrekturen durchzuführen.
  
![Liste der aktuellen Bedrohungs Vorfälle in Office 365](../../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)
  
Um die Liste der aktuellen Vorfälle für Ihre Organisation anzuzeigen, wechseln Sie &amp; im Security Compliance Center zu **Threat Management** \> **Review** \> **Incidents**.
  
![Wählen Sie im &amp; Security Compliance Center die Option Threat \> Management Review aus.](../../media/e0f46454-fa38-40f0-a120-b595614d1d22.png)

### <a name="attack-simulator"></a>Angriffssimulator

Verwenden Sie den Angriffs Simulator zum Einrichten und ausführen realistischer Cyberangriffe in Ihrer Organisation, und identifizieren Sie gefährdete Personen, bevor sich ein echter Cyberangriff auf Ihr Unternehmen auswirkt. Weitere Informationen finden Sie unter [Attack Simulator in Office 365](attack-simulator.md).

### <a name="automated-investigation-and-response"></a>Automatische Untersuchung und Reaktion

Verwenden Sie automatisierte Ermittlungs-und Antwortfunktionen (Air), um Zeit und Aufwand beim Korrelieren von Inhalten, Geräten und gefährdeten Personen vor Bedrohungen in Ihrer Organisation zu sparen. Air-Prozesse können beginnen, wenn bestimmte Warnungen ausgelöst werden oder wenn Sie von Ihrem Sicherheits Betriebsteam gestartet werden. Weitere Informationen finden Sie unter [Automatische Untersuchung und Antwort in Office 365](automated-investigation-response-office.md). 
  
## <a name="threat-intelligence-widgets"></a>Threat Intelligence-Widgets

Im Rahmen des Angebots von Office 365 Advanced Threat Protection Plan 2 können Sicherheitsanalysten Details zu einer bekannten Bedrohung überprüfen. Dies ist hilfreich, um zu ermitteln, ob zusätzliche vorbeugende Maßnahmen/Schritte ergriffen werden können, um die Benutzer zu schützen.
  
![Sicherheits Trends mit Informationen zu aktuellen Bedrohungen](../../media/11e7d40d-139b-4c56-8d52-c091c8654151.png) 
  
## <a name="how-do-we-get-these-capabilities"></a>Wie erhalten wir diese Funktionen?

Office 365 Threat-Ermittlungs-und-Antwortfunktionen sind in Office 365 Advanced Threat Protection Plan 2 enthalten, der in Enterprise E5 oder als Add-on für bestimmte Abonnements enthalten ist. Weitere Informationen finden Sie unter [Office 365 ATP-Plan 1 und Plan 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2).

## <a name="required-roles-and-permissions"></a>Erforderliche Rollen und Berechtigungen

Office 365 Advanced Threat Protection verwendet rollenbasierte Zugriffssteuerung. Berechtigungen werden über bestimmte Rollen in Azure Active Directory, dem Microsoft 365 Admin Center oder dem Office 365 Security & Compliance Center zugewiesen.

> [!TIP]
> Obwohl einige Rollen, wie etwa der Sicherheits Administrator, im Office 365 Security & Compliance Center zugewiesen werden können, sollten Sie stattdessen entweder das Microsoft 365 Admin Center oder Azure Active Directory verwenden. Informationen zu Rollen, Rollengruppen und Berechtigungen finden Sie in den folgenden Ressourcen:
> - [Berechtigungen im Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)
> - [Administratorrollenberechtigungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)


|Aktivität |Rollen und Berechtigungen |  
|:-----|:-----|
|Verwenden des Threat-Dashboards (oder des neuen [Sicherheits Dashboards](security-dashboard.md))<br/> <br/>Anzeigen von Informationen zu aktuellen oder aktuellen Bedrohungen  <br/> |Eine der folgenden Varianten: <br/>- **Office 365 globaler Administrator**  <br/> - **Sicherheits Administrator** <br/>- **Sicherheits Leser** <br/> <br/>Diese Rollen können entweder in Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) oder im Microsoft 365 Admin Center ([https://admin.microsoft.com](https://admin.microsoft.com)) zugewiesen werden. |
|Verwenden von [Threat Explorer (und Echtzeiterkennung)](threat-explorer.md) zum Analysieren von Bedrohungen  <br/> |Eine der folgenden Varianten: <br/>- **Office 365 globaler Administrator**  <br/> - **Sicherheits Administrator** <br/>- **Sicherheits Leser** <br/> <br/>Diese Rollen können entweder in Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) oder im Microsoft 365 Admin Center ([https://admin.microsoft.com](https://admin.microsoft.com)) zugewiesen werden. |
|Anzeigen von Vorfällen (auch Untersuchungen genannt) <br/> Hinzufügen von e-Mail-Nachrichten zu einem Vorfall  <br/> |Eine der folgenden Varianten: <br/>- **Office 365 globaler Administrator**  <br/> - **Sicherheits Administrator** <br/>- **Sicherheits Leser** <br/> <br/>Diese Rollen können entweder in Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) oder im Microsoft 365 Admin Center ([https://admin.microsoft.com](https://admin.microsoft.com)) zugewiesen werden.  |
|Auslösen von e-Mail-Aktionen in einem Vorfall <br/> <br/> Suchen und Löschen von verdächtigen e-Mail-Nachrichten  <br/> |Eine der folgenden Varianten: <br/>- **Office 365 globaler Administrator**  <br/> - **Sicherheits Administrator** plus die **Such-und Lösch** Rolle<br/><br/>Die **globalen Administrator** -und **Sicherheitsadministrator** Rollen können entweder in Azure Active Directory ([https://portal.azure.com](https://portal.azure.com)) oder im Microsoft 365 Admin Center ([https://admin.microsoft.com](https://admin.microsoft.com)) zugewiesen werden. <br/><br/>Die **Such-und Lösch** Rolle muss im Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) zugewiesen werden. |
|Integration von Office 365 Advanced Threat Protection Plan 2 mit Advanced Threat Protection von Microsoft Defender  <br/><br/> Integrieren von Office 365 Advanced Threat Protection Plan 2 mit einem Siem-Server  <br/> |Entweder der **Office 365 globale Administrator** oder die **Sicherheitsadministrator** Rolle, die entweder in Azure Active Directory[https://portal.azure.com](https://portal.azure.com)() oder im Microsoft 365 Admin Center[https://admin.microsoft.com](https://admin.microsoft.com)() zugewiesen ist.<br/>--- **Plus** ---<br/>Eine entsprechende Rolle, die in weiteren Anwendungen zugewiesen ist (beispielsweise [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles) oder Ihr Siem-Server)  |
   
    
## <a name="next-steps"></a>Nächste Schritte

- [Informationen zu Threat Tracker – neu und bemerkenswert](threat-trackers.md)
    
- [Suchen und untersuchen schädlicher e-Mails, die zugestellt wurden (Office 365 Untersuchung und Reaktion auf Bedrohungen)](investigate-malicious-email-that-was-delivered.md)
    
- [Integrieren von Office 365 Bedrohungs Ermittlung und-Reaktion mit Microsoft Defender Advanced Threat Protection](integrate-office-365-ti-with-wdatp.md)
    
- [Informationen zum Angriffs Simulator](attack-simulator.md)
  

