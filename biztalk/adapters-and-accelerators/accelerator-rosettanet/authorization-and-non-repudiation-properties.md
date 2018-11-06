---
title: Propiedades de autorización y sin repudio | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- authorization properties
- non-repudiation, properties
ms.assetid: e752b95b-9dae-4403-8f3e-3a0a50acd519
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d7088b25ec2526c19c60d21c9929afb92be42a7
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752764"
---
# <a name="authorization-and-non-repudiation-properties"></a>Propiedades de autorización y sin repudio
Este tema describe el comportamiento de las propiedades `Is Authorization Required`, `Non-Repudiation of Origin and Content`, y `Non-Repudiation Required (Acknowledgement of Receipt)` de los procesos de interfaz de socio (PIP). También se describen las combinaciones de estas propiedades que Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] admite.  

 Estas propiedades se establecen en la ficha **Actividad** de las propiedades de configuración del proceso en la sección de configuración del proceso de la consola de administración de [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] . Para obtener más información, consulte [cómo crear o editar una configuración de procesos](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).  

## <a name="property-behavior"></a>Comportamiento de la propiedad  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] muestra el siguiente comportamiento según la configuración de las propiedades `Is Authorization Required`, `Non-Repudiation of Origin and Content` y `Non-Repudiation Required (Acknowledgement of Receipt)`.  


|                        Property                         |                                                                                                                                                                             Comportamiento cuando es True                                                                                                                                                                             |                                                                               Comportamiento cuando es False                                                                               |
|---------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|               `Is Authorization Required`               | Los mensajes entrantes de acción o señal deben estar firmados; de lo contrario, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] rechazará el mensaje. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] no acepta el documento empresarial si el usuario o el rol no está autorizado para realizar la actividad. | No es necesario que los mensajes entrantes de señal o acción estén firmados. Se aplicará la autorización sencilla con el número DUNS del socio de las partes del encabezado RNIF del mensaje. |
|         `Non-Repudiation of Origin and Content`         |                                                                                                Los mensajes de acción o señal salientes se firmarán. Los mensajes de acción se almacenarán en su forma de recepción original en la tabla MessageStorageOut de la base de datos BTARNDATA.                                                                                                 |                                                             Los mensajes de acción o señal salientes no se almacenarán.                                                              |
| `Non-Repudiation Required (Acknowledgement of Receipt)` |                                                                                 Los mensajes entrantes de acción o señal deben estar firmados. El mensaje entrante se almacenará en la tabla MessageStorageIn en la base de datos BTARNDATA. Debe incluirse una síntesis del mensaje en la confirmación.                                                                                  |                                                             Los mensajes de acción o señal entrantes no se almacenarán.                                                              |

## <a name="property-support"></a>Compatibilidad con propiedades  
 La siguiente tabla muestra la compatibilidad de [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] con las combinaciones de las propiedades `Is Authorization Required`, `Non-Repudiation of Origin and Content` y `Non-Repudiation Required (Acknowledgement of Receipt)`.  

> [!IMPORTANT]
>  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] debe firmar tanto los mensajes de acción como los mensajes de señal o bien no firmar ni los mensajes de acción ni los mensajes de señal. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] admite la firma de acciones, pero no la firma de señales, o viceversa.  
> 
> [!IMPORTANT]
>  Si [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] firma un mensaje saliente, debe guardar el mensaje en la tabla MessageStorageOut de la base de datos BTARNArchive.  

|Is Authorization Required|Non-Repudiation of Origin and Content|Non-Repudiation Required (Acknowledgement of Receipt)|¿Compatible con BTARN?|  
|-------------------------------|--------------------------------------------|--------------------------------------------------------------|-------------------------|  
|`False`|`False`|`False`|Sí|  
|`False`|`False`|`True`|No\*|  
|`False`|`True`|`False`|No\*\*|  
|`False`|`True`|`True`|No\*\*\*|  
|`True`|`False`|`False`|Sí\*\*\*\*|  
|`True`|`False`|`True`|Sí\*\*\*\*|  
|`True`|`True`|`False`|Sí|  
|`True`|`True`|`True`|Sí|  

 \* [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] no se admite esta combinación porque requiere que se firmen las señales de las acciones no esté firmado.  

 \*\* [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] no se admite esta combinación porque requiere que las acciones se firmen las señales no.  

 \*\*\* [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] no se admite esta combinación porque si se establece sin repudio en `True` para acciones y las señales significa que [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] realiza la autorización. Por lo tanto, esta combinación no es válida.  

 \*\*\*\* Al establecer `Is Authorization Required` a `True` y `Non-Repudiation of Origin and Content` a `False`, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] almacena el mensaje en la tabla sin repudio.  

## <a name="see-also"></a>Vea también  
 [Cómo crear o editar una configuración de procesos](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)