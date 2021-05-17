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
ms.openlocfilehash: bf8672ee6c3332ea6f8522f5086d72e58d1b9048
ms.sourcegitcommit: bdf65d48b20f0f428162c39ee997accfa84f4e5d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2020
ms.locfileid: "49371490"
---
# <a name="configurable-settings---microsoft-managed-desktop"></a>Konfigurierbare Einstellungen – Microsoft Managed Desktop

Microsoft Managed Desktop werden Einstellungen und Richtlinien bereitgestellt, die auf alle Geräte angewendet werden, die von Microsoft Managed Desktop. Weitere Informationen finden Sie unter [Gerätekonfiguration](../service-description/device-policies.md).

Konfigurierbare Einstellungen in Microsoft Managed Desktop IT-Administratoren eine Möglichkeit zum Anpassen und Bereitstellen von Einstellungen, die für ihre Organisations- und Geschäftsanforderungen einzigartig sind. Diese Einstellungen sind zusätzlich zu gerätekonfigurationseinstellungen und -richtlinien, die von der Microsoft Managed Desktop.  

Konfigurierbare Einstellungsänderungen werden in der Cloud vorgenommen und auf Ihre Microsoft Managed Desktop in definierten Bereitstellungsgruppen angewendet. Dieser Vorgang ähnelt der Microsoft Managed Desktop von Änderungen an Gerätekonfigurationseinstellungen und -richtlinien, die vom Dienst definiert und verwaltet werden. Mit demselben Prozess, den Microsoft Managed Desktop für die Bereitstellung von Änderungen verwendet, setzen Sie Ihre Organisation mithilfe moderner IT-Verwaltungspraktiken fort.

## <a name="when-to-use-configurable-settings"></a>Wann können konfigurierbare Einstellungen verwendet werden?

Es gibt einige Male, um konfigurierbare Einstellungen zu verwenden. 

**Onboardingprozess–** Microsoft Managed Desktop empfiehlt, konfigurierbare Einstellungen anzupassen, wenn Sie das Onboarding für den Microsoft Managed Desktop-Dienst oder beim Onboarding einer großen Anzahl von Geräten (20 oder mehr) vornehmen. Einstellungskategorien werden im Microsoft Managed Desktop konfiguriert. Nachdem Sie das Onboarding vorgenommen haben und Zugriff auf das Administratorportal haben, können Sie entscheiden, welche Einstellungskategorien Sie für Ihre Organisation anpassen möchten, die Änderungen vornehmen, eine Bereitstellung bereitstellen und dann Ihre Änderungen bereitstellen.

**Einstellungen verwalten** – Überprüfen Sie Ihre Einstellungen regelmäßig, und nehmen Sie die erforderlichen Updates vor. Möglicherweise müssen Sie Änderungen vornehmen, um eine Änderung in Ihrem Unternehmen zu unterstützen.   

## <a name="setting-categories"></a>Festlegen von Kategorien

