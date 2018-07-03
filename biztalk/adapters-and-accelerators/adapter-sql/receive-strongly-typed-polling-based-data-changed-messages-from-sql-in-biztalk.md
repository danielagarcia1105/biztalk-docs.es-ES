---
title: Recibir mensajes fuertemente tipados basados en sondeos cambio de datos desde SQL Server mediante BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e6e6ba7e-9e13-4e28-b57d-d24569277bbc
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5454a20e087a643acb6f2b0bc9735eae6d29b996
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976261"
---
# <a name="receive-strongly-typed-polling-based-data-changed-messages-from-sql-server-using-biztalk-server"></a>Recibir mensajes fuertemente tipados basados en sondeos cambio de datos desde SQL Server mediante BizTalk Server
Puede configurar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para recibir mensajes de sondeo fuertemente tipado de SQL Server. Puede especificar una instrucción de sondeo que se ejecuta el adaptador para sondear la base de datos. La instrucción de sondeo puede ser una instrucción SELECT o un procedimiento almacenado que devuelve un conjunto de resultados.  
  
 Debe usar sondeo fuertemente tipado en un escenario donde desea asignar los elementos en el mensaje de sondeo a cualquier otro esquema. El esquema que desea asignar a podría ser para otra operación en SQL Server. Por ejemplo, podría asignar determinados elementos en el mensaje de sondeo para el esquema para una operación de inserción en otra tabla. Por lo tanto, los valores en el mensaje de sondeo actúan como parámetros para la operación de inserción. En un escenario más sencillo, podría asignar el esquema de mensaje de sondeo fuertemente tipados en un archivo de esquema que simplemente almacena la información.  
  
