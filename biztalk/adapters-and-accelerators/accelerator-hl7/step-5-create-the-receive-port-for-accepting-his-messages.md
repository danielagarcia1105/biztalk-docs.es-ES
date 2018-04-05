---
title: 'Paso 5: Crear el puerto de recepción para aceptar los mensajes | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, receive ports
ms.assetid: c0b311d8-541c-4c21-a514-c93092c36fe2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0df326e3b08438f7a1eb7d3a2df3c5a816e79bc7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-5-create-the-receive-port-for-accepting-his-messages"></a>Paso 5: Crear el puerto de recepción para aceptar los mensajes
En este paso creará un puerto de recepción para especificar la ubicación para los mensajes entrantes enviados por el sistema de información de Hospital (HIS). Utilice el procedimiento siguiente para crear el puerto de recepción para aceptar mensajes de respuesta de consulta desde el sistema ADT mediante el adaptador de protocolo de nivel inferior mínimo (MLLP).  
  
## <a name="create-the-hisreceiveport-receive-port"></a>Crear el HIS_ReceivePort puerto de recepción  

1.  Abra **administración de BizTalk Server**, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, y, a continuación, expanda **BizTalk Application 1**.  
  
2.  Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, seleccione **puerto de recepción unidireccional**.   
  
3.  Para el **nombre**, escriba **HIS_ReceivePort**.  

4.  Seleccione **aplicar** para enlazar el puerto y, a continuación, seleccione **ubicaciones de recepción**.  
  
5.  Seleccione **nueva**.  
  
6.  Para el **nombre**, escriba **HIS_Receive**.  

7. En el **transporte** sección, seleccione **tipo**y, a continuación, seleccione **MLLP** en la lista desplegable.  
  
8. Seleccione **Configurar**. En **propiedades de transporte de MLLP**, configure lo siguiente y, a continuación, seleccione **Aceptar**.  

    |Use|Para|  
    |---|---|  
    |**Tiempo de reintento (s) de conexión**|Nuevo a partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]. <br/><br/>El límite de tiempo de espera antes de intentar volver a conectar una conexión cerrada o se han quitado. Se aplica cuando **conexión iniciada por** está establecido en **Local**.<br/><br/>Valor predeterminado es 20 segundos.|
    |**Conexión iniciada por**| Nuevo a partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]. <br/><br/>Escriba **Local** para el MLLP ubicación de recepción para iniciar la conexión a un servidor remoto de LOB. Esta es la opción nuevo.<br/><br/>Escriba **remoto** para el MLLP ubicación de recepción para continuar realizar escuchas de una conexión desde el servidor remoto de LOB. Esta es la opción predeterminada sea compatible.<br/><br/>Valor predeterminado es remoto.| 
    |**Nombre de conexión**|Escriba **HIS_ReceiveMLLP**.|  
    |**Nombre de host**|Específicos de [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] y versiones anteriores. <br/><br/>Escriba **localhost**.|  
    |**Nombre de Host local**|Nuevo a partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]. <br/><br/>Escriba el nombre DNS o dirección IP de la variable local [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]. También puede especificar **localhost**.|  
    |**Puerto**|Específicos de [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] y versiones anteriores. <br/><br/>Establecido en **23000**.|  
    |**Puerto local**|Nuevo a partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]. <br/><br/>Escriba el número de puerto TCP para la conexión de host local. Solo es aplicable cuando **conexión iniciada por** es **remoto**. <br/><br/>Establecido en **23000**.|
    |**Host remoto**|Nuevo a partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]. <br/><br/>Escriba el nombre DNS o dirección IP del servidor remoto de LOB. Se aplica cuando **conexión iniciada por** está establecido en **Local**.|  
    |**Puerto remoto**|Nuevo a partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]. <br/><br/>Escriba el número de puerto TCP para la conexión a host remoto. Se aplica cuando **conexión iniciada por** está establecido en **Local**.<br/><br/>Establecido en **23000**.|  
    
9. Establecer el **controlador de recepción** a **BizTalkServerApplication**.  
  
10. Establecer el **canalización de recepción** a **BTAHL72XPipelines.BTAHL72XReceivePipeline**.  
  
11. Seleccione **Aceptar** para guardar los cambios.  
  
12. Habilitar la ubicación de recepción que acaba de crear haciendo clic en él y, a continuación, seleccione **habilitar**.  

## <a name="next-step"></a>Paso siguiente  
[Paso 6: Crear un puerto de envío para entregar los mensajes de consulta](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-query-messages.md)