---
title: Einrichten neuer Nachrichtenverschlüsselungsfunktionen
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Erfahren Sie mehr über die neuen Funktionen der Office 365-Nachrichtenverschlüsselung, die die geschützte E-Mail-Kommunikation mit Personen innerhalb und außerhalb Ihrer Organisation ermöglichen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4102611d3be43a5bedffc83fba5c83c0b648ca42
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547617"
---
# <a name="set-up-new-message-encryption-capabilities"></a>Einrichten neuer Nachrichtenverschlüsselungsfunktionen

Die neuen Funktionen der Office 365-Nachrichtenverschlüsselung (OME) ermöglichen es Organisationen, geschützte E-Mails mit anderen Personen auf jedem Gerät freizugeben. Benutzer können geschützte Nachrichten mit anderen Microsoft 365-Organisationen sowie Nicht-Kunden austauschen, die Outlook.com, Gmail und andere E-Mail-Dienste verwenden.

Führen Sie die folgenden Schritte aus, um sicherzustellen, dass die neuen OME-Funktionen in Ihrer Organisation zur Verfügung stehen.

## <a name="verify-that-azure-rights-management-is-active"></a>Überprüfen Sie, dass Azure Rights Management aktiv ist.

Die neuen OME-Funktionen nutzen die Schutzfeatures in [Azure Rights Management Services (Azure RMS)](https://docs.microsoft.com/azure/information-protection/what-is-information-protection), der Technologie, die von [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) zum Schützen von E-Mails und Dokumenten mithilfe von Verschlüsselung und Zugriffssteuerelementen verwendet wird.

Die einzige Voraussetzung für die Verwendung der neuen OME-Funktionen besteht darin, dass [Azure Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) im Mandanten Ihrer Organisation aktiviert sein muss. Wenn dies zutrifft, werden die neuen OME-Funktionen von Microsoft 365 automatisch aktiviert, und Sie müssen nichts unternehmen.

Azure RMS wird auch bei den meisten berechtigenden Plänen automatisch aktiviert, daher müssen Sie in dieser Hinsicht wahrscheinlich auch keine Maßnahmen ergreifen. Weitere Informationen hierzu finden Sie unter [Aktivieren von Azure Rights Management](https://docs.microsoft.com/azure/information-protection/activate-service).

>[!IMPORTANT]
>Wenn Sie Active Directory Rights Management Services (AD RMS) mit Exchange Online verwenden, müssen Sie zu [Azure Information Protection migrieren](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms), bevor Sie die neuen OME-Funktionen verwenden können. OME ist nicht kompatibel mit AD RMS.  

Weitere Informationen finden Sie unter:

- Lesen Sie [Welche Abonnements benötige ich, um die neuen OME-Funktionen nutzen zu können?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities), um zu überprüfen, ob Ihr Abonnementplan Azure Information Protection umfasst (das Azure RMS-Funktionen beinhaltet).
- Informationen zum Kauf eines berechtigenden Abonnements finden Sie unter [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).  

### <a name="manually-activating-azure-rights-management"></a>Manuelles Aktivieren von Azure Rights Management

Wenn Sie Azure RMS deaktiviert haben oder wenn es aus irgendeinem Grund nicht automatisch aktiviert wurde, können Sie es hier manuell im aktivieren:

- **Microsoft 365 Admin Center**: Anweisungen hierzu finden Sie unter [Aktivieren von Azure Rights Management im Admin Center](https://docs.microsoft.com/azure/information-protection/activate-office365).
- **Azure-Portal**: Anweisungen hierzu finden Sie unter [Aktivieren von Azure Rights Management im Azure-Portal](https://docs.microsoft.com/azure/information-protection/activate-azure).

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a>Konfigurieren der Verwaltung Ihres Azure Information Protection-Mandantenschlüssels

Dies ist ein optionaler Schritt. Microsoft das Verwalten des Hauptschlüssels für Azure Information Protection zu gestatten, ist die Standardeinstellung und wird als bewährte Methode für die meisten Organisationen empfohlen. In diesem Fall brauchen Sie nichts zu unternehmen.

Es gibt viele Gründe, beispielsweise Complianceanforderungen, aus denen Sie Ihren eigenen Hauptschlüssel generieren und verwalten müssen – auch als "Bring Your Own Key" (BYOK) bezeichnet. In diesem Fall empfehlen wir Ihnen, vor dem Einrichten der neuen OME-Funktionen die erforderlichen Schritte auszuführen. Weitere Informationen finden Sie unter [Planen und Implementieren Ihres Azure Information Protection-Mandantenschlüssels](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key).

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a>Überprüfen der neuen OME-Konfiguration in Exchange Online PowerShell

Sie können überprüfen, ob Ihr Microsoft 365-Mandant für die Verwendung der neuen OME-Funktionen in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell) ordnungsgemäß konfiguriert wurde.
  
1. [Stellen Sie eine Verbindung mit Exchange Online PowerShell her](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell), und verwenden Sie dafür ein Konto mit globalen Administratorberechtigungen in Ihrem Microsoft 365-Mandanten.

2. Führen Sie das Cmdlet "Get-IRMConfiguration" aus.

     Für den Parameter AzureRMSLicensingEnabled sollte der Wert "$True" angezeigt werden, der angibt, dass OME auf Ihrem-Mandanten konfiguriert ist. Ist das nicht der Fall, verwenden Sie "Set-IRMConfiguration", um den Wert von "AzureRMSLicensingEnabled" auf "$True" festzulegen, um OME zu aktivieren.

3. Führen Sie das Cmdlet "Test-IRMConfiguration" unter Verwendung der folgenden Syntax aus:

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   **Beispiel**:

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

     - Die Angabe der E-Mail-Adresse eines Absenders ist optional, aber durch diesen Wert wird das System gezwungen, zusätzliche Prüfungen durchzuführen. Verwenden Sie die E-Mail-Adresse eines beliebigen Benutzers in Ihrem Microsoft 365-Mandanten.

     Die Ergebnisse sollten in etwa folgendermaßen aussehen:

     ```text
     Results : Acquiring RMS Templates ...
                - PASS: RMS Templates acquired.  Templates available: Contoso  - Confidential View Only, Contoso  - Confidential, Do Not
            Forward.
            Verifying encryption ...
                - PASS: Encryption verified successfully.
            Verifying decryption ...
                - PASS: Decryption verified successfully.
            Verifying IRM is enabled ...
                - PASS: IRM verified successfully.

            OVERALL RESULT: PASS
     ```

   - Der Name Ihrer Organisation ersetzt *Contoso*.

   - Die Standardvorlagennamen unterscheiden sich möglicherweise von den vorstehenden. Weitere Informationen finden Sie unter [Konfigurieren und Verwalten von Vorlagen für Azure Information Protection](https://docs.microsoft.com/azure/information-protection/configure-policy-templates).

4. Führen Sie das Cmdlet "Remove-PSSession" aus, um die Verbindung mit dem Rights Management-Dienst zu trennen.

     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-mail-flow-rules-to-use-new-ome-capabilities"></a>Nächste Schritte: Definieren von Nachrichtenflussregeln, um neue OME-Funktionen zu verwenden

Wenn zuvor konfigurierte Nachrichtenflussregeln zum Verschlüsseln von E-Mails in Ihrer Organisation konfiguriert wurden, müssen Sie die vorhandenen Regeln zur Verwendung der neuen OME-Funktionen aktualisieren. Für neue Bereitstellungen müssen Sie neue Nachrichtenflussregeln erstellen.

>[!IMPORTANT]
>Wenn Sie vorhandene Nachrichtenflussregeln nicht aktualisieren, werden Ihre Benutzer weiterhin verschlüsselte E-Mails empfangen, bei denen das vorherige HTML-Anlagenformat statt der neuen, nahtlosen OME-Erfahrung verwendet wird.

Nachrichtenflussregeln bestimmen, unter welchen Bedingungen E-Mail-Nachrichten verschlüsselt werden sollten, sowie Bedingungen zum Entfernen dieser Verschlüsselung. Wenn Sie eine Aktion für eine Regel festlegen, werden alle Nachrichten, die den Regelbedingungen entsprechen, beim Senden verschlüsselt.
  
Schritte zum Erstellen von Nachrichtenflussregeln für OME finden Sie unter [Definieren von Nachrichtenflussregeln zum Verschlüsseln von E-Mail-Nachrichten in Office 365](define-mail-flow-rules-to-encrypt-email.md).

So aktualisieren Sie vorhandene Regeln so, dass die neuen OME-Funktionen verwendet werden:

1. Wechseln Sie im Microsoft 365 Admin Center zu **Admin Center > Exchange**.
2. Wechseln Sie im Exchange Admin Center zu **Nachrichtenfluss > Regeln**.
3. **Gehen Sie für jede Regel wie folgt vor**:
    - Wählen Sie **Nachrichtensicherheit ändern** aus.
    - Wählen Sie **Office 365-Nachrichtenverschlüsselung und Rechteschutz anwenden** aus.
    - Wählen Sie eine RMS-Vorlage aus der Liste aus.
    - Klicken Sie auf **Speichern**.
    - Wählen Sie **OK** aus.
