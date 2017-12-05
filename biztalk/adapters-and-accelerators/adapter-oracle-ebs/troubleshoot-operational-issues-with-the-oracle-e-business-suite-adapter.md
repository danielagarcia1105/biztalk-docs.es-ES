---
title: Solucionar problemas de funcionamiento con el adaptador de Oracle E-Business Suite | Documentos de Microsoft
description: "Problemas comunes y soluciones para el adaptador de Oracle EBS en el módulo de adaptador de BizTalk (BAP)"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 667633e0-055a-418a-ab64-d4f6e6c7a898
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4654e228a4ca86c9d89686f826d57777f2353efd
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="troubleshoot-operational-issues-with-the-oracle-e-business-suite-adapter"></a>Solucionar problemas de funcionamiento con el adaptador de Oracle E-Business Suite
Esta sección describe el uso de técnicas de solución de problemas para resolver errores de operaciones que pueden surgir al usar [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)].  
  
## <a name="enabling-tracing"></a>La habilitación del seguimiento  
 Para obtener más información acerca del seguimiento de soporte técnico en el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], [el seguimiento de diagnóstico y registro de mensajes en el adaptador de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/diagnostic-tracing-and-message-logging-in-the-oracle-e-business-suite-adapter.md).  
  
## <a name="known-issues"></a>Problemas conocidos  
 Éstos son los errores más comunes que pueden surgir al usar el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], junto con sus causa probable y la resolución.  
  
  
  
###  <a name="BKMK_LoadBindings"></a>Error al cargar los enlaces del adaptador  
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
  
-   Asegúrese de que las versiones de cliente LOB necesarias se instalan en el equipo donde instaló el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener información acerca de las versiones de cliente compatibles, consulte la Guía de instalación disponible en \<unidad de instalación\>: \Program [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].  
  
-   Asegúrese de que se realiza una instalación personalizada de los adaptadores para instalar a sólo el adaptador que necesita.  
  
