---
title: Seguimiento de eventos empresariales asíncronos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, BAM
- events, tracking [BAM]
- BAM, event tracking
- BAM, performance
ms.assetid: 6d51fadf-b329-4536-9618-d982d9c17882
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7191d9b0be94b4b089a91e78dd526867171c68a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230476"
---
# <a name="asynchronous-business-event-tracking"></a>Seguimiento asíncrono de eventos empresariales
Asincrónica (con `BufferedEventStream`)-este modelo ofrece importantes mejoras de rendimiento. Utiliza una API parecida a la del modelo sincrónico, que utiliza solo un constructor diferente. En lugar de insertar los datos en la base de datos de importación principal, BufferedEventStream acumula los datos de eventos en la memoria en forma binaria y luego los inserta como un registro de tabla único en la base de datos temporal (cuadro de mensajes). El servicio de bus de eventos BAM lee los datos que BizTalk tiene en cola en la base de datos de cuadro de mensajes y los importa a la base de datos de importación principal.  
  
 Para configurar BAM para operaciones asíncronas, el servicio de bus de eventos y la aplicación que realiza la llamada (p.ej. host de orquestación) se deben ejecutar en equipos diferentes. De esta manera, la aplicación que realiza la llamada puede deshacerse inmediatamente de los datos de eventos que se van a procesar con la CPU en un equipo diferente.  
  
 Esta topología de BAM también es coherente con las transacciones. No se podrán obtener datos de BAM para transacciones que se deshacen en la aplicación que realiza la llamada, ya que el servicio de bus de eventos solo lee los datos confirmados de la base de datos de cuadro de mensajes. Se mostrarán los datos de BAM para las transacciones que se confirmaron para consultas y agregaciones con poca latencia.  
  
 Si se produce un error, el servicio de bus de eventos volverá a intentarlo varias veces, utilizará tiempos de espera, bloqueará la lógica de recuperación, etc. Sin embargo, si los datos están en un formato no válido, acabarán en tablas especiales. Se produce un evento en el registro de eventos para indicar esta condición. Este posible punto de error dificulta más la administración del sistema.  
  
 Utilizar el enfoque asíncrono desde el código es normalmente tan fácil como sustituir DirectEventStream por BufferedEventStream, y pasar la cadena de conexión a la base de datos de cuadro de mensajes del constructor, en lugar de a la base de datos de importación principal de BAM.  
  
 Tenga en cuenta las siguientes directrices en relación al seguimiento de eventos empresariales asíncronos en su código:  
  
-   Utilice siempre una continuación cuando la actividad abarque varias aplicaciones y envíe los datos de forma asíncrona a BAM, incluso si propaga ActivityID a todos los componentes. En este caso, utilice un ActivityID diferente en cada aplicación, anexándole un prefijo de cadena única (p.ej. Nombre de aplicación). Este proceso resulta necesario porque puede que los datos de las distintas aplicaciones lleguen a BAM de forma aleatoria, y que BAM tenga que administrar los eventos desordenados para garantizar resultados correctos de la consulta y de la agregación.  
  
-   Los métodos habituales de supervisión de eventos (p.ej. eventos con correspondencia imprecisa COM+ o eventos de WMI) no se pueden aplicar a BAM porque los datos de eventos son independientes de la transacción. Por ejemplo, puede que parezca que recibió 10 pedidos por un total de 10.000 $ mientras que solo había un pedido de compra entrante de 1.000 $, pero se produjo un error 10 veces al intentar guardarlo en la base de datos.  
  
## <a name="see-also"></a>Vea también  

 [Seguimiento de eventos empresariales sincrónico](../core/synchronous-business-event-tracking.md)