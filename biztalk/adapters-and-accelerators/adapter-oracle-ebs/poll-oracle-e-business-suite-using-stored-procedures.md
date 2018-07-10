---
title: Sondear Oracle E-Business Suite mediante procedimientos almacenados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9e89dfe-f33a-436b-94c6-be78e84d5efd
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0301a571fba8e768052fa9caaf1465abd8aa162
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990917"
---
# <a name="poll-oracle-e-business-suite-using-stored-procedures"></a>Sondear Oracle E-Business Suite mediante procedimientos almacenados
Puede configurar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para recibir mensajes de cambio de datos periódica mediante procedimientos almacenados que para sondear continuamente la base de datos de Oracle. Puede especificar un procedimiento almacenado como una instrucción de sondeo que el adaptador se ejecuta periódicamente para sondear la base de datos de Oracle.  

 Para habilitar el sondeo, debe especificar que ciertas propiedades de enlace en el WCF-Custom o WCF-OracleEBS de puerto de recepción.  Para obtener más información acerca de cómo el adaptador admite el sondeo, consulte [compatibilidad con entrada de sondeo utilizando llamadas](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md). Para obtener información acerca de la estructura del mensaje SOAP para las operaciones de sondeo, consulte [esquemas de mensaje para las operaciones de sondeo](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-polling-operations1.md).  

## <a name="configuring-a-polling-operation-with-oracle-e-business-adapter-binding-properties"></a>Configuración de una operación de sondeo con el adaptador de Oracle E-Business propiedades de enlace  
 La siguiente tabla resume el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] propiedades que usan para configurar el adaptador para recibir mensajes de cambio de datos de enlace. Debe especificar el puerto de recepción de estas propiedades de enlace al configurar el WCF-Custom o WCF-OracleEBS la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  


|         Propiedad de enlace         |                                                                                                                                                                                                                                                                       Descripción                                                                                                                                                                                                                                                                       |
|----------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     **InboundOperationType**     |                                                                                                                                                                                                                   Especifica si desea realizar un **sondeo** o **notificación** operación entrante. El valor predeterminado es **sondeo**.                                                                                                                                                                                                                    |
| **PolledDataAvailableStatement** |                                                                                                                                                       Especifica la instrucción SQL que ejecuta el adaptador para determinar si los datos están disponibles para el sondeo. Solo si hay un registro, el procedimiento almacenado que especificó para el **PollingInput** se ejecutará el enlace de propiedad.                                                                                                                                                       |
|       **PollingInterval**        |                                           Especifica el intervalo, en segundos, en el que el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ejecuta la instrucción especificada para el **PolledDataAvailableStatement** enlaza la propiedad. El valor predeterminado es 30 segundos. El intervalo de sondeo determina el intervalo de tiempo entre sondeos sucesivos. Si la instrucción se ejecuta en el intervalo especificado, el adaptador se suspende durante el tiempo restante en el intervalo.                                            |
|         **PollingInput**         | Especifica la instrucción de sondeo. Para sondear con un procedimiento almacenado, debe especificar el mensaje de solicitud completo para esta propiedad de enlace. El mensaje de solicitud debe ser el mismo que enviar al adaptador para invocar el procedimiento almacenado como una operación de salida. El valor predeterminado es null.<br /><br /> Debe especificar un valor para **PollingInput** enlace de propiedad para habilitar el sondeo. Se ejecuta la instrucción de sondeo solo si hay datos disponibles para el sondeo, que viene determinado por la **PolledDataAvailableStatement** enlaza la propiedad. |
|        **PollingAction**         |                                                                                                                                               Especifica la acción para la operación de sondeo. Puede determinar la acción de sondeo para una operación específica de los metadatos que se genera para la operación mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].                                                                                                                                               |
|      **PostPollStatement**       |                                                                                                                                                                                                            Especifica un bloque de instrucciones que se ejecuta después de la instrucción especificada por el **PollingInput** propiedad de enlace se ejecuta.                                                                                                                                                                                                             |
|      **PollWhileDataFound**      |                                                                               Especifica si el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] pasa por alto el intervalo de sondeo y la instrucción de sondeo, se ejecuta continuamente si hay datos disponibles en la tabla que se sondea. Si no hay datos disponibles en la tabla, el adaptador vuelve para ejecutar la instrucción de sondeo en el intervalo de sondeo especificado. El valor predeterminado es False.                                                                               |

 Para obtener una descripción más completa de estas propiedades, vea [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md). Para obtener una descripción completa de cómo usar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para sondear la base de datos de Oracle, lea las secciones siguientes.  

