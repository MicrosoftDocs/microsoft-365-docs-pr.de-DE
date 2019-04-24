---
title: Rollen und Verantwortlichkeiten von Microsoft Managed Desktop
description: In diesem Thema werden die Rollen und Verantwortlichkeiten von Microsoft für Microsoft Managed Desktop beschrieben.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 161be07907754cdd7a0cd88dd3342d4b5e3c72e4
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283558"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Rollen und Verantwortlichkeiten von Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

Wenn Ihre Organisation in Microsoft Managed Desktop registriert ist, was macht Microsoft für Sie? Und was sind die Verantwortlichkeiten Ihrer Organisation?

## <a name="microsofts-roles-and-responsibilities"></a>Rollen und Verantwortlichkeiten von Microsoft

Im folgenden finden Sie einige wichtige Rollen und Verantwortlichkeiten, die Ihnen von Microsoft zur Verfügung gestellt werden.

Rolle oder Verantwortlichkeit | Beschreibung
--- | ---
Verwaltung von MDM-Richtlinien | Microsoft wendet die MDM-Richtlinien entsprechend den bewährten Methoden an und berücksichtigt Anforderungen für Richtlinienänderungen. Wir werden auch Änderungen an Ihrem Mandanten vornehmen, wie in [Geräterichtlinien](../service-description/device-policies.md)vorgeschrieben.
Endbenutzersupport | Microsoft bietet Endbenutzern Unterstützung für Geräte, Windows und Office-Produktsuite für alle registrierten Benutzer über die Get-Hilfe-APP, die auf allen Microsoft Managed Desktop-Geräten vorinstalliert ist. 
Unterstützung für Microsoft Managed Desktop Service | Microsoft unterstützt Kunden IT-Abteilungen über ein Microsoft Managed Desktop Operations-Team. Dieses Team unterstützt technische Problembehandlung, Änderungsanforderungen und Vorfallverwaltung für die von Microsoft verwaltete Desktop Umgebung des Kunden. Weitere Informationen finden Sie unter [Administrator Unterstützung für Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).
Sicherheitsüberwachung | Microsoft überwacht von Microsoft verwaltete Desktop Geräte des Kunden mithilfe von Windows Defender ATP. Wenn eine Bedrohung vom Microsoft Managed Desktop Security Operations Center (SOC) erkannt wird, wird der Kunde von Microsoft benachrichtigt, das Gerät isolieren und das Problem Remote beheben. Weitere Informationen finden Sie unter [Sicherheit](../service-description/security.md).
Aktualisieren der Überwachung und Verwaltung | Microsoft überwacht von Microsoft verwaltete Desktop Geräte, um sicherzustellen, dass die neuesten Qualitäts-und Funktionsupdates für Microsoft Windows und Microsoft Office installiert werden. Weitere Informationen finden Sie unter [wie Updates behandelt werden](../service-description/updates.md).
Benutzer-und Geräte Gruppierung | Microsoft Managed Desktop Operations Team erstellt und verwaltet erforderliche Geräte-und Benutzergruppen als Teil des IT-Betriebs. Es sind keine Mitgliedschafts-oder Konfigurationsänderungen an diesen Gruppen zulässig. Das Ändern dieser Gruppen kann zu unerwarteter Konfiguration von Geräten und Funktionalitätsverlust führen. Bei Problemen oder Fragen zu diesen Gruppen nach der Einrichtung können IT-Administratoren Microsoft Managed Desktop-Vorgänge kontaktieren. Weitere Informationen finden Sie unter [Administrator Unterstützung für Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).

## <a name="your-roles-and-responsibilities"></a>Ihre Rollen und Verantwortlichkeiten

Nachfolgend finden Sie eine zusätzliche Reihe allgemeiner Rollen und Zuständigkeiten, die von Microsoft nicht bereitgestellt werden, aber für eine erfolgreiche Bereitstellung erforderlich sind. Es ist nicht erschöpfend, sondern gilt für die meisten Organisationen. Unten gibt es einige Elemente, die sowohl von Microsoft als auch vom Kunden Verantwortlichkeiten werden. 

