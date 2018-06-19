---
title: Compatibilidad con CIDX | Documentos de Microsoft
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
ms.openlocfilehash: 224d2b50d132efa67e1cfc24dda2df77fa7d29e3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210700"
---
# <a name="cidx-support"></a>Compatibilidad con CIDX
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] proporciona compatibilidad para el intercambio de mensajes XML CIDX (intercambio de datos de la industria química). [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]es compatible con normas europeas de química CIDX las versiones 2.0 y 3.0, ambos de los cuales utilizan RosettaNet Implementation Framework (RNIF) 1.1.  
  
 El [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] procesos públicos simples asincrónicos (compatibilidad con mensajes de acción única y doble acción) utilizar y distribuir contenido de servicio CIDX.  
  
 Para un acuerdo según un PIP CIDX, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] validará lo siguiente en un mensaje:  
  
-   Solo la versión de RNIF 1.1  
  
-   No hay 0A1  
  
-   Solo acción única  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]no podrá configuración el `Standard` propiedad para una configuración del proceso en "CIDX", después de haber establecido el `0A1 agreement` propiedad para un acuerdo que utilizará dicho perfil a "0A1" (que no se admite para CIDX). [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]no lleva a cabo la validación de campos cruzados que impedirían que esto.  
  
## <a name="applying-a-pip-to-a-cidx-implementation"></a>Aplicar un PIP a una implementación CIDX  
 Para aplicar un PIP a una implementación CIDX, establezca el `Standard` propiedad en el perfil de configuración de proceso a **CIDX**. Cuando haya terminado, podrá especificar valores para el estándar de mensajes, la versión estándar y el identificador de enlace de carga. Puede encontrar estos valores en la especificación de normas europeas de química CIDX.  
  
## <a name="connecting-to-the-elemica-network"></a>Conectarse a la red Elemica  
 Puede habilitar una instalación de [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] para conectarse a la Elemica [!INCLUDE[btsExchangeSvrNoVersion](../../includes/btsexchangesvrnoversion-md.md)] proveedor (ESP). Puede usar la red Elemica para la industria química compra, venta y administración de la cadena de suministro mediante CIDX intercambio de mensajes.  
  
 Personalizar [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] para conectarse a Elemica con archivos de proyecto en el módulo de conectividad Elemica. Puede descargar el módulo de conectividad de [http://go.microsoft.com/fwlink/?LinkId=46195](http://go.microsoft.com/fwlink/?LinkId=46195). Para obtener más información, vea las notas del producto "Conectando con la red Elemica con el Acelerador de BizTalk para RosettaNet 3.0" en MSDN en [http://go.microsoft.com/fwlink/?linkid=46539](http://go.microsoft.com/fwlink/?linkid=46539).  
  
> [!NOTE]
>  La información en las notas del producto "Conectando con la red Elemica con el Acelerador de BizTalk para RosettaNet 3.0" es válida para [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)].  
  
## <a name="cidx-procedures"></a>Procedimientos CIDX  
 En las siguientes secciones se describen cómo configurar el intercambio de mensajes CIDX:  
  
-   [Normas europeas de configuración seguridad CIDX intercambio de mensajes](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md)  
  
-   [Crear o editar un acuerdo](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)  
  
-   [Importar una PIP basado en XSD](../../adapters-and-accelerators/accelerator-rosettanet/importing-an-xsd-based-pip.md)  
  
## <a name="see-also"></a>Vea también  
 [Lo que agrega el Acelerador de BizTalk para RosettaNet a BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md)   
 [Estándares de mensajería CIDX](../../adapters-and-accelerators/accelerator-rosettanet/cidx-messaging-standards.md)