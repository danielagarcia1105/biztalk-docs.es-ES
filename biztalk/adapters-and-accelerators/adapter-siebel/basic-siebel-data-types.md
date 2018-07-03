---
title: Los tipos de datos básicos de Siebel | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Siebel data types, supported
ms.assetid: bf86f639-6c45-49db-9e58-79c3ad2c9978
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d45a5c8b0caf16d38df7b368c6f0f63ba020d95
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971549"
---
# <a name="basic-siebel-data-types"></a>Tipos de datos básicos de Siebel
Esta sección describe cómo se admiten los tipos de datos de Siebel en el [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].  

## <a name="supported-siebel-data-types"></a>Tipos de datos admitidos de Siebel  
 La siguiente tabla muestra los tipos de datos de Siebel el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] admite y cómo se representan mediante el adaptador de BizTalk (tipo XSD) y en el modelo de servicio WCF (tipo de. NET). Para los tipos marcados con un asterisco, vea la nota que sigue a la tabla.  


|     Tipo de datos     |    Tipo XSD    | Tipo de .NET |                                                                                                                                                                                                                                                                                                                                                                             Descripción                                                                                                                                                                                                                                                                                                                                                                              |
|-------------------|----------------|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    DTYPE_BOOL     |  xsd:boolean   |  Boolean  |                                                                                                                                                                                                                                                                                                                                                                                  -                                                                                                                                                                                                                                                                                                                                                                                   |
|  DTYPE_CURRENCY   |  xsd:decimal   |  Decimal  |                                                                                                                                                                                                                                                                                                                                                                                  -                                                                                                                                                                                                                                                                                                                                                                                   |
|    DTYPE_DATE     | xsd: DateTime\* | DateTime  | El valor no debe ser la hora Universal coordinada (UTC).<br /><br /> -En XSD: DateTime, los valores se esperan que siga este patrón: "(\d\d\d\d-\d\d-\d\d)T(00:00:00) (.\*)".<br />-En **DateTime** objetos,**DateTime.Kind** debe ser **DateTimeKind.Unspecified**.<br /><br /> El componente de hora se omitirá el adaptador.<br /><br /> Para los mensajes salientes, el adaptador realiza una validación en tiempo de ejecución para asegurarse de que el valor especificado no es UTC (z o diferencia horaria con UTC). Si se produce un error en la que la validación, el adaptador lanza una excepción.<br /><br /> Cuando este tipo se expone como XSD: String (según las reglas que se explica más adelante):<br /><br /> -El formato viene determinado por la base de datos subyacente.<br />-Ninguna validación en tiempo de ejecución se realiza en el valor. |
|  DTYPE_DATETIME   | xsd: DateTime\* | DateTime  |                                                                                          El valor puede contener componentes de fecha y hora y no debe ser la hora UTC.<br /><br /> -En **DateTime** objetos, **DateTime.Kind** debe ser **DateTimeKind.Unspecified**.<br /><br /> Para los mensajes salientes, el adaptador realiza una validación en tiempo de ejecución para asegurarse de que se cumplen estas condiciones; Si se produce un error en la validación, el adaptador lanza una excepción.<br /><br /> Cuando este tipo se expone como XSD: String (según las reglas que se explica más adelante):<br /><br /> -El formato viene determinado por la base de datos subyacente.<br />-Ninguna validación en tiempo de ejecución se realiza en el valor.                                                                                           |
|     DTYPE_ID      |   xsd:cadena   |  String   |                                                                                                                                                                                                                                                                                                                                                                                  -                                                                                                                                                                                                                                                                                                                                                                                   |
|   DTYPE_INTEGER   |    xsd:int     |   Int32   |                                                                                                                                                                                                                                                                                                                                                                                  -                                                                                                                                                                                                                                                                                                                                                                                   |
|    DTYPE_NOTE     |   xsd:cadena   |  String   |                                                                                                                                                                                                                                                                                                                                                                                  -                                                                                                                                                                                                                                                                                                                                                                                   |
|   DTYPE_NUMBER    |  xsd:decimal   |  Decimal  |                                                                                                                                                                                                                                                                                                                                                                                  -                                                                                                                                                                                                                                                                                                                                                                                   |
|    DTYPE_PHONE    |   xsd:cadena   |  String   |                                                                                                                                                                                                                                                                                                                                                                                  -                                                                                                                                                                                                                                                                                                                                                                                   |
|    DTYPE_TEXT     |   xsd:cadena   |  String   |                                                                                                                                                                                                                                                                                                                                                                                  -                                                                                                                                                                                                                                                                                                                                                                                   |
|    DTYPE_TIME     | xsd: DateTime\* | DateTime  |                                       El valor no debe ser la hora UTC.<br /><br /> -En XSD: DateTime, se esperan que siga este patrón de los valores: (1753-01-01)T(\d\d:\d\d:\d\d) (.\*) ".<br />-En **DateTime** objetos<strong>, DateTime.Kind</strong> debe ser **DateTimeKind.Unspecified**.<br /><br /> Para los mensajes salientes, el adaptador realiza una validación en tiempo de ejecución para asegurarse de que el valor especificado no es UTC (z o diferencia horaria con UTC). Si se produce un error en la que la validación, el adaptador lanza una excepción.<br /><br /> Cuando este tipo se expone como XSD: String (según las reglas que se explica más adelante):<br /><br /> -El formato viene determinado por la base de datos subyacente.<br />-Ninguna validación en tiempo de ejecución se realiza en el valor.                                       |
| DTYPE_UTCDATETIME | xsd: DateTime\* | DateTime  |                                                   El valor puede contener componentes de fecha y hora y debe ser la hora UTC.<br /><br /> -En XSD: DateTime, el valor se debe expresar en UTC (notación de "Z" o diferencia horaria con UTC).<br />-En **DateTime** objetos **DateTime.Kind** debe ser **DateTimeKind.Utc**.<br /><br /> Para los mensajes salientes, el adaptador realiza una validación en tiempo de ejecución para asegurarse de que se cumplen estas condiciones; Si se produce un error en la validación, el adaptador lanza una excepción.<br /><br /> Cuando este tipo se expone como XSD: String (según las reglas que se explica más adelante):<br /><br /> -El formato viene determinado por la base de datos subyacente.<br />-Ninguna validación en tiempo de ejecución se realiza en el valor.                                                   |

 Los siguientes son los tipos de argumento del método de servicio para la empresa:  

 date  
 Igual que DTYPE_DATE.  

 Number  
 Igual que DTYPE_NUMBER.  

 String  
 Igual que DTYPE_TEXT.  

 Hierarchy  
 Corresponde a XSD de tipo XSD: String y al tipo String. NET.  En los mensajes XML, este debe colocarse en un nodo de CDATA.  

 Objeto de integración  
 Igual que la jerarquía.  

 * El adaptador determina si se debe usar xsd: DateTime o xsd: String para representar los campos DTYPE_DATE, DTYPE_DATETIME, DTYPE_TIME y DTYPE_UTCDATETIME en componentes empresariales de la siguiente manera.  

