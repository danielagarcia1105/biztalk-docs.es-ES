---
title: Diferentes tipos de esquemas de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad8847d3-6f0e-4982-b4a8-92a5f39a4b48
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a60907b3b8bbecf430984ec3a799bc1f91953be
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010701"
---
# <a name="different-types-of-biztalk-schemas"></a>Tipos de esquemas de BizTalk
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] admite los siguientes cuatro tipos de esquemas:  
  
- **Esquema XML**. un esquema XML define la estructura de una clase de mensajes de instancia XML. Puesto que este tipo de esquema usa el lenguaje de definición de esquemas XML (XSD) para definir la estructura de un mensaje de instancia XML, y éste es el fin previsto de XSD, dichos esquemas usan XSD de un modo sencillo.  
  
- **Esquema de archivo sin formato**. un esquema de archivo sin formato define la estructura de una clase de mensajes de instancia que usan un formato de archivo sin formato, ya sea delimitado, posicional o una combinación de los anteriores. Dado que las capacidades semánticas nativas de XSD no dar cabida a todos los requisitos para definir la estructura de mensajes de instancia de archivo sin formato, como los distintos tipos de delimitadores que se pueden usar para diversos registros y campos del archivo sin formato: BizTalk Server utiliza las capacidades de anotación de XSD para almacenar esta información adicional dentro de un esquema XSD. BizTalk Server define un eficaz conjunto de etiquetas de anotación específicas útiles para almacenar toda la información adicional necesaria.  
  
- **Esquema de sobres**. un esquema de sobre es un tipo especial de esquema XML. Los esquemas de sobres se utilizan para definir la estructura de los sobres XML, que permiten incluir uno o más documentos empresariales XML en un único mensaje de instancia XML. Al definir un esquema XML para que sea un esquema de sobre, es necesario configurar un par de propiedades adicionales, en función de factores tales como si hay más de un registro raíz definido en el esquema de sobre.  
  
- **Esquema de propiedad**. los esquemas de propiedades se utilizan con uno de los dos mecanismos existentes en BizTalk Server para lo que se conoce como promoción de propiedades. La promoción de propiedades es el proceso de copiar valores específicos que se encuentran en niveles profundos de un mensaje de instancia al contexto del mensaje. En el contexto del mensaje, varios componentes de BizTalk Server pueden tener un acceso más sencillo a estos valores. Estos componentes utilizan los valores para realizar acciones como el enrutamiento de mensajes. Justo antes de que el mensaje de instancia se envíe al destino, los valores de las propiedades promocionadas también se pueden copiar en la otra dirección, desde el de más fácil acceso contexto del mensaje a los niveles profundos del mensaje de instancia. Un esquema de propiedades es una versión simple de un esquema de BizTalk que desempeña un rol en el proceso de copiar las propiedades promocionadas entre el mensaje de instancia y el contexto del mensaje.  
  
  El resto de la sección proporciona información adicional acerca de estos cuatro tipos de esquemas en BizTalk Server.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Esquemas XML](../core/xml-schemas.md)  
  
-   [Esquemas de archivos sin formato](../core/flat-file-schemas.md)  
  
-   [Esquemas de sobres](../core/envelope-schemas.md)  
  
-   [Esquemas de propiedades](../core/property-schemas.md)