---
title: 'Paso 15: Configurar el envío y puertos de recepción | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, ports
ms.assetid: d532b196-473e-4c8f-b4ed-acef674fc698
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 020d83db1db86f9ff9ce116578cf58f19ba08241
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206460"
---
# <a name="step-15-configure-the-send-and-receive-ports"></a>Paso 15: Configurar el envío y puertos de recepción
En los pasos anteriores, creó un envío lógico y puerto de recepción mediante el Diseñador de orquestaciones y establece el enlace de puerto para "Especificar más tarde". En este paso, use el Explorador de BizTalk para finalizar la configuración del puerto definiendo las ubicaciones físicas de origen y de destino y enlazar los puertos físicos a los puertos lógicos que creó en la orquestación.  
  
## <a name="configure-the-send-and-receive-ports"></a>Configurar el envío y puertos de recepción  
  
1.  En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda **Aplicación de BizTalk 1**.  
  
2.  Haga clic en **puertos de envío**, elija Nuevo y, a continuación, haga clic en **puerto de envío unidireccional estático**.  
  
3.  En el cuadro de diálogo Propiedades de puerto de envío, en la **nombre** , escriba **MLLPSendPort**.  
  
4.  Para **tipo**, seleccione **MLLP**.  
  
5.  Haga clic en el **configurar** situado a la derecha de la **tipo** campo.  
  
6.  En el cuadro de diálogo Propiedades de transporte de MLLP para **nombre de la conexión** escriba **MLLPConnection**. Para **Host** escriba **localhost**. Haga clic en **Aceptar**.  
  
7.  En el cuadro de diálogo Propiedades de puerto de envío, para **canalización de envío**, seleccione **BTAHL72XPipelines.BTAHL72XSendPipeline**y, a continuación, haga clic en **Aceptar**.  
  
8.  En la consola de administración, haga clic en **MLLPSendPort** de puerto y, a continuación, haga clic en **iniciar**.  
  
9. Expanda **configuración de plataforma**, haga clic en **instancias de Host**, haga clic en **BizTalkServerApplication**y, a continuación, haga clic en **iniciar**. Si ya se está ejecutando el host, haga clic en **reiniciar**.  
  
10. Haga clic en **orquestaciones**, haga clic en **BTAHL7_Project.Doorbell_Orchestration**y, a continuación, haga clic en **propiedades**.  
  
11. En el cuadro de diálogo Propiedades de orquestación, en el árbol de consola, haga clic en **enlaces**.  
  
12. En el **enlaces** panel, para **Host**, seleccione **BizTalkServerApplication**.  
  
13. Para **SOAPReceivePort**, seleccione **WebPort_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort** en el **puertos de recepción** columna.  
  
14. Para **MLLPSendPort**, seleccione **MLLPSendPort** en el **grupos de puertos de envío y puertos de envío** columna.  
  
15. Haga clic en **Aceptar** para guardar los cambios.  
  
## <a name="msh-5-and-msh-6"></a>MSH 5 y 6 de MSH  
 Los campos de encabezado de MSH 5 y 6 de MSH contienen la aplicación de destino y la utilidad, respectivamente. En el Explorador de configuración, puede especificar los valores para cada uno de los tres componentes de MSH 5 y 6 de MSH, en casos si desea que la información de destino en el mensaje va a cambiar. Este es un escenario probable cuando el mensaje original no incluye información específica de la entidad. Este paso es aplicable en el modelo declarativo (publicador y suscriptor). Realice este paso si es aplicable en su entorno. Para obtener más información acerca de cómo establecer estos valores, consulte [partes - Explorador de configuración de BTAHL7](parties-tab.md).  
  
 Continúe con [paso 16: iniciar la orquestación](../../adapters-and-accelerators/accelerator-hl7/step-16-start-the-orchestration.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial de enriquecimiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)