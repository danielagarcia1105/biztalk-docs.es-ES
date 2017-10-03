---
title: "Diseñador de configuración de adaptador personalizado | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9b231c3-3948-4db8-b4f0-d9c21c31b168
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e876892b3eef9e5dd47c51c64997d84a0f0dc98
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="custom-adapter-configuration-designer"></a>Diseñador de configuración de adaptador personalizado
Deberá crear una biblioteca de clases .NET a partir de los diseñadores personalizados. Puede integrarlos al DLL del adaptador o crear un DLL distinto.  Una vez creado un ensamblado de diseñador debe hacer referencia a él mediante decoraciones, como lo haría con una descripción o categoría. La referencia incluye una especificación del ensamblado y un nombre completo de clase para su uso.  
  
 Estas decoraciones permiten dos maneras de hacer referencia al diseñador personalizado específico: como un ensamblado en la caché global de ensamblados global o como un ensamblado externo ubicado en el disco.  
  
> [!NOTE]
>  Hay dos rutas de acceso de un ensamblado en tiempo de diseño posibles: puede especificar la ruta de acceso absoluta a los editores de tipo y los convertidores utilizados en la configuración de XSD en dicho XSD (no se admite la ruta de acceso relativa), o puede almacenar los convertidores y editores de tipo en la información global caché de ensamblados y necesita una ruta de acceso absoluta.  
  
## <a name="global-assembly-cache-designer-use"></a>Uso del diseñador de la caché de ensamblados global  
 La caché de ensamblados global almacena ensamblados por nombre, clave pública, versión y referencia cultural. Por este motivo es recomendable:  
  
1.  Generar un archivo de clave pública y agregarlo al archivo AssemblyInfo.cs.  
  
2.  Especificar una versión específica en el archivo AssemblyInfo.cs.  
  
 Puede arrastrar el ensamblado hasta la caché de ensamblados global o usar GACUTIL para agregarlo a ella.  
  
 Para usar este diseñador, especifique el nombre completo de clase, una coma y la entrada de la caché de ensamblados global (nombre de ensamblado, versión, referencia cultural y token de clave pública) como valor de la decoración. Use \<editor > decoraciones para **UITypeEditor** implementaciones y \<convertidor > decoraciones para **TypeConverter** implementaciones.  
  
 En el código siguiente se muestra cómo inicializar los diseñadores personalizados en un archivo XSD:  
  
```  
<xs:element name="Global" type="xs:string">  
   <xs:annotation>  
      <xs:appinfo>  
         <baf:designer>  
            <baf:category>GAC Designer Component</baf:category>  
            <baf:editor>AdapterManagement.ComponentModel. PasswordUITypeEditor, AdapterManagement, Version=1.0.1.0, Culture=neutral, PublicKeyToken=f0db50abb0615c18</baf:editor>  
         </baf:designer>  
      </xs:appinfo>  
   </xs:annotation>  
</xs:element>  
      </xs:sequence>  
```  
  
## <a name="external-assembly-installation-and-use"></a>Instalación y uso de un ensamblado externo  
 Para ensamblados externos, la decoración contiene un ensamblado de atributo opcional que especifica el nombre y ruta completos del ensamblado que contiene el diseñador deseado.  
  
 En el código siguiente se muestra cómo inicializar los diseñadores personalizados contenidos en ensamblados externos:  
  
```  
<xs:element name="External" type="xs:string">  
   <xs:annotation>  
      <xs:appinfo>  
         <baf:designer>  
            <baf:category>External Designer Component</baf:category>  
            <baf:converter assembly="C:\source\private\Adapter\Framework\Designer\bin\Debug\Designer.External.dll">Designer.External.DesignerTypeConverter</baf:converter>  
         </baf:designer>  
      </xs:appinfo>  
   </xs:annotation>  
</xs:element>  
```  
  
## <a name="see-also"></a>Vea también  
 [Editor desplegable personalizado para la configuración del adaptador](../core/custom-drop-down-editor-for-adapter-configuration.md)   
 [Editor de cuadro de diálogo Modal personalizado para la configuración del adaptador](../core/custom-modal-dialog-editor-for-adapter-configuration.md)   
 [Convertidor de tipos personalizado para la configuración del adaptador](../core/custom-type-converter-for-adapter-configuration.md)   
 [Componentes de configuración avanzada para adaptadores](../core/advanced-configuration-components-for-adapters.md)