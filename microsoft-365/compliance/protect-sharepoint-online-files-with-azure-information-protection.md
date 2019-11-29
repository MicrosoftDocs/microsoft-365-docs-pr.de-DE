---
title: Schützen von SharePoint Online-Dateien mit Azure Information Protection
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/29/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.custom:
- Ent_Solutions
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: 'Zusammenfassung: Verwenden Sie Azure Information Protection zum Schützen von Dateien auf einer streng vertraulichen SharePoint Online-Teamwebsite.'
ms.openlocfilehash: 6302ee8163525502550017f62fe4350645af59b3
ms.sourcegitcommit: bf30a2314376f0b7d577741b97df017969737d11
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/27/2019
ms.locfileid: "39630875"
---
# <a name="protect-sharepoint-online-files-with-azure-information-protection"></a>Schützen von SharePoint Online-Dateien mit Azure Information Protection

 **Zusammenfassung:** Verwenden Sie Azure Information Protection zum Schützen von Dateien auf einer streng vertraulichen SharePoint Online-Teamwebsite.
  
Konfigurieren Sie anhand der Schritte in diesem Artikel Azure Information Protection, um eine Verschlüsselung und Berechtigungen für Dateien bereitzustellen. Die Dateien können zu einer SharePoint-Bibliothek hinzugefügt werden, die für die Schutzebene „streng vertraulich“ konfiguriert wurde. Sie können eine Datei auch direkt über die Website öffnen und den Azure Information Protection-Client verwenden, um eine Verschlüsselung hinzuzufügen. Der Verschlüsselungs- und Berechtigungsschutz einer Datei bleibt auch dann bestehen, wenn die Datei von der Website heruntergeladen wird. 

