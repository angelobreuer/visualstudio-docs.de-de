---
title: 'Vorgehensweise: Verwenden reservierter XML-Zeichen in Projektdateien | Microsoft-Dokumentation'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, using reserved XML characters
- MSBuild, reserved XML characters
ms.assetid: 1ae37275-96bf-4e6e-897b-6b048e5bbe93
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a041802af1c2fe8cfa195990e6eda3e9b49d773a
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "77633771"
---
# <a name="how-to-use-reserved-xml-characters-in-project-files"></a>Vorgehensweise: Verwenden reservierter XML-Zeichen in Projektdateien

Wenn Sie Projektdateien erstellen, müssen Sie reservierte XML-Zeichen verwenden, z.B. in Eigenschaftswerten oder Aufgabenparameterwerten. Einige reservierte Zeichen müssen jedoch durch eine benannte Entität ersetzt werden, sodass die Projektdatei analysiert werden kann.

## <a name="use-reserved-characters"></a>Verwenden reservierter Zeichen

 Die folgende Tabelle beschreibt die reservierten XML-Zeichen, die durch die entsprechende benannte Entität ersetzt werden müssen, damit die Projektdatei analysiert werden kann.

|Reserviertes Zeichen|Benannte Entität|
|------------------------|------------------|
|\<|&amp;lt;|
|>|&amp;gt;|
|&|&amp;amp;|
|"|&amp;quot;|
|'|&amp;apos;|

#### <a name="to-use-double-quotes-in-a-project-file"></a>Doppelte Anführungszeichen in einer Projektdatei verwenden

- Ersetzen Sie die doppelten Anführungszeichen durch die entsprechende benannte Entität &amp;quot;. Um beispielsweise doppelte Anführungszeichen um die `EXEFile`-Elementliste zu setzen, geben Sie Folgendes ein:

    ```xml
    <Message Text="The output file is &quot;@(EXEFile)&quot;."/>
    ```

## <a name="example"></a>Beispiel

 Im folgenden Codebeispiel werden doppelte Anführungszeichen zum Markieren des Dateinamens in der Meldung benutzt, die von der Projektdatei ausgegeben wird.

```xml
<Project DefaultTargets="Compile"
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003" >
    <!-- Set the application name as a property -->
    <PropertyGroup>
        <appname>"HelloWorldCS"</appname>
    </PropertyGroup>
    <!-- Specify the inputs -->
    <ItemGroup>
        <CSFile Include = "consolehwcs1.cs" />
    </ItemGroup>
    <Target Name = "Compile">
        <!-- Run the Visual C# compilation using input
        files of type CSFile -->
        <Csc Sources = "@(CSFile)">
            <!-- Set the OutputAssembly attribute of the CSC task
            to the name of the executable file that is created -->
            <Output
                TaskParameter = "OutputAssembly"
                ItemName = "EXEFile"/>
        </Csc>
        <!-- Log the file name of the output file -->
        <Message Text="The output file is &quot;@(EXEFile)&quot;."/>
    </Target>
</Project>
```

## <a name="see-also"></a>Weitere Informationen

- [MSBuild-Referenz](../msbuild/msbuild-reference.md)
- [MSBuild](../msbuild/msbuild.md)
