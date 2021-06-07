---
title: Berechtigungen im Microsoft 365 Compliance Center
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
localization_priority: Normal
description: Erfahren Sie mehr über das Verwalten von Berechtigungen im Microsoft 365 Compliance Center.
ms.collection: M365-security-compliance
ms.openlocfilehash: 7038863c0cbcaf99cf07072445a3b001e7b8ca0b
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782849"
---
# <a name="permissions-in-the-microsoft-365-compliance-center"></a>Berechtigungen im Microsoft 365 Compliance Center

Das Microsoft 365 Compliance Center wurde kürzlich aktualisiert und unterstützt jetzt die direkte Verwaltung von Berechtigungen für Benutzer, die Compliance-Aufgaben in Microsoft 365 ausführen. Dieses Update bedeutet, dass Sie das Office 365 Security & Compliance Center nicht mehr verwenden müssen, um Berechtigungen für Compliance-Lösungen zu verwalten. Über die neue Seite **"Berechtigungen"** im Microsoft 365 Compliance Center können Sie Berechtigungen für Benutzer für Complianceaufgaben in Features wie Geräteverwaltung, Verhinderung von Datenverlust, eDiscovery, Insider-Risikomanagement, Aufbewahrung und vielen anderen verwalten. Benutzer können nur die Complianceaufgaben ausführen, auf die Sie ihnen explizit Zugriff gewähren.

Um die Registerkarte **"Berechtigungen"** im Microsoft 365 Compliance Center anzuzeigen, müssen Benutzer ein globaler Administrator sein oder der *Rollenverwaltungsrolle* zugewiesen werden (eine Rolle wird nur der Rollengruppe *"Organisationsverwaltung"* zugewiesen). Mit der *Rollenverwaltungsrolle* können Benutzer Rollengruppen anzeigen, erstellen und ändern.

![Seite "Berechtigungen" im Microsoft 365 Compliance Center](../media/m365-compliance-center-permissions.png)

Berechtigungen im Microsoft 365 Compliance Center basieren auf dem Rollenbasierten Zugriffssteuerungsmodell (RBAC). RBAC ist das gleiche Berechtigungsmodell, das von den meisten Microsoft 365-Diensten verwendet wird. Wenn Sie also mit der Berechtigungsstruktur in diesen Diensten vertraut sind, ist ihnen das Gewähren von Berechtigungen im Microsoft 365 Compliance Center vertraut. Es ist wichtig zu beachten, dass die im Microsoft 365 Compliance Center verwalteten Berechtigungen nicht die Verwaltung aller in jedem einzelnen Dienst benötigten Berechtigungen abdecken. Sie müssen weiterhin bestimmte dienstspezifische Berechtigungen im Admin Center für den jeweiligen Dienst verwalten. Wenn Sie beispielsweise Berechtigungen für Archivierungs-, Überwachungs- und MRM-Aufbewahrungsrichtlinien zuweisen müssen, müssen Sie diese Berechtigungen im Exchange Admin Center verwalten.

## <a name="relationship-of-members-roles-and-role-groups"></a>Beziehung zwischen Mitgliedern, Rollen und Rollengruppen

Eine Rolle gewährt Berechtigungen zum Ausführen einer Reihe von Aufgaben. Mit der Rolle "Fallverwaltung" können Benutzer beispielsweise mit eDiscovery-Fällen arbeiten.

Eine Rollengruppe ist eine Reihe von Rollen, die es Benutzern ermöglichen, ihre Aufgaben über Compliancelösungen hinweg im Microsoft 365 Compliance Center zu erledigen. Beispielsweise werden durch Hinzufügen von Benutzern zur Rollengruppe *"Insider-Risikomanagement"* designierte Administratoren, Analysten, Ermittler und Auditoren für die erforderlichen Berechtigungen für das Insider-Risikomanagement in einer einzelnen Gruppe konfiguriert. Das Microsoft 365 Compliance Center enthält Standardrollengruppen für Aufgaben und Funktionen für jede Compliancelösung, der Sie Personen zuweisen müssen. Im Allgemeinen wird empfohlen, einzelne Benutzer bei Bedarf einfach als Mitglieder zu den standardmäßigen Compliance-Rollengruppen hinzuzufügen.

