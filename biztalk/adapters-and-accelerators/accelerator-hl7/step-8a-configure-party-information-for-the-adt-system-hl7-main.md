---
title: 'Paso 8A: configurar la información de entidad para el System_hl7_main ADT | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 693fda8b-9a99-4a6e-89b7-294f84676350
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f407f549404744d76eccdfe1af47f12cbb64ef82
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971165"
---
# <a name="step-8a-configure-party-information-for-the-adt-systemhl7main"></a>Paso 8A: configurar la información de entidad para el System_hl7_main ADT
En este paso, configure la información de entidad para el sistema de ADT.  
  
### <a name="to-configure-the-adt-system-party-information"></a>Para configurar la información de entidad del sistema de ADT  
  
1. En la consola de administración de BizTalk, expanda **administración de BizTalk Server**y, a continuación, expanda **grupo de BizTalk**. Haga clic en **partes**, apunte a **New**y, a continuación, haga clic en **entidad**.  
  
2. En el cuadro de diálogo Propiedades de entidad en el **nombre** , escriba **ADT**. (El valor que escriba en este cuadro debe coincidir con la instancia de mensaje original de HL7, QRY^Q01.txt MSH3.)  
  
3. En el árbol de consola, haga clic en **puertos de envío**.  
  
4. En el **puerto de envío** panel, para **nombre** en la primera fila, seleccione **ADT_Send**y, a continuación, haga clic en **Aceptar**.  
  
5. Haga clic en **iniciar**, apunte a **programas**, apunte a **Microsoft BizTalk \<versión\> Acelerador para HL7**y, a continuación, haga clic en  **BTAHL7 Explorador de configuración**.  
  
6. En el Explorador de configuración de BTAHL7, haga clic en el **confirmación** ficha. Para **tipo de confirmación**, seleccione **EnhancedMode**.  
  
7. En las propiedades de confirmación en el panel de mensajes de Inboiund, para **MSH15 - acepte el tipo de confirmación**, seleccione **AL**.  
  
8. En el panel de propiedades de confirmación para **MSH16 - tipo de confirmación de la aplicación**, seleccione **NE**.  
  
9. Haga clic en **guardar**y, a continuación, cierre el Explorador de configuración de BTAHL7.  
  
   Continúe con [paso 8B: configurar la información de entidad para el sistema de HI](../../adapters-and-accelerators/accelerator-hl7/step-8b-configure-party-information-for-the-hi-system.md).