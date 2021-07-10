---
title: Anfordern von Benutzersupport für Microsoft Managed Desktop
description: Wie Benutzer Hilfe zum Dienst und den Geräten erhalten können
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2eea02b0a891f65ccd7e4e993ca719b0f3aa1b8b
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362606"
---
# <a name="getting-help-for-users"></a>Hilfe für Benutzer

Wenn Sie den Punkt im [Workflow](../service-description/user-support.md) erreicht haben, an dem Sie erhöhten Gerätezugriff oder eine Eskalation an Microsoft anfordern müssen, führen Sie die folgenden Schritte aus:
 
>[!NOTE]
>Diese Supportoptionen sind für Geräte in der Testgruppe nicht verfügbar.

## <a name="elevation-requests"></a>Anforderungen für erhöhte Rechte

Bevor Sie erhöhten Zugriff auf ein Gerät anfordern, sollten Sie überprüfen, welche Aktionen am besten geeignet sind.

- **Typische Aktionen** sind das, wofür dieser Prozess vorgesehen ist und routinemäßig ausgeführt werden würde, während Probleme mit Microsoft Managed Desktop Geräten behoben werden. Dazu gehören:
    - Erhöhen der integrierten Systemproblembehandlung, der Eingabeaufforderung oder Windows PowerShell
    - Problembehandlung bei Branchenanwendungen
    - Verwenden einer Problemumgehung zum Korrigieren eines Problems, das entwurfsbedingt funktionieren sollte (z. B. BitLocker-Aktivierung oder Nichtaktualisierung der Systemzeit)
    - Erhöhen des Geräte-Managers zum Aktualisieren von Treibern, Deinstallieren eines Geräts oder Suchen nach neuen Änderungen

- **Aktionen, die nicht empfohlen werden, umfassen Folgendes:**
    - Installieren von Software oder Browsern
    - Installieren von Treibern außerhalb von Windows-Einstellungen, einschließlich treiber für Peripheriegeräte
    - Installieren .msi oder .exe Dateien
    - Installieren Windows Features

- **Aktionen, die nicht unterstützt werden, umfassen Folgendes:**
    - Installieren von Software oder Features, die mit Microsoft Managed Desktop Sicherheits- oder Verwaltungsfunktionen oder -vorgängen in Konflikt geraten
    - Deaktivieren eines Windows Features, das für Microsoft Managed Desktop erforderlich ist, z. B. BitLocker
    - Ändern der von Ihrer Organisation verwalteten Einstellungen

### <a name="to-request-elevation"></a>So fordern Sie erhöhte Rechte an

1. Wechseln Sie zum [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) Portal, und melden Sie sich mit Ihren Azure Active Directory-Anmeldeinformationen an.
2. Wählen Sie **"Neue Rechteerweiterungsanforderung"** aus.
3. Geben Sie diese Details an:
    - **Supportticket-ID** von Ihrem eigenen Support-Ticketingsystem.
    - **Gerätename:** Geben Sie die Seriennummer des Geräts ein, und wählen Sie dann das Gerät aus dem Menü aus.
    - **Kategorie:** Wählen Sie die Kategorie aus, die am besten zu Ihrem Problem passt. Wenn keine Option geschlossen zu sein scheint, wählen Sie **"Andere"** aus, und geben Sie weitere Informationen in den Feldern **"Titel"** und **"Plan der Aktion"** ein. Es empfiehlt sich, nach Möglichkeit eine Kategorie auszuwählen.
    - **Unterkategorie:** Wählen Sie diejenige aus, die am besten zu dem Problem passt. Wenn keine Option geschlossen zu sein scheint, wählen Sie **Andere** aus, und geben Sie unter **"Titel"** eine kurze Beschreibung ein. Geben Sie **im Aktionsplan** die Schritte zur Problembehandlung an, die Sie nach Erteilung der Rechteerweiterung ausführen möchten.
4. Wählen Sie **Senden** aus.


## <a name="escalation-requests"></a>Eskalationsanforderungen


Wenn Sie ein Problem an Microsoft [eskalieren](../service-description/user-support.md#escalation-portal) müssen, führen Sie die folgenden Schritte aus:

1. Wechseln Sie zum [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) Portal, und melden Sie sich mit Ihren Azure Active Directory-Anmeldeinformationen an.
2. Wählen Sie **Eskalationsanforderungen aus,** und wählen Sie dann **neue Eskalationsanforderung** aus.
3. Geben Sie diese Details an:
    - **Kategorie:** Wählen Sie die Kategorie aus, die am besten zu Ihrem Problem passt.
    - **Titel:** Geben Sie eine sehr kurze Beschreibung an.
    - **Beschreibung:** Fügen Sie alle zusätzlichen Details hinzu, die unserem Team helfen könnten, das Problem zu verstehen. Wenn Sie Dateien anfügen müssen, können Sie dies tun, indem Sie nach der Übermittlung zur Anforderung zurückkehren.
    - **Primäre Kontaktinformationen:** Geben Sie Informationen dazu an, wie Sie die Hauptperson kontaktieren, die für die Arbeit mit unserem Team verantwortlich ist.
4. Wählen Sie **Senden** aus.
5. Besuchen Sie das Ticket im selben Portal erneut, um mit unserem Team zu interagieren.

> [!NOTE]
> Nur Probleme mit Schweregrad C können über diesen Pfad eskaliert werden. Wenden Sie sich bei anderen Problemen an Ihren IT-Administrator, um die Anforderung über das Verwaltungsportal zu übermitteln.