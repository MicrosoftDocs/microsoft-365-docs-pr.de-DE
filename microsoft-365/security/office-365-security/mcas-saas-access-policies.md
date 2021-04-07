---
title: Empfohlene Microsoft Cloud App Security-Richtlinien für SaaS-Apps – Microsoft 365 Enterprise | Microsoft Docs
description: Beschreibt empfohlene Richtlinien für die Integration in Microsoft Cloud App Security.
author: BrendaCarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
audience: Admin
ms.author: bcarter
ms.date: 03/22/2021
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 61509c88ea2289509abd5ec7b6c0dcd54395d5f0
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599971"
---
# <a name="recommended-microsoft-cloud-app-security-policies-for-saas-apps"></a>Empfohlene Microsoft Cloud App Security-Richtlinien für SaaS-Apps
Microsoft Cloud App Security baut auf Azure AD-Richtlinien für bedingten Zugriff auf, um die Echtzeitüberwachung und Steuerung präziser Aktionen mit SaaS-Apps zu ermöglichen, z. B. das Blockieren von Downloads, Uploads, Kopieren und Einfügen und Drucken. Dieses Feature fügt Sitzungen, die ein inhärentes Risiko darstellen, Sicherheit hinzu, z. B. wenn auf Unternehmensressourcen von nicht verwalteten Geräten oder von Gastbenutzern zugegriffen wird.

Microsoft Cloud App Security integriert sich auch systemeigener Weise in Microsoft Information Protection und bietet Eine Echtzeit-Inhaltsprüfung, um vertrauliche Daten basierend auf vertraulichen Informationstypen und Vertraulichkeitsbezeichnungen zu finden und geeignete Maßnahmen zu ergreifen.

Diese Anleitung enthält Empfehlungen für die folgenden Szenarien:

- Hinzufügen von SaaS-Apps in die IT-Verwaltung
- Optimieren des Schutzes für bestimmte SaaS-Apps
- Konfigurieren der Verhinderung von Datenverlust (Data Loss Prevention, DLP) zur Einhaltung von Datenschutzbestimmungen

## <a name="bring-saas-apps-into-it-management"></a>Hinzufügen von SaaS-Apps in die IT-Verwaltung

Der erste Schritt bei der Verwendung von Microsoft Cloud App Security zum Verwalten von SaaS-Apps besteht im Ermitteln und anschließenden Hinzufügen zu Ihrem Azure AD-Mandanten. Wenn Sie Hilfe bei der Ermittlung benötigen, lesen [Sie Entdecken und Verwalten von SaaS-Apps in Ihrem Netzwerk.](/cloud-app-security/tutorial-shadow-it) Nachdem Sie Apps entdeckt haben, [fügen Sie diese ihrem Azure AD-Mandanten hinzu.](/azure/active-directory/manage-apps/add-application-portal)

Sie können damit beginnen, diese zu verwalten, indem Sie die folgenden Schritte tun:

1. Erstellen Sie zunächst in Azure AD eine neue Richtlinie für bedingten Zugriff, und konfigurieren Sie sie so, dass sie "App-Steuerelement für bedingten Zugriff verwenden" verwendet wird. Dadurch wird die Anforderung an Cloud App Security umgeleitet. Sie können eine Richtlinie erstellen und dieser Richtlinie alle SaaS-Apps hinzufügen.
1. Erstellen Sie als Nächstes in Cloud App Security Sitzungsrichtlinien. Erstellen Sie eine Richtlinie für jedes Steuerelement, das Sie anwenden möchten.

Berechtigungen für SaaS-Apps basieren in der Regel auf der geschäftlichen Notwendigkeit für den Zugriff auf die App. Diese Berechtigungen können sehr dynamisch sein. Die Verwendung von Cloud App Security-Richtlinien stellt den Schutz von App-Daten sicher, unabhängig davon, ob Benutzer einer Azure AD-Gruppe zugewiesen sind, die dem basisbasierten, vertraulichen oder streng regulierten Schutz zugeordnet ist.

Zum Schutz von Daten in Ihrer gesamten Sammlung von SaaS-Apps veranschaulicht das folgende Diagramm die erforderliche Azure AD-Richtlinie für bedingten Zugriff sowie vorgeschlagene Richtlinien, die Sie in Cloud App Security erstellen können. In diesem Beispiel gelten die in Cloud App Security erstellten Richtlinien für alle von Ihnen verwalteten SaaS-Apps. Diese sollen geeignete Steuerelemente anwenden, die darauf basieren, ob Geräte verwaltet werden, sowie Vertraulichkeitsbezeichnungen, die bereits auf Dateien angewendet werden.

![Richtlinien für die Verwaltung von SaaS-Apps in Cloud App Security](../../media/microsoft-365-policies-configurations/mcas-manage-saas-apps-2.png)

In der folgenden Tabelle ist die neue Richtlinie für bedingten Zugriff aufgeführt, die Sie in Azure AD erstellen müssen.

