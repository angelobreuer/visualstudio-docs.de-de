---
title: Referenz für die WPF-MSBuild-Task |Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- WPF MSBuild task reference [WPF MSBuild], term/definition table
- build tasks [WPF MSBuild], Microsoft build engine
- build tasks using the Microsoft build engine [WPF MSBuild], compile markup and process resources
- WPF MSBuild task reference [WPF MSBuild]
ms.assetid: 96df0370-e50f-4ffc-9771-b12fb8721143
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 70d994e32b717ff566a2e38acee732c7525d1bb0
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "77630846"
---
# <a name="wpf-msbuild-task-reference"></a>Referenz zu MSBuild-Tasks für WPF

Der Buildprozess von WPF erweitert die Microsoft-Build-Engine (MSBuild) durch einen zusätzlichen Satz an Buildtasks, einschließlich Tasks zum Kompilieren von Markup- und Prozessressourcen.

## <a name="in-this-section"></a>In diesem Abschnitt

- [FileClassifier](../msbuild/fileclassifier-task.md)

 Klassifiziert eine Gruppe von Quellressourcen als diejenigen, die in eine Assembly eingebettet werden. Wenn eine Ressource nicht lokalisierbar ist, wird sie in die Hauptanwendungsassembly eingebettet; andernfalls wird sie in eine Satellitenassembly eingebettet.

- [GenerateTemporaryTargetAssembly](../msbuild/generatetemporarytargetassembly-task.md)

 Generiert eine Assembly, wenn mindestens eine XAML-Seite in einem Projekt auf einen Typ verweist, der lokal in diesem Projekt deklariert ist. Die generierte Assembly wird entfernt, nachdem der Build abgeschlossen ist, oder wenn beim Buildprozess ein Fehler auftritt.

- [GetWinFXPath](../msbuild/getwinfxpath-task.md)

 Gibt das Verzeichnis der aktuellen .NET Framework-Runtime zurück.

- [MarkupCompilePass1](../msbuild/markupcompilepass1-task.md)

 Konvertiert nicht lokalisierbare XAML-Projektdateien in das kompilierte Binärformat.

- [MarkupCompilePass2](../msbuild/markupcompilepass2-task.md)

 Führt den zweiten Markupkompilierungsschritt für XAML-Dateien aus, die auf Typen im selben Projekt verweisen.

- [MergeLocalizationDirectives](../msbuild/mergelocalizationdirectives-task.md)

 Führt die Lokalisierungsattribute und -kommentare aus einer oder mehreren XAML-Binärformatdateien für die gesamte Assembly in einer einzelnen Datei zusammen.

- [ResourcesGenerator](../msbuild/resourcesgenerator-task.md)

 Bettet mindestens eine Ressource (*JPG*, *ICO*, *BMP*, XAML im Binärformat und andere Erweiterungstypen) in eine *RESOURCES*-Datei ein.

- [UidManager](../msbuild/uidmanager-task.md)

 Überprüft, aktualisiert oder entfernt eindeutige Bezeichner (UIDs), um alle XAML-Elemente zu lokalisieren, die in den XAML-Quelldateien enthalten sind.

- [UpdateManifestForBrowserApplication](../msbuild/updatemanifestforbrowserapplication-task.md)

 Fügt dem Anwendungsmanifest ( *\<Projektname>.exe.manifest*)  das Element **\<hostInBrowser />** hinzu, wenn ein XAML-Browseranwendungsprojekt (XBAP) erstellt wird.

## <a name="see-also"></a>Siehe auch

- [MSBuild](../msbuild/msbuild.md)