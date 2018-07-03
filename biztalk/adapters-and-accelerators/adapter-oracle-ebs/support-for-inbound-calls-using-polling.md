---
title: Soporte técnico para las llamadas entrantes mediante sondeo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae02a93a-808f-4774-a2c4-efdf39a4d49a
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 868e56730f21235e3f73f6ab91a463ea4589bafd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984669"
---
# <a name="support-for-inbound-calls-using-polling"></a>Soporte técnico para las llamadas entrantes mediante sondeo
El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] permite que los programas de cliente recibir mensajes de Oracle E-Business Suite que les informa de los cambios a los datos de Oracle E-Business Suite. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] admite la recepción de mensajes "basados en sondeos" en la que el adaptador ejecuta una instrucción SQL especificada, el procedimiento almacenado, función o un procedimiento dentro de un paquete, recupera los datos y proporciona el resultado al cliente a intervalos regulares de tiempo.  

> [!NOTE]
>  También puede establecer el contexto de las aplicaciones para la operación de sondeo en [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Es obligatorio para establecer el contexto de las aplicaciones para la operación de sondeo, si la operación se realiza en una tabla de interfaz o la vista de interfaz. Para obtener información sobre el contexto de las aplicaciones y cómo configurarlo, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  

 Una operación de sondeo típico mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] implica lo siguiente:  

1. Deben especificar los clientes del adaptador `Polling` como la operación de entrada en el **InboundOperationType** enlaza la propiedad. El valor predeterminado para esta propiedad de enlace es **sondeo**.  

2. Los clientes del adaptador deben especificar una instrucción SELECT para la **PolledDataAvailableStatement** enlaza la propiedad para determinar si hay datos disponibles para el sondeo. Si la primera columna de la primera fila del primer conjunto de resultados devuelto en la ejecución de esta instrucción contiene un valor entero positivo, hay fecha disponible para el sondeo.  

3. Los clientes del adaptador deben especificar un intervalo de sondeo para el **PollingInterval** enlace de propiedad para definir el intervalo en segundos en el que la instrucción especificada en el **PolledDataAvailableStatement** propiedad de enlace se ejecuta. Al final de cada intervalo de sondeo, se ejecuta la instrucción disponibles datos extraídos y se devuelve el conjunto de resultados.  

4. Los clientes del adaptador deben especificar una instrucción SELECT o un procedimiento almacenado para el **PollingInput** enlaza la propiedad. Si desea sondear una tabla o vista, debe especificar una instrucción SELECT para esta propiedad de enlace. Si desea sondear mediante un procedimiento almacenado, debe especificar el mensaje de solicitud completo para esta propiedad de enlace.  

    La instrucción en el **PollingInput** enlaza la propiedad solo se ejecuta si hay datos disponibles para el sondeo, que viene determinado por la **PolledDataAvailableStatement** enlazar la propiedad en el paso 2.  

5. Los clientes del adaptador deben especificar una acción para la operación de sondeo en el **PollingAction** enlaza la propiedad. La acción de sondeo para una operación específica se determina a partir de los metadatos generados para la operación utilizando el complemento Consume Adapter Service.  

6. Los clientes del adaptador pueden usar el **PollWhileDataFound** enlaza la propiedad para omitir el intervalo de sondeo y datos, un sondeo continuo como y cuando esté disponible.  

   > [!IMPORTANT]
   >  Si establece el valor de la **PollWhileDataFound** propiedad de enlace en True, los clientes del adaptador sondean continuamente los datos de Oracle y en el proceso de abrir y cerrar las conexiones a la base de datos de Oracle en un bucle. Como la velocidad a la que se abren las conexiones por ODP.NET es mayor que las conexiones que se va a cerrar, las conexiones agotarse más tarde y se produce una excepción. Como solución alternativa, asegúrese de que el valor de la **UseOracleConnectionPool** está establecida en True, y un valor adecuado que se menciona en la **IncrPoolSize** enlaza la propiedad para controlar el número de conexiones que se abren los clientes del adaptador.  

