---
title: Implementación de PIP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PIPs
- PIPs, element-level constraints
- Document Type Definitions (DTDs)
- PIPs, schemas
- examples, schemas
- schemas, examples
- PIPs, about PIPs
- element-level constraints
- PIPs, DTDs
- schemas, PIPs
- XML Schema Definition files (XSDs)
- Partner Interface Processes (PIPs)
- DTDs, XSDs
- schemas, XSDs
ms.assetid: 0d964223-e0b6-4377-b26a-5fdc89ec81f4
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef7ab139b7efe94df33f393554814c8f7e59efcb
ms.sourcegitcommit: 436ebffd959a9c4bdaafd4da9a5843c59a018eb7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2018
ms.locfileid: "34855551"
---
# <a name="pip-implementation"></a>Implementación de PIP
Procesos de interfaz de socio (PIP) RosettaNet definir procesos empresariales entre socios comerciales en una cadena de suministro. [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Proporciona un conjunto de PIP de cuadro y puede crear PIP adicionales. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] es compatible con todos los PIP definido por la organización RosettaNet.  
  
 Para obtener más información, consulte [PIP de RosettaNet](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md).  
  
## <a name="schemas-in-btarn"></a>Esquemas de BTARN  
 RosettaNet especifica todos los esquemas de mensaje PIP en forma de definiciones de tipo de documento (DTD). Los socios comerciales que participan en el intercambio de documentos empresariales deben obedecer estas DTD. Sin embargo, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] implementa estas DTD como archivos de definición de esquemas XML (XSD), dado que Microsoft BizTalk Server representa documentos mediante XSD, no las DTD. XSD sustituir las DTD en términos de funcionalidad y puede representar la mayoría de la información proporcionada en las directrices de los mensajes de forma nativa.  
  
> [!NOTE]
>  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] También es compatible con PIP de próxima generación, publicada recientemente por la organización RosettaNet, que usan las especificaciones de XSD.  
  
 Para implementar un PIP nueva, debe convertir DTD del PIP en XSD. Descargar la DTD asociada del PIP desde el sitio RosettaNet Web en [ http://go.microsoft.com/fwlink/?linkid=33859 ](http://go.microsoft.com/fwlink/?linkid=33859). A continuación, cree un [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] procesar el perfil de configuración basado en el PIP. Para obtener más información, consulte [incorpora un nuevo proceso de interfaz de socio comercial](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md).  
  
 Puede crear un nuevo perfil de configuración de proceso basado en un perfil existente. Para obtener más información, consulte [cómo crear o editar una configuración de procesos](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md). Puede crear varios contratos basados en el mismo perfil de configuración de proceso entre los mismos asociados. Sin embargo, solo puede activar uno de ellos a la vez. Para crear y activar un acuerdo, vea [crear o editar un acuerdo](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] implementa XSD con las restricciones de instrucciones del mensaje de RosettaNet para los encabezados de RosettaNet siguientes:  
  
-   Preámbulo para RNIF 1.1 y RNIF 2.01  
  
-   Encabezado de servicio para RNIF 1.1 y RNIF 2.0  
  
-   Encabezado de entrega para RNIF 2.0  
  
-   Contenido del servicio para todos los mensajes de señal de RNIF 1.1 y RNIF 2.01.  
  
## <a name="sample-schemas"></a>Esquemas de ejemplo  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] el programa de instalación instala un conjunto de PIP en \< *unidad*\>: \Program BizTalk \<versión\> Accelerator for RosettaNet\SDK\Schemas. Se trata únicamente con fines de ejemplo. Antes de utilizarlos en producción, se recomienda encarecidamente que comparar estos esquemas con las especificaciones de PIP de RosettaNet más reciente publicadas y directrices de los mensajes. BTARN admite implementación de todos los PIP de RosettaNet.  
  
## <a name="element-level-constraints-in-btarn"></a>Restricciones de nivel de elemento de BTARN  
 En BTARN, implemente las restricciones de nivel de elemento especificadas en los documentos de instrucciones del mensaje PIP como procesar los valores de configuración. Componentes de tiempo de ejecución utilizan la configuración del proceso para determinar cómo procesar un PIP específico.  
  
 Para implementar un PIP nueva, debe aplicar las restricciones de la regla de mensaje para el PIP mediante la creación de un nuevo perfil de configuración de proceso. Para ello, en la consola de administración de BTARN. Para obtener más información, consulte [cómo crear o editar una configuración de procesos](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).  
  
 El perfil de configuración de proceso se asigna a la especificación de PIP de RosettaNet, como se muestra en [mediante la especificación de PIP para crear una configuración de procesos](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md).  
  
## <a name="see-also"></a>Vea también  
 [Lo que agrega el Acelerador de BizTalk para RosettaNet a BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md)   
 [Acuerdos de socios comerciales](../../adapters-and-accelerators/accelerator-rosettanet/trading-partner-agreements.md)   
 [PIP de RosettaNet](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-pips.md)
