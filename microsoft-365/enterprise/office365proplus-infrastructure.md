---
title: 'Phase 4: Office 365 ProPlus'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Die Schritte zur Bereitstellung der Office 365 Pro Plus-Infrastruktur für Microsoft 365 Enterprise.
ms.openlocfilehash: f41990055a97a2853622529e7cc28ccf096eef69
ms.sourcegitcommit: c5ca71d6feb0f033b50ccd4de816fd59b0925007
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "39831896"
---
# <a name="phase-4-office-365-proplus"></a>Phase 4: Office 365 ProPlus

![Phase 4: Office 365 ProPlus](./media/deploy-foundation-infrastructure/O365proplus_icon.png)

*Dies gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise und Microsoft 365 Education.*

Microsoft 365 Enterprise enthält Office 365 ProPlus, die Abonnementversion von Office. Wie Office 2019 enthält auch Office 365 ProPlus alle Office-Anwendungen, und diese Anwendungen werden direkt auf Ihren Clientgeräten installiert. Anders als bei Office 2019 wird Office 365 ProPlus regelmäßig mit neuen Features aktualisiert und verfügt über ein benutzerbasiertes Lizenzierungsmodell, das es Benutzern ermöglicht, Office auf mehreren Geräten zu installieren. Weitere Details finden Sie unter [Informationen zu Office 365 ProPlus im Unternehmen](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).

In dieser Phase stellen Sie Office 365 ProPlus auf Clientgeräten im Rahmen von Microsoft 365 Enterprise bereit. Zusätzlich zu dieser Anleitung empfehlen wir die Verwendung von [Microsoft Fastrack](https://fasttrack.microsoft.com/office) bei der Bereitstellung. 

Wenn Sie bereits Office 365 ProPlus bereitgestellt haben, lesen Sie bitte den Abschnitt zu den [Beendigungskriterien](office365proplus-exit-criteria.md) für diese Phase, um sicherzustellen, dass sie die erforderlichen Kriterien für Microsoft 365 Enterprise erfüllen.

>[!Note]
>Weitere Informationen, um Windows 10 Enterprise und Office 365 ProPlus zusammen zu erstellen, finden Sie unter [Bereitstellungscenter für Desktop](desktop-deployment-center-home.md).
>

## <a name="step-1-assess-your-environment"></a>Schritt 1: Bewerten der Umgebung

Befolgen Sie vor der Bereitstellung von Office 365 ProPlus die Anleitungen unter [Bewerten der Umgebung und Anforderungen für die Bereitstellung von Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus). Diese Bewertung umfasst die Systemanforderungen, Details zu Ihren Clientgeräten (z. B. Architekturen und erforderliche Sprachen), Lizenzen, Netzwerkfunktion und Anwendungskompatibilität. Das Abschließen der Bewertung unterstützt Sie bei grundlegender Entscheidungsfindung im Rahmen der Planung Ihrer Bereitstellung.

## <a name="step-2-plan-your-deployment"></a>Schritt 2: Planen der Bereitstellung

Befolgen Sie nach dem Bewerten der Umgebung die Anleitungen unter [Planen der Bereitstellung von Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) zum Erstellen eines Bereitstellungsplans. Dieser Plan enthält die folgenden Entscheidungen: 

- Bereitstellen von Office, einschließlich dem zu verwendenden Tool (z. B. Microsoft Endpoint Configuration Manager oder Office-Bereitstellungstool) und dem Ort, von dem aus Office installiert werden soll
- Verwalten von Updates für Office
- Zu verwendende Updatekanäle (Updatekanäle für Office steuern, wie häufig die Benutzer Updates von Funktionen in ihren Office-Anwendungen erhalten)
- Zu verwendende Office-Installationspakete und -Bereitstellungsgruppen, darunter die zu installierenden Office-Anwendungen und Sprachen für Benutzer

Der Artikel zum [Planen](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) enthält die bewährten Methoden für alle diese Optionen, darunter die Verwaltung der Bereitstellung, Verwaltung der Updates, Definition der Installationspakete und Erstellung von Bereitstellungsgruppen. 

## <a name="step-3-deploy"></a>Schritt 3: Bereitstellen

Wählen Sie basierend auf Ihrem Bereitstellungsplan die Methode für die Bereitstellung aus:

- **[Bereitstellen von Office 365 ProPlus mit dem Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** Verwalten der Bereitstellung mit dem Configuration Manager und Herunterladen und Bereitstellen von Office über Verteilungspunkte in Ihrem Netzwerk.

- **[Bereitstellen von Office 365 ProPlus mit dem Office-Bereitstellungstool aus der Cloud](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** Verwalten der Bereitstellung mit dem Office-Bereitstellungstool und direktes Installieren von Office über das Office-CDN auf Clientgeräten
 
- **[Installieren von Office 365 ProPlus über das Office-Portal](https://docs.microsoft.com/deployoffice/manage-software-download-settings-office-365):** Verwalten der Bereitstellung im Office-Portal und direktes Installieren von Office auf Clientgeräten über das Portal durch Benutzer

Viele Organisationen verwenden für unterschiedliche Benutzer eine Kombination aus diesen Optionen. Eine Organisation kann z. B. Configuration Manager verwenden, um Office für die meisten Benutzer bereitzustellen, einer kleinen Gruppe von Mitarbeitern, die nicht häufig mit dem internen Netzwerk verbunden sind, jedoch ermöglichen, Office selbst zu installieren. 

Wenn Ihre Organisation Configuration Manager verwendet, wird empfohlen, ein Upgrade auf Current Branch durchzuführen und auf die aktuelle Version zu aktualisieren. Weitere Informationen finden Sie unter [Welchen Branch von Configuration Manager sollte ich verwenden?](https://docs.microsoft.com/sccm/core/understand/which-branch-should-i-use).

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Funktionsweise von Microsoft 365 Enterprise bei Microsoft

Erfahren Sie, wie die Experten bei Microsoft [Updates für Office 365 ProPlus bereitstellen und verwalten](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7).

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Wie Microsoft 365 Enterprise bei Contoso eingesetzt wird

Erfahren Sie, wie die Contoso Corporation, ein fiktives, aber multinationales, repräsentatives Unternehmen [Office 365 ProPlus bereitgestellt hat](contoso-o365pp.md).

![Die Contoso Corporation](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Nächster Schritt

[Beendigungskriterien für die Office 365 ProPlus-Infrastruktur](office365proplus-exit-criteria.md)
