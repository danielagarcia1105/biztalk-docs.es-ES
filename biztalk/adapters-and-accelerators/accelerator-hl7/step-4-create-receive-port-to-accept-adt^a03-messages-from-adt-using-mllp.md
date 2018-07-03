---
title: 'Paso 4: Crear el puerto de recepción para aceptar ADT ^ A03 mensajes desde sistemas ADT mediante el adaptador MLLP | Microsoft Docs'
ms.custom: ''
ms.date: 2015-12-09
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive ports
- end-to-end tutorial, receive ports
- creating, receive ports
ms.assetid: 3c4192d5-d011-48b0-a3f9-47c5225780ee
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1571d0f506f052aac08735d426fdbb4dcaf4b647
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000157"
---
# <a name="step-4-create-the-receive-port-for-accepting-adta03-messages-from-adt-systems-using-the-mllp-adapter"></a>Paso 4: Crear el puerto de recepción para aceptar ADT ^ A03 mensajes desde sistemas ADT mediante el adaptador de MLLP
Utilice el puerto de recepción para especificar la ubicación de recepción para los mensajes entrantes. Use el procedimiento siguiente para crear el puerto de recepción para aceptar ADT ^ A03 mensajes desde el sistema de ADT mediante el adaptador de MLLP.  

## <a name="create-the-receive-port"></a>Crear el puerto de recepción  

1. Abra **administración de BizTalk Server**, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**, y, a continuación, expanda **BizTalk Application 1**.  

   > [!NOTE]
   >  La consola de administración de BizTalk Server también se puede abrir desde dentro de Visual Studio, haga clic en **administración de BizTalk Server** en el **herramientas** menú.  

2. Haga clic en **puertos de recepción**, seleccione **New**y, a continuación, seleccione **puerto de recepción unidireccional**.  

3. Para el **nombre**, escriba **Tutorial_1WayReceive**.  

4. Seleccione **aplicar** para enlazar el puerto y, a continuación, seleccione **ubicaciones de recepción**.  

5. Seleccione **nuevo**.  

6. Para el **nombre**, escriba **Tutorial_MLLPReceive**.  

7. En el **transporte** sección, seleccione **tipo**y, a continuación, seleccione **MLLP** en la lista desplegable.  

8. Seleccione **Configurar**. En **propiedades de transporte de MLLP**, configure lo siguiente y, a continuación, seleccione **Aceptar**.  


   |           Use           |                                                                                                                                                                                                     Para                                                                                                                                                                                                     |
   |------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Tiempo de reintento (s) de conexión** |                                                                 Nuevo a partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]. <br/><br/>El límite de tiempo de espera antes de intentar volver a conectar una conexión cerrada o se han quitado. Se aplica cuando **conexión iniciada por** está establecido en **Local**.<br/><br/>Valor predeterminado es 20 segundos.                                                                  |
   | **Conexión iniciada por**  | Nuevo a partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]. <br/><br/>Escriba **Local** para el MLLP ubicación de recepción para iniciar la conexión a un servidor LOB remoto. Esta es la opción nuevo.<br/><br/>Escriba **remoto** para el MLLP ubicación de recepción para continuar escuchar una conexión desde el servidor LOB remoto. Se trata de la opción predeterminada compatible.<br/><br/>El valor predeterminado es remoto. |
   |     **Nombre de conexión**      |                                                                                                                                                                                                  Escriba **1Way**.                                                                                                                                                                                                   |
   |        **Nombre de host**         |                                                                                                                                              Específicos de [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] y versiones anteriores. <br/><br/>Escriba **localhost**.                                                                                                                                               |
   |     **Nombre de Host local**      |                                                                            Nuevo a partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]. <br/><br/>Escriba el nombre DNS o dirección IP de la variable local [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]. También puede escribir **localhost**.                                                                             |
   |           **Puerto**           |                                                                                                                                              Específicos de [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)] y versiones anteriores. <br/><br/>El valor predeterminado es **11000**.                                                                                                                                              |
   |        **Puerto local**        |                                                                                     Nuevo a partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]. <br/><br/>Escriba el número de puerto TCP para la conexión de host local. Solo es aplicable cuando **conexión iniciada por** es **remoto**. <br/><br/>El valor predeterminado es **11000**.                                                                                      |
   |       **Host remoto**        |                                                                                                   Nuevo a partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]. <br/><br/>Escriba el nombre DNS o dirección IP del servidor LOB remoto. Se aplica cuando **conexión iniciada por** está establecido en **Local**.                                                                                                    |
   |       **Puerto remoto**        |                                                                                                    Nuevo a partir de [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]. <br/><br/>Escriba el número de puerto TCP para la conexión del host remoto. Se aplica cuando **conexión iniciada por** está establecido en **Local**.                                                                                                    |


9. Establecer el **controlador de recepción** a **BizTalkServerApplication**.  

10. Establecer el **canalización de recepción** a **BTAHL72XPipelines.BTAHL72XReceivePipeline**.  

11. Seleccione **Aceptar** para guardar los cambios.  

12. Habilitar la ubicación de recepción que acaba de crear haciendo clic y, a continuación, seleccione **habilitar**.  

## <a name="next-step"></a>Paso siguiente  
[Paso 5: Crear un puerto de envío para entregar confirmaciones al sistema ADT mediante el adaptador de archivo](../../adapters-and-accelerators/accelerator-hl7/step-5-create-send-port-to-deliver-acknowledgments-to-adt-system-using-file.md)