---
title: Überprüfen von Ereignissen und Fehlern mithilfe der Ereignisanzeige
description: Erhalten Sie Beschreibungen und weitere Schritte zur Problembehandlung (falls erforderlich) für alle Ereignisse, die vom Microsoft Defender for Endpoint-Dienst gemeldet wurden.
keywords: Problembehandlung, Ereignisanzeige, Protokollzusammenfassung, Fehlercode, Fehler, Microsoft Defender for Endpoint-Dienst, kann nicht gestartet, unterbrochen, nicht gestartet werden
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 05/21/2018
ms.technology: mde
ms.openlocfilehash: 1b8454107b6a2737f1236a066c3a24a2b9c776cb
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222653"
---
# <a name="review-events-and-errors-using-event-viewer"></a>Überprüfen von Ereignissen und Fehlern mithilfe der Ereignisanzeige

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- Ereignisanzeige
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

Sie können Ereignis-IDs in der [Ereignisanzeige auf](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) einzelnen Geräten überprüfen.

Wenn Geräte beispielsweise nicht in der Liste Geräte angezeigt **werden,** müssen Sie möglicherweise nach Ereignis-IDs auf den Geräten suchen. Anschließend können Sie diese Tabelle verwenden, um weitere Schritte zur Problembehandlung zu ermitteln.

**Öffnen Sie die Ereignisanzeige, und suchen Sie das Microsoft Defender for Endpoint-Dienstereignisprotokoll:**

1. Klicken **Sie im** Menü Windows auf Start, geben Sie **Ereignisanzeige ein,** und drücken Sie die **EINGABETASTE.**

2. Führen Sie in der Protokollliste unter **Protokollzusammenfassung** einen Bildlauf durch, bis **Microsoft-Windows-SENSE/Operational angezeigt wird.** Doppelklicken Sie auf das Element, um das Protokoll zu öffnen.

   a.  Sie können auch auf das Protokoll zugreifen, indem Sie **Anwendungen und Dienstprotokolle** Microsoft Windows SENSE erweitern  >    >    >   und auf **Betriebs klicken.**

   > [!NOTE]
   > SENSE ist der interne Name, der verwendet wird, um auf den Verhaltenssensor zu verweisen, der Microsoft Defender for Endpoint unterstützt.

3. Vom Dienst aufgezeichnete Ereignisse werden im Protokoll angezeigt. Eine Liste der vom Dienst aufgezeichneten Ereignisse finden Sie in der folgenden Tabelle.

<table>
<tbody style="vertical-align:top;">
<tr>
<th>Ereigniskennung</th>
<th>Nachricht</th>
<th>Beschreibung</th>
<th>Aktion</th>
</tr>
<tr>
<td>1</td>
<td>Microsoft Defender for Endpoint Service gestartet (Version <code>variable</code> ).</td>
<td>Tritt während des Systemstarts, heruntergefahren und während des Onboardings auf.</td>
<td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
<td>2</td>
<td>Herunterfahren des Microsoft Defender for Endpoint-Diensts.</td>
<td>Tritt auf, wenn das Gerät heruntergefahren oder offboarded wird.</td>
<td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
<td>3</td>
<td>Der Microsoft Defender for Endpoint-Dienst konnte nicht gestartet werden. Fehlercode: <code>variable</code> .</td>
<td>Der Dienst wurde nicht gestartet.</td>
<td>Überprüfen Sie andere Nachrichten, um mögliche Ursachen und Schritte zur Problembehandlung zu ermitteln.</td>
</tr>
<tr>
<td>4 </td>
<td>Der Microsoft Defender for Endpoint-Dienst hat den Server unter <code>variable</code> kontaktiert.</td>
<td>Variable = URL der Defender for Endpoint-Verarbeitungsserver.<br>
Diese URL ist mit der In der Firewall- oder Netzwerkaktivität übereinstimmend.</td>
<td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
<td>5 </td>
<td>Microsoft Defender for Endpoint-Dienst konnte keine Verbindung mit dem Server unter <code>variable</code> herstellen.</td>
<td>Variable = URL der Defender for Endpoint-Verarbeitungsserver.<br>
Der Dienst konnte die externen Verarbeitungsserver unter dieser URL nicht kontaktieren.</td>
<td>Überprüfen Sie die Verbindung zur URL. Weitere Informationen finden Sie unter <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and internet connectivity</a>.</td>
</tr>
<tr>
<td>6 </td>
<td>Der Microsoft Defender for Endpoint-Dienst ist nicht onboarded, und es wurden keine Onboardingparameter gefunden.</td>
<td>Das Gerät wurde nicht ordnungsgemäß onboardiert und meldet nicht an das Portal.</td>
<td>Das Onboarding muss vor dem Starten des Diensts ausgeführt werden.<br>
Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden. Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.<br>
Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboarding von Windows 10-Geräten.</a></td>
</tr>
<tr>
<td>7 </td>
<td>Der Microsoft Defender for Endpoint-Dienst konnte die Onboardingparameter nicht lesen. Fehler: <code>variable</code> .</td>
<td>Variable = detaillierte Fehlerbeschreibung. Das Gerät wurde nicht ordnungsgemäß onboardiert und meldet nicht an das Portal.</td>
<td>Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden. Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.<br>
Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboarding von Windows 10-Geräten.</a></td>
</tr>
<tr>
<td>8 </td>
<td>Der Microsoft Defender for Endpoint-Dienst konnte seine Konfiguration nicht bereinigen. Fehlercode: <code>variable</code> .</td>
<td><b>Während des Onboardings:</b> Fehler beim Bereinigen der Konfiguration während des Onboardings durch den Dienst. Der Onboardingprozess wird fortgesetzt. <br><br> <b>Während des Offboardings:</b> Der Dienst konnte seine Konfiguration während des Offboardings nicht bereinigen. Der Offboardingvorgang wurde abgeschlossen, der Dienst wird jedoch weiterhin ausgeführt.
 </td>