|Schutzebene|Richtlinie|Weitere Informationen|
|---|---|---|
|Alle Schutzstufen|[Verwenden der App-Steuerung für bedingten Zugriff in Cloud App Security](/cloud-app-security/proxy-deployment-aad#configure-integration-with-azure-ad)|Dadurch wird Ihr IdP (Azure AD) für die Verwendung mit Cloud App Security konfiguriert.|
||||

In der nächsten Tabelle sind die oben dargestellten Beispielrichtlinien aufgeführt, die Sie zum Schutz aller SaaS-Apps erstellen können. Achten Sie darauf, Ihre eigenen Geschäfts-, Sicherheits- und Complianceziele zu bewerten und dann Richtlinien zu erstellen, die den am besten geeigneten Schutz für Ihre Umgebung bieten.

|Schutzebene|Richtlinie|
|---|---|
|Baseline|Überwachen des Datenverkehrs von nicht verwalteten Geräten <p> Hinzufügen von Schutz zu Dateidownloads von nicht verwalteten Geräten|
|Vertraulich|Blockieren des Downloads von Dateien mit der Bezeichnung "vertraulich" oder "klassifiziert" von nicht verwalteten Geräten (dadurch wird nur Browserzugriff ermöglicht)|
|Streng geregelt|Blockieren des Downloads von Dateien, die von allen Geräten mit der Bezeichnung klassifiziert sind (dies bietet nur Browserzugriff)|
|||

Eine End-to-End-Anleitung zum Einrichten der App-Steuerung für bedingten Zugriff finden Sie unter [Deploy Conditional Access App Control for featured apps](/cloud-app-security/proxy-deployment-aad). In diesem Artikel werden Sie durch den Prozess des Erstellens der erforderlichen Richtlinie für bedingten Zugriff in Azure AD und testen Ihrer SaaS-Apps erläutert.

Weitere Informationen finden Sie unter [Schützen von Apps mit Microsoft Cloud App Security Conditional Access App Control](/cloud-app-security/proxy-intro-aad).

## <a name="tune-protection-for-specific-saas-apps"></a>Optimieren des Schutzes für bestimmte SaaS-Apps

Möglicherweise möchten Sie zusätzliche Überwachung und Steuerelemente auf bestimmte SaaS-Apps in Ihrer Umgebung anwenden. Cloud App Security ermöglicht Ihnen dies. Wenn beispielsweise eine App wie Box in Ihrer Umgebung stark verwendet wird, ist es sinnvoll, zusätzliche Steuerelemente anzuwenden. Wenn Ihre Rechts- oder Finanzabteilung eine bestimmte SaaS-App für vertrauliche Geschäftsdaten verwendet, können Sie diesen Apps zusätzlichen Schutz bieten.

Beispielsweise können Sie Ihre Box-Umgebung mit den folgenden Typen von integrierten Richtlinienvorlagen für die Erkennung von Anomalie schützen:

- Aktivität von anonymen IP-Adressen
- Aktivität von seltenem Land
- Aktivität von verdächtigen IP-Adressen
- Unmöglicher Ortswechsel
- Vom beendeten Benutzer ausgeführte Aktivität (erfordert AAD als IdP)
- Schadsoftwareerkennung
- Mehrere fehlgeschlagene Anmeldeversuche
- Ransomware-Aktivität
- Riskante Oauth-App
- Ungewöhnliche Dateifreigabeaktivität

Dies sind Beispiele. Weitere Richtlinienvorlagen werden regelmäßig hinzugefügt. Beispiele zum Anwenden eines zusätzlichen Schutzes auf bestimmte Apps finden Sie unter [Protecting connected apps](/cloud-app-security/protect-connected-apps).

[Wie Cloud App Security Ihre Box-Umgebung](/cloud-app-security/protect-box) schützt, veranschaulicht die Arten von Steuerelementen, die Ihnen helfen können, Ihre Geschäftsdaten in Box und anderen Apps mit vertraulichen Daten zu schützen.

## <a name="configure-data-loss-prevention-dlp-to-help-comply-with-data-protection-regulations"></a>Konfigurieren der Verhinderung von Datenverlust (Data Loss Prevention, DLP) zur Einhaltung von Datenschutzbestimmungen

Cloud App Security kann ein wertvolles Tool zum Konfigurieren des Schutzes für Compliancebestimmungen sein. In diesem Fall erstellen Sie bestimmte Richtlinien, um nach bestimmten Daten zu suchen, auf die eine Verordnung angewendet wird, und konfigurieren jede Richtlinie, um geeignete Maßnahmen zu ergreifen.

Die folgende Abbildung und Tabelle enthält mehrere Beispiele für Richtlinien, die zur Einhaltung der DSGVO konfiguriert werden können. In diesen Beispielen suchen Richtlinien nach bestimmten Daten. Basierend auf der Vertraulichkeit der Daten ist jede Richtlinie so konfiguriert, dass sie geeignete Maßnahmen ergreifen kann.

![Beispiel für Cloud App-Sicherheitsrichtlinien zur Verhinderung von Datenverlust](../../media/microsoft-365-policies-configurations/mcas-dlp.png)

|Schutzebene|Beispielrichtlinien|
|---|---|
|Baseline|Warnung, wenn Dateien mit diesem vertraulichen Informationstyp ("Kreditkartennummer") außerhalb der Organisation freigegeben werden <p> >Blockieren von Downloads von Dateien mit diesem vertraulichen Informationstyp ("Kreditkartennummer") auf nicht verwaltete Geräte|
|Vertraulich|Schützen von Downloads von Dateien mit diesem vertraulichen Informationstyp ("Kreditkartennummer") auf verwaltete Geräte <p> Blockieren von Downloads von Dateien mit diesem vertraulichen Informationstyp ("Kreditkartennummer") auf nicht verwaltete Geräte <p> Warnung, wenn eine Datei mit on dieser Bezeichnungen in OneDrive for Business oder Box hochgeladen wird (Kundendaten, Personalwesen: Gehaltsdaten,Personalwesen, Mitarbeiterdaten)|
|Streng geregelt|Warnung, wenn Dateien mit dieser Bezeichnung ("Hochgradig klassifiziert") auf verwaltete Geräte heruntergeladen werden <p> Blockieren von Downloads von Dateien mit dieser Bezeichnung ("Hochgradig klassifiziert") auf nicht verwaltete Geräte|
|||

## <a name="next-steps"></a>Nächste Schritte

Weitere Informationen zur Verwendung von Cloud App Security finden Sie in [der Microsoft Cloud App Security-Dokumentation](//cloud-app-security/).
