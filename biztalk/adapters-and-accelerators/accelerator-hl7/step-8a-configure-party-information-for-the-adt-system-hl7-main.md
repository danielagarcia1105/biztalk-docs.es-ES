---
title: "Paso 8: configurar la información de entidad para el System_hl7_main ADT | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 693fda8b-9a99-4a6e-89b7-294f84676350
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9683fd02f94b96ead6817c72298338c064a14cc1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-8a-configure-party-information-for-the-adt-systemhl7main"></a>Paso 8: configurar la información de entidad para el System_hl7_main ADT
En este paso, configurará la información de entidad para el sistema ADT.  
  
### <a name="to-configure-the-adt-system-party-information"></a>Para configurar la información de entidad del sistema ADT  
  
1.  En la consola de administración de BizTalk, expanda **administración de BizTalk Server**y, a continuación, expanda **grupo de BizTalk**. Haga clic en **partes**, seleccione **New**y, a continuación, haga clic en **entidad**.  
  
2.  En el cuadro de diálogo Propiedades de la entidad, en la **nombre** , escriba **ADT**. (El valor que escriba en este cuadro debe coincidir con la instancia original del mensaje HL7, QRY^Q01.txt MSH3.)  
  
3.  En el árbol de consola, haga clic en **puertos de envío**.  
  
4.  En el **puerto de envío** panel, para **nombre** en la primera fila, seleccione **ADT_Send**y, a continuación, haga clic en **Aceptar**.  
  
5.  Haga clic en **iniciar**, seleccione **programas**, seleccione **Microsoft BizTalk \<versión\> Acelerador para HL7**y, a continuación, haga clic en  **BTAHL7 Explorador de configuración**.  
  
6.  En el Explorador de configuración de BTAHL7, haga clic en el **confirmación** ficha. Para **tipo de confirmación**, seleccione **EnhancedMode**.  
  
7.  En las propiedades de confirmación en el panel de mensajes de Inboiund, para **MSH15 - tipo de confirmación que acepte**, seleccione **AL**.  
  
8.  En el panel de propiedades de confirmación, para **MSH16 - tipo de confirmación de la aplicación**, seleccione **NE**.  
  
9. Haga clic en **guardar**y, a continuación, cierre el Explorador de configuración de BTAHL7.  
  
 Continúe con [paso 8B: configurar la información de entidad para el sistema de HI](../../adapters-and-accelerators/accelerator-hl7/step-8b-configure-party-information-for-the-hi-system.md).