<td><b>Onboarding:</b> Keine Aktion erforderlich. <br><br> <b>Offboarding:</b> Starten Sie das System neu.<br>
Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboarding von Windows 10-Geräten.</a></td>
</tr>
<tr>
<td>9 </td>
<td>Der Microsoft Defender for Endpoint-Dienst konnte seinen Starttyp nicht ändern. Fehlercode: <code>variable</code> .</td>
<td><b>Während des Onboardings:</b> Das Gerät wurde nicht ordnungsgemäß onboardiert und meldet nicht an das Portal. <br><br><b>Während des Offboardings:</b> Fehler beim Ändern des Dienststarttyps. Der Offboardingprozess wird fortgesetzt. </td>
<td>Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden. Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.<br>
Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboarding von Windows 10-Geräten.</a></td>
</tr>
<tr>
<td>10  </td>
<td>Der Microsoft Defender for Endpoint-Dienst konnte die Onboardinginformationen nicht beibehalten. Fehlercode: <code>variable</code> .</td>
<td>Das Gerät wurde nicht ordnungsgemäß onboardiert und meldet nicht an das Portal.</td>
<td>Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden. Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.<br>
Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboarding von Windows 10-Geräten.</a></td>
</tr>
<tr>
<td>11</td>
<td>Onboarding oder erneutes Onboarding des Defender for Endpoint-Diensts abgeschlossen.</td>
<td>Das Gerät wurde ordnungsgemäß onboardiert.</td>
<td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.<br>
Es kann mehrere Stunden dauern, bis das Gerät im Portal angezeigt wird.</td>
</tr>
<tr>
<td>12 </td>
<td>Microsoft Defender for Endpoint konnte die Standardkonfiguration nicht anwenden.</td>
<td>Der Dienst konnte die Standardkonfiguration nicht anwenden.</td>
<td>Dieser Fehler sollte nach kurzer Zeit behoben werden.</td>
</tr>
<tr>
<td>13</td>
<td>Microsoft Defender for Endpoint-Geräte-ID berechnet: <code>variable</code> .</td>
<td>Normaler Betriebsprozess.</td>
<td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
<td>15 </td>
<td>Microsoft Defender for Endpoint kann den Befehlskanal nicht mit DER URL starten: <code>variable</code> .</td>
<td>Variable = URL der Defender for Endpoint-Verarbeitungsserver.<br>
Der Dienst konnte die externen Verarbeitungsserver unter dieser URL nicht kontaktieren.</td>
<td>Überprüfen Sie die Verbindung zur URL. Weitere Informationen finden Sie unter <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and internet connectivity</a>.</td>
</tr>
<tr>
<td>17 </td>
<td>Der Microsoft Defender for Endpoint-Dienst konnte den Speicherort des Diensts für verbundene Benutzererfahrungen und Telemetrie nicht ändern. Fehlercode: <code>variable</code> .</td>
<td>Beim Windows-Telemetriedienst ist ein Fehler aufgetreten.</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Stellen Sie sicher, dass der Diagnosedatendienst aktiviert ist.</a><br>
Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden. Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.<br>
Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboarding von Windows 10-Geräten.</a></td>
</tr>
<tr>
<td>18 </td>
<td>OOBE (Windows Welcome) ist abgeschlossen.</td>
<td>Der Dienst wird erst gestartet, nachdem alle Windows-Updates installiert wurden.</td>
<td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
<td>19</td>
<td>OOBE (Windows Welcome) wurde noch nicht abgeschlossen.</td>
<td>Der Dienst wird erst gestartet, nachdem alle Windows-Updates installiert wurden.</td>
<td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.<br>
Wenn dieser Fehler nach einem Systemneustart weiterhin auftritt, stellen Sie sicher, dass alle Windows-Updates vollständig installiert sind.</td>
</tr>
<tr>
<td>20</td>
<td>Kann nicht warten, bis OOBE (Windows Welcome) abgeschlossen ist. Fehlercode: <code>variable</code> .</td>
<td>Interner Fehler.</td>
<td>Wenn dieser Fehler nach einem Systemneustart weiterhin auftritt, stellen Sie sicher, dass alle Windows-Updates vollständig installiert sind.</td>
</tr>
<tr>
<td>25</td>
<td>Der Microsoft Defender for Endpoint-Dienst konnte den Integritätsstatus in der Registrierung nicht zurücksetzen. Fehlercode: <code>variable</code> .</td>
<td>Das Gerät wurde nicht ordnungsgemäß onboardiert.
Er wird dem Portal gemeldet, der Dienst wird jedoch möglicherweise nicht in SCCM oder der Registrierung registriert angezeigt.</td>
<td>Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden. Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.<br>
Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboarding von Windows 10-Geräten.</a></td>
</tr>
<tr>
<td>26</td>
<td>Der Microsoft Defender for Endpoint-Dienst konnte den Onboardingstatus in der Registrierung nicht festlegen. Fehlercode: <code>variable</code> .</td>
<td>Das Gerät wurde nicht ordnungsgemäß onboardiert.<br>
Er wird dem Portal gemeldet, der Dienst wird jedoch möglicherweise nicht in SCCM oder der Registrierung registriert angezeigt.</td>
<td>Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden. Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.<br>
Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboarding von Windows 10-Geräten.</a></td>
</tr>
<tr>
<td>27</td>
<td>Der Microsoft Defender for Endpoint-Dienst konnte den SENSE-bewussten Modus in Microsoft Defender Antivirus nicht aktivieren. Fehler beim Onboardingprozess. Fehlercode: <code>variable</code> .</td>
<td>Normalerweise wird Microsoft Defender Antivirus in einen speziellen passiven Zustand ein, wenn ein anderes Antischasoftwareprodukt in Echtzeit ordnungsgemäß auf dem Gerät ausgeführt wird und das Gerät an Defender for Endpoint meldet.</td>
<td>Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden. Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.<br>
Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboarding von Windows 10-Geräten.</a><br>
Stellen Sie sicher, dass der Antischalwareschutz in Echtzeit ordnungsgemäß ausgeführt wird.</td>
</tr>
<tr>
<td>28</td>
<td>Fehler bei der Registrierung des Microsoft Defender for Endpoint Connected User Experiences and Telemetry Service. Fehlercode: <code>variable</code> .</td>
<td>Beim Windows-Telemetriedienst ist ein Fehler aufgetreten.</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Stellen Sie sicher, dass der Diagnosedatendienst aktiviert ist.</a><br>
Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden. Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.<br>
Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboarding von Windows 10-Geräten.</a></td>
</tr>
<tr>
<td>29</td>
<td>Fehler beim Lesen der offboarding-Parameter. Fehlertyp: %1, Fehlercode: %2, Beschreibung: %3 </td>
<td>Dieses Ereignis tritt auf, wenn das System&#39;offboarding-Parameter nicht lesen kann.</td>
<td>Stellen Sie sicher, dass das Gerät über Internetzugriff verfügt, und führen Sie dann den gesamten Offboardingvorgang erneut aus. Stellen Sie sicher, dass das offboarding-Paket nicht abgelaufen ist.</td>
</tr>
<tr>
<td>30</td>
<td>Der Microsoft Defender for Endpoint-Dienst konnte den SENSE-benachrichtigungsmodus in Microsoft Defender Antivirus nicht deaktivieren. Fehlercode: <code>variable</code> .</td>
<td>Normalerweise wird Microsoft Defender Antivirus in einen speziellen passiven Zustand ein, wenn ein anderes Antischasoftwareprodukt in Echtzeit ordnungsgemäß auf dem Gerät ausgeführt wird und das Gerät an Defender for Endpoint meldet.</td>
<td>Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden. Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.<br>
Siehe <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboarding von Windows 10-Geräten</a><br>
Stellen Sie sicher, dass der Antischalwareschutz in Echtzeit ordnungsgemäß ausgeführt wird.</td>
</tr>
<tr>
<td>31</td>
<td>Die Registrierung des Microsoft Defender for Endpoint Connected User Experiences and Telemetry Service ist fehlgeschlagen. Fehlercode: <code>variable</code> .</td>
<td>Beim Onboarding ist beim Windows-Telemetriedienst ein Fehler aufgetreten. Der Offboardingprozess wird fortgesetzt.</td>
<td><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Überprüfen Sie mit dem Windows-Telemetriedienst auf Fehler.</a></td>
</tr>
<tr>
<td>32</td>
<td>Der Microsoft Defender for Endpoint-Dienst konnte nicht anfordern, dass er sich nach dem Offboardingvorgang selbst beendet. Fehlercode: %1</td>
<td>Beim Offboarding ist ein Fehler aufgetreten.</td>
<td>Starten Sie das Gerät neu.</td>
</tr>
<tr>
<td>33</td>
<td>Microsoft Defender for Endpoint-Dienst konnte die SENSE-GUID nicht beibehalten. Fehlercode: <code>variable</code> .</td>
<td>Ein eindeutiger Bezeichner wird verwendet, um jedes Gerät zu repräsentieren, das an das Portal meldet.<br>
Wenn der Bezeichner nicht beibehalten wird, wird das gleiche Gerät möglicherweise zweimal im Portal angezeigt.</td>
<td>Überprüfen Sie die Registrierungsberechtigungen auf dem Gerät, um sicherzustellen, dass der Dienst die Registrierung aktualisieren kann.</td>
</tr>
<tr>
<td>34</td>
<td>Der Microsoft Defender for Endpoint-Dienst konnte sich nicht selbst als Abhängigkeit vom Dienst für verbundene Benutzererfahrungen und Telemetrie hinzufügen, wodurch der Onboardingprozess fehlschlagen konnte. Fehlercode: <code>variable</code> .</td>
<td>Beim Windows-Telemetriedienst ist ein Fehler aufgetreten.</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Stellen Sie sicher, dass der Diagnosedatendienst aktiviert ist.</a><br>
Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden. Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.<br>
Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboarding von Windows 10-Geräten.</a></td>
</tr>
<tr>
<td>35</td>
<td>Der Microsoft Defender for Endpoint-Dienst konnte sich nicht selbst als Abhängigkeit vom Dienst für verbundene Benutzererfahrungen und Telemetrie entfernen. Fehlercode: <code>variable</code> .</td>
<td>Beim Offboarding ist beim Windows-Telemetriedienst ein Fehler aufgetreten. Der Offboardingprozess wird fortgesetzt.
</td>
<td>Überprüfen Sie beim Windows-Diagnosedatendienst auf Fehler.</td>
</tr>
<tr>
<td>36</td>
<td>Die Registrierung des Microsoft Defender for Endpoint Connected User Experiences and Telemetry Service ist erfolgreich. Fertigstellungscode: <code>variable</code> .</td>
<td>Die Registrierung von Defender for Endpoint beim Dienst für verbundene Benutzererfahrungen und Telemetrie wurde erfolgreich abgeschlossen.</td>
<td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
<td>37</td>
<td>Microsoft Defender for Endpoint A module is about to exceed its quota. Modul: %1, Kontingent: {%2} {%3}, Prozentsatz der Kontingentauslastung: %4.</td>
<td>Das gerät hat fast das zugewiesene Kontingent des aktuellen 24-Stunden-Fensters verwendet. Es wird gedrosselt.</td>
<td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
<td>38</td>
<td>Die Netzwerkverbindung wird als niedrig identifiziert. Microsoft Defender for Endpoint kontaktiert den Server alle %1 Minuten. Gemessene Verbindung: %2, Internet verfügbar: %3, kostenloses Netzwerk verfügbar: %4.</td>
<td>Das Gerät verwendet ein gemessenes/kostenpflichtiges Netzwerk und kontaktiert den Server seltener.</td>
<td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
<td>39</td>
<td>Die Netzwerkverbindung wird als normal identifiziert. Microsoft Defender for Endpoint kontaktiert den Server alle %1 Minuten. Gemessene Verbindung: %2, Internet verfügbar: %3, kostenloses Netzwerk verfügbar: %4.</td>
<td>Das Gerät verwendet keine meterierte/kostenpflichtige Verbindung und kontaktiert den Server wie gewohnt.</td>
<td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
<td>40</td>
<td>Der Akkuzustand wird als niedrig gekennzeichnet. Microsoft Defender for Endpoint kontaktiert den Server alle %1 Minuten. Akkuzustand: %2.</td>
<td>Das Gerät hat einen niedrigen Akkustand und kontaktiert den Server seltener.</td>
<td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
<td>41</td>
<td>Der Akkuzustand wird als normal identifiziert. Microsoft Defender for Endpoint kontaktiert den Server alle %1 Minuten. Akkuzustand: %2.</td>
<td>Das Gerät hat keinen niedrigen Akkustand und kontaktiert den Server wie gewohnt.</td>
<td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
<td>42</td>
<td>Microsoft Defender for Endpoint WDATP-Komponente konnte keine Aktion ausführen. Komponente: %1, Aktion: %2, Ausnahmetyp: %3, Ausnahmemeldung: %4</td>
<td>Interner Fehler. Der Dienst konnte nicht gestartet werden.</td>
<td>Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</td>
</tr>
<tr>
<td>43</td>
<td>Microsoft Defender for Endpoint WDATP-Komponente konnte keine Aktion ausführen. Komponente: %1, Aktion: %2, Ausnahmetyp: %3, Ausnahmefehler: %4, Ausnahmemeldung: %5</td>
<td>Interner Fehler. Der Dienst konnte nicht gestartet werden.</td>
<td>Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</td>
</tr>
<tr>
<td>44</td>
<td>Offboarding des Defender for Endpoint-Diensts abgeschlossen.</td>
<td>Der Dienst wurde offboarded.</td>
<td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
<td>45</td>
<td>Fehler beim Registrieren und Starten der Ereignisverfolgungssitzung [%1]. Fehlercode: %2</td>
<td>Beim Starten des Diensts beim Erstellen einer ETW-Sitzung ist ein Fehler aufgetreten. Dies führte zu einem Fehler beim Starten des Diensts.</td>
<td>Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</td>
</tr>
<tr>
<td>46</td>
<td>Fehler beim Registrieren und Starten der Ereignisverfolgungssitzung [%1] aufgrund fehlender Ressourcen. Fehlercode: %2. Dies liegt wahrscheinlich daran, dass zu viele aktive Ereignisverfolgungssitzungen sind. Der Dienst wird in 1 Minute erneut versuchen.</td>
<td>Fehler beim Starten des Diensts beim Erstellen einer ETW-Sitzung aufgrund fehlender Ressourcen. Der Dienst wurde gestartet und wird ausgeführt, es wird jedoch erst ein Sensorereignis berichtet, wenn die ETW-Sitzung gestartet wurde.</td>
<td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich. Der Dienst versucht, die Sitzung jede Minute zu starten.</td>
</tr>
<tr>
<td>47</td>
<td>Die Ereignisverfolgungssitzung wurde erfolgreich registriert und gestartet – nach vorherigen fehlgeschlagenen Versuchen wiederhergestellt.</td>
<td>Dieses Ereignis folgt dem vorherigen Ereignis nach dem erfolgreichen Starten der ETW-Sitzung.</td>
<td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
<td>48</td>
<td>Fehler beim Hinzufügen eines Anbieters [%1] zur Ereignisverfolgungssitzung [%2]. Fehlercode: %3. Dies bedeutet, dass Ereignisse von diesem Anbieter nicht gemeldet werden.</td>
<td>Fehler beim Hinzufügen eines Anbieters zur ETW-Sitzung. Aus diesem Grund werden die Anbieterereignisse nicht gemeldet.</td>
<td>Überprüfen Sie den Fehlercode. Wenn der Fehler weiterhin auftritt, wenden Sie sich an den Support.</td>
</tr>
</tr>
<tr>
   <td>49</td>
   <td>Ungültiger Cloudkonfigurationsbefehl empfangen und ignoriert. Version: %1, Status: %2, Fehlercode: %3, Meldung: %4</td>
   <td>Vom Clouddienst wurde eine ungültige Konfigurationsdatei empfangen, die ignoriert wurde.</td>
   <td>Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</td>