7. Los clientes del adaptador pueden especificar una instrucción posterior a la encuesta, un bloque de PL/SQL de Oracle para el **PostPollStatement** enlaza la propiedad. La instrucción especificada en esta propiedad de enlace se ejecuta después de la instrucción especificada en el **PollingInput** propiedad de enlace se ejecuta.  

   > [!NOTE]
   >  El adaptador ejecuta la instrucción especificada en el **PollingInput** y **PostPollStatement** propiedades de enlace en una transacción. Para obtener más información acerca de las transacciones en el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], consulte [¿cómo las transacciones de adaptador controlar?](https://msdn.microsoft.com/library/dd788428.aspx).  

   El adaptador suprime las respuestas de sondeo vacío procedentes de Oracle E-Business Suite.  

   La ilustración siguiente proporciona información sobre el flujo de trabajo de sondeo en [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Se muestran dos escenarios para el flujo de trabajo de sondeo:  

8. Cuando el valor de la **PollWhileDataFound** está establecido en "False" (valor predeterminado).  

9. Cuando el valor de la **PollWhileDataFound** está establecido en "True".  

   ![Escenario de sondeo &#40;PollWhileDataFound&#61;False&#41;](../../adapters-and-accelerators/adapter-oracle-ebs/media/e5f00f4c-cc76-4e8b-9991-b4471f9d4865.gif "e5f00f4c-cc76-4e8b-9991-b4471f9d4865") ![escenario de sondeo &#40;PollWhileDataFound &#61; True&#41; ] (../../adapters-and-accelerators/adapter-oracle-ebs/media/ebecf64c-a770-4525-9c75-62fdb71e1fb1.gif "ebecf64c-a770-4525-9c75-62fdb71e1fb1")  

## <a name="differences-between-polling-and-notification"></a>Diferencias entre el sondeo y la notificación  
 Aunque el sondeo y la notificación son ambas operaciones de entrada e informar a los clientes del adaptador acerca de los cambios de datos en la base de datos de Oracle, en la tabla siguiente se enumera algunas diferencias entre los dos. Las siguientes diferencias le ayudará a decidirse por una operación según sus requisitos:  


|                                                                                                                                                                                                                                                      Sondeo                                                                                                                                                                                                                                                      |                                                                                                                              Notification                                                                                                                               |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                                                                                                   Sondeo es compatible con todas las versiones de la base de datos de Oracle que son compatibles con el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].                                                                                                                                                                    |                                                                                               Notificación solo se admite para las versiones de la base de datos de Oracle 10.2 y versiones posteriores.                                                                                               |
| Puede configurar el intervalo de sondeo para comprobar los datos disponibles para el sondeo a intervalos regulares o de forma inmediata como y cuando los datos están disponibles. **Sugerencia:** sondeo puede ofrecerle un mejor rendimiento en escenarios donde los cambios de datos se producen de forma continua, y no desea recibir una notificación de cada cambio como y cuando ocurre. En su lugar, especifique un intervalo de sondeo después del cual desea recibir una notificación de todos los cambios que se han producido desde el último cambio de notificación. |                                                                                                          La notificación de cambio de datos siempre es instantánea.                                                                                                          |
|                                                                                                                                         Sondeo es iniciado por el adaptador. El adaptador ejecuta una instrucción SQL para validar si los datos está disponibles para el sondeo y, a continuación, inicia el sondeo al ejecutar la instrucción de sondeo si algunos datos están disponibles para el sondeo.                                                                                                                                         | Se inicia la notificación de la base de datos de Oracle. La instrucción de notificación emitida el adaptador simplemente indica a la base de datos para iniciar la notificación en caso de que hay un cambio en el conjunto de resultados de la instrucción. Notificación es una característica de la base de datos de Oracle. |
|                                                                                                                                                                                                                 Puede usar la instrucción de sondeo para leer o actualizar datos en la base de datos de Oracle.                                                                                                                                                                                                                  |                                                                                             Puede usar la instrucción de notificación solo lea datos de una base de datos de Oracle.                                                                                             |
|                                                                                                                                                                                                                            Sondeo le informa sobre los datos reales que han cambiado.                                                                                                                                                                                                                            |                                                                                   Notificación informa solo sobre el tipo de cambio en los datos, como Insert, Update y Delete.                                                                                    |

 Para obtener más información acerca de:  

- Las propiedades de enlace relacionadas con el sondeo, consulte [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  

- Recepción de mensajes basados en sondeos con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], consulte [sondeo Oracle E-Business Suite mediante BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-biztalk-server.md).  

## <a name="see-also"></a>Vea también  
 [¿Qué operaciones pueden ser realizadas utilizando el adaptador?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)