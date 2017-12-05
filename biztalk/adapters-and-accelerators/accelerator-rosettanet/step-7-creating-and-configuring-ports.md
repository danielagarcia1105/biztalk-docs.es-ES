---
title: 'Paso 7: Crear y configurar puertos | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating ports
- private process tutorial, configuring ports
ms.assetid: c00344c6-506a-4560-a948-e5fed2b9fd58
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44a9696f907928f31a740e4d8545567921a82df9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-7-creating-and-configuring-ports"></a>Paso 7: Crear y configurar puertos
En este paso, se creará y configurará los puertos que se usan para comunicarse con los procesos empresariales. Cada puerto tiene un tipo, la dirección y la propiedad de enlace. Estas propiedades establecen la dirección y el patrón de comunicación, la ubicación de donde se envía o recibe el mensaje y cómo se produce la comunicación.  
  
### <a name="to-create-a-logical-send-port"></a>Para crear un puerto de envío lógico  
  
1.  En Visual Studio, en el cuadro de herramientas, arrastre el **puerto** dar forma a la superficie de diseño de orquestación y colóquela en la **superficie para el puerto** para abrir el **Asistente de configuración de puerto**.  
  
2.  En el **Asistente para configuración de puertos** página, haga clic en **siguiente**.  
  
3.  En el **propiedades de puerto** página, en la **nombre** , escriba **ContosoSQLReqResponsePort**y, a continuación, haga clic en **siguiente**.  
  
4.  En el **seleccionar un tipo de puerto** página, en la **nombre de tipo de puerto** , escriba **ContosoSQLReqResponsePortName**.  
  
5.  Para **patrón de comunicación**, seleccione **solicitud-respuesta**.  
  
6.  Para **restricciones de acceso**, seleccione **interno: limitado a este proyecto**y, a continuación, haga clic en **siguiente**.  
  
7.  En el **enlace de puerto** página, seleccione **enviaré una solicitud y recibiré una respuesta**, deje el **enlace de puerto** opción establecida en **especificar más tarde**y, a continuación, haga clic en **siguiente**.  
  
8.  Haga clic en **finalizar** para crear el puerto.  
  
### <a name="to-change-the-variable-type-for-the-orchestration-ports"></a>Para cambiar el tipo de variable para los puertos de orquestación  
  
1.  En la Vista orquestación, expanda **tipos**, expanda **tipos de puerto**, expanda **ContosoSQLReqResponsePortName**, expanda **Operation_1**, y, a continuación, seleccione **solicitar**.  
  
2.  En la ventana Propiedades, seleccione la **tipo de mensaje** propiedad, expanda **esquemas** y, a continuación, haga clic en  **\<seleccionar del ensamblado mencionado\>**  .  
  
3.  En el cuadro de diálogo Seleccionar tipo de artefacto, haga clic en **ContosoPriceAndAvailability**.  
  
4.  En el panel derecho, seleccione **rootPriceRequest**y, a continuación, haga clic en **Aceptar**.  
  
5.  En la Vista orquestación, en **Operation_1**, seleccione **respuesta** para el **ContosoSQLReqResponsePortName** tipo de puerto.  
  
6.  En la ventana Propiedades, seleccione la **tipo de mensaje** propiedad, expanda **esquemas** y, a continuación, haga clic en \< **seleccionar del ensamblado mencionado\>**  .  
  
7.  En el **Seleccionar tipo de artefacto** cuadro de diálogo, haga clic en **ContosoPriceAndAvailability**.  
  
8.  En el panel derecho, seleccione **rootPriceResponse**y, a continuación, haga clic en **Aceptar**.  
  
### <a name="to-connect-the-ports-to-the-receive-shapes"></a>Para conectar los puertos a las formas de recepción  
  
1.  En la superficie de diseño de orquestación, seleccione la **Send_1** forma.  
  
2.  En la ventana Propiedades, seleccione la **mensaje** propiedad y, a continuación, seleccione **Contoso3A2RequestMessage** en la lista desplegable.  
  
3.  Conectar el **ContosoSQLReqResponsePort** seleccionando el indicador verde junto a la **solicitar** etiqueta y arrastrándolo hasta el indicador verde de la **Send_1** forma.  
  
4.  En la superficie de diseño de orquestación, seleccione la **Receive_1** forma.  
  
5.  En la ventana Propiedades, seleccione la **mensaje** propiedad y, a continuación, seleccione **Contoso3A2ResponseMessage** en la lista desplegable.  
  
6.  Conectar el **ContosoSQLReqResponsePort** seleccionando el indicador verde junto a la **respuesta** etiqueta y arrastrándolo hasta el indicador verde de la **Receive_1** forma.  
  
7.  En el **archivo** menú, haga clic en **guardar todo**.  
  
## <a name="see-also"></a>Vea también  
 [Paso 8: Creación e implementación de la orquestación de Contoso](../../adapters-and-accelerators/accelerator-rosettanet/step-8-building-and-deploying-the-contoso-orchestration.md)