---
title: Privileged Access Management in Office 365
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
- M365-security-compliance
ms.custom: Ent_Solutions
ms.assetid: ''
description: In diesem Thema erfahren Sie mehr über die Verwaltung privilegierter Zugriffsrechte in Office 365
ms.openlocfilehash: 9bc2aab9c9758daf35aa14a41d7997a0bff5764f
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "38686114"
---
# <a name="privileged-access-management-in-office-365"></a>Privileged Access Management in Office 365

> [!IMPORTANT]
> In diesem Thema werden Bereitstellungs-und Konfigurationsanleitungen für Features behandelt, die derzeit in Office 365 E5 und Advanced Compliance SKUs verfügbar sind.

Die privilegierte Zugriffsverwaltung ermöglicht eine granulare Zugriffssteuerung über privilegierte Verwaltungsaufgaben in Office 365. Damit können Sie Ihre Organisation vor Verstößen schützen, die vorhandene privilegierte Administratorkonten mit einem ständigen Zugriff auf vertrauliche Daten oder den Zugriff auf wichtige Konfigurationseinstellungen verwenden. Für die privilegierte Zugriffsverwaltung müssen Benutzer Just-in-Time-Zugriff anfordern, um erhöhte und privilegierte Aufgaben über einen umfangreichen und zeitgebundenen Genehmigungsworkflow abzuschließen. Dadurch erhalten Benutzer einfach genug Zugriff, um die Aufgabe zur Hand zu haben, ohne dass vertrauliche Daten oder wichtige Konfigurationseinstellungen gefährdet werden. Durch die Aktivierung der privilegierten Zugriffsverwaltung in Office 365 kann Ihre Organisation mit NULL stehenden rechten arbeiten und eine Verteidigungsstufe gegenständige administrative Zugriffs Sicherheitsrisiken bieten.