> [!IMPORTANT]
>  Si desea tener más de un sondeo operación en una sola aplicación de BizTalk, debe especificar un **InboundID** propiedad de conexión como parte de la conexión URI para que sea único. Con un URI de conexión único, puede crear varios puertos de recepción que sondean la misma base de datos, o incluso la misma tabla en una base de datos. Para obtener más información, consulte [de recepción de sondeo mensajes a través de varios puertos de recepción de SQL con Biztalk Server](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md).  
  
 Para obtener más información acerca de cómo el adaptador admite el sondeo fuertemente tipado, vea [soporte técnico para el sondeo](https://msdn.microsoft.com/library/dd788416.aspx). Para obtener más información sobre el esquema de mensaje de sondeo fuertemente tipado, vea [esquemas de mensaje para el sondeo y las operaciones de TypedPolling](../../adapters-and-accelerators/adapter-sql/message-schemas-for-the-polling-and-typedpolling-operations.md).  
  
## <a name="how-this-topic-demonstrates-strongly-typed-polling"></a>Cómo este tema muestra el sondeo fuertemente tipado  
 En este tema se muestra cómo usar el sondeo fuertemente tipado para asignar el mensaje de sondeo a otro esquema. Este tema muestra cómo crear un proyecto de BizTalk y genere el esquema para **TypedPolling** operación. Antes de generar el esquema para **TypedPolling** operación, debe hacer lo siguiente:  
  
- Debe especificar un **InboundID** como parte de la URI de conexión.  
  
- Debe especificar una instrucción de sondeo para el **PollingStatement** enlaza la propiedad.  
  
  Como parte de la instrucción de sondeo, realice las siguientes operaciones:  
  
- Seleccione todas las filas de la tabla Employee.  
  
- Ejecutar un procedimiento almacenado (MOVE_EMP_DATA) para mover todos los registros de la tabla de empleados a una tabla HistorialEmpleados.  
  
- Ejecutar un procedimiento almacenado (ADD_EMP_DETAILS) para agregar un nuevo registro a la tabla Employee. Este procedimiento toma el nombre de empleado, designación y salario como parámetros.  
  
  Para llevar a cabo estas operaciones, debe especificar lo siguiente para el **PollingStatement** enlaza la propiedad:  
  
```  
SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000   
```  
  
 Dado que genere el esquema para el **TypedPolling** operación, el esquema está fuertemente tipada y contiene todos los elementos que se incluirán en el mensaje de sondeo.  
  
 Como parte del mismo proyecto de BizTalk, agregue otro archivo de esquema, por ejemplo EmployeeDetails.xsd. El esquema para EmployeeDetails.xsd es similar al siguiente:  
  
```  
<?xml version="1.0" encoding="utf-16" ?>   
<xs:schema xmlns:b="http://schemas.microsoft.com/BizTalk/2003" xmlns="http://Typed_Polling.EmployeeDetails" elementFormDefault="qualified" targetNamespace="http://Typed_Polling.EmployeeDetails" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="EmployeeDetails">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="Employee_Info" type="xs:string" />   
        <xs:element name="Employee_Profile" type="xs:string" />   
        <xs:element name="Employee_Performance" type="xs:string" />   
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
 El asignador de BizTalk también se agregue al proyecto para asignar los elementos de la tabla Employee (recibida como mensaje de sondeo) a los elementos en el esquema EmployeeDetails.xsd. Como parte del mapa, combinar uno o más elementos del mensaje de sondeo y asignarlo a un único elemento en el esquema EmployeeDetails. Puede hacerlo mediante el **concatenación de cadenas** functoid.  
  
 Por último, como parte del proyecto de BizTalk, se quita un archivo que se ajuste al esquema EmployeeDetails.xsd a un puerto de envío de archivo.  
  
## <a name="configure-typed-polling-with-the-sql-adapter-binding-properties"></a>Configurar el sondeo con tipo con el adaptador SQL, las propiedades de enlace  
 La siguiente tabla resume el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] propiedades que usan para configurar el adaptador para recibir mensajes de cambio de datos de enlace. No sea el **PollingStatement** propiedad de enlace, todas las demás propiedades de enlace enumerados en esta sección son necesarios al configurar el puerto de recepción en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración. Debe especificar el **PollingStatement** enlaza la propiedad antes de generar el esquema para el **TypedPolling** operación.  
  
> [!NOTE]
>  Para el sondeo con tipo, debe especificar el **PollingStatement** enlace propiedad al generar el esquema. Puede especificar también las demás propiedades de enlace al generar el esquema, aunque no son obligatorios. Si se especifican las propiedades de enlace, el enlace de puerto del archivo que el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] genera como parte de la generación de metadatos también contiene los valores especificados para las propiedades de enlace. Más adelante puede importar este archivo de enlace en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] puerto de recepción de la consola de administración para crear el WCF-custom o WCF-SQL con el enlace de propiedades ya establecidas. Para obtener más información acerca de cómo crear un puerto mediante el archivo de enlace, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto para usar el adaptador SQL](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).  
  
|         Propiedad de enlace         |                                                                                                                                                                                                                                                                                                   Descripción                                                                                                                                                                                                                                                                                                    |
|----------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     **InboundOperationType**     |                                                                                                                                                                                                  Especifica si desea realizar **sondeo**, **TypedPolling**, o **notificación** operación entrante. El valor predeterminado es **sondeo**. Para recibir mensajes de sondeo fuertemente tipado, establezca esta opción en **TypedPolling**.                                                                                                                                                                                                   |
| **PolledDataAvailableStatement** |                                                                                                                                                 Especifica la instrucción SQL que ejecuta el adaptador para determinar si los datos están disponibles para el sondeo. La instrucción SQL debe devolver un conjunto que consta de filas y columnas de resultados. Solo si hay una fila, la instrucción SQL especificada para el **PollingStatement** se ejecutará el enlace de propiedad.                                                                                                                                                 |
|   **PollingIntervalInSeconds**   |                                                                                   Especifica el intervalo, en segundos, en el que el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ejecuta la instrucción especificada para el **PolledDataAvailableStatement** enlaza la propiedad. El valor predeterminado es 30 segundos. El intervalo de sondeo determina el intervalo de tiempo entre sondeos sucesivos. Si la instrucción se ejecuta en el intervalo especificado, el adaptador espera el tiempo restante en el intervalo.                                                                                    |
|       **PollingStatement**       | Especifica la instrucción SQL para sondear la tabla de base de datos de SQL Server. Puede especificar una instrucción SELECT simple o un procedimiento almacenado para la instrucción de sondeo. El valor predeterminado es null. Debe especificar un valor para **PollingStatement** para habilitar el sondeo. Se ejecuta la instrucción de sondeo solo si hay datos disponibles para el sondeo, que viene determinado por la **PolledDataAvailableStatement** enlaza la propiedad. Puede especificar cualquier número de instrucciones SQL separadas por punto y coma.<br /><br /> **Importante:** para **TypedPolling**, debe especificar esta propiedad de enlace antes de generar los metadatos. |
|      **PollWhileDataFound**      |                                                                                      Especifica si el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] pasa por alto el intervalo de sondeo y continuamente se ejecuta la instrucción SQL especificada para el **PolledDataAvailableStatement** enlaza la propiedad, si hay datos disponibles en la tabla que se sondea. Si no hay datos disponibles en la tabla, el adaptador vuelve para ejecutar la instrucción SQL en el intervalo de sondeo especificado. El valor predeterminado es **false**.                                                                                       |
  
 Para obtener una descripción más completa de estas propiedades, vea [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md). Para obtener una descripción completa de cómo usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para sondear SQL Server, siga leyendo.  
  
## <a name="how-to-receive-strongly-typed-data-change-messages-from-the-sql-server-database"></a>Cómo recibir mensajes de cambio de datos fuertemente tipado de la base de datos SQL Server  
 Realizar una operación en la base de datos de SQL Server mediante [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] conlleva las tareas de procedimientos se describe en [bloques de creación para desarrollar aplicaciones de BizTalk con el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md). Para configurar el adaptador para recibir mensajes de cambio de datos fuertemente tipados, estas tareas son:  
  
1. Crear un proyecto de BizTalk y, a continuación, genere el esquema para el **TypedPolling** operación. Debe especificar el **InboundID** propiedad de conexión y la **PollingStatement** enlace al generar el esquema de propiedad. Por ejemplo, un URI con el identificador de entrada especificado de la conexión es similar al siguiente:  
  
   ```  
   mssql://mysqlserver//mysqldatabase?InboundID=mydatabaseId  
   ```  
  
2. Cree un mensaje en el proyecto de BizTalk para recibir mensajes de la base de datos de SQL Server.  
  
3. Crear una orquestación para recibir mensajes de la base de datos de SQL Server y guardarlos en una carpeta.  
  
4. Agregue un esquema, por ejemplo, EmployeeDetails.xsd, en el proyecto de BizTalk.  
  
5. Agregue un asignador de BizTalk para asignar el esquema para el mensaje de sondeo al esquema EmployeeDetails.xsd.  
  
6. Compile e implemente el proyecto de BizTalk.  
  
7. Configurar la aplicación mediante la creación física de envío y puertos de recepción de BizTalk.  
  
   > [!IMPORTANT]
   >  Para escenarios de sondeo de entrada siempre debe configurar un unidireccional WCF-Custom o puerto de recepción WCF-SQL. Puertos de recepción bidireccional WCF-Custom o WCF-SQL no se admiten operaciones de entrada.  
  
8. Inicie la aplicación de BizTalk.  
  
   Este tema proporciona instrucciones para realizar estas tareas.  
  
## <a name="sample-based-on-this-topic"></a>Ejemplo basado en este tema.  
 Un ejemplo, TypedPolling, basado en este tema se proporciona con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener más información, consulte [ejemplos del adaptador de SQL](../../adapters-and-accelerators/adapter-sql/samples-for-the-sql-adapter.md).  
  
## <a name="generate-schema"></a>Generar el esquema  
 Debe generar el esquema para el **TypedPolling** operación. Consulte [recuperación de metadatos para operaciones de SQL Server en Visual Studio mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md) para obtener más información acerca de cómo generar el esquema. Realice las tareas siguientes al generar el esquema.  
  
1.  Especifique el **InboundID** propiedad de conexión al especificar el URI de conexión. Este tema, puede especificar el **InboundID** como **empleado**. Para obtener más información sobre el URI de conexión, consulte [crear el URI de conexión de SQL Server](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).  
  
2.  Especifique un valor para el **PollingStatement** enlaza la propiedad. Para obtener más información acerca de esta propiedad de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).  
  
     Para obtener instrucciones sobre cómo especificar las propiedades de enlace, consulte [configurar las propiedades de enlace del adaptador de SQL](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md).  
  
3.  Seleccione el tipo de contrato **(operación de entrada) de servicio**.  
  
4.  Genere el esquema para el **TypedPolling** operación.  
  
## <a name="define-messages-and-message-types"></a>Definir los mensajes y el mensaje de tipos  
 El esquema que ha generado anteriormente describe los "tipos" necesarios para los mensajes en la orquestación. Un mensaje suele ser una variable, el tipo para el que está definido por el esquema correspondiente. Una vez que se genera el esquema, debe vincularlo a los mensajes desde la vista de orquestación de BizTalk del proyecto.  
  
 Este tema, debe crear un mensaje para recibir mensajes de la base de datos de SQL Server.  
  
 Realice los pasos siguientes para crear mensajes y vincularlos a esquema.  
  
#### <a name="create-messages-and-link-to-schema"></a>Crear mensajes y vínculo a esquema  
  
1.  Agregar una orquestación al proyecto de BizTalk. En el Explorador de soluciones, haga clic en el nombre del proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**. Escriba un nombre para la orquestación de BizTalk y, a continuación, haga clic en **agregar**.  
  
2.  Abra la ventana Vista orquestación del proyecto de BizTalk, si aún no está abierto. Haga clic en **vista**, apunte a **Other Windows**y, a continuación, haga clic en **Vista orquestación**.  
  
3.  En el **Vista orquestación**, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.  
  
4.  Haga clic en el mensaje recién creado y, a continuación, seleccione **ventana propiedades**.  
  
5.  En el **propiedades** panel **Message_1**, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |Identificador|Tipo **PollingMessage**.|  
    |Tipo de mensaje|En la lista desplegable, expanda **esquemas**y seleccione *Typed_Polling.TypedPolling_Employee.TypedPolling*, donde *Typed_Polling* es el nombre de su BizTalk proyecto. *TypedPolling_Employee* es el esquema generado para el **TypedPolling** operación.|  
  
## <a name="set-up-the-orchestration"></a>Configurar la orquestación  
 Debe crear una orquestación de BizTalk para utilizar [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] para recibir mensajes de cambio de datos basados en sondeos de la base de datos de SQL Server. En esta orquestación, el adaptador recibe el mensaje de sondeo para la instrucción de sondeo especificado. El asignador de BizTalk, a continuación, asigna el esquema de mensaje de sondeo al esquema EmployeeDetails.xsd. El mensaje asignado, a continuación, se guarda en una ubicación de archivo. Contendría una orquestación para recibir el mensaje de sondeo fuertemente tipado desde una base de datos de SQL Server típica:  
  
- Recepción y envío formas para recibir mensajes de SQL Server y enviar a un puerto de archivo, respectivamente.  
  
- Puerto para recibir mensajes de SQL Server de recepción unidireccional.  
  
  > [!IMPORTANT]
  >  Para escenarios de sondeo de entrada siempre debe configurar un puerto de recepción unidireccional. Bidireccional recibir los puertos no se admiten operaciones de entrada.  
  
- Un puerto de envío unidireccional para enviar respuestas de sondeo de una base de datos de SQL Server en una carpeta.  
  
- Un asignador de BizTalk para asignar el esquema del mensaje de sondeo para cualquier otro esquema.  
  
  Una orquestación de ejemplo es similar al siguiente.  
  
  ![Orquestación para fuertemente&#45;con el tipo de sondeo](../../adapters-and-accelerators/adapter-sql/media/1db03859-b7f8-470c-9158-2be4da0b45ae.gif "1db03859-b7f8-470c-9158-2be4da0b45ae")  
  
### <a name="add-message-shapes"></a>Agregar formas de mensaje  
 Asegúrese de que especificar las siguientes propiedades para cada una de las formas de mensaje. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación simplemente mencionadas.  
  
|Forma|Tipo de forma|Propiedades|  
|-----------|----------------|----------------|  
|ReceiveMessage|Receive|-Establecer **nombre** a *ReceiveMessage*<br /><br /> -Establecer **activar** a *True*|  
|SaveMessage|Send|-Establecer **nombre** a *SaveMessage*|  
  
### <a name="add-ports"></a>Agregar puertos  
 Asegúrese de que especificar las siguientes propiedades para cada uno de los puertos lógicos. Los nombres que aparecen en la columna puerto son los nombres de los puertos tal como se muestra en la orquestación.  
  
|Puerto|Propiedades|  
|----------|----------------|  
|SQLReceivePort|-Establecer **identificador** a *SQLReceivePort*<br /><br /> -Establecer **tipo** a *SQLReceivePortType*<br /><br /> -Establecer **patrón de comunicación** a *unidireccional*<br /><br /> -Establecer **dirección de comunicación** a *de recepción*|  
|SaveMessagePort|-Establecer **identificador** a *SaveMessagePort*<br /><br /> -Establecer **tipo** a *SaveMessagePortType*<br /><br /> -Establecer **patrón de comunicación** a *unidireccional*<br /><br /> -Establecer **dirección de comunicación** a *enviar*|  
  
### <a name="enter-messages-for-action-shapes-and-connect-to-ports"></a>Escriba mensajes para las formas Acción y conectar a los puertos  
 En la tabla siguiente especifica las propiedades y sus valores que se deben establecer para especificar los mensajes para las formas Acción y vincular los mensajes a los puertos. Los nombres que aparecen en la columna de forma son los nombres de las formas de mensaje como se muestra en la orquestación que se ha mencionado anteriormente.  
  
|Forma|Propiedades|  
|-----------|----------------|  
|ReceiveMessage|Establecer **mensaje** a *PollingMessage*<br /><br /> Establecer **operación** a *SQLReceivePort.TypedPolling.Request*|  
|SaveMessage|Establecer **mensaje** a *PollingMessage*<br /><br /> Establecer **operación** a *SaveMessagePort.TypedPolling.Request*|  
  
 Después de especificar estas propiedades, se conectan los puertos y formas de mensaje.  
  
### <a name="add-a-biztalk-mapper"></a>Agregar a un asignador de BizTalk  
 Debe agregar a un asignador de BizTalk a la orquestación para asignar el esquema de mensaje de sondeo para el esquema EmployeeDetails.xsd. En el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, se usará este asignador para asignar el esquema para el mensaje de sondeo para el esquema EmployeeDetails.xsd.  
  

1. Agregue a un asignador de BizTalk para el proyecto de BizTalk. Haga clic en el proyecto de BizTalk, seleccione **agregar**y haga clic en **nuevo elemento**.  
  
    En el **Agregar nuevo elemento** cuadro de diálogo, en el panel izquierdo, seleccione **archivos de asignación**. En el panel derecho, seleccione **mapa**. Especifique un nombre para la asignación, como `MapSchema.btm`. Haga clic en **Agregar**.  
  
2. En el panel Esquema de origen, haga clic en **Abrir esquema de origen**.  
  
3. En el **selector de tipos de BizTalk** diálogo cuadro, expanda el nombre del proyecto, **esquemas**y seleccione el esquema para el mensaje de sondeo. Este tema, seleccione Typed_Polling.TypedPolling_Employee. Haga clic en **Aceptar**.  
  
4. En el **nodo raíz para esquema de origen** cuadro de diálogo, seleccione TypedPolling y haga clic en **Aceptar**.  
  
5. En el panel Esquema de destino, haga clic en **Abrir esquema de destino**.  
  
6. En el **selector de tipos de BizTalk** diálogo cuadro, expanda el nombre del proyecto, **esquemas**y seleccione el esquema para EmployeeDetails. Este tema, seleccione Typed_Polling.EmployeeDetails. Haga clic en **Aceptar**.  
  
7. En el esquema de origen del mensaje de sondeo, expanda el nodo de TypedPollingResultSet0 y los nodos posteriores para ver los elementos que se devuelven en el mensaje de sondeo. En el esquema de destino, expanda el nodo EmployeeDetails para ver los diferentes elementos del esquema. Este tema, debe asignar los esquemas de tal forma que:  
  
   - **Id_Empleado** y **nombre** en el origen de esquema debe asignar a **Employee_Info** en el esquema de destino.  
  
   - **Designación** y **Job_Description** en el origen de esquema debe asignar a **Employee_Profile** en el esquema de destino.  
  
   - **Clasificación** y **salario** en el origen de esquema debe asignar a **Employee_Performance** en el esquema de destino.  
  
     Para combinar más de un nodo en el esquema de origen y asignarlas a un único nodo del esquema de destino, debe usar el **functoid concatenación de cadenas**. Detalles [!INCLUDE[ui-guidance-developers-reference](../../includes/ui-guidance-developers-reference.md)].
  
8. Para usar el functoid de concatenación de cadenas:  
  
   1.  Desde el **cuadro de herramientas**, arrastre el **concatenación de cadenas** functoid y colóquela en la cuadrícula del asignador.  
  
   2.  Conectar el **Id_Empleado** y **nombre** elementos del esquema de origen hasta el functoid.  
  
   3.  Conecte el functoid para el **Employee_Info** elemento del esquema de destino.  
  
   4.  Repita estos pasos para todos los elementos que desea asignar. Un mapa termine será similar al siguiente:  
  
        ![Asignar el esquema de sondeo fuertemente tipado](../../adapters-and-accelerators/adapter-sql/media/0a4a2608-3b84-4bac-9a16-512cf42c7525.gif "0a4a2608-3b84-4bac-9a16-512cf42c7525")  
  
   5.  Guarde el mapa.  
  
   La orquestación completada después de crear al asignador. Ahora debe compilar la solución de BizTalk e implementarla en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, consulte [compilar y ejecutar orquestaciones](../../core/building-and-running-orchestrations.md).
  
## <a name="configure-the-biztalk-application"></a>Configurar la aplicación de BizTalk  
 Después de haber implementado el proyecto de BizTalk, aparece la orquestación que creó anteriormente en el **orquestaciones** panel en la consola de administración de BizTalk Server. Debe usar la consola de administración de BizTalk Server para configurar la aplicación. Para ver un tutorial, vea [Tutorial: implementar una aplicación básica de BizTalk](Walkthrough:%20Deploying%20a%20Basic%20BizTalk%20Application.md).
  
 Configuración de una aplicación implica:  
  
- Selección de un host de la aplicación.  
  
- Asignación de los puertos que ha creado en la orquestación con puertos físicos en la consola de administración de BizTalk Server. Para esta orquestación, debe:  
  
  - Definir un WCF-Custom físico o puerto de recepción unidireccionales de WCF-SQL. Este puerto sondea la base de datos de SQL Server con la instrucción de sondeo que especifique para el puerto. Para obtener información sobre cómo crear los puertos, consulte [configurar manualmente un enlace de puerto físico al adaptador de SQL](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md). Asegúrese de que especificar las siguientes propiedades de enlace para el puerto de recepción.  
  
    > [!IMPORTANT]
    >  Asegúrese de especificar el **InboundID** como parte de la URI de conexión. El identificador de entrada debe ser el mismo que especificó al generar el esquema.  
    > 
    > [!IMPORTANT]
    >  No es necesario realizar este paso si especifica las propiedades de enlace en tiempo de diseño. En tal caso, puede crear un WCF-custom o WCF-SQL puerto de recepción, con el conjunto de propiedades de enlace necesaria, importando el archivo de enlace creado por el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]. Para obtener más información, consulte [configurar un enlace de puerto físico mediante un archivo de enlace de puerto para usar el adaptador SQL](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).  
  
    |Propiedad de enlace|Valor|  
    |----------------------|-----------|  
    |**InboundOperationType**|Asegúrese de que se establece en **TypedPolling**.|  
    |**PolledDataAvailableStatement**|Asegúrese de que especificar la misma instrucción SQL que especificó al generar el esquema, que es:<br /><br /> `SELECT COUNT(*) FROM Employee`|  
    |**PollingStatement**|Asegúrese de que proporcionar la misma instrucción de sondeo que especificó al generar el esquema, que es:<br /><br /> `SELECT * FROM Employee;EXEC MOVE_EMP_DATA;EXEC ADD_EMP_DETAILS John, Tester, 100000`|  
  
     Para obtener más información acerca de las propiedades de enlace diferente, consulte [Obtenga información sobre el adaptador de BizTalk para propiedades de enlace del adaptador de SQL Server](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).  
  
    > [!NOTE]
    >  Se recomienda configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción al realizar operaciones de entrada mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Puede hacerlo agregando el servicio de puerto de recepción de comportamiento al configurar el WCF-Custom o WCF-SQL. Para obtener instrucciones sobre cómo agregar el comportamiento del servicio, consulte [configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción con SQL](../../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md).  
  
  - Definir un puerto de envío de archivo donde el adaptador quitará el mensaje. Este puerto de envío también van a usar la asignación creada en la orquestación para asignar el mensaje de sondeo a un mensaje que se ajuste al esquema EmployeeDetails.xsd. Realice los pasos siguientes para configurar el puerto de envío de archivo para usar la asignación.  
  
    1.  Cree un puerto de envío de archivos.  
  
    2.  En el panel izquierdo del cuadro de diálogo de propiedades de puerto de envío, haga clic en **asignaciones de salida**. En el panel derecho, haga clic en el campo el **mapa** columna y en la lista desplegable, seleccione **MapSchema**. Haga clic en **Aceptar**.  
  
         ![Configurar la asignación de salida en el puerto de envío de archivo](../../adapters-and-accelerators/adapter-sql/media/831c9aee-fd97-466f-9270-3b04dbccd9fe.gif "831c9aee-fd97-466f-9270-3b04dbccd9fe")  
  
## <a name="start-the-application"></a>Iniciar la aplicación  
 Debe iniciar la aplicación de BizTalk para recibir mensajes de la base de datos de SQL Server. Para obtener instrucciones acerca de cómo iniciar una aplicación de BizTalk, consulte [cómo iniciar una orquestación](../../core/how-to-start-an-orchestration.md).
  
 En esta etapa, asegúrese de que:  
  
-   El WCF-Custom o WCF-SQL unidireccional puerto de recepción, que sondea la base de datos de SQL Server mediante las instrucciones especificadas para el **PollingStatement** enlaza la propiedad, se está ejecutando.  
  
-   El puerto de envío de archivo que se asignará el mensaje de sondeo para el esquema EmployeeDetails, se está ejecutando.  
  
-   La orquestación de BizTalk para la operación se está ejecutando.  
  
## <a name="execute-the-operation"></a>Ejecutar la operación  
 Después de ejecutar la aplicación, el siguiente conjunto de acciones tienen lugar, en la misma secuencia:  
  
- El adaptador se ejecuta el **PolledDataAvailableStatement** en el empleado de la tabla y determina que la tabla tiene registros de sondeo.  
  
- El adaptador ejecuta la instrucción de sondeo. Porque la instrucción de sondeo consta de una instrucción SELECT y los procedimientos almacenados, el adaptador ejecutará todas las instrucciones uno tras otro.  
  
  - El adaptador ejecuta primero la instrucción SELECT que devuelve todos los registros en la tabla Employee.  
  
  - El adaptador, a continuación, ejecuta el procedimiento MOVE_EMP_DATA almacenados que mueve todos los datos de la tabla Employee a la tabla HistorialEmpleados. Este procedimiento almacenado no devuelve ningún valor.  
  
  - El adaptador, a continuación, ejecuta el procedimiento ADD_EMP_DETAILS almacenado que agrega un registro a la tabla Employee. Este procedimiento almacenado devuelve el identificador de empleado para el registro insertado.  
  
    Una vez que se ejecuta la instrucción de sondeo y se recibe el mensaje, el mensaje de sondeo obtiene envío al puerto de envío de archivo. Aquí, la asignación de salida (**MapSchema**) configurado en las asignaciones de puerto de envío el mensaje de sondeo en el esquema EmployeeDetails y coloca el mensaje en una ubicación de archivo. El mensaje es similar al siguiente:  
  
  ```  
  <?xml version="1.0" encoding="utf-8" ?>   
  <EmployeeDetails xmlns="http://Typed_Polling.EmployeeDetails">  
    <Employee_Info>10751John</Employee_Info>   
    <Employee_Profile>TesterManagesTesting</Employee_Profile>   
    <Employee_Performance>100000</EmployeePerformance>  
  </EmployeeDetails>  
  ```  
  
   En la respuesta anterior, observará que el elemento Employee_Info contiene una combinación de Id. de empleado (10751) y el nombre de empleado (John). Los demás elementos contienen también combinaciones como asignado en el asignador que creó como parte de la orquestación.  
  
> [!NOTE]
>  El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] seguirá sondeando hasta que deshabilite explícitamente el puerto de recepción desde el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
## <a name="best-practices"></a>Procedimientos recomendados  
 Una vez que haya implementado y configurado el proyecto de BizTalk, puede exportar opciones de configuración a un archivo XML llamado el archivo de enlace. Cuando genere un archivo de enlace, puede importar los valores de configuración desde el archivo, por lo que no es necesario crear los puertos de envío y recepción para la misma orquestación. Para obtener más información acerca de los archivos de enlace, consulte [reutilizar los enlaces del adaptador](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md).
  
## <a name="see-also"></a>Vea también  
 [Sondear el servidor SQL mediante el adaptador SQL con BizTalk Server](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-biztalk-server.md)