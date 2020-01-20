---
title: Erstellen und Veröffentlichen von Vertraulichkeitsbezeichnungen
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Anweisungen zum Erstellen, Konfigurieren und Veröffentlichen von Vertraulichkeitsbezeichnungen, um die Dokumente und E-Mails Ihres Unternehmens zu klassifizieren und zu schützen.
ms.openlocfilehash: edcfcf5a4f4891e4e1159c4c42327e59ceb35449
ms.sourcegitcommit: a122fd1fce523171529c7f610bb7faf09d30a8bb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/18/2020
ms.locfileid: "41238402"
---
# <a name="create-and-configure-sensitivity-labels-and-their-policies"></a>Erstellen und Konfigurieren von Vertraulichkeitsbezeichnungen und deren Richtlinien

Um Ihre [Vertraulichkeitsbezeichnungen](sensitivity-labels.md) zu erstellen und zu veröffentlichen, gehen Sie zu Ihrem Admin Center für Bezeichnungen, z. B. zum [Microsoft 365 Compliance Center](https://compliance.microsoft.com/). Sie können auch das Microsoft 365 Security Center oder das Office 365 Security & Compliance Center verwenden.

Erstellen und konfigurieren Sie zunächst die Vertraulichkeitsbezeichnungen, die Sie in Office-Anwendungen und für Dienste zur Verfügung stellen möchten. Erstellen Sie dann eine oder mehrere Bezeichnungsrichtlinien mit den von Ihnen konfigurierten Bezeichnungen und Richtlinieneinstellungen. Es ist die Bezeichnungsrichtlinie, die die Bezeichnungen und Einstellungen für die von Ihnen ausgewählten Benutzer und Standorte veröffentlicht.

## <a name="create-and-configure-sensitivity-labels"></a>Erstellen und Konfigurieren von Vertraulichkeitsbezeichnungen

1. Navigieren Sie in Ihrem Admin Center für Bezeichnungen zu Vertraulichkeitsbezeichnungen:
    
    - Microsoft 365 Compliance Center: 
        - **Lösungen** > **Informationsschutz (Vorschau)**
        
        Wenn diese Option nicht sofort angezeigt wird, wählen Sie zunächst **Alle anzeigen** aus. 
    
    - Microsoft 365 Security Center: 
        - **Klassifizierung** > **Vertraulichkeitsbezeichnungen**
    
    - Office 365 Security & Compliance Center:
        - **Klassifizierung** > **Vertraulichkeitsbezeichnungen**

2. Wählen Sie auf der Registerkarte **Bezeichnungen** die Option **+ Bezeichnung erstellen**, um den Assistenten **Neue Vertraulichkeitsbezeichnung** zu starten.

3. Folgen Sie den Eingabeaufforderungen für die Bezeichnungseinstellungen.
    
    Weitere Informationen zu den Bezeichnungseinstellungen finden Sie unter [Wirkung von Vertraulichkeitsbezeichnungen](sensitivity-labels.md#what-sensitivity-labels-can-do) in den Übersichtsinformationen.

4. Wiederholen Sie diese Schritte, um weitere Bezeichnungen zu erstellen. Wenn Sie jedoch eine Unterbezeichnung erstellen möchten, wählen Sie zuerst die übergeordnete Bezeichnung sowie **...** für **Weitere Aktionen** und dann **Unterbezeichnung hinzufügen** aus.

5. Wenn Sie alle benötigten Bezeichnungen erstellt haben, bringen Sie sie bei Bedarf durch Verschieben nach oben oder unten in die gewünschte Reihenfolge. Wenn Sie die Reihenfolge der Bezeichnungen ändern möchten, wählen Sie **...** für **Weitere Aktionen** und dann **Nach oben** oder **Nach unten** aus. Weitere Informationen hierzu finden Sie unter [Priorität der Bezeichnungen (Reihenfolge wesentlich)](sensitivity-labels.md#label-priority-order-matters) aus den Übersichtsinformationen.

Um eine vorhandene Bezeichnung zu bearbeiten, markieren Sie sie, und wählen Sie dann **Bezeichnung bearbeiten** aus. Dadurch wird der Assistent **Vertraulichkeitsbezeichnung bearbeiten** gestartet, mit dem Sie alle Bezeichnungseinstellungen in Schritt 3 ändern können. Wenn die Bezeichnung bereits mithilfe einer Bezeichnungsrichtlinie veröffentlicht wurde, sind keine weiteren Schritte erforderlich, aber es können bis zu 24 Stunden vergehen, bis die Änderungen an Benutzer und Standorte repliziert wurden.

Solange Sie Ihre Bezeichnungen noch nicht veröffentlicht haben, stehen sie in Apps oder für Services nicht zur Verfügung. Um die Bezeichnungen zu veröffentlichen, müssen sie zu einer Bezeichnungsrichtlinie hinzugefügt werden.

### <a name="additional-label-settings-with-office-365-security--compliance-center-powershell"></a>Zusätzliche Bezeichnungseinstellungen mit Office 365 Security & Compliance Center PowerShell

Zusätzliche Bezeichnungseinstellungen sind mit dem Cmdlet [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) von [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps) verfügbar.

Verwenden Sie z. B. den Parameter *LocaleSettings*, um verschiedene Sprachen für Ihre Bezeichnungsnamen und QuickInfos festzulegen. 

Mit diesem Cmdlet können Sie auch [erweiterte Einstellungen](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) für den Azure Information Protection-Client für einheitliche Bezeichnungen festlegen. Diese erweiterten Einstellungen umfassen das Festlegen einer Bezeichnungsfarbe und das Anwenden einer benutzerdefinierten Eigenschaft bei Auswahl einer Bezeichnung. Die vollständige Liste finden Sie unter [Verfügbare erweiterte Einstellungen für Bezeichnungsrichtlinien](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-label-policies). 

## <a name="publish-sensitivity-labels-by-creating-a-label-policy"></a>Veröffentlichen von Vertraulichkeitsbezeichnungen durch Erstellen einer Bezeichnungsrichtlinie

1. Navigieren Sie in Ihrem Admin Center für Bezeichnungen zu **Klassifizierung** > **Vertraulichkeitsbezeichnungen**.

2. Wählen Sie die Registerkarte **Bezeichnungsrichtlinien** aus.

3. Wählen Sie **Bezeichnungen veröffentlichen**, um den **Assistenten zum Erstellen von Richtlinien** zu starten.

4. Wählen Sie **Zu veröffentlichende Vertraulichkeitsbezeichnungen auswählen** aus. Wählen Sie die Bezeichnungen, die Sie in Apps und Diensten zur Verfügung stellen möchten, und dann **Hinzufügen** aus.

5. Überprüfen Sie die ausgewählten Bezeichnungen, und wählen Sie **Bearbeiten** aus, wenn Sie Änderungen vornehmen möchten. Anderenfalls klicken Sie auf **Weiter**.

6. Folgen Sie den Eingabeaufforderungen, um die Richtlinieneinstellungen zu konfigurieren.
    
    Weitere Informationen zu den Einstellungen finden Sie unter [Wirkung von Bezeichnungsrichtlinien](sensitivity-labels.md#what-label-policies-can-do) in den Übersichtsinformationen.

7. Wiederholen Sie diese Schritte, wenn Sie für verschiedene Benutzer oder Standorte unterschiedliche Richtlinieneinstellungen benötigen. Sie möchten z. B. zusätzliche Bezeichnungen für eine Gruppe von Benutzern oder eine andere Standardbezeichnung für eine Untergruppe von Benutzern festlegen.

8. Wenn Sie mehrere Bezeichnungsrichtlinie erstellen, die zu einem Konflikt für einen Benutzer oder Standort führen könnten, überprüfen Sie die Reihenfolge der Richtlinien und verschieben Sie einzelne Richtlinien gegebenenfalls nach oben oder unten. Wenn Sie die Reihenfolge der Bezeichnungsrichtlinien ändern möchten, wählen Sie **...** für **Weitere Aktionen** und dann **Nach oben** oder **Nach unten** aus. Weitere Informationen hierzu finden Sie unter [Priorität der Bezeichnungsrichtlinien (Reihenfolge wesentlich)](sensitivity-labels.md#label-policy-priority-order-matters) aus den Übersichtsinformationen.

Nach Abschluss des Assistenten wird die Bezeichnungsrichtlinie automatisch veröffentlicht. Um Änderungen an einer veröffentlichten Richtlinie vorzunehmen, bearbeiten Sie diese einfach. Es gibt keine spezielle Aktion zum Veröffentlichen oder Wiederveröffentlichen, die Sie auswählen können.

Um eine vorhandene Bezeichnungsrichtlinie zu bearbeiten, markieren Sie sie, und wählen Sie dann **Richtlinie bearbeiten** aus. Hierdurch wird der Assistent **Richtlinie erstellen** gestartet, mit dem Sie die Bezeichnungen und die Bezeichnungseinstellungen bearbeiten können. Wenn Sie den Assistenten abschließen, werden alle Änderungen automatisch auf die ausgewählten Benutzer und Standorte repliziert. Es kann bis zu 24 Stunden dauern, bis die Replikation abgeschlossen ist.

### <a name="additional-label-policy-settings-with-office-365-security--compliance-center-powershell"></a>Zusätzliche Bezeichnungsrichtlinieneinstellungen mit Office 365 Security & Compliance Center PowerShell

Zusätzliche Bezeichnungsrichtlinieneinstellungen sind mit dem Cmdlet [Set-Label](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-label?view=exchange-ps) von [Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/office-365-scc-powershell?view=exchange-ps) verfügbar.

Mit diesem Cmdlet können Sie [erweiterte Einstellungen](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations) für den Azure Information Protection-Client für einheitliche Bezeichnungen festlegen. Diese erweiterten Einstellungen umfassen das Festlegen einer anderen Standardbezeichnung für Outlook und das Implementieren von Popupmeldungen in Outlook zum Warnen, Rechtfertigen oder Blockieren des Versendens von E-Mails. Die vollständige Liste finden Sie unter [Verfügbare erweiterte Einstellungen für Bezeichnungen](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations#available-advanced-settings-for-labels). 

Sie können dieses Cmdlet auch zum Hinzufügen von Bezeichnungen zu und Entfernen von Bezeichnungen aus einer Bezeichnungsrichtlinie verwenden.


## <a name="next-steps"></a>Nächste Schritte

Informationen zum Konfigurieren und Verwenden Ihrer Vertraulichkeitsbezeichnungen für bestimmte Szenarien finden Sie in den folgenden Artikeln:

- [Einschränken des Zugriffs auf Inhalte mithilfe der Verschlüsselung in Vertraulichkeitsbezeichnungen](encryption-sensitivity-labels.md)

- [Automatisches Anwenden einer Vertraulichkeitsbezeichnung auf Inhalte](apply-sensitivity-label-automatically.md)

- [Verwenden von Vertraulichkeitsbezeichnungen für Teams, Gruppen und Websites](sensitivity-labels-teams-groups-sites.md)

- [Aktivieren von Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive](sensitivity-labels-sharepoint-onedrive-files.md)

Um zu überwachen, wie Ihre Bezeichnungen verwendet werden, lesen Sie [Anzeigen der Bezeichnungsnutzung mit der Analyse der Bezeichnungen](label-analytics.md).