---
title: Solucionar problemas de funcionamiento con el adaptador SAP en BizTalk | Documentos de Microsoft
description: "Comunes de los errores, problemas y soluciones con mySAP adaptador en el módulo de adaptador de BizTalk (BAP)"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb0f005b-7548-478b-8243-69e07c29d02c
caps.latest.revision: "32"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f98a4f7b9ed0a504c3adc245916ca9d39af7a7fe
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="troubleshoot-operational-issues-with-the-sap-adapter"></a>Solucionar problemas de funcionamiento con el adaptador SAP
Esta sección describe el uso de técnicas de solución de problemas para resolver errores de operaciones que pueden surgir al usar [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].  
  
### <a name="enable-tracing"></a>Habilitar el seguimiento  
 Para obtener información acerca del seguimiento de soporte técnico en el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], consulte [el seguimiento de diagnóstico y registro de mensajes para el adaptador SAP](../../adapters-and-accelerators/adapter-sap/diagnostic-tracing-and-message-logging-for-the-sap-adapter.md).  
  
##  <a name="client_dll"></a>Error al cargar el enlace  
 **Problema**  
  
 Al intentar iniciar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]o [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], la interfaz gráfica de usuario produce el siguiente error:  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 **Causa**  
  
 Al iniciar la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] carga los enlaces del adaptador para todos los adaptadores instalados. En cambio, los enlaces del adaptador están depende del software de cliente específico para la aplicación de empresa. Es posible que tenga este problema para uno o ambos de los siguientes motivos:  
  
-   El software de cliente LOB necesario no está instalado en el equipo donde instaló el adaptador.  
  
-   Se realizó una instalación típica o completar del adaptador, que se instala todos los adaptadores incluidos en el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Sin embargo, podrían instalarse las bibliotecas de cliente LOB para solo una aplicación empresarial. Como resultado, la interfaz gráfica de usuario produce un error al cargar los enlaces para los demás adaptadores.  
  
 **Resolución**  
  
-   Asegúrese de que se realiza una instalación personalizada de los adaptadores para instalar a sólo el adaptador que necesita.  
  
-   Asegúrese de que las versiones de cliente LOB necesarias se instalan en el equipo donde instaló el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. [Los sistemas LOB](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx) enumera las versiones compatibles. El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] también requiere determinado archivos DLL interactuar con el sistema SAP. Para obtener más información acerca de los archivos DLL requerida por el adaptador, vea [instalar RFC personalizado para el proveedor de datos para SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).
  
##  <a name="BKMK_SAPDisplay"></a>El adaptador SAP es falta en la consola de administración de BizTalk  
 **Problema**  
  
El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] incluido con [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] no aparecen en la lista de adaptadores en la consola de administración de BizTalk Server.  
  
 **Causa**  
  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] es un enlace personalizado de WCF. Por lo tanto, aunque la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] muestra de la consola de administración de la [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], no muestra los enlaces personalizados de WCF y por lo tanto, no se mostrarán basadas en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
 **Resolución**  
  
 Puede agregar explícitamente la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, siga los pasos mencionados en [agregar el adaptador SAP a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).  
  
##  <a name="BKMK_SAPConnOpen"></a>Error al abrir una conexión a SAP no tienen archivos DLL  
 **Problema**  
  
 Al intentar abrir una conexión con el sistema SAP mediante el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], aparece un cuadro de diálogo en el sistema SAP, que le informa de que faltan algunos archivos DLL.  
  
 **Causa**  
  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] librfc32u.dll se utiliza para establecer una conexión con el sistema SAP. Librfc32u.dll, a su vez, se requiere un conjunto de archivos DLL en la función. Este error aparece si estas DLL compatibles no se agregan a la variable de ruta de acceso en el equipo donde el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] está instalado.  
  
 **Resolución**  
  
 Hacer referencia a la tabla proporcionada como una resolución para el [Error al cargar los enlaces del adaptador](#client_dll) problema. La tabla enumeran los archivos DLL auxiliares necesarias para interactuar con el sistema SAP mediante el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
##  <a name="BKMK_SAPXmlRetrieve"></a>Error al recuperar el XML con más de 65.536 nodos  
 **Problema**  
  
 El adaptador produce el siguiente error al recuperar la salida XML que tiene más de 65.536 nodos.  
  
```  
Maximum number of items that can be serialized or deserialized in an object graph is '65536'.  
Change the object graph or increase the MaxItemsInObjectGraph quota.  
```  
  
 **Causa**  
  
 El adaptador no se puede serializar y deserializar un objeto con más de 65.536 elementos.  
  
 **Resolución**  
  
 Puede solucionar este problema estableciendo la `maxItemsInObjectGraph` parámetro de cualquiera de las dos maneras siguientes:  
  
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
  
 Un ejemplo app.config tendrá un aspecto similar al siguiente.  
  
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
      <endpoint   behaviorConfiguration="NewBehavior" binding="sapBinding"  
       contract="IOutboundContract" name="sap_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
##  <a name="BKMK_SAPConnURI"></a>Error al escribir un URI de conexión para un puerto personalizado de WCF en BizTalk Server  
 **Problema**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]produce el siguiente error cuando se especifica un URI de conexión para conectarse al sistema SAP.  
  
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
  
