---
title: Konfigurierbare Einstellungen für Microsoft Managed Desktop
description: Informationen zu konfigurierbaren Einstellungen mit Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation, Einstellungen, konfigurierbare Einstellungen
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/14/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0d30e92eb9747079a7edc5a8fd198298508f342e
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278212"
---
# <a name="configurable-settings---microsoft-managed-desktop"></a>Konfigurierbare Einstellungen – Microsoft Managed Desktop

Microsoft Managed Desktop stellt Einstellungen und Richtlinien bereit, die auf alle von Microsoft Managed Desktop verwalteten Geräte angewendet werden. Weitere Informationen finden Sie unter [Device Configuration](../service-description/device-policies.md).

Konfigurierbare Einstellungen in Microsoft Managed Desktop ermöglichen IT-Administratoren die Anpassung und Bereitstellung von Einstellungen, die für Ihre Organisation und Ihre geschäftlichen Anforderungen eindeutig sind. Diese Einstellungen gelten zusätzlich zu den Geräte Konfigurationseinstellungen und-Richtlinien, die von Microsoft Managed Desktop verwaltet werden.  

Konfigurierbare Einstellungsänderungen werden in der Cloud vorgenommen und auf Ihre Microsoft Managed Desktop-Geräte in definierten Bereitstellungsgruppen angewendet. Dieser Vorgang ähnelt der Verwaltung von Änderungen an Geräte configuruation-Einstellungen und-Richtlinien, die vom Dienst definiert und verwaltet werden. Mit dem gleichen Prozess, den Microsoft Managed Desktop für die Bereitstellung von Änderungen verwendet, bewegen Sie Ihre Organisation weiterhin mit modernen IT-Verwaltungsmethoden.

## <a name="when-to-use-configurable-settings"></a>Wann können konfigurierbare Einstellungen verwendet werden?

Es gibt einige Male, die konfigurierbare Einstellungen zu verwenden. 

Onboarding- **Prozess** – Microsoft Managed Desktop empfiehlt, konfigurierbare Einstellungen anzupassen, wenn Sie mit dem Microsoft Managed Desktop-Dienst Onboarding oder wenn Sie eine Vielzahl von Geräten (20 oder mehr) an Bord haben. Einstellungskategorien werden im Microsoft Managed Desktop Admin Portal konfiguriert. Nachdem Sie Onboarding und Zugriff auf das Administratorportal haben, können Sie entscheiden, welche Einstellungskategorien Sie für Ihre Organisation anpassen möchten, die Änderungen vornehmen, eine Bereitstellung durchführen und dann Ihre Änderungen bereitstellen.

**Einstellungen verwalten** -überprüfen Sie Ihre Einstellungen regelmäßig, und nehmen Sie die erforderlichen Updates vor. Möglicherweise müssen Sie Änderungen vornehmen, um eine Änderung in Ihrem Unternehmen zu unterstützen.   

## <a name="setting-categories"></a>Festlegen von Kategorien