</tr>
<tr>
   <td>50</td>
   <td>Neue Cloudkonfiguration wurde erfolgreich angewendet. Version: %1.</td>
   <td>Eine neue Konfiguration wurde erfolgreich vom Clouddienst angewendet.</td>
   <td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
   <td>51</td>
   <td>Neue Cloudkonfiguration konnte nicht angewendet werden, Version: %1. Die letzte bekannte gute Konfiguration, Version %2, wurde erfolgreich angewendet.</td>
   <td>Vom Clouddienst wurde eine ungültige Konfigurationsdatei empfangen. Die letzte bekannte gute Konfiguration wurde erfolgreich angewendet.</td>
   <td>Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</td>
</tr>
<tr>
   <td>52</td>
   <td>Neue Cloudkonfiguration konnte nicht angewendet werden, Version: %1. Außerdem konnte die letzte bekannte gute Konfiguration, Version %2, nicht angewendet werden. Die Standardkonfiguration wurde erfolgreich angewendet.</td>
   <td>Vom Clouddienst wurde eine ungültige Konfigurationsdatei empfangen. Fehler beim Anwenden der letzten als gut bekannten Konfiguration – und die Standardkonfiguration wurde angewendet.</td>
   <td>Der Dienst versucht, innerhalb von 5 Minuten eine neue Konfigurationsdatei herunterzuladen. Wenn das Ereignis nicht #50 , wenden Sie sich an den Support.</td>
