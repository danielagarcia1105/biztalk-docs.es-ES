---
title: Huella digital del certificado de cliente válido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f18fa0a2-b0d9-4190-aa96-12ab7007edd1
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74551ac825f9e517bec1d07edc7f288db732b348
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018886"
---
# <a name="invalid-client-certificate-thumbprint"></a>Huella digital de certificado de cliente no válida
## <a name="details"></a>Detalles  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  Nombre del producto   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| Versión del producto |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    Identificador del evento     |                                         0                                          |
|  Origen del evento   |                                         0                                          |
|    Componente    |                                         0                                          |
|  Nombre simbólico  |                                         0                                          |
|  Texto del mensaje   |       Huella digital de certificado no válida; se esperaban 40 dígitos hexadecimales.       |
  
## <a name="explanation"></a>Explicación  
 Se especificó una huella digital de certificado de cliente no válida.  
  
## <a name="user-action"></a>Acción del usuario  
 En el código que configura el puerto de envío WCF, la propiedad de certificado de cliente de la interfaz de usuario espera un valor de 40 dígitos hexadecimales. Ejemplo: 798A68E7A3E6F2CCC6929FC4AF2A15A9EED66E39  
  
 Para obtener más información sobre certificados, vea lo siguiente:  
  
-   [Instalación de certificados para los adaptadores de WCF](../core/installing-certificates-for-the-wcf-adapters.md)