1.  Si el campo del componente empresarial tiene uno de los tipos de datos anteriores, el adaptador expondrá como el XSD: DateTime tipo (en .net que se asigna al tipo de fecha y hora).  

2.  Si el campo del componente empresarial no tiene ningún tipo de datos, el adaptador se expondrá como XSD: String (en .net que se asigna al tipo de cadena).  

## <a name="supported-facets-for-the-xml-schema-types"></a>Facetas admitidas para los tipos de esquemas XML  
 El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] admite las siguientes facetas para los tipos de esquemas XML.  

|Tipo de Siebel|Faceta|  
|-----------------|-----------|  
|DTYPE_BOOL|None|  
|DTYPE_CURRENCY|Precisión (22), escala|  
|DTYPE_DATE|(\d\d\d\d-\d\d-\d\d)T(00:00:00)(.*)|  
|DTYPE_DATETIME|None|  
|DTYPE_ID|MaxLength (15)|  
|DTYPE_INTEGER|Precisión (22)|  
|DTYPE_NOTE|MaxLength (16384)|  
|DTYPE_NUMBER|Precisión (22), escala|  
|DTYPE_PHONE|MaxLength (40)|  
|DTYPE_TEXT|MaxLength (2048)|  
|DTYPE_TIME|(1753-01-01) T(\d\d:\d\d:\d\d)(.*)|  
|DTYPE_UTCDATETIME|None|  

 Los siguientes son algunas reglas que rigen cómo y cuándo se publican las facetas y sus valores,:  

 Si el atributo de longitud del campo se establece en un valor mayor que cero y menor o igual que el valor máximo (especificado entre paréntesis en la tabla anterior):  

