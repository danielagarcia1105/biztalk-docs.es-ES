---
title: Sondear Oracle E-Business Suite mediante la instrucción SELECT | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81d70b36-8b80-4ab9-b97c-ee861aafbbac
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1eda3c0afb5998485977efddb8a69d47ed4b92a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015423"
---
# <a name="poll-oracle-e-business-suite-using-select-statement"></a>Sondear Oracle E-Business Suite mediante la instrucción SELECT
Puede configurar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para recibir mensajes de cambio de datos periódica mediante el uso de una instrucción SELECT para las tablas de interfaz un sondeo continuo, interfaz vistas, tablas y vistas de Oracle E-Business Suite. Puede especificar una instrucción SELECT como una instrucción de sondeo que el adaptador se ejecuta periódicamente para sondear Oracle E-Business Suite. También puede especificar un bloque de código posterior a la encuesta PL/SQL que el adaptador se ejecuta después de ejecutar la instrucción de sondeo.  

 Para habilitar el sondeo, debe especificar que ciertas propiedades de enlace en el WCF-Custom o WCF-OracleEBS de puerto de recepción.  Para obtener más información acerca de cómo el adaptador admite el sondeo, consulte [compatibilidad con entrada de sondeo utilizando llamadas](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md). Para obtener información acerca de la estructura del mensaje SOAP para las operaciones de sondeo, consulte [esquemas de mensaje para las operaciones de sondeo](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-polling-operations1.md).  

## <a name="configuring-a-polling-operation-with-oracle-e-business-suite-adapter-binding-properties"></a>Configuración de una operación de sondeo con enlazar propiedades de adaptador para Oracle E-Business Suite  
 La siguiente tabla resume el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] mensajes de cambio de propiedades de enlace que usan para configurar el adaptador para recibir datos. Debe especificar estas propiedades de enlace al configurar el puerto de recepción en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  


|         Propiedad de enlace         |                                                                                                                                                                                                                            Descripción                                                                                                                                                                                                                             |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     **InboundOperationType**     |                                                                                                                                                                          Especifica si desea realizar **sondeo** o **notificación** operación entrante. El valor predeterminado es **sondeo**.                                                                                                                                                                          |
| **PolledDataAvailableStatement** |                                                                                                             Especifica la instrucción SQL que ejecuta el adaptador para determinar si los datos están disponibles para el sondeo. Solo si hay un registro, la instrucción SELECT especifique para la **PollingInput** se ejecutará el enlace de propiedad.                                                                                                              |
|       **PollingInterval**        | Especifica el intervalo, en segundos, en el que el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ejecuta la instrucción especificada para el **PolledDataAvailableStatement** enlaza la propiedad. El valor predeterminado es 30 segundos. El intervalo de sondeo determina el intervalo de tiempo entre sondeos sucesivos. Si la instrucción se ejecuta en el intervalo especificado, el adaptador se suspende durante el tiempo restante en el intervalo. |
|         **PollingInput**         |                         Especifica la instrucción de sondeo. Para sondear con una instrucción SELECT, debe especificar una instrucción SELECT para esta propiedad de enlace. El valor predeterminado es null.<br /><br /> Debe especificar un valor para **PollingInput** enlace de propiedad para habilitar el sondeo. Se ejecuta la instrucción de sondeo solo si hay datos disponibles para el sondeo, que viene determinado por la **PolledDataAvailableStatement** enlaza la propiedad.                          |
|        **PollingAction**         |                                                                                                    Especifica la acción para la operación de sondeo. Puede determinar la acción de sondeo para una operación específica de los metadatos que se genera para la operación mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].                                                                                                     |
|      **PostPollStatement**       |                                                                                                                                                                  Especifica un bloque de instrucciones que se ejecuta después de la instrucción especificada por el **PollingInput** propiedad de enlace se ejecuta.                                                                                                                                                                  |
|      **PollWhileDataFound**      |                                    Especifica si el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] pasa por alto el intervalo de sondeo y la instrucción de sondeo, se ejecuta continuamente si hay datos disponibles en la tabla que se sondea. Si no hay datos disponibles en la tabla, el adaptador vuelve para ejecutar la instrucción de sondeo en el intervalo de sondeo especificado. El valor predeterminado es False.                                     |

 Para obtener una descripción más completa de estas propiedades, vea [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md). Para obtener una descripción completa de cómo usar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para sondear la base de datos de Oracle, siga leyendo.  

