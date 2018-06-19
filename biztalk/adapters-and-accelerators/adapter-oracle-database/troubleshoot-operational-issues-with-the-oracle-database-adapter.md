---
title: Solucionar problemas de funcionamiento con el adaptador de la base de datos de Oracle | Documentos de Microsoft
description: Problemas comunes y soluciones para el adaptador de base de datos de Oracle en el módulo de adaptador de BizTalk (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2fb83245-2b6a-48cc-8601-b923bb009a58
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ac926a378224e09dce36a52b52c171fb27911b0
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010109"
---
# <a name="troubleshoot-operational-issues-with-the-oracle-database-adapter"></a>Solucionar problemas de funcionamiento con el adaptador de la base de datos de Oracle
Solución de problemas de técnicas para solucionar errores operativos que puede experimentar con [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)].  
  
## <a name="enable-tracing"></a>Habilitar el seguimiento  
 Para obtener información acerca del seguimiento de soporte técnico en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [el seguimiento de diagnóstico y registro de mensajes para el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/diagnostic-tracing-and-message-logging-for-the-oracle-database-adapter.md).  
  
## <a name="known-issues"></a>Problemas conocidos  
 Éstos son los errores más comunes que pueden surgir al usar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], junto con sus causa probable y la resolución.   
  
### <a name="BKMK_OraDBLoading"></a>Error al cargar los enlaces del adaptador  
 **Problema**  
  
 Al intentar iniciar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], obtendrá el error siguiente:  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 **Causa**  
  
 Al intentar iniciar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], WCF carga los enlaces del adaptador para todos los adaptadores instalados. En cambio, los enlaces del adaptador están depende del software de cliente específico para la aplicación de empresa. Es posible que tenga este problema para uno o ambos de los siguientes motivos:  
  
-   El software de cliente LOB necesario no está instalado en el equipo donde instaló el adaptador.  
  
-   Se realizó una instalación típica o completar del adaptador, que se instala todos los adaptadores incluidos en el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Sin embargo, podrían instalarse las bibliotecas de cliente LOB para solo una aplicación empresarial. Como resultado, la interfaz gráfica de usuario produce un error al cargar los enlaces para los demás adaptadores.  
  
 **Resolución**  
  
-   Asegúrese de que las versiones de cliente LOB necesarias se instalan en el equipo donde instaló el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. [Línea de negocio (LOB) y los sistemas empresariales compatibles](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx) se enumeran las versiones de cliente admitidos.  
  
-   Asegúrese de que se realiza una instalación personalizada de los adaptadores para instalar a sólo el adaptador que necesita.  
  
    > [!NOTE]
    >  Para asegurarse de que la aplicación funcione con la versión más reciente de ODP.NET, debe tener las "DLL de directiva" instalado en el equipo y registrado en la GAC. Para obtener más información, consulte [proveedor de datos de Oracle para .NET](http://go.microsoft.com/fwlink/p/?LinkId=92834) en el sitio Web de Oracle.  
  
###  <a name="BKMK_OraDBAdapDisplay"></a>El adaptador de la base de datos de Oracle no se muestra en la lista de adaptadores en la consola de administración de BizTalk Server  
 **Problema**  
  
El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] incluidos con [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] no aparece en la lista de adaptadores en la consola de administración de BizTalk Server.  
  
 **Causa**  
  
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] es un enlace personalizado de WCF. Por lo tanto, aunque la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] muestra de la consola de administración de la [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], no muestra los enlaces personalizados de WCF y por lo tanto, no se mostrarán basadas en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
 **Resolución**  
  
 Puede agregar explícitamente la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, siga los pasos mencionados en [agregar el adaptador de la base de datos de Oracle a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).  
  
###  <a name="BKMK_OraDBXMLRetrieve"></a>Error al recuperar la salida XML con más de 65.536 nodos  
 **Problema**  
  
 El adaptador produce el siguiente error al recuperar el XML de salida que tiene más de 65.536 nodos.  
  
