---
title: Erstellen und Verwalten von Rollen für die rollenbasierte Zugriffssteuerung
description: Erstellen von Rollen und Definieren der Berechtigungen, die der Rolle als Teil der rollenbasierten Zugriffssteuerungsimplementierung im Microsoft Defender Security Center zugewiesen sind
keywords: Benutzerrollen, Rollen, Access rbac
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 932fd6ecd7dca66f4cb587b226474109c788c341
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065951"
---
# <a name="create-and-manage-roles-for-role-based-access-control"></a>Erstellen und Verwalten von Rollen für die rollenbasierte Zugriffssteuerung

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-roles-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="create-roles-and-assign-the-role-to-an-azure-active-directory-group"></a>Erstellen von Rollen und Zuweisen der Rolle zu einer Azure Active Directory-Gruppe

In den folgenden Schritten erfahren Sie, wie Sie Rollen in Microsoft Defender Security Center erstellen. Es wird davon ausgegangen, dass Sie bereits Azure Active Directory-Benutzergruppen erstellt haben.

1. Melden Sie sich [beim Microsoft Defender Security Center mit](https://securitycenter.windows.com/) einem Konto an, dem ein Sicherheitsadministrator oder eine globale Administratorrolle zugewiesen ist.

2. Wählen Sie im Navigationsbereich Einstellungen **> Rollen aus.**

3. Wählen **Sie Element hinzufügen aus.**

4. Geben Sie den Rollennamen, die Beschreibung und die Berechtigungen ein, die Sie der Rolle zuweisen möchten.

5. Wählen **Sie Weiter** aus, um die Rolle einer Azure AD-Sicherheitsgruppe zuzuordnen.

6. Verwenden Sie den Filter, um die Azure AD-Gruppe auszuwählen, die Sie dieser Rolle hinzufügen möchten.

7. **Speichern und schließen** Sie .

8. Wenden Sie die Konfigurationseinstellungen an.

> [!IMPORTANT]
> Nach dem Erstellen von Rollen müssen Sie eine Gerätegruppe erstellen und zugriff auf die Gerätegruppe bereitstellen, indem Sie sie einer Rolle zuweisen, die Sie gerade erstellt haben.

### <a name="permission-options"></a>Berechtigungsoptionen

- **Anzeigen von Daten**
    - **Sicherheitsvorgänge** – Anzeigen aller Daten zu Sicherheitsvorgängen im Portal
    - **Bedrohungs- und Sicherheitsrisikoverwaltung** – Anzeigen von Daten zur Verwaltung von Bedrohungen und Sicherheitslücken im Portal

- **Aktive Korrekturaktionen**
    - **Sicherheitsvorgänge** – Ergreifen von Reaktionsaktionen, Genehmigen oder Schließen ausstehender Korrekturaktionen, Verwalten zulässiger/blockierter Listen für Automatisierung und Indikatoren
    - **Bedrohungs- und Sicherheitsrisikoverwaltung – Ausnahmebehandlung** – Erstellen neuer Ausnahmen und Verwalten aktiver Ausnahmen
    - **Bedrohungs- und Sicherheitsrisikoverwaltung – Behandlung** von Abhilfemaßnahmen – Übermitteln neuer Behebungsanforderungen, Erstellen von Tickets und Verwalten vorhandener Abhilfemaßnahmen

- **Warnungsuntersuchung** : Verwalten von Warnungen, Initiieren automatisierter Untersuchungen, Ausführen von Scans, Sammeln von Untersuchungspaketen, Verwalten von Gerätetags und Herunterladen nur portabler ausführbarer Dateien (PE) 

- **Verwalten von Portalsystemeinstellungen** : Konfigurieren von Speichereinstellungen, SIEM- und Bedrohungs-INTEL-API-Einstellungen (gilt global), erweiterten Einstellungen, automatisierten Dateiuploads, Rollen und Gerätegruppen

    > [!NOTE]
    > Diese Einstellung ist nur in der Microsoft Defender for Endpoint-Administratorrolle (Standard) verfügbar.

- **Verwalten von Sicherheitseinstellungen im Security Center** – Konfigurieren von Einstellungen für die Warnungsunterdrückung, Verwalten von Ordnerausschlüssen für Automatisierungs-, Onboard- und Offboardgeräte sowie Verwalten von E-Mail-Benachrichtigungen, Verwalten der Evaluierungsumgebung

- **Liveantwortfunktionen**
    - **Grundlegende** Befehle:
        - Starten einer Liveantwortsitzung
        - Ausführen von schreibgeschützten Liveantwortbefehlen auf einem Remotegerät (ohne Dateikopie und Ausführung)
    - **Erweiterte** Befehle:
        - Herunterladen einer Datei vom Remotegerät per Liveantwort
        - Herunterladen von PE- und Nicht-PE-Dateien von der Dateiseite
        - Hochladen einer Datei auf das Remotegerät
        - Anzeigen eines Skripts aus der Dateibibliothek
        - Ausführen eines Skripts auf dem Remotegerät aus der Dateibibliothek

Weitere Informationen zu den verfügbaren Befehlen finden Sie unter [Untersuchen von Geräten mithilfe der Liveantwort](live-response.md).
  
## <a name="edit-roles"></a>Bearbeiten von Rollen

1. Melden Sie sich [beim Microsoft Defender Security Center mithilfe eines](https://securitycenter.windows.com/) Kontos an, dem der Sicherheitsadministrator oder die globale Administratorrolle zugewiesen ist.

2. Wählen Sie im Navigationsbereich Einstellungen **> Rollen aus.**

3. Wählen Sie die Rolle aus, die Sie bearbeiten möchten.

4. Klicken Sie auf **Bearbeiten**.

5. Ändern Sie die Details oder Gruppen, die der Rolle zugewiesen sind. 

6. Klicken **Sie auf Speichern und schließen.**

## <a name="delete-roles"></a>Löschen von Rollen

1. Melden Sie sich [beim Microsoft Defender Security Center mithilfe eines](https://securitycenter.windows.com/) Kontos an, dem der Sicherheitsadministrator oder die globale Administratorrolle zugewiesen ist.

2. Wählen Sie im Navigationsbereich Einstellungen **> Rollen aus.**

3. Wählen Sie die Rolle aus, die Sie löschen möchten.

4. Klicken Sie auf die Dropdownschaltfläche, und wählen Sie **Rolle löschen aus.**

## <a name="related-topic"></a>Verwandtes Thema

- [Grundlegende Benutzerberechtigungen für den Zugriff auf das Portal](basic-permissions.md)
- [Erstellen und Verwalten von Gerätegruppen](machine-groups.md)
