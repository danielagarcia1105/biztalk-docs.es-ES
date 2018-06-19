---
title: Cómo ampliar el Asistente del generador de esquemas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- utilities, Schema Generator Wizard
- Schema Generator Wizard
ms.assetid: ea4b5532-f904-4da0-9612-e092e7e4edc1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11db44e07191b0996043dd6b819ef2ba9162a0e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254020"
---
# <a name="how-to-extend-the-schema-generator-wizard"></a>Cómo ampliar al Asistente del generador de esquemas
Cómo ampliar al Asistente del generador de esquema existente y cómo crear a un nuevo Asistente para generación de esquema.  
  
## <a name="extend-the-existing-schema-wizard"></a>Ampliar al Asistente de esquemas existente  
  
1.  Implemente la interfaz ISchemaGenerator para crear un nuevo módulo de generación de esquemas que pueda integrar en el asistente del Generador de esquemas existente.  
  
    ```  
    public interface ISchemaGenerator  
    {  
    //Method to extract a schema from a document.  
    void GenerateSchema(string inputDocument,string outputDocumentPath);  
  
    //Method to extract the errors.  
    [return : MarshalAs(UnmanagedType.SafeArray, SafeArraySubType = VarEnum.VT_VARIANT )]object [] Errors();  
  
    //Method to extract the warnings.  
    [return : MarshalAs(UnmanagedType.SafeArray, SafeArraySubType = VarEnum.VT_VARIANT )]object [] Warnings();  
  
    //Method to extract the referenced schemas.  
    [return : MarshalAs(UnmanagedType.SafeArray, SafeArraySubType = VarEnum.VT_VARIANT )]object [] ReferencedSchemas();  
    }  
    ```  
  
2.  Coloque el ensamblado resultante en la siguiente carpeta de instalación de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Extensiones de editor de \Developer Tools\Schema  
  
     La próxima vez que ejecute el asistente del Generador de esquemas, se seleccionará automáticamente el nuevo módulo de generación de esquemas.  
  
 Siga el procedimiento siguiente para crear un nuevo asistente de esquemas.  
  
 **Ubicación en SDK**  
  
 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\SDK\Utilities\Schema generator  
  
### <a name="create-a-new-schema-wizard"></a>Crear a un nuevo Asistente de esquema  
  
1.  Ejecute InstallDTD.vbs para instalar Microsoft.BizTalk.DTDToXSDGenerator.dll en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Developer Tools\Schema extensiones de Editor. DTDToXSDGenerator.dll expone las clases que puede usar para convertir archivos DTD en XSD.  
  
2.  Ejecute InstallWFX.vbs para instalar Microsoft.BizTalk.WFXToXSDGenerator.dll en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Developer Tools\Schema extensiones de Editor. WFXToXSDGenerator.dll expone las clases que puede usar para convertir archivos WFX en XSD.  
  
## <a name="see-also"></a>Vea también  
 [Utilidades del SDK de](../core/utilities-in-the-sdk.md)