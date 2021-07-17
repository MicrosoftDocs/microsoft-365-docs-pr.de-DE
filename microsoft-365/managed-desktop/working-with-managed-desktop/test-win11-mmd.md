---
title: Vorschau und Test Windows 11 mit Microsoft Managed Desktop
description: So erhalten Sie Windows 11 in Ihrer Umgebung
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 8dee18909d82656bcfb3e63fdc078328c678e660
ms.sourcegitcommit: ea8de1b48adb6df92fb9351ea862184a9f16cbbb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2021
ms.locfileid: "53461387"
---
# <a name="preview-and-test-windows-11-with-microsoft-managed-desktop"></a>Vorschau und Test Windows 11 mit Microsoft Managed Desktop

 Registrieren und Teilnehmen am Windows 11-Kompatibilitätstestprogramm in Ihrer Microsoft Managed Desktop Umgebung. Weitere Informationen zu Windows 11 und Microsoft Managed Desktop im Allgemeinen finden Sie unter [Windows 11 und Microsoft Managed Desktop.](../intro/win11-overview.md) 

## <a name="check-device-eligibility"></a>Überprüfen der Geräteberechtigung

Bisher erfüllen mehr als 95 % der Microsoft Managed Desktop Geräte [die Berechtigungskriterien für Windows 11.](/windows/whats-new/windows-11-requirements) Sie können Details zum Berechtigungsstatus Ihrer Geräte von Microsoft Managed Desktop anfordern. Führen Sie die folgenden Schritte aus, um die Anforderung zu übermitteln:

1. Öffnen Sie eine neue Serviceanfrage mit dem Microsoft Managed Desktop Service Engineering-Team. Wenn Sie weitere Informationen zum Einreichen der Anforderung benötigen, lesen Sie den [Administratorsupport.](admin-support.md)
2. Verwenden Sie diese Werte für die Felder:
    - Titel: Windows 11 Geräteberechtigung
    - Anforderungstyp: Anforderung von Informationen
    - Kategorie: Geräte
    - Unterkategorie: Sonstige


## <a name="add-devices-to-the-windows-11-test-group"></a>Hinzufügen von Geräten zur Testgruppe Windows 11

Fügen Sie zunächst Geräte zur Gerätegruppe (**\[ Modern Workplace Windows \] 11 Pre-Release Test Devices**) hinzu, die zum Testen und Auswerten Windows 11 erstellt wurde. Geräte in dieser Gruppe erhalten neue Windows 11-Builds und Microsoft Managed Desktop Basiskonfigurationen, sobald sie verfügbar sind und auf Zuverlässigkeitsprobleme überwacht werden.

Sie können jedes Ihrer vorhandenen oder neuen Geräte für Windows 11-Tests auswählen, sie sollten jedoch aufgrund des erhöhten Risikos von Fehlern oder Kompatibilitätsproblemen in Vorabversionen keine Produktionsgeräte in dieser Gruppe registrieren. Vorherige Gerätegruppenzuweisungen werden nach der Zuweisung zu dieser Gruppe entfernt.

So registrieren Sie Ihre Geräte in der Vorabversion der Testgruppe:

1. Öffnen Sie eine neue Serviceanfrage mit dem Microsoft Managed Desktop Service Engineering-Team.
2. Verwenden Sie diese Werte für die Felder:
    - Titel: Windows 11-Kompatibilitätsregistrierung
    - Anforderungstyp: Änderungsanforderung
    - Kategorie: Geräte
    - Unterkategorie: Bereitstellungsgruppenzuweisung
3. Listen Sie im Beschreibungsfeld die Seriennummern der Geräte auf, die Sie für Windows 11-Tests verwenden möchten. Beachten Sie, welche der angegebenen Geräte ggf. noch nicht in Ihrem Microsoft Managed Desktop Mandanten bereitgestellt werden.

## <a name="prioritize-applications-to-submit-to-test-base"></a>Priorisieren von Anwendungen, die an die Testbasis übermittelt werden sollen

Unternehmenskritische Anwendungen sind die besten Kandidaten für eine weitere Überprüfung in einer geschlossenen Windows 11-Umgebung. Wir können Ihnen helfen, Apps für Windows 11-Tests basierend auf Nutzungs- und Zuverlässigkeitsdaten zu priorisieren. Gehen Sie folgendermaßen vor, um unsere Empfehlungen anzufordern:

1. Öffnen Sie eine neue Serviceanfrage mit dem Microsoft Managed Desktop Service Engineering-Team. Wenn Sie weitere Informationen zum Einreichen der Anforderung benötigen, lesen Sie den [Administratorsupport.](admin-support.md)
2. Verwenden Sie diese Werte für die Felder:
    - Titel: Windows 11 TestBasiskandidaten
    - Anforderungstyp: Anforderung von Informationen
    - Kategorie: Apps
    - Unterkategorie: Sonstige

## <a name="report-issues"></a>Probleme melden

Wenn Windows 11 Kompatibilitätsprobleme mit Ihren Branchen- oder Microsoft 365-Apps auftreten, melden Sie diese uns zur Untersuchung und Behebung. Führen Sie die folgenden Schritte aus, um ein Problem zu melden:

1. Öffnen Sie eine neue Serviceanfrage mit dem Microsoft Managed Desktop Service Engineering-Team.
2. Verwenden Sie diese Werte für die Felder:
    - Titel: Windows 11-Kompatibilitätstests
    - Anforderungstyp: Vorfall
    - Kategorie: Geräte
    - Unterkategorie: Windows Upgrade/Update
3. Beschreiben Sie das Verhalten und wie stark es Ihr Unternehmen in einer Produktionsumgebung beeinträchtigen würde.

Microsoft Managed Desktop triages and handles issues with pre-release builds based on the effect on productivity. Während sich unsere Dienstbeschreibung nicht auf Probleme mit Vorabversionen bezieht, werden wir uns mit Kundenadministratoren beraten, um sicherzustellen, dass Probleme, die die Produktivität des Benutzers beeinträchtigen, vor beginn der Migration innerhalb eines bestimmten Mandanten behoben werden.