-   La faceta de precisión se publica como sigue:  

    -   Si se establece el atributo de precisión para el campo, el mismo valor se publica como faceta Precision.  

    -   Si no se establece el atributo de precisión para el campo, el valor de longitud se publica como la faceta Precision.  

-   La faceta de escala se publica únicamente si:  

    -   Se ha publicado el atributo de precisión  

    -   El atributo de escala está establecido para el campo en un valor mayor que cero y menor que el valor publicado como parte de la faceta de precisión  

-   La faceta MaxLength es el valor especificado para el atributo Length. Esto se selecciona en el repositorio de definición de campo. En caso de que no se especifica la longitud en el repositorio de definición de campo, se publica el valor especificado en paréntesis en la tabla anterior.  

### <a name="special-cases-related-to-siebel-data-types"></a>Casos especiales relacionadas con los tipos de datos de Siebel  
 Las siguientes reglas afectan a las facetas de campo de componente empresarial según el contexto de la operación en el que se usan. Estas reglas son aplicables para operaciones de INSERCIÓN y actualización. Para las operaciones de consulta, todos los campos de componente de negocio se exponen al usuario.  

 **Campo del componente empresarial marcado como obligatorio en Siebel**  

 Incluso si un campo del componente empresarial está marcado como obligatorio en el sistema Siebel pero se establecen los valores predeterminados anterior o posterior a la predeterminada para el campo, [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] marca el campo como opcional. Por lo tanto, si un usuario proporciona un valor que se va a insertar o actualizar, el adaptador procesa ese valor. Si se proporciona ningún valor, Siebel usa los valores de pre-default/post-default.  

 **Campo del componente empresarial no está marcado como READ ONLY en Siebel**  

 Si un campo del componente empresarial no está marcado como READ ONLY, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] lo expone como un campo de escritura. Sin embargo, hay un par de excepciones a esta regla. Los enfoques son:  

- Si el campo del componente empresarial es un **Calculated** campo de Siebel, no aparecerá en las operaciones de inserción o actualización porque Siebel automáticamente se encargará de **Calculated** campos.  

- Si el campo del componente de negocio se obtiene a través de una combinación explícita (combinación de tabla en otra tabla), es normalmente de solo lectura. Sin embargo Siebel permite que los datos se escriban en este campo si es un campo de lista desplegable. Por lo tanto, si el campo del componente empresarial proviene de una combinación explícita y el campo no es un campo de lista desplegable, a continuación, no aparecerá en las operaciones de inserción o actualización porque los clientes del adaptador no pueden escribir datos en esos campos.  

  **Tipo de datos de un campo que no se especifica en el componente empresarial**  

  Si no se especifica el tipo de datos de un campo del componente empresarial, la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] expone los metadatos de campo mediante la heurística siguiente.  

- Si el campo es un campo especial (es decir, lista desplegable o combinación), el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] buscará en el campo asignado en el componente empresarial de destino. Si ese campo tiene un tipo asociado, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] va a exponer como el tipo del campo. Sin embargo, si ese tipo es DTYPE_DATE, DTYPE_TIME, DTYPE_DATETIME o DTYPE_UTCDATETIME, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] expondrá el campo como el tipo XSD: String. Si el campo asignado no tiene un tipo asociado, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] expondrá el campo original como el tipo XSD: String.  

- Si el campo no es una lista desplegable o un campo de combinación, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] expondrá como el tipo XSD: String.  

  **Tipo de datos, longitud de campo o la precisión de un componente de negocio principal no está disponible**  

  Si los datos de tipo, longitud, o el campo de la precisión de un componente de negocio principal (un componente empresarial que tiene un componente de negocio secundarios basándose en las listas desplegables o MVLs), el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Obtiene la información sobre el tipo de datos, longitud, precisión y escala de la componente empresarial de lista desplegable o el componente empresarial MVL.  

## <a name="see-also"></a>Vea también  
 [Los mensajes y esquemas de mensaje para el adaptador de BizTalk para aplicaciones Siebel eBusiness](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)