</tr>
<tr>
   <td>53</td>
   <td>Cloudkonfiguration, die aus dem beständigen Speicher geladen wird, Version: %1.</td>
   <td>Die Konfiguration wurde beim Starten des Diensts aus dem beständigen Speicher geladen.</td>
   <td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
   <td>55</td>
   <td>Fehler beim Erstellen des Secure ETW-Autologgers. Fehlercode: %1</td>
   <td>Fehler beim Erstellen des sicheren ETW-Loggers.</td>
   <td>Starten Sie das Gerät neu. Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</td>
</tr>
<tr>
   <td>56</td>
   <td>Fehler beim Entfernen des Secure ETW-Autologgers. Fehlercode: %1</td>
   <td>Fehler beim Entfernen der sicheren ETW-Sitzung beim Offboarding.</td>
   <td>Wenden Sie sich an den Support.</td>
</tr>
<tr>
   <td>57</td>
   <td>Erfassen einer Momentaufnahme des Computers zur Problembehandlung.</td>
   <td>Ein Untersuchungspaket, das auch als Forensikpaket bezeichnet wird, wird gesammelt.</td>
   <td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
   <td>59</td>
   <td>Startbefehl: %1</td>
   <td>Starten der Ausführung des Antwortbefehls.</td>
   <td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
   <td>60</td>
   <td>Befehl "%1" konnte nicht ausgeführt werden, Fehler: %2.</td>
   <td>Antwortbefehl konnte nicht ausgeführt werden.</td>
   <td>Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</td>
