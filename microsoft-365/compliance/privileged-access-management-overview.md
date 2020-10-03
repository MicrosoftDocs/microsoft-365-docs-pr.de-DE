---
title: Privileged Access Management
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
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
ms.assetid: ''
description: Dieser Artikel bietet eine Übersicht über die Verwaltung privilegierter Zugriffsrechte in Microsoft 365, einschließlich Antworten auf häufig gestellte Fragen (FAQs).
ms.openlocfilehash: a1bcf1fbe767b4657be8a8ebcc8bf7b101c498d8
ms.sourcegitcommit: 79a21583a52aedd06317bbcabd8be40663379dec
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2020
ms.locfileid: "48341233"
---
# <a name="privileged-access-management"></a>Privileged Access Management

Die Verwaltung des privilegierten Zugriffs ermöglicht eine präzise steuerbare Zugriffskontrolle über privilegierte Administratoraufgaben in Office 365. Dies kann Ihre Organisation vor Angriffen schützen, bei denen vorhandene privilegierte Administratorkonten mit kontinuierlichem Zugang auf vertrauliche Daten oder kritische Konfigurationseinstellungen verwendet werden. Für die privilegierte Zugriffsverwaltung müssen Benutzer Just-in-Time-Zugriff anfordern, um erhöhte und privilegierte Aufgaben über einen umfangreichen und zeitgebundenen Genehmigungsworkflow abzuschließen. Diese Konfiguration ermöglicht Benutzern einen einfacheren Zugriff, um die jeweilige Aufgabe auszuführen, ohne dass vertrauliche Daten oder wichtige Konfigurationseinstellungen gefährdet werden. Durch die Aktivierung der privilegierten Zugriffsverwaltung in Microsoft 365 kann Ihre Organisation mit NULL stehenden rechten arbeiten und eine Verteidigungsstufe gegenständige administrative Zugriffs Sicherheitsrisiken bieten.

