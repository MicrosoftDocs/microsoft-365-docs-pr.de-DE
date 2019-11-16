---
title: Untersuchung von und Antwort auf Bedrohungen in Office 365
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 11/15/2019
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
ms.openlocfilehash: 047fb99a32fdd7e86572c5a96370f351da50f139
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673271"
---
# <a name="office-365-threat-investigation-and-response"></a>Untersuchung von und Antwort auf Bedrohungen in Office 365

Untersuchung und Antwortfunktionen für Bedrohungen in [Office 365 Advanced Threat Protection](office-365-atp.md) helfen Sicherheitsanalysten und Administratoren, die Office 365 Benutzer Ihrer Organisation zu schützen, indem Sie:
  
- Einfaches identifizieren, überwachen und verstehen von Cyberangriffe
    
- Unterstützung bei der schnellen Adressierung von Bedrohungen in Exchange Online, SharePoint Online, OneDrive für Unternehmen und Microsoft Teams
    
- Bereitstellen von Einblicken und Wissen zur Unterstützung von Sicherheitsmaßnahmen beim verhindern von Cyberangriffe in Ihrer Organisation

- Einsatz von [automatischer Vorfall Antwort](automated-investigation-response-office.md) für wichtige e-Mail-basierte Bedrohungen
    
Die Funktionen zur Ermittlung und Reaktion von Bedrohungen bieten Einblicke in Bedrohungen und zugehörige Reaktions Aktionen, die &amp; im Office 365 Security Compliance Center verfügbar sind. Diese Erkenntnisse können dazu beitragen, dass das Sicherheitsteam Ihrer Organisation Office 365 Benutzer vor e-Mail-oder dateibasierten Angriffen schützt. Die Funktionen helfen bei der Überwachung von Signalen und Sammeln von Daten aus mehreren Quellen wie Benutzeraktivität, Authentifizierung, e-Mail, kompromittierten PCs und Sicherheitsvorfällen. Entscheidungsträger im Unternehmen und Office 365 globale Administratoren, Sicherheitsadministratoren und Sicherheitsexperten können diese Informationen nutzen, um Bedrohungen gegen Office 365 Benutzer zu verstehen und darauf zu reagieren und geistiges Eigentum zu schützen.

## <a name="get-acquainted-with-threat-investigation-and-response-tools"></a>Kennenlernen von Bedrohungs Ermittlungs-und-Antwort Tools