```  
Maximum number of items that can be serialized or deserialized in an object graph is '65536'.  
Change the object graph or increase the MaxItemsInObjectGraph quota.  
```  
  
 **Causa**  
  
 El adaptador no se puede serializar y deserializar un objeto con más de 65.536 elementos.  
  
 **Resolución**  
  
 Puede solucionar este problema estableciendo la `maxItemsInObjectGraph` parámetro. Puede establecer en cualquiera de las dos maneras siguientes:  
  
-   Establezca este parámetro cambiando el `maxItemsInObjectGraph` parámetro en el `ServiceBehavior` atributo en la clase de servicio.  
  
-   Agregue lo siguiente al archivo app.config de la aplicación.  
  
    ```  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="NewBehavior">  
          <dataContractSerializer maxItemsInObjectGraph="65536000" />  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    ```  
  
 Un ejemplo app.config tiene el siguiente aspecto.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="NewBehavior">  
         <dataContractSerializer maxItemsInObjectGraph="65536000" />  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <client>  
      <endpoint   behaviorConfiguration="NewBehavior" binding="oracleDBBinding"  
       contract="IOutboundContract" name="oracle_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
###  <a name="BKMK_OraDBPerfOps"></a>Error al realizar operaciones en la base de datos de Oracle  
 **Problema**  
  
 El adaptador produce el siguiente error al realizar cualquier operación en la base de datos de Oracle mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  
  
-   **Para que BizTalk Server**  
  
    ```  
    System.ArgumentNullException: Value cannot be null.  
    ```  
  
 **Causa**  
  
 No se especifica la acción de WCF para el mensaje. WCF requiere una acción de SOAP que se especifique para cada operación, que informa al adaptador acerca de la operación se realizará en la aplicación de LOB.  
  
 **Resolución**  
  
 Especifica la acción de SOAP en el puerto de envío o como una propiedad de contexto de mensaje en una orquestación de BizTalk. Para obtener instrucciones, consulte [configurar la acción SOAP para la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-soap-action-for-oracle-database.md). Vea [mensajes y esquemas de mensaje](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md) para ver una lista de acciones para cada operación.  
  
###  <a name="BKMK_OraDBXmlParsing"></a>XmlReaderParsingException debido a un nombre de operación incorrecto en la acción especificada  
 **Problema**  
  
 La consola de administración de BizTalk Server produce el siguiente error al enviar mensajes a una base de datos de Oracle:  
  
```  
Microsoft.ServiceModel.Channels.Common.XmlReaderParsingException: Invalid argument:  
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<operation_name>" Action="<action>" />  
</BtsActionMapping>  
```  
  
 **Causa**  
  
 Si configura un puerto de WCF-Custom importando el archivo de enlace de puerto creado por el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], se especifica la acción en el puerto en el siguiente formato:  
  
```  
<BtsActionMapping>  
  <Operation Name="Op1" Action="http://MyService/Svc/Op1" />  
</BtsActionMapping>  
```  
  
 En el formato anterior, el nombre de la operación se rige por la operación que eligió al generar el esquema. Por ejemplo, si ha generado el esquema para la operación de inserción en una tabla, el nombre de la operación en la acción será "Insertar". Sin embargo, el nombre de la operación en el puerto lógico creado en la orquestación de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] podría ser diferente.  
  
 **Resolución**  
  
 Asegúrese de que los nombres de operación en el puerto lógico de ambas (en la orquestación de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) y el puerto físico (en la consola de administración de BizTalk Server) son los mismos.  
  
###  <a name="BKMK_OraDBConnURI"></a>Error al especificar un URI de conexión para un puerto personalizado de WCF de BizTalk  
 **Problema**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]produce el siguiente error cuando se especifica un URI de conexión para conectarse a la base de datos de Oracle.  
  
