---
title: Tarefa GenerateResource | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#GenerateResource
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, GenerateResource task
- GenerateResource task [MSBuild]
ms.assetid: c0aff32f-f2cc-46f6-9c3e-a5c9f8f912b1
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9b47c3315236dc228d3c561c4a3e0f333f5c9600
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56615904"
---
# <a name="generateresource-task"></a>Tarefa GenerateResource
Converte entre arquivos *.txt* e *.resx* (formato de recurso baseado em XML) e arquivos *.resources* binários do Common Language Runtime que podem ser inseridos em um executável binário do tempo de execução ou compilados em assemblies satélite. Essa tarefa geralmente é usada para converter arquivos *.txt* ou *.resx* em arquivos *.resources*. A tarefa `GenerateResource` é funcionalmente semelhante a [resgen.exe](/dotnet/framework/tools/resgen-exe-resource-file-generator).

## <a name="parameters"></a>Parâmetros
A tabela a seguir descreve os parâmetros da tarefa `GenerateResource`.

|Parâmetro|Descrição|
|---------------|-----------------|
|`AdditionalInputs`|Parâmetro opcional <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Contém entradas adicionais para a verificação de dependência realizada por tarefa. Por exemplo, os arquivos de projeto e de destino normalmente devem ser entradas, de modo que se eles forem atualizados, todos os recursos serão regenerados.|
|`EnvironmentVariables`|Parâmetro `String[]` opcional.<br /><br /> Especifica uma matriz de pares nome-valor das variáveis de ambiente que devem ser passados para o *resgen.exe* gerado, além (ou substituindo seletivamente) do bloco de ambiente comum.|
|`ExcludedInputPaths`|Parâmetro opcional <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Especifica uma matriz de itens que especificam os caminhos dos quais entradas controladas serão ignoradas durante a verificação de atualização.|
|`ExecuteAsTool`|Parâmetro `Boolean` opcional.<br /><br /> Se `true`, executa *tlbimp.exe* e *aximp.exe* da estrutura de destino apropriada fora de processo para gerar os assemblies de wrapper necessários. Esse parâmetro habilita multi-targeting de `ResolveComReferences`.|
|`FilesWritten`|Parâmetro de saída <xref:Microsoft.Build.Framework.ITaskItem>`[]` opcional.<br /><br /> Contém os nomes de todos os arquivos gravados em disco. Isso inclui o arquivo de cache, se houver. Esse parâmetro é útil para implementações do Clean.|
|`MinimalRebuildFromTracking`|Parâmetro `Boolean` opcional.<br /><br /> Obtém ou define uma opção que especifica se o build incremental controlado será usado. Se `true`, o build incremental é ativado; caso contrário, será forçada uma recompilação.|
|`NeverLockTypeAssemblies`|Parâmetro `Boolean` opcional.<br /><br /> Obtém ou define um valor booliano que especifica se é preciso criar um novo [AppDomain](/dotnet/api/system.appdomain) para avaliar os arquivos (verdadeiro) de recursos (*.resx*) ou criar um novo [AppDomain](/dotnet/api/system.appdomain) somente quando os arquivos de recursos fizerem referência ao assembly do usuário (falso).|
|`OutputResources`|Parâmetro de saída <xref:Microsoft.Build.Framework.ITaskItem>`[]` opcional.<br /><br /> Especifica o nome dos arquivos gerados, como arquivos *.resources*. Se você não especificar um nome, o nome do arquivo de entrada correspondente será usado e o arquivo *.resources* criado será colocado no diretório que contém o arquivo de entrada.|
|`PublicClass`|Parâmetro `Boolean` opcional.<br /><br /> Se `true`, cria uma classe de recurso fortemente tipada como uma classe pública.|
|`References`|Parâmetro `String[]` opcional.<br /><br /> Referências das quais carregar tipos em arquivos *.resx*. Elementos de dados de arquivo *.resx* podem ter um tipo .NET. Quando o arquivo *.resx* é lido, isso precisa ser resolvido. Normalmente, ele é resolvido com êxito usando o tipo padrão ao carregar regras. Se você fornecer assemblies em `References`, eles terão prioridade.<br /><br /> Esse parâmetro não é necessário para recursos fortemente tipados.|
|`SdkToolsPath`|Parâmetro `String` opcional.<br /><br /> Especifica o caminho para o SDK Tools, como *resgen.exe*.|
|`Sources`|Parâmetro <xref:Microsoft.Build.Framework.ITaskItem>`[]` obrigatório.<br /><br /> Especifica os itens a converter. Itens passados para esse parâmetro devem ter uma das seguintes extensões de arquivo:<br /><br /> -   *.txt*: Especifica a extensão de um arquivo de texto a converter. Os arquivos de texto só podem conter recursos de cadeia de caracteres.<br />-   *.resx*: Especifica a extensão de um arquivo de recurso com base em XML a converter.<br />-   *.restext*: Especifica o mesmo formato como *.txt*. Essa extensão diferente é útil se você quiser distinguir claramente os arquivos de origem que contêm recursos de outros arquivos de origem no processo de build.<br />-   *.resources*: Especifica a extensão de um arquivo de recurso a converter.|
|`StateFile`|Parâmetro <xref:Microsoft.Build.Framework.ITaskItem> opcional.<br /><br /> Especifica o caminho para um arquivo de cache opcional usado para acelerar a verificação de dependência de links em arquivos de entrada *.resx*.|
|`StronglyTypedClassName`|Parâmetro `String` opcional.<br /><br /> Especifica o nome de classe para a classe de recurso fortemente tipada. Se esse parâmetro não for especificado, o nome base do arquivo de recurso será usado.|
|`StronglyTypedFilename`|Parâmetro <xref:Microsoft.Build.Framework.ITaskItem> opcional.<br /><br /> Especifica o nome do arquivo para o arquivo de origem. Se esse parâmetro não for especificado, o nome de classe será usado como o nome de arquivo base, com a extensão dependendo da linguagem. Por exemplo: *MyClass.cs*.|
|`StronglyTypedLanguage`|Parâmetro `String` opcional.<br /><br /> Especifica a linguagem a ser usada ao gerar a fonte de classe para o recurso fortemente tipado. Esse parâmetro deve corresponder exatamente uma das linguagens usadas por CodeDomProvider. Por exemplo `VB` ou `C#`.<br /><br /> Ao passar um valor para esse parâmetro, você instrui a tarefa a gerar recursos fortemente tipados.|
|`StronglyTypedManifestPrefix`|Parâmetro `String` opcional.<br /><br /> Especifica o prefixo de manifesto ou namespace de recurso para usar na origem de classe gerada para o recurso fortemente tipado.|
|`StronglyTypedNamespace`|Parâmetro `String` opcional.<br /><br /> Especifica o namespace para usar na origem de classe gerada para o recurso fortemente tipado. Se esse parâmetro não for especificado, todos os recursos fortemente tipados estarão no namespace global.|
|`TLogReadFiles`|Parâmetro <xref:Microsoft.Build.Framework.ITaskItem>`[]` somente leitura opcional.<br /><br /> Obtém uma matriz de itens que representam os logs de acompanhamento de leitura.|
|`TLogWriteFiles`|Parâmetro <xref:Microsoft.Build.Framework.ITaskItem>`[]` somente leitura opcional.<br /><br /> Obtém uma matriz de itens que representam os logs de acompanhamento de gravação.|
|`ToolArchitecture`|Parâmetro <xref:System.String?displayProperty=fullName> opcional.<br /><br /> Usado para determinar se o *Tracker.exe* precisa ou não ser usado para gerar *ResGen.exe*.<br /><br /> Deve ser analisável para um membro da enumeração <xref:Microsoft.Build.Utilities.ExecutableType>. Se `String.Empty`, usa uma heurística para determinar uma arquitetura padrão. Deve ser analisável para um membro da enumeração Microsoft.Build.Utilities.ExecutableType.|
|`TrackerFrameworkPath`|Parâmetro `String` opcional.<br /><br /> Especifica o caminho para o local apropriado do .NET Framework que contém *FileTracker.dll*.<br /><br /> Se ele for definido, o usuário assumirá a responsabilidade por garantir que o número de bit de *FileTracker.dll* passado corresponda ao número de bit de *ResGen.exe* que ele pretende usar. Se não for definido, a tarefa decide o local apropriado com base na versão atual do .NET Framework.|
|`TrackerLogDirectory`|Parâmetro `String` opcional.<br /><br /> Especifica o diretório intermediário no qual os logs de acompanhamento da execução dessa tarefa serão colocados.|
|`TrackerSdkPath`|Parâmetro `String` opcional.<br /><br /> Especifica o caminho para o local apropriado do SDK do Windows que contém *Tracker.exe*.<br /><br /> Se ele for definido, o usuário assumirá a responsabilidade por garantir que o número de bit de *Tracker.exe* passado corresponda ao número de bit de *ResGen.exe* que ele pretende usar. Se não for definido, a tarefa decide o local apropriado com base no SDK do Windows atual.|
|`TrackFileAccess`|Parâmetro <xref:System.Boolean> opcional.<br /><br /> Se é true, o diretório do arquivo de entrada é usado para resolver caminhos de arquivo relativos.|
|`UseSourcePath`|Parâmetro `Boolean` opcional.<br /><br /> Se é `true`, especifica que o diretório do arquivo de entrada deve ser usado para resolver caminhos de arquivo relativos.|

