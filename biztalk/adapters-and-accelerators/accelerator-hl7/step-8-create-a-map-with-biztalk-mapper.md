---
title: 'Paso 8: Crear un mapa con el asignador de BizTalk | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, maps
- creating, maps
- maps, creating
- BizTalk Mapper
ms.assetid: 785426c7-5651-48be-b3f4-7f9d8051ba23
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1b9edeca21fe9967f816f05d2ceb12ffe5c5ded
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968461"
---
# <a name="step-8-create-a-map-with-biztalk-mapper"></a>Paso 8: Crear un mapa con el asignador de BizTalk
En este paso, usará al asignador de BizTalk para crear un mapa. Utilice este mapa para crear vínculos que asociación los datos (campos) en un documento de solicitud de reposición a los datos en una solicitud denegada documento.  
  
### <a name="to-create-a-map"></a>Para crear un mapa  
  
1. En el Explorador de soluciones, haga clic en **BTAHL7 proyecto**, apunte a **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
2. En el **Agregar nuevo elemento** cuadro de diálogo el **categorías** panel, haga clic en **archivos de asignación**.  
  
3. En el **nombre** , escriba **DoorbellMap** para nombrar el mapa y, a continuación, haga clic en **agregar** para iniciar el asignador de BizTalk.  
  
4. En el **esquema de origen** panel (izquierda), haga clic en **Abrir esquema de origen**.  
  
5. En el cuadro de diálogo Selector de tipos de BizTalk, expanda **BTAHL7 proyecto**, expanda **esquemas**, haga clic en **BTAHL7_Project.Doorbell**y, a continuación, haga clic en **Aceptar**.  
  
6. En el **esquema de destino** panel (derecha), haga clic en **Abrir esquema de destino**.  
  
7. En el selector de tipos de BizTalk, expanda **BTAHL7 proyecto**, expanda **esquemas**, haga clic en **BTAHL7Schemas.ADT_A04_22_GLO_DEF**y, a continuación, haga clic en **Aceptar**.  
  
8. En el **esquema de destino** panel (derecha), expanda **ADT_A04_22_GLO_DEF**, expanda **PID_PatientIdentification**y expanda **PID.5_PatientName** .  
  
9. En el **esquema de origen** panel (izquierda), expanda **DoorbellRoot**. Arrastre el **LastName** campo el **PN_0_FamilyName** campo el **esquema de destino** panel.  
  
10. En el **esquema de origen** panel, arrastre el **FirstName** campo el **PN_1_GivenName** campo el **esquema de destino** panel.  
  
11. En el **esquema de origen** panel, arrastre el **MiddleName** campo el **PN_2_MiddleInitialOrName** campo el **esquema de destino** panel .  
  
12. En el **esquema de destino** panel, expanda **PID_3_PatientIdInternalId**.  
  
13. En el **esquema de origen** panel, arrastre el **SSN** campo el **CM_PAT_ID_0_PatientID** en el **esquema de destino** panel.  
  
14. En el **archivo** menú, haga clic en **guardar todo**.  
  
    En un escenario de enriquecimiento típico de mensajes, si faltara cualquier información del paciente, se podría realizar una llamada a una base de datos de registros de pacientes en la orquestación y agregar la información que falta, use la información adicional para completar la asignación. Por ejemplo, podría recuperar la dirección particular de un paciente de la base de datos de registros de paciente, puesto que el mensaje de evento de desencadenador de entrada XML timbre no ha proporcionado.  
  
    Continúe con [paso 9: validar y compilar el proyecto de mapa](../../adapters-and-accelerators/accelerator-hl7/step-9-validate-and-build-the-map-project.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial de enriquecimiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)