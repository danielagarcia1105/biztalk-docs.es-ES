---
title: Solucionar problemas de funcionamiento con el adaptador de BizTalk | Documentos de Microsoft
description: "Problemas comunes y soluciones para el adaptador de Siebel en el módulo de adaptador de BizTalk (BAP)"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 74d152d9-9893-4f93-894a-350bae8be7bd
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62d1ffae1318f4d04f7bd61ef27dd24fd1d5a2b7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-operational-issues-with-the-siebel-adapter"></a>Solucionar problemas de funcionamiento con el adaptador de Siebel
Esta sección proporciona una ubicación centralizada para obtener información acerca de problemas de funcionamiento que pueden surgir al usar el [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].  
  
## <a name="enabling-tracing"></a>La habilitación del seguimiento  
 Para obtener información acerca del seguimiento de soporte técnico en el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], consulte [el seguimiento de diagnóstico y registro de mensajes para el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/diagnostic-tracing-and-message-logging-for-the-siebel-adapter.md).  
  
## <a name="known-issues"></a>Problemas conocidos  
 Los siguientes son algunos problemas y soluciones recomendadas que pueden surgir al usar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
  
###  <a name="BKMK_SiebelBindingError"></a>Error al cargar los enlaces del adaptador  
 **Problema**  
  
 Al intentar iniciar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], la interfaz gráfica de usuario produce el siguiente error:  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 **Causa**  
  
 Al iniciar la [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], WCF carga los enlaces del adaptador para todos los adaptadores instalados. En cambio, los enlaces del adaptador están depende del software de cliente de aplicación empresarial específico. Por lo tanto, podría enfrentarse a este problema para uno o ambos de los siguientes motivos:  
  
-   El software de cliente LOB necesario no está instalado en el equipo donde instaló el adaptador.  
  
-   Se realizó una instalación "Típica" o "Completar" del adaptador, que se instala todos los adaptadores de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Sin embargo, las bibliotecas de cliente podrían estar instaladas para solo una aplicación empresarial. Como resultado, la interfaz gráfica de usuario produce un error al cargar los enlaces para los demás adaptadores.  
  
 **Resolución**  
  
-   Asegúrese de que las versiones de cliente necesarias están instaladas en el equipo donde instaló el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].  
  
-   Asegúrese de que se realiza una instalación personalizada de los adaptadores para instalar a sólo el adaptador que necesita.  
  
###  <a name="BKMK_SiebelDispAdap"></a>El adaptador no se muestra en la lista de adaptadores en la consola de administración de BizTalk Server  
 **Problema**  
  
 A diferencia de la versión anterior de los adaptadores que se incluye con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] que acompaña a [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] no aparecen en la lista de adaptadores en la consola de administración de BizTalk Server.  
  
 **Causa**  
  
 La versión más reciente [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] es un enlace personalizado de WCF. Por lo tanto, aunque la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] muestra de la consola de administración de la [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], no muestra los enlaces personalizados de WCF y por lo tanto, no se mostrarán basadas en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].  
  
 **Resolución**  
  
 Puede agregar explícitamente la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, siga los pasos mencionados en [agregar el adaptador de Siebel a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).  
  
###  <a name="BKMK_SiebelConnecting"></a>Error al conectarse al sistema Siebel  
 **Problema**  
  
 El [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] produce el siguiente error al intentar conectarse al sistema Siebel:  
  