###  <a name="BKMK_Display"></a>El adaptador de Oracle E-Business Suite no se muestra en la lista de adaptadores en la consola de administración de BizTalk Server  
 **Problema**  
  
 A diferencia de la versión anterior de los adaptadores incluidos con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] acompaña [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] no aparecen en la lista de adaptadores en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
 **Causa**  
  
 La versión más reciente [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] es un enlace personalizado de WCF. Por lo tanto, aunque la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] muestra de la consola de administración de la [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], no muestra los enlaces personalizados de WCF y por lo tanto, no se mostrarán basadas en WCF [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  
  
 **Resolución**  
  
 Puede agregar explícitamente la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, siga los pasos mencionados en [agregar el adaptador de Oracle E-Business Suite a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md).  
  
###  <a name="BKMK_MissingAction"></a>Error al realizar operaciones en Oracle E-Business Suite  
 **Problema**  
  
 El adaptador produce el siguiente error al realizar cualquier operación en el uso de Oracle E-Business Suite [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  
  
-   **Para que BizTalk Server**  
  
    ```  
    System.ArgumentNullException: Value cannot be null.  
    ```  
  
 **Causa**  
  
 No se especifica la acción de WCF para el mensaje. WCF requiere una acción de SOAP que se especifique para cada operación, que informa al adaptador acerca de la operación se realizará en la aplicación de LOB.  
  
 **Resolución**  
  
 Especifica la acción de SOAP en el puerto de envío o como una propiedad de contexto de mensaje en una orquestación de BizTalk. Para obtener instrucciones, consulte [configurar la acción SOAP para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-soap-action-for-oracle-e-business-suite.md). Vea [mensajes y esquemas de mensaje para el adaptador de Oracle EBS](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md) para ver una lista de acciones para cada operación.  
  
###  <a name="BKMK_WrongClient"></a>Proceso de BizTalk puede bloquearse debido a una versión incorrecta de cliente de Oracle cuando se quita un mensaje de solicitud en la ubicación de recepción  
 **Problema**  
  
 Después de quita un mensaje de solicitud en una ubicación de recepción definida en una orquestación de BizTalk, la orquestación consume el mensaje y el host de BizTalk (BTSNTSvc.exe) se bloquea y se reinicia.  
  
 **Causa**  
  
 Instalar al cliente de Oracle, agrega la referencia a los ensamblados de cliente más recientes en la variable de ruta de acceso. Además, las referencias a la instalación más reciente del ensamblado de cliente de Oracle preceder a la referencia a los ensamblados de cliente existente. Por lo tanto, si la instalación más reciente del cliente de Oracle no tiene una versión de cliente compatibles, el host de BizTalk se bloquea y, a continuación, se reinicia.  
  
 Por ejemplo, suponga que el cliente de Oracle admitido 11.1.0.7 ya está instalado en el equipo y la variable de ruta de acceso tiene la siguiente referencia:  
  
```  
C:\oracle\product\11.1.0\client_1\bin;  
```  
  
 Si un cliente de Oracle no admitido, por ejemplo 10.2.0.3, está instalado en el mismo equipo, la variable de ruta de acceso tendrá la siguiente referencia:  
  
```  
C:\oracle\product\10.2.0\db_2\bin;C:\oracle\product\11.1.0\client_1\bin;  
```  
  
 Tenga en cuenta que se hace referencia a la versión de cliente no compatibles antes de la versión admitida y, por tanto, se bloquea el host de BizTalk. Si hay más de un hosts de BizTalk que se ejecutan, se bloquea aloja el adaptador.  
  
 **Resolución**  
  
 Si más de un cliente de Oracle está instalado en el mismo equipo, asegúrese de que se hace referencia a la versión de cliente de Oracle compatible antes de las otras versiones de cliente de Oracle en la variable de ruta de acceso. Por ejemplo, si la versión de cliente de Oracle admitida es 11.1.0.7, la referencia en la variable de ruta de acceso debe ser similar:  
  
```  
  
C:\oracle\product\11.1.0\client_1\bin;C:\oracle\product\10.2.0\db_2\bin;  
```  
  
###  <a name="BKMK_Overflow"></a>Adaptador podría producir una excepción de desbordamiento en la ejecución de una operación  
 **Problema**  
  
 Mediante el adaptador, si se intenta realizar una operación que contiene los tipos de datos numéricos de Oracle dentro de los conjuntos de datos o débilmente tipada cursores REF CURSOR, el adaptador podría producir una excepción de desbordamiento.  
  
 **Causa**  
  
 Esto sucede si se proporciona un valor grande para el tipo de datos numéricos de Oracle dentro de los conjuntos de datos o débilmente tipada cursores REF cursor que no caben en el tipo de .NET correspondiente.  
  
 **Resolución**  
  
 Si desea pasar valores grandes para el tipo de datos numéricos de Oracle dentro de los conjuntos de datos o débilmente tipada cursores REF CURSOR, debe habilitar escribiendo segura estableciendo el valor de la **EnableSafeTyping** enlace propiedad **true**. Habilitar escribiendo seguro, expone al tipo de datos numéricos de Oracle en conjuntos de datos o débilmente tipada cursores REF cursor como cadenas.  
  
###  <a name="BKMK_Arithmetic"></a>Adaptador podría producir una excepción de desbordamiento aritmético al ejecutar una operación ExecuteScalar  
 **Problema**  
  
 Mediante el adaptador, si intenta ejecutar una instrucción SELECT en una operación de ExecuteScalar que recupera un número grande, el adaptador devuelve la siguiente excepción: "System.OverflowException: operación aritmética ha provocado un desbordamiento."  
  
 **Causa**  
  
 Esto sucede debido a la limitación conocida de operación ExecuteScalar en ODP.NET. ODP.NET intenta ajustar en los datos en el tipo de datos Decimal. NET, y si el resultado es demasiado grande para caber en el tipo Decimal. NET, se produce la excepción.  
  
 **Resolución**  
  
 Utilice TO_CHAR() en la instrucción SELECT en la operación ExecuteScalar para convertir los datos devueltos como cadena.  
  
###  <a name="BKMK_AppContext"></a>Cliente de adaptador podría producir la excepción siguiente sobre cómo ejecutar una operación: "no se pudo recuperar el identificador de usuario, Id. de responsabilidad, identificador de la aplicación.  Compruebe si se han pasado valores correctos en."  
 **Problema**  
  
 Los clientes de adaptador podrían producir esta excepción si va a realizar operaciones en artefactos de Oracle E-Business Suite (tablas de interfaz, vistas de interfaz, programas simultáneos y conjuntos de solicitudes).  
  
 **Causa**  
  
 Esto sucede si se proporciona una combinación incorrecta de nombre de usuario, contraseña y nombre de responsabilidad de Oracle mientras se realizan operaciones en tablas de interfaz, vistas de interfaz, programas simultáneos y conjuntos de solicitudes. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] requiere estos valores para establecer el contexto de la aplicación de estos artefactos. Para obtener más información sobre el contexto de la aplicación de configuración, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  
  
 **Resolución**  
  
 Debe especificar una combinación correcta del nombre de usuario de Oracle, la contraseña y la responsabilidad a establecer correctamente el contexto de la aplicación de un artefacto de Oracle E-Business Suite. Para especificar los valores de nombre de usuario de Oracle y la contraseña, debe utilizar el **OracleUserName** y **OraclePassword** propiedades de enlace. Para especificar el valor de la responsabilidad de Oracle, puede utilizar el **OracleEBSResponsibilityName** propiedad o un mensaje de propiedad de contexto de enlace.  
  
###  <a name="BKMK_RootNode"></a>Error con RootNode TypeName en proyectos de BizTalk  
 **Problema**  
  
 En un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], si los esquemas generan a partir del [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] contiene caracteres no válidos o palabras reservadas para el **RootNode TypeName** propiedad, se producirá el siguiente error al compilar el proyecto :  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 **Resolución**  
  
1.  Haga clic en el nodo rood hace referencia en el error y seleccione **propiedades**.  
  
2.  Para el **RootNode TypeName** propiedad, quite los caracteres no válidos o reservados palabras, por ejemplo, punto (.).  
  