## <a name="how-this-topic-demonstrates-polling"></a>Cómo este tema muestra el sondeo  
 En este tema, para demostrar cómo el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] admite la recepción de datos cambiar mensajes mediante procedimientos almacenados, crear un proyecto de BizTalk y genere el esquema para el procedimiento almacenado que desea utilizar para sondear la base de datos de Oracle. En este tema, se usa el procedimiento almacenado de GET_ACTIVITYS para sondear la tabla ACCOUNTACTIVITY. Este procedimiento almacenado está disponible con el paquete ACCOUNT_PKG. Puede ejecutar los scripts SQL que se proporciona con los ejemplos para crear estos objetos en la base de datos.  

> [!NOTE]
>  La orquestación en este sondeos tema el ACCOUNTACTIVITY de tabla, que es una tabla de base de datos creada mediante la ejecución de los scripts proporcionados con los ejemplos. Debe realizar procedimientos similares, como se describe en este tema para sondear en cualquier otra tabla, incluidas las tablas de interfaz.  

 Para demostrar una operación de sondeo, llevamos a cabo lo siguiente:  

-   Especifique una instrucción SELECT para la **PolledDataAvailableStatement** enlaza la propiedad para determinar donde la tabla sondea (ACCOUNTACTIVITY) tiene los datos. En este ejemplo, puede establecer esta propiedad de enlace como:  

    ```  
    SELECT COUNT (*) FROM ACCOUNTACTIVITY  
    ```  

     Esto garantiza que el adaptador ejecuta la instrucción de sondeo solo cuando la tabla ACCOUNTACTIVITY tiene algunos registros.  

-   Ejecutar un procedimiento almacenado, GET_ACTIVITYS, proporcionando el mensaje de solicitud como parte de la **PollingInput** enlaza la propiedad. Este procedimiento almacenado recuperará todas las filas de la tabla ACCOUNTACTIVITY y obtendrá un mensaje de respuesta desde el adaptador.  

-   EJECUTAR un bloque de PL/SQL como parte de la **PostPollStatement** enlaza la propiedad. Esta instrucción moverá todos los datos de tabla ACCOUNTACTIVITY a otra tabla en la base de datos. Una vez que esto ocurre, la próxima vez **PollingInput** será ejecuta, no capturará todos los datos y, por tanto, el procedimiento almacenado de GET_ACTIVITYS devolverá un mensaje de respuesta vacío.  

-   Hasta que se agregan más datos a la tabla ACCOUNTACTIVITY, se seguirá pudiendo obtener mensajes de respuesta vacío. Por lo tanto, debe volver a llenar la tabla ACCOUNTACTIVITY con nuevos registros. Puede hacerlo ejecutando el script more_activity_data.sql proporcionado con los ejemplos. Después de ejecutar este script, la siguiente operación de sondeo capturará los nuevos registros que se insertan en la tabla.  

## <a name="how-to-receive-data-change-messages-from-oracle"></a>Cómo recibir mensajes de cambio de datos de Oracle  
 Realizar una operación en la base de datos de Oracle mediante [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] implica las siguientes tareas de procedimientos se describe en [bloques de creación para crear aplicaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md). Para configurar el adaptador para sondear la base de datos de Oracle mediante un procedimiento almacenado, estas tareas son:  

1. Cree un proyecto de BizTalk y genere el esquema para el procedimiento almacenado que desea usar para el sondeo.  

2. Cree un mensaje en el proyecto de BizTalk para recibir mensajes de la base de datos de Oracle.  

3. Crear una orquestación para recibir mensajes de la base de datos de Oracle y guardarlos en una carpeta.  

4. Compile e implemente el proyecto de BizTalk.  

5. Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  

   > [!IMPORTANT]
   >  Para escenarios de sondeo de entrada siempre debe configurar un puerto de recepción unidireccional. Bidireccional recibir los puertos no se admiten operaciones de entrada.  

6. Inicie la aplicación de BizTalk.  

   Este tema proporciona instrucciones para realizar estas tareas.  

## <a name="sample-based-on-this-topic"></a>Ejemplo basado en este tema.  
 Un ejemplo, PollingUsingStoredProc, basado en este tema también se proporciona con BizTalk Adapter Pack. Para obtener más información, consulte [ejemplos](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).  

## <a name="generating-schema"></a>Generar el esquema  
 Debe generar el esquema para la operación GET_ACTIVITYS. Realizar las tareas siguientes al generar el esquema mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  

- Seleccione el tipo de contrato **(operación de entrada) de servicio**.  

- Genere el esquema para el **GET_ACTIVITYS** procedimiento.  

  Para obtener más información acerca de cómo generar un esquema, vea [examinar, buscar y obtener metadatos para operaciones de Oracle E-Business](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md).  

## <a name="defining-messages-and-message-types"></a>Definición de los mensajes y tipos de mensaje  
 El esquema que ha generado anteriormente describe los "tipos" necesarios para los mensajes en la orquestación. Un mensaje suele ser una variable, el tipo para el que está definido por el esquema correspondiente. Una vez que se genera el esquema, debe vincularlo a los mensajes desde la vista de orquestación de BizTalk del proyecto.  

 Este tema, debe crear un mensaje para recibir mensajes de Oracle.  

 Realice los pasos siguientes para crear mensajes y vincularlos a esquema.  

#### <a name="to-create-messages-and-link-to-schema"></a>Para crear mensajes y vínculo a esquema  

1. Agregar una orquestación al proyecto de BizTalk. En el Explorador de soluciones, haga clic en el nombre del proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**. Escriba un nombre para la orquestación de BizTalk y, a continuación, haga clic en **agregar**.  

2. Abra la ventana Vista orquestación del proyecto de BizTalk, si aún no está abierto. Haga clic en **vista**, apunte a **Other Windows**y, a continuación, haga clic en **Vista orquestación**.  

3. En el **Vista orquestación**, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  

4. Haga clic en el mensaje recién creado y, a continuación, seleccione **ventana propiedades**.  

5. En el **propiedades** panel **Message_1**, realice lo siguiente:  

   |Use|Para|  
   |--------------|----------------|  
   |Identificador|Tipo **recibir**.|  
   |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y seleccione *Polling.OracleEBSBindingSchema*, donde *sondeo* es el nombre de su proyecto de BizTalk. *OracleEBSBindingSchema* es el esquema de respuesta generado para el **GET_ACTIVITYS** procedimiento almacenado.<br /><br /> **Importante:** porque el sondeo es una operación unidireccional, el esquema generado por el adaptador no tiene un nodo de respuesta y, por tanto, hay solo un nodo raíz en el esquema. Si utiliza estos esquemas para un tipo de mensaje, debe identificar el esquema mediante el nombre del esquema generado.<br /><br /> Por ejemplo, si crea un esquema para una operación bidireccional, los nodos en el esquema de archivo con un nombre `OracleEBSBindingSchema` puede ser similar a "Solicitud" y "Respuesta". Si desea crear un mensaje en la orquestación que se asigna al esquema de la solicitud, puede identificar el esquema en la lista, busque `OracleEBSBindingSchema.Request`. Sin embargo, en el caso de la operación de sondeo, dado que el único nodo es "Sondeo", no es fácil identificar el esquema que desee realizar la asignación porque no se muestran los esquemas con nodos únicos como \<schemafilename\>.\< rootnodename\>. En su lugar, estos esquemas se enumeran por sólo el nombre de archivo. En tal caso, la única manera de identificar el esquema es por el nombre de archivo de esquema, por ejemplo, OracleEBSBindingSchema.|  

    El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] genera un esquema para las operaciones entrantes y salientes para el GET_ACTIVITYS de procedimiento almacenan. Debe usar el esquema para que la operación de entrada:  

   - Asignar el mensaje creado como parte de la orquestación.  

   - Para recuperar la acción que se debe especificar para el **PollingAction** propiedad de enlace en tiempo de ejecución.  

     Debe usar el esquema para la operación de salida para obtener el mensaje de solicitud debe especificar como parte de la **PollingInput** enlaza la propiedad.  