</tr>
<tr>
   <td>61</td>
   <td>Parameter des Datensammlungsbefehls sind ungültig: SasUri: %1, compressionLevel: %2.</td>
   <td>Fehler beim Lesen oder Analysieren der Datensammlungsbefehlsargumente (ungültige Argumente).</td>
   <td>Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</td>
</tr>
<tr>
   <td>62</td>
   <td>Fehler beim Starten des Diensts für verbundene Benutzererfahrungen und Telemetrie. Fehlercode: %1</td>
   <td>Der Dienst für verbundene Benutzererfahrungen und Telemetrie (Diagtrack) konnte nicht gestartet werden. Telemetriedaten von Nicht-Microsoft Defender for Endpoint werden nicht von diesem Computer gesendet.</td>
   <td>Weitere Hinweise zur Problembehandlung finden Sie im Ereignisprotokoll: Microsoft-Windows-UniversalTelemetryClient/Operational.</td>
</tr>
<tr>
   <td>63</td>
   <td>Aktualisieren des Starttyps des externen Diensts. Name: %1, tatsächlicher Starttyp: %2, erwarteter Starttyp: %3, Exitcode: %4</td>
   <td>Der Starttyp des externen Diensts wurde aktualisiert.</td>
   <td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
   <td>64</td>
   <td>Starten des beendeten externen Diensts. Name: %1, Exitcode: %2</td>
   <td>Starten eines externen Diensts.</td>
   <td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
   <td>65</td>
   <td>Microsoft Security Events Component Minifilter-Treiber konnte nicht geladen werden. Fehlercode: %1</td>
   <td>Fehler beim Laden MsSecFlt.sys Dateisystem-Minifilters.</td>
   <td>Starten Sie das Gerät neu. Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</td>
