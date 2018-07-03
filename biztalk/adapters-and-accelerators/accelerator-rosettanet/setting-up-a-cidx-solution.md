---
title: Configuración de una solución CIDX | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- CIDX, process configuration
- creating, CIDX solutions
- CIDX, connecting to Elemica network
- agreements, CIDX
- process configuration, CIDX
- CIDX, agreements
- PIPs, importing for CIDX
- CIDX, PIPs
- CIDX, creating solutions
- CIDX, importing PIPs
- PIPs, CIDX
ms.assetid: 7f1f159f-3b09-4efd-907b-9a75f7f3ecd1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 770691b2862aba307e6f1cc444c8d38adce4aeb4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984293"
---
# <a name="setting-up-a-cidx-solution"></a>Configuración de una solución CIDX
Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] compatibilidad con intercambio de mensajes XML CIDX (intercambio de datos de la industria química) (normas europeas de química CIDX las versiones 2.0 y 3.0). Este tema describe cómo configurar una solución CIDX haciendo lo siguiente:  
  
-   Configuración de una configuración de procesos  
  
-   Configuración de un acuerdo  
  
-   Aplicar un PIP  
  
-   Importar un PIP basado en XSD  
  
-   Conectarse a la red Elemica  
  
## <a name="setting-up-a-cidx-process-configuration"></a>Una configuración de proceso CIDX  
 Para configurar un intercambio de mensajes de las normas europeas CIDX, deberá crear una configuración de proceso que tiene las siguientes propiedades:  
  
- **Estándar** propiedad en las opciones de configuración de proceso establecido en **CIDX**  
  
- **Es la única acción** propiedad en las opciones de configuración de proceso establecido en **True**  
  
- **Acuerdo de 0A1** propiedad en el acuerdo entre socios comerciales que se establece en **ningún 0A1**  
  
  Para obtener más información, consulte [configuración CIDX las normas europeas de intercambio de mensajes](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md).  
  
## <a name="creating-a-cidx-agreement"></a>Creación de un acuerdo CIDX  
 Para configurar un intercambio de mensajes de las normas europeas CIDX, deberá crear un acuerdo que tiene las siguientes propiedades:  
  
- **Versión de RNIF** propiedad en la configuración del contrato establecido en **V01.10.00**  
  
- **Acuerdo de 0A1** propiedad en la configuración del contrato establecido en **No 0A1**  
  
  Para obtener más información, consulte [crear o editar un acuerdo](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).  
  
## <a name="applying-a-pip-for-cidx"></a>Aplicar un PIP para CIDX  
 Para aplicar un PIP a una implementación CIDX, establezca el **estándar** propiedad en el perfil de configuración de proceso a **CIDX**. Cuando haya terminado, podrá especificar valores para el **estándar de mensajes**, **versión estándar**, y **Id. de enlace de carga**. Puede encontrar estos valores en la especificación de las normas europeas de química CIDX.  
  
## <a name="importing-an-xsd-based-pip-for-cidx"></a>Importar un PIP basado en XSD para CIDX  
 Para importar un PIP basado en XSD para CIDX, deberá descargar el archivo ZIP del PIP de CIDX.org en [ http://go.microsoft.com/FWLink/?LinkID=33859 ](http://go.microsoft.com/FWLink/?LinkID=62361). Siga el procedimiento de importación se describe en [importar un PIP basado en XSD](../../adapters-and-accelerators/accelerator-rosettanet/importing-an-xsd-based-pip.md).  
  
## <a name="connecting-to-the-elemica-network"></a>Conectarse a la red Elemica  
 Puede personalizar [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] para conectarse a Elemica mediante archivos de proyecto en el módulo de conectividad Elemica. Puede descargar el módulo de conectividad del [ http://go.microsoft.com/fwlink/?LinkId=46195 ](http://go.microsoft.com/fwlink/?LinkId=46195). Para obtener más información, consulte las notas del producto "Conectando con la red Elemica con el Acelerador de BizTalk para RosettaNet 3.0" en MSDN en [ http://go.microsoft.com/fwlink/?linkid=46539 ](http://go.microsoft.com/fwlink/?linkid=46539).  
  
> [!NOTE]
>  La información de las notas del producto "Conectando con la red Elemica con el Acelerador de BizTalk para RosettaNet 3.0" es válida para [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)].  
  
## <a name="see-also"></a>Vea también  
 [Compatibilidad con CIDX](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md)   
 [Estándares de mensajería de CIDX](../../adapters-and-accelerators/accelerator-rosettanet/cidx-messaging-standards.md)   
 [Configuración CIDX las normas europeas de intercambio de mensajes](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md)   
 [Crear o editar un acuerdo](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)   
 [Importación de un PIP basado en XSD](../../adapters-and-accelerators/accelerator-rosettanet/importing-an-xsd-based-pip.md)