## <a name="setting-up-the-orchestration"></a>Configuración de la orquestación  
 Debe crear una orquestación de BizTalk para utilizar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para recibir mensajes de cambio de datos basados en sondeos de Oracle. En esta orquestación, el adaptador recibe la respuesta al ejecutar el procedimiento almacenado para el que especifica el mensaje de solicitud como parte de la **PollingInput** enlaza la propiedad. El mensaje de respuesta para el procedimiento almacenado se guarda en una ubicación de archivo. Contendría una orquestación típica para el sondeo de base de datos de Oracle:  

- Recepción y envío formas para recibir mensajes de Oracle y enviar a un puerto de archivo, respectivamente.  

- Puerto para recibir mensajes de la base de datos de Oracle de recepción unidireccional.  

  > [!IMPORTANT]
  >  Para escenarios de sondeo de entrada siempre debe configurar un puerto de recepción unidireccional. Bidireccional recibir los puertos no se admiten operaciones de entrada.  

- Un puerto de envío unidireccional para enviar respuestas de sondeo de base de datos de Oracle.  

  Una orquestación de ejemplo es similar al siguiente.  

  ![Orquestación para una consulta de sondeo para Oracle](../../adapters-and-accelerators/adapter-oracle-database/media/6eddfe32-bfd0-4bd9-9e2a-fb4a7d0b53e3.gif "6eddfe32-bfd0-4bd9-9e2a-fb4a7d0b53e3")  

### <a name="adding-message-shapes"></a>Agregar formas de mensaje  
 Asegúrese de que especificar las siguientes propiedades para cada una de las formas de mensaje. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación simplemente mencionadas.  

|Forma|Tipo de forma|Propiedades|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-Establecer **nombre** a *ReceiveMessage*<br /><br /> -Establecer **activar** a *True*|  
|SaveMessage|Send|-Establecer **nombre** a *SaveMessage*|  

### <a name="adding-ports"></a>Agregar puertos  
 Asegúrese de que especificar las siguientes propiedades para cada uno de los puertos lógicos. Los nombres que aparecen en la columna puerto son los nombres de los puertos tal como se muestra en la orquestación.  

|Puerto|Propiedades|  
|----------|----------------|  
|OracleReceivePort|-Establecer **identificador** a *OracleReceivePort*<br /><br /> -Establecer **tipo** a *OracleReceivePortType*<br /><br /> -Establecer **patrón de comunicación** a *unidireccional*<br /><br /> -Establecer **dirección de comunicación** a *de recepción*|  
|SaveMessagePort|-Establecer **identificador** a *SaveMessagePort*<br /><br /> -Establecer **tipo** a *SaveMessagePortType*<br /><br /> -Establecer **patrón de comunicación** a *unidireccional*<br /><br /> -Establecer **dirección de comunicación** a *enviar*|  

### <a name="specify-messages-for-action-shapes-and-connect-to-ports"></a>Especifique los mensajes para las formas Acción y conectar a los puertos  
 En la tabla siguiente especifica las propiedades y sus valores que se deben establecer para especificar los mensajes para las formas Acción y vincular los mensajes a los puertos. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación que se ha mencionado anteriormente.  

|Forma|Propiedades|  
|-----------|----------------|  
|ReceiveMessage|-Establecer **mensaje** a *de recepción*<br /><br /> -Establecer **operación** a *OracleReceivePort.Polling.Request*|  
|SaveMessage|-Establecer **mensaje** a *de recepción*<br /><br /> -Establecer **operación** a *SaveMessagePort.Polling.Request*|  

 Después de especificar estas propiedades, están conectados a los puertos y formas de mensaje y se completa la orquestación.  

 Ahora debe compilar la solución de BizTalk e implementarla en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, consulte [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md).

