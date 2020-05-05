---
title: 'Phase 4: Microsoft 365 Apps for Enterprise'
f1.keywords:
- NOCSH
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
description: Die Schritte zur Bereitstellung der Microsoft 365 Apps for Enterprise-Infrastruktur für Microsoft 365 Enterprise.
ms.openlocfilehash: 5143ef8872a7ebd119e77c6148288828a39e20d9
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011947"
---
# <a name="phase-4-microsoft-365-apps-for-enterprise"></a>Phase 4: Microsoft 365 Apps for Enterprise

![Phase 4: Microsoft 365 Apps for Enterprise](../media/deploy-foundation-infrastructure/O365proplus_icon.png)

*Dies gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise und Microsoft 365 Education.*

Microsoft 365 Enterprise enthält Microsoft 365 Apps for Enterprise, die Abonnementversion von Office. Wie Office 2019 enthält auch Microsoft 365 Apps for Enterprise alle Office-Anwendungen, und diese Anwendungen werden direkt auf Ihren Clientgeräten installiert. Anders als bei Office 2019 wird Microsoft 365 Apps for Enterprise regelmäßig mit neuen Features aktualisiert und verfügt über ein benutzerbasiertes Lizenzierungsmodell, das Benutzern ermöglicht, Office auf mehreren Geräten zu installieren. Weitere Einzelheiten erfahren Sie unter [Info zu Microsoft 365 Apps for Enterprise](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps).

In dieser Phase stellen Sie Microsoft 365 Apps for Enterprise im Rahmen von Microsoft 365 Enterprise auf Clientgeräten bereit. Zusätzlich zur vorliegenden Anleitung empfehlen wir die Verwendung von [Microsoft FastTrack](https://fasttrack.microsoft.com/office) bei der Bereitstellung. 

Wenn Sie bereits Microsoft 365 Apps for Enterprise bereitgestellt haben, lesen Sie bitte den Abschnitt zu den [Beendigungskriterien](office365proplus-exit-criteria.md) für diese Phase, um sicherzustellen, dass sie die erforderlichen Kriterien für Microsoft 365 Enterprise erfüllen.

>[!Note]
>Weitere Informationen, um Windows 10 Enterprise und Microsoft 365 Apps for Enterprise zusammen bereitzustellen, finden Sie unter [Bereitstellungscenter für Desktop](desktop-deployment-center-home.md).
>

## <a name="step-1-assess-your-environment"></a>Schritt 1: Bewerten der Umgebung

Befolgen Sie vor der Bereitstellung von Microsoft 365 Apps for Enterprise die Anleitungen unter [Bewerten der Umgebung und Anforderungen für die Bereitstellung von Microsoft 365 Apps for Enterprise](https://docs.microsoft.com/DeployOffice/assess-microsoft-365-apps). Diese Bewertung schließt die Systemanforderungen, Details zu Ihren Clientgeräten (z. B. Architekturen und erforderliche Sprachen), Lizenzierungsanforderungen, Netzwerkfunktion und Anwendungskompatibilität ein. Das Abschließen der Bewertung unterstützt Sie bei der grundlegenden Entscheidungsfindung im Rahmen der Planung Ihrer Bereitstellung.

## <a name="step-2-plan-your-deployment"></a>Schritt 2: Planen der Bereitstellung

Befolgen Sie nach dem Bewerten Ihrer Umgebung die Anleitungen unter [Planen der Bereitstellung von Microsoft 365 Apps](https://docs.microsoft.com/DeployOffice/plan-microsoft-365-apps), um einen Bereitstellungsplan zu erstellen. Dieser Plan schließt die folgenden Entscheidungen ein: 

- Bereitstellen von Office, einschließlich dem zu verwendenden Tool (z. B. Microsoft Endpoint Configuration Manager oder Office-Bereitstellungstool) und dem Ort, von dem aus Office installiert werden soll
- Verwalten von Updates für Office
- Zu verwendende Updatekanäle (Updatekanäle für Office steuern, wie häufig die Benutzer Updates von Funktionen in ihren Office-Anwendungen erhalten)
- Zu verwendende Office-Installationspakete und -Bereitstellungsgruppen, darunter die zu installierenden Office-Anwendungen und Sprachen für Benutzer

Der Artikel zum [Planen](https://docs.microsoft.com/DeployOffice/plan-microsoft-365-apps) enthält die bewährten Methoden für alle diese Optionen, darunter die Verwaltung der Bereitstellung, Verwaltung der Updates, Definition der Installationspakete und Erstellung von Bereitstellungsgruppen. 

## <a name="step-3-deploy"></a>Schritt 3: Bereitstellen

Wählen Sie basierend auf Ihrem Bereitstellungsplan die Methode für die Bereitstellung aus:

- **[Bereitstellen von Microsoft 365 Apps mit Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-microsoft-365-apps-configuration-manager):** Verwalten der Bereitstellung mit Configuration Manager und Herunterladen und Bereitstellen von Office über Verteilungspunkte in Ihrem Netzwerk

- **[Bereitstellen von Microsoft 365 Apps über die Cloud](https://docs.microsoft.com/deployoffice/deploy-microsoft-365-apps-cloud):** Verwalten der Bereitstellung mit dem Office-Bereitstellungstool und direktes Installieren von Office über das Office-CDN auf Clientgeräten
 
- **[Installieren von Microsoft 365 Apps for Enterprise über das Office-Portal](https://docs.microsoft.com/deployoffice/manage-software-download-settings-office-365):** Verwalten der Bereitstellung im Office-Portal und direktes Installieren von Office auf Clientgeräten über das Portal durch Benutzer

Viele Organisationen verwenden für unterschiedliche Benutzer eine Kombination aus diesen Optionen. Eine Organisation kann z. B. Configuration Manager verwenden, um Office für die meisten Benutzer bereitzustellen, einer kleinen Gruppe von Mitarbeitern, die nicht häufig mit dem internen Netzwerk verbunden sind, jedoch ermöglichen, Office selbst zu installieren. 

Wenn Ihre Organisation Configuration Manager verwendet, wird empfohlen, ein Upgrade auf Current Branch durchzuführen und auf die aktuelle Version zu aktualisieren. Weitere Informationen finden Sie unter [Welchen Branch von Configuration Manager sollte ich verwenden?](https://docs.microsoft.com/mem/configmgr/core/understand/which-branch-should-i-use).

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Funktionsweise von Microsoft 365 Enterprise bei Microsoft

Erfahren Sie, wie die Experten bei Microsoft [Updates für Microsoft 365 Apps for Enterprise bereitstellen und verwalten](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7).

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Wie Microsoft 365 Enterprise bei Contoso eingesetzt wird

Erfahren Sie, wie die Contoso Corporation, ein fiktives, aber repräsentatives multinationales Unternehmen [Microsoft 365 Apps for Enterprise bereitgestellt hat](contoso-o365pp.md).

![Die Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Nächster Schritt

[Beendigungskriterien für die Infrastruktur von Microsoft 365 Apps for Enterprise](office365proplus-exit-criteria.md)
