---
title: Informationen zur Verwaltung des privilegierten Zugriffs
description: Dieser Artikel bietet eine Übersicht über privileged access management in Microsoft 365, einschließlich Antworten auf häufig gestellte Fragen (FAQs).
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

Die Verwaltung des privilegierten Zugriffs ermöglicht eine präzise steuerbare Zugriffskontrolle über privilegierte Administratoraufgaben in Office 365. Dies kann Ihre Organisation vor Angriffen schützen, bei denen vorhandene privilegierte Administratorkonten mit kontinuierlichem Zugang auf vertrauliche Daten oder kritische Konfigurationseinstellungen verwendet werden. Bei der Verwaltung des privilegierten Zugriffs müssen Benutzer Just-in-Time-Zugriff anfordern, um Aufgaben mit erhöhten und privilegierten Rechten über einen sehr bereichs- und zeitgebundenen Genehmigungsworkflow auszuführen. Diese Konfiguration ermöglicht Benutzern einen einfacheren Zugriff, um die jeweilige Aufgabe auszuführen, ohne dass vertrauliche Daten oder wichtige Konfigurationseinstellungen gefährdet werden. Die Aktivierung der Verwaltung des privilegierten Zugriffs in Microsoft 365 ermöglicht Es Ihrer Organisation, ohne ständige Berechtigungen zu arbeiten und eine Schutzebene gegen ständige Sicherheitslücken im Administrativen Zugriff zu bieten.

