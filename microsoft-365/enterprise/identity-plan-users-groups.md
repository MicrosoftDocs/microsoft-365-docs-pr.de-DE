---
title: 'Schritt 1: Planen von Benutzern und Gruppen'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Planen von Satz von Benutzern und Gruppen, die für Ihr Unternehmen arbeiten werden.
ms.openlocfilehash: f8b3df73518e33c7750c0b72b2cb9f36bc8e9745
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283792"
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

- **Active Directory Domain Services (AD DS)**, ein Intranet-Identitätsanbieter, der auf Computern mit Windows-Server gehostet wird. Dieser wird in der Regel von Organisationen genutzt, die über einen vorhandenen lokalen Identitätsanbieter verfügen.
- **Azure Active Directory (Azure AD**), ein cloudbasierter „Identity as a Service“(IDaaS)-Anbieter, der eine Vielzahl von Funktionen zum Verwalten und Schützen Ihre Umgebung bereitstellt. Dies wird normalerweise von Organisationen genutzt, die über keine vorhandene lokale Infrastruktur verfügen.

Wenn Ihr Unternehmen über einen vorhandenen lokalen Identitätsanbieter verfügt, müssen Sie Ihre Benutzerkonten und Gruppen von Active Directory Domain Services (AD DS) mit Azure AD synchronisieren, um mehr nahtlosen Zugriff auf die cloudbasierten Dienste von Microsoft 365 Enterprise zu bieten.  Sie können auch Azure AD verwenden, um Gruppen zu erstellen und zu verwalten, die nur in der Microsoft Cloud vorhanden sind.

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

## <a name="plan-for-ad-ds-and-azure-ad-groups"></a>Planung für AD DS und Azure Active Directory-Gruppen

Sie können Gruppen in Azure AD für mehrere Zwecke verwenden, die die Verwaltung Ihrer Cloudumgebung vereinfachen. Für Azure AD-Gruppen können Sie beispielsweise die folgenden Aufgaben durchführen:

- Sie können die gruppenbasierte Lizenzierung verwenden, um Ihren Benutzerkonten Lizenzen für Office 365 and Enterprise Mobility + Security (EMS) automatisch zuzuweisen, sobald diese in Azure AD hinzugefügt werden oder mit AD DS synchronisiert werden. 
- Sie können bestimmten Gruppen auf Grundlage von Benutzerkontoattributen wie Abteilung Benutzerkonten dynamisch hinzufügen.  
- Sie können automatisch SaaS-Anwendungen für Benutzer bereitstellen und den Zugriff auf diese Anwendungen mit der mehrstufigen Authentifizierung und anderen Regeln für bedingten Zugriff schützen.
- Sie können Berechtigungen und Zugriffsebenen für SharePoint Online-Teamwebsites bereitstellen. Azure AD-Gruppen können auch mit bereichsbezogenen Azure Information Protection-Richtlinien zum Schutz von Dateien mit einer Verschlüsselung und Berechtigungen verwendet werden. 

## <a name="results"></a>Ergebnisse

Wenn Sie diesen Schritt abgeschlossen haben, verfügen Sie über Folgendes:

- Eine Liste der Benutzerkonten in Azure AD, die den Mitarbeitern in Ihrer Organisation und den Lieferanten, Vertragsnehmern und Partnern, die für oder mit Ihrer Organisation arbeiten, entsprechen.
- Gruppen und deren Mitgliedschaft bei Azure AD, die den logischen Benutzerkonten und anderen Gruppen für die automatische Lizenzbereitstellung von Sicherheitseinstellungen für Microsoft-Clouddienste entsprechen.

Als Zwischenprüfung können Sie die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-user-groups) für diesen Schritt betrachten.

Sobald Ihre Benutzer und Gruppen in Azure AD vorhanden sind, können Sie mit dem Zuweisen von Lizenzen und der Verwendung von Exchange Online beginnen. Informationen zur Einführung von Exchange Online bei Ihren Benutzern finden Sie unter [Bereitstellen von Exchange Online für Microsoft 365 Enterprise](exchangeonline-workload.md).

## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [Sichern Ihrer privilegierten Identitäten](identity-designate-protect-admin-accounts.md) |

