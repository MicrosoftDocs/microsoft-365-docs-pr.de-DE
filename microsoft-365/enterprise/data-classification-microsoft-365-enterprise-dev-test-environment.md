---
title: Datenklassifizierung für Microsoft 365 für Die Unternehmenstestumgebung
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Verwenden Sie dieses Testumgebungshandbuch zum Erstellen und Verwenden von Aufbewahrungsbezeichnungen für Dokumente in Microsoft 365 Unternehmenstestumgebung.
ms.openlocfilehash: 613aa3713b4d72eed1bc0b2d88f70a817d0e7cff
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919188"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a>Datenklassifizierung für Microsoft 365 für Die Unternehmenstestumgebung

*Diese Testumgebungsanleitung kann sowohl für Microsoft 365 als auch für Office 365 Enterprise verwendet werden.*

In diesem Artikel wird beschrieben, wie Sie die Datenklassifizierung mithilfe von Aufbewahrungsbezeichnungen in Microsoft 365 Unternehmenstestumgebung konfigurieren.

Das Klassifizieren von Daten in Ihrer Testumgebung umfasst drei Phasen:
- [Phase 1: Build out your Microsoft 365 for Enterprise test environment](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Phase 2: Erstellen von Aufbewahrungsbezeichnungen](#phase-2-create-retention-labels)
- [Phase 3: Anwenden von Aufbewahrungsbezeichnungen auf Dokumente](#phase-3-apply-retention-labels-to-documents)

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Eine visuelle Karte zu allen Artikeln im Stapel Microsoft 365 test lab guide für unternehmen finden Sie unter [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Phase 1: Build out your Microsoft 365 for Enterprise test environment

Wenn Sie Aufbewahrungsbezeichnungen nur auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen unter [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Wenn Sie Aufbewahrungsbezeichnungen in einem simulierten Unternehmen konfigurieren möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Das Testen von Aufbewahrungsbezeichnungen erfordert keine simulierte Unternehmenstestumgebung, die ein simuliertes Intranet umfasst, das mit dem Internet verbunden ist, und die Verzeichnissynchronisierung für eine Active Directory Domain Services (AD DS)-Gesamtstruktur. Es wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen und damit in einer Umgebung experimentieren können, die eine typische Organisation darstellt.

## <a name="phase-2-create-retention-labels"></a>Phase 2: Erstellen von Aufbewahrungsbezeichnungen

Erstellen Sie in dieser Phase die Aufbewahrungsbezeichnungen für die verschiedenen Aufbewahrungsebenen für SharePoint Onlinedokumentordner:

1. Melden Sie sich beim [Microsoft 365 Security Center](https://security.microsoft.com/homepage) mit Ihrem globalen Administratorkonto an.
1. Wählen Sie auf der **Registerkarte Microsoft 365 Ihres** Browsers die Option Klassifizierungsaufbewahrungsbezeichnungen   >  **aus.**
1. Wählen Sie **Bezeichnung erstellen** aus.
1. Geben Sie **im Bereich** Bezeichnung benennen die Option **Internes Öffentliches** unter **Bezeichnung** benennen ein, und wählen Sie dann **Weiter aus.**
1. Wählen Sie **im Bereich Dateiplandeskriptoren** die Option **Weiter aus.**
1. Legen Sie **im Bereich** Bezeichnungseinstellungen bei Bedarf **aufbewahrung** auf **Ein** und wählen Sie dann **Weiter aus.**
1. Wählen Sie **im Bereich Einstellungen überprüfen** die Option Bezeichnung erstellen **aus.**
1. Wiederholen Sie die Schritte 3 bis 7 für die zusätzlichen Bezeichnungen mit diesen Namen:
  - Private
  - Vertraulich
  - Streng vertraulich
1. Wählen Sie **im Bereich Aufbewahrungsbezeichnungen** die Option **Bezeichnungen veröffentlichen aus.**
1. Wählen Sie **im Bereich Zu veröffentlichende Bezeichnungen** auswählen die Option **Zu veröffentlichende Bezeichnungen auswählen aus.**
1. Wählen Sie **im Bereich Bezeichnungen** auswählen die Option **Hinzufügen** aus, und wählen Sie alle vier Bezeichnungen aus.
1. Wählen **Sie Hinzufügen** aus, und wählen Sie dann Fertig **aus.**
1. Wählen Sie **im Bereich Zu veröffentlichende Bezeichnungen** auswählen die Option **Weiter aus.**
1. Wählen Sie **im Bereich** Speicherorte auswählen die Option **Weiter aus.**
1. Geben Sie im Bereich Name **Ihrer Richtlinie** **beispielorganisation** in **Name** ein, und wählen Sie dann **Weiter aus.**
1. Wählen Sie **im Bereich Einstellungen überprüfen** die Option **Bezeichnungen veröffentlichen aus.**
 
Es kann einige Minuten dauern, bis die Aufbewahrungsbezeichnungen veröffentlicht wurden.

## <a name="phase-3-apply-retention-labels-to-documents"></a>Phase 3: Anwenden von Aufbewahrungsbezeichnungen auf Dokumente

In dieser Phase ermitteln Sie das standardaufbewahrungsbezeichnungsverhalten für Dateien im Ordner Dokumente einer SharePoint Online-Website und ändern manuell die Aufbewahrungsbezeichnung eines Dokuments.

Erstellen Sie zunächst eine Website auf vertraulicher SharePoint Online-Teamwebsite:
  
1. Melden Sie sich mit einer privaten Instanz Ihres Browsers beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit Ihrem globalen Administratorkonto an.
1. Wählen Sie in der Liste der Kacheln **die Option SharePoint**.
1. Wählen Sie auf **der registerkarte SharePoint** in Ihrem Browser Website erstellen **aus.**
1. Wählen Sie auf der Seite **Website erstellen** die Option **Teamwebsite** aus.
1. Geben Sie **im Feld Teamwebsitename** **sensitiveFiles ein.**
1. Geben Sie **im Feld Teamwebsitebeschreibung** SharePoint für vertrauliche **Dateien ein.**
1. Wählen **Sie unter** Datenschutzeinstellungen die Option Privat aus – nur Mitglieder können auf diese Website **zugreifen,** und wählen Sie dann **Weiter aus.**
1. Wählen Sie **im Wer, die Sie hinzufügen möchten?** die Option **Fertig stellen aus.**
    
Konfigurieren Sie als Nächstes den Ordner Dokumente der SensitiveFiles-Teamwebsite für die Bezeichnung "Vertrauliche Aufbewahrung".
  
1. Wählen Sie auf der **Registerkarte SensitiveFiles** Ihres Browsers Dokumente **aus.**
1. Wählen Sie **Einstellungen** Symbol aus, und wählen Sie dann **Bibliothekseinstellungen aus.**
1. Wählen **Sie unter Berechtigungen und Verwaltung** die Option Bezeichnung auf Elemente in dieser Liste oder Bibliothek anwenden **aus.** Wenn diese Option nicht angezeigt wird, werden Ihre Aufbewahrungsbezeichnungen noch nicht veröffentlicht. Versuchen Sie diesen Schritt zu einem späteren Zeitpunkt.
1. Wählen **Einstellungen Im Dropdownfeld unter Bezeichnung** anwenden die Option **Vertraulich** aus, und wählen Sie dann **Speichern aus.**

Erstellen Sie als Nächstes ein neues Dokument auf der SensitiveFiles-Website, und ändern Sie die Aufbewahrungsbezeichnung.
    
1. Wählen Sie im Ordner Dokumente die Option **Neues**  >  **Word-Dokument aus.**
1. Geben Sie text in das leere Dokument ein. Warten Sie, bis der Text gespeichert ist.
1. Wählen Sie auf der Menüleiste **freigegebene Dokumente aus.**
1. Wählen Sie neben **Document.docx** Dateinamen die vertikalen Auslassungspunkte aus, und wählen Sie dann **Details aus.**
1. Beachten Sie im rechten Bereich im Abschnitt **Eigenschaften** unter **Aufbewahrungsbezeichnung** anwenden, dass für das Dokument automatisch die Aufbewahrungsbezeichnung **Vertraulich** angewendet wurde.
1. Klicken Sie auf **Alle bearbeiten**.
1. Wählen Sie **imDocument.docx** unter **Aufbewahrungsbezeichnung** anwenden die Bezeichnung **Streng vertraulich** aus, und wählen Sie dann **Speichern aus.**

## <a name="next-step"></a>Nächster Schritt

Erkunden Sie [zusätzliche Features und](m365-enterprise-test-lab-guides.md#information-protection) Funktionen zum Schutz von Informationen in Ihrer Testumgebung.

## <a name="see-also"></a>Siehe auch

[Testumgebungsanleitungen für Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Übersicht über Microsoft 365 Enterprise](microsoft-365-overview.md)

[Dokumentation zu Microsoft 365 Enterprise](/microsoft-365-enterprise/)