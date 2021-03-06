---
title: Con la consola de administración de BTARN | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- agreements, activating
- activating agreements
- BTARN Management Console, Scope pane
- tracking
- creating, trading partners
- BTARN Management Console, agreements
- process configuration
- agreements, modifying
- BTARN Management Console, home organizations
- agreements, creating
- BTARN Management Console, trading partners
- agreements, deleting
- deleting, agreements
- BTARN Management Console
- agreements, listing
- modifying, trading partners
- creating, agreements
- trading partners, creating
- modifying, agreements
- BAM tracking
- Scope pane [BTARN Management Console]
- trading partners, modifying
- trading partners, deleting
- BTARN Management Console, process configurations
- deleting, trading partners
- BTARN Management Console, about BTARN Management Console
- home organizations
ms.assetid: 000ee93d-eb1d-4ff8-a9cf-0547beff027d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b35c054e78f09edbe84d799b7218d4921b83795c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977925"
---
# <a name="using-the-btarn-management-console"></a>Con la consola de administración de BTARN
En este tema se describe cómo administrar [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] desde el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] consola de administración.  
  
 Abra el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console, haga clic en **iniciar**, seleccionando **programas**, seleccionando **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Consola de administración**.  
  
 El panel de ámbito (izquierdo) de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] consola de administración incluye todos [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] los nodos de configuración. El panel de resultados (derecha) incluye todas las instancias específicas de los elementos de configuración que ha seleccionado en el panel de ámbito.  
  
## <a name="operations-in-the-scope-pane"></a>Operaciones en el panel de ámbito  
 Puede realizar las siguientes operaciones en los nodos en el panel de ámbito:  
  
- Establecer el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] enviar y recibir las canalizaciones que desea usar para los puertos de envío asociado. Para obtener más información, consulte [canalizaciones de recepción y envío de configuración de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/setting-btarn-send-and-receive-pipelines.md).  
  
- Habilitar el seguimiento de la supervisión de la actividad económica (BAM). Para obtener más información, consulte [Habilitar seguimiento de BAM](../../adapters-and-accelerators/accelerator-rosettanet/enabling-bam-tracking.md).  
  
- Asegúrese de que cualquier configuración recién importada es visible en la consola haciendo clic en el nodo de configuración en el panel de ámbito y, a continuación, haga clic en **actualizar**.  
  
- Ver columnas adicionales en el panel de resultados haciendo clic con el **configuración del proceso** o **acuerdo** nodo en el panel de ámbito, que apunta a **vista**y, a continuación, al hacer clic en **agregar o quitar columnas**. Mover las columnas entre las columnas disponibles y muestran utilizando el **agregar o quitar** botón. Este comando resulta especialmente útil para los contratos que tienen muchas columnas disponibles que [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] no mostrar de forma predeterminada.  
  
## <a name="process-configurations"></a>Configuraciones del proceso  
 Puede realizar las siguientes operaciones en una configuración de procesos:  
  
-   Agregar una nueva configuración de proceso haciendo clic con el **configuración del proceso** nodo de ámbito, que apunta a **New**y, a continuación, haga clic en **configuración del proceso**. Para obtener más información, consulte [cómo crear o editar una configuración de procesos](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).  
  
-   Editar una configuración de proceso existente haciendo clic en la configuración del proceso en el panel de resultados y, a continuación, haga clic en **propiedades**, o haciendo doble clic en la configuración del proceso. Para obtener más información, consulte [cómo crear o editar una configuración de procesos](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).  
  
-   Eliminar una configuración de proceso existente haciendo clic en la configuración del proceso en el panel de resultados y, a continuación, haga clic en **eliminar**.  
  
-   Crear una nueva configuración de proceso en función de una configuración de proceso existente haciendo clic en la configuración en el panel de resultados que desea basar la nueva configuración y, a continuación, haga clic en **nueva configuración del proceso de copia**. Esto mostrará una nueva **propiedades de configuración de proceso** cuadro de diálogo que se rellena con la configuración de la configuración existente. Escriba un nuevo **mostrar código**y, a continuación, haga clic en **Aceptar** para crear la nueva configuración. Para obtener más información, consulte [mediante la especificación de PIP para crear una configuración de procesos](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md).  
  