###  <a name="BKMK_InvalidBinding"></a>Advertencia de enlace no válido al utilizar el adaptador en Visual Studio  
 **Problema**  
  
 Cuando usa el adaptador para crear una aplicación en [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)] y abra el archivo de configuración (app.config) generado por el adaptador, verá una advertencia similar al siguiente:  
  
```  
The element 'bindings' has invalid child element 'oracleEBSBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 **Causa**  
  
 Esta advertencia aparece porque la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] enlace, `oracleEBSBinding`, se incluye no es un enlace estándar con el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)].  
  
 **Resolución**  
  
 Puede omitir esta advertencia de forma segura.  
  
###  <a name="BKMK_Notify"></a>BizTalk Server produce una excepción si se utiliza más de un esquema de notificación en la misma aplicación o el esquema de notificación en varias aplicaciones en el mismo host  
 **Problema**  
  
 BizTalk Server produce una excepción de XLANG o una excepción que indica que la aplicación no encuentra la especificación de documento porque varios esquemas coincida con el tipo de mensaje.  
  
 **Causa**  
  
 Esto se debe a alguno de los siguientes:  
  
-   Ha generado más de un esquema de notificación en un proyecto de BizTalk Server, implementado en una aplicación de BizTalk Server y, a continuación, se ejecutó la aplicación para recibir notificaciones de la base de datos de Oracle. Dado que los esquemas de notificación son comunes, hay un conflicto entre los esquemas que se implementan en la aplicación de BizTalk Server.  
  
-   En el caso de varios proyectos, ha generado un esquema de notificación para cada uno de los proyectos que se implementan cada proyecto a una aplicación de BizTalk Server independiente en el mismo host de BizTalk Server y, a continuación, se ejecutaba una aplicación o aplicaciones reciban notificaciones de la base de datos de Oracle. Dado que los esquemas y los ensamblados son accesibles a través de las aplicaciones de BizTalk Server, hay un conflicto entre los esquemas comunes implementados en aplicaciones de BizTalk Server y los ensamblados.  
  
 **Resolución**  
  
 Usar un único archivo de esquema de notificación para una aplicación de BizTalk Server. Si tiene que usar el esquema de notificación de varias aplicaciones de BizTalk Server en el mismo host, crear una aplicación que contenga un único esquema de notificación y, a continuación, utilice el esquema de notificación de todas las demás aplicaciones de BizTalk Server.  
  
###  <a name="BKMK_Timeout"></a>Excepción de tiempo de espera durante la exploración de Oracle E-Business Suite artefactos en Visual Studio  
 **Problema**  
  
 Al examinar artefactos de Oracle E-Business Suite en un [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] proyecto usando la [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] podría encontrar una excepción de tiempo de espera.  
  
 **Causa**  
  
 Esto puede ocurrir si el servidor que hospeda la Oracle E-Business Suite es lento, servidor está ubicado en una ubicación remota o el esquema que se encuentre bajo tiene un gran número de artefactos.  
  
 **Resolución**  
  
 Puede elegir aumentar el valor de la **SendTimeout** propiedad de enlace o proporcionar una expresión de búsqueda en el **búsqueda en la categoría** cuadro de texto para reducir el número de artefactos que el adaptador recupera.  
  
 Para obtener más información acerca de cómo especificar las propiedades de enlace, vea [configurar las propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md). Para obtener más información acerca de cómo buscar artefactos en Oracle E-Business Suite, consulte [exploración, búsqueda y metadatos de get para las operaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md).  
  
###  <a name="BKMK_MemUsage"></a>Uso de memoria y subproceso recuento aumenta cuando se usa el adaptador en una operación de entrada de transacción  
 **Problema**  
  
 En una operación de entrada transacción, como el sondeo, **si no hay ningún dato disponible en la tabla se sondean,** y el adaptador while sigue sondeando, durante un período de tiempo experimente un aumento en el uso de memoria y el número de subprocesos.  
  
 **Causa**  
  
 **Si no hay ningún dato disponible en la tabla se sondean**, después cada ciclo de tiempo de espera de recepción [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] genera un nuevo subproceso para continuar con la operación de sondeo. Por lo tanto, el uso de memoria y el número de subprocesos aumenta durante un período de tiempo. Sin embargo, si la tabla se sondean, tiene algunos datos, sigue el mismo subproceso realizar todos los sondeos subsiguientes.  
  
 **Resolución**  
  
 Se recomienda establecer el **ReceiveTimeout** para el valor máximo posible, que es 24.20:31:23.6470000 (24 días) para que se genera un subproceso nuevo solo cada 24 días. Esto garantizará que el recuento de subprocesos y de uso de memoria no aumente demasiado demasiado pronto.  
  
 Para obtener más información sobre la **ReceiveTimeout** enlace de propiedad, vea [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md). Para obtener instrucciones sobre cómo especificar propiedades de enlace, consulte [configurar las propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md).  
  
> [!NOTE]
>  Al usar el adaptador con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], establecer el tiempo de espera en un valor grande no afecta a la funcionalidad del adaptador.  
  
## <a name="see-also"></a>Vea también  
[Solucionar problemas del adaptador de Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)