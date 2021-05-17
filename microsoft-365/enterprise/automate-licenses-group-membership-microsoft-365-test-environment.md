---
title: Automatisieren der Lizenzierung und Gruppenmitgliedschaft für Microsoft 365 für Unternehmenstestumgebung
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Konfigurieren Sie die gruppenbasierte Lizenzierung und die dynamische Gruppenmitgliedschaft in Microsoft 365 Unternehmenstestumgebung.
ms.openlocfilehash: 26840e2884202a0fa9c4bb563f3d7c653482ef87
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905368"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a>Automatisieren der Lizenzierung und Gruppenmitgliedschaft für Microsoft 365 für Unternehmenstestumgebung

*Diese Testumgebungsanleitung kann nur für Microsoft 365 für Unternehmenstestumgebungen verwendet werden.*

Gruppenbasierte Lizenzierung weist lizenzen für ein Benutzerkonto basierend auf der Gruppenmitgliedschaft automatisch zu oder entfernt sie. Die dynamische Gruppenmitgliedschaft fügt einer Gruppe basierend auf Denkeigenschaften des Benutzerkontos, z. B. **Abteilung** oder Land, Mitglieder hinzu oder **entfernt sie.** In diesem Artikel werden Demonstrationen zum Hinzufügen und Entfernen von Gruppenmitgliedern in Microsoft 365 Unternehmenstestumgebung durchgeführt.

Das Einrichten der automatischen Lizenzierung und der dynamischen Gruppenmitgliedschaft in Microsoft 365 unternehmensumgebung umfasst zwei Phasen:

- [Phase 1: Build out your Microsoft 365 for Enterprise test environment](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Phase 2: Konfigurieren und Testen der dynamischen Gruppenmitgliedschaft und automatischen Lizenzierung](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Eine visuelle Karte zu allen Artikeln im Stapel Microsoft 365 test lab guide für unternehmen finden Sie unter [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Phase 1: Build out your Microsoft 365 for Enterprise test environment

Wenn Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft nur auf einfache Weise mit den Mindestanforderungen testen möchten, befolgen Sie die Anweisungen unter [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft in einem simulierten Unternehmen testen möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Das Testen der automatisierten Lizenzierung und Gruppenmitgliedschaft erfordert keine simulierte Unternehmenstestumgebung, die ein simuliertes Intranet, das mit dem Internet verbunden ist, und die Verzeichnissynchronisierung für eine Active Directory Domain Services (AD DS)-Gesamtstruktur umfasst. Es wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen und damit in einer Umgebung experimentieren können, die eine typische Organisation darstellt.
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a>Phase 2: Konfigurieren und Testen der dynamischen Gruppenmitgliedschaft und automatischen Lizenzierung

Erstellen Sie zunächst eine neue Gruppe namens Sales, und fügen Sie  eine  dynamische Gruppenmitgliedschaftsregel hinzu, damit Benutzerkonten mit der Abteilung, die auf Vertrieb festgelegt ist, automatisch der Gruppe "Vertrieb" beitreten.

1. Melden Sie sich in einer privaten Instanz Ihres Internetbrowsers beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit dem globalen Administratorkonto Ihres Microsoft 365 E5 Testumgebungsabonnements an.
2. Wechseln Sie auf einer separaten Registerkarte Ihres Browsers zum Azure-Portal unter [https://portal.azure.com](https://portal.azure.com) .
3. Geben Sie im Azure-Portal **Gruppen** in das Suchfeld ein, und wählen Sie dann **Gruppen aus.**
4. Wählen Sie **im Bereich Alle Gruppen** die Option Neue Gruppe **aus.**
5. Wählen **Sie unter** Gruppentyp die Option **Microsoft 365** aus.
6. Geben **Sie unter Gruppenname** den Namen **Sales ein.**
7. Wählen **Sie im Mitgliedschaftstyp** **dynamischen Benutzer aus.**
8. Wählen **Sie Dynamische Benutzermitglieder aus.**
9. Im Bereich **Dynamische Mitgliedschaftsregeln:** 
   - Wählen Sie die **Department-Eigenschaft** aus.
   - Wählen Sie den **Operator Equals** aus.
   - Geben Sie **im Feld Wert** den Wert Sales **ein.**
10. Klicken Sie auf **Speichern**.
11. Wählen Sie **Erstellen** aus.

Konfigurieren Sie als Nächstes die Gruppe "Vertrieb", sodass den Mitgliedern automatisch die Microsoft 365 E5 wird.

1. Wählen Sie **die Gruppe** Vertrieb aus, und wählen Sie dann **Lizenzen aus.**
2. Wählen Sie im Bereich **Lizenzzuweisungen** **aktualisieren die Option Microsoft 365 E5** aus, und wählen Sie dann Speichern **aus.**
3. Schließen Sie in Ihrem Browser die Registerkarte Azure-Portal.

Testen Sie als Nächstes die dynamische Gruppenmitgliedschaft und die automatische Lizenzierung für das Konto "Benutzer 4":

1. Wählen Sie **auf Microsoft Office Registerkarte Start** in Ihrem Browser Administrator **aus.**
2. Wählen Sie **auf Microsoft 365 Registerkarte Admin Center** die Option Aktive Benutzer **aus.**
3. Wählen Sie **auf der Seite** Aktive Benutzer das Konto Benutzer **4** aus.
4. Wählen Sie **im Bereich Benutzer 4** die Option **Für Produktlizenzen** **bearbeiten aus.**
5. Deaktivieren Sie **im** Bereich Produktlizenzen **die Microsoft 365 E5,** und wählen Sie **dann Speichern**  >  **Schließen aus.**
6. Überprüfen Sie in den Eigenschaften des Benutzerkontos 4, dass keine Produktlizenzen zugewiesen wurden und keine Gruppenmitgliedschaften verfügbar sind.
7. Wählen **Sie für Kontaktinformationen** Bearbeiten **aus.**
8. Wählen Sie **im Bereich Kontaktinformationen bearbeiten** die Option **Kontaktinformationen aus.**
9. Geben Sie **im Feld Abteilung** die Option **Vertrieb** ein, und wählen Sie **dann Speichern**  >  **Schließen aus.**
10. Warten Sie einige Minuten, und wählen Sie dann in regelmäßigen Abständen das **Symbol Aktualisieren** in der oberen rechten Ecke des Kontobereichs Benutzer 4 aus.

Mit der Zeit sollten Sie die:

- **Eigenschaft "Gruppenmitgliedschaften",** die mit der Gruppe **"Vertrieb" aktualisiert** wurde.
- **Die Produktlizenzeigenschaft** wurde mit **der** Microsoft 365 E5 aktualisiert.

In den folgenden Artikeln finden Sie Informationen zum Bereitstellen der dynamischen Gruppenmitgliedschaft und der automatischen Lizenzierung in der Produktion:

- [Gruppenbasierte Lizenzierung in Azure Active Directory](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [Dynamische Gruppen in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a>Nächster Schritt

Sehen Sie sich weitere [Identitäts](m365-enterprise-test-lab-guides.md#identity)features und- funktionen in Ihrer Testumgebung an.

## <a name="see-also"></a>Siehe auch

[Identitätsplan](identity-roadmap-microsoft-365.md)

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Dokumentation zu Microsoft 365 Enterprise](/microsoft-365-enterprise/)