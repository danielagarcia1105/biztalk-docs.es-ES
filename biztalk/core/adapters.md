---
title: Adaptadores | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters, receive adapters
- adapters
- send adapters
- adapters, about adapters
- send adapters, about send adapters
- receive adapters, about receive adapters
- adapters, adapter framework
- receive adapters
- adapters, send adapters
ms.assetid: 7803a806-3396-4662-877f-eae11cb5e3e4
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a7f58a9d67b9702cfbb7b21788f751717ac61e4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="adapters"></a>adaptadores
Para intercambiar mensajes con sistemas, aplicaciones y entidades externas, Microsoft BizTalk Server utiliza el concepto de un adaptador. *Adaptadores* son COM o. Componentes basados en red que transfieren mensajes desde y hacia extremos empresariales (como sistemas de archivos, bases de datos y aplicaciones empresariales personalizadas) mediante distintos protocolos de comunicación.  
  
 BizTalk Server utiliza los adaptadores para intercambiar mensajes con entidades externas en operaciones de envío y recepción.  
  
-   Las operaciones de envío (o en el lado de envío) se producen cuando BizTalk Server envía información a una entidad externa mediante los protocolos compatibles con el adaptador.  
  
-   Las operaciones de recepción (o en el lado de recepción) se producen cuando el adaptador recibe información de una entidad externa y la pasa al motor de mensajería de BizTalk Server.  
  
## <a name="the-adapter-framework"></a>marco de trabajo del adaptador  
 En la siguiente ilustración se muestra cómo funcionan el adaptador y el marco de trabajo de adaptadores de forma conjunta para conectar la aplicación con BizTalk Server.  
  
1.  Los datos se reciben a través de una ubicación de recepción que escucha mensajes de un protocolo concreto en una dirección específica. La ubicación de recepción está asociada con un adaptador y una canalización de recepción. Puede configurar tanto el adaptador como los componentes de canalización para que realicen cierta lógica en los mensajes que tienen un protocolo predeterminado.  
  
2.  Tras recibir el mensaje la ubicación de recepción, se envía éste al adaptador, que crea un mensaje nuevo de BizTalk Server, agrega la secuencia de datos al mensaje (normalmente al cuerpo del mensaje), agrega cualquier metadato perteneciente al extremo en el que se han recibido los datos y envía dicho mensaje al motor de mensajería.  
  
3.  El motor de mensajería envía el mensaje a la canalización de recepción donde los datos se transforman en XML, se autentica el remitente del mensaje, se descifra y se valida el código XML.  
  
4.  El motor de mensajería publica el mensaje en el Cuadro de mensajes. El Cuadro de mensajes es una tabla de Microsoft SQL Server que contiene mensajes para procesarlos. Tanto las orquestaciones como los puertos de envío se pueden suscribir al Cuadro de mensajes.  
  
5.  El motor de mensajería envía el mensaje a una orquestación o a un suscriptor de puerto de envío según si las propiedades de contexto del mensaje coinciden con las especificaciones establecidas en el filtro del suscriptor.  
  
6.  Si una orquestación es el suscriptor, procesa el mensaje y lo envía mediante un puerto de envío. Una vez que el puerto de envío lo tiene, o si se trata del único suscriptor, el mensaje pasa a través de la canalización de envío a un adaptador de envío antes de transmitirse a través de la conexión.  
  
 marco de trabajo del adaptador  
  
 ![El marco de trabajo de adaptador](../core/media/ebiz-sdk-adpttoday.gif "ebiz_sdk_adpttoday")  
  
## <a name="receive-adapters"></a>Adaptadores de recepción  
 Los adaptadores de recepción son los responsables de la creación de un mensaje nuevo de BizTalk Server al adjuntar la secuencia de origen de datos o red al cuerpo del mensaje. También agregan todos los metadatos adecuados al extremo en el que se recibieron los datos y, después, envían el mensaje al motor de mensajería.  
  
 El adaptador elimina los datos del extremo de recepción o envía el mensaje de confirmación correspondiente al cliente indicando que se han aceptado los datos en BizTalk Server.  
  
## <a name="send-adapters"></a>Adaptadores de envío  
 Los adaptadores de envío son los responsable del envío de un mensaje de BizTalk Server al extremo especificado mediante su protocolo de transporte específico.  
  
 Para obtener más información acerca de los adaptadores, vea la estructura de un adaptador y escribir adaptadores personalizados, [desarrollar adaptadores personalizados](../core/developing-custom-adapters.md).  
  
## <a name="see-also"></a>Vea también  
 [Artefactos](../core/artifacts.md)