Dies sind die konfigurierbaren Einstellungskategorien, die Sie anpassen können:
- [Desktophintergrundbild](config-setting-ref.md#desktop-background-picture) – Passen Sie das Desktophintergrundbild für Microsoft Managed Desktop an. 
- [Browserstartseiten](config-setting-ref.md#browser-start-pages) – Fügen Sie Startseiten hinzu, die mit Microsoft Edge. Siehe Browser-Startseite
- [Enterprise - Websiteliste für den Modus](config-setting-ref.md#enterprise-mode-site-list-location) – Hinzufügen von Websites und deren Kompatibilitätsmodus. Websites in der Liste werden in Internet Explorer gestartet. 
- [Vertrauenswürdige Websites](config-setting-ref.md#trusted-sites) – Fügen Sie vertrauenswürdige Websites hinzu, und legen Sie Sicherheitszonen für jede Website ein. 
- [Proxywebsiteausnahmen](config-setting-ref.md#proxy) – Richten Sie Die Adresse und Portnummer des Proxyservers ein, und fügen Sie Proxywebsiteausnahmen hinzu.

Jede Einstellungskategorie kann individuell angepasst und bereitgestellt werden. Sie können Änderungen an mehreren Einstellungskategorien gleichzeitig bereitstellen. Sie können jedoch nur eine Änderung gleichzeitig für eine Einstellungskategorie bereitstellen.

Beispiel:
- Sie können Änderungen an Desktophintergrundbild und vertrauenswürdigen Websites gleichzeitig als eigene Bereitstellung bereitstellen. 
- Sie können zwei Bereitstellungen nicht gleichzeitig auf Browserstartseiten bereitstellen. Die neueste Bereitstellung beendet frühere Bereitstellungen, die noch ausgeführt werden.

## <a name="configurable-setting-process"></a>Konfigurierbarer Einstellungsprozess

Microsoft Managed Desktop empfiehlt, bei der Verwendung konfigurierbarer Einstellungen für Ihre Organisation einen Prozess wie den folgenden zu folgen:

**Schritt 1 – Planen –** Erfahren Sie mehr über konfigurierbare Einstellungen, und entscheiden Sie, welche Einstellungskategorien Sie für Ihre Organisation konfigurieren möchten. Erstellen Sie eine Zeitachse, wann Änderungen an jeder Gruppe bereitgestellt werden. Planen Sie die Kommunikation mit Ihren Benutzern, die Ihren internen Änderungsverwaltungsprozessen entspricht. Wenn Sie beispielsweise Browserstartseiten hinzufügen, teilen Sie Ihren Benutzern mit, dass sie nach der Bereitstellung einen neuen Satz von Startseiten in ihrem Browser haben.  

**Schritt 2 – Konfigurieren und Inszenieren** der Bereitstellung – Nehmen Sie Änderungen an konfigurierbaren Einstellungen im Microsoft Managed Desktop vor. Bereiten Sie die Änderungen vor, damit sie bereit für die Bereitstellung sind. Denken Sie daran, Ihre Benutzer über die Änderungen und darüber zu erfahren, wie die Änderungen ihre Geräteerfahrung ändern.   

Sie konfigurieren und stellen Änderungen im Administratorportal Microsoft Managed Desktop ein. Weitere Informationen finden Sie unter [Customize configurable settings](config-setting-ref.md). 

**Schritt 3 – Kommunizieren von Änderungen** Teilen Sie Ihren Benutzern Informationen zu bevorstehenden Änderungen mit. Führen Sie für jede Bereitstellung die Kommunikation aus, die Teil Ihrer Änderungsverwaltungsprozesse ist. Sie sollten alle Änderungen, die sich auf die Funktionsweise eines Benutzers oder auf deren Geräten ausdingen, klar kommunizieren.

**Schritt 4 – Bereitstellen von Änderungen** – Stellen Sie Ihre Änderungen ab der Testgruppe zur Bereitstellung ihrer Änderungen vor. Mit der Testgruppe können Sie alle Probleme in einer Gruppe mit weniger Geräten überprüfen und beheben, bevor Sie Änderungen an größeren Gerätegruppen bereitstellen. Wenn Probleme auftreten, können Sie die Änderung wiederherstellen, die Einstellung aktualisieren und eine neue Bereitstellung in die Phase bringen. Microsoft Managed Desktop empfiehlt, den strukturierten Ansatz zu befolgen und gruppen in dieser Reihenfolge zu implementieren: Test, First, Fast und dann Broad.   

Alle konfigurierbaren Einstellungen werden über das Microsoft Managed Desktop verwaltet. Weitere Informationen finden Sie unter [Deploy changes](config-setting-deploy.md). 

**Schritt 5 – Nachverfolgen von Änderungen** – Verfolgen Sie den Fortschritt Ihrer Änderungen im Bereitstellungsstatus. Für jede Einstellung können Sie:
- **Nachverfolgen des Fortschritts** – Nachverfolgen des Status nach der Bereitstellung der Änderung. Der Status wird in **In Bearbeitung** geändert, und dann **entweder Complete** oder **Failed**. Wenn bei einer Bereitstellung ein Fehler auftritt, wird automatisch eine Supportanforderung für Microsoft Managed Desktop geöffnet, um das Problem zu untersuchen.  
- **Siehe version deployed** – Jede bereitgestellte Änderung hat eine Versionsnummer.
- **Änderungen wiederherstellen** – Das Zurücksetzen einer Änderung beendet die aktuelle Bereitstellung und setzt alle Gruppen auf die letzten Änderungen zurück, die für alle Gruppen bereitgestellt wurden. Sie setzen ein Rollback auf den zuletzt bekannten Wert für gute Werte.
- **Überprüfen von** Änderungen – Überprüfen Sie nach Abschluss der Bereitstellung, ob die Änderungen wie erwartet angewendet wurden.  

Wenn eine Bereitstellung fehlgeschlagen ist oder Sie eine Änderung nicht wiederherstellen können, öffnen Sie eine [Supportanfrage](admin-support.md) mit Microsoft Managed Desktop Vorgängen. 

Weitere Informationen finden Sie unter [Deploy and track configurable settings](config-setting-deploy.md).

## <a name="additional-resources"></a>Zusätzliche Ressourcen
- [Referenz der konfigurierbaren Einstellungen](config-setting-ref.md) 
- [Bereitstellen konfigurierbarer Einstellungen](config-setting-deploy.md) 