## <a name="how-this-topic-demonstrates-polling"></a>Cómo este tema muestra el sondeo  
 En este tema, para demostrar cómo el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] admite la recepción de datos cambiar mensajes mediante las instrucciones SELECT, crear un proyecto de BizTalk y genere el esquema para el **sondeo** operación en la tabla que quiere sondear. En este tema, se genere el esquema para el **sondeo** operación para la **MS_SAMPLE_EMPLOYEE** tabla de interfaz en el **biblioteca de objetos de aplicación** aplicación. Esta tabla se crea al ejecutar el script de create_apps_artifacts.sql proporcionado con los ejemplos para crear estos objetos en Oracle E-Business Suite.  

 A continuación, se usará el enrutamiento por contenidos (CBR) en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para configurar una aplicación con un puerto de recepción que se va a recibir mensajes de sondeo desde el **MS_SAMPLE_EMPLOYEE** tabla de la interfaz y, a continuación, se enrutan a un puerto de envío. En este caso, se creará un filtro en el puerto de envío que comprueba la ubicación de recepción especificada y el mensaje se enruta al puerto de envío.  

 Para demostrar una operación de sondeo, llevamos a cabo lo siguiente:  

-   Especifique una instrucción SELECT para la **PolledDataAvailableStatement** enlaza la propiedad para determinar donde la interfaz tabla sondea (MS_SAMPLE_EMPLOYEE) tiene los datos. En este ejemplo, puede establecer esta propiedad de enlace como:  

    ```  
    SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE  
    ```  

     Esto garantiza que el adaptador ejecuta la instrucción de sondeo solo cuando la tabla de interfaz MS_SAMPLE_EMPLOYEE tiene algunos registros.  

-   Especifique una instrucción SELECT para la **PollingInput** enlaza la propiedad. Esta instrucción recupera todas las filas de la tabla de interfaz MS_SAMPLE_EMPLOYEE. En este ejemplo, puede establecer esta propiedad de enlace como:  

    ```  
    SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE  
    ```  

    > [!NOTE]
    >  Para obtener información acerca de la cláusula FOR UPDATE en la instrucción SELECT, vea [sondeo Oracle E-Business Suite mediante la instrucción SELECT](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement.md).  

-   Especifique una instrucción DELETE como parte de la **PostPollStatement** enlaza la propiedad. Esta instrucción eliminará todos los datos de tabla de la interfaz MS_SAMPLE_EMPLOYEE. En este ejemplo, puede establecer esta propiedad de enlace como:  

    ```  
    DELETE FROM MS_SAMPLE_EMPLOYEE  
    ```  

     Una vez que esto ocurre, la próxima vez que la instrucción especificada para **PollingInput** será ejecuta, no capturará todos los datos.  

-   Hasta que se agregan más datos a la tabla de interfaz MS_SAMPLE_EMPLOYEE, no obtendrá ningún mensaje de sondeo. Por lo tanto, debe volver a llenar la tabla de interfaz MS_SAMPLE_EMPLOYEE con nuevos registros. Puede hacerlo ejecutando el script insert_apps_data.sql proporcionado con los ejemplos. Después de ejecutar este script, la siguiente operación de sondeo capturará los nuevos registros que se insertan en la tabla.  

## <a name="how-to-receive-data-change-messages-from-oracle-e-business-suite"></a>Cómo recibir mensajes de cambio de datos de Oracle E-Business Suite  
 Realizar una operación en la base de datos de Oracle mediante [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] implica las siguientes tareas de procedimientos se describe en [bloques de creación para crear aplicaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md). Para configurar el adaptador para sondear Oracle E-Business Suite mediante una instrucción SELECT, estas tareas son:  

1. Crear un proyecto de BizTalk y genere el esquema para el **sondeo** operación para la tabla de interfaz que quiere sondear.  

2. Compile e implemente el proyecto de BizTalk.  

3. Configurar la aplicación mediante la creación de puertos de envío y recepción de BizTalk. Además, debe agregar filtro del puerto de envío para que comprueba la ubicación de recepción especificada en el puerto de recepción y el mensaje de sondeo se enruta al puerto de envío.  

   > [!IMPORTANT]
   >  Para escenarios de sondeo de entrada siempre debe configurar un puerto de recepción unidireccional. Bidireccional recibir los puertos no se admiten operaciones de entrada.  

4. Inicie la aplicación de BizTalk.  

   Este tema proporciona instrucciones para realizar estas tareas.  

## <a name="sample-based-on-this-topic"></a>Ejemplo basado en este tema.  
 Un ejemplo, PollingUsingSelectStatement, basado en este tema también se proporciona con BizTalk Adapter Pack. Para obtener más información, consulte [ejemplos](../../adapters-and-accelerators/adapter-oracle-ebs/samples-for-the-oracle-ebs-adapter.md).  

## <a name="generating-schema"></a>Generar el esquema  
 Debe generar el esquema para el **sondeo** operación en la tabla de interfaz MS_SAMPLE_EMPLOYEE en el **biblioteca de objetos de aplicación** aplicación. Realizar las tareas siguientes al generar el esquema mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  

- Seleccione el tipo de contrato **(operación de entrada) de servicio**.  