##  <a name="BKMK_SAPOperate"></a>Error de System.ArgumentNullException mientras se completa una operación en SAP  
 **Problema**  
  
 El adaptador produce el siguiente error al realizar cualquier operación en el sistema SAP mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  
  
```  
System.ArgumentNullException: Value cannot be null.  
```  
  
 **Causa**  
  
 No se especifica la acción de WCF para el mensaje. WCF requiere una acción de SOAP que se especifique para cada operación, que informa al adaptador acerca de la operación se realizará en la aplicación de LOB.  
  
 **Resolución**  
  
 Especifica la acción de SOAP en el puerto de envío o como una propiedad de contexto de mensaje en una orquestación de BizTalk. Para obtener instrucciones, consulte [configurar la acción SOAP para el sistema SAP](../../adapters-and-accelerators/adapter-sap/configure-the-soap-action-for-the-sap-system.md). Vea [mensajes y esquemas de mensaje](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md) para ver una lista de acciones para cada operación.  
  
##  <a name="BKMK_SAPXmlParsing"></a>XmlReaderParsingException debido a un nombre de operación incorrecto en la acción especificada  
 **Problema**  
  
 La consola de administración de BizTalk Server produce el siguiente error al enviar mensajes a un sistema SAP:  
  
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
  
 En el formato anterior, el nombre de la operación se rige por la operación que eligió al generar el esquema. Por ejemplo, si ha generado el esquema para RFC_CUSTOMER_GET, el nombre de la operación en la acción será "RFC_CUSTOMER_GET". Sin embargo, el nombre de la operación en el puerto lógico creado en la orquestación de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] podría ser diferente.  
  
 **Resolución**  
  
 Asegúrese de que los nombres de operación en el puerto lógico de ambas (en la orquestación de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) y el puerto físico (en la consola de administración de BizTalk Server) son los mismos.  
  
##  <a name="BKMK_SAPHundredCons"></a>Error al abrir más de 100 conexiones para SAP  
 **Problema**  
  
 El adaptador devuelve la siguiente excepción al abrir más de 100 conexiones al sistema SAP.  
  
```  
Microsoft.ServiceModel.Channels.Common.ConnectionException: ErrorCode=RFC_OK. ErrorGroup=RFC_ERROR_COMMUNICATION. SapErrorMessage=Connect to SAP gateway failed  
Connect_PM  GWHOST=<gw_host>, GWSERV=<gw_serv>, SYSNR=<sys_number>  
LOCATION    CPIC (TCP/IP) on local host with Unicode  
ERROR       max no of 100 conversations exceeded  
```  
  
 **Causa**  
  
 De forma predeterminada, SAP no habilita más de 100 conexiones en el sistema.  
  
 **Resolución**  
  
 Para aumentar el número máximo de conexiones, debe crear una variable de entorno en el equipo que tenga las bibliotecas de cliente SAP instalado y configurado en un valor numérico. El valor especificado para esta variable de entorno es el número máximo de conexiones que pueden realizarse en el sistema SAP. Crear la variable de entorno con los detalles siguientes:  
  
-   **Nombre de la variable**: CPIC_MAX_CONV  
  
-   **Valor de la variable**: cualquier valor numérico positivo. Por ejemplo, para habilitar 200 conexiones en el sistema SAP, especifique el valor 200.  
  
 Para obtener instrucciones sobre cómo crear una variable de entorno, consulte "Cómo crear Variables del sistema en Windows 2000" en [http://go.microsoft.com/fwlink/?LinkId=95020](http://go.microsoft.com/fwlink/?LinkId=95020).  
  
##  <a name="BKMK_SAPIDOCMetadata"></a>Generar errores o recuperar los metadatos para IDOC  
 **Problema**  
  
 Al generar metadatos para la **recepción** operación para un IDOC en un sistema SAP, la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] produce el siguiente error.  
  