```  
Connecting to the system LOB has failed. Retrieving the COM class factory for component with CLSID {ID} failed due to the following error: 80040154  
```  
  
 **Causa**  
  
 El cliente Siebel Web no puede instalarse en el equipo.  
  
 **Resolución**  
  
 Asegúrese de que la versión admitida del cliente Siebel Web está instalada en el equipo. Consulte la Guía de instalación de cliente admitida y las versiones de servidor para Siebel. La Guía de instalación está disponible en \<unidad del sistema >: \Program [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents.  
  
###  <a name="BKMK_SiebelXMLRetrieve"></a>Error al recuperar el XML con más de 65536 nodos  
 **Problema**  
  
 El adaptador produce el siguiente error al recuperar la salida XML que tiene más de 65536 nodos.  
  
```  
Maximum number of items that can be serialized or deserialized in an object graph is '65536'.  
Change the object graph or increase the MaxItemsInObjectGraph quota.  
```  
  
 **Causa**  
  
 El adaptador no se puede serializar y deserializar un objeto con más de 65536 elementos.  
  
 **Resolución**  
  
 Puede solucionar este problema estableciendo la `maxItemsInObjectGraph` parámetro. Esto se puede establecer en cualquiera de las dos maneras siguientes:  
  
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
  
 Un ejemplo app.config será similar:  
  
```  
\<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  \<system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="NewBehavior">  
         <dataContractSerializer maxItemsInObjectGraph="65536000" />  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <client>  
      <endpoint   behaviorConfiguration="NewBehavior" binding="siebelBinding"  
       contract="IOutboundContract" name="siebel_ICalculator" />  
    </client>  
  \</system.serviceModel>  
</configuration>  
```  
  
###  <a name="BKMK_SiebelConnURI"></a>Error al especificar un URI de conexión para un puerto personalizado de WCF de BizTalk  
 **Problema**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]produce el siguiente error cuando se especifica un URI de conexión para conectarse al sistema Siebel.  
  
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
  
