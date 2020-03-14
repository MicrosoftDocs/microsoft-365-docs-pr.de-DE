---
title: Microsoft 365 Enterprise-Workloads und -Szenarien
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Führen Sie die Benutzer Ihrer Organisation in die Produktivitätsworkloads von Microsoft 365 Enterprise ein.
ms.openlocfilehash: 692deeee652a4d27b8cc46a8e02890cccb8bb311
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633143"
---
# <a name="microsoft-365-for-enterprise-workloads-and-scenarios"></a>Microsoft 365 Enterprise-Workloads und -Szenarien

Um die Vorteile für Kreativität und Teamwork von Microsoft 365 Enterprise zu realisieren, stellen Sie die folgenden Workloads über Ihre Foundation-Infrastruktur bereit:

- [Microsoft Teams](teams-workload.md)
- [Exchange Online](exchangeonline-workload.md)
- [SharePoint und OneDrive](sharepoint-online-onedrive-workload.md)

Im Artikel [Migration](migration-microsoft-365-enterprise-workload.md) finden Sie eine allgemeine Roadmap zum Migrieren Ihrer gesamten Organisation zu Microsoft 365 Enterprise. Dies beinhaltet Microsoft Office-Client-Produkte, lokale Office-Serverprodukte und Microsoft Windows-basierte Geräte.

Szenarien verwenden Funktionen und Dienste aus Microsoft 365 Enterprise auf integrierte Art und Weise, um eine Geschäftsanforderung zu erfüllen. 

Eine solche Notwendigkeit besteht darin sicherzustellen, dass Ihre Mitarbeiter produktiv und sicher arbeiten können, wenn sie nicht direkt mit Ihrem Intranet verbunden sind. Eine Roadmap zur Bereitstellung von Infrastrukturelementen und zur Förderung der Einführung wichtiger Workloads, wie z. B. Microsoft Teams and Exchange Online, für Remotemitarbeiter finden Sie unter [Fördern von Remotemitarbeitern](empower-people-to-work-remotely.md).

Eine derartige Anforderung ist der Schutz von umfassend regulierten Daten, die in Microsoft 365 gespeichert sind. Stark regulierte Daten umfassen folgende digitale Assets:

- Daten, die regionalen Vorschriften unterliegen.
- Die wertvollsten Daten für Ihre Organisation, z. B. Geschäftsgeheimnisse, Informationen zu Finanzen oder Personalwesen und die Organisationsstrategie.

Informationen zum Schutz dieser Daten vor internen und externen Bedrohungen, finden Sie unter:

- [Microsoft Teams für streng regulierte Daten](secure-teams-highly-regulated-data-scenario.md)
- [SharePoint-Websites für streng regulierte Daten](teams-sharepoint-online-sites-highly-regulated-data.md). 

Diese Szenarien leiten Sie durch die Konfiguration eines Microsoft Teams-Teams oder einer SharePoint-Website, um Ihre wertvollsten Daten sicher zu speichern.

Dies sind die Workloads und Szenarien im allgemeinen Microsoft 365 Enterprise-Bereitstellungshandbuch:

![Workloads und Szenarien im allgemeinen Microsoft 365 Enterprise-Bereitstellungshandbuch:](../media/deploy-workloads/m365-deploy-content-arch-workloads.png)

Weitere Szenarien finden Sie in der [Microsoft 365-Produktivitätsbibliothek](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)). 

## <a name="foundation-infrastructure-prerequisites"></a>Foundation-Infrastruktur – Voraussetzungen

*Idealerweise* sollten Sie Arbeitslasten und Szenarios bereitstellen, nachdem Sie alle Phasen der [Foundation-Infrastruktur](deploy-foundation-infrastructure.md) konfiguriert haben. Dadurch wird sichergestellt, dass alle zugrunde liegenden Foundation-Ebenen vorhanden sind, um Integration, Sicherheit und die besten Ergebnisse für die Benutzer und deren Geräte bereitzustellen.