```  
Error saving properties.  
(System.ArgumentException) The specified address is invalid.  
(System.ArgumentException) Invalid address;  
"<connection URI>" is not a well-formed absolute uri.  
```  
  
 **Causa**  
  
 El URI de conexión no cumple con el formato de codificación estándar. Por ejemplo, el valor de un parámetro podría contener un espacio.  
  
 **Resolución**  
  
 Asegúrese de que la conexión URI especifica cumple el formato de codificación estándar. Por ejemplo, un espacio en blanco debe sustituirse por "% 20".  
  
###  <a name="BKMK_OraDBInvalCursor"></a>Excepción de cursor no válido al invocar procedimientos almacenados que toman parámetros REF CURSOR  
 **Problema**  
  
 Al invocar los procedimientos de la base de datos de Oracle que toman entradas de REF CURSOR, puede obtener la siguiente excepción:  
  
```  
Microsoft.ServiceModel.Channels.Common.TargetSystemException: ORA-01001: invalid cursor ---> Oracle.DataAccess.Client.OracleException  
```  
  
 **Causa**  
  
 El bloque de PL/SQL para conocer el procedimiento que se está invocando podría ser canalizando los cursores REF CURSOR, es decir, en REF CURSOR podría obtener asignarse a cabo REF CURSOR.  
  
 **Resolución**  
  
 El bloque de PL/SQL no debe canalizar la en la salida cursores REF cursor sin que se procese correctamente.  
  
###  <a name="BKMK_OraDBValidateResp"></a>Error al validar la respuesta para la operación de ReadLOB con BizTalk Server  
 **Problema**  
  
 Mientras se realiza una operación de ReadLOB con el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], la respuesta de la base de datos de Oracle se produce un error de validación en el lenguaje de descripción de servicios Web (WSDL).  
  
 **Causa**  
  
 El archivo WSDL contiene un nombre de nodo StreamBody que se define para la ejecución de las solicitudes de servicio, pero no es necesario para escenarios de BizTalk. Por lo tanto, cuando la salida XML, que no contiene el nodo StreamBody, se compara con el WSDL, se produce un error en validación.  
  
 **Resolución**  
  
 Quite el nodo StreamBody desde WSDL al validarlo con el resultado generado con el servidor BizTalk Server. Para ello, realice los pasos siguientes:  
  
1.  El archivo WSDL que contiene el nodo StreamBody tiene el siguiente aspecto.  
  
    ```  
    <xs:element name="ReadLOBResponse">  
        <xs:annotation>  
          <xs:documentation>  
            <doc:action xmlns:doc="http://schemas.microsoft.com/servicemodel/adapters/metadata/documentation">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/TBL_ALL_DATATYPES/ReadLOB/response\</doc:action>  
          </xs:documentation>  
        </xs:annotation>  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element minOccurs="1" maxOccurs="1" name="ReadLOBResult" nillable="true" type="ns3:StreamBody" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    ```  
  
     Reemplace los anteriores con lo siguiente.  
  
    ```  
    <xs:element name="ReadLOBResponse">  
     <xs:annotation>  
     <xs:documentation>  
      <doc:action xmlns:doc="http://schemas.microsoft.com/servicemodel/adapters/metadata/documentation">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/TBL_ALL_DATATYPES/ReadLOB/response\</doc:action>   
      </xs:documentation>  
      </xs:annotation>  
     <xs:complexType>  
     <xs:sequence>  
      <xs:element minOccurs="1" maxOccurs="1" name="ReadLOBResult" type="xs:base64Binary" />   
      </xs:sequence>  
      </xs:complexType>  
      </xs:element>  
    ```  
  
     En este paso, ha quitado la referencia al tipo = "ns3:StreamBody" en el documento XSD original y sustituirla por otra con el tipo = "base64Binary". Además, se quita el valor "true" nillable = de XSD original.  
  
