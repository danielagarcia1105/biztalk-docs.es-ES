---
title: Cómo ejecutar la solución de administración de procesos empresariales | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, validating
- process management solution tutorial, submitting orders
- process management solution tutorial, stopping orders
- process management solution tutorial, updating orders
ms.assetid: cb77651e-e16c-49dc-9f8a-88584cd68a8b
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3997fb18e7498ab2bc5f8c77b53740fb87ab6f93
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257628"
---
# <a name="how-to-run-the-business-process-management-solution"></a>Cómo ejecutar la solución de administración de proceso empresarial
Los pasos siguientes describen cómo ejecutar y validar la solución de administración de proceso empresarial en un único equipo.  
  
-   [Iniciar la solución de administración de procesos empresariales](#step1)  
  
-   [Ejecutar y validar la solución de administración de procesos empresariales](#step3)  
  
## <a name="prerequisites"></a>Requisitos previos  
 Antes de ejecutar la solución BPM, debe realizar los pasos descritos en [cómo instalar la solución de administración de procesos empresariales](../core/how-to-install-the-business-process-management-solution.md).  
  
##  <a name="step1"></a>Iniciar la solución de administración de procesos empresariales  
  
#### <a name="to-start-the-business-process-management-solution"></a>Para iniciar la solución de administración de proceso empresarial  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el **consola de administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**, expanda **instancias de Host**, Haga clic en **BizTalkServerApplication**y, a continuación, haga clic en **iniciar**.  
  
3.  En el **consola de administración de BizTalk Server**, expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.  
  
    1.  Haga clic en BTSScn.BPM.MessagingApp, haga clic en **iniciar**y, a continuación, haga clic en **iniciar** en el **Iniciar aplicación** cuadro de diálogo.  
  
    2.  Haga clic en BTSScn.BPM.OrderBrokerApp, haga clic en **iniciar**y, a continuación, haga clic en **iniciar** en el **Iniciar aplicación** cuadro de diálogo.  
  
    3.  Haga clic en BTSScn.BPM.CableOrderApp, haga clic en **iniciar**y, a continuación, haga clic en **iniciar** en el **Iniciar aplicación** cuadro de diálogo.  
  
    4.  Haga clic en BTSScn.BPM.OrderBrokerApp.Test y haga clic en **detener**. En el **detener aplicación** cuadro de diálogo, seleccione **detención completa: finalizar instancia**y, a continuación, haga clic en **detener**.  
  
    > [!NOTE]
    >  Para insertar información en la base de datos de historial. la orquestación OrderBroker utiliza el puerto de envío historyport, donde la **notificación de entrega** se establece la propiedad **transmitido**. El puerto de envío está enlazado con el grupo de envío HistoryInsert-SPG, que incluye los puertos de envío HistoryInsert-SP y HistoryInsert-Test-SP. En estos dos puertos de envío el motor de mensajes publicará dos mensajes de confirmación a la orquestación OrderBroker. Con esto, la orquestación se suspende debido a la existencia de mensajes sin consumir. Para evitar esta situación, debe dar de baja uno de los puertos de envío. En este tutorial, se dará de alta el puerto de envío HistoryInsert-Test-SP mediante la detención total de la aplicación BTSScn.BPM.OrderBrokerApp.Test. Para obtener más información acerca de la orquestación OrderBroker, vea [de procesamiento en la orquestación OrderBroker](../core/processing-in-the-orderbroker-orchestration.md). Para obtener más información acerca de **notificación de entrega** propiedad, vea [confirmaciones utilizando](../core/using-acknowledgments.md).  
  
4.  Ejecute el simulador de instalaciones como se indica a continuación:  
  
    1.  Abra un símbolo del sistema y cambie el directorio a la carpeta %BTSSolutionsPath%\BPM\FacilitiesSimulator\bin\debug.  
  
    2.  Escriba `BTSScnBPMFacilities.exe` y, a continuación, presione ENTRAR. Mantenga el simulador de instalaciones en ejecución. Esta aplicación simula las instalaciones que procesan sistemas de servidor en Southridge Video.  
  
    3.  En el simulador de instalaciones, escriba las siguientes colas de recepción y transmisión:  
  
        |Nombre|Valor|  
        |----------|-----------|  
        |**Cola de recepción**|`.\private$\ToFacilitiesQ`|  
        |**Cola de transmisión**|`.\private$\FromFacilitiesQ`|  
  
    4.  En el simulador de instalaciones, haga clic en **iniciar**.  
  
5.  Ejecute el servidor de operaciones como se indica a continuación:  
  
    1.  Abra un símbolo del sistema nuevo y cambie el directorio actual a la carpeta %BTSSolutionsPath%\BPM\OperationsServer\bin\debug.  
  
    2.  Tipo `BTSScnBPMOperations.exe 8881` en el símbolo del sistema y, a continuación, presione ENTRAR. Mantenga el servidor de operaciones en ejecución. El servidor de operaciones escucha en el puerto TCP, 8881, para recibir mensajes de error del adaptador Ops. Muestra los mensajes de error que recibe el adaptador Ops.  
  
6.  Ejecute el sistema de suministro de cable como se indica a continuación:  
  
    1.  Abra un símbolo del sistema nuevo y cambie el directorio actual a la carpeta %BTSSolutionsPath%\BPM\CableProvisioningSystemServer\bin\debug.  
  
    2.  Escriba `BTSScnBPMProvisioning.exe 8880` y, a continuación, presione ENTRAR. A continuación, mantenga el sistema de suministro de cable en ejecución. El sistema de suministro de Cable escucha en el puerto TPC 8880. Esta aplicación simula un sistema de pedidos de back-end y muestra los pedidos finales.  
  
##  <a name="step3"></a>Ejecutar y validar la solución de administración de procesos empresariales  
  
#### <a name="to-submit-a-new-order-and-validate-the-solution"></a>Para enviar un pedido nuevo y validar la solución.  
  
1.  En Internet Explorer, en el **dirección** cuadro, escriba la dirección URL para la aplicación Web de servicio al cliente como sigue:  
  
    -   `http://localhost/CSRWebApp/CSRMainForm.aspx`  
  
2.  En el **Southridge Video Customer Service Rep Order Entry Form** página, escriba un nuevo pedido en la tabla siguiente y, a continuación, haga clic en **Submit Order.**  
  
    |Entrada|Valor|  
    |-----------|-----------|  
    |Customer ID|1|  
    |Order ID|1|  
    |Sequence Number|1|  
    |Service Type Code|New Standard Service|  
  
3.  En el **Southridge Video Customer Service Rep Order Entry Form** página, el mensaje resultante como sigue:  
  
     **Id. de pedido de cliente identificador 1 1 número de secuencia 1**  
  
4.  Valide el pedido realizado en el símbolo del sistema ejecutando el sistema de suministro de cable. La aplicación muestra mensajes que informan de que el pedido enviado se ha analizado, activado y finalizado.  
  
5.  Validar que el número total de mensajes se incrementa en uno en el simulador de instalaciones.  
  
#### <a name="to-submit-a-duplicate-while-the-biztalk-server-is-processing-the-original-order"></a>Para enviar un duplicado mientras que el servidor BizTalk está procesando el pedido original  
  
1.  En Internet Explorer, en el **dirección** cuadro, escriba la dirección URL para la aplicación Web de servicio al cliente como sigue:  
  
    -   `http://localhost/CSRWebApp/CSRMainForm.aspx`  
  
2.  En el simulador de instalaciones, haga clic en **detener**. Impide que los pedidos enviados continúen procesándose.  
  
3.  En el **Southridge Video Customer Service Rep Order Entry Form** página, escriba un nuevo pedido en la tabla siguiente y, a continuación, haga clic en **Submit Order** dos veces para simular los pedidos duplicados.  
  
    |Entrada|Valor|  
    |-----------|-----------|  
    |Customer ID|2|  
    |Order ID|1|  
    |Sequence Number|1|  
    |Service Type Code|New Standard Service|  
  
4.  En el **Southridge Video Customer Service Rep Order Entry Form** página, el mensaje resultante como sigue:  
  
     **Id. de pedido de cliente Id. de 2 1 número de secuencia 1**  
  
5.  En el simulador de instalaciones, haga clic en **iniciar**. En el simulador de instalaciones haga clic en Iniciar. Se reanudarán las orquestaciones que esperan las respuestas del simulador de instalaciones. Simula que se envía un pedido duplicado mientras se está procesando el primer pedido.  
  
6.  Compruebe los pedidos realizado en el símbolo del sistema ejecutando el sistema de suministro de cable. La aplicación muestra  mensajes que informan de que sólo el primer pedido se ha analizado, activado y finalizado.  
  
7.  Compruebe el mensaje de error para los pedidos duplicados en el símbolo del sistema ejecutando el servidor de operaciones.  
  
#### <a name="to-update-an-order-while-the-biztalk-server-is-processing-the-order"></a>Para actualizar un pedido mientras que el servidor BizTalk está procesando el pedido.  
  
1.  En Internet Explorer, en el **dirección** cuadro, escriba la dirección URL para la aplicación Web de servicio al cliente como sigue:  
  
    -   `http://localhost/CSRWebApp/CSRMainForm.aspx`  
  
2.  En el simulador de instalaciones, haga clic en **detener**.  
  
3.  En el **Southridge Video Customer Service Rep Order Entry Form** página, escriba un nuevo pedido en la tabla siguiente y, a continuación, haga clic en **Submit Order**.  
  
    |Entrada|Valor|  
    |-----------|-----------|  
    |Customer ID|3|  
    |Order ID|1|  
    |Sequence Number|1|  
    |Service Type Code|New Standard Service|  
  
4.  En el **Southridge Video Customer Service Rep Order Entry Form** página, el mensaje resultante como sigue:  
  
     **Id. de pedido de cliente Id. de 3 1 número de secuencia 1**  
  
5.  En el **Southridge Video Customer Service Rep Order Entry Form** página, especifique un pedido actualizado en la tabla siguiente y, a continuación, haga clic en **Submit Order**.  
  
    |Entrada|Valor|  
    |-----------|-----------|  
    |Customer ID|3|  
    |Order ID|1|  
    |Sequence Number|2|  
    |Service Type Code|New Deluxe Service|  
  
6.  En el **Southridge Video Customer Service Rep Order Entry Form** página, el mensaje resultante como sigue:  
  
     **Id. de pedido de cliente Id. de 3 1 número de secuencia 2**  
  
7.  En el simulador de instalaciones, haga clic en **iniciar**  
  
8.  Compruebe el mensaje de resultado en el **Southridge Video Customer Service Rep Order Entry Form** página.  
  
9. Compruebe los pedidos realizado en el símbolo del sistema ejecutando el sistema de suministro de cable. La aplicación muestra mensajes que informan de que se han analizado dos pedidos, pero sólo se ha activado y finalizado el pedido actualizado.  
  
10. Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **herramientas administrativas**, haga clic en **Visor de eventos**y, a continuación, compruebe una advertencia nueva que la se interrumpió el pedido original.  
  
11. Compruebe el mensaje de error de enrutamiento en el símbolo del sistema ejecutando el servidor de operaciones.  
  
    > [!NOTE]
    >  Habrá un error en el registro de sucesos y en el servidor de operaciones. El mensaje de respuesta del sistema de instalaciones ya no corresponde a una instancia del proceso empresarial ya que finalizó por la interrupción causada por el pedido nuevo con un número de secuencia superior. Por lo tanto, el mensaje de respuesta está huérfano y se enruta al servidor de operaciones. Para obtener más información acerca de las actualizaciones de pedido, vea [a través del Administrador de procesos de flujo de orden](../core/order-flow-through-the-process-manager.md).  
  
12. Abra el mensaje más reciente de la carpeta %SystemDrive%:\BPMTest\HistoryUpdate-SP con el Bloc de notas. Comprobar **CustName**, **OrderNum**, **OrderSeqNum**, y **estado** campos para ver si el mensaje se ha creado para el pedido nuevo y la **Estado** campo es **completado**.  
  
#### <a name="to-terminate-an-order-while-the-biztalk-server-is-processing-the-order"></a>Para finalizar un pedido mientras que el servidor BizTalk está procesando el pedido  
  
1.  En Internet Explorer, en el **dirección** cuadro, escriba la dirección URL para la aplicación Web de servicio al cliente como sigue:  
  
    -   `http://localhost/CSRWebApp/CSRMainForm.aspx`  
  
2.  En el simulador de instalaciones, haga clic en **detener**.  
  
3.  En el **Southridge Video Customer Service Rep Order Entry Form** página, escriba un nuevo pedido en la tabla siguiente y, a continuación, haga clic en **Submit Order**.  
  
    |Entrada|Valor|  
    |-----------|-----------|  
    |Customer ID|4|  
    |Order ID|1|  
    |Sequence Number|1|  
    |Service Type Code|New Standard Service|  
  
4.  En el **Southridge Video Customer Service Rep Order Entry Form** página, el mensaje resultante como sigue:  
  
     **Id. de pedido de cliente Id. de 4 1 número de secuencia 1**  
  
5.  En el **Southridge Video Customer Service Rep Order Entry Form** página, haga clic en **Finalizar orden**.  
  
6.  En el **Southridge Video Customer Service Rep Order Entry Form** página, el mensaje resultante como sigue:  
  
     **Id. de pedido de cliente Id. de 4 1 número de secuencia 1**  
  
7.  En el simulador de instalaciones, haga clic en **iniciar**.  
  
8.  Compruebe los pedidos realizado en el símbolo del sistema ejecutando el sistema de suministro de cable. La aplicación muestra mensajes que informan de que el pedido sólo se ha analizado y activado.  
  
9. Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **herramientas administrativas**, haga clic en **Visor de eventos**y, a continuación, compruebe una advertencia nueva que la se finalizó el pedido por usuario.  
  
    > [!NOTE]
    >  Para obtener más información sobre cómo finalizar pedidos, vea [a través del Administrador de procesos de flujo de orden](../core/order-flow-through-the-process-manager.md).  
  
10. Compruebe el mensaje de error de enrutamiento en el símbolo del sistema ejecutando el servidor de operaciones.  
  
## <a name="see-also"></a>Vea también  
 [Antes de instalar la solución de administración de procesos empresariales](../core/before-installing-the-business-process-management-solution.md)   
 [Configuración del equipo del desarrollador para la solución de administración de procesos empresariales](../core/developer-machine-setup-for-the-business-process-management-solution.md)