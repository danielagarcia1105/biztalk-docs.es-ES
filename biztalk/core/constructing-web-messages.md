---
title: Construir mensajes Web | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web messages, about Web messages
- Web messages, message types
- Web services, Web messages
- Web messages, parts
- Web messages
- messages, Web messages
ms.assetid: ca1792be-5fba-4f5d-a88e-b854f6a8ce33
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c344bbb836a6524ec1fd2656a5ba3f8bc8fad7d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237988"
---
# <a name="constructing-web-messages"></a>Construcción de mensajes Web
Construirá un mensaje Web a partir de un tipo de mensaje Web. Al agregar una referencia Web, BizTalk crea tipos de mensajes Web de forma automática basándose en los métodos Web del servicio Web agregado. Cuando se agrega un mensaje Web a la orquestación, se establece el tipo de mensaje como uno de los tipos de mensajes Web. Las partes individuales de mensaje se crean en función de los tipos de esquemas o los tipos .NET primitivos. Aun así, es posible construir un mensaje Web que no contenga partes de mensaje.  
  
 **Tipos de mensajes Web**  
  
 Los tipos de mensajes Web, definidos en el archivo Reference.odx, son idénticos a un tipo de mensaje normal, con la excepción de que no se pueden modificar, cambiar de nombre o eliminar. Para poder eliminar un tipo de mensaje Web, debe eliminar la referencia Web del proyecto de BizTalk.  
  
 El proyecto de BizTalk crea un tipo de mensaje Web de solicitud y uno de respuesta para cada método Web del servicio Web agregado. Si el método Web es una operación unidireccional, BizTalk sólo crea un tipo de mensaje Web de solicitud. Un tipo de mensaje Web de solicitud contiene una parte de mensaje para cada parámetro de entrada del método Web. Un tipo de mensaje Web de respuesta contiene una parte de mensaje para el valor devuelto y otra para el parámetro de salida del método Web.  
  
 Dependiendo del parámetro del método Web (de entrada o salida), BizTalk crea un tipo de mensaje Web a partir de un tipo de esquema o de un tipo .NET primitivo. Si el parámetro del método Web es un tipo .NET primitivo, la parte de mensaje utiliza un tipo .NET primitivo. Si el parámetro del método Web es un tipo de esquema, BizTalk agrega el tipo de esquema al proyecto de BizTalk como un esquema de Reference.xsd. El esquema constituye la base de la parte de mensaje. Los esquemas Reference.xsd se encuentran en la carpeta de referencias Web.  
  
 No obstante, también puede crear tipos .NET de esquema y primitivos realizando una llamada a la clase .NET. Para obtener más información sobre cómo crear tipos de mensaje mediante una clase. NET, vea [construir mensajes en el código de usuario](../core/constructing-messages-in-user-code.md).  
  
 **Mensajes Web**  
  
 Los mensajes Web son los mensajes que los usuarios utilizan al consumir un servicio Web (o al llamarlo). Para agregar un mensaje Web a una orquestación, debe seguir el mismo procedimiento que al agregar un mensaje normal, con la excepción de que el tipo de mensaje se establece en uno de los tipos de mensajes Web que BizTalk ha creado al agregarse una referencia Web.  
  
 **Partes de mensaje**  
  
 Después de crear el mensaje Web, debe construirse las partes individuales de mensaje. Si su parte de mensaje utiliza un tipo .NET primitivo, se utiliza un **asignación de mensajes** forma. Si su parte de mensaje utiliza un tipo de esquema, se utiliza un **transformar** forma o **asignación de mensajes** forma. Para obtener más información, consulte [construir mensajes en el código de usuario](../core/constructing-messages-in-user-code.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo agregar mensajes Web](../core/how-to-add-web-messages.md)  
  
-   [Cómo determinar un tipo de parte de mensaje Web](../core/how-to-determine-a-web-message-part-type.md)  
  
-   [Cómo construir una parte de mensaje Web desde un tipo .NET primitivo](../core/how-to-construct-a-web-message-part-from-a-primitive-net-type.md)  
  
-   [Cómo construir una parte de mensaje Web desde un tipo de esquema](../core/how-to-construct-a-web-message-part-from-a-schema-type.md)  
  
-   [Cómo construir un mensaje Web sin partes de mensaje](../core/how-to-construct-a-web-message-with-no-message-parts.md)