2.  Extraiga los siguientes elementos de WSDL.  
  
    ```  
    <xs:complexType name="StreamBody">  
        <xs:sequence>  
          <xs:element minOccurs="1" maxOccurs="1" name="Stream">  
            <xs:simpleType>  
              <xs:restriction base="xs:base64Binary">  
                <xs:minLength value="0" />  
              </xs:restriction>  
            </xs:simpleType>  
          </xs:element>  
        </xs:sequence>  
      </xs:complexType>  
      <xs:element name="StreamBody" nillable="true" type="ns3:StreamBody" />  
    ```  
  
    > [!NOTE]
    >  No se admite la operación de ReadLOB con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Debe usar una operación de selección de tabla para leer los datos LOB de una [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución.  
  
###  <a name="BKMK_OraDBSchemaValidateFail"></a>Puede producir un error de validación del esquema en escenarios de sondeo  
 **Problema**  
  
 Se produce un error en la validación del esquema en escenarios donde la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] tablas que contienen campos de tipo ROWID o UNROWID sondea la base de datos.  
  
 **Causa**  
  
 En tiempo de diseño, cuando el adaptador genera los metadatos de la tabla que contiene campos de tipo ROWID o UNROWID, el esquema se incluye "nillable = false", lo que significa que los campos de tipo ROWID o UNROWID no pueden ser nulos. Sin embargo, en tiempo de ejecución cuando el adaptador recupera los metadatos, los campos de tipo ROWID o UNROWID contienen valores null. Por lo tanto, se produce un error en la validación del esquema.  
  
 **Resolución**  
  
 Si usas el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], quizá quiera deshabilitar la validación de esquema. Como alternativa, puede editar manualmente el esquema que se va a cambiar "nillbale = true" para los tipos de datos ROWID y UNROWID.  
  
###  <a name="BKMK_OraDBUnreasonConv"></a>Error de 'Conversion irrazonable solicitado' al ejecutar procedimientos almacenados con tipos de registros como parámetros  
 **Causa**  
  
 Considere un escenario donde un Oracle almacena procedimiento toma un tipo de registro como un parámetro. Suponga que se declara el tipo de registro como \<nombre de la tabla\>% ROWTYPE, donde la tabla tiene una columna de tipo de datos de tipo LONG. Cuando el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] encuentra los datos grandes de tipo, Establece el tamaño del tipo de datos igual que el valor especificado para la **LongDatatypeColumnSize** propiedad de enlace. Sin embargo, la base de datos de Oracle no definen un tamaño para el tipo de datos de tipo LONG. Por lo tanto, cuando el adaptador invoca el procedimiento almacenado, produce un error de 'Conversion irrazonable solicitado'.  
  
 **Resolución**  
  
 Si un tipo de registro tiene un tipo de datos de tipo LONG, debe definir explícitamente como parte de un paquete.  
  
###  <a name="BKMK_OraDBAdapRecognize"></a>El adaptador no reconoce la acción en el puerto físico incluso aunque use el archivo de enlace generado por el complemento Consume Adapter Service para crear los puertos  
 **Problema**  
  
 Después de usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar el esquema para una operación específica en la base de datos de Oracle, el complemento también crea un archivo de enlace de puerto. Puede importar este enlace archivo usando el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para crear puertos físicos en BizTalk Server. Sin embargo, cuando se envían mensajes a la base de datos de Oracle mediante estos puertos, el adaptador no se puede entender la acción especificada en el puerto y produce un error similar al siguiente:  
  
```  
Microsoft.ServiceModel.Channels.Common.UnsupportedOperationException: Incorrect Action   
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<op_name>" Action="<action>" />  
</BtsActionMapping>. Correct the specified Action, or refer to the documentation on the allowed formats for the Actions.  
```  
  
 **Causa**  
  
 Cuando crea puertos lógicos en una orquestación de BizTalk, especificar ciertos nombres para las operaciones en los puertos o simplemente utilizar los nombres predeterminados como Operation_1, Operation_2, etcetera. Sin embargo, en el archivo de enlace generado por el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], el nombre de la operación es el mismo que el nombre de la operación de base de datos de Oracle para el que generar los metadatos. Por ejemplo, si se generan metadatos para seleccionar operación en la tabla ACCOUNTACTIVITY en la base de datos de Oracle, se establecerá la acción a la siguiente:  
  
