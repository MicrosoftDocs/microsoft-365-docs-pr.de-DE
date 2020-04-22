---
title: Zuweisen von Berechtigungen für Daten Untersuchungen (Vorschau)
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: In diesem Artikel wird beschrieben, wie Sie die erforderlichen Berechtigungen für die Verwendung des Tools zur Datenermittlung in Microsoft 365 einrichten.
ms.openlocfilehash: 47a7923d38cfa0ea3bad6c4c266f580f8104c429
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637757"
---
# <a name="assign-permissions-for-data-investigations-preview"></a>Zuweisen von Berechtigungen für Daten Untersuchungen (Vorschau)

Für den Zugriff auf eine Daten Untersuchung im Office 365 oder Microsoft 365 Compliance Center müssen Sie Mitglied der Rollengruppe "Data Investigator" sein. Zum Hinzufügen von Mitgliedern zu einer Rollengruppe müssen Sie Mitglied der Rollengruppe "Organisationsverwaltung" sein oder der Rolle "Rollenverwaltung" im Security & Compliance Center zugewiesen sein. Nachdem ein Benutzer ein Mitglied der Rollengruppe "Data Investigator" geworden ist, kann er Untersuchungen erstellen, auf Sie zugreifen und diese durchführen, bei denen Sie Mitglied sind.

So weisen Sie Berechtigungen für die Datenermittlung zu:

1. Wechseln Sie [https://protection.office.com](https://protection.office.com) zu, und melden Sie sich mit den Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation an.

2. Klicken Sie im Security & Compliance Center auf **Berechtigungen**.

3. Klicken Sie auf die Rollengruppe **Daten Ermittler** , und klicken Sie dann neben **Mitglieder** auf der Flyout-Seite auf **Bearbeiten**.

4. Klicken Sie auf **Mitglieder auswählen** , und klicken Sie dann auf **Hinzufügen**. Wählen Sie die Benutzer aus, die Sie als Daten Ermittler hinzufügen möchten, und klicken Sie dann auf **Hinzufügen**.

5. Nachdem Sie alle Benutzer hinzugefügt haben, klicken Sie auf **Fertig** und dann auf **Speichern** , um die Änderungen an der Rollengruppe zu speichern.

> [!NOTE]
> Die Verwaltungsrolle "Data Investigation", die der Rollengruppe "Data Investigator" zugewiesen ist, stellt die erforderlichen Berechtigungen für den Zugriff auf das Tool für die Datenermittlung im Office 365 oder im Microsoft 365 Compliance Center bereit. Standardmäßig ist diese Rolle nicht der Rollengruppe "Organisationsverwaltung" zugewiesen, was bedeutet, dass globale Administratoren in Ihrer Organisation möglicherweise nicht standardmäßig auf das Tool für Daten Ermittlungen zugreifen können. Um dies zu beheben, können Sie der Rollengruppe "Data Investigator" globale Administratoren hinzufügen oder der Rollengruppe "Organisationsverwaltung" die Verwaltungsrolle "Daten Ermittlungsverwaltung" hinzufügen. Eine dritte Option besteht darin, eine benutzerdefinierte Rollengruppe zu erstellen und die Verwaltungsrolle "Data Investigation" (und andere Rollen) zuzuweisen und dann entsprechende Mitglieder hinzuzufügen. Weitere Informationen zu Rollengruppen und Rollen finden Sie unter [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).
