---
title: Ejemplos de esquema | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SDK samples, schemas
- examples, schemas
- schemas, examples
ms.assetid: 7d7e696d-935f-4582-b873-c5637673b651
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4f8070c260c3972b2e8eef58af538932f1c5bf6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="schema-samples"></a>Ejemplos de esquema
El [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK incluye una serie de esquemas XSD para el procesamiento de RNIF y proceso de interfaz de socio (PIP). [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]utiliza estos esquemas para procesar mensajes. Puede modificar estos esquemas para sus propios fines o usarlos para solucionar errores.  
  
 El [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK proporciona tres conjuntos de esquemas. Estos esquemas son esquemas XSD asociados con PIP de RosettaNet, esquemas de próxima generación de RosettaNet y esquemas RNIF.  
  
## <a name="xsd-schemas-associated-with-rosettanet-pips"></a>Esquemas XSD asociados con PIP de RosettaNet  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]estos esquemas se utiliza para validar el contenido del servicio de instancias de mensaje. Puede modificar estos esquemas para cambiar el procesamiento de mensajes. También puede utilizar los esquemas para validar las instancias de mensaje al solucionar problemas de errores en el procesamiento de contenido del servicio.  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]se compila estos esquemas en el ensamblado Rnpip. Puede modificar cualquiera de estos esquemas al anular la implementación del ensamblado Rnpip, cambiar el esquema y, a continuación, volver a implementar Rnpip. Debe tener cuidado de que no cambian el esquema. Si cambia el esquema, los cambios no pueden cumplir el PIP de RosettaNet correspondiente. También puede agregar un esquema a Rnpip. Para obtener más información, consulte [modificar un PIP existente en Rnpip](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md).  
  
 El [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] programa de instalación instala estos esquemas en \< *unidad*\>: \Program archivos\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<versión\> Acelerador para RosettaNet\SDK\Schemas.  
  
## <a name="rnif-schemas"></a>Esquemas RNIF  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]estos esquemas se utiliza para validar las partes de mensaje RNIF, como el preámbulo, encabezado de servicio y encabezado de entrega. También se incluyen los esquemas para las confirmaciones y las excepciones.  
  
 El [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] programa de instalación instala estos esquemas en \< *unidad*\>: \Program archivos\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<versión\> Acelerador para RosettaNet\SDK\RNIFSchemas.  
  
## <a name="rosettanet-next-generation-schemas"></a>Esquemas de RosettaNet de próxima generación  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]estos esquemas se utiliza para validar los mensajes sean conformes a los esquemas de próxima generación para RosettaNet. Estos esquemas admiten XSD de forma nativa, en lugar de DTD. Para utilizar estos esquemas, agréguelos al ensamblado Rnpip como se describe en [modificar un PIP existente en Rnpip](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md).  
  
 El [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] programa de instalación instala estos esquemas en el \< *unidad*\>: \Program archivos\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<versión\> Acelerador para Carpetas RosettaNet\SDK\Schemas\Domain, \Interchange y \Universal.  
  
## <a name="see-also"></a>Vea también  
 [Implementación de PIP](../../adapters-and-accelerators/accelerator-rosettanet/pip-implementation.md)   
 [Trabajar con PIP](../../adapters-and-accelerators/accelerator-rosettanet/working-with-pips.md)   
 [Ejemplos](../../adapters-and-accelerators/accelerator-rosettanet/samples3.md)