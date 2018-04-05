---
title: Solución orientada a servicios de inventario de archivos para el servicio | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solution tutorial, file inventory
ms.assetid: 32c25372-31e1-4059-b4ed-f12e62f315d5
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39d18b32e1b499009e7559a68d7e60e6ba43f28c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="file-inventory-for-the-service-oriented-solution"></a>Solución orientada a servicios de inventario de archivos para el servicio
En esta sección se enumeran los subdirectorios y los archivos de origen para la solución orientada a servicios. El directorio de instalación predeterminado para los archivos de origen de la solución orientada a servicios es [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Scenarios\SO. Las descripciones antes de las siguientes tablas reemplazan esta ruta con \<directorio de instalación\>.  
  
 Los archivos \<directorio de instalación\>\BTSSoln  
  
|Archivo|Description|  
|----------|-----------------|  
|Microsoft.Samples.BizTalk.WoodgroveBank.sln|Archivo de solución de Visual Studio.|  
|ReplacePKToken.vbs|VBScript para corregir símbolos (tokens) de clave pública en los archivos de la solución cuando se genera la solución.|  
|ReplacePKToken.wsf|Archivo de secuencia de comandos para el VBScript ReplacePKToken.|  
|SetupBTSSoln.bat|Crea una clave pública, actualiza las referencias a la clave pública y compila la solución. Para obtener información acerca de cómo implementar la solución, vea [implementar la solución orientada a servicios](../core/deploying-the-service-oriented-solution.md).|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\BAM  
  
|Archivo|Description|  
|----------|-----------------|  
|ServiceLevelTracking.xls|Hoja de cálculo de Excel para los datos de SAE.|  
|ServiceLevelTracking.xml|Esquema que define los tipos de elementos de datos de SAE.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\Bindings  
  
|Archivo|Description|  
|----------|-----------------|  
|AdapterSOAOrchBindings.xml|Archivos de enlace para la versión de adaptador de la solución.|  
|InlineSOAOrchBindings.xml|Archivos de enlace para la versión en línea de la solución.|  
|StubSOAOrchBindings.xml|Archivos de enlace para la versión de código auxiliar de la solución.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\ConfigHelper  
  
|Archivo|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|Archivo de información sobre el ensamblado.|  
|ConfigHelper.csproj|Archivo de proyecto de C#.|  
|ConfigParameters.cs|Archivo de código C# para los métodos de ayuda de la configuración SSO.|  
|ConfigPropertyBag.cs|Archivo de código C# para la bolsa de propiedades que utilizan los métodos de ayuda de la configuración SSO.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\ErrorHelper  
  
|Archivo|Description|  
|----------|-----------------|  
|CustomerServiceErrors.cs|Archivo de código C# para los errores de atención al cliente.|  
|ErrorHelper.csproj|Archivo de proyecto de C#.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\InPipeline  
  
|Archivo|Description|  
|----------|-----------------|  
|InPipeline.btp|Canalización de recepción que agrega un vale de SSO al mensaje.|  
|InPipeline.btproj|Archivo de proyecto de BizTalk.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\InPipelineComp  
  
|Archivo|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|Archivo de información sobre el ensamblado.|  
|InPipelineComp.csproj|Archivo de proyecto de C#.|  
|SSOTicketIssuer.cs|Archivo de código C# para el componente de canalización que emite vales de SSO.|  
|SSOTicketIssuer.resx|Archivo de recursos.|  
|SSOTicketIssuerIcon.bmp|Archivo de icono para el componente de canalización.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\Maps  
  
|Archivo|Description|  
|----------|-----------------|  
|Aggregate_To_CustomerServiceResponse.btm|Asignación para convertir la agregación de las tres respuestas de los sistemas servidor en un solo mensaje de respuesta.|  
|Aggregate_To_ErrorResponse.btm|Asignación para convertir la agregación de las tres respuestas en una sola respuesta de error cuando se produce un error.|  
|CustomerServiceRequest_To_CreditLimiRequest.btm|Asignación para convertir una solicitud de atención al cliente en un mensaje para solicitar el límite de crédito.|  
|CustomerServiceRequest_To_CreditLimitResponse.btm|Asignación para convertir una solicitud de atención al cliente en un mensaje para responder con el límite de crédito.|  
|CustomerServiceRequest_To_CustomerServiceResponseDenied.btm|Asignación para convertir una solicitud de atención al cliente en un mensaje de solicitud denegada.|  
|CustomerServiceRequest_To_LastPaymentRequest.btm|Asignación para convertir una solicitud de atención al cliente en un mensaje para solicitar la información del último pago.|  
|CustomerServiceRequest_To_LastPaymentResponseTimeout.btm|Asignación para convertir una solicitud de atención al cliente en un mensaje de respuesta del último pago.|  
|CustomerServiceRequest_To_PendingTransactionResponse.btm|Asignación para convertir una solicitud de atención al cliente en un mensaje de respuesta de transacción pendiente.|  
|CustomerServiceRequest_To_PendingTransactionsRequest.btm|Asignación para convertir una solicitud de atención al cliente en un mensaje para solicitar la información de la transacción pendiente.|  
|Maps.btproj|Archivo de proyecto de BizTalk.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\Orchestrations\Adapter  
  
|Archivo|Description|  
|----------|-----------------|  
|CustomerService.odx|Versión del adaptador de la **CustomerService** orquestación.|  
|CustomerServiceNativeRequestResponse.odx|Versión del adaptador de orquestación que actúa como front-end a la **CustomerService** orquestación.|  
|CustomerServiceReceiveSend.odx|Versión del adaptador de orquestación que actúa como front-end a la **CustomerService** orquestación.|  
|Orchestrations.Adapter.btproj|Archivo de proyecto de BizTalk.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\Orchestrations\Adapter\Web References\PendTransWS  
  
|Archivo|Description|  
|----------|-----------------|  
|PendTransWS.disco|Archivo generado.|  
|PendTransWS.wsdl|Archivo generado.|  
|Reference.map|Archivo generado.|  
|Reference.map.cs|Archivo generado|  
|Reference.odx|Archivo generado.|  
|Reference.xsd|Archivo generado.|  
|Reference1.xsd|Archivo generado.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\Orchestrations\Adapter\Web References\StubSAPWS  
  
|Archivo|Description|  
|----------|-----------------|  
|Reference.map|Archivo generado.|  
|Reference.map.cs|Archivo generado.|  
|Reference.odx|Archivo generado.|  
|Reference.xsd|Archivo generado.|  
|StubSAPWS.disco|Archivo generado.|  
|StubSAPWS.wsdl|Archivo generado.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\Orchestrations\Inline  
  
|Archivo|Description|  
|----------|-----------------|  
|CustomerService.odx|Versión en línea de la **CustomerService** orquestación.|  
|CustomerServiceNativeRequestResponse.odx|Versión en línea de orquestación que actúa como front-end a la **CustomerService** orquestación.|  
|CustomerServiceReceiveSend.odx|Versión en línea de orquestación que actúa como front-end a la **CustomerService** orquestación.|  
|Orchestrations.Inline.btproj|Archivo de proyecto de BizTalk.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\Orchestrations\Stub  
  
|Archivo|Description|  
|----------|-----------------|  
|CustomerService.odx|Versión de código auxiliar de la **CustomerService** orquestación.|  
|CustomerServiceNativeRequestResponse.odx|Versión de código auxiliar de orquestación que actúa como front-end a la **CustomerService** orquestación.|  
|Orchestrations.Stub.btproj|Archivo de proyecto de BizTalk.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\Orchestrations\Stub\Web References\StubPendTransWS  
  
|Archivo|Description|  
|----------|-----------------|  
|Reference.map|Archivo generado.|  
|Reference.map.cs|Archivo generado.|  
|Reference.odx|Archivo generado.|  
|Reference.xsd|Archivo generado.|  
|Reference1.xsd|Archivo generado.|  
|StubPendTransWS.disco|Archivo generado.|  
|StubPendTransWS.wsdl|Archivo generado.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\Orchestrations\Stub\Web References\StubPmntTrckWS  
  
|Archivo|Description|  
|----------|-----------------|  
|Reference.map|Archivo generado.|  
|Reference.map.cs|Archivo generado.|  
|Reference.odx|Archivo generado.|  
|Reference.xsd|Archivo generado.|  
|Reference1.xsd|Archivo generado.|  
|StubPmntTrckWS.disco|Archivo generado.|  
|StubPmntTrckWS.wsdl|Archivo generado.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\Orchestrations\Stub\Web References\StubSAPWS  
  
|Archivo|Description|  
|----------|-----------------|  
|Reference.map|Archivo generado.|  
|Reference.map.cs|Archivo generado.|  
|Reference.odx|Archivo generado.|  
|Reference.xsd|Archivo generado.|  
|StubSAPWS.disco|Archivo generado.|  
|StubSAPWS.wsdl|Archivo generado.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\OrchProxy\Adapter  
  
|Archivo|Description|  
|----------|-----------------|  
|CustomerServicePort.asmx|Archivo generado.|  
|Global.asax|Archivo generado.|  
|Global.asax.resx|Archivo generado.|  
|OrchProxy.Adapter.csproj.webinfo|Archivo generado.|  
|TraceExtension.cs|Archivo generado.|  
|Web.config|Archivo generado.|  
|WsdlExtension.cs|Archivo generado.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\OrchProxy\Adapter\app_code  
  
|Archivo|Description|  
|----------|-----------------|  
|assemblyinfo.cs|Archivo generado.|  
|customerserviceport.asmx.cs|Archivo generado.|  
|datatypes.cs|Archivo generado.|  
|global.asax.cs|Archivo generado.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\OrchProxy\Inline  
  
|Archivo|Description|  
|----------|-----------------|  
|CustomerServicePort.asmx|Archivo generado.|  
|Global.asax|Archivo generado.|  
|Global.asax.resx|Archivo generado.|  
|OrchProxy.Inline.csproj.webinfo|Archivo generado.|  
|TraceExtension.cs|Archivo generado.|  
|Web.config|Archivo generado.|  
|WsdlExtension.cs|Archivo generado.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\OrchProxy\Inline\app_code  
  
|Archivo|Description|  
|----------|-----------------|  
|assemblyinfo.cs|Archivo generado.|  
|customerserviceport.asmx.cs|Archivo generado.|  
|datatypes.cs|Archivo generado.|  
|global.asax.cs|Archivo generado.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\OrchProxy\Stub  
  
|Archivo|Description|  
|----------|-----------------|  
|CustomerServicePort.asmx|Archivo generado.|  
|Global.asax|Archivo generado.|  
|Global.asax.resx|Archivo generado.|  
|OrchProxy.Stub.csproj.webinfo|Archivo generado.|  
|TraceExtension.cs|Archivo generado.|  
|Web.config|Archivo generado.|  
|WsdlExtension.cs|Archivo generado.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\OrchProxy\Stub\app_code  
  
|Archivo|Description|  
|----------|-----------------|  
|assemblyinfo.cs|Archivo generado.|  
|customerserviceport.asmx.cs|Archivo generado.|  
|datatypes.cs|Archivo generado.|  
|global.asax.cs|Archivo generado.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\PaymentTracker  
  
|Archivo|Description|  
|----------|-----------------|  
|App.ico|Archivo de icono para el simulador de seguimiento de pago.|  
|AssemblyInfo.cs|Archivo de información sobre el ensamblado.|  
|MessageProcessor.cs|Código C# para que una clase procese los mensajes de seguimiento de pago y devuelva las respuestas apropiadas.|  
|PaymentTracker.cs|Código C# para la clase que simula el sistema de seguimiento de pagos.|  
|PaymentTracker.csproj|Archivo de proyecto de C#.|  
|PaymentTrackerSimulator.cs|Código C# para el servidor para el simulador de seguimiento de pago.|  
|runit.cmd|Archivo de comandos para iniciar el simulador de seguimiento de pago.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\PaymentTrackerCall  
  
|Archivo|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|Archivo de información sobre el ensamblado.|  
|Exceptions.cs|Código C# que define las excepciones para el sistema de seguimiento de pagos.|  
|PaymentTrackerCall.csproj|Archivo de proyecto de C#.|  
|PaymentTrackerCaller.cs|Código C# para llamar al sistema de seguimiento de pagos en línea desde las orquestaciones.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\PendTransCall  
  
|Archivo|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|Archivo de información sobre el ensamblado.|  
|Exceptions.cs|Código C# que define las excepciones para el sistema de transacciones pendientes.|  
|PendingTransactionsCaller.cs|Código C# para llamar al sistema de transacciones pendientes en línea desde las orquestaciones.|  
|PendingTransactionsWebService.disco|Archivo generado.|  
|PendingTransactionsWebService.wsdl|Archivo generado.|  
|PendTransCall.csproj|Archivo de proyecto de C#.|  
|WebServiceReference.cs|Archivo generado.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\PmTrkPipeline  
  
|Archivo|Description|  
|----------|-----------------|  
|PaymentTrackerReceivePipeline.btp|Canalización de recepción para el sistema de seguimiento de pagos.|  
|PaymentTrackerSendPipeline.btp|Canalización de envío para el sistema de seguimiento de pagos.|  
|PmTrkPipeline.btproj|Archivo de proyecto de BizTalk.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\PmTrkPipelineComp  
  
|Archivo|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|Archivo de información sobre el ensamblado.|  
|MQSeriesHeaderSetter.cs|Código C# para que un componente de canalización controle algunos de los valores de configuración del encabezado de los mensajes MQSeries de los mensajes que entran o salen del sistema de seguimiento de pagos.|  
|MQSeriesHeaderSetter.resx|Archivo de recursos.|  
|PmTrkPipelineComp.csproj|Archivo de proyecto de C#.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\SchemaClasses  
  
|Archivo|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|Archivo de información sobre el ensamblado.|  
|BAPI_BANKACCT_GET_DETAIL.cs|Se generó a partir del archivo de esquema (.xsd) correspondiente.|  
|CustomerServiceRequest.cs|Se generó a partir del archivo de esquema (.xsd) correspondiente.|  
|CustomerServiceResponse.cs|Se generó a partir del archivo de esquema (.xsd) correspondiente.|  
|LastPaymentRequest.cs|Se generó a partir del archivo de esquema (.xsd) correspondiente.|  
|LastPaymentResponse.cs|Se generó a partir del archivo de esquema (.xsd) correspondiente.|  
|PendingTransactionsRequest.cs|Se generó a partir del archivo de esquema (.xsd) correspondiente.|  
|PendingTransactionsResponse.cs|Se generó a partir del archivo de esquema (.xsd) correspondiente.|  
|SchemaClasses.csproj|Archivo de proyecto de C#.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\Schemas  
  
|Archivo|Description|  
|----------|-----------------|  
|BAPI_BANKACCT_GET_DETAIL.xsd|Esquema para el mensaje SAP de solicitud y respuesta.|  
|CustomerServiceRequest.xsd|Esquema del mensaje de solicitud de atención al cliente.|  
|CustomerServiceResponse.xsd|Esquema del mensaje de respuesta de atención al cliente.|  
|genClasses.cmd|Archivo de comandos para generar archivos de clase C# de esquemas.|  
|LastPaymentRequest.xsd|Esquema para el último mensaje de solicitud de pago.|  
|LastPaymentResponse.xsd|Esquema para el último mensaje de respuesta de pago.|  
|PendingTransactionsRequest.xsd|Esquema para el mensaje de solicitud de transacción pendiente.|  
|PendingTransactionsResponse.xsd|Esquema para el mensaje de respuesta de transacción pendiente.|  
|Schemas.btproj|Archivo de proyecto de BizTalk.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\Scripts  
  
|Archivo|Description|  
|----------|-----------------|  
|ConfigStoreApp.xml|Archivo XML que define los valores de configuración SSO.|  
|CreateInitialConfigInSSO.cmd|Archivo de comandos para crear los valores iniciales de configuración SSO.|  
|DeployAllBinding.cmd|Archivo de comandos para implementar todos los ensamblados.|  
|DeployStubBinding.cmd|Archivo de comandos para implementar la versión de código auxiliar de los ensamblados.|  
|PendTransAffApp.xml|Archivo XML que define los valores para la aplicación afiliada de transacciones pendientes.|  
|PendTransUserMap.xml|Archivo XML que define asignaciones de credenciales para usuarios para la aplicación afiliada de transacciones pendientes.|  
|PmntTrckAffApp.xml|Archivo XML que define los valores para la aplicación afiliada de transacciones pendientes.|  
|PmntTrckUserMap.xml|Archivo XML que define asignaciones de credenciales para usuarios para la aplicación afiliada de seguimiento de pagos.|  
|RemoveReceivePort.vbs|VBScript general para quitar un puerto de recepción.|  
|RemoveSendPort.vbs|VBScript general para quitar un puerto de envío.|  
|SetConfigValuesInSSO.cmd|Archivo de comandos para establecer los valores de configuración en SSO.|  
|StartAll.vbs|Archivo de comandos que da de alta e inicia todas las orquestaciones.|  
|StartStub.vbs|Archivo de comandos que da de alta e inicia las versiones de código auxiliar de orquestaciones.|  
|UndeployAll.cmd|Archivo de comandos para anular la implementación de todos los ensamblados.|  
|UndeployStub.cmd|Archivo de comandos para anular la implementación de las versiones de código auxiliar de los ensamblados.|  
|UnEnlistAll.vbs|Archivo de comandos que da de baja todas las orquestaciones.|  
|UnEnlistStub.vbs|Archivo de comandos para dar de baja las versiones de código auxiliar de las orquestaciones.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\ServiceLevelTracking  
  
|Archivo|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|Archivo de información sobre el ensamblado.|  
|ServiceLevelTracking.cs|Funciones auxiliares de C# para el seguimiento de nivel de servicio de SAE.|  
|ServiceLevelTracking.csproj|Archivo de proyecto de C#.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\SimpleClient  
  
|Archivo|Description|  
|----------|-----------------|  
|AdapterCustomerServicePort.disco|Archivo generado.|  
|AdapterCustomerServicePort.wsdl|Archivo generado.|  
|App.ico|Archivo de icono para aplicación de cliente sencillo.|  
|AssemblyInfo.cs|Archivo de información sobre el ensamblado.|  
|InlineCustomerServicePort.disco|Archivo generado.|  
|InlineCustomerServicePort.wsdl|Archivo generado.|  
|SimpleClient.cs|Aplicación sencilla de Windows Forms para realizar solicitudes.|  
|SimpleClient.csproj|Archivo de proyecto de C#.|  
|SimpleClient.resx|Archivo de recursos.|  
|WebServiceReferences.cs|Archivo generado.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\StubWebServices\PaymentTrack  
  
|Archivo|Description|  
|----------|-----------------|  
|Global.asax|Archivo generado.|  
|Global.asax.resx|Archivo generado.|  
|StubPmntTrck.csproj.webinfo|Archivo generado.|  
|StubPmntTrckWS.asmx|Archivo generado.|  
|StubPmntTrckWS.asmx.resx|Archivo generado.|  
|Web.config|Archivo generado.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\StubWebServices\PaymentTrack\app_code  
  
|Archivo|Description|  
|----------|-----------------|  
|assemblyinfo.cs|Archivo de información sobre el ensamblado.|  
|global.asax.cs|Archivo generado.|  
|StubPmntTrckWS.asmx.cs|Archivo generado.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\StubWebServices\PendingTrans  
  
|Archivo|Description|  
|----------|-----------------|  
|Global.asax|Archivo generado.|  
|Global.asax.resx|Archivo generado.|  
|StubPendTransWS.asmx|Archivo generado.|  
|StubPendTransWS.asmx.resx|Archivo generado.|  
|StubPendTransWS.csproj.webinfo|Archivo generado.|  
|Web.config|Archivo generado.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\StubWebServices\PendingTrans\app_code  
  
|Archivo|Description|  
|----------|-----------------|  
|assemblyinfo.cs|Archivo generado.|  
|global.asax.cs|Archivo generado.|  
|StubPendTransWS.asmx.cs|Archivo generado.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\StubWebServices\SAP  
  
|Archivo|Description|  
|----------|-----------------|  
|Global.asax|Archivo generado.|  
|Global.asax.resx|Archivo generado.|  
|StubSAP.csproj.webinfo|Archivo generado.|  
|StubSAPWS.asmx|Archivo generado.|  
|StubSAPWS.asmx.resx|Archivo generado.|  
|Web.config|Archivo generado.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\StubWebServices\SAP\app_code  
  
|Archivo|Description|  
|----------|-----------------|  
|assemblyinfo.cs|Archivo de información sobre el ensamblado.|  
|global.asax.cs|Archivo generado.|  
|stubsapws.asmx.cs|Archivo generado.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\StubWebServices\StubSAPCall  
  
|Archivo|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|Archivo de información sobre el ensamblado.|  
|Exceptions.cs|Código C# que define la excepción de tiempo de espera de la llamada a SAP del código auxiliar.|  
|StubSAPCall.csproj|Archivo de proyecto de C#.|  
|StubSAPCallHelper.cs|Código C# para que un ensamblado auxiliar llame al servicio Web SAP de código auxiliar.|  
|StubSAPWSProxy.cs|Código C# para que un ensamblado auxiliar llame al servicio Web SAP de código auxiliar.|  
  
 Los archivos \<directorio de instalación\>\BTSSoln\Utilities  
  
|Archivo|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|Archivo de información sobre el ensamblado.|  
|CustomerServiceHelper.cs|Código C# para métodos y clases auxiliares.|  
|ReceivePipelineHelper.cs|Código C# para que un ensamblado auxiliar llame a las canalizaciones desde las orquestaciones.|  
|Utilities.csproj|Archivo de proyecto de C#.|  
  
 Los archivos \<directorio de instalación\>\MFAccess  
  
|Archivo|Description|  
|----------|-----------------|  
|Microsoft.Samples.BizTalk.WoodgroveBank.MainframeAccess.sln|Archivo de solución de Visual Studio.|  
|SetupMFAccess.bat|Archivo por lotes que genera los componentes de acceso de los grandes sistemas (mainframes) a la solución.|  
  
 Los archivos \<directorio de instalación\>\MFAccess\HISTIComponent  
  
|Archivo|Description|  
|----------|-----------------|  
|bizcbl.txt|Programa COBOL ideado para ejecución en el gran sistema.|  
|HISTIComponent.tiproj|Archivo de proyecto de Transaction Integrator.|  
|MainFrameProgramVTCS2Description.txt|Archivo de exportación de Transaction Integrator.|  
|SOHISTIUsingCOM.TLB|Biblioteca de tipos.|  
  
 Los archivos \<directorio de instalación\>\MFAccess\HISTISimpleTester  
  
|Archivo|Description|  
|----------|-----------------|  
|App.ico|Archivo de icono|  
|AssemblyInfo.cs|Archivo de información sobre el ensamblado.|  
|Form1.cs|Programa de formularios Windows Forms para probar la conexión al sistema grande.|  
|Form1.resx|Archivo de recursos|  
|HISTISimpleTester.csproj|Archivo de proyecto de C#.|  
|Interop.SOHISTIUsingCOM.dll.reg|Archivo de registro DLL.|  
  
 Los archivos \<directorio de instalación\>\MFAccess\PendingTransactions  
  
|Archivo|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|Archivo de información sobre el ensamblado.|  
|Global.asax|Archivo generado.|  
|Global.asax.cs|Archivo generado.|  
|Global.asax.resx|Archivo generado.|  
|PendingTransactions.csproj|Archivo de proyecto de C#.|  
|PendingTransactions.csproj.webinfo|Archivo generado.|  
|PendTransWS.asmx|Archivo generado.|  
|PendTransWS.asmx.cs|Archivo generado.|  
|PendTransWS.asmx.resx|Archivo generado.|  
|Web.config|Archivo generado.|  
  
 Los archivos \<directorio de instalación\>\MFAccess\SchemaClasses  
  
|Archivo|Description|  
|----------|-----------------|  
|AssemblyInfo.cs|Archivo de información sobre el ensamblado.|  
|BAPI_BANKACCT_GET_DETAIL.cs|Clase C# generada a partir del archivo de esquema (.xsd) correspondiente.|  
|CustomerServiceRequest.cs|Clase C# generada a partir del archivo de esquema (.xsd) correspondiente.|  
|CustomerServiceResponse.cs|Clase C# generada a partir del archivo de esquema (.xsd) correspondiente.|  
|LastPaymentRequest.cs|Clase C# generada a partir del archivo de esquema (.xsd) correspondiente.|  
|LastPaymentResponse.cs|Clase C# generada a partir del archivo de esquema (.xsd) correspondiente.|  
|PendingTransactionsRequest.cs|Clase C# generada a partir del archivo de esquema (.xsd) correspondiente.|  
|PendingTransactionsResponse.cs|Clase C# generada a partir del archivo de esquema (.xsd) correspondiente.|  
|SchemaClasses.csproj|Archivo de proyecto de C#.|  
  
## <a name="see-also"></a>Vea también  
 [Solución orientada a servicios de componentes del servicio](../core/components-of-the-service-oriented-solution.md)   
 [Referencia de la solución orientada a servicios](../core/service-oriented-solution-reference.md)