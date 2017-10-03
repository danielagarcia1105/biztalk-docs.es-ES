---
title: Tipos de elemento de adaptador XSD compatibles | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00691a9e-434f-4baa-9a01-b6f452758ab3
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3992ecface8fafacb5e1e616c930178ad0ce33a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="supported-adapter-xsd-element-types"></a>Tipos de elemento XSD compatibles con el adaptador
En la tabla siguiente se enumeran los elementos admitidos por el Marco de trabajo de adaptadores. Al definir un nuevo elemento en el esquema de configuración, utilice cualquiera de los tipos siguientes para reemplazar `string` en el ejemplo siguiente:  
  
```  
<xs:element name="uri" type="xs:string">  
```  
  
|Tipo|Tipo XML|Comportamiento de interfaz de usuario|Otros detalles|  
|----------|--------------|-----------------|---------------------|  
|string|Ninguno|Cuadro de edición que solo admite elección de tipo.|Atributo para restringir máx/Mín|  
|normalizedString|Ninguno|Cuadro de edición que solo admite elección de tipo.|Atributo para restringir máx/Mín|  
|integer|Ninguno|Cuadro de edición que solo admite elección de tipo.|Atributo para restringir máx/Mín|  
|positiveInteger|Ninguno|Cuadro de edición que solo admite elección de tipo.|Atributo para restringir máx/Mín|  
|negativeInteger|Ninguno|Cuadro de edición que solo admite elección de tipo.|Atributo para restringir máx/Mín|  
|nonNegativeInteger|Ninguno|Cuadro de edición que solo admite elección de tipo.|Atributo para restringir máx/Mín|  
|nonPositiveInteger|Ninguno|Cuadro de edición que solo admite elección de tipo.|Atributo para restringir máx/Mín|  
|int|Ninguno|Cuadro de edición que solo admite elección de tipo.|Atributo para restringir máx/Mín|  
|unsignedInt|Ninguno|Cuadro de edición que solo admite elección de tipo.|Atributo para restringir máx/Mín|  
|long|Ninguno|Cuadro de edición que solo admite elección de tipo y un decimal.|Atributo para restringir máx/Mín|  
|unsignedLong|Ninguno|Cuadro de edición que solo admite elección de tipo y un decimal.|Atributo para restringir máx/mín|  
|short|Ninguno|Cuadro de edición que solo admite elección de tipo.|Atributo para restringir máx/Mín|  
|unsignedShort|Ninguno|Cuadro de edición que solo admite elección de tipo.|Atributo para restringir máx/Mín|  
|decimal|Ninguno|Cuadro de edición que solo admite elección de tipo.|Atributo para restringir máx/Mín|  
|float|Ninguno|Cuadro de edición que solo admite elección de tipo.|Atributo para restringir máx/Mín|  
|double|Ninguno|Cuadro de edición que solo admite elección de tipo.|Atributo para restringir máx/Mín|  
|boolean|Ninguno|Lista desplegable que se rellena con valores booleanos.|Ninguno|  
|time|Ninguno|Cuadro de edición que solo admite elección de tipo.|Ninguno|  
|dateTime|Ninguno|Cuadro de edición que solo admite elección de tipo. Aparecen puntos suspensivos al final del área de campo. Haga clic en los puntos suspensivos para que aparezca el calendario.|Ninguno|  
|date|Ninguno|Cuadro de edición que solo admite elección de tipo. Aparecen puntos suspensivos al final del área de campo. Haga clic en los puntos suspensivos para que aparezca el calendario.|Ninguno|  
|gMonth|Ninguno|Cuadro de edición que solo admite elección de tipo.|Este valor es una cadena, por lo que puede que no funcione del modo esperado. Considere la posibilidad de utilizar tipos xsd:int con restricciones, para alojar el valor de mes.|  
|gYear|Ninguno|Cuadro de edición que solo admite elección de tipo.|Este valor es una cadena, por lo que puede que no funcione del modo esperado. Considere la posibilidad de utilizar tipos xsd:int con restricciones, para alojar el valor de año.|  
|gYearMonth|Ninguno|Cuadro de edición que solo admite elección de tipo.|Este valor es una cadena, por lo que puede que no funcione del modo esperado. Considere la posibilidad de utilizar tipos xsd:int con restricciones, para alojar los valores de mes y año.|  
|gDay|Ninguno|Cuadro de edición que solo admite elección de tipo.|Este valor es una cadena, por lo que puede que no funcione del modo esperado. Considere la posibilidad de utilizar tipos xsd:int con restricciones, para alojar el valor de día.|  
|gMonthDay|Ninguno|Cuadro de edición que solo admite elección de tipo.|Este valor es una cadena, por lo que puede que no funcione del modo esperado. Considere la posibilidad de utilizar tipos xsd:int con restricciones, para alojar los valores de mes y día.|  
|Nombre|Ninguno|Cuadro de edición que solo admite elección de tipo.|Ninguno|  
|NCName|Ninguno|Cuadro de edición que solo admite elección de tipo.|Ninguno|  
|anyURI|Ninguno|Cuadro de edición que solo admite elección de tipo.|Ninguno|  
|Secuencia|Elemento de esquema "Sequence"|Ninguno|Ninguno|  
|Grupos|Ninguno|Los signos "+" o "-" expanden o contraen todos los campos de un grupo.<br /><br /> Ninguna funcionalidad de edición en el lado derecho de la página de propiedades.|Ninguno|  
|Nombre de archivo|FileName|Aparecen puntos suspensivos al final del área de campo. Haga clic en el botón de puntos suspensivos y la **Windows FileOpen** aparece el cuadro de diálogo, que permita la selección de un archivo.|Ninguno|  
|Folder Name|FolderName|Aparecen puntos suspensivos al final del área de campo. Haga clic en el botón de puntos suspensivos y la **Windows Folderopen** aparece el cuadro de diálogo Permitir selección de una carpeta.|Ninguno|  
|Id. de aplicación de SSO|SSOAppID|Lista desplegable que se rellena con la lista de aplicaciones de SSO|Ninguno|  
|Contraseña|Contraseña|Cuadro de edición en el que aparece "*" en lugar de texto no cifrado.|Ninguno|  
  
## <a name="see-also"></a>Vea también  
 [Problemas de diseño del adaptador](../core/adapter-design-issues.md)