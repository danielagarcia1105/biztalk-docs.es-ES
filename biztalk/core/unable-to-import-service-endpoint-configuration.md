---
title: No se puede importar la configuración de extremo de servicio | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6dae5154-04e2-4d9b-b2b2-85313683fd9e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d33b9b4963b69ed732c16e266300e398d7884035
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994317"
---
# <a name="unable-to-import-service-endpoint-configuration"></a>No se puede importar la configuración de extremo de servicio
## <a name="details"></a>Detalles  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  Nombre del producto   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| Versión del producto |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    Identificador del evento     |                                         0                                          |
|  Origen del evento   |                                         0                                          |
|    Componente    |                                         0                                          |
|  Nombre simbólico  |                                         0                                          |
|  Texto del mensaje   |                  No se puede importar la configuración de extremo de servicio.                   |
  
## <a name="explanation"></a>Explicación  
 Es posible que haya más de una explicación para este error. El archivo de configuración puede contener caracteres no válidos. Es posible que falte el elemento raíz. Es posible que los datos en el nivel de raíz no sean válidos.  
  
## <a name="user-action"></a>Acción del usuario  
 Compruebe la validez del archivo de configuración. Intente abrir el archivo de configuración con el Editor de configuración de servicio (**svcConfigEditor.exe**) y compruebe todas las propiedades.