---
title: BizTalk Adapter Pack preguntas más frecuentes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0cdaf09a-50fe-4f30-bd9d-60e316351846
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c9d6e28a5839bafb135285b90d8174a3fa18f49
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22227092"
---
# <a name="frequently-asked-questions"></a>Preguntas más frecuentes
Preguntas más frecuentes (P+f) sobre la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].  
 

## <a name="general-questions"></a>Preguntas generales

### <a name="what-are-the-supported-biztalk-versions-for-the-biztalk-adapter-pack"></a>¿Cuáles son las versiones compatibles de BizTalk para BizTalk Adapter Pack?  
 El [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] se incluye con Microsoft [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]. Instalar la versión incluida con su [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] versión. Instalar el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] desde otro [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] versión no es compatible. 
  
### <a name="in-which-user-context-should-the-setup-be-run"></a>¿En qué contexto de usuario se debe ejecutar el programa de instalación?  
Ejecute el [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] el programa de instalación con una cuenta que sea miembro del grupo Administradores local y [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] grupo de administradores. 

Vínculo relacionado: [derechos mínimos de seguridad](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)

### <a name="how-do-i-get-started-using-the-adapter"></a>¿Cómo comenzar a usar el adaptador?  
Si está familiarizado con [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] y la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], a continuación, instale [BAP 2016](../adapters-and-accelerators/install-the-biztalk-adapter-pack-2016.md) o [BAP 2013 R2 y 2013](../adapters-and-accelerators/install-biztalk-adapter-pack-2013-r2-and-2013.md)y, a continuación, empezar a trabajar con el el [diferentes adaptadores](../adapters-and-accelerators/biztalk-adapter-pack.md).

Si está totalmente familiarizado [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] o [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], vistazo get fue iniciado temas y paso a través de los tutoriales: 

[Empezar a trabajar con el adaptador de BizTalk para base de datos de Oracle](../adapters-and-accelerators/adapter-oracle-database/get-started-with-the-oracle-database-adapter.md)  
[Empezar a trabajar con el adaptador de BizTalk para Oracle E-Business Suite](../adapters-and-accelerators/adapter-oracle-ebs/get-started-with-the-biztalk-adapter-for-oracle-e-business-suite.md)  
[Empezar a trabajar con el adaptador de BizTalk para mySAP Business Suite](../adapters-and-accelerators/adapter-sap/get-started-with-the-biztalk-adapter-for-mysap-business-suite.md)  
[Empezar a trabajar con el adaptador de BizTalk para Siebel eBusiness Applications](../adapters-and-accelerators/adapter-siebel/get-started-with-the-biztalk-adapter-for-siebel-ebusiness-applications.md)  
[Empezar a trabajar con el adaptador de BizTalk para SQL](../adapters-and-accelerators/adapter-sql/get-started-with-the-biztalk-adapter-for-sql.md)
   
