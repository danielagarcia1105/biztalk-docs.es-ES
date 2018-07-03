---
title: Solucionar problemas de funcionamiento con el adaptador de Oracle E-Business Suite | Microsoft Docs
description: Problemas comunes y soluciones para el adaptador de Oracle EBS en el módulo de adaptador de BizTalk (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 667633e0-055a-418a-ab64-d4f6e6c7a898
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d119afaea2382e1ede6c780a40bbe2bf4329860f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989997"
---
# <a name="troubleshoot-operational-issues-with-the-oracle-e-business-suite-adapter"></a>Solucionar problemas de funcionamiento con el adaptador de Oracle E-Business Suite
En esta sección se analiza el uso de técnicas de solución de problemas para resolver errores operativos que pueden surgir al usar [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)].  
  
## <a name="enabling-tracing"></a>La habilitación del seguimiento  
 Para obtener más información acerca del seguimiento de soporte técnico en el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], [el seguimiento de diagnóstico y registro de mensajes en el adaptador de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/diagnostic-tracing-and-message-logging-in-the-oracle-e-business-suite-adapter.md).  
  
## <a name="known-issues"></a>Problemas conocidos  
 Los siguientes son los errores más comunes que pueden surgir al usar el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], junto con su causa y resolución.  
  
  
  
###  <a name="BKMK_LoadBindings"></a> Error al cargar los enlaces del adaptador  
 **Problema**  
  
 Al intentar iniciar el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] o [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], obtendrá el error siguiente:  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 **Causa**  
  
 Al intentar iniciar el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], WCF carga los enlaces del adaptador para todos los adaptadores instalados. A su vez, los enlaces del adaptador dependen del software cliente específica de la aplicación de empresa. Que puede enfrentarse a este problema para uno o ambos de los siguientes motivos:  
  
- El software de cliente LOB necesario no está instalado en el equipo donde instaló el adaptador.  
  
- Realizó una instalación típica o completo del adaptador, que se instala en todos los adaptadores incluidos en el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Sin embargo, podrían instalarse las bibliotecas de cliente de línea de negocio para sólo una aplicación empresarial. Como resultado, la interfaz gráfica de usuario no se puede cargar los enlaces para los demás adaptadores.  
  
  **Resolución**  
  
- Asegúrese de que las versiones de cliente de línea de negocio necesarias están instaladas en el equipo donde instaló el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]. Para obtener información acerca de las versiones de cliente compatibles, consulte la Guía de instalación disponible en \<unidad de instalación\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].  
  
- Asegúrese de que realizar una instalación personalizada de los adaptadores que se va a instalar a sólo el adaptador que necesita.  
  