Diese Schritte sind Teil einer umfangreicheren Lösung zur Konfiguration eines Schutzes streng vertraulicher Daten für SharePoint-Websites und die Dateien innerhalb dieser Websites. Weitere Informationen finden Sie unter [Sichern von SharePoint Online-Websites und -Dateien](https://docs.microsoft.com/microsoft-365/compliance/deploy-sharepoint-online-sites-for-three-tiers-of-protection). 

Die Verwendung von Azure Information Protection für Dateien in SharePoint Online wird nicht für alle Benutzer empfohlen, sie ist jedoch eine Option für Kunden, die für eine Teilmenge von Dateien diese Ebene des Schutzes benötigen.

Einige wichtige Hinweise zu dieser Lösung:
- Wenn Azure Information Protection-Verschlüsselung auf Dateien in Office 365 angewendet wird, kann der Dienst den Inhalt dieser Dateien nicht verarbeiten. Gemeinsame Dokumenterstellung, eDiscovery, Suche, Delve und andere Features für die Zusammenarbeit funktionieren nicht. DLP-Richtlinien können nur auf die Metadaten (einschließlich Office 365-Bezeichnungen) angewendet werden, aber nicht auf den Inhalt dieser Dateien (z. B. Kreditkartennummern in Dateien).

- Bei dieser Lösung muss ein Benutzer eine Bezeichnung auswählen, die den Schutz von Azure Information Protection anwendet. Wenn Sie eine automatische Verschlüsselung benötigen und SharePoint die Dateien indizieren und überprüfen soll, sollten Sie die Verwaltung von Informationsrechten (Information Rights Management, IRM) in SharePoint Online in Betracht ziehen. Wenn Sie eine SharePoint-Bibliothek für IRM konfigurieren, werden die Dateien automatisch beim Herunterladen für die Bearbeitung verschlüsselt. Für SharePoint IRM gelten einige Einschränkungen, die Ihre Entscheidung beeinflussen könnten. Weitere Informationen finden Sie unter [Einrichten von Information Rights Management (IRM) im SharePoint Admin Center](https://support.office.com/article/Set-up-Information-Rights-Management-IRM-in-SharePoint-admin-center-239CE6EB-4E81-42DB-BF86-A01362FED65C).

## <a name="admin-setup"></a>Einrichten eines Administrators
Befolgen Sie zuerst die Anweisungen unter [Aktivieren von Azure RMS mit Microsoft 365 Admin Center](https://docs.microsoft.com/information-protection/deploy-use/activate-office365) für Ihr Office 365-Abonnement.
  
Konfigurieren Sie anschließend Azure Information Protection mit einer neuen bereichsbezogenen Richtlinie und einer untergeordneten Bezeichnung mit dem Schutz und den Berechtigungen für die streng vertrauliche SharePoint Online-Teamwebsite.
  
1. Melden Sie sich beim Admin Center mit einem Konto an, das über die Rolle „Sicherheitsadministrator" oder Unternehmensadministrator" verfügt. Hilfe finden Sie unter [Where to sign in to Office 365 (Wo kann ich mich bei Office 365 anmelden?)](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. Wechseln Sie auf einer separaten Registerkarte im Browser zum Azure-Portal unter [https://portal.azure.com](https://portal.azure.com).
    
3. Wenn Sie Azure Information Protection zum ersten Mal konfigurieren, befolgen Sie diese [Anweisungen](https://docs.microsoft.com/information-protection/deploy-use/configure-policy#to-access-the-azure-information-protection-blade-for-the-first-time).

4. Klicken Sie im Listenbereich auf **Alle Dienste**, geben Sie **Information** ein, und klicken Sie dann auf **Azure Information Protection**.

5. Klicken Sie auf **Etiketten**.
    
6. Klicken Sie mit der rechten Maustaste auf die Bezeichnung **Streng vertraulich**, und klicken Sie dann auf **Unterbezeichnung hinzufügen**.
    
7. Geben Sie unter **Name** einen Namen für die Unterbezeichnung und unter **Beschreibung** eine Beschreibung für die Unterbezeichnung ein.
    
8. Klicken Sie unter **Berechtigungen für Dokumente und E-Mails mit dieser Bezeichnung festlegen** auf **Schützen**.
    
9. Klicken Sie im Abschnitt **Schutz** auf **Azure (Cloudschlüssel)**.
    
10. Klicken Sie auf dem Blatt **Schutz** unter **Schutzeinstellungen** auf **Berechtigungen hinzufügen**.
    
11. Klicken Sie auf dem Blatt **Berechtigungen hinzufügen** unter **Benutzer und Gruppen angeben** auf **Verzeichnis durchsuchen**.
    
12. Wählen Sie im Bereich **AAD-Benutzer und -Gruppen** die Websitemitglieder-Zugriffsgruppe für Ihre streng vertrauliche SharePoint Online-Teamwebsite aus, und klicken Sie dann auf **Auswählen**.
    
13. Klicken Sie unter **Aus voreingestellten Berechtigungen wählen oder Benutzerdefiniert festlegen** auf **Benutzerdefiniert**, und aktivieren Sie dann die Kontrollkästchen **Rechte anzeigen**, **Inhalt bearbeiten**, ** Speichern**, **Antworten** und **Allen antworten**.
    
14. Klicken Sie zweimal auf **OK**.
    
15. Klicken Sie auf dem Blatt **Untergeordnete Bezeichnung** auf **Speichern** und dann auf **OK**.

16. Klicken Sie auf dem Blatt **Azure Information Protection** auf **Richtlinien > + Neue Richtlinie hinzufügen**.
    
17. Geben Sie unter **Richtlinienname** einen Namen für die neue Richtlinie und unter **Beschreibung** eine Beschreibung ein.
    
18. Klicken Sie auf **Auswählen, welche Benutzer oder Gruppen diese Richtlinie erhalten > Benutzer/Gruppen**, und wählen Sie dann die Websitemitglieder-Zugriffsgruppe für Ihre streng vertrauliche SharePoint Online-Teamwebsite aus.
    
19. Klicken Sie auf **Auswählen > OK**.

20. Klicken Sie auf **Bezeichnungen hinzufügen oder entfernen**. Klicken Sie im Bereich **Richtlinie: Bezeichnungen hinzufügen oder entfernen** auf den Namen Ihrer neuen Unterbezeichnung und dann auf **OK**.   

21. Klicken Sie auf **Speichern** und dann auf **OK**.
 
## <a name="client-setup"></a>Einrichten eines Clients
Sie können jetzt damit beginnen, Dokumente zu erstellen und diese mit Azure Information Protection und der neuen Bezeichnung zu schützen.
  
Sie müssen den [Azure Information Protection-Client](https://docs.microsoft.com/information-protection/rms-client/install-client-app) auf Ihrem Gerät oder Ihrem Windows-Computer installieren. Sie können ein Skript erstellen und die Installation automatisieren, oder Benutzer können den Client manuell installieren. Informationen finden Sie in den folgenden Ressourcen:
  
- [Die Clientseite von Azure Information Protection](https://docs.microsoft.com/information-protection/rms-client/use-client)
    
- [Installieren des Azure Information Protection-Clients](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide)
    
- [Downloadseite für die manuelle Installation](https://www.microsoft.com/download/details.aspx?id=53018)
    
Nach der Installation führen die Benutzer eine Office-Anwendung (wie z. B. Microsoft Word) aus und melden sich von dort aus mit Ihrem Office 365-Konto an. Die neue Symbolleiste **Information Protection** ermöglicht es Benutzern, die neue Bezeichnung auszuwählen. Stellen Sie sicher, dass Ihre Benutzer die SharePoint Online-Teamwebsite kennen und wissen, welche Bezeichnung sie verwenden müssen, um ihre streng vertraulichen Dateien zu schützen.
  
> [!NOTE]
> Wenn Sie über mehrere streng vertrauliche SharePoint Online-Teamwebsites verfügen, müssen Sie anhand der oben aufgeführten Einstellungen mehrere bereichsbezogene Azure Information Protection-Richtlinien mit Unterbezeichnungen erstellen, wobei die Berechtigungen für jede Unterbezeichnung auf die Websitemitglieder-Zugriffsgruppe einer bestimmten SharePoint Online-Teamwebsite festgelegt sind. 
  
## <a name="adding-permissions-for-external-users"></a>Hinzufügen von Berechtigungen für externe Benutzer
Es gibt zwei Möglichkeiten, wie Sie externen Benutzern Zugriff auf Dateien gewähren können, die mit Azure Information Protection geschützt sind. In beiden Fällen benötigen die externen Benutzer ein Azure AD-Konto. Wenn externe Benutzer kein Mitglied einer Organisation sind, die Azure Active Directory verwendet, können sie auf dieser Registrierungsseite ein Azure AD-Konto als Einzelperson beantragen: [https://aka.ms/aip-signup](https://aka.ms/aip-signup).

 - Hinzufügen von externen Benutzern zu einer Azure AD-Gruppe, die zum Konfigurieren des Schutzes für eine Bezeichnung verwendet wird. Sie müssen zuerst das Konto als B2B-Benutzer in Ihrem Verzeichnis hinzufügen. Das [Zwischenspeichern einer Gruppenmitgliedschaft durch Azure Rights Management](https://docs.microsoft.com/azure/information-protection/plan-design/prepare#group-membership-caching-by-azure-information-protection) kann einige Stunden in Anspruch nehmen.  
 - Direktes Hinzufügen von externen Benutzern zum Bezeichnungsschutz. Sie können alle Benutzer aus einer Organisation (z. B. „Fabrikam.com“), eine Azure AD-Gruppe (z. B. eine Finanzgruppe innerhalb einer Organisation) oder einen Benutzer hinzufügen. Sie können beispielsweise ein externes Team von Aufsichtsbeamten zum Schutz für eine Bezeichnung hinzufügen.

## <a name="see-also"></a>Siehe auch

[Sichern von SharePoint Online-Websites und -Dateien](https://docs.microsoft.com/microsoft-365/compliance/deploy-sharepoint-online-sites-for-three-tiers-of-protection)
  
[Microsoft-Sicherheitsleitfaden für politische Kampagnen, gemeinnützige Organisationen und andere agile Organisationen](/security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[Cloudakzeptanz und Hybridlösungen](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
