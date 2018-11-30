---
title: 'Schritt 6: Schutz vor Kompromittierung von Anmeldeinformationen'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Grundlegendes zu und Konfiguration von Azure AD Identity Protection.
ms.openlocfilehash: b1dea9d2917c45bf87bd972f56c9eac2b074c252
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868203"
---
# <a name="step-6-protect-against-credential-compromise"></a>Schritt 6: Schutz vor Kompromittierung von Anmeldeinformationen

*Dieser Schritt ist optional und gilt nur für die Versionen E5 von Microsoft 365 Enterprise.*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

In diesem Schritt erfahren Sie, wie Sie die Richtlinien zum Schutz vor Kompromittierung von Anmeldeinformationen konfigurieren. Bei der Kompromittierung von Anmeldeinformationen bestimmt ein Angreifer den Kontonamen und das Kennwort des Benutzers, um Zugriff auf die Clouddienste und Daten einer Organisation zu erhalten. Azure AD Identity Protection bietet eine Reihe von Methoden, mit denen verhindert werden kann, dass sich ein Angreifer seitwärts durch Konten und Gruppen und folglich Ihre wertvollsten Daten bewegt.

Mit Azure AD Identity Protection können Sie Folgendes:

|||
|:---------|:---------|
|Ermitteln und Beseitigen potenzieller Anfälligkeiten für Identitätsverletzungen in Ihrer Organisation|Azure Active Directory verwendet maschinelles Lernen, um Anomalien und verdächtige Aktivitäten automatisch zu erkennen, z. B. Anmeldungen und Aktivitäten nach der Anmeldung. Anhand dieser Daten generiert Identity Protection Berichte und Warnungen, mit denen Sie die Probleme auswerten und entsprechende Maßnahmen ergreifen können.|
|Erkennen verdächtiger Aktionen, die im Zusammenhang mit Identitäten in Ihrer Organisation stehen, und automatisches Reagieren auf diese|Sie können risikobasierte Richtlinien konfigurieren, die automatisch auf erkannte Probleme reagieren, wenn eine angegebene Risikostufe erreicht wurde. Mit diesen Richtlinien können Sie neben anderen von Azure Active Directory and Enterprise Mobility + Security (EMS) bereitgestellten bedingten Zugriffssteuerungen entweder den Zugriff automatisch blockieren oder Korrekturmaßnahmen ergreifen, z. B. Kennwörter zurücksetzen oder mehrstufige Authentifizierung für nachfolgende Anmeldungen festlegen.|
|Untersuchen verdächtiger Vorfälle und Beseitigen mit Verwaltungsaufgaben|Sie können Risikoereignisse anhand von Informationen zu dem Sicherheitsvorfall untersuchen. Es stehen grundlegende Workflows zur Nachverfolgung von Untersuchungen und Initiierung von Korrekturmaßnahmen wie das Zurücksetzen von Kennwörtern zur Verfügung.|

Siehe [weitere Informationen zu Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).

Siehe [Schritte zum Aktivieren von Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).

In diesem Schritt haben Sie Azure AD Identity Protection aktiviert und verwenden es für Folgendes:

- Beseitigen potenzieller Anfälligkeiten für Identitätsverletzungen
- Erkennen möglicher Kompromittierungsversuche von Anmeldeinformationen
- Untersuchen und Beheben laufender verdächtiger Identitätsvorfälle

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testumgebungsanleitung: Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

Als Zwischenprüfpunkt können Sie sich die [Beendigungskriterien](identity-exit-criteria.md#crit-identity-ident-prot) für diesen Schritt ansehen.

## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![](./media/stepnumbers/Step7.png)| [Synchronisieren von Verzeichnissen](identity-azure-ad-connect.md) |


