---
title: Crear o editar una configuración de procesos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process configuration, modifying
- process configuration, creating
- creating, process configuration
- modifying, process configuration
ms.assetid: 39cc2c93-0986-48d3-8c6f-4280ec9af4e0
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9130ab7370f8f6e1fcbe75bc7a85a6c74dfe328
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207124"
---
# <a name="creating-or-editing-a-process-configuration"></a>Crear o editar una configuración de procesos
Esta sección describe cómo crear o editar una configuración de procesos para implementar un proceso de interfaz de socio (PIP) en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]. Un PIP de RosettaNet define un cuadro de diálogo de proceso empresarial entre dos socios comerciales. En [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], para crear una PIP con un socio comercial, primero debe crear una configuración de procesos. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Este perfil se usa para almacenar todas las características de la configuración del PIP. A continuación, puede usar esta configuración para crear un acuerdo con el socio comercial.  
  
 Para obtener información sobre propiedades de configuración de procesos y procedimientos para crear o editar una configuración de procesos, vea [cómo crear o editar una configuración de procesos](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).  
  
 Al crear una nueva configuración de proceso, se debe basar la configuración en el documento de especificación de PIP mantenida por la organización RosettaNet. Configuración procede de las especificaciones de PIP, toda la configuración del proceso y [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] rellena la mayoría de los parámetros con valores predeterminados que son los valores utilizados normalmente para los campos. Debe comprobar que la configuración se corresponde con los valores de la especificación de PIP adecuado. Para obtener más información acerca de cómo se asignan los valores de PIP que especifique para las instrucciones de la especificación de PIP, consulte [mediante la especificación de PIP para crear una configuración de procesos](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md).  
  
 La configuración del proceso puede ser para RosettaNet o CIDX (intercambio de datos de la industria química). Para obtener información acerca de una configuración CIDX, consulte [normas europeas de configuración seguridad CIDX intercambio de mensajes](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md).  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]no admite el cambio de una configuración de procesos mientras hay procesos activos. Si lo hace, los procesos activos se completarán con errores. Todos los nuevos procesos correctamente recogerá la nueva configuración.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo crear o editar una configuración de procesos](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)  
  
-   [Mediante la especificación de PIP para crear una configuración de procesos](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md)  
  
-   [Propiedades de autorización y sin repudio](../../adapters-and-accelerators/accelerator-rosettanet/authorization-and-non-repudiation-properties.md)  
  
-   [Normas europeas de configuración seguridad CIDX intercambio de mensajes](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md)