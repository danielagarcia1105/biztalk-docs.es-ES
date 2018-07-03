---
title: Ciclo de vida del mensaje del Kit de herramientas de ESB de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c72fdbda-b9ef-431a-8322-56dba98e9eab
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f93a4ee2024fcb9cfaf65e7cf33922784a47030
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979141"
---
# <a name="biztalk-esb-toolkit-message-life-cycle"></a>Ciclo de vida del mensaje del Kit de herramientas de BizTalk ESB
Este es el ciclo de vida de un mensaje que se origina en un sistema externo y recorre el ESB para llegar a su destino final:  

1. Una rampa recibe el mensaje. Dependiendo de la entidad de envío o cliente, el mensaje puede o no puede contener un itinerario que define las instrucciones de procesamiento del mensaje.  

2. Los componentes de canalización ESB copie el itinerario (si está presente en el encabezado SOAP) en el contexto del mensaje como propiedades promocionadas. Si el mensaje se recibe sin un itinerario, se puede configurar un componente de canalización específica para seleccionar el itinerario adecuado de una base de datos, según el contexto, o el contenido del mensaje y, a continuación, copie el itinerario en el contexto del mensaje. Durante la duración de la duración del mensaje, se mantiene el itinerario dentro del contexto de mensaje.  

3. Mientras sigue en la canalización, se evalúa el itinerario y servicios de itinerario de mensaje pueden procesar el mensaje. Estos servicios de itinerario podrán transformar el mensaje o configuren extremos de enrutamientos.  

4. El mensaje se publica en la base de datos de cuadro de mensaje de Microsoft BizTalk Server.  

5. BizTalk Server evalúa las propiedades promocionadas del mensaje y las colas en el mensaje para uno o varios suscriptores.  

6. Los suscriptores de procesan el mensaje mediante los mecanismos típicos de BizTalk Server. Un suscriptor puede ser cualquiera de las siguientes acciones:  

   -   Puerto de recepción de una orquestación de BizTalk Server con un filtro configurado en un enlace directo  

   -   Un servidor BizTalk Server dinámica puerto de envío, que también se conoce como un ESB fuera de rampa. El itinerario determina cómo se configurará el puerto para continuar procesando el mensaje.  

   Como alternativa a un mensaje que llega a través de una rampa de itinerario, orquestaciones de BizTalk Server también pueden publicar mensajes en el cuadro de mensaje para el procesamiento de ESB:  

7. Se crea un mensaje dentro de una orquestación de BizTalk Server.  

8. Contexto del mensaje se rellena con los itinerarios ESB.  

9. El mensaje se publica a través de un puerto de enlace directo a la base de datos de cuadro de mensaje.
