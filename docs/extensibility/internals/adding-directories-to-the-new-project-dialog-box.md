---
title: Adicionar diretórios à caixa de diálogo Novo projeto | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- New Project dialog box, extending
ms.assetid: 53b328f5-20bb-49a3-bf9e-1818f4fbdf50
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9d8e68413795b7004542ee312dcb27492e55e7f0
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56626187"
---
# <a name="add-directories-to-the-new-project-dialog-box"></a>Adicionar diretórios à caixa de diálogo Novo projeto
Quando você cria novos tipos de projeto, você também pode registrar um novo diretório na **novo projeto** caixa de diálogo para exibi-los para uso como modelos. O exemplo de código a seguir explica como registrar um novo diretório, também conhecido como um nó. No exemplo, modelos expostos pelo VSPackage *CLSID_Package*, são registrados. Como resultado, o lado esquerdo do **novo projeto** caixa de diálogo oferece o nó adicionado, com um nome determinado pelo *Folder_Label_ResID* recursos. Esse recurso é carregado do DLL de satélite do VSPackage.

 O **pasta** valor representa um GUID de uma pasta sob a qual o *Folder_Label_ResID* nó é exibido. No exemplo, o GUID que representa o **outros projetos** pasta na **tipos de projeto** painel da **novo projeto** caixa de diálogo. Se o **outros projetos** valor estiver ausente, o rótulo é posicionado no nível superior.

 O `TemplatesDir` valor Especifica o caminho completo do diretório que contém os modelos de projeto. Esses arquivos podem ser *. vsz* arquivos ou arquivos de modelo típico a ser clonado.

 Se você especificar `TemplatesLocalizedSubDir`, ele deve ser a ID do recurso de uma cadeia de caracteres que nomeia o subdiretório do `TemplatesDir` que contém modelos localizados. Porque [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] carrega o recurso de cadeia de caracteres de uma DLL satélite se você tiver um, cada DLL satélite pode conter um nome de subdiretório diferentes. O `SortPriority` valor Especifica uma prioridade de classificação.

```
NoRemove NewProjectTemplates
{
    NoRemove TemplateDirs
  {
    ForceRemove %CLSID_Package%
    {
      ForceRemove /1 = s '#%Folder_Label_ResID%'
      {
        val Folder = s '{DCF2A94A-45B0-11D1-ADBF-00C04FB6BE4C}'
        val TemplatesDir = s '%Template_Path%'
        val TemplatesLocalizedSubDir = s '#100'
        val SortPriority = d 1000
      }
    }
  }
}
```

## <a name="see-also"></a>Consulte também
- [Registrar os modelos de projeto e de item](../../extensibility/internals/registering-project-and-item-templates.md)
- [Adicionar itens à caixa de diálogo Adicionar Novo Item](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)
- [Adicionar diretórios à caixa de diálogo Adicionar Novo Item](../../extensibility/internals/adding-directories-to-the-add-new-item-dialog-box.md)