![Diagramm mit dem Verhältnis von Rollengruppen zu Rollen und Elementen](../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="permissions-needed-to-use-features-in-the-microsoft-365-compliance-center"></a>Erforderliche Berechtigungen für die Verwendung von Features im Microsoft 365 Compliance Center

Informationen zum Anzeigen aller Standardrollengruppen, die im Microsoft 365 Compliance Center verfügbar sind, und der Rollen, die den Rollengruppen standardmäßig zugewiesen sind, finden Sie unter den [Berechtigungen im Security & Compliance Center.](/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)

Die Verwaltung von Berechtigungen im Microsoft 365 Compliance Center gewährt Benutzern nur Zugriff auf die Compliance-Features, die im Microsoft 365 Compliance Center verfügbar sind. Wenn Sie anderen Features, die sich nicht im Microsoft 365 Compliance Center befinden, Berechtigungen erteilen möchten, z. B. Exchange Nachrichtenflussregeln (auch als Transportregeln bezeichnet), müssen Sie das Exchange Admin Center verwenden.

## <a name="azure-roles-in-the-microsoft-365-compliance-center"></a>Azure-Rollen im Microsoft 365 Compliance Center

Die Rollen, die im Abschnitt **"Azure**  >  **AD-Rollen"** auf der Seite **"Berechtigungen** für das Microsoft 365 Compliance Center" angezeigt werden, sind Azure Active Directory Rollen. Diese Rollen sind so konzipiert, dass Sie den Aufgaben in der IT-Gruppe Ihrer Organisation entsprechen, sodass einer Person ganz einfach alle Berechtigungen gewährt werden können, die sie für ihre Arbeit benötigt. Sie können die derzeit jeder Rolle zugewiesenen Benutzer anzeigen, indem Sie eine Administratorrolle auswählen und die Details des Rollenbereichs anzeigen. Um Mitglieder einer Azure AD-Rolle zu verwalten, wählen Sie "Mitglieder in Azure AD verwalten" aus. Diese Auswahl leitet Sie an das Azure-Verwaltungsportal weiter.

|Rolle|Beschreibung|
|:---|:----------|
|**Globaler Administrator**|Zugriff auf alle Verwaltungsfunktionen in allen Microsoft 365-Diensten. Nur globale Administratoren können weitere Administratorrollen zuweisen. Weitere Informationen finden Sie unter [Globaler Administrator/Unternehmensadministrator](/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator).|
|**Compliancedatenadministrator**|Verfolgen Sie die Daten Ihrer Organisation in Microsoft 365 nach, stellen Sie sicher, dass sie geschützt sind, und erhalten Sie Einblicke in alle Probleme, um Risiken zu minimieren. Weitere Informationen finden Sie unter [Compliancedatenadministrator](/azure/active-directory/roles/permissions-reference#compliance-data-administrator).|
|**Complianceadministrator**|Tragen Sie dazu bei, dass Ihre Organisation alle behördlichen Bestimmungen einhält und eDiscovery-Fälle verwalten sowie Richtlinien zur Datengovernance über Microsoft 365-Standorte, -Identitäten und -Apps hinweg aufrechterhalten kann. Weitere Informationen finden Sie unter [Complianceadministrator](/azure/active-directory/roles/permissions-reference#compliance-administrator).|
|**Sicherheitsoperator**|Zeigen Sie aktive Bedrohungen für Ihre Microsoft 365-Benutzer, -Geräte und -Inhalte an und untersuchen und reagieren Sie auf sie. Weitere Informationen finden Sie unter [Sicherheitsoperator](/azure/active-directory/roles/permissions-reference#security-operator).|
|**Benutzer mit Leseberechtigung für Sicherheitsfunktionen**|Zeigen Sie aktive Bedrohungen für Ihre Microsoft 365-Benutzer, -Geräte und -Inhalte an und untersuchen Sie diese; Sie besitzen jedoch (im Gegensatz zum Sicherheitsoperator) keine Berechtigung dazu, dagegen Maßnahmen zu ergreifen. Weitere Informationen finden Sie unter [Benutzer mit Leseberechtigung für Sicherheitsfunktionen](/azure/active-directory/roles/permissions-reference#security-reader).|
|**Sicherheitsadministrator**|Steuern Sie die Gesamtsicherheit Ihres Unternehmens, indem Sie Sicherheitsrichtlinien verwalten, Sicherheitsanalysen und Berichte zu Microsoft 365-Produkten überprüfen und im Hinblick auf Bedrohungen immer auf dem neuesten Stand bleiben. Weitere Informationen finden Sie unter [Sicherheitsadministrator](/azure/active-directory/roles/permissions-reference#security-administrator).|
|**Globaler Leser**|Die Version mit reiner Leseberechtigung der Rolle **globaler Administrator**. Zeigen Sie alle Einstellungen und Verwaltungsinformationen in Microsoft 365 an. Weitere Informationen finden Sie unter [Globaler Leser](/azure/active-directory/roles/permissions-reference#global-reader).|
|**Angriffssimulationsadministrator**|Erstellen und verwalten Sie alle Aspekte einer Angriffssimulation: Erstellung und Einführung/Planung einer Simulation sowie Überprüfung der Ergebnisse von Simulationen. Weitere Informationen finden Sie unter [Angriffssimulationsadministrator](/azure/active-directory/roles/permissions-reference#attack-simulation-administrator).|
|**Angriffsnutzlastautor**|Erstellen Sie Angriffsnutzlasten, ohne sie tatsächlich zu starten oder zu planen. Weitere Informationen finden Sie unter [Angriffsnutzlastautor](/azure/active-directory/roles/permissions-reference#attack-payload-author).|
|

## <a name="add-users-to-a-compliance-role-group"></a>Hinzufügen von Benutzern zu einer Compliance-Rollengruppe

Führen Sie die folgenden Schritte aus, um Einer Compliance-Rollengruppe Benutzer hinzuzufügen:

1. Melden Sie sich mit den Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365 Organisation beim Berechtigungsbereich des [Microsoft 365 Compliance Centers](https://compliance.microsoft.com/permissions) an.
2. Wechseln Sie im Microsoft 365 Compliance Center zu **"Berechtigungen".** Wählen Sie den Link aus, um Compliancerollen in Microsoft 365 anzuzeigen und zu verwalten.
3. Erweitern Sie den Abschnitt **"Compliance Center",** und wählen Sie **"Rollen"** aus.
4. Wählen Sie auf der Rollenseite des **Compliance Centers** eine Compliance-Rollengruppe aus, der Sie Benutzer hinzufügen möchten, und wählen Sie dann im Detailbereich die **Rollengruppe bearbeiten** aus.
5. Wählen Sie Im linken Navigationsbereich **"Mitglieder auswählen"** und dann **"Bearbeiten"** aus.
6. Wählen Sie **"Hinzufügen"** aus, und aktivieren Sie dann das Kontrollkästchen für alle Benutzer, die Sie der Rollengruppe hinzufügen möchten.
7. Wählen Sie **Hinzufügen** aus, und klicken Sie dann auf **Fertig**.
8. Wählen Sie **"Speichern"** aus, um die Benutzer der Rollengruppe hinzuzufügen. Wählen Sie **"Schließen"** aus, um die Schritte auszuführen.

## <a name="remove-users-from-a-compliance-role-group"></a>Entfernen von Benutzern aus einer Compliance-Rollengruppe

Führen Sie die folgenden Schritte aus, um Benutzer aus einer Compliance-Rollengruppe zu entfernen:

1. Melden Sie sich mit den Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365 Organisation beim Berechtigungsbereich des [Microsoft 365 Compliance Centers](https://compliance.microsoft.com/permissions) an.
2. Wechseln Sie im Microsoft 365 Compliance Center zu **"Berechtigungen".** Wählen Sie den Link aus, um Compliancerollen in Microsoft 365 anzuzeigen und zu verwalten.
3. Erweitern Sie den Abschnitt "Compliance Center", und wählen Sie **"Rollen"** aus.
4. Wählen Sie auf der Rollenseite des **Compliance Centers** eine Compliance-Rollengruppe aus, aus der Sie Benutzer entfernen möchten, und wählen Sie dann die **Rollengruppe bearbeiten** im Detailbereich aus.
5. Wählen Sie Im linken Navigationsbereich **"Mitglieder auswählen"** und dann **"Bearbeiten"** aus.
6. Wählen Sie **"Entfernen"** aus, und aktivieren Sie dann das Kontrollkästchen für alle Benutzer, die Sie aus der Rollengruppe entfernen möchten.
7. Wählen Sie **"Entfernen"** und dann **"Fertig"** aus.
8. Wählen Sie **"Speichern"** aus, um die Benutzer aus der Rollengruppe zu entfernen. Wählen Sie **"Schließen"** aus, um die Schritte auszuführen.