- Genere el esquema para el **sondeo** operación en la tabla de interfaz MS_SAMPLE_EMPLOYEE. Puede seleccionar la operación y la tabla de interfaz desde el **vista basada en la aplicación** nodo o la **artefacto-vista basada en** nodo.  

  Para obtener más información acerca de cómo generar un esquema, vea [examinar, buscar y obtener metadatos para operaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md).  

## <a name="building-and-deploying-the-biztalk-project"></a>Compilar e implementar el proyecto de BizTalk  
 Ahora debe compilar la solución de BizTalk e implementarla en un servidor BizTalk Server. Para obtener información sobre cómo implementar la solución en BizTalk Server, vea [implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).

## <a name="configuring-the-biztalk-application"></a>Configuración de la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, la aplicación aparece en el **aplicaciones** nodo en la consola de administración de BizTalk Server. Debe usar la consola de administración de BizTalk Server para configurar la aplicación. Como parte de la configuración de la aplicación, debe crear un puerto de recepción y un puerto de envío en la aplicación y, a continuación, agregue el filtro al puerto de envío para que todos los mensajes desde el puerto de recepción se enrutan al puerto de envío.  

 Configuración de una aplicación implica:  

-   Selección de un host de la aplicación.  

-   Creación de puertos de envío y recepción.  

### <a name="creating-a-receive-port"></a>Creación de un puerto de recepción  
 Debe crear un WCF-Custom o WCF-OracleEBS unidireccionales puerto de recepción, que realiza un sondeo Oracle mediante la instrucción SELECT especificada para el **PollingInput** enlaza la propiedad. Para obtener información sobre cómo crear puertos de recepción, vea [configurar manualmente un enlace de puerto físico al adaptador de Oracle E-Business](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md). Al crear el puerto de recepción, asegúrese de que especificar las siguientes propiedades de enlace.  

 **Para el sondeo**  

|Propiedad de enlace|Valor|  
|----------------------|-----------|  
|**InboundOperationType**|Establezca esta opción en **sondeo**.|  
|**PolledDataAvailableStatement**|En este ejemplo, establezca esta propiedad de enlace en:<br /><br /> `SELECT COUNT (*) FROM MS_SAMPLE_EMPLOYEE`|  
|**PollingAction**|Recuperar la acción de sondeo desde el esquema generado para el **sondeo** operación en la tabla de interfaz MS_SAMPLE_EMPLOYEE. En este ejemplo, establezca esta propiedad de enlace en **InterfaceTables, sondeo, buscar, aplicaciones/MS_SAMPLE_EMPLOYEE**.|  
|**PollingInput**|Para esta propiedad de enlace, especifique una instrucción SELECT para recuperar todos los registros de la tabla de interfaz MS_SAMPLE_EMPLOYEE. En este ejemplo, establezca esta propiedad de enlace en:<br /><br /> `SELECT * FROM MS_SAMPLE_EMPLOYEE FOR UPDATE`|  
|**PostPollStatement**|Especifique la instrucción posterior a la encuesta para eliminar todos los datos de la tabla de interfaz MS_SAMPLE_EMPLOYEE. En este ejemplo, establezca esta propiedad de enlace en:<br /><br /> `DELETE FROM MS_SAMPLE_EMPLOYEE`|  

 **Para establecer el contexto de la aplicación**  

 Si va a realizar la operación en artefactos de Oracle E-Business Suite, debe especificar valores para las propiedades de enlace adecuado establecer el contexto de la aplicación. Para obtener más información sobre el contexto de la aplicación y las propiedades de enlace necesarias para el contexto de la aplicación de configuración, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  

 En este ejemplo, especifique los valores adecuados para el **oracleUserName**, **oraclePassword**, y **oracleEBSResponsibility** propiedades de enlace.  

> [!NOTE]
>  Se recomienda configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción al realizar operaciones de entrada mediante el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Puede hacerlo agregando el comportamiento del servicio al configurar el puerto de recepción. Para obtener instrucciones sobre cómo agregar el comportamiento del servicio, consulte [configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción con Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md).  

### <a name="creating-a-send-port"></a>Crear un puerto de envío  
 Definir una ubicación en el disco duro y crear un puerto de envío de archivo correspondiente donde [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] se quitará los mensajes de Oracle. Estos mensajes serán en respuesta a la instrucción de sondeo que especifique para el puerto de recepción. Para obtener información sobre cómo crear puertos de envío, consulte [configurar manualmente un enlace de puerto físico al adaptador de Oracle E-Business](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md).  

 También debe agregar un filtro en el puerto de envío para enrutar los mensajes desde la ubicación de recepción. Para agregar el filtro al puerto de envío:  

1.  Haga doble clic en el puerto de envío para abrir el **propiedades de puerto de envío** cuadro de diálogo.  

2.  En el **propiedades de puerto de envío** cuadro de diálogo, haga clic en el **filtros** ficha.  