```  
Error while retrieving or generating the WSDL.  
Adapter message: Details: ErrorCode=RFC_EXCEPTION.  
ErrorGroup=RFC_ERROR_APPLICATION_EXCEPTION. SapErrorMessage= OBJECT_UNKNOWN.  
AdapterErrorMessage=Error returned by RfcCallReceiveEx while calling RFC: IDOCTYPE_READ_COMPLETE.  
```  
  
 **Causa**  
  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] usa la RFC IDOCTYPE_READ_COMPLETE para recuperar los metadatos de la **recepción** operación para un IDOC. Invocar esta RFC requiere permisos de usuario específico en el sistema SAP. Para generar los metadatos, si se ha conectado al sistema SAP mediante una credencial que no tiene permiso para invocar la RFC IDOCTYPE_READ_COMPLETE, la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] produce un error.  
  
 **Resolución**  
  
 Inicie sesión en la GUI de SAP con las mismas credenciales que se hubiera usado para el adaptador. Navegue hasta la transacción SE37 y escriba el nombre de la solicitud de cambio para ejecutar como IDOCTYPE_READ_COMPLETE.  
  
 Para los parámetros de entrada PI_IDOCTYP y PI_CIMTYP, escriba los valores correspondientes a lo IDoc personalizado. Para los parámetros PI_VERSION y PI_RELEASE, especifique los mismos valores que se haya elegido en la interfaz de usuario de metadatos de adaptador. Y presione F8 para ejecutar.  
  
 Debe obtener la misma excepción como lo que el adaptador recibe, con más información sobre el problema.  
  
 Si está aún no se ha podido resolver el problema, generar un esquema para el **ReceiveIdoc** operación en lugar de la **recepción** operación. En este caso, el adaptador SAP no usa IDOCTYPE_READ_COMPLETE y no produce ningún error.  
  
##  <a name="BKMK_SAPIDOCReceive"></a>Error al enviar o recibir IDOC que haya no lanzados segmentos  
 **Problema**  
  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] ofrece un XmlReaderParsingException al enviar IDOC (mediante **enviar** operación) o recibir IDOC (mediante **recepción** operación) que han no lanzados segmentos.  
  
 **Causa**  
  
 IDOC se constituye de segmentos. Durante la generación de metadatos, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] recupera todos los segmentos de lanzamiento que se encuentran en el sistema SAP. Sin embargo, si el cliente de adaptador usa los metadatos para realizar una operación como la recepción de un IDOC, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] ofrece un XmlReaderParsingException. Esto ocurre porque cuando se recibe el IDOC, el sistema SAP posible que haya enviado algunos segmentos no lanzados así, los metadatos para el que no fue generado por el adaptador.  
  
 **Resolución**  
  
 Realice una de las siguientes acciones:  
  
-   Actualizar el sistema SAP mediante la aplicación de revisiones apropiadas para los segmentos no lanzados.  
  
-   Use **SendIdoc** o **ReceiveIdoc** operaciones para enviar y recibir IDOC respectivamente. Para obtener más información acerca de estas operaciones, vea [operaciones en IDOC en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md).  
  
##  <a name="BKMK_SAPIDOCSend"></a>Error al enviar el archivo sin formato IDOC a SAP que se han recibido mediante el FilePort de SAP  
 **Problema**  
  
 Si intenta enviar (mediante **enviar** operación) un IDOC de archivo sin formato a un sistema SAP que se ha generado mediante una FilePort de SAP, el analizador de archivos sin formato en la orquestación de BizTalk no puede convertir el archivo flatf en un formato XML, con lo que se producen errores en el IDOD **enviar** operación.  
  
 **Causa**  
  
 Cuando el sistema SAP genera un IDOC mediante un FilePort, que recorta desactivar todos los espacios en blanco al final de un segmento de. Sin embargo, el analizador de archivos sin formato espera que los datos del último campo en el segmento que se va a estar presente para convertir correctamente el archivo sin formato en XML. Como los espacios vacíos que no se encuentran en el segmento, el analizador de archivos sin formato no se puede analizar el archivo sin formato a XML.  
  
 **Resolución**  
  
 Para este tipo IDOC de archivo sin formato generado mediante la FilePort de SAP, use la **SendIdoc** operación en su lugar. Para obtener más información acerca de esta operación, vea [operaciones en IDOC en SAP](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md).  
  