Rolle oder Verantwortlichkeit | Beschreibung
--- | ---
Änderungsverwaltung | Microsoft benachrichtigt Kunden im voraus, wenn Änderungen an der von Microsoft verwalteten Desktop Umgebung vorgenommen werden müssen. Der Kunde muss über einen eigenen Change Management-Prozess verfügen und einen Kontakt mit dem Microsoft Managed Desktop Operations-Team aufnehmen. Der Kunde muss außerdem über Ressourcen verfügen, um diese Änderungen zu überarbeiten und zu genehmigen. Weitere Informationen finden Sie unter [Vorgänge und Überwachung](../service-description/operations-and-monitoring.md).  
Identitätsverwaltung | Der Kunde ist für das Erstellen von Benutzerkonten, das Zuweisen von Benutzern zu Gruppen und das Aktualisieren von Metadaten auf dem neuesten Stand. 
Office 365-Konfiguration und-Verwaltung | Microsoft ist dafür verantwortlich, dass Office-Anwendungen für Endbenutzer bereitgestellt werden und diese Anwendungen auf dem neuesten Stand sind. <br><br> Der Kunde ist für die Verwaltung von Office 365-Diensten und-Richtlinien verantwortlich, einschließlich der Verantwortlichkeiten für die Exchange Online-Verwaltung:<br>-E-Mail-Verwaltung<br>-Postfach-und Regelkonfiguration<br>-Lokale Exchange-Verwaltung<br><br>Der Kunde ist außerdem verantwortlich für Tools für die Zusammenarbeit, SharePoint Server-Verwaltung, Domänenverwaltung, Sicherheits-und Informationsrichtlinien, die im Office 365-Verwaltungsportal festgelegt sind. 
Endbenutzersupport | Der Kunde ist für die Unterstützung von Endbenutzern für Folgendes verantwortlich: <br>-On-Site-Infrastruktur: alle Netzwerk-und Internetkonnektivität, VPN-Infrastruktur und Clientkonfiguration, lokale konferenzraumausstattung, Drucker, Proxy Server und-Konfiguration, Firewalls.<br><br>-Unternehmensweite Cloud-Ressourcen: e-Mail, SharePoint, Collaboration Services und andere Cloud-Infrastruktur, die sich auf den unternehmensweiten Technologie-Fußabdruck bezieht.<br><br>-Branche und alle anderen unternehmensspezifischen Anwendungen.
Apps | Microsoft stellt auf Anforderung mithilfe von InTune Bereitstellungsanweisungen für genehmigte Anwendungen bereit.<br><br>Der Kunde ist verantwortlich für:<br>-Bereitstelleneiner Liste von Apps für Ihre Organisation (außerhalb von Office 365-Apps)<br>-App-Lizenzverwaltung<br>– Die richtige Art und Menge von Lizenzen haben<br>-App-Zuweisung<br>– Zuweisen von apps zu Azure AD-Benutzergruppen<br>-APP-Updates<br>– ÜberWachen, Verpacken und Bereitstellen von App-Features und Sicherheitsupdates<br>-Benutzer Anwendungstests (BENUTZERAKZEPTANZTEST)<br>-Bereitstellen eines geeigneten bereitstellbaren Pakets<br><br>Weitere Informationen finden Sie unter [apps](../get-ready/apps.md)
Sicherheitsüberwachung und-Antwort | Der Kunde ist für die Untersuchung und Lösung von Vorfällen für nicht von Microsoft verwaltete Desktop Geräte verantwortlich und stellt sicher, dass das Microsoft Managed Desktop Operations-Team über Probleme informiert wird, die sich auf den Dienst auswirken können.
Betriebsunterstützung | Der Kunde ist dafür verantwortlich, eine Liste der bevorzugten Kundenkontakte und Fachexperten bereitzustellen. Microsoft benötigt diese, falls es einen nicht von Microsoft verwalteten Desktop-Vorfall gibt. <br><br>Der Kunde ist auch für die Untersuchung und Lösung von Vorfällen für nicht von Microsoft verwaltete Desktop-Geräte und-Dienste verantwortlich und stellt sicher, dass das Microsoft Managed Desktop Operations-Team immer informiert ist.
Netzwerkinfrastruktur, einschließlich VPN | Der Kunde ist für die Einrichtung, Konfiguration und Verwaltung (einschließlich Problembehandlung und Debugging) aller netzwerkbezogenen Infrastrukturen und Dienste verantwortlich, einschließlich Internetkonnektivität, Netzwerksteuerung, Proxykonfiguration und Remote Verbindungsinfrastruktur.<br><br>Wenn ein Proxy konfiguriert ist (in Hardware oder Software), gibt es eine Sammlung von URLs, die vom Proxy zugelassen werden müssen. Der Kunde ist für die Problembehandlung von Konflikten oder Inkompatibilitäten aufgrund mehrerer Proxys verantwortlich. Sie können mithilfe von konfigurierbaren Einstellungen Netzwerk Proxys für Ihre Organisation hinzufügen. Weitere Informationen finden Sie unter [konfigurierbare Einstellungen](../working-with-managed-desktop/config-setting-ref.md#proxy).<br><br>Weitere Informationen finden Sie unter [Proxy Konfiguration](../get-ready/network.md).
Drucken | Der Kunde ist für die Installation, Wartung und Verwaltung von Druckern und Druckerwarteschlangen verantwortlich. Cloud Printing ist eine empfohlene Lösung, ist aber nicht erforderlich. 




