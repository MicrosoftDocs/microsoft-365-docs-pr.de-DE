---
title: Informationen zur Verwaltung des privilegierten Zugriffs
description: Dieser Artikel bietet eine Übersicht über die Verwaltung privilegierter Zugriffe in Microsoft 365, einschließlich Antworten auf häufig gestellte Fragen (FAQs).
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
f1.keywords:
- NOCSH
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.openlocfilehash: 059e1653d7db9140dbc80fd69fe36e95a744b079
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126604"
---
# <a name="learn-about-privileged-access-management"></a>Informationen zur Verwaltung des privilegierten Zugriffs

Die Verwaltung des privilegierten Zugriffs ermöglicht eine präzise steuerbare Zugriffskontrolle über privilegierte Administratoraufgaben in Office 365. Dies kann Ihre Organisation vor Angriffen schützen, bei denen vorhandene privilegierte Administratorkonten mit kontinuierlichem Zugang auf vertrauliche Daten oder kritische Konfigurationseinstellungen verwendet werden. Für die Verwaltung des privilegierten Zugriffs müssen Benutzer just-in-time-Zugriff anfordern, um Aufgaben mit erhöhten rechten Rechten über einen besonders bereichs- und zeitgebundenen Genehmigungsworkflow auszuführen. Diese Konfiguration ermöglicht Benutzern einen einfacheren Zugriff, um die jeweilige Aufgabe auszuführen, ohne dass vertrauliche Daten oder wichtige Konfigurationseinstellungen gefährdet werden. Wenn Sie die Verwaltung von privilegierten Zugriffen in Microsoft 365, kann Ihre Organisation mit null stehenden Rechten arbeiten und eine Schutzebene gegen ständige Sicherheitsrisiken im Administrativen Zugriff bereitstellen.

