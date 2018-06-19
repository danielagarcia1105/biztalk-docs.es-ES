---
title: 'Paso 4: Crear un puerto de recepción para aceptar el mensaje por lotes | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a37eb334-c4ae-40d1-a433-bf0ab39c0765
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56d1aa54639263e6741c6df89c3888b9b4120515
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207612"
---
# <a name="step-4-create-a-receive-port-for-accepting-the-batch-message"></a>Paso 4: Crear un puerto de recepción para aceptar el mensaje de lote
En este paso, se creará y configurará un puerto para recibir el lote entrante.  
  
 Crear una solicitud-respuesta (bidireccional) puerto de recepción, dado que el escenario incluye la generación de aplicaciones de aceptación de confirmaciones para los mensajes individuales del lote. En el modo bidireccional, el adaptador de recepción MLLP no aceptará un nuevo mensaje entrante hasta que la canalización de recepción ha generado la confirmación (ACK) para el mensaje anterior.  
  
## <a name="create-the-receive-port-for-accepting-the-batch-message"></a>Crear el puerto de recepción para aceptar el mensaje de lote  
  
1.  Abra **administración de BizTalk Server**, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, y, a continuación, expanda **BizTalk Application 1**.  
  
    > [!NOTE]
    >  La consola de administración de BizTalk Server también puede abrir desde dentro de Visual Studio, haga clic en **administración de BizTalk Server** en el **herramientas** menú.  
  
2.  Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, seleccione **puerto de recepción de solicitud-respuesta**.  

3.  Para el **nombre**, escriba **Tutorial_2WayReceive**.  

4.  Seleccione **aplicar** para enlazar el puerto y, a continuación, seleccione **ubicaciones de recepción**.  
  
5.  Seleccione **nueva**.  

6.  Para el **nombre**, escriba **Tutorial_2WayReceive**.

7. En el **transporte** sección, seleccione **tipo**y, a continuación, seleccione **MLLP** en la lista desplegable.  
  
8. Seleccione **Configurar**. En **propiedades de transporte de MLLP**, configure lo siguiente y, a continuación, seleccione **Aceptar**.  

    |Use|Para|  
    |---|---|  
    |**Tiempo de reintento (s) de conexión**|Nuevo a partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]. <br/><br/>El límite de tiempo de espera antes de intentar volver a conectar una conexión cerrada o se han quitado. Se aplica cuando **conexión iniciada por** está establecido en **Local**.<br/><br/>Valor predeterminado es 20 segundos.|
    |**Conexión iniciada por**| Nuevo a partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]. <br/><br/>Escriba **Local** para el MLLP ubicación de recepción para iniciar la conexión a un servidor remoto de LOB. Esta es la opción nuevo.<br/><br/>Escriba **remoto** para el MLLP ubicación de recepción para continuar realizar escuchas de una conexión desde el servidor remoto de LOB. Esta es la opción predeterminada sea compatible.<br/><br/>Valor predeterminado es remoto.| 
    |**Nombre de conexión**|Escriba **2 vías**.|  
    |**Nombre de host**|Específicos de [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] y versiones anteriores. <br/><br/>Escriba **localhost**.|  
    |**Nombre de Host local**|Nuevo a partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]. <br/><br/>Escriba el nombre DNS o dirección IP de la variable local [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]. También puede especificar **localhost**.|  
    |**Puerto**|Específicos de [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] y versiones anteriores. <br/><br/>Establecido en **21000**.|  
    |**Puerto local**|Nuevo a partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]. <br/><br/>Escriba el número de puerto TCP para la conexión de host local. Solo es aplicable cuando **conexión iniciada por** es **remoto**. <br/><br/>Establecido en **21000**.|
    |**Host remoto**|Nuevo a partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]. <br/><br/>Escriba el nombre DNS o dirección IP del servidor remoto de LOB. Se aplica cuando **conexión iniciada por** está establecido en **Local**.|  
    |**Puerto remoto**|Nuevo a partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]. <br/><br/>Escriba el número de puerto TCP para la conexión a host remoto. Se aplica cuando **conexión iniciada por** está establecido en **Local**.<br/><br/>Establecido en **21000**.|  

9. En las propiedades de ubicación de recepción, seleccione lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Controlador de recepción**|Seleccione **BizTalkServerApplication** en la lista desplegable|  
    |**La canalización de recepción**|Seleccione **BTAHL72XPipelines.BTAHL72XReceivePipeline**|  
    |**Canalización de envío**|Seleccione **BTAHL72XPipelines.BTAHL72XSendPipeline**|  

11. Seleccione **Aceptar** para guardar los cambios.  
  
12. Habilitar la ubicación de recepción que acaba de crear haciendo clic en él y, a continuación, seleccione **habilitar**.  
  
## <a name="next-step"></a>Paso siguiente
[Paso 5: Crear un puerto de envío para la entrega de mensajes](../../adapters-and-accelerators/accelerator-hl7/step-5-create-a-send-port-to-deliver-messages.md)