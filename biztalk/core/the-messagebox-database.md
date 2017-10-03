---
title: La base de datos de cuadro de mensajes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, MessageBox database
- messages, suspended messages
- MessageBox database, messages
- MessageBox database, about MessageBox database
- MessageBox database, suspended messages
- suspended messages
- MessageBox database
- suspended messages, MessageBox database
ms.assetid: f89eb02c-1b83-4127-8a91-e78fb4a1f96e
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: edf1fb3a89d6e08f6a0183a3242c53c4be890e60
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-messagebox-database"></a>La base de datos de cuadro de mensajes
El núcleo del motor de suscripción o publicación de Microsoft BizTalk Server es la base de datos de cuadro de mensajes. El cuadro de mensajes está formada por dos componentes: una o más bases de datos de Microsoft SQL Server y el agente de mensajería. La base de datos de SQL Server proporciona el almacén de persistencia para numerosos componentes, entre los que se incluyen, entre otros, mensajes, partes de mensaje, propiedades de mensaje, suscripciones, estados de orquestación, datos de seguimiento y colas de host para el enrutamiento. El grupo de BizTalk Server puede poseer una o varias bases de datos de cuadro de mensajes, en las que se van a publicar mensajes y desde las que los suscriptores de esos mensajes extraerán mensajes.  
  
 La base de datos proporciona algunos de los aspectos lógicos relacionados con el enrutamiento de mensajes y la cumplimentación de suscripciones. No obstante, el agente de mensaje es el componente que encapsula y abstrae el componente de base de datos. Además, constituye la interfaz que BizTalk Server utiliza para interactuar con el cuadro de mensajes. El agente de mensaje es un componente COM (Modelo de objetos componentes) que proporciona interfaces para publicar mensajes, suscribirse a los mensajes, recuperarlos, etc. Esta interfaz constituye el único mecanismo que utilizan los demás componentes de BizTalk Server, entre los que se incluyen el marco de trabajo de los adaptadores y las orquestaciones, para interactuar con el cuadro de mensajes  
  
## <a name="the-messagebox-and-the-message"></a>El cuadro de mensajes y el mensaje  
 Una suscripción de base de datos de cuadro de mensajes es un conjunto formado por información de servicio e información establecida. La información establecida (o predicado) son los criterios que debe cumplir todo mensaje. La información de servicio es la acción que se emprende con el mensaje que cumple los criterios. Todos estos datos se almacenan en un conjunto de tablas que llaman al motor de orquestaciones y de mensajería.  
  
 Cuando BizTalk Server recibe un mensaje, lo procesa en una canalización y lo coloca en la base de datos de cuadro de mensajes. El mensaje entrante tiene un contexto. El contexto de mensaje hace referencia a un conjunto de propiedades que se asocian al mensaje. Los tres tipos de propiedades de contexto de mensaje son los siguientes:  
  
-   Propiedades escritas simples  
  
-   Propiedades promocionadas  
  
-   Propiedades de predicado  
  
 Los propiedades de mensaje promocionadas y de predicado reflejan el proceso empresarial que se suscribe a este mensaje. Señala, además, si el proceso empresarial dispone de los permisos necesarios para recibir el mensaje.  
  
 Si un proceso empresarial se suscribe al mensaje, la base de datos de cuadro de mensajes envía el mensaje al proceso empresarial. Cuando el proceso empresarial recibe el mensaje, lo procesa en una instancia de host disponible. Después de procesar el mensaje, si el proceso empresarial se suscribe a una canalización o puerto de envío, el proceso empresarial envía un mensaje devuelto a la base de datos de cuadro de mensajes.  
  
 En cada host de BizTalk, el cuadro de mensajes asociado posee una cola de trabajo y una cola de suspensión. Además, todas las bases de datos de cuadro de mensajes contienen un conjunto de tablas para los estados estáticos, estados dinámicos y estados de instancias. Para obtener información acerca de los Hosts de BizTalk, consulte [entidades](../core/entities.md).  
  
> [!IMPORTANT]
>  Si un host pasa a estar no disponible (por ejemplo, la base de datos de cuadro de mensajes que recibe mensajes del host pasa a estar no disponible), todas las bases de datos de cuadro de mensajes se establecen también como no disponibles.  
  
 Cree la primera base de datos cuando ejecute el Asistente para configuración. La base de datos de cuadro de mensajes configurada se convierte en la base de datos de cuadro de mensajes principal. La base de datos de cuadro de mensajes principal evalúa y enruta las suscripciones a todas las demás bases de datos de cuadro de mensajes del entorno de BizTalk Server. Para obtener información acerca de cómo mejorar el rendimiento de la base de datos maestra, vea [administrar bases de datos de cuadro de mensajes](../core/managing-messagebox-databases.md).  
  
> [!IMPORTANT]
>  Debe utilizar la organización por clústeres de SQL Server para proporcionar protección de conmutación por error a las bases de datos de cuadro de mensajes.  
  
## <a name="suspended-messages-in-the-messagebox-database"></a>Mensajes suspendidos de la base de datos de cuadro de mensajes  
 BizTalk Server almacena mensajes asociados con canalizaciones suspendidas en la base de datos de cuadro de mensajes. Si se produce un error en la canalización, BizTalk Server suspende la instancia de un mensaje. Existen dos tipos de instancias de servicio suspendidas:  
  
-   Instancias suspendidas que se pueden reanudar.  
  
-   Instancias suspendidas que no se pueden reanudar. Por ejemplo, si una instancia está dañada.  
  
 En función de la causa de la suspensión, puede que sea posible reanudar servicios suspendidos por BizTalk Server. Por ejemplo, si una orquestación activa una forma Suspender o si un transporte no puede entregar un mensaje, BizTalk Server no quita automáticamente las instancias suspendidas que no se pueden reanudar de la base de datos de cuadro de mensaje. Puede guardar una instancia de servicio en disco antes de quitarla de la cola de suspensión.  
  
 Para obtener información acerca de la copia de seguridad de bases de datos de cuadro de mensajes, vea [copia de seguridad y restaurar bases de datos de servidor de BizTalk](../core/backing-up-and-restoring-biztalk-server.md).  
  
## <a name="see-also"></a>Vea también  
 [El motor de mensajería](../core/the-messaging-engine.md)