-   Mostrar una lista de todos los acuerdos que está asociada una configuración de proceso haciendo clic en la configuración específica en el panel de resultados y, a continuación, haga clic en **mostrar acuerdos**. Esto cambiará el foco a la **acuerdos** nodo en el panel de ámbito y mostrar los contratos asociados en el panel de resultados. Puede revertir a una lista completa de los acuerdos haciendo clic con el **acuerdos** nodo en el panel de ámbito y luego haga clic en **mostrar todo**.  
  
## <a name="home-organizations"></a>Organizaciones principales  
 Puede realizar las siguientes operaciones en la organización principal:  
  
-   Agregar una nueva organización principal haciendo clic con el **organizaciones principales** nodo de ámbito, que apunta a **New**y, a continuación, haga clic en **organización principal**. Para obtener más información, consulte [creación o edición de una organización](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md).  
  
-   Editar una organización principal existente haciendo clic en la organización principal en el panel de resultados y, a continuación, haga clic en **propiedades**, o haciendo doble clic en la organización principal. Para obtener más información, consulte [creación o edición de una organización](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md).  
  
-   Eliminar una organización principal existente haciendo clic en la organización principal en el panel de resultados y, a continuación, haga clic en **eliminar**.  
  
## <a name="partners"></a>Asociados  
 Puede realizar las siguientes operaciones en un asociado:  
  
-   Agregar un nuevo asociado con el botón secundario del **asociados** nodo de ámbito, que apunta a **New**y, a continuación, haga clic en **asociado**. Para obtener más información, consulte [creación o edición de un socio](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md).  
  
-   Editar un asociado existente haciendo clic en el asociado en el panel de resultados y, a continuación, haga clic en **propiedades**, o haciendo doble clic en el asociado. Para obtener más información, consulte [creación o edición de un socio](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md).  
  
-   Eliminar un socio existente haciendo clic en el asociado en el panel de resultados y, a continuación, haga clic en **eliminar**.  
  
## <a name="agreements"></a>Acuerdos  
 Puede realizar las siguientes operaciones en un acuerdo:  
  
-   Agregue un nuevo contrato haciendo clic con el **acuerdos** nodo de ámbito, que apunta a **New**y, a continuación, haga clic en **contrato**. Para obtener más información, consulte [crear o editar un acuerdo](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).  
  
-   Editar un acuerdo existente haciendo clic en el acuerdo en el panel de resultados y, a continuación, haga clic en **propiedades**, o haciendo doble clic en el acuerdo. Para obtener más información, consulte [crear o editar un acuerdo](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).  
  
-   Eliminar un acuerdo existente haciendo clic en el acuerdo en el panel de resultados y, a continuación, haga clic en **eliminar**.  
  
-   Activar un acuerdo haciendo clic en el acuerdo desactivado en el panel de resultados y, a continuación, haga clic en **activar**. Esto permitirá que los mensajes asociados con el acuerdo para enviar o recibir. También puede desactivar un acuerdo para evitar que los mensajes asociados con el acuerdo de envío o recepción.  
  
-   Revertir a una lista completa de los acuerdos, después de mostrar una lista de sólo los contratos que está asociada una configuración de procesos, haciendo clic con el **acuerdos** nodo en el panel de ámbito y luego haga clic en **mostrar todo** .  
  
## <a name="see-also"></a>Vea también  
 [Configuración de envío BTARN y canalizaciones de recepción](../../adapters-and-accelerators/accelerator-rosettanet/setting-btarn-send-and-receive-pipelines.md)   
 [Habilitar el seguimiento de BAM](../../adapters-and-accelerators/accelerator-rosettanet/enabling-bam-tracking.md)   
 [Cómo crear o editar una configuración de procesos](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)   
 [Creación o edición de la organización principal](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md)   
 [Creación o edición de un socio](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md)   
 [Creación o edición de un acuerdo](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)