## <a name="remarks"></a>Comentários
Já que arquivos *.resx* podem conter links para outros arquivos de recurso, não é suficiente apenas comparar carimbos de data/hora de arquivos *.resx* e *.resources* para ver se as saídas estão atualizadas. Em vez disso, a tarefa `GenerateResource` segue os links nos arquivos *.resx* e verifica também os carimbos de data/hora dos arquivos vinculados. Isso significa que, geralmente, você não deve usar os atributos `Inputs` e `Outputs` no destino que contém a tarefa `GenerateResource`, pois isso pode fazer com que ela seja ignorada quando, na verdade, ela deve ser executada.

Além dos parâmetros listados acima, essa tarefa herda parâmetros da classe <xref:Microsoft.Build.Tasks.TaskExtension>, que herda da classe <xref:Microsoft.Build.Utilities.Task>. Para obter uma lista desses parâmetros adicionais e suas descrições, confira [Classe base TaskExtension](../msbuild/taskextension-base-class.md).

Ao usar o MSBuild 4.0 para projetos de destino do .NET 3.5, o build pode falhar em recursos x86. Para contornar esse problema, é possível criar o destino como um assembly AnyCPU.

## <a name="example"></a>Exemplo
O exemplo a seguir usa a tarefa `GenerateResource` para gerar arquivos *.resources* com base nos arquivos especificados pela coleção de itens `Resx`.

```xml
<GenerateResource
    Sources="@(Resx)"
    OutputResources="@(Resx->'$(IntermediateOutputPath)%(Identity).resources')">
    <Output
        TaskParameter="OutputResources"
        ItemName="Resources"/>
</GenerateResource>
```

A tarefa `GenerateResource` usa os metadados \<LogicalName> de um item \<EmbeddedResource> para nomear os recursos que são inseridos em um assembly.

Supondo que o assembly seja nomeado myAssembly, o seguinte código gera um recurso inserido chamado *someQualifier.someResource.resources*:

```xml
<ItemGroup>
    <EmbeddedResource Include="myResource.resx">
        <LogicalName>someQualifier.someResource.resources</LogicalName>
    </EmbeddedResource>
</ItemGroup>
```

Sem os metadados de \<LogicalName>, o recurso é nomeado *myAssembly.myResource.resources*.  Este exemplo aplica-se somente ao processo de build do Visual Basic e Visual C#.

## <a name="see-also"></a>Consulte também
- [Tarefas](../msbuild/msbuild-tasks.md)
- [Referência de tarefas](../msbuild/msbuild-task-reference.md)