##  <a name="BKMK_SAPRecIDOCCompat"></a>Error al recibir IDOC desde SAP si EnableBizTalkCompatibilityMode propiedad se establece en true  
 **Problema**  
  
 La siguiente excepción se produce al recibir un IDOC con el **EnableBizTalkCompatibilityMode** enlace propiedad establecida en true:  
  
```  
System.Exception: Loading property information list by namespace failed or property not found in the list. Verify that the schema is deployed properly.  
```  
  
 **Causa**  
  
 Si la propiedad de enlace **EnableBizTalkCompatibilityMode** está establecido en **true**, debe agregar el esquema de propiedades de BizTalk DLL para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] como un recurso en la aplicación de BizTalk, es decir, el en el que se implementa el proyecto de aplicación.  
  
 **Resolución**  
  
 El nombre para el esquema de propiedad de BizTalk para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] es *Microsoft.Adapters.SAP.BiztalkPropertySchema.dll*. Este servicio se instala mediante el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] el programa de instalación en \<unidad de instalación\>: \ Archivos de programa\Microsoft BizTalk adaptador Pack\bin. Realice las tareas siguientes para agregar este ensamblado como un recurso en la aplicación de BizTalk.  
  
#### <a name="add-an-assembly-as-a-resource-in-biztalk-application"></a>Agregar un ensamblado como un recurso de aplicación de BizTalk  
  
1.  Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
2.  En el árbol de consola, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, la aplicación a la que desea agregar un ensamblado de BizTalk.  
  
3.  Expanda **aplicaciones** y la aplicación a la que desea agregar un ensamblado de BizTalk.  
  
4.  Haga clic en **recursos**, seleccione **agregar**y, a continuación, haga clic en **ensamblados de BizTalk**.  
  
5.  Haga clic en **agregar**, navegue hasta la carpeta que contiene el archivo de ensamblado de BizTalk, seleccione el archivo de ensamblado de BizTalk y, a continuación, haga clic en **abiertos**.  
  
6.  En **opciones**, especifique las opciones para instalar el ensamblado de BizTalk en la GAC y, a continuación, haga clic en **Aceptar**.  
  
##  <a name="BKMK_SAPIDOCValidate"></a>Error en la validación al recibir IDOC desde un sistema SAP  
 **Problema**  
  
 Un IDOC recibido desde un sistema SAP no puede validar con un mensaje de error similar al siguiente:  
  
```  
There was a failure executing the receive pipeline: "Microsoft.BizTalk.DefaultPipelines.XMLReceive, Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral, PublicKeyToken=<token>"  
Source: "Pipeline " Receive Port: "ReceiveIdoc" URI: "<connection uri>"  
Reason: The document failed to validate because of the following error:  
"The 'http://Microsoft.LobServices.Sap/2007/03/Types/Idoc/3/CREMAS03//620:TAXBS' element has an invalid value according to its data type."  
```  
  
 **Causa**  
  
 Los metadatos generados para recibir un IDOC contienen los valores permitidos que se pueden recibir de una determinada columna como parte de la operación de recepción. Estos valores se exponen como enumeración de los metadatos generados. Sin embargo, cuando realmente se recibe el IDOC, el valor recibido podría ser diferente de los valores enumerados. Por lo tanto, la operación de recepción se produce un error al validar los valores. Por ejemplo, en el error anterior mensaje falla la validación de la columna TAXBS.  
  
 **Resolución**  
  
 Debe editar manualmente la enumeración en el esquema (para los proyectos de BizTalk) o el proxy de cliente (para los proyectos de .NET mediante WCF el modelo de servicio) para incluir el valor recibido desde el sistema SAP.  
  
##  <a name="BKMK_SAPFFIDOC"></a>IDOC de archivo sin formato, antes y después de convertir a XML, no es idéntico  
 **Problema**  
  
 Si utiliza un analizador de archivos planos para convertir un IDOC de archivo sin formato a un XML con el esquema y, a continuación, convertir el código XML en un IDOC de archivo sin formato a través de una canalización mediante el esquema, lo dos IDOC de archivo sin formato no es idéntico.  
  
 **Causa**  
  
 Al generar el XML de un IDOC de archivo sin formato, el analizador de archivos planos no genera los nodos XML con valores en blanco. Cuando este XML se convierte a un archivo sin formato, los nodos que faltan en el código XML no se reflejan en el IDOC de archivo sin formato. Por lo tanto, el IDOC de archivo sin formato no es idéntico.  
  
 **Resolución**  
  
 En el esquema que se utiliza para convertir el archivo sin formato XML y viceversa, dentro de la definición de nodo de "Envío" o "Recepción", haga lo siguiente:  
  