```  
<Operation Name="Select" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select" />  
```  
  
 Cuando se importa el archivo de enlace, la misma acción que se establece en el puerto físico. Por lo tanto, los nombres de operación en el puerto lógico (Operation_1, Operation_2, etc.) no coincide con los nombres de operación especificados en la acción en el puerto físico, lo que produce un error.  
  
 **Resolución**  
  
 Asegúrese de que el nombre de la operación en el puerto lógico es el mismo que el nombre de operación especificado como parte de la acción en el puerto físico. Realice una de las siguientes operaciones:  
  
-   Cambiar el nombre de la operación en el puerto lógico de orquestación de BizTalk de Operation_1, etc. a la operación para el que genera metadatos, por ejemplo Select.  
  
-   Cambiar el nombre de la operación en la acción en el puerto físico para el nombre de la operación en el puerto lógico. Por ejemplo, puede cambiar la acción en el puerto físico que es similar al siguiente:  
  
    ```  
    <Operation Name="Operation_1" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select" />  
    ```  
  
###  <a name="BKMK_OraDBOverflowExcep"></a>Adaptador lanza una excepción de desbordamiento ("System.OverflowException") en la ejecución de una operación  
 **Problema**  
  
 Mediante el adaptador, si se intenta realizar una operación que contiene los tipos de datos numéricos de Oracle dentro de los conjuntos de datos o débilmente tipada cursores REF CURSOR, el adaptador podría producir una excepción de desbordamiento.  
  
 **Causa**  
  
 Esto sucede si se proporciona un valor grande para el tipo de datos numéricos de Oracle dentro de los conjuntos de datos o débilmente tipada cursores REF cursor que no caben en el tipo de .NET correspondiente.  
  
 **Resolución**  
  
 Si desea pasar valores grandes para el tipo de datos numéricos de Oracle dentro de los conjuntos de datos o débilmente tipada cursores REF CURSOR, debe habilitar escribiendo segura estableciendo el valor de la **EnableSafeTyping** enlace propiedad **true**. Habilitar escribiendo seguro, expone al tipo de datos numéricos de Oracle en conjuntos de datos o débilmente tipada cursores REF cursor como cadenas.  
  
###  <a name="BKMK_OraDBRootNode"></a>Error con RootNode TypeName en proyectos de BizTalk  
 **Problema**  
  
 En un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], si los esquemas generan a partir del [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] contiene caracteres no válidos o palabras reservadas para el **RootNode TypeName** propiedad, se producirá el siguiente error al compilar el proyecto :  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 **Resolución**  
  
1.  Haga clic en el nodo rood hace referencia en el error y seleccione **propiedades**.  
  
2.  Para el **RootNode TypeName** propiedad, quite los caracteres no válidos o reservados palabras, por ejemplo, punto (.).  
  
###  <a name="BKMK_OraDBInvalBinding"></a>Advertencia de enlace no válido al utilizar el adaptador en Visual Studio  
 **Problema**  
  
 Cuando usa el adaptador para crear una aplicación en [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)] y abra el archivo de configuración (app.config) generado por el adaptador, verá una advertencia similar al siguiente:  
  
