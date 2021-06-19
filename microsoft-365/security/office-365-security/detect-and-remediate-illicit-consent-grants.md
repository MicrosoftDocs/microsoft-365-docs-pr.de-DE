---
title: Erkennen und Korrigieren unrechtmäßiger Zustimmungserwilligung
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
description: Erfahren Sie, wie Sie den Angriff auf unrechtmäßige Zustimmungserwilligung in Microsoft 365 erkennen und beheben.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c0041c473f196dace893122c5c0543a06c1e6ff8
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029861"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a>Erkennen und Korrigieren unrechtmäßiger Zustimmungserwilligung

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Zusammenfassung**  Erfahren Sie, wie Sie den Angriff auf unrechtmäßige Zustimmungserwilligung in Microsoft 365 erkennen und beheben.

## <a name="what-is-the-illicit-consent-grant-attack-in-microsoft-365"></a>Was ist der Angriff auf unzulässige Zustimmungserteilung in Microsoft 365?

Bei einem illegalen Angriff zur Erteilung der Zustimmung erstellt der Angreifer eine in Azure registrierte Anwendung, die Zugriff auf Daten wie Kontaktinformationen, E-Mails oder Dokumente anfordert. Der Angreifer trickst dann einen Endbenutzer dazu aus, dieser Anwendung die Zustimmung zu erteilen, entweder durch einen Phishingangriff oder durch Einfügen von unzulässigen Code in eine vertrauenswürdige Website auf seine Daten zuzugreifen. Nachdem der unzulässigen Anwendung die Zustimmung erteilt wurde, hat sie Zugriff auf Daten auf Kontoebene, ohne dass ein Organisationskonto erforderlich ist. Normale Korrekturschritte, z. B. das Zurücksetzen von Kennwörtern für fehlerhafte Konten oder die Anforderung der mehrstufigen Authentifizierung (Multi-Factor Authentication, MFA) für Konten, sind gegen diese Art von Angriff nicht wirksam, da es sich hierbei um Drittanbieteranwendungen handelt, die sich außerhalb der Organisation befinden.

Diese Angriffe nutzen ein Interaktionsmodell, bei dem davon ausgegangen wird, dass es sich bei der Entität, die die Informationen aufruft, um Automatisierung und nicht um einen Menschen handelt.

> [!IMPORTANT]
> Gehen Sie davon aus, dass Sie derzeit Probleme mit unrechtmäßigen Genehmigungen von einer App haben? Microsoft Cloud App Security (MCAS) verfügt über Tools zum Erkennen, Untersuchen und Beheben Ihrer OAuth-Apps. Dieser MCAS-Artikel enthält ein Lernprogramm, in dem beschrieben wird, wie Sie [riskante OAuth-Apps untersuchen.](/cloud-app-security/investigate-risky-oauth) Sie können auch [OAuth-App-Richtlinien](/cloud-app-security/app-permission-policy) festlegen, um von Apps angeforderte Berechtigungen zu untersuchen, welche Benutzer diese Apps autorisieren, und diese Berechtigungsanforderungen allgemein genehmigen oder verbieten.

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-microsoft-365"></a>Wie sieht ein angriffsähnlicher Genehmigungserteilungsangriff in Microsoft 365 aus?

Sie müssen das **Überwachungsprotokoll** durchsuchen, um Nachschlagezeichen zu finden, die auch als Indikatoren für Kompromittierung (Indicators of Compromise, IOC) für diesen Angriff bezeichnet werden. Für Organisationen mit vielen von Azure registrierten Anwendungen und einer großen Benutzerbasis empfiehlt es sich, die Genehmigungen Ihrer Organisation wöchentlich zu überprüfen.

### <a name="steps-for-finding-signs-of-this-attack"></a>Schritte zum Auffinden von Anzeichen für diesen Angriff

1. Öffnen **Sie** das Microsoft 365 Defender-Portal <https://security.microsoft.com> unter, und wählen Sie dann **"Überwachen"** aus.

2. Überprüfen Sie auf der daraufhin geöffneten Seite **"Überwachung",** ob die Registerkarte **"Suchen"** ausgewählt ist, und konfigurieren Sie dann die folgenden Einstellungen:
   - **Datums- und Uhrzeitbereich**
   - **Aktivitäten:** Überprüfen Sie, ob **die Ergebnisse für alle Aktivitäten** angezeigt werden.

   Wenn Sie fertig sind, klicken Sie auf **Suchen.**

