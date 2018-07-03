---
title: 'Paso 5: Promocionar las propiedades de esquema | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, pomoted properties
- promoted properties
- schemas, promoted properties
ms.assetid: cb51cece-1b65-4ba2-b8e6-ce8b6694cdb6
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60aa8681e9647e592af3173295c3d32e216f1f2d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003221"
---
# <a name="step-5-promote-schema-properties"></a>Paso 5: Promocionar las propiedades de esquema
En este paso, se promocionan las propiedades de esquema para que un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] orquestación puede hacer referencia a esos valores de propiedad que se creación en pasos posteriores. La promoción es un mecanismo que se usa para hacer referencia a un valor específico dentro de una instancia de mensaje y hacerla accesible a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] componentes como orquestación o para fines de enrutamiento por contenidos. Además, es visible de forma Microsoft IntelliSense en el Editor de expresiones de propiedad promocionada [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].  
  
> [!NOTE]
>  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] auditoría y la funcionalidad de registro con la herramienta de mantenimiento de BizTalk y el seguimiento de actividad (HAT) pueden realizar un seguimiento de propiedades promocionadas del esquema único.  
  
### <a name="to-promote-schema-properties"></a>Para promocionar las propiedades de esquema  
  
1. En el Explorador de soluciones, bajo **BTAHL7 proyecto**, haga doble clic en el **DoorBell.xsd** el nodo para abrir el esquema.  
  
2. Haga clic en el **FirstName** elemento de campo, seleccione **promover**y, a continuación, haga clic en **promoción rápida**.  
  
3. Haga clic en **Aceptar** para agregar el esquema de propiedades al proyecto.  
  
   > [!NOTE]
   >  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] Agrega un círculo de color naranja en el icono para el **FirstName** elemento, que indica que el elemento se ha promocionado.  
  
4. Repita estos pasos para promover los siguientes elementos de campo:  
  
   -   **middleName**  
  
   -   **Apellidos**  
  
   -   **SSN**  
  
   > [!IMPORTANT]
   >  Es importante tener en cuenta que un identificador (PID) del paciente promocionar como un número del seguro social (SSN) hace que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] para realizar el seguimiento de esa propiedad para cada mensaje entrante a través del sistema. El inconveniente de esta situación es que la base de datos de seguimiento de mensajes mantiene una copia de los números de seguridad social del paciente. Esto puede crear un problema de seguridad importantes. Debe proteger este almacén de datos con extremo cuidado o evitar por completo la promoción de los datos de PID.  
  
    Para obtener más información sobre el seguimiento de documentos en función de los elementos de esquema que ha promocionado, consulte la Ayuda de BizTalk Server para obtener información sobre el seguimiento de estado y actividad.  
  
   Continúe con [paso 6: validar los esquemas](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md).  
  
## <a name="see-also"></a>Vea también  
 [Tutorial de enriquecimiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)