Eine kurze Übersicht über den integrierten Workflow für die integrierte kundensperre und den privilegierten Zugriffs Verwaltungsdienst finden Sie [in dieser Customer Lockbox und der privilegierten Zugriffsverwaltung in Office 365 Video](https://go.microsoft.com/fwlink/?linkid=2066800).

## <a name="layers-of-protection"></a>Schutzebenen

Die privilegierte Zugriffsverwaltung ergänzt andere Daten-und Zugriffs Funktionsschutz Funktionen in der Office 365 Sicherheitsarchitektur. Das Einschließen einer privilegierten Zugriffsverwaltung im Rahmen eines integrierten und mehrschichtigen Sicherheitsansatzes stellt ein Sicherheitsmodell bereit, das den Schutz vertraulicher Informationen und Office 365 Konfigurationseinstellungen maximiert. Wie im Diagramm dargestellt, basiert die Verwaltung privilegierter Zugriffe auf dem Schutz, der mit der systemeigenen Verschlüsselung von Office 365 Daten und dem Sicherheitsmodell der rollenbasierten Zugriffssteuerung Office 365 Dienste bereitgestellt wird. Bei Verwendung mit [Azure AD privilegierten Identitätsverwaltung](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)bieten diese beiden Features Zugriffssteuerung mit Just-in-Time-Zugriff in unterschiedlichen Bereichen.

![Mehrstufiger Schutz in Office 365](media/pam-layered-protection.png)

Die Verwaltung privilegierter Zugriffsrechte in Office 365 ist auf **Aufgaben** Ebene definiert und beschränkt, während Azure AD privilegierte Identitätsverwaltung den Schutz auf **Rollen** Ebene mit der Möglichkeit anwendet, mehrere Aufgaben auszuführen. Azure AD privilegierte Identitätsverwaltung ermöglicht in erster Linie das Verwalten von Zugriffsrechten für AD-Rollen und Rollengruppen, während die privilegierte Zugriffsverwaltung in Office 365 nur auf Aufgabenebene gilt.

- **Aktivieren der privilegierten Zugriffsverwaltung in Office 365, während bereits Azure AD privilegierte Identitätsverwaltung verwendet wird:** Das Hinzufügen einer privilegierten Zugriffsverwaltung in Office 365 bietet eine weitere granulare Schicht von Schutz-und Überwachungsfunktionen für privilegierten Zugriff auf Office 365 Daten.

- **Aktivieren Azure AD privilegierter Identitätsverwaltung, während Sie bereits die privilegierte Zugriffsverwaltung in Office 365 verwenden:**  Das Hinzufügen Azure AD privilegierter Identitätsverwaltung zu einer privilegierten Zugriffsverwaltung in Office 365 kann den privilegierten Zugriff auf Daten außerhalb Office 365 erweitern, die in erster Linie durch Benutzerrollen oder Identität definiert ist.  

## <a name="privileged-access-management-architecture-and-process-flow"></a>Privilegierte Zugriffs Verwaltungsarchitektur und Prozessfluss

Jeder der folgenden Prozessabläufe gibt einen Überblick über die Architektur des privilegierten Zugriffs und deren Interaktion mit dem Office 365 Substrat, Office 365 Überwachung und der Exchange-Verwaltungs Remoterunspace.

### <a name="step-1-configure-a-privileged-access-policy"></a>Schritt 1: Konfigurieren einer Richtlinie für privilegierten Zugriff

Wenn Sie eine Richtlinie für privilegierten Zugriff mit dem [Microsoft 365 Admin Center](https://admin.microsoft.com) oder der Exchange-Verwaltungskonsole konfigurieren, definieren Sie die Richtlinie und die Features für den privilegierten Zugriff und die Richtlinien Attribute im Office 365 Substrat. Die Aktivitäten werden im Office 365 Security and Compliance Center protokolliert. Die Richtlinie ist jetzt aktiviert und kann eingehende Anforderungen für Genehmigungen verarbeiten.

![Schritt 1: Richtlinienerstellung](media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>Schritt 2: Zugriffsanforderung

Im [Microsoft 365 Admin Center](https://admin.microsoft.com) oder mit der Exchange-Verwaltungs-PowerShell können Benutzer Zugriff auf Erweiterte oder privilegierte Aufgaben anfordern. Das Feature für privilegierten Zugriff sendet die Anforderung an das Office 365 Substrat zur Verarbeitung mit der konfigurierten Zugriffsrichtlinie für Berechtigungen und zeichnet die Aktivität in den Protokollen des Office 365 Security and Compliance Center auf.

![Schritt 2: Zugriffsanforderung](media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>Schritt 3: Zugriffsgenehmigung

Eine Genehmigungsanforderung wird generiert, und die Benachrichtigung über ausstehende Anforderungen wird an genehmigende Personen gesendet. Wenn diese Berechtigung genehmigt wurde, wird die privilegierte Zugriffsanforderung als Genehmigung verarbeitet, und die Aufgabe ist fertig. Wenn die Aufgabe verweigert wird, wird der Vorgang blockiert, und dem Anforderer wird kein Zugriff gewährt. Der Anforderer wird über die Anforderungsgenehmigung oder Ablehnung per e-Mail-Nachricht benachrichtigt.

![Schritt 3: Zugriffsgenehmigung](media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>Schritt 4: Zugriffs Verarbeitung

Für eine genehmigte Anforderung wird die Aufgabe von der Exchange-Verwaltungs-Remoterunspace verarbeitet. Die Genehmigung wird anhand der privilegierten Zugriffsrichtlinie überprüft und von der Office 365 Substrat verarbeitet. Alle Aktivitäten für den Vorgang werden im Office 365 Security and Compliance Center protokolliert.

![Schritt 4: Zugriffs Verarbeitung](media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

### <a name="what-skus-can-use-privileged-access-in-office-365"></a>Welche SKUs können in Office 365 privilegierten Zugriff verwenden?
Für Kunden mit Office 365 E5-und Advanced Compliance-SKUs steht eine privilegierte Zugriffsverwaltung zur Verfügung.

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a>Wann unterstützt der privilegierte Zugriff Office 365 Arbeitsauslastungen jenseits von Exchange?
Die privilegierte Zugriffsverwaltung steht in Kürze in anderen Office 365 Arbeitsauslastungen zur Verfügung. Weitere Informationen finden Sie in der [Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap) .

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a>Meine Organisation benötigt mehr als 30 privilegierte Zugriffsrichtlinien, wird dieser Grenzwert erhöht?
Ja, das Erhöhen der aktuellen Grenze von 30 privilegierten Zugriffsrichtlinien pro Office 365 Organisation erfolgt in der Feature-Roadmap.

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>Muss ich ein globaler Administrator sein, um den privilegierten Zugriff in Office 365 zu verwalten?
Nein, Sie müssen die Rolle "Exchange-Rollenverwaltung" Konten zuweisen, die den privilegierten Zugriff in Office 365 verwalten. Wenn Sie die Rolle "Rollenverwaltung" nicht als eigenständige Konto Berechtigung konfigurieren möchten, umfasst die globale Administrator Rolle standardmäßig diese Rolle und kann den privilegierten Zugriff verwalten. Benutzer, die in der Gruppe einer genehmigenden Person enthalten sind, müssen kein globaler Administrator sein, oder es ist die Rolle "Rollenverwaltung" zum Überprüfen und Genehmigen von Anforderungen zugewiesen.

### <a name="how-is-privileged-access-management-in-office-365-related-to-customer-lockbox"></a>Wie wird die privilegierte Zugriffsverwaltung in Office 365 im Zusammenhang mit Kunden-Lockbox?
[Kunden-Lockbox](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests) ermöglicht eine Ebene der Zugriffssteuerung für Organisationen, wenn Microsoft auf Daten zugreift. Die privilegierte Zugriffsverwaltung in Office 365 ermöglicht eine granulare Zugriffssteuerung in einer Organisation für alle Office 365 privilegierten Aufgaben.

## <a name="ready-to-get-started"></a>Sind Sie bereit zu beginnen?

Beginnen [Sie mit der Konfiguration Ihrer Organisation für die privilegierte Zugriffsverwaltung](privileged-access-management-configuration.md).

## <a name="learn-more"></a>Weitere Informationen

[Interaktiver Leitfaden: überwachen und Steuern von Administratoraufgaben mit privilegierter Zugriffsverwaltung](https://content.cloudguides.com/guides/Privileged%20Access%20Management)