</tr>
<tr>
   <td>66</td>
   <td>Richtlinienupdate: Latenzmodus – %1</td>
   <td>Die C&C-Verbindungshäufigkeitsrichtlinie wurde aktualisiert.</td>
   <td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
   <td>68</td>
   <td>Der Starttyp des Diensts ist unerwartet. Dienstname: %1, tatsächlicher Starttyp: %2, erwarteter Starttyp: %3</td>
   <td>Unerwarteter Starttyp des externen Diensts.</td>
   <td>Fix the external service start type.</td>
</tr>
<tr>
   <td>69</td>
   <td>Der Dienst wird beendet. Dienstname: %1</td>
   <td>Der externe Dienst wird beendet.</td>
   <td>Starten Sie den externen Dienst.</td>
</tr>
<tr>
   <td>70</td>
   <td>Richtlinienupdate: Beispielsammlung zulassen – %1</td>
   <td>Die Beispielsammlungsrichtlinie wurde aktualisiert.</td>
   <td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
   <td>71</td>
   <td>Befehl konnte erfolgreich ausgeführt werden: %1</td>
   <td>Der Befehl wurde erfolgreich ausgeführt.</td>
   <td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
   <td>72</td>
   <td>Es wurde versucht, den ersten vollständigen Computerprofilbericht zu senden. Ergebniscode: %1</td>
   <td>Nur Information.</td>
   <td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
   <td>73</td>
   <td>Sinn beim Starten der Plattform: %1</td>
   <td>Nur Information.</td>
   <td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
   <td>74</td>
   <td>Das Gerätetag in der Registrierung überschreitet die Längenbeschränkung. Tagname: %2. Längenbeschränkung: %1.</td>
   <td>Das Gerätetag überschreitet den Längengrenzwert.</td>
   <td>Verwenden Sie ein kürzeres Gerätetag.</td>
