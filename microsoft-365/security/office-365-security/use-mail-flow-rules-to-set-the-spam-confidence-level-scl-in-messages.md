---
title: Verwenden von Nachrichtenflussregeln zum Festlegen der SCL-Bewertung (Spam Confidence Level) in Nachrichten
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie die SCL-Bewertung von Nachrichten in Exchange Online Schutz festlegen.
ms.openlocfilehash: 627284a1c2a7463989ca3050b2becbff780cf3d6
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082389"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a>Verwenden von Nachrichtenflussregeln zum Festlegen der SCL-Bewertung (Spam Confidence Level) in Nachrichten

Sie können eine e-Mail-Fluss Regel (auch als Transportregel bezeichnet) erstellen, mit der die SCL-Bewertung (Spam Confidence Level) einer e-Mail-Nachricht festgelegt wird. Die SCL-Bewertung ist ein Maßstab dafür, wie wahrscheinlich es ist, dass es sich bei einer Nachricht um Spam handelt. Spam sind unverlangt zugesandte (und normalerweise unerwünschte) E-Mail-Nachrichten. Dieser Dienst kann verschiedene Aktionen für eine Nachricht ausführen, die von ihrer SCL-Bewertung abhängen. Beispielsweise können Sie die Spam Inhaltsfilterung für Nachrichten umgehen, die von Personen innerhalb Ihrer Organisation gesendet werden, da Sie darauf vertrauen, dass eine intern von einem Kollegen gesendete Nachricht kein Spam ist. Durch die Verwendung von Nachrichtenfluss Regeln zum Festlegen des SCL-Werts einer Nachricht erhalten Sie eine erhöhte Kontrolle bei der Verarbeitung von Spam. 
  
 **Was sollten Sie wissen, bevor Sie beginnen?**
  
- Geschätzte Zeit bis zum Abschließen dieses Verfahrens: 10 Minuten.
    
- Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Informationen zu den von Ihnen benötigten Berechtigungen finden Sie unter "Nachrichtenfluss Regeln" in [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) oder [Feature Permissions in EoP](feature-permissions-in-eop.md). 
    
- Informationen zu Tastenkombinationen, die möglicherweise für die Verfahren in diesem Thema gelten, finden Sie unter [Tastenkombinationen für das Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).
    
### <a name="to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a>So erstellen Sie eine Nachrichtenfluss Regel, die den SCL-Wert einer Nachricht festlegt

1. Navigieren Sie in der Exchange-Verwaltungskonsole (EAC) zu **Nachrichtenfluss** \> **Regeln**.
    
2. Klicken Sie auf **Neu**![Hinzufügen (Symbol)](../media/ITPro-EAC-AddIcon.gif), und wählen Sie dann **Eine neue Regel erstellen** aus.
    
3. Geben Sie einen Namen für die Regel ein.
    
4. Klicken Sie auf **Weitere Optionen**, und geben Sie anschließend unter **Diese Regel anwenden, wenn** eine Bedingung an, durch die die Aktion ausgelöst wird, die Sie für diese Regel festlegen (in diesem Falle die Festlegung des SCL-Werts).
    
    Sie können z. B. festlegen **Der Absender** \> **ist intern/extern** und anschließend im Dialogfeld **Absenderposition auswählen** auf die Option **Innerhalb meiner Organisation** und auf **OK** klicken.<br/>
    ![Absenderstandort auswählen](../media/EOP-ETR-SetSCL-1.jpg)
  
5. Wählen Sie unter **Gehen Sie folgendermaßen vor...** die Option **Nachrichteneigenschaften ändern** \> **SCL-Bewertung (Spam Confidence Level) festlegen** aus.
  
6. Wählen sie im Dialogfeld **SCL angeben** einen der folgenden Werte aus, und klicken Sie auf **OK**:
    
  - **Spamfilter umgehen** - Mit dieser Option wird der SCL-Wert auf -1 gesetzt, was bedeutet, dass keine Inhaltsfilterung durchgeführt wird. 
    
  - **0-4** - Wenn Sie den SCL auf einen dieser Werte setzen, wird die Nachricht zur weiteren Verarbeitung an den Inhaltsfilter weitergeleitet. 
    
  - **5, 6** - Wenn Sie den SCL auf einen dieser Werte setzen, wird die Aktion durchgeführt, die in der entsprechenden Inhaltsfilterrichtlinie für **Spam** festgelegt ist. Die Standardaktion ist das Senden der Nachricht an den Junk-E-Mail-Ordner des Empfängers. 
    
  - **7-9** - Wenn Sie den SCL auf einen dieser Werte setzen, wird die Aktion durchgeführt, die in der entsprechenden Inhaltsfilterrichtlinie für **Nachricht mit hoher Spamwahrscheinlichkeit** festgelegt ist. Die Standardaktion ist das Senden der Nachricht an den Junk-E-Mail-Ordner des Empfängers. 
    
    Weitere Informationen zum Konfigurieren Ihrer Inhaltsfilterrichtlinien finden Sie unter [Konfigurieren von Spamfilterrichtlinien](configure-your-spam-filter-policies.md). Weitere Informationen zu SCL-Werten in diesem Dienst finden Sie unter [SCL-Bewertungen (Spam Confidence Level)](spam-confidence-levels.md).
    
7. Geben Sie zusätzliche Eigenschaften für die Regel an, und wählen Sie **Speichern**.
    
    > [!TIP]
    > Weitere Informationen zu den zusätzlichen Eigenschaften, die Sie für diese Regel auswählen oder angeben können, finden Sie unter [Verwenden der Exchange-Verwaltungskonsole zum Erstellen von Nachrichtenfluss Regeln](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures#use-the-eac-to-create-mail-flow-rules). 
  
## <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Wenn Sie verifizieren möchten, dass das Verfahren ordnungsgemäß funktioniert, senden Sie eine E-Mail-Nachricht an einen Mitarbeiter in Ihrer Organisation, und prüfen Sie, ob die erwartete Aktion mit der Nachricht durchgeführt wird. Wenn Sie z. B. **den SCL-Wert (Spam Confidence Level)** auf **Spamfilterung umgehen** setzen, sollte die Nachricht an das Postfach des angegebenen Empfängers gesendet werden. Wenn Sie allerdings **den SCL-Wert (Spam Confidence Level)** auf **9** gesetzt haben und die Aktion in der entsprechenden Inhaltsfilterungsrichtlinie für eine **Nachricht mit hoher Spamwahrscheinlichkeit** darin besteht, die Nachricht in den Junk-E-Mail-Ordner zu verschieben, sollte die Nachricht an den Junk-E-Mail-Ordner des angegebenen Empfängers gesendet werden. 
  