### <a name="does-the-microsoft-biztalk-adapter-pack-support-tracing"></a>¿Admite Microsoft BizTalk Adapter Pack seguimiento?  
El [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] permite a los clientes de adaptador habilitar el seguimiento de Windows Communication Foundation (WCF) y seguimiento específicas del adaptador. Cuando se habilita el seguimiento, también elegir el nombre de ruta de acceso y la carpeta. Por lo tanto, los seguimientos se almacenan donde prefiera. Para ver los seguimientos, use la herramienta WCF Service Trace Viewer. Vea [utilizando Service Trace Viewer para ver seguimientos asociados y solución de problemas](https://msdn.microsoft.com/library/aa751795.aspx).

Para obtener más información acerca del seguimiento y otras ideas para solucionar problemas, consulte: 

[Solucionar problemas del adaptador de base de datos de Oracle](../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)  
[Solucionar problemas del adaptador de Oracle EBS](../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)  
[Solucionar problemas del adaptador SAP](../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)  
[Solucionar problemas del adaptador de Siebel](../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)  
[Solucionar problemas del adaptador SQL](../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)  
  
### <a name="are-performance-counters-available-for-the-adapters"></a>¿Hay contadores de rendimiento disponibles para los adaptadores?  
Sí. El [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] proporciona un **tiempo LOB (acumulado)** contador de rendimiento para medir el tiempo, en milisegundos, que la biblioteca de cliente LOB que se tarda en completar una acción iniciada por el adaptador.  Puede habilitar los contadores de rendimiento estableciendo la `EnablePerformanceCounters` enlazar la propiedad a **True**. Para deshabilitar los contadores de rendimiento, establezca `EnablePerformanceCounters` a **False** (el valor predeterminado).   

## <a name="biztalk-server-questions"></a>Preguntas de BizTalk Server

### <a name="which-biztalk-server-tools-are-used-while-working-with-adapters-where-can-i-find-more-information-about-these-tools"></a>¿Las herramientas de BizTalk Server se usan al trabajar con adaptadores? ¿Dónde puedo encontrar más información acerca de estas herramientas?  
Hay varias herramientas que pueden ayudar a los artefactos que usan estos adaptadores: 
 
 |Herramienta|Temas de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentación principal|  
|---|---|  
|[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]|-   [Con Visual Studio](../core/using-visual-studio.md) <br />-   [Trabajar con proyectos de BizTalk](../core/working-with-biztalk-projects.md)<br />-   [Implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)<br /><br /> Obtener información acerca de soluciones de Visual Studio, proyectos y elementos en [soluciones y proyectos en Visual Studio](https://msdn.microsoft.com/library/b142f8e7.aspx).|  
|Diseñador de orquestaciones|[Crear orquestaciones mediante el Diseñador de orquestaciones](../core/creating-orchestrations-using-orchestration-designer.md)|  
|Diseñador de canalizaciones| [Crear canalizaciones mediante el Diseñador de canalizaciones](../core/creating-pipelines-using-pipeline-designer.md)|  
|Asignador de BizTalk| [Creación de mapas mediante el asignador de BizTalk](../core/creating-maps-using-biztalk-mapper.md)|  
|Consola de administración de BizTalk Server|[Utilizar la consola de administración de BizTalk Server](../core/using-the-biztalk-server-administration-console.md)|  
  
### <a name="can-i-reuse-bindings-of-a-biztalk-application-how"></a>¿Puedo volver a usar enlaces de una aplicación de BizTalk? ¿Cómo?  
Sí. Un enlace crea una asignación entre un extremo lógico, por ejemplo, un puerto de orquestación o un vínculo de función y un extremo físico, como un envío y puerto de recepción. Permite la comunicación entre componentes diferentes de una solución empresarial de BizTalk. La información de enlace se almacena en un archivo XML que contiene información de enlace para cada orquestación de BizTalk en el ámbito de un ensamblado de BizTalk, la aplicación o el grupo. Puede exportar los enlaces de ensamblado de BizTalk, aplicación o grupo y, a continuación, volver a usarla importando a cualquier otro grupo o aplicación de BizTalk. Para obtener más información, vea 

[Reutilizar los enlaces del adaptador de base de datos de Oracle](../adapters-and-accelerators/adapter-oracle-database/reuse-oracle-database-adapter-bindings.md)  
[Reutilizar los enlaces del adaptador de Oracle EBS](../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)  
[Reutilizar los enlaces del adaptador SAP](../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)  
[Reutilizar los enlaces del adaptador de Siebel](../adapters-and-accelerators/adapter-siebel/reuse-adapter-bindings-in-the-siebel-adapter.md)  
[Reutilizar los enlaces del adaptador de SQL](../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)
  
### <a name="what-is-the-transaction-isolation-level-how-can-i-configure-it"></a>¿Qué es el "nivel de aislamiento de transacción"? ¿Cómo se puede configurar?  
 El nivel de aislamiento de transacción determina el grado al que una transacción se aísla de los cambios de datos realizados por otras transacciones. Define el comportamiento de bloqueo de los comandos de Transact-SQL emitidos por una conexión con el sistema de línea de negocio (LOB). 
  
Esto es configurable para algunos de los adaptadores. Vea: 

[Base de datos de Oracle: Configurar la nivel de aislamiento de transacción y el tiempo de espera de transacción](../adapters-and-accelerators/adapter-oracle-database/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-db.md)  
[Oracle E-Business Suite: Configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción](../adapters-and-accelerators/adapter-oracle-ebs/configure-transaction-isolation-level-and-transaction-timeout-with-oracle-ebs.md)  
[SQL: Configurar el nivel de aislamiento de transacción y el tiempo de espera de transacción](../adapters-and-accelerators/adapter-sql/configure-transaction-isolation-level-and-transaction-timeout-with-sql.md)

[Niveles de aislamiento en el motor de base de datos de SQL](https://technet.microsoft.com/library/ms189122.aspx) describe los diferentes niveles en SQL. 

## <a name="wcf-based-adapter-faqs"></a>Preguntas más frecuentes de adaptador basado en WCF

### <a name="what-is-wcf"></a>¿Qué es WCF?
 WCF es el acrónimo Windows Communication Foundation. WCF es un marco de programación desarrollado por Microsoft para compilar aplicaciones orientadas a servicios. WCF forma parte de .NET framework y permite a los desarrolladores compilar soluciones seguras, confiables y de transacciones que se integran en diferentes plataformas e interoperen con las inversiones existentes.  
  
Vínculo relacionado: [¿qué es Windows Communication Foundation](https://msdn.microsoft.com/library/ms731082.aspx)  
  
### <a name="what-is-wcf-lob-adapter-sdk"></a>¿Qué es el SDK de adaptador LOB de WCF?  
 El SDK de adaptador LOB de WCF es una colección de herramientas y componentes que proporcionan un marco coherente para desarrollar adaptadores reutilizables, con datos completos de metadatos para los sistemas de línea de negocio. Adaptadores escritos mediante el SDK de adaptador LOB de WCF se exponen como enlaces de WCF personalizados y pueden ser utilizados por un cliente compatible con WCF. 
 
Vínculo relacionado: [documentación de línea de negocio SDK de adaptador WCF](../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md) 

### <a name="what-is-the-wcf-service-model"></a>¿Qué es el modelo de servicio WCF?  
 El modelo de servicio WCF es un modelo de programación proporcionado por WCF en el que el sistema LOB (por ejemplo, Oracle o SAP) se expone como un servicio WCF. El contrato de servicio que existe entre un cliente y un servicio se representa como una interfaz de .NET y las operaciones se representan como métodos en esta interfaz. El modelo de servicio WCF genera una clase de proxy, la clase de cliente WCF: a través del cual el código puede invocar operaciones y datos con el adaptador de recepción. 
 
 Todos los adaptadores de la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] admite el modelo de servicio WCF.
 
 ### <a name="what-is-the-wcf-channel-model"></a>¿Qué es el modelo de canal WCF?  
 El modelo de canal WCF es una abstracción del intercambio de mensajes SOAP entre clientes y servicios de bajo nivel. Proporciona interfaces y tipos que permiten enviar y recibir mensajes mediante el uso de una pila de protocolo por capas que se llama a una pila de canales. Cada nivel de la pila se compone de un canal y se crea cada canal de un enlace de WCF. Cada adaptador es un enlace de transporte personalizado de WCF que expone el sistema LOB como un servicio WCF. 
 
  Todos los adaptadores de la [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] admite el modelo de canal WCF.
  
### <a name="when-should-i-use-the-wcf-service-model-or-the-wcf-channel-model"></a>¿Cuándo se puede usar el modelo de servicio WCF o el modelo de canal WCF?  
 El modelo de servicio WCF presenta un modelo que resultará familiar a los programadores de .NET y oculta las complejidades subyacentes de intercambio de mensajes SOAP a través de un canal. Además, el complemento de agregar referencia de servicio de adaptador se integra con la experiencia de diseño de Visual Studio y presenta una interfaz estándar de Microsoft Windows que proporciona una exploración y capacidades en las operaciones expuestas por el adaptador de búsqueda eficaces. Por lo tanto, el modelo de servicio WCF suele ser la mejor opción para desarrollar soluciones de programación para cualquier adaptador basado en WCF.  

 Desea utilizar el modelo de canal WCF a través del servicio WCF de modelo cuando:  
  
-   El modelo de canal WCF proporciona un control más minucioso sobre las operaciones que realiza en el sistema LOB en el modelo de canal WCF, puede controlar directamente el contenido de los mensajes que envía a través del canal.  
  
-   El modelo de canal WCF ofrece compatibilidad con más completa-to-end de transmisión por secuencias de tipos de datos de objetos grandes (LOB) que el modelo de servicio WCF. Esto es porque en el modelo de canal WCF, puede controlar directamente cómo proporcionar el cuerpo del mensaje en los mensajes salientes y la forma de procesar el cuerpo del mensaje en los mensajes entrantes. 
  
### <a name="how-do-i-get-started-with-the-wcf-service-model"></a>¿Cómo empezar con el modelo de servicio WCF?  
 Puede utilizar cualquiera de las siguientes herramientas proporcionados por el modelo de servicio WCF para generar una clase de cliente WCF o un contrato de servicio WCF y auxiliares asociados código desde los metadatos del servicio expuesto por cada adaptador:  
  
-   El ServiceModel Metadata Utility Tool (svcutil.exe), que se suministra con WCF.  
  
-   El agregar adaptador de servicio de referencia de complemento de Visual Studio, que se suministra con la [!INCLUDE[adapterpacknoversion_md](../includes/adapterpacknoversion-md.md)].  
  
### <a name="how-do-i-get-started-with-the-wcf-channel-model"></a>¿Cómo empezar con el modelo de canal WCF?  
 Mediante el modelo de canal WCF, puede invocar operaciones y recibir los resultados de una consulta de sondeo mediante el intercambio de mensajes SOAP con el adaptador a través de un canal WCF. Para empezar, debe crear canales de entrada (servicio) y saliente (cliente).
  
## <a name="see-also"></a>Vea también  
[BizTalk Adapter Pack](../adapters-and-accelerators/biztalk-adapter-pack.md)