###  <a name="BKMK_SiebelPerfOps"></a>Error al realizar la operación en el sistema Siebel  
 **Problema**  
  
 El adaptador produce el siguiente error al realizar cualquier operación en el sistema Siebel mediante [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  
  
-   **Para[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]**  
  
    ```  
    System.ArgumentNullException: Value cannot be null.  
    ```  
  
 **Causa**  
  
 No se especifica la acción de WCF para el mensaje. WCF requiere una acción de SOAP que se especifique para cada operación, que informa al adaptador acerca de la operación se realizará en la aplicación de LOB.  
  
 **Resolución**  
  
 Especifica la acción de SOAP en el puerto de envío o como una propiedad de contexto de mensaje en una orquestación de BizTalk. Para obtener instrucciones, consulte [configurar la acción SOAP para Siebel](../../adapters-and-accelerators/adapter-siebel/configure-the-soap-action-for-siebel.md). Vea [mensajes y esquemas de mensaje](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md) para obtener una lista de acciones para cada operación.  
  
###  <a name="BKMK_SiebelXmlParsing"></a>XmlReaderParsingException debido a un nombre de operación incorrecto en la acción especificada  
 **Problema**  
  
 La consola de administración de BizTalk Server proporciona el siguiente error al enviar mensajes a un sistema Siebel:  
  
```  
Microsoft.ServiceModel.Channels.Common.XmlReaderParsingException: Invalid argument:  
\<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
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
  
 En el formato anterior, el nombre de la operación se rige por la operación que eligió al generar el esquema. Por ejemplo, si ha generado el esquema para una operación de consulta en un componente de negocio de Siebel, el nombre de la operación en la acción será "Query". Sin embargo, el nombre de la operación en el puerto lógico creado en la orquestación de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] podría ser diferente.  
  
 **Resolución**  
  
 Asegúrese de que los nombres de operación en el puerto lógico de ambas (en la orquestación de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) y el puerto físico (en la consola de administración de BizTalk Server) son los mismos.  
  
###  <a name="BKMK_SiebelTerminate"></a>No finalizar la aplicación con el adaptador de Siebel  
 **Problema**  
  
 Una aplicación que utiliza el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] con Siebel no termina con la versión 7.5 de cliente.  
  
 **Causa**  
  
 Esto es debido a un problema de cliente de Siebel donde el proceso no finaliza al cerrar la sesión de un servidor de Siebel.  
  
 **Resolución**  
  
 Asegúrese de que tiene la revisión 7.5.3.17 instalado para el servidor de Siebel, junto con la corrección rápida QF0H05.  
  
###  <a name="BKMK_SiebelHang"></a>Adaptador de Siebel puede bloquearse si se reinicia el servidor de Siebel  
 **Problema**  
  
 Si se reinicia el servidor de Siebel mientras el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] está enviando un mensaje en el servidor de Siebel mediante, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] puede bloquearse.  
  
 **Resolución**  
  
 Reinicie la instancia de host de aplicación de BizTalk. Para hacerlo desde la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] expanda consola de administración, en el árbol de consola **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, haga clic en **instancias de Host**. En el panel derecho, haga clic en el nombre de host y, a continuación, seleccione **reiniciar**.  
  
###  <a name="BKMK_SiebelAction"></a>El adaptador no reconoce la acción en el puerto físico incluso aunque use el archivo de enlace generado por el complemento Consume Adapter Service para crear los puertos  
 **Problema**  
  
 Después de usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar el esquema para una operación específica en el sistema Siebel, el complemento también crea un archivo de enlace de puerto. Puede importar este enlace archivo usando el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración para crear puertos físicos en BizTalk Server. Sin embargo, cuando se envían mensajes al sistema Siebel usando estos puertos, el adaptador no se puede entender la acción especificada en el puerto y produce un error similar al siguiente:  
  
```  
Microsoft.ServiceModel.Channels.Common.UnsupportedOperationException: Incorrect Action   
\<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<op_name>" Action="<action>" />  
</BtsActionMapping>. Correct the specified Action, or refer to the documentation on the allowed formats for the Actions.  
```  
  
 **Causa**  
  
 Cuando crea puertos lógicos en una orquestación de BizTalk, especificar ciertos nombres para las operaciones en los puertos o simplemente utilizar los nombres predeterminados como Operation_1, Operation_2, etcetera. Sin embargo, en el archivo de enlace generado por el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], el nombre de la operación es el mismo que el nombre de la operación para la que generar los metadatos. Por ejemplo, si genera metadatos para la operación de inserción en el componente de negocio de la cuenta, la acción se establecerá al siguiente:  
  
```  
<Operation Name="Insert" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert" />  
```  
  
 Cuando se importa el archivo de enlace, la misma acción que se establece en el puerto físico. Por lo tanto, los nombres de operación en el puerto lógico (Operation_1, Operation_2, etc.) no coincide con los nombres de operación especificados en la acción en el puerto físico, lo que produce un error.  
  
 **Resolución**  
  
 Asegúrese de que el nombre de la operación en el puerto lógico es el mismo que el nombre de operación especificado como parte de la acción en el puerto físico. Realice una de las siguientes operaciones:  
  
-   Cambiar el nombre de la operación en el puerto lógico de orquestación de BizTalk de Operation_1, etc. a la operación para el que genera metadatos, por ejemplo Insert.  
  
-   Cambiar el nombre de la operación en la acción en el puerto físico para el nombre de la operación en el puerto lógico. Por ejemplo, puede cambiar la acción en el puerto físico que es similar al siguiente:  
  
    ```  
    <Operation Name="Operation_1" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert" />  
    ```  
  
###  <a name="BKMK_SiebelXMLEncode"></a>Adaptador de Siebel no controla los objetos de Siebel con cadenas XML codificado en el nombre  
 **Problema**  
  
 El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no se puede realizar operaciones relacionadas con objetos de Siebel (objetos de negocios, los componentes empresariales, servicios para la empresa, lista de selección, métodos, campos, argumentos, etcetera) que contienen cadenas XML codificado en su nombre. Por ejemplo, el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] no podrá invocar un método de servicio de negocio con el nombre Time_x0020_Stamp.  
  
 **Resolución**  
  
 Asegúrese de que los objetos de Siebel no contienen cadenas XML codificado en su nombre.  
  
###  <a name="BKMK_SiebelRootNode"></a>Error con RootNode TypeName en proyectos de BizTalk  
 **Problema**  
  
 En un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], si los esquemas generan a partir del [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] contiene caracteres no válidos o palabras reservadas para el **RootNode TypeName** propiedad, se producirá el siguiente error al compilar el proyecto :  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 **Resolución**  
  
1.  Haga clic en el nodo rood hace referencia en el error y seleccione **propiedades**.  
  
2.  Para el **RootNode TypeName** propiedad, quite los caracteres no válidos o reservados palabras, por ejemplo, punto (.).  
  
###  <a name="BKMK_SiebelVS2008"></a>Advertencia de enlace no válido al utilizar el adaptador en Visual Studio  
 **Problema**  
  
 Cuando usa el adaptador para crear una aplicación en [!INCLUDE[vs2010](../../includes/vs2010-md.md)] y abra el archivo de configuración (app.config) generado por el adaptador, verá una advertencia similar al siguiente:  
  
```  
The element 'bindings' has invalid child element 'siebelBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 **Causa**  
  
 Esta advertencia aparece porque la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] enlace, `siebelBinding`, se incluye no es un enlace estándar con el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)].  
  
 **Resolución**  
  
 Puede omitir esta advertencia de forma segura.  
  
## <a name="see-also"></a>Vea también  
[Solucionar problemas del adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)