Eine kurze Übersicht über die integrierte Kunden-Lockbox und den Workflow für die Verwaltung des privilegierten Zugriffs finden Sie in diesem Video zur Verwaltung von Kunden-Lockbox und [privilegiertem Zugriff.](https://go.microsoft.com/fwlink/?linkid=2066800)

## <a name="layers-of-protection"></a>Schutzstufen

Privileged Access Management ergänzt andere Datenschutz- und Zugriffsfunktionsschutz in der Microsoft 365-Sicherheitsarchitektur. Die Einbeziehung von Privileged Access Management als Teil eines integrierten und mehrschichtigen Sicherheitsansatzes bietet ein Sicherheitsmodell, das den Schutz vertraulicher Informationen und Microsoft 365-Konfigurationseinstellungen maximiert. Wie im Diagramm dargestellt, basiert die Verwaltung des privilegierten Zugriffs auf dem Schutz, der mit der systemeigenen Verschlüsselung von Microsoft 365-Daten bereitgestellt wird, und dem rollenbasierten Sicherheitsmodell für die Zugriffssteuerung von Microsoft 365-Diensten. Bei Verwendung mit [Azure AD Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure)bieten diese beiden Features die Zugriffssteuerung mit Just-in-Time-Zugriff in unterschiedlichen Bereich.

![Mehrschichtigen Schutz in Microsoft 365](../media/pam-layered-protection.png)

Die Verwaltung des privilegierten Zugriffs  wird auf Aufgabenebene definiert und festgelegt, während Azure AD Privileged Identity Management Schutz auf Rollenebene mit der Möglichkeit bietet, mehrere Aufgaben auszuführen.  Azure AD Privileged Identity Management ermöglicht in erster Linie die Verwaltung der Zugriffe für AD-Rollen und Rollengruppen, während die Verwaltung privilegierter Zugriffe in Microsoft 365 nur auf Aufgabenebene erfolgt.

- **Aktivieren der Verwaltung des privilegierten Zugriffs, während Azure AD Privileged Identity Management bereits verwendet wird:** Das Hinzufügen von Privileged Access Management bietet eine weitere granulare Schutz- und Überwachungsebene für privilegierten Zugriff auf Microsoft 365-Daten.

- **Aktivieren von Azure AD Privileged Identity Management, während die Verwaltung des privilegierten Zugriffs bereits in Office 365 verwendet wird:**  Durch das Hinzufügen von Azure AD Privileged Identity Management zur Verwaltung des privilegierten Zugriffs kann der privilegierte Zugriff auf Daten außerhalb von Microsoft 365 erweitert werden, die in erster Linie durch Benutzerrollen oder Identität definiert sind.  

## <a name="privileged-access-management-architecture-and-process-flow"></a>Architektur und Prozessablauf der Verwaltung des privilegierten Zugriffs

Jeder der folgenden Prozessabläufe beschreibt die Architektur des privilegierten Zugriffs und seine Interaktion mit dem Microsoft 365-Substrate, der Überwachung und dem Exchange-Verwaltungs-Runspace.

### <a name="step-1-configure-a-privileged-access-policy"></a>Schritt 1: Richtlinie für privilegierten Zugriff konfigurieren

Wenn Sie eine Richtlinie für den privilegierten Zugriff mit dem [Microsoft 365 Admin Center](https://admin.microsoft.com) oder der Exchange Management PowerShell konfigurieren, definieren Sie die Richtlinien- und Featureprozesse für privilegierten Zugriff sowie die Richtlinienattribute im Microsoft 365-Substrate. Die Aktivitäten werden im Security &amp; Compliance Center protokolliert. Die Richtlinie ist jetzt aktiviert und bereit, eingehende Genehmigungsanforderungen zu bearbeiten.

![Schritt 1: Erstellen von Richtlinien](../media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>Schritt 2: Zugriffsanforderung

Im [Microsoft 365 Admin Center](https://admin.microsoft.com) oder mit der Exchange-Verwaltungs-PowerShell können Benutzer Zugriff auf erhöhte oder privilegierte Aufgaben anfordern. Das Feature für privilegierten Zugriff sendet die Anforderung an das Microsoft 365-Substrate zur Verarbeitung gemäß der konfigurierten Berechtigungszugriffsrichtlinie und zeichnet die Aktivität in den Security Compliance Center-Protokollen &amp; auf.

![Schritt 2: Zugriffsanforderung](../media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>Schritt 3: Zugriffsgenehmigung

Eine Genehmigungsanforderung wird generiert und die ausstehende Anforderungsbenachrichtigung wird per E-Mail an die Genehmigenden gesendet. Im Falle einer Genehmigung wird die Anforderung des privilegierten Zugriffs als Genehmigung bearbeitet, und die Aufgabe kann erledigt werden. Bei Ablehnung wird die Aufgabe blockiert und dem Antragsteller kein Zugriff gewährt. Der Antragsteller wird über die Genehmigung oder Ablehnung der Anforderung per E-Mail benachrichtigt.

![Schritt 3: Zugriffsgenehmigung](../media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>Schritt 4: Zugriffsverarbeitung

Bei einer genehmigten Anforderung wird die Aufgabe vom Exchange-Verwaltungs-Runspace verarbeitet. Die Genehmigung wird gegen die Richtlinie für privilegierten Zugriff geprüft und vom Microsoft 365-Substrat verarbeitet. Alle Aktivitäten für die Aufgabe werden im Security &amp; Compliance Center protokolliert.

![Schritt 4: Zugriffsverarbeitung](../media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

### <a name="what-skus-can-use-privileged-access-in-office-365"></a>Welche SKUs können privilegierten Zugriff in Office 365 verwenden?

Privileged Access Management steht Kunden für eine breite Auswahl an Microsoft 365- und Office 365-Abonnements und -Add-Ons zur Verfügung. Weitere [Informationen finden Sie unter "Erste Schritte mit der Verwaltung des privilegierten](privileged-access-management-configuration.md) Zugriffs".

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a>Wann unterstützt der privilegierte Zugriff Office 365-Workloads über Exchange hinaus?

Privileged access management will be available in other Office 365 workloads soon. Weitere Informationen finden Sie in der [Microsoft 365-Roadmap.](https://www.microsoft.com/microsoft-365/roadmap)

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a>Meine Organisation benötigt mehr als 30 Richtlinien für privilegierten Zugriff. Wird dieser Grenzwert erhöht?

Ja, das Erhöhen des aktuellen Grenzwerts von 30 Richtlinien für privilegierten Zugriff pro Organisation steht in der Feature-Roadmap.

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>Muss ich ein globaler Administrator sein, um privilegierten Zugriff in Office 365 zu verwalten?

Nein, Sie benötigen die Exchange-Rollenverwaltungsrolle, die Konten zugewiesen ist, die privilegierten Zugriff in Office 365 verwalten. Wenn Sie die Rolle "Rollenverwaltung" nicht als eigenständige Kontoberechtigung konfigurieren möchten, umfasst die Rolle "Globaler Administrator" diese Rolle standardmäßig und kann privilegierten Zugriff verwalten. Benutzer, die in der Gruppe der genehmigenden Benutzer enthalten sind, müssen kein globaler Administrator sein oder die Rolle "Rollenverwaltung" zum Überprüfen und Genehmigen von Anforderungen mit PowerShell zugewiesen haben.

### <a name="how-is-privileged-access-management-related-to-customer-lockbox"></a>Wie ist die Verwaltung des privilegierten Zugriffs mit der Kunden-Lockbox verbunden?

[Die Kunden-Lockbox](/office365/admin/manage/customer-lockbox-requests) ermöglicht organisationen eine Zugriffskontrolle, wenn Microsoft auf Daten zulässt. Privileged access management allows granular access control within an organization for all Microsoft 365 privileged tasks.

## <a name="ready-to-get-started"></a>Sind Sie bereit zu beginnen?

Beginnen [Sie mit der Konfiguration Ihrer Organisation für die Verwaltung des privilegierten Zugriffs.](privileged-access-management-configuration.md)

## <a name="learn-more"></a>Weitere Informationen

[Interaktives Handbuch: Überwachen und Steuern von Administratoraufgaben mit Privileged Access Management](https://content.cloudguides.com/guides/Privileged%20Access%20Management)
