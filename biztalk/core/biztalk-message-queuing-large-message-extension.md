---
title: Extensión de mensajes de BizTalk para Message Queue grandes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Message Queuing Large Message Extension
- utilities, BizTalk Message Queuing Large Message Extension
ms.assetid: 5d6892d3-fda8-41a3-8111-d28c11bd71fb
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb50b2e3270644a73dd3fb4f3b11af4da2dc0f72
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020514"
---
# <a name="biztalk-message-queuing-large-message-extension"></a>Extensión de mensajes de gran tamaño de Message Queue Server de BizTalk
Nativa de message Queue Server no puede procesar un mensaje cuyo cuerpo exceda los 4megabytes (MB). Sin embargo, Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] incluye un complemento para la versión nativa de Message Queue Server que permite procesar mensajes de más de 4 MB. Este complemento se entrega como el archivo Mqrtlarge.dll y expone el **MQSendLargeMessage** y **MQReceiveLargeMessage** aplicación interfaces de programación (API) y el modelo COM análogo. Estas funciones se implementan como message Queue Server de las API, **MQSendMessage** y **MQReceiveMessage** respectivamente.  

 Para participar en intercambios de mensajes de gran tamaño, el equipo de Message Queue Server debe tener instalado el archivo Mqrtlarge.dll, y la aplicación Message Queue Server debe utilizar las interfaces de API de complemento. En caso contrario, mensajes completos se fragmentarán.  

 **Ubicación en SDK**  

 \<*Ruta de instalación*\>\SDK\ Mqrtlarge.dll  

 **Inventario de archivos**  

 En la siguiente tabla se indica el archivo que emplea esta utilidad y se describe su finalidad.  


|    Archivos    |                                                                                                                                                                                              Descripción                                                                                                                                                                                               |
|---------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Mqrtlarge.dll | Una biblioteca de vínculos dinámicos Win32 que expone **MQSendLargeMessage** y **MQReceiveLargeMessage**.<br /><br /> Los archivos de encabezado se encuentran en el  *\<ruta de instalación\>* directorio \SDK\Include. **Nota:** debe instalar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en una versión de 64 bits de Windows para tener acceso a la versión de 64 bits de Mqrtlarge.dll. |

 **Usar esta utilidad**  

 Utilice el procedimiento siguiente para ejecutar el archivo Mqrtlarge.dll.  

### <a name="to-use-the-mqrtlargedll-file"></a>Para utilizar el archivo Mqrtlarge.dll  

1. > [!NOTE]
   >  Una solución MSMQ sin BizTalk Server, todavía puede funcionar correctamente MQRTLarge.dll. Sin embargo, esto no es una configuración recomendada que admita Microsoft, y pueden producirse resultados inesperados si se usa fuera del entorno de BizTalk Server.  

    Agregue el archivo Mqrtlarge.dll al equipo que no cuente con una instalación de BizTalk Server. Message Queue Server utiliza el archivo Mqrtlarge.dll para enviar mensajes a BizTalk Server o recibirlos desde éste.  

2. Para tener acceso a las API del archivo Mqrtlarge.dll, agregue una referencia al archivo Mqrtlarge.dll en las aplicaciones que envían mensajes a otros equipos o los reciben de éstos para el extremo de Message Queue Server de BizTalk.  

   **Comentarios**  

   Los mensajes de gran tamaño se envían a las colas estándar de Message Queue Server de BizTalk (también conocido como MSMQ). Sólo debería utilizar las API para mensajes de gran tamaño en dichas colas, aunque no es obligatorio.  

   Todavía puede usar **MQSendMessage** para enviar mensajes a una cola a la que se envían mensajes de gran tamaño. Del mismo modo, puede usar **MQReceiveMessage** para recibir mensajes de dichas colas, aunque no se recomienda ya que puede afectar el rendimiento de la **MQReceiveLargeMessage** API.  

   Para fines de recuperación, se recomienda utilizar **DEAD_LETTER** registro en diario.  

   **Fragmentación**  

   Generalmente, un mensaje de gran tamaño se fragmentará en diversos mensajes, cada uno con un tamaño inferior a 4 MB. Resulta importante saber que sólo se fragmenta el cuerpo. Las demás propiedades se envían con cada uno de los fragmentos.  

   El número de fragmentos se define según el tamaño del mensaje y del tamaño de los fragmentos. El tamaño de los fragmentos puede establecerse automáticamente mediante el archivo Mqrtlarge.dll o la parte correspondiente de Message Queue Server de BizTalk. Las aplicaciones también pueden especificar explícitamente el tamaño de los fragmentos.  

   Tenga en cuenta que la extensión de mensajes de gran tamaño requiere la extensión del mensaje mediante la adición de datos internos adicionales de un tamaño constante.  

   **PROPID_M_EXTENSION**  

   Puede usar el **PROPID_M_EXTENSION/PROPID_M_EXTENSION_LEN** propiedades para firmar el mensaje. La firma se compone de 40 bytes (B). En la tabla siguiente se muestran los fragmentos de la firma.  

|Descripción|Tamaño|  
|-----------------|----------|  
|Identificador único global (GUID) que indica que este mensaje se envió mediante **MQSendLargeMessage**|16 B|  
|GUID para el mensaje: Id. único por mensaje de gran tamaño que es común a todas las partes del mensaje|16 B|  
|Tamaño total mensaje de gran tamaño|4 B|  
|Número de parte|2 B|  
|Número de partes del mensaje|2 B|  

 La decisión de utilizar **PROPID_M_EXTENSION** tiene una consecuencia adicional. El puente MSMQ-MQSeries de Microsoft Host Integration Server utiliza esta propiedad para pasar una estructura que contiene propiedades que no están asignadas directamente entre mensajes de MQSeries y de Message Queue Server. Las aplicaciones que envían mensajes desde y hacia MQSeries, explícita o implícitamente, utilizan esta estructura. Message Queue Server puede generar confirmaciones cuando se ha recibido un mensaje desde una cola mediante una aplicación de recepción. Las confirmaciones se envían a una cola especificada por la aplicación de envío. En el caso de los mensajes de gran tamaño, esta confirmación se envía únicamente para la última parte del mensaje.  

## <a name="see-also"></a>Vea también  
 [Utilidades del SDK](../core/utilities-in-the-sdk.md)