---
title: Cómo ejecutar el servicio de la solución orientada a servicios | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solution tutorial, client applications
- service solution tutorial, starting solution
- service solution tutorial, sending requests
- service solution tutorial, SOAP transports
ms.assetid: 764a5ddc-e571-41d8-9e2f-6d0fb3361b2f
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35c33b914ecbb9f385e5546d100b7572b4b48b6a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973818"
---
# <a name="how-to-run-the-service-oriented-solution"></a>Cómo ejecutar la solución orientada a servicios
Los pasos siguientes describen cómo ejecutar y validar la solución orientada a servicios en un único equipo. Una vez iniciado el simulador de seguimiento de pago, puede enviar solicitudes utilizando el transporte SOAP o MQSeries (con procedimientos independientes para las versiones de adaptador en línea de la solución orientada a servicios).  
  
-   [Enviar solicitudes con el transporte SOAP utilizando la aplicación de cliente (versión de código auxiliar)](#step1)  
  
-   [Enviar solicitudes utilizando la aplicación de cliente (versión de adaptador)](#step3)  
  
-   [Enviar solicitudes utilizando la aplicación de cliente (versión en línea)](#step5)  
  
##  <a name="step1"></a>Enviar solicitudes con el transporte SOAP utilizando la aplicación de cliente (versión de código auxiliar)  
  
#### <a name="to-send-requests-by-soap-transport-using-the-client-application-stub-version"></a>Para enviar solicitudes con el transporte SOAP utilizando la aplicación de cliente (versión de código auxiliar)  
  
1.  Abra un símbolo del sistema, cambie el directorio a la \< *directorio de instalación de BizTalk Server*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release y, a continuación, ejecute BTSScnSOSimpleClient.exe.  
  
2.  Escriba unos caracteres en el **RequestType**, **RequestSource**, y **RequestID** cuadros de texto.  
  
3.  Escriba cualquier número de 16 dígitos en el **número de cuenta** cuadro de texto.  
  
4.  Seleccione **SOAP (WS Call)** y **código auxiliar** en el **Select Transport and Parameters** cuadro de grupo.  
  
5.  Escriba la dirección URL siguiente en la **URL** cuadro de texto, por ejemplo:  
  
6.  `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Stub/CustomerServicePort.asmx`  
  
7.  Tipo de `ZipCode` en el **nombre** cuadro de texto bajo **Authentication Elements**y, a continuación, escriba unos caracteres en el **valor** cuadro de texto.  
  
8.  Tipo de `CustomerName` en el **nombre** cuadro de texto bajo **Authentication Elements**y, a continuación, escriba unos caracteres en el **valor** cuadro de texto.  
  
9. Haga clic en **obtener mi Saldo**.  
  
10. La respuesta se muestra en el **respuesta** cuadro de texto: **correcto** aparece si la solicitud se realiza correctamente; un mensaje de error aparece si se produce un error en la solicitud.  
  
     ![Ejecutar la aplicación de cliente para la versión de código auxiliar](../core/media/bts-cp-so-deploy-stubversion-success.gif "BTS_CP_SO_Deploy_StubVersion_Success")  
  
##  <a name="step3"></a>Enviar solicitudes utilizando la aplicación de cliente (versión de adaptador)  
  
#### <a name="to-send-requests-using-the-client-application-adapter-version"></a>Para enviar solicitudes utilizando la aplicación de cliente (versión de adaptador)  
  
1.  Abra un símbolo del sistema, cambie al directorio \< *directorio de instalación de BizTalk Server*\>\SDK\Scenarios\SO\BTSSoln\PaymentTracker\bin\Debug y, a continuación, ejecute el siguiente comando para iniciar el Simulador de seguimiento de pago:  
  
     `BTSScnSOPaymentTracker.exe LastPaymentsInputQueue LastPaymentsOutputQueue <`*Nombre del Administrador de cola* `> 5 [<` *definición de canal*`>]`  
  
    > [!NOTE]
    >  La definición de canal es opcional si MQSeries Server no es remoto.  
  
    -   Deje que el simulador de seguimiento de pago se ejecute.  
  
2.  Abra un símbolo del sistema, cambie el directorio a la \< *directorio de instalación de BizTalk Server*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release y, a continuación, ejecute BTSScnSOSimpleClient.exe.  
  
3.  En BTSScnSOSimpleClient.exe, envíe una solicitud mediante el transporte SOAP del siguiente modo:  
  
    1.  Escriba unos caracteres en el **RequestType**, **RequestSource**, y **RequestID** cuadros de texto.  
  
    2.  Escriba cualquier número de 16 dígitos en el **número de cuenta** cuadro de texto.  
  
    3.  Seleccione **SOAP (WS Call)** y **adaptador** en el **Select Transport and Parameters** cuadro de grupo.  
  
    4.  Escriba la dirección URL siguiente en la **URL** cuadro de texto, por ejemplo:  
  
         `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Adapter/CustomerServicePort.asmx`  
  
    5.  Tipo de `ZipCode` en el **nombre** cuadro de texto bajo **Authentication Elements**y, a continuación, escriba unos caracteres en el **valor** cuadro de texto.  
  
    6.  Tipo de `CustomerName` en el **nombre** cuadro de texto bajo **Authentication Elements**y, a continuación, escriba unos caracteres en el **valor** cuadro de texto.  
  
    7.  Haga clic en **obtener mi Saldo**.  
  
    8.  La respuesta se muestra en el **respuesta** cuadro de texto: **correcto** aparece si la solicitud se realiza correctamente; un mensaje de error aparece si se produce un error en la solicitud.  
  
         ![Ejecutar la aplicación cliente para la versión del adaptador](../core/media/soap-transport-adapter-success.gif "SOAP_Transport_adapter_success")  
  
4.  En BTSScnSOSimpleClient.exe, envíe solicitudes mediante el transporte MQSeries del siguiente modo:  
  
    1.  Escriba unos caracteres en el **RequestType**, **RequestSource**, y **RequestID** cuadros de texto.  
  
    2.  Escriba un número de 16 dígitos en el **número de cuenta** cuadro de texto.  
  
    3.  Seleccione **MQSeries** en el **Select Transport and Parameters** cuadro de grupo.  
  
    4.  Tipo de \< *nombre del Administrador de cola* \> en el **Administrador de cola** cuadro de texto. QM_\<*el nombre del equipo* \> es el valor predeterminado de \< *nombre del Administrador de cola*\>.  
  
    5.  Tipo de `AdapterSOAInputQueue` en el **Input Queue** cuadro de texto.  
  
    6.  Tipo de `AdapterSOAOutputQueue` en el **cola de salida** cuadro de texto.  
  
    7.  Tipo de \< *definición de canal* \> en el **definición de canal** cuadro. S_\<*el nombre del equipo*\>/TCP /\<*el nombre del equipo*\>(1414) es el valor predeterminado de \<  *Definición de canal*\>.  
  
    8.  Tipo de `ZipCode` en el **nombre** cuadro de texto bajo **Authentication Elements**y, a continuación, escriba unos caracteres en el **valor** cuadro de texto.  
  
    9. Tipo de `CustomerName` en el **nombre** cuadro de texto bajo **Authentication Elements**y, a continuación, escriba unos caracteres en el **valor** cuadro de texto.  
  
    10. Haga clic en **obtener mi Saldo**.  
  
    11. La respuesta se muestra en el **respuesta** cuadro de texto: **correcto** aparece si la solicitud se realiza correctamente; un mensaje de error aparece si se produce un error en la solicitud.  
  
         ![Ejecutar la aplicación cliente para la versión del adaptador](../core/media/mqseries-transport-adapter.gif "MQSeries_Transport_adapter")  
  
##  <a name="step5"></a>Enviar solicitudes utilizando la aplicación de cliente (versión en línea)  
  
#### <a name="to-send-requests-using-the-client-application-inline-version"></a>Para enviar solicitudes utilizando la aplicación de cliente (versión en línea)  
  
1.  Abra un símbolo del sistema, cambie al directorio \< *directorio de instalación de BizTalk Server*\>\SDK\Scenarios\SO\BTSSoln\PaymentTracker\bin\Debug y, a continuación, ejecute el siguiente comando para iniciar el Simulador de seguimiento de pago:  
  
     `BTSScnSOPaymentTracker.exe LastPaymentsInputQueue LastPaymentsOutputQueue <`*Nombre del Administrador de cola* `> 5 [<` *definición de canal*`>]`  
  
    > [!NOTE]
    >  La definición de canal es opcional si MQSeries Server no es remoto.  
  
    > [!NOTE]
    >  Omita este paso si el simulador de seguimiento de pago ya se está ejecutando.  
  
    -   Deje que el simulador de seguimiento de pago se ejecute.  
  
2.  En el **consola de administración de BizTalk Server**, expanda **BTSScn.SO.CustomerService**, haga clic en **ubicaciones de recepción**, haga clic en  **PaymentTrackingSystemOutputQueue** en el panel derecho y, a continuación, haga clic en **deshabilitar**.  
  
    > [!NOTE]
    >  La versión adaptador y la versión en línea utilizan la misma cola MQSeries, LastPaymentsOutputQueue. Para evitar la condición de anticipación entre dos versiones, deshabilite la escucha de la ubicación de recepción de la versión adaptador en la cola MQSeries.  
  
3.  Abra un símbolo del sistema, cambie el directorio a la \< *directorio de instalación de BizTalk Server*\>\SDK\Scenarios\SO\BTSSoln\SimpleClient\bin\Release y, a continuación, ejecute BTSScnSOSimpleClient.exe.  
  
4.  En BTSScnSOSimpleClient.exe, envíe una solicitud mediante el transporte SOAP del siguiente modo:  
  
    1.  Escriba unos caracteres en el **RequestType**, **RequestSource**, y **RequestID** cuadros de texto.  
  
    2.  Escriba cualquier número de 16 dígitos en el **número de cuenta** cuadro de texto.  
  
    3.  Seleccione **SOAP (WS Call)** y **en línea** en el **Select Transport and Parameters** cuadro de grupo.  
  
    4.  Escriba la dirección URL siguiente en la **URL** cuadro de texto, por ejemplo:  
  
         `http://localhost/Microsoft.Samples.BizTalk.WoodgroveBank.OrchProxy.Inline/CustomerServicePort.asmx`  
  
    5.  Tipo de `ZipCode` en el **nombre** cuadro de texto bajo **Authentication Elements**y, a continuación, escriba unos caracteres en el **valor** cuadro de texto.  
  
    6.  Tipo de `CustomerName` en el **nombre** cuadro de texto bajo **Authentication Elements**y, a continuación, escriba unos caracteres en el **valor** cuadro de texto.  
  
    7.  Haga clic en **obtener mi Saldo**.  
  
    8.  La respuesta se muestra en el **respuesta** cuadro de texto: **correcto** aparece si la solicitud se realiza correctamente; un mensaje de error aparece si se produce un error en la solicitud.  
  
         ![Ejecutar la aplicación cliente para la versión en línea](../core/media/soap-transport-inline.gif "SOAP_Transport_inline")  
  
5.  En BTSScnSOSimpleClient.exe, envíe solicitudes mediante el transporte MQSeries del siguiente modo:  
  
    1.  Escriba unos caracteres en el **RequestType**, **RequestSource**, y **RequestID** cuadros de texto.  
  
    2.  Escriba un número de 16 dígitos en el **número de cuenta** cuadro de texto.  
  
    3.  Seleccione **MQSeries** en el **Select Transport and Parameters** cuadro de grupo.  
  
    4.  Tipo de \< *nombre del Administrador de cola* \> en el **Administrador de cola** cuadro de texto. QM_\<*el nombre del equipo* \> es el valor predeterminado de \< *nombre del Administrador de cola*\>.  
  
    5.  Tipo de `InlineSOAInputQueue` en el **Input Queue** cuadro de texto.  
  
    6.  Tipo de `InlineSOAOutputQueue` en el **cola de salida** cuadro de texto.  
  
    7.  Tipo de \< *definición de canal* \> en el **definición de canal** cuadro. S_\<*el nombre del equipo*\>/TCP /\<*el nombre del equipo*\>(1414) es el valor predeterminado de \<  *Definición de canal*\>.  
  
    8.  Tipo de `ZipCode` en el **nombre** cuadro de texto bajo **Authentication Elements**y, a continuación, escriba unos caracteres en el **valor** cuadro de texto.  
  
    9. Tipo de `CustomerName` en el **nombre** cuadro de texto bajo **Authentication Elements**y, a continuación, escriba unos caracteres en el **valor** cuadro de texto.  
  
    10. Haga clic en **obtener mi Saldo**.  
  
    11. La respuesta se muestra en el **respuesta** cuadro de texto: **correcto** aparece si la solicitud se realiza correctamente; un mensaje de error aparece si se produce un error en la solicitud.  
  
         ![Ejecutar la aplicación cliente para la versión en línea](../core/media/mqseries-transport-inline.gif "MQSeries_Transport_inline")  
  
## <a name="see-also"></a>Vea también  
 [Antes de instalar la solución orientada a servicios](../core/before-installing-the-service-oriented-solution.md)   
 [Cómo instalar la versión de código auxiliar del servicio en la solución orientada a servicios](../core/how-to-install-the-stub-version-of-the-service-oriented-solution.md)   
 [Cómo instalar las versiones de adaptador del servicio y en línea solución orientada a servicios](../core/how-to-install-the-inline-and-adapter-versions-of-the-service-oriented-solution.md)   
 [Configurar el equipo del desarrollador para la solución orientada a servicios](../core/developer-machine-setup-for-the-service-oriented-solution.md)