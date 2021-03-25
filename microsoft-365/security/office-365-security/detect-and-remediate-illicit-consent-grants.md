---
title: Erkennen und Behebung unrechtmäßiger Zustimmungszuserm n
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: Erfahren Sie, wie Sie den Angriff auf unrechtmäßige Zustimmungszuserkennungen in Microsoft Office 365 erkennen und abbehandeln.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4a9b3ff11acb32a4b3038cc18922f8e22fda0b4c
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205942"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a>Erkennen und Behebung unrechtmäßiger Zustimmungszuserm n

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Zusammenfassung**  Erfahren Sie, wie Sie den Angriff auf unrechtmäßige Zustimmungszuserkennungen in Office 365 erkennen und 2013 wiederbehandeln können.

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a>Was ist der Angriff auf unrechtmäßige Zustimmungserteilung in Office 365?

Bei einem Angriff auf unrechtmäßige Zustimmungserteilung erstellt der Angreifer eine in Azure registrierte Anwendung, die Zugriff auf Daten wie Kontaktinformationen, E-Mails oder Dokumente anfordert. Der Angreifer trickst dann einen Endbenutzer dazu, dieser Anwendung die Zustimmung zu erteilen, entweder über einen Phishingangriff oder durch Injizieren von unerlaubtem Code auf einer vertrauenswürdigen Website auf ihre Daten zu zugreifen. Nachdem der unrechtmäßigen Anwendung die Zustimmung erteilt wurde, hat sie zugriff auf Kontoebene auf Daten, ohne dass ein Organisationskonto benötigt wird. Normale Korrekturschritte, z. B. das Zurücksetzen von Kennwörtern für verletzte Konten oder das Erfordern der mehrstufigen Authentifizierung (Multi-Factor Authentication, MFA) für Konten, sind bei dieser Art von Angriff nicht wirksam, da es sich um Drittanbieteranwendungen handelt und außerhalb der Organisation sind.

Diese Angriffe nutzen ein Interaktionsmodell, bei dem davon ausgegangen wird, dass die Entität, die die Informationen aufruft, Automatisierung und kein Mensch ist.

> [!IMPORTANT]
> Vermuten Sie, dass Sie probleme mit unrechtmäßigen Zustimmungsermächtigungsermächtigungen von einer App haben, gerade jetzt? Microsoft Cloud App Security (MCAS) verfügt über Tools zum Erkennen, Untersuchen und Behebung Ihrer OAuth-Apps. Dieser MCAS-Artikel enthält ein Lernprogramm, in dem erläutert wird, wie Sie [riskante OAuth-Apps untersuchen.](/cloud-app-security/investigate-risky-oauth) Sie können auch [OAuth-App-Richtlinien](/cloud-app-security/app-permission-policy) festlegen, um von apps angeforderte Berechtigungen zu untersuchen, welche Benutzer diese Apps autorisieren, und diese Berechtigungsanforderungen allgemein genehmigen oder verbieten.

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a>Wie sieht ein Angriff auf unrechtmäßige Zustimmungserteilung in Office 365 aus?

Sie müssen das Überwachungsprotokoll **durchsuchen,** um Nach Anzeichen zu finden, die auch als Indikatoren für den Kompromiss (Indicators of Compromise, IOC) dieses Angriffs bezeichnet werden. Für Organisationen mit vielen von Azure registrierten Anwendungen und einer großen Benutzerbasis sollten Sie die Zustimmungszuserm nen ihrer Organisation wöchentlich überprüfen.

### <a name="steps-for-finding-signs-of-this-attack"></a>Schritte zum Suchen nach Anzeichen dieses Angriffs

1. Öffnen Sie **das Security & Compliance Center unter** <https://protection.office.com> .

2. Navigieren Sie zu **Suchen,** und wählen **Sie Überwachungsprotokollsuche aus.**

3. Suchen Sie (alle Aktivitäten und alle Benutzer), geben Sie bei Bedarf das Start- und Enddatum ein, und klicken Sie dann auf **Suchen**.

4. Klicken **Sie auf Ergebnisse filtern,** und geben Sie Zustimmung zur Anwendung in das Feld **Aktivität** ein.