3.  Especifique los valores siguientes:  

    -   En el **propiedad** lista, haga clic en **BTS. ReceivePortName**.  

    -   En el **operador** lista, haga clic en **==**.  

    -   En el **valor** , especifique el nombre del puerto de recepción.  

4.  En el **propiedades de puerto de envío** cuadro de diálogo, haga clic en **Aceptar**.  

## <a name="starting-the-application"></a>Iniciar la aplicación  
 Debe iniciar la aplicación de BizTalk para Oracle E-Business Suite de sondeo. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [cómo iniciar una orquestación](../../core/how-to-start-an-orchestration.md).  

 En esta etapa, asegúrese de que:  

-   El WCF-Custom o WCF-OracleEBS unidireccional puerto de recepción, que realiza un sondeo Oracle mediante la instrucción SELECT especificada para el **PollingInput** enlaza la propiedad, se está ejecutando.  

-   El puerto de envío de archivo que recibe los mensajes de base de datos de Oracle, se está ejecutando.  

## <a name="executing-the-operation"></a>Ejecutar la operación  
 Después de ejecutar la aplicación, el siguiente conjunto de acciones tienen lugar, en la misma secuencia:  

-   El adaptador se ejecuta el **PolledDataAvailableStatement** que devuelve un valor positivo que indica el adaptador para ejecutar la instrucción especificada para **PollingInput** enlaza la propiedad.  

-   El adaptador ejecuta la instrucción SELECT para la **PollingInput** enlace de propiedad y devuelve todas las filas en la tabla de interfaz MS_SAMPLE_EMPLOYEE. La respuesta de Oracle E-Business Suite es similar al siguiente:  

    ```  
    <?xml version="1.0" encoding="utf-8" ?>   
    <Poll xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/InterfaceTables/FND/APPS/MS_SAMPLE_EMPLOYEE">   
      <DATA>   
        <SelectRecord xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/TableViewRecord/APPS/MS_SAMPLE_EMPLOYEE">   
         <EMP_NO>10002</EMP_NO>   
         <NAME>JEFF PRICE</NAME>   
         <DESIGNATION>MANAGER</DESIGNATION>   
         <SALARY>25000</SALARY>   
         <JOIN_DATE>2007-12-15T00:00:00</JOIN_DATE>   
        </SelectRecord>   
        <SelectRecord xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/TableViewRecord/APPS/MS_SAMPLE_EMPLOYEE">   
         <EMP_NO>10003</EMP_NO>   
         <NAME>DON HALL</NAME>   
         <DESIGNATION>ACCOUNTANT</DESIGNATION>   
         <SALARY>12000</SALARY>   
         <JOIN_DATE>2005-10-29T00:00:00</JOIN_DATE>   
        </SelectRecord>   
        …        
        <SelectRecord xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/TableViewRecord/APPS/MS_SAMPLE_EMPLOYEE">   
         …   
        </SelectRecord>   
        …   
      </DATA>   
    </Poll>  
    ```  

-   El adaptador ejecuta la instrucción posterior a la encuesta, que elimina todos los datos de tabla de la interfaz MS_SAMPLE_EMPLOYEE.  

-   Después del intervalo de sondeo, el adaptador ejecuta nuevo **PolledDataAvailableStatement**. Dado que la tabla de interfaz MS_SAMPLE_EMPLOYEE no tiene registros ahora, **PolledDataAvailableStatement** no devuelve un valor positivo y, por tanto, el adaptador no ejecuta la instrucción especificada para el  **PollingInput** enlaza la propiedad. Como resultado, el cliente del adaptador no obtener cualquier mensaje de sondeo.  

-   El cliente de adaptador no reciba más mensajes de sondeo hasta que explícitamente se insertan algunos registros en la tabla de interfaz MS_SAMPLE_EMPLOYEE. Para insertar más registros, puede ejecutar el script de insert_apps_data.sql proporcionado con los ejemplos. Después de ejecutar este script, la próxima vez **PolledDataAvailableStatement** es ejecuta, devuelve un valor positivo. Como resultado, el adaptador ejecuta la instrucción de sondeo y los clientes del adaptador volverá a reciben un mensaje de sondeo.  

> [!NOTE]
>  El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] seguirá sondeando hasta que deshabilite explícitamente el puerto de recepción desde el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  

## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez que haya implementado y configurado el proyecto de BizTalk, puede exportar opciones de configuración a un archivo XML llamado el archivo de enlaces. Cuando genere un archivo de enlaces, puede importar la configuración del archivo para que no es necesario crear los puertos de envío y recepción. Para obtener más información acerca de los archivos de enlace, consulte [reutilizar enlaces del adaptador con Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md).  

## <a name="see-also"></a>Vea también  
 [Sondear Oracle E-Business Suite con BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-biztalk-server.md)