| Phase | Ergebnis |
|:-------|:-----|
| Netzwerk | Ihr Netzwerk wird für optimale Leistung auf Microsoft 365-Clouddienste aktualisiert. |
| Identität | Die Identität wird mit starker Authentifizierung für Benutzerkonten und Schutz für Administratorkonten synchronisiert und gesichert. |
| Windows 10 Enterprise | Ihre Computer mit Windows 7 oder Windows 8.1 können auf Windows 10 Enterprise aktualisiert werden, und neue Geräte sind mit Windows 10 Enterprise ausgestattet. |
| Office 365 ProPlus | Ihre vorhandenen Benutzer von Microsoft Office können ein Upgrade auf Office 365 ProPlus durchführen. |
| Verwaltung mobiler Geräte | Ihre Geräte können registriert und verwaltet werden. |
| Schutz von Daten | Die Microsoft 365-Features zum Schutz von Informationen sind konfiguriert, und Ihre Vertraulichkeits- oder Azure Information Protection-Bezeichnungen sind bereit zum Schützen von Dokumenten und E-Mail. |

Denken Sie daran, dass dies der Idealzustand ist, der einige Zeit zum Planen, Konfigurieren, Testen und Durchführen einer Pilotphase erfordert, insbesondere in großen Organisationen mit vorhandener Infrastruktur und mehreren Standorten. Die Durchführung dieser Phasen an allen Standorten ist nicht erforderlich, damit Sie schneller einen geschäftlichen Nutzen aus Microsoft 365 Enterprise ziehen. 

Hier einige allgemeine Arbeitslasten, die Sie sofort bereitstellen können: 

- Nachdem die Phase **Identität** der Foundation-Infrastruktur für Benutzer bereitgestellt wurde, stellen viele Organisationen Folgendes bereit:
  - [Office 365 ProPlus](office365proplus-infrastructure.md) in Kombination mit [OneDrive](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise). Office 365 ProPlus bietet die Sicherheit der modernen Authentifizierung und die Benutzeroberfläche des neuesten Microsoft Office-Clients. Die Migration der persönlichen Dateien des Benutzers zu OneDrive verkleinert die Infrastruktur und reduziert die Notwendigkeit, Home-Ordner und Laufwerke zu unterstützen.
  - [Exchange Online](exchangeonline-workload.md), damit Benutzer mithilfe von Cloud-basierter E-Mail beginnen können.
- Wenn Sie nicht sofort stark regulierte digitale Assets in der Cloud speichern müssen, stellen Sie [Microsoft Teams](teams-workload.md) und [SharePoint](sharepoint-online-onedrive-workload.md) für Ihre Benutzer vor der Phase **Informationsschutz** bereit.

Sie müssen entscheiden, wie Sie die Konfiguration der erforderlichen Phasen der Foundation-Infrastruktur am besten anordnen und bereitstellen, um Ihre Geschäftsanforderungen zu erfüllen.

### <a name="best-practice"></a>Bewährte Methode

Es wird dringend empfohlen, dass Sie die Phase **Identität** der Foundation-Infrastruktur vor dem Onboarding der Benutzer für alle Arbeitslasten oder Szenarien bereitstellen und implementieren.

Die Phase **Identität** stellt sicher, dass Ihre Cloud-basierte Identität, sei es Cloud oder mit Ihren lokalen Active Directory Domain Services (AD DS) synchronisiert, die Konten und Gruppen (Benutzer und Computer) für die Verwaltung der Authentifizierung und den Zugriff enthält. Starke Authentifizierung für alle Benutzer zusammen mit effizientem Schutz von Administratorkonten sind erforderlich, bevor Sie die digitalen Assets Ihrer Organisation in der Microsoft 365-Cloud platzieren.

Obwohl sie grundlegend und sehr wichtig für die Gesamtleistung ist, kann die Implementierung der Phase **Netzwerk** während des Onboardings der Benutzer für Arbeitslasten durchgeführt werden, mit dem Wissen, dass die Leistung von Microsoft 365-Workload und -Dienst mit der Zeit besser wird. Dies gilt insbesondere für Unternehmen mit mehreren Standorten und eine Mischung von Edge-Geräte und Internet-Verbindungen.