5. Klicken Sie auf das Ergebnis, um die Details der Aktivität anzuzeigen. Klicken **Sie auf Weitere Informationen,** um Details zur Aktivität zu erhalten. Überprüfen Sie, ob IsAdminContent auf True festgelegt ist.

> [!NOTE]
>
> Es kann zwischen 30 Minuten und 24 Stunden dauern, bis der entsprechende Überwachungsprotokolleintrag in den Suchergebnissen angezeigt wird, nachdem ein Ereignis auftritt.
>
> Die Dauer, für die ein Überwachungsdatensatz im Überwachungsprotokoll aufbewahrt und durchsucht werden kann, hängt von Ihrem Microsoft 365-Abonnement und insbesondere vom Typ der Lizenz ab, die einem bestimmten Benutzer zugewiesen ist. Weitere Informationen finden Sie unter [Überwachungsprotokoll](../../compliance/search-the-audit-log-in-security-and-compliance.md).
>
> Wenn dieser Wert true ist, bedeutet dies, dass eine Person mit zugriff auf den globalen Administrator möglicherweise einen breiten Zugriff auf Daten gewährt hat. Wenn dies unerwartet ist, führen Sie Schritte aus, um [einen Angriff zu bestätigen.](#how-to-confirm-an-attack)

## <a name="how-to-confirm-an-attack"></a>Bestätigen eines Angriffs

Wenn Sie über eine oder mehrere Instanzen der oben aufgeführten IOCs verfügen, müssen Sie weitere Untersuchungen unternehmen, um den Angriff positiv zu bestätigen. Sie können eine der drei folgenden Methoden verwenden, um den Angriff zu bestätigen:

- Inventaranwendungen und deren Berechtigungen mithilfe des Azure Active Directory-Portals. Diese Methode ist gründlich, Aber Sie können nur einen Benutzer gleichzeitig überprüfen, was sehr zeitaufwändig sein kann, wenn Sie viele Benutzer zu überprüfen haben.

- Inventaranwendungen und deren Berechtigungen mithilfe von PowerShell. Dies ist die schnellste und gründlichste Methode mit dem geringsten Aufwand.

- Lassen Sie Ihre Benutzer ihre Apps und Berechtigungen einzeln überprüfen und die Ergebnisse zur Behebung an die Administratoren zurück melden.

## <a name="inventory-apps-with-access-in-your-organization"></a>Inventarisierung von Apps mit Zugriff in Ihrer Organisation

Sie können dies für Ihre Benutzer entweder mit dem Azure Active Directory-Portal oder mit PowerShell tun oder Ihre Benutzer einzeln aufzählen lassen.

### <a name="steps-for-using-the-azure-active-directory-portal"></a>Schritte für die Verwendung des Azure Active Directory-Portals

Sie können die Anwendungen nachschauen, denen jeder einzelne Benutzer Berechtigungen erteilt hat, indem Sie das [Azure Active Directory-Portal verwenden.](https://portal.azure.com/)

1. Melden Sie sich mit Administratorrechten beim Azure-Portal an.

2. Wählen Sie das Azure Active Directory-Blatt aus.

3. Wählen Sie **Benutzer** aus.

4. Wählen Sie den Benutzer aus, den Sie überprüfen möchten.

5. Wählen Sie **Anwendungen aus.**

Dadurch werden die Apps angezeigt, die dem Benutzer zugewiesen sind und welche Berechtigungen die Anwendungen besitzen.

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>Schritte zum Aufzählen des Anwendungszugriffs durch Ihre Benutzer

Lassen Sie Ihre Benutzer zu https://myapps.microsoft.com und überprüfen Sie dort ihren eigenen Anwendungszugriff. Sie sollten in der Lage sein, alle Apps mit Zugriff anzuzeigen, Details zu ihnen anzuzeigen (einschließlich des Zugriffsbereichs) und Berechtigungen für verdächtige oder unrechtmäßige Apps widerrufen zu können.

### <a name="steps-for-doing-this-with-powershell"></a>Schritte dazu mit PowerShell

Die einfachste Möglichkeit zum Überprüfen des Angriffs auf unrechtmäßige Zustimmung besteht in der Ausführung von [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), das alle OAuth-Zustimmungszuserteilungen und OAuth-Apps für alle Benutzer in Ihrem Mandanz in einer CSV-Datei abbilden wird.

#### <a name="pre-requisites"></a>Voraussetzungen

- Die Installierte Azure AD PowerShell-Bibliothek.

- Globale Administratorrechte für den Mandanten, für den das Skript ausgeführt wird.

- Lokaler Administrator auf dem Computer, auf dem die Skripts ausgeführt werden.

> [!IMPORTANT]
> Es ***wird dringend*** empfohlen, dass Sie die mehrstufige Authentifizierung für Ihr Administratorkonto benötigen. Dieses Skript unterstützt die MFA-Authentifizierung.

1. Melden Sie sich bei dem Computer an, von dem Sie das Skript mit lokalen Administratorrechten ausführen.

2. Laden Sie das Skript [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) GitHub in einen Ordner herunter, aus dem Sie das Skript ausführen. Dies ist derselbe Ordner, in den die Ausgabedatei "permissions.csv" geschrieben wird.

3. Öffnen Sie eine PowerShell-Instanz als Administrator, und öffnen Sie den Ordner, in dem Sie das Skript gespeichert haben.

4. Stellen Sie eine Verbindung mit Ihrem Verzeichnis mithilfe des [Connect-AzureAD-Cmdlets](/powershell/module/azuread/connect-azuread) bereit.

5. Führen Sie diesen PowerShell-Befehl aus:

   ```powershell
   Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

Das Skript erzeugt eine Datei namens Permissions.csv. Führen Sie die folgenden Schritte aus, um nach unrechtmäßigen Anwendungsberechtigungen zu suchen:

1. Suchen Sie in der Spalte ConsentType (Spalte G) nach dem Wert "AllPrinciples". Mit der AllPrincipals-Berechtigung kann die Clientanwendung auf alle Inhalte im Mandanten zugreifen. Systemeigene Microsoft 365-Anwendungen benötigen diese Berechtigung, um ordnungsgemäß zu funktionieren. Jede Nicht-Microsoft-Anwendung mit dieser Berechtigung sollte sorgfältig überprüft werden.

2. Überprüfen Sie in der Spalte Berechtigung (Spalte F) die Berechtigungen, die jede delegierte Anwendung für inhalte hat. Suchen Sie nach den Berechtigungen "Lesen" und "Schreiben" oder "*. All"-Berechtigung, und überprüfen Sie diese sorgfältig, da sie möglicherweise nicht geeignet sind.

3. Überprüfen Sie die bestimmten Benutzer, die über erteilte Zustimmungen verfügen. Wenn Benutzern mit hoher Profil- oder Wirkungskraft unangemessene Zustimmungen erteilt wurden, sollten Sie dies weiter untersuchen.

4. Suchen Sie in der Spalte ClientDisplayName (Spalte C) nach Apps, die verdächtig erscheinen. Apps mit falsch geschriebenen Namen, Super-Bland-Namen oder Hacker-klingenden Namen sollten sorgfältig überprüft werden.

## <a name="determine-the-scope-of-the-attack"></a>Bestimmen des Umfangs des Angriffs

Nachdem Sie den Inventarisierungsanwendungszugriff abgeschlossen haben, überprüfen Sie das Überwachungsprotokoll, **um** den vollständigen Umfang der Verletzung zu ermitteln. Suchen Sie nach den betroffenen Benutzern, den Zeitrahmen, auf die die unerlaubte Anwendung Zugriff auf Ihre Organisation hatte, und den Berechtigungen, die die App hatte. Sie können das **Überwachungsprotokoll im** [Microsoft 365 Security and Compliance Center durchsuchen.](../../compliance/search-the-audit-log-in-security-and-compliance.md)

> [!IMPORTANT]
> [Postfachüberwachung](../../compliance/enable-mailbox-auditing.md) und [Aktivitätsüberwachung für Administratoren](../../compliance/turn-audit-log-search-on-or-off.md) und Benutzer müssen vor dem Angriff aktiviert sein, damit Sie diese Informationen erhalten können.

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a>Beenden und Behebung eines Angriffs auf unrechtmäßige Zustimmungserteilung

Nachdem Sie eine Anwendung mit unzulässigen Berechtigungen identifiziert haben, haben Sie mehrere Möglichkeiten, diesen Zugriff zu entfernen.

- Sie können die Berechtigung der Anwendung im Azure Active Directory-Portal widerrufen, indem Sie:

  - Navigieren Sie zum betroffenen Benutzer im **Blatt Azure Active Directory User.**

  - Wählen Sie **Anwendungen aus.**

  - Wählen Sie die unzulässige Anwendung aus.

  - Klicken **Sie im** Drilldown auf Entfernen.

- Sie können die OAuth-Zustimmung mit PowerShell widerrufen, indem Sie die Schritte unter [Remove-AzureADOAuth2PermissionGrant ausführen.](/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant)

- Sie können die Dienst-App-Rollenzuweisung mit PowerShell widerrufen, indem Sie die Schritte unter [Remove-AzureADServiceAppRoleAssignment ausführen.](/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment)

- Sie können auch die Anmeldung für das betroffene Konto vollständig deaktivieren, wodurch wiederum der App-Zugriff auf Daten in diesem Konto deaktiviert wird. Dies ist natürlich nicht ideal für die Produktivität des Endbenutzers, aber wenn Sie daran arbeiten, die Auswirkungen schnell zu begrenzen, kann dies eine praktikable kurzfristige Korrektur sein.

- Sie können integrierte Anwendungen für Ihre Mandanz deaktivieren. Dies ist ein drastischer Schritt, der die Möglichkeit für Endbenutzer deaktiviert, mandantenweite Zustimmung zu erteilen. Dadurch wird verhindert, dass Benutzer versehentlich Zugriff auf eine schädliche Anwendung gewähren. Dies wird nicht dringend empfohlen, da dies die Produktivität ihrer Benutzer bei Anwendungen von Drittanbietern stark beeinträchtigt. Sie können dazu die Schritte unter Aktivieren oder Deaktivieren von [integrierten Apps ausführen.](../../admin/misc/user-consent.md)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Sichern von Microsoft 365 wie ein Profi für Internetsicherheit

Ihr Microsoft 365-Abonnement bietet eine Reihe von leistungsfähigen Funktionen für Sicherheit, die Sie zum Schutz Ihrer Daten und Ihrer Benutzer verwenden können. Verwenden Sie die [Microsoft 365-Sicherheits-Roadmap: Top-Prioritäten für die ersten 30 Tage, 90 Tage und darüber hinaus](security-roadmap.md) zum Implementieren von empfohlenen Microsoft-Best-Practices für den Schutz Ihres Microsoft 365-Mandanten.

- Aufgaben, die in den ersten 30 Tagen ausgeführt werden sollten. Diese sind unmittelbar gültig und haben nur geringe Auswirkungen für die Benutzer.

- Aufgaben, die innerhalb von 90 Tagen ausgeführt werden sollten. Diese erfordern etwas mehr Zeit für Planung und Implementierung, stärken die Sicherheit Ihres Unternehmens jedoch erheblich.

- Über 90 Tage hinaus. Diese Verbesserungen werden in den ersten 90 Tagen Ihrer Arbeit umgesetzt.

## <a name="see-also"></a>Siehe auch:

- [Unerwartete Anwendung in der Liste "Meine](/azure/active-directory/application-access-unexpected-application) Anwendungen" führt Administratoren durch verschiedene Aktionen, die sie möglicherweise ausführen möchten, nachdem sie sich über unerwartete Anwendungen mit Zugriff auf Daten geärgt haben.

- [Die Integration von Anwendungen in Azure Active Directory](/azure/active-directory/active-directory-apps-permissions-consent) ist eine Übersicht über Zustimmung und Berechtigungen auf hoher Ebene.

- [Probleme bei der Entwicklung meiner Anwendung](/azure/active-directory/active-directory-application-dev-development-content-map) stellen Links zu verschiedenen zustimmungsbezogenen Artikeln.

- [Anwendungs- und Dienstprinzipalobjekte in Azure Active Directory (Azure AD)](/azure/active-directory/develop/active-directory-application-objects) bieten eine Übersicht über die Anwendungs- und Dienstprinzipalobjekte, die kern des Anwendungsmodells sind.

- [Verwalten des Zugriffs auf Apps](/azure/active-directory/active-directory-managing-access-to-apps) ist eine Übersicht über die Funktionen, die Administratoren zum Verwalten des Benutzerzugriffs auf Apps haben.