## <a name="configuring-the-biztalk-application"></a>Configuración de la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, aparece la orquestación que creó anteriormente en el **orquestaciones** panel en la consola de administración de BizTalk Server. Debe usar la consola de administración de BizTalk Server para configurar la aplicación. Para ver un tutorial, vea [Tutorial: implementar una aplicación básica de BizTalk](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).

 Configuración de una aplicación implica:  

- Selección de un host de la aplicación.  

- Asignación de los puertos que ha creado en la orquestación con puertos físicos en la consola de administración de BizTalk Server. Para esta orquestación, debe:  

  - Definir una ubicación en el disco duro y un puerto de archivo correspondiente donde la orquestación de BizTalk quitará los mensajes de Oracle. Estos mensajes serán en respuesta a la instrucción de sondeo que especifique para el puerto de recepción.  

  - Definir un WCF-Custom físico o puerto de recepción WCF-OracleEBS unidireccionales. Este puerto sondea la base de datos de Oracle. Para obtener información sobre cómo crear puertos de recepción, vea [configurar manualmente un enlace de puerto físico al adaptador de Oracle E-Business](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md). Asegúrese de que especificar las siguientes propiedades de enlace para el puerto de recepción.  


    |         Propiedad de enlace         |                                                                                                                                                                                                                                                                                                                                                  Valor                                                                                                                                                                                                                                                                                                                                                   |
    |----------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    |     **InboundOperationType**     |                                                                                                                                                                                                                                                                                                                                         Establezca esta opción en **sondeo**.                                                                                                                                                                                                                                                                                                                                         |
    | **PolledDataAvailableStatement** |                                                                                                                                                                                                                                    En este ejemplo, establezca esta propiedad de enlace en:<br /><br /> `SELECT COUNT (*) FROM ACCOUNTACTIVITY`<br /><br /> Esto garantiza que el adaptador ejecuta la instrucción de sondeo solo cuando la tabla ACCOUNTACTIVITY tiene algunos registros.                                                                                                                                                                                                                                    |
    |        **PollingAction**         |                                                                                                                                                                                                                                           Recuperar la acción de sondeo desde el esquema generado para el mensaje entrante para el procedimiento GET_ACTIVITYS. En este ejemplo, establezca esta propiedad de enlace en **PollingPackageApis/aplicaciones/ACCOUNT_PKG/GET_ACTIVITYS**.                                                                                                                                                                                                                                           |
    |         **PollingInput**         | Para esta propiedad de enlace, especifique el mensaje de solicitud para invocar el GET_ACTIVITYS procedimiento almacenado. Puede obtener el mensaje de solicitud del esquema para la operación de salida generado por el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Debe proporcionar todo el mensaje XML como entrada para esta propiedad de enlace. En este ejemplo, establezca esta propiedad de enlace en:<br /><br /> `<GET_ACTIVITYS xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/PackageApis/APPS/ACCOUNT_PKG">   <INRECS>OPEN ? FOR SELECT * FROM ACCOUNTACTIVITY</INRECS> </GET_ACTIVITYS>`<br /><br /> El GET_ACTIVITYS procedimiento almacenado toma una entrada de REF CURSOR como parámetro. |
    |      **PostPollStatement**       |                                                                                                                                                                                                                                                  Especifique la instrucción posterior a la encuesta para mover todos los datos de tabla ACCOUNTACTIVITY a otra tabla. En este ejemplo, establezca esta propiedad de enlace en:<br /><br /> `BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;`                                                                                                                                                                                                                                                  |

     Para obtener más información acerca de las propiedades de enlace diferente, consulte [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  

    > [!IMPORTANT]
    >  Si se sondear una tabla de interfaz, debe establecer el contexto de la aplicación mediante la especificación de las propiedades de enlace necesaria. Para obtener más información acerca de cómo establecer el contexto de la aplicación vea [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  
    > 
    > [!NOTE]
    >  Se recomienda configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción al realizar operaciones de entrada mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Puede hacerlo agregando el comportamiento del servicio durante la configuración personalizada de WCF o puerto de recepción WCF-OracleEBS. Para obtener instrucciones sobre cómo agregar el comportamiento del servicio, consulte [configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción con Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md).  

## <a name="starting-the-application"></a>Iniciar la aplicación  
 Debe iniciar la aplicación de BizTalk para el sondeo de base de datos de Oracle. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [cómo iniciar una orquestación](../../core/how-to-start-an-orchestration.md).

 En esta etapa, asegúrese de que:  

-   El WCF-Custom o WCF-OracleEBS unidireccional puerto de recepción, que realiza un sondeo Oracle mediante el procedimiento almacenado especificado para el **PollingInput** enlaza la propiedad, se está ejecutando.  

-   El puerto de envío de archivo que recibe los mensajes de base de datos de Oracle, se está ejecutando.  

-   La orquestación de BizTalk para la operación se está ejecutando.  

## <a name="executing-the-operation"></a>Ejecutar la operación  
 Después de ejecutar la aplicación, el siguiente conjunto de acciones tienen lugar, en la misma secuencia:  

-   El adaptador se ejecuta el **PolledDataAvailableStatement** que devuelve un valor positivo que indica el adaptador para ejecutar la instrucción especificada para **PollingInput** enlaza la propiedad.  

-   El adaptador ejecuta el procedimiento almacenado de GET_ACTIVITYS especificado para el **PollingInput** enlace de propiedad y devuelve todas las filas en la tabla ACCOUNTACTIVITY. La respuesta de la base de datos de Oracle es similar al siguiente:  

    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <GET_ACTIVITYS xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/PollingPackageApis/APPS/ACCOUNT_PKG">  
      <OUTRECS>  
        <OUTRECSRecord xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/ReferencedRecordTypes/APPS/ACCOUNT_PKG/GET_ACTIVITYS/APPS/GET_ACTIVITYS">  
          <TID>1</TID>   
          <ACCOUNT>100001</ACCOUNT>   
          <AMOUNT>500</AMOUNT>   
          <DESCRIPTION />   
          <TRANSDATE>2008-06-21T15:52:19</TRANSDATE>   
          <PROCESSED>n</PROCESSED>   
        </OUTRECSRecord>  
        <OUTRECSRecord xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/ReferencedRecordTypes/APPS/ACCOUNT_PKG/GET_ACTIVITYS/APPS/GET_ACTIVITYS">  
          ......  
          ......   
        </OUTRECSRecord>  
        ......  
        ......  
      </OUTRECS>  
    </GET_ACTIVITYS>  
    ```  

-   El adaptador ejecuta la instrucción posterior a la encuesta, que mueve todos los datos de tabla ACCOUNTACTIVITY a otra tabla.  

-   Después del intervalo de sondeo, el adaptador ejecuta nuevo **PolledDataAvailableStatement**. Porque la tabla ACCOUNTACTIVITY no tiene ningún registro ahora, **PolledDataAvailableStatement** no devuelve un valor positivo y, por tanto, el adaptador no ejecuta la instrucción especificada para el **PollingInput** propiedad de enlace. Como resultado, el cliente del adaptador no obtener cualquier mensaje de sondeo.  

-   El cliente de adaptador no reciba más mensajes de sondeo hasta que explícitamente se insertan algunos registros en la tabla ACCOUNTACTIVITY. Para insertar más registros, puede ejecutar el script de more_activity_data.sql proporcionado con los ejemplos. Después de ejecutar este script, la próxima vez **PolledDataAvailableStatement** es ejecuta, devuelve un valor positivo. Como resultado, el adaptador ejecuta la instrucción de sondeo y los clientes del adaptador volverá a reciben un mensaje de sondeo.  

> [!NOTE]
>  El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] seguirá sondeando hasta que deshabilite explícitamente el puerto de recepción desde el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  

## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez que haya implementado y configurado el proyecto de BizTalk, puede exportar opciones de configuración a un archivo XML llamado el archivo de enlaces. Cuando genere un archivo de enlaces, puede importar los valores de configuración desde el archivo, por lo que no es necesario crear los puertos de envío y recepción para la misma orquestación. Para obtener más información acerca de los archivos de enlace, consulte [reutilizar enlaces del adaptador SQL](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md).  

## <a name="see-also"></a>Vea también  
 [Sondear Oracle E-Business Suite con BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-biztalk-server.md)