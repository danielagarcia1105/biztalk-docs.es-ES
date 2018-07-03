---
title: 'Paso 4: Crear un puerto de recepción para aceptar el mensaje por lotes | Microsoft Docs'
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
ms.openlocfilehash: 9a0d2f6f36ee34f93e8a5069aadc1958837af00c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966813"
---
# <a name="step-4-create-a-receive-port-for-accepting-the-batch-message"></a>Paso 4: Crear un puerto de recepción para aceptar el mensaje de lote
En este paso, crear y configurar un puerto para recibir el lote entrante.  

 Crear una solicitud-respuesta (bidireccional) puerto de recepción, debido a que el escenario incluye la generación de aplicaciones-acepte las confirmaciones de los mensajes individuales del lote. En el modo bidireccional, el adaptador de recepción MLLP no aceptará un nuevo mensaje entrante hasta que la canalización de recepción ha generado la confirmación (ACK) para el mensaje anterior.  

## <a name="create-the-receive-port-for-accepting-the-batch-message"></a>Crear el puerto de recepción para aceptar el mensaje de lote  

1. Abra **administración de BizTalk Server**, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, y, a continuación, expanda **BizTalk Application 1**.  

   > [!NOTE]
   >  La consola de administración de BizTalk Server también se puede abrir desde dentro de Visual Studio, haga clic en **administración de BizTalk Server** en el **herramientas** menú.  

2. Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, seleccione **puerto de recepción de solicitud-respuesta**.  

3. Para el **nombre**, escriba **Tutorial_2WayReceive**.  

4. Seleccione **aplicar** para enlazar el puerto y, a continuación, seleccione **ubicaciones de recepción**.  

5. Seleccione **nuevo**.  

6. Para el **nombre**, escriba **Tutorial_2WayReceive**.

7. En el **transporte** sección, seleccione **tipo**y, a continuación, seleccione **MLLP** en la lista desplegable.  

8. Seleccione **Configurar**. En **propiedades de transporte de MLLP**, configure lo siguiente y, a continuación, seleccione **Aceptar**.  


   |           Use           |                                                                                                                                                                                                     Para                                                                                                                                                                                                     |
   |------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Tiempo de reintento (s) de conexión** |                                                                 Nuevo a partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]. <br/><br/>El límite de tiempo de espera antes de intentar volver a conectar una conexión cerrada o se han quitado. Se aplica cuando **conexión iniciada por** está establecido en **Local**.<br/><br/>Valor predeterminado es 20 segundos.                                                                  |
   | **Conexión iniciada por**  | Nuevo a partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]. <br/><br/>Escriba **Local** para el MLLP ubicación de recepción para iniciar la conexión a un servidor LOB remoto. Esta es la opción nuevo.<br/><br/>Escriba **remoto** para el MLLP ubicación de recepción para continuar escuchar una conexión desde el servidor LOB remoto. Se trata de la opción predeterminada compatible.<br/><br/>El valor predeterminado es remoto. |
   |     **Nombre de conexión**      |                                                                                                                                                                                                  Escriba **2 vías**.                                                                                                                                                                                                   |
   |        **Nombre de host**         |                                                                                                                                              Específicos de [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] y versiones anteriores. <br/><br/>Escriba **localhost**.                                                                                                                                               |
   |     **Nombre de Host local**      |                                                                            Nuevo a partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]. <br/><br/>Escriba el nombre DNS o dirección IP de la variable local [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]. También puede escribir **localhost**.                                                                             |
   |           **Puerto**           |                                                                                                                                                Específicos de [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] y versiones anteriores. <br/><br/>Establecido en **21000**.                                                                                                                                                |
   |        **Puerto local**        |                                                                                       Nuevo a partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]. <br/><br/>Escriba el número de puerto TCP para la conexión de host local. Solo es aplicable cuando **conexión iniciada por** es **remoto**. <br/><br/>Establecido en **21000**.                                                                                        |
   |       **Host remoto**        |                                                                                                   Nuevo a partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]. <br/><br/>Escriba el nombre DNS o dirección IP del servidor LOB remoto. Se aplica cuando **conexión iniciada por** está establecido en **Local**.                                                                                                    |
   |       **Puerto remoto**        |                                                                                      Nuevo a partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]. <br/><br/>Escriba el número de puerto TCP para la conexión del host remoto. Se aplica cuando **conexión iniciada por** está establecido en **Local**.<br/><br/>Establecido en **21000**.                                                                                       |


9. En las propiedades de ubicación de recepción, seleccione lo siguiente:  


   |       Use       |                         Para                          |
   |----------------------|-------------------------------------------------------------|
   | **Controlador de recepción**  | Seleccione **BizTalkServerApplication** en la lista desplegable |
   | **Canalización de recepción** |    Seleccione **BTAHL72XPipelines.BTAHL72XReceivePipeline**     |
   |  **Canalización de envío**   |      Seleccione **BTAHL72XPipelines.BTAHL72XSendPipeline**      |


10. Seleccione **Aceptar** para guardar los cambios.  

11. Habilitar la ubicación de recepción que acaba de crear haciendo clic y, a continuación, seleccione **habilitar**.  

## <a name="next-step"></a>Paso siguiente
[Paso 5: Crear un puerto de envío para entregar mensajes](../../adapters-and-accelerators/accelerator-hl7/step-5-create-a-send-port-to-deliver-messages.md)