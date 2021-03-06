---
title: 'Como: Criar um manifesto de produto | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- product files [ClickOnce]
- product files [Windows Installer]
- prerequisites, custom bootstrapper package
- dependencies, custom bootstrapper package
ms.assetid: 2d316aaa-8bc0-4ce5-90ab-23b3eac0b5dd
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 68f3006104b50876f6d2716ff4eb1efe0a705284
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60057401"
---
# <a name="how-to-create-a-product-manifest"></a>Como: Criar um manifesto do produto
Para implantar o pré-requisitos para o seu aplicativo, você pode criar um pacote de bootstrapper. Um pacote de bootstrapper contém um arquivo de manifesto de produto único, mas um manifesto de pacote para cada localidade. O manifesto de pacote contém aspectos específicos de localização do seu pacote. Isso inclui cadeias de caracteres, os contratos de licença de usuário final e os pacotes de idiomas.

 Para obter mais informações sobre manifestos de pacote, consulte [como: Criar um manifesto do pacote](../deployment/how-to-create-a-package-manifest.md).

## <a name="create-the-product-manifest"></a>Crie o manifesto de produto

#### <a name="to-create-the-product-manifest"></a>Para criar o manifesto do produto

1. Crie um diretório para o pacote de bootstrapper. Este exemplo usa C:\package.

2. No Visual Studio, crie um novo arquivo XML chamado *Product*e salvá-lo para o *C:\package* pasta.

3. Adicione o seguinte XML para descrever o código de produto e de namespace XML para o pacote. Substitua o código do produto com um identificador exclusivo para o pacote.

    ```xml
    <Product
    xmlns="http://schemas.microsoft.com/developer/2004/01/bootstrapper"
    ProductCode="Custom.Bootstrapper.Package">
    ```

4. Adicione o XML para especificar que o pacote tem uma dependência. Este exemplo usa uma dependência no Microsoft Windows Installer 3.1.

    ```xml
    <RelatedProducts>
        <DependsOnProduct Code="Microsoft.Windows.Installer.3.1" />
      </RelatedProducts>
    ```

5. Adicione o XML para listar todos os arquivos que estão no pacote de bootstrapper. Este exemplo usa o nome do arquivo de pacote *CorePackage.msi*.

    ```xml
    <PackageFiles>
        <PackageFile Name="CorePackage.msi"/>
    </PackageFiles>
    ```

6. Copiar ou mover o *CorePackage.msi* do arquivo para o *C:\package* pasta.

7. Adicione o XML para instalar o pacote usando comandos de bootstrapper. O bootstrapper adiciona automaticamente a **/qn** sinalizar para o *. msi* arquivo, que será instalado silenciosamente. Se o arquivo for um *.exe*, o bootstrapper é executado o *.exe* arquivo usando o shell. O seguinte XML mostra os argumentos a serem *CorePackage.msi*, mas você pode colocar o argumento de linha de comando para o `Arguments` atributo.

    ```xml
    <Commands>
        <Command PackageFile="CorePackage.msi" Arguments="">
    ```

8. Adicione o XML a seguir para verificar se este pacote de bootstrapper foi instalado. Substitua o código do produto com o GUID para o componente redistribuível.

    ```xml
    <InstallChecks>
        <MsiProductCheck
            Property="IsMsiInstalled"
            Product="{XXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX}"/>
    </InstallChecks>
    ```

9. Adicione o XML para alterar o comportamento do bootstrapper, dependendo se o componente de bootstrapper já está instalado. Se o componente está instalado, o pacote de bootstrapper não será executado. O XML a seguir verifica se o usuário atual é um administrador porque esse componente requer privilégios administrativos.

    ```xml
    <InstallConditions>
        <BypassIf
           Property="IsMsiInstalled"
           Compare="ValueGreaterThan" Value="0"/>
        <FailIf Property="AdminUser"
            Compare="ValueNotEqualTo" Value="True"
            String="NotAnAdmin"/>
    </InstallConditions>
    ```

10. Adicione o XML para definir códigos de saída se a instalação for bem-sucedida e se uma reinicialização é necessária. O XML a seguir demonstra que a falha e FailReboot códigos, o que indicam que o bootstrapper não continuará instalando pacotes de saída.

    ```xml
    <ExitCodes>
        <ExitCode Value="0" Result="Success"/>
        <ExitCode Value="1641" Result="SuccessReboot"/>
        <ExitCode Value="3010" Result="SuccessReboot"/>
        <DefaultExitCode Result="Fail" String="GeneralFailure"/>
    </ExitCodes>
    ```

11. Adicione o seguinte XML para encerrar a seção para comandos de bootstrapper.

    ```xml
        </Command>
    </Commands>
    ```

12. Mover o *C:\package* pasta para o diretório de bootstrapper do Visual Studio. Para o Visual Studio 2010, este é o *\Program Files\Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages* directory.

## <a name="example"></a>Exemplo
 O manifesto do produto contém instruções de instalação para pré-requisitos personalizados.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<Product
  xmlns="http://schemas.microsoft.com/developer/2004/01/bootstrapper"
  ProductCode="Custom.Bootstrapper.Package">

  <RelatedProducts>
    <DependsOnProduct Code="Microsoft.Windows.Installer.3.1" />
  </RelatedProducts>

  <PackageFiles>
    <PackageFile Name="CorePackage.msi"/>
  </PackageFiles>

  <InstallChecks>
    <MsiProductCheck Product="IsMsiInstalled"
      Property="{XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX}"/>
  </InstallChecks>

  <Commands>
    <Command PackageFile="CorePackage.msi" Arguments="">

      <InstallConditions>
        <BypassIf Property="IsMsiInstalled"
          Compare="ValueGreaterThan" Value="0"/>
        <FailIf Property="AdminUser"
          Compare="ValueNotEqualTo" Value="True"
         String="NotAnAdmin"/>
      </InstallConditions>

      <ExitCodes>
        <ExitCode Value="0" Result="Success"/>
        <ExitCode Value="1641" Result="SuccessReboot"/>
        <ExitCode Value="3010" Result="SuccessReboot"/>
        <DefaultExitCode Result="Fail" String="GeneralFailure"/>
      </ExitCodes>
    </Command>
  </Commands>
</Product>
```

## <a name="see-also"></a>Consulte também
- [Referência de esquema de produto e pacote](../deployment/product-and-package-schema-reference.md)