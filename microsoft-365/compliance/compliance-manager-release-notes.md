---
title: Anmerkungen zur Microsoft Compliance-Manager-Version
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Der Microsoft Compliance-Manager ist ein kostenloses Workflow basiertes Risiko Bewertungstool im Microsoft-Dienst Vertrauensstellungs Portal. Mit dem Compliance-Manager können Sie behördliche Compliance-Aktivitäten im Zusammenhang mit Microsoft Cloud Services nachverfolgen, zuweisen und überprüfen.
ms.openlocfilehash: 1a490212b2275b9f297e2585e7242f5331d0fe56
ms.sourcegitcommit: 5c6c30ec5541d2fb77e53a1309db1fe7b75fc3e2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2019
ms.locfileid: "38686050"
---
# <a name="release-notes-for-compliance-manager-preview"></a>Anmerkungen zur Version für Compliance-Manager (Vorschau)

Die Public Preview of Compliance Manager bietet Ihnen frühzeitigen Zugriff auf bevorstehende Funktionen und Updates.

Sie können das aktualisierte [Compliance-Manager-](https://servicetrust.microsoft.com/ComplianceManager) Tool im [Dienst Vertrauensstellungs Portal](https://servicetrust.microsoft.com) zum Nachverfolgen, zuweisen und Überprüfen von behördlichen Compliance-Aktivitäten im Zusammenhang mit Microsoft Cloud Services verwenden.

## <a name="whats-new-in-compliance-manager-preview"></a>Neuerungen im Compliance-Manager (Vorschau)

- **Rollenbasierter Zugriff auf den Compliance-Manager:** Die standardmäßige **Gastzugriffs** Rolle wurde entfernt. Damit ein Benutzer auf den Compliance-Manager zugreifen kann, muss der globale Administrator [jedem Benutzer eine Berechtigung zuweisen](compliance-manager-overview.md#permissions).

- **Aktualisierte Kompatibilitätsbewertung**: das Kompatibilitäts Ergebnis enthält jetzt Ergebnisse für von Microsoft verwaltete Aktionen. Ihre Punktzahl wird dadurch zunehmen.

- **Actions-Elemente:** Aktionselemente sind jetzt einzelne Elemente, und viele umfassen die Telemetrie-Sammlung aus der Microsoft Secure Score Graph-API. Wenn möglich, werden Empfehlungen zur technischen Aktion nun Links zur entsprechenden Konfigurationsseite im Office 365-Dienst angezeigt.

- **Mandantenverwaltung:** Neue Schnittstelle zum Verwalten neuer Datenelemente im Compliance-Manager (Preview):
    - **Dimensionen:** Anzeigen, hinzufügen und Anpassen von Metadaten für Vorlagen, BEWERTUNGEN und Aktionselemente, mit denen Sie benutzerdefinierte Pivots für Filter erstellen können.
    - **Besitzer:** Geben Sie einen Besitzer für jedes Aktionselement an.
    - **Aktionen für Kunden:** Verwalten Sie die vollständige Liste der Aktionen, die in Compliance-Manager (Preview) enthalten sind, und aktivieren/deaktivieren Sie die Überwachung sicherer Bewertungen für Aktionselemente, die mit Secure Score integriert sind.

## <a name="known-issues-in-compliance-manager-preview"></a>Bekannte Probleme im Compliance-Manager (Vorschau)

In den folgenden Abschnitten werden bekannte Probleme behandelt, die in bevorstehenden Versionen von Compliance-Manager behoben werden sollten.

### <a name="compliance-score"></a>Kompatibilitätsbewertung

- Bei Aktionselementen, die als " **nicht im Bereich**" gekennzeichnet sind, wird die dem Aktionselement zugewiesene Bewertung nicht aus der Berechnung der Konformitätsbewertung ausgeschlossen. Aktionselemente, die **nicht im Bereich** gekennzeichnet sind, verbessern nicht die Konformitätsbewertung.

### <a name="secure-score"></a>Sicherheitsbewertung

- Sichere Ergebnis Ergebnisse sind für einige Aktionselemente in bestimmten Microsoft 365-und Office 365-Abonnements nicht verfügbar. In diesen Fällen konnte das sichere Ergebnis Ergebnis **nicht erkannt werden** .
- Manchmal werden sichere Ergebnis Ergebnisse für die entsprechenden Richtlinien und Aktionselemente nicht abgeschlossen zurückgegeben.
- Für neue Mandanten ist die Sicherung der Bewertungs Aktualisierungen für alle Aktionen automatisch aktiviert. Der globale Administrator kann die Option für die kontinuierliche Aktualisierung sicherer Bewertungen auf aus festlegen, wodurch Updates für alle Aktionen deaktiviert werden.
- Wenn Secure Score Updates aktiviert sind, werden Aktionen aktiv durch Secure Score überwacht, obwohl das Test Datum der Aktion nicht aktualisiert wird, um die Überwachung widerzuspiegeln.
- Wenn neue Bewertungen erstellt werden, enthalten Scores automatisch von Microsoft verwaltete Steuerpunkte und die Integration sicherer Bewertungen.

### <a name="microsoft-managed-controls"></a>Von Microsoft verwaltete Steuerelemente

- Das Testdatum für von Microsoft verwaltete Steuerelemente wird nicht in der Benutzeroberfläche angezeigt, auch wenn diese in die Bewertung einbezogen werden. Wenn Sie Informationen zum Test Datum anzeigen möchten, müssen Sie die Bewertung exportieren.

### <a name="customization"></a>Anpassung

- Durch das Hinzufügen von benutzerdefinierten Steuerelementen kann ein neues Steuerelement einer vorhandenen Steuerelement Familie hinzugefügt werden, es ist jedoch nicht möglich, eine neue Steuerelement Familie hinzuzufügen.
- In dieser Version wird das Verknüpfen von Aktionselementen oder das Hinzufügen von Aktionen Elementen oder Steuerelementen zu einer Bewertung nicht unterstützt.
- Wenn Sie eine benutzerdefinierte Aktion erstellen, können Sie Sie nicht bearbeiten oder löschen.

### <a name="control-families-not-shown-in-assessments"></a>Steuern von Familien, die in Bewertungen nicht angezeigt werden

- Wenn Sie eine Vorlage importieren, spiegeln alle auf dieser Vorlage basierenden Bewertungen alle Steuerelementfamilien wider, die Teil der Vorlage sind. Wenn Sie der Vorlage jedoch neue Steuerelementfamilien hinzufügen, werden die Änderungen in vorhandenen Bewertungen nicht berücksichtigt. Nur neue Bewertungen, die aus der aktualisierten Vorlage erstellt wurden, spiegeln die Änderungen wider.

### <a name="templates"></a>Vorlagen

- Beim Erstellen einer Vorlage müssen Sie Dimensionen für **Produkt** und **Zertifizierung** einschließen, um sicherzustellen, dass Ihre Vorlage im Kompatibilitäts Bewertungsergebnis angezeigt wird.
- Archivierte Vorlagen können bearbeitet werden, und Sie sollten nicht bearbeitbar sein.
- Gesperrte Vorlagen ermöglichen eine Beurteilungs Erstellung, wenn Sie dies nicht tun sollten. Das Sperren einer Vorlage soll verhindern, dass Sie zum Erstellen von Bewertungen verwendet wird.

### <a name="export"></a>Exportieren

- Der Vorlagenexport in JSON schlägt fehl, wenn der Vorlagenstatus auf " **importiert** " oder " **Ausstehende Genehmigung**" festgelegt ist.

### <a name="supported-browsers"></a>Unterstützte Browser

- Die neuesten Versionen von Microsoft Edge, Chrome und Safari werden unterstützt.
- Es gibt möglicherweise Fälle, in denen aktualisierte Daten erst angezeigt werden, wenn Ihr Browser aktualisiert wurde.
- Die Preview-Version von Microsoft Edge wird nicht unterstützt, aber es sind keine bekannten Probleme aufgetreten.
- Internet Explorer wird nicht unterstützt.

### <a name="session-timeout"></a>Sitzungstimeout

- Wenn ein Timeout für eine Sitzung auftritt, wird möglicherweise der Fehler "etwas ging falsch" angezeigt. Um zu beheben, gehen Sie zu [Compliance-Manager](https://servicetrust.microsoft.com/ComplianceManager) , und melden Sie sich erneut an.
 
### <a name="language-support"></a>Sprachunterstützung

- Alle Sprachen werden für alle Webseiten nicht unterstützt. Wenn Ihre lokale Sprache nicht unterstützt wird, zeigen Sie in US-Englisch an.