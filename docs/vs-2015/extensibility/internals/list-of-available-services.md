---
title: Liste der verfügbaren Dienste | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- services, Visual Studio
- Visual Studio, services
ms.assetid: 724eb24b-b87c-4971-a2e7-adee7afc03b2
caps.latest.revision: 50
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b09e58ee64eeb27940ea30f9a03429706b720cf0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47514397"
---
# <a name="list-of-available-services"></a>Liste der verfügbaren Dienste
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Liste der Verfügbaren\r\ndienste](https://docs.microsoft.com/visualstudio/extensibility/internals/list-of-available-services).  
  
[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] und Visual Studio SDK unterstützen die folgenden Dienste. Einige Pakete bieten, ihre eigenen Dienste, die hier nicht aufgeführt sind, z. B. Sprachdienste keinen einzelnen Dienst GUID haben. Sie müssen den Namen der Sprache verwenden, um die GUID des Sprachdiensts in der Registrierung zu suchen.  
  
 Verwenden Sie die Dienst-GUIDs, die hier aufgeführten oder von einer anderen Quelle (z. B. Sprachdienste) abgerufen, um die primäre Schnittstelle oder Schnittstellen, der für jeden Dienst zu erhalten.  
  
## <a name="the-services"></a>Die Dienste  
  
|Dienst|Interface|Visual Studio|Visual Studio 2005|Beschreibung|  
|-------------|---------------|-------------------|------------------------|-----------------|  
|<xref:Microsoft.VisualStudio.OLE.Interop.SBindHost>|<xref:Microsoft.VisualStudio.OLE.Interop.IBindHost>|Ja|Ja|Wird von VSPackages verwendet zum Abrufen einer <xref:Microsoft.VisualStudio.OLE.Interop.IBindHost> Schnittstelle aus einem ActiveX-Steuerelement, um asynchrone Datenübertragungen zu ermöglichen.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SDTE>|<xref:EnvDTE.DTE>|Nein|Ja|Ruft die Design-Time-Erweiterbarkeit (DTE)-Objekt, das verwendet wird, für die Automatisierung ab.<br /><br /> C/C++-ID: SID_SDTE|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SCodeNavigate>|<xref:Microsoft.VisualStudio.Shell.Interop.ICodeNavigate>|Ja|Ja|Durch ein Forms-Designer zum Anzeigen des Standardereignishandler für ein Steuerelement implementiert.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.SContainerDispatch>|IDispatch|Ja|Ja|Ermöglicht einem VSPackages, die Automationsschnittstelle von einem anderen VSPackage oder ein Steuerelement zugreifen.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SExtendedTypeLib>|<xref:Microsoft.VisualStudio.Shell.Interop.IExtendedTypeLib>|Ja|Ja|Aktiviert ein VSPackage hinzufügen oder erstellen eine erweiterte Typbibliothek.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SDirList>|<xref:Microsoft.VisualStudio.Shell.Interop.IDirList>|Nein|Ja|Bietet Zugriff auf einen Container für die Liste von Listen mit dem Namen des; z. B. die Liste der Verzeichnisse zu suchen, siehe die **suchen und Ersetzen** im Dialogfeld die **Suchen In** Dropdown-Liste. Die <xref:Microsoft.VisualStudio.Shell.Interop.IDirList> Objekt kann auslesen sowie werden geschrieben.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SIVsPackageDynamicToolOwner>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPackageDynamicToolOwner>|Ja|Ja|Ermöglicht einem VSPackages, haben eine eigene Toolfenster dynamisch angezeigt oder ausgeblendet.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SLicensedClassManager>|<xref:Microsoft.VisualStudio.Shell.Interop.ILicensedClassManager>|Ja|Ja|Ermöglicht einem VSPackages, anzugeben, [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] die Klassen, die es benötigt, indem Sie eine Liste von Lizenzschlüsseln angeben.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SLocalRegistry>|<xref:Microsoft.VisualStudio.Shell.Interop.ILocalRegistry><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.ILocalRegistry2>|Ja|Ja|Aktiviert ein VSPackage, das Zugriff auf die Registrierung relativ zur lokalen [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Registrierungsstruktur.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.SOleComponentManager>|<xref:Microsoft.VisualStudio.OLE.Interop.IOleComponentManager>|Ja|Ja|Stellt die Koordinierung der Komponentendienste wie Nachrichtenschleifen, Tastatur, Schleifen und ereignisbenachrichtigungen bereit.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SOleComponentUIManager>|<xref:Microsoft.VisualStudio.Shell.Interop.IOleComponentUIManager>|Ja|Ja|Aktiviert ein VSPackage, die verschiedene Elemente der Benutzeroberfläche (UI) der Zugriff auf [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], z. B. Hilfe, Statusleiste und UI-Ereignisse.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SOleInPlaceComponent>|<xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponent>|Ja|Ja|Aktiviert ein VSPackage, integrieren ihre Benutzeroberfläche mit der Benutzeroberfläche der [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SOleInPlaceComponentSite>|<xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponentSite>|Ja|Ja|Aktiviert ein VSPackage, um Änderungen an der Benutzeroberfläche zu steuern, die spezifisch für die Tools sind.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.SOleUndoManager>|<xref:Microsoft.VisualStudio.OLE.Interop.IOleUndoManager>|Ja|Ja|Aktiviert ein VSPackage eines Containers rückgängig-Manager entweder teilnehmen Rückgängig-Stapel des Containers oder des Containers Rückgängig-Stapel den Zugriff auf den Zugriff auf.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SProfferService>|<xref:Microsoft.VisualStudio.Shell.Interop.IProfferService>|Ja|Ja|Aktiviert ein VSPackage, eigene Dienste anzubieten.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SProfferTypeLib>|<xref:Microsoft.VisualStudio.Shell.Interop.IProfferTypeLib>|Ja|Ja|Ermöglicht einen Forms-Designer, um eine Typbibliothek als Referenz verfügbar zu machen.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.STrackSelection>|<xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection>|Ja|Ja|Bietet Zugriff auf die Auswahl in einem Auswahlcontainer. Wird von einem Forms-Designer verwendet.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SUIHostCommandDispatcher>|<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>|Ja|Ja|Aktiviert ein VSPackage das Befehl-handlerkette teilnehmen und Befehle im Auftrag von der integrierten Entwicklungsumgebung (IDE) oder selbst verarbeiten.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SUIHostLocale>|<xref:Microsoft.VisualStudio.Shell.Interop.IUIHostLocale>|Ja|Ja|Bietet Zugriff auf die Benutzeroberfläche Gebietsschemainformationen des Hosts.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsActivityLog>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog>|Nein|Ja|Ermöglicht einem VSPackages, allgemeine Meldungen protokolliert, wenn die Protokollierung aktiviert ist.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsAddProjectItemDlg>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsAddProjectItemDlg>|Ja|Ja|Ermöglicht den Zugriff auf die **Projektelemente hinzufügen** im Dialogfeld VSPackages implementieren ihre eigenen **Element hinzufügen** Option des Menüs.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsAddWebReferenceDlg>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsAddWebReferenceDlg>|Ja|Ja|Zeigt die **Verweis hinzufügen** Dialogfeld.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsAppCommandLine>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsAppCommandLine>|Ja|Ja|Aktiviert ein VSPackage, um festzustellen, ob devenv.exe ein Befehlszeilenschalters zugewiesen wurde.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsCallBrowser>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCallBrowser>|Nein|Ja|Aktiviert ein VSPackage zum Erstellen eines neuen **Aufrufbrowser** beim Debuggen verwendet.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsClassView>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsClassView>|Ja|Ja|Aktiviert ein VSPackage, zu synchronisieren der **Klassenansicht** auf ein bestimmtes Objekt.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsCmdNameMapping>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCmdNameMapping>|Ja|Ja|Bietet Unterstützung für das Zuordnen von Befehlsnamen zu GUIDs und wieder zurück, und Bestimmen der Namen aller verfügbaren Befehle und Namen.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsCodeDefView>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCodeDefView>|Nein|Ja|Aktiviert ein VSPackage, das Bearbeiten der **Codedefinitionsansicht**.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsCodeShareHandler>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCodeShareHandler>|Ja|Ja|Interner Dienst. Nicht verwenden.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.SVsCodeWindow>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow>|Ja|Ja|Bietet Zugriff auf ein Code-Fenster, das ein oder mehrere Dokumente enthalten kann.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.SVsCodeWindowManager>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager>|Ja|Ja|Aktiviert ein VSPackage Änderungen im Code-Fenster, z. B. dropdownleisten hinzu.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsCommandWindow>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCommandWindow><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsCommandWindow2>|Ja|Ja|Aktiviert ein VSPackage zum Ausführen eines Befehls über die **Befehlsfenster** und interagieren Sie andernfalls mit dem **Befehlsfenster**.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsCommandWindowsCollection>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCommandWindowsCollection>|Nein|Ja|Aktiviert ein VSPackage, bearbeiten die Liste der **Befehl** von Windows verwaltet wird [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsComplusLibrary>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsLibraryReferenceManager>|Ja|Ja|Aktiviert ein VSPackage, das Durchsuchen von Informationen zum Bereitstellen der **Objektkatalog**.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsComponentSelectorDlg>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsComponentSelectorDlg>|Nein|Ja|Aktiviert ein VSPackage, unterstützen die **Verweis hinzufügen** auswählen, um einen Benutzer aus, wählen Sie die externe Komponenten, die dem Projekt hinzufügen kann.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsComponentSelectorDlg2>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsComponentSelectorDlg2>|Nein|Ja|Aktiviert ein VSPackage, unterstützen die **Verweis hinzufügen** auswählen, um einen Benutzer aus, wählen Sie die externe Komponenten, die dem Projekt hinzufügen kann. Diese Version des Dialogfelds kann vorab auffüllen, der die Liste der Komponenten, bevor es angezeigt wird.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsConfigurationManagerDlg>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsConfigurationManagerDlg>|Nein|Ja|Zeigt die **Configuration Manager** Dialogfeld.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsCreateAggregateProject>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCreateAggregateProject>|Nein|Ja|Aktiviert ein VSPackage, um ein Projekt zu erstellen, die eine Auflistung von anderen Projekten enthält.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsDebuggableProtocol>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProtocol>|Ja|Ja|Aktiviert ein VSPackage zum Aktualisieren der Liste der debugfähigen Protokolle, die von der IDE verwendet werden, um bestimmte Debug-Engines zu starten.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsDebugLaunch>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsDebugLaunch>|Ja|Ja|Aktiviert ein VSPackage zum Starten des Debuggers zu unterstützen.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsDiscoveryService>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsDiscoveryService>|Ja|Ja|Aktiviert ein VSPackage eine Discovery-Sitzung zu erstellen, die verwendet wird, um Webdienste zu ermitteln.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsEnumHierarchyItemsFactory>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumHierarchyItemsFactory>|Ja|Ja|Stellt eine Factory zum Erstellen <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumHierarchyItemsFactory> Objekte, die zum Aufzählen der angegebenen Hierarchien (Projekte).|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsErrorList>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsErrorList>|Nein|Ja|Stellt zusätzliche Methoden zum Bearbeiten der **Fehlerliste erstellen** Aufgabenfenster. Insbesondere wird die **Fehlerliste erstellen** Aufgabenfenster in den Vordergrund und erzwingt, dass alle Fehler angezeigt werden soll.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsExternalFilesManager>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsExternalFilesManager>|Ja|Ja|Ermöglicht den Zugriff auf die **verschiedene Dateien** Projektknoten aus der aktuellen Projektmappe.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsFileChange>||Ja|Ja|Veraltet. Verwendung `SVsFileChangeEx` stattdessen service.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsFileChangeEx>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsFileChangeEx>|Ja|Ja|Aktiviert ein VSPackage für den Zugriff auf verschiedene Datei-Change-Ereignissen, die von der IDE ausgelöst.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsFilterAddProjectItemDlg>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg>|Ja|Ja|Aktiviert ein VSPackage zum Filtern von Elementen, die in angezeigt werden. die **Element hinzufügen** Dialogfeld.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsFilterKeys>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterKeys>|Ja|Ja|Aktiviert ein VSPackage erweiterte Tastatur gefiltert werden.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsFontAndColorCacheManager>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorCacheManager>|Nein|Ja|Bietet Zugriff auf den Satz von Caches für Schriftarten und Farben in [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] aktualisieren oder Löschen von einem bestimmten Cache "oder" alle Caches.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsFontAndColorStorage>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorUtilities>|Ja|Ja|Aktiviert ein VSPackage, die Bearbeitung der Schriftart- und farbeinstellungen-Einstellungen, die von verwaltet [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]. Dieser Dienst bietet darüber hinaus den Zugriff auf eine Auflistung von Hilfsprogrammmethoden zum Bearbeiten von Schriftart und Farbe.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsGeneralOutputWindowPane>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputWindowPane>|Ja|Ja|Bietet Zugriff auf den allgemeinen **Fenster "Ausgabe"** Bereich nach Bedarf erstellen.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsHelpService>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsHelpSystem>|Ja|Ja|Bietet Zugriff auf das Hilfesystem.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsHTMLConverter>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsHTMLConverter>|Ja|Ja|Ein, die die [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Debugger Handle HTML zum Formatieren der Ausgabe.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsIME>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsIME>|Ja|Ja|Ermöglicht den Zugriff auf die Eingabe-Editor (IME)-API von in einem VSPackage.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsIntegratedHelp>|<xref:Microsoft.VisualStudio.VSHelp.SVsHelp>|Ja|Ja|Ermöglicht den Zugriff auf die [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Hilfesystem für Schlüsselwort oder URL, die über eine Hilfedatei sowie Navigationssteuerelement auf zugreifen. Dieser Dienst ist nur verfügbar, wenn Hilfe integriert ist die [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] IDE und nicht als externes Programm ausgeführt wird.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsIntelliMouseHandler>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsIntelliMouseHandler>|Ja|Ja|Ermöglicht einem VSPackages, erhalten Sie Zugriff auf die IntelliMouse-Funktionalität, z. B. das Mausrad verwenden, und Behandeln von Bitmaps scrollen und Schwenken, wenn das Mausrad geklickt wird.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsIntellisenseEngine>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsIntellisenseEngine>|Nein|Ja|Ermöglicht einem projekthierarchienknoten, zum Laden oder Entfernen von Dateien als Teil der Unterstützung für IntelliSense-Vorgänge. Der Prozess laden und Entladen von löst Ereignisse, die beeinflussen können, was in IntelliSense-QuickInfo für das Projekt angezeigt wird.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsIntellisenseProjectHost>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsIntellisenseProjectHost>|Nein|Ja|Ermöglicht einem projekthierarchienknoten, Informationen über geschachtelte IntelliSense-Projekte liefern (implementiert die <xref:Microsoft.VisualStudio.Shell.Interop.IVsIntellisenseProject> Schnittstelle) in einer IntelliSense-QuickInfo angezeigt werden können.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsIntellisenseProjectManager>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsIntellisenseProjectManager>|Nein|Ja|Ermöglicht einem projekthierarchienknoten, beraten Listener über Ereignisse, wie Änderungen in Verweise oder Konfiguration, die auswirken kann, was in IntelliSense-QuickInfo angezeigt wird. Soll mit enthaltenen Sprachen verwendet werden.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsInvisibleEditorManager>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsInvisibleEditorManager>|Ja|Ja|Ermöglicht einem VSPackages, registrieren Sie einen "unsichtbaren" Editor, d. h. einen Editor, der bietet vollständige Bearbeitungsfunktionen ist jedoch nicht für Benutzer sichtbar.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.SVsLanguageFilter>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewFilter>|Ja|Ja|Aktiviert ein VSPackage für die Textansicht, z. B. Datentipps und der Umfang der Wörter zusätzliche Informationen bereitzustellen.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsLaunchPad>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsLaunchPad>|Ja|Ja|Aktiviert ein VSPackage zum Ausführen von temporären Batchskripts, um ein Befehlszeilenprogramm auszuführen, deren Ausgabe in einem Ausgabebereich gesendet wird, und klicken Sie zum Analysieren von standard Warn- und Fehlermeldungen, die an ein Fenster gesendet werden.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsLaunchPadFactory>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsLaunchPadFactory>|Ja|Ja|Stellt eine Factory zum Erstellen von <xref:Microsoft.VisualStudio.Shell.Interop.IVsLaunchPad> Objekte.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.SVsLinkedUndoTransactionManager>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLinkedUndoTransactionManager>|Ja|Ja|Bietet Zugriff auf die verknüpfte rückgängig-Manager.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsMenuEditor>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsMenuEditorFactory>|Ja|Ja|Ermöglicht einen Forms-Designer auf den freigegebenen Menü-Editor zuzugreifen. IVsMenuEditorFactory abgefragt werden kann, für die <xref:Microsoft.VisualStudio.Shell.Interop.IVsMenuEditor>.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsMonitorUserContext>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorUserContext>|Ja|Ja|Ermöglicht einem VSPackages, erstellen eine "Kontextsammlung", die verwendet wird, um Hilfeschlüsselwörter für einen bestimmten Kontext zuzuordnen.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsObjBrowser>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsObjBrowser>|Ja|Ja|Aktiviert ein VSPackage, navigieren Sie zu einem bestimmten Objekt in der **Objektkatalog**.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsObjectManager>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager>|Ja|Ja|Aktiviert ein VSPackage, registrieren Sie den Hilfebibliotheks-Manager mit [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] zum Verwalten von Objekten wie z. B. Namespaces, Klassen und Enumerationen.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsObjectSearch>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectSearch>|Ja|Ja|Aktiviert ein VSPackage, um für ein bestimmtes Objekt zu suchen.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsOpenProjectOrSolutionDlg>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsOpenProjectOrSolutionDlg>|Nein|Ja|Aktiviert ein VSPackage die Standardklasse [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Dialogfeld Projekt oder Projektmappe geöffnet.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsOutputWindow>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputWindow>|Ja|Ja|Aktiviert ein VSPackage, um zusätzliche Ausgabebereiche im Ausgabefenster Allgemein zu erstellen.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsParseCommandLine>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsParseCommandLine>|Ja|Ja|Ermöglicht eine Implementierung der <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> Schnittstelle Befehlszeilen zu analysieren.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsPathVariableResolver>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPathVariableResolver>|Nein|Ja|Bietet eine Möglichkeit zum Auflösen von Variablen, die spezifisch für [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] und eingebettet in Pfade zu einem endgültigen Verzeichnis zu erstellen.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsPreviewChangesService>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPreviewChangesService>|Nein|Ja|Zeigt die **Vorschau der Änderungen** Dialogfeld, das im Umgestaltungscode verwendet wird.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsProfileDataManager>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProfileDataManager>|Nein|Ja|Bietet Zugriff auf den Profil-Manager von [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] importieren und Exportieren von für Einstellungsdaten als auch eine grafische Benutzeroberfläche des aktuellen Benutzers profileinstellungen anzeigen können.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsProfilesManagerUI>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProfilesManagerUI>|Nein|Ja|Zeigt ein Dialogfeld mit Einstellungen des aktuellen Benutzers.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsPropertyPageFrame>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPropertyPageFrame>|Ja|Ja|Aktiviert ein VSPackage, überschreiben Sie die Eigenschaftenseite anfänglich angezeigt wird, in der **Eigenschaften** Fenster.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsQueryEditQuerySave>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>|Nein|Ja|Von VSPackages verwendet, um ein Quellcode-Verwaltungsanbieter darüber zu informieren, die eine Datei im Arbeitsspeicher geändert oder gespeichert werden.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsRegisterDebugTargetProvider>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterProjectDebugTargetProvider>|Nein|Ja|Aktiviert ein VSPackage-Projekt, um das Ziel, das in einem Debugger starten programmgesteuert zu überschreiben.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsRegisterEditors>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterEditors>|Ja|Ja|Aktiviert ein VSPackage eine Editorfactory bei der IDE zu registrieren.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.SVsRegisterFindScope>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsRegisterFindScope>|Nein|Ja|Aktiviert ein VSPackage, registrieren einen Suchbereich für den **in Dateien suchen** Dialogfeld.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsRegisterPriorityCommandTarget>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterPriorityCommandTarget>|Ja|Ja|Aktiviert ein VSPackage, um sich selbst als ein Befehlshandler von hoher Priorität, registrieren, dadurch kann das VSPackage, um alle Befehle finden Sie unter. Verwenden Sie sparsam und nur dann, wenn überhaupt.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsRegisterProjectTypes>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterProjectTypes>|Ja|Ja|Aktiviert ein VSPackage mit der IDE Projekttypen zu registrieren.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsResourceManager>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsResourceManager>|Nein|Ja|Aktiviert ein VSPackage beim Laden von verwalteter und nicht verwalteter Ressourcen aus Satelliten-DLLs.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsResourceView>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsResourceView>|Ja|Ja|Verwendung <xref:Microsoft.VisualStudio.Shell.Interop.SVsClassView> stattdessen service.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsRunningDocumentTable>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable>|Ja|Ja|Bietet Zugriff auf die IDE Ausführung Dokumenttabelle (RDT), die alle derzeit nachverfolgt Dokumente geöffnet.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSccManager>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>|Nein|Ja|Ermöglicht VSPackages, registrieren sich mit einem Quellcode-Verwaltungsanbieter in Datenquellen-Steuerelement beteiligt werden können.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSccToolsOptions>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccToolsOptions>|Ja|Ja|Aktiviert ein VSPackage abrufen und Festlegen der quellcodeverwaltung Anbieteroptionen.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSettingsReader>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsReader>|Nein|Ja|Bietet Lesezugriff auf den profileinstellungen des Benutzers an.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsShell>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsShell>|Ja|Ja|Aktiviert ein VSPackage direkt interagieren, und Bearbeiten von anderen VSPackages.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsShellDebugger>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsDebugger>|Ja|Ja|Ermöglicht den Zugriff auf die [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Debugger.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection>|Ja|Ja|Aktiviert ein VSPackage zugreifen auf die aktuelle Auswahl und Verwalten von Benutzeroberflächen-Kontexten zu Befehl.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVSMDCodeDomProvider>|IVSMDCodeDomProvider|Nein|Ja|Bietet Zugriff auf ein Dokument Objekt Dokumentobjektmodell (DOM) Codeanbieter die in nativem Code verwendet werden kann.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVSMDDesignerService>|Schnittstellen IVSMDCodeDomCreator<br /><br /> IVSMDDesignerService|Nein|Ja|Ermöglicht den Zugriff auf die IDE Unterstützung für verwaltete Formular-Designer. Die `IVSMDCodeDomCreator` kann zum Erstellen von Code-DOM-Anbieter verwendet werden.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVSMDPropertyBrowser>|IVSMDPropertyBrowser|Nein|Ja|Bietet Zugriff auf den Designer Eigenschaft Windows-Dienst.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVSMDTypeResolutionService>|<xref:Microsoft.VisualStudio.Shell.Interop.IVSMDTypeResolutionService>|Nein|Ja|Ermöglicht den Zugriff auf eine Schnittstelle, die zurückgegeben werden kann eine <xref:System.ComponentModel.Design.ITypeResolutionService> Objekt in systemeigenem Code verwendbar.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSmartOpenScope>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSmartOpenScope>|Nein|Ja|Bietet eine Möglichkeit, um einen Bereich für eine Assembly, die Berücksichtigung Sperren nach Bedarf zu öffnen.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution>|Ja|Ja|Ermöglicht der obersten Ebene Zugriff auf die aktuelle Projektmappe.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSolutionBuildManager>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionBuildManager>|Ja|Ja|Aktiviert ein VSPackage für die Interaktion mit einer Lösung Buildprozess.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSolutionObject>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution>|Ja|Ja|Verwenden der <xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution> stattdessen service.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSolutionPersistence>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence>|Ja|Ja|Aktiviert ein VSPackage zum Speichern und Abrufen von Informationen aus der aktuellen Projektmappe sln-Datei.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSQLCLRReferences>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSQLCLRReferences>|Nein|Ja|Ermöglicht das Hinzufügen und Aktualisieren von Verweisen in Assemblys mit verwaltetem Code.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsStartPageDownload>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsStartPageDownload>|Nein|Ja|Bietet Zugriff auf die Startseite-Downloaddienst für starten und beenden die Download-Diensts in einem Hintergrundthread.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsStatusbar>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar>|Ja|Ja|Bietet Zugriff auf die IDE Statusleiste angezeigt.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsStrongNameKeys>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsStrongNameKeys>|Nein|Ja|Bietet Zugriff auf Methoden zum Erstellen von starken Schlüsselnamen und Schlüsseldateien mit Kennwörtern, die bei der Signierung von Assemblys mit verwaltetem Code verwendet werden.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsStructuredFileIO>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsStructuredFileIO>|Ja|Ja|Ermöglicht einem VSPackages, die zum Speichern von Daten in verschiedenen Formaten zu unterstützen.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsTaskList>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskList>|Ja|Ja|Ermöglicht den Zugriff der IDE-Fenster "Aufgabenliste".|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.SVsTextImageUtilities>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextImageUtilities>|Nein|Ja|Stellt Hilfsprogramme zum Laden und Speichern von Textdateien bereit.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.SVsTextManager>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManager><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager>|Ja|Ja|Bietet Zugriff auf alle Textpuffer sowie Sitzungen des ausgeblendeten Textes (für ausgeblendete Bereiche), die in der IDE verfügbar sind.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsTextOut>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTextOut>|Ja|Ja|Stellt eine Version von Win32 `TextOut` -Funktion für das Schreiben von Text für einen Gerätekontext (erfordert ein Handle DC).|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.SVsTextSpanSet>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextSpanSet>|Ja|Ja|Bietet Zugriff auf eine Liste von Textspannen in einem TEXTIMAGE oder Puffer. Dieser Dienst wird auf einen Container mit Dokumenten in der Regel implementiert und bezieht sich auf das aktuelle Dokument.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsThreadedWaitDialog>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsThreadedWaitDialog>|Nein|Ja|Aktiviert ein VSPackage, um ein Dialogfeld anzuzeigen, die auf einem anderen Thread (mit dem Warten auf Aufgaben im Hintergrund) wartet.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsThreadPool>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsThreadPool>|Nein|Ja|Aktiviert ein VSPackage, das Initiieren von Hintergrundaufgaben, die dann von verwaltet werden [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsToolbox>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox>|Ja|Ja|Bietet Zugriff auf der IDE **Toolbox**.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsToolboxActiveXDataProvider>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxDataProvider>|Ja|Ja|Aktiviert ein VSPackage zum Abrufen von Informationen aus **Toolbox** Elemente.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsToolboxDataProviderRegistry>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxDataProviderRegistry>|Nein|Ja|Aktiviert ein VSPackage, das einen toolboxdatenanbieter registrieren, ohne dass die Leistungseinbußen durch den gesamten Vorabladen **Toolbox**.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsToolsOptions>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsToolsOptions>|Nein|Ja|Aktiviert ein VSPackage, zu bestimmen, ob die **Optionen** -Dialogfeld geöffnet ist und die Sichtbarkeit der Seite "Optionen" Alle aktualisieren.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackProjectDocuments>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments3>|Nein|Ja|Aktiviert ein VSPackage, um Änderungen in der Projektdateien zu überwachen und Batch Kontrolle über ein Quellcodeverwaltungsanbieter.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackSelectionEx>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx>|Ja|Ja|Aktiviert ein VSPackage, um die IDE Änderungen an einer Auswahl zu informieren, die die aktuell ausgewählte Element betreffen können.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsUIHierWinClipboardHelper>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierWinClipboardHelper>|Ja|Ja|Verwendung der Zwischenablage mit anderen Hierarchien koordinieren können eine Hierarchie (z. B. ein VSPackage-Projekt).|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell>|Ja|Ja|Bietet Zugriff auf die IDE Benutzeroberflächenelemente wie z. B. Toolfenster und Dokumentfenster.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShellDocumentWindowMgr>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellDocumentWindowMgr>|Ja|Ja|Aktiviert ein VSPackage, um die Positionen aller Fenster, die auf Basis der Inhalte eines Datenstroms von Daten wiederherstellen oder die Position aller Fenster in einen Stream zu speichern. Selten verwendet.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShellOpenDocument>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument>|Ja|Ja|Aktiviert ein VSPackage, die Dokumente auf vielerlei Weise öffnen und um zu bestimmen, wer welche Dokument besitzt.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsUpgradeLogger>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsUpgradeLogger>|Nein|Ja|Ein, die Implementierungen der <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory> Schnittstelle, um Fehler und informationsmeldungen.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsWebBrowsingService>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWebBrowsingService>|Ja|Ja|Aktiviert ein VSPackage erstellen und eine Webbrowsersitzung zu steuern.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsWebFavorites>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWebFavorites>|Ja|Ja|Aktiviert ein VSPackage, das Hinzufügen des Benutzers **Favoriten** Liste.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsWebPreview>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWebPreview>|Ja|Ja|Aktiviert ein VSPackage für die Vorschau einer Webseite, in der Regel in einem untergeordneten Fenster.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsWebURLMRU>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWebURLMRU>|Ja|Ja|Aktiviert ein VSPackage, die zuletzt verwendeten (MRU)-Liste der URLs eine URL hinzuzufügen und zum Abrufen einer Liste aller URLs in der MRU-Liste.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsWindowFrame>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame>|Ja|Ja|Aktiviert ein VSPackage, um den Fensterrahmen zu erhalten, in dem das Paket oder einen Teil des Pakets belegen kann.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsXMLMemberIndexService>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsXMLMemberIndexService>|Ja|Ja|Bietet Zugriff auf XML-formatierte Dokumentationsdateien, die einer bestimmten Metadaten-Datei zugeordnet.|  
  
## <a name="see-also"></a>Siehe auch  
 [Com- und verwalteten Diensten](http://msdn.microsoft.com/en-us/6c5808b4-ad87-48d7-ae06-33a81e7052af)   
 [Verwenden und Bereitstellen von Diensten](../../extensibility/using-and-providing-services.md)
