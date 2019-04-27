---
title: Automatisieren von Lizenzen und Gruppenmitgliedschaften für Ihre Microsoft 365 Enterprise-Testumgebung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Konfigurieren Sie die Gruppenbasierte Lizenzierung und die dynamische Gruppenmitgliedschaft in Ihrer Microsoft 365 Enterprise-Testumgebung.
ms.openlocfilehash: 4ee929b345469d9cab05968a4a4c7f7399635b32
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2019
ms.locfileid: "33353077"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a>Automatisieren von Lizenzen und Gruppenmitgliedschaften für Ihre Microsoft 365 Enterprise-Testumgebung

Bei der gruppenbasierten Lizenzierung werden Lizenzen für ein Benutzerkonto basierend auf der Gruppenmitgliedschaft automatisch zugewiesen oder entfernt. Die dynamische Gruppenmitgliedschaft fügt Mitglieder zu einer Gruppe hinzu oder entfernt Sie basierend auf Benutzerkontoeigenschaften wie Abteilung oder Land. Dieser Artikel führt Sie durch eine Demonstration beider in Ihrer Microsoft 365 Enterprise-Testumgebung.

Es gibt zwei Phasen zum Einrichten der automatischen Lizenzierung und der dynamischen Gruppenmitgliedschaft in Ihrer Microsoft 365 Enterprise-Testumgebung:

1. Erstellen Sie die Microsoft 365 Enterprise-Testumgebung.
2. Konfigurieren und testen Sie die dynamische Gruppenmitgliedschaft und die automatische Lizenzierung.

![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klicken Sie [hier](https://aka.ms/m365etlgstack), um eine visuelle Darstellung aller Artikel im Stapel der Testumgebungsanleitungen in Microsoft 365 Enterprise zu erhalten.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Phase 1: Erstellen Ihrer Microsoft 365 Enterprise-Testumgebung

Wenn Sie die automatische Lizenzierung und Gruppenmitgliedschaft auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie die automatische Lizenzierung und Gruppenmitgliedschaft in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Passthrough-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Das Testen der automatisierten Lizenzierung und der Gruppenmitgliedschaft erfordert nicht die simulierte Enterprise-Testumgebung, die ein simuliertes Intranet enthält, das mit dem Internet und der Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) verbunden ist. Sie wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und die Gruppenmitgliedschaft testen und mit dieser in einer Umgebung experimentieren können, die eine typische Organisation darstellt. 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>Phase 2: Konfigurieren und Testen der dynamischen Gruppenmitgliedschaft und der automatischen Lizenzierung

Zunächst erstellen Sie eine neue Vertriebsgruppe und fügen eine dynamische Gruppen Mitgliedschaftsregel hinzu, sodass Benutzerkonten mit der Abteilung "Sales" automatisch der Gruppe "Sales" hinzugefügt werden.

1. Melden Sie sich über eine private Instanz Ihres Internet Browsers im Office 365-Portal unter [https://portal.office.com](https://portal.office.com) mit dem globalen Administratorkonto ihres Office 365 E5-Test Lab-Abonnements an.
2. Wechseln Sie auf einer separaten Registerkarte in Ihrem Browser zum Azure-Portal [https://portal.azure.com](https://portal.azure.com)unter.
3. Klicken Sie im Azure-Portal auf **Azure Active Directory > Benutzer und Gruppen > Alle Gruppen**.
4. Klicken Sie auf dem Blatt **alle Gruppen** auf **neue Gruppe**.
5. Wählen **** Sie unter Gruppentyp die option **Office 365**aus.
6. Geben Sie unter **Gruppenname den Namen** **Sales**ein.
7. Wählen **** Sie unter Mitgliedstyp die Option **dynamischer Benutzer** aus.
8. Klicken Sie auf **Dynamische Abfrage hinzufügen**.
9. Wählen Sie unter **Benutzer hinzufügen**die Option **Abteilung** aus.
10. Wählen Sie im nächsten Feld **Gleich** aus.
11. Geben Sie im nächsten Feld **Umsatz**ein.
12. Klicken Sie auf **Abfrage hinzufügen**, und klicken Sie dann auf **Erstellen**.
13. Schließt die **Gruppe** und **alle Gruppen-** Blades.

Als Nächstes konfigurieren Sie die Gruppe "Sales" so, dass Mitgliedern automatisch Office 365 E5 und Enterprise Mobility + Security E5-Lizenzen zugewiesen werden.

1. Klicken Sie auf dem Blatt **Übersicht** für Azure Active Directory auf **Lizenzen > alle Produkte**.
2. Wählen Sie in der Liste **Enterprise Mobility + Security E5** und **Office 365 Enterprise E5** aus, und klicken Sie dann auf **Zuweisen**.
3. Klicken Sie auf der **Lizenzblatt zuweisen** auf **Benutzer und Gruppen**.
4. Wählen Sie in der Liste der Gruppen die Gruppe **Sales** aus.
5. Klicken Sie auf **Auswählen** und dann auf **Zuweisen**.
6. Schließen Sie die Registerkarte für das Azure Portal in Ihrem Browser.

Als nächstes testen Sie die dynamische Gruppenmitgliedschaft und die automatische Lizenzierung für das Benutzer 4-Konto. 

1. Klicken Sie auf der Registerkarte **Microsoft Office Home** in Ihrem Browser auf **Admin**.
2. Klicken Sie auf der Registerkarte **Microsoft 365 Admin Center** auf **aktive Benutzer**.
3. Klicken Sie auf der Seite **aktive Benutzer** auf das Konto **Benutzer 4** .
4. Klicken Sie im Bereich **Benutzer 4** auf für **Produktlizenzen** **Bearbeiten** .
5. Aktivieren Sie im Bereich **Produktlizenzen** die Lizenzen **Enterprise Mobility + Security e5** und **Office 365 Enterprise E5** , und klicken Sie dann auf **> speichern**.
6. Vergewissern Sie sich, dass in den Eigenschaften des Benutzer 4-Kontos keine Produktlizenzen zugewiesen wurden und keine Gruppenmitgliedschaften vorhanden sind.
7. Klicken Sie auf **Bearbeiten** für **Kontaktinformationen**.
8. Klicken Sie im Bereich **Kontaktinformationen bearbeiten** auf **Kontaktinformationen**.
9. Geben Sie im Feld **Abteilung** den Namen **Sales**ein, und klicken Sie dann auf **> speichern**.
10. Warten Sie einige Minuten, und klicken Sie dann regelmäßig auf das Aktualisierungssymbol in der oberen rechten Ecke des Benutzer 4-Konto Bereichs. 

In der Zeit sollten Sie Folgendes sehen:

- Die **Group Memberships** -Eigenschaft wurde mit der Gruppe " **Sales** " aktualisiert.
- Eigenschaft **Product licenses** , die mit den Lizenzen **Enterprise Mobility + Security E5** und **Office 365 Enterprise E5** aktualisiert wurde.

Weitere Informationen und Links zur Bereitstellung der dynamischen Gruppenmitgliedschaft und der automatischen Lizenzierung in der Produktion finden Sie in den folgenden Schritten in der Identitäts Phase:

- [Einrichten der automatischen Lizenzierung](identity-self-service-group-management.md#identity-group-license)
- [Einrichten der dynamischen Gruppenmitgliedschaft](identity-self-service-group-management.md#identity-dyn-groups)

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Phase 2: Identität](identity-infrastructure.md)

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise-Bereitstellung](deploy-microsoft-365-enterprise.md)

[Dokumentation zu Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
