---
title: 'Paso 4: Crear el puerto de recepción para aceptar mensajes de consulta ADT | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, receive ports
ms.assetid: 8bef032f-5f43-4d36-b88f-ed81f27bb803
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: acda59342c8469810a4645521c395c458fe5d73e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000757"
---
# <a name="step-4-create-the-receive-port-for-accepting-adt-query-messages"></a>Paso 4: Crear el puerto de recepción para aceptar mensajes de consulta ADT
Crear un puerto de recepción para especificar la ubicación de los mensajes entrantes de consulta enviadas por los pacientes, descarga y el sistema de transferencia (ADT). Use el procedimiento siguiente para crear el puerto de recepción para aceptar las consultas (QRY ^ Q01 mensajes) desde el sistema ADT mediante el adaptador de protocolo de nivel inferior mínimo (MLLP).  

## <a name="create-the-adtreceiveport-receive-port"></a>Crear el ADT_ReceivePort puerto de recepción  

1. Abra **administración de BizTalk Server**, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, y, a continuación, expanda **BizTalk Application 1**.  

2. Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, seleccione **puerto de recepción de solicitud-respuesta**.  

3. Para el **nombre**, escriba **ADT_ReceivePort**.  

4. Seleccione **aplicar** para enlazar el puerto y, a continuación, seleccione **ubicaciones de recepción**.  

5. Seleccione **nuevo**. 

6. Para el **nombre**, escriba **ADT_Receive**.  

7. En el **transporte** sección, seleccione **tipo**y, a continuación, seleccione **MLLP** en la lista desplegable.  

8. Seleccione **Configurar**. En **propiedades de transporte de MLLP**, configure lo siguiente y, a continuación, seleccione **Aceptar**.  


   |           Use           |                                                                                                                                                                                                     Para                                                                                                                                                                                                     |
   |------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Tiempo de reintento (s) de conexión** |                                                                 Nuevo a partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]. <br/><br/>El límite de tiempo de espera antes de intentar volver a conectar una conexión cerrada o se han quitado. Se aplica cuando **conexión iniciada por** está establecido en **Local**.<br/><br/>Valor predeterminado es 20 segundos.                                                                  |
   | **Conexión iniciada por**  | Nuevo a partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]. <br/><br/>Escriba **Local** para el MLLP ubicación de recepción para iniciar la conexión a un servidor LOB remoto. Esta es la opción nuevo.<br/><br/>Escriba **remoto** para el MLLP ubicación de recepción para continuar escuchar una conexión desde el servidor LOB remoto. Se trata de la opción predeterminada compatible.<br/><br/>El valor predeterminado es remoto. |
   |     **Nombre de conexión**      |                                                                                                                                                                                             Escriba **ADT_ReceiveMLLP**.                                                                                                                                                                                             |
   |        **Nombre de host**         |                                                                                                                                              Específicos de [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] y versiones anteriores. <br/><br/>Escriba **localhost**.                                                                                                                                               |
   |     **Nombre de Host local**      |                                                                            Nuevo a partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]. <br/><br/>Escriba el nombre DNS o dirección IP de la variable local [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]. También puede escribir **localhost**.                                                                             |
   |           **Puerto**           |                                                                                                                                                Específicos de [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] y versiones anteriores. <br/><br/>Establecido en **22000**.                                                                                                                                                |
   |        **Puerto local**        |                                                                                       Nuevo a partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]. <br/><br/>Escriba el número de puerto TCP para la conexión de host local. Solo es aplicable cuando **conexión iniciada por** es **remoto**. <br/><br/>Establecido en **22000**.                                                                                        |
   |       **Host remoto**        |                                                                                                   Nuevo a partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]. <br/><br/>Escriba el nombre DNS o dirección IP del servidor LOB remoto. Se aplica cuando **conexión iniciada por** está establecido en **Local**.                                                                                                    |
   |       **Puerto remoto**        |                                                                                      Nuevo a partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]. <br/><br/>Escriba el número de puerto TCP para la conexión del host remoto. Se aplica cuando **conexión iniciada por** está establecido en **Local**.<br/><br/>Establecido en **22000**.                                                                                       |


9. Establecer el **controlador de recepción** a **BizTalkServerApplication**.  

10. Establecer el **canalización de recepción** a **BTAHL72XPipelines.BTAHL72XReceivePipeline**.  

11. Establecer el **canalización de envío** a **PassThruTransmit**.

12. Seleccione **Aceptar** para guardar los cambios.  

13. Habilitar la ubicación de recepción que acaba de crear haciendo clic y, a continuación, seleccione **habilitar**.  

## <a name="next-step"></a>Paso siguiente  
[Paso 5: Crear el puerto de recepción para aceptar mensajes de consulta de HIS](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-receive-port-for-accepting-his-messages.md)