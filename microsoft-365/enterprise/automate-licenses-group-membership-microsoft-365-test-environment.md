---
title: Automatisieren der Lizenzierung und der Gruppenmitgliedschaft für Ihre Microsoft 365 Enterprise-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Konfigurieren Sie die Gruppenbasierte Lizenzierung und die dynamische Gruppenmitgliedschaft in Ihrer Microsoft 365 Enterprise-Testumgebung.
ms.openlocfilehash: b1f3bc4a44e66d162360e82295c8f2877131cd07
ms.sourcegitcommit: fb3815ee186b2b3ec790ee32a9d7b1628d623b0b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "39202476"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a>Automatisieren der Lizenzierung und der Gruppenmitgliedschaft für Ihre Microsoft 365 Enterprise-Testumgebung

*Diese Testumgebungsanleitung kann nur für Microsoft 365 Enterprise-Testumgebungen verwendet werden.*

Bei der gruppenbasierten Lizenzierung werden basierend auf der Gruppenmitgliedschaft automatisch Lizenzen für ein Benutzerkonto zugewiesen oder entfernt. Durch die dynamische Gruppenmitgliedschaft werden Mitglieder einer Gruppe basierend auf den Eigenschaften des Benutzerkontos wie Abteilung oder Land hinzugefügt oder entfernt. In diesem Artikel werden Sie durch eine Demonstration beider Schritte in Ihrer Microsoft 365 Enterprise-Testumgebung geführt.

Es gibt zwei Phasen zum Einrichten der automatischen Lizenzierung und der dynamischen Gruppenmitgliedschaft in Ihrer Microsoft 365 Enterprise-Testumgebung:

1. Erstellen Sie die Microsoft 365 Enterprise-Testumgebung.
2. Konfigurieren und Testen der dynamischen Gruppenmitgliedschaft und der automatischen Lizenzierung.

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klicken Sie [hier](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung

Wenn Sie die automatische Lizenzierung und Gruppenmitgliedschaft nur auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie die automatische Lizenzierung und Gruppenmitgliedschaft in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Für das Testen der automatischen Lizenzierung und der Gruppenmitgliedschaft ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst. Sie wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen und in einer Umgebung experimentieren können, die eine typische Organisation darstellt. 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>Phase 2: Konfigurieren und Testen der dynamischen Gruppenmitgliedschaft und der automatischen Lizenzierung

Zunächst erstellen Sie eine neue Gruppe "Sales" und fügen eine dynamische Gruppen Mitgliedschaftsregel hinzu, sodass Benutzerkonten mit der Abteilung "Sales" automatisch der Gruppe "Sales" hinzugefügt werden.

1. Melden Sie sich mit einer privaten Instanz Ihres Internet Browsers beim Office 365-Portal unter [https://portal.office.com](https://portal.office.com) mit dem globalen Administratorkonto Ihres Office 365 E5 Test Lab-Abonnements an.
2. Wechseln Sie auf einer separaten Registerkarte Ihres Browsers zum Azure-Portal unter [https://portal.azure.com](https://portal.azure.com).
3. Klicken Sie im Azure-Portal auf **Azure Active Directory > Benutzer und Gruppen > Alle Gruppen**.
4. Klicken Sie auf dem Blatt **alle Gruppen** auf **neue Gruppe**.
5. Wählen Sie unter **Gruppentyp**die Option **Office 365**aus.
6. Geben Sie unter **Gruppenname den Namen** **Sales**ein.
7. Wählen Sie im **Typ Mitgliedschaft**die Option **dynamischer Benutzer** aus.
8. Klicken Sie auf **Dynamische Abfrage hinzufügen**.
9. Wählen Sie unter **Benutzer hinzufügen**die Option **Abteilung** aus.
10. Wählen Sie im nächsten Feld **Gleich** aus.
11. Geben Sie im nächsten Feld **Umsatz**ein.
12. Klicken Sie auf **Abfrage hinzufügen**, und klicken Sie dann auf **Erstellen**.
13. Schließen Sie die Blades **Gruppe** und **Gruppen – alle Gruppen** .

Als Nächstes konfigurieren Sie die Gruppe "Sales" so, dass Mitgliedern automatisch die Microsoft 365 E5-Lizenz zugewiesen wird.

1. Klicken Sie auf der Active Directory **Übersicht** Blade for Azure auf **Lizenzen #a0 alle Produkte**.
2. Wählen Sie in der Liste **Micrsooft 365 E5**aus, und klicken Sie dann auf **zuweisen**.
3. Klicken Sie auf dem Blatt **Lizenz zuweisen** auf **Benutzer und Gruppen**.
4. Wählen Sie in der Liste der Gruppen die Gruppe **Vertrieb** aus.
5. Klicken Sie auf **Auswählen** und dann auf **Zuweisen**.
6. Schließen Sie die Registerkarte für das Azure Portal in Ihrem Browser.

Als nächstes testen Sie die dynamische Gruppenmitgliedschaft und die automatische Lizenzierung für das Benutzerkonto 4. 

1. Klicken Sie auf der Registerkarte **Microsoft Office Start** in Ihrem Browser auf **Administrator**.
2. Klicken Sie auf der Registerkarte **Microsoft 365 Admin Center** auf **aktive Benutzer**.
3. Klicken Sie auf der Seite **aktive Benutzer** auf das Konto **Benutzer 4** .
4. Klicken Sie im Bereich **Benutzer 4** auf für **Produktlizenzen** **Bearbeiten** .
5. Deaktivieren Sie im Bereich **Produktlizenzen** die Lizenz **Microsoft 365 E5** , und klicken Sie dann auf **#a0 schließen speichern**.
6. Überprüfen Sie in den Eigenschaften des Benutzerkontos 4, dass keine Produktlizenzen zugewiesen wurden und keine Gruppenmitgliedschaften vorhanden sind.
7. Klicken Sie auf **Bearbeiten** , um **Kontaktinformationen zu erhalten**.
8. Klicken Sie im Bereich **Kontaktinformationen bearbeiten** auf **Kontaktinformationen**.
9. Geben Sie im Feld **Abteilung** den Namen **Sales**ein, und klicken Sie dann auf **#a0 schließen speichern**.
10. Warten Sie einige Minuten, und klicken Sie dann regelmäßig auf das Aktualisierungssymbol in der oberen rechten Ecke des Benutzer-4-Konto Bereichs. 

In der Zeit sollte Folgendes angezeigt werden:

- **Group Memberships** -Eigenschaft mit der Gruppe " **Sales** " aktualisiert.
- Die Eigenschaft " **Produktlizenzen** " wurde mit der **Microsoft 365 E5** -Lizenz aktualisiert.

In den folgenden Schritten in der Identitäts Phase finden Sie Informationen und Links zum Bereitstellen der dynamischen Gruppenmitgliedschaft und der automatischen Lizenzierung in der Produktionsumgebung:

- [Einrichten der automatischen Lizenzierung](identity-use-group-management.md#identity-group-license)
- [Einrichten der dynamischen Gruppenmitgliedschaft](identity-use-group-management.md#identity-dyn-groups)

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Phase 2: Identität](identity-infrastructure.md)

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise-Bereitstellungshandbuch](deploy-microsoft-365-enterprise.md)

[Dokumentation zu Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
