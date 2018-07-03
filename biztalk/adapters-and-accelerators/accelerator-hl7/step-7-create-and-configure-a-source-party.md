---
title: 'Paso 7: Crear y configurar una entidad de origen | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d8788a9c-ae6f-461b-82e5-f4276d1d5e0c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4708a682047ced4fa33ae34781fd88d379c5e70b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968933"
---
# <a name="step-7-create-and-configure-a-source-party"></a>Paso 7: Crear y configurar una entidad de origen
En este paso, crear y configurar una entidad de origen y asignar los puertos de envío para que las transformaciones de encabezado de mensaje para el mensaje saliente.  
  
### <a name="to-create-and-configure-a-source-party"></a>Para crear y configurar una entidad de origen  
  
1. En la consola de administración de BizTalk, haga clic en **partes**, apunte a **New**y, a continuación, haga clic en **entidad**.  
  
2. En el **las propiedades de entidad** cuadro de diálogo, en el campo nombre, tipo **Tutorial_BatchSource**.  
  
   > [!NOTE]
   >  El valor que escriba en este cuadro es de FHS3.1 del original [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] mensaje por lotes, FragmentedInboundBatch.txt.  
  
3. En el árbol de consola, haga clic en **puertos de envío**.  
  
4. En el panel puertos de envío, para el campo nombre, seleccione **Tutorial_2wayAck**.  
  
5. Haga clic en **Aceptar**.  
  
6. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft BizTalk \<versión\> Acelerador para HL7**y, a continuación, haga clic en **Explorador de configuración de BTAHL7**.  
  
7. En el Explorador de configuración de BTAHL7, en el **partes** , haga clic **Tutorial_BatchSource**.  
  
8. Seleccione el **definición de lote** pestaña del explorador de configuración de BTAHL7. Seleccione **Sí** para **requerida fragmentación**y, a continuación, haga clic en **guardar**.  
  
9. Seleccione el **confirmación** ficha. Para **tipo de confirmación**, seleccione **OriginalMode**y, a continuación, haga clic en **guardar**.  
  
   Continúe con [paso 8: reiniciar BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-8-restart-biztalk-server.md).