Eine kurze Übersicht über den integrierten Workflow "Customer Lockbox" und "privileged Access Management" finden Sie in diesem [Customer Lockbox-und privileged Access Management-Video](https://go.microsoft.com/fwlink/?linkid=2066800).

## <a name="layers-of-protection"></a>Schutzstufen

Die privilegierte Zugriffsverwaltung ergänzt andere Daten-und Zugriffs Funktionsschutz Funktionen in der Microsoft 365-Sicherheitsarchitektur. Das Einschließen einer privilegierten Zugriffsverwaltung als Teil eines integrierten und mehrschichtigen Sicherheitsansatzes stellt ein Sicherheitsmodell bereit, das den Schutz von vertraulichen Informationen und Microsoft 365-Konfigurationseinstellungen maximiert. Wie im Diagramm dargestellt, basiert die Verwaltung privilegierter Zugriffsrechte auf dem Schutz der systemeigenen Verschlüsselung von Microsoft 365-Daten und dem Sicherheitsmodell der rollenbasierten Zugriffssteuerung von Microsoft 365-Diensten. Bei Verwendung mit [Azure AD privilegierten Identitätsverwaltung](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)bieten diese beiden Features Zugriffssteuerung mit Just-in-Time-Zugriff in unterschiedlichen Bereichen.

![Mehrstufiger Schutz in Microsoft 365](../media/pam-layered-protection.png)

Die Verwaltung von privilegierten Zugriffsrechten wird auf **Taskebene** definiert und auf der Ebene des Bereichs durchgeführt, während Azure AD privilegierte Identitätsverwaltung den Schutz auf **Rollen** Ebene mit der Möglichkeit zur Ausführung mehrerer Aufgaben anwendet. Azure AD Privileged Identity Management ermöglicht in erster Linie die Verwaltung der Zugriffe für AD-Rollen und Rollengruppen, während die Verwaltung privilegierter Zugriffe in Microsoft 365 nur auf Aufgabenebene erfolgt.

- **Aktivieren der privilegierten Zugriffsverwaltung, wobei bereits Azure AD privilegierte Identitätsverwaltung verwendet wird:** Das Hinzufügen einer privilegierten Zugriffsverwaltung bietet eine weitere granulare Schicht von Schutz-und Überwachungsfunktionen für privilegierten Zugriff auf Microsoft 365-Daten.

- **Aktivieren Azure AD privilegierter Identitätsverwaltung, während Sie bereits die privilegierte Zugriffsverwaltung in Office 365 verwenden:**  Das Hinzufügen Azure AD privilegierter Identitätsverwaltung zur privilegierten Zugriffsverwaltung kann den privilegierten Zugriff auf Daten außerhalb von Microsoft 365 erweitern, die in erster Linie von Benutzerrollen oder Identität definiert werden.  

## <a name="privileged-access-management-architecture-and-process-flow"></a>Privilegierte Zugriffs Verwaltungsarchitektur und Prozessfluss

Jeder der folgenden Prozessabläufe gibt einen Überblick über die Architektur des privilegierten Zugriffs und deren Interaktion mit dem Microsoft 365-Substrat, der Überwachung und der Exchange-Verwaltungs Remoterunspace.

### <a name="step-1-configure-a-privileged-access-policy"></a>Schritt 1: Richtlinie für privilegierten Zugriff konfigurieren

Wenn Sie eine Richtlinie für privilegierten Zugriff mit dem [Microsoft 365 Admin Center](https://admin.microsoft.com) oder der Exchange-Verwaltungskonsole konfigurieren, definieren Sie die Richtlinie und die Features für den privilegierten Zugriff und die Richtlinien Attribute im Microsoft 365-Substrat. Die Aktivitäten werden im Security &amp; Compliance Center protokolliert. Die Richtlinie ist jetzt aktiviert und bereit, eingehende Genehmigungsanforderungen zu bearbeiten.

![Schritt 1: Richtlinienerstellung](../media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>Schritt 2: Zugriffsanforderung

Im [Microsoft 365 Admin Center](https://admin.microsoft.com) oder mit der Exchange-Verwaltungs-PowerShell können Benutzer Zugriff auf Erweiterte oder privilegierte Aufgaben anfordern. Das Feature für privilegierten Zugriff sendet die Anforderung an das Microsoft 365-Substrat zur Verarbeitung mit der konfigurierten Zugriffsrichtlinie für Berechtigungen und zeichnet die Aktivität in den Security &amp; Compliance Center-Protokollen auf.

![Schritt 2: Zugriffsanforderung](../media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>Schritt 3: Zugriffsgenehmigung

Eine Genehmigungsanforderung wird generiert und die ausstehende Anforderungsbenachrichtigung wird per E-Mail an die Genehmigenden gesendet. Im Falle einer Genehmigung wird die Anforderung des privilegierten Zugriffs als Genehmigung bearbeitet, und die Aufgabe kann erledigt werden. Bei Ablehnung wird die Aufgabe blockiert und dem Antragsteller kein Zugriff gewährt. Der Antragsteller wird über die Genehmigung oder Ablehnung der Anforderung per E-Mail benachrichtigt.

![Schritt 3: Zugriffsgenehmigung](../media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>Schritt 4: Zugriffsverarbeitung

Bei einer genehmigten Anforderung wird die Aufgabe vom Exchange-Verwaltungs-Runspace verarbeitet. Die Genehmigung wird gegen die Richtlinie für privilegierten Zugriff geprüft und vom Microsoft 365-Substrat verarbeitet. Alle Aktivitäten für den Vorgang werden im Security &amp; Compliance Center protokolliert.

![Schritt 4: Zugriffsverarbeitung](../media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

### <a name="what-skus-can-use-privileged-access-in-office-365"></a>Welche SKUs können in Office 365 privilegierten Zugriff verwenden?

Die privilegierte Zugriffsverwaltung steht Kunden für eine große Auswahl an Microsoft 365-und Office 365-Abonnements und-Add-ons zur Verfügung. Weitere Informationen finden Sie unter [Erste Schritte mit privilegierten Zugriffsverwaltung](privileged-access-management-configuration.md) .

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a>Wann unterstützt der privilegierte Zugriff Office 365 Arbeitsauslastungen jenseits von Exchange?

Die privilegierte Zugriffsverwaltung steht in Kürze in anderen Office 365 Arbeitsauslastungen zur Verfügung. Weitere Informationen finden Sie in der [Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap) .

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a>Meine Organisation benötigt mehr als 30 privilegierte Zugriffsrichtlinien, wird dieser Grenzwert erhöht?

Ja, das Erhöhen der aktuellen Begrenzung von 30 privilegierten Zugriffsrichtlinien pro Organisation erfolgt in der Feature-Roadmap.

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>Muss ich ein globaler Administrator sein, um den privilegierten Zugriff in Office 365 zu verwalten?

Nein, Sie müssen die Rolle "Exchange-Rollenverwaltung" Konten zuweisen, die den privilegierten Zugriff in Office 365 verwalten. Wenn Sie die Rolle "Rollenverwaltung" nicht als eigenständige Konto Berechtigung konfigurieren möchten, umfasst die globale Administrator Rolle standardmäßig diese Rolle und kann den privilegierten Zugriff verwalten. Benutzer, die in der Gruppe einer genehmigenden Person enthalten sind, müssen kein globaler Administrator sein oder die Rolle "Rollenverwaltung" zugewiesen haben, um Anforderungen mit PowerShell zu überprüfen und zu genehmigen.

### <a name="how-is-privileged-access-management-related-to-customer-lockbox"></a>Wie bezieht sich die privilegierte Zugriffsverwaltung auf die kundensperre?

[Kunden-Lockbox](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests) ermöglicht eine Ebene der Zugriffssteuerung für Organisationen, wenn Microsoft auf Daten zugreift. Die privilegierte Zugriffsverwaltung ermöglicht eine granulare Zugriffssteuerung innerhalb einer Organisation für alle Microsoft 365-privilegierten Aufgaben.

## <a name="ready-to-get-started"></a>Sind Sie bereit loszulegen?

Beginnen [Sie mit der Konfiguration Ihrer Organisation für die privilegierte Zugriffsverwaltung](privileged-access-management-configuration.md).

## <a name="learn-more"></a>Weitere Informationen

[Interaktiver Leitfaden: überwachen und Steuern von Administratoraufgaben mit privilegierter Zugriffsverwaltung](https://content.cloudguides.com/guides/Privileged%20Access%20Management)
