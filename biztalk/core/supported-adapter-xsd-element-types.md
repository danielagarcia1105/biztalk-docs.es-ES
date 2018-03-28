---
title: Tipos de elemento de adaptador XSD compatibles | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00691a9e-434f-4baa-9a01-b6f452758ab3
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3992ecface8fafacb5e1e616c930178ad0ce33a7
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="supported-adapter-xsd-element-types"></a>Tipos de elemento XSD compatibles con el adaptador
En la tabla siguiente se enumeran los elementos admitidos por el Marco de trabajo de adaptadores. Al definir un nuevo elemento en el esquema de configuración, utilice cualquiera de los tipos siguientes para reemplazar `string` en el ejemplo siguiente:  
  
```  
<xs:element name="uri" type="xs:string">  
```  
  
|Tipo|Tipo XML|Comportamiento de interfaz de usuario|Otros detalles|  
|----------|--------------|-----------------|---------------------|  
|string|None|Cuadro de edición que solo admite elección de tipo.|Atributo para restringir máx/Mín|  
|normalizedString|None|Cuadro de edición que solo admite elección de tipo.|Atributo para restringir máx/Mín|  
|integer|None|Cuadro de edición que solo admite elección de tipo.|Atributo para restringir máx/Mín|  
|positiveInteger|None|Cuadro de edición que solo admite elección de tipo.|Atributo para restringir máx/Mín|  
|negativeInteger|None|Cuadro de edición que solo admite elección de tipo.|Atributo para restringir máx/Mín|  
|nonNegativeInteger|None|Cuadro de edición que solo admite elección de tipo.|Atributo para restringir máx/Mín|  
|nonPositiveInteger|None|Cuadro de edición que solo admite elección de tipo.|Atributo para restringir máx/Mín|  
|int|None|Cuadro de edición que solo admite elección de tipo.|Atributo para restringir máx/Mín|  
|unsignedInt|None|Cuadro de edición que solo admite elección de tipo.|Atributo para restringir máx/Mín|  
|long|None|Cuadro de edición que solo admite elección de tipo y un decimal.|Atributo para restringir máx/Mín|  
|unsignedLong|None|Cuadro de edición que solo admite elección de tipo y un decimal.|Atributo para restringir máx/mín|  
|short|None|Cuadro de edición que solo admite elección de tipo.|Atributo para restringir máx/Mín|  
|unsignedShort|None|Cuadro de edición que solo admite elección de tipo.|Atributo para restringir máx/Mín|  
|decimal|None|Cuadro de edición que solo admite elección de tipo.|Atributo para restringir máx/Mín|  
|float|None|Cuadro de edición que solo admite elección de tipo.|Atributo para restringir máx/Mín|  
|double|None|Cuadro de edición que solo admite elección de tipo.|Atributo para restringir máx/Mín|  
|boolean|None|Lista desplegable que se rellena con valores booleanos.|None|  
|time|None|Cuadro de edición que solo admite elección de tipo.|None|  
|dateTime|None|Cuadro de edición que solo admite elección de tipo. Aparecen puntos suspensivos al final del área de campo. Haga clic en los puntos suspensivos para que aparezca el calendario.|None|  
|date|None|Cuadro de edición que solo admite elección de tipo. Aparecen puntos suspensivos al final del área de campo. Haga clic en los puntos suspensivos para que aparezca el calendario.|None|  
|gMonth|None|Cuadro de edición que solo admite elección de tipo.|Este valor es una cadena, por lo que puede que no funcione del modo esperado. Considere la posibilidad de utilizar tipos xsd:int con restricciones, para alojar el valor de mes.|  
|gYear|None|Cuadro de edición que solo admite elección de tipo.|Este valor es una cadena, por lo que puede que no funcione del modo esperado. Considere la posibilidad de utilizar tipos xsd:int con restricciones, para alojar el valor de año.|  
|gYearMonth|None|Cuadro de edición que solo admite elección de tipo.|Este valor es una cadena, por lo que puede que no funcione del modo esperado. Considere la posibilidad de utilizar tipos xsd:int con restricciones, para alojar los valores de mes y año.|  
|gDay|None|Cuadro de edición que solo admite elección de tipo.|Este valor es una cadena, por lo que puede que no funcione del modo esperado. Considere la posibilidad de utilizar tipos xsd:int con restricciones, para alojar el valor de día.|  
|gMonthDay|None|Cuadro de edición que solo admite elección de tipo.|Este valor es una cadena, por lo que puede que no funcione del modo esperado. Considere la posibilidad de utilizar tipos xsd:int con restricciones, para alojar los valores de mes y día.|  
|Nombre|None|Cuadro de edición que solo admite elección de tipo.|None|  
|NCName|None|Cuadro de edición que solo admite elección de tipo.|None|  
|anyURI|None|Cuadro de edición que solo admite elección de tipo.|None|  
|Secuencia|Elemento de esquema "Sequence"|None|None|  
|Grupos|None|Los signos "+" o "-" expanden o contraen todos los campos de un grupo.<br /><br /> Ninguna funcionalidad de edición en el lado derecho de la página de propiedades.|None|  
|Nombre de archivo|FileName|Aparecen puntos suspensivos al final del área de campo. Haga clic en el botón de puntos suspensivos y la **Windows FileOpen** aparece el cuadro de diálogo, que permita la selección de un archivo.|None|  
|Folder Name|FolderName|Aparecen puntos suspensivos al final del área de campo. Haga clic en el botón de puntos suspensivos y la **Windows Folderopen** aparece el cuadro de diálogo Permitir selección de una carpeta.|None|  
|Id. de aplicación de SSO|SSOAppID|Lista desplegable que se rellena con la lista de aplicaciones de SSO|None|  
|Contraseña|Contraseña|Cuadro de edición en el que aparece "*" en lugar de texto no cifrado.|None|  
  
## <a name="see-also"></a>Vea también  
 [Problemas de diseño del adaptador](../core/adapter-design-issues.md)