###  <a name="BKMK_Display"></a> El adaptador de Oracle E-Business Suite no se muestra en la lista de adaptadores en la consola de administración de BizTalk Server  
 **Problema**  
  
 A diferencia de la versión anterior de los adaptadores incluidos con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] acompaña [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] no se muestra en la lista de adaptadores en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
 **Causa**  
  
 La versión más reciente [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] es un enlace personalizado de WCF. Por lo tanto, aunque el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] muestra la consola de administración de la [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], no muestra los enlaces personalizados de WCF y por lo tanto, no muestra basada en WCF [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  
  
 **Resolución**  
  
 Puede agregar explícitamente la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, siga los pasos mencionados en [agregar el adaptador de Oracle E-Business Suite a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md).  
  
###  <a name="BKMK_MissingAction"></a> Error al realizar operaciones en Oracle E-Business Suite  
 **Problema**  
  
 El adaptador produce el siguiente error al realizar cualquier operación en el uso de Oracle E-Business Suite [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  
  
- **Para que BizTalk Server**  
  
  ```  
  System.ArgumentNullException: Value cannot be null.  
  ```  
  
  **Causa**  
  
  No se especifica la acción de WCF para el mensaje. WCF requiere una acción de SOAP que se especifique para cada operación, que informa al adaptador de la operación que se realizará en la aplicación de LOB.  
  
  **Resolución**  
  
  Especifica la acción de SOAP en el puerto de envío o como una propiedad de contexto de mensaje en una orquestación de BizTalk. Para obtener instrucciones, consulte [configurar la acción SOAP para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-soap-action-for-oracle-e-business-suite.md). Consulte [mensajes y esquemas de mensaje para el adaptador de Oracle EBS](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md) para ver una lista de acciones para cada operación.  
  
###  <a name="BKMK_WrongClient"></a> Proceso de BizTalk puede bloquearse debido a una versión incorrecta de cliente de Oracle cuando se quita un mensaje de solicitud en la ubicación de recepción  
 **Problema**  
  
 Después de quita un mensaje de solicitud en una ubicación de recepción definida en una orquestación de BizTalk, la orquestación consume el mensaje y el host de BizTalk (BTSNTSvc.exe) se bloquea y se reinicia.  
  
 **Causa**  
  
 Instalación del cliente de Oracle, agrega la referencia a los ensamblados de cliente más recientes en la variable PATH. Además, las referencias a la instalación más reciente del ensamblado de cliente de Oracle preceder a la referencia a los ensamblados de cliente existentes. Por lo tanto, si la instalación de cliente más reciente de Oracle no tiene una versión compatible del cliente, el host de BizTalk se bloquea y, a continuación, se reinicia.  
  
 Por ejemplo, suponga que el cliente de Oracle compatible 11.1.0.7 ya está instalado en el equipo y la variable de ruta de acceso tiene la siguiente referencia:  
  
```  
C:\oracle\product\11.1.0\client_1\bin;  
```  
  
 Si se instala un cliente de Oracle no admitido, por ejemplo 10.2.0.3, en el mismo equipo, la variable de ruta de acceso tendrá la siguiente referencia:  
  
```  
C:\oracle\product\10.2.0\db_2\bin;C:\oracle\product\11.1.0\client_1\bin;  
```  
  
 Tenga en cuenta que se hace referencia a la versión de cliente no compatibles antes de la versión admitida y, por tanto, se bloquea el host de BizTalk. Si hay varios hosts de BizTalk ejecuta, aloja el adaptador se bloquea.  
  
 **Resolución**  
  
 Si más de un cliente de Oracle está instalado en el mismo equipo, asegúrese de que se hace referencia a la versión de cliente de Oracle compatible antes de las otras versiones de cliente de Oracle en la variable PATH. Por ejemplo, si la versión de cliente de Oracle compatible es 11.1.0.7, la referencia en la variable de ruta de acceso debe ser similar:  
  
```  
  
C:\oracle\product\11.1.0\client_1\bin;C:\oracle\product\10.2.0\db_2\bin;  
```  
  
###  <a name="BKMK_Overflow"></a> Adaptador podría producir una excepción de desbordamiento en ejecutando una operación  
 **Problema**  
  
 Usa el adaptador, si se intenta realizar una operación que contiene los tipos de datos numéricos de Oracle dentro de los conjuntos de datos o débilmente tipada parámetros REF CURSOR, el adaptador podría generar una excepción de desbordamiento.  
  
 **Causa**  
  
 Esto sucede si proporciona un valor grande para el tipo de datos numéricos de Oracle dentro de los conjuntos de datos o débilmente tipada cursores REF cursor que no quepan en el tipo de .NET correspondiente.  
  
 **Resolución**  
  
 Si desea pasar valores grandes para el tipo de datos numéricos de Oracle dentro de los conjuntos de datos o débilmente tipada parámetros REF CURSOR, debe habilitar seguro escribiendo estableciendo el valor de la **EnableSafeTyping** enlazar la propiedad a **true**. Habilitar seguro escribiendo expone el tipo de datos numéricos de Oracle dentro de los conjuntos de datos o cursores REF cursor de débilmente tipada como cadenas.  
  
###  <a name="BKMK_Arithmetic"></a> Adaptador podría producir una excepción de desbordamiento aritmético al ejecutar una operación ExecuteScalar  
 **Problema**  
  
 Usa el adaptador, si intenta ejecutar una instrucción SELECT en una operación de ExecuteScalar que recupera un número grande, el adaptador inicia la siguiente excepción: "System.OverflowException: operación aritmética ha provocado un desbordamiento."  
  
 **Causa**  
  
 Esto sucede debido a la limitación conocida de operación ExecuteScalar en ODP.NET. ODP.NET intenta ajustar en los datos en el tipo de datos Decimal. NET, y si el resultado es demasiado grande para caber en el tipo Decimal. NET, se produce la excepción.  
  
 **Resolución**  
  
 Usar TO_CHAR() en la instrucción SELECT en la operación ExecuteScalar para convertir los datos devueltos como cadena.  
  
###  <a name="BKMK_AppContext"></a> Cliente de adaptador podría producir una excepción al ejecutar una operación: "no se pudo recuperar el identificador de usuario, Id. de responsabilidad, Id. de aplicación.  Compruebe si se pasaron valores correctos."  
 **Problema**  
  
 Los clientes del adaptador podrían producir esta excepción si está realizando operaciones en los artefactos de Oracle E-Business Suite (tablas, vistas de interfaz, programas simultáneos y conjuntos de solicitudes).  
  
 **Causa**  
  
 Esto sucede si se proporciona una combinación incorrecta de nombre de usuario, contraseña y nombre de la responsabilidad de Oracle al realizar operaciones en tablas, vistas de interfaz, programas simultáneos y conjuntos de solicitudes. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] requiere estos valores con el fin de establecer el contexto de la aplicación de estos artefactos. Para obtener más información sobre el contexto de la aplicación de configuración, consulte [establecer contexto de la aplicación](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).  
  
 **Resolución**  
  
 Debe especificar una combinación correcta del nombre de usuario de Oracle, la contraseña y el responsable de establecer correctamente el contexto de la aplicación de un artefacto de Oracle E-Business Suite. Para especificar valores para nombre de usuario de Oracle y la contraseña, debe usar el **OracleUserName** y **OraclePassword** propiedades de enlace. Para especificar el valor de la responsabilidad de Oracle, puede usar el **OracleEBSResponsibilityName** enlaza la propiedad de contexto de propiedad o un mensaje.  
  
###  <a name="BKMK_RootNode"></a> Error con RootNode TypeName en proyectos de BizTalk  
 **Problema**  
  
 En un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], si los esquemas generan a partir del [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] contiene caracteres no válidos o palabras reservadas para el **RootNode TypeName** propiedad, se producirá el siguiente error al compilar el proyecto :  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 **Resolución**  
  
