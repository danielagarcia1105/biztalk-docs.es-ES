---
title: 'Paso 10: Crear una orquestación | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, creating
- creating, orchestrations
- message enrichment tutorial, orchestrations
ms.assetid: 10f5cf3d-4a34-4c80-89d1-c390552cfc09
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfc554a6f3c94a077b34ae79a36b8e484eadcd5d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206572"
---
# <a name="step-10-create-an-orchestration"></a>Paso 10: Crear una orquestación
En este paso, se utiliza el Diseñador de orquestaciones para crear una orquestación para representar el proceso empresarial para recuperar los detalles del paciente adicionales para llenar totalmente un mensaje ADT_A04. Con el Diseñador de orquestaciones, se seleccionan las formas de orquestación necesarias para representar acciones para este proceso empresarial. De ejercicios posteriores, se proporciona información adicional para configurar las formas para que pueda funcionar correctamente.  
  
> [!NOTE]
>  La orquestación creada en los pasos siguientes solo funciona en el contexto de este tutorial. En el orden de la orquestación para que funcione correctamente, necesita las referencias de ensamblado, mapas y los demás artefactos que cree durante el uso de este tutorial.  
  
### <a name="to-create-an-orchestration"></a>Para crear una orquestación  
  
1.  En el Explorador de soluciones, haga clic en **BTAHL7 proyecto**, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
2.  En el **Agregar nuevo elemento** cuadro de diálogo, en la **categorías** panel, haga clic en **archivos de orquestación**.  
  
3.  En el **plantillas** panel, haga clic en **orquestación de BizTalk**.  
  
4.  En el **nombre** , escriba **timbre Orchestration.odx** (tenga en cuenta que hay un espacio entre la palabra **timbre** y **orquestación** ) como nombre de la orquestación y, a continuación, haga clic en **agregar** para crear un nuevo archivo de orquestación.  
  
5.  En el **vista** menú, haga clic en **cuadro de herramientas**.  
  
6.  En el **cuadro de herramientas** , arrastre el **recepción** dar forma a la superficie de la vista de diseño y colóquela en el área con la etiqueta **coloca una forma en el cuadro de herramientas aquí**.  
  
7.  En la ventana de propiedades (en la parte inferior derecha de la pantalla), haga clic en el **nombre** propiedad y el tipo **DoorbellReceive** como el nombre de la **recepción** forma y, a continuación, presione  **Escriba**.  
  
8.  En la ventana Propiedades, cambie la **activar** propiedad **True**.  
  
9. Arrastre el **transformar** forma del cuadro de herramientas y colóquelo directamente debajo del **DoorbellReceive** forma.  
  
10. En la ventana de propiedades (en la parte inferior derecha de la pantalla), haga clic en el **nombre** propiedad para cambiar el nombre de la **transformar** dar forma a **DoorbellTransform**y, a continuación, presione **Escriba**.  
  
11. En el **cuadro de herramientas** , arrastre el **asignación de mensajes** dar forma a la superficie de la vista de diseño y colóquela en el área situada directamente debajo del **ConstructMessage_1** forma.  
  
12. En la superficie de la vista de diseño de orquestación, haga clic en el **MessageAssignment_1** forma y en el **propiedades** panel, haga clic en **nombre** y escriba el nuevo nombre  **DoorbellFinalTransform**y, a continuación, presione **ENTRAR**.  
  
13. Arrastre el **enviar** forma del cuadro de herramientas y colóquela en la línea de conexión directamente debajo del **DoorbellFinalTransform** forma.  
  
14. En la ventana de propiedades (en la parte inferior derecha de la pantalla), haga clic en el **nombre** propiedad para cambiar el nombre de la **enviar** dar forma a **DoorbellSend**y, a continuación, presione  **Escriba**.  
  
 Continúe con [paso 11: crear Variables de orquestación](../../adapters-and-accelerators/accelerator-hl7/step-11-create-orchestration-variables.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial de enriquecimiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)