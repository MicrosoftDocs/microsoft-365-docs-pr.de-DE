---
title: Konfigurierbare Einstellungen für Microsoft Managed Desktop
description: Informationen zu konfigurierbaren Einstellungen mit Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation, Einstellungen, konfigurierbare Einstellungen
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1af320ee6151036000e4e8c6fedc4d9152411283
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530235"
---
# <a name="configurable-settings---microsoft-managed-desktop"></a>Konfigurierbare Einstellungen – Microsoft Managed Desktop

Microsoft Managed Desktop stellt Einstellungen und Richtlinien bereit, die auf alle von Microsoft Managed Desktop verwalteten Geräte angewendet werden. Weitere Informationen finden Sie unter [Device Configuration](../service-description/device-policies.md).

Konfigurierbare Einstellungen in Microsoft Managed Desktop ermöglichen IT-Administratoren das anpassen und Bereitstellen von Einstellungen, die für Ihre Organisation und Ihre geschäftlichen Anforderungen eindeutig sind. Diese Einstellungen sind zusätzlich zu den Geräte Konfigurationseinstellungen und-Richtlinien, die von Microsoft Managed Desktop verwaltet werden.  

Konfigurierbare Einstellungsänderungen werden in der Cloud vorgenommen und auf Ihre verwalteten Microsoft-Desktop Geräte in definierten Bereitstellungsgruppen angewendet. Dieser Prozess ähnelt dem Verwalten von Änderungen an Geräte configuruation-Einstellungen und-Richtlinien, die vom Dienst definiert und verwaltet werden, mit Microsoft Managed Desktop. Mithilfe des gleichen Verfahrens, das von Microsoft Managed Desktop für die Bereitstellung von Änderungen verwendet wird, können Sie Ihre Organisation mit modernen IT-Verwaltungsmethoden weiter nach vorn bewegen.

## <a name="when-to-use-configurable-settings"></a>Wann können konfigurierbare Einstellungen verwendet werden?

Es gibt einige Male, um konfigurierbare Einstellungen zu verwenden. 

**Onboarding-Prozess** – Microsoft Managed Desktop empfiehlt, konfigurierbare Einstellungen anzupassen, wenn Sie sich an den Microsoft Managed Desktop Service oder an eine große Anzahl von Geräten (20 oder mehr) an Bord anpassen. Einstellungskategorien werden im Verwaltungsportal von Microsoft Managed Desktop konfiguriert. Nachdem Sie onboarded haben und Zugriff auf das Verwaltungsportal haben, können Sie festlegen, welche Einstellungskategorien für Ihre Organisation angepasst werden sollen, die Änderungen vornehmen, eine Bereitstellung inszenieren und dann die Änderungen bereitstellen.

**Einstellungen verwalten** – überprüfen Sie Ihre Einstellungen regelmäßig, und machen Sie die erforderlichen Updates. Möglicherweise müssen Sie Änderungen vornehmen, um eine Änderung in Ihrem Unternehmen zu unterstützen.   

## <a name="setting-categories"></a>Festlegen von Kategorien

