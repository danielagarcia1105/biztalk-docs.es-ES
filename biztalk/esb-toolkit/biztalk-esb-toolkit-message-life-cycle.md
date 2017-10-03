---
title: Ciclo de vida del mensaje del Kit de herramientas de ESB de BizTalk | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c72fdbda-b9ef-431a-8322-56dba98e9eab
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2cb15a4c87a497a5595327b65019ca95b3201664
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-esb-toolkit-message-life-cycle"></a>Ciclo de vida del mensaje del Kit de herramientas de ESB de BizTalk
A continuación se muestra el ciclo de vida de un mensaje que se origina en un sistema externo y recorre el ESB para alcanzar su destino final:  
  
1.  En rampa recibe el mensaje. Dependiendo de la entidad o el cliente enviando, el mensaje puede o no puede contener un itinerario que define las instrucciones de procesamiento para el mensaje.  
  
2.  Componentes de canalización ESB copiar el itinerario (si está presente en el encabezado SOAP) en el contexto del mensaje como propiedades promocionadas. Si se recibe el mensaje sin un itinerario, un componente de canalización específica puede configurarse para seleccionar el itinerario adecuado de una base de datos, según el contenido del mensaje o un contexto y, a continuación, copie el itinerario en el contexto del mensaje. Durante la duración de la duración del mensaje, el itinerario se mantiene en el contexto del mensaje.  
  
3.  Mientras se encuentra en la canalización, se evalúa el itinerario y servicios itinerarios basada en mensajes pueden procesar el mensaje. Estos servicios itinerarios pueden transformar el mensaje o configuren extremos de enrutamientos.  
  
4.  El mensaje se publica en la base de datos de cuadro de mensaje de Microsoft BizTalk Server.  
  
5.  BizTalk Server evalúa las propiedades promocionadas de las colas y mensajes en el mensaje para uno o más suscriptores.  
  
6.  Los suscriptores de procesan el mensaje mediante los mecanismos típicos de BizTalk Server. Un suscriptor puede ser cualquiera de las siguientes acciones:  
  
    -   Puerto de recepción de una orquestación de BizTalk Server con un filtro configurado en un enlace directo  
  
    -   Un servidor de BizTalk dinámico puerto de envío, que también se conoce como ESB fuera de rampa. El itinerario determina cómo se configurará el puerto para continuar procesando el mensaje.  
  
 Como alternativa a un mensaje que llega a través de itinerario en rampa, orquestaciones de BizTalk Server también pueden publicar mensajes en el cuadro de mensaje para el procesamiento de ESB:  
  
1.  Se crea un mensaje dentro de una orquestación de BizTalk Server.  
  
2.  Contexto del mensaje se rellena con el itinerario ESB.  
  
3.  El mensaje se publica a través de un puerto de enlace directo a la base de datos de cuadro de mensaje.