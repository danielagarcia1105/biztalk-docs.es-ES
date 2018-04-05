---
title: El archivo de inventario para la solución de administración de procesos empresariales | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, file inventory
ms.assetid: 3efb7495-9543-4fe0-8f4b-26c19b3b6db9
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4cc187a96e7252fad7edacba10b7a3dcc39c1b33
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="file-inventory-for-the-business-process-management-solution"></a>Inventario de archivos para la solución de administración de procesos empresariales
En esta sección se enumeran los subdirectorios y los archivos de origen para la solución de administración de procesos empresariales. El directorio de instalación predeterminado para los archivos de origen de la solución de administración de procesos empresariales es [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios\BPM. Las descripciones antes de las siguientes tablas reemplazan esta ruta con \<directorio de instalación\>.  
  
 Los archivos \<directorio de instalación\>  
  
|Archivo|Description|  
|----------|-----------------|  
|Microsoft.Samples.BizTalk.SouthridgeVideo.sln|Archivo de solución de Visual Studio.|  
|leame.html|Archivo Léame de la solución.|  
|ReplacePKToken.vbs|VBScript para corregir símbolos (tokens) de clave pública en los archivos de la solución cuando se genera la solución.|  
|ReplacePKToken.wsf|Archivo de secuencia de comandos para el VBScript ReplacePKToken.|  
|SetupBPM.bat|Crea una clave pública, actualiza las referencias a la clave pública y compila la solución. Para obtener información acerca de cómo implementar la solución, vea [implementar la solución de administración de procesos empresariales](../core/deploying-the-business-process-management-solution.md).|  
  
 Los archivos \<directorio de instalación\>\BAM  
  
|Archivo|Description|  
|----------|-----------------|  
|BAMServiceOrder.xls|Hoja de cálculo de Excel para los datos de SAE.|  
|BAMServiceOrder.xml|Esquema que define los tipos de elementos de datos de SAE.|  
  
 Los archivos \<directorio de instalación\>\Bindings  
  
|Archivo|Description|  
|----------|-----------------|  
|CableOrderAppBindings-test.xml|Archivo de enlace para la versión de prueba de la **CableOrderApp** aplicación.|  
|CableOrderAppBindings.xml|Archivo de enlace para el **CableOrderAPP** aplicación.|  
|MessagingAppBindings-test.xml|Archivo de enlace para la versión de prueba de la **MessagingApp** aplicación.|  
|MessagingAppBindings.xml|Archivo de enlace para el **MessagingApp** aplicación.|  
|OrderBrokerAppBindings-test.xml|Archivo de enlace para la versión de prueba de la **OrderBrokerApp** aplicación.|  
|OrderBrokerAppBindings.xml|Archivo de enlace para el **OrderBrokerApp** aplicación.|  
  
 Los archivos \<directorio de instalación\>\CableProvisioningSystemClient  
  
|Archivo|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|Archivo de ensamblado para el lado del cliente de los componentes que simulan el sistema de pedidos.|  
|CableProvisioningSystemClient.csproj|Archivo de proyecto de C#.|  
|CPSClient.cs|Origen para el cliente. Incluye el **OrderHandlerWrapper** código de la clase.|  
|OrderException.cs|Archivo C# para la clase que define la **OrderException**.|  
  
 Los archivos \<directorio de instalación\>\CableProvisioningSystemServer  
  
|Archivo|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|Archivo de ensamblado para el lado del servidor de los componentes que simulan el sistema de pedidos.|  
|CableProvisioningSystemServer.csproj|Archivo de proyecto de C#.|  
|CableProvisioningSystemServer.csproj.user|Archivo de opciones de usuario de proyecto de Visual Studio|  
|CPSServer.cs|Origen para el servidor.|  
  
 Los archivos \<directorio de instalación\>\CSRWebApp  
  
|Archivo|Description|  
|----------|-----------------|  
|CSRMainForm.aspx|Formulario ASP de entrada de atención al cliente.|  
|CSRMainForm.aspx.cs|Formulario de código C# subyacente.|  
|Web.Config|Archivos de configuración para el formulario.|  
  
 Los archivos \<directorio de instalación\>\CSRWebApp\App_WebReferences\SouthridgeVideo_OrderBroker  
  
|Archivo|Description|  
|----------|-----------------|  
|orderbrokerorch_orderport.disco|Archivo .disco de la **OrderBroker** presenta como un servicio web.|  
|orderbrokerorch_orderport.discomap|Archivo generado.|  
|orderbrokerorch_orderport.wsdl|Archivo WSDL para el **OrderBroker** presenta como un servicio web.|  
  
 Los archivos \<directorio de instalación\>\FacilitiesSimulator  
  
|Archivo|Description|  
|----------|-----------------|  
|FacilitiesSimulator.csproj|Archivo de proyecto de C# del simulador de instalaciones.|  
|FacilitiesSimulator.csproj.user|Archivo de opciones de usuario de proyecto de Visual Studio|  
|FacilitiesSimulatorForm.cs|Código C# del simulador de instalaciones.|  
|FacilitiesSimulatorForm.resx|Archivo de recursos.|  
  
 Los archivos \<directorio de instalación\>\HistoryDB  
  
|Archivo|Description|  
|----------|-----------------|  
|CreateDatabase.cmd|Archivo que controla al archivo SQL que crea la base de datos de historial.|  
|SouthridgeVideoHistory.sql|Comandos SQL para crear la base de datos de historial.|  
  
 Los archivos \<directorio de instalación\>\IOperationsSystem  
  
|Archivo|Description|  
|----------|-----------------|  
|IOperationsSystem.cs|Definición de interfaz del sistema de operaciones.|  
|IOperationsSystem.csproj|Archivo de proyecto de C#.|  
|IOperationsSystem.csproj.user|Archivo de opciones de usuario de proyecto de Visual Studio|  
  
 Los archivos \<directorio de instalación\>\IOrderHandler  
  
|Archivo|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|Archivo de información sobre el ensamblado.|  
|IOrderHandler.cs|Definición de interfaz para la **OrderHandler**.|  
|IOrderHandler.csproj|Archivo de proyecto de C#.|  
  
 Los archivos \<directorio de instalación\>\Maps  
  
|Archivo|Description|  
|----------|-----------------|  
|Maps.btproj|Archivo de proyecto de BizTalk.|  
|Order_To_SQLUpdateStatus.btm|Asignación para convertir un pedido en mensaje para actualizar el estado.|  
  
 Los archivos \<directorio de instalación\>\MessagingSchemas  
  
|Archivo|Description|  
|----------|-----------------|  
|ErrorEnvelope.xsd|Esquema que define el sobre del mensaje de error.|  
|MessagingSchemas.btproj|Archivo de proyecto de BizTalk.|  
|OrderEnvelope.xsd|Esquema que define el sobre de un pedido.|  
|OrderStatusEnvelope.xsd|Esquema que define el sobre de un mensaje de estado de pedido.|  
|SQLUpdateStatus.xsd|Esquema que define el sobre de un mensaje de actualización de estado de SQL.|  
  
 Los archivos \<directorio de instalación\>\OperationsClient  
  
|Archivo|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|Archivo de información sobre el ensamblado.|  
|OperationsClient.csproj|Proyecto de C# del cliente de operaciones.|  
|OpsClient.cs|Código C# del cliente de operaciones.|  
|OpsExceptions.cs|Código C# que define la excepción de operaciones.|  
  
 Los archivos \<directorio de instalación\>\OperationsHandler  
  
|Archivo|Description|  
|----------|-----------------|  
|OperationsHandler.csproj|Archivo de proyecto de C# para el controlador de operaciones.|  
|OpsHandler.cs|Código C# para el **OpsHandler**. Utilizado por el **OpsClient** para realizar solicitudes de los sistemas de operaciones.|  
  
 Los archivos \<directorio de instalación\>\OperationsServer  
  
|Archivo|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|Archivo de información sobre el ensamblado.|  
|OperationsServer.csproj|Archivo de proyecto de C# para el servidor de operaciones.|  
|OpsServer.cs|Código C# para el servidor de operaciones que proporciona instancias de la **OpsHandler** objeto.|  
  
 Los archivos \<directorio de instalación\>\OpsAdapter  
  
|Archivo|Description|  
|----------|-----------------|  
|OpsAdapter.sln|Solución de Visual Studio para el adaptador Ops.|  
|Register_Ops_Adapter.vbs|VBScript para registrar el adaptador Ops.|  
|SetupOpsAdapter.bat|Archivo por lotes para configurar el adaptador Ops.|  
  
 Los archivos \<directorio de instalación\>\OpsAdapter\IOpsAIC  
  
|Archivo|Description|  
|----------|-----------------|  
|IOpsAIC.cs|Archivo de código de C# para la interfaz que define el **inicializar** y **Execute** métodos llamados por el adaptador Ops.|  
|IOpsAIC.csproj|Archivo de proyecto de C#.|  
  
 Los archivos \<directorio de instalación\>\OpsAdapter\OpsAdapterMgmt  
  
|Archivo|Description|  
|----------|-----------------|  
|AdapterManagement.cs|Archivo de origen C# del adaptador Ops.|  
|AssemblyInfo.cs|Archivo de información sobre el ensamblado.|  
|OpsAdapterMgmt.csproj|Archivo de origen C# del adaptador Ops.|  
|TransmitHandler.xsd|Archivo de origen C# del adaptador Ops.|  
|TransmitLocation.xsd|Archivo de origen C# del adaptador Ops.|  
  
 Los archivos \<directorio de instalación\>\OpsAdapter\OpsTxAdapter  
  
|Archivo|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|Archivo de información sobre el ensamblado.|  
|OpsAdapterExceptions.cs|Archivo de origen C# del adaptador Ops.|  
|OpsAdapterProperties.cs|Archivo de origen C# del adaptador Ops.|  
|OpsTransmitAdapterBatch.cs|Archivo de origen C# del adaptador Ops.|  
|OpsTransmitter.cs|Archivo de origen C# del adaptador Ops.|  
|OpsTxAdapter.csproj|Archivo de proyecto de C#.|  
  
 Los archivos \<directorio de instalación\>\Orchestrations\CableOrderActions  
  
|Archivo|Description|  
|----------|-----------------|  
|Activate.odx|El **activar** orquestación usada por las fases de procesamiento de pedido.|  
|Analyze.odx|El **analizar** orquestación usada por las fases de procesamiento de pedido.|  
|CableOrderActions.btproj|Archivo de proyecto de BizTalk.|  
|Cancel.odx|El **cancelar** orquestación usada por las fases de procesamiento de pedido.|  
|Change.odx|El **cambio** orquestación usada por las fases de procesamiento de pedido.|  
|Complete.odx|El **completar** orquestación usada por las fases de procesamiento de pedido.|  
|Validate.odx|El **validar** orquestación usada por las fases de procesamiento de pedido.|  
  
 Los archivos \<directorio de instalación\>\Orchestrations\CableOrderStage1  
  
|Archivo|Description|  
|----------|-----------------|  
|CableOrder1.odx|Orquestación para la primera fase de procesamiento de pedido.|  
|CableOrderStage1.btproj|Archivo de proyecto de BizTalk.|  
  
 Los archivos \<directorio de instalación\>\Orchestrations\CableOrderStage2  
  
|Archivo|Description|  
|----------|-----------------|  
|CableOrder2.odx|Orquestación para la segunda fase de procesamiento de pedido.|  
|CableOrderStage2.btproj|Archivo de proyecto de BizTalk.|  
  
 Los archivos \<directorio de instalación\>\Orchestrations\OrderBroker  
  
|Archivo|Description|  
|----------|-----------------|  
|OrderBroker.btproj|Archivo de proyecto de BizTalk.|  
|OrderBroker.odx|El **OrderBroker** orquestación.|  
  
 Los archivos \<directorio de instalación\>\Orchestrations\OrderManager  
  
|Archivo|Description|  
|----------|-----------------|  
|CheckInterrupt.odx|El **CheckInterrupt** orquestación.|  
|ErrorHandler.odx|El **ErrorHandler** orquestación.|  
|ExceptionHandler.odx|El **ExceptionHandler** orquestación.|  
|Interrupter.odx|El **Interrupter** orquestación.|  
|OrderManager.btproj|Archivo de proyecto de BizTalk.|  
|OrderManager.odx|El **OrderManager** orquestación.|  
  
 Los archivos \<directorio de instalación\>\OrderBrokerMaps  
  
|Archivo|Description|  
|----------|-----------------|  
|CSR_OrderRequest_To_Order.btm|Asignación para convertir una solicitud de pedido de atención al cliente en un mensaje de pedido.|  
|CSR_OrderRequest_To_Servicing_OrderRequest.btm|Asignación para convertir una solicitud de pedido de atención al cliente en un mensaje al departamento de atención.|  
|CSR_OrderRequest_To_SQLHistoryInsert.btm|Asignación para convertir una solicitud de pedido de atención al cliente en un mensaje de actualización de historial.|  
|OrderBrokerMaps.btproj|Archivo de proyecto de BizTalk.|  
|Order_To_CSR_OrderRequest.btm|Asignación para convertir un mensaje de pedido en una solicitud de pedido de atención al cliente.|  
  
 Los archivos \<directorio de instalación\>\OrderBrokerSchemas  
  
|Archivo|Description|  
|----------|-----------------|  
|CSR_OrderRequest.xsd|Esquema de la solicitud de atención al cliente.|  
|OrderBrokerSchemas.btproj|Archivo de proyecto de BizTalk.|  
|Servicing_OrderRequest.xsd|Esquema que define el mensaje enviado al sistema de servicio.|  
|SQLHistoryInsert.xsd|Esquema para el mensaje de historial de SQL.|  
  
 Los archivos \<directorio de instalación\>\OrderBroker_Proxy  
  
|Archivo|Description|  
|----------|-----------------|  
|Global.asax|Archivo generado.|  
|Index.htm|Archivo generado.|  
|OrderBrokerOrch_OrderPort.asmx|Archivo generado.|  
|Web.config|Archivo generado.|  
  
 Los archivos \<directorio de instalación\>\OrderBroker_Proxy\App_Code  
  
|Archivo|Description|  
|----------|-----------------|  
|DataTypes.cs|Archivo generado.|  
|OrderBrokerOrch_OrderPort.asmx.cs|Archivo generado.|  
  
 Los archivos \<directorio de instalación\>\OrderHandler  
  
|Archivo|Description|  
|----------|-----------------|  
|OrderHandler.cs|Código C# para el **OrderHandler** objeto.|  
|OrderHandler.csproj|Archivo de proyecto de C#.|  
  
 Los archivos \<directorio de instalación\>\Rules  
  
|Archivo|Description|  
|----------|-----------------|  
|DecodeAndValidateOrderRules.xml|Archivo de reglas para el motor de reglas de negocios.|  
  
 Los archivos \<directorio de instalación\>\SampleMessages  
  
|Archivo|Description|  
|----------|-----------------|  
|CSR_OrderRequest.xml|Solicitud de pedido de atención al cliente de ejemplo.|  
|OrderEnvelope.xml|Sobre de pedido de ejemplo.|  
  
 Los archivos \<directorio de instalación\>\SchemaClasses  
  
|Archivo|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|Archivo de información sobre el ensamblado.|  
|InternalMessages.cs|Código C# para las clases que definen los mensajes utilizados para la comunicación entre los componentes de la solución.|  
|SchemaClasses.csproj|Archivo de proyecto de C#.|  
  
 Los archivos \<directorio de instalación\>\Schemas  
  
|Archivo|Description|  
|----------|-----------------|  
|Order.xsd|Esquema para el mensaje de pedido.|  
|OrderPropertySchema.xsd|Esquema de propiedades promocionadas para el mensaje de pedido.|  
|Schemas.btproj|Archivo de proyecto de BizTalk.|  
  
 Los archivos \<directorio de instalación\>\Scripts  
  
|Archivo|Description|  
|----------|-----------------|  
|CleanDirs.cmd|Archivo de comandos para eliminar directorios que emplean archivos que sólo usan la versión de prueba de la solución.|  
|CreateAppReferences.vbs|VBScript para crear referencias de aplicación.|  
|CreateQueues.vbs|VBScript para crear colas MSMQ.|  
|CreateSouthridgeVideoApplication.cmd|Archivo de comandos para crear los valores de configuración en el almacén de configuración SSO.|  
|CreateTestDirectories.cmd|Archivo de comandos para crear directorios para la versión de prueba de la solución.|  
|DeployBPM.cmd|Archivo de comandos para implementar la solución. |  
|regac.bat|Archivo por lotes para registrar ensamblados en la caché de ensamblados global (GAC).|  
|SouthridgeVideoSSOConfiguration.xml|Archivo que contiene los valores de configuración SSO iniciales.|  
  
 Los archivos \<directorio de instalación\>\ServiceLevelTracking  
  
|Archivo|Description|  
|----------|-----------------|  
|Activity_CustomerOrderRequest.cs|Código C# para definir las actividades de SAE de solicitud de pedido de cliente.|  
|Activity_OrderManager.cs|Código C# para definir las actividades de SAE del administrador de pedidos.|  
|Activity_ServiceOrderRequest.cs|Código C# para definir las actividades de SAE de solicitud de pedido de atención al cliente.|  
|ServiceLevelTracking.cs|Código C# para definir la clase base abstracta para las actividades.|  
|ServiceLevelTracking.csproj|Archivo de proyecto de C#.|  
  
 Los archivos \<directorio de instalación\>\Utilities  
  
|Archivo|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|Archivo de información sobre el ensamblado.|  
|CableOrderException.cs|Código C# que define la clase de excepción de pedido de cable.|  
|Helper.cs|Código C# para varios métodos y clases de ayuda.|  
|Recaller.cs|Código C# para el **Recaller** objeto.|  
|SSOConfigHelper.cs|Código C# para los métodos y objetos de ayuda de la configuración SSO.|  
|Utilities.csproj|Archivo de proyecto de C#.|  
  
## <a name="see-also"></a>Vea también  
 [Referencia de solución de administración de proceso empresarial](../core/business-process-management-solution-reference.md)   
 [Componentes de la solución de administración de procesos empresariales](../core/components-of-the-business-process-management-solution.md)