Dies sind die konfigurierbaren Einstellungskategorien, die Sie anpassen können:
- [Desktophintergrundbild](config-setting-ref.md#desktop-background-picture) – Anpassen des Desktop Hintergrundbilds für von Microsoft verwaltete Desktop Geräte. 
- [Browser Startseiten](config-setting-ref.md#browser-start-pages) – Hinzufügen von Startseiten zur Verwendung mit Microsoft Edge. Siehe Browser Startseite
- [Unternehmens Modus-Website Liste](config-setting-ref.md#enterprise-mode-site-list-location) – Hinzufügen von Websites und des Kompatibilitätsmodus. Websites in der Liste werden in Internet Explorer gestartet. 
- [Vertrauenswürdige Websites](config-setting-ref.md#trusted-sites) – fügen Sie vertrauenswürdige Websites hinzu, und legen Sie Sicherheitszonen für jeden Standort fest. 
- [Proxy Site Exceptions](config-setting-ref.md#proxy) – richten Sie Ihre Proxy Server-Adressnummer und Portnummer ein, und fügen Sie Proxy Site Exceptions hinzu.

Jede Einstellungskategorie kann individuell angepasst und bereitgestellt werden. Sie können Änderungen an mehreren Einstellungskategorien gleichzeitig bereitstellen, jedoch können Sie nur eine Änderung gleichzeitig in einer Einstellungskategorie bereitstellen.

Zum Beispiel:
- Sie können Änderungen am Desktophintergrundbild und an vertrauenswürdigen Websites, jeweils als eigene Bereitstellung, gleichzeitig bereitstellen. 
- Sie können nicht gleichzeitig zwei Bereitstellungen für Browser Startseiten bereitstellen. Bei der letzten Bereitstellung werden frühere Bereitstellungen angehalten, die noch ausgeführt werden.

## <a name="configurable-setting-process"></a>Konfigurierbarer Einstellungsprozess

Microsoft Managed Desktop empfiehlt die Verwendung von konfigurierbaren Einstellungen für Ihre Organisation, wenn Sie einen ähnlichen Prozess wie den folgenden ausführen:

**Schritt 1 – planen** – erfahren Sie mehr über konfigurierbare Einstellungen, und entscheiden Sie, welche Einstellungskategorien für Ihre Organisation konfiguriert werden sollen. Erstellen Sie eine Zeitachse für die Bereitstellung von Änderungen an jeder Gruppe. Planen der Kommunikation mit ihren Benutzern, die ihre internen Änderungsverwaltungsprozesse erfüllt. Wenn Sie beispielsweise Browser Startseiten hinzufügen, sollten Sie Ihren Benutzern mitteilen, dass Sie nach der Bereitstellung eine neue Gruppe von Startseiten in Ihrem Browser haben.  

**Schritt 2 – konfigurieren und Bereitstellen der Bereitstellung** – vornehmen von Änderungen an konfigurierbaren Einstellungen im Verwaltungsportal von Microsoft Managed Desktop. Stufen Sie die Änderungen so ein, dass Sie bereit bereitgestellt werden können. Denken Sie daran, die Benutzer über die Änderungen zu informieren und zu erfahren, wie die Änderungen ihre Geräte Erfahrung ändern werden.   

Sie können Änderungen im Verwaltungsportal von Microsoft Managed Desktop konfigurieren und Stufen. Weitere Informationen finden Sie unter [Anpassen von konfigurierbaren Einstellungen](config-setting-ref.md). 

**Schritt 3 – kommunizieren von Änderungen** Informieren Sie Ihre Benutzer über bevorstehende Änderungen. Vervollständigen Sie für jede Bereitstellung die Kommunikation, die Teil ihrer Änderungsverwaltungsprozesse ist. Sie sollten jede Änderung deutlich mitteilen, die Auswirkungen auf die Funktionsweise eines Benutzers hat oder auf den Geräten angezeigt wird.

**Schritt 4 – Bereitstellen von Änderungen** – Bereitstellen der Änderungen, beginnend mit der Test Gruppe. Mit der Test Gruppe können Sie alle Probleme in einer Gruppe mit weniger Geräten validieren und beheben, bevor Sie Änderungen an größeren Gerätegruppen bereitstellen. Wenn Probleme auftreten, können Sie die Änderung rückgängig machen, die Einstellung aktualisieren und eine neue Bereitstellung inszenieren. Microsoft Managed Desktop empfiehlt, dass Sie dem strukturierten Ansatz folgen und die Bereitstellung für Gruppen in dieser Reihenfolge ausführen: Test, erste, schnell und dann breit.   

Alle konfigurierbaren Einstellungen werden über das Verwaltungsportal von Microsoft Managed Desktop verwaltet. Weitere Informationen finden Sie unter [Bereitstellen von Änderungen](config-setting-deploy.md). 

**Schritt 5: Nachverfolgen von Änderungen** – Nachverfolgen des Fortschritts für Ihre Änderungen am Bereitstellungsstatus. Für jede Einstellung haben Sie folgende Möglichkeiten:
- Nach **verfolgen des Fortschritts** – Status nachverfolgen, nachdem Sie die Änderung bereitgestellt haben. Der Status wird in " **in Bearbeitung**" und dann entweder " **abgeschlossen**" oder " **fehlgeschlagen**" geändert. Wenn bei einer Bereitstellung ein Fehler auftritt, wird automatisch eine Supportanforderung für Microsoft Managed Desktop-Vorgänge geöffnet, um das Problem zu untersuchen.  
- **Siehe Version deployed** – jede bereitgestellte Änderung verfügt über eine Versionsnummer.
- **Änderungen wiederherstellen** – durch das Zurücksetzen einer Änderung wird die aktuelle Bereitstellung angehalten, und alle Gruppen werden auf die letzten Änderungen zurückgesetzt, die für alle Gruppen bereitgestellt wurden. Sie führen ein Rollback auf den letzten zweifelsfrei funktionierenden Einstellungswert aus.
- Über **Prüfen der Änderungen** – nachdem die Bereitstellung abgeschlossen ist, überprüfen Sie, ob die Änderungen wie erwartet angewendet wurden.  

Wenn eine Bereitstellung fehlgeschlagen ist oder Sie eine Änderung nicht rückgängig machen können, [Öffnen Sie eine Supportanfrage](admin-support.md) bei Microsoft Managed Desktop Operations. 

Weitere Informationen finden Sie unter [Deploy and Track konfigurierbar Settings](config-setting-deploy.md).

## <a name="additional-resources"></a>Zusätzliche Ressourcen
- [Referenz der konfigurierbaren Einstellungen](config-setting-ref.md) 
- [Bereitstellen konfigurierbarer Einstellungen](config-setting-deploy.md) 
