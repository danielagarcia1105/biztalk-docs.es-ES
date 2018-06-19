---
title: Configurar una solución CIDX | Documentos de Microsoft
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
ms.openlocfilehash: ab617efc701551f1d5bcbae2a292676cc4f33251
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210916"
---
# <a name="setting-up-a-cidx-solution"></a>Cómo configurar una solución CIDX
Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] compatibilidad con intercambio de mensajes XML CIDX (intercambio de datos de la industria química) (normas europeas de química CIDX las versiones 2.0 y 3.0). Este tema describe cómo configurar una solución CIDX haciendo lo siguiente:  
  
-   Cómo configurar una configuración de procesos  
  
-   Cómo configurar un acuerdo  
  
-   Aplicar un PIP  
  
-   Importar un PIP basado en XSD  
  
-   Conectarse a la red Elemica  
  
## <a name="setting-up-a-cidx-process-configuration"></a>Cómo configurar una configuración de procesos CIDX  
 Para configurar un intercambio de mensajes de normas europeas CIDX, debe crear una configuración de proceso que tiene las siguientes propiedades:  
  
-   **Estándar** propiedad en los valores de configuración de proceso establecido en **CIDX**  
  
-   **Es la única acción** propiedad en los valores de configuración de proceso establecido en **es True**  
  
-   **Acuerdo de 0A1** propiedad en el acuerdo de socio comercial establecido en **No 0A1**  
  
 Para obtener más información, consulte [normas europeas de configuración seguridad CIDX intercambio de mensajes](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md).  
  
## <a name="creating-a-cidx-agreement"></a>Crear un acuerdo CIDX  
 Para configurar un intercambio de mensajes de normas europeas CIDX, debe crear un acuerdo que tiene las siguientes propiedades:  
  
-   **Versión de RNIF** propiedad en la configuración del acuerdo establecido en **V01.10.00**  
  
-   **Acuerdo de 0A1** propiedad en la configuración del acuerdo establecido en **No 0A1**  
  
 Para obtener más información, consulte [crear o editar un acuerdo](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).  
  
## <a name="applying-a-pip-for-cidx"></a>Aplicar un PIP para CIDX  
 Para aplicar un PIP a una implementación CIDX, establezca el **estándar** propiedad en el perfil de configuración de proceso a **CIDX**. Cuando haya terminado, podrá especificar valores para la **estándar de mensajes**, **versión estándar**, y **Id. de enlace de carga**. Puede encontrar estos valores en la especificación de normas europeas de química CIDX.  
  
## <a name="importing-an-xsd-based-pip-for-cidx"></a>Importar una PIP basado en XSD para CIDX  
 Para importar una PIP basado en XSD para CIDX, necesitará descargar el archivo ZIP del PIP de CIDX.org en [http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=62361). Siga el procedimiento de importación se describe en [importar una PIP basado en XSD](../../adapters-and-accelerators/accelerator-rosettanet/importing-an-xsd-based-pip.md).  
  
## <a name="connecting-to-the-elemica-network"></a>Conectarse a la red Elemica  
 Puede personalizar [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] para conectarse a Elemica con archivos de proyecto en el módulo de conectividad Elemica. Puede descargar el módulo de conectividad de [http://go.microsoft.com/fwlink/?LinkId=46195](http://go.microsoft.com/fwlink/?LinkId=46195). Para obtener más información, vea las notas del producto "Conectando con la red Elemica con el Acelerador de BizTalk para RosettaNet 3.0" en MSDN en [http://go.microsoft.com/fwlink/?linkid=46539](http://go.microsoft.com/fwlink/?linkid=46539).  
  
> [!NOTE]
>  La información en las notas del producto "Conectando con la red Elemica con el Acelerador de BizTalk para RosettaNet 3.0" es válida para [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)].  
  
## <a name="see-also"></a>Vea también  
 [Compatibilidad con CIDX](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md)   
 [Estándares de mensajería CIDX](../../adapters-and-accelerators/accelerator-rosettanet/cidx-messaging-standards.md)   
 [Normas europeas de configuración seguridad CIDX intercambio de mensajes](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md)   
 [Crear o editar un acuerdo](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)   
 [Importar una PIP basado en XSD](../../adapters-and-accelerators/accelerator-rosettanet/importing-an-xsd-based-pip.md)