</tr>
<tr>
   <td>81</td>
   <td>Fehler beim Erstellen Windows Defender Advanced Threat Protection ETW-Autologgers. Fehlercode: %1</td>
   <td>Fehler beim Erstellen der ETW-Sitzung.</td>
   <td>Starten Sie das Gerät neu. Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</td>
</tr>
<tr>
   <td>82</td>
   <td>Fehler beim Entfernen Windows Defender Advanced Threat Protection ETW-Autologgers. Fehlercode: %1</td>
   <td>Fehler beim Löschen der ETW-Sitzung.</td>
   <td>Wenden Sie sich an den Support.</td>
</tr>
<tr>
   <td>84</td>
   <td>Festlegen Windows Defender Antivirus-Ausführungsmodus. Erzwingen des passiven Modus: %1, Ergebniscode: %2.</td>
   <td>Festlegen des laufenden Defender-Modus (aktiv oder passiv).</td>
   <td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
   <td>85</td>
   <td>Fehler beim Auslösen der Windows Defender Advanced Threat Protection. Fehlercode: %1</td>
   <td>Fehler beim Ausführen der ausführbaren SenseIR-Datei.</td>
   <td>Starten Sie das Gerät neu. Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</td>
</tr>
<tr>
   <td>86</td>
   <td>Beim erneuten Starten wurde der externe Dienst beendet, der eingerichtet werden sollte. Name: %1, Exitcode: %2</td>
   <td>Starten Sie den externen Dienst erneut.</td>
   <td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
   <td>87</td>
   <td>Der externe Dienst kann nicht gestartet werden. Name: %1</td>
   <td>Fehler beim Starten des externen Diensts.</td>
   <td>Wenden Sie sich an den Support.</td>
</tr>
<tr>
   <td>88</td>
   <td>Aktualisieren des Starttyps des externen Diensts erneut. Name: %1, tatsächlicher Starttyp: %2, erwarteter Starttyp: %3, Exitcode: %4</td>
   <td>Der Starttyp des externen Diensts wurde aktualisiert.</td>
   <td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
   <td>89</td>
   <td>Der Starttyp des externen Diensts kann nicht aktualisiert werden. Name: %1, tatsächlicher Starttyp: %2, erwarteter Starttyp: %3</td>
   <td>Der Starttyp des externen Diensts kann nicht aktualisiert werden.</td>
   <td>Wenden Sie sich an den Support.</td>