```  
The element 'bindings' has invalid child element 'oracleDBBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 **Causa**  
  
 Esta advertencia aparece porque la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] enlace, `oracleDBBinding`, se incluye no es un enlace estándar con el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)].  
  
 **Resolución**  
  
 Puede omitir esta advertencia de forma segura.  
  
###  <a name="BKMK_OraDBNotification"></a>BizTalk Server produce una excepción si se utiliza más de un esquema de notificación en la misma aplicación o el esquema de notificación en varias aplicaciones en el mismo host  
 **Problema**  
  
 BizTalk Server produce una excepción de XLANG o una excepción que indica que la aplicación no encuentra la especificación de documento porque varios esquemas coincida con el tipo de mensaje.  
  
 **Causa**  
  
 Esto se debe a alguno de los siguientes:  
  
-   Ha generado más de un esquema de notificación en un proyecto de BizTalk Server, implementado en una aplicación de BizTalk Server y, a continuación, se ejecutó la aplicación para recibir notificaciones de la base de datos de Oracle. Dado que los esquemas de notificación son comunes, hay un conflicto entre los esquemas que se implementan en la aplicación de BizTalk Server.  
  
-   En el caso de varios proyectos, ha generado un esquema de notificación para cada uno de los proyectos que se implementan cada proyecto a una aplicación de BizTalk Server independiente en el mismo host de BizTalk Server y, a continuación, se ejecutaba una aplicación o aplicaciones reciban notificaciones de la base de datos de Oracle. Dado que los esquemas y los ensamblados son accesibles a través de las aplicaciones de BizTalk Server, hay un conflicto entre los esquemas comunes implementados en aplicaciones de BizTalk Server y los ensamblados.  
  
 **Resolución**  
  
 Usar un único archivo de esquema de notificación para una aplicación de BizTalk Server. Si tiene que usar el esquema de notificación de varias aplicaciones de BizTalk Server en el mismo host, crear una aplicación que contenga un único esquema de notificación y, a continuación, utilice el esquema de notificación de todas las demás aplicaciones de BizTalk Server.  
  
###  <a name="BKMK_MemUsage"></a>Uso de memoria y subproceso recuento aumenta cuando se usa el adaptador en una operación de entrada de transacción  
 **Problema**  
  
 En una operación de entrada transacción, como el sondeo, **si no hay ningún dato disponible en la tabla se sondean,** y el adaptador while sigue sondeando, durante un período de tiempo experimente un aumento en el uso de memoria y el número de subprocesos.  
  
 **Causa**  
  
 **Si no hay ningún dato disponible en la tabla se sondean**, después cada ciclo de tiempo de espera de recepción [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] genera un nuevo subproceso para continuar con la operación de sondeo. Por lo tanto, el uso de memoria y el número de subprocesos aumenta durante un período de tiempo. Sin embargo, si la tabla se sondean, tiene algunos datos, sigue el mismo subproceso realizar todos los sondeos subsiguientes.  
  
 **Resolución**  
  
 Se recomienda establecer el **ReceiveTimeout** para el valor máximo posible, que es 24.20:31:23.6470000 (24 días) para que se genera un subproceso nuevo solo cada 24 días. Esto garantizará que el recuento de subprocesos y de uso de memoria no aumente demasiado demasiado pronto.  
  
> [!NOTE]
>  Si se ha establecido SqlAdapterInboundTransactionBehavior, asegúrese de que el TransactionTimeout también está configurado para el valor máximo posible, que es 24.20:31:23.6470000 (24 días). Al utilizar esta solución alternativa, podemos agregar la SqlAdapterInboundTransactionBehavior sólo si el nivel de aislamiento de transacción debe estar configurado. En caso contrario, es una práctica recomendada para quitar ese comportamiento.  
  
 Para obtener más información sobre la **ReceiveTimeout** enlace de propiedad, vea [leer acerca de las propiedades de enlace del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md). Para obtener instrucciones sobre cómo especificar propiedades de enlace, consulte [configurar las propiedades de enlace de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).  
  
> [!NOTE]
>  Al usar el adaptador con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], establecer el tiempo de espera en un valor grande no afecta a la funcionalidad del adaptador.  
  
## <a name="see-also"></a>Vea también  
[Solucionar problemas del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)  
[Solucionar problemas de instalación con el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-installation-issues-with-the-oracle-database-adapter.md)