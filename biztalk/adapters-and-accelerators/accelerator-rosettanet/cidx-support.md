---
title: Compatibilidad con CIDX | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- CIDX, procedures
- CIDX, about CIDX
- CIDX, Elemica Exchange Server Provider (ESP)
- CIDX, PIPs
- CIDX
- Elemica Exchange Server Provider (ESP)
- procedures [CIDX]
- PIPs, CIDX
ms.assetid: 58b75ad3-f6b9-47c0-8dbf-506a3eaf010b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57500dc25e719d7ef693975b74850cbc04289dec
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997813"
---
# <a name="cidx-support"></a>Compatibilidad con CIDX
Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] proporciona compatibilidad para el intercambio de mensajes XML CIDX (intercambio de datos de la industria química). [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] es compatible con las normas europeas de química CIDX las versiones 2.0 y 3.0, que utilizan el marco de implementación de RosettaNet (RNIF) 1.1.  
  
 El [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] asincrónicos simple los procesos públicos (compatibilidad con mensajes de acción única y de doble acción), consumir y enrutar el contenido del servicio CIDX.  
  
 Para un contrato basado en un PIP CIDX, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] validará lo siguiente en un mensaje:  
  
- Solo la versión de RNIF 1.1  
  
- No hay 0A1  
  
- Acción de un solo  
  
  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] no le impedirá configuración la `Standard` propiedad para una configuración de procesos para "CIDX" después de haber establecido el `0A1 agreement` propiedad para un acuerdo que utilizará dicho perfil a "0A1" (que no se admite para CIDX). [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] no se realiza la validación de campos cruzados que lo impedirían.  
  
## <a name="applying-a-pip-to-a-cidx-implementation"></a>Aplicar un PIP a una implementación de CIDX  
 Para aplicar un PIP a una implementación CIDX, establezca el `Standard` propiedad en el perfil de configuración de proceso a **CIDX**. Cuando haya terminado, podrá especificar valores para el estándar de mensajes, la versión estándar y el identificador de enlace de carga. Puede encontrar estos valores en la especificación de las normas europeas de química CIDX.  
  
## <a name="connecting-to-the-elemica-network"></a>Conectarse a la red Elemica  
 Puede permitir que una instalación de Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] para conectarse a la Elemica [!INCLUDE[btsExchangeSvrNoVersion](../../includes/btsexchangesvrnoversion-md.md)] proveedor (ESP). Puede usar la red Elemica para la industria de sustancias químicas comprar, vender y administración de la cadena de suministro mediante CIDX intercambio de mensajes.  
  
 Personaliza [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] para conectarse a Elemica mediante archivos de proyecto en el módulo de conectividad Elemica. Puede descargar el módulo de conectividad del [ http://go.microsoft.com/fwlink/?LinkId=46195 ](http://go.microsoft.com/fwlink/?LinkId=46195). Para obtener más información, consulte las notas del producto "Conectando con la red Elemica con el Acelerador de BizTalk para RosettaNet 3.0" en MSDN en [ http://go.microsoft.com/fwlink/?linkid=46539 ](http://go.microsoft.com/fwlink/?linkid=46539).  
  
> [!NOTE]
>  La información de las notas del producto "Conectando con la red Elemica con el Acelerador de BizTalk para RosettaNet 3.0" es válida para [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)].  
  
## <a name="cidx-procedures"></a>Procedimientos CIDX  
 Las secciones siguientes describen cómo configurar el intercambio de mensajes CIDX:  
  
-   [Configuración del intercambio de mensajes de normas europeas de intercambio de datos para CIDX](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md)  
  
-   [Creación o edición de un acuerdo](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)  
  
-   [Importación de un PIP basado en XSD](../../adapters-and-accelerators/accelerator-rosettanet/importing-an-xsd-based-pip.md)  
  
## <a name="see-also"></a>Vea también  
 [Qué agrega el Acelerador de BizTalk para RosettaNet a BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md)   
 [Estándares de mensajería de CIDX](../../adapters-and-accelerators/accelerator-rosettanet/cidx-messaging-standards.md)