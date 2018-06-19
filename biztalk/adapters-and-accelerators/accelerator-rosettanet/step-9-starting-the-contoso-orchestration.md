---
title: 'Paso 9: Iniciar la orquestación de Contoso | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, starting orchestrations
ms.assetid: df3ff90b-5a9f-4ae7-819a-11cb36d64ccd
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d58d7f2f9d725fca94eb6cf3d2412b3c376fe015
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209452"
---
# <a name="step-9-starting-the-contoso-orchestration"></a>Paso 9: Iniciar la orquestación de Contoso
En este paso completará el proceso de configuración de los puertos mediante la definición de las ubicaciones físicas de origen y de destino. Enlazar los puertos físicos a los puertos lógicos que creó en [paso 7: crear y configurar puertos](../../adapters-and-accelerators/accelerator-rosettanet/step-7-creating-and-configuring-ports.md). A continuación, dará de alta el servicio para asociar el proceso de negocio que ha diseñado en la orquestación con el entorno físico en el que se ejecutará la orquestación. Por último, iniciará la orquestación para que pueda participar en transacciones de negocio con Fabrikam.  
  
### <a name="to-bind-the-orchestration-ports"></a>Para enlazar los puertos de orquestación  
  
1.  Abra el **Explorador de BizTalk**.  
  
2.  En el Explorador de BizTalk, expanda **Base de datos de configuración de BizTalk**y **Orquestaciones**, haga clic con el botón derecho en **ContosoPriceAndAvailability.PrivateResponderProcess**y, a continuación, haga clic en **Enlazar**.  
  
3.  En la página de propiedades de enlaces de puertos, seleccione **LOB_To_PrivateResponder** en la propiedad **FromLOB** .  
  
4.  En el cuadro **ContosoSQLReqResponsePort** , seleccione **3A2SQLReqResponseSendPort**.  
  
5.  En la propiedad **ToLOB** , expanda **Puertos de envío** y seleccione **PrivateResponder_To_LOB**.  
  
6.  En la ventana de configuración en el panel izquierdo, seleccione **Host**.  
  
7.  En la propiedad **Host** , en la categoría **Host de BizTalk** , seleccione **BizTalkServerApplication** en la lista desplegable y, a continuación, haga clic en **Aceptar**.  
  
### <a name="to-start-the-biztalk-runtime-process"></a>Para iniciar el proceso de tiempo de ejecución de BizTalk  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En la consola de administración de BizTalk, en el panel izquierdo, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, Expanda **instancias de Host**.  
  
3.  Compruebe que el estado del servicio **BizTalkServerApplication** es **En ejecución**.  
  
### <a name="to-enlist-and-start-the-orchestration"></a>Para dar de alta e iniciar la orquestación  
  
1.  En el panel izquierdo de la consola de administración de BizTalk, expanda **Aplicaciones**y **Aplicación de BizTalk 1**, y haga clic en **Orquestaciones**.  
  
2.  En el panel derecho, haga clic con el botón derecho en la orquestación **ContosoPriceAndAvailability.PrivateResponderProcess** y, a continuación, haga clic en **Dar de alta**.  
  
3.  Haga clic con el botón derecho en la orquestación **ContosoPriceAndAvailability.PrivateResponderProcess** y, a continuación, haga clic en **Iniciar** para iniciar la orquestación.  
  
## <a name="see-also"></a>Vea también  
 [Creación de la solución de Fabrikam](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-fabrikam-solution.md)