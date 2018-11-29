---
title: 'Schritt 1: Planen von Benutzern und Gruppen'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Planen von Satz von Benutzern und Gruppen, die für Ihr Unternehmen arbeiten werden.
ms.openlocfilehash: 8062cc2b681f0ae45a8114a6d827f5d1ece2fe3e
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867551"
---
# <a name="step-1-plan-for-users-and-groups"></a>Schritt 1: Planen von Benutzern und Gruppen

*Dieser Schritt ist erforderlich und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

In diesem Schritt erstellen Sie Ihre Identitätsinfrastruktur, die Benutzer, Gruppen und Gruppenmitgliedschaften mit Sicherheitsfunktionen in der richtigen Konfiguration verwendet. Dadurch können Sie:

- die Kontrolle darüber behalten, wer Zugriff auf Ressourcen in Ihrer Umgebung hat.
- den Zugriff durch Steuerelemente sichern, die starke Sicherheiten im Bezug auf die Identität bieten (Benutzer sind die, die sie behaupten, zu sein), und über sichere Geräte zugreifen.
- Ressourcen in Ihrer Umgebung entsprechende Berechtigungen bereitstellen, um das Risiko für potenziellen Schaden und Datenverlust zu reduzieren. 
- Ihre Umgebung auf abweichendes Benutzerverhalten überwachen und automatisch Maßnahmen ergreifen.

## <a name="plan-your-primary-identity-provider"></a>Planen Ihres primären Identitätsanbieter

Um Ihre Identitätsinfrastruktur zu erstellen, müssen Sie einen primären Identitätsanbieter festlegen. Dieser Dienst speichert Benutzerkonten und deren Attribute, Gruppen und Mitgliedschaften und unterstützt deren kontinuierliche Verwaltung.

Wenn Ihre Organisation Microsoft 365 Enterprise einführt, ist Ihr primärer Identitätsanbieter entweder:

- **Windows Server Active Directory (AD)**, ein Intranet-Identitätsanbieter, der auf Computern gehostet wird, die auf dem Windows Server laufen. Dies wird normalerweise von Unternehmen genutzt, die über einen vorhandenen lokalen Identitätsanbieter verfügen.
- **Azure Active Directory (Azure AD**), ein cloudbasierter „Identity as a Service“(IDaaS)-Anbieter, der eine Vielzahl von Funktionen zum Verwalten und Schützen Ihre Umgebung bereitstellt. Dies wird normalerweise von Organisationen genutzt, die über keine vorhandene lokale Infrastruktur verfügen.

Wenn Ihr Unternehmen über einen vorhandenen lokalen Identitätsanbieter verfügt, müssen Sie Ihre Benutzerkonten und Gruppen von Windows Server AD mit Azure AD synchronisieren, um mehr nahtlosen Zugriff auf die cloudbasierten Dienste von Microsoft 365 Enterprise zu bieten. Sie können auch Azure AD verwenden, um Gruppen zu erstellen und zu verwalten, die nur in der Microsoft Cloud vorhanden sind.

Nachdem Sie Ihre Benutzer und Gruppen in Azure AD haben, können Sie:

- alle Azure AD-Konten für all Ihre Cloudanwendungen verwalten. 
- denselben Satz Steuerelemente zum Schützen des Zugriffs auf Anwendungen in Ihrer gesamten Umgebung verwenden.
- mit externen Partnern zusammenarbeiten.
- abweichendes Kontoverhalten, z. B. verdächtige Anmeldeversuche, überwachen und automatisch eingreifen.

Befolgen Sie die Anweisungen in den nächsten beiden Abschnitten, um Ihre Benutzerkonten und Gruppen zu planen und zu implementieren.

## <a name="categorize-your-users"></a>Kategorisieren Ihrer Benutzer
Benutzer in Unternehmen können auf verschiedene Weise kategorisiert werden. Einige sind beispielsweise Mitarbeiter und haben einen permanenten Status. Einige sind Lieferanten, Auftragnehmer oder Partner, die über einen temporären Status verfügen. Einige sind externe Benutzer, die keine Benutzerkonten haben, denen aber trotzdem Zugriff auf bestimmte Dienste und Ressourcen zur Unterstützung der Interaktion und Zusammenarbeit gewährt werden muss. Zum Beispiel:

- Mandantenkonten stellen Benutzer in Ihrem Unternehmen dar, die Sie für Clouddienste lizenzieren.
- Business-to-Business(B2B)-Konten stellen Benutzer außerhalb Ihres Unternehmens dar, die Sie zur Zusammenarbeit einladen.

Nehmen Sie eine Bestandsaufnahme der Arten von Benutzern in Ihrem Unternehmen vor. Was sind die Gruppierungen? Beispielsweise können Sie Benutzer nach hoher Funktion oder nach dem Zweck für Ihr Unternehmen gruppieren.

Darüber hinaus können einige Clouddienste für Benutzer außerhalb Ihres Unternehmens ohne Benutzerkonten freigegeben werden. Sie müssen diese Benutzergruppen ebenfalls identifizieren.

## <a name="plan-for-windows-server-ad-and-azure-ad-groups"></a>Planen von Windows Server AD- und Azure AD-Gruppen

Sie können Gruppen in Azure AD für mehrere Zwecke verwenden, die die Verwaltung Ihrer Cloudumgebung vereinfachen. Für Azure AD-Gruppen können Sie beispielsweise die folgenden Aufgaben durchführen:

- Sie können die gruppenbasierte Lizenzierung verwenden, um Ihren Benutzerkonten Lizenzen für Office 365 and Enterprise Mobility + Security (EMS) automatisch zuzuweisen, sobald diese in Azure AD hinzugefügt werden oder mit Windows Server AD synchronisiert werden. 
- Sie können bestimmten Gruppen auf Grundlage von Benutzerkontoattributen wie Abteilung Benutzerkonten dynamisch hinzufügen.  
- Sie können automatisch SaaS-Anwendungen für Benutzer bereitstellen und den Zugriff auf diese Anwendungen mit der mehrstufigen Authentifizierung und anderen Regeln für bedingten Zugriff schützen.
- Sie können Berechtigungen und Zugriffsebenen für SharePoint Online-Teamwebsites bereitstellen. Azure AD-Gruppen können auch mit bereichsbezogenen Azure Information Protection-Richtlinien zum Schutz von Dateien mit einer Verschlüsselung und Berechtigungen verwendet werden. 

## <a name="results"></a>Ergebnisse

Wenn Sie diesen Schritt abgeschlossen haben, verfügen Sie über Folgendes:

- Eine Liste der Benutzerkonten in Azure AD, die den Mitarbeitern in Ihrer Organisation und den Lieferanten, Vertragsnehmern und Partnern, die für oder mit Ihrer Organisation arbeiten, entsprechen.
- Gruppen und deren Mitgliedschaft bei Azure AD, die den logischen Benutzerkonten und anderen Gruppen für die automatische Lizenzbereitstellung von Sicherheitseinstellungen für Microsoft-Clouddienste entsprechen.

Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-user-groups) für diesen Schritt betrachten.


## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [Schützen von globalen Administratorkonten](identity-designate-protect-admin-accounts.md) |