3. Klicken Sie auf die Spalte **"Aktivität",** um die Ergebnisse zu sortieren und nach **"Zustimmung zur Anwendung" zu** suchen.

4. Wählen Sie einen Eintrag aus der Liste aus, um die Details der Aktivität anzuzeigen. Überprüfen Sie, ob IsAdminContent auf "True" festgelegt ist.

> [!NOTE]
>
> Es kann bis zu 30 Minuten bis zu 24 Stunden dauern, bis der entsprechende Überwachungsprotokolleintrag in den Suchergebnissen angezeigt wird, nachdem ein Ereignis aufgetreten ist.
>
> Die Zeitdauer, die ein Überwachungsdatensatz aufbewahrt und im Überwachungsprotokoll durchsucht werden kann, hängt von Ihrem Microsoft 365 Abonnement und insbesondere vom Lizenztyp ab, der einem bestimmten Benutzer zugewiesen ist. Weitere Informationen finden Sie unter [Überwachungsprotokoll.](../../compliance/search-the-audit-log-in-security-and-compliance.md)
>
> Wenn dieser Wert wahr ist, gibt er an, dass eine Person mit globalem Administratorzugriff möglicherweise umfassenden Zugriff auf Daten gewährt hat. Wenn dies unerwartet ist, führen Sie Schritte aus, um einen Angriff zu [bestätigen.](#how-to-confirm-an-attack)

## <a name="how-to-confirm-an-attack"></a>Bestätigen eines Angriffs

Wenn Sie über mindestens eine Instanz der oben aufgeführten IOCs verfügen, müssen Sie weitere Untersuchungen durchführen, um zu bestätigen, dass der Angriff aufgetreten ist. Sie können eine der folgenden drei Methoden verwenden, um den Angriff zu bestätigen:

- Inventarisieren von Anwendungen und deren Berechtigungen über das Azure Active Directory Portal. Diese Methode ist gründlich, Aber Sie können nur jeweils einen Benutzer überprüfen, was sehr zeitaufwändig sein kann, wenn Sie viele Benutzer zu überprüfen haben.
- Inventarisieren von Anwendungen und deren Berechtigungen mithilfe von PowerShell. Dies ist die schnellste und gründlichste Methode mit dem geringsten Mehraufwand.
- Lassen Sie Ihre Benutzer ihre Apps und Berechtigungen einzeln überprüfen und die Ergebnisse zur Behebung an die Administratoren melden.

## <a name="inventory-apps-with-access-in-your-organization"></a>Inventarisieren von Apps mit Zugriff in Ihrer Organisation

Sie können dies für Ihre Benutzer entweder mit dem Azure Active Directory-Portal oder PowerShell tun oder Ihre Benutzer einzeln auflisten lassen, um ihren Anwendungszugriff auflisten zu lassen.

### <a name="steps-for-using-the-azure-active-directory-portal"></a>Schritte für die Verwendung des Azure Active Directory-Portals

Sie können die Anwendungen nachschlagen, für die ein einzelner Benutzer Berechtigungen erteilt hat, indem Sie das Azure Active Directory Portal unter <https://portal.azure.com> verwenden.

1. Melden Sie sich beim Azure-Portal mit Administratorrechten an.
2. Wählen Sie das Blatt Azure Active Directory aus.
3. Wählen Sie **Benutzer** aus.
4. Wählen Sie den Benutzer aus, den Sie überprüfen möchten.
5. Wählen Sie **Anwendungen** aus.

Hier erfahren Sie, welche Apps dem Benutzer zugewiesen sind und welche Berechtigungen die Anwendungen haben.

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a>Schritte zum Aufzählen des Anwendungszugriffs durch Ihre Benutzer

Lassen Sie Ihre Benutzer dort ihren eigenen Anwendungszugriff aufrufen <https://myapps.microsoft.com> und überprüfen. Sie sollten in der Lage sein, alle Apps mit Zugriff anzuzeigen, Details zu ihnen anzuzeigen (einschließlich des Umfangs des Zugriffs), und sie sollten in der Lage sein, Berechtigungen für verdächtige oder unzulässige Apps zu widerrufen.

### <a name="steps-for-doing-this-with-powershell"></a>Schritte dazu mit PowerShell

Die einfachste Möglichkeit zum Überprüfen des Angriffs auf die genehmigungserteilung besteht darin, [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)auszuführen, wodurch alle OAuth-Zustimmungserteilungen und OAuth-Apps für alle Benutzer in Ihrem Mandanten in einer .csv Datei gespeichert werden.

#### <a name="pre-requisites"></a>Voraussetzungen

- Die Installierte Azure AD PowerShell-Bibliothek.
- Globale Administratorrechte für den Mandanten, für den das Skript ausgeführt wird.
- Lokaler Administrator auf dem Computer, auf dem die Skripts ausgeführt werden.

> [!IMPORTANT]
> Es ***wird dringend empfohlen,*** dass Sie die mehrstufige Authentifizierung für Ihr Administratorkonto benötigen. Dieses Skript unterstützt die MFA-Authentifizierung.

1. Melden Sie sich bei dem Computer an, auf dem Sie das Skript mit lokalen Administratorrechten ausführen.

2. Laden Sie das [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) Skript aus GitHub in einen Ordner herunter, in dem Sie das Skript ausführen, oder kopieren Sie es. Dies ist derselbe Ordner, in den die Ausgabedatei "permissions.csv" geschrieben wird.

3. Öffnen Sie eine PowerShell-Sitzung als Administrator, und öffnen Sie den Ordner, in dem Sie das Skript gespeichert haben.

4. Verbinden mithilfe des Cmdlets [Verbinden-AzureAD](/powershell/module/azuread/connect-azuread) zu Ihrem Verzeichnis.

5. Führen Sie diesen PowerShell-Befehl aus:

   ```powershell
   .\Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

Das Skript erzeugt eine Datei mit dem Namen Permissions.csv. Führen Sie die folgenden Schritte aus, um nach unzulässigen Anwendungsberechtigungen zu suchen:

1. Suchen Sie in der ConsentType-Spalte (Spalte G) nach dem Wert "AllPrinciples". Die AllPrincipals-Berechtigung ermöglicht der Clientanwendung den Zugriff auf alle Inhalte des Mandanten. Native Microsoft 365 Anwendungen benötigen diese Berechtigung, um ordnungsgemäß zu funktionieren. Jede Nicht-Microsoft-Anwendung mit dieser Berechtigung sollte sorgfältig überprüft werden.

2. Überprüfen Sie in der Spalte "Berechtigung" (Spalte F) die Berechtigungen, die jede delegierte Anwendung für Inhalte hat. Suchen Sie nach der Berechtigung "Lesen" und "Schreiben" oder "*". Alle" Berechtigungen, und überprüfen Sie diese sorgfältig, da sie möglicherweise nicht geeignet sind.

3. Überprüfen Sie die spezifischen Benutzer, die über erteilte Zustimmungen verfügen. Wenn Benutzer mit hohem Profil oder hoher Auswirkung unangemessene Zustimmungen erteilt haben, sollten Sie weitere Untersuchungen durchführen.

4. Suchen Sie in der Spalte "ClientDisplayName" (Spalte C) nach Apps, die verdächtig erscheinen. Apps mit falsch geschriebenen Namen, Super-Bland-Namen oder Hackernamen sollten sorgfältig überprüft werden.

## <a name="determine-the-scope-of-the-attack"></a>Bestimmen des Umfangs des Angriffs

Nachdem Sie die Bestandsaufnahme des Anwendungszugriffs abgeschlossen haben, überprüfen Sie das **Überwachungsprotokoll,** um den vollständigen Umfang der Verletzung zu ermitteln. Suchen Sie nach den betroffenen Benutzern, den Zeitrahmen, auf die die unzulässige Anwendung Zugriff auf Ihre Organisation hatte, und den Berechtigungen, die die App hatte. Sie können das **Überwachungsprotokoll** im [Microsoft 365 Defender](../../compliance/search-the-audit-log-in-security-and-compliance.md)durchsuchen.

> [!IMPORTANT]
> [Die Postfachüberwachung](../../compliance/enable-mailbox-auditing.md) und [Aktivitätsüberwachung für Administratoren und Benutzer](../../compliance/turn-audit-log-search-on-or-off.md) muss vor dem Angriff aktiviert worden sein, damit Sie diese Informationen erhalten können.

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a>So stoppen und beheben Sie einen Angriff auf die Erteilung unrechtmäßiger Zustimmungen

Nachdem Sie eine Anwendung mit unzulässigen Berechtigungen identifiziert haben, haben Sie mehrere Möglichkeiten, diesen Zugriff zu entfernen.

- Sie können die Berechtigung der Anwendung im Azure Active Directory-Portal widerrufen, indem Sie:
  1. Navigieren Sie im Blatt **"Azure Active Directory Benutzer"** zum betroffenen Benutzer.
  2. Wählen Sie **Anwendungen** aus.
  3. Wählen Sie die unzulässige Anwendung aus.
  4. Klicken Sie im Drilldown auf **"Entfernen".**

- Sie können die OAuth-Zustimmungserteilung mit PowerShell widerrufen, indem Sie die Schritte in [Remove-AzureADOAuth2PermissionGrant](/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant)ausführen.

- Sie können die Dienst-App-Rollenzuweisung mit PowerShell widerrufen, indem Sie die Schritte in [Remove-AzureADServiceAppRoleAssignment](/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment)ausführen.

- Sie können die Anmeldung für das betroffene Konto auch vollständig deaktivieren, wodurch wiederum der App-Zugriff auf Daten in diesem Konto deaktiviert wird. Dies ist natürlich nicht ideal für die Produktivität des Endbenutzers, aber wenn Sie daran arbeiten, die Auswirkungen schnell zu begrenzen, kann dies eine geeignete kurzfristige Korrektur sein.

- Sie können integrierte Anwendungen für Ihren Mandanten deaktivieren. Dies ist ein erheblicher Schritt, durch den Endbenutzern die Möglichkeit zur mandantenweiten Zustimmung deaktiviert wird. Dadurch wird verhindert, dass Ihre Benutzer versehentlich Zugriff auf eine schädliche Anwendung gewähren. Dies wird nicht dringend empfohlen, da dies die Fähigkeit Ihrer Benutzer, mit Drittanbieteranwendungen produktiv zu sein, stark beeinträchtigt. Führen Sie dazu die Schritte zum [Aktivieren oder Deaktivieren integrierter Apps aus.](../../admin/misc/user-consent.md)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Sichern von Microsoft 365 wie ein Profi für Internetsicherheit

Ihr Microsoft 365-Abonnement bietet eine Reihe von leistungsfähigen Funktionen für Sicherheit, die Sie zum Schutz Ihrer Daten und Ihrer Benutzer verwenden können. Verwenden Sie die [Microsoft 365-Sicherheits-Roadmap: Top-Prioritäten für die ersten 30 Tage, 90 Tage und darüber hinaus](security-roadmap.md) zum Implementieren von empfohlenen Microsoft-Best-Practices für den Schutz Ihres Microsoft 365-Mandanten.

- Aufgaben, die in den ersten 30 Tagen ausgeführt werden sollten. Diese sind unmittelbar gültig und haben nur geringe Auswirkungen für die Benutzer.
- Aufgaben, die innerhalb von 90 Tagen ausgeführt werden sollten. Diese erfordern etwas mehr Zeit für Planung und Implementierung, stärken die Sicherheit Ihres Unternehmens jedoch erheblich.
- Über 90 Tage hinaus. Diese Verbesserungen werden in den ersten 90 Tagen Ihrer Arbeit umgesetzt.

## <a name="see-also"></a>Siehe auch

- [Unerwartete Anwendungen in der Liste "Meine Anwendungen"](/azure/active-directory/application-access-unexpected-application) führen Administratoren durch verschiedene Aktionen, die sie möglicherweise ausführen möchten, nachdem sie erkannt haben, dass unerwartete Anwendungen mit Zugriff auf Daten vorhanden sind.
- [Die Integration von Anwendungen in Azure Active Directory](/azure/active-directory/active-directory-apps-permissions-consent) ist eine allgemeine Übersicht über Die Zustimmung und Berechtigungen.
- [Probleme bei der Entwicklung meiner Anwendung](/azure/active-directory/active-directory-application-dev-development-content-map) stellen Links zu verschiedenen Zustimmungsartikeln bereit.
- [Anwendungs- und Dienstprinzipalobjekte in Azure Active Directory (Azure AD)](/azure/active-directory/develop/active-directory-application-objects) bieten eine Übersicht über die Anwendungs- und Dienstprinzipalobjekte, die den Kern des Anwendungsmodells bilden.
- [Verwalten des Zugriffs auf Apps](/azure/active-directory/active-directory-managing-access-to-apps) ist eine Übersicht über die Funktionen, die Administratoren zum Verwalten des Benutzerzugriffs auf Apps haben.