Die Funktionen "Bedrohungs Ermittlung und-Reaktion &amp; " werden im Security Compliance Center als eine Reihe von Tools und Antwort Workflows, einschließlich des [Threat-Dashboards](#threat-dashboard), des [Explorers](#threat-explorer), der [Vorfälle](#incidents), des [Angriffs Simulators](#attack-simulator)und der [automatischen Vorfall Antwort](automated-investigation-response-office.md), Oberfläche angezeigt.
  
### <a name="threat-dashboard"></a>Threat-Dashboard

Verwenden Sie das Threat-Dashboard (Dies wird auch als [Sicherheits Dashboard](security-dashboard.md)bezeichnet), um schnell zu sehen, welche Bedrohungen angesprochen wurden, und als visuelle Möglichkeit, um Geschäfts Entscheidungsträgern zu berichten, wie Office 365 Dienste Ihr Unternehmen schützen.
  
![Threat-Dashboard](../media/ce013a31-3f80-4d09-bb95-bfb7623b8bc4.png)
  
Um dieses Dashboard anzuzeigen und zu verwenden, wechseln Sie im &amp; Office 365 Security Compliance Center zu **Threat Management** \> **Dashboard**.

Weitere Informationen 
  
### <a name="threat-explorer"></a>Sicherheitsrisiken-Explorer

Verwenden Sie [Threat Explorer (und Echtzeiterkennung)](threat-explorer.md) , um Bedrohungen zu analysieren, die Anzahl der Angriffe über einen bestimmten Zeitraum zu ermitteln und Daten nach Bedrohungs Familien, Angreifer-Infrastruktur und vielem mehr zu analysieren. Threat Explorer (auch als Explorer bezeichnet) ist der Ausgangspunkt für den unter Such Workflow eines Sicherheitsanalysten.
  
![Bedrohungs-Explorer](../media/7a7cecee-17f0-4134-bcb8-7cee3f3c3890.png)
  
Um diesen Bericht anzuzeigen und zu verwenden, wechseln Sie im &amp; Office 365 Security Compliance Center zu **Threat Management** \> **Explorer**.
  
### <a name="incidents"></a>Vorfälle

Verwenden Sie die Liste Vorfälle (Dies wird auch Untersuchungen genannt), um eine Liste der in Flight-Sicherheitsvorfälle anzuzeigen. Vorfälle werden verwendet, um Bedrohungen wie verdächtige e-Mail-Nachrichten nachzuverfolgen und weitere Untersuchungen und Korrekturen durchzuführen.
  
![Liste der aktuellen Bedrohungs Vorfälle in Office 365](../media/acadd4c7-d2de-4146-aeb8-90cfad805a9c.png)
  
Um die Liste der aktuellen Vorfälle für Ihre Organisation anzuzeigen, wechseln Sie &amp; im Security Compliance Center zu **Threat Management** \> **Review** \> **Incidents**.
  
![Wählen Sie im &amp; Security Compliance Center die Option Threat \> Management Review aus.](../media/e0f46454-fa38-40f0-a120-b595614d1d22.png)

### <a name="attack-simulator"></a>Angriffs Simulator

Verwenden Sie den Angriffs Simulator zum Einrichten und ausführen realistischer Cyberangriffe in Ihrer Organisation, und identifizieren Sie gefährdete Personen, bevor sich ein echter Cyberangriff auf Ihr Unternehmen auswirkt. Weitere Informationen finden Sie unter [Attack Simulator in Office 365](attack-simulator.md).

### <a name="automated-investigation-and-response"></a>Automatische Untersuchung und Reaktion

Verwenden Sie automatisierte Ermittlungs-und Antwortfunktionen (Air), um Zeit und Aufwand beim Korrelieren von Inhalten, Geräten und gefährdeten Personen vor Bedrohungen in Ihrer Organisation zu sparen. Air-Prozesse können beginnen, wenn bestimmte Warnungen ausgelöst werden oder wenn Sie von Ihrem Sicherheits Betriebsteam gestartet werden. Weitere Informationen finden Sie unter [Automatische Vorfall Antwort in Office 365](automated-investigation-response-office.md). 
  
## <a name="threat-intelligence-widgets"></a>Threat Intelligence-Widgets

Im Rahmen des Angebots von Office 365 Advanced Threat Protection Plan 2 können Sicherheitsanalysten Details zu einer bekannten Bedrohung überprüfen. Dies ist hilfreich, um zu ermitteln, ob zusätzliche vorbeugende Maßnahmen/Schritte ergriffen werden können, um die Benutzer zu schützen.
  
![Sicherheits Trends mit Informationen zu aktuellen Bedrohungen](../media/11e7d40d-139b-4c56-8d52-c091c8654151.png) 
  
## <a name="how-do-we-get-these-capabilities"></a>Wie erhalten wir diese Funktionen?

In Office 365 Advanced Threat Protection Plan 2 und Enterprise E5 sind Office 365 Funktionen zur Untersuchung und Reaktion von Bedrohungen enthalten. 

> [!TIP]
> Wenn Ihre Organisation über ein Office 365es Abonnement verfügt, das diese Ermittlungs-und Antwortfunktionen für Bedrohungen nicht enthält, können Sie Office 365 Advanced Threat Protection Plan 2 als Add-on möglicherweise erwerben. Weitere Informationen zu Planoptionen finden Sie unter [Office 365 Advanced Threat Protection-Dienstbeschreibung](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) und [kaufen oder Bearbeiten eines Add-ons für Office 365 für Unternehmen](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on).
  
1. Wechseln Sie als globaler Office 365 Administrator zu, [https://admin.microsoft.com](https://admin.microsoft.com) und melden Sie sich mit Ihrem Arbeits-oder Schulkonto für Office 365 an. 
    
2. Wählen Sie **Administrator** \> **Abrechnung** aus, um zu sehen, was Ihr aktuelles Abonnement enthält. 
    - Wenn **Office 365 Enterprise E5**angezeigt wird, verfügt Ihre Organisation über Office 365 Advanced Threat Protection Plan 2 (einschließlich der Untersuchung und Antwortfunktionen für Bedrohungen). 
    - Wenn ein anderes Abonnement wie **Office 365 Enterprise E3** oder **Office 365 Enterprise E1**angezeigt wird, sollten Sie Office 365 Advanced Threat Protection Plan 2 hinzufügen. (Wählen Sie dazu **+ Abonnement hinzufügen**aus.)
    
3. Wählen Sie im Microsoft 365 Admin Center die Option **Users** \> **Active Users**aus.
    
4. Weisen Sie allen aktiven Benutzern Office 365 Advanced Threat Protection-Plan 2-Lizenzen zu. (Nur Benutzer, die über eine Lizenz dafür verfügen, werden in Berichten wie dem Explorer angezeigt.)
    
5. Zuweisen von Rollen zu Personen in Ihrer Organisation, die mit dem Office 365 Advanced Threat Protection arbeiten werden. Weitere Informationen finden Sie unter [Gewähren von Benutzern &amp; Zugriff auf das Office 365 Security Compliance Center](grant-access-to-the-security-and-compliance-center.md)und in der folgenden Tabelle:<br/>

  |**Um diese Aktivität durchführen zu können...** <br/> |**Sie müssen über eine dieser Rollen verfügen.** <br/> |  
  |:-----|:-----|
  |Verwenden des Threat-Dashboards (oder des neuen [Sicherheits Dashboards](security-dashboard.md))<br/> Anzeigen von Informationen zu aktuellen oder aktuellen Bedrohungen  <br/> |Globaler Office 365-Administrator  <br/> Sicherheits Administrator (im Security &amp; Compliance Center zugewiesen)  <br/> Sicherheits Leser (im Security &amp; Compliance Center zugewiesen)  <br/> |
  |Verwenden von [Threat Explorer (und Echtzeiterkennung)](threat-explorer.md) zum Analysieren von Bedrohungen  <br/> |Globaler Office 365-Administrator  <br/> Sicherheits Administrator (im Security &amp; Compliance Center zugewiesen)  <br/> Sicherheits Leser (im Security &amp; Compliance Center zugewiesen)  <br/> |
  |Anzeigen von Vorfällen (auch Untersuchungen genannt) <br/> Hinzufügen von e-Mail-Nachrichten zu einem Vorfall  <br/> |Globaler Office 365-Administrator  <br/> Sicherheits Administrator (im Security &amp; Compliance Center zugewiesen)  <br/> Sicherheits Leser (im Security &amp; Compliance Center zugewiesen)  <br/> |
  |Auslösen von e-Mail-Aktionen in einem Vorfall  <br/> Suchen und Löschen von verdächtigen e-Mail-Nachrichten  <br/> |Office 365 globaler Administrator oder Sicherheitsadministrator  <br/> Eine der obigen Rollen und suchen und löschen (zugewiesen im Security &amp; Compliance Center)  <br/> |
  |Integrieren von Office 365 Advanced Threat Protection Plan 2 mit Microsoft Defender ATP  <br/> Integrieren von Office 365 Advanced Threat Protection Plan 2 mit einem Siem-Server  <br/> |Globaler Office 365-Administrator  <br/> Sicherheits Administrator (im Security &amp; Compliance Center zugewiesen)  <br/> Entsprechende Rolle, die in weiteren Anwendungen zugewiesen ist (beispielsweise Microsoft Defender Security Center oder ein Siem-Server)  <br/> |
   
Informationen zu Rollen, Rollengruppen und Berechtigungen finden Sie unter [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).
    
## <a name="next-steps"></a>Nächste Schritte

- [Informationen zu Threat Tracker – neu und bemerkenswert](threat-trackers.md)
    
- [Suchen und untersuchen schädlicher e-Mails, die zugestellt wurden (Office 365 Untersuchung und Reaktion auf Bedrohungen)](investigate-malicious-email-that-was-delivered.md)
    
- [Integrieren von Office 365 Bedrohungs Ermittlung und-Reaktion mit Microsoft Defender Advanced Threat Protection](integrate-office-365-ti-with-wdatp.md)
    
- [Informationen zum Angriffs Simulator](attack-simulator.md)
  