1.  Haga clic en el nodo raíz al que hace referencia en el error y seleccione **propiedades**.  
  
2.  Para el **RootNode TypeName** propiedad, quite los caracteres no válidos o palabras reservadas, por ejemplo, punto (.).  
  
###  <a name="BKMK_InvalidBinding"></a> Advertencia de enlace no válido al usar el adaptador en Visual Studio  
 **Problema**  
  
 Cuando se usa el adaptador para crear una aplicación en [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)] y abra el archivo de configuración (app.config) generado por el adaptador, verá una advertencia similar al siguiente:  
  
```  
The element 'bindings' has invalid child element 'oracleEBSBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 **Causa**  
  
 Esta advertencia aparece porque la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] enlace, `oracleEBSBinding`, no un enlace estándar incluye el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)].  
  
 **Resolución**  
  
 Puede omitir esta advertencia de forma segura.  
  
###  <a name="BKMK_Notify"></a> BizTalk Server produce una excepción si usa más de un esquema de notificación en la misma aplicación o el esquema de notificación en varias aplicaciones en el mismo host  
 **Problema**  
  
 BizTalk Server produce una excepción de XLANG o una excepción que indica que la aplicación no puede encontrar la especificación de documento; varios esquemas coincidieron con el tipo de mensaje.  
  
 **Causa**  
  
 Esto sucede debido a una de las siguientes:  
  
- Ha generado más de un esquema de notificación en un proyecto de BizTalk Server, implementado en una aplicación de BizTalk Server y, a continuación, se ejecutó la aplicación para recibir notificaciones de la base de datos de Oracle. Dado que los esquemas de notificaciones son comunes, hay un conflicto entre los esquemas que se implementan en la aplicación de BizTalk Server.  
  
- En el caso de varios proyectos, han generado un esquema de notificación para cada uno de los proyectos, que se implementan cada proyecto para una aplicación de BizTalk Server independiente en el mismo host de BizTalk Server y, a continuación, ejecutó una aplicación o aplicaciones para recibir notificaciones de la base de datos de Oracle. Dado que los ensamblados y esquemas son accesibles a través de las aplicaciones de BizTalk Server, hay un conflicto entre los esquemas comunes implementados en varias aplicaciones de BizTalk Server y ensamblados.  
  
  **Resolución**  
  
  Utilizar un único archivo de esquema de notificación para una aplicación de BizTalk Server. Si tiene que usar el esquema de notificación en varias aplicaciones de BizTalk Server en el mismo host, cree una aplicación que contenga un único esquema de notificación y, a continuación, utilice el esquema de notificación de todas las demás aplicaciones de BizTalk Server.  
  
###  <a name="BKMK_Timeout"></a> Excepción de tiempo de espera durante la exploración de los artefactos de Oracle E-Business Suite en Visual Studio  
 **Problema**  
  
 Al examinar los artefactos de Oracle E-Business Suite en un [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] proyecto usando el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], o [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] puede producirse una excepción de tiempo de espera.  
  
 **Causa**  
  
 Esto podría suceder si el servidor que hospeda la Oracle E-Business Suite es lento, está ubicado el servidor en una ubicación remota o el esquema que se mira tiene un gran número de artefactos.  
  
 **Resolución**  
  
 Puede elegir aumentar el valor de la **SendTimeout** enlazar la propiedad o proporcionar una expresión de búsqueda en el **búsqueda en la categoría** cuadro de texto para reducir el número de artefactos que el adaptador recupera.  
  
 Para obtener más información acerca de cómo especificar las propiedades de enlace, consulte [configurar las propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md). Para obtener más información acerca de la búsqueda de artefactos en Oracle E-Business Suite, consulte [examinar, buscar y obtener metadatos para operaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md).  
  
###  <a name="BKMK_MemUsage"></a> Uso de memoria y subproceso recuento aumenta cuando se usa el adaptador en una operación de entrada con transacciones  
 **Problema**  
  
 En una operación de entrada con transacciones, como el sondeo, **si no hay ningún dato disponible en la tabla que se sondea** y while sigue sondeando el adaptador, durante un período de tiempo experimente un aumento en el uso de memoria y el número de subprocesos.  
  
 **Causa**  
  
 **Si no hay ningún dato disponible en la tabla que se sondea**, después cada ciclo de tiempo de espera de recepción [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] genera un subproceso nuevo para continuar la operación de sondeo. Por lo tanto, el uso de memoria y recuento de subprocesos aumenta durante un período de tiempo. Sin embargo, si la tabla que se sondea tiene algunos datos, sigue el mismo subproceso realizar todos los sondeos subsiguientes.  
  
 **Resolución**  
  
 Se recomienda establecer el **ReceiveTimeout** en el valor máximo posible, que es 24.20:31:23.6470000 (24 días) para que un nuevo subproceso se genera solo cada 24 días. Esto garantizará que el recuento de subprocesos y de uso de memoria no aumentan demasiado demasiado pronto.  
  
 Para obtener más información sobre la **ReceiveTimeout** enlaza la propiedad, vea [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md). Para obtener instrucciones sobre cómo especificar las propiedades de enlace, consulte [configurar las propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md).  
  
> [!NOTE]
>  Al usar el adaptador con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], establecer el tiempo de espera en un valor grande no afecta a la funcionalidad del adaptador.  
  
## <a name="see-also"></a>Vea también  
[Solucionar problemas del adaptador de Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)