</tr>
<tr>
   <td>90</td>
   <td>Fehler beim Konfigurieren des System Guard-Laufzeitmonitors für die Verbindung mit dem Clouddienst in der geografischen Region "%1". Fehlercode: %2</td>
   <td>System Guard Runtime Monitor sendet keine Nachweisdaten an den Clouddienst.</td>
   <td>Überprüfen Sie die Berechtigungen im Registerpfad: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm". Wenn keine Probleme auftreten, wenden Sie sich an den Support.</td>
</tr>
<tr>
   <td>91</td>
   <td>Fehler beim Entfernen von Informationen zur geografischen Region des System Guard-Runtime-Monitors. Fehlercode: %1</td>
   <td>System Guard Runtime Monitor sendet keine Nachweisdaten an den Clouddienst.</td>
   <td>Überprüfen Sie die Berechtigungen im Registerpfad: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm". Wenn keine Probleme auftreten, wenden Sie sich an den Support.</td>
</tr>
<tr>
   <td>92</td>
   <td>Beenden des Sendens des Cyberdatenkontingents des Sensors, da das Datenkontingent überschritten wird. Wird das Senden fortgesetzt, sobald der Kontingentzeitraum vergeht. Zustandsmaske: %1</td>
   <td>Drosselungsgrenzwert überschreiten.</td>
   <td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
   <td>93</td>
   <td>Fortsetzen des Sendens von Sensor-Cyberdaten. Zustandsmaske: %1</td>
   <td>Fortsetzen der Cyberdatenübermittlung.</td>
   <td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
   <td>94</td>
   <td>Windows Defender der ausführbaren Datei Advanced Threat Protection wurde gestartet</td>
   <td>Die ausführbare Datei SenseCE wurde gestartet.</td>
   <td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
   <td>95</td>
   <td>Windows Defender der ausführbaren Datei "Advanced Threat Protection" wurde beendet</td>
   <td>Die ausführbare Datei SenseCE wurde beendet.</td>
   <td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
   <td>96</td>
   <td>Windows Defender Advanced Threat Protection Init wurde aufgerufen. Ergebniscode: %2</td>
   <td>Die ausführbare SenseCE-Datei hat die MCE-Initialisierung aufgerufen.</td>
   <td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
   <td>97</td>
   <td>Es gibt Konnektivitätsprobleme mit der Cloud für das DLP-Szenario</td>
   <td>Es gibt Netzwerkkonnektivitätsprobleme, die sich auf den DLP-Klassifizierungsfluss auswirken.</td>
   <td>Überprüfen Sie die Netzwerkkonnektivität.</td>
</tr>
<tr>
   <td>98</td>
   <td>Die Konnektivität mit der Cloud für das DLP-Szenario wurde wiederhergestellt.</td>
   <td>Die Verbindung mit dem Netzwerk wurde wiederhergestellt, und der DLP-Klassifizierungsfluss kann fortgesetzt werden.</td>
   <td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
   <td>99</td>
   <td>Bei der Kommunikation mit dem Server ist der folgende Fehler aufgetreten: (%1). Ergebnis: (%2)</td>
   <td>Ein Kommunikationsfehler ist aufgetreten.</td>
   <td>Überprüfen Sie die folgenden Ereignisse im Ereignisprotokoll auf weitere Details.</td>
</tr>
<tr>
   <td>100</td>
   <td>Windows Defender der ausführbaren Datei Advanced Threat Protection konnte nicht gestartet werden. Fehlercode: %1</td>
   <td>Die ausführbare Datei SenseCE konnte nicht gestartet werden.</td>
   <td>Starten Sie das Gerät neu. Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</td>
</tr>
<tr>
   <td>102</td>
   <td>Windows Defender advanced Threat Protection Network Detection and Response executable has started</td>
   <td>Die ausführbare Datei SenseNdr wurde gestartet.</td>
   <td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
   <td>103</td>
   <td>Windows Defender advanced Threat Protection Network Detection and Response executable has ended</td>
   <td>Die ausführbare Datei SenseNdr wurde beendet.</td>
   <td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
</tbody>
</table>

>Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a>Verwandte Themen
- [Onboarding von Windows 10-Geräten](configure-endpoints.md)
- [Konfigurieren von Geräteproxy- und Internetverbindungseinstellungen](configure-proxy-internet.md)
- [Problembehandlung für Microsoft Defender for Endpoint](troubleshoot-onboarding.md)