1.  Establecer el **suppress_empty_nodes** propiedad **false** y establezca el **generate_empty_nodes** propiedad **true**. De forma predeterminada, el **suppress_empty_nodes** propiedad está establecida en **true** y **generate_empty_nodes** propiedad está establecida en **false**, y por lo tanto, todos los nodos vacíos no se reflejan en el archivo XML.  
  
2.  El archivo sin formato puede contener un retorno de carro adicional al final. Puede establecer la **suppress_trailing_delimiters** propiedad **Sí** para evitar este retorno de carro adicional. Esta propiedad también se expone como la **Suprimir delimitadores finales** propiedad si abre el esquema en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].  
  
##  <a name="BKMK_SAPAction"></a>Error de acción incorrecta con un puerto físico crear con un archivo de enlace  
 **Problema**  
  
 Después de usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar el esquema para una operación específica en el sistema SAP, el complemento también crea un archivo de enlace de puerto. Puede importar este enlace archivo usando el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para crear puertos físicos en BizTalk Server. Sin embargo, cuando se envían mensajes al sistema SAP usando estos puertos, el adaptador no se puede entender la acción especificada en el puerto y produce un error similar al siguiente:  
  
```  
Microsoft.ServiceModel.Channels.Common.UnsupportedOperationException: Incorrect Action   
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<op_name>" Action="<action>" />  
</BtsActionMapping>. Correct the specified Action, or refer to the documentation on the allowed formats for the Actions.  
```  
  
 **Causa**  
  
 Cuando crea puertos lógicos en una orquestación de BizTalk, especificar ciertos nombres para las operaciones en los puertos o simplemente utilizar los nombres predeterminados como Operation_1, Operation_2, etcetera. Sin embargo, en el archivo de enlace generado por el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], el nombre de la operación es el mismo que el nombre de la operación para la que generar los metadatos. Por ejemplo, si genera metadatos para RFC_CUSTOMER_GET, se establecerá la acción a la siguiente:  
  
```  
<Operation Name="RFC_CUSTOMER_GET" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET" />  
```  
  
 Cuando se importa el archivo de enlace, la misma acción que se establece en el puerto físico. Por lo tanto, los nombres de operación en el puerto lógico (Operation_1, Operation_2, etc.) no coincide con los nombres de operación especificados en la acción en el puerto físico, lo que produce un error.  
  
 **Resolución**  
  
 Asegúrese de que el nombre de la operación en el puerto lógico es el mismo que el nombre de operación especificado como parte de la acción en el puerto físico. Realice una de las siguientes operaciones:  
  
-   Cambiar el nombre de la operación en el puerto lógico de orquestación de BizTalk de Operation_1, etc. a la operación para el que genera metadatos, por ejemplo RFC_CUSTOMER_GET.  
  
-   Cambiar el nombre de la operación en la acción en el puerto físico para el nombre de la operación en el puerto lógico. Por ejemplo, puede cambiar la acción en el puerto físico que es similar al siguiente:  
  
    ```  
    <Operation Name="Operation_1" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET" />  
    ```  
  
##  <a name="BKMK_SAPTableParams"></a>El mensaje de respuesta de una operación que se ejecutó en SAP no contiene ningún parámetro de tabla  
 **Causa**  
  
 Si utiliza el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] para ejecutar una operación en el sistema SAP que devuelve un gran número de tablas y cada tabla tiene un gran número de registros, que se importe a un conjunto de datos grande que se devuelve como parte del mensaje de respuesta desde el sistema SAP. Por lo tanto, de forma predeterminada, la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] no devuelve ningún parámetro de tabla como parte del mensaje de respuesta.  
  
 **Resolución**  
  
 Puede solicitar las tablas que desea [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] para devolver como parte de la respuesta. Para ello, puede proporcionar un parámetro de una tabla vacía como parte del mensaje de solicitud que envía al sistema SAP. Por ejemplo, `<table_parameter_name />`.  
  
##  <a name="BKMK_SAPIncorrectCreds"></a>Los clientes de adaptador no recibir la respuesta de SAP
 **Problema**  
  
 Al usar los adaptadores con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], si las credenciales de WCF-custom puerto son correctos, no se procesan los mensajes de solicitud de envío. Después de especificar las credenciales correctas, el mensaje se envía al sistema SAP y se recibe una respuesta. Sin embargo, el mensaje de respuesta no está disponible para el puerto de salida.  
  
 **Resolución**  
  
 Reinicie la instancia de host de BizTalk.  
  