Eine schnelle Übersicht über die integrierte Customer Lockbox und den Workflow für die Verwaltung privilegierter Zugriffe finden Sie in diesem Video zur Verwaltung von Kundensperren und [privilegiertem Zugriff.](https://go.microsoft.com/fwlink/?linkid=2066800)

## <a name="layers-of-protection"></a>Schutzstufen

Die Verwaltung des privilegierten Zugriffs ergänzt andere Daten- und Zugriffsfunktionsschutze innerhalb Microsoft 365 Sicherheitsarchitektur. Die Einbeziehung der Verwaltung des privilegierten Zugriffs als Teil eines integrierten und mehrschichtigen Sicherheitsansatzes bietet ein Sicherheitsmodell, das den Schutz vertraulicher Informationen maximiert und Microsoft 365 konfiguriert. Wie im Diagramm dargestellt, basiert die Verwaltung privilegierter Zugriffe auf dem Schutz, der mit der systemeigenen Verschlüsselung von Microsoft 365-Daten und dem rollenbasierten Sicherheitsmodell für die Zugriffssteuerung von Microsoft 365 wird. Bei Verwendung mit [Azure AD Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure)bieten diese beiden Features die Zugriffssteuerung mit Just-in-Time-Zugriff auf unterschiedliche Bereiche.

![Mehrschichtigen Schutz in Microsoft 365](../media/pam-layered-protection.png)

Die Verwaltung des privilegierten Zugriffs  wird auf Aufgabenebene definiert und auf  sie angewendet, während Azure AD Privileged Identity Management auf Rollenebene Schutz bietet und mehrere Aufgaben ausführen kann. Azure AD Privileged Identity Management ermöglicht in erster Linie die Verwaltung der Zugriffe für AD-Rollen und Rollengruppen, während die Verwaltung privilegierter Zugriffe in Microsoft 365 nur auf Aufgabenebene erfolgt.

- **Aktivieren der Verwaltung des privilegierten Zugriffs während der Verwendung von Azure AD Privileged Identity Management:** Das Hinzufügen der Verwaltung des privilegierten Zugriffs bietet eine weitere granulare Schutz- und Überwachungsebene für den privilegierten Zugriff auf Microsoft 365 Daten.

- **Aktivieren von Azure AD Privileged Identity Management, während sie bereits die Verwaltung privilegierter Zugriffe in Office 365:**  Das Hinzufügen von Azure AD Privileged Identity Management zur Verwaltung privilegierter Zugriffe kann den privilegierten Zugriff auf Daten außerhalb von Microsoft 365, die in erster Linie durch Benutzerrollen oder -identität definiert sind, erweitern.  

## <a name="privileged-access-management-architecture-and-process-flow"></a>Architektur und Prozessablauf der Privilegierten Zugriffsverwaltung

Jeder der folgenden Prozessabläufe beschreibt die Architektur des privilegierten Zugriffs und die Interaktion mit dem Microsoft 365, der Überwachung und dem Exchange Management-Runspace.

### <a name="step-1-configure-a-privileged-access-policy"></a>Schritt 1: Richtlinie für privilegierten Zugriff konfigurieren

Wenn Sie eine Richtlinie für den privilegierten Zugriff mit dem [Microsoft 365 Admin Center](https://admin.microsoft.com) oder der Exchange Management PowerShell konfigurieren, definieren Sie die Richtlinie, die Featureprozesse für den privilegierten Zugriff und die Richtlinienattribute im Microsoft 365 Substrate. Die Aktivitäten werden im Security &amp; Compliance Center protokolliert. Die Richtlinie ist jetzt aktiviert und bereit, eingehende Genehmigungsanforderungen zu bearbeiten.

![Schritt 1: Erstellen von Richtlinien](../media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>Schritt 2: Zugriffsanforderung

Im [Microsoft 365 Admin Center](https://admin.microsoft.com) oder mit der Exchange Management PowerShell können Benutzer Zugriff auf Aufgaben mit erhöhten oder privilegierten Rechten anfordern. Das Feature für den privilegierten Zugriff sendet die Anforderung an das Microsoft 365 zur Verarbeitung für die konfigurierte Berechtigungszugriffsrichtlinie und zeichnet die Aktivität in den Protokollen des Security &amp; Compliance Center auf.

![Schritt 2: Zugriffsanforderung](../media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>Schritt 3: Zugriffsgenehmigung

Eine Genehmigungsanforderung wird generiert und die ausstehende Anforderungsbenachrichtigung wird per E-Mail an die Genehmigenden gesendet. Im Falle einer Genehmigung wird die Anforderung des privilegierten Zugriffs als Genehmigung bearbeitet, und die Aufgabe kann erledigt werden. Bei Ablehnung wird die Aufgabe blockiert und dem Antragsteller kein Zugriff gewährt. Der Antragsteller wird über die Genehmigung oder Ablehnung der Anforderung per E-Mail benachrichtigt.

![Schritt 3: Zugriffsgenehmigung](../media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>Schritt 4: Zugriffsverarbeitung

Bei einer genehmigten Anforderung wird die Aufgabe vom Exchange-Verwaltungs-Runspace verarbeitet. Die Genehmigung wird gegen die Richtlinie für privilegierten Zugriff geprüft und vom Microsoft 365-Substrat verarbeitet. Alle Aktivitäten für die Aufgabe werden im Security &amp; Compliance Center protokolliert.

![Schritt 4: Zugriffsverarbeitung](../media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

### <a name="what-skus-can-use-privileged-access-in-office-365"></a>Welche SKUs können privilegierten Zugriff in Office 365?

Die Verwaltung des privilegierten Zugriffs steht Kunden für eine große Auswahl von Microsoft 365 und Office 365 Abonnements und Add-Ons zur Verfügung. Weitere [Informationen finden Sie unter Erste Schritte mit der Verwaltung privilegierter](privileged-access-management-configuration.md) Zugriffe.

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a>Wann werden privilegierte Zugriffsunterstützung Office 365 Arbeitsauslastungen über Exchange?

Privileged access management wird in Kürze in anderen Office 365 verfügbar sein. Weitere Informationen [Microsoft 365 finden](https://www.microsoft.com/microsoft-365/roadmap) Sie in der Microsoft 365 Roadmap.

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a>Meine Organisation benötigt mehr als 30 Richtlinien für den privilegierten Zugriff. Wird dieser Grenzwert erhöht?

Ja, das Erhöhen des aktuellen Grenzwerts von 30 Richtlinien für den privilegierten Zugriff pro Organisation ist in der Feature-Roadmap.

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>Muss ich ein globaler Administrator sein, um den privilegierten Zugriff in Office 365?

Nein, Sie benötigen die Exchange Rollenverwaltungsrolle, die Konten zugewiesen ist, die den privilegierten Zugriff in Office 365. Wenn Sie die Rollenverwaltungsrolle nicht als eigenständige Kontoberechtigung konfigurieren möchten, enthält die Rolle globaler Administrator diese Rolle standardmäßig und kann privilegierten Zugriff verwalten. Benutzer, die in einer Gruppe genehmigender Benutzer enthalten sind, müssen kein globaler Administrator sein oder die Rollenverwaltungsrolle zum Überprüfen und Genehmigen von Anforderungen mit PowerShell zugewiesen haben.

### <a name="how-is-privileged-access-management-related-to-customer-lockbox"></a>Wie steht die Verwaltung des privilegierten Zugriffs im Zusammenhang mit Customer Lockbox?

[Customer Lockbox](/office365/admin/manage/customer-lockbox-requests) ermöglicht eine Ebene der Zugriffssteuerung für Organisationen, wenn Microsoft auf Daten zutritt. Die Verwaltung des privilegierten Zugriffs ermöglicht eine präzise Zugriffssteuerung innerhalb einer Organisation für alle Microsoft 365 privilegierte Aufgaben.

## <a name="ready-to-get-started"></a>Sind Sie bereit zu beginnen?

Beginnen [Sie, Ihre Organisation für die Verwaltung privilegierter Zugriffe zu konfigurieren.](privileged-access-management-configuration.md)

## <a name="learn-more"></a>Weitere Informationen

[Interaktive Anleitung: Überwachen und Steuern von Administratoraufgaben mit privilegierter Zugriffsverwaltung](https://content.cloudguides.com/guides/Privileged%20Access%20Management)
