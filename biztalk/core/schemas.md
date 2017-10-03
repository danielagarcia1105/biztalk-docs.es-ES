---
title: Esquemas | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, schema types
- deploying, schemas
- schemas
- schemas, about schemas
- property schemas
- envelope schemas
- schemas, deploying
- XML schemas
- flat file schemas
ms.assetid: aea772bd-e7ab-448e-ba82-e7c8f38087db
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 696c79a30bb58cd91536c19c97db54d6159762b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="schemas"></a>Esquemas
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] utiliza el lenguaje de definición (XSD) de esquemas XML para definir la estructura de todos los mensajes que procesa y hace referencia a estas definiciones de estructura de mensaje como *esquemas*. Salvo contadas excepciones, los mensajes estructurados son la base de cualquier aplicación. Estos mensajes estructurados pueden adoptar cualquier forma, ser grandes o pequeños, y dirigirse a un amplio conjunto de sistemas de servidor y almacenes de datos. Los sistemas que crean y consumen mensajes estructurados a menudo usan distintos formatos. Dos de los formatos más comunes en los mensajes estructurados son XML y archivos sin formato.  
  
 BizTalk Server es compatible con los cuatro tipos siguientes de esquema:  
  
-   Esquema XML: un esquema XML define la estructura de una clase de mensajes de instancia XML. Puesto que este tipo de esquema usa el lenguaje de definición de esquemas XML (XSD) para definir la estructura de un mensaje de instancia XML, y éste es el fin previsto de XSD, dichos esquemas usan XSD de un modo sencillo. Para obtener más información acerca de los esquemas XML, vea [esquemas XML](../core/xml-schemas.md).  
  
-   Esquema de archivo sin formato. un esquema de archivo sin formato define la estructura de una clase de mensajes de instancia que usan un formato de archivo sin formato, ya sea delimitado, posicional o una combinación de los anteriores. Dado que las capacidades semánticas nativas de XSD no se ajustan a todos los requisitos para definir la estructura de mensajes de instancia de archivo sin formato, como los distintos tipos de delimitadores que podrían utilizarse para diversos registros y campos del archivo sin formato: BizTalk Server utiliza las capacidades de anotación de XSD para almacenar esta información adicional dentro de un esquema XSD. BizTalk Server define un eficaz conjunto de etiquetas de anotación específicas útiles para almacenar toda la información adicional necesaria. Para obtener más información acerca de los esquemas de archivo sin formato, vea [esquemas de archivo sin formato](../core/flat-file-schemas.md).  
  
-   Esquema de sobre. un esquema de sobre es un tipo de esquema XML. Los esquemas de sobres se utilizan para definir la estructura de los sobres XML, que permiten incluir uno o más documentos empresariales XML en un único mensaje de instancia XML. Al definir un esquema XML para que sea un esquema de sobre, es necesario configurar propiedades adicionales, en función de factores tales como si hay más de un registro raíz definido en el esquema de sobre. Para obtener más información acerca de los esquemas de sobres, consulte [esquemas de sobres](../core/envelope-schemas.md).  
  
-   Esquema de propiedad. los esquemas de propiedades se utilizan con uno de los dos mecanismos existentes en BizTalk Server para la promoción de propiedades. *Promoción de propiedades* es el proceso de copiar valores específicos en niveles profundos de un mensaje de instancia en el contexto del mensaje. En el contexto del mensaje, varios componentes de BizTalk Server pueden tener un acceso más sencillo a estos valores. Estos componentes utilizan los valores para realizar acciones como el enrutamiento de mensajes. Justo antes de que el mensaje de instancia se envíe al destino, los valores de las propiedades promocionadas también se pueden copiar en la otra dirección, desde el de más fácil acceso contexto del mensaje a los niveles profundos del mensaje de instancia. Un esquema de propiedades, que es una versión simple de un esquema de BizTalk, desempeña una función en el proceso de copiar las propiedades promocionadas entre el mensaje de instancia y el contexto del mensaje. Para obtener más información acerca de los esquemas de propiedad, vea [esquemas de propiedades](../core/property-schemas.md).  
  
## <a name="schema-deployment"></a>Implementación de esquemas  
 Existen varios tipos de esquemas que implementará, como esquemas de mensajes, esquemas de propiedades y esquemas de sobres. Puesto que cada esquema es distinto, hay pocas diferencias respecto a cómo se administran después de la implementación. En esta sección se describen los elementos comunes a todos los esquemas, además de las diferencias relacionadas con los tipos de esquema.  
  
 Al implementar un esquema, la base de datos de administración almacena el contenido de éste. Puede implementar varios esquemas con el mismo espacio de nombres de destino. BizTalk Server señala de forma explícita al esquema en el Diseñador de canalizaciones que se utiliza en tiempo de ejecución. Si usa canalizaciones predeterminadas o no especifica un esquema en el Diseñador de canalizaciones y se implementan varias versiones del mismo esquema, BizTalk Server determina el esquema que se debe usar. En este caso, será el esquema asociado a la versión más reciente, con el mayor número de versión: del ensamblado implementado con ese esquema.  
  
 Al quitar la versión más reciente del ensamblado que implementó un esquema, el esquema de la versión previa superior del mismo ensamblado se convierte en el esquema activo.  
  
 Si implementa esquemas con espacios de nombres de destino duplicados, debe hacer referencia a un esquema desde una canalización personalizada diseñada por el usuario. Esto proporciona al motor de mensajería información adicional que le permite cargar el esquema correcto.  
  
 Por ejemplo, un caso en el que se debe usar un espacio de nombres de destino duplicado es cuando se crean varias versiones del esquema de un servicio Web.  
  
## <a name="see-also"></a>Vea también  
 [Crear esquemas con el Editor de BizTalk](../core/creating-schemas-using-biztalk-editor.md)   
 [Representación de esquemas de BizTalk](../core/biztalk-representation-of-schemas.md)   
 [Artefactos](../core/artifacts.md)