##  <a name="BKMK_SAPInboundConn"></a>Problemas de conectividad de recibir un mensaje entrante desde el servidor SAP  
 **Problema**  
  
 Muestra el siguiente error sólo al recibir un mensaje entrante desde el servidor SAP utilizando un WCF-Custom puerto de recepción para el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].  
  
```  
The Messaging Engine failed to add a receive location "<location_name>" with URL "<connection URI>" to the adapter "WCF-Custom".  
Reason: "Microsoft.Adapters.SAP.RFCException: Details: ErrorCode=RFC_OK. ErrorGroup=RFC_ERROR_COMMUNICATION. SapErrorMessage=Connect to SAP gateway failed  
Connect_PM  TPNAME=<name>, GWHOST=<host>, GWSERV=<server>  
```  
  
 Sin embargo, es posible correctamente enviar mensajes al sistema SAP mediante un WCF-Custom puerto de envío.  
  
 **Resolución**  
  
 Instale la GUI de SAP en el mismo equipo donde se está ejecutando al cliente de adaptador e intente volver a recibir el mensaje entrante. Para obtener más información acerca de cómo instalar la GUI de SAP, consulte la documentación de SAP.  
  
##  <a name="BKMK_SAPRootNode"></a>Error con RootNode TypeName en proyectos de BizTalk  
 **Problema**  
  
 En un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], si los esquemas generan a partir del [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] contiene caracteres no válidos o palabras reservadas para el **RootNode TypeName** propiedad, se producirá el siguiente error al compilar el proyecto :  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 **Resolución**  
  
1.  Haga clic en el nodo rood hace referencia en el error y seleccione **propiedades**.  
  
2.  Para el **RootNode TypeName** propiedad, quite los caracteres no válidos o reservados palabras, por ejemplo, punto (.).  
  
##  <a name="BKMK_SAPVS2008"></a>Advertencia de enlace no válido al utilizar el adaptador en Visual Studio  
 **Problema**  
  
 Cuando se utiliza el adaptador para crear una aplicación en Visual Studio y abra el archivo de configuración (app.config) generado por el adaptador, verá una advertencia similar al siguiente:  
  
```  
The element 'bindings' has invalid child element 'sapBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 **Causa**  
  
 Esta advertencia aparece porque la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] enlace, `sapBinding`, se incluye no es un enlace estándar con el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)].  
  
 **Resolución**  
  
 Puede omitir esta advertencia de forma segura.  
  
##  <a name="BKMK_SAPSimilarSchema"></a>Excepción de XLANG en BizTalk Server
 **Problema**  
  
 BizTalk Server produce una excepción de XLANG o una excepción que indica que la aplicación no encuentra la especificación de documento porque varios esquemas coincida con el tipo de mensaje.  
  
 **Causa**  
  
 Esto se debe a alguno de los siguientes:  
  
-   Ha generado más de un esquema de una operación genérica (por ejemplo, SendIdoc y ReceiveIdoc) en un proyecto de BizTalk Server, implementado en una aplicación de BizTalk Server y, a continuación, se ejecutó la aplicación para realizar operaciones respectivas en un sistema SAP. Dado que los esquemas son comunes, hay un conflicto entre los esquemas que se implementan en la aplicación de BizTalk Server.  
  
-   En el caso de varios proyectos, tiene un esquema de operación genérica generado para cada uno de los proyectos de BizTalk Server, implementado cada proyecto en otro aplicación de BizTalk Server en el mismo host y, a continuación, se ejecutó de una aplicación o las aplicaciones puedan realizar respectivos operaciones en un sistema SAP. Dado que los esquemas y los ensamblados son accesibles a través de las aplicaciones de BizTalk Server, hay un conflicto entre los esquemas comunes implementados en aplicaciones de BizTalk Server y los ensamblados.  
  
 **Resolución**  
  
 Utilizar un archivo de esquema de operación genérico único para una aplicación de BizTalk Server. Si necesita usar un esquema de operación genérica en varias aplicaciones de BizTalk Server en el mismo host, crear una aplicación que contiene un esquema de operación genérico único y, a continuación, utilice el esquema de operación genérica de todas las demás aplicaciones de BizTalk Server.  
  
## <a name="see-also"></a>Vea también  
[Solucionar problemas del adaptador SAP](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)