Dies sind die konfigurierbaren Einstellungskategorien, die Sie anpassen können:
- [Desktophintergrundbild](config-setting-ref.md#desktop-background-picture) – Anpassen des Desktop Hintergrundbilds für Microsoft Managed Desktop-Geräte. 
- [Browser Startseiten](config-setting-ref.md#browser-start-pages) – Hinzufügen von Startseiten zur Verwendung mit Microsoft Edge. Siehe Browser-Startseite
- [Unternehmens Modus-Website Liste](config-setting-ref.md#enterprise-mode-site-list-location) – Websites hinzufügen und deren Kompatibilitätsmodus. Websites in der Liste werden in Internet Explorer gestartet. 
- [Vertrauenswürdige Sites](config-setting-ref.md#trusted-sites) – fügen Sie vertrauenswürdige Websites hinzu, und legen Sie Sicherheitszonen für jeden Standort fest. 
- [Proxy Site Exceptions](config-setting-ref.md#proxy) – richten Sie Ihre Proxy Server-Adressnummer und-Nummer ein, und fügen Sie Proxy-Website Ausnahmen hinzu.

Jede Einstellungskategorie kann individuell angepasst und bereitgestellt werden. Sie können gleichzeitig Änderungen an mehreren Einstellungskategorien bereitstellen, aber Sie können jeweils nur eine Änderung in einer Einstellungskategorie bereitstellen.

Beispiel:
- Sie können gleichzeitig Änderungen an Desktophintergrundbild und vertrauenswürdigen Websites bereitstellen. 
- Sie können nicht gleichzeitig zwei Bereitstellungen für Browser Startseiten bereitstellen. Die neueste Bereitstellung beendet frühere Bereitstellungen, die noch ausgeführt werden.

## <a name="configurable-setting-process"></a>Konfigurierbarer Einstellungsprozess

Microsoft Managed Desktop empfiehlt Folgendes, wenn Sie konfigurierbare Einstellungen für Ihre Organisation verwenden:

**Schritt 1 – planen** – erfahren Sie mehr über konfigurierbare Einstellungen, und entscheiden Sie, welche Einstellungskategorien Sie für Ihre Organisation konfigurieren möchten. Erstellen Sie eine Zeitachse, wenn Sie erwarten, dass Änderungen für jede Gruppe bereitgestellt werden. Planen Sie die Kommunikation zu Ihren Benutzern, die ihren internen Change Management-Prozessen entspricht. Wenn Sie beispielsweise Browser Startseiten hinzufügen, sollten Sie Ihren Benutzern mitteilen, dass Sie nach der Bereitstellung einen neuen Satz Startseiten in Ihrem Browser haben.  

**Schritt 2: Konfigurieren und bereit** stellen von Änderungen an konfigurierbaren Einstellungen im Microsoft Managed Desktop Admin Portal. Stufen Sie die Änderungen so ein, dass Sie bereit sind, bereitzustellen. Denken Sie daran, Ihre Benutzer über die Änderungen zu informieren und zu erfahren, wie die Änderungen ihre Geräteumgebung ändern.   

Sie konfigurieren und Stufen Änderungen im Microsoft Managed Desktop-Verwaltungsportal ab. Weitere Informationen finden Sie unter [Customize konfigurierbar Settings](config-setting-ref.md). 

**Schritt 3-kommunizieren von Änderungen** Informieren Sie Ihre Benutzer über bevorstehende Änderungen. Schließen Sie für jede Bereitstellung die Kommunikation ab, die Teil ihrer Change Management-Prozesse ist. Sie sollten jede Änderung klar kommunizieren, die Auswirkungen auf die Funktionsweise eines Benutzers hat oder was er auf seinen Geräten sieht.

**Schritt 4 – Bereitstellen von Änderungen** – stellen Sie Ihre Änderungen beginnend mit der Test Gruppe bereit. Die Test Gruppe ermöglicht die Überprüfung und Behandlung von Problemen in einer Gruppe mit weniger Geräten, bevor Änderungen an größeren Gerätegruppen bereitgestellt werden. Wenn Probleme auftreten, können Sie die Änderung rückgängig machen, die Einstellung aktualisieren und eine neue Bereitstellung inszenieren. Microsoft Managed Desktop empfiehlt, dass Sie den strukturierten Ansatz und die Bereitstellung in Gruppen in dieser Reihenfolge befolgen: Test, First, fast und dann Broad.   

Alle konfigurierbaren Einstellungen werden mithilfe des Microsoft Managed Desktop admin Portals verwaltet. Weitere Informationen finden Sie unter [Deploy Changes](config-setting-deploy.md). 

**Schritt 5-Nachverfolgen von Änderungen** – verfolgen Sie den Fortschritt für Ihre Änderungen am Bereitstellungsstatus. Für jede Einstellung können Sie Folgendes tun:
- **Verfolgen des Fortschritts** – Nachverfolgen des Status nach der Bereitstellung der Änderung. Der Status ändert sich **in in Bearbeitung**und wird dann **abgeschlossen**oder **fehlgeschlagen**. Wenn eine Bereitstellung fehlschlägt, wird automatisch eine Supportanforderung für Microsoft Managed Desktop-Vorgänge geöffnet, um das Problem zu untersuchen.  
- **Siehe Version deployed** – jede bereitgestellte Änderung hat eine Versionsnummer.
- **Änderungen rückgängig** machen – beim Rückgängigmachen einer Änderung wird die aktuelle Bereitstellung angehalten, und alle Gruppen werden auf die letzten Änderungen zurückgesetzt, die für alle Gruppen bereitgestellt wurden. Sie setzen zurück auf den Wert für die letzte bekanntermaßen gute Einstellung.
- **Änderungen überprüfen** – nachdem die Bereitstellung abgeschlossen ist, überprüfen Sie, ob die Änderungen wie erwartet angewendet wurden.  

Wenn eine Bereitstellung fehlgeschlagen ist oder Sie eine Änderung nicht rückgängig machen können, [Öffnen Sie eine Supportanfrage](admin-support.md) mit Microsoft Managed Desktop Operations. 

Weitere Informationen finden Sie unter [bereitstellen und Nachverfolgen von konfigurierbaren Einstellungen](config-setting-deploy.md).

## <a name="additional-resources"></a>Zusätzliche Ressourcen
- [Referenz zu konfigurierbaren Einstellungen](config-setting-ref.md) 
- [Bereitstellen von konfigurierbaren Einstellungen](config-setting-deploy.md) 
